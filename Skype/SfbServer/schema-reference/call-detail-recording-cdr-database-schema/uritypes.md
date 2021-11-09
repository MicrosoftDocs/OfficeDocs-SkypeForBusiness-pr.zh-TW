---
title: UriTypes 表格
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: UriTypes 表格包含在商務用 Skype Server 2015 中監控的不同 URI (統一資源識別項) 類型。
ms.openlocfilehash: ed0cc7e62aba47af6622f821af785d8daf571649
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60859760"
---
# <a name="uritypes-table"></a>UriTypes 表格
 
UriTypes 表格包含在商務用 Skype Server 2015 中監控的不同 URI (統一資源識別項) 類型。

在建立 CDR DB 時，會建立兩個代表 PhoneUri 和 UserUri 的記錄，並在該之後建立的記錄會以動態方式指派 UriTypeId。 
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |Tinyint  <br/> |主要  <br/> |指派給 URI 類型的唯一識別碼。  <br/> 可能的值-0 至255 |
|**UriType** <br/> |Nvarchar (256)   <br/> || 不同 URI 類型的描述。 下列值是預先指派的： <br/>  1-電話 Uri <br/>  0-使用者 Uri <br/> <br/>  其他可能類型包括： <br/>會議： applicationsharing <br/> 會議：音訊-影片<br/> 會議：聊天<br/>    會議：焦點<br/>   Mras<br/>
