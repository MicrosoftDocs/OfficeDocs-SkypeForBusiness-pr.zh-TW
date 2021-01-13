---
title: 在商務用 Skype Server 2015 中設定 Persistent Chat 使用者原則
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 摘要：閱讀此主題以瞭解如何在商務用 Skype Server 2015 中為 Persistent Chat Server 建立初始使用者原則。 Persistent Chat 使用者原則決定使用者是否可以存取聊天室。
ms.openlocfilehash: 531146a55b0282db191f503ef39e9be9e4d5f879
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802113"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="e0aa3-104">在商務用 Skype Server 2015 中設定 Persistent Chat 使用者原則</span><span class="sxs-lookup"><span data-stu-id="e0aa3-104">Configure Persistent Chat user policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e0aa3-105">**摘要：** 閱讀此主題以瞭解如何在商務用 Skype Server 2015 中為 Persistent Chat Server 建立初始使用者原則。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-105">**Summary:** Read this topic to learn how to create initial user policies for Persistent Chat Server in Skype for Business Server 2015.</span></span> <span data-ttu-id="e0aa3-106">Persistent Chat 使用者原則決定使用者是否可以存取聊天室。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-106">Persistent Chat user policies determine whether or not users are allowed access to chat rooms.</span></span>
  
<span data-ttu-id="e0aa3-107">您可以在下列層級管理 Persistent Chat Server 使用者原則：全域、網站或使用者。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-107">You can manage Persistent Chat Server user policies at the following levels: global, site, or user.</span></span> <span data-ttu-id="e0aa3-108">起初，您會設定全域原則，為部署中的所有使用者啟用 Persistent Chat 設定，然後建立其他使用者和網站原則，以控制是否開啟特定使用者和網站的持續性聊天功能。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-108">Initially, you configure the global policy to enable Persistent Chat settings for all users in your deployment, and then create additional user and site policies to control whether Persistent Chat is turned on for specific users and sites.</span></span>
  
<span data-ttu-id="e0aa3-109">本主題包含下列各節：</span><span class="sxs-lookup"><span data-stu-id="e0aa3-109">This topic contains the following sections:</span></span>
  
- <span data-ttu-id="e0aa3-110">設定全域原則</span><span class="sxs-lookup"><span data-stu-id="e0aa3-110">Configure the global policy</span></span>
    
- <span data-ttu-id="e0aa3-111">建立網站原則</span><span class="sxs-lookup"><span data-stu-id="e0aa3-111">Create a site policy</span></span>
    
- <span data-ttu-id="e0aa3-112">建立使用者原則</span><span class="sxs-lookup"><span data-stu-id="e0aa3-112">Create a user policy</span></span>
    
- <span data-ttu-id="e0aa3-113">將原則套用至使用者或使用者群組</span><span class="sxs-lookup"><span data-stu-id="e0aa3-113">Apply a policy to a user or user group</span></span>
    
> [!NOTE] 
> <span data-ttu-id="e0aa3-114">商務用 Skype Server 2015 仍提供持續聊天，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-114">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="e0aa3-115">小組中提供相同的功能。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="e0aa3-116">如需詳細資訊，請參閱 [Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="e0aa3-117">如果您需要使用持續聊天，您可以選擇將需要這項功能的使用者遷移至小組，或是繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-117">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="configure-the-global-policy"></a><span data-ttu-id="e0aa3-118">設定全域原則</span><span class="sxs-lookup"><span data-stu-id="e0aa3-118">Configure the global policy</span></span>

<span data-ttu-id="e0aa3-119">若要設定全域原則：</span><span class="sxs-lookup"><span data-stu-id="e0aa3-119">To configure the global policy:</span></span>
  
