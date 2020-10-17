---
title: Lync Server 2013：外部使用者存取的案例
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
ms.openlocfilehash: c8404a48ae4a8fce5f0d0a85fd5aa36824152c9d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510850"
---
# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013 中的外部使用者存取案例

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-08_

提供外部使用者存取的 Lync Server 2013 時，需要在周邊網路中至少部署一個 Edge Server 與一個反向 proxy。 您也可以選擇性地在內部網路中部署 Director 或 Director 集區。

如果您需要的容量大於單一 Edge Server 所能提供的容量，或如果您需要 Edge Server 部署的高可用性，您可以在負載平衡集區中設定負載平衡及部署多部 Edge server。 如果您的組織有多個資料中心，您可以讓 Edge Server 或 Edge 集區部署位於一個以上的位置。 不過，只有其中一個 Edge Server 部署可以指定為同盟路由。

本節定義 Edge Server 部署的案例，並將規劃區段對應至可能的案例。 例如，如果您的部署需要高可用性、具有可延伸訊息和顯示狀態的同盟 (XMPP) 連絡人和 Lync 行動性，請選取下表中符合這些需求的相符專案，並使用參考的規劃區段來定義您的部署，如下流程圖所示。

**Edge Server 部署案例選擇程序**

![範例部署流程圖](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "範例部署流程圖")

使用此程式，您可以規劃及記錄您要為使用者部署的所有潛在功能設定。 不過，您可以在部署 Edge Server 後新增同盟及行動性服務，並在新增其他功能之前確認正確的操作。 在 [部署] 區段中涵蓋將功能新增至現有 Edge Server 部署的程式。 如需有關部署的詳細資訊，請參閱在初次規劃程式期間， [在 Lync Server 2013 中部署外部使用者存取](lync-server-2013-deploying-external-user-access.md) ，您可以為新增的功能準備 dns、防火牆和憑證需求，這樣可讓您預先取得憑證及設定 dns 及埠/通訊協定需求。

<div>


> [!TIP]  
> 如果您打算安裝 Edge Server 和反向 proxy，然後在稍後新增功能 (例如，同盟與行動性) ，請決定部署後所有服務所需的憑證。 預先規劃及取得所有功能的憑證，最初部署的憑證，可讓您不必定購新的憑證，以滿足同盟 (的需求，也就是在 Edge Server 上) 或反向 proxy (也是針對行動服務) 。



</div>

<div>


