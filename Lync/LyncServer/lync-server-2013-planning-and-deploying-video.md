---
title: Lync Server 2013： 規劃及部署影片
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
ms.openlocfilehash: 3938ca54278f71d8f51ecacfe3fdc3278ec59679
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050255"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-and-deploying-video-in-lync-server-2013"></a><span data-ttu-id="e9fbb-102">規劃及部署 Lync Server 2013 中的影片</span><span class="sxs-lookup"><span data-stu-id="e9fbb-102">Planning and deploying video in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9fbb-103">_**主題上次修改日期：** 2012年-10-02_</span><span class="sxs-lookup"><span data-stu-id="e9fbb-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e9fbb-104">Lync Server 2013 引進下列新視訊功能：</span><span class="sxs-lookup"><span data-stu-id="e9fbb-104">Lync Server 2013 introduces the following new video features:</span></span>

  - <span data-ttu-id="e9fbb-105">**HD 視訊**   使用者可體驗全彩高畫質 (HD) (也就是 1920 x 1080) 在雙方通話與多方會議中。</span><span class="sxs-lookup"><span data-stu-id="e9fbb-105">**HD video**   Users can experience resolutions up to full high definition (HD) (that is, 1920 x 1080) in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="e9fbb-106">**圖庫檢視**   在視訊會議中，有兩個以上的人員，使用者可以看到參與者的視訊。</span><span class="sxs-lookup"><span data-stu-id="e9fbb-106">**Gallery View**   In video conferences that have more than two people, users can see videos of participants in the conference.</span></span> <span data-ttu-id="e9fbb-107">如果會議有五個以上的參與者，最活躍的參與者的視訊會出現在第一列，並將相片顯示其他參與者。</span><span class="sxs-lookup"><span data-stu-id="e9fbb-107">If the conference has more than five participants, video of only the most active participants appears in the top row, and a photo appears for the other participants.</span></span>

  - <span data-ttu-id="e9fbb-108">**H.264 視訊**   H.264 視訊轉碼器現在是編碼影片 Lync 2013 用戶端上的預設值。</span><span class="sxs-lookup"><span data-stu-id="e9fbb-108">**H.264 video**   The H.264 video codec is now the default for encoding video on Lync 2013 clients.</span></span> <span data-ttu-id="e9fbb-109">H.264 視訊支援更大範圍的解析度和畫面播放速率，並提升了視訊延展性。</span><span class="sxs-lookup"><span data-stu-id="e9fbb-109">H.264 video supports a greater range of resolutions and frame rates, and improves video scalability.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9fbb-110">Lync Server 2013 仍然支援與舊版 Lync 互通性的 VC1 轉碼器。</span><span class="sxs-lookup"><span data-stu-id="e9fbb-110">Lync Server 2013 still supports the VC1 codec for interoperability with previous versions of Lync.</span></span> <span data-ttu-id="e9fbb-111">如需詳細資訊及新的視訊轉碼器的背景資訊，請參閱 Jeff Schertz 部落格文章: 「 視訊的互通性在 Lync 2013，「 在<A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A>。</span><span class="sxs-lookup"><span data-stu-id="e9fbb-111">For details and background information about the new video codec, see Jeff Schertz's Blog article, "Video Interoperability in Lync 2013," at <A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A>.</span></span>

    
    </div>

<span data-ttu-id="e9fbb-112">本節說明如何管理 Lync Server 2013 中的視訊頻寬，以及如何設定視訊功能。</span><span class="sxs-lookup"><span data-stu-id="e9fbb-112">This section describes how to manage bandwidth for video in Lync Server 2013 and how to configure video features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e9fbb-113">本章節內容</span><span class="sxs-lookup"><span data-stu-id="e9fbb-113">In This Section</span></span>

  - [<span data-ttu-id="e9fbb-114">在 Lync Server 2013 中設定視訊頻寬</span><span class="sxs-lookup"><span data-stu-id="e9fbb-114">Configuring video bandwidth in Lync Server 2013</span></span>](lync-server-2013-configuring-video-bandwidth.md)

  - [<span data-ttu-id="e9fbb-115">在 Lync Server 2013 中設定圖庫檢視</span><span class="sxs-lookup"><span data-stu-id="e9fbb-115">Configuring Gallery View in Lync Server 2013</span></span>](lync-server-2013-configuring-gallery-view.md)

  - [<span data-ttu-id="e9fbb-116">Lync Server 2013 設定視訊範例案例</span><span class="sxs-lookup"><span data-stu-id="e9fbb-116">Configuring video example scenarios for Lync Server 2013</span></span>](lync-server-2013-configuring-video-example-scenarios.md)

  - [<span data-ttu-id="e9fbb-117">Lync Server 2013 中的視訊會議的互通性考量</span><span class="sxs-lookup"><span data-stu-id="e9fbb-117">Interoperability considerations for video conferencing in Lync Server 2013</span></span>](lync-server-2013-interoperability-considerations-for-video-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

