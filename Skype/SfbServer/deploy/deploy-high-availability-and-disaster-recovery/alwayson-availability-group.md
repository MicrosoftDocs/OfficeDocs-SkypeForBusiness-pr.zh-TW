---
title: 在商務用 Skype 伺服器的後端伺服器上部署 Alwayson 可用性群組
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: 在商務用 Skype 伺服器部署中部署 (安裝) Always On 可用性群組。
ms.openlocfilehash: 83565efe850570ac5ab9a0695757e708f3eae566
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830653"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a><span data-ttu-id="e7011-103">在商務用 Skype 伺服器的後端伺服器上部署 Alwayson 可用性群組</span><span class="sxs-lookup"><span data-stu-id="e7011-103">Deploy an Always On Availability Group on a Back End Server in Skype for Business Server</span></span>
 
<span data-ttu-id="e7011-104">在商務用 Skype Server 部署中部署 (安裝)  (AG) 。</span><span class="sxs-lookup"><span data-stu-id="e7011-104">Deploy (install) an Always On Availability Group (AG) in your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="e7011-105">如何部署 AG 取決於您是在新的集區中部署它、使用鏡像的現有集區，或是目前沒有後端資料庫高可用性的現有集區。</span><span class="sxs-lookup"><span data-stu-id="e7011-105">How you deploy an AG depends on whether you are deploying it in a new pool, an existing pool that uses mirroring, or an existing pool that currently has no high availability for the Back End database.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e7011-106">不支援使用具有 Persistent Chat Server role 的 AG。</span><span class="sxs-lookup"><span data-stu-id="e7011-106">Using an AG with a Persistent Chat Server role is not supported.</span></span> 
  
