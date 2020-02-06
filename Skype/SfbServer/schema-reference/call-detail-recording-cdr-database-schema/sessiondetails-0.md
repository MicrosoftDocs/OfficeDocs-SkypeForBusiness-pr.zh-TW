---
title: SessionDetails 視圖
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
ms.assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
description: SessionDetails view 會儲存點對點工作階段的相關資訊，這可能是 VoIP VoIP 通話、兩方 IM 會話或其他類型的會話。 此視圖已在 Microsoft Lync Server 2013 中推出。
ms.openlocfilehash: f1d0d68fe152f277c02c53fd87afdb0ea4e4ab0c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814911"
---
# <a name="sessiondetails-view"></a>SessionDetails 視圖
 
SessionDetails view 會儲存點對點工作階段的相關資訊，這可能是 VoIP VoIP 通話、兩方 IM 會話或其他類型的會話。 此視圖已在 Microsoft Lync Server 2013 中推出。
  
|**左欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |會話要求的時間。 與 SessionIdSeq 搭配使用，可唯一識別會話。 如需詳細資訊，請參閱[商務用 Skype Server 2015 資料表中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |識別會話的識別碼編號。 與 SessionIdTime 搭配使用，可唯一識別會話。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**InviteTime** <br/> |datetime  <br/> |第一次邀請要求的時間。 這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。 如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。 這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。 如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。  <br/> |
|**FromUri** <br/> |Nvarchar （450）  <br/> |啟動會話之使用者的 URI。  <br/> |
|**ToUri** <br/> |Nvarchar （450）  <br/> |加入會話的使用者 URI。  <br/> |
|**FromUriType** <br/> |Nvarchar （256）  <br/> |啟動會話之使用者的 URI 類型。 如需詳細資訊，請參閱[UriTypes 資料表](uritypes.md)。 <br/> |
|**ToUriType** <br/> |Nvarchar （256）  <br/> |加入會話之使用者的 URI 類型。 如需詳細資訊，請參閱[UriTypes 資料表](uritypes.md)。 <br/> |
|**FromTenant** <br/> |Nvarchar （450）  <br/> |啟動會話之使用者的租使用者。 如需詳細資訊，請參閱[承租人資料表](tenants.md)。 <br/> |
|**ToTenant** <br/> |Nvarchar （256）  <br/> |加入會話之使用者的租使用者。 如需詳細資訊，請參閱[承租人資料表](tenants.md)。 <br/> |
|**FromEndpointId** <br/> |uniqueidentifier  <br/> |啟動會話之使用者之端點的唯一識別碼。  <br/> |
|**ToEndpointId** <br/> |uniqueidentifier  <br/> |加入會話之使用者之端點的唯一識別碼。  <br/> |
|**EndTime** <br/> |datetime  <br/> |會話的結束時間。  <br/> |
|**FromMessageCount** <br/> |int  <br/> |啟動會話的使用者所傳送的訊息數目。  <br/> |
|**ToMessageCount** <br/> |int  <br/> |加入會話的使用者所傳送的訊息數目。  <br/> |
|**FromClientVersion** <br/> |Nvarchar （256）  <br/> |啟動會話的使用者所使用的用戶端版本。  <br/> |
|**FromClientType** <br/> |int  <br/> |啟動會話的使用者所使用的用戶端。 如需詳細資訊，請參閱[UserAgentDef 資料表](useragentdef.md)。 <br/> |
|**FromClientCategory** <br/> |Nvarchar （64）  <br/> |啟動會話之使用者所使用之用戶端類別的名稱。  <br/> |
|**ToClientVersion** <br/> |Nvarchar （256）  <br/> |加入會話的使用者所使用的用戶端版本  <br/> |
|**ToClientType** <br/> |int  <br/> |加入會話的使用者所使用的用戶端。 如需詳細資訊，請參閱[UserAgentDef 資料表](useragentdef.md)。 <br/> |
|**ToClientCategory** <br/> |Nvarchar （64）  <br/> |加入會話之使用者所使用之用戶端類別的名稱。  <br/> |
|**TargetUri** <br/> |Nvarchar （450）  <br/> |會話目標使用者的 URI。  <br/> |
|**TargetUriType** <br/> |Nvarchar （450）  <br/> |會話的目標使用者 URI 類型。 如需詳細資訊，請參閱[UriTypes 資料表](uritypes.md)。 <br/> |
|**OnBehalfOfUri** <br/> |Nvarchar （450）  <br/> |代表其啟動會話的使用者 URI。  <br/> |
|**OnnnBehalfOfUriType** <br/> |Nvarchar （256）  <br/> |啟動會話所代表之使用者的 URI 類型。 如需詳細資訊，請參閱[UriTypes 資料表](uritypes.md)。 <br/> |
|**OnBehalfOfTenant** <br/> |Nvarchar （256）  <br/> |代表啟動會話的使用者租使用者。 如需詳細資訊，請參閱[承租人資料表](tenants.md)。 <br/> |
|**ReferredByUri** <br/> |Nvarchar （450）  <br/> |參照會話之使用者的 URI。  <br/> |
|**ReferredByUriType** <br/> |Nvarchar （256）  <br/> |參照會話之使用者的 URI 類型。 如需詳細資訊，請參閱[UriTypes 資料表](uritypes.md)。 <br/> |
|**ReferredByTenant** <br/> |Nvarchar （256）  <br/> |參照會話之使用者的租使用者。 如需詳細資訊，請參閱[承租人資料表](tenants.md)。 <br/> |
|**DialogId** <br/> |Varchar （775）  <br/> |SIP 對話方塊識別碼。 格式為：  <br/> 對話方塊; 從標籤; 到標籤  <br/> |
|**Id** <br/> |uniqueidentifier  <br/> |用於關聯多個會話的 GUID。  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |會話所取代的對話方塊時間。 與 ReplaceDialogIdSeq 搭配使用，以唯一識別會話所取代的對話方塊。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |識別會話的識別碼編號。 與 ReplaceDialogIdTime 搭配使用，以唯一識別會話所取代的對話方塊。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**ReplacesDialogId** <br/> |Varchar （775）  <br/> |[SIP] 對話方塊識別碼，該會話會取代。 格式為：  <br/> 對話方塊; 從標籤; 到標籤  <br/> |
|**ResponseTime** <br/> |datetime  <br/> |第一次邀請訊息的回復時間。 這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。 如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。  <br/> |
|**ResponseCode** <br/> |int  <br/> |SIP 回應程式碼加入會話邀請。 這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。 如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。  <br/> |
|**DiagnosticId** <br/> |int  <br/> |從 SIP 標頭捕獲的診斷 ID。  <br/> |
|**ContentType** <br/> |Nvarchar （256）  <br/> |會話的內容類型。  <br/> |
|**FrontEnd** <br/> |Nvarchar （256）  <br/> |捕獲會話資料的前端伺服器 FQDN。  <br/> |
|**集區** <br/> |Nvarchar （256）  <br/> |捕獲會話資料之池的 FQDN。  <br/> |
|**FromEdgeServer** <br/> |Nvarchar （256）  <br/> |啟動會話之使用者所使用的邊緣伺服器 FQDN。  <br/> |
|**ToEdgeServer** <br/> |Nvarchar （256）  <br/> |啟動會話之使用者所使用的邊緣伺服器 FQDN  <br/> |
|**IsFromInternal** <br/> |稍微  <br/> |指出啟動會話的使用者是否已從內部網路登入。  <br/> |
|**IsToInternal** <br/> |稍微  <br/> |指出加入會話的使用者是否已從內部網路登入。  <br/> |
|**CallPriority** <br/> |Nvarchar （256）  <br/> |會話的呼叫優先順序。  <br/> |
|**FromUserFlag** <br/> |Smallint  <br/> |指出啟動會話之使用者的屬性。 允許下列屬性定義：  <br/> 0x01-與桌面電話整合  <br/> |
|**ToUserFlag** <br/> |Smallint  <br/> |指出啟動會話之使用者的屬性。 允許下列屬性定義：  <br/> 0x01-與桌面電話整合  <br/> |
|**CallFlag** <br/> |Smallint  <br/> |指出通話屬性。 允許下列屬性定義：  <br/> 0x01-重新嘗試會話  <br/> 0x02-代理代表回應群組所做的通話  <br/> |
|**位置** <br/> |Varchar （max）  <br/> |緊急通話的位置。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> |供監視服務內部使用。  <br/> 此欄位是在商務用 Skype Server 2015 中推出。  <br/> |
   

