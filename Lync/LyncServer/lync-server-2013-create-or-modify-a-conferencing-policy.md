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
ms.openlocfilehash: 522f1d1240e73775ae1f0976556b882ba00fe1d3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180070"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-conferencing-policy-in-lync-server-2013"></a><span data-ttu-id="7b5a3-102">在 Lync Server 2013 中建立或修改會議原則</span><span class="sxs-lookup"><span data-stu-id="7b5a3-102">Create or modify a conferencing policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b5a3-103">_**主題上次修改日期：** 2013-02-07_</span><span class="sxs-lookup"><span data-stu-id="7b5a3-103">_**Topic Last Modified:** 2013-02-07_</span></span>

<span data-ttu-id="7b5a3-104">請遵循下列步驟建立使用者層級或網站層級會議原則。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-104">Follow these steps to create a user-level or a site-level conferencing policy.</span></span> <span data-ttu-id="7b5a3-105">如需如何將使用者層級原則指派給使用者的詳細資訊，請參閱[在 Lync Server 2013 中指派每個使用者的會議原則](lync-server-2013-assign-a-per-user-conferencing-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-105">For details about how to assign a user-level policy to a user, see [Assign a per-user conferencing policy in Lync Server 2013](lync-server-2013-assign-a-per-user-conferencing-policy.md).</span></span> <span data-ttu-id="7b5a3-106">如需所有可用之會議原則設定的清單，請參閱[Lync Server 2013 的會議原則設定參考](lync-server-2013-conferencing-policy-settings-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-106">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>

## <a name="to-create-a-new-user-or-site-policy"></a><span data-ttu-id="7b5a3-107">若要建立新的使用者或網站原則</span><span class="sxs-lookup"><span data-stu-id="7b5a3-107">To create a new user or site policy</span></span>

1.  <span data-ttu-id="7b5a3-108">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7b5a3-109">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7b5a3-110">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7b5a3-111">請在左導覽列中按一下 **[會議]**，然後按一下 **[會議原則]**。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-111">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="7b5a3-112">按一下 **[新增]**，然後執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="7b5a3-112">Click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="7b5a3-113">若要建立使用者層級原則，請按一下 [**使用者原則**]。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-113">To create a user-level policy, click **User policy**.</span></span> <span data-ttu-id="7b5a3-114">在 [**新的會議原則**] 的 [**名稱**] 中，輸入原則的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-114">In **New Conferencing Policy**, in **Name**, type a descriptive name for the policy.</span></span>
    
      - <span data-ttu-id="7b5a3-115">若要建立網站層級原則，請按一下 [**網站原則**]。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-115">To create a site-level policy, click **Site policy**.</span></span> <span data-ttu-id="7b5a3-116">在 [**選取網站**] 搜尋欄位中，輸入您要建立原則的網站名稱全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-116">In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy.</span></span> <span data-ttu-id="7b5a3-117">在網站清單中，按一下您想要的網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-117">In the list of sites, click the site that you want, and then click **OK**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="7b5a3-118">網站名稱會成為會議原則名稱，且無法變更。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-118">The site name becomes the conferencing policy name, and it cannot be changed.</span></span>

        
        </div>

5.  <span data-ttu-id="7b5a3-119">在 [**描述**] 中，輸入原則的描述。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-119">In **Description**, type a description for the policy.</span></span>

6.  <span data-ttu-id="7b5a3-p105">在 **[召集人原則]** 下方的 **[最大會議大小]** 中，輸入您想要允許的會議使用者數量上限。最大會議大小預設為 250。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-p105">Under **Organizer policy**, in **Maximum meeting size**, type the maximum number of users that you want to allow at a meeting. By default, the maximum meeting size is 250.</span></span>

7.  <span data-ttu-id="7b5a3-122">若要防止使用者邀請匿名使用者參加會議，請清除 **[允許參與者邀請匿名使用者]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-122">To prevent users from inviting anonymous users to meetings, clear the **Allow participants to invite anonymous users** check box.</span></span> <span data-ttu-id="7b5a3-123">匿名使用者是指不具備組織之 Active Directory 網域服務之認證的使用者，因此未進行驗證。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-123">Anonymous users are users who do not have credentials in your organization’s Active Directory Domain Services and who, therefore, are not authenticated.</span></span> <span data-ttu-id="7b5a3-124">使用者預設可以邀請匿名使用者參加會議。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-124">By default, users can invite anonymous users to meetings.</span></span>

8.  <span data-ttu-id="7b5a3-125">在 **[錄製]** 中，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="7b5a3-125">In **Recording**, do one of the following:</span></span>
    
      - <span data-ttu-id="7b5a3-p107">若要防止參與者錄製會議內容，按一下 **[無]**。此設定為預設值。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-p107">To prevent participants from recording meetings, click **None**. This is the default setting.</span></span>
    
      - <span data-ttu-id="7b5a3-128">若要允許參與者錄製會議內容，按一下 **[啟用錄製]**。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-128">To allow participants to record meetings, click **Enable recording**.</span></span>

9.  <span data-ttu-id="7b5a3-p108">若要允許外部參與者錄製會議內容，選取 **[允許同盟和匿名參與者錄製]** 核取方塊。預設值會防止外部參與者錄製會議內容。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-p108">To allow external participants to record meetings, select the **Allow federated and anonymous participants to record** check box. The default is to prevent external participants from recording meetings.</span></span>

10. <span data-ttu-id="7b5a3-131">在 **[音訊/視訊]** 中，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="7b5a3-131">In **Audio/video**, do one of the following:</span></span>
    
      - <span data-ttu-id="7b5a3-132">若要防止使用音訊及視訊，按一下 **[無]**。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-132">To prevent the use of audio and video, click **None**.</span></span>
    
      - <span data-ttu-id="7b5a3-133">若要允許使用音訊 (但不允許視訊)，按一下 **[啟用 IP 音訊]**。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-133">To allow the use of audio but not video, click **Enable IP audio**.</span></span>
    
      - <span data-ttu-id="7b5a3-p109">若要允許使用音訊與視訊，按一下 **[啟用 IP 音訊/視訊]**。此設定為預設值。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-p109">To allow the use of audio and video, click **Enable IP audio/video**. This is the default setting.</span></span>

11. <span data-ttu-id="7b5a3-136">如果您在 **[音訊/視訊]** 中選擇允許使用音訊，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="7b5a3-136">If you chose to allow the use of audio in **Audio/video**, do the following:</span></span>
    
      - <span data-ttu-id="7b5a3-p110">若要防止使用者藉由撥入電話來加入會議，請清除 **[啟用 PSTN 電話撥入式會議]** 核取方塊。根據預設，使用者可以使用公用交換電話網路 (PSTN) 來撥入會議。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-p110">To prevent users from joining the meeting by dialing in, clear the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
      - <span data-ttu-id="7b5a3-p111">如果您允許使用者撥入會議，而且想要允許未經驗證 (匿名) 的使用者透過撥出電話來加入會議，則選取 **[允許匿名參與者撥出]** 核取方塊。透過撥出電話，會議伺服器會呼叫使用者，這時使用者可以接聽電話以加入會議。根據預設，匿名使用者無法透過撥出電話方式來加入會議。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-p111">If you allow users to dial in to meetings and you want to allow unauthenticated (anonymous) users to join a meeting by using dial out phoning, select the **Allow anonymous participants to dial out** check box. With dial-out phoning, the conference server calls the user, and the user answers the phone to join the meeting. By default, anonymous users cannot join a meeting by using dial-out phoning.</span></span>

12. <span data-ttu-id="7b5a3-142">如果您選擇允許在**音訊/視頻**中使用影片，請選取 [**允許多個影片資料流程**]。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-142">If you chose to allow the use of video in **Audio/video**, check **Allow multiple video streams** .</span></span>

13. <span data-ttu-id="7b5a3-143">在 **[資料共同作業]** 中，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="7b5a3-143">In **Data collaboration**, do one of the following:</span></span>
    
      - <span data-ttu-id="7b5a3-144">若要防止進行資料共同作業，按一下 **[無]**。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-144">To prevent data collaboration, click **None**.</span></span>
    
      - <span data-ttu-id="7b5a3-p112">若要允許進行資料共同作業，按一下 **[啟用資料共同作業]**。此設定為預設值。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-p112">To allow data collaboration, click **Enable data collaboration**. This is the default setting.</span></span>

14. <span data-ttu-id="7b5a3-147">如果您在 **[資料共同作業]** 中選擇允許資料共同作業，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="7b5a3-147">If you chose to allow data collaboration in **Data collaboration**, do the following:</span></span>
    
      - <span data-ttu-id="7b5a3-p113">若要防止外部下載，請清除 **[允許同盟和匿名參與者下載內容]** 核取方塊。根據預設，外部使用者可以下載內容。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-p113">To prevent external downloads, clear the **Allow federated and anonymous participants to download content** check box. By default, external users can download content.</span></span>
    
      - <span data-ttu-id="7b5a3-p114">若要防止進行檔案傳輸，請清除 **[允許參與者傳輸檔案]** 核取方塊。根據預設，使用者可以傳輸檔案。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-p114">To prevent file transfers, clear the **Allow participants to transfer files** check box. By default, users can transfer files.</span></span>
    
      - <span data-ttu-id="7b5a3-152">若要防止使用註釋，請清除 **[啟用註釋]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-152">To prevent the use of annotations, clear the **Enable annotations** check box.</span></span> <span data-ttu-id="7b5a3-153">若要在 shard PowerPoint 簡報中使用批註，請清除 [**啟用 PowerPoint 批註**]。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-153">To the use of annotations in shard PowerPoint presentations, clear the **Enable PowerPoint annotations**.</span></span> <span data-ttu-id="7b5a3-154">預設允許使用註釋。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-154">By default, annotations are allowed.</span></span>
    
      - <span data-ttu-id="7b5a3-p116">若要防止使用投票，請清除 **[啟用投票]** 核取方塊。預設允許使用投票。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-p116">To prevent the use of polls, clear the **Enable polls** check box. By default, polls are allowed.</span></span>

15. <span data-ttu-id="7b5a3-157">在 **[應用程式共用]** 中，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="7b5a3-157">In **Application sharing**, do one of the following:</span></span>
    
      - <span data-ttu-id="7b5a3-158">若要防止使用應用程式共用，按一下 **[停用應用程式共用]**。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-158">To prevent the use of application sharing, click **Disable application sharing**.</span></span>
    
      - <span data-ttu-id="7b5a3-p117">若要允許使用應用程式共用，按一下 **[啟用應用程式共用]**。此設定為預設值。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-p117">To allow the use of application sharing, click **Enable application sharing**. This is the default setting.</span></span>

16. <span data-ttu-id="7b5a3-161">如果您在 **[應用程式共同]** 中選擇允許應用程式共同，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="7b5a3-161">If you chose to allow application sharing in **Application sharing**, do the following:</span></span>
    
      - <span data-ttu-id="7b5a3-p118">若要防止會議參與者掌控應用程式共用功能，請清除 **[允許參與者取得控制權]** 核取方塊。根據預設，參與者可以掌控應用程式共用功能。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-p118">To prevent meeting participants from taking control of application sharing, clear the **Allow participants to take control** check box. By default, participants can take control of application sharing.</span></span>
    
      - <span data-ttu-id="7b5a3-p119">如果您選擇允許會議參與者掌控應用程式共用功能，請選取 **[允許同盟和匿名參與者取得控制權]** 核取方塊，以允許外部使用者掌控應用程式共用功能。根據預設，外部使用者無法掌控應用程式共用功能。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-p119">If you chose to allow meeting participants to take control of application sharing, select the **Allow federated and anonymous participants to take control** check box to allow external users to take control of application sharing. By default, external users cannot take control of application sharing.</span></span>

17. <span data-ttu-id="7b5a3-166">在 **[參與者原則]** 下方，執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="7b5a3-166">Under **Participant policy**, do one of the following:</span></span>
    
      - <span data-ttu-id="7b5a3-167">若要同時防止使用應用程式共用與桌面共用功能，按一下 **[停用應用程式和桌面共用]**。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-167">To prevent both application sharing and desktop sharing, click **Disable application and desktop sharing**.</span></span>
    
      - <span data-ttu-id="7b5a3-168">若要允許使用應用程式共用，但防止使用桌面共用，則按一下 **[啟用應用程式共用]**。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-168">To allow application sharing but not desktop sharing, click **Enable application sharing**.</span></span>
    
      - <span data-ttu-id="7b5a3-p120">若要同時允許使用應用程式共用與桌面共用功能，按一下 **[啟用應用程式和桌面共用]**。此設定為預設值。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-p120">To allow both application sharing and desktop sharing, click **Enable application and desktop sharing**. This is the default setting.</span></span>

18. <span data-ttu-id="7b5a3-p121">若要防止點對點檔案傳輸，請清除 **[啟用點對點檔案傳輸]** 核取方塊。預設允許進行點對點檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-p121">To prevent peer-to-peer file transfers, clear the **Enable peer-to-peer file transfer** check box. By default, peer-to-peer file transfers are allowed.</span></span>

19. <span data-ttu-id="7b5a3-p122">若要允許進行點對點錄製作業，選取 **[啟用點對點錄製]** 核取方塊。預設不允許進行點對點錄製。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-p122">To allow peer-to-peer recording, select the **Enable peer-to-peer recording** check box. By default, peer-to-peer recording is not allowed.</span></span>

20. <span data-ttu-id="7b5a3-175">若要允許參與者與多個影片資料流程加入，請選取 [**啟用參與者以多個影片加入**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-175">To allow participants to join with multiple video streams, select the **Enable participants to join with multiple video streams** check box.</span></span> <span data-ttu-id="7b5a3-176">根據預設，允許多個影片資料流程。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-176">By default, multiple video streams are allowed.</span></span>

21. <span data-ttu-id="7b5a3-177">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-177">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-user-or-site-policy"></a><span data-ttu-id="7b5a3-178">修改現有的使用者或網站原則</span><span class="sxs-lookup"><span data-stu-id="7b5a3-178">To modify an existing user or site policy</span></span>

1.  <span data-ttu-id="7b5a3-179">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-179">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7b5a3-180">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-180">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7b5a3-181">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-181">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7b5a3-182">請在左導覽列中按一下 **[會議]**，然後按一下 **[會議原則]**。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-182">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="7b5a3-183">在會議原則清單中，按一下您要變更的原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-183">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="7b5a3-184">在 [**編輯會議原則**] 中，修改原則名稱以外的任何原則設定，但無法修改。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-184">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>

6.  <span data-ttu-id="7b5a3-185">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="7b5a3-185">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

