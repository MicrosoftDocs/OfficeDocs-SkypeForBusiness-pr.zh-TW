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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: '[使用者] 資料表是支援表格。 資料表中的每一筆記錄都儲存有關在資料庫中有記錄的通話或會話中涉及之一個使用者的相關資訊。'
ms.openlocfilehash: 21d03dc2214ac74188094c10a7b53ec84b8a51a9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814801"
---
# <a name="users-table"></a>Users 表格
 
[使用者] 資料表是支援表格。 資料表中的每一筆記錄都儲存有關在資料庫中有記錄的通話或會話中涉及之一個使用者的相關資訊。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> ||內部使用的時間戳記。  <br/> |
|**UserId** <br/> |int  <br/> |首選  <br/> |標識此使用者的唯一號碼。  <br/> |
|**UserUri** <br/> |Nvarchar （450）  <br/> | <br/> |使用者 URI。  <br/> |
|**TenantId** <br/> |int  <br/> |外  <br/> |此使用者的租使用者識別碼。 如需詳細資訊，請參閱[承租人資料表](tenants.md)。 <br/> |
|**UriTypeId** <br/> |int  <br/> |外  <br/> |此使用者的 URI 類型。 如需詳細資訊，請參閱[UriTypes 資料表](uritypes.md)。 <br/> |
   

