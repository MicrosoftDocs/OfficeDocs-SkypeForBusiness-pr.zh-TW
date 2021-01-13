---
title: AppSharingStream 表格
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
ms.assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
description: AppSharingStream 表格包含用於應用程式共用之網路資料流程的經驗品質計量。 此表格已引進 Microsoft Lync Server 2013。
ms.openlocfilehash: 675b4ef689b62577cbee1cef93a28865ca09abfe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809673"
---
# <a name="appsharingstream-table"></a>AppSharingStream 表格
 
AppSharingStream 表格包含用於應用程式共用之網路資料流程的經驗品質計量。 此表格已引進 Microsoft Lync Server 2013。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |Datetime  <br/> |主要、外部  <br/> |會話開始的日期與時間。  <br/> |
|**SessionSeq** <br/> |int  <br/> |主要、外部  <br/> |用來區分在相同日期和同一時間開始之會話的連續識別碼。  <br/> |
|**MediaLineLabel** <br/> |Tinyint  <br/> |主要，外部  <br/> | 請參閱 [MediaLine Table](https://docs.microsoft.com/skypeforbusiness/schema-reference/quality-of-experience-qoe-database-schema/medialine-0)。 <br/> |
|**StreamID** <br/> |int  <br/> |主要  <br/> |應用程式共用資料流程的唯一識別碼。  <br/> |
|**JitterInterArrival** <br/> |int  <br/> ||在 RTP 封包抵達之間偵測到的平均抖動。  (抖動是指通話的 "shakiness" 量值。 ) 高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會產生失真或遺失的音訊。  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> ||在 RTP 封包抵達之間偵測到的最大抖動。  (抖動是指通話的 "shakiness" 量值。 ) 高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會產生失真或遺失的音訊。  <br/> |
|**往返** <br/> |int  <br/> ||Real-Time 傳輸通訊協定封包傳送到另一個端點後再回的平均 (量（毫秒）) 所需。 在200毫秒或更少的來回行程時間，會考慮可接受的品質。  <br/> 高來回行程值可能是由國際通話路由所造成;路由傳送錯誤;或重載的媒體伺服器。 較高的往返時間會導致使用雙向即時音訊交談的困難。  <br/> |
|**RoundTripMax** <br/> |int  <br/> ||Real-Time 傳輸通訊協定資料包移至另一個端點後，所需的 (（毫秒）) 數目上限。 在200毫秒或更少的來回行程時間，會考慮可接受的品質。  <br/> 高來回行程值可能是由國際通話路由所造成;路由傳送錯誤;或重載的媒體伺服器。 較高的往返時間會導致使用雙向即時音訊交談的困難。  <br/> |
|**PacketLossRate** <br/> |float  <br/> || (RTP) 封包遺失 Real-Time 傳輸通訊協定的平均速率。 當 RTP 封包（用於透過網際網路傳送音訊和影片的通訊協定）無法抵達目的地時，就會發生 (封包遺失。 ) 高遺失率通常是由擁塞所造成;缺乏頻寬;無線擁塞或干擾;或重載的媒體伺服器。 封包遺失通常會導致音訊失真或遺失。  <br/> |
|**PacketLossRateMax** <br/> |float  <br/> || (RTP) 封包遺失 Real-Time 傳輸通訊協定的最大速率。 當 RTP 封包（用於透過網際網路傳送音訊和影片的通訊協定）無法抵達目的地時，就會發生 (封包遺失。 ) 高遺失率通常是由擁塞所造成;缺乏頻寬;無線擁塞或干擾;或重載的媒體伺服器。 封包遺失通常會導致音訊失真或遺失。  <br/> |
|**PacketUtilization** <br/> |int  <br/> ||傳送的封包數目。  <br/> |
|**BandwidthEst** <br/> |int  <br/> ||在會話結束時可使用的預估單向頻寬。 每秒的位數報告。  <br/> |
|**AppSharingPayloadDescription** <br/> |int  <br/> ||應用程式共用負載的描述。  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||單向延遲的總金額。 相對單向延遲會測量用戶端與伺服器之間的延遲。  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||單向延遲的平均金額。 相對單向延遲會測量用戶端與伺服器之間的延遲。  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||單向延遲的最大值。 相對單向延遲會測量用戶端與伺服器之間的延遲。  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||總單向突發的發生次數。 "爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。 此度量單位會測量用戶端與伺服器之間的資料流程。  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||總單向爆炸流量密度。 "爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。 此度量單位會測量用戶端與伺服器之間的資料流程。  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||總單向突發持續時間。 "爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。 此度量單位會測量用戶端與伺服器之間的資料流程。  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||對單向間隔的總發生次數。 "爆發" 傳輸是一種傳輸，其中資料流程的資料流程與穩定的資料流程相反，其資料流程會以無法預測的方式傳輸;間隙表示這些猝發間的延遲。 此度量單位會測量用戶端與伺服器之間的資料流程。  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||總單向間距密度。 "爆發" 傳輸是一種傳輸，其中資料流程的資料流程與穩定的資料流程相反，其資料流程會以無法預測的方式傳輸;間隙表示這些猝發間的延遲。 此度量單位會測量用戶端與伺服器之間的資料流程。  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||總的單向間距持續時間。 "爆發" 傳輸是一種傳輸，其中資料流程的資料流程與穩定的資料流程相反，其資料流程會以無法預測的方式傳輸;間隙表示這些猝發間的延遲。 此度量單位會測量用戶端與伺服器之間的資料流程。  <br/> |
|**ApplicationSharingType** <br/> |varChar (256)   <br/> || (共用或檢視器的應用程式角色) 和內容類型。  <br/> |
|**RDPTileProcessingLatencyTotal** <br/> |float  <br/> ||遠端桌面通訊協定 (RDP) 麻將牌的總處理時間。 較高的總數相當於觀賞體驗中較長的延遲。  <br/> |
|**RDPTileProcessingLatencyAverage** <br/> |float  <br/> ||遠端桌面通訊協定 (RDP) 磚的平均處理時間。 較高的總數相當於觀賞體驗中較長的延遲。  <br/> |
|**RDPTileProcessingLatencyMax** <br/> |float  <br/> ||遠端桌面通訊協定 (RDP) 磚的處理時間上限。 較高的總數相當於觀賞體驗中較長的延遲。  <br/> |
|**RDPTileProcessingLatencyBurstOccurrences** <br/> |int  <br/> ||遠端桌面通訊協定 (RDP) 的處理時間中的爆發發生次數。 "爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。  <br/> |
|**RDPTileProcessingLatencyBurstDensity** <br/> |float  <br/> ||遠端桌面通訊協定 (RDP) 磚的處理時間中的暴沖密度。 "爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。  <br/> |
|**RDPTileProcessingLatencyBurstDuration** <br/> |float  <br/> ||遠端桌面通訊協定 (RDP 的處理時間中的暴沖持續時間) 磚。 "爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。  <br/> |
|**RDPTileProcessingLatencyGapOccurrences** <br/> |int  <br/> ||遠端桌面通訊協定的處理時間中的缺口發生次數 (RDP) 麻將牌。  <br/> |
|**RDPTileProcessingLatencyGapDensity** <br/> |float  <br/> ||遠端桌面通訊協定 (RDP) 圖塊的處理時間中的缺口密度。 低間距密度相當於更好的觀賞體驗。  <br/> |
|**RDPTileProcessingLatencyGapDuration** <br/> |float  <br/> ||遠端桌面通訊協定 (RDP 的處理時間中的缺口持續時間) 麻將牌。 短的缺口持續時間等於更好的觀賞體驗。  <br/> |
|**CaptureTileRateTotal** <br/> |float  <br/> ||每秒 (每秒磚) 中的捕獲磚總速率。  <br/> |
|**CaptureTileRateAverage** <br/> |float  <br/> ||每秒 (每秒磚的已捕獲磚的平均速率) 。  <br/> |
|**CaptureTileRateMax** <br/> |float  <br/> ||每秒 (每秒的磚) 中所捕獲的麻將牌的最大速率。  <br/> |
|**CaptureTileRateBurstOccurrences** <br/> |在 t  <br/> ||以每秒 (每秒磚數為單位所捕獲的麻將牌的速率) 中的爆發次數。  <br/> |
|**CaptureTileRateBurstDensity** <br/> |float  <br/> ||) 中每秒 (以每秒所捕獲的麻將牌速率為單位的流量密度。  <br/> |
|**CaptureTileRateBurstDuration** <br/> |float  <br/> ||以每秒磚數 (為單位的每秒) 中捕獲的磚的流量。  <br/> |
|**CaptureTileRateGapOccurrences** <br/> |int  <br/> ||以每秒貼圖)  (所捕獲的麻將牌速率為單位的缺口發生次數。  <br/> |
|**CaptureTileRateGapDensity** <br/> |float  <br/> ||以每秒貼圖)  (所捕獲的麻將牌速率為單位的間距密度。  <br/> |
|**CaptureTileRateGapDuration** <br/> |float  <br/> ||以每秒貼圖)  (所捕獲的麻將牌速率為單位的缺口持續時間。  <br/> |
|**SpoiledTilePercentTotal** <br/> |float  <br/> ||未到達檢視器而被捨棄並以全新內容覆寫之內容的總百分比。  <br/> |
|**SpoiledTilePercentAverage** <br/> |float  <br/> ||未到達檢視器而被捨棄並以全新內容覆寫之內容的平均百分比。  <br/> |
|**SpoiledTilePercentMax** <br/> |float  <br/> ||未到達檢視器而被捨棄並以全新內容覆寫之內容的最大百分比。  <br/> |
|**SpoiledTilePercentBurstOccurrences** <br/> |int  <br/> ||未到達檢視器而被捨棄並以全新內容覆寫之內容的爆發發生次數。  <br/> |
|**SpoiledTilePercentBurstDensity** <br/> |float  <br/> ||未到達檢視器之內容的暴沖密度，但已被捨棄並以全新內容覆寫。  <br/> |
|**SpoiledTilePercentBurstDuration** <br/> |float  <br/> ||未到達檢視器而被捨棄並以全新內容覆寫之內容的暴沖持續時間。  <br/> |
|**SpoiledTilePercentGapOccurrences** <br/> |int  <br/> ||未到達檢視器而被捨棄並以全新內容覆寫之內容的缺口發生次數。  <br/> |
|**SpoiledTilePercentGapDensity** <br/> |float  <br/> ||未到達檢視器之內容的缺口密度，但已被捨棄並以全新內容覆寫。  <br/> |
|**SpoiledTilePercentGapDuration** <br/> |float  <br/> ||未到達檢視器而被捨棄並以全新內容覆寫之內容的缺口持續時間。  <br/> |
|**ScrapingFrameRateTotal** <br/> |float  <br/> ||從圖形來源消去的框架總數目。  <br/> |
|**ScrapingFrameRateAverage** <br/> |float  <br/> ||從圖形來源消去的平均框架數目。  <br/> |
|**ScrapingFrameRateMax** <br/> |float  <br/> ||從圖形來源消去的最大相框數目。  <br/> |
|**ScrapingFrameRateBurstOccurrences** <br/> |int  <br/> ||從圖形來源消去的幀中的出現爆發。  <br/> |
|**ScrapingFrameRateBurstDensity** <br/> |float  <br/> ||從圖形來源消去之框架中的流量密度。  <br/> |
|**ScrapingFrameRateBurstDuration** <br/> |float  <br/> ||從圖形來源消去之框架中的暴沖持續時間。  <br/> |
|**ScrapingFrameRateGapOccurrences** <br/> |int  <br/> ||從圖形來源消去之框架中的缺口發生次數。  <br/> |
|**ScrapingFrameRateGapDensity** <br/> |float  <br/> ||從圖形來源消去之框架中的間距密度。  <br/> |
|**ScrapingFrameRateGapDuration** <br/> |float  <br/> ||從圖形來源消去之框架中的空隙 duration。  <br/> |
|**IncomingTileRateTotal** <br/> |float  <br/> ||檢視器接收到的內送框架速率總數。  <br/> |
|**IncomingTileRateAverage** <br/> |float  <br/> ||檢視器接收的平均內送框架速率。  <br/> |
|**IncomingTileRateMax** <br/> |float  <br/> ||檢視器所收到的傳入磚率上限。  <br/> |
|**IncomingTileRateBurstOccurrences** <br/> |int  <br/> ||由檢視器接收的傳入磚速率中的突發流量。  <br/> |
|**IncomingTileRateBurstDensity** <br/> |float  <br/> ||由檢視器接收的傳入磚速率中的暴沖密度。  <br/> |
|**IncomingTileRateBurstDuration** <br/> |float  <br/> ||由檢視器接收的傳入磚速率中的暴沖持續時間。  <br/> |
|**IncomingTileRateGapOccurrences** <br/> |int  <br/> ||由 viewer 接收的內送磚速率中的間距發生次數。  <br/> |
|**IncomingTileRateGapDensity** <br/> |float  <br/> ||由 viewer 接收的內送磚速率中的間距密度。  <br/> |
|**IncomingTileRateGapDuration** <br/> |float  <br/> ||依檢視器接收的內送磚速率中的缺口持續時間。  <br/> |
|**IncomingFrameRateTotal** <br/> |float  <br/> ||檢視器接收到的內送框架速率總數。  <br/> |
|**IncomingFrameRateAverage** <br/> |float  <br/> ||檢視器接收的平均內送框架速率。  <br/> |
|**IncomingFrameRateMax** <br/> |float  <br/> ||檢視器接收到的內送框架速率上限。  <br/> |
|**IncomingFrameRateBurstOccurrences** <br/> |int  <br/> ||檢視器接收的內送畫面播放速率中的突發流量發生方式。  <br/> |
|**IncomingFrameRateBurstDensity** <br/> |float  <br/> ||由檢視器接收的內送畫面播放速率中的暴沖密度。  <br/> |
|**IncomingFrameRateBurstDuration** <br/> |float  <br/> ||以瀏覽器接收的傳入相框速率中的暴沖持續時間。  <br/> |
|**IncomingFrameRateGapOccurrences** <br/> |int  <br/> ||檢視器接收的內送畫面播放速率中的間距發生次數。  <br/> |
|**IncomingFrameRateGapDensity** <br/> |float  <br/> ||檢視器接收的內送框架速率中的間距密度。  <br/> |
|**IncomingFrameRateDuration** <br/> |float  <br/> ||依檢視器接收的內送框架速率中的間距持續時間。  <br/> |
|**OutgoingTileRateTotal** <br/> |float  <br/> ||寄件者的傳出磚總速率。  <br/> |
|**OutgoingTileRateAverage** <br/> |float  <br/> ||寄件者的平均傳出磚速率。  <br/> |
|**OutgoingTileRateMax** <br/> |float  <br/> ||寄件者的傳出磚流量上限。  <br/> |
|**OutgoingTileRateBurstOccurrences** <br/> |int  <br/> ||以寄件者的傳出磚速率表示的突發流量發生次數。  <br/> |
|**OutgoingTileRateBurstDensity** <br/> |float  <br/> ||以傳送者之傳出磚速率表示的暴沖密度。  <br/> |
|**OutgoingTileRateBurstDuration** <br/> |float  <br/> ||以寄件者的傳出磚速率表示的暴沖持續時間。  <br/> |
|**OutgoingTileRateGapOccurrences** <br/> |int  <br/> ||以寄件者的傳出磚速率表示的缺口發生次數。  <br/> |
|**OutgoingTileRateGapDensity** <br/> |float  <br/> ||以寄件者的傳出磚速率表示的缺口密度。  <br/> |
|**OutgoingTileRateGapDuration** <br/> |float  <br/> ||以寄件者的傳出磚速率表示的缺口持續時間。  <br/> |
|**OutgoingFrameRateTotal** <br/> |float  <br/> ||寄件者的傳出畫面速率總數。  <br/> |
|**OutgoingFrameRateAverage** <br/> |float  <br/> ||寄件者的平均傳出畫面速率。  <br/> |
|**OutgoingFrameRateMax** <br/> |float  <br/> ||寄件者的最大傳出畫面速率。  <br/> |
|**OutgoingFrameRateBurstOccurrences** <br/> |int  <br/> ||寄件者的傳出畫面速率中的暴沖出現次數。  <br/> |
|**OutgoingFrameRateBurstDensity** <br/> |float  <br/> ||寄件者的傳出畫面速率中的暴沖密度。  <br/> |
|**OutgoingFrameRateBurstDuration** <br/> |float  <br/> ||以寄件者的傳出畫面速率表示的暴沖持續時間。  <br/> |
|**OutgoingFrameRateGapOccurrences** <br/> |int  <br/> ||以寄件者的傳出畫面速率表示的缺口發生次數。  <br/> |
|**OutgoingFrameRateGapDensity** <br/> |float  <br/> ||寄件者的傳出畫面速率中的間距密度。  <br/> |
|**OutgoingFrameRateGapDuration** <br/> |float  <br/> ||以寄件者的傳出畫面速率表示的缺口持續時間。  <br/> |
|**AverageRectangleHeight** <br/> |int  <br/> ||影片的平均解析度高度（以圖元為單位）。  <br/> |
|**AverageRectangleWidth** <br/> |int  <br/> ||影片的平均解析度寬度（以圖元為單位）。  <br/> |
|**入境** <br/> |位  <br/> ||輸入傳輸的平均每秒幀 () 的平均框架速率。  <br/> |
|**出境** <br/> |位  <br/> ||輸出傳輸) 每秒幀中 (的平均框架速率。  <br/> |
|**SenderIsCallerPAI** <br/> |位  <br/> ||1表示資料流程的方向從來電者到被叫方。  <br/> 0表示資料流程方向從被叫方傳送給來電者。  <br/> |
   

