---
title: 商務用 Skype Server 中的失敗散佈報告
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
ms.assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
description: 摘要：瞭解商務用 Skype Server 中的失敗散佈報告。
ms.openlocfilehash: 251cf8e2017312d9e42e0d1aebcfe5d1d9bd3568
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823523"
---
# <a name="failure-distribution-report-in-skype-for-business-server"></a><span data-ttu-id="48e12-103">商務用 Skype Server 中的失敗散佈報告</span><span class="sxs-lookup"><span data-stu-id="48e12-103">Failure Distribution Report in Skype for Business Server</span></span>
 
<span data-ttu-id="48e12-104">**摘要：** 深入瞭解商務用 Skype Server 中的失敗散佈報告。</span><span class="sxs-lookup"><span data-stu-id="48e12-104">**Summary:** Learn about the Failure Distribution Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="48e12-105">失敗散佈報告會在下列類別中為失敗的工作階段進行排名：</span><span class="sxs-lookup"><span data-stu-id="48e12-105">The Failure Distribution Report ranks failed sessions in the following categories:</span></span>
  
- <span data-ttu-id="48e12-106">最常見診斷原因</span><span class="sxs-lookup"><span data-stu-id="48e12-106">Top diagnostic reasons</span></span>
    
- <span data-ttu-id="48e12-107">最常見形式</span><span class="sxs-lookup"><span data-stu-id="48e12-107">Top modalities</span></span>
    
- <span data-ttu-id="48e12-108">最常見集區</span><span class="sxs-lookup"><span data-stu-id="48e12-108">Top pools</span></span>
    
- <span data-ttu-id="48e12-109">最常見來源</span><span class="sxs-lookup"><span data-stu-id="48e12-109">Top sources</span></span>
    
- <span data-ttu-id="48e12-110">最常見元件</span><span class="sxs-lookup"><span data-stu-id="48e12-110">Top components</span></span>
    
- <span data-ttu-id="48e12-111">最常見來源使用者</span><span class="sxs-lookup"><span data-stu-id="48e12-111">Top from users</span></span>
    
- <span data-ttu-id="48e12-112">最常見目標使用者</span><span class="sxs-lookup"><span data-stu-id="48e12-112">Top to users</span></span>
    
- <span data-ttu-id="48e12-113">最常見來源使用者代理程式</span><span class="sxs-lookup"><span data-stu-id="48e12-113">Top from user agents</span></span>
    
<span data-ttu-id="48e12-p101">您可以使用這些類別來判斷確實發生問題的地方，並在某些情況下判斷發生問題的原因。例如，假設您在某一天記錄了 242 個失敗的音訊/視訊工作階段。如果您查看失敗散佈報告，其中可能會顯示有 237 個失敗的工作階段是發生在您的 Dublin 集區中。這讓您在追蹤和診斷這些失敗背後的原因時可以有一個良好的開端。如果您按一下 **[最常見集區]** 類別下方的 Dublin 集區，就只會看見該集區的失敗散佈報告。接著，您可以開始分析為什麼 Dublin 集區會遇到這麼多問題。</span><span class="sxs-lookup"><span data-stu-id="48e12-p101">You can use these categories to determine exactly where a problem is occurring and, in some cases, why the problem is occurring. For example, suppose you recorded 242 failed audio/video sessions during a given day. If you look at the Failure Distribution Report, it might show that 237 of those failed sessions took place in your Dublin pool. That gives you a good place to start when it comes to tracking down and diagnosing the causes behind those failures. If you click on the Dublin pool under the **Top pools** category, you will see a Failure Distribution Report just for that pool. You can then begin analyzing why the Dublin pool was experiencing so many difficulties.</span></span>
  
## <a name="viewing-the-failure-distribution-report"></a><span data-ttu-id="48e12-120">檢視失敗散佈報告</span><span class="sxs-lookup"><span data-stu-id="48e12-120">Viewing the Failure Distribution Report</span></span>

<span data-ttu-id="48e12-121">您可以按一下 **[預期失敗次數]** 或 **[未預期失敗次數]** 計量，從下列任一個報告存取失敗散佈報告：</span><span class="sxs-lookup"><span data-stu-id="48e12-121">You can access the Failure Distribution Report from any of the following reports by clicking either the **Expected failure volume** or the **Unexpected failure volume** metric:</span></span>
  
- [<span data-ttu-id="48e12-122">商務用 Skype Server 中的最大失敗報告</span><span class="sxs-lookup"><span data-stu-id="48e12-122">Top Failures Report in Skype for Business Server</span></span>](top-failures-report.md)
    
