---
title: UriTypes 表格
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
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: UriTypes 資料表包含在商務用 Skype Server 2015 中監控的不同 URI （統一資源識別項）類型。
ms.openlocfilehash: 81cd00503f88eac03f952b63ef7a3bd9464c1f51
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814841"
---
# <a name="uritypes-table"></a>UriTypes 表格
 
UriTypes 資料表包含在商務用 Skype Server 2015 中監控的不同 URI （統一資源識別項）類型。

在 CDR 資料庫建立之後，會建立兩筆記錄來代表 PhoneUri 和 UserUri，並在該記錄是動態指派的 UriTypeId。 
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |Tinyint  <br/> |首選  <br/> |指派給 URI 類型的唯一識別碼。  <br/> 可能的值-0 至255 |
|**UriType** <br/> |Nvarchar （256）  <br/> || 不同 URI 類型的描述。 下列值是預先指派的： <br/>  1-電話 Uri <br/>  0-使用者 Uri <br/> <br/>  其他可能的類型包括： <br/>會議： applicationsharing <br/> 會議：音訊-影片<br/> 會議：聊天<br/>    會議：焦點<br/>   mras<br/>
