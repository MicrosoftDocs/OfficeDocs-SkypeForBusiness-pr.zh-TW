---
title: Lync Server 2013：AudioStream 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioStream table
ms:assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425961(v=OCS.15)
ms:contentKeyID: 48184077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97a8015bce118991b21b541faf588dd4d76ac784
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a>Lync Server 2013 中的 AudioStream 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-02_

每個記錄代表一個音訊資料流程。 一個音訊媒體行通常包含兩個音訊資料流程。


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
<td><p><strong>StreamID</strong></p></td>
<td><p>int</p></td>
<td><p>首選</p></td>
<td><p>媒體線中的唯一識別碼。</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>從即時控制通訊協定（RTCP）統計資料的平均網路抖動。</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>通話期間網路抖動的最大值。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>十進位（5，4）</p></td>
<td><p> </p></td>
<td><p>通話期間的平均資料包遺失率。</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>十進位（5，4）</p></td>
<td><p> </p></td>
<td><p>通話期間觀察到的最大資料包遺失。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BurstDensity</strong></p></td>
<td><p>十進位（9，4）</p></td>
<td><p> </p></td>
<td><p>通話期間猝發損失期間的平均資料包遺失密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>BurstDuration</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>通話期間猝發損失期間的平均資料包遺失時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BurstGapDensity</strong></p></td>
<td><p>十進位（9，4）</p></td>
<td><p> </p></td>
<td><p>在突發資料包遺失之間的間隔期間的平均資料包遺失密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>BurstGapDuration</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>猝發資料包遺失之間的平均持續時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>音訊資料流程的 [資料包計數]。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEst</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>音訊資料流程的頻寬估計值。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DegradationAvg</strong></p></td>
<td><p>decimal （3，2）</p></td>
<td><p> </p></td>
<td><p>整個通話的網路 MOS 下降。 範圍是0.0 到5.0。 這個指標顯示由於抖動和資料包遺失而減少網路 MOS 的數量。 針對可接受的品質，它應該小於0.5。</p></td>
</tr>
<tr class="even">
<td><p><strong>DegradationMax</strong></p></td>
<td><p>decimal （3，2）</p></td>
<td><p> </p></td>
<td><p>通話期間網路 MOS 的最大下降。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DegradationJitterAvg</strong></p></td>
<td><p>decimal （3，2）</p></td>
<td><p> </p></td>
<td><p>抖動造成的網路 MOS 下降。</p></td>
</tr>
<tr class="even">
<td><p><strong>DegradationPacketLossAvg</strong></p></td>
<td><p>decimal （3，2）</p></td>
<td><p> </p></td>
<td><p>因數據包遺失而造成的網路 MOS 下降。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioPayloadDescription</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>用於通話的音訊編解碼器，從 PayloadDescription 資料表中引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSampleRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>音訊資料流程的採樣速率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>環路</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>從 RTCP 統計資料中往返的時間。 針對可接受的品質，這應該小於100ms。</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>音訊資料流程的最大往返行程時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OverallAvgNetworkMOS</strong></p></td>
<td><p>decimal （3，2）</p></td>
<td><p> </p></td>
<td><p>通話的平均 wideband 網路 MOS。 這個指標取決於所使用的資料包遺失、抖動和編解碼器。 範圍是 [1.0 到 5.0]。</p></td>
</tr>
<tr class="even">
<td><p><strong>OverallMinNetworkMOS</strong></p></td>
<td><p>decimal （3，2）</p></td>
<td><p> </p></td>
<td><p>通話的最小 wideband 網路 MOS。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendListenMOS</strong></p></td>
<td><p>decimal （3，2）</p></td>
<td><p> </p></td>
<td><p>已傳送音訊的平均預計 wideband 偵聽 MOS 分數，包括語音等級、雜訊等級及捕捉裝置特徵。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendListenMOSMin</strong></p></td>
<td><p>decimal （3，2）</p></td>
<td><p> </p></td>
<td><p>通話的最小 SendListenMOS。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvListenMOS</strong></p></td>
<td><p>decimal （3，2）</p></td>
<td><p> </p></td>
<td><p>從網路接收的音訊的平均預計 wideband，包括語音電平、雜訊層級、編解碼器、網路條件及捕獲裝置功能。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvListenMOSMin</strong></p></td>
<td><p>decimal （3，2）</p></td>
<td><p> </p></td>
<td><p>通話的最小 RecvListenMOS。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioFECUsed</strong></p></td>
<td><p>稍微</p></td>
<td></td>
<td><p>指示是否已使用音訊 FEC 進行通話的標記。</p></td>
</tr>
<tr class="even">
<td><p><strong>RatioConcealedSamplesAvg</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td></td>
<td><p>從音訊康復產生的隱藏樣本到典型範例的平均比率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RatioStretchedSamplesAvg</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td></td>
<td><p>從音訊康復產生的延伸樣本數與典型範例的平均比率。</p></td>
</tr>
<tr class="even">
<td><p><strong>RatioCompressedSamplesAvg</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td></td>
<td><p>從音訊修復到典型範例所產生之壓縮樣本的平均比率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>進貨</strong></p></td>
<td><p>稍微</p></td>
<td><p> </p></td>
<td><p>收到接收器端的資料流程資料。</p></td>
</tr>
<tr class="even">
<td><p><strong>發</strong></p></td>
<td><p>稍微</p></td>
<td><p> </p></td>
<td><p>收到寄件者端的資料流程資料。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>稍微</p></td>
<td><p> </p></td>
<td><p>1表示資料流程方向從來電者到被叫方。</p>
<p>0表示資料流程方向是從被叫方到來電者。</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalSD</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>抖動到貨時間的標準差。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConcealRatioMax</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>Healer 所隱藏之資料包的最大比率。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConcealRatioSD</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>Healer 所隱藏之資料包之比率的標準差。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>HealerPacketDropRatio</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>Healer 丟棄的資料包與接收的總數據包數目之比。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>HealerFECPacketUsedRatio</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>與接收到的總數據包數目相比，已使用的轉寄錯誤修正資料包的比例。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxCompressedSamples</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>Healer 壓縮的音訊資料包數目上限。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>LossCongestionPercent</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>表示通話處於遺失擁塞狀態的時間百分比。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DelayCongestionPercent</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>指出因網路資料包損損，導致堵塞的時間百分比。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentionDetectedPercent</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>表示通話爭用網路資源的時間百分比。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>呼叫期間測量的最小頻寬估計量。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>呼叫期間測量的最大頻寬估計量。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstStdDev</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>在通話期間測量之頻寬估計的標準差。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstAvge</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通話期間平均測量的頻寬估計量。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>單向延遲的總金額。 相對單向延遲會測量用戶端與伺服器之間的延遲。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayAverage</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>單向延隔時間的平均量。 相對單向延遲會測量用戶端與伺服器之間的延遲。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>單向延隔時間的最大值。 相對單向延遲會測量用戶端與伺服器之間的延遲。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>單向突發發生次數總計。 "Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。 此量度會測量用戶端與伺服器之間的資料流程。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>總計單向突發密度。 "Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。 此量度會測量用戶端與伺服器之間的資料流程。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>總計單向突發持續時間。 "Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。 此量度會測量用戶端與伺服器之間的資料流程。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>總的單向間距發生情況。 "Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程;[空隙] 表示這些猝發之間的延遲。 此量度會測量用戶端與伺服器之間的資料流程。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>總單向間距密度。 "Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程;[空隙] 表示這些猝發之間的延遲。 此量度會測量用戶端與伺服器之間的資料流程。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>總共一個單向間距時間。 "Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程;[空隙] 表示這些猝發之間的延遲。 此量度會測量用戶端與伺服器之間的資料流程。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>DecodeStereoPercent</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>解碼為身歷聲的通話百分比。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AecRenderStereoPercent</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>以身歷聲顯示的通話百分比，透過聲音回音 canceller。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioPostFECPLR</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>已套用轉寄錯誤修正之後的資料包遺失率。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EncodeStereoPercent</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>編碼為身歷聲的通話百分比。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>AecCaptureStereoPercent</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>以身歷聲的 canceller 所捕獲的通話百分比。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

