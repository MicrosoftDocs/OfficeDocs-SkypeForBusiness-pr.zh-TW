---
title: 在商務用 Skype Server 中 Peer-to-Peer IM 報告
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
ms.assetid: 19ec0145-2398-437b-8989-f780c179b798
description: 摘要：瞭解商務用 Skype Server 中的 Peer-to-Peer IM 報告。
ms.openlocfilehash: 1962d2d39ce23b6cdfeaedf7db6a3ada3b1e8eab
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823493"
---
# <a name="peer-to-peer-im-report-in-skype-for-business-server"></a><span data-ttu-id="a8d41-103">在商務用 Skype Server 中 Peer-to-Peer IM 報告</span><span class="sxs-lookup"><span data-stu-id="a8d41-103">Peer-to-Peer IM Report in Skype for Business Server</span></span>
 
<span data-ttu-id="a8d41-104">**摘要：** 深入瞭解商務用 Skype Server 中的 Peer-to-Peer IM 報告。</span><span class="sxs-lookup"><span data-stu-id="a8d41-104">**Summary:** Learn about the Peer-to-Peer IM Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="a8d41-p101">對等 IM 報告會提供對等立即訊息 (IM) 工作階段的趨勢資訊 (依集區和驗證類型細分)。此報告可以顯示指定時段內 (例如，每天或每小時) 主控的工作階段總數，或者可以顯示該時段內傳送的立即訊息總數。</span><span class="sxs-lookup"><span data-stu-id="a8d41-p101">The Peer-to-Peer IM Report provides trend information about peer-to-peer instant messaging (IM) sessions, broken down by pool and by authentication type. The report can show either the total number of sessions held during the specified time period (for example, day-by-day or hour-by-hour), or it can show the total number of instant messages sent during that time period.</span></span>
  
## <a name="accessing-the-peer-to-peer-im-report"></a><span data-ttu-id="a8d41-107">存取對等 IM 報告</span><span class="sxs-lookup"><span data-stu-id="a8d41-107">Accessing the Peer-to-Peer IM Report</span></span>

<span data-ttu-id="a8d41-108">您可以只 [在商務用 Skype Server 中開啟 Peer-to-Peer 活動摘要報告](peer-to-peer-activity-summary-report.md) ，然後按一下下列其中一個計量，即可存取 Peer-to-Peer IM 報告：</span><span class="sxs-lookup"><span data-stu-id="a8d41-108">You can access the Peer-to-Peer IM Report only by opening the [Peer-to-Peer Activity Summary Report in Skype for Business Server](peer-to-peer-activity-summary-report.md) and then clicking either of the following metrics:</span></span>
  
- <span data-ttu-id="a8d41-109">對等 IM 工作階段總數</span><span class="sxs-lookup"><span data-stu-id="a8d41-109">Total peer-to-peer IM sessions</span></span>
    
- <span data-ttu-id="a8d41-110">對等 IM 訊息總數</span><span class="sxs-lookup"><span data-stu-id="a8d41-110">Total peer-to-peer IM messages</span></span>
    
## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a><span data-ttu-id="a8d41-111">善加利用對等 IM 報告</span><span class="sxs-lookup"><span data-stu-id="a8d41-111">Making the Best Use of the Peer-to-Peer IM Report</span></span>

<span data-ttu-id="a8d41-p102">依預設，對等 IM 報告會顯示每小時 (或每天，視您的設定而定) 的訊息計數。不過，您也可以選擇依每小時的工作階段來檢視那一天。若要執行這項作業，請按一下報告視窗右上角的 [隱藏/顯示參數]，然後從 [報告者] 清單按一下 [工作階段計數]。</span><span class="sxs-lookup"><span data-stu-id="a8d41-p102">By default, the Peer-to-Peer IM Report shows you the message count per-hour (or day, depending on your settings). However, you can also choose to view the day by sessions per hour. To do that, click **Hide/Show Parameters** in the upper-right corner of the Reports window, and then click **Session Count** from the **Report by** list.</span></span>
  
