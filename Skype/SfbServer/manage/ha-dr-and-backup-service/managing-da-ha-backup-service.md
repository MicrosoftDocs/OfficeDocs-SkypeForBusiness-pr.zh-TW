---
title: 管理災難修復、高可用性及備份服務
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 深入瞭解災難修復作業的程式，以及維護備份服務，以同步處理成對前端集區中的資料。
ms.openlocfilehash: e486a71203b64b4fc351888869ac64a24689ba7b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817153"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="26067-103">管理商務用 Skype Server 的嚴重損壞修復、高可用性及備份服務</span><span class="sxs-lookup"><span data-stu-id="26067-103">Managing Skype for Business Server disaster recovery, high availability, and Backup Service</span></span>

<span data-ttu-id="26067-104">本節包含嚴重損壞修復作業的程式，以及維護備份服務，以同步處理成對前端集區中的資料。</span><span class="sxs-lookup"><span data-stu-id="26067-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service, which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="26067-105">容錯移轉和回切回的嚴重損壞修復程式都是手動。</span><span class="sxs-lookup"><span data-stu-id="26067-105">Disaster recovery procedures, both failover and failback, are manual.</span></span> <span data-ttu-id="26067-106">如果發生災難，系統管理員必須手動呼叫容錯移轉程式。</span><span class="sxs-lookup"><span data-stu-id="26067-106">If there is a disaster, the administrator must manually invoke the failover procedures.</span></span> <span data-ttu-id="26067-107">修復集區之後，回復器也同樣適用。</span><span class="sxs-lookup"><span data-stu-id="26067-107">The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="26067-108">本節中的嚴重損壞修復程式假設下列各項：</span><span class="sxs-lookup"><span data-stu-id="26067-108">The disaster recovery procedures in this section assume the following:</span></span>

  - <span data-ttu-id="26067-109">您的部署具有成對的前端集區，位於不同的網站，如 [規劃高可用性和嚴重損壞修復](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)所述。</span><span class="sxs-lookup"><span data-stu-id="26067-109">You have a deployment with paired Front End pools, located in different sites, as described in [Plan for high availability and disaster recovery](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="26067-110">備份服務已在這些配對集區上執行，使其保持同步。</span><span class="sxs-lookup"><span data-stu-id="26067-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="26067-111">如果中央管理存放區裝載于任何集區上，則會在兩個配對集區上安裝並執行，其中一個集區會裝載作用中的主集區，而另一個集區會主控備用的集區。</span><span class="sxs-lookup"><span data-stu-id="26067-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="26067-112">在下列程式中， *PoolFQDN* 參數會參照受災難影響的集區的 FQDN，而不會重新導向受影響使用者的集區。</span><span class="sxs-lookup"><span data-stu-id="26067-112">In the following procedures, the *PoolFQDN* parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from.</span></span> <span data-ttu-id="26067-113">針對相同組受影響的使用者，它會在容錯移轉和回切 (Cmdlet 中同時參考相同的集區，也就是在容錯移轉) 之前第一位使用者的集區。</span><span class="sxs-lookup"><span data-stu-id="26067-113">For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><br><span data-ttu-id="26067-114">例如，假設某個案例位於集區 P1 的所有使用者都已容錯移轉至備份組區 P2。</span><span class="sxs-lookup"><span data-stu-id="26067-114">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2.</span></span> <span data-ttu-id="26067-115">如果系統管理員想要移動所有目前由 P2 服務服務的使用者，以 P1 為服務，系統管理員必須執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="26067-115">If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="26067-116">使用回復指令 Cmdlet，將原來在 P1 上的所有使用者都從 P2 重新容錯回復至 P1。</span><span class="sxs-lookup"><span data-stu-id="26067-116">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet.</span></span> <span data-ttu-id="26067-117">在此情況下， *PoolFQDN* 為 P1's FQDN。</span><span class="sxs-lookup"><span data-stu-id="26067-117">In this case, the *PoolFQDN* is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="26067-118">使用容錯移轉指令，將所有原先位於 P2 的使用者容錯移轉至 P1。</span><span class="sxs-lookup"><span data-stu-id="26067-118">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="26067-119">在此情況下，PoolFQDN 為 P2's FQDN。</span><span class="sxs-lookup"><span data-stu-id="26067-119">In this case, the PoolFQDN is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="26067-120">如果系統管理員稍後想要將這些 P2 使用者容錯回復回 P2，則 PoolFQDN 為 P2's FQDN。</span><span class="sxs-lookup"><span data-stu-id="26067-120">If the administrator later wants to fail back those P2 users back to P2, the PoolFQDN is P2’s FQDN.</span></span></P></LI></OL><br><span data-ttu-id="26067-121">請注意，必須先執行上述步驟1，再執行步驟2以保留集區完整性。</span><span class="sxs-lookup"><span data-stu-id="26067-121">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="26067-122">如果您在步驟1之前嘗試步驟2，則步驟 2 Cmdlet 會失敗。</span><span class="sxs-lookup"><span data-stu-id="26067-122">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>


## <a name="see-also"></a><span data-ttu-id="26067-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="26067-123">See Also</span></span>

[<span data-ttu-id="26067-124">規劃高可用性和嚴重損壞修復</span><span class="sxs-lookup"><span data-stu-id="26067-124">Plan for high availability and disaster recovery</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
