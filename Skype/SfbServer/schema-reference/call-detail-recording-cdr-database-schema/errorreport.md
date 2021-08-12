---
title: 商務用 Skype Server 2015 中的 ErrorReport 表格
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
localization_priority: Normal
ms.assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
description: ErrorReport 表儲存發生錯誤的相關資訊。 每個記錄是一個錯誤發生。 這兩個錯誤是由前端伺服器上執行的 CDR 代理程式所捕獲，或是從用戶端傳送。
ms.openlocfilehash: 1cac143f50e361598c7985aa585485bd73c9aa79d3b47bd21fb0b70e75b9377e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303676"
---
# <a name="errorreport-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 ErrorReport 表格
 
ErrorReport 表儲存發生錯誤的相關資訊。 每個記錄是一個錯誤發生。 這兩個錯誤是由前端伺服器上執行的 CDR 代理程式所捕獲，或是從用戶端傳送。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |主要  <br/> |發生錯誤的日期和時間。  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |主要  <br/> |用以識別錯誤報表的 ID 號碼。 與 **ErrorTime** 搭配使用，以唯一識別錯誤報表。 <br/> |
|**ErrorId** <br/> |int  <br/> |Foreign  <br/> |錯誤類型的唯一識別碼。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的 ErrorDef 表格](errordef.md)。 <br/> |
|**FromUserId** <br/> |int  <br/> |Foreign  <br/> |產生導致錯誤之要求的使用者。 如需詳細資訊，請參閱 [Users 表格](users.md) 。 <br/> |
|**ToUserId** <br/> |int  <br/> |Foreign  <br/> |導致錯誤之要求的目的地使用者。 如需詳細資訊，請參閱 [Users 表格](users.md) 。 <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Foreign  <br/> |與錯誤相關的會議 URI。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的 ConferenceUris 表格](conferenceuris.md)。 一般來說，如果 ConferenceUriId 不是 null，則 FromUserId 或 ToUserId 將會是 null。 <br/> |
|**SessionIdTime** <br/> |datetime  <br/> |Foreign  <br/> |其會與 **SessionIdSeq** 搭配使用，專門用於識別工作階段。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Foreign  <br/> |用來識別工作階段的識別碼。 會與 **SessionIdTime** 搭配使用，專門用於識別工作階段。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 <br/> |
|**SourceId** <br/> |int  <br/> |Foreign  <br/> |傳送錯誤報表 (的伺服器，如果報告是從伺服器元件傳送) 中傳送。 如需詳細資訊，請參閱 [Servers 表格](servers.md) 。 <br/> 此欄位是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**ApplicationId** <br/> |int  <br/> |Foreign  <br/> |傳送錯誤報表 (的伺服器，如果報告是從伺服器元件傳送) 中傳送。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的應用程式表格](application.md)。 <br/> 此欄位是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**MsDiagHeader** <br/> |image  <br/> | <br/> |錯誤的詳細資訊。  <br/> 您可以使用下列語法將此資料轉換成文字格式：  <br/>  `cast(cast(Detail as varbinary(max)) as varchar(max))` <br/> |
|**ClientVersionId** <br/> |int  <br/> |Foreign  <br/> |傳送錯誤報表之端點的用戶端版本。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的 ClientVersions 表格](clientversions.md)。 <br/> |
|**IsCapturedByServer** <br/> |位  <br/> ||是由前端伺服器上執行的 CDR 代理程式所捕獲的錯誤報表，或是由用戶端所傳送的錯誤報表。  <br/> |
|**Flag** <br/> |Smallint  <br/> ||保留供日後使用。  <br/> |
|**TelemetryId** <br/> |唯一  <br/> ||與會議相關聯之不同元件的加入時間資訊的唯一識別碼。  <br/> 此欄位是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||特定元件加入會議所需的時間 (（毫秒）) 。  <br/> 此欄位是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**ServerId** <br/> |int  <br/> |Foreign  <br/> |代表產生錯誤報表之伺服器的完整功能變數名稱。  <br/> |
|**PoolId** <br/> |int  <br/> |Foreign  <br/> |代表產生錯誤報表之集區的完整功能變數名稱。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供監控服務內部使用。  <br/> 此欄位是在商務用 Skype Server 2015 中引入。  <br/> |
   

