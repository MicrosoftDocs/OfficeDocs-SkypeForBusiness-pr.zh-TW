---
title: Lync Server 2013：SIP 直接部署選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Direct SIP deployment options
ms:assetid: 84691944-03f2-4a89-9f2b-1ab3d7f388cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398672(v=OCS.15)
ms:contentKeyID: 48184692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e88dd5a576e467fbca25e9f467bd168fd6401d17
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762221"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="direct-sip-deployment-options-in-lync-server-2013"></a><span data-ttu-id="0b083-102">Lync Server 2013 中的 SIP 直接部署選項</span><span class="sxs-lookup"><span data-stu-id="0b083-102">Direct SIP deployment options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b083-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="0b083-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="0b083-104">本主題提供部署直接 SIP 連線的範例拓撲。</span><span class="sxs-lookup"><span data-stu-id="0b083-104">This topic provides example topologies for deploying direct SIP connections.</span></span>

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a><span data-ttu-id="0b083-105">Lync Server 獨立</span><span class="sxs-lookup"><span data-stu-id="0b083-105">Lync Server Stand-Alone</span></span>

<span data-ttu-id="0b083-106">如果您的組織使用本節所述的其中一個部署，您就可以使用 Lync Server 2013 做為部分或整個組織的唯一電話方案。</span><span class="sxs-lookup"><span data-stu-id="0b083-106">If your organization uses one of the deployments described in this section, you can use Lync Server 2013 as the sole telephony solution for part or all of an organization.</span></span> <span data-ttu-id="0b083-107">本節詳細說明下列部署：</span><span class="sxs-lookup"><span data-stu-id="0b083-107">This section describes the following deployments in detail:</span></span>

  - <span data-ttu-id="0b083-108">**增量式部署：** 此選項假設您有現有的專用分支 exchange （PBX）基礎結構，而且您想要將企業語音逐步引入到貴組織內較小的群組或小組中。</span><span class="sxs-lookup"><span data-stu-id="0b083-108">**Incremental deployment:** This option assumes that you have an existing private branch exchange (PBX) infrastructure and you intend to introduce Enterprise Voice incrementally to smaller groups or teams within your organization.</span></span>

  - <span data-ttu-id="0b083-109">**Lync Server VoIP 專用式部署：** 此選項假設您要考慮在沒有傳統電話結構的網站上部署企業語音。</span><span class="sxs-lookup"><span data-stu-id="0b083-109">**Lync Server VoIP-only deployment:** this option assumes that you are considering deploying Enterprise Voice at a site that does not have a traditional telephony infrastructure.</span></span>

<div>

## <a name="incremental-deployment"></a><span data-ttu-id="0b083-110">漸進式部署</span><span class="sxs-lookup"><span data-stu-id="0b083-110">Incremental Deployment</span></span>

<span data-ttu-id="0b083-111">在增量式部署中，Lync Server 2013 是個別小組或部門的唯一電話方案，而組織中的其他使用者仍可繼續使用 PBX。</span><span class="sxs-lookup"><span data-stu-id="0b083-111">In incremental deployment, Lync Server 2013 is the sole telephony solution for individual teams or departments, while the rest of the users in an organization continue to use a PBX.</span></span> <span data-ttu-id="0b083-112">此增量式部署策略提供一種方式，透過受控制的試驗計畫將 IP 電話引入您的企業。</span><span class="sxs-lookup"><span data-stu-id="0b083-112">This incremental deployment strategy provides one way to introduce IP telephony into your enterprise through controlled pilot programs.</span></span> <span data-ttu-id="0b083-113">Microsoft 整合通訊需要最佳服務的工作組會移至企業語音，而其他使用者則會保留在現有的 PBX 中。</span><span class="sxs-lookup"><span data-stu-id="0b083-113">Workgroups whose communication needs are best served by Microsoft Unified Communications are moved to Enterprise Voice, while other users remain on the existing PBX.</span></span> <span data-ttu-id="0b083-114">您可以視需要將其他工作組遷移至企業語音。</span><span class="sxs-lookup"><span data-stu-id="0b083-114">Additional workgroups can be migrated to Enterprise Voice, as needed.</span></span>

<span data-ttu-id="0b083-115">如果您明確定義的使用者群組有共同的通訊需求，且其本身提供集中式管理，則建議使用 [遞增] 選項。</span><span class="sxs-lookup"><span data-stu-id="0b083-115">The incremental option is recommended if you have clearly defined user groups that have communication requirements in common and that lend themselves to centralized management.</span></span> <span data-ttu-id="0b083-116">如果您的小組或部門分佈于廣域地理區域，且在長途電話費用中的節約可能相當重要，此選項也很有效。</span><span class="sxs-lookup"><span data-stu-id="0b083-116">This option is also effective if you have teams or departments that are spread over wide geographic areas, where the savings in long-distance charges can be significant.</span></span> <span data-ttu-id="0b083-117">事實上，此選項對於建立成員可能散佈在地球上的虛擬小組非常有用。</span><span class="sxs-lookup"><span data-stu-id="0b083-117">In fact, this option is useful for creating virtual teams whose members may be scattered across the globe.</span></span> <span data-ttu-id="0b083-118">您可以建立、修改或解散此類小組，以快速回應變化的商業需求。</span><span class="sxs-lookup"><span data-stu-id="0b083-118">You can create, modify, or disband such teams in rapid response to shifting business requirements.</span></span>

<span data-ttu-id="0b083-119">下圖顯示在 PBX 後部署企業語音的一般拓撲。</span><span class="sxs-lookup"><span data-stu-id="0b083-119">The following figure shows the generic topology for deployment of Enterprise Voice behind a PBX.</span></span> <span data-ttu-id="0b083-120">這是漸進式部署的建議拓撲。</span><span class="sxs-lookup"><span data-stu-id="0b083-120">This is the recommended topology for incremental deployment.</span></span>

<span data-ttu-id="0b083-121">**增量式部署選項**</span><span class="sxs-lookup"><span data-stu-id="0b083-121">**Incremental deployment option**</span></span>

<span data-ttu-id="0b083-122">![部門的移轉選項圖表](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "部門的移轉選項圖表")</span><span class="sxs-lookup"><span data-stu-id="0b083-122">![Departmental Migration Option diagram](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Departmental Migration Option diagram")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0b083-123">如果您將 Lync Server 部署連線到認證的直接 SIP 合作夥伴，則不需要在中繼伺服器與 PBX 之間的公用交換電話網絡（PSTN）閘道。</span><span class="sxs-lookup"><span data-stu-id="0b083-123">If you are connecting your Lync Server deployment to a certified Direct SIP partner, a public switched telephone network (PSTN) gateway between the Mediation Server and the PBX is not required.</span></span> <span data-ttu-id="0b083-124">如需認證直接 SIP 合作夥伴的清單，請參閱 Microsoft 整合通訊開啟互通性計畫<A href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</A>網站。</span><span class="sxs-lookup"><span data-stu-id="0b083-124">For a list of certified Direct SIP partners, see the Microsoft Unified Communications Open Interoperability Program website at <A href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="0b083-125">此圖所示的媒體路徑已啟用媒體旁路（建議的配置）。</span><span class="sxs-lookup"><span data-stu-id="0b083-125">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="0b083-126">如果您選用停用媒體旁路，媒體路徑會透過中繼伺服器進行路由。</span><span class="sxs-lookup"><span data-stu-id="0b083-126">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

<span data-ttu-id="0b083-127">在此拓撲中，已選取的部門或工作組可供企業語音。</span><span class="sxs-lookup"><span data-stu-id="0b083-127">In this topology, selected departments or workgroups are enabled for Enterprise Voice.</span></span> <span data-ttu-id="0b083-128">PSTN 閘道會將語音透過網際網路通訊協定（VoIP）的工作組連結到 PBX。</span><span class="sxs-lookup"><span data-stu-id="0b083-128">A PSTN gateway links the Voice over Internet Protocol (VoIP)-enabled workgroup to the PBX.</span></span> <span data-ttu-id="0b083-129">已啟用企業語音的使用者，包括遠端工作人員、透過 IP 網路進行通訊。</span><span class="sxs-lookup"><span data-stu-id="0b083-129">Users who are enabled for Enterprise Voice, including remote workers, communicate across the IP network.</span></span> <span data-ttu-id="0b083-130">企業語音使用者通話至 PSTN，而未啟用企業語音的同事則會路由至適當的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="0b083-130">Calls by Enterprise Voice users to the PSTN and to coworkers who are not enabled for Enterprise Voice are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="0b083-131">來自仍在 PBX 系統或從 PSTN 的呼叫者的同事的呼叫會路由到 PSTN 閘道，並將呼叫轉寄給 Lync Server 進行路由。</span><span class="sxs-lookup"><span data-stu-id="0b083-131">Calls from colleagues who are still on the PBX system, or from callers on the PSTN, are routed to the PSTN gateway, which forwards the calls to Lync Server for routing.</span></span>

<span data-ttu-id="0b083-132">將企業語音連接至現有的 PBX 基礎結構以進行互通性時，有兩個建議的設定：在 PBX 前，在 PBX 和企業語音背後使用企業語音。</span><span class="sxs-lookup"><span data-stu-id="0b083-132">There are two recommended configurations for connecting Enterprise Voice to an existing PBX infrastructure for interoperability: Enterprise Voice behind the PBX and Enterprise Voice in front of the PBX.</span></span>

<div>

## <a name="enterprise-voice-behind-the-pbx"></a><span data-ttu-id="0b083-133">在 PBX 後的企業語音</span><span class="sxs-lookup"><span data-stu-id="0b083-133">Enterprise Voice Behind the PBX</span></span>

<span data-ttu-id="0b083-134">當企業語音部署在 PBX 之後，所有來自 PSTN 的呼叫都會送到 PBX，將呼叫企業語音使用者的電話路由至 PSTN 閘道，並呼叫 pbx 使用者至 PBX。</span><span class="sxs-lookup"><span data-stu-id="0b083-134">When Enterprise Voice is deployed behind the PBX, all calls from the PSTN arrive at the PBX, which routes calls to Enterprise Voice users to a PSTN gateway, and calls to PBX users to the PBX.</span></span>

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a><span data-ttu-id="0b083-135">PBX 前面的企業語音</span><span class="sxs-lookup"><span data-stu-id="0b083-135">Enterprise Voice in Front of the PBX</span></span>

<span data-ttu-id="0b083-136">在 PBX 前面部署企業語音時，所有來電都會到達 PSTN 閘道，這會將企業語音使用者的呼叫路由至 Lync Server，並呼叫 pbx 使用者至 PBX。</span><span class="sxs-lookup"><span data-stu-id="0b083-136">When Enterprise Voice is deployed in front of the PBX, all calls arrive at the PSTN gateway, which routes calls for Enterprise Voice users to Lync Server and calls for PBX users to the PBX.</span></span> <span data-ttu-id="0b083-137">從企業語音和 PBX 使用者到 PSTN 的呼叫都是透過 IP 網路路由到最經濟高效的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="0b083-137">Calls to the PSTN from both Enterprise Voice and PBX users are routed over the IP network to the most cost-efficient PSTN gateway.</span></span> <span data-ttu-id="0b083-138">下表顯示這項設定的優點與缺點。</span><span class="sxs-lookup"><span data-stu-id="0b083-138">The following table shows the advantages and disadvantages of this configuration.</span></span>

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a><span data-ttu-id="0b083-139">在 PBX 前面部署企業語音的優點與缺點</span><span class="sxs-lookup"><span data-stu-id="0b083-139">Advantages and Disadvantages of Deploying Enterprise Voice in Front of PBX</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0b083-140">優勢</span><span class="sxs-lookup"><span data-stu-id="0b083-140">Advantages</span></span></th>
<th><span data-ttu-id="0b083-141">劣勢</span><span class="sxs-lookup"><span data-stu-id="0b083-141">Disadvantages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0b083-142">PBX 仍可為不支援企業語音的使用者提供服務。</span><span class="sxs-lookup"><span data-stu-id="0b083-142">PBX still serves users not enabled for Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="0b083-143">現有的閘道可能不支援您想要的功能或容量。</span><span class="sxs-lookup"><span data-stu-id="0b083-143">Existing gateways may not support the features or capacity that you want.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b083-144">PBX 會處理所有先前的裝置。</span><span class="sxs-lookup"><span data-stu-id="0b083-144">PBX handles all earlier devices.</span></span></p></td>
<td><p><span data-ttu-id="0b083-145">需要從閘道到 PBX 的主幹，以及從閘道到中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="0b083-145">Requires a trunk from gateway to the PBX and from the gateway to the Mediation Server.</span></span> <span data-ttu-id="0b083-146">您可能需要來自服務提供者的其他 trunks。</span><span class="sxs-lookup"><span data-stu-id="0b083-146">You may need more trunks from the service provider.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b083-147">企業語音使用者會保留相同的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="0b083-147">Enterprise Voice users keep the same phone numbers.</span></span></p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a><span data-ttu-id="0b083-148">Lync Server VoIP 專用部署</span><span class="sxs-lookup"><span data-stu-id="0b083-148">Lync Server VoIP-Only Deployment</span></span>

<span data-ttu-id="0b083-149">企業語音提供新的企業，以及現有企業的新 office 網站，有機會可以實施完整的 VoIP 解決方案，而不必擔心 PBX 整合，或導致大量的部署和維護。IP PBX 基礎結構的成本。</span><span class="sxs-lookup"><span data-stu-id="0b083-149">Enterprise Voice provides new businesses, and also new office sites for existing businesses, with the opportunity to implement a full-featured VoIP solution without having to worry about PBX integration or incurring the substantial deployment and maintenance costs of an IP-PBX infrastructure.</span></span> <span data-ttu-id="0b083-150">這個方案同時支援現場與遠端員工。</span><span class="sxs-lookup"><span data-stu-id="0b083-150">This solution supports both on-site and remote workers.</span></span>

<span data-ttu-id="0b083-151">在此部署中，所有通話都是經由 IP 網路路由。</span><span class="sxs-lookup"><span data-stu-id="0b083-151">In this deployment, all calls are routed over the IP network.</span></span> <span data-ttu-id="0b083-152">PSTN 的呼叫會路由至適當的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="0b083-152">Calls to the PSTN are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="0b083-153">Lync 2013 或 Lync 手機版是以 softphone 的方式進行。</span><span class="sxs-lookup"><span data-stu-id="0b083-153">Lync 2013 or Lync Phone Edition serves as a softphone.</span></span> <span data-ttu-id="0b083-154">遠端通話控制無法使用且不必要，因為沒有可供使用者控制的 PBX 電話。</span><span class="sxs-lookup"><span data-stu-id="0b083-154">Remote call control is unavailable and unnecessary because there are no PBX phones for users to control.</span></span> <span data-ttu-id="0b083-155">語音信箱和自動助理服務可透過 [Exchange 整合訊息（UM）] 的選擇性部署來使用。</span><span class="sxs-lookup"><span data-stu-id="0b083-155">Voice mail and auto-attendant services are available through the optional deployment of Exchange Unified Messaging (UM).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0b083-156">除了支援 Lync Server 2013 所需的網路基礎結構之外，VoIP 專用部署還可以使用小型的合格閘道來支援傳真機和類比裝置。</span><span class="sxs-lookup"><span data-stu-id="0b083-156">In addition to the network infrastructure that is required to support Lync Server 2013, a VoIP-only deployment can use a small, qualified gateway to support fax machines and analog devices.</span></span>



</div>

<span data-ttu-id="0b083-157">下圖顯示僅限 VoIP 部署的一般拓撲。</span><span class="sxs-lookup"><span data-stu-id="0b083-157">The following figure shows a typical topology for a VoIP-only deployment.</span></span>

<span data-ttu-id="0b083-158">**僅限 VoIP 部署選項**</span><span class="sxs-lookup"><span data-stu-id="0b083-158">**VoIP-only deployment option**</span></span>

<span data-ttu-id="0b083-159">![Greenfidle 部署選項](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle 部署選項")</span><span class="sxs-lookup"><span data-stu-id="0b083-159">![Greenfidle deployment option](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle deployment option")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0b083-160">此圖所示的媒體路徑已啟用媒體旁路（建議的配置）。</span><span class="sxs-lookup"><span data-stu-id="0b083-160">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="0b083-161">如果您選用停用媒體旁路，媒體路徑會透過中繼伺服器進行路由。</span><span class="sxs-lookup"><span data-stu-id="0b083-161">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

