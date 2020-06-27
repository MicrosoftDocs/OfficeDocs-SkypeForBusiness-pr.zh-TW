---
title: 在商務用 Skype Server 中評價我的通話
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: 摘要：瞭解商務用 Skype Server 中的通話功能的速率。
ms.openlocfilehash: 15f2bcbcf75690baaa350541f5f1da134fb32025
ms.sourcegitcommit: a73df97a06ea860bfaf5387e0acbf3c724697e14
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "44902217"
---
# <a name="rate-my-call-in-skype-for-business-server"></a><span data-ttu-id="be2b0-103">在商務用 Skype Server 中評價我的通話</span><span class="sxs-lookup"><span data-stu-id="be2b0-103">Rate my Call in Skype for Business Server</span></span>

<span data-ttu-id="be2b0-104">**摘要：** 深入瞭解商務用 Skype Server 中的通話功能的速率。</span><span class="sxs-lookup"><span data-stu-id="be2b0-104">**Summary:** Learn about the Rate My Call feature in Skype for Business Server.</span></span>

<span data-ttu-id="be2b0-105">評價我的來電是商務用 Skype 2015 和2016用戶端在 Windows 上的新功能，可讓企業從他們的使用者取得意見反應的方式。</span><span class="sxs-lookup"><span data-stu-id="be2b0-105">Rate My Call was a new feature in Skype for Business 2015 and 2016 clients on Windows that provides enterprises a way to get feedback from their end-users.</span></span>

<span data-ttu-id="be2b0-106">「我的呼叫」視窗的速率是「星形」分級系統及音訊及視頻通話的預先定義的標記。</span><span class="sxs-lookup"><span data-stu-id="be2b0-106">The Rate My Call window offers a "star" rating system and predefined tokens for audio and video calls.</span></span> <span data-ttu-id="be2b0-107">此外，系統管理員可以讓自訂欄位提供意見反應。</span><span class="sxs-lookup"><span data-stu-id="be2b0-107">In addition, administrators can enable a custom field to provide feedback.</span></span>

<span data-ttu-id="be2b0-108">收集的速率我的呼叫資料目前不會包含在任何現有的監控報告中，但有個別的監控報告。</span><span class="sxs-lookup"><span data-stu-id="be2b0-108">Collected Rate My Call data is not currently included in any existing monitoring report, but it has a separate monitoring report.</span></span> <span data-ttu-id="be2b0-109">在 SQL 資料表中收集的資料可透過執行 SQL 查詢進行存取。</span><span class="sxs-lookup"><span data-stu-id="be2b0-109">Data is collected in SQL tables that can be accessed by running SQL queries.</span></span>

## <a name="rate-my-call-prerequisites"></a><span data-ttu-id="be2b0-110">評估我的來電先決條件</span><span class="sxs-lookup"><span data-stu-id="be2b0-110">Rate my Call Prerequisites</span></span>

<span data-ttu-id="be2b0-111">在商務用 Skype 伺服器部署中的使用者可以存取我的呼叫功能之前，必須部署及設定下列元件：</span><span class="sxs-lookup"><span data-stu-id="be2b0-111">Before the users in your Skype for Business Server deployment can access Rate My Call functionality, the following set of components must be deployed and configured:</span></span>

-  <span data-ttu-id="be2b0-112">您必須已安裝商務用 Skype Server （版本9160或更高版本）。</span><span class="sxs-lookup"><span data-stu-id="be2b0-112">You must have Skype for Business Server installed (version 9160 or higher).</span></span>

- <span data-ttu-id="be2b0-113">讓您的使用者安裝並更新至最新版本的商務用 Skype，也要求他們使用商務用 Skype UI。</span><span class="sxs-lookup"><span data-stu-id="be2b0-113">Have your users install and update to the latest version of Skype for Business and also ask them to use the Skype for Business UI.</span></span>

- <span data-ttu-id="be2b0-114">使用者必須位於商務用 Skype 伺服器前端集區。</span><span class="sxs-lookup"><span data-stu-id="be2b0-114">Users must be homed on the Skype for Business Server Front End pool.</span></span>

- <span data-ttu-id="be2b0-115">您必須已部署商務用 Skype Server 監控資料庫並與商務用 Skype 伺服器集區相關聯。</span><span class="sxs-lookup"><span data-stu-id="be2b0-115">You must have a Skype for Business Server monitoring database deployed and associated to your Skype for Business Server pools.</span></span>

