---
title: Lync Server 2013：規劃前端集區配對
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Front End pool pairing
ms:assetid: cca5773d-57ff-45ce-a7b4-f82ae697c477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205293(v=OCS.15)
ms:contentKeyID: 48185508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d85f6e19f3aa74c09a522e737d1223095f17d7c1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-front-end-pool-pairing-in-lync-server-2013"></a><span data-ttu-id="26f3e-102">在 Lync Server 2013 中規劃前端集區配對</span><span class="sxs-lookup"><span data-stu-id="26f3e-102">Planning for Front End pool pairing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26f3e-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="26f3e-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="26f3e-104">針對 Lync Server 2013 中最佳的災害復原能力，請跨兩個地理位置分散的網站，部署前端池的對。</span><span class="sxs-lookup"><span data-stu-id="26f3e-104">For the best disaster recovery abilities in Lync Server 2013, deploy pairs of Front End pools across two geographically dispersed sites.</span></span> <span data-ttu-id="26f3e-105">每個網站都包含與另一個網站中相對應的前端池配對的前端池。</span><span class="sxs-lookup"><span data-stu-id="26f3e-105">Each site contains a Front End pool which is paired with a corresponding Front End pool in the other site.</span></span> <span data-ttu-id="26f3e-106">這兩個網站都是作用中的，而 Lync Server 備份服務提供即時資料複製來保持池同步處理。</span><span class="sxs-lookup"><span data-stu-id="26f3e-106">Both sites are active, and the Lync Server Backup Service provides real-time data replication to keep the pools synchronized.</span></span> <span data-ttu-id="26f3e-107">備份服務是 Lync Server 2013 中的新功能，可用於支援災害復原方案。</span><span class="sxs-lookup"><span data-stu-id="26f3e-107">The Backup Service is a new feature in Lync Server 2013, designed to support the disaster recovery solution.</span></span> <span data-ttu-id="26f3e-108">當您將池與另一個前端池配對時，它會安裝在前端池。</span><span class="sxs-lookup"><span data-stu-id="26f3e-108">It is installed on a Front End pool when you pair the pool with another Front End pool.</span></span>

<span data-ttu-id="26f3e-109">如果一個網站中的 [池] 失敗，您可以將該池的使用者容錯移轉至其他網站的 [池]，然後在這兩個池中的所有使用者提供服務。</span><span class="sxs-lookup"><span data-stu-id="26f3e-109">If the pool in one site fails, you can fail over the users from that pool to the pool in the other site, which then provides services to all the users in both pools.</span></span> <span data-ttu-id="26f3e-110">針對容量規劃目的，每個池都應該設計為在發生災難事件時，處理兩個彙集中所有使用者的工作量。</span><span class="sxs-lookup"><span data-stu-id="26f3e-110">For capacity planning purposes, each pool should be designed to handle the workloads of all users in both pools in the event of a disaster.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="26f3e-111">本節內容</span><span class="sxs-lookup"><span data-stu-id="26f3e-111">In This Section</span></span>

  - [<span data-ttu-id="26f3e-112">支援 Lync Server 2013 的池配對選項和最佳做法</span><span class="sxs-lookup"><span data-stu-id="26f3e-112">Supported pool pairing options and best practices for Lync Server 2013</span></span>](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [<span data-ttu-id="26f3e-113">Lync Server 2013 中的備份登錄器關聯</span><span class="sxs-lookup"><span data-stu-id="26f3e-113">Backup Registrar relationships in Lync Server 2013</span></span>](lync-server-2013-backup-registrar-relationships.md)

  - [<span data-ttu-id="26f3e-114">Lync Server 2013 中的集區容錯回復與集區容錯移轉的復原時間</span><span class="sxs-lookup"><span data-stu-id="26f3e-114">Recovery time for pool failover and pool failback in Lync Server 2013</span></span>](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [<span data-ttu-id="26f3e-115">Lync Server 2013 中的中央管理存放區容錯移轉</span><span class="sxs-lookup"><span data-stu-id="26f3e-115">Central Management store failover in Lync Server 2013</span></span>](lync-server-2013-central-management-store-failover.md)

  - [<span data-ttu-id="26f3e-116">Lync Server 2013 中前端集區配對資料安全性</span><span class="sxs-lookup"><span data-stu-id="26f3e-116">Front End pool pairing data security in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-pairing-data-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

