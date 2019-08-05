---
title: 設定常設聊天室使用者原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: '摘要: 請閱讀本主題, 以瞭解如何在商務用 Skype Server 2015 中建立持續聊天伺服器的初始使用者原則。 持續聊天的使用者原則會判斷是否允許使用者存取聊天室。'
ms.openlocfilehash: 3f2a55f3a411fc3020ebe9af57d456f00dd74ef4
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2019
ms.locfileid: "36193998"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="22774-104">設定常設聊天室使用者原則</span><span class="sxs-lookup"><span data-stu-id="22774-104">Configure Persistent Chat user policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="22774-105">**摘要:** 請閱讀本主題, 瞭解如何在商務用 Skype Server 2015 中建立持續聊天伺服器的初始使用者原則。</span><span class="sxs-lookup"><span data-stu-id="22774-105">**Summary:** Read this topic to learn how to create initial user policies for Persistent Chat Server in Skype for Business Server 2015.</span></span> <span data-ttu-id="22774-106">持續聊天的使用者原則會判斷是否允許使用者存取聊天室。</span><span class="sxs-lookup"><span data-stu-id="22774-106">Persistent Chat user policies determine whether or not users are allowed access to chat rooms.</span></span>
  
<span data-ttu-id="22774-107">您可以在下列層面管理持續性聊天伺服器使用者原則: 全域、網站或使用者。</span><span class="sxs-lookup"><span data-stu-id="22774-107">You can manage Persistent Chat Server user policies at the following levels: global, site, or user.</span></span> <span data-ttu-id="22774-108">首先, 您要設定全域原則, 為您部署中的所有使用者啟用持續聊天設定, 然後建立其他使用者和網站原則, 以控制是否針對特定的使用者和網站開啟持續聊天功能。</span><span class="sxs-lookup"><span data-stu-id="22774-108">Initially, you configure the global policy to enable Persistent Chat settings for all users in your deployment, and then create additional user and site policies to control whether Persistent Chat is turned on for specific users and sites.</span></span>
  
<span data-ttu-id="22774-109">本主題包含下列各節:</span><span class="sxs-lookup"><span data-stu-id="22774-109">This topic contains the following sections:</span></span>
  
- <span data-ttu-id="22774-110">設定全域原則</span><span class="sxs-lookup"><span data-stu-id="22774-110">Configure the global policy</span></span>
    
- <span data-ttu-id="22774-111">建立網站原則</span><span class="sxs-lookup"><span data-stu-id="22774-111">Create a site policy</span></span>
    
- <span data-ttu-id="22774-112">建立使用者原則</span><span class="sxs-lookup"><span data-stu-id="22774-112">Create a user policy</span></span>
    
- <span data-ttu-id="22774-113">將原則套用到使用者或使用者群組</span><span class="sxs-lookup"><span data-stu-id="22774-113">Apply a policy to a user or user group</span></span>
    
> [!NOTE] 
> <span data-ttu-id="22774-114">商務用 Skype Server 2015 提供持續聊天, 但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="22774-114">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="22774-115">團隊中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="22774-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="22774-116">如需詳細資訊, 請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="22774-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="22774-117">如果您需要使用持續聊天, 您可以選擇將需要此功能的使用者遷移至小組, 或繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="22774-117">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="configure-the-global-policy"></a><span data-ttu-id="22774-118">設定全域原則</span><span class="sxs-lookup"><span data-stu-id="22774-118">Configure the global policy</span></span>

<span data-ttu-id="22774-119">若要設定全域原則:</span><span class="sxs-lookup"><span data-stu-id="22774-119">To configure the global policy:</span></span>
  
