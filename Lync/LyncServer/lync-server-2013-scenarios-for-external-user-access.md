---
title: Lync Server 2013：外部使用者存取案例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for external user access
ms:assetid: 25697446-b045-4d12-9b1c-47f694b4f224
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425727(v=OCS.15)
ms:contentKeyID: 48183640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eab8323744615dc3f5d0b68f4325fbfb85bf911e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013 中的外部使用者存取案例

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-08_

提供 Lync Server 2013 的外部使用者存取需要您在周邊網路中至少部署一個 Edge 伺服器與一個反向 proxy。 您也可以選擇在內部網路中部署控制器或控制器池。

如果您需要比單一邊緣伺服器更大的容量，或者如果您的 Edge 伺服器部署需要高可用性，您可以在負載均衡的池中設定負載平衡與部署多個 Edge 伺服器。 如果您的組織有多個資料中心，您可以在一個以上的位置進行 Edge 伺服器或邊緣池部署。 不過，只有其中一個 Edge 伺服器部署可以指定為同盟路由。

本節定義 Edge 伺服器部署的案例，並將規劃區段對應至可能的案例。 例如，如果您的部署需要高可用性、具有可擴展訊息和目前狀態（XMPP）連絡人的同盟，以及 Lync 行動性，您可以在下表中選取符合這些需求的相符專案，並使用參照規劃區段來定義您的部署，如以下流程圖所示。

**Edge 伺服器部署案例選取流程**

![範例部署流程圖](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "範例部署流程圖")

您可以使用此程式來規劃並記錄您想要為使用者部署的所有可能功能的設定。 不過，您可以在部署 Edge 伺服器之後新增同盟與行動服務，並在新增其他功能之前確認正確的操作。 在現有的邊緣伺服器部署中新增功能的套裝程式含在 [部署] 區段中。 如需有關部署的詳細資料，請參閱在初次規劃程式期間，在[Lync Server 2013 中部署外部使用者存取](lync-server-2013-deploying-external-user-access.md)，您可以為新增功能準備 dns、防火牆和憑證需求，這可讓您提前取得證書並設定 dns 和埠/通訊協定需求。

<div>


> [!TIP]  
> 如果您打算安裝 Edge 伺服器和反向 proxy，然後在稍後新增功能（例如，同盟與行動行動），請判斷部署之後所有服務所需的憑證。 預先規劃及取得所有功能的憑證（初次部署），讓您不必定購新的憑證，就能滿足同盟的需求（也就是在 Edge 伺服器上），或是反向 proxy （也就是移動性的方式）。服務）。



</div>

<div>


