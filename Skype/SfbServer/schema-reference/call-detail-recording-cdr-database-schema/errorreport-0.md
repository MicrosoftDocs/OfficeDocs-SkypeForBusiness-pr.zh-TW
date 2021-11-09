---
title: ErrorReport view
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
ms.assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
description: ErrorReport view 會儲存所報告錯誤的相關資訊。 每個記錄是一個錯誤發生。 這兩個錯誤是由前端伺服器上執行的 CDR 代理程式所捕獲，或是從用戶端傳送。 此視圖已引進于 Microsoft Lync Server 2013。
ms.openlocfilehash: 5a35cc8b3a726549be7de10259c7e59a67ca5500
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60852927"
---
# <a name="errorreport-view"></a>ErrorReport view
 
ErrorReport view 會儲存所報告錯誤的相關資訊。 每個記錄是一個錯誤發生。 這兩個錯誤是由前端伺服器上執行的 CDR 代理程式所捕獲，或是從用戶端傳送。 此視圖已引進于 Microsoft Lync Server 2013。
  
|**欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |發生錯誤的時間。 與 ErrorReportSeq 搭配使用，以唯一識別錯誤。  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |用以識別錯誤的 ID 號碼。 與 ErrorTime 搭配使用，以唯一識別錯誤。  <br/> |
|**MsDiagId** <br/> |int  <br/> |錯誤報表的診斷識別碼。  <br/> |
|**FromUri** <br/> |Nvarchar (450)   <br/> |產生錯誤之使用者的 URI。  <br/> |
|**FromUriType** <br/> |Nvarchar (256)   <br/> |產生錯誤之使用者的 URI 類型。 如需詳細資訊，請參閱 [UriTypes 表格](uritypes.md) 。 <br/> |
|**FromTenant** <br/> |Nvarchar (256)   <br/> |產生錯誤之使用者的租使用者。 如需詳細資訊，請參閱 [承租人資料表](tenants.md) 。 <br/> |
|**ToUri** <br/> |Nvarchar (450)   <br/> |錯誤報表之目標之使用者的 URI。  <br/> |
|**ToUriType** <br/> |Nvarchar (256)   <br/> |錯誤報表目標使用者的 URI 類型。 如需詳細資訊，請參閱＜UriTypes Table＞。  <br/> |
|**ToTenant** <br/> |Nvarchar (256)   <br/> |目標為錯誤報表之使用者的租使用者。 如需詳細資訊，請參閱 [承租人資料表](tenants.md) 。 <br/> |
|**ConferenceUri** <br/> |Nvarchar (450)   <br/> |錯誤報表目標的會議 URI。  <br/> |
|**ConferenceUriType** <br/> |Nvarchar (256)   <br/> |錯誤報表目標的會議 URI 類型。 如需詳細資訊，請參閱 [UriTypes 表格](uritypes.md) 。 <br/> |
|**SessionIdTime** <br/> |datetime  <br/> |發出錯誤報表之會話要求的時間。 與 SessionIdSeq 搭配使用，以唯一識別工作階段。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |識別產生錯誤報表之會話要求的識別碼編號。 與 SessionIdTime 搭配使用，以唯一識別工作階段。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 <br/> |
|**DialogId** <br/> |varstring (775)   <br/> |發出錯誤之會話的 SIP 對話方塊識別碼。 格式為：  <br/> dialog; 從-標籤; to-標記  <br/> 您可以使用下列語法將此資料轉換成文字格式：  <br/> cast (cast (ExternalId 為 Varbinary (max) ) 為 Varchar (max) )   <br/> |
|**Microsoft.rtc.management.writableconfig.policy.clientversion.rule** <br/> |Nvarchar (256)   <br/> |產生錯誤之使用者所使用的用戶端版本。  <br/> |
|**ClientType** <br/> |int  <br/> |產生錯誤之使用者所使用的用戶端。 如需詳細資訊，請參閱 [UserAgentDef 表格](useragentdef.md) 。 <br/> |
|**ClientCategory** <br/> |Nvarchar (64)   <br/> |產生錯誤之使用者所使用的用戶端類別名稱。  <br/> |
|**Source** <br/> |Nvarchar (256)   <br/> |起源錯誤的伺服器名稱 (如果報告是從伺服器元件傳送) 中。  <br/> |
|**應用程式** <br/> |Nvarchar (256)   <br/> |起源錯誤的應用程式名稱 (如果報告是從伺服器元件傳送) 。  <br/> |
|**ResponseCode** <br/> |int  <br/> |包含錯誤報表之 SIP 郵件會話的 SIP 回應碼。  <br/> |
|**RequestType** <br/> |Varchar (max)   <br/> |失敗的要求類型。  <br/> |
|**ContentType** <br/> |Varchar (max)   <br/> |失敗之要求的內容類型。  <br/> |
|**CallType** <br/> |Nvarchar (256)   <br/> |會話類型。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的 CallType 表格](calltype.md)。 <br/> |
|**TelemetryId** <br/> |唯一  <br/> |與會議相關聯之不同元件的加入時間資訊的唯一識別碼。  <br/> |
|**SetupTime** <br/> |int  <br/> |特定元件加入會議所需的時間 (（毫秒）) 。  <br/> |
|**IsCapturedByServer** <br/> |位  <br/> |會指出是否是由前端伺服器上執行的 CDR 代理程式所捕獲，或是由用戶端所傳送的錯誤報表。  <br/> |
|**Flag** <br/> |Smallint  <br/> |保留供日後使用。  <br/> |
|**MsDiagHeader** <br/> |Varchar (max)   <br/> |有關錯誤的其他資訊。  <br/> |
|**FrontEnd** <br/> |Nvarchar  <br/> |提交報告之前端伺服器的完整功能變數名稱。  <br/> |
|**集區** <br/> |Nvarchar  <br/> |包含提交報告之前端伺服器集區的完整功能變數名稱。  <br/> |
   

