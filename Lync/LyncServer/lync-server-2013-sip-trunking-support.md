---
title: Lync Server 2013 SIP 主幹連線支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunking support
ms:assetid: e3042831-e8d8-4ea2-baa2-1a697401ffa0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399005(v=OCS.15)
ms:contentKeyID: 48185714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58108df8795aaae8d431b320125d34d14ee3a275
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunking-support-in-lync-server-2013"></a><span data-ttu-id="4b620-102">Lync Server 2013 中的 SIP 主幹連線支援</span><span class="sxs-lookup"><span data-stu-id="4b620-102">SIP trunking support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b620-103">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="4b620-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="4b620-104">如果您打算使用企業語音搭配 SIP 中繼，您必須部署一個轉送伺服器並確定其他基礎結構和元件符合您部署模型適當的支援需求。</span><span class="sxs-lookup"><span data-stu-id="4b620-104">If you plan to use Enterprise Voice with SIP trunking, you must deploy a Mediation Server and make sure that other infrastructure and components meet the support requirements appropriate to your deployment model.</span></span> <span data-ttu-id="4b620-105">如需決定是否要實現 SIP 中繼的詳細資料，請參閱規劃檔中的[Lync Server 2013 中的 SIP 中繼概覽](lync-server-2013-overview-of-sip-trunking.md)。</span><span class="sxs-lookup"><span data-stu-id="4b620-105">For details about determining whether to implement SIP trunking, see [Overview of SIP trunking in Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) in the Planning documentation.</span></span>

