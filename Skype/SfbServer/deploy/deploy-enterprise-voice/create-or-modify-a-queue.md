---
title: 在商務用 Skype 中建立或修改佇列
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
ms.assetid: b9d6366a-839f-4651-a01d-9254546cadeb
description: 在商務用 Skype Server Enterprise Voice 中建立或修改回應群組佇列。
ms.openlocfilehash: b58ec9065eea1cc2dd8686b07ea798ac71c460fa
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233675"
---
# <a name="create-or-modify-a-queue-in-skype-for-business"></a><span data-ttu-id="ae603-103">在商務用 Skype 中建立或修改佇列</span><span class="sxs-lookup"><span data-stu-id="ae603-103">Create or modify a queue in Skype for Business</span></span>
 
<span data-ttu-id="ae603-104">在商務用 Skype Server Enterprise Voice 中建立或修改回應群組佇列。</span><span class="sxs-lookup"><span data-stu-id="ae603-104">Create or modify a Response Group queue, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="ae603-105">[佇列] 會按住呼叫者, 直到工程師接聽通話。</span><span class="sxs-lookup"><span data-stu-id="ae603-105">Queues hold callers until an agent answers the call.</span></span> <span data-ttu-id="ae603-106">當回應群組應用程式搜尋可用的代理時, 會按照您列出的順序來搜尋代理群組。</span><span class="sxs-lookup"><span data-stu-id="ae603-106">When the Response Group application searches for an available agent, it searches agent groups in the order that you list them.</span></span> <span data-ttu-id="ae603-107">您可以選取指派給佇列的代理群組, 並指定佇列行為, 例如限制該列隊可以保留的呼叫次數, 以及呼叫在工程師接聽通話之前等待的時間。</span><span class="sxs-lookup"><span data-stu-id="ae603-107">You can select the agent groups that are assigned to the queue and specify queue behavior, such as limiting the number of calls that the queue can hold and the period of time that a call waits until an agent answers the call.</span></span>
  
<span data-ttu-id="ae603-108">使用下列其中一個程式來建立或修改佇列。</span><span class="sxs-lookup"><span data-stu-id="ae603-108">Use one of the following procedures to create or modify a queue.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-queue"></a><span data-ttu-id="ae603-109">使用商務用 Skype Server 的 [控制台] 來建立或修改佇列</span><span class="sxs-lookup"><span data-stu-id="ae603-109">To use Skype for Business Server Control Panel to create or modify a queue</span></span>

1. <span data-ttu-id="ae603-110">以 RTCUniversalServerAdmins 群組成員的身分登入, 或以支援回應群組的預先定義之系統管理角色的成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="ae603-110">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ae603-111">如果您是受管理工作流程的委派回應群組管理員之一, 您可以建立或修改回應群組佇列, 並將其指派給您管理的工作流程。</span><span class="sxs-lookup"><span data-stu-id="ae603-111">If you are one of the delegated Response Group Managers for a managed workflow, you can create or modify response group queues and assign them to the workflows that you manage.</span></span> 
  
2. <span data-ttu-id="ae603-112">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="ae603-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="ae603-113">在左側導覽列中, 按一下 [**回應群組**], 然後按一下 [**佇列**]。</span><span class="sxs-lookup"><span data-stu-id="ae603-113">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>
    
4. <span data-ttu-id="ae603-114">在 [**佇列**] 頁面上, 執行下列其中一項操作:</span><span class="sxs-lookup"><span data-stu-id="ae603-114">On the **Queue** page, do one of the following:</span></span>
    
   - <span data-ttu-id="ae603-115">若要建立新的佇列, 請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="ae603-115">To create a new queue, click **New**.</span></span> <span data-ttu-id="ae603-116">在 [**選取服務**] 中, 在 [搜尋] 欄位中, 輸入您要新增佇列之**ApplicationServer**服務的部分或所有名稱。</span><span class="sxs-lookup"><span data-stu-id="ae603-116">In **Select a Service**, type part or all of the name of the **ApplicationServer** service where you want to add the queue in the search field.</span></span> <span data-ttu-id="ae603-117">在產生的服務清單中, 按一下您想要的服務, 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ae603-117">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="ae603-118">若要修改現有的佇列, 請在 [搜尋] 欄位中輸入全部或部分的佇列名稱。</span><span class="sxs-lookup"><span data-stu-id="ae603-118">To modify an existing queue, type all or part of the queue name in the search field.</span></span> <span data-ttu-id="ae603-119">在產生的佇列清單中, 按一下您想要的佇列, 按一下 [**編輯**], 然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="ae603-119">In the resulting list of queues, click the queue that you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="ae603-120">在 [**名稱**] 中, 輸入佇列的識別名稱。</span><span class="sxs-lookup"><span data-stu-id="ae603-120">In **Name**, type an identifying name for the queue.</span></span>
    
