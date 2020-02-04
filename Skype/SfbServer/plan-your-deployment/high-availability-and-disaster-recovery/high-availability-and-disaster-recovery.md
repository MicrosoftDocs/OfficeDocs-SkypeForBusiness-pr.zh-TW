---
title: 規劃商務用 Skype Server 中的高可用性與災害復原
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
f1.keywords:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: 商務用 Skype Server 提供高可用性，包括伺服器池、含池配對的災害復原，以及後端伺服器高可用性的數種模式，包括 AlwaysOn 可用性群組、資料庫鏡像及 SQL 容錯移轉叢集。
ms.openlocfilehash: 31059936249aa4e691f3e6b4b467841fd66a04ea
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41695968"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="b1946-103">規劃商務用 Skype Server 中的高可用性與災害復原</span><span class="sxs-lookup"><span data-stu-id="b1946-103">Plan for high availability and disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="b1946-104">商務用 Skype Server 提供高可用性，包括伺服器池、含池配對的災害復原，以及後端伺服器高可用性的數種模式，包括 AlwaysOn 可用性群組、資料庫鏡像及 SQL 容錯移轉叢集。</span><span class="sxs-lookup"><span data-stu-id="b1946-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="b1946-105">高可用性指的是在一或多個伺服器關閉的情況下，仍可使用商務用 Skype Server 服務。</span><span class="sxs-lookup"><span data-stu-id="b1946-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.</span></span> <span data-ttu-id="b1946-106">災害復原指的是在自然或人工造成災難的情況下，讓服務繼續進行，並在災難發生前保留盡可能大的資料。</span><span class="sxs-lookup"><span data-stu-id="b1946-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="b1946-107">就像在舊版的 Lync Server 中，商務用 Skype Server 中大多數伺服器角色的主要高可用性功能，都是透過 pooling 提供伺服器冗余。</span><span class="sxs-lookup"><span data-stu-id="b1946-107">As in previous versions of Lync Server, the main high availability feature for most server roles in Skype for Business Server is server redundancy via pooling.</span></span> <span data-ttu-id="b1946-108">如果執行特定伺服器角色的伺服器失敗，則池中執行相同角色的其他伺服器會載入該伺服器。</span><span class="sxs-lookup"><span data-stu-id="b1946-108">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="b1946-109">這適用于前端伺服器、邊緣伺服器、轉送伺服器和控制器。</span><span class="sxs-lookup"><span data-stu-id="b1946-109">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="b1946-110">商務用 Skype 伺服器也會提供前端池的災害復原選項。</span><span class="sxs-lookup"><span data-stu-id="b1946-110">Skype for Business Server also provides disaster recovery options for Front End pools.</span></span> <span data-ttu-id="b1946-111">您可以在不同的地理區域中設定兩個池來充當彼此的備份。</span><span class="sxs-lookup"><span data-stu-id="b1946-111">You can set up two pools in different geographical areas to serve as backups for each other.</span></span> <span data-ttu-id="b1946-112">然後，如果您擁有整個池或網站，備份池就可以繼續為兩個網站上的使用者提供服務。</span><span class="sxs-lookup"><span data-stu-id="b1946-112">Then if you have an entire pool or site go down, the backup pool can continue to provide service to users at both sites.</span></span>
  
<span data-ttu-id="b1946-113">商務用 Skype 伺服器也支援後端伺服器的四種高可用性模式： [SQL 鏡像]、[AlwaysOn 可用性] 群組、[AlwaysOn] 容錯移轉叢集實例（FCI），以及 SQL 容錯移轉叢集。</span><span class="sxs-lookup"><span data-stu-id="b1946-113">Skype for Business Server also supports four modes of high availability for your Back End Servers: SQL mirroring, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b1946-114">在商務用 Skype Server 2015 中提供 SQL 鏡像，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="b1946-114">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="b1946-115">使用商務用 Skype Server 2019 時，AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例（FCI）和 SQL 容錯移轉叢集方法都是可取的。</span><span class="sxs-lookup"><span data-stu-id="b1946-115">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="b1946-116">永久聊天伺服器不支援 AlwaysOn 可用性群組。</span><span class="sxs-lookup"><span data-stu-id="b1946-116">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="b1946-117">本節說明這些功能，以及您可以針對一些其他伺服器角色的高可用性及災難復原所需採取的步驟。</span><span class="sxs-lookup"><span data-stu-id="b1946-117">This section explains these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b1946-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b1946-118">See also</span></span>

[<span data-ttu-id="b1946-119">前端池高可用性與管理</span><span class="sxs-lookup"><span data-stu-id="b1946-119">Front End Pool high availability and management</span></span>](high-availability.md)
  
[<span data-ttu-id="b1946-120">商務用 Skype Server 中的前端池災害復原</span><span class="sxs-lookup"><span data-stu-id="b1946-120">Front End pool disaster recovery in Skype for Business Server</span></span>](disaster-recovery.md)
  
[<span data-ttu-id="b1946-121">商務用 Skype Server 中的 pool 失敗期間的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="b1946-121">User experience during pool failure in Skype for Business Server</span></span>](user-experience.md)
  
[<span data-ttu-id="b1946-122">商務用 Skype Server 的後端伺服器高可用性</span><span class="sxs-lookup"><span data-stu-id="b1946-122">Back End Server high availability in Skype for Business Server</span></span>](back-end-server.md)
  
[<span data-ttu-id="b1946-123">商務用 Skype Server 的檔案共用高可用性</span><span class="sxs-lookup"><span data-stu-id="b1946-123">File sharing high availability in Skype for Business Server</span></span>](file-sharing.md)
