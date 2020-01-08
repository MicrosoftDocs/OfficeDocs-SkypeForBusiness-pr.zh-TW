---
title: Lync Server 2013：SIP 直接部署選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Direct SIP deployment options
ms:assetid: 84691944-03f2-4a89-9f2b-1ab3d7f388cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398672(v=OCS.15)
ms:contentKeyID: 48184692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 277b64346dc17815438f2ac34da58f36d2b150f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982743"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="direct-sip-deployment-options-in-lync-server-2013"></a>Lync Server 2013 中的 SIP 直接部署選項

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

本主題提供部署直接 SIP 連線的範例拓撲。

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a>Lync Server 獨立

如果您的組織使用本節所述的其中一個部署，您就可以使用 Lync Server 2013 做為部分或整個組織的唯一電話方案。 本節詳細說明下列部署：

  - **增量式部署：** 此選項假設您有現有的專用分支 exchange （PBX）基礎結構，而且您想要將企業語音逐步引入到貴組織內較小的群組或小組中。

  - **Lync Server VoIP 專用式部署：** 此選項假設您要考慮在沒有傳統電話結構的網站上部署企業語音。

<div>

## <a name="incremental-deployment"></a>漸進式部署

在增量式部署中，Lync Server 2013 是個別小組或部門的唯一電話方案，而組織中的其他使用者仍可繼續使用 PBX。 此增量式部署策略提供一種方式，透過受控制的試驗計畫將 IP 電話引入您的企業。 Microsoft 整合通訊需要最佳服務的工作組會移至企業語音，而其他使用者則會保留在現有的 PBX 中。 您可以視需要將其他工作組遷移至企業語音。

如果您明確定義的使用者群組有共同的通訊需求，且其本身提供集中式管理，則建議使用 [遞增] 選項。 如果您的小組或部門分佈于廣域地理區域，且在長途電話費用中的節約可能相當重要，此選項也很有效。 事實上，此選項對於建立成員可能散佈在地球上的虛擬小組非常有用。 您可以建立、修改或解散此類小組，以快速回應變化的商業需求。

下圖顯示在 PBX 後部署企業語音的一般拓撲。 這是漸進式部署的建議拓撲。

**增量式部署選項**

![部門遷移選項圖表](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "部門遷移選項圖表")

<div>


> [!NOTE]  
> 如果您將 Lync Server 部署連線到認證的直接 SIP 合作夥伴，則不需要在中繼伺服器與 PBX 之間的公用交換電話網絡（PSTN）閘道。 如需認證直接 SIP 合作夥伴的清單，請參閱 Microsoft 整合通訊開啟互通性計畫<A href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</A>網站。



</div>

<div>


> [!NOTE]  
> 此圖所示的媒體路徑已啟用媒體旁路（建議的配置）。 如果您選用停用媒體旁路，媒體路徑會透過中繼伺服器進行路由。



</div>

在此拓撲中，已選取的部門或工作組可供企業語音。 PSTN 閘道會將語音透過網際網路通訊協定（VoIP）的工作組連結到 PBX。 已啟用企業語音的使用者，包括遠端工作人員、透過 IP 網路進行通訊。 企業語音使用者通話至 PSTN，而未啟用企業語音的同事則會路由至適當的 PSTN 閘道。 來自仍在 PBX 系統或從 PSTN 的呼叫者的同事的呼叫會路由到 PSTN 閘道，並將呼叫轉寄給 Lync Server 進行路由。

將企業語音連接至現有的 PBX 基礎結構以進行互通性時，有兩個建議的設定：在 PBX 前，在 PBX 和企業語音背後使用企業語音。

<div>

## <a name="enterprise-voice-behind-the-pbx"></a>在 PBX 後的企業語音

當企業語音部署在 PBX 之後，所有來自 PSTN 的呼叫都會送到 PBX，將呼叫企業語音使用者的電話路由至 PSTN 閘道，並呼叫 pbx 使用者至 PBX。

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a>PBX 前面的企業語音

在 PBX 前面部署企業語音時，所有來電都會到達 PSTN 閘道，這會將企業語音使用者的呼叫路由至 Lync Server，並呼叫 pbx 使用者至 PBX。 從企業語音和 PBX 使用者到 PSTN 的呼叫都是透過 IP 網路路由到最經濟高效的 PSTN 閘道。 下表顯示這項設定的優點與缺點。

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a>在 PBX 前面部署企業語音的優點與缺點

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>優勢</th>
<th>劣勢</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PBX 仍可為不支援企業語音的使用者提供服務。</p></td>
<td><p>現有的閘道可能不支援您想要的功能或容量。</p></td>
</tr>
<tr class="even">
<td><p>PBX 會處理所有先前的裝置。</p></td>
<td><p>需要從閘道到 PBX 的主幹，以及從閘道到中繼伺服器。 您可能需要來自服務提供者的其他 trunks。</p></td>
</tr>
<tr class="odd">
<td><p>企業語音使用者會保留相同的電話號碼。</p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a>Lync Server VoIP 專用部署

企業語音提供新的企業，以及現有企業的新 office 網站，有機會可以實施完整的 VoIP 解決方案，而不必擔心 PBX 整合，或導致大量的部署和維護。IP PBX 基礎結構的成本。 這個方案同時支援現場與遠端員工。

在此部署中，所有通話都是經由 IP 網路路由。 PSTN 的呼叫會路由至適當的 PSTN 閘道。 Lync 2013 或 Lync 手機版是以 softphone 的方式進行。 遠端通話控制無法使用且不必要，因為沒有可供使用者控制的 PBX 電話。 語音信箱和自動助理服務可透過 [Exchange 整合訊息（UM）] 的選擇性部署來使用。

<div>


> [!NOTE]  
> 除了支援 Lync Server 2013 所需的網路基礎結構之外，VoIP 專用部署還可以使用小型的合格閘道來支援傳真機和類比裝置。



</div>

下圖顯示僅限 VoIP 部署的一般拓撲。

**僅限 VoIP 部署選項**

![Greenfidle 部署選項](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle 部署選項")

<div>


> [!NOTE]  
> 此圖所示的媒體路徑已啟用媒體旁路（建議的配置）。 如果您選用停用媒體旁路，媒體路徑會透過中繼伺服器進行路由。



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

