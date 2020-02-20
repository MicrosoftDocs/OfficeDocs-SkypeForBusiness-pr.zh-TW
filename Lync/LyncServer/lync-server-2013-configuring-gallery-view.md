---
title: Lync Server 2013： 設定圖庫檢視
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
ms.openlocfilehash: 02c13f2b1fa312394edfaba01ecd05179f86a0c9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151423"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-gallery-view-in-lync-server-2013"></a><span data-ttu-id="3e1e0-102">在 Lync Server 2013 中設定圖庫檢視</span><span class="sxs-lookup"><span data-stu-id="3e1e0-102">Configuring Gallery View in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e1e0-103">_**主題上次修改日期：** 2012年-10-30_</span><span class="sxs-lookup"><span data-stu-id="3e1e0-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="3e1e0-104">在 Lync Server 2013 中，您可以設定圖庫檢視 」 視訊會議的會議原則。</span><span class="sxs-lookup"><span data-stu-id="3e1e0-104">In Lync Server 2013, you configure Gallery View video conferencing in conferencing policy.</span></span> <span data-ttu-id="3e1e0-105">「圖庫檢視」預設為開啟狀態。</span><span class="sxs-lookup"><span data-stu-id="3e1e0-105">Gallery View is turned on by default.</span></span> <span data-ttu-id="3e1e0-106">如果您不想允許「圖庫檢視」，或只想針對部分使用者允許「圖庫檢視」，必須在會議原則中關閉此功能。</span><span class="sxs-lookup"><span data-stu-id="3e1e0-106">If you do not want to allow Gallery View, or want to allow it for only some users, you need to turn off the feature in conferencing policy.</span></span>

