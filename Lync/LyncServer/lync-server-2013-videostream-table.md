---
title: 'Lync Server 2013: VideoStream 表格'
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
ms.openlocfilehash: 00abc61fc7ba83b94f3228de91eb9fa6810fc93c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007242"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a>Lync Server 2013 中的 VideoStream 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013 年 12 月 13 日_

每筆記錄代表一個視訊資料流。 視訊媒體上的一行通常包含兩個視訊資料流。


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
<td><p>R 參考來源： <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的來源： MediaLine table</a>。</p></td>
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
<td><p><strong>VideoPayloadDescription</strong></p></td>
<td><p>smallint</p></td>
<td><p>外部、 主要</p></td>
<td><p>裝載的描述。 請參閱如需詳細資訊，<a href="lync-server-2013-payloaddescription-table.md">在 Lync Server 2013 中的為 PayloadDescription table</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>即時控制通訊協定 (RTCP) 統計資料的平均網路抖動。</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>視訊工作階段期間的最大網路抖動。</p></td>
</tr>
<tr class="even">
<td><p><strong>來回</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>RTCP 統計資料中的來回時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>視訊資料流的最大來回時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>decimal(5,4)</p></td>
<td><p> </p></td>
<td><p>通話期間的平均封包遺失率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>decimal(5,4)</p></td>
<td><p> </p></td>
<td><p>觀察到的通話期間的最大封包遺失。</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>視訊資料流 （即時傳輸通訊協定 （RTP）） 的封包計數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEst</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>視訊資料流的頻寬預估值。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoResolution</strong></p></td>
<td><p>char(9)</p></td>
<td><p> </p></td>
<td><p>以像素為單位寬度乘以像素為單位的高度的視訊解析度。 報告做為字串。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoBitRateAvg</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>視訊資料流的平均位元速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>InboundVideoFrameRateAvg</strong></p></td>
<td><p>decimal(9,4)</p></td>
<td><p> </p></td>
<td><p>已接收視訊播放速率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutboundVideoFrameRateAvg</strong></p></td>
<td><p>decimal(9,4)</p></td>
<td><p> </p></td>
<td><p>傳送視訊播放速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoBitRateMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>視訊工作階段期間的最大視訊位元速率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoFrameLossRate</strong></p></td>
<td><p>decimal(9,4)</p></td>
<td><p> </p></td>
<td><p>便會遺失之視訊框總數的百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoFEC</strong></p></td>
<td><p>位元</p></td>
<td><p> </p></td>
<td><p>無法使用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoLocalFrameLossPercentageAvg</strong></p></td>
<td><p>decimal(9,4)</p></td>
<td></td>
<td><p>便會遺失之視訊框總數的百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>CIFQualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>常見 Interchange Format (CIF) 解析度之通話百分比。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VGAQualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>VGA 解析度之通話百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>HD720QualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>HD720 解析度之通話百分比。</p></td>
</tr>
<tr class="odd">
<td><p><strong>NoneDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>未捨棄框架的通話時間百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>BDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>捨棄 B 框架的通話時間百分比。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BPDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>捨棄 BP 框架的通話時間百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>BPSPDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Bpsp 框架的通話時間百分比。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BPSPIDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Bpspi 框架的通話時間百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>輸入</strong></p></td>
<td><p>位元</p></td>
<td><p> </p></td>
<td><p>所收到的接收端的資料流資料。</p></td>
</tr>
<tr class="odd">
<td><p><strong>輸出</strong></p></td>
<td><p>位元</p></td>
<td><p> </p></td>
<td><p>所收到的一邊寄件者的資料流資料。</p></td>
</tr>
<tr class="even">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>位元</p></td>
<td><p> </p></td>
<td><p>1 表示資料流是從發話者流向受話者。</p>
<p>0 表示資料流是從受話者流向發話者。</p></td>
</tr>
<tr class="odd">
<td><p><strong>LossCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>指出通話處於遺漏壅塞狀態的時間百分比。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="even">
<td><p><strong>DelayCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>會指出在這期間抵達造成壅塞的網路封包延遲抵達的通話百分比。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ContentionDetectedPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>會指出當通話爭用網路資源的時間百分比。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通話期間測量的頻寬預估最小值。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通話期間測量的頻寬預估最大數量。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstStdDev</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通話期間測量的頻寬預估標準差。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstAvge</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通話期間測量的頻寬預估平均量。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="even">
<td><p><strong>LowBandwidthForMultiview</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>結束點決定的網路連線無法支援 multiview 視訊通話百分比。</p>
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
<td><p>int</p></td>
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
<td><p><strong>VideoPacketLossRate</strong></p></td>
<td><p>decimal(9,4)</p></td>
<td></td>
<td><p>視訊封包丟失的速率。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoAllocateBWAvg</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>分配給視訊的頻寬平均量。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendCodecTypes</strong></p></td>
<td><p>smallint</p></td>
<td><p>Foreign</p></td>
<td><p>使用寄件者的視訊轉碼器類型。 請參閱<a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 中的 CodecDescription 表</a>如需詳細資訊。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendResolutionWidth</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>寄件者所使用的解析度寬度。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendResolutionHeight</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>寄件者所使用的解析度高度。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>寄件者所使用的平均視訊播放速率傳輸。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendBitRateMaximum</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>寄件者的最大位元速率。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
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
<td><p>最大數目由寄件者的視訊資料流的詳細資訊。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvCodecTypes</strong></p></td>
<td><p>smallint</p></td>
<td><p>Foreign</p></td>
<td><p>接收者使用的視訊的代碼。 請參閱<a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 中的 CodecDescription 表</a>如需詳細資訊。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvResolutionWidth</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>接收者使用的解析度寬度。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvResolutionHeight</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>接收者使用的解析度高度。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>接收者使用的平均視訊播放速率。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvBitRateMaximum</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>接收者的最大位元速率。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvBitRateAverage</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>接收者的平均位元速率。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvVideoStreamsMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>接收者的最大視訊資料流。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvVideoStreamsMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>接收者的最小視訊資料流。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvVideoStreamsMode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>（例如圖庫或單一資料流） 接收者的視訊模式。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPostFECPLR</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>封包遺失率之後已套用正向錯誤修正。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DynamicCapabilityPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>動態功能旗幟的時間百分比。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="even">
<td><p><strong>ResolutionMin</strong></p></td>
<td><p>char(9)</p></td>
<td></td>
<td><p>通話期間測量最小解析。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowBitRateCallPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>低位元速率臨界值 （每秒 70 kbps） 以下的通話百分比。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="even">
<td><p><strong>LowFrameRateCallPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>低播放速率臨界值以下的通話百分比 （每秒 7.5 個畫面輸入）。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowResolutionCallPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>以最低解析度進行的通話百分比。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="even">
<td><p><strong>DurationSeconds</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>以秒為單位之通話的長度。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsAggregatedData</strong></p></td>
<td><p>位元</p></td>
<td></td>
<td><p>會指出資料是否已彙總從多個通話。</p>
<p>Microsoft Lync Server 2013 中已引進此欄。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

