---
title: Lync Server 2013：主幹間路由
description: Lync Server 2013：主幹間路由傳送。
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
ms.openlocfilehash: 30c838ee94a2df0807195c172d7e2a3a393523af
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553139"
---
# <a name="intertrunk-routing-in-lync-server-2013"></a><span data-ttu-id="0d739-103">Lync Server 2013 中的主幹間路由</span><span class="sxs-lookup"><span data-stu-id="0d739-103">Intertrunk routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d739-104">_**主題上次修改日期：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="0d739-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="0d739-105">Lync Server 2013 可將 IP-PBX 互連至公用交換電話網路 (PSTN) 閘道，以便從 PBX 電話將通話路由傳送至 PSTN，然後將傳入 PSTN 通話路由傳送至專用交換機 (PBX) phone。</span><span class="sxs-lookup"><span data-stu-id="0d739-105">Lync Server 2013 can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a PBX phone can be routed to the PSTN, and incoming PSTN calls can be routed to a private branch exchange (PBX) phone.</span></span> <span data-ttu-id="0d739-106">同樣地，Lync Server 2013 可以互連兩個或多個 IP-PBX 系統，這樣通話便可在不同 IP-PBX 系統的 PBX 電話間撥打及接收。</span><span class="sxs-lookup"><span data-stu-id="0d739-106">Similarly, Lync Server 2013 can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span>

<span data-ttu-id="0d739-107">您可以使用 Lync Server 管理命令介面 Cmdlet **Set-CsTrunkConfiguration**，使用新參數 PstnUsages 來設定此主幹間路由功能。</span><span class="sxs-lookup"><span data-stu-id="0d739-107">This intertrunk routing feature can be configured by using the Lync Server Management Shell cmdlet, **Set-CsTrunkConfiguration**, with the new parameter, PstnUsages.</span></span> <span data-ttu-id="0d739-108">此參數會指定要使用的 PSTN 使用方式記錄集合。</span><span class="sxs-lookup"><span data-stu-id="0d739-108">This parameter specifies the set of PSTN usage records to use.</span></span> <span data-ttu-id="0d739-109">主幹使用此 PSTN 使用方式判斷路由，並據此路由傳送所有來電。</span><span class="sxs-lookup"><span data-stu-id="0d739-109">A trunk uses this PSTN usage to determine a route and to route all incoming calls accordingly.</span></span>

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

<span data-ttu-id="0d739-110">下圖說明 Lync Server 2013 在 PSTN 閘道和 IP-PBX 之間提供 interconnectivity。</span><span class="sxs-lookup"><span data-stu-id="0d739-110">The following diagram illustrates Lync Server 2013 providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

<span data-ttu-id="0d739-111">**閘道和 IP PBX 間的主幹間路由**</span><span class="sxs-lookup"><span data-stu-id="0d739-111">**Intertrunk routing between gateway and IP PBX**</span></span>

<span data-ttu-id="0d739-112">![連接 PSTN 閘道/IP-PBX 圖表的 Lync Server](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "連接 PSTN 閘道/IP-PBX 圖表的 Lync Server")</span><span class="sxs-lookup"><span data-stu-id="0d739-112">![Lync Server connecting PSTN gateway/IP-PBX diagram](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server connecting PSTN gateway/IP-PBX diagram")</span></span>

<span data-ttu-id="0d739-113">下圖說明 Lync Server 2013 互連兩個 IP-PBX 系統的互連。</span><span class="sxs-lookup"><span data-stu-id="0d739-113">The following diagram illustrates Lync Server 2013 interconnecting two IP-PBX systems.</span></span>

<span data-ttu-id="0d739-114">**主幹間兩個 IP PBXs 之間的路由**</span><span class="sxs-lookup"><span data-stu-id="0d739-114">**Intertrunk routing between two IP PBXs**</span></span>

<span data-ttu-id="0d739-115">![Lync Server 互連 IP-PAX 系統圖表](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server 互連 IP-PAX 系統圖表")</span><span class="sxs-lookup"><span data-stu-id="0d739-115">![Lync Server interconnecting IP-PAX systems diagram](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server interconnecting IP-PAX systems diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

