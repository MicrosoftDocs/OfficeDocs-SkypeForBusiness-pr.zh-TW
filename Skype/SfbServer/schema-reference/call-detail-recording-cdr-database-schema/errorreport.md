---
title: 商務用 Skype Server 2015 中的 ErrorReport 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
description: ErrorReport 資料表儲存所發生錯誤的相關資訊。 每一筆記錄都是一個錯誤發生。 錯誤是由在前端伺服器上執行或從用戶端傳送的 CDR 代理程式所捕獲。
ms.openlocfilehash: 80a6106bd7c6b87a7519bca6ce5cc72f45147ad6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192862"
---
# <a name="errorreport-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 ErrorReport 表格
 
ErrorReport 資料表儲存所發生錯誤的相關資訊。 每一筆記錄都是一個錯誤發生。 錯誤是由在前端伺服器上執行或從用戶端傳送的 CDR 代理程式所捕獲。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |首選  <br/> |發生錯誤的日期和時間。  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |首選  <br/> |識別錯誤報表的識別碼編號。 與**ErrorTime**搭配使用, 可唯一識別錯誤報表。 <br/> |
|**ErrorId** <br/> |int  <br/> |外  <br/> |錯誤類型的唯一識別碼。 如需詳細資訊, 請參閱[商務用 Skype Server 2015 中](errordef.md)的 [ErrorDef] 資料表。 <br/> |
|**FromUserId** <br/> |int  <br/> |外  <br/> |產生導致錯誤之要求的使用者。 如需詳細資訊, 請參閱 [[使用者] 表格](users.md)。 <br/> |
|**ToUserId** <br/> |int  <br/> |外  <br/> |導致錯誤之要求的目的地使用者。 如需詳細資訊, 請參閱 [[使用者] 表格](users.md)。 <br/> |
|**ConferenceUriId** <br/> |int  <br/> |外  <br/> |與錯誤相關的會議 URI。 如需詳細資訊, 請參閱[商務用 Skype Server 2015 中](conferenceuris.md)的 [ConferenceUris] 資料表。 通常, 如果 ConferenceUriId 不是 null, 則 FromUserId 或 ToUserId 將會是 null。 <br/> |
|**SessionIdTime** <br/> |datetime  <br/> |外  <br/> |與**SessionIdSeq**搭配使用, 可唯一識別會話。 如需詳細資訊, 請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |外  <br/> |識別會話的識別碼編號。 與**SessionIdTime**搭配使用, 可唯一識別會話。 如需詳細資訊, 請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**源** <br/> |int  <br/> |外  <br/> |傳送錯誤報表的伺服器 (如果報告是從伺服器元件傳送)。 如需詳細資訊, 請參閱 [[伺服器] 資料表](servers.md)。 <br/> 此欄位是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**ApplicationId** <br/> |int  <br/> |外  <br/> |傳送錯誤報表的伺服器 (如果報告是從伺服器元件傳送)。 如需詳細資訊, 請參閱[商務用 Skype Server 2015 中的 [應用程式] 資料表](application.md)。 <br/> 此欄位是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**MsDiagHeader** <br/> |影像  <br/> | <br/> |有關錯誤的詳細資訊。  <br/> 您可以使用下列語法, 將此資料轉換成文字格式:  <br/>  `cast(cast(Detail as varbinary(max)) as varchar(max))` <br/> |
|**ClientVersionId** <br/> |int  <br/> |外  <br/> |傳送錯誤報表的用戶端版本端點。 如需詳細資訊, 請參閱[商務用 Skype Server 2015 中](clientversions.md)的 [ClientVersions] 資料表。 <br/> |
|**IsCapturedByServer** <br/> |稍微  <br/> ||是由在前端伺服器上執行的 CDR 代理程式所捕獲, 或由用戶端傳送的錯誤報表。  <br/> |
|**標識** <br/> |Smallint  <br/> ||保留供日後使用。  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||與會議中所涉及之不同元件的加入時間資訊關聯的唯一識別碼。  <br/> 此欄位是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||特定元件加入會議所需的時間 (以毫秒為單位)。  <br/> 此欄位是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**ServerId** <br/> |int  <br/> |外  <br/> |代表產生錯誤報表之伺服器的完整功能變數名稱。  <br/> |
|**PoolId** <br/> |int  <br/> |外  <br/> |代表產生錯誤報表之池的完整功能變數名稱。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供監視服務內部使用。  <br/> 此欄位是在商務用 Skype Server 2015 中推出。  <br/> |
   

