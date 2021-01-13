---
title: 常設聊天室原則
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatPolicy
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb9e95b9-f69d-4545-970f-9dfdd93b0eff
description: 您可以使用 Persistent 聊天群組的持續聊天原則頁面，管理全域、集區、網站或使用者層級的原則，包括設定預設全域原則，以及為您的部署建立一或多個額外的使用者和網站原則。 如果使用者依原則為使用者啟用 Persistent Chat Server，則 Persistent Chat Server 環境會出現在其用戶端中。
ms.openlocfilehash: e7148530f571a46937ee8d8a3bf44315ac692eb6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819293"
---
# <a name="persistent-chat-policy"></a><span data-ttu-id="0f4ca-104">常設聊天室原則</span><span class="sxs-lookup"><span data-stu-id="0f4ca-104">Persistent Chat Policy</span></span>
 
<span data-ttu-id="0f4ca-105">您可以使用 **Persistent 聊天** 群組的 **持續聊天原則** 頁面，管理全域、集區、網站或使用者層級的原則，包括設定預設全域原則，以及為您的部署建立一或多個額外的使用者和網站原則。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-105">You can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="0f4ca-106">如果使用者依原則為使用者啟用 Persistent Chat Server，則 Persistent Chat Server 環境會出現在其用戶端中。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-106">If Persistent Chat Server is enabled for a user by policy, then the Persistent Chat Server environment appears in their client.</span></span>
  
<span data-ttu-id="0f4ca-107">當您部署 Persistent Chat Server 時，會自動建立全域原則，而且可以設定，但不能刪除。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-107">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="0f4ca-108">因為全域原則會套用至所有使用者，所以不需要為每個使用者設定。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-108">Because the global policy applies to all users, it doesn't have to be set per user.</span></span>
  
<span data-ttu-id="0f4ca-109">您可以建立及設定多個網站和使用者原則，以及全域原則，讓使用者能夠使用 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-109">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="0f4ca-110">Pool 和 site Persistent Chat Server policy 會覆寫全域 Persistent Chat Server policy，但僅限於該網站的使用者。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-110">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="0f4ca-111">對於獲指派指使用原則的使用者，使用者原則會優先於其全域、集區和網站原則。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-111">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0f4ca-112">若要設定及使用 Persistent Chat Server，您必須先使用拓撲產生器，將 Persistent Chat Server 支援新增至拓撲，然後發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-112">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="0f4ca-113">如需詳細資訊，請參閱 [將 Persistent Chat Server 新增至您的商務用 Skype server 2015 拓撲](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-113">For details, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span></span> 
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="0f4ca-114">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="0f4ca-114">Tasks that you can perform</span></span>

<span data-ttu-id="0f4ca-115">您可以在 **Persistent Chat Policy** 頁面上執行下列工作：啟用 Persistent chat Server Policy;manage Persistent Chat Server policy。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-115">You can perform the following tasks on the **Persistent Chat Policy** page: enable Persistent Chat Server policy; manage Persistent Chat Server policy.</span></span>
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="0f4ca-116">設定持久聊天的全域原則</span><span class="sxs-lookup"><span data-stu-id="0f4ca-116">To configure the Global Policy for Persistent Chat</span></span>

