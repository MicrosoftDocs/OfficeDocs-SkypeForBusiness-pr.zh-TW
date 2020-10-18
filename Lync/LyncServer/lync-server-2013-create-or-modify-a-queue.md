---
title: Lync Server 2013：建立或修改佇列
description: Lync Server 2013：建立或修改佇列。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a queue
ms:assetid: b9d6366a-839f-4651-a01d-9254546cadeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205207(v=OCS.15)
ms:contentKeyID: 48185247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbd8d6d00df8d6a09ef5861d876bd1363db09e3d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574529"
---
# <a name="create-or-modify-a-queue-in-lync-server-2013"></a><span data-ttu-id="d93f1-103">在 Lync Server 2013 中建立或修改佇列</span><span class="sxs-lookup"><span data-stu-id="d93f1-103">Create or modify a queue in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d93f1-104">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d93f1-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d93f1-105">使用下列其中一個程式來建立或修改佇列。</span><span class="sxs-lookup"><span data-stu-id="d93f1-105">Use one of the following procedures to create or modify a queue.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-queue"></a><span data-ttu-id="d93f1-106">使用 Lync Server 控制台建立或修改佇列</span><span class="sxs-lookup"><span data-stu-id="d93f1-106">To use Lync Server Control Panel to create or modify a queue</span></span>

1.  <span data-ttu-id="d93f1-107">以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="d93f1-107">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d93f1-108">如果您是受管理工作流程的其中一位委派回應群組管理員，您可以建立或修改回應群組佇列，並將其指派給您管理的工作流程。</span><span class="sxs-lookup"><span data-stu-id="d93f1-108">If you are one of the delegated Response Group Managers for a managed workflow, you can create or modify response group queues and assign them to the workflows that you manage.</span></span>

    
    </div>

2.  <span data-ttu-id="d93f1-109">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="d93f1-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d93f1-110">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="d93f1-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d93f1-111">在左導覽列中，按一下 **[回應群組]**，然後按一下 **[佇列]**。</span><span class="sxs-lookup"><span data-stu-id="d93f1-111">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>

4.  <span data-ttu-id="d93f1-112">在 [ **佇列** ] 頁面上，執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="d93f1-112">On the **Queue** page, do one of the following:</span></span>
    
      - <span data-ttu-id="d93f1-113">若要建立新的佇列，請按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="d93f1-113">To create a new queue, click **New**.</span></span> <span data-ttu-id="d93f1-114">在 [ **選取服務**] 中，在 [搜尋] 欄位中輸入您要在其中新增佇列的 **ApplicationServer** 服務的部分或全部名稱。</span><span class="sxs-lookup"><span data-stu-id="d93f1-114">In **Select a Service**, type part or all of the name of the **ApplicationServer** service where you want to add the queue in the search field.</span></span> <span data-ttu-id="d93f1-115">在產生的服務清單中，按一下您想要的服務，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d93f1-115">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="d93f1-116">若要修改現有的佇列，請在搜尋欄位中輸入全部或部分的佇列名稱。</span><span class="sxs-lookup"><span data-stu-id="d93f1-116">To modify an existing queue, type all or part of the queue name in the search field.</span></span> <span data-ttu-id="d93f1-117">在產生的佇列清單中，按一下您想要的佇列，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="d93f1-117">In the resulting list of queues, click the queue that you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="d93f1-118">在 [ **名稱**] 中，輸入佇列的識別名稱。</span><span class="sxs-lookup"><span data-stu-id="d93f1-118">In **Name**, type an identifying name for the queue.</span></span>

6.  <span data-ttu-id="d93f1-119">在 **[描述]** 中，輸入佇列的描述。</span><span class="sxs-lookup"><span data-stu-id="d93f1-119">In **Description**, type a description for the queue.</span></span>

