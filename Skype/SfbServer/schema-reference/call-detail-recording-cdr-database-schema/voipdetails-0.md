---
title: VoipDetails 表格
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
localization_priority: Normal
ms.assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
description: 每筆記錄代表一通雙方通話，其中至少一位使用者為 VoIP 使用者。
ms.openlocfilehash: 900598c99965292e7d349520cc2dfa55443bb5a9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813093"
---
# <a name="voipdetails-table"></a>VoipDetails 表格
 
每筆記錄代表一通雙方通話，其中至少一位使用者為 VoIP 使用者。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主要  <br/> |工作階段要求的時間。 其會與 **SessionIdSeq** 搭配使用，專門用於識別工作階段。 如需詳細資訊，請參閱 [商務用 Skype Server 2015 中的對話方塊表格](dialogs.md) 。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主要  <br/> |用來識別工作階段的識別碼。 會與 **SessionIdTime** 搭配使用，專門用於識別工作階段。 如需詳細資訊，請參閱 [商務用 Skype Server 2015 中的對話方塊表格](dialogs.md) 。 <br/> |
|**FromNumberId** <br/> |int  <br/> |Foreign  <br/> |發話者的 **PhoneId**。 如需詳細資訊，請參閱 [電話表格](phones.md) 。 若非 NULL，且 **FromGatewayId** 亦非 NULL，代表發話者為 PSTN 使用者。 <br/> |
|**ConnectedNumberId** <br/> |int  <br/> |Foreign  <br/> |受話者的 **PhoneId**。 如需詳細資訊，請參閱 [電話表格](phones.md) 。 若非 NULL，且 **ToGatewayId** 亦非 NULL，代表受話者為 PSTN 使用者。 <br/> |
|**FromMediationServerId** <br/> |int  <br/> |Foreign  <br/> |通話的來源中繼伺服器。 如需詳細資訊，請參閱 [MediationServers 表格](mediationservers.md) 。 <br/> |
|**ToMediationServerId** <br/> |int  <br/> |Foreign  <br/> |通話的目標中繼伺服器。 如需詳細資訊，請參閱 [MediationServers 表格](mediationservers.md) 。 <br/> |
|**FromGatewayId** <br/> |int  <br/> |Foreign  <br/> |通話的來源閘道。 如需詳細資訊，請參閱 [商務用 Skype Server 2015 中的閘道表格](gateways.md) 。 <br/> |
|**ToGatewayId** <br/> |int  <br/> |Foreign  <br/> |通話的目標閘道。 如需詳細資訊，請參閱 [商務用 Skype Server 2015 中的閘道表格](gateways.md) 。 <br/> |
|**DisconnectedbyURIId** <br/> |int  <br/> |Foreign  <br/> |中斷通話之使用者的 URI (若該使用者有 URI 的話)。 如需詳細資訊，請參閱 [Users 表格](users.md) 。 <br/> |
|**DisconnectedbyPhoneId** <br/> |int  <br/> |Foreign  <br/> |中斷通話之電話的識別碼 (若通話是從電話所中斷的話)。 如需詳細資訊，請參閱 [電話表格](phones.md) 。 <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供監控服務內部使用。  <br/> 此欄位已引進商務用 Skype Server 2015。  <br/> |
   