- [<span data-ttu-id="48e12-123">商務用 Skype Server 中的會議診斷報告</span><span class="sxs-lookup"><span data-stu-id="48e12-123">Conference Diagnostic Report in Skype for Business Server</span></span>](conference-diagnostic-report.md)
    
- [<span data-ttu-id="48e12-124">在商務用 Skype Server 中 Peer-to-Peer 活動診斷報告</span><span class="sxs-lookup"><span data-stu-id="48e12-124">Peer-to-Peer Activity Diagnostic Report in Skype for Business Server</span></span>](peer-to-peer-activity-diagnostic-report.md)
    
<span data-ttu-id="48e12-125">在 [失敗散佈報告] 中，您可以按一下下列任何度量，以 [在商務用 Skype Server 中查看失敗清單報告](failure-list-report.md)：</span><span class="sxs-lookup"><span data-stu-id="48e12-125">From the Failure Distribution Report, you can click any of the following metrics to view the [Failure List Report in Skype for Business Server](failure-list-report.md):</span></span>
  
- <span data-ttu-id="48e12-126">前幾名診斷原因 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="48e12-126">Top diagnostic reasons (sessions)</span></span>
    
- <span data-ttu-id="48e12-127">最常見形式 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="48e12-127">Top modalities (sessions)</span></span>
    
- <span data-ttu-id="48e12-128">最常見集區 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="48e12-128">Top pools (sessions)</span></span>
    
- <span data-ttu-id="48e12-129">最常見來源 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="48e12-129">Top sources (sessions)</span></span>
    
- <span data-ttu-id="48e12-130">最常見元件 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="48e12-130">Top components (sessions)</span></span>
    
- <span data-ttu-id="48e12-131">最常見來源使用者 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="48e12-131">Top from users (sessions)</span></span>
    
- <span data-ttu-id="48e12-132">最常見目標使用者 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="48e12-132">Top to users (sessions)</span></span>
    
- <span data-ttu-id="48e12-133">最常見來源使用者代理程式 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="48e12-133">Top from user agents (sessions)</span></span>
    
## <a name="using-the-failure-distribution-report"></a><span data-ttu-id="48e12-134">使用失敗散佈報告</span><span class="sxs-lookup"><span data-stu-id="48e12-134">Using the Failure Distribution Report</span></span>

<span data-ttu-id="48e12-p102">根據您的監視器大小和螢幕解析度而定，當您在螢幕上檢視失敗散佈報告時，該報告中顯示的部分資料可能被截斷。這種情況特別會出現在像是使用者代理程式的計量中，因為這類計量含有非常長的標籤。例如，名稱像是 "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" 的使用者代理程式可能只會在螢幕上顯示部分名稱：</span><span class="sxs-lookup"><span data-stu-id="48e12-p102">Depending on your monitor size and screen resolution, it's possible that some of the data shown in the Failure Distribution Report might be truncated when you view it onscreen. This is especially true for metrics such as user agents, which can have very long labels. For example, a user agent with a name like "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" might only partially appear onscreen:</span></span> 
  
<span data-ttu-id="48e12-138">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span><span class="sxs-lookup"><span data-stu-id="48e12-138">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span></span>
  
<span data-ttu-id="48e12-139">幸運地是，您只需在截斷的值上按住滑鼠，就可以看見完整的標籤。</span><span class="sxs-lookup"><span data-stu-id="48e12-139">Fortunately, you can see the entire label simply by holding your mouse over the truncated value.</span></span>
  
<span data-ttu-id="48e12-p103">有一個您可以使用失敗散佈報告來篩選的特別計量是診斷識別碼。如果您在其他報告中看見經過剪裁的相同診斷識別碼，就可以在失敗散佈報告中使用該識別碼來篩選，並取得在失敗工作階段執行期間該識別碼確實出現在何處以及出現的頻率等非常詳盡的內容。</span><span class="sxs-lookup"><span data-stu-id="48e12-p103">One interesting metric that you can filter on by using the Failure Distribution Report is Diagnostic ID. If you see the same Diagnostic ID cropping up in other reports you can filter on that ID in the Failure Distribution Report and get a very detailed look at exactly where, and how often, that ID has been reported during a failed session.</span></span>
  
## <a name="filters"></a><span data-ttu-id="48e12-142">篩選</span><span class="sxs-lookup"><span data-stu-id="48e12-142">Filters</span></span>

