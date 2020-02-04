---
title: Lync Server 2013：媒體旁路簡介
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
ms.openlocfilehash: 84c70cae521deebecf30e7c8ec6505b18e9842fa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755497"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-media-bypass-in-lync-server-2013"></a><span data-ttu-id="491f5-102">Lync Server 2013 中的媒體旁路概覽</span><span class="sxs-lookup"><span data-stu-id="491f5-102">Overview of media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="491f5-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="491f5-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="491f5-104">如果您想要將部署的中繼伺服器數量減至最少，則可以使用 [媒體旁路]。</span><span class="sxs-lookup"><span data-stu-id="491f5-104">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="491f5-105">通常，會將中繼伺服器池部署在中央網站，它會控制分支網站上的閘道。</span><span class="sxs-lookup"><span data-stu-id="491f5-105">Typically, a Mediation Server pool will be deployed at a central site, and it will control gateways at branch sites.</span></span> <span data-ttu-id="491f5-106">啟用「媒體旁路」可讓您從分支網站上的用戶端直接透過閘道從分支網站傳送公用交換電話網絡（PSTN）通話的媒體。</span><span class="sxs-lookup"><span data-stu-id="491f5-106">Enabling media bypass allows media for public switched telephone network (PSTN) calls from clients at branch sites to flow directly through the gateways at those sites.</span></span> <span data-ttu-id="491f5-107">Lync Server 2013 出站通話路由及企業語音原則必須正確設定，才能將分支網站用戶端的 PSTN 呼叫路由至適當的閘道。</span><span class="sxs-lookup"><span data-stu-id="491f5-107">Lync Server 2013 outbound call routes and Enterprise Voice policies must be properly configured so that PSTN calls from clients at a branch site are routed to the appropriate gateway.</span></span>

<span data-ttu-id="491f5-108">Wi-fi 網路通常會比有線網路遇到更多的資料包遺失情況。</span><span class="sxs-lookup"><span data-stu-id="491f5-108">Wi-Fi networks typically experience more packet loss than wired networks.</span></span> <span data-ttu-id="491f5-109">從這個資料包遺失中進行的復原並非通常是由閘道所能容納的。</span><span class="sxs-lookup"><span data-stu-id="491f5-109">Recovery from this packet loss is not typically something that can be accommodated by gateways.</span></span> <span data-ttu-id="491f5-110">因此，建議您先評估 Wi-fi 網路的品質，然後再決定是否應該針對無線子網啟用旁路。</span><span class="sxs-lookup"><span data-stu-id="491f5-110">Therefore, we recommend that you evaluate the quality of a Wi-Fi network before determining whether bypass should be enabled for a wireless subnet.</span></span> <span data-ttu-id="491f5-111">在延遲減少與從資料包遺失到恢復的情況下，也有一個折衷考慮。</span><span class="sxs-lookup"><span data-stu-id="491f5-111">There is a tradeoff in latency reduction versus recovery from packet loss to consider, as well.</span></span> <span data-ttu-id="491f5-112">RTAudio （可供不略過中繼伺服器的呼叫使用的編解碼器）更適合處理資料包遺失。</span><span class="sxs-lookup"><span data-stu-id="491f5-112">RTAudio, a codec which is available for calls that do not bypass the Mediation Server, is better suited for handling packet loss.</span></span>

<span data-ttu-id="491f5-113">在您的企業語音結構就緒之後，規劃媒體略過簡單。</span><span class="sxs-lookup"><span data-stu-id="491f5-113">After your Enterprise Voice structure is in place, planning for media bypass is straightforward.</span></span>

  - <span data-ttu-id="491f5-114">如果您的中央拓撲沒有 WAN 連結至分支網站，您可以啟用全域媒體旁路，因為不需要微調控制措施。</span><span class="sxs-lookup"><span data-stu-id="491f5-114">If you have a centralized topology without WAN links to branch sites, you can enable global media bypass, because fine-tuned control is unnecessary.</span></span>

  - <span data-ttu-id="491f5-115">如果您有包含一或多個網路區域及其附屬分支網站的分散式拓朴，請判斷下列事項：</span><span class="sxs-lookup"><span data-stu-id="491f5-115">If you have a distributed topology that consists of one or more network regions and their affiliated branch sites, determine the following:</span></span>
    
      - <span data-ttu-id="491f5-116">您的中繼伺服器對等是否能夠支援媒體旁路所需的功能。</span><span class="sxs-lookup"><span data-stu-id="491f5-116">Whether your Mediation Server peers are able to support the capabilities required for media bypass.</span></span>
    
      - <span data-ttu-id="491f5-117">每個網路區域中的哪些網站有良好的連接。</span><span class="sxs-lookup"><span data-stu-id="491f5-117">Which sites in each network region are well-connected.</span></span>
    
      - <span data-ttu-id="491f5-118">[媒體旁路] 與 [呼叫許可控制] 的組合適合您的網路。</span><span class="sxs-lookup"><span data-stu-id="491f5-118">Which combination of media bypass and call admission control is appropriate for your network.</span></span>

