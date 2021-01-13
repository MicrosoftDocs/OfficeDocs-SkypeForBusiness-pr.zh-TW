---
title: 在商務用 Skype Server 中 Peer-to-Peer 會話詳細資料包告
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
ms.assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
description: 摘要：瞭解商務用 Skype Server 中的 Peer-to-Peer 會話詳細資料包告。
ms.openlocfilehash: 4dfa2b87b1fbba72282b52fa2ca58ca0f1e70630
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816763"
---
# <a name="peer-to-peer-session-detail-report-in-skype-for-business-server"></a><span data-ttu-id="724e6-103">在商務用 Skype Server 中 Peer-to-Peer 會話詳細資料包告</span><span class="sxs-lookup"><span data-stu-id="724e6-103">Peer-to-Peer Session Detail Report in Skype for Business Server</span></span>
 
<span data-ttu-id="724e6-104">**摘要：** 深入瞭解商務用 Skype Server 中的 Peer-to-Peer 會話詳細資料包告。</span><span class="sxs-lookup"><span data-stu-id="724e6-104">**Summary:** Learn about the Peer-to-Peer Session Detail Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="724e6-105">Peer-to-Peer 會話詳細資料包告會傳回點對點工作階段的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="724e6-105">The Peer-to-Peer Session Detail Report returns detailed information about a peer-to-peer session.</span></span> <span data-ttu-id="724e6-106">例如，如果您選取立即訊息會話，該報告將會告訴您會話中的兩位使用者所傳送的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="724e6-106">For example, if you select an instant messaging session, the report will tell you the number of messages sent by each of the two users in the session.</span></span>
  
## <a name="accessing-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="724e6-107">存取 Peer-to-Peer 會話詳細資料包告</span><span class="sxs-lookup"><span data-stu-id="724e6-107">Accessing the Peer-to-Peer Session Detail Report</span></span>

<span data-ttu-id="724e6-108">您可以從下列任何報告中存取 Peer-to-Peer 會話詳細資料包告 (所有可從監控報告首頁存取的報告) ：</span><span class="sxs-lookup"><span data-stu-id="724e6-108">The Peer-to-Peer Session Detail Report can be accessed from any of the following reports (all of which can be accessed from the Monitoring Reports home page):</span></span>
  
- <span data-ttu-id="724e6-109">IP 電話清查報告</span><span class="sxs-lookup"><span data-stu-id="724e6-109">IP Phone Inventory Report</span></span>
    
- <span data-ttu-id="724e6-110">使用者活動報告</span><span class="sxs-lookup"><span data-stu-id="724e6-110">User Activity Report</span></span>
    
- <span data-ttu-id="724e6-111">通話許可控制報告</span><span class="sxs-lookup"><span data-stu-id="724e6-111">Call Admission Control Report</span></span>
    
- <span data-ttu-id="724e6-112">失敗清單報告</span><span class="sxs-lookup"><span data-stu-id="724e6-112">Failure List Report</span></span> 
    
<span data-ttu-id="724e6-113">在 [Peer-to-Peer 會話詳細資料包告] 中，按一下 [診斷報告 (詳細資料]) 指標，即可存取 [商務用 Skype Server 中的診斷報告](diagnostic-report.md) 。</span><span class="sxs-lookup"><span data-stu-id="724e6-113">From within the Peer-to-Peer Session Detail Report you can access the [Diagnostic Report in Skype for Business Server](diagnostic-report.md) by clicking the Diagnostic Report (Details) metric.</span></span> <span data-ttu-id="724e6-114">您也可以按一下下列兩個度量，以存取最上層失敗報告：</span><span class="sxs-lookup"><span data-stu-id="724e6-114">You can also access the Top Failures Report by clicking either of these two metrics:</span></span>
  
- <span data-ttu-id="724e6-115">回應</span><span class="sxs-lookup"><span data-stu-id="724e6-115">Response</span></span>
    
- <span data-ttu-id="724e6-116">診斷識別碼</span><span class="sxs-lookup"><span data-stu-id="724e6-116">Diagnostic ID</span></span>
    
## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="724e6-117">Peer-to-Peer 會話詳細資料包告的最佳用法</span><span class="sxs-lookup"><span data-stu-id="724e6-117">Making the Best Use of the Peer-to-Peer session Detail Report</span></span>

