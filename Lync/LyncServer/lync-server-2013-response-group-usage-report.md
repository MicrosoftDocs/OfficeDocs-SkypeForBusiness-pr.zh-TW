---
title: Lync Server 2013：回應群組使用方式報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group Usage Report
ms:assetid: 3248b320-a552-400a-8485-6891af4eb0f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558632(v=OCS.15)
ms:contentKeyID: 48183811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 702ab291955ef7c8ec992e3607de581dff52b6a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-usage-report-in-lync-server-2013"></a><span data-ttu-id="2607b-102">Lync Server 2013 中的 [回應群組使用方式] 報告</span><span class="sxs-lookup"><span data-stu-id="2607b-102">Response Group Usage Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2607b-103">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="2607b-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="2607b-104">回應群組應用程式提供一種方式，讓 Microsoft Lync Server 2013 根據所撥打的號碼，以及在來電者對一系列問題的回應，來應答並傳送電話撥打電話。</span><span class="sxs-lookup"><span data-stu-id="2607b-104">The Response Group application provides a way for Microsoft Lync Server 2013 to answer and route phone calls based on the number that was dialed and, optionally, on the caller's responses to a series of questions.</span></span> <span data-ttu-id="2607b-105">通常，回應群組通話不會傳送給個別人，而是傳送給稱為「代理人」群組的人員小組。</span><span class="sxs-lookup"><span data-stu-id="2607b-105">Typically, Response Group calls are not routed to an individual person but, instead, are routed to a team of people referred to as an agent group.</span></span> <span data-ttu-id="2607b-106">例如，如果某人撥打電話號碼給您的技術支援人員，Lync Server 2013 可以自動將該呼叫路由到第一個可用的技術支援人員代理程式。</span><span class="sxs-lookup"><span data-stu-id="2607b-106">For example, if someone calls the phone number for your help desk, Lync Server 2013 can automatically route that call to the first available help desk agent.</span></span> <span data-ttu-id="2607b-107">或者，如果您遇到硬體問題，Lync Server 可能會提出一系列問題（「按1）。</span><span class="sxs-lookup"><span data-stu-id="2607b-107">Alternatively, Lync Server could ask a series of questions ("Press 1 if you are having hardware problems.</span></span> <span data-ttu-id="2607b-108">如果您遇到軟體問題，請按2。</span><span class="sxs-lookup"><span data-stu-id="2607b-108">Press 2 if you are having software problems.</span></span> <span data-ttu-id="2607b-109">如果您有網路問題，請按3。）然後根據這些問題的答案，將呼叫路由到最合適的技術支援人員。</span><span class="sxs-lookup"><span data-stu-id="2607b-109">Press 3 if you are having network problems.") and then route the call to the most appropriate help desk agent based on the answer to those questions.</span></span>

<span data-ttu-id="2607b-110">[回應群組使用方式] 報告詳細瞭解所有回應群組工作流程接收到的電話數，然後將這些通話中斷為更有限的類別，例如提供的通話、接聽的通話，以及已放棄的通話。</span><span class="sxs-lookup"><span data-stu-id="2607b-110">The Response Group Usage Report provides a detailed look at the number of phone calls received by all your Response Group workflows, then breaks those calls down into more finite categories such as Offered calls, Answered calls, and Abandoned calls.</span></span>

