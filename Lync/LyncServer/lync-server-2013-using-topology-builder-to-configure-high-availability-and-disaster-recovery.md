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
ms.openlocfilehash: 75117cd8a88b5ff5f333457033b5af49c5464f53
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42116726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="1581c-102">使用拓撲產生器 Lync Server 2013 中設定高可用性與災害復原</span><span class="sxs-lookup"><span data-stu-id="1581c-102">Using Topology Builder to configure high availability and disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1581c-103">_**主題上次修改日期：** 2012年-10-06_</span><span class="sxs-lookup"><span data-stu-id="1581c-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="1581c-104">執行下列步驟在拓撲產生器來設定 for Persistent Chat Server 的高可用性和災害復原。</span><span class="sxs-lookup"><span data-stu-id="1581c-104">Perform the following steps within Topology Builder to configure high availability and disaster recovery for Persistent Chat Server.</span></span>

1.  <span data-ttu-id="1581c-105">新增鏡像資料庫與記錄傳送次要資料庫 SQL Server 儲存區。</span><span class="sxs-lookup"><span data-stu-id="1581c-105">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>

2.  <span data-ttu-id="1581c-106">編輯 Persistent Chat Server 服務屬性：</span><span class="sxs-lookup"><span data-stu-id="1581c-106">Edit the Persistent Chat Server service properties to:</span></span>
    
    1.  <span data-ttu-id="1581c-107">啟用主要資料庫的鏡像。</span><span class="sxs-lookup"><span data-stu-id="1581c-107">Enable mirroring for the primary database.</span></span>
    
    2.  <span data-ttu-id="1581c-108">新增主要鏡像 SQL Server 儲存區。</span><span class="sxs-lookup"><span data-stu-id="1581c-108">Add the primary mirror SQL Server store.</span></span>
    
    3.  <span data-ttu-id="1581c-109">啟用 SQL Server 記錄傳送資料庫。</span><span class="sxs-lookup"><span data-stu-id="1581c-109">Enable the SQL Server Log Shipping database.</span></span>
    
    4.  <span data-ttu-id="1581c-110">新增 SQL Server 記錄傳送次要 SQL Server 存放區。</span><span class="sxs-lookup"><span data-stu-id="1581c-110">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    5.  <span data-ttu-id="1581c-111">新增次要資料庫的 SQL Server 儲存區鏡像。</span><span class="sxs-lookup"><span data-stu-id="1581c-111">Add the SQL Server store mirror for the secondary database.</span></span>
    
    6.  <span data-ttu-id="1581c-112">發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="1581c-112">Publish the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

