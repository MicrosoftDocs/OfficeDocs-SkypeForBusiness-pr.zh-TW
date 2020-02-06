---
title: User 表格
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
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: '[使用者] 資料表是一個支援資料表，可儲存已參與資料庫中記錄之會話的各種使用者清單。 資料表中的每一筆記錄代表一個使用者。'
ms.openlocfilehash: fcb6c4d45f1392c31ba87637d6e3a1a697f7be9e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805091"
---
# <a name="user-table"></a>User 表格
 
[使用者] 資料表是一個支援資料表，可儲存已參與資料庫中記錄之會話的各種使用者清單。 資料表中的每一筆記錄代表一個使用者。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |int  <br/> |首選  <br/> |標識此使用者的唯一號碼。  <br/> |
|**URL** <br/> |Nvarchar （450）  <br/> |唯一  <br/> |URI 字串。  <br/> |
|**URIType** <br/> |int  <br/> ||1是未知的 URI 類型。  <br/> 2是使用者 URI。  <br/> 4是會議 URI。  <br/> 8是電話 URI。  <br/> |
|**TenantKey** <br/> |int  <br/> |外  <br/> |使用者的租使用者，從租使用者資料表參考。  <br/> |
|**LastPoorCallTime** <br/> |datetime  <br/> ||當使用者的語音通話不佳時，請使用最新的時間戳記。  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||僅供內部使用。  <br/> |
   