7.  <span data-ttu-id="d93f1-120">在 [ **群組**] 中，指定您想要指派給佇列的群組。</span><span class="sxs-lookup"><span data-stu-id="d93f1-120">In **Groups**, specify the groups you want to assign to the queue.</span></span> <span data-ttu-id="d93f1-121">執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="d93f1-121">Do one of the following:</span></span>
    
      - <span data-ttu-id="d93f1-122">若要將群組新增至佇列，請按一下 [ **選取**]。</span><span class="sxs-lookup"><span data-stu-id="d93f1-122">To add a group to the queue, click **Select**.</span></span> <span data-ttu-id="d93f1-123">在 [ **選取群組** ] 搜尋欄位中，輸入您要指派給佇列的代理人群組全部或部分名稱，然後按一下您想要的代理人群組，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d93f1-123">In the **Select Groups** search field, type all or part of the name of the agent group that you want to assign to the queue, click the agent group that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="d93f1-124">若要從佇列中移除群組，請在代理程式群組清單中，按一下您要移除的群組，然後按一下 [ **移除**]。</span><span class="sxs-lookup"><span data-stu-id="d93f1-124">To remove a group from the queue, in the list of agent groups, click the group that you want to remove, and then click **Remove**.</span></span>
    
      - <span data-ttu-id="d93f1-125">若要變更代理人的搜尋順序，請在代理人群組清單中，按一下群組，然後按一下向上箭號或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="d93f1-125">To change the order in which agents are searched, in the list of agent groups, click a group, and then click the up arrow or down arrow.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="d93f1-126">當伺服器搜尋佇列的可用代理程式時，會使用群組順序。</span><span class="sxs-lookup"><span data-stu-id="d93f1-126">When the server searches for an available agent for the queue, it uses group order.</span></span> <span data-ttu-id="d93f1-127">也就是會先搜尋清單中的第一個群組，然後是清單中的第二個群組，以此類推。</span><span class="sxs-lookup"><span data-stu-id="d93f1-127">That is, the first group in the list is searched first, followed by the second group in the list, and so on.</span></span>

        
        </div>

