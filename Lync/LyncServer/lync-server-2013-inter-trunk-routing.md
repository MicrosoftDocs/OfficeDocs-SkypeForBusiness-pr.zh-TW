---
title: Lync Server 2013：主幹間路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Inter-trunk routing
ms:assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721940(v=OCS.15)
ms:contentKeyID: 49733877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de302ec9bfbf81ea1d5c43ec568f2a0c0f6c19bf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498490"
---
# <a name="inter-trunk-routing-in-lync-server-2013"></a><span data-ttu-id="c0645-102">Lync Server 2013 中的主幹間路由</span><span class="sxs-lookup"><span data-stu-id="c0645-102">Inter-trunk routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0645-103">_**主題上次修改日期：** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="c0645-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="c0645-104">Lync Server 2013 提供基本的會話管理，其支援主幹間路由。</span><span class="sxs-lookup"><span data-stu-id="c0645-104">Lync Server 2013 provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="c0645-105">這項新功能可讓 Lync Server 向下游電話語音系統提供呼叫控制功能。</span><span class="sxs-lookup"><span data-stu-id="c0645-105">This new capability enables Lync Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="c0645-106">主幹間路由可將 IP-PBX 互連至公用交換電話網路 (PSTN) 閘道，使來自私營分公司 exchange (PBX) phone 的呼叫可以路由傳送至 PSTN，而且傳入 PSTN 通話可以路由傳送至 PBX 電話。</span><span class="sxs-lookup"><span data-stu-id="c0645-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="c0645-107">同樣地，Lync Server 可以互連兩個或多個 IP-PBX 系統，這樣通話便可在不同 IP-PBX 系統的 PBX 電話之間進行和接收。</span><span class="sxs-lookup"><span data-stu-id="c0645-107">Similarly, Lync Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span>

<span data-ttu-id="c0645-108">下圖說明 Lync Server 2013 在 PSTN 閘道和 IP-PBX 之間提供 interconnectivity。</span><span class="sxs-lookup"><span data-stu-id="c0645-108">The following figure illustrates Lync Server 2013 providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

<span data-ttu-id="c0645-109">![連接 PSTN 閘道/IP-PBX 圖表的 Lync Server](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "連接 PSTN 閘道/IP-PBX 圖表的 Lync Server")</span><span class="sxs-lookup"><span data-stu-id="c0645-109">![Lync Server connecting PSTN gateway/IP-PBX diagram](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server connecting PSTN gateway/IP-PBX diagram")</span></span>

<span data-ttu-id="c0645-110">下圖說明連接兩個 IP-PBX 系統的 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="c0645-110">The next figure illustrates Lync Server 2013 connecting two IP-PBX systems.</span></span>

<span data-ttu-id="c0645-111">![Lync Server 互連 IP-PAX 系統圖表](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server 互連 IP-PAX 系統圖表")</span><span class="sxs-lookup"><span data-stu-id="c0645-111">![Lync Server interconnecting IP-PAX systems diagram](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server interconnecting IP-PAX systems diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

