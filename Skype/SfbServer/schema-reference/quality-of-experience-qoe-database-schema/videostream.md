---
title: VideoStream 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
description: 每個記錄代表一個影片資料流程。 一個影片媒體線通常包含兩個影片串流。
ms.openlocfilehash: 678f8b14fb3746ddd50a83ebd68c3878237908e4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192610"
---
# <a name="videostream-table"></a>VideoStream 表格
 
每個記錄代表一個影片資料流程。 一個影片媒體線通常包含兩個影片串流。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |首選  <br/> |從[MediaLine 資料表](medialine-0.md)中參照。  <br/> |
|**SessionSeq** <br/> |int  <br/> |首選  <br/> |從[MediaLine 資料表](medialine-0.md)參考 R。  <br/> |
|**MediaLineLabel** <br/> |Tinyint  <br/> |首選  <br/> |從[MediaLine 資料表](medialine-0.md)中參照。  <br/> |
|**StreamID** <br/> |int  <br/> |首選  <br/> |媒體線中的唯一識別碼。  <br/> |
|**VideoPayloadDescription** <br/> |Smallint  <br/> |外、主要  <br/> |[負載描述]。 如需詳細資訊, 請參閱[PayloadDescription 資料表](payloaddescription.md)。 <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |從即時控制通訊協定 (RTCP) 統計資料的平均網路抖動。  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |在視頻會話期間網路抖動的上限。  <br/> |
|**環路** <br/> |int  <br/> | <br/> |從 RTCP 統計資料中往返的時間。  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |影片串流的最大往返行程時間。  <br/> |
|**PacketLossRate** <br/> |十進位 (5, 4)  <br/> | <br/> |通話期間的平均資料包遺失率。  <br/> |
|**PacketLossRateMax** <br/> |十進位 (5, 4)  <br/> | <br/> |通話期間觀察到的最大資料包遺失。  <br/> |
|**PacketUtilization** <br/> |int  <br/> | <br/> |影片串流的資料包計數 (即時傳輸通訊協定、RTP)。  <br/> |
|**BandwidthEst** <br/> |int  <br/> | <br/> |影片串流的頻寬估計值。  <br/> |
|**VideoResolution** <br/> |char (9)  <br/> | <br/> |以圖元為單位的影片解析度, 以圖元為單位的寬度乘以圖元高度。 報告為字串。  <br/> |
|**VideoBitRateAvg** <br/> |int  <br/> | <br/> |影片串流的平均位元速率。  <br/> |
|**InboundVideoFrameRateAvg** <br/> |十進位 (9, 4)  <br/> | <br/> |收到的影片畫面播放速率。  <br/> |
|**OutboundVideoFrameRateAvg** <br/> |十進位 (9, 4)  <br/> | <br/> |已傳送的影片畫面播放速率。  <br/> |
|**VideoBitRateMax** <br/> |int  <br/> | <br/> |影片會話期間的最大視頻位元速率。  <br/> |
|**VideoFrameLossRate** <br/> |十進位 (9, 4)  <br/> | <br/> |遺失的視頻畫面總百分比。  <br/> |
|**VideoFEC** <br/> |稍微  <br/> | <br/> |無法使用。  <br/> |
|**VideoLocalFrameLossPercentageAvg** <br/> |十進位 (9, 4)  <br/> ||遺失的視頻畫面總百分比。  <br/> |
|**CIFQualityRatio** <br/> |Tinyint  <br/> ||常見交換格式 (CIF) 解析度的通話百分比。  <br/> |
|**VGAQualityRatio** <br/> |Tinyint  <br/> ||以 VGA 解析度表示的通話百分比。  <br/> |
|**HD720QualityRatio** <br/> |Tinyint  <br/> ||HD720 解析度的通話百分比。  <br/> |
|**NoneDropRatio** <br/> |Tinyint  <br/> ||沒有框架拖放的通話持續時間百分比。  <br/> |
|**BDropRatio** <br/> |Tinyint  <br/> ||B 框架下沉的通話持續時間百分比。  <br/> |
|**BPDropRatio** <br/> |Tinyint  <br/> ||含 BP 框架下沉之通話持續時間百分比。  <br/> |
|**BPSPDropRatio** <br/> |Tinyint  <br/> ||BPSP 框架下沉的通話持續時間百分比。  <br/> |
|**BPSPIDropRatio** <br/> |Tinyint  <br/> ||BPSPI 框架下沉的通話持續時間百分比。  <br/> |
|**進貨** <br/> |稍微  <br/> | <br/> |收到接收器端的資料流程資料。  <br/> |
|**發** <br/> |稍微  <br/> | <br/> |收到寄件者端的資料流程資料。  <br/> |
|**SenderIsCallerPAI** <br/> |稍微  <br/> | <br/> |1表示資料流程方向從來電者到被叫方。  <br/> 0表示資料流程方向是從被叫方到來電者。  <br/> |
|**LossCongestionPercent** <br/> |浮  <br/> ||表示通話處於遺失擁塞狀態的時間百分比。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**DelayCongestionPercent** <br/> |浮  <br/> ||指出因網路資料包損損, 導致堵塞的時間百分比。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**ContentionDetectedPercent** <br/> |浮  <br/> ||表示通話爭用網路資源的時間百分比。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||呼叫期間測量的最小頻寬估計量。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||呼叫期間測量的最大頻寬估計量。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||在通話期間測量之頻寬估計的標準差。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||通話期間平均測量的頻寬估計量。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**LowBandwidthForMultiview** <br/> |浮  <br/> ||端點判斷網路連接無法支援多種顯示的通話百分比。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**RelativeOneWayTotal** <br/> |浮  <br/> ||單向延遲的總金額。 相對單向延遲會測量用戶端與伺服器之間的延遲。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**RelativeOneWayAverage** <br/> |浮  <br/> ||單向延隔時間的平均量。 相對單向延遲會測量用戶端與伺服器之間的延遲。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**RelativeOneWayMax** <br/> |浮  <br/> ||單向延隔時間的最大值。 相對單向延遲會測量用戶端與伺服器之間的延遲。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||單向突發發生次數總計。 "Bursty" 傳輸是一種傳輸, 其中的資料流程過無法預料的猝發, 而不是穩定的資料流程。 此量度會測量用戶端與伺服器之間的資料流程。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**RelativeOneWayBurstDensity** <br/> |int  <br/> ||總計單向突發密度。 "Bursty" 傳輸是一種傳輸, 其中的資料流程過無法預料的猝發, 而不是穩定的資料流程。 此量度會測量用戶端與伺服器之間的資料流程。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**RelativeOneWayBurstDuration** <br/> |浮  <br/> ||總計單向突發持續時間。 "Bursty" 傳輸是一種傳輸, 其中的資料流程過無法預料的猝發, 而不是穩定的資料流程。 此量度會測量用戶端與伺服器之間的資料流程。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||總的單向間距發生情況。 "Bursty" 傳輸是一種傳輸, 其中的資料流程過無法預料的猝發, 而不是穩定的資料流程;[空隙] 表示這些猝發之間的延遲。 此量度會測量用戶端與伺服器之間的資料流程。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**RelativeOneWayGapDensity** <br/> |浮  <br/> ||總單向間距密度。 "Bursty" 傳輸是一種傳輸, 其中的資料流程過無法預料的猝發, 而不是穩定的資料流程;[空隙] 表示這些猝發之間的延遲。 此量度會測量用戶端與伺服器之間的資料流程。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**RelativeOneWayGapDuration** <br/> |浮  <br/> ||總共一個單向間距時間。 "Bursty" 傳輸是一種傳輸, 其中的資料流程過無法預料的猝發, 而不是穩定的資料流程;[空隙] 表示這些猝發之間的延遲。 此量度會測量用戶端與伺服器之間的資料流程。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**VideoPacketLossRate** <br/> |十進位 (9, 4)  <br/> ||視頻資料包遺失的頻率。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**VideoAllocateBWAvg** <br/> |int  <br/> ||為影片所分配的平均頻寬量。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**SendCodecTypes** <br/> |Smallint  <br/> |外  <br/> |寄件者所用的視頻編解碼器類型。 如需詳細資訊, 請參閱[CodecDescription 資料表](codecdescription.md)。 <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**SendResolutionWidth** <br/> |int  <br/> ||寄件者使用的解析度寬度。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**SendResolutionHeight** <br/> |int  <br/> ||寄件者使用的解析度高度。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**SendFrameRateAverage** <br/> |浮  <br/> ||寄件者使用的平均視頻畫面播放速率傳輸。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**SendBitRateMaximum** <br/> |int  <br/> ||該寄件者的最大位元速率。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**SendBitRateAverage** <br/> |int  <br/> ||寄件者的平均位元速率。  <br/> |
|**SendVideoStreamsMax** <br/> |int  <br/> ||寄件者使用的最大視頻串流數。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**RecvCodecTypes** <br/> |Smallint  <br/> |外  <br/> |接收器所使用的影片代碼。 如需詳細資訊, 請參閱[CodecDescription 資料表](codecdescription.md)。 <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**RecvResolutionWidth** <br/> |int  <br/> ||接收器所使用的解析度寬度。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**RecvResolutionHeight** <br/> |int  <br/> ||接收器所使用的解析度高度。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**RecvFrameRateAverage** <br/> |浮  <br/> ||接收器所使用的平均視頻畫面播放速率。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**RecvBitRateMaximum** <br/> |int  <br/> ||接收器的最大位元速率。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**RecvBitRateAverage** <br/> |int  <br/> ||接收器的平均位元速率。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**RecvVideoStreamsMax** <br/> |int  <br/> ||接收器的最大影片流量。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**RecvVideoStreamsMin** <br/> |int  <br/> ||接收器的最小視頻流量。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**RecvVideoStreamsMode** <br/> |int  <br/> ||接收器的影片模式 (例如圖庫或單一資料流程)。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**VideoPostFECPLR** <br/> |浮  <br/> ||已套用轉寄錯誤修正之後的資料包遺失率。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**DynamicCapabilityPercent** <br/> |浮  <br/> ||動態功能標誌作用中的時間百分比。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**ResolutionMin** <br/> |char (9)  <br/> ||通話期間測量的最小解析度。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**LowBitRateCallPercent** <br/> |浮  <br/> ||通話百分比低於低位率閾值 (70 kb/秒)。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**LowFrameRateCallPercent** <br/> |浮  <br/> ||通話百分比低於低畫面播放速率閾值 (7.5 幀/秒、入站)。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**LowResolutionCallPercent** <br/> |浮  <br/> ||最低解析度所發生通話的百分比。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**DurationSeconds** <br/> |浮  <br/> ||通話長度 (以秒為單位)。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**IsAggregatedData** <br/> |稍微  <br/> ||指示資料是否已從多個通話匯總。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
   

