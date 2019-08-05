---
title: 商務用 Skype Server 中的失敗發佈報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
description: '摘要: 瞭解商務用 Skype Server 中的失敗發佈報告。'
ms.openlocfilehash: d9e7d2ac0ff10743c69bee665be3878ac9009933
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193741"
---
# <a name="failure-distribution-report-in-skype-for-business-server"></a><span data-ttu-id="8c143-103">商務用 Skype Server 中的失敗發佈報告</span><span class="sxs-lookup"><span data-stu-id="8c143-103">Failure Distribution Report in Skype for Business Server</span></span>
 
<span data-ttu-id="8c143-104">**摘要:** 瞭解商務用 Skype Server 的失敗發佈報告。</span><span class="sxs-lookup"><span data-stu-id="8c143-104">**Summary:** Learn about the Failure Distribution Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="8c143-105">失敗的發佈報告在下列類別中排名失敗的會話:</span><span class="sxs-lookup"><span data-stu-id="8c143-105">The Failure Distribution Report ranks failed sessions in the following categories:</span></span>
  
- <span data-ttu-id="8c143-106">常見的診斷原因</span><span class="sxs-lookup"><span data-stu-id="8c143-106">Top diagnostic reasons</span></span>
    
- <span data-ttu-id="8c143-107">上方形式</span><span class="sxs-lookup"><span data-stu-id="8c143-107">Top modalities</span></span>
    
- <span data-ttu-id="8c143-108">頂層池</span><span class="sxs-lookup"><span data-stu-id="8c143-108">Top pools</span></span>
    
- <span data-ttu-id="8c143-109">熱門來源</span><span class="sxs-lookup"><span data-stu-id="8c143-109">Top sources</span></span>
    
- <span data-ttu-id="8c143-110">上方元件</span><span class="sxs-lookup"><span data-stu-id="8c143-110">Top components</span></span>
    
- <span data-ttu-id="8c143-111">使用者頂端</span><span class="sxs-lookup"><span data-stu-id="8c143-111">Top from users</span></span>
    
- <span data-ttu-id="8c143-112">使用者頂端</span><span class="sxs-lookup"><span data-stu-id="8c143-112">Top to users</span></span>
    
- <span data-ttu-id="8c143-113">從使用者代理程式頂端</span><span class="sxs-lookup"><span data-stu-id="8c143-113">Top from user agents</span></span>
    
<span data-ttu-id="8c143-114">您可以使用這些類別來判斷問題發生的確切位置, 在某些情況下, 也會發生問題的原因。</span><span class="sxs-lookup"><span data-stu-id="8c143-114">You can use these categories to determine exactly where a problem is occurring and, in some cases, why the problem is occurring.</span></span> <span data-ttu-id="8c143-115">例如, 假設您在指定的一天期間記錄了242失敗的音訊/視頻會話。</span><span class="sxs-lookup"><span data-stu-id="8c143-115">For example, suppose you recorded 242 failed audio/video sessions during a given day.</span></span> <span data-ttu-id="8c143-116">如果您看到失敗的發佈報告, 可能會顯示您的都柏林池中發生了這些失敗會話的237。</span><span class="sxs-lookup"><span data-stu-id="8c143-116">If you look at the Failure Distribution Report, it might show that 237 of those failed sessions took place in your Dublin pool.</span></span> <span data-ttu-id="8c143-117">這可讓您在追蹤及診斷這些失敗背後的原因時提供良好的開始位置。</span><span class="sxs-lookup"><span data-stu-id="8c143-117">That gives you a good place to start when it comes to tracking down and diagnosing the causes behind those failures.</span></span> <span data-ttu-id="8c143-118">如果您在 [**頂層池**] 類別底下按一下 [都柏林], 就會看到該群組的 [分發報告] 只出現失敗。</span><span class="sxs-lookup"><span data-stu-id="8c143-118">If you click on the Dublin pool under the **Top pools** category, you will see a Failure Distribution Report just for that pool.</span></span> <span data-ttu-id="8c143-119">然後, 您就可以開始分析都柏林池為什麼會遇到這麼多問題。</span><span class="sxs-lookup"><span data-stu-id="8c143-119">You can then begin analyzing why the Dublin pool was experiencing so many difficulties.</span></span>
  
## <a name="viewing-the-failure-distribution-report"></a><span data-ttu-id="8c143-120">查看失敗發佈報告</span><span class="sxs-lookup"><span data-stu-id="8c143-120">Viewing the Failure Distribution Report</span></span>

<span data-ttu-id="8c143-121">您可以按一下**預期的失敗量**或**意外的失敗體積**指標, 從下列任何報告存取失敗的發佈報告:</span><span class="sxs-lookup"><span data-stu-id="8c143-121">You can access the Failure Distribution Report from any of the following reports by clicking either the **Expected failure volume** or the **Unexpected failure volume** metric:</span></span>
  
- <span data-ttu-id="8c143-122">[商務用 Skype Server 中的 [熱門失敗] 報表](top-failures-report.md)</span><span class="sxs-lookup"><span data-stu-id="8c143-122">[Top Failures Report in Skype for Business Server](top-failures-report.md)</span></span>
    
