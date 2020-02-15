---
title: Lync Server 2013： 規劃前端集區配對
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
ms.openlocfilehash: 4daeb3ea88570afaf9fc90c0e252466be67ed192
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036773"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-front-end-pool-pairing-in-lync-server-2013"></a><span data-ttu-id="d3e73-102">前端集區配對 Lync Server 2013 中規劃</span><span class="sxs-lookup"><span data-stu-id="d3e73-102">Planning for Front End pool pairing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3e73-103">_**主題上次修改日期：** 2012年-09-28_</span><span class="sxs-lookup"><span data-stu-id="d3e73-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="d3e73-104">對於在 Lync Server 2013 最佳嚴重損壞修復能力，部署配對前端集區的跨兩個地理位置分散的站台。</span><span class="sxs-lookup"><span data-stu-id="d3e73-104">For the best disaster recovery abilities in Lync Server 2013, deploy pairs of Front End pools across two geographically dispersed sites.</span></span> <span data-ttu-id="d3e73-105">每個網站包含與其他站台中的對應前端集區配對前端集區。</span><span class="sxs-lookup"><span data-stu-id="d3e73-105">Each site contains a Front End pool which is paired with a corresponding Front End pool in the other site.</span></span> <span data-ttu-id="d3e73-106">這兩個網站都在使用中，與 Lync Server 備份服務提供即時資料複寫到保持同步處理的集區。</span><span class="sxs-lookup"><span data-stu-id="d3e73-106">Both sites are active, and the Lync Server Backup Service provides real-time data replication to keep the pools synchronized.</span></span> <span data-ttu-id="d3e73-107">備份服務是在設計為支援的災害復原解決方案的 Lync Server 2013 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="d3e73-107">The Backup Service is a new feature in Lync Server 2013, designed to support the disaster recovery solution.</span></span> <span data-ttu-id="d3e73-108">配對與另一個前端集區的集區時，它會安裝在前端集區。</span><span class="sxs-lookup"><span data-stu-id="d3e73-108">It is installed on a Front End pool when you pair the pool with another Front End pool.</span></span>

<span data-ttu-id="d3e73-109">如果一個站台中的集區失敗，您可以容錯移轉至其他站台中，然後在兩個集區中的所有使用者提供服務的集區將使用者從該集區。</span><span class="sxs-lookup"><span data-stu-id="d3e73-109">If the pool in one site fails, you can fail over the users from that pool to the pool in the other site, which then provides services to all the users in both pools.</span></span> <span data-ttu-id="d3e73-110">為了進行容量規劃，每個集區應被設計來處理發生嚴重損壞兩個集區中的所有使用者的工作負載。</span><span class="sxs-lookup"><span data-stu-id="d3e73-110">For capacity planning purposes, each pool should be designed to handle the workloads of all users in both pools in the event of a disaster.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d3e73-111">本章節內容</span><span class="sxs-lookup"><span data-stu-id="d3e73-111">In This Section</span></span>

  - [<span data-ttu-id="d3e73-112">支援的集區配對選項和 Lync Server 2013 的最佳做法</span><span class="sxs-lookup"><span data-stu-id="d3e73-112">Supported pool pairing options and best practices for Lync Server 2013</span></span>](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [<span data-ttu-id="d3e73-113">備份 Lync Server 2013 中的登錄器關聯</span><span class="sxs-lookup"><span data-stu-id="d3e73-113">Backup Registrar relationships in Lync Server 2013</span></span>](lync-server-2013-backup-registrar-relationships.md)

  - [<span data-ttu-id="d3e73-114">集區容錯移轉和集區容錯回復 Lync Server 2013 中的復原時間</span><span class="sxs-lookup"><span data-stu-id="d3e73-114">Recovery time for pool failover and pool failback in Lync Server 2013</span></span>](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [<span data-ttu-id="d3e73-115">Lync Server 2013 中的中央管理存放區容錯移轉</span><span class="sxs-lookup"><span data-stu-id="d3e73-115">Central Management store failover in Lync Server 2013</span></span>](lync-server-2013-central-management-store-failover.md)

  - [<span data-ttu-id="d3e73-116">前端配對 Lync Server 2013 中的資料安全性集區</span><span class="sxs-lookup"><span data-stu-id="d3e73-116">Front End pool pairing data security in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-pairing-data-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