<span data-ttu-id="2607b-111">使用回應群組使用方式報告的關鍵是瞭解報告通話類型之間的差異：</span><span class="sxs-lookup"><span data-stu-id="2607b-111">The key to working with the Response Group Usage Report is to understand the difference between the reported call types:</span></span>

  - <span data-ttu-id="2607b-112">**已接收來電**。</span><span class="sxs-lookup"><span data-stu-id="2607b-112">**Received calls**.</span></span> <span data-ttu-id="2607b-113">所有回應群組應用程式實例接收到的呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="2607b-113">Total number of calls received by all instances of the Response Group application.</span></span>

  - <span data-ttu-id="2607b-114">**成功的通話**。</span><span class="sxs-lookup"><span data-stu-id="2607b-114">**Successful calls**.</span></span> <span data-ttu-id="2607b-115">回應群組應用程式所挑選的通話總數目。</span><span class="sxs-lookup"><span data-stu-id="2607b-115">Total number of calls that were picked up by the Response Group application.</span></span>

  - <span data-ttu-id="2607b-116">已**提供來電**。</span><span class="sxs-lookup"><span data-stu-id="2607b-116">**Offered calls**.</span></span> <span data-ttu-id="2607b-117">傳送給回應群組代理程式的呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="2607b-117">Total number of calls that were transferred to a Response Group agent.</span></span>

  - <span data-ttu-id="2607b-118">已**接聽通話**。</span><span class="sxs-lookup"><span data-stu-id="2607b-118">**Answered calls**.</span></span> <span data-ttu-id="2607b-119">已由回應群組代理程式實際接聽的通話總數目。</span><span class="sxs-lookup"><span data-stu-id="2607b-119">Total number of calls that were actually answered by a Response Group agent.</span></span>

  - <span data-ttu-id="2607b-120">已**放棄通話的百分比**。</span><span class="sxs-lookup"><span data-stu-id="2607b-120">**Percentage of abandoned calls**.</span></span> <span data-ttu-id="2607b-121">回應群組應用程式接收，但沒有由代理程式接聽的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="2607b-121">Percentage of calls that were received by the Response Group application but were never answered by an agent.</span></span> <span data-ttu-id="2607b-122">此值的計算方法是從收到的電話減去接聽的通話，然後根據收到的通話數來除以該值。</span><span class="sxs-lookup"><span data-stu-id="2607b-122">This value is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of Received calls.</span></span> <span data-ttu-id="2607b-123">例如，如果您收到10個通話，且已接聽7個，您會從10減去7，然後離開3個未回復的通話。</span><span class="sxs-lookup"><span data-stu-id="2607b-123">For example, if you received 10 calls and 7 were answered, you would subtract 7 from 10, leaving 3 unanswered calls.</span></span> <span data-ttu-id="2607b-124">這個值將除以10，從而讓您放棄通話百分比30%。</span><span class="sxs-lookup"><span data-stu-id="2607b-124">That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span>

  - <span data-ttu-id="2607b-125">**轉接來電**。</span><span class="sxs-lookup"><span data-stu-id="2607b-125">**Transferred calls**.</span></span> <span data-ttu-id="2607b-126">由於佇列超時或佇列溢出而轉移之回應群組通話的總數。</span><span class="sxs-lookup"><span data-stu-id="2607b-126">Total number of Response Group calls that were transferred because of a queue timeout or queue overflow.</span></span>

<span data-ttu-id="2607b-127">如果您正在查看 [回應群組使用量] 報告，而且不記得任何這些撥號類型的定義，只要將滑鼠放在適當的通話類型標籤上即可。</span><span class="sxs-lookup"><span data-stu-id="2607b-127">If you are looking at the Response Group Usage Report and can't remember the definition for any of these call types, simply hold your mouse over the appropriate call type label.</span></span> <span data-ttu-id="2607b-128">隨即會出現工具提示，其中提供通話類型的簡短描述。</span><span class="sxs-lookup"><span data-stu-id="2607b-128">A tooltip will appear that offers a brief description of the call type.</span></span>

<span data-ttu-id="2607b-129">[回應群組使用方式] 報告可讓您篩選工作流程 URI （與該工作流程相關聯的 SIP 位址）。</span><span class="sxs-lookup"><span data-stu-id="2607b-129">The Response Group Usage Report allows you to filter on a workflow URI (the SIP address associated with that workflow).</span></span> <span data-ttu-id="2607b-130">不過，工作流程 Uri 實際上不會出現在報表本身。</span><span class="sxs-lookup"><span data-stu-id="2607b-130">However, workflow URIs do not actually appear on the report itself.</span></span> <span data-ttu-id="2607b-131">如果您想知道哪些工作流程正在接聽最多來電，或是哪些工作流程遇到最大的通話，請按一下適當的度量單位，以開啟該特定時段的回應群組通話清單報告。</span><span class="sxs-lookup"><span data-stu-id="2607b-131">If you would like to know things such as which workflows are answering the most calls or which workflows are experiencing the most transferred calls, click the appropriate metric to open the Response Group Call List Report for that given time period.</span></span> <span data-ttu-id="2607b-132">該報告會列出工作流程 Uri。</span><span class="sxs-lookup"><span data-stu-id="2607b-132">That reports does list the workflow URIs.</span></span>

<div>

