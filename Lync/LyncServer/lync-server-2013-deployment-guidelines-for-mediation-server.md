---
title: Lync Server 2013：轉送伺服器的部署指導方針
description: Lync Server 2013：轉送伺服器的部署指導方針。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Mediation Server
ms:assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398622(v=OCS.15)
ms:contentKeyID: 48184606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8198431b24714666c9411029aecd12835014fef4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575769"
---
# <a name="deployment-guidelines-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="2b4f3-103">Lync Server 2013 中轉送伺服器的部署指導方針</span><span class="sxs-lookup"><span data-stu-id="2b4f3-103">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b4f3-104">_**主題上次修改日期：** 2012-10-12_</span><span class="sxs-lookup"><span data-stu-id="2b4f3-104">_**Topic Last Modified:** 2012-10-12_</span></span>

<span data-ttu-id="2b4f3-105">本主題說明轉送伺服器部署的規劃指導方針。</span><span class="sxs-lookup"><span data-stu-id="2b4f3-105">This topic describes planning guidelines for Mediation Server deployment.</span></span> <span data-ttu-id="2b4f3-106">在複查這些指導方針之後，建議您使用規劃工具來建立及查看可能的替代拓撲，其可用作您決定要部署之最終定制拓撲的模型。</span><span class="sxs-lookup"><span data-stu-id="2b4f3-106">After reviewing these guidelines, we recommend that you use the Planning Tool to create and view possible alternative topologies, which can serve as models for what the final tailored topology that you decide to deploy would look like.</span></span>

<div>

## <a name="collocated-or-stand-alone-mediation-server"></a><span data-ttu-id="2b4f3-107">組合或獨立轉送伺服器？</span><span class="sxs-lookup"><span data-stu-id="2b4f3-107">Collocated or Stand-alone Mediation Server?</span></span>

<span data-ttu-id="2b4f3-108">中繼伺服器依預設會組合於中央網站上的 Standard Edition 伺服器或前端集區中的前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="2b4f3-108">Mediation Server is by default collocated on the Standard Edition server or Front End Server in a Front End pool at central sites.</span></span> <span data-ttu-id="2b4f3-109">可以處理的公用交換電話網路 (PSTN) 通話的數目，以及集區中所需的機器數目，取決於下列各項：</span><span class="sxs-lookup"><span data-stu-id="2b4f3-109">The number of public switched telephone network (PSTN) calls that can be handled and the number of machines required in the pool will depend on the following:</span></span>

  - <span data-ttu-id="2b4f3-110">轉送伺服器集區所控制的閘道對等數目</span><span class="sxs-lookup"><span data-stu-id="2b4f3-110">The number of gateway peers that the Mediation Server pool controls</span></span>

  - <span data-ttu-id="2b4f3-111">透過這些閘道的高磁片流量週期</span><span class="sxs-lookup"><span data-stu-id="2b4f3-111">The high-volume traffic periods through those gateways</span></span>

  - <span data-ttu-id="2b4f3-112">媒體略過轉送伺服器之來電所占的百分比</span><span class="sxs-lookup"><span data-stu-id="2b4f3-112">The percentage of calls that are calls whose media bypass the Mediation Server</span></span>

<span data-ttu-id="2b4f3-113">在規劃時，請務必考慮有關未針對媒體旁路設定之 PSTN 通話和 A/V 會議的媒體處理需求，以及處理需要支援之繁忙小時通話數目的信號互動所需的處理方式。</span><span class="sxs-lookup"><span data-stu-id="2b4f3-113">When planning, be sure to take into account the media processing requirements for PSTN calls and A/V conferences that are not configured for media bypass, as well as the processing needed to handle signaling interactions for the number of busy-hour calls that need to be supported.</span></span> <span data-ttu-id="2b4f3-114">如果沒有足夠的 CPU，則必須部署一部獨立的轉送伺服器集區;而且 PSTN 閘道、IP PBXs 和 SBCs 必須分割為由一個集區中的組合轉送伺服器，以及一或多個獨立集區中的獨立轉送伺服器所控制的子集。</span><span class="sxs-lookup"><span data-stu-id="2b4f3-114">If there is not enough CPU, then you must deploy a stand-alone pool of Mediation Servers; and PSTN gateways, IP-PBXs, and SBCs will need to be split into subsets that are controlled by the collocated Mediation Servers in one pool and the stand-alone Mediation Servers in one or more stand-alone pools.</span></span>

