---
title: Lync Server 2013 拓撲變更
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Topology changes
ms:assetid: 9e40ef93-9ab0-498c-9bbf-f94584353e53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688153(v=OCS.15)
ms:contentKeyID: 49733756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f0ea02d1643a686e16d3d1984e756a48311b421
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982544"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topology-changes-in-lync-server-2013"></a><span data-ttu-id="973f8-102">Lync Server 2013 中的拓撲變更</span><span class="sxs-lookup"><span data-stu-id="973f8-102">Topology changes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="973f8-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="973f8-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="973f8-104">Lync Server 2013 的拓撲需求和考慮與舊版版本不同，如本節所述。</span><span class="sxs-lookup"><span data-stu-id="973f8-104">Topology requirements and considerations for Lync Server 2013 are different from those for earlier releases, as described in this section.</span></span>

<div>

## <a name="new-front-end-pools-architecture"></a><span data-ttu-id="973f8-105">新的前端池架構</span><span class="sxs-lookup"><span data-stu-id="973f8-105">New Front End Pools Architecture</span></span>

<span data-ttu-id="973f8-106">在 Lync Server 2013 中，企業版前端池的架構已變更為分散式系統架構。</span><span class="sxs-lookup"><span data-stu-id="973f8-106">In Lync Server 2013, the architecture of Enterprise Edition Front End pools has changed to a distributed systems architecture.</span></span>

<span data-ttu-id="973f8-107">使用這個新的架構，後端資料庫就不再是池中的即時資料存放區。</span><span class="sxs-lookup"><span data-stu-id="973f8-107">With this new architecture, the Back End database is no longer the real-time data store in a pool.</span></span> <span data-ttu-id="973f8-108">特定使用者的相關資訊會保留在池中的三個前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="973f8-108">Information about a particular user is kept on three Front End Servers in the pool.</span></span> <span data-ttu-id="973f8-109">針對每位使用者，一個前端伺服器充當該使用者資訊的主版，而其他兩個前端伺服器則充當複本。</span><span class="sxs-lookup"><span data-stu-id="973f8-109">For each user, one Front End Server acts as the master for that user’s information, and two other Front End Servers serve as replicas.</span></span> <span data-ttu-id="973f8-110">如果前端伺服器發生故障，另一個作為複本的前端伺服器會自動升級至 [主版]。</span><span class="sxs-lookup"><span data-stu-id="973f8-110">If a Front End Server goes down, another Front End Server which served as a replica is automatically promoted to master.</span></span>

<span data-ttu-id="973f8-111">這會在幕後發生，而系統管理員不需要知道哪些前端伺服器是使用者的主機。</span><span class="sxs-lookup"><span data-stu-id="973f8-111">This happens behind the scenes, and administrators do not need to know which Front End Servers are the masters for which users.</span></span> <span data-ttu-id="973f8-112">這種資料儲存的發佈可改善池中的效能和可伸縮性，並消除單一後端伺服器的單一故障點。</span><span class="sxs-lookup"><span data-stu-id="973f8-112">This distribution of data storage improves performance and scalability within the pool, and eliminates the single point of failure of a single Back End Server.</span></span>

<span data-ttu-id="973f8-113">後端伺服器充當使用者與會議資料的備份儲存空間，也是其他資料庫（例如回應群組資料庫）的主要儲存空間。</span><span class="sxs-lookup"><span data-stu-id="973f8-113">The Back End Server serves as backup storage for user and conference data, and is also the primary storage for other databases such as the Response Group database.</span></span>

