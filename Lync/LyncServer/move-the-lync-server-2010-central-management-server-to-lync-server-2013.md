---
title: 將 Lync Server 2010 中央管理伺服器移至 Lync Server 2013
description: 將 Lync Server 2010 中央管理伺服器移至 Lync Server 2013。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move the Lync Server 2010 Central Management Server to Lync Server 2013
ms:assetid: 30cc98f2-1916-4dbe-99d0-8df5368ed3ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688013(v=OCS.15)
ms:contentKeyID: 49733602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19d53d797375b1eb8fde72f6b999e509b97f85ae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571279"
---
# <a name="move-the-lync-server-2010-central-management-server-to-lync-server-2013"></a><span data-ttu-id="fb639-103">將 Lync Server 2010 中央管理伺服器移至 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb639-103">Move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb639-104">_**主題上次修改日期：** 2013-11-25_</span><span class="sxs-lookup"><span data-stu-id="fb639-104">_**Topic Last Modified:** 2013-11-25_</span></span>

<span data-ttu-id="fb639-105">從 Lync Server 2010 遷移至 Lync Server 2013 之後，您必須將 Lync Server 2010 中央管理伺服器移至 Lync Server 2013 前端伺服器或集區，才能移除舊版 Lync Server 2010 伺服器。</span><span class="sxs-lookup"><span data-stu-id="fb639-105">After migrating from Lync Server 2010 to Lync Server 2013, you need to move the Lync Server 2010 Central Management Server to the Lync Server 2013 Front End Server or pool, before you can remove the legacy Lync Server 2010 server.</span></span>

