---
title: Lync Server 2013： 回應群組通話清單報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group Call List Report
ms:assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615443(v=OCS.15)
ms:contentKeyID: 48184954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e02c5493f8582d401ea02df3f94cd2df57e0093
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214889"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="response-group-call-list-report-in-lync-server-2013"></a><span data-ttu-id="7582d-102">Lync Server 2013 中的回應群組通話清單報告</span><span class="sxs-lookup"><span data-stu-id="7582d-102">Response Group Call List Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7582d-103">_**上次修改主題：** 2013年-02-22_</span><span class="sxs-lookup"><span data-stu-id="7582d-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="7582d-104">回應群組應用程式提供方法讓 Microsoft Lync Server 2013 來接聽和路由電話上所撥打的號碼，並選擇性地在一系列的問題的發話者的回覆。</span><span class="sxs-lookup"><span data-stu-id="7582d-104">The Response Group application provides a way for Microsoft Lync Server 2013 to answer and route phone calls based on the number that was dialed and, optionally, on the caller's responses to a series of questions.</span></span> <span data-ttu-id="7582d-105">系統通常不會將回應群組通話路由傳送給個人，而是將通話路由傳送給稱為代理群組的一組人員。</span><span class="sxs-lookup"><span data-stu-id="7582d-105">Typically, Response Group calls are not routed to an individual person but, instead, are routed to a team of people referred to as an agent group.</span></span> <span data-ttu-id="7582d-106">例如，如果某人撥打的電話號碼為您的服務台，Lync Server 2013 可以自動路由傳送該呼叫的第一個可用的說明 desk 代理程式。</span><span class="sxs-lookup"><span data-stu-id="7582d-106">For example, if someone calls the phone number for your help desk, Lync Server 2013 can automatically route that call to the first available help desk agent.</span></span> <span data-ttu-id="7582d-107">或者，Lync Server 可能會要求一系列的問題 (「 按下 1 如果您有硬體問題。</span><span class="sxs-lookup"><span data-stu-id="7582d-107">Alternatively, Lync Server could ask a series of questions ("Press 1 if you are having hardware problems.</span></span> <span data-ttu-id="7582d-108">軟體問題請按 2。</span><span class="sxs-lookup"><span data-stu-id="7582d-108">Press 2 if you are having software problems.</span></span> <span data-ttu-id="7582d-109">按 3 如果您有網路問題 」）。然後將呼叫路由至最適當說明支援工程師的代理程式根據這些問題的答案。</span><span class="sxs-lookup"><span data-stu-id="7582d-109">Press 3 if you are having network problems.") and then route the call to the most appropriate help desk agent based on the answer to those questions.</span></span>