## <a name="filters"></a><span data-ttu-id="a8d41-115">篩選</span><span class="sxs-lookup"><span data-stu-id="a8d41-115">Filters</span></span>

<span data-ttu-id="a8d41-p103">篩選器可以讓您傳回更精確的資料集，或者以不同方法檢視傳回的資料。下表列出您可以搭配對等 IM 報告的篩選器。</span><span class="sxs-lookup"><span data-stu-id="a8d41-p103">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Peer-to-Peer IM Report.</span></span>
  
<span data-ttu-id="a8d41-118">**對等 IM 報告篩選器**</span><span class="sxs-lookup"><span data-stu-id="a8d41-118">**Peer-to-Peer IM Report Filters**</span></span>

|<span data-ttu-id="a8d41-119">**名稱**</span><span class="sxs-lookup"><span data-stu-id="a8d41-119">**Name**</span></span>|<span data-ttu-id="a8d41-120">**描述**</span><span class="sxs-lookup"><span data-stu-id="a8d41-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a8d41-121">**From**</span><span class="sxs-lookup"><span data-stu-id="a8d41-121">**From**</span></span> <br/> |<span data-ttu-id="a8d41-p104">時間範圍的開始日期和時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a8d41-p104">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span>  <br/> <span data-ttu-id="a8d41-124">7/7/2015 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="a8d41-124">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="a8d41-p105">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="a8d41-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="a8d41-127">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="a8d41-127">7/7/2015</span></span>  <br/> <span data-ttu-id="a8d41-128">若要按星期或月份查看，請輸入當週或該月內的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="a8d41-128">To view by week or by month, enter a date that falls anywhere within the week or month (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="a8d41-129">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="a8d41-129">7/3/2015</span></span>  <br/> <span data-ttu-id="a8d41-130">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="a8d41-130">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="a8d41-131">**To**</span><span class="sxs-lookup"><span data-stu-id="a8d41-131">**To**</span></span> <br/> |<span data-ttu-id="a8d41-p106">時間範圍的結束日期和時間。若要按照小時檢視資料，請輸入結束日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a8d41-p106">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span>  <br/> <span data-ttu-id="a8d41-134">7/7/2015 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="a8d41-134">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="a8d41-p107">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="a8d41-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="a8d41-137">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="a8d41-137">7/7/2015</span></span>  <br/> <span data-ttu-id="a8d41-138">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="a8d41-138">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="a8d41-139">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="a8d41-139">7/3/2015</span></span>  <br/> <span data-ttu-id="a8d41-140">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="a8d41-140">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="a8d41-141">**Interval**</span><span class="sxs-lookup"><span data-stu-id="a8d41-141">**Interval**</span></span> <br/> | <span data-ttu-id="a8d41-p108">時間間隔。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="a8d41-p108">Time interval. Select one of the following:</span></span> <br/>  <span data-ttu-id="a8d41-144">每小時 (最多可以顯示 25 個小時)</span><span class="sxs-lookup"><span data-stu-id="a8d41-144">Hourly (a maximum of 25 hours can be displayed)</span></span> <br/>  <span data-ttu-id="a8d41-145">每日 (最多可以顯示 31 天)</span><span class="sxs-lookup"><span data-stu-id="a8d41-145">Daily (a maximum of 31 days can be displayed)</span></span> <br/>  <span data-ttu-id="a8d41-146">每週 (最多可以顯示 12 週)</span><span class="sxs-lookup"><span data-stu-id="a8d41-146">Weekly (a maximum of 12 weeks can be displayed)</span></span> <br/>  <span data-ttu-id="a8d41-147">每月 (最多可以顯示 12 個月)</span><span class="sxs-lookup"><span data-stu-id="a8d41-147">Monthly (a maximum of 12 months can be displayed)</span></span> <br/>  <span data-ttu-id="a8d41-148">若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。</span><span class="sxs-lookup"><span data-stu-id="a8d41-148">If the start and end dates exceed the maximum number of values allowed for the selected interval then only the maximum number of values (starting from the start date) are displayed.</span></span> <span data-ttu-id="a8d41-149">例如，如果您選取 [開始日期 7/7/2015] 和 [結束2/28/2015 日期] 的 [每日間隔]，將會顯示 8/7/2015 12:00 AM 到 9/7/2015 12:00 AM (的資料，也就是有31天的資料) 總計。</span><span class="sxs-lookup"><span data-stu-id="a8d41-149">For example, if you select the Daily interval with a start date of 7/7/2015 and an end date of 2/28/2015, data is displayed for the days 8/7/2015 12:00 AM to 9/7/2015 12:00 AM (that is, a total of 31 days' worth of data).</span></span> <br/> |
|<span data-ttu-id="a8d41-150">**報告依據**</span><span class="sxs-lookup"><span data-stu-id="a8d41-150">**Report by**</span></span> <br/> | <span data-ttu-id="a8d41-p110">指定報告中所要使用的值。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="a8d41-p110">Indicates the values to be used in the report. Select one of the following:</span></span> <br/>  <span data-ttu-id="a8d41-153">工作階段計數</span><span class="sxs-lookup"><span data-stu-id="a8d41-153">Session count</span></span> <br/>  <span data-ttu-id="a8d41-154">訊息計數</span><span class="sxs-lookup"><span data-stu-id="a8d41-154">Message count</span></span> <br/> |
   
## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a><span data-ttu-id="a8d41-155">對等 IM 工作階段計量 (依集區)</span><span class="sxs-lookup"><span data-stu-id="a8d41-155">Metrics for Peer-to-Peer IM Session by Pool</span></span>

<span data-ttu-id="a8d41-156">下表列出對等 IM 報告提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="a8d41-156">The following table lists the information provided in the Peer-to-Peer IM Report.</span></span>
  
<span data-ttu-id="a8d41-157">**對等 IM 工作階段計量 (依集區)**</span><span class="sxs-lookup"><span data-stu-id="a8d41-157">**Metrics for Peer-to-Peer IM Session by Pool**</span></span>

|<span data-ttu-id="a8d41-158">**名稱**</span><span class="sxs-lookup"><span data-stu-id="a8d41-158">**Name**</span></span>|<span data-ttu-id="a8d41-159">**可以排序這個項目嗎？**</span><span class="sxs-lookup"><span data-stu-id="a8d41-159">**Can you sort on this item?**</span></span>|<span data-ttu-id="a8d41-160">**描述**</span><span class="sxs-lookup"><span data-stu-id="a8d41-160">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a8d41-161">**集區**</span><span class="sxs-lookup"><span data-stu-id="a8d41-161">**Pool**</span></span> <br/> |<span data-ttu-id="a8d41-162">否</span><span class="sxs-lookup"><span data-stu-id="a8d41-162">No</span></span>  <br/> |<span data-ttu-id="a8d41-163">註冊機構集區或 Edge Server 的名稱。</span><span class="sxs-lookup"><span data-stu-id="a8d41-163">Name of the Registrar pool or Edge Server.</span></span>  <br/> |
|<span data-ttu-id="a8d41-164">**日期/時間**</span><span class="sxs-lookup"><span data-stu-id="a8d41-164">**Date/Time**</span></span> <br/> |<span data-ttu-id="a8d41-165">否</span><span class="sxs-lookup"><span data-stu-id="a8d41-165">No</span></span>  <br/> |<span data-ttu-id="a8d41-166">工作階段的執行日期與時間。</span><span class="sxs-lookup"><span data-stu-id="a8d41-166">Date and time that the sessions took place.</span></span>  <br/> |
|<span data-ttu-id="a8d41-167">**Total**</span><span class="sxs-lookup"><span data-stu-id="a8d41-167">**Total**</span></span> <br/> |<span data-ttu-id="a8d41-168">否</span><span class="sxs-lookup"><span data-stu-id="a8d41-168">No</span></span>  <br/> |<span data-ttu-id="a8d41-169">工作階段總數或訊息總數。</span><span class="sxs-lookup"><span data-stu-id="a8d41-169">Total number of sessions or total message count.</span></span>  <br/> |
   
## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a><span data-ttu-id="a8d41-170">對等 IM 工作階段計量 (依驗證類型)</span><span class="sxs-lookup"><span data-stu-id="a8d41-170">Metrics for Peer-to-Peer IM Session by Authentication Type</span></span>

<span data-ttu-id="a8d41-171">下表列出對等 IM 報告針對參與者在對等工作階段中使用之每項驗證類型所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="a8d41-171">The following table lists the information provided in the Peer-to-Peer IM Report for each type of authentication used by the participants in a peer-to-peer session.</span></span>
  
<span data-ttu-id="a8d41-172">**對等 IM 工作階段計量 (依驗證類型)**</span><span class="sxs-lookup"><span data-stu-id="a8d41-172">**Metrics for Peer-to-Peer IM Session by Authentication Type**</span></span>

|<span data-ttu-id="a8d41-173">**名稱**</span><span class="sxs-lookup"><span data-stu-id="a8d41-173">**Name**</span></span>|<span data-ttu-id="a8d41-174">**可以排序這個項目嗎？**</span><span class="sxs-lookup"><span data-stu-id="a8d41-174">**Can you sort on this item?**</span></span>|<span data-ttu-id="a8d41-175">**描述**</span><span class="sxs-lookup"><span data-stu-id="a8d41-175">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a8d41-176">**驗證類型**</span><span class="sxs-lookup"><span data-stu-id="a8d41-176">**Authentication type**</span></span> <br/> |<span data-ttu-id="a8d41-177">否</span><span class="sxs-lookup"><span data-stu-id="a8d41-177">No</span></span>  <br/> | <span data-ttu-id="a8d41-p111">工作階段參與者所使用的驗證類型。一般來說，值都是下列其中之一：</span><span class="sxs-lookup"><span data-stu-id="a8d41-p111">Type of authentication used by the session participants. Values are typically one of the following:</span></span> <br/>  <span data-ttu-id="a8d41-180">Enterprise</span><span class="sxs-lookup"><span data-stu-id="a8d41-180">Enterprise</span></span> <br/>  <span data-ttu-id="a8d41-181">聯邦</span><span class="sxs-lookup"><span data-stu-id="a8d41-181">Federated</span></span> <br/>  <span data-ttu-id="a8d41-182">Pic</span><span class="sxs-lookup"><span data-stu-id="a8d41-182">PIC</span></span> <br/> |
|<span data-ttu-id="a8d41-183">**日期/時間**</span><span class="sxs-lookup"><span data-stu-id="a8d41-183">**Date/Time**</span></span> <br/> |<span data-ttu-id="a8d41-184">否</span><span class="sxs-lookup"><span data-stu-id="a8d41-184">No</span></span>  <br/> |<span data-ttu-id="a8d41-185">工作階段的執行日期與時間。</span><span class="sxs-lookup"><span data-stu-id="a8d41-185">Date and time that the sessions took place.</span></span>  <br/> |
|<span data-ttu-id="a8d41-186">**Total**</span><span class="sxs-lookup"><span data-stu-id="a8d41-186">**Total**</span></span> <br/> |<span data-ttu-id="a8d41-187">否</span><span class="sxs-lookup"><span data-stu-id="a8d41-187">No</span></span>  <br/> |<span data-ttu-id="a8d41-188">工作階段總數或訊息總數。</span><span class="sxs-lookup"><span data-stu-id="a8d41-188">Total number of sessions or total message count.</span></span>  <br/> |
   

