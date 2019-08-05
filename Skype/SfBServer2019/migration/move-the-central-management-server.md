---
title: 移動中央管理伺服器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 遷移到商務用 Skype Server 2019 之後, 您必須先將中央管理伺服器移至商務用 Skype Server 2019 前端伺服器或池, 才能移除舊版伺服器。
ms.openlocfilehash: 5e16145b6695a9ee7006ab7d5321af9e478d7c37
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191959"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="ae047-103">將舊版中央管理伺服器移至商務用 Skype Server 2019</span><span class="sxs-lookup"><span data-stu-id="ae047-103">Move the legacy Central Management Server to Skype for Business Server 2019</span></span>

<span data-ttu-id="ae047-104">遷移至商務用 Skype Server 2019 之後, 且您必須先將中央管理伺服器移至商務用 Skype Server 2019 前端伺服器或池, 然後才能移除舊版伺服器。</span><span class="sxs-lookup"><span data-stu-id="ae047-104">After migrating to Skype for Business Server 2019, and before you can remove the legacy server, you need to move the Central Management Server to the Skype for Business Server 2019 Front End Server or pool.</span></span> 
  
<span data-ttu-id="ae047-105">[中央管理伺服器] 是單一主要/多重複本系統, 其中資料庫的讀/寫複本是由包含中央管理伺服器的前端伺服器所保留。</span><span class="sxs-lookup"><span data-stu-id="ae047-105">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="ae047-106">拓朴中的每個電腦 (包括包含中央管理伺服器的前端伺服器) 在安裝期間都有在電腦上安裝的 SQL Server 資料庫中的中央管理儲存資料 (預設為 RTCLOCAL) 的唯讀複本部署.</span><span class="sxs-lookup"><span data-stu-id="ae047-106">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="ae047-107">本機資料庫會透過商務用 Skype Server 複製複製器代理程式 (在所有電腦上以服務的方式) 來接收復本更新。</span><span class="sxs-lookup"><span data-stu-id="ae047-107">The local database receives replica updates by way of the Skype for Business Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="ae047-108">中央管理伺服器上的實際資料庫名稱與局部複本是 XDS, 這是由 XDS 和 XDS 檔案組成。</span><span class="sxs-lookup"><span data-stu-id="ae047-108">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="ae047-109">主資料庫位置是由 Active Directory 網域服務中的服務控制點 (SCP) 所參照。</span><span class="sxs-lookup"><span data-stu-id="ae047-109">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="ae047-110">使用中央管理伺服器來管理和設定商務用 Skype Server 的所有工具, 都使用 SCP 來尋找中央管理儲存區。</span><span class="sxs-lookup"><span data-stu-id="ae047-110">All tools that use the Central Management Server to manage and configure Skype for Business Server use the SCP to locate the Central Management store.</span></span>
  