> [!NOTE]  
> 所有 edge 服務都在每個 Edge 伺服器上執行。 無法在兩個不同的邊緣伺服器間分割服務。 如果您部署邊緣池以實現可伸縮性，則所有 edge 服務都會部署在該池中的每個 Edge 伺服器上。 XMPP 同盟、Office 通訊伺服器和 Lync Server 同盟、公用 IM 連線與客戶行動，也是部署第一個邊緣伺服器或 Edge 池之後可以部署的其他服務。 行動服務是使用反向 proxy 的功能。 安裝行動服務不會將功能新增到 Edge 伺服器，但需要重新配置您的反向 proxy。 列出這些功能的 [<STRONG>安裝目標</STRONG>] 欄會在 [ <STRONG>edge 伺服器規劃] 區段</STRONG>下的關聯欄中提供規劃指導方針，或按一下章節，在安裝及設定邊緣伺服器時，同時規劃要部署的這些功能。



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a>識別及對應您的部署目標


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>安裝目標</th>
<th>Edge 伺服器規劃檔</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>您已決定單一伺服器足以在您的基礎結構中提供 Edge 服務。 您也想要將使用 NAT 的邊緣伺服器外部介面的私人 IP 位址用於網際網路。</p>
<p>如果您要在您的周長部署單一邊緣伺服器，請使用此規劃區段。 您將會部署邊緣伺服器，並將私人 IP 位址指派給 Edge 伺服器，並將使用 NAT 為網際網路上的外部使用者提供公用 IP 位址。</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Lync Server 2013 中的單一合併 Edge (利用私人 IP 位址及 NAT)</a></p></td>
</tr>
<tr class="even">
<td><p>您已決定單一伺服器足以在您的基礎結構中提供 Edge 服務。 您也想要將邊緣伺服器外部介面的公用 IP 位址用於網際網路。</p>
<p>如果您要在您的周長部署單一邊緣伺服器，請使用此規劃區段。 您將會部署邊緣伺服器，並將公用 IP 位址指派給 Edge 伺服器。 在這種情況下，您將不會使用 NAT，而是使用路由。 外部使用者連線會提供邊緣伺服器的實際公用 IP 位址。</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Lync Server 2013 中的單一合併 Edge (利用公用 IP 位址)</a></p></td>
</tr>
<tr class="odd">
<td><p>您認為 Edge 服務的高可用性對您的使用者而言很重要，您將會在這個池中部署兩個或多個 Edge 伺服器。 您也想要將使用 NAT 的邊緣伺服器外部介面的私人 IP 位址用於網際網路。</p>
<p>如果您要在您的周長部署邊緣伺服器池，請使用此規劃區段。 您將使用 DNS 負載平衡來在整個池中散佈通訊，將邊緣伺服器部署成已指派給 Edge 伺服器的私人 IP 位址。 您將會使用 NAT，為網際網路上的外部使用者提供公用 IP 位址。</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Lync Server 2013 中的調整式合併 Edge (使用 NAT 透過私人 IP 位址進行 DNS 負載平衡)</a></p></td>
</tr>
<tr class="even">
<td><p>您認為 Edge 服務的高可用性對您的使用者而言很重要，您將會在這個池中部署兩個或多個 Edge 伺服器。 您也想要將邊緣伺服器外部介面的公用 IP 位址用於網際網路。</p>
<p>如果您要在您的周長部署邊緣伺服器池，請使用此規劃區段。 您將使用 DNS 負載平衡來在整個池中散佈通訊，將邊緣伺服器部署成指派給 Edge 伺服器的公用 IP 位址。 您會使用路由來為網際網路上的外部使用者提供公用 IP 位址（而不是 NAT）。</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Lync Server 2013 中的調整式合併 Edge (透過公用 IP 位址進行 DNS 負載平衡)</a></p></td>
</tr>
<tr class="odd">
<td><p>您認為 Edge 服務的高可用性對您的使用者而言很重要，您將會使用硬體負載平衡器在這個池中部署兩個或多個 Edge 伺服器。</p>
<p>如果您要在您的周長部署邊緣伺服器池，請使用此規劃區段。 您將使用硬體負載平衡器在整個池中散佈通訊，將邊緣伺服器部署成指派給 Edge 伺服器的公用 IP 位址。 您會使用路由來為網際網路上的外部使用者提供公用 IP 位址（而不是 NAT）。</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Lync Server 2013 中含硬體負載平衡器的調整式合併 Edge</a></p></td>
</tr>
<tr class="even">
<td><p>同盟案例可讓您規劃可延伸您的使用者可與之通訊之合作夥伴類型的功能。</p>
<ul>
<li><p>Lync Server 同盟</p></li>
<li><p>Office 通訊伺服器同盟</p></li>
<li><p>公用 IM 連線</p></li>
<li><p>XMPP 同盟</p></li>
</ul></td>
<td><p>規劃同盟案例</p>
<ul>
<li><p><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">規劃 Lync Server 2013 與 Office 通訊伺服器同盟</a></p></li>
<li><p><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">規劃 Lync Server 2013 中的公用立即訊息連線能力</a></p></li>
<li><p><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">在 Lync Server 2013 中規劃可擴展訊息和目前狀態通訊協定（XMPP）同盟</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>行動服務是透過反向 proxy 提供。 針對外部使用者啟用行動性的服務會部署在前端伺服器或頂層池。 您可以在反向 proxy 上建立或修改現有的發佈規則，為您的外部使用者啟用行動服務。</p></td>
<td><p><a href="lync-server-2013-planning-for-mobility.md">Lync Server 2013 中的行動規劃</a></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> 在下列案例區段中，是參考體系結構、範例 DNS、埠/通訊協定定義及證書需求。 也包含您的 DNS、埠/通訊協定定義及證書需求的圖表。 圖表會提供範本供您填入並散佈給其他小組（例如，貴組織的網路小組、公開金鑰基礎結構小組和伺服器部署小組）。 圖表的目標是加強溝通，並確保將必要的邊緣伺服器設定元素傳達給將執行實際設定工作的人員時，取得成功。 建議您使用圖表與關聯的參考體系結構來規劃您的部署。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

