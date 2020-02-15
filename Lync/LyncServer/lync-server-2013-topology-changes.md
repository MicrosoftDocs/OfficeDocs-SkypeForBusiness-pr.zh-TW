---
title: Lync Server 2013 拓撲變更
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topology changes
ms:assetid: 9e40ef93-9ab0-498c-9bbf-f94584353e53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688153(v=OCS.15)
ms:contentKeyID: 49733756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a993057d3aae52b1c080d05fe9bba4eaff1ebeab
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036523"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topology-changes-in-lync-server-2013"></a><span data-ttu-id="95816-102">Lync Server 2013 中的拓撲變更</span><span class="sxs-lookup"><span data-stu-id="95816-102">Topology changes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95816-103">_**主題上次修改日期：** 2012年-10-02_</span><span class="sxs-lookup"><span data-stu-id="95816-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="95816-104">Lync Server 2013 的拓撲需求及考量是不同於舊版，如本節所述。</span><span class="sxs-lookup"><span data-stu-id="95816-104">Topology requirements and considerations for Lync Server 2013 are different from those for earlier releases, as described in this section.</span></span>

<div>

## <a name="new-front-end-pools-architecture"></a><span data-ttu-id="95816-105">新的前端集區架構</span><span class="sxs-lookup"><span data-stu-id="95816-105">New Front End Pools Architecture</span></span>