1. <span data-ttu-id="0f4ca-117">使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-117">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="0f4ca-118">從 [ **開始** ] 功能表中，選取商務用 Skype Server 控制台或開啟瀏覽器視窗，然後輸入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-118">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="0f4ca-119">在商務用 Skype Server 控制台中，按一下 [ **Persistent chat**]，然後按一下 [ **persistent chat Policy**]。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-119">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="0f4ca-120">依序按一下原則清單中的 [全域]、[編輯] 及 [顯示詳細資料]。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-120">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="0f4ca-121">在 [編輯常設聊天室原則 - 全域] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="0f4ca-121">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="0f4ca-122">如果您不想要使用預設值 [全域]，請在 [名稱] 中指定全域原則的新名稱。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-122">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="0f4ca-123">在 [ **描述**] 中，提供 (使用者原則的詳細資訊（例如  _CentralSiteName_) 的全域原則）。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-123">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="0f4ca-124">若要控制未特別透過網站原則或使用者原則控制之所有網站及使用者的持續性聊天，請選取或清除 [ **啟用持續性聊天** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-124">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="0f4ca-125">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-125">Click **Commit**.</span></span>
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="0f4ca-126">若要建立網站的持續聊天原則</span><span class="sxs-lookup"><span data-stu-id="0f4ca-126">To create a Persistent Chat policy for a site</span></span>

<span data-ttu-id="0f4ca-127">您可以針對已部署的每個網站，建立網站特定的持久聊天原則。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-127">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>
  
<span data-ttu-id="0f4ca-128">網站原則中的設定會覆寫全域原則，但僅限於該網站原則所涵蓋的特定網站。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-128">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>
  
1. <span data-ttu-id="0f4ca-129">使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-129">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="0f4ca-130">從 [ **開始** ] 功能表中，選取商務用 Skype Server 控制台或開啟瀏覽器視窗，然後輸入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-130">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="0f4ca-131">在左導覽列中，按一下 [常設聊天室]，然後按一下 [常設聊天室原則]。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-131">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="0f4ca-132">按一下 [新增]，然後按一下 [站台原則]。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-132">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="0f4ca-133">在 [選取站台] 中，按一下要套用該原則的網站。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-133">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="0f4ca-134">在 [新增常設聊天室原則] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="0f4ca-134">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="0f4ca-135">在 [名稱] 中，指定新網站原則的名稱 (例如，Redmond)。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-135">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="0f4ca-136">在 [描述] 中，提供網站原則的詳細資訊 (例如，Redmond 的聊天室原則)。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-136">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="0f4ca-137">若要控制未特別透過網站原則控制之所有網站的持續性聊天，請選取或清除 [ **啟用持續性聊天** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-137">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="0f4ca-138">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-138">Click **Commit**.</span></span>
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a><span data-ttu-id="0f4ca-139">若要建立持久聊天的使用者原則</span><span class="sxs-lookup"><span data-stu-id="0f4ca-139">To create a user policy for Persistent Chat</span></span>

<span data-ttu-id="0f4ca-140">在商務用 Skype Server 控制台中，您可以定義可指派 **給使用者使用者** 的使用者原則。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-140">In the Skype for Business Server Control Panel, you define user policies that can be assigned to users in **Users**.</span></span>
  
<span data-ttu-id="0f4ca-141">使用者原則會覆寫全域與網站原則，但僅限於指派?特定使用者的使用者原則。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-141">The user policy overrides the global policy and site policies, but only for the specific users who are assigned the user policy.</span></span>
  
1. <span data-ttu-id="0f4ca-142">使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-142">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="0f4ca-143">從 [ **開始** ] 功能表中，選取商務用 Skype Server 控制台或開啟瀏覽器視窗，然後輸入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-143">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="0f4ca-144">在左導覽列中，按一下 [常設聊天室]，然後按一下 [常設聊天室原則]。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-144">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="0f4ca-145">按一下 [新增]，然後按一下 [使用者原則]。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-145">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="0f4ca-146">在 [新增常設聊天室原則] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="0f4ca-146">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="0f4ca-147">在 [名稱] 中，指定新使用者原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-147">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="0f4ca-148">在 [ **描述**] 中，提供 (使用者原則的詳細資訊（例如，特定使用者) 的持續性聊天原則）。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-148">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="0f4ca-149">若要控制未特別透過使用者原則控制之所有使用者的持續聊天，請選取或清除 [ **啟用持續性聊天** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-149">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="0f4ca-150">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-150">Click **Commit**.</span></span>
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="0f4ca-151">將 Persistent Chat 使用者原則套用至使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="0f4ca-151">To apply a Persistent Chat user policy to a user account</span></span>

<span data-ttu-id="0f4ca-152">如果使用者已啟用商務用 Skype Server，您可以將適當的原則套用至特定使用者，以便為 Persistent Chat Server 啟用或停用。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-152">If a user has been enabled for Skype for Business Server, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>
  
<span data-ttu-id="0f4ca-153">使用本主題中的程式，將先前建立的 Persistent Chat 使用者原則套用至一或多個使用者帳戶或使用者群組。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-153">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>
  
1. <span data-ttu-id="0f4ca-154">使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-154">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="0f4ca-155">從 [ **開始** ] 功能表中，選取商務用 Skype Server 控制台或開啟瀏覽器視窗，然後輸入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-155">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="0f4ca-156">在左導覽列中，按一下 **[使用者]**，然後搜尋想要設定的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-156">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="0f4ca-157">在列出搜尋結果的表格中，按一下使用者帳戶，並依序按一下 **[編輯]** 及 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-157">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="0f4ca-158">在 [ **Persistent chat 原則**] 底下的 [**編輯 Lync Server 使用者**] 中，選取您要套用的 [持久聊天] 使用者原則。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-158">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0f4ca-159">**\<Automatic\>** 設定將套用預設的有效原則。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-159">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="0f4ca-160">伺服器會自動套用這些設定。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-160">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="0f4ca-161">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="0f4ca-161">Click **Commit**.</span></span>
    

