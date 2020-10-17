---
title: Lync Server 2013：建立或修改代理程式群組
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an agent group
ms:assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205370(v=OCS.15)
ms:contentKeyID: 48185784
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 874b73af42869bc5cbe6a66b7efaf792d231b95d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525750"
---
# <a name="create-or-modify-an-agent-group-in-lync-server-2013"></a><span data-ttu-id="d4e8b-102">在 Lync Server 2013 中建立或修改代理程式群組</span><span class="sxs-lookup"><span data-stu-id="d4e8b-102">Create or modify an agent group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4e8b-103">_**主題上次修改日期：** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="d4e8b-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="d4e8b-104">使用下列其中一個程式來建立或修改代理程式群組。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-104">Use one of the following procedures to create or modify an agent group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d4e8b-105">例如，管理員（CsVoiceAdministrator）必須先啟用使用者的 Enterprise Voice 和 Lync Server，使用者才能將使用者指派給代理人群組。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-105">An Administrator—for example, CsVoiceAdministrator—must enable users for Enterprise Voice and Lync Server before the users can be assigned to agent groups.</span></span> <span data-ttu-id="d4e8b-106">如果您是受管理工作流程的其中一位委派回應群組管理員，您可以在您管理的工作流程中建立代理人群組和使用代理人群組。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-106">If you are one of the delegated Response Group Managers for a managed workflow, you can create agent groups and use the agent groups in the workflows that you manage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d4e8b-p102">當您將使用者指派為回應群組代理人時，如果他們已啟用隱私權模式，請通知他們需要搜尋 "RGS Presence Watcher" 連絡人並將他們新增到其連絡人清單。已啟用隱私權模式但其連絡人清單中沒有 "RGS Presence Watcher" 的代理人，無法接收到打給回應群組的電話。未啟用隱私權模式的代理人則不受影響。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-p102">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list. Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group. Agents who do not have Privacy mode enabled are not affected.</span></span>



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-an-agent-group"></a><span data-ttu-id="d4e8b-110">使用 Lync Server 控制台建立或修改代理程式群組</span><span class="sxs-lookup"><span data-stu-id="d4e8b-110">To use Lync Server Control Panel to create or modify an agent group</span></span>

1.  <span data-ttu-id="d4e8b-111">以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-111">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d4e8b-112">如果您是受管理工作流程的其中一位委派回應群組管理員，您可以在您管理的工作流程中建立群組並加以使用。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-112">If you are one of the delegated Response Group Managers for a managed workflow, you can create groups and use them in the workflows that you manage.</span></span>

    
    </div>

2.  <span data-ttu-id="d4e8b-113">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d4e8b-114">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d4e8b-115">在左側導覽列中，按一下 **[回應群組]**，然後按一下 **[群組]**。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-115">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>

4.  <span data-ttu-id="d4e8b-116">在 [ **群組** ] 頁面上，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="d4e8b-116">On the **Group** page, do one of the following:</span></span>
    
      - <span data-ttu-id="d4e8b-117">若要建立新的代理人群組，請按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-117">To create a new agent group, click **New**.</span></span> <span data-ttu-id="d4e8b-118">在 [ **選取服務** ] 搜尋欄位中，輸入您要在其中新增群組之 **ApplicationServer** 服務的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-118">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service where you want to add the group.</span></span> <span data-ttu-id="d4e8b-119">在產生的服務清單中，按一下您想要的服務，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-119">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="d4e8b-120">若要修改現有的代理人群組，請在 [搜尋] 欄位中輸入 agent 群組的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-120">To modify an existing agent group, type all or part of the name of the agent group in the search field.</span></span> <span data-ttu-id="d4e8b-121">在產生的清單中，按一下您想要的群組，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-121">In the resulting list, click the group that you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="d4e8b-122">在 [ **名稱**] 中，輸入代理人群組的識別名稱。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-122">In **Name**, type an identifying name for the agent group.</span></span>

6.  <span data-ttu-id="d4e8b-123">在 **[描述]** 中，輸入群組的描述。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-123">In **Description**, type a description for the group.</span></span>