## <a name="accessing-the-response-group-usage-report"></a><span data-ttu-id="2607b-133">存取回應群組使用方式報告</span><span class="sxs-lookup"><span data-stu-id="2607b-133">Accessing the Response Group Usage Report</span></span>

<span data-ttu-id="2607b-134">[回應群組使用方式] 報告是從 [監控報告] 首頁存取。</span><span class="sxs-lookup"><span data-stu-id="2607b-134">The Response Group Usage Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="2607b-135">您可以按一下下列任一度量，[在 Lync Server 2013 中向下切入 [回應群組通話清單] 報告](lync-server-2013-response-group-call-list-report.md)：</span><span class="sxs-lookup"><span data-stu-id="2607b-135">You can drill down to the [Response Group Call List Report in Lync Server 2013](lync-server-2013-response-group-call-list-report.md) by clicking any of the following metrics:</span></span>

  - <span data-ttu-id="2607b-136">已接聽通話</span><span class="sxs-lookup"><span data-stu-id="2607b-136">Received calls</span></span>

  - <span data-ttu-id="2607b-137">成功的通話</span><span class="sxs-lookup"><span data-stu-id="2607b-137">Successful calls</span></span>

  - <span data-ttu-id="2607b-138">已提供通話</span><span class="sxs-lookup"><span data-stu-id="2607b-138">Offered calls</span></span>

  - <span data-ttu-id="2607b-139">已接聽通話</span><span class="sxs-lookup"><span data-stu-id="2607b-139">Answered calls</span></span>

  - <span data-ttu-id="2607b-140">已轉移通話</span><span class="sxs-lookup"><span data-stu-id="2607b-140">Transferred calls</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-usage-report"></a><span data-ttu-id="2607b-141">充分利用 [回應群組使用量] 報告</span><span class="sxs-lookup"><span data-stu-id="2607b-141">Making the Best Use of the Response Group Usage Report</span></span>

<span data-ttu-id="2607b-142">[回應群組使用量] 報告的其中一個較有趣的用途，可能不容易看出：能夠針對單一回應群組工作流程檢索使用方式資訊。</span><span class="sxs-lookup"><span data-stu-id="2607b-142">One of the more interesting uses of the Response Group Usage Report might not be readily apparent: the ability to retrieve usage information for a single Response Group workflow.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="2607b-143">回應群組工作流程基本上是一組指示您的 Lync Server 在使用者撥打電話號碼時要執行的動作。</span><span class="sxs-lookup"><span data-stu-id="2607b-143">A Response Group workflow is basically a set of instructions that determines what Lync Server does when a user dials a particular phone number.</span></span> <span data-ttu-id="2607b-144">如此一來，每個工作流程都會與電話號碼建立唯一的關聯。</span><span class="sxs-lookup"><span data-stu-id="2607b-144">To that end, each workflow is uniquely associated with a phone number.</span></span> <span data-ttu-id="2607b-145">當某人呼叫該號碼時，工作流程會判斷通話的處理方式。</span><span class="sxs-lookup"><span data-stu-id="2607b-145">When someone calls that number, the workflow determines how the call will be handled.</span></span> <span data-ttu-id="2607b-146">例如，工作流程可能會將呼叫路由到一系列的互動式語音回應（IVR）問題，提示來電者輸入其他資訊（「按1取得硬體支援。</span><span class="sxs-lookup"><span data-stu-id="2607b-146">For example, the workflow might cause the call to be routed to a series of interactive voice response (IVR) questions that prompt the caller to enter additional information ("Press 1 for hardware support.</span></span> <span data-ttu-id="2607b-147">按下2取得軟體支援。</span><span class="sxs-lookup"><span data-stu-id="2607b-147">Press 2 for software support.").</span></span> <span data-ttu-id="2607b-148">或者，工作流程可能會導致呼叫放在佇列中，而呼叫者則會停留在通話中，直到有可用的工程師接聽通話。</span><span class="sxs-lookup"><span data-stu-id="2607b-148">Alternatively, the workflow might cause the call to be placed in a queue , with the caller put on hold until an agent is available to answer the call.</span></span> <span data-ttu-id="2607b-149">您也可以使用工作流程來設定接聽電話的代理程式的可用性： [工作流程] 是用來設定兩個上班時間（一周中的天數，以及可供代理接聽之電話的時間）和假日（沒有代理程式可供應答的天數）。通話）。</span><span class="sxs-lookup"><span data-stu-id="2607b-149">The availability of agents to answer calls is also dictated by the workflow: workflows are used to configure both business hours (the days of the week and the times of day when agents are available to answer calls) and holidays (days when no agents are available to answer calls).</span></span> <span data-ttu-id="2607b-150">任何時候只要您撥打屬於回應群組應用程式的電話號碼，您就會實質呼叫回應群組工作流程。</span><span class="sxs-lookup"><span data-stu-id="2607b-150">Any time you dial a phone number that belongs to the Response Group application you are essentially calling a Response Group workflow.</span></span>



