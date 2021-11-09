---
title: FocusJoinsAndLeaves view
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 226460ef-766f-4d61-80cb-f332b65a210d
description: FocusJoinsAndLeaves 檢視可儲存會議的加入和離開相關資訊。 每次有使用者加入和離開某場會議時，此檢視中的該場會議都會有一筆撰寫記錄來表示。 此視圖已引進于 Microsoft Lync Server 2013。
ms.openlocfilehash: 8dcc82fe641b451190236f813f432c237e7fa2e2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845056"
---
# <a name="focusjoinsandleaves-view"></a>FocusJoinsAndLeaves view
 
FocusJoinsAndLeaves 檢視可儲存會議的加入和離開相關資訊。 每次有使用者加入和離開某場會議時，此檢視中的該場會議都會有一筆撰寫記錄來表示。 此視圖已引進于 Microsoft Lync Server 2013。
  
|**欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |會議執行個體的時間。 會與 SessionIdSeq 搭配使用，專門用於識別會議執行個體。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](conferences.md)的 [會議] 表格。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |用於辨識執行個體的 ID 號碼。 會與 SessionIDTime 搭配使用，專門用於識別會議執行個體。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](conferences.md)的 [會議] 表格。 <br/> |
|**UserUri** <br/> |Nvarchar (450)   <br/> |已擷取其加入/離開會議資訊之使用者的 URI。  <br/> |
|**UserUriType** <br/> |Nvarchar (256)   <br/> |已擷取其加入/離開會議資訊之使用者的 URI 類型。 如需詳細資訊，請參閱 [UriTypes 表格](uritypes.md) 。 <br/> |
|**UserTenant** <br/> |Nvarchar (256)   <br/> |已擷取其加入/離開會議資訊之使用者的租用戶。 如需詳細資訊，請參閱 [承租人資料表](tenants.md) 。 <br/> |
|**UserEndpointId** <br/> |唯一  <br/> |已擷取其加入/離開會議資訊之使用者的唯一識別碼。  <br/> |
|**UserClientVersion** <br/> |Nvarchar (256)   <br/> |已擷取其加入/離開會議資訊之使用者所用的用戶端版本。  <br/> |
|**UserClientType** <br/> |int  <br/> |已擷取其加入/離開會議資訊之使用者所用的用戶端。 如需詳細資訊，請參閱 [UserAgentDef 表格](useragentdef.md) 。 <br/> |
|**UserClientCategory** <br/> |Nvarchar (64)   <br/> |已擷取其加入/離開會議資訊之使用者所用的用戶端類別名稱。  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||
|**IsuserInternal** <br/> |位  <br/> |代表使用者是否為內部使用者的位元。  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |工作階段要求的時間。 與 SessionIdSeq 搭配使用，以唯一識別工作階段。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |若使用者同時登入多部電腦或裝置，會使用 UserInstance 專門識別使用者/裝置的組合。  <br/> |
|**DialogId** <br/> |Varchar (775)   <br/> |工作階段的 SIP 對話方塊識別碼，格式為：dialog;from-tag;to-tag。  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |使用者加入會議的時間。  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |使用者離開會議的時間。  <br/> |
|**UserRole** <br/> |Nvarchar (256)   <br/> |使用者在會議中的角色，例如簡報者或出席者。  <br/> |
   

