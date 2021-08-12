---
title: AudioStream 表格
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
description: 每筆記錄代表一個音訊資料流程。 一個音訊媒體行通常包含兩個音訊資料流程。
ms.openlocfilehash: 28111f9c97efdc729d13fda824f4236caad97eee1f08ff31eea0b751dda1cb88
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309192"
---
# <a name="audiostream-table"></a>AudioStream 表格
 
每筆記錄代表一個音訊資料流程。 一個音訊媒體行通常包含兩個音訊資料流程。
  
|欄位|資料類型|索引鍵/索引|詳細資料|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |主要  <br/> |從 [MediaLine 表格](medialine-0.md)中參照。  <br/> |
|**SessionSeq** <br/> |int  <br/> |主要  <br/> |從 [MediaLine 表格](medialine-0.md)中參照。  <br/> |
|**MediaLineLabel** <br/> |Tinyint  <br/> |主要  <br/> |從 [MediaLine 表格](medialine-0.md)中參照。  <br/> |
|**StreamID** <br/> |int  <br/> |主要  <br/> |媒體行中的唯一識別碼。  <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |從即時控制通訊協定 (RTCP) 統計資料的平均網路抖動。  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |通話期間的最大網路抖動。  <br/> |
|**PacketLossRate** <br/> |十進位 (5，4)   <br/> | <br/> |通話期間的平均封包遺失率。  <br/> |
|**PacketLossRateMax** <br/> |十進位 (5，4)   <br/> | <br/> |通話期間觀察到的封包遺失上限。  <br/> |
|**BurstDensity** <br/> |十進位 (9，4)   <br/> | <br/> |通話期間的猝量遺失期間的封包遺失平均密度。  <br/> |
|**BurstDuration** <br/> |int  <br/> | <br/> |通話期間的猝量遺失期間的封包遺失平均持續時間。  <br/> |
|**BurstGapDensity** <br/> |十進位 (9，4)   <br/> | <br/> |封包遺失失敗之間的平均封包遺失密度。  <br/> |
|**BurstGapDuration** <br/> |int  <br/> | <br/> |封包遺失的平均持續時間。  <br/> |
|**PacketUtilization** <br/> |臨界值  <br/> | <br/> |音訊資料流程的封包計數。  <br/> |
|**BandwidthEst** <br/> |臨界值  <br/> | <br/> |音訊資料流程的頻寬估計值。  <br/> |
|**DegradationAvg** <br/> |十進位 (3，2)   <br/> | <br/> |整個通話的網路 MOS 降低。 範圍是0.0 到5.0。 此度量顯示由於抖動和封包遺失，網路 MOS 減少的數量。 可接受的品質應小於0.5。  <br/> |
|**DegradationMax** <br/> |十進位 (3，2)   <br/> | <br/> |通話期間的最大網路 MOS 降級。  <br/> |
|**DegradationJitterAvg** <br/> |十進位 (3，2)   <br/> | <br/> |抖動導致的網路 MOS 降低。  <br/> |
|**DegradationPacketLossAvg** <br/> |十進位 (3，2)   <br/> | <br/> |封包遺失導致的網路 MOS 降低。  <br/> |
|**AudioPayloadDescription** <br/> |int  <br/> |Foreign  <br/> |用於通話的音訊編解碼器，參考來源為 PayloadDescription Table。  <br/> |
|**AudioSampleRate** <br/> |int  <br/> | <br/> |音訊資料流程的取樣速率。  <br/> |
|**往返** <br/> |int  <br/> | <br/> |從 RTCP 統計資料來回的時間。 若為可接受的品質，則應小於100ms。  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |音訊資料流程的最大來回時間。  <br/> |
|**OverallAvgNetworkMOS** <br/> |十進位 (3，2)   <br/> | <br/> |通話的平均寬頻網路 MOS。 此度量取決於所用的封包遺失、抖動和編解碼器。 範圍為 [1.0 至 5.0]。  <br/> |
|**OverallMinNetworkMOS** <br/> |十進位 (3，2)   <br/> | <br/> |通話的最小寬頻網路 MOS。  <br/> |
|**SendListenMOS** <br/> |十進位 (3，2)   <br/> | <br/> |已傳送之音訊的平均預測寬頻傾聽 MOS 分數，包括語音層級、雜訊層級和捕獲裝置特性。  <br/> |
|**SendListenMOSMin** <br/> |十進位 (3，2)   <br/> | <br/> |通話的最小 SendListenMOS。  <br/> |
|**RecvListenMOS** <br/> |十進位 (3，2)   <br/> | <br/> |從網路接收之音訊的平均預測寬頻傾聽 MOS 分數，包括語音層級、雜訊層級、編解碼器、網路狀況和捕獲裝置特性。  <br/> |
|**RecvListenMOSMin** <br/> |十進位 (3，2)   <br/> | <br/> |通話的最小 RecvListenMOS。  <br/> |
|**AudioFECUsed** <br/> |位  <br/> ||指示是否要將音訊 FEC 用於通話的旗標。  <br/> |
|**RatioConcealedSamplesAvg** <br/> |十進位 (5，2)   <br/> ||音訊修復所產生之隱藏樣本與一般範例的平均比率。  <br/> |
|**RatioStretchedSamplesAvg** <br/> |十進位 (5，2)   <br/> ||音訊修復所產生之延伸樣本的平均比率為典型範例。  <br/> |
|**RatioCompressedSamplesAvg** <br/> |十進位 (5，2)   <br/> ||音訊修復所產生之壓縮樣本與一般範例的平均比率。  <br/> |
|**入境** <br/> |位  <br/> | <br/> |接收接收方的資料流程資料。  <br/> |
|**出埠** <br/> |位  <br/> | <br/> |接收寄件者端的資料流程資料。  <br/> |
|**SenderIsCallerPAI** <br/> |位  <br/> | <br/> |1表示資料流程是從來電者流向被呼叫方。  <br/> 0表示資料流程方向從被叫方傳送給來電者。  <br/> |
|**JitterInterArrivalSD** <br/> |float  <br/> ||抖動到達時間的標準差。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**ConcealRatioMax** <br/> |float  <br/> ||修復所隱藏的封包的最大比率。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**ConcealRatioSD** <br/> |float  <br/> ||修復所隱藏之封包的標準差。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**HealerPacketDropRatio** <br/> |float  <br/> ||修復丟棄的封包比率與接收的封包總數。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**HealerFECPacketUsedRatio** <br/> |float  <br/> ||與接收的封包總數相比，使用轉寄錯誤修正資料包的比例。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**MaxCompressedSamples** <br/> |float  <br/> ||修復壓縮的音訊封包數目上限。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||會指出通話處於遺失擁塞狀態的時間百分比。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||會指出在此通話所占的百分比，造成擁塞是由網路封包的延遲抵達所造成。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||會指出通話在競爭網路資源時的時間百分比。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||通話期間測量的頻寬預估最小值。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||通話期間測量的頻寬預估最大值。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||通話期間測量的頻寬預估標準差。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||通話期間測量的平均頻寬預估量。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||單向延遲的總金額。 相對單向延遲會測量用戶端與伺服器之間的延遲。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||單向延遲的平均金額。 相對單向延遲會測量用戶端與伺服器之間的延遲。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||單向延遲的最大值。 相對單向延遲會測量用戶端與伺服器之間的延遲。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||總單向突發的發生次數。 "爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。 此度量單位會測量用戶端與伺服器之間的資料流程。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||總單向爆炸流量密度。 "爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。 此度量單位會測量用戶端與伺服器之間的資料流程。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||總單向突發持續時間。 "爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。 此度量單位會測量用戶端與伺服器之間的資料流程。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||對單向間隔的總發生次數。 "爆發" 傳輸是一種傳輸，其中資料流程的資料流程與穩定的資料流程相反，其資料流程會以無法預測的方式傳輸;間隙表示這些猝發間的延遲。 此度量單位會測量用戶端與伺服器之間的資料流程。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||總單向間距密度。 "爆發" 傳輸是一種傳輸，其中資料流程的資料流程與穩定的資料流程相反，其資料流程會以無法預測的方式傳輸;間隙表示這些猝發間的延遲。 此度量單位會測量用戶端與伺服器之間的資料流程。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||總的單向間距持續時間。 "爆發" 傳輸是一種傳輸，其中資料流程的資料流程與穩定的資料流程相反，其資料流程會以無法預測的方式傳輸;間隙表示這些猝發間的延遲。 此度量單位會測量用戶端與伺服器之間的資料流程。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**DecodeStereoPercent** <br/> |float  <br/> ||解碼為身歷聲的通話百分比。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**AecRenderStereoPercent** <br/> |float  <br/> ||透過聲音回聲效果取消器呈現為身歷聲的通話百分比。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**AudioPostFECPLR** <br/> |float  <br/> ||套用轉寄錯誤修正後的封包遺失率。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**EncodeStereoPercent** <br/> |float  <br/> ||編碼為身歷聲的通話百分比。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**AecCaptureStereoPercent** <br/> |float  <br/> ||以身歷聲的回聲效果取消器取得之來電所占的百分比。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
