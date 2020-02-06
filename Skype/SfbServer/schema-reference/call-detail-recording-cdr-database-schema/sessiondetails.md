---
title: SessionDetails 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
description: 每個記錄代表一個點對點工作階段，這可能是 VoIP VoIP 通話、兩方 IM 會話或其他類型的會話。 您可以執行表格加入媒體資料表，以尋找此會話中涉及的每個媒體的詳細資料。
ms.openlocfilehash: 1a211598e7771c5637af191f19ad2926e3cc803e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814901"
---
# <a name="sessiondetails-table"></a>SessionDetails 表格
 
每個記錄代表一個點對點工作階段，這可能是 VoIP VoIP 通話、兩方 IM 會話或其他類型的會話。 您可以執行表格加入[媒體資料表](media.md)，以尋找此會話中涉及的每個媒體的詳細資料。
  
請注意，IsUser1IntegratedWithDeskPhone 和 IsUser2IntegratedWithDeskPhone 欄位已從商務用 Skype Server 2015 中使用的 SessionDetails 資料表中刪除。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主要、外部  <br/> |會話要求的時間。 與**SessionIdSeq**搭配使用，可唯一識別會話。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主要、外部  <br/> |識別會話的識別碼編號。 與**SessionIdTime**搭配使用，以唯一識別會話。 * 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**Id** <br/> |uniqueidentifier  <br/> ||要關聯多個會話的 GUID。  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |外  <br/> |[識別碼] 編號，找出目前會話所取代的對話方塊。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |外  <br/> |識別會話的識別碼編號。 與**ReplacesDialogIdTime**搭配使用，可唯一識別此會話所取代的會話。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**User1Id** <br/> |int  <br/> |外  <br/> |會話中一個使用者的 ID。 如需詳細資訊，請參閱 [[使用者] 表格](users.md)。 <br/> |
|**User2Id** <br/> |int  <br/> |外  <br/> |會話中其他使用者的 ID。 如需詳細資訊，請參閱 [[使用者] 表格](users.md)。 <br/> |
|**User1EndpointId** <br/> |uniqueIdentifier  <br/> ||識別會話中第一個使用者所使用端點的 GUID。  <br/> 此欄位是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**User2EndpointId** <br/> |uniqueIdentifier  <br/> ||GUID，可識別會話中第二位使用者使用的端點。  <br/> 此欄位是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**TargetUserId** <br/> |int  <br/> |外  <br/> |SIP 要求中的原始使用者 URI。 如需詳細資訊，請參閱 [[使用者] 表格](users.md)。 <br/> |
|**SessionStartedById** <br/> |int  <br/> |外  <br/> |啟動會話的使用者識別碼。 如需詳細資訊，請參閱 [[使用者] 表格](users.md)。 <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |外  <br/> |表示呼叫者代表者的使用者識別碼。 如需詳細資訊，請參閱 [[使用者] 表格](users.md)。 <br/> |
|**ReferredById** <br/> |int  <br/> |外  <br/> |呼叫者的使用者識別碼。 如需詳細資訊，請參閱 [[使用者] 表格](users.md)。 <br/> |
|**ServerId** <br/> |int  <br/> |外  <br/> |此會話所用的前端伺服器 ID。 如需詳細資訊，請參閱 [[伺服器] 資料表](servers.md)。 <br/> |
|**PoolId** <br/> |int  <br/> |外  <br/> |捕獲會話的池 ID。 如需詳細資訊，請參閱 [[彙集] 資料表](pools.md)。 <br/> |
|**ContentTypeID** <br/> |int  <br/> |外  <br/> |會話中使用的內容類型。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](contenttypes.md)的 [主控] 資料表。 <br/> |
|**User1ClientVerId** <br/> |int  <br/> |外  <br/> |[User1] 使用的用戶端版本。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](clientversions.md)的 [ClientVersions] 資料表。 <br/> |
|**User2ClientVerId** <br/> |int  <br/> |外  <br/> |由者使用的用戶端版本。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](clientversions.md)的 [ClientVersions] 資料表。 <br/> |
|**User1EdgeServerid** <br/> |int  <br/> |外  <br/> |[User1] 使用的邊緣伺服器。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](edgeservers.md)的 [EdgeServers] 資料表。 <br/> |
|**User2EdgeServerid** <br/> |int  <br/> |外  <br/> |由者使用的邊緣伺服器。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](edgeservers.md)的 [EdgeServers] 資料表。 <br/> |
|**IsUser1Internal** <br/> |稍微  <br/> ||User1 是否已從內部登入。  <br/> |
|**IsUser2Internal** <br/> |稍微  <br/> ||您是否已從內部或非登入  <br/> |
|**InviteTime** <br/> |datetime  <br/> ||第一次邀請要求的時間。 這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。 如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。 這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。 如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。  <br/> |
|**ResponseTime** <br/> |datetime  <br/> ||回應第一個邀請訊息的時間。 這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。 如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。  <br/> |
|**ResponseCode** <br/> |int  <br/> ||SIP 回應程式碼加入會話邀請。 這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。 如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||從 SIP 標頭捕獲的診斷 ID。  <br/> |
|**CallPriority** <br/> |int  <br/> |外  <br/> |通話優先順序。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](callpriorities.md)的 [CallPriorities] 資料表。 <br/> |
|**User1MessageCount** <br/> |int  <br/> ||在會話期間由 User1 傳送的訊息數目。  <br/> |
|**User2MessageCount** <br/> |int  <br/> ||在會話期間由方法2傳送的訊息數目。  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||會話結束時的時間。  <br/> |
|**MediaTypes** <br/> |int  <br/> ||一個位組，指明此會話的媒體類型。 所列的是以下類型的定義：  <br/> 1-IM  <br/> 2-FILE_TRANSFER  <br/> 4-REMOTE_ASSISTANCE  <br/> 8-APP_SHARING  <br/> 16-音訊  <br/> 32-影片  <br/> 64-APP_INVITE  <br/> |
|**User1Flag** <br/> |Smallint  <br/> ||指示 User1 屬性的位組。 下列屬性定義如下所示：  <br/> 0x01-與桌面電話整合  <br/> |
|**User2Flag** <br/> |Smallint  <br/> ||指示使用2屬性的位組。 下列屬性定義如下所示：  <br/> 0x01-與桌面電話整合  <br/> |
|**CallFlag** <br/> |Smallint  <br/> ||指明通話屬性的位組。 下列屬性定義如下所示：  <br/> 0x01-重新嘗試會話  <br/> 0x02-代理代表回應群組所做的通話  <br/> |
|**預處理** <br/> |稍微  <br/> ||供監視服務內部使用。  <br/> 此欄位是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供監視服務內部使用。  <br/> 此欄位是在商務用 Skype Server 2015 中推出。  <br/> |
   
\*在大部分的會話中，SessionIdSeq 將會有1的值。 如果多個會話的開始時間完全相同，則 SessionIdSeq 會是1，另一個會是2，依此類推。
  

