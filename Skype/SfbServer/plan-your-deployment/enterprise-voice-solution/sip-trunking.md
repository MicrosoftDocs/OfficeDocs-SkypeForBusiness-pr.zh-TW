---
title: 商務用 Skype Server 中的 SIP 主幹
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
ms.assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
description: 深入瞭解商務用 Skype Server Enterprise Voice 中的 SIP 主幹
ms.openlocfilehash: dcfcf6d08b16f79c0985f337db68124442026bb1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802713"
---
# <a name="sip-trunking-in-skype-for-business-server"></a><span data-ttu-id="fba20-103">商務用 Skype Server 中的 SIP 主幹</span><span class="sxs-lookup"><span data-stu-id="fba20-103">SIP trunking in Skype for Business Server</span></span>

<span data-ttu-id="fba20-104">深入瞭解商務用 Skype Server Enterprise Voice 中的 SIP 主幹</span><span class="sxs-lookup"><span data-stu-id="fba20-104">Learn about SIP trunking in Skype for Business Server Enterprise Voice</span></span>

<span data-ttu-id="fba20-105">工作階段初始通訊協定 (SIP) 可用來為基本電話服務與其他即時通訊服務 (如立即訊息、會議、顯示狀態偵測和多媒體等) 啟動及管理 VoIP 通訊工作階段。</span><span class="sxs-lookup"><span data-stu-id="fba20-105">Session Initiation Protocol (SIP) is used to initiate and manage Voice over IP (VoIP) communications sessions for basic telephone service and for additional real-time communication services, such as instant messaging, conferencing, presence detection, and multimedia.</span></span> <span data-ttu-id="fba20-106">本節將提供實作「SIP 主幹」的規劃資訊，這是一種可延伸到您區域網路邊界以外的 SIP 連線。</span><span class="sxs-lookup"><span data-stu-id="fba20-106">This section provides planning information for implementing SIP trunks, a type of SIP connection that extends beyond the boundary of your local network.</span></span>

## <a name="what-is-sip-trunking"></a><span data-ttu-id="fba20-107">何謂 SIP 主幹？</span><span class="sxs-lookup"><span data-stu-id="fba20-107">What is SIP Trunking?</span></span>

<span data-ttu-id="fba20-108">SIP 主幹是一種 IP 連線，可在您的組織與網際網路電話語音服務提供者 (ITSP) 之間建立延伸到防火牆以外的 SIP 通訊連結。</span><span class="sxs-lookup"><span data-stu-id="fba20-108">A SIP trunk is an IP connection that establishes a SIP communications link between your organization and an Internet telephony service provider (ITSP) beyond your firewall.</span></span> <span data-ttu-id="fba20-109">通常，SIP 主幹是用來將組織的中央網站連線到 ITSP。</span><span class="sxs-lookup"><span data-stu-id="fba20-109">Typically, a SIP trunk is used to connect your organization's central site to an ITSP.</span></span> <span data-ttu-id="fba20-110">有時候，您也可能會選擇使用 SIP 主幹將分支網站連線至 ITSP。</span><span class="sxs-lookup"><span data-stu-id="fba20-110">In some cases, you may also opt to use SIP trunking to connect your branch site to an ITSP.</span></span>

<span data-ttu-id="fba20-111">部署 SIP 中繼可能是簡化組織之電信的重要步驟，並準備即時通訊的最新增強功能。</span><span class="sxs-lookup"><span data-stu-id="fba20-111">Deploying SIP trunking can be a big step toward simplifying your organization's telecommunications and preparing for up-to-date enhancements to real-time communications.</span></span> <span data-ttu-id="fba20-112">SIP 主幹的其中一個主要優點是，您可以將組織的連線整合至中央網站上的公用交換電話網路 (PSTN) ，而不是其前置任務、分複用 (TDM) 主幹，這通常需要每個分支網站的個別主幹。</span><span class="sxs-lookup"><span data-stu-id="fba20-112">One of the primary advantages of SIP trunking is that you can consolidate your organization's connections to the public switched telephone network (PSTN) at a central site, as opposed to its predecessor, time division multiplexing (TDM) trunking, which typically requires a separate trunk from each branch site.</span></span>

### <a name="cost-savings"></a><span data-ttu-id="fba20-113">節省成本</span><span class="sxs-lookup"><span data-stu-id="fba20-113">Cost Savings</span></span>

<span data-ttu-id="fba20-114">與 SIP 主幹相關聯的成本節約可能相當大：</span><span class="sxs-lookup"><span data-stu-id="fba20-114">The cost savings associated with SIP trunking can be substantial:</span></span>

- <span data-ttu-id="fba20-115">長途通話通常會透過 SIP 主幹降低成本。</span><span class="sxs-lookup"><span data-stu-id="fba20-115">Long distance calls typically cost much less through a SIP trunk.</span></span>

