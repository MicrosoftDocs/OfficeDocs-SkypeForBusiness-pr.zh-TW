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
ms.openlocfilehash: bf5eca9118c9f4706aa209dc1e2db1b3dbbed358
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519810"
---
# <a name="planning-and-deploying-video-in-lync-server-2013"></a><span data-ttu-id="45677-102">在 Lync Server 2013 中規劃及部署影片</span><span class="sxs-lookup"><span data-stu-id="45677-102">Planning and deploying video in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45677-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="45677-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="45677-104">Lync Server 2013 引進下列新的影片功能：</span><span class="sxs-lookup"><span data-stu-id="45677-104">Lync Server 2013 introduces the following new video features:</span></span>

  - <span data-ttu-id="45677-105">**HD 影片**    在雙方通話和多方會議中，使用者可以經歷最高定義 (HD)  (也就是 1920 x 1080) 的解析度。</span><span class="sxs-lookup"><span data-stu-id="45677-105">**HD video**   Users can experience resolutions up to full high definition (HD) (that is, 1920 x 1080) in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="45677-106">**圖庫視圖**    在包含超過兩個人的影片會議中，使用者可以查看會議中的參與者影片。</span><span class="sxs-lookup"><span data-stu-id="45677-106">**Gallery View**   In video conferences that have more than two people, users can see videos of participants in the conference.</span></span> <span data-ttu-id="45677-107">如果會議的參與者超過五位，最上層的參與者只會顯示最上層的參與者的影片，而且會顯示其他參與者的相片。</span><span class="sxs-lookup"><span data-stu-id="45677-107">If the conference has more than five participants, video of only the most active participants appears in the top row, and a photo appears for the other participants.</span></span>

  - <span data-ttu-id="45677-108">上**的264影片**    現在，在 Lync 2013 用戶端上的編碼影片的預設值為 H-p 影片。</span><span class="sxs-lookup"><span data-stu-id="45677-108">**H.264 video**   The H.264 video codec is now the default for encoding video on Lync 2013 clients.</span></span> <span data-ttu-id="45677-109">H.264 視訊支援更大範圍的解析度和畫面播放速率，並提升了視訊延展性。</span><span class="sxs-lookup"><span data-stu-id="45677-109">H.264 video supports a greater range of resolutions and frame rates, and improves video scalability.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="45677-110">Lync Server 2013 仍然支援 VC1 編解碼器，以與舊版 Lync 進行交互操作。</span><span class="sxs-lookup"><span data-stu-id="45677-110">Lync Server 2013 still supports the VC1 codec for interoperability with previous versions of Lync.</span></span> <span data-ttu-id="45677-111">如需有關新影片編解碼器的詳細資訊及背景資訊，請參閱 Jeff Schertz 的博客文章：「Lync 2013 的影片互通性」，網址為 <A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A> 。</span><span class="sxs-lookup"><span data-stu-id="45677-111">For details and background information about the new video codec, see Jeff Schertz's Blog article, "Video Interoperability in Lync 2013," at <A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A>.</span></span>

    
    </div>

<span data-ttu-id="45677-112">本節說明如何在 Lync Server 2013 中管理影片的頻寬，以及如何設定影片功能。</span><span class="sxs-lookup"><span data-stu-id="45677-112">This section describes how to manage bandwidth for video in Lync Server 2013 and how to configure video features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="45677-113">本章節內容</span><span class="sxs-lookup"><span data-stu-id="45677-113">In This Section</span></span>

  - [<span data-ttu-id="45677-114">在 Lync Server 2013 中設定影片頻寬</span><span class="sxs-lookup"><span data-stu-id="45677-114">Configuring video bandwidth in Lync Server 2013</span></span>](lync-server-2013-configuring-video-bandwidth.md)

  - [<span data-ttu-id="45677-115">在 Lync Server 2013 中設定圖庫視圖</span><span class="sxs-lookup"><span data-stu-id="45677-115">Configuring Gallery View in Lync Server 2013</span></span>](lync-server-2013-configuring-gallery-view.md)

  - [<span data-ttu-id="45677-116">設定 Lync Server 2013 的影片範例案例</span><span class="sxs-lookup"><span data-stu-id="45677-116">Configuring video example scenarios for Lync Server 2013</span></span>](lync-server-2013-configuring-video-example-scenarios.md)

  - [<span data-ttu-id="45677-117">Lync Server 2013 中的視訊會議的互通性考慮</span><span class="sxs-lookup"><span data-stu-id="45677-117">Interoperability considerations for video conferencing in Lync Server 2013</span></span>](lync-server-2013-interoperability-considerations-for-video-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

