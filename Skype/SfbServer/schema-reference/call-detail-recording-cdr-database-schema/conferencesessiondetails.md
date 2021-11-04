---
title: ConferenceSessionDetails view
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 5858c84d-baed-421d-ad1d-3726e150e256
description: ConferenceSessionDetails 檢視會儲存多方成員工作階段的相關資訊。 每筆記錄都代表一個會議工作階段，它可以是有「焦點」的工作階段，或是特定會議伺服器的工作階段。 此視圖已引進于 Microsoft Lync Server 2013。
ms.openlocfilehash: cebd4acd218d551f7f43dba39334c342441e216a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771899"
---
# <a name="conferencesessiondetails-view"></a>ConferenceSessionDetails view
 
ConferenceSessionDetails 檢視會儲存多方成員工作階段的相關資訊。 每筆記錄都代表一個會議工作階段，它可以是有「焦點」的工作階段，或是特定會議伺服器的工作階段。 此視圖已引進于 Microsoft Lync Server 2013。
  
|**欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |工作階段要求的時間。 與 SessionIdSeq 搭配使用，以唯一識別工作階段。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |識別工作階段的 ID 號碼。 與 SessionIdTime 搭配使用，以唯一識別工作階段。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 <br/> |
|**InviteTime** <br/> |datetime  <br/> |第一個 INVITE 要求的時間。此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。  <br/> |
|**ConferenceUri** <br/> |Nvarchar (450)   <br/> |會議的 URI。  <br/> |
|**ConferenceUriType** <br/> |Nvarchar (256)   <br/> |會議 URI 的類型。 如需詳細資訊，請參閱 [UriTypes 表格](uritypes.md) 。 <br/> |
|**ConfInstance** <br/> |唯一  <br/> |可區分週期性會議的執行個體的識別碼。每個週期性會議執行個體都會有相同的 ConferenceURI 且不同的 ConfInstance 值。  <br/> |
|**McuConferenceUri** <br/> |Nvarchar (450)   <br/> |會議伺服器的 URI。  <br/> |
|**McuConferenceUriType** <br/> |Nvarchar (256)   <br/> |會議伺服器 URI 的類型。 如需詳細資訊，請參閱 [UriTypes 表格](uritypes.md) 。 <br/> |
|**UserUri** <br/> |Nvarchar (450)   <br/> |工作階段中所含之使用者的 URI。  <br/> |
|**UserUriType** <br/> |Nvarchar (256)   <br/> |屬於工作階段一部分之使用者的 URI 類型。 如需詳細資訊，請參閱 [UriTypes 表格](uritypes.md) 。 <br/> |
|**UserTenant** <br/> |Nvarchar (256)   <br/> |屬於工作階段一部分之使用者的租用戶。 如需詳細資訊，請參閱 [承租人資料表](tenants.md) 。 <br/> |
|**UserEndpointId** <br/> |唯一  <br/> |屬於工作階段一部分之使用者的唯一識別碼。  <br/> |
|**EndTime** <br/> |datetime  <br/> |工作階段的結束時間。  <br/> |
|**ConferenceClientVersion** <br/> |Nvarchar (256)   <br/> |會議伺服器的版本。  <br/> |
|**ConferenceClientType** <br/> |int  <br/> |會議伺服器的類型。 如需詳細資訊，請參閱 [UserAgentDef 表格](useragentdef.md) 。 <br/> |
|**ConferenceCategory** <br/> |Nvarchar (64)   <br/> |會議伺服器類別。  <br/> |
|**UserClientVersion** <br/> |Nvarchar (256)   <br/> |參與工作階段之使用者所使用的用戶端版本。  <br/> |
|**UserClientType** <br/> |int  <br/> |參與工作階段之使用者所使用的用戶端。 如需詳細資訊，請參閱 [UserAgentDef 表格](useragentdef.md) 。 <br/> |
|**UserClientCategory** <br/> |Nvarchar (64)   <br/> |屬於工作階段一部分之使用者所使用的用戶端類別名稱。  <br/> |
|**OnBehalfOfUri** <br/> |Nvarchar (450)   <br/> |代表啟動工作階段之使用者的 URI。  <br/> |
|**OnBehalfOfUriType** <br/> |Nvarchar (256)   <br/> |代表啟動工作階段之使用者的 URI 類型。 如需詳細資訊，請參閱 [UriTypes 表格](uritypes.md) 。 <br/> |
|**OnBehalfOfTenant** <br/> |Nvarchar (256)   <br/> |代表啟動工作階段之使用者的租用戶。 如需詳細資訊，請參閱 [承租人資料表](tenants.md) 。 <br/> |
|**ReferredByUri** <br/> |Nvarchar (450)   <br/> |引用工作階段之使用者的 URI。  <br/> |
|**ReferredByUriType** <br/> |Nvarchar (256)   <br/> |引用工作階段之使用者的 URI 類型。 如需詳細資訊，請參閱 [UriTypes 表格](uritypes.md) 。 <br/> |
|**ReferredByUriTenant** <br/> |Nvarchar (256)   <br/> |引用工作階段之使用者的租用戶。 如需詳細資訊，請參閱 [承租人資料表](tenants.md) 。 <br/> |
|**DialogId** <br/> |varstring (775)   <br/> |SIP 對話方塊識別碼。格式為  <br/> :d ialog; from-tag; to-tag  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |用來識別目前工作階段所取代之對話的識別碼。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |用來識別工作階段的識別碼。 可與 ReplaceDialogIdTime 搭配使用，來唯一識別此工作階段所取代的工作階段。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 <br/> |
|**ReplacesDialogId** <br/> |Varchar (775)   <br/> |工作階段取代的 SIP 對話方塊識別碼。格式為：  <br/> dialog; 從-標籤; to-標記  <br/> |
|**IsStartedByConfServer** <br/> |位  <br/> |指出是否要透過會議伺服器來啟動工作階段。  <br/> |
|**IsEndedByConfServer** <br/> |位  <br/> |指出是否要透過會議伺服器來結束工作階段。  <br/> |
|**IsUserInternal** <br/> |位  <br/> |指出使用者是否會從內部網路登入。  <br/> |
|**ResponseTime** <br/> |datetime  <br/> |回應第一個 INVITE 訊息的時間。此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。  <br/> |
|**ResponseCode** <br/> |int  <br/> |工作階段邀請的 SIP 回應碼。此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。  <br/> |
|**DiagnosticId** <br/> |int  <br/> |從工作階段 SIP 標頭擷取而來的診斷識別碼。  <br/> |
|**ContentType** <br/> |Nvarchar (256)   <br/> |工作階段的內容類型。  <br/> |
|**FrontEnd** <br/> |Nvarchar (256)   <br/> |擷取工作階段適用之資料的前端伺服器 FQDN。  <br/> |
|**集區** <br/> |Nvarchar (256)   <br/> |擷取工作階段適用之資料的集區 FQDN。  <br/> |
|**MediationServer** <br/> |Nvarchar (256)   <br/> |參與工作階段之使用者所使用的中繼伺服器。  <br/> |
|**閘道** <br/> |Nvarchar (256)   <br/> |參與工作階段之使用者所使用的閘道。  <br/> |
|**Edgeserver atl-edge** <br/> |Nvarchar (256)   <br/> |參與工作階段之使用者所使用的 Edge Server FQDN。  <br/> |
|**UserFlag** <br/> |Smallint  <br/> |指出參與工作階段之使用者的屬性。以下為允許的屬性定義：  <br/> 0x01 - 與桌上電話整合  <br/> |
|**CallFlag** <br/> |Smallint  <br/> |指出通話屬性。以下為允許的屬性定義：  <br/> 0x01 - 已重試工作階段0  <br/> x02 - 代理程式代表回應群組所撥打的通話  <br/> |
   