- <span data-ttu-id="fba20-116">您可以削減管理成本，並降低部署的複雜度。</span><span class="sxs-lookup"><span data-stu-id="fba20-116">You can cut manageability costs and reduce the complexity of deployment.</span></span>

- <span data-ttu-id="fba20-117">基本速率介面 (BRI) 和主要速率介面 (PRI) 費用，可在您將 SIP 主幹直接連接至您的 ITSP 時，降低成本。</span><span class="sxs-lookup"><span data-stu-id="fba20-117">Basic rate interface (BRI) and primary rate interface (PRI) fees can be eliminated if you connect a SIP trunk directly to your ITSP at significantly lower cost.</span></span> <span data-ttu-id="fba20-118">在 TDM trunk 中，服務提供者會在一分鐘內收取通話的費用。</span><span class="sxs-lookup"><span data-stu-id="fba20-118">In TDM trunking, service providers charge for calls by the minute.</span></span> <span data-ttu-id="fba20-119">SIP 主幹的成本可能是根據頻寬使用量而定，您可以更小、更經濟的增量購買。</span><span class="sxs-lookup"><span data-stu-id="fba20-119">The cost of SIP trunking may be based on bandwidth usage, which you can buy in smaller, more economical increments.</span></span> <span data-ttu-id="fba20-120"> (實際成本取決於您所選擇之 ITSP 的服務模型。 ) </span><span class="sxs-lookup"><span data-stu-id="fba20-120">(The actual cost depends on the service model of the ITSP you choose.)</span></span>

#### <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a><span data-ttu-id="fba20-121">與裝載 PSTN 閘道或 IP-PBX 的 SIP Trunk</span><span class="sxs-lookup"><span data-stu-id="fba20-121">SIP Trunking vs. Hosting a PSTN Gateway or IP-PBX</span></span>

<span data-ttu-id="fba20-122">由於 SIP 主幹直接連線至您的服務提供者，所以您可以省去您的 PSTN 閘道及其管理成本和複雜性。</span><span class="sxs-lookup"><span data-stu-id="fba20-122">Because SIP trunks connect directly to your service provider, you can eliminate your PSTN gateways and their management cost and complexity.</span></span> <span data-ttu-id="fba20-123">使用 SIP 主幹可縮短維護和管理，從而導致大量成本節約。</span><span class="sxs-lookup"><span data-stu-id="fba20-123">Using a SIP trunk can lead to substantial cost savings through reduced maintenance and administration.</span></span>

### <a name="expanded-voip-services"></a><span data-ttu-id="fba20-124">擴充的 VoIP 服務</span><span class="sxs-lookup"><span data-stu-id="fba20-124">Expanded VoIP Services</span></span>

<span data-ttu-id="fba20-125">語音功能常常是部署 SIP 主幹的主要動機，但語音支援只是第一步。</span><span class="sxs-lookup"><span data-stu-id="fba20-125">Voice features are often the primary motivation for deploying SIP trunking, but voice support is just the first step.</span></span> <span data-ttu-id="fba20-126">透過 SIP 主幹，您可以擴充 VoIP 功能，並啟用商務用 Skype 伺服器以傳遞一組更豐富的服務。</span><span class="sxs-lookup"><span data-stu-id="fba20-126">With SIP trunking, you can extend VoIP capabilities and enable Skype for Business Server to deliver a richer set of services.</span></span> <span data-ttu-id="fba20-127">例如：</span><span class="sxs-lookup"><span data-stu-id="fba20-127">For example:</span></span>

- <span data-ttu-id="fba20-128">未執行商務用 Skype Server 之裝置的增強顯示狀態偵測，可提供與行動電話的更好整合，讓您能看到使用者何時接聽行動電話。</span><span class="sxs-lookup"><span data-stu-id="fba20-128">Enhanced presence detection for devices that are not running Skype for Business Server can provide better integration with mobile phones, enabling you to see when a user is on a mobile phone call.</span></span>

- <span data-ttu-id="fba20-129">E9-1-1 緊急電話可讓接聽911呼叫的授權者判斷來電者的電話號碼的位置。</span><span class="sxs-lookup"><span data-stu-id="fba20-129">E9-1-1 emergency calling enables the authorities who answer 911 calls to determine the caller's location from his or her telephone number.</span></span>

> [!NOTE]
> <span data-ttu-id="fba20-130">請與您的 ITSP 取得支援的服務清單，並可為您的組織啟用這些服務。</span><span class="sxs-lookup"><span data-stu-id="fba20-130">Contact your ITSP for a list of services that they support and can enable for your organization.</span></span>

### <a name="sip-trunks-vs-direct-sip-connections"></a><span data-ttu-id="fba20-131">SIP 主幹與直接 SIP 連線的比較</span><span class="sxs-lookup"><span data-stu-id="fba20-131">SIP Trunks vs. Direct SIP Connections</span></span>

