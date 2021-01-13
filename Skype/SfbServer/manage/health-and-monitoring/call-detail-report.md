---
title: 商務用 Skype Server 中的詳細通話報告
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
ms.assetid: 38862e35-3fec-41b9-a035-0b301942d446
description: 摘要：瞭解用在商務用 Skype Server 中的通話詳細資料包告。
ms.openlocfilehash: 9b02722c8dd872b5703d6b459c2cd48568e39f94
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826513"
---
# <a name="call-detail-report-in-skype-for-business-server"></a><span data-ttu-id="f367d-103">商務用 Skype Server 中的詳細通話報告</span><span class="sxs-lookup"><span data-stu-id="f367d-103">Call Detail Report in Skype for Business Server</span></span>
 
<span data-ttu-id="f367d-104">**摘要：** 深入瞭解商務用 Skype Server 中使用的詳細通話報告。</span><span class="sxs-lookup"><span data-stu-id="f367d-104">**Summary:** Learn about the Call Detail Report used in Skype for Business Server.</span></span>
  
<span data-ttu-id="f367d-105">[通話詳細資料包告] 提供個別通話的詳細資訊，請參閱報告中包含的所有經驗品質計量和商務用 Skype Server 收集的統計資料，劃分成報表區段，例如：</span><span class="sxs-lookup"><span data-stu-id="f367d-105">The Call Detail Report provides a detailed look at an individual call; the report includes nearly all the Quality of Experience metrics and statistics collected by Skype for Business Server, divided into report sections such as:</span></span>
  
- <span data-ttu-id="f367d-106">通話資訊</span><span class="sxs-lookup"><span data-stu-id="f367d-106">Call Information</span></span> 
    
- <span data-ttu-id="f367d-107">呼叫者裝置和訊號計量</span><span class="sxs-lookup"><span data-stu-id="f367d-107">Caller Device and Signal Metrics</span></span>
    
- <span data-ttu-id="f367d-108">被呼叫者裝置和訊號計量</span><span class="sxs-lookup"><span data-stu-id="f367d-108">Callee Device and Signal metrics</span></span>
    
- <span data-ttu-id="f367d-109">呼叫者用戶端事件</span><span class="sxs-lookup"><span data-stu-id="f367d-109">Caller Client Event</span></span>
    
- <span data-ttu-id="f367d-110">被呼叫者用戶端事件</span><span class="sxs-lookup"><span data-stu-id="f367d-110">Callee Client Event</span></span>
    
- <span data-ttu-id="f367d-111">音訊資料流 (呼叫者至被呼叫者)</span><span class="sxs-lookup"><span data-stu-id="f367d-111">Audio Stream (Caller to Callee)</span></span>
    
- <span data-ttu-id="f367d-112">視訊資料流 (呼叫者至被呼叫者)</span><span class="sxs-lookup"><span data-stu-id="f367d-112">Video Stream (Caller to Callee)</span></span>
    
- <span data-ttu-id="f367d-113">音訊資料流 (被呼叫者至呼叫者)</span><span class="sxs-lookup"><span data-stu-id="f367d-113">Audio Stream (Callee to Caller)</span></span>
    
- <span data-ttu-id="f367d-114">視訊資料流 (被呼叫者至呼叫者)</span><span class="sxs-lookup"><span data-stu-id="f367d-114">Video Stream (Callee to Caller)</span></span>
    
