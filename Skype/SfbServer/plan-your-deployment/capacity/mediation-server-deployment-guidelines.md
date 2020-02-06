---
title: 商務用 Skype Server 中的中繼伺服器部署指導方針
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
ms.collection: IT_Skype16
ms.assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
description: 本主題描述有關轉送伺服器部署的規劃指導方針。
ms.openlocfilehash: 806886b7c7c5e8ae367a6e104f7fd9127f25c099
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816052"
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server"></a><span data-ttu-id="e3c5d-103">商務用 Skype Server 中的中繼伺服器部署指導方針</span><span class="sxs-lookup"><span data-stu-id="e3c5d-103">Deployment guidelines for Mediation Server in Skype for Business Server</span></span>
 
<span data-ttu-id="e3c5d-104">本主題描述有關轉送伺服器部署的規劃指導方針。</span><span class="sxs-lookup"><span data-stu-id="e3c5d-104">This topic describes planning guidelines for Mediation Server deployment.</span></span>
  
## <a name="collocated-or-stand-alone-mediation-server"></a><span data-ttu-id="e3c5d-105">Collocated 或獨立的中繼伺服器？</span><span class="sxs-lookup"><span data-stu-id="e3c5d-105">Collocated or Stand-alone Mediation Server?</span></span>

<span data-ttu-id="e3c5d-106">在預設情況下，中繼伺服器是在中央網站的 [標準版] 伺服器或 [前端] 池中的 [標準版] 伺服器或 [前端伺服器] 上 collocated。</span><span class="sxs-lookup"><span data-stu-id="e3c5d-106">Mediation Server is, by default, collocated on the Standard Edition server or Front End Server in a Front End pool at central sites.</span></span> <span data-ttu-id="e3c5d-107">可處理的公用交換電話網絡（PSTN）通話數目，以及池中所需的電腦數將取決於：</span><span class="sxs-lookup"><span data-stu-id="e3c5d-107">The number of public switched telephone network (PSTN) calls that can be handled and the number of machines required in the pool will depend on:</span></span>
  
- <span data-ttu-id="e3c5d-108">中繼伺服器池控制的閘道對等數目。</span><span class="sxs-lookup"><span data-stu-id="e3c5d-108">The number of gateway peers that the Mediation Server pool controls.</span></span>
    
- <span data-ttu-id="e3c5d-109">高容量流量穿過這些閘道。</span><span class="sxs-lookup"><span data-stu-id="e3c5d-109">The high-volume traffic periods through those gateways.</span></span>
    
- <span data-ttu-id="e3c5d-110">呼叫其媒體略過中繼伺服器的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="e3c5d-110">The percentage of calls that are calls whose media bypass the Mediation Server.</span></span>
    
<span data-ttu-id="e3c5d-111">規劃時，請務必考慮 PSTN 通話的媒體處理需求，以及不支援媒體旁路的 A/V 會議，以及處理需要支援之繁忙時間呼叫的信號互動所需的處理。</span><span class="sxs-lookup"><span data-stu-id="e3c5d-111">When you're planning, be sure to take into account the media processing requirements for PSTN calls and A/V conferences that don't support media bypass, as well as the processing needed to handle signaling interactions for the number of busy-hour calls that need to be supported.</span></span> <span data-ttu-id="e3c5d-112">如果您沒有足夠的 CPU，您必須部署一個獨立的中繼伺服器池。</span><span class="sxs-lookup"><span data-stu-id="e3c5d-112">If you don't have enough CPU, you'll need to deploy a stand-alone pool of Mediation Servers.</span></span> <span data-ttu-id="e3c5d-113">此外，PSTN 閘道、IP-Pbx 和 SBCs 將需要分割為由一個池中的 collocated 轉送伺服器所控制的子集，以及一個或多個獨立的池中的獨立轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="e3c5d-113">Additionally, PSTN gateways, IP-PBXs, and SBCs will need to be split into subsets that are controlled by the collocated Mediation Servers in one pool and the stand-alone Mediation Servers in one or more stand-alone pools.</span></span>
  
<span data-ttu-id="e3c5d-114">如果您已部署 PSTN 閘道、IP-Pbx 或會話邊界控制器（SBCs），但缺乏與中繼伺服器池互動的能力，就必須將它們與單一轉送伺服器所組成的獨立池建立關聯。</span><span class="sxs-lookup"><span data-stu-id="e3c5d-114">If you deployed PSTN gateways, IP-PBXs, or Session Border Controllers (SBCs) that lack the ability to interact with a pool of Mediation Servers, they'll need to be associated with a stand-alone pool consisting of a single Mediation Server.</span></span> <span data-ttu-id="e3c5d-115">您的 PSTN 閘道、IP-Pbx 或 SBCs 需要做的一些事包括：</span><span class="sxs-lookup"><span data-stu-id="e3c5d-115">Some of the things your PSTN gateways, IP-PBXs or SBCs would need to do include:</span></span>
  
