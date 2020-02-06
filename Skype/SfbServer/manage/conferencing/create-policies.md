---
title: 在商務用 Skype Server 中建立會議原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8c685326-8356-4075-bf95-32324b16ef81
description: 摘要：瞭解如何在商務用 Skype Server 中建立會議原則。
ms.openlocfilehash: 6fc8145e5f7c4dc0ee4b824a92248e365df56213
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818614"
---
# <a name="create-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="1cbb3-103">在商務用 Skype Server 中建立會議原則</span><span class="sxs-lookup"><span data-stu-id="1cbb3-103">Create conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="1cbb3-104">**摘要：** 瞭解如何在商務用 Skype Server 中建立會議原則。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-104">**Summary:** Learn how to create conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="1cbb3-105">您可以使用商務用 Skype Server 的 [控制台] 或使用商務用 Skype Server 管理命令介面來建立會議原則。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-105">You can create conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="create-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1cbb3-106">使用商務用 Skype Server 的 [控制台] 建立會議原則</span><span class="sxs-lookup"><span data-stu-id="1cbb3-106">Create conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="1cbb3-107">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="1cbb3-108">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="1cbb3-109">在左側導覽列中，按一下 [**會議**]，然後按一下 [**會議原則**]。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="1cbb3-110">按一下 [**新增**]，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="1cbb3-110">Click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="1cbb3-111">若要建立使用者層級原則，按一下 [**使用者原則**]。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-111">To create a user-level policy, click **User policy**.</span></span> <span data-ttu-id="1cbb3-112">在 [**新會議原則**] 的 [**名稱**] 中，輸入原則的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-112">In **New Conferencing Policy**, in **Name**, type a descriptive name for the policy.</span></span>
    
   - <span data-ttu-id="1cbb3-113">若要建立網站層級原則，按一下 [**網站原則**]。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-113">To create a site-level policy, click **Site policy**.</span></span> <span data-ttu-id="1cbb3-114">在 [**選取網站**搜尋] 欄位中，輸入您要為其建立原則之網站的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-114">In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy.</span></span> <span data-ttu-id="1cbb3-115">在網站清單中，按一下您想要的網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-115">In the list of sites, click the site that you want, and then click **OK**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="1cbb3-116">網站名稱會變成會議原則名稱;無法變更。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-116">The site name becomes the conferencing policy name; it cannot be changed.</span></span> 
  
5. <span data-ttu-id="1cbb3-117">在 [**描述**] 中，輸入原則的描述。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-117">In **Description**, type a description for the policy.</span></span>
    
6. <span data-ttu-id="1cbb3-118">在 [**召集人原則**] 底下的 [**最大會議大小**] 中，輸入您要允許會議的使用者數目上限。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-118">Under **Organizer policy**, in **Maximum meeting size**, type the maximum number of users that you want to allow at a meeting.</span></span> <span data-ttu-id="1cbb3-119">根據預設，會議最大大小是250。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-119">By default, the maximum meeting size is 250.</span></span>
    