- <span data-ttu-id="be2b0-116">建議您部署通話品質儀表板（CQD）。</span><span class="sxs-lookup"><span data-stu-id="be2b0-116">We recommend deploying Call Quality Dashboard (CQD).</span></span>

## <a name="configure-rate-my-call"></a><span data-ttu-id="be2b0-117">設定通話的速率</span><span class="sxs-lookup"><span data-stu-id="be2b0-117">Configure Rate my Call</span></span>

<span data-ttu-id="be2b0-118">使用下列設定，用戶端原則中預設會啟用「我的通話」功能：</span><span class="sxs-lookup"><span data-stu-id="be2b0-118">The Rate My Call feature is enabled by default in the Client policy with the following settings:</span></span>

- <span data-ttu-id="be2b0-119">將我的通話顯示百分比打分-10%</span><span class="sxs-lookup"><span data-stu-id="be2b0-119">Rate My Call Display Percentage - 10%</span></span>

- <span data-ttu-id="be2b0-120">對我的呼叫允許自訂使用者的反應率-已停用</span><span class="sxs-lookup"><span data-stu-id="be2b0-120">Rate My Call Allow Custom User Feedback - disabled</span></span>

<span data-ttu-id="be2b0-121">啟用基本功能沒有必要的動作，但是如果您想要有自訂的意見反應，您必須個別啟用。</span><span class="sxs-lookup"><span data-stu-id="be2b0-121">There is no action required to enable the base feature, however but if you want custom feedback you will need to enable it separately.</span></span> <span data-ttu-id="be2b0-122">下列 Windows PowerShell Cmdlet 是啟用自訂使用者意見反應的範例，並將從10% 到80% 的間隔變更。</span><span class="sxs-lookup"><span data-stu-id="be2b0-122">The following Windows PowerShell cmdlet is an example of enabling custom end user feedback and changing the interval from 10% to 80%.</span></span>

```PowerShell
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 -RateMyCallAllowCustomUserFeedback $true 
```

## <a name="accessing-rate-my-call-data"></a><span data-ttu-id="be2b0-123">存取通話資料的速率</span><span class="sxs-lookup"><span data-stu-id="be2b0-123">Accessing Rate My Call Data</span></span>

<span data-ttu-id="be2b0-124">使用者的資料會收集在監控資料庫中的兩個表格中。</span><span class="sxs-lookup"><span data-stu-id="be2b0-124">Data from users is collected in two tables in the monitoring database.</span></span>

 <span data-ttu-id="be2b0-125">**[QoeMetrics]。[dbo]。[CallQualityFeedbackToken]**-此表格包含使用者對權杖進行輪詢的結果。</span><span class="sxs-lookup"><span data-stu-id="be2b0-125">**[QoeMetrics].[dbo].[CallQualityFeedbackToken]** - this table contains results of token polling by end users.</span></span>

 <span data-ttu-id="be2b0-126">**[QoeMetrics]。[dbo]。[CallQualityFeedbackTokenDef]**-此表格包含 token 定義。</span><span class="sxs-lookup"><span data-stu-id="be2b0-126">**[QoeMetrics].[dbo].[CallQualityFeedbackTokenDef]** - this table contains token definitions.</span></span>

