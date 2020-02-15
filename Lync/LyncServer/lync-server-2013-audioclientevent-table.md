---
title: 'Lync Server 2013: AudioClientEvent 表格'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioClientEvent table
ms:assetid: fef73d8f-7261-4e5b-9769-82435b007979
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413086(v=OCS.15)
ms:contentKeyID: 48185967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53f43bdae2fd134e851c93be958aa671657489e1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044595"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audioclientevent-table-in-lync-server-2013"></a><span data-ttu-id="05a9d-102">Lync Server 2013 中的 AudioClientEvent 表格</span><span class="sxs-lookup"><span data-stu-id="05a9d-102">AudioClientEvent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05a9d-103">_**主題上次修改日期：** 2012年-10-17_</span><span class="sxs-lookup"><span data-stu-id="05a9d-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="05a9d-104">每一筆記錄含有一個端點音訊通話的用戶端事件。</span><span class="sxs-lookup"><span data-stu-id="05a9d-104">Each record contains a client event for one endpoint in an audio call.</span></span> <span data-ttu-id="05a9d-105">通常，一次呼叫會有兩個記錄、 一個來電者，一個用於受話者。</span><span class="sxs-lookup"><span data-stu-id="05a9d-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="05a9d-106"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="05a9d-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="05a9d-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="05a9d-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="05a9d-108"><strong>主索引鍵 /</strong></span><span class="sxs-lookup"><span data-stu-id="05a9d-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="05a9d-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="05a9d-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05a9d-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="05a9d-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="05a9d-111">datetime</span><span class="sxs-lookup"><span data-stu-id="05a9d-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="05a9d-112">主要</span><span class="sxs-lookup"><span data-stu-id="05a9d-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="05a9d-113">參考來源： <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的來源： MediaLine table</a>。</span><span class="sxs-lookup"><span data-stu-id="05a9d-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a9d-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="05a9d-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="05a9d-115">int</span><span class="sxs-lookup"><span data-stu-id="05a9d-115">int</span></span></p></td>
<td><p><span data-ttu-id="05a9d-116">主要</span><span class="sxs-lookup"><span data-stu-id="05a9d-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="05a9d-117">參考來源： <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的來源： MediaLine table</a>。</span><span class="sxs-lookup"><span data-stu-id="05a9d-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a9d-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="05a9d-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="05a9d-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="05a9d-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="05a9d-120">主要</span><span class="sxs-lookup"><span data-stu-id="05a9d-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="05a9d-121">參考來源： <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的來源： MediaLine table</a>。</span><span class="sxs-lookup"><span data-stu-id="05a9d-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a9d-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="05a9d-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="05a9d-123">位元</span><span class="sxs-lookup"><span data-stu-id="05a9d-123">bit</span></span></p></td>
<td><p><span data-ttu-id="05a9d-124">主要</span><span class="sxs-lookup"><span data-stu-id="05a9d-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="05a9d-125">0： 受話者的資料</span><span class="sxs-lookup"><span data-stu-id="05a9d-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="05a9d-126">1： 發話者的資料</span><span class="sxs-lookup"><span data-stu-id="05a9d-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a9d-127"><strong>NetworkSendQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="05a9d-127"><strong>NetworkSendQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="05a9d-128">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="05a9d-128">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="05a9d-129">工作階段百分比 NetworkSendQuality 事件引發 「 故障 」 狀態。</span><span class="sxs-lookup"><span data-stu-id="05a9d-129">Percentage of session the NetworkSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="05a9d-130">在網路品質來說抖動或封包遺失相當嚴重且會影響所接收的音訊品質。</span><span class="sxs-lookup"><span data-stu-id="05a9d-130">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a9d-131"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="05a9d-131"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="05a9d-132">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="05a9d-132">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="05a9d-133">工作階段百分比 receivesendquality 「 故障 」 狀態。</span><span class="sxs-lookup"><span data-stu-id="05a9d-133">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="05a9d-134">在網路品質來說抖動或封包遺失相當嚴重且會影響所接收的音訊品質。</span><span class="sxs-lookup"><span data-stu-id="05a9d-134">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a9d-135"><strong>NetworkDelayEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="05a9d-135"><strong>NetworkDelayEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="05a9d-136">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="05a9d-136">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="05a9d-137">工作階段百分比延遲事件引發 「 故障 」 狀態。</span><span class="sxs-lookup"><span data-stu-id="05a9d-137">Percentage of session the Delay event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="05a9d-138">網路延遲相當嚴重，藉由防止互動式通訊以至體驗</span><span class="sxs-lookup"><span data-stu-id="05a9d-138">Network latency is severe and impacting the experience by preventing interactive communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a9d-139"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="05a9d-139"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="05a9d-140">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="05a9d-140">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="05a9d-141">工作階段百分比 LowBandwidth 事件引發 「 故障 」 狀態。</span><span class="sxs-lookup"><span data-stu-id="05a9d-141">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="05a9d-142">可用的頻寬不足的可接受的語音體驗。</span><span class="sxs-lookup"><span data-stu-id="05a9d-142">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a9d-143"><strong>CPUInsufficientEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="05a9d-143"><strong>CPUInsufficientEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="05a9d-144">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="05a9d-144">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="05a9d-145">工作階段沒有足夠的 CPU 事件引發 「 故障 」 狀態的百分比。</span><span class="sxs-lookup"><span data-stu-id="05a9d-145">Percentage of session the insufficient CPU event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="05a9d-146">有沒有足夠的 CPU 循環處理與目前的形式和使用中的應用程式。</span><span class="sxs-lookup"><span data-stu-id="05a9d-146">There are insufficient CPU cycles for processing with the current modalities and applications in use.</span></span> <span data-ttu-id="05a9d-147">這會導致失真音訊的通道。</span><span class="sxs-lookup"><span data-stu-id="05a9d-147">This causes distortions with the audio channel.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a9d-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="05a9d-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="05a9d-149">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="05a9d-149">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="05a9d-150">工作階段百分比 DeviceHalfDuplexAEC 事件引發 「 故障 」 狀態。</span><span class="sxs-lookup"><span data-stu-id="05a9d-150">Percentage of session the DeviceHalfDuplexAEC event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="05a9d-151">若要避免回音，系統已輸入半雙工。</span><span class="sxs-lookup"><span data-stu-id="05a9d-151">In order to prevent echo, the system has enter half duplex.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a9d-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="05a9d-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="05a9d-153">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="05a9d-153">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="05a9d-154">工作階段百分比 DeviceRenderNotFunctioning 事件引發 「 故障 」 狀態。</span><span class="sxs-lookup"><span data-stu-id="05a9d-154">Percentage of session the DeviceRenderNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="05a9d-155">目前工作階段使用轉換裝置無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="05a9d-155">The render device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="05a9d-156">這可能會導致單向音訊問題。</span><span class="sxs-lookup"><span data-stu-id="05a9d-156">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a9d-157"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="05a9d-157"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="05a9d-158">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="05a9d-158">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="05a9d-159">工作階段百分比 DeviceCaptureNotFunctioning 事件引發 「 故障 」 狀態。</span><span class="sxs-lookup"><span data-stu-id="05a9d-159">Percentage of session the DeviceCaptureNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="05a9d-160">目前使用的工作階段的擷取裝置無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="05a9d-160">The capture device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="05a9d-161">這可能會導致單向音訊問題。</span><span class="sxs-lookup"><span data-stu-id="05a9d-161">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a9d-162"><strong>DeviceGlitchesEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="05a9d-162"><strong>DeviceGlitchesEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="05a9d-163">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="05a9d-163">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="05a9d-164">工作階段百分比 DeviceGlitches 事件引發 「 故障 」 狀態。</span><span class="sxs-lookup"><span data-stu-id="05a9d-164">Percentage of session the DeviceGlitches event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="05a9d-165">這會導致扭曲音訊的轉譯中有嚴重的故障。</span><span class="sxs-lookup"><span data-stu-id="05a9d-165">There are severe glitches in the rendering of audio which is causing distortions.</span></span> <span data-ttu-id="05a9d-166">這些故障可能被因驅動程式問題、 延後的程序呼叫 (DPC) 風暴 （驅動程式），以及高 CPU 使用率。</span><span class="sxs-lookup"><span data-stu-id="05a9d-166">These glitches can be caused by driver issues, deferred procedure calls (DPC) storm (drivers), and high CPU usage.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a9d-167"><strong>DeviceLowSNREventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="05a9d-167"><strong>DeviceLowSNREventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="05a9d-168">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="05a9d-168">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="05a9d-169">工作階段百分比 DeviceLowSNR 事件引發 「 故障 」 狀態。</span><span class="sxs-lookup"><span data-stu-id="05a9d-169">Percentage of session the DeviceLowSNR event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="05a9d-170">可以是非常不佳，擷取品質非常吵雜或使用者從麥克風太遠交談。</span><span class="sxs-lookup"><span data-stu-id="05a9d-170">The capture quality is very poor, either very noisy or user is talking too far away from the microphone.</span></span> <span data-ttu-id="05a9d-171">這會導致扭曲。</span><span class="sxs-lookup"><span data-stu-id="05a9d-171">This will cause distortions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a9d-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="05a9d-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="05a9d-173">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="05a9d-173">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="05a9d-174">工作階段百分比 DeviceLowSpeechLevel 事件引發 「 故障 」 狀態。</span><span class="sxs-lookup"><span data-stu-id="05a9d-174">Percentage of session the DeviceLowSpeechLevel event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="05a9d-175">使用者的語音層級很太低，且系統無法增加其任何進一步。</span><span class="sxs-lookup"><span data-stu-id="05a9d-175">User‘s speech level is too low and the system cannot increase it any further.</span></span> <span data-ttu-id="05a9d-176">這可能也會造成扭曲或認知以單向音訊。</span><span class="sxs-lookup"><span data-stu-id="05a9d-176">This can either cause distortions or perceived as one-way audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a9d-177"><strong>DeviceClippingEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="05a9d-177"><strong>DeviceClippingEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="05a9d-178">Decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="05a9d-178">Decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="05a9d-179">工作階段百分比 DeviceClipping 事件引發 「 故障 」 狀態。</span><span class="sxs-lookup"><span data-stu-id="05a9d-179">Percentage of session the DeviceClipping event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="05a9d-180">當附近端語音剪裁麥克風時，距離端會聽到由於裁剪圖像扭曲。</span><span class="sxs-lookup"><span data-stu-id="05a9d-180">When near-end speech clips the microphone, far-end hears distortion due to clipping.</span></span> <span data-ttu-id="05a9d-181">請務必避免結束靠近麥克風雜音。</span><span class="sxs-lookup"><span data-stu-id="05a9d-181">It is important to avoid near-end microphone clipping.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a9d-182"><strong>DeviceEchoEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="05a9d-182"><strong>DeviceEchoEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="05a9d-183">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="05a9d-183">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="05a9d-184">工作階段百分比 DeviceEchoEvent 事件引發 「 故障 」 狀態。</span><span class="sxs-lookup"><span data-stu-id="05a9d-184">Percentage of session the DeviceEchoEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="05a9d-185">裝置或安裝程式會造成回音超出來彌補系統的能力。</span><span class="sxs-lookup"><span data-stu-id="05a9d-185">Device or setup is causing echo beyond the ability of the system to compensate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a9d-186"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="05a9d-186"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="05a9d-187">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="05a9d-187">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="05a9d-188">工作階段百分比 DeviceNearEndToEchoRatio 事件引發 「 故障 」 狀態。</span><span class="sxs-lookup"><span data-stu-id="05a9d-188">Percentage of session the DeviceNearEndToEchoRatio event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="05a9d-189">使用者的語音是太低相較於回音正在擷取影響使用者經驗，因為它限制了中斷使用者何其輕鬆。</span><span class="sxs-lookup"><span data-stu-id="05a9d-189">The user’s speech is too low compared to the echo being captured which impacts the users experience because it limits how easy it is to interrupt a user.</span></span> <span data-ttu-id="05a9d-190">減少喇叭音量，將靠近麥克風移至 「 說話者 」。</span><span class="sxs-lookup"><span data-stu-id="05a9d-190">Reduce speaker volume, move the microphone closer to the talker.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a9d-191"><strong>DeviceMultipleEndpointsEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="05a9d-191"><strong>DeviceMultipleEndpointsEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="05a9d-192">int</span><span class="sxs-lookup"><span data-stu-id="05a9d-192">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a9d-193">工作階段 DeviceMultipleEndpoints 事件引發 「 故障 」 狀態的次數。</span><span class="sxs-lookup"><span data-stu-id="05a9d-193">Number of times during session the DeviceMultipleEndpoints event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="05a9d-194">偵測到相同的工作階段中的多個音訊端點和系統具有補償藉由減少轉譯磁碟區。</span><span class="sxs-lookup"><span data-stu-id="05a9d-194">Multiple audio endpoints in the same session detected and the system has compensated by reducing render volume.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a9d-195"><strong>DeviceHowlingEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="05a9d-195"><strong>DeviceHowlingEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="05a9d-196">int</span><span class="sxs-lookup"><span data-stu-id="05a9d-196">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="05a9d-197">工作階段 DeviceHowlingEvent 事件引發 「 故障 」 狀態的次數。</span><span class="sxs-lookup"><span data-stu-id="05a9d-197">Number of times during session the DeviceHowlingEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="05a9d-198">偵測到的音訊回饋迴圈 （因共用音訊路徑的多個端點）。</span><span class="sxs-lookup"><span data-stu-id="05a9d-198">Audio feedback loop detected (caused by multiple endpoints sharing audio path).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05a9d-199"><strong>DeviceRenderZeroVolumeEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="05a9d-199"><strong>DeviceRenderZeroVolumeEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="05a9d-200">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="05a9d-200">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a9d-201">百分比的工作階段 DeviceRenderZeroVolume 事件會出現在 「 錯誤 」 狀態。</span><span class="sxs-lookup"><span data-stu-id="05a9d-201">Percentage of session the DeviceRenderZeroVolume event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="05a9d-202">轉換裝置未設定為零個磁碟區。</span><span class="sxs-lookup"><span data-stu-id="05a9d-202">The render device was set to zero volume.</span></span></p>
<p><span data-ttu-id="05a9d-203">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="05a9d-203">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05a9d-204"><strong>DeviceRenderMuteEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="05a9d-204"><strong>DeviceRenderMuteEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="05a9d-205">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="05a9d-205">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05a9d-206">百分比的工作階段 DeviceRenderMute 事件會出現在 「 錯誤 」 狀態。</span><span class="sxs-lookup"><span data-stu-id="05a9d-206">Percentage of session the DeviceRenderMute event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="05a9d-207">轉換裝置已設為靜音。</span><span class="sxs-lookup"><span data-stu-id="05a9d-207">The render device was muted.</span></span></p>
<p><span data-ttu-id="05a9d-208">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="05a9d-208">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

