---
title: Lync Server 2013：通話詳細資料包告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call Detail Report
ms:assetid: 38862e35-3fec-41b9-a035-0b301942d446
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558637(v=OCS.15)
ms:contentKeyID: 48183843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a258a5c228cfe96218c9c694b05055cc5ebd7eb6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977259"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-detail-report-in-lync-server-2013"></a><span data-ttu-id="8a471-102">在 Lync Server 2013 中呼叫詳細資料包告</span><span class="sxs-lookup"><span data-stu-id="8a471-102">Call Detail Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a471-103">_**主題上次修改日期：** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="8a471-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="8a471-104">[通話詳細資料] 報告提供個別通話的詳細資訊，請參閱報告幾乎包括 Lync Server 收集的所有經驗統計資料和統計資料，分為幾個報表區段，例如：</span><span class="sxs-lookup"><span data-stu-id="8a471-104">The Call Detail Report provides a detailed look at an individual call; the report includes nearly all the Quality of Experience metrics and statistics collected by Lync Server, divided into report sections such as:</span></span>

  - <span data-ttu-id="8a471-105">通話資訊</span><span class="sxs-lookup"><span data-stu-id="8a471-105">Call Information</span></span>

  - <span data-ttu-id="8a471-106">本機號碼裝置與信號規格</span><span class="sxs-lookup"><span data-stu-id="8a471-106">Caller Device and Signal Metrics</span></span>

  - <span data-ttu-id="8a471-107">被呼叫裝置與信號規格</span><span class="sxs-lookup"><span data-stu-id="8a471-107">Callee Device and Signal metrics</span></span>

  - <span data-ttu-id="8a471-108">來電者用戶端事件</span><span class="sxs-lookup"><span data-stu-id="8a471-108">Caller Client Event</span></span>

  - <span data-ttu-id="8a471-109">被呼叫方用戶端事件</span><span class="sxs-lookup"><span data-stu-id="8a471-109">Callee Client Event</span></span>

  - <span data-ttu-id="8a471-110">音訊資料流程（來電者至被叫方）</span><span class="sxs-lookup"><span data-stu-id="8a471-110">Audio Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="8a471-111">影片資料流程（來電者為被叫方）</span><span class="sxs-lookup"><span data-stu-id="8a471-111">Video Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="8a471-112">音訊資料流程（被叫來電者）</span><span class="sxs-lookup"><span data-stu-id="8a471-112">Audio Stream (Callee to Caller)</span></span>

  - <span data-ttu-id="8a471-113">影片串流（被叫來電者）</span><span class="sxs-lookup"><span data-stu-id="8a471-113">Video Stream (Callee to Caller)</span></span>

<span data-ttu-id="8a471-114">請記住，您在指定報告上看到的類別和度量單位，取決於兩個專案：會話類型和會話中使用的端點類型。</span><span class="sxs-lookup"><span data-stu-id="8a471-114">Keep in mind that the categories and the metrics you see on a given report depend on two things: the type of session and the type of endpoints used in the session.</span></span> <span data-ttu-id="8a471-115">例如，音訊專用通話不會報告視頻資料流程的度量單位;這是因為通話沒有影片串流。</span><span class="sxs-lookup"><span data-stu-id="8a471-115">For example, an audio-only call will not report metrics for video streams; that's because the call didn't have a video stream.</span></span> <span data-ttu-id="8a471-116">同樣地，您可能會有一個清單，其中列出本機號碼，但不會列出被叫方統計資料。</span><span class="sxs-lookup"><span data-stu-id="8a471-116">Likewise, you might have a report that lists caller statistics but not callee statistics.</span></span> <span data-ttu-id="8a471-117">這通常是因為被呼叫者不是使用與 SIP 相容的裝置。</span><span class="sxs-lookup"><span data-stu-id="8a471-117">That's typically because the callee was not using a SIP-compliant device.</span></span> <span data-ttu-id="8a471-118">端點負責在通話結束時報告統計資料;不過，手機（不知道 SIP 或 SIP 統計資料）無法報告該類型的資訊。</span><span class="sxs-lookup"><span data-stu-id="8a471-118">Endpoints are responsible for reporting statistics at the end of a call; however, a cell phone (which knows nothing about SIP or SIP statistics) is unable to report that kind of information.</span></span> <span data-ttu-id="8a471-119">如果您打電話給某個人，並在手機上接聽，您就不會在通話結束時從該手機取得報告。</span><span class="sxs-lookup"><span data-stu-id="8a471-119">If you call someone and they answer you on their cell phone, you will not get a report from that cell phone when the call ends.</span></span>

