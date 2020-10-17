---
title: 埠摘要-調整式合併 edge （使用硬體負載平衡器）
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
ms.openlocfilehash: dc4a56edb79d2eff52bf0d234aedcee1b3cdced4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534110"
---
# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Lync Server 2013 中的埠摘要-調整式合併 edge （使用硬體負載平衡器）

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-04-27_

此案例架構中所述的 Lync Server 2013，Edge Server 功能非常類似于 Lync Server 2010 中所執行的功能。 最值得注意的是加入了可延伸訊息及目前狀態通訊協定 (XMPP) 的連接埠 **5269 over TCP** 項目。 Lync Server 2013 （選用）在 Edge Server 或 Edge 集區上部署 XMPP proxy，並在前端伺服器或前端集區上部署 XMPP 閘道伺服器。

除了 IPv4 之外，Edge Server 現在還支援 IPv6。 但為了清楚說明起見，此案例僅會使用 IPv4。

**使用硬體負載平衡調整式合併 Edge**

![Edge Server 周邊網路埠和通訊協定](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge Server 周邊網路埠和通訊協定")

<div>

## <a name="port-and-protocol-details"></a>埠與通訊協定詳細資料

建議您只開啟支援您提供外部存取之功能所需的埠。

若要讓遠端存取可用於任何 edge service，必須保證 SIP 流量雙向流動，如輸入/輸出 edge 流量圖所示。 換句話說，來回 Access Edge Service 的 SIP 訊息會涉及立即訊息 (IM)、顯示狀態、Web 會議、音訊/視訊 (A/V) 與同盟等功能。

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a>調整式合併 Edge （硬體負載平衡）的防火牆摘要：外部介面–節點1和節點 2 (範例) 

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
<td><p>存取/HTTP/TCP/80</p></td>
<td><p>Edge Server Access Edge service 公用 IP 位址</p></td>
<td><p>任何</p></td>
<td><p>憑證撤銷/CRL 檢查及擷取</p></td>
</tr>
<tr class="even">
<td><p>存取/DNS/TCP/53</p></td>
<td><p>Edge Server Access Edge service 公用 IP 位址</p></td>
<td><p>任何</p></td>
<td><p>透過 TCP 的 DNS 查詢</p></td>
</tr>
<tr class="odd">
<td><p>存取/DNS/UDP/53</p></td>
<td><p>Edge Server Access Edge service 公用 IP 位址</p></td>
<td><p>任何</p></td>
<td><p>透過 UDP 的 DNS 查詢</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>Edge Server A/V Edge service IP 位址</p></td>
<td><p>任何</p></td>
<td><p>與執行 Office 通訊伺服器2007、Office 通訊伺服器 2007 R2、Lync Server 2010 和 Lync Server 2013 的合作夥伴進行同盟所需。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59999</p></td>
<td><p>Edge Server A/V Edge service 公用 IP 位址</p></td>
<td><p>任何</p></td>
<td><p>僅適用于執行 Office 通訊伺服器2007之合作夥伴的同盟。</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>任何</p></td>
<td><p>Edge Server A/V Edge service 公用 IP 位址</p></td>
<td><p>僅適用于執行 Office 通訊伺服器2007之合作夥伴的同盟</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59999</p></td>
<td><p>任何</p></td>
<td><p>Edge Server A/V Edge service 公用 IP 位址</p></td>
<td><p>僅適用于執行 Office 通訊伺服器2007之合作夥伴的同盟</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>Edge Server A/V Edge service 公用 IP 位址</p></td>
<td><p>任何</p></td>
<td><p>3478輸出可用來判斷與 Lync Server 進行通訊的 Edge Server 版本，以及來自 Edge Server 至 Edge Server 的媒體流量。 與 Lync Server 2010、Windows Live Messenger 和 Office 通訊伺服器 2007 R2 的同盟是必要的，此外，如果在公司內部署了多個 Edge 集區，也是必要的。</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>任何</p></td>
<td><p>Edge Server A/V Edge service 公用 IP 位址</p></td>
<td><p>透過 UDP/3478 之 STUN/TURN 候選的交涉</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/TCP/443</p></td>
<td><p>任何</p></td>
<td><p>Edge Server A/V Edge service 公用 IP 位址</p></td>
<td><p>透過 UDP/443 之 STUN/TURN 候選的交涉</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/TCP/443</p></td>
<td><p>Edge Server A/V Edge service 公用 IP 位址</p></td>
<td><p>任何</p></td>
<td><p>透過 UDP/443 之 STUN/TURN 候選的交涉</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a>調整式合併 Edge （硬體負載平衡）的防火牆摘要：內部介面節點1和節點2

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
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>任何 (都可以定義為前端伺服器位址，或執行 XMPP 閘道服務的前端集區虛擬 IP 位址) </p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>來自前端伺服器或前端集區上執行之 XMPP 閘道服務的輸出 XMPP 流量</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>任何 (都可以定義為具有中央管理存放區的前端伺服器伺服器 IP 或集區) </p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>從中央管理存放區到 Edge Server 的變更複製</p></td>
</tr>
<tr class="odd">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>任何 (都可以定義為 Director IP、前端伺服器 IP 或集區虛擬 IP) </p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>從內部部署至內部 Edge Server 介面的 Web 會議流量</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>任何 (都可以定義為 Director IP、前端伺服器 IP 或集區虛擬 IP) </p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>內部與外部使用者之間的 A/V 媒體傳輸的慣用路徑，Survivable Branch 裝置或 Survivable Branch 伺服器</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>任何 (都可以定義為 Director IP、前端伺服器 IP 或集區虛擬 IP) </p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>內部與外部使用者之間 A/V 媒體傳輸的回退路徑。 Survivable 分支裝置或 Survivable Branch Server 如果無法建立 UDP 通訊，則會使用 TCP 進行檔案傳輸和桌面共用</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50001</p></td>
<td><p>任何</p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>集中式記錄服務控制器使用 Lync Server 管理命令介面和集中式記錄服務 Cmdlet，ClsController 命令列 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50002</p></td>
<td><p>任何</p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>集中式記錄服務控制器使用 Lync Server 管理命令介面和集中式記錄服務 Cmdlet，ClsController 命令列 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50003</p></td>
<td><p>任何</p></td>
<td><p>Edge Server 內部介面</p></td>
<td><p>集中式記錄服務控制器使用 Lync Server 管理命令介面和集中式記錄服務 Cmdlet，ClsController 命令列 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</p></td>
</tr>
</tbody>
</table>


硬體負載平衡器在部署時有特定的需求，可提供 Lync Server 的可用性和負載平衡。 這些需求是在下圖和表格中定義的。 協力廠商廠商可能會針對這裡定義的需求使用不同的術語。 您必須將 Lync Server 的需求對應至硬體負載平衡器廠商所提供的功能和設定選項。

設定硬體負載平衡器時，請考慮下列需求：

  - 您可以在 HLB 的硬體負載平衡器 () 上設定 [來源網路位址)  (轉譯]，以取得 Access Edge service 和 Web 會議 Edge service

  - 無法在 A/V Edge service 上設定 SNAT – A/V Edge service 必須以實際伺服器位址（而非 HLB 虛擬 IP (VIP) ）回應，以透過 UDP over NAT 的簡單遍歷 (STUN) /traversal 使用轉送 NAT (將) /federation 關閉 (FTURN) 才能正常運作
    
      - 如果用戶端將要求傳送給 HLB，回應必須從 HLB VIP 傳回
    
      - 如果用戶端將要求傳送給 Edge，回應必須從 Edge IP 傳回

  - 公用 IP 位址會用於每個伺服器介面及 HLB 的 Vip 上，而您的公用 IP 位址需求為 N + 1，其中每個實際伺服器介面的公用 IP 位址，以及每個 HLB VIP 的一個公用 IP 位址。 在集區中有2部 Edge server 的地方，這會產生9個公用 IP 位址，其中3是用於 HLB Vip，另一個則用於每個 Edge server 介面， (伺服器總共六個) 

  - 針對 Access Edge service 和 Web 會議 Edge service， (和使用 HLB 上的 NAT) 用戶端會接觸 VIP，VIP 會將來源 IP 位址從用戶端變更為自己的 IP 位址。 伺服器介面會將寄件者位址定址至 VIP，VIP 會從伺服器介面 IP 位址變更來源位址，並將資料包傳送給用戶端。

  - 在 A/V Edge service 中，VIP 不得變更來源 IP 位址，而且實際伺服器位址會直接傳回用戶端–您無法在 HLB 上設定用於 AV 流量的 NAT。
    
      - 如果用戶端將要求傳送至 HLB VIP，回應必須從 HLB VIP 傳回
    
      - 如果用戶端將要求傳送至 Edge IP，回應必須從 Edge IP 傳回

  - 對於 AV，外部防火牆將保留所有資料包的實際伺服器公用 IP 位址

  - 在建立後，用戶端對 A/V Edge service 通訊是指實際伺服器，而非 HLB

  - 內部 edge 至內部伺服器和用戶端必須路由傳送，且為主控伺服器或用戶端的所有內部網路設定持久路由

  - HLB Access Edge service VIP 將充當每個 Edge server 介面的預設閘道

<div>


> [!NOTE]
> 如需有關 NAT 規劃及功能的進一步資訊，請參閱 <A href="lync-server-2013-hardware-load-balancer-requirements.md">Lync Server 2013 的硬體負載平衡器需求</A>。



</div>

![Edge Server 埠與通訊協定詳細資料](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Edge Server 埠與通訊協定詳細資料")

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a>調整式合併 Edge （硬體負載平衡）的必要外部埠設定：外部介面虛擬 Ip

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
<td><p>XMPP/TCP/5269</p></td>
<td><p>XMPP Proxy 服務 (與 Access Edge service 共用 IP 位址) </p></td>
<td><p>任何</p></td>
<td><p>XMPP Proxy 服務會將流量傳送至已定義 XMPP 同盟中的 XMPP 連絡人</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP (TLS) /TCP/443</p></td>
<td><p>任何</p></td>
<td><p>Access Edge service 公用 VIP 位址</p></td>
<td><p>外部使用者存取從用戶端到伺服器的 SIP 流量</p></td>
</tr>
<tr class="even">
<td><p>存取/SIP (MTLS) /TCP/5061</p></td>
<td><p>任何</p></td>
<td><p>Access Edge service 公用 VIP 位址</p></td>
<td><p>使用 SIP 的 SIP 信號、同盟和公用 IM 連線</p></td>
</tr>
<tr class="odd">
<td><p>存取/SIP (MTLS) /TCP/5061</p></td>
<td><p>Access Edge service 公用 VIP 位址</p></td>
<td><p>同盟合作夥伴</p></td>
<td><p>使用 SIP 的 SIP 信號、同盟和公用 IM 連線</p></td>
</tr>
<tr class="even">
<td><p>Web 會議/PSOM (TLS) /TCP/443</p></td>
<td><p>任何</p></td>
<td><p>Edge Server Web 會議 Edge service 公用 VIP 位址</p></td>
<td><p>Web 會議媒體</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN、MSTURN/UDP/3478</p></td>
<td><p>任何</p></td>
<td><p>Edge Server A/V Edge service 公用 VIP 位址</p></td>
<td><p>透過 UDP/3478 之 STUN/TURN 候選的交涉</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN、MSTURN/TCP/443</p></td>
<td><p>任何</p></td>
<td><p>Edge Server A/V Edge service 公用 VIP 位址</p></td>
<td><p>透過 UDP/443 之 STUN/TURN 候選的交涉</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a>調整式合併 Edge 的防火牆摘要（硬體負載平衡）：內部介面虛擬 Ip

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
<td><p>任何 (都可以定義為 Director、Director 集區虛擬 IP 位址、前端伺服器或前端集區虛擬 IP 位址) </p></td>
<td><p>Edge Server 內部 VIP 介面</p></td>
<td><p>從 Director、Director 集區虛擬 IP 位址、前端伺服器或前端集區虛擬 IP 位址 (到內部 Edge VIP 的輸出 SIP 流量) </p></td>
</tr>
<tr class="even">
<td><p>存取/SIP (MTLS) /TCP/5061</p></td>
<td><p>Edge Server 內部 VIP 介面</p></td>
<td><p>任何 (都可以定義為 Director、Director 集區虛擬 IP 位址、前端伺服器或前端集區虛擬 IP 位址) </p></td>
<td><p>從 Edge Server 內部介面) 的輸入 SIP 流量 (到 Director、Director 集區虛擬 IP 位址、前端伺服器或前端集區虛擬 IP 位址</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>任何 (都可以定義為前端伺服器的 IP 位址，或前端集區的 IP 位址，或是使用此 Edge Server 的任何 Survivable Branch 裝置或 Survivable Branch 伺服器) </p></td>
<td><p>Edge Server 內部 VIP 介面</p></td>
<td><p>A/V 使用者的驗證 (A/V 驗證服務) 來自前端伺服器或前端集區的 IP 位址，或是使用此 Edge Server 的任何 Survivable 分支裝置或 Survivable 分支伺服器</p></td>
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

