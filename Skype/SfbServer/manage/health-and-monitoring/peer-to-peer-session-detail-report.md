---
title: 商務用 Skype Server 中的點對點工作階段詳細資料包告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
description: '摘要: 瞭解商務用 Skype Server 中點對點工作階段詳細資料包告。'
ms.openlocfilehash: 768609c68e37eebf46c350009638b960066f9456
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188734"
---
# <a name="peer-to-peer-session-detail-report-in-skype-for-business-server"></a><span data-ttu-id="07ec2-103">商務用 Skype Server 中的點對點工作階段詳細資料包告</span><span class="sxs-lookup"><span data-stu-id="07ec2-103">Peer-to-Peer Session Detail Report in Skype for Business Server</span></span>
 
<span data-ttu-id="07ec2-104">**摘要:** 瞭解商務用 Skype Server 中的點對點工作階段詳細資料包告。</span><span class="sxs-lookup"><span data-stu-id="07ec2-104">**Summary:** Learn about the Peer-to-Peer Session Detail Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="07ec2-105">點對點工作階段詳細資料包告會傳回點對點工作階段的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="07ec2-105">The Peer-to-Peer Session Detail Report returns detailed information about a peer-to-peer session.</span></span> <span data-ttu-id="07ec2-106">例如, 如果您選取 [立即訊息] 會話, 報告就會告訴您會話中兩位使用者傳送的訊息數目。</span><span class="sxs-lookup"><span data-stu-id="07ec2-106">For example, if you select an instant messaging session, the report will tell you the number of messages sent by each of the two users in the session.</span></span>
  
## <a name="accessing-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="07ec2-107">存取點對點工作階段詳細資料包告</span><span class="sxs-lookup"><span data-stu-id="07ec2-107">Accessing the Peer-to-Peer Session Detail Report</span></span>

<span data-ttu-id="07ec2-108">您可以從下列任何報告存取點對點工作階段詳細資料包告 (所有這些報告都可以從 [監控報告] 首頁存取):</span><span class="sxs-lookup"><span data-stu-id="07ec2-108">The Peer-to-Peer Session Detail Report can be accessed from any of the following reports (all of which can be accessed from the Monitoring Reports home page):</span></span>
  
- <span data-ttu-id="07ec2-109">IP 電話清查報告</span><span class="sxs-lookup"><span data-stu-id="07ec2-109">IP Phone Inventory Report</span></span>
    
- <span data-ttu-id="07ec2-110">使用者活動報告</span><span class="sxs-lookup"><span data-stu-id="07ec2-110">User Activity Report</span></span>
    
- <span data-ttu-id="07ec2-111">通話許可控制報告</span><span class="sxs-lookup"><span data-stu-id="07ec2-111">Call Admission Control Report</span></span>
    
- <span data-ttu-id="07ec2-112">失敗清單報告</span><span class="sxs-lookup"><span data-stu-id="07ec2-112">Failure List Report</span></span> 
    
<span data-ttu-id="07ec2-113">從點對點工作階段詳細資料包告中, 您可以按一下診斷報告 (詳細資料) 規格,[在商務用 Skype 伺服器中存取診斷報告](diagnostic-report.md)。</span><span class="sxs-lookup"><span data-stu-id="07ec2-113">From within the Peer-to-Peer Session Detail Report you can access the [Diagnostic Report in Skype for Business Server](diagnostic-report.md) by clicking the Diagnostic Report (Details) metric.</span></span> <span data-ttu-id="07ec2-114">您也可以按一下以下兩個指標中的任何一個, 以存取 [熱門失敗] 報告:</span><span class="sxs-lookup"><span data-stu-id="07ec2-114">You can also access the Top Failures Report by clicking either of these two metrics:</span></span>
  
- <span data-ttu-id="07ec2-115">應對</span><span class="sxs-lookup"><span data-stu-id="07ec2-115">Response</span></span>
    
- <span data-ttu-id="07ec2-116">診斷識別碼</span><span class="sxs-lookup"><span data-stu-id="07ec2-116">Diagnostic ID</span></span>
    
## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="07ec2-117">充分運用點對點工作階段詳細資料包告</span><span class="sxs-lookup"><span data-stu-id="07ec2-117">Making the Best Use of the Peer-to-Peer session Detail Report</span></span>

