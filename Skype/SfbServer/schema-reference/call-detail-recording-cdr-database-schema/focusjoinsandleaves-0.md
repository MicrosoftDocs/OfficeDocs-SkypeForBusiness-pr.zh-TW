---
title: FocusJoinsAndLeaves 視圖
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 226460ef-766f-4d61-80cb-f332b65a210d
description: '[FocusJoinsAndLeaves] 視圖儲存有關加入會議的資訊，並留下一個會議的資訊。 每個會議都會在每次使用者加入並離開會議時所撰寫的記錄在這個視圖中顯示。 此視圖已在 Microsoft Lync Server 2013 中推出。'
ms.openlocfilehash: 771685a5546ef5b462a3ce3955406eb535f4c3eb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815191"
---
# <a name="focusjoinsandleaves-view"></a>FocusJoinsAndLeaves 視圖
 
[FocusJoinsAndLeaves] 視圖儲存有關加入會議的資訊，並留下一個會議的資訊。 每個會議都會在每次使用者加入並離開會議時所撰寫的記錄在這個視圖中顯示。 此視圖已在 Microsoft Lync Server 2013 中推出。
  
|**左欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |會議實例的時間。 與 SessionIdSeq 搭配使用，可唯一識別會議實例。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](conferences.md)的 [會議] 表格。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |識別會議實例的識別碼編號。 與 SessionIdTime 搭配使用，可唯一識別會議實例。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](conferences.md)的 [會議] 表格。 <br/> |
|**UserUri** <br/> |Nvarchar （450）  <br/> |已捕獲會議加入/離開資訊之使用者的 URI。  <br/> |
|**UserUriType** <br/> |Nvarchar （256）  <br/> |已捕獲會議加入/離開資訊之使用者的 URI 類型。 如需詳細資訊，請參閱[UriTypes 資料表](uritypes.md)。 <br/> |
|**UserTenant** <br/> |Nvarchar （256）  <br/> |已捕獲會議加入/離開資訊之使用者的租使用者。 如需詳細資訊，請參閱[承租人資料表](tenants.md)。 <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> |已捕獲會議加入/離開資訊之使用者的唯一識別碼。  <br/> |
|**UserClientVersion** <br/> |Nvarchar （256）  <br/> |已捕獲會議加入/離開資訊的使用者所使用的用戶端版本。  <br/> |
|**UserClientType** <br/> |int  <br/> |已捕獲會議加入/離開資訊的使用者所使用的用戶端。 如需詳細資訊，請參閱[UserAgentDef 資料表](useragentdef.md)。 <br/> |
|**UserClientCategory** <br/> |Nvarchar （64）  <br/> |已捕獲會議加入/離開資訊之使用者所使用之用戶端類別的名稱。  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||
|**IsuserInternal** <br/> |稍微  <br/> |代表使用者是否為內部使用者的位。  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |會話要求的時間。 與 SessionIdSeq 搭配使用，可唯一識別會話。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |如果使用者是同時在多部電腦或裝置上登入，則 UserInstance 會用來唯一識別使用者/裝置組合。  <br/> |
|**DialogId** <br/> |Varchar （775）  <br/> |會話的 SIP 對話方塊識別碼。 格式為：對話方塊; 從標籤; 到標籤。  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |使用者加入會議的時間。  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |使用者離開會議的時間。  <br/> |
|**UserRole** <br/> |Nvarchar （256）  <br/> |使用者在會議中的角色，例如 [簡報者] 或 [出席者]。  <br/> |
   