<span data-ttu-id="95816-106">在 [Lync Server 2013 Enterprise Edition 前端集區的架構已變更為分散式的系統架構。</span><span class="sxs-lookup"><span data-stu-id="95816-106">In Lync Server 2013, the architecture of Enterprise Edition Front End pools has changed to a distributed systems architecture.</span></span>

<span data-ttu-id="95816-107">使用此新的架構後, 端資料庫不再是集區中的即時資料存放區。</span><span class="sxs-lookup"><span data-stu-id="95816-107">With this new architecture, the Back End database is no longer the real-time data store in a pool.</span></span> <span data-ttu-id="95816-108">三個前端伺服器集區中，會保留特定使用者的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="95816-108">Information about a particular user is kept on three Front End Servers in the pool.</span></span> <span data-ttu-id="95816-109">每位使用者，一部前端伺服器做為該使用者的資訊之母片及兩個其他前端伺服器做為複本。</span><span class="sxs-lookup"><span data-stu-id="95816-109">For each user, one Front End Server acts as the master for that user’s information, and two other Front End Servers serve as replicas.</span></span> <span data-ttu-id="95816-110">前端伺服器停機時，另一個前端伺服器可作為複本是否會自動升級至母片。</span><span class="sxs-lookup"><span data-stu-id="95816-110">If a Front End Server goes down, another Front End Server which served as a replica is automatically promoted to master.</span></span>

<span data-ttu-id="95816-111">發生在幕後這種情況，系統管理員不需要知道哪些前端伺服器是哪一個使用者的母片。</span><span class="sxs-lookup"><span data-stu-id="95816-111">This happens behind the scenes, and administrators do not need to know which Front End Servers are the masters for which users.</span></span> <span data-ttu-id="95816-112">此通訊群組的資料存放區提升效能與延展性內集區，並且消除單一的單一後端伺服器的失敗點。</span><span class="sxs-lookup"><span data-stu-id="95816-112">This distribution of data storage improves performance and scalability within the pool, and eliminates the single point of failure of a single Back End Server.</span></span>

<span data-ttu-id="95816-113">後端伺服器會擔任使用者與會議資料的備份儲存區，同時也是回應群組資料庫等其他資料庫的主要儲存區。</span><span class="sxs-lookup"><span data-stu-id="95816-113">The Back End Server serves as backup storage for user and conference data, and is also the primary storage for other databases such as the Response Group database.</span></span>

<span data-ttu-id="95816-114">這些改良功能也表示您如何規劃和維護您的集區中有變更。</span><span class="sxs-lookup"><span data-stu-id="95816-114">These improvements also mean there are changes in how you plan and maintain your pools.</span></span> <span data-ttu-id="95816-115">我們建議所有 Enterprise Edition 前端集區都包含至少三個前端伺服器，以提供完整的數字的前端集區架構針對所設計的複本。</span><span class="sxs-lookup"><span data-stu-id="95816-115">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers, to provide the full number of replicas that the Front End pool architecture is designed for.</span></span> <span data-ttu-id="95816-116">此外，您必須遵循特定程序將伺服器新增至前端集區時移除伺服器或伺服器升級。</span><span class="sxs-lookup"><span data-stu-id="95816-116">Additionally, you must follow certain procedures when adding servers to a Front End pool, removing servers from it, or upgrading servers.</span></span> <span data-ttu-id="95816-117">如需詳細資訊，請參閱[前端伺服器、 立即訊息和 Lync Server 2013 中的目前狀態的元件和拓撲](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="95816-117">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<div>

## <a name="server-role-topology-changes"></a><span data-ttu-id="95816-118">伺服器角色拓撲變更</span><span class="sxs-lookup"><span data-stu-id="95816-118">Server Role Topology Changes</span></span>

<span data-ttu-id="95816-119">先前在個別伺服器執行的某些伺服器角色現在已合併成前端伺服器角色，讓您節省硬體成本</span><span class="sxs-lookup"><span data-stu-id="95816-119">Some server roles that previously ran on separate servers are now consolidated into the Front End Server role, enabling you to save on hardware costs</span></span>

  - <span data-ttu-id="95816-120">在 Lync Server 2013 中，A / V 會議伺服器一律與前端伺服器組合。</span><span class="sxs-lookup"><span data-stu-id="95816-120">In Lync Server 2013, A/V Conferencing Server is always collocated with Front End Server.</span></span>

  - <span data-ttu-id="95816-121">監控和封存的前端現在一律組合與前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="95816-121">The front ends for both Monitoring and Archiving are now always collocated with Front End Server.</span></span> <span data-ttu-id="95816-122">監控和封存每個仍需要個別的後端資料庫，其中可以組合在相同的前端集區的後端資料庫伺服器上，或可以架設在不同的後端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="95816-122">Monitoring and Archiving each still require a separate Back-End Database, which can be collocated on the same server as the Front End Pool’s back-end database, or can be hosted on separate Back-End Servers.</span></span>

  - <span data-ttu-id="95816-123">Persistent Chat Server 現在是一個伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="95816-123">Persistent Chat Server is now a server role.</span></span> <span data-ttu-id="95816-124">在 [Microsoft Lync Server 2010，Group Chat 伺服器已 Microsoft Lync Server 2010 的協力廠商信任應用程式。</span><span class="sxs-lookup"><span data-stu-id="95816-124">In Microsoft Lync Server 2010, Group Chat Server was a third-party trusted application for Microsoft Lync Server 2010.</span></span> <span data-ttu-id="95816-125">在 Lync Server 2013，Persistent Chat Server 功能被實作使用三個新的伺服器角色：</span><span class="sxs-lookup"><span data-stu-id="95816-125">In Lync Server 2013, Persistent Chat Server functionality is implemented using three new server roles:</span></span>
    
      - <span data-ttu-id="95816-126">**PersistentChatService:** 實作為前端角色的主要 Persistent Chat Server 服務</span><span class="sxs-lookup"><span data-stu-id="95816-126">**PersistentChatService:** Main Persistent Chat Server services implemented as a front end role</span></span>
    
      - <span data-ttu-id="95816-127">**PersistentChatStore:** 後端伺服器角色</span><span class="sxs-lookup"><span data-stu-id="95816-127">**PersistentChatStore:** Back End Server role</span></span>
    
      - <span data-ttu-id="95816-128">**PersistentChatComplianceStore:** 常設聊天室規範後端伺服器角色</span><span class="sxs-lookup"><span data-stu-id="95816-128">**PersistentChatComplianceStore:** Back End Server role for Persistent Chat Compliance</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

