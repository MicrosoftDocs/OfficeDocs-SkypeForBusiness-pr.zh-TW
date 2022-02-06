---
title: 使用者表格
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
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: User 表格是一種支援資料表，儲存資料庫中所記錄的工作階段之各參與使用者的清單。表格中的每筆記錄代表一位使用者。
---

# <a name="user-table"></a>使用者表格
 
User 表格是一種支援資料表，儲存資料庫中所記錄的工作階段之各參與使用者的清單。表格中的每筆記錄代表一位使用者。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |int  <br/> |主要  <br/> |用於識別此使用者的唯一號碼。  <br/> |
|**URI** <br/> |Nvarchar (450)   <br/> |Unique  <br/> |URI 字串。  <br/> |
|**URIType** <br/> |int  <br/> ||1 是未知的 URI 類型。  <br/> 2 是使用者 URI。  <br/> 4 是會議 URI。  <br/> 8 是電話 URI。  <br/> |
|**TenantKey** <br/> |int  <br/> |Foreign  <br/> |使用者的承租人，參考來源：Tenant 表格。  <br/> |
|**LastPoorCallTime** <br/> |datetime  <br/> ||最近一次使用者通話音訊品質不佳的時間戳記。  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||僅限內部使用。  <br/> |
   