<span data-ttu-id="f367d-p101">請注意，在指定報告上所見的類別及計量取決於兩個因素：工作階段類型，以及工作階段中所使用的端點類型。例如，純音訊通話不會報告視訊資料流計量，這是因為該通話沒有視訊資料流。同樣地，報告可能會只列出呼叫者統計資料，而沒有被呼叫者統計資料。這通常是因為被呼叫者並非使用 SIP 相容的裝置。端點會負責在通話結束時報告統計資料；不過行動電話 (對 SIP 或 SIP 統計資料一無所悉) 就無法報告該類資訊。如果您與某人通話，而他們使用行動電話接聽，則通話結束時將無法從該行動電話取得報告。</span><span class="sxs-lookup"><span data-stu-id="f367d-p101">Keep in mind that the categories and the metrics you see on a given report depend on two things: the type of session and the type of endpoints used in the session. For example, an audio-only call will not report metrics for video streams; that's because the call didn't have a video stream. Likewise, you might have a report that lists caller statistics but not callee statistics. That's typically because the callee was not using a SIP-compliant device. Endpoints are responsible for reporting statistics at the end of a call; however, a cell phone (which knows nothing about SIP or SIP statistics) is unable to report that kind of information. If you call someone and they answer you on their cell phone, you will not get a report from that cell phone when the call ends.</span></span>
  
<span data-ttu-id="f367d-121">當您想確認指定通話為何發生媒體品質問題的確切原因時，[通話詳細資料報告] 最派得上用場。</span><span class="sxs-lookup"><span data-stu-id="f367d-121">The Call Detail Report is most useful when you are trying to determine exactly why a given call experienced media quality problems.</span></span>
  
## <a name="accessing-the-call-detail-report"></a><span data-ttu-id="f367d-122">存取通話詳細資料報告</span><span class="sxs-lookup"><span data-stu-id="f367d-122">Accessing the Call Detail Report</span></span>

<span data-ttu-id="f367d-123">您可從下列報告中存取 [通話詳細資料報告]：</span><span class="sxs-lookup"><span data-stu-id="f367d-123">The Call Detail Report can be accessed from any of the following reports:</span></span>
  