1. <span data-ttu-id="22774-120">使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="22774-120">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="22774-121">從 [**開始**] 功能表中, 選取 [商務用 Skype 伺服器] 控制台或開啟瀏覽器視窗, 然後輸入管理員 URL。</span><span class="sxs-lookup"><span data-stu-id="22774-121">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="22774-122">在商務用 Skype Server 的 [控制台] 中, 按一下 [**持續聊天**], 然後按一下 [**永久聊天原則**]。</span><span class="sxs-lookup"><span data-stu-id="22774-122">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="22774-123">按一下原則清單中的 [全域]\*\*\*\*，按一下 [編輯]\*\*\*\*，然後按一下 [顯示詳細資料]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22774-123">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="22774-124">在 [編輯常設聊天室原則 - 全域] \*\*\*\* 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="22774-124">In **Edit Persistent Chat Policy - Global**, do the following:</span></span> 
    
   - <span data-ttu-id="22774-125">如果不想要使用全域的預設設定，請在 [名稱] \*\*\*\* 中指定全域原則的新名稱。</span><span class="sxs-lookup"><span data-stu-id="22774-125">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="22774-126">在 [**描述**] 中, 提供使用者原則的詳細資料 (例如, _centralSiteName_的全域原則)。</span><span class="sxs-lookup"><span data-stu-id="22774-126">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="22774-127">若要控制未透過網站原則或使用者原則專門控制之所有網站和使用者的持續聊天, 請選取或清除 [**啟用持續聊天**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="22774-127">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="22774-128">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22774-128">Click **Commit**.</span></span>
    
## <a name="create-a-site-policy"></a><span data-ttu-id="22774-129">建立網站原則</span><span class="sxs-lookup"><span data-stu-id="22774-129">Create a site policy</span></span>

<span data-ttu-id="22774-130">針對您已部署的每個網站, 您可以建立特定于網站的持久聊天原則。</span><span class="sxs-lookup"><span data-stu-id="22774-130">For each site that you have deployed, you can create a site-specific Persistent Chat policy.</span></span> <span data-ttu-id="22774-131">網站原則中的設定優先於全域原則，但僅限該網站原則所涵蓋的特定網站。</span><span class="sxs-lookup"><span data-stu-id="22774-131">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="22774-132">若要建立網站原則:</span><span class="sxs-lookup"><span data-stu-id="22774-132">To create a site policy:</span></span>
  
1. <span data-ttu-id="22774-133">使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="22774-133">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="22774-134">從 [**開始**] 功能表中, 選取 [商務用 Skype 伺服器] 控制台或開啟瀏覽器視窗, 然後輸入管理員 URL。</span><span class="sxs-lookup"><span data-stu-id="22774-134">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="22774-135">在左導覽列中，按一下 [常設聊天室]\*\*\*\*，然後按一下 [常設聊天室原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22774-135">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="22774-136">按一下 [新增]\*\*\*\*，然後按一下 [站台原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22774-136">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="22774-137">在 [選取站台] \*\*\*\* 中，按一下要套用原則的網站。</span><span class="sxs-lookup"><span data-stu-id="22774-137">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="22774-138">在 [新增常設聊天室原則] \*\*\*\* 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="22774-138">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="22774-139">在 [名稱]\*\*\*\* 中，指定新網站原則的名稱 (例如，Redmond)。</span><span class="sxs-lookup"><span data-stu-id="22774-139">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="22774-140">在 [描述]\*\*\*\* 中，提供網站原則的詳細資訊 (例如，Redmond 的聊天室原則)。</span><span class="sxs-lookup"><span data-stu-id="22774-140">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="22774-141">若要控制未特別透過網站原則控制之所有網站的常設聊天室，請選取或清除 [啟用常設聊天室]\*\*\*\* 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="22774-141">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="22774-142">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22774-142">Click **Commit**.</span></span>
    
## <a name="create-a-user-policy"></a><span data-ttu-id="22774-143">建立使用者原則</span><span class="sxs-lookup"><span data-stu-id="22774-143">Create a user policy</span></span>

<span data-ttu-id="22774-144">您可以建立使用者專用的原則來覆寫全域原則, 以及使用者所屬的任何網站原則。</span><span class="sxs-lookup"><span data-stu-id="22774-144">You can create user-specific policies that override the global policy and any site policies to which the user belongs.</span></span> <span data-ttu-id="22774-145">若要建立使用者原則:</span><span class="sxs-lookup"><span data-stu-id="22774-145">To create a user policy:</span></span>
  
1. <span data-ttu-id="22774-146">使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="22774-146">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="22774-147">從 [**開始**] 功能表中, 選取 [商務用 Skype 伺服器] 控制台或開啟瀏覽器視窗, 然後輸入管理員 URL。</span><span class="sxs-lookup"><span data-stu-id="22774-147">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="22774-148">在左導覽列中，按一下 [常設聊天室]\*\*\*\*，然後按一下 [常設聊天室原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22774-148">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="22774-149">依序按一下 [新增]\*\*\*\* 和 [使用者原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22774-149">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="22774-150">在 [新增常設聊天室原則] \*\*\*\* 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="22774-150">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="22774-151">在 [名稱] \*\*\*\* 中，指定新使用者原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="22774-151">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="22774-152">在 [**描述**] 中, 提供使用者原則的詳細資料 (例如, 針對特定使用者的持續聊天原則)。</span><span class="sxs-lookup"><span data-stu-id="22774-152">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="22774-153">若要控制未透過使用者原則明確控制之所有使用者的持續聊天, 請選取或清除 [**啟用持續聊天**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="22774-153">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="22774-154">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22774-154">Click **Commit**.</span></span>
    
## <a name="apply-a-policy-to-a-user-account"></a><span data-ttu-id="22774-155">將原則套用到使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="22774-155">Apply a policy to a user account</span></span>

<span data-ttu-id="22774-156">建立原則之後, 您可以將它們套用至使用者帳戶, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="22774-156">After you create policies, you can apply them to a user account as follows:</span></span>
  
1. <span data-ttu-id="22774-157">使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="22774-157">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="22774-158">從 [**開始**] 功能表中, 選取 [商務用 Skype 伺服器] 控制台或開啟瀏覽器視窗, 然後輸入管理員 URL。</span><span class="sxs-lookup"><span data-stu-id="22774-158">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="22774-159">在左導覽列中，按一下 [使用者]\*\*\*\*，然後搜尋想要設定的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="22774-159">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="22774-160">在列出搜尋結果的表格中，依序按一下使用者帳戶、[編輯]\*\*\*\* 及 [顯示詳細資料]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22774-160">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="22774-161">在 [**永久聊天原則**] 底下的 [**編輯商務用 Skype Server 使用者**] 中, 選取您要套用的持久聊天使用者原則。</span><span class="sxs-lookup"><span data-stu-id="22774-161">In **Edit Skype for Business Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="22774-162">[ \*\* \<自動\> \*\*設定] 會套用預設的有效原則。</span><span class="sxs-lookup"><span data-stu-id="22774-162">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="22774-163">伺服器會自動套用這些設定。</span><span class="sxs-lookup"><span data-stu-id="22774-163">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="22774-164">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22774-164">Click **Commit**.</span></span>
    

