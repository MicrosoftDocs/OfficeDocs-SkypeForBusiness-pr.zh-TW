---
title: Users 表格
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
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: '[使用者] 表格是支援表格。 資料表中的每一筆記錄都儲存在具有資料庫中記錄的通話或會話中的一個使用者相關資訊。'
ms.openlocfilehash: 66f3e1247d29969ecef36a5d6247510b5eae022c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62389775"
---
# <a name="users-table"></a>Users 表格
 
[使用者] 表格是支援表格。 資料表中的每一筆記錄都儲存在具有資料庫中記錄的通話或會話中的一個使用者相關資訊。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> ||內部使用的時間戳記。  <br/> |
|**UserId** <br/> |int  <br/> |主要  <br/> |用於識別此使用者的唯一號碼。  <br/> |
|**UserUri** <br/> |Nvarchar (450)   <br/> | <br/> |使用者 URI。  <br/> |
|**TenantId** <br/> |int  <br/> |Foreign  <br/> |此使用者的租使用者識別碼。 如需詳細資訊，請參閱 [承租人資料表](tenants.md) 。 <br/> |
|**UriTypeId** <br/> |int  <br/> |Foreign  <br/> |此使用者的 URI 類型。 如需詳細資訊，請參閱 [UriTypes 表格](uritypes.md) 。 <br/> |
   

