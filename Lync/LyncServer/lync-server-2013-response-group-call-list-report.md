---
title: Lync Server 2013：回應群組通話清單報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response Group Call List Report
ms:assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615443(v=OCS.15)
ms:contentKeyID: 48184954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf2c45167b5e5c437a3ff755115aa54d34c74a87
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974262"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-call-list-report-in-lync-server-2013"></a><span data-ttu-id="b843a-102">Lync Server 2013 中的 [回應群組通話清單] 報告</span><span class="sxs-lookup"><span data-stu-id="b843a-102">Response Group Call List Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b843a-103">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="b843a-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="b843a-104">回應群組應用程式提供一種方式，讓 Microsoft Lync Server 2013 根據所撥打的號碼，以及在來電者對一系列問題的回應，來應答並傳送電話撥打電話。</span><span class="sxs-lookup"><span data-stu-id="b843a-104">The Response Group application provides a way for Microsoft Lync Server 2013 to answer and route phone calls based on the number that was dialed and, optionally, on the caller's responses to a series of questions.</span></span> <span data-ttu-id="b843a-105">通常，回應群組通話不會傳送給個別人，而是傳送給稱為「代理人」群組的人員小組。</span><span class="sxs-lookup"><span data-stu-id="b843a-105">Typically, Response Group calls are not routed to an individual person but, instead, are routed to a team of people referred to as an agent group.</span></span> <span data-ttu-id="b843a-106">例如，如果某人撥打電話號碼給您的技術支援人員，Lync Server 2013 可以自動將該呼叫路由到第一個可用的技術支援人員代理程式。</span><span class="sxs-lookup"><span data-stu-id="b843a-106">For example, if someone calls the phone number for your help desk, Lync Server 2013 can automatically route that call to the first available help desk agent.</span></span> <span data-ttu-id="b843a-107">或者，如果您遇到硬體問題，Lync Server 可能會提出一系列問題（「按1）。</span><span class="sxs-lookup"><span data-stu-id="b843a-107">Alternatively, Lync Server could ask a series of questions ("Press 1 if you are having hardware problems.</span></span> <span data-ttu-id="b843a-108">如果您遇到軟體問題，請按2。</span><span class="sxs-lookup"><span data-stu-id="b843a-108">Press 2 if you are having software problems.</span></span> <span data-ttu-id="b843a-109">如果您有網路問題，請按3。）然後根據這些問題的答案，將呼叫路由到最合適的技術支援人員。</span><span class="sxs-lookup"><span data-stu-id="b843a-109">Press 3 if you are having network problems.") and then route the call to the most appropriate help desk agent based on the answer to those questions.</span></span>

