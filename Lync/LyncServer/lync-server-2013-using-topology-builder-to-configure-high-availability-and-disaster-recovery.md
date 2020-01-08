---
title: 使用拓撲產生器設定高可用性和災害復原
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Topology Builder to configure high availability and disaster recovery
ms:assetid: abc1a25d-1f5e-46ef-91d2-0144fc847206
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205172(v=OCS.15)
ms:contentKeyID: 48185113
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b167ea64f42510febe0f405d15e2eafab7efc2bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978469"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="bdf5a-102">在 Lync Server 2013 中使用拓撲產生器設定高可用性和災害復原</span><span class="sxs-lookup"><span data-stu-id="bdf5a-102">Using Topology Builder to configure high availability and disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bdf5a-103">_**主題上次修改日期：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="bdf5a-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="bdf5a-104">在拓撲建立器中執行下列步驟，以設定持久聊天伺服器的高可用性和災害復原。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-104">Perform the following steps within Topology Builder to configure high availability and disaster recovery for Persistent Chat Server.</span></span>

1.  <span data-ttu-id="bdf5a-105">新增鏡像資料庫與記錄傳送次要資料庫 SQL Server 書店。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-105">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>

2.  <span data-ttu-id="bdf5a-106">編輯持續聊天伺服器的服務屬性至：</span><span class="sxs-lookup"><span data-stu-id="bdf5a-106">Edit the Persistent Chat Server service properties to:</span></span>
    
    1.  <span data-ttu-id="bdf5a-107">針對主要資料庫啟用鏡像。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-107">Enable mirroring for the primary database.</span></span>
    
    2.  <span data-ttu-id="bdf5a-108">新增主鏡像 SQL Server 存放區。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-108">Add the primary mirror SQL Server store.</span></span>
    
    3.  <span data-ttu-id="bdf5a-109">啟用 SQL Server 記錄傳送資料庫。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-109">Enable the SQL Server Log Shipping database.</span></span>
    
    4.  <span data-ttu-id="bdf5a-110">新增 SQL Server 記錄傳送的次要 SQL Server store。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-110">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    5.  <span data-ttu-id="bdf5a-111">為次要資料庫新增 SQL Server store 鏡像。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-111">Add the SQL Server store mirror for the secondary database.</span></span>
    
    6.  <span data-ttu-id="bdf5a-112">發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-112">Publish the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

