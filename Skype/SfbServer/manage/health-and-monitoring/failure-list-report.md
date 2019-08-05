---
title: 商務用 Skype Server 中的 [失敗清單] 報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: '摘要: 瞭解商務用 Skype 伺服器中的 [失敗清單] 報告。'
ms.openlocfilehash: 72637863d7a15d26ea997de8a9c3526279afc57f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193738"
---
# <a name="failure-list-report-in-skype-for-business-server"></a><span data-ttu-id="3e5a5-103">商務用 Skype Server 中的 [失敗清單] 報告</span><span class="sxs-lookup"><span data-stu-id="3e5a5-103">Failure List Report in Skype for Business Server</span></span> 
 
<span data-ttu-id="3e5a5-104">**摘要:** 瞭解商務用 Skype Server 中的 [失敗清單] 報告。</span><span class="sxs-lookup"><span data-stu-id="3e5a5-104">**Summary:** Learn about the Failure List Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="3e5a5-105">[失敗清單] 報告會提供參與對等無法進行對等或會議會話的個別參與者的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="3e5a5-105">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session.</span></span> <span data-ttu-id="3e5a5-106">此資訊包含遇到問題之使用者的 URI, 以及與失敗相關聯的 SIP 回應程式碼與診斷 ID。</span><span class="sxs-lookup"><span data-stu-id="3e5a5-106">This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span></span>
  
## <a name="accessing-the-failure-list-report"></a><span data-ttu-id="3e5a5-107">存取失敗清單報告</span><span class="sxs-lookup"><span data-stu-id="3e5a5-107">Accessing the Failure List Report</span></span>

<span data-ttu-id="3e5a5-108">若要存取 [失敗清單] 報告, 請按一下 [商務用 Skype 伺服器] 的 [[失敗] 發佈報告中](failure-distribution-report.md)的任何一個度量單位:</span><span class="sxs-lookup"><span data-stu-id="3e5a5-108">The Failure List Report is accessed by clicking any of the following metrics on the [Failure Distribution Report in Skype for Business Server](failure-distribution-report.md):</span></span>
  
- <span data-ttu-id="3e5a5-109">常見的診斷原因 (會話)</span><span class="sxs-lookup"><span data-stu-id="3e5a5-109">Top diagnostic reasons (sessions)</span></span>
    
- <span data-ttu-id="3e5a5-110">熱門形式 (會話)</span><span class="sxs-lookup"><span data-stu-id="3e5a5-110">Top modalities (sessions)</span></span>
    
- <span data-ttu-id="3e5a5-111">頂層池 (會話)</span><span class="sxs-lookup"><span data-stu-id="3e5a5-111">Top pools (sessions)</span></span>
    
- <span data-ttu-id="3e5a5-112">熱門來源 (會話)</span><span class="sxs-lookup"><span data-stu-id="3e5a5-112">Top sources (sessions)</span></span>
    
- <span data-ttu-id="3e5a5-113">Top 元件 (會話)</span><span class="sxs-lookup"><span data-stu-id="3e5a5-113">Top components (sessions)</span></span>
    
- <span data-ttu-id="3e5a5-114">使用者的最上層 (會話)</span><span class="sxs-lookup"><span data-stu-id="3e5a5-114">Top from users (sessions)</span></span>
    
- <span data-ttu-id="3e5a5-115">使用者的最上層 (會話)</span><span class="sxs-lookup"><span data-stu-id="3e5a5-115">Top to users (sessions)</span></span>
    
- <span data-ttu-id="3e5a5-116">使用者代理程式 (會話) 的頂端</span><span class="sxs-lookup"><span data-stu-id="3e5a5-116">Top from user agents (sessions)</span></span>
    
<span data-ttu-id="3e5a5-117">在 [失敗清單] 報告中, 您可以透過按一下點對點工作階段的會話詳細資料指標,[在商務用 Skype Server 中存取點對點工作階段詳細資料包告](peer-to-peer-session-detail-report.md)。</span><span class="sxs-lookup"><span data-stu-id="3e5a5-117">From the Failure List Report you can access the [Peer-to-Peer Session Detail Report in Skype for Business Server](peer-to-peer-session-detail-report.md) by clicking the Session detail metric for a peer-to-peer session.</span></span> <span data-ttu-id="3e5a5-118">您也可以按一下會議的會議指標, 以存取會議詳細資料包告。</span><span class="sxs-lookup"><span data-stu-id="3e5a5-118">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span></span>
  
