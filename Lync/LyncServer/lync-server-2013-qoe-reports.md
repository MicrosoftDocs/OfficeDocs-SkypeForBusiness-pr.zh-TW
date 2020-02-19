---
title: 'Lync Server 2013: QoE 報告'
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
ms.openlocfilehash: 9b08544365cf536b791fdfffa5d1d1521a1cc966
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138924"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="qoe-reports-in-lync-server-2013"></a><span data-ttu-id="36d49-102">Lync Server 2013 中的 QoE 報告</span><span class="sxs-lookup"><span data-stu-id="36d49-102">QoE reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36d49-103">_**上次修改主題：** 2014年-05-01_</span><span class="sxs-lookup"><span data-stu-id="36d49-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<div>

## <a name="qoe-summarytrend-reports"></a><span data-ttu-id="36d49-104">QoE 摘要/趨勢報告</span><span class="sxs-lookup"><span data-stu-id="36d49-104">QoE summary/trend reports</span></span>

<span data-ttu-id="36d49-105">QoE 摘要/趨勢報告可以用來尋找每日的尖峰流量時間，並以協助確保貴組織的網路資源即已足夠的這些時段中檢查的媒體品質。</span><span class="sxs-lookup"><span data-stu-id="36d49-105">The QoE summary/trends reports are useful for finding the peak usage times of day and examining the media quality during those times to help assure that your organization's network resources are sufficient.</span></span> <span data-ttu-id="36d49-106">您的組織也可以使用可用報告中的許多篩選器來隔離的特定位置、 用戶端和裝置類型，以及伺服器的效能數字。</span><span class="sxs-lookup"><span data-stu-id="36d49-106">Your organization can also use the many filters available in the report to isolate performance numbers for certain locations, client and device types, and servers.</span></span>

<span data-ttu-id="36d49-107">QoE 摘要/趨勢報告所組成：</span><span class="sxs-lookup"><span data-stu-id="36d49-107">QoE summary/trend reports consist of:</span></span>

  - <span data-ttu-id="36d49-108">UC-UC 摘要/趨勢報告</span><span class="sxs-lookup"><span data-stu-id="36d49-108">UC-to-UC Summary/Trend Report</span></span>

  - <span data-ttu-id="36d49-109">PSTN 摘要/趨勢報告</span><span class="sxs-lookup"><span data-stu-id="36d49-109">PSTN Summary/Trend Report</span></span>

  - <span data-ttu-id="36d49-110">會議摘要/趨勢報告</span><span class="sxs-lookup"><span data-stu-id="36d49-110">Conference Summary/Trend Report</span></span>

</div>

<div>

## <a name="qoe-performance-reports"></a><span data-ttu-id="36d49-111">QoE 效能報告</span><span class="sxs-lookup"><span data-stu-id="36d49-111">QoE performance reports</span></span>

<span data-ttu-id="36d49-112">QoE 效能報告可提供專注的三個報告的詳細 QoE 效能的中繼伺服器，A / V 會議伺服器，並結束點位置。</span><span class="sxs-lookup"><span data-stu-id="36d49-112">QoE performance reports provide details about the three reports that concentrate on the QoE performance of Mediation Servers, A/V Conferencing Servers, and endpoint locations.</span></span>

</div>

<div>

## <a name="mediation-server-performance-report"></a><span data-ttu-id="36d49-113">中繼伺服器效能報告</span><span class="sxs-lookup"><span data-stu-id="36d49-113">Mediation server performance report</span></span>

<span data-ttu-id="36d49-114">中繼伺服器效能報告列出達到指定的時間期間的一或多個中繼的評量。</span><span class="sxs-lookup"><span data-stu-id="36d49-114">The Mediation Server Performance report lists the metrics achieved by one or more Mediation during the specified time period.</span></span> <span data-ttu-id="36d49-115">整合通訊 (UC)-對-中繼伺服器 leg 和每次呼叫中繼伺服器-閘道 leg 計量報告分開。</span><span class="sxs-lookup"><span data-stu-id="36d49-115">The metrics for the unified communications (UC)-to-Mediation Server leg and the Mediation Server-to-Gateway leg of each call are reported separately.</span></span> <span data-ttu-id="36d49-116">使用此報告來比較貴組織的各種中繼伺服器的效能與磁碟區。</span><span class="sxs-lookup"><span data-stu-id="36d49-116">Use this report to compare the volume and performance of your organization's various Mediation Servers.</span></span>

