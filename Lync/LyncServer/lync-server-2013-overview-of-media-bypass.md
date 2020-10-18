---
title: Lync Server 2013：媒體旁路簡介
description: Lync Server 2013：媒體旁路的簡介。
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
ms.openlocfilehash: 3859c41a01ae5e7f1100a6872fd4e6747f45dbd8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577329"
---
# <a name="overview-of-media-bypass-in-lync-server-2013"></a><span data-ttu-id="46fa9-103">Lync Server 2013 中的媒體旁路概述</span><span class="sxs-lookup"><span data-stu-id="46fa9-103">Overview of media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46fa9-104">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="46fa9-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="46fa9-105">當您想要將已部署的轉送伺服器數目降至最低時，媒體旁路很有用。</span><span class="sxs-lookup"><span data-stu-id="46fa9-105">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="46fa9-106">一般來說，轉送伺服器集區會部署在中央網站，它會控制分支網站上的閘道。</span><span class="sxs-lookup"><span data-stu-id="46fa9-106">Typically, a Mediation Server pool will be deployed at a central site, and it will control gateways at branch sites.</span></span> <span data-ttu-id="46fa9-107">啟用媒體旁路允許公用交換電話網路的媒體 (PSTN) 來自分支網站用戶端的呼叫，以直接透過這些網站上的閘道來流向。</span><span class="sxs-lookup"><span data-stu-id="46fa9-107">Enabling media bypass allows media for public switched telephone network (PSTN) calls from clients at branch sites to flow directly through the gateways at those sites.</span></span> <span data-ttu-id="46fa9-108">Lync Server 2013 輸出呼叫路由和 Enterprise Voice 原則必須正確設定，才能讓來自分支網站之用戶端的 PSTN 呼叫路由傳送至適當的閘道。</span><span class="sxs-lookup"><span data-stu-id="46fa9-108">Lync Server 2013 outbound call routes and Enterprise Voice policies must be properly configured so that PSTN calls from clients at a branch site are routed to the appropriate gateway.</span></span>

<span data-ttu-id="46fa9-109">Wi-Fi 網路通常會比有線網路體驗更大的封包遺失。</span><span class="sxs-lookup"><span data-stu-id="46fa9-109">Wi-Fi networks typically experience more packet loss than wired networks.</span></span> <span data-ttu-id="46fa9-110">從這封包中復原的情況通常不是閘道可容納的內容。</span><span class="sxs-lookup"><span data-stu-id="46fa9-110">Recovery from this packet loss is not typically something that can be accommodated by gateways.</span></span> <span data-ttu-id="46fa9-111">因此，建議您先評估 Wi-Fi 網路的品質，再決定是否應該為無線子網啟用旁路。</span><span class="sxs-lookup"><span data-stu-id="46fa9-111">Therefore, we recommend that you evaluate the quality of a Wi-Fi network before determining whether bypass should be enabled for a wireless subnet.</span></span> <span data-ttu-id="46fa9-112">延遲延遲與從封包遺失的復原也有折衷。</span><span class="sxs-lookup"><span data-stu-id="46fa9-112">There is a tradeoff in latency reduction versus recovery from packet loss to consider, as well.</span></span> <span data-ttu-id="46fa9-113">RTAudio，可供未略過轉送伺服器之呼叫使用的編解碼器，會更適合處理封包遺失。</span><span class="sxs-lookup"><span data-stu-id="46fa9-113">RTAudio, a codec which is available for calls that do not bypass the Mediation Server, is better suited for handling packet loss.</span></span>

<span data-ttu-id="46fa9-114">在您的企業語音結構就緒後，規劃媒體旁路是直接的。</span><span class="sxs-lookup"><span data-stu-id="46fa9-114">After your Enterprise Voice structure is in place, planning for media bypass is straightforward.</span></span>

  - <span data-ttu-id="46fa9-115">如果您有集中式拓撲，但沒有分支網站的 WAN 連結，您可以啟用全域媒體旁路，因為不需要微調控制項。</span><span class="sxs-lookup"><span data-stu-id="46fa9-115">If you have a centralized topology without WAN links to branch sites, you can enable global media bypass, because fine-tuned control is unnecessary.</span></span>

  - <span data-ttu-id="46fa9-116">如果您有分散式拓撲，且該拓撲是由一或多個網路地區和其附屬分支網站組成，請決定下列各項：</span><span class="sxs-lookup"><span data-stu-id="46fa9-116">If you have a distributed topology that consists of one or more network regions and their affiliated branch sites, determine the following:</span></span>
    
      - <span data-ttu-id="46fa9-117">您的轉送伺服器對等是否可以支援媒體旁路所需的功能。</span><span class="sxs-lookup"><span data-stu-id="46fa9-117">Whether your Mediation Server peers are able to support the capabilities required for media bypass.</span></span>
    
      - <span data-ttu-id="46fa9-118">每個網路地區的哪些網站已正確連接。</span><span class="sxs-lookup"><span data-stu-id="46fa9-118">Which sites in each network region are well-connected.</span></span>
    
      - <span data-ttu-id="46fa9-119">媒體旁路和通話許可控制的組合適用于您的網路。</span><span class="sxs-lookup"><span data-stu-id="46fa9-119">Which combination of media bypass and call admission control is appropriate for your network.</span></span>

