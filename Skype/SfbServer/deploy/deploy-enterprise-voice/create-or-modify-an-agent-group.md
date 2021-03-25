---
title: 在商務用 Skype 中建立或修改代理人群組
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
description: 在 [商務用 Skype 伺服器 Enterprise Voice] 中，以回應群組建立或修改代理程式群組。
ms.openlocfilehash: 0c0e7d54008ba6affa2bae5bd3228c93e430a114
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105809"
---
# <a name="create-or-modify-an-agent-group-in-skype-for-business"></a><span data-ttu-id="d3d71-103">在商務用 Skype 中建立或修改代理人群組</span><span class="sxs-lookup"><span data-stu-id="d3d71-103">Create or modify an agent group in Skype for Business</span></span>
 
<span data-ttu-id="d3d71-104">在 [商務用 Skype 伺服器 Enterprise Voice] 中，以回應群組建立或修改代理程式群組。</span><span class="sxs-lookup"><span data-stu-id="d3d71-104">Create or modify an agent group in Response Group, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="d3d71-105">當您建立代理群組時，需要選取指派給該群組的代理，並指定額外的群組設定，例如路由方法以及代理是否可以登入和登出群組。</span><span class="sxs-lookup"><span data-stu-id="d3d71-105">When you create an agent group, you select the agents that are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span> 
  
<span data-ttu-id="d3d71-106">必須登入和登出群組的代理商，該代理程式不會登入或登出商務用 Skype，稱為正式代理程式。</span><span class="sxs-lookup"><span data-stu-id="d3d71-106">An agent who must sign in and out of the group, which is different from signing in or out of Skype for Business, is called a formal agent.</span></span> <span data-ttu-id="d3d71-107">正式代理必須先登入此群組，才可以接聽路由傳送到此群組的電話。</span><span class="sxs-lookup"><span data-stu-id="d3d71-107">Formal agents must be signed in to the group before they can receive calls routed to the group.</span></span> <span data-ttu-id="d3d71-108">對於以兼職身分接聽群組來電的代理而言，這可能相當實用。</span><span class="sxs-lookup"><span data-stu-id="d3d71-108">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="d3d71-109">正式代理程式會按一下商務用 Skype 中的功能表項目，以開啟 Windows Internet Explorer Internet 瀏覽器，並顯示網頁主控台，以登入和登出其群組。</span><span class="sxs-lookup"><span data-stu-id="d3d71-109">Formal agents sign in and out of their groups by clicking a menu item in Skype for Business to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>
  
<span data-ttu-id="d3d71-110">未登入或登出群組的代理人稱為「非正式代理人」。</span><span class="sxs-lookup"><span data-stu-id="d3d71-110">An agent who does not sign in or out of the group is called an informal agent.</span></span> <span data-ttu-id="d3d71-111">非正式代理程式會在登入商務用 Skype 時自動登入至群組，且無法登出群組。</span><span class="sxs-lookup"><span data-stu-id="d3d71-111">Informal agents are automatically signed in to the group when they sign in to Skype for Business, and they cannot sign out of the group.</span></span>
  
<span data-ttu-id="d3d71-p103">只有內部部署的使用者可以成為代理人。如果將代理人從內部部署移至線上，回應群組電話將無法路由傳送給該代理人。</span><span class="sxs-lookup"><span data-stu-id="d3d71-p103">Only on-premises users can be agents. If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>
  
<span data-ttu-id="d3d71-114">使用下列其中一個程式來建立或修改代理程式群組。</span><span class="sxs-lookup"><span data-stu-id="d3d71-114">Use one of the following procedures to create or modify an agent group.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d3d71-p104">當您將使用者指派為回應群組代理人時，如果他們已啟用隱私權模式，請通知他們需要搜尋 "RGS Presence Watcher" 連絡人並將他們新增到其連絡人清單。已啟用隱私權模式但其連絡人清單中沒有 "RGS Presence Watcher" 的代理人，無法接收到打給回應群組的電話。未啟用隱私權模式的代理人則不受影響。</span><span class="sxs-lookup"><span data-stu-id="d3d71-p104">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list. Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group. Agents who do not have Privacy mode enabled are not affected.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-an-agent-group"></a><span data-ttu-id="d3d71-118">使用商務用 Skype Server 控制台建立或修改代理程式群組</span><span class="sxs-lookup"><span data-stu-id="d3d71-118">To use Skype for Business Server Control Panel to create or modify an agent group</span></span>

