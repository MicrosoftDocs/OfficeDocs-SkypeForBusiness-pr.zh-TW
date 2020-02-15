---
title: Lync Server 2013： 連接埠摘要-調整式合併 edge，使用 NAT 的私人 IP 位址使用 DNS 負載平衡
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: a296c2af-54d4-4b4f-9795-9191baf688cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412756(v=OCS.15)
ms:contentKeyID: 48184955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96bf91dfaf4d231ec64ce1b385983f63b15ee0b6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034715"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a>連接埠摘要-調整式合併 edge、 DNS 負載平衡與 Lync Server 2013 中使用 NAT 的私人 IP 位址

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-12-04_

Lync Server 2013 中，在此案例的架構中所述的 Edge Server 功能是非常類似於項目已在 Lync Server 2010 中實作。 最值得注意的是加入了可延伸訊息及目前狀態通訊協定 (XMPP) 的連接埠 **5269 over TCP** 項目。 Lync Server 2013 選擇性地部署 Edge Server 或 Edge 集區與前端伺服器或前端集區上的 XMPP 閘道伺服器上的 XMPP proxy。

IPv4，除了 Edge Server 現在可支援 IPv6。 但為了清楚說明起見，此案例僅會使用 IPv4。

**企業周邊網路的調整式合併的 edge，具有使用 NAT 的私人 IP 位址**

