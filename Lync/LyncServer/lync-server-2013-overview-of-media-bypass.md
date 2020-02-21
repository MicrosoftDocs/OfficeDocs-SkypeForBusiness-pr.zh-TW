---
title: 媒體旁路的 Lync Server 2013： 概觀
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of media bypass
ms:assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412740(v=OCS.15)
ms:contentKeyID: 48184924
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66c2484b656cce15a6f7d013060c1fc95047f49d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-media-bypass-in-lync-server-2013"></a><span data-ttu-id="57bed-102">Lync Server 2013 中的媒體旁路概觀</span><span class="sxs-lookup"><span data-stu-id="57bed-102">Overview of media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57bed-103">_**主題上次修改日期：** 2012年-09-21_</span><span class="sxs-lookup"><span data-stu-id="57bed-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="57bed-104">當您想要部署的中繼伺服器的數目降至最低，媒體旁路特別有用。</span><span class="sxs-lookup"><span data-stu-id="57bed-104">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="57bed-105">一般而言，或中繼伺服器集區將會部署在中央網站，而且它會控制在分支站台的閘道。</span><span class="sxs-lookup"><span data-stu-id="57bed-105">Typically, a Mediation Server pool will be deployed at a central site, and it will control gateways at branch sites.</span></span> <span data-ttu-id="57bed-106">啟用媒體旁路允許來自在分支站台的用戶端至流程直接通過這些網站閘道的公用交換的電話網路 (PSTN) 通話的媒體。</span><span class="sxs-lookup"><span data-stu-id="57bed-106">Enabling media bypass allows media for public switched telephone network (PSTN) calls from clients at branch sites to flow directly through the gateways at those sites.</span></span> <span data-ttu-id="57bed-107">Lync Server 2013 撥出電話路由和企業語音原則必須正確設定，讓來自用戶端在分支網站的 PSTN 通話路由傳送至適當的閘道。</span><span class="sxs-lookup"><span data-stu-id="57bed-107">Lync Server 2013 outbound call routes and Enterprise Voice policies must be properly configured so that PSTN calls from clients at a branch site are routed to the appropriate gateway.</span></span>

<span data-ttu-id="57bed-108">Wi-fi 網路通常會遇到更多比有線網路封包遺失。</span><span class="sxs-lookup"><span data-stu-id="57bed-108">Wi-Fi networks typically experience more packet loss than wired networks.</span></span> <span data-ttu-id="57bed-109">從這個封包遺失復原不是通常可以容納的閘道。</span><span class="sxs-lookup"><span data-stu-id="57bed-109">Recovery from this packet loss is not typically something that can be accommodated by gateways.</span></span> <span data-ttu-id="57bed-110">因此，建議您先決定是否應啟用無線子網路的旁路評估的 Wi-fi 網路品質。</span><span class="sxs-lookup"><span data-stu-id="57bed-110">Therefore, we recommend that you evaluate the quality of a Wi-Fi network before determining whether bypass should be enabled for a wireless subnet.</span></span> <span data-ttu-id="57bed-111">與封包遺失考量，以及從復原延遲減少沒有取捨。</span><span class="sxs-lookup"><span data-stu-id="57bed-111">There is a tradeoff in latency reduction versus recovery from packet loss to consider, as well.</span></span> <span data-ttu-id="57bed-112">RTAudio，這是適用於不會略過中繼伺服器的呼叫轉碼器是更適合處理封包遺失。</span><span class="sxs-lookup"><span data-stu-id="57bed-112">RTAudio, a codec which is available for calls that do not bypass the Mediation Server, is better suited for handling packet loss.</span></span>

<span data-ttu-id="57bed-113">您的企業語音結構就緒後，規劃媒體旁路便相當簡單。</span><span class="sxs-lookup"><span data-stu-id="57bed-113">After your Enterprise Voice structure is in place, planning for media bypass is straightforward.</span></span>

  - <span data-ttu-id="57bed-114">如果您有集中式的拓撲，而 WAN 連結至分支網站，您可以啟用通用媒體旁路，因為不需要精細的控制。</span><span class="sxs-lookup"><span data-stu-id="57bed-114">If you have a centralized topology without WAN links to branch sites, you can enable global media bypass, because fine-tuned control is unnecessary.</span></span>

  - <span data-ttu-id="57bed-115">如果您有分散式的拓撲，其中包含一或多個網路地區及其附屬的分支網站的決定下列項目：</span><span class="sxs-lookup"><span data-stu-id="57bed-115">If you have a distributed topology that consists of one or more network regions and their affiliated branch sites, determine the following:</span></span>
    
      - <span data-ttu-id="57bed-116">中繼伺服器對等是否可以支援媒體旁路所需的功能。</span><span class="sxs-lookup"><span data-stu-id="57bed-116">Whether your Mediation Server peers are able to support the capabilities required for media bypass.</span></span>
    
      - <span data-ttu-id="57bed-117">每個網路地區中的哪些網站已妥善連接。</span><span class="sxs-lookup"><span data-stu-id="57bed-117">Which sites in each network region are well-connected.</span></span>
    
      - <span data-ttu-id="57bed-118">哪一種媒體組合旁路和通話許可控制適合您的網路。</span><span class="sxs-lookup"><span data-stu-id="57bed-118">Which combination of media bypass and call admission control is appropriate for your network.</span></span>