<span data-ttu-id="fb639-106">中央管理伺服器是單一主/多個複本系統，其中包含中央管理伺服器的前端伺服器會持有資料庫的讀/寫副本。</span><span class="sxs-lookup"><span data-stu-id="fb639-106">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="fb639-107">拓撲中的每一部電腦（包括包含中央管理伺服器的前端伺服器）在安裝及部署期間，RTCLOCAL 會在電腦上安裝的預設) SQL Server (資料庫中的中央管理存放區資料的唯讀副本。</span><span class="sxs-lookup"><span data-stu-id="fb639-107">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="fb639-108">本機資料庫會透過 Lync Server 複本複製器代理程式，以在所有電腦上執行為服務的方式接收復本更新。</span><span class="sxs-lookup"><span data-stu-id="fb639-108">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="fb639-109">中央管理伺服器及本機複本上之實際資料庫的名稱是 XDS，這是由 XDS 及 XDS 檔所組成。</span><span class="sxs-lookup"><span data-stu-id="fb639-109">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="fb639-110">Master 資料庫位置是由 Active Directory 網域服務中 (SCP) 的服務控制點所參照。</span><span class="sxs-lookup"><span data-stu-id="fb639-110">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="fb639-111">所有使用中央管理伺服器來管理及設定 Lync Server 的工具，都使用 SCP 來尋找中央管理存放區。</span><span class="sxs-lookup"><span data-stu-id="fb639-111">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>

<span data-ttu-id="fb639-112">順利移動中央管理伺服器後，應從原始前端伺服器移除中央管理伺服器資料庫。</span><span class="sxs-lookup"><span data-stu-id="fb639-112">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="fb639-113">如需移除中央管理伺服器資料庫的詳細資訊，請參閱 [移除前端集區的 SQL Server 資料庫](remove-the-sql-server-database-for-a-front-end-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="fb639-113">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>

<span data-ttu-id="fb639-114">您可以使用 Lync Server 管理命令介面中的 [Windows PowerShell Cmdlet **Move-CsManagementServer** ，將資料庫從 lync SERVER 2010 sql server 資料庫移至 lync SERVER 2013 sql server 資料庫，然後將 SCP 更新為指向 lync Server 2013 中央管理伺服器位置。</span><span class="sxs-lookup"><span data-stu-id="fb639-114">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Lync Server Management Shell to move the database from the Lync Server 2010 SQL Server database to the Lync Server 2013 SQL Server database, and then update the SCP to point to the Lync Server 2013 Central Management Server location.</span></span>

<div>

## <a name="preparing-lync-server-2013front-end-servers-before-moving-the-central-management-server"></a><span data-ttu-id="fb639-115">在移動中央管理伺服器之前，準備 Lync Server 2013 前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fb639-115">Preparing Lync Server 2013 Front End Servers before moving the Central Management Server</span></span>

<span data-ttu-id="fb639-116">使用本節中的程式，準備 Lync Server 2013 前端伺服器，然後再移動 Lync Server 2010 中央管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="fb639-116">Use the procedures in this section to prepare the Lync Server 2013 Front End Servers before you move the Lync Server 2010 Central Management Server.</span></span>

<div>

## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="fb639-117">準備 Enterprise Edition 前端集區</span><span class="sxs-lookup"><span data-stu-id="fb639-117">To prepare an Enterprise Edition Front End pool</span></span>

1.  <span data-ttu-id="fb639-118">在您想要重新放置中央管理伺服器的 Lync Server 2013 Enterprise Edition 前端集區上，登入安裝了 Lync Server 管理命令介面的電腦做為 **RTCUniversalServerAdmins** 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="fb639-118">On the Lync Server 2013 Enterprise Edition Front End pool where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="fb639-119">您也必須在您要安裝中央管理存放區的資料庫上，具有 SQL Server 資料庫的 sysadmin 使用者權利和許可權。</span><span class="sxs-lookup"><span data-stu-id="fb639-119">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span>

2.  <span data-ttu-id="fb639-120">開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="fb639-120">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="fb639-121">若要在 Lync Server 2013 SQL Server 資料庫中建立新的中央管理存放區，請在 Lync Server 管理命令介面中輸入：</span><span class="sxs-lookup"><span data-stu-id="fb639-121">To create the new Central Management store in the Lync Server 2013 SQL Server database, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  <span data-ttu-id="fb639-122">確認 **Lync Server 前端**服務的狀態為 [已啟動]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fb639-122">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

<div>

## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="fb639-123">準備 Standard Edition 前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fb639-123">To prepare a Standard Edition Front End Server</span></span>

1.  <span data-ttu-id="fb639-124">在您想要重新放置中央管理伺服器的 Lync Server 2013 Standard Edition 前端伺服器上，登入安裝了 Lync Server 管理命令介面的電腦做為 **RTCUniversalServerAdmins** 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="fb639-124">On the Lync Server 2013 Standard Edition Front End Server where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span>

2.  <span data-ttu-id="fb639-125">開啟 Lync Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="fb639-125">Open the Lync Server Deployment Wizard.</span></span>

3.  <span data-ttu-id="fb639-126">在 [Lync Server 部署嚮導] 中，按一下 [ **準備第一個 Standard Edition Server**]。</span><span class="sxs-lookup"><span data-stu-id="fb639-126">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="fb639-127">在 [ **執行命令** ] 頁面上，SQL Server Express 是以中央管理伺服器的方式安裝。</span><span class="sxs-lookup"><span data-stu-id="fb639-127">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="fb639-128">已建立所需的防火牆規則。</span><span class="sxs-lookup"><span data-stu-id="fb639-128">Necessary firewall rules are created.</span></span> <span data-ttu-id="fb639-129">在完成資料庫和必要軟體的安裝時，請按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="fb639-129">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fb639-130">如果命令輸出摘要畫面沒有可見的更新，則初始安裝可能需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="fb639-130">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="fb639-131">這是因為安裝 SQL Server Express。</span><span class="sxs-lookup"><span data-stu-id="fb639-131">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="fb639-132">如果您需要監控資料庫的安裝，請使用 [工作管理員] 來監控安裝程式。</span><span class="sxs-lookup"><span data-stu-id="fb639-132">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

5.  <span data-ttu-id="fb639-133">若要在 Lync Server 2013 Standard Edition 前端伺服器上建立新的中央管理存放區，請在 Lync Server 管理命令介面中輸入：</span><span class="sxs-lookup"><span data-stu-id="fb639-133">To create the new Central Management store on the Lync Server 2013 Standard Edition Front End Server, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  <span data-ttu-id="fb639-134">確認 **Lync Server 前端**服務的狀態為 [已啟動]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fb639-134">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

</div>

<div>

## <a name="to-move-the-lync-server-2010central-management-server-to-lync-server-2013"></a><span data-ttu-id="fb639-135">將 Lync Server 2010 中央管理伺服器移至 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb639-135">To move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

1.  <span data-ttu-id="fb639-136">在將成為中央管理伺服器的 Lync Server 2013 伺服器上，登入安裝了 Lync Server 管理命令介面的電腦做為 **RTCUniversalServerAdmins** 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="fb639-136">On the Lync Server 2013 server that will be the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="fb639-137">您也必須具有 SQL Server 資料庫管理員使用者權限。</span><span class="sxs-lookup"><span data-stu-id="fb639-137">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="fb639-138">開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="fb639-138">Open Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="fb639-139">在 Lync Server 管理命令介面中，輸入：</span><span class="sxs-lookup"><span data-stu-id="fb639-139">In the Lync Server Management Shell, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="fb639-140">若 <CODE>Enable-CsTopology</CODE> 未成功，請解決問題，使命令無法完成，再繼續進行。</span><span class="sxs-lookup"><span data-stu-id="fb639-140">If <CODE>Enable-CsTopology</CODE> is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="fb639-141">如果 <STRONG>Enable-CsTopology</STRONG> 不成功，移動會失敗，而且可能會使拓撲處於沒有中央管理存放區的狀態。</span><span class="sxs-lookup"><span data-stu-id="fb639-141">If <STRONG>Enable-CsTopology</STRONG> is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span>

    
    </div>

4.  <span data-ttu-id="fb639-142">在 lync Server 2013 前端伺服器或前端集區的 Lync Server 管理命令介面中，輸入：</span><span class="sxs-lookup"><span data-stu-id="fb639-142">On the Lync Server 2013 Front End Server or Front End pool, in the Lync Server Management Shell, type:</span></span>
    
        Move-CsManagementServer

5.  <span data-ttu-id="fb639-143">Lync Server 管理命令介面會顯示伺服器、檔案存放區、資料庫儲存區，以及目前狀態和建議狀態的服務連線點。</span><span class="sxs-lookup"><span data-stu-id="fb639-143">Lync Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="fb639-144">請詳細閱讀資訊，並確認預期的來源與目的地是否無誤。</span><span class="sxs-lookup"><span data-stu-id="fb639-144">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="fb639-145">輸入 [Y]\*\*\*\* 繼續或 [N]\*\*\*\* 停止移動。</span><span class="sxs-lookup"><span data-stu-id="fb639-145">Type **Y** to continue, or **N** to stop the move.</span></span>

6.  <span data-ttu-id="fb639-146">檢閱由 **Move-CsManagementServer** 命令所產生的任何警告或錯誤，並加以解決。</span><span class="sxs-lookup"><span data-stu-id="fb639-146">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span>

7.  <span data-ttu-id="fb639-147">在 Lync Server 2013 伺服器上，開啟 [Lync Server 部署嚮導]。</span><span class="sxs-lookup"><span data-stu-id="fb639-147">On the Lync Server 2013 server, open the Lync Server Deployment Wizard.</span></span>

8.  <span data-ttu-id="fb639-148">在 [Lync Server 部署嚮導] 中，按一下 [ **安裝或更新 Lync Server 系統**]，按一下 [ **步驟2：安裝或移除 lync server 元件**]，按 **[下一步]**，查看摘要，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="fb639-148">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

9.  <span data-ttu-id="fb639-149">在 Lync Server 2010 伺服器上，開啟 [Lync Server 部署嚮導]。</span><span class="sxs-lookup"><span data-stu-id="fb639-149">On the Lync Server 2010 server, open the Lync Server Deployment Wizard.</span></span>

10. <span data-ttu-id="fb639-150">在 [Lync Server 部署嚮導] 中，按一下 [ **安裝或更新 Lync Server 系統**]，按一下 [ **步驟2：安裝或移除 lync server 元件**]，按 **[下一步]**，查看摘要，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="fb639-150">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

11. <span data-ttu-id="fb639-151">重新開機 Lync Server 2013 伺服器。</span><span class="sxs-lookup"><span data-stu-id="fb639-151">Reboot the Lync Server 2013 server.</span></span> <span data-ttu-id="fb639-152">因為存取中央管理伺服器資料庫的群組成員資格變更，所以需要這麼做。</span><span class="sxs-lookup"><span data-stu-id="fb639-152">This is required because of a group membership change to access Central Management Server database.</span></span>

12. <span data-ttu-id="fb639-153">若要確認有新中央管理存放區的複寫發生，請在 Lync Server 管理命令介面中輸入：</span><span class="sxs-lookup"><span data-stu-id="fb639-153">To confirm that replication with the new Central Management store is occurring, in the Lync Server Management Shell, type:</span></span>
    
        Get-CsManagementStoreReplicationStatus
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fb639-154">複寫可能要花一些時間來更新所有目前的複本。</span><span class="sxs-lookup"><span data-stu-id="fb639-154">The replication may take some time to update all current replicas.</span></span>

    
    </div>

</div>

<div>

## <a name="to-remove-lync-server-2010central-management-store-files-after-a-move"></a><span data-ttu-id="fb639-155">移動後移除 Lync Server 2010 中央管理存放區檔案</span><span class="sxs-lookup"><span data-stu-id="fb639-155">To remove Lync Server 2010 Central Management store files after a move</span></span>

1.  <span data-ttu-id="fb639-156">在 Lync Server 2010 Server 上：登入安裝了 Lync Server 管理命令介面的電腦做為 **RTCUniversalServerAdmins** 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="fb639-156">On the Lync Server 2010 server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="fb639-157">您也必須具有 SQL Server 資料庫管理員使用者權限。</span><span class="sxs-lookup"><span data-stu-id="fb639-157">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="fb639-158">開啟 Lync Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="fb639-158">Open Lync Server Management Shell</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="fb639-159">請先確認複寫已完成且狀態穩定後，再繼續移除之前的資料庫檔案。</span><span class="sxs-lookup"><span data-stu-id="fb639-159">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="fb639-160">若要在完成複寫之前移除檔案，您會中斷複寫處理常式，並將新移動的中央管理伺服器保持在未知的狀態。</span><span class="sxs-lookup"><span data-stu-id="fb639-160">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="fb639-161">請使用 <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> Cmdlet 來確認複寫狀態。</span><span class="sxs-lookup"><span data-stu-id="fb639-161">Use the cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> to confirm the replication status.</span></span>

    
    </div>

3.  <span data-ttu-id="fb639-162">若要從 Lync Server 2010 中央管理伺服器移除中央管理存放區資料庫檔案，請輸入：</span><span class="sxs-lookup"><span data-stu-id="fb639-162">To remove the Central Management store database files from the Lync Server 2010 Central Management Server, type:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    <span data-ttu-id="fb639-163">例如：</span><span class="sxs-lookup"><span data-stu-id="fb639-163">For example:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    <span data-ttu-id="fb639-164">在 \<FQDN of SQL Server\> 企業版部署中的 Lync server 2010 後端伺服器或 Standard edition Server 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fb639-164">Where the \<FQDN of SQL Server\> is either the Lync Server 2010 Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

