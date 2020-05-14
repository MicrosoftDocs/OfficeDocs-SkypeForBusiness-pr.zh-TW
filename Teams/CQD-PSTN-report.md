---
title: 使用 CQD PSTN Direct 路由報告
ms.author: lolaj
author: LolaJacobsen
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
description: 使用 CQD PSTN Direct 路由報告來監控並疑難排解 Microsoft 團隊中的 PSTN 通話。
ms.openlocfilehash: a3a7d84a21858b8cb2039f3f5bb6efde6b9adaaa
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221747"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a><span data-ttu-id="304b8-103">使用 CQD PSTN Direct 路由報告</span><span class="sxs-lookup"><span data-stu-id="304b8-103">Using the CQD PSTN Direct Routing report</span></span>

<span data-ttu-id="304b8-104">我們已在2020年3月新增 CQD PSTN Direct 路由報告，以供您下載[的 POWER BI 查詢範本 FOR CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="304b8-104">New in March 2020, we've added a CQD PSTN Direct Routing report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 


<span data-ttu-id="304b8-105">CQD PSTN Direct 路由報告（CQD PSTN 直向路由報告 pbit）可協助您瞭解 PSTN 服務的使用模式與品質。</span><span class="sxs-lookup"><span data-stu-id="304b8-105">The CQD PSTN Direct Routing report (CQD PSTN Direct Routing Report.pbit) helps you understand the usage patterns and quality of your PSTN services.</span></span> <span data-ttu-id="304b8-106">使用此報告可監視服務使用方式、會話邊界控制器（SBC）、電話語音、網路參數及網路效能比率詳細資料的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="304b8-106">Use this report to monitor service usage, information about your Session Border Controller (SBC), the telephony service, network parameters, and Network Effectiveness Ratio details.</span></span> <span data-ttu-id="304b8-107">此資訊可協助您找出問題，包括中斷通話的原因。</span><span class="sxs-lookup"><span data-stu-id="304b8-107">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="304b8-108">例如，您可以看到 [音量下降]，或多少通話受到影響，以及原因。</span><span class="sxs-lookup"><span data-stu-id="304b8-108">For example, you'll be able to see when volume drops, or how many calls get affected and for what reason.</span></span>


<span data-ttu-id="304b8-109">CQD PSTN Direct 路由報告有四個區段：</span><span class="sxs-lookup"><span data-stu-id="304b8-109">The CQD PSTN Direct Routing Report has four sections:</span></span>

  - [<span data-ttu-id="304b8-110">PSTN 概述</span><span class="sxs-lookup"><span data-stu-id="304b8-110">PSTN Overview</span></span>](#pstn-overview)

  - [<span data-ttu-id="304b8-111">服務詳細資料</span><span class="sxs-lookup"><span data-stu-id="304b8-111">Service Details</span></span>](#service-details)

  - [<span data-ttu-id="304b8-112">網路效能比率</span><span class="sxs-lookup"><span data-stu-id="304b8-112">Network Effectiveness Ratio</span></span>](#network-effectiveness-ratio)

  - [<span data-ttu-id="304b8-113">網路參數</span><span class="sxs-lookup"><span data-stu-id="304b8-113">Network Parameters</span></span>](#network-parameters)

## <a name="highlights"></a><span data-ttu-id="304b8-114">顯著</span><span class="sxs-lookup"><span data-stu-id="304b8-114">Highlights</span></span>

1. <span data-ttu-id="304b8-115">依呼叫類型、SBC、來電者和被叫方國家/地區分析</span><span class="sxs-lookup"><span data-stu-id="304b8-115">Analyze by call type, SBC, caller and callee country</span></span>

   <span data-ttu-id="304b8-116">CQD PSTN Direct 路由報告會針對最近7、30或180天（6個月）的所有半形在您的租使用者上匯總可靠性和使用方式度量單位。</span><span class="sxs-lookup"><span data-stu-id="304b8-116">The CQD PSTN Direct Routing report aggregates reliability and usage metrics for all SBCs on your tenant for the last 7, 30, or 180 days (6 months).</span></span> <span data-ttu-id="304b8-117">您可以依呼叫類型、SBC、來電者和被叫方國家/地區來分析資料。</span><span class="sxs-lookup"><span data-stu-id="304b8-117">You can analyze data by call type, SBC, caller and callee country.</span></span> <span data-ttu-id="304b8-118">如果您對特定的 SBC 或國家/地區感興趣，您可以在選取的時間範圍內，找出趨勢的變更。</span><span class="sxs-lookup"><span data-stu-id="304b8-118">If you're interested in a particular SBC or country, you'll be able to identify changes in trends over the selected time range.</span></span>
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="CQD PSTN Direct 路由報告中可用之篩選的螢幕擷取畫面":::
   
2. <span data-ttu-id="304b8-120">追蹤趨勢</span><span class="sxs-lookup"><span data-stu-id="304b8-120">Track trends</span></span>

    <span data-ttu-id="304b8-121">當您嘗試瞭解服務使用方式及可靠性時，趨勢分析是必要的。</span><span class="sxs-lookup"><span data-stu-id="304b8-121">Trends analysis is essential when trying to understand service usage and reliability.</span></span> <span data-ttu-id="304b8-122">每小時趨勢都提供近時間的外觀，可協助您找出即時事件。</span><span class="sxs-lookup"><span data-stu-id="304b8-122">Hourly trends provide a close look at daily performance, which helps identify real-time incidents.</span></span> <span data-ttu-id="304b8-123">每日趨勢可讓您從長期角度查看您的服務健康情況。</span><span class="sxs-lookup"><span data-stu-id="304b8-123">Daily trends let you see your service health from a long-term perspective.</span></span> <span data-ttu-id="304b8-124">在這兩種模式間移動必須具備適當的資料細微性，這一點很重要。</span><span class="sxs-lookup"><span data-stu-id="304b8-124">It's important to be able to shift between those two modes with appropriate data granularity.</span></span> <span data-ttu-id="304b8-125">CQD PSTN Direct 路由報告提供6個月的趨勢概覽、7天和30天的每日趨勢，以及每小時趨勢，讓您在每個層面上分析效能。</span><span class="sxs-lookup"><span data-stu-id="304b8-125">The CQD PSTN Direct Routing report provides 6-month trends overview, 7- and 30-day daily trends, and hourly trends so you can analyze performance at each level.</span></span>
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="CQD PSTN Direct 路由報告中趨勢圖的螢幕擷取畫面":::

3. <span data-ttu-id="304b8-127">鑽取至 SBC 或使用者層級</span><span class="sxs-lookup"><span data-stu-id="304b8-127">Drill through to SBC or user level</span></span>

   <span data-ttu-id="304b8-128">我們已在 CQD 的許多資料類別中建立鑽取功能，可讓您快速瞭解 SBC 或使用者層級的使用或可靠性發佈。</span><span class="sxs-lookup"><span data-stu-id="304b8-128">We've been building in drill-through capability on many data categories in CQD, which lets you quickly understand usage or reliability distribution at the SBC or user level.</span></span> <span data-ttu-id="304b8-129">透過使用 [鑽取]，您可以快速 poinpoint 問題，並瞭解實際的使用者影響。</span><span class="sxs-lookup"><span data-stu-id="304b8-129">By using drill through, you can quickly poinpoint issues and understand real user impact.</span></span> <span data-ttu-id="304b8-130">CQD PSTN Direct 路由報告功能會在服務詳細資料和網路效能比率指標之間向下切入。</span><span class="sxs-lookup"><span data-stu-id="304b8-130">The CQD PSTN Direct Routing report features drill through on the Service Detail and Network Effectiveness Ratio metrics.</span></span> <span data-ttu-id="304b8-131">按一下您感興趣的資料點，以流覽至 SBC 或使用者層級的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="304b8-131">Click the data point you're interested in to drill through to SBC- or user-level details.</span></span>
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="顯示資料點上的鑽取功能的螢幕擷取畫面":::


## <a name="pstn-overview"></a><span data-ttu-id="304b8-133">PSTN 概述</span><span class="sxs-lookup"><span data-stu-id="304b8-133">PSTN Overview</span></span>

<span data-ttu-id="304b8-134">CQD PSTN Direct 路由報告提供下列與服務的整體健康情況相關的資訊（在過去的180天內）。</span><span class="sxs-lookup"><span data-stu-id="304b8-134">The CQD PSTN Direct Routing Report provides the following information related to overall health of the service for the past 180 days.</span></span>
<span data-ttu-id="304b8-135">![螢幕擷取畫面： PSTN CQD 報告](media/CQD-PSTN-report1.png)</span><span class="sxs-lookup"><span data-stu-id="304b8-135">![Screenshot: PSTN CQD report](media/CQD-PSTN-report1.png)</span></span>

<span data-ttu-id="304b8-136">例如，如果您對透過 SBC abc.bca.adatum.biz 進行的所有撥出電話的整體使用量和健康情況感興趣，我們就是內部國家/地區：</span><span class="sxs-lookup"><span data-stu-id="304b8-136">For example, if you are interested in the overall usage and health about all inbound calls going through SBC abc.bca.adatum.biz with US as the internal country:</span></span>

| <span data-ttu-id="304b8-137">**撥出**</span><span class="sxs-lookup"><span data-stu-id="304b8-137">**Call Out**</span></span> | <span data-ttu-id="304b8-138">**描述**</span><span class="sxs-lookup"><span data-stu-id="304b8-138">**Description**</span></span>                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="304b8-139">1</span><span class="sxs-lookup"><span data-stu-id="304b8-139">1</span></span>            | <span data-ttu-id="304b8-140">您可以使用上方的篩選來向下切入，然後選取 [ByotIn] 作為 [呼叫類型]、abc.bca.contoso.com [會話 Boarder 控制器]，以及 [美國] 作為內部國家/地區。</span><span class="sxs-lookup"><span data-stu-id="304b8-140">You can use the filters at the top to drill down and select ByotIn as call type, abc.bca.contoso.com as Session Boarder Controller, and US as internal country.</span></span> |
| <span data-ttu-id="304b8-141">2</span><span class="sxs-lookup"><span data-stu-id="304b8-141">2</span></span>            | <span data-ttu-id="304b8-142">過去180天的使用量趨勢。</span><span class="sxs-lookup"><span data-stu-id="304b8-142">Usage trend for the past 180 days.</span></span> <span data-ttu-id="304b8-143">您可以在服務詳細資料頁面找到使用狀況詳細資料包告。</span><span class="sxs-lookup"><span data-stu-id="304b8-143">You can find usage detail report on Service Detail page.</span></span>                                                                     |
| <span data-ttu-id="304b8-144">3</span><span class="sxs-lookup"><span data-stu-id="304b8-144">3</span></span>            | <span data-ttu-id="304b8-145">過去180天后的撥號延遲、延遲、抖動及資料包遺失趨勢。</span><span class="sxs-lookup"><span data-stu-id="304b8-145">Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days.</span></span> <span data-ttu-id="304b8-146">您可以在 [網路參數] 頁面上找到 [詳細資料包表]。</span><span class="sxs-lookup"><span data-stu-id="304b8-146">You can find detail report on Network Parameters page.</span></span>                           |
| <span data-ttu-id="304b8-147">4</span><span class="sxs-lookup"><span data-stu-id="304b8-147">4</span></span>            | <span data-ttu-id="304b8-148">過去180天的同時通話和每日作用中使用者趨勢。</span><span class="sxs-lookup"><span data-stu-id="304b8-148">Concurrent Call and Daily Active User trend for the past 180 days.</span></span> <span data-ttu-id="304b8-149">此圖表可協助您瞭解服務的最大數量。</span><span class="sxs-lookup"><span data-stu-id="304b8-149">This chart can help you understand the max volume of the service.</span></span>                            |
| <span data-ttu-id="304b8-150">500</span><span class="sxs-lookup"><span data-stu-id="304b8-150">5</span></span>            | <span data-ttu-id="304b8-151">上個通話結束原因在過去的180天中受影響的服務品質。</span><span class="sxs-lookup"><span data-stu-id="304b8-151">Top Call End Reason affected service quality for the past 180 days.</span></span> <span data-ttu-id="304b8-152">您可以在 [網路有效比率（NER）] 頁面上找到服務健康情況詳細資料。</span><span class="sxs-lookup"><span data-stu-id="304b8-152">You can find service health detail on Network Effective Ratio(NER) page.</span></span>                    |

## <a name="service-details"></a><span data-ttu-id="304b8-153">服務詳細資料</span><span class="sxs-lookup"><span data-stu-id="304b8-153">Service Details</span></span>

<span data-ttu-id="304b8-154">此頁面提供每天的服務使用趨勢，以及依地理位置的使用者意見反應細分。</span><span class="sxs-lookup"><span data-stu-id="304b8-154">This page provides service usage trends per day and user feedback breakdown by geographic.</span></span>

  - <span data-ttu-id="304b8-155">**總嘗試通話–** 總嘗試在該時間範圍內呼叫，包括成功和失敗的通話</span><span class="sxs-lookup"><span data-stu-id="304b8-155">**Total Attempt Calls –** Total attempt calls in that time range, including both success and failed calls</span></span>

  - <span data-ttu-id="304b8-156">**已連線的通話總數-** 該時間範圍內的連線通話總數</span><span class="sxs-lookup"><span data-stu-id="304b8-156">**Total Connected Calls -** Total connected calls in that time range</span></span>

  - <span data-ttu-id="304b8-157">**總分鐘數–** 該時間範圍內的總分鐘使用量</span><span class="sxs-lookup"><span data-stu-id="304b8-157">**Total Minutes –** Total minute usage in that time range</span></span>

  - <span data-ttu-id="304b8-158">**每日作用中的使用者（DAU）-** 一天中至少進行一個連線通話的每日作用中使用者計數</span><span class="sxs-lookup"><span data-stu-id="304b8-158">**Daily Active Users(DAU) –** Count of daily active user who made at least one connected call in that day</span></span>

  - <span data-ttu-id="304b8-159">**同時通話–** 一分鐘內同時進行中的通話最大值</span><span class="sxs-lookup"><span data-stu-id="304b8-159">**Concurrent Calls –** Max of simultaneous active calls in a minute</span></span>

  - <span data-ttu-id="304b8-160">**使用者意見反應–**「對我的通話打分」分數來自使用者。</span><span class="sxs-lookup"><span data-stu-id="304b8-160">**User Feedback –** "Rate My Call" score comes from the user.</span></span> <span data-ttu-id="304b8-161">3-5 被視為良好的通話。</span><span class="sxs-lookup"><span data-stu-id="304b8-161">3-5 is considered as a good call.</span></span> <span data-ttu-id="304b8-162">1-2 被視為不正確的呼叫。</span><span class="sxs-lookup"><span data-stu-id="304b8-162">1-2 is considered as a bad call.</span></span>

![螢幕擷取畫面： PSTN CQD 報告](media/CQD-PSTN-report2.png)

<span data-ttu-id="304b8-164">例如：</span><span class="sxs-lookup"><span data-stu-id="304b8-164">For example:</span></span>

1.  <span data-ttu-id="304b8-165">如果您在02/14/2020 看到 [平均通話持續時間] 為0，您可以先檢查通話量看起來是否正常，並查看總的連線通話與總嘗試通話之間是否有很大的差異。</span><span class="sxs-lookup"><span data-stu-id="304b8-165">If you see average call duration drops to 0 at 02/14/2020, you can first check if the call volume looks normal and see if there is a big discrepancy between total connect calls and total attempt calls.</span></span> <span data-ttu-id="304b8-166">然後移至 [網路效能比率] 頁面，以投資撥打電話失敗的原因。</span><span class="sxs-lookup"><span data-stu-id="304b8-166">Then go to Network Effectiveness Ratio page to invest on call failure reasons.</span></span>

2.  <span data-ttu-id="304b8-167">如果您在 [使用者意見反應圖] 中看到增加紅色斑點，您可以移至 [網路效能比率] 頁面和 [網路] 參數，查看是否有任何不確定，您可以使用 MS 服務台來提升票證。</span><span class="sxs-lookup"><span data-stu-id="304b8-167">If you see increasing red spots on the user feedback map, you could go to Network Effectiveness Ratio page and Network Parameter to see if there are any anomalies and you could raise a ticket using MS Service Desk.</span></span>

## <a name="network-effectiveness-ratio"></a><span data-ttu-id="304b8-168">網路效能比率</span><span class="sxs-lookup"><span data-stu-id="304b8-168">Network Effectiveness Ratio</span></span>

<span data-ttu-id="304b8-169">這就是顯示在整體健康情況儀表板上的相同指標。</span><span class="sxs-lookup"><span data-stu-id="304b8-169">This is the same metric that appears on the Overall Health dashboard.</span></span> <span data-ttu-id="304b8-170">您可以在每小時網路效能比率中，查看含有受影響通話路線的每小時 NER 數的通話指示（入站/出站），並在下方加上通話結束原因圖表。</span><span class="sxs-lookup"><span data-stu-id="304b8-170">You can check hourly NER number with affected calls detail for both call directions (inbound/outbound) on the Hourly network effectiveness ratio and call ending reason chart below.</span></span>

  - <span data-ttu-id="304b8-171">**NER** -功能（%）透過測量傳送給收件者的呼叫數與傳送給收件者的呼叫次數來傳送通話的網路。</span><span class="sxs-lookup"><span data-stu-id="304b8-171">**NER** - The ability (%) of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>

  - <span data-ttu-id="304b8-172">**SIP 回應程式碼**-三位數的整數回應代碼會顯示通話狀態。</span><span class="sxs-lookup"><span data-stu-id="304b8-172">**SIP response code**- A three-digit integer response code shows the call status.</span></span>

  - <span data-ttu-id="304b8-173">**Microsoft 回應代碼**-從 Microsoft 元件發出回應代碼。</span><span class="sxs-lookup"><span data-stu-id="304b8-173">**Microsoft response code**-A response code sent out from Microsoft component.</span></span>

  - <span data-ttu-id="304b8-174">**描述**：與 SIP 回應代碼及 Microsoft 回應程式碼相對應的原因階段。</span><span class="sxs-lookup"><span data-stu-id="304b8-174">**Description** – The reason phase that corresponding to the SIP response code and Microsoft response code.</span></span>

  - <span data-ttu-id="304b8-175">**受影響的通話數量**-在所選時間範圍內，通話總數量會受到影響。</span><span class="sxs-lookup"><span data-stu-id="304b8-175">**Number of calls affected** – The total number of calls got affected during the selected time range.</span></span>

> ![螢幕擷取畫面： PSTN CQD 報告](media/CQD-PSTN-report3.png)
> 
<span data-ttu-id="304b8-177">例如：</span><span class="sxs-lookup"><span data-stu-id="304b8-177">For example:</span></span>

![螢幕擷取畫面： PSTN CQD 報告](media/CQD-PSTN-report4.png)

<span data-ttu-id="304b8-179">如果 [每日 NER] 在02/05/2020 上有一個 dip，您可以按一下日期，其他圖表就會縮放至該特定日期。</span><span class="sxs-lookup"><span data-stu-id="304b8-179">If Daily NER has a dip on 02/05/2020, you can click on the date and other charts will zoom to that specific date.</span></span>

![螢幕擷取畫面： PSTN CQD 報告](media/CQD-PSTN-report5.png)

<span data-ttu-id="304b8-181">從 NER 良好的每小時趨勢，您可以找出在21:00 周圍發生的 dip。</span><span class="sxs-lookup"><span data-stu-id="304b8-181">From the NER Good Percentage Hourly Trend, you can find the dip happens around 21:00.</span></span> <span data-ttu-id="304b8-182">然後再次按一下以調整為小時21，並查看受影響的通話詳細資料，查看該小時內的通話失敗多少，以及通話結束的原因。</span><span class="sxs-lookup"><span data-stu-id="304b8-182">Then click again to zoom to hour 21 and check Effected Call Details to see how many calls failed in that hour and what are the call end reasons.</span></span> <span data-ttu-id="304b8-183">如果問題不與 SBC 有關，您可以從任何 SBC 問題或向服務台取得報告，開始進行自我疑難排解。</span><span class="sxs-lookup"><span data-stu-id="304b8-183">You can start with self-trouble shooting on any SBC problems or report to Service Desk if the problem is not related to SBC.</span></span>

## <a name="network-parameters"></a><span data-ttu-id="304b8-184">網路參數</span><span class="sxs-lookup"><span data-stu-id="304b8-184">Network Parameters</span></span>

<span data-ttu-id="304b8-185">所有網路參數都是從直接路由介面到會話邊界控制器的測量。</span><span class="sxs-lookup"><span data-stu-id="304b8-185">All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="304b8-186">如需建議值的相關資訊，請參閱為[Microsoft 團隊準備貴組織的網路](prepare-network.md)，並查看客戶邊緣至 microsoft Edge 的建議值。</span><span class="sxs-lookup"><span data-stu-id="304b8-186">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

  - <span data-ttu-id="304b8-187">**抖動**：是在使用 RTCP （RTP 控制通訊協定）的兩個端點之間計算之網路傳播延遲時間變化的毫秒測量。</span><span class="sxs-lookup"><span data-stu-id="304b8-187">**Jitter** – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

  - <span data-ttu-id="304b8-188">**資料包遺失**-是一種無法送達資料包的量度，它是在兩個端點之間計算。</span><span class="sxs-lookup"><span data-stu-id="304b8-188">**Packet Loss** – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

  - <span data-ttu-id="304b8-189">**滯後**時間（也稱為往返行程時間）是傳送信號所需的時間長度，加上接收該信號所需的確認時間長度。</span><span class="sxs-lookup"><span data-stu-id="304b8-189">**Latency** - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="304b8-190">此時間延遲是由兩個信號點之間的傳播時間所組成。</span><span class="sxs-lookup"><span data-stu-id="304b8-190">This time delay consists of the propagation times between the two points of a signal.</span></span>

> ![螢幕擷取畫面： PSTN CQD 報告](media/CQD-PSTN-report6.png)

<span data-ttu-id="304b8-192">例如：</span><span class="sxs-lookup"><span data-stu-id="304b8-192">For example:</span></span>

<span data-ttu-id="304b8-193">如果您在四個圖表的任何一個（延遲、抖動、套件遺失率、Post 延遲）中看到一個峰值，請在02/14/2020 上按一下該日期點。</span><span class="sxs-lookup"><span data-stu-id="304b8-193">If you see a spike on any of the four charts (Latency, Jitter, Package Loss Rate, Post Dial Delay) for a specific date, for example, Latency on 02/14/2020, click on the date point.</span></span> <span data-ttu-id="304b8-194">而底部的每小時趨勢圖將會重新整理，以顯示小時數。</span><span class="sxs-lookup"><span data-stu-id="304b8-194">And the hourly trend chart at the bottom will refresh to show the hourly number.</span></span> <span data-ttu-id="304b8-195">您可以檢查 SBCs，或使用 MS 服務台來提升票證。</span><span class="sxs-lookup"><span data-stu-id="304b8-195">You can check the SBCs or raise a ticket with MS Service Desk.</span></span>

![螢幕擷取畫面： PSTN CQD 報告](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a><span data-ttu-id="304b8-197">相關主題</span><span class="sxs-lookup"><span data-stu-id="304b8-197">Related topics</span></span>

[<span data-ttu-id="304b8-198">使用 Power BI 來分析 Microsoft 團隊的 CQD 資料</span><span class="sxs-lookup"><span data-stu-id="304b8-198">Use Power BI to analyze CQD data for Microsoft Teams</span></span>](CQD-PSTN-report.md)