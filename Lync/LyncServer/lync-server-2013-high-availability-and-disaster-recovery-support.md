---
title: Lync Server 2013：高可用性和嚴重損壞修復支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: High availability and disaster recovery support
ms:assetid: 47e77e85-c7c3-4ade-8db7-a34c71aeafd7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204866(v=OCS.15)
ms:contentKeyID: 48184053
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c78982552cfe85479f2f1551fc85e64c3f89cbea
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528230"
---
# <a name="high-availability-and-disaster-recovery-support-in-lync-server-2013"></a><span data-ttu-id="8913a-102">Lync Server 2013 的高可用性和嚴重損壞修復支援</span><span class="sxs-lookup"><span data-stu-id="8913a-102">High availability and disaster recovery support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8913a-103">_**主題上次修改日期：** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="8913a-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="8913a-104">Lync Server 2013 透過 pooling 透過伺服器的冗余度，提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="8913a-104">Lync Server 2013 provides high availability by server redundancy via pooling.</span></span> <span data-ttu-id="8913a-105">如果執行特定伺服器角色的伺服器失敗，集區中執行相同角色的其他伺服器就會接手該伺服器的負載。</span><span class="sxs-lookup"><span data-stu-id="8913a-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="8913a-106">這適用於前端伺服器、Edge Server、中繼伺服器和 Director。</span><span class="sxs-lookup"><span data-stu-id="8913a-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span> <span data-ttu-id="8913a-107">如需伺服器角色的詳細資訊，請參閱 [Lync server 2013 中的伺服器角色](lync-server-2013-server-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="8913a-107">For details about server roles, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md).</span></span>

<span data-ttu-id="8913a-108">Lync Server 2013 也會啟用集區配對，以提供嚴重損壞修復措施。</span><span class="sxs-lookup"><span data-stu-id="8913a-108">Lync Server 2013 also provides disaster recovery measures by enabling pool pairing.</span></span> <span data-ttu-id="8913a-109">如果您部署這個拓樸，將會指定前端集區配對，每一對中各個集區都位在不同的資料中心，並且在不同的地理區。</span><span class="sxs-lookup"><span data-stu-id="8913a-109">If you deploy this topology, you will designate pairs of Front End pools, with each pool in a pair located in a separate data center, and in a separate geographical area.</span></span> <span data-ttu-id="8913a-110">如果一個集區或網站故障，您可以重新導向該集區的使用者，以使用該配對中另一個集區，讓服務中斷時間降至最低。</span><span class="sxs-lookup"><span data-stu-id="8913a-110">If one pool or site goes down, you can redirect the users of that pool to use the other pool in the pair, with minimal interruption of service.</span></span>

<span data-ttu-id="8913a-111">Lync Server 2013 也支援後端伺服器高可用性。</span><span class="sxs-lookup"><span data-stu-id="8913a-111">Lync Server 2013 also supports Back End Server high availability.</span></span> <span data-ttu-id="8913a-112">這是選用的拓撲，您可以在其中部署前端集區的兩部後端伺服器，並為在後端伺服器上執行的所有 Lync 資料庫設定同步 SQL Server 鏡像。</span><span class="sxs-lookup"><span data-stu-id="8913a-112">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL Server mirroring for all the Lync databases running on the Back End Servers.</span></span>

<span data-ttu-id="8913a-113">如需有關集區配對及後端伺服器鏡像的詳細資訊，請參閱 [在 Lync Server 2013 中規劃高可用性和嚴重損壞修復](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="8913a-113">For details about pool pairing and Back End Server mirroring, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="8913a-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8913a-114">See Also</span></span>


[<span data-ttu-id="8913a-115">Lync Server 2013 中的伺服器角色</span><span class="sxs-lookup"><span data-stu-id="8913a-115">Server roles in Lync Server 2013</span></span>](lync-server-2013-server-roles.md)  
[<span data-ttu-id="8913a-116">在 Lync Server 2013 中規劃高可用性和嚴重損壞修復</span><span class="sxs-lookup"><span data-stu-id="8913a-116">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

