---
title: AudioStream 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
description: 每個記錄代表一個音訊資料流程。 一個音訊媒體行通常包含兩個音訊資料流程。
ms.openlocfilehash: 265125202de25da4c6e653ecd53bd465f9a5472b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810431"
---
# <a name="audiostream-table"></a>AudioStream 表格
 
每個記錄代表一個音訊資料流程。 一個音訊媒體行通常包含兩個音訊資料流程。
  
|左欄|資料類型|索引鍵/索引|詳細資料|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |首選  <br/> |從[MediaLine 資料表](medialine-0.md)中參照。  <br/> |
|**SessionSeq** <br/> |int  <br/> |首選  <br/> |從[MediaLine 資料表](medialine-0.md)中參照。  <br/> |
|**MediaLineLabel** <br/> |Tinyint  <br/> |首選  <br/> |從[MediaLine 資料表](medialine-0.md)中參照。  <br/> |
|**StreamID** <br/> |int  <br/> |首選  <br/> |媒體線中的唯一識別碼。  <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |從即時控制通訊協定（RTCP）統計資料的平均網路抖動。  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |通話期間網路抖動的最大值。  <br/> |
|**PacketLossRate** <br/> |十進位（5，4）  <br/> | <br/> |通話期間的平均資料包遺失率。  <br/> |
|**PacketLossRateMax** <br/> |十進位（5，4）  <br/> | <br/> |通話期間觀察到的最大資料包遺失。  <br/> |
|**BurstDensity** <br/> |十進位（9，4）  <br/> | <br/> |通話期間猝發損失期間的平均資料包遺失密度。  <br/> |
|**BurstDuration** <br/> |int  <br/> | <br/> |通話期間猝發損失期間的平均資料包遺失時間。  <br/> |
|**BurstGapDensity** <br/> |十進位（9，4）  <br/> | <br/> |在突發資料包遺失之間的間隔期間的平均資料包遺失密度。  <br/> |
|**BurstGapDuration** <br/> |int  <br/> | <br/> |猝發資料包遺失之間的平均持續時間。  <br/> |
|**PacketUtilization** <br/> |Int  <br/> | <br/> |音訊資料流程的 [資料包計數]。  <br/> |
|**BandwidthEst** <br/> |Int  <br/> | <br/> |音訊資料流程的頻寬估計值。  <br/> |
|**DegradationAvg** <br/> |decimal （3，2）  <br/> | <br/> |整個通話的網路 MOS 下降。 範圍是0.0 到5.0。 這個指標顯示由於抖動和資料包遺失而減少網路 MOS 的數量。 針對可接受的品質，它應該小於0.5。  <br/> |
|**DegradationMax** <br/> |decimal （3，2）  <br/> | <br/> |通話期間網路 MOS 的最大下降。  <br/> |
|**DegradationJitterAvg** <br/> |decimal （3，2）  <br/> | <br/> |抖動造成的網路 MOS 下降。  <br/> |
|**DegradationPacketLossAvg** <br/> |decimal （3，2）  <br/> | <br/> |因數據包遺失而造成的網路 MOS 下降。  <br/> |
|**AudioPayloadDescription** <br/> |int  <br/> |外  <br/> |用於通話的音訊編解碼器，從 PayloadDescription 資料表中引用。  <br/> |
|**AudioSampleRate** <br/> |int  <br/> | <br/> |音訊資料流程的採樣速率。  <br/> |
|**環路** <br/> |int  <br/> | <br/> |從 RTCP 統計資料中往返的時間。 針對可接受的品質，這應該小於100ms。  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |音訊資料流程的最大往返行程時間。  <br/> |
|**OverallAvgNetworkMOS** <br/> |decimal （3，2）  <br/> | <br/> |通話的平均 wideband 網路 MOS。 這個指標取決於所使用的資料包遺失、抖動和編解碼器。 範圍是 [1.0 到 5.0]。  <br/> |
|**OverallMinNetworkMOS** <br/> |decimal （3，2）  <br/> | <br/> |通話的最小 wideband 網路 MOS。  <br/> |
|**SendListenMOS** <br/> |decimal （3，2）  <br/> | <br/> |已傳送音訊的平均預計 wideband 偵聽 MOS 分數，包括語音等級、雜訊等級及捕捉裝置特徵。  <br/> |
|**SendListenMOSMin** <br/> |decimal （3，2）  <br/> | <br/> |通話的最小 SendListenMOS。  <br/> |
|**RecvListenMOS** <br/> |decimal （3，2）  <br/> | <br/> |從網路接收的音訊的平均預計 wideband，包括語音電平、雜訊層級、編解碼器、網路條件及捕獲裝置功能。  <br/> |
|**RecvListenMOSMin** <br/> |decimal （3，2）  <br/> | <br/> |通話的最小 RecvListenMOS。  <br/> |
|**AudioFECUsed** <br/> |稍微  <br/> ||指示是否已使用音訊 FEC 進行通話的標記。  <br/> |
|**RatioConcealedSamplesAvg** <br/> |decimal （5，2）  <br/> ||從音訊康復產生的隱藏樣本到典型範例的平均比率。  <br/> |
|**RatioStretchedSamplesAvg** <br/> |decimal （5，2）  <br/> ||從音訊康復產生的延伸樣本數與典型範例的平均比率。  <br/> |
|**RatioCompressedSamplesAvg** <br/> |decimal （5，2）  <br/> ||從音訊修復到典型範例所產生之壓縮樣本的平均比率。  <br/> |
|**進貨** <br/> |稍微  <br/> | <br/> |收到接收器端的資料流程資料。  <br/> |
|**發** <br/> |稍微  <br/> | <br/> |收到寄件者端的資料流程資料。  <br/> |
|**SenderIsCallerPAI** <br/> |稍微  <br/> | <br/> |1表示資料流程方向從來電者到被叫方。  <br/> 0表示資料流程方向是從被叫方到來電者。  <br/> |
|**JitterInterArrivalSD** <br/> |浮  <br/> ||抖動到貨時間的標準差。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**ConcealRatioMax** <br/> |浮  <br/> ||Healer 所隱藏之資料包的最大比率。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**ConcealRatioSD** <br/> |浮  <br/> ||Healer 所隱藏之資料包之比率的標準差。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**HealerPacketDropRatio** <br/> |浮  <br/> ||Healer 丟棄的資料包與接收的總數據包數目之比。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**HealerFECPacketUsedRatio** <br/> |浮  <br/> ||與接收到的總數據包數目相比，已使用的轉寄錯誤修正資料包的比例。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**MaxCompressedSamples** <br/> |浮  <br/> ||Healer 壓縮的音訊資料包數目上限。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**LossCongestionPercent** <br/> |浮  <br/> ||表示通話處於遺失擁塞狀態的時間百分比。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**DelayCongestionPercent** <br/> |浮  <br/> ||指出因網路資料包損損，導致堵塞的時間百分比。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**ContentionDetectedPercent** <br/> |浮  <br/> ||表示通話爭用網路資源的時間百分比。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||呼叫期間測量的最小頻寬估計量。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||呼叫期間測量的最大頻寬估計量。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||在通話期間測量之頻寬估計的標準差。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||通話期間平均測量的頻寬估計量。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**RelativeOneWayTotal** <br/> |浮  <br/> ||單向延遲的總金額。 相對單向延遲會測量用戶端與伺服器之間的延遲。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**RelativeOneWayAverage** <br/> |浮  <br/> ||單向延隔時間的平均量。 相對單向延遲會測量用戶端與伺服器之間的延遲。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**RelativeOneWayMax** <br/> |浮  <br/> ||單向延隔時間的最大值。 相對單向延遲會測量用戶端與伺服器之間的延遲。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||單向突發發生次數總計。 "Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。 此量度會測量用戶端與伺服器之間的資料流程。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**RelativeOneWayBurstDensity** <br/> |浮  <br/> ||總計單向突發密度。 "Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。 此量度會測量用戶端與伺服器之間的資料流程。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**RelativeOneWayBurstDuration** <br/> |浮  <br/> ||總計單向突發持續時間。 "Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。 此量度會測量用戶端與伺服器之間的資料流程。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||總的單向間距發生情況。 "Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程;[空隙] 表示這些猝發之間的延遲。 此量度會測量用戶端與伺服器之間的資料流程。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**RelativeOneWayGapDensity** <br/> |浮  <br/> ||總單向間距密度。 "Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程;[空隙] 表示這些猝發之間的延遲。 此量度會測量用戶端與伺服器之間的資料流程。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**RelativeOneWayGapDuration** <br/> |浮  <br/> ||總共一個單向間距時間。 "Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程;[空隙] 表示這些猝發之間的延遲。 此量度會測量用戶端與伺服器之間的資料流程。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**DecodeStereoPercent** <br/> |浮  <br/> ||解碼為身歷聲的通話百分比。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**AecRenderStereoPercent** <br/> |浮  <br/> ||以身歷聲顯示的通話百分比，透過聲音回音 canceller。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**AudioPostFECPLR** <br/> |浮  <br/> ||已套用轉寄錯誤修正之後的資料包遺失率。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**EncodeStereoPercent** <br/> |浮  <br/> ||編碼為身歷聲的通話百分比。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**AecCaptureStereoPercent** <br/> |浮  <br/> ||以身歷聲的 canceller 所捕獲的通話百分比。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
