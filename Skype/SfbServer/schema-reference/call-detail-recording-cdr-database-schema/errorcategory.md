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
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'ErrorCategory 表格包含每個商務用 Skype Server 2015 診斷分類的易記名稱。 根據預設, 商務用 Skype Server 2015 使用下列分類:'
ms.openlocfilehash: bafeb75ee9e6ae0f96b08e26909828f1b36f7e7b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192865"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 ErrorCategory 表格
 
ErrorCategory 表格包含每個商務用 Skype Server 2015 診斷分類的易記名稱。 根據預設, 商務用 Skype Server 2015 使用下列分類:
  
- 0--成功
    
- 1--預期失敗
    
- 2-意外失敗
    
此表格是在 Microsoft Lync Server 2013 中推出。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**Id** <br/> |Tinyint  <br/> |首選  <br/> |分類的唯一識別碼。  <br/> |
|**名稱** <br/> |Nvarchar (256)  <br/> || 指派給分類的值和易記名稱。 允許的值為： <br/>  0--成功 <br/>  1--預期失敗 <br/>  2-意外失敗 <br/> |
   