7.  <span data-ttu-id="d4e8b-124">在 **[參與原則]** 中，選取下列其中一項作業來設定群組的登入行為：</span><span class="sxs-lookup"><span data-stu-id="d4e8b-124">In the **Participation policy**, select one of the following to set up the sign-in behavior for the group:</span></span>
    
      - <span data-ttu-id="d4e8b-125">選取 **[非正式]** 指定群組中的專員不需要登入及登出群組。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-125">Select **Informal** to specify that agents in the group do not need to sign in and out of the group.</span></span> <span data-ttu-id="d4e8b-126">當代理人登入 Lync Server 2013 時，會自動登入群組。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-126">Agents are automatically signed in to the group when they sign in to Lync Server 2013.</span></span>
    
      - <span data-ttu-id="d4e8b-127">選取 **[正式]** 指定群組中的專員必須登入和登出群組。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-127">Select **Formal** to specify that agents in the group must sign in and out of the group.</span></span> <span data-ttu-id="d4e8b-128">當您選取此選項時，代理程式會按一下 Lync 中的功能表項目以開啟 Internet Explorer，並顯示網頁主控台以供登入和登出群組。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-128">When you select this option, agents click a menu item in Lync to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>

8.  <span data-ttu-id="d4e8b-129">在 **[警示時間 (秒)]** 中，指定專員的電話響幾秒 (預設值為 20 秒) 後會轉給下一個線上專員。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-129">In **Alert time (seconds)**, specify the number of seconds to ring an agent before offering the call to the next available agent (the default is 20 seconds).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d4e8b-130">「代理程式警示時間」設定不得超過180秒。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-130">The agent alert time setting cannot exceed 180 seconds.</span></span> <span data-ttu-id="d4e8b-131">如果代理程式警示時間超過180秒，用戶端應用程式會拒絕呼叫，因為 SIP 交易計時器已達到其最長等待時間。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-131">If the agent alert time exceeds 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span>

    
    </div>

9.  <span data-ttu-id="d4e8b-132">在 **[路由方法]** 中，選取將電話路由轉送給群組專員的方式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d4e8b-132">In **Routing method**, select the method for routing calls to agents in the group as follows:</span></span>
    
      - <span data-ttu-id="d4e8b-133">若要先對閒置最長 (的代理商提供新呼叫，使其在 Lync Server 中的狀態為 [ **可用** ] 或 [ **非** 使用中] 的時間最長的) ，請按一下 [ **最長閒置**]。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-133">To offer a new call first to the agent who has been idle the longest (has had a presence of **Available** or **Inactive** in Lync Server the longest), click **Longest idle**.</span></span>
    
      - <span data-ttu-id="d4e8b-p109">若要將新電話同時提供給所有的線上專員，請按一下 **[平行]**。該電話會路由傳送給第一個接聽的專員。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-p109">To offer a new call to all available agents at the same time, click **Parallel**. The call is sent to the first agent who accepts it.</span></span>
    
      - <span data-ttu-id="d4e8b-136">若要將新電話輪流提供給每個專員，請按一下 **[循環配置資源]**。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-136">To offer a new call to each agent in turn, click **Round robin**.</span></span>
    
      - <span data-ttu-id="d4e8b-137">若要永遠依照 **[專員]** 清單中的順序將新的來電提供給專員，請按一下 **[序列]**。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-137">To always offer a new call to the agents in the order in which they are listed in the **Agent** list, click **Serial**.</span></span>
    
      - <span data-ttu-id="d4e8b-138">若要同時登入 Lync Server 2013 和回應群組應用程式的新呼叫，不論其目前目前狀態為何， **請按一下 [** 語音應答]。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-138">To offer a new call to all agents who are signed into Lync Server 2013 and the Response Group application at the same time, regardless of their current presence, click **Attendant**.</span></span> <span data-ttu-id="d4e8b-139">設定為代理人的 Lync 2010 語音應答使用者可以查看所有等待的來電，並以任何順序接聽等候通話。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-139">Lync 2010 Attendant users who are configured as agents can see all the calls that are waiting and answer waiting calls in any order.</span></span> <span data-ttu-id="d4e8b-140">呼叫會傳送給第一個接受它的代理商，之後其他的 Lync 2010 語音應答使用者就不會再看到通話。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-140">The call is sent to the first agent who accepts it, after which the other Lync 2010 Attendant users no longer see the call.</span></span>