<span data-ttu-id="fba20-132">「主幹」一詞衍生自電路交換技術。</span><span class="sxs-lookup"><span data-stu-id="fba20-132">The term trunk is derived from circuit-switched technology.</span></span> <span data-ttu-id="fba20-133">它是指將電話交換設備相連的專門實體線路。</span><span class="sxs-lookup"><span data-stu-id="fba20-133">It refers to a dedicated physical line that connects telephone switching equipment.</span></span> <span data-ttu-id="fba20-134">像是其前置任務、時間分割多工 (TDM) 主幹、SIP 主幹是兩個不同 SIP 網路（商務用 Skype Server enterprise 和 ITSP）之間的連線。</span><span class="sxs-lookup"><span data-stu-id="fba20-134">Like their predecessor, time division multiplexing (TDM) trunks, SIP trunks are connections between two separate SIP networks—the Skype for Business Server enterprise and the ITSP.</span></span> <span data-ttu-id="fba20-135">與電路交換主幹不同之處在於，SIP 主幹是可以透過任何支援的 SIP 主幹連線類型建立的虛擬連線。</span><span class="sxs-lookup"><span data-stu-id="fba20-135">Unlike circuit-switched trunks, SIP trunks are virtual connections that can be established over any of the supported SIP trunking connection types.</span></span>

<span data-ttu-id="fba20-136">另一方面，直接 SIP 連線是未穿越區域網路邊界的 SIP 連線 (亦即，它們是連線至位於您內部網路中的公用交換電話網路 (PSTN) 閘道或專用交換機 (PBX))。</span><span class="sxs-lookup"><span data-stu-id="fba20-136">Direct SIP connections, on the other hand, are SIP connections that do not cross the local network boundary (that is, they connect to a public switched telephone network (PSTN) gateway or private branch exchange (PBX) within your internal network).</span></span> <span data-ttu-id="fba20-137">如需如何使用與商務用 Skype Server 的直接 SIP 連線的詳細資訊，請參閱 [商務用 Skype server 中的直接 sip](direct-sip.md)連線。</span><span class="sxs-lookup"><span data-stu-id="fba20-137">For details about how you can use direct SIP connections with Skype for Business Server, see [Direct SIP connections in Skype for Business Server](direct-sip.md).</span></span>

## <a name="how-do-i-implement-sip-trunking"></a><span data-ttu-id="fba20-138">如何執行 SIP 主幹？</span><span class="sxs-lookup"><span data-stu-id="fba20-138">How do I implement SIP Trunking?</span></span>

<span data-ttu-id="fba20-139">若要執行 SIP 主幹，您必須透過轉送伺服器路由傳送，該伺服器可充當商務用 Skype Server 用戶端與服務提供者和 transcodes 媒體（必要時）之間的通訊會話 proxy。</span><span class="sxs-lookup"><span data-stu-id="fba20-139">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Skype for Business Server clients and the service provider and transcodes media, when necessary.</span></span>

<span data-ttu-id="fba20-140">每個轉送伺服器都具有內部網路介面和外部網路介面。</span><span class="sxs-lookup"><span data-stu-id="fba20-140">Each Mediation Server has an internal network interface and an external network interface.</span></span> <span data-ttu-id="fba20-141">內部介面連接至前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="fba20-141">The internal interface connects to the Front End Servers.</span></span> <span data-ttu-id="fba20-142">外部介面一般稱為閘道介面，因為傳統上它是用來將轉送伺服器連接到公用交換電話網路 (PSTN) 閘道或 IP-PBX。</span><span class="sxs-lookup"><span data-stu-id="fba20-142">The external interface is commonly called the gateway interface because it has traditionally been used to connect the Mediation Server to a public switched telephone network (PSTN) gateway or an IP-PBX.</span></span> <span data-ttu-id="fba20-143">若要執行 SIP 主幹，您可以將轉送伺服器的外部介面連接至 ITSP 的外部 edge 元件。</span><span class="sxs-lookup"><span data-stu-id="fba20-143">To implement a SIP trunk, you connect the external interface of the Mediation Server to the external edge component of the ITSP.</span></span> <span data-ttu-id="fba20-144">ITSP 的外部 Edge 元件可以是工作階段界限控制器 (SBC)、路由器或閘道。</span><span class="sxs-lookup"><span data-stu-id="fba20-144">The external edge component of the ITSP could be a Session Border Controller (SBC), a router, or a gateway.</span></span>

<span data-ttu-id="fba20-145">如需轉送伺服器的詳細資訊，請參閱 lync [server component In 商務用 Skype server](mediation-server.md)。</span><span class="sxs-lookup"><span data-stu-id="fba20-145">For details about Mediation Servers, see [Mediation Server component in Skype for Business Server](mediation-server.md).</span></span>

