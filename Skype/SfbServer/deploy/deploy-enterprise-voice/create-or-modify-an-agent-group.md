---
title: 在商務用 Skype 中建立或修改代理群組
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
description: 在商務用 Skype Server Enterprise Voice 中，在 [回應] 群組中建立或修改代理群組。
ms.openlocfilehash: a919c1a25f3f4aa5a2d8648d782ea329f1e70d60
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001683"
---
# <a name="create-or-modify-an-agent-group-in-skype-for-business"></a><span data-ttu-id="e635c-103">在商務用 Skype 中建立或修改代理群組</span><span class="sxs-lookup"><span data-stu-id="e635c-103">Create or modify an agent group in Skype for Business</span></span>
 
<span data-ttu-id="e635c-104">在商務用 Skype Server Enterprise Voice 中，在 [回應] 群組中建立或修改代理群組。</span><span class="sxs-lookup"><span data-stu-id="e635c-104">Create or modify an agent group in Response Group, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="e635c-105">當您建立 [代理群組] 時，請選取指派給群組的 agent，並指定其他群組設定，例如路由方法，以及代理程式是否可以登入和登出群組。</span><span class="sxs-lookup"><span data-stu-id="e635c-105">When you create an agent group, you select the agents that are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span> 
  
<span data-ttu-id="e635c-106">必須登入和登出群組的工程師（與登入或登出商務用 Skype 不同）稱為正式代理程式。</span><span class="sxs-lookup"><span data-stu-id="e635c-106">An agent who must sign in and out of the group, which is different from signing in or out of Skype for Business, is called a formal agent.</span></span> <span data-ttu-id="e635c-107">正式的代理程式必須先登入群組，才能接收路由到群組的呼叫。</span><span class="sxs-lookup"><span data-stu-id="e635c-107">Formal agents must be signed in to the group before they can receive calls routed to the group.</span></span> <span data-ttu-id="e635c-108">此功能對從群組接聽通話的工程師很有用。</span><span class="sxs-lookup"><span data-stu-id="e635c-108">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="e635c-109">正式的代理程式可在商務用 Skype 中按一下功能表項目來登入和登出其群組，以開啟 Windows Internet Explorer Internet 瀏覽器，並顯示網頁主控台。</span><span class="sxs-lookup"><span data-stu-id="e635c-109">Formal agents sign in and out of their groups by clicking a menu item in Skype for Business to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>
  
<span data-ttu-id="e635c-110">未登入或登出群組的工程師稱為非正式代理程式。</span><span class="sxs-lookup"><span data-stu-id="e635c-110">An agent who does not sign in or out of the group is called an informal agent.</span></span> <span data-ttu-id="e635c-111">非正式的代理程式會在登入商務用 Skype 時自動登入群組，且無法登出群組。</span><span class="sxs-lookup"><span data-stu-id="e635c-111">Informal agents are automatically signed in to the group when they sign in to Skype for Business, and they cannot sign out of the group.</span></span>
  
<span data-ttu-id="e635c-112">只有內部部署使用者可以使用代理程式。</span><span class="sxs-lookup"><span data-stu-id="e635c-112">Only on-premises users can be agents.</span></span> <span data-ttu-id="e635c-113">如果代理程式是從內部部署移至線上，回應群組呼叫將不會路由至該代理程式。</span><span class="sxs-lookup"><span data-stu-id="e635c-113">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>
  
<span data-ttu-id="e635c-114">使用下列其中一個程式來建立或修改代理群組。</span><span class="sxs-lookup"><span data-stu-id="e635c-114">Use one of the following procedures to create or modify an agent group.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e635c-115">當您將使用者指派為回應群組代理程式時，如果他們已啟用隱私權模式，就必須搜尋「RGS 目前狀態觀察程式」連絡人，然後將他們新增到他們的連絡人清單。</span><span class="sxs-lookup"><span data-stu-id="e635c-115">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list.</span></span> <span data-ttu-id="e635c-116">已啟用隱私權模式的代理，但其 [連絡人] 清單中沒有「RGS 目前狀態觀察程式」，就無法接收回應群組的呼叫。</span><span class="sxs-lookup"><span data-stu-id="e635c-116">Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group.</span></span> <span data-ttu-id="e635c-117">未啟用隱私權模式的代理不會受到影響。</span><span class="sxs-lookup"><span data-stu-id="e635c-117">Agents who do not have Privacy mode enabled are not affected.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-an-agent-group"></a><span data-ttu-id="e635c-118">使用商務用 Skype Server 的 [控制台] 來建立或修改代理群組</span><span class="sxs-lookup"><span data-stu-id="e635c-118">To use Skype for Business Server Control Panel to create or modify an agent group</span></span>