<span data-ttu-id="be2b0-127">權杖定義的編碼方式如下：</span><span class="sxs-lookup"><span data-stu-id="be2b0-127">Token definitions are coded as follows:</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="be2b0-128">1 </span><span class="sxs-lookup"><span data-stu-id="be2b0-128">1</span></span>  <br/> |<span data-ttu-id="be2b0-129">DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="be2b0-129">DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="be2b0-130">2 </span><span class="sxs-lookup"><span data-stu-id="be2b0-130">2</span></span>  <br/> | <span data-ttu-id="be2b0-131">ElectronicFeedback</span><span class="sxs-lookup"><span data-stu-id="be2b0-131">ElectronicFeedback</span></span> <br/> |
|<span data-ttu-id="be2b0-132">3 </span><span class="sxs-lookup"><span data-stu-id="be2b0-132">3</span></span>  <br/> | <span data-ttu-id="be2b0-133">BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="be2b0-133">BackgroundNoise</span></span> <br/> |
|<span data-ttu-id="be2b0-134">4 </span><span class="sxs-lookup"><span data-stu-id="be2b0-134">4</span></span>  <br/> |<span data-ttu-id="be2b0-135">MuffledSpeech</span><span class="sxs-lookup"><span data-stu-id="be2b0-135">MuffledSpeech</span></span>  <br/> |
|<span data-ttu-id="be2b0-136">5 </span><span class="sxs-lookup"><span data-stu-id="be2b0-136">5</span></span>  <br/> |<span data-ttu-id="be2b0-137">回音</span><span class="sxs-lookup"><span data-stu-id="be2b0-137">Echo</span></span>  <br/> |
|<span data-ttu-id="be2b0-138"> 21</span><span class="sxs-lookup"><span data-stu-id="be2b0-138">21</span></span>  <br/> | <span data-ttu-id="be2b0-139">FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="be2b0-139">FrozenVideo</span></span> <br/> |
|<span data-ttu-id="be2b0-140">22</span><span class="sxs-lookup"><span data-stu-id="be2b0-140">22</span></span>  <br/> | <span data-ttu-id="be2b0-141">PixelatedVideo</span><span class="sxs-lookup"><span data-stu-id="be2b0-141">PixelatedVideo</span></span> <br/> |
|<span data-ttu-id="be2b0-142">至</span><span class="sxs-lookup"><span data-stu-id="be2b0-142">23</span></span>  <br/> | <span data-ttu-id="be2b0-143">BlurryImage</span><span class="sxs-lookup"><span data-stu-id="be2b0-143">BlurryImage</span></span> <br/> |
|<span data-ttu-id="be2b0-144">24</span><span class="sxs-lookup"><span data-stu-id="be2b0-144">24</span></span>  <br/> | <span data-ttu-id="be2b0-145">PoorColor</span><span class="sxs-lookup"><span data-stu-id="be2b0-145">PoorColor</span></span> <br/> |
|<span data-ttu-id="be2b0-146">0.25</span><span class="sxs-lookup"><span data-stu-id="be2b0-146">25</span></span>  <br/> | <span data-ttu-id="be2b0-147">DarkVideo</span><span class="sxs-lookup"><span data-stu-id="be2b0-147">DarkVideo</span></span> <br/> |
|<span data-ttu-id="be2b0-148">101</span><span class="sxs-lookup"><span data-stu-id="be2b0-148">101</span></span>  <br/> |<span data-ttu-id="be2b0-149">Audio_SilentLocal</span><span class="sxs-lookup"><span data-stu-id="be2b0-149">Audio_SilentLocal</span></span>  <br/> |
|<span data-ttu-id="be2b0-150">102</span><span class="sxs-lookup"><span data-stu-id="be2b0-150">102</span></span>  <br/> |<span data-ttu-id="be2b0-151">Audio_SilentRemote</span><span class="sxs-lookup"><span data-stu-id="be2b0-151">Audio_SilentRemote</span></span>  <br/> |
|<span data-ttu-id="be2b0-152">103</span><span class="sxs-lookup"><span data-stu-id="be2b0-152">103</span></span>  <br/> |<span data-ttu-id="be2b0-153">Audio_Echo</span><span class="sxs-lookup"><span data-stu-id="be2b0-153">Audio_Echo</span></span>  <br/> |
|<span data-ttu-id="be2b0-154">104</span><span class="sxs-lookup"><span data-stu-id="be2b0-154">104</span></span>  <br/> |<span data-ttu-id="be2b0-155">Audio_BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="be2b0-155">Audio_BackgroundNoise</span></span>  <br/> |
|<span data-ttu-id="be2b0-156">105</span><span class="sxs-lookup"><span data-stu-id="be2b0-156">105</span></span>  <br/> |<span data-ttu-id="be2b0-157">Audio_LowSound</span><span class="sxs-lookup"><span data-stu-id="be2b0-157">Audio_LowSound</span></span>  <br/> |
|<span data-ttu-id="be2b0-158">106</span><span class="sxs-lookup"><span data-stu-id="be2b0-158">106</span></span>  <br/> |<span data-ttu-id="be2b0-159">Audio_Dropped</span><span class="sxs-lookup"><span data-stu-id="be2b0-159">Audio_Dropped</span></span>  <br/> |
|<span data-ttu-id="be2b0-160">107</span><span class="sxs-lookup"><span data-stu-id="be2b0-160">107</span></span>  <br/> |<span data-ttu-id="be2b0-161">Audio_DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="be2b0-161">Audio_DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="be2b0-162">108</span><span class="sxs-lookup"><span data-stu-id="be2b0-162">108</span></span>  <br/> |<span data-ttu-id="be2b0-163">Audio_Interrupted</span><span class="sxs-lookup"><span data-stu-id="be2b0-163">Audio_Interrupted</span></span>  <br/> |
|<span data-ttu-id="be2b0-164">109</span><span class="sxs-lookup"><span data-stu-id="be2b0-164">109</span></span>  <br/> |<span data-ttu-id="be2b0-165">Audio_Other</span><span class="sxs-lookup"><span data-stu-id="be2b0-165">Audio_Other</span></span>  <br/> |
|<span data-ttu-id="be2b0-166">201</span><span class="sxs-lookup"><span data-stu-id="be2b0-166">201</span></span>  <br/> |<span data-ttu-id="be2b0-167">Video_NoLocalVideo</span><span class="sxs-lookup"><span data-stu-id="be2b0-167">Video_NoLocalVideo</span></span>  <br/> |
|<span data-ttu-id="be2b0-168">202</span><span class="sxs-lookup"><span data-stu-id="be2b0-168">202</span></span>  <br/> |<span data-ttu-id="be2b0-169">Video_NoRemoteVideo</span><span class="sxs-lookup"><span data-stu-id="be2b0-169">Video_NoRemoteVideo</span></span>  <br/> |
|<span data-ttu-id="be2b0-170">203</span><span class="sxs-lookup"><span data-stu-id="be2b0-170">203</span></span>  <br/> |<span data-ttu-id="be2b0-171">Video_LowQuality</span><span class="sxs-lookup"><span data-stu-id="be2b0-171">Video_LowQuality</span></span>  <br/> |
|<span data-ttu-id="be2b0-172">204</span><span class="sxs-lookup"><span data-stu-id="be2b0-172">204</span></span>  <br/> |<span data-ttu-id="be2b0-173">Video_FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="be2b0-173">Video_FrozenVideo</span></span>  <br/> |
|<span data-ttu-id="be2b0-174">205</span><span class="sxs-lookup"><span data-stu-id="be2b0-174">205</span></span>  <br/> |<span data-ttu-id="be2b0-175">Video_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="be2b0-175">Video_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="be2b0-176">206</span><span class="sxs-lookup"><span data-stu-id="be2b0-176">206</span></span>  <br/> |<span data-ttu-id="be2b0-177">Video_DarkVideo</span><span class="sxs-lookup"><span data-stu-id="be2b0-177">Video_DarkVideo</span></span>  <br/> |
|<span data-ttu-id="be2b0-178">207</span><span class="sxs-lookup"><span data-stu-id="be2b0-178">207</span></span>  <br/> |<span data-ttu-id="be2b0-179">Video_NoAudioSync</span><span class="sxs-lookup"><span data-stu-id="be2b0-179">Video_NoAudioSync</span></span>  <br/> |
|<span data-ttu-id="be2b0-180">208</span><span class="sxs-lookup"><span data-stu-id="be2b0-180">208</span></span>  <br/> |<span data-ttu-id="be2b0-181">Video_Other</span><span class="sxs-lookup"><span data-stu-id="be2b0-181">Video_Other</span></span>  <br/> |
|<span data-ttu-id="be2b0-182">301</span><span class="sxs-lookup"><span data-stu-id="be2b0-182">301</span></span>  <br/> |<span data-ttu-id="be2b0-183">Pstn_DialPad</span><span class="sxs-lookup"><span data-stu-id="be2b0-183">Pstn_DialPad</span></span>  <br/> |
|<span data-ttu-id="be2b0-184">401</span><span class="sxs-lookup"><span data-stu-id="be2b0-184">401</span></span>  <br/> |<span data-ttu-id="be2b0-185">SS_NoContentLocal</span><span class="sxs-lookup"><span data-stu-id="be2b0-185">SS_NoContentLocal</span></span>  <br/> |
|<span data-ttu-id="be2b0-186">402</span><span class="sxs-lookup"><span data-stu-id="be2b0-186">402</span></span>  <br/> |<span data-ttu-id="be2b0-187">SS_NoContentRemote</span><span class="sxs-lookup"><span data-stu-id="be2b0-187">SS_NoContentRemote</span></span>  <br/> |
|<span data-ttu-id="be2b0-188">403</span><span class="sxs-lookup"><span data-stu-id="be2b0-188">403</span></span>  <br/> |<span data-ttu-id="be2b0-189">SS_CantPresent</span><span class="sxs-lookup"><span data-stu-id="be2b0-189">SS_CantPresent</span></span>  <br/> |
|<span data-ttu-id="be2b0-190">404</span><span class="sxs-lookup"><span data-stu-id="be2b0-190">404</span></span>  <br/> |<span data-ttu-id="be2b0-191">SS_LowQuality</span><span class="sxs-lookup"><span data-stu-id="be2b0-191">SS_LowQuality</span></span>  <br/> |
|<span data-ttu-id="be2b0-192">405</span><span class="sxs-lookup"><span data-stu-id="be2b0-192">405</span></span>  <br/> |<span data-ttu-id="be2b0-193">SS_Freezing</span><span class="sxs-lookup"><span data-stu-id="be2b0-193">SS_Freezing</span></span>  <br/> |
|<span data-ttu-id="be2b0-194">406</span><span class="sxs-lookup"><span data-stu-id="be2b0-194">406</span></span>  <br/> |<span data-ttu-id="be2b0-195">SS_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="be2b0-195">SS_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="be2b0-196">407</span><span class="sxs-lookup"><span data-stu-id="be2b0-196">407</span></span>  <br/> |<span data-ttu-id="be2b0-197">SS_LargeDelay</span><span class="sxs-lookup"><span data-stu-id="be2b0-197">SS_LargeDelay</span></span>  <br/> |
|<span data-ttu-id="be2b0-198">408</span><span class="sxs-lookup"><span data-stu-id="be2b0-198">408</span></span>  <br/> |<span data-ttu-id="be2b0-199">SS_Other</span><span class="sxs-lookup"><span data-stu-id="be2b0-199">SS_Other</span></span>  <br/> |
|<span data-ttu-id="be2b0-200">501</span><span class="sxs-lookup"><span data-stu-id="be2b0-200">501</span></span>  <br/> |<span data-ttu-id="be2b0-201">Reliabilty_Join</span><span class="sxs-lookup"><span data-stu-id="be2b0-201">Reliabilty_Join</span></span>  <br/> |
|<span data-ttu-id="be2b0-202">502</span><span class="sxs-lookup"><span data-stu-id="be2b0-202">502</span></span>  <br/> |<span data-ttu-id="be2b0-203">Reliabilty_Invite</span><span class="sxs-lookup"><span data-stu-id="be2b0-203">Reliabilty_Invite</span></span>  <br/> |

 <span data-ttu-id="be2b0-204">**[QoeMetrics]。[dbo]。[CallQualityFeedback]** 此表格包含 "星" 投票和客戶意見反應（若啟用）的輪詢結果。</span><span class="sxs-lookup"><span data-stu-id="be2b0-204">**[QoeMetrics].[dbo].[CallQualityFeedback]** This table contains polling results from "Star" voting and customer feedback if enabled.</span></span>

