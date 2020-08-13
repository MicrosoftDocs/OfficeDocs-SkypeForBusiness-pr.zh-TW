---
title: Lync Server 2013：如何執行 SIP 主幹？
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How do I implement SIP trunking?
ms:assetid: 273a22b1-8a4c-4187-acf8-c57d5c6598ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425743(v=OCS.15)
ms:contentKeyID: 48183666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28d9b55dff41e0013852b52eee97eb26fef3997e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204545"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="how-do-i-implement-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="25b0b-102">如何在 Lync Server 2013 中實施 SIP 主幹？</span><span class="sxs-lookup"><span data-stu-id="25b0b-102">How do I implement SIP trunking in Lync Server 2013?</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25b0b-103">_**主題上次修改日期：** 2013-03-18_</span><span class="sxs-lookup"><span data-stu-id="25b0b-103">_**Topic Last Modified:** 2013-03-18_</span></span>

<span data-ttu-id="25b0b-104">若要執行 SIP 主幹，您必須透過轉送伺服器路由傳送，該伺服器可充當 Lync Server 2013 用戶端與服務提供者和 transcodes 媒體（必要時）之間的通訊會話 proxy。</span><span class="sxs-lookup"><span data-stu-id="25b0b-104">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Lync Server 2013 clients and the service provider and transcodes media, when necessary.</span></span>

<span data-ttu-id="25b0b-105">每個轉送伺服器都具有內部網路介面和外部網路介面。</span><span class="sxs-lookup"><span data-stu-id="25b0b-105">Each Mediation Server has an internal network interface and an external network interface.</span></span> <span data-ttu-id="25b0b-106">內部介面連接至前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="25b0b-106">The internal interface connects to the Front End Servers.</span></span> <span data-ttu-id="25b0b-107">外部介面一般稱為閘道介面，因為傳統上它是用來將轉送伺服器連接到公用交換電話網路 (PSTN) 閘道或 IP-PBX。</span><span class="sxs-lookup"><span data-stu-id="25b0b-107">The external interface is commonly called the gateway interface because it has traditionally been used to connect the Mediation Server to a public switched telephone network (PSTN) gateway or an IP-PBX.</span></span> <span data-ttu-id="25b0b-108">若要執行 SIP 主幹，您可以將轉送伺服器的外部介面連接至 ITSP 的外部 edge 元件。</span><span class="sxs-lookup"><span data-stu-id="25b0b-108">To implement a SIP trunk, you connect the external interface of the Mediation Server to the external edge component of the ITSP.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="25b0b-109">ITSP 的外部 Edge 元件可以是工作階段界限控制器 (SBC)、路由器或閘道。</span><span class="sxs-lookup"><span data-stu-id="25b0b-109">The external edge component of the ITSP could be a Session Border Controller (SBC), a router, or a gateway.</span></span>



</div>

<span data-ttu-id="25b0b-110">如需有關轉送伺服器的詳細資訊，請參閱[Lync server 2013 中的轉送伺服器元件](lync-server-2013-mediation-server-component.md)。</span><span class="sxs-lookup"><span data-stu-id="25b0b-110">For details about Mediation Servers, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md).</span></span>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="25b0b-111">集中式與分散式 SIP 主幹的比較</span><span class="sxs-lookup"><span data-stu-id="25b0b-111">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="25b0b-112">*集中式*SIP 主幹會將所有 Voice over Internet Protocol (VoIP) 流量，包括分支網站流量（透過您的中央網站）。</span><span class="sxs-lookup"><span data-stu-id="25b0b-112">*Centralized* SIP trunking routes all Voice over Internet Protocol (VoIP) traffic, including branch site traffic, through your central site.</span></span> <span data-ttu-id="25b0b-113">集中式部署模型是簡單、經濟划算的，通常是以 Lync Server 2013 實施 SIP 主幹的建議方法。</span><span class="sxs-lookup"><span data-stu-id="25b0b-113">The centralized deployment model is simple, cost-effective, and is generally the recommended approach for implementing SIP trunks with Lync Server 2013.</span></span>

<span data-ttu-id="25b0b-114">*分散式*SIP 主幹是一種部署模型，您可以在其中執行一或多個分支網站上的本機 SIP 主幹。</span><span class="sxs-lookup"><span data-stu-id="25b0b-114">*Distributed* SIP trunking is a deployment model in which you implement a local SIP trunk at one or more branch sites.</span></span> <span data-ttu-id="25b0b-115">VoIP 流量會從分支網站直接路由傳送至服務提供者，而不需要透過中央網站。</span><span class="sxs-lookup"><span data-stu-id="25b0b-115">VoIP traffic is then routed from the branch site directly to a service provider without going through the central site.</span></span>

