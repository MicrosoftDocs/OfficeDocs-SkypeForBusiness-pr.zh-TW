---
title: AudioSignal 表格
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
ms.localizationpriority: medium
ms.assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
description: 每筆記錄代表一個端點的音訊信號計量。 通常，每個呼叫都有兩筆記錄，一個用於來電者，另一個則用於被叫用方。
ms.openlocfilehash: 0f021b438fe31bf180ee06ce83dad86e01c04070
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58592397"
---
# <a name="audiosignal-table"></a>AudioSignal 表格
 
每筆記錄代表一個端點的音訊信號計量。 通常，每個呼叫都有兩筆記錄，一個用於來電者，另一個則用於被叫用方。 
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |主要  <br/> |從 [MediaLine 表格](medialine-0.md)中參照。  <br/> |
|**SessionSeq** <br/> |int  <br/> |主要  <br/> |從 [MediaLine 表格](medialine-0.md)中參照。  <br/> |
|**MediaLineLabel** <br/> |Tinyint  <br/> |主要  <br/> |從 [MediaLine 表格](medialine-0.md)中參照。  <br/> |
|**FromCaller** <br/> |位  <br/> |主要  <br/> |0：被呼叫者的資料  <br/> 1：來電者的資料  <br/> |
|**SendSignalLevel** <br/> |int  <br/> | <br/> |代表 [類比後增益控制音訊信號] 層級。 此度量單位的單位是 dBmo。 若要取得可接受的品質，至少要有 30 dBmo。 A/V 的會議服務器或 IP 電話不會報告此度量。  <br/> |
|**RecvSignalLevel** <br/> |int  <br/> | <br/> |請參閱 SendSignalLevel。  <br/> |
|**SendNoiseLevel** <br/> |int  <br/> | <br/> |代表 [類比後增益控制音訊雜訊層級]。 此度量單位的單位是 dBmo。 針對可接受的品質，它應小於 35 dBmo。 A/V 的會議服務器或 IP 電話不會報告此度量。  <br/> |
|**RecvNoiseLevel** <br/> |int  <br/> | <br/> |請參閱 SendNoiseLevel。  <br/> |
|**EchoReturn** <br/> |int  <br/> | <br/> |迴響傳回遺失增強度量。 此度量單位的單位為 dB。 較低的值表示較少的回聲。 A/V 的會議服務器或 IP 電話不會報告此度量。  <br/> |
|**AudioSpeakerGlitchRate** <br/> |int  <br/> | <br/> |喇叭轉譯每五分鐘的平均故障。 為了獲得良好的品質，應小於每五分鐘一次。 不會 A/V 會議伺服器、轉送伺服器或 IP 電話上報告。  <br/> |
|**AudioMicGlitchRate** <br/> |int  <br/> | <br/> |每五分鐘捕獲麥克風的平均故障。 若為良好的品質，這應小於每五分鐘一次。 不會 A/V 會議伺服器、轉送伺服器或 IP 電話上報告。  <br/> |
|**AudioTimestampDriftRateMic** <br/> |十進位 (9，2)   <br/> | <br/> |麥克風裝置時鐘相對於 CPU 時鐘的相對頻率。  <br/> |
|**AudioTimestampDriftRateSpk** <br/> |十進位 (9，2)   <br/> | <br/> |揚聲器裝置時鐘相對於 CPU 時鐘的相對頻率。  <br/> |
|**AudioTimestampErrorMicMs** <br/> |十進位 (9，2)   <br/> | <br/> |揚聲器裝置時鐘相對於 CPU 時鐘的相對頻率。  <br/> 通話的最後20秒內的平均麥克風捕獲資料流程時間戳記錯誤（毫秒）。  <br/> |
|**AudioTimestampErrorSpkMs** <br/> |十進位 (9，2)   <br/> | <br/> |通話的最後20秒內，平均喇叭轉譯資料流程時間戳記錯誤（毫秒）。  <br/> |
|**VsEntryCauses** <br/> |Smallint  <br/> | <br/> |語音開關是一種具有低中斷能力的半雙工模式。 語音開關專案的原因：  <br/> ENTER_VS_BADTS 0x01  <br/> ENTER_VS_ECHO 0x02  <br/> ENTER_VS_FORCEORCONVERGENCE 0x04  <br/> ENTER_VS_DNLP 0x08  <br/> 原因可能是個別原因的組合。 ENTER_VS_FORCEORCONVERGENCE 只能透過 regkey 為測試目的來啟用。  <br/> 在 Microsoft Lync Server 2013 中，此欄的資料類型已變更。  <br/> |
|**EchoEventCauses** <br/> |Tinyint  <br/> | <br/> |Echo 事件的原因：  <br/> ECHO_EVENT_BAD_TIMESTAMP 0x01  <br/> ECHO_EVENT_POSTAEC_ECHO 0x02  <br/> ECHO_EVENT_ANLP 0x04  <br/> ECHO_EVENT_DNLP 0x08  <br/> ECHO_EVENT_MIC_CLIPPING 0x10  <br/> ECHO_EVENT_BAD_STATE 0x20  <br/> 原因可能是個別原因的組合。  <br/> |
|**EchoPercentMicIn** <br/> |十進位 (5，2)   <br/> | <br/> |在麥克風捕獲資料流程中偵測到迴響的時間百分比。 通常，耳機或電話機的值很低，對喇叭或獨立揚聲器而言，其值也會比較高。 針對支援板載聲音回聲取消功能的裝置，高值表示回聲洩漏。 若為其他裝置，則不應該使用此度量來評估裝置品質。  <br/> |
|**EchoPercentSend** <br/> |十進位 (5，2)   <br/> ||在傳送的資料流程中偵測到迴響時的時間百分比。 傳送資料流程中的高回音百分比會傳回回聲洩漏。  <br/> |
|**RxAGCSignalLevel** <br/> |int  <br/> | <br/> |從閘道從轉送伺服器接收信號層級;這只適用于轉送伺服器。 此度量單位為 dBoV。 為了獲得良好的品質，可接受的範圍應為 [-30 到-18] dBoV。  <br/> |
|**RxAGCNoiseLevel** <br/> |int  <br/> | <br/> |從閘道從轉送伺服器接收信號層級。 這只適用于轉送伺服器。 此度量單位為 dBoV。 為了獲得良好的品質，可接受的範圍應小於-50 dBoV。  <br/> |
|**RxAvgAGCGain** <br/> |int  <br/> | <br/> | (AGC) 轉送伺服器端的自動增益控制。  <br/> |
|**InitialSignalLevelRMS** <br/> |float  <br/> | <br/> |從來電的前30秒內之傳入信號的根平均平方 (RMS) 。  <br/> |
|**RecvSignalLevelCh1** <br/> |int  <br/> ||通道1上接收的信號等級。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**RecvSignalLevelCh2** <br/> |int  <br/> ||通道2上接收的信號等級。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**RecvNoiseLevelCh1** <br/> |int  <br/> ||通道1上接收的雜訊層級。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**RecvNoiseLevelCh2** <br/> |int  <br/> ||通道2上接收的雜訊水準。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**SendSignalLevelCh1** <br/> |int  <br/> ||通道1上傳送的信號層級。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**SendSignalLevelCh2** <br/> |int  <br/> ||通道2上傳送的信號層級。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**SendNoiseLevelCh1** <br/> |int  <br/> ||通道1上傳送的雜訊層級。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**SendNoiseLevelCh2** <br/> |int  <br/> ||通道2上傳送的雜訊層級。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**RenderLoopbackSignalLevel** <br/> |int  <br/> ||傳送至喇叭進行播放之信號的 dBFS 層級。 對收到的信號所做的任何增益調整帳戶。 <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |   
|**RenderNoiseLevel** <br/> |int  <br/> ||傳送至喇叭進行播放之信號中的 dBFS 雜訊內容層級 <br/> |

