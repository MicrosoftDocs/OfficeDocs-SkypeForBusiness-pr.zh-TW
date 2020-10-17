---
title: 埠摘要-單一合併 edge （使用 NAT 透過私人 IP 位址）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: 3c1a389f-5f42-4719-a05b-e0b84aa3eb9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425891(v=OCS.15)
ms:contentKeyID: 48183877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a5aaa4628a92174aca39579c5f2e6a8e4f31987
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534000"
---
# <a name="port-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a>Lync Server 2013 中的埠摘要-單一合併 edge （使用 NAT 透過私人 IP 位址）

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-04-03_

此案例架構中所述的 Lync Server 2013，Edge Server 功能非常類似于 Lync Server 2010 中所執行的功能。 最值得注意的是加入了可延伸訊息及目前狀態通訊協定 (XMPP) 的連接埠 **5269 over TCP** 項目。 Lync Server 2013 （選用）在 Edge Server 或 Edge 集區上部署 XMPP proxy，並在前端伺服器或前端集區上部署 XMPP 閘道伺服器。

除了 IPv4 之外，Edge Server 現在還支援 IPv6。 但為了清楚說明起見，此案例僅會使用 IPv4。

**具有使用 NAT 的私人 IP 位址之單一合併 Edge Server 的網路周邊**

