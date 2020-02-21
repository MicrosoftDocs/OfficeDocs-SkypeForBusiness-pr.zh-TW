---
title: Lync Server 2013： 主幹間路由
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
ms.openlocfilehash: af9fd674a83eed898eddc47f8cc95114a29d54b0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214536"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="inter-trunk-routing-in-lync-server-2013"></a><span data-ttu-id="b1e38-102">Lync Server 2013 中的主幹間路由</span><span class="sxs-lookup"><span data-stu-id="b1e38-102">Inter-trunk routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1e38-103">_**主題上次修改日期：** 2012年-10-08_</span><span class="sxs-lookup"><span data-stu-id="b1e38-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="b1e38-104">Lync Server 2013 提供透過支援的主幹相互路由功能的基本工作階段管理。</span><span class="sxs-lookup"><span data-stu-id="b1e38-104">Lync Server 2013 provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="b1e38-105">這項新功能可讓 Lync 伺服器，以提供呼叫控制功能下游電話語音系統。</span><span class="sxs-lookup"><span data-stu-id="b1e38-105">This new capability enables Lync Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="b1e38-106">主幹間路由可以 interconnect 至公用交換的電話網路 (PSTN) 閘道 IP PBX，以便從專用交換機 (pbx) 電話的通話路由至 PSTN，以及傳入 PSTN 通話可以路由傳送至 PBX 的電話。</span><span class="sxs-lookup"><span data-stu-id="b1e38-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="b1e38-107">同樣地，Lync Server 可以 interconnect 兩個或多個 IP-PBX 系統，以便可以放置和 PBX 電話從不同的 IP PBX 系統之間接收來電。</span><span class="sxs-lookup"><span data-stu-id="b1e38-107">Similarly, Lync Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span>

<span data-ttu-id="b1e38-108">下圖說明提供互連功能 PSTN 閘道與 IP-PBX 間的 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="b1e38-108">The following figure illustrates Lync Server 2013 providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

<span data-ttu-id="b1e38-109">![Lync Server 連線 PSTN 閘道/IP-PBX 圖表](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server 連線 PSTN 閘道/IP-PBX 圖表")</span><span class="sxs-lookup"><span data-stu-id="b1e38-109">![Lync Server connecting PSTN gateway/IP-PBX diagram](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server connecting PSTN gateway/IP-PBX diagram")</span></span>

<span data-ttu-id="b1e38-110">下圖說明連接兩個 IP-PBX 系統的 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="b1e38-110">The next figure illustrates Lync Server 2013 connecting two IP-PBX systems.</span></span>

<span data-ttu-id="b1e38-111">![Lync Server 交互連接 IP PAX 系統圖表](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server 交互連接 IP PAX 系統圖表")</span><span class="sxs-lookup"><span data-stu-id="b1e38-111">![Lync Server interconnecting IP-PAX systems diagram](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server interconnecting IP-PAX systems diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