### <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="fba20-146">集中式與分散式 SIP 主幹的比較</span><span class="sxs-lookup"><span data-stu-id="fba20-146">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="fba20-147">集中式 SIP 中繼會透過您的中央網站路由傳送所有 VoIP 流量，包括分支網站流量。</span><span class="sxs-lookup"><span data-stu-id="fba20-147">Centralized SIP trunking routes all VoIP traffic, including branch site traffic, through your central site.</span></span> <span data-ttu-id="fba20-148">集中式部署模型是簡單、經濟划算的，通常是以商務用 Skype Server 實施 SIP 主幹的建議方法。</span><span class="sxs-lookup"><span data-stu-id="fba20-148">The centralized deployment model is simple, cost-effective, and is generally the recommended approach for implementing SIP trunks with Skype for Business Server.</span></span>

<span data-ttu-id="fba20-149">分散式 SIP 主幹是一種部署模型，您可以在其中執行一或多個分支網站上的本機 SIP 主幹。</span><span class="sxs-lookup"><span data-stu-id="fba20-149">Distributed SIP trunking is a deployment model in which you implement local SIP trunks at one or more branch sites.</span></span> <span data-ttu-id="fba20-150">VoIP 流量會從分支網站直接路由傳送至服務提供者，而不需要透過中央網站。</span><span class="sxs-lookup"><span data-stu-id="fba20-150">VoIP traffic is then routed from the branch site directly to a service provider without going through the central site.</span></span>

<span data-ttu-id="fba20-151">只有下列情況才必須使用分散式 SIP 主幹：</span><span class="sxs-lookup"><span data-stu-id="fba20-151">Distributed SIP trunking is required only in the following cases:</span></span>

- <span data-ttu-id="fba20-152">分支網站需要 survivable phone connectivity (例如，如果 WAN 停機) 。</span><span class="sxs-lookup"><span data-stu-id="fba20-152">The branch site requires survivable phone connectivity (for example, if the WAN goes down).</span></span> <span data-ttu-id="fba20-153">應該針對每個分支網站來分析此需求;您的部分分支可能需要冗余和容錯移轉，但其他分支可能不需要。</span><span class="sxs-lookup"><span data-stu-id="fba20-153">This requirement should be analyzed for each branch site; some of your branches may require redundancy and failover, whereas others may not.</span></span>

- <span data-ttu-id="fba20-154">兩部中央網站之間需要恢復功能。</span><span class="sxs-lookup"><span data-stu-id="fba20-154">Resiliency is required between two central sites.</span></span> <span data-ttu-id="fba20-155">您必須確定 SIP 主幹會在每個中央網站終止。</span><span class="sxs-lookup"><span data-stu-id="fba20-155">You need to make sure that a SIP trunk terminates at each central site.</span></span> <span data-ttu-id="fba20-156">例如，如果您有都柏林和 Tukwila 中央網站，且兩者都只使用一個網站的 SIP 主幹，如果主幹中斷，其他網站的使用者將無法進行 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="fba20-156">For example, if you have Dublin and Tukwila central sites and both use only one site's SIP trunk, if the trunk goes down, the other site's users cannot make PSTN calls.</span></span>

- <span data-ttu-id="fba20-157">分支網站與中央網站位於不同的國家/地區。</span><span class="sxs-lookup"><span data-stu-id="fba20-157">The branch site and central site are in different countries/regions.</span></span> <span data-ttu-id="fba20-158">基於相容性與法規考量，每個國家/地區至少要有一個 SIP 主幹。</span><span class="sxs-lookup"><span data-stu-id="fba20-158">For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span> <span data-ttu-id="fba20-159">以歐盟地區為例，若未在中心點上進行本機終止，通訊就只能侷限在國家/地區的範圍。</span><span class="sxs-lookup"><span data-stu-id="fba20-159">For example, in the European Union, communications cannot leave a country/region without terminating locally at a centralized point.</span></span>

<span data-ttu-id="fba20-160">根據網站的地理位置和您在企業中預期的流量，您可能不想要透過中央 SIP 主幹路由傳送所有使用者，或者您可以選擇透過分支網站的 SIP 主幹路由傳送部分使用者。</span><span class="sxs-lookup"><span data-stu-id="fba20-160">Depending on the geographical location of sites and how much traffic you anticipate within your enterprise, you may not want to route all users through the central SIP trunk, or you may opt to route some users through a SIP trunk at their branch site.</span></span> <span data-ttu-id="fba20-161">若要分析自身需求，請回答下列問題：</span><span class="sxs-lookup"><span data-stu-id="fba20-161">To analyze your needs, answer the following questions:</span></span>

- <span data-ttu-id="fba20-162">每個網站有多大 (，也就是有多少使用者已啟用企業語音) ？</span><span class="sxs-lookup"><span data-stu-id="fba20-162">How big is each site (that is, how many users are enabled for Enterprise Voice)?</span></span>

