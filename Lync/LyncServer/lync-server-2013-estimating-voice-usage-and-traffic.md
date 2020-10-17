---
title: Lync Server 2013：評估語音使用方式和流量
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Estimating voice usage and traffic
ms:assetid: 621b08fb-f894-4d91-ac38-e443401b098b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398439(v=OCS.15)
ms:contentKeyID: 48184332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9541619578c69a571d93d8c4960b3ecb33476027
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532000"
---
# <a name="estimating-voice-usage-and-traffic-for-lync-server-2013"></a><span data-ttu-id="318ae-102">評估 Lync Server 2013 的語音使用狀況和流量</span><span class="sxs-lookup"><span data-stu-id="318ae-102">Estimating voice usage and traffic for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="318ae-103">_**主題上次修改日期：** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="318ae-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="318ae-104">Microsoft Lync Server 2013，規劃工具使用下列度量，評估每個網站的使用者流量，以及支援該流量所需的埠數目。</span><span class="sxs-lookup"><span data-stu-id="318ae-104">The Microsoft Lync Server 2013, Planning Tool uses the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>

  - <span></span>  
    <span data-ttu-id="318ae-105">針對**輕型流量** (每位使用者每小時一個 PSTN 通話)，估計每個連接埠 15 位使用者。</span><span class="sxs-lookup"><span data-stu-id="318ae-105">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>

  - <span></span>  
    <span data-ttu-id="318ae-106">針對**中型流量** (每位使用者每小時兩個 PSTN 通話)，估計每個連接埠 10 位使用者。</span><span class="sxs-lookup"><span data-stu-id="318ae-106">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>

  - <span></span>  
    <span data-ttu-id="318ae-107">針對**重型流量** (每位使用者每小時三個以上的 PSTN 通話)，估計每個連接埠 5 位使用者。</span><span class="sxs-lookup"><span data-stu-id="318ae-107">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>

<span data-ttu-id="318ae-108">接下來的埠數目會決定所需的轉送伺服器和閘道數目。</span><span class="sxs-lookup"><span data-stu-id="318ae-108">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="318ae-109">公用交換電話網路 (PSTN) 閘道，大多數的組織都會考慮從兩個埠的大小部署至多達960埠的範圍。</span><span class="sxs-lookup"><span data-stu-id="318ae-109">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="318ae-110"> (甚至會有較大的閘道，但是主要是由電話語音服務提供者使用。 ) </span><span class="sxs-lookup"><span data-stu-id="318ae-110">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>

<span data-ttu-id="318ae-p102">例如，有 10,000 位使用者及中型流量的組織需要 1000 個連接埠。需要的閘道數目會等於閘道總容量所決定的必要連接埠總數。</span><span class="sxs-lookup"><span data-stu-id="318ae-p102">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

