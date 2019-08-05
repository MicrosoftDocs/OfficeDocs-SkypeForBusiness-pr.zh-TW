---
title: VoIPDetails 視圖
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: '[VoIPDetails] 視圖儲存點對點工作階段的相關資訊, 其中至少有一個使用者是 VoIP 使用者。 此視圖已在 Microsoft Lync Server 2013 中推出。'
ms.openlocfilehash: 7f5f1e3cf1540e1a12a9365753e494ff2d8a371e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192773"
---
# <a name="voipdetails-view"></a>VoIPDetails 視圖
 
[VoIPDetails] 視圖儲存點對點工作階段的相關資訊, 其中至少有一個使用者是 VoIP 使用者。 此視圖已在 Microsoft Lync Server 2013 中推出。
  
> [!NOTE]
> [VoIPDetails] 視圖會包含 [ [SessionDetails] 視圖](sessiondetails-0.md)中的所有資料行, 以及下方所列的欄。
  
|**左欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|**FromPhone** <br/> |Nvarchar (450)  <br/> |啟動會話之使用者的電話 URI。  <br/> |
|**ToPhone** <br/> |Nvarchar (450)  <br/> |加入會話之使用者的電話 URI。  <br/> |
|**DisconnectedByUri** <br/> |Nvarchar (450)  <br/> |中斷會話的使用者 URI。  <br/> |
|**DisconnectedByUriType** <br/> |Nvarchar (256)  <br/> |中斷會話的使用者 URI 類型。 如需詳細資訊, 請參閱[UriTypes 資料表](uritypes.md)。 <br/> |
|**DisconnectedByTenant** <br/> |Nvarchar (256)  <br/> |中斷會話的使用者租使用者。  <br/> |
|**DisconnectedByPhone** <br/> |Nvarchar (450)  <br/> |中斷會話的使用者的電話 URI。  <br/> |
|**FromMediationServer** <br/> |Nvarchar (256)  <br/> |啟動會話的使用者所使用的中繼伺服器。  <br/> |
|**ToMediationServer** <br/> |Nvarchar (256)  <br/> |加入會話的使用者所使用的中繼伺服器。  <br/> |
|**FromGateway** <br/> |Nvarchar (256)  <br/> |啟動會話的使用者所使用的閘道。  <br/> |
|**ToGateway** <br/> |Nvarchar (256)  <br/> |加入會話的使用者所使用的閘道。  <br/> |
   

