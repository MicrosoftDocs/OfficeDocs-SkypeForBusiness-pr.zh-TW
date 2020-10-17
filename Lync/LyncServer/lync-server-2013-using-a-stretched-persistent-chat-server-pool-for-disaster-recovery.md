---
title: 使用延伸的持久聊天伺服器集區進行嚴重損壞修復
description: 使用延伸的持久聊天伺服器集區進行嚴重損壞修復。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using a stretched Persistent Chat Server pool for disaster recovery
ms:assetid: 74c5287e-d70d-490a-9adc-ab419917ddd9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205007(v=OCS.15)
ms:contentKeyID: 48184506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b83a7226f7b9a49a2676b6222505f53247bd5abf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548539"
---
# <a name="using-a-stretched-persistent-chat-server-pool-for-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="9ec7f-103">在 Lync Server 2013 中使用延伸的持久聊天伺服器集區進行嚴重損壞修復</span><span class="sxs-lookup"><span data-stu-id="9ec7f-103">Using a stretched Persistent Chat Server pool for disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ec7f-104">_**主題上次修改日期：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="9ec7f-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="9ec7f-105">Persistent Chat Server 的嚴重損壞復原解決方案是在延伸的持久聊天伺服器集區上建立。</span><span class="sxs-lookup"><span data-stu-id="9ec7f-105">The disaster recovery solution for Persistent Chat Server is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="9ec7f-106">這與 Lync Server 2010 中的大都市網站恢復功能類似;不過，不需要延伸虛擬區域網路絡 (VLAN) 。</span><span class="sxs-lookup"><span data-stu-id="9ec7f-106">This is similar to metropolitan site resiliency in Lync Server 2010; however, there is no requirement for a stretched virtual local area network (VLAN).</span></span> <span data-ttu-id="9ec7f-107">透過拉伸 Persistent Chat Server 集區，您基本上會以邏輯方式設定拓撲中的一個集區，但實際將伺服器集放在兩個不同資料中心的集區中。</span><span class="sxs-lookup"><span data-stu-id="9ec7f-107">By stretching Persistent Chat Server pool, you essentially configure one pool in the topology logically, but you physically place the servers in the pool in two different data centers.</span></span> <span data-ttu-id="9ec7f-108">以相同的方式設定資料庫的 SQL Server 鏡像，並在相同的資料中心部署資料庫和鏡像。</span><span class="sxs-lookup"><span data-stu-id="9ec7f-108">Configure SQL Server mirroring for the database in the same way, and deploy the database and the mirror in the same data center.</span></span> <span data-ttu-id="9ec7f-109">您必須在次要資料中心設定備份資料庫 (包含於災害復原期間提供高可用性的選用鏡像)。</span><span class="sxs-lookup"><span data-stu-id="9ec7f-109">You need to configure a backup database in the secondary data center (with an optional mirror to provide high availability during disaster recovery).</span></span> <span data-ttu-id="9ec7f-110">此為在災害復原期間用於容錯移轉的備份資料庫。</span><span class="sxs-lookup"><span data-stu-id="9ec7f-110">This is the backup database used for failover during disaster recovery.</span></span>

<span data-ttu-id="9ec7f-111">如需如何設定 SQL Server 鏡像以取得高可用性的詳細資訊，請參閱 [Lync server 2013 中的 SQL server 鏡像](lync-server-2013-sql-server-mirroring.md)。</span><span class="sxs-lookup"><span data-stu-id="9ec7f-111">For details about how to configure SQL Server mirroring for high availability, see [SQL Server mirroring in Lync Server 2013](lync-server-2013-sql-server-mirroring.md).</span></span> <span data-ttu-id="9ec7f-112">如需容錯移轉資料庫容錯移轉的相關詳細資訊，請參閱2013在 lync server 2013 中 [為 Persistent Chat server 主資料庫設定 Sql Server 記錄傳送](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) ，並 [設定主要鏡像與記錄傳送次要資料庫之間的 Sql server 記錄傳送](lync-server-2013-set-up-log-shipping-secondary-database.md)。</span><span class="sxs-lookup"><span data-stu-id="9ec7f-112">For details about failing over the database for disaster recovery, see [Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) and [Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database in Lync Server 2013](lync-server-2013-set-up-log-shipping-secondary-database.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

