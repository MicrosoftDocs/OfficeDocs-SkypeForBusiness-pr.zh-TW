---
title: 商務用 Skype Server 2015 中的 McuJoinsAndLeaves 表格
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
description: 此表格中的每一筆記錄都包含有關使用者加入或離開和會議服務器之一種結合的呼叫詳細資料。 例如，如果使用者加入包含 web 會議及音訊/視頻元素的會議，則會為該使用者的 web 會議加入建立一個記錄，並為使用者的音訊/視訊會議加入建立另一筆記錄。
ms.openlocfilehash: 5d01781dd0d16abb3f03cdc8f6021981e7ebfff7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58629465"
---
# <a name="mcujoinsandleaves-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 McuJoinsAndLeaves 表格
 
此表格中的每一筆記錄都包含有關使用者加入或離開和會議服務器之一種結合的呼叫詳細資料。 例如，如果使用者加入包含 web 會議及音訊/視頻元素的會議，則會為該使用者的 web 會議加入建立一個記錄，並為使用者的音訊/視訊會議加入建立另一筆記錄。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主要，外部  <br/> |會議執行個體的時間。 與 **SessionIdSeq** 搭配使用，以唯一識別會議實例。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](conferences.md)的 [會議] 表格。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主要、外部  <br/> |用於辨識執行個體的 ID 號碼。 與 **SessionIdTime** 搭配使用，以唯一識別會議實例。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](conferences.md)的 [會議] 表格。 <br/> |
|**UserId** <br/> |int  <br/> |主要、外部  <br/> |用於識別此使用者的唯一號碼。 如需詳細資訊，請參閱 [Users 表格](users.md) 。 <br/> |
|**McuUserInstance** <br/> |int  <br/> |主要  <br/> |如果使用者同時在多部電腦或裝置上登入，McuUserInstance 會唯一識別使用者/裝置組合。  <br/> |
|**IsFromPstn** <br/> |位  <br/> | <br/> |使用者是否從 PSTN 加入。  <br/> |
|**McuId** <br/> |int  <br/> |主要、外部  <br/> |用於識別此會議服務器的唯一號碼。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的 Mcus 表格](mcus.md)。 <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Foreign  <br/> |工作階段要求的時間。 其會與 **SessionIdSeq** 搭配使用，專門用於識別工作階段。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Foreign  <br/> |用來識別工作階段的識別碼。 會與 **SessionIdTime** 搭配使用，專門用於識別工作階段。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |此使用者加入此會議服務器的時間。  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |此使用者離開此會議服務器的時間。  <br/> |
|**ClientVerId** <br/> |int  <br/> |Foreign  <br/> |指定會議中用戶端軟體使用版本號碼的識別碼。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的 ClientVersions 表格](clientversions.md)。 <br/> 此欄位是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供監控服務內部使用。  <br/> 此欄位是在商務用 Skype Server 2015 中引入。  <br/> |
   

