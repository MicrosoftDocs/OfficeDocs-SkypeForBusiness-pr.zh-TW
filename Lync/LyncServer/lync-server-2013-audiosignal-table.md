---
title: Lync Server 2013：AudioSignal 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AudioSignal table
ms:assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398064(v=OCS.15)
ms:contentKeyID: 48183217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6605a25191906660bbad11908f754a81360c893
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980375"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="b3551-102">Lync Server 2013 中的 AudioSignal 表格</span><span class="sxs-lookup"><span data-stu-id="b3551-102">AudioSignal table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3551-103">_**主題上次修改日期：** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="b3551-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="b3551-104">每個記錄代表一個端點的音訊信號度量單位。</span><span class="sxs-lookup"><span data-stu-id="b3551-104">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="b3551-105">通常，每個通話都有兩筆記錄，一個用於呼叫者，另一個則稱為被叫方。</span><span class="sxs-lookup"><span data-stu-id="b3551-105">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3551-106"><strong>左欄</strong></span><span class="sxs-lookup"><span data-stu-id="b3551-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="b3551-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="b3551-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="b3551-108"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="b3551-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="b3551-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="b3551-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3551-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="b3551-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b3551-111">datetime</span><span class="sxs-lookup"><span data-stu-id="b3551-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="b3551-112">首選</span><span class="sxs-lookup"><span data-stu-id="b3551-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="b3551-113">從<a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="b3551-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3551-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b3551-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b3551-115">int</span><span class="sxs-lookup"><span data-stu-id="b3551-115">int</span></span></p></td>
<td><p><span data-ttu-id="b3551-116">首選</span><span class="sxs-lookup"><span data-stu-id="b3551-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="b3551-117">從<a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="b3551-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3551-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="b3551-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="b3551-119">Tinyint</span><span class="sxs-lookup"><span data-stu-id="b3551-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="b3551-120">首選</span><span class="sxs-lookup"><span data-stu-id="b3551-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="b3551-121">從<a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="b3551-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3551-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="b3551-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="b3551-123">稍微</span><span class="sxs-lookup"><span data-stu-id="b3551-123">bit</span></span></p></td>
<td><p><span data-ttu-id="b3551-124">首選</span><span class="sxs-lookup"><span data-stu-id="b3551-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="b3551-125">0：被方程式的資料</span><span class="sxs-lookup"><span data-stu-id="b3551-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="b3551-126">1：來電者的資料</span><span class="sxs-lookup"><span data-stu-id="b3551-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3551-127"><strong>SendSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="b3551-127"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="b3551-128">int</span><span class="sxs-lookup"><span data-stu-id="b3551-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b3551-129">代表 [反後的類比增益控制音訊信號] 層級。</span><span class="sxs-lookup"><span data-stu-id="b3551-129">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="b3551-130">這個指標的單位是 dBmo。</span><span class="sxs-lookup"><span data-stu-id="b3551-130">The unit for this metric is dBmo.</span></span> <span data-ttu-id="b3551-131">若要取得可接受的品質，至少要有 30 dBmo。</span><span class="sxs-lookup"><span data-stu-id="b3551-131">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="b3551-132">A/V 會議伺服器或 IP 電話不會報告此統計值。</span><span class="sxs-lookup"><span data-stu-id="b3551-132">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3551-133"><strong>RecvSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="b3551-133"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="b3551-134">int</span><span class="sxs-lookup"><span data-stu-id="b3551-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b3551-135">請參閱 SendSignalLevel。</span><span class="sxs-lookup"><span data-stu-id="b3551-135">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3551-136"><strong>SendNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="b3551-136"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="b3551-137">int</span><span class="sxs-lookup"><span data-stu-id="b3551-137">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b3551-138">代表 [反後類比增益控制音訊雜訊] 層級。</span><span class="sxs-lookup"><span data-stu-id="b3551-138">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="b3551-139">這個指標的單位是 dBmo。</span><span class="sxs-lookup"><span data-stu-id="b3551-139">The unit for this metric is dBmo.</span></span> <span data-ttu-id="b3551-140">針對可接受的品質，它應該小於 35 dBmo。</span><span class="sxs-lookup"><span data-stu-id="b3551-140">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="b3551-141">A/V 會議伺服器或 IP 電話不會報告此統計值。</span><span class="sxs-lookup"><span data-stu-id="b3551-141">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3551-142"><strong>RecvNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="b3551-142"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="b3551-143">int</span><span class="sxs-lookup"><span data-stu-id="b3551-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b3551-144">請參閱 SendNoiseLevel。</span><span class="sxs-lookup"><span data-stu-id="b3551-144">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3551-145"><strong>EchoReturn</strong></span><span class="sxs-lookup"><span data-stu-id="b3551-145"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="b3551-146">int</span><span class="sxs-lookup"><span data-stu-id="b3551-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b3551-147">迴響傳回損失增強指標。</span><span class="sxs-lookup"><span data-stu-id="b3551-147">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="b3551-148">這個指標的單位是 dB。</span><span class="sxs-lookup"><span data-stu-id="b3551-148">The unit for this metric is dB.</span></span> <span data-ttu-id="b3551-149">較低的值代表較少的回音。</span><span class="sxs-lookup"><span data-stu-id="b3551-149">Lower values represent less echo.</span></span> <span data-ttu-id="b3551-150">A/V 會議伺服器或 IP 電話不會報告此統計值。</span><span class="sxs-lookup"><span data-stu-id="b3551-150">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3551-151"><strong>AudioSpeakerGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="b3551-151"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="b3551-152">int</span><span class="sxs-lookup"><span data-stu-id="b3551-152">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b3551-153">喇叭前轉譯每五分鐘的平均故障。</span><span class="sxs-lookup"><span data-stu-id="b3551-153">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="b3551-154">若要獲得較高的品質，此頻率應該小於每五分鐘。</span><span class="sxs-lookup"><span data-stu-id="b3551-154">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="b3551-155">無法由 A/V 會議伺服器、中繼伺服器或 IP 電話來報告。</span><span class="sxs-lookup"><span data-stu-id="b3551-155">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3551-156"><strong>AudioMicGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="b3551-156"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="b3551-157">int</span><span class="sxs-lookup"><span data-stu-id="b3551-157">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b3551-158">麥克風捕獲每五分鐘的平均故障。</span><span class="sxs-lookup"><span data-stu-id="b3551-158">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="b3551-159">若要獲得良好的品質，這應該少於每五分鐘一次。</span><span class="sxs-lookup"><span data-stu-id="b3551-159">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="b3551-160">無法由 A/V 會議伺服器、中繼伺服器或 IP 電話來報告。</span><span class="sxs-lookup"><span data-stu-id="b3551-160">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3551-161"><strong>AudioTimestampDriftRateMic</strong></span><span class="sxs-lookup"><span data-stu-id="b3551-161"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="b3551-162">decimal （9，2）</span><span class="sxs-lookup"><span data-stu-id="b3551-162">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b3551-163">麥克風裝置時鐘相對於 CPU 時鐘的時鐘偏移速度。</span><span class="sxs-lookup"><span data-stu-id="b3551-163">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3551-164"><strong>AudioTimestampDriftRateSpk</strong></span><span class="sxs-lookup"><span data-stu-id="b3551-164"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="b3551-165">decimal （9，2）</span><span class="sxs-lookup"><span data-stu-id="b3551-165">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b3551-166">喇叭裝置時鐘相對於 CPU 時鐘的時鐘偏移速度。</span><span class="sxs-lookup"><span data-stu-id="b3551-166">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3551-167"><strong>AudioTimestampErrorMicMs</strong></span><span class="sxs-lookup"><span data-stu-id="b3551-167"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="b3551-168">decimal （9，2）</span><span class="sxs-lookup"><span data-stu-id="b3551-168">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b3551-169">喇叭裝置時鐘相對於 CPU 時鐘的時鐘偏移速度。</span><span class="sxs-lookup"><span data-stu-id="b3551-169">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="b3551-170">在呼叫的最後20秒內，麥克風捕獲串流的時間戳記錯誤（以毫秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="b3551-170">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3551-171"><strong>AudioTimestampErrorSpkMs</strong></span><span class="sxs-lookup"><span data-stu-id="b3551-171"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="b3551-172">decimal （9，2）</span><span class="sxs-lookup"><span data-stu-id="b3551-172">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b3551-173">在呼叫的最後20秒內，演講者轉譯資料流程時間戳記的錯誤（以毫秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="b3551-173">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3551-174"><strong>VsEntryCauses</strong></span><span class="sxs-lookup"><span data-stu-id="b3551-174"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="b3551-175">Smallint</span><span class="sxs-lookup"><span data-stu-id="b3551-175">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b3551-176">Voice 開關是一種半雙工模式，可減少中斷能力。</span><span class="sxs-lookup"><span data-stu-id="b3551-176">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="b3551-177">語音切換專案的原因：</span><span class="sxs-lookup"><span data-stu-id="b3551-177">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="b3551-178">ENTER_VS_BADTS 0x01</span><span class="sxs-lookup"><span data-stu-id="b3551-178">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="b3551-179">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="b3551-179">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="b3551-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span><span class="sxs-lookup"><span data-stu-id="b3551-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="b3551-181">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="b3551-181">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="b3551-182">原因可能是由這些個別原因所組成。</span><span class="sxs-lookup"><span data-stu-id="b3551-182">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="b3551-183">只有在測試用途中，才能啟用 ENTER_VS_FORCEORCONVERGENCE。</span><span class="sxs-lookup"><span data-stu-id="b3551-183">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="b3551-184">此欄的資料類型已在 Microsoft Lync Server 2013 中變更。</span><span class="sxs-lookup"><span data-stu-id="b3551-184">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3551-185"><strong>EchoEventCauses</strong></span><span class="sxs-lookup"><span data-stu-id="b3551-185"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="b3551-186">Tinyint</span><span class="sxs-lookup"><span data-stu-id="b3551-186">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b3551-187">Echo 事件的原因：</span><span class="sxs-lookup"><span data-stu-id="b3551-187">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="b3551-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="b3551-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="b3551-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="b3551-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="b3551-190">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="b3551-190">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="b3551-191">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="b3551-191">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="b3551-192">ECHO_EVENT_MIC_CLIPPING 0x10</span><span class="sxs-lookup"><span data-stu-id="b3551-192">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="b3551-193">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="b3551-193">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="b3551-194">原因可能是由這些個別原因所組成。</span><span class="sxs-lookup"><span data-stu-id="b3551-194">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3551-195"><strong>EchoPercentMicIn</strong></span><span class="sxs-lookup"><span data-stu-id="b3551-195"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="b3551-196">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="b3551-196">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b3551-197">在麥克風捕獲資料流程中檢測到迴響的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="b3551-197">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="b3551-198">通常，耳機或話機的值較低，而喇叭或獨立喇叭的值則較高。</span><span class="sxs-lookup"><span data-stu-id="b3551-198">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="b3551-199">對於支援板載音響回聲取消的裝置，高值表示迴響洩漏。</span><span class="sxs-lookup"><span data-stu-id="b3551-199">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="b3551-200">對於其他裝置，此規格不應該用來評估裝置品質。</span><span class="sxs-lookup"><span data-stu-id="b3551-200">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3551-201"><strong>EchoPercentSend</strong></span><span class="sxs-lookup"><span data-stu-id="b3551-201"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="b3551-202">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="b3551-202">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b3551-203">在傳送資料流程中檢測到迴響的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="b3551-203">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="b3551-204">傳送資料流程中的高迴響百分比表示回應洩漏。</span><span class="sxs-lookup"><span data-stu-id="b3551-204">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3551-205"><strong>RxAGCSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="b3551-205"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="b3551-206">int</span><span class="sxs-lookup"><span data-stu-id="b3551-206">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b3551-207">從閘道在中繼伺服器接收到的信號等級;這只適用于中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="b3551-207">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="b3551-208">這個度量單位是 dBoV。</span><span class="sxs-lookup"><span data-stu-id="b3551-208">The unit of this metric is dBoV.</span></span> <span data-ttu-id="b3551-209">若要獲得良好的品質，可接受的範圍應該是 [-30 至-18] dBoV。</span><span class="sxs-lookup"><span data-stu-id="b3551-209">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3551-210"><strong>RxAGCNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="b3551-210"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="b3551-211">int</span><span class="sxs-lookup"><span data-stu-id="b3551-211">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b3551-212">從閘道在中繼伺服器上收到的信號等級。</span><span class="sxs-lookup"><span data-stu-id="b3551-212">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="b3551-213">這只適用于中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="b3551-213">This applies only to the Mediation Server.</span></span> <span data-ttu-id="b3551-214">這個度量單位是 dBoV。</span><span class="sxs-lookup"><span data-stu-id="b3551-214">The unit of this metric is dBoV.</span></span> <span data-ttu-id="b3551-215">若要獲得良好的品質，可接受的範圍應該小於-50 dBoV。</span><span class="sxs-lookup"><span data-stu-id="b3551-215">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3551-216"><strong>RxAvgAGCGain</strong></span><span class="sxs-lookup"><span data-stu-id="b3551-216"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="b3551-217">int</span><span class="sxs-lookup"><span data-stu-id="b3551-217">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b3551-218">在中繼伺服器端的自動增益控制（AGC）。</span><span class="sxs-lookup"><span data-stu-id="b3551-218">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3551-219"><strong>InitialSignalLevelRMS</strong></span><span class="sxs-lookup"><span data-stu-id="b3551-219"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="b3551-220">浮</span><span class="sxs-lookup"><span data-stu-id="b3551-220">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b3551-221">撥入信號的根平均數（RMS），最多可達呼叫的前30秒。</span><span class="sxs-lookup"><span data-stu-id="b3551-221">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3551-222"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="b3551-222"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="b3551-223">int</span><span class="sxs-lookup"><span data-stu-id="b3551-223">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b3551-224">頻道1上接收到的信號等級。</span><span class="sxs-lookup"><span data-stu-id="b3551-224">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="b3551-225">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="b3551-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3551-226"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="b3551-226"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="b3551-227">int</span><span class="sxs-lookup"><span data-stu-id="b3551-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b3551-228">頻道2上接收到的信號等級。</span><span class="sxs-lookup"><span data-stu-id="b3551-228">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="b3551-229">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="b3551-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3551-230"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="b3551-230"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="b3551-231">int</span><span class="sxs-lookup"><span data-stu-id="b3551-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b3551-232">頻道1上接收到的雜訊等級。</span><span class="sxs-lookup"><span data-stu-id="b3551-232">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="b3551-233">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="b3551-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3551-234"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="b3551-234"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="b3551-235">int</span><span class="sxs-lookup"><span data-stu-id="b3551-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b3551-236">頻道2上接收的噪音等級。</span><span class="sxs-lookup"><span data-stu-id="b3551-236">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="b3551-237">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="b3551-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3551-238"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="b3551-238"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="b3551-239">int</span><span class="sxs-lookup"><span data-stu-id="b3551-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b3551-240">頻道1上傳送的信號等級。</span><span class="sxs-lookup"><span data-stu-id="b3551-240">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="b3551-241">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="b3551-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3551-242"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="b3551-242"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="b3551-243">int</span><span class="sxs-lookup"><span data-stu-id="b3551-243">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b3551-244">頻道2上傳送的信號等級。</span><span class="sxs-lookup"><span data-stu-id="b3551-244">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="b3551-245">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="b3551-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3551-246"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="b3551-246"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="b3551-247">int</span><span class="sxs-lookup"><span data-stu-id="b3551-247">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b3551-248">頻道1上傳送的雜訊等級。</span><span class="sxs-lookup"><span data-stu-id="b3551-248">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="b3551-249">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="b3551-249">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3551-250"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="b3551-250"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="b3551-251">int</span><span class="sxs-lookup"><span data-stu-id="b3551-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b3551-252">頻道2上傳送的雜訊等級。</span><span class="sxs-lookup"><span data-stu-id="b3551-252">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="b3551-253">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="b3551-253">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