<span data-ttu-id="7582d-110">回應群組通話清單報告代表一群通話所做的一段時間的時間與指定類型的呼叫。</span><span class="sxs-lookup"><span data-stu-id="7582d-110">The Response Group Call List Report represents a collection of calls made for a specified period of time and for a specified type of call.</span></span> <span data-ttu-id="7582d-111">回應群組使用量報告 （其必須先開啟之前您可以開啟回應群組通話清單報告） 可辨識下列通話類型：</span><span class="sxs-lookup"><span data-stu-id="7582d-111">The Response Group Usage Report (which must be opened first before you can open the Response Group Call List Report) recognizes the following call types:</span></span>

  - <span data-ttu-id="7582d-112">**接收的通話**。</span><span class="sxs-lookup"><span data-stu-id="7582d-112">**Received calls**.</span></span> <span data-ttu-id="7582d-113">回應群組應用程式的所有執行個體接收的通話總數。</span><span class="sxs-lookup"><span data-stu-id="7582d-113">Total number of calls received by all instances of the Response Group application.</span></span>

  - <span data-ttu-id="7582d-114">**成功的通話**。</span><span class="sxs-lookup"><span data-stu-id="7582d-114">**Successful calls**.</span></span> <span data-ttu-id="7582d-115">已收取的回應群組應用程式的通話總數。</span><span class="sxs-lookup"><span data-stu-id="7582d-115">Total number of calls that were picked up by the Response Group application.</span></span>

  - <span data-ttu-id="7582d-p105">**提供的通話**。轉接至回應群組代理程式的通話總數。</span><span class="sxs-lookup"><span data-stu-id="7582d-p105">**Offered calls**. Total number of calls that were transferred to a Response Group agent.</span></span>

  - <span data-ttu-id="7582d-p106">**接聽的通話**。回應群組代理程式實際接聽的通話總數。</span><span class="sxs-lookup"><span data-stu-id="7582d-p106">**Answered calls**. Total number of calls that were actually answered by a Response Group agent.</span></span>

  - <span data-ttu-id="7582d-120">放棄的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="7582d-120">Percentage of abandoned calls.</span></span> <span data-ttu-id="7582d-121">回應群組應用程式已接收，但代理從未接聽的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="7582d-121">Percentage of calls that were received by the Response Group application but were never answered by an agent.</span></span> <span data-ttu-id="7582d-122">這是從接收的通話減掉接聽的通話，再除以接收的通話數，所計算出來的值。</span><span class="sxs-lookup"><span data-stu-id="7582d-122">This value is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of Received calls.</span></span> <span data-ttu-id="7582d-123">例如，如果您接收到 10 次通話，並接聽 7 次，就要從 10 減掉 7，剩下 3 次未接聽的通話。</span><span class="sxs-lookup"><span data-stu-id="7582d-123">For example, if you received 10 calls and 7 were answered, you would subtract 7 from 10, leaving 3 unanswered calls.</span></span> <span data-ttu-id="7582d-124">該值再除以 10，則得到的放棄通話百分比為 30%。</span><span class="sxs-lookup"><span data-stu-id="7582d-124">That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span>

  - <span data-ttu-id="7582d-125">**轉接的通話**。</span><span class="sxs-lookup"><span data-stu-id="7582d-125">**Transferred calls**.</span></span> <span data-ttu-id="7582d-126">因為佇列逾時或佇列溢位而轉接的回應群組通話總數。</span><span class="sxs-lookup"><span data-stu-id="7582d-126">Total number of Response Group calls that were transferred because of a queue timeout or queue overflow.</span></span>

<div>

## <a name="accessing-the-response-group-call-list-report"></a><span data-ttu-id="7582d-127">存取回應群組通話清單報告</span><span class="sxs-lookup"><span data-stu-id="7582d-127">Accessing the Response Group Call List Report</span></span>

