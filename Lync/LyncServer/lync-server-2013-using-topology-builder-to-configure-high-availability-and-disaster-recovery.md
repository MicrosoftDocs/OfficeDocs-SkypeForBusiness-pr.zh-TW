---
title: 使用拓撲產生器設定高可用性與災害復原
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Topology Builder to configure high availability and disaster recovery
ms:assetid: abc1a25d-1f5e-46ef-91d2-0144fc847206
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205172(v=OCS.15)
ms:contentKeyID: 48185113
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56f74465ecba83ec2d4f857a504952a1ed271fb7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="78a0d-102">使用拓撲產生器 Lync Server 2013 中設定高可用性與災害復原</span><span class="sxs-lookup"><span data-stu-id="78a0d-102">Using Topology Builder to configure high availability and disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78a0d-103">_**主題上次修改日期：** 2012年-10-06_</span><span class="sxs-lookup"><span data-stu-id="78a0d-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="78a0d-104">執行下列步驟在拓撲產生器來設定 for Persistent Chat Server 的高可用性和災害復原。</span><span class="sxs-lookup"><span data-stu-id="78a0d-104">Perform the following steps within Topology Builder to configure high availability and disaster recovery for Persistent Chat Server.</span></span>

1.  <span data-ttu-id="78a0d-105">新增鏡像資料庫與記錄傳送次要資料庫 SQL Server 儲存區。</span><span class="sxs-lookup"><span data-stu-id="78a0d-105">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>

2.  <span data-ttu-id="78a0d-106">編輯 Persistent Chat Server 服務屬性：</span><span class="sxs-lookup"><span data-stu-id="78a0d-106">Edit the Persistent Chat Server service properties to:</span></span>
    
    1.  <span data-ttu-id="78a0d-107">啟用主要資料庫的鏡像。</span><span class="sxs-lookup"><span data-stu-id="78a0d-107">Enable mirroring for the primary database.</span></span>
    
    2.  <span data-ttu-id="78a0d-108">新增主要鏡像 SQL Server 儲存區。</span><span class="sxs-lookup"><span data-stu-id="78a0d-108">Add the primary mirror SQL Server store.</span></span>
    
    3.  <span data-ttu-id="78a0d-109">啟用 SQL Server 記錄傳送資料庫。</span><span class="sxs-lookup"><span data-stu-id="78a0d-109">Enable the SQL Server Log Shipping database.</span></span>
    
    4.  <span data-ttu-id="78a0d-110">新增 SQL Server 記錄傳送次要 SQL Server 存放區。</span><span class="sxs-lookup"><span data-stu-id="78a0d-110">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    5.  <span data-ttu-id="78a0d-111">新增次要資料庫的 SQL Server 儲存區鏡像。</span><span class="sxs-lookup"><span data-stu-id="78a0d-111">Add the SQL Server store mirror for the secondary database.</span></span>
    
    6.  <span data-ttu-id="78a0d-112">發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="78a0d-112">Publish the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

