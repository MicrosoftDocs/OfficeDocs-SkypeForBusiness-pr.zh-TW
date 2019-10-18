---
title: Microsoft 團隊通話流程
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 06/08/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sonua
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
description: 說明團隊如何在各種不同拓撲中使用 Office 365 流程。
ms.openlocfilehash: 91be46f556419dfd1ba8c52a99b8f06a19c63542
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573409"
---
# <a name="microsoft-teams-call-flows"></a><span data-ttu-id="a1044-103">Microsoft 團隊通話流程</span><span class="sxs-lookup"><span data-stu-id="a1044-103">Microsoft Teams call flows</span></span>

> [!Tip]
> <span data-ttu-id="a1044-104">請觀看下列會話，瞭解團隊如何利用您的網路，以及如何規劃最佳的網路連線：[團隊網路規劃](https://aka.ms/teams-networking)</span><span class="sxs-lookup"><span data-stu-id="a1044-104">Watch the following session to learn how Teams leverages your network and how to plan for optimal network connectivity: [Teams Network Planning](https://aka.ms/teams-networking)</span></span>

## <a name="overview"></a><span data-ttu-id="a1044-105">概觀</span><span class="sxs-lookup"><span data-stu-id="a1044-105">Overview</span></span>
<span data-ttu-id="a1044-106">本文將說明團隊如何在各種不同拓撲中使用 Office 365 通話流程。</span><span class="sxs-lookup"><span data-stu-id="a1044-106">This article describes how Teams uses Office 365 call flows in various topologies.</span></span> <span data-ttu-id="a1044-107">此外，它還描述用於對等媒體通訊的獨特團隊流程。</span><span class="sxs-lookup"><span data-stu-id="a1044-107">In addition, it describes unique Teams flows that are used for peer-to-peer media communication.</span></span> <span data-ttu-id="a1044-108">檔會說明這些流程、其用途，以及其在網路上的來源和終止。</span><span class="sxs-lookup"><span data-stu-id="a1044-108">The document describes these flows, their purpose, and their origin and termination on the network.</span></span> <span data-ttu-id="a1044-109">針對本文的用途，請假設下列事項：</span><span class="sxs-lookup"><span data-stu-id="a1044-109">For purposes of this article, assume the following:</span></span>

- <span data-ttu-id="a1044-110">內部部署的 Office 365 用戶端會使用流程 X 與雲端中的 Office 365 服務進行通訊。</span><span class="sxs-lookup"><span data-stu-id="a1044-110">Flow X is used by the on-premises Office 365 client to communicate with the Office 365 service in the cloud.</span></span> <span data-ttu-id="a1044-111">它是從客戶網路產生，並終止為 Office 365 中的端點。</span><span class="sxs-lookup"><span data-stu-id="a1044-111">It originates from the customer network, and it terminates as an endpoint in Office 365.</span></span>

- <span data-ttu-id="a1044-112">內部部署 Office 365 用戶端使用流程 Y 來與 Office 365 所依賴的網際網路上的服務進行通訊。</span><span class="sxs-lookup"><span data-stu-id="a1044-112">Flow Y is used by the on-premises Office 365 client to communicate with a service on the Internet that Office 365 has a dependency on.</span></span> <span data-ttu-id="a1044-113">它源于客戶網路，並終止為網際網路上的端點。</span><span class="sxs-lookup"><span data-stu-id="a1044-113">It originates from the customer network, and it terminates as an endpoint on the Internet.</span></span>

<span data-ttu-id="a1044-114">本文包含下列各節：</span><span class="sxs-lookup"><span data-stu-id="a1044-114">The article contains the following sections:</span></span>

- <span data-ttu-id="a1044-115">**背景**-提供背景資訊，例如 Office 365 流程可能流經的網路、流量類型、從客戶網路到 Office 365 服務端點的連線指示、與協力廠商元件的互通性，以及團隊用來選取媒體流程的原則。</span><span class="sxs-lookup"><span data-stu-id="a1044-115">**Background** - Provides background information, such as networks that Office 365 flows may traverse, type of traffic, connectivity guidance from the customer network to Office 365 service endpoints, interoperability with third-party components, and principles that are used by Teams to select media flows.</span></span>

- <span data-ttu-id="a1044-116">**不同拓撲中的通話流程**-說明各種拓撲中通話流程的使用方式。</span><span class="sxs-lookup"><span data-stu-id="a1044-116">**Call flows in various topologies** - Illustrates the use of call flows in various topologies.</span></span> <span data-ttu-id="a1044-117">針對每個拓朴，此區段會列舉所有受支援的資料流程，並說明如何透過幾種使用案例使用這些流程。</span><span class="sxs-lookup"><span data-stu-id="a1044-117">For each topology, the section enumerates all supported flows and illustrates how these flows are used via several use cases.</span></span> <span data-ttu-id="a1044-118">針對每個使用案例，它會透過流程圖來描述資料流程的順序與選取。</span><span class="sxs-lookup"><span data-stu-id="a1044-118">For each use case, it describes the sequence and selection of flows via a flow diagram.</span></span> 

- <span data-ttu-id="a1044-119">**具有快速路由優化的小組**-說明在部署快速路由以進行優化時，這些流程的使用方式，以簡單拓撲說明。</span><span class="sxs-lookup"><span data-stu-id="a1044-119">**Teams with Express Route optimization** - Describes how these flows are used when Express Route is deployed for optimization, illustrated via a simple topology.</span></span>

## <a name="background"></a><span data-ttu-id="a1044-120">背景</span><span class="sxs-lookup"><span data-stu-id="a1044-120">Background</span></span>
### <a name="network-segments"></a><span data-ttu-id="a1044-121">網段</span><span class="sxs-lookup"><span data-stu-id="a1044-121">Network segments</span></span>
<span data-ttu-id="a1044-122">**客戶網路**：這是您控制和管理的網路區段。</span><span class="sxs-lookup"><span data-stu-id="a1044-122">**Customer network**: This is the network segment that you control and manage.</span></span> <span data-ttu-id="a1044-123">這包括客戶辦公室內的所有客戶連線（無論是有線或無線）、office 建築物之間、內部部署資料中心，以及您連線至網際網路供應商、快速路由或任何其他私人對等。</span><span class="sxs-lookup"><span data-stu-id="a1044-123">This includes all customer connections within customer offices, whether wired or wireless, between office buildings, to on-premises datacenters, and your connections to Internet providers, Express Route, or any other private peering.</span></span> 

<span data-ttu-id="a1044-124">通常，客戶網路有數個網路週邊，且有多個防火牆和/或 proxy 伺服器，會強制執行您組織的安全性原則，而且只允許您已設定和設定的特定網路流量。</span><span class="sxs-lookup"><span data-stu-id="a1044-124">Typically, a customer network has several network perimeters with firewalls and/or proxy servers, which enforce your organization's security policies, and that only allow certain network traffic that you have set up and configured.</span></span> <span data-ttu-id="a1044-125">因為您要管理此網路，所以您可以直接控制網路的效能，而且強烈建議您完成網路評量，以驗證您網路中的網站與 Office 365 網路中的網站的效能。</span><span class="sxs-lookup"><span data-stu-id="a1044-125">Because you manage this network, you have direct control over the performance of the network, and it is highly recommended that you complete network assessments to validate performance both within sites in your network and from your network to the Office 365 network.</span></span> 

<span data-ttu-id="a1044-126">**網際網路**：這是整個網路的一部分，該網路區段將由從客戶網路外部連線至 Office 365 的使用者所使用。</span><span class="sxs-lookup"><span data-stu-id="a1044-126">**Internet**: This is the network segment that is part of your overall network that will be used by users who are connecting to Office 365 from outside of the customer network.</span></span> <span data-ttu-id="a1044-127">從客戶網路到 Office 365 的某些流量也會使用它。</span><span class="sxs-lookup"><span data-stu-id="a1044-127">It is also used by some traffic from the customer network to Office 365.</span></span> 

<span data-ttu-id="a1044-128">已**訪問/來賓私人網路**：這是客戶網路外部的網路區段，但不在公用網際網路中，您的使用者和/或其客人可能會造訪。</span><span class="sxs-lookup"><span data-stu-id="a1044-128">**Visited/Guest private network**: This is the network segment outside your customer network, but not in the public Internet, that your users and/or their guests may visit.</span></span> <span data-ttu-id="a1044-129">例如，「家用私人網路」或「企業私人網路」，它不會部署小組，您的使用者和/或其客戶與團隊服務可以駐留在其中。</span><span class="sxs-lookup"><span data-stu-id="a1044-129">For example, home private network or an Enterprise private network, that does not deploy Teams, where your users and/or their customers that interact with Teams services may reside.</span></span>

><span data-ttu-id="a1044-130">**注意**：與 Office 365 的連線也適用于這些網路。</span><span class="sxs-lookup"><span data-stu-id="a1044-130">**Note**: Connectivity to Office 365 is also applicable to these networks.</span></span>

<span data-ttu-id="a1044-131">**Office 365**：這是支援 Office 365 服務的網路區段。</span><span class="sxs-lookup"><span data-stu-id="a1044-131">**Office 365**: This is the network segment that supports Office 365 services.</span></span> <span data-ttu-id="a1044-132">它在全球各地分佈，且最接近客戶網路在大部分位置的邊緣。</span><span class="sxs-lookup"><span data-stu-id="a1044-132">It is distributed worldwide with edges in proximity to the customer network in most locations.</span></span> <span data-ttu-id="a1044-133">本檔中提到的函數包括傳輸中繼、會議服務器和媒體處理器。</span><span class="sxs-lookup"><span data-stu-id="a1044-133">Functions mentioned in this document include Transport Relay, conferencing server, and Media Processor.</span></span> 

<span data-ttu-id="a1044-134">**快速路線（選用）**：這是整個網路的一部分，可為您提供 Office 365 網路的專用專用連線。</span><span class="sxs-lookup"><span data-stu-id="a1044-134">**Express Route (optional)**: This is the network segment that is part of your overall network that will give you a dedicated, private connection to the Office 365 network.</span></span>

### <a name="types-of-traffic"></a><span data-ttu-id="a1044-135">流量類型</span><span class="sxs-lookup"><span data-stu-id="a1044-135">Types of traffic</span></span>

<span data-ttu-id="a1044-136">**即時媒體**：在 RTP （即時傳輸通訊協定）中封裝的資料，支援音訊、影片和螢幕共用工作負載。</span><span class="sxs-lookup"><span data-stu-id="a1044-136">**Real-time media**: Data encapsulated within RTP (Real-time Transport Protocol) that supports audio, video and screen sharing workloads.</span></span> <span data-ttu-id="a1044-137">一般來說，媒體流量會有很高的延遲，因此您可能會希望此流量盡可能地採用最直接路徑，並將 UDP 與 TCP 做為傳輸層通訊協定，這是從品質觀點開始互動即時媒體的最佳傳輸.</span><span class="sxs-lookup"><span data-stu-id="a1044-137">In general, media traffic is highly latency sensitive, so you would want this traffic to take the most direct path possible, and to use UDP versus TCP as the transport layer protocol, which is the best transport for interactive real time media from a quality perspective.</span></span> <span data-ttu-id="a1044-138">（注意：作為最後一個手段，媒體可以在 HTTP 通訊協定中使用 TCP/IP，也可在 HTTP 通訊協定內進行隧道作業，但由於不良品質的影響，不建議您這麼做。）RTP 流程是透過 SRTP 加以保護，其中只有負載是經過加密的。</span><span class="sxs-lookup"><span data-stu-id="a1044-138">(Note: As a last resort, media can use TCP/IP and also be tunneled within the HTTP protocol, but it is not recommended due to bad quality implications.) RTP flow is secured via SRTP, in which only the payload is encrypted.</span></span>

<span data-ttu-id="a1044-139">[**通知**]：用戶端與伺服器之間的通訊連結，或用來控制活動的其他用戶端（例如，啟動通話時），並傳送立即訊息。</span><span class="sxs-lookup"><span data-stu-id="a1044-139">**Signaling**: The communication link between the client and server, or other clients that are used to control activities (for example, when a call is initiated), and deliver instant messages.</span></span> <span data-ttu-id="a1044-140">大多數的信號流量都使用 HTTPS 式的 REST 介面，但在某些情況下（例如，Office 365 與會話邊界控制器之間的連線），它會使用 SIP 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="a1044-140">Most signaling traffic uses the HTTPS-based REST interfaces, though in some scenarios (for example, connection between Office 365 and a Session Border Controller) it uses SIP protocol.</span></span> <span data-ttu-id="a1044-141">請務必瞭解，這項流量對延遲而言不太敏感，但如果端點之間的延遲時間超過數秒，可能會導致服務中斷或呼叫超時。</span><span class="sxs-lookup"><span data-stu-id="a1044-141">It's important to understand that this traffic is much less sensitive to latency but may cause service outages or call timeouts if latency between the endpoints exceeds several seconds.</span></span> 

### <a name="connectivity-to-office-365"></a><span data-ttu-id="a1044-142">Office 365 的連線能力</span><span class="sxs-lookup"><span data-stu-id="a1044-142">Connectivity to Office 365</span></span>

<span data-ttu-id="a1044-143">小組需要[連線至網際網路](https://support.office.com/article/connectivity-to-the-internet-64b420ef-0218-48f6-8a34-74bb27633b10)。</span><span class="sxs-lookup"><span data-stu-id="a1044-143">Teams requires [connectivity to the Internet](https://support.office.com/article/connectivity-to-the-internet-64b420ef-0218-48f6-8a34-74bb27633b10).</span></span> <span data-ttu-id="a1044-144">團隊端點 Url 和 IP 位址範圍會列在[Office 365 url 和 ip 位址範圍](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)中。</span><span class="sxs-lookup"><span data-stu-id="a1044-144">Teams endpoint URLs and IP address ranges are listed in [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span> <span data-ttu-id="a1044-145">（注意：請開啟與 TCP 埠80和443的連線，並需要 UDP 埠3478到3481。）此外，小組也會對商務用 Skype Online 產生相依性的相依性，這也必須連線到網際網路。</span><span class="sxs-lookup"><span data-stu-id="a1044-145">(Note: Open connectivity to TCP ports 80 and 443, and to UDP ports 3478 through 3481 is required.) Furthermore, Teams has a dependency on Skype for Business Online, which must also be connected to the Internet.</span></span>

<span data-ttu-id="a1044-146">團隊媒體流程連線是透過標準的 IETF ICE （互動式連接建立）程式來實現。</span><span class="sxs-lookup"><span data-stu-id="a1044-146">Teams media flows connectivity is implemented via standard IETF ICE (Interactive Connectivity Establishment) procedures.</span></span>

### <a name="interoperability-restrictions"></a><span data-ttu-id="a1044-147">互通性限制</span><span class="sxs-lookup"><span data-stu-id="a1044-147">Interoperability restrictions</span></span>
<span data-ttu-id="a1044-148">**協力廠商媒體繼電器**：團隊媒體流程（也就是，其中一個媒體端點是團隊）可能只會遍歷團隊或商務用 Skype 原生媒體轉送器。</span><span class="sxs-lookup"><span data-stu-id="a1044-148">**Third party media relays**: A Teams media flow (that is, one of the media endpoints is Teams) may traverse only Teams or Skype for Business native media relays.</span></span> <span data-ttu-id="a1044-149">不支援與協力廠商媒體轉接的互通性。</span><span class="sxs-lookup"><span data-stu-id="a1044-149">Interoperability with a third party media relay is not supported.</span></span> <span data-ttu-id="a1044-150">（注意： PSTN 上的協力廠商 SBC 必須結束 RTP/RTCP 串流，並透過 SRTP 加以保護，而不會將其轉接至下一個躍點）。</span><span class="sxs-lookup"><span data-stu-id="a1044-150">(Note: A third party SBC on the boundary with PSTN must terminate RTP/RTCP stream, secured via SRTP, and not relay it to the next hop.)</span></span>

<span data-ttu-id="a1044-151">**協力廠商 SIP proxy 伺服器**：具有協力廠商 SBC 和/或閘道的 [使用 SIP 通知 SIP] 對話方塊，可能會遍歷小組或商務用 Skype 原生 SIP proxy。</span><span class="sxs-lookup"><span data-stu-id="a1044-151">**Third party SIP proxy servers**: A Teams signaling SIP dialog with a third party SBC and/or gateway may traverse Teams or Skype for Business native SIP proxies.</span></span> <span data-ttu-id="a1044-152">不支援與協力廠商 SIP proxy 的互通性。</span><span class="sxs-lookup"><span data-stu-id="a1044-152">Interoperability with a third party SIP proxy is not supported.</span></span>

<span data-ttu-id="a1044-153">**協力廠商 B2BUA （也就是 SBC）**：來自/到 PSTN 的團隊媒體流程是由協力廠商 SBC 終止。</span><span class="sxs-lookup"><span data-stu-id="a1044-153">**Third party B2BUA (that is, SBC)**: A Teams media flow from/to the PSTN is terminated by a third party SBC.</span></span> <span data-ttu-id="a1044-154">不過，不支援在小組網路中與協力廠商 SBC （也就是協力廠商 SBC 調節兩個小組/商務用 Skype 端點）的互通性。</span><span class="sxs-lookup"><span data-stu-id="a1044-154">However, interoperability with a third party SBC within the Teams network (that is, a third party SBC mediates two Teams/Skype for Business endpoints) is not supported.</span></span>

### <a name="technologies-that-are-not-recommended-with-microsoft-teams"></a><span data-ttu-id="a1044-155">Microsoft 團隊不建議的技術</span><span class="sxs-lookup"><span data-stu-id="a1044-155">Technologies that are not recommended with Microsoft Teams</span></span>

<span data-ttu-id="a1044-156">**VPN 網路**：不建議媒體流量（即，流程2」）。</span><span class="sxs-lookup"><span data-stu-id="a1044-156">**VPN network**: It is not recommended for media traffic (that is, flow 2').</span></span> <span data-ttu-id="a1044-157">VPN 用戶端應該使用分割式 VPN，並路由媒體流量，就像在中指定的https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/任何外部非 VPN 使用者。</span><span class="sxs-lookup"><span data-stu-id="a1044-157">The VPN client should use split VPN and route media traffic like any external non-VPN user, as specified in https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/.</span></span>

><span data-ttu-id="a1044-158">**注意**：雖然標題是 Lync，但也適用于團隊。</span><span class="sxs-lookup"><span data-stu-id="a1044-158">**Note**: Although the title is Lync, it is applicable to Teams as well.</span></span>

<span data-ttu-id="a1044-159">[**資料包 shapers**]：不建議任何類型的資料包 snippers、資料包檢查或資料包整形服務裝置，可能會顯著降低品質。</span><span class="sxs-lookup"><span data-stu-id="a1044-159">**Packet shapers**: Any kind of packet snippers, packet inspection, or packet shaper devices are not recommended and may degrade quality significantly.</span></span> 

### <a name="principles"></a><span data-ttu-id="a1044-160">理念</span><span class="sxs-lookup"><span data-stu-id="a1044-160">Principles</span></span>
<span data-ttu-id="a1044-161">有四個一般原則可協助您瞭解 Microsoft 團隊的通話流程：</span><span class="sxs-lookup"><span data-stu-id="a1044-161">There are four general principles that help you understand call flows for Microsoft Teams:</span></span>
 
1.  <span data-ttu-id="a1044-162">Microsoft 團隊會議是由 Office 365 託管于第一個參與者加入的同一個區域中。</span><span class="sxs-lookup"><span data-stu-id="a1044-162">A Microsoft Teams conference is hosted by Office 365 in the same region where the first participant joined.</span></span> <span data-ttu-id="a1044-163">（注意：如果這項規則在某些拓撲中會有例外狀況，則會在這份檔中說明，並以適當的通話流程來說明。）</span><span class="sxs-lookup"><span data-stu-id="a1044-163">(Note: If there will be exceptions to this rule in some topologies, then they will be described in this document, and illustrated by an appropriate call flow.)</span></span>

2.  <span data-ttu-id="a1044-164">Office 365 中的團隊媒體端點是根據媒體處理需求使用，而不是以通話類型為基礎。</span><span class="sxs-lookup"><span data-stu-id="a1044-164">A Teams media endpoint in Office 365 is used based on media processing needs and not based on call type.</span></span> <span data-ttu-id="a1044-165">（例如，點對點通話可能會使用雲端中的媒體端點來處理操作媒體及/或錄製，而有兩個參與者的會議可能不會使用雲端中的任何媒體端點）。不過，大部分的會議將會使用媒體端點來進行混合和路由用途，並在託管會議的位置進行分派。</span><span class="sxs-lookup"><span data-stu-id="a1044-165">(For example, a point-to-point call may use a media endpoint in the cloud to process media for transcription and/or recording, while a conference with two participants may not use any media endpoint in the cloud.) However, most conferences will use a media endpoint for mixing and routing purposes, allocated where the conference is hosted.</span></span> <span data-ttu-id="a1044-166">從用戶端傳送至媒體端點的媒體流量可能會直接路由，或在 Office 365 中使用傳輸中繼（如果由於客戶網路防火牆限制而需要）。</span><span class="sxs-lookup"><span data-stu-id="a1044-166">The media traffic sent from a client to the media endpoint may be routed directly or use a Transport Relay in Office 365 if required due to customer network firewall restrictions.</span></span> 

3.  <span data-ttu-id="a1044-167">對等通話的媒體流量會佔用最直接的路線，假設該通話不會要求雲端中的媒體端點（請參閱上述 #2）。</span><span class="sxs-lookup"><span data-stu-id="a1044-167">Media traffic for peer-to-peer calls take the most direct route that is available, assuming that the call doesn't mandate a media endpoint in the cloud (see #2 above).</span></span> <span data-ttu-id="a1044-168">首選路由會直接連到遠端對等（用戶端），但如果該路由無法使用，則一或多個傳輸中繼將會中繼流量。</span><span class="sxs-lookup"><span data-stu-id="a1044-168">The preferred route is direct to the remote peer (client), but if that route isn't available, then one or more Transport Relays will relay traffic.</span></span> <span data-ttu-id="a1044-169">建議媒體流量不應該橫向伺服器（例如資料包 shapers、VPN 伺服器等），因為這會影響媒體質量。</span><span class="sxs-lookup"><span data-stu-id="a1044-169">It is recommended that media traffic shall not transverse servers such as packet shapers, VPN servers, and so on, since this will impact the media quality.</span></span>

4.  <span data-ttu-id="a1044-170">信號流量永遠會移至最接近使用者的伺服器。</span><span class="sxs-lookup"><span data-stu-id="a1044-170">Signaling traffic always goes to the closest server to the user.</span></span> 

<span data-ttu-id="a1044-171">若要深入瞭解所選媒體路徑的詳細資訊，請參閱https://www.youtube.com/watch?v=1tmHMIlAQdo。</span><span class="sxs-lookup"><span data-stu-id="a1044-171">To learn more about the details on the media path that is chosen, see https://www.youtube.com/watch?v=1tmHMIlAQdo.</span></span>

## <a name="call-flows-in-various-topologies"></a><span data-ttu-id="a1044-172">不同拓撲中的通話流程</span><span class="sxs-lookup"><span data-stu-id="a1044-172">Call flows in various topologies</span></span>
### <a name="teams-topology"></a><span data-ttu-id="a1044-173">團隊拓朴</span><span class="sxs-lookup"><span data-stu-id="a1044-173">Teams topology</span></span>
<span data-ttu-id="a1044-174">此拓朴是由客戶使用來自雲端的團隊服務，而不需要任何內部部署（例如商務用 Skype Server 或電話系統直式路由）。</span><span class="sxs-lookup"><span data-stu-id="a1044-174">This topology is used by customers that leverage Teams services from the cloud without any on-premises deployment, such as Skype for Business Server or Phone System Direct Routing.</span></span> <span data-ttu-id="a1044-175">此外，Office 365 的介面是透過沒有 Azure Express 路由的網際網路完成。</span><span class="sxs-lookup"><span data-stu-id="a1044-175">In addition, the interface to Office 365 is done via the Internet without Azure Express Route.</span></span> 

<span data-ttu-id="a1044-176">[![Microsoft 團隊線上通話流程圖01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)</span><span class="sxs-lookup"><span data-stu-id="a1044-176">[![Microsoft Teams Online Call Flows Figure 01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)</span></span>

<span data-ttu-id="a1044-177">*圖 1-團隊拓朴*</span><span class="sxs-lookup"><span data-stu-id="a1044-177">*Figure 1 - Teams topology*</span></span>

<span data-ttu-id="a1044-178">請注意：</span><span class="sxs-lookup"><span data-stu-id="a1044-178">Note that:</span></span>

- <span data-ttu-id="a1044-179">上方圖表上的箭號方向反映了對企業週邊的連線所產生的溝通的起始方向。</span><span class="sxs-lookup"><span data-stu-id="a1044-179">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="a1044-180">在 UDP 的 [媒體] 中，第一個資料包可能會以相反的方向流向，但在其他方向的資料包都可能會遭到封鎖，直到其他方向的資料包流動為止。</span><span class="sxs-lookup"><span data-stu-id="a1044-180">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>
- <span data-ttu-id="a1044-181">團隊會與商務用 Skype Online 一起進行並排部署，因此用戶端會顯示為「團隊/SFB 使用者」。</span><span class="sxs-lookup"><span data-stu-id="a1044-181">Teams is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user".</span></span>

<span data-ttu-id="a1044-182">您可以在以下文章中找到有關下列選用拓撲的詳細資訊：</span><span class="sxs-lookup"><span data-stu-id="a1044-182">You can find more information on the following optional topologies later in the article:</span></span>

- <span data-ttu-id="a1044-183">商務用 Skype 內部部署在**團隊混合式拓撲**中有說明。</span><span class="sxs-lookup"><span data-stu-id="a1044-183">Skype for Business on-premises deployment is described in **Teams  hybrid topology**.</span></span>
- <span data-ttu-id="a1044-184">[電話系統 Direct 路由（適用于 PSTN 連線）] 會在**具有直接路由拓撲的小組**中描述。</span><span class="sxs-lookup"><span data-stu-id="a1044-184">Phone System Direct Routing (for PSTN connectivity) is described in **Teams with Direct Routing topology**.</span></span>
- <span data-ttu-id="a1044-185">在**具有快速路線優化的小組**中，會說明快速路線。</span><span class="sxs-lookup"><span data-stu-id="a1044-185">Express Route is described in  **Teams with Express Route optimization**.</span></span>

<span data-ttu-id="a1044-186">**流程描述**：</span><span class="sxs-lookup"><span data-stu-id="a1044-186">**Flow descriptions**:</span></span>
- <span data-ttu-id="a1044-187">[**流程 2** ]：代表使用者在使用者的小組體驗中，由客戶網路上的使用者在網際網路上所啟動的流程。</span><span class="sxs-lookup"><span data-stu-id="a1044-187">**Flow 2** – Represents a flow initiated by a user on the customer network to the Internet as a part of the user's Teams experience.</span></span> <span data-ttu-id="a1044-188">這些流程的範例是 DNS 和對等媒體。</span><span class="sxs-lookup"><span data-stu-id="a1044-188">Examples of these flows are DNS and peer-to-peer media.</span></span>
- <span data-ttu-id="a1044-189">[**流程 2 "** –代表由遠端行動小組使用者所啟動的流程，其中包含 VPN 至客戶網路。</span><span class="sxs-lookup"><span data-stu-id="a1044-189">**Flow 2'** – Represents a flow initiated by a remote mobile Teams user, with VPN to the customer network.</span></span> 
- <span data-ttu-id="a1044-190">**流程 3** –代表由遠端行動小組使用者發起給 Office 365/團隊端點的流程。</span><span class="sxs-lookup"><span data-stu-id="a1044-190">**Flow 3** – Represents a flow initiated by a remote mobile Teams user to Office 365/Teams endpoints.</span></span> 
- <span data-ttu-id="a1044-191">[**流程 4** ]-代表使用者在客戶網路上由 Office 365/小組端點啟動的流程。</span><span class="sxs-lookup"><span data-stu-id="a1044-191">**Flow 4** – Represents a flow initiated by a user on the customer network to Office 365/Teams endpoints.</span></span>
- <span data-ttu-id="a1044-192">**流程 5** –代表團隊使用者與客戶網路中的其他小組或商務用 Skype 使用者之間的對等媒體流程。</span><span class="sxs-lookup"><span data-stu-id="a1044-192">**Flow 5** – Represents a peer-to-peer media flow between a Teams user and another Teams or Skype for Business user within the customer network.</span></span>
- <span data-ttu-id="a1044-193">**流程 6** –代表遠端行動小組使用者與其他遠端行動小組或網際網路上的商務用 Skype 使用者之間的對等媒體流程。</span><span class="sxs-lookup"><span data-stu-id="a1044-193">**Flow 6** – Represents a peer-to-peer media flow between a remote mobile Teams user and another remote mobile Teams or Skype for Business user over the Internet.</span></span>

#### <a name="use-case-one-to-one"></a><span data-ttu-id="a1044-194">使用案例：一對一</span><span class="sxs-lookup"><span data-stu-id="a1044-194">Use case: One-to-one</span></span>
<span data-ttu-id="a1044-195">一對一通話使用常見的模型，在此模式中，呼叫者會透過 IP 位址/埠來取得一組候選人，包括本機、中繼及反身（用戶端的公用 IP 位址（由中繼）候選人來查看）。</span><span class="sxs-lookup"><span data-stu-id="a1044-195">One-to-one calls use a common model in which the caller will obtain a set of candidates consisting of IP addresses/ports--including local, relay, and reflexive (public IP address of client as seen by the relay) candidates.</span></span> <span data-ttu-id="a1044-196">來電者會將這些候選人傳送給被叫方;呼叫的參與方也會獲得類似的候選人集合，並將其傳送給來電者。</span><span class="sxs-lookup"><span data-stu-id="a1044-196">The caller sends these candidates to the called party; the called party also obtains a similar set of candidates and sends them to the caller.</span></span> <span data-ttu-id="a1044-197">STUN 連線檢查訊息是用來找出哪些來電者/叫方媒體路徑正常運作，且選取了最佳的工作路徑。</span><span class="sxs-lookup"><span data-stu-id="a1044-197">STUN connectivity check messages are used to find which caller/called party media paths work, and the best working path is selected.</span></span> <span data-ttu-id="a1044-198">然後使用選取的候選對，傳送媒體（也就是透過 SRTP 保護的 RTP/RTCP 資料包）。</span><span class="sxs-lookup"><span data-stu-id="a1044-198">Media (that is, RTP/RTCP packets secured via SRTP) are then sent using the selected candidate pair.</span></span> <span data-ttu-id="a1044-199">傳輸中繼是作為 Office 365 的一部分來部署。</span><span class="sxs-lookup"><span data-stu-id="a1044-199">The Transport relay is deployed as part of Office 365.</span></span>

<span data-ttu-id="a1044-200">如果本機 IP 位址/埠候選或反身候選人都有連通性，則會選取用戶端（或透過 NAT）之間的直接路徑來供媒體使用。</span><span class="sxs-lookup"><span data-stu-id="a1044-200">If the local IP address/port candidates or the reflexive candidates have connectivity, then the direct path between the clients (or via a NAT) will be selected for media.</span></span> <span data-ttu-id="a1044-201">如果用戶端都在客戶網路上，則應選取直接路徑。</span><span class="sxs-lookup"><span data-stu-id="a1044-201">If the clients are both on the customer network, then the direct path should be selected.</span></span> <span data-ttu-id="a1044-202">這需要在客戶網路中直接進行 UDP 連線。</span><span class="sxs-lookup"><span data-stu-id="a1044-202">This requires direct UDP connectivity within the customer network.</span></span> <span data-ttu-id="a1044-203">如果用戶端都是 nomadic 雲端使用者，則視 NAT/防火牆而定，媒體可能會使用直接連通性。</span><span class="sxs-lookup"><span data-stu-id="a1044-203">If the clients are both nomadic cloud users, then depending on the NAT/firewall, media may use direct connectivity.</span></span>

<span data-ttu-id="a1044-204">如果客戶網路上有一個用戶端，且有一個用戶端是外部用戶端（例如，行動雲端使用者），則無法直接連線到本機或反身候選作業。</span><span class="sxs-lookup"><span data-stu-id="a1044-204">If one client is internal on the customer network and one client is external (for example, a mobile cloud user), then it is unlikely that direct connectivity between the local or reflexive candidates is working.</span></span> <span data-ttu-id="a1044-205">在此情況下，選項是使用其中一個用戶端的傳輸中繼站候選人（例如，內部用戶端從 Office 365 中的傳輸中繼取得中繼候選人）; 外部用戶端必須能夠傳送 STUN/RTP/RTCP 資料包至傳輸轉接）。</span><span class="sxs-lookup"><span data-stu-id="a1044-205">In this case, an option is to use one of the Transport Relay candidates from either client (for example, the internal client obtained a relay candidate from the Transport relay in Office 365; the external client needs to be able to send STUN/RTP/RTCP packets to the transport relay).</span></span> <span data-ttu-id="a1044-206">另一個選項是內部用戶端傳送至行動雲端用戶端取得的中繼候選人。</span><span class="sxs-lookup"><span data-stu-id="a1044-206">Another option is the internal client sends to the relay candidate obtained by the mobile cloud client.</span></span> <span data-ttu-id="a1044-207">請注意，雖然強烈建議媒體的 UDP 連線，但支援 TCP。</span><span class="sxs-lookup"><span data-stu-id="a1044-207">Note that, although UDP connectivity for media is highly recommended, TCP is supported.</span></span>

<span data-ttu-id="a1044-208">**高層次步驟**：</span><span class="sxs-lookup"><span data-stu-id="a1044-208">**High-level steps**:</span></span>
1. <span data-ttu-id="a1044-209">團隊使用者 A 透過 flow2 解析 URL 網功能變數名稱稱（DNS）</span><span class="sxs-lookup"><span data-stu-id="a1044-209">Teams User A resolves URL domain name (DNS) via flow2</span></span>
2. <span data-ttu-id="a1044-210">小組使用者 A 透過流程4在團隊傳輸中繼上分配媒體轉送埠</span><span class="sxs-lookup"><span data-stu-id="a1044-210">Teams User A allocates a media Relay port on Teams Transport Relay via flow 4</span></span>
3. <span data-ttu-id="a1044-211">團隊使用者 A 透過流程4至 Office 365，透過 ICE 候選人傳送「邀請」</span><span class="sxs-lookup"><span data-stu-id="a1044-211">Teams User A sends "invite" with ICE candidates via flow 4 to Office 365</span></span>
4. <span data-ttu-id="a1044-212">Office 365 透過流程4將通知傳送給團隊使用者 B</span><span class="sxs-lookup"><span data-stu-id="a1044-212">Office 365 sends notification to Teams User B via flow 4</span></span>
5. <span data-ttu-id="a1044-213">團隊使用者 B 透過流程4在團隊傳輸中繼上分配媒體轉送埠</span><span class="sxs-lookup"><span data-stu-id="a1044-213">Teams User B allocates a media Relay port on Teams Transport Relay via flow 4</span></span>
6. <span data-ttu-id="a1044-214">團隊使用者 B 透過流程4傳送由 ICE 候選人提供的「回答」，並透過流程4轉寄回小組使用者 A</span><span class="sxs-lookup"><span data-stu-id="a1044-214">Teams User B sends "answer" with ICE candidates via flow 4, which is forwarded back to Teams User A via Flow 4</span></span>
7. <span data-ttu-id="a1044-215">小組使用者 A 與團隊使用者 B 呼叫 ICE 連線測試，並選取最佳可用媒體路徑（請參閱下圖以查看各種使用方式）</span><span class="sxs-lookup"><span data-stu-id="a1044-215">Teams User A and Teams User B invoke ICE connectivity tests and the best available media path is selected (see diagrams below for various use cases)</span></span>
8. <span data-ttu-id="a1044-216">團隊使用者透過流程4傳送遙測至 Office 365</span><span class="sxs-lookup"><span data-stu-id="a1044-216">Teams Users send telemetry to Office 365 via flow 4</span></span>

<span data-ttu-id="a1044-217">**在客戶網路中：**</span><span class="sxs-lookup"><span data-stu-id="a1044-217">**Within customer network:**</span></span>

<span data-ttu-id="a1044-218">[![Microsoft 團隊線上通話流程圖02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)</span><span class="sxs-lookup"><span data-stu-id="a1044-218">[![Microsoft Teams Online Call Flows Figure 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)</span></span>

<span data-ttu-id="a1044-219">*圖 2-客戶網路內*</span><span class="sxs-lookup"><span data-stu-id="a1044-219">*Figure 2 - Within customer network*</span></span>
 
<span data-ttu-id="a1044-220">在步驟7中，選取了對等媒體流程5。</span><span class="sxs-lookup"><span data-stu-id="a1044-220">In step 7, peer-to-peer media flow 5 is selected.</span></span>
 
<span data-ttu-id="a1044-221">媒體是雙向的。</span><span class="sxs-lookup"><span data-stu-id="a1044-221">Media is bidirectional.</span></span> <span data-ttu-id="a1044-222">[流程 5] 的方向代表 [一側] 會從連線的角度啟動通訊，且與本檔中的所有流程一致。</span><span class="sxs-lookup"><span data-stu-id="a1044-222">The direction of flow 5 indicates that one side initiates the communication from a connectivity perspective, consistent with all the flows in this document.</span></span> <span data-ttu-id="a1044-223">在這種情況下，因為兩個端點都在客戶網路內，所以使用哪個方向是不重要的。</span><span class="sxs-lookup"><span data-stu-id="a1044-223">In this case, it doesn't matter which direction is used because both endpoints are within the customer network.</span></span>

<span data-ttu-id="a1044-224">**外部使用者的客戶網路（依小組傳輸轉接的媒體轉送）：**</span><span class="sxs-lookup"><span data-stu-id="a1044-224">**Customer network to external user (media relayed by Teams Transport Relay):**</span></span>

<span data-ttu-id="a1044-225">[![Microsoft 團隊線上通話流程圖03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)</span><span class="sxs-lookup"><span data-stu-id="a1044-225">[![Microsoft Teams Online Call Flows Figure 03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)</span></span>

<span data-ttu-id="a1044-226">*圖 3-外部使用者的客戶網路（依小組傳輸轉接的媒體轉送）*</span><span class="sxs-lookup"><span data-stu-id="a1044-226">*Figure 3 - Customer network to external user (media relayed by Teams Transport Relay)*</span></span>
 
<span data-ttu-id="a1044-227">在步驟7、流程4中，從客戶網路到 Office 365，以及流程3（從遠端行動小組使用者到 Office 365）已選取。</span><span class="sxs-lookup"><span data-stu-id="a1044-227">In step 7, flow 4, from customer network to Office 365, and flow 3, from remote mobile Teams user to Office 365, are selected.</span></span> <span data-ttu-id="a1044-228">這些流程是透過 Office 365 內的小組傳輸中繼進行中繼。</span><span class="sxs-lookup"><span data-stu-id="a1044-228">These flows are relayed by Teams Transport Relay within Office 365.</span></span>

<span data-ttu-id="a1044-229">媒體是雙向的，其中的方向表示哪個端從連線性角度啟動通訊。</span><span class="sxs-lookup"><span data-stu-id="a1044-229">Media is bidirectional, where direction indicates which side initiates the communication from a connectivity perspective.</span></span> <span data-ttu-id="a1044-230">在這種情況下，這些流程是透過不同的傳輸通訊協定和位址，用於傳送信號和媒體。</span><span class="sxs-lookup"><span data-stu-id="a1044-230">In this case, these flows are used for signaling and media, via different transport protocols and addresses.</span></span>

<span data-ttu-id="a1044-231">**外部使用者的客戶網路（直接媒體）：**</span><span class="sxs-lookup"><span data-stu-id="a1044-231">**Customer network to external user (direct media):**</span></span>

<span data-ttu-id="a1044-232">[![Microsoft 團隊線上通話流程圖04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)</span><span class="sxs-lookup"><span data-stu-id="a1044-232">[![Microsoft Teams Online Call Flows Figure 04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)</span></span>

<span data-ttu-id="a1044-233">*圖 4-外部使用者的客戶網路（直接媒體）*</span><span class="sxs-lookup"><span data-stu-id="a1044-233">*Figure 4 - Customer network to external user (direct media)*</span></span>
 
<span data-ttu-id="a1044-234">在步驟7中，選取了 [從客戶網路到網際網路（用戶端對等）] 的 [流程 2]。</span><span class="sxs-lookup"><span data-stu-id="a1044-234">In step 7, flow 2, from customer network to Internet (client's peer), is selected.</span></span>
- <span data-ttu-id="a1044-235">使用遠端行動使用者（也就是不透過 Office 365 中繼）的直接媒體是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="a1044-235">Direct media with remote mobile user (that is, not relayed through Office 365) is optional.</span></span> <span data-ttu-id="a1044-236">換句話說，客戶可能會封鎖此路徑，透過 Office 365 中的傳輸中繼來強制執行媒體路徑。</span><span class="sxs-lookup"><span data-stu-id="a1044-236">In other words, customer may block this path to enforce a media path through Transport Relay in Office 365.</span></span>

- <span data-ttu-id="a1044-237">媒體是雙向的。</span><span class="sxs-lookup"><span data-stu-id="a1044-237">Media is bidirectional.</span></span> <span data-ttu-id="a1044-238">[流程 2] 到 [遠端行動使用者] 的方向表示一個端從連線的觀點啟動通訊。</span><span class="sxs-lookup"><span data-stu-id="a1044-238">The direction of flow 2 to remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span> 

<span data-ttu-id="a1044-239">**VPN 使用者至內部使用者（依小組傳輸轉接的媒體轉送）**</span><span class="sxs-lookup"><span data-stu-id="a1044-239">**VPN user to internal user (media relayed by Teams Transport Relay)**</span></span>

<span data-ttu-id="a1044-240">[![Microsoft 團隊線上通話流程圖05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)</span><span class="sxs-lookup"><span data-stu-id="a1044-240">[![Microsoft Teams Online Call Flows Figure 05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)</span></span>

<span data-ttu-id="a1044-241">*圖 5-VPN 使用者至內部使用者（依小組傳輸轉接的媒體轉送）*</span><span class="sxs-lookup"><span data-stu-id="a1044-241">*Figure 5 - VPN user to internal user (media relayed by Teams Transport Relay)*</span></span>
 
<span data-ttu-id="a1044-242">從 VPN 到客戶網路之間的信號，是透過流程2」。</span><span class="sxs-lookup"><span data-stu-id="a1044-242">Signaling between the VPN to the customer network is via flow 2'.</span></span> <span data-ttu-id="a1044-243">客戶網路與 Office 365 之間的信號是透過流程4。</span><span class="sxs-lookup"><span data-stu-id="a1044-243">Signaling between the customer network and Office 365 is via flow 4.</span></span> <span data-ttu-id="a1044-244">不過，媒體會繞過 VPN，而且是透過 Office 365 中的 [流程 3] 和 [4] 到 [小組媒體轉送] 進行路由。</span><span class="sxs-lookup"><span data-stu-id="a1044-244">However, media bypasses the VPN and is routed via flows 3 and 4 through Teams media relay in Office 365.</span></span>

<span data-ttu-id="a1044-245">**VPN 使用者至內部使用者（直接媒體）**</span><span class="sxs-lookup"><span data-stu-id="a1044-245">**VPN user to internal user (direct media)**</span></span>

<span data-ttu-id="a1044-246">[![Microsoft 團隊線上通話流程圖06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)</span><span class="sxs-lookup"><span data-stu-id="a1044-246">[![Microsoft Teams Online Call Flows Figure 06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)</span></span>

<span data-ttu-id="a1044-247">*圖 6-VPN 使用者至內部使用者（直接媒體）*</span><span class="sxs-lookup"><span data-stu-id="a1044-247">*Figure 6 - VPN user to internal user (direct media)*</span></span>

<span data-ttu-id="a1044-248">從 VPN 到客戶網路之間的信號，是透過流程2」。</span><span class="sxs-lookup"><span data-stu-id="a1044-248">Signaling between the VPN to the customer network is via flow 2'.</span></span> <span data-ttu-id="a1044-249">客戶網路與 Office 365 之間的信號是透過流程4。</span><span class="sxs-lookup"><span data-stu-id="a1044-249">Signaling between the customer network and Office 365 is via flow 4.</span></span> <span data-ttu-id="a1044-250">不過，媒體會繞過 VPN，且是透過流程2從客戶網路傳送到網際網路。</span><span class="sxs-lookup"><span data-stu-id="a1044-250">However, media bypasses the VPN and is routed via flow 2 from the customer network to the Internet.</span></span>

<span data-ttu-id="a1044-251">媒體是雙向的。</span><span class="sxs-lookup"><span data-stu-id="a1044-251">Media is bidirectional.</span></span> <span data-ttu-id="a1044-252">流向遠端行動使用者的流程2的方向，表示一側會從連接的觀點啟動通訊。</span><span class="sxs-lookup"><span data-stu-id="a1044-252">The direction of flow 2 to the remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span>

<span data-ttu-id="a1044-253">**VPN 使用者至外部使用者（直接媒體）**</span><span class="sxs-lookup"><span data-stu-id="a1044-253">**VPN user to external user (direct media)**</span></span>

<span data-ttu-id="a1044-254">[![Microsoft 團隊通話流程圖表07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)</span><span class="sxs-lookup"><span data-stu-id="a1044-254">[![Microsoft Teams call flows Figure 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)</span></span>

<span data-ttu-id="a1044-255">*圖 7-VPN 使用者與外部使用者（直接媒體）*</span><span class="sxs-lookup"><span data-stu-id="a1044-255">*Figure 7 - VPN user to external user (direct media)*</span></span>

<span data-ttu-id="a1044-256">VPN 使用者與客戶網路之間的信號，是透過流程2」，並透過流程4傳送到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="a1044-256">Signaling between the VPN user to the customer network is via flow 2' and via flow 4 to Office 365.</span></span> <span data-ttu-id="a1044-257">不過，媒體會繞過 VPN，且是透過流程6路由。</span><span class="sxs-lookup"><span data-stu-id="a1044-257">However, media bypasses VPN and is routed via flow 6.</span></span>

<span data-ttu-id="a1044-258">媒體是雙向的。</span><span class="sxs-lookup"><span data-stu-id="a1044-258">Media is bidirectional.</span></span> <span data-ttu-id="a1044-259">[流量 6] 到 [遠端行動使用者] 的方向代表，一個端會從連接的角度啟動通訊。</span><span class="sxs-lookup"><span data-stu-id="a1044-259">The direction of flow 6 to the remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span>

#### <a name="use-case-teams-to-pstn-through-office-365-trunk"></a><span data-ttu-id="a1044-260">使用案例：透過 Office 365 幹線的團隊至 PSTN</span><span class="sxs-lookup"><span data-stu-id="a1044-260">Use Case: Teams to PSTN through Office 365 Trunk</span></span>
<span data-ttu-id="a1044-261">Office 365 有一個手機系統，可讓您撥打及接聽公用交換電話網絡（PSTN）撥打電話。</span><span class="sxs-lookup"><span data-stu-id="a1044-261">Office 365 has a Phone System that allows placing and receiving calls from the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="a1044-262">如果 PSTN 幹線是透過電話系統通話方案連線，則此使用案例沒有特殊的連接需求。</span><span class="sxs-lookup"><span data-stu-id="a1044-262">If the PSTN trunk is connected via the Phone System Calling Plan, then there are no special connectivity requirements for this use case.</span></span> <span data-ttu-id="a1044-263">（如果您想要將自己的內部部署 PSTN 幹線連接至 Office 365，您可以使用 [電話系統直式路由]。）</span><span class="sxs-lookup"><span data-stu-id="a1044-263">(If you want to connect your own on-premises PSTN trunk to Office 365, you can use Phone System Direct Routing.)</span></span>

<span data-ttu-id="a1044-264">[![Microsoft 團隊線上通話流程圖表08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)</span><span class="sxs-lookup"><span data-stu-id="a1044-264">[![Microsoft Teams Online Call Flows Figure 08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)</span></span>

<span data-ttu-id="a1044-265">*圖 8-透過 Office 365 幹線的團隊至 PSTN*</span><span class="sxs-lookup"><span data-stu-id="a1044-265">*Figure 8 - Teams to PSTN through Office 365 Trunk*</span></span>

#### <a name="use-case-teams-meeting"></a><span data-ttu-id="a1044-266">使用案例：團隊會議</span><span class="sxs-lookup"><span data-stu-id="a1044-266">Use Case: Teams Meeting</span></span>

<span data-ttu-id="a1044-267">音訊/視頻/螢幕共用（VBSS）會議服務器是 Office 365 的一部分。</span><span class="sxs-lookup"><span data-stu-id="a1044-267">The audio/video/screen sharing (VBSS) conferencing server is part of Office 365.</span></span> <span data-ttu-id="a1044-268">它的公用 IP 位址必須可從客戶網路取得，而且必須是從 Nomadic 雲端用戶端取得的。</span><span class="sxs-lookup"><span data-stu-id="a1044-268">It has a public IP address that must be reachable from the customer network and must be reachable from a Nomadic Cloud client.</span></span> <span data-ttu-id="a1044-269">每個用戶端/端點都需要能夠連接到會議服務器。</span><span class="sxs-lookup"><span data-stu-id="a1044-269">Each client/endpoint needs to be able to connect to the conferencing server.</span></span>

<span data-ttu-id="a1044-270">內部用戶端會以與一對一通話描述的相同方式來取得本機、身式和中繼候選人。</span><span class="sxs-lookup"><span data-stu-id="a1044-270">Internal clients will obtain local, reflexive, and relay candidates in the same manner as described for one-to-one calls.</span></span> <span data-ttu-id="a1044-271">用戶端會將這些候選人傳送給邀請中的會議服務器。</span><span class="sxs-lookup"><span data-stu-id="a1044-271">The clients will send these candidates to the conferencing server in an invite.</span></span> <span data-ttu-id="a1044-272">會議服務器不會使用中繼，因為它有可公開取得的 IP 位址，因此它會以其當地 IP 位址候選的方式回復。</span><span class="sxs-lookup"><span data-stu-id="a1044-272">The conferencing server does not use a relay since it has a publicly reachable IP address, so it responds with its local IP address candidate.</span></span> <span data-ttu-id="a1044-273">用戶端與會議服務器會以與一對一通話描述的相同方式檢查連線性。</span><span class="sxs-lookup"><span data-stu-id="a1044-273">The client and conferencing server will check connectivity in the same manner described for one-to-one calls.</span></span> 

<span data-ttu-id="a1044-274">請注意：</span><span class="sxs-lookup"><span data-stu-id="a1044-274">Note that:</span></span>

- <span data-ttu-id="a1044-275">團隊用戶端無法加入商務用 Skype 會議，且商務用 Skype 用戶端無法加入團隊會議。</span><span class="sxs-lookup"><span data-stu-id="a1044-275">Teams clients cannot join Skype for Business meetings, and Skype for Business clients cannot join Teams meetings.</span></span>

- <span data-ttu-id="a1044-276">PSTN 使用者可以選擇 [撥入] 或 [撥出]，視會議的召集人 PSTN 通話和/或會議提供而定。</span><span class="sxs-lookup"><span data-stu-id="a1044-276">A PSTN user optionally "Dials IN" or "Dialed OUT", depending on the meeting's organizer PSTN Calling and/or conferencing provisioning.</span></span> 

- <span data-ttu-id="a1044-277">來賓使用者或客戶使用者可以從來賓私人網路絡加入，而這是透過 FW/NAT 與嚴格規則來保護。</span><span class="sxs-lookup"><span data-stu-id="a1044-277">A guest user or a customer user may join from a guest private network, which is protected via FW/NAT with strict rules.</span></span>

<span data-ttu-id="a1044-278">[![Microsoft 團隊線上通話流程圖09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)</span><span class="sxs-lookup"><span data-stu-id="a1044-278">[![Microsoft Teams Online Call Flows Figure 09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)</span></span>

<span data-ttu-id="a1044-279">*圖 9-團隊會議*</span><span class="sxs-lookup"><span data-stu-id="a1044-279">*Figure 9 - Teams Meeting*</span></span>

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a><span data-ttu-id="a1044-280">使用案例：與商務用 Skype 內部部署的同盟</span><span class="sxs-lookup"><span data-stu-id="a1044-280">Use Case: Federation with Skype for Business on premises</span></span>

<span data-ttu-id="a1044-281">**媒體會依團隊在 Office 365 中傳輸的方式進行中繼**</span><span class="sxs-lookup"><span data-stu-id="a1044-281">**Media relayed by Teams Transport Relay in Office 365**</span></span>

<span data-ttu-id="a1044-282">[![Microsoft 團隊線上通話流程圖10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)</span><span class="sxs-lookup"><span data-stu-id="a1044-282">[![Microsoft Teams Online Call Flows Figure 10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)</span></span>

<span data-ttu-id="a1044-283">*圖 10-在 Office 365 中，依團隊傳輸中繼的方式傳送媒體*</span><span class="sxs-lookup"><span data-stu-id="a1044-283">*Figure 10 - Media relayed by Teams Transport Relay in Office 365*</span></span>

<span data-ttu-id="a1044-284">請注意：</span><span class="sxs-lookup"><span data-stu-id="a1044-284">Note that:</span></span>

- <span data-ttu-id="a1044-285">同盟是依定義，在兩個租使用者之間的通訊。</span><span class="sxs-lookup"><span data-stu-id="a1044-285">Federation is, by definition, a communication between two tenants.</span></span> <span data-ttu-id="a1044-286">在此案例中，使用團隊的租使用者 federates 使用商務用 Skype 內部部署。</span><span class="sxs-lookup"><span data-stu-id="a1044-286">In this case, tenant A, which uses Teams, federates with tenant B, which uses Skype for Business on premises.</span></span> <span data-ttu-id="a1044-287">如果承租人 B 也是使用 Office 365，則商務用 Skype 用戶端將使用流程3與 Office 365 連線。</span><span class="sxs-lookup"><span data-stu-id="a1044-287">If tenant B is also using Office 365, then the Skype for Business client would have used flow 3 to connect with Office 365.</span></span>

- <span data-ttu-id="a1044-288">從同盟商務用 Skype 用戶端到內部部署商務用 skype 伺服器的信號和媒體不在本檔的範圍內。</span><span class="sxs-lookup"><span data-stu-id="a1044-288">Signaling and media from the federated Skype for Business client to on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="a1044-289">不過，這裡有清楚的說明。</span><span class="sxs-lookup"><span data-stu-id="a1044-289">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="a1044-290">在團隊與商務用 Skype 之間的通知是由 Office 365 中的閘道橋接。</span><span class="sxs-lookup"><span data-stu-id="a1044-290">Signaling between Teams and Skype for Business is bridged by a gateway in Office 365.</span></span>

- <span data-ttu-id="a1044-291">在這種情況下，媒體會透過 Office 365 中的小組傳輸中繼來轉接至客戶網路，以及透過流程4進行遠端 Skype 用戶端。</span><span class="sxs-lookup"><span data-stu-id="a1044-291">Media in this case is relayed by Teams Transport Relay in Office 365 to the customer network and remote Skype for Business client via flow 4.</span></span>

<span data-ttu-id="a1044-292">**受同盟租使用者的商務用 Skype 媒體轉送所進行的媒體轉送**</span><span class="sxs-lookup"><span data-stu-id="a1044-292">**Media relayed by Skype for Business Media Relay in federated tenant**</span></span>

<span data-ttu-id="a1044-293">[![Microsoft 團隊線上通話流程圖11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)</span><span class="sxs-lookup"><span data-stu-id="a1044-293">[![Microsoft Teams Online Call Flows Figure 11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)</span></span>

<span data-ttu-id="a1044-294">*圖 11-受同盟租使用者的商務用 Skype 媒體轉送所進行的媒體轉送*</span><span class="sxs-lookup"><span data-stu-id="a1044-294">*Figure 11 - Media relayed by Skype for Business Media Relay in federated tenant*</span></span>

<span data-ttu-id="a1044-295">請注意：</span><span class="sxs-lookup"><span data-stu-id="a1044-295">Note that:</span></span>

- <span data-ttu-id="a1044-296">從同盟商務用 Skype 用戶端到內部部署商務用 skype 伺服器的信號和媒體不在本檔的範圍內。</span><span class="sxs-lookup"><span data-stu-id="a1044-296">Signaling and media from the federated Skype for Business client to an on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="a1044-297">不過，這裡有清楚的說明。</span><span class="sxs-lookup"><span data-stu-id="a1044-297">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="a1044-298">在團隊與商務用 Skype 之間的通知是由 Office 365 中的閘道橋接。</span><span class="sxs-lookup"><span data-stu-id="a1044-298">Signaling between Teams and Skype for Business is bridged by a Gateway in Office 365.</span></span>

- <span data-ttu-id="a1044-299">在此案例中，媒體是透過商務用 Skype 在內部部署媒體轉送轉接至客戶網路（透過流程2）。</span><span class="sxs-lookup"><span data-stu-id="a1044-299">Media in this case is relayed by Skype for Business on-premises Media Relay to the customer network via flow 2.</span></span> <span data-ttu-id="a1044-300">（請注意，媒體轉送會先將來自團隊使用者的流量傳送給聯盟客戶網路中的遠端媒體轉送，直到相反方向的流量開始流動為止。</span><span class="sxs-lookup"><span data-stu-id="a1044-300">(Note that traffic from Teams user to the remote Media Relay in the federated customer network will be initially blocked by the Media Relay until traffic in the reverse direction starts to flow.</span></span> <span data-ttu-id="a1044-301">不過，雙向流程會以兩個方向開啟連線。</span><span class="sxs-lookup"><span data-stu-id="a1044-301">However, the bidirectional flow will open connectivity in both directions.)</span></span>

<span data-ttu-id="a1044-302">**Direct （對等）**</span><span class="sxs-lookup"><span data-stu-id="a1044-302">**Direct (peer-to-peer)**</span></span>

<span data-ttu-id="a1044-303">[![Microsoft 團隊線上通話流程圖12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)</span><span class="sxs-lookup"><span data-stu-id="a1044-303">[![Microsoft Teams Online Call Flows Figure 12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)</span></span>

<span data-ttu-id="a1044-304">*圖 12-Direct （對等）*</span><span class="sxs-lookup"><span data-stu-id="a1044-304">*Figure 12 - Direct (peer-to-peer)*</span></span>

### <a name="teams-hybrid-topology"></a><span data-ttu-id="a1044-305">小組混合式拓朴</span><span class="sxs-lookup"><span data-stu-id="a1044-305">Teams hybrid topology</span></span>
<span data-ttu-id="a1044-306">此拓朴包括擁有商務用 Skype 內部部署的小組。</span><span class="sxs-lookup"><span data-stu-id="a1044-306">This topology includes Teams with a Skype for Business on-premises deployment.</span></span>

<span data-ttu-id="a1044-307">[![Microsoft 團隊線上通話流程圖13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)</span><span class="sxs-lookup"><span data-stu-id="a1044-307">[![Microsoft Teams Online Call Flows Figure 13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)</span></span>

<span data-ttu-id="a1044-308">*圖 13-小組混合式拓撲*</span><span class="sxs-lookup"><span data-stu-id="a1044-308">*Figure 13 - Teams hybrid topology*</span></span>
 
- <span data-ttu-id="a1044-309">上方圖表上的箭號方向反映了對企業週邊的連線所產生的溝通的起始方向。</span><span class="sxs-lookup"><span data-stu-id="a1044-309">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="a1044-310">在 UDP 的 [媒體] 中，第一個資料包可能會以相反的方向流向，但在其他方向的資料包都可能會遭到封鎖，直到其他方向的資料包流動為止。</span><span class="sxs-lookup"><span data-stu-id="a1044-310">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>

- <span data-ttu-id="a1044-311">團隊會與商務用 Skype Online 一起進行並排部署，因此用戶端會顯示為「團隊/SFB 使用者」。</span><span class="sxs-lookup"><span data-stu-id="a1044-311">Teams is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user".</span></span>

<span data-ttu-id="a1044-312">其他流程（在小組拓撲之上）：</span><span class="sxs-lookup"><span data-stu-id="a1044-312">Additional flows (on top of Teams topology):</span></span>
- <span data-ttu-id="a1044-313">[**流程 5a** ] –代表客戶網路中的小組使用者與客戶網路邊緣的商務用 Skype 內部網路媒體中繼之間的對等媒體流程。</span><span class="sxs-lookup"><span data-stu-id="a1044-313">**Flow 5A** – Represents a peer-to-peer media flow between a Teams user within the customer network and a Skype for Business on-premises media relay at the customer network edge.</span></span>

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a><span data-ttu-id="a1044-314">使用案例：團隊到商務用 Skype 一對一</span><span class="sxs-lookup"><span data-stu-id="a1044-314">Use Case: Teams to Skype for Business one-to-one</span></span>
<span data-ttu-id="a1044-315">**在客戶網路中混合式**</span><span class="sxs-lookup"><span data-stu-id="a1044-315">**Hybrid within the customer network**</span></span>

<span data-ttu-id="a1044-316">[![Microsoft 團隊線上通話流程圖14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)</span><span class="sxs-lookup"><span data-stu-id="a1044-316">[![Microsoft Teams Online Call Flows Figure 14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)</span></span>

<span data-ttu-id="a1044-317">*圖 14-在客戶網路中混合式*</span><span class="sxs-lookup"><span data-stu-id="a1044-317">*Figure 14 - Hybrid within customer network*</span></span>
 
<span data-ttu-id="a1044-318">在團隊與商務用 Skype 之間的通知是由 Office 365 中的閘道橋接。</span><span class="sxs-lookup"><span data-stu-id="a1044-318">Signaling between Teams and Skype for Business is bridged by a gateway in Office 365.</span></span> <span data-ttu-id="a1044-319">不過，媒體是透過流程5在客戶網路內以直接對等方式傳送。</span><span class="sxs-lookup"><span data-stu-id="a1044-319">However, media is routed directly peer-to-peer within the customer network via flow 5.</span></span>

<span data-ttu-id="a1044-320">**含外部商務用 Skype 使用者的混合式客戶網路（由 Office 365 中繼）**</span><span class="sxs-lookup"><span data-stu-id="a1044-320">**Hybrid customer network with external Skype for Business user – relayed by Office 365**</span></span>

<span data-ttu-id="a1044-321">[![Microsoft 團隊線上通話流程圖15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)</span><span class="sxs-lookup"><span data-stu-id="a1044-321">[![Microsoft Teams Online Call Flows Figure 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)</span></span>

<span data-ttu-id="a1044-322">*圖 15-使用外部商務用 Skype 使用者的混合式客戶網路-由 Office 365 中繼*</span><span class="sxs-lookup"><span data-stu-id="a1044-322">*Figure 15 - Hybrid customer network with external Skype for Business user - relayed by Office 365*</span></span>

<span data-ttu-id="a1044-323">請注意：</span><span class="sxs-lookup"><span data-stu-id="a1044-323">Note that:</span></span>

- <span data-ttu-id="a1044-324">從商務用 Skype 用戶端到內部部署商務用 Skype 伺服器的信號和媒體不在本檔的範圍內。</span><span class="sxs-lookup"><span data-stu-id="a1044-324">Signaling and media from the Skype for Business client to an on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="a1044-325">不過，這裡有清楚的說明。</span><span class="sxs-lookup"><span data-stu-id="a1044-325">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="a1044-326">在團隊與商務用 Skype 之間的通知是由 Office 365 中的閘道橋接。</span><span class="sxs-lookup"><span data-stu-id="a1044-326">Signaling between Teams and Skype for Business is bridged by a gateway in Office 365.</span></span>

- <span data-ttu-id="a1044-327">媒體是透過整個流程4傳送到客戶網路，在 Office 365 中，透過團隊傳輸繼電器進行中繼。</span><span class="sxs-lookup"><span data-stu-id="a1044-327">Media is relayed through Teams Transport Relay in Office 365 to the customer network through flow 4.</span></span>

<span data-ttu-id="a1044-328">**含外部商務用 Skype 使用者的混合式客戶網路–由內部部署邊緣進行中繼**</span><span class="sxs-lookup"><span data-stu-id="a1044-328">**Hybrid customer network with external Skype for Business user – relayed by on-premises Edge**</span></span>

<span data-ttu-id="a1044-329">[![Microsoft 團隊線上通話流程圖16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)</span><span class="sxs-lookup"><span data-stu-id="a1044-329">[![Microsoft Teams Online Call Flows Figure 16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)</span></span>

<span data-ttu-id="a1044-330">*圖 16-含外部商務用 Skype 使用者的混合式客戶網路-透過內部部署邊緣進行中繼*</span><span class="sxs-lookup"><span data-stu-id="a1044-330">*Figure 16 - Hybrid customer network with external Skype for Business user - relayed by on-premises Edge*</span></span>
 
<span data-ttu-id="a1044-331">請注意：</span><span class="sxs-lookup"><span data-stu-id="a1044-331">Note that:</span></span>

- <span data-ttu-id="a1044-332">從商務用 Skype 用戶端到內部部署商務用 Skype 伺服器的信號及媒體不在本檔的範圍內。</span><span class="sxs-lookup"><span data-stu-id="a1044-332">Signaling and media from Skype for Business client to an on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="a1044-333">不過，這裡有清楚的說明。</span><span class="sxs-lookup"><span data-stu-id="a1044-333">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="a1044-334">在 Office 365 中，發網關會將信號橋接。</span><span class="sxs-lookup"><span data-stu-id="a1044-334">Signaling is bridged by a gateway in Office 365.</span></span>

- <span data-ttu-id="a1044-335">在商務用 Skype 內部部署邊緣，透過媒體流程5A 在客戶網路內，透過商務用 Skype 媒體轉送來中繼媒體。</span><span class="sxs-lookup"><span data-stu-id="a1044-335">Media is relayed by Skype for Business Media Relay within Skype for Business on-premises Edge to Teams user within the customer network via media flow 5A.</span></span>

### <a name="teams-with-phone-system-direct-routing-topology"></a><span data-ttu-id="a1044-336">使用電話系統直通路由拓朴的小組</span><span class="sxs-lookup"><span data-stu-id="a1044-336">Teams with Phone System Direct Routing topology</span></span>
<span data-ttu-id="a1044-337">此拓朴包括具有手機系統直接路由的小組。</span><span class="sxs-lookup"><span data-stu-id="a1044-337">This topology includes Teams with Phone System Direct Routing.</span></span> 

<span data-ttu-id="a1044-338">[直接路由] 可讓您使用協力廠商公用的電話網絡（PSTN）服務提供者，方法是將支援的內部部署客戶擁有的會話邊界控制器（SBC）硬體裝置與 Office 365 進行配對，然後將電話幹線連接到該裝置。</span><span class="sxs-lookup"><span data-stu-id="a1044-338">Direct Routing enables you to use a third-party Public Switched Telephone Network (PSTN) service provider by pairing a supported on-premises customer-owned Session Border Controller (SBC) hardware device to Office 365, and then connecting the telephony trunk to that device.</span></span> 

<span data-ttu-id="a1044-339">為了支援此案例，客戶必須部署一個認證的 SBC，以便直接從 Microsoft 認證合作夥伴中傳送。</span><span class="sxs-lookup"><span data-stu-id="a1044-339">To support this scenario, the customer must deploy a certified SBC for Direct Routing from one of Microsoft's certified partners.</span></span> <span data-ttu-id="a1044-340">SBC 必須根據供應商的建議進行設定，並可透過 Office 365 路由以進行直接的 UDP 流量。</span><span class="sxs-lookup"><span data-stu-id="a1044-340">The SBC must be configured as recommended by the vendor, and be routable from Office 365 for direct UDP traffic.</span></span> <span data-ttu-id="a1044-341">媒體可能直接從團隊和/或商務用 Skype 用戶端傳送至 SBC （繞過團隊閘道）或遍歷團隊閘道。</span><span class="sxs-lookup"><span data-stu-id="a1044-341">The media may flow directly from Teams and/or the Skype for Business client to the SBC (bypassing the Teams gateway) or traverse through the Teams gateway.</span></span> <span data-ttu-id="a1044-342">當主幹設定為略過團隊閘道時，與 sbc 的連線是依據 ICE，而 SBC 支援 ICE，而商務用 Skype 媒體端點支援全冰。</span><span class="sxs-lookup"><span data-stu-id="a1044-342">The connectivity with the SBC, when the trunk is configured to bypass the Teams gateway, is based on ICE, where SBC supports ICE-Lite, while the Teams/Skype for Business media endpoint supports ICE Full.</span></span> 

<span data-ttu-id="a1044-343">[![Microsoft 團隊線上通話流程圖17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)</span><span class="sxs-lookup"><span data-stu-id="a1044-343">[![Microsoft Teams Online Call Flows Figure 17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)</span></span>

<span data-ttu-id="a1044-344">\* 圖 17-使用電話系統直通路由拓撲的團隊</span><span class="sxs-lookup"><span data-stu-id="a1044-344">\*Figure 17 - Teams with Phone System Direct Routing topology</span></span>

<span data-ttu-id="a1044-345">請注意：</span><span class="sxs-lookup"><span data-stu-id="a1044-345">Note that:</span></span>

- <span data-ttu-id="a1044-346">上方圖表上的箭號方向反映了對企業週邊的連線所產生的溝通的起始方向。</span><span class="sxs-lookup"><span data-stu-id="a1044-346">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="a1044-347">在 UDP 的 [媒體] 中，第一個資料包可能會以相反的方向流向，但在其他方向的資料包都可能會遭到封鎖，直到其他方向的資料包流動為止。</span><span class="sxs-lookup"><span data-stu-id="a1044-347">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>

- <span data-ttu-id="a1044-348">團隊會與商務用 Skype Online 一起進行並排部署，因此用戶端會顯示為「團隊/SFB 使用者」。</span><span class="sxs-lookup"><span data-stu-id="a1044-348">Teams is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user".</span></span>

<span data-ttu-id="a1044-349">其他流程（在團隊線上拓朴之上）：</span><span class="sxs-lookup"><span data-stu-id="a1044-349">Additional flows (on top of Teams online topology):</span></span>
- <span data-ttu-id="a1044-350">[**流程 4** ]-代表從 Office 365 到客戶網路的流程，用來在雲端的小組媒體伺服器與 SBC 內部部署之間建立連線。</span><span class="sxs-lookup"><span data-stu-id="a1044-350">**Flow 4'** - Represents a flow from Office 365 to the customer network, used to establish a connection between the Teams media server in the cloud with the SBC on premises.</span></span>
- <span data-ttu-id="a1044-351">**流程 5b** –代表客戶網路中的小組使用者之間的媒體流程，並以旁路模式直接傳送 SBC。</span><span class="sxs-lookup"><span data-stu-id="a1044-351">**Flow 5B** – Represents a media flow between the Teams user within the customer network with the Direct Routing SBC in bypass mode.</span></span>
- <span data-ttu-id="a1044-352">**流程 5c** -代表在 PSTN hairpin 通話旁路模式中，直接路由 sbc 與另一個直接路由 sbc 之間的媒體流程。</span><span class="sxs-lookup"><span data-stu-id="a1044-352">**Flow 5C** – Represents a media flow between the Direct Routing SBC to another Direct Routing SBC in a PSTN hairpin call bypass mode.</span></span>

<span data-ttu-id="a1044-353">**具有直接路由的內部使用者（依團隊在 Office 365 中傳輸中繼的方式進行媒體轉送）**</span><span class="sxs-lookup"><span data-stu-id="a1044-353">**Internal user with Direct Routing (media relayed by Teams Transport Relay in Office 365)**</span></span>

<span data-ttu-id="a1044-354">[![Microsoft 團隊線上通話流程圖18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)</span><span class="sxs-lookup"><span data-stu-id="a1044-354">[![Microsoft Teams Online Call Flows Figure 18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)</span></span>

<span data-ttu-id="a1044-355">*圖 18-在 Office 365 中使用直接路由的內部使用者（依小組傳輸的媒體轉接）*</span><span class="sxs-lookup"><span data-stu-id="a1044-355">*Figure 18 - Internal user with Direct Routing (media relayed by Teams Transport Relay in Office 365)*</span></span>

<span data-ttu-id="a1044-356">請注意：</span><span class="sxs-lookup"><span data-stu-id="a1044-356">Note that:</span></span>
 
- <span data-ttu-id="a1044-357">SBC 必須有可從 Office 365 路由的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a1044-357">The SBC must have a public IP address that is routable from Office 365.</span></span>

- <span data-ttu-id="a1044-358">從 SBC 到 Office 365 的信號和媒體，反之亦然，請使用流程4和/或流程4。</span><span class="sxs-lookup"><span data-stu-id="a1044-358">Signaling and media from the SBC to Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="a1044-359">從客戶網路中用戶端到 Office 365 的傳送信號及媒體使用流程4。</span><span class="sxs-lookup"><span data-stu-id="a1044-359">Signaling and media from the client within the customer network to Office 365 use flow 4.</span></span>


<span data-ttu-id="a1044-360">**含直接路由的遠端使用者（透過 Office 365 中的媒體伺服器（MP）路由媒體）**</span><span class="sxs-lookup"><span data-stu-id="a1044-360">**Remote user with Direct Routing (media is routed through a media server (MP) in Office 365)**</span></span>

<span data-ttu-id="a1044-361">[![Microsoft 團隊線上通話流程圖19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)</span><span class="sxs-lookup"><span data-stu-id="a1044-361">[![Microsoft Teams Online Call Flows Figure 19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)</span></span>

<span data-ttu-id="a1044-362">*圖 19-有直接路由的遠端使用者（媒體是透過 Office 365 中的媒體伺服器（MP）路由）*</span><span class="sxs-lookup"><span data-stu-id="a1044-362">*Figure 19 - Remote user with Direct Routing (media is routed through a media server (MP) in Office 365)*</span></span>
 
<span data-ttu-id="a1044-363">請注意：</span><span class="sxs-lookup"><span data-stu-id="a1044-363">Note that:</span></span>

- <span data-ttu-id="a1044-364">SBC 必須有可從 Office 365 路由的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a1044-364">The SBC must have a public IP address that is routable from Office 365.</span></span>

- <span data-ttu-id="a1044-365">從 SBC 到 Office 365 的信號和媒體，反之亦然，請使用流程4和/或流程4。</span><span class="sxs-lookup"><span data-stu-id="a1044-365">Signaling and media from the SBC to Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="a1044-366">從網際網路上的用戶端傳送信號和媒體至 Office 365 使用流程3。</span><span class="sxs-lookup"><span data-stu-id="a1044-366">Signaling and media from the client on the Internet to Office 365 use flow 3.</span></span>

<span data-ttu-id="a1044-367">**內部使用者直接路由（媒體旁路）**</span><span class="sxs-lookup"><span data-stu-id="a1044-367">**Internal user Direct Routing (media bypass)**</span></span>

<span data-ttu-id="a1044-368">[![Microsoft 團隊線上通話流程圖20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)</span><span class="sxs-lookup"><span data-stu-id="a1044-368">[![Microsoft Teams Online Call Flows Figure 20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)</span></span>

<span data-ttu-id="a1044-369">*圖 20-內部使用者直接路由（媒體旁路）*</span><span class="sxs-lookup"><span data-stu-id="a1044-369">*Figure 20 - Internal user Direct Routing (media bypass)*</span></span>
 
<span data-ttu-id="a1044-370">請注意：</span><span class="sxs-lookup"><span data-stu-id="a1044-370">Note that:</span></span>

- <span data-ttu-id="a1044-371">SBC 必須有可從 Office 365 路由的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a1044-371">The SBC must have a public IP address that is routable from Office 365.</span></span>

- <span data-ttu-id="a1044-372">從 SBC 到 Office 365 的信號，反之亦然，使用流程4和/或流程4。</span><span class="sxs-lookup"><span data-stu-id="a1044-372">Signaling from SBC to Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="a1044-373">從客戶網路中的用戶端傳送給 Office 365 使用流程4。</span><span class="sxs-lookup"><span data-stu-id="a1044-373">Signaling from client within the customer network to Office 365 use flow 4.</span></span>

- <span data-ttu-id="a1044-374">從客戶網路中的用戶端傳送到客戶網路中的 SBC 的媒體使用流程5B。</span><span class="sxs-lookup"><span data-stu-id="a1044-374">Media from client within the customer network to SBC within the customer network use flow 5B.</span></span>

<span data-ttu-id="a1044-375">**具有直接路由的遠端使用者（由 Office 365 中的小組傳輸繼電器的媒體旁路中繼）**</span><span class="sxs-lookup"><span data-stu-id="a1044-375">**Remote user with Direct Routing (media bypass relayed by Teams Transport Relay in Office 365)**</span></span>

<span data-ttu-id="a1044-376">[![Microsoft 團隊線上通話流程圖21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)</span><span class="sxs-lookup"><span data-stu-id="a1044-376">[![Microsoft Teams Online Call Flows Figure 21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)</span></span>

<span data-ttu-id="a1044-377">*圖21：使用直接路由的遠端使用者（在 Office 365 中，由小組傳輸中繼的媒體旁路中繼）*</span><span class="sxs-lookup"><span data-stu-id="a1044-377">*Figure 21 - Remote user with Direct Routing (media bypass relayed by Teams Transport Relay in Office 365)*</span></span>

<span data-ttu-id="a1044-378">請注意：</span><span class="sxs-lookup"><span data-stu-id="a1044-378">Note that:</span></span>

- <span data-ttu-id="a1044-379">SBC 必須有可從 Office 365 和網際網路路由的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a1044-379">The SBC must have a public IP address that is routable from Office 365 and Internet.</span></span>

- <span data-ttu-id="a1044-380">從 SBC 到 Office 365 的信號，反之亦然，使用流程4和/或流程4。</span><span class="sxs-lookup"><span data-stu-id="a1044-380">Signaling from the SBC to Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="a1044-381">從網際網路上的用戶端傳送到 Office 365 的信號是使用流程3。</span><span class="sxs-lookup"><span data-stu-id="a1044-381">Signaling from the client on the Internet to Office 365 uses flow 3.</span></span>

- <span data-ttu-id="a1044-382">從網際網路上的用戶端到客戶網路中的 SBC 使用流程3和4，由 Office 365 中的小組傳輸繼電器來中繼。</span><span class="sxs-lookup"><span data-stu-id="a1044-382">Media from the client on the Internet to the SBC within the customer network uses flows 3 and 4, relayed by Teams Transport Relay in Office 365.</span></span> 

<span data-ttu-id="a1044-383">**遠端使用者直接路由（媒體旁路直接）**</span><span class="sxs-lookup"><span data-stu-id="a1044-383">**Remote user Direct Routing (media bypass direct)**</span></span>

<span data-ttu-id="a1044-384">[![Microsoft 團隊線上通話流程圖22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)</span><span class="sxs-lookup"><span data-stu-id="a1044-384">[![Microsoft Teams Online Call Flows Figure 22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)</span></span>

<span data-ttu-id="a1044-385">*圖 22-遠端使用者直接路由（媒體旁路直接）*</span><span class="sxs-lookup"><span data-stu-id="a1044-385">*Figure 22 - Remote user Direct Routing (media bypass direct)*</span></span>
 
<span data-ttu-id="a1044-386">請注意：</span><span class="sxs-lookup"><span data-stu-id="a1044-386">Note that:</span></span>

- <span data-ttu-id="a1044-387">SBC 必須有可透過 Office 365 和網際網路路由的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a1044-387">The SBC must have a public IP address that is routable from Office 365 and the Internet.</span></span>

- <span data-ttu-id="a1044-388">從 SBC 到 Office 365 的信號，反之亦然，使用流程4和/或流程4。</span><span class="sxs-lookup"><span data-stu-id="a1044-388">Signaling from the SBC to Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="a1044-389">從網際網路上的用戶端傳送到 Office 365 的信號是使用流程3。</span><span class="sxs-lookup"><span data-stu-id="a1044-389">Signaling from the client on the Internet to Office 365 uses flow 3.</span></span>

- <span data-ttu-id="a1044-390">從網際網路上的用戶端媒體到客戶網路中的 SBC 使用流程2。</span><span class="sxs-lookup"><span data-stu-id="a1044-390">Media from the client on the Internet to the SBC within the customer network uses flow 2.</span></span>

<span data-ttu-id="a1044-391">**直接路由（媒體旁路）-PSTN hairpin 通話（由於呼叫轉寄/轉接）**</span><span class="sxs-lookup"><span data-stu-id="a1044-391">**Direct Routing (media bypass) – PSTN hairpin call (due to call forward/transfer)**</span></span>

<span data-ttu-id="a1044-392">[![Microsoft 團隊線上通話流程圖23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)</span><span class="sxs-lookup"><span data-stu-id="a1044-392">[![Microsoft Teams Online Call Flows Figure 23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)</span></span>

<span data-ttu-id="a1044-393">*圖 23-直接路由（媒體旁路）-PSTN hairpin 通話（由於呼叫轉寄/轉接）*</span><span class="sxs-lookup"><span data-stu-id="a1044-393">*Figure 23 - Direct Routing (media bypass) - PSTN hairpin call (due to call forward/transfer)*</span></span>
 
<span data-ttu-id="a1044-394">請注意：</span><span class="sxs-lookup"><span data-stu-id="a1044-394">Note that:</span></span>

- <span data-ttu-id="a1044-395">SBC 必須有可從 Office 365 路由的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a1044-395">The SBC must have a public IP address that is routable from Office 365.</span></span>

- <span data-ttu-id="a1044-396">從 SBC 到 Office 365 的信號，反之亦然，使用流程4和/或流程4。</span><span class="sxs-lookup"><span data-stu-id="a1044-396">Signaling from the SBC to Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="a1044-397">從 PSTN 到 PSTN hairpinned 通話之後，用戶端就不在信號和媒體循環。</span><span class="sxs-lookup"><span data-stu-id="a1044-397">The client is out of the signaling and media loop after the call is hairpinned from PSTN to PSTN.</span></span>

- <span data-ttu-id="a1044-398">從客戶網路內部的 SBC 實例 A 到客戶網路內的 sbc 實例 B （其中 A 和 B 可以是相同實例）的媒體則使用流程5C。</span><span class="sxs-lookup"><span data-stu-id="a1044-398">Media from SBC instance A within the customer network to SBC instance B within the customer network (where, A and B can be the same instance) uses flow 5C.</span></span>

<span data-ttu-id="a1044-399">**直接路由（透過 Office 365 的媒體）-跨兩個租使用者的 PSTN hairpin 通話**</span><span class="sxs-lookup"><span data-stu-id="a1044-399">**Direct Routing (media through Office 365) – PSTN hairpin call across two tenants**</span></span>

<span data-ttu-id="a1044-400">[![Microsoft 團隊線上通話流程圖24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)</span><span class="sxs-lookup"><span data-stu-id="a1044-400">[![Microsoft Teams Online Call Flows Figure 24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)</span></span>

<span data-ttu-id="a1044-401">*圖 24-直接路由（透過 Office 365 的媒體）-跨兩個租使用者的 PSTN hairpin 通話*</span><span class="sxs-lookup"><span data-stu-id="a1044-401">*Figure 24 - Direct Routing (media through Office 365) – PSTN hairpin call across two tenants*</span></span>
 
<span data-ttu-id="a1044-402">請注意：</span><span class="sxs-lookup"><span data-stu-id="a1044-402">Note that:</span></span>

- <span data-ttu-id="a1044-403">SBC 必須有可從 Office 365 路由的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a1044-403">The SBC must have a public IP address that is routable from Office 365.</span></span>

- <span data-ttu-id="a1044-404">從 SBC 到 Office 365 的信號，反之亦然，使用流程4和/或流程4。</span><span class="sxs-lookup"><span data-stu-id="a1044-404">Signaling from the SBC to Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="a1044-405">從 PSTN 到 PSTN hairpinned 通話之後，用戶端就不在信號和媒體循環。</span><span class="sxs-lookup"><span data-stu-id="a1044-405">The client is out of the signaling and media loop after the call is hairpinned from PSTN to PSTN.</span></span>

- <span data-ttu-id="a1044-406">從位於客戶網路 X 至 SBC 實例 B 之 SBC 實例 A 的媒體，必須透過 Office 365 媒體伺服器中繼，且無法使用旁路模式。</span><span class="sxs-lookup"><span data-stu-id="a1044-406">Media from SBC instance A within the customer network X to SBC instance B must be relayed through the Office 365 Media Server and can't use bypass mode.</span></span>

## <a name="teams-with-express-route-optimization"></a><span data-ttu-id="a1044-407">具有快速路線優化的小組</span><span class="sxs-lookup"><span data-stu-id="a1044-407">Teams with Express Route optimization</span></span>

<span data-ttu-id="a1044-408">[![Microsoft 團隊線上通話流程圖25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)</span><span class="sxs-lookup"><span data-stu-id="a1044-408">[![Microsoft Teams Online Call Flows Figure 25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)</span></span>

<span data-ttu-id="a1044-409">*圖 25-具有快速路線優化的小組*</span><span class="sxs-lookup"><span data-stu-id="a1044-409">*Figure 25 - Teams with Express Route optimization*</span></span>
 
<span data-ttu-id="a1044-410">在直通路線已左右對齊和部署的情況下，小組流程可能會從流程4重新路由至流程1，並從流程4」重新路由至 [流程 1]。</span><span class="sxs-lookup"><span data-stu-id="a1044-410">In the case that Express Route is justified and deployed, then Teams flows could be re-routed from flow 4 to flow 1 and from flow 4' to flow 1'.</span></span> <span data-ttu-id="a1044-411">不過，小組應用程式會透過資料流程4和4，在網際網路上對其他 Office 365 流程產生硬性依賴性;因此，不一定會封鎖這些流程。</span><span class="sxs-lookup"><span data-stu-id="a1044-411">However, Teams Application has a hard dependency on other Office 365 flows over the internet via flows 4 and 4'; hence these flows must not be blocked.</span></span> 

<span data-ttu-id="a1044-412">請注意，商務用 Skype 混合式邊緣流量會路由到網際網路，而不是表示與外部使用者通訊，並與其他租使用者聯盟的路線。</span><span class="sxs-lookup"><span data-stu-id="a1044-412">Note that Skype for Business hybrid Edge traffic is routed to the Internet and not to Express Route to communicate with external users and federate with other tenants.</span></span> 

<span data-ttu-id="a1044-413">若要避免非對稱資料流程，必須在兩個方向之間進行重新路由。</span><span class="sxs-lookup"><span data-stu-id="a1044-413">To prevent asymmetrical flows, re-routing must be in both directions.</span></span> <span data-ttu-id="a1044-414">換句話說，在客戶網路中的位址是透過 [網際網路] 或 [快速路由] 進行路由，而不是透過優化，而是在這兩者中都可以。</span><span class="sxs-lookup"><span data-stu-id="a1044-414">In other words, an address within the customer network is routable either through Internet or Express Route, based on optimization, but not through both.</span></span>

<span data-ttu-id="a1044-415">例如：</span><span class="sxs-lookup"><span data-stu-id="a1044-415">For example:</span></span>

<span data-ttu-id="a1044-416">**外部使用者的客戶網路（依小組傳輸轉接的媒體轉送）：**</span><span class="sxs-lookup"><span data-stu-id="a1044-416">**Customer network to external user (media relayed by Teams Transport Relay):**</span></span>

<span data-ttu-id="a1044-417">[![Microsoft 團隊線上通話流程圖26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)</span><span class="sxs-lookup"><span data-stu-id="a1044-417">[![Microsoft Teams Online Call Flows Figure 26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)</span></span>

<span data-ttu-id="a1044-418">*圖 26-外部使用者的客戶網路（依小組傳輸轉接的媒體轉送）*</span><span class="sxs-lookup"><span data-stu-id="a1044-418">*Figure 26 - Customer network to external user (media relayed by Teams Transport Relay)*</span></span>
 
<span data-ttu-id="a1044-419">**高層次步驟：**</span><span class="sxs-lookup"><span data-stu-id="a1044-419">**High Level Steps:**</span></span>
1. <span data-ttu-id="a1044-420">客戶網路中的小組使用者可透過 flow2 解析 URL 功能變數名稱（DNS）</span><span class="sxs-lookup"><span data-stu-id="a1044-420">Teams User within customer network resolves URL domain name (DNS) via flow2</span></span>
2. <span data-ttu-id="a1044-421">客戶網路中的小組使用者會透過流程1在小組傳輸中繼上分配媒體轉送埠</span><span class="sxs-lookup"><span data-stu-id="a1044-421">Teams User within customer network allocates a media Relay port on Teams Transport Relay via flow 1</span></span>
3. <span data-ttu-id="a1044-422">在客戶網路中的小組使用者透過流程1到 Office 365 傳送「邀請」給 ICE 候選人</span><span class="sxs-lookup"><span data-stu-id="a1044-422">Teams User within customer network sends "invite" with ICE candidates via flow 1 to Office 365</span></span>
4. <span data-ttu-id="a1044-423">OFFICE 365 透過流程3將通知傳送給外部團隊使用者</span><span class="sxs-lookup"><span data-stu-id="a1044-423">OFFICE 365 sends notification to external Teams user via flow 3</span></span>
5. <span data-ttu-id="a1044-424">團隊外部使用者透過流程3在團隊傳輸中繼上分配媒體轉送埠</span><span class="sxs-lookup"><span data-stu-id="a1044-424">Teams external user allocates a media Relay port on Teams Transport Relay via flow 3</span></span>
6. <span data-ttu-id="a1044-425">團隊外部使用者透過流程3傳送「回答」與 ICE 候選人，然後透過流程3轉寄傳回給小組使用者 A</span><span class="sxs-lookup"><span data-stu-id="a1044-425">Teams external user sends "answer" with ICE candidates via flow 3, which is forwarded back to Teams user A via Flow 1</span></span>
7. <span data-ttu-id="a1044-426">小組使用者 A 與團隊使用者 B 呼叫 ICE 連線測試，並選取 [流程 1] 和 [3]，這些是由 Office 365 中的小組傳輸繼電器來中繼</span><span class="sxs-lookup"><span data-stu-id="a1044-426">Teams User A and Teams User B invoke ICE connectivity tests and selects flows 1 and 3, which are relayed by Teams Transport Relay in Office 365</span></span>
8. <span data-ttu-id="a1044-427">團隊使用者透過流程1和3，將遙測傳送至 Office 365</span><span class="sxs-lookup"><span data-stu-id="a1044-427">Teams Users send telemetry to Office 365 via flows 1 and 3</span></span>

><span data-ttu-id="a1044-428">**注意**：必須啟用流程4，才能支援在要求流程4的其他微服務上使用小組應用程式的相依性。</span><span class="sxs-lookup"><span data-stu-id="a1044-428">**Note**: Flow 4 must be enabled to support dependencies of Teams application on other micro-services that mandates flow 4.</span></span>
