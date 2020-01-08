---
title: Lync Server 2013：如何實作 SIP 主幹？
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: How do I implement SIP trunking?
ms:assetid: 273a22b1-8a4c-4187-acf8-c57d5c6598ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425743(v=OCS.15)
ms:contentKeyID: 48183666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c14375f9e0b7f3a7615c11ddaca2bc6c46ec72f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974256"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-do-i-implement-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="56b68-102">如何在 Lync Server 2013 中實作 SIP 主幹？</span><span class="sxs-lookup"><span data-stu-id="56b68-102">How do I implement SIP trunking in Lync Server 2013?</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56b68-103">_**主題上次修改日期：** 2013-03-18_</span><span class="sxs-lookup"><span data-stu-id="56b68-103">_**Topic Last Modified:** 2013-03-18_</span></span>

<span data-ttu-id="56b68-104">若要實現 SIP 中繼，您必須透過中繼伺服器路由連線，該伺服器充當 Lync Server 2013 用戶端與服務提供者之間通訊會話的 proxy，以及在必要時使用 transcodes 媒體。</span><span class="sxs-lookup"><span data-stu-id="56b68-104">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Lync Server 2013 clients and the service provider and transcodes media, when necessary.</span></span>

<span data-ttu-id="56b68-105">每個中繼伺服器都有一個內部網路介面與一個外部網路介面。</span><span class="sxs-lookup"><span data-stu-id="56b68-105">Each Mediation Server has an internal network interface and an external network interface.</span></span> <span data-ttu-id="56b68-106">內部介面會連接到前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="56b68-106">The internal interface connects to the Front End Servers.</span></span> <span data-ttu-id="56b68-107">外部介面通常稱為閘道介面，因為它通常是用來將中繼伺服器連線到公用交換式電話網絡（PSTN）閘道或 IP PBX。</span><span class="sxs-lookup"><span data-stu-id="56b68-107">The external interface is commonly called the gateway interface because it has traditionally been used to connect the Mediation Server to a public switched telephone network (PSTN) gateway or an IP-PBX.</span></span> <span data-ttu-id="56b68-108">若要實施 SIP 幹線，您可以將中繼伺服器的外部介面連接到 ITSP 的外部邊緣元件。</span><span class="sxs-lookup"><span data-stu-id="56b68-108">To implement a SIP trunk, you connect the external interface of the Mediation Server to the external edge component of the ITSP.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="56b68-109">ITSP 的外部邊緣元件可以是 [會話邊界控制器（SBC）]、[路由器] 或 [閘道]。</span><span class="sxs-lookup"><span data-stu-id="56b68-109">The external edge component of the ITSP could be a Session Border Controller (SBC), a router, or a gateway.</span></span>



</div>

<span data-ttu-id="56b68-110">如需有關中繼伺服器的詳細資料，請參閱[Lync server 2013 中的 [轉送伺服器元件](lync-server-2013-mediation-server-component.md)]。</span><span class="sxs-lookup"><span data-stu-id="56b68-110">For details about Mediation Servers, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md).</span></span>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="56b68-111">集中化與分散式 SIP 中繼</span><span class="sxs-lookup"><span data-stu-id="56b68-111">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="56b68-112">*集中式*SIP 中繼路由所有透過網際網路通訊協定（VoIP）流量的語音，包括分支網站流量，透過您的中央網站進行。</span><span class="sxs-lookup"><span data-stu-id="56b68-112">*Centralized* SIP trunking routes all Voice over Internet Protocol (VoIP) traffic, including branch site traffic, through your central site.</span></span> <span data-ttu-id="56b68-113">[集中式部署模型] 簡單、經濟高效，而且通常是使用 Lync Server 2013 實現 SIP trunks 的建議方法。</span><span class="sxs-lookup"><span data-stu-id="56b68-113">The centralized deployment model is simple, cost-effective, and is generally the recommended approach for implementing SIP trunks with Lync Server 2013.</span></span>