- <span data-ttu-id="e3c5d-116">在池中的中繼伺服器上執行網狀圖層網域名稱系統（DNS）負載平衡（或將流量均勻地路由到池中的所有中繼伺服器）。</span><span class="sxs-lookup"><span data-stu-id="e3c5d-116">Perform network layer Domain Name System (DNS) load balancing across Mediation Servers in a pool (or otherwise route traffic uniformly to all Mediation Servers in a pool).</span></span>
    
- <span data-ttu-id="e3c5d-117">接受來自池中任何中繼伺服器的流量。</span><span class="sxs-lookup"><span data-stu-id="e3c5d-117">Accept traffic from any Mediation Server in a pool.</span></span>
    
<span data-ttu-id="e3c5d-118">您可以使用商務用 Skype 規劃工具來評估 collocating 的中繼伺服器與您的前端池是否可以處理負載。</span><span class="sxs-lookup"><span data-stu-id="e3c5d-118">You can use the Skype for Business Planning Tool to evaluate whether collocating the Mediation Server with your Front End pool can handle the load.</span></span> <span data-ttu-id="e3c5d-119">如果您的環境無法滿足這些需求，則您必須部署獨立的中繼伺服器池。</span><span class="sxs-lookup"><span data-stu-id="e3c5d-119">If your environment can't meet these requirements, then you'll need to deploy a stand-alone Mediation Server pool.</span></span>
  
## <a name="central-site-and-branch-site-considerations"></a><span data-ttu-id="e3c5d-120">中心網站與分支網站考慮</span><span class="sxs-lookup"><span data-stu-id="e3c5d-120">Central Site and Branch Site Considerations</span></span>

 <span data-ttu-id="e3c5d-121">中央網站上的中繼伺服器可用於傳送分支網站上 IP-Pbx 或 PSTN 閘道的呼叫。</span><span class="sxs-lookup"><span data-stu-id="e3c5d-121">Mediation Servers at the central site can be used to route calls for IP-PBXs or PSTN gateways at branch sites.</span></span> <span data-ttu-id="e3c5d-122">不過，如果您要部署 SIP trunks，則必須在每個幹線終止的網站上部署一個轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="e3c5d-122">If you deploy SIP trunks, however, you have to deploy a Mediation Server at the site where each trunk terminates.</span></span> <span data-ttu-id="e3c5d-123">在分支網站上的 IP PBX 或 PSTN 閘道呼叫中央網站路由的中繼伺服器不需要使用媒體旁路，但建議使用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="e3c5d-123">Having a Mediation Server at the central site route calls for an IP-PBX or PSTN gateway at a branch site doesn't require the use of media bypass, but a media bypass is recommended.</span></span> <span data-ttu-id="e3c5d-124">這是因為，如果您可以啟用媒體旁路，它會減少媒體路徑延遲，因此，因為媒體路徑不需要追蹤信號路徑，因此會改善媒體質量。</span><span class="sxs-lookup"><span data-stu-id="e3c5d-124">That's because, if you can enable media bypass, it'll reduce media path latency and, consequently, result in improved media quality because the media path isn't required to follow the signaling path.</span></span> <span data-ttu-id="e3c5d-125">[媒體旁路] 也會減少池中的處理負載。</span><span class="sxs-lookup"><span data-stu-id="e3c5d-125">Media bypass will also decrease the processing load on the pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e3c5d-126">媒體旁路無法與每個 PSTN 閘道、IP PBX 和 SBC 進行交互操作。</span><span class="sxs-lookup"><span data-stu-id="e3c5d-126">Media bypass won't interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="e3c5d-127">Microsoft 已經測試了一組 PSTN 閘道，並有已認證的合作夥伴，且已使用 Cisco IP-Pbx 進行了一些測試。</span><span class="sxs-lookup"><span data-stu-id="e3c5d-127">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="e3c5d-128">只有在整合通訊開啟互通性計畫中列出的產品與版本，才支援媒體旁路[，請參閱探索已測試的裝置、基礎結構，以及支援及擴充商務用 Skype 體驗的工具](http://partnersolutions.skypeforbusiness.com/solutionscatalog)。</span><span class="sxs-lookup"><span data-stu-id="e3c5d-128">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program - Lync Server at [Explore tested devices, infrastructure, and tools that support and extend your Skype for Business experience](http://partnersolutions.skypeforbusiness.com/solutionscatalog).</span></span> 
  
