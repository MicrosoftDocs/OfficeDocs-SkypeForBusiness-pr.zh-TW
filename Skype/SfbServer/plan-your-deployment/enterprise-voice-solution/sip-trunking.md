---
title: 商務用 Skype Server 中的 SIP 中繼
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 瞭解商務用 Skype Server 中的 SIP 中繼企業版語音
ms.openlocfilehash: 229774ef976a08031da7892dec0088d78b954b24
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802413"
---
# <a name="sip-trunking-in-skype-for-business-server"></a><span data-ttu-id="0d8fd-103">商務用 Skype Server 中的 SIP 中繼</span><span class="sxs-lookup"><span data-stu-id="0d8fd-103">SIP trunking in Skype for Business Server</span></span>

<span data-ttu-id="0d8fd-104">瞭解商務用 Skype Server 中的 SIP 中繼企業版語音</span><span class="sxs-lookup"><span data-stu-id="0d8fd-104">Learn about SIP trunking in Skype for Business Server Enterprise Voice</span></span>

<span data-ttu-id="0d8fd-105">會話初始通訊協定（SIP）是用來啟動及管理基本電話語音的語音 IP （VoIP）通訊會話，以及其他即時通訊服務，例如立即訊息、會議、目前狀態偵測及彩信.</span><span class="sxs-lookup"><span data-stu-id="0d8fd-105">Session Initiation Protocol (SIP) is used to initiate and manage Voice over IP (VoIP) communications sessions for basic telephone service and for additional real-time communication services, such as instant messaging, conferencing, presence detection, and multimedia.</span></span> <span data-ttu-id="0d8fd-106">本節提供有關實現 SIP trunks 的規劃資訊，這種類型的 SIP 連線延伸到您的本機網路邊界以外。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-106">This section provides planning information for implementing SIP trunks, a type of SIP connection that extends beyond the boundary of your local network.</span></span>

## <a name="what-is-sip-trunking"></a><span data-ttu-id="0d8fd-107">什麼是 SIP 中繼？</span><span class="sxs-lookup"><span data-stu-id="0d8fd-107">What is SIP Trunking?</span></span>

<span data-ttu-id="0d8fd-108">SIP 幹線是一種 IP 連線，可在您的組織與防火牆以外的網際網路電話服務提供者（ITSP）之間建立 SIP 通訊連結。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-108">A SIP trunk is an IP connection that establishes a SIP communications link between your organization and an Internet telephony service provider (ITSP) beyond your firewall.</span></span> <span data-ttu-id="0d8fd-109">通常，SIP 幹線是用來將貴組織的中心網站連線至 ITSP。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-109">Typically, a SIP trunk is used to connect your organization's central site to an ITSP.</span></span> <span data-ttu-id="0d8fd-110">在某些情況下，您也可以選擇使用 SIP 中繼將分支網站連線至 ITSP。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-110">In some cases, you may also opt to use SIP trunking to connect your branch site to an ITSP.</span></span>

<span data-ttu-id="0d8fd-111">部署 SIP 中繼可能是簡化貴組織的電訊，並準備最新的即時通訊功能的重要步驟。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-111">Deploying SIP trunking can be a big step toward simplifying your organization's telecommunications and preparing for up-to-date enhancements to real-time communications.</span></span> <span data-ttu-id="0d8fd-112">SIP 中繼的主要優點之一是，您可以將貴組織的連線到中央網站的公用交換電話網絡（PSTN），而不是其前置任務、時間單位複用（TDM）中繼（通常是需要來自每個分支網站的個別幹線。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-112">One of the primary advantages of SIP trunking is that you can consolidate your organization's connections to the public switched telephone network (PSTN) at a central site, as opposed to its predecessor, time division multiplexing (TDM) trunking, which typically requires a separate trunk from each branch site.</span></span>

### <a name="cost-savings"></a><span data-ttu-id="0d8fd-113">成本節約</span><span class="sxs-lookup"><span data-stu-id="0d8fd-113">Cost Savings</span></span>

<span data-ttu-id="0d8fd-114">與 SIP 中繼相關的成本節約可能相當重要：</span><span class="sxs-lookup"><span data-stu-id="0d8fd-114">The cost savings associated with SIP trunking can be substantial:</span></span>

- <span data-ttu-id="0d8fd-115">遠距離通話通常會透過 SIP 幹線降低成本。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-115">Long distance calls typically cost much less through a SIP trunk.</span></span>

