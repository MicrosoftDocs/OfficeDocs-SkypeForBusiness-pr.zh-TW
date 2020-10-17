---
title: Lync Server 2013 SIP 主幹支援
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
ms.openlocfilehash: 8d9bbf5ea35b6b24180f7853fd3715ad95973051
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519650"
---
# <a name="sip-trunking-support-in-lync-server-2013"></a><span data-ttu-id="61f19-102">Lync Server 2013 的 SIP 主幹支援</span><span class="sxs-lookup"><span data-stu-id="61f19-102">SIP trunking support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61f19-103">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="61f19-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="61f19-104">如果您打算將 Enterprise Voice 用於 SIP 主幹，您必須部署轉送伺服器，並確定其他基礎結構和元件符合部署模型適用的支援需求。</span><span class="sxs-lookup"><span data-stu-id="61f19-104">If you plan to use Enterprise Voice with SIP trunking, you must deploy a Mediation Server and make sure that other infrastructure and components meet the support requirements appropriate to your deployment model.</span></span> <span data-ttu-id="61f19-105">如需決定是否要執行 SIP trunk 的詳細資訊，請參閱規劃檔中的 [Lync Server 2013 中的 SIP](lync-server-2013-overview-of-sip-trunking.md) 主幹。</span><span class="sxs-lookup"><span data-stu-id="61f19-105">For details about determining whether to implement SIP trunking, see [Overview of SIP trunking in Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) in the Planning documentation.</span></span>

