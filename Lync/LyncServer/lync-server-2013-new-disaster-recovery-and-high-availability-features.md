---
title: Lync Server 2013：新的嚴重損壞修復和高可用性功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New disaster recovery and high availability features
ms:assetid: 4fa7cd0f-784b-4d3f-b839-432c2ecaf7c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204892(v=OCS.15)
ms:contentKeyID: 48184130
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33a9039c65d059042d9eb93c9d5437a00ebff266
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512560"
---
# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a><span data-ttu-id="a03e2-102">Lync Server 2013 中新的嚴重損壞修復和高可用性功能</span><span class="sxs-lookup"><span data-stu-id="a03e2-102">New disaster recovery and high availability features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a03e2-103">_**主題上次修改日期：** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="a03e2-103">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="a03e2-104">在 Lync Server 2010 中，Lync Server 2013 的主要高可用性 (HA) 模式是透過 pooling server 冗余度為基礎。</span><span class="sxs-lookup"><span data-stu-id="a03e2-104">As in Lync Server 2010, the main high availability (HA) scheme for Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="a03e2-105">如果執行特定伺服器角色的伺服器失敗，集區中執行相同角色的其他伺服器就會接手該伺服器的負載。</span><span class="sxs-lookup"><span data-stu-id="a03e2-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="a03e2-106">這適用於前端伺服器、Edge Server、中繼伺服器和 Director。</span><span class="sxs-lookup"><span data-stu-id="a03e2-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="a03e2-107">Lync Server 2013 可讓您將位於兩個資料中心的前端集區配對，以加入新的嚴重損壞修復措施。</span><span class="sxs-lookup"><span data-stu-id="a03e2-107">Lync Server 2013 adds new disaster recovery measures by enabling you to pair Front End pools located in two datacenters.</span></span> <span data-ttu-id="a03e2-108">如果配對的集區中有一個故障，系統管理員可以將使用者從該集區容錯移轉至配對中的另一個集區，以便繼續提供服務。</span><span class="sxs-lookup"><span data-stu-id="a03e2-108">If one of the paired pools goes down, an administrator can fail over the users from that pool to the other pool in the pair, to provide continuation of service.</span></span> <span data-ttu-id="a03e2-109">這項功能不需要昂貴的網路或硬體解決方案，例如存放網路或共用磁碟。</span><span class="sxs-lookup"><span data-stu-id="a03e2-109">This functionality does not require expensive network or hardware solutions such as storage networks or shared disks.</span></span>

<span data-ttu-id="a03e2-110">Lync Server 2013 也新增後端伺服器高可用性。</span><span class="sxs-lookup"><span data-stu-id="a03e2-110">Lync Server 2013 also adds Back End Server high availability.</span></span> <span data-ttu-id="a03e2-111">這是選用的拓撲，您可以在其中部署前端集區的兩部後端伺服器，並為在後端伺服器上執行的所有 Lync 資料庫設定同步 SQL 鏡像。</span><span class="sxs-lookup"><span data-stu-id="a03e2-111">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL mirroring for all the Lync databases running on the Back End Servers.</span></span> <span data-ttu-id="a03e2-112">您可以選擇是否要部署鏡像見證。</span><span class="sxs-lookup"><span data-stu-id="a03e2-112">You may choose whether to deploy a witness for the mirror.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="a03e2-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a03e2-113">See Also</span></span>


[<span data-ttu-id="a03e2-114">在 Lync Server 2013 中規劃高可用性和嚴重損壞修復</span><span class="sxs-lookup"><span data-stu-id="a03e2-114">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