<span data-ttu-id="36d49-117">為每個中繼伺服器 （以及每個通話計量），報表會顯示下列訊息：</span><span class="sxs-lookup"><span data-stu-id="36d49-117">For each Mediation Server (and for each call leg), the report displays the following:</span></span>

  - <span data-ttu-id="36d49-118">通話數目</span><span class="sxs-lookup"><span data-stu-id="36d49-118">Number of calls</span></span>

  - <span data-ttu-id="36d49-119">封包遺失</span><span class="sxs-lookup"><span data-stu-id="36d49-119">Packet Loss</span></span>

  - <span data-ttu-id="36d49-120">來回行程時間</span><span class="sxs-lookup"><span data-stu-id="36d49-120">Round Trip Time</span></span>

  - <span data-ttu-id="36d49-121">抖動</span><span class="sxs-lookup"><span data-stu-id="36d49-121">Jitter</span></span>

  - <span data-ttu-id="36d49-122">交談的平均意見分數 (MOS)</span><span class="sxs-lookup"><span data-stu-id="36d49-122">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="36d49-123">傳送 MOS</span><span class="sxs-lookup"><span data-stu-id="36d49-123">Sending MOS</span></span>

  - <span data-ttu-id="36d49-124">傾聽 MOS</span><span class="sxs-lookup"><span data-stu-id="36d49-124">Listening MOS</span></span>

  - <span data-ttu-id="36d49-125">網路 MOS</span><span class="sxs-lookup"><span data-stu-id="36d49-125">Network MOS</span></span>

  - <span data-ttu-id="36d49-126">網路 MOS 降低的情形</span><span class="sxs-lookup"><span data-stu-id="36d49-126">Network MOS Degradation</span></span>

  - <span data-ttu-id="36d49-127">回音傳回</span><span class="sxs-lookup"><span data-stu-id="36d49-127">Echo Return</span></span>

  - <span data-ttu-id="36d49-128">訊號等級</span><span class="sxs-lookup"><span data-stu-id="36d49-128">Signal Level</span></span>

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a><span data-ttu-id="36d49-129">A / V 會議伺服器效能報告</span><span class="sxs-lookup"><span data-stu-id="36d49-129">A/V conferencing server performance report</span></span>

<span data-ttu-id="36d49-130">A / V 會議伺服器效能報告提供的評量達到一個以上的清單 / V 會議伺服器在指定的時間期間。</span><span class="sxs-lookup"><span data-stu-id="36d49-130">The A/V Conferencing Server Performance report provides lists of metrics achieved by one or more A/V Conferencing Servers during the specified time period.</span></span> <span data-ttu-id="36d49-131">這份報告可用於比較的磁碟區和效能貴組織的各種 A / V 會議伺服器。</span><span class="sxs-lookup"><span data-stu-id="36d49-131">This report can be used to compare the volume and performance of your organization’s various A/V Conferencing Servers.</span></span> <span data-ttu-id="36d49-132">您的組織也可以隔離報表以顯示特定用戶端類型，例如 Lync 用戶端或 PSTN 用戶端體驗。</span><span class="sxs-lookup"><span data-stu-id="36d49-132">Your organization can also isolate the report to show only the experience for specific client types, such as Lync clients or PSTN clients.</span></span>