<span data-ttu-id="2b4f3-115">如果您已部署 PSTN 閘道、IP PBXs 或會話邊界控制器 (SBCs) 不支援與轉送伺服器集區互動的適當功能（包括下列專案），則必須與包含單一轉送伺服器的獨立集區產生關聯：</span><span class="sxs-lookup"><span data-stu-id="2b4f3-115">If you deployed PSTN gateways, IP-PBXs, or Session Border Controllers (SBCs) that do not support the correct capabilities to interact with a pool of Mediation Servers, including the following, then they will need to be associated with a stand-alone pool consisting of a single Mediation Server:</span></span>

  - <span data-ttu-id="2b4f3-116">執行網路層網域名稱系統 (在集區中的轉送伺服器之間) 負載平衡 (或將流量統一傳送至集區中的所有轉送伺服器) </span><span class="sxs-lookup"><span data-stu-id="2b4f3-116">Perform network layer Domain Name System (DNS) load balancing across Mediation Servers in a pool (or otherwise route traffic uniformly to all Mediation Servers in a pool)</span></span>

  - <span data-ttu-id="2b4f3-117">接受來自集區中任何中繼伺服器的流量</span><span class="sxs-lookup"><span data-stu-id="2b4f3-117">Accept traffic from any Mediation Server in a pool</span></span>

<span data-ttu-id="2b4f3-118">您可以使用 Microsoft Lync Server 2013，規劃工具評估組合您的前端集區的轉送伺服器是否可以處理這種負載。</span><span class="sxs-lookup"><span data-stu-id="2b4f3-118">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether collocating the Mediation Server with your Front End pool can handle the load.</span></span> <span data-ttu-id="2b4f3-119">如果環境無法符合這些需求，則您必須部署獨立的中繼伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="2b4f3-119">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

</div>

<div>

## <a name="central-site-and-branch-site-considerations"></a><span data-ttu-id="2b4f3-120">中央網站與分支網站的考量事項</span><span class="sxs-lookup"><span data-stu-id="2b4f3-120">Central Site and Branch Site Considerations</span></span>

<span data-ttu-id="2b4f3-p105">中央網站上的中繼伺服器可用來路由分支網站上 IP-PBX 或 PSTN 閘道的電話。但如果您部署 SIP 主幹，則必須在每個主幹終止的網站上部署中繼伺服器。若要讓中央網站上的中繼伺服器路由分支網站上 IP-PBX 或 PSTN 閘道的電話，並不需要使用媒體旁路。但是可以啟用媒體旁路的話又不同了，啟用媒體旁路將可減少媒體路徑延遲的情況，進而改善媒體品質，因為這時媒體路徑已不需遵循訊號路徑。媒體旁路也可減少集區上的處理負載。</span><span class="sxs-lookup"><span data-stu-id="2b4f3-p105">Mediation Servers at the central site can be used to route calls for IP-PBXs or PSTN gateways at branch sites. If you deploy SIP trunks, however, you must deploy a Mediation Server at the site where each trunk terminates. Having a Mediation Server at the central site route calls for an IP-PBX or PSTN gateway at a branch site does not require the use of media bypass. However, if you can enable media bypass, doing so will reduce media path latency and, consequently, result in improved media quality because the media path is no longer required to follow the signaling path. Media bypass will also decrease the processing load on the pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2b4f3-126">媒體旁路不會與每個 PSTN 閘道、IP-PBX 以及 SBC 相互溝通。</span><span class="sxs-lookup"><span data-stu-id="2b4f3-126">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="2b4f3-127">Microsoft 已測試一組 PSTN 閘道，並與認證的協力廠商 SBCs，並利用 Cisco IP PBXs 進行一些測試。</span><span class="sxs-lookup"><span data-stu-id="2b4f3-127">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="2b4f3-128">只有在整合通訊開啟互通性計畫– Lync Server at 上列出的產品及版本，才支援媒體旁路 <A href="https://go.microsoft.com/fwlink/p/?linkid=268730">https://go.microsoft.com/fwlink/p/?LinkId=268730</A> 。</span><span class="sxs-lookup"><span data-stu-id="2b4f3-128">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=268730">https://go.microsoft.com/fwlink/p/?LinkId=268730</A>.</span></span>



