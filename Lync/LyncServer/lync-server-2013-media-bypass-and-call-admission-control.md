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
ms.openlocfilehash: 2034a58f686d62ab8e755c0e2c624a9a8994961e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765664"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="39a2f-102">Lync Server 2013 中的媒體旁路和通話許可控制</span><span class="sxs-lookup"><span data-stu-id="39a2f-102">Media bypass and call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39a2f-103">_**主題上次修改日期：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="39a2f-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="39a2f-104">[媒體旁路] 和 [呼叫許可控制（CAC）] 共同合作，管理通話媒體的頻寬控制。</span><span class="sxs-lookup"><span data-stu-id="39a2f-104">Media bypass and call admission control (CAC) work together to manage bandwidth control for call media.</span></span> <span data-ttu-id="39a2f-105">[媒體旁路] 有利於在連線的連結上使用媒體流程;CAC 會管理頻寬限制連結的通信量。</span><span class="sxs-lookup"><span data-stu-id="39a2f-105">Media bypass facilitates media flow over well-connected links; CAC manages traffic on links with bandwidth constraints.</span></span> <span data-ttu-id="39a2f-106">因為媒體旁路和 CAC 是互斥的，所以在規劃另一個時，您必須注意到一個。</span><span class="sxs-lookup"><span data-stu-id="39a2f-106">Because Media Bypass and CAC are mutually exclusive, you must be mindful of one when planning for the other.</span></span> <span data-ttu-id="39a2f-107">支援下列組合：</span><span class="sxs-lookup"><span data-stu-id="39a2f-107">The following combinations are supported:</span></span>

  - <span data-ttu-id="39a2f-108">已啟用 CAC 和媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="39a2f-108">CAC and Media Bypass are both enabled.</span></span> <span data-ttu-id="39a2f-109">必須將媒體旁路設定為**使用網站和區域資訊**。</span><span class="sxs-lookup"><span data-stu-id="39a2f-109">Media Bypass must be set to **Use Site and Region Information**.</span></span> <span data-ttu-id="39a2f-110">此網站和區域資訊與用於 CAC 的資訊相同。</span><span class="sxs-lookup"><span data-stu-id="39a2f-110">This site and region information is the same as that used for CAC.</span></span>
    
    <span data-ttu-id="39a2f-111">如果您啟用 CAC，您就無法選取 [**永遠略過**]，反之亦然，因為這兩個設定是互相排斥的。</span><span class="sxs-lookup"><span data-stu-id="39a2f-111">If you enable CAC, you cannot select **Always Bypass**, and vice-versa, because the two configurations are mutually exclusive.</span></span> <span data-ttu-id="39a2f-112">也就是說，只有其中一個是適用于任何已知的 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="39a2f-112">That is, only one of the two will apply to any given PSTN call.</span></span> <span data-ttu-id="39a2f-113">首先，會進行檢查，以判斷媒體旁路是否適用于通話。</span><span class="sxs-lookup"><span data-stu-id="39a2f-113">First, a check is made to determine if media bypass applies to the call.</span></span> <span data-ttu-id="39a2f-114">如果有的話，則不使用 CAC。</span><span class="sxs-lookup"><span data-stu-id="39a2f-114">If it does, then CAC is not used.</span></span> <span data-ttu-id="39a2f-115">這麼做很有意義，因為如果通話符合旁路，就是使用不需要 CAC 的連線來進行定義。</span><span class="sxs-lookup"><span data-stu-id="39a2f-115">This makes sense, because if a call is eligible for bypass, it is by definition using a connection where CAC is not needed.</span></span> <span data-ttu-id="39a2f-116">如果旁路無法套用到通話（也就是用戶端和閘道的旁路識別碼不相符），則會將 CAC 套用到通話。</span><span class="sxs-lookup"><span data-stu-id="39a2f-116">If bypass cannot be applied to the call (that is, if the client’s and gateway’s bypass IDs do not match), then CAC is applied to the call.</span></span>

  - <span data-ttu-id="39a2f-117">未啟用 CAC，且媒體旁路設定為 [**總是略過**]。</span><span class="sxs-lookup"><span data-stu-id="39a2f-117">CAC not enabled and Media Bypass set to **Always Bypass**.</span></span>
    
    <span data-ttu-id="39a2f-118">在這個設定中，用戶端和中繼子網都對應到一個，而且只有一個旁路 ID 是由系統計算。</span><span class="sxs-lookup"><span data-stu-id="39a2f-118">In this configuration, both client and trunk subnets are mapped to one and only one bypass ID, which is computed by the system.</span></span>

  - <span data-ttu-id="39a2f-119">未啟用 CAC，且媒體旁路設定為**使用網站和區域資訊**。</span><span class="sxs-lookup"><span data-stu-id="39a2f-119">CAC not enabled and Media Bypass set to **Use Site and Region Information**.</span></span>
    
    <span data-ttu-id="39a2f-120">在啟用 [**使用網站和區域資訊**] 的情況下，旁路判斷的運作方式基本相同，不論是否已啟用 CAC。</span><span class="sxs-lookup"><span data-stu-id="39a2f-120">Where **Use Site and Region Information** is enabled, bypass determination works essentially the same way, regardless of whether CAC is enabled or not.</span></span> <span data-ttu-id="39a2f-121">也就是說，對於任何已知的 PSTN 呼叫，客戶的子網會對應到特定的網站，而該子網上的旁路識別碼則會被抽取。</span><span class="sxs-lookup"><span data-stu-id="39a2f-121">That is, for any given PSTN call, the client’s subnet is mapped to a particular site, and the bypass ID for that subnet is extracted.</span></span> <span data-ttu-id="39a2f-122">同樣地，閘道的子網會對應到特定的網站，而該子網上的旁路識別碼則會解壓縮。</span><span class="sxs-lookup"><span data-stu-id="39a2f-122">Similarly, the gateway’s subnet is mapped to a particular site, and the bypass ID for that subnet is extracted.</span></span> <span data-ttu-id="39a2f-123">只有當兩個旁路 Id 完全相同時，才會繞過呼叫的情況。</span><span class="sxs-lookup"><span data-stu-id="39a2f-123">Only if the two bypass IDs are identical will bypass happen for the call.</span></span> <span data-ttu-id="39a2f-124">如果兩者不完全相同，則不會發生媒體略過。</span><span class="sxs-lookup"><span data-stu-id="39a2f-124">If they are not identical, media bypass will not occur.</span></span>
    
    <span data-ttu-id="39a2f-125">即使是全域停用的 CAC，也必須針對每個網站和連結定義頻寬原則，如果您想要使用網站和區域設定來控制旁路決策。</span><span class="sxs-lookup"><span data-stu-id="39a2f-125">Even though CAC is disabled globally, bandwidth policy needs to be defined for each site and link if you want to use site-and-region configuration to control the bypass decision.</span></span> <span data-ttu-id="39a2f-126">頻寬限制或其模態的實際值並不重要。</span><span class="sxs-lookup"><span data-stu-id="39a2f-126">The actual value of the bandwidth constraint or its modality doesn’t matter.</span></span> <span data-ttu-id="39a2f-127">最終的目標是讓系統自動計算不同的旁路識別碼，以與沒有良好連接的不同區域設定建立關聯。</span><span class="sxs-lookup"><span data-stu-id="39a2f-127">The ultimate goal is to have the system automatically calculate different bypass IDs to associate with different locales that are not well connected.</span></span> <span data-ttu-id="39a2f-128">依定義定義頻寬限制表示連結未正確連接。</span><span class="sxs-lookup"><span data-stu-id="39a2f-128">Defining a bandwidth constraint by definition means a link is not well connected.</span></span>

  - <span data-ttu-id="39a2f-129">已啟用 CAC，且未啟用媒體旁路功能。</span><span class="sxs-lookup"><span data-stu-id="39a2f-129">CAC is enabled and media bypass is not enabled.</span></span> <span data-ttu-id="39a2f-130">這僅適用于所有閘道與 IP Pbx 沒有正確連接或不符合其他媒體旁路需求的情況。</span><span class="sxs-lookup"><span data-stu-id="39a2f-130">This would apply only where all gateways and IP-PBXs are not well connected or do not meet other requirements for media bypass.</span></span> <span data-ttu-id="39a2f-131">如需媒體旁路需求的詳細資訊，請參閱[Lync Server 2013 中媒體旁路的技術需求](lync-server-2013-technical-requirements-for-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="39a2f-131">For details about requirements for media bypass, see [Technical requirements for media bypass in Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="39a2f-132">請參閱</span><span class="sxs-lookup"><span data-stu-id="39a2f-132">See Also</span></span>


[<span data-ttu-id="39a2f-133">Lync Server 2013 中的媒體旁路概覽</span><span class="sxs-lookup"><span data-stu-id="39a2f-133">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)  
[<span data-ttu-id="39a2f-134">Lync Server 2013 中的媒體旁路模式</span><span class="sxs-lookup"><span data-stu-id="39a2f-134">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="39a2f-135">Lync Server 2013 中媒體旁路的技術需求</span><span class="sxs-lookup"><span data-stu-id="39a2f-135">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

