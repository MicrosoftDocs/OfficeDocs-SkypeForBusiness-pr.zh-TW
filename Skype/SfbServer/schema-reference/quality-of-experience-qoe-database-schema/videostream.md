---
title: VideoStream 表格
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
description: 每筆記錄代表一個視頻資料流程。 一個影片媒體行通常包含兩個影片。
ms.openlocfilehash: fde5036803bd02bed4b766ca9e6d2419d9b4cca92d78968867e18e9e4083897e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322905"
---
# <a name="videostream-table"></a>VideoStream 表格
 
每筆記錄代表一個視頻資料流程。 一個影片媒體行通常包含兩個影片。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |主要  <br/> |從 [MediaLine 表格](medialine-0.md)中參照。  <br/> |
|**SessionSeq** <br/> |int  <br/> |主要  <br/> |從 [MediaLine 表格](medialine-0.md)參考的 R。  <br/> |
|**MediaLineLabel** <br/> |Tinyint  <br/> |主要  <br/> |從 [MediaLine 表格](medialine-0.md)中參照。  <br/> |
|**StreamID** <br/> |int  <br/> |主要  <br/> |媒體行中的唯一識別碼。  <br/> |
|**VideoPayloadDescription** <br/> |Smallint  <br/> |外部、主要  <br/> |負載描述。 如需詳細資訊，請參閱 [PayloadDescription 表格](payloaddescription.md) 。 <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |從即時控制通訊協定 (RTCP) 統計資料的平均網路抖動。  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |影片中的最大網路抖動。  <br/> |
|**往返** <br/> |int  <br/> | <br/> |從 RTCP 統計資料來回的時間。  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |影片資料流程的最大來回時間。  <br/> |
|**PacketLossRate** <br/> |十進位 (5，4)   <br/> | <br/> |通話期間的平均封包遺失率。  <br/> |
|**PacketLossRateMax** <br/> |十進位 (5，4)   <br/> | <br/> |通話期間觀察到的封包遺失上限。  <br/> |
|**PacketUtilization** <br/> |int  <br/> | <br/> |影片的封包計數 (即時傳輸通訊協定，RTP) 。  <br/> |
|**BandwidthEst** <br/> |int  <br/> | <br/> |視頻資料流程的頻寬估計值。  <br/> |
|**VideoResolution** <br/> |char (9)   <br/> | <br/> |影片解析度（圖元寬度乘以圖元高度）。 報告為字串。  <br/> |
|**VideoBitRateAvg** <br/> |int  <br/> | <br/> |視頻資料流程的平均位元速率。  <br/> |
|**InboundVideoFrameRateAvg** <br/> |十進位 (9，4)   <br/> | <br/> |收到的影片框架速率。  <br/> |
|**OutboundVideoFrameRateAvg** <br/> |十進位 (9，4)   <br/> | <br/> |傳送的影片畫面速率。  <br/> |
|**VideoBitRateMax** <br/> |int  <br/> | <br/> |影片會話期間的最大影片位元速率。  <br/> |
|**VideoFrameLossRate** <br/> |十進位 (9，4)   <br/> | <br/> |丟失之總影片幀的百分比。  <br/> |
|**VideoFEC** <br/> |位  <br/> | <br/> |無法使用。  <br/> |
|**VideoLocalFrameLossPercentageAvg** <br/> |十進位 (9，4)   <br/> ||丟失之總影片幀的百分比。  <br/> |
|**CIFQualityRatio** <br/> |Tinyint  <br/> ||一般交換格式之通話的百分比 (CIF) 解析度。  <br/> |
|**VGAQualityRatio** <br/> |Tinyint  <br/> ||VGA 解析度之通話的百分比。  <br/> |
|**HD720QualityRatio** <br/> |Tinyint  <br/> ||HD720 解析度之通話的百分比。  <br/> |
|**NoneDropRatio** <br/> |Tinyint  <br/> ||未放下框架的通話時間百分比。  <br/> |
|**BDropRatio** <br/> |Tinyint  <br/> ||以 B 框架丟棄的通話持續時間百分比。  <br/> |
|**BPDropRatio** <br/> |Tinyint  <br/> ||具有 BP 框架丟棄之通話持續時間的百分比。  <br/> |
|**BPSPDropRatio** <br/> |Tinyint  <br/> ||具有 BPSP 框架下沉的通話持續時間百分比。  <br/> |
|**BPSPIDropRatio** <br/> |Tinyint  <br/> ||具有 BPSPI 框架下沉的通話持續時間百分比。  <br/> |
|**入境** <br/> |位  <br/> | <br/> |接收接收方的資料流程資料。  <br/> |
|**出埠** <br/> |位  <br/> | <br/> |接收寄件者端的資料流程資料。  <br/> |
|**SenderIsCallerPAI** <br/> |位  <br/> | <br/> |1表示資料流程的方向從來電者到被叫方。  <br/> 0表示資料流程方向從被叫方傳送給來電者。  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||會指出通話處於遺失擁塞狀態的時間百分比。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||會指出在此通話所占的百分比，造成擁塞是由網路封包的延遲抵達所造成。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||會指出通話在競爭網路資源時的時間百分比。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||通話期間測量的頻寬預估最小值。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||通話期間測量的頻寬預估最大值。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||通話期間測量的頻寬預估標準差。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||通話期間測量的平均頻寬預估量。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**LowBandwidthForMultiview** <br/> |float  <br/> ||端點決定網路連線無法支援多種顯示的情況影片所占的百分比。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||單向延遲的總金額。 相對單向延遲會測量用戶端與伺服器之間的延遲。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||單向延遲的平均金額。 相對單向延遲會測量用戶端與伺服器之間的延遲。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||單向延遲的最大值。 相對單向延遲會測量用戶端與伺服器之間的延遲。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||總單向突發的發生次數。 "爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。 此度量單位會測量用戶端與伺服器之間的資料流程。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**RelativeOneWayBurstDensity** <br/> |int  <br/> ||總單向爆炸流量密度。 "爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。 此度量單位會測量用戶端與伺服器之間的資料流程。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||總單向突發持續時間。 "爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。 此度量單位會測量用戶端與伺服器之間的資料流程。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||對單向間隔的總發生次數。 "爆發" 傳輸是一種傳輸，其中資料流程的資料流程與穩定的資料流程相反，其資料流程會以無法預測的方式傳輸;間隙表示這些猝發間的延遲。 此度量單位會測量用戶端與伺服器之間的資料流程。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||總單向間距密度。 "爆發" 傳輸是一種傳輸，其中資料流程的資料流程與穩定的資料流程相反，其資料流程會以無法預測的方式傳輸;間隙表示這些猝發間的延遲。 此度量單位會測量用戶端與伺服器之間的資料流程。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||總的單向間距持續時間。 "爆發" 傳輸是一種傳輸，其中資料流程的資料流程與穩定的資料流程相反，其資料流程會以無法預測的方式傳輸;間隙表示這些猝發間的延遲。 此度量單位會測量用戶端與伺服器之間的資料流程。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**VideoPacketLossRate** <br/> |十進位 (9，4)   <br/> ||視頻封包遺失的速率。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**VideoAllocateBWAvg** <br/> |int  <br/> ||為影片所分配的平均頻寬量。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**SendCodecTypes** <br/> |Smallint  <br/> |Foreign  <br/> |寄件者使用的影片編解碼器類型。 如需詳細資訊，請參閱 [CodecDescription 表格](codecdescription.md) 。 <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**SendResolutionWidth** <br/> |int  <br/> ||寄件者使用的解析度寬度。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**SendResolutionHeight** <br/> |int  <br/> ||寄件者使用的解析度高度。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**SendFrameRateAverage** <br/> |float  <br/> ||寄件者使用的平均視頻畫面播放速率傳輸。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**SendBitRateMaximum** <br/> |int  <br/> ||寄件者的最大位元速率。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**SendBitRateAverage** <br/> |int  <br/> ||寄件者的平均位元速率。  <br/> |
|**SendVideoStreamsMax** <br/> |int  <br/> ||寄件者使用的影片資料流程數目上限。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**RecvCodecTypes** <br/> |Smallint  <br/> |Foreign  <br/> |接收器使用的影片代碼。 如需詳細資訊，請參閱 [CodecDescription 表格](codecdescription.md) 。 <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**RecvResolutionWidth** <br/> |int  <br/> ||接收器使用的解析度寬度。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**RecvResolutionHeight** <br/> |int  <br/> ||接收器使用的解析度高度。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**RecvFrameRateAverage** <br/> |float  <br/> ||接收器所用的平均影片速率。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**RecvBitRateMaximum** <br/> |int  <br/> ||接收器的最大位元速率。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**RecvBitRateAverage** <br/> |int  <br/> ||接收器的平均位元速率。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**RecvVideoStreamsMax** <br/> |int  <br/> ||接收器的影片流量上限。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**RecvVideoStreamsMin** <br/> |int  <br/> ||接收器的最小影片資料流程。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**RecvVideoStreamsMode** <br/> |int  <br/> ||影片模式 (例如，收件者的畫廊或單一 stream) 。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**VideoPostFECPLR** <br/> |float  <br/> ||套用轉寄錯誤修正後的封包遺失率。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**DynamicCapabilityPercent** <br/> |float  <br/> ||動態功能旗標使用中的時間百分比。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**ResolutionMin** <br/> |char (9)   <br/> ||通話期間測量的最小解析度。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**LowBitRateCallPercent** <br/> |float  <br/> ||低於低位元速率閾值的通話百分比 (70 千位/秒) 。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**LowFrameRateCallPercent** <br/> |float  <br/> ||低於低機架速率閾值的通話百分比 (7.5 每秒，輸入) 的框架。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**LowResolutionCallPercent** <br/> |float  <br/> ||最低解析度發生之通話的百分比。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**DurationSeconds** <br/> |float  <br/> ||通話的長度（秒）。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**IsAggregatedData** <br/> |位  <br/> ||會指出資料是否已從多個呼叫匯總。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
   