<span data-ttu-id="491f5-119">當您啟用媒體旁路時，系統會自動為網路區域建立唯一的旁路 ID，以及該區域內不含頻寬限制的所有網路網站。</span><span class="sxs-lookup"><span data-stu-id="491f5-119">When you enable media bypass, a unique bypass ID is automatically generated for a network region, and for all network sites without bandwidth constraints within that region.</span></span> <span data-ttu-id="491f5-120">在區域內具有頻寬限制的網站，以及使用頻寬限制連接到區域的網站，會分別指派自己獨特的旁路 Id。</span><span class="sxs-lookup"><span data-stu-id="491f5-120">Sites with bandwidth constraints within the region and sites connected to the region over WAN links with bandwidth constraints are each assigned their own unique bypass IDs.</span></span>

<span data-ttu-id="491f5-121">當使用者撥打電話給 PSTN 時，中繼伺服器會將用戶端子網上的旁路 ID 與閘道子網的旁路 ID 進行比較。</span><span class="sxs-lookup"><span data-stu-id="491f5-121">When a user makes a call to the PSTN, the Mediation Server compares the bypass ID of the client subnet with the bypass ID of the gateway subnet.</span></span> <span data-ttu-id="491f5-122">如果兩個旁路識別碼相符，就會使用媒體旁路進行通話。</span><span class="sxs-lookup"><span data-stu-id="491f5-122">If the two bypass IDs match, media bypass is used for the call.</span></span> <span data-ttu-id="491f5-123">如果旁路識別碼不相符，通話的媒體必須透過中繼伺服器進行流動。</span><span class="sxs-lookup"><span data-stu-id="491f5-123">If the bypass IDs do not match, media for the call must flow through the Mediation Server.</span></span>

<span data-ttu-id="491f5-124">當使用者從 PSTN 接收來電時，使用者的用戶端會將它的旁路 ID 與 PSTN 閘道的旁路識別碼進行比較。</span><span class="sxs-lookup"><span data-stu-id="491f5-124">When a user receives a call from the PSTN, the user’s client compares its bypass ID to that of the PSTN gateway.</span></span> <span data-ttu-id="491f5-125">如果兩個旁路識別碼相符，媒體就會直接從閘道流向用戶端，而不需要轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="491f5-125">If the two bypass IDs match, media flows directly from the gateway to the client, bypassing the Mediation Server.</span></span>

<span data-ttu-id="491f5-126">只有 Lync 2010 或以上的用戶端與裝置支援與中繼伺服器的媒體旁路互動。</span><span class="sxs-lookup"><span data-stu-id="491f5-126">Only Lync 2010 or above clients and devices support media bypass interactions with a Mediation Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="491f5-127">除了在全域啟用旁路媒體之外，您還必須在每個 PSTN 主幹上個別啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="491f5-127">In addition to enabling media bypass globally, you must enable media bypass individually on each PSTN trunk.</span></span> <span data-ttu-id="491f5-128">如果旁路是全域啟用，但未針對特定 PSTN 幹線啟用，則任何涉及 PSTN 幹線的呼叫都不會呼叫媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="491f5-128">If bypass is enabled globally, but is not enabled for a particular PSTN trunk, media bypass will not be invoked for any calls involving that PSTN trunk.</span></span> <span data-ttu-id="491f5-129">此外，當 [媒體旁路] 設定為<STRONG>使用網站和區域資訊</STRONG>時，您必須將所有可路由的子網與它們所在的網站建立關聯。</span><span class="sxs-lookup"><span data-stu-id="491f5-129">In addition, when media bypass is set to <STRONG>Use Site and Region Information</STRONG>, you must associate all routable subnets with the sites in which they are located.</span></span> <span data-ttu-id="491f5-130">如果在不想要略過的網站內有可路由的子網，在您啟用媒體旁路之前，必須將這些子網群組放在新的網站中。</span><span class="sxs-lookup"><span data-stu-id="491f5-130">If there are routable subnets within a site for which bypass is not wanted, these subnets should be grouped within a new site before you enable media bypass.</span></span> <span data-ttu-id="491f5-131">如此一來，就能保證 unroutable 子網已獲指派不同的旁路 ID。</span><span class="sxs-lookup"><span data-stu-id="491f5-131">Doing so will assure that the unroutable subnets are assigned a different bypass ID.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="491f5-132">請參閱</span><span class="sxs-lookup"><span data-stu-id="491f5-132">See Also</span></span>


[<span data-ttu-id="491f5-133">Lync Server 2013 中的媒體旁路模式</span><span class="sxs-lookup"><span data-stu-id="491f5-133">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="491f5-134">Lync Server 2013 中的媒體旁路和通話許可控制</span><span class="sxs-lookup"><span data-stu-id="491f5-134">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
[<span data-ttu-id="491f5-135">Lync Server 2013 中媒體旁路的技術需求</span><span class="sxs-lookup"><span data-stu-id="491f5-135">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

