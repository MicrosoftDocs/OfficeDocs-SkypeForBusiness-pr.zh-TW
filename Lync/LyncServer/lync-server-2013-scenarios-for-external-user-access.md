---
title: 外部使用者存取的 Lync Server 2013： 案例
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
ms.openlocfilehash: a237a971bbf98636b81fa028c9b64721364fca07
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144201"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013 中的外部使用者存取的案例

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-08_

提供 Lync Server 2013 的外部使用者存取需要您先部署在周邊網路中，至少有一部 Edge Server 和一個反向 proxy。 或者，您可以在其中部署 Director 或 Director 集區中您的內部網路。

如果您需要更多的容量，比可以提供單一 Edge Server，或如果您需要為 Edge Server 部署高可用性，您可以設定負載平衡功能和部署多部 Edge Server 的負載平衡集區中。 如果組織有多個資料中心，您可以有多個位置的 Edge Server 或 Edge 集區部署。 不過，只有其中一個 Edge Server 部署可以指定作為同盟路由。

本節定義 Edge Server 部署案例，並將對應的可能案例規劃章節。 例如，如果您的部署需要高可用性，以可延伸訊息和目前狀態 (XMPP) 的連絡人，以及 Lync mobility 同盟選取相符的項目會滿足這些需求，使用下列表格中下列流程圖所示，請參考規劃的各節，以定義您的部署。

**Edge Server 部署案例選擇程序**

![範例部署流程圖](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "範例部署流程圖")

藉由使用此程序，您可以規劃及文件的所有潛在的功能，您想要部署為您的使用者設定。 不過，您可以新增同盟和行動服務後您已部署 Edge Server 並確認正確的操作，才能新增其他功能。 將功能新增至現有的 Edge Server 部署的程序涵蓋在 [部署] 區段中。 如需部署的詳細資訊，請參閱[部署外部使用者存取 Lync Server 2013 中](lync-server-2013-deploying-external-user-access.md)藉由包括在初始的規劃程序期間進行規劃的這些功能，您可以準備 DNS、 防火牆和憑證需求的新增功能，可讓您取得憑證並設定 DNS 和連接埠/通訊協定需求事先。

<div>


