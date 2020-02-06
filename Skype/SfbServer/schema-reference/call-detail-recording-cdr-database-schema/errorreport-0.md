---
title: ErrorReport 視圖
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
ms.assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
description: '[ErrorReport] 視圖儲存所報告錯誤的相關資訊。 每一筆記錄都是一個錯誤發生。 錯誤是由在前端伺服器上執行或從用戶端傳送的 CDR 代理程式所捕獲。 此視圖已在 Microsoft Lync Server 2013 中推出。'
ms.openlocfilehash: d51b085d5dabb8a6ae0dc367b23dd23a1702174e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815241"
---
# <a name="errorreport-view"></a>ErrorReport 視圖
 
[ErrorReport] 視圖儲存所報告錯誤的相關資訊。 每一筆記錄都是一個錯誤發生。 錯誤是由在前端伺服器上執行或從用戶端傳送的 CDR 代理程式所捕獲。 此視圖已在 Microsoft Lync Server 2013 中推出。
  
|**左欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |發生錯誤的時間。 與 ErrorReportSeq 搭配使用，可唯一識別錯誤。  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |識別錯誤的識別碼號碼。 與 ErrorTime 搭配使用，可唯一識別錯誤。  <br/> |
|**MsDiagId** <br/> |int  <br/> |錯誤報表的診斷 ID。  <br/> |
|**FromUri** <br/> |Nvarchar （450）  <br/> |產生錯誤之使用者的 URI。  <br/> |
|**FromUriType** <br/> |Nvarchar （256）  <br/> |產生錯誤之使用者的 URI 類型。 如需詳細資訊，請參閱[UriTypes 資料表](uritypes.md)。 <br/> |
|**FromTenant** <br/> |Nvarchar （256）  <br/> |產生錯誤之使用者的租使用者。 如需詳細資訊，請參閱[承租人資料表](tenants.md)。 <br/> |
|**ToUri** <br/> |Nvarchar （450）  <br/> |錯誤報表目標使用者的 URI。  <br/> |
|**ToUriType** <br/> |Nvarchar （256）  <br/> |錯誤報表目標使用者的 URI 類型。 如需詳細資訊，請參閱 UriTypes 資料表。  <br/> |
|**ToTenant** <br/> |Nvarchar （256）  <br/> |針對錯誤報表的目標使用者的租使用者。 如需詳細資訊，請參閱[承租人資料表](tenants.md)。 <br/> |
|**ConferenceUri** <br/> |Nvarchar （450）  <br/> |錯誤報表目標的會議 URI。  <br/> |
|**ConferenceUriType** <br/> |Nvarchar （256）  <br/> |錯誤報表目標會議的 URI 類型。 如需詳細資訊，請參閱[UriTypes 資料表](uritypes.md)。 <br/> |
|**SessionIdTime** <br/> |datetime  <br/> |產生錯誤報表之會話要求的時間。 與 SessionIdSeq 搭配使用，可唯一識別會話。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |識別產生錯誤報表之會話要求的識別碼編號。 與 SessionIdTime 搭配使用，可唯一識別會話。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**DialogId** <br/> |varstring （775）  <br/> |產生錯誤之會話的 SIP 對話方塊識別碼。 格式為：  <br/> 對話方塊; 從標籤; 到標籤  <br/> 您可以使用下列語法，將此資料轉換成文字格式：  <br/> cast （轉換（ExternalId 為 Varbinary （max））做為 Varchar （max））  <br/> |
|**ClientVersion** <br/> |Nvarchar （256）  <br/> |產生錯誤的使用者所使用的用戶端版本。  <br/> |
|**ClientType** <br/> |int  <br/> |產生錯誤的使用者所使用的用戶端。 如需詳細資訊，請參閱[UserAgentDef 資料表](useragentdef.md)。 <br/> |
|**ClientCategory** <br/> |Nvarchar （64）  <br/> |產生錯誤之使用者所使用之用戶端類別的名稱。  <br/> |
|**從源** <br/> |Nvarchar （256）  <br/> |產生錯誤的伺服器名稱（如果報表是從伺服器元件傳送）。  <br/> |
|**應用程式** <br/> |Nvarchar （256）  <br/> |產生錯誤的應用程式名稱（如果報表是從伺服器元件傳送）。  <br/> |
|**ResponseCode** <br/> |int  <br/> |SIP 回應程式碼加入包含錯誤報表之 SIP 訊息的會話中。  <br/> |
|**RequestType** <br/> |Varchar （max）  <br/> |失敗的要求類型。  <br/> |
|**ContentType** <br/> |Varchar （max）  <br/> |失敗之要求的內容類型。  <br/> |
|**CallType** <br/> |Nvarchar （256）  <br/> |會話類型。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](calltype.md)的 [CallType] 資料表。 <br/> |
|**TelemetryId** <br/> |uniqueidentifier  <br/> |與會議中所涉及之不同元件的加入時間資訊關聯的唯一識別碼。  <br/> |
|**SetupTime** <br/> |int  <br/> |特定元件加入會議所需的時間（以毫秒為單位）。  <br/> |
|**IsCapturedByServer** <br/> |稍微  <br/> |指示錯誤報表是由在前端伺服器上執行的 CDR 代理程式捕獲，還是由用戶端傳送。  <br/> |
|**標識** <br/> |Smallint  <br/> |保留供日後使用。  <br/> |
|**MsDiagHeader** <br/> |Varchar （max）  <br/> |錯誤的其他相關資訊。  <br/> |
|**FrontEnd** <br/> |Nvarchar  <br/> |提交報表之前端伺服器的完整功能變數名稱。  <br/> |
|**集區** <br/> |Nvarchar  <br/> |包含提交報表之前端伺服器之池的完整功能變數名稱。  <br/> |
   