<span data-ttu-id="56b68-114">*分散式*SIP 中繼是一種部署模型，您可以在其中一個或多個分支網站上執行本機 SIP 主幹。</span><span class="sxs-lookup"><span data-stu-id="56b68-114">*Distributed* SIP trunking is a deployment model in which you implement a local SIP trunk at one or more branch sites.</span></span> <span data-ttu-id="56b68-115">然後，VoIP 流量會直接從分支網站路由到服務提供者，而不需要透過中心網站。</span><span class="sxs-lookup"><span data-stu-id="56b68-115">VoIP traffic is then routed from the branch site directly to a service provider without going through the central site.</span></span>

<span data-ttu-id="56b68-116">只有在下列情況下，才需要分散式 SIP 中繼：</span><span class="sxs-lookup"><span data-stu-id="56b68-116">Distributed SIP trunking is required only in the following cases:</span></span>

  - <span data-ttu-id="56b68-117">分支網站需要 survivable 手機連線（例如 WAN 向下）。</span><span class="sxs-lookup"><span data-stu-id="56b68-117">The branch site requires survivable phone connectivity (for example, if the WAN goes down).</span></span> <span data-ttu-id="56b68-118">必須針對每個分支網站來分析此需求;某些分支可能需要冗余和容錯移轉，而其他則可能不需要。</span><span class="sxs-lookup"><span data-stu-id="56b68-118">This requirement should be analyzed for each branch site; some of your branches may require redundancy and failover, whereas others may not.</span></span>

  - <span data-ttu-id="56b68-119">在兩個中央網站之間必須具備復原能力。</span><span class="sxs-lookup"><span data-stu-id="56b68-119">Resiliency is required between two central sites.</span></span> <span data-ttu-id="56b68-120">您必須確定 SIP 主幹會在每個中央站台終止。</span><span class="sxs-lookup"><span data-stu-id="56b68-120">You need to make sure that a SIP trunk terminates at each central site.</span></span> <span data-ttu-id="56b68-121">例如，如果您有都柏林及 Tukwila 的中央網站，且兩者都只使用一個網站的 SIP 主幹，則在幹線關閉時，其他網站的使用者就無法進行 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="56b68-121">For example, if you have Dublin and Tukwila central sites and both use only one site’s SIP trunk, if the trunk goes down, the other site’s users cannot make PSTN calls.</span></span>

  - <span data-ttu-id="56b68-122">分支網站與中央網站位於不同的國家/地區。</span><span class="sxs-lookup"><span data-stu-id="56b68-122">The branch site and central site are in different countries/regions.</span></span> <span data-ttu-id="56b68-123">出於相容性和法律原因，您至少需要針對每個國家/地區提供一個 SIP 幹線。</span><span class="sxs-lookup"><span data-stu-id="56b68-123">For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span> <span data-ttu-id="56b68-124">例如，在 [歐盟] 中，通訊不能離開國家/地區，也不會在本機終止並集中點。</span><span class="sxs-lookup"><span data-stu-id="56b68-124">For example, in the European Union, communications cannot leave a country/region without terminating locally at a centralized point.</span></span>

