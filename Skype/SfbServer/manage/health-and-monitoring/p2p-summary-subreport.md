---
title: 商務用 Skype Server 中的 P2P 摘要子報表
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
ms.assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
description: 摘要：瞭解商務用 Skype Server 中的 P2P 摘要子報表。
ms.openlocfilehash: 518047fbca3c46cdc9b99299b8222d4f4fbd48ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816813"
---
# <a name="p2p-summary-subreport-in-skype-for-business-server"></a><span data-ttu-id="033ac-103">商務用 Skype Server 中的 P2P 摘要子報表</span><span class="sxs-lookup"><span data-stu-id="033ac-103">P2P Summary Subreport in Skype for Business Server</span></span>
 
<span data-ttu-id="033ac-104">**摘要：** 瞭解商務用 Skype Server 中的 P2P 摘要子報表。</span><span class="sxs-lookup"><span data-stu-id="033ac-104">**Summary:** Learn about the P2P Summary Subreport in Skype for Business Server.</span></span>
  
<span data-ttu-id="033ac-105">P2P 摘要子報表可提供失敗的對等通訊會話的整體觀點。</span><span class="sxs-lookup"><span data-stu-id="033ac-105">The P2P Summary Subreport provides an overall view of your failed peer-to-peer communication sessions.</span></span>
  
## <a name="filters"></a><span data-ttu-id="033ac-106">篩選</span><span class="sxs-lookup"><span data-stu-id="033ac-106">Filters</span></span>

<span data-ttu-id="033ac-107">篩選器可以讓您傳回更精確的資料集，或者以不同方法檢視傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="033ac-107">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="033ac-108">下表列出您可以搭配 P2P 摘要子報表使用的篩選器。</span><span class="sxs-lookup"><span data-stu-id="033ac-108">The following table lists the filters that you can use with the P2P Summary Subreport.</span></span>
  
<span data-ttu-id="033ac-109">**P2P 摘要子報表篩選**</span><span class="sxs-lookup"><span data-stu-id="033ac-109">**P2P Summary Subreport Filters**</span></span>

|<span data-ttu-id="033ac-110">**名稱**</span><span class="sxs-lookup"><span data-stu-id="033ac-110">**Name**</span></span>|<span data-ttu-id="033ac-111">**描述**</span><span class="sxs-lookup"><span data-stu-id="033ac-111">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="033ac-112">**From**</span><span class="sxs-lookup"><span data-stu-id="033ac-112">**From**</span></span> <br/> |<span data-ttu-id="033ac-p102">時間範圍的開始日期和時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="033ac-p102">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span>  <br/> <span data-ttu-id="033ac-115">7/7/2015 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="033ac-115">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="033ac-p103">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="033ac-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="033ac-118">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="033ac-118">7/7/2015</span></span>  <br/> <span data-ttu-id="033ac-119">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="033ac-119">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="033ac-120">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="033ac-120">7/3/2015</span></span>  <br/> <span data-ttu-id="033ac-121">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="033ac-121">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="033ac-122">**To**</span><span class="sxs-lookup"><span data-stu-id="033ac-122">**To**</span></span> <br/> |<span data-ttu-id="033ac-p104">時間範圍的結束日期和時間。若要按照小時檢視資料，請輸入結束日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="033ac-p104">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span>  <br/> <span data-ttu-id="033ac-125">7/7/2015 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="033ac-125">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="033ac-p105">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="033ac-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="033ac-128">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="033ac-128">7/7/2015</span></span>  <br/> <span data-ttu-id="033ac-129">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="033ac-129">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="033ac-130">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="033ac-130">7/3/2015</span></span>  <br/> <span data-ttu-id="033ac-131">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="033ac-131">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="033ac-132">**集區**</span><span class="sxs-lookup"><span data-stu-id="033ac-132">**Pool**</span></span> <br/> |<span data-ttu-id="033ac-p106">登錄器集區或 Edge Server 的完整網域名稱 (FQDN)。您可以選取個別的集區，或是按一下 [全部] 檢視所有集區的資料。此下拉式清單會自動將資料庫內的資料填入。</span><span class="sxs-lookup"><span data-stu-id="033ac-p106">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click **[All]** to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database. </span></span><br/> |
   
## <a name="metrics"></a><span data-ttu-id="033ac-136">指標</span><span class="sxs-lookup"><span data-stu-id="033ac-136">Metrics</span></span>

<span data-ttu-id="033ac-137">下表列出 P2P 摘要子報表中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="033ac-137">The following table lists the information provided in the P2P Summary Subreport.</span></span>
  
<span data-ttu-id="033ac-138">**P2P 摘要子報表度量**</span><span class="sxs-lookup"><span data-stu-id="033ac-138">**P2P Summary Subreport Metrics**</span></span>

|<span data-ttu-id="033ac-139">**名稱**</span><span class="sxs-lookup"><span data-stu-id="033ac-139">**Name**</span></span>|<span data-ttu-id="033ac-140">**可以排序這個項目嗎？**</span><span class="sxs-lookup"><span data-stu-id="033ac-140">**Can you sort on this item?**</span></span>|<span data-ttu-id="033ac-141">**描述**</span><span class="sxs-lookup"><span data-stu-id="033ac-141">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="033ac-142">**工作階段總數**</span><span class="sxs-lookup"><span data-stu-id="033ac-142">**Total sessions**</span></span> <br/> |<span data-ttu-id="033ac-143">否</span><span class="sxs-lookup"><span data-stu-id="033ac-143">No</span></span>  <br/> |<span data-ttu-id="033ac-144">工作階段的總數，包括成功的工作階段、失敗的工作階段 (預期失敗與未預期失敗) 以及未分類的工作階段。</span><span class="sxs-lookup"><span data-stu-id="033ac-144">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span>  <br/> |
|<span data-ttu-id="033ac-145">**失敗率**</span><span class="sxs-lookup"><span data-stu-id="033ac-145">**Failure rate**</span></span> <br/> |<span data-ttu-id="033ac-146">否</span><span class="sxs-lookup"><span data-stu-id="033ac-146">No</span></span>  <br/> |<span data-ttu-id="033ac-147">失敗的點對點工作階段百分比。</span><span class="sxs-lookup"><span data-stu-id="033ac-147">Percentage of peer-to-peer sessions that failed.</span></span>  <br/> |
|<span data-ttu-id="033ac-148">**依模態的會話**</span><span class="sxs-lookup"><span data-stu-id="033ac-148">**Sessions by Modality**</span></span> <br/> |<span data-ttu-id="033ac-149">否</span><span class="sxs-lookup"><span data-stu-id="033ac-149">No</span></span>  <br/> |<span data-ttu-id="033ac-150">依模態模式分組的會話總數 (例如立即訊息) 。</span><span class="sxs-lookup"><span data-stu-id="033ac-150">Total number of sessions grouped by modality (for example, instant messaging).</span></span>  <br/> |
|<span data-ttu-id="033ac-151">**依形式區分的失敗率**</span><span class="sxs-lookup"><span data-stu-id="033ac-151">**Failure rate by modality**</span></span> <br/> |<span data-ttu-id="033ac-152">否</span><span class="sxs-lookup"><span data-stu-id="033ac-152">No</span></span>  <br/> |<span data-ttu-id="033ac-153">依形式分類 (所群組的失敗會話總數，例如立即訊息) 。</span><span class="sxs-lookup"><span data-stu-id="033ac-153">Total number of failed sessions grouped by modality (for example, instant messaging).</span></span>  <br/> |
   

