---
title: 商務用 Skype Server 中轉送伺服器的部署指導方針
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
ms.collection: IT_Skype16
ms.assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
description: 本主題說明轉送伺服器部署的規劃指導方針。
ms.openlocfilehash: ffb60abaf3027541f13fe73294eafda51e5d1d0f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118532"
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server"></a><span data-ttu-id="c2e80-103">商務用 Skype Server 中轉送伺服器的部署指導方針</span><span class="sxs-lookup"><span data-stu-id="c2e80-103">Deployment guidelines for Mediation Server in Skype for Business Server</span></span>
 
<span data-ttu-id="c2e80-104">本主題說明轉送伺服器部署的規劃指導方針。</span><span class="sxs-lookup"><span data-stu-id="c2e80-104">This topic describes planning guidelines for Mediation Server deployment.</span></span>
  
## <a name="collocated-or-stand-alone-mediation-server"></a><span data-ttu-id="c2e80-105">組合或獨立轉送伺服器？</span><span class="sxs-lookup"><span data-stu-id="c2e80-105">Collocated or Stand-alone Mediation Server?</span></span>

<span data-ttu-id="c2e80-106">根據預設，轉送伺服器是組合在 Standard Edition server 或前端伺服器上，位於中央網站的前端集區中。</span><span class="sxs-lookup"><span data-stu-id="c2e80-106">Mediation Server is, by default, collocated on the Standard Edition server or Front End Server in a Front End pool at central sites.</span></span> <span data-ttu-id="c2e80-107">可以處理之公用交換電話網路 (PSTN) 通話的數目，以及集區中所需的機器數目會取決於下列專案：</span><span class="sxs-lookup"><span data-stu-id="c2e80-107">The number of public switched telephone network (PSTN) calls that can be handled and the number of machines required in the pool will depend on:</span></span>
  
- <span data-ttu-id="c2e80-108">轉送伺服器集區所控制的閘道對等數目。</span><span class="sxs-lookup"><span data-stu-id="c2e80-108">The number of gateway peers that the Mediation Server pool controls.</span></span>
    
- <span data-ttu-id="c2e80-109">透過這些閘道的高磁片流量週期。</span><span class="sxs-lookup"><span data-stu-id="c2e80-109">The high-volume traffic periods through those gateways.</span></span>
    
- <span data-ttu-id="c2e80-110">媒體略過轉送伺服器之來電所占的百分比。</span><span class="sxs-lookup"><span data-stu-id="c2e80-110">The percentage of calls that are calls whose media bypass the Mediation Server.</span></span>
    
<span data-ttu-id="c2e80-111">當您進行規劃時，請務必考慮 PSTN 通話的媒體處理需求，以及不支援媒體旁路的 A/V 會議，以及處理需要支援之繁忙小時通話數目之信號互動的處理方式。</span><span class="sxs-lookup"><span data-stu-id="c2e80-111">When you're planning, be sure to take into account the media processing requirements for PSTN calls and A/V conferences that don't support media bypass, as well as the processing needed to handle signaling interactions for the number of busy-hour calls that need to be supported.</span></span> <span data-ttu-id="c2e80-112">如果您沒有足夠的 CPU，您必須部署一部獨立的轉送伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="c2e80-112">If you don't have enough CPU, you'll need to deploy a stand-alone pool of Mediation Servers.</span></span> <span data-ttu-id="c2e80-113">此外，PSTN 閘道、IP PBXs 和 SBCs 必須分割為由一個集區中的組合轉送伺服器，以及一或多個獨立集區中的獨立轉送伺服器所控制的子集。</span><span class="sxs-lookup"><span data-stu-id="c2e80-113">Additionally, PSTN gateways, IP-PBXs, and SBCs will need to be split into subsets that are controlled by the collocated Mediation Servers in one pool and the stand-alone Mediation Servers in one or more stand-alone pools.</span></span>
  
<span data-ttu-id="c2e80-114">如果您已部署 PSTN 閘道、IP PBXs 或會話邊界控制器 (SBCs) 與轉送伺服器集區互動，則必須與包含單一轉送伺服器集區的獨立集區相關聯。</span><span class="sxs-lookup"><span data-stu-id="c2e80-114">If you deployed PSTN gateways, IP-PBXs, or Session Border Controllers (SBCs) that lack the ability to interact with a pool of Mediation Servers, they'll need to be associated with a stand-alone pool consisting of a single Mediation Server.</span></span> <span data-ttu-id="c2e80-115">您的 PSTN 閘道、IP-PBXs 或 SBCs 需要做的部分事情包括：</span><span class="sxs-lookup"><span data-stu-id="c2e80-115">Some of the things your PSTN gateways, IP-PBXs or SBCs would need to do include:</span></span>
  