- [<span data-ttu-id="8c143-123">商務用 Skype Server 中的會議診斷報告</span><span class="sxs-lookup"><span data-stu-id="8c143-123">Conference Diagnostic Report in Skype for Business Server</span></span>](conference-diagnostic-report.md)
    
- [<span data-ttu-id="8c143-124">商務用 Skype Server 中的對等活動診斷報告</span><span class="sxs-lookup"><span data-stu-id="8c143-124">Peer-to-Peer Activity Diagnostic Report in Skype for Business Server</span></span>](peer-to-peer-activity-diagnostic-report.md)
    
<span data-ttu-id="8c143-125">從失敗的發佈報告中, 您可以按一下下列任何一項衡量標準,[在商務用 Skype Server 中查看失敗清單報告](failure-list-report.md):</span><span class="sxs-lookup"><span data-stu-id="8c143-125">From the Failure Distribution Report, you can click any of the following metrics to view the [Failure List Report in Skype for Business Server](failure-list-report.md):</span></span>
  
- <span data-ttu-id="8c143-126">常見的診斷原因 (會話)</span><span class="sxs-lookup"><span data-stu-id="8c143-126">Top diagnostic reasons (sessions)</span></span>
    
- <span data-ttu-id="8c143-127">熱門形式 (會話)</span><span class="sxs-lookup"><span data-stu-id="8c143-127">Top modalities (sessions)</span></span>
    
- <span data-ttu-id="8c143-128">頂層池 (會話)</span><span class="sxs-lookup"><span data-stu-id="8c143-128">Top pools (sessions)</span></span>
    
- <span data-ttu-id="8c143-129">熱門來源 (會話)</span><span class="sxs-lookup"><span data-stu-id="8c143-129">Top sources (sessions)</span></span>
    
- <span data-ttu-id="8c143-130">Top 元件 (會話)</span><span class="sxs-lookup"><span data-stu-id="8c143-130">Top components (sessions)</span></span>
    
- <span data-ttu-id="8c143-131">使用者的最上層 (會話)</span><span class="sxs-lookup"><span data-stu-id="8c143-131">Top from users (sessions)</span></span>
    
- <span data-ttu-id="8c143-132">使用者的最上層 (會話)</span><span class="sxs-lookup"><span data-stu-id="8c143-132">Top to users (sessions)</span></span>
    
- <span data-ttu-id="8c143-133">使用者代理程式 (會話) 的頂端</span><span class="sxs-lookup"><span data-stu-id="8c143-133">Top from user agents (sessions)</span></span>
    
## <a name="using-the-failure-distribution-report"></a><span data-ttu-id="8c143-134">使用失敗發佈報告</span><span class="sxs-lookup"><span data-stu-id="8c143-134">Using the Failure Distribution Report</span></span>

<span data-ttu-id="8c143-135">視您的監視器大小和螢幕解析度而定, 當您在螢幕上查看失敗的發佈報告時, 可能會有一些顯示的資料會被截斷。</span><span class="sxs-lookup"><span data-stu-id="8c143-135">Depending on your monitor size and screen resolution, it's possible that some of the data shown in the Failure Distribution Report might be truncated when you view it onscreen.</span></span> <span data-ttu-id="8c143-136">特別是對於使用者代理程式 (例如使用者代理程式) 而言, 可能會有非常長的標籤。</span><span class="sxs-lookup"><span data-stu-id="8c143-136">This is especially true for metrics such as user agents, which can have very long labels.</span></span> <span data-ttu-id="8c143-137">例如, 名為「UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)」的使用者代理程式可能只會部分出現在螢幕上:</span><span class="sxs-lookup"><span data-stu-id="8c143-137">For example, a user agent with a name like "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" might only partially appear onscreen:</span></span> 
  
<span data-ttu-id="8c143-138">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly .。。</span><span class="sxs-lookup"><span data-stu-id="8c143-138">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span></span>
  
<span data-ttu-id="8c143-139">幸運的是, 您只需將滑鼠放在截斷的值上, 就能看到整張標籤。</span><span class="sxs-lookup"><span data-stu-id="8c143-139">Fortunately, you can see the entire label simply by holding your mouse over the truncated value.</span></span>
  
<span data-ttu-id="8c143-140">您可以使用「失敗發佈」報告篩選的一個有趣的度量單位是 [診斷 ID]。</span><span class="sxs-lookup"><span data-stu-id="8c143-140">One interesting metric that you can filter on by using the Failure Distribution Report is Diagnostic ID.</span></span> <span data-ttu-id="8c143-141">如果您在其他報告中看到相同的診斷識別碼, 您可以在失敗的發佈報告中篩選該識別碼, 並在失敗的會話期間, 獲得非常詳細的資訊, 以及該識別碼已報告的頻率。</span><span class="sxs-lookup"><span data-stu-id="8c143-141">If you see the same Diagnostic ID cropping up in other reports you can filter on that ID in the Failure Distribution Report and get a very detailed look at exactly where, and how often, that ID has been reported during a failed session.</span></span>
  
## <a name="filters"></a><span data-ttu-id="8c143-142">濾鏡</span><span class="sxs-lookup"><span data-stu-id="8c143-142">Filters</span></span>

