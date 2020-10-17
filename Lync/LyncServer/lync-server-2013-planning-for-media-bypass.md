---
title: Lync Server 2013：規劃媒體旁路
description: Lync Server 2013：規劃媒體旁路。
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
ms.openlocfilehash: 7d92a50d9d838b0f13fd6837cbfadee1c48712f0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549439"
---
# <a name="planning-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="13bbb-103">在 Lync Server 2013 中規劃媒體旁路</span><span class="sxs-lookup"><span data-stu-id="13bbb-103">Planning for media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13bbb-104">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="13bbb-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="13bbb-105">媒體旁路是指當呼叫的轉送伺服器的信號流經轉送伺服器時，從媒體路徑移除轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="13bbb-105">Media bypass refers to removing the Mediation Server from the media path whenever possible for calls whose signaling traverses the Mediation Server.</span></span>

<span data-ttu-id="13bbb-106">媒體旁路可減少延遲、不必要的轉譯、封包遺失的可能性，以及潛在失敗的點數，以改善語音品質。</span><span class="sxs-lookup"><span data-stu-id="13bbb-106">Media bypass can improve voice quality by reducing latency, needless translation, possibility of packet loss, and the number of points of potential failure.</span></span> <span data-ttu-id="13bbb-107">可提高擴充性，因為消除回避通話的媒體處理會減少轉送伺服器上的負載。</span><span class="sxs-lookup"><span data-stu-id="13bbb-107">Scalability can be improved, because elimination of media processing for bypassed calls reduces the load on the Mediation Server.</span></span> <span data-ttu-id="13bbb-108">這項負載降低負載，對轉送伺服器控制多個閘道的能力有所補充。</span><span class="sxs-lookup"><span data-stu-id="13bbb-108">This reduction in load complements the ability of the Mediation Server to control multiple gateways.</span></span>

<span data-ttu-id="13bbb-109">在下列情況下，如果沒有轉送伺服器的分支網站會透過一或多個具有限制頻寬的 WAN 連結連線至中央網站，媒體略過可允許來自分支網站用戶端的媒體，以直接流向其本地閘道，而不需要先透過 WAN 連結傳送至中央網站的轉送伺服器和回復。</span><span class="sxs-lookup"><span data-stu-id="13bbb-109">Where a branch site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by allowing media from a client at a branch site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.</span></span>

<span data-ttu-id="13bbb-110">透過從媒體處理中免除轉送伺服器，媒體旁路也可以減少企業語音基礎結構所需的轉送伺服器數目。</span><span class="sxs-lookup"><span data-stu-id="13bbb-110">By relieving the Mediation Server from media processing, media bypass may also reduce the number of Mediation Servers that an Enterprise Voice infrastructure requires.</span></span>

<span data-ttu-id="13bbb-111">下圖顯示在具有和不含媒體旁路的拓撲中的基本媒體和信號路徑。</span><span class="sxs-lookup"><span data-stu-id="13bbb-111">The following figure shows basic media and signaling pathways in topologies with and without media bypass.</span></span>

<span data-ttu-id="13bbb-112">**具有和不含媒體旁路的媒體和信號路徑**</span><span class="sxs-lookup"><span data-stu-id="13bbb-112">**Media and signaling pathways with and without media bypass**</span></span>

<span data-ttu-id="13bbb-113">![語音 CAC 媒體旁路連接強制](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "語音 CAC 媒體旁路連接強制")</span><span class="sxs-lookup"><span data-stu-id="13bbb-113">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

<span data-ttu-id="13bbb-114">一般來說，盡可能啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="13bbb-114">As a general rule, enable media bypass wherever possible.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="13bbb-115">本章節內容</span><span class="sxs-lookup"><span data-stu-id="13bbb-115">In This Section</span></span>

  - [<span data-ttu-id="13bbb-116">Lync Server 2013 中的媒體旁路概述</span><span class="sxs-lookup"><span data-stu-id="13bbb-116">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)

  - [<span data-ttu-id="13bbb-117">Lync Server 2013 中的媒體旁路模式</span><span class="sxs-lookup"><span data-stu-id="13bbb-117">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)

  - [<span data-ttu-id="13bbb-118">Lync Server 2013 中的媒體旁路和通話許可控制</span><span class="sxs-lookup"><span data-stu-id="13bbb-118">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [<span data-ttu-id="13bbb-119">Lync Server 2013 中媒體旁路的技術需求</span><span class="sxs-lookup"><span data-stu-id="13bbb-119">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="13bbb-120">相關各節</span><span class="sxs-lookup"><span data-stu-id="13bbb-120">Related Sections</span></span>

[<span data-ttu-id="13bbb-121">在 Lync Server 2013 中部署高級 Enterprise Voice 功能</span><span class="sxs-lookup"><span data-stu-id="13bbb-121">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="13bbb-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="13bbb-122">See Also</span></span>


[<span data-ttu-id="13bbb-123">在 Lync Server 2013 中設定含媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="13bbb-123">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[<span data-ttu-id="13bbb-124">Lync Server 2013 中的全域媒體旁路選項</span><span class="sxs-lookup"><span data-stu-id="13bbb-124">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

