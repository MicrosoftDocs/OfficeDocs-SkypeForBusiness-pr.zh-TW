---
title: 評估商務用 Skype Server 的語音使用方式和流量
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 621b08fb-f894-4d91-ac38-e443401b098b
description: 您可以使用下列度量，評估每個網站的使用者流量，以及支援該流量所需的埠數目。
ms.openlocfilehash: c631361a7ef6d4706632f59366adac3384a6d255
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827683"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a>評估商務用 Skype Server 的語音使用方式和流量
 
您可以使用下列度量，評估每個網站的使用者流量，以及支援該流量所需的埠數目。
  
> 針對 **輕型流量** (每位使用者每小時一個 PSTN 通話)，估計每個連接埠 15 位使用者。
> 
> 針對 **中型流量** (每位使用者每小時兩個 PSTN 通話)，估計每個連接埠 10 位使用者。
> 
> 針對 **重型流量** (每位使用者每小時三個以上的 PSTN 通話)，估計每個連接埠 5 位使用者。
    
接下來的埠數目會決定所需的轉送伺服器和閘道數目。 公用交換電話網路 (PSTN) 閘道，大多數的組織都會考慮從兩個埠的大小部署至多達960埠的範圍。  (甚至會有較大的閘道，但是主要是由電話語音服務提供者使用。 ) 
  
例如，有 10,000 位使用者及中型流量的組織需要 1000 個連接埠。需要的閘道數目會等於閘道總容量所決定的必要連接埠總數。
  