<span data-ttu-id="8c143-143">篩選提供一種方式, 可讓您傳回更精細設定目標的資料集, 或以不同方式查看傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="8c143-143">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="8c143-144">例如, 失敗的發佈報告可讓您篩選諸如活動類型 (點對點工作階段或會議會話) 或隨附每個失敗會話的診斷 ID 等專案。</span><span class="sxs-lookup"><span data-stu-id="8c143-144">For example, the Failed Distribution Report enables you to filter on such things as the activity type (peer-to-peer session or conferencing session) or by the diagnostic ID that accompanied each failed session.</span></span>
  
<span data-ttu-id="8c143-145">下表列出您可與失敗發佈報告搭配使用的篩選。</span><span class="sxs-lookup"><span data-stu-id="8c143-145">The following table lists the filters that you can use with the Failure Distribution Report.</span></span>
  
<span data-ttu-id="8c143-146">**失敗的發佈報表篩選**</span><span class="sxs-lookup"><span data-stu-id="8c143-146">**Failure Distribution Report Filters**</span></span>

|<span data-ttu-id="8c143-147">**名稱**</span><span class="sxs-lookup"><span data-stu-id="8c143-147">**Name**</span></span>|<span data-ttu-id="8c143-148">**說明**</span><span class="sxs-lookup"><span data-stu-id="8c143-148">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8c143-149">**從**</span><span class="sxs-lookup"><span data-stu-id="8c143-149">**From**</span></span> <br/> |<span data-ttu-id="8c143-150">時間範圍的開始日期/時間。</span><span class="sxs-lookup"><span data-stu-id="8c143-150">Start date/time for the time range.</span></span> <span data-ttu-id="8c143-151">若要依時間查看資料, 請輸入 [開始日期] 和 [時間], 如下所示:</span><span class="sxs-lookup"><span data-stu-id="8c143-151">To view data by hours, enter both the start date and time as follows:</span></span>  <br/> <span data-ttu-id="8c143-152">7/7/2015 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="8c143-152">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="8c143-153">如果您沒有輸入開始時間, 報告會在指定日期自動于12:00 點開始。</span><span class="sxs-lookup"><span data-stu-id="8c143-153">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="8c143-154">若要依天查看資料, 只需輸入日期:</span><span class="sxs-lookup"><span data-stu-id="8c143-154">To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="8c143-155">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="8c143-155">7/7/2015</span></span>  <br/> <span data-ttu-id="8c143-156">若要依周或依月查看, 請在您要查看的周或月份中, 輸入您要查看的日期 (不需要輸入周或月的第一天):</span><span class="sxs-lookup"><span data-stu-id="8c143-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="8c143-157">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="8c143-157">7/3/2015</span></span>  <br/> <span data-ttu-id="8c143-158">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="8c143-158">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="8c143-159">**自**</span><span class="sxs-lookup"><span data-stu-id="8c143-159">**To**</span></span> <br/> |<span data-ttu-id="8c143-160">時間範圍的結束日期/時間。</span><span class="sxs-lookup"><span data-stu-id="8c143-160">End date/time for the time range.</span></span> <span data-ttu-id="8c143-161">若要依時間查看資料, 請輸入 [結束日期] 和 [時間], 如下所示:</span><span class="sxs-lookup"><span data-stu-id="8c143-161">To view data by hours, enter both the end date and time as follows:</span></span>  <br/> <span data-ttu-id="8c143-162">7/7/2015 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="8c143-162">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="8c143-163">如果您沒有輸入結束時間, 報告會在指定日期自動結束于12:00。</span><span class="sxs-lookup"><span data-stu-id="8c143-163">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="8c143-164">若要依天查看資料, 只需輸入日期:</span><span class="sxs-lookup"><span data-stu-id="8c143-164">To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="8c143-165">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="8c143-165">7/7/2015</span></span>  <br/> <span data-ttu-id="8c143-166">若要依周或依月查看, 請在您要查看的周或月份中, 輸入您要查看的日期 (不需要輸入周或月的第一天):</span><span class="sxs-lookup"><span data-stu-id="8c143-166">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="8c143-167">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="8c143-167">7/3/2015</span></span>  <br/> <span data-ttu-id="8c143-168">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="8c143-168">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="8c143-169">**共**</span><span class="sxs-lookup"><span data-stu-id="8c143-169">**Pool**</span></span> <br/> |<span data-ttu-id="8c143-170">註冊機構池或邊緣伺服器的完整功能變數名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="8c143-170">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="8c143-171">您可以選取個別的池中, 或按一下 **[全部]** 來查看所有資源庫的資料。</span><span class="sxs-lookup"><span data-stu-id="8c143-171">You can either select an individual pool or click **[All]** to view data for all the pools.</span></span> <span data-ttu-id="8c143-172">這個下拉式清單會根據資料庫中的記錄, 自動填入給您。</span><span class="sxs-lookup"><span data-stu-id="8c143-172">This drop-down list is automatically populated for you based on the records in the database.</span></span> <br/> |
|<span data-ttu-id="8c143-173">**活動類型**</span><span class="sxs-lookup"><span data-stu-id="8c143-173">**Activity type**</span></span> <br/> | <span data-ttu-id="8c143-174">要篩選的活動類型。</span><span class="sxs-lookup"><span data-stu-id="8c143-174">Type of activity to filter on.</span></span> <span data-ttu-id="8c143-175">選取下列其中一項:</span><span class="sxs-lookup"><span data-stu-id="8c143-175">Select one of the following:</span></span> <br/>  <span data-ttu-id="8c143-176">同時</span><span class="sxs-lookup"><span data-stu-id="8c143-176">[All]</span></span> <br/>  <span data-ttu-id="8c143-177">對等</span><span class="sxs-lookup"><span data-stu-id="8c143-177">Peer-to-peer</span></span> <br/>  <span data-ttu-id="8c143-178">會議</span><span class="sxs-lookup"><span data-stu-id="8c143-178">Conference</span></span> <br/> |
|<span data-ttu-id="8c143-179">**會話類別**</span><span class="sxs-lookup"><span data-stu-id="8c143-179">**Session category**</span></span> <br/> | <span data-ttu-id="8c143-180">指出問題中的活動是否已成功或失敗。</span><span class="sxs-lookup"><span data-stu-id="8c143-180">Indicates whether the activity in question succeeded or failed.</span></span> <span data-ttu-id="8c143-181">選取下列其中一項:</span><span class="sxs-lookup"><span data-stu-id="8c143-181">Select one of the following:</span></span> <br/>  <span data-ttu-id="8c143-182">同時</span><span class="sxs-lookup"><span data-stu-id="8c143-182">[All]</span></span> <br/>  <span data-ttu-id="8c143-183">成功案例</span><span class="sxs-lookup"><span data-stu-id="8c143-183">Success</span></span> <br/>  <span data-ttu-id="8c143-184">預期失敗</span><span class="sxs-lookup"><span data-stu-id="8c143-184">Expected failure</span></span> <br/>  <span data-ttu-id="8c143-185">意外失敗</span><span class="sxs-lookup"><span data-stu-id="8c143-185">Unexpected failure</span></span> <br/>  <span data-ttu-id="8c143-186">「預期失敗」就是預期發生的錯誤。</span><span class="sxs-lookup"><span data-stu-id="8c143-186">An "expected failure" is a failure that is expected to happen.</span></span> <span data-ttu-id="8c143-187">例如, 如果使用者將自己的狀態設為 [請勿打擾], 您預期該使用者的任何呼叫都會失敗。</span><span class="sxs-lookup"><span data-stu-id="8c143-187">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="8c143-188">[意外失敗] 是看起來像是狀況正常的系統會發生的錯誤。</span><span class="sxs-lookup"><span data-stu-id="8c143-188">An "unexpected failure" is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="8c143-189">例如, 如果來電者停留在 [保留] 上, 就不應該終止通話。</span><span class="sxs-lookup"><span data-stu-id="8c143-189">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="8c143-190">如果發生這種情況, 就會將它標記為未預期的失敗。</span><span class="sxs-lookup"><span data-stu-id="8c143-190">If that occurs, that would be flagged as an unexpected failure.</span></span> <br/> |
|<span data-ttu-id="8c143-191">**診斷識別碼**</span><span class="sxs-lookup"><span data-stu-id="8c143-191">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="8c143-192">附加至 SIP 訊息的唯一識別碼 (ms diagnostics 標頭形式), 通常可在疑難排解錯誤中提供有用的資訊。</span><span class="sxs-lookup"><span data-stu-id="8c143-192">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span> <span data-ttu-id="8c143-193">診斷標頭是可選項 (有可能是不包含這些標頭的 SIP 會話), 而且只會針對遇到某種問題的會話報告診斷 Id。</span><span class="sxs-lookup"><span data-stu-id="8c143-193">Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span>  <br/> |
   