<span data-ttu-id="46fa9-120">當您啟用媒體旁路時，系統會自動為網路地區產生唯一的旁路識別碼，以及該地區內沒有頻寬限制的所有網路網站。</span><span class="sxs-lookup"><span data-stu-id="46fa9-120">When you enable media bypass, a unique bypass ID is automatically generated for a network region, and for all network sites without bandwidth constraints within that region.</span></span> <span data-ttu-id="46fa9-121">在地區內具有頻寬限制的網站，以及透過頻寬限制透過 WAN 連結連線至區域的網站，會為每個使用者指派各自的唯一旁路 IDs。</span><span class="sxs-lookup"><span data-stu-id="46fa9-121">Sites with bandwidth constraints within the region and sites connected to the region over WAN links with bandwidth constraints are each assigned their own unique bypass IDs.</span></span>

<span data-ttu-id="46fa9-122">當使用者呼叫 PSTN 時，轉送伺服器會將用戶端子網上的旁路識別碼與閘道子網的旁路識別碼進行比較。</span><span class="sxs-lookup"><span data-stu-id="46fa9-122">When a user makes a call to the PSTN, the Mediation Server compares the bypass ID of the client subnet with the bypass ID of the gateway subnet.</span></span> <span data-ttu-id="46fa9-123">如果兩個旁路 IDs 相符，媒體旁路會用於通話。</span><span class="sxs-lookup"><span data-stu-id="46fa9-123">If the two bypass IDs match, media bypass is used for the call.</span></span> <span data-ttu-id="46fa9-124">如果旁路 IDs 不符，則通話的媒體必須透過轉送伺服器流動。</span><span class="sxs-lookup"><span data-stu-id="46fa9-124">If the bypass IDs do not match, media for the call must flow through the Mediation Server.</span></span>

<span data-ttu-id="46fa9-125">當使用者從 PSTN 接收來電時，使用者的用戶端會將其旁路識別碼與 PSTN 閘道的要求進行比較。</span><span class="sxs-lookup"><span data-stu-id="46fa9-125">When a user receives a call from the PSTN, the user’s client compares its bypass ID to that of the PSTN gateway.</span></span> <span data-ttu-id="46fa9-126">如果兩個略過的 IDs 相符，媒體就會直接從閘道流向用戶端，以略過轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="46fa9-126">If the two bypass IDs match, media flows directly from the gateway to the client, bypassing the Mediation Server.</span></span>

<span data-ttu-id="46fa9-127">只有 Lync 2010 或以上的用戶端和裝置才支援與轉送伺服器的媒體旁路互動。</span><span class="sxs-lookup"><span data-stu-id="46fa9-127">Only Lync 2010 or above clients and devices support media bypass interactions with a Mediation Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="46fa9-128">除了啟用全域旁路之外，您還必須在每個 PSTN 主幹上個別啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="46fa9-128">In addition to enabling media bypass globally, you must enable media bypass individually on each PSTN trunk.</span></span> <span data-ttu-id="46fa9-129">如果以全域方式啟用旁路，但未針對特定 PSTN 主幹啟用旁路，則任何涉及該 PSTN 主幹的呼叫都不會叫用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="46fa9-129">If bypass is enabled globally, but is not enabled for a particular PSTN trunk, media bypass will not be invoked for any calls involving that PSTN trunk.</span></span> <span data-ttu-id="46fa9-130">此外，當媒體旁路設定為 <STRONG>使用網站與地區資訊</STRONG>時，您必須將所有可路由的子網與所在的網站產生關聯。</span><span class="sxs-lookup"><span data-stu-id="46fa9-130">In addition, when media bypass is set to <STRONG>Use Site and Region Information</STRONG>, you must associate all routable subnets with the sites in which they are located.</span></span> <span data-ttu-id="46fa9-131">如果不想要略過的網站內有可路由的子網，這些子網應該會在新的網站中群組，再啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="46fa9-131">If there are routable subnets within a site for which bypass is not wanted, these subnets should be grouped within a new site before you enable media bypass.</span></span> <span data-ttu-id="46fa9-132">這樣做會保證會為 unroutable 子網指派不同的回避識別碼。</span><span class="sxs-lookup"><span data-stu-id="46fa9-132">Doing so will assure that the unroutable subnets are assigned a different bypass ID.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="46fa9-133">另請參閱</span><span class="sxs-lookup"><span data-stu-id="46fa9-133">See Also</span></span>


[<span data-ttu-id="46fa9-134">Lync Server 2013 中的媒體旁路模式</span><span class="sxs-lookup"><span data-stu-id="46fa9-134">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="46fa9-135">Lync Server 2013 中的媒體旁路和通話許可控制</span><span class="sxs-lookup"><span data-stu-id="46fa9-135">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
[<span data-ttu-id="46fa9-136">Lync Server 2013 中媒體旁路的技術需求</span><span class="sxs-lookup"><span data-stu-id="46fa9-136">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

