---
title: UserSite 表格
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
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: UserSite 表格是一種支援資料表，其中的每一項記錄都代表網路組態設定中定義的一個使用者網站。
---

# <a name="usersite-table"></a>UserSite 表格
 
UserSite 表格是一種支援資料表，其中的每一項記錄都代表網路組態設定中定義的一個使用者網站。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |主要  <br/> |用於識別使用者網站的唯一號碼。  <br/> |
|**UserSiteName** <br/> |Nvarchar (128)   <br/> |Unique  <br/> |使用者網站的名稱。  <br/> |
|**RegionKey** <br/> |int  <br/> |Foreign  <br/> |參照自 [地區表](region.md)。  <br/> |
   

