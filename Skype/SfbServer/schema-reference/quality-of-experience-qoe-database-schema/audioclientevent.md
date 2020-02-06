---
title: AudioClientEvent 表格
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
ms.assetid: fef73d8f-7261-4e5b-9769-82435b007979
description: 每個記錄都包含音訊通話中某個端點的用戶端事件。 通常，一個通話有兩筆記錄，一個用於呼叫者，另一個用於被叫方。
ms.openlocfilehash: 713804875f9cd2a1fc37a2255697c4ffda47a3c5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41811081"
---
# <a name="audioclientevent-table"></a>AudioClientEvent 表格
 
每個記錄都包含音訊通話中某個端點的用戶端事件。 通常，一個通話有兩筆記錄，一個用於呼叫者，另一個用於被叫方。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |首選  <br/> |從[MediaLine 資料表](medialine-0.md)中參照。  <br/> |
|**SessionSeq** <br/> |int  <br/> |首選  <br/> |從[MediaLine 資料表](medialine-0.md)中參照。  <br/> |
|**MediaLineLabel** <br/> |Tinyint  <br/> |首選  <br/> |從[MediaLine 資料表](medialine-0.md)中參照。  <br/> |
|**FromCaller** <br/> |稍微  <br/> |首選  <br/> |0：被方程式的資料  <br/> 1：來電者的資料  <br/> |
|**NetworkSendQualityEventRatio** <br/> |decimal （5，2）  <br/> | <br/> |會話針對「錯誤」狀態觸發 NetworkSendQuality 事件的百分比。  <br/> 在抖動或資料包遺失方面的網路品質很嚴重，而且會影響音訊傳送品質。  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> |decimal （5，2）  <br/> | <br/> |會話針對「錯誤」狀態觸發 ReceiveSendQuality 事件的百分比。  <br/> 在抖動或資料包遺失方面的網路品質很嚴重，而且會影響接收的音訊品質。  <br/> |
|**NetworkDelayEventRatio** <br/> |decimal （5，2）  <br/> | <br/> |會話針對「錯誤」狀態觸發延遲事件的百分比。 網路延遲是嚴重的，並防止互動式通訊而影響體驗  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> |decimal （5，2）  <br/> | <br/> |會話針對「錯誤」狀態觸發 LowBandwidth 事件的百分比。 可用的頻寬不足以取得可接受的語音體驗。  <br/> |
|**CPUInsufficientEventRatio** <br/> |decimal （5，2）  <br/> | <br/> |會話百分比因「錯誤」狀態而觸發的 CPU 事件不足。 使用目前的形式和應用程式時，沒有足夠的 CPU 週期來處理。 這會導致音訊通道出現扭曲。  <br/> |
|**DeviceHalfDuplexAECEventRatio** <br/> |decimal （5，2）  <br/> | <br/> |會話針對「錯誤」狀態觸發 DeviceHalfDuplexAEC 事件的百分比。 為了防止回顯，系統會輸入半雙工。  <br/> |
|**DeviceRenderNotFunctioningEventRatio** <br/> |decimal （5，2）  <br/> | <br/> |會話針對「錯誤」狀態觸發 DeviceRenderNotFunctioning 事件的百分比。 目前用於會話的轉譯裝置無法正常運作。 這可能會導致單向音訊問題。  <br/> |
|**DeviceCaptureNotFunctioningEventRatio** <br/> |decimal （5，2）  <br/> | <br/> |會話針對「錯誤」狀態觸發 DeviceCaptureNotFunctioning 事件的百分比。 目前用於會話的捕獲裝置無法正常運作。 這可能會導致單向音訊問題。  <br/> |
|**DeviceGlitchesEventRatio** <br/> |decimal （5，2）  <br/> | <br/> |會話針對「錯誤」狀態觸發 DeviceGlitches 事件的百分比。 在轉譯造成扭曲的音訊時，會發生嚴重的問題。 這些故障可能是由驅動程式問題、延遲的程式呼叫（DPC）風暴（驅動程式）和高 CPU 使用率所造成。  <br/> |
|**DeviceLowSNREventRatio** <br/> |decimal （5，2）  <br/> | <br/> |會話針對「錯誤」狀態觸發 DeviceLowSNR 事件的百分比。 捕捉品質很差、極大雜音，或使用者正在遠離麥克風太遠。 這會造成扭曲。  <br/> |
|**DeviceLowSpeechLevelEventRatio** <br/> |decimal （5，2）  <br/> | <br/> |會話針對「錯誤」狀態觸發 DeviceLowSpeechLevel 事件的百分比。 使用者的語音等級太低，且系統無法進一步增加。 這可能會造成扭曲或視為單向音訊。  <br/> |
|**DeviceClippingEventRatio** <br/> |Decimal （5，2）  <br/> | <br/> |會話針對「錯誤」狀態觸發 DeviceClipping 事件的百分比。  <br/> 近距離語音會剪下麥克風，這是由於修剪而進行的最大終點聲音失真。 請務必避免接近結束的麥克風剪輯。  <br/> |
|**DeviceEchoEventRatio** <br/> |decimal （5，2）  <br/> | <br/> |會話針對「錯誤」狀態觸發 DeviceEchoEvent 事件的百分比。 裝置或安裝程式導致回應超出系統的補償能力。  <br/> |
|**DeviceNearEndToEchoRatioEventRatio** <br/> |decimal （5，2）  <br/> | <br/> |會話針對「錯誤」狀態觸發 DeviceNearEndToEchoRatio 事件的百分比。 使用者的語音太低，因為所捕獲的迴響會影響使用者體驗，因為它限制了中斷使用者的難易程度。 減少喇叭音量，請將麥克風移近交談者。  <br/> |
|**DeviceMultipleEndpointsEventCount** <br/> |int  <br/> ||會話期間觸發 DeviceMultipleEndpoints 事件以取得「錯誤」狀態的次數。 檢測到相同會話中有多個音訊端點，且系統已透過減少轉譯音量進行補償。  <br/> |
|**DeviceHowlingEventCount** <br/> |int  <br/> | <br/> |會話期間觸發 DeviceHowlingEvent 事件以取得「錯誤」狀態的次數。 偵測到音訊意見反應（由多個端點共用音訊路徑所致）。  <br/> |
|**DeviceRenderZeroVolumeEventRatio** <br/> |decimal （5，2）  <br/> ||已觸發 DeviceRenderZeroVolume 事件以「錯誤」狀態的會話百分比。 轉譯裝置已設定為零卷。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**DeviceRenderMuteEventRatio** <br/> |decimal （5，2）  <br/> ||已觸發 DeviceRenderMute 事件以「錯誤」狀態的會話百分比。 渲染裝置已靜音。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
   

