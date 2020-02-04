---
title: Lync Server 2013：規劃媒體旁路
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for media bypass
ms:assetid: 8ac732b6-8538-4d7b-b1a9-2035e419dac2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398703(v=OCS.15)
ms:contentKeyID: 48184768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97b28559ea58439d370042d54ab7ef58943bc594
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41751153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="99483-102">在 Lync Server 2013 中規劃媒體旁路</span><span class="sxs-lookup"><span data-stu-id="99483-102">Planning for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99483-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="99483-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="99483-104">「媒體旁路」是指當信號流經中繼伺服器時，從媒體路徑中移除轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="99483-104">Media bypass refers to removing the Mediation Server from the media path whenever possible for calls whose signaling traverses the Mediation Server.</span></span>

<span data-ttu-id="99483-105">媒體旁路可減少延遲、不必要的轉換、資料包遺失的可能性，以及可能失敗的點數，以改善語音品質。</span><span class="sxs-lookup"><span data-stu-id="99483-105">Media bypass can improve voice quality by reducing latency, needless translation, possibility of packet loss, and the number of points of potential failure.</span></span> <span data-ttu-id="99483-106">可提高可伸縮性，因為取消繞過呼叫的媒體處理減少了中繼伺服器上的負載。</span><span class="sxs-lookup"><span data-stu-id="99483-106">Scalability can be improved, because elimination of media processing for bypassed calls reduces the load on the Mediation Server.</span></span> <span data-ttu-id="99483-107">這個負載的減少是補充了轉送伺服器控制多個閘道的能力。</span><span class="sxs-lookup"><span data-stu-id="99483-107">This reduction in load complements the ability of the Mediation Server to control multiple gateways.</span></span>

<span data-ttu-id="99483-108">如果不含轉送伺服器的分支網站是透過受限制頻寬的一個或多個 WAN 連結連線到中央網站，媒體略過減少頻寬需求，只要允許分支網站的用戶端媒體直接流向本機閘道，而不首先，必須在中央網站和返回轉送伺服器的 WAN 連結之間流動。</span><span class="sxs-lookup"><span data-stu-id="99483-108">Where a branch site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by allowing media from a client at a branch site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.</span></span>

<span data-ttu-id="99483-109">透過從媒體處理中免除轉送伺服器，媒體旁路也可能會減少企業語音結構所需的中繼伺服器數目。</span><span class="sxs-lookup"><span data-stu-id="99483-109">By relieving the Mediation Server from media processing, media bypass may also reduce the number of Mediation Servers that an Enterprise Voice infrastructure requires.</span></span>

<span data-ttu-id="99483-110">下圖顯示拓撲中的基本媒體與信號路徑，以及不使用媒體旁路的情況。</span><span class="sxs-lookup"><span data-stu-id="99483-110">The following figure shows basic media and signaling pathways in topologies with and without media bypass.</span></span>

<span data-ttu-id="99483-111">**媒體與信號路徑，以及不使用媒體旁路**</span><span class="sxs-lookup"><span data-stu-id="99483-111">**Media and signaling pathways with and without media bypass**</span></span>

<span data-ttu-id="99483-112">![強制語音 CAC 媒體旁路連線](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "強制語音 CAC 媒體旁路連線")</span><span class="sxs-lookup"><span data-stu-id="99483-112">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

<span data-ttu-id="99483-113">一般來說，只要有可能就啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="99483-113">As a general rule, enable media bypass wherever possible.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="99483-114">本節內容</span><span class="sxs-lookup"><span data-stu-id="99483-114">In This Section</span></span>

  - [<span data-ttu-id="99483-115">Lync Server 2013 中的媒體旁路概覽</span><span class="sxs-lookup"><span data-stu-id="99483-115">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)

  - [<span data-ttu-id="99483-116">Lync Server 2013 中的媒體旁路模式</span><span class="sxs-lookup"><span data-stu-id="99483-116">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)

  - [<span data-ttu-id="99483-117">Lync Server 2013 中的媒體旁路和通話許可控制</span><span class="sxs-lookup"><span data-stu-id="99483-117">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [<span data-ttu-id="99483-118">Lync Server 2013 中媒體旁路的技術需求</span><span class="sxs-lookup"><span data-stu-id="99483-118">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="99483-119">相關各節</span><span class="sxs-lookup"><span data-stu-id="99483-119">Related Sections</span></span>

[<span data-ttu-id="99483-120">在 Lync Server 2013 中部署高級企業語音功能</span><span class="sxs-lookup"><span data-stu-id="99483-120">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="99483-121">請參閱</span><span class="sxs-lookup"><span data-stu-id="99483-121">See Also</span></span>


<span data-ttu-id="99483-122">[在 Lync Server 2013 中使用 [旁路媒體] 設定主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="99483-122">[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)</span></span>  


[<span data-ttu-id="99483-123">Lync Server 2013 中的全域媒體旁路選項</span><span class="sxs-lookup"><span data-stu-id="99483-123">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