<span data-ttu-id="724e6-118">「Peer-to-Peer 會話詳細資料包告」包括大量的計量，許多系統管理員可能都不熟悉。</span><span class="sxs-lookup"><span data-stu-id="724e6-118">The Peer-to-Peer Session Detail Report includes a large number of metrics, many of which might not be familiar to system administrators.</span></span> <span data-ttu-id="724e6-119">不過，您通常可以查看工具提示，只要將滑鼠放在「規格」標籤上方，就能提供該度量的簡短描述。</span><span class="sxs-lookup"><span data-stu-id="724e6-119">Often-times, however, you can view a tooltip that offers a brief description of that metric simply by holding your mouse over the metric label.</span></span>
  
<span data-ttu-id="724e6-120">請注意，顯示在特定報告上的實際度量值將取決於您所選取的點對點工作階段類型。</span><span class="sxs-lookup"><span data-stu-id="724e6-120">Note that the actual metrics shown on a given report will depend on the type of peer-to-peer session you selected.</span></span> <span data-ttu-id="724e6-121">音訊/視頻會話會報告一組不同于立即訊息會話的計量。</span><span class="sxs-lookup"><span data-stu-id="724e6-121">An audio/video session will report a different set of metrics than an instant messaging session.</span></span>
  
<span data-ttu-id="724e6-122">您也可以將滑鼠停留在回應程式碼和診斷識別碼計量中，以取得這些值的描述：</span><span class="sxs-lookup"><span data-stu-id="724e6-122">You can also hold your mouse over the Response code and Diagnostic ID metrics in order to obtain a description of those values:</span></span>
  
## <a name="filters"></a><span data-ttu-id="724e6-123">篩選</span><span class="sxs-lookup"><span data-stu-id="724e6-123">Filters</span></span>

<span data-ttu-id="724e6-124">無。</span><span class="sxs-lookup"><span data-stu-id="724e6-124">None.</span></span> <span data-ttu-id="724e6-125">您無法篩選 Peer-to-Peer 會話詳細資料包告。</span><span class="sxs-lookup"><span data-stu-id="724e6-125">You cannot filter the Peer-to-Peer Session Detail Report.</span></span>
  
## <a name="session-information-metrics"></a><span data-ttu-id="724e6-126">會話資訊計量</span><span class="sxs-lookup"><span data-stu-id="724e6-126">Session Information Metrics</span></span>

<span data-ttu-id="724e6-127">下表列出每個會話的 Peer-to-Peer 會話詳細資料包告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="724e6-127">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session.</span></span>
  
<span data-ttu-id="724e6-128">**會話資訊計量**</span><span class="sxs-lookup"><span data-stu-id="724e6-128">**Session Information Metrics**</span></span>

