---
title: 將 Lync Server 2010 中央管理伺服器移至 Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move the Lync Server 2010 Central Management Server to Lync Server 2013
ms:assetid: 30cc98f2-1916-4dbe-99d0-8df5368ed3ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688013(v=OCS.15)
ms:contentKeyID: 49733602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abcb361beb82b98cd765b3797b63b22c280fdf70
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974873"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-the-lync-server-2010-central-management-server-to-lync-server-2013"></a><span data-ttu-id="fd285-102">將 Lync Server 2010 中央管理伺服器移至 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd285-102">Move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd285-103">_**主題上次修改日期：** 2013-11-25_</span><span class="sxs-lookup"><span data-stu-id="fd285-103">_**Topic Last Modified:** 2013-11-25_</span></span>

<span data-ttu-id="fd285-104">從 Lync Server 2010 遷移至 Lync Server 2013 之後，您必須將 Lync Server 2010 中央管理伺服器移至 Lync Server 2013 前端伺服器或伺服器池，才能移除舊版 Lync Server 2010 伺服器。</span><span class="sxs-lookup"><span data-stu-id="fd285-104">After migrating from Lync Server 2010 to Lync Server 2013, you need to move the Lync Server 2010 Central Management Server to the Lync Server 2013 Front End Server or pool, before you can remove the legacy Lync Server 2010 server.</span></span>

<span data-ttu-id="fd285-105">[中央管理伺服器] 是單一主要/多重複本系統，其中資料庫的讀/寫複本是由包含中央管理伺服器的前端伺服器所保留。</span><span class="sxs-lookup"><span data-stu-id="fd285-105">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="fd285-106">拓朴中的每個電腦（包括包含中央管理伺服器的前端伺服器）在安裝期間都有在電腦上安裝的 SQL Server 資料庫中的中央管理儲存資料（預設為 RTCLOCAL）的唯讀複本部署.</span><span class="sxs-lookup"><span data-stu-id="fd285-106">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="fd285-107">本機資料庫會按照 Lync Server 複本複製器代理程式（在所有電腦上以服務形式執行）的方式來接收復制副本更新。</span><span class="sxs-lookup"><span data-stu-id="fd285-107">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="fd285-108">中央管理伺服器上的實際資料庫名稱與局部複本是 XDS，這是由 XDS 和 XDS 檔案組成。</span><span class="sxs-lookup"><span data-stu-id="fd285-108">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="fd285-109">主資料庫位置是由 Active Directory 網域服務中的服務控制點（SCP）所參照。</span><span class="sxs-lookup"><span data-stu-id="fd285-109">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="fd285-110">所有使用中央管理伺服器來管理和設定 Lync Server 的工具，都使用 SCP 來尋找中央管理儲存區。</span><span class="sxs-lookup"><span data-stu-id="fd285-110">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>

