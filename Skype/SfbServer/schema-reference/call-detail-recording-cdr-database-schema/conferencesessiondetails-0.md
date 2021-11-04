---
title: 商務用 Skype Server 2015 中的 ConferenceSessionDetails 表格
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
description: 每筆記錄都代表一個會議工作階段，它可以是有「焦點」的工作階段，或是特定會議伺服器的工作階段。
ms.openlocfilehash: 087dd056dae0041ab63934b25038672a74410343
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759445"
---
# <a name="conferencesessiondetails-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 ConferenceSessionDetails 表格
 
每筆記錄都代表一個會議工作階段，它可以是有「焦點」的工作階段，或是特定會議伺服器的工作階段。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Datetime  <br/> |主要、外部  <br/> |會話要求的時間;與 **SessionIdSeq** 搭配使用，以唯一識別會議會話。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主要，外部  <br/> |用來識別工作階段的識別碼。 與 **SessionIdTime** 搭配使用，以唯一識別會議會話。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Foreign  <br/> |與此會話相關的聚焦會議 URI。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的 ConferenceUris 表格](conferenceuris.md)。 此 URI 是以焦點為基礎的會議 URI。 <br/> |
|**ConfInstance** <br/> |唯一  <br/> ||可區分週期性會議的執行個體的識別碼。每個週期性會議執行個體都會有相同的 ConferenceURI 且不同的 ConfInstance 值。  <br/> 此欄位是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**McuConferenceUriId** <br/> |int  <br/> |Foreign  <br/> |與此會話相關的會議服務器會議 URI。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的 ConferenceUris 表格](conferenceuris.md)。 此 URI 是以會議服務器為基礎的會議 URI。 若為 Focus 會議會話，此欄將會是 null。 <br/> |
|**UserId** <br/> |int  <br/> |Foreign  <br/> |會議會話中某位使用者的識別碼。 如需詳細資訊，請參閱 [Users 表格](users.md) 。 <br/> |
|**UserEndpointId** <br/> |唯一  <br/> ||識別端點實例的 GUID。 例如，如果一個使用者使用相同的帳戶登入不同的機器，則每一部機器都會有不同的端點識別碼。  <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |Foreign  <br/> |指出來電者所代表之使用者的識別碼。 如需詳細資訊，請參閱 [Users 表格](users.md) 。 <br/> |
|**ReferredById** <br/> |int  <br/> |Foreign  <br/> |轉接此通話之使用者的識別碼。 如需詳細資訊，請參閱 [Users 表格](users.md) 。 <br/> |
|**UserClientVersionId** <br/> |int  <br/> |Foreign  <br/> |會議使用者使用的用戶端版本。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的 ClientVersions 表格](clientversions.md)。 <br/> |
|**ConfClientVersionId** <br/> |int  <br/> |Foreign  <br/> |會議服務器所使用的用戶端版本。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的 ClientVersions 表格](clientversions.md)。 <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Foreign  <br/> |用來識別目前工作階段所取代之對話的識別碼。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Foreign  <br/> |用來識別工作階段的識別碼。 其會與 **ReplacesDialogIdTime** 搭配使用，專門用於識別此工作階段所取代的工作階段。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 <br/> |
|**IsStartedByConfServer** <br/> |位  <br/> ||會指出會議服務器是否已啟動會話。  <br/> |
|**IsEndedByConfServer** <br/> |位  <br/> ||表示會話是否由會議服務器結束。  <br/> |
|**IsUserInternal** <br/> |位  <br/> ||使用者是否從內部登入。  <br/> |
|**ResponseCode** <br/> |int  <br/> ||會話初始通訊協定 (SIP) 回應程式碼加入會話邀請。 此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。 如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||從 SIP 標頭擷取而來的診斷識別碼。  <br/> |
|**ServerId** <br/> |int  <br/> |Foreign  <br/> |用於此工作階段之前端伺服器的識別碼。 如需詳細資訊，請參閱 [Servers 表格](servers.md) 。 <br/> |
|**PoolId** <br/> |int  <br/> |Foreign  <br/> |擷取工作階段所在集區的識別碼。 如需詳細資訊，請參閱 [pool 表格](pools.md) 。 <br/> |
|**MediationServerId** <br/> |int  <br/> |Foreign  <br/> |通話所使用的轉送伺服器。 如需詳細資訊，請參閱 [MediationServers 表格](mediationservers.md) 。 <br/> |
|**GatewayId** <br/> |int  <br/> |Foreign  <br/> |通話所使用的閘道。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的閘道表格](gateways.md)。 <br/> |
|**EdgeServerId** <br/> |int  <br/> |Foreign  <br/> |通話所使用的 Edge Server。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的 EdgeServers 表格](edgeservers.md)。 <br/> |
|**ContentTypeId** <br/> |int  <br/> |Foreign  <br/> |工作階段中所使用的內容類型。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的 ContentTypes 表格](contenttypes.md)。 <br/> |
|**InviteTime** <br/> |datetime  <br/> ||第一個 INVITE 要求的時間。 此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。 如果沒有 INVITE 訊息，則會使用第一個相關 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。  <br/> |
|**ResponseTime** <br/> |datetime  <br/> ||第一次 SIP 回應的時間。 此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。 如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||會話結束的時間。  <br/> |
|**UriTypeId** <br/> |Tinyint  <br/> |Foreign  <br/> |包含 [UriTypes 表格](uritypes.md)中的 MCU URI 類型值。 此欄位是用來改善查詢效能。  <br/> 此欄位是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**UserFlag** <br/> |Smallint  <br/> || 會指出使用者屬性的位組。 下列是屬性的定義： <br/>  與桌面電話-1 整合 <br/> |
|**CallFlag** <br/> |Smallint  <br/> || 指出通話屬性的位元設定。下列是屬性的定義： <br/>  重新嘗試的會話-1 <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供監控服務內部使用。  <br/> 此欄位是在商務用 Skype Server 2015 中引入。  <br/> |
   
\* 對於大部分的會話，SessionIdSeq 的值會是1。 如有多個工作階段的啟動時間完全相同，將只有一個工作階段的 SessionIdSeq 值會是 1，其餘工作階段皆是 2，依此類推。
  

