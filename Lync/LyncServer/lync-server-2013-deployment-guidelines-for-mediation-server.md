---
title: Lync Server 2013：中繼伺服器的部署指南
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment guidelines for Mediation Server
ms:assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398622(v=OCS.15)
ms:contentKeyID: 48184606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 400f8cceeb86d407297b3f564c01266a477ca0ef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977164"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="cf552-102">Lync Server 2013 中的中繼伺服器部署指導方針</span><span class="sxs-lookup"><span data-stu-id="cf552-102">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf552-103">_**主題上次修改日期：** 2012-10-12_</span><span class="sxs-lookup"><span data-stu-id="cf552-103">_**Topic Last Modified:** 2012-10-12_</span></span>

<span data-ttu-id="cf552-104">本主題描述有關轉送伺服器部署的規劃指導方針。</span><span class="sxs-lookup"><span data-stu-id="cf552-104">This topic describes planning guidelines for Mediation Server deployment.</span></span> <span data-ttu-id="cf552-105">複習這些指導方針之後，我們建議您使用規劃工具來建立及查看可能的替代拓撲，這可以作為模型，讓您決定要部署的最終量身定制拓朴看起來像這樣。</span><span class="sxs-lookup"><span data-stu-id="cf552-105">After reviewing these guidelines, we recommend that you use the Planning Tool to create and view possible alternative topologies, which can serve as models for what the final tailored topology that you decide to deploy would look like.</span></span>

<div>

## <a name="collocated-or-stand-alone-mediation-server"></a><span data-ttu-id="cf552-106">Collocated 或獨立的中繼伺服器？</span><span class="sxs-lookup"><span data-stu-id="cf552-106">Collocated or Stand-alone Mediation Server?</span></span>

<span data-ttu-id="cf552-107">在 [中央網站] 的 [標準版] 伺服器或 [前端伺服器] 中，[中繼伺服器] 是預設的 collocated。</span><span class="sxs-lookup"><span data-stu-id="cf552-107">Mediation Server is by default collocated on the Standard Edition server or Front End Server in a Front End pool at central sites.</span></span> <span data-ttu-id="cf552-108">可處理的公用交換電話網絡（PSTN）通話數目，以及池中所需的電腦數將視下列專案而定：</span><span class="sxs-lookup"><span data-stu-id="cf552-108">The number of public switched telephone network (PSTN) calls that can be handled and the number of machines required in the pool will depend on the following:</span></span>

  - <span data-ttu-id="cf552-109">中繼伺服器池控制的閘道對等數目</span><span class="sxs-lookup"><span data-stu-id="cf552-109">The number of gateway peers that the Mediation Server pool controls</span></span>

  - <span data-ttu-id="cf552-110">透過這些閘道的高容量流量</span><span class="sxs-lookup"><span data-stu-id="cf552-110">The high-volume traffic periods through those gateways</span></span>

  - <span data-ttu-id="cf552-111">媒體略過中繼伺服器的呼叫百分比</span><span class="sxs-lookup"><span data-stu-id="cf552-111">The percentage of calls that are calls whose media bypass the Mediation Server</span></span>

<span data-ttu-id="cf552-112">規劃時，請務必考慮進行 PSTN 通話的媒體處理需求，以及未針對媒體旁路設定的 A/V 會議，以及處理需要支援之繁忙時間呼叫的信號互動所需的處理。</span><span class="sxs-lookup"><span data-stu-id="cf552-112">When planning, be sure to take into account the media processing requirements for PSTN calls and A/V conferences that are not configured for media bypass, as well as the processing needed to handle signaling interactions for the number of busy-hour calls that need to be supported.</span></span> <span data-ttu-id="cf552-113">如果沒有足夠的 CPU，您必須部署一個獨立的中繼伺服器池;而且 PSTN 閘道、IP Pbx 和 SBCs 將需要分割成多個子集，這些子集是由一個池中的 collocated 轉送伺服器和一或多個獨立的池中的獨立轉送伺服器所控制。</span><span class="sxs-lookup"><span data-stu-id="cf552-113">If there is not enough CPU, then you must deploy a stand-alone pool of Mediation Servers; and PSTN gateways, IP-PBXs, and SBCs will need to be split into subsets that are controlled by the collocated Mediation Servers in one pool and the stand-alone Mediation Servers in one or more stand-alone pools.</span></span>