![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")

<div>

## <a name="port-and-protocol-details"></a>埠與通訊協定詳細資料

建議您僅針對要提供給外部存取的功能，開啟支援所需的連接埠。

若要讓遠端存取可用於任何 edge service，必須保證 SIP 流量雙向流動，如輸入/輸出 edge 流量圖所示。 另一種方法，「Access Edge service」的 SIP 訊息會包含在立即訊息 (IM) 、顯示狀態、web 會議、音訊/視頻 (A/V) 和同盟中。

### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-external-interface"></a>具有使用 NAT 的私人 IP 位址之單一合併 Edge 的防火牆摘要：外部介面

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
<th>注意事項</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>任何</p></td>
<td><p>XMPP Proxy 服務 (與 Access Edge service 共用 IP 位址) </p></td>
<td><p>XMPP Proxy 服務接受來自定義之 XMPP 同盟中 XMPP 連絡人的流量</p></td>
</tr>
<tr class="even">
<td><p>存取/HTTP/TCP/80</p></td>
<td><p>Edge Server Access Edge service</p></td>
<td><p>任何</p></td>
<td><p>憑證撤銷/CRL 檢查及擷取</p></td>
</tr>
<tr class="odd">
<td><p>存取/DNS/TCP/53</p></td>
<td><p>Edge Server Access Edge service</p></td>
<td><p>任何</p></td>
<td><p>透過 TCP 的 DNS 查詢</p></td>
</tr>
<tr class="even">
<td><p>存取/DNS/UDP/53</p></td>
<td><p>Edge Server Access Edge service</p></td>
<td><p>任何</p></td>
<td><p>透過 UDP 的 DNS 查詢</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP (TLS) /TCP/443</p></td>
<td><p>任何</p></td>
<td><p>Edge Server Access Edge service</p></td>
<td><p>外部使用者存取從用戶端到伺服器的 SIP 流量</p></td>
</tr>
<tr class="even">
<td><p>存取/SIP (MTLS) /TCP/5061</p></td>
<td><p>任何</p></td>
<td><p>Edge Server Access Edge service</p></td>
<td><p>適用於使用 SIP 的同盟與公用 IM 連線</p></td>
</tr>
<tr class="odd">
<td><p>存取/SIP (MTLS) /TCP/5061</p></td>
<td><p>Edge Server Access Edge service</p></td>
<td><p>任何</p></td>
<td><p>適用於使用 SIP 的同盟與公用 IM 連線</p></td>
</tr>
<tr class="even">
<td><p>Web 會議/PSOM (TLS) /TCP/443</p></td>
<td><p>任何</p></td>
<td><p>Edge Server Web 會議 Edge service</p></td>
<td><p>Web 會議媒體</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>Edge Server A/V Edge service</p></td>
<td><p>任何</p></td>
<td><p>與執行 Office 通訊伺服器2007、Office 通訊伺服器 2007 R2、Lync Server 2010 和 Lync Server 2013 的合作夥伴進行同盟所需。</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/UDP/50000-59999</p></td>
<td><p>Edge Server A/V Edge service</p></td>
<td><p>任何</p></td>
<td><p>僅適用于執行 Office 通訊伺服器2007之合作夥伴的同盟。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>任何</p></td>
<td><p>Edge Server A/V Edge service</p></td>
<td><p>僅適用于執行 Office 通訊伺服器2007之合作夥伴的同盟</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/UDP/50000-59999</p></td>
<td><p>任何</p></td>
<td><p>Edge Server A/V Edge service</p></td>
<td><p>僅適用于執行 Office 通訊伺服器2007之合作夥伴的同盟</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>Edge Server A/V Edge service</p></td>
<td><p>任何</p></td>
<td><p>3478輸出可用來判斷與 Lync Server 進行通訊的 Edge Server 版本，以及來自 Edge Server 至 Edge Server 的媒體流量。 與 Lync Server 2010、Windows Live Messenger 和 Office 通訊伺服器 2007 R2 的同盟是必要的，此外，如果在公司內部署了多個 Edge 集區，也是必要的。</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>任何</p></td>
<td><p>Edge Server A/V Edge service</p></td>
<td><p>透過 UDP/3478 之 STUN/TURN 候選的交涉</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/TCP/443</p></td>
<td><p>任何</p></td>
<td><p>Edge Server A/V Edge service</p></td>
<td><p>透過 UDP/443 之 STUN/TURN 候選的交涉</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/TCP/443</p></td>
<td><p>Edge Server A/V Edge service</p></td>
<td><p>任何</p></td>
<td><p>透過 UDP/443 之 STUN/TURN 候選的交涉</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-internal-interface"></a>具有使用 NAT 的私人 IP 位址之單一合併 Edge 的防火牆摘要：內部介面

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
<td><p>任何 (都可以定義為 Standard Edition server IP、Standard Edition server IP 位址，或執行 XMPP 閘道服務的集區 IP 位址) </p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>來自前端伺服器或前端集區上執行之 XMPP 閘道服務的輸出 XMPP 流量</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>任何 (都可以定義為 Director、Director 集區 IP 位址、前端伺服器或前端集區 IP 位址) </p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p> (從 Director、Director 集區 IP 位址、前端伺服器或前端集區 IP 位址) 到 Edge Server 內部介面的輸出 SIP 流量</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>任何 (都可以定義為 Director、Director 集區 IP 位址、前端伺服器或前端集區 IP 位址) </p></td>
<td><p>從 Edge Server 內部介面) 的輸入 SIP 流量 (到 Director、Director 集區 IP 位址、前端伺服器或前端集區 IP 位址</p></td>
</tr>
<tr class="even">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>任何 (都可以定義為前端伺服器的 IP 位址，或前端集區中的每個前端伺服器 IP 位址) </p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>如果在集區中，則為 Edge Server 內部介面，來自前端伺服器或每一部前端伺服器的 Web 會議流量</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>任何 (都可以定義為前端伺服器的 IP 位址，或前端集區的 IP 位址，或是使用此 Edge Server 的任何 Survivable Branch 裝置或 Survivable Branch 伺服器) </p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>A/V 使用者的驗證 (A/V 驗證服務) 來自前端伺服器或前端集區的 IP 位址，或是使用此 Edge Server 的任何 Survivable 分支裝置或 Survivable 分支伺服器</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>任何</p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>內部與外部使用者之間的 A/V 媒體傳輸的慣用路徑，Survivable Branch 裝置或 Survivable Branch 伺服器</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>任何</p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>內部與外部使用者之間 A/V 媒體傳輸的回退路徑。 Survivable 分支裝置或 Survivable Branch Server 如果無法建立 UDP 通訊，則會使用 TCP 進行檔案傳輸和桌面共用</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>任何 (都可以定義為前端伺服器的 IP 位址，或存放中央管理存放區的集區) </p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>從中央管理存放區到 Edge Server 的變更複製</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>任何</p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>集中式記錄服務控制器使用 Lync Server 管理命令介面和集中式記錄服務 Cmdlet，ClsController 命令列 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>任何</p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>集中式記錄服務控制器使用 Lync Server 管理命令介面和集中式記錄服務 Cmdlet，ClsController 命令列 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>任何</p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>集中式記錄服務控制器使用 Lync Server 管理命令介面和集中式記錄服務 Cmdlet，ClsController 命令列 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</p></td>
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
<th>注意事項</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>存取/SIP (MTLS) /TCP/5061</p></td>
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
<th>注意事項</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>存取/SIP (MTLS) /TCP/5061</p></td>
<td><p>公用 IM 連線協力廠商</p></td>
<td><p>Edge Server Access Edge service</p></td>
<td><p>適用於使用 SIP 的同盟與公用 IM 連線</p></td>
</tr>
<tr class="even">
<td><p>存取/SIP (MTLS) /TCP/5061</p></td>
<td><p>Edge Server Access Edge service</p></td>
<td><p>公用 IM 連線協力廠商</p></td>
<td><p>適用於使用 SIP 的同盟與公用 IM 連線</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP (TLS) /TCP/443</p></td>
<td><p>用戶端</p></td>
<td><p>Edge Server Access Edge service</p></td>
<td><p>外部使用者存取從用戶端到伺服器的 SIP 流量</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>Edge Server A/V Edge service</p></td>
<td><p>Live Messenger 用戶端</p></td>
<td><p>如果有設定 IM 連線，可與 Windows Live Messenger 用於 A/V 工作階段</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>Edge Server A/V Edge service</p></td>
<td><p>Live Messenger 用戶端</p></td>
<td><p>與 Windows Live Messenger 進行公用 IM 連線時必須使用</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>Live Messenger 用戶端</p></td>
<td><p>Edge Server A/V Edge service</p></td>
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
<td><p>Edge Server Access Edge service interface IP address</p></td>
<td><p>XMPP 的標準伺服器對伺服器通訊連接埠。 允許來自同盟 XMPP 合作夥伴的 Edge Server XMPP proxy 的通訊</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Edge Server Access Edge service interface IP address</p></td>
<td><p>任何</p></td>
<td><p>XMPP 的標準伺服器對伺服器通訊連接埠。 允許從 Edge Server XMPP proxy 到同盟 XMPP 合作夥伴的通訊</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>任何</p></td>
<td><p>每個內部 Edge Server 介面 IP</p></td>
<td><p>從前端伺服器或前端集區的 XMPP 閘道到 Edge Server 內部 IP 位址或每個 Edge 集區成員的內部 IP 位址的內部 XMPP 流量</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