</div>

<span data-ttu-id="2607b-151">雖然工作流程 Uri 不會出現在 [回應群組使用量] 報告中，但仍可以查看單一工作流程的使用方式統計資料，這項功能通常相當有用。</span><span class="sxs-lookup"><span data-stu-id="2607b-151">Although workflow URIs do not appear in the Response Group Usage Report, it's still possible to view the usage statistics for a single workflow, something that is often extremely useful.</span></span> <span data-ttu-id="2607b-152">例如，假設您最近 unveiled 新的廣告活動，而且想知道人員是否正在撥打電話給該產品。</span><span class="sxs-lookup"><span data-stu-id="2607b-152">For example, suppose you recently unveiled a new ad campaign and are curious to know whether people are calling in to ask about that product.</span></span> <span data-ttu-id="2607b-153">如果您已將回應群組工作流程與廣告行銷活動中指定的電話號碼相關聯，您可以輕鬆檢查是否有多少人（如果有）撥打該號碼。</span><span class="sxs-lookup"><span data-stu-id="2607b-153">If you have associated a Response Group workflow with the phone number given in the ad campaign, you can easily check to see how many people (if any) are calling that number.</span></span>

<span data-ttu-id="2607b-154">您也可以使用類似的方法來測量由您的內部問訊台或客戶服務部門處理的通話數量。</span><span class="sxs-lookup"><span data-stu-id="2607b-154">You might also use a similar approach to gauge the number of calls being handled by your internal help desk or your customer service department.</span></span>

<span data-ttu-id="2607b-155">若要查看特定工作流程的使用方式統計資料，請在 [工作流程 URI] 方塊中輸入工作流程 URI。</span><span class="sxs-lookup"><span data-stu-id="2607b-155">To review usage statistics for a particular workflow, enter the workflow URI in the Workflow URI box.</span></span> <span data-ttu-id="2607b-156">當然，如所述，工作流程 Uri （與工作流程相關聯的 SIP 位址）不會出現在報表上。</span><span class="sxs-lookup"><span data-stu-id="2607b-156">Of course, as noted, workflow URIs (the SIP address associated with a workflow) do not appear on the report.</span></span> <span data-ttu-id="2607b-157">這表示您需要尋找一些其他方法來判斷工作流程的 URI。</span><span class="sxs-lookup"><span data-stu-id="2607b-157">That means you need to find some other way to determine the URI of a workflow.</span></span> <span data-ttu-id="2607b-158">其中一個方法是使用 Windows PowerShell 和 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="2607b-158">One way to do this is to use Windows PowerShell and the Lync Server Management Shell.</span></span> <span data-ttu-id="2607b-159">例如，這個命令會傳回所有回應群組工作流程的 Uri：</span><span class="sxs-lookup"><span data-stu-id="2607b-159">For example, this command returns the URIs for all your Response Group workflows:</span></span>

    Get-CsRgsWorkflow | Select-Object Name, PrimaryUri

<span data-ttu-id="2607b-160">這樣會傳回如下所示的資料：</span><span class="sxs-lookup"><span data-stu-id="2607b-160">That will return data similar to this:</span></span>

    Name                            PrimaryUri
    ----                            ----------
    Customer Support                sip:support@litwareinc.com
    Help Desk                       sip:helpdesk@litwareinc.com
    New Ad Campaign                 sip:newads@litwareinc.com

<span data-ttu-id="2607b-161">這個命令會傳回單一工作流程的資訊，其中一個工作流程是 [新廣告活動] 的名稱：</span><span class="sxs-lookup"><span data-stu-id="2607b-161">This command returns information for a single workflow, the one with the name New Ad Campaign:</span></span>

    Get-CsRgsWorkflow -Name "New Ad Campaign" | Select-Object Name, PrimaryUri

</div>

<div>

