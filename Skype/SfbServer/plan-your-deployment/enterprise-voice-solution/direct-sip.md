---
title: 商務用 Skype Server 中的直接 SIP 連線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0a37737d-9628-4e36-b27b-c134fa5a3882
description: 商務用 Skype 伺服器與企業語音中的 PSTN 閘道與 IP PBX 之間都支援直接 SIP 連線。
ms.openlocfilehash: d70fa72032b86251870ebaf623679dedc782fe24
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187732"
---
# <a name="direct-sip-connections-in-skype-for-business-server"></a><span data-ttu-id="d556b-103">商務用 Skype Server 中的直接 SIP 連線</span><span class="sxs-lookup"><span data-stu-id="d556b-103">Direct SIP connections in Skype for Business Server</span></span>

<span data-ttu-id="d556b-104">商務用 Skype 伺服器與企業語音中的 PSTN 閘道與 IP PBX 之間都支援直接 SIP 連線。</span><span class="sxs-lookup"><span data-stu-id="d556b-104">Direct SIP connections are supported between Skype for Business Server and both PSTN gateways and IP-PBX in Enterprise Voice.</span></span>

<span data-ttu-id="d556b-105">您可以使用直接 SIP 連線, 將商務用 Skype 伺服器連線至下列其中一項:</span><span class="sxs-lookup"><span data-stu-id="d556b-105">You can use direct SIP connections to connect Skype for Business Server to either of the following:</span></span>

- <span data-ttu-id="d556b-106">IP PBX</span><span class="sxs-lookup"><span data-stu-id="d556b-106">An IP-PBX</span></span>

- <span data-ttu-id="d556b-107">PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="d556b-107">A PSTN gateway</span></span>

<span data-ttu-id="d556b-108">若要實現直接 SIP 連線, 您必須遵循與實施 SIP 幹線相同的部署步驟。</span><span class="sxs-lookup"><span data-stu-id="d556b-108">To implement a direct SIP connection, you follow essentially the same deployment steps as you would to implement a SIP trunk.</span></span> <span data-ttu-id="d556b-109">在這兩種情況下, 您可以使用中繼伺服器的外部介面來實現連線。</span><span class="sxs-lookup"><span data-stu-id="d556b-109">In both cases, you implement the connection by using the external interface of a Mediation Server.</span></span> <span data-ttu-id="d556b-110">唯一的差異是, 您可以將 SIP trunks 連線至外部實體 (例如 ITSP 閘道), 並將直接 SIP 連線連接到本機網路中的內部實體, 例如 IP PBX 或公用交換電話網絡 (PSTN) 閘道。</span><span class="sxs-lookup"><span data-stu-id="d556b-110">The only difference is that you connect SIP trunks to an external entity, such as an ITSP gateway, and you connect direct SIP connections to an internal entity within your local network, such as an IP-PBX or a public switched telephone network (PSTN) gateway.</span></span>

## <a name="direct-sip-deployment-options"></a><span data-ttu-id="d556b-111">SIP 直接部署選項</span><span class="sxs-lookup"><span data-stu-id="d556b-111">Direct SIP deployment options</span></span>

### <a name="skype-for-business-server-stand-alone"></a><span data-ttu-id="d556b-112">商務用 Skype 伺服器 (獨立版)</span><span class="sxs-lookup"><span data-stu-id="d556b-112">Skype for Business Server Stand-Alone</span></span>
<span data-ttu-id="d556b-113"><a name="BKMK_CommunicationsServerStand-Alone"> </a></span><span class="sxs-lookup"><span data-stu-id="d556b-113"></span></span>

<span data-ttu-id="d556b-114">如果您的組織使用本節所述的其中一個部署, 您可以使用商務用 Skype Server 做為組織中的部分或全部的電話方案。</span><span class="sxs-lookup"><span data-stu-id="d556b-114">If your organization uses one of the deployments described in this section, you can use Skype for Business Server as the sole telephony solution for part or all of an organization.</span></span> <span data-ttu-id="d556b-115">本節詳細說明下列部署:</span><span class="sxs-lookup"><span data-stu-id="d556b-115">This section describes the following deployments in detail:</span></span>

- <span data-ttu-id="d556b-116">**增量式部署:** 此選項假設您有現有的專用分支 exchange (PBX) 基礎結構, 而且您想要將企業語音逐步引入到貴組織內較小的群組或小組中。</span><span class="sxs-lookup"><span data-stu-id="d556b-116">**Incremental deployment:** This option assumes that you have an existing private branch exchange (PBX) infrastructure and you intend to introduce Enterprise Voice incrementally to smaller groups or teams within your organization.</span></span>

