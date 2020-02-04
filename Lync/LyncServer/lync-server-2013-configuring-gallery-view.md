---
title: Lync Server 2013：設定圖庫視圖
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
ms.openlocfilehash: 06054e1728245c87e8bf35419d3890f4e379543a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728843"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-gallery-view-in-lync-server-2013"></a><span data-ttu-id="28a30-102">在 Lync Server 2013 中設定圖庫視圖</span><span class="sxs-lookup"><span data-stu-id="28a30-102">Configuring Gallery View in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28a30-103">_**主題上次修改日期：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="28a30-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="28a30-104">在 Lync Server 2013 中，您可以在會議原則中設定圖庫視圖視訊會議。</span><span class="sxs-lookup"><span data-stu-id="28a30-104">In Lync Server 2013, you configure Gallery View video conferencing in conferencing policy.</span></span> <span data-ttu-id="28a30-105">預設會開啟圖庫視圖。</span><span class="sxs-lookup"><span data-stu-id="28a30-105">Gallery View is turned on by default.</span></span> <span data-ttu-id="28a30-106">如果您不想允許圖庫視圖，或只想允許部分使用者查看，您必須關閉會議原則中的功能。</span><span class="sxs-lookup"><span data-stu-id="28a30-106">If you do not want to allow Gallery View, or want to allow it for only some users, you need to turn off the feature in conferencing policy.</span></span>

