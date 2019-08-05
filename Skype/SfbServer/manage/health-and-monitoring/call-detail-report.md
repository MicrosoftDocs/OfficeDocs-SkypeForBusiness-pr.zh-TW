---
title: 商務用 Skype Server 中的通話詳細資料包告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38862e35-3fec-41b9-a035-0b301942d446
description: '摘要: 瞭解商務用 Skype Server 中使用的通話詳細資料包告。'
ms.openlocfilehash: 8ced1a93f32f5f62ad33563e295ec456303232fc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191410"
---
# <a name="call-detail-report-in-skype-for-business-server"></a><span data-ttu-id="a2478-103">商務用 Skype Server 中的通話詳細資料包告</span><span class="sxs-lookup"><span data-stu-id="a2478-103">Call Detail Report in Skype for Business Server</span></span>
 
<span data-ttu-id="a2478-104">**摘要:** 瞭解商務用 Skype Server 中所用的通話詳細資料包告。</span><span class="sxs-lookup"><span data-stu-id="a2478-104">**Summary:** Learn about the Call Detail Report used in Skype for Business Server.</span></span>
  
<span data-ttu-id="a2478-105">[通話詳細資料] 報告提供個別通話的詳細資訊, 請參閱此報告包括幾乎所有的經驗指標及商務用 Skype Server 收集的統計資料, 分為幾個報表區段, 例如:</span><span class="sxs-lookup"><span data-stu-id="a2478-105">The Call Detail Report provides a detailed look at an individual call; the report includes nearly all the Quality of Experience metrics and statistics collected by Skype for Business Server, divided into report sections such as:</span></span>
  
- <span data-ttu-id="a2478-106">通話資訊</span><span class="sxs-lookup"><span data-stu-id="a2478-106">Call Information</span></span> 
    
- <span data-ttu-id="a2478-107">本機號碼裝置與信號規格</span><span class="sxs-lookup"><span data-stu-id="a2478-107">Caller Device and Signal Metrics</span></span>
    
- <span data-ttu-id="a2478-108">被呼叫裝置與信號規格</span><span class="sxs-lookup"><span data-stu-id="a2478-108">Callee Device and Signal metrics</span></span>
    
- <span data-ttu-id="a2478-109">來電者用戶端事件</span><span class="sxs-lookup"><span data-stu-id="a2478-109">Caller Client Event</span></span>
    
- <span data-ttu-id="a2478-110">被呼叫方用戶端事件</span><span class="sxs-lookup"><span data-stu-id="a2478-110">Callee Client Event</span></span>
    
- <span data-ttu-id="a2478-111">音訊資料流程 (來電者至被叫方)</span><span class="sxs-lookup"><span data-stu-id="a2478-111">Audio Stream (Caller to Callee)</span></span>
    
- <span data-ttu-id="a2478-112">影片資料流程 (來電者為被叫方)</span><span class="sxs-lookup"><span data-stu-id="a2478-112">Video Stream (Caller to Callee)</span></span>
    
- <span data-ttu-id="a2478-113">音訊資料流程 (被叫來電者)</span><span class="sxs-lookup"><span data-stu-id="a2478-113">Audio Stream (Callee to Caller)</span></span>
    
- <span data-ttu-id="a2478-114">影片串流 (被叫來電者)</span><span class="sxs-lookup"><span data-stu-id="a2478-114">Video Stream (Callee to Caller)</span></span>
    