<span data-ttu-id="36d49-133">每個 a / V 會議伺服器，報表會顯示下列：</span><span class="sxs-lookup"><span data-stu-id="36d49-133">For each A/V Conferencing Server, the report displays the following:</span></span>

  - <span data-ttu-id="36d49-134">會議的數目</span><span class="sxs-lookup"><span data-stu-id="36d49-134">Number of conferences</span></span>

  - <span data-ttu-id="36d49-135">封包遺失</span><span class="sxs-lookup"><span data-stu-id="36d49-135">Packet Loss</span></span>

  - <span data-ttu-id="36d49-136">來回行程時間</span><span class="sxs-lookup"><span data-stu-id="36d49-136">Round Trip Time</span></span>

  - <span data-ttu-id="36d49-137">抖動</span><span class="sxs-lookup"><span data-stu-id="36d49-137">Jitter</span></span>

  - <span data-ttu-id="36d49-138">交談的平均意見分數 (MOS)</span><span class="sxs-lookup"><span data-stu-id="36d49-138">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="36d49-139">傳送 MOS</span><span class="sxs-lookup"><span data-stu-id="36d49-139">Sending MOS</span></span>

  - <span data-ttu-id="36d49-140">傾聽 MOS</span><span class="sxs-lookup"><span data-stu-id="36d49-140">Listening MOS</span></span>

  - <span data-ttu-id="36d49-141">網路 MOS</span><span class="sxs-lookup"><span data-stu-id="36d49-141">Network MOS</span></span>

  - <span data-ttu-id="36d49-142">網路 MOS 降低的情形</span><span class="sxs-lookup"><span data-stu-id="36d49-142">Network MOS Degradation</span></span>

  - <span data-ttu-id="36d49-143">回音傳回</span><span class="sxs-lookup"><span data-stu-id="36d49-143">Echo Return</span></span>

  - <span data-ttu-id="36d49-144">訊號等級</span><span class="sxs-lookup"><span data-stu-id="36d49-144">Signal Level</span></span>

</div>

<div>

## <a name="location-based-performance-report"></a><span data-ttu-id="36d49-145">位置型效能報告</span><span class="sxs-lookup"><span data-stu-id="36d49-145">Location-based performance report</span></span>

<span data-ttu-id="36d49-146">位置型效能報告提供的網路位置，並為每個位置清單會顯示品質的每個預先決定範圍的來電數目。</span><span class="sxs-lookup"><span data-stu-id="36d49-146">The Location-Based Performance report provides a list of network locations and for each location shows the number of calls in each pre-determined range of quality.</span></span> <span data-ttu-id="36d49-147">這份報告的目標是要針對不同位置提供深入的貴組織的電話大量的媒體品質，以便您可以找出執行不良的位置，並在您的組織中看到不同等級的媒體品質不同的位置。</span><span class="sxs-lookup"><span data-stu-id="36d49-147">The goal of this report is to provide insight into the media quality of the bulk of your organization’s telephone calls for various locations so that you can identify poorly performing locations, and see the different grades of media quality in your organization’s different locations.</span></span>

<span data-ttu-id="36d49-148">不同的度量資訊的資料表時顯示的報告，顯示 — 為每個評量的一個資料表貴組織決定報告。</span><span class="sxs-lookup"><span data-stu-id="36d49-148">When displaying the report, different tables of metrics appear—one table for each metric your organization decides to report on.</span></span> <span data-ttu-id="36d49-149">您可以選擇此報告計量：</span><span class="sxs-lookup"><span data-stu-id="36d49-149">You can choose from the following metrics for this report:</span></span>

  - <span data-ttu-id="36d49-150">交談的平均意見分數 (MOS)</span><span class="sxs-lookup"><span data-stu-id="36d49-150">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="36d49-151">網路 MOS</span><span class="sxs-lookup"><span data-stu-id="36d49-151">Network MOS</span></span>

  - <span data-ttu-id="36d49-152">網路 MOS 降低的情形</span><span class="sxs-lookup"><span data-stu-id="36d49-152">Network MOS Degradation</span></span>

  - <span data-ttu-id="36d49-153">傳送 MOS</span><span class="sxs-lookup"><span data-stu-id="36d49-153">Sending MOS</span></span>

  - <span data-ttu-id="36d49-154">傾聽 MOS</span><span class="sxs-lookup"><span data-stu-id="36d49-154">Listening MOS</span></span>

  - <span data-ttu-id="36d49-155">封包遺失</span><span class="sxs-lookup"><span data-stu-id="36d49-155">Packet Loss</span></span>

  - <span data-ttu-id="36d49-156">抖動</span><span class="sxs-lookup"><span data-stu-id="36d49-156">Jitter</span></span>

  - <span data-ttu-id="36d49-157">延遲</span><span class="sxs-lookup"><span data-stu-id="36d49-157">Latency</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

