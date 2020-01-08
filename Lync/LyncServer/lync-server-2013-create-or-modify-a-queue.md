---
title: Lync Server 2013：建立或修改佇列
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a queue
ms:assetid: b9d6366a-839f-4651-a01d-9254546cadeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205207(v=OCS.15)
ms:contentKeyID: 48185247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96b6bc1e5f956b5b975e14f07a3c37f2802d1b39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-queue-in-lync-server-2013"></a><span data-ttu-id="ff1d4-102">在 Lync Server 2013 中建立或修改佇列</span><span class="sxs-lookup"><span data-stu-id="ff1d4-102">Create or modify a queue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff1d4-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="ff1d4-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="ff1d4-104">使用下列其中一個程式來建立或修改佇列。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-104">Use one of the following procedures to create or modify a queue.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-queue"></a><span data-ttu-id="ff1d4-105">使用 Lync Server [控制台] 來建立或修改佇列</span><span class="sxs-lookup"><span data-stu-id="ff1d4-105">To use Lync Server Control Panel to create or modify a queue</span></span>

1.  <span data-ttu-id="ff1d4-106">以 RTCUniversalServerAdmins 群組成員的身分登入，或以支援回應群組的預先定義之系統管理角色的成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ff1d4-107">如果您是受管理工作流程的委派回應群組管理員之一，您可以建立或修改回應群組佇列，並將其指派給您管理的工作流程。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-107">If you are one of the delegated Response Group Managers for a managed workflow, you can create or modify response group queues and assign them to the workflows that you manage.</span></span>

    
    </div>

2.  <span data-ttu-id="ff1d4-108">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ff1d4-109">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ff1d4-110">在左側導覽列中，按一下 [**回應群組**]，然後按一下 [**佇列**]。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-110">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>

4.  <span data-ttu-id="ff1d4-111">在 [**佇列**] 頁面上，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="ff1d4-111">On the **Queue** page, do one of the following:</span></span>
    
      - <span data-ttu-id="ff1d4-112">若要建立新的佇列，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-112">To create a new queue, click **New**.</span></span> <span data-ttu-id="ff1d4-113">在 [**選取服務**] 中，在 [搜尋] 欄位中，輸入您要新增佇列之**ApplicationServer**服務的部分或所有名稱。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-113">In **Select a Service**, type part or all of the name of the **ApplicationServer** service where you want to add the queue in the search field.</span></span> <span data-ttu-id="ff1d4-114">在產生的服務清單中，按一下您想要的服務，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-114">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="ff1d4-115">若要修改現有的佇列，請在 [搜尋] 欄位中輸入全部或部分的佇列名稱。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-115">To modify an existing queue, type all or part of the queue name in the search field.</span></span> <span data-ttu-id="ff1d4-116">在產生的佇列清單中，按一下您想要的佇列，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-116">In the resulting list of queues, click the queue that you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="ff1d4-117">在 [**名稱**] 中，輸入佇列的識別名稱。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-117">In **Name**, type an identifying name for the queue.</span></span>

6.  <span data-ttu-id="ff1d4-118">在 [**描述**] 中，輸入佇列的描述。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-118">In **Description**, type a description for the queue.</span></span>

7.  <span data-ttu-id="ff1d4-119">在 [**群組**] 中，指定您要指派給佇列的群組。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-119">In **Groups**, specify the groups you want to assign to the queue.</span></span> <span data-ttu-id="ff1d4-120">請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="ff1d4-120">Do one of the following:</span></span>
    
      - <span data-ttu-id="ff1d4-121">若要在佇列中新增群組，請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-121">To add a group to the queue, click **Select**.</span></span> <span data-ttu-id="ff1d4-122">在 [**選取群組**搜尋] 欄位中，輸入您要指派給佇列之 agent 群組的全部或部分名稱，按一下您想要的 agent 群組，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-122">In the **Select Groups** search field, type all or part of the name of the agent group that you want to assign to the queue, click the agent group that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="ff1d4-123">若要從佇列中移除群組，請在 [代理群組] 清單中，按一下您要移除的群組，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-123">To remove a group from the queue, in the list of agent groups, click the group that you want to remove, and then click **Remove**.</span></span>
    
      - <span data-ttu-id="ff1d4-124">若要變更代理的搜尋順序，請在 [代理程式群組] 清單中，按一下群組，然後按一下向上箭號或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-124">To change the order in which agents are searched, in the list of agent groups, click a group, and then click the up arrow or down arrow.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ff1d4-125">當伺服器搜尋佇列的可用代理程式時，它會使用群組順序。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-125">When the server searches for an available agent for the queue, it uses group order.</span></span> <span data-ttu-id="ff1d4-126">也就是說，會先搜尋清單中的第一個群組，然後搜尋清單中的第二個群組，依此類推。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-126">That is, the first group in the list is searched first, followed by the second group in the list, and so on.</span></span>

        
        </div>