6. <span data-ttu-id="ae603-121">在 [**描述**] 中, 輸入佇列的描述。</span><span class="sxs-lookup"><span data-stu-id="ae603-121">In **Description**, type a description for the queue.</span></span>
    
7. <span data-ttu-id="ae603-122">在 [**群組**] 中, 指定您要指派給佇列的群組。</span><span class="sxs-lookup"><span data-stu-id="ae603-122">In **Groups**, specify the groups you want to assign to the queue.</span></span> <span data-ttu-id="ae603-123">請執行下列其中一項操作:</span><span class="sxs-lookup"><span data-stu-id="ae603-123">Do one of the following:</span></span> 
    
   - <span data-ttu-id="ae603-124">若要在佇列中新增群組, 請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="ae603-124">To add a group to the queue, click **Select**.</span></span> <span data-ttu-id="ae603-125">在 [**選取群組**搜尋] 欄位中, 輸入您要指派給佇列之 agent 群組的全部或部分名稱, 按一下您想要的 agent 群組, 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ae603-125">In the **Select Groups** search field, type all or part of the name of the agent group that you want to assign to the queue, click the agent group that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="ae603-126">若要從佇列中移除群組, 請在 [代理群組] 清單中, 按一下您要移除的群組, 然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="ae603-126">To remove a group from the queue, in the list of agent groups, click the group that you want to remove, and then click **Remove**.</span></span>
    
   - <span data-ttu-id="ae603-127">若要變更代理的搜尋順序, 請在 [代理程式群組] 清單中, 按一下群組, 然後按一下向上箭號或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="ae603-127">To change the order in which agents are searched, in the list of agent groups, click a group, and then click the up arrow or down arrow.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="ae603-128">當伺服器搜尋佇列的可用代理程式時, 它會使用群組順序。</span><span class="sxs-lookup"><span data-stu-id="ae603-128">When the server searches for an available agent for the queue, it uses group order.</span></span> <span data-ttu-id="ae603-129">也就是說, 會先搜尋清單中的第一個群組, 然後搜尋清單中的第二個群組, 依此類推。</span><span class="sxs-lookup"><span data-stu-id="ae603-129">That is, the first group in the list is searched first, followed by the second group in the list, and so on.</span></span> 
  
