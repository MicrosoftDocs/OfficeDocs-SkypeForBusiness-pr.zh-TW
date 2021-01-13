---
title: 商務用 Skype Server 中的失敗清單報告
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
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: 摘要：瞭解商務用 Skype Server 中的失敗清單報告。
ms.openlocfilehash: 48654ee827f0d7efcb50bcccc4e1d2f3fdb5422e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816843"
---
# <a name="failure-list-report-in-skype-for-business-server"></a><span data-ttu-id="9fcd2-103">商務用 Skype Server 中的失敗清單報告</span><span class="sxs-lookup"><span data-stu-id="9fcd2-103">Failure List Report in Skype for Business Server</span></span> 
 
<span data-ttu-id="9fcd2-104">**摘要：** 深入瞭解商務用 Skype Server 中的失敗清單報告。</span><span class="sxs-lookup"><span data-stu-id="9fcd2-104">**Summary:** Learn about the Failure List Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="9fcd2-105">「失敗清單報告」會提供參與「對等」或「會議」會話失敗之人員的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="9fcd2-105">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session.</span></span> <span data-ttu-id="9fcd2-106">此資訊包含發生問題之使用者的 URI，以及與失敗相關聯的 SIP 回應碼和診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="9fcd2-106">This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span></span>
  
## <a name="accessing-the-failure-list-report"></a><span data-ttu-id="9fcd2-107">存取失敗清單報告</span><span class="sxs-lookup"><span data-stu-id="9fcd2-107">Accessing the Failure List Report</span></span>

<span data-ttu-id="9fcd2-108">若要存取失敗清單報告，請 [在 [商務用 Skype 伺服器] 的 [失敗散佈報告] 中](failure-distribution-report.md)按一下下列任一度量：</span><span class="sxs-lookup"><span data-stu-id="9fcd2-108">The Failure List Report is accessed by clicking any of the following metrics on the [Failure Distribution Report in Skype for Business Server](failure-distribution-report.md):</span></span>
  
- <span data-ttu-id="9fcd2-109">前幾名診斷原因 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="9fcd2-109">Top diagnostic reasons (sessions)</span></span>
    
- <span data-ttu-id="9fcd2-110">最常見形式 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="9fcd2-110">Top modalities (sessions)</span></span>
    
- <span data-ttu-id="9fcd2-111">最常見集區 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="9fcd2-111">Top pools (sessions)</span></span>
    
- <span data-ttu-id="9fcd2-112">最常見來源 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="9fcd2-112">Top sources (sessions)</span></span>
    
- <span data-ttu-id="9fcd2-113">最常見元件 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="9fcd2-113">Top components (sessions)</span></span>
    
- <span data-ttu-id="9fcd2-114">最常見來源使用者 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="9fcd2-114">Top from users (sessions)</span></span>
    
- <span data-ttu-id="9fcd2-115">最常見目標使用者 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="9fcd2-115">Top to users (sessions)</span></span>
    
- <span data-ttu-id="9fcd2-116">最常見來源使用者代理程式 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="9fcd2-116">Top from user agents (sessions)</span></span>
    
<span data-ttu-id="9fcd2-117">在 [失敗清單] 報告中，您可以透過按一下點對點工作階段的會話詳細資料計量，存取 [商務用 Skype Server 中的 Peer-to-Peer 會話詳細資料包告](peer-to-peer-session-detail-report.md) 。</span><span class="sxs-lookup"><span data-stu-id="9fcd2-117">From the Failure List Report you can access the [Peer-to-Peer Session Detail Report in Skype for Business Server](peer-to-peer-session-detail-report.md) by clicking the Session detail metric for a peer-to-peer session.</span></span> <span data-ttu-id="9fcd2-118">您也可以按一下會議的會議度量來存取會議詳細資料包告。</span><span class="sxs-lookup"><span data-stu-id="9fcd2-118">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span></span>
  
## <a name="making-the-best-use-of-the-failure-list-report"></a><span data-ttu-id="9fcd2-119">讓 [失敗清單] 報告的最佳用法</span><span class="sxs-lookup"><span data-stu-id="9fcd2-119">Making the Best Use of the Failure List Report</span></span>

