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
ms.openlocfilehash: 484a19b890602ea338f5e98a126a13582ce7e931
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522190"
---
# <a name="planning-for-front-end-pool-pairing-in-lync-server-2013"></a><span data-ttu-id="11373-102">在 Lync Server 2013 中規劃前端集區配對</span><span class="sxs-lookup"><span data-stu-id="11373-102">Planning for Front End pool pairing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11373-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="11373-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="11373-104">為了獲得 Lync Server 2013 中最佳的嚴重損壞復原能力，請將前端集區配對部署到兩個地理位置分散的網站。</span><span class="sxs-lookup"><span data-stu-id="11373-104">For the best disaster recovery abilities in Lync Server 2013, deploy pairs of Front End pools across two geographically dispersed sites.</span></span> <span data-ttu-id="11373-105">每個網站都包含與另一個網站中對應的前端集區成對的前端集區。</span><span class="sxs-lookup"><span data-stu-id="11373-105">Each site contains a Front End pool which is paired with a corresponding Front End pool in the other site.</span></span> <span data-ttu-id="11373-106">這兩個網站都使用中，而 Lync Server 備份服務會提供即時資料複寫，以保持集區同步。</span><span class="sxs-lookup"><span data-stu-id="11373-106">Both sites are active, and the Lync Server Backup Service provides real-time data replication to keep the pools synchronized.</span></span> <span data-ttu-id="11373-107">備份服務是 Lync Server 2013 中的新功能，其設計目的是用來支援嚴重損壞修復解決方案。</span><span class="sxs-lookup"><span data-stu-id="11373-107">The Backup Service is a new feature in Lync Server 2013, designed to support the disaster recovery solution.</span></span> <span data-ttu-id="11373-108">當您將集區與另一個前端集區配對時，它會安裝在前端集區上。</span><span class="sxs-lookup"><span data-stu-id="11373-108">It is installed on a Front End pool when you pair the pool with another Front End pool.</span></span>

<span data-ttu-id="11373-109">如果某個網站中的集區失敗，您可以將該集區中的使用者容錯移轉至其他網站的集區，然後再為這兩個集區中的所有使用者提供服務。</span><span class="sxs-lookup"><span data-stu-id="11373-109">If the pool in one site fails, you can fail over the users from that pool to the pool in the other site, which then provides services to all the users in both pools.</span></span> <span data-ttu-id="11373-110">為了進行容量規劃，每個集區都應該設計為在發生嚴重損壞時處理兩個集區中所有使用者的工作負載。</span><span class="sxs-lookup"><span data-stu-id="11373-110">For capacity planning purposes, each pool should be designed to handle the workloads of all users in both pools in the event of a disaster.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="11373-111">本章節內容</span><span class="sxs-lookup"><span data-stu-id="11373-111">In This Section</span></span>

  - [<span data-ttu-id="11373-112">支援 Lync Server 2013 的集區配對選項及最佳作法</span><span class="sxs-lookup"><span data-stu-id="11373-112">Supported pool pairing options and best practices for Lync Server 2013</span></span>](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [<span data-ttu-id="11373-113">Lync Server 2013 中的備份註冊器關聯</span><span class="sxs-lookup"><span data-stu-id="11373-113">Backup Registrar relationships in Lync Server 2013</span></span>](lync-server-2013-backup-registrar-relationships.md)

  - [<span data-ttu-id="11373-114">Lync Server 2013 的集區容錯移轉及集區回復器恢復時間</span><span class="sxs-lookup"><span data-stu-id="11373-114">Recovery time for pool failover and pool failback in Lync Server 2013</span></span>](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [<span data-ttu-id="11373-115">Lync Server 2013 中的中央管理存放區容錯移轉</span><span class="sxs-lookup"><span data-stu-id="11373-115">Central Management store failover in Lync Server 2013</span></span>](lync-server-2013-central-management-store-failover.md)

  - [<span data-ttu-id="11373-116">Lync Server 2013 中的前端集區配對資料安全性</span><span class="sxs-lookup"><span data-stu-id="11373-116">Front End pool pairing data security in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-pairing-data-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