<span data-ttu-id="48e12-p104">篩選可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。例如，失敗散佈報告可讓您依活動類型 (對等工作階段或會議工作階段) 之類的項目，或是依每個失敗工作階段隨附的診斷識別碼篩選。</span><span class="sxs-lookup"><span data-stu-id="48e12-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Failed Distribution Report enables you to filter on such things as the activity type (peer-to-peer session or conferencing session) or by the diagnostic ID that accompanied each failed session.</span></span>
  
<span data-ttu-id="48e12-145">下表列出您可以用於失敗散佈報告的篩選。</span><span class="sxs-lookup"><span data-stu-id="48e12-145">The following table lists the filters that you can use with the Failure Distribution Report.</span></span>
  
<span data-ttu-id="48e12-146">**失敗散佈報告篩選**</span><span class="sxs-lookup"><span data-stu-id="48e12-146">**Failure Distribution Report Filters**</span></span>

|<span data-ttu-id="48e12-147">**名稱**</span><span class="sxs-lookup"><span data-stu-id="48e12-147">**Name**</span></span>|<span data-ttu-id="48e12-148">**描述**</span><span class="sxs-lookup"><span data-stu-id="48e12-148">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="48e12-149">**From**</span><span class="sxs-lookup"><span data-stu-id="48e12-149">**From**</span></span> <br/> |<span data-ttu-id="48e12-p105">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="48e12-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span>  <br/> <span data-ttu-id="48e12-152">7/7/2015 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="48e12-152">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="48e12-p106">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="48e12-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="48e12-155">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="48e12-155">7/7/2015</span></span>  <br/> <span data-ttu-id="48e12-156">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="48e12-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="48e12-157">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="48e12-157">7/3/2015</span></span>  <br/> <span data-ttu-id="48e12-158">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="48e12-158">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="48e12-159">**To**</span><span class="sxs-lookup"><span data-stu-id="48e12-159">**To**</span></span> <br/> |<span data-ttu-id="48e12-p107">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="48e12-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span>  <br/> <span data-ttu-id="48e12-162">7/7/2015 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="48e12-162">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="48e12-p108">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="48e12-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="48e12-165">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="48e12-165">7/7/2015</span></span>  <br/> <span data-ttu-id="48e12-166">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="48e12-166">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="48e12-167">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="48e12-167">7/3/2015</span></span>  <br/> <span data-ttu-id="48e12-168">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="48e12-168">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="48e12-169">**集區**</span><span class="sxs-lookup"><span data-stu-id="48e12-169">**Pool**</span></span> <br/> |<span data-ttu-id="48e12-p109">登錄器集區或 Edge Server 的完整網域名稱 (FQDN)。您可以選取個別的集區，或是按一下 [全部] 檢視所有集區的資料。此下拉式清單會自動將資料庫內的資料填入。</span><span class="sxs-lookup"><span data-stu-id="48e12-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click **[All]** to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database. </span></span><br/> |
|<span data-ttu-id="48e12-173">**活動類型**</span><span class="sxs-lookup"><span data-stu-id="48e12-173">**Activity type**</span></span> <br/> | <span data-ttu-id="48e12-p110">篩選的活動類型。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="48e12-p110">Type of activity to filter on. Select one of the following:</span></span> <br/>  <span data-ttu-id="48e12-176">一切</span><span class="sxs-lookup"><span data-stu-id="48e12-176">[All]</span></span> <br/>  <span data-ttu-id="48e12-177">對等</span><span class="sxs-lookup"><span data-stu-id="48e12-177">Peer-to-peer</span></span> <br/>  <span data-ttu-id="48e12-178">會議</span><span class="sxs-lookup"><span data-stu-id="48e12-178">Conference</span></span> <br/> |
|<span data-ttu-id="48e12-179">**工作階段類別**</span><span class="sxs-lookup"><span data-stu-id="48e12-179">**Session category**</span></span> <br/> | <span data-ttu-id="48e12-p111">指出有疑問的活動為成功或失敗。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="48e12-p111">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span> <br/>  <span data-ttu-id="48e12-182">一切</span><span class="sxs-lookup"><span data-stu-id="48e12-182">[All]</span></span> <br/>  <span data-ttu-id="48e12-183">成功</span><span class="sxs-lookup"><span data-stu-id="48e12-183">Success</span></span> <br/>  <span data-ttu-id="48e12-184">預期的失敗</span><span class="sxs-lookup"><span data-stu-id="48e12-184">Expected failure</span></span> <br/>  <span data-ttu-id="48e12-185">未預期的失敗</span><span class="sxs-lookup"><span data-stu-id="48e12-185">Unexpected failure</span></span> <br/>  <span data-ttu-id="48e12-p112">「預期的失敗」是指預期會發生的失敗。 例如，當使用者將其狀態設為「勿打擾」時，即應預期所有撥話給該使用者的通話皆會失敗。「未預期的失敗」是指起因於系統不健全的失敗。 例如，當發話者處於保留狀態時，不應掛斷通話。 當發生此狀況時，會將其標幟為未預期的失敗。</span><span class="sxs-lookup"><span data-stu-id="48e12-p112">An "expected failure" is a failure that is expected to happen. For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail. An "unexpected failure" is a failure that occurs in what would appear to be an otherwise healthy system. For example, a call should not be terminated if the caller is placed on hold. If that occurs, that would be flagged as an unexpected failure.</span></span> <br/> |
|<span data-ttu-id="48e12-191">**診斷識別碼**</span><span class="sxs-lookup"><span data-stu-id="48e12-191">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="48e12-p113">附加在 SIP 訊息中的唯一識別碼 (採用 ms-diagnostics 標頭的格式)，常可以在疑難排解錯誤時提供實用的資訊。診斷標頭為選用 (也可能有 SIP 工作階段不包含這些標頭)。只有發生特定問題的工作階段才會回報診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="48e12-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span>  <br/> |
   
