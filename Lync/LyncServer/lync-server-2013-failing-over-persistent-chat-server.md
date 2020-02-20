---
title: Lync Server 2013： 容錯移轉常設聊天室伺服器
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
ms.openlocfilehash: 91c4d5092fc12ac374b57872b7cda2d6f88d9e33
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145842"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-over-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="40487-102">容錯移轉 Lync Server 2013 中的常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="40487-102">Failing over Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40487-103">_**上次修改主題：** 2014年-02-05_</span><span class="sxs-lookup"><span data-stu-id="40487-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="40487-104">Persistent Chat Server 的容錯移轉設計為主要是手動程序。</span><span class="sxs-lookup"><span data-stu-id="40487-104">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>

<span data-ttu-id="40487-105">容錯移轉程序是根據其假設次要資料中心，且是且正在執行，但主要的常設聊天室資料庫所在的 Persistent Chat Server 服務已完全無法使用，包括下列：</span><span class="sxs-lookup"><span data-stu-id="40487-105">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>

  - <span data-ttu-id="40487-106">常設聊天室伺服器主要資料庫與 Persistent Chat Server 鏡像資料庫已關閉。</span><span class="sxs-lookup"><span data-stu-id="40487-106">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>

  - <span data-ttu-id="40487-107">Lync Server 前端伺服器已離線。</span><span class="sxs-lookup"><span data-stu-id="40487-107">Lync Server Front End Server is down.</span></span>

<span data-ttu-id="40487-108">此程序主要有兩個基本步驟：</span><span class="sxs-lookup"><span data-stu-id="40487-108">The procedure is based on two basic steps:</span></span>

  - <span data-ttu-id="40487-109">復原主要常設聊天室資料庫 (mgc)。</span><span class="sxs-lookup"><span data-stu-id="40487-109">Recover the primary Persistent Chat database (mgc).</span></span>

  - <span data-ttu-id="40487-110">建立新主要資料庫的鏡像。</span><span class="sxs-lookup"><span data-stu-id="40487-110">Establish mirroring for the new primary database.</span></span>

<span data-ttu-id="40487-111">常設聊天室規範資料庫 (mgccomp) 不容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="40487-111">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="40487-112">此資料庫的內容僅為暫時性，且會在規範介面卡處理資料時被清除。</span><span class="sxs-lookup"><span data-stu-id="40487-112">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="40487-113">是您的責任，常設聊天室系統管理員身分，正確地管理介面卡輸出，以避免資料遺失。</span><span class="sxs-lookup"><span data-stu-id="40487-113">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>

<div>

## <a name="to-fail-over-persistent-chat-server"></a><span data-ttu-id="40487-114">容錯移轉常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="40487-114">To fail over Persistent Chat Server</span></span>

1.  <span data-ttu-id="40487-115">移除記錄傳送從常設聊天室伺服器備份記錄傳送資料庫。</span><span class="sxs-lookup"><span data-stu-id="40487-115">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
    1.  <span data-ttu-id="40487-116">使用 SQL Server Management Studio，連線至 Persistent Chat Server 備份 mgc 資料庫所在的資料庫執行個體。</span><span class="sxs-lookup"><span data-stu-id="40487-116">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
    2.  <span data-ttu-id="40487-117">開啟 Master 資料庫的查詢視窗。</span><span class="sxs-lookup"><span data-stu-id="40487-117">Open a query window to the master database.</span></span>
    
    3.  <span data-ttu-id="40487-118">使用下列命令移除記錄傳送：</span><span class="sxs-lookup"><span data-stu-id="40487-118">Use the following command to drop log shipping:</span></span>
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  <span data-ttu-id="40487-119">從備份共用複製所有未複製的備份檔案至備份伺服器的複製目的地資料夾。</span><span class="sxs-lookup"><span data-stu-id="40487-119">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>

3.  <span data-ttu-id="40487-120">依序將所有未套用的交易記錄備份套用至次要資料庫。</span><span class="sxs-lookup"><span data-stu-id="40487-120">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="40487-121">如需詳細資訊，請參閱 「 How to： 套用一個交易記錄備份 (TRANSACT-SQL) 」 在https://go.microsoft.com/fwlink/p/?linkid=247428。</span><span class="sxs-lookup"><span data-stu-id="40487-121">For details, see "How to: Apply a Transaction Log Backup (Transact-SQL)" at https://go.microsoft.com/fwlink/p/?linkid=247428.</span></span>

