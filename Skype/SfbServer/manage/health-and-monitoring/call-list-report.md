---
title: 商務用 Skype Server 中的回應群組通話清單報告
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
description: 摘要：瞭解商務用 Skype Server 中的回應群組應用程式。
ms.openlocfilehash: 416a0e7b7a7aebaeae84a00c04a7ab5c4e1a5bf8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826493"
---
# <a name="response-group-call-list-report-in-skype-for-business-server"></a><span data-ttu-id="30fd4-103">商務用 Skype Server 中的回應群組通話清單報告</span><span class="sxs-lookup"><span data-stu-id="30fd4-103">Response Group Call List Report in Skype for Business Server</span></span>

<span data-ttu-id="30fd4-104">**摘要：** 深入瞭解商務用 Skype Server 中的回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="30fd4-104">**Summary:** Learn about the Response Group application in Skype for Business Server.</span></span>

<span data-ttu-id="30fd4-105">回應群組應用程式提供一種方式，讓商務用 Skype 伺服器根據撥打的號碼來接聽和路由通話，也可以在來電者對一系列問題的回應中作出通話。</span><span class="sxs-lookup"><span data-stu-id="30fd4-105">The Response Group application provides a way for Skype for Business Server to answer and route phone calls based on the number that was dialed and, optionally, on the caller's responses to a series of questions.</span></span> <span data-ttu-id="30fd4-106">系統通常不會將回應群組通話路由傳送給個人，而是將通話路由傳送給稱為代理群組的一組人員。</span><span class="sxs-lookup"><span data-stu-id="30fd4-106">Typically, Response Group calls are not routed to an individual person but, instead, are routed to a team of people referred to as an agent group.</span></span> <span data-ttu-id="30fd4-107">例如，如果有人撥打協助服務台的電話號碼，商務用 Skype 伺服器就會自動將該呼叫路由傳送至第一個可用的服務台代理程式。</span><span class="sxs-lookup"><span data-stu-id="30fd4-107">For example, if someone calls the phone number for your help desk, Skype for Business Server can automatically route that call to the first available help desk agent.</span></span> <span data-ttu-id="30fd4-108">或者，商務用 Skype 伺服器可能會詢問一系列問題 ( "當您遇到硬體問題時，請按1。</span><span class="sxs-lookup"><span data-stu-id="30fd4-108">Alternatively, Skype for Business Server could ask a series of questions ("Press 1 if you are having hardware problems.</span></span> <span data-ttu-id="30fd4-109">軟體問題請按 2。</span><span class="sxs-lookup"><span data-stu-id="30fd4-109">Press 2 if you are having software problems.</span></span> <span data-ttu-id="30fd4-110">如果您有網路問題，請按3。」) ，然後根據這些問題的答案，將通話路由傳送給最適當的服務台代理程式。</span><span class="sxs-lookup"><span data-stu-id="30fd4-110">Press 3 if you are having network problems.") and then route the call to the most appropriate help desk agent based on the answer to those questions.</span></span>

<span data-ttu-id="30fd4-111">回應群組通話清單報告代表指定的一段時間內和指定的通話類型所撥打的來電集合。</span><span class="sxs-lookup"><span data-stu-id="30fd4-111">The Response Group Call List Report represents a collection of calls made for a specified period of time and for a specified type of call.</span></span> <span data-ttu-id="30fd4-112">[回應群組使用量] 報告 (，必須先開啟此報告，才能開啟回應群組通話清單報告) 識別下列呼叫類型：</span><span class="sxs-lookup"><span data-stu-id="30fd4-112">The Response Group Usage Report (which must be opened first before you can open the Response Group Call List Report) recognizes the following call types:</span></span>

- <span data-ttu-id="30fd4-113">**接收的通話**。</span><span class="sxs-lookup"><span data-stu-id="30fd4-113">**Received calls**.</span></span> <span data-ttu-id="30fd4-114">回應群組應用程式的所有執行個體接收的通話總數。</span><span class="sxs-lookup"><span data-stu-id="30fd4-114">Total number of calls received by all instances of the Response Group application.</span></span>

- <span data-ttu-id="30fd4-115">**成功的通話**。</span><span class="sxs-lookup"><span data-stu-id="30fd4-115">**Successful calls**.</span></span> <span data-ttu-id="30fd4-116">回應群組應用程式挑選的呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="30fd4-116">Total number of calls that were picked up by the Response Group application.</span></span>

