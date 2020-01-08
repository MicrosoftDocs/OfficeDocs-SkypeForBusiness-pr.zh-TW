---
title: Lync Server 2013：幹線間路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Inter-trunk routing
ms:assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721940(v=OCS.15)
ms:contentKeyID: 49733877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 204402ba6620fa75b64bb9710ce979b44b63f412
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975692"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="inter-trunk-routing-in-lync-server-2013"></a><span data-ttu-id="76d3e-102">Lync Server 2013 中的中繼間路由</span><span class="sxs-lookup"><span data-stu-id="76d3e-102">Inter-trunk routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76d3e-103">_**主題上次修改日期：** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="76d3e-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="76d3e-104">Lync Server 2013 提供基本的會話管理，並支援 intertrunk 路由。</span><span class="sxs-lookup"><span data-stu-id="76d3e-104">Lync Server 2013 provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="76d3e-105">這項新功能可讓 Lync Server 提供對下游電話系統的呼叫控制功能。</span><span class="sxs-lookup"><span data-stu-id="76d3e-105">This new capability enables Lync Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="76d3e-106">Intertrunk 路由可以將 IP PBX 互連至公用的交換電話網絡（PSTN）閘道，讓來自私人分支 exchange （PBX）電話的呼叫可以路由到 PSTN，而且傳入 PSTN 呼叫可以路由到 PBX 電話。</span><span class="sxs-lookup"><span data-stu-id="76d3e-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="76d3e-107">同樣地，Lync Server 可以相互連接兩個或多個 IP PBX 系統，以便在不同 IP PBX 系統的 PBX 手機之間進行呼叫和接收。</span><span class="sxs-lookup"><span data-stu-id="76d3e-107">Similarly, Lync Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span>

<span data-ttu-id="76d3e-108">下圖說明 Lync Server 2013，提供 PSTN 閘道與 IP PBX 之間的 interconnectivity。</span><span class="sxs-lookup"><span data-stu-id="76d3e-108">The following figure illustrates Lync Server 2013 providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

<span data-ttu-id="76d3e-109">連線![pstn 閘道/IP pbx 圖的 Lync server]連接(images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "pstn 閘道/ip pbx 圖表的 lync server")</span><span class="sxs-lookup"><span data-stu-id="76d3e-109">![Lync Server connecting PSTN gateway/IP-PBX diagram](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server connecting PSTN gateway/IP-PBX diagram")</span></span>

<span data-ttu-id="76d3e-110">下圖說明連接兩個 IP PBX 系統的 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="76d3e-110">The next figure illustrates Lync Server 2013 connecting two IP-PBX systems.</span></span>

<span data-ttu-id="76d3e-111">![Lync server 互連 ip-pax 系統圖表](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "LYNC server 互連 ip-pax 系統圖表")</span><span class="sxs-lookup"><span data-stu-id="76d3e-111">![Lync Server interconnecting IP-PAX systems diagram](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server interconnecting IP-PAX systems diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