<span data-ttu-id="be2b0-205">您可以使用\*\* \* [Table.Name]\*\* 查詢或使用 Microsoft SQL Server Management Studio 來呼叫資料表中的資料。</span><span class="sxs-lookup"><span data-stu-id="be2b0-205">Data from tables can be called by using a **select \* from [Table.Name]** query or by using Microsoft SQL Server Management Studio.</span></span>

<span data-ttu-id="be2b0-206">下列 SQL 查詢可供使用：</span><span class="sxs-lookup"><span data-stu-id="be2b0-206">The following SQL queries can be used:</span></span>

 <span data-ttu-id="be2b0-207">**音訊**</span><span class="sxs-lookup"><span data-stu-id="be2b0-207">**Audio**</span></span>

```SQL
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [AudioStream] AS a WITH (NOLOCK) ON -- only look at Audio related feedback
            a.MediaLineLabel = m.MediaLineLabel    
            and a.ConferenceDateTime = m.ConferenceDateTime 
            and a.SessionSeq = m.SessionSeq
            and a.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
            (CallerCqfToken.TokenId < 20 or (CallerCqfToken.TokenId > 100 and CallerCqfToken.TokenId < 200)) -- only look at Audio related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
```

 <span data-ttu-id="be2b0-208">**影片**</span><span class="sxs-lookup"><span data-stu-id="be2b0-208">**Video**</span></span>