1. <span data-ttu-id="e635c-119">以 RTCUniversalServerAdmins 群組成員的身分登入，或以支援回應群組的預先定義之系統管理角色的成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="e635c-119">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e635c-120">如果您是受管理工作流程的委派回應群組管理員之一，您可以在您管理的工作流程中建立群組並使用。</span><span class="sxs-lookup"><span data-stu-id="e635c-120">If you are one of the delegated Response Group Managers for a managed workflow, you can create groups and use them in the workflows that you manage.</span></span> 
  
2. <span data-ttu-id="e635c-121">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="e635c-121">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="e635c-122">在左側導覽列中，按一下 [**回應群組**]，然後按一下 [**群組**]。</span><span class="sxs-lookup"><span data-stu-id="e635c-122">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>
    
4. <span data-ttu-id="e635c-123">在 [**群組**] 頁面上，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="e635c-123">On the **Group** page, do one of the following:</span></span>
    
   - <span data-ttu-id="e635c-124">若要建立新的 [代理] 群組，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="e635c-124">To create a new agent group, click **New**.</span></span> <span data-ttu-id="e635c-125">在 [**選取服務**搜尋] 欄位中，輸入您要新增群組之**ApplicationServer**服務的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="e635c-125">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service where you want to add the group.</span></span> <span data-ttu-id="e635c-126">在產生的服務清單中，按一下您想要的服務，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e635c-126">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="e635c-127">若要修改現有的 [代理] 群組，請在 [搜尋] 欄位中輸入 [代理] 群組的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="e635c-127">To modify an existing agent group, type all or part of the name of the agent group in the search field.</span></span> <span data-ttu-id="e635c-128">在產生的清單中，按一下您想要的群組，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="e635c-128">In the resulting list, click the group that you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="e635c-129">在 [**名稱**] 中，輸入 [代理] 群組的識別名稱。</span><span class="sxs-lookup"><span data-stu-id="e635c-129">In **Name**, type an identifying name for the agent group.</span></span>
    
6. <span data-ttu-id="e635c-130">在 [**描述**] 中，輸入群組的描述。</span><span class="sxs-lookup"><span data-stu-id="e635c-130">In **Description**, type a description for the group.</span></span>
    
7. <span data-ttu-id="e635c-131">在**參與原則**中，選取下列其中一個選項，為群組設定登入行為：</span><span class="sxs-lookup"><span data-stu-id="e635c-131">In the **Participation policy**, select one of the following to set up the sign-in behavior for the group:</span></span>
    
   - <span data-ttu-id="e635c-132">選取 [**非正式**]，指定群組中的代理不需要登入和登出群組。</span><span class="sxs-lookup"><span data-stu-id="e635c-132">Select **Informal** to specify that agents in the group do not need to sign in and out of the group.</span></span> <span data-ttu-id="e635c-133">當代理登入商務用 Skype 時，系統會自動登入該群組。</span><span class="sxs-lookup"><span data-stu-id="e635c-133">Agents are automatically signed in to the group when they sign in to Skype for Business.</span></span>
    
   - <span data-ttu-id="e635c-134">選取 [**正式**]，指定群組中的代理程式必須登入和登出群組。</span><span class="sxs-lookup"><span data-stu-id="e635c-134">Select **Formal** to specify that agents in the group must sign in and out of the group.</span></span> <span data-ttu-id="e635c-135">當您選取此選項時，代理程式會按一下商務用 Skype 中的功能表項目來開啟 Internet Explorer，並顯示可登入和登出群組的網頁主控台。</span><span class="sxs-lookup"><span data-stu-id="e635c-135">When you select this option, agents click a menu item in Skype for Business to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>
    
