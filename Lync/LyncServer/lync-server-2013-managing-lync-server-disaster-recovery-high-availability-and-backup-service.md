---
title: 管理 Lync Server 災害復原、 高可用性及備份服務
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
ms.openlocfilehash: b7ee9bd75ce0f9326c06ffda28a48193749a950c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150284"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="0b905-102">管理 Lync Server 2013 災害復原、 高可用性及備份服務</span><span class="sxs-lookup"><span data-stu-id="0b905-102">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b905-103">_**主題上次修改日期：** 2012年-11-12_</span><span class="sxs-lookup"><span data-stu-id="0b905-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="0b905-104">本節包含災難復原作業，以及維護備份服務 」 的同步處理配對前端集區中的資料的程序。</span><span class="sxs-lookup"><span data-stu-id="0b905-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="0b905-105">災害復原程序，容錯移轉和容錯回復，都是手動。</span><span class="sxs-lookup"><span data-stu-id="0b905-105">Disaster recovery procedures, both failover and failback, are manual.</span></span> <span data-ttu-id="0b905-106">如果沒有損毀，系統管理員必須以手動方式叫用容錯移轉程序。</span><span class="sxs-lookup"><span data-stu-id="0b905-106">If there is a disaster, the administrator must manually invoke the failover procedures.</span></span> <span data-ttu-id="0b905-107">適用於容錯回復之後修復之集區。</span><span class="sxs-lookup"><span data-stu-id="0b905-107">The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="0b905-108">本節的其餘部分中的災害復原程序假設下列情況：</span><span class="sxs-lookup"><span data-stu-id="0b905-108">The disaster recovery procedures in the rest of this section assume the following:</span></span>

  - <span data-ttu-id="0b905-109">您必須具有配對前端集區，位於不同的站台，作為 > 中所述[的高可用性和災害復原 Lync Server 2013 中的規劃](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)部署。</span><span class="sxs-lookup"><span data-stu-id="0b905-109">You have a deployment with paired Front End pools, located in different sites, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="0b905-110">備份服務已經對它們進行同步化這些配對集區上執行。</span><span class="sxs-lookup"><span data-stu-id="0b905-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="0b905-111">如果其中一個集區上裝載的中央管理存放區，它是安裝及執行在這兩個配對集區]，以其中一個這些集區代管作用中的主圖形和其他集區代管待命資料庫。</span><span class="sxs-lookup"><span data-stu-id="0b905-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="0b905-112">下列程序， <EM>PoolFQDN</EM>參數是指會受到嚴重損壞的集區的 FQDN，不會影響使用者的集區從重新導向。</span><span class="sxs-lookup"><span data-stu-id="0b905-112">In the following procedures, the <EM>PoolFQDN</EM> parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from.</span></span> <span data-ttu-id="0b905-113">如需受影響的使用者同一組，它參照相同的集區容錯移轉和容錯回復 cmdlet （亦即，集區的第一次位於 [容錯移轉之前的使用者） 中。</span><span class="sxs-lookup"><span data-stu-id="0b905-113">For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><span data-ttu-id="0b905-114">例如，假設所有使用者都隸屬於 P1 已容錯移轉至備份集區 P2 的集區中的案例。</span><span class="sxs-lookup"><span data-stu-id="0b905-114">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2.</span></span> <span data-ttu-id="0b905-115">如果管理員想要移動目前由 P2 到由 P1 服務的所有使用者，系統管理員必須執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="0b905-115">If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="0b905-116">Fail 備份所有原先隸屬於 P1 從 P2 到 P1 的使用者使用容錯回復指令程式。</span><span class="sxs-lookup"><span data-stu-id="0b905-116">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet.</span></span> <span data-ttu-id="0b905-117">在此情況下，則<EM>PoolFQDN</EM>是 P1 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="0b905-117">In this case, the <EM>PoolFQDN</EM> is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="0b905-118">容錯移轉所有原先隸屬於 P2 到 P1 的使用者使用容錯移轉指令程式。</span><span class="sxs-lookup"><span data-stu-id="0b905-118">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="0b905-119">在此情況下，則<EM>PoolFQDN</EM>是 P2 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="0b905-119">In this case, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="0b905-120">如果系統管理員稍後想要容錯回復那些 P2 使用者容錯回復至 P2，則<EM>PoolFQDN</EM>是 P2 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="0b905-120">If the administrator later wants to fail back those P2 users back to P2, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P></LI></OL><span data-ttu-id="0b905-121">請注意，上述步驟 1 必須執行步驟 2 來保留集區完整性之前。</span><span class="sxs-lookup"><span data-stu-id="0b905-121">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="0b905-122">如果您嘗試步驟 2 前面步驟 1，步驟 2 指令程式將會失敗。</span><span class="sxs-lookup"><span data-stu-id="0b905-122">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0b905-123">本章節內容</span><span class="sxs-lookup"><span data-stu-id="0b905-123">In This Section</span></span>

  - [<span data-ttu-id="0b905-124">設定和監控 Lync Server 2013 中備份服務</span><span class="sxs-lookup"><span data-stu-id="0b905-124">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [<span data-ttu-id="0b905-125">容錯移轉集區中 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b905-125">Failing over a pool in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-pool.md)

  - [<span data-ttu-id="0b905-126">容錯回復的 Lync Server 2013 中的集區</span><span class="sxs-lookup"><span data-stu-id="0b905-126">Failing back a pool in Lync Server 2013</span></span>](lync-server-2013-failing-back-a-pool.md)

  - [<span data-ttu-id="0b905-127">容錯移轉鏡像資料庫在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b905-127">Failing over a mirrored database in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-mirrored-database.md)

  - [<span data-ttu-id="0b905-128">容錯移轉用於 Lync Server 2013 中的 Lync Server 同盟的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="0b905-128">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [<span data-ttu-id="0b905-129">容錯移轉用於 Lync Server 2013 中的 XMPP 同盟的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="0b905-129">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [<span data-ttu-id="0b905-130">容錯回復用於 Lync Server 同盟或 Lync Server 2013 中的 XMPP 同盟的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="0b905-130">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [<span data-ttu-id="0b905-131">變更與 Lync Server 2013 中的前端集區相關聯的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="0b905-131">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [<span data-ttu-id="0b905-132">使用 Lync Server 2013 中備份服務還原會議內容</span><span class="sxs-lookup"><span data-stu-id="0b905-132">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0b905-133">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0b905-133">See Also</span></span>


[<span data-ttu-id="0b905-134">規劃 Lync Server 2013 中的高可用性和災害復原</span><span class="sxs-lookup"><span data-stu-id="0b905-134">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

