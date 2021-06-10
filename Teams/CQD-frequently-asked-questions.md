---
title: '通話品質儀表板 (CQD) 常見問題 (常見問題) '
ms.author: serdars
author: SerdarSoysal
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
description: 閱讀常見問題 (常見問題) 常見問題Microsoft Teams通話品質儀表板 (CQD) 。
ms.openlocfilehash: ad718df893b69b333dd63d224663238879fda8c7
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/02/2021
ms.locfileid: "52718004"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a><span data-ttu-id="76d18-103">通話品質儀表板 (CQD) 常見問題 (常見問題) </span><span class="sxs-lookup"><span data-stu-id="76d18-103">Call Quality Dashboard (CQD) Frequently asked questions (FAQ)</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="76d18-104">常見問題集</span><span class="sxs-lookup"><span data-stu-id="76d18-104">Frequently asked questions</span></span>

[<span data-ttu-id="76d18-105">如果一或多個會議參與者體驗不佳，CQD 為何將通話標記為「良好」？</span><span class="sxs-lookup"><span data-stu-id="76d18-105">Why does CQD mark a call as "Good" if one or more meeting participants had a poor experience?</span></span>](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[<span data-ttu-id="76d18-106">為什麼我在量值上看到最多 0.2% 的通話和使用者計數值差異，以及如何取得最準確的音量？ </span><span class="sxs-lookup"><span data-stu-id="76d18-106">Why do I see up to 0.2% difference in call and user count values on measures and how to get most accurate volumes? </span></span>](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[<span data-ttu-id="76d18-107">為什麼來自 商務用 Skype 的 CQD 資料商務用 Skype與 CQD 資料Teams？</span><span class="sxs-lookup"><span data-stu-id="76d18-107">Why is CQD data from Skype for Business different than CQD data from Teams? </span></span>](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[<span data-ttu-id="76d18-108">為什麼我在 CQD 中看不到 EUII？</span><span class="sxs-lookup"><span data-stu-id="76d18-108">Why can't I see EUII in CQD?</span></span>](#why-cant-i-see-euii-in-cqd)

[<span data-ttu-id="76d18-109">當我只篩選商務用 Skype時，為什麼在 CQD 中Teams資訊？</span><span class="sxs-lookup"><span data-stu-id="76d18-109">Why am I seeing Skype for Business information in CQD when I've filtered for Teams only?</span></span>](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[<span data-ttu-id="76d18-110">為什麼我的自訂報表最多隻會返回 10，000 列，當我知道應該有更多的專案時？</span><span class="sxs-lookup"><span data-stu-id="76d18-110">Why do my custom reports only return a maximum of 10,000 rows when I know there should be more entries?</span></span>](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

[<span data-ttu-id="76d18-111">為什麼 WiFi VPN 連接會顯示為有線而非 WiFi？</span><span class="sxs-lookup"><span data-stu-id="76d18-111">Why do WiFi VPN connections show as Wired instead of WiFi?</span></span>](#why-do-wifi-vpn-connections-show-as-wired-instead-of-wifi)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a><span data-ttu-id="76d18-112">如果一或多個會議參與者體驗不佳，CQD 為何將通話標記為「良好」？</span><span class="sxs-lookup"><span data-stu-id="76d18-112">Why does CQD mark a call as "Good" if one or more meeting participants had a poor experience?</span></span>

<span data-ttu-id="76d18-113">請查看 CQD 用於資料流程分類 [的規則](stream-classification-in-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="76d18-113">Check out the rules CQD uses for [stream classification](stream-classification-in-call-quality-dashboard.md).</span></span>
 
<span data-ttu-id="76d18-114">對於音訊流，根據通話長度計算平均值的五個分類器之任何一個，可能都位於「良好」參數內。</span><span class="sxs-lookup"><span data-stu-id="76d18-114">For audio streams, any of the five classifiers, which are calculated for the average based on the length of the call, could all be within "good" parameters.</span></span> <span data-ttu-id="76d18-115">這不表示使用者沒有遇到導致音訊輸出、靜態或干擾的問題。</span><span class="sxs-lookup"><span data-stu-id="76d18-115">It doesn't mean the users didn't experience something that contributed to an audio drop out, static, or glitch.</span></span> 

<span data-ttu-id="76d18-116">若要判斷它是網路問題，請看看會話的平均值與最大值之間的增量。</span><span class="sxs-lookup"><span data-stu-id="76d18-116">To determine if it was a network problem, look at the delta between the average values for the session and the max values.</span></span> <span data-ttu-id="76d18-117">最大值是會話期間偵測及報告的最大值。</span><span class="sxs-lookup"><span data-stu-id="76d18-117">Max values are the maximum detected and reported during the session.</span></span>
 
<span data-ttu-id="76d18-118">以下是如何針對此情況進行疑難排解的範例。</span><span class="sxs-lookup"><span data-stu-id="76d18-118">Here's an example of how to troubleshoot this situation.</span></span> <span data-ttu-id="76d18-119">假設您在通話期間進行網路追蹤，且前 20 分鐘沒有遺失封包，但封包的間隔為 1.5 秒，然後適用于通話的其餘部分。</span><span class="sxs-lookup"><span data-stu-id="76d18-119">Let's say you take a network trace during a call and the first 20 minutes there are no lost packets but then you have a gap of 1.5 seconds of packets and then good for the remainder of the call.</span></span> <span data-ttu-id="76d18-120">即使 Wireshark 追蹤 RTP 分析<封包 (0.1，平均) 10%。</span><span class="sxs-lookup"><span data-stu-id="76d18-120">The average is going to be <10% (0.1) Packet loss even in a Wireshark trace RTP analysis.</span></span> <span data-ttu-id="76d18-121">什麼是最大封包遺失？</span><span class="sxs-lookup"><span data-stu-id="76d18-121">What was the Max Packet Loss?</span></span> <span data-ttu-id="76d18-122">5 秒期間 1.5 秒為 30%， (0.3 秒) 。</span><span class="sxs-lookup"><span data-stu-id="76d18-122">1.5 Seconds in a 5-second period would be 30% (0.3).</span></span> <span data-ttu-id="76d18-123">這是否發生在 5 秒的抽樣期間 (或可能分割為 5 秒的) ？</span><span class="sxs-lookup"><span data-stu-id="76d18-123">Did that occur within the 5-second sampling period (maybe or it could be split over the sampling period)?</span></span>
 
<span data-ttu-id="76d18-124">如果網路度量在平均值和最大值中看起來不錯，請尋找其他遙測資料：</span><span class="sxs-lookup"><span data-stu-id="76d18-124">If network metrics look good in the averages and max values, then look to other telemetry data:</span></span> 
- <span data-ttu-id="76d18-125">檢查 CPU 不足事件比，查看偵測到的可用 CPU 資源是否不足，並造成品質不佳。</span><span class="sxs-lookup"><span data-stu-id="76d18-125">Check CPU Insufficient Event Ratio to see if the detected CPU resources available were insufficient and caused poor quality.</span></span> 
- <span data-ttu-id="76d18-126">音訊裝置是否以半雙面模式防止麥克風接近喇叭而收到意見回饋？</span><span class="sxs-lookup"><span data-stu-id="76d18-126">Was the audio device in Half Duplex mode to prevent feedback due to microphones that are to close to speakers?</span></span> 
- <span data-ttu-id="76d18-127">檢查裝置半雙面 AEC 事件比。</span><span class="sxs-lookup"><span data-stu-id="76d18-127">Check the Device Half Duplex AEC Event Ratio.</span></span> <span data-ttu-id="76d18-128">當插入集線器或固定座時，裝置是否因為 USB 音訊輸出而產生雜訊或靜態問題？。</span><span class="sxs-lookup"><span data-stu-id="76d18-128">Was the device glitching or the microphone glitching introducing noise or static due to USB Audio Drop outs when plugged into a Hub or Docking Station?</span></span>  
- <span data-ttu-id="76d18-129">檢查裝置故障和麥克風問題事件比。</span><span class="sxs-lookup"><span data-stu-id="76d18-129">Check the Device Glitches and Microphone glitches event ratios.</span></span> <span data-ttu-id="76d18-130">裝置本身是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="76d18-130">Was the device itself functioning properly?</span></span>  
- <span data-ttu-id="76d18-131">檢查捕獲和呈現裝置無法運作的事件比率。</span><span class="sxs-lookup"><span data-stu-id="76d18-131">Check the Capture and Render Device Not Functioning Event Ratios.</span></span>


<span data-ttu-id="76d18-132">如要進一步瞭解 CQD 遙測中可用的維度和量值，請參閱通話品質儀表板中可用的維度 [和度量](dimensions-and-measures-available-in-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="76d18-132">For more on dimensions and measures available in CQD telemetry, read [Dimensions and measurements available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>

<span data-ttu-id="76d18-133">針對背景雜訊，請檢查靜音事件比，以查看參與者靜音的時間長度。</span><span class="sxs-lookup"><span data-stu-id="76d18-133">For background noise, check mute event ratio to see the length of time participants were muted.</span></span>
 
<span data-ttu-id="76d18-134">在 CQD 中建立詳細報告，並篩選會議 ID，查看會議中的所有使用者和資料流程，並新增您感興趣的欄位。</span><span class="sxs-lookup"><span data-stu-id="76d18-134">Create detailed reports in CQD and filter on Meeting ID to look at all users and streams in a meeting and add the fields you are interested in.</span></span> <span data-ttu-id="76d18-135">報告問題的使用者可能沒有問題。</span><span class="sxs-lookup"><span data-stu-id="76d18-135">A user reporting the issue may not be the one that was having the issue.</span></span> <span data-ttu-id="76d18-136">他們只是報告體驗。</span><span class="sxs-lookup"><span data-stu-id="76d18-136">They are just reporting the experience.</span></span>
 
<span data-ttu-id="76d18-137">遙測不一定會說明問題，但可協助您進一步瞭解在何處尋找，並告知您的決策。</span><span class="sxs-lookup"><span data-stu-id="76d18-137">The telemetry will not necessarily call out the issue, but it can help you better understand where to look and inform your decisions.</span></span> <span data-ttu-id="76d18-138">它是網路、裝置、驅動程式或固件更新、使用方式或使用者？</span><span class="sxs-lookup"><span data-stu-id="76d18-138">Is it network, device, driver or firmware updates, usage, or user?</span></span>

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a><span data-ttu-id="76d18-139">為什麼我在量值上看到最多 0.2% 的通話和使用者計數值差異，以及如何取得最準確的音量？</span><span class="sxs-lookup"><span data-stu-id="76d18-139">Why do I see up to 0.2% difference in call and user count values on measures and how to get most accurate volumes?</span></span> 
<span data-ttu-id="76d18-140">若要計算通話計數和使用者計數測量，會針對資料集中的通話或使用者識別碼執行不同的計數運算。</span><span class="sxs-lookup"><span data-stu-id="76d18-140">To compute call count and user count measures, a distinct countif operation is performed against the call or user identifiers in the data set.</span></span> <span data-ttu-id="76d18-141">在大型資料集上，不同 countif 運算所固有的誤差最高為 0.2%。</span><span class="sxs-lookup"><span data-stu-id="76d18-141">On large data sets, there is an up to 0.2% error inherent with the distinct countif operation.</span></span> <span data-ttu-id="76d18-142">針對最精確的音量，您應該仰賴資料流程計數量詞，因為它們不仰賴這個不同的 countif 運算。</span><span class="sxs-lookup"><span data-stu-id="76d18-142">For the most accurate volume, you should rely on stream count measures since they do not rely on this distinct countif operation.</span></span> <span data-ttu-id="76d18-143">篩選以降低資料量可能會減少錯誤，但可能無法排除不同通話和使用者計數中的錯誤來源。</span><span class="sxs-lookup"><span data-stu-id="76d18-143">Filtering to reduce the data volume may reduce the error but may not eliminate this source of error in distinct call and user counts.</span></span> <span data-ttu-id="76d18-144">請參閱 [通話品質儀表板](dimensions-and-measures-available-in-call-quality-dashboard.md) 中可用的維度和度量，其中量值會受到影響。</span><span class="sxs-lookup"><span data-stu-id="76d18-144">Refer to [Dimensions and measurements available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md) for which measures are impacted.</span></span>


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a><span data-ttu-id="76d18-145">為什麼來自 商務用 Skype 的 CQD 資料商務用 Skype與 CQD 資料Teams？</span><span class="sxs-lookup"><span data-stu-id="76d18-145">Why is CQD data from Skype for Business different than CQD data from Teams?</span></span> 


> [!IMPORTANT]
> <span data-ttu-id="76d18-146">自 2020 年 7 月 1 日起，較舊的 CQD (CQD.lync.com) 會使用來自最新 CQD (CQD 的資料。Teams.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="76d18-146">As of July 1, 2020, the older CQD (CQD.lync.com) uses data from the latest CQD (CQD.Teams.microsoft.com).</span></span> <span data-ttu-id="76d18-147">不再提供較舊的 CQD 資料，而且無法匯出建築物或報表資料。</span><span class="sxs-lookup"><span data-stu-id="76d18-147">The older CQD data is no longer available, and you can't export your building or report data.</span></span> <span data-ttu-id="76d18-148">您仍可使用 CQD.lync.com (系統管理中心 商務用 Skype 提供) ，但我們很快就會關閉 CQD.lync.com 的存取權，因此您應該移至 CQD。Teams.microsoft.com 尚未執行。</span><span class="sxs-lookup"><span data-stu-id="76d18-148">You can still use CQD.lync.com (available from the Skype for Business admin center), but we'll turn off access to CQD.lync.com soon, so you should move to CQD.Teams.microsoft.com if you haven't already done so.</span></span>


<span data-ttu-id="76d18-149">如果您嘗試比較 商務用 Skype 舊版入口網站 (cqd.lync.com) 較舊的 CQD 與 Teams 系統管理中心 (cqd.teams.microsoft.com) 的最新 CQD 之間的資料，您很快就會注意到資料不相符。</span><span class="sxs-lookup"><span data-stu-id="76d18-149">If you're trying to compare data between the older CQD from the Skype for Business legacy portal (cqd.lync.com) and the latest CQD from the Teams admin center (cqd.teams.microsoft.com), you'll quickly notice that the data doesn't match.</span></span> <span data-ttu-id="76d18-150">這是因為最新的 CQD 會報告許多其他通話案例。</span><span class="sxs-lookup"><span data-stu-id="76d18-150">That's because the latest CQD reports on many additional calling scenarios.</span></span> <span data-ttu-id="76d18-151">如果您仍在使用舊版 CQD 中的報表，請使用本文來協助解譯這些[報表：撥打](/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard)適用于 商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="76d18-151">If you're still using reports from the older CQD, use this article to help you interpret those reports: [Call Quality Dashboard for Skype for Business Server](/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard).</span></span>


  
### <a name="why-cant-i-see-euii-in-cqd"></a><span data-ttu-id="76d18-152">為什麼我在 CQD 中看不到 EUII？</span><span class="sxs-lookup"><span data-stu-id="76d18-152">Why can't I see EUII in CQD?</span></span>

<span data-ttu-id="76d18-153">這些系統管理員角色可以存取 CQD，但他們無法查看 EUII (使用者識別) ：</span><span class="sxs-lookup"><span data-stu-id="76d18-153">These admin roles can access CQD, but they can't view EUII (end-user identifiable information):</span></span>
- <span data-ttu-id="76d18-154">Microsoft 365報表閱讀程式</span><span class="sxs-lookup"><span data-stu-id="76d18-154">Microsoft 365 Reports Reader</span></span>
- <span data-ttu-id="76d18-155">Teams通訊支援專家</span><span class="sxs-lookup"><span data-stu-id="76d18-155">Teams Communications Support Specialist</span></span>

<span data-ttu-id="76d18-156">若要深入瞭解可存取 CQD 的角色 ，包括 EUII，請參閱指派角色[以存取 CQD。](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)</span><span class="sxs-lookup"><span data-stu-id="76d18-156">To learn more about roles that can access CQD - including EUII - read [Assign roles for accessing CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).</span></span>

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a><span data-ttu-id="76d18-157">當我只篩選商務用 Skype時，為什麼我在 CQD 中看到Teams資訊？</span><span class="sxs-lookup"><span data-stu-id="76d18-157">Why am I seeing Skype for Business information in CQD when I've filtered for Teams only?</span></span>

<span data-ttu-id="76d18-158">當您只在 CQD Teams中篩選 (isTeams = 1) 時，您篩選的是第一個端點為 Teams 的所有通話。</span><span class="sxs-lookup"><span data-stu-id="76d18-158">When you filter for Teams only in CQD reports (isTeams = 1), you're filtering for all calls where the *first endpoint* is Teams.</span></span> <span data-ttu-id="76d18-159">如果第 *二個* 端點商務用 Skype，該資訊會顯示在 CQD 報告中。</span><span class="sxs-lookup"><span data-stu-id="76d18-159">If the *second endpoint* is Skype for Business, that information will show up in your CQD report.</span></span>

<span data-ttu-id="76d18-160">CQDv2 和 CQDv3 的總數一定會不同，因為 CQDv3 將會有 CQDv2 不會有的新案例。</span><span class="sxs-lookup"><span data-stu-id="76d18-160">CQDv2 and CQDv3 will always have different total counts since CQDv3 will have new scenarios that CQDv2 will not have.</span></span> <span data-ttu-id="76d18-161">這就是為什麼比較匯總總計或匯總匯總數位與沒有篩選的數值會具有這些預期差異的原因。</span><span class="sxs-lookup"><span data-stu-id="76d18-161">That’s why comparing Summary Total or Aggregated all-up numbers with no filters will have these expected differences.</span></span>  

<span data-ttu-id="76d18-162">根據客戶案例，CQDv3 會包含 SFB 2019 內部部署通話 (如果 SFB 2019 用於資料連線器) 、Skype Bot 通話 (AA、CVI、VDI) 、Live Events 和 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="76d18-162">Depending on Customers’ scenario, CQDv3 will include SFB 2019 on-premises calls (if SFB 2019 is used with a data connector), Skype Bot calls (AA, CVI, VDI), Live Events and PSTN calls.</span></span> <span data-ttu-id="76d18-163">客戶可用的案例/功能，但他們的資料不在 CQD V2 中。</span><span class="sxs-lookup"><span data-stu-id="76d18-163">Scenarios/Features which are available for the customers, but their data are not in CQD V2.</span></span>

<span data-ttu-id="76d18-164">例如，預期您的客戶和您會看到 200，000 個音訊資料流程，而 CQD V2 摘要報告中有 5000 個失敗;與 300，000 個音訊資料流程，有 5500 個失敗 (來自 CQD V3 中的 2019 on-prem 通話、CVI 通話、PSTN 通話等 ) 。</span><span class="sxs-lookup"><span data-stu-id="76d18-164">For instance, it is expected that your customers and you will see 200,000 audio streams, with 5000 failures in CQD V2 Summary Report; versus 300,000 audio streams with 5500 failures (coming from 2019 on-prem calls, CVI calls, PSTN calls, etc.) in CQD V3.</span></span>

<span data-ttu-id="76d18-165">若要判斷是否有任何意外的差異，您必須查看整體資料的各種明細。</span><span class="sxs-lookup"><span data-stu-id="76d18-165">In order to determine, if there are any unexpected differences, you must look at various breakdowns of the overall data.</span></span>  <span data-ttu-id="76d18-166">與目的比較。</span><span class="sxs-lookup"><span data-stu-id="76d18-166">Compare with intent.</span></span>  <span data-ttu-id="76d18-167">根據使用者代理程式類別組來剪下資料是我們建議的第一件事。</span><span class="sxs-lookup"><span data-stu-id="76d18-167">Slicing the data by User Agent Category Pair is one of the first things we recommend.</span></span>  <span data-ttu-id="76d18-168">*第一個* 產品 *和第二個產品* 也是很好的切線機。</span><span class="sxs-lookup"><span data-stu-id="76d18-168">*First Product* and *Second Product* are also good slicers.</span></span>  

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a><span data-ttu-id="76d18-169">為什麼我的自訂報表最多隻會返回 10，000 列，當我知道應該有更多的專案時？</span><span class="sxs-lookup"><span data-stu-id="76d18-169">Why do my custom reports only return a maximum of 10,000 rows when I know there should be more entries?</span></span>

<span data-ttu-id="76d18-170">CQD 是專為摘要資料查詢所設計，並非專為數據匯出所設計。</span><span class="sxs-lookup"><span data-stu-id="76d18-170">CQD is designed for summarized data queries, and is not designed for data export.</span></span> <span data-ttu-id="76d18-171">建議您盡可能調整報表的重組，以防止超過 10，000 列的限制。</span><span class="sxs-lookup"><span data-stu-id="76d18-171">We recommend restructuring your reports, where possible, to prevent the 10,000 row limit from being exceeded.</span></span> <span data-ttu-id="76d18-172">首先，使用更廣泛的較低基數維度來查看 KPI，例如月、年、日期、地區、國家/地區等。您可以在那裡向下向下切入到愈高基數維度。</span><span class="sxs-lookup"><span data-stu-id="76d18-172">Start by looking at your KPIs using broader, lower-cardinality dimensions, such as Month, Year, Date, Region, Country, etc. From there, you can drill down into increasingly higher-cardinality dimensions.</span></span> <span data-ttu-id="76d18-173">說明台和Location-Enhanced報表都提供此向下切入工作流程的範例。</span><span class="sxs-lookup"><span data-stu-id="76d18-173">The Helpdesk and Location-Enhanced Reports both provide good examples of this drill down workflow.</span></span>

### <a name="why-do-wifi-vpn-connections-show-as-wired-instead-of-wifi"></a><span data-ttu-id="76d18-174">為什麼 WiFi VPN 連接會顯示為有線而非 WiFi？</span><span class="sxs-lookup"><span data-stu-id="76d18-174">Why do WiFi VPN connections show as Wired instead of WiFi?</span></span>

<span data-ttu-id="76d18-175">這是預期行為 。</span><span class="sxs-lookup"><span data-stu-id="76d18-175">This is expected.</span></span> <span data-ttu-id="76d18-176">VPN 廠商建立了虛擬乙太網路介面卡，其視為有線連接。</span><span class="sxs-lookup"><span data-stu-id="76d18-176">The VPN vendor created a virtual ethernet adapter which is treated like a wired connection.</span></span> <span data-ttu-id="76d18-177">由於未正確標示，作業系統不知道它是 WiFi 連接，並報告為有線。</span><span class="sxs-lookup"><span data-stu-id="76d18-177">Since it's not properly labeled, the operating system doesn't know it's a WiFi connection and reports it as wired.</span></span>

## <a name="related-topics"></a><span data-ttu-id="76d18-178">相關主題</span><span class="sxs-lookup"><span data-stu-id="76d18-178">Related topics</span></span>

[<span data-ttu-id="76d18-179">改善及監控通話品質Teams</span><span class="sxs-lookup"><span data-stu-id="76d18-179">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="76d18-180">什麼是 CQD？</span><span class="sxs-lookup"><span data-stu-id="76d18-180">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="76d18-181">設定通話品質儀表板 (CQD) </span><span class="sxs-lookup"><span data-stu-id="76d18-181">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="76d18-182">Upload租使用者和建築物資料</span><span class="sxs-lookup"><span data-stu-id="76d18-182">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="76d18-183">CQD 資料和報表</span><span class="sxs-lookup"><span data-stu-id="76d18-183">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="76d18-184">使用 CQD 管理通話和會議品質</span><span class="sxs-lookup"><span data-stu-id="76d18-184">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="76d18-185">CQD 中可用的維度和度量</span><span class="sxs-lookup"><span data-stu-id="76d18-185">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="76d18-186">CQD 中的資料流程分類</span><span class="sxs-lookup"><span data-stu-id="76d18-186">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="76d18-187">使用 Power BI分析 CQD 資料</span><span class="sxs-lookup"><span data-stu-id="76d18-187">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)

[<span data-ttu-id="76d18-188">Teams 疑難排解</span><span class="sxs-lookup"><span data-stu-id="76d18-188">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