- <span data-ttu-id="f367d-124">[商務用 Skype 伺服器 (location-report.md 中的 [位置報告])  (按一下 [通話量] 或 [低通話百分比] 計量，) </span><span class="sxs-lookup"><span data-stu-id="f367d-124">The [Location Report in Skype for Business Server (location-report.md) (by clicking either the Call volume or the Poor call percentage metric)</span></span>
    
- <span data-ttu-id="f367d-125">[商務用 Skype Server 中的媒體質量摘要報告] (summary.md)  (按一下 [通話量] 或 [不良通話百分比] 度量，) </span><span class="sxs-lookup"><span data-stu-id="f367d-125">The [Media Quality Summary Report in Skype for Business Server (summary.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>
    
- <span data-ttu-id="f367d-126">商務用 Skype server 中的 [媒體質量比較報告](comparison.md) (按一下 [ [商務用 skype 伺服器中的通話清單報告](call-list-report-0.md) ]，然後按一下 [詳細資料] 度量) 。</span><span class="sxs-lookup"><span data-stu-id="f367d-126">The [Media Quality Comparison Report in Skype for Business Server](comparison.md) (by clicking the [Call List Report in Skype for Business Server](call-list-report-0.md) and then clicking the Detail metric).</span></span>
    
- <span data-ttu-id="f367d-127">[商務用 Skype server (中的伺服器效能報告](server-performance.md)，請按一下 [通話量] 或 [不良通話百分比] 度量值) </span><span class="sxs-lookup"><span data-stu-id="f367d-127">The [Server Performance Report in Skype for Business Server](server-performance.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>
    
- <span data-ttu-id="f367d-128">[商務用 Skype Server (中的通話清單報告](call-list-report-0.md)，請按一下詳細資料度量) </span><span class="sxs-lookup"><span data-stu-id="f367d-128">The [Call List Report in Skype for Business Server](call-list-report-0.md) (by clicking the Detail metric)</span></span>
    
<span data-ttu-id="f367d-129">從 [通話詳細資料包告] 中，按一下下列其中一個計量，即可存取 [商務用 Skype Server 中的裝置報告](device-report.md) ：</span><span class="sxs-lookup"><span data-stu-id="f367d-129">From within the Call Detail Report you can access the [Device Report in Skype for Business Server](device-report.md) by clicking either of the following metrics:</span></span>
  
- <span data-ttu-id="f367d-130">擷取裝置</span><span class="sxs-lookup"><span data-stu-id="f367d-130">Capture device</span></span>
    
- <span data-ttu-id="f367d-131">轉換裝置</span><span class="sxs-lookup"><span data-stu-id="f367d-131">Render device</span></span>
    
<span data-ttu-id="f367d-132">按一下 [A/V Edge Server] 計量也可存取 [伺服器媒體品質趨勢報告]。</span><span class="sxs-lookup"><span data-stu-id="f367d-132">You can also access the Server Media Quality Trend Report by clicking the A/V edge server metric.</span></span>
  
## <a name="making-the-best-use-of-the-call-detail-report"></a><span data-ttu-id="f367d-133">發揮通話詳細資料報告的最大效用</span><span class="sxs-lookup"><span data-stu-id="f367d-133">Making the Best Use of the Call Detail Report</span></span>

<span data-ttu-id="f367d-p102">[通話詳細資料報告] 通常涵蓋超過 250 個不同的計量，包括麥克風時間戳記漂移、低 SNR 時間及近端回音時間等項目。如果不記得這些計量實際上測量什麼，可嘗試將滑鼠移至計量標籤上，通常會顯示工具提示來說明該計量。</span><span class="sxs-lookup"><span data-stu-id="f367d-p102">The Call Detail Report typically includes over 250 different metrics, including such items as Microphone timestamp drift, Low SNR time, and Near end to echo time. If you can't remember what all of these metrics actually measure, try holding your mouse over the metric label; often-times, a tooltip will appear describing that metric.</span></span>
  
<span data-ttu-id="f367d-136">如果您找不到度量，請在搜尋方塊中輸入「度量」標籤的一部分，然後按一下 [ **尋找**]。</span><span class="sxs-lookup"><span data-stu-id="f367d-136">If you have problems locating a metric, type part of the metric label in the search box, and then click **Find**.</span></span> <span data-ttu-id="f367d-137">例如，如果您找不到 [低 SNR] 時間度量，請在搜尋方塊中輸入 SNR，然後按一下 [ **尋找**]。</span><span class="sxs-lookup"><span data-stu-id="f367d-137">For example, if you can't find the Low SNR time metric, type SNR in the search box, and then click **Find**.</span></span>
  
<span data-ttu-id="f367d-138">請注意，報告只追蹤通話的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f367d-138">Note that the report only tracks information about a call.</span></span> <span data-ttu-id="f367d-139">不會記錄通話本身。</span><span class="sxs-lookup"><span data-stu-id="f367d-139">The call itself is not recorded.</span></span>
  
## <a name="filters"></a><span data-ttu-id="f367d-140">篩選</span><span class="sxs-lookup"><span data-stu-id="f367d-140">Filters</span></span>

<span data-ttu-id="f367d-p105">無。您無法篩選詳細通話報告。</span><span class="sxs-lookup"><span data-stu-id="f367d-p105">None. You cannot filter the Call Detail Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="f367d-143">指標</span><span class="sxs-lookup"><span data-stu-id="f367d-143">Metrics</span></span>

<span data-ttu-id="f367d-144">下表列出每個通話的詳細通話報告。</span><span class="sxs-lookup"><span data-stu-id="f367d-144">The following table lists the information provided in the Call Detail Report for each call.</span></span>
  
<span data-ttu-id="f367d-145">**詳細通話報告計量**</span><span class="sxs-lookup"><span data-stu-id="f367d-145">**Call Detail Report Metrics**</span></span>

|<span data-ttu-id="f367d-146">**名稱**</span><span class="sxs-lookup"><span data-stu-id="f367d-146">**Name**</span></span>|<span data-ttu-id="f367d-147">**可以排序這個項目嗎？**</span><span class="sxs-lookup"><span data-stu-id="f367d-147">**Can you sort on this item?**</span></span>|<span data-ttu-id="f367d-148">**描述**</span><span class="sxs-lookup"><span data-stu-id="f367d-148">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f367d-149">**呼叫者 PAI**</span><span class="sxs-lookup"><span data-stu-id="f367d-149">**Caller PAI**</span></span> <br/> |<span data-ttu-id="f367d-150">否</span><span class="sxs-lookup"><span data-stu-id="f367d-150">No</span></span>  <br/> |<span data-ttu-id="f367d-p106">撥打通話之使用者的 P-Asserted-Identity。P-Asserted-Identity 可用來傳達信任網路中之使用者經驗證的身分識別。</span><span class="sxs-lookup"><span data-stu-id="f367d-p106">P-Asserted-Identity of the user who initiated the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span>  <br/> |
|<span data-ttu-id="f367d-153">**呼叫者 URI**</span><span class="sxs-lookup"><span data-stu-id="f367d-153">**Caller URI**</span></span> <br/> |<span data-ttu-id="f367d-154">否</span><span class="sxs-lookup"><span data-stu-id="f367d-154">No</span></span>  <br/> |<span data-ttu-id="f367d-155">撥打通話之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="f367d-155">SIP address of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="f367d-156">**呼叫者者端點**</span><span class="sxs-lookup"><span data-stu-id="f367d-156">**Caller endpoint**</span></span> <br/> |<span data-ttu-id="f367d-157">否</span><span class="sxs-lookup"><span data-stu-id="f367d-157">No</span></span>  <br/> |<span data-ttu-id="f367d-158">用來撥打通話的裝置。</span><span class="sxs-lookup"><span data-stu-id="f367d-158">Device used to make the call.</span></span>  <br/> |
|<span data-ttu-id="f367d-159">**呼叫者使用者代理程式**</span><span class="sxs-lookup"><span data-stu-id="f367d-159">**Caller user agent**</span></span> <br/> |<span data-ttu-id="f367d-160">否</span><span class="sxs-lookup"><span data-stu-id="f367d-160">No</span></span>  <br/> |<span data-ttu-id="f367d-161">撥打通話之裝置上所使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="f367d-161">Software used on the device that made the call.</span></span>  <br/> |
|<span data-ttu-id="f367d-162">**通話開始**</span><span class="sxs-lookup"><span data-stu-id="f367d-162">**Call start**</span></span> <br/> |<span data-ttu-id="f367d-163">否</span><span class="sxs-lookup"><span data-stu-id="f367d-163">No</span></span>  <br/> |<span data-ttu-id="f367d-164">啟動通話的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="f367d-164">Date and time that the call was initially placed.</span></span>  <br/> |
|<span data-ttu-id="f367d-165">**中繼伺服器旁路通話**</span><span class="sxs-lookup"><span data-stu-id="f367d-165">**Mediation Server bypass call**</span></span> <br/> |<span data-ttu-id="f367d-166">否</span><span class="sxs-lookup"><span data-stu-id="f367d-166">No</span></span>  <br/> |<span data-ttu-id="f367d-167">指出通話是連接至 PSTN 語音閘道或完整 IP-PBX，而未通過中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="f367d-167">Indicates whether the call connected to a PSTN voice gateway or qualified IP-PBX without passing through the Mediation Server.</span></span>  <br/> |
|<span data-ttu-id="f367d-168">**呼叫者 OS**</span><span class="sxs-lookup"><span data-stu-id="f367d-168">**Caller OS**</span></span> <br/> |<span data-ttu-id="f367d-169">否</span><span class="sxs-lookup"><span data-stu-id="f367d-169">No</span></span>  <br/> |<span data-ttu-id="f367d-170">呼叫者電腦的作業系統。</span><span class="sxs-lookup"><span data-stu-id="f367d-170">Operating system of the caller's computer.</span></span>  <br/> |
|<span data-ttu-id="f367d-171">**呼叫者 CPU**</span><span class="sxs-lookup"><span data-stu-id="f367d-171">**Caller CPU**</span></span> <br/> |<span data-ttu-id="f367d-172">否</span><span class="sxs-lookup"><span data-stu-id="f367d-172">No</span></span>  <br/> |<span data-ttu-id="f367d-173">安裝在啟動通話之使用者電腦上的 CPU。</span><span class="sxs-lookup"><span data-stu-id="f367d-173">CPU installed in the computer of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="f367d-174">**呼叫者 CPU 核心編號**</span><span class="sxs-lookup"><span data-stu-id="f367d-174">**Caller CPU core number**</span></span> <br/> |<span data-ttu-id="f367d-175">否</span><span class="sxs-lookup"><span data-stu-id="f367d-175">No</span></span>  <br/> |<span data-ttu-id="f367d-176">啟動通話者所使用電腦的處理器編號。</span><span class="sxs-lookup"><span data-stu-id="f367d-176">Processor number in the computer used by the person who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="f367d-177">**呼叫者 CPU 速度**</span><span class="sxs-lookup"><span data-stu-id="f367d-177">**Caller CPU speed**</span></span> <br/> |<span data-ttu-id="f367d-178">否</span><span class="sxs-lookup"><span data-stu-id="f367d-178">No</span></span>  <br/> |<span data-ttu-id="f367d-179">啟動通話者所使用電腦的 CPU 時脈速度。</span><span class="sxs-lookup"><span data-stu-id="f367d-179">Clock speed of the CPU of the computer used by the person who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="f367d-180">**呼叫者 CPU 模擬**</span><span class="sxs-lookup"><span data-stu-id="f367d-180">**Caller CPU virtualization**</span></span> <br/> |<span data-ttu-id="f367d-181">否</span><span class="sxs-lookup"><span data-stu-id="f367d-181">No</span></span>  <br/> |<span data-ttu-id="f367d-182">啟動通話者所使用電腦上的虛擬化 (若有的話)。</span><span class="sxs-lookup"><span data-stu-id="f367d-182">Virtualization (if any) used on the computer used by the person who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="f367d-183">**被呼叫者 PAI**</span><span class="sxs-lookup"><span data-stu-id="f367d-183">**Callee PAI**</span></span> <br/> |<span data-ttu-id="f367d-184">否</span><span class="sxs-lookup"><span data-stu-id="f367d-184">No</span></span>  <br/> |<span data-ttu-id="f367d-p107">受邀加入通話之使用者的 P-Asserted-Identity。P-Asserted-Identity 可用來傳達信任網路中之使用者經驗證的身分識別。</span><span class="sxs-lookup"><span data-stu-id="f367d-p107">P-Asserted-Identity of the user who was invited to join the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span>  <br/> |
|<span data-ttu-id="f367d-187">**被呼叫者 URI**</span><span class="sxs-lookup"><span data-stu-id="f367d-187">**Callee URI**</span></span> <br/> |<span data-ttu-id="f367d-188">否</span><span class="sxs-lookup"><span data-stu-id="f367d-188">No</span></span>  <br/> |<span data-ttu-id="f367d-189">被呼叫使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="f367d-189">SIP address of the user who was called.</span></span>  <br/> |
|<span data-ttu-id="f367d-190">**被呼叫者端點**</span><span class="sxs-lookup"><span data-stu-id="f367d-190">**Callee endpoint**</span></span> <br/> |<span data-ttu-id="f367d-191">否</span><span class="sxs-lookup"><span data-stu-id="f367d-191">No</span></span>  <br/> |<span data-ttu-id="f367d-192">用來接收通話的裝置。</span><span class="sxs-lookup"><span data-stu-id="f367d-192">Device used to receive the call.</span></span>  <br/> |
|<span data-ttu-id="f367d-193">**被呼叫者使用者代理程式**</span><span class="sxs-lookup"><span data-stu-id="f367d-193">**Callee user agent**</span></span> <br/> |<span data-ttu-id="f367d-194">否</span><span class="sxs-lookup"><span data-stu-id="f367d-194">No</span></span>  <br/> |<span data-ttu-id="f367d-195">接收通話之裝置上所使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="f367d-195">Software used on the device that received the call.</span></span>  <br/> |
|<span data-ttu-id="f367d-196">**Duration**</span><span class="sxs-lookup"><span data-stu-id="f367d-196">**Duration**</span></span> <br/> |<span data-ttu-id="f367d-197">否</span><span class="sxs-lookup"><span data-stu-id="f367d-197">No</span></span>  <br/> |<span data-ttu-id="f367d-198">通話時間長度。</span><span class="sxs-lookup"><span data-stu-id="f367d-198">Length of time for the call.</span></span>  <br/> |
|<span data-ttu-id="f367d-199">**媒體旁路警告旗標**</span><span class="sxs-lookup"><span data-stu-id="f367d-199">**Media bypass warning flag**</span></span> <br/> |<span data-ttu-id="f367d-200">否</span><span class="sxs-lookup"><span data-stu-id="f367d-200">No</span></span>  <br/> |<span data-ttu-id="f367d-201">略過中繼伺服器時發出的警告。</span><span class="sxs-lookup"><span data-stu-id="f367d-201">Warning issued when the Mediation Server was bypassed.</span></span>  <br/> |
|<span data-ttu-id="f367d-202">**被呼叫者 OS**</span><span class="sxs-lookup"><span data-stu-id="f367d-202">**Callee OS**</span></span> <br/> |<span data-ttu-id="f367d-203">否</span><span class="sxs-lookup"><span data-stu-id="f367d-203">No</span></span>  <br/> |<span data-ttu-id="f367d-204">被呼叫使用者的電腦作業系統。</span><span class="sxs-lookup"><span data-stu-id="f367d-204">Operating system of the computer for the user who was called.</span></span>  <br/> |
|<span data-ttu-id="f367d-205">**被呼叫者 CPU**</span><span class="sxs-lookup"><span data-stu-id="f367d-205">**Callee CPU**</span></span> <br/> |<span data-ttu-id="f367d-206">否</span><span class="sxs-lookup"><span data-stu-id="f367d-206">No</span></span>  <br/> |<span data-ttu-id="f367d-207">安裝在被呼叫使用者電腦上的 CPU。</span><span class="sxs-lookup"><span data-stu-id="f367d-207">CPU installed in the computer of the user who was called.</span></span>  <br/> |
|<span data-ttu-id="f367d-208">**被呼叫者核心編號**</span><span class="sxs-lookup"><span data-stu-id="f367d-208">**Callee core number**</span></span> <br/> |<span data-ttu-id="f367d-209">否</span><span class="sxs-lookup"><span data-stu-id="f367d-209">No</span></span>  <br/> |<span data-ttu-id="f367d-210">被呼叫者所使用電腦中的處理器編號。</span><span class="sxs-lookup"><span data-stu-id="f367d-210">Processor number in the computer used by the person who was called.</span></span>  <br/> |
|<span data-ttu-id="f367d-211">**被呼叫者 CPU 速度**</span><span class="sxs-lookup"><span data-stu-id="f367d-211">**Callee CPU speed**</span></span> <br/> |<span data-ttu-id="f367d-212">否</span><span class="sxs-lookup"><span data-stu-id="f367d-212">No</span></span>  <br/> |<span data-ttu-id="f367d-213">被呼叫者所使用電腦中的 CPU 時脈速度。</span><span class="sxs-lookup"><span data-stu-id="f367d-213">Clock speed of the CPU of the computer used by the person who was called.</span></span>  <br/> |
|<span data-ttu-id="f367d-214">**被呼叫者 CPU 虛擬**</span><span class="sxs-lookup"><span data-stu-id="f367d-214">**Callee CPU virtualization**</span></span> <br/> |<span data-ttu-id="f367d-215">否</span><span class="sxs-lookup"><span data-stu-id="f367d-215">No</span></span>  <br/> |<span data-ttu-id="f367d-216">被呼叫者所使用電腦上的虛擬化 (若有的話)。</span><span class="sxs-lookup"><span data-stu-id="f367d-216">Virtualization (if any) used on the computer used by the person who was called.</span></span>  <br/> |
   

