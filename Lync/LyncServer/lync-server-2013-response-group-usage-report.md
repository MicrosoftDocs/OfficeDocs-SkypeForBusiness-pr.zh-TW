---
title: Lync Server 2013：回應群組使用方式報告
description: Lync Server 2013：回應群組使用方式報告。
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
ms.openlocfilehash: e541a618e8578debc84630037d530c96f4e39ea3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553059"
---
# <a name="response-group-usage-report-in-lync-server-2013"></a><span data-ttu-id="7e4dd-103">Lync Server 2013 的回應群組使用方式報告</span><span class="sxs-lookup"><span data-stu-id="7e4dd-103">Response Group Usage Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e4dd-104">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="7e4dd-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="7e4dd-105">回應群組應用程式提供一種方式，讓 Microsoft Lync Server 2013 根據撥打的號碼來接聽和路由通話，也可以在來電者對一系列問題的回應中作出通話。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-105">The Response Group application provides a way for Microsoft Lync Server 2013 to answer and route phone calls based on the number that was dialed and, optionally, on the caller's responses to a series of questions.</span></span> <span data-ttu-id="7e4dd-106">系統通常不會將回應群組通話路由傳送給個人，而是將通話路由傳送給稱為代理群組的一組人員。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-106">Typically, Response Group calls are not routed to an individual person but, instead, are routed to a team of people referred to as an agent group.</span></span> <span data-ttu-id="7e4dd-107">例如，如果有人呼叫您的技術支援人員的電話號碼，Lync Server 2013 可自動將該呼叫路由傳送至第一個可用的服務台代理。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-107">For example, if someone calls the phone number for your help desk, Lync Server 2013 can automatically route that call to the first available help desk agent.</span></span> <span data-ttu-id="7e4dd-108">或者，如果您有硬體問題，Lync Server 可能會詢問一系列的問題 ( "請按1。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-108">Alternatively, Lync Server could ask a series of questions ("Press 1 if you are having hardware problems.</span></span> <span data-ttu-id="7e4dd-109">軟體問題請按 2。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-109">Press 2 if you are having software problems.</span></span> <span data-ttu-id="7e4dd-110">如果您有網路問題，請按3。」) ，然後根據這些問題的答案，將通話路由傳送給最適當的服務台代理程式。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-110">Press 3 if you are having network problems.") and then route the call to the most appropriate help desk agent based on the answer to those questions.</span></span>

<span data-ttu-id="7e4dd-111">回應群組使用方式報告會提供您所有回應群組工作流程所接收之通話數的詳細資訊，然後將這些通話細分為更有限的分類，例如，提供的通話、接聽的通話及放棄的通話。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-111">The Response Group Usage Report provides a detailed look at the number of phone calls received by all your Response Group workflows, then breaks those calls down into more finite categories such as Offered calls, Answered calls, and Abandoned calls.</span></span>

<span data-ttu-id="7e4dd-112">使用回應群組使用方式報告的關鍵是了解所報告之通話類型間的差異：</span><span class="sxs-lookup"><span data-stu-id="7e4dd-112">The key to working with the Response Group Usage Report is to understand the difference between the reported call types:</span></span>

  - <span data-ttu-id="7e4dd-p102">**接收的通話**。回應群組應用程式的所有執行個體接收的通話總數。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-p102">**Received calls**. Total number of calls received by all instances of the Response Group application.</span></span>

  - <span data-ttu-id="7e4dd-115">**成功的通話**。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-115">**Successful calls**.</span></span> <span data-ttu-id="7e4dd-116">回應群組應用程式挑選的呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-116">Total number of calls that were picked up by the Response Group application.</span></span>

  - <span data-ttu-id="7e4dd-p104">**提供的通話**。轉接至回應群組代理程式的通話總數。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-p104">**Offered calls**. Total number of calls that were transferred to a Response Group agent.</span></span>

  - <span data-ttu-id="7e4dd-p105">**接聽的通話**。回應群組代理程式實際接聽的通話總數。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-p105">**Answered calls**. Total number of calls that were actually answered by a Response Group agent.</span></span>

  - <span data-ttu-id="7e4dd-p106">**放棄的通話百分比**。回應群組應用程式已接收，但代理從未接聽的通話百分比。這是從接收的通話減掉接聽的通話，再除以接收的通話數，所計算出來的值。例如，如果您接收到 10 次通話，並接聽 7 次，就要從 10 減掉 7，剩下 3 次未接聽的通話。該值再除以 10，則得到的放棄通話百分比為 30%。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-p106">**Percentage of abandoned calls**. Percentage of calls that were received by the Response Group application but were never answered by an agent. This value is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of Received calls. For example, if you received 10 calls and 7 were answered, you would subtract 7 from 10, leaving 3 unanswered calls. That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span>

  - <span data-ttu-id="7e4dd-p107">**轉接的通話**。因為佇列逾時或佇列溢位而轉接的回應群組通話總數。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-p107">**Transferred calls**. Total number of Response Group calls that were transferred because of a queue timeout or queue overflow.</span></span>

