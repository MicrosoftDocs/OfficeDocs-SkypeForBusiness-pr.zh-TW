---
title: 'Lync Server 2013: AudioStream 表格'
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
ms.openlocfilehash: 0f169a00a9eff262d0229daf6e52110d64cf7a34
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145472"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a>Lync Server 2013 中的 AudioStream 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-02_

每筆記錄代表一個音訊資料流。 音訊媒體上的一行通常包含兩個音訊資料流。


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
<td><p><strong>StreamID</strong></p></td>
<td><p>int</p></td>
<td><p>主要</p></td>
<td><p>媒體行中的唯一識別碼。</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>即時控制通訊協定 (RTCP) 統計資料的平均網路抖動。</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>通話期間的最大網路抖動。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>decimal(5,4)</p></td>
<td><p> </p></td>
<td><p>通話期間的平均封包遺失率。</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>decimal(5,4)</p></td>
<td><p> </p></td>
<td><p>觀察到的通話期間的最大封包遺失。</p></td>
</tr>
<tr class="odd">
<td><p><strong>密度連續</strong></p></td>
<td><p>decimal(9,4)</p></td>
<td><p> </p></td>
<td><p>量激增時的通話期間的封包遺失平均密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>BurstDuration</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>封包遺失量激增時的通話期間的平均持續時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BurstGapDensity</strong></p></td>
<td><p>decimal(9,4)</p></td>
<td><p> </p></td>
<td><p>封包遺失量激增之間的間歇期封包遺失平均密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>BurstGapDuration</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>封包遺失量激增之間的間歇期平均持續時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>臨界值</p></td>
<td><p> </p></td>
<td><p>音訊資料流的封包計數。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEst</strong></p></td>
<td><p>臨界值</p></td>
<td><p> </p></td>
<td><p>音訊資料流的頻寬預估值。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DegradationAvg</strong></p></td>
<td><p>decimal(3,2)</p></td>
<td><p> </p></td>
<td><p>整個通話的網路 MOS 降低。 範圍是介於 0.0 到 5.0。 此評量顯示網路 MOS 降低由於抖動和封包遺失量。 可接受的品質它應該小於 0.5。</p></td>
</tr>
<tr class="even">
<td><p><strong>DegradationMax</strong></p></td>
<td><p>decimal(3,2)</p></td>
<td><p> </p></td>
<td><p>通話期間的最大網路 MOS 降低。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DegradationJitterAvg</strong></p></td>
<td><p>decimal(3,2)</p></td>
<td><p> </p></td>
<td><p>抖動所導致的網路 MOS 降低。</p></td>
</tr>
<tr class="even">
<td><p><strong>DegradationPacketLossAvg</strong></p></td>
<td><p>decimal(3,2)</p></td>
<td><p> </p></td>
<td><p>封包遺失所導致的網路 MOS 降低。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioPayloadDescription</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>音訊轉碼器通話，參考來源： PayloadDescription Table。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSampleRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>音訊資料流的取樣率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>來回</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>RTCP 統計資料中的來回時間。 可接受的品質這應該是小於 100 毫秒。</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>音訊資料流的最大來回時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OverallAvgNetworkMOS</strong></p></td>
<td><p>decimal(3,2)</p></td>
<td><p> </p></td>
<td><p>平均寬頻網路 MOS 通話。 此評量取決於封包遺失、 抖動，以及使用轉碼器。 範圍是 [1.0 到 5.0]。</p></td>
</tr>
<tr class="even">
<td><p><strong>OverallMinNetworkMOS</strong></p></td>
<td><p>decimal(3,2)</p></td>
<td><p> </p></td>
<td><p>最小寬頻網路 MOS 通話。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendListenMOS</strong></p></td>
<td><p>decimal(3,2)</p></td>
<td><p> </p></td>
<td><p>平均預測的寬頻傾聽 MOS 分數所傳送之音訊，包括語音層級、 雜訊層級和擷取裝置特性。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendListenMOSMin</strong></p></td>
<td><p>decimal(3,2)</p></td>
<td><p> </p></td>
<td><p>最小 SendListenMOS。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvListenMOS</strong></p></td>
<td><p>decimal(3,2)</p></td>
<td><p> </p></td>
<td><p>從包括語音層級、 雜訊層級、 轉碼器、 網路狀況和擷取裝置特性網路接收之音訊的平均預測的寬頻傾聽 MOS 分數。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvListenMOSMin</strong></p></td>
<td><p>decimal(3,2)</p></td>
<td><p> </p></td>
<td><p>最小 RecvListenMOS。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioFECUsed</strong></p></td>
<td><p>位元</p></td>
<td></td>
<td><p>指出是否將音訊 FEC 用於通話的旗標。</p></td>
</tr>
<tr class="even">
<td><p><strong>RatioConcealedSamplesAvg</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td></td>
<td><p>一般樣本的音訊修復所產生之隱藏樣本的平均比率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RatioStretchedSamplesAvg</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td></td>
<td><p>一般樣本的音訊修復所產生的延伸樣本的平均比率。</p></td>
</tr>
<tr class="even">
<td><p><strong>RatioCompressedSamplesAvg</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td></td>
<td><p>一般樣本的音訊修復所產生之壓縮樣本的平均比率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>輸入</strong></p></td>
<td><p>位元</p></td>
<td><p> </p></td>
<td><p>所收到的接收端的資料流資料。</p></td>
</tr>
<tr class="even">
<td><p><strong>輸出</strong></p></td>
<td><p>位元</p></td>
<td><p> </p></td>
<td><p>所收到的一邊寄件者的資料流資料。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>位元</p></td>
<td><p> </p></td>
<td><p>1 表示資料流是從發話者流向受話者。</p>
<p>0 表示資料流是從受話者流向發話者。</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalSD</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>抖動到達時間的標準差。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConcealRatioMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>修復隱藏封包的最大比率。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConcealRatioSD</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>修復隱藏封包率的標準差。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="odd">
<td><p><strong>HealerPacketDropRatio</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>修復捨棄封收到封包總數相比的封包的比率。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="even">
<td><p><strong>HealerFECPacketUsedRatio</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>收到封包總數相比的正向錯誤修正封包的比率。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxCompressedSamples</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>音訊修復所壓縮的封包的數目上限。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="even">
<td><p><strong>LossCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>指出通話處於遺漏壅塞狀態的時間百分比。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DelayCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>會指出在這期間抵達造成壅塞的網路封包延遲抵達的通話百分比。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentionDetectedPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>會指出當通話爭用網路資源的時間百分比。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通話期間測量的頻寬預估最小值。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通話期間測量的頻寬預估最大數量。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstStdDev</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通話期間測量的頻寬預估標準差。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstAvge</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通話期間測量的頻寬預估平均量。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>總數量單向延遲的詳細資訊。 相對單向延遲測量用戶端與伺服器之間的延遲時間。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>平均量單向延遲的詳細資訊。 相對單向延遲測量用戶端與伺服器之間的延遲時間。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>最大數量單向延遲的詳細資訊。 相對單向延遲測量用戶端與伺服器之間的延遲時間。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>總單向的高載發生次數。 「 爆發的 「 傳輸是傳輸資料流向中而不穩定的資料流是不可預期的連續的位置。 此評量測量用戶端與伺服器之間的資料流程。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>總單向的高載密度。 「 爆發的 「 傳輸是傳輸資料流向中而不穩定的資料流是不可預期的連續的位置。 此評量測量用戶端與伺服器之間的資料流程。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>總單向的高載持續時間。 「 爆發的 「 傳輸是傳輸資料流向中而不穩定的資料流是不可預期的連續的位置。 此評量測量用戶端與伺服器之間的資料流程。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>總單向的缺口發生次數。 「 爆發的 「 傳輸是傳輸資料流向無法預測激增而不穩定的資料流; 中的位置間斷的傷害指出這些激增之間的延遲。 此評量測量用戶端與伺服器之間的資料流程。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>總單向的缺口密度。 「 爆發的 「 傳輸是傳輸資料流向無法預測激增而不穩定的資料流; 中的位置間斷的傷害指出這些激增之間的延遲。 此評量測量用戶端與伺服器之間的資料流程。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>總單向缺口持續時間。 「 爆發的 「 傳輸是傳輸資料流向無法預測激增而不穩定的資料流; 中的位置間斷的傷害指出這些激增之間的延遲。 此評量測量用戶端與伺服器之間的資料流程。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="even">
<td><p><strong>DecodeStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>解碼為立體聲的通話百分比。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AecRenderStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>由柔和式迴音效果取消器轉換為立體聲的通話百分比。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioPostFECPLR</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>封包遺失率之後已套用正向錯誤修正。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EncodeStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>編碼為立體聲的通話百分比。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="even">
<td><p><strong>AecCaptureStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>由柔和式迴音效果取消器擷取為立體聲的通話百分比。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