- <span data-ttu-id="fba20-163">各網站上的哪些直接向內撥號 (DID) 號碼來電數最多？</span><span class="sxs-lookup"><span data-stu-id="fba20-163">Which direct inward dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="fba20-164">在考量應部署集中式或分散式 SIP 主幹時，必須進行成本效益分析。</span><span class="sxs-lookup"><span data-stu-id="fba20-164">The decision whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis.</span></span> <span data-ttu-id="fba20-165">在某些情況下，即便並非必要，選擇分散式部署模型可能較有利。</span><span class="sxs-lookup"><span data-stu-id="fba20-165">In some cases, it may be advantageous to opt for the distributed deployment model even if it is not required.</span></span> <span data-ttu-id="fba20-166">在完整的集中式部署中，所有分支網站流量都透過 WAN 連結路由傳送。</span><span class="sxs-lookup"><span data-stu-id="fba20-166">In a completely centralized deployment, all branch site traffic is routed over WAN links.</span></span> <span data-ttu-id="fba20-167">與其為 WAN 連結所需的頻寬支付高額費用，您可能寧可使用分散式 SIP 主幹。</span><span class="sxs-lookup"><span data-stu-id="fba20-167">Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span> <span data-ttu-id="fba20-168">例如，您可能想要在具有同盟的中央網站的分支網站上部署 Standard Edition server，或使用小型閘道部署 Survivable Branch 裝置或 Survivable Branch Server。</span><span class="sxs-lookup"><span data-stu-id="fba20-168">For example, you may want to deploy a Standard Edition server at a branch site with federation to the central site, or you may want to deploy a Survivable Branch Appliance or a Survivable Branch Server with a small gateway.</span></span>

> [!NOTE]
> <span data-ttu-id="fba20-169">如需有關分散式 SIP 主幹的詳細資訊，請參閱 [在商務用 Skype Server 中的分支網站 SIP trunk](branch-site.md)。</span><span class="sxs-lookup"><span data-stu-id="fba20-169">For details about distributed SIP trunking, see [Branch site SIP trunking in Skype for Business Server](branch-site.md).</span></span>

### <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="fba20-170">支援的 SIP 主幹連線類型</span><span class="sxs-lookup"><span data-stu-id="fba20-170">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="fba20-171">商務用 Skype 伺服器支援 SIP 主幹的下列連線類型：</span><span class="sxs-lookup"><span data-stu-id="fba20-171">Skype for Business Server supports the following connection types for SIP trunking:</span></span>

- <span data-ttu-id="fba20-172">Multiprotocol Label Switching (MPLS) 是可將資料從一個網路節點導向及承載到另一個網路節點的私人網路。</span><span class="sxs-lookup"><span data-stu-id="fba20-172">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next.</span></span> <span data-ttu-id="fba20-173">MPLS 網路中的頻寬是與其他訂閱者共用的，而每封資料包都會被指派標籤，以辨別來自另一位訂閱者的資料。</span><span class="sxs-lookup"><span data-stu-id="fba20-173">The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber's data from another's.</span></span> <span data-ttu-id="fba20-174">此連線類型不需要虛擬私人網路 (VPN)。</span><span class="sxs-lookup"><span data-stu-id="fba20-174">This connection type does not require a virtual private network (VPN).</span></span> <span data-ttu-id="fba20-175">可能的缺點是，過多的 IP 流量可能會干擾 VoIP 作業，除非 VoIP 流量享有優先權。</span><span class="sxs-lookup"><span data-stu-id="fba20-175">A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

- <span data-ttu-id="fba20-p118">不含其他流量的私人連線 (例如租用的光纖連線或 T1 線路) 通常會是最可靠而安全的連線類型。此連線類型可提供最高的通話承載能力，但通常也最昂貴。此連線類型不需要 VPN。私人連線適用於通話量大或安全性與可用性需求很高的組織。</span><span class="sxs-lookup"><span data-stu-id="fba20-p118">A private connection with no other traffic—for example, a leased fiber-optic connection or T1 line—is typically the most reliable and secure connection type. This connection type provides the highest call-carrying capacity, but it is typically the most expensive. VPN is not required. Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

- <span data-ttu-id="fba20-180">網際網路是最經濟的連線類型，但可靠性也最低。</span><span class="sxs-lookup"><span data-stu-id="fba20-180">The Internet is the least expensive connection type, but it is also the least reliable.</span></span> <span data-ttu-id="fba20-181">Internet connection 是唯一需要 VPN 的商務用 Skype Server SIP 主幹連線類型。</span><span class="sxs-lookup"><span data-stu-id="fba20-181">Internet connection is the only Skype for Business Server SIP trunking connection type that requires VPN.</span></span>

#### <a name="selecting-a-connection-type"></a><span data-ttu-id="fba20-182">選取連線類型</span><span class="sxs-lookup"><span data-stu-id="fba20-182">Selecting a Connection Type</span></span>

<span data-ttu-id="fba20-183">您的企業最適合使用的 SIP 主幹連線類型，端視您的需求與預算而定。</span><span class="sxs-lookup"><span data-stu-id="fba20-183">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

