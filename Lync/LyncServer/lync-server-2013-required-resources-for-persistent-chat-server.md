---
title: Lync Server 2013：常設聊天室伺服器的必要資源
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Required resources
ms:assetid: bce50b95-f3c8-407e-963a-d8896ee77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205211(v=OCS.15)
ms:contentKeyID: 48185255
ms.date: 02/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac51432de0a6ca261e42f77d64ef1aa1a615cb6d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982458"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="required-resources-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="e5b52-102">Lync Server 2013 中的常設聊天室伺服器的必要資源</span><span class="sxs-lookup"><span data-stu-id="e5b52-102">Required resources for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5b52-103">_**主題上次修改日期：** 2016-02-05_</span><span class="sxs-lookup"><span data-stu-id="e5b52-103">_**Topic Last Modified:** 2016-02-05_</span></span>

<span data-ttu-id="e5b52-104">持續性聊天伺服器的高可用性和災難復原需要額外的資源，超出完整操作所需的資源。</span><span class="sxs-lookup"><span data-stu-id="e5b52-104">High availability and disaster recovery for Persistent Chat Server requires additional resources beyond what is typically needed for full operation.</span></span> <span data-ttu-id="e5b52-105">在針對高可用性和災害復原設定持續聊天伺服器前，請確定您有下列資源，以及標準持續聊天伺服器作業所需的內容。</span><span class="sxs-lookup"><span data-stu-id="e5b52-105">Before configuring Persistent Chat Server for high availability and disaster recovery, ensure that you have the following resources in addition to what is required for standard Persistent Chat Server operation.</span></span> <span data-ttu-id="e5b52-106">如需其他配置資訊，請參閱[在 Lync server 2013 中設定持久聊天伺服器](lync-server-2013-configuring-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="e5b52-106">For additional configuration information, see [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).</span></span>

  - <span data-ttu-id="e5b52-107">一個專用的資料庫實例位於與持久性聊天伺服器服務的主前端相同的物理資料中心。</span><span class="sxs-lookup"><span data-stu-id="e5b52-107">One dedicated database instance located in the same physical data center in which the home front end of the Persistent Chat Server service is located.</span></span> <span data-ttu-id="e5b52-108">此資料庫將充當主要持久聊天資料庫的 SQL Server mirror。</span><span class="sxs-lookup"><span data-stu-id="e5b52-108">This database will serve as the SQL Server mirror for the primary Persistent Chat database.</span></span> <span data-ttu-id="e5b52-109">或者，如果您想要將自動容錯移轉到鏡像資料庫，請指定額外的 SQL Server 作為鏡像見證。</span><span class="sxs-lookup"><span data-stu-id="e5b52-109">Optionally, designate an additional SQL Server to serve as the mirroring witness if you want an automated failover to the mirror database.</span></span>

  - <span data-ttu-id="e5b52-110">一個位於另一個物理資料中心的專用資料庫實例。</span><span class="sxs-lookup"><span data-stu-id="e5b52-110">One dedicated database instance located in the other physical data center.</span></span> <span data-ttu-id="e5b52-111">此資料庫將充當主要資料中心中資料庫的 SQL Server 記錄傳送次要資料庫。</span><span class="sxs-lookup"><span data-stu-id="e5b52-111">This database will serve as the SQL Server Log Shipping secondary database for the database in the primary data center.</span></span>

  - <span data-ttu-id="e5b52-112">要作為次要資料庫之 SQL Server mirror 的一個專用資料庫實例。</span><span class="sxs-lookup"><span data-stu-id="e5b52-112">One dedicated database instance to serve as the SQL Server mirror for the secondary database.</span></span> <span data-ttu-id="e5b52-113">或者，您也可以將其他 SQL Server 指派給伺服器做為鏡像見證。</span><span class="sxs-lookup"><span data-stu-id="e5b52-113">Optionally, designate an additional SQL Server to server as the mirroring witness.</span></span> <span data-ttu-id="e5b52-114">這兩者必須位於與次要資料庫相同的物理資料中心。</span><span class="sxs-lookup"><span data-stu-id="e5b52-114">Both of these must be located in the same physical data center as the secondary database.</span></span>

  - <span data-ttu-id="e5b52-115">如果已啟用持續聊天伺服器合規性，則需要額外的三個專用資料庫實例。</span><span class="sxs-lookup"><span data-stu-id="e5b52-115">If Persistent Chat Server compliance is enabled, an additional three dedicated database instances are required.</span></span> <span data-ttu-id="e5b52-116">其分配與先前在持續聊天資料庫中所述的相同。</span><span class="sxs-lookup"><span data-stu-id="e5b52-116">Their distribution is the same as those previously outlined for the Persistent Chat database.</span></span> <span data-ttu-id="e5b52-117">雖然合規性資料庫可以與持久聊天資料庫共用相同的 SQL Server 實例，但我們建議獨立的實例提供高可用性和災害復原。</span><span class="sxs-lookup"><span data-stu-id="e5b52-117">While it is possible for the compliance database to share the same SQL Server instance as the Persistent Chat database, we recommend standalone instances for high availability and disaster recovery.</span></span>

  - <span data-ttu-id="e5b52-118">必須針對 SQL Server 記錄傳送事務記錄記錄建立並指派檔案共用。</span><span class="sxs-lookup"><span data-stu-id="e5b52-118">A file share must be created and designated for the SQL Server Log Shipping transaction logs.</span></span> <span data-ttu-id="e5b52-119">在兩個資料中心中的所有 SQL 伺服器都執行持續聊天資料庫，必須擁有此檔案共用的讀/寫存取權。</span><span class="sxs-lookup"><span data-stu-id="e5b52-119">All SQL Servers in both data centers that run Persistent Chat databases must have read/write access to this file share.</span></span> <span data-ttu-id="e5b52-120">此共用沒有定義為 [您的顯示格式] 角色的一部分。</span><span class="sxs-lookup"><span data-stu-id="e5b52-120">This share is not defined as part of a FileStore role.</span></span>

  - <span data-ttu-id="e5b52-121">次要資料庫伺服器上的檔案共用，可作為從主要伺服器檔案共用複製的 SQL Server 事務日誌的目的地資料夾。</span><span class="sxs-lookup"><span data-stu-id="e5b52-121">A file share on the secondary database server to serve as the destination folder for the SQL Server transaction logs that are copied from the primary server file share.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e5b52-122">持續聊天伺服器池中的作用中持續聊天伺服器，必須位於與拓撲中定義的下一個躍點 Lync 池相同的時區中。</span><span class="sxs-lookup"><span data-stu-id="e5b52-122">Active Persistent Chat servers in a Persistent Chat Server pool MUST reside in the same time zone as the next hop Lync Pool defined in the topology.</span></span>



</div>

<span data-ttu-id="e5b52-123">下列圖表提供在兩個不同延伸池拓撲中如何設定整個持續聊天伺服器池的範例：</span><span class="sxs-lookup"><span data-stu-id="e5b52-123">The following figures provide examples about how the entire Persistent Chat Server pool can be configured in the two different stretched pool topologies:</span></span>

  - <span data-ttu-id="e5b52-124">當資料中心位於具有高頻寬/低延遲的地理位置時，延伸持久聊天伺服器池。</span><span class="sxs-lookup"><span data-stu-id="e5b52-124">Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.</span></span>

  - <span data-ttu-id="e5b52-125">當資料中心位於具有低頻寬/高延遲的地理位置時，延伸持久聊天伺服器池。</span><span class="sxs-lookup"><span data-stu-id="e5b52-125">Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.</span></span>

<span data-ttu-id="e5b52-126">下圖顯示延伸持續聊天伺服器池拓撲，其中資料中心是具有高頻寬/低延遲的地理位置。</span><span class="sxs-lookup"><span data-stu-id="e5b52-126">The following figure shows a stretched Persistent Chat Server pool topology where data centers are geo-located with high bandwidth/low latency.</span></span>

<span data-ttu-id="e5b52-127">**當資料中心位於具有高頻寬/低延遲的地理位置時，延伸持久聊天伺服器池。**</span><span class="sxs-lookup"><span data-stu-id="e5b52-127">**Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.**</span></span>

<span data-ttu-id="e5b52-128">![持續聊天伺服器池 HBW 設定考試](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "持續聊天伺服器池 HBW 配置測試")</span><span class="sxs-lookup"><span data-stu-id="e5b52-128">![Persistent Chat Server pool HBW configuration exam](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Persistent Chat Server pool HBW configuration exam")</span></span>

<span data-ttu-id="e5b52-129">下圖顯示延伸的持久聊天伺服器池拓撲，其中資料中心是具有低頻寬/高延遲的地理位置。</span><span class="sxs-lookup"><span data-stu-id="e5b52-129">The following figure shows a stretched Persistent Chat Server pool topology where data centers are geo-located with low bandwidth/high latency.</span></span>

<span data-ttu-id="e5b52-130">**當資料中心位於具有低頻寬/高延遲的地理位置時，延伸持久聊天伺服器池。**</span><span class="sxs-lookup"><span data-stu-id="e5b52-130">**Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.**</span></span>

<span data-ttu-id="e5b52-131">![持續聊天伺服器池 LBW 設定考試](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "持續聊天伺服器池 LBW 配置測試")</span><span class="sxs-lookup"><span data-stu-id="e5b52-131">![Persistent Chat Server pool LBW configuration exam](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Persistent Chat Server pool LBW configuration exam")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