> [!NOTE]  
> 在每一部 Edge Server 上執行所有 edge 服務。 無法在兩個不同的 Edge Server 之間分割服務。 如果您部署 Edge 集區以取得可擴充性，所有 edge service 都會部署在集區中的每一部 Edge Server 上。 XMPP 同盟、Office 通訊伺服器和 Lync Server 同盟、公用 IM 連線和用戶端行動是在您部署第一部 Edge Server 或 Edge 集區之後，可以部署的其他服務。 Mobility Service 是一種使用反向 Proxy 的功能。 安裝行動服務不會將功能新增至 Edge Server，但需要重新配置反向 proxy。 列出這些功能的 <STRONG>安裝目標</STRONG> 欄，會在 edge <STRONG>Server 計畫區段</STRONG> 底下的相關欄中提供規劃指導方針，以在安裝及設定 edge server 時同時規劃要部署的這些功能。



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
<p>如果您要在周邊環境中部署單一 Edge Server，請使用此規劃區段。 您將使用指派給 Edge Server 的私人 IP 位址部署 Edge Server，並使用 NAT 為網際網路上的外部使用者提供公用 IP 位址。</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Lync Server 2013 中的單一合併 edge （利用私人 IP 位址及 NAT）</a></p></td>
</tr>
<tr class="even">
<td><p>您已決定在您的基礎架構中，只需要一部 Edge Service 伺服器就足夠。您也打算要針對 Edge Server 外部介面使用公用 IP 位址來面向網際網路。</p>
<p>如果您要在周邊環境中部署單一 Edge Server，請使用此規劃區段。 您將使用指派給 Edge Server 的公用 IP 位址，部署 Edge Server。 在此案例中，您將使用路由取代 NAT。 Edge Server 的實際公用 IP 位址可供外部使用者連線使用。</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Lync Server 2013 中的單一合併 edge （使用公用 IP 位址）</a></p></td>
</tr>
<tr class="odd">
<td><p>您已決定 Edge Service 的高可用性對使用者來說非常重要，且您要在此集區內部署兩部以上的 Edge Server。您也打算要針對 Edge Server 外部介面使用私人 IP 位址，並使用 NAT 來面向網際網路。</p>
<p>如果您要在周邊環境中部署 Edge Server 集區，請使用此規劃區段。 您將使用 DNS 負載平衡來散佈整個集區中的通訊，以部署具有指派給 Edge Server 之私人 IP 位址的 Edge server。 您將使用 NAT 來提供網際網路之外部使用者所需的公用 IP 位址。</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Lync Server 2013 中的調整式合併 edge （使用 NAT 透過私人 IP 位址進行 DNS 負載平衡）</a></p></td>
</tr>
<tr class="even">
<td><p>您已決定 Edge Service 的高可用性對使用者來說非常重要，且您要在此集區內部署兩部以上的 Edge Server。 您也想要對網際網路使用 Edge Server 外部介面的公用 IP 位址。</p>
<p>如果您要在周邊環境中部署 Edge Server 集區，請使用此規劃區段。 您將使用 DNS 負載平衡來散佈整個集區中的通訊，以部署具有指派給 Edge Server 之公用 IP 位址的 Edge server。 您不打算使用 NAT，而要使用路由傳送來提供網際網路之外部使用者所需的公用 IP 位址。</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Lync Server 2013 中的調整式合併 edge （透過公用 IP 位址進行 DNS 負載平衡）</a></p></td>
</tr>
<tr class="odd">
<td><p>您已決定 Edge service 的高可用性對您的使用者來說很重要，且您將使用硬體負載平衡器在此集區中部署兩部以上的 Edge Server。</p>
<p>如果您要在周邊環境中部署 Edge Server 集區，請使用此規劃區段。 您將使用硬體負載平衡器來散佈跨集區的通訊，以指派給 Edge Server 的公用 IP 位址，來部署 Edge Server。 您不打算使用 NAT，而要使用路由傳送來提供網際網路之外部使用者所需的公用 IP 位址。</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Lync Server 2013 中的調整式合併 edge （搭配硬體負載平衡器）</a></p></td>
</tr>
<tr class="even">
<td><p>您可使用同盟案例來規劃可擴充與使用者進行通訊之協力廠商類型的功能。</p>
<ul>
<li><p>Lync Server 同盟</p></li>
<li><p>Office 通訊伺服器同盟</p></li>
<li><p>公共 IM 連線</p></li>
<li><p>XMPP 同盟</p></li>
</ul></td>
<td><p>規劃同盟案例</p>
<ul>
<li><p><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">規劃 Lync Server 2013 和 Office 通訊伺服器同盟</a></p></li>
<li><p><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">在 Lync Server 2013 中規劃公用立即訊息連線</a></p></li>
<li><p><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">在 Lync Server 2013 中規劃可擴展郵件和顯示狀態通訊協定 (XMPP) 同盟</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>行動性服務是透過反向 proxy 提供。 對外部使用者啟用行動性的服務會部署在前端伺服器或前端集區上。 您可以在反向 proxy 上建立或修改現有的發行規則，為外部使用者啟用行動服務。</p></td>
<td><p><a href="lync-server-2013-planning-for-mobility.md">在 Lync Server 2013 中規劃行動性</a></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> 在下列案例區段中，為參考架構、範例 DNS、埠/通訊協定定義和憑證需求。 此外，也包含您的 DNS、埠/通訊協定定義和憑證需求的圖表。 圖表會提供範本，供您用來填入或散佈至其他小組 (例如，組織的網路小組、公開金鑰基礎結構小組和伺服器部署小組) 。 圖表的目的是為了加強通訊，並在將必要的 Edge Server 設定元素傳遞給將執行實際設定工作的人員時，確保成功。 建議您使用圖表和相關的參考架構規劃您的部署。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