<span data-ttu-id="973f8-114">這些改良也表示您規劃及維護您的池的方式有何變更。</span><span class="sxs-lookup"><span data-stu-id="973f8-114">These improvements also mean there are changes in how you plan and maintain your pools.</span></span> <span data-ttu-id="973f8-115">我們建議您所有的企業版前端池都包含至少三個前端伺服器，以提供最多可供設計的最大複本數。</span><span class="sxs-lookup"><span data-stu-id="973f8-115">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers, to provide the full number of replicas that the Front End pool architecture is designed for.</span></span> <span data-ttu-id="973f8-116">此外，您必須遵循將伺服器新增到前端池、移除伺服器或升級伺服器的特定程式。</span><span class="sxs-lookup"><span data-stu-id="973f8-116">Additionally, you must follow certain procedures when adding servers to a Front End pool, removing servers from it, or upgrading servers.</span></span> <span data-ttu-id="973f8-117">如需詳細資訊，請參閱[Lync Server 2013 中前端伺服器、立即訊息和目前狀態的拓撲與元件](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="973f8-117">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<div>

## <a name="server-role-topology-changes"></a><span data-ttu-id="973f8-118">伺服器角色拓朴變更</span><span class="sxs-lookup"><span data-stu-id="973f8-118">Server Role Topology Changes</span></span>

<span data-ttu-id="973f8-119">先前在個別伺服器上執行的一些伺服器角色現在已整合至前端伺服器角色，可讓您儲存硬體成本</span><span class="sxs-lookup"><span data-stu-id="973f8-119">Some server roles that previously ran on separate servers are now consolidated into the Front End Server role, enabling you to save on hardware costs</span></span>

  - <span data-ttu-id="973f8-120">在 Lync Server 2013 中，A/V 會議伺服器總是與前端伺服器 collocated。</span><span class="sxs-lookup"><span data-stu-id="973f8-120">In Lync Server 2013, A/V Conferencing Server is always collocated with Front End Server.</span></span>

  - <span data-ttu-id="973f8-121">監視和封存的前端現在總是與前端伺服器 collocated。</span><span class="sxs-lookup"><span data-stu-id="973f8-121">The front ends for both Monitoring and Archiving are now always collocated with Front End Server.</span></span> <span data-ttu-id="973f8-122">監視及封存每個仍需要個別的後端資料庫，這可以在與前端池的後端資料庫相同的伺服器上 collocated，也可以裝載在不同的後端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="973f8-122">Monitoring and Archiving each still require a separate Back-End Database, which can be collocated on the same server as the Front End Pool’s back-end database, or can be hosted on separate Back-End Servers.</span></span>

  - <span data-ttu-id="973f8-123">持續聊天伺服器現在是一個伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="973f8-123">Persistent Chat Server is now a server role.</span></span> <span data-ttu-id="973f8-124">在 Microsoft Lync Server 2010 中，群組聊天伺服器是適用于 Microsoft Lync Server 2010 的協力廠商信任應用程式。</span><span class="sxs-lookup"><span data-stu-id="973f8-124">In Microsoft Lync Server 2010, Group Chat Server was a third-party trusted application for Microsoft Lync Server 2010.</span></span> <span data-ttu-id="973f8-125">在 Lync Server 2013 中，持續聊天伺服器功能是使用三個新的伺服器角色來實現：</span><span class="sxs-lookup"><span data-stu-id="973f8-125">In Lync Server 2013, Persistent Chat Server functionality is implemented using three new server roles:</span></span>
    
      - <span data-ttu-id="973f8-126">**PersistentChatService：** 以前端角色形式實現的主要持久聊天伺服器服務</span><span class="sxs-lookup"><span data-stu-id="973f8-126">**PersistentChatService:** Main Persistent Chat Server services implemented as a front end role</span></span>
    
      - <span data-ttu-id="973f8-127">**PersistentChatStore：** 後端伺服器角色</span><span class="sxs-lookup"><span data-stu-id="973f8-127">**PersistentChatStore:** Back End Server role</span></span>
    
      - <span data-ttu-id="973f8-128">**PersistentChatComplianceStore：** 持久的聊天合規性的後端伺服器角色</span><span class="sxs-lookup"><span data-stu-id="973f8-128">**PersistentChatComplianceStore:** Back End Server role for Persistent Chat Compliance</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

