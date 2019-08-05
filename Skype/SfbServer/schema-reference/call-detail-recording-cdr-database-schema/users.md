---
title: Users 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: '[使用者] 資料表是支援表格。 資料表中的每一筆記錄都儲存有關在資料庫中有記錄的通話或會話中涉及之一個使用者的相關資訊。'
ms.openlocfilehash: 0dcc2fda73305be2bbe6a7a5c546dac0b05f8273
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192779"
---
# <a name="users-table"></a>Users 表格
 
[使用者] 資料表是支援表格。 資料表中的每一筆記錄都儲存有關在資料庫中有記錄的通話或會話中涉及之一個使用者的相關資訊。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> ||內部使用的時間戳記。  <br/> |
|**UserId** <br/> |int  <br/> |首選  <br/> |標識此使用者的唯一號碼。  <br/> |
|**UserUri** <br/> |Nvarchar (450)  <br/> | <br/> |使用者 URI。  <br/> |
|**TenantId** <br/> |int  <br/> |外  <br/> |此使用者的租使用者識別碼。 如需詳細資訊, 請參閱[承租人資料表](tenants.md)。 <br/> |
|**UriTypeId** <br/> |int  <br/> |外  <br/> |此使用者的 URI 類型。 如需詳細資訊, 請參閱[UriTypes 資料表](uritypes.md)。 <br/> |
   

