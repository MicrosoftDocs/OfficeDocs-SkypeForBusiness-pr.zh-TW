---
title: 將延伸的常設聊天室伺服器集區用於災害復原
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using a stretched Persistent Chat Server pool for disaster recovery
ms:assetid: 74c5287e-d70d-490a-9adc-ab419917ddd9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205007(v=OCS.15)
ms:contentKeyID: 48184506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ae23ed2d12548388cd1462aad653de4652633dc
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111737"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-a-stretched-persistent-chat-server-pool-for-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="3253e-102">在 Lync Server 2013 中將延伸的常設聊天室伺服器集區用於災害復原</span><span class="sxs-lookup"><span data-stu-id="3253e-102">Using a stretched Persistent Chat Server pool for disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3253e-103">_**主題上次修改日期：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="3253e-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="3253e-104">持續聊天伺服器的災害復原解決方案是在延伸持續性的持久聊天伺服器池中建立。</span><span class="sxs-lookup"><span data-stu-id="3253e-104">The disaster recovery solution for Persistent Chat Server is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="3253e-105">這與 Lync Server 2010 中的大都市版網站復原類似;不過，延伸虛擬區域網路絡（VLAN）就沒有任何需求。</span><span class="sxs-lookup"><span data-stu-id="3253e-105">This is similar to metropolitan site resiliency in Lync Server 2010; however, there is no requirement for a stretched virtual local area network (VLAN).</span></span> <span data-ttu-id="3253e-106">透過拉伸持續性聊天伺服器池，您實質上會以邏輯方式設定拓撲中的一個池，但實際上是將伺服器放在兩個不同資料中心的池中。</span><span class="sxs-lookup"><span data-stu-id="3253e-106">By stretching Persistent Chat Server pool, you essentially configure one pool in the topology logically, but you physically place the servers in the pool in two different data centers.</span></span> <span data-ttu-id="3253e-107">以相同的方式為資料庫設定 SQL Server 鏡像，並在相同的資料中心部署資料庫和鏡像。</span><span class="sxs-lookup"><span data-stu-id="3253e-107">Configure SQL Server mirroring for the database in the same way, and deploy the database and the mirror in the same data center.</span></span> <span data-ttu-id="3253e-108">您需要在次要資料中心中設定備份資料庫（在災害復原期間有選擇性的鏡像來提供高可用性）。</span><span class="sxs-lookup"><span data-stu-id="3253e-108">You need to configure a backup database in the secondary data center (with an optional mirror to provide high availability during disaster recovery).</span></span> <span data-ttu-id="3253e-109">這是在災害復原期間用來進行容錯移轉的備份資料庫。</span><span class="sxs-lookup"><span data-stu-id="3253e-109">This is the backup database used for failover during disaster recovery.</span></span>

<span data-ttu-id="3253e-110">如需有關如何設定 SQL Server 鏡像以取得高可用性的詳細資料，請參閱[Lync Server 2013 中的 Sql server 鏡像](lync-server-2013-sql-server-mirroring.md)。</span><span class="sxs-lookup"><span data-stu-id="3253e-110">For details about how to configure SQL Server mirroring for high availability, see [SQL Server mirroring in Lync Server 2013](lync-server-2013-sql-server-mirroring.md).</span></span> <span data-ttu-id="3253e-111">如需針對災難復原容錯移轉資料庫的詳細資料，請參閱[在 Lync server 2013 中設定 Sql Server 記錄傳送（針對持續聊天伺服器主要資料庫](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md)），以及[在 Lync server 2013 中的主鏡像與記錄傳送次要資料庫之間設定 Sql server 記錄傳送](lync-server-2013-set-up-log-shipping-secondary-database.md)。</span><span class="sxs-lookup"><span data-stu-id="3253e-111">For details about failing over the database for disaster recovery, see [Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) and [Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database in Lync Server 2013](lync-server-2013-set-up-log-shipping-secondary-database.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