<span data-ttu-id="07ec2-118">點對點工作階段詳細資料包告包含大量的度量單位, 而系統管理員可能不熟悉其中許多規格。</span><span class="sxs-lookup"><span data-stu-id="07ec2-118">The Peer-to-Peer Session Detail Report includes a large number of metrics, many of which might not be familiar to system administrators.</span></span> <span data-ttu-id="07ec2-119">不過, 通常只要將滑鼠放在公制標籤上, 就可以查看工具提示, 以提供該標準的簡短描述。</span><span class="sxs-lookup"><span data-stu-id="07ec2-119">Often-times, however, you can view a tooltip that offers a brief description of that metric simply by holding your mouse over the metric label.</span></span>
  
<span data-ttu-id="07ec2-120">請注意, 指定報告上顯示的實際度量單位將取決於您所選取的點對點工作階段類型。</span><span class="sxs-lookup"><span data-stu-id="07ec2-120">Note that the actual metrics shown on a given report will depend on the type of peer-to-peer session you selected.</span></span> <span data-ttu-id="07ec2-121">音訊/視頻會話會報告一組不同的度量值, 而不是立即訊息會話。</span><span class="sxs-lookup"><span data-stu-id="07ec2-121">An audio/video session will report a different set of metrics than an instant messaging session.</span></span>
  
<span data-ttu-id="07ec2-122">您也可以將滑鼠放在回應程式碼和診斷 ID 指標中, 以取得這些值的描述:</span><span class="sxs-lookup"><span data-stu-id="07ec2-122">You can also hold your mouse over the Response code and Diagnostic ID metrics in order to obtain a description of those values:</span></span>
  
## <a name="filters"></a><span data-ttu-id="07ec2-123">濾鏡</span><span class="sxs-lookup"><span data-stu-id="07ec2-123">Filters</span></span>

<span data-ttu-id="07ec2-124">無。</span><span class="sxs-lookup"><span data-stu-id="07ec2-124">None.</span></span> <span data-ttu-id="07ec2-125">您無法篩選點對點工作階段詳細資料包告。</span><span class="sxs-lookup"><span data-stu-id="07ec2-125">You cannot filter the Peer-to-Peer Session Detail Report.</span></span>
  
## <a name="session-information-metrics"></a><span data-ttu-id="07ec2-126">會話資訊度量單位</span><span class="sxs-lookup"><span data-stu-id="07ec2-126">Session Information Metrics</span></span>

<span data-ttu-id="07ec2-127">下表列出每個會話的點對點工作階段詳細資料包告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="07ec2-127">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session.</span></span>
  
<span data-ttu-id="07ec2-128">**會話資訊度量單位**</span><span class="sxs-lookup"><span data-stu-id="07ec2-128">**Session Information Metrics**</span></span>

