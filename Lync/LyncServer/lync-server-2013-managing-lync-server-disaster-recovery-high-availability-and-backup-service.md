---
title: 管理 Lync Server 災難修復、高可用性及備份服務
description: 管理 Lync Server 災難修復、高可用性及備份服務。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Lync Server disaster recovery, high availability, and Backup Service
ms:assetid: f4cd36fb-ffd6-48fa-b761-e11b3bcff91a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721939(v=OCS.15)
ms:contentKeyID: 49733876
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e440c8c72ab5e66d27a86dfce963368dff804bc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569409"
---
# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="6589f-103">管理 Lync Server 2013 災難修復、高可用性及備份服務</span><span class="sxs-lookup"><span data-stu-id="6589f-103">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6589f-104">_**主題上次修改日期：** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="6589f-104">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="6589f-105">本節包含嚴重損壞復原作業的程式，以及維護備份服務，以同步處理成對前端集區中的資料。</span><span class="sxs-lookup"><span data-stu-id="6589f-105">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="6589f-106">容錯移轉和回切回的嚴重損壞修復程式都是手動。</span><span class="sxs-lookup"><span data-stu-id="6589f-106">Disaster recovery procedures, both failover and failback, are manual.</span></span> <span data-ttu-id="6589f-107">如果發生災難，系統管理員必須手動呼叫容錯移轉程式。</span><span class="sxs-lookup"><span data-stu-id="6589f-107">If there is a disaster, the administrator must manually invoke the failover procedures.</span></span> <span data-ttu-id="6589f-108">修復集區之後，回復器也同樣適用。</span><span class="sxs-lookup"><span data-stu-id="6589f-108">The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="6589f-109">本節其餘部分的嚴重損壞修復程式會假設下列各項：</span><span class="sxs-lookup"><span data-stu-id="6589f-109">The disaster recovery procedures in the rest of this section assume the following:</span></span>

  - <span data-ttu-id="6589f-110">您的部署具有成對的前端集區，位於不同的網站，如在 [Lync Server 2013 中規劃高可用性和嚴重損壞修復](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="6589f-110">You have a deployment with paired Front End pools, located in different sites, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="6589f-111">備份服務已在這些配對集區上執行，使其保持同步。</span><span class="sxs-lookup"><span data-stu-id="6589f-111">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="6589f-112">如果中央管理存放區裝載于任何集區上，則會在兩個配對集區上安裝並執行，其中一個集區會裝載作用中的主集區，而另一個集區會主控備用的集區。</span><span class="sxs-lookup"><span data-stu-id="6589f-112">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="6589f-113">在下列程式中， <EM>PoolFQDN</EM> 參數會參照受災難影響的集區的 FQDN，而不會重新導向受影響使用者的集區。</span><span class="sxs-lookup"><span data-stu-id="6589f-113">In the following procedures, the <EM>PoolFQDN</EM> parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from.</span></span> <span data-ttu-id="6589f-114">針對相同組受影響的使用者，它會在容錯移轉和回切 (Cmdlet 中同時參考相同的集區，也就是在容錯移轉) 之前第一位使用者的集區。</span><span class="sxs-lookup"><span data-stu-id="6589f-114">For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><span data-ttu-id="6589f-115">例如，假設某個案例位於集區 P1 的所有使用者都已容錯移轉至備份組區 P2。</span><span class="sxs-lookup"><span data-stu-id="6589f-115">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2.</span></span> <span data-ttu-id="6589f-116">如果系統管理員想要移動所有目前由 P2 服務服務的使用者，以 P1 為服務，系統管理員必須執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="6589f-116">If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="6589f-117">使用回復指令 Cmdlet，將原來在 P1 上的所有使用者都從 P2 重新容錯回復至 P1。</span><span class="sxs-lookup"><span data-stu-id="6589f-117">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet.</span></span> <span data-ttu-id="6589f-118">在此情況下， <EM>PoolFQDN</EM> 為 P1's FQDN。</span><span class="sxs-lookup"><span data-stu-id="6589f-118">In this case, the <EM>PoolFQDN</EM> is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="6589f-119">使用容錯移轉指令，將所有原先位於 P2 的使用者容錯移轉至 P1。</span><span class="sxs-lookup"><span data-stu-id="6589f-119">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="6589f-120">在此情況下， <EM>PoolFQDN</EM> 為 P2's FQDN。</span><span class="sxs-lookup"><span data-stu-id="6589f-120">In this case, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="6589f-121">如果系統管理員稍後想要將這些 P2 使用者容錯回復回 P2，則 <EM>PoolFQDN</EM> 為 P2's FQDN。</span><span class="sxs-lookup"><span data-stu-id="6589f-121">If the administrator later wants to fail back those P2 users back to P2, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P></LI></OL><span data-ttu-id="6589f-122">請注意，必須先執行上述步驟1，再執行步驟2以保留集區完整性。</span><span class="sxs-lookup"><span data-stu-id="6589f-122">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="6589f-123">如果您在步驟1之前嘗試步驟2，則步驟 2 Cmdlet 會失敗。</span><span class="sxs-lookup"><span data-stu-id="6589f-123">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6589f-124">本章節內容</span><span class="sxs-lookup"><span data-stu-id="6589f-124">In This Section</span></span>

  - [<span data-ttu-id="6589f-125">在 Lync Server 2013 中設定及監視備份服務</span><span class="sxs-lookup"><span data-stu-id="6589f-125">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [<span data-ttu-id="6589f-126">在 Lync Server 2013 中容錯移轉集區</span><span class="sxs-lookup"><span data-stu-id="6589f-126">Failing over a pool in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-pool.md)

  - [<span data-ttu-id="6589f-127">在 Lync Server 2013 中回復集區失敗</span><span class="sxs-lookup"><span data-stu-id="6589f-127">Failing back a pool in Lync Server 2013</span></span>](lync-server-2013-failing-back-a-pool.md)

  - [<span data-ttu-id="6589f-128">在 Lync Server 2013 中容錯移轉鏡像資料庫</span><span class="sxs-lookup"><span data-stu-id="6589f-128">Failing over a mirrored database in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-mirrored-database.md)

  - [<span data-ttu-id="6589f-129">在 Lync Server 2013 中容錯移轉用於 Lync Server 同盟的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="6589f-129">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [<span data-ttu-id="6589f-130">在 Lync Server 2013 中容錯移轉用於 XMPP 同盟的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="6589f-130">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [<span data-ttu-id="6589f-131">在 Lync Server 2013 中回復用於 Lync Server 同盟或 XMPP 同盟的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="6589f-131">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [<span data-ttu-id="6589f-132">在 Lync Server 2013 中變更與前端集區相關聯的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="6589f-132">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [<span data-ttu-id="6589f-133">在 Lync Server 2013 中使用備份服務還原會議內容</span><span class="sxs-lookup"><span data-stu-id="6589f-133">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6589f-134">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6589f-134">See Also</span></span>


[<span data-ttu-id="6589f-135">在 Lync Server 2013 中規劃高可用性和嚴重損壞修復</span><span class="sxs-lookup"><span data-stu-id="6589f-135">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

