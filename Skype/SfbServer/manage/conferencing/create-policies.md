---
title: 在商務用 Skype Server 中建立會議原則
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8c685326-8356-4075-bf95-32324b16ef81
description: 摘要：瞭解如何在商務用 Skype Server 中建立會議原則。
ms.openlocfilehash: 81fcaa15c7b12b499c833ac012ef6d999da683ad
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119522"
---
# <a name="create-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="bf5c4-103">在商務用 Skype Server 中建立會議原則</span><span class="sxs-lookup"><span data-stu-id="bf5c4-103">Create conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="bf5c4-104">**摘要：** 瞭解如何在商務用 Skype Server 中建立會議原則。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-104">**Summary:** Learn how to create conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="bf5c4-105">您可以使用商務用 Skype Server 控制台或使用商務用 Skype Server 管理命令介面來建立會議原則。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-105">You can create conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="create-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="bf5c4-106">使用商務用 Skype Server 控制台建立會議原則</span><span class="sxs-lookup"><span data-stu-id="bf5c4-106">Create conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="bf5c4-107">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="bf5c4-108">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="bf5c4-109">在左導覽列中，按一下 [ **會議**]，然後按一下 [ **會議原則**]。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="bf5c4-110">按一下 **[新增]**，然後執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="bf5c4-110">Click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="bf5c4-111">若要建立使用者層級原則，請按一下 [ **使用者原則**]。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-111">To create a user-level policy, click **User policy**.</span></span> <span data-ttu-id="bf5c4-112">在 [ **新的會議原則**] 的 [ **名稱**] 中，輸入原則的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-112">In **New Conferencing Policy**, in **Name**, type a descriptive name for the policy.</span></span>
    
   - <span data-ttu-id="bf5c4-113">若要建立網站層級原則，請按一下 [ **網站原則**]。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-113">To create a site-level policy, click **Site policy**.</span></span> <span data-ttu-id="bf5c4-114">在 [ **選取網站** ] 搜尋欄位中，輸入您要建立原則的網站名稱全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-114">In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy.</span></span> <span data-ttu-id="bf5c4-115">在網站清單中，按一下您想要的網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-115">In the list of sites, click the site that you want, and then click **OK**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="bf5c4-116">網站名稱會成為會議原則名稱;無法變更。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-116">The site name becomes the conferencing policy name; it cannot be changed.</span></span> 
  
5. <span data-ttu-id="bf5c4-117">在 [ **描述**] 中，輸入原則的描述。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-117">In **Description**, type a description for the policy.</span></span>
    
6. <span data-ttu-id="bf5c4-p103">在 **[召集人原則]** 下方的 **[最大會議大小]** 中，輸入您想要允許的會議使用者數量上限。最大會議大小預設為 250。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-p103">Under **Organizer policy**, in **Maximum meeting size**, type the maximum number of users that you want to allow at a meeting. By default, the maximum meeting size is 250.</span></span>
    
7. <span data-ttu-id="bf5c4-120">若要防止使用者邀請匿名使用者參加會議，請清除 **[允許參與者邀請匿名使用者]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-120">To prevent users from inviting anonymous users to meetings, clear the **Allow participants to invite anonymous users** check box.</span></span> <span data-ttu-id="bf5c4-121">匿名使用者是指不具備組織之 Active Directory 網域服務之認證的使用者，因此未進行驗證。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-121">Anonymous users are users who do not have credentials in your organization's Active Directory Domain Services and who, therefore, are not authenticated.</span></span> <span data-ttu-id="bf5c4-122">使用者預設可以邀請匿名使用者參加會議。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-122">By default, users can invite anonymous users to meetings.</span></span>
    
8. <span data-ttu-id="bf5c4-123">在 **[錄製]** 中，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="bf5c4-123">In **Recording**, do one of the following:</span></span>
    
   - <span data-ttu-id="bf5c4-p105">若要防止參與者錄製會議內容，按一下 **[無]**。此設定為預設值。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-p105">To prevent participants from recording meetings, click **None**. This is the default setting.</span></span>
    
   - <span data-ttu-id="bf5c4-126">若要允許參與者錄製會議內容，按一下 **[啟用錄製]**。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-126">To allow participants to record meetings, click **Enable recording**.</span></span>
    
9. <span data-ttu-id="bf5c4-p106">若要允許外部參與者錄製會議內容，選取 **[允許同盟和匿名參與者錄製]** 核取方塊。預設值會防止外部參與者錄製會議內容。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-p106">To allow external participants to record meetings, select the **Allow federated and anonymous participants to record** check box. The default is to prevent external participants from recording meetings.</span></span>
    
