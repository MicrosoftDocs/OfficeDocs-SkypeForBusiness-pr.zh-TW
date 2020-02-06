---
title: 常設聊天室原則主要頁面
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0dc18d5c-82d6-4d39-afb1-efdb3ae6d2c7
description: 您可以使用 [常設聊天室] 群組的 [常設聊天室原則] 頁面來管理全域、集區、網站或使用者層級的原則，包括為部署設定預設全域原則，以及建立一個或多個其他使用者和站台原則。 如果使用者依原則啟用持久聊天伺服器，則持續聊天伺服器環境會出現在其用戶端中。
ms.openlocfilehash: 053e7fb4f03f7e152a238a3b155eac161433c141
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822516"
---
# <a name="persistent-chat-policy-main-page"></a><span data-ttu-id="b82da-104">常設聊天室原則主要頁面</span><span class="sxs-lookup"><span data-stu-id="b82da-104">Persistent Chat Policy Main Page</span></span>
 
<span data-ttu-id="b82da-105">您可以使用 [常設聊天室] \*\*\*\* 群組的 [常設聊天室原則] \*\*\*\* 頁面來管理全域、集區、網站或使用者層級的原則，包括為部署設定預設全域原則，以及建立一個或多個其他使用者和站台原則。</span><span class="sxs-lookup"><span data-stu-id="b82da-105">You can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="b82da-106">如果使用者依原則啟用持久聊天伺服器，則持續聊天伺服器環境會出現在其用戶端中。</span><span class="sxs-lookup"><span data-stu-id="b82da-106">If a user is enabled for Persistent Chat Server by policy, then the Persistent Chat Server environment appears in their client.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b82da-107">在拓撲中，持續式聊天伺服器網站原則會全域、每個使用者的池子或每個使用者的網站，或每個使用者。</span><span class="sxs-lookup"><span data-stu-id="b82da-107">In the topology, Persistent Chat Server site policies apply globally, per user's pool, or per user's site, or per user.</span></span> 
  
<span data-ttu-id="b82da-108">全域原則是在您部署持久聊天伺服器時自動建立，而且可以設定，但不能刪除。</span><span class="sxs-lookup"><span data-stu-id="b82da-108">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="b82da-109">因為全域原則適用于所有使用者，因此不需要針對每個使用者進行設定。</span><span class="sxs-lookup"><span data-stu-id="b82da-109">Because the global policy applies to all users, it doesn't have to be set per user.</span></span>
  
<span data-ttu-id="b82da-110">您可以建立及設定多個網站和使用者原則，搭配全域原則，可讓使用者使用持久聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="b82da-110">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="b82da-111">文件庫和網站持續聊天伺服器原則會覆寫全域持久聊天伺服器原則，但只適用于該網站的使用者。</span><span class="sxs-lookup"><span data-stu-id="b82da-111">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="b82da-112">針對受指派使用原則的使用者，使用者原則會優先於全域、集區和網站原則。</span><span class="sxs-lookup"><span data-stu-id="b82da-112">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b82da-113">若要設定及使用持續聊天伺服器，您必須先使用拓撲建立器，才能將持續聊天伺服器支援新增到拓撲結構，然後發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="b82da-113">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="b82da-114">如需詳細資訊，請參閱[在商務用 Skype server 2015 拓撲中新增永久聊天伺服器](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="b82da-114">For details, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span></span> 
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="b82da-115">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="b82da-115">Tasks that you can perform</span></span>

<span data-ttu-id="b82da-116">您可以在 [常設聊天室原則] \*\*\*\* 頁面上執行下列工作：啟用和管理常設聊天室伺服器原則。</span><span class="sxs-lookup"><span data-stu-id="b82da-116">You can perform the following tasks on the **Persistent Chat Policy** page: enable and manage Persistent Chat Server policy.</span></span>
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="b82da-117">設定持續聊天的全域原則</span><span class="sxs-lookup"><span data-stu-id="b82da-117">To configure the Global Policy for Persistent Chat</span></span>

