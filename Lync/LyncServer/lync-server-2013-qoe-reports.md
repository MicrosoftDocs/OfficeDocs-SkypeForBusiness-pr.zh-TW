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
ms.openlocfilehash: 9eead17e9cd08267f941d80cb25460f4d456d896
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="qoe-reports-in-lync-server-2013"></a><span data-ttu-id="2f8eb-102">在 Lync Server 2013 中 QoE 報表</span><span class="sxs-lookup"><span data-stu-id="2f8eb-102">QoE reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f8eb-103">_**主題上次修改日期：** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="2f8eb-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<div>

## <a name="qoe-summarytrend-reports"></a><span data-ttu-id="2f8eb-104">QoE 摘要/趨勢報表</span><span class="sxs-lookup"><span data-stu-id="2f8eb-104">QoE summary/trend reports</span></span>

<span data-ttu-id="2f8eb-105">QoE 摘要/趨勢報告可用於找出一天的高峰使用時間，並在這些時間檢查媒體質量，以協助確保貴組織的網路資源足夠。</span><span class="sxs-lookup"><span data-stu-id="2f8eb-105">The QoE summary/trends reports are useful for finding the peak usage times of day and examining the media quality during those times to help assure that your organization's network resources are sufficient.</span></span> <span data-ttu-id="2f8eb-106">貴組織也可以使用報告中提供的許多篩選器，來隔離特定位置、用戶端和裝置類型以及伺服器的效能數。</span><span class="sxs-lookup"><span data-stu-id="2f8eb-106">Your organization can also use the many filters available in the report to isolate performance numbers for certain locations, client and device types, and servers.</span></span>

<span data-ttu-id="2f8eb-107">QoE 摘要/趨勢報表包括：</span><span class="sxs-lookup"><span data-stu-id="2f8eb-107">QoE summary/trend reports consist of:</span></span>

  - <span data-ttu-id="2f8eb-108">UC 與 UC 摘要/趨勢報告</span><span class="sxs-lookup"><span data-stu-id="2f8eb-108">UC-to-UC Summary/Trend Report</span></span>

  - <span data-ttu-id="2f8eb-109">PSTN 摘要/趨勢報告</span><span class="sxs-lookup"><span data-stu-id="2f8eb-109">PSTN Summary/Trend Report</span></span>

  - <span data-ttu-id="2f8eb-110">會議摘要/趨勢報表</span><span class="sxs-lookup"><span data-stu-id="2f8eb-110">Conference Summary/Trend Report</span></span>

</div>

<div>

## <a name="qoe-performance-reports"></a><span data-ttu-id="2f8eb-111">QoE 效能報告</span><span class="sxs-lookup"><span data-stu-id="2f8eb-111">QoE performance reports</span></span>

<span data-ttu-id="2f8eb-112">QoE 效能報告提供三筆報表的詳細資料，集中精力集中在中繼伺服器、A/V 會議伺服器及端點位置的 QoE 效能。</span><span class="sxs-lookup"><span data-stu-id="2f8eb-112">QoE performance reports provide details about the three reports that concentrate on the QoE performance of Mediation Servers, A/V Conferencing Servers, and endpoint locations.</span></span>

</div>

<div>

## <a name="mediation-server-performance-report"></a><span data-ttu-id="2f8eb-113">中繼伺服器效能報告</span><span class="sxs-lookup"><span data-stu-id="2f8eb-113">Mediation server performance report</span></span>

<span data-ttu-id="2f8eb-114">[採集轉送伺服器效能] 報告會列出在指定期間內由一或多個轉送器所達到的指標。</span><span class="sxs-lookup"><span data-stu-id="2f8eb-114">The Mediation Server Performance report lists the metrics achieved by one or more Mediation during the specified time period.</span></span> <span data-ttu-id="2f8eb-115">整合通訊（UC）到轉送伺服器腿的度量值，以及每個通話的中繼伺服器對閘道腿都是分開報告的。</span><span class="sxs-lookup"><span data-stu-id="2f8eb-115">The metrics for the unified communications (UC)-to-Mediation Server leg and the Mediation Server-to-Gateway leg of each call are reported separately.</span></span> <span data-ttu-id="2f8eb-116">使用此報告來比較貴組織不同中繼伺服器的數量與效能。</span><span class="sxs-lookup"><span data-stu-id="2f8eb-116">Use this report to compare the volume and performance of your organization's various Mediation Servers.</span></span>