## <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="8c143-194">常見診斷原因的度量單位</span><span class="sxs-lookup"><span data-stu-id="8c143-194">Metrics for Top Diagnostic Reasons</span></span>

<span data-ttu-id="8c143-195">下表列出以最常報告的診斷 ID 為基礎的失敗發佈報告所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="8c143-195">The following table lists the information provided in the Failure Distribution Report based on the most frequently reported diagnostic ID.</span></span>
  
<span data-ttu-id="8c143-196">**常見診斷原因的度量單位**</span><span class="sxs-lookup"><span data-stu-id="8c143-196">**Metrics for Top Diagnostic Reasons**</span></span>

|<span data-ttu-id="8c143-197">**名稱**</span><span class="sxs-lookup"><span data-stu-id="8c143-197">**Name**</span></span>|<span data-ttu-id="8c143-198">**您可以針對此專案進行排序嗎？**</span><span class="sxs-lookup"><span data-stu-id="8c143-198">**Can you sort on this item?**</span></span>|<span data-ttu-id="8c143-199">**說明**</span><span class="sxs-lookup"><span data-stu-id="8c143-199">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8c143-200">**排名**</span><span class="sxs-lookup"><span data-stu-id="8c143-200">**Rank**</span></span> <br/> |<span data-ttu-id="8c143-201">不</span><span class="sxs-lookup"><span data-stu-id="8c143-201">No</span></span>  <br/> |<span data-ttu-id="8c143-202">根據診斷識別碼, 失敗會話的相對排名。</span><span class="sxs-lookup"><span data-stu-id="8c143-202">Relative ranking of failed sessions based on diagnostic IDs.</span></span> <span data-ttu-id="8c143-203">診斷識別碼是附加至 SIP 訊息的唯一識別碼 (以 ms 診斷標頭形式), 它通常會在疑難排解錯誤中提供有用的資訊。</span><span class="sxs-lookup"><span data-stu-id="8c143-203">The diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="8c143-204">**常見的診斷原因**</span><span class="sxs-lookup"><span data-stu-id="8c143-204">**Top diagnostic reasons**</span></span> <br/> |<span data-ttu-id="8c143-205">不</span><span class="sxs-lookup"><span data-stu-id="8c143-205">No</span></span>  <br/> |<span data-ttu-id="8c143-206">在會話中產生的診斷 ID。</span><span class="sxs-lookup"><span data-stu-id="8c143-206">Diagnostic ID generated in a session.</span></span>  <br/> |
|<span data-ttu-id="8c143-207">**時段**</span><span class="sxs-lookup"><span data-stu-id="8c143-207">**Sessions**</span></span> <br/> |<span data-ttu-id="8c143-208">不</span><span class="sxs-lookup"><span data-stu-id="8c143-208">No</span></span>  <br/> |<span data-ttu-id="8c143-209">產生指定診斷 ID 的失敗會話總數。</span><span class="sxs-lookup"><span data-stu-id="8c143-209">Total number of failed sessions where the specified diagnostic ID was generated.</span></span>  <br/> |
   