- <span data-ttu-id="30fd4-p105">**提供的通話**。轉接至回應群組代理程式的通話總數。</span><span class="sxs-lookup"><span data-stu-id="30fd4-p105">**Offered calls**. Total number of calls that were transferred to a Response Group agent.</span></span>

- <span data-ttu-id="30fd4-p106">**接聽的通話**。回應群組代理程式實際接聽的通話總數。</span><span class="sxs-lookup"><span data-stu-id="30fd4-p106">**Answered calls**. Total number of calls that were actually answered by a Response Group agent.</span></span>

- <span data-ttu-id="30fd4-121">**放棄通話的百分比。**</span><span class="sxs-lookup"><span data-stu-id="30fd4-121">**Percentage of abandoned calls.**</span></span> <span data-ttu-id="30fd4-122">回應群組應用程式已接收，但代理從未接聽的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="30fd4-122">Percentage of calls that were received by the Response Group application but were never answered by an agent.</span></span> <span data-ttu-id="30fd4-123">這是從接收的通話減掉接聽的通話，再除以接收的通話數，所計算出來的值。</span><span class="sxs-lookup"><span data-stu-id="30fd4-123">This value is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of Received calls.</span></span> <span data-ttu-id="30fd4-124">例如，如果您接收到 10 次通話，並接聽 7 次，就要從 10 減掉 7，剩下 3 次未接聽的通話。</span><span class="sxs-lookup"><span data-stu-id="30fd4-124">For example, if you received 10 calls and 7 were answered, you would subtract 7 from 10, leaving 3 unanswered calls.</span></span> <span data-ttu-id="30fd4-125">該值再除以 10，則得到的放棄通話百分比為 30%。</span><span class="sxs-lookup"><span data-stu-id="30fd4-125">That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span>

- <span data-ttu-id="30fd4-126">**轉接的通話**。</span><span class="sxs-lookup"><span data-stu-id="30fd4-126">**Transferred calls**.</span></span> <span data-ttu-id="30fd4-127">因為佇列逾時或佇列溢位而轉接的回應群組通話總數。</span><span class="sxs-lookup"><span data-stu-id="30fd4-127">Total number of Response Group calls that were transferred because of a queue timeout or queue overflow.</span></span>

## <a name="accessing-the-response-group-call-list-report"></a><span data-ttu-id="30fd4-128">存取回應群組通話清單報告</span><span class="sxs-lookup"><span data-stu-id="30fd4-128">Accessing the Response Group Call List Report</span></span>

<span data-ttu-id="30fd4-129">您只能透過按一下在 [商務用 Skype Server 之 [回應群組使用量] 報告中](response-group-usage-report.md)找到的下列其中一個計量，才能存取回應群組通話清單報告：</span><span class="sxs-lookup"><span data-stu-id="30fd4-129">The Response Group Call List Report can only be accessed by clicking one of the following metrics found on the [Response Group Usage Report in Skype for Business Server](response-group-usage-report.md):</span></span>

- <span data-ttu-id="30fd4-130">接收的通話</span><span class="sxs-lookup"><span data-stu-id="30fd4-130">Received calls</span></span>

- <span data-ttu-id="30fd4-131">成功的通話</span><span class="sxs-lookup"><span data-stu-id="30fd4-131">Successful calls</span></span>

- <span data-ttu-id="30fd4-132">提供的通話</span><span class="sxs-lookup"><span data-stu-id="30fd4-132">Offered calls</span></span>

- <span data-ttu-id="30fd4-133">接聽的通話</span><span class="sxs-lookup"><span data-stu-id="30fd4-133">Answered calls</span></span>

- <span data-ttu-id="30fd4-134">轉接的通話</span><span class="sxs-lookup"><span data-stu-id="30fd4-134">Transferred calls</span></span>

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a><span data-ttu-id="30fd4-135">充分利用回應群組通話清單報告</span><span class="sxs-lookup"><span data-stu-id="30fd4-135">Making the Best Use of the Response Group Call List Report</span></span>

