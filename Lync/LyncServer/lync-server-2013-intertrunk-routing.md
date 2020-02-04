---
title: Lync Server 2013：主幹間路由
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
ms.openlocfilehash: eaa41fe229e9246506fd92eb9f48767994997e4e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="intertrunk-routing-in-lync-server-2013"></a><span data-ttu-id="7ab9a-102">Lync Server 2013 中的主幹間路由</span><span class="sxs-lookup"><span data-stu-id="7ab9a-102">Intertrunk routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ab9a-103">_**主題上次修改日期：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="7ab9a-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="7ab9a-104">Lync Server 2013 可以將 IP PBX 與公用交換式電話網絡（PSTN）閘道相互連接，讓來自 PBX 電話的呼叫可以路由到 PSTN，而且傳入的 PSTN 呼叫可以路由到專用的分支 exchange （PBX）電話。</span><span class="sxs-lookup"><span data-stu-id="7ab9a-104">Lync Server 2013 can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a PBX phone can be routed to the PSTN, and incoming PSTN calls can be routed to a private branch exchange (PBX) phone.</span></span> <span data-ttu-id="7ab9a-105">同樣地，Lync Server 2013 可以相互連接兩個或多個 IP PBX 系統，以便在不同 IP PBX 系統的 PBX 手機之間進行呼叫和接收。</span><span class="sxs-lookup"><span data-stu-id="7ab9a-105">Similarly, Lync Server 2013 can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span>

<span data-ttu-id="7ab9a-106">此 intertrunk 路由功能可以使用 Lync Server Management Shell Cmdlet （**設定為 new-cstrunkconfiguration**），並使用新的參數 PstnUsages 進行設定。</span><span class="sxs-lookup"><span data-stu-id="7ab9a-106">This intertrunk routing feature can be configured by using the Lync Server Management Shell cmdlet, **Set-CsTrunkConfiguration**, with the new parameter, PstnUsages.</span></span> <span data-ttu-id="7ab9a-107">這個參數會指定要使用的 PSTN 使用記錄集合。</span><span class="sxs-lookup"><span data-stu-id="7ab9a-107">This parameter specifies the set of PSTN usage records to use.</span></span> <span data-ttu-id="7ab9a-108">主幹使用這種 PSTN 用法來判斷路線，並據此傳送所有來電。</span><span class="sxs-lookup"><span data-stu-id="7ab9a-108">A trunk uses this PSTN usage to determine a route and to route all incoming calls accordingly.</span></span>

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

<span data-ttu-id="7ab9a-109">下圖說明 Lync Server 2013，提供 PSTN 閘道與 IP PBX 之間的 interconnectivity。</span><span class="sxs-lookup"><span data-stu-id="7ab9a-109">The following diagram illustrates Lync Server 2013 providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

<span data-ttu-id="7ab9a-110">**Intertrunk 閘道與 IP PBX 之間的路由**</span><span class="sxs-lookup"><span data-stu-id="7ab9a-110">**Intertrunk routing between gateway and IP PBX**</span></span>

<span data-ttu-id="7ab9a-111">![連接 PSTN 閘道/IP-PBX 圖表的 Lync Server](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "連接 PSTN 閘道/IP-PBX 圖表的 Lync Server")</span><span class="sxs-lookup"><span data-stu-id="7ab9a-111">![Lync Server connecting PSTN gateway/IP-PBX diagram](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server connecting PSTN gateway/IP-PBX diagram")</span></span>

<span data-ttu-id="7ab9a-112">下圖說明 Lync Server 2013 互連兩個 IP PBX 系統的操作。</span><span class="sxs-lookup"><span data-stu-id="7ab9a-112">The following diagram illustrates Lync Server 2013 interconnecting two IP-PBX systems.</span></span>

<span data-ttu-id="7ab9a-113">**在兩個 IP Pbx 之間 Intertrunk 路由**</span><span class="sxs-lookup"><span data-stu-id="7ab9a-113">**Intertrunk routing between two IP PBXs**</span></span>

<span data-ttu-id="7ab9a-114">![交互連接 IP-PAX 系統圖表的 Lync Server](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "交互連接 IP-PAX 系統圖表的 Lync Server")</span><span class="sxs-lookup"><span data-stu-id="7ab9a-114">![Lync Server interconnecting IP-PAX systems diagram](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server interconnecting IP-PAX systems diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

