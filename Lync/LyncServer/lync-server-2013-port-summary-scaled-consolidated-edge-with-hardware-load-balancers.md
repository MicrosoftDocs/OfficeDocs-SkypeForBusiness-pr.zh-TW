---
title: 連接埠摘要 - 調整式合併 Edge (利用硬體負載平衡器)
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
ms.openlocfilehash: 6260a4ad7f2717e0b4eb2446fc5b17671c3e45a5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Lync Server 2013 中的連接埠摘要 - 調整式合併 Edge (利用硬體負載平衡器)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-04-27_

此案例架構中所述的 Lync Server 2013、Edge 伺服器功能與 Lync Server 2010 中所實施的內容非常類似。 最顯著的新增是針對可擴展訊息和目前狀態通訊協定（XMPP）的**TCP 專案上**的埠5269。 Lync Server 2013 可選擇在 Edge 伺服器或 Edge 池以及前端伺服器或頂層端池中的 XMPP 閘道伺服器上部署 XMPP proxy。

除了 IPv4，Edge 伺服器現在還支援 IPv6。 為清楚起見，在案例中只使用 IPv4。

**使用硬體負載平衡來調整合並的邊緣**

![Edge Server 周邊網路連接埠與通訊協定](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge Server 周邊網路連接埠與通訊協定")

<div>

## <a name="port-and-protocol-details"></a>埠與通訊協定詳細資料

建議您只開啟支援您提供外部存取的功能所需的埠。

若要讓遠端存取作用於任何 edge 服務，必須具備 SIP 流量來流動雙向，如入站/出站邊緣流量圖所示。 換句話說，在「立即訊息（IM）」、「目前狀態」、「web 會議」、音訊/視頻（A/V）及同盟中，都會涉及來自存取邊緣服務的 SIP 訊息。

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a>已調整合並邊緣的防火牆摘要、硬體負載平衡：外部介面–節點1和節點2（範例）

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
<td><p>Access/HTTP/TCP/80</p></td>
<td><p>Edge 伺服器存取邊緣服務公用 IP 位址</p></td>
<td><p>每</p></td>
<td><p>憑證吊銷/CRL 檢查及檢索</p></td>
</tr>
<tr class="even">
<td><p>Access/DNS/TCP/53</p></td>
<td><p>Edge 伺服器存取邊緣服務公用 IP 位址</p></td>
<td><p>每</p></td>
<td><p>TCP 的 DNS 查詢</p></td>
</tr>
<tr class="odd">
<td><p>Access/DNS/UDP/53</p></td>
<td><p>Edge 伺服器存取邊緣服務公用 IP 位址</p></td>
<td><p>每</p></td>
<td><p>經由 UDP 的 DNS 查詢</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>Edge 伺服器 A/V 邊緣的服務 IP 位址</p></td>
<td><p>每</p></td>
<td><p>與執行 Office 通訊伺服器2007、Office 通訊伺服器 2007 R2、Lync Server 2010 和 Lync Server 2013 的合作夥伴進行聯盟時需要。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59999</p></td>
<td><p>Edge 伺服器 A/V 邊緣服務公用 IP 位址</p></td>
<td><p>每</p></td>
<td><p>只有與執行 Office 通訊伺服器2007之夥伴的同盟才需要。</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>每</p></td>
<td><p>Edge 伺服器 A/V 邊緣服務公用 IP 位址</p></td>
<td><p>僅限執行 Office 通訊伺服器2007之合作夥伴的同盟所需</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59999</p></td>
<td><p>每</p></td>
<td><p>Edge 伺服器 A/V 邊緣服務公用 IP 位址</p></td>
<td><p>僅限執行 Office 通訊伺服器2007之合作夥伴的同盟所需</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>Edge 伺服器 A/V 邊緣服務公用 IP 位址</p></td>
<td><p>每</p></td>
<td><p>3478 [輸出] 是用來判斷 Lync Server 所與之通訊的邊緣伺服器版本，也是從邊緣伺服器到邊緣伺服器的媒體流量。 使用 Lync Server 2010、Windows Live Messenger 和 Office 通訊伺服器 2007 R2 進行聯盟所需，以及在公司中部署了多個 Edge 池的情況。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>每</p></td>
<td><p>Edge 伺服器 A/V 邊緣服務公用 IP 位址</p></td>
<td><p>STUN/開啟候選人對 UDP/3478 的協商</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/TCP/443</p></td>
<td><p>每</p></td>
<td><p>Edge 伺服器 A/V 邊緣服務公用 IP 位址</p></td>
<td><p>STUN/開啟候選人對 TCP/443 的協商</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/TCP/443</p></td>
<td><p>Edge 伺服器 A/V 邊緣服務公用 IP 位址</p></td>
<td><p>每</p></td>
<td><p>STUN/開啟候選人對 TCP/443 的協商</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a>用於調整合並邊緣的防火牆摘要、硬體負載平衡：內部介面節點1和節點2

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
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>[任何] （可以定義為前端伺服器位址，或執行 XMPP 閘道服務的前端池虛擬 IP 位址）</p></td>
<td><p>Edge 伺服器內部介面</p></td>
<td><p>在前端伺服器或前端池上執行的 XMPP 閘道服務的輸出 XMPP 流量</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>[任何] （可定義為擁有中央管理儲存區的前端伺服器伺服器 IP 或池）</p></td>
<td><p>Edge 伺服器內部介面</p></td>
<td><p>從中央管理儲存體將變更複製到 Edge 伺服器</p></td>
</tr>
<tr class="odd">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>[任何] （可以定義為 [控制器 IP]、[前端伺服器 IP] 或 [池虛擬 IP]）</p></td>
<td><p>Edge 伺服器內部介面</p></td>
<td><p>從內部部署到內部邊緣伺服器介面的網路會議流量</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>[任何] （可以定義為 [控制器 IP]、[前端伺服器 IP] 或 [池虛擬 IP]）</p></td>
<td><p>Edge 伺服器內部介面</p></td>
<td><p>內部與外部使用者之間的 A/V 媒體傳輸的首選路徑、Survivable 分支裝置或 Survivable 分支伺服器</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>[任何] （可以定義為 [控制器 IP]、[前端伺服器 IP] 或 [池虛擬 IP]）</p></td>
<td><p>Edge 伺服器內部介面</p></td>
<td><p>內部與外部使用者之間的 A/V 媒體傳輸的回退路徑、Survivable 分支裝置或 Survivable 分支伺服器如果無法建立 UDP 通訊，則會使用 TCP 進行檔案傳輸與桌面共用</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50001</p></td>
<td><p>每</p></td>
<td><p>Edge 伺服器內部介面</p></td>
<td><p>使用 Lync Server 管理命令介面與集中式記錄服務 Cmdlet、ClsController 命令列（ClsController）或 agent （ClsAgent .exe）命令和記錄集合的集中式記錄服務控制器</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50002</p></td>
<td><p>每</p></td>
<td><p>Edge 伺服器內部介面</p></td>
<td><p>使用 Lync Server 管理命令介面與集中式記錄服務 Cmdlet、ClsController 命令列（ClsController）或 agent （ClsAgent .exe）命令和記錄集合的集中式記錄服務控制器</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50003</p></td>
<td><p>每</p></td>
<td><p>Edge 伺服器內部介面</p></td>
<td><p>使用 Lync Server 管理命令介面與集中式記錄服務 Cmdlet、ClsController 命令列（ClsController）或 agent （ClsAgent .exe）命令和記錄集合的集中式記錄服務控制器</p></td>
</tr>
</tbody>
</table>


硬體負載平衡器在部署時有特定的需求，以提供 Lync Server 的可用性與負載平衡。 這些需求是在下圖和資料表中定義。 協力廠商廠商對於此處定義的需求，可能會使用不同的術語。 您必須將 Lync Server 的需求對應到您的硬體負載平衡器提供者所提供的功能和設定選項。

配置硬體負載平衡器時，請考慮下列需求：

  - 您可以在硬體負載平衡器（HLB）上設定來源網路位址轉譯（SNAT），以存取邊緣服務和網路會議 Edge 服務

  - SNAT 不能在 A/V 邊緣服務上設定-A/V Edge 服務必須回應實際的伺服器位址，而不是 HLB 的虛擬 IP （VIP），以便透過 NAT （STUN）/traversal 使用中繼 NAT （關閉）/federation 轉彎（FTURN）來正常運作
    
      - 如果用戶端傳送要求給 HLB，回應必須從 HLB VIP 傳回
    
      - 如果用戶端傳送要求給邊緣，回應必須從邊緣 IP 傳回

  - 公用 IP 位址是在每個伺服器介面和 HLB 的 Vip 上使用，而您的公用 IP 位址需求是 N + 1，其中包含每個真實伺服器介面的公用 IP 位址，以及每個 HLB VIP 的一個公用 IP 位址。 如果您在池中有2台邊緣伺服器，這會產生9個公用 IP 位址，其中3個是用於 HLB Vip，另一個用於每個 Edge 伺服器介面（在伺服器上總共6個）

  - 針對 [存取邊緣服務] 和 [Web 會議 Edge 服務] （以及在 HLB 上使用 NAT），用戶端會與 VIP 進行聯絡，而 VIP 會將來源 IP 位址從用戶端變更為自己的 IP 位址。 伺服器介面會將寄件者位址定址至 VIP，而 VIP 會從伺服器介面 IP 位址變更來源位址，並將資料包傳送給用戶端。

  - 在 A/V 邊緣服務中，VIP 不能變更來源 IP 位址，而真正的伺服器位址會直接傳回用戶端–您無法在 HLB 上設定 NAT 以進行 AV 流量
    
      - 如果用戶端傳送要求至 HLB VIP，回應必須從 HLB VIP 傳回
    
      - 如果用戶端傳送要求至 Edge IP，回應必須從邊緣 IP 傳回

  - 針對 AV，外部防火牆會保留所有資料包的真實伺服器公用 IP 位址

  - 一旦建立，用戶端到 A/V 邊緣服務通訊就是真實的伺服器，而不是 HLB

  - 內部邊緣至內部伺服器和用戶端必須路由，且為主機伺服器或用戶端的所有內部網路設定持久路由

  - HLB 存取邊緣服務 VIP 將充當每個 Edge 伺服器介面的預設閘道

<div>


> [!NOTE]
> 如需有關 NAT 規劃與功能的進一步資訊，請參閱<A href="lync-server-2013-hardware-load-balancer-requirements.md">Lync Server 2013 的硬體負載平衡器需求</A>。



</div>

![Edge Server 連接埠與通訊協定詳細資訊](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Edge Server 連接埠與通訊協定詳細資訊")

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a>已調整的合併邊緣所需的外部埠設定、硬體負載平衡：外部介面虛擬 Ip

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
<td><p>XMPP/TCP/5269</p></td>
<td><p>XMPP Proxy service （與存取邊緣服務共用 IP 位址）</p></td>
<td><p>每</p></td>
<td><p>XMPP Proxy service 會傳送流量給已定義 XMPP 聯合體中的 XMPP 連絡人</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP （TLS）/TCP/443</p></td>
<td><p>每</p></td>
<td><p>Access Edge 服務公用 VIP 位址</p></td>
<td><p>外部使用者存取的用戶端到伺服器 SIP 流量</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP （MTLS）/TCP/5061</p></td>
<td><p>每</p></td>
<td><p>Access Edge 服務公用 VIP 位址</p></td>
<td><p>使用 SIP 的 SIP 信號、同盟與公用 IM 連線</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP （MTLS）/TCP/5061</p></td>
<td><p>Access Edge 服務公用 VIP 位址</p></td>
<td><p>聯盟合作夥伴</p></td>
<td><p>使用 SIP 的 SIP 信號、同盟與公用 IM 連線</p></td>
</tr>
<tr class="even">
<td><p>網路會議/PSOM （TLS）/TCP/443</p></td>
<td><p>每</p></td>
<td><p>Edge 伺服器網路會議 Edge 服務公用 VIP 位址</p></td>
<td><p>網路會議媒體</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>每</p></td>
<td><p>Edge 伺服器 A/V 邊緣服務公用 VIP 位址</p></td>
<td><p>STUN/開啟候選人對 UDP/3478 的協商</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/TCP/443</p></td>
<td><p>每</p></td>
<td><p>Edge 伺服器 A/V 邊緣服務公用 VIP 位址</p></td>
<td><p>STUN/開啟候選人對 TCP/443 的協商</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a>用於調整合並邊緣的防火牆摘要、硬體負載平衡：內部介面虛擬 Ip

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
<td><p>[任何] （可定義為 [控制器]、[控制器池] 虛擬 IP 位址、[前端伺服器] 或 [前端池虛擬 IP 位址]）</p></td>
<td><p>Edge 伺服器內部 VIP 介面</p></td>
<td><p>輸出 SIP 流量（從控制器、控制器池虛擬 IP 位址、前端伺服器或前端池虛擬 IP 位址）到內部邊緣 VIP</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP （MTLS）/TCP/5061</p></td>
<td><p>Edge 伺服器內部 VIP 介面</p></td>
<td><p>[任何] （可定義為 [控制器]、[控制器池] 虛擬 IP 位址、[前端伺服器] 或 [前端池虛擬 IP 位址]）</p></td>
<td><p>來自 Edge 伺服器內部介面的入站 SIP 流量（針對控制器、控制器池虛擬 IP 位址、前端伺服器或前端池虛擬 IP 位址）</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>[任何] （可以使用此 Edge 伺服器定義為前端伺服器 IP 位址或前端池 IP 位址或任何 Survivable 分支裝置或 Survivable 分支伺服器）</p></td>
<td><p>Edge 伺服器內部 VIP 介面</p></td>
<td><p>使用此 Edge 伺服器從前端伺服器或前端池 IP 位址或任何 Survivable 分支裝置或 Survivable 分支伺服器驗證 A/V 使用者（A/V 驗證服務）</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>每</p></td>
<td><p>Edge 伺服器內部 VIP 介面</p></td>
<td><p>內部與外部使用者之間的 A/V 媒體傳輸的首選路徑</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>每</p></td>
<td><p>Edge 伺服器內部 VIP 介面</p></td>
<td><p>內部與外部使用者之間的 A/V 媒體傳輸的回退路徑如果無法建立 UDP 通訊，則會使用 TCP 進行檔案傳輸與桌面共用</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Edge 伺服器內部 VIP 介面</p></td>
<td><p>每</p></td>
<td><p>內部與外部使用者之間的 A/V 媒體傳輸的回退路徑如果無法建立 UDP 通訊，則會使用 TCP 進行檔案傳輸與桌面共用</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