8. <span data-ttu-id="e635c-136">在 [**警示時間（秒）**] 中，指定在向下一個可用的代理程式撥打電話之前撥打代理程式的秒數（預設值為20秒）。</span><span class="sxs-lookup"><span data-stu-id="e635c-136">In **Alert time (seconds)**, specify the number of seconds to ring an agent before offering the call to the next available agent (the default is 20 seconds).</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e635c-137">Agent 警示時間設定不能超過180秒。</span><span class="sxs-lookup"><span data-stu-id="e635c-137">The agent alert time setting cannot exceed 180 seconds.</span></span> <span data-ttu-id="e635c-138">如果 agent 警示時間超過180秒，用戶端應用程式會拒絕呼叫，因為 SIP 事務計時器達到最大等待時間。</span><span class="sxs-lookup"><span data-stu-id="e635c-138">If the agent alert time exceeds 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span> 
  
9. <span data-ttu-id="e635c-139">在**路由方法**中，選取將呼叫路由到群組中的方法，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e635c-139">In **Routing method**, select the method for routing calls to agents in the group as follows:</span></span>
    
   - <span data-ttu-id="e635c-140">若要先為閒置時間最長（在商務用 Skype 中的目前狀態為「已**使用**」或「**非**使用中」）的代理提供新呼叫，請按一下 [**最長閒置**]。</span><span class="sxs-lookup"><span data-stu-id="e635c-140">To offer a new call first to the agent who has been idle the longest (has had a presence of **Available** or **Inactive** in Skype for Business the longest), click **Longest idle**.</span></span> 
    
   - <span data-ttu-id="e635c-141">若要同時提供新呼叫給所有可用的代理程式，請按一下 [**平行**]。</span><span class="sxs-lookup"><span data-stu-id="e635c-141">To offer a new call to all available agents at the same time, click **Parallel**.</span></span> <span data-ttu-id="e635c-142">電話會傳送給第一個接聽的代理人。</span><span class="sxs-lookup"><span data-stu-id="e635c-142">The call is sent to the first agent who accepts it.</span></span>
    
   - <span data-ttu-id="e635c-143">若要依次提供對每個代理程式的新呼叫，請按一下 [**迴圈**]。</span><span class="sxs-lookup"><span data-stu-id="e635c-143">To offer a new call to each agent in turn, click **Round robin**.</span></span> 
    
   - <span data-ttu-id="e635c-144">若要隨時以其在 [**代理程式**清單] 中列出的順序提供給 agent 的新呼叫，請按一下 [**串列**]。</span><span class="sxs-lookup"><span data-stu-id="e635c-144">To always offer a new call to the agents in the order in which they are listed in the **Agent** list, click **Serial**.</span></span> 
    
   - <span data-ttu-id="e635c-145">若要為所有登入商務用 Skype 和回應群組應用程式的代理提供新的呼叫，請按一下 [**助理**]。</span><span class="sxs-lookup"><span data-stu-id="e635c-145">To offer a new call to all agents who are signed into Skype for Business and the Response Group application at the same time, regardless of their current presence, click **Attendant**.</span></span> <span data-ttu-id="e635c-146">已設定為代理的使用者可以查看所有等待的通話，並以任何順序接聽等待通話。</span><span class="sxs-lookup"><span data-stu-id="e635c-146">Users who are configured as agents can see all the calls that are waiting and answer waiting calls in any order.</span></span> <span data-ttu-id="e635c-147">通話會傳送給接受該通話的第一份代理商，之後其他代理就不會再看到通話。</span><span class="sxs-lookup"><span data-stu-id="e635c-147">The call is sent to the first agent who accepts it, after which the other agents no longer see the call.</span></span>
    