- <span data-ttu-id="0d8fd-116">您可以削減易管理性成本，並減少部署的複雜性。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-116">You can cut manageability costs and reduce the complexity of deployment.</span></span>

- <span data-ttu-id="0d8fd-117">如果您將 SIP 主幹直接連線至 ITSP，成本較低，就可以消除基本比率介面（BRI）和主要比率介面（PRI）費用。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-117">Basic rate interface (BRI) and primary rate interface (PRI) fees can be eliminated if you connect a SIP trunk directly to your ITSP at significantly lower cost.</span></span> <span data-ttu-id="0d8fd-118">在 TDM 中繼中，服務提供者會以分鐘為通話付費。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-118">In TDM trunking, service providers charge for calls by the minute.</span></span> <span data-ttu-id="0d8fd-119">SIP 中繼的成本可能是以頻寬使用量為基礎，您可以使用較小的增量來購買。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-119">The cost of SIP trunking may be based on bandwidth usage, which you can buy in smaller, more economical increments.</span></span> <span data-ttu-id="0d8fd-120">（實際成本取決於您所選擇之 ITSP 的服務模型。）</span><span class="sxs-lookup"><span data-stu-id="0d8fd-120">(The actual cost depends on the service model of the ITSP you choose.)</span></span>

#### <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a><span data-ttu-id="0d8fd-121">SIP 中繼與託管 PSTN 閘道或 IP PBX</span><span class="sxs-lookup"><span data-stu-id="0d8fd-121">SIP Trunking vs. Hosting a PSTN Gateway or IP-PBX</span></span>

<span data-ttu-id="0d8fd-122">因為 SIP trunks 直接連線至您的服務提供者，所以您可以消除 PSTN 閘道及其管理成本與複雜性。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-122">Because SIP trunks connect directly to your service provider, you can eliminate your PSTN gateways and their management cost and complexity.</span></span> <span data-ttu-id="0d8fd-123">使用 SIP 幹線，只需要減少維護與管理，即可帶來巨大的成本節約。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-123">Using a SIP trunk can lead to substantial cost savings through reduced maintenance and administration.</span></span>

### <a name="expanded-voip-services"></a><span data-ttu-id="0d8fd-124">擴充的 VoIP 服務</span><span class="sxs-lookup"><span data-stu-id="0d8fd-124">Expanded VoIP Services</span></span>

<span data-ttu-id="0d8fd-125">語音功能通常是部署 SIP 中繼的主要動機，但語音支援只是第一個步驟。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-125">Voice features are often the primary motivation for deploying SIP trunking, but voice support is just the first step.</span></span> <span data-ttu-id="0d8fd-126">有了 SIP 中繼，您就可以延伸 VoIP 功能並啟用商務用 Skype Server，以提供一組更豐富的服務。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-126">With SIP trunking, you can extend VoIP capabilities and enable Skype for Business Server to deliver a richer set of services.</span></span> <span data-ttu-id="0d8fd-127">例如：</span><span class="sxs-lookup"><span data-stu-id="0d8fd-127">For example:</span></span>

- <span data-ttu-id="0d8fd-128">針對未執行商務用 Skype Server 的裝置，增強的目前狀態偵測功能可提供與行動電話的更佳整合，讓您可以查看使用者何時在行動電話上通話。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-128">Enhanced presence detection for devices that are not running Skype for Business Server can provide better integration with mobile phones, enabling you to see when a user is on a mobile phone call.</span></span>

- <span data-ttu-id="0d8fd-129">E9-1-1 緊急通話可讓您接聽911通話的主管機構，判斷來電者與其電話號碼的位置。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-129">E9-1-1 emergency calling enables the authorities who answer 911 calls to determine the caller's location from his or her telephone number.</span></span>

> [!NOTE]
> <span data-ttu-id="0d8fd-130">請與您的 ITSP 取得他們支援並可供您組織使用的服務清單。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-130">Contact your ITSP for a list of services that they support and can enable for your organization.</span></span>

### <a name="sip-trunks-vs-direct-sip-connections"></a><span data-ttu-id="0d8fd-131">SIP Trunks 與直接 SIP 連線</span><span class="sxs-lookup"><span data-stu-id="0d8fd-131">SIP Trunks vs. Direct SIP Connections</span></span>

