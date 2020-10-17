---
title: Lync Server 2013：後端伺服器高可用性
description: Lync Server 2013：後端伺服器高可用性。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Back End Server high availability
ms:assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205248(v=OCS.15)
ms:contentKeyID: 48185358
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 805cbf96e107329aa5c374cfa1e2d01234d360a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543769"
---
# <a name="back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="2fdae-103">Lync Server 2013 中的後端伺服器高可用性</span><span class="sxs-lookup"><span data-stu-id="2fdae-103">Back End Server high availability in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2fdae-104">_**主題上次修改日期：** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="2fdae-104">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="2fdae-105">為了確保後端伺服器的高可用性，您可以使用同步 SQL 鏡像或 SQL 叢集。</span><span class="sxs-lookup"><span data-stu-id="2fdae-105">To ensure high availability for your Back End Servers, you can use either synchronous SQL mirroring or SQL clustering.</span></span> <span data-ttu-id="2fdae-106">使用其中一種解決方案選用，但建議維護貴組織的業務持續性。</span><span class="sxs-lookup"><span data-stu-id="2fdae-106">Using one of these solutions optional, but is recommended to maintain your organization's business continuity.</span></span> <span data-ttu-id="2fdae-107">在 Lync Server 2013 中，不支援非同步 SQL 鏡像的後端伺服器高可用性。</span><span class="sxs-lookup"><span data-stu-id="2fdae-107">Asynchronous SQL mirroring is not supported for Back End Server high availability in Lync Server 2013.</span></span> <span data-ttu-id="2fdae-108">在本文的其餘部分中，SQL 鏡像是指同步的 SQL 鏡像，除非特別明確指出。</span><span class="sxs-lookup"><span data-stu-id="2fdae-108">In the rest of this document, SQL mirroring means synchronous SQL mirroring, unless otherwise explicitly stated.</span></span>

<span data-ttu-id="2fdae-109">您可以使用拓撲產生器輕鬆設定 SQL 鏡像。</span><span class="sxs-lookup"><span data-stu-id="2fdae-109">You can easily set up SQL mirroring with Topology Builder.</span></span> <span data-ttu-id="2fdae-110">針對 SQL 容錯移轉叢集，您必須使用 SQL Server 進行安裝。</span><span class="sxs-lookup"><span data-stu-id="2fdae-110">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="2fdae-111">如果您在與另一個前端集區成對的集區中使用 SQL 鏡像或 SQL 叢集，以進行嚴重損壞修復，您應該在兩個集區中使用相同的後端高可用性解決方案。</span><span class="sxs-lookup"><span data-stu-id="2fdae-111">If you use either SQL mirroring or SQL clustering in a pool which is paired with another Front End pool for disaster recovery, you should use the same Back End high availability solution in both pools.</span></span> <span data-ttu-id="2fdae-112">您不應該使用 sql 叢集與集區一起使用 SQL 鏡像，將集區配對。</span><span class="sxs-lookup"><span data-stu-id="2fdae-112">You should not pair a pool using SQL mirroring with a pool using SQL clustering.</span></span>

<span data-ttu-id="2fdae-113">當您部署 SQL 鏡像時，集區中的所有 Lync 伺服器資料庫都會進行鏡像，包括中央管理存放區（如果位於此集區中）以及回應群組應用程式資料庫及通話駐留應用程式資料庫（如果集區中正在執行這些應用程式）。</span><span class="sxs-lookup"><span data-stu-id="2fdae-113">When you deploy SQL mirroring, all Lync Server databases in the pool are mirrored, including the Central Management store, if it is located in this pool, as well as the Response Group application database and the Call Park application database, if those applications are running in the pool.</span></span>

<span data-ttu-id="2fdae-114">使用 SQL 鏡像，您不需要使用伺服器的共用儲存區。</span><span class="sxs-lookup"><span data-stu-id="2fdae-114">With SQL mirroring, you do not need to use shared storage for the servers.</span></span> <span data-ttu-id="2fdae-115">每一部伺服器都會在本機儲存區中保留其資料庫複本。</span><span class="sxs-lookup"><span data-stu-id="2fdae-115">Each server keeps its copy of the databases in local storage.</span></span>

<span data-ttu-id="2fdae-116">您可以選擇使用或不使用見證來部署 SQL 鏡像。</span><span class="sxs-lookup"><span data-stu-id="2fdae-116">You may choose to deploy SQL mirroring with or without a witness.</span></span> <span data-ttu-id="2fdae-117">我們建議使用見證，因為它可讓後端伺服器的容錯移轉成為自動。</span><span class="sxs-lookup"><span data-stu-id="2fdae-117">We recommend using a witness because it enables failover of the Back End Server to be automatic.</span></span> <span data-ttu-id="2fdae-118">否則，管理員必須手動呼叫容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="2fdae-118">Otherwise, an administrator must manually invoke failover.</span></span> <span data-ttu-id="2fdae-119">請注意，即使部署見證，管理員也可以手動叫用後端伺服器容錯移轉（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="2fdae-119">Note that even if a witness is deployed, an administrator can manually invoke Back End Server failover, if necessary.</span></span>

