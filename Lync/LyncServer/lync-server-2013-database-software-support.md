---
title: Lync Server 2013 資料庫軟體支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database software support
ms:assetid: e05d0032-bbea-4e61-987d-d07b1c045fd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398990(v=OCS.15)
ms:contentKeyID: 48185517
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16c37644e07fd0dfd192867d7d8372d3630d13fb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="database-software-support-in-lync-server-2013"></a><span data-ttu-id="c99a4-102">Lync Server 2013 中的資料庫軟體支援</span><span class="sxs-lookup"><span data-stu-id="c99a4-102">Database software support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c99a4-103">_**主題上次修改日期：** 2014-12-01_</span><span class="sxs-lookup"><span data-stu-id="c99a4-103">_**Topic Last Modified:** 2014-12-01_</span></span>

<span data-ttu-id="c99a4-104">Lync Server 2013 支援下列資料庫管理系統：</span><span class="sxs-lookup"><span data-stu-id="c99a4-104">Lync Server 2013 supports the following database management systems:</span></span>

  - <span data-ttu-id="c99a4-105">**前端集區的後端資料庫、封存資料庫、監控資料庫、persistent chat database 及 persistent chat 規範資料庫**</span><span class="sxs-lookup"><span data-stu-id="c99a4-105">**Back-end database of a Front End pool, Archiving database, Monitoring database, persistent chat database, and persistent chat compliance database**</span></span>
    
      - <span data-ttu-id="c99a4-106">Microsoft SQL Server 2008 R2 Enterprise database 軟體 (64-位版本) 。</span><span class="sxs-lookup"><span data-stu-id="c99a4-106">Microsoft SQL Server 2008 R2 Enterprise database software (64-bit edition).</span></span> <span data-ttu-id="c99a4-107">建議您另外執行最新的 service pack。</span><span class="sxs-lookup"><span data-stu-id="c99a4-107">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="c99a4-108">Microsoft SQL Server 2008 R2 Standard (64-bit edition) 。</span><span class="sxs-lookup"><span data-stu-id="c99a4-108">Microsoft SQL Server 2008 R2 Standard (64-bit edition).</span></span> <span data-ttu-id="c99a4-109">建議您另外執行最新的 service pack。</span><span class="sxs-lookup"><span data-stu-id="c99a4-109">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="c99a4-110">Microsoft SQL Server 2012 Enterprise (64-位版本) 。</span><span class="sxs-lookup"><span data-stu-id="c99a4-110">Microsoft SQL Server 2012 Enterprise (64-bit edition).</span></span> <span data-ttu-id="c99a4-111">建議您另外執行最新的 service pack。</span><span class="sxs-lookup"><span data-stu-id="c99a4-111">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="c99a4-112">Microsoft SQL Server 2012 Standard (64-bit edition) 。</span><span class="sxs-lookup"><span data-stu-id="c99a4-112">Microsoft SQL Server 2012 Standard (64-bit edition).</span></span> <span data-ttu-id="c99a4-113">建議您另外執行最新的 service pack。</span><span class="sxs-lookup"><span data-stu-id="c99a4-113">Additionally running the latest service pack is recommended.</span></span>

  - <span data-ttu-id="c99a4-114">**Standard Edition server 資料庫和前端伺服器資料庫**</span><span class="sxs-lookup"><span data-stu-id="c99a4-114">**Standard Edition server database and Front End Server databases**</span></span>
    
      - <span data-ttu-id="c99a4-115">Microsoft SQL Server 2012 Express (64-位版本) 。</span><span class="sxs-lookup"><span data-stu-id="c99a4-115">Microsoft SQL Server 2012 Express (64-bit edition).</span></span> <span data-ttu-id="c99a4-116">建議您另外執行最新的 service pack。</span><span class="sxs-lookup"><span data-stu-id="c99a4-116">Additionally running the latest service pack is recommended.</span></span>
        
        <span data-ttu-id="c99a4-117">我們支援在前端伺服器和 Standard Edition server 上修補及升級 Microsoft SQL Server。</span><span class="sxs-lookup"><span data-stu-id="c99a4-117">We support the patching and upgrade of Microsoft SQL Server on Front End Servers and Standard Edition servers.</span></span> <span data-ttu-id="c99a4-118">不過，當您在前端伺服器上進行任何類型的升級或修補程式時，您必須考慮仲裁需求。</span><span class="sxs-lookup"><span data-stu-id="c99a4-118">However, when you make any kind of upgrade or patch on Front End Servers, you must account for quorum requirements.</span></span> <span data-ttu-id="c99a4-119">如需詳細資訊，請參閱[Upgrade or Update 前端伺服器 In Lync server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)和[拓撲及元件中的前端伺服器、立即訊息及顯示狀態在 lync server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)中。</span><span class="sxs-lookup"><span data-stu-id="c99a4-119">For more information, see [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) and [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c99a4-120">Microsoft SQL Server 2012 Express (64-位版本) 會由 Lync Server 2013 于每個 Standard Edition server 和每一部前端伺服器伺服器自動安裝。</span><span class="sxs-lookup"><span data-stu-id="c99a4-120">Microsoft SQL Server 2012 Express (64-bit edition) is automatically installed by Lync Server 2013 on each Standard Edition server and each Front End Server server.</span></span>

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="c99a4-121">Lync Server 2013 不支援32位版本的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="c99a4-121">Lync Server 2013 does not support the 32-bit edition of SQL Server.</span></span> <span data-ttu-id="c99a4-122">您必須使用64位版本。</span><span class="sxs-lookup"><span data-stu-id="c99a4-122">You must use the 64-bit edition.</span></span></P>
> <LI>
> <P><span data-ttu-id="c99a4-123">不支援 SQL Server Web edition 和 SQL Server Workgroup edition。</span><span class="sxs-lookup"><span data-stu-id="c99a4-123">SQL Server Web edition and SQL Server Workgroup edition are not supported.</span></span> <span data-ttu-id="c99a4-124">您無法使用 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="c99a4-124">You cannot use them with Lync Server 2013.</span></span></P>
> <LI>
> <P><span data-ttu-id="c99a4-125">Lync Server 2013 不支援原生資料庫鏡像功能。</span><span class="sxs-lookup"><span data-stu-id="c99a4-125">Lync Server 2013 does support native database mirroring.</span></span></P>
> <LI>
> <P><span data-ttu-id="c99a4-126">若要使用監控伺服器角色，您應該安裝 SQL Server Reporting Services。</span><span class="sxs-lookup"><span data-stu-id="c99a4-126">To use the Monitoring Server role, you should install SQL Server Reporting Services.</span></span></P></LI></UL>



</div>

<span data-ttu-id="c99a4-127">在前端集區中，後端資料庫可以是單一的 SQL Server 電腦。</span><span class="sxs-lookup"><span data-stu-id="c99a4-127">In a Front End pool, the back-end database can be a single SQL Server computer.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c99a4-128">如果您使用其他資料庫組合 Lync Server 資料庫，我們強烈建議評估可能影響可用性和效能的所有因素，並確保如果一個節點失敗，則剩餘的節點可以處理該負載。</span><span class="sxs-lookup"><span data-stu-id="c99a4-128">If you collocate Lync Server databases with other databases, we highly recommend assessing all factors that might affect availability and performance, as well as ensuring that, if one node fails, the remaining node can handle the load.</span></span> <span data-ttu-id="c99a4-129">若要確認容錯移轉功能，建議您測試所有容錯移轉狀況。</span><span class="sxs-lookup"><span data-stu-id="c99a4-129">To verify failover capabilities, we recommend testing all failover scenarios.</span></span>



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a><span data-ttu-id="c99a4-130">使用 SQL 鏡像與 SQL 叢集</span><span class="sxs-lookup"><span data-stu-id="c99a4-130">Using SQL Mirroring and SQL Clustering</span></span>

<span data-ttu-id="c99a4-131">Lync Server 2013 支援對每個 Lync Server 資料庫使用 SQL 鏡像或 SQL 叢集。</span><span class="sxs-lookup"><span data-stu-id="c99a4-131">Lync Server 2013 supports the use of either SQL mirroring or SQL clustering for each Lync Server database.</span></span> <span data-ttu-id="c99a4-132">您可以使用 Lync Server 2013 中的拓撲產生器工具，輕鬆地設定 SQL 鏡像。</span><span class="sxs-lookup"><span data-stu-id="c99a4-132">You can easily set up SQL mirroring with the Topology Builder tool in Lync Server 2013.</span></span> <span data-ttu-id="c99a4-133">針對 SQL 容錯移轉叢集，您必須使用 SQL Server 進行安裝。</span><span class="sxs-lookup"><span data-stu-id="c99a4-133">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="c99a4-134">Lync Server 2013 同時支援所有部署的 SQL 鏡像與 SQL 叢集拓撲，包括已從舊版 Lync Server 升級的嶄新部署和組織。</span><span class="sxs-lookup"><span data-stu-id="c99a4-134">Lync Server 2013 supports both SQL mirroring and SQL clustering topologies for all deployments, including greenfield deployments and organizations that have upgraded from previous versions of Lync Server.</span></span>

<span data-ttu-id="c99a4-135">SQL 叢集支援適用于主動/被動設定。</span><span class="sxs-lookup"><span data-stu-id="c99a4-135">SQL Clustering support is for an active/passive configuration.</span></span> <span data-ttu-id="c99a4-136">基於效能考慮，被動節點不應該由任何其他 SQL 實例共用。</span><span class="sxs-lookup"><span data-stu-id="c99a4-136">For performance reasons, the passive node should not be shared by any other SQL instance.</span></span>

<span data-ttu-id="c99a4-137">包含下列支援：</span><span class="sxs-lookup"><span data-stu-id="c99a4-137">The following support is included:</span></span>

  - <span data-ttu-id="c99a4-138">下列兩個節點的容錯移轉叢集：</span><span class="sxs-lookup"><span data-stu-id="c99a4-138">Two-node failover clustering for the following:</span></span>
    
      - <span data-ttu-id="c99a4-139">Microsoft SQL Server 2012 Standard (64-bit edition) 。</span><span class="sxs-lookup"><span data-stu-id="c99a4-139">Microsoft SQL Server 2012 Standard (64-bit edition).</span></span> <span data-ttu-id="c99a4-140">建議您另外執行最新的 service pack。</span><span class="sxs-lookup"><span data-stu-id="c99a4-140">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="c99a4-141">Microsoft SQL Server 2008 R2 Standard (64-bit edition) 。</span><span class="sxs-lookup"><span data-stu-id="c99a4-141">Microsoft SQL Server 2008 R2 Standard (64-bit edition).</span></span> <span data-ttu-id="c99a4-142">建議您另外執行最新的 service pack。</span><span class="sxs-lookup"><span data-stu-id="c99a4-142">Additionally running the latest service pack is recommended.</span></span>

  - <span data-ttu-id="c99a4-143">最多十六個節點的容錯移轉叢集可用於下列各項：</span><span class="sxs-lookup"><span data-stu-id="c99a4-143">Up to sixteen-node failover clustering for the following:</span></span>
    
      - <span data-ttu-id="c99a4-144">Microsoft SQL Server 2012 Enterprise (64-位版本) 。</span><span class="sxs-lookup"><span data-stu-id="c99a4-144">Microsoft SQL Server 2012 Enterprise (64-bit edition).</span></span> <span data-ttu-id="c99a4-145">建議您另外執行最新的 service pack。</span><span class="sxs-lookup"><span data-stu-id="c99a4-145">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="c99a4-146">Microsoft SQL Server 2008 R2 Enterprise database 軟體 (64-位版本) 。</span><span class="sxs-lookup"><span data-stu-id="c99a4-146">Microsoft SQL Server 2008 R2 Enterprise database software (64-bit edition).</span></span> <span data-ttu-id="c99a4-147">建議您另外執行最新的 service pack。</span><span class="sxs-lookup"><span data-stu-id="c99a4-147">Additionally running the latest service pack is recommended.</span></span>

<span data-ttu-id="c99a4-148">如需 SQL 鏡像的詳細資訊，請參閱[Lync server 2013 中的後端伺服器高可用性](lync-server-2013-back-end-server-high-availability.md)。</span><span class="sxs-lookup"><span data-stu-id="c99a4-148">For more information about SQL mirroring, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span> <span data-ttu-id="c99a4-149">如需如何部署 SQL 叢集的詳細資訊，請參閱[CONFIGURE Sql Server 叢集 For Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md)。</span><span class="sxs-lookup"><span data-stu-id="c99a4-149">For details on how to deploy SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<span data-ttu-id="c99a4-150">如需 SQL Server 2012 中容錯移轉叢集的詳細資訊與最佳作法，請參閱 <https://technet.microsoft.com/library/hh231721.aspx> 。</span><span class="sxs-lookup"><span data-stu-id="c99a4-150">For more information and best practices for failover clustering in SQL Server 2012, see <https://technet.microsoft.com/library/hh231721.aspx>.</span></span> <span data-ttu-id="c99a4-151">如需 SQL Server 2008 中的容錯移轉叢集，請參閱 <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx> 。</span><span class="sxs-lookup"><span data-stu-id="c99a4-151">For failover clustering in SQL Server 2008, see <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx>.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

