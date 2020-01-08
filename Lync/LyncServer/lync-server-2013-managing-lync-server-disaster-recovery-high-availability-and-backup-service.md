---
title: 管理 Lync Server 災害復原、高可用性及備份服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing Lync Server disaster recovery, high availability, and Backup Service
ms:assetid: f4cd36fb-ffd6-48fa-b761-e11b3bcff91a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721939(v=OCS.15)
ms:contentKeyID: 49733876
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cada393fca28895ee5f23a12fdd55eabd211128e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981713"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="f7835-102">管理 Lync Server 2013 災害復原、高可用性及備份服務</span><span class="sxs-lookup"><span data-stu-id="f7835-102">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7835-103">_**主題上次修改日期：** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="f7835-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="f7835-104">本節包含災害復原作業的程式，以及維護備份服務以同步處理成對的前端池中的資料。</span><span class="sxs-lookup"><span data-stu-id="f7835-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="f7835-105">容錯移轉和回切的災害復原程式都是手動的。</span><span class="sxs-lookup"><span data-stu-id="f7835-105">Disaster recovery procedures, both failover and failback, are manual.</span></span> <span data-ttu-id="f7835-106">如果發生災難，系統管理員必須手動喚醒呼叫容錯移轉程式。</span><span class="sxs-lookup"><span data-stu-id="f7835-106">If there is a disaster, the administrator must manually invoke the failover procedures.</span></span> <span data-ttu-id="f7835-107">在修復池之後，回切會有同樣的作用。</span><span class="sxs-lookup"><span data-stu-id="f7835-107">The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="f7835-108">本節其餘部分中的災難復原程式是假設下列事項：</span><span class="sxs-lookup"><span data-stu-id="f7835-108">The disaster recovery procedures in the rest of this section assume the following:</span></span>

  - <span data-ttu-id="f7835-109">您的部署具有成對的前端池（位於不同的網站中），如在[Lync Server 2013 規劃高可用性和災難](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)復原中所述。</span><span class="sxs-lookup"><span data-stu-id="f7835-109">You have a deployment with paired Front End pools, located in different sites, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="f7835-110">備份服務已在這些成對的池中執行，以讓它們保持同步處理。</span><span class="sxs-lookup"><span data-stu-id="f7835-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="f7835-111">如果中央管理儲存體是裝載在任何一個 pool，則會在兩個配對的池子上安裝並執行，而其中一個池則是裝載作用中主機，另一個裝載備用的池。</span><span class="sxs-lookup"><span data-stu-id="f7835-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="f7835-112">在下列程式中， <EM>PoolFQDN</EM>參數會參照受災難影響之池的 FQDN，而不是重新導向受影響的使用者的池。</span><span class="sxs-lookup"><span data-stu-id="f7835-112">In the following procedures, the <EM>PoolFQDN</EM> parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from.</span></span> <span data-ttu-id="f7835-113">針對同一組受影響的使用者，它會參照容錯移轉與回切的 Cmdlet 中的同一個池（也就是在容錯移轉前先駐留使用者的池）。</span><span class="sxs-lookup"><span data-stu-id="f7835-113">For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><span data-ttu-id="f7835-114">例如，假設駐留在 pool P1 上的所有使用者都已容錯移轉到備份池（P2）。</span><span class="sxs-lookup"><span data-stu-id="f7835-114">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2.</span></span> <span data-ttu-id="f7835-115">如果系統管理員想要將所有目前由 P2 提供服務的使用者移至 P1，系統管理員必須執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="f7835-115">If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="f7835-116">使用容錯回復 Cmdlet，將原來駐留在 P1 上的所有使用者，從 P2 切換回 P1。</span><span class="sxs-lookup"><span data-stu-id="f7835-116">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet.</span></span> <span data-ttu-id="f7835-117">在此情況下， <EM>PoolFQDN</EM>是 P1's FQDN。</span><span class="sxs-lookup"><span data-stu-id="f7835-117">In this case, the <EM>PoolFQDN</EM> is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="f7835-118">使用容錯移轉 Cmdlet，將原來駐留在 P2 上的所有使用者容錯移轉到 P1。</span><span class="sxs-lookup"><span data-stu-id="f7835-118">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="f7835-119">在此情況下， <EM>PoolFQDN</EM>是 P2's FQDN。</span><span class="sxs-lookup"><span data-stu-id="f7835-119">In this case, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="f7835-120">如果系統管理員稍後想要將這些 P2 使用者傳回切回 P2， <EM>PoolFQDN</EM>是 P2's FQDN。</span><span class="sxs-lookup"><span data-stu-id="f7835-120">If the administrator later wants to fail back those P2 users back to P2, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P></LI></OL><span data-ttu-id="f7835-121">請注意，上述步驟1必須在步驟2之前執行，才能保留池完整性。</span><span class="sxs-lookup"><span data-stu-id="f7835-121">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="f7835-122">如果您先嘗試步驟2，再執行步驟1，則步驟 2 Cmdlet 將會失敗。</span><span class="sxs-lookup"><span data-stu-id="f7835-122">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f7835-123">本節內容</span><span class="sxs-lookup"><span data-stu-id="f7835-123">In This Section</span></span>

  - [<span data-ttu-id="f7835-124">在 Lync Server 2013 中設定和監控備份服務</span><span class="sxs-lookup"><span data-stu-id="f7835-124">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [<span data-ttu-id="f7835-125">在 Lync Server 2013 中容錯移轉集區</span><span class="sxs-lookup"><span data-stu-id="f7835-125">Failing over a pool in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-pool.md)

  - [<span data-ttu-id="f7835-126">在 Lync Server 2013 中容錯回復集區</span><span class="sxs-lookup"><span data-stu-id="f7835-126">Failing back a pool in Lync Server 2013</span></span>](lync-server-2013-failing-back-a-pool.md)

  - [<span data-ttu-id="f7835-127">在 Lync Server 2013 中容錯移轉鏡像資料庫</span><span class="sxs-lookup"><span data-stu-id="f7835-127">Failing over a mirrored database in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-mirrored-database.md)

  - [<span data-ttu-id="f7835-128">在 Lync Server 2013 中容錯移轉用於 Lync Server 同盟的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="f7835-128">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [<span data-ttu-id="f7835-129">在 Lync Server 2013 中容錯移轉用於 XMPP 同盟的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="f7835-129">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [<span data-ttu-id="f7835-130">在 Lync Server 2013 中容錯回復 Lync Server 同盟或 XMPP 同盟使用的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="f7835-130">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [<span data-ttu-id="f7835-131">在 Lync Server 2013 中變更與前端集區相關聯的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="f7835-131">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [<span data-ttu-id="f7835-132">在 Lync Server 2013 中使用備份服務還原會議內容</span><span class="sxs-lookup"><span data-stu-id="f7835-132">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f7835-133">請參閱</span><span class="sxs-lookup"><span data-stu-id="f7835-133">See Also</span></span>


[<span data-ttu-id="f7835-134">在 Lync Server 2013 中規劃高可用性和災害復原</span><span class="sxs-lookup"><span data-stu-id="f7835-134">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

