---
title: Lync Server 2013：後端伺服器高可用性
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
ms.openlocfilehash: 5708212aa2eb30cfcc3c3d40894ca2340475bd8b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="af8e1-102">Lync Server 2013 的後端伺服器高可用性</span><span class="sxs-lookup"><span data-stu-id="af8e1-102">Back End Server high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af8e1-103">_**主題上次修改日期：** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="af8e1-103">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="af8e1-104">為了確保後端伺服器的高可用性，您可以使用同步 SQL 鏡像或 SQL 群集。</span><span class="sxs-lookup"><span data-stu-id="af8e1-104">To ensure high availability for your Back End Servers, you can use either synchronous SQL mirroring or SQL clustering.</span></span> <span data-ttu-id="af8e1-105">使用其中一種解決方案是選用的，但建議維持貴組織的業務連續性。</span><span class="sxs-lookup"><span data-stu-id="af8e1-105">Using one of these solutions optional, but is recommended to maintain your organization's business continuity.</span></span> <span data-ttu-id="af8e1-106">在 Lync Server 2013 中，後端伺服器高可用性不支援非同步 SQL 鏡像。</span><span class="sxs-lookup"><span data-stu-id="af8e1-106">Asynchronous SQL mirroring is not supported for Back End Server high availability in Lync Server 2013.</span></span> <span data-ttu-id="af8e1-107">在本檔的其餘部分中，SQL 鏡像代表同步的 SQL 鏡像，除非明確指出。</span><span class="sxs-lookup"><span data-stu-id="af8e1-107">In the rest of this document, SQL mirroring means synchronous SQL mirroring, unless otherwise explicitly stated.</span></span>

<span data-ttu-id="af8e1-108">您可以使用拓撲結構建立器輕鬆設定 SQL 鏡像。</span><span class="sxs-lookup"><span data-stu-id="af8e1-108">You can easily set up SQL mirroring with Topology Builder.</span></span> <span data-ttu-id="af8e1-109">對於 SQL 容錯移轉叢集，您必須使用 SQL Server 進行設定。</span><span class="sxs-lookup"><span data-stu-id="af8e1-109">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="af8e1-110">如果您在與災害復原的另一個前端池成對的 pool 中使用 SQL 鏡像或 SQL 群集，您應該在兩個池中使用相同的後端高可用性方案。</span><span class="sxs-lookup"><span data-stu-id="af8e1-110">If you use either SQL mirroring or SQL clustering in a pool which is paired with another Front End pool for disaster recovery, you should use the same Back End high availability solution in both pools.</span></span> <span data-ttu-id="af8e1-111">您不應該在使用 SQL 群集的情況中，將使用 SQL 鏡像與池進行配對。</span><span class="sxs-lookup"><span data-stu-id="af8e1-111">You should not pair a pool using SQL mirroring with a pool using SQL clustering.</span></span>

<span data-ttu-id="af8e1-112">當您部署 SQL 鏡像時，會對池中的所有 Lync Server 資料庫進行鏡像，包括中央管理儲存體（如果它位於此池中），以及回應群組應用程式資料庫及通話駐留應用程式資料庫（如果這些應用程式正在池中執行。</span><span class="sxs-lookup"><span data-stu-id="af8e1-112">When you deploy SQL mirroring, all Lync Server databases in the pool are mirrored, including the Central Management store, if it is located in this pool, as well as the Response Group application database and the Call Park application database, if those applications are running in the pool.</span></span>

<span data-ttu-id="af8e1-113">有了 SQL 鏡像，就不需要使用伺服器的共用儲存空間。</span><span class="sxs-lookup"><span data-stu-id="af8e1-113">With SQL mirroring, you do not need to use shared storage for the servers.</span></span> <span data-ttu-id="af8e1-114">每個伺服器都會在本機儲存空間中保留自己的資料庫複本。</span><span class="sxs-lookup"><span data-stu-id="af8e1-114">Each server keeps its copy of the databases in local storage.</span></span>

<span data-ttu-id="af8e1-115">您可以選擇部署含或不含見證的 SQL 鏡像。</span><span class="sxs-lookup"><span data-stu-id="af8e1-115">You may choose to deploy SQL mirroring with or without a witness.</span></span> <span data-ttu-id="af8e1-116">我們建議使用見證，因為它可讓後端伺服器的容錯移轉自動進行。</span><span class="sxs-lookup"><span data-stu-id="af8e1-116">We recommend using a witness because it enables failover of the Back End Server to be automatic.</span></span> <span data-ttu-id="af8e1-117">否則，系統管理員必須手動喚醒呼叫容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="af8e1-117">Otherwise, an administrator must manually invoke failover.</span></span> <span data-ttu-id="af8e1-118">請注意，即使已部署見證，系統管理員也可以在必要時手動呼叫後端伺服器容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="af8e1-118">Note that even if a witness is deployed, an administrator can manually invoke Back End Server failover, if necessary.</span></span>

<span data-ttu-id="af8e1-119">如果您使用見證，您可以針對多對後端伺服器使用單一見證。</span><span class="sxs-lookup"><span data-stu-id="af8e1-119">If you use a witness, you can use a single witness for multiple pairs of Back End Servers.</span></span> <span data-ttu-id="af8e1-120">Witnesses 和對後端伺服器之間沒有嚴格的1:1 對應。</span><span class="sxs-lookup"><span data-stu-id="af8e1-120">There is no strict 1:1 correspondence between witnesses and pairs of Back End Servers.</span></span> <span data-ttu-id="af8e1-121">針對多對後端伺服器使用單一見證伺服器的部署，不具彈性，因為每個後端伺服器對都有單獨的見證。</span><span class="sxs-lookup"><span data-stu-id="af8e1-121">Deployments that use a single witness for multiple pairs of Back End Servers are not quite as resilient as topologies with a separate witness for each Back End Server pair.</span></span>

