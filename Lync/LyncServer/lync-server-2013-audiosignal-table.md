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
ms.openlocfilehash: de07393ef9f43346d0c1b4c96dcfdcf33f00513a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a>Lync Server 2013 中的 AudioSignal 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-11-12_

每筆記錄代表一個端點的音訊訊號計量。 通常，每次呼叫具有兩個記錄、 一個是來電者，而另一個做為受話者。


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
<td><p><strong>SendSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>代表後類比獲得控制音訊訊號層級。 此評量單位為 dBmo。 可接受的品質，它應該至少 30 dBmo。 此評量不報告的 A / V 會議伺服器或 IP 電話。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>請參閱 SendSignalLevel。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>代表後類比獲得控制音訊有雜音層級。 此評量單位為 dBmo。 可接受的品質，它應該小於 35 dBmo。 此評量不報告的 A / V 會議伺服器或 IP 電話。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>請參閱 SendNoiseLevel。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoReturn</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>回音傳回遺失增強評量。 此評量單位為 dB。 較低的值代表較少回應。 此評量不報告的 A / V 會議伺服器或 IP 電話。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSpeakerGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>平均每五分鐘喇叭呈現的故障。 為品質良好，這應該是小於每五分鐘。 不報告的 A / V 會議伺服器、 中繼伺服器或 IP 電話。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioMicGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>平均每五分鐘麥克風擷取故障。 良好的品質這應該是小於 1 每五分鐘。 不報告的 A / V 會議伺服器、 中繼伺服器或 IP 電話。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampDriftRateMic</strong></p></td>
<td><p>decimal(9,2)</p></td>
<td><p> </p></td>
<td><p>麥克風裝置時脈的漂移率，相對於 CPU 時脈。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampDriftRateSpk</strong></p></td>
<td><p>decimal(9,2)</p></td>
<td><p> </p></td>
<td><p>喇叭裝置時脈的漂移率，相對於 CPU 時脈。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampErrorMicMs</strong></p></td>
<td><p>decimal(9,2)</p></td>
<td><p> </p></td>
<td><p>喇叭裝置時脈的漂移率，相對於 CPU 時脈。</p>
<p>通話的最後 20 秒中，平均麥克風擷取資料流時間戳記錯誤，單位為毫秒。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampErrorSpkMs</strong></p></td>
<td><p>decimal(9,2)</p></td>
<td><p> </p></td>
<td><p>平均喇叭呈現資料流時間戳記錯誤，以毫秒為單位，通話的最後 20 秒中。</p></td>
</tr>
<tr class="even">
<td><p><strong>VsEntryCauses</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>語音交換是降低的中斷能力與半雙工模式。 語音的原因切換項目：</p>
<p>ENTER_VS_BADTS 0X01</p>
<p>ENTER_VS_ECHO 0X02</p>
<p>ENTER_VS_FORCEORCONVERGENCE 0X04</p>
<p>ENTER_VS_DNLP 0X08</p>
<p>原因可以是這些個別原因的組合。 針對測試目的 regkey 可以只啟用 ENTER_VS_FORCEORCONVERGENCE。</p>
<p>Microsoft Lync Server 2013 中已變更此資料行的資料類型。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoEventCauses</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>回音事件的原因：</p>
<p>ECHO_EVENT_BAD_TIMESTAMP 0X01</p>
<p>ECHO_EVENT_POSTAEC_ECHO 0X02</p>
<p>ECHO_EVENT_ANLP 0X04</p>
<p>ECHO_EVENT_DNLP 0X08</p>
<p>ECHO_EVENT_MIC_CLIPPING 0X10</p>
<p>ECHO_EVENT_BAD_STATE 0X20</p>
<p>原因可以是這些個別原因的組合。</p></td>
</tr>
<tr class="even">
<td><p><strong>EchoPercentMicIn</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>回音麥克風擷取資料流中偵測到時的時間百分比。 一般而言，值為低，耳機或 handsets，及喇叭電話或獨立喇叭較高。 針對支援委任柔和式迴音效果取消功能的裝置，高的值可指出回音外洩。 針對其他裝置，此評量不應該用來評估裝置品質。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoPercentSend</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td></td>
<td><p>當傳送的資料流中偵測到回音的時間百分比。 在高的回音百分比傳送資料流回音遺漏的指示。</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAGCSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>在中繼伺服器上的訊號等級接收來自閘道;僅適用於中繼伺服器。 此評量的單位是 dBoV。 品質良好，可接受的範圍必須是 [-30 至-18] dBoV。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RxAGCNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>來自閘道的中繼伺服器已接收的訊號等級。 僅適用於中繼伺服器。 此評量的單位是 dBoV。 基於品質良好，可接受的範圍應該小於-50 dBoV。</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAvgAGCGain</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>自動增益控制 (AGC) 上之中繼伺服器端。</p></td>
</tr>
<tr class="odd">
<td><p><strong>InitialSignalLevelRMS</strong></p></td>
<td><p>float</p></td>
<td><p> </p></td>
<td><p>平方根 (RMS) 接收的傳入訊號的最多通話前 30 秒。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>頻道 1 上接收的訊號等級。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>頻道 2 上接收的訊號等級。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>頻道 1 上接收雜訊層級。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>頻道 2 上接收雜訊層級。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>頻道 1 上傳送的訊號等級。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>頻道 2 上傳送的訊號等級。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>頻道 1 上傳送雜訊層級。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>頻道 2 上傳送雜訊層級。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

