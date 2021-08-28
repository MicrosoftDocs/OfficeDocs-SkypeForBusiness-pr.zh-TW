---
title: 註冊表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
description: 每筆記錄都代表一個使用者註冊事件。
ms.openlocfilehash: ed8ce9f160f42384548a01d2cd6c74b3b24e60f1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627775"
---
# <a name="registration-table"></a>註冊表
 
每筆記錄都代表一個使用者註冊事件。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主要，外部  <br/> |工作階段要求的時間。 其會與 **SessionIdSeq** 搭配使用，專門用於識別工作階段。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主要，外部  <br/> |用來識別工作階段的識別碼。 會與 **SessionIdTime** 搭配使用，專門用於識別工作階段。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 <br/> |
|**UserId** <br/> |int  <br/> |Foreign  <br/> |使用者識別碼。 如需詳細資訊，請參閱 [Users 表格](users.md) 。 <br/> |
|**EndpointId** <br/> |唯一  <br/> ||識別註冊端點的 GUID。通常，來自相同使用者電腦的註冊事件會具備相同的端點識別碼，不同的機器則會有不同的端點識別碼。  <br/> |
|**EndpointEra** <br/> |唯一  <br/> ||用於區分相同使用者和相同端點相關之登錄的識別碼。  <br/> 此欄位是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**ClientVersionId** <br/> |int  <br/> |Foreign  <br/> |目前使用者的用戶端版本。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的 ClientVersions 表格](clientversions.md)。 <br/> |
|**RegistrarId** <br/> |int  <br/> |Foreign  <br/> |登錄伺服器用於登錄的識別碼。 如需詳細資訊，請參閱 [Servers 表格](servers.md) 。 <br/> |
|**PoolId** <br/> |int  <br/> |Foreign  <br/> |擷取工作階段所在集區的識別碼。 如需詳細資訊，請參閱 [pool 表格](pools.md) 。 <br/> |
|**EdgeServerId** <br/> |int  <br/> |Foreign  <br/> |登錄通過的 Edge Server。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的 EdgeServers 表格](edgeservers.md)。 <br/> |
|**IsInternal** <br/> |位  <br/> ||使用者是否從內部登入。  <br/> |
|**IsUserServiceAvailable** <br/> |位  <br/> ||UserService 是否可供使用。  <br/> |
|**IsPrimaryRegistrar** <br/> |位  <br/> ||是否登錄至主要登錄器。  <br/> |
|**IsPrimaryRegistrarCentral** <br/> |位  <br/> ||表示是否使用 Survivable Branch Appliance 登錄使用者。  <br/> 此欄位是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RegisterTime** <br/> |datetime  <br/> ||登錄時間。  <br/> |
|**DeRegisterTime** <br/> |datetime  <br/> ||解除登錄時間。  <br/> |
|**ResponseCode** <br/> |int  <br/> ||登錄要求的回應碼。  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||登錄要求的診斷識別碼。這會指出診斷資訊類型。  <br/> |
|**DeviceId** <br/> |int  <br/> |Foreign  <br/> |登錄要求的來源裝置。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的裝置表格](devices.md)。 <br/> |
|**DeRegisterTypeId** <br/> |Tinyint  <br/> |Foreign  <br/> |取消註冊的原因，例如「使用者已初始化」、「註冊到期」、「用戶端失敗」等等。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的 DeRegisterType 表格](deregistertype.md)。 <br/> |
|**IPAddress** <br/> |Nvarchar (256)   <br/> ||使用者登錄所使用的端點 IP 位址。 可以是 IPv4 位址或 IPv6 位址。  <br/> 此欄位是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供監控服務內部使用。  <br/> 此欄位是在商務用 Skype Server 2015 中引入。  <br/> |
   

