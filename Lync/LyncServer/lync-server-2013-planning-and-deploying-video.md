---
title: Lync Server 2013：規劃及部署影片
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning and deploying video
ms:assetid: dadfb7f3-dfd6-4847-b137-17dacafd7368
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205307(v=OCS.15)
ms:contentKeyID: 48185558
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2662a6397bc096969ca73baab096bc886de65ce3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-and-deploying-video-in-lync-server-2013"></a><span data-ttu-id="d7190-102">在 Lync Server 2013 中規劃及部署影片</span><span class="sxs-lookup"><span data-stu-id="d7190-102">Planning and deploying video in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7190-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="d7190-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="d7190-104">Lync Server 2013 引進了下列新的影片功能：</span><span class="sxs-lookup"><span data-stu-id="d7190-104">Lync Server 2013 introduces the following new video features:</span></span>

  - <span data-ttu-id="d7190-105">**HD video**   使用者可以在雙方通話和多方會議中體驗最高解析度（hd）（也就是 1920 x 1080）的解析度。</span><span class="sxs-lookup"><span data-stu-id="d7190-105">**HD video**   Users can experience resolutions up to full high definition (HD) (that is, 1920 x 1080) in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="d7190-106">\*\*\*\*    在視訊會議中有超過兩個人的 [庫] 視圖，使用者可以在會議中看到參與者的影片。</span><span class="sxs-lookup"><span data-stu-id="d7190-106">**Gallery View**   In video conferences that have more than two people, users can see videos of participants in the conference.</span></span> <span data-ttu-id="d7190-107">如果會議有超過五個參與者，則只有最活躍參與者的影片會出現在頂端列中，而其他參與者則會出現相片。</span><span class="sxs-lookup"><span data-stu-id="d7190-107">If the conference has more than five participants, video of only the most active participants appears in the top row, and a photo appears for the other participants.</span></span>

  - <span data-ttu-id="d7190-108">**中的 264 video**   現在，我們是 Lync 2013 用戶端的編碼影片的預設值。</span><span class="sxs-lookup"><span data-stu-id="d7190-108">**H.264 video**   The H.264 video codec is now the default for encoding video on Lync 2013 clients.</span></span> <span data-ttu-id="d7190-109">H-p 影片支援更多範圍的解析度和畫面播放速率，並改善影片的可伸縮性。</span><span class="sxs-lookup"><span data-stu-id="d7190-109">H.264 video supports a greater range of resolutions and frame rates, and improves video scalability.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d7190-110">Lync Server 2013 仍支援與舊版 Lync 互通性的 VC1 編解碼器。</span><span class="sxs-lookup"><span data-stu-id="d7190-110">Lync Server 2013 still supports the VC1 codec for interoperability with previous versions of Lync.</span></span> <span data-ttu-id="d7190-111">如需有關新視頻編解碼器的詳細資訊和背景資訊，請參閱李明 Schertz 的博客文章：「Lync 2013 中的<A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A>影片互通性」。</span><span class="sxs-lookup"><span data-stu-id="d7190-111">For details and background information about the new video codec, see Jeff Schertz's Blog article, "Video Interoperability in Lync 2013," at <A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A>.</span></span>

    
    </div>

<span data-ttu-id="d7190-112">本節說明如何在 Lync Server 2013 中管理影片的頻寬，以及如何設定視頻功能。</span><span class="sxs-lookup"><span data-stu-id="d7190-112">This section describes how to manage bandwidth for video in Lync Server 2013 and how to configure video features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d7190-113">本節內容</span><span class="sxs-lookup"><span data-stu-id="d7190-113">In This Section</span></span>

  - [<span data-ttu-id="d7190-114">在 Lync Server 2013 中設定影片頻寬</span><span class="sxs-lookup"><span data-stu-id="d7190-114">Configuring video bandwidth in Lync Server 2013</span></span>](lync-server-2013-configuring-video-bandwidth.md)

  - [<span data-ttu-id="d7190-115">在 Lync Server 2013 中設定圖庫視圖</span><span class="sxs-lookup"><span data-stu-id="d7190-115">Configuring Gallery View in Lync Server 2013</span></span>](lync-server-2013-configuring-gallery-view.md)

  - [<span data-ttu-id="d7190-116">設定 Lync Server 2013 的影片範例案例</span><span class="sxs-lookup"><span data-stu-id="d7190-116">Configuring video example scenarios for Lync Server 2013</span></span>](lync-server-2013-configuring-video-example-scenarios.md)

  - [<span data-ttu-id="d7190-117">Lync Server 2013 中的視訊會議的互通性考慮</span><span class="sxs-lookup"><span data-stu-id="d7190-117">Interoperability considerations for video conferencing in Lync Server 2013</span></span>](lync-server-2013-interoperability-considerations-for-video-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