<span data-ttu-id="0d8fd-132">[幹線] 一詞是從電路交換技術衍生而來。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-132">The term trunk is derived from circuit-switched technology.</span></span> <span data-ttu-id="0d8fd-133">它是指連接電話交換裝置的專用物理線路。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-133">It refers to a dedicated physical line that connects telephone switching equipment.</span></span> <span data-ttu-id="0d8fd-134">就像其前置任務一樣，時間分割複用（TDM） trunks，SIP trunks 是兩個獨立 SIP 網路之間的連線，即商務用 Skype Server enterprise 和 ITSP。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-134">Like their predecessor, time division multiplexing (TDM) trunks, SIP trunks are connections between two separate SIP networks—the Skype for Business Server enterprise and the ITSP.</span></span> <span data-ttu-id="0d8fd-135">與電路交換 trunks 不同，SIP trunks 是可在任何支援的 SIP 中繼連線類型上建立的虛擬連線。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-135">Unlike circuit-switched trunks, SIP trunks are virtual connections that can be established over any of the supported SIP trunking connection types.</span></span>

<span data-ttu-id="0d8fd-136">另一方面，直接 SIP 連線就是不跨越本機網路邊界的 SIP 連線（也就是，它們會連線到內部網路內的公用交換電話網絡（PSTN）閘道或私人分支 exchange （PBX）。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-136">Direct SIP connections, on the other hand, are SIP connections that do not cross the local network boundary (that is, they connect to a public switched telephone network (PSTN) gateway or private branch exchange (PBX) within your internal network).</span></span> <span data-ttu-id="0d8fd-137">如需有關如何將直接 SIP 連線與商務用 Skype Server 搭配使用的詳細資訊，請參閱[商務用 Skype server 中的直接 sip](direct-sip.md)連線。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-137">For details about how you can use direct SIP connections with Skype for Business Server, see [Direct SIP connections in Skype for Business Server](direct-sip.md).</span></span>

## <a name="how-do-i-implement-sip-trunking"></a><span data-ttu-id="0d8fd-138">如何實現 SIP 中繼？</span><span class="sxs-lookup"><span data-stu-id="0d8fd-138">How do I implement SIP Trunking?</span></span>

<span data-ttu-id="0d8fd-139">若要實現 SIP 中繼，您必須透過中繼伺服器路由連線，該伺服器充當商務用 Skype Server 用戶端與服務提供者之間通訊會話的 proxy，並視需要使用 transcodes 媒體。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-139">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Skype for Business Server clients and the service provider and transcodes media, when necessary.</span></span>

<span data-ttu-id="0d8fd-140">每個中繼伺服器都有一個內部網路介面與一個外部網路介面。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-140">Each Mediation Server has an internal network interface and an external network interface.</span></span> <span data-ttu-id="0d8fd-141">內部介面會連接到前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-141">The internal interface connects to the Front End Servers.</span></span> <span data-ttu-id="0d8fd-142">外部介面通常稱為閘道介面，因為它通常是用來將中繼伺服器連線到公用交換式電話網絡（PSTN）閘道或 IP PBX。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-142">The external interface is commonly called the gateway interface because it has traditionally been used to connect the Mediation Server to a public switched telephone network (PSTN) gateway or an IP-PBX.</span></span> <span data-ttu-id="0d8fd-143">若要實施 SIP 幹線，您可以將中繼伺服器的外部介面連接到 ITSP 的外部邊緣元件。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-143">To implement a SIP trunk, you connect the external interface of the Mediation Server to the external edge component of the ITSP.</span></span> <span data-ttu-id="0d8fd-144">ITSP 的外部邊緣元件可以是 [會話邊界控制器（SBC）]、[路由器] 或 [閘道]。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-144">The external edge component of the ITSP could be a Session Border Controller (SBC), a router, or a gateway.</span></span>

<span data-ttu-id="0d8fd-145">如需有關中繼伺服器的詳細資訊，請參閱[商務用 Skype server 中的中繼伺服器元件](mediation-server.md)。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-145">For details about Mediation Servers, see [Mediation Server component in Skype for Business Server](mediation-server.md).</span></span>