<span data-ttu-id="7e4dd-p108">如果您正在查看回應群組使用方法報告且不記得這其中任一個通話類型的定義，只需在適當的通話類型標籤上方按住您的滑鼠。即會出現工具提示，提供該通話類型的簡短說明。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-p108">If you are looking at the Response Group Usage Report and can't remember the definition for any of these call types, simply hold your mouse over the appropriate call type label. A tooltip will appear that offers a brief description of the call type.</span></span>

<span data-ttu-id="7e4dd-p109">回應群組使用方式報告讓您能夠篩選工作流程 URI (與該工作流程相關聯的 SIP 位址)。但是，工作流程 URI 不會實際出現在報告本身上。如果您想要了解像是哪些工作流程接聽了最多通話或者哪些工作流程經歷了最多轉接通話等事項，請按一下適當的衡量標準，以開啟該特定期間的回應群組通話清單報告。該報告不會列出工作流程 URI。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-p109">The Response Group Usage Report allows you to filter on a workflow URI (the SIP address associated with that workflow). However, workflow URIs do not actually appear on the report itself. If you would like to know things such as which workflows are answering the most calls or which workflows are experiencing the most transferred calls, click the appropriate metric to open the Response Group Call List Report for that given time period. That reports does list the workflow URIs.</span></span>

<div>

## <a name="accessing-the-response-group-usage-report"></a><span data-ttu-id="7e4dd-134">存取回應群組使用方式報告</span><span class="sxs-lookup"><span data-stu-id="7e4dd-134">Accessing the Response Group Usage Report</span></span>

<span data-ttu-id="7e4dd-135">您可以從 [監視報告] 首頁存取回應群組使用方式報告。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-135">The Response Group Usage Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="7e4dd-136">您可以按一下下列任一度量，向下流覽 [Lync Server 2013 中的回應群組通話清單報告](lync-server-2013-response-group-call-list-report.md) ：</span><span class="sxs-lookup"><span data-stu-id="7e4dd-136">You can drill down to the [Response Group Call List Report in Lync Server 2013](lync-server-2013-response-group-call-list-report.md) by clicking any of the following metrics:</span></span>

  - <span data-ttu-id="7e4dd-137">接收的通話</span><span class="sxs-lookup"><span data-stu-id="7e4dd-137">Received calls</span></span>

  - <span data-ttu-id="7e4dd-138">成功的通話</span><span class="sxs-lookup"><span data-stu-id="7e4dd-138">Successful calls</span></span>

  - <span data-ttu-id="7e4dd-139">提供的通話</span><span class="sxs-lookup"><span data-stu-id="7e4dd-139">Offered calls</span></span>

  - <span data-ttu-id="7e4dd-140">接聽的通話</span><span class="sxs-lookup"><span data-stu-id="7e4dd-140">Answered calls</span></span>

  - <span data-ttu-id="7e4dd-141">轉接的通話</span><span class="sxs-lookup"><span data-stu-id="7e4dd-141">Transferred calls</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-usage-report"></a><span data-ttu-id="7e4dd-142">回應群組使用方式報告的最佳用法</span><span class="sxs-lookup"><span data-stu-id="7e4dd-142">Making the Best Use of the Response Group Usage Report</span></span>

