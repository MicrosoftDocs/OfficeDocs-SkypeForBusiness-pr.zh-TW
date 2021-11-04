---
title: 商務用 Skype Server 2015 中的 ErrorCategory 表格
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: ErrorCategory 表格包含每個商務用 Skype Server 2015 診斷分類的易記名稱。 商務用 Skype Server 2015 預設會使用下列類別：
ms.openlocfilehash: 19fa265b337f293656473aa24c85bb5fc22008de
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743909"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 ErrorCategory 表格
 
ErrorCategory 表格包含每個商務用 Skype Server 2015 診斷分類的易記名稱。 商務用 Skype Server 2015 預設會使用下列類別：
  
- 0 -- 成功
    
- 1--預期的失敗
    
- 2-未預期的失敗
    
此表格已引進 Microsoft Lync Server 2013。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**CategoryId** <br/> |Tinyint  <br/> |主要  <br/> |分類的唯一識別碼。  <br/> |
|**名稱** <br/> |Nvarchar (256)   <br/> || 指派給分類的值和易記名稱。允許的值為： <br/>  0 -- 成功 <br/>  1--預期的失敗 <br/>  2-未預期的失敗 <br/> |
   