![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")

<div>

## <a name="port-and-protocol-details"></a>連接埠和通訊協定詳細資料

建議您開啟支援所提供給外部存取的功能所需的連接埠。

適用於任何 edge service 的遠端存取，它是強制雙向輸入/輸出 edge 流量圖所示流向允許的 SIP 流量。 換句話說，來回 Access Edge Service 的 SIP 訊息會涉及立即訊息 (IM)、顯示狀態、Web 會議、音訊/視訊 (A/V) 與同盟等功能。

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a>使用 NAT 的調整式合併 Edge，透過私人 IP DNS 負載平衡的防火牆摘要地址： 外部介面 – 節點 1 與節點 2 (Example)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>角色/通訊協定/TCP 或 UDP/連接埠</th>
<th>來源 IP 位址</th>
<th>目的地 IP 位址</th>
<th>附註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>任何</p></td>
<td><p>XMPP Proxy 服務 （與 Access Edge 服務共用 IP 位址）</p></td>
<td><p>XMPP Proxy 服務接受來自定義之 XMPP 同盟中 XMPP 連絡人的流量</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>XMPP Proxy 服務 （與 Access Edge 服務共用 IP 位址）</p></td>
<td><p>任何</p></td>
<td><p>XMPP Proxy 服務將流量傳送至已定義之 XMPP 同盟中 XMPP 連絡人</p></td>
</tr>
<tr class="odd">
<td><p>Access/HTTP/TCP/80</p></td>
<td><p>Edge Server Access Edge service</p></td>
<td><p>任何</p></td>
<td><p>憑證撤銷/CRL 檢查及擷取</p></td>
</tr>
<tr class="even">
<td><p>Access/DNS/TCP/53</p></td>
<td><p>Edge Server Access Edge service</p></td>
<td><p>任何</p></td>
<td><p>透過 TCP 的 DNS 查詢</p></td>
</tr>
<tr class="odd">
<td><p>Access/DNS/UDP/53</p></td>
<td><p>Edge Server Access Edge service</p></td>
<td><p>任何</p></td>
<td><p>透過 UDP 的 DNS 查詢</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP (TLS) / TCP/443</p></td>
<td><p>任何</p></td>
<td><p>Edge Server Access Edge service</p></td>
<td><p>外部使用者存取從用戶端到伺服器的 SIP 流量</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP (MTLS) / TCP/5061</p></td>
<td><p>任何</p></td>
<td><p>Edge Server Access Edge service</p></td>
<td><p>適用於使用 SIP 的同盟與公用 IM 連線</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP (MTLS) / TCP/5061</p></td>
<td><p>Edge Server Access Edge service</p></td>
<td><p>任何</p></td>
<td><p>適用於使用 SIP 的同盟與公用 IM 連線</p></td>
</tr>
<tr class="odd">
<td><p>Web 會議 /PSOM (TLS) / TCP/443</p></td>
<td><p>任何</p></td>
<td><p>Edge Server Web Conferencing Edge service</p></td>
<td><p>Web 會議媒體</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>Edge Server A / V Edge service</p></td>
<td><p>任何</p></td>
<td><p>所需的同盟與協力廠商執行 Office Communications Server 2007、 Office Communications Server 2007 R2、 Lync Server 2010 和 Lync Server 2013。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59999</p></td>
<td><p>Edge Server A / V Edge service</p></td>
<td><p>任何</p></td>
<td><p>僅適用於同盟需要與執行 Office Communications Server 2007 的協力廠商。</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>任何</p></td>
<td><p>Edge Server A / V Edge service</p></td>
<td><p>僅適用於同盟需要與協力廠商執行 Office Communications Server 2007</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59999</p></td>
<td><p>任何</p></td>
<td><p>Edge Server A / V Edge service</p></td>
<td><p>僅適用於同盟需要與協力廠商執行 Office Communications Server 2007</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN，MSTURN/UDP/3478</p></td>
<td><p>Edge Server A / V Edge service</p></td>
<td><p>任何</p></td>
<td><p>3478 輸出用於判斷 Lync Server 與通訊，以及從 Edge Server 至 Edge Server 的媒體流量的 Edge Server 的版本。 所需的 Lync Server 2010、 Windows Live Messenger 與 Office Communications Server 2007 R2，同盟，以及如果公司內部署多個 Edge 集區。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN，MSTURN/UDP/3478</p></td>
<td><p>任何</p></td>
<td><p>Edge Server A / V Edge service</p></td>
<td><p>透過 UDP/3478 之 STUN/TURN 候選的交涉</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN，MSTURN/TCP/443</p></td>
<td><p>任何</p></td>
<td><p>Edge Server A / V Edge service</p></td>
<td><p>透過 UDP/443 之 STUN/TURN 候選的交涉</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN，MSTURN/TCP/443</p></td>
<td><p>Edge Server A / V Edge service</p></td>
<td><p>任何</p></td>
<td><p>透過 UDP/443 之 STUN/TURN 候選的交涉</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a>使用 NAT 的調整式合併 Edge，透過私人 IP DNS 負載平衡的防火牆摘要地址： 內部介面 – 節點 1 與節點 2 (Example)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>通訊協定/TCP 或 UDP/連接埠</th>
<th>來源 IP 位址</th>
<th>目的地 IP 位址</th>
<th>註解</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>任何 （可定義為前端伺服器位址或執行 XMPP 閘道服務的前端集區 IP 位址）</p></td>
<td><p>Edge Server 內部介面 IP 位址</p></td>
<td><p>從前端伺服器或前端集區上執行的 XMPP 閘道服務的輸出 XMPP 流量</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>任何 （可定義為 Director，Director 集區的 IP 位址、 前端伺服器或前端集區 IP 位址）</p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>輸出 SIP 流量 （來自 Director、 Director 集區的 IP 位址、 前端伺服器或前端集區 IP 位址) 至 Edge Server 內部介面</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>任何 （可定義為 Director，Director 集區的 IP 位址、 前端伺服器或前端集區 IP 位址）</p></td>
<td><p>輸入從 Edge Server 內部介面的 SIP 流量 （至 Director、 Director 集區的 IP 位址、 前端伺服器或前端集區 IP 位址)</p></td>
</tr>
<tr class="even">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>任何 （可定義為前端伺服器 IP 位址或在前端集區中的每個前端伺服器 IP 位址）</p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>從前端伺服器或每個前端伺服器集區中, Edge Server 內部介面的 web 會議流量</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>任何 （可定義為前端伺服器 IP 位址，或前端集區的 IP 位址或任何 Survivable Branch Appliance 或 Survivable Branch 伺服器使用此 Edge Server）</p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>驗證 A / V 使用者 (A / V 驗證服務) 從前端伺服器或前端集區 IP 位址或任何 Survivable Branch Appliance 或 Survivable Branch 伺服器使用此 Edge Server</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>任何</p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>慣用的路徑 a / V 媒體傳輸內部與外部使用者，Survivable Branch Appliance 或 Survivable Branch 伺服器之間</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>任何</p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>後援路徑 a / V 媒體傳輸內部與外部使用者，Survivable Branch Appliance 或 Survivable Branch 伺服器之間，如果無法建立 UDP 通訊、 TCP 用於檔案傳輸及桌面共用</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>任何 （可定義為前端伺服器 IP 位址或主控的中央管理存放區的集區）</p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>從中央管理存放區的 Edge server 的變更的複寫</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>任何</p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>使用 Lync Server 管理命令介面和 Centralized Logging Service 指令程式、 ClsController 命令列 (ClsController.exe) 或代理程式 (ClsAgent.exe) 命令和記錄集合的集中式記錄服務控制站</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>任何</p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>使用 Lync Server 管理命令介面和 Centralized Logging Service 指令程式、 ClsController 命令列 (ClsController.exe) 或代理程式 (ClsAgent.exe) 命令和記錄集合的集中式記錄服務控制站</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>任何</p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>使用 Lync Server 管理命令介面和 Centralized Logging Service 指令程式、 ClsController 命令列 (ClsController.exe) 或代理程式 (ClsAgent.exe) 命令和記錄集合的集中式記錄服務控制站</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a>同盟的防火牆摘要


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>角色/通訊協定/TCP 或 UDP/連接埠</th>
<th>來源 IP 位址</th>
<th>目的地 IP 位址</th>
<th>附註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Access/SIP (MTLS) / TCP/5061</p></td>
<td><p>Access Edge Service 公用 IP 位址</p></td>
<td><p>任何</p></td>
<td><p>適用於使用 SIP 的同盟與公用 IM 連線</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a>防火牆摘要 - 公用立即訊息連線


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>角色/通訊協定/TCP 或 UDP/連接埠</th>
<th>來源 IP 位址</th>
<th>目的地 IP 位址</th>
<th>附註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Access/SIP (MTLS) / TCP/5061</p></td>
<td><p>公用 IM 連線協力廠商</p></td>
<td><p>Edge Server Access Edge service</p></td>
<td><p>適用於使用 SIP 的同盟與公用 IM 連線</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP (MTLS) / TCP/5061</p></td>
<td><p>Edge Server Access Edge service</p></td>
<td><p>公用 IM 連線協力廠商</p></td>
<td><p>適用於使用 SIP 的同盟與公用 IM 連線</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP (TLS) / TCP/443</p></td>
<td><p>用戶端</p></td>
<td><p>Edge Server Access Edge service</p></td>
<td><p>外部使用者存取從用戶端到伺服器的 SIP 流量</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>Edge Server A / V Edge service</p></td>
<td><p>Live Messenger 用戶端</p></td>
<td><p>如果有設定 IM 連線，可與 Windows Live Messenger 用於 A/V 工作階段</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN，MSTURN/UDP/3478</p></td>
<td><p>Edge Server A / V Edge service</p></td>
<td><p>Live Messenger 用戶端</p></td>
<td><p>與 Windows Live Messenger 進行公用 IM 連線時必須使用</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN，MSTURN/UDP/3478</p></td>
<td><p>Live Messenger 用戶端</p></td>
<td><p>Edge Server A / V Edge service</p></td>
<td><p>與 Windows Live Messenger 進行公用 IM 連線時必須使用</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a>可延伸訊息和顯示狀態通訊協定的防火牆摘要


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>通訊協定/TCP 或 UDP/連接埠</th>
<th>來源 (IP 位址)</th>
<th>目的地 (IP 位址)</th>
<th>註解</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>任何</p></td>
<td><p>Edge Server Access Edge service 介面 IP 位址</p></td>
<td><p>XMPP 的標準伺服器對伺服器通訊連接埠。 允許從同盟 XMPP 協力廠商通訊的 Edge Server XMPP proxy</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Edge Server Access Edge service 介面 IP 位址</p></td>
<td><p>任何</p></td>
<td><p>XMPP 的標準伺服器對伺服器通訊連接埠。 可從 Edge Server XMPP proxy 的通訊，讓同盟 XMPP 協力廠商</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>任何</p></td>
<td><p>每個內部 Edge Server 介面 IP</p></td>
<td><p>內部 XMPP 流量從前端伺服器或前端集區上的 XMPP 閘道到 Edge Server 內部 IP 位址或每個 Edge 集區成員的內部 IP 位址</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