### <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="0d8fd-146">集中化與分散式 SIP 中繼</span><span class="sxs-lookup"><span data-stu-id="0d8fd-146">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="0d8fd-147">集中式 SIP 中繼會透過您的中央網站路由所有 VoIP 流量，包括分支網站流量。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-147">Centralized SIP trunking routes all VoIP traffic, including branch site traffic, through your central site.</span></span> <span data-ttu-id="0d8fd-148">集中式部署模型簡單、經濟高效，且通常是在商務用 Skype Server 上實現 SIP trunks 的建議方法。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-148">The centralized deployment model is simple, cost-effective, and is generally the recommended approach for implementing SIP trunks with Skype for Business Server.</span></span>

<span data-ttu-id="0d8fd-149">分散式 SIP 中繼是一種部署模型，您可以在其中在一或多個分支網站上執行本機 SIP trunks。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-149">Distributed SIP trunking is a deployment model in which you implement local SIP trunks at one or more branch sites.</span></span> <span data-ttu-id="0d8fd-150">然後，VoIP 流量會直接從分支網站路由到服務提供者，而不需要透過中心網站。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-150">VoIP traffic is then routed from the branch site directly to a service provider without going through the central site.</span></span>

<span data-ttu-id="0d8fd-151">只有在下列情況下，才需要分散式 SIP 中繼：</span><span class="sxs-lookup"><span data-stu-id="0d8fd-151">Distributed SIP trunking is required only in the following cases:</span></span>

- <span data-ttu-id="0d8fd-152">分支網站需要 survivable 手機連線（例如 WAN 向下）。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-152">The branch site requires survivable phone connectivity (for example, if the WAN goes down).</span></span> <span data-ttu-id="0d8fd-153">必須針對每個分支網站來分析此需求;某些分支可能需要冗余和容錯移轉，而其他則可能不需要。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-153">This requirement should be analyzed for each branch site; some of your branches may require redundancy and failover, whereas others may not.</span></span>

- <span data-ttu-id="0d8fd-154">在兩個中央網站之間必須具備復原能力。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-154">Resiliency is required between two central sites.</span></span> <span data-ttu-id="0d8fd-155">您必須確定 SIP 主幹會在每個中央站台終止。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-155">You need to make sure that a SIP trunk terminates at each central site.</span></span> <span data-ttu-id="0d8fd-156">例如，如果您有都柏林及 Tukwila 的中央網站，且兩者都只使用一個網站的 SIP 主幹，則在幹線關閉時，其他網站的使用者就無法進行 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-156">For example, if you have Dublin and Tukwila central sites and both use only one site's SIP trunk, if the trunk goes down, the other site's users cannot make PSTN calls.</span></span>

- <span data-ttu-id="0d8fd-157">分支網站與中央網站位於不同的國家/地區。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-157">The branch site and central site are in different countries/regions.</span></span> <span data-ttu-id="0d8fd-158">出於相容性和法律原因，您至少需要針對每個國家/地區提供一個 SIP 幹線。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-158">For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span> <span data-ttu-id="0d8fd-159">例如，在 [歐盟] 中，通訊不能離開國家/地區，也不會在本機終止並集中點。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-159">For example, in the European Union, communications cannot leave a country/region without terminating locally at a centralized point.</span></span>

<span data-ttu-id="0d8fd-160">根據網站的地理位置和您在企業中預期的流量，您可能不想要透過中央 SIP 主幹傳送所有使用者，或者您可以選擇透過 SIP 幹線在其分支網站上傳送部分使用者。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-160">Depending on the geographical location of sites and how much traffic you anticipate within your enterprise, you may not want to route all users through the central SIP trunk, or you may opt to route some users through a SIP trunk at their branch site.</span></span> <span data-ttu-id="0d8fd-161">若要分析您的需求，請回答下列問題：</span><span class="sxs-lookup"><span data-stu-id="0d8fd-161">To analyze your needs, answer the following questions:</span></span>

- <span data-ttu-id="0d8fd-162">每個網站有多大（也就是有多少使用者可供企業語音）？</span><span class="sxs-lookup"><span data-stu-id="0d8fd-162">How big is each site (that is, how many users are enabled for Enterprise Voice)?</span></span>

