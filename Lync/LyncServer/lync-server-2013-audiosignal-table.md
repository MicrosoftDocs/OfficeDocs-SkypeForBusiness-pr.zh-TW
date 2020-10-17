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
# <a name="audiosignal-table-in-lync-server-2013"></a>Lync Server 2013 中的 AudioSignal 表格

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-12_

每筆記錄代表一個端點的音訊信號計量。 通常，每個呼叫都有兩筆記錄，一個用於來電者，另一個則用於被叫用方。


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
<td><p><strong>SendSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>代表 [類比後增益控制音訊信號] 層級。 此度量單位的單位是 dBmo。 若要取得可接受的品質，至少要有 30 dBmo。 A/V 的會議服務器或 IP 電話不會報告此度量。</p></td>
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
<td><p>代表 [類比後增益控制音訊雜訊層級]。 此度量單位的單位是 dBmo。 針對可接受的品質，它應小於 35 dBmo。 A/V 的會議服務器或 IP 電話不會報告此度量。</p></td>
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
<td><p>迴響傳回遺失增強度量。 此度量單位的單位為 dB。 較低的值表示較少的回聲。 A/V 的會議服務器或 IP 電話不會報告此度量。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSpeakerGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>喇叭轉譯每五分鐘的平均故障。 為了獲得良好的品質，應小於每五分鐘一次。 不會 A/V 會議伺服器、轉送伺服器或 IP 電話上報告。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioMicGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>每五分鐘捕獲麥克風的平均故障。 若為良好的品質，這應小於每五分鐘一次。 不會 A/V 會議伺服器、轉送伺服器或 IP 電話上報告。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampDriftRateMic</strong></p></td>
<td><p>十進位 (9，2) </p></td>
<td><p> </p></td>
<td><p>麥克風裝置時鐘相對於 CPU 時鐘的相對頻率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampDriftRateSpk</strong></p></td>
<td><p>十進位 (9，2) </p></td>
<td><p> </p></td>
<td><p>揚聲器裝置時鐘相對於 CPU 時鐘的相對頻率。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampErrorMicMs</strong></p></td>
<td><p>十進位 (9，2) </p></td>
<td><p> </p></td>
<td><p>揚聲器裝置時鐘相對於 CPU 時鐘的相對頻率。</p>
<p>通話的最後20秒內的平均麥克風捕獲資料流程時間戳記錯誤（毫秒）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampErrorSpkMs</strong></p></td>
<td><p>十進位 (9，2) </p></td>
<td><p> </p></td>
<td><p>通話的最後20秒內，平均喇叭轉譯資料流程時間戳記錯誤（毫秒）。</p></td>
</tr>
<tr class="even">
<td><p><strong>VsEntryCauses</strong></p></td>
<td><p>Smallint</p></td>
<td><p> </p></td>
<td><p>語音開關是一種具有低中斷能力的半雙工模式。 語音開關專案的原因：</p>
<p>ENTER_VS_BADTS 0x01</p>
<p>ENTER_VS_ECHO 0x02</p>
<p>ENTER_VS_FORCEORCONVERGENCE 0x04</p>
<p>ENTER_VS_DNLP 0x08</p>
<p>原因可能是個別原因的組合。 ENTER_VS_FORCEORCONVERGENCE 只能透過 regkey 為測試目的來啟用。</p>
<p>在 Microsoft Lync Server 2013 中，此欄的資料類型已變更。</p></td>
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
<p>原因可能是個別原因的組合。</p></td>
</tr>
<tr class="even">
<td><p><strong>EchoPercentMicIn</strong></p></td>
<td><p>十進位 (5，2) </p></td>
<td><p> </p></td>
<td><p>在麥克風捕獲資料流程中偵測到迴響的時間百分比。 通常，耳機或電話機的值很低，對喇叭或獨立揚聲器而言，其值也會比較高。 針對支援板載聲音回聲取消功能的裝置，高值表示回聲洩漏。 若為其他裝置，則不應該使用此度量來評估裝置品質。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoPercentSend</strong></p></td>
<td><p>十進位 (5，2) </p></td>
<td></td>
<td><p>在傳送的資料流程中偵測到迴響時的時間百分比。 傳送資料流程中的高回音百分比會傳回回聲洩漏。</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAGCSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>從閘道從轉送伺服器接收信號層級;這只適用于轉送伺服器。 此度量單位為 dBoV。 為了獲得良好的品質，可接受的範圍應為 [-30 到-18] dBoV。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RxAGCNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>從閘道從轉送伺服器接收信號層級。 這只適用于轉送伺服器。 此度量單位為 dBoV。 為了獲得良好的品質，可接受的範圍應小於-50 dBoV。</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAvgAGCGain</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p> (AGC) 轉送伺服器端的自動增益控制。</p></td>
</tr>
<tr class="odd">
<td><p><strong>InitialSignalLevelRMS</strong></p></td>
<td><p>float</p></td>
<td><p> </p></td>
<td><p>從來電的前30秒內之傳入信號的根平均平方 (RMS) 。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通道1上接收的信號等級。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通道2上接收的信號等級。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通道1上接收的雜訊層級。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通道2上接收的雜訊水準。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通道1上傳送的信號層級。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通道2上傳送的信號層級。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通道1上傳送的雜訊層級。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通道2上傳送的雜訊層級。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

