---
title: Lync Server 2013：AudioSignal 表格
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
ms.openlocfilehash: 950c8457f80c69af5875064fff55c5ac7df61b24
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a>Lync Server 2013 中的 AudioSignal 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-12_

每個記錄代表一個端點的音訊信號度量單位。 通常，每個通話都有兩筆記錄，一個用於呼叫者，另一個則稱為被叫方。


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
<td><p><strong>SendSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>代表 [反後的類比增益控制音訊信號] 層級。 這個指標的單位是 dBmo。 若要取得可接受的品質，至少要有 30 dBmo。 A/V 會議伺服器或 IP 電話不會報告此統計值。</p></td>
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
<td><p>代表 [反後類比增益控制音訊雜訊] 層級。 這個指標的單位是 dBmo。 針對可接受的品質，它應該小於 35 dBmo。 A/V 會議伺服器或 IP 電話不會報告此統計值。</p></td>
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
<td><p>迴響傳回損失增強指標。 這個指標的單位是 dB。 較低的值代表較少的回音。 A/V 會議伺服器或 IP 電話不會報告此統計值。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSpeakerGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>喇叭前轉譯每五分鐘的平均故障。 若要獲得較高的品質，此頻率應該小於每五分鐘。 無法由 A/V 會議伺服器、中繼伺服器或 IP 電話來報告。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioMicGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>麥克風捕獲每五分鐘的平均故障。 若要獲得良好的品質，這應該少於每五分鐘一次。 無法由 A/V 會議伺服器、中繼伺服器或 IP 電話來報告。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampDriftRateMic</strong></p></td>
<td><p>decimal （9，2）</p></td>
<td><p> </p></td>
<td><p>麥克風裝置時鐘相對於 CPU 時鐘的時鐘偏移速度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampDriftRateSpk</strong></p></td>
<td><p>decimal （9，2）</p></td>
<td><p> </p></td>
<td><p>喇叭裝置時鐘相對於 CPU 時鐘的時鐘偏移速度。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampErrorMicMs</strong></p></td>
<td><p>decimal （9，2）</p></td>
<td><p> </p></td>
<td><p>喇叭裝置時鐘相對於 CPU 時鐘的時鐘偏移速度。</p>
<p>在呼叫的最後20秒內，麥克風捕獲串流的時間戳記錯誤（以毫秒為單位）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampErrorSpkMs</strong></p></td>
<td><p>decimal （9，2）</p></td>
<td><p> </p></td>
<td><p>在呼叫的最後20秒內，演講者轉譯資料流程時間戳記的錯誤（以毫秒為單位）。</p></td>
</tr>
<tr class="even">
<td><p><strong>VsEntryCauses</strong></p></td>
<td><p>Smallint</p></td>
<td><p> </p></td>
<td><p>Voice 開關是一種半雙工模式，可減少中斷能力。 語音切換專案的原因：</p>
<p>ENTER_VS_BADTS 0x01</p>
<p>ENTER_VS_ECHO 0x02</p>
<p>ENTER_VS_FORCEORCONVERGENCE 0x04</p>
<p>ENTER_VS_DNLP 0x08</p>
<p>原因可能是由這些個別原因所組成。 只有在測試用途中，才能啟用 ENTER_VS_FORCEORCONVERGENCE。</p>
<p>此欄的資料類型已在 Microsoft Lync Server 2013 中變更。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoEventCauses</strong></p></td>
<td><p>Tinyint</p></td>
<td><p> </p></td>
<td><p>Echo 事件的原因：</p>
<p>ECHO_EVENT_BAD_TIMESTAMP 0x01</p>
<p>ECHO_EVENT_POSTAEC_ECHO 0x02</p>
<p>ECHO_EVENT_ANLP 0x04</p>
<p>ECHO_EVENT_DNLP 0x08</p>
<p>ECHO_EVENT_MIC_CLIPPING 0x10</p>
<p>ECHO_EVENT_BAD_STATE 0x20</p>
<p>原因可能是由這些個別原因所組成。</p></td>
</tr>
<tr class="even">
<td><p><strong>EchoPercentMicIn</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td><p> </p></td>
<td><p>在麥克風捕獲資料流程中檢測到迴響的時間百分比。 通常，耳機或話機的值較低，而喇叭或獨立喇叭的值則較高。 對於支援板載音響回聲取消的裝置，高值表示迴響洩漏。 對於其他裝置，此規格不應該用來評估裝置品質。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoPercentSend</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td></td>
<td><p>在傳送資料流程中檢測到迴響的時間百分比。 傳送資料流程中的高迴響百分比表示回應洩漏。</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAGCSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>從閘道在中繼伺服器接收到的信號等級;這只適用于中繼伺服器。 這個度量單位是 dBoV。 若要獲得良好的品質，可接受的範圍應該是 [-30 至-18] dBoV。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RxAGCNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>從閘道在中繼伺服器上收到的信號等級。 這只適用于中繼伺服器。 這個度量單位是 dBoV。 若要獲得良好的品質，可接受的範圍應該小於-50 dBoV。</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAvgAGCGain</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>在中繼伺服器端的自動增益控制（AGC）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>InitialSignalLevelRMS</strong></p></td>
<td><p>浮</p></td>
<td><p> </p></td>
<td><p>撥入信號的根平均數（RMS），最多可達呼叫的前30秒。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>頻道1上接收到的信號等級。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>頻道2上接收到的信號等級。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>頻道1上接收到的雜訊等級。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>頻道2上接收的噪音等級。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>頻道1上傳送的信號等級。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>頻道2上傳送的信號等級。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>頻道1上傳送的雜訊等級。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>頻道2上傳送的雜訊等級。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

