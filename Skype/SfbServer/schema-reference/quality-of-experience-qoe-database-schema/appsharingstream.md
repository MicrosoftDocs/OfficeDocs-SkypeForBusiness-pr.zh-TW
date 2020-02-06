---
title: AppSharingStream 資料表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
description: AppSharingStream 表格包含用於應用程式共用之網路資料流程的經驗品質度量單位。 此表格是在 Microsoft Lync Server 2013 中推出。
ms.openlocfilehash: 1ebcfe16fe5863bcb3046e88ba5cdc2079f22a9c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41811101"
---
# <a name="appsharingstream-table"></a>AppSharingStream 資料表
 
AppSharingStream 表格包含用於應用程式共用之網路資料流程的經驗品質度量單位。 此表格是在 Microsoft Lync Server 2013 中推出。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |dateTime  <br/> |主要、外部  <br/> |會話開始的日期和時間。  <br/> |
|**SessionSeq** <br/> |int  <br/> |主要、外部  <br/> |使用順序識別碼來區分在相同日期和同一時間啟動的會話。  <br/> |
|**MediaLineLabel** <br/> |Tinyint  <br/> |主要、外部  <br/> | 請參閱[MediaLine 表格](https://docs.microsoft.com/skypeforbusiness/schema-reference/quality-of-experience-qoe-database-schema/medialine-0)。 <br/> |
|**StreamID** <br/> |int  <br/> |首選  <br/> |應用程式共用資料流程的唯一識別碼。  <br/> |
|**JitterInterArrival** <br/> |int  <br/> ||在 RTP 資料包抵達之間檢測到的平均抖動。 （抖動是通話 "shakiness" 的測量值）。高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會造成失真或遺失音訊。  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> ||在 RTP 資料包抵達之間檢測到最大抖動。 （抖動是通話 "shakiness" 的測量值）。高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會造成失真或遺失音訊。  <br/> |
|**環路** <br/> |int  <br/> ||即時傳輸通訊協定資料包移動到另一個端點之後，再返回的平均（以毫秒為單位）。 200毫秒或較低的往返行程時間會視為可接受的品質。  <br/> 國際呼叫路由可能會造成高往返值。路由無法正確配置;或超載的媒體伺服器。 較高的往返行程時間會造成使用雙向即時音訊交談的困難。  <br/> |
|**RoundTripMax** <br/> |int  <br/> ||即時傳輸通訊協定資料包要傳送到另一個端點的最大值（以毫秒為單位），然後返回。 200毫秒或較低的往返行程時間會視為可接受的品質。  <br/> 國際呼叫路由可能會造成高往返值。路由無法正確配置;或超載的媒體伺服器。 較高的往返行程時間會造成使用雙向即時音訊交談的困難。  <br/> |
|**PacketLossRate** <br/> |浮  <br/> ||即時傳輸通訊協定（RTP）資料包遺失的平均速率。 （當 RTP 資料包（這是一種用來透過網際網路傳送音訊和影片的通訊協定）無法送達目的地時，會發生資料包遺失。高遺失率通常是由擁塞所造成;缺乏頻寬;無線擁塞或干擾;或超載的媒體伺服器。 [資料包遺失] 通常會導致聲音失真或遺失。  <br/> |
|**PacketLossRateMax** <br/> |浮  <br/> ||即時傳輸通訊協定（RTP）資料包遺失率的最大值。 （當 RTP 資料包（這是一種用來透過網際網路傳送音訊和影片的通訊協定）無法送達目的地時，會發生資料包遺失。高遺失率通常是由擁塞所造成;缺乏頻寬;無線擁塞或干擾;或超載的媒體伺服器。 [資料包遺失] 通常會導致聲音失真或遺失。  <br/> |
|**PacketUtilization** <br/> |int  <br/> ||已傳送的資料包數目。  <br/> |
|**BandwidthEst** <br/> |int  <br/> ||會話結束時可使用的估計單向頻寬。 以每秒位數報告。  <br/> |
|**AppSharingPayloadDescription** <br/> |int  <br/> ||應用程式共用負載的描述。  <br/> |
|**RelativeOneWayTotal** <br/> |浮  <br/> ||單向延遲的總金額。 相對單向延遲會測量用戶端與伺服器之間的延遲。  <br/> |
|**RelativeOneWayAverage** <br/> |浮  <br/> ||單向延隔時間的平均量。 相對單向延遲會測量用戶端與伺服器之間的延遲。  <br/> |
|**RelativeOneWayMax** <br/> |浮  <br/> ||單向延隔時間的最大值。 相對單向延遲會測量用戶端與伺服器之間的延遲。  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||單向突發發生次數總計。 "Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。 此量度會測量用戶端與伺服器之間的資料流程。  <br/> |
|**RelativeOneWayBurstDensity** <br/> |浮  <br/> ||總計單向突發密度。 "Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。 此量度會測量用戶端與伺服器之間的資料流程。  <br/> |
|**RelativeOneWayBurstDuration** <br/> |浮  <br/> ||總計單向突發持續時間。 "Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。 此量度會測量用戶端與伺服器之間的資料流程。  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||總的單向間距發生情況。 "Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程;[空隙] 表示這些猝發之間的延遲。 此量度會測量用戶端與伺服器之間的資料流程。  <br/> |
|**RelativeOneWayGapDensity** <br/> |浮  <br/> ||總單向間距密度。 "Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程;[空隙] 表示這些猝發之間的延遲。 此量度會測量用戶端與伺服器之間的資料流程。  <br/> |
|**RelativeOneWayGapDuration** <br/> |浮  <br/> ||總共一個單向間距時間。 "Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程;[空隙] 表示這些猝發之間的延遲。 此量度會測量用戶端與伺服器之間的資料流程。  <br/> |
|**ApplicationSharingType** <br/> |varChar （256）  <br/> ||應用程式角色（共用或檢視器）與內容類型。  <br/> |
|**RDPTileProcessingLatencyTotal** <br/> |浮  <br/> ||遠端桌面通訊協定（RDP）磚的總處理時間。 較高的總計相當於觀賞體驗中較長的延遲。  <br/> |
|**RDPTileProcessingLatencyAverage** <br/> |浮  <br/> ||遠端桌面通訊協定（RDP）磚的平均處理時間。 較高的總計相當於觀賞體驗中較長的延遲。  <br/> |
|**RDPTileProcessingLatencyMax** <br/> |浮  <br/> ||遠端桌面通訊協定（RDP）磚的最大處理時間。 較高的總計相當於觀賞體驗中較長的延遲。  <br/> |
|**RDPTileProcessingLatencyBurstOccurrences** <br/> |int  <br/> ||遠端桌面通訊協定（RDP）磚處理時間的突發事件發生方式。 "Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。  <br/> |
|**RDPTileProcessingLatencyBurstDensity** <br/> |浮  <br/> ||遠端桌面通訊協定（RDP）磚處理時間的暴沖密度。 "Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。  <br/> |
|**RDPTileProcessingLatencyBurstDuration** <br/> |浮  <br/> ||遠端桌面通訊協定（RDP）磚處理時間中的爆發時間。 "Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。  <br/> |
|**RDPTileProcessingLatencyGapOccurrences** <br/> |int  <br/> ||遠端桌面通訊協定（RDP）磚處理時間中的差距出現次數。  <br/> |
|**RDPTileProcessingLatencyGapDensity** <br/> |浮  <br/> ||遠端桌面通訊協定（RDP）磚處理時間的差距密度。 低差距密度可讓您獲得更佳的觀賞體驗。  <br/> |
|**RDPTileProcessingLatencyGapDuration** <br/> |浮  <br/> ||遠端桌面通訊協定（RDP）磚處理時間中的差距持續時間。 短差距期間會等同于更佳的觀賞體驗。  <br/> |
|**CaptureTileRateTotal** <br/> |浮  <br/> ||捕獲磚的總速率（每秒磚）。  <br/> |
|**CaptureTileRateAverage** <br/> |浮  <br/> ||捕獲磚的平均速率（每秒磚）。  <br/> |
|**CaptureTileRateMax** <br/> |浮  <br/> ||捕獲磚的最大速率（每秒磚）。  <br/> |
|**CaptureTileRateBurstOccurrences** <br/> |在 t  <br/> ||在捕獲磚（每秒磚數）中，突發發生的頻率。  <br/> |
|**CaptureTileRateBurstDensity** <br/> |浮  <br/> ||捕獲磚（每秒磚）的流量峰值密度。  <br/> |
|**CaptureTileRateBurstDuration** <br/> |浮  <br/> ||以捕獲磚（每秒磚）為單位的爆發時段。  <br/> |
|**CaptureTileRateGapOccurrences** <br/> |int  <br/> ||間距出現在捕獲磚的速率中（每秒磚）。  <br/> |
|**CaptureTileRateGapDensity** <br/> |浮  <br/> ||已捕獲磚（每秒磚）中的間距密度。  <br/> |
|**CaptureTileRateGapDuration** <br/> |浮  <br/> ||所捕獲磚（每秒磚）中的差距間隔時間。  <br/> |
|**SpoiledTilePercentTotal** <br/> |浮  <br/> ||未到達檢視器的內容總百分比，但已被新內容捨棄並覆寫。  <br/> |
|**SpoiledTilePercentAverage** <br/> |浮  <br/> ||未到達檢視器的內容平均百分比，而是由新內容捨棄並覆寫。  <br/> |
|**SpoiledTilePercentMax** <br/> |浮  <br/> ||未到達檢視器的內容的最大百分比，而是由新內容捨棄並覆寫。  <br/> |
|**SpoiledTilePercentBurstOccurrences** <br/> |int  <br/> ||無法到達檢視器的內容突發事件，但已被新內容捨棄並覆寫。  <br/> |
|**SpoiledTilePercentBurstDensity** <br/> |浮  <br/> ||未到達檢視器之內容的突發密度，但已被新內容捨棄並覆寫。  <br/> |
|**SpoiledTilePercentBurstDuration** <br/> |浮  <br/> ||無法到達檢視器之內容的爆發持續時間，但已被新內容捨棄並覆寫。  <br/> |
|**SpoiledTilePercentGapOccurrences** <br/> |int  <br/> ||未到達檢視器之內容的差距出現次數，但已被新內容捨棄並覆寫。  <br/> |
|**SpoiledTilePercentGapDensity** <br/> |浮  <br/> ||未到達檢視器之內容的差距密度，但已被新內容捨棄並覆寫。  <br/> |
|**SpoiledTilePercentGapDuration** <br/> |浮  <br/> ||未到達檢視器之內容的差距持續時間，但已被新內容捨棄並覆寫。  <br/> |
|**ScrapingFrameRateTotal** <br/> |浮  <br/> ||圖形來源的畫面總 scraped 數。  <br/> |
|**ScrapingFrameRateAverage** <br/> |浮  <br/> ||圖形來源的平均幀 scraped 數。  <br/> |
|**ScrapingFrameRateMax** <br/> |浮  <br/> ||圖形來源中的最大幀 scraped 數。  <br/> |
|**ScrapingFrameRateBurstOccurrences** <br/> |int  <br/> ||來自圖形來源的 [幀 scraped] 中的 [突發] 出現次數。  <br/> |
|**ScrapingFrameRateBurstDensity** <br/> |浮  <br/> ||圖形來源的 [幀 scraped] 中的 [暴沖密度]。  <br/> |
|**ScrapingFrameRateBurstDuration** <br/> |浮  <br/> ||圖形來源的 [幀 scraped] 中的 [突發期間]。  <br/> |
|**ScrapingFrameRateGapOccurrences** <br/> |int  <br/> ||圖形來源的 [幀 scraped] 中的空隙出現次數。  <br/> |
|**ScrapingFrameRateGapDensity** <br/> |浮  <br/> ||圖形來源的 [框架 scraped] 中的間距密度。  <br/> |
|**ScrapingFrameRateGapDuration** <br/> |浮  <br/> ||圖形來源的 [框架 scraped] 中的 [空隙] 工期。  <br/> |
|**IncomingTileRateTotal** <br/> |浮  <br/> ||檢視器接收的傳入畫面播放速率總計。  <br/> |
|**IncomingTileRateAverage** <br/> |浮  <br/> ||檢視器接收到的平均接收畫面播放速率。  <br/> |
|**IncomingTileRateMax** <br/> |浮  <br/> ||檢視器接收到的傳入磚速率上限。  <br/> |
|**IncomingTileRateBurstOccurrences** <br/> |int  <br/> ||檢視器接收到的傳入磚速率中的爆發次數。  <br/> |
|**IncomingTileRateBurstDensity** <br/> |浮  <br/> ||檢視器接收的傳入磚速率中的高載密度。  <br/> |
|**IncomingTileRateBurstDuration** <br/> |浮  <br/> ||檢視器接收的傳入磚速率中的爆發持續時間。  <br/> |
|**IncomingTileRateGapOccurrences** <br/> |int  <br/> ||檢視器接收的傳入磚速率中的間距值。  <br/> |
|**IncomingTileRateGapDensity** <br/> |浮  <br/> ||檢視器接收的傳入磚速率中的差距密度。  <br/> |
|**IncomingTileRateGapDuration** <br/> |浮  <br/> ||檢視器接收到的內送磚速率中的差距持續時間。  <br/> |
|**IncomingFrameRateTotal** <br/> |浮  <br/> ||檢視器接收的傳入畫面播放速率總計。  <br/> |
|**IncomingFrameRateAverage** <br/> |浮  <br/> ||檢視器接收到的平均接收畫面播放速率。  <br/> |
|**IncomingFrameRateMax** <br/> |浮  <br/> ||檢視器接收到的最大傳入畫面播放速率。  <br/> |
|**IncomingFrameRateBurstOccurrences** <br/> |int  <br/> ||檢視器接收到的傳入畫面播放速率中的爆發次數。  <br/> |
|**IncomingFrameRateBurstDensity** <br/> |浮  <br/> ||檢視器接收到的傳入畫面播放速率中的暴沖密度。  <br/> |
|**IncomingFrameRateBurstDuration** <br/> |浮  <br/> ||檢視器接收到的傳入畫面播放速率中的爆發持續時間。  <br/> |
|**IncomingFrameRateGapOccurrences** <br/> |int  <br/> ||檢視器接收到的內送畫面播放速率中出現的間距。  <br/> |
|**IncomingFrameRateGapDensity** <br/> |浮  <br/> ||檢視器接收的傳入畫面播放速率中的差距密度。  <br/> |
|**IncomingFrameRateDuration** <br/> |浮  <br/> ||檢視器接收的傳入畫面播放速率中的差距持續時間。  <br/> |
|**OutgoingTileRateTotal** <br/> |浮  <br/> ||寄件者的外寄磚率總計。  <br/> |
|**OutgoingTileRateAverage** <br/> |浮  <br/> ||寄件者的平均外寄磚速率。  <br/> |
|**OutgoingTileRateMax** <br/> |浮  <br/> ||寄件者的最大外寄磚速率。  <br/> |
|**OutgoingTileRateBurstOccurrences** <br/> |int  <br/> ||寄件者的傳出磚速率中的突發事件。  <br/> |
|**OutgoingTileRateBurstDensity** <br/> |浮  <br/> ||寄件者的傳出磚速率的高載密度。  <br/> |
|**OutgoingTileRateBurstDuration** <br/> |浮  <br/> ||寄件者的傳出磚頻率內的爆發持續時間。  <br/> |
|**OutgoingTileRateGapOccurrences** <br/> |int  <br/> ||寄件者的外寄磚頻率中出現空隙。  <br/> |
|**OutgoingTileRateGapDensity** <br/> |浮  <br/> ||寄件者的外寄磚工資率的差距密度。  <br/> |
|**OutgoingTileRateGapDuration** <br/> |浮  <br/> ||寄件者的外寄磚工資率的差距持續時間。  <br/> |
|**OutgoingFrameRateTotal** <br/> |浮  <br/> ||寄件者的外寄畫面播放速率總計。  <br/> |
|**OutgoingFrameRateAverage** <br/> |浮  <br/> ||寄件者的平均傳出畫面播放速率。  <br/> |
|**OutgoingFrameRateMax** <br/> |浮  <br/> ||寄件者的最大外寄畫面播放速率。  <br/> |
|**OutgoingFrameRateBurstOccurrences** <br/> |int  <br/> ||寄件者在外寄畫面播放速率中的突發事件。  <br/> |
|**OutgoingFrameRateBurstDensity** <br/> |浮  <br/> ||寄件者的外寄畫面播放速率中的暴沖密度。  <br/> |
|**OutgoingFrameRateBurstDuration** <br/> |浮  <br/> ||寄件者的外寄畫面播放速率中的爆發持續時間。  <br/> |
|**OutgoingFrameRateGapOccurrences** <br/> |int  <br/> ||寄件者的外寄畫面播放速率中出現空隙。  <br/> |
|**OutgoingFrameRateGapDensity** <br/> |浮  <br/> ||寄件者的外寄畫面播放速率中的差距密度。  <br/> |
|**OutgoingFrameRateGapDuration** <br/> |浮  <br/> ||寄件者的外寄畫面播放速率中的差距持續時間。  <br/> |
|**AverageRectangleHeight** <br/> |int  <br/> ||平均視頻解析度高度（以圖元為單位）。  <br/> |
|**AverageRectangleWidth** <br/> |int  <br/> ||以圖元為單位的平均視頻解析度寬度。  <br/> |
|**進貨** <br/> |稍微  <br/> ||入站傳輸的平均畫面播放速率（在每秒的幀數）。  <br/> |
|**發** <br/> |稍微  <br/> ||輸出傳送的平均畫面播放速率（在每秒的幀數）。  <br/> |
|**SenderIsCallerPAI** <br/> |稍微  <br/> ||1表示資料流程方向從來電者到被叫方。  <br/> 0表示資料流程方向是從被叫方到來電者。  <br/> |
   