- <span data-ttu-id="fba20-p120">對中型或較大的企業而言，MPLS 網路通常能提供最大的效益。它可以低於特殊私人網路的費率提供所需的頻寬。</span><span class="sxs-lookup"><span data-stu-id="fba20-p120">For a mid-size or larger enterprise, an MPLS network usually provides the greatest value. It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

- <span data-ttu-id="fba20-186">大型企業可能需要私人光纖連線、T1、T3 或更高階的連線 (歐盟地區為 E1、E3 或更高階連線)。</span><span class="sxs-lookup"><span data-stu-id="fba20-186">Large enterprises may require a private fiber-optic, T1, T3 or higher connection (E1, E3 or higher in the European Union).</span></span>

- <span data-ttu-id="fba20-187">對於具有低通話數量的小型企業或分支網站，透過網際網路的 SIP 主幹可能是最佳選擇。</span><span class="sxs-lookup"><span data-stu-id="fba20-187">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice.</span></span> <span data-ttu-id="fba20-188">不建議中型或較大的網站使用此連線類型。</span><span class="sxs-lookup"><span data-stu-id="fba20-188">This connection type is not recommended for mid-size or larger sites.</span></span>

### <a name="bandwidth-requirements"></a><span data-ttu-id="fba20-189">頻寬需求</span><span class="sxs-lookup"><span data-stu-id="fba20-189">Bandwidth Requirements</span></span>

<span data-ttu-id="fba20-p122">您的實作所需的頻寬量，取決於您的話務量 (您必須能夠支援的並行通話數量)。您必須將頻寬可用性納入考量，以充分使用您花錢購買的最大容量。您可以使用下列公式計算 SIP 主幹的最大頻寬需求：</span><span class="sxs-lookup"><span data-stu-id="fba20-p122">The amount of bandwidth your implementation requires depends on call capacity (the number of concurrent calls you must be able to support). You need to consider bandwidth availability, so that you can take full advantage of the peak capacity that you have paid for. Use the following formula to calculate SIP trunk peak bandwidth requirement:</span></span>

<span data-ttu-id="fba20-193">SIP 主幹最大頻寬 = 同時通話數上限 x (64 kbps + 標頭大小)</span><span class="sxs-lookup"><span data-stu-id="fba20-193">SIP Trunk Peak Bandwidth = Max Simultaneous Calls x (64 kbps + header size)</span></span>

> [!NOTE]
> <span data-ttu-id="fba20-194">標頭大小上限為 20 個位元組。</span><span class="sxs-lookup"><span data-stu-id="fba20-194">Header size is 20 bytes maximum.</span></span>

### <a name="codec-support"></a><span data-ttu-id="fba20-195">轉碼器支援</span><span class="sxs-lookup"><span data-stu-id="fba20-195">Codec Support</span></span>

<span data-ttu-id="fba20-196">商務用 Skype 伺服器只支援下列編解碼器：</span><span class="sxs-lookup"><span data-stu-id="fba20-196">Skype for Business Server supports only the following codecs:</span></span>

- <span data-ttu-id="fba20-197">G.711 a-law (主要使用於北美以外的地區)</span><span class="sxs-lookup"><span data-stu-id="fba20-197">G.711 a-law (used primarily outside North America)</span></span>

- <span data-ttu-id="fba20-198">G.711 µ-law (使用於北美地區)</span><span class="sxs-lookup"><span data-stu-id="fba20-198">G.711 µ-law (used in North America)</span></span>

### <a name="internet-telephony-service-provider"></a><span data-ttu-id="fba20-199">網際網路電話語音服務提供者</span><span class="sxs-lookup"><span data-stu-id="fba20-199">Internet Telephony Service Provider</span></span>

