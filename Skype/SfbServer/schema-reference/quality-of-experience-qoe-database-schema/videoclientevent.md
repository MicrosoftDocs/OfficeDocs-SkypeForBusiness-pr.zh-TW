---
title: VideoClientEvent 表格
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: 每個記錄在影片通話中包含一個端點的用戶端事件。 通常，一個呼叫有兩筆記錄，一個用於來電者，另一個用於呼叫者。
---

# <a name="videoclientevent-table"></a>VideoClientEvent 表格
 
每個記錄在影片通話中包含一個端點的用戶端事件。 通常，一個呼叫有兩筆記錄，一個用於來電者，另一個用於呼叫者。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |主要  <br/> |從 [MediaLine 表格](medialine-0.md)中參照。  <br/> |
|**SessionSeq** <br/> |int  <br/> |主要  <br/> |從 [MediaLine 表格](medialine-0.md)中參照。  <br/> |
|**MediaLineLabel** <br/> |Tinyint  <br/> |主要  <br/> |從 [MediaLine 表格](medialine-0.md)中參照。  <br/> |
|**FromCaller** <br/> |位  <br/> |主要  <br/> |0：被呼叫者的資料  <br/> 1：來電者的資料  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> || <br/> |會話百分比 LowBandwidth 事件引發「不良」狀態。 可用的頻寬不足以取得可接受的語音體驗。  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> || <br/> |會話百分比已針對 ' 壞」狀態引發 ReceiveSendQuality 事件。  <br/> 抖動或封包遺失方面的網路品質很嚴重，且會影響所接收的音訊品質。  <br/> |
   