- <span data-ttu-id="d556b-117">**僅限 VoIP 部署:** 此選項假設您要考慮在沒有傳統電話結構的網站上部署企業語音。</span><span class="sxs-lookup"><span data-stu-id="d556b-117">**VoIP-only deployment:** this option assumes that you are considering deploying Enterprise Voice at a site that does not have a traditional telephony infrastructure.</span></span>

#### <a name="incremental-deployment"></a><span data-ttu-id="d556b-118">漸進式部署</span><span class="sxs-lookup"><span data-stu-id="d556b-118">Incremental Deployment</span></span>

<span data-ttu-id="d556b-119">在漸進式部署中, 商務用 Skype Server 是個別團隊或部門的唯一電話方案, 而組織中的其他使用者仍可繼續使用 PBX。</span><span class="sxs-lookup"><span data-stu-id="d556b-119">In incremental deployment, Skype for Business Server is the sole telephony solution for individual teams or departments, while the rest of the users in an organization continue to use a PBX.</span></span> <span data-ttu-id="d556b-120">此增量式部署策略提供一種方式, 透過受控制的試驗計畫將 IP 電話引入您的企業。</span><span class="sxs-lookup"><span data-stu-id="d556b-120">This incremental deployment strategy provides one way to introduce IP telephony into your enterprise through controlled pilot programs.</span></span> <span data-ttu-id="d556b-121">Microsoft 整合通訊需要最佳服務的工作組會移至企業語音, 而其他使用者則會保留在現有的 PBX 中。</span><span class="sxs-lookup"><span data-stu-id="d556b-121">Workgroups whose communication needs are best served by Microsoft Unified Communications are moved to Enterprise Voice, while other users remain on the existing PBX.</span></span> <span data-ttu-id="d556b-122">您可以視需要將其他工作組遷移至企業語音。</span><span class="sxs-lookup"><span data-stu-id="d556b-122">Additional workgroups can be migrated to Enterprise Voice, as needed.</span></span>

<span data-ttu-id="d556b-123">如果您明確定義的使用者群組有共同的通訊需求, 且其本身提供集中式管理, 則建議使用 [遞增] 選項。</span><span class="sxs-lookup"><span data-stu-id="d556b-123">The incremental option is recommended if you have clearly defined user groups that have communication requirements in common and that lend themselves to centralized management.</span></span> <span data-ttu-id="d556b-124">如果您的小組或部門分佈于廣域地理區域, 且在長途電話費用中的節約可能相當重要, 此選項也很有效。</span><span class="sxs-lookup"><span data-stu-id="d556b-124">This option is also effective if you have teams or departments that are spread over wide geographic areas, where the savings in long-distance charges can be significant.</span></span> <span data-ttu-id="d556b-125">事實上, 此選項對於建立成員可能散佈在地球上的虛擬小組非常有用。</span><span class="sxs-lookup"><span data-stu-id="d556b-125">In fact, this option is useful for creating virtual teams whose members may be scattered across the globe.</span></span> <span data-ttu-id="d556b-126">您可以建立、修改或解散此類小組, 以快速回應變化的商業需求。</span><span class="sxs-lookup"><span data-stu-id="d556b-126">You can create, modify, or disband such teams in rapid response to shifting business requirements.</span></span>

<span data-ttu-id="d556b-127">下圖顯示在 PBX 後部署企業語音的一般拓撲。</span><span class="sxs-lookup"><span data-stu-id="d556b-127">The following figure shows the generic topology for deployment of Enterprise Voice behind a PBX.</span></span> <span data-ttu-id="d556b-128">這是漸進式部署的建議拓撲。</span><span class="sxs-lookup"><span data-stu-id="d556b-128">This is the recommended topology for incremental deployment.</span></span>

<span data-ttu-id="d556b-129">**增量式部署選項**</span><span class="sxs-lookup"><span data-stu-id="d556b-129">**Incremental deployment option**</span></span>

![部門的移轉選項圖表](../../media/Fig28_Departmental_migration_option.jpg)

