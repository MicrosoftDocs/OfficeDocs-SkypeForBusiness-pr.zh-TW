---
title: 商務用 Skype Server 2015 中的 ConferenceSessionDetails 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
description: 每個記錄代表一個會議會話，可能是與焦點進行的會話，或是與特定會議服務器的會話。
ms.openlocfilehash: 95cf64589cdcd0fd38b4e29cd4e863c870f2a7a6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815341"
---
# <a name="conferencesessiondetails-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 ConferenceSessionDetails 表格
 
每個記錄代表一個會議會話，可能是與焦點進行的會話，或是與特定會議服務器的會話。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Datetime  <br/> |主要、外部  <br/> |會話要求的時間;與**SessionIdSeq**搭配使用，可唯一識別會議會話。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主要、外部  <br/> |識別會話的識別碼編號。 與**SessionIdTime**搭配使用，可唯一識別會議會話。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |外  <br/> |與此會話相關的焦點會議 URI。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](conferenceuris.md)的 [ConferenceUris] 資料表。 此 URI 是以焦點為基礎的會議 URI。 <br/> |
|**ConfInstance** <br/> |uniqueIdentifier  <br/> ||區分週期性會議實例的識別碼。 每個週期性會議實例都有相同的 ConferenceURI，但有不同的 ConfInstance 值。  <br/> 此欄位是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**McuConferenceUriId** <br/> |int  <br/> |外  <br/> |與此會話相關的會議服務器會議 URI。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](conferenceuris.md)的 [ConferenceUris] 資料表。 此 URI 是會議服務器的會議 URI。 針對焦點會議會話，此欄會是 null。 <br/> |
|**UserId** <br/> |int  <br/> |外  <br/> |在會議會話中，有一個使用者的識別碼。 如需詳細資訊，請參閱 [[使用者] 表格](users.md)。 <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> ||識別端點實例的 GUID。 例如，如果某個使用者使用相同的帳戶登入不同的電腦，則每個電腦將會有不同的端點 ID。  <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |外  <br/> |表示呼叫者代表者的使用者識別碼。 如需詳細資訊，請參閱 [[使用者] 表格](users.md)。 <br/> |
|**ReferredById** <br/> |int  <br/> |外  <br/> |呼叫者的使用者識別碼。 如需詳細資訊，請參閱 [[使用者] 表格](users.md)。 <br/> |
|**UserClientVersionId** <br/> |int  <br/> |外  <br/> |會議使用者使用的用戶端版本。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](clientversions.md)的 [ClientVersions] 資料表。 <br/> |
|**ConfClientVersionId** <br/> |int  <br/> |外  <br/> |會議服務器所使用的用戶端版本。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](clientversions.md)的 [ClientVersions] 資料表。 <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |外  <br/> |[識別碼] 編號，找出目前會話所取代的對話方塊。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |外  <br/> |識別會話的識別碼編號。 與**ReplacesDialogIdTime**搭配使用，可唯一識別此會話所取代的會話。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**IsStartedByConfServer** <br/> |稍微  <br/> ||指示會議服務器是否已啟動會話。  <br/> |
|**IsEndedByConfServer** <br/> |稍微  <br/> ||表示會議服務器是否已結束會話。  <br/> |
|**IsUserInternal** <br/> |稍微  <br/> ||使用者是否已從內部登入。  <br/> |
|**ResponseCode** <br/> |int  <br/> ||會話初始通訊協定（SIP）回應程式碼加入會話邀請。 這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。 如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||從 SIP 標頭捕獲的診斷 ID。  <br/> |
|**ServerId** <br/> |int  <br/> |外  <br/> |此會話所用的前端伺服器 ID。 如需詳細資訊，請參閱 [[伺服器] 資料表](servers.md)。 <br/> |
|**PoolId** <br/> |int  <br/> |外  <br/> |捕獲會話的池 ID。 如需詳細資訊，請參閱 [[彙集] 資料表](pools.md)。 <br/> |
|**MediationServerId** <br/> |int  <br/> |外  <br/> |通話使用的中繼伺服器。 如需詳細資訊，請參閱[MediationServers 資料表](mediationservers.md)。 <br/> |
|**GatewayId** <br/> |int  <br/> |外  <br/> |通話使用的閘道。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的 [閘道] 資料表](gateways.md)。 <br/> |
|**EdgeServerId** <br/> |int  <br/> |外  <br/> |通話使用的邊緣伺服器。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](edgeservers.md)的 [EdgeServers] 資料表。 <br/> |
|**ContentTypeId** <br/> |int  <br/> |外  <br/> |會話中使用的內容類型。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](contenttypes.md)的 [主控] 資料表。 <br/> |
|**InviteTime** <br/> |datetime  <br/> ||第一次邀請要求的時間。 這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。 如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。  <br/> |
|**ResponseTime** <br/> |datetime  <br/> ||第一次 SIP 回應的時間。 這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。 如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||會話結束的時間。  <br/> |
|**UriTypeId** <br/> |Tinyint  <br/> |外  <br/> |包含[UriTypes 資料表](uritypes.md)中的 MCU URI 類型值。 此欄位可用來改善查詢效能。  <br/> 此欄位是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**UserFlag** <br/> |Smallint  <br/> || 指示使用者屬性的位組。 下列屬性定義如下所示： <br/>  與桌面手機整合-1 <br/> |
|**CallFlag** <br/> |Smallint  <br/> || 指明通話屬性的位組。 下列屬性定義如下所示： <br/>  重試會話-1 <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供監視服務內部使用。  <br/> 此欄位是在商務用 Skype Server 2015 中推出。  <br/> |
   
\*在大部分的會話中，SessionIdSeq 將會有1的值。 如果多個會話的開始時間完全相同，則 SessionIdSeq 會是1，另一個會是2，依此類推。
  