<span data-ttu-id="9fcd2-120">在 [失敗清單] 報告中，只要將滑鼠停留在該值上，您就可以查看每個回應代碼或每個診斷識別碼的描述。</span><span class="sxs-lookup"><span data-stu-id="9fcd2-120">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value.</span></span> <span data-ttu-id="9fcd2-121">例如，如果您將滑鼠停留在診斷 ID 7025 上，您會看到工具提示中顯示下列內容：</span><span class="sxs-lookup"><span data-stu-id="9fcd2-121">For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span></span>
  
<span data-ttu-id="9fcd2-122">為使用者建立媒體時發生內部伺服器錯誤。</span><span class="sxs-lookup"><span data-stu-id="9fcd2-122">Internal server error creating media for user.</span></span>
  
<span data-ttu-id="9fcd2-123">請務必注意，失敗清單報告並未提供直接找回至少參與一則失敗之會話之所有使用者的清單，也不會提供一種方法來判斷失敗的會話中最常參與的使用者。</span><span class="sxs-lookup"><span data-stu-id="9fcd2-123">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session.</span></span> <span data-ttu-id="9fcd2-124"> (一件事，失敗清單報告沒有篩選功能。 ) 不過，如果您匯出資料，然後將其轉換成逗號分隔值檔案，您可以使用 Windows PowerShell 尋找類似問題的答案。</span><span class="sxs-lookup"><span data-stu-id="9fcd2-124">(For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those.</span></span> <span data-ttu-id="9fcd2-125">例如，假設您將資料儲存到。名為 C:\Data\Failure_List.csv 的 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="9fcd2-125">For example, suppose you save the data to a .CSV file named C:\Data\Failure_List.csv.</span></span> <span data-ttu-id="9fcd2-126">根據儲存在該檔案中的資料，此命令會列出至少包含一個失敗會話的所有使用者：</span><span class="sxs-lookup"><span data-stu-id="9fcd2-126">Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span></span> 
  
```PowerShell
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

<span data-ttu-id="9fcd2-127">該命令會傳回類似以下的清單：</span><span class="sxs-lookup"><span data-stu-id="9fcd2-127">That command will return a list similar to this:</span></span>
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

<span data-ttu-id="9fcd2-128">這兩個命令傳回每位使用者參與的失敗會話總數：</span><span class="sxs-lookup"><span data-stu-id="9fcd2-128">These two commands report back the total number of failed sessions that each user was involved in:</span></span>
  
```PowerShell
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

<span data-ttu-id="9fcd2-129">該命令將傳回類似下列的資料：</span><span class="sxs-lookup"><span data-stu-id="9fcd2-129">That will return data similar to this:</span></span>
  
<pre>
Count    Name
 -----    ----
    20    Pilar.Ackerman@litwareinc.com
    20    David.Ahs@litwareinc.com
    16    Gilead.Amosnino@litwareinc.com
    16    Ken.Myero@litwareinc.com
    14    Henrik.Jensen@litwareinc.com
</pre>

## <a name="filters"></a><span data-ttu-id="9fcd2-130">篩選</span><span class="sxs-lookup"><span data-stu-id="9fcd2-130">Filters</span></span>

<span data-ttu-id="9fcd2-131">無。</span><span class="sxs-lookup"><span data-stu-id="9fcd2-131">None.</span></span> <span data-ttu-id="9fcd2-132">您無法篩選失敗清單報告。</span><span class="sxs-lookup"><span data-stu-id="9fcd2-132">You cannot filter the Failure List Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="9fcd2-133">指標</span><span class="sxs-lookup"><span data-stu-id="9fcd2-133">Metrics</span></span>

<span data-ttu-id="9fcd2-134">下表列出每個失敗通話的失敗清單報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="9fcd2-134">The following table lists the information provided in the Failure List Report for each failed call.</span></span>
  
<span data-ttu-id="9fcd2-135">**失敗清單報告計量**</span><span class="sxs-lookup"><span data-stu-id="9fcd2-135">**Failure List Report Metrics**</span></span>

|<span data-ttu-id="9fcd2-136">**名稱**</span><span class="sxs-lookup"><span data-stu-id="9fcd2-136">**Name**</span></span>|<span data-ttu-id="9fcd2-137">**可以排序這個項目嗎？**</span><span class="sxs-lookup"><span data-stu-id="9fcd2-137">**Can you sort on this item?**</span></span>|<span data-ttu-id="9fcd2-138">**描述**</span><span class="sxs-lookup"><span data-stu-id="9fcd2-138">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9fcd2-139">**報告時間**</span><span class="sxs-lookup"><span data-stu-id="9fcd2-139">**Reported time**</span></span> <br/> |<span data-ttu-id="9fcd2-140">否</span><span class="sxs-lookup"><span data-stu-id="9fcd2-140">No</span></span>  <br/> |<span data-ttu-id="9fcd2-141">報告的記錄日期與時間。</span><span class="sxs-lookup"><span data-stu-id="9fcd2-141">Date and time the report was recorded.</span></span>  <br/> |
|<span data-ttu-id="9fcd2-142">**請求**</span><span class="sxs-lookup"><span data-stu-id="9fcd2-142">**Request**</span></span> <br/> |<span data-ttu-id="9fcd2-143">否</span><span class="sxs-lookup"><span data-stu-id="9fcd2-143">No</span></span>  <br/> |<span data-ttu-id="9fcd2-144">失敗的 SIP 要求類型。</span><span class="sxs-lookup"><span data-stu-id="9fcd2-144">SIP request type that failed.</span></span> <span data-ttu-id="9fcd2-145">例如，INVITE 或再見。</span><span class="sxs-lookup"><span data-stu-id="9fcd2-145">For example, INVITE or BYE.</span></span>  <br/> |
|<span data-ttu-id="9fcd2-146">**回應碼**</span><span class="sxs-lookup"><span data-stu-id="9fcd2-146">**Response code**</span></span> <br/> |<span data-ttu-id="9fcd2-147">否</span><span class="sxs-lookup"><span data-stu-id="9fcd2-147">No</span></span>  <br/> |<span data-ttu-id="9fcd2-148">會議失敗時所傳送的 SIP 回應碼。</span><span class="sxs-lookup"><span data-stu-id="9fcd2-148">SIP response code sent when the conference failed.</span></span>  <br/> |
|<span data-ttu-id="9fcd2-149">**診斷識別碼**</span><span class="sxs-lookup"><span data-stu-id="9fcd2-149">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="9fcd2-150">否</span><span class="sxs-lookup"><span data-stu-id="9fcd2-150">No</span></span>  <br/> |<span data-ttu-id="9fcd2-151">附加至 SIP 郵件（通常會在疑難排解錯誤中提供有用資訊) ）的表單中的唯一識別碼 (。</span><span class="sxs-lookup"><span data-stu-id="9fcd2-151">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="9fcd2-152">**加入成本時間 (毫秒)**</span><span class="sxs-lookup"><span data-stu-id="9fcd2-152">**Join cost time (ms)**</span></span> <br/> |<span data-ttu-id="9fcd2-153">否</span><span class="sxs-lookup"><span data-stu-id="9fcd2-153">No</span></span>  <br/> |<span data-ttu-id="9fcd2-154">使用者加入會議所需的時間長度 (（毫秒）) 。</span><span class="sxs-lookup"><span data-stu-id="9fcd2-154">Amount of time (in milliseconds) required for the user to join the conference.</span></span>  <br/> |
|<span data-ttu-id="9fcd2-155">**來源使用者**</span><span class="sxs-lookup"><span data-stu-id="9fcd2-155">**From user**</span></span> <br/> |<span data-ttu-id="9fcd2-156">否</span><span class="sxs-lookup"><span data-stu-id="9fcd2-156">No</span></span>  <br/> |<span data-ttu-id="9fcd2-157">撥打通話之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="9fcd2-157">SIP address of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="9fcd2-158">**從使用者代理程式**</span><span class="sxs-lookup"><span data-stu-id="9fcd2-158">**From user agent**</span></span> <br/> |<span data-ttu-id="9fcd2-159">否</span><span class="sxs-lookup"><span data-stu-id="9fcd2-159">No</span></span>  <br/> |<span data-ttu-id="9fcd2-160">起始通話之使用者端點所使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="9fcd2-160">Software used by the endpoint of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="9fcd2-161">**目標使用者**</span><span class="sxs-lookup"><span data-stu-id="9fcd2-161">**To user**</span></span> <br/> |<span data-ttu-id="9fcd2-162">否</span><span class="sxs-lookup"><span data-stu-id="9fcd2-162">No</span></span>  <br/> |<span data-ttu-id="9fcd2-163">呼叫之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="9fcd2-163">SIP address of the user who was being called.</span></span>  <br/> |
   