## <a name="metrics-for-top-modalities"></a><span data-ttu-id="8c143-210">Top 形式的度量單位</span><span class="sxs-lookup"><span data-stu-id="8c143-210">Metrics for Top Modalities</span></span>

<span data-ttu-id="8c143-211">下表列出根據遇到最多失敗的會話形式, 在失敗發佈報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="8c143-211">The following table lists the information provided in the Failure Distribution Report based on the session modalities that experienced the most failures.</span></span>
  
<span data-ttu-id="8c143-212">**Top 形式的度量單位**</span><span class="sxs-lookup"><span data-stu-id="8c143-212">**Metrics for Top Modalities**</span></span>

|<span data-ttu-id="8c143-213">**名稱**</span><span class="sxs-lookup"><span data-stu-id="8c143-213">**Name**</span></span>|<span data-ttu-id="8c143-214">**您可以針對此專案進行排序嗎？**</span><span class="sxs-lookup"><span data-stu-id="8c143-214">**Can you sort on this item?**</span></span>|<span data-ttu-id="8c143-215">**說明**</span><span class="sxs-lookup"><span data-stu-id="8c143-215">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8c143-216">**排名**</span><span class="sxs-lookup"><span data-stu-id="8c143-216">**Rank**</span></span> <br/> |<span data-ttu-id="8c143-217">不</span><span class="sxs-lookup"><span data-stu-id="8c143-217">No</span></span>  <br/> |<span data-ttu-id="8c143-218">根據會話類型 (例如音訊/視訊會議或對等檔案傳輸會話), 以失敗的會話為基礎的相對排名。</span><span class="sxs-lookup"><span data-stu-id="8c143-218">Relative ranking based of failed session based on session type (for example, an audio/video conference or a peer-to-peer file transfer session).</span></span>  <br/> |
|<span data-ttu-id="8c143-219">**上方形式**</span><span class="sxs-lookup"><span data-stu-id="8c143-219">**Top modalities**</span></span> <br/> |<span data-ttu-id="8c143-220">不</span><span class="sxs-lookup"><span data-stu-id="8c143-220">No</span></span>  <br/> |<span data-ttu-id="8c143-221">會話類型。</span><span class="sxs-lookup"><span data-stu-id="8c143-221">Session type.</span></span>  <br/> |
|<span data-ttu-id="8c143-222">**時段**</span><span class="sxs-lookup"><span data-stu-id="8c143-222">**Sessions**</span></span> <br/> |<span data-ttu-id="8c143-223">不</span><span class="sxs-lookup"><span data-stu-id="8c143-223">No</span></span>  <br/> |<span data-ttu-id="8c143-224">涉及指定模態的失敗會話總數。</span><span class="sxs-lookup"><span data-stu-id="8c143-224">Total number of failed sessions involving the specified modality.</span></span>  <br/> |
   
## <a name="metrics-for-top-pools"></a><span data-ttu-id="8c143-225">頂層池的度量單位</span><span class="sxs-lookup"><span data-stu-id="8c143-225">Metrics for Top Pools</span></span>

<span data-ttu-id="8c143-226">下表列出根據遇到最多失敗的池, 在失敗發佈報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="8c143-226">The following table lists the information provided in the Failure Distribution Report based on the pools that experienced the most failures.</span></span>
  
<span data-ttu-id="8c143-227">**頂層池的度量單位**</span><span class="sxs-lookup"><span data-stu-id="8c143-227">**Metrics for Top Pools**</span></span>

