---
title: 商務用 Skype Server 2015 中的 FocusJoinsAndLeaves 表格
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
ms.assetid: e6f0212c-67e9-4061-8720-d0296e855991
description: 此資料表中的每一筆記錄都包含一個使用者加入的 CDR 資訊，並留下一個會議的資訊。 每個會議都會在每次使用者加入並離開會議時，由一筆記錄在這個資料表中顯示。
ms.openlocfilehash: ac5e2b7316dd7d3477d76675d3a3960154b90f35
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815181"
---
# <a name="focusjoinsandleaves-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 FocusJoinsAndLeaves 表格
 
此資料表中的每一筆記錄都包含一個使用者加入的 CDR 資訊，並留下一個會議的資訊。 每個會議都會在每次使用者加入並離開會議時，由一筆記錄在這個資料表中顯示。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主要、外部  <br/> |會議實例的時間。 與**SessionIdSeq**搭配使用，可唯一識別會議實例。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](conferences.md)的 [會議] 表格。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主要、外部  <br/> |識別會議實例的識別碼編號。 與**SessionIdTime**搭配使用，可唯一識別會議實例。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](conferences.md)的 [會議] 表格。 <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |主要、外部  <br/> |會話要求的時間。 與**SessionIdSeq**搭配使用，可唯一識別會話。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |主要、外部  <br/> |識別會話的識別碼編號。 與**SessionIdTime**搭配使用，可唯一識別會話。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**UserId** <br/> |int  <br/> |外  <br/> |標識此使用者的唯一編號，從 [[使用者] 資料表](users.md)中引用。  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||如果使用者是同時在多部電腦或裝置上登入，則**UserInstance**會用來唯一識別使用者/裝置組合。 <br/> |
|**IsUserInternal** <br/> |稍微  <br/> | <br/> |使用者是否已從內部登入。  <br/> |
|**UserRole** <br/> |int  <br/> | <br/> |此使用者在會議中的角色，例如 [簡報者] 或 [出席者]。  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |此使用者加入會議的時間。  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |此使用者離開會議的時間。  <br/> |
|**ClientVerId** <br/> |int  <br/> |外  <br/> |使用者的用戶端軟體版本，[在商務用 Skype Server 2015 中參照至 ClientVersions 資料表](clientversions.md)。  <br/> |
|**UserEndpointId** <br/> |uniqueIdentifier  <br/> ||在會議中使用之端點的全域唯一識別碼（GUID）。  <br/> 此欄位是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供監視服務內部使用。  <br/> 此欄位是在商務用 Skype Server 2015 中推出。  <br/> |
   

