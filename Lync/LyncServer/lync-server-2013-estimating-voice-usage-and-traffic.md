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
ms.openlocfilehash: 06093893c5de9a08322e1577fbbbe6779d4209cc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="estimating-voice-usage-and-traffic-for-lync-server-2013"></a><span data-ttu-id="2808b-102">針對 Lync Server 2013 評估語音使用方式和流量</span><span class="sxs-lookup"><span data-stu-id="2808b-102">Estimating voice usage and traffic for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2808b-103">_**主題上次修改日期：** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="2808b-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="2808b-104">Microsoft Lync Server 2013、規劃工具會使用下列度量來估計每個網站的使用者流量，以及支援該流量所需的埠數。</span><span class="sxs-lookup"><span data-stu-id="2808b-104">The Microsoft Lync Server 2013, Planning Tool uses the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>

  - <span></span>  
    <span data-ttu-id="2808b-105">對於**輕型流量**（每個使用者每小時一個 PSTN 通話），請在每個埠上見15個使用者。</span><span class="sxs-lookup"><span data-stu-id="2808b-105">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>

  - <span></span>  
    <span data-ttu-id="2808b-106">針對**中型交通**（每位使用者每小時2個 PSTN 通話），圖10每個埠的使用者數。</span><span class="sxs-lookup"><span data-stu-id="2808b-106">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>

  - <span></span>  
    <span data-ttu-id="2808b-107">對於**大量流量**（3個或更多每個使用者每小時的 PSTN 通話），請依圖5每個埠的使用者。</span><span class="sxs-lookup"><span data-stu-id="2808b-107">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>

<span data-ttu-id="2808b-108">接下來的埠數會決定要使用的中繼伺服器和閘道數目。</span><span class="sxs-lookup"><span data-stu-id="2808b-108">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="2808b-109">大多陣列織考慮將範圍從2個埠部署到最多960個埠的公用交換電話網絡（PSTN）閘道。</span><span class="sxs-lookup"><span data-stu-id="2808b-109">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="2808b-110">（甚至是更大的閘道，但主要是由電話服務提供者使用。）</span><span class="sxs-lookup"><span data-stu-id="2808b-110">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>

<span data-ttu-id="2808b-111">例如，有10000使用者和中型交通的組織需要1000埠。</span><span class="sxs-lookup"><span data-stu-id="2808b-111">For example, an organization with 10,000 users and medium traffic would require 1000 ports.</span></span> <span data-ttu-id="2808b-112">所需的閘道數目會等於由閘道總容量決定所需的埠總數。</span><span class="sxs-lookup"><span data-stu-id="2808b-112">The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

