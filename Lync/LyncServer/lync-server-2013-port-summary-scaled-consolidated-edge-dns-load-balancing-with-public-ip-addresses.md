---
title: Lync Server 2013：連接埠摘要 - 調整式合併 Edge (利用公用 IP 位址進行 DNS 負載平衡)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: f7cbd0f1-841d-4116-8d17-e9d991daa4a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205394(v=OCS.15)
ms:contentKeyID: 48185865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2095df7ebd68265d135a8b174ce2d1d3ae76ca5d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a>Lync Server 2013 中的連接埠摘要 - 調整式合併 Edge (利用公用 IP 位址進行 DNS 負載平衡)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-04-03_

此案例架構中所述的 Lync Server 2013、Edge 伺服器功能與 Lync Server 2010 中所實施的內容非常類似。 最顯著的新增是針對可擴展訊息和目前狀態通訊協定（XMPP）的**TCP 專案上**的埠5269。 Lync Server 2013 可選擇在 Edge 伺服器或 Edge 池以及前端伺服器或頂層端池中的 XMPP 閘道伺服器上部署 XMPP proxy。

除了 IPv4，Edge 伺服器現在還支援 IPv6。 為清楚起見，在案例中只使用 IPv4。

**企業周邊網路可調整整合的邊緣，使用公用 IP 位址進行 DNS 負載平衡**