<span data-ttu-id="8a471-120">當您嘗試判斷某個特定呼叫為何遇到媒體質量問題時，通話詳細資料包告最實用。</span><span class="sxs-lookup"><span data-stu-id="8a471-120">The Call Detail Report is most useful when you are trying to determine exactly why a given call experienced media quality problems.</span></span>

<div>

## <a name="accessing-the-call-detail-report"></a><span data-ttu-id="8a471-121">存取通話詳細資料包告</span><span class="sxs-lookup"><span data-stu-id="8a471-121">Accessing the Call Detail Report</span></span>

<span data-ttu-id="8a471-122">您可以從下列任何一種報告存取通話詳細資料包告：</span><span class="sxs-lookup"><span data-stu-id="8a471-122">The Call Detail Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="8a471-123">[Lync Server 2013 中的位置報告](lync-server-2013-location-report.md)（按一下通話量或不佳的通話百分比指標）</span><span class="sxs-lookup"><span data-stu-id="8a471-123">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking either the Call volume or the Poor call percentage metric)</span></span>

  - <span data-ttu-id="8a471-124">[Lync Server 2013 中的 [媒體質量摘要] 報告](lync-server-2013-media-quality-summary-report.md)（按一下通話量或較差的通話百分比指標）</span><span class="sxs-lookup"><span data-stu-id="8a471-124">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="8a471-125">[Lync server 2013 中的媒體質量比較報告](lync-server-2013-media-quality-comparison-report.md)（按一下[lync server 2013 中的 [通話清單] 報告](lync-server-2013-call-list-report.md)，然後按一下 [詳細資料] 度量）。</span><span class="sxs-lookup"><span data-stu-id="8a471-125">The [Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md) (by clicking the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) and then clicking the Detail metric).</span></span>

  - <span data-ttu-id="8a471-126">[Lync server 2013 中的 [伺服器效能報告](lync-server-2013-server-performance-report.md)] （按一下 [通話量] 或 [較差的通話百分比躍點數]）</span><span class="sxs-lookup"><span data-stu-id="8a471-126">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="8a471-127">[Lync Server 2013 中的通話清單報告](lync-server-2013-call-list-report.md)（按一下詳細資料指標）</span><span class="sxs-lookup"><span data-stu-id="8a471-127">The [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) (by clicking the Detail metric)</span></span>