<span data-ttu-id="56b68-125">根據網站的地理位置和您在企業中預期的流量，您可能不想要透過中央 SIP 主幹傳送所有使用者，或者您可以選擇透過 SIP 幹線在其分支網站上傳送部分使用者。</span><span class="sxs-lookup"><span data-stu-id="56b68-125">Depending on the geographical location of sites and how much traffic you anticipate within your enterprise, you may not want to route all users through the central SIP trunk, or you may opt to route some users through a SIP trunk at their branch site.</span></span> <span data-ttu-id="56b68-126">若要分析您的需求，請回答下列問題：</span><span class="sxs-lookup"><span data-stu-id="56b68-126">To analyze your needs, answer the following questions:</span></span>

  - <span data-ttu-id="56b68-127">每個網站有多大（也就是有多少使用者可供企業語音）？</span><span class="sxs-lookup"><span data-stu-id="56b68-127">How big is each site (that is, how many users are enabled for Enterprise Voice)?</span></span>

  - <span data-ttu-id="56b68-128">在每個網站上哪一條直向撥打電話（已有）號碼會取得最多電話？</span><span class="sxs-lookup"><span data-stu-id="56b68-128">Which direct inward dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="56b68-129">部署集中式或分散式 SIP 中繼的決定需要成本效益分析。</span><span class="sxs-lookup"><span data-stu-id="56b68-129">The decision whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis.</span></span> <span data-ttu-id="56b68-130">在某些情況下，您可以選擇選用分散式部署模型（即使不需要）。</span><span class="sxs-lookup"><span data-stu-id="56b68-130">In some cases, it may be advantageous to opt for the distributed deployment model even if it is not required.</span></span> <span data-ttu-id="56b68-131">在完整的集中式部署中，所有分支網站流量都是透過 WAN 連結路由。</span><span class="sxs-lookup"><span data-stu-id="56b68-131">In a completely centralized deployment, all branch site traffic is routed over WAN links.</span></span> <span data-ttu-id="56b68-132">您可能會想要使用分散式 SIP 中繼，而不是針對 WAN 連結所需的頻寬付費。</span><span class="sxs-lookup"><span data-stu-id="56b68-132">Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span> <span data-ttu-id="56b68-133">例如，您可能會想要在分支網站上部署標準版伺服器，並在中央網站使用同盟，或者您可能想要部署 Survivable 分支裝置或 Survivable 分支伺服器與小型閘道。</span><span class="sxs-lookup"><span data-stu-id="56b68-133">For example, you may want to deploy a Standard Edition server at a branch site with federation to the central site, or you may want to deploy a Survivable Branch Appliance or a Survivable Branch Server with a small gateway.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="56b68-134">如需分散式 SIP 中繼的詳細資料，請參閱<A href="lync-server-2013-branch-site-sip-trunking.md">Lync Server 2013 中的分支網站 SIP 中繼</A>。</span><span class="sxs-lookup"><span data-stu-id="56b68-134">For details about distributed SIP trunking, see <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="56b68-135">支援的 SIP 中繼連線類型</span><span class="sxs-lookup"><span data-stu-id="56b68-135">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="56b68-136">Lync Server 支援下列 SIP 中繼連線類型：</span><span class="sxs-lookup"><span data-stu-id="56b68-136">Lync Server supports the following connection types for SIP trunking:</span></span>

  - <span data-ttu-id="56b68-137">多協定標籤切換（MPLS）是一種私人網路絡，可引導並將資料從一個網路節點傳送到下一個。</span><span class="sxs-lookup"><span data-stu-id="56b68-137">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next.</span></span> <span data-ttu-id="56b68-138">MPLS 網路中的頻寬是與其他訂閱者共用的，每個資料包都指派標籤來區分訂閱者的資料與另一個訂閱者的資料。</span><span class="sxs-lookup"><span data-stu-id="56b68-138">The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber’s data from another’s.</span></span> <span data-ttu-id="56b68-139">此連線類型不需要虛擬私人網路（VPN）。</span><span class="sxs-lookup"><span data-stu-id="56b68-139">This connection type does not require a virtual private network (VPN).</span></span> <span data-ttu-id="56b68-140">可能的缺點是，過多的 IP 流量可能會干擾 VoIP 操作，除非 VoIP 流量是有優先權的。</span><span class="sxs-lookup"><span data-stu-id="56b68-140">A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

  - <span data-ttu-id="56b68-141">沒有其他通訊的私人連線（例如租用的光纖連接或 T1 線路）通常是最可靠且安全的連線類型。</span><span class="sxs-lookup"><span data-stu-id="56b68-141">A private connection with no other traffic—for example, a leased fiber-optic connection or T1 line—is typically the most reliable and secure connection type.</span></span> <span data-ttu-id="56b68-142">這個連線類型提供最高的呼叫儲存容量，但通常是最昂貴的容量。</span><span class="sxs-lookup"><span data-stu-id="56b68-142">This connection type provides the highest call-carrying capacity, but it is typically the most expensive.</span></span> <span data-ttu-id="56b68-143">VPN 不是必要的。</span><span class="sxs-lookup"><span data-stu-id="56b68-143">VPN is not required.</span></span> <span data-ttu-id="56b68-144">私人連線適合具有高呼叫量或嚴格的安全性和可用性需求的組織。</span><span class="sxs-lookup"><span data-stu-id="56b68-144">Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

  - <span data-ttu-id="56b68-145">網際網路是成本最低的連線類型，但也是最不可靠的。</span><span class="sxs-lookup"><span data-stu-id="56b68-145">The Internet is the least expensive connection type, but it is also the least reliable.</span></span> <span data-ttu-id="56b68-146">[網際網路連線] 是唯一需要 VPN 的 Lync Server SIP 中繼連線類型。</span><span class="sxs-lookup"><span data-stu-id="56b68-146">Internet connection is the only Lync Server SIP trunking connection type that requires VPN.</span></span>

