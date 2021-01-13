---
title: 在商務用 Skype Server 中規劃高可用性和嚴重損壞修復
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.custom:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: 商務用 Skype 伺服器具有伺服器集區的高可用性、具有集區配對的嚴重損壞復原功能，以及後端伺服器高可用性的幾種模式，包括 AlwaysOn 可用性群組、資料庫鏡像及 SQL 容錯移轉叢集。
ms.openlocfilehash: 61b720bc9dce5bc8dc54a6c493429b0a3c9b27d2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802813"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="5db76-103">在商務用 Skype Server 中規劃高可用性和嚴重損壞修復</span><span class="sxs-lookup"><span data-stu-id="5db76-103">Plan for high availability and disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="5db76-104">商務用 Skype 伺服器具有伺服器集區的高可用性、具有集區配對的嚴重損壞復原功能，以及後端伺服器高可用性的幾種模式，包括 AlwaysOn 可用性群組、資料庫鏡像及 SQL 容錯移轉叢集。</span><span class="sxs-lookup"><span data-stu-id="5db76-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="5db76-105">高可用性是指確定即使一或多部伺服器停機，仍然可以使用商務用 Skype Server 服務。</span><span class="sxs-lookup"><span data-stu-id="5db76-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.</span></span> <span data-ttu-id="5db76-106">「嚴重損壞復原」是指讓服務在自然或人工造成的情況下進行，並盡可能從災難中保留盡可能多的資料。</span><span class="sxs-lookup"><span data-stu-id="5db76-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="5db76-107">如同舊版的 Lync Server，商務用 Skype Server 中的大部分伺服器角色的主要高可用性功能，都是透過 pooling pooling server 冗余度。</span><span class="sxs-lookup"><span data-stu-id="5db76-107">As in previous versions of Lync Server, the main high availability feature for most server roles in Skype for Business Server is server redundancy via pooling.</span></span> <span data-ttu-id="5db76-108">如果執行特定伺服器角色的伺服器失敗，集區中執行相同角色的其他伺服器就會接手該伺服器的負載。</span><span class="sxs-lookup"><span data-stu-id="5db76-108">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="5db76-109">這適用於前端伺服器、Edge Server、中繼伺服器和 Director。</span><span class="sxs-lookup"><span data-stu-id="5db76-109">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="5db76-110">商務用 Skype 伺服器也會提供前端集區的嚴重損壞修復選項。</span><span class="sxs-lookup"><span data-stu-id="5db76-110">Skype for Business Server also provides disaster recovery options for Front End pools.</span></span> <span data-ttu-id="5db76-111">您可以設定不同地理區域中的兩個集區，以做為彼此的備份。</span><span class="sxs-lookup"><span data-stu-id="5db76-111">You can set up two pools in different geographical areas to serve as backups for each other.</span></span> <span data-ttu-id="5db76-112">當您有整個集區或網站停機時，備份組區可以繼續為這兩個網站的使用者提供服務。</span><span class="sxs-lookup"><span data-stu-id="5db76-112">Then if you have an entire pool or site go down, the backup pool can continue to provide service to users at both sites.</span></span>
  
<span data-ttu-id="5db76-113">商務用 Skype 伺服器也支援後端伺服器的四種高可用性模式：「SQL 鏡像」、「AlwaysOn 可用性群組」、AlwaysOn 容錯移轉叢集實例 (FCI) 及 SQL 容錯移轉叢集。</span><span class="sxs-lookup"><span data-stu-id="5db76-113">Skype for Business Server also supports four modes of high availability for your Back End Servers: SQL mirroring, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5db76-114">在商務用 Skype 2015 Server 中可使用 SQL 鏡像，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="5db76-114">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="5db76-115">AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例 (FCI) ，以及使用商務用 Skype Server 2019 的首選 SQL 容錯移轉叢集方法。</span><span class="sxs-lookup"><span data-stu-id="5db76-115">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="5db76-116">Persistent Chat Server 不支援 AlwaysOn 可用性群組。</span><span class="sxs-lookup"><span data-stu-id="5db76-116">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="5db76-117">本節說明這些功能，也涵蓋您可以採取的步驟，以進行部分其他伺服器角色的高可用性和嚴重損壞修復。</span><span class="sxs-lookup"><span data-stu-id="5db76-117">This section explains these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5db76-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5db76-118">See also</span></span>

[<span data-ttu-id="5db76-119">前端集區高可用性和管理</span><span class="sxs-lookup"><span data-stu-id="5db76-119">Front End Pool high availability and management</span></span>](high-availability.md)
  
[<span data-ttu-id="5db76-120">商務用 Skype Server 中的前端集區嚴重損壞修復</span><span class="sxs-lookup"><span data-stu-id="5db76-120">Front End pool disaster recovery in Skype for Business Server</span></span>](disaster-recovery.md)
  
[<span data-ttu-id="5db76-121">商務用 Skype 伺服器集區失敗期間的使用者經驗</span><span class="sxs-lookup"><span data-stu-id="5db76-121">User experience during pool failure in Skype for Business Server</span></span>](user-experience.md)
  
[<span data-ttu-id="5db76-122">商務用 Skype Server 中的後端伺服器高可用性</span><span class="sxs-lookup"><span data-stu-id="5db76-122">Back End Server high availability in Skype for Business Server</span></span>](back-end-server.md)
  
[<span data-ttu-id="5db76-123">商務用 Skype Server 中的檔共用高可用性</span><span class="sxs-lookup"><span data-stu-id="5db76-123">File sharing high availability in Skype for Business Server</span></span>](file-sharing.md)