<span data-ttu-id="a2478-115">請記住, 您在指定報告上看到的類別和度量單位, 取決於兩個專案: 會話類型和會話中使用的端點類型。</span><span class="sxs-lookup"><span data-stu-id="a2478-115">Keep in mind that the categories and the metrics you see on a given report depend on two things: the type of session and the type of endpoints used in the session.</span></span> <span data-ttu-id="a2478-116">例如, 音訊專用通話不會報告視頻資料流程的度量單位;這是因為通話沒有影片串流。</span><span class="sxs-lookup"><span data-stu-id="a2478-116">For example, an audio-only call will not report metrics for video streams; that's because the call didn't have a video stream.</span></span> <span data-ttu-id="a2478-117">同樣地, 您可能會有一個清單, 其中列出本機號碼, 但不會列出被叫方統計資料。</span><span class="sxs-lookup"><span data-stu-id="a2478-117">Likewise, you might have a report that lists caller statistics but not callee statistics.</span></span> <span data-ttu-id="a2478-118">這通常是因為被呼叫者不是使用與 SIP 相容的裝置。</span><span class="sxs-lookup"><span data-stu-id="a2478-118">That's typically because the callee was not using a SIP-compliant device.</span></span> <span data-ttu-id="a2478-119">端點負責在通話結束時報告統計資料;不過, 手機 (不知道 SIP 或 SIP 統計資料) 無法報告該類型的資訊。</span><span class="sxs-lookup"><span data-stu-id="a2478-119">Endpoints are responsible for reporting statistics at the end of a call; however, a cell phone (which knows nothing about SIP or SIP statistics) is unable to report that kind of information.</span></span> <span data-ttu-id="a2478-120">如果您打電話給某個人, 並在手機上接聽, 您就不會在通話結束時從該手機取得報告。</span><span class="sxs-lookup"><span data-stu-id="a2478-120">If you call someone and they answer you on their cell phone, you will not get a report from that cell phone when the call ends.</span></span>
  
<span data-ttu-id="a2478-121">當您嘗試判斷某個特定呼叫為何遇到媒體質量問題時, 通話詳細資料包告最實用。</span><span class="sxs-lookup"><span data-stu-id="a2478-121">The Call Detail Report is most useful when you are trying to determine exactly why a given call experienced media quality problems.</span></span>
  
## <a name="accessing-the-call-detail-report"></a><span data-ttu-id="a2478-122">存取通話詳細資料包告</span><span class="sxs-lookup"><span data-stu-id="a2478-122">Accessing the Call Detail Report</span></span>

<span data-ttu-id="a2478-123">您可以從下列任何一種報告存取通話詳細資料包告:</span><span class="sxs-lookup"><span data-stu-id="a2478-123">The Call Detail Report can be accessed from any of the following reports:</span></span>
  
