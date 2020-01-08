---
title: Lync Server 2013 資料庫軟體支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Database software support
ms:assetid: e05d0032-bbea-4e61-987d-d07b1c045fd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398990(v=OCS.15)
ms:contentKeyID: 48185517
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bc8daef764ce5b15fd8c8b7e29f7031ebcfbafc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978265"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-software-support-in-lync-server-2013"></a><span data-ttu-id="d339f-102">Lync Server 2013 中的資料庫軟體支援</span><span class="sxs-lookup"><span data-stu-id="d339f-102">Database software support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d339f-103">_**主題上次修改日期：** 2014-12-01_</span><span class="sxs-lookup"><span data-stu-id="d339f-103">_**Topic Last Modified:** 2014-12-01_</span></span>

<span data-ttu-id="d339f-104">Lync Server 2013 支援下列資料庫管理系統：</span><span class="sxs-lookup"><span data-stu-id="d339f-104">Lync Server 2013 supports the following database management systems:</span></span>

  - <span data-ttu-id="d339f-105">**前端集區的後端資料庫、封存資料庫、監控資料庫、常設聊天室資料庫以及常設聊天室規範資料庫**</span><span class="sxs-lookup"><span data-stu-id="d339f-105">**Back-end database of a Front End pool, Archiving database, Monitoring database, persistent chat database, and persistent chat compliance database**</span></span>
    
      - <span data-ttu-id="d339f-p101">Microsoft SQL Server 2008 R2 Enterprise 資料庫軟體 (64 位元版本)。建議額外執行最新的 Service Pack。</span><span class="sxs-lookup"><span data-stu-id="d339f-p101">Microsoft SQL Server 2008 R2 Enterprise database software (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="d339f-108">Microsoft SQL Server 2008 R2 Standard (64 位元版本)。</span><span class="sxs-lookup"><span data-stu-id="d339f-108">Microsoft SQL Server 2008 R2 Standard (64-bit edition).</span></span> <span data-ttu-id="d339f-109">建議額外執行最新的 Service Pack。</span><span class="sxs-lookup"><span data-stu-id="d339f-109">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="d339f-p103">Microsoft SQL Server 2012 Enterprise (64 位元版本)。建議額外執行最新的 Service Pack。</span><span class="sxs-lookup"><span data-stu-id="d339f-p103">Microsoft SQL Server 2012 Enterprise (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="d339f-p104">Microsoft SQL Server 2012 Standard (64 位元版本)。建議額外執行最新的 Service Pack。</span><span class="sxs-lookup"><span data-stu-id="d339f-p104">Microsoft SQL Server 2012 Standard (64-bit edition). Additionally running the latest service pack is recommended.</span></span>

  - <span data-ttu-id="d339f-114">**標準版伺服器資料庫與前端伺服器資料庫**</span><span class="sxs-lookup"><span data-stu-id="d339f-114">**Standard Edition server database and Front End Server databases**</span></span>
    
      - <span data-ttu-id="d339f-115">Microsoft SQL Server 2012 Express (64 位元版本)。</span><span class="sxs-lookup"><span data-stu-id="d339f-115">Microsoft SQL Server 2012 Express (64-bit edition).</span></span> <span data-ttu-id="d339f-116">另外建議執行最新的 Service Pack。</span><span class="sxs-lookup"><span data-stu-id="d339f-116">Additionally running the latest service pack is recommended.</span></span>
        
        <span data-ttu-id="d339f-117">我們支援在前端伺服器和標準版伺服器上進行 Microsoft SQL Server 的修補與升級。</span><span class="sxs-lookup"><span data-stu-id="d339f-117">We support the patching and upgrade of Microsoft SQL Server on Front End Servers and Standard Edition servers.</span></span> <span data-ttu-id="d339f-118">不過，當您在前端伺服器上進行任何類型的升級或修補程式時，您必須考慮仲裁需求。</span><span class="sxs-lookup"><span data-stu-id="d339f-118">However, when you make any kind of upgrade or patch on Front End Servers, you must account for quorum requirements.</span></span> <span data-ttu-id="d339f-119">如需詳細資訊，請參閱[Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)及 [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="d339f-119">For more information, see [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) and [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d339f-120">Microsoft SQL Server 2012 Express （64位版本）是由 Lync Server 2013 在每個標準 Edition 伺服器和每個前端伺服器伺服器上自動安裝。</span><span class="sxs-lookup"><span data-stu-id="d339f-120">Microsoft SQL Server 2012 Express (64-bit edition) is automatically installed by Lync Server 2013 on each Standard Edition server and each Front End Server server.</span></span>

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="d339f-121">Lync Server 2013 不支援32位版本的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="d339f-121">Lync Server 2013 does not support the 32-bit edition of SQL Server.</span></span> <span data-ttu-id="d339f-122">您必須使用 64 位元版本。</span><span class="sxs-lookup"><span data-stu-id="d339f-122">You must use the 64-bit edition.</span></span></P>
> <LI>
> <P><span data-ttu-id="d339f-123">SQL Server Web edition 與 SQL Server Workgroup edition 不受支援。</span><span class="sxs-lookup"><span data-stu-id="d339f-123">SQL Server Web edition and SQL Server Workgroup edition are not supported.</span></span> <span data-ttu-id="d339f-124">您無法搭配 Lync Server 2013 使用。</span><span class="sxs-lookup"><span data-stu-id="d339f-124">You cannot use them with Lync Server 2013.</span></span></P>
> <LI>
> <P><span data-ttu-id="d339f-125">Lync Server 2013 不支援原生資料庫鏡像。</span><span class="sxs-lookup"><span data-stu-id="d339f-125">Lync Server 2013 does support native database mirroring.</span></span></P>
> <LI>
> <P><span data-ttu-id="d339f-126">若要使用監視伺服器角色，您應該安裝 SQL Server Reporting Services。</span><span class="sxs-lookup"><span data-stu-id="d339f-126">To use the Monitoring Server role, you should install SQL Server Reporting Services.</span></span></P></LI></UL>



</div>

<span data-ttu-id="d339f-127">在前端池中，後端資料庫可以是單一 SQL Server 電腦。</span><span class="sxs-lookup"><span data-stu-id="d339f-127">In a Front End pool, the back-end database can be a single SQL Server computer.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d339f-128">如果您 collocate Lync Server 資料庫與其他資料庫，我們強烈建議您評估可能會影響可用性和效能的所有因素，並確保如果一個節點發生故障，剩餘的節點就能處理載入。</span><span class="sxs-lookup"><span data-stu-id="d339f-128">If you collocate Lync Server databases with other databases, we highly recommend assessing all factors that might affect availability and performance, as well as ensuring that, if one node fails, the remaining node can handle the load.</span></span> <span data-ttu-id="d339f-129">若要確認容錯移轉功能，建議測試所有容錯移轉案例。</span><span class="sxs-lookup"><span data-stu-id="d339f-129">To verify failover capabilities, we recommend testing all failover scenarios.</span></span>



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a><span data-ttu-id="d339f-130">使用 SQL 鏡像與 SQL 叢集</span><span class="sxs-lookup"><span data-stu-id="d339f-130">Using SQL Mirroring and SQL Clustering</span></span>

<span data-ttu-id="d339f-131">Lync Server 2013 支援針對每個 Lync Server 資料庫使用 SQL 鏡像或 SQL 群集。</span><span class="sxs-lookup"><span data-stu-id="d339f-131">Lync Server 2013 supports the use of either SQL mirroring or SQL clustering for each Lync Server database.</span></span> <span data-ttu-id="d339f-132">您可以使用 Lync Server 2013 中的 [拓撲建立器] 工具，輕鬆設定 SQL 鏡像。</span><span class="sxs-lookup"><span data-stu-id="d339f-132">You can easily set up SQL mirroring with the Topology Builder tool in Lync Server 2013.</span></span> <span data-ttu-id="d339f-133">對於 SQL 容錯移轉叢集，您必須使用 SQL Server 進行設定。</span><span class="sxs-lookup"><span data-stu-id="d339f-133">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="d339f-134">Lync Server 2013 支援所有部署的 SQL 鏡像與 SQL 群集拓朴，包括從舊版 Lync Server 升級的嶄新部署和組織。</span><span class="sxs-lookup"><span data-stu-id="d339f-134">Lync Server 2013 supports both SQL mirroring and SQL clustering topologies for all deployments, including greenfield deployments and organizations that have upgraded from previous versions of Lync Server.</span></span>

<span data-ttu-id="d339f-p111">SQL 叢集支援適用於主動/被動組態。基於效能因素，被動節點不應由任何其他 SQL 執行個體共用。</span><span class="sxs-lookup"><span data-stu-id="d339f-p111">SQL Clustering support is for an active/passive configuration. For performance reasons, the passive node should not be shared by any other SQL instance.</span></span>

<span data-ttu-id="d339f-137">以下支援包含在內：</span><span class="sxs-lookup"><span data-stu-id="d339f-137">The following support is included:</span></span>

  - <span data-ttu-id="d339f-138">適用於下列項目的雙節點容錯移轉叢集：</span><span class="sxs-lookup"><span data-stu-id="d339f-138">Two-node failover clustering for the following:</span></span>
    
      - <span data-ttu-id="d339f-p112">Microsoft SQL Server 2012 Standard (64 位元版本)。建議額外執行最新的 Service Pack。</span><span class="sxs-lookup"><span data-stu-id="d339f-p112">Microsoft SQL Server 2012 Standard (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="d339f-p113">Microsoft SQL Server 2008 R2 Standard (64 位元版本)。建議額外執行最新的 Service Pack。</span><span class="sxs-lookup"><span data-stu-id="d339f-p113">Microsoft SQL Server 2008 R2 Standard (64-bit edition). Additionally running the latest service pack is recommended.</span></span>

  - <span data-ttu-id="d339f-143">適用於下列項目、最多可有 16 個節點的容錯移轉叢集：</span><span class="sxs-lookup"><span data-stu-id="d339f-143">Up to sixteen-node failover clustering for the following:</span></span>
    
      - <span data-ttu-id="d339f-p114">Microsoft SQL Server 2012 Enterprise (64 位元版本)。建議額外執行最新的 Service Pack。</span><span class="sxs-lookup"><span data-stu-id="d339f-p114">Microsoft SQL Server 2012 Enterprise (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="d339f-p115">Microsoft SQL Server 2008 R2 Enterprise 資料庫軟體 (64 位元版本)。建議額外執行最新的 Service Pack。</span><span class="sxs-lookup"><span data-stu-id="d339f-p115">Microsoft SQL Server 2008 R2 Enterprise database software (64-bit edition). Additionally running the latest service pack is recommended.</span></span>

<span data-ttu-id="d339f-148">如需有關 SQL 鏡像的詳細資訊，請參閱[Lync Server 2013 中的後端伺服器高可用性](lync-server-2013-back-end-server-high-availability.md)。</span><span class="sxs-lookup"><span data-stu-id="d339f-148">For more information about SQL mirroring, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span> <span data-ttu-id="d339f-149">如需如何部署 SQL 群集的詳細資料，請參閱[設定 Lync server 2013 的 SQL Server 群集](lync-server-2013-configure-sql-server-clustering.md)。</span><span class="sxs-lookup"><span data-stu-id="d339f-149">For details on how to deploy SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<span data-ttu-id="d339f-150">如需 SQL Server 2012 中容錯移轉叢集的詳細資訊和最佳做法<http://technet.microsoft.com/en-us/library/hh231721.aspx>，請參閱。</span><span class="sxs-lookup"><span data-stu-id="d339f-150">For more information and best practices for failover clustering in SQL Server 2012, see <http://technet.microsoft.com/en-us/library/hh231721.aspx>.</span></span> <span data-ttu-id="d339f-151">針對 SQL Server 2008 中的容錯移轉叢集<http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>，請參閱。</span><span class="sxs-lookup"><span data-stu-id="d339f-151">For failover clustering in SQL Server 2008, see <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