<span data-ttu-id="28a30-107">在會議參與者的影片無法使用時，如果您要部署高解析度相片（Lync Server 2013 中的新功能），可以增強使用者的圖庫視圖體驗。</span><span class="sxs-lookup"><span data-stu-id="28a30-107">When a conference participant's video is not available, the users' Gallery View experience can be enhanced if you deploy high-resolution photos, a new feature in Lync Server 2013.</span></span> <span data-ttu-id="28a30-108">高解析度相片可為儲存在 Active Directory 網域服務中的較小、有限的解析度連絡人相片提供替代方案。</span><span class="sxs-lookup"><span data-stu-id="28a30-108">High-resolution photos provide an alternative to the smaller, limited resolution contact photos stored in Active Directory Domain Services.</span></span> <span data-ttu-id="28a30-109">高解析度相片是儲存在使用者的 Exchange 2013 信箱中，因此需要您整合 Lync Server 2013 與 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="28a30-109">High-resolution photos are stored in a user's Exchange 2013 mailbox, and, therefore, require you to integrate Lync Server 2013 with Exchange 2013.</span></span> <span data-ttu-id="28a30-110">如需詳細資訊，請參閱 NextHop 博客文章：「整合 Exchange 2013 和 Lync Server 2013」 [http://go.microsoft.com/fwlink/p/?LinkId=260987](http://go.microsoft.com/fwlink/p/?linkid=260987)。</span><span class="sxs-lookup"><span data-stu-id="28a30-110">For details, see the NextHop blog article, "Integrating Exchange 2013 and Lync Server 2013," at [http://go.microsoft.com/fwlink/p/?LinkId=260987](http://go.microsoft.com/fwlink/p/?linkid=260987).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="28a30-111">每個博客及其 URL 的內容可能會變更，恕不另行通知。</span><span class="sxs-lookup"><span data-stu-id="28a30-111">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<span data-ttu-id="28a30-112">您可以使用 Lync Server 2013 [控制台] 或使用下列其中一個 Cmdlet 來查看或修改圖庫視圖參數：</span><span class="sxs-lookup"><span data-stu-id="28a30-112">You can view or modify the Gallery View parameters by using Lync Server 2013 Control Panel or by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="28a30-113">**Get-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="28a30-113">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="28a30-114">**Set-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="28a30-114">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="28a30-115">**New-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="28a30-115">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="28a30-116">使用下列會議原則設定來設定圖庫視圖：</span><span class="sxs-lookup"><span data-stu-id="28a30-116">Configure Gallery View with the following conferencing policy settings:</span></span>

  - <span data-ttu-id="28a30-117">**AllowMultiview**   此參數可控制是否允許使用者組織圖庫觀看視訊會議。</span><span class="sxs-lookup"><span data-stu-id="28a30-117">**AllowMultiview**   This parameter controls whether a user is allowed to organize Gallery View video conferences.</span></span> <span data-ttu-id="28a30-118">此參數適用于使用者建立的排程與臨時會議。</span><span class="sxs-lookup"><span data-stu-id="28a30-118">This parameter applies to scheduled and ad-hoc meetings created by the user.</span></span>
    
    <span data-ttu-id="28a30-119">示例</span><span class="sxs-lookup"><span data-stu-id="28a30-119">Examples:</span></span>
    
      - <span data-ttu-id="28a30-120">此參數針對使用者 A （在 Lync Server 2013 池上是託管的使用者 A）設定為 True。</span><span class="sxs-lookup"><span data-stu-id="28a30-120">This parameter is set to True for User A, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="28a30-121">依使用者 A 組織的會議，可讓使用者加入並接收多個視頻串流。</span><span class="sxs-lookup"><span data-stu-id="28a30-121">Meetings organized by User A enable users to join and receive multiple video streams.</span></span>
    
      - <span data-ttu-id="28a30-122">此參數針對使用者 B （在 Lync Server 2013 池上是託管的使用者 B）設定為 False。</span><span class="sxs-lookup"><span data-stu-id="28a30-122">This parameter is set to False for User B, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="28a30-123">依使用者 B 組織的會議都有一個類似于 Lync Server 2010 所提供之視訊會議體驗的單一視頻資料流程。</span><span class="sxs-lookup"><span data-stu-id="28a30-123">Meetings organized by User B have a single video stream that is similar to the video conference experience provided by Lync Server 2010.</span></span>
    
    <span data-ttu-id="28a30-124">這個參數決定誰可以組織允許多個視頻串流的會議。</span><span class="sxs-lookup"><span data-stu-id="28a30-124">This parameter determines who can organize meetings that allow multiple video streams.</span></span> <span data-ttu-id="28a30-125">在會議中，允許多個視頻資料流程的參與者可能會根據自己的許可權接收多個視頻資料流程（請參閱 EnableMultiviewJoin 參數的描述）。</span><span class="sxs-lookup"><span data-stu-id="28a30-125">Participants in meetings that allow multiple video streams may or may not be allowed to receive multiple video streams, based on their individual permissions (see the description for the EnableMultiviewJoin parameter).</span></span>

  - <span data-ttu-id="28a30-126">**EnableMultiviewJoin**   此參數可控制會議中的參與者是否在允許的會議中接收圖庫 View 影片體驗。</span><span class="sxs-lookup"><span data-stu-id="28a30-126">**EnableMultiviewJoin**   This parameter controls whether a participant in a meeting receives the Gallery View video experience in meetings that allow it.</span></span> <span data-ttu-id="28a30-127">這個參數控制使用者在參與的任何會議中的體驗。</span><span class="sxs-lookup"><span data-stu-id="28a30-127">This parameter controls the user's experience in any meeting in which he or she participates.</span></span>
    
    <span data-ttu-id="28a30-128">示例</span><span class="sxs-lookup"><span data-stu-id="28a30-128">Examples:</span></span>
    
      - <span data-ttu-id="28a30-129">此參數會針對使用者 C 設定為 True。使用者 C 會在參與由使用者 A 組織或啟動的會議時，收到多個視頻資料流程。使用者 C 會收到一個類似于 Lync Server 2010 所提供的視訊會議體驗的單一視頻資料流程參與由使用者 B 組織或啟動的會議。</span><span class="sxs-lookup"><span data-stu-id="28a30-129">This parameter is set to True for User C. User C can receive multiple video streams when participating in a meeting organized or started by User A. User C receives a single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in a meeting organized or started by User B.</span></span>
    
      - <span data-ttu-id="28a30-130">此參數針對使用者 D 設定為 False。當您參與由使用者 A 或使用者 B 組織的任何會議時，使用者 D 會收到與 Lync Server 2010 所提供的視訊會議體驗類似的單一視頻資料流程。</span><span class="sxs-lookup"><span data-stu-id="28a30-130">This parameter is set to False for User D. User D receives single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in any meeting organized by User A or User B.</span></span>

<span data-ttu-id="28a30-131">下列程式是使用 Lync Server 管理命令介面來啟用圖庫查看視訊會議的範例。</span><span class="sxs-lookup"><span data-stu-id="28a30-131">The following procedure is an example of using Lync Server Management Shell to enable Gallery View video conferencing.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a><span data-ttu-id="28a30-132">修改圖庫的會議原則查看視訊會議</span><span class="sxs-lookup"><span data-stu-id="28a30-132">To modify conferencing policy for Gallery View video conferencing</span></span>

1.  <span data-ttu-id="28a30-133">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="28a30-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="28a30-134">在命令列上，執行下列 Cmdlet 來編輯會議原則：</span><span class="sxs-lookup"><span data-stu-id="28a30-134">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>