<span data-ttu-id="fd285-111">成功移動中央管理伺服器之後，您應該從原始前端伺服器移除中央管理伺服器資料庫。</span><span class="sxs-lookup"><span data-stu-id="fd285-111">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="fd285-112">如需有關移除中央管理伺服器資料庫的詳細資訊，請參閱[移除前端池的 SQL Server 資料庫](remove-the-sql-server-database-for-a-front-end-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="fd285-112">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>

<span data-ttu-id="fd285-113">您可以在 Lync Server 管理命令介面中使用 Windows PowerShell Cmdlet **CsManagementServer** ，將資料庫從 lync SERVER 2010 sql server 資料庫移至 lync SERVER 2013 sql server 資料庫，然後更新 SCP 以指向 lync Server 2013 中央管理伺服器位置。</span><span class="sxs-lookup"><span data-stu-id="fd285-113">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Lync Server Management Shell to move the database from the Lync Server 2010 SQL Server database to the Lync Server 2013 SQL Server database, and then update the SCP to point to the Lync Server 2013 Central Management Server location.</span></span>

<div>

## <a name="preparing-lync-server-2013front-end-servers-before-moving-the-central-management-server"></a><span data-ttu-id="fd285-114">在移動中央管理伺服器前準備 Lync Server 2013 前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd285-114">Preparing Lync Server 2013 Front End Servers before moving the Central Management Server</span></span>

<span data-ttu-id="fd285-115">在移動 Lync Server 2010 中央管理伺服器之前，請使用本節中的程式來準備 Lync Server 2013 前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="fd285-115">Use the procedures in this section to prepare the Lync Server 2013 Front End Servers before you move the Lync Server 2010 Central Management Server.</span></span>

<div>

## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="fd285-116">準備企業版前端池</span><span class="sxs-lookup"><span data-stu-id="fd285-116">To prepare an Enterprise Edition Front End pool</span></span>

1.  <span data-ttu-id="fd285-117">在您想要重設中央管理伺服器位置的 Lync Server 2013 企業版前端池上：登入 Lync Server 管理命令介面安裝為**RTCUniversalServerAdmins**群組成員的電腦。</span><span class="sxs-lookup"><span data-stu-id="fd285-117">On the Lync Server 2013 Enterprise Edition Front End pool where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="fd285-118">您也必須在您要安裝中央管理儲存區的資料庫上，同時擁有 SQL Server 資料庫系統管理員的使用者權利和許可權。</span><span class="sxs-lookup"><span data-stu-id="fd285-118">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span>

2.  <span data-ttu-id="fd285-119">開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="fd285-119">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="fd285-120">若要在 Lync Server 2013 SQL Server 資料庫中建立新的中央管理儲存體，請在 Lync Server 管理命令介面中，輸入：</span><span class="sxs-lookup"><span data-stu-id="fd285-120">To create the new Central Management store in the Lync Server 2013 SQL Server database, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  <span data-ttu-id="fd285-121">確認**Lync Server 前端**服務的狀態為 [**已啟動**]。</span><span class="sxs-lookup"><span data-stu-id="fd285-121">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

<div>

## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="fd285-122">準備標準版的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd285-122">To prepare a Standard Edition Front End Server</span></span>

1.  <span data-ttu-id="fd285-123">在您想要重設中央管理伺服器位置的 Lync Server 2013 標準版前端伺服器上：登入 Lync Server 管理命令介面安裝為**RTCUniversalServerAdmins**群組成員的電腦。</span><span class="sxs-lookup"><span data-stu-id="fd285-123">On the Lync Server 2013 Standard Edition Front End Server where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span>

2.  <span data-ttu-id="fd285-124">開啟 [Lync Server 部署] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="fd285-124">Open the Lync Server Deployment Wizard.</span></span>

3.  <span data-ttu-id="fd285-125">在 Lync Server 部署嚮導中，按一下 [**準備第一個標準版 Server**]。</span><span class="sxs-lookup"><span data-stu-id="fd285-125">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="fd285-126">在 [**執行命令**] 頁面上，SQL Server Express 已安裝為中央管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="fd285-126">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="fd285-127">已建立必要的防火牆規則。</span><span class="sxs-lookup"><span data-stu-id="fd285-127">Necessary firewall rules are created.</span></span> <span data-ttu-id="fd285-128">完成資料庫與必備軟體的安裝後，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="fd285-128">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fd285-129">初始安裝可能需要一些時間，且 [命令輸出摘要] 畫面沒有顯示更新。</span><span class="sxs-lookup"><span data-stu-id="fd285-129">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="fd285-130">這是由 SQL Server Express 的安裝所造成。</span><span class="sxs-lookup"><span data-stu-id="fd285-130">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="fd285-131">如果您需要監視資料庫的安裝，請使用 [工作管理員] 來監視設定。</span><span class="sxs-lookup"><span data-stu-id="fd285-131">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

5.  <span data-ttu-id="fd285-132">若要在 Lync Server 2013 標準版前端伺服器上建立新的中央管理存放區，請在 Lync Server 管理命令介面中，鍵入：</span><span class="sxs-lookup"><span data-stu-id="fd285-132">To create the new Central Management store on the Lync Server 2013 Standard Edition Front End Server, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  <span data-ttu-id="fd285-133">確認**Lync Server 前端**服務的狀態為 [**已啟動**]。</span><span class="sxs-lookup"><span data-stu-id="fd285-133">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

</div>

<div>

## <a name="to-move-the-lync-server-2010central-management-server-to-lync-server-2013"></a><span data-ttu-id="fd285-134">若要將 Lync Server 2010 中央管理伺服器移至 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd285-134">To move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

1.  <span data-ttu-id="fd285-135">在將是中央管理伺服器的 Lync Server 2013 伺服器上：登入 Lync Server 管理命令介面安裝為**RTCUniversalServerAdmins**群組成員的電腦。</span><span class="sxs-lookup"><span data-stu-id="fd285-135">On the Lync Server 2013 server that will be the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="fd285-136">您也必須具備 SQL Server 資料庫管理員的使用者權限和許可權。</span><span class="sxs-lookup"><span data-stu-id="fd285-136">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="fd285-137">開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="fd285-137">Open Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="fd285-138">在 Lync Server 管理命令介面中，鍵入：</span><span class="sxs-lookup"><span data-stu-id="fd285-138">In the Lync Server Management Shell, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="fd285-139">如果<CODE>Enable-CsTopology</CODE>未成功，請解決導致命令無法完成的問題，然後再繼續進行。</span><span class="sxs-lookup"><span data-stu-id="fd285-139">If <CODE>Enable-CsTopology</CODE> is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="fd285-140">如果<STRONG>啟用-CsTopology</STRONG>未成功，移動就會失敗，而且可能會讓您的拓撲處於沒有中央管理儲存區的狀態。</span><span class="sxs-lookup"><span data-stu-id="fd285-140">If <STRONG>Enable-CsTopology</STRONG> is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span>

    
    </div>

4.  <span data-ttu-id="fd285-141">在 Lync Server 2013 前端伺服器或頂層端池的 Lync Server 管理命令介面中，鍵入：</span><span class="sxs-lookup"><span data-stu-id="fd285-141">On the Lync Server 2013 Front End Server or Front End pool, in the Lync Server Management Shell, type:</span></span>
    
        Move-CsManagementServer

5.  <span data-ttu-id="fd285-142">Lync Server 管理命令介面會顯示伺服器、檔案儲存區、資料庫儲存區，以及目前狀態與建議狀態的服務連接點。</span><span class="sxs-lookup"><span data-stu-id="fd285-142">Lync Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="fd285-143">仔細閱讀資訊並確認這是您想要的來源和目的地。</span><span class="sxs-lookup"><span data-stu-id="fd285-143">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="fd285-144">鍵入**Y**繼續，或輸入**N**以停止移動。</span><span class="sxs-lookup"><span data-stu-id="fd285-144">Type **Y** to continue, or **N** to stop the move.</span></span>

6.  <span data-ttu-id="fd285-145">查看**移動流覽 CsManagementServer**命令產生的任何警告或錯誤，並加以解決。</span><span class="sxs-lookup"><span data-stu-id="fd285-145">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span>

7.  <span data-ttu-id="fd285-146">在 Lync Server 2013 Server 上，開啟 Lync Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="fd285-146">On the Lync Server 2013 server, open the Lync Server Deployment Wizard.</span></span>

8.  <span data-ttu-id="fd285-147">在 Lync Server 部署嚮導中，按一下 [**安裝或更新 Lync Server System**]，按一下 [**步驟2：設定] 或 [移除 Lync server 元件**]，按一下 **[下一步]**，查看摘要，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="fd285-147">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

9.  <span data-ttu-id="fd285-148">在 Lync Server 2010 Server 上，開啟 Lync Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="fd285-148">On the Lync Server 2010 server, open the Lync Server Deployment Wizard.</span></span>

10. <span data-ttu-id="fd285-149">在 Lync Server 部署嚮導中，按一下 [**安裝或更新 Lync Server System**]，按一下 [**步驟2：設定] 或 [移除 Lync server 元件**]，按一下 **[下一步]**，查看摘要，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="fd285-149">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

11. <span data-ttu-id="fd285-150">重新開機 Lync Server 2013 伺服器。</span><span class="sxs-lookup"><span data-stu-id="fd285-150">Reboot the Lync Server 2013 server.</span></span> <span data-ttu-id="fd285-151">這是必要的，因為群組成員資格變更為 access 中央管理伺服器資料庫。</span><span class="sxs-lookup"><span data-stu-id="fd285-151">This is required because of a group membership change to access Central Management Server database.</span></span>

12. <span data-ttu-id="fd285-152">若要確認正在進行與新中央管理存放區的複製，請在 Lync Server 管理命令介面中輸入：</span><span class="sxs-lookup"><span data-stu-id="fd285-152">To confirm that replication with the new Central Management store is occurring, in the Lync Server Management Shell, type:</span></span>
    
        Get-CsManagementStoreReplicationStatus
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fd285-153">複製可能需要一些時間來更新所有目前的複本。</span><span class="sxs-lookup"><span data-stu-id="fd285-153">The replication may take some time to update all current replicas.</span></span>

    
    </div>

</div>

<div>

## <a name="to-remove-lync-server-2010central-management-store-files-after-a-move"></a><span data-ttu-id="fd285-154">若要在移動後移除 Lync Server 2010 中央管理儲存檔案</span><span class="sxs-lookup"><span data-stu-id="fd285-154">To remove Lync Server 2010 Central Management store files after a move</span></span>

1.  <span data-ttu-id="fd285-155">在 Lync Server 2010 Server 上：登入 Lync Server 管理命令介面安裝為**RTCUniversalServerAdmins**群組成員的電腦。</span><span class="sxs-lookup"><span data-stu-id="fd285-155">On the Lync Server 2010 server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="fd285-156">您也必須具備 SQL Server 資料庫管理員的使用者權限和許可權。</span><span class="sxs-lookup"><span data-stu-id="fd285-156">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="fd285-157">開啟 Lync Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="fd285-157">Open Lync Server Management Shell</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="fd285-158">在複製完成且穩定之前，請勿繼續移除先前的資料庫檔案。</span><span class="sxs-lookup"><span data-stu-id="fd285-158">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="fd285-159">如果您在完成複製之前移除檔案，您將會中斷複製程式，並將新移動的中央管理伺服器保持在未知狀態。</span><span class="sxs-lookup"><span data-stu-id="fd285-159">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="fd285-160">使用 Cmdlet <STRONG>CsManagementStoreReplicationStatus</STRONG>來確認複製狀態。</span><span class="sxs-lookup"><span data-stu-id="fd285-160">Use the cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> to confirm the replication status.</span></span>

    
    </div>

3.  <span data-ttu-id="fd285-161">若要從 Lync Server 2010 中央管理伺服器移除中央管理儲存資料庫檔案，請輸入：</span><span class="sxs-lookup"><span data-stu-id="fd285-161">To remove the Central Management store database files from the Lync Server 2010 Central Management Server, type:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    <span data-ttu-id="fd285-162">例如：</span><span class="sxs-lookup"><span data-stu-id="fd285-162">For example:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    <span data-ttu-id="fd285-163">其中， \<SQL Server\>的 FQDN 是企業版部署中的 Lync Server 2010 後端伺服器，或是標準版 Server 的 fqdn。</span><span class="sxs-lookup"><span data-stu-id="fd285-163">Where the \<FQDN of SQL Server\> is either the Lync Server 2010 Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

