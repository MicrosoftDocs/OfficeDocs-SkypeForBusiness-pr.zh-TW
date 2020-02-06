---
title: '[註冊] 視圖'
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
ms.assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
description: '[註冊] 視圖儲存使用者註冊的相關資訊。 此視圖是在 Lync Server 2013 中推出。'
ms.openlocfilehash: 0ee19d4addae9ee7318828c4ab294dc15bd72f86
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814951"
---
# <a name="registration-view"></a>[註冊] 視圖
 
[註冊] 視圖儲存使用者註冊的相關資訊。 此視圖是在 Lync Server 2013 中推出。
  
|**左欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |會話要求的時間。 與 SessionIdSeq 搭配使用，可唯一識別會話。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |識別會話的識別碼編號。 與 SessionIdTime 搭配使用，可唯一識別會話。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**RegisterTime** <br/> |datetime  <br/> |發生註冊的時間。  <br/> |
|**UserUri** <br/> |Nvarchar （450）  <br/> |已登錄之使用者的 URI。  <br/> |
|**UserUriType** <br/> |Nvarchar （256）  <br/> |已登錄之使用者的 URI 類型。 如需詳細資訊，請參閱[UriTypes 資料表](uritypes.md)。 <br/> |
|**UserTenant** <br/> |Nvarchar （256）  <br/> |已註冊的使用者租使用者。 如需詳細資訊，請參閱[承租人資料表](tenants.md)。 <br/> |
|**EndpointId** <br/> |uniqueidentifier  <br/> |已登錄之使用者之端點的唯一識別碼。  <br/> |
|**EndpointEra** <br/> |uniqueidentifier  <br/> |唯一識別碼，用於區分涉及相同使用者和同一個端點的登記。  <br/> |
|**DeRegisterType** <br/> |datetime  <br/> |發生取消註冊的時間。  <br/> |
|**DeRegisterReason** <br/> |Nvarchar （256）  <br/> |取消註冊的原因。  <br/> |
|**ClientVersion** <br/> |Nvarchar （256）  <br/> |註冊的使用者所使用的用戶端版本。  <br/> |
|**ClientType** <br/> |int  <br/> |已註冊的使用者所使用的用戶端。 如需詳細資訊，請參閱[UserAgentDef 資料表](useragentdef.md)。 <br/> |
|**ClientCategory** <br/> |Nvarchar （64）  <br/> |已註冊的使用者所使用的用戶端類別。  <br/> |
|**IpAddress** <br/> |Nvarchar （256）  <br/> |使用者註冊的 IP 位址。 這可能是 IPv4 或 IPv6 位址。  <br/> |
|**DialogId** <br/> |varstring （775）  <br/> |SIP 對話方塊識別碼。 的格式為：  <br/> 對話方塊; 從標籤; 到標籤  <br/> |
|**ResponseCode** <br/> |int  <br/> |SIP 回應程式碼加入會話邀請。 這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。 如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。  <br/> |
|**DiagnosticId** <br/> |int  <br/> |從 SIP 標頭捕獲的診斷 ID。  <br/> |
|**註冊機構** <br/> |Nvarchar （256）  <br/> |註冊機構的 FQDN。  <br/> |
|**集區** <br/> |Nvarchar （256）  <br/> |捕獲會話資料之池的 FQDN。  <br/> |
|**EdgeServer** <br/> |Nvarchar （256）  <br/> |已註冊的使用者所使用的邊緣伺服器 FQDN。  <br/> |
|**IsInternal** <br/> |稍微  <br/> |指示使用者是否從內部網路登入。  <br/> |
|**IsUserServiceAvailable** <br/> |稍微  <br/> |指示在註冊時間是否可以使用 UserService。  <br/> |
|**IsPrimaryRegistrar** <br/> |稍微  <br/> |指出註冊是否與主要註冊機構一起使用。  <br/> |
|**DeviceMacAddress** <br/> |Bigint  <br/> |已註冊的裝置 MAC 位址。  <br/> |
|**DeviceManufacturer** <br/> |Nvarchar （256）  <br/> |已註冊裝置的製造商。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](manufacturers.md)的 [製造商] 資料表。 <br/> |
|**DeviceHardwareVersion** <br/> |Nvarchar （256）  <br/> |已註冊裝置的硬體版本。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](hardwareversions.md)的 [HardwareVersions] 資料表。 <br/> |
   

