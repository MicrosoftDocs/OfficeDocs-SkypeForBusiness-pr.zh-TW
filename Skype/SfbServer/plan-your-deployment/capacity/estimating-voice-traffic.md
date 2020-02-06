---
title: 估計商務用 Skype Server 的語音使用與流量
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 621b08fb-f894-4d91-ac38-e443401b098b
description: 您可以使用下列度量單位來估計每個網站的使用者流量，以及支援該流量所需的埠數。
ms.openlocfilehash: f324a3030a8265288a30062fdfc1040a1aea8349
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816062"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a>估計商務用 Skype Server 的語音使用與流量
 
您可以使用下列度量單位來估計每個網站的使用者流量，以及支援該流量所需的埠數。
  
> 對於**輕型流量**（每個使用者每小時一個 PSTN 通話），請在每個埠上見15個使用者。
> 
> 針對**中型交通**（每位使用者每小時2個 PSTN 通話），圖10每個埠的使用者數。
> 
> 對於**大量流量**（3個或更多每個使用者每小時的 PSTN 通話），請依圖5每個埠的使用者。
    
接下來的埠數會決定要使用的中繼伺服器和閘道數目。 大多陣列織考慮將範圍從2個埠部署到最多960個埠的公用交換電話網絡（PSTN）閘道。 （甚至是更大的閘道，但主要是由電話服務提供者使用。）
  
例如，有10000使用者和中型交通的組織需要1000埠。 所需的閘道數目會等於由閘道總容量決定所需的埠總數。
  