4.  <span data-ttu-id="40487-p103">若要使備份 mgc 資料庫上線。請使用步驟 1b 中開啟的查詢視窗，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="40487-p103">Bring the backup mgc database online. Using the query window that opens in step 1b, do the following:</span></span>
    
    1.  <span data-ttu-id="40487-124">結束所有 mgc 資料庫的連線 (若有連線)：</span><span class="sxs-lookup"><span data-stu-id="40487-124">End all connections to the mgc database, if there are any:</span></span>
        
        1.  <span data-ttu-id="40487-125">**exec sp\_who2**來識別 mgc 資料庫的連線。</span><span class="sxs-lookup"><span data-stu-id="40487-125">**exec sp\_who2** to identify connections to the mgc database.</span></span>
        
        2.  <span data-ttu-id="40487-126">**kill \<spid\>** 結束這些連線。</span><span class="sxs-lookup"><span data-stu-id="40487-126">**kill \<spid\>** to end these connections.</span></span>
    
    2.  <span data-ttu-id="40487-127">使資料庫上線：</span><span class="sxs-lookup"><span data-stu-id="40487-127">Bring the database online:</span></span>
        
        1.  <span data-ttu-id="40487-128">**還原使用復原資料庫 mgc**。</span><span class="sxs-lookup"><span data-stu-id="40487-128">**restore database mgc with recovery**.</span></span>

5.  <span data-ttu-id="40487-129">Lync Server 管理命令介面中使用命令**Set-cspersistentchatstate-身分識別 」 服務： atl-cs-atl-cs-001.litwareinc.com"– PoolState FailedOver**容錯移轉至 mgc 備份資料庫。</span><span class="sxs-lookup"><span data-stu-id="40487-129">In Lync Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" –PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="40487-130">務必確定替代 atl-cs-001.litwareinc.com 的常設聊天室集區的完整的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="40487-130">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="40487-131">現在 mgc 備份資料庫已是主要資料庫。</span><span class="sxs-lookup"><span data-stu-id="40487-131">The mgc backup database now serves as the primary database.</span></span>

6.  <span data-ttu-id="40487-132">在 Lync Server 管理命令介面，使用**Install-csmirrordatabase** cmdlet 來建立備份資料庫中現在做為主要資料庫的高可用性鏡像。</span><span class="sxs-lookup"><span data-stu-id="40487-132">In Lync Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="40487-133">使用備份資料庫執行個體作為主要資料庫，而使用備份鏡像資料庫執行個體作為鏡像執行個體。</span><span class="sxs-lookup"><span data-stu-id="40487-133">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="40487-134">此鏡像並不是安裝程式期間，最初為主要資料庫設定的鏡像。</span><span class="sxs-lookup"><span data-stu-id="40487-134">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span> <span data-ttu-id="40487-135">如需詳細資訊，請參閱 「 使用 Lync Server 管理命令介面 Cmdlet 」 中[的 Lync Server 2013 中的後端伺服器高可用性部署 SQL 鏡像](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)。</span><span class="sxs-lookup"><span data-stu-id="40487-135">For details, see the section "Using Lync Server Management Shell Cmdlets" in [Deploying SQL mirroring for Back End Server high availability in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span></span>

7.  <span data-ttu-id="40487-136">設定作用中 Persistent Chat Server 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="40487-136">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="40487-137">從 Lync Server 命令介面中，使用**Set-cspersistentchatactiveserver** cmdlet 可設定的作用中的伺服器清單。</span><span class="sxs-lookup"><span data-stu-id="40487-137">From the Lync Server Command Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="40487-138">所有作用中的伺服器必須位於與新主要資料庫相同的資料中心，或位於具有低延遲/高頻寬資料庫連線的資料中心內。</span><span class="sxs-lookup"><span data-stu-id="40487-138">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span>

    
    </div>
    
    <span data-ttu-id="40487-139">此時，從常設聊天室伺服器主要資料庫 Persistent Chat Server 的備份資料庫的容錯移轉即可成功完成。</span><span class="sxs-lookup"><span data-stu-id="40487-139">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