- [<span data-ttu-id="e7011-107">在新的前端集區上部署 Always On 可用性群組</span><span class="sxs-lookup"><span data-stu-id="e7011-107">Deploy an Always On Availability Group on a new Front End pool</span></span>](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="e7011-108">在使用資料庫鏡像的現有集區上部署 Always On 可用性群組</span><span class="sxs-lookup"><span data-stu-id="e7011-108">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="e7011-109">在未使用資料庫鏡像的現有集區上部署 Always On 可用性群組</span><span class="sxs-lookup"><span data-stu-id="e7011-109">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a><span data-ttu-id="e7011-110">在新的前端集區上部署 Always On 可用性群組</span><span class="sxs-lookup"><span data-stu-id="e7011-110">Deploy an Always On Availability Group on a new Front End pool</span></span>
<span data-ttu-id="e7011-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="e7011-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span></span>

1. <span data-ttu-id="e7011-112">在將成為 AG 一部分之所有資料庫伺服器上啟用容錯移轉叢集功能。</span><span class="sxs-lookup"><span data-stu-id="e7011-112">Enable the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="e7011-113">在每一部伺服器上，執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="e7011-113">On each server, do the following</span></span>
    
   - <span data-ttu-id="e7011-114">開啟 [伺服器管理員]，然後按一下 [ **新增角色及功能**]。</span><span class="sxs-lookup"><span data-stu-id="e7011-114">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="e7011-115">按 **[下一步]** ，直到您到達 [ **選取功能** ] 方塊。</span><span class="sxs-lookup"><span data-stu-id="e7011-115">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="e7011-116">在這裡，選取 [ **容錯移轉** 叢集] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e7011-116">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="e7011-117">在 [ **新增容錯移轉叢集所需的功能？** ] 方塊中，按一下 [ **新增功能**]。</span><span class="sxs-lookup"><span data-stu-id="e7011-117">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="e7011-118">按一下 **安裝**。</span><span class="sxs-lookup"><span data-stu-id="e7011-118">Click **Install**.</span></span>
    
2. <span data-ttu-id="e7011-119">驗證叢集設定。</span><span class="sxs-lookup"><span data-stu-id="e7011-119">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="e7011-120">在 [伺服器管理員] 中，按一下 [ **工具** ] 功能表，然後按一下 [ **容錯移轉叢集管理員**]。</span><span class="sxs-lookup"><span data-stu-id="e7011-120">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="e7011-121">在螢幕右側的 [ **動作** ] 下，按一下 [ **驗證** 設定]。</span><span class="sxs-lookup"><span data-stu-id="e7011-121">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="e7011-122">在 **[開始之前]** 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-122">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="e7011-123">選取要新增至該群集中的伺服器，然後按一下 [ **執行所有測試**]。</span><span class="sxs-lookup"><span data-stu-id="e7011-123">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="e7011-124">在 [ **摘要** ] 方塊中，檢查嚮導所報告的任何錯誤。</span><span class="sxs-lookup"><span data-stu-id="e7011-124">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="e7011-125">然後按一下 **[完成]** 以完成驗證。</span><span class="sxs-lookup"><span data-stu-id="e7011-125">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="e7011-126">嚮導可能會報告數個警告，尤其是當您不是使用共用儲存區時。</span><span class="sxs-lookup"><span data-stu-id="e7011-126">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="e7011-127">您不需要使用共用儲存區。</span><span class="sxs-lookup"><span data-stu-id="e7011-127">You are not required to use shared storage.</span></span> <span data-ttu-id="e7011-128">不過，如果您看到任何 **錯誤** 訊息，您必須先修正這些問題，再繼續進行。</span><span class="sxs-lookup"><span data-stu-id="e7011-128">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="e7011-129">建立 Windows Server 容錯移轉叢集 (WSFC) 。</span><span class="sxs-lookup"><span data-stu-id="e7011-129">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="e7011-130">在 [ **容錯移轉叢集管理** ] 嚮導中，以滑鼠右鍵按一下 [ **容錯移轉叢集管理**]，然後按一下 [ **建立** 叢集]。</span><span class="sxs-lookup"><span data-stu-id="e7011-130">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="e7011-131">在 **[開始之前]** 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-131">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="e7011-132">新增群集名稱和 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="e7011-132">Add the cluster name and IP address.</span></span> <span data-ttu-id="e7011-133">驗證設定後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-133">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="e7011-134">在 [確認] 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-134">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="e7011-135">建立叢集後，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-135">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="e7011-136">建議您將叢集仲裁設定設定為使用檔案共用見證。</span><span class="sxs-lookup"><span data-stu-id="e7011-136">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="e7011-137">若要這麼做，請使用下列步驟：</span><span class="sxs-lookup"><span data-stu-id="e7011-137">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="e7011-138">以滑鼠右鍵按一下叢集名稱，按一下 [ **其他動作**]，然後按一下 [ **設定叢集仲裁設定**]。</span><span class="sxs-lookup"><span data-stu-id="e7011-138">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="e7011-139">在 [ **選取仲裁設定選項** ] 頁面上，按一下 **[選取仲裁見證**]。</span><span class="sxs-lookup"><span data-stu-id="e7011-139">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="e7011-140">在 [ **選取仲裁見證** ] 頁面上，按一下 [ **設定檔案共用見證**]。</span><span class="sxs-lookup"><span data-stu-id="e7011-140">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="e7011-141">在 [ **設定檔案共用見證** ] 頁面中，輸入您要使用的檔案共用路徑，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-141">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="e7011-142">在 [確認] 頁面上，按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="e7011-142">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="e7011-143">在該群集中的每一部伺服器上，啟用 SQL Server Configuration Manager 中的 AG 功能。</span><span class="sxs-lookup"><span data-stu-id="e7011-143">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="e7011-144">開啟 SQL Server Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="e7011-144">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="e7011-145">在螢幕左側的樹狀目錄中，按一下 [ **Sql Server 服務**]，然後按兩下 [sql server 服務]。</span><span class="sxs-lookup"><span data-stu-id="e7011-145">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="e7011-146">在 [ **屬性** ] 方塊中，選取 [ **AlwaysOn 高可用性** ] 索引標籤。選取 [ **啟用 AlwaysOn 可用性群組** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e7011-146">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="e7011-147">出現提示時，請重新開機 SQL Server 服務。</span><span class="sxs-lookup"><span data-stu-id="e7011-147">Restart the SQL Server service when prompted.</span></span>
   
6. <span data-ttu-id="e7011-148">使用拓撲產生器建立前端集區，如在 [商務用 Skype Server 中建立及發行新拓撲](../../deploy/install/create-and-publish-new-topology.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="e7011-148">Use Topology Builder to create the Front End pool, as explained in [Create and publish new topology in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md).</span></span> <span data-ttu-id="e7011-149">當您這麼做時，請將 AG 指定為集區的 SQL 存放區。</span><span class="sxs-lookup"><span data-stu-id="e7011-149">When you do, specify the AG as the SQL store for the pool.</span></span>
    
7. <span data-ttu-id="e7011-150">建立可用性群組。</span><span class="sxs-lookup"><span data-stu-id="e7011-150">Create the availability group.</span></span>
    
   - <span data-ttu-id="e7011-151">開啟 SQL Server Management Studio，並連接至 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="e7011-151">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="e7011-152">在 [物件瀏覽器] 中，展開 [ **永不增加高可用性** ] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="e7011-152">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="e7011-153">在 [ **可用性群組** ] 資料夾上按一下滑鼠右鍵，然後按一下 [ **新增可用性群組嚮導]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-153">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="e7011-154">如果出現 [ **簡介** ] 頁面，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-154">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="e7011-155">在 [ **指定可用性組名** ] 頁面中，輸入可用性群組的名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-155">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="e7011-156">在 [選取資料庫] 頁面中，選取您要包含在 [AlwaysOn 可用性] 群組中的資料庫。</span><span class="sxs-lookup"><span data-stu-id="e7011-156">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="e7011-157">然後按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="e7011-157">Then click **Next**.</span></span>
    
     <span data-ttu-id="e7011-158">請不要在 AlwaysOn 可用性群組中包含 **ReportServer**、 **ReportServerTempDB** 或 Persistent 聊天資料庫，因為這種情況不會支援這些功能。</span><span class="sxs-lookup"><span data-stu-id="e7011-158">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="e7011-159">您可以在 AlwaysOn 可用性群組中包含所有其他商務用 Skype Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="e7011-159">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="e7011-160">在 [ **指定複本** ] 頁面上，按一下 [ **複本** ] 索引標籤。然後按一下 [ **新增複製副本** ] 按鈕，並聯機至您加入為 Windows Server 容錯移轉叢集之節點的其他 SQL 實例。</span><span class="sxs-lookup"><span data-stu-id="e7011-160">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="e7011-161">針對每個實例，選取 [ **自動容錯移轉** ] 和 [ **同步認可** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="e7011-161">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="e7011-162">請勿選取 [ **可讀取的次要** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="e7011-162">Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="e7011-163">按一下 [ **端點** ] 索引標籤，並確認 **埠號碼** 設定為5022。</span><span class="sxs-lookup"><span data-stu-id="e7011-163">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="e7011-164">按一下 [ **監聽器** ] 索引標籤，然後選取 [ **建立可用性群組接聽程式** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="e7011-164">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="e7011-165">在 [此選項] 底下輸入監聽器的名稱，並將 **埠** 設定為 1433 (此選項) 不支援其他埠。</span><span class="sxs-lookup"><span data-stu-id="e7011-165">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="e7011-166">按一下 [ **新增**]，然後在 [ **IPv4 網址** ] 方塊中，提供您慣用的虛擬 IP 位址，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-166">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="e7011-167">在 [ **選取初始資料同步** 處理] 頁面中，選取 [完整]，並指定複本可存取的資料夾，而且這兩個複本所使用的 SQL Server 服務帳戶都具有寫入權限。</span><span class="sxs-lookup"><span data-stu-id="e7011-167">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="e7011-168">然後按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="e7011-168">Then click **Next**.</span></span>
    
     <span data-ttu-id="e7011-169">當您初始化資料庫時，會暫時使用此檔案共用。</span><span class="sxs-lookup"><span data-stu-id="e7011-169">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="e7011-170">如果您正在處理大型資料庫，建議您手動加以初始化，以防您的網路頻寬無法容納資料庫備份的大小。</span><span class="sxs-lookup"><span data-stu-id="e7011-170">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
   - <span data-ttu-id="e7011-171">在 [驗證] 頁面中，確認所有驗證檢查是否都成功，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-171">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="e7011-172">在 [ **摘要** ] 頁面中，確認所有設定，然後按一下 [完成]。</span><span class="sxs-lookup"><span data-stu-id="e7011-172">In the **Summary** page, verify all settings and click Finish.</span></span>
      
8. <span data-ttu-id="e7011-173">部署集區和 AG 之後，請執行一些最後的步驟，確定每個副本的 SQL 登入都位於 AlwaysOn 可用性群組中。</span><span class="sxs-lookup"><span data-stu-id="e7011-173">After the pool and the AG are deployed, perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span> 
    
   - <span data-ttu-id="e7011-174">開啟拓撲產生器，選取 [ **從現有的部署下載拓撲**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-174">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="e7011-175">展開 [商務用 Skype 伺服器]，展開您的拓撲，然後展開 **[SQL Server 儲存區**]。</span><span class="sxs-lookup"><span data-stu-id="e7011-175">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="e7011-176">以滑鼠右鍵按一下新 AlwaysOn 可用性群組的 SQL 存放區，然後按一下 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="e7011-176">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
     - <span data-ttu-id="e7011-177">在頁面底部的 [ **SQL SERVER FQDN** ] 方塊中，將值變更為 AG 的攔截器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e7011-177">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
   - <span data-ttu-id="e7011-178">發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="e7011-178">Publish the topology.</span></span> <span data-ttu-id="e7011-179">從 [ **動作** ] 功能表中，按一下 [ **拓撲** ]，然後再 **發佈**。</span><span class="sxs-lookup"><span data-stu-id="e7011-179">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="e7011-180">然後在 [確認] 頁面中按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-180">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="e7011-181">然後，請稍候幾分鐘，以複製新的拓撲。</span><span class="sxs-lookup"><span data-stu-id="e7011-181">Then wait a few minutes for the new topology to replicate.</span></span>
    
   - <span data-ttu-id="e7011-182">開啟 SQL Server Management Studio，並流覽至 AG。</span><span class="sxs-lookup"><span data-stu-id="e7011-182">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="e7011-183">將其容錯移轉至次要複本。</span><span class="sxs-lookup"><span data-stu-id="e7011-183">Fail it over to a secondary replica.</span></span>
    
   - <span data-ttu-id="e7011-184">開啟商務用 Skype Server 管理命令介面，並輸入下列 Cmdlet，以在此複本上建立 SQL 登入：</span><span class="sxs-lookup"><span data-stu-id="e7011-184">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
   ```powershell
   Install-CsDatabase -Update
   ```

   - <span data-ttu-id="e7011-185">重複執行先前的兩個步驟 (將群組容錯移轉至次要複本，然後  `Install-CsDatabase -Update` 針對群組中的每個複本使用) 。</span><span class="sxs-lookup"><span data-stu-id="e7011-185">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a><span data-ttu-id="e7011-186">在使用資料庫鏡像的現有集區上部署 Always On 可用性群組</span><span class="sxs-lookup"><span data-stu-id="e7011-186">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>
<span data-ttu-id="e7011-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="e7011-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="e7011-188">如果您要升級的集區為 AG 主控組織的中央管理存放區，則必須先將 CMS 移至另一個集區，再升級此集區。</span><span class="sxs-lookup"><span data-stu-id="e7011-188">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="e7011-189">使用 Move-CsManagementServer Cmdlet 可移動集區。</span><span class="sxs-lookup"><span data-stu-id="e7011-189">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="e7011-190">如果您的組織中沒有另一個集區，您可以暫時部署 Standard Edition server，並將 CMS 移至此伺服器，再將您的集區升級至 AG。</span><span class="sxs-lookup"><span data-stu-id="e7011-190">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="e7011-191">開啟商務用 Skype Server 管理命令介面並輸入下列指令程式，以將鏡像中的所有資料容錯移轉至主體節點。</span><span class="sxs-lookup"><span data-stu-id="e7011-191">Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.</span></span>
    
   ```powershell
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    <span data-ttu-id="e7011-192">針對集區中的每個資料庫類型重複此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e7011-192">Repeat this cmdlet for each database type in the pool.</span></span> <span data-ttu-id="e7011-193">您可以使用下列 Cmdlet 來尋找儲存在此集區中的所有資料庫類型。</span><span class="sxs-lookup"><span data-stu-id="e7011-193">You can use the following cmdlet to find all the database types stored in this pool.</span></span>
     
   ```powershell
   Get-CsPool -Identity <Pool FQDN>
   ```

2. <span data-ttu-id="e7011-194">使用拓撲產生器，從集區中移除資料庫鏡像。</span><span class="sxs-lookup"><span data-stu-id="e7011-194">Use Topology Builder to remove database mirroring from the pool.</span></span>
    
   - <span data-ttu-id="e7011-195">開啟拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="e7011-195">Open Topology Builder.</span></span> <span data-ttu-id="e7011-196">在您的拓撲中，展開 [ **Enterprise Edition 前端** 集區]，以滑鼠右鍵按一下集區的名稱，然後按一下 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="e7011-196">In your topology, expand **Enterprise Edition Front End Pools**, right-click the name of the pool, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="e7011-197">針對集區中的每一種 SQL 存放區，清除 [ **啟用 SQL 存放區鏡像** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e7011-197">For each type of SQL store in the pool, clear the **Enable SQL Store Mirroring** check box.</span></span>
    
3. <span data-ttu-id="e7011-198">發佈變更的拓撲。</span><span class="sxs-lookup"><span data-stu-id="e7011-198">Publish the changed topology.</span></span> <span data-ttu-id="e7011-199">從 [ **動作** ] 功能表中，按一下 [ **拓撲** ]，然後再 **發佈**。</span><span class="sxs-lookup"><span data-stu-id="e7011-199">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="e7011-200">然後在 [確認] 頁面中，按 **[下一步]**</span><span class="sxs-lookup"><span data-stu-id="e7011-200">Then in the confirmation page click **Next**</span></span>
    
4. <span data-ttu-id="e7011-201">使用 SQL Server Management Studio 來中斷鏡像。</span><span class="sxs-lookup"><span data-stu-id="e7011-201">Use SQL Server Management Studio to break the mirror.</span></span>
    
   - <span data-ttu-id="e7011-202">開啟 SQL Server Management Studio，流覽至您的資料庫，以滑鼠右鍵按一下 [ **任務** ]，然後按一下 [ **鏡像**]。</span><span class="sxs-lookup"><span data-stu-id="e7011-202">Open SQL Server Management Studio, navigate to your databases, right-click **Tasks** and click **Mirror**.</span></span> <span data-ttu-id="e7011-203">然後按一下 [ **移除鏡像** ]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-203">Then click **Remove Mirroring** and click **OK**.</span></span>
    
   - <span data-ttu-id="e7011-204">針對集區中將轉換為 AG 的所有資料庫重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="e7011-204">Repeat this for all databases in the pool which will be converted to an AG.</span></span>
    
5. <span data-ttu-id="e7011-205">在將成為 AG 一部分的所有資料庫伺服器上，設定容錯移轉叢集功能。</span><span class="sxs-lookup"><span data-stu-id="e7011-205">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="e7011-206">在每一部伺服器上，執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="e7011-206">On each server, do the following</span></span>
    
   - <span data-ttu-id="e7011-207">開啟 [伺服器管理員]，然後按一下 [ **新增角色及功能**]。</span><span class="sxs-lookup"><span data-stu-id="e7011-207">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="e7011-208">按 **[下一步]** ，直到您到達 [ **選取功能** ] 方塊。</span><span class="sxs-lookup"><span data-stu-id="e7011-208">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="e7011-209">在這裡，選取 [ **容錯移轉** 叢集] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e7011-209">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="e7011-210">在 [ **新增容錯移轉叢集所需的功能？** ] 方塊中，按一下 [ **新增功能**]。</span><span class="sxs-lookup"><span data-stu-id="e7011-210">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="e7011-211">按一下 **安裝**。</span><span class="sxs-lookup"><span data-stu-id="e7011-211">Click **Install**.</span></span>
    
6. <span data-ttu-id="e7011-212">驗證叢集設定。</span><span class="sxs-lookup"><span data-stu-id="e7011-212">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="e7011-213">在 [伺服器管理員] 中，按一下 [ **工具** ] 功能表，然後按一下 [ **容錯移轉叢集管理員**]。</span><span class="sxs-lookup"><span data-stu-id="e7011-213">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="e7011-214">在螢幕右側的 [ **動作** ] 下，按一下 [ **驗證** 設定]。</span><span class="sxs-lookup"><span data-stu-id="e7011-214">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="e7011-215">在 **[開始之前]** 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-215">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="e7011-216">選取要新增至該群集中的伺服器，然後按一下 [ **執行所有測試**]。</span><span class="sxs-lookup"><span data-stu-id="e7011-216">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="e7011-217">在 [ **摘要** ] 方塊中，檢查嚮導所報告的任何錯誤。</span><span class="sxs-lookup"><span data-stu-id="e7011-217">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="e7011-218">然後按一下 **[完成]** 以完成驗證。</span><span class="sxs-lookup"><span data-stu-id="e7011-218">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="e7011-219">嚮導可能會報告數個警告，尤其是當您不是使用共用儲存區時。</span><span class="sxs-lookup"><span data-stu-id="e7011-219">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="e7011-220">您不需要使用共用儲存區。</span><span class="sxs-lookup"><span data-stu-id="e7011-220">You are not required to use shared storage.</span></span> <span data-ttu-id="e7011-221">不過，如果您看到任何 **錯誤** 訊息，您必須先修正這些問題，再繼續進行。</span><span class="sxs-lookup"><span data-stu-id="e7011-221">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
7. <span data-ttu-id="e7011-222">建立 Windows Server 容錯移轉叢集。</span><span class="sxs-lookup"><span data-stu-id="e7011-222">Create the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="e7011-223">在 [ **容錯移轉叢集管理** ] 嚮導中，以滑鼠右鍵按一下 [ **容錯移轉叢集管理**]，然後按一下 [ **建立** 叢集]。</span><span class="sxs-lookup"><span data-stu-id="e7011-223">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="e7011-224">在 **[開始之前]** 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-224">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="e7011-225">新增群集名稱和 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="e7011-225">Add the cluster name and IP address.</span></span> <span data-ttu-id="e7011-226">驗證設定後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-226">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="e7011-227">在 [確認] 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-227">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="e7011-228">建立叢集後，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-228">After the cluster is created, click **Finish**.</span></span>
    
8. <span data-ttu-id="e7011-229">建議您將叢集仲裁設定設定為使用檔案共用見證。</span><span class="sxs-lookup"><span data-stu-id="e7011-229">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="e7011-230">若要這麼做，請使用下列步驟：</span><span class="sxs-lookup"><span data-stu-id="e7011-230">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="e7011-231">以滑鼠右鍵按一下叢集名稱，按一下 [ **其他動作**]，然後按一下 [ **設定叢集仲裁設定**]。</span><span class="sxs-lookup"><span data-stu-id="e7011-231">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="e7011-232">在 [ **選取仲裁設定選項** ] 頁面上，按一下 **[選取仲裁見證**]。</span><span class="sxs-lookup"><span data-stu-id="e7011-232">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="e7011-233">在 [ **選取仲裁見證** ] 頁面上，按一下 [ **設定檔案共用見證**]。</span><span class="sxs-lookup"><span data-stu-id="e7011-233">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="e7011-234">在 [ **設定檔案共用見證** ] 頁面中，輸入您要使用的檔案共用路徑，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-234">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="e7011-235">在 [確認] 頁面上，按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="e7011-235">On the **Confirmation** page, click **Next**.</span></span>
    
9. <span data-ttu-id="e7011-236">在該群集中的每一部伺服器上，啟用 SQL Server Configuration Manager 中的 AG 功能。</span><span class="sxs-lookup"><span data-stu-id="e7011-236">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="e7011-237">開啟 SQL Server Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="e7011-237">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="e7011-238">在螢幕左側的樹狀目錄中，按一下 [ **Sql Server 服務**]，然後按兩下 [sql server 服務]。</span><span class="sxs-lookup"><span data-stu-id="e7011-238">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="e7011-239">在 [ **屬性** ] 方塊中，選取 [ **AlwaysOn 高可用性** ] 索引標籤。選取 [ **啟用 AlwaysOn 可用性群組** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e7011-239">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="e7011-240">出現提示時，請重新開機 SQL Server 服務。</span><span class="sxs-lookup"><span data-stu-id="e7011-240">Restart the SQL Server service when prompted.</span></span>
    
10. <span data-ttu-id="e7011-241">建立可用性群組。</span><span class="sxs-lookup"><span data-stu-id="e7011-241">Create the availability group.</span></span>
    
    - <span data-ttu-id="e7011-242">開啟 SQL Server Management Studio，並連接至 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="e7011-242">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
    - <span data-ttu-id="e7011-243">在 [物件瀏覽器] 中，展開 [ **永不增加高可用性** ] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="e7011-243">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="e7011-244">在 [ **可用性群組** ] 資料夾上按一下滑鼠右鍵，然後按一下 [ **新增可用性群組嚮導]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-244">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
    - <span data-ttu-id="e7011-245">如果出現 [ **簡介** ] 頁面，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-245">If the **Introduction** page appears, click **Next**.</span></span>
    
    - <span data-ttu-id="e7011-246">在 [ **指定可用性組名** ] 頁面中，輸入可用性群組的名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-246">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
    - <span data-ttu-id="e7011-247">在 [選取資料庫] 頁面中，選取您要包含在 [AlwaysOn 可用性] 群組中的資料庫。</span><span class="sxs-lookup"><span data-stu-id="e7011-247">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="e7011-248">然後按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="e7011-248">Then click **Next**.</span></span>
    
    <span data-ttu-id="e7011-249">請不要在 AlwaysOn 可用性群組中包含 **ReportServer**、 **ReportServerTempDB** 或 Persistent 聊天資料庫，因為這種情況不會支援這些功能。</span><span class="sxs-lookup"><span data-stu-id="e7011-249">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="e7011-250">您可以在 AlwaysOn 可用性群組中包含所有其他商務用 Skype Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="e7011-250">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="e7011-251">在 [ **指定複本** ] 頁面上，按一下 [ **複本** ] 索引標籤。然後按一下 [ **新增複製副本** ] 按鈕，並聯機至您加入為 Windows Server 容錯移轉叢集之節點的其他 SQL 實例。</span><span class="sxs-lookup"><span data-stu-id="e7011-251">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
    - <span data-ttu-id="e7011-252">針對每個實例，選取 [ **自動容錯移轉** ] 和 [ **同步認可** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="e7011-252">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="e7011-253">請勿選取 [ **可讀取的次要** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="e7011-253">Do not select the **Readable Secondary** option.</span></span>
    
    - <span data-ttu-id="e7011-254">按一下 [ **端點** ] 索引標籤，並確認 **埠號碼** 設定為5022。</span><span class="sxs-lookup"><span data-stu-id="e7011-254">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
      - <span data-ttu-id="e7011-255">按一下 [ **監聽器** ] 索引標籤，然後選取 [ **建立可用性群組接聽程式** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="e7011-255">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="e7011-256">在 [此選項] 底下輸入監聽器的名稱，並將 **埠** 設定為 1433 (此選項) 不支援其他埠。</span><span class="sxs-lookup"><span data-stu-id="e7011-256">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
    - <span data-ttu-id="e7011-257">按一下 [ **新增**]，然後在 [ **IPv4 網址** ] 方塊中，提供您慣用的虛擬 IP 位址，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-257">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
    - <span data-ttu-id="e7011-258">在 [ **選取初始資料同步** 處理] 頁面中，選取 [完整]，並指定複本可存取的資料夾，而且這兩個複本所使用的 SQL Server 服務帳戶都具有寫入權限。</span><span class="sxs-lookup"><span data-stu-id="e7011-258">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="e7011-259">然後按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="e7011-259">Then click **Next**.</span></span>
    
    <span data-ttu-id="e7011-260">當您初始化資料庫時，會暫時使用此檔案共用。</span><span class="sxs-lookup"><span data-stu-id="e7011-260">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="e7011-261">如果您正在處理大型資料庫，建議您手動加以初始化，以防您的網路頻寬無法容納資料庫備份的大小。</span><span class="sxs-lookup"><span data-stu-id="e7011-261">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="e7011-262">在 [驗證] 頁面中，確認所有驗證檢查是否都成功，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-262">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
    - <span data-ttu-id="e7011-263">在 [ **摘要** ] 頁面中，確認所有設定，然後按一下 [完成]。</span><span class="sxs-lookup"><span data-stu-id="e7011-263">In the **Summary** page, verify all settings and click Finish.</span></span>
    
11. <span data-ttu-id="e7011-264">建立新的存放區，指定 AG 接聽程式，並將舊鏡像的主體指定為 AG 的主要節點。</span><span class="sxs-lookup"><span data-stu-id="e7011-264">Create a new store specifying the AG listener, and specifying the principal of the old mirror as the primary node of the AG.</span></span>
    
    - <span data-ttu-id="e7011-265">開啟拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="e7011-265">Open Topology Builder.</span></span> <span data-ttu-id="e7011-266">在拓撲中，展開 [ **共用元件**]，以滑鼠右鍵按一下 **[sql server** 存放區]，然後按一下 **[新增 sql server 儲存區**]。</span><span class="sxs-lookup"><span data-stu-id="e7011-266">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
    - <span data-ttu-id="e7011-267">在 [ **定義新的 SQL 存放區** ] 頁面中，先選取 [ **高可用性設定** ] 核取方塊，然後確定 [SQL AlwaysOn 可用性群組會出現在下拉式方塊中。</span><span class="sxs-lookup"><span data-stu-id="e7011-267">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
    - <span data-ttu-id="e7011-268">在 [ **SQL Server 可用性接聽程式 FQDN]** 方塊中，輸入您在建立可用性群組時所建立的攔截器 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e7011-268">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
    - <span data-ttu-id="e7011-269">在 [ **SQL SERVER FQDN** ] 方塊中，輸入 AG 的主要節點的 FQDN，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-269">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span> <span data-ttu-id="e7011-270">這應該是此存放區之舊鏡像的主體。</span><span class="sxs-lookup"><span data-stu-id="e7011-270">This should be the principal of the old mirror for this store.</span></span>
    
12. <span data-ttu-id="e7011-271">將新的 AG 與前端集區產生關聯。</span><span class="sxs-lookup"><span data-stu-id="e7011-271">Associate the new AG with the Front End pool.</span></span>
    
    - <span data-ttu-id="e7011-272">在 [拓撲產生器] 中，以滑鼠右鍵按一下要與 AG 產生關聯的集區，然後按一下 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="e7011-272">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="e7011-273">在 [ **關聯**] 底下，選取 [ **SQL Server 存放區** ] 方塊中的 AG。</span><span class="sxs-lookup"><span data-stu-id="e7011-273">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="e7011-274">針對您要移至 AG 的集區中的任何其他資料庫，選取相同的群組。</span><span class="sxs-lookup"><span data-stu-id="e7011-274">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
    - <span data-ttu-id="e7011-275">當您確定所有必要的資料庫都設定為 AG 時，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-275">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
13. <span data-ttu-id="e7011-276">發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="e7011-276">Publish the topology.</span></span> <span data-ttu-id="e7011-277">從 [ **動作** ] 功能表中，按一下 [ **拓撲** ]，然後再 **發佈**。</span><span class="sxs-lookup"><span data-stu-id="e7011-277">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="e7011-278">然後在 [確認] 頁面中按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-278">Then in the confirmation page click **Next**.</span></span>
    
14. <span data-ttu-id="e7011-279">執行一些最後一個步驟，確定每個副本的 SQL 登入都位於 AlwaysOn 可用性群組中的每個副本上。</span><span class="sxs-lookup"><span data-stu-id="e7011-279">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="e7011-280">開啟拓撲產生器，選取 [ **從現有的部署下載拓撲**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-280">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="e7011-281">展開 [商務用 Skype 伺服器]，展開您的拓撲，然後展開 **[SQL Server 儲存區**]。</span><span class="sxs-lookup"><span data-stu-id="e7011-281">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="e7011-282">以滑鼠右鍵按一下新 AG 的 SQL 存放區，然後按一下 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="e7011-282">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="e7011-283">在頁面底部的 [ **SQL SERVER FQDN** ] 方塊中，將值變更為 AG 的攔截器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e7011-283">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="e7011-284">發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="e7011-284">Publish the topology.</span></span> <span data-ttu-id="e7011-285">從 [ **動作** ] 功能表中，按一下 [ **拓撲** ]，然後再 **發佈**。</span><span class="sxs-lookup"><span data-stu-id="e7011-285">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="e7011-286">然後在 [確認] 頁面中按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-286">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="e7011-287">然後，請稍候幾分鐘，以複製新的拓撲。</span><span class="sxs-lookup"><span data-stu-id="e7011-287">Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="e7011-288">開啟 SQL Server Management Studio，並流覽至 AG。</span><span class="sxs-lookup"><span data-stu-id="e7011-288">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="e7011-289">將其容錯移轉至次要複本。</span><span class="sxs-lookup"><span data-stu-id="e7011-289">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="e7011-290">開啟商務用 Skype Server 管理命令介面，並輸入下列 Cmdlet，以在此複本上建立 SQL 登入：</span><span class="sxs-lookup"><span data-stu-id="e7011-290">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
    ```powershell
    Install-CsDatabase -Update
    ```

    - <span data-ttu-id="e7011-291">重複執行先前的兩個步驟 (將群組容錯移轉至次要複本，然後  `Install-CsDatabase -Update` 針對群組中的每個複本使用) 。</span><span class="sxs-lookup"><span data-stu-id="e7011-291">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a><span data-ttu-id="e7011-292">在未使用資料庫鏡像的現有集區上部署 Always On 可用性群組</span><span class="sxs-lookup"><span data-stu-id="e7011-292">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>
<span data-ttu-id="e7011-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="e7011-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="e7011-294">如果您要升級的集區為 AG 主控組織的中央管理存放區，則必須先將 CMS 移至另一個集區，再升級此集區。</span><span class="sxs-lookup"><span data-stu-id="e7011-294">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="e7011-295">使用 Move-CsManagementServer Cmdlet 可移動集區。</span><span class="sxs-lookup"><span data-stu-id="e7011-295">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="e7011-296">如果您的組織中沒有另一個集區，您可以暫時部署 Standard Edition server，並將 CMS 移至此伺服器，再將您的集區升級至 AG。</span><span class="sxs-lookup"><span data-stu-id="e7011-296">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="e7011-297">在將成為 AG 一部分的所有資料庫伺服器上，設定容錯移轉叢集功能。</span><span class="sxs-lookup"><span data-stu-id="e7011-297">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="e7011-298">在每一部伺服器上，執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="e7011-298">On each server, do the following</span></span>
    
   - <span data-ttu-id="e7011-299">開啟 [伺服器管理員]，然後按一下 [ **新增角色及功能**]。</span><span class="sxs-lookup"><span data-stu-id="e7011-299">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="e7011-300">按 **[下一步]** ，直到您到達 [ **選取功能** ] 方塊。</span><span class="sxs-lookup"><span data-stu-id="e7011-300">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="e7011-301">在這裡，選取 [ **容錯移轉** 叢集] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e7011-301">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="e7011-302">在 [ **新增容錯移轉叢集所需的功能？** ] 方塊中，按一下 [ **新增功能**]。</span><span class="sxs-lookup"><span data-stu-id="e7011-302">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="e7011-303">按一下 **安裝**。</span><span class="sxs-lookup"><span data-stu-id="e7011-303">Click **Install**.</span></span>
    
2. <span data-ttu-id="e7011-304">驗證叢集設定。</span><span class="sxs-lookup"><span data-stu-id="e7011-304">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="e7011-305">在 [伺服器管理員] 中，按一下 [ **工具** ] 功能表，然後按一下 [ **容錯移轉叢集管理員**]。</span><span class="sxs-lookup"><span data-stu-id="e7011-305">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="e7011-306">在螢幕右側的 [ **動作** ] 下，按一下 [ **驗證** 設定]。</span><span class="sxs-lookup"><span data-stu-id="e7011-306">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="e7011-307">在 **[開始之前]** 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-307">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="e7011-308">選取要新增至該群集中的伺服器，然後按一下 [ **執行所有測試**]。</span><span class="sxs-lookup"><span data-stu-id="e7011-308">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="e7011-309">在 [ **摘要** ] 方塊中，檢查嚮導所報告的任何錯誤。</span><span class="sxs-lookup"><span data-stu-id="e7011-309">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="e7011-310">然後按一下 **[完成]** 以完成驗證。</span><span class="sxs-lookup"><span data-stu-id="e7011-310">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="e7011-311">嚮導可能會報告數個警告，尤其是當您不是使用共用儲存區時。</span><span class="sxs-lookup"><span data-stu-id="e7011-311">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="e7011-312">您不需要使用共用儲存區。</span><span class="sxs-lookup"><span data-stu-id="e7011-312">You are not required to use shared storage.</span></span> <span data-ttu-id="e7011-313">不過，如果您看到任何 **錯誤** 訊息，您必須先修正這些問題，再繼續進行。</span><span class="sxs-lookup"><span data-stu-id="e7011-313">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="e7011-314">建立 Windows Server 容錯移轉叢集 (WSFC) 。</span><span class="sxs-lookup"><span data-stu-id="e7011-314">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="e7011-315">在 [ **容錯移轉叢集管理** ] 嚮導中，以滑鼠右鍵按一下 [ **容錯移轉叢集管理**]，然後按一下 [ **建立** 叢集]。</span><span class="sxs-lookup"><span data-stu-id="e7011-315">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="e7011-316">在 **[開始之前]** 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-316">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="e7011-317">新增群集名稱和 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="e7011-317">Add the cluster name and IP address.</span></span> <span data-ttu-id="e7011-318">驗證設定後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-318">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="e7011-319">在 [確認] 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-319">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="e7011-320">建立叢集後，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-320">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="e7011-321">建議您將叢集仲裁設定設定為使用檔案共用見證。</span><span class="sxs-lookup"><span data-stu-id="e7011-321">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="e7011-322">若要這麼做，請使用下列步驟：</span><span class="sxs-lookup"><span data-stu-id="e7011-322">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="e7011-323">以滑鼠右鍵按一下叢集名稱，按一下 [ **其他動作**]，然後按一下 [ **設定叢集仲裁設定**]。</span><span class="sxs-lookup"><span data-stu-id="e7011-323">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="e7011-324">在 [ **選取仲裁設定選項** ] 頁面上，按一下 **[選取仲裁見證**]。</span><span class="sxs-lookup"><span data-stu-id="e7011-324">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="e7011-325">在 [ **選取仲裁見證** ] 頁面上，按一下 [ **設定檔案共用見證**]。</span><span class="sxs-lookup"><span data-stu-id="e7011-325">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="e7011-326">在 [ **設定檔案共用見證** ] 頁面中，輸入您要使用的檔案共用路徑，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-326">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="e7011-327">在 [確認] 頁面上，按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="e7011-327">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="e7011-328">在該群集中的每一部伺服器上，于 SQL Server Configuration Manager 中啟用 AG。</span><span class="sxs-lookup"><span data-stu-id="e7011-328">On each server in the cluster, enable AG in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="e7011-329">開啟 SQL Server Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="e7011-329">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="e7011-330">在螢幕左側的樹狀目錄中，按一下 [ **Sql Server 服務**]，然後按兩下 [sql server 服務]。</span><span class="sxs-lookup"><span data-stu-id="e7011-330">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="e7011-331">在 [ **屬性** ] 方塊中，選取 [ **AlwaysOn 高可用性** ] 索引標籤。選取 [ **啟用 AlwaysOn 可用性群組** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e7011-331">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="e7011-332">出現提示時，請重新開機 SQL Server 服務。</span><span class="sxs-lookup"><span data-stu-id="e7011-332">Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="e7011-333">建立可用性群組。</span><span class="sxs-lookup"><span data-stu-id="e7011-333">Create the availability group.</span></span>
    
   - <span data-ttu-id="e7011-334">開啟 SQL Server Management Studio，並連接至 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="e7011-334">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="e7011-335">在 [物件瀏覽器] 中，展開 [ **永不增加高可用性** ] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="e7011-335">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="e7011-336">在 [ **可用性群組** ] 資料夾上按一下滑鼠右鍵，然後按一下 [ **新增可用性群組嚮導]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-336">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="e7011-337">如果出現 [ **簡介** ] 頁面，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-337">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="e7011-338">在 [ **指定可用性組名** ] 頁面中，輸入可用性群組的名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-338">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="e7011-339">在 [選取資料庫] 頁面中，選取您要包含在 AG 中的資料庫。</span><span class="sxs-lookup"><span data-stu-id="e7011-339">In the Select Databases page, select the databases that you want to include in the AG.</span></span> <span data-ttu-id="e7011-340">然後按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="e7011-340">Then click **Next**.</span></span>
    
     <span data-ttu-id="e7011-341">請勿在 AG 中包含 **ReportServer**、 **ReportServerTempDB** 或 Persistent 聊天資料庫，因為這種情況不會支援這些功能。</span><span class="sxs-lookup"><span data-stu-id="e7011-341">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AG, as these are not supported in this scenario.</span></span> <span data-ttu-id="e7011-342">您可以在 AG 中包含所有其他商務用 Skype Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="e7011-342">You can include all other Skype for Business Server databases in the AG.</span></span>
    
   - <span data-ttu-id="e7011-343">在 [ **指定複本** ] 頁面上，按一下 [ **複本** ] 索引標籤。然後按一下 [ **新增複製副本** ] 按鈕，並聯機至您加入為 WSFC 節點的其他 SQL 實例。</span><span class="sxs-lookup"><span data-stu-id="e7011-343">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the WSFC.</span></span>
    
   - <span data-ttu-id="e7011-344">針對每個實例，選取 [ **自動容錯移轉** ] 和 [ **同步認可** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="e7011-344">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="e7011-345">請勿選取 [ **可讀取的次要** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="e7011-345">Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="e7011-346">按一下 [ **端點** ] 索引標籤，並確認 **埠號碼** 設定為5022。</span><span class="sxs-lookup"><span data-stu-id="e7011-346">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="e7011-347">按一下 [ **監聽器** ] 索引標籤，然後選取 [ **建立可用性群組接聽程式** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="e7011-347">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="e7011-348">在 [此選項] 底下輸入監聽器的名稱，並將 **埠** 設定為 1433 (此選項) 不支援其他埠。</span><span class="sxs-lookup"><span data-stu-id="e7011-348">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="e7011-349">按一下 [ **新增**]，然後在 [ **IPv4 網址** ] 方塊中，提供您慣用的虛擬 IP 位址，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-349">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="e7011-350">在 [ **選取初始資料同步** 處理] 頁面中，選取 [完整]，並指定複本可存取的資料夾，而且這兩個複本所使用的 SQL Server 服務帳戶都具有寫入權限。</span><span class="sxs-lookup"><span data-stu-id="e7011-350">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="e7011-351">然後按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="e7011-351">Then click **Next**.</span></span>
    
     <span data-ttu-id="e7011-352">當您初始化資料庫時，會暫時使用此檔案共用。</span><span class="sxs-lookup"><span data-stu-id="e7011-352">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="e7011-353">如果您正在處理大型資料庫，建議您手動加以初始化，以防您的網路頻寬無法容納資料庫備份的大小。</span><span class="sxs-lookup"><span data-stu-id="e7011-353">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
     - <span data-ttu-id="e7011-354">在 [驗證] 頁面中，確認所有驗證檢查是否都成功，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-354">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="e7011-355">在 [ **摘要** ] 頁面中，確認所有設定，然後按一下 [完成]。</span><span class="sxs-lookup"><span data-stu-id="e7011-355">In the **Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="e7011-356">建立新的存放區，以指定 AG 偵聽程式。</span><span class="sxs-lookup"><span data-stu-id="e7011-356">Create a new store specifying the AG listener.</span></span>
    
   - <span data-ttu-id="e7011-357">開啟拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="e7011-357">Open Topology Builder.</span></span> <span data-ttu-id="e7011-358">在拓撲中，展開 [ **共用元件**]，以滑鼠右鍵按一下 **[sql server** 存放區]，然後按一下 **[新增 sql server 儲存區**]。</span><span class="sxs-lookup"><span data-stu-id="e7011-358">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
   - <span data-ttu-id="e7011-359">在 [ **定義新的 SQL 存放區** ] 頁面中，先選取 [ **高可用性設定** ] 核取方塊，然後確定 [SQL AlwaysOn 可用性群組會出現在下拉式方塊中。</span><span class="sxs-lookup"><span data-stu-id="e7011-359">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
   - <span data-ttu-id="e7011-360">在 [ **SQL Server 可用性接聽程式 FQDN]** 方塊中，輸入您在建立可用性群組時所建立的攔截器 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e7011-360">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
   - <span data-ttu-id="e7011-361">在 [ **SQL SERVER FQDN** ] 方塊中，輸入 AG 的主要節點的 FQDN，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-361">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span>
    
8. <span data-ttu-id="e7011-362">將新的 Always On 可用性群組與前端集區產生關聯。</span><span class="sxs-lookup"><span data-stu-id="e7011-362">Associate the new Always On Availability Group with the Front End pool.</span></span>
    
   - <span data-ttu-id="e7011-363">在 [拓撲產生器] 中，以滑鼠右鍵按一下要與 AG 產生關聯的集區，然後按一下 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="e7011-363">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="e7011-364">在 [ **關聯**] 底下，選取 [ **SQL Server 存放區** ] 方塊中的 AG。</span><span class="sxs-lookup"><span data-stu-id="e7011-364">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="e7011-365">針對您要移至 AG 的集區中的任何其他資料庫，選取相同的群組。</span><span class="sxs-lookup"><span data-stu-id="e7011-365">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
   - <span data-ttu-id="e7011-366">當您確定所有必要的資料庫都設定為 AG 時，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-366">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
9. <span data-ttu-id="e7011-367">發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="e7011-367">Publish the topology.</span></span> <span data-ttu-id="e7011-368">從 [ **動作** ] 功能表中，按一下 [ **拓撲** ]，然後再 **發佈**。</span><span class="sxs-lookup"><span data-stu-id="e7011-368">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="e7011-369">然後在 [確認] 頁面中按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-369">Then in the confirmation page click **Next**.</span></span>
    
10. <span data-ttu-id="e7011-370">請執行一些最後的步驟，確定在 AG 中的每個複本上都有 SQL 登入。</span><span class="sxs-lookup"><span data-stu-id="e7011-370">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AG.</span></span>
    
    - <span data-ttu-id="e7011-371">開啟拓撲產生器，選取 [ **從現有的部署下載拓撲**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-371">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="e7011-372">展開 [商務用 Skype 伺服器]，展開您的拓撲，然後展開 **[SQL Server 儲存區**]。</span><span class="sxs-lookup"><span data-stu-id="e7011-372">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="e7011-373">以滑鼠右鍵按一下新 AG 的 SQL 存放區，然後按一下 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="e7011-373">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="e7011-374">在頁面底部的 [ **SQL SERVER FQDN** ] 方塊中，將值變更為 AG 的攔截器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e7011-374">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="e7011-375">發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="e7011-375">Publish the topology.</span></span> <span data-ttu-id="e7011-376">從 [ **動作** ] 功能表中，按一下 [ **拓撲** ]，然後再 **發佈**。</span><span class="sxs-lookup"><span data-stu-id="e7011-376">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="e7011-377">然後在 [確認] 頁面中按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e7011-377">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="e7011-378">然後，請稍候幾分鐘，以複製新的拓撲。</span><span class="sxs-lookup"><span data-stu-id="e7011-378">Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="e7011-379">開啟 SQL Server Management Studio，並流覽至 AG。</span><span class="sxs-lookup"><span data-stu-id="e7011-379">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="e7011-380">將其容錯移轉至次要複本。</span><span class="sxs-lookup"><span data-stu-id="e7011-380">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="e7011-381">開啟商務用 Skype Server 管理命令介面，並輸入下列 Cmdlet，以在此複本上建立 SQL 登入：</span><span class="sxs-lookup"><span data-stu-id="e7011-381">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
      ```powershell
      Install-CsDatabase -Update
      ```

      - <span data-ttu-id="e7011-382">重複執行先前的兩個步驟 (將群組容錯移轉至次要複本，然後  `Install-CsDatabase -Update` 針對群組中的每個複本使用) 。</span><span class="sxs-lookup"><span data-stu-id="e7011-382">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