- <span data-ttu-id="c2e80-116">在集區中執行網路層網域名稱系統 (DNS) 負載平衡 (或將流量統一傳送至集區中的所有轉送伺服器) 。</span><span class="sxs-lookup"><span data-stu-id="c2e80-116">Perform network layer Domain Name System (DNS) load balancing across Mediation Servers in a pool (or otherwise route traffic uniformly to all Mediation Servers in a pool).</span></span>
    
- <span data-ttu-id="c2e80-117">接受來自集區中任何轉送伺服器的流量。</span><span class="sxs-lookup"><span data-stu-id="c2e80-117">Accept traffic from any Mediation Server in a pool.</span></span>
    
<span data-ttu-id="c2e80-118">您可以使用商務用 Skype 規劃工具評估組合您的前端集區的轉送伺服器是否可以處理該負載。</span><span class="sxs-lookup"><span data-stu-id="c2e80-118">You can use the Skype for Business Planning Tool to evaluate whether collocating the Mediation Server with your Front End pool can handle the load.</span></span> <span data-ttu-id="c2e80-119">如果您的環境無法符合這些需求，則您必須部署獨立的轉送伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="c2e80-119">If your environment can't meet these requirements, then you'll need to deploy a stand-alone Mediation Server pool.</span></span>
  
## <a name="central-site-and-branch-site-considerations"></a><span data-ttu-id="c2e80-120">中央網站與分支網站的考量事項</span><span class="sxs-lookup"><span data-stu-id="c2e80-120">Central Site and Branch Site Considerations</span></span>

 <span data-ttu-id="c2e80-121">中央網站上的中繼伺服器可用來路由分支網站上 IP-PBX 或 PSTN 閘道的電話。</span><span class="sxs-lookup"><span data-stu-id="c2e80-121">Mediation Servers at the central site can be used to route calls for IP-PBXs or PSTN gateways at branch sites.</span></span> <span data-ttu-id="c2e80-122">不過，如果您部署 SIP 主幹，您必須在每個主幹終止的網站上部署轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="c2e80-122">If you deploy SIP trunks, however, you have to deploy a Mediation Server at the site where each trunk terminates.</span></span> <span data-ttu-id="c2e80-123">在分支網站上的 IP-PBX 或 PSTN 閘道的中央網站路由呼叫轉送伺服器，不需要使用媒體旁路，但建議使用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="c2e80-123">Having a Mediation Server at the central site route calls for an IP-PBX or PSTN gateway at a branch site doesn't require the use of media bypass, but a media bypass is recommended.</span></span> <span data-ttu-id="c2e80-124">這是因為，如果您可以啟用媒體旁路，它會縮短媒體路徑延遲時間，因此，由於沒有必要使用媒體路徑來追蹤信號路徑，因此會改善媒體質量。</span><span class="sxs-lookup"><span data-stu-id="c2e80-124">That's because, if you can enable media bypass, it'll reduce media path latency and, consequently, result in improved media quality because the media path isn't required to follow the signaling path.</span></span> <span data-ttu-id="c2e80-125">媒體旁路也可減少集區上的處理負載。</span><span class="sxs-lookup"><span data-stu-id="c2e80-125">Media bypass will also decrease the processing load on the pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c2e80-126">媒體旁路不會與每個 PSTN 閘道、IP-PBX 及 SBC 互動。</span><span class="sxs-lookup"><span data-stu-id="c2e80-126">Media bypass won't interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="c2e80-127">Microsoft 已測試一組 PSTN 閘道，並與認證的協力廠商 SBCs，並利用 Cisco IP PBXs 進行一些測試。</span><span class="sxs-lookup"><span data-stu-id="c2e80-127">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="c2e80-128">媒體旁路只支援整合通訊開啟互通性計畫中所列的產品和版本。在 [探索已測試的裝置、基礎結構，以及支援和擴充商務用 Skype 體驗的工具](http://partnersolutions.skypeforbusiness.com/solutionscatalog)時，會支援 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="c2e80-128">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program - Lync Server at [Explore tested devices, infrastructure, and tools that support and extend your Skype for Business experience](http://partnersolutions.skypeforbusiness.com/solutionscatalog).</span></span> 
  
