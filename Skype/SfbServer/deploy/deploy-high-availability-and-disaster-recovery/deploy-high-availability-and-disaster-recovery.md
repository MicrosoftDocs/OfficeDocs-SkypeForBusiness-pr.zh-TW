---
title: 部署高可用性和災害復原
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: 商務用 Skype Server 提供高可用性，包括伺服器池、含池配對的災害復原，以及後端伺服器高可用性的數種模式，包括 AlwaysOn 可用性群組、資料庫鏡像及 SQL 容錯移轉叢集。
ms.openlocfilehash: 68c6a12f80ac2d915c678f69146d0001daedbe5c
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790121"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a><span data-ttu-id="3202a-103">部署高可用性和災害復原</span><span class="sxs-lookup"><span data-stu-id="3202a-103">Deploy high availability and disaster recovery</span></span>
 
<span data-ttu-id="3202a-104">商務用 Skype Server 提供高可用性，包括伺服器池、含池配對的災害復原，以及後端伺服器高可用性的數種模式，包括 AlwaysOn 可用性群組、資料庫鏡像及 SQL 容錯移轉叢集。</span><span class="sxs-lookup"><span data-stu-id="3202a-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="3202a-105">高可用性指的是在一或多個伺服器關閉的情況下，仍可使用商務用 Skype Server 服務。災害復原指的是在自然或人工造成災難的情況下，讓服務繼續進行，並在災難發生前保留盡可能大的資料。</span><span class="sxs-lookup"><span data-stu-id="3202a-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="3202a-106">本節說明如何部署這些功能，以及如何針對您的其他伺服器角色提供高可用性和災難復原所需採取的步驟。</span><span class="sxs-lookup"><span data-stu-id="3202a-106">This section tells how to deploy these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span>

> [!NOTE]
> <span data-ttu-id="3202a-107">在商務用 Skype Server 2015 中提供 SQL 鏡像，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="3202a-107">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="3202a-108">使用商務用 Skype Server 2019 時，AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例（FCI）和 SQL 容錯移轉叢集方法都是可取的。</span><span class="sxs-lookup"><span data-stu-id="3202a-108">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="3202a-109">相關章節</span><span class="sxs-lookup"><span data-stu-id="3202a-109">Related sections</span></span>

[<span data-ttu-id="3202a-110">規劃商務用 Skype Server 中的高可用性與災害復原</span><span class="sxs-lookup"><span data-stu-id="3202a-110">Plan for high availability and disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a><span data-ttu-id="3202a-111">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3202a-111">See also</span></span>

[<span data-ttu-id="3202a-112">在商務用 Skype Server 的後端伺服器上部署 AlwaysOn 可用性群組</span><span class="sxs-lookup"><span data-stu-id="3202a-112">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server</span></span>](alwayson-availability-group.md)

[<span data-ttu-id="3202a-113">在商務用 Skype Server 中部署已配對的前端池以進行災害復原</span><span class="sxs-lookup"><span data-stu-id="3202a-113">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>](front-end-pools-for-disaster-recovery.md)
  
[<span data-ttu-id="3202a-114">在商務用 Skype Server 2015 中部署適用于後端伺服器高可用性的 SQL 鏡像</span><span class="sxs-lookup"><span data-stu-id="3202a-114">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](sql-mirroring-for-high-availability.md)
  
