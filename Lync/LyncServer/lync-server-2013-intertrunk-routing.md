---
title: Lync Server 2013： 主幹間路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Intertrunk routing
ms:assetid: d3a33b4a-8bf4-4a8c-a371-8ef79e740780
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205272(v=OCS.15)
ms:contentKeyID: 48185442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23aab6df352b162f7f389ef56fb2300f01654edb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="intertrunk-routing-in-lync-server-2013"></a><span data-ttu-id="000be-102">Lync Server 2013 中的主幹相互路由</span><span class="sxs-lookup"><span data-stu-id="000be-102">Intertrunk routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="000be-103">_**主題上次修改日期：** 2012年-10-20 個_</span><span class="sxs-lookup"><span data-stu-id="000be-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="000be-104">Lync Server 2013 可以相互連線至公用交換的電話網路 (PSTN) 閘道 IP PBX，以便從 PBX 電話的通話路由至 PSTN，以及傳入 PSTN 通話路由至專用交換機 (pbx) 電話。</span><span class="sxs-lookup"><span data-stu-id="000be-104">Lync Server 2013 can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a PBX phone can be routed to the PSTN, and incoming PSTN calls can be routed to a private branch exchange (PBX) phone.</span></span> <span data-ttu-id="000be-105">同樣地，Lync Server 2013 可以 interconnect 兩個或多個 IP-PBX 系統，以便可以放置和 PBX 電話從不同的 IP PBX 系統之間接收來電。</span><span class="sxs-lookup"><span data-stu-id="000be-105">Similarly, Lync Server 2013 can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span>

<span data-ttu-id="000be-106">此主幹間路由功能可以設定 Lync Server 管理命令介面指令程式， **Set-cstrunkconfiguration**，使用新的參數，PstnUsages。</span><span class="sxs-lookup"><span data-stu-id="000be-106">This intertrunk routing feature can be configured by using the Lync Server Management Shell cmdlet, **Set-CsTrunkConfiguration**, with the new parameter, PstnUsages.</span></span> <span data-ttu-id="000be-107">此參數會指定要使用的 PSTN 使用方式記錄的集合。</span><span class="sxs-lookup"><span data-stu-id="000be-107">This parameter specifies the set of PSTN usage records to use.</span></span> <span data-ttu-id="000be-108">主幹使用此 PSTN 使用方式，來判定路由，並據此路由傳送所有來電。</span><span class="sxs-lookup"><span data-stu-id="000be-108">A trunk uses this PSTN usage to determine a route and to route all incoming calls accordingly.</span></span>

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

<span data-ttu-id="000be-109">下圖說明提供互連功能 PSTN 閘道與 IP-PBX 間的 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="000be-109">The following diagram illustrates Lync Server 2013 providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

<span data-ttu-id="000be-110">**閘道和 IP PBX 之間的主幹相互路由**</span><span class="sxs-lookup"><span data-stu-id="000be-110">**Intertrunk routing between gateway and IP PBX**</span></span>

<span data-ttu-id="000be-111">![Lync Server 連線 PSTN 閘道/IP-PBX 圖表](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server 連線 PSTN 閘道/IP-PBX 圖表")</span><span class="sxs-lookup"><span data-stu-id="000be-111">![Lync Server connecting PSTN gateway/IP-PBX diagram](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server connecting PSTN gateway/IP-PBX diagram")</span></span>

<span data-ttu-id="000be-112">下圖說明交互連接兩個 IP-PBX 系統的 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="000be-112">The following diagram illustrates Lync Server 2013 interconnecting two IP-PBX systems.</span></span>

<span data-ttu-id="000be-113">**兩個 IP Pbx 之間的主幹相互路由**</span><span class="sxs-lookup"><span data-stu-id="000be-113">**Intertrunk routing between two IP PBXs**</span></span>

<span data-ttu-id="000be-114">![Lync Server 交互連接 IP PAX 系統圖表](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server 交互連接 IP PAX 系統圖表")</span><span class="sxs-lookup"><span data-stu-id="000be-114">![Lync Server interconnecting IP-PAX systems diagram](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server interconnecting IP-PAX systems diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

