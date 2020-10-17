---
title: Lync Server 2013： AudioSignal 表格
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
ms.openlocfilehash: 2605bfbd3e1d4023c013557aea2bcf75404fb23c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533510"
---
# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="bb7b8-102">Lync Server 2013 中的 AudioSignal 表格</span><span class="sxs-lookup"><span data-stu-id="bb7b8-102">AudioSignal table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb7b8-103">_**主題上次修改日期：** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="bb7b8-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="bb7b8-104">每筆記錄代表一個端點的音訊信號計量。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-104">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="bb7b8-105">通常，每個呼叫都有兩筆記錄，一個用於來電者，另一個則用於被叫用方。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-105">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb7b8-106"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="bb7b8-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="bb7b8-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="bb7b8-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="bb7b8-108"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="bb7b8-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="bb7b8-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="bb7b8-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb7b8-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="bb7b8-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bb7b8-111">datetime</span><span class="sxs-lookup"><span data-stu-id="bb7b8-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="bb7b8-112">主要</span><span class="sxs-lookup"><span data-stu-id="bb7b8-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="bb7b8-113">從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb7b8-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="bb7b8-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="bb7b8-115">int</span><span class="sxs-lookup"><span data-stu-id="bb7b8-115">int</span></span></p></td>
<td><p><span data-ttu-id="bb7b8-116">主要</span><span class="sxs-lookup"><span data-stu-id="bb7b8-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="bb7b8-117">從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb7b8-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="bb7b8-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="bb7b8-119">Tinyint</span><span class="sxs-lookup"><span data-stu-id="bb7b8-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="bb7b8-120">主要</span><span class="sxs-lookup"><span data-stu-id="bb7b8-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="bb7b8-121">從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb7b8-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="bb7b8-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="bb7b8-123">位</span><span class="sxs-lookup"><span data-stu-id="bb7b8-123">bit</span></span></p></td>
<td><p><span data-ttu-id="bb7b8-124">主要</span><span class="sxs-lookup"><span data-stu-id="bb7b8-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="bb7b8-125">0：被呼叫者的資料</span><span class="sxs-lookup"><span data-stu-id="bb7b8-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="bb7b8-126">1：來電者的資料</span><span class="sxs-lookup"><span data-stu-id="bb7b8-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb7b8-127"><strong>SendSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="bb7b8-127"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="bb7b8-128">int</span><span class="sxs-lookup"><span data-stu-id="bb7b8-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bb7b8-129">代表 [類比後增益控制音訊信號] 層級。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-129">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="bb7b8-130">此度量單位的單位是 dBmo。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-130">The unit for this metric is dBmo.</span></span> <span data-ttu-id="bb7b8-131">若要取得可接受的品質，至少要有 30 dBmo。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-131">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="bb7b8-132">A/V 的會議服務器或 IP 電話不會報告此度量。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-132">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb7b8-133"><strong>RecvSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="bb7b8-133"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="bb7b8-134">int</span><span class="sxs-lookup"><span data-stu-id="bb7b8-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bb7b8-135">請參閱 SendSignalLevel。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-135">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb7b8-136"><strong>SendNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="bb7b8-136"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="bb7b8-137">int</span><span class="sxs-lookup"><span data-stu-id="bb7b8-137">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bb7b8-138">代表 [類比後增益控制音訊雜訊層級]。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-138">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="bb7b8-139">此度量單位的單位是 dBmo。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-139">The unit for this metric is dBmo.</span></span> <span data-ttu-id="bb7b8-140">針對可接受的品質，它應小於 35 dBmo。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-140">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="bb7b8-141">A/V 的會議服務器或 IP 電話不會報告此度量。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-141">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb7b8-142"><strong>RecvNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="bb7b8-142"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="bb7b8-143">int</span><span class="sxs-lookup"><span data-stu-id="bb7b8-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bb7b8-144">請參閱 SendNoiseLevel。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-144">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb7b8-145"><strong>EchoReturn</strong></span><span class="sxs-lookup"><span data-stu-id="bb7b8-145"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="bb7b8-146">int</span><span class="sxs-lookup"><span data-stu-id="bb7b8-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bb7b8-147">迴響傳回遺失增強度量。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-147">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="bb7b8-148">此度量單位的單位為 dB。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-148">The unit for this metric is dB.</span></span> <span data-ttu-id="bb7b8-149">較低的值表示較少的回聲。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-149">Lower values represent less echo.</span></span> <span data-ttu-id="bb7b8-150">A/V 的會議服務器或 IP 電話不會報告此度量。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-150">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb7b8-151"><strong>AudioSpeakerGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="bb7b8-151"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="bb7b8-152">int</span><span class="sxs-lookup"><span data-stu-id="bb7b8-152">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bb7b8-153">喇叭轉譯每五分鐘的平均故障。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-153">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="bb7b8-154">為了獲得良好的品質，應小於每五分鐘一次。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-154">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="bb7b8-155">不會 A/V 會議伺服器、轉送伺服器或 IP 電話上報告。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-155">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb7b8-156"><strong>AudioMicGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="bb7b8-156"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="bb7b8-157">int</span><span class="sxs-lookup"><span data-stu-id="bb7b8-157">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bb7b8-158">每五分鐘捕獲麥克風的平均故障。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-158">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="bb7b8-159">若為良好的品質，這應小於每五分鐘一次。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-159">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="bb7b8-160">不會 A/V 會議伺服器、轉送伺服器或 IP 電話上報告。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-160">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb7b8-161"><strong>AudioTimestampDriftRateMic</strong></span><span class="sxs-lookup"><span data-stu-id="bb7b8-161"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="bb7b8-162">十進位 (9，2) </span><span class="sxs-lookup"><span data-stu-id="bb7b8-162">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bb7b8-163">麥克風裝置時鐘相對於 CPU 時鐘的相對頻率。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-163">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb7b8-164"><strong>AudioTimestampDriftRateSpk</strong></span><span class="sxs-lookup"><span data-stu-id="bb7b8-164"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="bb7b8-165">十進位 (9，2) </span><span class="sxs-lookup"><span data-stu-id="bb7b8-165">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bb7b8-166">揚聲器裝置時鐘相對於 CPU 時鐘的相對頻率。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-166">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb7b8-167"><strong>AudioTimestampErrorMicMs</strong></span><span class="sxs-lookup"><span data-stu-id="bb7b8-167"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="bb7b8-168">十進位 (9，2) </span><span class="sxs-lookup"><span data-stu-id="bb7b8-168">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bb7b8-169">揚聲器裝置時鐘相對於 CPU 時鐘的相對頻率。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-169">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="bb7b8-170">通話的最後20秒內的平均麥克風捕獲資料流程時間戳記錯誤（毫秒）。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-170">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb7b8-171"><strong>AudioTimestampErrorSpkMs</strong></span><span class="sxs-lookup"><span data-stu-id="bb7b8-171"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="bb7b8-172">十進位 (9，2) </span><span class="sxs-lookup"><span data-stu-id="bb7b8-172">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bb7b8-173">通話的最後20秒內，平均喇叭轉譯資料流程時間戳記錯誤（毫秒）。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-173">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb7b8-174"><strong>VsEntryCauses</strong></span><span class="sxs-lookup"><span data-stu-id="bb7b8-174"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="bb7b8-175">Smallint</span><span class="sxs-lookup"><span data-stu-id="bb7b8-175">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bb7b8-176">語音開關是一種具有低中斷能力的半雙工模式。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-176">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="bb7b8-177">語音開關專案的原因：</span><span class="sxs-lookup"><span data-stu-id="bb7b8-177">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="bb7b8-178">ENTER_VS_BADTS 0x01</span><span class="sxs-lookup"><span data-stu-id="bb7b8-178">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="bb7b8-179">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="bb7b8-179">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="bb7b8-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span><span class="sxs-lookup"><span data-stu-id="bb7b8-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="bb7b8-181">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="bb7b8-181">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="bb7b8-182">原因可能是個別原因的組合。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-182">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="bb7b8-183">ENTER_VS_FORCEORCONVERGENCE 只能透過 regkey 為測試目的來啟用。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-183">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="bb7b8-184">在 Microsoft Lync Server 2013 中，此欄的資料類型已變更。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-184">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb7b8-185"><strong>EchoEventCauses</strong></span><span class="sxs-lookup"><span data-stu-id="bb7b8-185"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="bb7b8-186">Tinyint</span><span class="sxs-lookup"><span data-stu-id="bb7b8-186">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bb7b8-187">Echo 事件的原因：</span><span class="sxs-lookup"><span data-stu-id="bb7b8-187">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="bb7b8-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="bb7b8-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="bb7b8-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="bb7b8-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="bb7b8-190">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="bb7b8-190">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="bb7b8-191">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="bb7b8-191">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="bb7b8-192">ECHO_EVENT_MIC_CLIPPING 0x10</span><span class="sxs-lookup"><span data-stu-id="bb7b8-192">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="bb7b8-193">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="bb7b8-193">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="bb7b8-194">原因可能是個別原因的組合。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-194">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb7b8-195"><strong>EchoPercentMicIn</strong></span><span class="sxs-lookup"><span data-stu-id="bb7b8-195"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="bb7b8-196">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="bb7b8-196">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bb7b8-197">在麥克風捕獲資料流程中偵測到迴響的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-197">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="bb7b8-198">通常，耳機或電話機的值很低，對喇叭或獨立揚聲器而言，其值也會比較高。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-198">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="bb7b8-199">針對支援板載聲音回聲取消功能的裝置，高值表示回聲洩漏。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-199">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="bb7b8-200">若為其他裝置，則不應該使用此度量來評估裝置品質。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-200">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb7b8-201"><strong>EchoPercentSend</strong></span><span class="sxs-lookup"><span data-stu-id="bb7b8-201"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="bb7b8-202">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="bb7b8-202">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bb7b8-203">在傳送的資料流程中偵測到迴響時的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-203">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="bb7b8-204">傳送資料流程中的高回音百分比會傳回回聲洩漏。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-204">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb7b8-205"><strong>RxAGCSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="bb7b8-205"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="bb7b8-206">int</span><span class="sxs-lookup"><span data-stu-id="bb7b8-206">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bb7b8-207">從閘道從轉送伺服器接收信號層級;這只適用于轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-207">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="bb7b8-208">此度量單位為 dBoV。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-208">The unit of this metric is dBoV.</span></span> <span data-ttu-id="bb7b8-209">為了獲得良好的品質，可接受的範圍應為 [-30 到-18] dBoV。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-209">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb7b8-210"><strong>RxAGCNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="bb7b8-210"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="bb7b8-211">int</span><span class="sxs-lookup"><span data-stu-id="bb7b8-211">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bb7b8-212">從閘道從轉送伺服器接收信號層級。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-212">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="bb7b8-213">這只適用于轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-213">This applies only to the Mediation Server.</span></span> <span data-ttu-id="bb7b8-214">此度量單位為 dBoV。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-214">The unit of this metric is dBoV.</span></span> <span data-ttu-id="bb7b8-215">為了獲得良好的品質，可接受的範圍應小於-50 dBoV。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-215">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb7b8-216"><strong>RxAvgAGCGain</strong></span><span class="sxs-lookup"><span data-stu-id="bb7b8-216"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="bb7b8-217">int</span><span class="sxs-lookup"><span data-stu-id="bb7b8-217">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bb7b8-218"> (AGC) 轉送伺服器端的自動增益控制。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-218">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb7b8-219"><strong>InitialSignalLevelRMS</strong></span><span class="sxs-lookup"><span data-stu-id="bb7b8-219"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="bb7b8-220">float</span><span class="sxs-lookup"><span data-stu-id="bb7b8-220">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bb7b8-221">從來電的前30秒內之傳入信號的根平均平方 (RMS) 。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-221">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb7b8-222"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="bb7b8-222"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="bb7b8-223">int</span><span class="sxs-lookup"><span data-stu-id="bb7b8-223">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bb7b8-224">通道1上接收的信號等級。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-224">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="bb7b8-225">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb7b8-226"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="bb7b8-226"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="bb7b8-227">int</span><span class="sxs-lookup"><span data-stu-id="bb7b8-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bb7b8-228">通道2上接收的信號等級。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-228">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="bb7b8-229">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb7b8-230"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="bb7b8-230"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="bb7b8-231">int</span><span class="sxs-lookup"><span data-stu-id="bb7b8-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bb7b8-232">通道1上接收的雜訊層級。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-232">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="bb7b8-233">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb7b8-234"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="bb7b8-234"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="bb7b8-235">int</span><span class="sxs-lookup"><span data-stu-id="bb7b8-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bb7b8-236">通道2上接收的雜訊水準。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-236">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="bb7b8-237">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb7b8-238"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="bb7b8-238"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="bb7b8-239">int</span><span class="sxs-lookup"><span data-stu-id="bb7b8-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bb7b8-240">通道1上傳送的信號層級。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-240">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="bb7b8-241">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb7b8-242"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="bb7b8-242"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="bb7b8-243">int</span><span class="sxs-lookup"><span data-stu-id="bb7b8-243">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bb7b8-244">通道2上傳送的信號層級。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-244">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="bb7b8-245">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb7b8-246"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="bb7b8-246"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="bb7b8-247">int</span><span class="sxs-lookup"><span data-stu-id="bb7b8-247">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bb7b8-248">通道1上傳送的雜訊層級。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-248">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="bb7b8-249">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-249">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb7b8-250"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="bb7b8-250"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="bb7b8-251">int</span><span class="sxs-lookup"><span data-stu-id="bb7b8-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bb7b8-252">通道2上傳送的雜訊層級。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-252">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="bb7b8-253">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="bb7b8-253">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

