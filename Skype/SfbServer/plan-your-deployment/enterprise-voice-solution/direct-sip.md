---
title: 在商務用 Skype Server 中的直接 SIP 連線
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0a37737d-9628-4e36-b27b-c134fa5a3882
description: 商務用 Skype Server 和兩部 PSTN 閘道和 Enterprise Voice IP-PBX 都支援直接 SIP 連線。
ms.openlocfilehash: 7a70a6f3afd303ef5847993240b26b47d1b4ceac
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096413"
---
# <a name="direct-sip-connections-in-skype-for-business-server"></a><span data-ttu-id="f3297-103">在商務用 Skype Server 中的直接 SIP 連線</span><span class="sxs-lookup"><span data-stu-id="f3297-103">Direct SIP connections in Skype for Business Server</span></span>

<span data-ttu-id="f3297-104">商務用 Skype Server 和兩部 PSTN 閘道和 Enterprise Voice IP-PBX 都支援直接 SIP 連線。</span><span class="sxs-lookup"><span data-stu-id="f3297-104">Direct SIP connections are supported between Skype for Business Server and both PSTN gateways and IP-PBX in Enterprise Voice.</span></span>

<span data-ttu-id="f3297-105">您可以使用直接 SIP 連線，將商務用 Skype 伺服器連線至下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="f3297-105">You can use direct SIP connections to connect Skype for Business Server to either of the following:</span></span>

- <span data-ttu-id="f3297-106">IP-PBX</span><span class="sxs-lookup"><span data-stu-id="f3297-106">An IP-PBX</span></span>

- <span data-ttu-id="f3297-107">PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="f3297-107">A PSTN gateway</span></span>

<span data-ttu-id="f3297-108">若要實作直接 SIP 連線，基本上遵循您用於實作 SIP 主幹的相同部署步驟。</span><span class="sxs-lookup"><span data-stu-id="f3297-108">To implement a direct SIP connection, you follow essentially the same deployment steps as you would to implement a SIP trunk.</span></span> <span data-ttu-id="f3297-109">在這兩種情況下，您可以使用轉送伺服器的外部介面來執行連線。</span><span class="sxs-lookup"><span data-stu-id="f3297-109">In both cases, you implement the connection by using the external interface of a Mediation Server.</span></span> <span data-ttu-id="f3297-110">唯一的差異在於您將 SIP 主幹連線至外部實體 (如 ITSP 閘道)，而將直接 SIP 連線連接至區域網路中的內部實體 (如 IP-PBX 或公用交換電話網路 (PSTN) 閘道)。</span><span class="sxs-lookup"><span data-stu-id="f3297-110">The only difference is that you connect SIP trunks to an external entity, such as an ITSP gateway, and you connect direct SIP connections to an internal entity within your local network, such as an IP-PBX or a public switched telephone network (PSTN) gateway.</span></span>

## <a name="direct-sip-deployment-options"></a><span data-ttu-id="f3297-111">直接 SIP 部署選項</span><span class="sxs-lookup"><span data-stu-id="f3297-111">Direct SIP deployment options</span></span>

### <a name="skype-for-business-server-stand-alone"></a><span data-ttu-id="f3297-112">商務用 Skype Server Stand-Alone</span><span class="sxs-lookup"><span data-stu-id="f3297-112">Skype for Business Server Stand-Alone</span></span>
<span data-ttu-id="f3297-113"><a name="BKMK_CommunicationsServerStand-Alone"> </a></span><span class="sxs-lookup"><span data-stu-id="f3297-113"><a name="BKMK_CommunicationsServerStand-Alone"> </a></span></span>

<span data-ttu-id="f3297-114">如果您的組織使用本節所述的其中一個部署，您可以使用商務用 Skype 伺服器做為組織的一部分或所有組織的唯一電話語音解決方案。</span><span class="sxs-lookup"><span data-stu-id="f3297-114">If your organization uses one of the deployments described in this section, you can use Skype for Business Server as the sole telephony solution for part or all of an organization.</span></span> <span data-ttu-id="f3297-115">本節詳細說明下列部署：</span><span class="sxs-lookup"><span data-stu-id="f3297-115">This section describes the following deployments in detail:</span></span>

- <span data-ttu-id="f3297-116">**漸進式部署：** 此選項假設您有現有的私人分公司 exchange (PBX) 基礎結構，而您想要將 Enterprise Voice 逐步引入組織中較小的群組或小組。</span><span class="sxs-lookup"><span data-stu-id="f3297-116">**Incremental deployment:** This option assumes that you have an existing private branch exchange (PBX) infrastructure and you intend to introduce Enterprise Voice incrementally to smaller groups or teams within your organization.</span></span>

