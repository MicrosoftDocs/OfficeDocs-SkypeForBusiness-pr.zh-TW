---
title: 商務用 Skype Server 2015 中的 ErrorCategory 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: ErrorCategory 表格包含每個商務用 Skype Server 2015 診斷分類的易記名稱。 根據預設，商務用 Skype Server 2015 使用下列分類：
ms.openlocfilehash: f3ad3f86a382b900d53c5e86140a46d7f32ca1c1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815251"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 ErrorCategory 表格
 
ErrorCategory 表格包含每個商務用 Skype Server 2015 診斷分類的易記名稱。 根據預設，商務用 Skype Server 2015 使用下列分類：
  
- 0--成功
    
- 1--預期失敗
    
- 2-意外失敗
    
此表格是在 Microsoft Lync Server 2013 中推出。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**Id** <br/> |Tinyint  <br/> |首選  <br/> |分類的唯一識別碼。  <br/> |
|**名稱** <br/> |Nvarchar （256）  <br/> || 指派給分類的值和易記名稱。 允許的值為： <br/>  0--成功 <br/>  1--預期失敗 <br/>  2-意外失敗 <br/> |
   