<span data-ttu-id="af8e1-122">如需 SQL 群集支援的詳細資訊，請參閱[Lync Server 2013 中的資料庫軟體支援](lync-server-2013-database-software-support.md)。</span><span class="sxs-lookup"><span data-stu-id="af8e1-122">For more information about SQL clustering support, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="af8e1-123">如需有關部署 SQL 群集的詳細資料，請參閱[設定 Lync server 2013 的 SQL Server 群集](lync-server-2013-configure-sql-server-clustering.md)。</span><span class="sxs-lookup"><span data-stu-id="af8e1-123">For details on deploying SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a><span data-ttu-id="af8e1-124">使用 SQL 鏡像自動後端伺服器容錯移轉的恢復時間</span><span class="sxs-lookup"><span data-stu-id="af8e1-124">Recovery Time for Automatic Back End Server Failover with SQL Mirroring</span></span>

<span data-ttu-id="af8e1-125">如需使用 SQL 鏡像的自動後端容錯移轉，工程目標為復原時間目標（RTO）為5分鐘。</span><span class="sxs-lookup"><span data-stu-id="af8e1-125">For automatic Back End failover with SQL mirroring, the engineering target for recovery time objective (RTO) is 5 minutes.</span></span> <span data-ttu-id="af8e1-126">由於同步處理 SQL 的鏡像，我們不會在回退端伺服器失敗期間預計資料遺失，除非當前端伺服器和後端伺服器在伺服器間移動資料時，在一般情況下，就不會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="af8e1-126">Because of the synchronous SQL mirroring, we do not anticipate data loss during Back End Server failures except in rare occasions when both the Front End Servers and the Back End Server go down simultaneously while data is being moved between the servers.</span></span> <span data-ttu-id="af8e1-127">針對復原點目標（RPO）的工程目標是5分鐘。</span><span class="sxs-lookup"><span data-stu-id="af8e1-127">The engineering target for recovery point objective (RPO) is 5 minutes.</span></span>

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a><span data-ttu-id="af8e1-128">在後端伺服器失敗的情況中使用 SQL 鏡像的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="af8e1-128">User Experience During Back End Server Failure with SQL Mirroring</span></span>

<span data-ttu-id="af8e1-129">故障期間的使用者體驗取決於失敗的性質，以及拓撲。</span><span class="sxs-lookup"><span data-stu-id="af8e1-129">User experience during a failure depends on the nature of the failure, and on your topology.</span></span>

<span data-ttu-id="af8e1-130">如果您使用 SQL 鏡像且已設定見證伺服器，則主體會失敗，後端伺服器容錯移轉會自動及快速進行。</span><span class="sxs-lookup"><span data-stu-id="af8e1-130">If you use SQL mirroring and have a witness configured, and the principal fails, Back End Server failover happens automatically and quickly.</span></span> <span data-ttu-id="af8e1-131">作用中的使用者不應該注意到他們的日常會話會有太大的中斷。</span><span class="sxs-lookup"><span data-stu-id="af8e1-131">Active users should not notice much interruption to their ongoing sessions.</span></span>

<span data-ttu-id="af8e1-132">如果沒有設定見證，系統會在管理員手動呼叫容錯移轉時需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="af8e1-132">If there is no witness configured, it will take some time for the administrator to manually invoke the failover.</span></span> <span data-ttu-id="af8e1-133">在這段時間內，作用中的使用者可能會受到影響。</span><span class="sxs-lookup"><span data-stu-id="af8e1-133">During that time, active users may be affected.</span></span> <span data-ttu-id="af8e1-134">它們會在大約30分鐘內繼續正常的會話。</span><span class="sxs-lookup"><span data-stu-id="af8e1-134">They will continue their sessions as normal for about 30 minutes.</span></span> <span data-ttu-id="af8e1-135">如果主版仍未還原，或系統管理員沒有失敗轉移至備份，則使用者會切換到復原模式，這表示他們無法執行需要 Lync 伺服器上的永久變更的工作（例如新增連絡人）。</span><span class="sxs-lookup"><span data-stu-id="af8e1-135">If the primary is still not restored, or an administrator has not failed over to the backup, then users are switched to Resiliency mode, meaning that they are unable to perform tasks that require a persistent change on Lync Server (such as adding a contact).</span></span>

<span data-ttu-id="af8e1-136">如果主體和鏡像後端伺服器失敗，或其中一個伺服器與見證伺服器發生故障，後端伺服器將變為無法使用（即使是仍在運作的主體）。</span><span class="sxs-lookup"><span data-stu-id="af8e1-136">If both the principal and the mirror Back End Servers fail, or if one of those servers and the witness fails, the Back End Server will become unavailable (even if it is the principal that is still working).</span></span> <span data-ttu-id="af8e1-137">在這種情況下，作用中的使用者會在一段時間後切換為復原模式。</span><span class="sxs-lookup"><span data-stu-id="af8e1-137">In this case, active users are switched to Resiliency mode after some time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