<span data-ttu-id="25b0b-116">只有下列情況才必須使用分散式 SIP 主幹：</span><span class="sxs-lookup"><span data-stu-id="25b0b-116">Distributed SIP trunking is required only in the following cases:</span></span>

  - <span data-ttu-id="25b0b-117">分支網站需要 survivable phone connectivity (例如，如果 WAN 停機) 。</span><span class="sxs-lookup"><span data-stu-id="25b0b-117">The branch site requires survivable phone connectivity (for example, if the WAN goes down).</span></span> <span data-ttu-id="25b0b-118">應該針對每個分支網站來分析此需求;您的部分分支可能需要冗余和容錯移轉，但其他分支可能不需要。</span><span class="sxs-lookup"><span data-stu-id="25b0b-118">This requirement should be analyzed for each branch site; some of your branches may require redundancy and failover, whereas others may not.</span></span>

  - <span data-ttu-id="25b0b-119">兩部中央網站之間需要恢復功能。</span><span class="sxs-lookup"><span data-stu-id="25b0b-119">Resiliency is required between two central sites.</span></span> <span data-ttu-id="25b0b-120">您必須確定 SIP 主幹會在每個中央網站終止。</span><span class="sxs-lookup"><span data-stu-id="25b0b-120">You need to make sure that a SIP trunk terminates at each central site.</span></span> <span data-ttu-id="25b0b-121">例如，如果您有都柏林和 Tukwila 中央網站，且兩者都只使用一個網站的 SIP 主幹，如果主幹中斷，其他網站的使用者將無法進行 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="25b0b-121">For example, if you have Dublin and Tukwila central sites and both use only one site’s SIP trunk, if the trunk goes down, the other site’s users cannot make PSTN calls.</span></span>

  - <span data-ttu-id="25b0b-122">分支網站與中央網站位於不同的國家/地區。</span><span class="sxs-lookup"><span data-stu-id="25b0b-122">The branch site and central site are in different countries/regions.</span></span> <span data-ttu-id="25b0b-123">基於相容性與法規考量，每個國家/地區至少要有一個 SIP 主幹。</span><span class="sxs-lookup"><span data-stu-id="25b0b-123">For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span> <span data-ttu-id="25b0b-124">以歐盟地區為例，若未在中心點上進行本機終止，通訊就只能侷限在國家/地區的範圍。</span><span class="sxs-lookup"><span data-stu-id="25b0b-124">For example, in the European Union, communications cannot leave a country/region without terminating locally at a centralized point.</span></span>