<div>

## <a name="selecting-a-connection-type"></a><span data-ttu-id="56b68-147">選取連線類型</span><span class="sxs-lookup"><span data-stu-id="56b68-147">Selecting a Connection Type</span></span>

<span data-ttu-id="56b68-148">貴企業最合適的 SIP 中繼連線類型取決於您的需求和預算。</span><span class="sxs-lookup"><span data-stu-id="56b68-148">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

  - <span data-ttu-id="56b68-149">針對中型或大型企業而言，MPLS 網路通常會提供最大的價值。</span><span class="sxs-lookup"><span data-stu-id="56b68-149">For a mid-size or larger enterprise, an MPLS network usually provides the greatest value.</span></span> <span data-ttu-id="56b68-150">它可以提供所需的頻寬，比專用的私人網路絡更便宜。</span><span class="sxs-lookup"><span data-stu-id="56b68-150">It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

  - <span data-ttu-id="56b68-151">大型企業可能需要在歐盟中使用私有光纖、T1、T3 或更高的連線（E1、E3 或較高的介面）。</span><span class="sxs-lookup"><span data-stu-id="56b68-151">Large enterprises may require a private fiber-optic, T1, T3 or higher connection (E1, E3 or higher in the European Union).</span></span>

  - <span data-ttu-id="56b68-152">針對小型企業版或含有低通話量的分支網站，透過網際網路進行 SIP 中繼可能是最佳選擇。</span><span class="sxs-lookup"><span data-stu-id="56b68-152">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice.</span></span> <span data-ttu-id="56b68-153">建議您不要針對中型或大型網站使用此連線類型。</span><span class="sxs-lookup"><span data-stu-id="56b68-153">This connection type is not recommended for mid-size or larger sites.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-requirements"></a><span data-ttu-id="56b68-154">頻寬需求</span><span class="sxs-lookup"><span data-stu-id="56b68-154">Bandwidth Requirements</span></span>

<span data-ttu-id="56b68-155">您的實現所需的頻寬量，取決於撥號容量（您必須能夠支援的併發呼叫數量）。</span><span class="sxs-lookup"><span data-stu-id="56b68-155">The amount of bandwidth your implementation requires depends on call capacity (the number of concurrent calls you must be able to support).</span></span> <span data-ttu-id="56b68-156">您必須考慮頻寬可用性，才能充分利用您已支付的峰值容量。</span><span class="sxs-lookup"><span data-stu-id="56b68-156">You need to consider bandwidth availability, so that you can take full advantage of the peak capacity that you have paid for.</span></span> <span data-ttu-id="56b68-157">使用下列公式來計算 SIP 中繼峰值頻寬需求：</span><span class="sxs-lookup"><span data-stu-id="56b68-157">Use the following formula to calculate SIP trunk peak bandwidth requirement:</span></span>

