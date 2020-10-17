---
title: Lync Server 2013： AudioStream 表格
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
ms.openlocfilehash: 331b2afbfa4b6c4147ffab3765af4e9e5031c190
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502870"
---
# <a name="audiostream-table-in-lync-server-2013"></a>Lync Server 2013 中的 AudioStream 表格

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-02_

每筆記錄代表一個音訊資料流程。 一個音訊媒體行通常包含兩個音訊資料流程。


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
<td><p><strong>StreamID</strong></p></td>
<td><p>int</p></td>
<td><p>主要</p></td>
<td><p>媒體行中的唯一識別碼。</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>從即時控制通訊協定 (RTCP) 統計資料的平均網路抖動。</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>通話期間的最大網路抖動。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>十進位 (5，4) </p></td>
<td><p> </p></td>
<td><p>通話期間的平均封包遺失率。</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>十進位 (5，4) </p></td>
<td><p> </p></td>
<td><p>通話期間觀察到的封包遺失上限。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BurstDensity</strong></p></td>
<td><p>十進位 (9，4) </p></td>
<td><p> </p></td>
<td><p>通話期間的猝量遺失期間的封包遺失平均密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>BurstDuration</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>通話期間的猝量遺失期間的封包遺失平均持續時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BurstGapDensity</strong></p></td>
<td><p>十進位 (9，4) </p></td>
<td><p> </p></td>
<td><p>封包遺失失敗之間的平均封包遺失密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>BurstGapDuration</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>封包遺失的平均持續時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>臨界值</p></td>
<td><p> </p></td>
<td><p>音訊資料流程的封包計數。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEst</strong></p></td>
<td><p>臨界值</p></td>
<td><p> </p></td>
<td><p>音訊資料流程的頻寬估計值。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DegradationAvg</strong></p></td>
<td><p>十進位 (3，2) </p></td>
<td><p> </p></td>
<td><p>整個通話的網路 MOS 降低。 範圍是0.0 到5.0。 此度量顯示由於抖動和封包遺失，網路 MOS 減少的數量。 可接受的品質應小於0.5。</p></td>
</tr>
<tr class="even">
<td><p><strong>DegradationMax</strong></p></td>
<td><p>十進位 (3，2) </p></td>
<td><p> </p></td>
<td><p>通話期間的最大網路 MOS 降級。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DegradationJitterAvg</strong></p></td>
<td><p>十進位 (3，2) </p></td>
<td><p> </p></td>
<td><p>抖動導致的網路 MOS 降低。</p></td>
</tr>
<tr class="even">
<td><p><strong>DegradationPacketLossAvg</strong></p></td>
<td><p>十進位 (3，2) </p></td>
<td><p> </p></td>
<td><p>封包遺失導致的網路 MOS 降低。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioPayloadDescription</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>用於通話的音訊編解碼器，參考來源為 PayloadDescription Table。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSampleRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>音訊資料流程的取樣速率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>往返</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>從 RTCP 統計資料來回的時間。 若為可接受的品質，則應小於100ms。</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>音訊資料流程的最大來回時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OverallAvgNetworkMOS</strong></p></td>
<td><p>十進位 (3，2) </p></td>
<td><p> </p></td>
<td><p>通話的平均寬頻網路 MOS。 此度量取決於所用的封包遺失、抖動和編解碼器。 範圍為 [1.0 至 5.0]。</p></td>
</tr>
<tr class="even">
<td><p><strong>OverallMinNetworkMOS</strong></p></td>
<td><p>十進位 (3，2) </p></td>
<td><p> </p></td>
<td><p>通話的最小寬頻網路 MOS。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendListenMOS</strong></p></td>
<td><p>十進位 (3，2) </p></td>
<td><p> </p></td>
<td><p>已傳送之音訊的平均預測寬頻傾聽 MOS 分數，包括語音層級、雜訊層級和捕獲裝置特性。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendListenMOSMin</strong></p></td>
<td><p>十進位 (3，2) </p></td>
<td><p> </p></td>
<td><p>通話的最小 SendListenMOS。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvListenMOS</strong></p></td>
<td><p>十進位 (3，2) </p></td>
<td><p> </p></td>
<td><p>從網路接收之音訊的平均預測寬頻傾聽 MOS 分數，包括語音層級、雜訊層級、編解碼器、網路狀況和捕獲裝置特性。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvListenMOSMin</strong></p></td>
<td><p>十進位 (3，2) </p></td>
<td><p> </p></td>
<td><p>通話的最小 RecvListenMOS。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioFECUsed</strong></p></td>
<td><p>位</p></td>
<td></td>
<td><p>指示是否要將音訊 FEC 用於通話的旗標。</p></td>
</tr>
<tr class="even">
<td><p><strong>RatioConcealedSamplesAvg</strong></p></td>
<td><p>十進位 (5，2) </p></td>
<td></td>
<td><p>音訊修復所產生之隱藏樣本與一般範例的平均比率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RatioStretchedSamplesAvg</strong></p></td>
<td><p>十進位 (5，2) </p></td>
<td></td>
<td><p>音訊修復所產生之延伸樣本的平均比率為典型範例。</p></td>
</tr>
<tr class="even">
<td><p><strong>RatioCompressedSamplesAvg</strong></p></td>
<td><p>十進位 (5，2) </p></td>
<td></td>
<td><p>音訊修復所產生之壓縮樣本與一般範例的平均比率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>入境</strong></p></td>
<td><p>位</p></td>
<td><p> </p></td>
<td><p>接收接收方的資料流程資料。</p></td>
</tr>
<tr class="even">
<td><p><strong>出境</strong></p></td>
<td><p>位</p></td>
<td><p> </p></td>
<td><p>接收寄件者端的資料流程資料。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>位</p></td>
<td><p> </p></td>
<td><p>1表示資料流程是從來電者流向被呼叫方。</p>
<p>0表示資料流程方向從被叫方傳送給來電者。</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalSD</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>抖動到達時間的標準差。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConcealRatioMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>修復所隱藏的封包的最大比率。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConcealRatioSD</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>修復所隱藏之封包的標準差。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>HealerPacketDropRatio</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>修復丟棄的封包比率與接收的封包總數。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>HealerFECPacketUsedRatio</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>與接收的封包總數相比，使用轉寄錯誤修正資料包的比例。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxCompressedSamples</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>修復壓縮的音訊封包數目上限。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>LossCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>會指出通話處於遺失擁塞狀態的時間百分比。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DelayCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>會指出在此通話所占的百分比，造成擁塞是由網路封包的延遲抵達所造成。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentionDetectedPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>會指出通話在競爭網路資源時的時間百分比。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通話期間測量的頻寬預估最小值。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通話期間測量的頻寬預估最大值。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstStdDev</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通話期間測量的頻寬預估標準差。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstAvge</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通話期間測量的平均頻寬預估量。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>單向延遲的總金額。 相對單向延遲會測量用戶端與伺服器之間的延遲。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>單向延遲的平均金額。 相對單向延遲會測量用戶端與伺服器之間的延遲。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>單向延遲的最大值。 相對單向延遲會測量用戶端與伺服器之間的延遲。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>總單向突發的發生次數。 "爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。 此度量單位會測量用戶端與伺服器之間的資料流程。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>總單向爆炸流量密度。 "爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。 此度量單位會測量用戶端與伺服器之間的資料流程。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>總單向突發持續時間。 "爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。 此度量單位會測量用戶端與伺服器之間的資料流程。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>對單向間隔的總發生次數。 "爆發" 傳輸是一種傳輸，其中資料流程的資料流程與穩定的資料流程相反，其資料流程會以無法預測的方式傳輸;間隙表示這些猝發間的延遲。 此度量單位會測量用戶端與伺服器之間的資料流程。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>總單向間距密度。 "爆發" 傳輸是一種傳輸，其中資料流程的資料流程與穩定的資料流程相反，其資料流程會以無法預測的方式傳輸;間隙表示這些猝發間的延遲。 此度量單位會測量用戶端與伺服器之間的資料流程。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>總的單向間距持續時間。 "爆發" 傳輸是一種傳輸，其中資料流程的資料流程與穩定的資料流程相反，其資料流程會以無法預測的方式傳輸;間隙表示這些猝發間的延遲。 此度量單位會測量用戶端與伺服器之間的資料流程。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>DecodeStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>解碼為身歷聲的通話百分比。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AecRenderStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>透過聲音回聲效果取消器呈現為身歷聲的通話百分比。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioPostFECPLR</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>套用轉寄錯誤修正後的封包遺失率。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EncodeStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>編碼為身歷聲的通話百分比。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>AecCaptureStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>以身歷聲的回聲效果取消器取得之來電所占的百分比。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