- <span data-ttu-id="f3297-117">**僅限 VoIP 部署：** 此選項假設您考慮在沒有傳統電話語音基礎結構的網站上部署 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="f3297-117">**VoIP-only deployment:** this option assumes that you are considering deploying Enterprise Voice at a site that does not have a traditional telephony infrastructure.</span></span>

#### <a name="incremental-deployment"></a><span data-ttu-id="f3297-118">漸進式部署</span><span class="sxs-lookup"><span data-stu-id="f3297-118">Incremental Deployment</span></span>

<span data-ttu-id="f3297-119">在漸進式部署中，商務用 Skype 伺服器是個別小組或部門的唯一電話語音解決方案，而組織中的其他使用者仍會繼續使用 PBX。</span><span class="sxs-lookup"><span data-stu-id="f3297-119">In incremental deployment, Skype for Business Server is the sole telephony solution for individual teams or departments, while the rest of the users in an organization continue to use a PBX.</span></span> <span data-ttu-id="f3297-120">這項增量部署策略提供一種方法，透過控制的試驗計畫，將 IP 電話語音引入您的企業。</span><span class="sxs-lookup"><span data-stu-id="f3297-120">This incremental deployment strategy provides one way to introduce IP telephony into your enterprise through controlled pilot programs.</span></span> <span data-ttu-id="f3297-121">Microsoft 整合通訊最適合使用其通訊的工作組會移至 Enterprise Voice，其他使用者仍會保留在現有的 PBX 上。</span><span class="sxs-lookup"><span data-stu-id="f3297-121">Workgroups whose communication needs are best served by Microsoft Unified Communications are moved to Enterprise Voice, while other users remain on the existing PBX.</span></span> <span data-ttu-id="f3297-122">其他的工作組可以視需要遷移至 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="f3297-122">Additional workgroups can be migrated to Enterprise Voice, as needed.</span></span>

<span data-ttu-id="f3297-123">如果您明確定義的使用者群組具有共同的通訊需求，且其本身適用于集中式管理，則建議使用 [累加] 選項。</span><span class="sxs-lookup"><span data-stu-id="f3297-123">The incremental option is recommended if you have clearly defined user groups that have communication requirements in common and that lend themselves to centralized management.</span></span> <span data-ttu-id="f3297-124">如果您擁有遍佈地理區域的團隊或部門，而且在長途計費中的節約成本可能很大，此選項也會有效。</span><span class="sxs-lookup"><span data-stu-id="f3297-124">This option is also effective if you have teams or departments that are spread over wide geographic areas, where the savings in long-distance charges can be significant.</span></span> <span data-ttu-id="f3297-125">實際上，此選項對於建立其成員可能分散在全球的虛擬小組非常有用。</span><span class="sxs-lookup"><span data-stu-id="f3297-125">In fact, this option is useful for creating virtual teams whose members may be scattered across the globe.</span></span> <span data-ttu-id="f3297-126">您可以建立、修改或 disband 這類團隊，以快速回應轉向的業務需求。</span><span class="sxs-lookup"><span data-stu-id="f3297-126">You can create, modify, or disband such teams in rapid response to shifting business requirements.</span></span>

<span data-ttu-id="f3297-127">下圖顯示在 PBX 背後部署 Enterprise Voice 的一般拓撲。</span><span class="sxs-lookup"><span data-stu-id="f3297-127">The following figure shows the generic topology for deployment of Enterprise Voice behind a PBX.</span></span> <span data-ttu-id="f3297-128">這是增量部署的建議拓撲。</span><span class="sxs-lookup"><span data-stu-id="f3297-128">This is the recommended topology for incremental deployment.</span></span>

<span data-ttu-id="f3297-129">**漸進式部署選項**</span><span class="sxs-lookup"><span data-stu-id="f3297-129">**Incremental deployment option**</span></span>

![部門遷移選項圖表](../../media/Fig28_Departmental_migration_option.jpg)

