---
title: 在商務用 Skype 中建立或修改佇列
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
ms.assetid: b9d6366a-839f-4651-a01d-9254546cadeb
description: 在商務用 Skype Server Enterprise Voice 中建立或修改回應群組佇列。
ms.openlocfilehash: b355cde0d8a99938538488152276a6c8eb4c6d4b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103579"
---
# <a name="create-or-modify-a-queue-in-skype-for-business"></a><span data-ttu-id="f9ec5-103">在商務用 Skype 中建立或修改佇列</span><span class="sxs-lookup"><span data-stu-id="f9ec5-103">Create or modify a queue in Skype for Business</span></span>
 
<span data-ttu-id="f9ec5-104">在商務用 Skype Server Enterprise Voice 中建立或修改回應群組佇列。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-104">Create or modify a Response Group queue, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="f9ec5-105">佇列會使來電者等候，直到代理接聽電話為止。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-105">Queues hold callers until an agent answers the call.</span></span> <span data-ttu-id="f9ec5-106">當回應群組應用程式搜尋可用的代理程式時，它會依照列出的順序來搜尋代理人群組。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-106">When the Response Group application searches for an available agent, it searches agent groups in the order that you list them.</span></span> <span data-ttu-id="f9ec5-107">您可以選取指派給佇列的代理群組，並指定佇列行為，例如限制佇列中可以包含的電話數目，以及限制在代理接聽電話之前，電話等候的時間長度。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-107">You can select the agent groups that are assigned to the queue and specify queue behavior, such as limiting the number of calls that the queue can hold and the period of time that a call waits until an agent answers the call.</span></span>
  
<span data-ttu-id="f9ec5-108">使用下列其中一個程式來建立或修改佇列。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-108">Use one of the following procedures to create or modify a queue.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-queue"></a><span data-ttu-id="f9ec5-109">使用商務用 Skype Server 控制台建立或修改佇列</span><span class="sxs-lookup"><span data-stu-id="f9ec5-109">To use Skype for Business Server Control Panel to create or modify a queue</span></span>

1. <span data-ttu-id="f9ec5-110">以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-110">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f9ec5-111">如果您是受管理工作流程的其中一位委派回應群組管理員，您可以建立或修改回應群組佇列，並將其指派給您管理的工作流程。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-111">If you are one of the delegated Response Group Managers for a managed workflow, you can create or modify response group queues and assign them to the workflows that you manage.</span></span> 
  
2. <span data-ttu-id="f9ec5-112">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="f9ec5-113">在左導覽列中，按一下 **[回應群組]**，然後按一下 **[佇列]**。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-113">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>
    
4. <span data-ttu-id="f9ec5-114">在 [ **佇列** ] 頁面上，執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="f9ec5-114">On the **Queue** page, do one of the following:</span></span>
    
   - <span data-ttu-id="f9ec5-115">若要建立新的佇列，請按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-115">To create a new queue, click **New**.</span></span> <span data-ttu-id="f9ec5-116">在 [ **選取服務**] 中，在 [搜尋] 欄位中輸入您要在其中新增佇列的 **ApplicationServer** 服務的部分或全部名稱。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-116">In **Select a Service**, type part or all of the name of the **ApplicationServer** service where you want to add the queue in the search field.</span></span> <span data-ttu-id="f9ec5-117">在產生的服務清單中，按一下您想要的服務，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-117">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="f9ec5-118">若要修改現有的佇列，請在搜尋欄位中輸入全部或部分的佇列名稱。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-118">To modify an existing queue, type all or part of the queue name in the search field.</span></span> <span data-ttu-id="f9ec5-119">在產生的佇列清單中，按一下您想要的佇列，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-119">In the resulting list of queues, click the queue that you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="f9ec5-120">在 [ **名稱**] 中，輸入佇列的識別名稱。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-120">In **Name**, type an identifying name for the queue.</span></span>
    
6. <span data-ttu-id="f9ec5-121">在 **[描述]** 中，輸入佇列的描述。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-121">In **Description**, type a description for the queue.</span></span>
    