## <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="48e12-194">前幾名診斷原因的計量</span><span class="sxs-lookup"><span data-stu-id="48e12-194">Metrics for Top Diagnostic Reasons</span></span>

<span data-ttu-id="48e12-195">下表依據最常報告的診斷識別碼，列出失敗散佈報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="48e12-195">The following table lists the information provided in the Failure Distribution Report based on the most frequently reported diagnostic ID.</span></span>
  
<span data-ttu-id="48e12-196">**前幾名診斷原因的計量**</span><span class="sxs-lookup"><span data-stu-id="48e12-196">**Metrics for Top Diagnostic Reasons**</span></span>

|<span data-ttu-id="48e12-197">**名稱**</span><span class="sxs-lookup"><span data-stu-id="48e12-197">**Name**</span></span>|<span data-ttu-id="48e12-198">**可以排序這個項目嗎？**</span><span class="sxs-lookup"><span data-stu-id="48e12-198">**Can you sort on this item?**</span></span>|<span data-ttu-id="48e12-199">**描述**</span><span class="sxs-lookup"><span data-stu-id="48e12-199">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="48e12-200">**Rank**</span><span class="sxs-lookup"><span data-stu-id="48e12-200">**Rank**</span></span> <br/> |<span data-ttu-id="48e12-201">否</span><span class="sxs-lookup"><span data-stu-id="48e12-201">No</span></span>  <br/> |<span data-ttu-id="48e12-p114">依據診斷識別碼的失敗工作階段相對排名。診斷識別碼是附加在 SIP 訊息中的唯一識別碼 (採用 ms-diagnostics 標頭的格式)，常可以在疑難排解錯誤時提供實用的資訊。</span><span class="sxs-lookup"><span data-stu-id="48e12-p114">Relative ranking of failed sessions based on diagnostic IDs. The diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="48e12-204">**前幾名診斷原因**</span><span class="sxs-lookup"><span data-stu-id="48e12-204">**Top diagnostic reasons**</span></span> <br/> |<span data-ttu-id="48e12-205">否</span><span class="sxs-lookup"><span data-stu-id="48e12-205">No</span></span>  <br/> |<span data-ttu-id="48e12-206">在工作階段產生的診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="48e12-206">Diagnostic ID generated in a session.</span></span>  <br/> |
|<span data-ttu-id="48e12-207">**工作階段**</span><span class="sxs-lookup"><span data-stu-id="48e12-207">**Sessions**</span></span> <br/> |<span data-ttu-id="48e12-208">否</span><span class="sxs-lookup"><span data-stu-id="48e12-208">No</span></span>  <br/> |<span data-ttu-id="48e12-209">產生所指定之診斷識別碼的失敗工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="48e12-209">Total number of failed sessions where the specified diagnostic ID was generated.</span></span>  <br/> |
   
## <a name="metrics-for-top-modalities"></a><span data-ttu-id="48e12-210">前幾名形式的計量</span><span class="sxs-lookup"><span data-stu-id="48e12-210">Metrics for Top Modalities</span></span>

<span data-ttu-id="48e12-211">下表依據最常發生失敗的工作階段形式，列出失敗散佈報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="48e12-211">The following table lists the information provided in the Failure Distribution Report based on the session modalities that experienced the most failures.</span></span>
  
<span data-ttu-id="48e12-212">**前幾名形式的計量**</span><span class="sxs-lookup"><span data-stu-id="48e12-212">**Metrics for Top Modalities**</span></span>

