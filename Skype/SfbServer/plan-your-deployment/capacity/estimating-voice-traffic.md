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
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a><span data-ttu-id="a05a0-103">評估商務用 Skype Server 的語音使用方式和流量</span><span class="sxs-lookup"><span data-stu-id="a05a0-103">Estimating voice usage and traffic for Skype for Business Server</span></span>
 
<span data-ttu-id="a05a0-104">您可以使用下列度量，評估每個網站的使用者流量，以及支援該流量所需的埠數目。</span><span class="sxs-lookup"><span data-stu-id="a05a0-104">You can use the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="a05a0-105">針對 **輕型流量** (每位使用者每小時一個 PSTN 通話)，估計每個連接埠 15 位使用者。</span><span class="sxs-lookup"><span data-stu-id="a05a0-105">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
> 
> <span data-ttu-id="a05a0-106">針對 **中型流量** (每位使用者每小時兩個 PSTN 通話)，估計每個連接埠 10 位使用者。</span><span class="sxs-lookup"><span data-stu-id="a05a0-106">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
> 
> <span data-ttu-id="a05a0-107">針對 **重型流量** (每位使用者每小時三個以上的 PSTN 通話)，估計每個連接埠 5 位使用者。</span><span class="sxs-lookup"><span data-stu-id="a05a0-107">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="a05a0-108">接下來的埠數目會決定所需的轉送伺服器和閘道數目。</span><span class="sxs-lookup"><span data-stu-id="a05a0-108">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="a05a0-109">公用交換電話網路 (PSTN) 閘道，大多數的組織都會考慮從兩個埠的大小部署至多達960埠的範圍。</span><span class="sxs-lookup"><span data-stu-id="a05a0-109">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="a05a0-110"> (甚至會有較大的閘道，但是主要是由電話語音服務提供者使用。 ) </span><span class="sxs-lookup"><span data-stu-id="a05a0-110">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="a05a0-p102">例如，有 10,000 位使用者及中型流量的組織需要 1000 個連接埠。需要的閘道數目會等於閘道總容量所決定的必要連接埠總數。</span><span class="sxs-lookup"><span data-stu-id="a05a0-p102">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  

