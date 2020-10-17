---
title: Lync Server 2013：媒體旁路和通話許可控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass and call admission control
ms:assetid: 120b2a2b-5f97-4735-a2ee-0f849feb8c1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398203(v=OCS.15)
ms:contentKeyID: 48183454
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4afa8f26e28fbb4261b0d8524c02efeb8d2a3132
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524630"
---
# <a name="media-bypass-and-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="6ae5f-102">Lync Server 2013 中的媒體旁路和通話許可控制</span><span class="sxs-lookup"><span data-stu-id="6ae5f-102">Media bypass and call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ae5f-103">_**主題上次修改日期：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="6ae5f-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="6ae5f-p101">媒體旁路與通話許可控制 (CAC) 可一起運作，管理通話媒體的頻寬控制。媒體旁路有助於媒體在連線良好的連結上流通；CAD 則可管理具有頻寬限制的連結流量。由於媒體旁路與 CAC 會互相排斥，因此規劃時請務必小心。支援下列組合：</span><span class="sxs-lookup"><span data-stu-id="6ae5f-p101">Media bypass and call admission control (CAC) work together to manage bandwidth control for call media. Media bypass facilitates media flow over well-connected links; CAC manages traffic on links with bandwidth constraints. Because Media Bypass and CAC are mutually exclusive, you must be mindful of one when planning for the other. The following combinations are supported:</span></span>

  - <span data-ttu-id="6ae5f-p102">CAC 與媒體旁路同時啟用。媒體旁路必須設為 **[使用網站與地區資訊]**。該網站與地區資訊必須與 CAC 所使用的網站與地區資訊相同。</span><span class="sxs-lookup"><span data-stu-id="6ae5f-p102">CAC and Media Bypass are both enabled. Media Bypass must be set to **Use Site and Region Information**. This site and region information is the same as that used for CAC.</span></span>
    
    <span data-ttu-id="6ae5f-p103">若您啟用了 CAC，則您無法選取 **[永遠略過]**，反之亦然，因為兩者的組態會互相排斥。亦即，任何特定的 PSTN 通話一次只能適用其中一種組態。首先，系統會檢查並判斷通話是否可套用媒體旁路。如果是的話，就不會使用 CAC。這麼做是有道理的，因為如果通話適用旁路的話，依據定義會使用不需要 CAC 的連線。如果通話不適用旁路 (亦即，如果用戶端與閘道的旁路 ID 不相符)，則通話會套用 CAC。</span><span class="sxs-lookup"><span data-stu-id="6ae5f-p103">If you enable CAC, you cannot select **Always Bypass**, and vice-versa, because the two configurations are mutually exclusive. That is, only one of the two will apply to any given PSTN call. First, a check is made to determine if media bypass applies to the call. If it does, then CAC is not used. This makes sense, because if a call is eligible for bypass, it is by definition using a connection where CAC is not needed. If bypass cannot be applied to the call (that is, if the client’s and gateway’s bypass IDs do not match), then CAC is applied to the call.</span></span>

  - <span data-ttu-id="6ae5f-117">CAC 未啟用且媒體旁路設為 **[永遠略過]**。</span><span class="sxs-lookup"><span data-stu-id="6ae5f-117">CAC not enabled and Media Bypass set to **Always Bypass**.</span></span>
    
    <span data-ttu-id="6ae5f-118">在此組態中，用戶端與主幹子網路會對應至唯一的旁路 ID (由系統計算而來)。</span><span class="sxs-lookup"><span data-stu-id="6ae5f-118">In this configuration, both client and trunk subnets are mapped to one and only one bypass ID, which is computed by the system.</span></span>

  - <span data-ttu-id="6ae5f-119">CAC 未啟用且媒體旁路設為 **[使用網站與地區資訊]**。</span><span class="sxs-lookup"><span data-stu-id="6ae5f-119">CAC not enabled and Media Bypass set to **Use Site and Region Information**.</span></span>
    
    <span data-ttu-id="6ae5f-p104">一旦啟用 **[使用網站與地區資訊]**，旁路判斷工作基本上會以相同模式運作，不管 CAC 是否已啟用都沒有影響。亦即，針對任何特定的 PSTN 通話，用戶端的子網路會對應至特定網站，並擷取該子網路的旁路 ID。同理，閘道的子網路會對應至特定網站，並擷取該子網路的旁路 ID。只有兩組旁路 ID 都一模一樣時，通話才會套用旁路。如果沒有一模一樣，將不會套用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="6ae5f-p104">Where **Use Site and Region Information** is enabled, bypass determination works essentially the same way, regardless of whether CAC is enabled or not. That is, for any given PSTN call, the client’s subnet is mapped to a particular site, and the bypass ID for that subnet is extracted. Similarly, the gateway’s subnet is mapped to a particular site, and the bypass ID for that subnet is extracted. Only if the two bypass IDs are identical will bypass happen for the call. If they are not identical, media bypass will not occur.</span></span>
    
    <span data-ttu-id="6ae5f-p105">即便 CAC 已經全域停用，如果您想要使用網站與地區組態來控制旁路決策時，還是需要針對每個網站與連結定義頻寬原則。頻寬限制或其模式的實際值並沒有影響。最終目標是讓系統自動計算不同的旁路 ID 以便和未能順利連接的不同區域產生關聯。依據定義，定義頻寬限制代表某個連結並未順利連接。</span><span class="sxs-lookup"><span data-stu-id="6ae5f-p105">Even though CAC is disabled globally, bandwidth policy needs to be defined for each site and link if you want to use site-and-region configuration to control the bypass decision. The actual value of the bandwidth constraint or its modality doesn’t matter. The ultimate goal is to have the system automatically calculate different bypass IDs to associate with different locales that are not well connected. Defining a bandwidth constraint by definition means a link is not well connected.</span></span>

  - <span data-ttu-id="6ae5f-129">CAC 已啟用而媒體旁路未啟用。</span><span class="sxs-lookup"><span data-stu-id="6ae5f-129">CAC is enabled and media bypass is not enabled.</span></span> <span data-ttu-id="6ae5f-130">只有當所有閘道與 IP-PBX 並未順利連接，或是不符合其他媒體旁路需求時，才會套用此設定。</span><span class="sxs-lookup"><span data-stu-id="6ae5f-130">This would apply only where all gateways and IP-PBXs are not well connected or do not meet other requirements for media bypass.</span></span> <span data-ttu-id="6ae5f-131">如需媒體旁路需求的詳細資訊，請參閱 [Lync Server 2013 中媒體旁路的技術需求](lync-server-2013-technical-requirements-for-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="6ae5f-131">For details about requirements for media bypass, see [Technical requirements for media bypass in Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="6ae5f-132">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6ae5f-132">See Also</span></span>


[<span data-ttu-id="6ae5f-133">Lync Server 2013 中的媒體旁路概述</span><span class="sxs-lookup"><span data-stu-id="6ae5f-133">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)  
[<span data-ttu-id="6ae5f-134">Lync Server 2013 中的媒體旁路模式</span><span class="sxs-lookup"><span data-stu-id="6ae5f-134">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="6ae5f-135">Lync Server 2013 中媒體旁路的技術需求</span><span class="sxs-lookup"><span data-stu-id="6ae5f-135">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

