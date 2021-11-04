---
title: 承租人表格
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: 承租人資料表是一種支援資料表，可儲存各種承租人的清單。 表格中的每筆記錄代表一位承租人。
ms.openlocfilehash: 6cb4c5edbf2751e06012628be48690c46592ca9a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759405"
---
# <a name="tenants-table"></a>承租人表格
 
承租人資料表是一種支援資料表，可儲存各種承租人的清單。 表格中的每筆記錄代表一位承租人。
  
> [!NOTE]
> 在內部部署中，CDR 使用內建承租人租使用者識別碼來表示不同的驗證類型，例如公用 IM 連線、同盟和匿名。 
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**TenantId** <br/> |int  <br/> |主要  <br/> |用於識別此租使用者識別碼的唯一號碼。  <br/> |
|**TenantKey** <br/> |Nvarchar (256)   <br/> || 允許的值： <br/>  00000000-0000-0000-0000-000000000000-Enterprise <br/>  00000000-0000-0000-0000-000000000001-同盟 <br/>  00000000-0000-0000-0000-000000000002-匿名 <br/>  00000000-0000-0000-0000-000000000003-公用 IM 連線能力 <br/> |
   

