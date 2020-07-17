---
title: 移動中央管理伺服器
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 在遷移至商務用 Skype Server 2019 之後，您必須將中央管理伺服器移至商務用 Skype Server 2019 前端伺服器或集區，才能移除舊版伺服器。
ms.openlocfilehash: b5412e1b538627c50c3f2a98a5b68c64364f00a9
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752465"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="1b9db-103">將舊版中央管理伺服器移至商務用 Skype Server 2019</span><span class="sxs-lookup"><span data-stu-id="1b9db-103">Move the legacy Central Management Server to Skype for Business Server 2019</span></span>

<span data-ttu-id="1b9db-104">在遷移至商務用 Skype Server 2019 後，在您可以移除舊版伺服器之前，您必須將中央管理伺服器移至商務用 Skype Server 2019 前端伺服器或集區。</span><span class="sxs-lookup"><span data-stu-id="1b9db-104">After migrating to Skype for Business Server 2019, and before you can remove the legacy server, you need to move the Central Management Server to the Skype for Business Server 2019 Front End Server or pool.</span></span> 
  
<span data-ttu-id="1b9db-105">中央管理伺服器是單一主/多個複本系統，其中包含中央管理伺服器的前端伺服器會持有資料庫的讀/寫副本。</span><span class="sxs-lookup"><span data-stu-id="1b9db-105">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="1b9db-106">拓撲中的每一部電腦（包括包含中央管理伺服器的前端伺服器）在安裝和部署期間，都有安裝于電腦上的 SQL Server 資料庫（名為 RTCLOCAL）中的中央管理存放區資料的唯讀副本。</span><span class="sxs-lookup"><span data-stu-id="1b9db-106">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="1b9db-107">本機資料庫會透過商務用 Skype 伺服器複本複製器代理程式（在所有電腦上以服務方式執行）來接收復本更新。</span><span class="sxs-lookup"><span data-stu-id="1b9db-107">The local database receives replica updates by way of the Skype for Business Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="1b9db-108">中央管理伺服器及本機複本上之實際資料庫的名稱是 XDS，這是由 XDS 及 XDS 檔所組成。</span><span class="sxs-lookup"><span data-stu-id="1b9db-108">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="1b9db-109">Master 資料庫位置是由 Active Directory 網域服務中的服務控制點（SCP）所參照。</span><span class="sxs-lookup"><span data-stu-id="1b9db-109">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="1b9db-110">所有使用中央管理伺服器來管理及設定商務用 Skype Server 的工具，都可以使用 SCP 來尋找中央管理存放區。</span><span class="sxs-lookup"><span data-stu-id="1b9db-110">All tools that use the Central Management Server to manage and configure Skype for Business Server use the SCP to locate the Central Management store.</span></span>
  
