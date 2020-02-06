---
title: 登錄表格
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
ms.assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
description: 每個記錄代表一個使用者註冊事件。
ms.openlocfilehash: bca31b85a0b88854760c2a79528792ee82bd272e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814941"
---
# <a name="registration-table"></a>登錄表格
 
每個記錄代表一個使用者註冊事件。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主要、外部  <br/> |會話要求的時間。 與**SessionIdSeq**搭配使用，可唯一識別會話。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主要、外部  <br/> |識別會話的識別碼編號。 與**SessionIdTime**搭配使用，可唯一識別會話。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**UserId** <br/> |int  <br/> |外  <br/> |使用者識別碼。 如需詳細資訊，請參閱 [[使用者] 表格](users.md)。 <br/> |
|**EndpointId** <br/> |uniqueidentifier  <br/> ||識別註冊端點的 GUID。 通常，來自同一個使用者的同一部電腦的 register 事件將會有相同的端點 ID。 不同的電腦都有不同的端點識別碼。  <br/> |
|**EndpointEra** <br/> |uniqueIdentifier  <br/> ||用於區分涉及相同使用者和同一個端點的登記的識別碼。  <br/> 此欄位是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**ClientVersionId** <br/> |int  <br/> |外  <br/> |目前使用者的用戶端版本。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](clientversions.md)的 [ClientVersions] 資料表。 <br/> |
|**RegistrarId** <br/> |int  <br/> |外  <br/> |註冊所用的註冊機構伺服器 ID。 如需詳細資訊，請參閱 [[伺服器] 資料表](servers.md)。 <br/> |
|**PoolId** <br/> |int  <br/> |外  <br/> |捕獲會話的池 ID。 如需詳細資訊，請參閱 [[彙集] 資料表](pools.md)。 <br/> |
|**EdgeServerId** <br/> |int  <br/> |外  <br/> |註冊即將進行的邊緣伺服器。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](edgeservers.md)的 [EdgeServers] 資料表。 <br/> |
|**IsInternal** <br/> |稍微  <br/> ||使用者是否已從內部登入。  <br/> |
|**IsUserServiceAvailable** <br/> |稍微  <br/> ||UserService 是否可供使用。  <br/> |
|**IsPrimaryRegistrar** <br/> |稍微  <br/> ||是否註冊到主要註冊機構。  <br/> |
|**IsPrimaryRegistrarCentral** <br/> |稍微  <br/> ||指出使用者是否已向 survivable 分支裝置註冊。  <br/> 此欄位是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**RegisterTime** <br/> |datetime  <br/> ||註冊時間。  <br/> |
|**DeRegisterTime** <br/> |datetime  <br/> ||取消註冊時間。  <br/> |
|**ResponseCode** <br/> |int  <br/> ||寄存器要求的回應代碼。  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||寄存器要求的診斷識別碼。 這表示診斷資訊類型。  <br/> |
|**DeviceId** <br/> |int  <br/> |外  <br/> |寄存器要求所來自的裝置。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](devices.md)的 [裝置] 資料表。 <br/> |
|**DeRegisterTypeId** <br/> |Tinyint  <br/> |外  <br/> |取消註冊的原因，例如「使用者已啟動」、「註冊已過期」、「用戶端失敗」等等。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](deregistertype.md)的 [DeRegisterType] 資料表。 <br/> |
|**IPAddress** <br/> |Nvarchar （256）  <br/> ||使用者註冊之端點的 IP 位址。 這可以是 IPv4 位址或 IPv6 位址。  <br/> 此欄位是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供監視服務內部使用。  <br/> 此欄位是在商務用 Skype Server 2015 中推出。  <br/> |
   

