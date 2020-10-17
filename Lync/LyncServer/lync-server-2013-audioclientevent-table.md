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
# <a name="audioclientevent-table-in-lync-server-2013"></a>Lync Server 2013 中的 AudioClientEvent 表格

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-17_

每筆記錄都包含音訊撥號中一個端點的用戶端事件。 通常，一個呼叫有兩筆記錄，一個用於來電者，另一個用於呼叫者。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>欄</strong></th>
<th><strong>資料類型</strong></th>
<th><strong>索引鍵/索引</strong></th>
<th><strong>詳細資料</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主要</p></td>
<td><p>從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主要</p></td>
<td><p>從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>Tinyint</p></td>
<td><p>主要</p></td>
<td><p>從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>位</p></td>
<td><p>主要</p></td>
<td><p>0：被呼叫者的資料</p>
<p>1：來電者的資料</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkSendQualityEventRatio</strong></p></td>
<td><p>十進位 (5，2) </p></td>
<td><p> </p></td>
<td><p>會話百分比已針對 ' 壞」狀態引發 NetworkSendQuality 事件。</p>
<p>抖動或封包遺失方面的網路品質很嚴重，且會影響所傳送之音訊的品質。</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkReceiveQualityEventRatio</strong></p></td>
<td><p>十進位 (5，2) </p></td>
<td><p> </p></td>
<td><p>會話百分比已針對 ' 壞」狀態引發 ReceiveSendQuality 事件。</p>
<p>抖動或封包遺失方面的網路品質很嚴重，且會影響所接收的音訊品質。</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkDelayEventRatio</strong></p></td>
<td><p>十進位 (5，2) </p></td>
<td><p> </p></td>
<td><p>會話百分比 Delay 事件因「錯誤」的狀態而引發。 網路延遲是嚴重的，而且會影響互動式通訊的體驗</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkBandwidthLowEventRatio</strong></p></td>
<td><p>十進位 (5，2) </p></td>
<td><p> </p></td>
<td><p>會話百分比 LowBandwidth 事件引發「不良」狀態。 可用的頻寬不足以取得可接受的語音體驗。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUInsufficientEventRatio</strong></p></td>
<td><p>十進位 (5，2) </p></td>
<td><p> </p></td>
<td><p>會話百分比因「壞」狀態而引發的 CPU 事件不足。 使用目前的形式和應用程式來處理的 CPU 週期不足。 這會導致音訊通道失真。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHalfDuplexAECEventRatio</strong></p></td>
<td><p>十進位 (5，2) </p></td>
<td><p> </p></td>
<td><p>會話百分比 DeviceHalfDuplexAEC 事件引發「不良」狀態。 為了避免回聲，系統有輸入半雙工。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderNotFunctioningEventRatio</strong></p></td>
<td><p>十進位 (5，2) </p></td>
<td><p> </p></td>
<td><p>會話百分比 DeviceRenderNotFunctioning 事件引發「不良」狀態。 目前用於會話的呈現裝置無法正常運作。 這可能會造成單向音訊問題。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceCaptureNotFunctioningEventRatio</strong></p></td>
<td><p>十進位 (5，2) </p></td>
<td><p> </p></td>
<td><p>會話百分比 DeviceCaptureNotFunctioning 事件引發「不良」狀態。 目前用於會話的捕獲裝置無法正常運作。 這可能會造成單向音訊問題。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceGlitchesEventRatio</strong></p></td>
<td><p>十進位 (5，2) </p></td>
<td><p> </p></td>
<td><p>會話百分比 DeviceGlitches 事件引發「不良」狀態。 呈現導致失真的音訊時，發生嚴重的難題。 這些難題可能是由於驅動程式問題、延遲的程式呼叫 (DPC) 風暴 (驅動程式) 和高 CPU 使用率而引起。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceLowSNREventRatio</strong></p></td>
<td><p>十進位 (5，2) </p></td>
<td><p> </p></td>
<td><p>會話百分比 DeviceLowSNR 事件引發「不良」狀態。 [！注意] 捕獲品質很低，可能是極大噪音，或是使用者從麥克風的距離太遠。 這會導致失真。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceLowSpeechLevelEventRatio</strong></p></td>
<td><p>十進位 (5，2) </p></td>
<td><p> </p></td>
<td><p>會話百分比 DeviceLowSpeechLevel 事件引發「不良」狀態。 使用者的語音層級太低，系統無法進一步增加。 這可能會造成扭曲或感覺為單向音訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceClippingEventRatio</strong></p></td>
<td><p>十進位 (5，2) </p></td>
<td><p> </p></td>
<td><p>會話百分比已針對 ' 壞」狀態引發 DeviceClipping 事件。</p>
<p>當近序語音剪下麥克風時，會因為剪裁而結束的時間太長。 請務必避免接近端的麥克風剪裁。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceEchoEventRatio</strong></p></td>
<td><p>十進位 (5，2) </p></td>
<td><p> </p></td>
<td><p>會話百分比 DeviceEchoEvent 事件引發「不良」狀態。 裝置或安裝程式導致回應超出系統補償的能力。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceNearEndToEchoRatioEventRatio</strong></p></td>
<td><p>十進位 (5，2) </p></td>
<td><p> </p></td>
<td><p>會話百分比 DeviceNearEndToEchoRatio 事件引發「不良」狀態。 使用者的語音變得太低，因為其所捕獲的回音會影響使用者的體驗，因為它會限制使用者的中斷。 減少喇叭的音量，請將麥克風移近 talker。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceMultipleEndpointsEventCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>會話期間為「不良」狀態引發 DeviceMultipleEndpoints 事件的次數。 偵測到相同會話中的多個音訊端點，而且系統已透過減少轉譯體積量進行補償。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHowlingEventCount</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>會話期間為「不良」狀態引發 DeviceHowlingEvent 事件的次數。 在多個端點共用音訊路徑) 所造成的 (，會偵測到音訊意見反應。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderZeroVolumeEventRatio</strong></p></td>
<td><p>十進位 (5，2) </p></td>
<td></td>
<td><p>會話百分比會引發 DeviceRenderZeroVolume 事件，使其處於「不良」狀態。 呈現裝置已設定為零磁片區。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceRenderMuteEventRatio</strong></p></td>
<td><p>十進位 (5，2) </p></td>
<td></td>
<td><p>會話百分比會引發 DeviceRenderMute 事件，使其處於「不良」狀態。 呈現裝置已靜音。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