<span data-ttu-id="c2e80-129">如果需要分支網站恢復功能，則必須在分支網站上部署 Survivable 分支裝置或前端伺服器、轉送伺服器和閘道的組合。</span><span class="sxs-lookup"><span data-stu-id="c2e80-129">If branch site resiliency is required, a Survivable Branch Appliance or combination of a Front End Server, a Mediation Server, and a gateway must be deployed at the branch site.</span></span> <span data-ttu-id="c2e80-130"> (以分支網站恢復的設想，其目前狀態和會議不會在網站上復原。 ) 如需適用于通話的分支網站規劃指引，請參閱 [Plan For Enterprise voice 韌性 In 商務用 Skype Server](../enterprise-voice-solution/enterprise-voice-resiliency.md)。</span><span class="sxs-lookup"><span data-stu-id="c2e80-130">(The assumption with branch site resiliency is that presence and conferencing are not resilient at the site.) For guidance on branch site planning for voice, see [Plan for Enterprise Voice resiliency in Skype for Business Server](../enterprise-voice-solution/enterprise-voice-resiliency.md).</span></span>
  
<span data-ttu-id="c2e80-131">在與 IP-PBX 互動的情況下，如果 IP-PBX 無法正確支援與多個早期對話方塊和 RFC 3960 互動的早期媒體互動，則可以從 IP-PBX 至 Lync 端點的來電中，將問候語的前幾個字裁剪。</span><span class="sxs-lookup"><span data-stu-id="c2e80-131">For interactions with an IP-PBX, if the IP-PBX does not correctly support early media interactions with multiple early dialogs and RFC 3960 interactions, there can be clipping of the first few words of the greeting for incoming calls from the IP-PBX to Lync endpoints.</span></span> <span data-ttu-id="c2e80-132">如果中央網站上的中繼伺服器是為其整條路由是終止於分支網站的 IP-PBX 來路由電話，前述行為可能會更嚴重，因為需要更多時間來完成訊號。</span><span class="sxs-lookup"><span data-stu-id="c2e80-132">This behavior can be more severe if a Mediation Server at a central site is routing calls for an IP-PBX where the route terminates at a branch site, because more time is needed for signaling to complete.</span></span> <span data-ttu-id="c2e80-133">如果您遇到此行為，請在分支網站上部署轉送伺服器，以減少前幾個字的裁剪。</span><span class="sxs-lookup"><span data-stu-id="c2e80-133">If you experience this behavior, deploying a Mediation Server at the branch site is the only way to reduce clipping of the first few words.</span></span>
  
<span data-ttu-id="c2e80-134">最後，如果您的中央網站上有 TDM PBX，或是您的 IP-PBX 非得使用 PSTN 閘道不可，則您必須在連接中繼伺服器與 PBX 的電話路由上部署閘道。</span><span class="sxs-lookup"><span data-stu-id="c2e80-134">Finally, if your central site has a TDM PBX, or if your IP-PBX does not eliminate the need for a PSTN gateway, then you must deploy a gateway on the call route connecting Mediation Server and the PBX.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c2e80-135">若要改善獨立轉送伺服器的媒體效能，您應該在這些伺服器的網路介面卡上啟用接收端伸縮 (RSS) 。</span><span class="sxs-lookup"><span data-stu-id="c2e80-135">To improve the media performance of standalone Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on these servers.</span></span> <span data-ttu-id="c2e80-136">RSS 可讓伺服器上的多個處理器同時處理內送的封包。</span><span class="sxs-lookup"><span data-stu-id="c2e80-136">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="c2e80-137">如需詳細資訊，請參閱「[Windows Server 中的接收端擴充功能增強功能](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11))」。</span><span class="sxs-lookup"><span data-stu-id="c2e80-137">For details, see "[Receive-Side Scaling Enhancements in Windows Server](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11))".</span></span> <span data-ttu-id="c2e80-138">如需如何啟用 RSS 的詳細資訊，請參閱您的網路介面卡檔。</span><span class="sxs-lookup"><span data-stu-id="c2e80-138">For details about how to enable RSS, see your network adapter documentation.</span></span> 
