---
title: Lync Server 2013： AudioClientEvent 表格
description: Lync Server 2013： AudioClientEvent 表格。
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
ms.openlocfilehash: 2200cd9567bdd10ac4ad8f5c269062c2f5614dcb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568779"
---
# <a name="audioclientevent-table-in-lync-server-2013"></a><span data-ttu-id="a85bf-103">Lync Server 2013 中的 AudioClientEvent 表格</span><span class="sxs-lookup"><span data-stu-id="a85bf-103">AudioClientEvent table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a85bf-104">_**主題上次修改日期：** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="a85bf-104">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="a85bf-105">每筆記錄都包含音訊撥號中一個端點的用戶端事件。</span><span class="sxs-lookup"><span data-stu-id="a85bf-105">Each record contains a client event for one endpoint in an audio call.</span></span> <span data-ttu-id="a85bf-106">通常，一個呼叫有兩筆記錄，一個用於來電者，另一個用於呼叫者。</span><span class="sxs-lookup"><span data-stu-id="a85bf-106">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a85bf-107"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="a85bf-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="a85bf-108"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="a85bf-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="a85bf-109"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="a85bf-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="a85bf-110"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="a85bf-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a85bf-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="a85bf-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a85bf-112">datetime</span><span class="sxs-lookup"><span data-stu-id="a85bf-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="a85bf-113">主要</span><span class="sxs-lookup"><span data-stu-id="a85bf-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="a85bf-114">從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="a85bf-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a85bf-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a85bf-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a85bf-116">int</span><span class="sxs-lookup"><span data-stu-id="a85bf-116">int</span></span></p></td>
<td><p><span data-ttu-id="a85bf-117">主要</span><span class="sxs-lookup"><span data-stu-id="a85bf-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="a85bf-118">從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="a85bf-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a85bf-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="a85bf-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="a85bf-120">Tinyint</span><span class="sxs-lookup"><span data-stu-id="a85bf-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a85bf-121">主要</span><span class="sxs-lookup"><span data-stu-id="a85bf-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="a85bf-122">從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="a85bf-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a85bf-123"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="a85bf-123"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="a85bf-124">位</span><span class="sxs-lookup"><span data-stu-id="a85bf-124">bit</span></span></p></td>
<td><p><span data-ttu-id="a85bf-125">主要</span><span class="sxs-lookup"><span data-stu-id="a85bf-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="a85bf-126">0：被呼叫者的資料</span><span class="sxs-lookup"><span data-stu-id="a85bf-126">0: Callee’s data</span></span></p>
<p><span data-ttu-id="a85bf-127">1：來電者的資料</span><span class="sxs-lookup"><span data-stu-id="a85bf-127">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a85bf-128"><strong>NetworkSendQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a85bf-128"><strong>NetworkSendQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a85bf-129">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="a85bf-129">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a85bf-130">會話百分比已針對 ' 壞」狀態引發 NetworkSendQuality 事件。</span><span class="sxs-lookup"><span data-stu-id="a85bf-130">Percentage of session the NetworkSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="a85bf-131">抖動或封包遺失方面的網路品質很嚴重，且會影響所傳送之音訊的品質。</span><span class="sxs-lookup"><span data-stu-id="a85bf-131">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a85bf-132"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a85bf-132"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a85bf-133">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="a85bf-133">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a85bf-134">會話百分比已針對 ' 壞」狀態引發 ReceiveSendQuality 事件。</span><span class="sxs-lookup"><span data-stu-id="a85bf-134">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="a85bf-135">抖動或封包遺失方面的網路品質很嚴重，且會影響所接收的音訊品質。</span><span class="sxs-lookup"><span data-stu-id="a85bf-135">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a85bf-136"><strong>NetworkDelayEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a85bf-136"><strong>NetworkDelayEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a85bf-137">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="a85bf-137">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a85bf-138">會話百分比 Delay 事件因「錯誤」的狀態而引發。</span><span class="sxs-lookup"><span data-stu-id="a85bf-138">Percentage of session the Delay event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="a85bf-139">網路延遲是嚴重的，而且會影響互動式通訊的體驗</span><span class="sxs-lookup"><span data-stu-id="a85bf-139">Network latency is severe and impacting the experience by preventing interactive communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a85bf-140"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a85bf-140"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a85bf-141">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="a85bf-141">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a85bf-142">會話百分比 LowBandwidth 事件引發「不良」狀態。</span><span class="sxs-lookup"><span data-stu-id="a85bf-142">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="a85bf-143">可用的頻寬不足以取得可接受的語音體驗。</span><span class="sxs-lookup"><span data-stu-id="a85bf-143">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a85bf-144"><strong>CPUInsufficientEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a85bf-144"><strong>CPUInsufficientEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a85bf-145">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="a85bf-145">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a85bf-146">會話百分比因「壞」狀態而引發的 CPU 事件不足。</span><span class="sxs-lookup"><span data-stu-id="a85bf-146">Percentage of session the insufficient CPU event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="a85bf-147">使用目前的形式和應用程式來處理的 CPU 週期不足。</span><span class="sxs-lookup"><span data-stu-id="a85bf-147">There are insufficient CPU cycles for processing with the current modalities and applications in use.</span></span> <span data-ttu-id="a85bf-148">這會導致音訊通道失真。</span><span class="sxs-lookup"><span data-stu-id="a85bf-148">This causes distortions with the audio channel.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a85bf-149"><strong>DeviceHalfDuplexAECEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a85bf-149"><strong>DeviceHalfDuplexAECEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a85bf-150">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="a85bf-150">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a85bf-151">會話百分比 DeviceHalfDuplexAEC 事件引發「不良」狀態。</span><span class="sxs-lookup"><span data-stu-id="a85bf-151">Percentage of session the DeviceHalfDuplexAEC event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="a85bf-152">為了避免回聲，系統有輸入半雙工。</span><span class="sxs-lookup"><span data-stu-id="a85bf-152">In order to prevent echo, the system has enter half duplex.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a85bf-153"><strong>DeviceRenderNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a85bf-153"><strong>DeviceRenderNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a85bf-154">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="a85bf-154">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a85bf-155">會話百分比 DeviceRenderNotFunctioning 事件引發「不良」狀態。</span><span class="sxs-lookup"><span data-stu-id="a85bf-155">Percentage of session the DeviceRenderNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="a85bf-156">目前用於會話的呈現裝置無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="a85bf-156">The render device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="a85bf-157">這可能會造成單向音訊問題。</span><span class="sxs-lookup"><span data-stu-id="a85bf-157">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a85bf-158"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a85bf-158"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a85bf-159">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="a85bf-159">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a85bf-160">會話百分比 DeviceCaptureNotFunctioning 事件引發「不良」狀態。</span><span class="sxs-lookup"><span data-stu-id="a85bf-160">Percentage of session the DeviceCaptureNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="a85bf-161">目前用於會話的捕獲裝置無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="a85bf-161">The capture device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="a85bf-162">這可能會造成單向音訊問題。</span><span class="sxs-lookup"><span data-stu-id="a85bf-162">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a85bf-163"><strong>DeviceGlitchesEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a85bf-163"><strong>DeviceGlitchesEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a85bf-164">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="a85bf-164">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a85bf-165">會話百分比 DeviceGlitches 事件引發「不良」狀態。</span><span class="sxs-lookup"><span data-stu-id="a85bf-165">Percentage of session the DeviceGlitches event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="a85bf-166">呈現導致失真的音訊時，發生嚴重的難題。</span><span class="sxs-lookup"><span data-stu-id="a85bf-166">There are severe glitches in the rendering of audio which is causing distortions.</span></span> <span data-ttu-id="a85bf-167">這些難題可能是由於驅動程式問題、延遲的程式呼叫 (DPC) 風暴 (驅動程式) 和高 CPU 使用率而引起。</span><span class="sxs-lookup"><span data-stu-id="a85bf-167">These glitches can be caused by driver issues, deferred procedure calls (DPC) storm (drivers), and high CPU usage.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a85bf-168"><strong>DeviceLowSNREventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a85bf-168"><strong>DeviceLowSNREventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a85bf-169">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="a85bf-169">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a85bf-170">會話百分比 DeviceLowSNR 事件引發「不良」狀態。</span><span class="sxs-lookup"><span data-stu-id="a85bf-170">Percentage of session the DeviceLowSNR event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="a85bf-171">[！注意] 捕獲品質很低，可能是極大噪音，或是使用者從麥克風的距離太遠。</span><span class="sxs-lookup"><span data-stu-id="a85bf-171">The capture quality is very poor, either very noisy or user is talking too far away from the microphone.</span></span> <span data-ttu-id="a85bf-172">這會導致失真。</span><span class="sxs-lookup"><span data-stu-id="a85bf-172">This will cause distortions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a85bf-173"><strong>DeviceLowSpeechLevelEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a85bf-173"><strong>DeviceLowSpeechLevelEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a85bf-174">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="a85bf-174">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a85bf-175">會話百分比 DeviceLowSpeechLevel 事件引發「不良」狀態。</span><span class="sxs-lookup"><span data-stu-id="a85bf-175">Percentage of session the DeviceLowSpeechLevel event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="a85bf-176">使用者的語音層級太低，系統無法進一步增加。</span><span class="sxs-lookup"><span data-stu-id="a85bf-176">User‘s speech level is too low and the system cannot increase it any further.</span></span> <span data-ttu-id="a85bf-177">這可能會造成扭曲或感覺為單向音訊。</span><span class="sxs-lookup"><span data-stu-id="a85bf-177">This can either cause distortions or perceived as one-way audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a85bf-178"><strong>DeviceClippingEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a85bf-178"><strong>DeviceClippingEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a85bf-179">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="a85bf-179">Decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a85bf-180">會話百分比已針對 ' 壞」狀態引發 DeviceClipping 事件。</span><span class="sxs-lookup"><span data-stu-id="a85bf-180">Percentage of session the DeviceClipping event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="a85bf-181">當近序語音剪下麥克風時，會因為剪裁而結束的時間太長。</span><span class="sxs-lookup"><span data-stu-id="a85bf-181">When near-end speech clips the microphone, far-end hears distortion due to clipping.</span></span> <span data-ttu-id="a85bf-182">請務必避免接近端的麥克風剪裁。</span><span class="sxs-lookup"><span data-stu-id="a85bf-182">It is important to avoid near-end microphone clipping.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a85bf-183"><strong>DeviceEchoEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a85bf-183"><strong>DeviceEchoEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a85bf-184">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="a85bf-184">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a85bf-185">會話百分比 DeviceEchoEvent 事件引發「不良」狀態。</span><span class="sxs-lookup"><span data-stu-id="a85bf-185">Percentage of session the DeviceEchoEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="a85bf-186">裝置或安裝程式導致回應超出系統補償的能力。</span><span class="sxs-lookup"><span data-stu-id="a85bf-186">Device or setup is causing echo beyond the ability of the system to compensate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a85bf-187"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a85bf-187"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a85bf-188">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="a85bf-188">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a85bf-189">會話百分比 DeviceNearEndToEchoRatio 事件引發「不良」狀態。</span><span class="sxs-lookup"><span data-stu-id="a85bf-189">Percentage of session the DeviceNearEndToEchoRatio event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="a85bf-190">使用者的語音變得太低，因為其所捕獲的回音會影響使用者的體驗，因為它會限制使用者的中斷。</span><span class="sxs-lookup"><span data-stu-id="a85bf-190">The user’s speech is too low compared to the echo being captured which impacts the users experience because it limits how easy it is to interrupt a user.</span></span> <span data-ttu-id="a85bf-191">減少喇叭的音量，請將麥克風移近 talker。</span><span class="sxs-lookup"><span data-stu-id="a85bf-191">Reduce speaker volume, move the microphone closer to the talker.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a85bf-192"><strong>DeviceMultipleEndpointsEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="a85bf-192"><strong>DeviceMultipleEndpointsEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="a85bf-193">int</span><span class="sxs-lookup"><span data-stu-id="a85bf-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a85bf-194">會話期間為「不良」狀態引發 DeviceMultipleEndpoints 事件的次數。</span><span class="sxs-lookup"><span data-stu-id="a85bf-194">Number of times during session the DeviceMultipleEndpoints event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="a85bf-195">偵測到相同會話中的多個音訊端點，而且系統已透過減少轉譯體積量進行補償。</span><span class="sxs-lookup"><span data-stu-id="a85bf-195">Multiple audio endpoints in the same session detected and the system has compensated by reducing render volume.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a85bf-196"><strong>DeviceHowlingEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="a85bf-196"><strong>DeviceHowlingEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="a85bf-197">int</span><span class="sxs-lookup"><span data-stu-id="a85bf-197">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a85bf-198">會話期間為「不良」狀態引發 DeviceHowlingEvent 事件的次數。</span><span class="sxs-lookup"><span data-stu-id="a85bf-198">Number of times during session the DeviceHowlingEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="a85bf-199">在多個端點共用音訊路徑) 所造成的 (，會偵測到音訊意見反應。</span><span class="sxs-lookup"><span data-stu-id="a85bf-199">Audio feedback loop detected (caused by multiple endpoints sharing audio path).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a85bf-200"><strong>DeviceRenderZeroVolumeEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a85bf-200"><strong>DeviceRenderZeroVolumeEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a85bf-201">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="a85bf-201">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a85bf-202">會話百分比會引發 DeviceRenderZeroVolume 事件，使其處於「不良」狀態。</span><span class="sxs-lookup"><span data-stu-id="a85bf-202">Percentage of session the DeviceRenderZeroVolume event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="a85bf-203">呈現裝置已設定為零磁片區。</span><span class="sxs-lookup"><span data-stu-id="a85bf-203">The render device was set to zero volume.</span></span></p>
<p><span data-ttu-id="a85bf-204">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="a85bf-204">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a85bf-205"><strong>DeviceRenderMuteEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a85bf-205"><strong>DeviceRenderMuteEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a85bf-206">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="a85bf-206">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a85bf-207">會話百分比會引發 DeviceRenderMute 事件，使其處於「不良」狀態。</span><span class="sxs-lookup"><span data-stu-id="a85bf-207">Percentage of session the DeviceRenderMute event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="a85bf-208">呈現裝置已靜音。</span><span class="sxs-lookup"><span data-stu-id="a85bf-208">The render device was muted.</span></span></p>
<p><span data-ttu-id="a85bf-209">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="a85bf-209">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

