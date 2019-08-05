---
title: 商務用 Skype Server 中的 P2P 摘要子報表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
description: '摘要: 瞭解商務用 Skype 伺服器中的 P2P 摘要子報表。'
ms.openlocfilehash: 5238e910896a6af956285235d7e1234fe17fe005
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188752"
---
# <a name="p2p-summary-subreport-in-skype-for-business-server"></a><span data-ttu-id="11f58-103">商務用 Skype Server 中的 P2P 摘要子報表</span><span class="sxs-lookup"><span data-stu-id="11f58-103">P2P Summary Subreport in Skype for Business Server</span></span>
 
<span data-ttu-id="11f58-104">**摘要:** 瞭解商務用 Skype Server 中的 P2P 摘要子報表。</span><span class="sxs-lookup"><span data-stu-id="11f58-104">**Summary:** Learn about the P2P Summary Subreport in Skype for Business Server.</span></span>
  
<span data-ttu-id="11f58-105">P2P 摘要子報表提供失敗的對等通訊會話的整體視圖。</span><span class="sxs-lookup"><span data-stu-id="11f58-105">The P2P Summary Subreport provides an overall view of your failed peer-to-peer communication sessions.</span></span>
  
## <a name="filters"></a><span data-ttu-id="11f58-106">濾鏡</span><span class="sxs-lookup"><span data-stu-id="11f58-106">Filters</span></span>

<span data-ttu-id="11f58-107">篩選提供一種方式, 可讓您傳回更精細設定目標的資料集, 或以不同的方式來查看傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="11f58-107">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="11f58-108">下表列出可與 P2P 摘要子報表搭配使用的篩選。</span><span class="sxs-lookup"><span data-stu-id="11f58-108">The following table lists the filters that you can use with the P2P Summary Subreport.</span></span>
  
<span data-ttu-id="11f58-109">**P2P 摘要子報表篩選**</span><span class="sxs-lookup"><span data-stu-id="11f58-109">**P2P Summary Subreport Filters**</span></span>

|<span data-ttu-id="11f58-110">**名稱**</span><span class="sxs-lookup"><span data-stu-id="11f58-110">**Name**</span></span>|<span data-ttu-id="11f58-111">**說明**</span><span class="sxs-lookup"><span data-stu-id="11f58-111">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="11f58-112">**從**</span><span class="sxs-lookup"><span data-stu-id="11f58-112">**From**</span></span> <br/> |<span data-ttu-id="11f58-113">時間範圍的開始日期和時間。</span><span class="sxs-lookup"><span data-stu-id="11f58-113">Start date and time for the time range.</span></span> <span data-ttu-id="11f58-114">若要依時間查看資料, 請輸入 [開始日期] 和 [時間], 如下所示:</span><span class="sxs-lookup"><span data-stu-id="11f58-114">To view data by hours, enter both the start date and time as follows:</span></span>  <br/> <span data-ttu-id="11f58-115">7/7/2015 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="11f58-115">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="11f58-116">如果您沒有輸入開始時間, 報告會在指定日期自動于12:00 點開始。</span><span class="sxs-lookup"><span data-stu-id="11f58-116">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="11f58-117">若要依天查看資料, 只需輸入日期:</span><span class="sxs-lookup"><span data-stu-id="11f58-117">To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="11f58-118">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="11f58-118">7/7/2015</span></span>  <br/> <span data-ttu-id="11f58-119">若要依周或依月查看, 請在您要查看的周或月份中, 輸入您要查看的日期 (不需要輸入周或月的第一天):</span><span class="sxs-lookup"><span data-stu-id="11f58-119">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="11f58-120">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="11f58-120">7/3/2015</span></span>  <br/> <span data-ttu-id="11f58-121">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="11f58-121">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="11f58-122">**自**</span><span class="sxs-lookup"><span data-stu-id="11f58-122">**To**</span></span> <br/> |<span data-ttu-id="11f58-123">時間範圍的結束日期和時間。</span><span class="sxs-lookup"><span data-stu-id="11f58-123">End date and time for the time range.</span></span> <span data-ttu-id="11f58-124">若要依時間查看資料, 請輸入 [結束日期] 和 [時間], 如下所示:</span><span class="sxs-lookup"><span data-stu-id="11f58-124">To view data by hours, enter both the end date and time as follows:</span></span>  <br/> <span data-ttu-id="11f58-125">7/7/2015 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="11f58-125">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="11f58-126">如果您沒有輸入結束時間, 報告會在指定日期自動結束于12:00。</span><span class="sxs-lookup"><span data-stu-id="11f58-126">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="11f58-127">若要依天查看資料, 只需輸入日期:</span><span class="sxs-lookup"><span data-stu-id="11f58-127">To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="11f58-128">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="11f58-128">7/7/2015</span></span>  <br/> <span data-ttu-id="11f58-129">若要依周或依月查看, 請在您要查看的周或月份中, 輸入您要查看的日期 (不需要輸入周或月的第一天):</span><span class="sxs-lookup"><span data-stu-id="11f58-129">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="11f58-130">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="11f58-130">7/3/2015</span></span>  <br/> <span data-ttu-id="11f58-131">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="11f58-131">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="11f58-132">**共**</span><span class="sxs-lookup"><span data-stu-id="11f58-132">**Pool**</span></span> <br/> |<span data-ttu-id="11f58-133">註冊機構池或邊緣伺服器的完整功能變數名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="11f58-133">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="11f58-134">您可以選取個別的池中, 或按一下 **[全部]** 來查看所有資源庫的資料。</span><span class="sxs-lookup"><span data-stu-id="11f58-134">You can either select an individual pool or click **[All]** to view data for all the pools.</span></span> <span data-ttu-id="11f58-135">這個下拉式清單會根據資料庫中的記錄, 自動填入給您。</span><span class="sxs-lookup"><span data-stu-id="11f58-135">This drop-down list is automatically populated for you based on the records in the database.</span></span> <br/> |
   
