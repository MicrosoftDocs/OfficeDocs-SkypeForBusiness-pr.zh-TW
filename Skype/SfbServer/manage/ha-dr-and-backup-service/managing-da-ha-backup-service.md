---
title: 管理災害復原、高可用性和備份服務
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 瞭解災害復原作業的程式, 以及維護備份服務, 這會同步處理成對的前端池中的資料。
ms.openlocfilehash: 9664a7d9d48ca084232e2a0473a15d29d970cea6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193586"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="1589f-103">管理商務用 Skype Server 災害復原、高可用性及備份服務</span><span class="sxs-lookup"><span data-stu-id="1589f-103">Managing Skype for Business Server disaster recovery, high availability, and Backup Service</span></span>

<span data-ttu-id="1589f-104">本節包含災害復原作業的程式, 以及維護備份服務, 以同步處理成對的前端池中的資料。</span><span class="sxs-lookup"><span data-stu-id="1589f-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service, which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="1589f-105">容錯移轉和回切的災害復原程式都是手動的。</span><span class="sxs-lookup"><span data-stu-id="1589f-105">Disaster recovery procedures, both failover and failback, are manual.</span></span> <span data-ttu-id="1589f-106">如果發生災難, 系統管理員必須手動喚醒呼叫容錯移轉程式。</span><span class="sxs-lookup"><span data-stu-id="1589f-106">If there is a disaster, the administrator must manually invoke the failover procedures.</span></span> <span data-ttu-id="1589f-107">在修復池之後, 回切會有同樣的作用。</span><span class="sxs-lookup"><span data-stu-id="1589f-107">The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="1589f-108">本節中的災難復原程式假設如下:</span><span class="sxs-lookup"><span data-stu-id="1589f-108">The disaster recovery procedures in this section assume the following:</span></span>

  - <span data-ttu-id="1589f-109">您的部署具有成對的前端池 (位於不同的網站中), 如 [[高可用性] 和 [災害復原] 規劃](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="1589f-109">You have a deployment with paired Front End pools, located in different sites, as described in [Plan for high availability and disaster recovery](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="1589f-110">備份服務已在這些成對的池中執行, 以讓它們保持同步處理。</span><span class="sxs-lookup"><span data-stu-id="1589f-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="1589f-111">如果中央管理儲存體是裝載在任何一個 pool, 則會在兩個配對的池子上安裝並執行, 而其中一個池則是裝載作用中主機, 另一個裝載備用的池。</span><span class="sxs-lookup"><span data-stu-id="1589f-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1589f-112">在下列程式中, *PoolFQDN*參數會參照受災難影響之池的 FQDN, 而不是重新導向受影響的使用者的池。</span><span class="sxs-lookup"><span data-stu-id="1589f-112">In the following procedures, the *PoolFQDN* parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from.</span></span> <span data-ttu-id="1589f-113">針對同一組受影響的使用者, 它會參照容錯移轉與回切的 Cmdlet 中的同一個池 (也就是在容錯移轉前先駐留使用者的池)。</span><span class="sxs-lookup"><span data-stu-id="1589f-113">For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><br><span data-ttu-id="1589f-114">例如, 假設駐留在 pool P1 上的所有使用者都已容錯移轉到備份池 (P2)。</span><span class="sxs-lookup"><span data-stu-id="1589f-114">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2.</span></span> <span data-ttu-id="1589f-115">如果系統管理員想要將所有目前由 P2 提供服務的使用者移至 P1, 系統管理員必須執行下列步驟:</span><span class="sxs-lookup"><span data-stu-id="1589f-115">If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="1589f-116">使用容錯回復 Cmdlet, 將原來駐留在 P1 上的所有使用者, 從 P2 切換回 P1。</span><span class="sxs-lookup"><span data-stu-id="1589f-116">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet.</span></span> <span data-ttu-id="1589f-117">在此情況下, *PoolFQDN*是 P1's FQDN。</span><span class="sxs-lookup"><span data-stu-id="1589f-117">In this case, the *PoolFQDN* is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="1589f-118">使用容錯移轉 Cmdlet, 將原來駐留在 P2 上的所有使用者容錯移轉到 P1。</span><span class="sxs-lookup"><span data-stu-id="1589f-118">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="1589f-119">在此情況下, PoolFQDN 是 P2's FQDN。</span><span class="sxs-lookup"><span data-stu-id="1589f-119">In this case, the PoolFQDN is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="1589f-120">如果系統管理員稍後想要將這些 P2 使用者傳回切回 P2, PoolFQDN 是 P2's FQDN。</span><span class="sxs-lookup"><span data-stu-id="1589f-120">If the administrator later wants to fail back those P2 users back to P2, the PoolFQDN is P2’s FQDN.</span></span></P></LI></OL><br><span data-ttu-id="1589f-121">請注意, 上述步驟1必須在步驟2之前執行, 才能保留池完整性。</span><span class="sxs-lookup"><span data-stu-id="1589f-121">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="1589f-122">如果您先嘗試步驟 2, 再執行步驟 1, 則步驟 2 Cmdlet 將會失敗。</span><span class="sxs-lookup"><span data-stu-id="1589f-122">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>


## <a name="see-also"></a><span data-ttu-id="1589f-123">請參閱</span><span class="sxs-lookup"><span data-stu-id="1589f-123">See Also</span></span>

[<span data-ttu-id="1589f-124">規劃高可用性與災害復原</span><span class="sxs-lookup"><span data-stu-id="1589f-124">Plan for high availability and disaster recovery</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
