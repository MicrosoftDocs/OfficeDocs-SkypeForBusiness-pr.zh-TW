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

# <a name="audioclientevent-table-in-lync-server-2013"></a>Lync Server 2013 中的 AudioClientEvent 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-17_

每個記錄都包含音訊通話中某個端點的用戶端事件。 通常，一個通話有兩筆記錄，一個用於呼叫者，另一個用於被叫方。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>左欄</strong></th>
<th><strong>資料類型</strong></th>
<th><strong>索引鍵/索引</strong></th>
<th><strong>詳細資料</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>首選</p></td>
<td><p>從<a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 資料表中</a>參考。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>首選</p></td>
<td><p>從<a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 資料表中</a>參考。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>Tinyint</p></td>
<td><p>首選</p></td>
<td><p>從<a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 資料表中</a>參考。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>稍微</p></td>
<td><p>首選</p></td>
<td><p>0：被方程式的資料</p>
<p>1：來電者的資料</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkSendQualityEventRatio</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td><p> </p></td>
<td><p>會話針對「錯誤」狀態觸發 NetworkSendQuality 事件的百分比。</p>
<p>在抖動或資料包遺失方面的網路品質很嚴重，而且會影響音訊傳送品質。</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkReceiveQualityEventRatio</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td><p> </p></td>
<td><p>會話針對「錯誤」狀態觸發 ReceiveSendQuality 事件的百分比。</p>
<p>在抖動或資料包遺失方面的網路品質很嚴重，而且會影響接收的音訊品質。</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkDelayEventRatio</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td><p> </p></td>
<td><p>會話針對「錯誤」狀態觸發延遲事件的百分比。 網路延遲是嚴重的，並防止互動式通訊而影響體驗</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkBandwidthLowEventRatio</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td><p> </p></td>
<td><p>會話針對「錯誤」狀態觸發 LowBandwidth 事件的百分比。 可用的頻寬不足以取得可接受的語音體驗。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUInsufficientEventRatio</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td><p> </p></td>
<td><p>會話百分比因「錯誤」狀態而觸發的 CPU 事件不足。 使用目前的形式和應用程式時，沒有足夠的 CPU 週期來處理。 這會導致音訊通道出現扭曲。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHalfDuplexAECEventRatio</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td><p> </p></td>
<td><p>會話針對「錯誤」狀態觸發 DeviceHalfDuplexAEC 事件的百分比。 為了防止回顯，系統會輸入半雙工。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderNotFunctioningEventRatio</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td><p> </p></td>
<td><p>會話針對「錯誤」狀態觸發 DeviceRenderNotFunctioning 事件的百分比。 目前用於會話的轉譯裝置無法正常運作。 這可能會導致單向音訊問題。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceCaptureNotFunctioningEventRatio</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td><p> </p></td>
<td><p>會話針對「錯誤」狀態觸發 DeviceCaptureNotFunctioning 事件的百分比。 目前用於會話的捕獲裝置無法正常運作。 這可能會導致單向音訊問題。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceGlitchesEventRatio</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td><p> </p></td>
<td><p>會話針對「錯誤」狀態觸發 DeviceGlitches 事件的百分比。 在轉譯造成扭曲的音訊時，會發生嚴重的問題。 這些故障可能是由驅動程式問題、延遲的程式呼叫（DPC）風暴（驅動程式）和高 CPU 使用率所造成。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceLowSNREventRatio</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td><p> </p></td>
<td><p>會話針對「錯誤」狀態觸發 DeviceLowSNR 事件的百分比。 捕捉品質很差、極大雜音，或使用者正在遠離麥克風太遠。 這會造成扭曲。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceLowSpeechLevelEventRatio</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td><p> </p></td>
<td><p>會話針對「錯誤」狀態觸發 DeviceLowSpeechLevel 事件的百分比。 使用者的語音等級太低，且系統無法進一步增加。 這可能會造成扭曲或視為單向音訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceClippingEventRatio</strong></p></td>
<td><p>Decimal （5，2）</p></td>
<td><p> </p></td>
<td><p>會話針對「錯誤」狀態觸發 DeviceClipping 事件的百分比。</p>
<p>近距離語音會剪下麥克風，這是由於修剪而進行的最大終點聲音失真。 請務必避免接近結束的麥克風剪輯。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceEchoEventRatio</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td><p> </p></td>
<td><p>會話針對「錯誤」狀態觸發 DeviceEchoEvent 事件的百分比。 裝置或安裝程式導致回應超出系統的補償能力。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceNearEndToEchoRatioEventRatio</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td><p> </p></td>
<td><p>會話針對「錯誤」狀態觸發 DeviceNearEndToEchoRatio 事件的百分比。 使用者的語音太低，因為所捕獲的迴響會影響使用者體驗，因為它限制了中斷使用者的難易程度。 減少喇叭音量，請將麥克風移近交談者。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceMultipleEndpointsEventCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>會話期間觸發 DeviceMultipleEndpoints 事件以取得「錯誤」狀態的次數。 檢測到相同會話中有多個音訊端點，且系統已透過減少轉譯音量進行補償。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHowlingEventCount</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>會話期間觸發 DeviceHowlingEvent 事件以取得「錯誤」狀態的次數。 偵測到音訊意見反應（由多個端點共用音訊路徑所致）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderZeroVolumeEventRatio</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td></td>
<td><p>已觸發 DeviceRenderZeroVolume 事件以「錯誤」狀態的會話百分比。 轉譯裝置已設定為零卷。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceRenderMuteEventRatio</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td></td>
<td><p>已觸發 DeviceRenderMute 事件以「錯誤」狀態的會話百分比。 渲染裝置已靜音。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