<span data-ttu-id="e3c5d-129">如果需要分支網站復原功能，Survivable 分支裝置或前端伺服器、中繼伺服器和閘道的組合必須部署在分支網站上。</span><span class="sxs-lookup"><span data-stu-id="e3c5d-129">If branch site resiliency is required, a Survivable Branch Appliance or combination of a Front End Server, a Mediation Server, and a gateway must be deployed at the branch site.</span></span> <span data-ttu-id="e3c5d-130">（分支網站復原的假設是，目前狀態與會議不會在網站上復原。）如需有關分支網站規劃語音的指導方針，請參閱[商務用 Skype Server 中的企業語音復原方案](../enterprise-voice-solution/enterprise-voice-resiliency.md)。</span><span class="sxs-lookup"><span data-stu-id="e3c5d-130">(The assumption with branch site resiliency is that presence and conferencing are not resilient at the site.) For guidance on branch site planning for voice, see [Plan for Enterprise Voice resiliency in Skype for Business Server](../enterprise-voice-solution/enterprise-voice-resiliency.md).</span></span>
  
<span data-ttu-id="e3c5d-131">針對 IP PBX 的互動，如果 IP PBX 無法正確支援使用多個前期對話方塊與 RFC 3960 互動的早期媒體互動，就可以將從 IP PBX 撥入通話的前幾個字剪切到 Lync 端點。</span><span class="sxs-lookup"><span data-stu-id="e3c5d-131">For interactions with an IP-PBX, if the IP-PBX does not correctly support early media interactions with multiple early dialogs and RFC 3960 interactions, there can be clipping of the first few words of the greeting for incoming calls from the IP-PBX to Lync endpoints.</span></span> <span data-ttu-id="e3c5d-132">如果中央站台的中繼伺服器是路由在分支網站中斷的 IP PBX 路由呼叫，這種行為可能會較嚴重，因為需要更多的時間來完成通知。</span><span class="sxs-lookup"><span data-stu-id="e3c5d-132">This behavior can be more severe if a Mediation Server at a central site is routing calls for an IP-PBX where the route terminates at a branch site, because more time is needed for signaling to complete.</span></span> <span data-ttu-id="e3c5d-133">如果您遇到這種情況，請在分支網站上部署中繼伺服器，這是減少前幾個字的剪輯的唯一方法。</span><span class="sxs-lookup"><span data-stu-id="e3c5d-133">If you experience this behavior, deploying a Mediation Server at the branch site is the only way to reduce clipping of the first few words.</span></span>
  
<span data-ttu-id="e3c5d-134">最後，如果您的中央網站有 TDM PBX，或者您的 IP PBX 不會消除 PSTN 閘道的需求，則您必須在連線轉送伺服器和 PBX 的呼叫路由中部署閘道。</span><span class="sxs-lookup"><span data-stu-id="e3c5d-134">Finally, if your central site has a TDM PBX, or if your IP-PBX does not eliminate the need for a PSTN gateway, then you must deploy a gateway on the call route connecting Mediation Server and the PBX.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e3c5d-135">若要改善獨立轉送伺服器的媒體效能，您應該在這些伺服器的網路介面卡上啟用接收端縮放（RSS）。</span><span class="sxs-lookup"><span data-stu-id="e3c5d-135">To improve the media performance of standalone Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on these servers.</span></span> <span data-ttu-id="e3c5d-136">RSS 可讓伺服器上的多個處理常式並行處理傳入的資料包。</span><span class="sxs-lookup"><span data-stu-id="e3c5d-136">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="e3c5d-137">如需詳細資訊，請參閱「[Windows Server 中的接收端縮放增強功能](https://go.microsoft.com/fwlink/p/?LinkId=268731)」。</span><span class="sxs-lookup"><span data-stu-id="e3c5d-137">For details, see "[Receive-Side Scaling Enhancements in Windows Server](https://go.microsoft.com/fwlink/p/?LinkId=268731)".</span></span> <span data-ttu-id="e3c5d-138">如需有關如何啟用 RSS 的詳細資訊，請參閱您的網路介面卡檔。</span><span class="sxs-lookup"><span data-stu-id="e3c5d-138">For details about how to enable RSS, see your network adapter documentation.</span></span> 
  