</div>

<span data-ttu-id="2b4f3-129">如果需要分支網站恢復功能，則必須在分支網站上部署 Survivable 分支裝置或前端伺服器、轉送伺服器和閘道的組合。</span><span class="sxs-lookup"><span data-stu-id="2b4f3-129">If branch site resiliency is required, a Survivable Branch Appliance or combination of a Front End Server, a Mediation Server, and a gateway must be deployed at the branch site.</span></span> <span data-ttu-id="2b4f3-130"> (以分支網站恢復的設想，其目前狀態和會議不會在網站上恢復。 ) 如需有關如何進行語音規劃的分支網站的指導，請參閱 [在 Lync Server 2013 中規劃分支網站語音彈性](lync-server-2013-planning-for-branch-site-voice-resiliency.md)。</span><span class="sxs-lookup"><span data-stu-id="2b4f3-130">(The assumption with branch site resiliency is that presence and conferencing are not resilient at the site.) For guidance on branch site planning for voice, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span></span>

<span data-ttu-id="2b4f3-131">在與 IP-PBX 互動的情況下，如果 IP-PBX 無法正確支援與多個早期對話方塊和 RFC 3960 互動的早期媒體互動，則可以從 IP-PBX 至 Lync 端點的來電中，將問候語的前幾個字裁剪。</span><span class="sxs-lookup"><span data-stu-id="2b4f3-131">For interactions with an IP-PBX, if the IP-PBX does not correctly support early media interactions with multiple early dialogs and RFC 3960 interactions, there can be clipping of the first few words of the greeting for incoming calls from the IP-PBX to Lync endpoints.</span></span> <span data-ttu-id="2b4f3-132">如果中央網站上的中繼伺服器是為其整條路由是終止於分支網站的 IP-PBX 來路由電話，前述行為可能會更嚴重，因為需要更多時間來完成訊號。</span><span class="sxs-lookup"><span data-stu-id="2b4f3-132">This behavior can be more severe if a Mediation Server at a central site is routing calls for an IP-PBX where the route terminates at a branch site, because more time is needed for signaling to complete.</span></span> <span data-ttu-id="2b4f3-133">如果您遇到此行為，請在分支網站上部署轉送伺服器，以減少前幾個字的裁剪。</span><span class="sxs-lookup"><span data-stu-id="2b4f3-133">If you experience this behavior, deploying a Mediation Server at the branch site is the only way to reduce clipping of the first few words.</span></span>

<span data-ttu-id="2b4f3-134">最後，如果您的中央網站上有 TDM PBX，或是您的 IP-PBX 非得使用 PSTN 閘道不可，則您必須在連接中繼伺服器與 PBX 的電話路由上部署閘道。</span><span class="sxs-lookup"><span data-stu-id="2b4f3-134">Finally, if your central site has a TDM PBX, or if your IP-PBX does not eliminate the need for a PSTN gateway, then you must deploy a gateway on the call route connecting Mediation Server and the PBX.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2b4f3-135">若要改善獨立轉送伺服器的媒體效能，您應該在這些伺服器的網路介面卡上啟用接收端伸縮 (RSS) 。</span><span class="sxs-lookup"><span data-stu-id="2b4f3-135">To improve the media performance of standalone Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on these servers.</span></span> <span data-ttu-id="2b4f3-136">RSS 可讓伺服器上的多個處理器同時處理內送的封包。</span><span class="sxs-lookup"><span data-stu-id="2b4f3-136">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="2b4f3-137">如需詳細資訊，請參閱的「Windows Server 中的接收端擴充功能增強功能」 <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?LinkId=268731</A> 。</span><span class="sxs-lookup"><span data-stu-id="2b4f3-137">For details, see "Receive-Side Scaling Enhancements in Windows Server" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?LinkId=268731</A>.</span></span> <span data-ttu-id="2b4f3-138">如需如何啟用 RSS 的詳細資訊，請參閱您的網路介面卡檔。</span><span class="sxs-lookup"><span data-stu-id="2b4f3-138">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

