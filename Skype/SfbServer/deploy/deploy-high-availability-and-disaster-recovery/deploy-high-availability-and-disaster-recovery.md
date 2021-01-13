---
title: 部署高可用性和災害復原
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: 商務用 Skype 伺服器具有伺服器集區的高可用性、具有集區配對的嚴重損壞復原功能，以及後端伺服器高可用性的幾種模式，包括 AlwaysOn 可用性群組、資料庫鏡像及 SQL 容錯移轉叢集。
ms.openlocfilehash: 68baae183ff45571e38e922035d287e733bcc930
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830613"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a><span data-ttu-id="400f9-103">部署高可用性和災害復原</span><span class="sxs-lookup"><span data-stu-id="400f9-103">Deploy high availability and disaster recovery</span></span>
 
<span data-ttu-id="400f9-104">商務用 Skype 伺服器具有伺服器集區的高可用性、具有集區配對的嚴重損壞復原功能，以及後端伺服器高可用性的幾種模式，包括 AlwaysOn 可用性群組、資料庫鏡像及 SQL 容錯移轉叢集。</span><span class="sxs-lookup"><span data-stu-id="400f9-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="400f9-105">高可用性是指確定即使一或多部伺服器停機，仍然可以使用商務用 Skype Server 服務。「嚴重損壞復原」是指讓服務在自然或人工造成的情況下進行，並盡可能從災難中保留盡可能多的資料。</span><span class="sxs-lookup"><span data-stu-id="400f9-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="400f9-106">本節說明如何部署這些功能，還涵蓋您可以採取的步驟，以供部分其他伺服器角色的高可用性和嚴重損壞修復。</span><span class="sxs-lookup"><span data-stu-id="400f9-106">This section tells how to deploy these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span>

> [!NOTE]
> <span data-ttu-id="400f9-107">在商務用 Skype 2015 Server 中可使用 SQL 鏡像，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="400f9-107">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="400f9-108">AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例 (FCI) ，以及使用商務用 Skype Server 2019 的首選 SQL 容錯移轉叢集方法。</span><span class="sxs-lookup"><span data-stu-id="400f9-108">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="400f9-109">相關章節</span><span class="sxs-lookup"><span data-stu-id="400f9-109">Related sections</span></span>

[<span data-ttu-id="400f9-110">在商務用 Skype Server 中規劃高可用性和嚴重損壞修復</span><span class="sxs-lookup"><span data-stu-id="400f9-110">Plan for high availability and disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a><span data-ttu-id="400f9-111">另請參閱</span><span class="sxs-lookup"><span data-stu-id="400f9-111">See also</span></span>

[<span data-ttu-id="400f9-112">在商務用 Skype Server 中的後端伺服器上部署 AlwaysOn 可用性群組</span><span class="sxs-lookup"><span data-stu-id="400f9-112">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server</span></span>](alwayson-availability-group.md)

[<span data-ttu-id="400f9-113">在商務用 Skype Server 中部署用於嚴重損壞修復的配對前端集區</span><span class="sxs-lookup"><span data-stu-id="400f9-113">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>](front-end-pools-for-disaster-recovery.md)
  
[<span data-ttu-id="400f9-114">為商務用 Skype Server 2015 中的後端伺服器高可用性部署 SQL 鏡像</span><span class="sxs-lookup"><span data-stu-id="400f9-114">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](sql-mirroring-for-high-availability.md)
  