|<span data-ttu-id="48e12-213">**名稱**</span><span class="sxs-lookup"><span data-stu-id="48e12-213">**Name**</span></span>|<span data-ttu-id="48e12-214">**可以排序這個項目嗎？**</span><span class="sxs-lookup"><span data-stu-id="48e12-214">**Can you sort on this item?**</span></span>|<span data-ttu-id="48e12-215">**描述**</span><span class="sxs-lookup"><span data-stu-id="48e12-215">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="48e12-216">**Rank**</span><span class="sxs-lookup"><span data-stu-id="48e12-216">**Rank**</span></span> <br/> |<span data-ttu-id="48e12-217">否</span><span class="sxs-lookup"><span data-stu-id="48e12-217">No</span></span>  <br/> |<span data-ttu-id="48e12-218">依據工作階段類型 (例如，音訊/視訊會議或對等檔案傳輸工作階段) 的失敗工作階段相對排名。</span><span class="sxs-lookup"><span data-stu-id="48e12-218">Relative ranking based of failed session based on session type (for example, an audio/video conference or a peer-to-peer file transfer session).</span></span>  <br/> |
|<span data-ttu-id="48e12-219">**前幾名形式**</span><span class="sxs-lookup"><span data-stu-id="48e12-219">**Top modalities**</span></span> <br/> |<span data-ttu-id="48e12-220">否</span><span class="sxs-lookup"><span data-stu-id="48e12-220">No</span></span>  <br/> |<span data-ttu-id="48e12-221">工作階段類型。</span><span class="sxs-lookup"><span data-stu-id="48e12-221">Session type.</span></span>  <br/> |
|<span data-ttu-id="48e12-222">**工作階段**</span><span class="sxs-lookup"><span data-stu-id="48e12-222">**Sessions**</span></span> <br/> |<span data-ttu-id="48e12-223">否</span><span class="sxs-lookup"><span data-stu-id="48e12-223">No</span></span>  <br/> |<span data-ttu-id="48e12-224">與指定形式有關的失敗工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="48e12-224">Total number of failed sessions involving the specified modality.</span></span>  <br/> |
   
## <a name="metrics-for-top-pools"></a><span data-ttu-id="48e12-225">前幾名集區的計量</span><span class="sxs-lookup"><span data-stu-id="48e12-225">Metrics for Top Pools</span></span>

<span data-ttu-id="48e12-226">下表依據最常發生失敗的集區，列出失敗散佈報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="48e12-226">The following table lists the information provided in the Failure Distribution Report based on the pools that experienced the most failures.</span></span>
  
<span data-ttu-id="48e12-227">**前幾名集區的計量**</span><span class="sxs-lookup"><span data-stu-id="48e12-227">**Metrics for Top Pools**</span></span>

|<span data-ttu-id="48e12-228">**名稱**</span><span class="sxs-lookup"><span data-stu-id="48e12-228">**Name**</span></span>|<span data-ttu-id="48e12-229">**可以排序這個項目嗎？**</span><span class="sxs-lookup"><span data-stu-id="48e12-229">**Can you sort on this item?**</span></span>|<span data-ttu-id="48e12-230">**描述**</span><span class="sxs-lookup"><span data-stu-id="48e12-230">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="48e12-231">**Rank**</span><span class="sxs-lookup"><span data-stu-id="48e12-231">**Rank**</span></span> <br/> |<span data-ttu-id="48e12-232">否</span><span class="sxs-lookup"><span data-stu-id="48e12-232">No</span></span>  <br/> |<span data-ttu-id="48e12-233">根據執行會話之註冊集區或 Edge Server 之失敗會話的相對排名。</span><span class="sxs-lookup"><span data-stu-id="48e12-233">Relative ranking of failed sessions based on the Registrar pool or Edge Server where the session was conducted.</span></span>  <br/> |
|<span data-ttu-id="48e12-234">**前幾名集區**</span><span class="sxs-lookup"><span data-stu-id="48e12-234">**Top pools**</span></span> <br/> |<span data-ttu-id="48e12-235">否</span><span class="sxs-lookup"><span data-stu-id="48e12-235">No</span></span>  <br/> |<span data-ttu-id="48e12-236">註冊機構集區或 Edge Server 的名稱。</span><span class="sxs-lookup"><span data-stu-id="48e12-236">Name of the Registrar pool or Edge Server.</span></span>  <br/> |
|<span data-ttu-id="48e12-237">**工作階段**</span><span class="sxs-lookup"><span data-stu-id="48e12-237">**Sessions**</span></span> <br/> |<span data-ttu-id="48e12-238">否</span><span class="sxs-lookup"><span data-stu-id="48e12-238">No</span></span>  <br/> |<span data-ttu-id="48e12-239">每個註冊集區或 Edge Server 的失敗會話總數。</span><span class="sxs-lookup"><span data-stu-id="48e12-239">Total number of failed sessions per Registrar pool or Edge Server.</span></span>  <br/> |
   
