---
title: 'Lync Server 2013: Direct SIP 部署選項'
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
ms.openlocfilehash: b4bbacbbb6f1a420e989f4bed02ba2fc0db6f85f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036623"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="direct-sip-deployment-options-in-lync-server-2013"></a><span data-ttu-id="2136d-102">Lync Server 2013 中的直接 SIP 部署選項</span><span class="sxs-lookup"><span data-stu-id="2136d-102">Direct SIP deployment options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2136d-103">_**主題上次修改日期：** 2012年-09-21_</span><span class="sxs-lookup"><span data-stu-id="2136d-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="2136d-104">本主題提供範例拓樸部署的直接 SIP 連線。</span><span class="sxs-lookup"><span data-stu-id="2136d-104">This topic provides example topologies for deploying direct SIP connections.</span></span>

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a><span data-ttu-id="2136d-105">Lync Server 獨立</span><span class="sxs-lookup"><span data-stu-id="2136d-105">Lync Server Stand-Alone</span></span>

<span data-ttu-id="2136d-106">如果您的組織會使用其中一個這一節所述的部署，您可以使用唯一的電話語音解決方案 Lync Server 2013 的部分或全部的組織。</span><span class="sxs-lookup"><span data-stu-id="2136d-106">If your organization uses one of the deployments described in this section, you can use Lync Server 2013 as the sole telephony solution for part or all of an organization.</span></span> <span data-ttu-id="2136d-107">本節說明在詳細資料中的下列部署：</span><span class="sxs-lookup"><span data-stu-id="2136d-107">This section describes the following deployments in detail:</span></span>

  - <span data-ttu-id="2136d-108">**漸進式部署：** 此選項假設您有現有的專用交換機 (pbx) 基礎結構，且您想要以較小的群組或組織內的團隊逐漸引進 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="2136d-108">**Incremental deployment:** This option assumes that you have an existing private branch exchange (PBX) infrastructure and you intend to introduce Enterprise Voice incrementally to smaller groups or teams within your organization.</span></span>

  - <span data-ttu-id="2136d-109">**Lync Server 僅限 VoIP 部署：** 此選項假設您考慮部署 Enterprise Voice 在沒有傳統電話語音基礎結構的網站。</span><span class="sxs-lookup"><span data-stu-id="2136d-109">**Lync Server VoIP-only deployment:** this option assumes that you are considering deploying Enterprise Voice at a site that does not have a traditional telephony infrastructure.</span></span>

<div>

## <a name="incremental-deployment"></a><span data-ttu-id="2136d-110">漸進式部署</span><span class="sxs-lookup"><span data-stu-id="2136d-110">Incremental Deployment</span></span>

<span data-ttu-id="2136d-111">在漸進式部署 Lync Server 2013 是唯一的電話語音解決方案的個別小組或部門，同時的其餘部分組織中的使用者繼續使用 PBX。</span><span class="sxs-lookup"><span data-stu-id="2136d-111">In incremental deployment, Lync Server 2013 is the sole telephony solution for individual teams or departments, while the rest of the users in an organization continue to use a PBX.</span></span> <span data-ttu-id="2136d-112">這個漸進式部署策略提供 IP 電話語音引入受控制的試驗程式透過企業的一種方法。</span><span class="sxs-lookup"><span data-stu-id="2136d-112">This incremental deployment strategy provides one way to introduce IP telephony into your enterprise through controlled pilot programs.</span></span> <span data-ttu-id="2136d-113">其通訊需求最佳由 Microsoft 整合通訊的工作群組移至 Enterprise Voice 時保持在現有的 PBX 上的其他使用者。</span><span class="sxs-lookup"><span data-stu-id="2136d-113">Workgroups whose communication needs are best served by Microsoft Unified Communications are moved to Enterprise Voice, while other users remain on the existing PBX.</span></span> <span data-ttu-id="2136d-114">視需要額外的工作群組可移轉至 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="2136d-114">Additional workgroups can be migrated to Enterprise Voice, as needed.</span></span>