|<span data-ttu-id="07ec2-129">**名稱**</span><span class="sxs-lookup"><span data-stu-id="07ec2-129">**Name**</span></span>|<span data-ttu-id="07ec2-130">**說明**</span><span class="sxs-lookup"><span data-stu-id="07ec2-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="07ec2-131">**池 FQDN**</span><span class="sxs-lookup"><span data-stu-id="07ec2-131">**Pool FQDN**</span></span> <br/> |<span data-ttu-id="07ec2-132">會話中所涉及的註冊機構池或邊緣伺服器的完整功能變數名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="07ec2-132">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server involved in the session.</span></span>  <br/> |
|<span data-ttu-id="07ec2-133">**邀請時間**</span><span class="sxs-lookup"><span data-stu-id="07ec2-133">**Invite time**</span></span> <br/> |<span data-ttu-id="07ec2-134">最初傳送會話邀請的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="07ec2-134">Date and time the session invitation was originally sent.</span></span>  <br/> |
|<span data-ttu-id="07ec2-135">**回應時間**</span><span class="sxs-lookup"><span data-stu-id="07ec2-135">**Response time**</span></span> <br/> |<span data-ttu-id="07ec2-136">收到邀請接受的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="07ec2-136">Date and time that the invitation acceptance was received.</span></span>  <br/> |
|<span data-ttu-id="07ec2-137">**從使用者**</span><span class="sxs-lookup"><span data-stu-id="07ec2-137">**From user**</span></span> <br/> |<span data-ttu-id="07ec2-138">啟動會話之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="07ec2-138">SIP address of the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="07ec2-139">**從使用者代理程式**</span><span class="sxs-lookup"><span data-stu-id="07ec2-139">**From user agent**</span></span> <br/> |<span data-ttu-id="07ec2-140">啟動會話之使用者的端點所使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="07ec2-140">Software used by the endpoint of the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="07ec2-141">**是來自使用者內部**</span><span class="sxs-lookup"><span data-stu-id="07ec2-141">**Is From user internal**</span></span> <br/> |<span data-ttu-id="07ec2-142">指出啟動會話的使用者是否已登入內部網路。</span><span class="sxs-lookup"><span data-stu-id="07ec2-142">Indicates whether the user who initiated the session was logged on to the internal network.</span></span>  <br/> |
|<span data-ttu-id="07ec2-143">**是來自與手機整合的使用者**</span><span class="sxs-lookup"><span data-stu-id="07ec2-143">**Is From user integrated with desk phone**</span></span> <br/> |<span data-ttu-id="07ec2-144">指出啟動會話的使用者所使用的端點是否與他或她的桌面電話整合。</span><span class="sxs-lookup"><span data-stu-id="07ec2-144">Indicates whether the endpoint used by the user who initiated the session is integrated with his or her desktop phone.</span></span>  <br/> |
|<span data-ttu-id="07ec2-145">**會話優先順序**</span><span class="sxs-lookup"><span data-stu-id="07ec2-145">**Session Priority**</span></span> <br/> |<span data-ttu-id="07ec2-146">指派給會話的優先順序。</span><span class="sxs-lookup"><span data-stu-id="07ec2-146">Priority assigned to the session.</span></span> <span data-ttu-id="07ec2-147">有效的優先順序為: 未知;非緊急;標準非常以及緊急情況。</span><span class="sxs-lookup"><span data-stu-id="07ec2-147">Valid priorities are: Unknown; Non-Urgent; Normal; Urgent; and Emergency.</span></span>  <br/> |
|<span data-ttu-id="07ec2-148">**回應代碼**</span><span class="sxs-lookup"><span data-stu-id="07ec2-148">**Response code**</span></span> <br/> |<span data-ttu-id="07ec2-149">在會話失敗時傳送 SIP 回應代碼。</span><span class="sxs-lookup"><span data-stu-id="07ec2-149">SIP response code sent when the session failed.</span></span>  <br/> |
|<span data-ttu-id="07ec2-150">**前端**</span><span class="sxs-lookup"><span data-stu-id="07ec2-150">**Front end**</span></span> <br/> |<span data-ttu-id="07ec2-151">在會議中使用的前端伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="07ec2-151">Name of the Front End Server used in the conference.</span></span>  <br/> |
|<span data-ttu-id="07ec2-152">**捕獲時間**</span><span class="sxs-lookup"><span data-stu-id="07ec2-152">**Capture time**</span></span> <br/> |<span data-ttu-id="07ec2-153">記錄會話資訊的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="07ec2-153">Date and time that the session information was recorded.</span></span>  <br/> |
|<span data-ttu-id="07ec2-154">**結束時間**</span><span class="sxs-lookup"><span data-stu-id="07ec2-154">**End time**</span></span> <br/> |<span data-ttu-id="07ec2-155">會話結束的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="07ec2-155">Date and time the session ended.</span></span>  <br/> |
|<span data-ttu-id="07ec2-156">**給使用者**</span><span class="sxs-lookup"><span data-stu-id="07ec2-156">**To user**</span></span> <br/> |<span data-ttu-id="07ec2-157">受邀者加入會話之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="07ec2-157">SIP address of the user who was invited to the session.</span></span>  <br/> |
|<span data-ttu-id="07ec2-158">**給使用者代理程式**</span><span class="sxs-lookup"><span data-stu-id="07ec2-158">**To user agent**</span></span> <br/> |<span data-ttu-id="07ec2-159">受邀者參與會話之使用者的端點所使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="07ec2-159">Software used by the endpoint of the user who was invited to the session.</span></span>  <br/> |
|<span data-ttu-id="07ec2-160">**是對使用者內部**</span><span class="sxs-lookup"><span data-stu-id="07ec2-160">**Is To user internal**</span></span> <br/> |<span data-ttu-id="07ec2-161">指出受邀加入會話的使用者是否已登入內部網路。</span><span class="sxs-lookup"><span data-stu-id="07ec2-161">Indicates whether the user who was invited to the session was logged on to the internal network.</span></span>  <br/> |
|<span data-ttu-id="07ec2-162">**是與手機整合的使用者**</span><span class="sxs-lookup"><span data-stu-id="07ec2-162">**Is To user integrated with desk phone**</span></span> <br/> |<span data-ttu-id="07ec2-163">表示受邀者加入會話的使用者所使用的端點是否與他或她的桌面電話整合。</span><span class="sxs-lookup"><span data-stu-id="07ec2-163">Indicates whether the endpoint used by the user who was invited to the session is integrated with his or her desktop phone.</span></span>  <br/> |
|<span data-ttu-id="07ec2-164">**[重試] 會話**</span><span class="sxs-lookup"><span data-stu-id="07ec2-164">**Is retried session**</span></span> <br/> |<span data-ttu-id="07ec2-165">指出會話是否嘗試重試先前失敗的會話。</span><span class="sxs-lookup"><span data-stu-id="07ec2-165">Indicates whether the session is an attempt to retry a session that previously failed.</span></span>  <br/> |
|<span data-ttu-id="07ec2-166">**診斷識別碼**</span><span class="sxs-lookup"><span data-stu-id="07ec2-166">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="07ec2-167">附加至 SIP 訊息的唯一識別碼 (ms diagnostics 標頭形式), 通常可在疑難排解錯誤中提供有用的資訊。</span><span class="sxs-lookup"><span data-stu-id="07ec2-167">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span> <span data-ttu-id="07ec2-168">將滑鼠停留在識別碼編號上方, 即可查看該識別碼的其他相關資訊。</span><span class="sxs-lookup"><span data-stu-id="07ec2-168">Hold the mouse over the ID number to view additional information about that ID.</span></span>  <br/> |
   
