---
title: Microsoft Teams 通話流程
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
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
description: 瞭解Teams如何使用Office 365拓撲中的流程，以及用於對等媒體通訊的唯一小組流程。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 27a2c68483c3d54cb3f3572bbed3a06a53ccc67e
ms.sourcegitcommit: 1ee9b1857f472a5b95352f7471c0cf21be6ea0c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2021
ms.locfileid: "52059207"
---
# <a name="microsoft-teams-call-flows"></a><span data-ttu-id="eecb0-103">Microsoft Teams 通話流程</span><span class="sxs-lookup"><span data-stu-id="eecb0-103">Microsoft Teams call flows</span></span>

> [!TIP]
> <span data-ttu-id="eecb0-104">請觀看此會話，瞭解Teams如何運用您的網路，以及如何規劃最佳的網路連接[：Teams規劃](https://aka.ms/teams-networking)。</span><span class="sxs-lookup"><span data-stu-id="eecb0-104">Watch this session to learn how Teams leverages your network and how to plan for optimal network connectivity: [Teams Network Planning](https://aka.ms/teams-networking).</span></span>

## <a name="overview"></a><span data-ttu-id="eecb0-105">概觀</span><span class="sxs-lookup"><span data-stu-id="eecb0-105">Overview</span></span>

<span data-ttu-id="eecb0-106">本文將說明如何在各種拓撲Teams Microsoft 365 Office 365通話流程。</span><span class="sxs-lookup"><span data-stu-id="eecb0-106">This article describes how Teams uses Microsoft 365 or Office 365 call flows in various topologies.</span></span> <span data-ttu-id="eecb0-107">此外，本文說明Teams對等媒體通訊的唯一流程。</span><span class="sxs-lookup"><span data-stu-id="eecb0-107">In addition, it describes unique Teams flows that are used for peer-to-peer media communication.</span></span> <span data-ttu-id="eecb0-108">檔說明這些流程、其用途，以及其來源和網路上終止。</span><span class="sxs-lookup"><span data-stu-id="eecb0-108">The document describes these flows, their purpose, and their origin and termination on the network.</span></span> <span data-ttu-id="eecb0-109">為了本文的目的，請假設下列各項：</span><span class="sxs-lookup"><span data-stu-id="eecb0-109">For purposes of this article, assume the following:</span></span>

- <span data-ttu-id="eecb0-110">Flow內部部署用戶端會使用 X 與雲端Microsoft 365或Office 365服務通訊。</span><span class="sxs-lookup"><span data-stu-id="eecb0-110">Flow X is used by the on-premises client to communicate with the Microsoft 365 or Office 365 service in the cloud.</span></span> <span data-ttu-id="eecb0-111">它來自客戶網路，並終止為 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="eecb0-111">It originates from the customer network, and it terminates as an endpoint in Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="eecb0-112">Flow內部部署用戶端會使用 Y 與網際網路上具有相依性Microsoft 365 Office 365通訊。</span><span class="sxs-lookup"><span data-stu-id="eecb0-112">Flow Y is used by the on-premises client to communicate with a service on the Internet that Microsoft 365 or Office 365 has a dependency on.</span></span> <span data-ttu-id="eecb0-113">它來自客戶網路，並終止為網際網路上的端點。</span><span class="sxs-lookup"><span data-stu-id="eecb0-113">It originates from the customer network, and it terminates as an endpoint on the Internet.</span></span>

<span data-ttu-id="eecb0-114">本文涵蓋下列資訊：</span><span class="sxs-lookup"><span data-stu-id="eecb0-114">This article covers the following information:</span></span>

- <span data-ttu-id="eecb0-115">**背景**。</span><span class="sxs-lookup"><span data-stu-id="eecb0-115">**Background**.</span></span> <span data-ttu-id="eecb0-116">提供背景資訊，例如流程可能經過的網路、流量類型、從客戶網路到 Microsoft 365 或 Office 365 服務端點的連接指引、協力廠商元件的互通性，以及 Teams 用來選取媒體流程的原則。</span><span class="sxs-lookup"><span data-stu-id="eecb0-116">Provides background information such as networks that the flows may traverse, types of traffic, connectivity guidance from the customer network to Microsoft 365 or Office 365 service endpoints, interoperability with third-party components, and principles that are used by Teams to select media flows.</span></span>

- <span data-ttu-id="eecb0-117">**各種拓撲中的通話流程**。</span><span class="sxs-lookup"><span data-stu-id="eecb0-117">**Call flows in various topologies**.</span></span> <span data-ttu-id="eecb0-118">說明各種拓撲中通話流的使用方式。</span><span class="sxs-lookup"><span data-stu-id="eecb0-118">Illustrates the use of call flows in various topologies.</span></span> <span data-ttu-id="eecb0-119">針對每個拓撲，該區段會列舉所有支援流程，並說明這些流程在數個使用案例中的使用方式。</span><span class="sxs-lookup"><span data-stu-id="eecb0-119">For each topology, the section enumerates all supported flows and illustrates how these flows are used in several use cases.</span></span> <span data-ttu-id="eecb0-120">針對每個使用案例，它會使用流程圖說明流程的順序和選取範圍。</span><span class="sxs-lookup"><span data-stu-id="eecb0-120">For each use case, it describes the sequence and selection of flows using a flow diagram.</span></span>

- <span data-ttu-id="eecb0-121">**Teams快速路由優化 。**</span><span class="sxs-lookup"><span data-stu-id="eecb0-121">**Teams with Express Route optimization**.</span></span> <span data-ttu-id="eecb0-122">說明如何在部署 Express Route 進行優化時使用這些流程，以簡單拓撲說明。</span><span class="sxs-lookup"><span data-stu-id="eecb0-122">Describes how these flows are used when Express Route is deployed for optimization, illustrated using a simple topology.</span></span>

## <a name="background"></a><span data-ttu-id="eecb0-123">背景</span><span class="sxs-lookup"><span data-stu-id="eecb0-123">Background</span></span>

### <a name="network-segments"></a><span data-ttu-id="eecb0-124">網路區段</span><span class="sxs-lookup"><span data-stu-id="eecb0-124">Network segments</span></span>

<span data-ttu-id="eecb0-125">**客戶網路**。</span><span class="sxs-lookup"><span data-stu-id="eecb0-125">**Customer network**.</span></span> <span data-ttu-id="eecb0-126">這是您控制和管理的網路區段。</span><span class="sxs-lookup"><span data-stu-id="eecb0-126">This is the network segment that you control and manage.</span></span> <span data-ttu-id="eecb0-127">這包括客戶辦公室內的所有客戶連結，無論是有線或無線網路、辦公室大樓之間的連接、內部部署資料中心的連線，以及您與網際網路提供者、Express Route 或任何其他私人對等互連的關聯。</span><span class="sxs-lookup"><span data-stu-id="eecb0-127">This includes all customer connections within customer offices, whether wired or wireless, connections between office buildings, connections to on-premises datacenters, and your connections to Internet providers, Express Route, or any other private peering.</span></span>

<span data-ttu-id="eecb0-128">一般來說，客戶網路具有數個網路周邊與防火牆和/或 Proxy 伺服器，會強制執行貴組織的安全性原則，而且只允許您設定和設定的某些網路流量。</span><span class="sxs-lookup"><span data-stu-id="eecb0-128">Typically, a customer network has several network perimeters with firewalls and/or proxy servers, which enforce your organization's security policies, and that only allow certain network traffic that you have set up and configured.</span></span> <span data-ttu-id="eecb0-129">由於您管理此網路，因此您可以直接控制網路的表現，因此我們建議您完成網路評定，以驗證網路內的網站，以及從網路到 Microsoft 365 或 Office 365 網路之間的績效。</span><span class="sxs-lookup"><span data-stu-id="eecb0-129">Because you manage this network, you have direct control over the performance of the network, and we recommend that you complete network assessments to validate performance both within sites in your network and from your network to the Microsoft 365 or Office 365 network.</span></span>

<span data-ttu-id="eecb0-130">**網際網路**。</span><span class="sxs-lookup"><span data-stu-id="eecb0-130">**Internet**.</span></span> <span data-ttu-id="eecb0-131">這是網路區段，屬於您整體網路的一部分，由從客戶網路外部Microsoft 365或Office 365使用者使用。</span><span class="sxs-lookup"><span data-stu-id="eecb0-131">This is the network segment that is part of your overall network that will be used by users who are connecting to Microsoft 365 or Office 365 from outside of the customer network.</span></span> <span data-ttu-id="eecb0-132">一些來自客戶網路的流量也會使用Microsoft 365 Office 365。</span><span class="sxs-lookup"><span data-stu-id="eecb0-132">It is also used by some traffic from the customer network to Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="eecb0-133">**已流覽或來賓私人網路絡**。</span><span class="sxs-lookup"><span data-stu-id="eecb0-133">**Visited or guest private network**.</span></span> <span data-ttu-id="eecb0-134">這是客戶網路外部的網路區段，而非公用網際網路中的網路區段，您的使用者及其來賓可能會流覽 (，例如家用私人網路絡或企業私人網路絡，不會部署 Teams，而您的使用者及其客戶與 Teams 服務互動的位置可能位於) 。</span><span class="sxs-lookup"><span data-stu-id="eecb0-134">This is the network segment outside your customer network, but not in the public Internet, that your users and their guests may visit (for example, a home private network or an enterprise private network, that does not deploy Teams, where your users and their customers that interact with Teams services may reside).</span></span>

> [!NOTE]
> <span data-ttu-id="eecb0-135">與Microsoft 365或Office 365的連接也適用于這些網路。</span><span class="sxs-lookup"><span data-stu-id="eecb0-135">Connectivity to Microsoft 365 or Office 365 is also applicable to these networks.</span></span>

<span data-ttu-id="eecb0-136">**Microsoft 365 或 Office 365。**</span><span class="sxs-lookup"><span data-stu-id="eecb0-136">**Microsoft 365 or Office 365**.</span></span> <span data-ttu-id="eecb0-137">這是支援服務或Microsoft 365 Office 365區段。</span><span class="sxs-lookup"><span data-stu-id="eecb0-137">This is the network segment that supports Microsoft 365 or Office 365 services.</span></span> <span data-ttu-id="eecb0-138">它在全球分佈，大部分位置的邊緣都靠近客戶網路。</span><span class="sxs-lookup"><span data-stu-id="eecb0-138">It is distributed worldwide with edges in proximity to the customer network in most locations.</span></span> <span data-ttu-id="eecb0-139">函數包括傳輸轉場、會議服務器和媒體處理器。</span><span class="sxs-lookup"><span data-stu-id="eecb0-139">Functions include Transport Relay, conferencing server, and Media Processor.</span></span>

<span data-ttu-id="eecb0-140">**Express Route (選) 。**</span><span class="sxs-lookup"><span data-stu-id="eecb0-140">**Express Route (optional)**.</span></span> <span data-ttu-id="eecb0-141">這是您整體網路的一部分網路區段，可為您提供專用、私人的網Microsoft 365或Office 365連接。</span><span class="sxs-lookup"><span data-stu-id="eecb0-141">This is the network segment that is part of your overall network that will give you a dedicated, private connection to the Microsoft 365 or Office 365 network.</span></span>

### <a name="types-of-traffic"></a><span data-ttu-id="eecb0-142">流量類型</span><span class="sxs-lookup"><span data-stu-id="eecb0-142">Types of traffic</span></span>

<span data-ttu-id="eecb0-143">**即時媒體**。</span><span class="sxs-lookup"><span data-stu-id="eecb0-143">**Real-time media**.</span></span> <span data-ttu-id="eecb0-144">封裝在即時傳輸通訊通訊協定 (RTP) 支援音訊、視視和螢幕共用工作負載的資料。</span><span class="sxs-lookup"><span data-stu-id="eecb0-144">Data encapsulated within Real-time Transport Protocol (RTP) that supports audio, video, and screen sharing workloads.</span></span> <span data-ttu-id="eecb0-145">一般而言，媒體流量對延遲高度敏感，因此您希望此流量採用盡可能最直接的路徑，並使用 UDP 與 TCP 做為傳輸層通訊協定，這是從品質角度分析互動式即時媒體的最佳傳輸方式。</span><span class="sxs-lookup"><span data-stu-id="eecb0-145">In general, media traffic is highly latency sensitive, so you would want this traffic to take the most direct path possible, and to use UDP versus TCP as the transport layer protocol, which is the best transport for interactive real-time media from a quality perspective.</span></span> <span data-ttu-id="eecb0-146"> (請注意，媒體可以使用 TCP/IP，也可以在 HTTP 通訊協定內進行加密，但因為品質影響不佳，不建議使用 ) RTP 流程，因為 SRTP 只會加密有效負載。</span><span class="sxs-lookup"><span data-stu-id="eecb0-146">(Note that as a last resort, media can use TCP/IP and also be tunneled within the HTTP protocol, but it is not recommended due to bad quality implications.) RTP flow is secured using SRTP, in which only the payload is encrypted.</span></span>

<span data-ttu-id="eecb0-147">**訊號**。</span><span class="sxs-lookup"><span data-stu-id="eecb0-147">**Signaling**.</span></span> <span data-ttu-id="eecb0-148">用戶端與伺服器之間的通訊連結，或其他用來控制活動的用戶端 (例如，在通話) 傳送立即訊息。</span><span class="sxs-lookup"><span data-stu-id="eecb0-148">The communication link between the client and server, or other clients that are used to control activities (for example, when a call is initiated), and deliver instant messages.</span></span> <span data-ttu-id="eecb0-149">大多數訊號流量使用 HTTPS 型 REST 介面，但在某些情況下 (例如 Microsoft 365 或 Office 365 與會話邊界控制器之間的) 使用 SIP 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="eecb0-149">Most signaling traffic uses the HTTPS-based REST interfaces, though in some scenarios (for example, connection between Microsoft 365 or Office 365 and a Session Border Controller) it uses SIP protocol.</span></span> <span data-ttu-id="eecb0-150">請注意，此流量對於延遲的敏感性要低得多，但如果端點之間的延遲超過數秒，可能會導致服務中斷或通話超時。</span><span class="sxs-lookup"><span data-stu-id="eecb0-150">It's important to understand that this traffic is much less sensitive to latency but may cause service outages or call timeouts if latency between the endpoints exceeds several seconds.</span></span>

### <a name="connectivity-to-microsoft-365-or-office-365"></a><span data-ttu-id="eecb0-151">與 Microsoft 365 或 Office 365</span><span class="sxs-lookup"><span data-stu-id="eecb0-151">Connectivity to Microsoft 365 or Office 365</span></span>

<span data-ttu-id="eecb0-152">Teams[需要網際網路的網際網路連接](/office365/enterprise/assessing-network-connectivity)。</span><span class="sxs-lookup"><span data-stu-id="eecb0-152">Teams requires [connectivity to the Internet](/office365/enterprise/assessing-network-connectivity).</span></span> <span data-ttu-id="eecb0-153">Teams URL 和 IP 位址範圍列于 Office 365 [URL 和 IP 位址範圍中](/office365/enterprise/urls-and-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="eecb0-153">Teams endpoint URLs and IP address ranges are listed in [Office 365 URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges).</span></span> <span data-ttu-id="eecb0-154"> (請注意，您必須開啟 TCP 埠 80 和 443 以及 UDP 埠 3478 到 3481 的連線。) 此外，Teams 與 商務用 Skype Online 有相依性，也必須連線至網際網路。</span><span class="sxs-lookup"><span data-stu-id="eecb0-154">(Note that open connectivity to TCP ports 80 and 443, and to UDP ports 3478 through 3481, is required.) Furthermore, Teams has a dependency on Skype for Business Online, which must also be connected to the Internet.</span></span>

<span data-ttu-id="eecb0-155">Teams使用標準 IETF 互動式連接建立 (ICE) 流程連接。</span><span class="sxs-lookup"><span data-stu-id="eecb0-155">Teams media flows connectivity is implemented using standard IETF Interactive Connectivity Establishment (ICE) procedures.</span></span>

### <a name="interoperability-restrictions"></a><span data-ttu-id="eecb0-156">互通性限制</span><span class="sxs-lookup"><span data-stu-id="eecb0-156">Interoperability restrictions</span></span>

<span data-ttu-id="eecb0-157">**協力廠商媒體轉場**。</span><span class="sxs-lookup"><span data-stu-id="eecb0-157">**Third-party media relays**.</span></span> <span data-ttu-id="eecb0-158">一Teams媒體流程 (，也就是說，其中一個媒體端點Teams) 只可Teams或商務用 Skype原生媒體轉場。</span><span class="sxs-lookup"><span data-stu-id="eecb0-158">A Teams media flow (that is, where one of the media endpoints is Teams) may traverse only Teams or Skype for Business native media relays.</span></span> <span data-ttu-id="eecb0-159">不支援協力廠商媒體轉場的互通性。</span><span class="sxs-lookup"><span data-stu-id="eecb0-159">Interoperability with a third-party media relay is not supported.</span></span> <span data-ttu-id="eecb0-160"> (請注意，與 PSTN 邊界上的協力廠商 SBC 必須終止 RTP/RTCP 資料流程，使用 SRTP 保護，不得轉傳至下一個躍點。) </span><span class="sxs-lookup"><span data-stu-id="eecb0-160">(Note that a third-party SBC on the boundary with PSTN must terminate RTP/RTCP stream, secured using SRTP, and not relay it to the next hop.)</span></span>

<span data-ttu-id="eecb0-161">**協力廠商 SIP Proxy 伺服器**。</span><span class="sxs-lookup"><span data-stu-id="eecb0-161">**Third-party SIP proxy servers**.</span></span> <span data-ttu-id="eecb0-162">使用Teams SBC 和/或閘道來傳訊 SIP 對話方塊時，可能會Teams或商務用 Skype SIP 代理。</span><span class="sxs-lookup"><span data-stu-id="eecb0-162">A Teams signaling SIP dialog with a third-party SBC and/or gateway may traverse Teams or Skype for Business native SIP proxies.</span></span> <span data-ttu-id="eecb0-163">不支援協力廠商 SIP Proxy 的互通性。</span><span class="sxs-lookup"><span data-stu-id="eecb0-163">Interoperability with a third-party SIP proxy is not supported.</span></span>

<span data-ttu-id="eecb0-164">**協力廠商 B2BUA (或 SBC) 。**</span><span class="sxs-lookup"><span data-stu-id="eecb0-164">**Third-party B2BUA (or SBC)**.</span></span> <span data-ttu-id="eecb0-165">第Teams SBC 會終止來自 PSTN 的媒體流程。</span><span class="sxs-lookup"><span data-stu-id="eecb0-165">A Teams media flow to and from the PSTN is terminated by a third-party SBC.</span></span> <span data-ttu-id="eecb0-166">不過，不支援協力廠商 SBC 在 Teams 網路 (中與協力廠商 SBC 之間的互通性Teams或 商務用 Skype端點) 。</span><span class="sxs-lookup"><span data-stu-id="eecb0-166">However, interoperability with a third-party SBC within the Teams network (where a third-party SBC mediates two Teams or Skype for Business endpoints) is not supported.</span></span>

### <a name="technologies-that-are-not-recommended-with-microsoft-teams"></a><span data-ttu-id="eecb0-167">不建議使用 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="eecb0-167">Technologies that are not recommended with Microsoft Teams</span></span>

<span data-ttu-id="eecb0-168">**VPN 網路**。</span><span class="sxs-lookup"><span data-stu-id="eecb0-168">**VPN network**.</span></span> <span data-ttu-id="eecb0-169">不建議媒體流量 (流程 2') 。</span><span class="sxs-lookup"><span data-stu-id="eecb0-169">It is not recommended for media traffic (or flow 2').</span></span> <span data-ttu-id="eecb0-170">VPN 用戶端應該使用分割Teams路由媒體流量，就像任何外部非 VPN 使用者一樣，如啟用 Lync 媒體以避開 VPN 管道[所指定](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Enabling-Lync-Media-to-Bypass-a-VPN-Tunnel/ba-p/620210)。</span><span class="sxs-lookup"><span data-stu-id="eecb0-170">The VPN client should use split tunneling and route Teams media traffic like any external non-VPN user, as specified in [Enabling Lync media to bypass a VPN tunnel](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Enabling-Lync-Media-to-Bypass-a-VPN-Tunnel/ba-p/620210).</span></span>

> [!NOTE]
> <span data-ttu-id="eecb0-171">雖然標題表示 Lync，但也適用于Teams Lync。</span><span class="sxs-lookup"><span data-stu-id="eecb0-171">Although the title indicates Lync, it is applicable to Teams as well.</span></span>

<span data-ttu-id="eecb0-172">**封包圖形器**。</span><span class="sxs-lookup"><span data-stu-id="eecb0-172">**Packet shapers**.</span></span> <span data-ttu-id="eecb0-173">不建議在媒體流量中使用任何類型的封包Teams、封包檢查或封包圖形器裝置，而且可能會大幅降低品質。</span><span class="sxs-lookup"><span data-stu-id="eecb0-173">Any kind of packet snipper, packet inspection, or packet shaper devices are not recommended for Teams media traffic and may degrade quality significantly.</span></span>

### <a name="principles"></a><span data-ttu-id="eecb0-174">原則</span><span class="sxs-lookup"><span data-stu-id="eecb0-174">Principles</span></span>

<span data-ttu-id="eecb0-175">有四項一般原則可協助您瞭解通話流程Microsoft Teams：</span><span class="sxs-lookup"><span data-stu-id="eecb0-175">There are four general principles that help you understand call flows for Microsoft Teams:</span></span>

- <span data-ttu-id="eecb0-176">會議Microsoft Teams由第一Microsoft 365 Office 365參與者加入之同一地區的人員主持。</span><span class="sxs-lookup"><span data-stu-id="eecb0-176">A Microsoft Teams conference is hosted by Microsoft 365 or Office 365 in the same region where the first participant joined.</span></span> <span data-ttu-id="eecb0-177"> (請注意，如果某些拓撲中此規則有例外，將在本檔中說明這些例外，並以適當的通話流程說明。) </span><span class="sxs-lookup"><span data-stu-id="eecb0-177">(Note that if there are exceptions to this rule in some topologies, they will be described in this document and illustrated by an appropriate call flow.)</span></span>

- <span data-ttu-id="eecb0-178">Teams或Microsoft 365媒體端點Office 365媒體處理需求使用，而不是根據通話類型使用。</span><span class="sxs-lookup"><span data-stu-id="eecb0-178">A Teams media endpoint in Microsoft 365 or Office 365 is used based on media processing needs and not based on call type.</span></span> <span data-ttu-id="eecb0-179"> (例如，點對點通話可能會使用雲端中的媒體端點來處理媒體的抄寫或錄製，而有兩個參與者的會議可能不會在雲端使用任何媒體端點。) 不過，大部分會議都會使用媒體端點進行混合和路由，而該目的會配置在會議舉辦地點。</span><span class="sxs-lookup"><span data-stu-id="eecb0-179">(For example, a point-to-point call may use a media endpoint in the cloud to process media for transcription or recording, while a conference with two participants may not use any media endpoint in the cloud.) However, most conferences will use a media endpoint for mixing and routing purposes, allocated where the conference is hosted.</span></span> <span data-ttu-id="eecb0-180">從用戶端傳送至媒體端點的媒體流量可能會直接路由，或因客戶網路防火牆限制Microsoft 365或 Office 365使用傳輸轉送。</span><span class="sxs-lookup"><span data-stu-id="eecb0-180">The media traffic sent from a client to the media endpoint may be routed directly or use a Transport Relay in Microsoft 365 or Office 365 if required due to customer network firewall restrictions.</span></span>

- <span data-ttu-id="eecb0-181">對等通話的媒體流量會採用可用的最直接路由，假設通話未強制使用雲端中的媒體端點 (請參閱先前的) 。</span><span class="sxs-lookup"><span data-stu-id="eecb0-181">Media traffic for peer-to-peer calls takes the most direct route that is available, assuming that the call doesn't mandate a media endpoint in the cloud (see previous principle).</span></span> <span data-ttu-id="eecb0-182">偏好的路由會直接傳送至遠端對等 (用戶端) ，但如果該路由不可用，則一或多個傳輸轉場會轉傳流量。</span><span class="sxs-lookup"><span data-stu-id="eecb0-182">The preferred route is direct to the remote peer (client), but if that route isn't available, then one or more Transport Relays will relay traffic.</span></span> <span data-ttu-id="eecb0-183">建議媒體流量不得轉譯伺服器，例如封包圖形器、VPN 伺服器等，因為這會影響媒體質量。</span><span class="sxs-lookup"><span data-stu-id="eecb0-183">It is recommended that media traffic shall not transverse servers such as packet shapers, VPN servers, and so on, since this will impact the media quality.</span></span>

- <span data-ttu-id="eecb0-184">訊號流量一直會進入最接近使用者的伺服器。</span><span class="sxs-lookup"><span data-stu-id="eecb0-184">Signaling traffic always goes to the closest server to the user.</span></span>

<span data-ttu-id="eecb0-185">若要深入瞭解所選媒體路徑的詳細資訊，請參閱瞭解 Microsoft Teams [- BRK4016](https://www.youtube.com/watch?v=1tmHMIlAQdo)中的媒體流程。</span><span class="sxs-lookup"><span data-stu-id="eecb0-185">To learn more about the details on the media path that is chosen, see [Understanding Media Flows in Microsoft Teams - BRK4016](https://www.youtube.com/watch?v=1tmHMIlAQdo).</span></span>

## <a name="call-flows-in-various-topologies"></a><span data-ttu-id="eecb0-186">各種拓撲中的通話流程</span><span class="sxs-lookup"><span data-stu-id="eecb0-186">Call flows in various topologies</span></span>

### <a name="teams-topology"></a><span data-ttu-id="eecb0-187">Teams拓撲</span><span class="sxs-lookup"><span data-stu-id="eecb0-187">Teams topology</span></span>

<span data-ttu-id="eecb0-188">此拓撲是由使用雲端Teams服務的客戶所使用，而不需要任何內部部署，例如 商務用 Skype Server 或 電話系統路由。</span><span class="sxs-lookup"><span data-stu-id="eecb0-188">This topology is used by customers that leverage Teams services from the cloud without any on-premises deployment, such as Skype for Business Server or Phone System Direct Routing.</span></span> <span data-ttu-id="eecb0-189">此外，無需 Azure Express 路由Microsoft 365或Office 365的介面即可在網際網路上完成。</span><span class="sxs-lookup"><span data-stu-id="eecb0-189">In addition, the interface to Microsoft 365 or Office 365 is done over the Internet without Azure Express Route.</span></span>

<span data-ttu-id="eecb0-190">[![Microsoft Teams線上通話流程圖 01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)</span><span class="sxs-lookup"><span data-stu-id="eecb0-190">[![Microsoft Teams Online Call Flows Figure 01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)</span></span>

<span data-ttu-id="eecb0-191">*圖 1 - Teams拓撲*</span><span class="sxs-lookup"><span data-stu-id="eecb0-191">*Figure 1 - Teams topology*</span></span>

<span data-ttu-id="eecb0-192">請注意：</span><span class="sxs-lookup"><span data-stu-id="eecb0-192">Note that:</span></span>

- <span data-ttu-id="eecb0-193">上圖中箭的方向會反映影響企業周邊連接之通訊的起始方向。</span><span class="sxs-lookup"><span data-stu-id="eecb0-193">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="eecb0-194">在媒體用 UDP 的情況下，第一個封包 () 可能會以相反方向流動，但這些封包可能會封鎖，直到其他方向的封包流程。</span><span class="sxs-lookup"><span data-stu-id="eecb0-194">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>
- <span data-ttu-id="eecb0-195">Teams與 商務用 Skype並排部署，因此用戶端會顯示為「Teams/SFB 使用者」。</span><span class="sxs-lookup"><span data-stu-id="eecb0-195">Teams is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user."</span></span>

<span data-ttu-id="eecb0-196">您可以在本文稍後找到下列選擇性拓撲的更多相關資訊：</span><span class="sxs-lookup"><span data-stu-id="eecb0-196">You can find more information on the following optional topologies later in the article:</span></span>

- <span data-ttu-id="eecb0-197">商務用 Skype混合拓撲中說明內部部署 **Teams部署**。</span><span class="sxs-lookup"><span data-stu-id="eecb0-197">Skype for Business on-premises deployment is described in **Teams hybrid topology**.</span></span>
- <span data-ttu-id="eecb0-198">電話系統PSTN (的直接路由) 描述于 Teams **路由拓撲中**。</span><span class="sxs-lookup"><span data-stu-id="eecb0-198">Phone System Direct Routing (for PSTN connectivity) is described in **Teams with Direct Routing topology**.</span></span>
- <span data-ttu-id="eecb0-199">Express Route 在 Teams **快速路由優化中描述**。</span><span class="sxs-lookup"><span data-stu-id="eecb0-199">Express Route is described in **Teams with Express Route optimization**.</span></span>

<span data-ttu-id="eecb0-200">**Flow描述**：</span><span class="sxs-lookup"><span data-stu-id="eecb0-200">**Flow descriptions**:</span></span>

- <span data-ttu-id="eecb0-201">**Flow 2** – 代表客戶網路上使用者啟動到網際網路的流量，作為使用者體驗Teams一部分。</span><span class="sxs-lookup"><span data-stu-id="eecb0-201">**Flow 2** – Represents a flow initiated by a user on the customer network to the Internet as a part of the user's Teams experience.</span></span> <span data-ttu-id="eecb0-202">這些流程的範例為 DNS 和對等媒體。</span><span class="sxs-lookup"><span data-stu-id="eecb0-202">Examples of these flows are DNS and peer-to-peer media.</span></span>
- <span data-ttu-id="eecb0-203">**Flow 2'** – 代表由遠端行動Teams使用者所發起的流程，使用 VPN 到客戶網路。</span><span class="sxs-lookup"><span data-stu-id="eecb0-203">**Flow 2'** – Represents a flow initiated by a remote mobile Teams user, with VPN to the customer network.</span></span>
- <span data-ttu-id="eecb0-204">**Flow 3** – 代表由遠端行動Teams使用者啟動Microsoft 365或Office 365/Teams流程。</span><span class="sxs-lookup"><span data-stu-id="eecb0-204">**Flow 3** – Represents a flow initiated by a remote mobile Teams user to Microsoft 365 or Office 365/Teams endpoints.</span></span>
- <span data-ttu-id="eecb0-205">**Flow 4** – 代表客戶網路上使用者啟動以Microsoft 365或Office 365/Teams流程。</span><span class="sxs-lookup"><span data-stu-id="eecb0-205">**Flow 4** – Represents a flow initiated by a user on the customer network to Microsoft 365 or Office 365/Teams endpoints.</span></span>
- <span data-ttu-id="eecb0-206">**Flow 5** – 代表客戶網路內使用者與另Teams使用者Teams或商務用 Skype之間的對等媒體流程。</span><span class="sxs-lookup"><span data-stu-id="eecb0-206">**Flow 5** – Represents a peer-to-peer media flow between a Teams user and another Teams or Skype for Business user within the customer network.</span></span>
- <span data-ttu-id="eecb0-207">**Flow 6** – 代表遠端行動Teams使用者與另一個遠端行動Teams或商務用 Skype使用者之間的對等媒體流程。</span><span class="sxs-lookup"><span data-stu-id="eecb0-207">**Flow 6** – Represents a peer-to-peer media flow between a remote mobile Teams user and another remote mobile Teams or Skype for Business user over the Internet.</span></span>

#### <a name="use-case-one-to-one"></a><span data-ttu-id="eecb0-208">使用案例：一對一</span><span class="sxs-lookup"><span data-stu-id="eecb0-208">Use case: One-to-one</span></span>

<span data-ttu-id="eecb0-209">一對一通話使用一般模型，來電者會取得一組包含 IP 位址/埠的候選者，包括用戶端的 ip 位址、轉傳和反射式 (公用 IP 位址，如轉傳) 候選者所看見。</span><span class="sxs-lookup"><span data-stu-id="eecb0-209">One-to-one calls use a common model in which the caller will obtain a set of candidates consisting of IP addresses/ports, including local, relay, and reflexive (public IP address of client as seen by the relay) candidates.</span></span> <span data-ttu-id="eecb0-210">來電者會傳送這些候選者給被叫方;被叫方也會取得一組類似的候選者，並將他們傳送給來電者。</span><span class="sxs-lookup"><span data-stu-id="eecb0-210">The caller sends these candidates to the called party; the called party also obtains a similar set of candidates and sends them to the caller.</span></span> <span data-ttu-id="eecb0-211">STUN 連接檢查訊息會用來尋找哪些來電者/稱為方媒體路徑可以工作，並選取最佳工作路徑。</span><span class="sxs-lookup"><span data-stu-id="eecb0-211">STUN connectivity check messages are used to find which caller/called party media paths work, and the best working path is selected.</span></span> <span data-ttu-id="eecb0-212">媒體 (，即使用 SRTP 保護的 RTP/RTCP 封包) 然後使用選取的候選組來送出。</span><span class="sxs-lookup"><span data-stu-id="eecb0-212">Media (that is, RTP/RTCP packets secured using SRTP) are then sent using the selected candidate pair.</span></span> <span data-ttu-id="eecb0-213">傳輸轉場是部署在 Microsoft 365 Office 365。</span><span class="sxs-lookup"><span data-stu-id="eecb0-213">The Transport relay is deployed as part of Microsoft 365 and Office 365.</span></span>

<span data-ttu-id="eecb0-214">如果本地 IP 位址/埠候選者或反射式候選者具有連線性，則媒體會選取用戶端 (或使用 NAT) 之間的直接路徑。</span><span class="sxs-lookup"><span data-stu-id="eecb0-214">If the local IP address/port candidates or the reflexive candidates have connectivity, then the direct path between the clients (or using a NAT) will be selected for media.</span></span> <span data-ttu-id="eecb0-215">如果用戶端都位於客戶網路上，則應該選取直接路徑。</span><span class="sxs-lookup"><span data-stu-id="eecb0-215">If the clients are both on the customer network, then the direct path should be selected.</span></span> <span data-ttu-id="eecb0-216">這需要客戶網路內的直接 UDP 連接。</span><span class="sxs-lookup"><span data-stu-id="eecb0-216">This requires direct UDP connectivity within the customer network.</span></span> <span data-ttu-id="eecb0-217">如果用戶端都是移動雲端使用者，則根據 NAT/防火牆，媒體可能會使用直接連接。</span><span class="sxs-lookup"><span data-stu-id="eecb0-217">If the clients are both nomadic cloud users, then depending on the NAT/firewall, media may use direct connectivity.</span></span>

<span data-ttu-id="eecb0-218">如果客戶網路上有一個用戶端是內部用戶端，而一個用戶端是外部 (例如行動雲端使用者) ，則本地或反身候選者之間的直接連接不太可能正常。</span><span class="sxs-lookup"><span data-stu-id="eecb0-218">If one client is internal on the customer network and one client is external (for example, a mobile cloud user), then it is unlikely that direct connectivity between the local or reflexive candidates is working.</span></span> <span data-ttu-id="eecb0-219">在這種情況下，一個選項是使用用戶端 (的其中一個傳輸轉場候選項目，例如，內部用戶端從 Microsoft 365 或 Office 365 傳輸轉場取得轉場候選者;外部用戶端必須能夠將 STUN/RTP/RTCP 封包傳送至傳輸轉) 。</span><span class="sxs-lookup"><span data-stu-id="eecb0-219">In this case, an option is to use one of the Transport Relay candidates from either client (for example, the internal client obtained a relay candidate from the Transport relay in Microsoft 365 or Office 365; the external client needs to be able to send STUN/RTP/RTCP packets to the transport relay).</span></span> <span data-ttu-id="eecb0-220">另一個選項是內部用戶端傳送給行動雲端用戶端所取得之轉送候選者。</span><span class="sxs-lookup"><span data-stu-id="eecb0-220">Another option is the internal client sends to the relay candidate obtained by the mobile cloud client.</span></span> <span data-ttu-id="eecb0-221">請注意，雖然強烈建議使用媒體的 UDP 連接，但支援 TCP。</span><span class="sxs-lookup"><span data-stu-id="eecb0-221">Note that, although UDP connectivity for media is highly recommended, TCP is supported.</span></span>

<span data-ttu-id="eecb0-222">**高層級步驟**：</span><span class="sxs-lookup"><span data-stu-id="eecb0-222">**High-level steps**:</span></span>

1. <span data-ttu-id="eecb0-223">Teams使用者 A 會使用流程 2 (DNS) URL 功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="eecb0-223">Teams User A resolves URL domain name (DNS) using flow 2.</span></span>
1. <span data-ttu-id="eecb0-224">Teams使用者 A 使用流程 4 在傳輸轉Teams上配置媒體轉場埠。</span><span class="sxs-lookup"><span data-stu-id="eecb0-224">Teams User A allocates a media Relay port on Teams Transport Relay using flow 4.</span></span>
1. <span data-ttu-id="eecb0-225">Teams使用者 A 會使用流程 4 傳送「邀請」給 ICE 求職者Microsoft 365或Office 365。</span><span class="sxs-lookup"><span data-stu-id="eecb0-225">Teams User A sends "invite" with ICE candidates using flow 4 to Microsoft 365 or Office 365.</span></span>
1. <span data-ttu-id="eecb0-226">Microsoft 365或Office 365使用流程 4 傳送通知Teams使用者 B。</span><span class="sxs-lookup"><span data-stu-id="eecb0-226">Microsoft 365 or Office 365 sends notification to Teams User B using flow 4.</span></span>
1. <span data-ttu-id="eecb0-227">Teams使用者 B 使用流程 4 在傳輸轉Teams上配置媒體轉場埠。</span><span class="sxs-lookup"><span data-stu-id="eecb0-227">Teams User B allocates a media Relay port on Teams Transport Relay using flow 4.</span></span>
1. <span data-ttu-id="eecb0-228">Teams使用者 B 使用流程 4 傳送「answer」給 ICE 候選者，然後使用 Teams 4 轉Flow回使用者 A。</span><span class="sxs-lookup"><span data-stu-id="eecb0-228">Teams User B sends "answer" with ICE candidates using flow 4, which is forwarded back to Teams User A using Flow 4.</span></span>
1. <span data-ttu-id="eecb0-229">Teams使用者 A Teams使用者 B 會調用 ICE 連接測試，且已選取最佳的可用媒體路徑 (請參閱下方圖表，瞭解各種使用案例) 。</span><span class="sxs-lookup"><span data-stu-id="eecb0-229">Teams User A and Teams User B invoke ICE connectivity tests and the best available media path is selected (see diagrams below for various use cases).</span></span>
1. <span data-ttu-id="eecb0-230">Teams使用者使用流程 4 傳送遙測Microsoft 365或Office 365傳送遙測。</span><span class="sxs-lookup"><span data-stu-id="eecb0-230">Teams Users send telemetry to Microsoft 365 or Office 365 using flow 4.</span></span>

<span data-ttu-id="eecb0-231">**在客戶網路中：**</span><span class="sxs-lookup"><span data-stu-id="eecb0-231">**Within customer network:**</span></span>

<span data-ttu-id="eecb0-232">[![Microsoft Teams線上通話流程圖 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)</span><span class="sxs-lookup"><span data-stu-id="eecb0-232">[![Microsoft Teams Online Call Flows Figure 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)</span></span>

<span data-ttu-id="eecb0-233">*圖 2 - 在客戶網路中*</span><span class="sxs-lookup"><span data-stu-id="eecb0-233">*Figure 2 - Within customer network*</span></span>

<span data-ttu-id="eecb0-234">在步驟 7 中，已選取對等媒體流程 5。</span><span class="sxs-lookup"><span data-stu-id="eecb0-234">In step 7, peer-to-peer media flow 5 is selected.</span></span>

<span data-ttu-id="eecb0-235">媒體是雙向的。</span><span class="sxs-lookup"><span data-stu-id="eecb0-235">Media is bidirectional.</span></span> <span data-ttu-id="eecb0-236">流程 5 的方向表示一端會從連接的角度啟動通訊，與本檔中所有流程一致。</span><span class="sxs-lookup"><span data-stu-id="eecb0-236">The direction of flow 5 indicates that one side initiates the communication from a connectivity perspective, consistent with all the flows in this document.</span></span> <span data-ttu-id="eecb0-237">在這種情況下，使用哪個方向並不重要，因為兩個端點都位於客戶網路內。</span><span class="sxs-lookup"><span data-stu-id="eecb0-237">In this case, it doesn't matter which direction is used because both endpoints are within the customer network.</span></span>

<span data-ttu-id="eecb0-238">**客戶網路傳送至外部使用者 (傳輸轉Teams轉) ：**</span><span class="sxs-lookup"><span data-stu-id="eecb0-238">**Customer network to external user (media relayed by Teams Transport Relay):**</span></span>

<span data-ttu-id="eecb0-239">[![Microsoft Teams線上通話流程圖 03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)</span><span class="sxs-lookup"><span data-stu-id="eecb0-239">[![Microsoft Teams Online Call Flows Figure 03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)</span></span>

<span data-ttu-id="eecb0-240">*圖 3 - 由傳輸轉 (轉Teams轉傳至外部使用者)*</span><span class="sxs-lookup"><span data-stu-id="eecb0-240">*Figure 3 - Customer network to external user (media relayed by Teams Transport Relay)*</span></span>

<span data-ttu-id="eecb0-241">在步驟 7 中，會選取流程 4，從客戶網路到 Microsoft 365 或 Office 365，以及流程 3，從遠端行動Teams使用者到 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="eecb0-241">In step 7, flow 4, from customer network to Microsoft 365 or Office 365, and flow 3, from remote mobile Teams user to Microsoft 365 or Office 365, are selected.</span></span> <span data-ttu-id="eecb0-242">這些流程會由 Teams 傳輸轉Microsoft 365或Office 365。</span><span class="sxs-lookup"><span data-stu-id="eecb0-242">These flows are relayed by Teams Transport Relay within Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="eecb0-243">媒體是雙向的，其中方向會指出哪一端會從連接角度啟動通訊。</span><span class="sxs-lookup"><span data-stu-id="eecb0-243">Media is bidirectional, where direction indicates which side initiates the communication from a connectivity perspective.</span></span> <span data-ttu-id="eecb0-244">在此案例中，這些流程會使用不同的傳輸通訊協定和位址，用於訊號和媒體。</span><span class="sxs-lookup"><span data-stu-id="eecb0-244">In this case, these flows are used for signaling and media, using different transport protocols and addresses.</span></span>

<span data-ttu-id="eecb0-245">**直接使用媒體 (外部使用者) ：**</span><span class="sxs-lookup"><span data-stu-id="eecb0-245">**Customer network to external user (direct media):**</span></span>

<span data-ttu-id="eecb0-246">[![Microsoft Teams線上通話流程圖 04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)</span><span class="sxs-lookup"><span data-stu-id="eecb0-246">[![Microsoft Teams Online Call Flows Figure 04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)</span></span>

<span data-ttu-id="eecb0-247">*圖 4 - 客戶網路與外部使用者 (媒體)*</span><span class="sxs-lookup"><span data-stu-id="eecb0-247">*Figure 4 - Customer network to external user (direct media)*</span></span>

<span data-ttu-id="eecb0-248">在步驟 7 中，已選取流程 2，從客戶網路 (用戶端對等) 網際網路。</span><span class="sxs-lookup"><span data-stu-id="eecb0-248">In step 7, flow 2, from customer network to the Internet (client's peer), is selected.</span></span>

- <span data-ttu-id="eecb0-249">使用遠端行動使用者直接 (不透過Microsoft 365或Office 365) 媒體是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="eecb0-249">Direct media with remote mobile user (not relayed through Microsoft 365 or Office 365) is optional.</span></span> <span data-ttu-id="eecb0-250">換句話說，客戶可能會封鎖此路徑，以透過傳輸轉場或Microsoft 365 Office 365。</span><span class="sxs-lookup"><span data-stu-id="eecb0-250">In other words, customer may block this path to enforce a media path through Transport Relay in Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="eecb0-251">媒體是雙向的。</span><span class="sxs-lookup"><span data-stu-id="eecb0-251">Media is bidirectional.</span></span> <span data-ttu-id="eecb0-252">流程 2 對遠端行動使用者的方向表示一端從連接角度啟動通訊。</span><span class="sxs-lookup"><span data-stu-id="eecb0-252">The direction of flow 2 to remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span>

<span data-ttu-id="eecb0-253">**VPN 使用者傳送至內部使用者 (傳輸轉Teams轉)**</span><span class="sxs-lookup"><span data-stu-id="eecb0-253">**VPN user to internal user (media relayed by Teams Transport Relay)**</span></span>

<span data-ttu-id="eecb0-254">[![Microsoft Teams線上通話流程圖 05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)</span><span class="sxs-lookup"><span data-stu-id="eecb0-254">[![Microsoft Teams Online Call Flows Figure 05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)</span></span>

<span data-ttu-id="eecb0-255">*圖 5 - 由傳輸轉 (轉Teams內部使用者的 VPN 使用者)*</span><span class="sxs-lookup"><span data-stu-id="eecb0-255">*Figure 5 - VPN user to internal user (media relayed by Teams Transport Relay)*</span></span>

<span data-ttu-id="eecb0-256">VPN 與客戶網路之間的訊號是使用 flow 2'。</span><span class="sxs-lookup"><span data-stu-id="eecb0-256">Signaling between the VPN to the customer network is using flow 2'.</span></span> <span data-ttu-id="eecb0-257">客戶網路與客戶或Microsoft 365之間的Office 365使用流程 4。</span><span class="sxs-lookup"><span data-stu-id="eecb0-257">Signaling between the customer network and Microsoft 365 or Office 365 is using flow 4.</span></span> <span data-ttu-id="eecb0-258">不過，媒體會忽略 VPN，並且使用流程 3 和 4 路由至 Teams 或 Microsoft 365 媒體轉Office 365。</span><span class="sxs-lookup"><span data-stu-id="eecb0-258">However, media bypasses the VPN and is routed using flows 3 and 4 through Teams media relay in Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="eecb0-259">**VPN 使用者至內部使用者 (媒體)**</span><span class="sxs-lookup"><span data-stu-id="eecb0-259">**VPN user to internal user (direct media)**</span></span>

<span data-ttu-id="eecb0-260">[![Microsoft Teams線上通話流程圖 06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)</span><span class="sxs-lookup"><span data-stu-id="eecb0-260">[![Microsoft Teams Online Call Flows Figure 06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)</span></span>

<span data-ttu-id="eecb0-261">*圖 6 - 將 VPN 使用者內部使用者 (媒體)*</span><span class="sxs-lookup"><span data-stu-id="eecb0-261">*Figure 6 - VPN user to internal user (direct media)*</span></span>

<span data-ttu-id="eecb0-262">VPN 與客戶網路之間的訊號是使用 flow 2'。</span><span class="sxs-lookup"><span data-stu-id="eecb0-262">Signaling between the VPN to the customer network is using flow 2'.</span></span> <span data-ttu-id="eecb0-263">客戶網路與客戶或Microsoft 365之間的Office 365使用流程 4。</span><span class="sxs-lookup"><span data-stu-id="eecb0-263">Signaling between the customer network and Microsoft 365 or Office 365 is using flow 4.</span></span> <span data-ttu-id="eecb0-264">不過，媒體會忽略 VPN，並且使用流程 2 從客戶網路路由至網際網路。</span><span class="sxs-lookup"><span data-stu-id="eecb0-264">However, media bypasses the VPN and is routed using flow 2 from the customer network to the Internet.</span></span>

<span data-ttu-id="eecb0-265">媒體是雙向的。</span><span class="sxs-lookup"><span data-stu-id="eecb0-265">Media is bidirectional.</span></span> <span data-ttu-id="eecb0-266">流程 2 對遠端行動使用者的方向表示一端從連接角度啟動通訊。</span><span class="sxs-lookup"><span data-stu-id="eecb0-266">The direction of flow 2 to the remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span>

<span data-ttu-id="eecb0-267">**VPN 使用者到外部使用者 (媒體)**</span><span class="sxs-lookup"><span data-stu-id="eecb0-267">**VPN user to external user (direct media)**</span></span>

<span data-ttu-id="eecb0-268">[![Microsoft Teams通話流程圖 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)</span><span class="sxs-lookup"><span data-stu-id="eecb0-268">[![Microsoft Teams call flows Figure 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)</span></span>

<span data-ttu-id="eecb0-269">*圖 7 - VPN 使用者到外部使用者 (媒體)*</span><span class="sxs-lookup"><span data-stu-id="eecb0-269">*Figure 7 - VPN user to external user (direct media)*</span></span>

<span data-ttu-id="eecb0-270">VPN 使用者與客戶網路之間的訊號是使用 flow 2' ，並且使用流程 4 Microsoft 365或Office 365。</span><span class="sxs-lookup"><span data-stu-id="eecb0-270">Signaling between the VPN user to the customer network is using flow 2' and using flow 4 to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="eecb0-271">不過，媒體會忽略 VPN，而且會使用流程 6 路由。</span><span class="sxs-lookup"><span data-stu-id="eecb0-271">However, media bypasses VPN and is routed using flow 6.</span></span>

<span data-ttu-id="eecb0-272">媒體是雙向的。</span><span class="sxs-lookup"><span data-stu-id="eecb0-272">Media is bidirectional.</span></span> <span data-ttu-id="eecb0-273">流程 6 對遠端行動使用者的方向表示一端從連接角度啟動通訊。</span><span class="sxs-lookup"><span data-stu-id="eecb0-273">The direction of flow 6 to the remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span>

#### <a name="use-case-teams-to-pstn-through-microsoft-365-or-office-365-trunk"></a><span data-ttu-id="eecb0-274">使用案例：Teams或主幹Microsoft 365 PSTN Office 365 PSTN</span><span class="sxs-lookup"><span data-stu-id="eecb0-274">Use Case: Teams to PSTN through Microsoft 365 or Office 365 Trunk</span></span>

<span data-ttu-id="eecb0-275">Microsoft 365 Office 365具有電話系統，可讓您從公用交換電話網絡或 PSTN (接聽) 。</span><span class="sxs-lookup"><span data-stu-id="eecb0-275">Microsoft 365 and Office 365 have a Phone System that allows placing and receiving calls from the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="eecb0-276">如果 PSTN 主幹是使用 電話系統方案進行連接，則此使用案例沒有特殊的連接需求。</span><span class="sxs-lookup"><span data-stu-id="eecb0-276">If the PSTN trunk is connected using the Phone System Calling Plan, then there are no special connectivity requirements for this use case.</span></span> <span data-ttu-id="eecb0-277"> (如果您想要將您自己的內部部署 PSTN 主幹連接到 Microsoft 365 或 Office 365，您可以使用 電話系統路由.) </span><span class="sxs-lookup"><span data-stu-id="eecb0-277">(If you want to connect your own on-premises PSTN trunk to Microsoft 365 or Office 365, you can use Phone System Direct Routing.)</span></span>

<span data-ttu-id="eecb0-278">[![Microsoft Teams線上通話流程圖 08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)</span><span class="sxs-lookup"><span data-stu-id="eecb0-278">[![Microsoft Teams Online Call Flows Figure 08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)</span></span>

<span data-ttu-id="eecb0-279">*圖 8 - Teams透過主幹Office 365 PSTN*</span><span class="sxs-lookup"><span data-stu-id="eecb0-279">*Figure 8 - Teams to PSTN through Office 365 Trunk*</span></span>

#### <a name="use-case-teams-meeting"></a><span data-ttu-id="eecb0-280">使用案例：Teams會議</span><span class="sxs-lookup"><span data-stu-id="eecb0-280">Use case: Teams meeting</span></span>

<span data-ttu-id="eecb0-281">會議服務器中的音訊/視 (/螢幕) 是Microsoft 365 Office 365。</span><span class="sxs-lookup"><span data-stu-id="eecb0-281">The audio/video/screen sharing (VBSS) conferencing server is part of Microsoft 365 and Office 365.</span></span> <span data-ttu-id="eecb0-282">其公用 IP 位址必須可從客戶網路取得，而且必須從 Nomadic Cloud 用戶端取得。</span><span class="sxs-lookup"><span data-stu-id="eecb0-282">It has a public IP address that must be reachable from the customer network and must be reachable from a Nomadic Cloud client.</span></span> <span data-ttu-id="eecb0-283">每個用戶端/端點必須能夠連接到會議服務器。</span><span class="sxs-lookup"><span data-stu-id="eecb0-283">Each client/endpoint needs to be able to connect to the conferencing server.</span></span>

<span data-ttu-id="eecb0-284">內部用戶端會以與一對一通話相同的方式取得本地、反身及轉傳候選者。</span><span class="sxs-lookup"><span data-stu-id="eecb0-284">Internal clients will obtain local, reflexive, and relay candidates in the same manner as described for one-to-one calls.</span></span> <span data-ttu-id="eecb0-285">用戶端會以邀請將這些候選者傳送至會議服務器。</span><span class="sxs-lookup"><span data-stu-id="eecb0-285">The clients will send these candidates to the conferencing server in an invite.</span></span> <span data-ttu-id="eecb0-286">會議服務器不會使用轉接，因為它有可公開到達的 IP 位址，因此會以其本地 IP 位址候選者回應。</span><span class="sxs-lookup"><span data-stu-id="eecb0-286">The conferencing server does not use a relay since it has a publicly reachable IP address, so it responds with its local IP address candidate.</span></span> <span data-ttu-id="eecb0-287">用戶端和會議服務器會以一對一通話所述的方式檢查連接。</span><span class="sxs-lookup"><span data-stu-id="eecb0-287">The client and conferencing server will check connectivity in the same manner described for one-to-one calls.</span></span>

<span data-ttu-id="eecb0-288">請注意：</span><span class="sxs-lookup"><span data-stu-id="eecb0-288">Note that:</span></span>

- <span data-ttu-id="eecb0-289">Teams無法加入商務用 Skype，而且商務用 Skype無法加入Teams會議。</span><span class="sxs-lookup"><span data-stu-id="eecb0-289">Teams clients cannot join Skype for Business meetings, and Skype for Business clients cannot join Teams meetings.</span></span>

- <span data-ttu-id="eecb0-290">PSTN 使用者視會議的召集人 PSTN 通話和/或會議布備而選擇「撥入」或「撥出」。</span><span class="sxs-lookup"><span data-stu-id="eecb0-290">A PSTN user optionally "Dials IN" or is "Dialed OUT", depending on the meeting's organizer PSTN Calling and/or conferencing provisioning.</span></span>

- <span data-ttu-id="eecb0-291">來賓使用者或客戶使用者可以從來賓私人網路絡加入，此網路受到 FW/NAT 的嚴格規則保護。</span><span class="sxs-lookup"><span data-stu-id="eecb0-291">A guest user or a customer user may join from a guest private network, which is protected using FW/NAT with strict rules.</span></span>

<span data-ttu-id="eecb0-292">[![Microsoft Teams線上通話流程圖 09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)</span><span class="sxs-lookup"><span data-stu-id="eecb0-292">[![Microsoft Teams Online Call Flows Figure 09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)</span></span>

<span data-ttu-id="eecb0-293">*圖 9 - Teams會議*</span><span class="sxs-lookup"><span data-stu-id="eecb0-293">*Figure 9 - Teams Meeting*</span></span>

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a><span data-ttu-id="eecb0-294">使用案例：與內部商務用 Skype的聯盟</span><span class="sxs-lookup"><span data-stu-id="eecb0-294">Use case: Federation with Skype for Business on premises</span></span>

<span data-ttu-id="eecb0-295">**在傳送或Teams傳輸轉Microsoft 365轉Office 365**</span><span class="sxs-lookup"><span data-stu-id="eecb0-295">**Media relayed by Teams Transport Relay in Microsoft 365 or Office 365**</span></span>

<span data-ttu-id="eecb0-296">[![Microsoft Teams線上通話流程圖 10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)</span><span class="sxs-lookup"><span data-stu-id="eecb0-296">[![Microsoft Teams Online Call Flows Figure 10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)</span></span>

<span data-ttu-id="eecb0-297">*圖 10 - 在 Teams 傳輸轉場轉Office 365*</span><span class="sxs-lookup"><span data-stu-id="eecb0-297">*Figure 10 - Media relayed by Teams Transport Relay in Office 365*</span></span>

<span data-ttu-id="eecb0-298">請注意：</span><span class="sxs-lookup"><span data-stu-id="eecb0-298">Note that:</span></span>

- <span data-ttu-id="eecb0-299">根據定義，聯合是兩個租使用者之間的通訊。</span><span class="sxs-lookup"><span data-stu-id="eecb0-299">Federation is, by definition, a communication between two tenants.</span></span> <span data-ttu-id="eecb0-300">在此案例中，租使用者 A 使用 Teams，會與租使用者 B 進行聯盟，商務用 Skype內部部署。</span><span class="sxs-lookup"><span data-stu-id="eecb0-300">In this case, tenant A, which uses Teams, federates with tenant B, which uses Skype for Business on premises.</span></span> <span data-ttu-id="eecb0-301">如果租使用者 B 也使用 Microsoft 365 或 Office 365，則 商務用 Skype 用戶端會使用 flow 3 與 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="eecb0-301">If tenant B is also using Microsoft 365 or Office 365, then the Skype for Business client would have used flow 3 to connect with Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="eecb0-302">從聯合用戶端商務用 Skype到內部部署商務用 Skype Server的訊號與媒體超出本檔的範圍。</span><span class="sxs-lookup"><span data-stu-id="eecb0-302">Signaling and media from the federated Skype for Business client to on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="eecb0-303">不過，此處說明清楚。</span><span class="sxs-lookup"><span data-stu-id="eecb0-303">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="eecb0-304">閘道會Teams商務用 Skype之間的訊號。</span><span class="sxs-lookup"><span data-stu-id="eecb0-304">Signaling between Teams and Skype for Business is bridged by a gateway.</span></span>

- <span data-ttu-id="eecb0-305">在此案例中，媒體會使用流程 4 Teams傳輸轉接至客戶網路和遠端商務用 Skype用戶端。</span><span class="sxs-lookup"><span data-stu-id="eecb0-305">Media in this case is relayed by Teams Transport Relay to the customer network and remote Skype for Business client using flow 4.</span></span>

<span data-ttu-id="eecb0-306">**在聯盟租使用者中商務用 Skype媒體轉場的媒體**</span><span class="sxs-lookup"><span data-stu-id="eecb0-306">**Media relayed by Skype for Business Media Relay in federated tenant**</span></span>

<span data-ttu-id="eecb0-307">[![Microsoft Teams線上通話流程圖 11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)</span><span class="sxs-lookup"><span data-stu-id="eecb0-307">[![Microsoft Teams Online Call Flows Figure 11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)</span></span>

<span data-ttu-id="eecb0-308">*圖 11 - 在商務用 Skype租使用者中由媒體轉商務用 Skype轉轉的媒體*</span><span class="sxs-lookup"><span data-stu-id="eecb0-308">*Figure 11 - Media relayed by Skype for Business Media Relay in federated tenant*</span></span>

<span data-ttu-id="eecb0-309">請注意：</span><span class="sxs-lookup"><span data-stu-id="eecb0-309">Note that:</span></span>

- <span data-ttu-id="eecb0-310">從聯合用戶端商務用 Skype到內部部署商務用 Skype Server的訊號和媒體超出本檔的範圍。</span><span class="sxs-lookup"><span data-stu-id="eecb0-310">Signaling and media from the federated Skype for Business client to an on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="eecb0-311">不過，此處說明清楚。</span><span class="sxs-lookup"><span data-stu-id="eecb0-311">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="eecb0-312">閘道會Teams商務用 Skype之間的訊號。</span><span class="sxs-lookup"><span data-stu-id="eecb0-312">Signaling between Teams and Skype for Business is bridged by a Gateway.</span></span>

- <span data-ttu-id="eecb0-313">在此案例中，媒體會使用流程 2 商務用 Skype內部部署媒體轉遞傳送至客戶網路。</span><span class="sxs-lookup"><span data-stu-id="eecb0-313">Media in this case is relayed by Skype for Business on-premises Media Relay to the customer network using flow 2.</span></span> <span data-ttu-id="eecb0-314"> (請注意，從 Teams 使用者到聯盟客戶網路中遠端媒體轉場的流量一開始會由媒體轉場封鎖，直到相反方向的流量開始流動。</span><span class="sxs-lookup"><span data-stu-id="eecb0-314">(Note that traffic from Teams user to the remote Media Relay in the federated customer network will be initially blocked by the Media Relay until traffic in the reverse direction starts to flow.</span></span> <span data-ttu-id="eecb0-315">不過，雙向流程會開啟雙向的) </span><span class="sxs-lookup"><span data-stu-id="eecb0-315">However, the bidirectional flow will open connectivity in both directions.)</span></span>

<span data-ttu-id="eecb0-316">**直接 (對等)**</span><span class="sxs-lookup"><span data-stu-id="eecb0-316">**Direct (peer-to-peer)**</span></span>

<span data-ttu-id="eecb0-317">[![Microsoft Teams線上通話流程圖 12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)</span><span class="sxs-lookup"><span data-stu-id="eecb0-317">[![Microsoft Teams Online Call Flows Figure 12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)</span></span>

<span data-ttu-id="eecb0-318">*圖 12 - 直接 (對等)*</span><span class="sxs-lookup"><span data-stu-id="eecb0-318">*Figure 12 - Direct (peer-to-peer)*</span></span>

### <a name="teams-hybrid-topology"></a><span data-ttu-id="eecb0-319">Teams混合式拓撲</span><span class="sxs-lookup"><span data-stu-id="eecb0-319">Teams hybrid topology</span></span>

<span data-ttu-id="eecb0-320">此拓撲包含Teams部署商務用 Skype拓撲。</span><span class="sxs-lookup"><span data-stu-id="eecb0-320">This topology includes Teams with a Skype for Business on-premises deployment.</span></span>

<span data-ttu-id="eecb0-321">[![Microsoft Teams線上通話流程圖 13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)</span><span class="sxs-lookup"><span data-stu-id="eecb0-321">[![Microsoft Teams Online Call Flows Figure 13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)</span></span>

<span data-ttu-id="eecb0-322">*圖 13 - Teams拓撲*</span><span class="sxs-lookup"><span data-stu-id="eecb0-322">*Figure 13 - Teams hybrid topology*</span></span>

- <span data-ttu-id="eecb0-323">上圖中箭的方向會反映影響企業周邊連接之通訊的起始方向。</span><span class="sxs-lookup"><span data-stu-id="eecb0-323">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="eecb0-324">在媒體用 UDP 的情況下，第一個封包 () 可能會以相反方向流動，但這些封包可能會封鎖，直到其他方向的封包流程。</span><span class="sxs-lookup"><span data-stu-id="eecb0-324">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>

- <span data-ttu-id="eecb0-325">Teams與 商務用 Skype並排部署，因此用戶端會顯示為「Teams/SFB 使用者」。</span><span class="sxs-lookup"><span data-stu-id="eecb0-325">Teams is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user."</span></span>

<span data-ttu-id="eecb0-326">拓撲 (上方的其他Teams流程) ：</span><span class="sxs-lookup"><span data-stu-id="eecb0-326">Additional flow (on top of Teams topology):</span></span>

- <span data-ttu-id="eecb0-327">**Flow 5A** – 代表客戶網路中 Teams 使用者之間的對等媒體流程，以及客戶網路邊緣的 商務用 Skype 內部部署媒體轉場。</span><span class="sxs-lookup"><span data-stu-id="eecb0-327">**Flow 5A** – Represents a peer-to-peer media flow between a Teams user within the customer network and a Skype for Business on-premises media relay at the customer network edge.</span></span>

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a><span data-ttu-id="eecb0-328">使用案例：Teams商務用 Skype一對一</span><span class="sxs-lookup"><span data-stu-id="eecb0-328">Use case: Teams to Skype for Business one-to-one</span></span>

<span data-ttu-id="eecb0-329">**客戶網路中混合式**</span><span class="sxs-lookup"><span data-stu-id="eecb0-329">**Hybrid within the customer network**</span></span>

<span data-ttu-id="eecb0-330">[![Microsoft Teams線上通話流程圖 14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)</span><span class="sxs-lookup"><span data-stu-id="eecb0-330">[![Microsoft Teams Online Call Flows Figure 14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)</span></span>

<span data-ttu-id="eecb0-331">*圖 14 - 客戶網路內部的混合式*</span><span class="sxs-lookup"><span data-stu-id="eecb0-331">*Figure 14 - Hybrid within customer network*</span></span>

<span data-ttu-id="eecb0-332">閘道會Teams商務用 Skype之間的訊號。</span><span class="sxs-lookup"><span data-stu-id="eecb0-332">Signaling between Teams and Skype for Business is bridged by a gateway.</span></span> <span data-ttu-id="eecb0-333">不過，媒體會使用流程 5 在客戶網路中直接對等路由。</span><span class="sxs-lookup"><span data-stu-id="eecb0-333">However, media is routed directly peer-to-peer within the customer network using flow 5.</span></span>

<span data-ttu-id="eecb0-334">**混合式客戶網路與外部商務用 Skype使用者 - 由Microsoft 365或Office 365**</span><span class="sxs-lookup"><span data-stu-id="eecb0-334">**Hybrid customer network with external Skype for Business user – relayed by Microsoft 365 or Office 365**</span></span>

<span data-ttu-id="eecb0-335">[![Microsoft Teams線上通話流程圖 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)</span><span class="sxs-lookup"><span data-stu-id="eecb0-335">[![Microsoft Teams Online Call Flows Figure 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)</span></span>

<span data-ttu-id="eecb0-336">*圖 15 - 混合式客戶網路與外部商務用 Skype使用者 - 由 Office 365*</span><span class="sxs-lookup"><span data-stu-id="eecb0-336">*Figure 15 - Hybrid customer network with external Skype for Business user - relayed by Office 365*</span></span>

<span data-ttu-id="eecb0-337">請注意：</span><span class="sxs-lookup"><span data-stu-id="eecb0-337">Note that:</span></span>

- <span data-ttu-id="eecb0-338">從用戶端到內部商務用 Skype的訊號商務用 Skype Server媒體超出本檔的範圍。</span><span class="sxs-lookup"><span data-stu-id="eecb0-338">Signaling and media from the Skype for Business client to an on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="eecb0-339">不過，此處說明清楚。</span><span class="sxs-lookup"><span data-stu-id="eecb0-339">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="eecb0-340">閘道會Teams商務用 Skype之間的訊號。</span><span class="sxs-lookup"><span data-stu-id="eecb0-340">Signaling between Teams and Skype for Business is bridged by a gateway.</span></span>

- <span data-ttu-id="eecb0-341">媒體會透過傳輸轉Teams透過流程 4 傳送至客戶網路。</span><span class="sxs-lookup"><span data-stu-id="eecb0-341">Media is relayed through Teams Transport Relay to the customer network through flow 4.</span></span>

<span data-ttu-id="eecb0-342">**與外部使用者商務用 Skype混合式客戶網路 – 由內部部署 Edge 轉用**</span><span class="sxs-lookup"><span data-stu-id="eecb0-342">**Hybrid customer network with external Skype for Business user – relayed by on-premises Edge**</span></span>

<span data-ttu-id="eecb0-343">[![Microsoft Teams線上通話流程圖 16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)</span><span class="sxs-lookup"><span data-stu-id="eecb0-343">[![Microsoft Teams Online Call Flows Figure 16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)</span></span>

<span data-ttu-id="eecb0-344">*圖 16 - 混合式客戶網路與外部商務用 Skype使用者 - 由內部部署 Edge 轉傳*</span><span class="sxs-lookup"><span data-stu-id="eecb0-344">*Figure 16 - Hybrid customer network with external Skype for Business user - relayed by on-premises Edge*</span></span>

<span data-ttu-id="eecb0-345">請注意：</span><span class="sxs-lookup"><span data-stu-id="eecb0-345">Note that:</span></span>

- <span data-ttu-id="eecb0-346">從用戶端商務用 Skype到內部部署商務用 Skype Server的訊號與媒體超出本檔的範圍。</span><span class="sxs-lookup"><span data-stu-id="eecb0-346">Signaling and media from Skype for Business client to an on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="eecb0-347">不過，此處說明清楚。</span><span class="sxs-lookup"><span data-stu-id="eecb0-347">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="eecb0-348">閘道會橋接器連接訊號。</span><span class="sxs-lookup"><span data-stu-id="eecb0-348">Signaling is bridged by a gateway.</span></span>

- <span data-ttu-id="eecb0-349">媒體是由內部商務用 Skype內部部署商務用 Skype內媒體轉Teams，以使用媒體流程 5A 傳送至客戶網路內的使用者。</span><span class="sxs-lookup"><span data-stu-id="eecb0-349">Media is relayed by Skype for Business Media Relay within Skype for Business on-premises Edge to Teams user within the customer network using media flow 5A.</span></span>

### <a name="teams-with-phone-system-direct-routing-topology"></a><span data-ttu-id="eecb0-350">Teams直接路由電話系統拓撲</span><span class="sxs-lookup"><span data-stu-id="eecb0-350">Teams with Phone System Direct Routing topology</span></span>

<span data-ttu-id="eecb0-351">此拓撲包含Teams路由電話系統拓撲。</span><span class="sxs-lookup"><span data-stu-id="eecb0-351">This topology includes Teams with Phone System Direct Routing.</span></span>

<span data-ttu-id="eecb0-352">直接路由可讓您將支援的內部部署客戶擁有會話邊界控制器 (SBC) 硬體裝置配對至 Microsoft 365 或 Office 365，然後將電話主幹連接到該裝置，以使用協力廠商公用交換電話網絡 (PSTN) 服務提供者。</span><span class="sxs-lookup"><span data-stu-id="eecb0-352">Direct Routing enables you to use a third-party Public Switched Telephone Network (PSTN) service provider by pairing a supported on-premises customer-owned Session Border Controller (SBC) hardware device to Microsoft 365 or Office 365, and then connecting the telephony trunk to that device.</span></span>

<span data-ttu-id="eecb0-353">若要支援此案例，客戶必須從 Microsoft 的其中一個認證合作夥伴部署經過認證的 SBC 以直接路由。</span><span class="sxs-lookup"><span data-stu-id="eecb0-353">To support this scenario, the customer must deploy a certified SBC for Direct Routing from one of Microsoft's certified partners.</span></span> <span data-ttu-id="eecb0-354">SBC 必須按照廠商的建議進行配置，並且可路由至 Microsoft 365 或 Office 365 UDP 流量。</span><span class="sxs-lookup"><span data-stu-id="eecb0-354">The SBC must be configured as recommended by the vendor, and be routable from Microsoft 365 or Office 365 for direct UDP traffic.</span></span> <span data-ttu-id="eecb0-355">媒體可能會直接從 Teams 和/或 商務用 Skype 用戶端流向 SBC (，而忽略 Teams 閘道) 或Teams閘道。</span><span class="sxs-lookup"><span data-stu-id="eecb0-355">The media may flow directly from Teams and/or the Skype for Business client to the SBC (bypassing the Teams gateway) or traverse through the Teams gateway.</span></span> <span data-ttu-id="eecb0-356">當主幹已配置為跳過 Teams 閘道時，與 SBC 的連線性是以 ICE 為基礎，其中 SBC 支援 ICE-Lite，而 Teams/商務用 Skype 媒體端點則支援 ICE Full Form。</span><span class="sxs-lookup"><span data-stu-id="eecb0-356">The connectivity with the SBC, when the trunk is configured to bypass the Teams gateway, is based on ICE, where SBC supports ICE-Lite, while the Teams/Skype for Business media endpoint supports ICE Full Form.</span></span>

<span data-ttu-id="eecb0-357">[![Microsoft Teams線上通話流程圖 17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)</span><span class="sxs-lookup"><span data-stu-id="eecb0-357">[![Microsoft Teams Online Call Flows Figure 17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)</span></span>

<span data-ttu-id="eecb0-358">\*圖 17 - Teams路由電話系統拓撲</span><span class="sxs-lookup"><span data-stu-id="eecb0-358">\*Figure 17 - Teams with Phone System Direct Routing topology</span></span>

<span data-ttu-id="eecb0-359">請注意：</span><span class="sxs-lookup"><span data-stu-id="eecb0-359">Note that:</span></span>

- <span data-ttu-id="eecb0-360">上圖中箭的方向會反映影響企業周邊連接之通訊的起始方向。</span><span class="sxs-lookup"><span data-stu-id="eecb0-360">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="eecb0-361">在媒體用 UDP 的情況下，第一個封包 () 可能會以相反方向流動，但這些封包可能會封鎖，直到其他方向的封包流程。</span><span class="sxs-lookup"><span data-stu-id="eecb0-361">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>

- <span data-ttu-id="eecb0-362">Teams與 商務用 Skype並排部署，因此用戶端會顯示為「Teams/SFB 使用者」。</span><span class="sxs-lookup"><span data-stu-id="eecb0-362">Teams is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user."</span></span>

<span data-ttu-id="eecb0-363">其他流程 (線上拓撲Teams上) ：</span><span class="sxs-lookup"><span data-stu-id="eecb0-363">Additional flows (on top of Teams online topology):</span></span>

- <span data-ttu-id="eecb0-364">**Flow 4'** - 代表從 Microsoft 365 或 Office 365 到客戶網路的流量，用於在雲端中的 Teams 媒體伺服器與內部部署 SBC 建立連接。</span><span class="sxs-lookup"><span data-stu-id="eecb0-364">**Flow 4'** - Represents a flow from Microsoft 365 or Office 365 to the customer network, used to establish a connection between the Teams media server in the cloud with the SBC on premises.</span></span>
- <span data-ttu-id="eecb0-365">**Flow 5B** – 代表客戶網路內Teams直接路由 SBC 以旁路模式傳送 SBC 之間的媒體流程。</span><span class="sxs-lookup"><span data-stu-id="eecb0-365">**Flow 5B** – Represents a media flow between the Teams user within the customer network with the Direct Routing SBC in bypass mode.</span></span>
- <span data-ttu-id="eecb0-366">**Flow 5C** – 代表 PSTN hairpin 通話旁路模式中，將 SBC 直接路由至另一個直接路由 SBC 之間的媒體流程。</span><span class="sxs-lookup"><span data-stu-id="eecb0-366">**Flow 5C** – Represents a media flow between the Direct Routing SBC to another Direct Routing SBC in a PSTN hairpin call bypass mode.</span></span>

<span data-ttu-id="eecb0-367">**具有直接路由的內部使用者 (傳輸轉Teams轉)**</span><span class="sxs-lookup"><span data-stu-id="eecb0-367">**Internal user with Direct Routing (media relayed by Teams Transport Relay)**</span></span>

<span data-ttu-id="eecb0-368">[![Microsoft Teams線上通話流程圖 18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)</span><span class="sxs-lookup"><span data-stu-id="eecb0-368">[![Microsoft Teams Online Call Flows Figure 18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)</span></span>

<span data-ttu-id="eecb0-369">*圖 18 - 內部使用者使用直接路由 (傳輸轉Teams轉)*</span><span class="sxs-lookup"><span data-stu-id="eecb0-369">*Figure 18 - Internal user with Direct Routing (media relayed by Teams Transport Relay)*</span></span>

<span data-ttu-id="eecb0-370">請注意：</span><span class="sxs-lookup"><span data-stu-id="eecb0-370">Note that:</span></span>

- <span data-ttu-id="eecb0-371">SBC 必須有一個公用 IP 位址，可路由自 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="eecb0-371">The SBC must have a public IP address that is routable from Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="eecb0-372">從 SBC 到 Microsoft 365 或 Office 365 訊號和媒體使用流程 4 和/或流程 4'。</span><span class="sxs-lookup"><span data-stu-id="eecb0-372">Signaling and media from the SBC to Microsoft 365 or Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="eecb0-373">從客戶網路內的用戶端將訊號和媒體Microsoft 365或Office 365使用流程 4。</span><span class="sxs-lookup"><span data-stu-id="eecb0-373">Signaling and media from the client within the customer network to Microsoft 365 or Office 365 use flow 4.</span></span>

<span data-ttu-id="eecb0-374">**使用直接路由或 (的遠端使用者會透過媒體伺服器或 MP (路由) )**</span><span class="sxs-lookup"><span data-stu-id="eecb0-374">**Remote user with Direct Routing (media is routed through a media server (MP))**</span></span>

<span data-ttu-id="eecb0-375">[![Microsoft Teams線上通話流程圖 19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)</span><span class="sxs-lookup"><span data-stu-id="eecb0-375">[![Microsoft Teams Online Call Flows Figure 19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)</span></span>

<span data-ttu-id="eecb0-376">*圖 19 - 使用直接路由或 (的遠端使用者會透過媒體伺服器或 MP (路由) )*</span><span class="sxs-lookup"><span data-stu-id="eecb0-376">*Figure 19 - Remote user with Direct Routing (media is routed through a media server (MP))*</span></span>

<span data-ttu-id="eecb0-377">請注意：</span><span class="sxs-lookup"><span data-stu-id="eecb0-377">Note that:</span></span>

- <span data-ttu-id="eecb0-378">SBC 必須有一個公用 IP 位址，可路由自 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="eecb0-378">The SBC must have a public IP address that is routable from Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="eecb0-379">從 SBC 到 Microsoft 365 或 Office 365 訊號和媒體使用流程 4 和/或流程 4'。</span><span class="sxs-lookup"><span data-stu-id="eecb0-379">Signaling and media from the SBC to Microsoft 365 or Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="eecb0-380">從網際網路用戶端將訊號和媒體Microsoft 365或Office 365使用流程 3。</span><span class="sxs-lookup"><span data-stu-id="eecb0-380">Signaling and media from the client on the Internet to Microsoft 365 or Office 365 use flow 3.</span></span>

<span data-ttu-id="eecb0-381">**內部使用者直接路由 (媒體旁)**</span><span class="sxs-lookup"><span data-stu-id="eecb0-381">**Internal user Direct Routing (media bypass)**</span></span>

<span data-ttu-id="eecb0-382">[![Microsoft Teams線上通話流程圖 20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)</span><span class="sxs-lookup"><span data-stu-id="eecb0-382">[![Microsoft Teams Online Call Flows Figure 20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)</span></span>

<span data-ttu-id="eecb0-383">*圖 20 - 內部使用者直接路由 (媒體旁)*</span><span class="sxs-lookup"><span data-stu-id="eecb0-383">*Figure 20 - Internal user Direct Routing (media bypass)*</span></span>

<span data-ttu-id="eecb0-384">請注意：</span><span class="sxs-lookup"><span data-stu-id="eecb0-384">Note that:</span></span>

- <span data-ttu-id="eecb0-385">SBC 必須有一個公用 IP 位址，可路由自 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="eecb0-385">The SBC must have a public IP address that is routable from Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="eecb0-386">從 SBC Microsoft 365或 Office 365，反之亦然，請使用流程 4 和/或流程 4'。</span><span class="sxs-lookup"><span data-stu-id="eecb0-386">Signaling from SBC to Microsoft 365 or Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="eecb0-387">使用流程 4，從客戶網路內的用戶端Microsoft 365或Office 365用戶端。</span><span class="sxs-lookup"><span data-stu-id="eecb0-387">Signaling from client within the customer network to Microsoft 365 or Office 365 use flow 4.</span></span>

- <span data-ttu-id="eecb0-388">客戶網路內從用戶端到客戶網路內 SBC 的媒體使用流程 5B。</span><span class="sxs-lookup"><span data-stu-id="eecb0-388">Media from client within the customer network to SBC within the customer network use flow 5B.</span></span>

<span data-ttu-id="eecb0-389">**使用直接路由的遠端使用者 (傳輸轉Teams轉)**</span><span class="sxs-lookup"><span data-stu-id="eecb0-389">**Remote user with Direct Routing (media bypass relayed by Teams Transport Relay)**</span></span>

<span data-ttu-id="eecb0-390">[![Microsoft Teams線上通話流程圖 21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)</span><span class="sxs-lookup"><span data-stu-id="eecb0-390">[![Microsoft Teams Online Call Flows Figure 21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)</span></span>

<span data-ttu-id="eecb0-391">*圖 21 - 使用直接路由的遠端使用者 (傳輸轉Teams轉)*</span><span class="sxs-lookup"><span data-stu-id="eecb0-391">*Figure 21 - Remote user with Direct Routing (media bypass relayed by Teams Transport Relay)*</span></span>

<span data-ttu-id="eecb0-392">請注意：</span><span class="sxs-lookup"><span data-stu-id="eecb0-392">Note that:</span></span>

- <span data-ttu-id="eecb0-393">SBC 必須有一個公用 IP 位址，可路由至 Microsoft 365 或 Office 365 網際網路。</span><span class="sxs-lookup"><span data-stu-id="eecb0-393">The SBC must have a public IP address that is routable from Microsoft 365 or Office 365 and Internet.</span></span>

- <span data-ttu-id="eecb0-394">從 SBC 到 Microsoft 365 或 Office 365 訊號使用流程 4 和/或流程 4'。</span><span class="sxs-lookup"><span data-stu-id="eecb0-394">Signaling from the SBC to Microsoft 365 or Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="eecb0-395">從用戶端在網際網路上接收Microsoft 365或Office 365使用 flow 3。</span><span class="sxs-lookup"><span data-stu-id="eecb0-395">Signaling from the client on the Internet to Microsoft 365 or Office 365 uses flow 3.</span></span>

- <span data-ttu-id="eecb0-396">從網際網路用戶端到客戶網路中 SBC 的媒體會使用流程 3 和 4，由傳輸轉Teams轉場。</span><span class="sxs-lookup"><span data-stu-id="eecb0-396">Media from the client on the Internet to the SBC within the customer network uses flows 3 and 4, relayed by Teams Transport Relay.</span></span>

<span data-ttu-id="eecb0-397">**遠端使用者直接路由 (直接路由)**</span><span class="sxs-lookup"><span data-stu-id="eecb0-397">**Remote user Direct Routing (media bypass direct)**</span></span>

<span data-ttu-id="eecb0-398">[![Microsoft Teams線上通話流程圖 22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)</span><span class="sxs-lookup"><span data-stu-id="eecb0-398">[![Microsoft Teams Online Call Flows Figure 22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)</span></span>

<span data-ttu-id="eecb0-399">*圖 22 - 遠端使用者直接路由 (直接)*</span><span class="sxs-lookup"><span data-stu-id="eecb0-399">*Figure 22 - Remote user Direct Routing (media bypass direct)*</span></span>

<span data-ttu-id="eecb0-400">請注意：</span><span class="sxs-lookup"><span data-stu-id="eecb0-400">Note that:</span></span>

- <span data-ttu-id="eecb0-401">SBC 必須有一個公用 IP 位址，可路由至 Microsoft 365 或 Office 365 網際網路。</span><span class="sxs-lookup"><span data-stu-id="eecb0-401">The SBC must have a public IP address that is routable from Microsoft 365 or Office 365 and the Internet.</span></span>

- <span data-ttu-id="eecb0-402">從 SBC 到 Microsoft 365 或 Office 365 訊號使用流程 4 和/或流程 4'。</span><span class="sxs-lookup"><span data-stu-id="eecb0-402">Signaling from the SBC to Microsoft 365 or Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="eecb0-403">從用戶端在網際網路上接收Microsoft 365或Office 365使用 flow 3。</span><span class="sxs-lookup"><span data-stu-id="eecb0-403">Signaling from the client on the Internet to Microsoft 365 or Office 365 uses flow 3.</span></span>

- <span data-ttu-id="eecb0-404">從網際網路用戶端到客戶網路中 SBC 的媒體使用流程 2。</span><span class="sxs-lookup"><span data-stu-id="eecb0-404">Media from the client on the Internet to the SBC within the customer network uses flow 2.</span></span>

<span data-ttu-id="eecb0-405">**直接路由 (媒體旁) - PSTN 髮夾 (由於來電轉接/轉接)**</span><span class="sxs-lookup"><span data-stu-id="eecb0-405">**Direct Routing (media bypass) – PSTN hairpin call (due to call forward/transfer)**</span></span>

<span data-ttu-id="eecb0-406">[![Microsoft Teams線上通話流程圖 23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)</span><span class="sxs-lookup"><span data-stu-id="eecb0-406">[![Microsoft Teams Online Call Flows Figure 23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)</span></span>

<span data-ttu-id="eecb0-407">*圖 23 - 直接路由 (媒體) - PSTN 髮夾 (由於來電轉接/轉接)*</span><span class="sxs-lookup"><span data-stu-id="eecb0-407">*Figure 23 - Direct Routing (media bypass) - PSTN hairpin call (due to call forward/transfer)*</span></span>

<span data-ttu-id="eecb0-408">請注意：</span><span class="sxs-lookup"><span data-stu-id="eecb0-408">Note that:</span></span>

- <span data-ttu-id="eecb0-409">SBC 必須有一個公用 IP 位址，可路由自 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="eecb0-409">The SBC must have a public IP address that is routable from Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="eecb0-410">從 SBC 到 Microsoft 365 或 Office 365 訊號使用流程 4 和/或流程 4'。</span><span class="sxs-lookup"><span data-stu-id="eecb0-410">Signaling from the SBC to Microsoft 365 or Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="eecb0-411">呼叫從 PSTN 到 PSTN 後，用戶端會結束訊號和媒體循環。</span><span class="sxs-lookup"><span data-stu-id="eecb0-411">The client is out of the signaling and media loop after the call is hairpinned from PSTN to PSTN.</span></span>

- <span data-ttu-id="eecb0-412">從客戶網路內的 SBC 實例 A 到客戶網路內的 SBC 實例 B 的媒體 (其中，A 和 B 可以使用流程 5C) 同一個實例。</span><span class="sxs-lookup"><span data-stu-id="eecb0-412">Media from SBC instance A within the customer network to SBC instance B within the customer network (where, A and B can be the same instance) uses flow 5C.</span></span>

<span data-ttu-id="eecb0-413">**直接路由 (媒體Microsoft 365或Office 365) - 跨兩個租使用者撥打 PSTN 發釘電話**</span><span class="sxs-lookup"><span data-stu-id="eecb0-413">**Direct Routing (media through Microsoft 365 or Office 365) – PSTN hairpin call across two tenants**</span></span>

<span data-ttu-id="eecb0-414">[![Microsoft Teams線上通話流程圖 24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)</span><span class="sxs-lookup"><span data-stu-id="eecb0-414">[![Microsoft Teams Online Call Flows Figure 24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)</span></span>

<span data-ttu-id="eecb0-415">*圖 24 - 透過 (或 Microsoft 365 直接路由Office 365) - 跨兩個租使用者撥打 PSTN 發釘電話*</span><span class="sxs-lookup"><span data-stu-id="eecb0-415">*Figure 24 - Direct Routing (media through Microsoft 365 or Office 365) – PSTN hairpin call across two tenants*</span></span>

<span data-ttu-id="eecb0-416">請注意：</span><span class="sxs-lookup"><span data-stu-id="eecb0-416">Note that:</span></span>

- <span data-ttu-id="eecb0-417">SBC 必須有一個公用 IP 位址，可路由自 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="eecb0-417">The SBC must have a public IP address that is routable from Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="eecb0-418">從 SBC 到 Microsoft 365 或 Office 365 訊號使用流程 4 和/或流程 4'。</span><span class="sxs-lookup"><span data-stu-id="eecb0-418">Signaling from the SBC to Microsoft 365 or Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="eecb0-419">呼叫從 PSTN 到 PSTN 後，用戶端會結束訊號和媒體循環。</span><span class="sxs-lookup"><span data-stu-id="eecb0-419">The client is out of the signaling and media loop after the call is hairpinned from PSTN to PSTN.</span></span>

- <span data-ttu-id="eecb0-420">客戶網路 X 到 SBC 實例 B 內的 SBC 實例 A 媒體必須透過 Microsoft 365 或 Office 365 Media Server 轉傳，且不得使用旁路模式。</span><span class="sxs-lookup"><span data-stu-id="eecb0-420">Media from SBC instance A within the customer network X to SBC instance B must be relayed through the Microsoft 365 or Office 365 Media Server and can't use bypass mode.</span></span>

## <a name="teams-with-express-route-optimization"></a><span data-ttu-id="eecb0-421">Teams快速路由優化</span><span class="sxs-lookup"><span data-stu-id="eecb0-421">Teams with Express Route optimization</span></span>

<span data-ttu-id="eecb0-422">[![Microsoft Teams線上通話流程圖 25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)</span><span class="sxs-lookup"><span data-stu-id="eecb0-422">[![Microsoft Teams Online Call Flows Figure 25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)</span></span>

<span data-ttu-id="eecb0-423">*圖 25 - Teams快速路由優化*</span><span class="sxs-lookup"><span data-stu-id="eecb0-423">*Figure 25 - Teams with Express Route optimization*</span></span>

<span data-ttu-id="eecb0-424">如果 Express Route 是對齊並部署，Teams流程可以重新路由從流程 4 到流程 1，以及從流程 4' 到流程 1'。</span><span class="sxs-lookup"><span data-stu-id="eecb0-424">In the case that Express Route is justified and deployed, then Teams flows could be re-routed from flow 4 to flow 1 and from flow 4' to flow 1'.</span></span> <span data-ttu-id="eecb0-425">不過，Teams應用程式會與其他使用流程 4 和 4'的網際網路Microsoft 365或Office 365流量有硬性相依性;因此，這些流程不得被封鎖。</span><span class="sxs-lookup"><span data-stu-id="eecb0-425">However, the Teams application has a hard dependency on other Microsoft 365 or Office 365 flows over the Internet using flows 4 and 4'; hence these flows must not be blocked.</span></span>

<span data-ttu-id="eecb0-426">請注意，商務用 Skype混合式 Edge 流量會路由至網際網路，而非 Express Route 來與外部使用者通訊，並與其他租使用者進行聯盟。</span><span class="sxs-lookup"><span data-stu-id="eecb0-426">Note that Skype for Business hybrid Edge traffic is routed to the Internet and not to Express Route to communicate with external users and federate with other tenants.</span></span>

<span data-ttu-id="eecb0-427">若要避免非對稱流程，重新路由必須同時朝兩個方向進行。</span><span class="sxs-lookup"><span data-stu-id="eecb0-427">To prevent asymmetrical flows, re-routing must be in both directions.</span></span> <span data-ttu-id="eecb0-428">換句話說，客戶網路內的位址可以透過網際網路或 Express Route 路由路由，根據優化，但不能透過這兩者路由路由。</span><span class="sxs-lookup"><span data-stu-id="eecb0-428">In other words, an address within the customer network is routable either through Internet or Express Route, based on optimization, but not through both.</span></span>


<span data-ttu-id="eecb0-429">**客戶網路傳送至外部使用者 (傳輸轉Teams轉) ：**</span><span class="sxs-lookup"><span data-stu-id="eecb0-429">**Customer network to external user (media relayed by Teams Transport Relay):**</span></span>

<span data-ttu-id="eecb0-430">[![Microsoft Teams線上通話流程圖 26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)</span><span class="sxs-lookup"><span data-stu-id="eecb0-430">[![Microsoft Teams Online Call Flows Figure 26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)</span></span>

<span data-ttu-id="eecb0-431">*圖 26 - 由傳輸轉 (轉Teams轉傳至外部使用者)*</span><span class="sxs-lookup"><span data-stu-id="eecb0-431">*Figure 26 - Customer network to external user (media relayed by Teams Transport Relay)*</span></span>

<span data-ttu-id="eecb0-432">**高層級步驟：**</span><span class="sxs-lookup"><span data-stu-id="eecb0-432">**High-Level Steps:**</span></span>

1. <span data-ttu-id="eecb0-433">Teams客戶網路內的使用者會使用 flow2 解析 DNS (名稱) URL 功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="eecb0-433">Teams User within customer network resolves URL domain name (DNS) using flow2.</span></span>
1. <span data-ttu-id="eecb0-434">Teams客戶網路內的使用者會使用流程 1 在 Teams 傳輸轉場上配置媒體轉場埠。</span><span class="sxs-lookup"><span data-stu-id="eecb0-434">Teams User within customer network allocates a media Relay port on Teams Transport Relay using flow 1.</span></span>
1. <span data-ttu-id="eecb0-435">Teams客戶網路內的使用者會使用流程 1 傳送「邀請」給 ICE 求職者，Microsoft 365或Office 365。</span><span class="sxs-lookup"><span data-stu-id="eecb0-435">Teams User within customer network sends "invite" with ICE candidates using flow 1 to Microsoft 365 or Office 365.</span></span>
1. <span data-ttu-id="eecb0-436">Microsoft 365或Office 365使用流程 3 將通知傳送Teams外部使用者。</span><span class="sxs-lookup"><span data-stu-id="eecb0-436">Microsoft 365 or Office 365 sends notification to external Teams user using flow 3.</span></span>
1. <span data-ttu-id="eecb0-437">Teams使用者使用流程 3 在傳輸轉Teams上配置媒體轉場埠。</span><span class="sxs-lookup"><span data-stu-id="eecb0-437">Teams external user allocates a media Relay port on Teams Transport Relay using flow 3.</span></span>
1. <span data-ttu-id="eecb0-438">Teams使用流程 3 傳送「answer」給 ICE 候選者，而流程 3 會使用第 1 個Teams傳送回Flow A。</span><span class="sxs-lookup"><span data-stu-id="eecb0-438">Teams external user sends "answer" with ICE candidates using flow 3, which is forwarded back to Teams user A using Flow 1.</span></span>
1. <span data-ttu-id="eecb0-439">Teams使用者 A 和 Teams 使用者 B 會調用 ICE 連接測試，並選取流程 1 和 3，這兩個流程會由 Teams轉傳。</span><span class="sxs-lookup"><span data-stu-id="eecb0-439">Teams User A and Teams User B invoke ICE connectivity tests and selects flows 1 and 3, which are relayed by Teams Transport Relay.</span></span>
1. <span data-ttu-id="eecb0-440">Teams使用者使用流程 1 和 Microsoft 365 3 Office 365傳送遙測至或傳送資料。</span><span class="sxs-lookup"><span data-stu-id="eecb0-440">Teams Users send telemetry to Microsoft 365 or Office 365 using flows 1 and 3.</span></span>

> [!NOTE]
> <span data-ttu-id="eecb0-441">Flow 4 必須啟用，Teams要求流程 4 的其他微服務上的應用程式相依性。</span><span class="sxs-lookup"><span data-stu-id="eecb0-441">Flow 4 must be enabled to support dependencies of Teams application on other micro-services that mandates flow 4.</span></span>
