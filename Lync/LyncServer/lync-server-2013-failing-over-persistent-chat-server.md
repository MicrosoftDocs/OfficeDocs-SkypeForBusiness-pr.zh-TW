---
title: Lync Server 2013：容錯移轉持久聊天伺服器
description: Lync Server 2013：容錯移轉 Persistent Chat Server。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over Persistent Chat Server
ms:assetid: 2cd79ffd-fee6-44ce-96cf-b98bf25e2690
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204772(v=OCS.15)
ms:contentKeyID: 48183726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42a3a8f5df203cc23be39a4a691ad713330eab59
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554959"
---
# <a name="failing-over-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="6b95e-103">在 Lync Server 2013 中容錯移轉 Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="6b95e-103">Failing over Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b95e-104">_**主題上次修改日期：** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="6b95e-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="6b95e-105">Persistent Chat Server 的容錯移轉是設計為主要是手動處理常式。</span><span class="sxs-lookup"><span data-stu-id="6b95e-105">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>

<span data-ttu-id="6b95e-106">容錯移轉程式的假設是在次要資料中心啟動並執行，但主要 Persistent Chat 資料庫所在的 Persistent Chat Server 服務完全無法使用，包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="6b95e-106">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>

  - <span data-ttu-id="6b95e-107">Persistent Chat Server 主資料庫和 Persistent Chat Server 鏡像資料庫已停機。</span><span class="sxs-lookup"><span data-stu-id="6b95e-107">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>

  - <span data-ttu-id="6b95e-108">Lync Server 前端伺服器已關機。</span><span class="sxs-lookup"><span data-stu-id="6b95e-108">Lync Server Front End Server is down.</span></span>

<span data-ttu-id="6b95e-109">此程序主要有兩個基本步驟：</span><span class="sxs-lookup"><span data-stu-id="6b95e-109">The procedure is based on two basic steps:</span></span>

  - <span data-ttu-id="6b95e-110">復原主要 Persistent Chat database (mgc) 。</span><span class="sxs-lookup"><span data-stu-id="6b95e-110">Recover the primary Persistent Chat database (mgc).</span></span>

  - <span data-ttu-id="6b95e-111">建立新主要資料庫的鏡像。</span><span class="sxs-lookup"><span data-stu-id="6b95e-111">Establish mirroring for the new primary database.</span></span>

<span data-ttu-id="6b95e-112">Persistent Chat 規範資料庫 (mgccomp) 未進行容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="6b95e-112">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="6b95e-113">此資料庫的內容僅為暫時性，且會在規範介面卡處理資料時被清除。</span><span class="sxs-lookup"><span data-stu-id="6b95e-113">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="6b95e-114">您的責任是 Persistent Chat Administrator，可正確管理配接器輸出以避免資料遺失。</span><span class="sxs-lookup"><span data-stu-id="6b95e-114">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>

<div>

## <a name="to-fail-over-persistent-chat-server"></a><span data-ttu-id="6b95e-115">若要容錯移轉持久聊天伺服器</span><span class="sxs-lookup"><span data-stu-id="6b95e-115">To fail over Persistent Chat Server</span></span>

1.  <span data-ttu-id="6b95e-116">從 Persistent Chat Server 備份記錄傳送資料庫中移除記錄傳送。</span><span class="sxs-lookup"><span data-stu-id="6b95e-116">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
    1.  <span data-ttu-id="6b95e-117">使用 SQL Server Management Studio，連接至 Persistent Chat Server backup mgc 資料庫所在的資料庫實例。</span><span class="sxs-lookup"><span data-stu-id="6b95e-117">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
    2.  <span data-ttu-id="6b95e-118">開啟 Master 資料庫的查詢視窗。</span><span class="sxs-lookup"><span data-stu-id="6b95e-118">Open a query window to the master database.</span></span>
    
    3.  <span data-ttu-id="6b95e-119">使用下列命令移除記錄傳送：</span><span class="sxs-lookup"><span data-stu-id="6b95e-119">Use the following command to drop log shipping:</span></span>
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  <span data-ttu-id="6b95e-120">從備份共用複製所有未複製的備份檔案至備份伺服器的複製目的地資料夾。</span><span class="sxs-lookup"><span data-stu-id="6b95e-120">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>

3.  <span data-ttu-id="6b95e-121">依序將所有未套用的交易記錄備份套用至次要資料庫。</span><span class="sxs-lookup"><span data-stu-id="6b95e-121">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="6b95e-122">如需詳細資訊，請參閱 how to： Apply Transaction Log Backup (Transact-SQL) 」 at https://go.microsoft.com/fwlink/p/?linkid=247428 。</span><span class="sxs-lookup"><span data-stu-id="6b95e-122">For details, see "How to: Apply a Transaction Log Backup (Transact-SQL)" at https://go.microsoft.com/fwlink/p/?linkid=247428.</span></span>

