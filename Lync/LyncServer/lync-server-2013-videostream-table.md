---
title: Lync Server 2013：VideoStream 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VideoStream table
ms:assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425928(v=OCS.15)
ms:contentKeyID: 48184014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98e0ad3f7c18032dd903d2f8d1d41428ccc12cf9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a>Lync Server 2013 中的 VideoStream 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-12-13_

每個記錄代表一個影片資料流程。 一個影片媒體線通常包含兩個影片串流。


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
<td><p><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 的 MediaLine 資料表中</a>參照 R。</p></td>
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
<td><p><strong>VideoPayloadDescription</strong></p></td>
<td><p>Smallint</p></td>
<td><p>外、主要</p></td>
<td><p>[負載描述]。 如需詳細資訊，請參閱<a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 中</a>的 [PayloadDescription] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>從即時控制通訊協定（RTCP）統計資料的平均網路抖動。</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>在視頻會話期間網路抖動的上限。</p></td>
</tr>
<tr class="even">
<td><p><strong>環路</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>從 RTCP 統計資料中往返的時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>影片串流的最大往返行程時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>十進位（5，4）</p></td>
<td><p> </p></td>
<td><p>通話期間的平均資料包遺失率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>十進位（5，4）</p></td>
<td><p> </p></td>
<td><p>通話期間觀察到的最大資料包遺失。</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>影片串流的資料包計數（即時傳輸通訊協定、RTP）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEst</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>影片串流的頻寬估計值。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoResolution</strong></p></td>
<td><p>char （9）</p></td>
<td><p> </p></td>
<td><p>以圖元為單位的影片解析度，以圖元為單位的寬度乘以圖元高度。 報告為字串。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoBitRateAvg</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>影片串流的平均位元速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>InboundVideoFrameRateAvg</strong></p></td>
<td><p>十進位（9，4）</p></td>
<td><p> </p></td>
<td><p>收到的影片畫面播放速率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutboundVideoFrameRateAvg</strong></p></td>
<td><p>十進位（9，4）</p></td>
<td><p> </p></td>
<td><p>已傳送的影片畫面播放速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoBitRateMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>影片會話期間的最大視頻位元速率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoFrameLossRate</strong></p></td>
<td><p>十進位（9，4）</p></td>
<td><p> </p></td>
<td><p>遺失的視頻畫面總百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoFEC</strong></p></td>
<td><p>稍微</p></td>
<td><p> </p></td>
<td><p>無法使用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoLocalFrameLossPercentageAvg</strong></p></td>
<td><p>十進位（9，4）</p></td>
<td></td>
<td><p>遺失的視頻畫面總百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>CIFQualityRatio</strong></p></td>
<td><p>Tinyint</p></td>
<td></td>
<td><p>常見交換格式（CIF）解析度的通話百分比。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VGAQualityRatio</strong></p></td>
<td><p>Tinyint</p></td>
<td></td>
<td><p>以 VGA 解析度表示的通話百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>HD720QualityRatio</strong></p></td>
<td><p>Tinyint</p></td>
<td></td>
<td><p>HD720 解析度的通話百分比。</p></td>
</tr>
<tr class="odd">
<td><p><strong>NoneDropRatio</strong></p></td>
<td><p>Tinyint</p></td>
<td></td>
<td><p>沒有框架拖放的通話持續時間百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>BDropRatio</strong></p></td>
<td><p>Tinyint</p></td>
<td></td>
<td><p>B 框架下沉的通話持續時間百分比。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BPDropRatio</strong></p></td>
<td><p>Tinyint</p></td>
<td></td>
<td><p>含 BP 框架下沉之通話持續時間百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>BPSPDropRatio</strong></p></td>
<td><p>Tinyint</p></td>
<td></td>
<td><p>BPSP 框架下沉的通話持續時間百分比。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BPSPIDropRatio</strong></p></td>
<td><p>Tinyint</p></td>
<td></td>
<td><p>BPSPI 框架下沉的通話持續時間百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>進貨</strong></p></td>
<td><p>稍微</p></td>
<td><p> </p></td>
<td><p>收到接收器端的資料流程資料。</p></td>
</tr>
<tr class="odd">
<td><p><strong>發</strong></p></td>
<td><p>稍微</p></td>
<td><p> </p></td>
<td><p>收到寄件者端的資料流程資料。</p></td>
</tr>
<tr class="even">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>稍微</p></td>
<td><p> </p></td>
<td><p>1表示資料流程方向從來電者到被叫方。</p>
<p>0表示資料流程方向是從被叫方到來電者。</p></td>
</tr>
<tr class="odd">
<td><p><strong>LossCongestionPercent</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>表示通話處於遺失擁塞狀態的時間百分比。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>DelayCongestionPercent</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>指出因網路資料包損損，導致堵塞的時間百分比。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ContentionDetectedPercent</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>表示通話爭用網路資源的時間百分比。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>呼叫期間測量的最小頻寬估計量。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>呼叫期間測量的最大頻寬估計量。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstStdDev</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>在通話期間測量之頻寬估計的標準差。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstAvge</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通話期間平均測量的頻寬估計量。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>LowBandwidthForMultiview</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>端點判斷網路連接無法支援多種顯示的通話百分比。</p>
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
<td><p>int</p></td>
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
<td><p><strong>VideoPacketLossRate</strong></p></td>
<td><p>十進位（9，4）</p></td>
<td></td>
<td><p>視頻資料包遺失的頻率。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoAllocateBWAvg</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>為影片所分配的平均頻寬量。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendCodecTypes</strong></p></td>
<td><p>Smallint</p></td>
<td><p>外</p></td>
<td><p>寄件者所用的視頻編解碼器類型。 如需詳細資訊，請參閱<a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 中</a>的 [CodecDescription] 資料表。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendResolutionWidth</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>寄件者使用的解析度寬度。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendResolutionHeight</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>寄件者使用的解析度高度。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendFrameRateAverage</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>寄件者使用的平均視頻畫面播放速率傳輸。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendBitRateMaximum</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>該寄件者的最大位元速率。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
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
<td><p>寄件者使用的最大視頻串流數。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvCodecTypes</strong></p></td>
<td><p>Smallint</p></td>
<td><p>外</p></td>
<td><p>接收器所使用的影片代碼。 如需詳細資訊，請參閱<a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 中</a>的 [CodecDescription] 資料表。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvResolutionWidth</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>接收器所使用的解析度寬度。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvResolutionHeight</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>接收器所使用的解析度高度。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvFrameRateAverage</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>接收器所使用的平均視頻畫面播放速率。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvBitRateMaximum</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>接收器的最大位元速率。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvBitRateAverage</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>接收器的平均位元速率。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvVideoStreamsMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>接收器的最大影片流量。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvVideoStreamsMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>接收器的最小視頻流量。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvVideoStreamsMode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>接收器的影片模式（例如圖庫或單一資料流程）。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPostFECPLR</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>已套用轉寄錯誤修正之後的資料包遺失率。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DynamicCapabilityPercent</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>動態功能標誌作用中的時間百分比。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>ResolutionMin</strong></p></td>
<td><p>char （9）</p></td>
<td></td>
<td><p>通話期間測量的最小解析度。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowBitRateCallPercent</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>通話百分比低於低位率閾值（70 kb/秒）。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>LowFrameRateCallPercent</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>通話百分比低於低畫面播放速率閾值（7.5 幀/秒、入站）。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowResolutionCallPercent</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>最低解析度所發生通話的百分比。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>DurationSeconds</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>通話長度（以秒為單位）。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsAggregatedData</strong></p></td>
<td><p>稍微</p></td>
<td></td>
<td><p>指示資料是否已從多個通話匯總。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