7. <span data-ttu-id="f9ec5-122">在 [ **群組**] 中，指定您想要指派給佇列的群組。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-122">In **Groups**, specify the groups you want to assign to the queue.</span></span> <span data-ttu-id="f9ec5-123">執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="f9ec5-123">Do one of the following:</span></span> 
    
   - <span data-ttu-id="f9ec5-124">若要將群組新增至佇列，請按一下 [ **選取**]。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-124">To add a group to the queue, click **Select**.</span></span> <span data-ttu-id="f9ec5-125">在 [ **選取群組** ] 搜尋欄位中，輸入您要指派給佇列的代理人群組全部或部分名稱，然後按一下您想要的代理人群組，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-125">In the **Select Groups** search field, type all or part of the name of the agent group that you want to assign to the queue, click the agent group that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="f9ec5-126">若要從佇列中移除群組，請在代理程式群組清單中，按一下您要移除的群組，然後按一下 [ **移除**]。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-126">To remove a group from the queue, in the list of agent groups, click the group that you want to remove, and then click **Remove**.</span></span>
    
   - <span data-ttu-id="f9ec5-127">若要變更代理人的搜尋順序，請在代理人群組清單中，按一下群組，然後按一下向上箭號或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-127">To change the order in which agents are searched, in the list of agent groups, click a group, and then click the up arrow or down arrow.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="f9ec5-128">當伺服器搜尋佇列的可用代理程式時，會使用群組順序。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-128">When the server searches for an available agent for the queue, it uses group order.</span></span> <span data-ttu-id="f9ec5-129">也就是會先搜尋清單中的第一個群組，然後是清單中的第二個群組，以此類推。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-129">That is, the first group in the list is searched first, followed by the second group in the list, and so on.</span></span> 
  
