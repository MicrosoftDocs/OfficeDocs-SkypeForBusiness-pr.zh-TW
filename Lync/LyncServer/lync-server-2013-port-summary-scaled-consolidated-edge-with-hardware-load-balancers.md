---
title: 連接埠摘要-調整式合併邊緣搭配硬體負載平衡器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 91213b1e-f875-464b-83e8-fe3a351595a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398739(v=OCS.15)
ms:contentKeyID: 48184841
ms.date: 04/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6af913a6be7b92a7a640a2e06537197ba21351c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183866"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>連接埠摘要-調整式合併邊緣搭配硬體負載平衡器在 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015 年 04 月 27 日_

Lync Server 2013 中，在此案例的架構中所述的 Edge Server 功能是非常類似於項目已在 Lync Server 2010 中實作。 最值得注意的是加入了可延伸訊息及目前狀態通訊協定 (XMPP) 的連接埠 **5269 over TCP** 項目。 Lync Server 2013 選擇性地部署 Edge Server 或 Edge 集區與前端伺服器或前端集區上的 XMPP 閘道伺服器上的 XMPP proxy。

IPv4，除了 Edge Server 現在可支援 IPv6。 但為了清楚說明起見，此案例僅會使用 IPv4。

**調整式合併 Edge，使用硬體負載平衡**

