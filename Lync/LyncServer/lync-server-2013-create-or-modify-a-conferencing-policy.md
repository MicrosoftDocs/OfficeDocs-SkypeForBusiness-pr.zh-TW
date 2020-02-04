---
title: Lync Server 2013：建立或修改會議原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a conferencing policy
ms:assetid: e2974030-2c0a-4634-91e8-93f4e2d674d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721910(v=OCS.15)
ms:contentKeyID: 49733844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f3dd712b94838382f6022de888383c0f47bee6e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758087"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-conferencing-policy-in-lync-server-2013"></a><span data-ttu-id="65ee2-102">在 Lync Server 2013 中建立或修改會議原則</span><span class="sxs-lookup"><span data-stu-id="65ee2-102">Create or modify a conferencing policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65ee2-103">_**主題上次修改日期：** 2013-02-07_</span><span class="sxs-lookup"><span data-stu-id="65ee2-103">_**Topic Last Modified:** 2013-02-07_</span></span>

<span data-ttu-id="65ee2-104">請依照這些步驟來建立使用者層級會議原則或網站層級會議原則。</span><span class="sxs-lookup"><span data-stu-id="65ee2-104">Follow these steps to create a user-level or a site-level conferencing policy.</span></span> <span data-ttu-id="65ee2-105">如需如何將使用者層級原則指派給使用者的詳細資料，請參閱[在 Lync Server 2013 中指派每使用者會議原則](lync-server-2013-assign-a-per-user-conferencing-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="65ee2-105">For details about how to assign a user-level policy to a user, see [Assign a per-user conferencing policy in Lync Server 2013](lync-server-2013-assign-a-per-user-conferencing-policy.md).</span></span> <span data-ttu-id="65ee2-106">如需所有可用會議原則設定的清單，請參閱[Lync Server 2013 的會議原則設定參考](lync-server-2013-conferencing-policy-settings-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="65ee2-106">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>

## <a name="to-create-a-new-user-or-site-policy"></a><span data-ttu-id="65ee2-107">若要建立新的使用者或網站原則</span><span class="sxs-lookup"><span data-stu-id="65ee2-107">To create a new user or site policy</span></span>

1.  <span data-ttu-id="65ee2-108">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="65ee2-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="65ee2-109">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="65ee2-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="65ee2-110">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="65ee2-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="65ee2-111">在左側導覽列中，按一下 [**會議**]，然後按一下 [**會議原則**]。</span><span class="sxs-lookup"><span data-stu-id="65ee2-111">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="65ee2-112">按一下 [**新增**]，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="65ee2-112">Click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="65ee2-113">若要建立使用者層級原則，按一下 [**使用者原則**]。</span><span class="sxs-lookup"><span data-stu-id="65ee2-113">To create a user-level policy, click **User policy**.</span></span> <span data-ttu-id="65ee2-114">在 [**新會議原則**] 的 [**名稱**] 中，輸入原則的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="65ee2-114">In **New Conferencing Policy**, in **Name**, type a descriptive name for the policy.</span></span>
    
      - <span data-ttu-id="65ee2-115">若要建立網站層級原則，按一下 [**網站原則**]。</span><span class="sxs-lookup"><span data-stu-id="65ee2-115">To create a site-level policy, click **Site policy**.</span></span> <span data-ttu-id="65ee2-116">在 [**選取網站**搜尋] 欄位中，輸入您要為其建立原則之網站的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="65ee2-116">In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy.</span></span> <span data-ttu-id="65ee2-117">在網站清單中，按一下您想要的網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="65ee2-117">In the list of sites, click the site that you want, and then click **OK**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="65ee2-118">網站名稱會變成會議原則名稱，且無法變更。</span><span class="sxs-lookup"><span data-stu-id="65ee2-118">The site name becomes the conferencing policy name, and it cannot be changed.</span></span>

        
        </div>

5.  <span data-ttu-id="65ee2-119">在 [**描述**] 中，輸入原則的描述。</span><span class="sxs-lookup"><span data-stu-id="65ee2-119">In **Description**, type a description for the policy.</span></span>

6.  <span data-ttu-id="65ee2-120">在 [**召集人原則**] 底下的 [**最大會議大小**] 中，輸入您要允許會議的使用者數目上限。</span><span class="sxs-lookup"><span data-stu-id="65ee2-120">Under **Organizer policy**, in **Maximum meeting size**, type the maximum number of users that you want to allow at a meeting.</span></span> <span data-ttu-id="65ee2-121">根據預設，會議最大大小是250。</span><span class="sxs-lookup"><span data-stu-id="65ee2-121">By default, the maximum meeting size is 250.</span></span>

7.  <span data-ttu-id="65ee2-122">若要防止使用者邀請匿名使用者加入會議，請清除 [**允許參與者邀請匿名使用者**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="65ee2-122">To prevent users from inviting anonymous users to meetings, clear the **Allow participants to invite anonymous users** check box.</span></span> <span data-ttu-id="65ee2-123">匿名使用者是在貴組織的 Active Directory 網域服務中沒有認證的使用者，因此沒有經過驗證的使用者。</span><span class="sxs-lookup"><span data-stu-id="65ee2-123">Anonymous users are users who do not have credentials in your organization’s Active Directory Domain Services and who, therefore, are not authenticated.</span></span> <span data-ttu-id="65ee2-124">根據預設，使用者可以邀請匿名使用者加入會議。</span><span class="sxs-lookup"><span data-stu-id="65ee2-124">By default, users can invite anonymous users to meetings.</span></span>

8.  <span data-ttu-id="65ee2-125">在 [**錄製**] 中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="65ee2-125">In **Recording**, do one of the following:</span></span>
    
      - <span data-ttu-id="65ee2-126">若要防止參與者錄製會議，請按一下 [**無**]。</span><span class="sxs-lookup"><span data-stu-id="65ee2-126">To prevent participants from recording meetings, click **None**.</span></span> <span data-ttu-id="65ee2-127">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="65ee2-127">This is the default setting.</span></span>
    
      - <span data-ttu-id="65ee2-128">若要允許參與者錄製會議，請按一下 [**啟用錄製**]。</span><span class="sxs-lookup"><span data-stu-id="65ee2-128">To allow participants to record meetings, click **Enable recording**.</span></span>

9.  <span data-ttu-id="65ee2-129">若要允許外部參與者錄製會議，請選取 [**允許聯盟和匿名參與者進行記錄**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="65ee2-129">To allow external participants to record meetings, select the **Allow federated and anonymous participants to record** check box.</span></span> <span data-ttu-id="65ee2-130">預設是要防止外部參與者錄製會議。</span><span class="sxs-lookup"><span data-stu-id="65ee2-130">The default is to prevent external participants from recording meetings.</span></span>

10. <span data-ttu-id="65ee2-131">在 [**音訊/影片**] 中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="65ee2-131">In **Audio/video**, do one of the following:</span></span>
    
      - <span data-ttu-id="65ee2-132">若要避免使用音訊和影片，請按一下 [**無**]。</span><span class="sxs-lookup"><span data-stu-id="65ee2-132">To prevent the use of audio and video, click **None**.</span></span>
    
      - <span data-ttu-id="65ee2-133">若要允許使用音訊而不是影片，請按一下 [**啟用 IP 音訊**]。</span><span class="sxs-lookup"><span data-stu-id="65ee2-133">To allow the use of audio but not video, click **Enable IP audio**.</span></span>
    
      - <span data-ttu-id="65ee2-134">若要允許使用音訊和影片，請按一下 [**啟用 IP 音訊/視頻**]。</span><span class="sxs-lookup"><span data-stu-id="65ee2-134">To allow the use of audio and video, click **Enable IP audio/video**.</span></span> <span data-ttu-id="65ee2-135">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="65ee2-135">This is the default setting.</span></span>

11. <span data-ttu-id="65ee2-136">如果您選擇允許在**音訊/視頻**中使用音訊，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="65ee2-136">If you chose to allow the use of audio in **Audio/video**, do the following:</span></span>
    
      - <span data-ttu-id="65ee2-137">若要防止使用者透過撥號加入會議，請清除 [**啟用 PSTN 電話撥入式會議**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="65ee2-137">To prevent users from joining the meeting by dialing in, clear the **Enable PSTN dial-in conferencing** check box.</span></span> <span data-ttu-id="65ee2-138">根據預設，使用者可以使用公開交換電話網絡（PSTN）撥入會議。</span><span class="sxs-lookup"><span data-stu-id="65ee2-138">By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
      - <span data-ttu-id="65ee2-139">如果您允許使用者撥入會議，而您想要允許未經驗證（匿名）使用者使用 [撥出 phoning] 加入會議，請選取 [**允許匿名參與者撥出**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="65ee2-139">If you allow users to dial in to meetings and you want to allow unauthenticated (anonymous) users to join a meeting by using dial out phoning, select the **Allow anonymous participants to dial out** check box.</span></span> <span data-ttu-id="65ee2-140">使用撥出 phoning，會議服務器就會呼叫使用者，而使用者會接聽電話來加入會議。</span><span class="sxs-lookup"><span data-stu-id="65ee2-140">With dial-out phoning, the conference server calls the user, and the user answers the phone to join the meeting.</span></span> <span data-ttu-id="65ee2-141">根據預設，匿名使用者無法使用撥出 phoning 加入會議。</span><span class="sxs-lookup"><span data-stu-id="65ee2-141">By default, anonymous users cannot join a meeting by using dial-out phoning.</span></span>

12. <span data-ttu-id="65ee2-142">如果您選擇允許在**音訊/視頻**中使用影片，請核取 [**允許多個影片串流**]。</span><span class="sxs-lookup"><span data-stu-id="65ee2-142">If you chose to allow the use of video in **Audio/video**, check **Allow multiple video streams** .</span></span>

13. <span data-ttu-id="65ee2-143">在 [**資料**共同作業] 中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="65ee2-143">In **Data collaboration**, do one of the following:</span></span>
    
      - <span data-ttu-id="65ee2-144">若要防止資料共同作業，請按一下 [**無**]。</span><span class="sxs-lookup"><span data-stu-id="65ee2-144">To prevent data collaboration, click **None**.</span></span>
    
      - <span data-ttu-id="65ee2-145">若要允許資料共同作業，請按一下 [**啟用資料**共同作業]。</span><span class="sxs-lookup"><span data-stu-id="65ee2-145">To allow data collaboration, click **Enable data collaboration**.</span></span> <span data-ttu-id="65ee2-146">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="65ee2-146">This is the default setting.</span></span>

14. <span data-ttu-id="65ee2-147">如果您在**資料**共同作業中選擇允許資料共同作業，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="65ee2-147">If you chose to allow data collaboration in **Data collaboration**, do the following:</span></span>
    
      - <span data-ttu-id="65ee2-148">若要防止外部下載，請清除 [**允許聯盟和匿名參與者下載內容**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="65ee2-148">To prevent external downloads, clear the **Allow federated and anonymous participants to download content** check box.</span></span> <span data-ttu-id="65ee2-149">根據預設，外部使用者可以下載內容。</span><span class="sxs-lookup"><span data-stu-id="65ee2-149">By default, external users can download content.</span></span>
    
      - <span data-ttu-id="65ee2-150">若要防止檔案傳輸，請清除 [**允許參與者傳送**檔案] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="65ee2-150">To prevent file transfers, clear the **Allow participants to transfer files** check box.</span></span> <span data-ttu-id="65ee2-151">根據預設，使用者可以傳送檔案。</span><span class="sxs-lookup"><span data-stu-id="65ee2-151">By default, users can transfer files.</span></span>
    
      - <span data-ttu-id="65ee2-152">若要避免使用標注，請清除 [**啟用批註**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="65ee2-152">To prevent the use of annotations, clear the **Enable annotations** check box.</span></span> <span data-ttu-id="65ee2-153">若要在 shard PowerPoint 簡報中使用注釋，請清除 [**啟用 powerpoint 注釋**]。</span><span class="sxs-lookup"><span data-stu-id="65ee2-153">To the use of annotations in shard PowerPoint presentations, clear the **Enable PowerPoint annotations**.</span></span> <span data-ttu-id="65ee2-154">根據預設，允許使用批註。</span><span class="sxs-lookup"><span data-stu-id="65ee2-154">By default, annotations are allowed.</span></span>
    
      - <span data-ttu-id="65ee2-155">若要避免使用投票，請清除 [**啟用輪詢**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="65ee2-155">To prevent the use of polls, clear the **Enable polls** check box.</span></span> <span data-ttu-id="65ee2-156">根據預設，允許投票。</span><span class="sxs-lookup"><span data-stu-id="65ee2-156">By default, polls are allowed.</span></span>

15. <span data-ttu-id="65ee2-157">在 [**應用程式共用**] 中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="65ee2-157">In **Application sharing**, do one of the following:</span></span>
    
      - <span data-ttu-id="65ee2-158">若要避免使用應用程式共用，請按一下 [**停用應用程式共用**]。</span><span class="sxs-lookup"><span data-stu-id="65ee2-158">To prevent the use of application sharing, click **Disable application sharing**.</span></span>
    
      - <span data-ttu-id="65ee2-159">若要允許使用應用程式共用，請按一下 [**啟用應用程式共用**]。</span><span class="sxs-lookup"><span data-stu-id="65ee2-159">To allow the use of application sharing, click **Enable application sharing**.</span></span> <span data-ttu-id="65ee2-160">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="65ee2-160">This is the default setting.</span></span>

16. <span data-ttu-id="65ee2-161">如果您在 [**應用程式共用**] 中選擇 [允許應用程式共用]，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="65ee2-161">If you chose to allow application sharing in **Application sharing**, do the following:</span></span>
    
      - <span data-ttu-id="65ee2-162">若要避免會議參與者控制應用程式共用，請清除 [**允許參與者取得控制權**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="65ee2-162">To prevent meeting participants from taking control of application sharing, clear the **Allow participants to take control** check box.</span></span> <span data-ttu-id="65ee2-163">根據預設，參與者可以取得應用程式共用的控制權。</span><span class="sxs-lookup"><span data-stu-id="65ee2-163">By default, participants can take control of application sharing.</span></span>
    
      - <span data-ttu-id="65ee2-164">如果您選擇讓會議參與者控制應用程式共用，請選取 [**允許聯盟和匿名參與者取得控制權**] 核取方塊，以允許外部使用者控制應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="65ee2-164">If you chose to allow meeting participants to take control of application sharing, select the **Allow federated and anonymous participants to take control** check box to allow external users to take control of application sharing.</span></span> <span data-ttu-id="65ee2-165">根據預設，外部使用者無法取得應用程式共用的控制權。</span><span class="sxs-lookup"><span data-stu-id="65ee2-165">By default, external users cannot take control of application sharing.</span></span>

17. <span data-ttu-id="65ee2-166">在 [**參與者原則**] 底下，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="65ee2-166">Under **Participant policy**, do one of the following:</span></span>
    
      - <span data-ttu-id="65ee2-167">若要防止應用程式共用與桌面共用，請按一下 [**停用應用程式與桌面共用**]。</span><span class="sxs-lookup"><span data-stu-id="65ee2-167">To prevent both application sharing and desktop sharing, click **Disable application and desktop sharing**.</span></span>
    
      - <span data-ttu-id="65ee2-168">若要允許應用程式共用，但不允許桌面共用，請按一下 [**啟用應用程式共用**]。</span><span class="sxs-lookup"><span data-stu-id="65ee2-168">To allow application sharing but not desktop sharing, click **Enable application sharing**.</span></span>
    
      - <span data-ttu-id="65ee2-169">若要允許應用程式共用與桌面共用，請按一下 [**啟用應用程式和桌面**共用]。</span><span class="sxs-lookup"><span data-stu-id="65ee2-169">To allow both application sharing and desktop sharing, click **Enable application and desktop sharing**.</span></span> <span data-ttu-id="65ee2-170">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="65ee2-170">This is the default setting.</span></span>

18. <span data-ttu-id="65ee2-171">若要防止對等檔案傳輸，請清除 [**啟用對等檔案傳輸**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="65ee2-171">To prevent peer-to-peer file transfers, clear the **Enable peer-to-peer file transfer** check box.</span></span> <span data-ttu-id="65ee2-172">根據預設，允許對等檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="65ee2-172">By default, peer-to-peer file transfers are allowed.</span></span>

19. <span data-ttu-id="65ee2-173">若要允許對等錄製，請選取 [**啟用對等錄製**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="65ee2-173">To allow peer-to-peer recording, select the **Enable peer-to-peer recording** check box.</span></span> <span data-ttu-id="65ee2-174">根據預設，不允許對等錄製。</span><span class="sxs-lookup"><span data-stu-id="65ee2-174">By default, peer-to-peer recording is not allowed.</span></span>

20. <span data-ttu-id="65ee2-175">若要允許參與者加入多個視頻資料流程，請選取 [**允許參與者加入多個視頻資料流程**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="65ee2-175">To allow participants to join with multiple video streams, select the **Enable participants to join with multiple video streams** check box.</span></span> <span data-ttu-id="65ee2-176">根據預設，允許多個視頻資料流程。</span><span class="sxs-lookup"><span data-stu-id="65ee2-176">By default, multiple video streams are allowed.</span></span>

21. <span data-ttu-id="65ee2-177">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="65ee2-177">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-user-or-site-policy"></a><span data-ttu-id="65ee2-178">修改現有的使用者或網站原則</span><span class="sxs-lookup"><span data-stu-id="65ee2-178">To modify an existing user or site policy</span></span>

1.  <span data-ttu-id="65ee2-179">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="65ee2-179">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="65ee2-180">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="65ee2-180">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="65ee2-181">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="65ee2-181">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="65ee2-182">在左側導覽列中，按一下 [**會議**]，然後按一下 [**會議原則**]。</span><span class="sxs-lookup"><span data-stu-id="65ee2-182">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="65ee2-183">在會議原則清單中，按一下您要變更的原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="65ee2-183">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="65ee2-184">在 [**編輯會議原則**] 中，修改任何原則設定，除了不能修改的原則名稱以外。</span><span class="sxs-lookup"><span data-stu-id="65ee2-184">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>

6.  <span data-ttu-id="65ee2-185">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="65ee2-185">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