<span data-ttu-id="cf552-114">如果您已部署 PSTN 閘道、IP-Pbx 或會話邊界控制器（SBCs），且不支援與中繼伺服器池進行互動的正確功能，包括下列各項，則必須將它們與獨立的池中組成在單一中繼伺服器上：</span><span class="sxs-lookup"><span data-stu-id="cf552-114">If you deployed PSTN gateways, IP-PBXs, or Session Border Controllers (SBCs) that do not support the correct capabilities to interact with a pool of Mediation Servers, including the following, then they will need to be associated with a stand-alone pool consisting of a single Mediation Server:</span></span>

  - <span data-ttu-id="cf552-115">在池中的中繼伺服器上執行網狀圖層網域名稱系統（DNS）負載平衡（或將流量均勻地路由到池中的所有中繼伺服器）</span><span class="sxs-lookup"><span data-stu-id="cf552-115">Perform network layer Domain Name System (DNS) load balancing across Mediation Servers in a pool (or otherwise route traffic uniformly to all Mediation Servers in a pool)</span></span>

  - <span data-ttu-id="cf552-116">接受來自池中任何中繼伺服器的流量</span><span class="sxs-lookup"><span data-stu-id="cf552-116">Accept traffic from any Mediation Server in a pool</span></span>

<span data-ttu-id="cf552-117">您可以使用 Microsoft Lync Server 2013、規劃工具來評估 collocating 的中繼伺服器與您的前端池是否可以處理負載。</span><span class="sxs-lookup"><span data-stu-id="cf552-117">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether collocating the Mediation Server with your Front End pool can handle the load.</span></span> <span data-ttu-id="cf552-118">如果您的環境無法符合這些需求，則您必須部署獨立的中繼伺服器池。</span><span class="sxs-lookup"><span data-stu-id="cf552-118">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

</div>

<div>

## <a name="central-site-and-branch-site-considerations"></a><span data-ttu-id="cf552-119">中心網站與分支網站考慮</span><span class="sxs-lookup"><span data-stu-id="cf552-119">Central Site and Branch Site Considerations</span></span>

<span data-ttu-id="cf552-120">中央網站上的中繼伺服器可用於傳送分支網站上 IP-Pbx 或 PSTN 閘道的呼叫。</span><span class="sxs-lookup"><span data-stu-id="cf552-120">Mediation Servers at the central site can be used to route calls for IP-PBXs or PSTN gateways at branch sites.</span></span> <span data-ttu-id="cf552-121">不過，如果您要部署 SIP trunks，您必須在每個幹線終止的網站上部署一個轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="cf552-121">If you deploy SIP trunks, however, you must deploy a Mediation Server at the site where each trunk terminates.</span></span> <span data-ttu-id="cf552-122">在分支網站上，針對 IP PBX 或 PSTN 閘道呼叫中央網站路由的中繼伺服器，不需要使用 [媒體旁路]。</span><span class="sxs-lookup"><span data-stu-id="cf552-122">Having a Mediation Server at the central site route calls for an IP-PBX or PSTN gateway at a branch site does not require the use of media bypass.</span></span> <span data-ttu-id="cf552-123">不過，如果您可以啟用媒體旁路，這麼做會減少媒體路徑延遲，因此，因為媒體路徑已不再需要追蹤信號路徑，因此可改善媒體質量。</span><span class="sxs-lookup"><span data-stu-id="cf552-123">However, if you can enable media bypass, doing so will reduce media path latency and, consequently, result in improved media quality because the media path is no longer required to follow the signaling path.</span></span> <span data-ttu-id="cf552-124">[媒體旁路] 也會減少池中的處理負載。</span><span class="sxs-lookup"><span data-stu-id="cf552-124">Media bypass will also decrease the processing load on the pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cf552-125">媒體旁路將無法與每個 PSTN 閘道、IP PBX 和 SBC 進行交互操作。</span><span class="sxs-lookup"><span data-stu-id="cf552-125">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="cf552-126">Microsoft 已經測試了一組 PSTN 閘道，並有已認證的合作夥伴，且已使用 Cisco IP-Pbx 進行了一些測試。</span><span class="sxs-lookup"><span data-stu-id="cf552-126">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="cf552-127">只有在整合通訊開啟互通性計畫（Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=268730">http://go.microsoft.com/fwlink/p/?LinkId=268730</A>）中所列的產品和版本，才能支援媒體略過。</span><span class="sxs-lookup"><span data-stu-id="cf552-127">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=268730">http://go.microsoft.com/fwlink/p/?LinkId=268730</A>.</span></span>