> [!TIP]  
> 如果您計劃要安裝 Edge Server 和反向 proxy，然後新增功能更新版本 （例如，同盟和行動），決定您需要的所有服務之後部署何種憑證。 規劃並了解取得憑證，事先，所有功能的初始部署或沒看到，請儲存您不必順序新的憑證，以滿足需求的同盟 (亦即在 Edge Server 上) 或反向 proxy (也就是行動服務）。



</div>

<div>


> [!NOTE]  
> 在每部 Edge Server 上執行所有 edge 服務。 服務無法兩個不同的 Edge 伺服器之間分割。 如果您部署的延展性的 Edge 集區，在集區中每個 Edge Server 上要部署的所有 edge 服務。 XMPP 同盟、 Office Communications Server 及 Lync Server 同盟、 公用 IM 連線能力和用戶端行動性是您已部署您的第一個 Edge Server 或 Edge 集區之後，可以部署的其他服務。 Mobility Service 是一種使用反向 Proxy 的功能。 安裝行動服務不將功能加入您的 Edge Server，但需要重新設定您的反向 proxy。 列出這些功能的<STRONG>安裝目標</STRONG>欄同時規劃要部署 Edge Server 已安裝並設定當這些功能提供相關聯的資料行下<STRONG>Edge Server 規劃] 區段中或各節</STRONG>中的規劃指引。



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a>識別並對應您的部署目標


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>安裝目標</th>
<th>Edge Server 規劃文件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>您已決定在您的基礎架構中，只需要一部 Edge Service 伺服器就足夠。您也打算要針對 Edge Server 外部介面使用私人 IP 位址，並使用 NAT 來面向網際網路。</p>
<p>使用此計劃] 區段中，如果您在您的周邊中部署單一 Edge Server。 您將部署 Edge Server 與私人 IP 位址指派給 Edge Server，並將使用 NAT 網際網路上的外部使用者提供的公用 IP 位址。</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">私人 IP 位址及 NAT Lync Server 2013 中的單一合併的 edge</a></p></td>
</tr>
<tr class="even">
<td><p>您已決定在您的基礎架構中，只需要一部 Edge Service 伺服器就足夠。您也打算要針對 Edge Server 外部介面使用公用 IP 位址來面向網際網路。</p>
<p>使用此計劃] 區段中，如果您在您的周邊中部署單一 Edge Server。 您會使用公用 IP 位址指派給 Edge Server 部署 Edge Server。 而不是 NAT，您會使用此案例中的路由。 Edge Server 的實際公用 IP 位址是供外部使用者的連線數目。</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">與 Lync Server 2013 中的公用 IP 位址的單一合併的 edge</a></p></td>
</tr>
<tr class="odd">
<td><p>您已決定 Edge Service 的高可用性對使用者來說非常重要，且您要在此集區內部署兩部以上的 Edge Server。您也打算要針對 Edge Server 外部介面使用私人 IP 位址，並使用 NAT 來面向網際網路。</p>
<p>使用此計劃] 區段中，如果您要部署 Edge Server 集區中您周邊。 您將部署 Edge Server 與私人 IP 位址指派給 Edge Server，使用 DNS 負載平衡集區上散佈的通訊。 您將使用 NAT 來提供網際網路之外部使用者所需的公用 IP 位址。</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">調整式合併的 edge、 DNS 負載平衡與 Lync Server 2013 中使用 NAT 的私人 IP 位址</a></p></td>
</tr>
<tr class="even">
<td><p>您已決定 Edge Service 的高可用性對使用者來說非常重要，且您要在此集區內部署兩部以上的 Edge Server。 您也想要用於網際網路 Edge Server 外部介面公用 IP 位址。</p>
<p>使用此計劃] 區段中，如果您要部署 Edge Server 集區中您周邊。 您將部署 Edge Server 與公用 IP 位址指派給 Edge Server，使用 DNS 負載平衡集區上散佈的通訊。 您不打算使用 NAT，而要使用路由傳送來提供網際網路之外部使用者所需的公用 IP 位址。</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">調整式合併的 edge、 DNS 負載平衡與 Lync Server 2013 中的公用 IP 位址</a></p></td>
</tr>
<tr class="odd">
<td><p>您已決定 Edge service 的高可用性是重要給您的使用者，而您將部署兩部，或者使用硬體此集區中的更多 Edge Server 負載平衡器。</p>
<p>使用此計劃] 區段中，如果您要部署 Edge Server 集區中您周邊。 您將部署 Edge Server 與公用 IP 位址指派給 Edge Server，使用硬體負載平衡器集區上散佈的通訊。 您不打算使用 NAT，而要使用路由傳送來提供網際網路之外部使用者所需的公用 IP 位址。</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Lync Server 2013 中調整式合併的邊緣搭配硬體負載平衡器</a></p></td>
</tr>
<tr class="even">
<td><p>您可使用同盟案例來規劃可擴充與使用者進行通訊之協力廠商類型的功能。</p>
<ul>
<li><p>Lync Server 同盟</p></li>
<li><p>Office Communications Server 同盟</p></li>
<li><p>公共 IM 連線</p></li>
<li><p>XMPP 同盟</p></li>
</ul></td>
<td><p>規劃同盟案例</p>
<ul>
<li><p><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">規劃 Lync Server 2013 與 Office Communications Server 同盟</a></p></li>
<li><p><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">規劃 Lync Server 2013 中的 public instant messaging 連線</a></p></li>
<li><p><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">可延伸訊息與顯示狀態通訊協定 (XMPP) 同盟 Lync Server 2013 中規劃</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>行動服務提供通過反向 proxy。 服務，可以讓外部使用者的行動性部署上的前端伺服器或前端集區。 您建立或修改現有的發佈規則，以便為外部使用者的行動服務反向 proxy 上。</p></td>
<td><p><a href="lync-server-2013-planning-for-mobility.md">Lync Server 2013 中的行動規劃</a></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> 在下列案例中章節的某些參考架構、 範例 DNS、 連接埠/通訊協定定義和憑證需求。 也包含圖表用於您的 DNS，連接埠/通訊協定定義，而且需要憑證。 圖表會提供您填寫並散發至其他小組 （例如，貴組織的網路小組、 公用金鑰基礎結構小組和伺服器部署小組） 的範本。 圖表的目標是增強的通訊，並確保成功通訊所需的 Edge Server 組態元件會執行實際的人員時組態工作。 我們建議您使用的圖表和相關聯的參考架構規劃您的部署。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

