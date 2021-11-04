---
title: VoIPDetails view
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: VoIPDetails 檢視會儲存對等工作階段的相關資訊，其中至少有一個使用者是 VoIP 使用者。 此視圖已引進于 Microsoft Lync Server 2013。
ms.openlocfilehash: 8e647f79953efc507e63aa4f19e6f1deba53d7a1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765081"
---
# <a name="voipdetails-view"></a>VoIPDetails view
 
VoIPDetails 檢視會儲存對等工作階段的相關資訊，其中至少有一個使用者是 VoIP 使用者。 此視圖已引進于 Microsoft Lync Server 2013。
  
> [!NOTE]
> VoIPDetails view 包含 [SessionDetails 視圖](sessiondetails-0.md) 中的所有欄，此外還會包含下列欄。
  
|**欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|**FromPhone** <br/> |Nvarchar (450)   <br/> |起始工作階段之使用者的電話 URI。  <br/> |
|**ToPhone** <br/> |Nvarchar (450)   <br/> |參加工作階段之使用者的電話 URI。  <br/> |
|**DisconnectedByUri** <br/> |Nvarchar (450)   <br/> |中斷連線工作階段之使用者的 URI。  <br/> |
|**DisconnectedByUriType** <br/> |Nvarchar (256)   <br/> |中斷連線工作階段之使用者的 URI 類型。 如需詳細資訊，請參閱 [UriTypes 表格](uritypes.md) 。 <br/> |
|**DisconnectedByTenant** <br/> |Nvarchar (256)   <br/> |中斷連線工作階段之使用者的租用戶。  <br/> |
|**DisconnectedByPhone** <br/> |Nvarchar (450)   <br/> |中斷連線工作階段之使用者的電話 URI。  <br/> |
|**FromMediationServer** <br/> |Nvarchar (256)   <br/> |起始工作階段之使用者所使用的中繼伺服器。  <br/> |
|**ToMediationServer** <br/> |Nvarchar (256)   <br/> |參加工作階段之使用者所使用的中繼伺服器。  <br/> |
|**FromGateway** <br/> |Nvarchar (256)   <br/> |起始工作階段之使用者所使用的閘道。  <br/> |
|**ToGateway** <br/> |Nvarchar (256)   <br/> |參加工作階段之使用者所使用的閘道。  <br/> |
   

