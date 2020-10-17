---
title: Lync Server 2013 與 Lync Server 2010 大都市網站恢復的相容性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2010 metropolitan site resiliency
ms:assetid: 18673ff6-b664-4a57-a89b-cbda8b129e6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204715(v=OCS.15)
ms:contentKeyID: 48183526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04b3cca41b0ea7a7060e6349127dc7c7fb1732ea
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526050"
---
# <a name="lync-server-2010-metropolitan-site-resiliency"></a><span data-ttu-id="857d3-102">Lync Server 2010 大都市網站恢復功能</span><span class="sxs-lookup"><span data-stu-id="857d3-102">Lync Server 2010 metropolitan site resiliency</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="857d3-103">_**主題上次修改日期：** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="857d3-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="857d3-104">Lync 2013 Server 2010 不支援 Lync Server 支援的大都市網站恢復解決方案。</span><span class="sxs-lookup"><span data-stu-id="857d3-104">The metropolitan site resiliency solution supported for Lync Server 2010 is not supported for Lync Server 2013.</span></span> <span data-ttu-id="857d3-105">這個解決方案會將單一前端集區橫跨同一都會區中的兩個資料中心。</span><span class="sxs-lookup"><span data-stu-id="857d3-105">This solution involved spanning a single Front End pool across two data centers in the same metropolitan area.</span></span>

<span data-ttu-id="857d3-106">大都市網站恢復解決方案旨在從整個資料中心遺失時復原。</span><span class="sxs-lookup"><span data-stu-id="857d3-106">The metropolitan site resiliency solution was designed to recover from the loss of a full datacenter.</span></span> <span data-ttu-id="857d3-107">當您跨越兩個資料中心的集區時，您通常會在一個資料中心中放置一半的前端，另一個則是第二個資料中心的一半。</span><span class="sxs-lookup"><span data-stu-id="857d3-107">When you span your pool across two datacenters, you typically put half of your front ends in one datacenter and the other half in the second datacenter.</span></span> <span data-ttu-id="857d3-108">如果您遺失整個資料中心，您已遺失一半的前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="857d3-108">If you lose an entire datacenter, you have lost half of your Front End Servers.</span></span> <span data-ttu-id="857d3-109">這可能會導致 Lync Server 2013 中的前端集區的新分散式系統模型發生問題。</span><span class="sxs-lookup"><span data-stu-id="857d3-109">This can cause issues with the new distributed system model for Front End Pools in Lync Server 2013.</span></span> <span data-ttu-id="857d3-110">如需詳細資訊，請參閱 [Lync Server 2013 中的前端伺服器、立即訊息及顯示狀態的拓撲和元件](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="857d3-110">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