10. <span data-ttu-id="e635c-148">在 [**代理**程式] 中，指定您要建立的代理清單的方式：</span><span class="sxs-lookup"><span data-stu-id="e635c-148">In **Agents**, specify how you want to create your agents list:</span></span>
    
    - <span data-ttu-id="e635c-149">若要使用自訂的代理清單，請按一下 [**定義自訂的代理群組**]，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="e635c-149">To use a custom list of agents, click **Define a custom group of agents**, and do one of the following:</span></span>
    
    - <span data-ttu-id="e635c-150">若要將使用者新增到 [代理] 群組，請按一下 [**選取**]，然後在 [**選取代理**搜尋] 欄位中，輸入您要新增至此群組的所有或部分名稱，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="e635c-150">To add a user to the agent group, click **Select**, and then in the **Select Agents** search field, type all or part of the name of the user that you want to add to this group, and then click **Find**.</span></span> <span data-ttu-id="e635c-151">在產生的代理清單中，按一下使用者，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e635c-151">In the resulting list of agents, click the user, and then click **OK**.</span></span>
    
    - <span data-ttu-id="e635c-152">若要從 [代理] 群組中移除使用者，請在 [代理程式清單] 中，按一下您要移除的使用者，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="e635c-152">To remove a user from the agent group, in the list of agents, click the user you want to remove, and then click **Remove**.</span></span>
    
    - <span data-ttu-id="e635c-153">若要變更代理在使用迴圈路由或串列路由的群組中提供來電的順序，請在 [代理程式清單] 中，按一下使用者，然後按一下向上箭號或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="e635c-153">To change the order in which agents are offered calls in groups that use either round robin routing or serial routing, in the list of agents, click a user, and then click the up arrow or down arrow.</span></span> 
    
    - <span data-ttu-id="e635c-154">若要使用 Microsoft Exchange Server 通訊群組清單作為代理群組，請按一下 [**使用現有的電子郵件通訊群組清單**]，然後在 [**通訊群組清單位址**] 中，輸入通訊群組清單的電子郵件地址（例如，NetworkSupport@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="e635c-154">To use a Microsoft Exchange Server distribution list as your agent group, click **Use an existing email distribution list**, and then in **Distribution list address**, type the email address of the distribution list (for example, NetworkSupport@contoso.com).</span></span>
    
      <span data-ttu-id="e635c-155">如果您使用電子郵件通訊群組清單，您會受到下列限制：</span><span class="sxs-lookup"><span data-stu-id="e635c-155">If you use an email distribution list, you are subject to the following constraints:</span></span>
    
      - <span data-ttu-id="e635c-156">您無法針對 [代理] 群組選取多個通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="e635c-156">You cannot select multiple distribution lists for the agent group.</span></span> <span data-ttu-id="e635c-157">每個群組只支援單一通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="e635c-157">Each group supports only a single distribution list.</span></span>
    
      - <span data-ttu-id="e635c-158">如果通訊群組清單包含一或多個通訊群組清單，則嵌套通訊群組清單的成員不會新增到 [代理程式清單]。</span><span class="sxs-lookup"><span data-stu-id="e635c-158">If the distribution list contains one or more distribution lists, members of the nested distribution lists are not added to the agent list.</span></span>
    
      - <span data-ttu-id="e635c-159">如果已選取 [串列或迴圈路由]，伺服器會根據路由方法及代理在通訊群組清單中的顯示順序，將來電提供給適當的代理程式。</span><span class="sxs-lookup"><span data-stu-id="e635c-159">If serial or round robin routing is selected, the server offers an incoming call to the appropriate agent according to the routing method and according to the order in which agents are listed in the distribution list.</span></span>
    
      - <span data-ttu-id="e635c-160">如果通訊群組清單中包含已啟用 Lync Server 2010 的使用者，但尚未啟用企業語音，則會將它們以 dysfunctional agent 的形式新增到 agent 群組中。</span><span class="sxs-lookup"><span data-stu-id="e635c-160">If the distribution list contains users for which Lync Server 2010 is enabled but Enterprise Voice is not enabled, they will be added to the agent group as dysfunctional agents.</span></span> <span data-ttu-id="e635c-161">請確定通訊群組清單的所有成員都已針對其使用者帳戶啟用企業語音功能。</span><span class="sxs-lookup"><span data-stu-id="e635c-161">Make sure that all members of the distribution list have Enterprise Voice enabled for their user accounts.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e635c-162">如果您使用電子郵件通訊群組清單，回應群組管理員或使用者可能會看到隱藏的成員資格或隱藏清單。</span><span class="sxs-lookup"><span data-stu-id="e635c-162">If you use an email distribution list, hidden memberships or hidden lists might become visible to the Response Group administrator or users.</span></span> 
  
    <span data-ttu-id="e635c-163">隱藏的成員資格或隱藏清單可能會變成可見，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e635c-163">Hidden memberships or hidden lists can become visible as follows:</span></span>
    
     - <span data-ttu-id="e635c-164">如果已將通訊群組清單設定為隱藏成員資格，且回應群組管理員將通訊群組清單指派給 agent 清單，則使用者可以呼叫該群組來找出成員是誰。</span><span class="sxs-lookup"><span data-stu-id="e635c-164">If a distribution list was configured so that the membership is hidden and the Response Group administrator assigns the distribution list to the agent list, users can call the group to find out who the members are.</span></span> 
    
     - <span data-ttu-id="e635c-165">如果通訊群組清單已設定為在 Exchange 全域通訊清單中隱藏，回應群組管理員可能可以查看通訊群組清單，並將它指派給 agent 清單（如果回應群組進程具有適當的使用者權利），而且許可權，即使系統管理員沒有適當的使用者權利和許可權也一樣。</span><span class="sxs-lookup"><span data-stu-id="e635c-165">If a distribution list was configured so that it is hidden in the Exchange Global Address List, the Response Group administrator might be able to see the distribution list and assign it to the agent list if the Response Group process has the appropriate user rights and permissions, even if the administrator does not have the appropriate user rights and permissions.</span></span>
    