8. <span data-ttu-id="f9ec5-130">若要指定來電者等候專員接聽通話之前的最長保留期間，請選取 **[啟用佇列逾時]** 核取方塊，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="f9ec5-130">To specify a maximum period of time for a caller to wait on hold before an agent answers the call, select the **Enable queue time-out** check box, and then do the following:</span></span>
    
    <span data-ttu-id="f9ec5-131">a.</span><span class="sxs-lookup"><span data-stu-id="f9ec5-131">a.</span></span> <span data-ttu-id="f9ec5-132">在 **[逾時期限 (秒)]** 中，指定來電者等候專員接聽通話的最長秒數。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-132">In **Time-out period (seconds)**, specify the maximum number of seconds a caller waits for an agent to answer the call.</span></span>
    
    <span data-ttu-id="f9ec5-133">b.</span><span class="sxs-lookup"><span data-stu-id="f9ec5-133">b.</span></span> <span data-ttu-id="f9ec5-134">在 **[撥號動作]** 中，選取通話逾時時進行的動作 (如下所示)：</span><span class="sxs-lookup"><span data-stu-id="f9ec5-134">In **Call Action**, select the action that occurs when a call times out as follows:</span></span>
    
   - <span data-ttu-id="f9ec5-135">若要在逾時之後中斷通話，請按一下 **[中斷連線]**。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-135">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
   - <span data-ttu-id="f9ec5-136">若要將來電轉接至語音信箱，請按一下 [**轉寄至語音信箱**]，然後在 [ **sip 位址**] 欄位中輸入語音信箱位址，格式為 SIP： *\<username\>* @  *\<domainname\>* (例如，sip:bob@contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-136">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip: *\<username\>*@ *\<domainname\>* (for example, sip:bob@contoso.com).</span></span>
    
   - <span data-ttu-id="f9ec5-137">若要將通話轉寄給另一個電話號碼，請按一下 [**轉寄給電話號碼**]，然後在 [ **sip 位址**] 欄位中，輸入以 [sip： (格式] 的電話號碼（ *\<number\>* @  *\<domainname\>* 例如，sip:+14255550121@contoso.com) ）。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-137">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip: *\<number\>*@ *\<domainname\>* (for example, sip:+14255550121@contoso.com).</span></span>
    
   - <span data-ttu-id="f9ec5-138">若要將呼叫轉寄給另一位使用者，請按一下 [**轉寄給 SIP 位址**]，然後在 [ **sip 位址**] 欄位中，以 [sip：] 的格式輸入使用者的 URI _\<username\>_ @  _\<domainname\>_ 。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-138">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip: _\<username\>_@ _\<domainname\>_.</span></span>
    
   - <span data-ttu-id="f9ec5-139">若要將通話轉接至另一個佇列，請按一下 **[轉接至其他佇列]**，然後瀏覽至想要使用的佇列。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-139">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>
    
9. <span data-ttu-id="f9ec5-140">若要指定佇列可以保留的通話數目上限，請選取 **[啟用佇列溢位]** 核取方塊，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="f9ec5-140">To specify a maximum number of calls that the queue can hold, select the **Enable queue overflow** check box, and then do the following:</span></span>
    
    <span data-ttu-id="f9ec5-141">a.</span><span class="sxs-lookup"><span data-stu-id="f9ec5-141">a.</span></span> <span data-ttu-id="f9ec5-142">在 **[通話數目上限]** 中，選取想要佇列保留的通話數目上限。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-142">In **Maximum number of calls**, select the maximum number of calls that you want the queue to hold.</span></span> 
    
    <span data-ttu-id="f9ec5-143">b.</span><span class="sxs-lookup"><span data-stu-id="f9ec5-143">b.</span></span> <span data-ttu-id="f9ec5-144">在 **[轉接來電]** 中，選取佇列已滿時要轉接的通話：**[最新通話]** 或 **[最早通話]**。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-144">In **Forward the call**, select which call is to be forwarded when the queue is full: **Newest Call** or **Oldest Call**.</span></span>
    
    <span data-ttu-id="f9ec5-145">c.</span><span class="sxs-lookup"><span data-stu-id="f9ec5-145">c.</span></span> <span data-ttu-id="f9ec5-146">在 [ **通話動作**] 中，選取符合溢出閾值時所發生的動作，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f9ec5-146">In **Call action**, select the action that occurs when the overflow threshold is met as follows:</span></span>
    
   - <span data-ttu-id="f9ec5-147">若要在逾時之後中斷通話，請按一下 **[中斷連線]**。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-147">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
   - <span data-ttu-id="f9ec5-148">若要將來電轉接至語音信箱，請按一下 [**轉寄至語音信箱**]，然後在 [ **sip 位址**] 欄位中輸入語音信箱位址，格式為 SIP： *\<username\>* @  *\<domainname\>* (例如，sip:bob@contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-148">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip: *\<username\>*@ *\<domainname\>* (for example, sip:bob@contoso.com).</span></span>
    
   - <span data-ttu-id="f9ec5-149">若要將通話轉寄給另一個電話號碼，請按一下 [**轉寄給電話號碼**]，然後在 [ **sip 位址**] 欄位中，輸入以 [sip： (格式] 的電話號碼（ *\<number\>* @  *\<domainname\>* 例如，sip:+14255550121@contoso.com) ）。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-149">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip: *\<number\>*@ *\<domainname\>* (for example, sip:+14255550121@contoso.com).</span></span>
    
   - <span data-ttu-id="f9ec5-150">若要將呼叫轉寄給另一位使用者，請按一下 [**轉寄給 SIP 位址**]，然後在 [ **sip 位址**] 欄位中，以 [sip：] 的格式輸入使用者的 URI _\<username\>_ @  _\<domainname\>_ 。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-150">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip: _\<username\>_@ _\<domainname\>_.</span></span>
    
   - <span data-ttu-id="f9ec5-151">若要將通話轉接至另一個佇列，請按一下 **[轉接至其他佇列]**，然後瀏覽至想要使用的佇列。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-151">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>
    
10. <span data-ttu-id="f9ec5-152">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-152">Click **Commit**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-queue"></a><span data-ttu-id="f9ec5-153">使用商務用 Skype Server 管理命令介面來建立或修改佇列</span><span class="sxs-lookup"><span data-stu-id="f9ec5-153">To use Skype for Business Server Management Shell to create or modify a queue</span></span>

1. <span data-ttu-id="f9ec5-154">以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-154">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f9ec5-155">如果您是受管理工作流程的其中一位委派回應群組管理員，則可以建立代理人群組和佇列，並將代理群組指派給佇列。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-155">If you are one of the delegated Response Group Managers for a managed workflow, you will be able to create agent groups and queues, and assign agent groups to queues.</span></span> 
  
2. <span data-ttu-id="f9ec5-156">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f9ec5-157">建立當達到佇列的超時臨界值時要播放的提示，並將它儲存在變數中。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-157">Create the prompt to be played when the queue timeout threshold is met, and save it in a variable.</span></span> <span data-ttu-id="f9ec5-158">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="f9ec5-158">At the command line, run:</span></span>
    
   ```powershell
   $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   <span data-ttu-id="f9ec5-159">例如：</span><span class="sxs-lookup"><span data-stu-id="f9ec5-159">For example:</span></span>
    
   ```console
   "All agents are currently busy. Please call back later."
   ```

   > [!NOTE]
   > <span data-ttu-id="f9ec5-160">若要使用音訊檔以進行提示，請使用 **Import-CsRgsAudioFile** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-160">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="f9ec5-161">如需詳細資訊，請參閱 [Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-161">For details, see [Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span> 
  
4. <span data-ttu-id="f9ec5-162">定義達到佇列的超時臨界值時要採取的動作，並將它儲存在變數中。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-162">Define the action to be taken when the queue timeout threshold is met, and save it in a variable.</span></span> <span data-ttu-id="f9ec5-163">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="f9ec5-163">At the command line, run:</span></span>
    
   ```powershell
   $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

   > [!NOTE]
   > <span data-ttu-id="f9ec5-164">如需可能的動作及其語法的詳細資訊，請參閱 [New-CsRgsCallAction](/powershell/module/skype/new-csrgscallaction?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-164">For details about possible actions and their syntax, see [New-CsRgsCallAction](/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span> 
  
    <span data-ttu-id="f9ec5-165">例如：</span><span class="sxs-lookup"><span data-stu-id="f9ec5-165">For example:</span></span>
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate
   ```

5. <span data-ttu-id="f9ec5-166">建立在達到佇列溢出閾值時要播放的提示，並將其儲存在變數中。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-166">Create the prompt to be played when the queue overflow threshold is met, and save it in a variable.</span></span> <span data-ttu-id="f9ec5-167">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="f9ec5-167">At the command line, run:</span></span>
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   <span data-ttu-id="f9ec5-168">例如：</span><span class="sxs-lookup"><span data-stu-id="f9ec5-168">For example:</span></span>
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
   ```

      > [!NOTE]
      > <span data-ttu-id="f9ec5-169">若要使用音訊檔以進行提示，請使用 **Import-CsRgsAudioFile** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-169">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="f9ec5-170">如需詳細資訊，請參閱 [Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-170">For details, see [Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span> 
  
6. <span data-ttu-id="f9ec5-171">定義達到佇列溢出閾值時要採取的動作，並將其儲存在變數中。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-171">Define the action to be taken when the queue overflow threshold is met, and save it in a variable.</span></span> <span data-ttu-id="f9ec5-172">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="f9ec5-172">At the command line, run:</span></span>
    
   ```powershell
   $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

    > [!NOTE]
    > <span data-ttu-id="f9ec5-173">如需可能的動作及其語法的詳細資訊，請參閱 [New-CsRgsCallAction](/powershell/module/skype/new-csrgscallaction?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-173">For details about possible actions and their syntax, see [New-CsRgsCallAction](/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span> 
  
    <span data-ttu-id="f9ec5-174">例如：</span><span class="sxs-lookup"><span data-stu-id="f9ec5-174">For example:</span></span>
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate
   ```

7. <span data-ttu-id="f9ec5-175">取得回應群組服務的服務名稱，並將其指派給變數。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-175">Retrieve the service name for the Response Group service and assign it to a variable.</span></span> <span data-ttu-id="f9ec5-176">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="f9ec5-176">At the command line, run:</span></span>
    
   ```powershell
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;
   ```

8. <span data-ttu-id="f9ec5-177">取得要指派給佇列的代理人群組的身分識別。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-177">Get the identity of the agent group to be assigned to the queue.</span></span> <span data-ttu-id="f9ec5-178">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="f9ec5-178">At the command line, run:</span></span>
    
   ```powershell
   $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
   ```

    > [!NOTE]
    > <span data-ttu-id="f9ec5-179">如需建立代理人群組的詳細資訊，請參閱 [New-CsRgsAgentGroup](/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="f9ec5-179">For details about creating the agent group, see [New-CsRgsAgentGroup](/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)</span></span>
  
9. <span data-ttu-id="f9ec5-180">建立佇列。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-180">Create the queue.</span></span> <span data-ttu-id="f9ec5-181">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="f9ec5-181">At the command line, run:</span></span>
    
   ```powershell
   $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
   ```

   <span data-ttu-id="f9ec5-182">例如：</span><span class="sxs-lookup"><span data-stu-id="f9ec5-182">For example:</span></span>
    
   ```powershell
   $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;
   ```

10. <span data-ttu-id="f9ec5-183">確認已建立佇列。</span><span class="sxs-lookup"><span data-stu-id="f9ec5-183">Confirm that the queue is created.</span></span> <span data-ttu-id="f9ec5-184">執行：</span><span class="sxs-lookup"><span data-stu-id="f9ec5-184">Run:</span></span>
    
    ```powershell
    Get-CsRgsQueue -Name "Help Desk"
    ```

## <a name="see-also"></a><span data-ttu-id="f9ec5-185">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f9ec5-185">See also</span></span>

[<span data-ttu-id="f9ec5-186">New-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="f9ec5-186">New-CsRgsQueue</span></span>](/powershell/module/skype/new-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="f9ec5-187">Set-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="f9ec5-187">Set-CsRgsQueue</span></span>](/powershell/module/skype/set-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="f9ec5-188">New-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="f9ec5-188">New-CsRgsPrompt</span></span>](/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[<span data-ttu-id="f9ec5-189">New-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="f9ec5-189">New-CsRgsCallAction</span></span>](/powershell/module/skype/new-csrgscallaction?view=skype-ps)
  
[<span data-ttu-id="f9ec5-190">Get-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="f9ec5-190">Get-CsRgsQueue</span></span>](/powershell/module/skype/get-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="f9ec5-191">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="f9ec5-191">Import-CsRgsAudioFile</span></span>](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
  
[<span data-ttu-id="f9ec5-192">Remove-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="f9ec5-192">Remove-CsRgsQueue</span></span>](/powershell/module/skype/remove-csrgsqueue?view=skype-ps)