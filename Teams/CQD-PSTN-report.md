---
title: 使用 CQD PSTN Direct 路由報告
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: siunies
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
ms.openlocfilehash: 32d91d56e51c5706c3e460029312f3b6bb6948c3
ms.sourcegitcommit: 98fcfc03c55917d0aca48b7bd97988f81e8930c1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/07/2020
ms.locfileid: "42559422"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a><span data-ttu-id="7886c-103">使用 CQD PSTN Direct 路由報告</span><span class="sxs-lookup"><span data-stu-id="7886c-103">Using the CQD PSTN Direct Routing Report</span></span>

<span data-ttu-id="7886c-104">我們已在2020年3月新增 CQD PSTN Direct 路由報告，以供您下載[的 POWER BI 查詢範本 FOR CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="7886c-104">New in March 2020, we've added a CQD PSTN Direct Routing Report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 


<span data-ttu-id="7886c-105">CQD PSTN Direct 路由報告可協助客戶瞭解有關您的 SBC、電話語音、網路參數及網路效能比率的使用模式與品質的資訊services.</span><span class="sxs-lookup"><span data-stu-id="7886c-105">The CQD PSTN Direct Routing Report helps customers to understand the usage patterns and quality of their PSTN services monitor information about your SBC, the telephony service, the network parameters, and Network Effectiveness Ratio details and usage of the service.</span></span> <span data-ttu-id="7886c-106">此資訊可協助您找出問題，包括中斷通話的原因。</span><span class="sxs-lookup"><span data-stu-id="7886c-106">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="7886c-107">例如，您可以知道何時放下音量，有多少通話會依原因而受到影響。</span><span class="sxs-lookup"><span data-stu-id="7886c-107">For example, you will be able to know when volume drops, how many calls get affected by what reason.</span></span>

<span data-ttu-id="7886c-108">CQD PSTN Direct 路由報告有四個區段：</span><span class="sxs-lookup"><span data-stu-id="7886c-108">The CQD PSTN Direct Routing Report has four sections:</span></span>

  - [<span data-ttu-id="7886c-109">PSTN 概述</span><span class="sxs-lookup"><span data-stu-id="7886c-109">PSTN Overview</span></span>](#pstn-overview)

  - [<span data-ttu-id="7886c-110">服務詳細資料</span><span class="sxs-lookup"><span data-stu-id="7886c-110">Service Details</span></span>](#service-details)

  - [<span data-ttu-id="7886c-111">網路效能比率</span><span class="sxs-lookup"><span data-stu-id="7886c-111">Network Effectiveness Ratio</span></span>](#network-effectiveness-ratio)

  - [<span data-ttu-id="7886c-112">網路參數</span><span class="sxs-lookup"><span data-stu-id="7886c-112">Network Parameters</span></span>](#network-parameters)

## <a name="pstn-overview"></a><span data-ttu-id="7886c-113">PSTN 概述</span><span class="sxs-lookup"><span data-stu-id="7886c-113">PSTN Overview</span></span>

<span data-ttu-id="7886c-114">CQD PSTN Direct 路由報告提供下列與服務的整體健康情況相關的資訊（在過去的180天內）。</span><span class="sxs-lookup"><span data-stu-id="7886c-114">The CQD PSTN Direct Routing Report provides the following information related to overall health of the service for the past 180 days.</span></span>
<span data-ttu-id="7886c-115">![螢幕擷取畫面： PSTN CQD 報告](media/CQD-PSTN-report1.png)</span><span class="sxs-lookup"><span data-stu-id="7886c-115">![Screenshot: PSTN CQD report](media/CQD-PSTN-report1.png)</span></span>

<span data-ttu-id="7886c-116">例如，如果您對透過 SBC abc.bca.adatum.biz 進行的所有撥出電話的整體使用量和健康情況感興趣，我們就是內部國家/地區：</span><span class="sxs-lookup"><span data-stu-id="7886c-116">For example, if you are interested in the overall usage and health about all inbound calls going through SBC abc.bca.adatum.biz with US as the internal country:</span></span>

| <span data-ttu-id="7886c-117">**撥出**</span><span class="sxs-lookup"><span data-stu-id="7886c-117">**Call Out**</span></span> | <span data-ttu-id="7886c-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="7886c-118">**Description**</span></span>                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="7886c-119">1</span><span class="sxs-lookup"><span data-stu-id="7886c-119">1</span></span>            | <span data-ttu-id="7886c-120">您可以使用上方的篩選來向下切入，然後選取 [ByotIn] 作為 [呼叫類型]、abc.bca.contoso.com [會話 Boarder 控制器]，以及 [美國] 作為內部國家/地區。</span><span class="sxs-lookup"><span data-stu-id="7886c-120">You can use the filters at the top to drill down and select ByotIn as call type, abc.bca.contoso.com as Session Boarder Controller, and US as internal country.</span></span> |
| <span data-ttu-id="7886c-121">pplx-2</span><span class="sxs-lookup"><span data-stu-id="7886c-121">2</span></span>            | <span data-ttu-id="7886c-122">過去180天的使用量趨勢。</span><span class="sxs-lookup"><span data-stu-id="7886c-122">Usage trend for the past 180 days.</span></span> <span data-ttu-id="7886c-123">您可以在服務詳細資料頁面找到使用狀況詳細資料包告。</span><span class="sxs-lookup"><span data-stu-id="7886c-123">You can find usage detail report on Service Detail page.</span></span>                                                                     |
| <span data-ttu-id="7886c-124">3</span><span class="sxs-lookup"><span data-stu-id="7886c-124">3</span></span>            | <span data-ttu-id="7886c-125">過去180天后的撥號延遲、延遲、抖動及資料包遺失趨勢。</span><span class="sxs-lookup"><span data-stu-id="7886c-125">Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days.</span></span> <span data-ttu-id="7886c-126">您可以在 [網路參數] 頁面上找到 [詳細資料包表]。</span><span class="sxs-lookup"><span data-stu-id="7886c-126">You can find detail report on Network Parameters page.</span></span>                           |
| <span data-ttu-id="7886c-127">4</span><span class="sxs-lookup"><span data-stu-id="7886c-127">4</span></span>            | <span data-ttu-id="7886c-128">過去180天的同時通話和每日作用中使用者趨勢。</span><span class="sxs-lookup"><span data-stu-id="7886c-128">Concurrent Call and Daily Active User trend for the past 180 days.</span></span> <span data-ttu-id="7886c-129">此圖表可協助您瞭解服務的最大數量。</span><span class="sxs-lookup"><span data-stu-id="7886c-129">This chart can help you understand the max volume of the service.</span></span>                            |
| <span data-ttu-id="7886c-130">500</span><span class="sxs-lookup"><span data-stu-id="7886c-130">5</span></span>            | <span data-ttu-id="7886c-131">上個通話結束原因在過去的180天中受影響的服務品質。</span><span class="sxs-lookup"><span data-stu-id="7886c-131">Top Call End Reason affected service quality for the past 180 days.</span></span> <span data-ttu-id="7886c-132">您可以在 [網路有效比率（NER）] 頁面上找到服務健康情況詳細資料。</span><span class="sxs-lookup"><span data-stu-id="7886c-132">You can find service health detail on Network Effective Ratio(NER) page.</span></span>                    |

## <a name="service-details"></a><span data-ttu-id="7886c-133">服務詳細資料</span><span class="sxs-lookup"><span data-stu-id="7886c-133">Service Details</span></span>

<span data-ttu-id="7886c-134">此頁面提供每天的服務使用趨勢，以及依地理位置的使用者意見反應細分。</span><span class="sxs-lookup"><span data-stu-id="7886c-134">This page provides service usage trends per day and user feedback breakdown by geographic.</span></span>

  - <span data-ttu-id="7886c-135">**總嘗試通話–** 總嘗試在該時間範圍內呼叫，包括成功和失敗的通話</span><span class="sxs-lookup"><span data-stu-id="7886c-135">**Total Attempt Calls –** Total attempt calls in that time range, including both success and failed calls</span></span>

  - <span data-ttu-id="7886c-136">**已連線的通話總數-** 該時間範圍內的連線通話總數</span><span class="sxs-lookup"><span data-stu-id="7886c-136">**Total Connected Calls -** Total connected calls in that time range</span></span>

  - <span data-ttu-id="7886c-137">**總分鐘數–** 該時間範圍內的總分鐘使用量</span><span class="sxs-lookup"><span data-stu-id="7886c-137">**Total Minutes –** Total minute usage in that time range</span></span>

  - <span data-ttu-id="7886c-138">**每日作用中的使用者（DAU）-** 一天中至少進行一個連線通話的每日作用中使用者計數</span><span class="sxs-lookup"><span data-stu-id="7886c-138">**Daily Active Users(DAU) –** Count of daily active user who made at least one connected call in that day</span></span>

  - <span data-ttu-id="7886c-139">**同時通話–** 一分鐘內同時進行中的通話最大值</span><span class="sxs-lookup"><span data-stu-id="7886c-139">**Concurrent Calls –** Max of simultaneous active calls in a minute</span></span>

  - <span data-ttu-id="7886c-140">**使用者意見反應–**「對我的通話打分」分數來自使用者。</span><span class="sxs-lookup"><span data-stu-id="7886c-140">**User Feedback –** "Rate My Call" score comes from the user.</span></span> <span data-ttu-id="7886c-141">3-5 被視為良好的通話。</span><span class="sxs-lookup"><span data-stu-id="7886c-141">3-5 is considered as a good call.</span></span> <span data-ttu-id="7886c-142">1-2 被視為不正確的呼叫。</span><span class="sxs-lookup"><span data-stu-id="7886c-142">1-2 is considered as a bad call.</span></span>

![螢幕擷取畫面： PSTN CQD 報告](media/CQD-PSTN-report2.png)

<span data-ttu-id="7886c-144">例如：</span><span class="sxs-lookup"><span data-stu-id="7886c-144">For example:</span></span>

1.  <span data-ttu-id="7886c-145">如果您在02/14/2020 看到 [平均通話持續時間] 為0，您可以先檢查通話量看起來是否正常，並查看總的連線通話與總嘗試通話之間是否有很大的差異。</span><span class="sxs-lookup"><span data-stu-id="7886c-145">If you see average call duration drops to 0 at 02/14/2020, you can first check if the call volume looks normal and see if there is a big discrepancy between total connect calls and total attempt calls.</span></span> <span data-ttu-id="7886c-146">然後移至 [網路效能比率] 頁面，以投資撥打電話失敗的原因。</span><span class="sxs-lookup"><span data-stu-id="7886c-146">Then go to Network Effectiveness Ratio page to invest on call failure reasons.</span></span>

2.  <span data-ttu-id="7886c-147">如果您在 [使用者意見反應圖] 中看到增加紅色斑點，您可以移至 [網路效能比率] 頁面和 [網路] 參數，查看是否有任何不確定，您可以使用 MS 服務台來提升票證。</span><span class="sxs-lookup"><span data-stu-id="7886c-147">If you see increasing red spots on the user feedback map, you could go to Network Effectiveness Ratio page and Network Parameter to see if there are any anomalies and you could raise a ticket using MS Service Desk.</span></span>

## <a name="network-effectiveness-ratio"></a><span data-ttu-id="7886c-148">網路效能比率</span><span class="sxs-lookup"><span data-stu-id="7886c-148">Network Effectiveness Ratio</span></span>

<span data-ttu-id="7886c-149">這就是顯示在整體健康情況儀表板上的相同指標。</span><span class="sxs-lookup"><span data-stu-id="7886c-149">This is the same metric that appears on the Overall Health dashboard.</span></span> <span data-ttu-id="7886c-150">您可以在每小時網路效能比率中，查看含有受影響通話路線的每小時 NER 數的通話指示（入站/出站），並在下方加上通話結束原因圖表。</span><span class="sxs-lookup"><span data-stu-id="7886c-150">You can check hourly NER number with affected calls detail for both call directions (inbound/outbound) on the Hourly network effectiveness ratio and call ending reason chart below.</span></span>

  - <span data-ttu-id="7886c-151">**NER** -功能（%）透過測量傳送給收件者的呼叫數與傳送給收件者的呼叫次數來傳送通話的網路。</span><span class="sxs-lookup"><span data-stu-id="7886c-151">**NER** - The ability (%) of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>

  - <span data-ttu-id="7886c-152">**SIP 回應程式碼**-三位數的整數回應代碼會顯示通話狀態。</span><span class="sxs-lookup"><span data-stu-id="7886c-152">**SIP response code**- A three-digit integer response code shows the call status.</span></span>

  - <span data-ttu-id="7886c-153">**Microsoft 回應代碼**-從 Microsoft 元件發出回應代碼。</span><span class="sxs-lookup"><span data-stu-id="7886c-153">**Microsoft response code**-A response code sent out from Microsoft component.</span></span>

  - <span data-ttu-id="7886c-154">**描述**：與 SIP 回應代碼及 Microsoft 回應程式碼相對應的原因階段。</span><span class="sxs-lookup"><span data-stu-id="7886c-154">**Description** – The reason phase that corresponding to the SIP response code and Microsoft response code.</span></span>

  - <span data-ttu-id="7886c-155">**受影響的通話數量**-在所選時間範圍內，通話總數量會受到影響。</span><span class="sxs-lookup"><span data-stu-id="7886c-155">**Number of calls affected** – The total number of calls got affected during the selected time range.</span></span>

> ![螢幕擷取畫面： PSTN CQD 報告](media/CQD-PSTN-report3.png)
> 
<span data-ttu-id="7886c-157">例如：</span><span class="sxs-lookup"><span data-stu-id="7886c-157">For example:</span></span>

![螢幕擷取畫面： PSTN CQD 報告](media/CQD-PSTN-report4.png)

<span data-ttu-id="7886c-159">如果 [每日 NER] 在02/05/2020 上有一個 dip，您可以按一下日期，其他圖表就會縮放至該特定日期。</span><span class="sxs-lookup"><span data-stu-id="7886c-159">If Daily NER has a dip on 02/05/2020, you can click on the date and other charts will zoom to that specific date.</span></span>

![螢幕擷取畫面： PSTN CQD 報告](media/CQD-PSTN-report5.png)

<span data-ttu-id="7886c-161">從 NER 良好的每小時趨勢，您可以找出在21:00 周圍發生的 dip。</span><span class="sxs-lookup"><span data-stu-id="7886c-161">From the NER Good Percentage Hourly Trend, you can find the dip happens around 21:00.</span></span> <span data-ttu-id="7886c-162">然後再次按一下以調整為小時21，並查看受影響的通話詳細資料，查看該小時內的通話失敗多少，以及通話結束的原因。</span><span class="sxs-lookup"><span data-stu-id="7886c-162">Then click again to zoom to hour 21 and check Effected Call Details to see how many calls failed in that hour and what are the call end reasons.</span></span> <span data-ttu-id="7886c-163">如果問題不與 SBC 有關，您可以從任何 SBC 問題或向服務台取得報告，開始進行自我疑難排解。</span><span class="sxs-lookup"><span data-stu-id="7886c-163">You can start with self-trouble shooting on any SBC problems or report to Service Desk if the problem is not related to SBC.</span></span>

## <a name="network-parameters"></a><span data-ttu-id="7886c-164">網路參數</span><span class="sxs-lookup"><span data-stu-id="7886c-164">Network Parameters</span></span>

<span data-ttu-id="7886c-165">所有網路參數都是從直接路由介面到會話邊界控制器的測量。</span><span class="sxs-lookup"><span data-stu-id="7886c-165">All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="7886c-166">如需建議值的相關資訊，請參閱為[Microsoft 團隊準備貴組織的網路](prepare-network.md)，並查看客戶邊緣至 microsoft Edge 的建議值。</span><span class="sxs-lookup"><span data-stu-id="7886c-166">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

  - <span data-ttu-id="7886c-167">**抖動**：是在使用 RTCP （RTP 控制通訊協定）的兩個端點之間計算之網路傳播延遲時間變化的毫秒測量。</span><span class="sxs-lookup"><span data-stu-id="7886c-167">**Jitter** – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

  - <span data-ttu-id="7886c-168">**資料包遺失**-是一種無法送達資料包的量度，它是在兩個端點之間計算。</span><span class="sxs-lookup"><span data-stu-id="7886c-168">**Packet Loss** – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

  - <span data-ttu-id="7886c-169">**滯後**時間（也稱為往返行程時間）是傳送信號所需的時間長度，加上接收該信號所需的確認時間長度。</span><span class="sxs-lookup"><span data-stu-id="7886c-169">**Latency** - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="7886c-170">此時間延遲是由兩個信號點之間的傳播時間所組成。</span><span class="sxs-lookup"><span data-stu-id="7886c-170">This time delay consists of the propagation times between the two points of a signal.</span></span>

> ![螢幕擷取畫面： PSTN CQD 報告](media/CQD-PSTN-report6.png)

<span data-ttu-id="7886c-172">例如：</span><span class="sxs-lookup"><span data-stu-id="7886c-172">For example:</span></span>

<span data-ttu-id="7886c-173">如果您在四個圖表的任何一個（延遲、抖動、套件遺失率、Post 延遲）中看到一個峰值，請在02/14/2020 上按一下該日期點。</span><span class="sxs-lookup"><span data-stu-id="7886c-173">If you see a spike on any of the four charts (Latency, Jitter, Package Loss Rate, Post Dial Delay) for a specific date, for example, Latency on 02/14/2020, click on the date point.</span></span> <span data-ttu-id="7886c-174">而底部的每小時趨勢圖將會重新整理，以顯示小時數。</span><span class="sxs-lookup"><span data-stu-id="7886c-174">And the hourly trend chart at the bottom will refresh to show the hourly number.</span></span> <span data-ttu-id="7886c-175">您可以檢查 SBCs，或使用 MS 服務台來提升票證。</span><span class="sxs-lookup"><span data-stu-id="7886c-175">You can check the SBCs or raise a ticket with MS Service Desk.</span></span>

![螢幕擷取畫面： PSTN CQD 報告](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a><span data-ttu-id="7886c-177">相關主題</span><span class="sxs-lookup"><span data-stu-id="7886c-177">Related topics</span></span>

[<span data-ttu-id="7886c-178">使用 Power BI 來分析 Microsoft 團隊的 CQD 資料</span><span class="sxs-lookup"><span data-stu-id="7886c-178">Use Power BI to analyze CQD data for Microsoft Teams</span></span>](CQD-PSTN-report.md)