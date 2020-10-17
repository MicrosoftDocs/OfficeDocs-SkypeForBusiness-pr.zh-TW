---
title: Lync Server 2013： AudioSignal 表格
description: Lync Server 2013： AudioSignal 表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioSignal table
ms:assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398064(v=OCS.15)
ms:contentKeyID: 48183217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82f3b3119eaccfe56c4706cff07469bc3434461f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568759"
---
# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="c60c6-103">Lync Server 2013 中的 AudioSignal 表格</span><span class="sxs-lookup"><span data-stu-id="c60c6-103">AudioSignal table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c60c6-104">_**主題上次修改日期：** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="c60c6-104">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="c60c6-105">每筆記錄代表一個端點的音訊信號計量。</span><span class="sxs-lookup"><span data-stu-id="c60c6-105">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="c60c6-106">通常，每個呼叫都有兩筆記錄，一個用於來電者，另一個則用於被叫用方。</span><span class="sxs-lookup"><span data-stu-id="c60c6-106">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c60c6-107"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="c60c6-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="c60c6-108"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="c60c6-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="c60c6-109"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="c60c6-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="c60c6-110"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="c60c6-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c60c6-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="c60c6-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c60c6-112">datetime</span><span class="sxs-lookup"><span data-stu-id="c60c6-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="c60c6-113">主要</span><span class="sxs-lookup"><span data-stu-id="c60c6-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="c60c6-114">從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="c60c6-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c60c6-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c60c6-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c60c6-116">int</span><span class="sxs-lookup"><span data-stu-id="c60c6-116">int</span></span></p></td>
<td><p><span data-ttu-id="c60c6-117">主要</span><span class="sxs-lookup"><span data-stu-id="c60c6-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="c60c6-118">從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="c60c6-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c60c6-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="c60c6-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="c60c6-120">Tinyint</span><span class="sxs-lookup"><span data-stu-id="c60c6-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c60c6-121">主要</span><span class="sxs-lookup"><span data-stu-id="c60c6-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="c60c6-122">從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="c60c6-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c60c6-123"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="c60c6-123"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="c60c6-124">位</span><span class="sxs-lookup"><span data-stu-id="c60c6-124">bit</span></span></p></td>
<td><p><span data-ttu-id="c60c6-125">主要</span><span class="sxs-lookup"><span data-stu-id="c60c6-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="c60c6-126">0：被呼叫者的資料</span><span class="sxs-lookup"><span data-stu-id="c60c6-126">0: Callee’s data</span></span></p>
<p><span data-ttu-id="c60c6-127">1：來電者的資料</span><span class="sxs-lookup"><span data-stu-id="c60c6-127">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c60c6-128"><strong>SendSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="c60c6-128"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="c60c6-129">int</span><span class="sxs-lookup"><span data-stu-id="c60c6-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c60c6-130">代表 [類比後增益控制音訊信號] 層級。</span><span class="sxs-lookup"><span data-stu-id="c60c6-130">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="c60c6-131">此度量單位的單位是 dBmo。</span><span class="sxs-lookup"><span data-stu-id="c60c6-131">The unit for this metric is dBmo.</span></span> <span data-ttu-id="c60c6-132">若要取得可接受的品質，至少要有 30 dBmo。</span><span class="sxs-lookup"><span data-stu-id="c60c6-132">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="c60c6-133">A/V 的會議服務器或 IP 電話不會報告此度量。</span><span class="sxs-lookup"><span data-stu-id="c60c6-133">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c60c6-134"><strong>RecvSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="c60c6-134"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="c60c6-135">int</span><span class="sxs-lookup"><span data-stu-id="c60c6-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c60c6-136">請參閱 SendSignalLevel。</span><span class="sxs-lookup"><span data-stu-id="c60c6-136">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c60c6-137"><strong>SendNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="c60c6-137"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="c60c6-138">int</span><span class="sxs-lookup"><span data-stu-id="c60c6-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c60c6-139">代表 [類比後增益控制音訊雜訊層級]。</span><span class="sxs-lookup"><span data-stu-id="c60c6-139">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="c60c6-140">此度量單位的單位是 dBmo。</span><span class="sxs-lookup"><span data-stu-id="c60c6-140">The unit for this metric is dBmo.</span></span> <span data-ttu-id="c60c6-141">針對可接受的品質，它應小於 35 dBmo。</span><span class="sxs-lookup"><span data-stu-id="c60c6-141">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="c60c6-142">A/V 的會議服務器或 IP 電話不會報告此度量。</span><span class="sxs-lookup"><span data-stu-id="c60c6-142">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c60c6-143"><strong>RecvNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="c60c6-143"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="c60c6-144">int</span><span class="sxs-lookup"><span data-stu-id="c60c6-144">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c60c6-145">請參閱 SendNoiseLevel。</span><span class="sxs-lookup"><span data-stu-id="c60c6-145">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c60c6-146"><strong>EchoReturn</strong></span><span class="sxs-lookup"><span data-stu-id="c60c6-146"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="c60c6-147">int</span><span class="sxs-lookup"><span data-stu-id="c60c6-147">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c60c6-148">迴響傳回遺失增強度量。</span><span class="sxs-lookup"><span data-stu-id="c60c6-148">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="c60c6-149">此度量單位的單位為 dB。</span><span class="sxs-lookup"><span data-stu-id="c60c6-149">The unit for this metric is dB.</span></span> <span data-ttu-id="c60c6-150">較低的值表示較少的回聲。</span><span class="sxs-lookup"><span data-stu-id="c60c6-150">Lower values represent less echo.</span></span> <span data-ttu-id="c60c6-151">A/V 的會議服務器或 IP 電話不會報告此度量。</span><span class="sxs-lookup"><span data-stu-id="c60c6-151">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c60c6-152"><strong>AudioSpeakerGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="c60c6-152"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="c60c6-153">int</span><span class="sxs-lookup"><span data-stu-id="c60c6-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c60c6-154">喇叭轉譯每五分鐘的平均故障。</span><span class="sxs-lookup"><span data-stu-id="c60c6-154">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="c60c6-155">為了獲得良好的品質，應小於每五分鐘一次。</span><span class="sxs-lookup"><span data-stu-id="c60c6-155">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="c60c6-156">不會 A/V 會議伺服器、轉送伺服器或 IP 電話上報告。</span><span class="sxs-lookup"><span data-stu-id="c60c6-156">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c60c6-157"><strong>AudioMicGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="c60c6-157"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="c60c6-158">int</span><span class="sxs-lookup"><span data-stu-id="c60c6-158">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c60c6-159">每五分鐘捕獲麥克風的平均故障。</span><span class="sxs-lookup"><span data-stu-id="c60c6-159">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="c60c6-160">若為良好的品質，這應小於每五分鐘一次。</span><span class="sxs-lookup"><span data-stu-id="c60c6-160">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="c60c6-161">不會 A/V 會議伺服器、轉送伺服器或 IP 電話上報告。</span><span class="sxs-lookup"><span data-stu-id="c60c6-161">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c60c6-162"><strong>AudioTimestampDriftRateMic</strong></span><span class="sxs-lookup"><span data-stu-id="c60c6-162"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="c60c6-163">十進位 (9，2) </span><span class="sxs-lookup"><span data-stu-id="c60c6-163">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c60c6-164">麥克風裝置時鐘相對於 CPU 時鐘的相對頻率。</span><span class="sxs-lookup"><span data-stu-id="c60c6-164">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c60c6-165"><strong>AudioTimestampDriftRateSpk</strong></span><span class="sxs-lookup"><span data-stu-id="c60c6-165"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="c60c6-166">十進位 (9，2) </span><span class="sxs-lookup"><span data-stu-id="c60c6-166">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c60c6-167">揚聲器裝置時鐘相對於 CPU 時鐘的相對頻率。</span><span class="sxs-lookup"><span data-stu-id="c60c6-167">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c60c6-168"><strong>AudioTimestampErrorMicMs</strong></span><span class="sxs-lookup"><span data-stu-id="c60c6-168"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="c60c6-169">十進位 (9，2) </span><span class="sxs-lookup"><span data-stu-id="c60c6-169">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c60c6-170">揚聲器裝置時鐘相對於 CPU 時鐘的相對頻率。</span><span class="sxs-lookup"><span data-stu-id="c60c6-170">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="c60c6-171">通話的最後20秒內的平均麥克風捕獲資料流程時間戳記錯誤（毫秒）。</span><span class="sxs-lookup"><span data-stu-id="c60c6-171">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c60c6-172"><strong>AudioTimestampErrorSpkMs</strong></span><span class="sxs-lookup"><span data-stu-id="c60c6-172"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="c60c6-173">十進位 (9，2) </span><span class="sxs-lookup"><span data-stu-id="c60c6-173">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c60c6-174">通話的最後20秒內，平均喇叭轉譯資料流程時間戳記錯誤（毫秒）。</span><span class="sxs-lookup"><span data-stu-id="c60c6-174">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c60c6-175"><strong>VsEntryCauses</strong></span><span class="sxs-lookup"><span data-stu-id="c60c6-175"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="c60c6-176">Smallint</span><span class="sxs-lookup"><span data-stu-id="c60c6-176">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c60c6-177">語音開關是一種具有低中斷能力的半雙工模式。</span><span class="sxs-lookup"><span data-stu-id="c60c6-177">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="c60c6-178">語音開關專案的原因：</span><span class="sxs-lookup"><span data-stu-id="c60c6-178">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="c60c6-179">ENTER_VS_BADTS 0x01</span><span class="sxs-lookup"><span data-stu-id="c60c6-179">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="c60c6-180">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="c60c6-180">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="c60c6-181">ENTER_VS_FORCEORCONVERGENCE 0x04</span><span class="sxs-lookup"><span data-stu-id="c60c6-181">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="c60c6-182">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="c60c6-182">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="c60c6-183">原因可能是個別原因的組合。</span><span class="sxs-lookup"><span data-stu-id="c60c6-183">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="c60c6-184">ENTER_VS_FORCEORCONVERGENCE 只能透過 regkey 為測試目的來啟用。</span><span class="sxs-lookup"><span data-stu-id="c60c6-184">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="c60c6-185">在 Microsoft Lync Server 2013 中，此欄的資料類型已變更。</span><span class="sxs-lookup"><span data-stu-id="c60c6-185">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c60c6-186"><strong>EchoEventCauses</strong></span><span class="sxs-lookup"><span data-stu-id="c60c6-186"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="c60c6-187">Tinyint</span><span class="sxs-lookup"><span data-stu-id="c60c6-187">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c60c6-188">Echo 事件的原因：</span><span class="sxs-lookup"><span data-stu-id="c60c6-188">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="c60c6-189">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="c60c6-189">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="c60c6-190">ECHO_EVENT_POSTAEC_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="c60c6-190">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="c60c6-191">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="c60c6-191">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="c60c6-192">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="c60c6-192">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="c60c6-193">ECHO_EVENT_MIC_CLIPPING 0x10</span><span class="sxs-lookup"><span data-stu-id="c60c6-193">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="c60c6-194">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="c60c6-194">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="c60c6-195">原因可能是個別原因的組合。</span><span class="sxs-lookup"><span data-stu-id="c60c6-195">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c60c6-196"><strong>EchoPercentMicIn</strong></span><span class="sxs-lookup"><span data-stu-id="c60c6-196"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="c60c6-197">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="c60c6-197">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c60c6-198">在麥克風捕獲資料流程中偵測到迴響的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="c60c6-198">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="c60c6-199">通常，耳機或電話機的值很低，對喇叭或獨立揚聲器而言，其值也會比較高。</span><span class="sxs-lookup"><span data-stu-id="c60c6-199">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="c60c6-200">針對支援板載聲音回聲取消功能的裝置，高值表示回聲洩漏。</span><span class="sxs-lookup"><span data-stu-id="c60c6-200">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="c60c6-201">若為其他裝置，則不應該使用此度量來評估裝置品質。</span><span class="sxs-lookup"><span data-stu-id="c60c6-201">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c60c6-202"><strong>EchoPercentSend</strong></span><span class="sxs-lookup"><span data-stu-id="c60c6-202"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="c60c6-203">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="c60c6-203">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c60c6-204">在傳送的資料流程中偵測到迴響時的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="c60c6-204">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="c60c6-205">傳送資料流程中的高回音百分比會傳回回聲洩漏。</span><span class="sxs-lookup"><span data-stu-id="c60c6-205">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c60c6-206"><strong>RxAGCSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="c60c6-206"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="c60c6-207">int</span><span class="sxs-lookup"><span data-stu-id="c60c6-207">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c60c6-208">從閘道從轉送伺服器接收信號層級;這只適用于轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="c60c6-208">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="c60c6-209">此度量單位為 dBoV。</span><span class="sxs-lookup"><span data-stu-id="c60c6-209">The unit of this metric is dBoV.</span></span> <span data-ttu-id="c60c6-210">為了獲得良好的品質，可接受的範圍應為 [-30 到-18] dBoV。</span><span class="sxs-lookup"><span data-stu-id="c60c6-210">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c60c6-211"><strong>RxAGCNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="c60c6-211"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="c60c6-212">int</span><span class="sxs-lookup"><span data-stu-id="c60c6-212">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c60c6-213">從閘道從轉送伺服器接收信號層級。</span><span class="sxs-lookup"><span data-stu-id="c60c6-213">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="c60c6-214">這只適用于轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="c60c6-214">This applies only to the Mediation Server.</span></span> <span data-ttu-id="c60c6-215">此度量單位為 dBoV。</span><span class="sxs-lookup"><span data-stu-id="c60c6-215">The unit of this metric is dBoV.</span></span> <span data-ttu-id="c60c6-216">為了獲得良好的品質，可接受的範圍應小於-50 dBoV。</span><span class="sxs-lookup"><span data-stu-id="c60c6-216">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c60c6-217"><strong>RxAvgAGCGain</strong></span><span class="sxs-lookup"><span data-stu-id="c60c6-217"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="c60c6-218">int</span><span class="sxs-lookup"><span data-stu-id="c60c6-218">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c60c6-219"> (AGC) 轉送伺服器端的自動增益控制。</span><span class="sxs-lookup"><span data-stu-id="c60c6-219">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c60c6-220"><strong>InitialSignalLevelRMS</strong></span><span class="sxs-lookup"><span data-stu-id="c60c6-220"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="c60c6-221">float</span><span class="sxs-lookup"><span data-stu-id="c60c6-221">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c60c6-222">從來電的前30秒內之傳入信號的根平均平方 (RMS) 。</span><span class="sxs-lookup"><span data-stu-id="c60c6-222">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c60c6-223"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="c60c6-223"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="c60c6-224">int</span><span class="sxs-lookup"><span data-stu-id="c60c6-224">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c60c6-225">通道1上接收的信號等級。</span><span class="sxs-lookup"><span data-stu-id="c60c6-225">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="c60c6-226">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="c60c6-226">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c60c6-227"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="c60c6-227"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="c60c6-228">int</span><span class="sxs-lookup"><span data-stu-id="c60c6-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c60c6-229">通道2上接收的信號等級。</span><span class="sxs-lookup"><span data-stu-id="c60c6-229">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="c60c6-230">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="c60c6-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c60c6-231"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="c60c6-231"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="c60c6-232">int</span><span class="sxs-lookup"><span data-stu-id="c60c6-232">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c60c6-233">通道1上接收的雜訊層級。</span><span class="sxs-lookup"><span data-stu-id="c60c6-233">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="c60c6-234">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="c60c6-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c60c6-235"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="c60c6-235"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="c60c6-236">int</span><span class="sxs-lookup"><span data-stu-id="c60c6-236">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c60c6-237">通道2上接收的雜訊水準。</span><span class="sxs-lookup"><span data-stu-id="c60c6-237">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="c60c6-238">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="c60c6-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c60c6-239"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="c60c6-239"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="c60c6-240">int</span><span class="sxs-lookup"><span data-stu-id="c60c6-240">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c60c6-241">通道1上傳送的信號層級。</span><span class="sxs-lookup"><span data-stu-id="c60c6-241">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="c60c6-242">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="c60c6-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c60c6-243"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="c60c6-243"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="c60c6-244">int</span><span class="sxs-lookup"><span data-stu-id="c60c6-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c60c6-245">通道2上傳送的信號層級。</span><span class="sxs-lookup"><span data-stu-id="c60c6-245">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="c60c6-246">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="c60c6-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c60c6-247"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="c60c6-247"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="c60c6-248">int</span><span class="sxs-lookup"><span data-stu-id="c60c6-248">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c60c6-249">通道1上傳送的雜訊層級。</span><span class="sxs-lookup"><span data-stu-id="c60c6-249">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="c60c6-250">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="c60c6-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c60c6-251"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="c60c6-251"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="c60c6-252">int</span><span class="sxs-lookup"><span data-stu-id="c60c6-252">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c60c6-253">通道2上傳送的雜訊層級。</span><span class="sxs-lookup"><span data-stu-id="c60c6-253">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="c60c6-254">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="c60c6-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