- <span data-ttu-id="0d8fd-163">在每個網站上哪一條直向撥打電話（已有）號碼會取得最多電話？</span><span class="sxs-lookup"><span data-stu-id="0d8fd-163">Which direct inward dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="0d8fd-164">部署集中式或分散式 SIP 中繼的決定需要成本效益分析。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-164">The decision whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis.</span></span> <span data-ttu-id="0d8fd-165">在某些情況下，您可以選擇選用分散式部署模型（即使不需要）。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-165">In some cases, it may be advantageous to opt for the distributed deployment model even if it is not required.</span></span> <span data-ttu-id="0d8fd-166">在完整的集中式部署中，所有分支網站流量都是透過 WAN 連結路由。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-166">In a completely centralized deployment, all branch site traffic is routed over WAN links.</span></span> <span data-ttu-id="0d8fd-167">您可能會想要使用分散式 SIP 中繼，而不是針對 WAN 連結所需的頻寬付費。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-167">Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span> <span data-ttu-id="0d8fd-168">例如，您可能會想要在分支網站上部署標準版伺服器，並在中央網站使用同盟，或者您可能想要部署 Survivable 分支裝置或 Survivable 分支伺服器與小型閘道。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-168">For example, you may want to deploy a Standard Edition server at a branch site with federation to the central site, or you may want to deploy a Survivable Branch Appliance or a Survivable Branch Server with a small gateway.</span></span>

> [!NOTE]
> <span data-ttu-id="0d8fd-169">如需分散式 SIP 中繼的詳細資料，請參閱[商務用 Skype 伺服器中的分支網站 SIP 中繼](branch-site.md)。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-169">For details about distributed SIP trunking, see [Branch site SIP trunking in Skype for Business Server](branch-site.md).</span></span>

### <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="0d8fd-170">支援的 SIP 中繼連線類型</span><span class="sxs-lookup"><span data-stu-id="0d8fd-170">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="0d8fd-171">商務用 Skype 伺服器支援下列 SIP 中繼連線類型：</span><span class="sxs-lookup"><span data-stu-id="0d8fd-171">Skype for Business Server supports the following connection types for SIP trunking:</span></span>

- <span data-ttu-id="0d8fd-172">多協定標籤切換（MPLS）是一種私人網路絡，可引導並將資料從一個網路節點傳送到下一個。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-172">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next.</span></span> <span data-ttu-id="0d8fd-173">MPLS 網路中的頻寬是與其他訂閱者共用的，每個資料包都指派標籤來區分訂閱者的資料與另一個訂閱者的資料。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-173">The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber's data from another's.</span></span> <span data-ttu-id="0d8fd-174">此連線類型不需要虛擬私人網路（VPN）。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-174">This connection type does not require a virtual private network (VPN).</span></span> <span data-ttu-id="0d8fd-175">可能的缺點是，過多的 IP 流量可能會干擾 VoIP 操作，除非 VoIP 流量是有優先權的。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-175">A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

- <span data-ttu-id="0d8fd-176">沒有其他通訊的私人連線（例如租用的光纖連接或 T1 線路）通常是最可靠且安全的連線類型。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-176">A private connection with no other traffic—for example, a leased fiber-optic connection or T1 line—is typically the most reliable and secure connection type.</span></span> <span data-ttu-id="0d8fd-177">這個連線類型提供最高的呼叫儲存容量，但通常是最昂貴的容量。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-177">This connection type provides the highest call-carrying capacity, but it is typically the most expensive.</span></span> <span data-ttu-id="0d8fd-178">VPN 不是必要的。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-178">VPN is not required.</span></span> <span data-ttu-id="0d8fd-179">私人連線適合具有高呼叫量或嚴格的安全性和可用性需求的組織。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-179">Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

- <span data-ttu-id="0d8fd-180">網際網路是成本最低的連線類型，但也是最不可靠的。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-180">The Internet is the least expensive connection type, but it is also the least reliable.</span></span> <span data-ttu-id="0d8fd-181">[網際網路連線] 是唯一需要 VPN 的商務用 Skype Server SIP 中繼連線類型。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-181">Internet connection is the only Skype for Business Server SIP trunking connection type that requires VPN.</span></span>

#### <a name="selecting-a-connection-type"></a><span data-ttu-id="0d8fd-182">選取連線類型</span><span class="sxs-lookup"><span data-stu-id="0d8fd-182">Selecting a Connection Type</span></span>

<span data-ttu-id="0d8fd-183">貴企業最合適的 SIP 中繼連線類型取決於您的需求和預算。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-183">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

- <span data-ttu-id="0d8fd-184">針對中型或大型企業而言，MPLS 網路通常會提供最大的價值。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-184">For a mid-size or larger enterprise, an MPLS network usually provides the greatest value.</span></span> <span data-ttu-id="0d8fd-185">它可以提供所需的頻寬，比專用的私人網路絡更便宜。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-185">It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