<span data-ttu-id="ae047-111">成功移動中央管理伺服器之後, 您應該從原始前端伺服器移除中央管理伺服器資料庫。</span><span class="sxs-lookup"><span data-stu-id="ae047-111">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="ae047-112">如需有關移除中央管理伺服器資料庫的詳細資訊, 請參閱[移除前端池的 SQL Server 資料庫](remove-the-sql-server-database-for-a-front-end-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="ae047-112">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>
  
<span data-ttu-id="ae047-113">您可以在商務用 Skype Server Management Shell 中使用 Windows PowerShell Cmdlet**移動 CsManagementServer** , 將資料庫從舊版安裝 SQL server 資料庫移至商務用 skype SERVER 2019 sql server 資料庫, 然後更新SCP, 指向商務用 Skype Server 2019 中央管理伺服器位置。</span><span class="sxs-lookup"><span data-stu-id="ae047-113">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Skype for Business Server Management Shell to move the database from the legacy install SQL Server database to the Skype for Business Server 2019 SQL Server database, and then update the SCP to point to the Skype for Business Server 2019 Central Management Server location.</span></span> 
  
<span data-ttu-id="ae047-114">在移動中央管理伺服器之前, 請使用本節中的程式來準備商務用 Skype Server 2019 前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="ae047-114">Use the procedures in this section to prepare the Skype for Business Server 2019 Front End Servers before you move the Central Management Server.</span></span>
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="ae047-115">準備企業版前端池</span><span class="sxs-lookup"><span data-stu-id="ae047-115">To prepare an Enterprise Edition Front End pool</span></span>

1. <span data-ttu-id="ae047-116">在您要重設中央管理伺服器位置的 [商務用 Skype Server 2019 企業版] 前端池上, 登入商務用 Skype Server Management Shell 安裝為 RTCUniversalServerAdmins 成員的電腦。 \*\*\*\*[群組]。</span><span class="sxs-lookup"><span data-stu-id="ae047-116">On the Skype for Business Server 2019 Enterprise Edition Front End pool where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="ae047-117">您也必須在您要安裝中央管理儲存區的資料庫上, 同時擁有 SQL Server 資料庫系統管理員的使用者權利和許可權。</span><span class="sxs-lookup"><span data-stu-id="ae047-117">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span> 
    
2. <span data-ttu-id="ae047-118">開啟商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="ae047-118">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="ae047-119">若要在商務用 Skype Server 2019 SQL Server 資料庫中建立新的中央管理存放區, 請在商務用 Skype Server 管理命令介面中, 鍵入:</span><span class="sxs-lookup"><span data-stu-id="ae047-119">To create the new Central Management store in the Skype for Business Server 2019 SQL Server database, in the Skype for Business Server Management Shell, type:</span></span>
    
   ```
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. <span data-ttu-id="ae047-120">確認**已啟動\*\*\*\*商務用 Skype Server 前端**服務的狀態。</span><span class="sxs-lookup"><span data-stu-id="ae047-120">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="ae047-121">準備標準版的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="ae047-121">To prepare a Standard Edition Front End Server</span></span>

1. <span data-ttu-id="ae047-122">在您想要重新置放中央管理伺服器的商務用 Skype Server 2019 標準版前端伺服器上, 登入商務用 Skype Server Management Shell 作為 RTCUniversalServerAdmins 的成員安裝的電腦。 \*\*\*\*[群組]。</span><span class="sxs-lookup"><span data-stu-id="ae047-122">On the Skype for Business Server 2019 Standard Edition Front End Server where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> 
    
2. <span data-ttu-id="ae047-123">開啟商務用 Skype Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="ae047-123">Open the Skype for Business Server Deployment Wizard.</span></span>
    
3. <span data-ttu-id="ae047-124">在商務用 Skype Server 部署嚮導中, 按一下 [**準備第一個標準版 server Server**]。</span><span class="sxs-lookup"><span data-stu-id="ae047-124">In the Skype for Business Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>
    
4. <span data-ttu-id="ae047-125">在 [**執行命令**] 頁面上, SQL Server Express 已安裝為中央管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="ae047-125">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="ae047-126">已建立必要的防火牆規則。</span><span class="sxs-lookup"><span data-stu-id="ae047-126">Necessary firewall rules are created.</span></span> <span data-ttu-id="ae047-127">完成資料庫與必備軟體的安裝後, 按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="ae047-127">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ae047-128">初始安裝可能需要一些時間, 且 [命令輸出摘要] 畫面沒有顯示更新。</span><span class="sxs-lookup"><span data-stu-id="ae047-128">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="ae047-129">這是由 SQL Server Express 的安裝所導致。</span><span class="sxs-lookup"><span data-stu-id="ae047-129">This is due to the installation of SQL Server Express.</span></span> <span data-ttu-id="ae047-130">如果您需要監視資料庫的安裝, 請使用 [工作管理員] 來監視設定。</span><span class="sxs-lookup"><span data-stu-id="ae047-130">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span> 
  
5. <span data-ttu-id="ae047-131">若要在商務用 Skype Server 2019 標準版前端伺服器上建立新的中央管理存放區, 請在商務用 Skype Server 管理命令介面中, 鍵入:</span><span class="sxs-lookup"><span data-stu-id="ae047-131">To create the new Central Management store on the Skype for Business Server 2019 Standard Edition Front End Server, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. <span data-ttu-id="ae047-132">確認**已啟動\*\*\*\*商務用 Skype Server 前端**服務的狀態。</span><span class="sxs-lookup"><span data-stu-id="ae047-132">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="ae047-133">將舊版安裝中央管理伺服器移至商務用 Skype Server 2019</span><span class="sxs-lookup"><span data-stu-id="ae047-133">To move the legacy installs Central Management Server to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="ae047-134">在將是中央管理伺服器的商務用 Skype Server 2019 伺服器上, 登入將商務用 Skype Server Management Shell 安裝為**RTCUniversalServerAdmins**群組成員的電腦。</span><span class="sxs-lookup"><span data-stu-id="ae047-134">On the Skype for Business Server 2019 server that will be the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="ae047-135">您也必須具備 SQL Server 資料庫管理員的使用者權限和許可權。</span><span class="sxs-lookup"><span data-stu-id="ae047-135">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="ae047-136">開啟商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="ae047-136">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="ae047-137">在商務用 Skype Server Management 命令介面中, 鍵入:</span><span class="sxs-lookup"><span data-stu-id="ae047-137">In the Skype for Business Server Management Shell, type:</span></span> 
    
   ```
   Enable-CsTopology
   ```

    > [!CAUTION]
    > <span data-ttu-id="ae047-138">如果`Enable-CsTopology`未成功, 請解決導致命令無法完成的問題, 然後再繼續進行。</span><span class="sxs-lookup"><span data-stu-id="ae047-138">If `Enable-CsTopology` is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="ae047-139">如果**啟用-CsTopology**未成功, 移動就會失敗, 而且可能會讓您的拓撲處於沒有中央管理儲存區的狀態。</span><span class="sxs-lookup"><span data-stu-id="ae047-139">If **Enable-CsTopology** is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span> 
  
4. <span data-ttu-id="ae047-140">在商務用 Skype Server 2019 前端伺服器或 [前端] 池中, 在商務用 Skype Server 管理命令介面中, 鍵入:</span><span class="sxs-lookup"><span data-stu-id="ae047-140">On the Skype for Business Server 2019 Front End Server or Front End pool, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```
   Move-CsManagementServer
   ```

5. <span data-ttu-id="ae047-141">商務用 Skype Server 管理命令介面會顯示目前狀態和建議狀態的伺服器、檔案儲存區、資料庫儲存區及服務連接點。</span><span class="sxs-lookup"><span data-stu-id="ae047-141">Skype for Business Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="ae047-142">仔細閱讀資訊並確認這是您想要的來源和目的地。</span><span class="sxs-lookup"><span data-stu-id="ae047-142">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="ae047-143">鍵入**Y**繼續, 或輸入**N**以停止移動。</span><span class="sxs-lookup"><span data-stu-id="ae047-143">Type **Y** to continue, or **N** to stop the move.</span></span> 
    
6. <span data-ttu-id="ae047-144">查看**移動流覽 CsManagementServer**命令產生的任何警告或錯誤, 並加以解決。</span><span class="sxs-lookup"><span data-stu-id="ae047-144">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span> 
    
7. <span data-ttu-id="ae047-145">在商務用 Skype Server 2019 server 上, 開啟商務用 Skype Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="ae047-145">On the Skype for Business Server 2019 server, open the Skype for Business Server Deployment Wizard.</span></span> 
    
8. <span data-ttu-id="ae047-146">在商務用 Skype Server 部署嚮導中, 按一下 [**安裝或更新商務用 Skype Server System**], 按一下 [**步驟 2: 設定] 或 [移除商務用 Skype server 元件**], 按一下 **[下一步**], 查看摘要, 然後按一下 **[完成]。**.</span><span class="sxs-lookup"><span data-stu-id="ae047-146">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
9. <span data-ttu-id="ae047-147">在舊版安裝伺服器上, 開啟 [部署] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="ae047-147">On the legacy install server, open the Deployment Wizard.</span></span> 
    
10. <span data-ttu-id="ae047-148">在商務用 Skype Server 部署嚮導中, 按一下 [**安裝或更新商務用 Skype Server System**], 按一下 [**步驟 2: 設定] 或 [移除商務用 Skype server 元件**], 按一下 **[下一步**], 查看摘要, 然後按一下 **[完成]。**.</span><span class="sxs-lookup"><span data-stu-id="ae047-148">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
11. <span data-ttu-id="ae047-149">重新開機商務用 Skype Server 2019 伺服器。</span><span class="sxs-lookup"><span data-stu-id="ae047-149">Reboot the Skype for Business Server 2019 server.</span></span> <span data-ttu-id="ae047-150">這是必要的, 因為群組成員資格變更為 access 中央管理伺服器資料庫。</span><span class="sxs-lookup"><span data-stu-id="ae047-150">This is required because of a group membership change to access Central Management Server database.</span></span>
    
12. <span data-ttu-id="ae047-151">若要確認正在進行與新中央管理儲存體的複製, 請在商務用 Skype Server Management Shell 中輸入:</span><span class="sxs-lookup"><span data-stu-id="ae047-151">To confirm that replication with the new Central Management store is occurring, in the Skype for Business Server Management Shell, type:</span></span> 
    
    ```
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > <span data-ttu-id="ae047-152">複製可能需要一些時間來更新所有目前的複本。</span><span class="sxs-lookup"><span data-stu-id="ae047-152">The replication may take some time to update all current replicas.</span></span> 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a><span data-ttu-id="ae047-153">若要在移動後移除舊版安裝中央管理儲存檔案</span><span class="sxs-lookup"><span data-stu-id="ae047-153">To remove legacy install Central Management store files after a move</span></span>

1. <span data-ttu-id="ae047-154">在舊版安裝伺服器上, 登入將商務用 Skype Server Management Shell 安裝為**RTCUniversalServerAdmins**群組成員的電腦。</span><span class="sxs-lookup"><span data-stu-id="ae047-154">On the legacy install server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="ae047-155">您也必須具備 SQL Server 資料庫管理員的使用者權限和許可權。</span><span class="sxs-lookup"><span data-stu-id="ae047-155">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="ae047-156">開啟商務用 Skype Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="ae047-156">Open Skype for Business Server Management Shell</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="ae047-157">在複製完成且穩定之前, 請勿繼續移除先前的資料庫檔案。</span><span class="sxs-lookup"><span data-stu-id="ae047-157">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="ae047-158">如果您在完成複製之前移除檔案, 您將會中斷複製程式, 並將新移動的中央管理伺服器保持在未知狀態。</span><span class="sxs-lookup"><span data-stu-id="ae047-158">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="ae047-159">使用 Cmdlet **CsManagementStoreReplicationStatus**來確認複製狀態。</span><span class="sxs-lookup"><span data-stu-id="ae047-159">Use the cmdlet **Get-CsManagementStoreReplicationStatus** to confirm the replication status.</span></span> 
  
3. <span data-ttu-id="ae047-160">若要從舊版安裝中央管理伺服器移除中央管理儲存資料庫檔案, 請輸入:</span><span class="sxs-lookup"><span data-stu-id="ae047-160">To remove the Central Management store database files from the legacy install Central Management Server, type:</span></span>
    
   ```
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    <span data-ttu-id="ae047-161">例如：</span><span class="sxs-lookup"><span data-stu-id="ae047-161">For example:</span></span>
    
   ```
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    <span data-ttu-id="ae047-162">其中, _ \<SQL Server\>的 FQDN_是企業版部署中的舊版安裝後端伺服器, 或是標準版 Server 的 fqdn。</span><span class="sxs-lookup"><span data-stu-id="ae047-162">Where the  _\<FQDN of SQL Server\>_ is either the legacy install Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span> 
    