11. <span data-ttu-id="e635c-166">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e635c-166">Click **Commit**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-agent-group"></a><span data-ttu-id="e635c-167">若要使用商務用 Skype Server Management Shell 來建立或修改代理群組</span><span class="sxs-lookup"><span data-stu-id="e635c-167">To use Skype for Business Server Management Shell to create or modify an agent group</span></span>

1. <span data-ttu-id="e635c-168">以 RTCUniversalServerAdmins 群組成員的身分登入，或以支援回應群組的預先定義之系統管理角色的成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="e635c-168">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="e635c-169">啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="e635c-169">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="e635c-170">使用 [**新-CsRgsAgentGroup** ] 來建立新的代理群組。</span><span class="sxs-lookup"><span data-stu-id="e635c-170">Use **New-CsRgsAgentGroup** to create a new agent group.</span></span> <span data-ttu-id="e635c-171">使用 [**設定] CsRgsAgentGroup**修改現有的代理群組。</span><span class="sxs-lookup"><span data-stu-id="e635c-171">Use **Set-CsRgsAgentGroup** to modify an existing agent group.</span></span> <span data-ttu-id="e635c-172">在命令列上執行：</span><span class="sxs-lookup"><span data-stu-id="e635c-172">At the command line, run:</span></span>
    
   ```powershell
   New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
   ```

    <span data-ttu-id="e635c-173">例如：</span><span class="sxs-lookup"><span data-stu-id="e635c-173">For example:</span></span>
    
   ```powershell
   New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="e635c-174">Agent 警示時間設定不能超過180秒。</span><span class="sxs-lookup"><span data-stu-id="e635c-174">The agent alert time setting cannot exceed 180 seconds.</span></span> <span data-ttu-id="e635c-175">如果 agent 警示時間超過180秒，用戶端應用程式會拒絕呼叫，因為 SIP 事務計時器達到最大等待時間。</span><span class="sxs-lookup"><span data-stu-id="e635c-175">If the agent alert time is greater than 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span> 
  
4. <span data-ttu-id="e635c-176">確認已建立 [代理] 群組。</span><span class="sxs-lookup"><span data-stu-id="e635c-176">Confirm that the agent group is created.</span></span> <span data-ttu-id="e635c-177">用盡</span><span class="sxs-lookup"><span data-stu-id="e635c-177">Run:</span></span>
    
   ```powershell
   Get-CsRgsAgentGroup -Name "Help Desk"
   ```

## <a name="see-also"></a><span data-ttu-id="e635c-178">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e635c-178">See also</span></span>

[<span data-ttu-id="e635c-179">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="e635c-179">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
  
[<span data-ttu-id="e635c-180">新-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="e635c-180">New-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
[<span data-ttu-id="e635c-181">Set-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="e635c-181">Set-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsagentgroup?view=skype-ps)
  
[<span data-ttu-id="e635c-182">CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="e635c-182">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsagentgroup?view=skype-ps)
