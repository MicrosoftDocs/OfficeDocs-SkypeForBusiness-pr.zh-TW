---
title: Lync Server 2013：備份及還原 Lync Server
description: Lync Server 2013：備份及還原 Lync Server。
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
ms.openlocfilehash: c1a7024b2264fb895d1562a6da0775f9397644b4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543779"
---
# <a name="backing-up-and-restoring-lync-server-2013"></a><span data-ttu-id="9f6d1-103">備份及還原 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f6d1-103">Backing up and restoring Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f6d1-104">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="9f6d1-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="9f6d1-105">在本節中，您將會發現備份 Lync Server 2013 資料的最佳作法，以及在發生失敗時進行還原。</span><span class="sxs-lookup"><span data-stu-id="9f6d1-105">In this section, you’ll find the best practices for backing up your Lync Server 2013 data, and for restoring it if you have a failure.</span></span> <span data-ttu-id="9f6d1-106">這些最佳作法適用于下列情況：</span><span class="sxs-lookup"><span data-stu-id="9f6d1-106">These best practices apply to the following situations:</span></span>

  - <span data-ttu-id="9f6d1-107">完整的 Lync 伺服器集區，任何類型 (前端伺服器、Edge Server、轉送伺服器、Persistent Chat Server 或 Director) ，或是其中一個集區中的個別伺服器。</span><span class="sxs-lookup"><span data-stu-id="9f6d1-107">An entire Lync Server pool of any type (Front End Server, Edge Server, Mediation Server, Persistent Chat Server, or Director), or an individual server in one of these pools.</span></span>

  - <span data-ttu-id="9f6d1-108">中央管理伺服器</span><span class="sxs-lookup"><span data-stu-id="9f6d1-108">The Central Management Server</span></span>

  - <span data-ttu-id="9f6d1-109">Standard Edition server</span><span class="sxs-lookup"><span data-stu-id="9f6d1-109">A Standard Edition server</span></span>

  - <span data-ttu-id="9f6d1-110">Enterprise Edition 後端伺服器</span><span class="sxs-lookup"><span data-stu-id="9f6d1-110">An Enterprise Edition Back End Server</span></span>

  - <span data-ttu-id="9f6d1-111">檔存放區</span><span class="sxs-lookup"><span data-stu-id="9f6d1-111">A File Store</span></span>

  - <span data-ttu-id="9f6d1-112">封存資料庫、監控資料庫或 Persistent 聊天資料庫</span><span class="sxs-lookup"><span data-stu-id="9f6d1-112">An Archiving database, Monitoring database, or Persistent Chat database</span></span>

<span data-ttu-id="9f6d1-113">本節不包含還原整個網站或開發待機網站的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="9f6d1-113">This section does not include information about restoring an entire site or for developing a standby site.</span></span> <span data-ttu-id="9f6d1-114">如需開發搭配前端集區的嚴重損壞修復解決方案的詳細資訊，請參閱 [在 Lync Server 2013 中規劃高可用性和嚴重損壞修復](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="9f6d1-114">For details about developing a disaster recovery solution with paired Front End pools, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="9f6d1-115">這是規劃嚴重損壞修復的建議方法。</span><span class="sxs-lookup"><span data-stu-id="9f6d1-115">This is the recommended method for planning for disaster recovery.</span></span>

<span data-ttu-id="9f6d1-116">如果您已部署成對的前端集區，當其中一個集區失敗且無法復原時，您可以使用其配對的集區中的新完整功能變數名稱 (FQDN) 還原此集區。</span><span class="sxs-lookup"><span data-stu-id="9f6d1-116">If you have deployed paired Front End pools, if one of these pools fails and becomes unrecoverable, you can restore this pool with a new fully qualified domain name (FQDN) from its paired pool.</span></span> <span data-ttu-id="9f6d1-117">如需執行此復原之步驟的詳細資訊，請參閱 [在 Lync Server 2013 中容錯移轉集](lync-server-2013-failing-over-a-pool.md)區。</span><span class="sxs-lookup"><span data-stu-id="9f6d1-117">For details on the steps to perform this recovery, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span> <span data-ttu-id="9f6d1-118">此外，如果您稍後想要重新建立屬於前端對的失敗和不可復原的集區，您可以使用在 [Lync Server 2013 中執行 ABC 前端集區容錯移轉](lync-server-2013-performing-an-abc-front-end-pool-failover.md)的步驟。</span><span class="sxs-lookup"><span data-stu-id="9f6d1-118">Additionally, if you later want to recreate a failed and unrecoverable pool that was part of a Front End pair, you can use the steps in [Performing an ABC Front End pool failover in Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md).</span></span>

<span data-ttu-id="9f6d1-119">本文件中所說明的方法涉及規劃階段的特殊考量。</span><span class="sxs-lookup"><span data-stu-id="9f6d1-119">The methodology described in this document involves special considerations during the planning phase.</span></span> <span data-ttu-id="9f6d1-120">如需詳細資訊，請參閱 [建立 Lync Server 2013 的備份與還原方案](lync-server-2013-establishing-a-backup-and-restoration-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="9f6d1-120">For details, see [Establishing a backup and restoration plan for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9f6d1-121">本章節內容</span><span class="sxs-lookup"><span data-stu-id="9f6d1-121">In This Section</span></span>

  - [<span data-ttu-id="9f6d1-122">準備 Lync Server 2013 備份及還原</span><span class="sxs-lookup"><span data-stu-id="9f6d1-122">Preparing for Lync Server 2013 backup and restoration</span></span>](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [<span data-ttu-id="9f6d1-123">在 Lync Server 2013 中備份資料和設定</span><span class="sxs-lookup"><span data-stu-id="9f6d1-123">Backing up data and settings in Lync Server 2013</span></span>](lync-server-2013-backing-up-data-and-settings.md)

  - [<span data-ttu-id="9f6d1-124">在 Lync Server 2013 中還原資料和設定</span><span class="sxs-lookup"><span data-stu-id="9f6d1-124">Restoring data and settings in Lync Server 2013</span></span>](lync-server-2013-restoring-data-and-settings.md)

  - [<span data-ttu-id="9f6d1-125">Lync Server 2013 的備份及還原工作表</span><span class="sxs-lookup"><span data-stu-id="9f6d1-125">Backup and restoration worksheets for Lync Server 2013</span></span>](lync-server-2013-backup-and-restoration-worksheets.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