8.  <span data-ttu-id="d93f1-128">若要指定來電者等候專員接聽通話之前的最長保留期間，請選取 **[啟用佇列逾時]** 核取方塊，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="d93f1-128">To specify a maximum period of time for a caller to wait on hold before an agent answers the call, select the **Enable queue time-out** check box, and then do the following:</span></span>
    
    1.  <span data-ttu-id="d93f1-129">在 **[逾時期限 (秒)]** 中，指定來電者等候專員接聽通話的最長秒數。</span><span class="sxs-lookup"><span data-stu-id="d93f1-129">In **Time-out period (seconds)**, specify the maximum number of seconds a caller waits for an agent to answer the call.</span></span>
    
    2.  <span data-ttu-id="d93f1-130">在 **[撥號動作]** 中，選取通話逾時時進行的動作 (如下所示)：</span><span class="sxs-lookup"><span data-stu-id="d93f1-130">In **Call Action**, select the action that occurs when a call times out as follows:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="d93f1-131">若要在逾時之後中斷通話，請按一下 **[中斷連線]**。</span><span class="sxs-lookup"><span data-stu-id="d93f1-131">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
      - <span data-ttu-id="d93f1-132">若要將來電轉接至語音信箱，請按一下 [**轉寄至語音信箱**]，然後在 [ **sip 位址**] 欄位中輸入語音信箱位址，格式為 SIP： \<username\> @ \<domainname\> (例如，sip:bob@contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="d93f1-132">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip:\<username\>@\<domainname\> (for example, sip:bob@contoso.com).</span></span>
    
      - <span data-ttu-id="d93f1-133">若要將通話轉寄給另一個電話號碼，請按一下 [**轉寄給電話號碼**]，然後在 [ **sip 位址**] 欄位中，輸入以 [sip： (格式] 的電話號碼（ \<number\> @ \<domainname\> 例如，sip:+14255550121@contoso.com) ）。</span><span class="sxs-lookup"><span data-stu-id="d93f1-133">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip:\<number\>@\<domainname\> (for example, sip:+14255550121@contoso.com).</span></span>
    
      - <span data-ttu-id="d93f1-134">若要將呼叫轉寄給另一位使用者，請按一下 [**轉寄給 SIP 位址**]，然後在 [ **sip 位址**] 欄位中，以 [sip：] 的格式輸入使用者的 URI \<username\> @ \<domainname\> 。</span><span class="sxs-lookup"><span data-stu-id="d93f1-134">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip:\<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="d93f1-135">若要將通話轉接至另一個佇列，請按一下 **[轉接至其他佇列]**，然後瀏覽至想要使用的佇列。</span><span class="sxs-lookup"><span data-stu-id="d93f1-135">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>

9.  <span data-ttu-id="d93f1-136">若要指定佇列可以保留的通話數目上限，請選取 **[啟用佇列溢位]** 核取方塊，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="d93f1-136">To specify a maximum number of calls that the queue can hold, select the **Enable queue overflow** check box, and then do the following:</span></span>
    
    1.  <span data-ttu-id="d93f1-137">在 **[通話數目上限]** 中，選取想要佇列保留的通話數目上限。</span><span class="sxs-lookup"><span data-stu-id="d93f1-137">In **Maximum number of calls**, select the maximum number of calls that you want the queue to hold.</span></span>
    
    2.  <span data-ttu-id="d93f1-138">在 **[轉接來電]** 中，選取佇列已滿時要轉接的通話：**[最新通話]** 或 **[最早通話]**。</span><span class="sxs-lookup"><span data-stu-id="d93f1-138">In **Forward the call**, select which call is to be forwarded when the queue is full: **Newest Call** or **Oldest Call**.</span></span>
    
    3.  <span data-ttu-id="d93f1-139">在 [ **通話動作**] 中，選取符合溢出閾值時所發生的動作，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d93f1-139">In **Call action**, select the action that occurs when the overflow threshold is met as follows:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="d93f1-140">若要在逾時之後中斷通話，請按一下 **[中斷連線]**。</span><span class="sxs-lookup"><span data-stu-id="d93f1-140">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
      - <span data-ttu-id="d93f1-141">若要將來電轉接至語音信箱，請按一下 [**轉寄至語音信箱**]，然後在 [ **sip 位址**] 欄位中輸入語音信箱位址，格式為 SIP： \<username\> @ \<domainname\> (例如，sip:bob@contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="d93f1-141">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip:\<username\>@\<domainname\> (for example, sip:bob@contoso.com).</span></span>
    
      - <span data-ttu-id="d93f1-142">若要將通話轉寄給另一個電話號碼，請按一下 [**轉寄給電話號碼**]，然後在 [ **sip 位址**] 欄位中，輸入以 [sip： (格式] 的電話號碼（ \<number\> @ \<domainname\> 例如，sip:+14255550121@contoso.com) ）。</span><span class="sxs-lookup"><span data-stu-id="d93f1-142">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip:\<number\>@\<domainname\> (for example, sip:+14255550121@contoso.com).</span></span>
    
      - <span data-ttu-id="d93f1-143">若要將呼叫轉寄給另一位使用者，請按一下 [**轉寄給 SIP 位址**]，然後在 [ **sip 位址**] 欄位中，以 [sip：] 的格式輸入使用者的 URI \<username\> @ \<domainname\> 。</span><span class="sxs-lookup"><span data-stu-id="d93f1-143">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip:\<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="d93f1-144">若要將通話轉接至另一個佇列，請按一下 **[轉接至其他佇列]**，然後瀏覽至想要使用的佇列。</span><span class="sxs-lookup"><span data-stu-id="d93f1-144">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>

10. <span data-ttu-id="d93f1-145">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="d93f1-145">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-queue"></a><span data-ttu-id="d93f1-146">使用 Windows PowerShell 建立或修改佇列</span><span class="sxs-lookup"><span data-stu-id="d93f1-146">To use Windows PowerShell to create or modify a queue</span></span>

1.  <span data-ttu-id="d93f1-147">以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="d93f1-147">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d93f1-148">如果您是受管理工作流程的其中一位委派回應群組管理員，則可以建立代理人群組和佇列，並將代理群組指派給佇列。</span><span class="sxs-lookup"><span data-stu-id="d93f1-148">If you are one of the delegated Response Group Managers for a managed workflow, you will be able to create agent groups and queues, and assign agent groups to queues.</span></span>

    
    </div>

2.  <span data-ttu-id="d93f1-149">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="d93f1-149">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d93f1-150">建立當達到佇列的超時臨界值時要播放的提示，並將它儲存在變數中。</span><span class="sxs-lookup"><span data-stu-id="d93f1-150">Create the prompt to be played when the queue timeout threshold is met, and save it in a variable.</span></span> <span data-ttu-id="d93f1-151">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="d93f1-151">At the command line, run:</span></span>
    
        $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="d93f1-152">例如：</span><span class="sxs-lookup"><span data-stu-id="d93f1-152">For example:</span></span>
    
        "All agents are currently busy. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d93f1-153">若要使用音訊檔以進行提示，請使用 <STRONG>Import-CsRgsAudioFile</STRONG> Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d93f1-153">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="d93f1-154">如需詳細資訊，請參閱 <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>。</span><span class="sxs-lookup"><span data-stu-id="d93f1-154">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="d93f1-155">定義達到佇列的超時臨界值時要採取的動作，並將它儲存在變數中。</span><span class="sxs-lookup"><span data-stu-id="d93f1-155">Define the action to be taken when the queue timeout threshold is met, and save it in a variable.</span></span> <span data-ttu-id="d93f1-156">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="d93f1-156">At the command line, run:</span></span>
    
        $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d93f1-157">如需可能的動作及其語法的詳細資訊，請參閱 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>。</span><span class="sxs-lookup"><span data-stu-id="d93f1-157">For details about possible actions and their syntax, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="d93f1-158">例如：</span><span class="sxs-lookup"><span data-stu-id="d93f1-158">For example:</span></span>
    
        $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate

5.  <span data-ttu-id="d93f1-159">建立在達到佇列溢出閾值時要播放的提示，並將其儲存在變數中。</span><span class="sxs-lookup"><span data-stu-id="d93f1-159">Create the prompt to be played when the queue overflow threshold is met, and save it in a variable.</span></span> <span data-ttu-id="d93f1-160">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="d93f1-160">At the command line, run:</span></span>
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="d93f1-161">例如：</span><span class="sxs-lookup"><span data-stu-id="d93f1-161">For example:</span></span>
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d93f1-162">若要使用音訊檔以進行提示，請使用 <STRONG>Import-CsRgsAudioFile</STRONG> Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d93f1-162">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="d93f1-163">如需詳細資訊，請參閱 <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>。</span><span class="sxs-lookup"><span data-stu-id="d93f1-163">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

6.  <span data-ttu-id="d93f1-164">定義達到佇列溢出閾值時要採取的動作，並將其儲存在變數中。</span><span class="sxs-lookup"><span data-stu-id="d93f1-164">Define the action to be taken when the queue overflow threshold is met, and save it in a variable.</span></span> <span data-ttu-id="d93f1-165">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="d93f1-165">At the command line, run:</span></span>
    
        $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d93f1-166">如需可能的動作及其語法的詳細資訊，請參閱 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>。</span><span class="sxs-lookup"><span data-stu-id="d93f1-166">For details about possible actions and their syntax, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="d93f1-167">例如：</span><span class="sxs-lookup"><span data-stu-id="d93f1-167">For example:</span></span>
    
        $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate

7.  <span data-ttu-id="d93f1-168">取得回應群組服務的服務名稱，並將其指派給變數。</span><span class="sxs-lookup"><span data-stu-id="d93f1-168">Retrieve the service name for the Response Group service and assign it to a variable.</span></span> <span data-ttu-id="d93f1-169">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="d93f1-169">At the command line, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;

8.  <span data-ttu-id="d93f1-170">取得要指派給佇列的代理人群組的身分識別。</span><span class="sxs-lookup"><span data-stu-id="d93f1-170">Get the identity of the agent group to be assigned to the queue.</span></span> <span data-ttu-id="d93f1-171">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="d93f1-171">At the command line, run:</span></span>
    
        $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d93f1-172">如需建立代理人群組的詳細資訊，請參閱 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">New-CsRgsAgentGroup</A></span><span class="sxs-lookup"><span data-stu-id="d93f1-172">For details about creating the agent group, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">New-CsRgsAgentGroup</A></span></span>

    
    </div>

9.  <span data-ttu-id="d93f1-173">建立佇列。</span><span class="sxs-lookup"><span data-stu-id="d93f1-173">Create the queue.</span></span> <span data-ttu-id="d93f1-174">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="d93f1-174">At the command line, run:</span></span>
    
        $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
    
    <span data-ttu-id="d93f1-175">例如：</span><span class="sxs-lookup"><span data-stu-id="d93f1-175">For example:</span></span>
    
        $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;

10. <span data-ttu-id="d93f1-176">確認已建立佇列。</span><span class="sxs-lookup"><span data-stu-id="d93f1-176">Confirm that the queue is created.</span></span> <span data-ttu-id="d93f1-177">運行：</span><span class="sxs-lookup"><span data-stu-id="d93f1-177">Run:</span></span>
    
        Get-CsRgsQueue -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d93f1-178">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d93f1-178">See Also</span></span>


[<span data-ttu-id="d93f1-179">New-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="d93f1-179">New-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue)  
[<span data-ttu-id="d93f1-180">Set-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="d93f1-180">Set-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsQueue)  
[<span data-ttu-id="d93f1-181">New-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="d93f1-181">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[<span data-ttu-id="d93f1-182">New-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="d93f1-182">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
[<span data-ttu-id="d93f1-183">Get-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="d93f1-183">Get-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsQueue)  
[<span data-ttu-id="d93f1-184">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="d93f1-184">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
[<span data-ttu-id="d93f1-185">Remove-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="d93f1-185">Remove-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsQueue)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