## <a name="filters"></a><span data-ttu-id="2607b-162">濾鏡</span><span class="sxs-lookup"><span data-stu-id="2607b-162">Filters</span></span>

<span data-ttu-id="2607b-163">篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="2607b-163">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="2607b-164">例如，[回應群組使用方式] 報告可讓您查看所有回應群組工作流程的資料，或查看個別工作流程的資料。</span><span class="sxs-lookup"><span data-stu-id="2607b-164">For example, the Response Group Usage Report enables you to view data for all your Response Group workflows or to view data for an individual workflow.</span></span> <span data-ttu-id="2607b-165">您也可以選擇分組資料的方式。</span><span class="sxs-lookup"><span data-stu-id="2607b-165">You can also choose how data should be grouped.</span></span> <span data-ttu-id="2607b-166">在這種情況下，使用方式會依小時、日、周或月分組。</span><span class="sxs-lookup"><span data-stu-id="2607b-166">In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="2607b-167">下表列出可與回應群組使用方式報告搭配使用的篩選。</span><span class="sxs-lookup"><span data-stu-id="2607b-167">The following table lists the filters that you can use with the Response Group Usage Report.</span></span>

### <a name="response-group-usage-report-filters"></a><span data-ttu-id="2607b-168">回應群組使用方式報表篩選</span><span class="sxs-lookup"><span data-stu-id="2607b-168">Response Group Usage Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2607b-169">名稱</span><span class="sxs-lookup"><span data-stu-id="2607b-169">Name</span></span></th>
<th><span data-ttu-id="2607b-170">說明</span><span class="sxs-lookup"><span data-stu-id="2607b-170">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2607b-171"><strong>從</strong></span><span class="sxs-lookup"><span data-stu-id="2607b-171"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="2607b-172">時間範圍的開始日期/時間。</span><span class="sxs-lookup"><span data-stu-id="2607b-172">Start date/time for the time range.</span></span> <span data-ttu-id="2607b-173">若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2607b-173">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="2607b-174">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="2607b-174">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="2607b-175">如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。</span><span class="sxs-lookup"><span data-stu-id="2607b-175">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="2607b-176">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="2607b-176">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2607b-177">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="2607b-177">7/7/2012</span></span></p>
<p><span data-ttu-id="2607b-178">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="2607b-178">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2607b-179">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="2607b-179">7/3/2012</span></span></p>
<p><span data-ttu-id="2607b-180">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="2607b-180">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2607b-181"><strong>自</strong></span><span class="sxs-lookup"><span data-stu-id="2607b-181"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="2607b-182">時間範圍的結束日期/時間。</span><span class="sxs-lookup"><span data-stu-id="2607b-182">End date/time for the time range.</span></span> <span data-ttu-id="2607b-183">若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2607b-183">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="2607b-184">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="2607b-184">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="2607b-185">如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。</span><span class="sxs-lookup"><span data-stu-id="2607b-185">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="2607b-186">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="2607b-186">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2607b-187">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="2607b-187">7/7/2012</span></span></p>
<p><span data-ttu-id="2607b-188">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="2607b-188">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2607b-189">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="2607b-189">7/3/2012</span></span></p>
<p><span data-ttu-id="2607b-190">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="2607b-190">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2607b-191"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="2607b-191"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="2607b-192">時間間隔。</span><span class="sxs-lookup"><span data-stu-id="2607b-192">Time interval.</span></span> <span data-ttu-id="2607b-193">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="2607b-193">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2607b-194">每小時（最多可顯示25小時）</span><span class="sxs-lookup"><span data-stu-id="2607b-194">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="2607b-195">每天（最多可以顯示31天）</span><span class="sxs-lookup"><span data-stu-id="2607b-195">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="2607b-196">每週（最多可以顯示12周）</span><span class="sxs-lookup"><span data-stu-id="2607b-196">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="2607b-197">每月（最多可以顯示12個月）</span><span class="sxs-lookup"><span data-stu-id="2607b-197">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="2607b-198">如果 [開始] 和 [結束] 日期超過所選間隔所允許的最大值數，則會顯示值的數目上限（從開始日期開始）。</span><span class="sxs-lookup"><span data-stu-id="2607b-198">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="2607b-199">例如，如果您選取 [開始日期 7/7/2012] 和 [結束日期] 2/28/2012 的 [日間隔]，則會顯示 8/7/2012 12:00 AM 至 9/7/2012 12:00 AM （也就是31天內的資料）的資料。</span><span class="sxs-lookup"><span data-stu-id="2607b-199">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2607b-200"><strong>工作流程 URI</strong></span><span class="sxs-lookup"><span data-stu-id="2607b-200"><strong>Workflow URI</strong></span></span></p></td>
<td><p><span data-ttu-id="2607b-201">可讓您將傳回的資料限制在指定的回應群組工作流程中。</span><span class="sxs-lookup"><span data-stu-id="2607b-201">Enables you to limit the returned data to the specified Response Group workflow.</span></span> <span data-ttu-id="2607b-202">若要使用這個篩選器，請輸入工作流程 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="2607b-202">To use this filter, enter the Workflow SIP address.</span></span> <span data-ttu-id="2607b-203">例如：</span><span class="sxs-lookup"><span data-stu-id="2607b-203">For example:</span></span></p>
<p><span data-ttu-id="2607b-204">sip:helpdesk@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2607b-204">sip:helpdesk@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="2607b-205">指標</span><span class="sxs-lookup"><span data-stu-id="2607b-205">Metrics</span></span>

