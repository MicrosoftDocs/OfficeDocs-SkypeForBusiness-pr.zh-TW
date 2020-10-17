---
title: Lync Server 2013： VideoStream 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoStream table
ms:assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425928(v=OCS.15)
ms:contentKeyID: 48184014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef5c417ff391bb3ec5954cf12d00f6de3d2e6d9b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518560"
---
# <a name="videostream-table-in-lync-server-2013"></a>Lync Server 2013 中的 VideoStream 表格

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-12-13_

每筆記錄代表一個視頻資料流程。 一個影片媒體行通常包含兩個影片。


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
<td><p><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中從 MediaLine 表格</a>參考的 R。</p></td>
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
<td><p><strong>VideoPayloadDescription</strong></p></td>
<td><p>Smallint</p></td>
<td><p>外部、主要</p></td>
<td><p>負載描述。 如需詳細資訊，請參閱 <a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 中的 PayloadDescription 表格</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>從即時控制通訊協定 (RTCP) 統計資料的平均網路抖動。</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>影片中的最大網路抖動。</p></td>
</tr>
<tr class="even">
<td><p><strong>往返</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>從 RTCP 統計資料來回的時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>影片資料流程的最大來回時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>十進位 (5，4) </p></td>
<td><p> </p></td>
<td><p>通話期間的平均封包遺失率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>十進位 (5，4) </p></td>
<td><p> </p></td>
<td><p>通話期間觀察到的封包遺失上限。</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>影片的封包計數 (即時傳輸通訊協定，RTP) 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEst</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>視頻資料流程的頻寬估計值。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoResolution</strong></p></td>
<td><p>char (9) </p></td>
<td><p> </p></td>
<td><p>影片解析度（圖元寬度乘以圖元高度）。 報告為字串。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoBitRateAvg</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>視頻資料流程的平均位元速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>InboundVideoFrameRateAvg</strong></p></td>
<td><p>十進位 (9，4) </p></td>
<td><p> </p></td>
<td><p>收到的影片框架速率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutboundVideoFrameRateAvg</strong></p></td>
<td><p>十進位 (9，4) </p></td>
<td><p> </p></td>
<td><p>傳送的影片畫面速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoBitRateMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>影片會話期間的最大影片位元速率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoFrameLossRate</strong></p></td>
<td><p>十進位 (9，4) </p></td>
<td><p> </p></td>
<td><p>丟失之總影片幀的百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoFEC</strong></p></td>
<td><p>位</p></td>
<td><p> </p></td>
<td><p>無法使用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoLocalFrameLossPercentageAvg</strong></p></td>
<td><p>十進位 (9，4) </p></td>
<td></td>
<td><p>丟失之總影片幀的百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>CIFQualityRatio</strong></p></td>
<td><p>Tinyint</p></td>
<td></td>
<td><p>一般交換格式之通話的百分比 (CIF) 解析度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VGAQualityRatio</strong></p></td>
<td><p>Tinyint</p></td>
<td></td>
<td><p>VGA 解析度之通話的百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>HD720QualityRatio</strong></p></td>
<td><p>Tinyint</p></td>
<td></td>
<td><p>HD720 解析度之通話的百分比。</p></td>
</tr>
<tr class="odd">
<td><p><strong>NoneDropRatio</strong></p></td>
<td><p>Tinyint</p></td>
<td></td>
<td><p>未放下框架的通話時間百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>BDropRatio</strong></p></td>
<td><p>Tinyint</p></td>
<td></td>
<td><p>以 B 框架丟棄的通話持續時間百分比。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BPDropRatio</strong></p></td>
<td><p>Tinyint</p></td>
<td></td>
<td><p>具有 BP 框架丟棄之通話持續時間的百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>BPSPDropRatio</strong></p></td>
<td><p>Tinyint</p></td>
<td></td>
<td><p>具有 BPSP 框架下沉的通話持續時間百分比。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BPSPIDropRatio</strong></p></td>
<td><p>Tinyint</p></td>
<td></td>
<td><p>具有 BPSPI 框架下沉的通話持續時間百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>入境</strong></p></td>
<td><p>位</p></td>
<td><p> </p></td>
<td><p>接收接收方的資料流程資料。</p></td>
</tr>
<tr class="odd">
<td><p><strong>出境</strong></p></td>
<td><p>位</p></td>
<td><p> </p></td>
<td><p>接收寄件者端的資料流程資料。</p></td>
</tr>
<tr class="even">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>位</p></td>
<td><p> </p></td>
<td><p>1表示資料流程的方向從來電者到被叫方。</p>
<p>0表示資料流程方向從被叫方傳送給來電者。</p></td>
</tr>
<tr class="odd">
<td><p><strong>LossCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>會指出通話處於遺失擁塞狀態的時間百分比。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>DelayCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>會指出在此通話所占的百分比，造成擁塞是由網路封包的延遲抵達所造成。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ContentionDetectedPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>會指出通話在競爭網路資源時的時間百分比。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通話期間測量的頻寬預估最小值。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通話期間測量的頻寬預估最大值。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstStdDev</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通話期間測量的頻寬預估標準差。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstAvge</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通話期間測量的平均頻寬預估量。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>LowBandwidthForMultiview</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>端點決定網路連線無法支援多種顯示的情況影片所占的百分比。</p>
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
<td><p>int</p></td>
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
<td><p><strong>VideoPacketLossRate</strong></p></td>
<td><p>十進位 (9，4) </p></td>
<td></td>
<td><p>視頻封包遺失的速率。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoAllocateBWAvg</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>為影片所分配的平均頻寬量。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendCodecTypes</strong></p></td>
<td><p>Smallint</p></td>
<td><p>Foreign</p></td>
<td><p>寄件者使用的影片編解碼器類型。 如需詳細資訊，請參閱 <a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 中的 CodecDescription 表格</a> 。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendResolutionWidth</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>寄件者使用的解析度寬度。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendResolutionHeight</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>寄件者使用的解析度高度。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>寄件者使用的平均視頻畫面播放速率傳輸。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendBitRateMaximum</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>寄件者的最大位元速率。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendBitRateAverage</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>寄件者的平均位元速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendVideoStreamsMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>寄件者使用的影片資料流程數目上限。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvCodecTypes</strong></p></td>
<td><p>Smallint</p></td>
<td><p>Foreign</p></td>
<td><p>接收器使用的影片代碼。 如需詳細資訊，請參閱 <a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 中的 CodecDescription 表格</a> 。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvResolutionWidth</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>接收器使用的解析度寬度。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvResolutionHeight</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>接收器使用的解析度高度。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>接收器所用的平均影片速率。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvBitRateMaximum</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>接收器的最大位元速率。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvBitRateAverage</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>接收器的平均位元速率。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvVideoStreamsMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>接收器的影片流量上限。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvVideoStreamsMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>接收器的最小影片資料流程。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvVideoStreamsMode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>影片模式 (例如，收件者的畫廊或單一 stream) 。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPostFECPLR</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>套用轉寄錯誤修正後的封包遺失率。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DynamicCapabilityPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>動態功能旗標使用中的時間百分比。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>ResolutionMin</strong></p></td>
<td><p>char (9) </p></td>
<td></td>
<td><p>通話期間測量的最小解析度。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowBitRateCallPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>低於低位元速率閾值的通話百分比 (70 千位/秒) 。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>LowFrameRateCallPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>低於低機架速率閾值的通話百分比 (7.5 每秒，輸入) 的框架。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowResolutionCallPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>最低解析度發生之通話的百分比。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>DurationSeconds</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>通話的長度（秒）。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsAggregatedData</strong></p></td>
<td><p>位</p></td>
<td></td>
<td><p>會指出資料是否已從多個呼叫匯總。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

