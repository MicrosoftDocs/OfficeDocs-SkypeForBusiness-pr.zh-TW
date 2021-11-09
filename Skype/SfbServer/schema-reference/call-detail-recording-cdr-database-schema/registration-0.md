---
title: 註冊視圖
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
description: '[註冊] 視圖會儲存使用者註冊的相關資訊。 此視圖已引進 Lync Server 2013。'
ms.openlocfilehash: 62cfed96994f11ec7393bacc1e0b77edbe3374e7
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60842665"
---
# <a name="registration-view"></a>註冊視圖
 
[註冊] 視圖會儲存使用者註冊的相關資訊。 此視圖已引進 Lync Server 2013。
  
|**欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |工作階段要求的時間。 與 SessionIdSeq 搭配使用，以唯一識別工作階段。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |識別工作階段的 ID 號碼。 與 SessionIdTime 搭配使用，以唯一識別工作階段。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 <br/> |
|**RegisterTime** <br/> |datetime  <br/> |發生註冊的時間。  <br/> |
|**UserUri** <br/> |Nvarchar (450)   <br/> |註冊之使用者的 URI。  <br/> |
|**UserUriType** <br/> |Nvarchar (256)   <br/> |註冊之使用者的 URI 類型。 如需詳細資訊，請參閱 [UriTypes 表格](uritypes.md) 。 <br/> |
|**UserTenant** <br/> |Nvarchar (256)   <br/> |註冊的使用者租使用者。 如需詳細資訊，請參閱 [承租人資料表](tenants.md) 。 <br/> |
|**EndpointId** <br/> |唯一  <br/> |使用者已註冊之端點的唯一識別碼。  <br/> |
|**EndpointEra** <br/> |唯一  <br/> |唯一識別碼，用來區分包含相同使用者和相同端點的註冊。  <br/> |
|**DeRegisterType** <br/> |datetime  <br/> |發生取消註冊的時間。  <br/> |
|**DeRegisterReason** <br/> |Nvarchar (256)   <br/> |取消註冊的原因。  <br/> |
|**Microsoft.rtc.management.writableconfig.policy.clientversion.rule** <br/> |Nvarchar (256)   <br/> |註冊的使用者所使用的用戶端版本。  <br/> |
|**ClientType** <br/> |int  <br/> |註冊的使用者所使用的用戶端。 如需詳細資訊，請參閱 [UserAgentDef 表格](useragentdef.md) 。 <br/> |
|**ClientCategory** <br/> |Nvarchar (64)   <br/> |註冊的使用者所使用的用戶端類別。  <br/> |
|**址** <br/> |Nvarchar (256)   <br/> |使用者註冊的 IP 位址。 這可以是 IPv4 或 IPv6 位址。  <br/> |
|**DialogId** <br/> |varstring (775)   <br/> |SIP 對話方塊識別碼。 格式為：  <br/> dialog; 從-標籤; to-標記  <br/> |
|**ResponseCode** <br/> |int  <br/> |工作階段邀請的 SIP 回應碼。此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。  <br/> |
|**DiagnosticId** <br/> |int  <br/> |從 SIP 標頭擷取而來的診斷識別碼。  <br/> |
|**處長** <br/> |Nvarchar (256)   <br/> |註冊機的 FQDN。  <br/> |
|**集區** <br/> |Nvarchar (256)   <br/> |擷取工作階段適用之資料的集區 FQDN。  <br/> |
|**Edgeserver atl-edge** <br/> |Nvarchar (256)   <br/> |註冊之使用者所使用的 Edge Server FQDN。  <br/> |
|**IsInternal** <br/> |位  <br/> |指出使用者是否會從內部網路登入。  <br/> |
|**IsUserServiceAvailable** <br/> |位  <br/> |會指出註冊時是否可使用 UserService。  <br/> |
|**IsPrimaryRegistrar** <br/> |位  <br/> |會指出註冊是否與主要註冊機。  <br/> |
|**DeviceMacAddress** <br/> |Bigint  <br/> |已登錄裝置的 MAC 位址。  <br/> |
|**DeviceManufacturer** <br/> |Nvarchar (256)   <br/> |已登錄裝置的製造商。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的製造商表格](manufacturers.md)。 <br/> |
|**DeviceHardwareVersion** <br/> |Nvarchar (256)   <br/> |已登錄裝置的硬體版本。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的 HardwareVersions 表格](hardwareversions.md)。 <br/> |
   