<span data-ttu-id="7e4dd-143">回應群組使用方式報告有一個更有趣但不是相當明顯的用途：擷取單一回應群組工作流程之使用方式資訊的能力。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-143">One of the more interesting uses of the Response Group Usage Report might not be readily apparent: the ability to retrieve usage information for a single Response Group workflow.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="7e4dd-144">回應群組工作流程基本上是一組指示當使用者撥打特定電話號碼時的 Lync Server 所執行的動作。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-144">A Response Group workflow is basically a set of instructions that determines what Lync Server does when a user dials a particular phone number.</span></span> <span data-ttu-id="7e4dd-145">為該結束，每個工作流程都會與電話號碼有唯一的關聯。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-145">To that end, each workflow is uniquely associated with a phone number.</span></span> <span data-ttu-id="7e4dd-146">當某人呼叫該號碼時，工作流程會決定處理呼叫的方式。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-146">When someone calls that number, the workflow determines how the call will be handled.</span></span> <span data-ttu-id="7e4dd-147">例如，工作流程可能導致呼叫路由傳送至一系列互動語音回應 (IVR) 問題，提示來電者輸入其他資訊 ( "按1以取得硬體支援。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-147">For example, the workflow might cause the call to be routed to a series of interactive voice response (IVR) questions that prompt the caller to enter additional information ("Press 1 for hardware support.</span></span> <span data-ttu-id="7e4dd-148">軟體支援請按 2。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-148">Press 2 for software support.").</span></span> <span data-ttu-id="7e4dd-149">或者，工作流程可能會造成呼叫進入佇列中，來電者保留此呼叫直到代理可接聽來電。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-149">Alternatively, the workflow might cause the call to be placed in a queue , with the caller put on hold until an agent is available to answer the call.</span></span> <span data-ttu-id="7e4dd-150">代理是否可接聽電話的狀態，也是由工作流程指定的：工作流程可用來設定營業時間 (一星期的哪幾天和哪些時段會有代理接聽電話) 與假日 (代理無法接聽電話的日子)。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-150">The availability of agents to answer calls is also dictated by the workflow: workflows are used to configure both business hours (the days of the week and the times of day when agents are available to answer calls) and holidays (days when no agents are available to answer calls).</span></span> <span data-ttu-id="7e4dd-151">任何時候當您撥打屬於回應群組應用程式的電話號碼時，實際上就是呼叫回應群組工作流程。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-151">Any time you dial a phone number that belongs to the Response Group application you are essentially calling a Response Group workflow.</span></span>



</div>

<span data-ttu-id="7e4dd-p112">雖然工作流程 URI 不會出現在回應群組使用方式報告中，但仍能檢視單一工作流程的使用方式統計資料，此種通常非常有用的資訊。例如，假設您最近推出了新的廣告行銷活動，並且很好奇地想要了解是否有人來電詢問該產品。如果您已將回應群組工作流程關聯至廣告促銷活動中指定的電話號碼，即可輕易地進行檢查以查看有多少人撥打該號碼 (如果有的話)。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-p112">Although workflow URIs do not appear in the Response Group Usage Report, it's still possible to view the usage statistics for a single workflow, something that is often extremely useful. For example, suppose you recently unveiled a new ad campaign and are curious to know whether people are calling in to ask about that product. If you have associated a Response Group workflow with the phone number given in the ad campaign, you can easily check to see how many people (if any) are calling that number.</span></span>

<span data-ttu-id="7e4dd-155">您可能也會使用類似的處理方式，來估計您內部服務台或客戶服務部門所處理的通話數。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-155">You might also use a similar approach to gauge the number of calls being handled by your internal help desk or your customer service department.</span></span>

<span data-ttu-id="7e4dd-156">若要檢閱特定工作流程的使用方式統計資料，請在 [工作流程 URI] 方塊中輸入工作流程 URI。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-156">To review usage statistics for a particular workflow, enter the workflow URI in the Workflow URI box.</span></span> <span data-ttu-id="7e4dd-157">當然，如上所述，工作流程 URI (與工作流程相關聯的 SIP 位址) 不會出現在報告上。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-157">Of course, as noted, workflow URIs (the SIP address associated with a workflow) do not appear on the report.</span></span> <span data-ttu-id="7e4dd-158">這表示您需要尋找其他方法來決定工作流程的 URI。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-158">That means you need to find some other way to determine the URI of a workflow.</span></span> <span data-ttu-id="7e4dd-159">使用 Windows PowerShell 和 Lync Server 管理命令介面，一種方式是使用 Windows 和 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-159">One way to do this is to use Windows PowerShell and the Lync Server Management Shell.</span></span> <span data-ttu-id="7e4dd-160">例如，此命令會傳回您所有回應群組工作流程的 URI：</span><span class="sxs-lookup"><span data-stu-id="7e4dd-160">For example, this command returns the URIs for all your Response Group workflows:</span></span>

    Get-CsRgsWorkflow | Select-Object Name, PrimaryUri

<span data-ttu-id="7e4dd-161">該命令將傳回類似下列的資料：</span><span class="sxs-lookup"><span data-stu-id="7e4dd-161">That will return data similar to this:</span></span>

    Name                            PrimaryUri
    ----                            ----------
    Customer Support                sip:support@litwareinc.com
    Help Desk                       sip:helpdesk@litwareinc.com
    New Ad Campaign                 sip:newads@litwareinc.com

<span data-ttu-id="7e4dd-162">此命令會傳回單一工作流程 (名稱為「New Ad Campaign」的工作流程) 的資訊：</span><span class="sxs-lookup"><span data-stu-id="7e4dd-162">This command returns information for a single workflow, the one with the name New Ad Campaign:</span></span>

    Get-CsRgsWorkflow -Name "New Ad Campaign" | Select-Object Name, PrimaryUri

</div>

<div>

## <a name="filters"></a><span data-ttu-id="7e4dd-163">篩選</span><span class="sxs-lookup"><span data-stu-id="7e4dd-163">Filters</span></span>

<span data-ttu-id="7e4dd-p114">篩選可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。 例如，回應群組使用量報告可讓您檢視所有回應群組工作流程的資料，或檢視個別工作流程的資料。您也可以選擇資料的分組方式。在這種情況下，使用量會按照小時、日、星期或月加以分組。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-p114">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Response Group Usage Report enables you to view data for all your Response Group workflows or to view data for an individual workflow. You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="7e4dd-168">下表列出您可以用於回應群組使用量報告的篩選。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-168">The following table lists the filters that you can use with the Response Group Usage Report.</span></span>

### <a name="response-group-usage-report-filters"></a><span data-ttu-id="7e4dd-169">回應群組使用量報告篩選</span><span class="sxs-lookup"><span data-stu-id="7e4dd-169">Response Group Usage Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e4dd-170">名稱</span><span class="sxs-lookup"><span data-stu-id="7e4dd-170">Name</span></span></th>
<th><span data-ttu-id="7e4dd-171">描述</span><span class="sxs-lookup"><span data-stu-id="7e4dd-171">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e4dd-172"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="7e4dd-172"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="7e4dd-p115">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7e4dd-p115">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="7e4dd-175">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="7e4dd-175">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="7e4dd-p116">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="7e4dd-p116">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7e4dd-178">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="7e4dd-178">7/7/2012</span></span></p>
<p><span data-ttu-id="7e4dd-179">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="7e4dd-179">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7e4dd-180">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="7e4dd-180">7/3/2012</span></span></p>
<p><span data-ttu-id="7e4dd-181">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-181">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e4dd-182"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="7e4dd-182"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="7e4dd-p117">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7e4dd-p117">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="7e4dd-185">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="7e4dd-185">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="7e4dd-p118">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="7e4dd-p118">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7e4dd-188">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="7e4dd-188">7/7/2012</span></span></p>
<p><span data-ttu-id="7e4dd-189">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="7e4dd-189">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7e4dd-190">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="7e4dd-190">7/3/2012</span></span></p>
<p><span data-ttu-id="7e4dd-191">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-191">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e4dd-192"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="7e4dd-192"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="7e4dd-p119">時間間隔。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="7e4dd-p119">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7e4dd-195">每小時 (最多可以顯示 25 個小時)</span><span class="sxs-lookup"><span data-stu-id="7e4dd-195">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="7e4dd-196">每日 (最多可以顯示 31 天)</span><span class="sxs-lookup"><span data-stu-id="7e4dd-196">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="7e4dd-197">每週 (最多可以顯示 12 週)</span><span class="sxs-lookup"><span data-stu-id="7e4dd-197">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="7e4dd-198">每月 (最多可以顯示 12 個月)</span><span class="sxs-lookup"><span data-stu-id="7e4dd-198">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="7e4dd-p120">若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。例如，若您選取 [每日] 間隔，並將開始與結束日期分別設為 7/7/2012 及 2/28/2012，將只會顯示 8/7/2012 上午 12:00 至 9/7/2012 上午 12:00 這段期間的資料 (亦即只會顯示 31 天的資料)。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-p120">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e4dd-201"><strong>工作流程 URI</strong></span><span class="sxs-lookup"><span data-stu-id="7e4dd-201"><strong>Workflow URI</strong></span></span></p></td>
<td><p><span data-ttu-id="7e4dd-p121">可讓您將傳回的資料限定在指定的回應群組工作流程。若要使用此篩選，請輸入工作流程 SIP 位址。例如：</span><span class="sxs-lookup"><span data-stu-id="7e4dd-p121">Enables you to limit the returned data to the specified Response Group workflow. To use this filter, enter the Workflow SIP address. For example:</span></span></p>
<p><span data-ttu-id="7e4dd-205">sip:helpdesk@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7e4dd-205">sip:helpdesk@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="7e4dd-206">指標</span><span class="sxs-lookup"><span data-stu-id="7e4dd-206">Metrics</span></span>

<span data-ttu-id="7e4dd-207">下表列出回應群組使用量報告提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-207">The following table lists the information provided in the Response Group Usage Report.</span></span>

### <a name="response-group-usage-report-metrics"></a><span data-ttu-id="7e4dd-208">回應群組使用量報告計量</span><span class="sxs-lookup"><span data-stu-id="7e4dd-208">Response Group Usage Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e4dd-209">姓名</span><span class="sxs-lookup"><span data-stu-id="7e4dd-209">Name</span></span></th>
<th><span data-ttu-id="7e4dd-210">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="7e4dd-210">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7e4dd-211">描述</span><span class="sxs-lookup"><span data-stu-id="7e4dd-211">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e4dd-212"><strong>每小時</strong></span><span class="sxs-lookup"><span data-stu-id="7e4dd-212"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="7e4dd-213"><strong>每日</strong></span><span class="sxs-lookup"><span data-stu-id="7e4dd-213"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="7e4dd-214"><strong>每週</strong></span><span class="sxs-lookup"><span data-stu-id="7e4dd-214"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="7e4dd-215"><strong>每月</strong></span><span class="sxs-lookup"><span data-stu-id="7e4dd-215"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="7e4dd-216">否</span><span class="sxs-lookup"><span data-stu-id="7e4dd-216">No</span></span></p></td>
<td><p><span data-ttu-id="7e4dd-p122">指示所選的時間間隔。在適用的情況下，只要按一下指定的時間間隔，即可檢視該間隔的詳細資訊。例如，若您使用 [每日] 間隔並按一下 7/7/2012，將會顯示該日期之使用者登錄活動的每小時明細。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-p122">Indicates the selected time interval. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e4dd-220"><strong>接收的通話</strong></span><span class="sxs-lookup"><span data-stu-id="7e4dd-220"><strong>Received calls</strong></span></span></p></td>
<td><p><span data-ttu-id="7e4dd-221">否</span><span class="sxs-lookup"><span data-stu-id="7e4dd-221">No</span></span></p></td>
<td><p><span data-ttu-id="7e4dd-p123">回應群組應用程式的所有執行個體接收的通話總數。當您按一下此項目，報告即顯示所選取時段的回應群組通話清單報告。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-p123">Total number of calls received by all instances of the Response Group application. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e4dd-224"><strong>成功的通話</strong></span><span class="sxs-lookup"><span data-stu-id="7e4dd-224"><strong>Successful calls</strong></span></span></p></td>
<td><p><span data-ttu-id="7e4dd-225">否</span><span class="sxs-lookup"><span data-stu-id="7e4dd-225">No</span></span></p></td>
<td><p><span data-ttu-id="7e4dd-p124">回應群組應用程式接聽的通話總數。當您按一下此項目，報告即顯示所選取時段的回應群組通話清單報告。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-p124">Total number of calls that were picked up the Response Group application. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e4dd-228"><strong>提供的通話</strong></span><span class="sxs-lookup"><span data-stu-id="7e4dd-228"><strong>Offered calls</strong></span></span></p></td>
<td><p><span data-ttu-id="7e4dd-229">否</span><span class="sxs-lookup"><span data-stu-id="7e4dd-229">No</span></span></p></td>
<td><p><span data-ttu-id="7e4dd-p125">轉接至回應群組代理程式的通話總數。當您按一下此項目，報告即顯示所選取時段的回應群組通話清單報告。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-p125">Total number of calls that were transferred to a Response Group agent. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e4dd-232"><strong>接聽的通話</strong></span><span class="sxs-lookup"><span data-stu-id="7e4dd-232"><strong>Answered calls</strong></span></span></p></td>
<td><p><span data-ttu-id="7e4dd-233">否</span><span class="sxs-lookup"><span data-stu-id="7e4dd-233">No</span></span></p></td>
<td><p><span data-ttu-id="7e4dd-p126">回應群組代理程式實際接聽的通話總數。當您按一下此項目，報告即顯示所選取時段的回應群組通話清單報告。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-p126">Total number of calls that were actually answered by a Response Group agent. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e4dd-236"><strong>放棄的通話百分比</strong></span><span class="sxs-lookup"><span data-stu-id="7e4dd-236"><strong>Percentage of abandoned calls</strong></span></span></p></td>
<td><p><span data-ttu-id="7e4dd-237">否</span><span class="sxs-lookup"><span data-stu-id="7e4dd-237">No</span></span></p></td>
<td><p><span data-ttu-id="7e4dd-p127">回應群組應用程式已接收，但代理程式從未接聽的通話總數。這是從接收的通話減掉接聽的通話，再除以接收的通話數，所計算出來的值。例如，如果您收到 10 次通話，並接聽 7 次，就要從 10 減掉 7，剩下 3 次未接聽的通話。該值再除以 10，則得到的放棄通話百分比為 30%.</span><span class="sxs-lookup"><span data-stu-id="7e4dd-p127">Total number of calls that were received by the Response Group application but were never answered by an agent. This is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of received calls. For example, if you have 10 received calls and seven were answered, you would subtract seven from 10, leaving three unanswered calls. That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e4dd-242"><strong>代理程式的平均通話分鐘數</strong></span><span class="sxs-lookup"><span data-stu-id="7e4dd-242"><strong>Average call minutes by agent</strong></span></span></p></td>
<td><p><span data-ttu-id="7e4dd-243">否</span><span class="sxs-lookup"><span data-stu-id="7e4dd-243">No</span></span></p></td>
<td><p><span data-ttu-id="7e4dd-244">回應群組代理程式用在單一通話的平均時間量。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-244">Average amount of time a Response Group agent spent on a call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e4dd-245"><strong>轉接的通話</strong></span><span class="sxs-lookup"><span data-stu-id="7e4dd-245"><strong>Transferred calls</strong></span></span></p></td>
<td><p><span data-ttu-id="7e4dd-246">否</span><span class="sxs-lookup"><span data-stu-id="7e4dd-246">No</span></span></p></td>
<td><p><span data-ttu-id="7e4dd-p128">因為佇列逾時或佇列溢位而轉接的回應群組通話總數。當您按一下此項目，報告即顯示所選取時段的回應群組通話清單報告。</span><span class="sxs-lookup"><span data-stu-id="7e4dd-p128">Total number of Response Group calls that were transferred because of a queue timeout or queue overflow. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