<span data-ttu-id="fba20-200">SIP 主幹連線之服務提供者端的實作方式，會根據 ITSP 而不同。</span><span class="sxs-lookup"><span data-stu-id="fba20-200">How you implement the service provider side of a SIP trunk connection varies from one ITSP to another.</span></span> <span data-ttu-id="fba20-201">如需部署資訊，請連絡服務提供者。</span><span class="sxs-lookup"><span data-stu-id="fba20-201">For deployment information, contact your service provider.</span></span> <span data-ttu-id="fba20-202">如需認證 SIP 主幹服務提供者的清單，請參閱 [Microsoft 整合通訊開啟互通性計畫網站](https://go.microsoft.com/fwlink/p/?LinkId=287029)。</span><span class="sxs-lookup"><span data-stu-id="fba20-202">For a list of certified SIP trunking service providers, see [Microsoft Unified Communications Open Interoperability Program website](https://go.microsoft.com/fwlink/p/?LinkId=287029).</span></span>

<span data-ttu-id="fba20-203">如需 Microsoft 認證 SIP 主幹提供者的詳細資訊，請連絡 Microsoft 代表。</span><span class="sxs-lookup"><span data-stu-id="fba20-203">For details about Microsoft certified SIP trunking providers, contact your Microsoft representative.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fba20-p124">您必須使用 Microsoft 認證服務提供者，以確定 ITSP 支援所有周遊 SIP 主幹的功能 (例如，設定和管理工作階段，以及支援所有延伸的 VoIP 服務)。Microsoft 技術支援未延伸至使用非認證提供者的設定。如果您目前使用未獲得 SIP 主幹認證的網際網路服務提供者，則可以選擇繼續使用該提供者做為 ISP，並使用 Microsoft 認證的提供者進行 SIP 主幹作業。</span><span class="sxs-lookup"><span data-stu-id="fba20-p124">You must use a Microsoft certified service provider to ensure that your ITSP supports all of the functionality that traverses the SIP trunk (for example, setting up and managing sessions and supporting all of the extended VoIP services). Microsoft technical support does not extend to configurations that use noncertified providers. If you currently use an Internet service provider that is not certified for SIP trunking, you can opt to continue using that provider as your ISP and use a provider certified by Microsoft for SIP trunking.</span></span>

### <a name="topologies-and-components-for-sip-trunking"></a><span data-ttu-id="fba20-207">SIP 主幹的拓撲與元件</span><span class="sxs-lookup"><span data-stu-id="fba20-207">Topologies and Components for SIP Trunking</span></span>

<span data-ttu-id="fba20-208">下圖描述商務用 Skype Server 中的 SIP 主幹拓撲。</span><span class="sxs-lookup"><span data-stu-id="fba20-208">The following figure depicts the SIP trunking topology in Skype for Business Server.</span></span>

<span data-ttu-id="fba20-209">**SIP 主幹拓撲**</span><span class="sxs-lookup"><span data-stu-id="fba20-209">**SIP trunking topology**</span></span>

![SIP 主幹拓撲](../../media/669fb55d-7c81-4e21-9421-fabc43d6e064.jpg)

<span data-ttu-id="fba20-211">如圖所示，在商業網路和公用交換電話網路 (PSTN) 服務提供者之間的連線中，會使用 IP 虛擬私人網路 (VPN) 。</span><span class="sxs-lookup"><span data-stu-id="fba20-211">As shown in the diagram, an IP virtual private network (VPN) is used for connectivity between the enterprise network and the public switched telephone network (PSTN) service provider.</span></span> <span data-ttu-id="fba20-212">此私人網路的目的在於提供 IP 連線功能、增強安全性，以及 (選擇性) 取得服務品質 (QoS) 保證。</span><span class="sxs-lookup"><span data-stu-id="fba20-212">The purpose of this private network is to provide IP connectivity, enhance security, and (optionally) obtain Quality of Service (QoS) guarantees.</span></span> <span data-ttu-id="fba20-213">由於 VPN 的性質，您不需要使用傳輸層安全性 (TLS) 以進行 SIP 信號流量或安全即時傳輸通訊協定 (SRTP) 的媒體流量。</span><span class="sxs-lookup"><span data-stu-id="fba20-213">Because of the nature of a VPN, you do not need to use Transport Layer Security (TLS) for SIP signaling traffic or secure real-time transport protocol (SRTP) for the media traffic.</span></span> <span data-ttu-id="fba20-214">企業和服務提供者之間的連線是由 SIP 和即時即時傳輸通訊協定的純 TCP 連線所組成 (RTP)  (透過 UDP) 透過 IP VPN 傳送媒體隧道。</span><span class="sxs-lookup"><span data-stu-id="fba20-214">Connections between the enterprise and the service provider therefore consist of plain TCP connections for SIP and plain real-time transport protocol (RTP) (over UDP) for media tunneled through an IP VPN.</span></span> <span data-ttu-id="fba20-215">確定所有 VPN 路由器間的防火牆皆已開啟埠，以允許 VPN 路由器通訊，而且 VPN 路由器外部邊緣的 IP 位址可公開路由傳送。</span><span class="sxs-lookup"><span data-stu-id="fba20-215">Ensure that all firewalls between the VPN routers have ports open to allow the VPN routers to communicate, and that the IP addresses on the external edges of the VPN routers are publicly routable.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fba20-216">請與您的服務提供者聯繫，以判斷其是否提供高可用性支援（包括容錯移轉）。</span><span class="sxs-lookup"><span data-stu-id="fba20-216">Contact your service provider to determine whether it provides support for high availability, including failover.</span></span> <span data-ttu-id="fba20-217">如果是的話，您將需要決定設定的程式。</span><span class="sxs-lookup"><span data-stu-id="fba20-217">If so, you will need to determine the procedures for setting it up.</span></span> <span data-ttu-id="fba20-218">例如，您只需要在每個轉送伺服器上設定一個 IP 位址和一個 SIP 主幹，還是需要在每個轉送伺服器上設定多個 SIP 主幹？</span><span class="sxs-lookup"><span data-stu-id="fba20-218">For example, do you need to configure only one IP address and one SIP trunk on each Mediation Server, or do you need to configure multiple SIP trunks on each Mediation Server?</span></span> <span data-ttu-id="fba20-219">> 如果您有多部中央網站，也請詢問服務提供者是否有能力啟用與其他中央網站之間的連線。</span><span class="sxs-lookup"><span data-stu-id="fba20-219">> If you have multiple central sites, also ask whether the service provider has the ability to enable connections to and from another central site.</span></span>

> [!NOTE]
> <span data-ttu-id="fba20-220">若為 SIP 主幹，強烈建議您部署獨立的轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="fba20-220">For SIP trunking, we strongly recommend that you deploy stand-alone Mediation Servers.</span></span> <span data-ttu-id="fba20-221">如需詳細資訊，請參閱部署檔中的 [部署轉送伺服器及定義對等](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx) 專案。</span><span class="sxs-lookup"><span data-stu-id="fba20-221">For details, see [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx) in the Deployment documentation.</span></span>

### <a name="securing-the-mediation-server-for-sip-trunking"></a><span data-ttu-id="fba20-222">保護 SIP 中繼的轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="fba20-222">Securing the Mediation Server for SIP Trunking</span></span>

<span data-ttu-id="fba20-223">基於安全性的考慮，您應該為兩個 VPN 路由器間的每個連線設定虛擬 LAN (VLAN) 。</span><span class="sxs-lookup"><span data-stu-id="fba20-223">For security purposes, you should set up a virtual LAN (VLAN) for each connection between the two VPN routers.</span></span> <span data-ttu-id="fba20-224">安裝 VLAN 的實際程式會因不同的路由器製造商而異。</span><span class="sxs-lookup"><span data-stu-id="fba20-224">The actual process for setting up a VLAN varies from one router manufacturer to another.</span></span> <span data-ttu-id="fba20-225">如需詳細資訊，請與您的路由器廠商聯繫。</span><span class="sxs-lookup"><span data-stu-id="fba20-225">For details, contact your router vendor.</span></span>

<span data-ttu-id="fba20-226">建議您遵循這些方針：</span><span class="sxs-lookup"><span data-stu-id="fba20-226">We recommend that you follow these guidelines:</span></span>

- <span data-ttu-id="fba20-227">在周邊網路中的轉送伺服器和 VPN 路由器之間設定虛擬 LAN (VLAN)  (也稱為 DMZ、隔離區域和遮罩式子網) 。</span><span class="sxs-lookup"><span data-stu-id="fba20-227">Set up a virtual LAN (VLAN) between the Mediation Server and the VPN router in the perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span>

- <span data-ttu-id="fba20-228">不允許從路由器將廣播或多播封包傳輸至 VLAN。</span><span class="sxs-lookup"><span data-stu-id="fba20-228">Do not allow broadcast or multicast packets to be transferred from the router to the VLAN.</span></span>

- <span data-ttu-id="fba20-229">封鎖將流量從路由器路由傳送至任何地方（轉送伺服器）的路由規則。</span><span class="sxs-lookup"><span data-stu-id="fba20-229">Block any routing rules that route traffic from the router to anywhere but the Mediation Server.</span></span>

<span data-ttu-id="fba20-230">如果您使用 VPN 伺服器，我們建議您遵循下列指導方針：</span><span class="sxs-lookup"><span data-stu-id="fba20-230">If you use a VPN server, we recommend that you follow these guidelines:</span></span>

- <span data-ttu-id="fba20-231">在 VPN 伺服器與轉送伺服器之間設定 VLAN。</span><span class="sxs-lookup"><span data-stu-id="fba20-231">Set up a VLAN between the VPN server and the Mediation Server.</span></span>

- <span data-ttu-id="fba20-232">不允許從 VPN 伺服器將廣播或多播封包傳輸至 VLAN。</span><span class="sxs-lookup"><span data-stu-id="fba20-232">Do not allow broadcast or multicast packets to be transmitted from the VPN server to the VLAN.</span></span>

- <span data-ttu-id="fba20-233">封鎖將 VPN 伺服器流量路由傳送至任何無所不在（轉送伺服器）的路由規則。</span><span class="sxs-lookup"><span data-stu-id="fba20-233">Block any routing rule that routes VPN server traffic to anywhere but the Mediation Server.</span></span>

- <span data-ttu-id="fba20-234">使用一般路由封裝 (GRE) ，加密 VPN 上的資料。</span><span class="sxs-lookup"><span data-stu-id="fba20-234">Encrypt data on the VPN by using generic routing encapsulation (GRE).</span></span>

## <a name="see-also"></a><span data-ttu-id="fba20-235">另請參閱</span><span class="sxs-lookup"><span data-stu-id="fba20-235">See also</span></span>

[<span data-ttu-id="fba20-236">商務用 Skype Server 中的分支網站 SIP 主幹</span><span class="sxs-lookup"><span data-stu-id="fba20-236">Branch site SIP trunking in Skype for Business Server</span></span>](branch-site.md)

