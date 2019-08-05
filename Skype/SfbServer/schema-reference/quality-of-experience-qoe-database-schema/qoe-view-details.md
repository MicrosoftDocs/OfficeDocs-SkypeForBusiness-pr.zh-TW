---
title: QoE 查看詳細資料
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: '[視圖] 涵蓋從 QoE SQL 資料庫傳回資料最常見的案例。 它是用來建立自訂報表的建議視圖, 而不是直接存取資料庫資料表;這是因為視圖更可能會維持與未來版本的向後相容性。'
ms.openlocfilehash: c492b06f2b6e8050e4992837f0f2b7ebba106858
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192646"
---
# <a name="qoe-view-details"></a>QoE 查看詳細資料
 
[視圖] 涵蓋從 QoE SQL 資料庫傳回資料最常見的案例。 它是用來建立自訂報表的建議視圖, 而不是直接存取資料庫資料表;這是因為視圖更可能會維持與未來版本的向後相容性。
  
|**[視圖名稱]**|**說明**|
|:-----|:-----|
|[AudioStreamDetail 視圖](audiostreamdetail.md) <br/> |儲存資料庫中每個音訊資料流程的相關資訊。  <br/> |
|[MediaLine 視圖](medialine.md) <br/> |儲存資料庫中每個媒體線的相關資訊。 一個音訊會話通常包含一個音訊媒體線。 一個音訊與影片 (A/V) 會話通常包含一個音訊媒體線和一個影片媒體線;不過, 如果使用會議裝置或使用圖庫視圖, 該會話可能會包含兩個視頻媒體線。  <br/> |
|[NetworkConfigurationSettings 視圖](networkconfigurationsettings.md) <br/> |儲存網路設定的相關資訊。  <br/> |
|[[會話] 視圖](session-0.md) <br/> |儲存在資料庫中有記錄的會話的相關資訊。  <br/> |
|[UserAgent 視圖](useragent-0.md) <br/> |儲存在資料庫中有記錄的會話中所涉及之使用者代理程式的相關資訊。  <br/> |
|[VideoStreamDetail 視圖](videostreamdetail.md) <br/> |儲存資料庫中每個影片資料流程的相關資訊。  <br/> |
   

