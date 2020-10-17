---
title: 使用拓撲產生器來設定高可用性和嚴重損壞修復
description: 使用拓撲產生器來設定高可用性和嚴重損壞修復。
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
ms.openlocfilehash: 04764a58ac3ae1bbe0df97aadeabb03158ce8100
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547319"
---
# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="89abf-103">在 Lync Server 2013 中使用拓撲產生器來設定高可用性和嚴重損壞修復</span><span class="sxs-lookup"><span data-stu-id="89abf-103">Using Topology Builder to configure high availability and disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89abf-104">_**主題上次修改日期：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="89abf-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="89abf-105">在拓撲產生器中執行下列步驟，以設定 Persistent Chat Server 的高可用性和嚴重損壞修復。</span><span class="sxs-lookup"><span data-stu-id="89abf-105">Perform the following steps within Topology Builder to configure high availability and disaster recovery for Persistent Chat Server.</span></span>

1.  <span data-ttu-id="89abf-106">新增鏡像資料庫和記錄傳送次要資料庫 SQL Server 儲存區。</span><span class="sxs-lookup"><span data-stu-id="89abf-106">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>

2.  <span data-ttu-id="89abf-107">編輯 Persistent Chat Server 服務屬性，使其：</span><span class="sxs-lookup"><span data-stu-id="89abf-107">Edit the Persistent Chat Server service properties to:</span></span>
    
    1.  <span data-ttu-id="89abf-108">啟用主資料庫的鏡像。</span><span class="sxs-lookup"><span data-stu-id="89abf-108">Enable mirroring for the primary database.</span></span>
    
    2.  <span data-ttu-id="89abf-109">新增主要鏡像 SQL Server 儲存區。</span><span class="sxs-lookup"><span data-stu-id="89abf-109">Add the primary mirror SQL Server store.</span></span>
    
    3.  <span data-ttu-id="89abf-110">啟用 SQL Server 記錄傳送資料庫。</span><span class="sxs-lookup"><span data-stu-id="89abf-110">Enable the SQL Server Log Shipping database.</span></span>
    
    4.  <span data-ttu-id="89abf-111">新增 SQL Server 記錄傳送次要 SQL Server 儲存區。</span><span class="sxs-lookup"><span data-stu-id="89abf-111">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    5.  <span data-ttu-id="89abf-112">新增次要資料庫的 SQL Server 儲存區鏡像。</span><span class="sxs-lookup"><span data-stu-id="89abf-112">Add the SQL Server store mirror for the secondary database.</span></span>
    
    6.  <span data-ttu-id="89abf-113">發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="89abf-113">Publish the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

