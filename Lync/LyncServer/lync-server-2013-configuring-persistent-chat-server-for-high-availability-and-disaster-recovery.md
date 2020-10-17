---
title: 設定持久聊天伺服器以取得高可用性和嚴重損壞修復
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Persistent Chat Server for high availability and disaster recovery
ms:assetid: eebc581c-e3a0-4b69-8a43-80b607b4d8f2
ms:mtpsurl: https://technet.microsoft.com/library/JJ205364(v=OCS.15)
ms:contentKeyID: 48185760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90bb6ee0d9c060787c7b750046f79810aeb0c425
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532410"
---
# <a name="configuring-persistent-chat-server-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="26c8b-102">在 Lync Server 2013 中設定持久聊天伺服器以取得高可用性和嚴重損壞修復</span><span class="sxs-lookup"><span data-stu-id="26c8b-102">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26c8b-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="26c8b-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="26c8b-104">Lync Server 2013，Persistent Chat Server 服務使用 *延伸集* 區設定進行嚴重損壞修復。</span><span class="sxs-lookup"><span data-stu-id="26c8b-104">The Lync Server 2013, Persistent Chat Server services use a *stretched pool* configuration for disaster recovery.</span></span> <span data-ttu-id="26c8b-105">延伸集區是一種集區，其電腦是在兩個實體資料中心之間散佈，但位於單一邏輯 Lync 伺服器網站內。</span><span class="sxs-lookup"><span data-stu-id="26c8b-105">A stretched pool is a pool that has computers that are distributed between two physical data centers, but are within a single logical Lync Server site.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="26c8b-106">本章節內容</span><span class="sxs-lookup"><span data-stu-id="26c8b-106">In This Section</span></span>

  - [<span data-ttu-id="26c8b-107">Lync Server 2013 中持久聊天伺服器的必要資源</span><span class="sxs-lookup"><span data-stu-id="26c8b-107">Required resources for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-required-resources-for-persistent-chat-server.md)

  - [<span data-ttu-id="26c8b-108">在 Lync Server 2013 中使用拓撲產生器來設定高可用性和嚴重損壞修復</span><span class="sxs-lookup"><span data-stu-id="26c8b-108">Using Topology Builder to configure high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-using-topology-builder-to-configure-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="26c8b-109">在 Lync Server 2013 中使用延伸的持久聊天伺服器集區進行嚴重損壞修復</span><span class="sxs-lookup"><span data-stu-id="26c8b-109">Using a stretched Persistent Chat Server pool for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-using-a-stretched-persistent-chat-server-pool-for-disaster-recovery.md)

  - [<span data-ttu-id="26c8b-110">Lync Server 2013 中的 SQL Server 鏡像</span><span class="sxs-lookup"><span data-stu-id="26c8b-110">SQL Server mirroring in Lync Server 2013</span></span>](lync-server-2013-sql-server-mirroring.md)

  - [<span data-ttu-id="26c8b-111">在 Lync Server 2013 中為 Persistent Chat Server 主資料庫設定 SQL Server 記錄傳送</span><span class="sxs-lookup"><span data-stu-id="26c8b-111">Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database</span></span>](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md)

  - [<span data-ttu-id="26c8b-112">在 Lync Server 2013 中設定主要鏡像與記錄傳送次要資料庫之間的 SQL Server 記錄傳送</span><span class="sxs-lookup"><span data-stu-id="26c8b-112">Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database in Lync Server 2013</span></span>](lync-server-2013-set-up-log-shipping-secondary-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

