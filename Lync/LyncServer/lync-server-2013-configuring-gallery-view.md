---
title: Lync Server 2013：設定圖庫 View
description: Lync Server 2013：設定圖庫 View。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Gallery View
ms:assetid: 4a609178-47d8-4682-ac8d-29f882801924
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204871(v=OCS.15)
ms:contentKeyID: 48184069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2aec2f1e3c7bff9a3736f40584a29880978b9daa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575919"
---
# <a name="configuring-gallery-view-in-lync-server-2013"></a><span data-ttu-id="702b6-103">在 Lync Server 2013 中設定圖庫視圖</span><span class="sxs-lookup"><span data-stu-id="702b6-103">Configuring Gallery View in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="702b6-104">_**主題上次修改日期：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="702b6-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="702b6-105">在 [Lync Server 2013] 中，您可以在會議原則中設定圖庫 View video 會議。</span><span class="sxs-lookup"><span data-stu-id="702b6-105">In Lync Server 2013, you configure Gallery View video conferencing in conferencing policy.</span></span> <span data-ttu-id="702b6-106">「圖庫檢視」預設為開啟狀態。</span><span class="sxs-lookup"><span data-stu-id="702b6-106">Gallery View is turned on by default.</span></span> <span data-ttu-id="702b6-107">如果您不想允許「圖庫檢視」，或只想針對部分使用者允許「圖庫檢視」，必須在會議原則中關閉此功能。</span><span class="sxs-lookup"><span data-stu-id="702b6-107">If you do not want to allow Gallery View, or want to allow it for only some users, you need to turn off the feature in conferencing policy.</span></span>