8. <span data-ttu-id="ae603-130">若要指定呼叫者在工程師接聽通話之前等待的時間上限, 請選取 [**啟用佇列超時設定**] 核取方塊, 然後執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="ae603-130">To specify a maximum period of time for a caller to wait on hold before an agent answers the call, select the **Enable queue time-out** check box, and then do the following:</span></span>
    
    <span data-ttu-id="ae603-131">是.</span><span class="sxs-lookup"><span data-stu-id="ae603-131">a.</span></span> <span data-ttu-id="ae603-132">在 **[超時時間 (秒)**] 中, 指定呼叫者等待代理接聽通話的最大秒數。</span><span class="sxs-lookup"><span data-stu-id="ae603-132">In **Time-out period (seconds)**, specify the maximum number of seconds a caller waits for an agent to answer the call.</span></span>
    
    <span data-ttu-id="ae603-133">乙.</span><span class="sxs-lookup"><span data-stu-id="ae603-133">b.</span></span> <span data-ttu-id="ae603-134">在 [**通話**中] 中, 選取撥打電話時所發生的動作, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="ae603-134">In **Call Action**, select the action that occurs when a call times out as follows:</span></span>
    
   - <span data-ttu-id="ae603-135">若要在超時之後中斷通話, 請按一下 **[中斷**連線]。</span><span class="sxs-lookup"><span data-stu-id="ae603-135">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
   - <span data-ttu-id="ae603-136">若要將來電轉寄到語音信箱, 請按一下 [**轉寄給語音信箱**], 然後在 [ **sip 位址**] 欄位中, 輸入 [sip: \* \< \>username\*@ \*\<功能變數名稱\> \* ] 的語音信箱位址 (適用于範例、sip:bob@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="ae603-136">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip: *\<username\>*@ *\<domainname\>* (for example, sip:bob@contoso.com).</span></span>
    
   - <span data-ttu-id="ae603-137">若要將來電轉接到另一個電話號碼, 請按一下 [**轉寄電話號碼**], 然後在 [ **sip 位址**] 欄位中, 輸入 [sip: \* \<號碼\>\*@ *\<功能變數名稱\>* (例如, sip:+14255550121@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="ae603-137">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip: *\<number\>*@ *\<domainname\>* (for example, sip:+14255550121@contoso.com).</span></span>
    
   - <span data-ttu-id="ae603-138">若要將呼叫轉寄給其他使用者, 請按一下 [**轉寄給 SIP 位址**], 然後在 [ **sip 位址**] 欄位中, 輸入 [sip: _ \< \>username_@ _\<功能變數名稱\>_] 的使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="ae603-138">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip: _\<username\>_@ _\<domainname\>_.</span></span>
    
   - <span data-ttu-id="ae603-139">若要將來電轉接到另一個佇列, 請按一下 [**轉寄至另一份佇列**], 然後流覽至您要使用的佇列。</span><span class="sxs-lookup"><span data-stu-id="ae603-139">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>
    
9. <span data-ttu-id="ae603-140">若要指定佇列可以保留的呼叫數目上限, 請選取 [**啟用佇列溢出**] 核取方塊, 然後執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="ae603-140">To specify a maximum number of calls that the queue can hold, select the **Enable queue overflow** check box, and then do the following:</span></span>
    
    <span data-ttu-id="ae603-141">是.</span><span class="sxs-lookup"><span data-stu-id="ae603-141">a.</span></span> <span data-ttu-id="ae603-142">在 [**最大通話數**] 中, 選取您希望佇列保留的最大通話數。</span><span class="sxs-lookup"><span data-stu-id="ae603-142">In **Maximum number of calls**, select the maximum number of calls that you want the queue to hold.</span></span> 
    
    <span data-ttu-id="ae603-143">乙.</span><span class="sxs-lookup"><span data-stu-id="ae603-143">b.</span></span> <span data-ttu-id="ae603-144">在**轉寄通話**中, 選取當佇列已滿時要轉寄的通話: [**最新通話**] 或 [**最舊通話**]。</span><span class="sxs-lookup"><span data-stu-id="ae603-144">In **Forward the call**, select which call is to be forwarded when the queue is full: **Newest Call** or **Oldest Call**.</span></span>
    
    <span data-ttu-id="ae603-145">c-clip.</span><span class="sxs-lookup"><span data-stu-id="ae603-145">c.</span></span> <span data-ttu-id="ae603-146">在 [**呼叫] 動作**中, 選取符合溢出閾值時所發生的動作, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="ae603-146">In **Call action**, select the action that occurs when the overflow threshold is met as follows:</span></span>
    
   - <span data-ttu-id="ae603-147">若要在超時之後中斷通話, 請按一下 **[中斷**連線]。</span><span class="sxs-lookup"><span data-stu-id="ae603-147">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
   - <span data-ttu-id="ae603-148">若要將來電轉寄到語音信箱, 請按一下 [**轉寄給語音信箱**], 然後在 [ **sip 位址**] 欄位中, 輸入 [sip: \* \< \>username\*@ \*\<功能變數名稱\> \* ] 的語音信箱位址 (適用于範例、sip:bob@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="ae603-148">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip: *\<username\>*@ *\<domainname\>* (for example, sip:bob@contoso.com).</span></span>
    
   - <span data-ttu-id="ae603-149">若要將來電轉接到另一個電話號碼, 請按一下 [**轉寄電話號碼**], 然後在 [ **sip 位址**] 欄位中, 輸入 [sip: \* \<號碼\>\*@ *\<功能變數名稱\>* (例如, sip:+14255550121@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="ae603-149">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip: *\<number\>*@ *\<domainname\>* (for example, sip:+14255550121@contoso.com).</span></span>
    
   - <span data-ttu-id="ae603-150">若要將呼叫轉寄給其他使用者, 請按一下 [**轉寄給 SIP 位址**], 然後在 [ **sip 位址**] 欄位中, 輸入 [sip: _ \< \>username_@ _\<功能變數名稱\>_] 的使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="ae603-150">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip: _\<username\>_@ _\<domainname\>_.</span></span>
    
   - <span data-ttu-id="ae603-151">若要將來電轉接到另一個佇列, 請按一下 [**轉寄至另一份佇列**], 然後流覽至您要使用的佇列。</span><span class="sxs-lookup"><span data-stu-id="ae603-151">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>
    
10. <span data-ttu-id="ae603-152">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ae603-152">Click **Commit**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-queue"></a><span data-ttu-id="ae603-153">若要使用商務用 Skype Server Management Shell 來建立或修改佇列</span><span class="sxs-lookup"><span data-stu-id="ae603-153">To use Skype for Business Server Management Shell to create or modify a queue</span></span>

1. <span data-ttu-id="ae603-154">以 RTCUniversalServerAdmins 群組成員的身分登入, 或以支援回應群組的預先定義之系統管理角色的成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="ae603-154">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ae603-155">如果您是受管理工作流程的委派回應群組管理員, 您就可以建立代理群組和佇列, 並將代理群組指派給佇列。</span><span class="sxs-lookup"><span data-stu-id="ae603-155">If you are one of the delegated Response Group Managers for a managed workflow, you will be able to create agent groups and queues, and assign agent groups to queues.</span></span> 
  
2. <span data-ttu-id="ae603-156">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="ae603-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="ae603-157">在達到佇列的超時閾值時, 建立要播放的提示, 然後將它儲存在變數中。</span><span class="sxs-lookup"><span data-stu-id="ae603-157">Create the prompt to be played when the queue timeout threshold is met, and save it in a variable.</span></span> <span data-ttu-id="ae603-158">在命令列上執行:</span><span class="sxs-lookup"><span data-stu-id="ae603-158">At the command line, run:</span></span>
    
   ```
   $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   <span data-ttu-id="ae603-159">例如：</span><span class="sxs-lookup"><span data-stu-id="ae603-159">For example:</span></span>
    
   ```
   "All agents are currently busy. Please call back later."
   ```

   > [!NOTE]
   > <span data-ttu-id="ae603-160">若要在提示時使用音訊檔案, 請使用**CsRgsAudioFile** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ae603-160">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="ae603-161">如需詳細資訊, 請參閱匯[入-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="ae603-161">For details, see [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span> 
  
4. <span data-ttu-id="ae603-162">定義達到佇列的超時閾值時所採取的動作, 並將它儲存在變數中。</span><span class="sxs-lookup"><span data-stu-id="ae603-162">Define the action to be taken when the queue timeout threshold is met, and save it in a variable.</span></span> <span data-ttu-id="ae603-163">在命令列上執行:</span><span class="sxs-lookup"><span data-stu-id="ae603-163">At the command line, run:</span></span>
    
   ```
   $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

   > [!NOTE]
   > <span data-ttu-id="ae603-164">如需可能動作及其語法的詳細資訊, 請參閱[新 CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="ae603-164">For details about possible actions and their syntax, see [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span> 
  
    <span data-ttu-id="ae603-165">例如：</span><span class="sxs-lookup"><span data-stu-id="ae603-165">For example:</span></span>
    
   ```
   $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate
   ```

5. <span data-ttu-id="ae603-166">建立在符合佇列溢出閾值時要播放的提示, 並將它儲存在變數中。</span><span class="sxs-lookup"><span data-stu-id="ae603-166">Create the prompt to be played when the queue overflow threshold is met, and save it in a variable.</span></span> <span data-ttu-id="ae603-167">在命令列上執行:</span><span class="sxs-lookup"><span data-stu-id="ae603-167">At the command line, run:</span></span>
    
   ```
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   <span data-ttu-id="ae603-168">例如：</span><span class="sxs-lookup"><span data-stu-id="ae603-168">For example:</span></span>
    
   ```
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
   ```

      > [!NOTE]
      > <span data-ttu-id="ae603-169">若要在提示時使用音訊檔案, 請使用**CsRgsAudioFile** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ae603-169">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="ae603-170">如需詳細資訊, 請參閱匯[入-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="ae603-170">For details, see [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span> 
  
6. <span data-ttu-id="ae603-171">定義達到佇列溢出閾值時所採取的動作, 並將它儲存在變數中。</span><span class="sxs-lookup"><span data-stu-id="ae603-171">Define the action to be taken when the queue overflow threshold is met, and save it in a variable.</span></span> <span data-ttu-id="ae603-172">在命令列上執行:</span><span class="sxs-lookup"><span data-stu-id="ae603-172">At the command line, run:</span></span>
    
   ```
   $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

    > [!NOTE]
    > <span data-ttu-id="ae603-173">如需可能動作及其語法的詳細資訊, 請參閱[新 CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="ae603-173">For details about possible actions and their syntax, see [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span> 
  
    <span data-ttu-id="ae603-174">例如：</span><span class="sxs-lookup"><span data-stu-id="ae603-174">For example:</span></span>
    
   ```
   $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate
   ```

7. <span data-ttu-id="ae603-175">檢索回應群組服務的服務名稱, 並將它指派給變數。</span><span class="sxs-lookup"><span data-stu-id="ae603-175">Retrieve the service name for the Response Group service and assign it to a variable.</span></span> <span data-ttu-id="ae603-176">在命令列上執行:</span><span class="sxs-lookup"><span data-stu-id="ae603-176">At the command line, run:</span></span>
    
   ```
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;
   ```

8. <span data-ttu-id="ae603-177">取得指派給佇列的代理群組身分識別。</span><span class="sxs-lookup"><span data-stu-id="ae603-177">Get the identity of the agent group to be assigned to the queue.</span></span> <span data-ttu-id="ae603-178">在命令列上執行:</span><span class="sxs-lookup"><span data-stu-id="ae603-178">At the command line, run:</span></span>
    
   ```
   $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
   ```

    > [!NOTE]
    > <span data-ttu-id="ae603-179">如需建立代理群組的詳細資訊, 請參閱[新 CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="ae603-179">For details about creating the agent group, see [New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)</span></span>
  
9. <span data-ttu-id="ae603-180">建立佇列。</span><span class="sxs-lookup"><span data-stu-id="ae603-180">Create the queue.</span></span> <span data-ttu-id="ae603-181">在命令列上執行:</span><span class="sxs-lookup"><span data-stu-id="ae603-181">At the command line, run:</span></span>
    
   ```
   $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
   ```

   <span data-ttu-id="ae603-182">例如：</span><span class="sxs-lookup"><span data-stu-id="ae603-182">For example:</span></span>
    
   ```
   $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;
   ```

10. <span data-ttu-id="ae603-183">確認已建立佇列。</span><span class="sxs-lookup"><span data-stu-id="ae603-183">Confirm that the queue is created.</span></span> <span data-ttu-id="ae603-184">用盡</span><span class="sxs-lookup"><span data-stu-id="ae603-184">Run:</span></span>
    
    ```
    Get-CsRgsQueue -Name "Help Desk"
    ```

## <a name="see-also"></a><span data-ttu-id="ae603-185">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ae603-185">See also</span></span>

[<span data-ttu-id="ae603-186">新-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="ae603-186">New-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="ae603-187">Set-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="ae603-187">Set-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="ae603-188">新-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="ae603-188">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[<span data-ttu-id="ae603-189">新-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="ae603-189">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)
  
[<span data-ttu-id="ae603-190">CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="ae603-190">Get-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="ae603-191">匯入-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="ae603-191">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
  
[<span data-ttu-id="ae603-192">移除-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="ae603-192">Remove-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csrgsqueue?view=skype-ps)
