---
title: Lync Server 2013： QoE 報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoE reports
ms:assetid: 49c827af-b8dd-4c6e-b0dc-b4bc6d60e9a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720913(v=OCS.15)
ms:contentKeyID: 63969601
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69caa96c6f0e49d472f13da11b34f7d199322184
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512180"
---
# <a name="qoe-reports-in-lync-server-2013"></a><span data-ttu-id="6d44a-102">在 Lync Server 2013 中 QoE 報告</span><span class="sxs-lookup"><span data-stu-id="6d44a-102">QoE reports in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d44a-103">_**主題上次修改日期：** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="6d44a-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<div>

## <a name="qoe-summarytrend-reports"></a><span data-ttu-id="6d44a-104">QoE 摘要/趨勢報表</span><span class="sxs-lookup"><span data-stu-id="6d44a-104">QoE summary/trend reports</span></span>

<span data-ttu-id="6d44a-105">QoE 摘要/趨勢報告可用於尋找一天的峰使用時間，並檢查媒體質量，以協助確保組織的網路資源足夠。</span><span class="sxs-lookup"><span data-stu-id="6d44a-105">The QoE summary/trends reports are useful for finding the peak usage times of day and examining the media quality during those times to help assure that your organization's network resources are sufficient.</span></span> <span data-ttu-id="6d44a-106">您的組織也可以使用報告中提供的眾多篩選器，隔離特定位置、用戶端和裝置類型及伺服器的效能號碼。</span><span class="sxs-lookup"><span data-stu-id="6d44a-106">Your organization can also use the many filters available in the report to isolate performance numbers for certain locations, client and device types, and servers.</span></span>

<span data-ttu-id="6d44a-107">QoE 摘要/趨勢報告包含：</span><span class="sxs-lookup"><span data-stu-id="6d44a-107">QoE summary/trend reports consist of:</span></span>

  - <span data-ttu-id="6d44a-108">UC 對 UC 摘要/趨勢報告</span><span class="sxs-lookup"><span data-stu-id="6d44a-108">UC-to-UC Summary/Trend Report</span></span>

  - <span data-ttu-id="6d44a-109">PSTN 摘要/趨勢報告</span><span class="sxs-lookup"><span data-stu-id="6d44a-109">PSTN Summary/Trend Report</span></span>

  - <span data-ttu-id="6d44a-110">會議摘要/趨勢報告</span><span class="sxs-lookup"><span data-stu-id="6d44a-110">Conference Summary/Trend Report</span></span>

</div>

<div>

## <a name="qoe-performance-reports"></a><span data-ttu-id="6d44a-111">QoE 效能報告</span><span class="sxs-lookup"><span data-stu-id="6d44a-111">QoE performance reports</span></span>

<span data-ttu-id="6d44a-112">QoE 效能報告提供三個報告的詳細資訊，這些報告著重于轉送伺服器、A/V 會議伺服器及端點位置的 QoE 效能。</span><span class="sxs-lookup"><span data-stu-id="6d44a-112">QoE performance reports provide details about the three reports that concentrate on the QoE performance of Mediation Servers, A/V Conferencing Servers, and endpoint locations.</span></span>

</div>

<div>

## <a name="mediation-server-performance-report"></a><span data-ttu-id="6d44a-113">轉送伺服器效能報告</span><span class="sxs-lookup"><span data-stu-id="6d44a-113">Mediation server performance report</span></span>

<span data-ttu-id="6d44a-114">轉送伺服器效能報告會列出在指定期間內，一或多個中繼所取得的計量。</span><span class="sxs-lookup"><span data-stu-id="6d44a-114">The Mediation Server Performance report lists the metrics achieved by one or more Mediation during the specified time period.</span></span> <span data-ttu-id="6d44a-115">整合通訊 (UC) 對轉送伺服器腿的計量，以及每個通話的轉送伺服器對閘道腿會分開報告。</span><span class="sxs-lookup"><span data-stu-id="6d44a-115">The metrics for the unified communications (UC)-to-Mediation Server leg and the Mediation Server-to-Gateway leg of each call are reported separately.</span></span> <span data-ttu-id="6d44a-116">使用此報告可比較組織的各種轉送伺服器的數量與效能。</span><span class="sxs-lookup"><span data-stu-id="6d44a-116">Use this report to compare the volume and performance of your organization's various Mediation Servers.</span></span>

