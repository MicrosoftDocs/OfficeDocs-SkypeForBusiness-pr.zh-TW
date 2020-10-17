---
title: Lync Server 2013： QoE 報告
description: Lync Server 2013： QoE 報告。
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
ms.openlocfilehash: 55965d246b7f0ddd71eaeeec99d218eaf8819c2e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571399"
---
# <a name="qoe-reports-in-lync-server-2013"></a><span data-ttu-id="7e983-103">在 Lync Server 2013 中 QoE 報告</span><span class="sxs-lookup"><span data-stu-id="7e983-103">QoE reports in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e983-104">_**主題上次修改日期：** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="7e983-104">_**Topic Last Modified:** 2014-05-01_</span></span>

<div>

## <a name="qoe-summarytrend-reports"></a><span data-ttu-id="7e983-105">QoE 摘要/趨勢報表</span><span class="sxs-lookup"><span data-stu-id="7e983-105">QoE summary/trend reports</span></span>

<span data-ttu-id="7e983-106">QoE 摘要/趨勢報告可用於尋找一天的峰使用時間，並檢查媒體質量，以協助確保組織的網路資源足夠。</span><span class="sxs-lookup"><span data-stu-id="7e983-106">The QoE summary/trends reports are useful for finding the peak usage times of day and examining the media quality during those times to help assure that your organization's network resources are sufficient.</span></span> <span data-ttu-id="7e983-107">您的組織也可以使用報告中提供的眾多篩選器，隔離特定位置、用戶端和裝置類型及伺服器的效能號碼。</span><span class="sxs-lookup"><span data-stu-id="7e983-107">Your organization can also use the many filters available in the report to isolate performance numbers for certain locations, client and device types, and servers.</span></span>

<span data-ttu-id="7e983-108">QoE 摘要/趨勢報告包含：</span><span class="sxs-lookup"><span data-stu-id="7e983-108">QoE summary/trend reports consist of:</span></span>

  - <span data-ttu-id="7e983-109">UC 對 UC 摘要/趨勢報告</span><span class="sxs-lookup"><span data-stu-id="7e983-109">UC-to-UC Summary/Trend Report</span></span>

  - <span data-ttu-id="7e983-110">PSTN 摘要/趨勢報告</span><span class="sxs-lookup"><span data-stu-id="7e983-110">PSTN Summary/Trend Report</span></span>

  - <span data-ttu-id="7e983-111">會議摘要/趨勢報告</span><span class="sxs-lookup"><span data-stu-id="7e983-111">Conference Summary/Trend Report</span></span>

</div>

<div>

## <a name="qoe-performance-reports"></a><span data-ttu-id="7e983-112">QoE 效能報告</span><span class="sxs-lookup"><span data-stu-id="7e983-112">QoE performance reports</span></span>

<span data-ttu-id="7e983-113">QoE 效能報告提供三個報告的詳細資訊，這些報告著重于轉送伺服器、A/V 會議伺服器及端點位置的 QoE 效能。</span><span class="sxs-lookup"><span data-stu-id="7e983-113">QoE performance reports provide details about the three reports that concentrate on the QoE performance of Mediation Servers, A/V Conferencing Servers, and endpoint locations.</span></span>

</div>

<div>

## <a name="mediation-server-performance-report"></a><span data-ttu-id="7e983-114">轉送伺服器效能報告</span><span class="sxs-lookup"><span data-stu-id="7e983-114">Mediation server performance report</span></span>

<span data-ttu-id="7e983-115">轉送伺服器效能報告會列出在指定期間內，一或多個中繼所取得的計量。</span><span class="sxs-lookup"><span data-stu-id="7e983-115">The Mediation Server Performance report lists the metrics achieved by one or more Mediation during the specified time period.</span></span> <span data-ttu-id="7e983-116">整合通訊 (UC) 對轉送伺服器腿的計量，以及每個通話的轉送伺服器對閘道腿會分開報告。</span><span class="sxs-lookup"><span data-stu-id="7e983-116">The metrics for the unified communications (UC)-to-Mediation Server leg and the Mediation Server-to-Gateway leg of each call are reported separately.</span></span> <span data-ttu-id="7e983-117">使用此報告可比較組織的各種轉送伺服器的數量與效能。</span><span class="sxs-lookup"><span data-stu-id="7e983-117">Use this report to compare the volume and performance of your organization's various Mediation Servers.</span></span>