## <a name="metrics-for-top-sources"></a><span data-ttu-id="48e12-240">前幾名來源的計量</span><span class="sxs-lookup"><span data-stu-id="48e12-240">Metrics for Top Sources</span></span>

<span data-ttu-id="48e12-241">下表依據最常發生失敗的電腦，列出失敗散佈報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="48e12-241">The following table lists the information provided in the Failure Distribution Report based on the computers that experienced the most failures.</span></span>
  
<span data-ttu-id="48e12-242">**前幾名來源的計量**</span><span class="sxs-lookup"><span data-stu-id="48e12-242">**Metrics for Top Sources**</span></span>

|<span data-ttu-id="48e12-243">**名稱**</span><span class="sxs-lookup"><span data-stu-id="48e12-243">**Name**</span></span>|<span data-ttu-id="48e12-244">**可以排序這個項目嗎？**</span><span class="sxs-lookup"><span data-stu-id="48e12-244">**Can you sort on this item?**</span></span>|<span data-ttu-id="48e12-245">**描述**</span><span class="sxs-lookup"><span data-stu-id="48e12-245">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="48e12-246">**Rank**</span><span class="sxs-lookup"><span data-stu-id="48e12-246">**Rank**</span></span> <br/> |<span data-ttu-id="48e12-247">否</span><span class="sxs-lookup"><span data-stu-id="48e12-247">No</span></span>  <br/> |<span data-ttu-id="48e12-248">每部電腦的失敗工作階段相對排名。</span><span class="sxs-lookup"><span data-stu-id="48e12-248">Relative ranking failed sessions per computer.</span></span>  <br/> |
|<span data-ttu-id="48e12-249">**前幾名來源**</span><span class="sxs-lookup"><span data-stu-id="48e12-249">**Top sources**</span></span> <br/> |<span data-ttu-id="48e12-250">否</span><span class="sxs-lookup"><span data-stu-id="48e12-250">No</span></span>  <br/> |<span data-ttu-id="48e12-251">與失敗工作階段相關的電腦名稱。</span><span class="sxs-lookup"><span data-stu-id="48e12-251">Name of the computer involved in the failed session.</span></span>  <br/> |
|<span data-ttu-id="48e12-252">**工作階段**</span><span class="sxs-lookup"><span data-stu-id="48e12-252">**Sessions**</span></span> <br/> |<span data-ttu-id="48e12-253">否</span><span class="sxs-lookup"><span data-stu-id="48e12-253">No</span></span>  <br/> |<span data-ttu-id="48e12-254">每部電腦的失敗工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="48e12-254">Total number of failed sessions per computer.</span></span>  <br/> |
   
## <a name="metrics-for-top-components"></a><span data-ttu-id="48e12-255">前幾名元件的計量</span><span class="sxs-lookup"><span data-stu-id="48e12-255">Metrics for Top Components</span></span>

<span data-ttu-id="48e12-256">下表根據最近失敗的元件，列出失敗散佈報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="48e12-256">The following table lists the information provided in the Failure Distribution Report based on the components that experienced the most failures.</span></span>
  
<span data-ttu-id="48e12-257">**前幾名元件的計量**</span><span class="sxs-lookup"><span data-stu-id="48e12-257">**Metrics for Top Components**</span></span>