8.  <span data-ttu-id="ff1d4-127">若要指定呼叫者在工程師接聽通話之前等待的時間上限，請選取 [**啟用佇列超時設定**] 核取方塊，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="ff1d4-127">To specify a maximum period of time for a caller to wait on hold before an agent answers the call, select the **Enable queue time-out** check box, and then do the following:</span></span>
    
    1.  <span data-ttu-id="ff1d4-128">在 **[超時時間（秒）**] 中，指定呼叫者等待代理接聽通話的最大秒數。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-128">In **Time-out period (seconds)**, specify the maximum number of seconds a caller waits for an agent to answer the call.</span></span>
    
    2.  <span data-ttu-id="ff1d4-129">在 [**通話**中] 中，選取撥打電話時所發生的動作，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ff1d4-129">In **Call Action**, select the action that occurs when a call times out as follows:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="ff1d4-130">若要在超時之後中斷通話，請按一下 **[中斷**連線]。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-130">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
      - <span data-ttu-id="ff1d4-131">若要將來電轉寄到語音信箱，請按一下 [**轉寄給語音信箱**]，然後在 [ **sip 位址**] 欄位中，輸入\<[sip：使用者名\>@\<功能變數名稱\> ] 中的語音信箱位址（例如，sip:bob@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-131">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip:\<username\>@\<domainname\> (for example, sip:bob@contoso.com).</span></span>
    
      - <span data-ttu-id="ff1d4-132">若要將來電轉接到另一個電話號碼，請按一下 [**轉寄電話號碼**]，然後在 [ **sip 位址**] 欄位中，輸入 [sip：\<號碼\>@\<功能變數名稱\> ] （例如，sip:+14255550121@contoso.com）中的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-132">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip:\<number\>@\<domainname\> (for example, sip:+14255550121@contoso.com).</span></span>
    
      - <span data-ttu-id="ff1d4-133">若要將呼叫轉寄給其他使用者，請按一下 [**轉寄給 SIP 位址**]，然後在 [ **sip 位址**] 欄位中，輸入\<[sip： username\>@\<功能變數名稱\>] 的使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-133">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip:\<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="ff1d4-134">若要將來電轉接到另一個佇列，請按一下 [**轉寄至另一份佇列**]，然後流覽至您要使用的佇列。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-134">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>

