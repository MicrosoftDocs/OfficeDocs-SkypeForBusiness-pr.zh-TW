---
title: VideoClientEvent 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: 每個記錄都包含視頻通話中某個端點的用戶端事件。 通常, 一個通話有兩筆記錄, 一個用於呼叫者, 另一個用於被叫方。
ms.openlocfilehash: b8e93206ea30622baa82adcec5ee9a80235521c5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192613"
---
# <a name="videoclientevent-table"></a>VideoClientEvent 表格
 
每個記錄都包含視頻通話中某個端點的用戶端事件。 通常, 一個通話有兩筆記錄, 一個用於呼叫者, 另一個用於被叫方。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |首選  <br/> |從[MediaLine 資料表](medialine-0.md)中參照。  <br/> |
|**SessionSeq** <br/> |int  <br/> |首選  <br/> |從[MediaLine 資料表](medialine-0.md)中參照。  <br/> |
|**MediaLineLabel** <br/> |Tinyint  <br/> |首選  <br/> |從[MediaLine 資料表](medialine-0.md)中參照。  <br/> |
|**FromCaller** <br/> |稍微  <br/> |首選  <br/> |0: 被方程式的資料  <br/> 1: 來電者的資料  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> || <br/> |會話針對「錯誤」狀態觸發 LowBandwidth 事件的百分比。 可用的頻寬不足以取得可接受的語音體驗。  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> || <br/> |會話針對「錯誤」狀態觸發 ReceiveSendQuality 事件的百分比。  <br/> 在抖動或資料包遺失方面的網路品質很嚴重, 而且會影響接收的音訊品質。  <br/> |
   