<span data-ttu-id="2136d-115">[增量] 選項如果，建議您清楚地定義使用者群組，已在通用和，通訊需求擔任集中管理。</span><span class="sxs-lookup"><span data-stu-id="2136d-115">The incremental option is recommended if you have clearly defined user groups that have communication requirements in common and that lend themselves to centralized management.</span></span> <span data-ttu-id="2136d-116">此選項也是如果您有小組或部門的改變會展現透過寬的地理區域，可大幅節省的長途電話有效的。</span><span class="sxs-lookup"><span data-stu-id="2136d-116">This option is also effective if you have teams or departments that are spread over wide geographic areas, where the savings in long-distance charges can be significant.</span></span> <span data-ttu-id="2136d-117">事實上，這個選項適合用來建立其成員可能可能分佈在全球的虛擬小組。</span><span class="sxs-lookup"><span data-stu-id="2136d-117">In fact, this option is useful for creating virtual teams whose members may be scattered across the globe.</span></span> <span data-ttu-id="2136d-118">您可以建立、 修改或 disband 這類 teams 快速回應移位業務需求。</span><span class="sxs-lookup"><span data-stu-id="2136d-118">You can create, modify, or disband such teams in rapid response to shifting business requirements.</span></span>

<span data-ttu-id="2136d-119">下圖顯示部署企業語音 PBX 後方的一般拓撲。</span><span class="sxs-lookup"><span data-stu-id="2136d-119">The following figure shows the generic topology for deployment of Enterprise Voice behind a PBX.</span></span> <span data-ttu-id="2136d-120">這是漸進式部署的建議的拓撲。</span><span class="sxs-lookup"><span data-stu-id="2136d-120">This is the recommended topology for incremental deployment.</span></span>

<span data-ttu-id="2136d-121">**漸進式部署選項**</span><span class="sxs-lookup"><span data-stu-id="2136d-121">**Incremental deployment option**</span></span>

<span data-ttu-id="2136d-122">![部門的移轉選項圖表](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "部門的移轉選項圖表")</span><span class="sxs-lookup"><span data-stu-id="2136d-122">![Departmental Migration Option diagram](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Departmental Migration Option diagram")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2136d-123">如果您連線您的 Lync Server 部署到認證的直接 SIP 合作夥伴，就不需要中繼伺服器和 PBX 間的公用交換的電話網路 (PSTN) 閘道。</span><span class="sxs-lookup"><span data-stu-id="2136d-123">If you are connecting your Lync Server deployment to a certified Direct SIP partner, a public switched telephone network (PSTN) gateway between the Mediation Server and the PBX is not required.</span></span> <span data-ttu-id="2136d-124">認證直接 SIP 協力廠商的清單，請參閱 Microsoft Unified Communications Open Interoperability Program 網站， <A href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</A>。</span><span class="sxs-lookup"><span data-stu-id="2136d-124">For a list of certified Direct SIP partners, see the Microsoft Unified Communications Open Interoperability Program website at <A href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="2136d-125">此圖所示的媒體路徑有媒體旁路啟用 （建議的組態）。</span><span class="sxs-lookup"><span data-stu-id="2136d-125">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="2136d-126">如果您選擇停用媒體旁路，媒體路徑會透過中繼伺服器路由傳送。</span><span class="sxs-lookup"><span data-stu-id="2136d-126">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

<span data-ttu-id="2136d-127">在此拓撲中，選取的部門或工作群組已啟用 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="2136d-127">In this topology, selected departments or workgroups are enabled for Enterprise Voice.</span></span> <span data-ttu-id="2136d-128">PSTN 閘道連結 Voice over Internet Protocol (VoIP)-啟用工作群組]，將 PBX。</span><span class="sxs-lookup"><span data-stu-id="2136d-128">A PSTN gateway links the Voice over Internet Protocol (VoIP)-enabled workgroup to the PBX.</span></span> <span data-ttu-id="2136d-129">已啟用 Enterprise voice，包括遠端工作者，使用者透過 IP 網路通訊。</span><span class="sxs-lookup"><span data-stu-id="2136d-129">Users who are enabled for Enterprise Voice, including remote workers, communicate across the IP network.</span></span> <span data-ttu-id="2136d-130">Enterprise Voice 使用者的來電至 PSTN 和同事未啟用 Enterprise voice 會路由到適當的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="2136d-130">Calls by Enterprise Voice users to the PSTN and to coworkers who are not enabled for Enterprise Voice are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="2136d-131">通話仍在 PBX 系統、 同事或來自 pstn，來電者會路由傳送至 PSTN 閘道，會進行路由轉送至 Lync 伺服器的呼叫。</span><span class="sxs-lookup"><span data-stu-id="2136d-131">Calls from colleagues who are still on the PBX system, or from callers on the PSTN, are routed to the PSTN gateway, which forwards the calls to Lync Server for routing.</span></span>

