---
title: VoipDetails 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
description: 每個記錄代表 1 2 方通話, 其中至少有一個使用者是 VoIP 使用者。
ms.openlocfilehash: 7f0be2fb2f14e34cbe989d5912db1f66d3d65d18
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192775"
---
# <a name="voipdetails-table"></a>VoipDetails 表格
 
每個記錄代表 1 2 方通話, 其中至少有一個使用者是 VoIP 使用者。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |首選  <br/> |會話要求的時間。 與**SessionIdSeq**搭配使用, 可唯一識別會話。 如需詳細資訊, 請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |首選  <br/> |識別會話的識別碼編號。 與**SessionIdTime**搭配使用, 可唯一識別會話。 如需詳細資訊, 請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**FromNumberId** <br/> |int  <br/> |外  <br/> |來電者的**PhoneId** 。 如需詳細資訊, 請參閱[手機表格](phones.md)。 如果 not Null 且**FromGatewayId**不是 null, 則呼叫者是 PSTN 使用者。 <br/> |
|**ConnectedNumberId** <br/> |int  <br/> |外  <br/> |呼叫接收器的**PhoneId** 。 如需詳細資訊, 請參閱[手機表格](phones.md)。 如果 not Null 且**ToGatewayId**不是 null, 則呼叫接收器是 PSTN 使用者。 <br/> |
|**FromMediationServerId** <br/> |int  <br/> |外  <br/> |呼叫來源的中繼伺服器。 如需詳細資訊, 請參閱[MediationServers 資料表](mediationservers.md)。 <br/> |
|**ToMediationServerId** <br/> |int  <br/> |外  <br/> |呼叫的中繼伺服器將要移至。 如需詳細資訊, 請參閱[MediationServers 資料表](mediationservers.md)。 <br/> |
|**FromGatewayId** <br/> |int  <br/> |外  <br/> |通話來源的閘道。 如需詳細資訊, 請參閱[商務用 Skype Server 2015 中的 [閘道] 資料表](gateways.md)。 <br/> |
|**ToGatewayId** <br/> |int  <br/> |外  <br/> |通話的閘道。 如需詳細資訊, 請參閱[商務用 Skype Server 2015 中的 [閘道] 資料表](gateways.md)。 <br/> |
|**DisconnectedbyURIId** <br/> |int  <br/> |外  <br/> |中斷通話的使用者 URI (如果使用者有 URI)。 如需詳細資訊, 請參閱 [[使用者] 表格](users.md)。 <br/> |
|**DisconnectedbyPhoneId** <br/> |int  <br/> |外  <br/> |中斷通話的電話的識別碼已從手機中斷連線。 如需詳細資訊, 請參閱[手機表格](phones.md)。 <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供監視服務內部使用。  <br/> 此欄位是在商務用 Skype Server 2015 中推出。  <br/> |
   