<span data-ttu-id="4b620-106">您可以使用 Microsoft 整合通訊開啟企業電話結構的互通性計畫，找出合格的公用交換電話網絡（PSTN）閘道、IP-Pbx 和 SIP 中繼服務，包括合格的 IP 電話服務提供者。</span><span class="sxs-lookup"><span data-stu-id="4b620-106">You can use the Microsoft Unified Communications Open Interoperability Program for enterprise telephony infrastructure to find qualified public switched telephone network (PSTN) gateways, IP-PBXs, and SIP trunking services, including qualified IP telephony service providers.</span></span> <span data-ttu-id="4b620-107">如需詳細資訊，請參閱 Microsoft 整合通訊開啟交互操作[http://go.microsoft.com/fwlink/p/?LinkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309)性計畫網站。</span><span class="sxs-lookup"><span data-stu-id="4b620-107">For details, see the Microsoft Unified Communications Open Interoperability Program website at [http://go.microsoft.com/fwlink/p/?LinkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309).</span></span>

<div>

## <a name="mediation-server-support"></a><span data-ttu-id="4b620-108">中繼伺服器支援</span><span class="sxs-lookup"><span data-stu-id="4b620-108">Mediation Server Support</span></span>

<span data-ttu-id="4b620-109">若要實現 SIP 中繼，您必須透過中繼伺服器路由連線，該伺服器充當 Lync Server 2013 用戶端與服務提供者之間通訊會話的 proxy。</span><span class="sxs-lookup"><span data-stu-id="4b620-109">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Lync Server 2013 clients and the service provider.</span></span> <span data-ttu-id="4b620-110">中繼伺服器會從用戶端和伺服器解碼媒體流量，並在傳送給服務提供者之前重新進行編碼。</span><span class="sxs-lookup"><span data-stu-id="4b620-110">The Mediation Server decodes the media traffic from clients and servers and re-encodes it before sending it to the service provider.</span></span> <span data-ttu-id="4b620-111">您需要重新編碼，因為 SIP trunks 不支援某些使用的編解碼器，例如即時音訊（RTA）或適用于防火牆遍歷的互動式連接建立（ICE）通訊協定協商。</span><span class="sxs-lookup"><span data-stu-id="4b620-111">The re-encoding is needed because SIP trunks do not support some codecs used, such as Real Time Audio (RTA) or Interactive Connectivity Establishment (ICE) protocol negotiation for firewall traversal.</span></span>

<span data-ttu-id="4b620-112">每個中繼伺服器都可以有兩個網路介面卡，提供內部和外部網路介面。</span><span class="sxs-lookup"><span data-stu-id="4b620-112">Each Mediation Server can have two network adapters, which provide an internal and an external network interface.</span></span> <span data-ttu-id="4b620-113">外部介面通常稱為閘道介面，因為傳統的介面是用來連接 PSTN 閘道或 IP PBX。</span><span class="sxs-lookup"><span data-stu-id="4b620-113">The external interface is commonly called the gateway interface because, traditionally, it has been used to connect to a PSTN gateway or an IP-PBX.</span></span> <span data-ttu-id="4b620-114">若要實現 SIP 幹線，您可以將外部介面連接至服務提供者的會話邊界控制器（SBC）。</span><span class="sxs-lookup"><span data-stu-id="4b620-114">To implement a SIP trunk, you connect the external interface to a Session Border Controller (SBC) at a service provider.</span></span>

</div>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="4b620-115">集中化與分散式 SIP 中繼</span><span class="sxs-lookup"><span data-stu-id="4b620-115">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="4b620-116">*集中式*SIP 中繼路由所有透過網際網路通訊協定（VoIP）流量的語音，包括分支網站流量，以及透過您的資料中心。</span><span class="sxs-lookup"><span data-stu-id="4b620-116">*Centralized* SIP trunking routes all Voice over Internet Protocol (VoIP) traffic, including branch site traffic, through your data center.</span></span> <span data-ttu-id="4b620-117">[集中式部署模型] 簡單、經濟高效，而且通常是使用 Lync Server 2013 實現 SIP trunks 的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="4b620-117">The centralized deployment model is simple, cost-effective, and is generally the preferred approach for implementing SIP trunks with Lync Server 2013.</span></span>

<span data-ttu-id="4b620-118">您可能不想透過集中式 SIP 主幹來傳送所有使用者，這要視企業中的使用模式而定。</span><span class="sxs-lookup"><span data-stu-id="4b620-118">Depending on usage patterns within your enterprise, you may not want to route all users through the centralized SIP trunk.</span></span> <span data-ttu-id="4b620-119">若要分析您的需求，請回答下列問題：</span><span class="sxs-lookup"><span data-stu-id="4b620-119">To analyze your needs, answer the following questions:</span></span>

  - <span data-ttu-id="4b620-120">每個網站有多大？</span><span class="sxs-lookup"><span data-stu-id="4b620-120">How big is each site?</span></span> <span data-ttu-id="4b620-121">有多少使用者？</span><span class="sxs-lookup"><span data-stu-id="4b620-121">How many users?</span></span>

  - <span data-ttu-id="4b620-122">在每個網站上哪一條直向撥打電話（已有）號碼會取得最多電話？</span><span class="sxs-lookup"><span data-stu-id="4b620-122">Which Direct Inward Dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="4b620-123">*分散式*SIP 中繼是一種部署模型，您可以在其中一個或多個分支網站上執行本機 SIP 主幹。</span><span class="sxs-lookup"><span data-stu-id="4b620-123">*Distributed* SIP trunking is a deployment model in which you implement a local SIP trunk at one or more branch sites.</span></span> <span data-ttu-id="4b620-124">然後，VoIP 流量會直接從分支網站路由到其服務提供者，而不需要經過您的資料中心。</span><span class="sxs-lookup"><span data-stu-id="4b620-124">VoIP traffic is then routed from the branch site directly to their service provider, without going through your data center.</span></span>

<span data-ttu-id="4b620-125">只有在下列情況下，才需要分散式 SIP 中繼：</span><span class="sxs-lookup"><span data-stu-id="4b620-125">Distributed SIP trunking is required only in the following cases:</span></span>

  - <span data-ttu-id="4b620-126">分支網站需要 survivable 手機連線（例如 WAN 向下）。</span><span class="sxs-lookup"><span data-stu-id="4b620-126">The branch site requires survivable phone connectivity (for example, if the WAN goes down).</span></span> <span data-ttu-id="4b620-127">如果分支需要冗余及容錯移轉，服務提供者將會收取較高的費用，且設定需要較長的時間。</span><span class="sxs-lookup"><span data-stu-id="4b620-127">If the branch does need redundancy and failover, the service provider will charge more and the configuration will take longer.</span></span> <span data-ttu-id="4b620-128">這應該針對每個分支網站進行分析。</span><span class="sxs-lookup"><span data-stu-id="4b620-128">This should be analyzed for each branch site.</span></span> <span data-ttu-id="4b620-129">某些分支可能需要冗余和容錯移轉，而其他則可能不需要。</span><span class="sxs-lookup"><span data-stu-id="4b620-129">Some of your branches may require redundancy and failover, while others may not.</span></span>

  - <span data-ttu-id="4b620-130">分支網站與資料中心位於不同的國家/地區。</span><span class="sxs-lookup"><span data-stu-id="4b620-130">The branch site and data center are in different countries/regions.</span></span> <span data-ttu-id="4b620-131">出於相容性和法律原因，您至少需要針對每個國家/地區提供一個 SIP 幹線。</span><span class="sxs-lookup"><span data-stu-id="4b620-131">For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span>

<span data-ttu-id="4b620-132">決定是否要部署集中式或分散式 SIP 中繼需要成本效益分析。</span><span class="sxs-lookup"><span data-stu-id="4b620-132">Deciding whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis.</span></span> <span data-ttu-id="4b620-133">在某些情況下，選用分散式部署模式可能會有好處，即使不需要。</span><span class="sxs-lookup"><span data-stu-id="4b620-133">In some cases, it may be advantageous to opt for the distributed deployment mode, even if it is not required.</span></span> <span data-ttu-id="4b620-134">在完整的集中式部署中，所有分支網站流量都是透過 WAN 連結路由。</span><span class="sxs-lookup"><span data-stu-id="4b620-134">In a completely centralized deployment, all branch site traffic is routed over WAN links.</span></span> <span data-ttu-id="4b620-135">您可能會想要使用分散式 SIP 中繼，而不是針對 WAN 連結所需的頻寬付費。</span><span class="sxs-lookup"><span data-stu-id="4b620-135">Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4b620-136">如需有關為何以及如何使用分散式 SIP 中繼的詳細資料，請參閱規劃檔中的<A href="lync-server-2013-branch-site-sip-trunking.md">Lync Server 2013 中的分支網站 SIP 中繼</A>。</span><span class="sxs-lookup"><span data-stu-id="4b620-136">For details about why and how you might use distributed SIP trunking, see <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="4b620-137">支援的 SIP 中繼連線類型</span><span class="sxs-lookup"><span data-stu-id="4b620-137">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="4b620-138">Lync Server 2013 支援下列 SIP 中繼連線類型：</span><span class="sxs-lookup"><span data-stu-id="4b620-138">Lync Server 2013 supports the following connection types for SIP trunking:</span></span>

  - <span data-ttu-id="4b620-139">多協定標籤切換（MPLS）是一種私人網路絡，可引導並將資料從一個網路節點傳送到下一個。</span><span class="sxs-lookup"><span data-stu-id="4b620-139">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next.</span></span> <span data-ttu-id="4b620-140">MPLS 網路中的頻寬是與其他訂閱者共用的，每個資料包都指派標籤來區分訂閱者的資料與另一個訂閱者的資料。</span><span class="sxs-lookup"><span data-stu-id="4b620-140">The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber’s data from another’s.</span></span> <span data-ttu-id="4b620-141">此連線類型不需要 VPN。</span><span class="sxs-lookup"><span data-stu-id="4b620-141">This connection type does not require VPN.</span></span> <span data-ttu-id="4b620-142">可能的缺點是，過多的 IP 流量可能會干擾 VoIP 操作，除非 VoIP 流量是有優先權的。</span><span class="sxs-lookup"><span data-stu-id="4b620-142">A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

  - <span data-ttu-id="4b620-143">沒有其他流量的私人連線通常是最可靠且安全的連線類型（例如，租光纖連接或 T1 線路）。</span><span class="sxs-lookup"><span data-stu-id="4b620-143">A private connection with no other traffic is typically the most reliable and secure connection type (for example, a leased fiber-optic connection or T1 line).</span></span> <span data-ttu-id="4b620-144">這個連線類型提供最高的呼叫儲存容量，但通常是最昂貴的容量。</span><span class="sxs-lookup"><span data-stu-id="4b620-144">This connection type provides the highest call-carrying capacity, but is typically the most expensive.</span></span> <span data-ttu-id="4b620-145">VPN 不是必要的。</span><span class="sxs-lookup"><span data-stu-id="4b620-145">VPN is not required.</span></span> <span data-ttu-id="4b620-146">私人連線適合具有高呼叫量或嚴格的安全性和可用性需求的組織。</span><span class="sxs-lookup"><span data-stu-id="4b620-146">Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

  - <span data-ttu-id="4b620-147">公用網際網路是成本最低的連線類型，但也是最不可靠的，以及具有最低通話能力的容量。</span><span class="sxs-lookup"><span data-stu-id="4b620-147">The public Internet is the least expensive connection type, but also the least reliable, and the one with the lowest call-carrying capacity.</span></span> <span data-ttu-id="4b620-148">如果您的網際網路電話服務提供者（ITSP）支援傳輸層安全性（TLS）及安全即時傳輸通訊協定（SRTP）來加密信號與媒體流量，就能協助保護此 SIP 主幹連線類型。</span><span class="sxs-lookup"><span data-stu-id="4b620-148">Your Internet Telephony Service Provider (ITSP) can help secure this SIP trunk connection type if it supports Transport Layer Security (TLS) and Secure Real-Time Transport Protocol (SRTP) to encrypt signaling and media traffic.</span></span> <span data-ttu-id="4b620-149">如果您無法透過網際網路設定 SIP 中繼連線來使用 TLS 與 SRTP，我們強烈建議您使用 VPN 隧道來提供更安全的連線。</span><span class="sxs-lookup"><span data-stu-id="4b620-149">If you cannot configure a SIP trunk connection through the Internet to use TLS and SRTP, we strongly recommend that you use a VPN tunnel to provide a more secure connection.</span></span> <span data-ttu-id="4b620-150">請與您的 ITSP，以判斷它是否提供與 SRTP 的 TLS 支援。</span><span class="sxs-lookup"><span data-stu-id="4b620-150">Contact your ITSP to determine whether it provides support for TLS with SRTP.</span></span>

<div>

## <a name="selecting-a-connection-type"></a><span data-ttu-id="4b620-151">選取連線類型</span><span class="sxs-lookup"><span data-stu-id="4b620-151">Selecting a Connection Type</span></span>

<span data-ttu-id="4b620-152">貴企業最合適的 SIP 中繼連線類型取決於您的需求和預算。</span><span class="sxs-lookup"><span data-stu-id="4b620-152">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

  - <span data-ttu-id="4b620-153">針對中型或大型企業而言，MPLS 網路通常會提供最大的價值。</span><span class="sxs-lookup"><span data-stu-id="4b620-153">For a mid-size or larger enterprise, an MPLS network generally provides the most value.</span></span> <span data-ttu-id="4b620-154">它可以提供所需的頻寬，比專用的私人網路絡更便宜。</span><span class="sxs-lookup"><span data-stu-id="4b620-154">It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

  - <span data-ttu-id="4b620-155">大型企業可能需要專用光纖或 T1 連線。</span><span class="sxs-lookup"><span data-stu-id="4b620-155">Large enterprises may require a private fiber-optic or T1 connection.</span></span>

  - <span data-ttu-id="4b620-156">針對小型企業版或含有低通話量的分支網站，透過網際網路進行 SIP 中繼可能是最佳選擇。</span><span class="sxs-lookup"><span data-stu-id="4b620-156">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice.</span></span> <span data-ttu-id="4b620-157">不過，對於中等大小或較大的網站，建議不要使用此連線類型。</span><span class="sxs-lookup"><span data-stu-id="4b620-157">However, this connection type is not recommended for mid-size or larger sites.</span></span>

</div>

</div>

<div>

## <a name="codec-support"></a><span data-ttu-id="4b620-158">編解碼器支援</span><span class="sxs-lookup"><span data-stu-id="4b620-158">Codec Support</span></span>

<span data-ttu-id="4b620-159">服務提供者 proxy 必須支援下列編解碼器：</span><span class="sxs-lookup"><span data-stu-id="4b620-159">The service provider proxy must support the following codecs:</span></span>

  - <span data-ttu-id="4b620-160">G. 711 （主要在北美境外使用）</span><span class="sxs-lookup"><span data-stu-id="4b620-160">G.711 a-law (used primarily outside North America)</span></span>

  - <span data-ttu-id="4b620-161">G. 711 μ-定律（適用于北美）</span><span class="sxs-lookup"><span data-stu-id="4b620-161">G.711 µ-law (used in North America)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