<span data-ttu-id="56b68-158">SIP 幹線峰值頻寬 = 最大同時呼叫 x （64 kbps + 標頭大小）</span><span class="sxs-lookup"><span data-stu-id="56b68-158">SIP Trunk Peak Bandwidth = Max Simultaneous Calls x (64 kbps + header size)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="56b68-159">[標頭大小] 的最大值為20個位元組。</span><span class="sxs-lookup"><span data-stu-id="56b68-159">Header size is 20 bytes maximum.</span></span>



</div>

</div>

<div>

## <a name="codec-support"></a><span data-ttu-id="56b68-160">編解碼器支援</span><span class="sxs-lookup"><span data-stu-id="56b68-160">Codec Support</span></span>

<span data-ttu-id="56b68-161">Lync Server 2013 只支援下列編解碼器：</span><span class="sxs-lookup"><span data-stu-id="56b68-161">Lync Server 2013 supports only the following codecs:</span></span>

  - <span data-ttu-id="56b68-162">G. 711 （主要在北美境外使用）</span><span class="sxs-lookup"><span data-stu-id="56b68-162">G.711 a-law (used primarily outside North America)</span></span>

  - <span data-ttu-id="56b68-163">G. 711 μ-定律（適用于北美）</span><span class="sxs-lookup"><span data-stu-id="56b68-163">G.711 µ-law (used in North America)</span></span>

</div>

<div>

## <a name="internet-telephony-service-provider"></a><span data-ttu-id="56b68-164">網際網路電話服務提供者</span><span class="sxs-lookup"><span data-stu-id="56b68-164">Internet Telephony Service Provider</span></span>

<span data-ttu-id="56b68-165">您實現 SIP 中繼連線的服務提供者的方式，從一個 ITSP 到另一個不同。</span><span class="sxs-lookup"><span data-stu-id="56b68-165">How you implement the service provider side of a SIP trunk connection varies from one ITSP to another.</span></span> <span data-ttu-id="56b68-166">如需部署資訊，請聯絡您的服務提供者。</span><span class="sxs-lookup"><span data-stu-id="56b68-166">For deployment information, contact your service provider.</span></span> <span data-ttu-id="56b68-167">如需認證 SIP 中繼服務提供者清單，請參閱[Microsoft 整合通訊開啟互通性計畫網站](http://go.microsoft.com/fwlink/?linkid=287029)。</span><span class="sxs-lookup"><span data-stu-id="56b68-167">For a list of certified SIP trunking service providers, see [Microsoft Unified Communications Open Interoperability Program website](http://go.microsoft.com/fwlink/?linkid=287029).</span></span>

<span data-ttu-id="56b68-168">如需 Microsoft 認證 SIP 中繼提供者的詳細資料，請與您的 Microsoft 代表。</span><span class="sxs-lookup"><span data-stu-id="56b68-168">For details about Microsoft certified SIP trunking providers, contact your Microsoft representative.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="56b68-169">您必須使用 Microsoft 認證服務提供者，以確保您的 ITSP 支援所有流經 SIP 幹線的功能（例如，設定及管理會話，以及支援所有延伸 VoIP 服務）。</span><span class="sxs-lookup"><span data-stu-id="56b68-169">You must use a Microsoft certified service provider to ensure that your ITSP supports all of the functionality that traverses the SIP trunk (for example, setting up and managing sessions and supporting all of the extended VoIP services).</span></span> <span data-ttu-id="56b68-170">Microsoft 技術支援不會延伸到使用 noncertified 提供者的設定。</span><span class="sxs-lookup"><span data-stu-id="56b68-170">Microsoft technical support does not extend to configurations that use noncertified providers.</span></span> <span data-ttu-id="56b68-171">如果您目前使用的網際網路服務提供者未經過 SIP 中繼認證，您可以選擇繼續使用該提供者作為 ISP，然後使用 Microsoft 針對 SIP 中繼認證的提供者。</span><span class="sxs-lookup"><span data-stu-id="56b68-171">If you currently use an Internet service provider that is not certified for SIP trunking, you can opt to continue using that provider as your ISP and use a provider certified by Microsoft for SIP trunking.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