![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")

<div>

## <a name="port-and-protocol-details"></a>埠與通訊協定詳細資料

建議您只開啟支援您提供外部存取的功能所需的埠。

若要讓遠端存取作用於任何 edge 服務，必須具備 SIP 流量來流動雙向，如入站/出站邊緣流量圖所示。 換句話說，在「立即訊息（IM）」、「目前狀態」、「web 會議」、音訊/視頻（A/V）及同盟中，都會涉及來自存取邊緣服務的 SIP 訊息。

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-external-interface--node-1-and-node-2-example"></a>針對調整後邊緣的防火牆摘要、使用公用 IP 位址的 DNS 負載平衡：外部介面–節點1和節點2（範例）

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>角色/通訊協定/TCP 或 UDP/埠</th>
<th>來源 IP 位址</th>
<th>目的地 IP 位址</th>
<th>筆記</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>每</p></td>
<td><p>XMPP Proxy service （與存取邊緣服務共用 IP 位址）</p></td>
<td><p>XMPP Proxy service 接受來自已定義 XMPP 聯合體中 XMPP 連絡人的流量</p></td>
</tr>
<tr class="even">
<td><p>Access/HTTP/TCP/80</p></td>
<td><p>Edge 伺服器存取邊緣服務公用 IP 位址</p></td>
<td><p>每</p></td>
<td><p>憑證吊銷/CRL 檢查及檢索</p></td>
</tr>
<tr class="odd">
<td><p>Access/DNS/TCP/53</p></td>
<td><p>Edge 伺服器存取邊緣服務公用 IP 位址</p></td>
<td><p>每</p></td>
<td><p>TCP 的 DNS 查詢</p></td>
</tr>
<tr class="even">
<td><p>Access/DNS/UDP/53</p></td>
<td><p>Edge 伺服器存取邊緣服務公用 IP 位址</p></td>
<td><p>每</p></td>
<td><p>經由 UDP 的 DNS 查詢</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP （TLS）/TCP/443</p></td>
<td><p>每</p></td>
<td><p>Edge 伺服器存取邊緣服務公用 IP 位址</p></td>
<td><p>外部使用者存取的用戶端到伺服器 SIP 流量</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP （MTLS）/TCP/5061</p></td>
<td><p>每</p></td>
<td><p>Edge 伺服器存取邊緣服務公用 IP 位址</p></td>
<td><p>使用 SIP 進行聯盟及公用 IM 連線</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP （MTLS）/TCP/5061</p></td>
<td><p>Edge 伺服器存取邊緣服務公用 IP 位址</p></td>
<td><p>每</p></td>
<td><p>使用 SIP 進行聯盟及公用 IM 連線</p></td>
</tr>
<tr class="even">
<td><p>網路會議/PSOM （TLS） TCP/443</p></td>
<td><p>每</p></td>
<td><p>Edge 伺服器網路會議 Edge 服務公用 IP 位址</p></td>
<td><p>網路會議媒體</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>Edge 伺服器 A/V 邊緣服務公用 IP 位址</p></td>
<td><p>每</p></td>
<td><p>與執行 Office 通訊伺服器2007、Office 通訊伺服器 2007 R2、Lync Server 2010 和 Lync Server 2013 的合作夥伴進行聯盟時需要。</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/UDP/50000-59999</p></td>
<td><p>Edge 伺服器 A/V 邊緣服務公用 IP 位址</p></td>
<td><p>每</p></td>
<td><p>只有與執行 Office 通訊伺服器2007之夥伴的同盟才需要。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>每</p></td>
<td><p>Edge 伺服器 A/V 邊緣服務公用 IP 位址</p></td>
<td><p>僅限執行 Office 通訊伺服器2007之合作夥伴的同盟所需</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/UDP/50000-59999</p></td>
<td><p>每</p></td>
<td><p>Edge 伺服器 A/V 邊緣服務公用 IP 位址</p></td>
<td><p>僅限執行 Office 通訊伺服器2007之合作夥伴的同盟所需</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>Edge 伺服器 A/V 邊緣服務公用 IP 位址</p></td>
<td><p>每</p></td>
<td><p>3478 [輸出] 是用來判斷 Lync Server 所與之通訊的邊緣伺服器版本，也是從邊緣伺服器到邊緣伺服器的媒體流量。 使用 Lync Server 2010、Windows Live Messenger 和 Office 通訊伺服器 2007 R2 進行聯盟所需，以及在公司中部署了多個 Edge 池的情況。</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>每</p></td>
<td><p>Edge 伺服器 A/V 邊緣服務公用 IP 位址</p></td>
<td><p>STUN/開啟候選人對 UDP/3478 的協商</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/TCP/443</p></td>
<td><p>每</p></td>
<td><p>Edge 伺服器 A/V 邊緣服務公用 IP 位址</p></td>
<td><p>STUN/開啟候選人對 TCP/443 的協商</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/TCP/443</p></td>
<td><p>Edge 伺服器 A/V 邊緣服務</p></td>
<td><p>每</p></td>
<td><p>STUN/開啟候選人對 TCP/443 的協商</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-internal-interface--node-1-and-node-2-example"></a>針對調整後邊緣的防火牆摘要、使用公用 IP 位址的 DNS 負載平衡：內部介面–節點1和節點2（範例）

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>通訊協定/TCP 或 UDP/埠</th>
<th>來源 IP 位址</th>
<th>目的地 IP 位址</th>
<th>批註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>[任何] （可以定義為前端伺服器位址，或執行 XMPP 閘道服務的前端池 IP 位址）</p></td>
<td><p>Edge 伺服器內部介面</p></td>
<td><p>在前端伺服器或前端池上執行的 XMPP 閘道服務的輸出 XMPP 流量</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>[任何] （可以定義為 Director、控制器池 IP 位址、前端伺服器或前端池 IP 位址）</p></td>
<td><p>Edge 伺服器內部介面</p></td>
<td><p>輸出 SIP 流量（從控制器、控制器池 IP 位址、前端伺服器或前端池 IP 位址）到邊緣伺服器內部介面</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>Edge 伺服器內部介面</p></td>
<td><p>[任何] （可以定義為 Director、控制器池 IP 位址、前端伺服器或前端池 IP 位址）</p></td>
<td><p>來自 Edge 伺服器內部介面的入站 SIP 流量（到控制器、控制器池 IP 位址、前端伺服器或前端池 IP 位址）</p></td>
</tr>
<tr class="even">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>Any （可定義為前端伺服器 IP 位址，或前端池中的每個前端伺服器 IP 位址）</p></td>
<td><p>Edge 伺服器內部介面</p></td>
<td><p>從前臺伺服器或每個前端伺服器的網路會議流量（如果在池中）到 Edge 伺服器內部介面</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>[任何] （可以使用此 Edge 伺服器定義為前端伺服器 IP 位址或前端池 IP 位址或任何 Survivable 分支裝置或 Survivable 分支伺服器）</p></td>
<td><p>Edge 伺服器內部介面</p></td>
<td><p>使用此 Edge 伺服器從前端伺服器或前端池 IP 位址或任何 Survivable 分支裝置或 Survivable 分支伺服器驗證 A/V 使用者（A/V 驗證服務）</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>每</p></td>
<td><p>Edge 伺服器內部介面</p></td>
<td><p>內部與外部使用者之間的 A/V 媒體傳輸的首選路徑、Survivable 分支裝置或 Survivable 分支伺服器</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>每</p></td>
<td><p>Edge 伺服器內部介面</p></td>
<td><p>內部與外部使用者之間的 A/V 媒體傳輸的回退路徑、Survivable 分支裝置或 Survivable 分支伺服器如果無法建立 UDP 通訊，則會使用 TCP 進行檔案傳輸與桌面共用</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>[任何] （可定義為 [前端伺服器 IP 位址] 或 [擁有中央管理儲存區的池）]</p></td>
<td><p>Edge 伺服器內部介面</p></td>
<td><p>從中央管理儲存體將變更複製到 Edge 伺服器</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>每</p></td>
<td><p>Edge 伺服器內部介面</p></td>
<td><p>使用 Lync Server 管理命令介面與集中式記錄服務 Cmdlet、ClsController 命令列（ClsController）或 agent （ClsAgent .exe）命令和記錄集合的集中式記錄服務控制器</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>每</p></td>
<td><p>Edge 伺服器內部介面</p></td>
<td><p>使用 Lync Server 管理命令介面與集中式記錄服務 Cmdlet、ClsController 命令列（ClsController）或 agent （ClsAgent .exe）命令和記錄集合的集中式記錄服務控制器</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>每</p></td>
<td><p>Edge 伺服器內部介面</p></td>
<td><p>使用 Lync Server 管理命令介面與集中式記錄服務 Cmdlet、ClsController 命令列（ClsController）或 agent （ClsAgent .exe）命令和記錄集合的集中式記錄服務控制器</p></td>
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
<th>角色/通訊協定/TCP 或 UDP/埠</th>
<th>來源 IP 位址</th>
<th>目的地 IP 位址</th>
<th>筆記</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Access/SIP （MTLS）/TCP/5061</p></td>
<td><p>存取邊緣服務公用 IP 位址</p></td>
<td><p>每</p></td>
<td><p>使用 SIP 進行聯盟及公用 IM 連線</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a>防火牆摘要–公用立即訊息連線能力


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>角色/通訊協定/TCP 或 UDP/埠</th>
<th>來源 IP 位址</th>
<th>目的地 IP 位址</th>
<th>筆記</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Access/SIP （MTLS）/TCP/5061</p></td>
<td><p>公用 IM 連線性合作夥伴</p></td>
<td><p>Edge 伺服器存取邊緣服務</p></td>
<td><p>使用 SIP 進行聯盟及公用 IM 連線</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP （MTLS）/TCP/5061</p></td>
<td><p>Edge 伺服器存取邊緣服務</p></td>
<td><p>公用 IM 連線性合作夥伴</p></td>
<td><p>使用 SIP 進行聯盟及公用 IM 連線</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP （TLS）/TCP/443</p></td>
<td><p>台</p></td>
<td><p>Edge 伺服器存取邊緣服務</p></td>
<td><p>外部使用者存取的用戶端到伺服器 SIP 流量</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>Edge 伺服器 A/V 邊緣服務</p></td>
<td><p>即時 Messenger 用戶端</p></td>
<td><p>在已設定公用 IM 連線的情況中，使用 Windows Live Messenger 進行 A/V 會話。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>Edge 伺服器 A/V 邊緣服務</p></td>
<td><p>即時 Messenger 用戶端</p></td>
<td><p>與 Windows Live Messenger 的公用 IM 連線所需</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>即時 Messenger 用戶端</p></td>
<td><p>Edge 伺服器 A/V 邊緣服務</p></td>
<td><p>與 Windows Live Messenger 的公用 IM 連線所需</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a>可擴展訊息和目前狀態通訊協定的防火牆摘要


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>通訊協定/TCP 或 UDP/埠</th>
<th>來源（IP 位址）</th>
<th>目的地（IP 位址）</th>
<th>批註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>每</p></td>
<td><p>Edge 伺服器存取邊緣服務介面 IP 位址</p></td>
<td><p>XMPP 的標準伺服器與伺服器通訊埠。 允許從聯盟 XMPP 合作夥伴與 Edge 伺服器 XMPP proxy 進行通訊</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Edge 伺服器存取邊緣服務介面 IP 位址</p></td>
<td><p>每</p></td>
<td><p>XMPP 的標準伺服器與伺服器通訊埠。 允許從 Edge 伺服器 XMPP proxy 到聯盟 XMPP 合作夥伴的通訊</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>每</p></td>
<td><p>每個內部邊緣伺服器介面 IP</p></td>
<td><p>從前端伺服器或前端池的 XMPP 閘道到 Edge 伺服器內部 IP 位址或每個邊緣池成員的內部 IP 位址的內部 XMPP 流量</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