<span data-ttu-id="25b0b-125">根據網站的地理位置和您在企業中預期的流量，您可能不想要透過中央 SIP 主幹路由傳送所有使用者，或者您可以選擇透過分支網站的 SIP 主幹路由傳送部分使用者。</span><span class="sxs-lookup"><span data-stu-id="25b0b-125">Depending on the geographical location of sites and how much traffic you anticipate within your enterprise, you may not want to route all users through the central SIP trunk, or you may opt to route some users through a SIP trunk at their branch site.</span></span> <span data-ttu-id="25b0b-126">若要分析自身需求，請回答下列問題：</span><span class="sxs-lookup"><span data-stu-id="25b0b-126">To analyze your needs, answer the following questions:</span></span>

  - <span data-ttu-id="25b0b-127">每個網站有多大 (，也就是有多少使用者已啟用企業語音) ？</span><span class="sxs-lookup"><span data-stu-id="25b0b-127">How big is each site (that is, how many users are enabled for Enterprise Voice)?</span></span>

  - <span data-ttu-id="25b0b-128">各網站上的哪些直接向內撥號 (DID) 號碼來電數最多？</span><span class="sxs-lookup"><span data-stu-id="25b0b-128">Which direct inward dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="25b0b-129">在考量應部署集中式或分散式 SIP 主幹時，必須進行成本效益分析。</span><span class="sxs-lookup"><span data-stu-id="25b0b-129">The decision whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis.</span></span> <span data-ttu-id="25b0b-130">在某些情況下，即便並非必要，選擇分散式部署模型可能較有利。</span><span class="sxs-lookup"><span data-stu-id="25b0b-130">In some cases, it may be advantageous to opt for the distributed deployment model even if it is not required.</span></span> <span data-ttu-id="25b0b-131">在完整的集中式部署中，所有分支網站流量都透過 WAN 連結路由傳送。</span><span class="sxs-lookup"><span data-stu-id="25b0b-131">In a completely centralized deployment, all branch site traffic is routed over WAN links.</span></span> <span data-ttu-id="25b0b-132">與其為 WAN 連結所需的頻寬支付高額費用，您可能寧可使用分散式 SIP 主幹。</span><span class="sxs-lookup"><span data-stu-id="25b0b-132">Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span> <span data-ttu-id="25b0b-133">例如，您可能想要在具有同盟的中央網站的分支網站上部署 Standard Edition server，或使用小型閘道部署 Survivable Branch 裝置或 Survivable Branch Server。</span><span class="sxs-lookup"><span data-stu-id="25b0b-133">For example, you may want to deploy a Standard Edition server at a branch site with federation to the central site, or you may want to deploy a Survivable Branch Appliance or a Survivable Branch Server with a small gateway.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="25b0b-134">如需有關分散式 SIP trunk 的詳細資訊，請參閱<A href="lync-server-2013-branch-site-sip-trunking.md">Lync Server 2013 中的分支網站 SIP</A>主幹。</span><span class="sxs-lookup"><span data-stu-id="25b0b-134">For details about distributed SIP trunking, see <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="25b0b-135">支援的 SIP 主幹連線類型</span><span class="sxs-lookup"><span data-stu-id="25b0b-135">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="25b0b-136">Lync Server 支援 SIP 主幹的下列連線類型：</span><span class="sxs-lookup"><span data-stu-id="25b0b-136">Lync Server supports the following connection types for SIP trunking:</span></span>

  - <span data-ttu-id="25b0b-p109">Multiprotocol Label Switching (MPLS) 是可將資料從一個網路節點導向及承載到另一個網路節點的私人網路。MPLS 網路的頻寬會與其他訂戶共用，並且會為每個資料封包指派一個標籤，用以區別不同訂戶的資料。此連線類型不需要虛擬私人網路 (VPN)。可能的缺點是，過多的 IP 流量可能會干擾 VoIP 作業，除非 VoIP 流量享有優先權。</span><span class="sxs-lookup"><span data-stu-id="25b0b-p109">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next. The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber’s data from another’s. This connection type does not require a virtual private network (VPN). A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

  - <span data-ttu-id="25b0b-p110">不含其他流量的私人連線 (例如租用的光纖連線或 T1 線路) 通常會是最可靠而安全的連線類型。此連線類型可提供最高的通話承載能力，但通常也最昂貴。此連線類型不需要 VPN。私人連線適用於通話量大或安全性與可用性需求很高的組織。</span><span class="sxs-lookup"><span data-stu-id="25b0b-p110">A private connection with no other traffic—for example, a leased fiber-optic connection or T1 line—is typically the most reliable and secure connection type. This connection type provides the highest call-carrying capacity, but it is typically the most expensive. VPN is not required. Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

  - <span data-ttu-id="25b0b-145">網際網路是最經濟的連線類型，但可靠性也最低。</span><span class="sxs-lookup"><span data-stu-id="25b0b-145">The Internet is the least expensive connection type, but it is also the least reliable.</span></span> <span data-ttu-id="25b0b-146">Internet connection 是唯一需要 VPN 的 Lync Server SIP 主幹連線類型。</span><span class="sxs-lookup"><span data-stu-id="25b0b-146">Internet connection is the only Lync Server SIP trunking connection type that requires VPN.</span></span>

<div>

## <a name="selecting-a-connection-type"></a><span data-ttu-id="25b0b-147">選取連線類型</span><span class="sxs-lookup"><span data-stu-id="25b0b-147">Selecting a Connection Type</span></span>

<span data-ttu-id="25b0b-148">您的企業最適合使用的 SIP 主幹連線類型，端視您的需求與預算而定。</span><span class="sxs-lookup"><span data-stu-id="25b0b-148">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

  - <span data-ttu-id="25b0b-p112">對中型或較大的企業而言，MPLS 網路通常能提供最大的效益。它可以低於特殊私人網路的費率提供所需的頻寬。</span><span class="sxs-lookup"><span data-stu-id="25b0b-p112">For a mid-size or larger enterprise, an MPLS network usually provides the greatest value. It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

  - <span data-ttu-id="25b0b-151">大型企業可能需要私人光纖連線、T1、T3 或更高階的連線 (歐盟地區為 E1、E3 或更高階連線)。</span><span class="sxs-lookup"><span data-stu-id="25b0b-151">Large enterprises may require a private fiber-optic, T1, T3 or higher connection (E1, E3 or higher in the European Union).</span></span>

  - <span data-ttu-id="25b0b-152">對於具有低通話數量的小型企業或分支網站，透過網際網路的 SIP 主幹可能是最佳選擇。</span><span class="sxs-lookup"><span data-stu-id="25b0b-152">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice.</span></span> <span data-ttu-id="25b0b-153">不建議中型或較大的網站使用此連線類型。</span><span class="sxs-lookup"><span data-stu-id="25b0b-153">This connection type is not recommended for mid-size or larger sites.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-requirements"></a><span data-ttu-id="25b0b-154">頻寬需求</span><span class="sxs-lookup"><span data-stu-id="25b0b-154">Bandwidth Requirements</span></span>