<span data-ttu-id="8a471-128">從 [通話明細] 報告中，您可以按一下下列其中一個度量[單位，以存取 Lync Server 2013 中的裝置報告](lync-server-2013-device-report.md)：</span><span class="sxs-lookup"><span data-stu-id="8a471-128">From within the Call Detail Report you can access the [Device Report in Lync Server 2013](lync-server-2013-device-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="8a471-129">捕獲裝置</span><span class="sxs-lookup"><span data-stu-id="8a471-129">Capture device</span></span>

  - <span data-ttu-id="8a471-130">轉譯裝置</span><span class="sxs-lookup"><span data-stu-id="8a471-130">Render device</span></span>

<span data-ttu-id="8a471-131">您也可以按一下 A/V 邊緣伺服器規格，以存取伺服器媒體質量趨勢報告。</span><span class="sxs-lookup"><span data-stu-id="8a471-131">You can also access the Server Media Quality Trend Report by clicking the A/V edge server metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-detail-report"></a><span data-ttu-id="8a471-132">充分利用 [通話詳細資料] 報告</span><span class="sxs-lookup"><span data-stu-id="8a471-132">Making the Best Use of the Call Detail Report</span></span>

<span data-ttu-id="8a471-133">通話詳細資料包告通常包含超過250的指標，包括麥克風時間戳記偏移、低 SNR 時間等專案，以及靠近結束的迴響時間。</span><span class="sxs-lookup"><span data-stu-id="8a471-133">The Call Detail Report typically includes over 250 different metrics, including such items as Microphone timestamp drift, Low SNR time, and Near end to echo time.</span></span> <span data-ttu-id="8a471-134">如果您不記得這些指標的實際測量，請試著將滑鼠放在公制標籤上;通常會出現工具提示，描述該量度。</span><span class="sxs-lookup"><span data-stu-id="8a471-134">If you can't remember what all of these metrics actually measure, try holding your mouse over the metric label; often-times, a tooltip will appear describing that metric.</span></span>

<span data-ttu-id="8a471-135">如果您無法找到指標，請在搜尋方塊中輸入公制標籤的一部分，然後按一下 [尋找]。</span><span class="sxs-lookup"><span data-stu-id="8a471-135">If you have problems locating a metric, type part of the metric label in the search box and then click Find.</span></span> <span data-ttu-id="8a471-136">例如，如果您找不到低 SNR 時間度量，請在搜尋方塊中輸入 SNR，然後按一下 [尋找]。</span><span class="sxs-lookup"><span data-stu-id="8a471-136">For example, if you can't find the Low SNR time metric, type SNR in the search box and then click Find.</span></span>

<span data-ttu-id="8a471-137">請注意，報告只會追蹤通話的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="8a471-137">Note that the report only tracks information about a call.</span></span> <span data-ttu-id="8a471-138">不會錄製通話本身。</span><span class="sxs-lookup"><span data-stu-id="8a471-138">The call itself is not recorded.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="8a471-139">濾鏡</span><span class="sxs-lookup"><span data-stu-id="8a471-139">Filters</span></span>

<span data-ttu-id="8a471-140">無。</span><span class="sxs-lookup"><span data-stu-id="8a471-140">None.</span></span> <span data-ttu-id="8a471-141">您無法篩選 [通話詳細資料] 報告。</span><span class="sxs-lookup"><span data-stu-id="8a471-141">You cannot filter the Call Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="8a471-142">指標</span><span class="sxs-lookup"><span data-stu-id="8a471-142">Metrics</span></span>

<span data-ttu-id="8a471-143">下表列出每個通話的通話詳細資料包告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="8a471-143">The following table lists the information provided in the Call Detail Report for each call.</span></span>

### <a name="call-detail-report-metrics"></a><span data-ttu-id="8a471-144">通話詳細資料包表度量單位</span><span class="sxs-lookup"><span data-stu-id="8a471-144">Call Detail Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8a471-145">名稱</span><span class="sxs-lookup"><span data-stu-id="8a471-145">Name</span></span></th>
<th><span data-ttu-id="8a471-146">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="8a471-146">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8a471-147">描述</span><span class="sxs-lookup"><span data-stu-id="8a471-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8a471-148"><strong>來電者 PAI</strong></span><span class="sxs-lookup"><span data-stu-id="8a471-148"><strong>Caller PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="8a471-149">否</span><span class="sxs-lookup"><span data-stu-id="8a471-149">No</span></span></p></td>
<td><p><span data-ttu-id="8a471-150">P-已斷言-啟動通話之使用者的身分識別。</span><span class="sxs-lookup"><span data-stu-id="8a471-150">P-Asserted-Identity of the user who initiated the call.</span></span> <span data-ttu-id="8a471-151">P 斷言身分識別是用來傳達受信任網路中的使用者驗證身分識別。</span><span class="sxs-lookup"><span data-stu-id="8a471-151">The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a471-152"><strong>呼叫者 URI</strong></span><span class="sxs-lookup"><span data-stu-id="8a471-152"><strong>Caller URI</strong></span></span></p></td>
<td><p><span data-ttu-id="8a471-153">否</span><span class="sxs-lookup"><span data-stu-id="8a471-153">No</span></span></p></td>
<td><p><span data-ttu-id="8a471-154">啟動通話的使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="8a471-154">SIP address of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a471-155"><strong>來電者端點</strong></span><span class="sxs-lookup"><span data-stu-id="8a471-155"><strong>Caller endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="8a471-156">否</span><span class="sxs-lookup"><span data-stu-id="8a471-156">No</span></span></p></td>
<td><p><span data-ttu-id="8a471-157">用來進行通話的裝置。</span><span class="sxs-lookup"><span data-stu-id="8a471-157">Device used to make the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a471-158"><strong>本機號碼使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="8a471-158"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="8a471-159">否</span><span class="sxs-lookup"><span data-stu-id="8a471-159">No</span></span></p></td>
<td><p><span data-ttu-id="8a471-160">在進行通話的裝置上使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="8a471-160">Software used on the device that made the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a471-161"><strong>呼叫開始</strong></span><span class="sxs-lookup"><span data-stu-id="8a471-161"><strong>Call start</strong></span></span></p></td>
<td><p><span data-ttu-id="8a471-162">否</span><span class="sxs-lookup"><span data-stu-id="8a471-162">No</span></span></p></td>
<td><p><span data-ttu-id="8a471-163">開始撥打電話的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="8a471-163">Date and time that the call was initially placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a471-164"><strong>轉送伺服器旁路通話</strong></span><span class="sxs-lookup"><span data-stu-id="8a471-164"><strong>Mediation Server bypass call</strong></span></span></p></td>
<td><p><span data-ttu-id="8a471-165">否</span><span class="sxs-lookup"><span data-stu-id="8a471-165">No</span></span></p></td>
<td><p><span data-ttu-id="8a471-166">指示該呼叫是連線到 PSTN 語音閘道或合格的 IP-PBX，而不傳遞到轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="8a471-166">Indicates whether the call connected to a PSTN voice gateway or qualified IP-PBX without passing through the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a471-167"><strong>來電者 OS</strong></span><span class="sxs-lookup"><span data-stu-id="8a471-167"><strong>Caller OS</strong></span></span></p></td>
<td><p><span data-ttu-id="8a471-168">否</span><span class="sxs-lookup"><span data-stu-id="8a471-168">No</span></span></p></td>
<td><p><span data-ttu-id="8a471-169">來電者電腦的作業系統。</span><span class="sxs-lookup"><span data-stu-id="8a471-169">Operating system of the caller's computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a471-170"><strong>呼叫者 CPU</strong></span><span class="sxs-lookup"><span data-stu-id="8a471-170"><strong>Caller CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="8a471-171">否</span><span class="sxs-lookup"><span data-stu-id="8a471-171">No</span></span></p></td>
<td><p><span data-ttu-id="8a471-172">啟動通話之使用者的電腦中安裝的 CPU。</span><span class="sxs-lookup"><span data-stu-id="8a471-172">CPU installed in the computer of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a471-173"><strong>來電者 CPU 核心數</strong></span><span class="sxs-lookup"><span data-stu-id="8a471-173"><strong>Caller CPU core number</strong></span></span></p></td>
<td><p><span data-ttu-id="8a471-174">否</span><span class="sxs-lookup"><span data-stu-id="8a471-174">No</span></span></p></td>
<td><p><span data-ttu-id="8a471-175">啟動通話的人員所使用的電腦中的處理器號碼。</span><span class="sxs-lookup"><span data-stu-id="8a471-175">Processor number in the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a471-176"><strong>來電者 CPU 速度</strong></span><span class="sxs-lookup"><span data-stu-id="8a471-176"><strong>Caller CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="8a471-177">否</span><span class="sxs-lookup"><span data-stu-id="8a471-177">No</span></span></p></td>
<td><p><span data-ttu-id="8a471-178">啟動通話之人員所使用之電腦 CPU 的時脈速度。</span><span class="sxs-lookup"><span data-stu-id="8a471-178">Clock speed of the CPU of the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a471-179"><strong>呼叫者 CPU 虛擬化</strong></span><span class="sxs-lookup"><span data-stu-id="8a471-179"><strong>Caller CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="8a471-180">否</span><span class="sxs-lookup"><span data-stu-id="8a471-180">No</span></span></p></td>
<td><p><span data-ttu-id="8a471-181">啟動通話之人員所使用的電腦上使用的虛擬化（如果有）。</span><span class="sxs-lookup"><span data-stu-id="8a471-181">Virtualization (if any) used on the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a471-182"><strong>被呼叫者 PAI</strong></span><span class="sxs-lookup"><span data-stu-id="8a471-182"><strong>Callee PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="8a471-183">否</span><span class="sxs-lookup"><span data-stu-id="8a471-183">No</span></span></p></td>
<td><p><span data-ttu-id="8a471-184">P-宣稱-受邀加入通話的使用者身分識別。</span><span class="sxs-lookup"><span data-stu-id="8a471-184">P-Asserted-Identity of the user who was invited to join the call.</span></span> <span data-ttu-id="8a471-185">P 斷言身分識別是用來傳達受信任網路中的使用者驗證身分識別。</span><span class="sxs-lookup"><span data-stu-id="8a471-185">The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a471-186"><strong>被呼叫方 URI</strong></span><span class="sxs-lookup"><span data-stu-id="8a471-186"><strong>Callee URI</strong></span></span></p></td>
<td><p><span data-ttu-id="8a471-187">否</span><span class="sxs-lookup"><span data-stu-id="8a471-187">No</span></span></p></td>
<td><p><span data-ttu-id="8a471-188">呼叫的使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="8a471-188">SIP address of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a471-189"><strong>被呼叫方端點</strong></span><span class="sxs-lookup"><span data-stu-id="8a471-189"><strong>Callee endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="8a471-190">否</span><span class="sxs-lookup"><span data-stu-id="8a471-190">No</span></span></p></td>
<td><p><span data-ttu-id="8a471-191">用來接收通話的裝置。</span><span class="sxs-lookup"><span data-stu-id="8a471-191">Device used to receive the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a471-192"><strong>被呼叫使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="8a471-192"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="8a471-193">否</span><span class="sxs-lookup"><span data-stu-id="8a471-193">No</span></span></p></td>
<td><p><span data-ttu-id="8a471-194">在已接聽通話的裝置上使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="8a471-194">Software used on the device that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a471-195"><strong>內</strong></span><span class="sxs-lookup"><span data-stu-id="8a471-195"><strong>Duration</strong></span></span></p></td>
<td><p><span data-ttu-id="8a471-196">否</span><span class="sxs-lookup"><span data-stu-id="8a471-196">No</span></span></p></td>
<td><p><span data-ttu-id="8a471-197">通話的時間長度。</span><span class="sxs-lookup"><span data-stu-id="8a471-197">Length of time for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a471-198"><strong>[媒體旁路] 警告標誌</strong></span><span class="sxs-lookup"><span data-stu-id="8a471-198"><strong>Media bypass warning flag</strong></span></span></p></td>
<td><p><span data-ttu-id="8a471-199">否</span><span class="sxs-lookup"><span data-stu-id="8a471-199">No</span></span></p></td>
<td><p><span data-ttu-id="8a471-200">在已略過中繼伺服器時發出的警告。</span><span class="sxs-lookup"><span data-stu-id="8a471-200">Warning issued when the Mediation Server was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a471-201"><strong>被呼叫者 OS</strong></span><span class="sxs-lookup"><span data-stu-id="8a471-201"><strong>Callee OS</strong></span></span></p></td>
<td><p><span data-ttu-id="8a471-202">否</span><span class="sxs-lookup"><span data-stu-id="8a471-202">No</span></span></p></td>
<td><p><span data-ttu-id="8a471-203">已呼叫的使用者的電腦作業系統。</span><span class="sxs-lookup"><span data-stu-id="8a471-203">Operating system of the computer for the user who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a471-204"><strong>被呼叫方 CPU</strong></span><span class="sxs-lookup"><span data-stu-id="8a471-204"><strong>Callee CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="8a471-205">否</span><span class="sxs-lookup"><span data-stu-id="8a471-205">No</span></span></p></td>
<td><p><span data-ttu-id="8a471-206">已在呼叫的使用者電腦上安裝 CPU。</span><span class="sxs-lookup"><span data-stu-id="8a471-206">CPU installed in the computer of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a471-207"><strong>被呼叫方核心電話號碼</strong></span><span class="sxs-lookup"><span data-stu-id="8a471-207"><strong>Callee core number</strong></span></span></p></td>
<td><p><span data-ttu-id="8a471-208">否</span><span class="sxs-lookup"><span data-stu-id="8a471-208">No</span></span></p></td>
<td><p><span data-ttu-id="8a471-209">呼叫者所使用的電腦中的處理器號碼。</span><span class="sxs-lookup"><span data-stu-id="8a471-209">Processor number in the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a471-210"><strong>被呼叫者的 CPU 速度</strong></span><span class="sxs-lookup"><span data-stu-id="8a471-210"><strong>Callee CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="8a471-211">否</span><span class="sxs-lookup"><span data-stu-id="8a471-211">No</span></span></p></td>
<td><p><span data-ttu-id="8a471-212">呼叫者所使用之電腦 CPU 的時脈速度。</span><span class="sxs-lookup"><span data-stu-id="8a471-212">Clock speed of the CPU of the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a471-213"><strong>被佔用的 CPU 虛擬化</strong></span><span class="sxs-lookup"><span data-stu-id="8a471-213"><strong>Callee CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="8a471-214">否</span><span class="sxs-lookup"><span data-stu-id="8a471-214">No</span></span></p></td>
<td><p><span data-ttu-id="8a471-215">在呼叫者所使用的電腦上使用的虛擬化（如果有）。</span><span class="sxs-lookup"><span data-stu-id="8a471-215">Virtualization (if any) used on the computer used by the person who was called.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