<span data-ttu-id="7582d-128">按一下 [ [Lync Server 2013 中的回應群組使用量報告](lync-server-2013-response-group-usage-report.md)上找到下列計量之一只可以存取回應群組通話清單報告：</span><span class="sxs-lookup"><span data-stu-id="7582d-128">The Response Group Call List Report can only be accessed by clicking one of the following metrics found on the [Response Group Usage Report in Lync Server 2013](lync-server-2013-response-group-usage-report.md):</span></span>

  - <span data-ttu-id="7582d-129">接收的通話</span><span class="sxs-lookup"><span data-stu-id="7582d-129">Received calls</span></span>

  - <span data-ttu-id="7582d-130">成功的通話</span><span class="sxs-lookup"><span data-stu-id="7582d-130">Successful calls</span></span>

  - <span data-ttu-id="7582d-131">提供的通話</span><span class="sxs-lookup"><span data-stu-id="7582d-131">Offered calls</span></span>

  - <span data-ttu-id="7582d-132">接聽的通話</span><span class="sxs-lookup"><span data-stu-id="7582d-132">Answered calls</span></span>

  - <span data-ttu-id="7582d-133">轉接的通話</span><span class="sxs-lookup"><span data-stu-id="7582d-133">Transferred calls</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a><span data-ttu-id="7582d-134">最大效用的回應群組通話清單報告</span><span class="sxs-lookup"><span data-stu-id="7582d-134">Making the Best Use of the Response Group Call List Report</span></span>

<span data-ttu-id="7582d-135">回應群組通話清單報告可讓您限制對通話牽涉到特定的回應群組工作流程顯示的資料。</span><span class="sxs-lookup"><span data-stu-id="7582d-135">The Response Group Call List Report allows you to limit the displayed data to calls involving a particular Response Group workflow.</span></span> <span data-ttu-id="7582d-136">若要這樣做，您需要在 [工作流程 URI] 方塊中輸入工作流程 （工作流程的 SIP 位址） 的 URI。</span><span class="sxs-lookup"><span data-stu-id="7582d-136">To do that, you need to enter the workflow URI (the workflow's SIP address) in the Workflow URI box.</span></span> <span data-ttu-id="7582d-137">您可以這麼做之前，不過，您必須實際能夠看到工作流程 URI] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="7582d-137">Before you can do that, however, you must actually be able to see the Workflow URI box.</span></span> <span data-ttu-id="7582d-138">若要顯示回應群組通話清單報告的篩選選項，請按一下 [報表] 視窗的左上左邊部分中的 [顯示/隱藏參數] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="7582d-138">To display the filtering options for the Response Group Call List Report, click the Show/Hide Parameters button in the upper left-hand portion of the report window.</span></span>

<span data-ttu-id="7582d-139">請注意，回應群組通話清單不會顯示資訊的回應碼或診斷識別碼是否您將滑鼠停留在這些計量之一。</span><span class="sxs-lookup"><span data-stu-id="7582d-139">Note that the Response Group Call List does not display information about either the Response code or the Diagnostic ID if you hold the mouse over either of those metrics.</span></span> <span data-ttu-id="7582d-140">如果您需要的詳細資訊，您可能會記下的回應碼及/或診斷識別碼，並且然後搜尋[Lync Server 2013 中的最大失敗報告](lync-server-2013-top-failures-report.md)中的這些值。</span><span class="sxs-lookup"><span data-stu-id="7582d-140">If you need more information, you might note the Response code and/or Diagnostic ID, and then search for those values in the [Top Failures Report in Lync Server 2013](lync-server-2013-top-failures-report.md).</span></span>

<span data-ttu-id="7582d-141">像這樣的問題: 「 哪一個個別的工作流程接收最多通話？ 」，您可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="7582d-141">a question like this one: "Which individual workflow received the most calls?", you can do the following:</span></span>

1.  <span data-ttu-id="7582d-142">在回應群組使用量報告中，設定所需的時間期間，然後按一下已接收通話計量。</span><span class="sxs-lookup"><span data-stu-id="7582d-142">On the Response Group Usage Report, set the desired time period and then click the Received Calls metric.</span></span> <span data-ttu-id="7582d-143">如此會開啟回應群組通話清單報告。</span><span class="sxs-lookup"><span data-stu-id="7582d-143">That will open the Response Group Call List Report.</span></span>

2.  <span data-ttu-id="7582d-144">匯出的回應群組通話清單報告上顯示的資料。</span><span class="sxs-lookup"><span data-stu-id="7582d-144">Export the data shown on the Response Group Call List Report.</span></span> <span data-ttu-id="7582d-145">例如，您可能會匯出 Microsoft Excel 格式的資料，並再將該資料轉換成逗點分隔值檔案使用 Excel。</span><span class="sxs-lookup"><span data-stu-id="7582d-145">For example, you might export the data in Microsoft Excel format, and then use Excel to convert that data to a comma-separated values file.</span></span>

3.  <span data-ttu-id="7582d-146">執行分析使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="7582d-146">Run your analyses using Windows PowerShell.</span></span>

<span data-ttu-id="7582d-147">例如，如果您將資料儲存至檔案，名為 c:\\資料\\回應\_群組\_呼叫\_清單\_Report.csv，您可以再使用下列命令來傳回每個工作流程報告中所列的已接收通話總數：</span><span class="sxs-lookup"><span data-stu-id="7582d-147">For example, if you have saved the data to a file named C:\\Data\\Response\_Group\_Call\_List\_Report.csv, you can then use the following command to return the total number of received calls for each workflow listed in the report:</span></span>

    $calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
    $calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending

<span data-ttu-id="7582d-148">會將類似的資訊：</span><span class="sxs-lookup"><span data-stu-id="7582d-148">That will information similar to this:</span></span>

    Count    Name
    -----    ----
      160    Redmond Help Desk
       47    Dublin Help Desk
       31    North America Customer Support
       16    EMEA Customer Support
       14    Employment Opportunities

</div>

<div>

## <a name="filters"></a><span data-ttu-id="7582d-149">篩選</span><span class="sxs-lookup"><span data-stu-id="7582d-149">Filters</span></span>

<span data-ttu-id="7582d-150">篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="7582d-150">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="7582d-151">下表列出您可以使用回應群組通話清單報告的篩選器。</span><span class="sxs-lookup"><span data-stu-id="7582d-151">The following table lists the filters that you can use with the Response Group Call List Report.</span></span>

### <a name="response-group-call-list-report-filters"></a><span data-ttu-id="7582d-152">回應群組通話清單報告篩選器</span><span class="sxs-lookup"><span data-stu-id="7582d-152">Response Group Call List Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7582d-153">名稱</span><span class="sxs-lookup"><span data-stu-id="7582d-153">Name</span></span></th>
<th><span data-ttu-id="7582d-154">描述</span><span class="sxs-lookup"><span data-stu-id="7582d-154">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7582d-155"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="7582d-155"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="7582d-p114">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7582d-p114">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="7582d-158">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="7582d-158">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="7582d-p115">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="7582d-p115">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7582d-161">2012/7/7</span><span class="sxs-lookup"><span data-stu-id="7582d-161">7/7/2012</span></span></p>
<p><span data-ttu-id="7582d-162">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="7582d-162">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7582d-163">2012/7/3</span><span class="sxs-lookup"><span data-stu-id="7582d-163">7/3/2012</span></span></p>
<p><span data-ttu-id="7582d-164">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="7582d-164">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7582d-165"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="7582d-165"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="7582d-p116">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7582d-p116">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="7582d-168">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="7582d-168">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="7582d-p117">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="7582d-p117">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7582d-171">2012/7/7</span><span class="sxs-lookup"><span data-stu-id="7582d-171">7/7/2012</span></span></p>
<p><span data-ttu-id="7582d-172">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="7582d-172">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7582d-173">2012/7/3</span><span class="sxs-lookup"><span data-stu-id="7582d-173">7/3/2012</span></span></p>
<p><span data-ttu-id="7582d-174">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="7582d-174">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7582d-175"><strong>工作流程 URI</strong></span><span class="sxs-lookup"><span data-stu-id="7582d-175"><strong>Workflow URI</strong></span></span></p></td>
<td><p><span data-ttu-id="7582d-p118">可讓您將傳回的資料限定在指定的回應群組工作流程。若要使用此篩選，請輸入工作流程 SIP 位址。例如：</span><span class="sxs-lookup"><span data-stu-id="7582d-p118">Enables you to limit the returned data to the specified Response Group workflow. To use this filter, enter the Workflow SIP address. For example:</span></span></p>
<p><span data-ttu-id="7582d-179">sip:helpdesk@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7582d-179">sip:helpdesk@litwareinc.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7582d-180"><strong>通話</strong></span><span class="sxs-lookup"><span data-stu-id="7582d-180"><strong>Calls</strong></span></span></p></td>
<td><p><span data-ttu-id="7582d-181">您可以選取下列其中一個下列通話類型：</span><span class="sxs-lookup"><span data-stu-id="7582d-181">You can select one of the following call types:</span></span></p>
<ul>
<li><p><span data-ttu-id="7582d-182">接收的通話</span><span class="sxs-lookup"><span data-stu-id="7582d-182">Received Calls</span></span></p></li>
<li><p><span data-ttu-id="7582d-183">成功的通話</span><span class="sxs-lookup"><span data-stu-id="7582d-183">Successful Calls</span></span></p></li>
<li><p><span data-ttu-id="7582d-184">提供的通話</span><span class="sxs-lookup"><span data-stu-id="7582d-184">Offered Calls</span></span></p></li>
<li><p><span data-ttu-id="7582d-185">接聽的通話</span><span class="sxs-lookup"><span data-stu-id="7582d-185">Answered Calls</span></span></p></li>
<li><p><span data-ttu-id="7582d-186">轉接的通話</span><span class="sxs-lookup"><span data-stu-id="7582d-186">Transferred Calls</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="7582d-187">計量</span><span class="sxs-lookup"><span data-stu-id="7582d-187">Metrics</span></span>

<span data-ttu-id="7582d-188">下表列出回應群組應用程式所接收的每個呼叫的回應群組通話清單報告內所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="7582d-188">The following table lists the information provided in the Response Group Call List Report for each call received by the Response Group application.</span></span>

### <a name="response-group-call-list-report-metrics"></a><span data-ttu-id="7582d-189">回應群組通話清單報告計量</span><span class="sxs-lookup"><span data-stu-id="7582d-189">Response Group Call List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7582d-190">名稱</span><span class="sxs-lookup"><span data-stu-id="7582d-190">Name</span></span></th>
<th><span data-ttu-id="7582d-191">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="7582d-191">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7582d-192">說明</span><span class="sxs-lookup"><span data-stu-id="7582d-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7582d-193"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="7582d-193"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="7582d-194">否</span><span class="sxs-lookup"><span data-stu-id="7582d-194">No</span></span></p></td>
<td><p><span data-ttu-id="7582d-195">來電者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="7582d-195">SIP address of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7582d-196"><strong>工作流程</strong></span><span class="sxs-lookup"><span data-stu-id="7582d-196"><strong>Workflow</strong></span></span></p></td>
<td><p><span data-ttu-id="7582d-197">否</span><span class="sxs-lookup"><span data-stu-id="7582d-197">No</span></span></p></td>
<td><p><span data-ttu-id="7582d-198">回應群組工作流程的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="7582d-198">SIP address of the Response Group workflow.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7582d-199"><strong>開始時間</strong></span><span class="sxs-lookup"><span data-stu-id="7582d-199"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="7582d-200">否</span><span class="sxs-lookup"><span data-stu-id="7582d-200">No</span></span></p></td>
<td><p><span data-ttu-id="7582d-201">日期和時間通話的開始。</span><span class="sxs-lookup"><span data-stu-id="7582d-201">Date and time that the call started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7582d-202"><strong>結束時間</strong></span><span class="sxs-lookup"><span data-stu-id="7582d-202"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="7582d-203">否</span><span class="sxs-lookup"><span data-stu-id="7582d-203">No</span></span></p></td>
<td><p><span data-ttu-id="7582d-204">日期和時間通話的結束。</span><span class="sxs-lookup"><span data-stu-id="7582d-204">Date and time that the call ended.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7582d-205"><strong>回應碼</strong></span><span class="sxs-lookup"><span data-stu-id="7582d-205"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="7582d-206">否</span><span class="sxs-lookup"><span data-stu-id="7582d-206">No</span></span></p></td>
<td><p><span data-ttu-id="7582d-207">SIP 工作階段失敗時傳送的回應碼。</span><span class="sxs-lookup"><span data-stu-id="7582d-207">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7582d-208"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="7582d-208"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="7582d-209">否</span><span class="sxs-lookup"><span data-stu-id="7582d-209">No</span></span></p></td>
<td><p><span data-ttu-id="7582d-210">唯一識別項 （以毫秒診斷標頭的形式） 附加在 SIP 訊息通常提供在疑難排解錯誤很有用的資訊。</span><span class="sxs-lookup"><span data-stu-id="7582d-210">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