1. <span data-ttu-id="b82da-118">使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="b82da-118">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b82da-119">從 [**開始**] 功能表中，選取 [商務用 Skype 伺服器] 控制台或開啟瀏覽器視窗，然後輸入管理員 URL。</span><span class="sxs-lookup"><span data-stu-id="b82da-119">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="b82da-120">在商務用 Skype Server 的 [控制台] 中，按一下 [**持續聊天**]，然後按一下 [**永久聊天原則**]。</span><span class="sxs-lookup"><span data-stu-id="b82da-120">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="b82da-121">按一下原則清單中的 [全域]\*\*\*\*，按一下 [編輯]\*\*\*\*，然後按一下 [顯示詳細資料]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b82da-121">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="b82da-122">在 [編輯常設聊天室原則 - 全域] \*\*\*\* 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="b82da-122">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="b82da-123">如果不想要使用全域的預設設定，請在 [名稱] \*\*\*\* 中指定全域原則的新名稱。</span><span class="sxs-lookup"><span data-stu-id="b82da-123">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="b82da-124">在 [**描述**] 中，提供使用者原則的詳細資料（例如， _centralSiteName_的全域原則）。</span><span class="sxs-lookup"><span data-stu-id="b82da-124">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="b82da-125">若要控制未透過網站原則或使用者原則專門控制之所有網站和使用者的持續聊天，請選取或清除 [**啟用持續聊天**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b82da-125">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="b82da-126">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b82da-126">Click **Commit**.</span></span>
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="b82da-127">建立網站的持續聊天原則</span><span class="sxs-lookup"><span data-stu-id="b82da-127">To create a Persistent Chat policy for a site</span></span>

<span data-ttu-id="b82da-128">針對您已部署的每個網站，您可以建立特定于網站的持久聊天原則。</span><span class="sxs-lookup"><span data-stu-id="b82da-128">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>
  
<span data-ttu-id="b82da-129">網站原則中的設定優先於全域原則，但僅限該網站原則所涵蓋的特定網站。</span><span class="sxs-lookup"><span data-stu-id="b82da-129">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>
  
1. <span data-ttu-id="b82da-130">使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="b82da-130">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b82da-131">從 [**開始**] 功能表中，選取 [商務用 Skype 伺服器] 控制台或開啟瀏覽器視窗，然後輸入管理員 URL。</span><span class="sxs-lookup"><span data-stu-id="b82da-131">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="b82da-132">在左導覽列中，按一下 [常設聊天室]\*\*\*\*，然後按一下 [常設聊天室原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b82da-132">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="b82da-133">按一下 [新增]\*\*\*\*，然後按一下 [站台原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b82da-133">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="b82da-134">在 [選取站台] \*\*\*\* 中，按一下要套用原則的網站。</span><span class="sxs-lookup"><span data-stu-id="b82da-134">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="b82da-135">在 [新增常設聊天室原則] \*\*\*\* 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="b82da-135">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="b82da-136">在 [名稱]\*\*\*\* 中，指定新網站原則的名稱 (例如，Redmond)。</span><span class="sxs-lookup"><span data-stu-id="b82da-136">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="b82da-137">在 [描述]\*\*\*\* 中，提供網站原則的詳細資訊 (例如，Redmond 的聊天室原則)。</span><span class="sxs-lookup"><span data-stu-id="b82da-137">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="b82da-138">若要控制未特別透過網站原則控制之所有網站的常設聊天室，請選取或清除 [啟用常設聊天室]\*\*\*\* 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b82da-138">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="b82da-139">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b82da-139">Click **Commit**.</span></span>
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a><span data-ttu-id="b82da-140">建立持續聊天的使用者原則</span><span class="sxs-lookup"><span data-stu-id="b82da-140">To create a user policy for Persistent Chat</span></span>

<span data-ttu-id="b82da-141">在商務用 Skype Server [控制台] 中，您可以定義可指派給**使用者**使用者的使用者原則。</span><span class="sxs-lookup"><span data-stu-id="b82da-141">In the Skype for Business Server Control Panel, you define user policies that can be assigned to users in **Users**.</span></span>
  
<span data-ttu-id="b82da-142">使用者原則優先於全域與網站原則，但僅限於對其指派該使用者原則的特定使用者。</span><span class="sxs-lookup"><span data-stu-id="b82da-142">The user policy overrides the global policy and site policies, but only for the specific users who are assigned the user policy.</span></span>
  
1. <span data-ttu-id="b82da-143">使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="b82da-143">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b82da-144">從 [**開始**] 功能表中，選取 [商務用 Skype 伺服器] 控制台或開啟瀏覽器視窗，然後輸入管理員 URL。</span><span class="sxs-lookup"><span data-stu-id="b82da-144">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="b82da-145">在左導覽列中，按一下 [常設聊天室]\*\*\*\*，然後按一下 [常設聊天室原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b82da-145">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="b82da-146">依序按一下 [新增]\*\*\*\* 和 [使用者原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b82da-146">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="b82da-147">在 [新增常設聊天室原則] \*\*\*\* 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="b82da-147">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="b82da-148">在 [名稱] \*\*\*\* 中，指定新使用者原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="b82da-148">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="b82da-149">在 [**描述**] 中，提供使用者原則的詳細資料（例如，針對特定使用者的持續聊天原則）。</span><span class="sxs-lookup"><span data-stu-id="b82da-149">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="b82da-150">若要控制未透過使用者原則明確控制之所有使用者的持續聊天，請選取或清除 [**啟用持續聊天**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b82da-150">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="b82da-151">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b82da-151">Click **Commit**.</span></span>
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="b82da-152">若要將持續性聊天使用者原則套用到使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="b82da-152">To apply a Persistent Chat user policy to a user account</span></span>

<span data-ttu-id="b82da-153">如果使用者已針對商務用 Skype 啟用，您可以將適當的原則套用至特定的使用者，以啟用或停用持久聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="b82da-153">If a user has been enabled for Skype for Business, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>
  
<span data-ttu-id="b82da-154">使用本主題中的程式，將先前建立的持續聊天使用者原則套用至一或多個使用者帳戶或使用者群組。</span><span class="sxs-lookup"><span data-stu-id="b82da-154">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>
  
1. <span data-ttu-id="b82da-155">使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="b82da-155">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b82da-156">從 [**開始**] 功能表中，選取 [商務用 Skype 伺服器] 控制台或開啟瀏覽器視窗，然後輸入管理員 URL。</span><span class="sxs-lookup"><span data-stu-id="b82da-156">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="b82da-157">在左導覽列中，按一下 [使用者]\*\*\*\*，然後搜尋想要設定的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="b82da-157">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="b82da-158">在列出搜尋結果的表格中，依序按一下使用者帳戶、[編輯]\*\*\*\* 及 [顯示詳細資料]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b82da-158">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="b82da-159">在 [**永久聊天原則**] 底下的 [**編輯 Lync Server 使用者**] 中，選取您要套用的持久聊天使用者原則。</span><span class="sxs-lookup"><span data-stu-id="b82da-159">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b82da-160">[ \*\* \<自動\> \*\*設定] 會套用預設的有效原則。</span><span class="sxs-lookup"><span data-stu-id="b82da-160">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="b82da-161">伺服器會自動套用這些設定。</span><span class="sxs-lookup"><span data-stu-id="b82da-161">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="b82da-162">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b82da-162">Click **Commit**.</span></span>
    

