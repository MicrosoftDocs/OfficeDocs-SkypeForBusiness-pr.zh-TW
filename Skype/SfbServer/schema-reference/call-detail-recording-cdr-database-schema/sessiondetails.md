---
title: SessionDetails 表格
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
description: 每筆記錄代表一個對等工作階段，可以是 VoIP 對 VoIP 電話、雙方 IM 工作階段或其他工作階段類型。 您可以對 Media 資料表執行表格加入，以找出此會話中所涉及的每個媒體的詳細資料。
ms.openlocfilehash: eb47c87be69bfc9308c8c641c54a2173ba2ed03eeae7f7543ce6a5cbb97f7092
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54284483"
---
# <a name="sessiondetails-table"></a>SessionDetails 表格
 
每筆記錄代表一個對等工作階段，可以是 VoIP 對 VoIP 電話、雙方 IM 工作階段或其他工作階段類型。 您可以對 [media 資料表](media.md) 執行表格加入，以找出此會話中所涉及的每個媒體的詳細資料。
  
請注意，IsUser1IntegratedWithDeskPhone 和 IsUser2IntegratedWithDeskPhone 欄位已經從商務用 Skype Server 2015 所用的 SessionDetails 資料表中刪除。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主要，外部  <br/> |工作階段要求的時間。 其會與 **SessionIdSeq** 搭配使用，專門用於識別工作階段。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主要，外部  <br/> |用來識別工作階段的識別碼。 與 **SessionIdTime** 搭配使用，以唯一識別會話。 * 如需詳細資訊，請參閱 [商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 <br/> |
|**CorrelationId** <br/> |唯一  <br/> ||與多個工作階段相互關聯的 GUID。  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Foreign  <br/> |用來識別目前工作階段所取代之對話的識別碼。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Foreign  <br/> |用來識別工作階段的識別碼。 其會與 **ReplacesDialogIdTime** 搭配使用，專門用於識別此工作階段所取代的工作階段。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 <br/> |
|**User1Id** <br/> |int  <br/> |Foreign  <br/> |工作階段中某位使用者的識別碼。 如需詳細資訊，請參閱 [Users 表格](users.md) 。 <br/> |
|**User2Id** <br/> |int  <br/> |Foreign  <br/> |工作階段中其他使用者的識別碼。 如需詳細資訊，請參閱 [Users 表格](users.md) 。 <br/> |
|**User1EndpointId** <br/> |唯一  <br/> ||識別工作階段中第一位使用者所使用之端點的 GUID。  <br/> 此欄位是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**User2EndpointId** <br/> |唯一  <br/> ||識別工作階段中第二位使用者所使用之端點的 GUID。  <br/> 此欄位是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**TargetUserId** <br/> |int  <br/> |Foreign  <br/> |SIP 要求中原始的目標使用者 URI。 如需詳細資訊，請參閱 [Users 表格](users.md) 。 <br/> |
|**SessionStartedById** <br/> |int  <br/> |Foreign  <br/> |起始工作階段之使用者的識別碼。 如需詳細資訊，請參閱 [Users 表格](users.md) 。 <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |Foreign  <br/> |指出來電者所代表之使用者的識別碼。 如需詳細資訊，請參閱 [Users 表格](users.md) 。 <br/> |
|**ReferredById** <br/> |int  <br/> |Foreign  <br/> |轉接此通話之使用者的識別碼。 如需詳細資訊，請參閱 [Users 表格](users.md) 。 <br/> |
|**ServerId** <br/> |int  <br/> |Foreign  <br/> |用於此工作階段之前端伺服器的識別碼。 如需詳細資訊，請參閱 [Servers 表格](servers.md) 。 <br/> |
|**PoolId** <br/> |int  <br/> |Foreign  <br/> |擷取工作階段所在集區的識別碼。 如需詳細資訊，請參閱 [pool 表格](pools.md) 。 <br/> |
|**ContentTypeID** <br/> |int  <br/> |Foreign  <br/> |工作階段中所使用的內容類型。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的 ContentTypes 表格](contenttypes.md)。 <br/> |
|**User1ClientVerId** <br/> |int  <br/> |Foreign  <br/> |使用者1 所使用的用戶端版本。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的 ClientVersions 表格](clientversions.md)。 <br/> |
|**User2ClientVerId** <br/> |int  <br/> |Foreign  <br/> |使用者2 所使用的用戶端版本。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的 ClientVersions 表格](clientversions.md)。 <br/> |
|**User1EdgeServerid** <br/> |int  <br/> |Foreign  <br/> |使用者 1 所使用的 Edge Server。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的 EdgeServers 表格](edgeservers.md)。 <br/> |
|**User2EdgeServerid** <br/> |int  <br/> |Foreign  <br/> |使用者 2 所使用的 Edge Server。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的 EdgeServers 表格](edgeservers.md)。 <br/> |
|**IsUser1Internal** <br/> |位  <br/> ||使用者 1 是否由內部登入。  <br/> |
|**IsUser2Internal** <br/> |位  <br/> ||使用者 2 是否由內部登入。  <br/> |
|**InviteTime** <br/> |datetime  <br/> ||第一個 INVITE 要求的時間。 此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。 如果沒有 INVITE 訊息，則會使用第一個相關 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。 此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。 如果沒有 INVITE 訊息，則會使用第一個相關 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。  <br/> |
|**ResponseTime** <br/> |datetime  <br/> ||回應第一個 INVITE 訊息的時間。 此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。 如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。  <br/> |
|**ResponseCode** <br/> |int  <br/> ||工作階段邀請的 SIP 回應碼。此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||從 SIP 標頭擷取而來的診斷識別碼。  <br/> |
|**CallPriority** <br/> |int  <br/> |Foreign  <br/> |通話優先順序。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的 CallPriorities 表格](callpriorities.md)。 <br/> |
|**User1MessageCount** <br/> |int  <br/> ||工作階段期間使用者 1 所傳送的訊息數。  <br/> |
|**User2MessageCount** <br/> |int  <br/> ||工作階段期間使用者 2 所傳送的訊息數。  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||工作階段結束的時間。  <br/> |
|**MediaTypes** <br/> |int  <br/> ||指出此工作階段之媒體類型的位元集。下列為類型的定義：  <br/> 1-IM  <br/> 2-FILE_TRANSFER  <br/> 4-REMOTE_ASSISTANCE  <br/> 8-APP_SHARING  <br/> 16-音訊  <br/> 32-影片  <br/> 64-APP_INVITE  <br/> |
|**User1Flag** <br/> |Smallint  <br/> ||指出使用者 1 屬性的位元集。下列是屬性的定義：  <br/> 0x01 - 與桌上電話整合  <br/> |
|**User2Flag** <br/> |Smallint  <br/> ||指出使用者 2 屬性的位元集。下列是屬性的定義：  <br/> 0x01 - 與桌上電話整合  <br/> |
|**CallFlag** <br/> |Smallint  <br/> ||指出通話屬性的位元設定。下列是屬性的定義：  <br/> 0x01 - 重試工作階段 1  <br/> 0x02 - 由代理人代替回應群組撥出的通話  <br/> |
|**處理** <br/> |位  <br/> ||供監控服務內部使用。  <br/> 此欄位是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供監控服務內部使用。  <br/> 此欄位是在商務用 Skype Server 2015 中引入。  <br/> |
   
\* 對於大部分的會話，SessionIdSeq 的值會是1。 如有多個工作階段的啟動時間完全相同，將只有一個工作階段的 SessionIdSeq 值會是 1，其餘工作階段皆是 2，依此類推。
  