- <span data-ttu-id="0d8fd-186">大型企業可能需要在歐盟中使用私有光纖、T1、T3 或更高的連線（E1、E3 或較高的介面）。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-186">Large enterprises may require a private fiber-optic, T1, T3 or higher connection (E1, E3 or higher in the European Union).</span></span>

- <span data-ttu-id="0d8fd-187">針對小型企業版或含有低通話量的分支網站，透過網際網路進行 SIP 中繼可能是最佳選擇。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-187">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice.</span></span> <span data-ttu-id="0d8fd-188">建議您不要針對中型或大型網站使用此連線類型。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-188">This connection type is not recommended for mid-size or larger sites.</span></span>

### <a name="bandwidth-requirements"></a><span data-ttu-id="0d8fd-189">頻寬需求</span><span class="sxs-lookup"><span data-stu-id="0d8fd-189">Bandwidth Requirements</span></span>

<span data-ttu-id="0d8fd-190">您的實現所需的頻寬量，取決於撥號容量（您必須能夠支援的併發呼叫數量）。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-190">The amount of bandwidth your implementation requires depends on call capacity (the number of concurrent calls you must be able to support).</span></span> <span data-ttu-id="0d8fd-191">您必須考慮頻寬可用性，才能充分利用您已支付的峰值容量。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-191">You need to consider bandwidth availability, so that you can take full advantage of the peak capacity that you have paid for.</span></span> <span data-ttu-id="0d8fd-192">使用下列公式來計算 SIP 中繼峰值頻寬需求：</span><span class="sxs-lookup"><span data-stu-id="0d8fd-192">Use the following formula to calculate SIP trunk peak bandwidth requirement:</span></span>

<span data-ttu-id="0d8fd-193">SIP 幹線峰值頻寬 = 最大同時呼叫 x （64 kbps + 標頭大小）</span><span class="sxs-lookup"><span data-stu-id="0d8fd-193">SIP Trunk Peak Bandwidth = Max Simultaneous Calls x (64 kbps + header size)</span></span>

> [!NOTE]
> <span data-ttu-id="0d8fd-194">[標頭大小] 的最大值為20個位元組。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-194">Header size is 20 bytes maximum.</span></span>

### <a name="codec-support"></a><span data-ttu-id="0d8fd-195">編解碼器支援</span><span class="sxs-lookup"><span data-stu-id="0d8fd-195">Codec Support</span></span>

<span data-ttu-id="0d8fd-196">商務用 Skype 伺服器只支援下列編解碼器：</span><span class="sxs-lookup"><span data-stu-id="0d8fd-196">Skype for Business Server supports only the following codecs:</span></span>

- <span data-ttu-id="0d8fd-197">G. 711 （主要在北美境外使用）</span><span class="sxs-lookup"><span data-stu-id="0d8fd-197">G.711 a-law (used primarily outside North America)</span></span>

- <span data-ttu-id="0d8fd-198">G. 711 μ-定律（適用于北美）</span><span class="sxs-lookup"><span data-stu-id="0d8fd-198">G.711 µ-law (used in North America)</span></span>

### <a name="internet-telephony-service-provider"></a><span data-ttu-id="0d8fd-199">網際網路電話服務提供者</span><span class="sxs-lookup"><span data-stu-id="0d8fd-199">Internet Telephony Service Provider</span></span>