<span data-ttu-id="2136d-132">有兩種建議的設定，以連線至現有的 PBX 基礎結構的互通性的企業語音： Enterprise Voice 在 PBX 前方的 Enterprise Voice 與 PBX 後方。</span><span class="sxs-lookup"><span data-stu-id="2136d-132">There are two recommended configurations for connecting Enterprise Voice to an existing PBX infrastructure for interoperability: Enterprise Voice behind the PBX and Enterprise Voice in front of the PBX.</span></span>

<div>

## <a name="enterprise-voice-behind-the-pbx"></a><span data-ttu-id="2136d-133">Enterprise Voice 在 PBX 後方</span><span class="sxs-lookup"><span data-stu-id="2136d-133">Enterprise Voice Behind the PBX</span></span>

<span data-ttu-id="2136d-134">Enterprise Voice 在 PBX 後方部署時，所有來自 PSTN 的通話都會送達 PBX，將企業語音使用者的通話路由傳送至 PSTN 閘道，並呼叫將 PBX 使用者至 PBX。</span><span class="sxs-lookup"><span data-stu-id="2136d-134">When Enterprise Voice is deployed behind the PBX, all calls from the PSTN arrive at the PBX, which routes calls to Enterprise Voice users to a PSTN gateway, and calls to PBX users to the PBX.</span></span>

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a><span data-ttu-id="2136d-135">Enterprise Voice 在 PBX 前方</span><span class="sxs-lookup"><span data-stu-id="2136d-135">Enterprise Voice in Front of the PBX</span></span>

<span data-ttu-id="2136d-136">Enterprise Voice 在 PBX 前方部署時，所有通話都會都送達 PSTN 閘道，哪些路由呼叫 Enterprise Voice 使用者 Lync 伺服器和 PBX 的 PBX 使用者的呼叫。</span><span class="sxs-lookup"><span data-stu-id="2136d-136">When Enterprise Voice is deployed in front of the PBX, all calls arrive at the PSTN gateway, which routes calls for Enterprise Voice users to Lync Server and calls for PBX users to the PBX.</span></span> <span data-ttu-id="2136d-137">透過 IP 網路的成本最有效率的 PSTN 閘道路由傳送至 PSTN 的企業語音與 PBX 使用者的來電。</span><span class="sxs-lookup"><span data-stu-id="2136d-137">Calls to the PSTN from both Enterprise Voice and PBX users are routed over the IP network to the most cost-efficient PSTN gateway.</span></span> <span data-ttu-id="2136d-138">下表顯示這個設定的優缺點。</span><span class="sxs-lookup"><span data-stu-id="2136d-138">The following table shows the advantages and disadvantages of this configuration.</span></span>

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a><span data-ttu-id="2136d-139">部署 Enterprise Voice 在 PBX 前方的優點和缺點</span><span class="sxs-lookup"><span data-stu-id="2136d-139">Advantages and Disadvantages of Deploying Enterprise Voice in Front of PBX</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2136d-140">優點</span><span class="sxs-lookup"><span data-stu-id="2136d-140">Advantages</span></span></th>
<th><span data-ttu-id="2136d-141">缺點</span><span class="sxs-lookup"><span data-stu-id="2136d-141">Disadvantages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2136d-142">PBX 仍然會服務未啟用 Enterprise Voice 的使用者。</span><span class="sxs-lookup"><span data-stu-id="2136d-142">PBX still serves users not enabled for Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="2136d-143">現有的閘道可能不支援的功能或您想要的容量。</span><span class="sxs-lookup"><span data-stu-id="2136d-143">Existing gateways may not support the features or capacity that you want.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2136d-144">PBX 可處理所有舊版的裝置。</span><span class="sxs-lookup"><span data-stu-id="2136d-144">PBX handles all earlier devices.</span></span></p></td>
<td><p><span data-ttu-id="2136d-145">需要閘道與 PBX 從和到中繼伺服器閘道在主幹。</span><span class="sxs-lookup"><span data-stu-id="2136d-145">Requires a trunk from gateway to the PBX and from the gateway to the Mediation Server.</span></span> <span data-ttu-id="2136d-146">您可能需要從服務提供者的多個主幹。</span><span class="sxs-lookup"><span data-stu-id="2136d-146">You may need more trunks from the service provider.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2136d-147">Enterprise Voice 使用者可保留相同的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="2136d-147">Enterprise Voice users keep the same phone numbers.</span></span></p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a><span data-ttu-id="2136d-148">Lync Server 僅限 VoIP 部署</span><span class="sxs-lookup"><span data-stu-id="2136d-148">Lync Server VoIP-Only Deployment</span></span>

