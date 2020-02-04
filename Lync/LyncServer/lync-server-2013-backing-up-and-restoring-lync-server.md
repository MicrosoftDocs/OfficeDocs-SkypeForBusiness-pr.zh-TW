---
title: Lync Server 2013：備份和還原 Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up and restoring Lync Server 2013
ms:assetid: 07dc1f5e-af66-4e18-bf39-881dceff8bc3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202160(v=OCS.15)
ms:contentKeyID: 51541443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43a96f47bfe9d28fdbc37eea0ae62ef6cd763098
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740143"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-and-restoring-lync-server-2013"></a><span data-ttu-id="8984d-102">備份和還原 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8984d-102">Backing up and restoring Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8984d-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="8984d-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="8984d-104">在本節中，您將會發現備份 Lync Server 2013 資料的最佳做法，以及在發生失敗時將它還原。</span><span class="sxs-lookup"><span data-stu-id="8984d-104">In this section, you’ll find the best practices for backing up your Lync Server 2013 data, and for restoring it if you have a failure.</span></span> <span data-ttu-id="8984d-105">這些最佳做法適用于下列情況：</span><span class="sxs-lookup"><span data-stu-id="8984d-105">These best practices apply to the following situations:</span></span>

  - <span data-ttu-id="8984d-106">整個 Lync Server pool （前端伺服器、Edge 伺服器、中繼伺服器、永久聊天伺服器或控制器），或是其中一個池中的個別伺服器。</span><span class="sxs-lookup"><span data-stu-id="8984d-106">An entire Lync Server pool of any type (Front End Server, Edge Server, Mediation Server, Persistent Chat Server, or Director), or an individual server in one of these pools.</span></span>

  - <span data-ttu-id="8984d-107">中央管理伺服器</span><span class="sxs-lookup"><span data-stu-id="8984d-107">The Central Management Server</span></span>

  - <span data-ttu-id="8984d-108">標準版伺服器</span><span class="sxs-lookup"><span data-stu-id="8984d-108">A Standard Edition server</span></span>

  - <span data-ttu-id="8984d-109">企業版後端伺服器</span><span class="sxs-lookup"><span data-stu-id="8984d-109">An Enterprise Edition Back End Server</span></span>

  - <span data-ttu-id="8984d-110">檔案存放區</span><span class="sxs-lookup"><span data-stu-id="8984d-110">A File Store</span></span>

  - <span data-ttu-id="8984d-111">存檔資料庫、監視資料庫或持久聊天資料庫</span><span class="sxs-lookup"><span data-stu-id="8984d-111">An Archiving database, Monitoring database, or Persistent Chat database</span></span>

<span data-ttu-id="8984d-112">本節不包含還原整個網站或開發備用網站的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="8984d-112">This section does not include information about restoring an entire site or for developing a standby site.</span></span> <span data-ttu-id="8984d-113">如需使用成對的前端池來開發災害復原解決方案的詳細資料，請參閱[在 Lync Server 2013 中規劃高可用性和災難](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)復原。</span><span class="sxs-lookup"><span data-stu-id="8984d-113">For details about developing a disaster recovery solution with paired Front End pools, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="8984d-114">這是規劃災害復原的建議方法。</span><span class="sxs-lookup"><span data-stu-id="8984d-114">This is the recommended method for planning for disaster recovery.</span></span>

<span data-ttu-id="8984d-115">如果您已部署成對的前端池，且其中一個池失敗且無法復原，您就可以使用其配對的池中的新完整功能變數名稱（FQDN）來還原此池。</span><span class="sxs-lookup"><span data-stu-id="8984d-115">If you have deployed paired Front End pools, if one of these pools fails and becomes unrecoverable, you can restore this pool with a new fully qualified domain name (FQDN) from its paired pool.</span></span> <span data-ttu-id="8984d-116">如需執行此復原步驟的詳細資訊，請參閱[在 Lync Server 2013 中轉移池失敗](lync-server-2013-failing-over-a-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="8984d-116">For details on the steps to perform this recovery, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span> <span data-ttu-id="8984d-117">此外，如果您稍後想要重新建立屬於前端端對的失敗且無法使用的池，您可以使用在[Lync Server 2013 中執行 ABC 前端池容錯移轉](lync-server-2013-performing-an-abc-front-end-pool-failover.md)的步驟。</span><span class="sxs-lookup"><span data-stu-id="8984d-117">Additionally, if you later want to recreate a failed and unrecoverable pool that was part of a Front End pair, you can use the steps in [Performing an ABC Front End pool failover in Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md).</span></span>

<span data-ttu-id="8984d-118">本檔中所述的方法涉及規劃階段中的特殊考慮。</span><span class="sxs-lookup"><span data-stu-id="8984d-118">The methodology described in this document involves special considerations during the planning phase.</span></span> <span data-ttu-id="8984d-119">如需詳細資訊，請參閱[建立 Lync Server 2013 的備份與還原方案](lync-server-2013-establishing-a-backup-and-restoration-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="8984d-119">For details, see [Establishing a backup and restoration plan for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8984d-120">本節內容</span><span class="sxs-lookup"><span data-stu-id="8984d-120">In This Section</span></span>

  - [<span data-ttu-id="8984d-121">準備 Lync Server 2013 備份及還原</span><span class="sxs-lookup"><span data-stu-id="8984d-121">Preparing for Lync Server 2013 backup and restoration</span></span>](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [<span data-ttu-id="8984d-122">在 Lync Server 2013 中備份資料和設定</span><span class="sxs-lookup"><span data-stu-id="8984d-122">Backing up data and settings in Lync Server 2013</span></span>](lync-server-2013-backing-up-data-and-settings.md)

  - [<span data-ttu-id="8984d-123">在 Lync Server 2013 中還原資料和設定</span><span class="sxs-lookup"><span data-stu-id="8984d-123">Restoring data and settings in Lync Server 2013</span></span>](lync-server-2013-restoring-data-and-settings.md)

  - [<span data-ttu-id="8984d-124">Lync Server 2013 的備份和還原工作表</span><span class="sxs-lookup"><span data-stu-id="8984d-124">Backup and restoration worksheets for Lync Server 2013</span></span>](lync-server-2013-backup-and-restoration-worksheets.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