<span data-ttu-id="702b6-108">當會議參與者的影片無法使用時，如果您部署高解析度的相片（Lync Server 2013 中的新功能），則使用者的圖庫 View 體驗可以增強。</span><span class="sxs-lookup"><span data-stu-id="702b6-108">When a conference participant's video is not available, the users' Gallery View experience can be enhanced if you deploy high-resolution photos, a new feature in Lync Server 2013.</span></span> <span data-ttu-id="702b6-109">高解析度相片為儲存在 Active Directory 網域服務中的較小、有限解析度的連絡人相片提供替代方案。</span><span class="sxs-lookup"><span data-stu-id="702b6-109">High-resolution photos provide an alternative to the smaller, limited resolution contact photos stored in Active Directory Domain Services.</span></span> <span data-ttu-id="702b6-110">高解析度相片儲存在使用者的 Exchange 2013 信箱中，因此需要您將 Lync Server 2013 與 Exchange 2013 整合。</span><span class="sxs-lookup"><span data-stu-id="702b6-110">High-resolution photos are stored in a user's Exchange 2013 mailbox, and, therefore, require you to integrate Lync Server 2013 with Exchange 2013.</span></span> <span data-ttu-id="702b6-111">如需詳細資訊，請參閱《整合 Exchange 2013 和 Lync Server 2013 》的 NextHop 博客文章 [https://go.microsoft.com/fwlink/p/?LinkId=260987](https://go.microsoft.com/fwlink/p/?linkid=260987) 。</span><span class="sxs-lookup"><span data-stu-id="702b6-111">For details, see the NextHop blog article, "Integrating Exchange 2013 and Lync Server 2013," at [https://go.microsoft.com/fwlink/p/?LinkId=260987](https://go.microsoft.com/fwlink/p/?linkid=260987).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="702b6-112">每個網誌的內容及其 URL 如有變更，恕不另行通知。</span><span class="sxs-lookup"><span data-stu-id="702b6-112">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<span data-ttu-id="702b6-113">您可以使用 Lync Server 2013 控制台或使用下列其中一個 Cmdlet，查看或修改圖庫 View 參數：</span><span class="sxs-lookup"><span data-stu-id="702b6-113">You can view or modify the Gallery View parameters by using Lync Server 2013 Control Panel or by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="702b6-114">**Get-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="702b6-114">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="702b6-115">**Set-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="702b6-115">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="702b6-116">**New-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="702b6-116">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="702b6-117">請使用下列會議原則設定來設定「圖庫檢視」：</span><span class="sxs-lookup"><span data-stu-id="702b6-117">Configure Gallery View with the following conferencing policy settings:</span></span>

  - <span data-ttu-id="702b6-118">**AllowMultiview**    此參數會控制是否允許使用者組織圖庫 View 錄影會議。</span><span class="sxs-lookup"><span data-stu-id="702b6-118">**AllowMultiview**   This parameter controls whether a user is allowed to organize Gallery View video conferences.</span></span> <span data-ttu-id="702b6-119">此參數適用於排程會議及使用者建立的臨時會議。</span><span class="sxs-lookup"><span data-stu-id="702b6-119">This parameter applies to scheduled and ad-hoc meetings created by the user.</span></span>
    
    <span data-ttu-id="702b6-120">範例：</span><span class="sxs-lookup"><span data-stu-id="702b6-120">Examples:</span></span>
    
      - <span data-ttu-id="702b6-121">此參數會設定為 True 的使用者 A，其位於 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="702b6-121">This parameter is set to True for User A, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="702b6-122">由使用者 A 召集的會議可讓使用者加入及接收多個視訊資料流。</span><span class="sxs-lookup"><span data-stu-id="702b6-122">Meetings organized by User A enable users to join and receive multiple video streams.</span></span>
    
      - <span data-ttu-id="702b6-123">此參數會為使用者 B （位於 Lync Server 2013 集區）設定為 False。</span><span class="sxs-lookup"><span data-stu-id="702b6-123">This parameter is set to False for User B, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="702b6-124">使用者 B 所組織的會議具有單一的視頻資料流程，類似于 Lync Server 2010 提供的影片會議體驗。</span><span class="sxs-lookup"><span data-stu-id="702b6-124">Meetings organized by User B have a single video stream that is similar to the video conference experience provided by Lync Server 2010.</span></span>
    
    <span data-ttu-id="702b6-p106">此參數決定誰可以召集允許多個視訊資料流的會議。允許多個視訊資料流的會議的參與者是否可以接收多個視訊資料流，要視他們的個人權限而定 (請參閱 EnableMultiviewJoin 參數描述)。</span><span class="sxs-lookup"><span data-stu-id="702b6-p106">This parameter determines who can organize meetings that allow multiple video streams. Participants in meetings that allow multiple video streams may or may not be allowed to receive multiple video streams, based on their individual permissions (see the description for the EnableMultiviewJoin parameter).</span></span>

  - <span data-ttu-id="702b6-127">**EnableMultiviewJoin**    此參數會控制會議中的參與者是否會在允許會議的會議中，接收影片庫 View 影片體驗。</span><span class="sxs-lookup"><span data-stu-id="702b6-127">**EnableMultiviewJoin**   This parameter controls whether a participant in a meeting receives the Gallery View video experience in meetings that allow it.</span></span> <span data-ttu-id="702b6-128">此參數控制使用者在所有參與的會議中的體驗。</span><span class="sxs-lookup"><span data-stu-id="702b6-128">This parameter controls the user's experience in any meeting in which he or she participates.</span></span>
    
    <span data-ttu-id="702b6-129">範例：</span><span class="sxs-lookup"><span data-stu-id="702b6-129">Examples:</span></span>
    
      - <span data-ttu-id="702b6-130">此參數會為使用者 C 設定為 True。使用者 C 可在參與使用者 A 組織或啟動的會議時，收到多個影片。使用者 C 接收單一的影片，類似于在參與使用者 B 組織或啟動會議時，Lync Server 2010 所提供的影片會議體驗。</span><span class="sxs-lookup"><span data-stu-id="702b6-130">This parameter is set to True for User C. User C can receive multiple video streams when participating in a meeting organized or started by User A. User C receives a single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in a meeting organized or started by User B.</span></span>
    
      - <span data-ttu-id="702b6-131">此參數會為使用者 D 設定為 False。當參與使用者 A 或使用者 B 所組織的任何會議時，使用者 D 會收到單一影片，其類似于 Lync Server 2010 所提供的影片會議體驗。</span><span class="sxs-lookup"><span data-stu-id="702b6-131">This parameter is set to False for User D. User D receives single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in any meeting organized by User A or User B.</span></span>

<span data-ttu-id="702b6-132">下列程式是使用 Lync Server 管理命令介面來啟用圖庫 View video 會議的範例。</span><span class="sxs-lookup"><span data-stu-id="702b6-132">The following procedure is an example of using Lync Server Management Shell to enable Gallery View video conferencing.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a><span data-ttu-id="702b6-133">修改「圖庫檢視」視訊會議的會議原則</span><span class="sxs-lookup"><span data-stu-id="702b6-133">To modify conferencing policy for Gallery View video conferencing</span></span>

1.  <span data-ttu-id="702b6-134">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="702b6-134">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="702b6-135">在命令列上執行下列 Cmdlet 以編輯會議原則：</span><span class="sxs-lookup"><span data-stu-id="702b6-135">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>

