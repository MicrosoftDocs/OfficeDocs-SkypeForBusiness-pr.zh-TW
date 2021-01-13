---
title: 商務用 Skype Server 中的會議摘要子報告
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
ms.assetid: 2fc1d2bf-34f5-4093-a6e2-250ec1f1b004
description: 摘要：瞭解商務用 Skype Server 中的會議摘要子報告。
ms.openlocfilehash: 9a42e16bc22f01f196274f1e25396d8516e26af2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826473"
---
# <a name="conference-summary-subreport-in-skype-for-business-server"></a><span data-ttu-id="bcb70-103">商務用 Skype Server 中的會議摘要子報告</span><span class="sxs-lookup"><span data-stu-id="bcb70-103">Conference Summary Subreport in Skype for Business Server</span></span>
 
<span data-ttu-id="bcb70-104">**摘要：** 深入瞭解商務用 Skype Server 中的會議摘要子報告。</span><span class="sxs-lookup"><span data-stu-id="bcb70-104">**Summary:** Learn about the Conference Summary Subreport in Skype for Business Server.</span></span>
  
<span data-ttu-id="bcb70-p101">會議摘要子報告提供了失敗會議工作階段的整體檢視。這些失敗的工作階段可藉由工作階段類型加以細分為：焦點工作階段及 MCU 工作階段。</span><span class="sxs-lookup"><span data-stu-id="bcb70-p101">The Conference Summary Subreport provides an overall view of failed conference sessions. These failed sessions are further broken down by session type: Focus sessions and MCU sessions.</span></span>
  
## <a name="filters"></a><span data-ttu-id="bcb70-107">篩選</span><span class="sxs-lookup"><span data-stu-id="bcb70-107">Filters</span></span>

<span data-ttu-id="bcb70-p102">篩選器可供您用於傳回更加精確的一組資料，或是使用其他方式檢視傳回的資料。下表列出可搭配會議摘要子報告使用的篩選器。</span><span class="sxs-lookup"><span data-stu-id="bcb70-p102">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Summary Subreport.</span></span>
  
<span data-ttu-id="bcb70-110">**會議摘要子報告篩選器**</span><span class="sxs-lookup"><span data-stu-id="bcb70-110">**Conference Summary Subreport Filters**</span></span>

|<span data-ttu-id="bcb70-111">**名稱**</span><span class="sxs-lookup"><span data-stu-id="bcb70-111">**Name**</span></span>|<span data-ttu-id="bcb70-112">**描述**</span><span class="sxs-lookup"><span data-stu-id="bcb70-112">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bcb70-113">**From**</span><span class="sxs-lookup"><span data-stu-id="bcb70-113">**From**</span></span> <br/> |<span data-ttu-id="bcb70-p103">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bcb70-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span>  <br/> <span data-ttu-id="bcb70-116">7/7/2015 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="bcb70-116">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="bcb70-p104">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="bcb70-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="bcb70-119">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="bcb70-119">7/7/2015</span></span>  <br/> <span data-ttu-id="bcb70-120">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="bcb70-120">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="bcb70-121">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="bcb70-121">7/3/2015</span></span>  <br/> <span data-ttu-id="bcb70-122">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="bcb70-122">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="bcb70-123">**To**</span><span class="sxs-lookup"><span data-stu-id="bcb70-123">**To**</span></span> <br/> |<span data-ttu-id="bcb70-p105">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bcb70-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span>  <br/> <span data-ttu-id="bcb70-126">7/7/2015 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="bcb70-126">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="bcb70-p106">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="bcb70-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="bcb70-129">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="bcb70-129">7/7/2015</span></span>  <br/> <span data-ttu-id="bcb70-130">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="bcb70-130">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="bcb70-131">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="bcb70-131">7/3/2015</span></span>  <br/> <span data-ttu-id="bcb70-132">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="bcb70-132">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="bcb70-133">**集區**</span><span class="sxs-lookup"><span data-stu-id="bcb70-133">**Pool**</span></span> <br/> |<span data-ttu-id="bcb70-p107">登錄器集區或 Edge Server 的完整網域名稱 (FQDN)。您可以選取個別的集區，或是按一下 [全部] 檢視所有集區的資料。此下拉式清單會自動將資料庫內的資料填入。</span><span class="sxs-lookup"><span data-stu-id="bcb70-p107">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click **[All]** to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database. </span></span><br/> |
   
## <a name="metrics"></a><span data-ttu-id="bcb70-137">指標</span><span class="sxs-lookup"><span data-stu-id="bcb70-137">Metrics</span></span>

<span data-ttu-id="bcb70-138">下表列出會議摘要子報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="bcb70-138">The following table lists the information provided in the Conference Summary Subreport.</span></span>
  
<span data-ttu-id="bcb70-139">**會議摘要子報告計量**</span><span class="sxs-lookup"><span data-stu-id="bcb70-139">**Conference Summary Subreport Metrics**</span></span>