<span data-ttu-id="2f8eb-117">針對每個中繼伺服器（以及每個通話腿），報告會顯示下列內容：</span><span class="sxs-lookup"><span data-stu-id="2f8eb-117">For each Mediation Server (and for each call leg), the report displays the following:</span></span>

  - <span data-ttu-id="2f8eb-118">通話次數</span><span class="sxs-lookup"><span data-stu-id="2f8eb-118">Number of calls</span></span>

  - <span data-ttu-id="2f8eb-119">資料包遺失</span><span class="sxs-lookup"><span data-stu-id="2f8eb-119">Packet Loss</span></span>

  - <span data-ttu-id="2f8eb-120">往返行程時間</span><span class="sxs-lookup"><span data-stu-id="2f8eb-120">Round Trip Time</span></span>

  - <span data-ttu-id="2f8eb-121">抖動</span><span class="sxs-lookup"><span data-stu-id="2f8eb-121">Jitter</span></span>

  - <span data-ttu-id="2f8eb-122">會話平均觀念（MOS）</span><span class="sxs-lookup"><span data-stu-id="2f8eb-122">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="2f8eb-123">傳送 MOS</span><span class="sxs-lookup"><span data-stu-id="2f8eb-123">Sending MOS</span></span>

  - <span data-ttu-id="2f8eb-124">聆聽 MOS</span><span class="sxs-lookup"><span data-stu-id="2f8eb-124">Listening MOS</span></span>

  - <span data-ttu-id="2f8eb-125">Network MOS</span><span class="sxs-lookup"><span data-stu-id="2f8eb-125">Network MOS</span></span>

  - <span data-ttu-id="2f8eb-126">網路 MOS 下降</span><span class="sxs-lookup"><span data-stu-id="2f8eb-126">Network MOS Degradation</span></span>

  - <span data-ttu-id="2f8eb-127">回顯傳回</span><span class="sxs-lookup"><span data-stu-id="2f8eb-127">Echo Return</span></span>

  - <span data-ttu-id="2f8eb-128">信號電平</span><span class="sxs-lookup"><span data-stu-id="2f8eb-128">Signal Level</span></span>

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a><span data-ttu-id="2f8eb-129">A/V 會議伺服器效能報告</span><span class="sxs-lookup"><span data-stu-id="2f8eb-129">A/V conferencing server performance report</span></span>

<span data-ttu-id="2f8eb-130">A/V 會議伺服器效能報告提供在指定的時段內，一或多個 A/V 會議伺服器所達到的度量單位清單。</span><span class="sxs-lookup"><span data-stu-id="2f8eb-130">The A/V Conferencing Server Performance report provides lists of metrics achieved by one or more A/V Conferencing Servers during the specified time period.</span></span> <span data-ttu-id="2f8eb-131">此報告可用來比較貴組織的各種 A/V 會議伺服器的音量與效能。</span><span class="sxs-lookup"><span data-stu-id="2f8eb-131">This report can be used to compare the volume and performance of your organization’s various A/V Conferencing Servers.</span></span> <span data-ttu-id="2f8eb-132">您的組織也可以隔離報告，只顯示特定用戶端類型的體驗，例如 Lync 用戶端或 PSTN 用戶端。</span><span class="sxs-lookup"><span data-stu-id="2f8eb-132">Your organization can also isolate the report to show only the experience for specific client types, such as Lync clients or PSTN clients.</span></span>