![Edge Server 周邊網路連接埠和通訊協定](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge Server 周邊網路連接埠和通訊協定")

<div>

## <a name="port-and-protocol-details"></a>連接埠和通訊協定詳細資料

建議您開啟支援所提供給外部存取的功能所需的連接埠。

適用於任何 edge service 的遠端存取，它是強制雙向輸入/輸出 edge 流量圖所示流向允許的 SIP 流量。 換句話說，來回 Access Edge Service 的 SIP 訊息會涉及立即訊息 (IM)、顯示狀態、Web 會議、音訊/視訊 (A/V) 與同盟等功能。

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a>調整式合併 Edge，硬體負載平衡的防火牆摘要： 外部介面 – 節點 1 與節點 2 (Example)

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
<td><p>Access/HTTP/TCP/80</p></td>
<td><p>Edge Server Access Edge 服務公用 IP 位址</p></td>
<td><p>任何</p></td>
<td><p>憑證撤銷/CRL 檢查及擷取</p></td>
</tr>
<tr class="even">
<td><p>Access/DNS/TCP/53</p></td>
<td><p>Edge Server Access Edge 服務公用 IP 位址</p></td>
<td><p>任何</p></td>
<td><p>透過 TCP 的 DNS 查詢</p></td>
</tr>
<tr class="odd">
<td><p>Access/DNS/UDP/53</p></td>
<td><p>Edge Server Access Edge 服務公用 IP 位址</p></td>
<td><p>任何</p></td>
<td><p>透過 UDP 的 DNS 查詢</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>Edge Server A / V Edge service IP 位址</p></td>
<td><p>任何</p></td>
<td><p>所需的同盟與協力廠商執行 Office Communications Server 2007、 Office Communications Server 2007 R2、 Lync Server 2010 和 Lync Server 2013。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59999</p></td>
<td><p>Edge Server A / V Edge service 公用 IP 位址</p></td>
<td><p>任何</p></td>
<td><p>僅適用於同盟需要與執行 Office Communications Server 2007 的協力廠商。</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>任何</p></td>
<td><p>Edge Server A / V Edge service 公用 IP 位址</p></td>
<td><p>僅適用於同盟需要與協力廠商執行 Office Communications Server 2007</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59999</p></td>
<td><p>任何</p></td>
<td><p>Edge Server A / V Edge service 公用 IP 位址</p></td>
<td><p>僅適用於同盟需要與協力廠商執行 Office Communications Server 2007</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN，MSTURN/UDP/3478</p></td>
<td><p>Edge Server A / V Edge service 公用 IP 位址</p></td>
<td><p>任何</p></td>
<td><p>3478 輸出用於判斷 Lync Server 與通訊，以及從 Edge Server 至 Edge Server 的媒體流量的 Edge Server 的版本。 所需的 Lync Server 2010、 Windows Live Messenger 與 Office Communications Server 2007 R2，同盟，以及如果公司內部署多個 Edge 集區。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN，MSTURN/UDP/3478</p></td>
<td><p>任何</p></td>
<td><p>Edge Server A / V Edge service 公用 IP 位址</p></td>
<td><p>透過 UDP/3478 之 STUN/TURN 候選的交涉</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN，MSTURN/TCP/443</p></td>
<td><p>任何</p></td>
<td><p>Edge Server A / V Edge service 公用 IP 位址</p></td>
<td><p>透過 UDP/443 之 STUN/TURN 候選的交涉</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN，MSTURN/TCP/443</p></td>
<td><p>Edge Server A / V Edge service 公用 IP 位址</p></td>
<td><p>任何</p></td>
<td><p>透過 UDP/443 之 STUN/TURN 候選的交涉</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a>調整式合併 Edge，硬體負載平衡的防火牆摘要： 內部介面節點 1 與節點 2

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
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>任何 （可定義為前端伺服器位址] 或 [前端集區虛擬 IP 位址執行 「 XMPP 閘道服務）</p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>從前端伺服器或前端集區上執行的 XMPP 閘道服務的輸出 XMPP 流量</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>任何 （可定義為前端伺服器 server IP 或保有中央管理存放區的集區）</p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>從中央管理存放區的 Edge server 的變更的複寫</p></td>
</tr>
<tr class="odd">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>任何 （可定義為 Director IP、 前端伺服器 IP 或集區虛擬 IP）</p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>從內部部署至 Internal Edge Server 介面的 web 會議流量</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>任何 （可定義為 Director IP、 前端伺服器 IP 或集區虛擬 IP）</p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>慣用的路徑 a / V 媒體傳輸內部與外部使用者，Survivable Branch Appliance 或 Survivable Branch 伺服器之間</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>任何 （可定義為 Director IP、 前端伺服器 IP 或集區虛擬 IP）</p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>後援路徑 a / V 媒體傳輸內部與外部使用者，Survivable Branch Appliance 或 Survivable Branch 伺服器之間，如果無法建立 UDP 通訊、 TCP 用於檔案傳輸及桌面共用</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50001</p></td>
<td><p>任何</p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>使用 Lync Server 管理命令介面和 Centralized Logging Service 指令程式、 ClsController 命令列 (ClsController.exe) 或代理程式 (ClsAgent.exe) 命令和記錄集合的集中式記錄服務控制站</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50002</p></td>
<td><p>任何</p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>使用 Lync Server 管理命令介面和 Centralized Logging Service 指令程式、 ClsController 命令列 (ClsController.exe) 或代理程式 (ClsAgent.exe) 命令和記錄集合的集中式記錄服務控制站</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50003</p></td>
<td><p>任何</p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>使用 Lync Server 管理命令介面和 Centralized Logging Service 指令程式、 ClsController 命令列 (ClsController.exe) 或代理程式 (ClsAgent.exe) 命令和記錄集合的集中式記錄服務控制站</p></td>
</tr>
</tbody>
</table>


硬體負載平衡器有時提供可用性和負載平衡的 Lync Server 部署的特定需求。 下圖與資料表中定義的需求。 第三方廠商可能使用不同的術語，如以下所定義的需求。 您必須將 Lync Server 的需求對應至您的硬體負載平衡器廠商所提供的組態選項的功能。

當設定硬體負載平衡器，請考慮下列需求：

  - 來源網路位址轉譯 (SNAT) 可以設定上的 Access Edge service 和 Web Conferencing Edge service 的硬體負載平衡器 (HLB)

  - SNAT 無法進行設定的 a / V Edge service – A / V Edge service 必須回應與實際的伺服器位址，不 HLB 虛擬 IP (VIP)，如簡單周遊 UDP 透過 NAT (STUN) / 周遊使用轉送 NAT （開啟） / 同盟開啟 (FTURN) 才能正常運作
    
      - 如果用戶端會將要求傳送至 HLB，回應必須來自回 HLB VIP
    
      - 如果用戶端會將要求傳送至 Edge，回應必須來自回 Edge IP

  - HLB Vip 和每個伺服器介面上使用公用 IP 位址和您的公用 IP 位址需求為 N + 1，其中有是實際的伺服器的每個介面，另一個用於每個 HLB VIP 公用 IP 位址。 其中您有 2 Edge server 集區，這會導致 9 公用 IP 位址，其中 3 及所用的 HLB Vip，一個用於每個 Edge server 介面 （6 的伺服器總計）

  - Access edge service 和 Web Conferencing Edge service] （和 HLB 上使用 NAT） 用戶端的連絡人的 VIP，來源 IP 位址從用戶端它自己的 IP 位址的 VIP 變更。 伺服器介面 vip，來源地址從伺服器介面 IP 位址的 VIP 變更位址的回覆地址，並將封包傳送到用戶端

  - A / V Edge service 為 VIP 不得變更來源 IP 位址，以及實際的伺服器位址直接傳回給用戶端 – 您不能用於 AV 流量 HLB 上設定 NAT
    
      - 如果用戶端會將要求傳送至 HLB VIP，回應必須來自回 HLB VIP
    
      - 如果用戶端會將要求傳送至 Edge IP，回應必須來自回 Edge IP

  - AV，如外部防火牆會保留所有的封包的實際的伺服器公用 IP 位址

  - 一次建立的用戶端 a / V Edge 服務通訊是實際的伺服器，不 HLB

  - 必須路由傳送至內部伺服器和用戶端的內部邊緣，並在該主機伺服器或用戶端的所有內部網路設定持續路由

  - HLB Access Edge service VIP 做為預設閘道，以每個 Edge server 介面

