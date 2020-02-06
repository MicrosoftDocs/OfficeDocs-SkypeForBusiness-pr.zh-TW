---
title: ConferenceSessionDetails 視圖
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
ms.assetid: 5858c84d-baed-421d-ad1d-3726e150e256
description: '[ConferenceSessionDetails] 視圖儲存有關多方會話的資訊。 每個記錄代表一個會議會話，可能是與焦點進行的會話，或是與特定會議服務器的會話。 此視圖已在 Microsoft Lync Server 2013 中推出。'
ms.openlocfilehash: 3dc345c10836a34f99baa4d6a088ab152b23427d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815331"
---
# <a name="conferencesessiondetails-view"></a>ConferenceSessionDetails 視圖
 
[ConferenceSessionDetails] 視圖儲存有關多方會話的資訊。 每個記錄代表一個會議會話，可能是與焦點進行的會話，或是與特定會議服務器的會話。 此視圖已在 Microsoft Lync Server 2013 中推出。
  
|**左欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |會話要求的時間。 與 SessionIdSeq 搭配使用，可唯一識別會話。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |識別會話的識別碼編號。 與 SessionIdTime 搭配使用，可唯一識別會話。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**InviteTime** <br/> |datetime  <br/> |第一次邀請要求的時間。 這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。 如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。  <br/> |
|**ConferenceUri** <br/> |Nvarchar （450）  <br/> |會議的 URI。  <br/> |
|**ConferenceUriType** <br/> |Nvarchar （256）  <br/> |會議 URI 的類型。 如需詳細資訊，請參閱[UriTypes 資料表](uritypes.md)。 <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> |區分週期性會議實例的識別碼。 每個週期性會議實例都有相同的 ConferenceURI，但有不同的 ConfInstance 值。  <br/> |
|**McuConferenceUri** <br/> |Nvarchar （450）  <br/> |會議服務器的 URI。  <br/> |
|**McuConferenceUriType** <br/> |Nvarchar （256）  <br/> |會議服務器 URI 的類型。 如需詳細資訊，請參閱[UriTypes 資料表](uritypes.md)。 <br/> |
|**UserUri** <br/> |Nvarchar （450）  <br/> |會話中所涉及之使用者的 URI。  <br/> |
|**UserUriType** <br/> |Nvarchar （256）  <br/> |屬於會話一部分之使用者的 URI 類型。 如需詳細資訊，請參閱[UriTypes 資料表](uritypes.md)。 <br/> |
|**UserTenant** <br/> |Nvarchar （256）  <br/> |屬於會話一部分之使用者的租使用者。 如需詳細資訊，請參閱[承租人資料表](tenants.md)。 <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> |會話中的使用者的唯一識別碼。  <br/> |
|**EndTime** <br/> |datetime  <br/> |會話的結束時間。  <br/> |
|**ConferenceClientVersion** <br/> |Nvarchar （256）  <br/> |[會議服務器] 版本。  <br/> |
|**ConferenceClientType** <br/> |int  <br/> |會議服務器的類型。 如需詳細資訊，請參閱[UserAgentDef 資料表](useragentdef.md)。 <br/> |
|**ConferenceCategory** <br/> |Nvarchar （64）  <br/> |[會議服務器] 類別。  <br/> |
|**UserClientVersion** <br/> |Nvarchar （256）  <br/> |參與會話之使用者使用的用戶端版本。  <br/> |
|**UserClientType** <br/> |int  <br/> |參與會話的使用者所使用的用戶端。 如需詳細資訊，請參閱[UserAgentDef 資料表](useragentdef.md)。 <br/> |
|**UserClientCategory** <br/> |Nvarchar （64）  <br/> |參與會話之使用者所使用之用戶端類別的名稱。  <br/> |
|**OnBehalfOfUri** <br/> |Nvarchar （450）  <br/> |代表其啟動會話的使用者 URI。  <br/> |
|**OnBehalfOfUriType** <br/> |Nvarchar （256）  <br/> |啟動會話所代表之使用者的 URI 類型。 如需詳細資訊，請參閱[UriTypes 資料表](uritypes.md)。 <br/> |
|**OnBehalfOfTenant** <br/> |Nvarchar （256）  <br/> |代表啟動會話的使用者租使用者。 如需詳細資訊，請參閱[承租人資料表](tenants.md)。 <br/> |
|**ReferredByUri** <br/> |Nvarchar （450）  <br/> |參照會話之使用者的 URI。  <br/> |
|**ReferredByUriType** <br/> |Nvarchar （256）  <br/> |參照會話之使用者的 URI 類型。 如需詳細資訊，請參閱[UriTypes 資料表](uritypes.md)。 <br/> |
|**ReferredByUriTenant** <br/> |Nvarchar （256）  <br/> |參照會話之使用者的租使用者。 如需詳細資訊，請參閱[承租人資料表](tenants.md)。 <br/> |
|**DialogId** <br/> |varstring （775）  <br/> |SIP 對話方塊識別碼。 格式為  <br/> :d ialog; 從標籤; 到標籤  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |[識別碼] 編號，找出目前會話所取代的對話方塊。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |識別會話的識別碼編號。 與 ReplaceDialogIdTime 搭配使用，可唯一識別此會話所取代的會話。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**ReplacesDialogId** <br/> |Varchar （775）  <br/> |[SIP] 對話方塊識別碼，該會話會取代。 的格式為：  <br/> 對話方塊; 從標籤; 到標籤  <br/> |
|**IsStartedByConfServer** <br/> |稍微  <br/> |指出會話是否由會議服務器啟動。  <br/> |
|**IsEndedByConfServer** <br/> |稍微  <br/> |指出會議服務器是否已結束會話。  <br/> |
|**IsUserInternal** <br/> |稍微  <br/> |指示使用者是否從內部網路登入。  <br/> |
|**ResponseTime** <br/> |datetime  <br/> |第一次邀請訊息的回復時間。 這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。 如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。  <br/> |
|**ResponseCode** <br/> |int  <br/> |SIP 回應程式碼加入會話邀請。 這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。 如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。  <br/> |
|**DiagnosticId** <br/> |int  <br/> |從會話 SIP 標頭捕獲的診斷 ID。  <br/> |
|**ContentType** <br/> |Nvarchar （256）  <br/> |會話的內容類型。  <br/> |
|**FrontEnd** <br/> |Nvarchar （256）  <br/> |捕獲會話資料的前端伺服器 FQDN。  <br/> |
|**集區** <br/> |Nvarchar （256）  <br/> |捕獲會話資料之池的 FQDN。  <br/> |
|**MediationServer** <br/> |Nvarchar （256）  <br/> |參與會話的使用者所使用的中繼伺服器。  <br/> |
|**關** <br/> |Nvarchar （256）  <br/> |參與會話的使用者所使用的閘道。  <br/> |
|**EdgeServer** <br/> |Nvarchar （256）  <br/> |參與會話之使用者所使用的邊緣伺服器 FQDN。  <br/> |
|**UserFlag** <br/> |Smallint  <br/> |指出參與會話之使用者的屬性。 允許下列屬性定義：  <br/> 0x01-與桌面電話整合  <br/> |
|**CallFlag** <br/> |Smallint  <br/> |指出通話屬性。 允許下列屬性定義：  <br/> 0x01-重試 Session0  <br/> x02-代表回應群組發出的代理通話  <br/> |
   