<span data-ttu-id="2f8eb-133">針對每個 A/V 會議伺服器，報告會顯示下列內容：</span><span class="sxs-lookup"><span data-stu-id="2f8eb-133">For each A/V Conferencing Server, the report displays the following:</span></span>

  - <span data-ttu-id="2f8eb-134">會議數量</span><span class="sxs-lookup"><span data-stu-id="2f8eb-134">Number of conferences</span></span>

  - <span data-ttu-id="2f8eb-135">資料包遺失</span><span class="sxs-lookup"><span data-stu-id="2f8eb-135">Packet Loss</span></span>

  - <span data-ttu-id="2f8eb-136">往返行程時間</span><span class="sxs-lookup"><span data-stu-id="2f8eb-136">Round Trip Time</span></span>

  - <span data-ttu-id="2f8eb-137">抖動</span><span class="sxs-lookup"><span data-stu-id="2f8eb-137">Jitter</span></span>

  - <span data-ttu-id="2f8eb-138">會話平均觀念（MOS）</span><span class="sxs-lookup"><span data-stu-id="2f8eb-138">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="2f8eb-139">傳送 MOS</span><span class="sxs-lookup"><span data-stu-id="2f8eb-139">Sending MOS</span></span>

  - <span data-ttu-id="2f8eb-140">聆聽 MOS</span><span class="sxs-lookup"><span data-stu-id="2f8eb-140">Listening MOS</span></span>

  - <span data-ttu-id="2f8eb-141">Network MOS</span><span class="sxs-lookup"><span data-stu-id="2f8eb-141">Network MOS</span></span>

  - <span data-ttu-id="2f8eb-142">網路 MOS 下降</span><span class="sxs-lookup"><span data-stu-id="2f8eb-142">Network MOS Degradation</span></span>

  - <span data-ttu-id="2f8eb-143">回顯傳回</span><span class="sxs-lookup"><span data-stu-id="2f8eb-143">Echo Return</span></span>

  - <span data-ttu-id="2f8eb-144">信號電平</span><span class="sxs-lookup"><span data-stu-id="2f8eb-144">Signal Level</span></span>

</div>

<div>

## <a name="location-based-performance-report"></a><span data-ttu-id="2f8eb-145">以位置為基礎的效能報告</span><span class="sxs-lookup"><span data-stu-id="2f8eb-145">Location-based performance report</span></span>

<span data-ttu-id="2f8eb-146">以位置為基礎的效能報告會提供網路位置清單，並針對每個位置顯示每個預先確定的品質範圍中的呼叫數目。</span><span class="sxs-lookup"><span data-stu-id="2f8eb-146">The Location-Based Performance report provides a list of network locations and for each location shows the number of calls in each pre-determined range of quality.</span></span> <span data-ttu-id="2f8eb-147">此報告的目的是為了深入瞭解貴組織的各種位置電話通話的媒體質量，讓您能夠找出較差的位置，並查看貴組織中不同的媒體質量等級。不同的位置。</span><span class="sxs-lookup"><span data-stu-id="2f8eb-147">The goal of this report is to provide insight into the media quality of the bulk of your organization’s telephone calls for various locations so that you can identify poorly performing locations, and see the different grades of media quality in your organization’s different locations.</span></span>

<span data-ttu-id="2f8eb-148">顯示報表時，會顯示不同的度量資料表：針對貴組織決定要報告的每個指標，一個資料表。</span><span class="sxs-lookup"><span data-stu-id="2f8eb-148">When displaying the report, different tables of metrics appear—one table for each metric your organization decides to report on.</span></span> <span data-ttu-id="2f8eb-149">您可以從下列度量單位選擇此報告：</span><span class="sxs-lookup"><span data-stu-id="2f8eb-149">You can choose from the following metrics for this report:</span></span>

  - <span data-ttu-id="2f8eb-150">會話平均觀念（MOS）</span><span class="sxs-lookup"><span data-stu-id="2f8eb-150">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="2f8eb-151">Network MOS</span><span class="sxs-lookup"><span data-stu-id="2f8eb-151">Network MOS</span></span>

  - <span data-ttu-id="2f8eb-152">網路 MOS 下降</span><span class="sxs-lookup"><span data-stu-id="2f8eb-152">Network MOS Degradation</span></span>

  - <span data-ttu-id="2f8eb-153">傳送 MOS</span><span class="sxs-lookup"><span data-stu-id="2f8eb-153">Sending MOS</span></span>

  - <span data-ttu-id="2f8eb-154">聆聽 MOS</span><span class="sxs-lookup"><span data-stu-id="2f8eb-154">Listening MOS</span></span>

  - <span data-ttu-id="2f8eb-155">資料包遺失</span><span class="sxs-lookup"><span data-stu-id="2f8eb-155">Packet Loss</span></span>

  - <span data-ttu-id="2f8eb-156">抖動</span><span class="sxs-lookup"><span data-stu-id="2f8eb-156">Jitter</span></span>

  - <span data-ttu-id="2f8eb-157">遲滯</span><span class="sxs-lookup"><span data-stu-id="2f8eb-157">Latency</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