</div>

<span data-ttu-id="cf552-128">如果需要分支網站復原功能，Survivable 分支裝置或前端伺服器、中繼伺服器和閘道的組合必須部署在分支網站上。</span><span class="sxs-lookup"><span data-stu-id="cf552-128">If branch site resiliency is required, a Survivable Branch Appliance or combination of a Front End Server, a Mediation Server, and a gateway must be deployed at the branch site.</span></span> <span data-ttu-id="cf552-129">（分支網站復原的假設是，目前狀態與會議不會在網站上復原。）如需有關分支網站規劃語音的指導方針，請參閱[Lync Server 2013 中的分支網站語音復原規劃](lync-server-2013-planning-for-branch-site-voice-resiliency.md)。</span><span class="sxs-lookup"><span data-stu-id="cf552-129">(The assumption with branch site resiliency is that presence and conferencing are not resilient at the site.) For guidance on branch site planning for voice, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span></span>

<span data-ttu-id="cf552-130">針對 IP PBX 的互動，如果 IP PBX 無法正確支援使用多個前期對話方塊與 RFC 3960 互動的早期媒體互動，就可以將從 IP PBX 撥入通話的前幾個字剪切到 Lync 端點。</span><span class="sxs-lookup"><span data-stu-id="cf552-130">For interactions with an IP-PBX, if the IP-PBX does not correctly support early media interactions with multiple early dialogs and RFC 3960 interactions, there can be clipping of the first few words of the greeting for incoming calls from the IP-PBX to Lync endpoints.</span></span> <span data-ttu-id="cf552-131">如果中央站台的中繼伺服器是路由在分支網站中斷的 IP PBX 路由呼叫，這種行為可能會較嚴重，因為需要更多的時間來完成通知。</span><span class="sxs-lookup"><span data-stu-id="cf552-131">This behavior can be more severe if a Mediation Server at a central site is routing calls for an IP-PBX where the route terminates at a branch site, because more time is needed for signaling to complete.</span></span> <span data-ttu-id="cf552-132">如果您遇到這種情況，請在分支網站上部署中繼伺服器，這是減少前幾個字的剪輯的唯一方法。</span><span class="sxs-lookup"><span data-stu-id="cf552-132">If you experience this behavior, deploying a Mediation Server at the branch site is the only way to reduce clipping of the first few words.</span></span>

<span data-ttu-id="cf552-133">最後，如果您的中央網站有 TDM PBX，或者您的 IP PBX 不會消除 PSTN 閘道的需求，則您必須在連線轉送伺服器和 PBX 的呼叫路由中部署閘道。</span><span class="sxs-lookup"><span data-stu-id="cf552-133">Finally, if your central site has a TDM PBX, or if your IP-PBX does not eliminate the need for a PSTN gateway, then you must deploy a gateway on the call route connecting Mediation Server and the PBX.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cf552-134">若要改善獨立轉送伺服器的媒體效能，您應該在這些伺服器的網路介面卡上啟用接收端縮放（RSS）。</span><span class="sxs-lookup"><span data-stu-id="cf552-134">To improve the media performance of standalone Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on these servers.</span></span> <span data-ttu-id="cf552-135">RSS 可讓伺服器上的多個處理常式並行處理傳入的資料包。</span><span class="sxs-lookup"><span data-stu-id="cf552-135">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="cf552-136">如需詳細資訊，請參閱 Windows Server 中的 [接收端縮放<A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?LinkId=268731</A>增強功能]。</span><span class="sxs-lookup"><span data-stu-id="cf552-136">For details, see "Receive-Side Scaling Enhancements in Windows Server" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?LinkId=268731</A>.</span></span> <span data-ttu-id="cf552-137">如需有關如何啟用 RSS 的詳細資訊，請參閱您的網路介面卡檔。</span><span class="sxs-lookup"><span data-stu-id="cf552-137">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

