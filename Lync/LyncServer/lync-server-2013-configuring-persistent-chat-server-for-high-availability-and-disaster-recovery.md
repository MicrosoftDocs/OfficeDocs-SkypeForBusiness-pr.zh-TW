---
title: 針對高可用性和災害復原設定常設聊天室伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Persistent Chat Server for high availability and disaster recovery
ms:assetid: eebc581c-e3a0-4b69-8a43-80b607b4d8f2
ms:mtpsurl: https://technet.microsoft.com/library/JJ205364(v=OCS.15)
ms:contentKeyID: 48185760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b9ceda51485b0f4f9fde33a9499ca05998176b3
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111507"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-persistent-chat-server-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="90735-102">在 Lync Server 2013 中針對高可用性和災害復原設定常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="90735-102">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90735-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="90735-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="90735-104">Lync Server 2013，Persistent 聊天伺服器服務會使用*延伸池*設定來進行災害復原。</span><span class="sxs-lookup"><span data-stu-id="90735-104">The Lync Server 2013, Persistent Chat Server services use a *stretched pool* configuration for disaster recovery.</span></span> <span data-ttu-id="90735-105">延伸池是一種池，其中的電腦在兩個物理資料中心之間分佈，但位於單一邏輯 Lync 伺服器網站內。</span><span class="sxs-lookup"><span data-stu-id="90735-105">A stretched pool is a pool that has computers that are distributed between two physical data centers, but are within a single logical Lync Server site.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="90735-106">本節內容</span><span class="sxs-lookup"><span data-stu-id="90735-106">In This Section</span></span>

  - [<span data-ttu-id="90735-107">Lync Server 2013 中的常設聊天室伺服器的必要資源</span><span class="sxs-lookup"><span data-stu-id="90735-107">Required resources for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-required-resources-for-persistent-chat-server.md)

  - [<span data-ttu-id="90735-108">在 Lync Server 2013 中使用拓撲產生器設定高可用性和災害復原</span><span class="sxs-lookup"><span data-stu-id="90735-108">Using Topology Builder to configure high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-using-topology-builder-to-configure-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="90735-109">在 Lync Server 2013 中將延伸的常設聊天室伺服器集區用於災害復原</span><span class="sxs-lookup"><span data-stu-id="90735-109">Using a stretched Persistent Chat Server pool for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-using-a-stretched-persistent-chat-server-pool-for-disaster-recovery.md)

  - [<span data-ttu-id="90735-110">Lync Server 2013 中的 SQL Server 鏡像</span><span class="sxs-lookup"><span data-stu-id="90735-110">SQL Server mirroring in Lync Server 2013</span></span>](lync-server-2013-sql-server-mirroring.md)

  - [<span data-ttu-id="90735-111">在 Lync Server 2013 中針對常設聊天室伺服器主要資料庫設定 SQL Server 記錄傳送</span><span class="sxs-lookup"><span data-stu-id="90735-111">Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database</span></span>](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md)

  - [<span data-ttu-id="90735-112">在 Lync Server 2013 中設定主要鏡像與記錄傳送次要資料庫之間的 SQL Server 記錄傳送</span><span class="sxs-lookup"><span data-stu-id="90735-112">Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database in Lync Server 2013</span></span>](lync-server-2013-set-up-log-shipping-secondary-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