|<span data-ttu-id="8c143-228">**名稱**</span><span class="sxs-lookup"><span data-stu-id="8c143-228">**Name**</span></span>|<span data-ttu-id="8c143-229">**您可以針對此專案進行排序嗎？**</span><span class="sxs-lookup"><span data-stu-id="8c143-229">**Can you sort on this item?**</span></span>|<span data-ttu-id="8c143-230">**說明**</span><span class="sxs-lookup"><span data-stu-id="8c143-230">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8c143-231">**排名**</span><span class="sxs-lookup"><span data-stu-id="8c143-231">**Rank**</span></span> <br/> |<span data-ttu-id="8c143-232">不</span><span class="sxs-lookup"><span data-stu-id="8c143-232">No</span></span>  <br/> |<span data-ttu-id="8c143-233">根據執行會話的註冊機構池或邊緣伺服器來找出失敗會話的相對等級。</span><span class="sxs-lookup"><span data-stu-id="8c143-233">Relative ranking of failed sessions based on the Registrar pool or Edge Server where the session was conducted.</span></span>  <br/> |
|<span data-ttu-id="8c143-234">**頂層池**</span><span class="sxs-lookup"><span data-stu-id="8c143-234">**Top pools**</span></span> <br/> |<span data-ttu-id="8c143-235">不</span><span class="sxs-lookup"><span data-stu-id="8c143-235">No</span></span>  <br/> |<span data-ttu-id="8c143-236">註冊機構池或邊緣伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="8c143-236">Name of the Registrar pool or Edge Server.</span></span>  <br/> |
|<span data-ttu-id="8c143-237">**時段**</span><span class="sxs-lookup"><span data-stu-id="8c143-237">**Sessions**</span></span> <br/> |<span data-ttu-id="8c143-238">不</span><span class="sxs-lookup"><span data-stu-id="8c143-238">No</span></span>  <br/> |<span data-ttu-id="8c143-239">每個註冊機構池或邊緣伺服器的失敗會話總數。</span><span class="sxs-lookup"><span data-stu-id="8c143-239">Total number of failed sessions per Registrar pool or Edge Server.</span></span>  <br/> |
   
## <a name="metrics-for-top-sources"></a><span data-ttu-id="8c143-240">熱門來源的度量單位</span><span class="sxs-lookup"><span data-stu-id="8c143-240">Metrics for Top Sources</span></span>

<span data-ttu-id="8c143-241">下表列出根據遇到最多失敗的電腦, 在失敗發佈報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="8c143-241">The following table lists the information provided in the Failure Distribution Report based on the computers that experienced the most failures.</span></span>
  
<span data-ttu-id="8c143-242">**熱門來源的度量單位**</span><span class="sxs-lookup"><span data-stu-id="8c143-242">**Metrics for Top Sources**</span></span>

|<span data-ttu-id="8c143-243">**名稱**</span><span class="sxs-lookup"><span data-stu-id="8c143-243">**Name**</span></span>|<span data-ttu-id="8c143-244">**您可以針對此專案進行排序嗎？**</span><span class="sxs-lookup"><span data-stu-id="8c143-244">**Can you sort on this item?**</span></span>|<span data-ttu-id="8c143-245">**說明**</span><span class="sxs-lookup"><span data-stu-id="8c143-245">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8c143-246">**排名**</span><span class="sxs-lookup"><span data-stu-id="8c143-246">**Rank**</span></span> <br/> |<span data-ttu-id="8c143-247">不</span><span class="sxs-lookup"><span data-stu-id="8c143-247">No</span></span>  <br/> |<span data-ttu-id="8c143-248">每個電腦的相對排名失敗的會話。</span><span class="sxs-lookup"><span data-stu-id="8c143-248">Relative ranking failed sessions per computer.</span></span>  <br/> |
|<span data-ttu-id="8c143-249">**熱門來源**</span><span class="sxs-lookup"><span data-stu-id="8c143-249">**Top sources**</span></span> <br/> |<span data-ttu-id="8c143-250">不</span><span class="sxs-lookup"><span data-stu-id="8c143-250">No</span></span>  <br/> |<span data-ttu-id="8c143-251">失敗會話中所涉及的電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="8c143-251">Name of the computer involved in the failed session.</span></span>  <br/> |
|<span data-ttu-id="8c143-252">**時段**</span><span class="sxs-lookup"><span data-stu-id="8c143-252">**Sessions**</span></span> <br/> |<span data-ttu-id="8c143-253">不</span><span class="sxs-lookup"><span data-stu-id="8c143-253">No</span></span>  <br/> |<span data-ttu-id="8c143-254">每個電腦的失敗會話總數。</span><span class="sxs-lookup"><span data-stu-id="8c143-254">Total number of failed sessions per computer.</span></span>  <br/> |
   
## <a name="metrics-for-top-components"></a><span data-ttu-id="8c143-255">Top 元件的度量單位</span><span class="sxs-lookup"><span data-stu-id="8c143-255">Metrics for Top Components</span></span>

<span data-ttu-id="8c143-256">下表列出根據遇到最多失敗之元件的失敗發佈報告所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="8c143-256">The following table lists the information provided in the Failure Distribution Report based on the components that experienced the most failures.</span></span>
  
<span data-ttu-id="8c143-257">**Top 元件的度量單位**</span><span class="sxs-lookup"><span data-stu-id="8c143-257">**Metrics for Top Components**</span></span>