<span data-ttu-id="30fd4-136">回應群組通話清單報告可讓您將顯示的資料限制為涉及特定回應群組工作流程的呼叫。</span><span class="sxs-lookup"><span data-stu-id="30fd4-136">The Response Group Call List Report allows you to limit the displayed data to calls involving a particular Response Group workflow.</span></span> <span data-ttu-id="30fd4-137">若要這麼做，您必須在 [工作流程 URI] 方塊中輸入工作流程 URI (工作流程的 SIP 位址) 。</span><span class="sxs-lookup"><span data-stu-id="30fd4-137">To do that, you need to enter the workflow URI (the workflow's SIP address) in the Workflow URI box.</span></span> <span data-ttu-id="30fd4-138">不過，您必須確實能夠看到工作流程 URI 方塊，才能執行這項作業。</span><span class="sxs-lookup"><span data-stu-id="30fd4-138">Before you can do that, however, you must actually be able to see the Workflow URI box.</span></span> <span data-ttu-id="30fd4-139">若要顯示回應群組通話清單報告的篩選選項，請在報表視窗的左上方，按一下 [顯示/隱藏參數] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="30fd4-139">To display the filtering options for the Response Group Call List Report, click the Show/Hide Parameters button in the upper left-hand portion of the report window.</span></span>

<span data-ttu-id="30fd4-140">請注意，回應群組通話清單不會顯示回應碼或診斷識別碼的資訊（如果您將滑鼠放在其中一個計量中）。</span><span class="sxs-lookup"><span data-stu-id="30fd4-140">Note that the Response Group Call List does not display information about either the Response code or the Diagnostic ID if you hold the mouse over either of those metrics.</span></span> <span data-ttu-id="30fd4-141">如果您需要詳細資訊，請注意回應碼和/或診斷識別碼，然後在 [商務用 Skype Server 的最大失敗報告](top-failures-report.md)中搜尋這些值。</span><span class="sxs-lookup"><span data-stu-id="30fd4-141">If you need more information, you might note the Response code and/or Diagnostic ID, and then search for those values in the [Top Failures Report in Skype for Business Server](top-failures-report.md).</span></span>

<span data-ttu-id="30fd4-142">這類問題：「哪些個別工作流程接收最多通話？」，您可以執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="30fd4-142">a question like this one: "Which individual workflow received the most calls?", you can do the following:</span></span>

1. <span data-ttu-id="30fd4-143">在 [回應群組使用量] 報告上，設定所需的時間週期，然後按一下 [接收的通話計數]。</span><span class="sxs-lookup"><span data-stu-id="30fd4-143">On the Response Group Usage Report, set the desired time period and then click the Received Calls metric.</span></span> <span data-ttu-id="30fd4-144">這會開啟回應群組通話清單報告。</span><span class="sxs-lookup"><span data-stu-id="30fd4-144">That will open the Response Group Call List Report.</span></span>

2. <span data-ttu-id="30fd4-145">匯出回應群組通話清單報告上顯示的資料。</span><span class="sxs-lookup"><span data-stu-id="30fd4-145">Export the data shown on the Response Group Call List Report.</span></span> <span data-ttu-id="30fd4-146">例如，您可以將 Microsoft Excel 格式的資料匯出，然後使用 Excel 將該資料轉換成逗號分隔值檔案。</span><span class="sxs-lookup"><span data-stu-id="30fd4-146">For example, you might export the data in Microsoft Excel format, and then use Excel to convert that data to a comma-separated values file.</span></span>

3. <span data-ttu-id="30fd4-147">使用 Windows PowerShell 執行分析。</span><span class="sxs-lookup"><span data-stu-id="30fd4-147">Run your analyses using Windows PowerShell.</span></span>

<span data-ttu-id="30fd4-148">例如，如果您已將資料儲存到名為 C:\Data\Response_Group_Call_List_Report.csv 的檔案中，您就可以使用下列命令，針對報告中所列的每個工作流程傳回接收的呼叫總數：</span><span class="sxs-lookup"><span data-stu-id="30fd4-148">For example, if you have saved the data to a file named C:\Data\Response_Group_Call_List_Report.csv, you can then use the following command to return the total number of received calls for each workflow listed in the report:</span></span>

```PowerShell
$calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
$calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending
```

<span data-ttu-id="30fd4-149">這會類似如下的資訊：</span><span class="sxs-lookup"><span data-stu-id="30fd4-149">That will information similar to this:</span></span>

<pre>
Count    Name
-----    ----
  160    Redmond Help Desk
   47    Dublin Help Desk
   31    North America Customer Support
   16    EMEA Customer Support
   14    Employment Opportunities
</pre>

## <a name="filters"></a><span data-ttu-id="30fd4-150">篩選</span><span class="sxs-lookup"><span data-stu-id="30fd4-150">Filters</span></span>

<span data-ttu-id="30fd4-151">篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="30fd4-151">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="30fd4-152">下表列出您可以搭配回應群組通話清單報告使用的篩選器。</span><span class="sxs-lookup"><span data-stu-id="30fd4-152">The following table lists the filters that you can use with the Response Group Call List Report.</span></span>

<span data-ttu-id="30fd4-153">**回應群組通話清單報告篩選器**</span><span class="sxs-lookup"><span data-stu-id="30fd4-153">**Response Group Call List Report Filters**</span></span>


| <span data-ttu-id="30fd4-154">**名稱**</span><span class="sxs-lookup"><span data-stu-id="30fd4-154">**Name**</span></span>               | <span data-ttu-id="30fd4-155">**描述**</span><span class="sxs-lookup"><span data-stu-id="30fd4-155">**Description**</span></span>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="30fd4-156">**From**</span><span class="sxs-lookup"><span data-stu-id="30fd4-156">**From**</span></span> <br/>         | <span data-ttu-id="30fd4-p114">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="30fd4-p114">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span>  <br/> <span data-ttu-id="30fd4-159">7/7/2015 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="30fd4-159">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="30fd4-p115">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="30fd4-p115">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="30fd4-162">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="30fd4-162">7/7/2015</span></span>  <br/> <span data-ttu-id="30fd4-163">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="30fd4-163">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="30fd4-164">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="30fd4-164">7/3/2015</span></span>  <br/> <span data-ttu-id="30fd4-165">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="30fd4-165">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
| <span data-ttu-id="30fd4-166">**To**</span><span class="sxs-lookup"><span data-stu-id="30fd4-166">**To**</span></span> <br/>           | <span data-ttu-id="30fd4-p116">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="30fd4-p116">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span>  <br/> <span data-ttu-id="30fd4-169">7/7/2015 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="30fd4-169">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="30fd4-p117">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="30fd4-p117">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="30fd4-172">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="30fd4-172">7/7/2015</span></span>  <br/> <span data-ttu-id="30fd4-173">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="30fd4-173">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="30fd4-174">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="30fd4-174">7/3/2015</span></span>  <br/> <span data-ttu-id="30fd4-175">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="30fd4-175">Weeks always run from Sunday through Saturday.</span></span>  <br/>        |
| <span data-ttu-id="30fd4-176">**工作流程 URI**</span><span class="sxs-lookup"><span data-stu-id="30fd4-176">**Workflow URI**</span></span> <br/> | <span data-ttu-id="30fd4-p118">可讓您將傳回的資料限定在指定的回應群組工作流程。若要使用此篩選，請輸入工作流程 SIP 位址。例如：</span><span class="sxs-lookup"><span data-stu-id="30fd4-p118">Enables you to limit the returned data to the specified Response Group workflow. To use this filter, enter the Workflow SIP address. For example:</span></span>  <br/> <span data-ttu-id="30fd4-180">sip:helpdesk@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="30fd4-180">sip:helpdesk@litwareinc.com</span></span>  <br/>                                                                                                                                                                                                                                                                                                                                                                            |
| <span data-ttu-id="30fd4-181">**調用**</span><span class="sxs-lookup"><span data-stu-id="30fd4-181">**Calls**</span></span> <br/>        | <span data-ttu-id="30fd4-182">您可以選取下列其中一種通話類型：</span><span class="sxs-lookup"><span data-stu-id="30fd4-182">You can select one of the following call types:</span></span> <br/>  <span data-ttu-id="30fd4-183">接收通話</span><span class="sxs-lookup"><span data-stu-id="30fd4-183">Received Calls</span></span> <br/>  <span data-ttu-id="30fd4-184">通話成功</span><span class="sxs-lookup"><span data-stu-id="30fd4-184">Successful Calls</span></span> <br/>  <span data-ttu-id="30fd4-185">提供通話</span><span class="sxs-lookup"><span data-stu-id="30fd4-185">Offered Calls</span></span> <br/>  <span data-ttu-id="30fd4-186">接聽的通話</span><span class="sxs-lookup"><span data-stu-id="30fd4-186">Answered Calls</span></span> <br/>  <span data-ttu-id="30fd4-187">轉接通話</span><span class="sxs-lookup"><span data-stu-id="30fd4-187">Transferred Calls</span></span> <br/>                                                                                                                                                                                                                                                                                                                                                                                                |

## <a name="metrics"></a><span data-ttu-id="30fd4-188">指標</span><span class="sxs-lookup"><span data-stu-id="30fd4-188">Metrics</span></span>

<span data-ttu-id="30fd4-189">下表列出回應群組應用程式每次呼叫的回應群組通話清單報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="30fd4-189">The following table lists the information provided in the Response Group Call List Report for each call received by the Response Group application.</span></span>

<span data-ttu-id="30fd4-190">**回應群組通話清單報告計量**</span><span class="sxs-lookup"><span data-stu-id="30fd4-190">**Response Group Call List Report Metrics**</span></span>

|<span data-ttu-id="30fd4-191">**名稱**</span><span class="sxs-lookup"><span data-stu-id="30fd4-191">**Name**</span></span>|<span data-ttu-id="30fd4-192">**可以排序這個項目嗎？**</span><span class="sxs-lookup"><span data-stu-id="30fd4-192">**Can you sort on this item?**</span></span>|<span data-ttu-id="30fd4-193">**描述**</span><span class="sxs-lookup"><span data-stu-id="30fd4-193">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="30fd4-194">**Caller**</span><span class="sxs-lookup"><span data-stu-id="30fd4-194">**Caller**</span></span> <br/> |<span data-ttu-id="30fd4-195">否</span><span class="sxs-lookup"><span data-stu-id="30fd4-195">No</span></span>  <br/> |<span data-ttu-id="30fd4-196">來電者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="30fd4-196">SIP address of the caller.</span></span>  <br/> |
|<span data-ttu-id="30fd4-197">**工作流程**</span><span class="sxs-lookup"><span data-stu-id="30fd4-197">**Workflow**</span></span> <br/> |<span data-ttu-id="30fd4-198">否</span><span class="sxs-lookup"><span data-stu-id="30fd4-198">No</span></span>  <br/> |<span data-ttu-id="30fd4-199">回應群組工作流程的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="30fd4-199">SIP address of the Response Group workflow.</span></span>  <br/> |
|<span data-ttu-id="30fd4-200">**開始時間**</span><span class="sxs-lookup"><span data-stu-id="30fd4-200">**Start time**</span></span> <br/> |<span data-ttu-id="30fd4-201">否</span><span class="sxs-lookup"><span data-stu-id="30fd4-201">No</span></span>  <br/> |<span data-ttu-id="30fd4-202">通話的開始日期與時間。</span><span class="sxs-lookup"><span data-stu-id="30fd4-202">Date and time that the call started.</span></span>  <br/> |
|<span data-ttu-id="30fd4-203">**結束時間**</span><span class="sxs-lookup"><span data-stu-id="30fd4-203">**End time**</span></span> <br/> |<span data-ttu-id="30fd4-204">否</span><span class="sxs-lookup"><span data-stu-id="30fd4-204">No</span></span>  <br/> |<span data-ttu-id="30fd4-205">通話的結束日期和時間。</span><span class="sxs-lookup"><span data-stu-id="30fd4-205">Date and time that the call ended.</span></span>  <br/> |
|<span data-ttu-id="30fd4-206">**回應碼**</span><span class="sxs-lookup"><span data-stu-id="30fd4-206">**Response code**</span></span> <br/> |<span data-ttu-id="30fd4-207">否</span><span class="sxs-lookup"><span data-stu-id="30fd4-207">No</span></span>  <br/> |<span data-ttu-id="30fd4-208">會話失敗時傳送的 SIP 回應碼。</span><span class="sxs-lookup"><span data-stu-id="30fd4-208">SIP response code sent when the session failed.</span></span>  <br/> |
|<span data-ttu-id="30fd4-209">**診斷識別碼**</span><span class="sxs-lookup"><span data-stu-id="30fd4-209">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="30fd4-210">否</span><span class="sxs-lookup"><span data-stu-id="30fd4-210">No</span></span>  <br/> |<span data-ttu-id="30fd4-211">附加至 SIP 郵件（通常會在疑難排解錯誤中提供有用資訊) ）的表單中的唯一識別碼 (。</span><span class="sxs-lookup"><span data-stu-id="30fd4-211">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |


