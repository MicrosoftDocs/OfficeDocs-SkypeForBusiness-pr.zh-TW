---
title: Tenants 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: '[承租人] 資料表是一個支援資料表, 可儲存各種租使用者的清單。 資料表中的每一筆記錄代表一個租使用者。'
ms.openlocfilehash: 58c8a2e36ed6d95da46523597b455d228a24586c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192786"
---
# <a name="tenants-table"></a>Tenants 表格
 
[承租人] 資料表是一個支援資料表, 可儲存各種租使用者的清單。 資料表中的每一筆記錄代表一個租使用者。
  
> [!NOTE]
> 在內部部署中, CDR 使用內傳內部租使用者識別碼來指示不同的驗證類型, 例如公用 IM 連線、同盟與匿名。 
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**TenantId** <br/> |int  <br/> |首選  <br/> |標識此租使用者識別碼的唯一號碼。  <br/> |
|**TenantKey** <br/> |Nvarchar (256)  <br/> || 允許的值: <br/>  00000000-0000-0000-0000-000000000000-企業 <br/>  00000000-0000-0000-0000-000000000001-同盟 <br/>  00000000-0000-0000-0000-000000000002-匿名 <br/>  00000000-0000-0000-0000-000000000003-公用 IM 連線 <br/> |
   