<span data-ttu-id="b843a-110">[回應群組通話清單] 報告代表在指定的一段時間內，以及針對特定通話類型進行通話的集合。</span><span class="sxs-lookup"><span data-stu-id="b843a-110">The Response Group Call List Report represents a collection of calls made for a specified period of time and for a specified type of call.</span></span> <span data-ttu-id="b843a-111">回應群組使用方式報告（必須先開啟，才能開啟 [回應群組通話清單] 報告）可識別下列通話類型：</span><span class="sxs-lookup"><span data-stu-id="b843a-111">The Response Group Usage Report (which must be opened first before you can open the Response Group Call List Report) recognizes the following call types:</span></span>

  - <span data-ttu-id="b843a-112">**已接收來電**。</span><span class="sxs-lookup"><span data-stu-id="b843a-112">**Received calls**.</span></span> <span data-ttu-id="b843a-113">所有回應群組應用程式實例接收到的呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="b843a-113">Total number of calls received by all instances of the Response Group application.</span></span>

  - <span data-ttu-id="b843a-114">**成功的通話**。</span><span class="sxs-lookup"><span data-stu-id="b843a-114">**Successful calls**.</span></span> <span data-ttu-id="b843a-115">回應群組應用程式所挑選的通話總數目。</span><span class="sxs-lookup"><span data-stu-id="b843a-115">Total number of calls that were picked up by the Response Group application.</span></span>

  - <span data-ttu-id="b843a-116">已**提供來電**。</span><span class="sxs-lookup"><span data-stu-id="b843a-116">**Offered calls**.</span></span> <span data-ttu-id="b843a-117">傳送給回應群組代理程式的呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="b843a-117">Total number of calls that were transferred to a Response Group agent.</span></span>

  - <span data-ttu-id="b843a-118">已**接聽通話**。</span><span class="sxs-lookup"><span data-stu-id="b843a-118">**Answered calls**.</span></span> <span data-ttu-id="b843a-119">已由回應群組代理程式實際接聽的通話總數目。</span><span class="sxs-lookup"><span data-stu-id="b843a-119">Total number of calls that were actually answered by a Response Group agent.</span></span>

  - <span data-ttu-id="b843a-120">已放棄通話的百分比。</span><span class="sxs-lookup"><span data-stu-id="b843a-120">Percentage of abandoned calls.</span></span> <span data-ttu-id="b843a-121">回應群組應用程式接收，但沒有由代理程式接聽的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="b843a-121">Percentage of calls that were received by the Response Group application but were never answered by an agent.</span></span> <span data-ttu-id="b843a-122">此值的計算方法是從收到的電話減去接聽的通話，然後根據收到的通話數來除以該值。</span><span class="sxs-lookup"><span data-stu-id="b843a-122">This value is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of Received calls.</span></span> <span data-ttu-id="b843a-123">例如，如果您收到10個通話，且已接聽7個，您會從10減去7，然後離開3個未回復的通話。</span><span class="sxs-lookup"><span data-stu-id="b843a-123">For example, if you received 10 calls and 7 were answered, you would subtract 7 from 10, leaving 3 unanswered calls.</span></span> <span data-ttu-id="b843a-124">這個值將除以10，從而讓您放棄通話百分比30%。</span><span class="sxs-lookup"><span data-stu-id="b843a-124">That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span>

  - <span data-ttu-id="b843a-125">**轉接來電**。</span><span class="sxs-lookup"><span data-stu-id="b843a-125">**Transferred calls**.</span></span> <span data-ttu-id="b843a-126">由於佇列超時或佇列溢出而轉移之回應群組通話的總數。</span><span class="sxs-lookup"><span data-stu-id="b843a-126">Total number of Response Group calls that were transferred because of a queue timeout or queue overflow.</span></span>

<div>

## <a name="accessing-the-response-group-call-list-report"></a><span data-ttu-id="b843a-127">存取回應群組通話清單報告</span><span class="sxs-lookup"><span data-stu-id="b843a-127">Accessing the Response Group Call List Report</span></span>

<span data-ttu-id="b843a-128">只有在[Lync Server 2013 的 [回應群組使用方式] 報告中](lync-server-2013-response-group-usage-report.md)，按一下下列其中一個度量，才能存取 [回應] 群組通話清單報告：</span><span class="sxs-lookup"><span data-stu-id="b843a-128">The Response Group Call List Report can only be accessed by clicking one of the following metrics found on the [Response Group Usage Report in Lync Server 2013](lync-server-2013-response-group-usage-report.md):</span></span>

  - <span data-ttu-id="b843a-129">已接聽通話</span><span class="sxs-lookup"><span data-stu-id="b843a-129">Received calls</span></span>

  - <span data-ttu-id="b843a-130">成功的通話</span><span class="sxs-lookup"><span data-stu-id="b843a-130">Successful calls</span></span>

  - <span data-ttu-id="b843a-131">已提供通話</span><span class="sxs-lookup"><span data-stu-id="b843a-131">Offered calls</span></span>

  - <span data-ttu-id="b843a-132">已接聽通話</span><span class="sxs-lookup"><span data-stu-id="b843a-132">Answered calls</span></span>

  - <span data-ttu-id="b843a-133">已轉移通話</span><span class="sxs-lookup"><span data-stu-id="b843a-133">Transferred calls</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a><span data-ttu-id="b843a-134">充分利用 [回應群組通話清單] 報告</span><span class="sxs-lookup"><span data-stu-id="b843a-134">Making the Best Use of the Response Group Call List Report</span></span>

