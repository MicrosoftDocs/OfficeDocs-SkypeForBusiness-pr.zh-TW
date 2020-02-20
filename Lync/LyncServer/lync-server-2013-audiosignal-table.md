---
title: 'Lync Server 2013: AudioSignal 表格'
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
ms.openlocfilehash: 2d09842cb8b905798855cef7e015e4d9b32e72dd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149132"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="373f5-102">Lync Server 2013 中的 AudioSignal 表格</span><span class="sxs-lookup"><span data-stu-id="373f5-102">AudioSignal table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="373f5-103">_**上次修改主題：** 2013年-11-12_</span><span class="sxs-lookup"><span data-stu-id="373f5-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="373f5-104">每筆記錄代表一個端點的音訊訊號計量。</span><span class="sxs-lookup"><span data-stu-id="373f5-104">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="373f5-105">通常，每次呼叫具有兩個記錄、 一個是來電者，而另一個做為受話者。</span><span class="sxs-lookup"><span data-stu-id="373f5-105">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="373f5-106"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="373f5-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="373f5-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="373f5-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="373f5-108"><strong>主索引鍵 /</strong></span><span class="sxs-lookup"><span data-stu-id="373f5-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="373f5-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="373f5-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="373f5-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="373f5-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="373f5-111">datetime</span><span class="sxs-lookup"><span data-stu-id="373f5-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="373f5-112">主要</span><span class="sxs-lookup"><span data-stu-id="373f5-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="373f5-113">參考來源： <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的來源： MediaLine table</a>。</span><span class="sxs-lookup"><span data-stu-id="373f5-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="373f5-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="373f5-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="373f5-115">int</span><span class="sxs-lookup"><span data-stu-id="373f5-115">int</span></span></p></td>
<td><p><span data-ttu-id="373f5-116">主要</span><span class="sxs-lookup"><span data-stu-id="373f5-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="373f5-117">參考來源： <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的來源： MediaLine table</a>。</span><span class="sxs-lookup"><span data-stu-id="373f5-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="373f5-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="373f5-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="373f5-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="373f5-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="373f5-120">主要</span><span class="sxs-lookup"><span data-stu-id="373f5-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="373f5-121">參考來源： <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的來源： MediaLine table</a>。</span><span class="sxs-lookup"><span data-stu-id="373f5-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="373f5-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="373f5-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="373f5-123">位元</span><span class="sxs-lookup"><span data-stu-id="373f5-123">bit</span></span></p></td>
<td><p><span data-ttu-id="373f5-124">主要</span><span class="sxs-lookup"><span data-stu-id="373f5-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="373f5-125">0： 受話者的資料</span><span class="sxs-lookup"><span data-stu-id="373f5-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="373f5-126">1： 發話者的資料</span><span class="sxs-lookup"><span data-stu-id="373f5-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="373f5-127"><strong>SendSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="373f5-127"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="373f5-128">int</span><span class="sxs-lookup"><span data-stu-id="373f5-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="373f5-129">代表後類比獲得控制音訊訊號層級。</span><span class="sxs-lookup"><span data-stu-id="373f5-129">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="373f5-130">此評量單位為 dBmo。</span><span class="sxs-lookup"><span data-stu-id="373f5-130">The unit for this metric is dBmo.</span></span> <span data-ttu-id="373f5-131">可接受的品質，它應該至少 30 dBmo。</span><span class="sxs-lookup"><span data-stu-id="373f5-131">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="373f5-132">此評量不報告的 A / V 會議伺服器或 IP 電話。</span><span class="sxs-lookup"><span data-stu-id="373f5-132">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="373f5-133"><strong>RecvSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="373f5-133"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="373f5-134">int</span><span class="sxs-lookup"><span data-stu-id="373f5-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="373f5-135">請參閱 SendSignalLevel。</span><span class="sxs-lookup"><span data-stu-id="373f5-135">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="373f5-136"><strong>SendNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="373f5-136"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="373f5-137">int</span><span class="sxs-lookup"><span data-stu-id="373f5-137">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="373f5-138">代表後類比獲得控制音訊有雜音層級。</span><span class="sxs-lookup"><span data-stu-id="373f5-138">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="373f5-139">此評量單位為 dBmo。</span><span class="sxs-lookup"><span data-stu-id="373f5-139">The unit for this metric is dBmo.</span></span> <span data-ttu-id="373f5-140">可接受的品質，它應該小於 35 dBmo。</span><span class="sxs-lookup"><span data-stu-id="373f5-140">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="373f5-141">此評量不報告的 A / V 會議伺服器或 IP 電話。</span><span class="sxs-lookup"><span data-stu-id="373f5-141">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="373f5-142"><strong>RecvNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="373f5-142"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="373f5-143">int</span><span class="sxs-lookup"><span data-stu-id="373f5-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="373f5-144">請參閱 SendNoiseLevel。</span><span class="sxs-lookup"><span data-stu-id="373f5-144">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="373f5-145"><strong>EchoReturn</strong></span><span class="sxs-lookup"><span data-stu-id="373f5-145"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="373f5-146">int</span><span class="sxs-lookup"><span data-stu-id="373f5-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="373f5-147">回音傳回遺失增強評量。</span><span class="sxs-lookup"><span data-stu-id="373f5-147">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="373f5-148">此評量單位為 dB。</span><span class="sxs-lookup"><span data-stu-id="373f5-148">The unit for this metric is dB.</span></span> <span data-ttu-id="373f5-149">較低的值代表較少回應。</span><span class="sxs-lookup"><span data-stu-id="373f5-149">Lower values represent less echo.</span></span> <span data-ttu-id="373f5-150">此評量不報告的 A / V 會議伺服器或 IP 電話。</span><span class="sxs-lookup"><span data-stu-id="373f5-150">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="373f5-151"><strong>AudioSpeakerGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="373f5-151"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="373f5-152">int</span><span class="sxs-lookup"><span data-stu-id="373f5-152">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="373f5-153">平均每五分鐘喇叭呈現的故障。</span><span class="sxs-lookup"><span data-stu-id="373f5-153">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="373f5-154">為品質良好，這應該是小於每五分鐘。</span><span class="sxs-lookup"><span data-stu-id="373f5-154">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="373f5-155">不報告的 A / V 會議伺服器、 中繼伺服器或 IP 電話。</span><span class="sxs-lookup"><span data-stu-id="373f5-155">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="373f5-156"><strong>AudioMicGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="373f5-156"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="373f5-157">int</span><span class="sxs-lookup"><span data-stu-id="373f5-157">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="373f5-158">平均每五分鐘麥克風擷取故障。</span><span class="sxs-lookup"><span data-stu-id="373f5-158">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="373f5-159">良好的品質這應該是小於 1 每五分鐘。</span><span class="sxs-lookup"><span data-stu-id="373f5-159">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="373f5-160">不報告的 A / V 會議伺服器、 中繼伺服器或 IP 電話。</span><span class="sxs-lookup"><span data-stu-id="373f5-160">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="373f5-161"><strong>AudioTimestampDriftRateMic</strong></span><span class="sxs-lookup"><span data-stu-id="373f5-161"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="373f5-162">decimal(9,2)</span><span class="sxs-lookup"><span data-stu-id="373f5-162">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="373f5-163">麥克風裝置時脈的漂移率，相對於 CPU 時脈。</span><span class="sxs-lookup"><span data-stu-id="373f5-163">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="373f5-164"><strong>AudioTimestampDriftRateSpk</strong></span><span class="sxs-lookup"><span data-stu-id="373f5-164"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="373f5-165">decimal(9,2)</span><span class="sxs-lookup"><span data-stu-id="373f5-165">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="373f5-166">喇叭裝置時脈的漂移率，相對於 CPU 時脈。</span><span class="sxs-lookup"><span data-stu-id="373f5-166">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="373f5-167"><strong>AudioTimestampErrorMicMs</strong></span><span class="sxs-lookup"><span data-stu-id="373f5-167"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="373f5-168">decimal(9,2)</span><span class="sxs-lookup"><span data-stu-id="373f5-168">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="373f5-169">喇叭裝置時脈的漂移率，相對於 CPU 時脈。</span><span class="sxs-lookup"><span data-stu-id="373f5-169">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="373f5-170">通話的最後 20 秒中，平均麥克風擷取資料流時間戳記錯誤，單位為毫秒。</span><span class="sxs-lookup"><span data-stu-id="373f5-170">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="373f5-171"><strong>AudioTimestampErrorSpkMs</strong></span><span class="sxs-lookup"><span data-stu-id="373f5-171"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="373f5-172">decimal(9,2)</span><span class="sxs-lookup"><span data-stu-id="373f5-172">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="373f5-173">平均喇叭呈現資料流時間戳記錯誤，以毫秒為單位，通話的最後 20 秒中。</span><span class="sxs-lookup"><span data-stu-id="373f5-173">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="373f5-174"><strong>VsEntryCauses</strong></span><span class="sxs-lookup"><span data-stu-id="373f5-174"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="373f5-175">smallint</span><span class="sxs-lookup"><span data-stu-id="373f5-175">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="373f5-176">語音交換是降低的中斷能力與半雙工模式。</span><span class="sxs-lookup"><span data-stu-id="373f5-176">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="373f5-177">語音的原因切換項目：</span><span class="sxs-lookup"><span data-stu-id="373f5-177">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="373f5-178">ENTER_VS_BADTS 0X01</span><span class="sxs-lookup"><span data-stu-id="373f5-178">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="373f5-179">ENTER_VS_ECHO 0X02</span><span class="sxs-lookup"><span data-stu-id="373f5-179">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="373f5-180">ENTER_VS_FORCEORCONVERGENCE 0X04</span><span class="sxs-lookup"><span data-stu-id="373f5-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="373f5-181">ENTER_VS_DNLP 0X08</span><span class="sxs-lookup"><span data-stu-id="373f5-181">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="373f5-182">原因可以是這些個別原因的組合。</span><span class="sxs-lookup"><span data-stu-id="373f5-182">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="373f5-183">針對測試目的 regkey 可以只啟用 ENTER_VS_FORCEORCONVERGENCE。</span><span class="sxs-lookup"><span data-stu-id="373f5-183">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="373f5-184">Microsoft Lync Server 2013 中已變更此資料行的資料類型。</span><span class="sxs-lookup"><span data-stu-id="373f5-184">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="373f5-185"><strong>EchoEventCauses</strong></span><span class="sxs-lookup"><span data-stu-id="373f5-185"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="373f5-186">tinyint</span><span class="sxs-lookup"><span data-stu-id="373f5-186">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="373f5-187">回音事件的原因：</span><span class="sxs-lookup"><span data-stu-id="373f5-187">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="373f5-188">ECHO_EVENT_BAD_TIMESTAMP 0X01</span><span class="sxs-lookup"><span data-stu-id="373f5-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="373f5-189">ECHO_EVENT_POSTAEC_ECHO 0X02</span><span class="sxs-lookup"><span data-stu-id="373f5-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="373f5-190">ECHO_EVENT_ANLP 0X04</span><span class="sxs-lookup"><span data-stu-id="373f5-190">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="373f5-191">ECHO_EVENT_DNLP 0X08</span><span class="sxs-lookup"><span data-stu-id="373f5-191">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="373f5-192">ECHO_EVENT_MIC_CLIPPING 0X10</span><span class="sxs-lookup"><span data-stu-id="373f5-192">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="373f5-193">ECHO_EVENT_BAD_STATE 0X20</span><span class="sxs-lookup"><span data-stu-id="373f5-193">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="373f5-194">原因可以是這些個別原因的組合。</span><span class="sxs-lookup"><span data-stu-id="373f5-194">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="373f5-195"><strong>EchoPercentMicIn</strong></span><span class="sxs-lookup"><span data-stu-id="373f5-195"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="373f5-196">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="373f5-196">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="373f5-197">回音麥克風擷取資料流中偵測到時的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="373f5-197">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="373f5-198">一般而言，值為低，耳機或 handsets，及喇叭電話或獨立喇叭較高。</span><span class="sxs-lookup"><span data-stu-id="373f5-198">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="373f5-199">針對支援委任柔和式迴音效果取消功能的裝置，高的值可指出回音外洩。</span><span class="sxs-lookup"><span data-stu-id="373f5-199">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="373f5-200">針對其他裝置，此評量不應該用來評估裝置品質。</span><span class="sxs-lookup"><span data-stu-id="373f5-200">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="373f5-201"><strong>EchoPercentSend</strong></span><span class="sxs-lookup"><span data-stu-id="373f5-201"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="373f5-202">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="373f5-202">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="373f5-203">當傳送的資料流中偵測到回音的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="373f5-203">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="373f5-204">在高的回音百分比傳送資料流回音遺漏的指示。</span><span class="sxs-lookup"><span data-stu-id="373f5-204">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="373f5-205"><strong>RxAGCSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="373f5-205"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="373f5-206">int</span><span class="sxs-lookup"><span data-stu-id="373f5-206">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="373f5-207">在中繼伺服器上的訊號等級接收來自閘道;僅適用於中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="373f5-207">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="373f5-208">此評量的單位是 dBoV。</span><span class="sxs-lookup"><span data-stu-id="373f5-208">The unit of this metric is dBoV.</span></span> <span data-ttu-id="373f5-209">品質良好，可接受的範圍必須是 [-30 至-18] dBoV。</span><span class="sxs-lookup"><span data-stu-id="373f5-209">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="373f5-210"><strong>RxAGCNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="373f5-210"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="373f5-211">int</span><span class="sxs-lookup"><span data-stu-id="373f5-211">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="373f5-212">來自閘道的中繼伺服器已接收的訊號等級。</span><span class="sxs-lookup"><span data-stu-id="373f5-212">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="373f5-213">僅適用於中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="373f5-213">This applies only to the Mediation Server.</span></span> <span data-ttu-id="373f5-214">此評量的單位是 dBoV。</span><span class="sxs-lookup"><span data-stu-id="373f5-214">The unit of this metric is dBoV.</span></span> <span data-ttu-id="373f5-215">基於品質良好，可接受的範圍應該小於-50 dBoV。</span><span class="sxs-lookup"><span data-stu-id="373f5-215">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="373f5-216"><strong>RxAvgAGCGain</strong></span><span class="sxs-lookup"><span data-stu-id="373f5-216"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="373f5-217">int</span><span class="sxs-lookup"><span data-stu-id="373f5-217">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="373f5-218">自動增益控制 (AGC) 上之中繼伺服器端。</span><span class="sxs-lookup"><span data-stu-id="373f5-218">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="373f5-219"><strong>InitialSignalLevelRMS</strong></span><span class="sxs-lookup"><span data-stu-id="373f5-219"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="373f5-220">float</span><span class="sxs-lookup"><span data-stu-id="373f5-220">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="373f5-221">平方根 (RMS) 接收的傳入訊號的最多通話前 30 秒。</span><span class="sxs-lookup"><span data-stu-id="373f5-221">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="373f5-222"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="373f5-222"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="373f5-223">int</span><span class="sxs-lookup"><span data-stu-id="373f5-223">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="373f5-224">頻道 1 上接收的訊號等級。</span><span class="sxs-lookup"><span data-stu-id="373f5-224">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="373f5-225">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="373f5-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="373f5-226"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="373f5-226"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="373f5-227">int</span><span class="sxs-lookup"><span data-stu-id="373f5-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="373f5-228">頻道 2 上接收的訊號等級。</span><span class="sxs-lookup"><span data-stu-id="373f5-228">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="373f5-229">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="373f5-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="373f5-230"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="373f5-230"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="373f5-231">int</span><span class="sxs-lookup"><span data-stu-id="373f5-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="373f5-232">頻道 1 上接收雜訊層級。</span><span class="sxs-lookup"><span data-stu-id="373f5-232">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="373f5-233">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="373f5-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="373f5-234"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="373f5-234"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="373f5-235">int</span><span class="sxs-lookup"><span data-stu-id="373f5-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="373f5-236">頻道 2 上接收雜訊層級。</span><span class="sxs-lookup"><span data-stu-id="373f5-236">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="373f5-237">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="373f5-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="373f5-238"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="373f5-238"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="373f5-239">int</span><span class="sxs-lookup"><span data-stu-id="373f5-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="373f5-240">頻道 1 上傳送的訊號等級。</span><span class="sxs-lookup"><span data-stu-id="373f5-240">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="373f5-241">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="373f5-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="373f5-242"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="373f5-242"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="373f5-243">int</span><span class="sxs-lookup"><span data-stu-id="373f5-243">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="373f5-244">頻道 2 上傳送的訊號等級。</span><span class="sxs-lookup"><span data-stu-id="373f5-244">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="373f5-245">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="373f5-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="373f5-246"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="373f5-246"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="373f5-247">int</span><span class="sxs-lookup"><span data-stu-id="373f5-247">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="373f5-248">頻道 1 上傳送雜訊層級。</span><span class="sxs-lookup"><span data-stu-id="373f5-248">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="373f5-249">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="373f5-249">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="373f5-250"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="373f5-250"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="373f5-251">int</span><span class="sxs-lookup"><span data-stu-id="373f5-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="373f5-252">頻道 2 上傳送雜訊層級。</span><span class="sxs-lookup"><span data-stu-id="373f5-252">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="373f5-253">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="373f5-253">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

