---
title: McuJoinsAndLeaves 視圖
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
ms.assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
description: '[McuJoinsAndLeaves] 視圖儲存有關使用者如何加入與離開一個會議服務器的資訊。 此視圖中的每一筆記錄都包含使用者加入或離開與會議服務器之一個組合的通話詳細資料。 此視圖已在 Microsoft Lync Server 2013 中推出。'
ms.openlocfilehash: 7a7569795d55620051e617d9312d87f3c96c628a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815091"
---
# <a name="mcujoinsandleaves-view"></a>McuJoinsAndLeaves 視圖
 
[McuJoinsAndLeaves] 視圖儲存有關使用者如何加入與離開一個會議服務器的資訊。 此視圖中的每一筆記錄都包含使用者加入或離開與會議服務器之一個組合的通話詳細資料。 此視圖已在 Microsoft Lync Server 2013 中推出。
  
|**左欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |會議實例的時間。 與 SessionIdSeq 搭配使用，可唯一識別會議實例。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](conferences.md)的 [會議] 表格。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |識別會議實例的識別碼編號。 與 SessionIdTime 搭配使用，可唯一識別會議實例。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](conferences.md)的 [會議] 表格。 <br/> |
|**McuUri** <br/> |Nvarchar （256）  <br/> |使用者所連接之會議服務器的 URI。  <br/> |
|**McuUriType** <br/> |Nvarchar （256）  <br/> |使用者所連接之會議服務器的 URI。 如需詳細資訊，請參閱[UriTypes 資料表](uritypes.md)。 <br/> |
|**UserUri** <br/> |Nvarchar （450）  <br/> |已捕獲會議服務器加入/離開資訊的使用者 URI。  <br/> |
|**UserUriType** <br/> |Nvarchar （256）  <br/> |已捕獲會議服務器加入/離開資訊之使用者的 URI 類型。 如需詳細資訊，請參閱[UriTypes 資料表](uritypes.md)。 <br/> |
|**UserTenant** <br/> |Nvarchar （256）  <br/> |已捕獲會議服務器加入/離開資訊之使用者的租使用者。 如需詳細資訊，請參閱[承租人資料表](tenants.md)。 <br/> |
|**UserClientVersion** <br/> |Nvarchar （256）  <br/> |已捕獲會議服務器加入/離開資訊的使用者所使用的用戶端版本。  <br/> |
|**UserClientType** <br/> |int  <br/> |已捕獲會議服務器加入/離開資訊的使用者所使用的用戶端。 如需詳細資訊，請參閱[UserAgentDef 資料表](useragentdef.md)。 <br/> |
|**UserClientCategory** <br/> |Nvarchar （64）  <br/> |已捕獲會議服務器加入/離開資訊之使用者所使用之用戶端的類別名稱。  <br/> |
|**McuUserInstance** <br/> |int  <br/> |針對同時登入多個裝置的使用者，唯一識別使用者/裝置的組合。  <br/> |
|**IsUserFromPstn** <br/> |稍微  <br/> |代表使用者是否為內部使用者的位。  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |會話要求的時間。 與 SessionIdSeq 搭配使用，可唯一識別會話。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |識別會話的識別碼編號。 與 SessionIdTime 搭配使用，可唯一識別會話。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**DialogId** <br/> |Varchar （775）  <br/> |會話的 SIP 對話方塊識別碼。 格式為：對話方塊; 從標籤; 到標籤。  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |使用者加入會議服務器的時間。  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |使用者離開會議服務器的時間。  <br/> |
   