|<span data-ttu-id="48e12-258">**名稱**</span><span class="sxs-lookup"><span data-stu-id="48e12-258">**Name**</span></span>|<span data-ttu-id="48e12-259">**可以排序這個項目嗎？**</span><span class="sxs-lookup"><span data-stu-id="48e12-259">**Can you sort on this item?**</span></span>|<span data-ttu-id="48e12-260">**描述**</span><span class="sxs-lookup"><span data-stu-id="48e12-260">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="48e12-261">**Rank**</span><span class="sxs-lookup"><span data-stu-id="48e12-261">**Rank**</span></span> <br/> |<span data-ttu-id="48e12-262">否</span><span class="sxs-lookup"><span data-stu-id="48e12-262">No</span></span>  <br/> |<span data-ttu-id="48e12-263">根據元件 (的失敗會話的相對排名（例如，ExumRouting、GroupChat 或 MediationServer) ）。</span><span class="sxs-lookup"><span data-stu-id="48e12-263">Relative ranking of failed sessions based on component (for example, ExumRouting, GroupChat, or MediationServer).</span></span>  <br/> |
|<span data-ttu-id="48e12-264">**前幾名元件**</span><span class="sxs-lookup"><span data-stu-id="48e12-264">**Top components**</span></span> <br/> |<span data-ttu-id="48e12-265">否</span><span class="sxs-lookup"><span data-stu-id="48e12-265">No</span></span>  <br/> |<span data-ttu-id="48e12-266">與失敗工作階段相關的元件名稱。</span><span class="sxs-lookup"><span data-stu-id="48e12-266">Name of the component involved in the failed session.</span></span>  <br/> |
|<span data-ttu-id="48e12-267">**工作階段**</span><span class="sxs-lookup"><span data-stu-id="48e12-267">**Sessions**</span></span> <br/> |<span data-ttu-id="48e12-268">否</span><span class="sxs-lookup"><span data-stu-id="48e12-268">No</span></span>  <br/> |<span data-ttu-id="48e12-269">每個元件的失敗工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="48e12-269">Total number of failed sessions per component.</span></span>  <br/> |
   
## <a name="metrics-for-top-from-users"></a><span data-ttu-id="48e12-270">前幾名發話使用者的計量</span><span class="sxs-lookup"><span data-stu-id="48e12-270">Metrics for Top From Users</span></span>

<span data-ttu-id="48e12-271">下表依據最常在嘗試呼叫他人時發生失敗的使用者 (即所謂的「發話」使用者)，列出失敗散佈報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="48e12-271">The following table lists the information provided in the Failure Distribution Report based on users who experienced the most failures when they tried to call someone else (known as "From" users).</span></span>
  
<span data-ttu-id="48e12-272">**前幾名發話使用者的計量**</span><span class="sxs-lookup"><span data-stu-id="48e12-272">**Metrics for Top From Users**</span></span>

|<span data-ttu-id="48e12-273">**名稱**</span><span class="sxs-lookup"><span data-stu-id="48e12-273">**Name**</span></span>|<span data-ttu-id="48e12-274">**可以排序這個項目嗎？**</span><span class="sxs-lookup"><span data-stu-id="48e12-274">**Can you sort on this item?**</span></span>|<span data-ttu-id="48e12-275">**描述**</span><span class="sxs-lookup"><span data-stu-id="48e12-275">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="48e12-276">**Rank**</span><span class="sxs-lookup"><span data-stu-id="48e12-276">**Rank**</span></span> <br/> |<span data-ttu-id="48e12-277">否</span><span class="sxs-lookup"><span data-stu-id="48e12-277">No</span></span>  <br/> |<span data-ttu-id="48e12-278">依據受邀參加工作階段之使用者的失敗工作階段相對排名。</span><span class="sxs-lookup"><span data-stu-id="48e12-278">Relative ranking of failed sessions based on the user who was invited to join the session.</span></span>  <br/> |
|<span data-ttu-id="48e12-279">**前幾名發話使用者**</span><span class="sxs-lookup"><span data-stu-id="48e12-279">**Top from users**</span></span> <br/> |<span data-ttu-id="48e12-280">否</span><span class="sxs-lookup"><span data-stu-id="48e12-280">No</span></span>  <br/> |<span data-ttu-id="48e12-281">受邀參加工作階段之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="48e12-281">SIP address of the user invited to join the session.</span></span>  <br/> |
|<span data-ttu-id="48e12-282">**工作階段**</span><span class="sxs-lookup"><span data-stu-id="48e12-282">**Sessions**</span></span> <br/> |<span data-ttu-id="48e12-283">否</span><span class="sxs-lookup"><span data-stu-id="48e12-283">No</span></span>  <br/> |<span data-ttu-id="48e12-284">每位使用者的失敗工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="48e12-284">Total number of failed sessions per user.</span></span>  <br/> |
   
## <a name="metrics-for-top-to-users"></a><span data-ttu-id="48e12-285">前幾名受話使用者的計量</span><span class="sxs-lookup"><span data-stu-id="48e12-285">Metrics for Top To Users</span></span>

<span data-ttu-id="48e12-286">下表依據最常在其他使用者呼叫他們時發生失敗的使用者 (即所謂的「受話」使用者)，列出失敗散佈報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="48e12-286">The following table lists the information provided in the Failure Distribution Report based on the users who experienced the most failures when another user tried to call them (known as "To" users).</span></span>
  
