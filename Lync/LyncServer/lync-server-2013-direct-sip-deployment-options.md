---
title: Lync Server 2013：直接 SIP 部署選項
description: Lync Server 2013：直接的 SIP 部署選項。
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
ms.openlocfilehash: 5afe361a5522ee4869bbdb572e5016437d5580d1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568239"
---
# <a name="direct-sip-deployment-options-in-lync-server-2013"></a><span data-ttu-id="c7d70-103">Lync Server 2013 中的直接 SIP 部署選項</span><span class="sxs-lookup"><span data-stu-id="c7d70-103">Direct SIP deployment options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7d70-104">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="c7d70-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="c7d70-105">本主題提供部署直接 SIP 連線的範例拓撲。</span><span class="sxs-lookup"><span data-stu-id="c7d70-105">This topic provides example topologies for deploying direct SIP connections.</span></span>

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a><span data-ttu-id="c7d70-106">Lync Server Stand-Alone</span><span class="sxs-lookup"><span data-stu-id="c7d70-106">Lync Server Stand-Alone</span></span>

<span data-ttu-id="c7d70-107">如果您的組織使用本節所述的其中一個部署，您可以使用 Lync Server 2013 作為部分或所有組織的唯一電話語音解決方案。</span><span class="sxs-lookup"><span data-stu-id="c7d70-107">If your organization uses one of the deployments described in this section, you can use Lync Server 2013 as the sole telephony solution for part or all of an organization.</span></span> <span data-ttu-id="c7d70-108">本節詳細說明下列部署：</span><span class="sxs-lookup"><span data-stu-id="c7d70-108">This section describes the following deployments in detail:</span></span>

  - <span data-ttu-id="c7d70-109">**漸進式部署：** 此選項假設您有現有的私人分公司 exchange (PBX) 基礎結構，而您想要將 Enterprise Voice 逐步引入組織中較小的群組或小組。</span><span class="sxs-lookup"><span data-stu-id="c7d70-109">**Incremental deployment:** This option assumes that you have an existing private branch exchange (PBX) infrastructure and you intend to introduce Enterprise Voice incrementally to smaller groups or teams within your organization.</span></span>

  - <span data-ttu-id="c7d70-110">**Lync Server 僅限 VoIP 部署：** 此選項假設您考慮在沒有傳統電話語音基礎結構的網站上部署 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="c7d70-110">**Lync Server VoIP-only deployment:** this option assumes that you are considering deploying Enterprise Voice at a site that does not have a traditional telephony infrastructure.</span></span>

<div>

## <a name="incremental-deployment"></a><span data-ttu-id="c7d70-111">漸進式部署</span><span class="sxs-lookup"><span data-stu-id="c7d70-111">Incremental Deployment</span></span>

<span data-ttu-id="c7d70-112">在漸進式部署中，Lync Server 2013 是個別小組或部門的唯一電話語音解決方案，而組織中的其他使用者仍會繼續使用 PBX。</span><span class="sxs-lookup"><span data-stu-id="c7d70-112">In incremental deployment, Lync Server 2013 is the sole telephony solution for individual teams or departments, while the rest of the users in an organization continue to use a PBX.</span></span> <span data-ttu-id="c7d70-113">這項增量部署策略提供一種方法，透過控制的試驗計畫，將 IP 電話語音引入您的企業。</span><span class="sxs-lookup"><span data-stu-id="c7d70-113">This incremental deployment strategy provides one way to introduce IP telephony into your enterprise through controlled pilot programs.</span></span> <span data-ttu-id="c7d70-114">Microsoft 整合通訊最適合使用其通訊的工作組會移至 Enterprise Voice，其他使用者仍會保留在現有的 PBX 上。</span><span class="sxs-lookup"><span data-stu-id="c7d70-114">Workgroups whose communication needs are best served by Microsoft Unified Communications are moved to Enterprise Voice, while other users remain on the existing PBX.</span></span> <span data-ttu-id="c7d70-115">其他的工作組可以視需要遷移至 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="c7d70-115">Additional workgroups can be migrated to Enterprise Voice, as needed.</span></span>

<span data-ttu-id="c7d70-116">如果您明確定義的使用者群組具有共同的通訊需求，且其本身適用于集中式管理，則建議使用 [累加] 選項。</span><span class="sxs-lookup"><span data-stu-id="c7d70-116">The incremental option is recommended if you have clearly defined user groups that have communication requirements in common and that lend themselves to centralized management.</span></span> <span data-ttu-id="c7d70-117">如果您擁有遍佈地理區域的團隊或部門，而且在長途計費中的節約成本可能很大，此選項也會有效。</span><span class="sxs-lookup"><span data-stu-id="c7d70-117">This option is also effective if you have teams or departments that are spread over wide geographic areas, where the savings in long-distance charges can be significant.</span></span> <span data-ttu-id="c7d70-118">實際上，此選項對於建立其成員可能分散在全球的虛擬小組非常有用。</span><span class="sxs-lookup"><span data-stu-id="c7d70-118">In fact, this option is useful for creating virtual teams whose members may be scattered across the globe.</span></span> <span data-ttu-id="c7d70-119">您可以建立、修改或 disband 這類團隊，以快速回應轉向的業務需求。</span><span class="sxs-lookup"><span data-stu-id="c7d70-119">You can create, modify, or disband such teams in rapid response to shifting business requirements.</span></span>

<span data-ttu-id="c7d70-120">下圖顯示在 PBX 背後部署 Enterprise Voice 的一般拓撲。</span><span class="sxs-lookup"><span data-stu-id="c7d70-120">The following figure shows the generic topology for deployment of Enterprise Voice behind a PBX.</span></span> <span data-ttu-id="c7d70-121">這是增量部署的建議拓撲。</span><span class="sxs-lookup"><span data-stu-id="c7d70-121">This is the recommended topology for incremental deployment.</span></span>

<span data-ttu-id="c7d70-122">**漸進式部署選項**</span><span class="sxs-lookup"><span data-stu-id="c7d70-122">**Incremental deployment option**</span></span>