<span data-ttu-id="2fdae-120">如果您使用見證，您可以對多組的後端伺服器使用單一見證。</span><span class="sxs-lookup"><span data-stu-id="2fdae-120">If you use a witness, you can use a single witness for multiple pairs of Back End Servers.</span></span> <span data-ttu-id="2fdae-121">Witnesses 和後端伺服器對之間沒有嚴格的1:1 對應。</span><span class="sxs-lookup"><span data-stu-id="2fdae-121">There is no strict 1:1 correspondence between witnesses and pairs of Back End Servers.</span></span> <span data-ttu-id="2fdae-122">對多對後端伺服器使用單一見證的部署，並不像拓撲搭配每一組後端伺服器對具有個別的見證。</span><span class="sxs-lookup"><span data-stu-id="2fdae-122">Deployments that use a single witness for multiple pairs of Back End Servers are not quite as resilient as topologies with a separate witness for each Back End Server pair.</span></span>

<span data-ttu-id="2fdae-123">如需 SQL 群集支援的詳細資訊，請參閱 [Lync Server 2013 中的資料庫軟體支援](lync-server-2013-database-software-support.md)。</span><span class="sxs-lookup"><span data-stu-id="2fdae-123">For more information about SQL clustering support, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="2fdae-124">如需部署 SQL 叢集的詳細資訊，請參閱 [CONFIGURE Sql Server 叢集 For Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md)。</span><span class="sxs-lookup"><span data-stu-id="2fdae-124">For details on deploying SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a><span data-ttu-id="2fdae-125">使用 SQL 鏡像進行自動後端伺服器容錯移轉的復原時間</span><span class="sxs-lookup"><span data-stu-id="2fdae-125">Recovery Time for Automatic Back End Server Failover with SQL Mirroring</span></span>

<span data-ttu-id="2fdae-126">若要使用 SQL 鏡像進行自動後端容錯移轉，「恢復時間目標」的工程目標 (RTO) 為5分鐘。</span><span class="sxs-lookup"><span data-stu-id="2fdae-126">For automatic Back End failover with SQL mirroring, the engineering target for recovery time objective (RTO) is 5 minutes.</span></span> <span data-ttu-id="2fdae-127">因為同步 SQL 鏡像，所以在後端伺服器失敗的情況下，不會預見到資料遺失的情況，但在伺服器間移動資料時，一般情況下，當前端伺服器和後端伺服器都能同時停機的情況除外。</span><span class="sxs-lookup"><span data-stu-id="2fdae-127">Because of the synchronous SQL mirroring, we do not anticipate data loss during Back End Server failures except in rare occasions when both the Front End Servers and the Back End Server go down simultaneously while data is being moved between the servers.</span></span> <span data-ttu-id="2fdae-128">復原點目標的工程目標 (RPO) 為5分鐘。</span><span class="sxs-lookup"><span data-stu-id="2fdae-128">The engineering target for recovery point objective (RPO) is 5 minutes.</span></span>

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a><span data-ttu-id="2fdae-129">使用 SQL 鏡像的後端伺服器失敗期間的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="2fdae-129">User Experience During Back End Server Failure with SQL Mirroring</span></span>

<span data-ttu-id="2fdae-130">失敗期間的使用者經驗取決於失敗的性質和拓撲。</span><span class="sxs-lookup"><span data-stu-id="2fdae-130">User experience during a failure depends on the nature of the failure, and on your topology.</span></span>

<span data-ttu-id="2fdae-131">如果您使用 SQL 鏡像並已設定見證，但主體失敗，則後端伺服器容錯移轉會自動且快速地進行。</span><span class="sxs-lookup"><span data-stu-id="2fdae-131">If you use SQL mirroring and have a witness configured, and the principal fails, Back End Server failover happens automatically and quickly.</span></span> <span data-ttu-id="2fdae-132">作用中使用者應該不會注意到其持續進行的會話中斷很大的狀態。</span><span class="sxs-lookup"><span data-stu-id="2fdae-132">Active users should not notice much interruption to their ongoing sessions.</span></span>

<span data-ttu-id="2fdae-133">若未設定見證，系統管理員必須花一些時間來手動呼叫容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="2fdae-133">If there is no witness configured, it will take some time for the administrator to manually invoke the failover.</span></span> <span data-ttu-id="2fdae-134">在這段時間內，作用中的使用者可能會受到影響。</span><span class="sxs-lookup"><span data-stu-id="2fdae-134">During that time, active users may be affected.</span></span> <span data-ttu-id="2fdae-135">他們會將其會話繼續正常等候30分鐘。</span><span class="sxs-lookup"><span data-stu-id="2fdae-135">They will continue their sessions as normal for about 30 minutes.</span></span> <span data-ttu-id="2fdae-136">若主伺服器仍未還原，或系統管理員尚未容錯移轉至備份，使用者會切換至復原模式，也就是說，他們無法執行在 Lync Server (（例如新增連絡人) ）上需要持續變更的工作。</span><span class="sxs-lookup"><span data-stu-id="2fdae-136">If the primary is still not restored, or an administrator has not failed over to the backup, then users are switched to Resiliency mode, meaning that they are unable to perform tasks that require a persistent change on Lync Server (such as adding a contact).</span></span>

<span data-ttu-id="2fdae-137">如果主體和鏡像的後端伺服器失敗，或其中一個伺服器和見證失敗，則即使是仍在運作) 主體，後端伺服器也會無法使用 (。</span><span class="sxs-lookup"><span data-stu-id="2fdae-137">If both the principal and the mirror Back End Servers fail, or if one of those servers and the witness fails, the Back End Server will become unavailable (even if it is the principal that is still working).</span></span> <span data-ttu-id="2fdae-138">在此情況下，作用中的使用者會在一段時間後切換至復原模式。</span><span class="sxs-lookup"><span data-stu-id="2fdae-138">In this case, active users are switched to Resiliency mode after some time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