|<span data-ttu-id="48e12-287">**名稱**</span><span class="sxs-lookup"><span data-stu-id="48e12-287">**Name**</span></span>|<span data-ttu-id="48e12-288">**可以排序這個項目嗎？**</span><span class="sxs-lookup"><span data-stu-id="48e12-288">**Can you sort on this item?**</span></span>|<span data-ttu-id="48e12-289">**描述**</span><span class="sxs-lookup"><span data-stu-id="48e12-289">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="48e12-290">**Rank**</span><span class="sxs-lookup"><span data-stu-id="48e12-290">**Rank**</span></span> <br/> |<span data-ttu-id="48e12-291">否</span><span class="sxs-lookup"><span data-stu-id="48e12-291">No</span></span>  <br/> |<span data-ttu-id="48e12-292">依據啟動工作階段之使用者的失敗工作階段相對排名。</span><span class="sxs-lookup"><span data-stu-id="48e12-292">Relative ranking of failed sessions based on the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="48e12-293">**前幾名受話使用者**</span><span class="sxs-lookup"><span data-stu-id="48e12-293">**Top to users**</span></span> <br/> |<span data-ttu-id="48e12-294">否</span><span class="sxs-lookup"><span data-stu-id="48e12-294">No</span></span>  <br/> |<span data-ttu-id="48e12-295">啟動工作階段之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="48e12-295">SIP address of the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="48e12-296">**工作階段**</span><span class="sxs-lookup"><span data-stu-id="48e12-296">**Sessions**</span></span> <br/> |<span data-ttu-id="48e12-297">否</span><span class="sxs-lookup"><span data-stu-id="48e12-297">No</span></span>  <br/> |<span data-ttu-id="48e12-298">每位使用者的失敗工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="48e12-298">Total number of failed sessions per user.</span></span>  <br/> |
   
## <a name="metrics-for-top-user-agents"></a><span data-ttu-id="48e12-299">前幾名使用者代理程式的計量</span><span class="sxs-lookup"><span data-stu-id="48e12-299">Metrics for Top User Agents</span></span>

<span data-ttu-id="48e12-300">下表依據最常發生失敗的端點軟體，列出失敗通訊報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="48e12-300">The following table lists the information provided in the Failure Distribution Report based on the endpoint software that experienced the most failures.</span></span>
  
<span data-ttu-id="48e12-301">**前幾名使用者代理程式的計量**</span><span class="sxs-lookup"><span data-stu-id="48e12-301">**Metrics for Top User Agents**</span></span>

|<span data-ttu-id="48e12-302">**名稱**</span><span class="sxs-lookup"><span data-stu-id="48e12-302">**Name**</span></span>|<span data-ttu-id="48e12-303">**可以排序這個項目嗎？**</span><span class="sxs-lookup"><span data-stu-id="48e12-303">**Can you sort on this item?**</span></span>|<span data-ttu-id="48e12-304">**描述**</span><span class="sxs-lookup"><span data-stu-id="48e12-304">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="48e12-305">**Rank**</span><span class="sxs-lookup"><span data-stu-id="48e12-305">**Rank**</span></span> <br/> |<span data-ttu-id="48e12-306">否</span><span class="sxs-lookup"><span data-stu-id="48e12-306">No</span></span>  <br/> |<span data-ttu-id="48e12-p115">依據與工作階段相關之使用者代理程式 (軟體) 的失敗工作階段相對排名。例如：RTCC/4.0.0.0 輸入路由/4.0.0.0。</span><span class="sxs-lookup"><span data-stu-id="48e12-p115">Relative ranking of failed sessions based on the user agent (software) involved in the session. For example: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</span></span>  <br/> |
|<span data-ttu-id="48e12-309">**前幾名使用者代理程式**</span><span class="sxs-lookup"><span data-stu-id="48e12-309">**Top user agents**</span></span> <br/> |<span data-ttu-id="48e12-310">否</span><span class="sxs-lookup"><span data-stu-id="48e12-310">No</span></span>  <br/> |<span data-ttu-id="48e12-311">與失敗工作階段相關的使用者代理程式名稱。</span><span class="sxs-lookup"><span data-stu-id="48e12-311">Name of the user agent involved in the failed session.</span></span>  <br/> |
|<span data-ttu-id="48e12-312">**工作階段**</span><span class="sxs-lookup"><span data-stu-id="48e12-312">**Sessions**</span></span> <br/> |<span data-ttu-id="48e12-313">否</span><span class="sxs-lookup"><span data-stu-id="48e12-313">No</span></span>  <br/> |<span data-ttu-id="48e12-314">每個使用者代理程式的失敗工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="48e12-314">Total number of failed sessions per user agent.</span></span>  <br/> |
   