<span data-ttu-id="3e1e0-107">會議參與者的視訊無法使用時，如果您將部署高解析度相片，Lync Server 2013 中的新功能，可以被增強使用者的圖庫檢視經驗。</span><span class="sxs-lookup"><span data-stu-id="3e1e0-107">When a conference participant's video is not available, the users' Gallery View experience can be enhanced if you deploy high-resolution photos, a new feature in Lync Server 2013.</span></span> <span data-ttu-id="3e1e0-108">高解析度相片提供較小，有限的解析度連絡人相片儲存在 Active Directory 網域服務中的替代方案。</span><span class="sxs-lookup"><span data-stu-id="3e1e0-108">High-resolution photos provide an alternative to the smaller, limited resolution contact photos stored in Active Directory Domain Services.</span></span> <span data-ttu-id="3e1e0-109">高解析度相片儲存在使用者的 Exchange 2013 信箱，且，因此，需要您整合 Lync Server 2013 和 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="3e1e0-109">High-resolution photos are stored in a user's Exchange 2013 mailbox, and, therefore, require you to integrate Lync Server 2013 with Exchange 2013.</span></span> <span data-ttu-id="3e1e0-110">如需詳細資訊，請參閱 NextHop 部落格文章，「 整合 Exchange 2013 和 Lync Server 2013 中，「 [https://go.microsoft.com/fwlink/p/?LinkId=260987](https://go.microsoft.com/fwlink/p/?linkid=260987)。</span><span class="sxs-lookup"><span data-stu-id="3e1e0-110">For details, see the NextHop blog article, "Integrating Exchange 2013 and Lync Server 2013," at [https://go.microsoft.com/fwlink/p/?LinkId=260987](https://go.microsoft.com/fwlink/p/?linkid=260987).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3e1e0-111">每個網誌的內容及其 URL 如有變更，恕不另行通知。</span><span class="sxs-lookup"><span data-stu-id="3e1e0-111">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<span data-ttu-id="3e1e0-112">您可以檢視或修改圖庫檢視 」 參數，藉由使用 Lync Server 2013 控制台，或使用下列其中一個下列 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3e1e0-112">You can view or modify the Gallery View parameters by using Lync Server 2013 Control Panel or by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="3e1e0-113">**Get-csconferencingpolicy**</span><span class="sxs-lookup"><span data-stu-id="3e1e0-113">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="3e1e0-114">**Set-csmonitoringserver**</span><span class="sxs-lookup"><span data-stu-id="3e1e0-114">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="3e1e0-115">**New-csconferencingpolicy**</span><span class="sxs-lookup"><span data-stu-id="3e1e0-115">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="3e1e0-116">請使用下列會議原則設定來設定「圖庫檢視」：</span><span class="sxs-lookup"><span data-stu-id="3e1e0-116">Configure Gallery View with the following conferencing policy settings:</span></span>

  - <span data-ttu-id="3e1e0-117">**AllowMultiview**   此參數會控制是否允許使用者組織圖庫檢視視訊會議。</span><span class="sxs-lookup"><span data-stu-id="3e1e0-117">**AllowMultiview**   This parameter controls whether a user is allowed to organize Gallery View video conferences.</span></span> <span data-ttu-id="3e1e0-118">此參數適用於排程會議及使用者建立的臨時會議。</span><span class="sxs-lookup"><span data-stu-id="3e1e0-118">This parameter applies to scheduled and ad-hoc meetings created by the user.</span></span>
    
    <span data-ttu-id="3e1e0-119">範例:</span><span class="sxs-lookup"><span data-stu-id="3e1e0-119">Examples:</span></span>
    
      - <span data-ttu-id="3e1e0-120">此參數設為 True 的使用者 A，隸屬於 Lync Server 2013 集區中。</span><span class="sxs-lookup"><span data-stu-id="3e1e0-120">This parameter is set to True for User A, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="3e1e0-121">由使用者 A 召集的會議可讓使用者加入及接收多個視訊資料流。</span><span class="sxs-lookup"><span data-stu-id="3e1e0-121">Meetings organized by User A enable users to join and receive multiple video streams.</span></span>
    
      - <span data-ttu-id="3e1e0-122">此參數設為 False，使用者 b，隸屬於 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="3e1e0-122">This parameter is set to False for User B, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="3e1e0-123">依使用者 B 的會議有單一的視訊資料流，類似於 Lync Server 2010 所提供的視訊會議經驗。</span><span class="sxs-lookup"><span data-stu-id="3e1e0-123">Meetings organized by User B have a single video stream that is similar to the video conference experience provided by Lync Server 2010.</span></span>
    
    <span data-ttu-id="3e1e0-p106">此參數決定誰可以召集允許多個視訊資料流的會議。允許多個視訊資料流的會議的參與者是否可以接收多個視訊資料流，要視他們的個人權限而定 (請參閱 EnableMultiviewJoin 參數描述)。</span><span class="sxs-lookup"><span data-stu-id="3e1e0-p106">This parameter determines who can organize meetings that allow multiple video streams. Participants in meetings that allow multiple video streams may or may not be allowed to receive multiple video streams, based on their individual permissions (see the description for the EnableMultiviewJoin parameter).</span></span>

  - <span data-ttu-id="3e1e0-126">**EnableMultiviewJoin**   此參數會控制會議的參與者是否在會議中允許其接收圖庫檢視視訊體驗。</span><span class="sxs-lookup"><span data-stu-id="3e1e0-126">**EnableMultiviewJoin**   This parameter controls whether a participant in a meeting receives the Gallery View video experience in meetings that allow it.</span></span> <span data-ttu-id="3e1e0-127">此參數控制使用者在所有參與的會議中的體驗。</span><span class="sxs-lookup"><span data-stu-id="3e1e0-127">This parameter controls the user's experience in any meeting in which he or she participates.</span></span>
    
    <span data-ttu-id="3e1e0-128">範例:</span><span class="sxs-lookup"><span data-stu-id="3e1e0-128">Examples:</span></span>
    
      - <span data-ttu-id="3e1e0-129">此參數設為 True，針對 C 使用者 C.使用者可以接收多個視訊資料流生於參與會議主辦或由使用者 A C 使用者啟動單一的視訊資料流，類似於 Lync Server 2010 所提供的視訊會議經驗時參與會議主辦或啟動使用者 b。</span><span class="sxs-lookup"><span data-stu-id="3e1e0-129">This parameter is set to True for User C. User C can receive multiple video streams when participating in a meeting organized or started by User A. User C receives a single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in a meeting organized or started by User B.</span></span>
    
      - <span data-ttu-id="3e1e0-130">此參數設為 False 的使用者 d 使用者 D 收到單一視訊資料流，類似於參與任何會議組織時，Lync Server 2010 所提供的視訊會議經驗的使用者或使用者 b。</span><span class="sxs-lookup"><span data-stu-id="3e1e0-130">This parameter is set to False for User D. User D receives single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in any meeting organized by User A or User B.</span></span>

<span data-ttu-id="3e1e0-131">下列程序是使用 Lync Server 管理命令介面來啟用圖庫檢視 」 視訊會議的範例。</span><span class="sxs-lookup"><span data-stu-id="3e1e0-131">The following procedure is an example of using Lync Server Management Shell to enable Gallery View video conferencing.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a><span data-ttu-id="3e1e0-132">修改「圖庫檢視」視訊會議的會議原則</span><span class="sxs-lookup"><span data-stu-id="3e1e0-132">To modify conferencing policy for Gallery View video conferencing</span></span>

1.  <span data-ttu-id="3e1e0-133">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="3e1e0-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="3e1e0-134">在命令列上執行下列 Cmdlet 以編輯會議原則：</span><span class="sxs-lookup"><span data-stu-id="3e1e0-134">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>