10. <span data-ttu-id="bf5c4-129">在 **[音訊/視訊]** 中，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="bf5c4-129">In **Audio/video**, do one of the following:</span></span>
    
    - <span data-ttu-id="bf5c4-130">若要防止使用音訊及視訊，按一下 **[無]**。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-130">To prevent the use of audio and video, click **None**.</span></span>
    
    - <span data-ttu-id="bf5c4-131">若要允許使用音訊 (但不允許視訊)，按一下 **[啟用 IP 音訊]**。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-131">To allow the use of audio but not video, click **Enable IP audio**.</span></span>
    
    - <span data-ttu-id="bf5c4-p107">若要允許使用音訊與視訊，按一下 **[啟用 IP 音訊/視訊]**。此設定為預設值。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-p107">To allow the use of audio and video, click **Enable IP audio/video**. This is the default setting.</span></span>
    
11. <span data-ttu-id="bf5c4-134">如果您在 **[音訊/視訊]** 中選擇允許使用音訊，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="bf5c4-134">If you chose to allow the use of audio in **Audio/video**, do the following:</span></span>
    
    - <span data-ttu-id="bf5c4-p108">若要防止使用者藉由撥入電話來加入會議，請清除 **[啟用 PSTN 電話撥入式會議]** 核取方塊。根據預設，使用者可以使用公用交換電話網路 (PSTN) 來撥入會議。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-p108">To prevent users from joining the meeting by dialing in, clear the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
    - <span data-ttu-id="bf5c4-p109">如果您允許使用者撥入會議，而且想要允許未經驗證 (匿名) 的使用者透過撥出電話來加入會議，則選取 **[允許匿名參與者撥出]** 核取方塊。透過撥出電話，會議伺服器會呼叫使用者，這時使用者可以接聽電話以加入會議。根據預設，匿名使用者無法透過撥出電話方式來加入會議。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-p109">If you allow users to dial in to meetings and you want to allow unauthenticated (anonymous) users to join a meeting by using dial out phoning, select the **Allow anonymous participants to dial out** check box. With dial-out phoning, the conference server calls the user, and the user answers the phone to join the meeting. By default, anonymous users cannot join a meeting by using dial-out phoning.</span></span>
    
12. <span data-ttu-id="bf5c4-140">如果您選擇允許在 **音訊/視頻** 中使用影片，請選取 [ **允許多個影片資料流程**]。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-140">If you chose to allow the use of video in **Audio/video**, check **Allow multiple video streams**.</span></span>
    
13. <span data-ttu-id="bf5c4-141">在 **[資料共同作業]** 中，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="bf5c4-141">In **Data collaboration**, do one of the following:</span></span>
    
    - <span data-ttu-id="bf5c4-142">若要防止進行資料共同作業，按一下 **[無]**。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-142">To prevent data collaboration, click **None**.</span></span>
    
    - <span data-ttu-id="bf5c4-p110">若要允許進行資料共同作業，按一下 **[啟用資料共同作業]**。此設定為預設值。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-p110">To allow data collaboration, click **Enable data collaboration**. This is the default setting.</span></span>
    
14. <span data-ttu-id="bf5c4-145">如果您在 **[資料共同作業]** 中選擇允許資料共同作業，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="bf5c4-145">If you chose to allow data collaboration in **Data collaboration**, do the following:</span></span>
    
    - <span data-ttu-id="bf5c4-p111">若要防止外部下載，請清除 **[允許同盟和匿名參與者下載內容]** 核取方塊。根據預設，外部使用者可以下載內容。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-p111">To prevent external downloads, clear the **Allow federated and anonymous participants to download content** check box. By default, external users can download content.</span></span>
    
    - <span data-ttu-id="bf5c4-p112">若要防止進行檔案傳輸，請清除 **[允許參與者傳輸檔案]** 核取方塊。根據預設，使用者可以傳輸檔案。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-p112">To prevent file transfers, clear the **Allow participants to transfer files** check box. By default, users can transfer files.</span></span>
    
    - <span data-ttu-id="bf5c4-150">若要防止使用註釋，請清除 **[啟用註釋]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-150">To prevent the use of annotations, clear the **Enable annotations** check box.</span></span> <span data-ttu-id="bf5c4-151">若要使用共用 PowerPoint 簡報中的批註，請清除 [ **啟用 PowerPoint 批註**]。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-151">To the use of annotations in shared PowerPoint presentations, clear the **Enable PowerPoint annotations**.</span></span> <span data-ttu-id="bf5c4-152">預設允許使用註釋。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-152">By default, annotations are allowed.</span></span>
    
    - <span data-ttu-id="bf5c4-p114">若要防止使用投票，請清除 **[啟用投票]** 核取方塊。預設允許使用投票。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-p114">To prevent the use of polls, clear the **Enable polls** check box. By default, polls are allowed.</span></span>
    
15. <span data-ttu-id="bf5c4-155">在 **[應用程式共用]** 中，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="bf5c4-155">In **Application sharing**, do one of the following:</span></span>
    
    - <span data-ttu-id="bf5c4-156">若要防止使用應用程式共用，按一下 **[停用應用程式共用]**。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-156">To prevent the use of application sharing, click **Disable application sharing**.</span></span>
    
    - <span data-ttu-id="bf5c4-p115">若要允許使用應用程式共用，按一下 **[啟用應用程式共用]**。此設定為預設值。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-p115">To allow the use of application sharing, click **Enable application sharing**. This is the default setting.</span></span>
    