<span data-ttu-id="1b9db-111">順利移動中央管理伺服器後，應從原始前端伺服器移除中央管理伺服器資料庫。</span><span class="sxs-lookup"><span data-stu-id="1b9db-111">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="1b9db-112">如需移除中央管理伺服器資料庫的詳細資訊，請參閱[移除前端集區的 SQL Server 資料庫](remove-the-sql-server-database-for-a-front-end-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="1b9db-112">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>
  
<span data-ttu-id="1b9db-113">您可以使用商務用 Skype Server 管理命令介面中的 Windows PowerShell Cmdlet **Move-CsManagementServer** ，將資料庫從舊版安裝 SQL server 資料庫移至商務用 skype SERVER 2019 SQL server 資料庫，然後將 SCP 更新為指向商務用 skype Server 2019 中央管理伺服器位置。</span><span class="sxs-lookup"><span data-stu-id="1b9db-113">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Skype for Business Server Management Shell to move the database from the legacy install SQL Server database to the Skype for Business Server 2019 SQL Server database, and then update the SCP to point to the Skype for Business Server 2019 Central Management Server location.</span></span> 
  
<span data-ttu-id="1b9db-114">在移動中央管理伺服器之前，請使用本節中的程式來準備商務用 Skype Server 2019 前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="1b9db-114">Use the procedures in this section to prepare the Skype for Business Server 2019 Front End Servers before you move the Central Management Server.</span></span>
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="1b9db-115">準備 Enterprise Edition 前端集區</span><span class="sxs-lookup"><span data-stu-id="1b9db-115">To prepare an Enterprise Edition Front End pool</span></span>

1. <span data-ttu-id="1b9db-116">在您想要重新放置中央管理伺服器的商務用 Skype Server 2019 Enterprise Edition 前端集區上，登入到安裝商務用 Skype Server 管理命令介面的電腦做為**RTCUniversalServerAdmins**群組的成員。</span><span class="sxs-lookup"><span data-stu-id="1b9db-116">On the Skype for Business Server 2019 Enterprise Edition Front End pool where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="1b9db-117">您也必須在您要安裝中央管理存放區的資料庫上，具有 SQL Server 資料庫的 sysadmin 使用者權利和許可權。</span><span class="sxs-lookup"><span data-stu-id="1b9db-117">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span> 
    
2. <span data-ttu-id="1b9db-118">開啟商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="1b9db-118">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="1b9db-119">若要在商務用 Skype Server 2019 SQL Server 資料庫中建立新的中央管理存放區，請在商務用 Skype Server 管理命令介面中輸入：</span><span class="sxs-lookup"><span data-stu-id="1b9db-119">To create the new Central Management store in the Skype for Business Server 2019 SQL Server database, in the Skype for Business Server Management Shell, type:</span></span>
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. <span data-ttu-id="1b9db-120">確認**已啟動\*\*\*\*商務用 Skype Server 前端**服務的狀態。</span><span class="sxs-lookup"><span data-stu-id="1b9db-120">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="1b9db-121">準備 Standard Edition 前端伺服器</span><span class="sxs-lookup"><span data-stu-id="1b9db-121">To prepare a Standard Edition Front End Server</span></span>

1. <span data-ttu-id="1b9db-122">在您想要重新放置中央管理伺服器的商務用 Skype Server 2019 Standard Edition 前端伺服器上，登入已安裝商務用 Skype Server 管理命令介面的電腦做為**RTCUniversalServerAdmins**群組的成員。</span><span class="sxs-lookup"><span data-stu-id="1b9db-122">On the Skype for Business Server 2019 Standard Edition Front End Server where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> 
    
2. <span data-ttu-id="1b9db-123">開啟商務用 Skype 伺服器部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="1b9db-123">Open the Skype for Business Server Deployment Wizard.</span></span>
    
3. <span data-ttu-id="1b9db-124">在 [商務用 Skype 伺服器部署嚮導] 中，按一下 [**準備第一個 Standard Edition Server**]。</span><span class="sxs-lookup"><span data-stu-id="1b9db-124">In the Skype for Business Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>
    
4. <span data-ttu-id="1b9db-125">在 [**執行命令**] 頁面上，SQL Server Express 是以中央管理伺服器的方式安裝。</span><span class="sxs-lookup"><span data-stu-id="1b9db-125">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="1b9db-126">已建立所需的防火牆規則。</span><span class="sxs-lookup"><span data-stu-id="1b9db-126">Necessary firewall rules are created.</span></span> <span data-ttu-id="1b9db-127">在完成資料庫和必要軟體的安裝時，請按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="1b9db-127">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1b9db-128">如果命令輸出摘要畫面沒有可見的更新，則初始安裝可能需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="1b9db-128">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="1b9db-129">這是因為安裝 SQL Server Express。</span><span class="sxs-lookup"><span data-stu-id="1b9db-129">This is due to the installation of SQL Server Express.</span></span> <span data-ttu-id="1b9db-130">如果您需要監控資料庫的安裝，請使用 [工作管理員] 來監控安裝程式。</span><span class="sxs-lookup"><span data-stu-id="1b9db-130">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span> 
  
5. <span data-ttu-id="1b9db-131">若要在商務用 Skype Server 2019 Standard Edition 前端伺服器上建立新的中央管理存放區，請在商務用 Skype Server 管理命令介面中輸入：</span><span class="sxs-lookup"><span data-stu-id="1b9db-131">To create the new Central Management store on the Skype for Business Server 2019 Standard Edition Front End Server, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. <span data-ttu-id="1b9db-132">確認**已啟動\*\*\*\*商務用 Skype Server 前端**服務的狀態。</span><span class="sxs-lookup"><span data-stu-id="1b9db-132">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="1b9db-133">將舊版安裝中央管理伺服器移至商務用 Skype Server 2019</span><span class="sxs-lookup"><span data-stu-id="1b9db-133">To move the legacy installs Central Management Server to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="1b9db-134">在將成為中央管理伺服器的商務用 Skype Server 2019 伺服器上，登入已安裝商務用 Skype Server 管理命令介面的電腦做為**RTCUniversalServerAdmins**群組的成員。</span><span class="sxs-lookup"><span data-stu-id="1b9db-134">On the Skype for Business Server 2019 server that will be the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="1b9db-135">您也必須具有 SQL Server 資料庫管理員使用者權限。</span><span class="sxs-lookup"><span data-stu-id="1b9db-135">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="1b9db-136">開啟商務用 Skype Server 管理命令介面（以系統管理員身分執行）。</span><span class="sxs-lookup"><span data-stu-id="1b9db-136">Open Skype for Business Server Management Shell (run as administrator).</span></span>
    
3. <span data-ttu-id="1b9db-137">在商務用 Skype Server 管理命令介面中輸入：</span><span class="sxs-lookup"><span data-stu-id="1b9db-137">In the Skype for Business Server Management Shell, type:</span></span> 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > <span data-ttu-id="1b9db-138">若 `Enable-CsTopology` 未成功，請解決問題，使命令無法完成，再繼續進行。</span><span class="sxs-lookup"><span data-stu-id="1b9db-138">If `Enable-CsTopology` is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="1b9db-139">如果**Enable-CsTopology**不成功，移動會失敗，而且可能會使拓撲處於沒有中央管理存放區的狀態。</span><span class="sxs-lookup"><span data-stu-id="1b9db-139">If **Enable-CsTopology** is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span> 
  
4. <span data-ttu-id="1b9db-140">在商務用 Skype Server 2019 前端伺服器或前端集區上，在商務用 Skype Server 管理命令介面中輸入：</span><span class="sxs-lookup"><span data-stu-id="1b9db-140">On the Skype for Business Server 2019 Front End Server or Front End pool, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. <span data-ttu-id="1b9db-141">商務用 Skype Server 管理命令介面會顯示伺服器、檔案存放區、資料庫儲存區，以及目前狀態和建議狀態的服務連線點。</span><span class="sxs-lookup"><span data-stu-id="1b9db-141">Skype for Business Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="1b9db-142">請詳細閱讀資訊，並確認預期的來源與目的地是否無誤。</span><span class="sxs-lookup"><span data-stu-id="1b9db-142">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="1b9db-143">輸入 [Y]\*\*\*\* 繼續或 [N]\*\*\*\* 停止移動。</span><span class="sxs-lookup"><span data-stu-id="1b9db-143">Type **Y** to continue, or **N** to stop the move.</span></span> 
    
6. <span data-ttu-id="1b9db-144">檢閱由 **Move-CsManagementServer** 命令所產生的任何警告或錯誤，並加以解決。</span><span class="sxs-lookup"><span data-stu-id="1b9db-144">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span> 
    
7. <span data-ttu-id="1b9db-145">在商務用 Skype Server 2019 伺服器上，開啟商務用 Skype 伺服器部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="1b9db-145">On the Skype for Business Server 2019 server, open the Skype for Business Server Deployment Wizard.</span></span> 
    
8. <span data-ttu-id="1b9db-146">在 [商務用 Skype 伺服器部署嚮導] 中，按一下 [**安裝或更新商務用 Skype 伺服器系統**]，按一下 [**步驟2：設定或移除商務用 skype 伺服器元件**]，按 **[下一步]**，查看摘要，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="1b9db-146">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
9. <span data-ttu-id="1b9db-147">在舊版安裝伺服器上，開啟部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="1b9db-147">On the legacy install server, open the Deployment Wizard.</span></span> 
    
10. <span data-ttu-id="1b9db-148">在 [商務用 Skype 伺服器部署嚮導] 中，按一下 [**安裝或更新商務用 Skype 伺服器系統**]，按一下 [**步驟2：設定或移除商務用 skype 伺服器元件**]，按 **[下一步]**，查看摘要，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="1b9db-148">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
11. <span data-ttu-id="1b9db-149">重新開機商務用 Skype Server 2019 server。</span><span class="sxs-lookup"><span data-stu-id="1b9db-149">Reboot the Skype for Business Server 2019 server.</span></span> <span data-ttu-id="1b9db-150">因為存取中央管理伺服器資料庫的群組成員資格變更，所以需要這麼做。</span><span class="sxs-lookup"><span data-stu-id="1b9db-150">This is required because of a group membership change to access Central Management Server database.</span></span>
    
12. <span data-ttu-id="1b9db-151">若要確認有新中央管理存放區的複寫發生，請在商務用 Skype Server 管理命令介面中輸入：</span><span class="sxs-lookup"><span data-stu-id="1b9db-151">To confirm that replication with the new Central Management store is occurring, in the Skype for Business Server Management Shell, type:</span></span> 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > <span data-ttu-id="1b9db-152">複寫可能要花一些時間來更新所有目前的複本。</span><span class="sxs-lookup"><span data-stu-id="1b9db-152">The replication may take some time to update all current replicas.</span></span> 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a><span data-ttu-id="1b9db-153">移動之後移除舊版安裝中央管理存放區檔案</span><span class="sxs-lookup"><span data-stu-id="1b9db-153">To remove legacy install Central Management store files after a move</span></span>

1. <span data-ttu-id="1b9db-154">在舊版安裝伺服器上，登入安裝商務用 Skype Server 管理命令介面的電腦，做為**RTCUniversalServerAdmins**群組的成員。</span><span class="sxs-lookup"><span data-stu-id="1b9db-154">On the legacy install server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="1b9db-155">您也必須具有 SQL Server 資料庫管理員使用者權限。</span><span class="sxs-lookup"><span data-stu-id="1b9db-155">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="1b9db-156">開啟商務用 Skype Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="1b9db-156">Open Skype for Business Server Management Shell</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="1b9db-157">請先確認複寫已完成且狀態穩定後，再繼續移除之前的資料庫檔案。</span><span class="sxs-lookup"><span data-stu-id="1b9db-157">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="1b9db-158">若要在完成複寫之前移除檔案，您會中斷複寫處理常式，並將新移動的中央管理伺服器保持在未知的狀態。</span><span class="sxs-lookup"><span data-stu-id="1b9db-158">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="1b9db-159">請使用 **Get-CsManagementStoreReplicationStatus** Cmdlet 來確認複寫狀態。</span><span class="sxs-lookup"><span data-stu-id="1b9db-159">Use the cmdlet **Get-CsManagementStoreReplicationStatus** to confirm the replication status.</span></span> 
  
3. <span data-ttu-id="1b9db-160">若要從舊版安裝中央管理伺服器移除中央管理存放區資料庫檔案，請輸入：</span><span class="sxs-lookup"><span data-stu-id="1b9db-160">To remove the Central Management store database files from the legacy install Central Management Server, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    <span data-ttu-id="1b9db-161">例如：</span><span class="sxs-lookup"><span data-stu-id="1b9db-161">For example:</span></span>
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    <span data-ttu-id="1b9db-162">其中， _\<FQDN of SQL Server\>_ 指的是 Enterprise edition 部署中的舊版安裝後端伺服器或 Standard edition server 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1b9db-162">Where the  _\<FQDN of SQL Server\>_ is either the legacy install Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span> 
    

