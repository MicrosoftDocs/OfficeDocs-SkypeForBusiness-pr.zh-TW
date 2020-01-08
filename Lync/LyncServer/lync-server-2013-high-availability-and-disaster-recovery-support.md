---
title: Lync Server 2013：高可用性和災害復原支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: High availability and disaster recovery support
ms:assetid: 47e77e85-c7c3-4ade-8db7-a34c71aeafd7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204866(v=OCS.15)
ms:contentKeyID: 48184053
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fa5ec2ad01372d593a4452c352c33dd8077e395
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975391"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="high-availability-and-disaster-recovery-support-in-lync-server-2013"></a><span data-ttu-id="1047d-102">Lync Server 2013 中的高可用性和災害復原支援</span><span class="sxs-lookup"><span data-stu-id="1047d-102">High availability and disaster recovery support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1047d-103">_**主題上次修改日期：** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="1047d-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="1047d-104">Lync Server 2013 透過 [彙集]，透過伺服器冗余提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="1047d-104">Lync Server 2013 provides high availability by server redundancy via pooling.</span></span> <span data-ttu-id="1047d-105">如果執行特定伺服器角色的伺服器失敗，則池中執行相同角色的其他伺服器會載入該伺服器。</span><span class="sxs-lookup"><span data-stu-id="1047d-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="1047d-106">這適用于前端伺服器、邊緣伺服器、轉送伺服器和控制器。</span><span class="sxs-lookup"><span data-stu-id="1047d-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span> <span data-ttu-id="1047d-107">如需伺服器角色的詳細資料，請參閱[Lync server 2013 中的伺服器角色](lync-server-2013-server-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="1047d-107">For details about server roles, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md).</span></span>

<span data-ttu-id="1047d-108">Lync Server 2013 也會透過啟用池配對來提供災害復原措施。</span><span class="sxs-lookup"><span data-stu-id="1047d-108">Lync Server 2013 also provides disaster recovery measures by enabling pool pairing.</span></span> <span data-ttu-id="1047d-109">如果您部署這個拓朴，您將會指定一組前端池，其中每個池都位於另一個資料中心，且位於不同的地理區域中。</span><span class="sxs-lookup"><span data-stu-id="1047d-109">If you deploy this topology, you will designate pairs of Front End pools, with each pool in a pair located in a separate data center, and in a separate geographical area.</span></span> <span data-ttu-id="1047d-110">如果有一個池或網站停機，您可以重新導向該池的使用者，以使用該集中的其他池，並最少中斷服務。</span><span class="sxs-lookup"><span data-stu-id="1047d-110">If one pool or site goes down, you can redirect the users of that pool to use the other pool in the pair, with minimal interruption of service.</span></span>

<span data-ttu-id="1047d-111">Lync Server 2013 也支援後端伺服器高可用性。</span><span class="sxs-lookup"><span data-stu-id="1047d-111">Lync Server 2013 also supports Back End Server high availability.</span></span> <span data-ttu-id="1047d-112">這是一種選用拓朴，您可以在其中部署前端池的兩個後端伺服器，並針對在後端伺服器上執行的所有 Lync 資料庫，設定同步處理的 SQL Server 鏡像。</span><span class="sxs-lookup"><span data-stu-id="1047d-112">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL Server mirroring for all the Lync databases running on the Back End Servers.</span></span>

<span data-ttu-id="1047d-113">如需有關池配對與後端伺服器鏡像的詳細資料，請參閱[在 Lync Server 2013 中規劃高可用性和災害復原](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="1047d-113">For details about pool pairing and Back End Server mirroring, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="1047d-114">請參閱</span><span class="sxs-lookup"><span data-stu-id="1047d-114">See Also</span></span>


[<span data-ttu-id="1047d-115">Lync Server 2013 中的伺服器角色</span><span class="sxs-lookup"><span data-stu-id="1047d-115">Server roles in Lync Server 2013</span></span>](lync-server-2013-server-roles.md)  
[<span data-ttu-id="1047d-116">在 Lync Server 2013 中規劃高可用性和災害復原</span><span class="sxs-lookup"><span data-stu-id="1047d-116">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