10. <span data-ttu-id="d4e8b-141">在 [ **代理人**] 中，指定您要如何建立代理人清單：</span><span class="sxs-lookup"><span data-stu-id="d4e8b-141">In **Agents**, specify how you want to create your agents list:</span></span>
    
      - <span data-ttu-id="d4e8b-142">若要使用自訂的代理人清單，請按一下 [ **定義代理人的自訂群組**]，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="d4e8b-142">To use a custom list of agents, click **Define a custom group of agents**, and do one of the following:</span></span>
        
          - <span data-ttu-id="d4e8b-143">若要將使用者新增至代理人群組，請按一下 [ **選取**]，然後在 [ **選取代理** 搜尋] 欄位中，輸入您要新增至此群組的使用者名稱全部或部分名稱，然後按一下 [ **尋找**]。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-143">To add a user to the agent group, click **Select**, and then in the **Select Agents** search field, type all or part of the name of the user that you want to add to this group, and then click **Find**.</span></span> <span data-ttu-id="d4e8b-144">在產生的代理程式清單中，按一下使用者，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-144">In the resulting list of agents, click the user, and then click **OK**.</span></span>
        
          - <span data-ttu-id="d4e8b-145">若要從代理人群組中移除使用者，請在代理程式清單中，按一下您要移除的使用者，然後按一下 [ **移除**]。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-145">To remove a user from the agent group, in the list of agents, click the user you want to remove, and then click **Remove**.</span></span>
        
          - <span data-ttu-id="d4e8b-146">若要變更代理程式在使用迴圈傳送或串列路由的群組中提供通話的順序，請在代理程式清單中，按一下使用者，然後按一下向上鍵或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-146">To change the order in which agents are offered calls in groups that use either round robin routing or serial routing, in the list of agents, click a user, and then click the up arrow or down arrow.</span></span>
    
      - <span data-ttu-id="d4e8b-147">若要使用 Microsoft Exchange Server 通訊群組清單作為代理人群組，請按一下 [ **使用現有的電子郵件通訊群組清單**]，然後在 [ **通訊群組清單位址**] 中，輸入通訊群組清單的電子郵件地址 (例如，NetworkSupport@contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-147">To use a Microsoft Exchange Server distribution list as your agent group, click **Use an existing email distribution list**, and then in **Distribution list address**, type the email address of the distribution list (for example, NetworkSupport@contoso.com).</span></span>
        
        <span data-ttu-id="d4e8b-148">如果您使用電子郵件通訊群組清單，您會受到下列限制：</span><span class="sxs-lookup"><span data-stu-id="d4e8b-148">If you use an email distribution list, you are subject to the following constraints:</span></span>
        
          - <span data-ttu-id="d4e8b-p112">您無法為專員群組選取多個通訊群組清單。每一個群組只支援一個通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-p112">You cannot select multiple distribution lists for the agent group. Each group supports only a single distribution list.</span></span>
        
          - <span data-ttu-id="d4e8b-151">如果通訊群組清單包含一或多個通訊群組清單，則巢狀通訊群組清單的成員不會加入到專員清單中。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-151">If the distribution list contains one or more distribution lists, members of the nested distribution lists are not added to the agent list.</span></span>
        
          - <span data-ttu-id="d4e8b-152">如果選取了串列或迴圈複用路由，則伺服器會根據路由方法以及代理列在通訊群組清單中的順序，向適當的代理人提供來電。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-152">If serial or round robin routing is selected, the server offers an incoming call to the appropriate agent according to the routing method and according to the order in which agents are listed in the distribution list.</span></span>
        
          - <span data-ttu-id="d4e8b-153">如果通訊群組清單包含的使用者已啟用 Lync Server 2010，但是未啟用 Enterprise Voice，他們會以 dysfunctional 代理程式的形式新增至代理人群組。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-153">If the distribution list contains users for which Lync Server 2010 is enabled but Enterprise Voice is not enabled, they will be added to the agent group as dysfunctional agents.</span></span> <span data-ttu-id="d4e8b-154">請確定通訊群組清單的所有成員都已啟用企業語音的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-154">Make sure that all members of the distribution list have Enterprise Voice enabled for their user accounts.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="d4e8b-155">如果您使用電子郵件通訊群組清單，回應群組管理員或使用者可能會看到隱藏的成員資格或隱藏的清單。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-155">If you use an email distribution list, hidden memberships or hidden lists might become visible to the Response Group administrator or users.</span></span>

        
        </div>
        
        <span data-ttu-id="d4e8b-156">在下列情況下，隱藏的成員資格或隱藏的清單會顯現出來：</span><span class="sxs-lookup"><span data-stu-id="d4e8b-156">Hidden memberships or hidden lists can become visible as follows:</span></span>
        
          - <span data-ttu-id="d4e8b-157">如果已設定通訊群組清單以便隱藏成員資格，且回應群組管理員將通訊群組清單指派給代理人清單，則使用者可以呼叫群組以找出成員是誰。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-157">If a distribution list was configured so that the membership is hidden and the Response Group administrator assigns the distribution list to the agent list, users can call the group to find out who the members are.</span></span>
        
          - <span data-ttu-id="d4e8b-158">如果已設定通訊群組清單，使其在 Exchange 全域通訊清單中隱藏，回應群組管理員可能會看到通訊群組清單，並將其指派給代理人清單，如果回應群組處理具有適當的使用者權限，即使系統管理員沒有適當的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-158">If a distribution list was configured so that it is hidden in the Exchange Global Address List, the Response Group administrator might be able to see the distribution list and assign it to the agent list if the Response Group process has the appropriate user rights and permissions, even if the administrator does not have the appropriate user rights and permissions.</span></span>

11. <span data-ttu-id="d4e8b-159">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-159">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-agent-group"></a><span data-ttu-id="d4e8b-160">使用 Windows PowerShell 建立或修改代理程式群組</span><span class="sxs-lookup"><span data-stu-id="d4e8b-160">To use Windows PowerShell to create or modify an agent group</span></span>

1.  <span data-ttu-id="d4e8b-161">以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-161">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="d4e8b-162">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-162">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d4e8b-163">使用 **New-CsRgsAgentGroup** 建立新的代理人群組。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-163">Use **New-CsRgsAgentGroup** to create a new agent group.</span></span> <span data-ttu-id="d4e8b-164">使用 **get-csrgsagentgroup** 來修改現有的代理人群組。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-164">Use **Set-CsRgsAgentGroup** to modify an existing agent group.</span></span> <span data-ttu-id="d4e8b-165">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="d4e8b-165">At the command line, run:</span></span>
    
        New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
    
    <span data-ttu-id="d4e8b-166">例如：</span><span class="sxs-lookup"><span data-stu-id="d4e8b-166">For example:</span></span>
    
        New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d4e8b-167">「代理程式警示時間」設定不得超過180秒。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-167">The agent alert time setting cannot exceed 180 seconds.</span></span> <span data-ttu-id="d4e8b-168">如果代理程式警示時間大於180秒，用戶端應用程式會拒絕呼叫，因為 SIP 交易計時器已達到其最長等待時間。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-168">If the agent alert time is greater than 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span>

    
    </div>

4.  <span data-ttu-id="d4e8b-169">確認已建立代理人群組。</span><span class="sxs-lookup"><span data-stu-id="d4e8b-169">Confirm that the agent group is created.</span></span> <span data-ttu-id="d4e8b-170">運行：</span><span class="sxs-lookup"><span data-stu-id="d4e8b-170">Run:</span></span>
    
        Get-CsRgsAgentGroup -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d4e8b-171">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d4e8b-171">See Also</span></span>


[<span data-ttu-id="d4e8b-172">在 Lync Server 2013 中刪除代理群組</span><span class="sxs-lookup"><span data-stu-id="d4e8b-172">Delete an agent group in Lync Server 2013</span></span>](lync-server-2013-delete-an-agent-group.md)  


[<span data-ttu-id="d4e8b-173">在 Lync Server 2013 中管理回應群組代理群組</span><span class="sxs-lookup"><span data-stu-id="d4e8b-173">Managing Response Group agent groups in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-agent-groups.md)  
[<span data-ttu-id="d4e8b-174">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="d4e8b-174">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="d4e8b-175">New-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="d4e8b-175">New-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup)  
[<span data-ttu-id="d4e8b-176">Get-csrgsagentgroup</span><span class="sxs-lookup"><span data-stu-id="d4e8b-176">Set-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsAgentGroup)  
[<span data-ttu-id="d4e8b-177">Get-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="d4e8b-177">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