> [!NOTE]
> <span data-ttu-id="d556b-131">如果您要將商務用 Skype Server 部署連線到認證的直接 SIP 合作夥伴, 則不需要在中繼伺服器與 PBX 之間的公用交換電話網絡 (PSTN) 閘道。</span><span class="sxs-lookup"><span data-stu-id="d556b-131">If you are connecting your Skype for Business Server deployment to a certified Direct SIP partner, a public switched telephone network (PSTN) gateway between the Mediation Server and the PBX is not required.</span></span> <span data-ttu-id="d556b-132">如需認證直接 SIP 合作夥伴的清單, 請參閱[Microsoft 整合通訊開啟互通性計畫](https://go.microsoft.com/fwlink/p/?linkId=203309)。</span><span class="sxs-lookup"><span data-stu-id="d556b-132">For a list of certified Direct SIP partners, see the  [Microsoft Unified Communications Open Interoperability Program](https://go.microsoft.com/fwlink/p/?linkId=203309).</span></span>

> [!NOTE]
> <span data-ttu-id="d556b-133">此圖所示的媒體路徑已啟用媒體旁路 (建議的配置)。</span><span class="sxs-lookup"><span data-stu-id="d556b-133">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="d556b-134">如果您選用停用媒體旁路, 媒體路徑會透過中繼伺服器進行路由。</span><span class="sxs-lookup"><span data-stu-id="d556b-134">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>

<span data-ttu-id="d556b-135">在此拓撲中, 已選取的部門或工作組可供企業語音。</span><span class="sxs-lookup"><span data-stu-id="d556b-135">In this topology, selected departments or workgroups are enabled for Enterprise Voice.</span></span> <span data-ttu-id="d556b-136">PSTN 閘道會將語音透過網際網路通訊協定 (VoIP) 的工作組連結到 PBX。</span><span class="sxs-lookup"><span data-stu-id="d556b-136">A PSTN gateway links the Voice over Internet Protocol (VoIP)-enabled workgroup to the PBX.</span></span> <span data-ttu-id="d556b-137">已啟用企業語音的使用者, 包括遠端工作人員、透過 IP 網路進行通訊。</span><span class="sxs-lookup"><span data-stu-id="d556b-137">Users who are enabled for Enterprise Voice, including remote workers, communicate across the IP network.</span></span> <span data-ttu-id="d556b-138">企業語音使用者通話至 PSTN, 而未啟用企業語音的同事則會路由至適當的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="d556b-138">Calls by Enterprise Voice users to the PSTN and to coworkers who are not enabled for Enterprise Voice are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="d556b-139">來自仍在 PBX 系統或從 PSTN 的呼叫者的同事的呼叫會路由到 PSTN 閘道, 並將呼叫轉寄給商務用 Skype Server 進行路由。</span><span class="sxs-lookup"><span data-stu-id="d556b-139">Calls from colleagues who are still on the PBX system, or from callers on the PSTN, are routed to the PSTN gateway, which forwards the calls to Skype for Business Server for routing.</span></span>

<span data-ttu-id="d556b-140">將企業語音連接至現有的 PBX 基礎結構以進行互通性時, 有兩個建議的設定: 在 PBX 前, 在 PBX 和企業語音背後使用企業語音。</span><span class="sxs-lookup"><span data-stu-id="d556b-140">There are two recommended configurations for connecting Enterprise Voice to an existing PBX infrastructure for interoperability: Enterprise Voice behind the PBX and Enterprise Voice in front of the PBX.</span></span>

#### <a name="enterprise-voice-behind-the-pbx"></a><span data-ttu-id="d556b-141">在 PBX 後的企業語音</span><span class="sxs-lookup"><span data-stu-id="d556b-141">Enterprise Voice Behind the PBX</span></span>

<span data-ttu-id="d556b-142">當企業語音部署在 PBX 之後, 所有來自 PSTN 的呼叫都會送到 PBX, 將呼叫企業語音使用者的電話路由至 PSTN 閘道, 並呼叫 pbx 使用者至 PBX。</span><span class="sxs-lookup"><span data-stu-id="d556b-142">When Enterprise Voice is deployed behind the PBX, all calls from the PSTN arrive at the PBX, which routes calls to Enterprise Voice users to a PSTN gateway, and calls to PBX users to the PBX.</span></span>

#### <a name="enterprise-voice-in-front-of-the-pbx"></a><span data-ttu-id="d556b-143">PBX 前面的企業語音</span><span class="sxs-lookup"><span data-stu-id="d556b-143">Enterprise Voice in Front of the PBX</span></span>

<span data-ttu-id="d556b-144">當您在 PBX 前面部署企業語音時, 所有來電都會到達 PSTN 閘道, 這會將企業語音使用者的呼叫傳送到商務用 Skype Server, 並將 PBX 使用者的呼叫給 PBX。</span><span class="sxs-lookup"><span data-stu-id="d556b-144">When Enterprise Voice is deployed in front of the PBX, all calls arrive at the PSTN gateway, which routes calls for Enterprise Voice users to Skype for Business Server and calls for PBX users to the PBX.</span></span> <span data-ttu-id="d556b-145">從企業語音和 PBX 使用者到 PSTN 的呼叫都是透過 IP 網路路由到最經濟高效的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="d556b-145">Calls to the PSTN from both Enterprise Voice and PBX users are routed over the IP network to the most cost-efficient PSTN gateway.</span></span> <span data-ttu-id="d556b-146">下表顯示這項設定的優點與缺點。</span><span class="sxs-lookup"><span data-stu-id="d556b-146">The following table shows the advantages and disadvantages of this configuration.</span></span>

<span data-ttu-id="d556b-147">**在 PBX 前面部署企業語音的優點與缺點**</span><span class="sxs-lookup"><span data-stu-id="d556b-147">**Advantages and Disadvantages of Deploying Enterprise Voice in Front of PBX**</span></span>

|<span data-ttu-id="d556b-148">**優勢**</span><span class="sxs-lookup"><span data-stu-id="d556b-148">**Advantages**</span></span>|<span data-ttu-id="d556b-149">**劣勢**</span><span class="sxs-lookup"><span data-stu-id="d556b-149">**Disadvantages**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d556b-150">PBX 仍可為不支援企業語音的使用者提供服務。</span><span class="sxs-lookup"><span data-stu-id="d556b-150">PBX still serves users not enabled for Enterprise Voice.</span></span>  <br/> |<span data-ttu-id="d556b-151">現有的閘道可能不支援您想要的功能或容量。</span><span class="sxs-lookup"><span data-stu-id="d556b-151">Existing gateways may not support the features or capacity that you want.</span></span>  <br/> |
|<span data-ttu-id="d556b-152">PBX 會處理所有先前的裝置。</span><span class="sxs-lookup"><span data-stu-id="d556b-152">PBX handles all earlier devices.</span></span>  <br/> |<span data-ttu-id="d556b-153">需要從閘道到 PBX 的主幹, 以及從閘道到中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="d556b-153">Requires a trunk from gateway to the PBX and from the gateway to the Mediation Server.</span></span> <span data-ttu-id="d556b-154">您可能需要來自服務提供者的其他 trunks。</span><span class="sxs-lookup"><span data-stu-id="d556b-154">You may need more trunks from the service provider.</span></span>  <br/> |
|<span data-ttu-id="d556b-155">企業語音使用者會保留相同的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d556b-155">Enterprise Voice users keep the same phone numbers.</span></span>  <br/> | <br/> |

#### <a name="voip-only-deployment"></a><span data-ttu-id="d556b-156">僅限 VoIP 部署</span><span class="sxs-lookup"><span data-stu-id="d556b-156">VoIP-Only Deployment</span></span>

<span data-ttu-id="d556b-157">企業語音提供新的企業, 以及現有企業的新 office 網站, 有機會可以實施完整的 VoIP 解決方案, 而不必擔心 PBX 整合, 或導致大量的部署和維護。IP PBX 基礎結構的成本。</span><span class="sxs-lookup"><span data-stu-id="d556b-157">Enterprise Voice provides new businesses, and also new office sites for existing businesses, with the opportunity to implement a full-featured VoIP solution without having to worry about PBX integration or incurring the substantial deployment and maintenance costs of an IP-PBX infrastructure.</span></span> <span data-ttu-id="d556b-158">這個方案同時支援現場與遠端員工。</span><span class="sxs-lookup"><span data-stu-id="d556b-158">This solution supports both on-site and remote workers.</span></span>

<span data-ttu-id="d556b-159">在此部署中, 所有通話都是經由 IP 網路路由。</span><span class="sxs-lookup"><span data-stu-id="d556b-159">In this deployment, all calls are routed over the IP network.</span></span> <span data-ttu-id="d556b-160">PSTN 的呼叫會路由至適當的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="d556b-160">Calls to the PSTN are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="d556b-161">[商務用 Skype] 或 [Lync 手機版] 是 softphone。</span><span class="sxs-lookup"><span data-stu-id="d556b-161">Skype for Business or Lync Phone Edition serves as a softphone.</span></span> <span data-ttu-id="d556b-162">遠端通話控制無法使用且不必要, 因為沒有可供使用者控制的 PBX 電話。</span><span class="sxs-lookup"><span data-stu-id="d556b-162">Remote call control is unavailable and unnecessary because there are no PBX phones for users to control.</span></span> <span data-ttu-id="d556b-163">語音信箱和自動助理服務可透過 [Exchange 整合訊息 (UM)] 的選擇性部署來使用。</span><span class="sxs-lookup"><span data-stu-id="d556b-163">Voice mail and auto-attendant services are available through the optional deployment of Exchange Unified Messaging (UM).</span></span>

> [!NOTE]
> <span data-ttu-id="d556b-164">除了支援商務用 Skype Server 所需的網路基礎結構之外, VoIP 專用部署還可以使用小型的合格閘道來支援傳真機和類比裝置。</span><span class="sxs-lookup"><span data-stu-id="d556b-164">In addition to the network infrastructure that is required to support Skype for Business Server, a VoIP-only deployment can use a small, qualified gateway to support fax machines and analog devices.</span></span>

<span data-ttu-id="d556b-165">下圖顯示僅限 VoIP 部署的一般拓撲。</span><span class="sxs-lookup"><span data-stu-id="d556b-165">The following figure shows a typical topology for a VoIP-only deployment.</span></span>

<span data-ttu-id="d556b-166">**僅限 VoIP 部署選項**</span><span class="sxs-lookup"><span data-stu-id="d556b-166">**VoIP-only deployment option**</span></span>

![Greenfidle 部署選項](../../media/Fig29_Greenfield_deployment_option.jpg)

> [!NOTE]
> <span data-ttu-id="d556b-168">此圖所示的媒體路徑已啟用媒體旁路 (建議的配置)。</span><span class="sxs-lookup"><span data-stu-id="d556b-168">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="d556b-169">如果您選用停用媒體旁路, 媒體路徑會透過中繼伺服器進行路由。</span><span class="sxs-lookup"><span data-stu-id="d556b-169">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>

## <a name="pstn-gateway-deployment-options"></a><span data-ttu-id="d556b-170">PSTN 閘道部署選項</span><span class="sxs-lookup"><span data-stu-id="d556b-170">PSTN Gateway deployment options</span></span>

### <a name="pstn-gateways"></a><span data-ttu-id="d556b-171">PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="d556b-171">PSTN Gateways</span></span>

<span data-ttu-id="d556b-172">公用交換電話網絡 (PSTN) 閘道是協力廠商硬體元件, 可直接或透過連線至 SIP trunks, 在企業語音結構和 PSTN 之間轉換信號和媒體。</span><span class="sxs-lookup"><span data-stu-id="d556b-172">Public switched telephone network (PSTN) gateways are third-party hardware components that translate signaling and media between the Enterprise Voice infrastructure and the PSTN, either directly or through connection to SIP trunks.</span></span> <span data-ttu-id="d556b-173">在其中一個拓撲中, 閘道會終止 PSTN。</span><span class="sxs-lookup"><span data-stu-id="d556b-173">In either topology, the gateway terminates the PSTN.</span></span> <span data-ttu-id="d556b-174">閘道會隔離在自己的子網中, 並透過轉送伺服器連線到商業網路。</span><span class="sxs-lookup"><span data-stu-id="d556b-174">The gateway is isolated in its own subnet and is connected to the enterprise network through the Mediation Server.</span></span>

<span data-ttu-id="d556b-175">具有多個網站的企業通常會在每個網站上部署一個或多個閘道。</span><span class="sxs-lookup"><span data-stu-id="d556b-175">An enterprise with multiple sites would typically deploy one or more gateways at each site.</span></span> <span data-ttu-id="d556b-176">分支網站可以透過閘道或透過 Survivable 分支裝置連線到 PSTN, 這會將閘道與伺服器結合在單一方塊中。</span><span class="sxs-lookup"><span data-stu-id="d556b-176">Branch sites can connect to the PSTN either through a gateway, or through a Survivable Branch Appliance, which combines gateway and servers in a single box.</span></span> <span data-ttu-id="d556b-177">如果分支網站使用閘道, 則會在網站上需要註冊機構和中繼伺服器, 除非 WAN 連結是復原的。</span><span class="sxs-lookup"><span data-stu-id="d556b-177">If branch sites use a gateway, both a Registrar and Mediation Server are required on site, unless the WAN link is resilient.</span></span> <span data-ttu-id="d556b-178">一或多個在前端伺服器上 collocated 的中繼伺服器可以在每個網站上傳送一或多個閘道的呼叫。</span><span class="sxs-lookup"><span data-stu-id="d556b-178">One or more Mediation Servers, which are collocated on Front End Servers, can route calls for the one or more gateways at each site.</span></span> <span data-ttu-id="d556b-179">我們建議您將網站上所需的註冊機構、中繼伺服器和閘道部署為 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="d556b-179">We recommend that the Registrar, Mediation Server, and gateway required on site are deployed as a Survivable Branch Appliance.</span></span>

<span data-ttu-id="d556b-180">確定 PSTN 閘道的數目、大小及位置, 可能是規劃企業語音基礎結構時必須做出的最重要且昂貴的決策。</span><span class="sxs-lookup"><span data-stu-id="d556b-180">Determining the number, size, and location of PSTN gateways is perhaps the most important and expensive decision you must make when planning your Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="d556b-181">以下是要考慮的主要問題。</span><span class="sxs-lookup"><span data-stu-id="d556b-181">Here are the main questions to consider.</span></span> <span data-ttu-id="d556b-182">請記住, 這些問題的答案全都相互依賴</span><span class="sxs-lookup"><span data-stu-id="d556b-182">Keep in mind that the answers to these questions are all interdependent</span></span>

- <span data-ttu-id="d556b-183">需要多少 PSTN 閘道？</span><span class="sxs-lookup"><span data-stu-id="d556b-183">How many PSTN gateways are needed?</span></span> <span data-ttu-id="d556b-184">答案取決於使用者數目、預期的同時通話數 (流量負載), 以及網站數量 (每個網站需要一個)。</span><span class="sxs-lookup"><span data-stu-id="d556b-184">The answer depends on the number of users, the anticipated number of simultaneous calls (traffic load), and the number of sites (each site needs one).</span></span>

- <span data-ttu-id="d556b-185">閘道應該是什麼大小？</span><span class="sxs-lookup"><span data-stu-id="d556b-185">What size should the gateways be?</span></span> <span data-ttu-id="d556b-186">答案視網站上的使用者數目和流量負荷而定。</span><span class="sxs-lookup"><span data-stu-id="d556b-186">The answer depends on the number of users at the site and on the traffic load.</span></span>

- <span data-ttu-id="d556b-187">閘道應該位於何處？</span><span class="sxs-lookup"><span data-stu-id="d556b-187">Where should the gateways be located?</span></span> <span data-ttu-id="d556b-188">答案是在拓撲的一部分, 以及貴組織的地理位置分佈所組成。</span><span class="sxs-lookup"><span data-stu-id="d556b-188">The answer depends in part on the topology and in part on the geographic distribution of your organization.</span></span>

  <span data-ttu-id="d556b-189">您也應該考慮閘道拓朴選項 (如需詳細資訊, 請參閱本主題稍後的閘道拓撲)。</span><span class="sxs-lookup"><span data-stu-id="d556b-189">You should also consider your gateway topology options (for details, see Gateway Topologies later in this topic).</span></span>

#### <a name="mn-trunk-support"></a><span data-ttu-id="d556b-190">M:N 幹線支援</span><span class="sxs-lookup"><span data-stu-id="d556b-190">M:N Trunk Support</span></span>

<span data-ttu-id="d556b-191">中繼伺服器可透過多個閘道、網際網路電話服務提供者所提供的會話邊界控制器 (SBCs), 或這兩者的組合, 路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="d556b-191">The Mediation Servers can route calls through multiple gateways, Session Border Controllers (SBCs) provided by Internet telephony service providers, or a combination of the two.</span></span> <span data-ttu-id="d556b-192">此外, 池中的多個轉送伺服器可以與多個閘道互動。</span><span class="sxs-lookup"><span data-stu-id="d556b-192">Additionally, multiple Mediation Servers in the pool can interact with multiple gateways.</span></span> <span data-ttu-id="d556b-193">在中繼伺服器和閘道之間定義的邏輯路由稱為主幹。</span><span class="sxs-lookup"><span data-stu-id="d556b-193">The logical route defined between a Mediation Server and gateway is called a trunk.</span></span> <span data-ttu-id="d556b-194">當內部使用者進行 PSTN 通話時, 前端池上的輸出路由邏輯會選擇要路由超出所有可能可供路由該特定呼叫的組合。</span><span class="sxs-lookup"><span data-stu-id="d556b-194">When an internal user places a PSTN call, outbound routing logic on the Front End pool chooses which trunk to route over out of all possible combinations that may be available for routing that particular call.</span></span> <span data-ttu-id="d556b-195">使用 DNS 負載平衡時, 如果由於池中的特定中繼伺服器問題而導致呼叫無法接通閘道, 該呼叫將會重試至池中的備用轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="d556b-195">With DNS load balancing, if a call fails to reach a gateway due to an issue with a particular Mediation Server in the pool, the call will be retried to an alternate Mediation Server in the pool.</span></span>

<span data-ttu-id="d556b-196">如需規劃多個閘道的詳細資料, 請參閱[在商務用 Skype 伺服器中 M:N 幹線](m-n-trunk.md)。</span><span class="sxs-lookup"><span data-stu-id="d556b-196">For details about planning for multiple gateways, see [M:N trunk in Skype for Business Server](m-n-trunk.md).</span></span>

<span data-ttu-id="d556b-197">如需其他輸出路由增強功能的詳細資料, 請參閱[呼叫路由](https://technet.microsoft.com/library/a2ddf327-2ec4-407b-af0f-276f2b13eefd.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d556b-197">For details about other outbound routing enhancements, see [Call Routes](https://technet.microsoft.com/library/a2ddf327-2ec4-407b-af0f-276f2b13eefd.aspx).</span></span>

#### <a name="gateway-topologies"></a><span data-ttu-id="d556b-198">閘道拓撲</span><span class="sxs-lookup"><span data-stu-id="d556b-198">Gateway Topologies</span></span>

<span data-ttu-id="d556b-199">當您考慮閘道部署的基本問題時, 請遵循下列步驟:</span><span class="sxs-lookup"><span data-stu-id="d556b-199">When you consider the fundamental questions of gateway deployment, follow these steps:</span></span>

1. <span data-ttu-id="d556b-200">使用企業語音來計算您想要提供 PSTN 連線性的網站數目。</span><span class="sxs-lookup"><span data-stu-id="d556b-200">Count the sites at which you want to provide PSTN connectivity by using Enterprise Voice.</span></span>

2. <span data-ttu-id="d556b-201">估計每個網站的流量 (使用者數及每個使用者每小時的平均通話數)。</span><span class="sxs-lookup"><span data-stu-id="d556b-201">Estimate the traffic at each site (number of users and average number of calls per hour per user).</span></span>

3. <span data-ttu-id="d556b-202">在每個網站部署一或多個閘道, 以處理預期的流量。</span><span class="sxs-lookup"><span data-stu-id="d556b-202">Deploy one or more gateways at each site to handle the anticipated traffic.</span></span>

<span data-ttu-id="d556b-203">在這個拓朴中, 每個網站的工作人員之間以及網站之間的呼叫都是在您的內部網路上路由。</span><span class="sxs-lookup"><span data-stu-id="d556b-203">With this topology, calls among workers at each site and between sites are all routed over your intranet.</span></span> <span data-ttu-id="d556b-204">對 PSTN 的呼叫會在企業 IP 網路上路由至最接近目的地號碼位置的閘道。但是, 如果您的組織支援數十或幾百或甚至上千個以上的網站散佈在一或多個洲, 那麼許多金融機構和其他大型企業都有這麼做？</span><span class="sxs-lookup"><span data-stu-id="d556b-204">Calls to the PSTN are routed over the enterprise IP network to the gateways that are closest to the location of the destination numbers.But what if your organization supports dozens or hundreds or even thousands of sites spread across one or more continents, as many financial institutions and other large enterprises do?</span></span> <span data-ttu-id="d556b-205">在這種情況下, 在每個網站上部署個別的閘道並不是不切實際的。</span><span class="sxs-lookup"><span data-stu-id="d556b-205">In such cases, deploying a separate gateway at each site is not practical.</span></span>

<span data-ttu-id="d556b-206">若要解決此問題, 許多大型公司都想要部署一個或幾個大型電話中心網站。</span><span class="sxs-lookup"><span data-stu-id="d556b-206">To address this issue, many large companies prefer to deploy one or a few large telephony central sites.</span></span>

<span data-ttu-id="d556b-207">在這個拓朴中, 有幾個大型閘道足以容納預期的使用者負載, 就是在每一個中央網站部署。</span><span class="sxs-lookup"><span data-stu-id="d556b-207">In this topology, several large gateways sufficient to accommodate the anticipated user load are deployed at each central site.</span></span> <span data-ttu-id="d556b-208">企業中的所有使用者呼叫都是由公司的電話服務提供者轉寄至中心網站。</span><span class="sxs-lookup"><span data-stu-id="d556b-208">All calls to users in the enterprise are forwarded by the company's telephone service provider to a central site.</span></span> <span data-ttu-id="d556b-209">中央網站上的路由邏輯可決定是否要在內部網路或 PSTN 路由通話。</span><span class="sxs-lookup"><span data-stu-id="d556b-209">Routing logic at the central site determines whether the call should be routed over the intranet or to the PSTN.</span></span>

#### <a name="gateway-location"></a><span data-ttu-id="d556b-210">閘道位置</span><span class="sxs-lookup"><span data-stu-id="d556b-210">Gateway Location</span></span>

<span data-ttu-id="d556b-211">閘道位置也可以決定您選擇的閘道類型, 以及它們的設定方式。</span><span class="sxs-lookup"><span data-stu-id="d556b-211">Gateway location may also determine the types of gateways that you choose and how they are configured.</span></span> <span data-ttu-id="d556b-212">有許多 PSTN 通訊協定, 都不是世界標準。</span><span class="sxs-lookup"><span data-stu-id="d556b-212">There are dozens of PSTN protocols, none of which is a worldwide standard.</span></span> <span data-ttu-id="d556b-213">如果您的所有閘道都位於單一的國家/地區, 這不是問題, 但如果您在多個國家/地區中找到閘道, 則必須根據該國家/地區的 PSTN 標準進行設定。</span><span class="sxs-lookup"><span data-stu-id="d556b-213">If all your gateways are located in a single country/region, this is not an issue, but if you locate gateways in several countries/regions, each must be configured according to the PSTN standards of that country/region.</span></span> <span data-ttu-id="d556b-214">此外, 經認證的閘道 (例如加拿大), 可能無法在印度、巴西或歐盟進行認證。</span><span class="sxs-lookup"><span data-stu-id="d556b-214">Moreover, gateways that are certified for operation in, for example, Canada, may not be certified in India, Brazil, or the European Union.</span></span>

#### <a name="gateway-size-and-number"></a><span data-ttu-id="d556b-215">閘道大小與數位</span><span class="sxs-lookup"><span data-stu-id="d556b-215">Gateway Size and Number</span></span>

<span data-ttu-id="d556b-216">大多陣列織都要考慮部署範圍的 PSTN 閘道, 其大小必須是2到960埠。</span><span class="sxs-lookup"><span data-stu-id="d556b-216">The PSTN gateways that most organizations will consider deploying range in size from 2 to as many as 960 ports.</span></span> <span data-ttu-id="d556b-217">(甚至是更大的閘道, 但主要是由電話服務提供者使用。)估計貴組織所需的埠數時, 請遵循下列指導方針:</span><span class="sxs-lookup"><span data-stu-id="d556b-217">(There are even larger gateways, but these are used mainly by telephone service providers.) When estimating the number of ports your organization requires, use the following guidelines:</span></span>

- <span data-ttu-id="d556b-218">使用輕型電話使用的組織 (每個小時每個使用者一個 PSTN 通話) 應該為每15個使用者分配一個埠。</span><span class="sxs-lookup"><span data-stu-id="d556b-218">Organizations with light telephony usage (one PSTN call per user per hour) should allocate one port for every 15 users.</span></span> <span data-ttu-id="d556b-219">例如, 如果您有20個使用者, 就需要一個具有兩個埠的閘道。</span><span class="sxs-lookup"><span data-stu-id="d556b-219">For example, if you have 20 users, you will require a gateway with two ports.</span></span>

- <span data-ttu-id="d556b-220">具有中等電話使用方式 (每個使用者每小時兩個 PSTN 通話) 的組織應該為每10個使用者分配一個埠。</span><span class="sxs-lookup"><span data-stu-id="d556b-220">Organizations with moderate telephony usage (two PSTN calls per user per hour) should allocate one port for every 10 users.</span></span> <span data-ttu-id="d556b-221">例如, 如果您有100使用者, 您將需要在一或多個閘道間分配10個埠。</span><span class="sxs-lookup"><span data-stu-id="d556b-221">For example, if you have 100 users, you will require a total of 10 ports allocated among one or more gateways.</span></span>

- <span data-ttu-id="d556b-222">具有大量電話使用的組織 (每小時每位使用者有三個或更多個 PSTN 通話) 應該為每五位使用者指派一個埠。</span><span class="sxs-lookup"><span data-stu-id="d556b-222">Organizations with heavy telephony usage (three or more PSTN calls per user per hour) should allocate one port for every five users.</span></span> <span data-ttu-id="d556b-223">例如, 如果您有47000使用者, 您需要在至少10個大型閘道之間分配的9400埠總數。</span><span class="sxs-lookup"><span data-stu-id="d556b-223">For example, if you have 47,000 users, you will require a total of 9,400 ports allocated among at least 10 large gateways.</span></span>

- <span data-ttu-id="d556b-224">在貴組織中的使用者數目或流量增加時, 可以取得額外的埠。</span><span class="sxs-lookup"><span data-stu-id="d556b-224">Additional ports can be acquired as the number of users or amount of traffic in your organization increases.</span></span>

<span data-ttu-id="d556b-225">針對您必須支援的任何特定使用者數, 您可以選擇部署較少、較大的閘道或較小的閘道。</span><span class="sxs-lookup"><span data-stu-id="d556b-225">For any given number of users you must support, you have the choice of deploying fewer, larger gateways, or smaller ones.</span></span> <span data-ttu-id="d556b-226">就規則而言, 建議組織至少有兩個閘道, 才能在一個閘道失敗時維持可用性。</span><span class="sxs-lookup"><span data-stu-id="d556b-226">As a rule, a minimum of two gateways for an organization is recommended to maintain availability if one gateway fails.</span></span>

<span data-ttu-id="d556b-227">您部署的每個 PSTN 閘道都必須至少有一個相對應的產生轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="d556b-227">Each PSTN gateway that you deploy must have at least one corresponding Mediation Server.</span></span>