<span data-ttu-id="2607b-206">下表列出 [回應群組使用量] 報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="2607b-206">The following table lists the information provided in the Response Group Usage Report.</span></span>

### <a name="response-group-usage-report-metrics"></a><span data-ttu-id="2607b-207">回應群組使用方式報告度量單位</span><span class="sxs-lookup"><span data-stu-id="2607b-207">Response Group Usage Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2607b-208">名稱</span><span class="sxs-lookup"><span data-stu-id="2607b-208">Name</span></span></th>
<th><span data-ttu-id="2607b-209">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="2607b-209">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="2607b-210">說明</span><span class="sxs-lookup"><span data-stu-id="2607b-210">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2607b-211"><strong>工資</strong></span><span class="sxs-lookup"><span data-stu-id="2607b-211"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="2607b-212"><strong>日常</strong></span><span class="sxs-lookup"><span data-stu-id="2607b-212"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="2607b-213"><strong>周更新</strong></span><span class="sxs-lookup"><span data-stu-id="2607b-213"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="2607b-214"><strong>次</strong></span><span class="sxs-lookup"><span data-stu-id="2607b-214"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="2607b-215">否</span><span class="sxs-lookup"><span data-stu-id="2607b-215">No</span></span></p></td>
<td><p><span data-ttu-id="2607b-216">指出選取的時間間隔。</span><span class="sxs-lookup"><span data-stu-id="2607b-216">Indicates the selected time interval.</span></span> <span data-ttu-id="2607b-217">在適當的地方，您可以按一下指定的時間間隔，以查看該間隔的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="2607b-217">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="2607b-218">例如，如果您使用的是每日間隔，而您按一下 [7/7/2012]，就會看到該日期的使用者註冊活動的每小時細目。</span><span class="sxs-lookup"><span data-stu-id="2607b-218">For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2607b-219"><strong>已接聽通話</strong></span><span class="sxs-lookup"><span data-stu-id="2607b-219"><strong>Received calls</strong></span></span></p></td>
<td><p><span data-ttu-id="2607b-220">否</span><span class="sxs-lookup"><span data-stu-id="2607b-220">No</span></span></p></td>
<td><p><span data-ttu-id="2607b-221">所有回應群組應用程式實例接收到的呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="2607b-221">Total number of calls received by all instances of the Response Group application.</span></span> <span data-ttu-id="2607b-222">當您按一下此專案時，報告會顯示所選時段的回應群組通話清單報告。</span><span class="sxs-lookup"><span data-stu-id="2607b-222">When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2607b-223"><strong>成功的通話</strong></span><span class="sxs-lookup"><span data-stu-id="2607b-223"><strong>Successful calls</strong></span></span></p></td>
<td><p><span data-ttu-id="2607b-224">否</span><span class="sxs-lookup"><span data-stu-id="2607b-224">No</span></span></p></td>
<td><p><span data-ttu-id="2607b-225">已挑選回應群組應用程式的通話總數目。</span><span class="sxs-lookup"><span data-stu-id="2607b-225">Total number of calls that were picked up the Response Group application.</span></span> <span data-ttu-id="2607b-226">當您按一下此專案時，報告會顯示所選時段的回應群組通話清單報告。</span><span class="sxs-lookup"><span data-stu-id="2607b-226">When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2607b-227"><strong>已提供通話</strong></span><span class="sxs-lookup"><span data-stu-id="2607b-227"><strong>Offered calls</strong></span></span></p></td>
<td><p><span data-ttu-id="2607b-228">否</span><span class="sxs-lookup"><span data-stu-id="2607b-228">No</span></span></p></td>
<td><p><span data-ttu-id="2607b-229">傳送給回應群組代理程式的呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="2607b-229">Total number of calls that were transferred to a Response Group agent.</span></span> <span data-ttu-id="2607b-230">當您按一下此專案時，報告會顯示所選時段的回應群組通話清單報告。</span><span class="sxs-lookup"><span data-stu-id="2607b-230">When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2607b-231"><strong>已接聽通話</strong></span><span class="sxs-lookup"><span data-stu-id="2607b-231"><strong>Answered calls</strong></span></span></p></td>
<td><p><span data-ttu-id="2607b-232">否</span><span class="sxs-lookup"><span data-stu-id="2607b-232">No</span></span></p></td>
<td><p><span data-ttu-id="2607b-233">已由回應群組代理程式實際接聽的通話總數目。</span><span class="sxs-lookup"><span data-stu-id="2607b-233">Total number of calls that were actually answered by a Response Group agent.</span></span> <span data-ttu-id="2607b-234">當您按一下此專案時，報告會顯示所選時段的回應群組通話清單報告。</span><span class="sxs-lookup"><span data-stu-id="2607b-234">When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2607b-235"><strong>已放棄通話的百分比</strong></span><span class="sxs-lookup"><span data-stu-id="2607b-235"><strong>Percentage of abandoned calls</strong></span></span></p></td>
<td><p><span data-ttu-id="2607b-236">否</span><span class="sxs-lookup"><span data-stu-id="2607b-236">No</span></span></p></td>
<td><p><span data-ttu-id="2607b-237">回應群組應用程式接收，但沒有由代理程式接聽的通話總數量。</span><span class="sxs-lookup"><span data-stu-id="2607b-237">Total number of calls that were received by the Response Group application but were never answered by an agent.</span></span> <span data-ttu-id="2607b-238">這是透過從接收到的電話減去接聽的通話，然後根據接收到的通話數來計算。</span><span class="sxs-lookup"><span data-stu-id="2607b-238">This is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of received calls.</span></span> <span data-ttu-id="2607b-239">例如，如果您有10個來電，而且接聽了7個，您會從10減去七個，然後離開三個未回答的通話。</span><span class="sxs-lookup"><span data-stu-id="2607b-239">For example, if you have 10 received calls and seven were answered, you would subtract seven from 10, leaving three unanswered calls.</span></span> <span data-ttu-id="2607b-240">這個值將除以10，從而讓您放棄通話百分比30%。</span><span class="sxs-lookup"><span data-stu-id="2607b-240">That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2607b-241"><strong>每個代理的平均通話分鐘數</strong></span><span class="sxs-lookup"><span data-stu-id="2607b-241"><strong>Average call minutes by agent</strong></span></span></p></td>
<td><p><span data-ttu-id="2607b-242">否</span><span class="sxs-lookup"><span data-stu-id="2607b-242">No</span></span></p></td>
<td><p><span data-ttu-id="2607b-243">回應群組代理程式在通話上花費的平均時間長度。</span><span class="sxs-lookup"><span data-stu-id="2607b-243">Average amount of time a Response Group agent spent on a call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2607b-244"><strong>已轉移通話</strong></span><span class="sxs-lookup"><span data-stu-id="2607b-244"><strong>Transferred calls</strong></span></span></p></td>
<td><p><span data-ttu-id="2607b-245">否</span><span class="sxs-lookup"><span data-stu-id="2607b-245">No</span></span></p></td>
<td><p><span data-ttu-id="2607b-246">由於佇列超時或佇列溢出而轉移之回應群組通話的總數。</span><span class="sxs-lookup"><span data-stu-id="2607b-246">Total number of Response Group calls that were transferred because of a queue timeout or queue overflow.</span></span> <span data-ttu-id="2607b-247">當您按一下此專案時，報告會顯示所選時段的回應群組通話清單報告。</span><span class="sxs-lookup"><span data-stu-id="2607b-247">When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