1. <span data-ttu-id="d3d71-119">以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="d3d71-119">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d3d71-120">如果您是受管理工作流程的其中一位委派回應群組管理員，您可以在您管理的工作流程中建立群組並加以使用。</span><span class="sxs-lookup"><span data-stu-id="d3d71-120">If you are one of the delegated Response Group Managers for a managed workflow, you can create groups and use them in the workflows that you manage.</span></span> 
  
2. <span data-ttu-id="d3d71-121">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="d3d71-121">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="d3d71-122">在左側導覽列中，按一下 **[回應群組]**，然後按一下 **[群組]**。</span><span class="sxs-lookup"><span data-stu-id="d3d71-122">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>
    
4. <span data-ttu-id="d3d71-123">在 [ **群組** ] 頁面上，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="d3d71-123">On the **Group** page, do one of the following:</span></span>
    
   - <span data-ttu-id="d3d71-124">若要建立新的代理人群組，請按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="d3d71-124">To create a new agent group, click **New**.</span></span> <span data-ttu-id="d3d71-125">在 [ **選取服務** ] 搜尋欄位中，輸入您要在其中新增群組之 **ApplicationServer** 服務的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="d3d71-125">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service where you want to add the group.</span></span> <span data-ttu-id="d3d71-126">在產生的服務清單中，按一下您想要的服務，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d3d71-126">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="d3d71-127">若要修改現有的代理人群組，請在 [搜尋] 欄位中輸入 agent 群組的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="d3d71-127">To modify an existing agent group, type all or part of the name of the agent group in the search field.</span></span> <span data-ttu-id="d3d71-128">在產生的清單中，按一下您想要的群組，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="d3d71-128">In the resulting list, click the group that you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="d3d71-129">在 [ **名稱**] 中，輸入代理人群組的識別名稱。</span><span class="sxs-lookup"><span data-stu-id="d3d71-129">In **Name**, type an identifying name for the agent group.</span></span>
    
6. <span data-ttu-id="d3d71-130">在 **[描述]** 中，輸入群組的描述。</span><span class="sxs-lookup"><span data-stu-id="d3d71-130">In **Description**, type a description for the group.</span></span>
    
7. <span data-ttu-id="d3d71-131">在 **[參與原則]** 中，選取下列其中一項作業來設定群組的登入行為：</span><span class="sxs-lookup"><span data-stu-id="d3d71-131">In the **Participation policy**, select one of the following to set up the sign-in behavior for the group:</span></span>
    
   - <span data-ttu-id="d3d71-132">選取 **[非正式]** 指定群組中的專員不需要登入及登出群組。</span><span class="sxs-lookup"><span data-stu-id="d3d71-132">Select **Informal** to specify that agents in the group do not need to sign in and out of the group.</span></span> <span data-ttu-id="d3d71-133">當代理人登入商務用 Skype 時，會自動登入群組。</span><span class="sxs-lookup"><span data-stu-id="d3d71-133">Agents are automatically signed in to the group when they sign in to Skype for Business.</span></span>
    
   - <span data-ttu-id="d3d71-134">選取 **[正式]** 指定群組中的專員必須登入和登出群組。</span><span class="sxs-lookup"><span data-stu-id="d3d71-134">Select **Formal** to specify that agents in the group must sign in and out of the group.</span></span> <span data-ttu-id="d3d71-135">當您選取此選項時，代理程式會按一下商務用 Skype 中的功能表項目，以開啟 Internet Explorer，並顯示網頁主控台以登入和登出群組。</span><span class="sxs-lookup"><span data-stu-id="d3d71-135">When you select this option, agents click a menu item in Skype for Business to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>
    