|<span data-ttu-id="8c143-258">**名稱**</span><span class="sxs-lookup"><span data-stu-id="8c143-258">**Name**</span></span>|<span data-ttu-id="8c143-259">**您可以針對此專案進行排序嗎？**</span><span class="sxs-lookup"><span data-stu-id="8c143-259">**Can you sort on this item?**</span></span>|<span data-ttu-id="8c143-260">**說明**</span><span class="sxs-lookup"><span data-stu-id="8c143-260">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8c143-261">**排名**</span><span class="sxs-lookup"><span data-stu-id="8c143-261">**Rank**</span></span> <br/> |<span data-ttu-id="8c143-262">不</span><span class="sxs-lookup"><span data-stu-id="8c143-262">No</span></span>  <br/> |<span data-ttu-id="8c143-263">根據元件 (例如 ExumRouting、GroupChat 或 MediationServer) 進行失敗會話的相對排名。</span><span class="sxs-lookup"><span data-stu-id="8c143-263">Relative ranking of failed sessions based on component (for example, ExumRouting, GroupChat, or MediationServer).</span></span>  <br/> |
|<span data-ttu-id="8c143-264">**上方元件**</span><span class="sxs-lookup"><span data-stu-id="8c143-264">**Top components**</span></span> <br/> |<span data-ttu-id="8c143-265">不</span><span class="sxs-lookup"><span data-stu-id="8c143-265">No</span></span>  <br/> |<span data-ttu-id="8c143-266">失敗會話中所涉及元件的名稱。</span><span class="sxs-lookup"><span data-stu-id="8c143-266">Name of the component involved in the failed session.</span></span>  <br/> |
|<span data-ttu-id="8c143-267">**時段**</span><span class="sxs-lookup"><span data-stu-id="8c143-267">**Sessions**</span></span> <br/> |<span data-ttu-id="8c143-268">不</span><span class="sxs-lookup"><span data-stu-id="8c143-268">No</span></span>  <br/> |<span data-ttu-id="8c143-269">每個元件的失敗會話總數。</span><span class="sxs-lookup"><span data-stu-id="8c143-269">Total number of failed sessions per component.</span></span>  <br/> |
   
## <a name="metrics-for-top-from-users"></a><span data-ttu-id="8c143-270">使用者的最高指標</span><span class="sxs-lookup"><span data-stu-id="8c143-270">Metrics for Top From Users</span></span>

<span data-ttu-id="8c143-271">下表列出失敗發佈報告中提供的資訊, 這些資訊是根據在嘗試呼叫其他人 (稱為「寄件者」使用者) 時遇到最多失敗的使用者。</span><span class="sxs-lookup"><span data-stu-id="8c143-271">The following table lists the information provided in the Failure Distribution Report based on users who experienced the most failures when they tried to call someone else (known as "From" users).</span></span>
  
<span data-ttu-id="8c143-272">**使用者的最高指標**</span><span class="sxs-lookup"><span data-stu-id="8c143-272">**Metrics for Top From Users**</span></span>

|<span data-ttu-id="8c143-273">**名稱**</span><span class="sxs-lookup"><span data-stu-id="8c143-273">**Name**</span></span>|<span data-ttu-id="8c143-274">**您可以針對此專案進行排序嗎？**</span><span class="sxs-lookup"><span data-stu-id="8c143-274">**Can you sort on this item?**</span></span>|<span data-ttu-id="8c143-275">**說明**</span><span class="sxs-lookup"><span data-stu-id="8c143-275">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8c143-276">**排名**</span><span class="sxs-lookup"><span data-stu-id="8c143-276">**Rank**</span></span> <br/> |<span data-ttu-id="8c143-277">不</span><span class="sxs-lookup"><span data-stu-id="8c143-277">No</span></span>  <br/> |<span data-ttu-id="8c143-278">根據受邀加入會話的使用者, 對失敗的會話進行相對等級。</span><span class="sxs-lookup"><span data-stu-id="8c143-278">Relative ranking of failed sessions based on the user who was invited to join the session.</span></span>  <br/> |
|<span data-ttu-id="8c143-279">**使用者頂端**</span><span class="sxs-lookup"><span data-stu-id="8c143-279">**Top from users**</span></span> <br/> |<span data-ttu-id="8c143-280">不</span><span class="sxs-lookup"><span data-stu-id="8c143-280">No</span></span>  <br/> |<span data-ttu-id="8c143-281">受邀加入會話的使用者 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="8c143-281">SIP address of the user invited to join the session.</span></span>  <br/> |
|<span data-ttu-id="8c143-282">**時段**</span><span class="sxs-lookup"><span data-stu-id="8c143-282">**Sessions**</span></span> <br/> |<span data-ttu-id="8c143-283">不</span><span class="sxs-lookup"><span data-stu-id="8c143-283">No</span></span>  <br/> |<span data-ttu-id="8c143-284">每個使用者的失敗會話總數。</span><span class="sxs-lookup"><span data-stu-id="8c143-284">Total number of failed sessions per user.</span></span>  <br/> |
   
## <a name="metrics-for-top-to-users"></a><span data-ttu-id="8c143-285">最上層使用者的度量單位</span><span class="sxs-lookup"><span data-stu-id="8c143-285">Metrics for Top To Users</span></span>