7. <span data-ttu-id="1cbb3-120">若要防止使用者邀請匿名使用者加入會議，請清除 [**允許參與者邀請匿名使用者**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-120">To prevent users from inviting anonymous users to meetings, clear the **Allow participants to invite anonymous users** check box.</span></span> <span data-ttu-id="1cbb3-121">匿名使用者是在貴組織的 Active Directory 網域服務中沒有認證的使用者，因此沒有經過驗證的使用者。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-121">Anonymous users are users who do not have credentials in your organization's Active Directory Domain Services and who, therefore, are not authenticated.</span></span> <span data-ttu-id="1cbb3-122">根據預設，使用者可以邀請匿名使用者加入會議。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-122">By default, users can invite anonymous users to meetings.</span></span>
    
8. <span data-ttu-id="1cbb3-123">在 [**錄製**] 中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="1cbb3-123">In **Recording**, do one of the following:</span></span>
    
   - <span data-ttu-id="1cbb3-124">若要防止參與者錄製會議，請按一下 [**無**]。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-124">To prevent participants from recording meetings, click **None**.</span></span> <span data-ttu-id="1cbb3-125">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-125">This is the default setting.</span></span>
    
   - <span data-ttu-id="1cbb3-126">若要允許參與者錄製會議，請按一下 [**啟用錄製**]。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-126">To allow participants to record meetings, click **Enable recording**.</span></span>
    
9. <span data-ttu-id="1cbb3-127">若要允許外部參與者錄製會議，請選取 [**允許聯盟和匿名參與者進行記錄**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-127">To allow external participants to record meetings, select the **Allow federated and anonymous participants to record** check box.</span></span> <span data-ttu-id="1cbb3-128">預設是要防止外部參與者錄製會議。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-128">The default is to prevent external participants from recording meetings.</span></span>
    
10. <span data-ttu-id="1cbb3-129">在 [**音訊/影片**] 中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="1cbb3-129">In **Audio/video**, do one of the following:</span></span>
    
    - <span data-ttu-id="1cbb3-130">若要避免使用音訊和影片，請按一下 [**無**]。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-130">To prevent the use of audio and video, click **None**.</span></span>
    
    - <span data-ttu-id="1cbb3-131">若要允許使用音訊而不是影片，請按一下 [**啟用 IP 音訊**]。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-131">To allow the use of audio but not video, click **Enable IP audio**.</span></span>
    
    - <span data-ttu-id="1cbb3-132">若要允許使用音訊和影片，請按一下 [**啟用 IP 音訊/視頻**]。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-132">To allow the use of audio and video, click **Enable IP audio/video**.</span></span> <span data-ttu-id="1cbb3-133">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-133">This is the default setting.</span></span>
    
11. <span data-ttu-id="1cbb3-134">如果您選擇允許在**音訊/視頻**中使用音訊，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="1cbb3-134">If you chose to allow the use of audio in **Audio/video**, do the following:</span></span>
    
    - <span data-ttu-id="1cbb3-135">若要防止使用者透過撥號加入會議，請清除 [**啟用 PSTN 電話撥入式會議**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-135">To prevent users from joining the meeting by dialing in, clear the **Enable PSTN dial-in conferencing** check box.</span></span> <span data-ttu-id="1cbb3-136">根據預設，使用者可以使用公開交換電話網絡（PSTN）撥入會議。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-136">By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
    - <span data-ttu-id="1cbb3-137">如果您允許使用者撥入會議，而您想要允許未經驗證（匿名）使用者使用 [撥出 phoning] 加入會議，請選取 [**允許匿名參與者撥出**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-137">If you allow users to dial in to meetings and you want to allow unauthenticated (anonymous) users to join a meeting by using dial out phoning, select the **Allow anonymous participants to dial out** check box.</span></span> <span data-ttu-id="1cbb3-138">使用撥出 phoning，會議服務器就會呼叫使用者，而使用者會接聽電話來加入會議。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-138">With dial-out phoning, the conference server calls the user, and the user answers the phone to join the meeting.</span></span> <span data-ttu-id="1cbb3-139">根據預設，匿名使用者無法使用撥出 phoning 加入會議。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-139">By default, anonymous users cannot join a meeting by using dial-out phoning.</span></span>
    
12. <span data-ttu-id="1cbb3-140">如果您選擇允許在**音訊/視頻**中使用影片，請核取 [**允許多個影片串流**]。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-140">If you chose to allow the use of video in **Audio/video**, check **Allow multiple video streams**.</span></span>
    
13. <span data-ttu-id="1cbb3-141">在 [**資料**共同作業] 中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="1cbb3-141">In **Data collaboration**, do one of the following:</span></span>
    
    - <span data-ttu-id="1cbb3-142">若要防止資料共同作業，請按一下 [**無**]。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-142">To prevent data collaboration, click **None**.</span></span>
    
    - <span data-ttu-id="1cbb3-143">若要允許資料共同作業，請按一下 [**啟用資料**共同作業]。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-143">To allow data collaboration, click **Enable data collaboration**.</span></span> <span data-ttu-id="1cbb3-144">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-144">This is the default setting.</span></span>
    
14. <span data-ttu-id="1cbb3-145">如果您在**資料**共同作業中選擇允許資料共同作業，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="1cbb3-145">If you chose to allow data collaboration in **Data collaboration**, do the following:</span></span>
    
    - <span data-ttu-id="1cbb3-146">若要防止外部下載，請清除 [**允許聯盟和匿名參與者下載內容**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-146">To prevent external downloads, clear the **Allow federated and anonymous participants to download content** check box.</span></span> <span data-ttu-id="1cbb3-147">根據預設，外部使用者可以下載內容。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-147">By default, external users can download content.</span></span>
    
    - <span data-ttu-id="1cbb3-148">若要防止檔案傳輸，請清除 [**允許參與者傳送**檔案] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-148">To prevent file transfers, clear the **Allow participants to transfer files** check box.</span></span> <span data-ttu-id="1cbb3-149">根據預設，使用者可以傳送檔案。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-149">By default, users can transfer files.</span></span>
    
    - <span data-ttu-id="1cbb3-150">若要避免使用標注，請清除 [**啟用批註**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-150">To prevent the use of annotations, clear the **Enable annotations** check box.</span></span> <span data-ttu-id="1cbb3-151">若要在共用的 PowerPoint 簡報中使用注釋，請清除 [**啟用 PowerPoint 注釋**]。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-151">To the use of annotations in shared PowerPoint presentations, clear the **Enable PowerPoint annotations**.</span></span> <span data-ttu-id="1cbb3-152">根據預設，允許使用批註。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-152">By default, annotations are allowed.</span></span>
    
    - <span data-ttu-id="1cbb3-153">若要避免使用投票，請清除 [**啟用輪詢**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-153">To prevent the use of polls, clear the **Enable polls** check box.</span></span> <span data-ttu-id="1cbb3-154">根據預設，允許投票。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-154">By default, polls are allowed.</span></span>
    
15. <span data-ttu-id="1cbb3-155">在 [**應用程式共用**] 中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="1cbb3-155">In **Application sharing**, do one of the following:</span></span>
    
    - <span data-ttu-id="1cbb3-156">若要避免使用應用程式共用，請按一下 [**停用應用程式共用**]。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-156">To prevent the use of application sharing, click **Disable application sharing**.</span></span>
    
    - <span data-ttu-id="1cbb3-157">若要允許使用應用程式共用，請按一下 [**啟用應用程式共用**]。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-157">To allow the use of application sharing, click **Enable application sharing**.</span></span> <span data-ttu-id="1cbb3-158">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-158">This is the default setting.</span></span>
    
16. <span data-ttu-id="1cbb3-159">如果您在 [**應用程式共用**] 中選擇 [允許應用程式共用]，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="1cbb3-159">If you chose to allow application sharing in **Application sharing**, do the following:</span></span>
    
    - <span data-ttu-id="1cbb3-160">若要避免會議參與者控制應用程式共用，請清除 [**允許參與者取得控制權**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-160">To prevent meeting participants from taking control of application sharing, clear the **Allow participants to take control** check box.</span></span> <span data-ttu-id="1cbb3-161">根據預設，參與者可以取得應用程式共用的控制權。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-161">By default, participants can take control of application sharing.</span></span>
    
    - <span data-ttu-id="1cbb3-162">如果您選擇讓會議參與者控制應用程式共用，請選取 [**允許聯盟和匿名參與者取得控制權**] 核取方塊，以允許外部使用者控制應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-162">If you chose to allow meeting participants to take control of application sharing, select the **Allow federated and anonymous participants to take control** check box to allow external users to take control of application sharing.</span></span> <span data-ttu-id="1cbb3-163">根據預設，外部使用者無法取得應用程式共用的控制權。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-163">By default, external users cannot take control of application sharing.</span></span>
    
17. <span data-ttu-id="1cbb3-164">在 [**參與者原則**] 底下，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="1cbb3-164">Under **Participant policy**, do one of the following:</span></span>
    
    - <span data-ttu-id="1cbb3-165">若要防止應用程式共用與桌面共用，請按一下 [**停用應用程式與桌面共用**]。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-165">To prevent both application sharing and desktop sharing, click **Disable application and desktop sharing**.</span></span>
    
    - <span data-ttu-id="1cbb3-166">若要允許應用程式共用，但不允許桌面共用，請按一下 [**啟用應用程式共用**]。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-166">To allow application sharing but not desktop sharing, click **Enable application sharing**.</span></span>
    
    - <span data-ttu-id="1cbb3-167">若要允許應用程式共用與桌面共用，請按一下 [**啟用應用程式和桌面**共用]。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-167">To allow both application sharing and desktop sharing, click **Enable application and desktop sharing**.</span></span> <span data-ttu-id="1cbb3-168">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-168">This is the default setting.</span></span>
    
18. <span data-ttu-id="1cbb3-169">若要防止對等檔案傳輸，請清除 [**啟用對等檔案傳輸**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-169">To prevent peer-to-peer file transfers, clear the **Enable peer-to-peer file transfer** check box.</span></span> <span data-ttu-id="1cbb3-170">根據預設，允許對等檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-170">By default, peer-to-peer file transfers are allowed.</span></span>
    
19. <span data-ttu-id="1cbb3-171">若要允許對等錄製，請選取 [**啟用對等錄製**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-171">To allow peer-to-peer recording, select the **Enable peer-to-peer recording** check box.</span></span> <span data-ttu-id="1cbb3-172">根據預設，不允許對等錄製。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-172">By default, peer-to-peer recording is not allowed.</span></span>
    
20. <span data-ttu-id="1cbb3-173">若要允許參與者加入多個視頻資料流程，請選取 [**允許參與者加入多個視頻資料流程**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-173">To allow participants to join with multiple video streams, select the **Enable participants to join with multiple video streams** check box.</span></span> <span data-ttu-id="1cbb3-174">根據預設，允許多個視頻資料流程。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-174">By default, multiple video streams are allowed.</span></span>
    
21. <span data-ttu-id="1cbb3-175">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-175">Click **Commit**.</span></span>
    
## <a name="create-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="1cbb3-176">使用商務用 Skype Server Management Shell 建立會議原則</span><span class="sxs-lookup"><span data-stu-id="1cbb3-176">Create conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="1cbb3-177">若要建立會議原則，請使用**CsConferencingPolicy** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-177">To create conferencing policies, use the **New-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="1cbb3-178">下列範例會使用身分識別 SalesConferencingPolicy 建立新的會議原則。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-178">The following example creates a new conferencing policy with the Identity SalesConferencingPolicy.</span></span> <span data-ttu-id="1cbb3-179">此原則會針對會議原則使用所有預設值，除了一個： MaxMeetingSize。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-179">This policy will use all the default values for a conferencing policy except one: MaxMeetingSize.</span></span> <span data-ttu-id="1cbb3-180">在這個範例中，會議的最大大小會設定為50，而不是預設值250：</span><span class="sxs-lookup"><span data-stu-id="1cbb3-180">In this example, the maximum size for a meeting will be set to 50 instead of the default value of 250:</span></span>
  
```PowerShell
New-CsConferencingPolicy -Identity SalesConferencingPolicy -MaxMeetingSize 50
```

<span data-ttu-id="1cbb3-181">如需詳細資訊（包括完整的語法描述及參數清單），請參閱[新 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="1cbb3-181">For more information, including a complete syntax description and list of parameters, see [New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps).</span></span>
  

