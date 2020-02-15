---
title: Lync Server 2013 與 Lync Server 2010 都會網站恢復的相容性
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
ms.openlocfilehash: 2f432941773b72d18c22adc87779341996771399
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045605"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2010-metropolitan-site-resiliency"></a><span data-ttu-id="b7da6-102">Lync Server 2010 都會網站恢復</span><span class="sxs-lookup"><span data-stu-id="b7da6-102">Lync Server 2010 metropolitan site resiliency</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7da6-103">_**上次修改主題：** 2014年-03-19_</span><span class="sxs-lookup"><span data-stu-id="b7da6-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="b7da6-104">Lync Server 2013 不支援支援 Lync Server 2010 都會網站恢復解決方案。</span><span class="sxs-lookup"><span data-stu-id="b7da6-104">The metropolitan site resiliency solution supported for Lync Server 2010 is not supported for Lync Server 2013.</span></span> <span data-ttu-id="b7da6-105">這個解決方案會將單一前端集區橫跨同一都會區中的兩個資料中心。</span><span class="sxs-lookup"><span data-stu-id="b7da6-105">This solution involved spanning a single Front End pool across two data centers in the same metropolitan area.</span></span>

<span data-ttu-id="b7da6-106">都會網站恢復解決方案的設計目的在於復原遺失的完整的資料中心。</span><span class="sxs-lookup"><span data-stu-id="b7da6-106">The metropolitan site resiliency solution was designed to recover from the loss of a full datacenter.</span></span> <span data-ttu-id="b7da6-107">當您將您的集區跨兩個資料中心時，您通常您前端的下半部中放置一個資料中心，另一半第二個資料中心。</span><span class="sxs-lookup"><span data-stu-id="b7da6-107">When you span your pool across two datacenters, you typically put half of your front ends in one datacenter and the other half in the second datacenter.</span></span> <span data-ttu-id="b7da6-108">如果您遺失整個資料中心，您有遺失下半部前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="b7da6-108">If you lose an entire datacenter, you have lost half of your Front End Servers.</span></span> <span data-ttu-id="b7da6-109">這會造成問題的新的分散式的系統模型的 Lync Server 2013 中的 Front End Pools。</span><span class="sxs-lookup"><span data-stu-id="b7da6-109">This can cause issues with the new distributed system model for Front End Pools in Lync Server 2013.</span></span> <span data-ttu-id="b7da6-110">如需詳細資訊，請參閱[前端伺服器、 立即訊息和 Lync Server 2013 中的目前狀態的元件和拓撲](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="b7da6-110">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