4.  <span data-ttu-id="6b95e-p103">若要使備份 mgc 資料庫上線。請使用步驟 1b 中開啟的查詢視窗，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="6b95e-p103">Bring the backup mgc database online. Using the query window that opens in step 1b, do the following:</span></span>
    
    1.  <span data-ttu-id="6b95e-125">結束所有 mgc 資料庫的連線 (若有連線)：</span><span class="sxs-lookup"><span data-stu-id="6b95e-125">End all connections to the mgc database, if there are any:</span></span>
        
        1.  <span data-ttu-id="6b95e-126">**exec sp \_ who2** ，以識別 mgc 資料庫的連線。</span><span class="sxs-lookup"><span data-stu-id="6b95e-126">**exec sp\_who2** to identify connections to the mgc database.</span></span>
        
        2.  <span data-ttu-id="6b95e-127">\*\*kill \<spid\> \*\*以結束這些連線。</span><span class="sxs-lookup"><span data-stu-id="6b95e-127">**kill \<spid\>** to end these connections.</span></span>
    
    2.  <span data-ttu-id="6b95e-128">使資料庫上線：</span><span class="sxs-lookup"><span data-stu-id="6b95e-128">Bring the database online:</span></span>
        
        1.  <span data-ttu-id="6b95e-129">**restore database mgc with recovery**。</span><span class="sxs-lookup"><span data-stu-id="6b95e-129">**restore database mgc with recovery**.</span></span>

5.  <span data-ttu-id="6b95e-130">在 Lync Server 管理命令介面中，使用命令 **Set-CsPersistentChatState 身分識別 "服務： atl-ws-01" –PoolState FailedOver** 以容錯移轉至 mgc 備份資料庫。</span><span class="sxs-lookup"><span data-stu-id="6b95e-130">In Lync Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" –PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="6b95e-131">請務必將 Persistent Chat 集區的完整功能變數名稱取代為 atl-cs-001.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="6b95e-131">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="6b95e-132">現在 mgc 備份資料庫已是主要資料庫。</span><span class="sxs-lookup"><span data-stu-id="6b95e-132">The mgc backup database now serves as the primary database.</span></span>

6.  <span data-ttu-id="6b95e-133">在 Lync Server 管理命令介面中，使用 **Install-CsMirrorDatabase** Cmdlet 來建立現在用作主資料庫之備份資料庫的高可用性鏡像。</span><span class="sxs-lookup"><span data-stu-id="6b95e-133">In Lync Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="6b95e-134">使用備份資料庫執行個體作為主要資料庫，而使用備份鏡像資料庫執行個體作為鏡像執行個體。</span><span class="sxs-lookup"><span data-stu-id="6b95e-134">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="6b95e-135">此鏡像並不是安裝程式期間，最初為主要資料庫設定的鏡像。</span><span class="sxs-lookup"><span data-stu-id="6b95e-135">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span> <span data-ttu-id="6b95e-136">如需詳細資訊，請參閱在 [Lync server 2013 中針對後端伺服器高可用性部署 SQL 鏡像](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)中的「使用 Lync Server 管理命令介面 Cmdlet」一節。</span><span class="sxs-lookup"><span data-stu-id="6b95e-136">For details, see the section "Using Lync Server Management Shell Cmdlets" in [Deploying SQL mirroring for Back End Server high availability in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span></span>

7.  <span data-ttu-id="6b95e-137">設定 Persistent Chat Server active server。</span><span class="sxs-lookup"><span data-stu-id="6b95e-137">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="6b95e-138">在 Lync Server 命令命令介面中，使用 **Set-CsPersistentChatActiveServer** Cmdlet 來設定作用中的伺服器清單。</span><span class="sxs-lookup"><span data-stu-id="6b95e-138">From the Lync Server Command Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6b95e-139">所有作用中的伺服器必須位於與新主要資料庫相同的資料中心，或位於具有低延遲/高頻寬資料庫連線的資料中心內。</span><span class="sxs-lookup"><span data-stu-id="6b95e-139">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span>

    
    </div>
    
    <span data-ttu-id="6b95e-140">此時，從 Persistent Chat Server 主資料庫到 Persistent Chat Server backup 資料庫的容錯移轉已成功完成。</span><span class="sxs-lookup"><span data-stu-id="6b95e-140">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