1. <span data-ttu-id="e0aa3-120">使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-120">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e0aa3-121">從 [ **開始** ] 功能表中，選取商務用 Skype Server 控制台或開啟瀏覽器視窗，然後輸入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-121">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="e0aa3-122">在商務用 Skype Server 控制台中，按一下 [ **Persistent chat**]，然後按一下 [ **persistent chat Policy**]。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-122">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="e0aa3-123">依序按一下原則清單中的 [全域]、[編輯] 及 [顯示詳細資料]。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-123">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="e0aa3-124">在 [編輯常設聊天室原則 - 全域] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="e0aa3-124">In **Edit Persistent Chat Policy - Global**, do the following:</span></span> 
    
   - <span data-ttu-id="e0aa3-125">如果您不想要使用預設值 [全域]，請在 [名稱] 中指定全域原則的新名稱。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-125">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="e0aa3-126">在 [ **描述**] 中，提供 (使用者原則的詳細資訊（例如  _CentralSiteName_) 的全域原則）。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-126">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="e0aa3-127">若要控制未特別透過網站原則或使用者原則控制之所有網站及使用者的持續性聊天，請選取或清除 [ **啟用持續性聊天** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-127">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="e0aa3-128">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-128">Click **Commit**.</span></span>
    
## <a name="create-a-site-policy"></a><span data-ttu-id="e0aa3-129">建立網站原則</span><span class="sxs-lookup"><span data-stu-id="e0aa3-129">Create a site policy</span></span>

<span data-ttu-id="e0aa3-130">您可以針對已部署的每個網站，建立網站特定的持久聊天原則。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-130">For each site that you have deployed, you can create a site-specific Persistent Chat policy.</span></span> <span data-ttu-id="e0aa3-131">網站原則中的設定會覆寫全域原則，但僅限於該網站原則所涵蓋的特定網站。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-131">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="e0aa3-132">若要建立網站原則：</span><span class="sxs-lookup"><span data-stu-id="e0aa3-132">To create a site policy:</span></span>
  
1. <span data-ttu-id="e0aa3-133">使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-133">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e0aa3-134">從 [ **開始** ] 功能表中，選取商務用 Skype Server 控制台或開啟瀏覽器視窗，然後輸入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-134">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="e0aa3-135">在左導覽列中，按一下 [常設聊天室]，然後按一下 [常設聊天室原則]。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-135">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="e0aa3-136">按一下 [新增]，然後按一下 [站台原則]。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-136">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="e0aa3-137">在 [選取站台] 中，按一下要套用該原則的網站。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-137">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="e0aa3-138">在 [新增常設聊天室原則] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="e0aa3-138">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="e0aa3-139">在 [名稱] 中，指定新網站原則的名稱 (例如，Redmond)。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-139">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="e0aa3-140">在 [描述] 中，提供網站原則的詳細資訊 (例如，Redmond 的聊天室原則)。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-140">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="e0aa3-141">若要控制未特別透過網站原則控制之所有網站的持續性聊天，請選取或清除 [ **啟用持續性聊天** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-141">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="e0aa3-142">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-142">Click **Commit**.</span></span>
    
## <a name="create-a-user-policy"></a><span data-ttu-id="e0aa3-143">建立使用者原則</span><span class="sxs-lookup"><span data-stu-id="e0aa3-143">Create a user policy</span></span>

<span data-ttu-id="e0aa3-144">您可以建立使用者特有的原則，以覆寫全域原則和使用者所屬的任何網站原則。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-144">You can create user-specific policies that override the global policy and any site policies to which the user belongs.</span></span> <span data-ttu-id="e0aa3-145">若要建立使用者原則：</span><span class="sxs-lookup"><span data-stu-id="e0aa3-145">To create a user policy:</span></span>
  
1. <span data-ttu-id="e0aa3-146">使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-146">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e0aa3-147">從 [ **開始** ] 功能表中，選取商務用 Skype Server 控制台或開啟瀏覽器視窗，然後輸入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-147">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="e0aa3-148">在左導覽列中，按一下 [常設聊天室]，然後按一下 [常設聊天室原則]。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-148">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="e0aa3-149">按一下 [新增]，然後按一下 [使用者原則]。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-149">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="e0aa3-150">在 [新增常設聊天室原則] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="e0aa3-150">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="e0aa3-151">在 [名稱] 中，指定新使用者原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-151">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="e0aa3-152">在 [ **描述**] 中，提供 (使用者原則的詳細資訊（例如，特定使用者) 的持續性聊天原則）。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-152">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="e0aa3-153">若要控制未特別透過使用者原則控制之所有使用者的持續聊天，請選取或清除 [ **啟用持續性聊天** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-153">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="e0aa3-154">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-154">Click **Commit**.</span></span>
    
## <a name="apply-a-policy-to-a-user-account"></a><span data-ttu-id="e0aa3-155">將原則套用至使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="e0aa3-155">Apply a policy to a user account</span></span>

<span data-ttu-id="e0aa3-156">建立原則之後，您可以將原則套用至使用者帳戶，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e0aa3-156">After you create policies, you can apply them to a user account as follows:</span></span>
  
1. <span data-ttu-id="e0aa3-157">使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-157">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e0aa3-158">從 [ **開始** ] 功能表中，選取商務用 Skype Server 控制台或開啟瀏覽器視窗，然後輸入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-158">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="e0aa3-159">在左導覽列中，按一下 **[使用者]**，然後搜尋想要設定的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-159">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="e0aa3-160">在列出搜尋結果的表格中，按一下使用者帳戶，並依序按一下 **[編輯]** 及 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-160">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="e0aa3-161">在 [ **Persistent chat 原則**] 底下的 [**編輯商務用 Skype Server 使用者**] 中，選取您要套用的 [持久聊天] 使用者原則。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-161">In **Edit Skype for Business Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e0aa3-162">**\<Automatic\>** 設定將套用預設的有效原則。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-162">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="e0aa3-163">伺服器會自動套用這些設定。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-163">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="e0aa3-164">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="e0aa3-164">Click **Commit**.</span></span>
    

