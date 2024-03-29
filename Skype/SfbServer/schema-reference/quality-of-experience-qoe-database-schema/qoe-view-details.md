---
title: QoE 檢視詳細資料
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: 檢視涵蓋從 QoE SQL 資料庫傳回資料時最常見的案例。 它是用來建立自訂報告的建議方式，而不是直接存取資料庫資料表;這是因為視圖很可能會讓未來的版本保持向後相容性。
ms.openlocfilehash: d812af701a0073b8be4188b98cd94a66d50c68d3
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62385381"
---
# <a name="qoe-view-details"></a>QoE 檢視詳細資料
 
檢視涵蓋從 QoE SQL 資料庫傳回資料時最常見的案例。 它是用來建立自訂報告的建議方式，而不是直接存取資料庫資料表;這是因為視圖很可能會讓未來的版本保持向後相容性。
  
|**視圖名稱**|**描述**|
|:-----|:-----|
|[AudioStreamDetail view](audiostreamdetail.md) <br/> |儲存資料庫中每個音訊資料流的資訊。  <br/> |
|[MediaLine view](medialine.md) <br/> |儲存資料庫中每個媒體行的資訊。 一個音訊工作階段通常包含一個音訊媒體行。 一個音訊和視訊 (A/V) 工作階段通常包含一個音訊媒體行和一個視訊媒體行；不過，如果使用會議裝置或使用圖庫檢視，則工作階段可能包含兩個媒體行。  <br/> |
|[NetworkConfigurationSettings view](networkconfigurationsettings.md) <br/> |儲存網路設定的資訊。  <br/> |
|[會話視圖](session-0.md) <br/> |儲存在資料庫中擁有記錄之工作階段的資訊。  <br/> |
|[UserAgent view](useragent-0.md) <br/> |儲存使用者代理程式的資訊，這些使用者代理程式與在資料庫中擁有記錄的工作階段相關。  <br/> |
|[VideoStreamDetail view](videostreamdetail.md) <br/> |儲存在資料庫中每個視訊資料流的資訊。  <br/> |
   

