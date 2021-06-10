---
title: 使用 CQD PSTN 直接路由報告
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: siunies, fan.fan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: 使用 [Microsoft Teams通話品質儀表板 (PSTN) ) 直接路由報告來監控及疑難排解 PSTN Microsoft Teams。
ms.openlocfilehash: f2b63f991f42aa4de9e0e4474137f7f992f95c53
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094977"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a><span data-ttu-id="f619e-103">使用 CQD PSTN 直接路由報告</span><span class="sxs-lookup"><span data-stu-id="f619e-103">Using the CQD PSTN Direct Routing report</span></span>

<span data-ttu-id="f619e-104">我們于 2020 年 3 月新增 Microsoft Teams 通話品質儀表板 (CQD) PSTN 直接路由報表至可下載的 Power BI 查詢[範本 。](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="f619e-104">New in March 2020, we've added a Microsoft Teams Call Quality Dashboard (CQD) PSTN Direct Routing report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 


<span data-ttu-id="f619e-105">CQD PSTN 直接路由報告 (CQD PSTN 直接路由報表.pbit) 可協助瞭解 PSTN 服務的使用模式和品質。</span><span class="sxs-lookup"><span data-stu-id="f619e-105">The CQD PSTN Direct Routing report (CQD PSTN Direct Routing Report.pbit) helps you understand the usage patterns and quality of your PSTN services.</span></span> <span data-ttu-id="f619e-106">使用此報表可監控服務使用方式、會話邊界控制器 (SBC) 、電話語音、網路參數和網路效能比詳細資料。</span><span class="sxs-lookup"><span data-stu-id="f619e-106">Use this report to monitor service usage, information about your Session Border Controller (SBC), the telephony service, network parameters, and Network Effectiveness Ratio details.</span></span> <span data-ttu-id="f619e-107">這項資訊可協助找出問題，包括通話中斷的原因。</span><span class="sxs-lookup"><span data-stu-id="f619e-107">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="f619e-108">例如，您將能夠查看音量何時降低，或是有多少通話受到影響，以及原因。</span><span class="sxs-lookup"><span data-stu-id="f619e-108">For example, you'll be able to see when volume drops, or how many calls get affected and for what reason.</span></span>


<span data-ttu-id="f619e-109">CQD PSTN 直接路由報告有四個區段：</span><span class="sxs-lookup"><span data-stu-id="f619e-109">The CQD PSTN Direct Routing Report has four sections:</span></span>

  - [<span data-ttu-id="f619e-110">PSTN 概觀</span><span class="sxs-lookup"><span data-stu-id="f619e-110">PSTN Overview</span></span>](#pstn-overview)

  - [<span data-ttu-id="f619e-111">服務詳細資料</span><span class="sxs-lookup"><span data-stu-id="f619e-111">Service Details</span></span>](#service-details)

  - [<span data-ttu-id="f619e-112">網路效能比</span><span class="sxs-lookup"><span data-stu-id="f619e-112">Network Effectiveness Ratio</span></span>](#network-effectiveness-ratio)

  - [<span data-ttu-id="f619e-113">網路參數</span><span class="sxs-lookup"><span data-stu-id="f619e-113">Network Parameters</span></span>](#network-parameters)

## <a name="highlights"></a><span data-ttu-id="f619e-114">好友動向</span><span class="sxs-lookup"><span data-stu-id="f619e-114">Highlights</span></span>

1. <span data-ttu-id="f619e-115">根據通話類型、SBC、來電和通話物件國家/地區來分析</span><span class="sxs-lookup"><span data-stu-id="f619e-115">Analyze by call type, SBC, caller and callee country</span></span>

   <span data-ttu-id="f619e-116">CQD PSTN 直接路由報告會匯總租使用者上所有 SBC 在) 年的最後 7、30 或 180 天 (可靠性及使用量) 。</span><span class="sxs-lookup"><span data-stu-id="f619e-116">The CQD PSTN Direct Routing report aggregates reliability and usage metrics for all SBCs on your tenant for the last 7, 30, or 180 days (6 months).</span></span> <span data-ttu-id="f619e-117">您可以根據通話類型、SBC、來電者及通話物件國家/地區來分析資料。</span><span class="sxs-lookup"><span data-stu-id="f619e-117">You can analyze data by call type, SBC, caller and callee country.</span></span> <span data-ttu-id="f619e-118">如果您對特定的 SBC 或國家/地區感興趣，您可以找出所選時間範圍內的趨勢變更。</span><span class="sxs-lookup"><span data-stu-id="f619e-118">If you're interested in a particular SBC or country, you'll be able to identify changes in trends over the selected time range.</span></span>
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="CQD PSTN 直接路由報告中可用的篩選的螢幕擷取畫面":::
   
2. <span data-ttu-id="f619e-120">追蹤趨勢</span><span class="sxs-lookup"><span data-stu-id="f619e-120">Track trends</span></span>

    <span data-ttu-id="f619e-121">趨勢分析在嘗試瞭解服務使用方式和可靠性時不可或缺。</span><span class="sxs-lookup"><span data-stu-id="f619e-121">Trends analysis is essential when trying to understand service usage and reliability.</span></span> <span data-ttu-id="f619e-122">每小時趨勢提供每日績效的密切觀察，有助於識別即時事件。</span><span class="sxs-lookup"><span data-stu-id="f619e-122">Hourly trends provide a close look at daily performance, which helps identify real-time incidents.</span></span> <span data-ttu-id="f619e-123">每日趨勢讓您從長期的觀點來查看服務健康情況。</span><span class="sxs-lookup"><span data-stu-id="f619e-123">Daily trends let you see your service health from a long-term perspective.</span></span> <span data-ttu-id="f619e-124">必須能夠以適當的資料細微性，在兩種模式之間切換。</span><span class="sxs-lookup"><span data-stu-id="f619e-124">It's important to be able to shift between those two modes with appropriate data granularity.</span></span> <span data-ttu-id="f619e-125">CQD PSTN 直接路由報告提供 6 個月趨勢概觀、7 天和 30 天每日趨勢，以及每小時趨勢，以便分析每個層級的績效。</span><span class="sxs-lookup"><span data-stu-id="f619e-125">The CQD PSTN Direct Routing report provides 6-month trends overview, 7- and 30-day daily trends, and hourly trends so you can analyze performance at each level.</span></span>
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="CQD PSTN 直接路由報告中的趨勢圖形螢幕擷取畫面":::

3. <span data-ttu-id="f619e-127">深入到 SBC 或使用者層級</span><span class="sxs-lookup"><span data-stu-id="f619e-127">Drill through to SBC or user level</span></span>

   <span data-ttu-id="f619e-128">我們已在 CQD 中建立許多資料類別的深入深入功能，讓您快速瞭解 SBC 或使用者層級的使用方式或可靠性分配。</span><span class="sxs-lookup"><span data-stu-id="f619e-128">We've been building in drill-through capability on many data categories in CQD, which lets you quickly understand usage or reliability distribution at the SBC or user level.</span></span> <span data-ttu-id="f619e-129">使用鑽取功能，您可以快速發現問題並瞭解使用者的實際影響。</span><span class="sxs-lookup"><span data-stu-id="f619e-129">By using drill through, you can quickly poinpoint issues and understand real user impact.</span></span> <span data-ttu-id="f619e-130">CQD PSTN 直接路由報告功能會深入探討服務詳細資料與網路效能比度量。</span><span class="sxs-lookup"><span data-stu-id="f619e-130">The CQD PSTN Direct Routing report features drill through on the Service Detail and Network Effectiveness Ratio metrics.</span></span> <span data-ttu-id="f619e-131">按一下您感興趣的資料點，以深入瞭解 SBC 或使用者層級詳細資料。</span><span class="sxs-lookup"><span data-stu-id="f619e-131">Click the data point you're interested in to drill through to SBC- or user-level details.</span></span>
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="顯示資料點上的深入功能之螢幕擷取畫面":::


## <a name="pstn-overview"></a><span data-ttu-id="f619e-133">PSTN 概觀</span><span class="sxs-lookup"><span data-stu-id="f619e-133">PSTN Overview</span></span>

<span data-ttu-id="f619e-134">CQD PSTN 直接路由報告提供下列與過去 180 天服務整體健康情況有關的資訊。</span><span class="sxs-lookup"><span data-stu-id="f619e-134">The CQD PSTN Direct Routing Report provides the following information related to overall health of the service for the past 180 days.</span></span>
<span data-ttu-id="f619e-135">![螢幕擷取畫面：PSTN CQD 報表](media/CQD-PSTN-report1.png)</span><span class="sxs-lookup"><span data-stu-id="f619e-135">![Screenshot: PSTN CQD report](media/CQD-PSTN-report1.png)</span></span>

<span data-ttu-id="f619e-136">例如，如果您對透過 SBC 撥打的所有來電的整體使用狀況和健康情況感興趣，abc.bca.adatum.biz 美國作為國內國家/地區：</span><span class="sxs-lookup"><span data-stu-id="f619e-136">For example, if you are interested in the overall usage and health about all inbound calls going through SBC abc.bca.adatum.biz with US as the internal country:</span></span>

| <span data-ttu-id="f619e-137">**撥打**</span><span class="sxs-lookup"><span data-stu-id="f619e-137">**Call Out**</span></span> | <span data-ttu-id="f619e-138">**描述**</span><span class="sxs-lookup"><span data-stu-id="f619e-138">**Description**</span></span>                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="f619e-139">1</span><span class="sxs-lookup"><span data-stu-id="f619e-139">1</span></span>            | <span data-ttu-id="f619e-140">您可以使用頂端的篩選向下向下切入，然後選取 ByotIn 做為通話類型、abc.bca.contoso.com 會話 Boarder 控制器，以及美國做為內部國家/地區。</span><span class="sxs-lookup"><span data-stu-id="f619e-140">You can use the filters at the top to drill down and select ByotIn as call type, abc.bca.contoso.com as Session Boarder Controller, and US as internal country.</span></span> |
| <span data-ttu-id="f619e-141">2</span><span class="sxs-lookup"><span data-stu-id="f619e-141">2</span></span>            | <span data-ttu-id="f619e-142">過去 180 天的使用量趨勢。</span><span class="sxs-lookup"><span data-stu-id="f619e-142">Usage trend for the past 180 days.</span></span> <span data-ttu-id="f619e-143">您可以在服務詳細資料頁面上找到使用方式詳細資料包表。</span><span class="sxs-lookup"><span data-stu-id="f619e-143">You can find usage detail report on Service Detail page.</span></span>                                                                     |
| <span data-ttu-id="f619e-144">3</span><span class="sxs-lookup"><span data-stu-id="f619e-144">3</span></span>            | <span data-ttu-id="f619e-145">過去 180 天內的撥號延遲、延遲、抖動和封包遺失趨勢後。</span><span class="sxs-lookup"><span data-stu-id="f619e-145">Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days.</span></span> <span data-ttu-id="f619e-146">您可以在網路參數頁面上找到詳細報告。</span><span class="sxs-lookup"><span data-stu-id="f619e-146">You can find detail report on Network Parameters page.</span></span>                           |
| <span data-ttu-id="f619e-147">4</span><span class="sxs-lookup"><span data-stu-id="f619e-147">4</span></span>            | <span data-ttu-id="f619e-148">過去 180 天的同時通話和每日使用中使用者趨勢。</span><span class="sxs-lookup"><span data-stu-id="f619e-148">Concurrent Call and Daily Active User trend for the past 180 days.</span></span> <span data-ttu-id="f619e-149">此圖表可協助瞭解服務的最大數量。</span><span class="sxs-lookup"><span data-stu-id="f619e-149">This chart can help you understand the max volume of the service.</span></span>                            |
| <span data-ttu-id="f619e-150">5</span><span class="sxs-lookup"><span data-stu-id="f619e-150">5</span></span>            | <span data-ttu-id="f619e-151">熱門通話結束原因影響過去 180 天的服務品質。</span><span class="sxs-lookup"><span data-stu-id="f619e-151">Top Call End Reason affected service quality for the past 180 days.</span></span> <span data-ttu-id="f619e-152">您可以在網路有效比率與 NER (NER) 詳細資料。</span><span class="sxs-lookup"><span data-stu-id="f619e-152">You can find service health detail on Network Effective Ratio(NER) page.</span></span>                    |

## <a name="service-details"></a><span data-ttu-id="f619e-153">服務詳細資料</span><span class="sxs-lookup"><span data-stu-id="f619e-153">Service Details</span></span>

<span data-ttu-id="f619e-154">此頁面提供每天的服務使用趨勢，以及使用者的意見回饋按地理位置分類。</span><span class="sxs-lookup"><span data-stu-id="f619e-154">This page provides service usage trends per day and user feedback breakdown by geographic.</span></span>

  - <span data-ttu-id="f619e-155">**總嘗試通話次數 –** 該時間範圍內的總嘗試通話次數，包括成功和失敗的通話</span><span class="sxs-lookup"><span data-stu-id="f619e-155">**Total Attempt Calls –** Total attempt calls in that time range, including both success and failed calls</span></span>

  - <span data-ttu-id="f619e-156">**已連接通話總數 -** 該時間範圍內已連接的通話總數</span><span class="sxs-lookup"><span data-stu-id="f619e-156">**Total Connected Calls -** Total connected calls in that time range</span></span>

  - <span data-ttu-id="f619e-157">**總分鐘數 –** 該時間範圍內的總分鐘使用量</span><span class="sxs-lookup"><span data-stu-id="f619e-157">**Total Minutes –** Total minute usage in that time range</span></span>

  - <span data-ttu-id="f619e-158">**每日使用中使用者 (DAU) –** 當天至少撥打過一通電話的每日使用中使用者計數</span><span class="sxs-lookup"><span data-stu-id="f619e-158">**Daily Active Users(DAU) –** Count of daily active user who made at least one connected call in that day</span></span>

  - <span data-ttu-id="f619e-159">**同時通話 –** 一分鐘內同時進行中通話的最大值</span><span class="sxs-lookup"><span data-stu-id="f619e-159">**Concurrent Calls –** Max of simultaneous active calls in a minute</span></span>

  - <span data-ttu-id="f619e-160">**使用者意見-** 「我的通話評分」分數來自使用者。</span><span class="sxs-lookup"><span data-stu-id="f619e-160">**User Feedback –** "Rate My Call" score comes from the user.</span></span> <span data-ttu-id="f619e-161">3-5 視為良好的通話。</span><span class="sxs-lookup"><span data-stu-id="f619e-161">3-5 is considered as a good call.</span></span> <span data-ttu-id="f619e-162">1-2 視為錯誤通話。</span><span class="sxs-lookup"><span data-stu-id="f619e-162">1-2 is considered as a bad call.</span></span>

![螢幕擷取畫面：PSTN CQD 報表](media/CQD-PSTN-report2.png)

<span data-ttu-id="f619e-164">例如：</span><span class="sxs-lookup"><span data-stu-id="f619e-164">For example:</span></span>

1.  <span data-ttu-id="f619e-165">如果您看到平均通話持續時間在 2020/02/14 時降低為 0，您可以先檢查通話音量是否正常，並查看總連接通話與總通話次數之間是否有重大差異。</span><span class="sxs-lookup"><span data-stu-id="f619e-165">If you see average call duration drops to 0 at 02/14/2020, you can first check if the call volume looks normal and see if there is a big discrepancy between total connect calls and total attempt calls.</span></span> <span data-ttu-id="f619e-166">接著，請前往網路效能比頁面，以投資通話失敗的原因。</span><span class="sxs-lookup"><span data-stu-id="f619e-166">Then go to Network Effectiveness Ratio page to invest on call failure reasons.</span></span>

2.  <span data-ttu-id="f619e-167">如果您在使用者意見回饋地圖上看到紅點增加，您可以前往網路效能比頁面和網路參數，查看是否有異常情況，您也可以使用 MS Service Desk 提出票證。</span><span class="sxs-lookup"><span data-stu-id="f619e-167">If you see increasing red spots on the user feedback map, you could go to Network Effectiveness Ratio page and Network Parameter to see if there are any anomalies and you could raise a ticket using MS Service Desk.</span></span>

## <a name="network-effectiveness-ratio"></a><span data-ttu-id="f619e-168">網路效能比</span><span class="sxs-lookup"><span data-stu-id="f619e-168">Network Effectiveness Ratio</span></span>

<span data-ttu-id="f619e-169">這是顯示在整體健康情況儀表板上的相同度量。</span><span class="sxs-lookup"><span data-stu-id="f619e-169">This is the same metric that appears on the Overall Health dashboard.</span></span> <span data-ttu-id="f619e-170">您可以在下方的每小時網路效能比和通話結束原因圖表上，檢查每小時 NER 號碼與受影響的來電詳細資料， (來電/) 的來電路線。</span><span class="sxs-lookup"><span data-stu-id="f619e-170">You can check hourly NER number with affected calls detail for both call directions (inbound/outbound) on the Hourly network effectiveness ratio and call ending reason chart below.</span></span>

  - <span data-ttu-id="f619e-171">**NER** - (%) ，測量已傳送的通話數與傳送給收件者的通話數，以傳送通話。</span><span class="sxs-lookup"><span data-stu-id="f619e-171">**NER** - The ability (%) of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>

  - <span data-ttu-id="f619e-172">**SIP 回應程式** 代碼 - 三位數的整數回應程式碼會顯示通話狀態。</span><span class="sxs-lookup"><span data-stu-id="f619e-172">**SIP response code**- A three-digit integer response code shows the call status.</span></span>

  - <span data-ttu-id="f619e-173">**Microsoft 回應代碼**-從 Microsoft 元件所送出的回應代碼。</span><span class="sxs-lookup"><span data-stu-id="f619e-173">**Microsoft response code**-A response code sent out from Microsoft component.</span></span>

  - <span data-ttu-id="f619e-174">**描述** – 對應到 SIP 回應代碼和 Microsoft 回應代碼的原因階段。</span><span class="sxs-lookup"><span data-stu-id="f619e-174">**Description** – The reason phase that corresponding to the SIP response code and Microsoft response code.</span></span>

  - <span data-ttu-id="f619e-175">**受影響的通話數** ： 在所選時間範圍內受影響的通話總數。</span><span class="sxs-lookup"><span data-stu-id="f619e-175">**Number of calls affected** – The total number of calls got affected during the selected time range.</span></span>

> ![螢幕擷取畫面：PSTN CQD 報表](media/CQD-PSTN-report3.png)
> 
<span data-ttu-id="f619e-177">例如：</span><span class="sxs-lookup"><span data-stu-id="f619e-177">For example:</span></span>

![螢幕擷取畫面：PSTN CQD 報表](media/CQD-PSTN-report4.png)

<span data-ttu-id="f619e-179">如果 Daily NER 在 2020/02/05 出現下拉，您可以按一下日期，其他圖表會縮放至該特定日期。</span><span class="sxs-lookup"><span data-stu-id="f619e-179">If Daily NER has a dip on 02/05/2020, you can click on the date and other charts will zoom to that specific date.</span></span>

![螢幕擷取畫面：PSTN CQD 報表](media/CQD-PSTN-report5.png)

<span data-ttu-id="f619e-181">從 NER 良好百分比每小時趨勢中，您可以發現 21：00 左右會發生下拉。</span><span class="sxs-lookup"><span data-stu-id="f619e-181">From the NER Good Percentage Hourly Trend, you can find the dip happens around 21:00.</span></span> <span data-ttu-id="f619e-182">然後再次按一下以縮放至第 21 小時，並檢查 [影響通話詳細資料>，以查看該小時內有多少通話失敗，以及通話結束原因為何。</span><span class="sxs-lookup"><span data-stu-id="f619e-182">Then click again to zoom to hour 21 and check Effected Call Details to see how many calls failed in that hour and what are the call end reasons.</span></span> <span data-ttu-id="f619e-183">您可以在任何 SBC 問題上自行自找問題開始，如果問題與 SBC 沒有關系，也可以向服務台報告。</span><span class="sxs-lookup"><span data-stu-id="f619e-183">You can start with self-trouble shooting on any SBC problems or report to Service Desk if the problem is not related to SBC.</span></span>

## <a name="network-parameters"></a><span data-ttu-id="f619e-184">網路參數</span><span class="sxs-lookup"><span data-stu-id="f619e-184">Network Parameters</span></span>

<span data-ttu-id="f619e-185">所有網路參數都是從直接路由介面到會話邊界控制器測量。</span><span class="sxs-lookup"><span data-stu-id="f619e-185">All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="f619e-186">有關建議值的資訊，請參閱準備貴組織的網路[Microsoft Teams，並](prepare-network.md)查看 Customer Edge 以Microsoft Edge建議的值。</span><span class="sxs-lookup"><span data-stu-id="f619e-186">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

  - <span data-ttu-id="f619e-187">**抖動** – 是使用 RTCP 與 RTP 控制通訊協定 (計算兩個端點之間網路傳播延遲時間變化的毫秒) 。</span><span class="sxs-lookup"><span data-stu-id="f619e-187">**Jitter** – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

  - <span data-ttu-id="f619e-188">**封包** 遺失 – 是未送達的封包量值;這是在兩個端點之間計算。</span><span class="sxs-lookup"><span data-stu-id="f619e-188">**Packet Loss** – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

  - <span data-ttu-id="f619e-189">延遲 **-** (也稱為往返時間) 是訊號的接收時間長度，加上接收該訊號所花的時間長度。</span><span class="sxs-lookup"><span data-stu-id="f619e-189">**Latency** - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="f619e-190">此延遲時間是由訊號兩點之間的傳播時間所組成。</span><span class="sxs-lookup"><span data-stu-id="f619e-190">This time delay consists of the propagation times between the two points of a signal.</span></span>

> ![螢幕擷取畫面：PSTN CQD 報表](media/CQD-PSTN-report6.png)

<span data-ttu-id="f619e-192">例如：</span><span class="sxs-lookup"><span data-stu-id="f619e-192">For example:</span></span>

<span data-ttu-id="f619e-193">如果您在四個圖表上看到特定日期的 (延遲、抖動、封裝遺失率、撥號後延遲) ，例如 2020/02/14 的延遲，請按一下日期點。</span><span class="sxs-lookup"><span data-stu-id="f619e-193">If you see a spike on any of the four charts (Latency, Jitter, Package Loss Rate, Post Dial Delay) for a specific date, for example, Latency on 02/14/2020, click on the date point.</span></span> <span data-ttu-id="f619e-194">而底部的每小時趨勢圖會重新顯示每小時數位。</span><span class="sxs-lookup"><span data-stu-id="f619e-194">And the hourly trend chart at the bottom will refresh to show the hourly number.</span></span> <span data-ttu-id="f619e-195">您可以使用 MS Service Desk 檢查 SBCs 或提出票證。</span><span class="sxs-lookup"><span data-stu-id="f619e-195">You can check the SBCs or raise a ticket with MS Service Desk.</span></span>

![螢幕擷取畫面：PSTN CQD 報表](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a><span data-ttu-id="f619e-197">相關主題</span><span class="sxs-lookup"><span data-stu-id="f619e-197">Related topics</span></span>

[<span data-ttu-id="f619e-198">使用 Power BI 分析 CQD 資料Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f619e-198">Use Power BI to analyze CQD data for Microsoft Teams</span></span>](CQD-PSTN-report.md)

[<span data-ttu-id="f619e-199">Teams 疑難排解</span><span class="sxs-lookup"><span data-stu-id="f619e-199">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)