9.  <span data-ttu-id="ff1d4-135">若要指定佇列可以保留的呼叫數目上限，請選取 [**啟用佇列溢出**] 核取方塊，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="ff1d4-135">To specify a maximum number of calls that the queue can hold, select the **Enable queue overflow** check box, and then do the following:</span></span>
    
    1.  <span data-ttu-id="ff1d4-136">在 [**最大通話數**] 中，選取您希望佇列保留的最大通話數。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-136">In **Maximum number of calls**, select the maximum number of calls that you want the queue to hold.</span></span>
    
    2.  <span data-ttu-id="ff1d4-137">在**轉寄通話**中，選取當佇列已滿時要轉寄的通話： [**最新通話**] 或 [**最舊通話**]。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-137">In **Forward the call**, select which call is to be forwarded when the queue is full: **Newest Call** or **Oldest Call**.</span></span>
    
    3.  <span data-ttu-id="ff1d4-138">在 [**呼叫] 動作**中，選取符合溢出閾值時所發生的動作，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ff1d4-138">In **Call action**, select the action that occurs when the overflow threshold is met as follows:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="ff1d4-139">若要在超時之後中斷通話，請按一下 **[中斷**連線]。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-139">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
      - <span data-ttu-id="ff1d4-140">若要將來電轉寄到語音信箱，請按一下 [**轉寄給語音信箱**]，然後在 [ **sip 位址**] 欄位中，輸入\<[sip：使用者名\>@\<功能變數名稱\> ] 中的語音信箱位址（例如，sip:bob@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-140">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip:\<username\>@\<domainname\> (for example, sip:bob@contoso.com).</span></span>
    
      - <span data-ttu-id="ff1d4-141">若要將來電轉接到另一個電話號碼，請按一下 [**轉寄電話號碼**]，然後在 [ **sip 位址**] 欄位中，輸入 [sip：\<號碼\>@\<功能變數名稱\> ] （例如，sip:+14255550121@contoso.com）中的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-141">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip:\<number\>@\<domainname\> (for example, sip:+14255550121@contoso.com).</span></span>
    
      - <span data-ttu-id="ff1d4-142">若要將呼叫轉寄給其他使用者，請按一下 [**轉寄給 SIP 位址**]，然後在 [ **sip 位址**] 欄位中，輸入\<[sip： username\>@\<功能變數名稱\>] 的使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-142">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip:\<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="ff1d4-143">若要將來電轉接到另一個佇列，請按一下 [**轉寄至另一份佇列**]，然後流覽至您要使用的佇列。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-143">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>

10. <span data-ttu-id="ff1d4-144">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-144">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-queue"></a><span data-ttu-id="ff1d4-145">使用 Windows PowerShell 建立或修改佇列</span><span class="sxs-lookup"><span data-stu-id="ff1d4-145">To use Windows PowerShell to create or modify a queue</span></span>

1.  <span data-ttu-id="ff1d4-146">以 RTCUniversalServerAdmins 群組成員的身分登入，或以支援回應群組的預先定義之系統管理角色的成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-146">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ff1d4-147">如果您是受管理工作流程的委派回應群組管理員，您就可以建立代理群組和佇列，並將代理群組指派給佇列。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-147">If you are one of the delegated Response Group Managers for a managed workflow, you will be able to create agent groups and queues, and assign agent groups to queues.</span></span>

    
    </div>

2.  <span data-ttu-id="ff1d4-148">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-148">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ff1d4-149">在達到佇列的超時閾值時，建立要播放的提示，然後將它儲存在變數中。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-149">Create the prompt to be played when the queue timeout threshold is met, and save it in a variable.</span></span> <span data-ttu-id="ff1d4-150">在命令列上執行：</span><span class="sxs-lookup"><span data-stu-id="ff1d4-150">At the command line, run:</span></span>
    
        $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="ff1d4-151">例如：</span><span class="sxs-lookup"><span data-stu-id="ff1d4-151">For example:</span></span>
    
        "All agents are currently busy. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ff1d4-152">若要在提示時使用音訊檔案，請使用<STRONG>CsRgsAudioFile</STRONG> Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-152">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="ff1d4-153">如需詳細資訊，請參閱匯<A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">入-CsRgsAudioFile</A>。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-153">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="ff1d4-154">定義達到佇列的超時閾值時所採取的動作，並將它儲存在變數中。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-154">Define the action to be taken when the queue timeout threshold is met, and save it in a variable.</span></span> <span data-ttu-id="ff1d4-155">在命令列上執行：</span><span class="sxs-lookup"><span data-stu-id="ff1d4-155">At the command line, run:</span></span>
    
        $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ff1d4-156">如需可能動作及其語法的詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">新 CsRgsCallAction</A>。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-156">For details about possible actions and their syntax, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="ff1d4-157">例如：</span><span class="sxs-lookup"><span data-stu-id="ff1d4-157">For example:</span></span>
    
        $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate

5.  <span data-ttu-id="ff1d4-158">建立在符合佇列溢出閾值時要播放的提示，並將它儲存在變數中。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-158">Create the prompt to be played when the queue overflow threshold is met, and save it in a variable.</span></span> <span data-ttu-id="ff1d4-159">在命令列上執行：</span><span class="sxs-lookup"><span data-stu-id="ff1d4-159">At the command line, run:</span></span>
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="ff1d4-160">例如：</span><span class="sxs-lookup"><span data-stu-id="ff1d4-160">For example:</span></span>
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ff1d4-161">若要在提示時使用音訊檔案，請使用<STRONG>CsRgsAudioFile</STRONG> Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-161">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="ff1d4-162">如需詳細資訊，請參閱匯<A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">入-CsRgsAudioFile</A>。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-162">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

6.  <span data-ttu-id="ff1d4-163">定義達到佇列溢出閾值時所採取的動作，並將它儲存在變數中。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-163">Define the action to be taken when the queue overflow threshold is met, and save it in a variable.</span></span> <span data-ttu-id="ff1d4-164">在命令列上執行：</span><span class="sxs-lookup"><span data-stu-id="ff1d4-164">At the command line, run:</span></span>
    
        $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ff1d4-165">如需可能動作及其語法的詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">新 CsRgsCallAction</A>。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-165">For details about possible actions and their syntax, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="ff1d4-166">例如：</span><span class="sxs-lookup"><span data-stu-id="ff1d4-166">For example:</span></span>
    
        $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate

7.  <span data-ttu-id="ff1d4-167">檢索回應群組服務的服務名稱，並將它指派給變數。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-167">Retrieve the service name for the Response Group service and assign it to a variable.</span></span> <span data-ttu-id="ff1d4-168">在命令列上執行：</span><span class="sxs-lookup"><span data-stu-id="ff1d4-168">At the command line, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;

8.  <span data-ttu-id="ff1d4-169">取得指派給佇列的代理群組身分識別。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-169">Get the identity of the agent group to be assigned to the queue.</span></span> <span data-ttu-id="ff1d4-170">在命令列上執行：</span><span class="sxs-lookup"><span data-stu-id="ff1d4-170">At the command line, run:</span></span>
    
        $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ff1d4-171">如需建立代理群組的詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">新 CsRgsAgentGroup</A></span><span class="sxs-lookup"><span data-stu-id="ff1d4-171">For details about creating the agent group, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">New-CsRgsAgentGroup</A></span></span>

    
    </div>

9.  <span data-ttu-id="ff1d4-172">建立佇列。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-172">Create the queue.</span></span> <span data-ttu-id="ff1d4-173">在命令列上執行：</span><span class="sxs-lookup"><span data-stu-id="ff1d4-173">At the command line, run:</span></span>
    
        $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
    
    <span data-ttu-id="ff1d4-174">例如：</span><span class="sxs-lookup"><span data-stu-id="ff1d4-174">For example:</span></span>
    
        $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;

10. <span data-ttu-id="ff1d4-175">確認已建立佇列。</span><span class="sxs-lookup"><span data-stu-id="ff1d4-175">Confirm that the queue is created.</span></span> <span data-ttu-id="ff1d4-176">用盡</span><span class="sxs-lookup"><span data-stu-id="ff1d4-176">Run:</span></span>
    
        Get-CsRgsQueue -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ff1d4-177">請參閱</span><span class="sxs-lookup"><span data-stu-id="ff1d4-177">See Also</span></span>


[<span data-ttu-id="ff1d4-178">新-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="ff1d4-178">New-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue)  
[<span data-ttu-id="ff1d4-179">Set-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="ff1d4-179">Set-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsQueue)  
[<span data-ttu-id="ff1d4-180">新-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="ff1d4-180">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[<span data-ttu-id="ff1d4-181">新-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="ff1d4-181">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
[<span data-ttu-id="ff1d4-182">CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="ff1d4-182">Get-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsQueue)  
[<span data-ttu-id="ff1d4-183">匯入-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="ff1d4-183">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
[<span data-ttu-id="ff1d4-184">移除-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="ff1d4-184">Remove-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsQueue)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