<span data-ttu-id="b843a-135">[回應群組通話清單] 報告可讓您將顯示的資料限制在涉及特定回應群組工作流程的通話中。</span><span class="sxs-lookup"><span data-stu-id="b843a-135">The Response Group Call List Report allows you to limit the displayed data to calls involving a particular Response Group workflow.</span></span> <span data-ttu-id="b843a-136">若要這樣做，您必須在 [工作流程 URI] 方塊中輸入工作流程 URI （工作流程的 SIP 位址）。</span><span class="sxs-lookup"><span data-stu-id="b843a-136">To do that, you need to enter the workflow URI (the workflow's SIP address) in the Workflow URI box.</span></span> <span data-ttu-id="b843a-137">不過，您必須能夠看到 [工作流程 URI] 方塊，才能執行這項作業。</span><span class="sxs-lookup"><span data-stu-id="b843a-137">Before you can do that, however, you must actually be able to see the Workflow URI box.</span></span> <span data-ttu-id="b843a-138">若要顯示 [回應群組通話清單] 報告的篩選選項，請按一下報表視窗左上角的 [顯示/隱藏參數] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="b843a-138">To display the filtering options for the Response Group Call List Report, click the Show/Hide Parameters button in the upper left-hand portion of the report window.</span></span>

<span data-ttu-id="b843a-139">請注意，如果您將滑鼠放在其中一個指標中，回應群組通話清單不會顯示回應代碼或診斷 ID 的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b843a-139">Note that the Response Group Call List does not display information about either the Response code or the Diagnostic ID if you hold the mouse over either of those metrics.</span></span> <span data-ttu-id="b843a-140">如果您需要更多相關資訊，您可以記下回應代碼和/或診斷 ID，然後在[Lync Server 2013 的 [熱門失敗] 報告](lync-server-2013-top-failures-report.md)中搜尋這些值。</span><span class="sxs-lookup"><span data-stu-id="b843a-140">If you need more information, you might note the Response code and/or Diagnostic ID, and then search for those values in the [Top Failures Report in Lync Server 2013](lync-server-2013-top-failures-report.md).</span></span>

<span data-ttu-id="b843a-141">這個問題就像這樣：「哪個個別工作流程收到了最多通話？」，您可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="b843a-141">a question like this one: "Which individual workflow received the most calls?", you can do the following:</span></span>

1.  <span data-ttu-id="b843a-142">在 [回應群組使用方式] 報告中，設定所需的時間週期，然後按一下 [接收的通話統計]。</span><span class="sxs-lookup"><span data-stu-id="b843a-142">On the Response Group Usage Report, set the desired time period and then click the Received Calls metric.</span></span> <span data-ttu-id="b843a-143">這會開啟 [回應群組通話清單] 報告。</span><span class="sxs-lookup"><span data-stu-id="b843a-143">That will open the Response Group Call List Report.</span></span>

2.  <span data-ttu-id="b843a-144">匯出 [回應群組通話清單] 報告上顯示的資料。</span><span class="sxs-lookup"><span data-stu-id="b843a-144">Export the data shown on the Response Group Call List Report.</span></span> <span data-ttu-id="b843a-145">例如，您可能會將資料匯出為 Microsoft Excel 格式，然後使用 Excel 將這些資料轉換成逗號分隔值檔案。</span><span class="sxs-lookup"><span data-stu-id="b843a-145">For example, you might export the data in Microsoft Excel format, and then use Excel to convert that data to a comma-separated values file.</span></span>

3.  <span data-ttu-id="b843a-146">使用 Windows PowerShell 執行分析。</span><span class="sxs-lookup"><span data-stu-id="b843a-146">Run your analyses using Windows PowerShell.</span></span>

<span data-ttu-id="b843a-147">例如，如果您已將資料儲存到名為\\C：資料\\回應\_群組\_通話\_清單\_的檔案 .csv，您就可以使用下列命令，為報告中列出的每個工作流程傳回已接收的通話總數：</span><span class="sxs-lookup"><span data-stu-id="b843a-147">For example, if you have saved the data to a file named C:\\Data\\Response\_Group\_Call\_List\_Report.csv, you can then use the following command to return the total number of received calls for each workflow listed in the report:</span></span>

    $calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
    $calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending

<span data-ttu-id="b843a-148">這將會像這樣的資訊：</span><span class="sxs-lookup"><span data-stu-id="b843a-148">That will information similar to this:</span></span>

    Count    Name
    -----    ----
      160    Redmond Help Desk
       47    Dublin Help Desk
       31    North America Customer Support
       16    EMEA Customer Support
       14    Employment Opportunities

</div>

<div>

## <a name="filters"></a><span data-ttu-id="b843a-149">濾鏡</span><span class="sxs-lookup"><span data-stu-id="b843a-149">Filters</span></span>

<span data-ttu-id="b843a-150">篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="b843a-150">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="b843a-151">下表列出可與 [回應群組通話清單] 報告搭配使用的篩選。</span><span class="sxs-lookup"><span data-stu-id="b843a-151">The following table lists the filters that you can use with the Response Group Call List Report.</span></span>

### <a name="response-group-call-list-report-filters"></a><span data-ttu-id="b843a-152">回應群組通話清單報表篩選</span><span class="sxs-lookup"><span data-stu-id="b843a-152">Response Group Call List Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b843a-153">名稱</span><span class="sxs-lookup"><span data-stu-id="b843a-153">Name</span></span></th>
<th><span data-ttu-id="b843a-154">描述</span><span class="sxs-lookup"><span data-stu-id="b843a-154">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b843a-155"><strong>從</strong></span><span class="sxs-lookup"><span data-stu-id="b843a-155"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="b843a-156">時間範圍的開始日期/時間。</span><span class="sxs-lookup"><span data-stu-id="b843a-156">Start date/time for the time range.</span></span> <span data-ttu-id="b843a-157">若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b843a-157">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="b843a-158">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="b843a-158">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b843a-159">如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。</span><span class="sxs-lookup"><span data-stu-id="b843a-159">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="b843a-160">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="b843a-160">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b843a-161">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="b843a-161">7/7/2012</span></span></p>
<p><span data-ttu-id="b843a-162">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="b843a-162">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b843a-163">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="b843a-163">7/3/2012</span></span></p>
<p><span data-ttu-id="b843a-164">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="b843a-164">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b843a-165"><strong>自</strong></span><span class="sxs-lookup"><span data-stu-id="b843a-165"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="b843a-166">時間範圍的結束日期/時間。</span><span class="sxs-lookup"><span data-stu-id="b843a-166">End date/time for the time range.</span></span> <span data-ttu-id="b843a-167">若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b843a-167">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="b843a-168">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="b843a-168">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b843a-169">如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。</span><span class="sxs-lookup"><span data-stu-id="b843a-169">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="b843a-170">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="b843a-170">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b843a-171">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="b843a-171">7/7/2012</span></span></p>
<p><span data-ttu-id="b843a-172">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="b843a-172">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b843a-173">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="b843a-173">7/3/2012</span></span></p>
<p><span data-ttu-id="b843a-174">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="b843a-174">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b843a-175"><strong>工作流程 URI</strong></span><span class="sxs-lookup"><span data-stu-id="b843a-175"><strong>Workflow URI</strong></span></span></p></td>
<td><p><span data-ttu-id="b843a-176">可讓您將傳回的資料限制在指定的回應群組工作流程中。</span><span class="sxs-lookup"><span data-stu-id="b843a-176">Enables you to limit the returned data to the specified Response Group workflow.</span></span> <span data-ttu-id="b843a-177">若要使用這個篩選器，請輸入工作流程 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="b843a-177">To use this filter, enter the Workflow SIP address.</span></span> <span data-ttu-id="b843a-178">例如：</span><span class="sxs-lookup"><span data-stu-id="b843a-178">For example:</span></span></p>
<p><span data-ttu-id="b843a-179">sip:helpdesk@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b843a-179">sip:helpdesk@litwareinc.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b843a-180"><strong>撥</strong></span><span class="sxs-lookup"><span data-stu-id="b843a-180"><strong>Calls</strong></span></span></p></td>
<td><p><span data-ttu-id="b843a-181">您可以選取下列其中一種通話類型：</span><span class="sxs-lookup"><span data-stu-id="b843a-181">You can select one of the following call types:</span></span></p>
<ul>
<li><p><span data-ttu-id="b843a-182">已接聽通話</span><span class="sxs-lookup"><span data-stu-id="b843a-182">Received Calls</span></span></p></li>
<li><p><span data-ttu-id="b843a-183">成功的通話</span><span class="sxs-lookup"><span data-stu-id="b843a-183">Successful Calls</span></span></p></li>
<li><p><span data-ttu-id="b843a-184">已提供通話</span><span class="sxs-lookup"><span data-stu-id="b843a-184">Offered Calls</span></span></p></li>
<li><p><span data-ttu-id="b843a-185">已接聽通話</span><span class="sxs-lookup"><span data-stu-id="b843a-185">Answered Calls</span></span></p></li>
<li><p><span data-ttu-id="b843a-186">已轉移通話</span><span class="sxs-lookup"><span data-stu-id="b843a-186">Transferred Calls</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="b843a-187">指標</span><span class="sxs-lookup"><span data-stu-id="b843a-187">Metrics</span></span>

<span data-ttu-id="b843a-188">下表列出回應群組應用程式接收之每個通話的回應群組通話清單報告中所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="b843a-188">The following table lists the information provided in the Response Group Call List Report for each call received by the Response Group application.</span></span>

### <a name="response-group-call-list-report-metrics"></a><span data-ttu-id="b843a-189">回應群組通話清單報告度量單位</span><span class="sxs-lookup"><span data-stu-id="b843a-189">Response Group Call List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b843a-190">名稱</span><span class="sxs-lookup"><span data-stu-id="b843a-190">Name</span></span></th>
<th><span data-ttu-id="b843a-191">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="b843a-191">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b843a-192">描述</span><span class="sxs-lookup"><span data-stu-id="b843a-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b843a-193"><strong>呼叫</strong></span><span class="sxs-lookup"><span data-stu-id="b843a-193"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="b843a-194">否</span><span class="sxs-lookup"><span data-stu-id="b843a-194">No</span></span></p></td>
<td><p><span data-ttu-id="b843a-195">來電者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="b843a-195">SIP address of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b843a-196"><strong>工作流程</strong></span><span class="sxs-lookup"><span data-stu-id="b843a-196"><strong>Workflow</strong></span></span></p></td>
<td><p><span data-ttu-id="b843a-197">否</span><span class="sxs-lookup"><span data-stu-id="b843a-197">No</span></span></p></td>
<td><p><span data-ttu-id="b843a-198">回應群組工作流程的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="b843a-198">SIP address of the Response Group workflow.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b843a-199"><strong>開始時間</strong></span><span class="sxs-lookup"><span data-stu-id="b843a-199"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="b843a-200">否</span><span class="sxs-lookup"><span data-stu-id="b843a-200">No</span></span></p></td>
<td><p><span data-ttu-id="b843a-201">通話開始的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="b843a-201">Date and time that the call started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b843a-202"><strong>結束時間</strong></span><span class="sxs-lookup"><span data-stu-id="b843a-202"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="b843a-203">否</span><span class="sxs-lookup"><span data-stu-id="b843a-203">No</span></span></p></td>
<td><p><span data-ttu-id="b843a-204">通話結束的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="b843a-204">Date and time that the call ended.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b843a-205"><strong>回應代碼</strong></span><span class="sxs-lookup"><span data-stu-id="b843a-205"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="b843a-206">否</span><span class="sxs-lookup"><span data-stu-id="b843a-206">No</span></span></p></td>
<td><p><span data-ttu-id="b843a-207">在會話失敗時傳送 SIP 回應代碼。</span><span class="sxs-lookup"><span data-stu-id="b843a-207">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b843a-208"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="b843a-208"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="b843a-209">否</span><span class="sxs-lookup"><span data-stu-id="b843a-209">No</span></span></p></td>
<td><p><span data-ttu-id="b843a-210">附加至 SIP 訊息的唯一識別碼（ms diagnostics 標頭形式），通常可在疑難排解錯誤中提供有用的資訊。</span><span class="sxs-lookup"><span data-stu-id="b843a-210">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