8. <span data-ttu-id="d3d71-136">在 **[警示時間 (秒)]** 中，指定專員的電話響幾秒 (預設值為 20 秒) 後會轉給下一個線上專員。</span><span class="sxs-lookup"><span data-stu-id="d3d71-136">In **Alert time (seconds)**, specify the number of seconds to ring an agent before offering the call to the next available agent (the default is 20 seconds).</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d3d71-137">「代理程式警示時間」設定不得超過180秒。</span><span class="sxs-lookup"><span data-stu-id="d3d71-137">The agent alert time setting cannot exceed 180 seconds.</span></span> <span data-ttu-id="d3d71-138">如果代理程式警示時間超過180秒，用戶端應用程式會拒絕呼叫，因為 SIP 交易計時器已達到其最長等待時間。</span><span class="sxs-lookup"><span data-stu-id="d3d71-138">If the agent alert time exceeds 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span> 
  
9. <span data-ttu-id="d3d71-139">在 **[路由方法]** 中，選取將電話路由轉送給群組專員的方式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d3d71-139">In **Routing method**, select the method for routing calls to agents in the group as follows:</span></span>
    
   - <span data-ttu-id="d3d71-140">若 **要在已** 閒置最長 (的代理商中提供新來電，而該代理商的 **商務用 Skype** 最長) ，請按一下 [**最長閒置**]。</span><span class="sxs-lookup"><span data-stu-id="d3d71-140">To offer a new call first to the agent who has been idle the longest (has had a presence of **Available** or **Inactive** in Skype for Business the longest), click **Longest idle**.</span></span> 
    
   - <span data-ttu-id="d3d71-p110">若要將新電話同時提供給所有的線上專員，請按一下 **[平行]**。該電話會路由傳送給第一個接聽的專員。</span><span class="sxs-lookup"><span data-stu-id="d3d71-p110">To offer a new call to all available agents at the same time, click **Parallel**. The call is sent to the first agent who accepts it.</span></span>
    
   - <span data-ttu-id="d3d71-143">若要將新電話輪流提供給每個專員，請按一下 **[循環配置資源]**。</span><span class="sxs-lookup"><span data-stu-id="d3d71-143">To offer a new call to each agent in turn, click **Round robin**.</span></span> 
    
   - <span data-ttu-id="d3d71-144">若要永遠依照 **[專員]** 清單中的順序將新的來電提供給專員，請按一下 **[序列]**。</span><span class="sxs-lookup"><span data-stu-id="d3d71-144">To always offer a new call to the agents in the order in which they are listed in the **Agent** list, click **Serial**.</span></span> 
    
   - <span data-ttu-id="d3d71-145">若要為登入商務用 Skype 和回應群組應用程式的所有代理人提供新呼叫，不論其目前目前狀態為何， **請按一下 [** 語音應答]。</span><span class="sxs-lookup"><span data-stu-id="d3d71-145">To offer a new call to all agents who are signed into Skype for Business and the Response Group application at the same time, regardless of their current presence, click **Attendant**.</span></span> <span data-ttu-id="d3d71-146">設定為代理人的使用者可以查看所有等待的來電，並以任何順序接聽等候通話。</span><span class="sxs-lookup"><span data-stu-id="d3d71-146">Users who are configured as agents can see all the calls that are waiting and answer waiting calls in any order.</span></span> <span data-ttu-id="d3d71-147">通話會傳送給第一個接受此通話的代理商，在此之後，其他代理程式就不再看到通話。</span><span class="sxs-lookup"><span data-stu-id="d3d71-147">The call is sent to the first agent who accepts it, after which the other agents no longer see the call.</span></span>
    
