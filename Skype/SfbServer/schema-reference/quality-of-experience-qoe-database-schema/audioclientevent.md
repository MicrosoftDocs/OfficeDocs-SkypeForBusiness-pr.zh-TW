---
title: AudioClientEvent 表格
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
ms.assetid: fef73d8f-7261-4e5b-9769-82435b007979
description: 每筆記錄都包含音訊撥號中一個端點的用戶端事件。 通常，一個呼叫有兩筆記錄，一個用於來電者，另一個用於呼叫者。
ms.openlocfilehash: 65897c03f44cac5fd10a0e2c56e78bb5751ae7e3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583757"
---
# <a name="audioclientevent-table"></a>AudioClientEvent 表格
 
每筆記錄都包含音訊撥號中一個端點的用戶端事件。 通常，一個呼叫有兩筆記錄，一個用於來電者，另一個用於呼叫者。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |主要  <br/> |從 [MediaLine 表格](medialine-0.md)中參照。  <br/> |
|**SessionSeq** <br/> |int  <br/> |主要  <br/> |從 [MediaLine 表格](medialine-0.md)中參照。  <br/> |
|**MediaLineLabel** <br/> |Tinyint  <br/> |主要  <br/> |從 [MediaLine 表格](medialine-0.md)中參照。  <br/> |
|**FromCaller** <br/> |位  <br/> |主要  <br/> |0：被呼叫者的資料  <br/> 1：來電者的資料  <br/> |
|**NetworkSendQualityEventRatio** <br/> |十進位 (5，2)   <br/> | <br/> |會話百分比已針對 ' 壞」狀態引發 NetworkSendQuality 事件。  <br/> 抖動或封包遺失方面的網路品質很嚴重，且會影響所傳送之音訊的品質。  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> |十進位 (5，2)   <br/> | <br/> |會話百分比已針對 ' 壞」狀態引發 ReceiveSendQuality 事件。  <br/> 抖動或封包遺失方面的網路品質很嚴重，且會影響所接收的音訊品質。  <br/> |
|**NetworkDelayEventRatio** <br/> |十進位 (5，2)   <br/> | <br/> |會話百分比 Delay 事件因「錯誤」的狀態而引發。 網路延遲是嚴重的，而且會影響互動式通訊的體驗  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> |十進位 (5，2)   <br/> | <br/> |會話百分比 LowBandwidth 事件引發「不良」狀態。 可用的頻寬不足以取得可接受的語音體驗。  <br/> |
|**CPUInsufficientEventRatio** <br/> |十進位 (5，2)   <br/> | <br/> |會話百分比因「壞」狀態而引發的 CPU 事件不足。 使用目前的形式和應用程式來處理的 CPU 週期不足。 這會導致音訊通道失真。  <br/> |
|**DeviceHalfDuplexAECEventRatio** <br/> |十進位 (5，2)   <br/> | <br/> |會話百分比 DeviceHalfDuplexAEC 事件引發「不良」狀態。 為了避免回聲，系統有輸入半雙工。  <br/> |
|**DeviceRenderNotFunctioningEventRatio** <br/> |十進位 (5，2)   <br/> | <br/> |會話百分比 DeviceRenderNotFunctioning 事件引發「不良」狀態。 目前用於會話的呈現裝置無法正常運作。 這可能會造成單向音訊問題。  <br/> |
|**DeviceCaptureNotFunctioningEventRatio** <br/> |十進位 (5，2)   <br/> | <br/> |會話百分比 DeviceCaptureNotFunctioning 事件引發「不良」狀態。 目前用於會話的捕獲裝置無法正常運作。 這可能會造成單向音訊問題。  <br/> |
|**DeviceGlitchesEventRatio** <br/> |十進位 (5，2)   <br/> | <br/> |會話百分比 DeviceGlitches 事件引發「不良」狀態。 呈現導致失真的音訊時，發生嚴重的難題。 這些難題可能是由於驅動程式問題、延遲的程式呼叫 (DPC) 風暴 (驅動程式) 和高 CPU 使用率而引起。  <br/> |
|**DeviceLowSNREventRatio** <br/> |十進位 (5，2)   <br/> | <br/> |會話百分比 DeviceLowSNR 事件引發「不良」狀態。 [！注意] 捕獲品質很低，可能是極大噪音，或是使用者從麥克風的距離太遠。 這會導致失真。  <br/> |
|**DeviceLowSpeechLevelEventRatio** <br/> |十進位 (5，2)   <br/> | <br/> |會話百分比 DeviceLowSpeechLevel 事件引發「不良」狀態。 使用者的語音層級太低，系統無法進一步增加。 這可能會造成扭曲或感覺為單向音訊。  <br/> |
|**DeviceClippingEventRatio** <br/> |十進位 (5，2)   <br/> | <br/> |會話百分比已針對 ' 壞」狀態引發 DeviceClipping 事件。  <br/> 當近序語音剪下麥克風時，會因為剪裁而結束的時間太長。 請務必避免接近端的麥克風剪裁。  <br/> |
|**DeviceEchoEventRatio** <br/> |十進位 (5，2)   <br/> | <br/> |會話百分比 DeviceEchoEvent 事件引發「不良」狀態。 裝置或安裝程式導致回應超出系統補償的能力。  <br/> |
|**DeviceNearEndToEchoRatioEventRatio** <br/> |十進位 (5，2)   <br/> | <br/> |會話百分比 DeviceNearEndToEchoRatio 事件引發「不良」狀態。 使用者的語音變得太低，因為其所捕獲的回音會影響使用者的體驗，因為它會限制使用者的中斷。 減少喇叭的音量，請將麥克風移近 talker。  <br/> |
|**DeviceMultipleEndpointsEventCount** <br/> |int  <br/> ||會話期間為「不良」狀態引發 DeviceMultipleEndpoints 事件的次數。 偵測到相同會話中的多個音訊端點，而且系統已透過減少轉譯體積量進行補償。  <br/> |
|**DeviceHowlingEventCount** <br/> |int  <br/> | <br/> |會話期間為「不良」狀態引發 DeviceHowlingEvent 事件的次數。 在多個端點共用音訊路徑) 所造成的 (，會偵測到音訊意見反應。  <br/> |
|**DeviceRenderZeroVolumeEventRatio** <br/> |十進位 (5，2)   <br/> ||會話百分比會引發 DeviceRenderZeroVolume 事件，使其處於「不良」狀態。 呈現裝置已設定為零磁片區。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**DeviceRenderMuteEventRatio** <br/> |十進位 (5，2)   <br/> ||會話百分比會引發 DeviceRenderMute 事件，使其處於「不良」狀態。 呈現裝置已靜音。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
   