## <a name="metrics-for-modalities"></a><span data-ttu-id="07ec2-169">形式的度量單位</span><span class="sxs-lookup"><span data-stu-id="07ec2-169">Metrics for Modalities</span></span>

<span data-ttu-id="07ec2-170">下表列出每個會話模態的點對點工作階段詳細資料包告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="07ec2-170">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session modality.</span></span>
  
<span data-ttu-id="07ec2-171">**形式的度量單位**</span><span class="sxs-lookup"><span data-stu-id="07ec2-171">**Metrics for Modalities**</span></span>

|<span data-ttu-id="07ec2-172">**名稱**</span><span class="sxs-lookup"><span data-stu-id="07ec2-172">**Name**</span></span>|<span data-ttu-id="07ec2-173">**您可以針對此專案進行排序嗎？**</span><span class="sxs-lookup"><span data-stu-id="07ec2-173">**Can you sort on this item?**</span></span>|<span data-ttu-id="07ec2-174">**說明**</span><span class="sxs-lookup"><span data-stu-id="07ec2-174">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="07ec2-175">**形式**</span><span class="sxs-lookup"><span data-stu-id="07ec2-175">**Modalities**</span></span> <br/> |<span data-ttu-id="07ec2-176">不</span><span class="sxs-lookup"><span data-stu-id="07ec2-176">No</span></span>  <br/> |<span data-ttu-id="07ec2-177">在會話中使用的形式。</span><span class="sxs-lookup"><span data-stu-id="07ec2-177">Modalities used in the session.</span></span> <span data-ttu-id="07ec2-178">例如, 立即訊息 (IM) 或檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="07ec2-178">For example, instant messaging (IM) or file transfer.</span></span>  <br/> |
|<span data-ttu-id="07ec2-179">**從使用者郵件**</span><span class="sxs-lookup"><span data-stu-id="07ec2-179">**From user messages**</span></span> <br/> |<span data-ttu-id="07ec2-180">不</span><span class="sxs-lookup"><span data-stu-id="07ec2-180">No</span></span>  <br/> |<span data-ttu-id="07ec2-181">啟動會話的使用者所傳送的訊息數目。</span><span class="sxs-lookup"><span data-stu-id="07ec2-181">Number of messages sent by the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="07ec2-182">**給使用者訊息**</span><span class="sxs-lookup"><span data-stu-id="07ec2-182">**To user messages**</span></span> <br/> |<span data-ttu-id="07ec2-183">不</span><span class="sxs-lookup"><span data-stu-id="07ec2-183">No</span></span>  <br/> |<span data-ttu-id="07ec2-184">受邀加入會話的使用者所傳送的訊息數目。</span><span class="sxs-lookup"><span data-stu-id="07ec2-184">Number of messages sent by the user who was invited to join the session.</span></span>  <br/> |
   
## <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="07ec2-185">診斷報告的度量單位</span><span class="sxs-lookup"><span data-stu-id="07ec2-185">Metrics for Diagnostic Reports</span></span>

<span data-ttu-id="07ec2-186">下表列出每個診斷報告的點對點工作階段詳細資料包告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="07ec2-186">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each diagnostic report.</span></span>
  