<span data-ttu-id="6d44a-117">針對每個轉送伺服器 (和每個呼叫腿) ，該報告會顯示下列專案：</span><span class="sxs-lookup"><span data-stu-id="6d44a-117">For each Mediation Server (and for each call leg), the report displays the following:</span></span>

  - <span data-ttu-id="6d44a-118">通話數目</span><span class="sxs-lookup"><span data-stu-id="6d44a-118">Number of calls</span></span>

  - <span data-ttu-id="6d44a-119">封包遺失</span><span class="sxs-lookup"><span data-stu-id="6d44a-119">Packet Loss</span></span>

  - <span data-ttu-id="6d44a-120">來回時間</span><span class="sxs-lookup"><span data-stu-id="6d44a-120">Round Trip Time</span></span>

  - <span data-ttu-id="6d44a-121">抖動</span><span class="sxs-lookup"><span data-stu-id="6d44a-121">Jitter</span></span>

  - <span data-ttu-id="6d44a-122">MOS) 的平均觀點 (</span><span class="sxs-lookup"><span data-stu-id="6d44a-122">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="6d44a-123">傳送 MOS</span><span class="sxs-lookup"><span data-stu-id="6d44a-123">Sending MOS</span></span>

  - <span data-ttu-id="6d44a-124">聆聽 MOS</span><span class="sxs-lookup"><span data-stu-id="6d44a-124">Listening MOS</span></span>

  - <span data-ttu-id="6d44a-125">網路 MOS</span><span class="sxs-lookup"><span data-stu-id="6d44a-125">Network MOS</span></span>

  - <span data-ttu-id="6d44a-126">網路 MOS 降級</span><span class="sxs-lookup"><span data-stu-id="6d44a-126">Network MOS Degradation</span></span>

  - <span data-ttu-id="6d44a-127">回復傳回</span><span class="sxs-lookup"><span data-stu-id="6d44a-127">Echo Return</span></span>

  - <span data-ttu-id="6d44a-128">信號層級</span><span class="sxs-lookup"><span data-stu-id="6d44a-128">Signal Level</span></span>

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a><span data-ttu-id="6d44a-129">A/V 會議伺服器效能報告</span><span class="sxs-lookup"><span data-stu-id="6d44a-129">A/V conferencing server performance report</span></span>

<span data-ttu-id="6d44a-130">A/V 會議伺服器效能報告提供一或多個 A/V 會議伺服器在指定期間內取得的計量清單。</span><span class="sxs-lookup"><span data-stu-id="6d44a-130">The A/V Conferencing Server Performance report provides lists of metrics achieved by one or more A/V Conferencing Servers during the specified time period.</span></span> <span data-ttu-id="6d44a-131">您可以使用此報告來比較組織的各種 A/V 會議伺服器的數量與效能。</span><span class="sxs-lookup"><span data-stu-id="6d44a-131">This report can be used to compare the volume and performance of your organization’s various A/V Conferencing Servers.</span></span> <span data-ttu-id="6d44a-132">您的組織也可以隔離報告，只顯示特定用戶端類型的經驗，例如 Lync 用戶端或 PSTN 用戶端。</span><span class="sxs-lookup"><span data-stu-id="6d44a-132">Your organization can also isolate the report to show only the experience for specific client types, such as Lync clients or PSTN clients.</span></span>

<span data-ttu-id="6d44a-133">針對每個 A/V 會議伺服器，報表會顯示下列專案：</span><span class="sxs-lookup"><span data-stu-id="6d44a-133">For each A/V Conferencing Server, the report displays the following:</span></span>

  - <span data-ttu-id="6d44a-134">會議數目</span><span class="sxs-lookup"><span data-stu-id="6d44a-134">Number of conferences</span></span>

  - <span data-ttu-id="6d44a-135">封包遺失</span><span class="sxs-lookup"><span data-stu-id="6d44a-135">Packet Loss</span></span>

  - <span data-ttu-id="6d44a-136">來回時間</span><span class="sxs-lookup"><span data-stu-id="6d44a-136">Round Trip Time</span></span>

  - <span data-ttu-id="6d44a-137">抖動</span><span class="sxs-lookup"><span data-stu-id="6d44a-137">Jitter</span></span>

  - <span data-ttu-id="6d44a-138">MOS) 的平均觀點 (</span><span class="sxs-lookup"><span data-stu-id="6d44a-138">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="6d44a-139">傳送 MOS</span><span class="sxs-lookup"><span data-stu-id="6d44a-139">Sending MOS</span></span>

  - <span data-ttu-id="6d44a-140">聆聽 MOS</span><span class="sxs-lookup"><span data-stu-id="6d44a-140">Listening MOS</span></span>

  - <span data-ttu-id="6d44a-141">網路 MOS</span><span class="sxs-lookup"><span data-stu-id="6d44a-141">Network MOS</span></span>

  - <span data-ttu-id="6d44a-142">網路 MOS 降級</span><span class="sxs-lookup"><span data-stu-id="6d44a-142">Network MOS Degradation</span></span>

  - <span data-ttu-id="6d44a-143">回復傳回</span><span class="sxs-lookup"><span data-stu-id="6d44a-143">Echo Return</span></span>

  - <span data-ttu-id="6d44a-144">信號層級</span><span class="sxs-lookup"><span data-stu-id="6d44a-144">Signal Level</span></span>

</div>

<div>

## <a name="location-based-performance-report"></a><span data-ttu-id="6d44a-145">以位置為基礎的效能報告</span><span class="sxs-lookup"><span data-stu-id="6d44a-145">Location-based performance report</span></span>

<span data-ttu-id="6d44a-146">Location-Based 效能報告可提供網路位置清單，並針對每個位置顯示每個預先決定的品質範圍中的呼叫數目。</span><span class="sxs-lookup"><span data-stu-id="6d44a-146">The Location-Based Performance report provides a list of network locations and for each location shows the number of calls in each pre-determined range of quality.</span></span> <span data-ttu-id="6d44a-147">這份報告的目標是針對不同的位置提供大量組織通話的媒體質量深入瞭解，使您能夠識別出不良的位置，並在組織的不同位置查看不同的媒體質量等級。</span><span class="sxs-lookup"><span data-stu-id="6d44a-147">The goal of this report is to provide insight into the media quality of the bulk of your organization’s telephone calls for various locations so that you can identify poorly performing locations, and see the different grades of media quality in your organization’s different locations.</span></span>

<span data-ttu-id="6d44a-148">顯示報表時，會顯示不同的計量表-您的組織決定要報告的每個度量各有一個資料表。</span><span class="sxs-lookup"><span data-stu-id="6d44a-148">When displaying the report, different tables of metrics appear—one table for each metric your organization decides to report on.</span></span> <span data-ttu-id="6d44a-149">您可以從下列度量值中選擇此報告：</span><span class="sxs-lookup"><span data-stu-id="6d44a-149">You can choose from the following metrics for this report:</span></span>

  - <span data-ttu-id="6d44a-150">MOS) 的平均觀點 (</span><span class="sxs-lookup"><span data-stu-id="6d44a-150">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="6d44a-151">網路 MOS</span><span class="sxs-lookup"><span data-stu-id="6d44a-151">Network MOS</span></span>

  - <span data-ttu-id="6d44a-152">網路 MOS 降級</span><span class="sxs-lookup"><span data-stu-id="6d44a-152">Network MOS Degradation</span></span>

  - <span data-ttu-id="6d44a-153">傳送 MOS</span><span class="sxs-lookup"><span data-stu-id="6d44a-153">Sending MOS</span></span>

  - <span data-ttu-id="6d44a-154">聆聽 MOS</span><span class="sxs-lookup"><span data-stu-id="6d44a-154">Listening MOS</span></span>

  - <span data-ttu-id="6d44a-155">封包遺失</span><span class="sxs-lookup"><span data-stu-id="6d44a-155">Packet Loss</span></span>

  - <span data-ttu-id="6d44a-156">抖動</span><span class="sxs-lookup"><span data-stu-id="6d44a-156">Jitter</span></span>

  - <span data-ttu-id="6d44a-157">延遲</span><span class="sxs-lookup"><span data-stu-id="6d44a-157">Latency</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