<span data-ttu-id="8c143-286">下表列出失敗發佈報告所提供的資訊, 這些資訊是根據在其他使用者嘗試呼叫它們 (稱為「收件者」使用者) 時遇到最多失敗的使用者所提供。</span><span class="sxs-lookup"><span data-stu-id="8c143-286">The following table lists the information provided in the Failure Distribution Report based on the users who experienced the most failures when another user tried to call them (known as "To" users).</span></span>
  
|<span data-ttu-id="8c143-287">**名稱**</span><span class="sxs-lookup"><span data-stu-id="8c143-287">**Name**</span></span>|<span data-ttu-id="8c143-288">**您可以針對此專案進行排序嗎？**</span><span class="sxs-lookup"><span data-stu-id="8c143-288">**Can you sort on this item?**</span></span>|<span data-ttu-id="8c143-289">**說明**</span><span class="sxs-lookup"><span data-stu-id="8c143-289">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8c143-290">**排名**</span><span class="sxs-lookup"><span data-stu-id="8c143-290">**Rank**</span></span> <br/> |<span data-ttu-id="8c143-291">不</span><span class="sxs-lookup"><span data-stu-id="8c143-291">No</span></span>  <br/> |<span data-ttu-id="8c143-292">根據啟動會話的使用者, 失敗會話的相對等級。</span><span class="sxs-lookup"><span data-stu-id="8c143-292">Relative ranking of failed sessions based on the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="8c143-293">**使用者頂端**</span><span class="sxs-lookup"><span data-stu-id="8c143-293">**Top to users**</span></span> <br/> |<span data-ttu-id="8c143-294">不</span><span class="sxs-lookup"><span data-stu-id="8c143-294">No</span></span>  <br/> |<span data-ttu-id="8c143-295">啟動會話之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="8c143-295">SIP address of the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="8c143-296">**時段**</span><span class="sxs-lookup"><span data-stu-id="8c143-296">**Sessions**</span></span> <br/> |<span data-ttu-id="8c143-297">不</span><span class="sxs-lookup"><span data-stu-id="8c143-297">No</span></span>  <br/> |<span data-ttu-id="8c143-298">每個使用者的失敗會話總數。</span><span class="sxs-lookup"><span data-stu-id="8c143-298">Total number of failed sessions per user.</span></span>  <br/> |
   
## <a name="metrics-for-top-user-agents"></a><span data-ttu-id="8c143-299">主要使用者代理程式的度量單位</span><span class="sxs-lookup"><span data-stu-id="8c143-299">Metrics for Top User Agents</span></span>

<span data-ttu-id="8c143-300">下表列出根據遇到最多失敗的端點軟體, 在失敗發佈報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="8c143-300">The following table lists the information provided in the Failure Distribution Report based on the endpoint software that experienced the most failures.</span></span>
  
<span data-ttu-id="8c143-301">**主要使用者代理程式的度量單位**</span><span class="sxs-lookup"><span data-stu-id="8c143-301">**Metrics for Top User Agents**</span></span>

|<span data-ttu-id="8c143-302">**名稱**</span><span class="sxs-lookup"><span data-stu-id="8c143-302">**Name**</span></span>|<span data-ttu-id="8c143-303">**您可以針對此專案進行排序嗎？**</span><span class="sxs-lookup"><span data-stu-id="8c143-303">**Can you sort on this item?**</span></span>|<span data-ttu-id="8c143-304">**說明**</span><span class="sxs-lookup"><span data-stu-id="8c143-304">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8c143-305">**排名**</span><span class="sxs-lookup"><span data-stu-id="8c143-305">**Rank**</span></span> <br/> |<span data-ttu-id="8c143-306">不</span><span class="sxs-lookup"><span data-stu-id="8c143-306">No</span></span>  <br/> |<span data-ttu-id="8c143-307">根據會話中所涉及的使用者代理程式 (軟體), 在失敗的會話中相對排名的依據。</span><span class="sxs-lookup"><span data-stu-id="8c143-307">Relative ranking of failed sessions based on the user agent (software) involved in the session.</span></span> <span data-ttu-id="8c143-308">例如: RTCC/4.0.0.0 入站路由/4.0.0.0。</span><span class="sxs-lookup"><span data-stu-id="8c143-308">For example: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</span></span>  <br/> |
|<span data-ttu-id="8c143-309">**最上層的使用者代理程式**</span><span class="sxs-lookup"><span data-stu-id="8c143-309">**Top user agents**</span></span> <br/> |<span data-ttu-id="8c143-310">不</span><span class="sxs-lookup"><span data-stu-id="8c143-310">No</span></span>  <br/> |<span data-ttu-id="8c143-311">失敗會話中所涉及之使用者代理程式的名稱。</span><span class="sxs-lookup"><span data-stu-id="8c143-311">Name of the user agent involved in the failed session.</span></span>  <br/> |
|<span data-ttu-id="8c143-312">**時段**</span><span class="sxs-lookup"><span data-stu-id="8c143-312">**Sessions**</span></span> <br/> |<span data-ttu-id="8c143-313">不</span><span class="sxs-lookup"><span data-stu-id="8c143-313">No</span></span>  <br/> |<span data-ttu-id="8c143-314">每個使用者代理程式失敗的會話總數。</span><span class="sxs-lookup"><span data-stu-id="8c143-314">Total number of failed sessions per user agent.</span></span>  <br/> |
   

