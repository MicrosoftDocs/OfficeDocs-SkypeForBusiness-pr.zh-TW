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
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: '[使用者] 資料表是一個支援資料表, 可儲存已參與資料庫中記錄之會話的各種使用者清單。 資料表中的每一筆記錄代表一個使用者。'
ms.openlocfilehash: a9f72793d3b287406b1b3b7e1ad360e7f5abc598
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192625"
---
# <a name="user-table"></a>User 表格
 
[使用者] 資料表是一個支援資料表, 可儲存已參與資料庫中記錄之會話的各種使用者清單。 資料表中的每一筆記錄代表一個使用者。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |int  <br/> |首選  <br/> |標識此使用者的唯一號碼。  <br/> |
|**URL** <br/> |Nvarchar (450)  <br/> |唯一  <br/> |URI 字串。  <br/> |
|**URIType** <br/> |int  <br/> ||1是未知的 URI 類型。  <br/> 2是使用者 URI。  <br/> 4是會議 URI。  <br/> 8是電話 URI。  <br/> |
|**TenantKey** <br/> |int  <br/> |外  <br/> |使用者的租使用者, 從租使用者資料表參考。  <br/> |
|**LastPoorCallTime** <br/> |datetime  <br/> ||當使用者的語音通話不佳時, 請使用最新的時間戳記。  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||僅供內部使用。  <br/> |
   