<span data-ttu-id="25b0b-p114">您的實作所需的頻寬量，取決於您的話務量 (您必須能夠支援的並行通話數量)。您必須將頻寬可用性納入考量，以充分使用您花錢購買的最大容量。您可以使用下列公式計算 SIP 主幹的最大頻寬需求：</span><span class="sxs-lookup"><span data-stu-id="25b0b-p114">The amount of bandwidth your implementation requires depends on call capacity (the number of concurrent calls you must be able to support). You need to consider bandwidth availability, so that you can take full advantage of the peak capacity that you have paid for. Use the following formula to calculate SIP trunk peak bandwidth requirement:</span></span>

<span data-ttu-id="25b0b-158">SIP 主幹最大頻寬 = 同時通話數上限 x (64 kbps + 標頭大小)</span><span class="sxs-lookup"><span data-stu-id="25b0b-158">SIP Trunk Peak Bandwidth = Max Simultaneous Calls x (64 kbps + header size)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="25b0b-159">標頭大小上限為 20 個位元組。</span><span class="sxs-lookup"><span data-stu-id="25b0b-159">Header size is 20 bytes maximum.</span></span>



</div>

</div>

<div>

## <a name="codec-support"></a><span data-ttu-id="25b0b-160">轉碼器支援</span><span class="sxs-lookup"><span data-stu-id="25b0b-160">Codec Support</span></span>

<span data-ttu-id="25b0b-161">Lync Server 2013 僅支援下列編解碼器：</span><span class="sxs-lookup"><span data-stu-id="25b0b-161">Lync Server 2013 supports only the following codecs:</span></span>

  - <span data-ttu-id="25b0b-162">G.711 a-law (主要使用於北美以外的地區)</span><span class="sxs-lookup"><span data-stu-id="25b0b-162">G.711 a-law (used primarily outside North America)</span></span>

  - <span data-ttu-id="25b0b-163">G.711 µ-law (使用於北美地區)</span><span class="sxs-lookup"><span data-stu-id="25b0b-163">G.711 µ-law (used in North America)</span></span>

</div>

<div>

## <a name="internet-telephony-service-provider"></a><span data-ttu-id="25b0b-164">網際網路電話語音服務提供者</span><span class="sxs-lookup"><span data-stu-id="25b0b-164">Internet Telephony Service Provider</span></span>

<span data-ttu-id="25b0b-165">SIP 主幹連線之服務提供者端的實作方式，會根據 ITSP 而不同。</span><span class="sxs-lookup"><span data-stu-id="25b0b-165">How you implement the service provider side of a SIP trunk connection varies from one ITSP to another.</span></span> <span data-ttu-id="25b0b-166">如需部署資訊，請連絡服務提供者。</span><span class="sxs-lookup"><span data-stu-id="25b0b-166">For deployment information, contact your service provider.</span></span> <span data-ttu-id="25b0b-167">如需認證 SIP 主幹服務提供者的清單，請參閱[Microsoft 整合通訊開啟互通性計畫網站](https://go.microsoft.com/fwlink/?linkid=287029)。</span><span class="sxs-lookup"><span data-stu-id="25b0b-167">For a list of certified SIP trunking service providers, see [Microsoft Unified Communications Open Interoperability Program website](https://go.microsoft.com/fwlink/?linkid=287029).</span></span>

<span data-ttu-id="25b0b-168">如需 Microsoft 認證 SIP 主幹提供者的詳細資訊，請連絡 Microsoft 代表。</span><span class="sxs-lookup"><span data-stu-id="25b0b-168">For details about Microsoft certified SIP trunking providers, contact your Microsoft representative.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="25b0b-p116">您必須使用 Microsoft 認證服務提供者，以確定 ITSP 支援所有周遊 SIP 主幹的功能 (例如，設定和管理工作階段，以及支援所有延伸的 VoIP 服務)。Microsoft 技術支援未延伸至使用非認證提供者的設定。如果您目前使用未獲得 SIP 主幹認證的網際網路服務提供者，則可以選擇繼續使用該提供者做為 ISP，並使用 Microsoft 認證的提供者進行 SIP 主幹作業。</span><span class="sxs-lookup"><span data-stu-id="25b0b-p116">You must use a Microsoft certified service provider to ensure that your ITSP supports all of the functionality that traverses the SIP trunk (for example, setting up and managing sessions and supporting all of the extended VoIP services). Microsoft technical support does not extend to configurations that use noncertified providers. If you currently use an Internet service provider that is not certified for SIP trunking, you can opt to continue using that provider as your ISP and use a provider certified by Microsoft for SIP trunking.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