16. <span data-ttu-id="bf5c4-159">如果您在 **[應用程式共同]** 中選擇允許應用程式共同，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="bf5c4-159">If you chose to allow application sharing in **Application sharing**, do the following:</span></span>
    
    - <span data-ttu-id="bf5c4-p116">若要防止會議參與者掌控應用程式共用功能，請清除 **[允許參與者取得控制權]** 核取方塊。根據預設，參與者可以掌控應用程式共用功能。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-p116">To prevent meeting participants from taking control of application sharing, clear the **Allow participants to take control** check box. By default, participants can take control of application sharing.</span></span>
    
    - <span data-ttu-id="bf5c4-p117">如果您選擇允許會議參與者掌控應用程式共用功能，請選取 **[允許同盟和匿名參與者取得控制權]** 核取方塊，以允許外部使用者掌控應用程式共用功能。根據預設，外部使用者無法掌控應用程式共用功能。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-p117">If you chose to allow meeting participants to take control of application sharing, select the **Allow federated and anonymous participants to take control** check box to allow external users to take control of application sharing. By default, external users cannot take control of application sharing.</span></span>
    
17. <span data-ttu-id="bf5c4-164">在 **[參與者原則]** 下方，執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="bf5c4-164">Under **Participant policy**, do one of the following:</span></span>
    
    - <span data-ttu-id="bf5c4-165">若要同時防止使用應用程式共用與桌面共用功能，按一下 **[停用應用程式和桌面共用]**。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-165">To prevent both application sharing and desktop sharing, click **Disable application and desktop sharing**.</span></span>
    
    - <span data-ttu-id="bf5c4-166">若要允許使用應用程式共用，但防止使用桌面共用，則按一下 **[啟用應用程式共用]**。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-166">To allow application sharing but not desktop sharing, click **Enable application sharing**.</span></span>
    
    - <span data-ttu-id="bf5c4-p118">若要同時允許使用應用程式共用與桌面共用功能，按一下 **[啟用應用程式和桌面共用]**。此設定為預設值。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-p118">To allow both application sharing and desktop sharing, click **Enable application and desktop sharing**. This is the default setting.</span></span>
    
18. <span data-ttu-id="bf5c4-p119">若要防止點對點檔案傳輸，請清除 **[啟用點對點檔案傳輸]** 核取方塊。預設允許進行點對點檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-p119">To prevent peer-to-peer file transfers, clear the **Enable peer-to-peer file transfer** check box. By default, peer-to-peer file transfers are allowed.</span></span>
    
19. <span data-ttu-id="bf5c4-p120">若要允許進行點對點錄製作業，選取 **[啟用點對點錄製]** 核取方塊。預設不允許進行點對點錄製。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-p120">To allow peer-to-peer recording, select the **Enable peer-to-peer recording** check box. By default, peer-to-peer recording is not allowed.</span></span>
    
20. <span data-ttu-id="bf5c4-173">若要允許參與者與多個影片資料流程加入，請選取 [ **啟用參與者以多個影片加入** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-173">To allow participants to join with multiple video streams, select the **Enable participants to join with multiple video streams** check box.</span></span> <span data-ttu-id="bf5c4-174">根據預設，允許多個影片資料流程。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-174">By default, multiple video streams are allowed.</span></span>
    
21. <span data-ttu-id="bf5c4-175">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-175">Click **Commit**.</span></span>
    
## <a name="create-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="bf5c4-176">使用商務用 Skype Server 管理命令介面建立會議原則</span><span class="sxs-lookup"><span data-stu-id="bf5c4-176">Create conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="bf5c4-177">若要建立會議原則，請使用 **New-CsConferencingPolicy** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-177">To create conferencing policies, use the **New-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="bf5c4-178">下列範例會建立具有 Identity SalesConferencingPolicy 的新會議原則。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-178">The following example creates a new conferencing policy with the Identity SalesConferencingPolicy.</span></span> <span data-ttu-id="bf5c4-179">這項原則會使用會議原則的所有預設值，其中一項： MaxMeetingSize 除外。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-179">This policy will use all the default values for a conferencing policy except one: MaxMeetingSize.</span></span> <span data-ttu-id="bf5c4-180">在此範例中，會議大小上限會設定為50，而不是預設值250：</span><span class="sxs-lookup"><span data-stu-id="bf5c4-180">In this example, the maximum size for a meeting will be set to 50 instead of the default value of 250:</span></span>
  
```PowerShell
New-CsConferencingPolicy -Identity SalesConferencingPolicy -MaxMeetingSize 50
```

<span data-ttu-id="bf5c4-181">如需詳細資訊，包括完整的語法描述及參數清單，請參閱 [New-CsConferencingPolicy](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="bf5c4-181">For more information, including a complete syntax description and list of parameters, see [New-CsConferencingPolicy](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps).</span></span>
