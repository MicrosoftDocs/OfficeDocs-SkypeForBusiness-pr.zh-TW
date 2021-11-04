---
title: SessionDetails view
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
ms.assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
description: SessionDetails view 儲存點對點工作階段的資訊，這可能是 VoIP-VoIP 電話、兩方 IM 會話或其他類型的會話。 此視圖已引進于 Microsoft Lync Server 2013。
ms.openlocfilehash: 5a278960912ac38dc75fe398e3d75de710785800
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767451"
---
# <a name="sessiondetails-view"></a>SessionDetails view
 
SessionDetails view 儲存點對點工作階段的資訊，這可能是 VoIP-VoIP 電話、兩方 IM 會話或其他類型的會話。 此視圖已引進于 Microsoft Lync Server 2013。
  
|**欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |工作階段要求的時間。 與 SessionIdSeq 搭配使用，以唯一識別工作階段。 如需詳細資訊，請參閱[商務用 Skype Server 2015 表格中的對話方塊表格](dialogs.md)。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |識別工作階段的 ID 號碼。 與 SessionIdTime 搭配使用，以唯一識別工作階段。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 <br/> |
|**InviteTime** <br/> |datetime  <br/> |第一個邀請要求的時間。 此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。 如果沒有 INVITE 訊息，則會使用第一個相關 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。 此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。 如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。  <br/> |
|**FromUri** <br/> |Nvarchar (450)   <br/> |啟動會話之使用者的 URI。  <br/> |
|**ToUri** <br/> |Nvarchar (450)   <br/> |加入會話之使用者的 URI。  <br/> |
|**FromUriType** <br/> |Nvarchar (256)   <br/> |啟動會話之使用者的 URI 類型。 如需詳細資訊，請參閱 [UriTypes 表格](uritypes.md) 。 <br/> |
|**ToUriType** <br/> |Nvarchar (256)   <br/> |加入會話之使用者的 URI 類型。 如需詳細資訊，請參閱 [UriTypes 表格](uritypes.md) 。 <br/> |
|**FromTenant** <br/> |Nvarchar (450)   <br/> |啟動會話之使用者的租使用者。 如需詳細資訊，請參閱 [承租人資料表](tenants.md) 。 <br/> |
|**ToTenant** <br/> |Nvarchar (256)   <br/> |加入會話之使用者的租使用者。 如需詳細資訊，請參閱 [承租人資料表](tenants.md) 。 <br/> |
|**FromEndpointId** <br/> |唯一  <br/> |啟動會話之使用者的端點唯一識別碼。  <br/> |
|**ToEndpointId** <br/> |唯一  <br/> |加入會話之使用者的端點唯一識別碼。  <br/> |
|**EndTime** <br/> |datetime  <br/> |工作階段結束時間。  <br/> |
|**FromMessageCount** <br/> |int  <br/> |啟動會話之使用者所傳送的訊息數。  <br/> |
|**ToMessageCount** <br/> |int  <br/> |加入會話之使用者所傳送的訊息數。  <br/> |
|**FromClientVersion** <br/> |Nvarchar (256)   <br/> |啟動會話之使用者所使用的用戶端版本。  <br/> |
|**FromClientType** <br/> |int  <br/> |啟動會話之使用者所使用的用戶端。 如需詳細資訊，請參閱 [UserAgentDef 表格](useragentdef.md) 。 <br/> |
|**FromClientCategory** <br/> |Nvarchar (64)   <br/> |啟動會話之使用者所使用的用戶端類別名稱。  <br/> |
|**ToClientVersion** <br/> |Nvarchar (256)   <br/> |加入會話之使用者所使用的用戶端版本  <br/> |
|**ToClientType** <br/> |int  <br/> |加入會話之使用者所使用的用戶端。 如需詳細資訊，請參閱 [UserAgentDef 表格](useragentdef.md) 。 <br/> |
|**ToClientCategory** <br/> |Nvarchar (64)   <br/> |加入會話之使用者所使用的用戶端類別名稱。  <br/> |
|**TargetUri** <br/> |Nvarchar (450)   <br/> |會話目標使用者的 URI。  <br/> |
|**TargetUriType** <br/> |Nvarchar (450)   <br/> |會話之目標使用者的 URI 類型。 如需詳細資訊，請參閱 [UriTypes 表格](uritypes.md) 。 <br/> |
|**OnBehalfOfUri** <br/> |Nvarchar (450)   <br/> |代表啟動工作階段之使用者的 URI。  <br/> |
|**OnnnBehalfOfUriType** <br/> |Nvarchar (256)   <br/> |代表啟動工作階段之使用者的 URI 類型。 如需詳細資訊，請參閱 [UriTypes 表格](uritypes.md) 。 <br/> |
|**OnBehalfOfTenant** <br/> |Nvarchar (256)   <br/> |代表啟動工作階段之使用者的租用戶。 如需詳細資訊，請參閱 [承租人資料表](tenants.md) 。 <br/> |
|**ReferredByUri** <br/> |Nvarchar (450)   <br/> |引用工作階段之使用者的 URI。  <br/> |
|**ReferredByUriType** <br/> |Nvarchar (256)   <br/> |引用工作階段之使用者的 URI 類型。 如需詳細資訊，請參閱 [UriTypes 表格](uritypes.md) 。 <br/> |
|**ReferredByTenant** <br/> |Nvarchar (256)   <br/> |引用工作階段之使用者的租用戶。 如需詳細資訊，請參閱 [承租人資料表](tenants.md) 。 <br/> |
|**DialogId** <br/> |Varchar (775)   <br/> |SIP 對話方塊識別碼。 格式為：  <br/> dialog; 從-標籤; to-標記  <br/> |
|**CorrelationId** <br/> |唯一  <br/> |用於關聯多個會話的 GUID。  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |會話所取代之對話方塊的時間。 與 ReplaceDialogIdSeq 搭配使用，以唯一識別會話所取代的對話方塊。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |識別工作階段的 ID 號碼。 與 ReplaceDialogIdTime 搭配使用，以唯一識別會話所取代的對話方塊。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 <br/> |
|**ReplacesDialogId** <br/> |Varchar (775)   <br/> |工作階段取代的 SIP 對話方塊識別碼。 格式為：  <br/> dialog; 從-標籤; to-標記  <br/> |
|**ResponseTime** <br/> |datetime  <br/> |回應第一個 INVITE 訊息的時間。此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。  <br/> |
|**ResponseCode** <br/> |int  <br/> |工作階段邀請的 SIP 回應碼。此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。  <br/> |
|**DiagnosticId** <br/> |int  <br/> |從 SIP 標頭捕獲的診斷識別碼。  <br/> |
|**ContentType** <br/> |Nvarchar (256)   <br/> |會話的內容類型。  <br/> |
|**FrontEnd** <br/> |Nvarchar (256)   <br/> |擷取工作階段適用之資料的前端伺服器 FQDN。  <br/> |
|**集區** <br/> |Nvarchar (256)   <br/> |擷取工作階段適用之資料的集區 FQDN。  <br/> |
|**FromEdgeServer** <br/> |Nvarchar (256)   <br/> |啟動會話之使用者所使用的 Edge server FQDN。  <br/> |
|**ToEdgeServer** <br/> |Nvarchar (256)   <br/> |啟動會話之使用者所使用的 Edge server FQDN  <br/> |
|**IsFromInternal** <br/> |位  <br/> |會指出啟動會話的使用者是否從內部網路登入。  <br/> |
|**IsToInternal** <br/> |位  <br/> |會指出加入會話的使用者是否從內部網路登入。  <br/> |
|**CallPriority** <br/> |Nvarchar (256)   <br/> |會話的呼叫優先順序。  <br/> |
|**FromUserFlag** <br/> |Smallint  <br/> |會指出啟動會話之使用者的屬性。 以下為允許的屬性定義：  <br/> 0x01 - 與桌上電話整合  <br/> |
|**ToUserFlag** <br/> |Smallint  <br/> |會指出啟動會話之使用者的屬性。 以下為允許的屬性定義：  <br/> 0x01 - 與桌上電話整合  <br/> |
|**CallFlag** <br/> |Smallint  <br/> |指出通話屬性。以下為允許的屬性定義：  <br/> 0x01 - 重試工作階段 1  <br/> 0x02-代理程式代表回應群組所撥打的通話  <br/> |
|**Location** <br/> |Varchar (max)   <br/> |緊急電話的位置。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> |供監控服務內部使用。  <br/> 此欄位是在商務用 Skype Server 2015 中引入。  <br/> |
   