10. <span data-ttu-id="d3d71-148">在 [ **代理人**] 中，指定您要如何建立代理人清單：</span><span class="sxs-lookup"><span data-stu-id="d3d71-148">In **Agents**, specify how you want to create your agents list:</span></span>
    
    - <span data-ttu-id="d3d71-149">若要使用自訂的代理人清單，請按一下 [ **定義代理人的自訂群組**]，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="d3d71-149">To use a custom list of agents, click **Define a custom group of agents**, and do one of the following:</span></span>
    
    - <span data-ttu-id="d3d71-150">若要將使用者新增至代理人群組，請按一下 [ **選取**]，然後在 [ **選取代理** 搜尋] 欄位中，輸入您要新增至此群組的使用者名稱全部或部分名稱，然後按一下 [ **尋找**]。</span><span class="sxs-lookup"><span data-stu-id="d3d71-150">To add a user to the agent group, click **Select**, and then in the **Select Agents** search field, type all or part of the name of the user that you want to add to this group, and then click **Find**.</span></span> <span data-ttu-id="d3d71-151">在產生的代理程式清單中，按一下使用者，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d3d71-151">In the resulting list of agents, click the user, and then click **OK**.</span></span>
    
    - <span data-ttu-id="d3d71-152">若要從代理人群組中移除使用者，請在代理程式清單中，按一下您要移除的使用者，然後按一下 [ **移除**]。</span><span class="sxs-lookup"><span data-stu-id="d3d71-152">To remove a user from the agent group, in the list of agents, click the user you want to remove, and then click **Remove**.</span></span>
    
    - <span data-ttu-id="d3d71-153">若要變更代理程式在使用迴圈傳送或串列路由的群組中提供通話的順序，請在代理程式清單中，按一下使用者，然後按一下向上鍵或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="d3d71-153">To change the order in which agents are offered calls in groups that use either round robin routing or serial routing, in the list of agents, click a user, and then click the up arrow or down arrow.</span></span> 
    
    - <span data-ttu-id="d3d71-154">若要使用 Microsoft Exchange Server 通訊群組清單作為代理人群組，請按一下 [ **使用現有的電子郵件通訊群組清單**]，然後在 [ **通訊群組清單位址**] 中，輸入通訊群組清單的電子郵件地址 (例如，NetworkSupport@contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="d3d71-154">To use a Microsoft Exchange Server distribution list as your agent group, click **Use an existing email distribution list**, and then in **Distribution list address**, type the email address of the distribution list (for example, NetworkSupport@contoso.com).</span></span>
    
      <span data-ttu-id="d3d71-155">如果您使用電子郵件通訊群組清單，您會受到下列限制：</span><span class="sxs-lookup"><span data-stu-id="d3d71-155">If you use an email distribution list, you are subject to the following constraints:</span></span>
    
      - <span data-ttu-id="d3d71-p113">您無法為專員群組選取多個通訊群組清單。每一個群組只支援一個通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="d3d71-p113">You cannot select multiple distribution lists for the agent group. Each group supports only a single distribution list.</span></span>
    
      - <span data-ttu-id="d3d71-158">如果通訊群組清單包含一或多個通訊群組清單，則巢狀通訊群組清單的成員不會加入到專員清單中。</span><span class="sxs-lookup"><span data-stu-id="d3d71-158">If the distribution list contains one or more distribution lists, members of the nested distribution lists are not added to the agent list.</span></span>
    
      - <span data-ttu-id="d3d71-159">如果選取了串列或迴圈複用路由，則伺服器會根據路由方法以及代理列在通訊群組清單中的順序，向適當的代理人提供來電。</span><span class="sxs-lookup"><span data-stu-id="d3d71-159">If serial or round robin routing is selected, the server offers an incoming call to the appropriate agent according to the routing method and according to the order in which agents are listed in the distribution list.</span></span>
    
      - <span data-ttu-id="d3d71-160">如果通訊群組清單包含的使用者已啟用 Lync Server 2010，但是未啟用 Enterprise Voice，他們會以 dysfunctional 代理程式的形式新增至代理人群組。</span><span class="sxs-lookup"><span data-stu-id="d3d71-160">If the distribution list contains users for which Lync Server 2010 is enabled but Enterprise Voice is not enabled, they will be added to the agent group as dysfunctional agents.</span></span> <span data-ttu-id="d3d71-161">請確定通訊群組清單的所有成員都已啟用企業語音的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="d3d71-161">Make sure that all members of the distribution list have Enterprise Voice enabled for their user accounts.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d3d71-162">如果您使用電子郵件通訊群組清單，回應群組管理員或使用者可能會看到隱藏的成員資格或隱藏的清單。</span><span class="sxs-lookup"><span data-stu-id="d3d71-162">If you use an email distribution list, hidden memberships or hidden lists might become visible to the Response Group administrator or users.</span></span> 
  
    <span data-ttu-id="d3d71-163">在下列情況下，隱藏的成員資格或隱藏的清單會顯現出來：</span><span class="sxs-lookup"><span data-stu-id="d3d71-163">Hidden memberships or hidden lists can become visible as follows:</span></span>
    
     - <span data-ttu-id="d3d71-164">如果已設定通訊群組清單以便隱藏成員資格，且回應群組管理員將通訊群組清單指派給代理人清單，則使用者可以呼叫群組以找出成員是誰。</span><span class="sxs-lookup"><span data-stu-id="d3d71-164">If a distribution list was configured so that the membership is hidden and the Response Group administrator assigns the distribution list to the agent list, users can call the group to find out who the members are.</span></span> 
    
     - <span data-ttu-id="d3d71-165">如果已設定通訊群組清單，使其在 Exchange 全域通訊清單中隱藏，回應群組管理員可能會看到通訊群組清單，並將其指派給代理人清單，如果回應群組處理具有適當的使用者權限，即使系統管理員沒有適當的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="d3d71-165">If a distribution list was configured so that it is hidden in the Exchange Global Address List, the Response Group administrator might be able to see the distribution list and assign it to the agent list if the Response Group process has the appropriate user rights and permissions, even if the administrator does not have the appropriate user rights and permissions.</span></span>
    
11. <span data-ttu-id="d3d71-166">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="d3d71-166">Click **Commit**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-agent-group"></a><span data-ttu-id="d3d71-167">若要使用商務用 Skype Server 管理命令介面來建立或修改代理程式群組</span><span class="sxs-lookup"><span data-stu-id="d3d71-167">To use Skype for Business Server Management Shell to create or modify an agent group</span></span>

1. <span data-ttu-id="d3d71-168">以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="d3d71-168">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="d3d71-169">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="d3d71-169">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="d3d71-170">使用 **New-CsRgsAgentGroup** 建立新的代理人群組。</span><span class="sxs-lookup"><span data-stu-id="d3d71-170">Use **New-CsRgsAgentGroup** to create a new agent group.</span></span> <span data-ttu-id="d3d71-171">使用 **get-csrgsagentgroup** 來修改現有的代理人群組。</span><span class="sxs-lookup"><span data-stu-id="d3d71-171">Use **Set-CsRgsAgentGroup** to modify an existing agent group.</span></span> <span data-ttu-id="d3d71-172">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="d3d71-172">At the command line, run:</span></span>
    
   ```powershell
   New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
   ```

    <span data-ttu-id="d3d71-173">例如：</span><span class="sxs-lookup"><span data-stu-id="d3d71-173">For example:</span></span>
    
   ```powershell
   New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="d3d71-174">「代理程式警示時間」設定不得超過180秒。</span><span class="sxs-lookup"><span data-stu-id="d3d71-174">The agent alert time setting cannot exceed 180 seconds.</span></span> <span data-ttu-id="d3d71-175">如果代理程式警示時間大於180秒，用戶端應用程式會拒絕呼叫，因為 SIP 交易計時器已達到其最長等待時間。</span><span class="sxs-lookup"><span data-stu-id="d3d71-175">If the agent alert time is greater than 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span> 
  
4. <span data-ttu-id="d3d71-176">確認已建立代理人群組。</span><span class="sxs-lookup"><span data-stu-id="d3d71-176">Confirm that the agent group is created.</span></span> <span data-ttu-id="d3d71-177">執行：</span><span class="sxs-lookup"><span data-stu-id="d3d71-177">Run:</span></span>
    
   ```powershell
   Get-CsRgsAgentGroup -Name "Help Desk"
   ```

## <a name="see-also"></a><span data-ttu-id="d3d71-178">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d3d71-178">See also</span></span>

[<span data-ttu-id="d3d71-179">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="d3d71-179">Get-CsService</span></span>](/powershell/module/skype/get-csservice?view=skype-ps)
  
[<span data-ttu-id="d3d71-180">New-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="d3d71-180">New-CsRgsAgentGroup</span></span>](/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
[<span data-ttu-id="d3d71-181">Get-csrgsagentgroup</span><span class="sxs-lookup"><span data-stu-id="d3d71-181">Set-CsRgsAgentGroup</span></span>](/powershell/module/skype/set-csrgsagentgroup?view=skype-ps)
  
[<span data-ttu-id="d3d71-182">Get-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="d3d71-182">Get-CsRgsAgentGroup</span></span>](/powershell/module/skype/get-csrgsagentgroup?view=skype-ps)