<span data-ttu-id="07ec2-187">**診斷報告的度量單位**</span><span class="sxs-lookup"><span data-stu-id="07ec2-187">**Metrics for Diagnostic Reports**</span></span>

|<span data-ttu-id="07ec2-188">**名稱**</span><span class="sxs-lookup"><span data-stu-id="07ec2-188">**Name**</span></span>|<span data-ttu-id="07ec2-189">**您可以針對此專案進行排序嗎？**</span><span class="sxs-lookup"><span data-stu-id="07ec2-189">**Can you sort on this item?**</span></span>|<span data-ttu-id="07ec2-190">**說明**</span><span class="sxs-lookup"><span data-stu-id="07ec2-190">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="07ec2-191">**具體**</span><span class="sxs-lookup"><span data-stu-id="07ec2-191">**Detail**</span></span> <br/> |<span data-ttu-id="07ec2-192">不</span><span class="sxs-lookup"><span data-stu-id="07ec2-192">No</span></span>  <br/> |<span data-ttu-id="07ec2-193">當您按一下此專案時, 報告會顯示該會話的診斷報告。</span><span class="sxs-lookup"><span data-stu-id="07ec2-193">When you click this item, the report shows the Diagnostic Report for the session.</span></span>  <br/> |
|<span data-ttu-id="07ec2-194">**報告時間**</span><span class="sxs-lookup"><span data-stu-id="07ec2-194">**Report time**</span></span> <br/> |<span data-ttu-id="07ec2-195">不</span><span class="sxs-lookup"><span data-stu-id="07ec2-195">No</span></span>  <br/> |<span data-ttu-id="07ec2-196">記錄報告的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="07ec2-196">Date and time the report was recorded.</span></span>  <br/> |
|<span data-ttu-id="07ec2-197">**徵求**</span><span class="sxs-lookup"><span data-stu-id="07ec2-197">**Request**</span></span> <br/> |<span data-ttu-id="07ec2-198">不</span><span class="sxs-lookup"><span data-stu-id="07ec2-198">No</span></span>  <br/> |<span data-ttu-id="07ec2-199">SIP 要求類型。</span><span class="sxs-lookup"><span data-stu-id="07ec2-199">SIP request type.</span></span> <span data-ttu-id="07ec2-200">例如, [邀請] 或 [再見]。</span><span class="sxs-lookup"><span data-stu-id="07ec2-200">For example, INVITE or BYE.</span></span>  <br/> |
|<span data-ttu-id="07ec2-201">**診斷識別碼**</span><span class="sxs-lookup"><span data-stu-id="07ec2-201">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="07ec2-202">不</span><span class="sxs-lookup"><span data-stu-id="07ec2-202">No</span></span>  <br/> |<span data-ttu-id="07ec2-203">附加至 SIP 訊息的唯一識別碼 (ms diagnostics 標頭形式), 通常可在疑難排解錯誤中提供有用的資訊。</span><span class="sxs-lookup"><span data-stu-id="07ec2-203">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="07ec2-204">**內容類型**</span><span class="sxs-lookup"><span data-stu-id="07ec2-204">**Content type**</span></span> <br/> |<span data-ttu-id="07ec2-205">不</span><span class="sxs-lookup"><span data-stu-id="07ec2-205">No</span></span>  <br/> |<span data-ttu-id="07ec2-206">在會議中使用的媒體內容類型。</span><span class="sxs-lookup"><span data-stu-id="07ec2-206">Type of media content used in the conference.</span></span> <span data-ttu-id="07ec2-207">例如, 常見的內容類型是 Application/sdp。</span><span class="sxs-lookup"><span data-stu-id="07ec2-207">For example, a common content type is Application/sdp.</span></span> <span data-ttu-id="07ec2-208">會話描述通訊協定 (SDP) 是一種標準的網際網路通訊協定, 用於會話宣告、會話邀請以及其他多媒體會話啟動的形式。</span><span class="sxs-lookup"><span data-stu-id="07ec2-208">Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span>  <br/> |
|<span data-ttu-id="07ec2-209">**報告者**</span><span class="sxs-lookup"><span data-stu-id="07ec2-209">**Reported by**</span></span> <br/> |<span data-ttu-id="07ec2-210">不</span><span class="sxs-lookup"><span data-stu-id="07ec2-210">No</span></span>  <br/> |<span data-ttu-id="07ec2-211">報告問題的電腦 (即用戶端或伺服器)。</span><span class="sxs-lookup"><span data-stu-id="07ec2-211">Computer (that is, client or server) that reported the problem.</span></span>  <br/> |
   

