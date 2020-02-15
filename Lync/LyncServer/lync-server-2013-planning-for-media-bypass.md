---
title: Lync Server 2013： 規劃媒體旁路
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
ms.openlocfilehash: 0bb4d495637cd78e430e975e9831421906bfbf6e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="0d670-102">規劃 Lync Server 2013 中的媒體旁路</span><span class="sxs-lookup"><span data-stu-id="0d670-102">Planning for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d670-103">_**主題上次修改日期：** 2012年-09-21_</span><span class="sxs-lookup"><span data-stu-id="0d670-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="0d670-104">媒體旁路指的是移除媒體路徑儘通話訊號周遊中繼伺服器移除中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="0d670-104">Media bypass refers to removing the Mediation Server from the media path whenever possible for calls whose signaling traverses the Mediation Server.</span></span>

<span data-ttu-id="0d670-105">媒體旁路可以改善語音品質以減少延遲、 不必要的轉譯、 封包遺失的可能性和潛在的失敗點的數目。</span><span class="sxs-lookup"><span data-stu-id="0d670-105">Media bypass can improve voice quality by reducing latency, needless translation, possibility of packet loss, and the number of points of potential failure.</span></span> <span data-ttu-id="0d670-106">延展性可以改良，因為抵銷的媒體略過通話處理會減少中繼伺服器上的負載。</span><span class="sxs-lookup"><span data-stu-id="0d670-106">Scalability can be improved, because elimination of media processing for bypassed calls reduces the load on the Mediation Server.</span></span> <span data-ttu-id="0d670-107">載入此減少補充控制多個閘道中繼伺服器的能力。</span><span class="sxs-lookup"><span data-stu-id="0d670-107">This reduction in load complements the ability of the Mediation Server to control multiple gateways.</span></span>

<span data-ttu-id="0d670-108">媒體旁路其中分支網站沒有中繼伺服器會連線至中央網站透過一或多個頻寬限制的 WAN 連結，以允許媒體直接流向本地閘道不在分支網站的用戶端降低頻寬需求第一次不必流程跨 WAN 連結至中央網站中繼伺服器和備份。</span><span class="sxs-lookup"><span data-stu-id="0d670-108">Where a branch site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by allowing media from a client at a branch site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.</span></span>

<span data-ttu-id="0d670-109">藉由減輕中繼伺服器的媒體處理，媒體旁路還能減少需要 Enterprise Voice 基礎結構的中繼伺服器的數目。</span><span class="sxs-lookup"><span data-stu-id="0d670-109">By relieving the Mediation Server from media processing, media bypass may also reduce the number of Mediation Servers that an Enterprise Voice infrastructure requires.</span></span>

<span data-ttu-id="0d670-110">下圖顯示基本媒體和訊號路徑在拓撲中使用及沒有媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="0d670-110">The following figure shows basic media and signaling pathways in topologies with and without media bypass.</span></span>

<span data-ttu-id="0d670-111">**媒體和訊號路徑包含和不含媒體旁路**</span><span class="sxs-lookup"><span data-stu-id="0d670-111">**Media and signaling pathways with and without media bypass**</span></span>

<span data-ttu-id="0d670-112">![語音 CAC 媒體旁路連線強制執行](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "語音 CAC 媒體旁路連線強制執行")</span><span class="sxs-lookup"><span data-stu-id="0d670-112">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

<span data-ttu-id="0d670-113">作為一般規則，請盡可能啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="0d670-113">As a general rule, enable media bypass wherever possible.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0d670-114">本章節內容</span><span class="sxs-lookup"><span data-stu-id="0d670-114">In This Section</span></span>

  - [<span data-ttu-id="0d670-115">Lync Server 2013 中的媒體旁路概觀</span><span class="sxs-lookup"><span data-stu-id="0d670-115">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)

  - [<span data-ttu-id="0d670-116">媒體旁路模式的 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d670-116">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)

  - [<span data-ttu-id="0d670-117">媒體旁路和 Lync Server 2013 中的通話許可控制</span><span class="sxs-lookup"><span data-stu-id="0d670-117">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [<span data-ttu-id="0d670-118">Lync Server 2013 中略過媒體的技術需求</span><span class="sxs-lookup"><span data-stu-id="0d670-118">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="0d670-119">相關各節</span><span class="sxs-lookup"><span data-stu-id="0d670-119">Related Sections</span></span>

[<span data-ttu-id="0d670-120">部署 Lync Server 2013 中的進階的 Enterprise Voice 功能</span><span class="sxs-lookup"><span data-stu-id="0d670-120">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0d670-121">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0d670-121">See Also</span></span>


[<span data-ttu-id="0d670-122">設定與 Lync Server 2013 中的媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="0d670-122">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[<span data-ttu-id="0d670-123">通用媒體旁路 Lync Server 2013 中的選項</span><span class="sxs-lookup"><span data-stu-id="0d670-123">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