```SQL
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [VideoStream] AS v WITH (NOLOCK) ON -- only look at Video related feedback
            v.MediaLineLabel = m.MediaLineLabel    
            and v.ConferenceDateTime = m.ConferenceDateTime 
            and v.SessionSeq = m.SessionSeq
            and v.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
           ((CallerCqfToken.TokenId > 20 and CallerCqfToken.TokenId < 100) or (CallerCqfToken.TokenId > 200 and CallerCqfToken.TokenId < 300)) -- only look at Video related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
```

## <a name="updating-token-definitions"></a><span data-ttu-id="be2b0-209">更新權杖定義</span><span class="sxs-lookup"><span data-stu-id="be2b0-209">Updating Token Definitions</span></span>

<span data-ttu-id="be2b0-210">最新的商務用 Skype 用戶端報告新問題權杖 IDs （ \> 100）可能不會出現在 [QoeMetrics] 中。 [dbo]。[CallQualityFeedbackTokenDef] 表格。</span><span class="sxs-lookup"><span data-stu-id="be2b0-210">The latest Skype for Business clients report new problem token IDs (\> 100) that may not be present in your [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span> <span data-ttu-id="be2b0-211">若要以最新的標記定義更新資料庫資料表，可在使用 Microsoft SQL Server Management Studio 的監控資料庫上執行下列 SQL 命令。</span><span class="sxs-lookup"><span data-stu-id="be2b0-211">To update the database table with the latest token definitions, the below SQL command can be run on the monitoring database using Microsoft SQL Server Management Studio.</span></span> <span data-ttu-id="be2b0-212">此命令會取代 [QoeMetrics] 中的所有專案。[dbo]。[CallQualityFeedbackTokenDef] 表格。</span><span class="sxs-lookup"><span data-stu-id="be2b0-212">This command will replace all entries in the [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span>

```SQL
DELETE FROM [CallQualityFeedbackTokenDef];
INSERT INTO [CallQualityFeedbackTokenDef] (TokenId, TokenDescription) VALUES
    (1,   N'DistortedSpeech'),
    (2,   N'ElectronicFeedback'),
    (3,   N'BackgroundNoise'),
    (4,   N'MuffledSpeech'),
    (5,   N'Echo'),
    (21,  N'FrozenVideo'),
    (22,  N'PixelatedVideo'),
    (23,  N'BlurryImage'),
    (24,  N'PoorColor'),
    (25,  N'DarkVideo'),
    (101, N'Audio_SilentLocal'),
    (102, N'Audio_SilentRemote'),
    (103, N'Audio_Echo'),
    (104, N'Audio_BackgroundNoise'),
    (105, N'Audio_LowSound'),
    (106, N'Audio_Dropped'),
    (107, N'Audio_DistortedSpeech'),
    (108, N'Audio_Interrupted'),
    (109, N'Audio_Other'),
    (201, N'Video_NoLocalVideo'),
    (202, N'Video_NoRemoteVideo'),
    (203, N'Video_LowQuality'),
    (204, N'Video_FrozenVideo'),
    (205, N'Video_StoppedUnexpectedly'),
    (206, N'Video_DarkVideo'),
    (207, N'Video_NoAudioSync'),
    (208, N'Video_Other'),
    (301, N'Pstn_DialPad'),
    (401, N'SS_NoContentLocal'),
    (402, N'SS_NoContentRemote'),
    (403, N'SS_CantPresent'),
    (404, N'SS_LowQuality'),
    (405, N'SS_Freezing'),
    (406, N'SS_StoppedUnexpectedly'),
    (407, N'SS_LargeDelay'),
    (408, N'SS_Other'),
    (501, N'Reliabilty_Join'),
    (502, N'Reliabilty_Invite');
```