<div>


> [!NOTE]
> 如需規劃 NAT 和功能的進一步資訊，請參閱<A href="lync-server-2013-hardware-load-balancer-requirements.md">硬體負載平衡器需求，針對 Lync Server 2013</A>。



</div>

![Edge Server 的連接埠和通訊協定詳細資料](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Edge Server 的連接埠和通訊協定詳細資料")

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a>外部連接埠設定所需的調整式合併 Edge，硬體負載平衡： 外部介面虛擬 Ip

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
<td><p>Access/SIP (TLS) / TCP/443</p></td>
<td><p>任何</p></td>
<td><p>Access Edge 服務公用 VIP 位址</p></td>
<td><p>外部使用者存取從用戶端到伺服器的 SIP 流量</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP (MTLS) / TCP/5061</p></td>
<td><p>任何</p></td>
<td><p>Access Edge 服務公用 VIP 位址</p></td>
<td><p>SIP 使用 SIP 信號、 同盟與公用 IM 連線</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP (MTLS) / TCP/5061</p></td>
<td><p>Access Edge 服務公用 VIP 位址</p></td>
<td><p>同盟協力廠商</p></td>
<td><p>SIP 使用 SIP 信號、 同盟與公用 IM 連線</p></td>
</tr>
<tr class="even">
<td><p>Web 會議 /PSOM (TLS) / TCP/443</p></td>
<td><p>任何</p></td>
<td><p>Edge Server Web Conferencing Edge service 公用 VIP 位址</p></td>
<td><p>Web 會議媒體</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN，MSTURN/UDP/3478</p></td>
<td><p>任何</p></td>
<td><p>Edge Server A / V Edge service 公用 VIP 位址</p></td>
<td><p>透過 UDP/3478 之 STUN/TURN 候選的交涉</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN，MSTURN/TCP/443</p></td>
<td><p>任何</p></td>
<td><p>Edge Server A / V Edge service 公用 VIP 位址</p></td>
<td><p>透過 UDP/443 之 STUN/TURN 候選的交涉</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a>調整式合併 Edge，硬體負載平衡的防火牆摘要： 內部介面虛擬 Ip

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
<td><p>任何 （可定義為 Director，Director 集區虛擬 IP 位址、 前端伺服器或前端集區虛擬 IP 位址）</p></td>
<td><p>Edge Server 內部 VIP 介面</p></td>
<td><p>輸出 SIP 流量 （來自 Director、 Director 集區虛擬 IP 位址、 前端伺服器或前端集區虛擬 IP 位址) 內部 Edge VIP</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP (MTLS) / TCP/5061</p></td>
<td><p>Edge Server 內部 VIP 介面</p></td>
<td><p>任何 （可定義為 Director，Director 集區虛擬 IP 位址、 前端伺服器或前端集區虛擬 IP 位址）</p></td>
<td><p>輸入從 Edge Server 內部介面的 SIP 流量 （至 Director、 Director 集區虛擬 IP 位址、 前端伺服器或前端集區虛擬 IP 位址)</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>任何 （可定義為前端伺服器 IP 位址，或前端集區的 IP 位址或任何 Survivable Branch Appliance 或 Survivable Branch 伺服器使用此 Edge Server）</p></td>
<td><p>Edge Server 內部 VIP 介面</p></td>
<td><p>驗證 A / V 使用者 (A / V 驗證服務) 從前端伺服器或前端集區 IP 位址或任何 Survivable Branch Appliance 或 Survivable Branch 伺服器使用此 Edge Server</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>任何</p></td>
<td><p>Edge Server 內部 VIP 介面</p></td>
<td><p>內部與外部使用者之間 A/V 媒體傳輸的慣用路徑</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>任何</p></td>
<td><p>Edge Server 內部 VIP 介面</p></td>
<td><p>內部及外部使用者之間 A/V 媒體傳輸的後援路徑，如果無法建立 UDP 通訊，就會使用 TCP 進行檔案傳輸及桌面共用</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Edge Server 內部 VIP 介面</p></td>
<td><p>任何</p></td>
<td><p>內部及外部使用者之間 A/V 媒體傳輸的後援路徑，如果無法建立 UDP 通訊，就會使用 TCP 進行檔案傳輸及桌面共用</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