> [!NOTE]
> <span data-ttu-id="f3297-131">如果您要將商務用 Skype Server 部署連接至認可的 Direct SIP 夥伴，則不需要在轉送伺服器和 PBX 之間使用公用交換電話網路 (PSTN) 閘道。</span><span class="sxs-lookup"><span data-stu-id="f3297-131">If you are connecting your Skype for Business Server deployment to a certified Direct SIP partner, a public switched telephone network (PSTN) gateway between the Mediation Server and the PBX is not required.</span></span> <span data-ttu-id="f3297-132">如需認證直接 SIP 夥伴的清單，請參閱  [Microsoft 整合通訊開啟互通性計畫](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)。</span><span class="sxs-lookup"><span data-stu-id="f3297-132">For a list of certified Direct SIP partners, see the  [Microsoft Unified Communications Open Interoperability Program](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f3297-133">在此圖中所示的媒體路徑已啟用媒體旁路 (建議的設定) 。</span><span class="sxs-lookup"><span data-stu-id="f3297-133">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="f3297-134">如果您選用停用媒體旁路，媒體路徑會透過轉送伺服器進行路由傳送。</span><span class="sxs-lookup"><span data-stu-id="f3297-134">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>

<span data-ttu-id="f3297-135">在此拓撲中，會為企業語音啟用選取的部門或工作組。</span><span class="sxs-lookup"><span data-stu-id="f3297-135">In this topology, selected departments or workgroups are enabled for Enterprise Voice.</span></span> <span data-ttu-id="f3297-136">PSTN 閘道會將 Voice over Internet Protocol (VoIP 已啟用) 的 workgroup 連結至 PBX。</span><span class="sxs-lookup"><span data-stu-id="f3297-136">A PSTN gateway links the Voice over Internet Protocol (VoIP)-enabled workgroup to the PBX.</span></span> <span data-ttu-id="f3297-137">已啟用 Enterprise Voice （包括遠端工作者）的使用者在 IP 網路之間進行通訊。</span><span class="sxs-lookup"><span data-stu-id="f3297-137">Users who are enabled for Enterprise Voice, including remote workers, communicate across the IP network.</span></span> <span data-ttu-id="f3297-138">由 Enterprise Voice 使用者對 PSTN 及未啟用 Enterprise Voice 的同事進行呼叫會路由傳送至適當的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="f3297-138">Calls by Enterprise Voice users to the PSTN and to coworkers who are not enabled for Enterprise Voice are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="f3297-139">來自位於 PBX 系統或 PSTN 之來電者的同事的來電會路由傳送至 PSTN 閘道，而該閘道會將通話轉寄給用於路由傳送的商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="f3297-139">Calls from colleagues who are still on the PBX system, or from callers on the PSTN, are routed to the PSTN gateway, which forwards the calls to Skype for Business Server for routing.</span></span>

<span data-ttu-id="f3297-140">有兩個建議設定，可將 Enterprise Voice 連接至現有的 PBX 基礎結構，以進行互通性：在 PBX 前端和 Enterprise Voice 之後的 Enterprise voice。</span><span class="sxs-lookup"><span data-stu-id="f3297-140">There are two recommended configurations for connecting Enterprise Voice to an existing PBX infrastructure for interoperability: Enterprise Voice behind the PBX and Enterprise Voice in front of the PBX.</span></span>

#### <a name="enterprise-voice-behind-the-pbx"></a><span data-ttu-id="f3297-141">PBX 背後的 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="f3297-141">Enterprise Voice Behind the PBX</span></span>

<span data-ttu-id="f3297-142">當 Enterprise Voice 部署在 PBX 背後時，所有來自 PSTN 的呼叫都會到達 PBX，這會將呼叫傳送至 Enterprise Voice 使用者到 PSTN 閘道，並呼叫 PBX 使用者至 PBX。</span><span class="sxs-lookup"><span data-stu-id="f3297-142">When Enterprise Voice is deployed behind the PBX, all calls from the PSTN arrive at the PBX, which routes calls to Enterprise Voice users to a PSTN gateway, and calls to PBX users to the PBX.</span></span>

#### <a name="enterprise-voice-in-front-of-the-pbx"></a><span data-ttu-id="f3297-143">PBX 前端的 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="f3297-143">Enterprise Voice in Front of the PBX</span></span>

<span data-ttu-id="f3297-144">當 Enterprise Voice 部署在 PBX 的前方時，所有呼叫都會到達 PSTN 閘道，這會將 Enterprise Voice 使用者的通話路由傳送至商務用 Skype Server，並將 PBX 使用者叫用到 PBX。</span><span class="sxs-lookup"><span data-stu-id="f3297-144">When Enterprise Voice is deployed in front of the PBX, all calls arrive at the PSTN gateway, which routes calls for Enterprise Voice users to Skype for Business Server and calls for PBX users to the PBX.</span></span> <span data-ttu-id="f3297-145">從 Enterprise Voice 和 PBX 使用者呼叫 PSTN 會透過 IP 網路路由傳送至最具成本效益的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="f3297-145">Calls to the PSTN from both Enterprise Voice and PBX users are routed over the IP network to the most cost-efficient PSTN gateway.</span></span> <span data-ttu-id="f3297-146">下表顯示此設定的優點和缺點。</span><span class="sxs-lookup"><span data-stu-id="f3297-146">The following table shows the advantages and disadvantages of this configuration.</span></span>

<span data-ttu-id="f3297-147">**在 PBX 前面部署企業語音的優缺點**</span><span class="sxs-lookup"><span data-stu-id="f3297-147">**Advantages and Disadvantages of Deploying Enterprise Voice in Front of PBX**</span></span>

|<span data-ttu-id="f3297-148">**優點**</span><span class="sxs-lookup"><span data-stu-id="f3297-148">**Advantages**</span></span>|<span data-ttu-id="f3297-149">**缺點**</span><span class="sxs-lookup"><span data-stu-id="f3297-149">**Disadvantages**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f3297-150">PBX 仍可為未啟用 Enterprise Voice 的使用者提供服務。</span><span class="sxs-lookup"><span data-stu-id="f3297-150">PBX still serves users not enabled for Enterprise Voice.</span></span>  <br/> |<span data-ttu-id="f3297-151">現有的閘道可能不支援您想要的功能或容量。</span><span class="sxs-lookup"><span data-stu-id="f3297-151">Existing gateways may not support the features or capacity that you want.</span></span>  <br/> |
|<span data-ttu-id="f3297-152">PBX 處理所有舊版裝置。</span><span class="sxs-lookup"><span data-stu-id="f3297-152">PBX handles all earlier devices.</span></span>  <br/> |<span data-ttu-id="f3297-153">需要從閘道到 PBX 的主幹，以及從閘道到轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="f3297-153">Requires a trunk from gateway to the PBX and from the gateway to the Mediation Server.</span></span> <span data-ttu-id="f3297-154">您可能需要從服務提供者獲得更多主幹。</span><span class="sxs-lookup"><span data-stu-id="f3297-154">You may need more trunks from the service provider.</span></span>  <br/> |
|<span data-ttu-id="f3297-155">Enterprise Voice 使用者保留相同的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="f3297-155">Enterprise Voice users keep the same phone numbers.</span></span>  <br/> | <br/> |

#### <a name="voip-only-deployment"></a><span data-ttu-id="f3297-156">VoIP-Only 部署</span><span class="sxs-lookup"><span data-stu-id="f3297-156">VoIP-Only Deployment</span></span>

<span data-ttu-id="f3297-157">Enterprise Voice 可提供新的企業，以及現有公司的新 office 網站，並有機會實施功能齊全的 VoIP 解決方案，而不需要擔心 PBX 整合或產生 IP-PBX 基礎結構的實際部署及維護成本。</span><span class="sxs-lookup"><span data-stu-id="f3297-157">Enterprise Voice provides new businesses, and also new office sites for existing businesses, with the opportunity to implement a full-featured VoIP solution without having to worry about PBX integration or incurring the substantial deployment and maintenance costs of an IP-PBX infrastructure.</span></span> <span data-ttu-id="f3297-158">此解決方案同時支援現場和遠端工作者。</span><span class="sxs-lookup"><span data-stu-id="f3297-158">This solution supports both on-site and remote workers.</span></span>

<span data-ttu-id="f3297-159">在此部署中，所有呼叫都會透過 IP 網路路由傳送。</span><span class="sxs-lookup"><span data-stu-id="f3297-159">In this deployment, all calls are routed over the IP network.</span></span> <span data-ttu-id="f3297-160">PSTN 的來電會路由傳送至適當的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="f3297-160">Calls to the PSTN are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="f3297-161">商務用 Skype 或 Lync Phone Edition 是做為 softphone 的服務。</span><span class="sxs-lookup"><span data-stu-id="f3297-161">Skype for Business or Lync Phone Edition serves as a softphone.</span></span> <span data-ttu-id="f3297-162">因為沒有 PBX 電話供使用者控制，所以遠端呼叫控制無法使用且不需要。</span><span class="sxs-lookup"><span data-stu-id="f3297-162">Remote call control is unavailable and unnecessary because there are no PBX phones for users to control.</span></span> <span data-ttu-id="f3297-163">語音信箱和自動語音應答服務可透過選用 Exchange 整合通訊 (UM) 進行部署。</span><span class="sxs-lookup"><span data-stu-id="f3297-163">Voice mail and auto-attendant services are available through the optional deployment of Exchange Unified Messaging (UM).</span></span>

> [!NOTE]
> <span data-ttu-id="f3297-164">除了支援商務用 Skype Server 所需的網路結構之外，僅 VoIP 部署也可以使用小型的合格閘道來支援傳真機器和類比裝置。</span><span class="sxs-lookup"><span data-stu-id="f3297-164">In addition to the network infrastructure that is required to support Skype for Business Server, a VoIP-only deployment can use a small, qualified gateway to support fax machines and analog devices.</span></span>

<span data-ttu-id="f3297-165">下圖顯示僅限 VoIP 部署的一般拓撲。</span><span class="sxs-lookup"><span data-stu-id="f3297-165">The following figure shows a typical topology for a VoIP-only deployment.</span></span>

<span data-ttu-id="f3297-166">**僅限 VoIP 部署選項**</span><span class="sxs-lookup"><span data-stu-id="f3297-166">**VoIP-only deployment option**</span></span>

![Greenfidle 部署選項](../../media/Fig29_Greenfield_deployment_option.jpg)

> [!NOTE]
> <span data-ttu-id="f3297-168">在此圖中所示的媒體路徑已啟用媒體旁路 (建議的設定) 。</span><span class="sxs-lookup"><span data-stu-id="f3297-168">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="f3297-169">如果您選用停用媒體旁路，媒體路徑會透過轉送伺服器進行路由傳送。</span><span class="sxs-lookup"><span data-stu-id="f3297-169">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>

## <a name="pstn-gateway-deployment-options"></a><span data-ttu-id="f3297-170">PSTN 閘道部署選項</span><span class="sxs-lookup"><span data-stu-id="f3297-170">PSTN Gateway deployment options</span></span>

### <a name="pstn-gateways"></a><span data-ttu-id="f3297-171">PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="f3297-171">PSTN Gateways</span></span>

<span data-ttu-id="f3297-172">公用交換電話網路 (PSTN) 閘道是協力廠商硬體元件，可直接或透過連接至 SIP 主幹，在企業語音基礎結構與 PSTN 之間轉譯信號和媒體。</span><span class="sxs-lookup"><span data-stu-id="f3297-172">Public switched telephone network (PSTN) gateways are third-party hardware components that translate signaling and media between the Enterprise Voice infrastructure and the PSTN, either directly or through connection to SIP trunks.</span></span> <span data-ttu-id="f3297-173">在任一拓撲中，閘道會終止 PSTN。</span><span class="sxs-lookup"><span data-stu-id="f3297-173">In either topology, the gateway terminates the PSTN.</span></span> <span data-ttu-id="f3297-174">閘道會隔離在其自己的子網中，並透過轉送伺服器連線至商業網路。</span><span class="sxs-lookup"><span data-stu-id="f3297-174">The gateway is isolated in its own subnet and is connected to the enterprise network through the Mediation Server.</span></span>

<span data-ttu-id="f3297-175">具有多個網站的企業通常會在每個網站上部署一或多個閘道。</span><span class="sxs-lookup"><span data-stu-id="f3297-175">An enterprise with multiple sites would typically deploy one or more gateways at each site.</span></span> <span data-ttu-id="f3297-176">分支網站可以透過閘道或透過 Survivable 分支裝置連接至 PSTN，此裝置會將閘道和伺服器結合到單一方塊中。</span><span class="sxs-lookup"><span data-stu-id="f3297-176">Branch sites can connect to the PSTN either through a gateway, or through a Survivable Branch Appliance, which combines gateway and servers in a single box.</span></span> <span data-ttu-id="f3297-177">如果分支網站使用閘道，則網站上必須有註冊機構和轉送伺服器，除非 WAN 連結可復原。</span><span class="sxs-lookup"><span data-stu-id="f3297-177">If branch sites use a gateway, both a Registrar and Mediation Server are required on site, unless the WAN link is resilient.</span></span> <span data-ttu-id="f3297-178">在前端伺服器上組合的一或多個轉送伺服器，可在每個網站上路由傳送一或多個閘道的來電。</span><span class="sxs-lookup"><span data-stu-id="f3297-178">One or more Mediation Servers, which are collocated on Front End Servers, can route calls for the one or more gateways at each site.</span></span> <span data-ttu-id="f3297-179">建議將網站上的註冊機構、轉送伺服器和閘道部署為 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="f3297-179">We recommend that the Registrar, Mediation Server, and gateway required on site are deployed as a Survivable Branch Appliance.</span></span>

<span data-ttu-id="f3297-180">決定 PSTN 閘道的數量、大小和位置可能是規劃企業語音基礎結構時必須進行的最重要且昂貴的決策。</span><span class="sxs-lookup"><span data-stu-id="f3297-180">Determining the number, size, and location of PSTN gateways is perhaps the most important and expensive decision you must make when planning your Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="f3297-181">以下是需要考慮的主要問題。</span><span class="sxs-lookup"><span data-stu-id="f3297-181">Here are the main questions to consider.</span></span> <span data-ttu-id="f3297-182">請記住，這些問題的答案都是相互依賴的</span><span class="sxs-lookup"><span data-stu-id="f3297-182">Keep in mind that the answers to these questions are all interdependent</span></span>

- <span data-ttu-id="f3297-183">需要多少 PSTN 閘道？</span><span class="sxs-lookup"><span data-stu-id="f3297-183">How many PSTN gateways are needed?</span></span> <span data-ttu-id="f3297-184">其答案取決於使用者數目、預期同時通話的數目 (流量負載) ，以及每個網站 (的網站數目) 一個。</span><span class="sxs-lookup"><span data-stu-id="f3297-184">The answer depends on the number of users, the anticipated number of simultaneous calls (traffic load), and the number of sites (each site needs one).</span></span>

- <span data-ttu-id="f3297-185">閘道應該是什麼大小？</span><span class="sxs-lookup"><span data-stu-id="f3297-185">What size should the gateways be?</span></span> <span data-ttu-id="f3297-186">其答案取決於網站上的使用者人數及流量負載。</span><span class="sxs-lookup"><span data-stu-id="f3297-186">The answer depends on the number of users at the site and on the traffic load.</span></span>

- <span data-ttu-id="f3297-187">閘道應位於何處？</span><span class="sxs-lookup"><span data-stu-id="f3297-187">Where should the gateways be located?</span></span> <span data-ttu-id="f3297-188">其答案部分取決於拓撲，以及組織地理位置發佈的部分。</span><span class="sxs-lookup"><span data-stu-id="f3297-188">The answer depends in part on the topology and in part on the geographic distribution of your organization.</span></span>

  <span data-ttu-id="f3297-189">您也應該考慮閘道拓撲選項 (如需詳細資訊，請參閱本主題稍後的閘道拓撲) 。</span><span class="sxs-lookup"><span data-stu-id="f3297-189">You should also consider your gateway topology options (for details, see Gateway Topologies later in this topic).</span></span>

#### <a name="mn-trunk-support"></a><span data-ttu-id="f3297-190">M:N 主幹支援</span><span class="sxs-lookup"><span data-stu-id="f3297-190">M:N Trunk Support</span></span>

<span data-ttu-id="f3297-191">轉送伺服器可以透過多個閘道、會話邊界控制器 (SBCs) Internet 電話語音服務提供者所提供的電話，或是二者的組合，進行路由傳送。</span><span class="sxs-lookup"><span data-stu-id="f3297-191">The Mediation Servers can route calls through multiple gateways, Session Border Controllers (SBCs) provided by Internet telephony service providers, or a combination of the two.</span></span> <span data-ttu-id="f3297-192">此外，集區中的多個轉送伺服器可以與多個閘道互動。</span><span class="sxs-lookup"><span data-stu-id="f3297-192">Additionally, multiple Mediation Servers in the pool can interact with multiple gateways.</span></span> <span data-ttu-id="f3297-193">在轉送伺服器與閘道之間定義的邏輯路由稱為主幹。</span><span class="sxs-lookup"><span data-stu-id="f3297-193">The logical route defined between a Mediation Server and gateway is called a trunk.</span></span> <span data-ttu-id="f3297-194">當內部使用者加入 PSTN 通話時，前端集區上的輸出路由邏輯會選擇哪一個主幹可路由傳送該特定通話的所有可能可使用的組合。</span><span class="sxs-lookup"><span data-stu-id="f3297-194">When an internal user places a PSTN call, outbound routing logic on the Front End pool chooses which trunk to route over out of all possible combinations that may be available for routing that particular call.</span></span> <span data-ttu-id="f3297-195">使用 DNS 負載平衡，如果呼叫因集區中的特定轉送伺服器問題而無法抵達閘道，則會將此呼叫重試至集區中的替代轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="f3297-195">With DNS load balancing, if a call fails to reach a gateway due to an issue with a particular Mediation Server in the pool, the call will be retried to an alternate Mediation Server in the pool.</span></span>

<span data-ttu-id="f3297-196">如需規劃多個閘道的詳細資訊，請參閱 [M:N 主幹 In 商務用 Skype Server](m-n-trunk.md)。</span><span class="sxs-lookup"><span data-stu-id="f3297-196">For details about planning for multiple gateways, see [M:N trunk in Skype for Business Server](m-n-trunk.md).</span></span>

<span data-ttu-id="f3297-197">如需其他輸出路由增強功能的詳細資訊，請參閱 [通話路由](/previous-versions/office/lync-server-2013/lync-server-2013-voice-routes)。</span><span class="sxs-lookup"><span data-stu-id="f3297-197">For details about other outbound routing enhancements, see [Call Routes](/previous-versions/office/lync-server-2013/lync-server-2013-voice-routes).</span></span>

#### <a name="gateway-topologies"></a><span data-ttu-id="f3297-198">閘道拓撲</span><span class="sxs-lookup"><span data-stu-id="f3297-198">Gateway Topologies</span></span>

<span data-ttu-id="f3297-199">當您考慮閘道部署的基本問題時，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="f3297-199">When you consider the fundamental questions of gateway deployment, follow these steps:</span></span>

1. <span data-ttu-id="f3297-200">使用 Enterprise Voice，計算您想要提供 PSTN 連線的網站數目。</span><span class="sxs-lookup"><span data-stu-id="f3297-200">Count the sites at which you want to provide PSTN connectivity by using Enterprise Voice.</span></span>

2. <span data-ttu-id="f3297-201">評估每個網站的流量 (使用者數目，以及每個使用者) 每小時平均通話數目。</span><span class="sxs-lookup"><span data-stu-id="f3297-201">Estimate the traffic at each site (number of users and average number of calls per hour per user).</span></span>

3. <span data-ttu-id="f3297-202">在每個網站部署一或多個閘道，以處理預期的流量。</span><span class="sxs-lookup"><span data-stu-id="f3297-202">Deploy one or more gateways at each site to handle the anticipated traffic.</span></span>

<span data-ttu-id="f3297-203">透過此拓撲，每個網站和兩個網站之間的工作人員間的通話都會透過您的內部網路進行路由傳送。</span><span class="sxs-lookup"><span data-stu-id="f3297-203">With this topology, calls among workers at each site and between sites are all routed over your intranet.</span></span> <span data-ttu-id="f3297-204">對 PSTN 所進行的呼叫會透過企業 IP 網路路由傳送至最接近目的地號碼位置的閘道。不過，如果您的組織支援數十或數百甚至數千部的網站分散于一或多個洲，那麼許多金融機構和其他大型企業會這麼做？</span><span class="sxs-lookup"><span data-stu-id="f3297-204">Calls to the PSTN are routed over the enterprise IP network to the gateways that are closest to the location of the destination numbers.But what if your organization supports dozens or hundreds or even thousands of sites spread across one or more continents, as many financial institutions and other large enterprises do?</span></span> <span data-ttu-id="f3297-205">在這種情況下，在每個網站部署個別的閘道是不可行的。</span><span class="sxs-lookup"><span data-stu-id="f3297-205">In such cases, deploying a separate gateway at each site is not practical.</span></span>

<span data-ttu-id="f3297-206">若要解決此問題，許多大型公司喜歡部署一或多個大型電話語音中央網站。</span><span class="sxs-lookup"><span data-stu-id="f3297-206">To address this issue, many large companies prefer to deploy one or a few large telephony central sites.</span></span>

<span data-ttu-id="f3297-207">在此拓撲中，會在每個中央網站上部署數個足以容納預期使用者負載的大型閘道。</span><span class="sxs-lookup"><span data-stu-id="f3297-207">In this topology, several large gateways sufficient to accommodate the anticipated user load are deployed at each central site.</span></span> <span data-ttu-id="f3297-208">企業的所有呼叫都是由公司的電話服務提供者轉接至中央網站。</span><span class="sxs-lookup"><span data-stu-id="f3297-208">All calls to users in the enterprise are forwarded by the company's telephone service provider to a central site.</span></span> <span data-ttu-id="f3297-209">中央網站的路由邏輯會決定是否要透過內部網路或 PSTN 路由傳送呼叫。</span><span class="sxs-lookup"><span data-stu-id="f3297-209">Routing logic at the central site determines whether the call should be routed over the intranet or to the PSTN.</span></span>

#### <a name="gateway-location"></a><span data-ttu-id="f3297-210">閘道位置</span><span class="sxs-lookup"><span data-stu-id="f3297-210">Gateway Location</span></span>

<span data-ttu-id="f3297-211">閘道位置也可以決定您選擇的閘道類型及設定方式。</span><span class="sxs-lookup"><span data-stu-id="f3297-211">Gateway location may also determine the types of gateways that you choose and how they are configured.</span></span> <span data-ttu-id="f3297-212">有許多 PSTN 通訊協定，都不是全球標準。</span><span class="sxs-lookup"><span data-stu-id="f3297-212">There are dozens of PSTN protocols, none of which is a worldwide standard.</span></span> <span data-ttu-id="f3297-213">如果您的所有閘道都位於單一國家/地區內，這不是問題，但是如果您在多個國家/地區內找到閘道，則每個國家/地區都必須根據該國家/地區的 PSTN 標準進行設定。</span><span class="sxs-lookup"><span data-stu-id="f3297-213">If all your gateways are located in a single country/region, this is not an issue, but if you locate gateways in several countries/regions, each must be configured according to the PSTN standards of that country/region.</span></span> <span data-ttu-id="f3297-214">此外，認證于中運作的閘道（例如，加拿大）可能無法在印度、巴西或歐盟進行認證。</span><span class="sxs-lookup"><span data-stu-id="f3297-214">Moreover, gateways that are certified for operation in, for example, Canada, may not be certified in India, Brazil, or the European Union.</span></span>

#### <a name="gateway-size-and-number"></a><span data-ttu-id="f3297-215">閘道大小和數目</span><span class="sxs-lookup"><span data-stu-id="f3297-215">Gateway Size and Number</span></span>

<span data-ttu-id="f3297-216">大多陣列織會考慮採用從2到高達960埠的大小部署範圍的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="f3297-216">The PSTN gateways that most organizations will consider deploying range in size from 2 to as many as 960 ports.</span></span> <span data-ttu-id="f3297-217"> (甚至更大的閘道，但是主要是由電話服務提供者使用。 ) 當您的組織需要的埠數目進行估計時，請使用下列指導方針：</span><span class="sxs-lookup"><span data-stu-id="f3297-217">(There are even larger gateways, but these are used mainly by telephone service providers.) When estimating the number of ports your organization requires, use the following guidelines:</span></span>

- <span data-ttu-id="f3297-218">每位使用者每小時一次 PSTN 通話的組織 (每小時一次 PSTN 通話) 應該為每15位使用者分配一個埠。</span><span class="sxs-lookup"><span data-stu-id="f3297-218">Organizations with light telephony usage (one PSTN call per user per hour) should allocate one port for every 15 users.</span></span> <span data-ttu-id="f3297-219">例如，如果您有20位使用者，則需要有兩個埠的閘道。</span><span class="sxs-lookup"><span data-stu-id="f3297-219">For example, if you have 20 users, you will require a gateway with two ports.</span></span>

- <span data-ttu-id="f3297-220">組織使用適中的電話語音流量 (每個使用者每小時兩個 PSTN 通話) 每10位使用者都應該為一個埠指派。</span><span class="sxs-lookup"><span data-stu-id="f3297-220">Organizations with moderate telephony usage (two PSTN calls per user per hour) should allocate one port for every 10 users.</span></span> <span data-ttu-id="f3297-221">例如，如果您有100位使用者，則需要在一或多個閘道間分攤10個埠。</span><span class="sxs-lookup"><span data-stu-id="f3297-221">For example, if you have 100 users, you will require a total of 10 ports allocated among one or more gateways.</span></span>

- <span data-ttu-id="f3297-222">使用大量電話語音使用的組織 (每位使用者每小時三個或更多 PSTN 通話) 應該為每五位使用者分配一個埠。</span><span class="sxs-lookup"><span data-stu-id="f3297-222">Organizations with heavy telephony usage (three or more PSTN calls per user per hour) should allocate one port for every five users.</span></span> <span data-ttu-id="f3297-223">例如，如果您有47000位使用者，則需要至少10個大型閘道中所分配的9400埠總數。</span><span class="sxs-lookup"><span data-stu-id="f3297-223">For example, if you have 47,000 users, you will require a total of 9,400 ports allocated among at least 10 large gateways.</span></span>

- <span data-ttu-id="f3297-224">當您組織中的使用者人數或流量量增加時，可以取得額外的埠。</span><span class="sxs-lookup"><span data-stu-id="f3297-224">Additional ports can be acquired as the number of users or amount of traffic in your organization increases.</span></span>

<span data-ttu-id="f3297-225">針對您必須支援的任何特定使用者數目，您可以選擇部署較少、更大的閘道或較小的閘道。</span><span class="sxs-lookup"><span data-stu-id="f3297-225">For any given number of users you must support, you have the choice of deploying fewer, larger gateways, or smaller ones.</span></span> <span data-ttu-id="f3297-226">一般來說，如果一個閘道失敗時，建議至少有兩個組織閘道可維護可用性。</span><span class="sxs-lookup"><span data-stu-id="f3297-226">As a rule, a minimum of two gateways for an organization is recommended to maintain availability if one gateway fails.</span></span>

<span data-ttu-id="f3297-227">您部署的每個 PSTN 閘道都必須至少有一個對應的轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="f3297-227">Each PSTN gateway that you deploy must have at least one corresponding Mediation Server.</span></span>