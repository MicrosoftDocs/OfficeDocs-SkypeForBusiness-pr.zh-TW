---
title: Lync Server 2013：容錯移轉常設聊天室伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over Persistent Chat Server
ms:assetid: 2cd79ffd-fee6-44ce-96cf-b98bf25e2690
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204772(v=OCS.15)
ms:contentKeyID: 48183726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 021b34cafd91397cc36da1dbc22f91b8665aea96
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976851"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="a5a13-102">在 Lync Server 2013 中容錯移轉常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="a5a13-102">Failing over Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5a13-103">_**主題上次修改日期：** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="a5a13-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="a5a13-104">持續性聊天伺服器的容錯移轉主要是手動程式設計。</span><span class="sxs-lookup"><span data-stu-id="a5a13-104">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>

<span data-ttu-id="a5a13-105">容錯移轉程式的假設是次要資料中心已啟動且正在執行，但主要持久聊天資料庫所在的持久聊天伺服器服務完全無法使用，包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="a5a13-105">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>

  - <span data-ttu-id="a5a13-106">持續聊天伺服器主資料庫和持續聊天伺服器鏡像資料庫已關閉。</span><span class="sxs-lookup"><span data-stu-id="a5a13-106">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>

  - <span data-ttu-id="a5a13-107">Lync Server 前端伺服器已關閉。</span><span class="sxs-lookup"><span data-stu-id="a5a13-107">Lync Server Front End Server is down.</span></span>

<span data-ttu-id="a5a13-108">此程式是以兩個基本步驟為基礎：</span><span class="sxs-lookup"><span data-stu-id="a5a13-108">The procedure is based on two basic steps:</span></span>

  - <span data-ttu-id="a5a13-109">復原主要持久聊天資料庫（mgc）。</span><span class="sxs-lookup"><span data-stu-id="a5a13-109">Recover the primary Persistent Chat database (mgc).</span></span>

  - <span data-ttu-id="a5a13-110">為新的主資料庫建立鏡像。</span><span class="sxs-lookup"><span data-stu-id="a5a13-110">Establish mirroring for the new primary database.</span></span>

<span data-ttu-id="a5a13-111">永久聊天規範資料庫（mgccomp）未進行容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="a5a13-111">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="a5a13-112">此資料庫的內容是暫時性的，而且會在合規性配接器處理資料時清除。</span><span class="sxs-lookup"><span data-stu-id="a5a13-112">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="a5a13-113">您的責任是永久聊天管理員，正確管理配接器輸出以避免資料遺失。</span><span class="sxs-lookup"><span data-stu-id="a5a13-113">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>

<div>

## <a name="to-fail-over-persistent-chat-server"></a><span data-ttu-id="a5a13-114">若要容錯移轉持久聊天伺服器</span><span class="sxs-lookup"><span data-stu-id="a5a13-114">To fail over Persistent Chat Server</span></span>

1.  <span data-ttu-id="a5a13-115">從持續聊天伺服器備份記錄傳送資料庫中移除記錄傳送。</span><span class="sxs-lookup"><span data-stu-id="a5a13-115">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
    1.  <span data-ttu-id="a5a13-116">使用 SQL Server Management Studio，連線到持久聊天伺服器備份 mgc 資料庫所在的資料庫實例。</span><span class="sxs-lookup"><span data-stu-id="a5a13-116">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
    2.  <span data-ttu-id="a5a13-117">開啟 [查詢] 視窗至 [主資料庫]。</span><span class="sxs-lookup"><span data-stu-id="a5a13-117">Open a query window to the master database.</span></span>
    
    3.  <span data-ttu-id="a5a13-118">使用下列命令來刪除記錄傳送：</span><span class="sxs-lookup"><span data-stu-id="a5a13-118">Use the following command to drop log shipping:</span></span>
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  <span data-ttu-id="a5a13-119">將備份共用中的任何 uncopied 備份檔案複製到備份伺服器的 [複製目的地] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="a5a13-119">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>

3.  <span data-ttu-id="a5a13-120">將任何未套用的事務記錄備份以順序套用到次要資料庫。</span><span class="sxs-lookup"><span data-stu-id="a5a13-120">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="a5a13-121">如需詳細資訊，請參閱「如何：套用事務記錄備份（Transact-sql）」 http://go.microsoft.com/fwlink/p/?linkid=247428。</span><span class="sxs-lookup"><span data-stu-id="a5a13-121">For details, see "How to: Apply a Transaction Log Backup (Transact-SQL)" at http://go.microsoft.com/fwlink/p/?linkid=247428.</span></span>