## <a name="metrics"></a><span data-ttu-id="11f58-136">指標</span><span class="sxs-lookup"><span data-stu-id="11f58-136">Metrics</span></span>

<span data-ttu-id="11f58-137">下表列出 P2P 摘要子報表中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="11f58-137">The following table lists the information provided in the P2P Summary Subreport.</span></span>
  
<span data-ttu-id="11f58-138">**P2P 摘要子報表度量單位**</span><span class="sxs-lookup"><span data-stu-id="11f58-138">**P2P Summary Subreport Metrics**</span></span>

|<span data-ttu-id="11f58-139">**名稱**</span><span class="sxs-lookup"><span data-stu-id="11f58-139">**Name**</span></span>|<span data-ttu-id="11f58-140">**您可以針對此專案進行排序嗎？**</span><span class="sxs-lookup"><span data-stu-id="11f58-140">**Can you sort on this item?**</span></span>|<span data-ttu-id="11f58-141">**說明**</span><span class="sxs-lookup"><span data-stu-id="11f58-141">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="11f58-142">**總會話數**</span><span class="sxs-lookup"><span data-stu-id="11f58-142">**Total sessions**</span></span> <br/> |<span data-ttu-id="11f58-143">不</span><span class="sxs-lookup"><span data-stu-id="11f58-143">No</span></span>  <br/> |<span data-ttu-id="11f58-144">會話總數, 包括成功的會話、失敗的會話 (預期的失敗與意外的失敗), 以及未分類的會話。</span><span class="sxs-lookup"><span data-stu-id="11f58-144">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span>  <br/> |
|<span data-ttu-id="11f58-145">**失敗率**</span><span class="sxs-lookup"><span data-stu-id="11f58-145">**Failure rate**</span></span> <br/> |<span data-ttu-id="11f58-146">不</span><span class="sxs-lookup"><span data-stu-id="11f58-146">No</span></span>  <br/> |<span data-ttu-id="11f58-147">失敗的點對點工作階段百分比。</span><span class="sxs-lookup"><span data-stu-id="11f58-147">Percentage of peer-to-peer sessions that failed.</span></span>  <br/> |
|<span data-ttu-id="11f58-148">**依模態的課時**</span><span class="sxs-lookup"><span data-stu-id="11f58-148">**Sessions by Modality**</span></span> <br/> |<span data-ttu-id="11f58-149">不</span><span class="sxs-lookup"><span data-stu-id="11f58-149">No</span></span>  <br/> |<span data-ttu-id="11f58-150">依模態分組的會話總數 (例如, 立即訊息)。</span><span class="sxs-lookup"><span data-stu-id="11f58-150">Total number of sessions grouped by modality (for example, instant messaging).</span></span>  <br/> |
|<span data-ttu-id="11f58-151">**依模態的失敗率**</span><span class="sxs-lookup"><span data-stu-id="11f58-151">**Failure rate by modality**</span></span> <br/> |<span data-ttu-id="11f58-152">不</span><span class="sxs-lookup"><span data-stu-id="11f58-152">No</span></span>  <br/> |<span data-ttu-id="11f58-153">依模態分組的失敗會話總數 (例如立即訊息)。</span><span class="sxs-lookup"><span data-stu-id="11f58-153">Total number of failed sessions grouped by modality (for example, instant messaging).</span></span>  <br/> |
   