## <a name="making-the-best-use-of-the-failure-list-report"></a><span data-ttu-id="3e5a5-119">充分利用 [失敗清單] 報告</span><span class="sxs-lookup"><span data-stu-id="3e5a5-119">Making the Best Use of the Failure List Report</span></span>

<span data-ttu-id="3e5a5-120">在 [失敗清單] 報告中, 您只要將滑鼠放在該值上, 就能查看每個回應代碼或每個診斷 ID 的描述。</span><span class="sxs-lookup"><span data-stu-id="3e5a5-120">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value.</span></span> <span data-ttu-id="3e5a5-121">例如, 如果您將滑鼠放在診斷 ID 7025 上, 您會看到下列顯示在工具提示中:</span><span class="sxs-lookup"><span data-stu-id="3e5a5-121">For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span></span>
  
<span data-ttu-id="3e5a5-122">為使用者建立媒體時發生內部伺服器錯誤。</span><span class="sxs-lookup"><span data-stu-id="3e5a5-122">Internal server error creating media for user.</span></span>
  
<span data-ttu-id="3e5a5-123">請務必注意, [失敗清單] 報告不會提供直接檢索至少參與一個失敗會話之所有使用者清單的簡單方法, 也不會提供判斷哪些使用者最常參與失敗的方法。課時.</span><span class="sxs-lookup"><span data-stu-id="3e5a5-123">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session.</span></span> <span data-ttu-id="3e5a5-124">(一件事, 失敗清單報告沒有篩選功能)。不過, 如果您匯出資料, 然後將它轉換成逗號分隔值檔案, 您可以使用 Windows PowerShell 來尋找問題等問題的答案。</span><span class="sxs-lookup"><span data-stu-id="3e5a5-124">(For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those.</span></span> <span data-ttu-id="3e5a5-125">例如, 假設您將資料儲存至。名為 C:\Data\Failure_List.csv. 的 CSV 檔案</span><span class="sxs-lookup"><span data-stu-id="3e5a5-125">For example, suppose you save the data to a .CSV file named C:\Data\Failure_List.csv.</span></span> <span data-ttu-id="3e5a5-126">根據儲存在該檔案中的資料, 此命令會列出至少有一個失敗的會話中所涉及的所有使用者:</span><span class="sxs-lookup"><span data-stu-id="3e5a5-126">Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span></span> 
  
```
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

<span data-ttu-id="3e5a5-127">該命令會傳回如下所示的清單:</span><span class="sxs-lookup"><span data-stu-id="3e5a5-127">That command will return a list similar to this:</span></span>
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

<span data-ttu-id="3e5a5-128">這兩個命令會傳回每位使用者所涉及的失敗會話總數:</span><span class="sxs-lookup"><span data-stu-id="3e5a5-128">These two commands report back the total number of failed sessions that each user was involved in:</span></span>
  
```
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

<span data-ttu-id="3e5a5-129">這樣會傳回如下所示的資料:</span><span class="sxs-lookup"><span data-stu-id="3e5a5-129">That will return data similar to this:</span></span>
  
<pre>
Count    Name
 -----    ----
    20    Pilar.Ackerman@litwareinc.com
    20    David.Ahs@litwareinc.com
    16    Gilead.Amosnino@litwareinc.com
    16    Ken.Myero@litwareinc.com
    14    Henrik.Jensen@litwareinc.com
</pre>

## <a name="filters"></a><span data-ttu-id="3e5a5-130">濾鏡</span><span class="sxs-lookup"><span data-stu-id="3e5a5-130">Filters</span></span>

<span data-ttu-id="3e5a5-131">無。</span><span class="sxs-lookup"><span data-stu-id="3e5a5-131">None.</span></span> <span data-ttu-id="3e5a5-132">您無法篩選失敗清單報告。</span><span class="sxs-lookup"><span data-stu-id="3e5a5-132">You cannot filter the Failure List Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="3e5a5-133">指標</span><span class="sxs-lookup"><span data-stu-id="3e5a5-133">Metrics</span></span>

<span data-ttu-id="3e5a5-134">下表列出每個失敗的通話在失敗清單報告中所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="3e5a5-134">The following table lists the information provided in the Failure List Report for each failed call.</span></span>
  
<span data-ttu-id="3e5a5-135">**失敗清單報告度量單位**</span><span class="sxs-lookup"><span data-stu-id="3e5a5-135">**Failure List Report Metrics**</span></span>

|<span data-ttu-id="3e5a5-136">**名稱**</span><span class="sxs-lookup"><span data-stu-id="3e5a5-136">**Name**</span></span>|<span data-ttu-id="3e5a5-137">**您可以針對此專案進行排序嗎？**</span><span class="sxs-lookup"><span data-stu-id="3e5a5-137">**Can you sort on this item?**</span></span>|<span data-ttu-id="3e5a5-138">**說明**</span><span class="sxs-lookup"><span data-stu-id="3e5a5-138">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3e5a5-139">**報告時間**</span><span class="sxs-lookup"><span data-stu-id="3e5a5-139">**Reported time**</span></span> <br/> |<span data-ttu-id="3e5a5-140">不</span><span class="sxs-lookup"><span data-stu-id="3e5a5-140">No</span></span>  <br/> |<span data-ttu-id="3e5a5-141">記錄報告的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="3e5a5-141">Date and time the report was recorded.</span></span>  <br/> |
|<span data-ttu-id="3e5a5-142">**徵求**</span><span class="sxs-lookup"><span data-stu-id="3e5a5-142">**Request**</span></span> <br/> |<span data-ttu-id="3e5a5-143">不</span><span class="sxs-lookup"><span data-stu-id="3e5a5-143">No</span></span>  <br/> |<span data-ttu-id="3e5a5-144">失敗的 SIP 要求類型。</span><span class="sxs-lookup"><span data-stu-id="3e5a5-144">SIP request type that failed.</span></span> <span data-ttu-id="3e5a5-145">例如, [邀請] 或 [再見]。</span><span class="sxs-lookup"><span data-stu-id="3e5a5-145">For example, INVITE or BYE.</span></span>  <br/> |
|<span data-ttu-id="3e5a5-146">**回應代碼**</span><span class="sxs-lookup"><span data-stu-id="3e5a5-146">**Response code**</span></span> <br/> |<span data-ttu-id="3e5a5-147">不</span><span class="sxs-lookup"><span data-stu-id="3e5a5-147">No</span></span>  <br/> |<span data-ttu-id="3e5a5-148">在會議失敗時傳送 SIP 回應代碼。</span><span class="sxs-lookup"><span data-stu-id="3e5a5-148">SIP response code sent when the conference failed.</span></span>  <br/> |
|<span data-ttu-id="3e5a5-149">**診斷識別碼**</span><span class="sxs-lookup"><span data-stu-id="3e5a5-149">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="3e5a5-150">不</span><span class="sxs-lookup"><span data-stu-id="3e5a5-150">No</span></span>  <br/> |<span data-ttu-id="3e5a5-151">附加至 SIP 訊息的唯一識別碼 (ms diagnostics 標頭形式), 通常可在疑難排解錯誤中提供有用的資訊。</span><span class="sxs-lookup"><span data-stu-id="3e5a5-151">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="3e5a5-152">**加入成本時間 (毫秒)**</span><span class="sxs-lookup"><span data-stu-id="3e5a5-152">**Join cost time (ms)**</span></span> <br/> |<span data-ttu-id="3e5a5-153">不</span><span class="sxs-lookup"><span data-stu-id="3e5a5-153">No</span></span>  <br/> |<span data-ttu-id="3e5a5-154">使用者加入會議所需的時間長度 (以毫秒為單位)。</span><span class="sxs-lookup"><span data-stu-id="3e5a5-154">Amount of time (in milliseconds) required for the user to join the conference.</span></span>  <br/> |
|<span data-ttu-id="3e5a5-155">**從使用者**</span><span class="sxs-lookup"><span data-stu-id="3e5a5-155">**From user**</span></span> <br/> |<span data-ttu-id="3e5a5-156">不</span><span class="sxs-lookup"><span data-stu-id="3e5a5-156">No</span></span>  <br/> |<span data-ttu-id="3e5a5-157">啟動通話的使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="3e5a5-157">SIP address of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="3e5a5-158">**從使用者代理程式**</span><span class="sxs-lookup"><span data-stu-id="3e5a5-158">**From user agent**</span></span> <br/> |<span data-ttu-id="3e5a5-159">不</span><span class="sxs-lookup"><span data-stu-id="3e5a5-159">No</span></span>  <br/> |<span data-ttu-id="3e5a5-160">啟動通話之使用者的端點所使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="3e5a5-160">Software used by the endpoint of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="3e5a5-161">**給使用者**</span><span class="sxs-lookup"><span data-stu-id="3e5a5-161">**To user**</span></span> <br/> |<span data-ttu-id="3e5a5-162">不</span><span class="sxs-lookup"><span data-stu-id="3e5a5-162">No</span></span>  <br/> |<span data-ttu-id="3e5a5-163">呼叫的使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="3e5a5-163">SIP address of the user who was being called.</span></span>  <br/> |
   

