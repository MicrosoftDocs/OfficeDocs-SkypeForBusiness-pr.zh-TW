---
title: 商務用 Skype Server 2015 中的 FocusJoinsAndLeaves 表格
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e6f0212c-67e9-4061-8720-d0296e855991
description: 此表格中的每一筆記錄都包含有關一位使用者的加入的 CDR 資訊，並留下一次會議的資訊。 每個會議都會在每次使用者加入和離開會議時，以一筆記錄呈現在此表格中。
ms.openlocfilehash: 607101a4bbcc5909ab8c9271a878a0b59164552d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62392285"
---
# <a name="focusjoinsandleaves-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 FocusJoinsAndLeaves 表格
 
此表格中的每一筆記錄都包含有關一位使用者的加入的 CDR 資訊，並留下一次會議的資訊。 每個會議都會在每次使用者加入和離開會議時，以一筆記錄呈現在此表格中。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主要，外部  <br/> |會議執行個體的時間。 與 **SessionIdSeq** 搭配使用，以唯一識別會議實例。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](conferences.md)的 [會議] 表格。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主要、外部  <br/> |用於辨識執行個體的 ID 號碼。 與 **SessionIdTime** 搭配使用，以唯一識別會議實例。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](conferences.md)的 [會議] 表格。 <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |主要，外部  <br/> |工作階段要求的時間。 其會與 **SessionIdSeq** 搭配使用，專門用於識別工作階段。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |主要，外部  <br/> |用來識別工作階段的識別碼。 會與 **SessionIdTime** 搭配使用，專門用於識別工作階段。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 <br/> |
|**UserId** <br/> |int  <br/> |Foreign  <br/> |用於識別此使用者的唯一號碼，參考來源為 [ [使用者] 表格](users.md)。  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||如果使用者同時在多部電腦或裝置上登入，則會使用 **UserInstance** 來唯一地識別使用者/裝置組合。 <br/> |
|**IsUserInternal** <br/> |位  <br/> | <br/> |使用者是否從內部登入。  <br/> |
|**UserRole** <br/> |int  <br/> | <br/> |此使用者在會議中的角色，例如簡報者或出席者。  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |此使用者加入會議的時間。  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |此使用者離開會議的時間。  <br/> |
|**ClientVerId** <br/> |int  <br/> |Foreign  <br/> |使用者的用戶端軟體版本，參考[商務用 Skype Server 2015 中的 ClientVersions 表格](clientversions.md)。  <br/> |
|**UserEndpointId** <br/> |唯一  <br/> ||會議中所使用之端點的全域唯一識別碼 (GUID) 。  <br/> 此欄位是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供監控服務內部使用。  <br/> 此欄位是在商務用 Skype Server 2015 中引入。  <br/> |
   