- <span data-ttu-id="a2478-124">[商務用 Skype 伺服器 (location-report.md)] 中的 [位置報告] (按一下通話量或不佳的通話百分比指標)</span><span class="sxs-lookup"><span data-stu-id="a2478-124">The [Location Report in Skype for Business Server (location-report.md) (by clicking either the Call volume or the Poor call percentage metric)</span></span>
    
- <span data-ttu-id="a2478-125">[商務用 Skype 伺服器 (summary.md)] 中的 [媒體質量摘要] 報告 (透過按一下通話量或較差的通話百分比指標)</span><span class="sxs-lookup"><span data-stu-id="a2478-125">The [Media Quality Summary Report in Skype for Business Server (summary.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>
    
- <span data-ttu-id="a2478-126">[商務用 Skype server 中的媒體質量比較報告](comparison.md)(按一下商務用[skype server 中的 [通話清單] 報告](call-list-report-0.md), 然後按一下 [詳細資料規格])。</span><span class="sxs-lookup"><span data-stu-id="a2478-126">The [Media Quality Comparison Report in Skype for Business Server](comparison.md) (by clicking the [Call List Report in Skype for Business Server](call-list-report-0.md) and then clicking the Detail metric).</span></span>
    
- <span data-ttu-id="a2478-127">[商務用 Skype server 中的 [伺服器效能] 報告](server-performance.md)(按一下通話量或較差的通話百分比指標)</span><span class="sxs-lookup"><span data-stu-id="a2478-127">The [Server Performance Report in Skype for Business Server](server-performance.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>
    
- <span data-ttu-id="a2478-128">[商務用 Skype Server 中的通話清單報告](call-list-report-0.md)(按一下詳細資料度量)</span><span class="sxs-lookup"><span data-stu-id="a2478-128">The [Call List Report in Skype for Business Server](call-list-report-0.md) (by clicking the Detail metric)</span></span>
    
<span data-ttu-id="a2478-129">從 [通話明細] 報告中, 您可以按一下下列其中一個度量[單位, 以存取商務用 Skype Server 中的裝置報告](device-report.md):</span><span class="sxs-lookup"><span data-stu-id="a2478-129">From within the Call Detail Report you can access the [Device Report in Skype for Business Server](device-report.md) by clicking either of the following metrics:</span></span>
  
- <span data-ttu-id="a2478-130">捕獲裝置</span><span class="sxs-lookup"><span data-stu-id="a2478-130">Capture device</span></span>
    
- <span data-ttu-id="a2478-131">轉譯裝置</span><span class="sxs-lookup"><span data-stu-id="a2478-131">Render device</span></span>
    
<span data-ttu-id="a2478-132">您也可以按一下 A/V 邊緣伺服器規格, 以存取伺服器媒體質量趨勢報告。</span><span class="sxs-lookup"><span data-stu-id="a2478-132">You can also access the Server Media Quality Trend Report by clicking the A/V edge server metric.</span></span>
  
## <a name="making-the-best-use-of-the-call-detail-report"></a><span data-ttu-id="a2478-133">充分利用 [通話詳細資料] 報告</span><span class="sxs-lookup"><span data-stu-id="a2478-133">Making the Best Use of the Call Detail Report</span></span>

<span data-ttu-id="a2478-134">通話詳細資料包告通常包含超過250的指標, 包括麥克風時間戳記偏移、低 SNR 時間等專案, 以及靠近結束的迴響時間。</span><span class="sxs-lookup"><span data-stu-id="a2478-134">The Call Detail Report typically includes over 250 different metrics, including such items as Microphone timestamp drift, Low SNR time, and Near end to echo time.</span></span> <span data-ttu-id="a2478-135">如果您不記得這些指標的實際測量, 請試著將滑鼠放在公制標籤上;通常會出現工具提示, 描述該量度。</span><span class="sxs-lookup"><span data-stu-id="a2478-135">If you can't remember what all of these metrics actually measure, try holding your mouse over the metric label; often-times, a tooltip will appear describing that metric.</span></span>
  
<span data-ttu-id="a2478-136">如果您無法找到指標, 請在搜尋方塊中輸入 [公制] 標籤的一部分, 然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="a2478-136">If you have problems locating a metric, type part of the metric label in the search box, and then click **Find**.</span></span> <span data-ttu-id="a2478-137">例如, 如果您找不到低 SNR 時間度量, 請在搜尋方塊中輸入 SNR, 然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="a2478-137">For example, if you can't find the Low SNR time metric, type SNR in the search box, and then click **Find**.</span></span>
  
<span data-ttu-id="a2478-138">請注意, 報告只會追蹤通話的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a2478-138">Note that the report only tracks information about a call.</span></span> <span data-ttu-id="a2478-139">不會錄製通話本身。</span><span class="sxs-lookup"><span data-stu-id="a2478-139">The call itself is not recorded.</span></span>
  
## <a name="filters"></a><span data-ttu-id="a2478-140">濾鏡</span><span class="sxs-lookup"><span data-stu-id="a2478-140">Filters</span></span>

<span data-ttu-id="a2478-141">無。</span><span class="sxs-lookup"><span data-stu-id="a2478-141">None.</span></span> <span data-ttu-id="a2478-142">您無法篩選 [通話詳細資料] 報告。</span><span class="sxs-lookup"><span data-stu-id="a2478-142">You cannot filter the Call Detail Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="a2478-143">指標</span><span class="sxs-lookup"><span data-stu-id="a2478-143">Metrics</span></span>

<span data-ttu-id="a2478-144">下表列出每個通話的通話詳細資料包告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="a2478-144">The following table lists the information provided in the Call Detail Report for each call.</span></span>
  
<span data-ttu-id="a2478-145">**通話詳細資料包表度量單位**</span><span class="sxs-lookup"><span data-stu-id="a2478-145">**Call Detail Report Metrics**</span></span>

|<span data-ttu-id="a2478-146">**名稱**</span><span class="sxs-lookup"><span data-stu-id="a2478-146">**Name**</span></span>|<span data-ttu-id="a2478-147">**您可以針對此專案進行排序嗎？**</span><span class="sxs-lookup"><span data-stu-id="a2478-147">**Can you sort on this item?**</span></span>|<span data-ttu-id="a2478-148">**說明**</span><span class="sxs-lookup"><span data-stu-id="a2478-148">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a2478-149">**來電者 PAI**</span><span class="sxs-lookup"><span data-stu-id="a2478-149">**Caller PAI**</span></span> <br/> |<span data-ttu-id="a2478-150">不</span><span class="sxs-lookup"><span data-stu-id="a2478-150">No</span></span>  <br/> |<span data-ttu-id="a2478-151">P-已斷言-啟動通話之使用者的身分識別。</span><span class="sxs-lookup"><span data-stu-id="a2478-151">P-Asserted-Identity of the user who initiated the call.</span></span> <span data-ttu-id="a2478-152">P 斷言身分識別是用來傳達受信任網路中的使用者驗證身分識別。</span><span class="sxs-lookup"><span data-stu-id="a2478-152">The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span>  <br/> |
|<span data-ttu-id="a2478-153">**呼叫者 URI**</span><span class="sxs-lookup"><span data-stu-id="a2478-153">**Caller URI**</span></span> <br/> |<span data-ttu-id="a2478-154">不</span><span class="sxs-lookup"><span data-stu-id="a2478-154">No</span></span>  <br/> |<span data-ttu-id="a2478-155">啟動通話的使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="a2478-155">SIP address of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="a2478-156">**來電者端點**</span><span class="sxs-lookup"><span data-stu-id="a2478-156">**Caller endpoint**</span></span> <br/> |<span data-ttu-id="a2478-157">不</span><span class="sxs-lookup"><span data-stu-id="a2478-157">No</span></span>  <br/> |<span data-ttu-id="a2478-158">用來進行通話的裝置。</span><span class="sxs-lookup"><span data-stu-id="a2478-158">Device used to make the call.</span></span>  <br/> |
|<span data-ttu-id="a2478-159">**本機號碼使用者代理程式**</span><span class="sxs-lookup"><span data-stu-id="a2478-159">**Caller user agent**</span></span> <br/> |<span data-ttu-id="a2478-160">不</span><span class="sxs-lookup"><span data-stu-id="a2478-160">No</span></span>  <br/> |<span data-ttu-id="a2478-161">在進行通話的裝置上使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="a2478-161">Software used on the device that made the call.</span></span>  <br/> |
|<span data-ttu-id="a2478-162">**呼叫開始**</span><span class="sxs-lookup"><span data-stu-id="a2478-162">**Call start**</span></span> <br/> |<span data-ttu-id="a2478-163">不</span><span class="sxs-lookup"><span data-stu-id="a2478-163">No</span></span>  <br/> |<span data-ttu-id="a2478-164">開始撥打電話的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="a2478-164">Date and time that the call was initially placed.</span></span>  <br/> |
|<span data-ttu-id="a2478-165">**轉送伺服器旁路通話**</span><span class="sxs-lookup"><span data-stu-id="a2478-165">**Mediation Server bypass call**</span></span> <br/> |<span data-ttu-id="a2478-166">不</span><span class="sxs-lookup"><span data-stu-id="a2478-166">No</span></span>  <br/> |<span data-ttu-id="a2478-167">指示該呼叫是連線到 PSTN 語音閘道或合格的 IP-PBX, 而不傳遞到轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="a2478-167">Indicates whether the call connected to a PSTN voice gateway or qualified IP-PBX without passing through the Mediation Server.</span></span>  <br/> |
|<span data-ttu-id="a2478-168">**來電者 OS**</span><span class="sxs-lookup"><span data-stu-id="a2478-168">**Caller OS**</span></span> <br/> |<span data-ttu-id="a2478-169">不</span><span class="sxs-lookup"><span data-stu-id="a2478-169">No</span></span>  <br/> |<span data-ttu-id="a2478-170">來電者電腦的作業系統。</span><span class="sxs-lookup"><span data-stu-id="a2478-170">Operating system of the caller's computer.</span></span>  <br/> |
|<span data-ttu-id="a2478-171">**呼叫者 CPU**</span><span class="sxs-lookup"><span data-stu-id="a2478-171">**Caller CPU**</span></span> <br/> |<span data-ttu-id="a2478-172">不</span><span class="sxs-lookup"><span data-stu-id="a2478-172">No</span></span>  <br/> |<span data-ttu-id="a2478-173">啟動通話之使用者的電腦中安裝的 CPU。</span><span class="sxs-lookup"><span data-stu-id="a2478-173">CPU installed in the computer of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="a2478-174">**來電者 CPU 核心數**</span><span class="sxs-lookup"><span data-stu-id="a2478-174">**Caller CPU core number**</span></span> <br/> |<span data-ttu-id="a2478-175">不</span><span class="sxs-lookup"><span data-stu-id="a2478-175">No</span></span>  <br/> |<span data-ttu-id="a2478-176">啟動通話的人員所使用的電腦中的處理器號碼。</span><span class="sxs-lookup"><span data-stu-id="a2478-176">Processor number in the computer used by the person who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="a2478-177">**來電者 CPU 速度**</span><span class="sxs-lookup"><span data-stu-id="a2478-177">**Caller CPU speed**</span></span> <br/> |<span data-ttu-id="a2478-178">不</span><span class="sxs-lookup"><span data-stu-id="a2478-178">No</span></span>  <br/> |<span data-ttu-id="a2478-179">啟動通話之人員所使用之電腦 CPU 的時脈速度。</span><span class="sxs-lookup"><span data-stu-id="a2478-179">Clock speed of the CPU of the computer used by the person who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="a2478-180">**呼叫者 CPU 虛擬化**</span><span class="sxs-lookup"><span data-stu-id="a2478-180">**Caller CPU virtualization**</span></span> <br/> |<span data-ttu-id="a2478-181">不</span><span class="sxs-lookup"><span data-stu-id="a2478-181">No</span></span>  <br/> |<span data-ttu-id="a2478-182">啟動通話之人員所使用的電腦上使用的虛擬化 (如果有)。</span><span class="sxs-lookup"><span data-stu-id="a2478-182">Virtualization (if any) used on the computer used by the person who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="a2478-183">**被呼叫者 PAI**</span><span class="sxs-lookup"><span data-stu-id="a2478-183">**Callee PAI**</span></span> <br/> |<span data-ttu-id="a2478-184">不</span><span class="sxs-lookup"><span data-stu-id="a2478-184">No</span></span>  <br/> |<span data-ttu-id="a2478-185">P-宣稱-受邀加入通話的使用者身分識別。</span><span class="sxs-lookup"><span data-stu-id="a2478-185">P-Asserted-Identity of the user who was invited to join the call.</span></span> <span data-ttu-id="a2478-186">P 斷言身分識別是用來傳達受信任網路中的使用者驗證身分識別。</span><span class="sxs-lookup"><span data-stu-id="a2478-186">The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span>  <br/> |
|<span data-ttu-id="a2478-187">**被呼叫方 URI**</span><span class="sxs-lookup"><span data-stu-id="a2478-187">**Callee URI**</span></span> <br/> |<span data-ttu-id="a2478-188">不</span><span class="sxs-lookup"><span data-stu-id="a2478-188">No</span></span>  <br/> |<span data-ttu-id="a2478-189">呼叫的使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="a2478-189">SIP address of the user who was called.</span></span>  <br/> |
|<span data-ttu-id="a2478-190">**被呼叫方端點**</span><span class="sxs-lookup"><span data-stu-id="a2478-190">**Callee endpoint**</span></span> <br/> |<span data-ttu-id="a2478-191">不</span><span class="sxs-lookup"><span data-stu-id="a2478-191">No</span></span>  <br/> |<span data-ttu-id="a2478-192">用來接收通話的裝置。</span><span class="sxs-lookup"><span data-stu-id="a2478-192">Device used to receive the call.</span></span>  <br/> |
|<span data-ttu-id="a2478-193">**被呼叫使用者代理程式**</span><span class="sxs-lookup"><span data-stu-id="a2478-193">**Callee user agent**</span></span> <br/> |<span data-ttu-id="a2478-194">不</span><span class="sxs-lookup"><span data-stu-id="a2478-194">No</span></span>  <br/> |<span data-ttu-id="a2478-195">在已接聽通話的裝置上使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="a2478-195">Software used on the device that received the call.</span></span>  <br/> |
|<span data-ttu-id="a2478-196">**內**</span><span class="sxs-lookup"><span data-stu-id="a2478-196">**Duration**</span></span> <br/> |<span data-ttu-id="a2478-197">不</span><span class="sxs-lookup"><span data-stu-id="a2478-197">No</span></span>  <br/> |<span data-ttu-id="a2478-198">通話的時間長度。</span><span class="sxs-lookup"><span data-stu-id="a2478-198">Length of time for the call.</span></span>  <br/> |
|<span data-ttu-id="a2478-199">**[媒體旁路] 警告標誌**</span><span class="sxs-lookup"><span data-stu-id="a2478-199">**Media bypass warning flag**</span></span> <br/> |<span data-ttu-id="a2478-200">不</span><span class="sxs-lookup"><span data-stu-id="a2478-200">No</span></span>  <br/> |<span data-ttu-id="a2478-201">在已略過中繼伺服器時發出的警告。</span><span class="sxs-lookup"><span data-stu-id="a2478-201">Warning issued when the Mediation Server was bypassed.</span></span>  <br/> |
|<span data-ttu-id="a2478-202">**被呼叫者 OS**</span><span class="sxs-lookup"><span data-stu-id="a2478-202">**Callee OS**</span></span> <br/> |<span data-ttu-id="a2478-203">不</span><span class="sxs-lookup"><span data-stu-id="a2478-203">No</span></span>  <br/> |<span data-ttu-id="a2478-204">已呼叫的使用者的電腦作業系統。</span><span class="sxs-lookup"><span data-stu-id="a2478-204">Operating system of the computer for the user who was called.</span></span>  <br/> |
|<span data-ttu-id="a2478-205">**被呼叫方 CPU**</span><span class="sxs-lookup"><span data-stu-id="a2478-205">**Callee CPU**</span></span> <br/> |<span data-ttu-id="a2478-206">不</span><span class="sxs-lookup"><span data-stu-id="a2478-206">No</span></span>  <br/> |<span data-ttu-id="a2478-207">已在呼叫的使用者電腦上安裝 CPU。</span><span class="sxs-lookup"><span data-stu-id="a2478-207">CPU installed in the computer of the user who was called.</span></span>  <br/> |
|<span data-ttu-id="a2478-208">**被呼叫方核心電話號碼**</span><span class="sxs-lookup"><span data-stu-id="a2478-208">**Callee core number**</span></span> <br/> |<span data-ttu-id="a2478-209">不</span><span class="sxs-lookup"><span data-stu-id="a2478-209">No</span></span>  <br/> |<span data-ttu-id="a2478-210">呼叫者所使用的電腦中的處理器號碼。</span><span class="sxs-lookup"><span data-stu-id="a2478-210">Processor number in the computer used by the person who was called.</span></span>  <br/> |
|<span data-ttu-id="a2478-211">**被呼叫者的 CPU 速度**</span><span class="sxs-lookup"><span data-stu-id="a2478-211">**Callee CPU speed**</span></span> <br/> |<span data-ttu-id="a2478-212">不</span><span class="sxs-lookup"><span data-stu-id="a2478-212">No</span></span>  <br/> |<span data-ttu-id="a2478-213">呼叫者所使用之電腦 CPU 的時脈速度。</span><span class="sxs-lookup"><span data-stu-id="a2478-213">Clock speed of the CPU of the computer used by the person who was called.</span></span>  <br/> |
|<span data-ttu-id="a2478-214">**被佔用的 CPU 虛擬化**</span><span class="sxs-lookup"><span data-stu-id="a2478-214">**Callee CPU virtualization**</span></span> <br/> |<span data-ttu-id="a2478-215">不</span><span class="sxs-lookup"><span data-stu-id="a2478-215">No</span></span>  <br/> |<span data-ttu-id="a2478-216">在呼叫者所使用的電腦上使用的虛擬化 (如果有)。</span><span class="sxs-lookup"><span data-stu-id="a2478-216">Virtualization (if any) used on the computer used by the person who was called.</span></span>  <br/> |
   

