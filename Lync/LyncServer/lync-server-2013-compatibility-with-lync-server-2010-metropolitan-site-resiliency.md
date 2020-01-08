---
title: 與 Lync Server 2010 都會區網站復原的 Lync Server 2013 相容性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2010 metropolitan site resiliency
ms:assetid: 18673ff6-b664-4a57-a89b-cbda8b129e6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204715(v=OCS.15)
ms:contentKeyID: 48183526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3079f05d9860fd659d19df7b71ee633c0cea3fe2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982466"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2010-metropolitan-site-resiliency"></a><span data-ttu-id="1d9ad-102">Lync Server 2010 都會區網站復原</span><span class="sxs-lookup"><span data-stu-id="1d9ad-102">Lync Server 2010 metropolitan site resiliency</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d9ad-103">_**主題上次修改日期：** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="1d9ad-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="1d9ad-104">Lync Server 2013 不支援 Lync Server 2010 支援的大都市網站復原方案。</span><span class="sxs-lookup"><span data-stu-id="1d9ad-104">The metropolitan site resiliency solution supported for Lync Server 2010 is not supported for Lync Server 2013.</span></span> <span data-ttu-id="1d9ad-105">這個方案涉及跨同一大都市區域中的兩個資料中心跨越單一前端池。</span><span class="sxs-lookup"><span data-stu-id="1d9ad-105">This solution involved spanning a single Front End pool across two data centers in the same metropolitan area.</span></span>

<span data-ttu-id="1d9ad-106">大都市網站復原解決方案的設計目的是要從整個資料中心遺失時復原。</span><span class="sxs-lookup"><span data-stu-id="1d9ad-106">The metropolitan site resiliency solution was designed to recover from the loss of a full datacenter.</span></span> <span data-ttu-id="1d9ad-107">當您跨兩個資料中心跨越您的池時，通常會將半端放在一個資料中心，而另一個資料中心則是第二個資料中心。</span><span class="sxs-lookup"><span data-stu-id="1d9ad-107">When you span your pool across two datacenters, you typically put half of your front ends in one datacenter and the other half in the second datacenter.</span></span> <span data-ttu-id="1d9ad-108">如果您遺失整個資料中心，就會遺失一半的前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="1d9ad-108">If you lose an entire datacenter, you have lost half of your Front End Servers.</span></span> <span data-ttu-id="1d9ad-109">在 Lync Server 2013 中，這可能會導致新分散式系統模型的新分散式系統模型發生問題。</span><span class="sxs-lookup"><span data-stu-id="1d9ad-109">This can cause issues with the new distributed system model for Front End Pools in Lync Server 2013.</span></span> <span data-ttu-id="1d9ad-110">如需詳細資訊，請參閱[Lync Server 2013 中前端伺服器、立即訊息和目前狀態的拓撲與元件](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="1d9ad-110">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