<span data-ttu-id="0d8fd-200">您實現 SIP 中繼連線的服務提供者的方式，從一個 ITSP 到另一個不同。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-200">How you implement the service provider side of a SIP trunk connection varies from one ITSP to another.</span></span> <span data-ttu-id="0d8fd-201">如需部署資訊，請聯絡您的服務提供者。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-201">For deployment information, contact your service provider.</span></span> <span data-ttu-id="0d8fd-202">如需認證 SIP 中繼服務提供者清單，請參閱[Microsoft 整合通訊開啟互通性計畫網站](https://go.microsoft.com/fwlink/p/?LinkId=287029)。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-202">For a list of certified SIP trunking service providers, see [Microsoft Unified Communications Open Interoperability Program website](https://go.microsoft.com/fwlink/p/?LinkId=287029).</span></span>

<span data-ttu-id="0d8fd-203">如需 Microsoft 認證 SIP 中繼提供者的詳細資料，請與您的 Microsoft 代表。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-203">For details about Microsoft certified SIP trunking providers, contact your Microsoft representative.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0d8fd-204">您必須使用 Microsoft 認證服務提供者，以確保您的 ITSP 支援所有流經 SIP 幹線的功能（例如，設定及管理會話，以及支援所有延伸 VoIP 服務）。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-204">You must use a Microsoft certified service provider to ensure that your ITSP supports all of the functionality that traverses the SIP trunk (for example, setting up and managing sessions and supporting all of the extended VoIP services).</span></span> <span data-ttu-id="0d8fd-205">Microsoft 技術支援不會延伸到使用 noncertified 提供者的設定。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-205">Microsoft technical support does not extend to configurations that use noncertified providers.</span></span> <span data-ttu-id="0d8fd-206">如果您目前使用的網際網路服務提供者未經過 SIP 中繼認證，您可以選擇繼續使用該提供者作為 ISP，然後使用 Microsoft 針對 SIP 中繼認證的提供者。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-206">If you currently use an Internet service provider that is not certified for SIP trunking, you can opt to continue using that provider as your ISP and use a provider certified by Microsoft for SIP trunking.</span></span>

### <a name="topologies-and-components-for-sip-trunking"></a><span data-ttu-id="0d8fd-207">SIP 中繼的拓撲與元件</span><span class="sxs-lookup"><span data-stu-id="0d8fd-207">Topologies and Components for SIP Trunking</span></span>

<span data-ttu-id="0d8fd-208">下圖描述商務用 Skype 伺服器中的 SIP 中繼拓撲。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-208">The following figure depicts the SIP trunking topology in Skype for Business Server.</span></span>

<span data-ttu-id="0d8fd-209">**SIP 中繼拓撲**</span><span class="sxs-lookup"><span data-stu-id="0d8fd-209">**SIP trunking topology**</span></span>

![SIP 主幹拓撲](../../media/669fb55d-7c81-4e21-9421-fabc43d6e064.jpg)

<span data-ttu-id="0d8fd-211">如圖表中所示，IP 虛擬私人網路（VPN）是在商業網路與公用交換電話網絡（PSTN）服務提供者之間連線所使用。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-211">As shown in the diagram, an IP virtual private network (VPN) is used for connectivity between the enterprise network and the public switched telephone network (PSTN) service provider.</span></span> <span data-ttu-id="0d8fd-212">這個私人網路絡的用途是提供 IP 連線、加強安全性，以及（選擇）取得服務品質（QoS）保證。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-212">The purpose of this private network is to provide IP connectivity, enhance security, and (optionally) obtain Quality of Service (QoS) guarantees.</span></span> <span data-ttu-id="0d8fd-213">由於 VPN 的性質，您不需要針對媒體流量使用傳輸層安全性（TLS）來傳送 SIP 信號流量或安全即時傳輸通訊協定（SRTP）。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-213">Because of the nature of a VPN, you do not need to use Transport Layer Security (TLS) for SIP signaling traffic or secure real-time transport protocol (SRTP) for the media traffic.</span></span> <span data-ttu-id="0d8fd-214">企業與服務提供者之間的連線是由針對 SIP 的純 TCP 連線和純時間傳輸通訊協定（RTP）（透過 UDP），透過 IP VPN 傳送媒體隧道。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-214">Connections between the enterprise and the service provider therefore consist of plain TCP connections for SIP and plain real-time transport protocol (RTP) (over UDP) for media tunneled through an IP VPN.</span></span> <span data-ttu-id="0d8fd-215">確定 VPN 路由器之間的所有防火牆都已開啟埠，以允許 VPN 路由器進行通訊，以及 VPN 路由器外部邊緣的 IP 位址可公開路由。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-215">Ensure that all firewalls between the VPN routers have ports open to allow the VPN routers to communicate, and that the IP addresses on the external edges of the VPN routers are publicly routable.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0d8fd-216">請與您的服務提供者聯繫，判斷它是否提供高可用性支援，包括容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-216">Contact your service provider to determine whether it provides support for high availability, including failover.</span></span> <span data-ttu-id="0d8fd-217">如果是這樣，您將需要判斷設定的程式。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-217">If so, you will need to determine the procedures for setting it up.</span></span> <span data-ttu-id="0d8fd-218">例如，您是否只需要在每個中繼伺服器上設定一個 IP 位址和一個 SIP 幹線，或者您是否需要在每個中繼伺服器上設定多個 SIP trunks？</span><span class="sxs-lookup"><span data-stu-id="0d8fd-218">For example, do you need to configure only one IP address and one SIP trunk on each Mediation Server, or do you need to configure multiple SIP trunks on each Mediation Server?</span></span> <span data-ttu-id="0d8fd-219">> 如果您有多個中心網站，也會詢問服務提供者是否有能力啟用與其他中心網站的連線。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-219">> If you have multiple central sites, also ask whether the service provider has the ability to enable connections to and from another central site.</span></span>

> [!NOTE]
> <span data-ttu-id="0d8fd-220">針對 SIP 中繼，我們強烈建議您部署獨立的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-220">For SIP trunking, we strongly recommend that you deploy stand-alone Mediation Servers.</span></span> <span data-ttu-id="0d8fd-221">如需詳細資訊，請參閱在部署檔中[部署轉送伺服器和定義對等](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-221">For details, see [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx) in the Deployment documentation.</span></span>

### <a name="securing-the-mediation-server-for-sip-trunking"></a><span data-ttu-id="0d8fd-222">保護 SIP 中繼的中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="0d8fd-222">Securing the Mediation Server for SIP Trunking</span></span>

<span data-ttu-id="0d8fd-223">為安全起見，您應該針對兩個 VPN 路由器之間的每個連線設定虛擬 LAN （VLAN）。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-223">For security purposes, you should set up a virtual LAN (VLAN) for each connection between the two VPN routers.</span></span> <span data-ttu-id="0d8fd-224">設定 VLAN 的實際處理常式會因路由器製造商而異。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-224">The actual process for setting up a VLAN varies from one router manufacturer to another.</span></span> <span data-ttu-id="0d8fd-225">如需詳細資訊，請與您的路由器廠商聯繫。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-225">For details, contact your router vendor.</span></span>

<span data-ttu-id="0d8fd-226">我們建議您遵循下列指導方針：</span><span class="sxs-lookup"><span data-stu-id="0d8fd-226">We recommend that you follow these guidelines:</span></span>

- <span data-ttu-id="0d8fd-227">在中繼伺服器與周邊網路中的 VPN 路由器（也稱為 DMZ、網路隔離區域及遮罩子網）之間設定虛擬 LAN （VLAN）。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-227">Set up a virtual LAN (VLAN) between the Mediation Server and the VPN router in the perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span>

- <span data-ttu-id="0d8fd-228">請勿允許將廣播或多播封包從路由器傳輸到 VLAN。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-228">Do not allow broadcast or multicast packets to be transferred from the router to the VLAN.</span></span>

- <span data-ttu-id="0d8fd-229">封鎖任何路由規則，可將流量從路由器路由到任何位置，而不是中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-229">Block any routing rules that route traffic from the router to anywhere but the Mediation Server.</span></span>

<span data-ttu-id="0d8fd-230">如果您使用的是 VPN 伺服器，我們建議您遵循下列指導方針：</span><span class="sxs-lookup"><span data-stu-id="0d8fd-230">If you use a VPN server, we recommend that you follow these guidelines:</span></span>

- <span data-ttu-id="0d8fd-231">在 VPN 伺服器與中繼伺服器之間設定 VLAN。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-231">Set up a VLAN between the VPN server and the Mediation Server.</span></span>

- <span data-ttu-id="0d8fd-232">請勿允許從 VPN 伺服器傳送廣播或多播資料包至 VLAN。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-232">Do not allow broadcast or multicast packets to be transmitted from the VPN server to the VLAN.</span></span>

- <span data-ttu-id="0d8fd-233">封鎖將 VPN 伺服器流量路由到任何位置的任何路由規則，而是中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-233">Block any routing rule that routes VPN server traffic to anywhere but the Mediation Server.</span></span>

- <span data-ttu-id="0d8fd-234">使用一般路由封裝（GRE）來加密 VPN 上的資料。</span><span class="sxs-lookup"><span data-stu-id="0d8fd-234">Encrypt data on the VPN by using generic routing encapsulation (GRE).</span></span>

## <a name="see-also"></a><span data-ttu-id="0d8fd-235">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0d8fd-235">See also</span></span>

[<span data-ttu-id="0d8fd-236">商務用 Skype Server 中的分支網站 SIP 中繼</span><span class="sxs-lookup"><span data-stu-id="0d8fd-236">Branch site SIP trunking in Skype for Business Server</span></span>](branch-site.md)

