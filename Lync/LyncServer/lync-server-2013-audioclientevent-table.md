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
ms.openlocfilehash: d93a9cd9276ba2bdaacf892ca0ab3f4240458503
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203459"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audioclientevent-table-in-lync-server-2013"></a>Lync Server 2013 中的 AudioClientEvent 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-17_

每一筆記錄含有一個端點音訊通話的用戶端事件。 通常，一次呼叫會有兩個記錄、 一個來電者，一個用於受話者。


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
<th><strong>主索引鍵 /</strong></th>
<th><strong>詳細資料</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主要</p></td>
<td><p>參考來源： <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的來源： MediaLine table</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主要</p></td>
<td><p>參考來源： <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的來源： MediaLine table</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>主要</p></td>
<td><p>參考來源： <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的來源： MediaLine table</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>位元</p></td>
<td><p>主要</p></td>
<td><p>0： 受話者的資料</p>
<p>1： 發話者的資料</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkSendQualityEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>工作階段百分比 NetworkSendQuality 事件引發 「 故障 」 狀態。</p>
<p>在網路品質來說抖動或封包遺失相當嚴重且會影響所接收的音訊品質。</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkReceiveQualityEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>工作階段百分比 receivesendquality 「 故障 」 狀態。</p>
<p>在網路品質來說抖動或封包遺失相當嚴重且會影響所接收的音訊品質。</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkDelayEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>工作階段百分比延遲事件引發 「 故障 」 狀態。 網路延遲相當嚴重，藉由防止互動式通訊以至體驗</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkBandwidthLowEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>工作階段百分比 LowBandwidth 事件引發 「 故障 」 狀態。 可用的頻寬不足的可接受的語音體驗。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUInsufficientEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>工作階段沒有足夠的 CPU 事件引發 「 故障 」 狀態的百分比。 有沒有足夠的 CPU 循環處理與目前的形式和使用中的應用程式。 這會導致失真音訊的通道。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHalfDuplexAECEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>工作階段百分比 DeviceHalfDuplexAEC 事件引發 「 故障 」 狀態。 若要避免回音，系統已輸入半雙工。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderNotFunctioningEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>工作階段百分比 DeviceRenderNotFunctioning 事件引發 「 故障 」 狀態。 目前工作階段使用轉換裝置無法正常運作。 這可能會導致單向音訊問題。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceCaptureNotFunctioningEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>工作階段百分比 DeviceCaptureNotFunctioning 事件引發 「 故障 」 狀態。 目前使用的工作階段的擷取裝置無法正常運作。 這可能會導致單向音訊問題。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceGlitchesEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>工作階段百分比 DeviceGlitches 事件引發 「 故障 」 狀態。 這會導致扭曲音訊的轉譯中有嚴重的故障。 這些故障可能被因驅動程式問題、 延後的程序呼叫 (DPC) 風暴 （驅動程式），以及高 CPU 使用率。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceLowSNREventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>工作階段百分比 DeviceLowSNR 事件引發 「 故障 」 狀態。 可以是非常不佳，擷取品質非常吵雜或使用者從麥克風太遠交談。 這會導致扭曲。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceLowSpeechLevelEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>工作階段百分比 DeviceLowSpeechLevel 事件引發 「 故障 」 狀態。 使用者的語音層級很太低，且系統無法增加其任何進一步。 這可能也會造成扭曲或認知以單向音訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceClippingEventRatio</strong></p></td>
<td><p>Decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>工作階段百分比 DeviceClipping 事件引發 「 故障 」 狀態。</p>
<p>當附近端語音剪裁麥克風時，距離端會聽到由於裁剪圖像扭曲。 請務必避免結束靠近麥克風雜音。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceEchoEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>工作階段百分比 DeviceEchoEvent 事件引發 「 故障 」 狀態。 裝置或安裝程式會造成回音超出來彌補系統的能力。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceNearEndToEchoRatioEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>工作階段百分比 DeviceNearEndToEchoRatio 事件引發 「 故障 」 狀態。 使用者的語音是太低相較於回音正在擷取影響使用者經驗，因為它限制了中斷使用者何其輕鬆。 減少喇叭音量，將靠近麥克風移至 「 說話者 」。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceMultipleEndpointsEventCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>工作階段 DeviceMultipleEndpoints 事件引發 「 故障 」 狀態的次數。 偵測到相同的工作階段中的多個音訊端點和系統具有補償藉由減少轉譯磁碟區。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHowlingEventCount</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>工作階段 DeviceHowlingEvent 事件引發 「 故障 」 狀態的次數。 偵測到的音訊回饋迴圈 （因共用音訊路徑的多個端點）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderZeroVolumeEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td></td>
<td><p>百分比的工作階段 DeviceRenderZeroVolume 事件會出現在 「 錯誤 」 狀態。 轉換裝置未設定為零個磁碟區。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceRenderMuteEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td></td>
<td><p>百分比的工作階段 DeviceRenderMute 事件會出現在 「 錯誤 」 狀態。 轉換裝置已設為靜音。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

