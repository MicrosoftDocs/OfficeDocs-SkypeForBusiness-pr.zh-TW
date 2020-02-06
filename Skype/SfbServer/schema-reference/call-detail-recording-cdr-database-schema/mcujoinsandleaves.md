---
title: 商務用 Skype Server 2015 中的 McuJoinsAndLeaves 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
description: 此表格中的每筆記錄都包含有關使用者加入或離開與會議服務器之一個組合的呼叫詳細資料。 例如，如果使用者加入包含網路會議和音訊/視頻元素的會議，則會針對該使用者的網路會議加入建立一筆記錄，並會為使用者的音訊/視訊會議加入建立另一個記錄。
ms.openlocfilehash: 7eb2e8bccafcbd585c66cb77f2ba18a96c842d60
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815081"
---
# <a name="mcujoinsandleaves-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 McuJoinsAndLeaves 表格
 
此表格中的每筆記錄都包含有關使用者加入或離開與會議服務器之一個組合的呼叫詳細資料。 例如，如果使用者加入包含網路會議和音訊/視頻元素的會議，則會針對該使用者的網路會議加入建立一筆記錄，並會為使用者的音訊/視訊會議加入建立另一個記錄。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主要、外部  <br/> |會議實例的時間。 與**SessionIdSeq**搭配使用，可唯一識別會議實例。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](conferences.md)的 [會議] 表格。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主要、外部  <br/> |識別會議實例的識別碼編號。 與**SessionIdTime**搭配使用，可唯一識別會議實例。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](conferences.md)的 [會議] 表格。 <br/> |
|**UserId** <br/> |int  <br/> |主要、外部  <br/> |標識此使用者的唯一號碼。 如需詳細資訊，請參閱 [[使用者] 表格](users.md)。 <br/> |
|**McuUserInstance** <br/> |int  <br/> |首選  <br/> |如果使用者是一次在多部電腦或裝置上登入，McuUserInstance 會唯一識別使用者/裝置組合。  <br/> |
|**IsFromPstn** <br/> |稍微  <br/> | <br/> |使用者是否從 PSTN 加入。  <br/> |
|**McuId** <br/> |int  <br/> |主要、外部  <br/> |標識此會議服務器的唯一號碼。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](mcus.md)的 [Mcus] 資料表。 <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |外  <br/> |會話要求的時間。 與**SessionIdSeq**搭配使用，可唯一識別會話。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |外  <br/> |識別會話的識別碼編號。 與**SessionIdTime**搭配使用，可唯一識別會話。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |此使用者加入此會議服務器的時間。  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |此使用者離開此會議服務器的時間。  <br/> |
|**ClientVerId** <br/> |int  <br/> |外  <br/> |指定在會議中使用之用戶端軟體版本號碼的識別碼。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](clientversions.md)的 [ClientVersions] 資料表。 <br/> 此欄位是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供監視服務內部使用。  <br/> 此欄位是在商務用 Skype Server 2015 中推出。  <br/> |
   

