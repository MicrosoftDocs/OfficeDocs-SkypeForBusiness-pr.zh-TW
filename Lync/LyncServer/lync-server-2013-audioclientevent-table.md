---
title: Lync Server 2013：AudioClientEvent 表格
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
ms.openlocfilehash: 44d5146b334af83618ca2dd6261a18e72708f4f5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722623"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audioclientevent-table-in-lync-server-2013"></a><span data-ttu-id="110c2-102">Lync Server 2013 中的 AudioClientEvent 表格</span><span class="sxs-lookup"><span data-stu-id="110c2-102">AudioClientEvent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="110c2-103">_**主題上次修改日期：** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="110c2-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="110c2-104">每個記錄都包含音訊通話中某個端點的用戶端事件。</span><span class="sxs-lookup"><span data-stu-id="110c2-104">Each record contains a client event for one endpoint in an audio call.</span></span> <span data-ttu-id="110c2-105">通常，一個通話有兩筆記錄，一個用於呼叫者，另一個用於被叫方。</span><span class="sxs-lookup"><span data-stu-id="110c2-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="110c2-106"><strong>左欄</strong></span><span class="sxs-lookup"><span data-stu-id="110c2-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="110c2-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="110c2-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="110c2-108"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="110c2-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="110c2-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="110c2-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="110c2-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="110c2-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="110c2-111">datetime</span><span class="sxs-lookup"><span data-stu-id="110c2-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="110c2-112">首選</span><span class="sxs-lookup"><span data-stu-id="110c2-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="110c2-113">從<a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="110c2-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="110c2-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="110c2-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="110c2-115">int</span><span class="sxs-lookup"><span data-stu-id="110c2-115">int</span></span></p></td>
<td><p><span data-ttu-id="110c2-116">首選</span><span class="sxs-lookup"><span data-stu-id="110c2-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="110c2-117">從<a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="110c2-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="110c2-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="110c2-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="110c2-119">Tinyint</span><span class="sxs-lookup"><span data-stu-id="110c2-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="110c2-120">首選</span><span class="sxs-lookup"><span data-stu-id="110c2-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="110c2-121">從<a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="110c2-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="110c2-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="110c2-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="110c2-123">稍微</span><span class="sxs-lookup"><span data-stu-id="110c2-123">bit</span></span></p></td>
<td><p><span data-ttu-id="110c2-124">首選</span><span class="sxs-lookup"><span data-stu-id="110c2-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="110c2-125">0：被方程式的資料</span><span class="sxs-lookup"><span data-stu-id="110c2-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="110c2-126">1：來電者的資料</span><span class="sxs-lookup"><span data-stu-id="110c2-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="110c2-127"><strong>NetworkSendQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="110c2-127"><strong>NetworkSendQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="110c2-128">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="110c2-128">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="110c2-129">會話針對「錯誤」狀態觸發 NetworkSendQuality 事件的百分比。</span><span class="sxs-lookup"><span data-stu-id="110c2-129">Percentage of session the NetworkSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="110c2-130">在抖動或資料包遺失方面的網路品質很嚴重，而且會影響音訊傳送品質。</span><span class="sxs-lookup"><span data-stu-id="110c2-130">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="110c2-131"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="110c2-131"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="110c2-132">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="110c2-132">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="110c2-133">會話針對「錯誤」狀態觸發 ReceiveSendQuality 事件的百分比。</span><span class="sxs-lookup"><span data-stu-id="110c2-133">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="110c2-134">在抖動或資料包遺失方面的網路品質很嚴重，而且會影響接收的音訊品質。</span><span class="sxs-lookup"><span data-stu-id="110c2-134">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="110c2-135"><strong>NetworkDelayEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="110c2-135"><strong>NetworkDelayEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="110c2-136">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="110c2-136">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="110c2-137">會話針對「錯誤」狀態觸發延遲事件的百分比。</span><span class="sxs-lookup"><span data-stu-id="110c2-137">Percentage of session the Delay event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="110c2-138">網路延遲是嚴重的，並防止互動式通訊而影響體驗</span><span class="sxs-lookup"><span data-stu-id="110c2-138">Network latency is severe and impacting the experience by preventing interactive communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="110c2-139"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="110c2-139"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="110c2-140">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="110c2-140">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="110c2-141">會話針對「錯誤」狀態觸發 LowBandwidth 事件的百分比。</span><span class="sxs-lookup"><span data-stu-id="110c2-141">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="110c2-142">可用的頻寬不足以取得可接受的語音體驗。</span><span class="sxs-lookup"><span data-stu-id="110c2-142">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="110c2-143"><strong>CPUInsufficientEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="110c2-143"><strong>CPUInsufficientEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="110c2-144">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="110c2-144">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="110c2-145">會話百分比因「錯誤」狀態而觸發的 CPU 事件不足。</span><span class="sxs-lookup"><span data-stu-id="110c2-145">Percentage of session the insufficient CPU event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="110c2-146">使用目前的形式和應用程式時，沒有足夠的 CPU 週期來處理。</span><span class="sxs-lookup"><span data-stu-id="110c2-146">There are insufficient CPU cycles for processing with the current modalities and applications in use.</span></span> <span data-ttu-id="110c2-147">這會導致音訊通道出現扭曲。</span><span class="sxs-lookup"><span data-stu-id="110c2-147">This causes distortions with the audio channel.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="110c2-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="110c2-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="110c2-149">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="110c2-149">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="110c2-150">會話針對「錯誤」狀態觸發 DeviceHalfDuplexAEC 事件的百分比。</span><span class="sxs-lookup"><span data-stu-id="110c2-150">Percentage of session the DeviceHalfDuplexAEC event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="110c2-151">為了防止回顯，系統會輸入半雙工。</span><span class="sxs-lookup"><span data-stu-id="110c2-151">In order to prevent echo, the system has enter half duplex.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="110c2-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="110c2-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="110c2-153">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="110c2-153">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="110c2-154">會話針對「錯誤」狀態觸發 DeviceRenderNotFunctioning 事件的百分比。</span><span class="sxs-lookup"><span data-stu-id="110c2-154">Percentage of session the DeviceRenderNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="110c2-155">目前用於會話的轉譯裝置無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="110c2-155">The render device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="110c2-156">這可能會導致單向音訊問題。</span><span class="sxs-lookup"><span data-stu-id="110c2-156">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="110c2-157"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="110c2-157"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="110c2-158">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="110c2-158">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="110c2-159">會話針對「錯誤」狀態觸發 DeviceCaptureNotFunctioning 事件的百分比。</span><span class="sxs-lookup"><span data-stu-id="110c2-159">Percentage of session the DeviceCaptureNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="110c2-160">目前用於會話的捕獲裝置無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="110c2-160">The capture device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="110c2-161">這可能會導致單向音訊問題。</span><span class="sxs-lookup"><span data-stu-id="110c2-161">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="110c2-162"><strong>DeviceGlitchesEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="110c2-162"><strong>DeviceGlitchesEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="110c2-163">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="110c2-163">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="110c2-164">會話針對「錯誤」狀態觸發 DeviceGlitches 事件的百分比。</span><span class="sxs-lookup"><span data-stu-id="110c2-164">Percentage of session the DeviceGlitches event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="110c2-165">在轉譯造成扭曲的音訊時，會發生嚴重的問題。</span><span class="sxs-lookup"><span data-stu-id="110c2-165">There are severe glitches in the rendering of audio which is causing distortions.</span></span> <span data-ttu-id="110c2-166">這些故障可能是由驅動程式問題、延遲的程式呼叫（DPC）風暴（驅動程式）和高 CPU 使用率所造成。</span><span class="sxs-lookup"><span data-stu-id="110c2-166">These glitches can be caused by driver issues, deferred procedure calls (DPC) storm (drivers), and high CPU usage.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="110c2-167"><strong>DeviceLowSNREventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="110c2-167"><strong>DeviceLowSNREventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="110c2-168">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="110c2-168">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="110c2-169">會話針對「錯誤」狀態觸發 DeviceLowSNR 事件的百分比。</span><span class="sxs-lookup"><span data-stu-id="110c2-169">Percentage of session the DeviceLowSNR event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="110c2-170">捕捉品質很差、極大雜音，或使用者正在遠離麥克風太遠。</span><span class="sxs-lookup"><span data-stu-id="110c2-170">The capture quality is very poor, either very noisy or user is talking too far away from the microphone.</span></span> <span data-ttu-id="110c2-171">這會造成扭曲。</span><span class="sxs-lookup"><span data-stu-id="110c2-171">This will cause distortions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="110c2-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="110c2-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="110c2-173">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="110c2-173">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="110c2-174">會話針對「錯誤」狀態觸發 DeviceLowSpeechLevel 事件的百分比。</span><span class="sxs-lookup"><span data-stu-id="110c2-174">Percentage of session the DeviceLowSpeechLevel event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="110c2-175">使用者的語音等級太低，且系統無法進一步增加。</span><span class="sxs-lookup"><span data-stu-id="110c2-175">User‘s speech level is too low and the system cannot increase it any further.</span></span> <span data-ttu-id="110c2-176">這可能會造成扭曲或視為單向音訊。</span><span class="sxs-lookup"><span data-stu-id="110c2-176">This can either cause distortions or perceived as one-way audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="110c2-177"><strong>DeviceClippingEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="110c2-177"><strong>DeviceClippingEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="110c2-178">Decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="110c2-178">Decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="110c2-179">會話針對「錯誤」狀態觸發 DeviceClipping 事件的百分比。</span><span class="sxs-lookup"><span data-stu-id="110c2-179">Percentage of session the DeviceClipping event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="110c2-180">近距離語音會剪下麥克風，這是由於修剪而進行的最大終點聲音失真。</span><span class="sxs-lookup"><span data-stu-id="110c2-180">When near-end speech clips the microphone, far-end hears distortion due to clipping.</span></span> <span data-ttu-id="110c2-181">請務必避免接近結束的麥克風剪輯。</span><span class="sxs-lookup"><span data-stu-id="110c2-181">It is important to avoid near-end microphone clipping.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="110c2-182"><strong>DeviceEchoEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="110c2-182"><strong>DeviceEchoEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="110c2-183">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="110c2-183">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="110c2-184">會話針對「錯誤」狀態觸發 DeviceEchoEvent 事件的百分比。</span><span class="sxs-lookup"><span data-stu-id="110c2-184">Percentage of session the DeviceEchoEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="110c2-185">裝置或安裝程式導致回應超出系統的補償能力。</span><span class="sxs-lookup"><span data-stu-id="110c2-185">Device or setup is causing echo beyond the ability of the system to compensate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="110c2-186"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="110c2-186"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="110c2-187">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="110c2-187">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="110c2-188">會話針對「錯誤」狀態觸發 DeviceNearEndToEchoRatio 事件的百分比。</span><span class="sxs-lookup"><span data-stu-id="110c2-188">Percentage of session the DeviceNearEndToEchoRatio event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="110c2-189">使用者的語音太低，因為所捕獲的迴響會影響使用者體驗，因為它限制了中斷使用者的難易程度。</span><span class="sxs-lookup"><span data-stu-id="110c2-189">The user’s speech is too low compared to the echo being captured which impacts the users experience because it limits how easy it is to interrupt a user.</span></span> <span data-ttu-id="110c2-190">減少喇叭音量，請將麥克風移近交談者。</span><span class="sxs-lookup"><span data-stu-id="110c2-190">Reduce speaker volume, move the microphone closer to the talker.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="110c2-191"><strong>DeviceMultipleEndpointsEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="110c2-191"><strong>DeviceMultipleEndpointsEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="110c2-192">int</span><span class="sxs-lookup"><span data-stu-id="110c2-192">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="110c2-193">會話期間觸發 DeviceMultipleEndpoints 事件以取得「錯誤」狀態的次數。</span><span class="sxs-lookup"><span data-stu-id="110c2-193">Number of times during session the DeviceMultipleEndpoints event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="110c2-194">檢測到相同會話中有多個音訊端點，且系統已透過減少轉譯音量進行補償。</span><span class="sxs-lookup"><span data-stu-id="110c2-194">Multiple audio endpoints in the same session detected and the system has compensated by reducing render volume.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="110c2-195"><strong>DeviceHowlingEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="110c2-195"><strong>DeviceHowlingEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="110c2-196">int</span><span class="sxs-lookup"><span data-stu-id="110c2-196">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="110c2-197">會話期間觸發 DeviceHowlingEvent 事件以取得「錯誤」狀態的次數。</span><span class="sxs-lookup"><span data-stu-id="110c2-197">Number of times during session the DeviceHowlingEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="110c2-198">偵測到音訊意見反應（由多個端點共用音訊路徑所致）。</span><span class="sxs-lookup"><span data-stu-id="110c2-198">Audio feedback loop detected (caused by multiple endpoints sharing audio path).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="110c2-199"><strong>DeviceRenderZeroVolumeEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="110c2-199"><strong>DeviceRenderZeroVolumeEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="110c2-200">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="110c2-200">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="110c2-201">已觸發 DeviceRenderZeroVolume 事件以「錯誤」狀態的會話百分比。</span><span class="sxs-lookup"><span data-stu-id="110c2-201">Percentage of session the DeviceRenderZeroVolume event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="110c2-202">轉譯裝置已設定為零卷。</span><span class="sxs-lookup"><span data-stu-id="110c2-202">The render device was set to zero volume.</span></span></p>
<p><span data-ttu-id="110c2-203">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="110c2-203">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="110c2-204"><strong>DeviceRenderMuteEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="110c2-204"><strong>DeviceRenderMuteEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="110c2-205">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="110c2-205">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="110c2-206">已觸發 DeviceRenderMute 事件以「錯誤」狀態的會話百分比。</span><span class="sxs-lookup"><span data-stu-id="110c2-206">Percentage of session the DeviceRenderMute event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="110c2-207">渲染裝置已靜音。</span><span class="sxs-lookup"><span data-stu-id="110c2-207">The render device was muted.</span></span></p>
<p><span data-ttu-id="110c2-208">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="110c2-208">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

