---
title: 通話品質儀表板（CQD）常見問題（FAQ）
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: 閱讀常見問題（FAQ），以及關於 Microsoft 團隊通話品質儀表板（CQD）的解答。
ms.openlocfilehash: 43dd0f85c21914320ff48c2e0aab82614670ff90
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372122"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a><span data-ttu-id="eaff6-103">通話品質儀表板（CQD）常見問題（FAQ）</span><span class="sxs-lookup"><span data-stu-id="eaff6-103">Call Quality Dashboard (CQD) Frequently asked questions (FAQ)</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="eaff6-104">常見問題集</span><span class="sxs-lookup"><span data-stu-id="eaff6-104">Frequently asked questions</span></span>

[<span data-ttu-id="eaff6-105">如果有一個或多個會議參與者的體驗不佳，CQD 會將呼叫標示為「良好」嗎？</span><span class="sxs-lookup"><span data-stu-id="eaff6-105">Why does CQD mark a call as "Good" if one or more meeting participants had a poor experience?</span></span>](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

<span data-ttu-id="eaff6-106">[為什麼在 [通話] 和 [使用者計數] 值中看到的0.2% 差異，以及如何取得最精確的磁片容量？](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)</span><span class="sxs-lookup"><span data-stu-id="eaff6-106">[Why do I see up to 0.2% difference in call and user count values on measures and how to get most accurate volumes? ](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)</span></span>

[<span data-ttu-id="eaff6-107">為什麼商務用 Skype 的 CQD 資料與來自團隊的 CQD 資料不同？</span><span class="sxs-lookup"><span data-stu-id="eaff6-107">Why is CQD data from Skype for Business different than CQD data from Teams? </span></span>](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[<span data-ttu-id="eaff6-108">為什麼在 CQD 中看不到 EUII？</span><span class="sxs-lookup"><span data-stu-id="eaff6-108">Why can't I see EUII in CQD?</span></span>](#why-cant-i-see-euii-in-cqd)

[<span data-ttu-id="eaff6-109">為什麼我只針對團隊進行篩選時，我會在 CQD 中看到商務用 Skype 資訊？</span><span class="sxs-lookup"><span data-stu-id="eaff6-109">Why am I seeing Skype for Business information in CQD when I've filtered for Teams only?</span></span>](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a><span data-ttu-id="eaff6-110">如果有一個或多個會議參與者的體驗不佳，CQD 會將呼叫標示為「良好」嗎？</span><span class="sxs-lookup"><span data-stu-id="eaff6-110">Why does CQD mark a call as "Good" if one or more meeting participants had a poor experience?</span></span>

<span data-ttu-id="eaff6-111">查看 CQD 用於[資料流程分類](stream-classification-in-call-quality-dashboard.md)的規則。</span><span class="sxs-lookup"><span data-stu-id="eaff6-111">Check out the rules CQD uses for [stream classification](stream-classification-in-call-quality-dashboard.md).</span></span>
 
<span data-ttu-id="eaff6-112">對於音訊資料流程而言，任何5個分類器（根據呼叫長度來計算）都可以在「良好」參數中使用。</span><span class="sxs-lookup"><span data-stu-id="eaff6-112">For audio streams, any of the 5 classifiers, which are calculated for the average based on the length of the call, could all be within "good" parameters.</span></span> <span data-ttu-id="eaff6-113">這並不表示使用者並未遇到音訊 drop、static 或問題所帶來的問題。</span><span class="sxs-lookup"><span data-stu-id="eaff6-113">It doesn't mean the users didn't experience something that contributed to an audio drop out, static, or glitch.</span></span> 

<span data-ttu-id="eaff6-114">若要判斷是否為網路問題，請查看會話平均值與最大值之間的差異。</span><span class="sxs-lookup"><span data-stu-id="eaff6-114">To determine if it was a network problem, look at the delta between the average values for the session and the max values.</span></span> <span data-ttu-id="eaff6-115">[最大值] 是會話期間檢測到和報告的最大值。</span><span class="sxs-lookup"><span data-stu-id="eaff6-115">Max values are the maximum detected and reported during the session.</span></span>
 
<span data-ttu-id="eaff6-116">以下是如何針對此情況進行疑難排解的範例。</span><span class="sxs-lookup"><span data-stu-id="eaff6-116">Here's an example of how to troubleshoot this situation.</span></span> <span data-ttu-id="eaff6-117">假設您在通話期間進行網路追蹤，並在前20分鐘內沒有遺失的資料包，但接著您有1.5 秒的資料包，然後就能取得其他通話的差距。</span><span class="sxs-lookup"><span data-stu-id="eaff6-117">Let's say you take a network trace during a call and the first 20 minutes there are no lost packets but then you have a gap of 1.5 seconds of packets and then good for the remainder of the call.</span></span> <span data-ttu-id="eaff6-118">即使在 Wireshark 追蹤 RTP 分析中，平均值也會 <10% （0.1）的資料包遺失。</span><span class="sxs-lookup"><span data-stu-id="eaff6-118">The average is going to be <10% (0.1) Packet loss even in a Wireshark trace RTP analysis.</span></span> <span data-ttu-id="eaff6-119">最大的資料包遺失是什麼？</span><span class="sxs-lookup"><span data-stu-id="eaff6-119">What was the Max Packet Loss?</span></span> <span data-ttu-id="eaff6-120">5秒期間中的1.5 秒是30% （0.3）。</span><span class="sxs-lookup"><span data-stu-id="eaff6-120">1.5 Seconds in a 5-second period would be 30% (0.3).</span></span> <span data-ttu-id="eaff6-121">在五個採樣期間內發生（也許可能是在採樣期間進行分割）嗎？</span><span class="sxs-lookup"><span data-stu-id="eaff6-121">Did that occur within the five second sampling period (maybe or it could be split over the sampling period)?</span></span>
 
<span data-ttu-id="eaff6-122">如果網路躍點數在平均和最大值中看起來很好，請查看其他遙測資料：</span><span class="sxs-lookup"><span data-stu-id="eaff6-122">If network metrics look good in the averages and max values, then look to other telemetry data:</span></span> 
- <span data-ttu-id="eaff6-123">檢查 CPU 不足的事件比率，看看檢測到的 CPU 資源是否不足，並導致品質不佳。</span><span class="sxs-lookup"><span data-stu-id="eaff6-123">Check CPU Insufficient Event Ratio to see if the detected CPU resources available were insufficient and caused poor quality.</span></span> 
- <span data-ttu-id="eaff6-124">音訊裝置是否為半雙工模式，以避免因麥克風與喇叭接近而導致的意見反應？</span><span class="sxs-lookup"><span data-stu-id="eaff6-124">Was the audio device in Half Duplex mode to prevent feedback due to microphones that are to close to speakers?</span></span> 
- <span data-ttu-id="eaff6-125">檢查 Device 半雙工 AEC 事件比率。</span><span class="sxs-lookup"><span data-stu-id="eaff6-125">Check the Device Half Duplex AEC Event Ratio.</span></span> <span data-ttu-id="eaff6-126">裝置 glitching 或麥克風 glitching 在插入中樞或塢站時出現噪音或靜電，而導致聲音或靜電無法使用：</span><span class="sxs-lookup"><span data-stu-id="eaff6-126">Was the device glitching or the microphone glitching introducing noise or static due to USB Audio Drop outs when plugged into a Hub or Docking Station:</span></span>  
- <span data-ttu-id="eaff6-127">檢查裝置是否有問題，以及麥克風的故障事件比率。</span><span class="sxs-lookup"><span data-stu-id="eaff6-127">Check the Device Glitches and Microphone glitches event ratios.</span></span> <span data-ttu-id="eaff6-128">裝置本身是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="eaff6-128">Was the device itself functioning properly?</span></span>  
- <span data-ttu-id="eaff6-129">檢查捕獲和轉譯裝置無法運作的事件比率。</span><span class="sxs-lookup"><span data-stu-id="eaff6-129">Check the Capture and Render Device Not Functioning Event Ratios.</span></span>


<span data-ttu-id="eaff6-130">如需有關 CQD 遙測中可用之維度與量值的詳細資訊，請參閱[通話品質儀表板中提供的尺寸與測量](dimensions-and-measures-available-in-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="eaff6-130">For more on dimensions and measures available in CQD telemetry, read [Dimensions and measurements available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>

<span data-ttu-id="eaff6-131">針對背景雜音，請檢查 [靜音事件比率]，以查看參與者已靜音的時間長度。</span><span class="sxs-lookup"><span data-stu-id="eaff6-131">For background noise, check mute event ratio to see the length of time participants were muted.</span></span>
 
<span data-ttu-id="eaff6-132">在 CQD 中建立詳細報表，並篩選會議 ID 以查看會議中的所有使用者和資料流程，並新增感興趣的欄位。</span><span class="sxs-lookup"><span data-stu-id="eaff6-132">Create detailed reports in CQD and filter on Meeting ID to look at all users and streams in a meeting and add the fields you are interested in.</span></span> <span data-ttu-id="eaff6-133">報告問題的使用者可能不是有問題的使用者。</span><span class="sxs-lookup"><span data-stu-id="eaff6-133">A user reporting the issue may not be the one that was having the issue.</span></span> <span data-ttu-id="eaff6-134">他們只是報告體驗。</span><span class="sxs-lookup"><span data-stu-id="eaff6-134">They are just reporting the experience.</span></span>
 
<span data-ttu-id="eaff6-135">遙測不一定要找出問題，但它可以協助您更好地瞭解在何處查看並告知您的決策。</span><span class="sxs-lookup"><span data-stu-id="eaff6-135">The telemetry will not necessarily call out the issue, but it can help you better understand where to look and inform your decisions.</span></span> <span data-ttu-id="eaff6-136">是網路、裝置、驅動程式或固件更新、使用方式或使用者嗎？</span><span class="sxs-lookup"><span data-stu-id="eaff6-136">Is it network, device, driver or firmware updates, usage, or user?</span></span>

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a><span data-ttu-id="eaff6-137">為什麼在 [通話] 和 [使用者計數] 值中看到的0.2% 差異，以及如何取得最精確的磁片容量？</span><span class="sxs-lookup"><span data-stu-id="eaff6-137">Why do I see up to 0.2% difference in call and user count values on measures and how to get most accurate volumes?</span></span> 
<span data-ttu-id="eaff6-138">若要計算通話計數和使用者計數測量，請針對資料集中的通話或使用者識別碼執行不同的 countif 操作。</span><span class="sxs-lookup"><span data-stu-id="eaff6-138">To compute call count and user count measures, a distinct countif operation is performed against the call or user identifiers in the data set.</span></span> <span data-ttu-id="eaff6-139">在大型資料集上，有多達0.2% 的錯誤是由 distinct countif 操作所固有的。</span><span class="sxs-lookup"><span data-stu-id="eaff6-139">On large data sets, there is an up to 0.2% error inherent with the distinct countif operation.</span></span> <span data-ttu-id="eaff6-140">若要取得最精確的容量，您應該依靠資料流程計數測量，因為它們不依賴這個不同的 countif 操作。</span><span class="sxs-lookup"><span data-stu-id="eaff6-140">For the most accurate volume, you should rely on stream count measures since they do not rely on this distinct countif operation.</span></span> <span data-ttu-id="eaff6-141">篩選以減少資料量可能會減少錯誤，但在不同的通話和使用者計數中可能不會消除此錯誤來源。</span><span class="sxs-lookup"><span data-stu-id="eaff6-141">Filtering to reduce the data volume may reduce the error but may not eliminate this source of error in distinct call and user counts.</span></span> <span data-ttu-id="eaff6-142">請參閱[通話品質儀表板中可](dimensions-and-measures-available-in-call-quality-dashboard.md)受影響之量值的尺寸與測量。</span><span class="sxs-lookup"><span data-stu-id="eaff6-142">Refer to [Dimensions and measurements available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md) for which measures are impacted.</span></span>


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a><span data-ttu-id="eaff6-143">為什麼商務用 Skype 的 CQD 資料與來自團隊的 CQD 資料不同？</span><span class="sxs-lookup"><span data-stu-id="eaff6-143">Why is CQD data from Skype for Business different than CQD data from Teams?</span></span> 


> [!IMPORTANT]
> <span data-ttu-id="eaff6-144">自2020年7月1日起，較舊的 CQD （CQD.lync.com）會使用最新 CQD （CQD 中的資料。Teams.microsoft.com）。</span><span class="sxs-lookup"><span data-stu-id="eaff6-144">As of July 1, 2020, the older CQD (CQD.lync.com) uses data from the latest CQD (CQD.Teams.microsoft.com).</span></span> <span data-ttu-id="eaff6-145">較舊的 CQD 資料已不再提供，而且您無法匯出您的建立或報表資料。</span><span class="sxs-lookup"><span data-stu-id="eaff6-145">The older CQD data is no longer available, and you can't export your building or report data.</span></span> <span data-ttu-id="eaff6-146">您仍然可以使用 CQD.lync.com （在商務用 Skype 系統管理中心提供），但我們會關閉 CQD.lync.com 的存取權，因此您應該移至 CQD。如果您尚未這麼做，請 Teams.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="eaff6-146">You can still use CQD.lync.com (available from the Skype for Business admin center), but we'll turn off access to CQD.lync.com soon, so you should move to CQD.Teams.microsoft.com if you haven't already done so.</span></span>


<span data-ttu-id="eaff6-147">如果您嘗試在舊版 CQD （cqd.lync.com）與來自團隊系統管理中心（cqd.teams.microsoft.com）的最新 CQD 之間進行比較，您會很快發現資料不相符。</span><span class="sxs-lookup"><span data-stu-id="eaff6-147">If you're trying to compare data between the older CQD from the Skype for Business legacy portal (cqd.lync.com) and the latest CQD from the Teams admin center (cqd.teams.microsoft.com), you'll quickly notice that the data doesn't match.</span></span> <span data-ttu-id="eaff6-148">這是因為最新的 CQD 會報告許多其他通話案例。</span><span class="sxs-lookup"><span data-stu-id="eaff6-148">That's because the latest CQD reports on many additional calling scenarios.</span></span> <span data-ttu-id="eaff6-149">如果您仍在使用較舊 CQD 的報告，請參閱這篇文章以協助您解讀這些報告： [[通話品質] 儀表板（適用于商務用 Skype Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard)）。</span><span class="sxs-lookup"><span data-stu-id="eaff6-149">If you're still using reports from the older CQD, use this article to help you interpret those reports: [Call Quality Dashboard for Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard).</span></span>


  
### <a name="why-cant-i-see-euii-in-cqd"></a><span data-ttu-id="eaff6-150">為什麼在 CQD 中看不到 EUII？</span><span class="sxs-lookup"><span data-stu-id="eaff6-150">Why can't I see EUII in CQD?</span></span>

<span data-ttu-id="eaff6-151">這些系統管理員角色可以存取 CQD，但他們無法查看 EUII （使用者可辨識的資訊）：</span><span class="sxs-lookup"><span data-stu-id="eaff6-151">These admin roles can access CQD, but they can't view EUII (end-user identifiable information):</span></span>
- <span data-ttu-id="eaff6-152">Microsoft 365 報告閱讀程式</span><span class="sxs-lookup"><span data-stu-id="eaff6-152">Microsoft 365 Reports Reader</span></span>
- <span data-ttu-id="eaff6-153">團隊溝通支援專家</span><span class="sxs-lookup"><span data-stu-id="eaff6-153">Teams Communications Support Specialist</span></span>

<span data-ttu-id="eaff6-154">若要深入瞭解可存取 CQD 的角色，包括 EUII 讀取[指派角色以存取 CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)。</span><span class="sxs-lookup"><span data-stu-id="eaff6-154">To learn more about roles that can access CQD - including EUII - read [Assign roles for accessing CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).</span></span>

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a><span data-ttu-id="eaff6-155">為什麼我只針對團隊進行篩選時，我會在 CQD 中看到商務用 Skype 資訊？</span><span class="sxs-lookup"><span data-stu-id="eaff6-155">Why am I seeing Skype for Business information in CQD when I've filtered for Teams only?</span></span>

<span data-ttu-id="eaff6-156">如果您只在 CQD 報表（isTeams = 1）中篩選團隊，則會針對*第一個端點*為團隊的所有呼叫進行篩選。</span><span class="sxs-lookup"><span data-stu-id="eaff6-156">When you filter for Teams only in CQD reports (isTeams = 1), you're filtering for all calls where the *first endpoint* is Teams.</span></span> <span data-ttu-id="eaff6-157">如果*第二個端點*是商務用 Skype，該資訊將會顯示在您的 CQD 報告中。</span><span class="sxs-lookup"><span data-stu-id="eaff6-157">If the *second endpoint* is Skype for Business, that information will show up in your CQD report.</span></span>

<span data-ttu-id="eaff6-158">CQDv2 和 CQDv3 的總計數會永遠不同，因為 CQDv3 將會有 CQDv2 沒有的新案例。</span><span class="sxs-lookup"><span data-stu-id="eaff6-158">CQDv2 and CQDv3 will always have different total counts since CQDv3 will have new scenarios that CQDv2 will not have.</span></span> <span data-ttu-id="eaff6-159">這就是比較摘要合計或匯總的全部數位不含篩選的原因，將會有這些預期的差異。</span><span class="sxs-lookup"><span data-stu-id="eaff6-159">That’s why comparing Summary Total or Aggregated all-up numbers with no filters will have these expected differences.</span></span>  

<span data-ttu-id="eaff6-160">根據客戶的案例，CQDv3 將會包含 SFB 2019 內部部署呼叫（如果 SFB 2019 與資料連線器搭配使用）、Skype Bot 通話（AA、CVI、VDI）、即時事件和 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="eaff6-160">Depending on Customers’ scenario, CQDv3 will include SFB 2019 on-premises calls (if SFB 2019 is used with a data connector), Skype Bot calls (AA, CVI, VDI), Live Events and PSTN calls.</span></span> <span data-ttu-id="eaff6-161">客戶可以使用的案例/功能，但其資料不會在 CQD V2 中。</span><span class="sxs-lookup"><span data-stu-id="eaff6-161">Scenarios/Features which are available for the customers, but their data are not in CQD V2.</span></span>

<span data-ttu-id="eaff6-162">例如，預期您的客戶和您會看到200000音訊資料流程，且 CQD V2 摘要報告中出現5000個錯誤。在 CQD V3 中，300000音訊資料流程與5500失敗（來自2019內部部署通話、CVI 通話、PSTN 呼叫等）。</span><span class="sxs-lookup"><span data-stu-id="eaff6-162">For instance, it is expected that your customers and you will see 200,000 audio streams, with 5000 failures in CQD V2 Summary Report; versus 300,000 audio streams with 5500 failures (coming from 2019 on-prem calls, CVI calls, PSTN calls etc) in CQD V3.</span></span>

<span data-ttu-id="eaff6-163">若要判斷是否有任何意外的差異，您必須查看整體資料的各種細目。</span><span class="sxs-lookup"><span data-stu-id="eaff6-163">In order to determine, if there are any unexpected differences, you must look at various breakdowns of the overall data.</span></span>  <span data-ttu-id="eaff6-164">比較與意向。</span><span class="sxs-lookup"><span data-stu-id="eaff6-164">Compare with intent.</span></span>  <span data-ttu-id="eaff6-165">依使用者代理類別組對資料進行切分是我們建議的第一件事。</span><span class="sxs-lookup"><span data-stu-id="eaff6-165">Slicing the data by User Agent Category Pair is one of the first things we recommend.</span></span>  <span data-ttu-id="eaff6-166">*第一個產品*和*第二個產品*也是良好的交叉分析篩選器。</span><span class="sxs-lookup"><span data-stu-id="eaff6-166">*First Product* and *Second Product* are also good slicers.</span></span>  


## <a name="related-topics"></a><span data-ttu-id="eaff6-167">相關主題</span><span class="sxs-lookup"><span data-stu-id="eaff6-167">Related topics</span></span>

[<span data-ttu-id="eaff6-168">改善及監視團隊的通話品質</span><span class="sxs-lookup"><span data-stu-id="eaff6-168">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="eaff6-169">什麼是 CQD？</span><span class="sxs-lookup"><span data-stu-id="eaff6-169">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="eaff6-170">設定通話品質儀表板（CQD）</span><span class="sxs-lookup"><span data-stu-id="eaff6-170">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="eaff6-171">上傳租使用者及組建資料</span><span class="sxs-lookup"><span data-stu-id="eaff6-171">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="eaff6-172">CQD 資料和報表</span><span class="sxs-lookup"><span data-stu-id="eaff6-172">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="eaff6-173">使用 CQD 管理通話與會議品質</span><span class="sxs-lookup"><span data-stu-id="eaff6-173">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="eaff6-174">CQD 中可用的維度與量值</span><span class="sxs-lookup"><span data-stu-id="eaff6-174">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="eaff6-175">CQD 中的資料流程分類</span><span class="sxs-lookup"><span data-stu-id="eaff6-175">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="eaff6-176">使用 Power BI 來分析 CQD 資料</span><span class="sxs-lookup"><span data-stu-id="eaff6-176">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)

[<span data-ttu-id="eaff6-177">Teams 疑難排解</span><span class="sxs-lookup"><span data-stu-id="eaff6-177">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)