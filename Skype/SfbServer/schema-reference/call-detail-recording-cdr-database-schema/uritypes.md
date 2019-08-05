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
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: UriTypes 資料表包含在商務用 Skype Server 2015 中監控的不同 URI (統一資源識別項) 類型。
ms.openlocfilehash: 5ad8e1d0432aff3278f897fbe82d3759ad3c95e1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192785"
---
# <a name="uritypes-table"></a>UriTypes 表格
 
UriTypes 資料表包含在商務用 Skype Server 2015 中監控的不同 URI (統一資源識別項) 類型。

在 CDR 資料庫建立之後, 會建立兩筆記錄來代表 PhoneUri 和 UserUri, 並在該記錄是動態指派的 UriTypeId。 
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |Tinyint  <br/> |首選  <br/> |指派給 URI 類型的唯一識別碼。  <br/> 可能的值-0 至255 |
|**UriType** <br/> |Nvarchar (256)  <br/> || 不同 URI 類型的描述。 下列值是預先指派的: <br/>  1-電話 Uri <br/>  0-使用者 Uri <br/> <br/>  其他可能的類型包括: <br/>會議: applicationsharing <br/> 會議: 音訊-影片<br/> 會議: 聊天<br/>    會議: 焦點<br/>   mras<br/>