<span data-ttu-id="61f19-106">您可以使用適用于企業電話語音基礎結構的 Microsoft 整合通訊「開啟互通性」方案，尋找合格的公用交換電話網路 (PSTN) 閘道、IP PBXs 和 SIP trunk 服務，包括合格的 IP 電話語音服務提供者。</span><span class="sxs-lookup"><span data-stu-id="61f19-106">You can use the Microsoft Unified Communications Open Interoperability Program for enterprise telephony infrastructure to find qualified public switched telephone network (PSTN) gateways, IP-PBXs, and SIP trunking services, including qualified IP telephony service providers.</span></span> <span data-ttu-id="61f19-107">如需詳細資訊，請參閱 Microsoft 整合通訊開啟互通性計畫網站，網址為 [https://go.microsoft.com/fwlink/p/?LinkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309) 。</span><span class="sxs-lookup"><span data-stu-id="61f19-107">For details, see the Microsoft Unified Communications Open Interoperability Program website at [https://go.microsoft.com/fwlink/p/?LinkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309).</span></span>

<div>

## <a name="mediation-server-support"></a><span data-ttu-id="61f19-108">轉送伺服器支援</span><span class="sxs-lookup"><span data-stu-id="61f19-108">Mediation Server Support</span></span>

<span data-ttu-id="61f19-109">若要執行 SIP 主幹，您必須透過轉送伺服器路由傳送，該伺服器充當 Lync Server 2013 用戶端與服務提供者之間的通訊會話 proxy。</span><span class="sxs-lookup"><span data-stu-id="61f19-109">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Lync Server 2013 clients and the service provider.</span></span> <span data-ttu-id="61f19-110">轉送伺服器會對來自用戶端和伺服器的媒體流量進行解碼，並在將其傳送至服務提供者之前對其重新進行編碼。</span><span class="sxs-lookup"><span data-stu-id="61f19-110">The Mediation Server decodes the media traffic from clients and servers and re-encodes it before sending it to the service provider.</span></span> <span data-ttu-id="61f19-111">重新編碼是必要的，因為 SIP 主幹不支援某些使用的編解碼器，例如即時音訊 (RTA) 或互動式連線建立 (冰) 的通訊協定協商，以進行防火牆遍歷。</span><span class="sxs-lookup"><span data-stu-id="61f19-111">The re-encoding is needed because SIP trunks do not support some codecs used, such as Real Time Audio (RTA) or Interactive Connectivity Establishment (ICE) protocol negotiation for firewall traversal.</span></span>

<span data-ttu-id="61f19-112">每個轉送伺服器都可以有兩個網路介面卡，其提供內部和外部網路介面。</span><span class="sxs-lookup"><span data-stu-id="61f19-112">Each Mediation Server can have two network adapters, which provide an internal and an external network interface.</span></span> <span data-ttu-id="61f19-113">外部介面一般稱為閘道介面，因為傳統上它是用來連接到 PSTN 閘道或 IP-PBX。</span><span class="sxs-lookup"><span data-stu-id="61f19-113">The external interface is commonly called the gateway interface because, traditionally, it has been used to connect to a PSTN gateway or an IP-PBX.</span></span> <span data-ttu-id="61f19-114">若要執行 SIP 主幹，請將外部介面連接至服務提供者 (SBC) 的會話邊界控制器。</span><span class="sxs-lookup"><span data-stu-id="61f19-114">To implement a SIP trunk, you connect the external interface to a Session Border Controller (SBC) at a service provider.</span></span>

</div>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="61f19-115">集中式與分散式 SIP 主幹的比較</span><span class="sxs-lookup"><span data-stu-id="61f19-115">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="61f19-116">*集中式* SIP 主幹會透過網際網路通訊協定 (VoIP) 流量（包括分支網站流量），透過您的資料中心來路由傳送所有語音。</span><span class="sxs-lookup"><span data-stu-id="61f19-116">*Centralized* SIP trunking routes all Voice over Internet Protocol (VoIP) traffic, including branch site traffic, through your data center.</span></span> <span data-ttu-id="61f19-117">集中式部署模型是簡單、經濟划算的，通常是以 Lync Server 2013 實施 SIP 主幹的慣用方法。</span><span class="sxs-lookup"><span data-stu-id="61f19-117">The centralized deployment model is simple, cost-effective, and is generally the preferred approach for implementing SIP trunks with Lync Server 2013.</span></span>

<span data-ttu-id="61f19-118">根據企業內的使用模式，您可能不想要透過集中式 SIP 主幹路由傳送所有使用者。</span><span class="sxs-lookup"><span data-stu-id="61f19-118">Depending on usage patterns within your enterprise, you may not want to route all users through the centralized SIP trunk.</span></span> <span data-ttu-id="61f19-119">若要分析自身需求，請回答下列問題：</span><span class="sxs-lookup"><span data-stu-id="61f19-119">To analyze your needs, answer the following questions:</span></span>

  - <span data-ttu-id="61f19-120">每個網站有多大？</span><span class="sxs-lookup"><span data-stu-id="61f19-120">How big is each site?</span></span> <span data-ttu-id="61f19-121">有多少使用者？</span><span class="sxs-lookup"><span data-stu-id="61f19-121">How many users?</span></span>

  - <span data-ttu-id="61f19-122">在每個網站上，哪個直接向內撥號 () 號碼會取得最多的電話？</span><span class="sxs-lookup"><span data-stu-id="61f19-122">Which Direct Inward Dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="61f19-123">*分散式* SIP 主幹是一種部署模型，您可以在其中執行一或多個分支網站上的本機 SIP 主幹。</span><span class="sxs-lookup"><span data-stu-id="61f19-123">*Distributed* SIP trunking is a deployment model in which you implement a local SIP trunk at one or more branch sites.</span></span> <span data-ttu-id="61f19-124">VoIP 流量會從分支網站直接路由傳送至其服務提供者，而不需要透過您的資料中心。</span><span class="sxs-lookup"><span data-stu-id="61f19-124">VoIP traffic is then routed from the branch site directly to their service provider, without going through your data center.</span></span>

<span data-ttu-id="61f19-125">只有下列情況才必須使用分散式 SIP 主幹：</span><span class="sxs-lookup"><span data-stu-id="61f19-125">Distributed SIP trunking is required only in the following cases:</span></span>

  - <span data-ttu-id="61f19-126">分支網站需要 survivable phone connectivity (例如，如果 WAN 停機) 。</span><span class="sxs-lookup"><span data-stu-id="61f19-126">The branch site requires survivable phone connectivity (for example, if the WAN goes down).</span></span> <span data-ttu-id="61f19-127">如果分支需要重複和容錯移轉，服務提供者將會收費，且設定會花更長的時間。</span><span class="sxs-lookup"><span data-stu-id="61f19-127">If the branch does need redundancy and failover, the service provider will charge more and the configuration will take longer.</span></span> <span data-ttu-id="61f19-128">這應該會針對每個分支網站進行分析。</span><span class="sxs-lookup"><span data-stu-id="61f19-128">This should be analyzed for each branch site.</span></span> <span data-ttu-id="61f19-129">您的部分分支可能需要冗余和容錯移轉，但其他分支可能不需要。</span><span class="sxs-lookup"><span data-stu-id="61f19-129">Some of your branches may require redundancy and failover, while others may not.</span></span>

  - <span data-ttu-id="61f19-130">分支網站和資料中心位於不同的國家/地區。</span><span class="sxs-lookup"><span data-stu-id="61f19-130">The branch site and data center are in different countries/regions.</span></span> <span data-ttu-id="61f19-131">基於相容性與法規考量，每個國家/地區至少要有一個 SIP 主幹。</span><span class="sxs-lookup"><span data-stu-id="61f19-131">For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span>

<span data-ttu-id="61f19-132">決定是否要部署集中式或分散式 SIP 中繼時，需要成本效益分析。</span><span class="sxs-lookup"><span data-stu-id="61f19-132">Deciding whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis.</span></span> <span data-ttu-id="61f19-133">在某些情況下，選用分散式部署模式也是有益的，即使不是必要也一樣。</span><span class="sxs-lookup"><span data-stu-id="61f19-133">In some cases, it may be advantageous to opt for the distributed deployment mode, even if it is not required.</span></span> <span data-ttu-id="61f19-134">在完整的集中式部署中，所有分支網站流量都透過 WAN 連結路由傳送。</span><span class="sxs-lookup"><span data-stu-id="61f19-134">In a completely centralized deployment, all branch site traffic is routed over WAN links.</span></span> <span data-ttu-id="61f19-135">與其為 WAN 連結所需的頻寬支付高額費用，您可能寧可使用分散式 SIP 主幹。</span><span class="sxs-lookup"><span data-stu-id="61f19-135">Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="61f19-136">如需有關如何使用分散式 SIP 主幹的原因和方式的詳細資訊，請參閱規劃檔中的 <A href="lync-server-2013-branch-site-sip-trunking.md">Branch SITE SIP trunk In Lync Server 2013</A> 。</span><span class="sxs-lookup"><span data-stu-id="61f19-136">For details about why and how you might use distributed SIP trunking, see <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="61f19-137">支援的 SIP 主幹連線類型</span><span class="sxs-lookup"><span data-stu-id="61f19-137">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="61f19-138">Lync Server 2013 支援 SIP 主幹的下列連線類型：</span><span class="sxs-lookup"><span data-stu-id="61f19-138">Lync Server 2013 supports the following connection types for SIP trunking:</span></span>

  - <span data-ttu-id="61f19-139">Multiprotocol Label Switching (MPLS) 是可將資料從一個網路節點導向及承載到另一個網路節點的私人網路。</span><span class="sxs-lookup"><span data-stu-id="61f19-139">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next.</span></span> <span data-ttu-id="61f19-140">MPLS 網路的頻寬會與其他訂戶共用，並且會為每個資料封包指派一個標籤，用以區別不同訂戶的資料。</span><span class="sxs-lookup"><span data-stu-id="61f19-140">The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber’s data from another’s.</span></span> <span data-ttu-id="61f19-141">此連線類型不需要 VPN。</span><span class="sxs-lookup"><span data-stu-id="61f19-141">This connection type does not require VPN.</span></span> <span data-ttu-id="61f19-142">可能的缺點是，過多的 IP 流量可能會干擾 VoIP 作業，除非 VoIP 流量享有優先權。</span><span class="sxs-lookup"><span data-stu-id="61f19-142">A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

  - <span data-ttu-id="61f19-143">沒有其他流量的專用連線通常是最可靠且安全的連線類型 (例如，租用的光纜光纜或 T1 線路) 。</span><span class="sxs-lookup"><span data-stu-id="61f19-143">A private connection with no other traffic is typically the most reliable and secure connection type (for example, a leased fiber-optic connection or T1 line).</span></span> <span data-ttu-id="61f19-144">此連線類型可提供最高的通話容量，但通常是最昂貴的容量。</span><span class="sxs-lookup"><span data-stu-id="61f19-144">This connection type provides the highest call-carrying capacity, but is typically the most expensive.</span></span> <span data-ttu-id="61f19-145">此連線類型不需要 VPN。</span><span class="sxs-lookup"><span data-stu-id="61f19-145">VPN is not required.</span></span> <span data-ttu-id="61f19-146">私人連線適用於通話量大或安全性與可用性需求很高的組織。</span><span class="sxs-lookup"><span data-stu-id="61f19-146">Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

  - <span data-ttu-id="61f19-147">公用 Internet 是最低成本的連線類型，但也是最不可靠的，且具有最低通話能力的連線類型。</span><span class="sxs-lookup"><span data-stu-id="61f19-147">The public Internet is the least expensive connection type, but also the least reliable, and the one with the lowest call-carrying capacity.</span></span> <span data-ttu-id="61f19-148">您的網際網路電話語音服務提供者 (ITSP) 可以協助保護這種 SIP 主幹連線類型（如果它支援傳輸層安全性 (TLS) 及安全 Real-Time 傳輸通訊協定 (SRTP) ，以加密信號和媒體流量）。</span><span class="sxs-lookup"><span data-stu-id="61f19-148">Your Internet Telephony Service Provider (ITSP) can help secure this SIP trunk connection type if it supports Transport Layer Security (TLS) and Secure Real-Time Transport Protocol (SRTP) to encrypt signaling and media traffic.</span></span> <span data-ttu-id="61f19-149">如果您無法透過網際網路設定 SIP 主幹連線以使用 TLS 和 SRTP，強烈建議您使用 VPN 隧道提供更安全的連線。</span><span class="sxs-lookup"><span data-stu-id="61f19-149">If you cannot configure a SIP trunk connection through the Internet to use TLS and SRTP, we strongly recommend that you use a VPN tunnel to provide a more secure connection.</span></span> <span data-ttu-id="61f19-150">請與您的 ITSP 聯繫，以判斷其是否提供與 SRTP 的 TLS 支援。</span><span class="sxs-lookup"><span data-stu-id="61f19-150">Contact your ITSP to determine whether it provides support for TLS with SRTP.</span></span>

<div>

## <a name="selecting-a-connection-type"></a><span data-ttu-id="61f19-151">選取連線類型</span><span class="sxs-lookup"><span data-stu-id="61f19-151">Selecting a Connection Type</span></span>

<span data-ttu-id="61f19-152">您的企業最適合使用的 SIP 主幹連線類型，端視您的需求與預算而定。</span><span class="sxs-lookup"><span data-stu-id="61f19-152">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

  - <span data-ttu-id="61f19-153">針對中型或大型企業，MPLS 網路通常會提供最大的價值。</span><span class="sxs-lookup"><span data-stu-id="61f19-153">For a mid-size or larger enterprise, an MPLS network generally provides the most value.</span></span> <span data-ttu-id="61f19-154">它可以低於特殊私人網路的費率提供所需的頻寬。</span><span class="sxs-lookup"><span data-stu-id="61f19-154">It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

  - <span data-ttu-id="61f19-155">大型企業可能需要私人光纖或 T1 連接。</span><span class="sxs-lookup"><span data-stu-id="61f19-155">Large enterprises may require a private fiber-optic or T1 connection.</span></span>

  - <span data-ttu-id="61f19-156">對於具有低通話數量的小型企業或分支網站，透過網際網路的 SIP 主幹可能是最佳選擇。</span><span class="sxs-lookup"><span data-stu-id="61f19-156">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice.</span></span> <span data-ttu-id="61f19-157">不過，對於中型或大型網站，不建議使用此連線類型。</span><span class="sxs-lookup"><span data-stu-id="61f19-157">However, this connection type is not recommended for mid-size or larger sites.</span></span>

</div>

</div>

<div>

## <a name="codec-support"></a><span data-ttu-id="61f19-158">轉碼器支援</span><span class="sxs-lookup"><span data-stu-id="61f19-158">Codec Support</span></span>

<span data-ttu-id="61f19-159">服務提供者 proxy 必須支援下列編解碼器：</span><span class="sxs-lookup"><span data-stu-id="61f19-159">The service provider proxy must support the following codecs:</span></span>

  - <span data-ttu-id="61f19-160">G.711 a-law (主要使用於北美以外的地區)</span><span class="sxs-lookup"><span data-stu-id="61f19-160">G.711 a-law (used primarily outside North America)</span></span>

  - <span data-ttu-id="61f19-161">G.711 µ-law (使用於北美地區)</span><span class="sxs-lookup"><span data-stu-id="61f19-161">G.711 µ-law (used in North America)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