|<span data-ttu-id="724e6-129">**名稱**</span><span class="sxs-lookup"><span data-stu-id="724e6-129">**Name**</span></span>|<span data-ttu-id="724e6-130">**描述**</span><span class="sxs-lookup"><span data-stu-id="724e6-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="724e6-131">**集區 FQDN**</span><span class="sxs-lookup"><span data-stu-id="724e6-131">**Pool FQDN**</span></span> <br/> |<span data-ttu-id="724e6-132">與會話有關之註冊區集區或 Edge Server 的完整功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="724e6-132">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server involved in the session.</span></span>  <br/> |
|<span data-ttu-id="724e6-133">**邀請時間**</span><span class="sxs-lookup"><span data-stu-id="724e6-133">**Invite time**</span></span> <br/> |<span data-ttu-id="724e6-134">最初傳送會話邀請的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="724e6-134">Date and time the session invitation was originally sent.</span></span>  <br/> |
|<span data-ttu-id="724e6-135">**回應時間**</span><span class="sxs-lookup"><span data-stu-id="724e6-135">**Response time**</span></span> <br/> |<span data-ttu-id="724e6-136">收到邀請接受的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="724e6-136">Date and time that the invitation acceptance was received.</span></span>  <br/> |
|<span data-ttu-id="724e6-137">**來源使用者**</span><span class="sxs-lookup"><span data-stu-id="724e6-137">**From user**</span></span> <br/> |<span data-ttu-id="724e6-138">啟動工作階段之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="724e6-138">SIP address of the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="724e6-139">**從使用者代理程式**</span><span class="sxs-lookup"><span data-stu-id="724e6-139">**From user agent**</span></span> <br/> |<span data-ttu-id="724e6-140">啟動會話之使用者端點所使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="724e6-140">Software used by the endpoint of the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="724e6-141">**來自使用者內部**</span><span class="sxs-lookup"><span data-stu-id="724e6-141">**Is From user internal**</span></span> <br/> |<span data-ttu-id="724e6-142">會指出起始會話的使用者是否登入內部網路。</span><span class="sxs-lookup"><span data-stu-id="724e6-142">Indicates whether the user who initiated the session was logged on to the internal network.</span></span>  <br/> |
|<span data-ttu-id="724e6-143">**來源於與電話機整合的使用者**</span><span class="sxs-lookup"><span data-stu-id="724e6-143">**Is From user integrated with desk phone**</span></span> <br/> |<span data-ttu-id="724e6-144">會指出起始會話之使用者所使用的端點是否與他或她的桌面電話整合。</span><span class="sxs-lookup"><span data-stu-id="724e6-144">Indicates whether the endpoint used by the user who initiated the session is integrated with his or her desktop phone.</span></span>  <br/> |
|<span data-ttu-id="724e6-145">**會話優先順序**</span><span class="sxs-lookup"><span data-stu-id="724e6-145">**Session Priority**</span></span> <br/> |<span data-ttu-id="724e6-146">指派給會話的優先順序。</span><span class="sxs-lookup"><span data-stu-id="724e6-146">Priority assigned to the session.</span></span> <span data-ttu-id="724e6-147">有效的優先順序如下： Unknown;非緊急;一般緊迫和緊急。</span><span class="sxs-lookup"><span data-stu-id="724e6-147">Valid priorities are: Unknown; Non-Urgent; Normal; Urgent; and Emergency.</span></span>  <br/> |
|<span data-ttu-id="724e6-148">**回應碼**</span><span class="sxs-lookup"><span data-stu-id="724e6-148">**Response code**</span></span> <br/> |<span data-ttu-id="724e6-149">會話失敗時傳送的 SIP 回應碼。</span><span class="sxs-lookup"><span data-stu-id="724e6-149">SIP response code sent when the session failed.</span></span>  <br/> |
|<span data-ttu-id="724e6-150">**前端**</span><span class="sxs-lookup"><span data-stu-id="724e6-150">**Front end**</span></span> <br/> |<span data-ttu-id="724e6-151">會議中所使用的前端伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="724e6-151">Name of the Front End Server used in the conference.</span></span>  <br/> |
|<span data-ttu-id="724e6-152">**拍攝時間**</span><span class="sxs-lookup"><span data-stu-id="724e6-152">**Capture time**</span></span> <br/> |<span data-ttu-id="724e6-153">記錄會話資訊的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="724e6-153">Date and time that the session information was recorded.</span></span>  <br/> |
|<span data-ttu-id="724e6-154">**結束時間**</span><span class="sxs-lookup"><span data-stu-id="724e6-154">**End time**</span></span> <br/> |<span data-ttu-id="724e6-155">會話結束的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="724e6-155">Date and time the session ended.</span></span>  <br/> |
|<span data-ttu-id="724e6-156">**目標使用者**</span><span class="sxs-lookup"><span data-stu-id="724e6-156">**To user**</span></span> <br/> |<span data-ttu-id="724e6-157">獲邀加入會話之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="724e6-157">SIP address of the user who was invited to the session.</span></span>  <br/> |
|<span data-ttu-id="724e6-158">**至使用者代理程式**</span><span class="sxs-lookup"><span data-stu-id="724e6-158">**To user agent**</span></span> <br/> |<span data-ttu-id="724e6-159">受邀加入會話之使用者的端點所使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="724e6-159">Software used by the endpoint of the user who was invited to the session.</span></span>  <br/> |
|<span data-ttu-id="724e6-160">**是使用者內部使用者**</span><span class="sxs-lookup"><span data-stu-id="724e6-160">**Is To user internal**</span></span> <br/> |<span data-ttu-id="724e6-161">會指出被邀加入會話的使用者是否登入內部網路。</span><span class="sxs-lookup"><span data-stu-id="724e6-161">Indicates whether the user who was invited to the session was logged on to the internal network.</span></span>  <br/> |
|<span data-ttu-id="724e6-162">**是與電話機整合的使用者**</span><span class="sxs-lookup"><span data-stu-id="724e6-162">**Is To user integrated with desk phone**</span></span> <br/> |<span data-ttu-id="724e6-163">會指出受邀加入會話之使用者所使用的端點是否與他或她的桌面電話整合。</span><span class="sxs-lookup"><span data-stu-id="724e6-163">Indicates whether the endpoint used by the user who was invited to the session is integrated with his or her desktop phone.</span></span>  <br/> |
|<span data-ttu-id="724e6-164">**會重試會話**</span><span class="sxs-lookup"><span data-stu-id="724e6-164">**Is retried session**</span></span> <br/> |<span data-ttu-id="724e6-165">會指出會話是否嘗試重試先前失敗的會話。</span><span class="sxs-lookup"><span data-stu-id="724e6-165">Indicates whether the session is an attempt to retry a session that previously failed.</span></span>  <br/> |
|<span data-ttu-id="724e6-166">**診斷識別碼**</span><span class="sxs-lookup"><span data-stu-id="724e6-166">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="724e6-167">附加至 SIP 郵件（通常會在疑難排解錯誤中提供有用資訊) ）的表單中的唯一識別碼 (。</span><span class="sxs-lookup"><span data-stu-id="724e6-167">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span> <span data-ttu-id="724e6-168">將滑鼠停留在識別碼號碼上方，以查看有關該識別碼的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="724e6-168">Hold the mouse over the ID number to view additional information about that ID.</span></span>  <br/> |
   
## <a name="metrics-for-modalities"></a><span data-ttu-id="724e6-169">形式的計量</span><span class="sxs-lookup"><span data-stu-id="724e6-169">Metrics for Modalities</span></span>

<span data-ttu-id="724e6-170">下表列出每個會話模態的 Peer-to-Peer 會話詳細資料包告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="724e6-170">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session modality.</span></span>
  
<span data-ttu-id="724e6-171">**形式的計量**</span><span class="sxs-lookup"><span data-stu-id="724e6-171">**Metrics for Modalities**</span></span>

|<span data-ttu-id="724e6-172">**名稱**</span><span class="sxs-lookup"><span data-stu-id="724e6-172">**Name**</span></span>|<span data-ttu-id="724e6-173">**可以排序這個項目嗎？**</span><span class="sxs-lookup"><span data-stu-id="724e6-173">**Can you sort on this item?**</span></span>|<span data-ttu-id="724e6-174">**描述**</span><span class="sxs-lookup"><span data-stu-id="724e6-174">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="724e6-175">**方式**</span><span class="sxs-lookup"><span data-stu-id="724e6-175">**Modalities**</span></span> <br/> |<span data-ttu-id="724e6-176">否</span><span class="sxs-lookup"><span data-stu-id="724e6-176">No</span></span>  <br/> |<span data-ttu-id="724e6-177">會話中使用的形式。</span><span class="sxs-lookup"><span data-stu-id="724e6-177">Modalities used in the session.</span></span> <span data-ttu-id="724e6-178">例如，立即訊息 (IM) 或檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="724e6-178">For example, instant messaging (IM) or file transfer.</span></span>  <br/> |
|<span data-ttu-id="724e6-179">**從使用者郵件**</span><span class="sxs-lookup"><span data-stu-id="724e6-179">**From user messages**</span></span> <br/> |<span data-ttu-id="724e6-180">否</span><span class="sxs-lookup"><span data-stu-id="724e6-180">No</span></span>  <br/> |<span data-ttu-id="724e6-181">啟動會話之使用者所傳送的訊息數。</span><span class="sxs-lookup"><span data-stu-id="724e6-181">Number of messages sent by the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="724e6-182">**使用者訊息**</span><span class="sxs-lookup"><span data-stu-id="724e6-182">**To user messages**</span></span> <br/> |<span data-ttu-id="724e6-183">否</span><span class="sxs-lookup"><span data-stu-id="724e6-183">No</span></span>  <br/> |<span data-ttu-id="724e6-184">受邀加入會話之使用者所傳送的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="724e6-184">Number of messages sent by the user who was invited to join the session.</span></span>  <br/> |
   
## <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="724e6-185">診斷報告的計量</span><span class="sxs-lookup"><span data-stu-id="724e6-185">Metrics for Diagnostic Reports</span></span>

<span data-ttu-id="724e6-186">下表列出每個診斷報告的 Peer-to-Peer 會話詳細資料包告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="724e6-186">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each diagnostic report.</span></span>
  
<span data-ttu-id="724e6-187">**診斷報告的計量**</span><span class="sxs-lookup"><span data-stu-id="724e6-187">**Metrics for Diagnostic Reports**</span></span>

|<span data-ttu-id="724e6-188">**名稱**</span><span class="sxs-lookup"><span data-stu-id="724e6-188">**Name**</span></span>|<span data-ttu-id="724e6-189">**可以排序這個項目嗎？**</span><span class="sxs-lookup"><span data-stu-id="724e6-189">**Can you sort on this item?**</span></span>|<span data-ttu-id="724e6-190">**描述**</span><span class="sxs-lookup"><span data-stu-id="724e6-190">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="724e6-191">**Detail**</span><span class="sxs-lookup"><span data-stu-id="724e6-191">**Detail**</span></span> <br/> |<span data-ttu-id="724e6-192">否</span><span class="sxs-lookup"><span data-stu-id="724e6-192">No</span></span>  <br/> |<span data-ttu-id="724e6-193">當您按一下此專案時，報告會顯示會話的診斷報告。</span><span class="sxs-lookup"><span data-stu-id="724e6-193">When you click this item, the report shows the Diagnostic Report for the session.</span></span>  <br/> |
|<span data-ttu-id="724e6-194">**報告時間**</span><span class="sxs-lookup"><span data-stu-id="724e6-194">**Report time**</span></span> <br/> |<span data-ttu-id="724e6-195">否</span><span class="sxs-lookup"><span data-stu-id="724e6-195">No</span></span>  <br/> |<span data-ttu-id="724e6-196">報告的記錄日期與時間。</span><span class="sxs-lookup"><span data-stu-id="724e6-196">Date and time the report was recorded.</span></span>  <br/> |
|<span data-ttu-id="724e6-197">**請求**</span><span class="sxs-lookup"><span data-stu-id="724e6-197">**Request**</span></span> <br/> |<span data-ttu-id="724e6-198">否</span><span class="sxs-lookup"><span data-stu-id="724e6-198">No</span></span>  <br/> |<span data-ttu-id="724e6-199">SIP 要求類型。</span><span class="sxs-lookup"><span data-stu-id="724e6-199">SIP request type.</span></span> <span data-ttu-id="724e6-200">例如，INVITE 或再見。</span><span class="sxs-lookup"><span data-stu-id="724e6-200">For example, INVITE or BYE.</span></span>  <br/> |
|<span data-ttu-id="724e6-201">**診斷識別碼**</span><span class="sxs-lookup"><span data-stu-id="724e6-201">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="724e6-202">否</span><span class="sxs-lookup"><span data-stu-id="724e6-202">No</span></span>  <br/> |<span data-ttu-id="724e6-203">附加至 SIP 郵件（通常會在疑難排解錯誤中提供有用資訊) ）的表單中的唯一識別碼 (。</span><span class="sxs-lookup"><span data-stu-id="724e6-203">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="724e6-204">**內容類型**</span><span class="sxs-lookup"><span data-stu-id="724e6-204">**Content type**</span></span> <br/> |<span data-ttu-id="724e6-205">否</span><span class="sxs-lookup"><span data-stu-id="724e6-205">No</span></span>  <br/> |<span data-ttu-id="724e6-206">會議中所使用的媒體內容類型。</span><span class="sxs-lookup"><span data-stu-id="724e6-206">Type of media content used in the conference.</span></span> <span data-ttu-id="724e6-207">例如，常見的內容類型為 Application/sdp。</span><span class="sxs-lookup"><span data-stu-id="724e6-207">For example, a common content type is Application/sdp.</span></span> <span data-ttu-id="724e6-208">Session Description Protocol (SDP) 是標準的網際網路通訊協定，用來進行會話宣告、會話邀請及其他形式的多媒體會話初始。</span><span class="sxs-lookup"><span data-stu-id="724e6-208">Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span>  <br/> |
|<span data-ttu-id="724e6-209">**報告者**</span><span class="sxs-lookup"><span data-stu-id="724e6-209">**Reported by**</span></span> <br/> |<span data-ttu-id="724e6-210">否</span><span class="sxs-lookup"><span data-stu-id="724e6-210">No</span></span>  <br/> |<span data-ttu-id="724e6-211">電腦 (，也就是報告問題的用戶端或伺服器) 。</span><span class="sxs-lookup"><span data-stu-id="724e6-211">Computer (that is, client or server) that reported the problem.</span></span>  <br/> |
   