<span data-ttu-id="2136d-149">Enterprise Voice 提供新的企業，以及新的 office 網站的現有的公司，而不必擔心 PBX 整合或產生大量的部署及維護實作的功能完整的 VoIP 解決方案IP PBX 基礎結構成本。</span><span class="sxs-lookup"><span data-stu-id="2136d-149">Enterprise Voice provides new businesses, and also new office sites for existing businesses, with the opportunity to implement a full-featured VoIP solution without having to worry about PBX integration or incurring the substantial deployment and maintenance costs of an IP-PBX infrastructure.</span></span> <span data-ttu-id="2136d-150">此解決方案支援同時對現場與遠端工作者。</span><span class="sxs-lookup"><span data-stu-id="2136d-150">This solution supports both on-site and remote workers.</span></span>

<span data-ttu-id="2136d-151">在此部署中，所有的來電會透過 IP 網路路由傳送。</span><span class="sxs-lookup"><span data-stu-id="2136d-151">In this deployment, all calls are routed over the IP network.</span></span> <span data-ttu-id="2136d-152">PSTN 來電會路由到適當的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="2136d-152">Calls to the PSTN are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="2136d-153">Lync 2013 或 Lync Phone Edition 做為 softphone。</span><span class="sxs-lookup"><span data-stu-id="2136d-153">Lync 2013 or Lync Phone Edition serves as a softphone.</span></span> <span data-ttu-id="2136d-154">遠端呼叫控制是無法使用，並且不必要的因為有使用者控制項沒有 PBX 電話。</span><span class="sxs-lookup"><span data-stu-id="2136d-154">Remote call control is unavailable and unnecessary because there are no PBX phones for users to control.</span></span> <span data-ttu-id="2136d-155">語音信箱和自動語音應答服務可透過指定部署的 Exchange 整合通訊 (UM)。</span><span class="sxs-lookup"><span data-stu-id="2136d-155">Voice mail and auto-attendant services are available through the optional deployment of Exchange Unified Messaging (UM).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2136d-156">除了支援 Lync Server 2013 所需的網路基礎結構，僅限 VoIP 部署可以使用小型的合格閘道來支援傳真機和類比裝置。</span><span class="sxs-lookup"><span data-stu-id="2136d-156">In addition to the network infrastructure that is required to support Lync Server 2013, a VoIP-only deployment can use a small, qualified gateway to support fax machines and analog devices.</span></span>



</div>

<span data-ttu-id="2136d-157">下圖顯示在僅限 VoIP 部署的一般拓撲。</span><span class="sxs-lookup"><span data-stu-id="2136d-157">The following figure shows a typical topology for a VoIP-only deployment.</span></span>

<span data-ttu-id="2136d-158">**僅限 VoIP 部署選項**</span><span class="sxs-lookup"><span data-stu-id="2136d-158">**VoIP-only deployment option**</span></span>

<span data-ttu-id="2136d-159">![Greenfidle 部署選項](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle 部署選項")</span><span class="sxs-lookup"><span data-stu-id="2136d-159">![Greenfidle deployment option](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle deployment option")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2136d-160">此圖所示的媒體路徑有媒體旁路啟用 （建議的組態）。</span><span class="sxs-lookup"><span data-stu-id="2136d-160">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="2136d-161">如果您選擇停用媒體旁路，媒體路徑會透過中繼伺服器路由傳送。</span><span class="sxs-lookup"><span data-stu-id="2136d-161">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

