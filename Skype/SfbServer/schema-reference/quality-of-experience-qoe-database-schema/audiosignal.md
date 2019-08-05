---
title: AudioSignal 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
description: 每個記錄代表一個端點的音訊信號度量單位。 通常, 每個通話都有兩筆記錄, 一個用於呼叫者, 另一個則稱為被叫方。
ms.openlocfilehash: f8d617e96fe3427493bcb9e4cc70008fedae72e7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192690"
---
# <a name="audiosignal-table"></a>AudioSignal 表格
 
每個記錄代表一個端點的音訊信號度量單位。 通常, 每個通話都有兩筆記錄, 一個用於呼叫者, 另一個則稱為被叫方。 
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |首選  <br/> |從[MediaLine 資料表](medialine-0.md)中參照。  <br/> |
|**SessionSeq** <br/> |int  <br/> |首選  <br/> |從[MediaLine 資料表](medialine-0.md)中參照。  <br/> |
|**MediaLineLabel** <br/> |Tinyint  <br/> |首選  <br/> |從[MediaLine 資料表](medialine-0.md)中參照。  <br/> |
|**FromCaller** <br/> |稍微  <br/> |首選  <br/> |0: 被方程式的資料  <br/> 1: 來電者的資料  <br/> |
|**SendSignalLevel** <br/> |int  <br/> | <br/> |代表 [反後的類比增益控制音訊信號] 層級。 這個指標的單位是 dBmo。 若要取得可接受的品質, 至少要有 30 dBmo。 A/V 會議伺服器或 IP 電話不會報告此統計值。  <br/> |
|**RecvSignalLevel** <br/> |int  <br/> | <br/> |請參閱 SendSignalLevel。  <br/> |
|**SendNoiseLevel** <br/> |int  <br/> | <br/> |代表 [反後類比增益控制音訊雜訊] 層級。 這個指標的單位是 dBmo。 針對可接受的品質, 它應該小於 35 dBmo。 A/V 會議伺服器或 IP 電話不會報告此統計值。  <br/> |
|**RecvNoiseLevel** <br/> |int  <br/> | <br/> |請參閱 SendNoiseLevel。  <br/> |
|**EchoReturn** <br/> |int  <br/> | <br/> |迴響傳回損失增強指標。 這個指標的單位是 dB。 較低的值代表較少的回音。 A/V 會議伺服器或 IP 電話不會報告此統計值。  <br/> |
|**AudioSpeakerGlitchRate** <br/> |int  <br/> | <br/> |喇叭前轉譯每五分鐘的平均故障。 若要獲得較高的品質, 此頻率應該小於每五分鐘。 無法由 A/V 會議伺服器、中繼伺服器或 IP 電話來報告。  <br/> |
|**AudioMicGlitchRate** <br/> |int  <br/> | <br/> |麥克風捕獲每五分鐘的平均故障。 若要獲得良好的品質, 這應該少於每五分鐘一次。 無法由 A/V 會議伺服器、中繼伺服器或 IP 電話來報告。  <br/> |
|**AudioTimestampDriftRateMic** <br/> |decimal (9, 2)  <br/> | <br/> |麥克風裝置時鐘相對於 CPU 時鐘的時鐘偏移速度。  <br/> |
|**AudioTimestampDriftRateSpk** <br/> |decimal (9, 2)  <br/> | <br/> |喇叭裝置時鐘相對於 CPU 時鐘的時鐘偏移速度。  <br/> |
|**AudioTimestampErrorMicMs** <br/> |decimal (9, 2)  <br/> | <br/> |喇叭裝置時鐘相對於 CPU 時鐘的時鐘偏移速度。  <br/> 在呼叫的最後20秒內, 麥克風捕獲串流的時間戳記錯誤 (以毫秒為單位)。  <br/> |
|**AudioTimestampErrorSpkMs** <br/> |decimal (9, 2)  <br/> | <br/> |在呼叫的最後20秒內, 演講者轉譯資料流程時間戳記的錯誤 (以毫秒為單位)。  <br/> |
|**VsEntryCauses** <br/> |Smallint  <br/> | <br/> |Voice 開關是一種半雙工模式, 可減少中斷能力。 語音切換專案的原因:  <br/> ENTER_VS_BADTS 0x01  <br/> ENTER_VS_ECHO 0x02  <br/> ENTER_VS_FORCEORCONVERGENCE 0x04  <br/> ENTER_VS_DNLP 0x08  <br/> 原因可能是由這些個別原因所組成。 ENTER_VS_FORCEORCONVERGENCE 只能由 regkey 啟用以進行測試。  <br/> 此欄的資料類型已在 Microsoft Lync Server 2013 中變更。  <br/> |
|**EchoEventCauses** <br/> |Tinyint  <br/> | <br/> |Echo 事件的原因:  <br/> ECHO_EVENT_BAD_TIMESTAMP 0x01  <br/> ECHO_EVENT_POSTAEC_ECHO 0x02  <br/> ECHO_EVENT_ANLP 0x04  <br/> ECHO_EVENT_DNLP 0x08  <br/> ECHO_EVENT_MIC_CLIPPING 0x10  <br/> ECHO_EVENT_BAD_STATE 0x20  <br/> 原因可能是由這些個別原因所組成。  <br/> |
|**EchoPercentMicIn** <br/> |decimal (5, 2)  <br/> | <br/> |在麥克風捕獲資料流程中檢測到迴響的時間百分比。 通常, 耳機或話機的值較低, 而喇叭或獨立喇叭的值則較高。 對於支援板載音響回聲取消的裝置, 高值表示迴響洩漏。 對於其他裝置, 此規格不應該用來評估裝置品質。  <br/> |
|**EchoPercentSend** <br/> |decimal (5, 2)  <br/> ||在傳送資料流程中檢測到迴響的時間百分比。 傳送資料流程中的高迴響百分比表示回應洩漏。  <br/> |
|**RxAGCSignalLevel** <br/> |int  <br/> | <br/> |從閘道在中繼伺服器接收到的信號等級;這只適用于中繼伺服器。 這個度量單位是 dBoV。 若要獲得良好的品質, 可接受的範圍應該是 [-30 至-18] dBoV。  <br/> |
|**RxAGCNoiseLevel** <br/> |int  <br/> | <br/> |從閘道在中繼伺服器上收到的信號等級。 這只適用于中繼伺服器。 這個度量單位是 dBoV。 若要獲得良好的品質, 可接受的範圍應該小於-50 dBoV。  <br/> |
|**RxAvgAGCGain** <br/> |int  <br/> | <br/> |在中繼伺服器端的自動增益控制 (AGC)。  <br/> |
|**InitialSignalLevelRMS** <br/> |浮  <br/> | <br/> |撥入信號的根平均數 (RMS), 最多可達呼叫的前30秒。  <br/> |
|**RecvSignalLevelCh1** <br/> |int  <br/> ||頻道1上接收到的信號等級。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**RecvSignalLevelCh2** <br/> |int  <br/> ||頻道2上接收到的信號等級。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**RecvNoiseLevelCh1** <br/> |int  <br/> ||頻道1上接收到的雜訊等級。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**RecvNoiseLevelCh2** <br/> |int  <br/> ||頻道2上接收的噪音等級。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**SendSignalLevelCh1** <br/> |int  <br/> ||頻道1上傳送的信號等級。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**SendSignalLevelCh2** <br/> |int  <br/> ||頻道2上傳送的信號等級。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**SendNoiseLevelCh1** <br/> |int  <br/> ||頻道1上傳送的雜訊等級。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**SendNoiseLevelCh2** <br/> |int  <br/> ||頻道2上傳送的雜訊等級。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**RenderLoopbackSignalLevel** <br/> |int  <br/> ||DBFS 傳送到喇叭前來播放之信號的層級。 針對收到的信號所做的任何增益調整帳戶。 <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |   
|**RenderNoiseLevel** <br/> |int  <br/> ||DBFS 傳送至喇叭前以進行播放之信號中的噪音內容的層級 <br/> |