<span data-ttu-id="7e983-118">針對每個轉送伺服器 (和每個呼叫腿) ，該報告會顯示下列專案：</span><span class="sxs-lookup"><span data-stu-id="7e983-118">For each Mediation Server (and for each call leg), the report displays the following:</span></span>

  - <span data-ttu-id="7e983-119">通話數目</span><span class="sxs-lookup"><span data-stu-id="7e983-119">Number of calls</span></span>

  - <span data-ttu-id="7e983-120">封包遺失</span><span class="sxs-lookup"><span data-stu-id="7e983-120">Packet Loss</span></span>

  - <span data-ttu-id="7e983-121">來回時間</span><span class="sxs-lookup"><span data-stu-id="7e983-121">Round Trip Time</span></span>

  - <span data-ttu-id="7e983-122">抖動</span><span class="sxs-lookup"><span data-stu-id="7e983-122">Jitter</span></span>

  - <span data-ttu-id="7e983-123">MOS) 的平均觀點 (</span><span class="sxs-lookup"><span data-stu-id="7e983-123">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="7e983-124">傳送 MOS</span><span class="sxs-lookup"><span data-stu-id="7e983-124">Sending MOS</span></span>

  - <span data-ttu-id="7e983-125">聆聽 MOS</span><span class="sxs-lookup"><span data-stu-id="7e983-125">Listening MOS</span></span>

  - <span data-ttu-id="7e983-126">網路 MOS</span><span class="sxs-lookup"><span data-stu-id="7e983-126">Network MOS</span></span>

  - <span data-ttu-id="7e983-127">網路 MOS 降級</span><span class="sxs-lookup"><span data-stu-id="7e983-127">Network MOS Degradation</span></span>

  - <span data-ttu-id="7e983-128">回復傳回</span><span class="sxs-lookup"><span data-stu-id="7e983-128">Echo Return</span></span>

  - <span data-ttu-id="7e983-129">信號層級</span><span class="sxs-lookup"><span data-stu-id="7e983-129">Signal Level</span></span>

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a><span data-ttu-id="7e983-130">A/V 會議伺服器效能報告</span><span class="sxs-lookup"><span data-stu-id="7e983-130">A/V conferencing server performance report</span></span>

<span data-ttu-id="7e983-131">A/V 會議伺服器效能報告提供一或多個 A/V 會議伺服器在指定期間內取得的計量清單。</span><span class="sxs-lookup"><span data-stu-id="7e983-131">The A/V Conferencing Server Performance report provides lists of metrics achieved by one or more A/V Conferencing Servers during the specified time period.</span></span> <span data-ttu-id="7e983-132">您可以使用此報告來比較組織的各種 A/V 會議伺服器的數量與效能。</span><span class="sxs-lookup"><span data-stu-id="7e983-132">This report can be used to compare the volume and performance of your organization’s various A/V Conferencing Servers.</span></span> <span data-ttu-id="7e983-133">您的組織也可以隔離報告，只顯示特定用戶端類型的經驗，例如 Lync 用戶端或 PSTN 用戶端。</span><span class="sxs-lookup"><span data-stu-id="7e983-133">Your organization can also isolate the report to show only the experience for specific client types, such as Lync clients or PSTN clients.</span></span>

<span data-ttu-id="7e983-134">針對每個 A/V 會議伺服器，報表會顯示下列專案：</span><span class="sxs-lookup"><span data-stu-id="7e983-134">For each A/V Conferencing Server, the report displays the following:</span></span>

  - <span data-ttu-id="7e983-135">會議數目</span><span class="sxs-lookup"><span data-stu-id="7e983-135">Number of conferences</span></span>

  - <span data-ttu-id="7e983-136">封包遺失</span><span class="sxs-lookup"><span data-stu-id="7e983-136">Packet Loss</span></span>

  - <span data-ttu-id="7e983-137">來回時間</span><span class="sxs-lookup"><span data-stu-id="7e983-137">Round Trip Time</span></span>

  - <span data-ttu-id="7e983-138">抖動</span><span class="sxs-lookup"><span data-stu-id="7e983-138">Jitter</span></span>

  - <span data-ttu-id="7e983-139">MOS) 的平均觀點 (</span><span class="sxs-lookup"><span data-stu-id="7e983-139">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="7e983-140">傳送 MOS</span><span class="sxs-lookup"><span data-stu-id="7e983-140">Sending MOS</span></span>

  - <span data-ttu-id="7e983-141">聆聽 MOS</span><span class="sxs-lookup"><span data-stu-id="7e983-141">Listening MOS</span></span>

  - <span data-ttu-id="7e983-142">網路 MOS</span><span class="sxs-lookup"><span data-stu-id="7e983-142">Network MOS</span></span>

  - <span data-ttu-id="7e983-143">網路 MOS 降級</span><span class="sxs-lookup"><span data-stu-id="7e983-143">Network MOS Degradation</span></span>

  - <span data-ttu-id="7e983-144">回復傳回</span><span class="sxs-lookup"><span data-stu-id="7e983-144">Echo Return</span></span>

  - <span data-ttu-id="7e983-145">信號層級</span><span class="sxs-lookup"><span data-stu-id="7e983-145">Signal Level</span></span>

</div>

<div>

## <a name="location-based-performance-report"></a><span data-ttu-id="7e983-146">以位置為基礎的效能報告</span><span class="sxs-lookup"><span data-stu-id="7e983-146">Location-based performance report</span></span>

<span data-ttu-id="7e983-147">Location-Based 效能報告可提供網路位置清單，並針對每個位置顯示每個預先決定的品質範圍中的呼叫數目。</span><span class="sxs-lookup"><span data-stu-id="7e983-147">The Location-Based Performance report provides a list of network locations and for each location shows the number of calls in each pre-determined range of quality.</span></span> <span data-ttu-id="7e983-148">這份報告的目標是針對不同的位置提供大量組織通話的媒體質量深入瞭解，使您能夠識別出不良的位置，並在組織的不同位置查看不同的媒體質量等級。</span><span class="sxs-lookup"><span data-stu-id="7e983-148">The goal of this report is to provide insight into the media quality of the bulk of your organization’s telephone calls for various locations so that you can identify poorly performing locations, and see the different grades of media quality in your organization’s different locations.</span></span>

<span data-ttu-id="7e983-149">顯示報表時，會顯示不同的計量表-您的組織決定要報告的每個度量各有一個資料表。</span><span class="sxs-lookup"><span data-stu-id="7e983-149">When displaying the report, different tables of metrics appear—one table for each metric your organization decides to report on.</span></span> <span data-ttu-id="7e983-150">您可以從下列度量值中選擇此報告：</span><span class="sxs-lookup"><span data-stu-id="7e983-150">You can choose from the following metrics for this report:</span></span>

  - <span data-ttu-id="7e983-151">MOS) 的平均觀點 (</span><span class="sxs-lookup"><span data-stu-id="7e983-151">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="7e983-152">網路 MOS</span><span class="sxs-lookup"><span data-stu-id="7e983-152">Network MOS</span></span>

  - <span data-ttu-id="7e983-153">網路 MOS 降級</span><span class="sxs-lookup"><span data-stu-id="7e983-153">Network MOS Degradation</span></span>

  - <span data-ttu-id="7e983-154">傳送 MOS</span><span class="sxs-lookup"><span data-stu-id="7e983-154">Sending MOS</span></span>

  - <span data-ttu-id="7e983-155">聆聽 MOS</span><span class="sxs-lookup"><span data-stu-id="7e983-155">Listening MOS</span></span>

  - <span data-ttu-id="7e983-156">封包遺失</span><span class="sxs-lookup"><span data-stu-id="7e983-156">Packet Loss</span></span>

  - <span data-ttu-id="7e983-157">抖動</span><span class="sxs-lookup"><span data-stu-id="7e983-157">Jitter</span></span>

  - <span data-ttu-id="7e983-158">延遲</span><span class="sxs-lookup"><span data-stu-id="7e983-158">Latency</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