|<span data-ttu-id="bcb70-140">**名稱**</span><span class="sxs-lookup"><span data-stu-id="bcb70-140">**Name**</span></span>|<span data-ttu-id="bcb70-141">**可以排序這個項目嗎？**</span><span class="sxs-lookup"><span data-stu-id="bcb70-141">**Can you sort on this item?**</span></span>|<span data-ttu-id="bcb70-142">**描述**</span><span class="sxs-lookup"><span data-stu-id="bcb70-142">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bcb70-143">**會議總數**</span><span class="sxs-lookup"><span data-stu-id="bcb70-143">**Total conferences**</span></span> <br/> |<span data-ttu-id="bcb70-144">否</span><span class="sxs-lookup"><span data-stu-id="bcb70-144">No</span></span>  <br/> |<span data-ttu-id="bcb70-145">保留的會議總數。</span><span class="sxs-lookup"><span data-stu-id="bcb70-145">Total number of conferences held.</span></span>  <br/> |
|<span data-ttu-id="bcb70-146">**會議工作階段總數**</span><span class="sxs-lookup"><span data-stu-id="bcb70-146">**Total conference sessions**</span></span> <br/> |<span data-ttu-id="bcb70-147">否</span><span class="sxs-lookup"><span data-stu-id="bcb70-147">No</span></span>  <br/> |<span data-ttu-id="bcb70-p108">會議工作階段總數。單一會議可能會有多個工作階段；例如，會議可能包含焦點工作階段及 MCU 工作階段。</span><span class="sxs-lookup"><span data-stu-id="bcb70-p108">Total number of conference sessions. A single conference can have multiple sessions; for example, a conference might include both a Focus session and an MCU session.</span></span>  <br/> |
|<span data-ttu-id="bcb70-150">**整體工作階段失敗率**</span><span class="sxs-lookup"><span data-stu-id="bcb70-150">**Overall session failure rate**</span></span> <br/> |<span data-ttu-id="bcb70-151">否</span><span class="sxs-lookup"><span data-stu-id="bcb70-151">No</span></span>  <br/> |<span data-ttu-id="bcb70-152">所有失敗工作階段的百分比。</span><span class="sxs-lookup"><span data-stu-id="bcb70-152">Percentage of all conferences that failed.</span></span>  <br/> |
|<span data-ttu-id="bcb70-153">**焦點工作階段**</span><span class="sxs-lookup"><span data-stu-id="bcb70-153">**Focus sessions**</span></span> <br/> |<span data-ttu-id="bcb70-154">否</span><span class="sxs-lookup"><span data-stu-id="bcb70-154">No</span></span>  <br/> |<span data-ttu-id="bcb70-155">焦點工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="bcb70-155">Total number of Focus sessions.</span></span>  <br/> |
|<span data-ttu-id="bcb70-156">**焦點失敗率**</span><span class="sxs-lookup"><span data-stu-id="bcb70-156">**Focus failure rate**</span></span> <br/> |<span data-ttu-id="bcb70-157">否</span><span class="sxs-lookup"><span data-stu-id="bcb70-157">No</span></span>  <br/> |<span data-ttu-id="bcb70-158">失敗之焦點工作階段的百分比。</span><span class="sxs-lookup"><span data-stu-id="bcb70-158">Percentage of Focus sessions that failed.</span></span>  <br/> |
|<span data-ttu-id="bcb70-159">MCU 工作階段</span><span class="sxs-lookup"><span data-stu-id="bcb70-159">MCU sessions</span></span>  <br/> |<span data-ttu-id="bcb70-160">否</span><span class="sxs-lookup"><span data-stu-id="bcb70-160">No</span></span>  <br/> |<span data-ttu-id="bcb70-161">MCU 工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="bcb70-161">Total number of MCU sessions.</span></span>  <br/> |
|<span data-ttu-id="bcb70-162">**MCU 失敗率**</span><span class="sxs-lookup"><span data-stu-id="bcb70-162">**MCU failure rate**</span></span> <br/> |<span data-ttu-id="bcb70-163">否</span><span class="sxs-lookup"><span data-stu-id="bcb70-163">No</span></span>  <br/> |<span data-ttu-id="bcb70-164">失敗之 MCU 工作階段的百分比。</span><span class="sxs-lookup"><span data-stu-id="bcb70-164">Percentage of MCU sessions that failed.</span></span>  <br/> |
|<span data-ttu-id="bcb70-165">**依形式區分的 MCU 工作階段**</span><span class="sxs-lookup"><span data-stu-id="bcb70-165">**MCU sessions by modality**</span></span> <br/> |<span data-ttu-id="bcb70-166">否</span><span class="sxs-lookup"><span data-stu-id="bcb70-166">No</span></span>  <br/> |<span data-ttu-id="bcb70-167">依形式分組 (例如，IM 會議) 的 MCU 工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="bcb70-167">Total number of MCU sessions, grouped by modality (for example, IM conferencing).</span></span>  <br/> |
|<span data-ttu-id="bcb70-168">**依形式區分的失敗率**</span><span class="sxs-lookup"><span data-stu-id="bcb70-168">**Failure rate by modality**</span></span> <br/> |<span data-ttu-id="bcb70-169">否</span><span class="sxs-lookup"><span data-stu-id="bcb70-169">No</span></span>  <br/> |<span data-ttu-id="bcb70-170">依形式分組 (例如，IM 會議) 的 MCU 工作階段百分比。</span><span class="sxs-lookup"><span data-stu-id="bcb70-170">Percentage of MCU sessions that failed, grouped by modality (for example, IM conferencing).</span></span>  <br/> |
   