4.  <span data-ttu-id="a5a13-122">讓備份 mgc 資料庫在線上。</span><span class="sxs-lookup"><span data-stu-id="a5a13-122">Bring the backup mgc database online.</span></span> <span data-ttu-id="a5a13-123">使用在步驟1b 中開啟的 [查詢] 視窗，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="a5a13-123">Using the query window that opens in step 1b, do the following:</span></span>
    
    1.  <span data-ttu-id="a5a13-124">結束所有 mgc 資料庫連線（如果有的話）：</span><span class="sxs-lookup"><span data-stu-id="a5a13-124">End all connections to the mgc database, if there are any:</span></span>
        
        1.  <span data-ttu-id="a5a13-125">**exec sp\_who2**可識別 mgc 資料庫的連線。</span><span class="sxs-lookup"><span data-stu-id="a5a13-125">**exec sp\_who2** to identify connections to the mgc database.</span></span>
        
        2.  <span data-ttu-id="a5a13-126">\*\*kill \<spid\> \*\*以結束這些連線。</span><span class="sxs-lookup"><span data-stu-id="a5a13-126">**kill \<spid\>** to end these connections.</span></span>
    
    2.  <span data-ttu-id="a5a13-127">讓資料庫處於線上狀態：</span><span class="sxs-lookup"><span data-stu-id="a5a13-127">Bring the database online:</span></span>
        
        1.  <span data-ttu-id="a5a13-128">**使用恢復來還原資料庫 mgc**。</span><span class="sxs-lookup"><span data-stu-id="a5a13-128">**restore database mgc with recovery**.</span></span>

5.  <span data-ttu-id="a5a13-129">在 Lync Server 管理命令介面中，使用命令**CsPersistentChatState 身分識別 "服務： atl-cs-001.litwareinc.com" – PoolState FailedOver**容錯移轉至 mgc 備份資料庫。</span><span class="sxs-lookup"><span data-stu-id="a5a13-129">In Lync Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" –PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="a5a13-130">請務必以 atl-cs-001.litwareinc.com 的持久聊天池來取代完整的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="a5a13-130">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="a5a13-131">Mgc 備份資料庫現在是作為主要資料庫。</span><span class="sxs-lookup"><span data-stu-id="a5a13-131">The mgc backup database now serves as the primary database.</span></span>

6.  <span data-ttu-id="a5a13-132">在 Lync Server 管理命令介面中，請使用**CsMirrorDatabase** Cmdlet 來為現在作為主要資料庫的備份資料庫建立高可用性鏡像。</span><span class="sxs-lookup"><span data-stu-id="a5a13-132">In Lync Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="a5a13-133">使用備份資料庫實例作為主要資料庫，將備份鏡像資料庫實例做為鏡像實例。</span><span class="sxs-lookup"><span data-stu-id="a5a13-133">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="a5a13-134">這與在安裝期間最初為主要資料庫設定的同一個鏡像。</span><span class="sxs-lookup"><span data-stu-id="a5a13-134">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span> <span data-ttu-id="a5a13-135">如需詳細資訊，請參閱在 Lync Server 2013 中的 [使用 Lync Server Management Shell Cmdlet][部署 SQL 鏡像以取得後端伺服器高可用性](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)的章節。</span><span class="sxs-lookup"><span data-stu-id="a5a13-135">For details, see the section "Using Lync Server Management Shell Cmdlets" in [Deploying SQL mirroring for Back End Server high availability in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span></span>

7.  <span data-ttu-id="a5a13-136">設定持續聊天伺服器的使用中伺服器。</span><span class="sxs-lookup"><span data-stu-id="a5a13-136">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="a5a13-137">從 Lync Server 命令 Shell，使用**CsPersistentChatActiveServer** Cmdlet 來設定作用中伺服器的清單。</span><span class="sxs-lookup"><span data-stu-id="a5a13-137">From the Lync Server Command Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a5a13-138">所有的作用中伺服器都必須位於與新的主資料庫相同的資料中心內，或是在具有低延遲/高頻寬連接的資料中心中。</span><span class="sxs-lookup"><span data-stu-id="a5a13-138">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span>

    
    </div>
    
    <span data-ttu-id="a5a13-139">此時，來自持久聊天伺服器主要資料庫的容錯移轉至持續聊天伺服器備份資料庫成功完成。</span><span class="sxs-lookup"><span data-stu-id="a5a13-139">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