<span data-ttu-id="c7d70-123">![部門遷移選項圖表](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "部門遷移選項圖表")</span><span class="sxs-lookup"><span data-stu-id="c7d70-123">![Departmental Migration Option diagram](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Departmental Migration Option diagram")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c7d70-124">如果您要將 Lync Server 部署連接至認可的 Direct SIP 夥伴，則不需要在轉送伺服器和 PBX 之間 (PSTN) 閘道。</span><span class="sxs-lookup"><span data-stu-id="c7d70-124">If you are connecting your Lync Server deployment to a certified Direct SIP partner, a public switched telephone network (PSTN) gateway between the Mediation Server and the PBX is not required.</span></span> <span data-ttu-id="c7d70-125">如需認證直接 SIP 合作夥伴的清單，請參閱 Microsoft 整合通訊開啟互通性計畫網站，網址為 <A href="https://go.microsoft.com/fwlink/p/?linkid=203309">https://go.microsoft.com/fwlink/p/?linkId=203309</A> 。</span><span class="sxs-lookup"><span data-stu-id="c7d70-125">For a list of certified Direct SIP partners, see the Microsoft Unified Communications Open Interoperability Program website at <A href="https://go.microsoft.com/fwlink/p/?linkid=203309">https://go.microsoft.com/fwlink/p/?linkId=203309</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="c7d70-126">在此圖中所示的媒體路徑已啟用媒體旁路 (建議的設定) 。</span><span class="sxs-lookup"><span data-stu-id="c7d70-126">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="c7d70-127">如果您選用停用媒體旁路，媒體路徑會透過轉送伺服器進行路由傳送。</span><span class="sxs-lookup"><span data-stu-id="c7d70-127">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

<span data-ttu-id="c7d70-128">在此拓撲中，會為企業語音啟用選取的部門或工作組。</span><span class="sxs-lookup"><span data-stu-id="c7d70-128">In this topology, selected departments or workgroups are enabled for Enterprise Voice.</span></span> <span data-ttu-id="c7d70-129">PSTN 閘道會將 Voice over Internet Protocol (VoIP 已啟用) 的 workgroup 連結至 PBX。</span><span class="sxs-lookup"><span data-stu-id="c7d70-129">A PSTN gateway links the Voice over Internet Protocol (VoIP)-enabled workgroup to the PBX.</span></span> <span data-ttu-id="c7d70-130">已啟用 Enterprise Voice （包括遠端工作者）的使用者在 IP 網路之間進行通訊。</span><span class="sxs-lookup"><span data-stu-id="c7d70-130">Users who are enabled for Enterprise Voice, including remote workers, communicate across the IP network.</span></span> <span data-ttu-id="c7d70-131">由 Enterprise Voice 使用者對 PSTN 及未啟用 Enterprise Voice 的同事進行呼叫會路由傳送至適當的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="c7d70-131">Calls by Enterprise Voice users to the PSTN and to coworkers who are not enabled for Enterprise Voice are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="c7d70-132">來自位於 PBX 系統或 PSTN 之來電者的同事的來電會路由傳送至 PSTN 閘道，而該閘道會將通話轉送至 Lync 伺服器進行路由傳送。</span><span class="sxs-lookup"><span data-stu-id="c7d70-132">Calls from colleagues who are still on the PBX system, or from callers on the PSTN, are routed to the PSTN gateway, which forwards the calls to Lync Server for routing.</span></span>

<span data-ttu-id="c7d70-133">有兩個建議設定，可將 Enterprise Voice 連接至現有的 PBX 基礎結構，以進行互通性：在 PBX 前端和 Enterprise Voice 之後的 Enterprise voice。</span><span class="sxs-lookup"><span data-stu-id="c7d70-133">There are two recommended configurations for connecting Enterprise Voice to an existing PBX infrastructure for interoperability: Enterprise Voice behind the PBX and Enterprise Voice in front of the PBX.</span></span>

<div>

## <a name="enterprise-voice-behind-the-pbx"></a><span data-ttu-id="c7d70-134">PBX 背後的 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="c7d70-134">Enterprise Voice Behind the PBX</span></span>

<span data-ttu-id="c7d70-135">當 Enterprise Voice 部署在 PBX 背後時，所有來自 PSTN 的呼叫都會到達 PBX，這會將呼叫傳送至 Enterprise Voice 使用者到 PSTN 閘道，並呼叫 PBX 使用者至 PBX。</span><span class="sxs-lookup"><span data-stu-id="c7d70-135">When Enterprise Voice is deployed behind the PBX, all calls from the PSTN arrive at the PBX, which routes calls to Enterprise Voice users to a PSTN gateway, and calls to PBX users to the PBX.</span></span>

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a><span data-ttu-id="c7d70-136">PBX 前端的 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="c7d70-136">Enterprise Voice in Front of the PBX</span></span>

<span data-ttu-id="c7d70-137">當 Enterprise Voice 部署在 PBX 的前方時，所有呼叫都會到達 PSTN 閘道，這會將 Enterprise Voice 使用者的通話路由傳送至 Lync Server，並將 PBX 使用者叫用至 PBX。</span><span class="sxs-lookup"><span data-stu-id="c7d70-137">When Enterprise Voice is deployed in front of the PBX, all calls arrive at the PSTN gateway, which routes calls for Enterprise Voice users to Lync Server and calls for PBX users to the PBX.</span></span> <span data-ttu-id="c7d70-138">從 Enterprise Voice 和 PBX 使用者呼叫 PSTN 會透過 IP 網路路由傳送至最具成本效益的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="c7d70-138">Calls to the PSTN from both Enterprise Voice and PBX users are routed over the IP network to the most cost-efficient PSTN gateway.</span></span> <span data-ttu-id="c7d70-139">下表顯示此設定的優點和缺點。</span><span class="sxs-lookup"><span data-stu-id="c7d70-139">The following table shows the advantages and disadvantages of this configuration.</span></span>

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a><span data-ttu-id="c7d70-140">在 PBX 前面部署企業語音的優缺點</span><span class="sxs-lookup"><span data-stu-id="c7d70-140">Advantages and Disadvantages of Deploying Enterprise Voice in Front of PBX</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7d70-141">優點</span><span class="sxs-lookup"><span data-stu-id="c7d70-141">Advantages</span></span></th>
<th><span data-ttu-id="c7d70-142">缺點</span><span class="sxs-lookup"><span data-stu-id="c7d70-142">Disadvantages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7d70-143">PBX 仍可為未啟用 Enterprise Voice 的使用者提供服務。</span><span class="sxs-lookup"><span data-stu-id="c7d70-143">PBX still serves users not enabled for Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="c7d70-144">現有的閘道可能不支援您想要的功能或容量。</span><span class="sxs-lookup"><span data-stu-id="c7d70-144">Existing gateways may not support the features or capacity that you want.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7d70-145">PBX 處理所有舊版裝置。</span><span class="sxs-lookup"><span data-stu-id="c7d70-145">PBX handles all earlier devices.</span></span></p></td>
<td><p><span data-ttu-id="c7d70-146">需要從閘道到 PBX 的主幹，以及從閘道到轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="c7d70-146">Requires a trunk from gateway to the PBX and from the gateway to the Mediation Server.</span></span> <span data-ttu-id="c7d70-147">您可能需要從服務提供者獲得更多主幹。</span><span class="sxs-lookup"><span data-stu-id="c7d70-147">You may need more trunks from the service provider.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7d70-148">Enterprise Voice 使用者保留相同的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="c7d70-148">Enterprise Voice users keep the same phone numbers.</span></span></p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a><span data-ttu-id="c7d70-149">Lync Server VoIP-Only 部署</span><span class="sxs-lookup"><span data-stu-id="c7d70-149">Lync Server VoIP-Only Deployment</span></span>

<span data-ttu-id="c7d70-150">Enterprise Voice 可提供新的企業，以及現有公司的新 office 網站，並有機會實施功能齊全的 VoIP 解決方案，而不需要擔心 PBX 整合或產生 IP-PBX 基礎結構的實際部署及維護成本。</span><span class="sxs-lookup"><span data-stu-id="c7d70-150">Enterprise Voice provides new businesses, and also new office sites for existing businesses, with the opportunity to implement a full-featured VoIP solution without having to worry about PBX integration or incurring the substantial deployment and maintenance costs of an IP-PBX infrastructure.</span></span> <span data-ttu-id="c7d70-151">此解決方案同時支援現場和遠端工作者。</span><span class="sxs-lookup"><span data-stu-id="c7d70-151">This solution supports both on-site and remote workers.</span></span>

<span data-ttu-id="c7d70-152">在此部署中，所有呼叫都會透過 IP 網路路由傳送。</span><span class="sxs-lookup"><span data-stu-id="c7d70-152">In this deployment, all calls are routed over the IP network.</span></span> <span data-ttu-id="c7d70-153">PSTN 的來電會路由傳送至適當的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="c7d70-153">Calls to the PSTN are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="c7d70-154">Lync 2013 或 Lync Phone Edition 是做為 softphone 的服務。</span><span class="sxs-lookup"><span data-stu-id="c7d70-154">Lync 2013 or Lync Phone Edition serves as a softphone.</span></span> <span data-ttu-id="c7d70-155">因為沒有 PBX 電話供使用者控制，所以遠端呼叫控制無法使用且不需要。</span><span class="sxs-lookup"><span data-stu-id="c7d70-155">Remote call control is unavailable and unnecessary because there are no PBX phones for users to control.</span></span> <span data-ttu-id="c7d70-156">語音信箱和自動語音應答服務可透過選用 Exchange 整合通訊 (UM) 進行部署。</span><span class="sxs-lookup"><span data-stu-id="c7d70-156">Voice mail and auto-attendant services are available through the optional deployment of Exchange Unified Messaging (UM).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c7d70-157">除了支援 Lync Server 2013 所需的網路結構之外，僅 VoIP 部署也可以使用小型的合格閘道來支援傳真機器和類比裝置。</span><span class="sxs-lookup"><span data-stu-id="c7d70-157">In addition to the network infrastructure that is required to support Lync Server 2013, a VoIP-only deployment can use a small, qualified gateway to support fax machines and analog devices.</span></span>



</div>

<span data-ttu-id="c7d70-158">下圖顯示僅限 VoIP 部署的一般拓撲。</span><span class="sxs-lookup"><span data-stu-id="c7d70-158">The following figure shows a typical topology for a VoIP-only deployment.</span></span>

<span data-ttu-id="c7d70-159">**僅限 VoIP 部署選項**</span><span class="sxs-lookup"><span data-stu-id="c7d70-159">**VoIP-only deployment option**</span></span>

<span data-ttu-id="c7d70-160">![Greenfidle 部署選項](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle 部署選項")</span><span class="sxs-lookup"><span data-stu-id="c7d70-160">![Greenfidle deployment option](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle deployment option")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c7d70-161">在此圖中所示的媒體路徑已啟用媒體旁路 (建議的設定) 。</span><span class="sxs-lookup"><span data-stu-id="c7d70-161">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="c7d70-162">如果您選用停用媒體旁路，媒體路徑會透過轉送伺服器進行路由傳送。</span><span class="sxs-lookup"><span data-stu-id="c7d70-162">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

