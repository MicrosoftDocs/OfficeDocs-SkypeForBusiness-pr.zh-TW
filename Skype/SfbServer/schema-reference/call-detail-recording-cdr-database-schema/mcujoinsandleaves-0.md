---
title: McuJoinsAndLeaves view
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
description: McuJoinsAndLeaves 檢視會儲存使用者加入或離開一個會議伺服器的相關資訊。 這個檢視中的每筆記錄都包含一組使用者加入或離開會議伺服器的通話詳細資料。 此視圖已引進于 Microsoft Lync Server 2013。
ms.openlocfilehash: 50213655ad1dc48e85015d47ac4bd5bb450e05559556e0d6b4123dc2c9c32d69
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54318716"
---
# <a name="mcujoinsandleaves-view"></a>McuJoinsAndLeaves view
 
McuJoinsAndLeaves 檢視會儲存使用者加入或離開一個會議伺服器的相關資訊。 這個檢視中的每筆記錄都包含一組使用者加入或離開會議伺服器的通話詳細資料。 此視圖已引進于 Microsoft Lync Server 2013。
  
|**欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |會議執行個體的時間。 會與 SessionIdSeq 搭配使用，專門用於識別會議執行個體。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](conferences.md)的 [會議] 表格。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |用於辨識執行個體的 ID 號碼。 會與 SessionIDTime 搭配使用，專門用於識別會議執行個體。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](conferences.md)的 [會議] 表格。 <br/> |
|**McuUri** <br/> |Nvarchar (256)   <br/> |使用者連線至會議伺服器的 URI。  <br/> |
|**McuUriType** <br/> |Nvarchar (256)   <br/> |使用者連線至會議伺服器的 URI。 如需詳細資訊，請參閱 [UriTypes 表格](uritypes.md) 。 <br/> |
|**UserUri** <br/> |Nvarchar (450)   <br/> |擷取會議伺服器加入/離開資訊之使用者的 URI 。  <br/> |
|**UserUriType** <br/> |Nvarchar (256)   <br/> |擷取會議伺服器加入/離開資訊之使用者的 URI 類型。 如需詳細資訊，請參閱 [UriTypes 表格](uritypes.md) 。 <br/> |
|**UserTenant** <br/> |Nvarchar (256)   <br/> |擷取會議伺服器加入/離開資訊之使用者的租用戶。 如需詳細資訊，請參閱 [承租人資料表](tenants.md) 。 <br/> |
|**UserClientVersion** <br/> |Nvarchar (256)   <br/> |擷取會議伺服器加入/離開資訊之使用者所使用的用戶端版本。  <br/> |
|**UserClientType** <br/> |int  <br/> |擷取會議伺服器加入/離開資訊之使用者所使用的用戶端。 如需詳細資訊，請參閱 [UserAgentDef 表格](useragentdef.md) 。 <br/> |
|**UserClientCategory** <br/> |Nvarchar (64)   <br/> |擷取會議伺服器加入/離開資訊之使用者所使用的用戶端類別名稱。  <br/> |
|**McuUserInstance** <br/> |int  <br/> |唯一識別使用者同時登入多個裝置的使用者/裝置組合。  <br/> |
|**IsUserFromPstn** <br/> |位  <br/> |代表使用者是否為內部使用者的位元。  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |工作階段要求的時間。 與 SessionIdSeq 搭配使用，以唯一識別工作階段。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |識別工作階段的 ID 號碼。 與 SessionIdTime 搭配使用，以唯一識別工作階段。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 <br/> |
|**DialogId** <br/> |Varchar (775)   <br/> |工作階段的 SIP 對話方塊識別碼，格式為：dialog;from-tag;to-tag。  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |使用者加入會議伺服器的時間。  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |使用者離開會議伺服器的時間。  <br/> |
   