<span data-ttu-id="57bed-119">當您啟用媒體旁路時，唯一的旁路 ID 會自動產生的網路地區，並沒有該區域內的頻寬限制的所有網路網站。</span><span class="sxs-lookup"><span data-stu-id="57bed-119">When you enable media bypass, a unique bypass ID is automatically generated for a network region, and for all network sites without bandwidth constraints within that region.</span></span> <span data-ttu-id="57bed-120">使用的區域內的頻寬限制的網站和網站透過與頻寬限制的 WAN 連結來連線至區域是每個指派給其專屬唯一旁路 Id。</span><span class="sxs-lookup"><span data-stu-id="57bed-120">Sites with bandwidth constraints within the region and sites connected to the region over WAN links with bandwidth constraints are each assigned their own unique bypass IDs.</span></span>

<span data-ttu-id="57bed-121">當使用者進行 pstn 通話時，中繼伺服器比較旁路 ID 之用戶端子網路與閘道子網路的旁路識別碼。</span><span class="sxs-lookup"><span data-stu-id="57bed-121">When a user makes a call to the PSTN, the Mediation Server compares the bypass ID of the client subnet with the bypass ID of the gateway subnet.</span></span> <span data-ttu-id="57bed-122">如果這兩個略過識別碼比對，媒體旁路用於通話。</span><span class="sxs-lookup"><span data-stu-id="57bed-122">If the two bypass IDs match, media bypass is used for the call.</span></span> <span data-ttu-id="57bed-123">略過不相符識別碼，如果通話的媒體必須經過中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="57bed-123">If the bypass IDs do not match, media for the call must flow through the Mediation Server.</span></span>

<span data-ttu-id="57bed-124">當使用者收到 PSTN 呼叫時，使用者的用戶端會比較的 PSTN 閘道其旁路識別碼。</span><span class="sxs-lookup"><span data-stu-id="57bed-124">When a user receives a call from the PSTN, the user’s client compares its bypass ID to that of the PSTN gateway.</span></span> <span data-ttu-id="57bed-125">如果這兩個略過識別碼比對，媒體流向直接從用戶端，略過中繼伺服器閘道。</span><span class="sxs-lookup"><span data-stu-id="57bed-125">If the two bypass IDs match, media flows directly from the gateway to the client, bypassing the Mediation Server.</span></span>

<span data-ttu-id="57bed-126">只有 Lync 2010 或以上的用戶端和裝置支援媒體旁路與中繼伺服器之間的互動。</span><span class="sxs-lookup"><span data-stu-id="57bed-126">Only Lync 2010 or above clients and devices support media bypass interactions with a Mediation Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="57bed-127">除了啟用媒體旁路全域，您必須啟用媒體旁路，分別在每個 PSTN 主幹。</span><span class="sxs-lookup"><span data-stu-id="57bed-127">In addition to enabling media bypass globally, you must enable media bypass individually on each PSTN trunk.</span></span> <span data-ttu-id="57bed-128">如果旁路全域，已啟用，但未啟用特定的 PSTN 主幹，媒體旁路將不會叫用任何涉及該 PSTN 主幹的通話。</span><span class="sxs-lookup"><span data-stu-id="57bed-128">If bypass is enabled globally, but is not enabled for a particular PSTN trunk, media bypass will not be invoked for any calls involving that PSTN trunk.</span></span> <span data-ttu-id="57bed-129">此外，當媒體旁路設為<STRONG>使用網站與地區資訊</STRONG>，您必須關聯可路由傳送的所有子網路所屬的所在的網站。</span><span class="sxs-lookup"><span data-stu-id="57bed-129">In addition, when media bypass is set to <STRONG>Use Site and Region Information</STRONG>, you must associate all routable subnets with the sites in which they are located.</span></span> <span data-ttu-id="57bed-130">如果不想略過站台內的路由傳送子網路，則這些子網路應進行分組，新的站台內啟用媒體旁路之前。</span><span class="sxs-lookup"><span data-stu-id="57bed-130">If there are routable subnets within a site for which bypass is not wanted, these subnets should be grouped within a new site before you enable media bypass.</span></span> <span data-ttu-id="57bed-131">這樣可確保無法路由的子網路會指派不同的旁路 id。</span><span class="sxs-lookup"><span data-stu-id="57bed-131">Doing so will assure that the unroutable subnets are assigned a different bypass ID.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="57bed-132">另請參閱</span><span class="sxs-lookup"><span data-stu-id="57bed-132">See Also</span></span>


[<span data-ttu-id="57bed-133">媒體旁路模式的 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57bed-133">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="57bed-134">媒體旁路和 Lync Server 2013 中的通話許可控制</span><span class="sxs-lookup"><span data-stu-id="57bed-134">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
[<span data-ttu-id="57bed-135">Lync Server 2013 中略過媒體的技術需求</span><span class="sxs-lookup"><span data-stu-id="57bed-135">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

