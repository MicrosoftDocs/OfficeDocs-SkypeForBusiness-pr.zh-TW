---
title: 在商務用 Skype Server 的後端伺服器上部署 Alwayson 可用性群組
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: 在商務用 Skype Server 部署中部署（安裝） [Alwayson 可用性] 群組。
ms.openlocfilehash: d69e370716af2b23c57ad463ea7f4651ea0ea89a
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798270"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a><span data-ttu-id="d5e95-103">在商務用 Skype Server 的後端伺服器上部署 Alwayson 可用性群組</span><span class="sxs-lookup"><span data-stu-id="d5e95-103">Deploy an Always On Availability Group on a Back End Server in Skype for Business Server</span></span>
 
<span data-ttu-id="d5e95-104">在商務用 Skype Server 部署中部署（安裝） [Alwayson 可用性] 群組（AG）。</span><span class="sxs-lookup"><span data-stu-id="d5e95-104">Deploy (install) an Always On Availability Group (AG) in your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="d5e95-105">您部署 AG 的方式取決於您是要將它部署在新的池中、使用鏡像的現有池，或是目前沒有後端資料庫高可用性的現有池。</span><span class="sxs-lookup"><span data-stu-id="d5e95-105">How you deploy an AG depends on whether you are deploying it in a new pool, an existing pool that uses mirroring, or an existing pool that currently has no high availability for the Back End database.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d5e95-106">不支援將 AG 與持續聊天伺服器角色一起使用。</span><span class="sxs-lookup"><span data-stu-id="d5e95-106">Using an AG with a Persistent Chat Server role is not supported.</span></span> 
  
- [<span data-ttu-id="d5e95-107">在新的前端池中部署 Alwayson 可用性群組</span><span class="sxs-lookup"><span data-stu-id="d5e95-107">Deploy an Always On Availability Group on a new Front End pool</span></span>](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="d5e95-108">在使用資料庫鏡像的現有資料庫池中部署 Alwayson 可用性群組</span><span class="sxs-lookup"><span data-stu-id="d5e95-108">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="d5e95-109">在不使用資料庫鏡像的現有池上部署 Alwayson 可用性群組</span><span class="sxs-lookup"><span data-stu-id="d5e95-109">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a><span data-ttu-id="d5e95-110">在新的前端池中部署 Alwayson 可用性群組</span><span class="sxs-lookup"><span data-stu-id="d5e95-110">Deploy an Always On Availability Group on a new Front End pool</span></span>
<span data-ttu-id="d5e95-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="d5e95-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span></span>

1. <span data-ttu-id="d5e95-112">在將成為 AG 一部分的所有資料庫伺服器上，啟用 [容錯移轉叢集] 功能。</span><span class="sxs-lookup"><span data-stu-id="d5e95-112">Enable the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="d5e95-113">在每個伺服器上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="d5e95-113">On each server, do the following</span></span>
    
   - <span data-ttu-id="d5e95-114">開啟 [伺服器管理員]，然後按一下 [**新增角色和功能**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-114">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="d5e95-115">按一下 **[下一步]** ，直到您到達 [**選取功能**] 方塊為止。</span><span class="sxs-lookup"><span data-stu-id="d5e95-115">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="d5e95-116">在這裡，選取 [**容錯移轉叢集**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d5e95-116">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="d5e95-117">在 [**新增容錯移轉叢集所需的功能？** ] 方塊中，按一下 [**新增功能**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-117">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="d5e95-118">按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-118">Click **Install**.</span></span>
    
2. <span data-ttu-id="d5e95-119">驗證群集設定。</span><span class="sxs-lookup"><span data-stu-id="d5e95-119">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="d5e95-120">在 [伺服器管理員] 中，按一下 [**工具**] 功能表，然後按一下 [**容錯移轉叢集管理器**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-120">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="d5e95-121">在畫面右側的 [**動作**] 底下，按一下 [**驗證配置**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-121">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="d5e95-122">在 [**開始之前**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-122">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="d5e95-123">選取要新增至群集的伺服器，然後按一下 [**執行所有測試**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-123">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="d5e95-124">在 [**摘要**] 方塊中，檢查嚮導所報告的任何錯誤。</span><span class="sxs-lookup"><span data-stu-id="d5e95-124">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="d5e95-125">然後按一下 **[完成]** 以完成驗證。</span><span class="sxs-lookup"><span data-stu-id="d5e95-125">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="d5e95-126">此嚮導可能會報告幾個警告，特別是如果您不是使用共用儲存空間。</span><span class="sxs-lookup"><span data-stu-id="d5e95-126">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="d5e95-127">您不需要使用共用儲存空間。</span><span class="sxs-lookup"><span data-stu-id="d5e95-127">You are not required to use shared storage.</span></span> <span data-ttu-id="d5e95-128">不過，如果您看到任何**錯誤**訊息，您必須先修正這些問題，然後才能繼續進行。</span><span class="sxs-lookup"><span data-stu-id="d5e95-128">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="d5e95-129">建立 Windows Server 容錯移轉叢集（WSFC）。</span><span class="sxs-lookup"><span data-stu-id="d5e95-129">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="d5e95-130">在 [**容錯移轉叢集管理**] 嚮導中，以滑鼠右鍵按一下 [**容錯移轉叢集管理**]，然後按一下 [**建立群集**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-130">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="d5e95-131">在 [**開始之前**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-131">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="d5e95-132">新增 [群集名稱] 和 [IP 位址]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-132">Add the cluster name and IP address.</span></span> <span data-ttu-id="d5e95-133">驗證設定後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-133">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="d5e95-134">在確認頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-134">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="d5e95-135">建立群集之後，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-135">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="d5e95-136">我們建議您將群集仲裁設定設定為使用檔案共用見證。</span><span class="sxs-lookup"><span data-stu-id="d5e95-136">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="d5e95-137">若要這樣做，請使用下列步驟：</span><span class="sxs-lookup"><span data-stu-id="d5e95-137">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="d5e95-138">以滑鼠右鍵按一下群集名稱，按一下 [**其他動作**]，然後按一下 [**設定群集仲裁設定**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-138">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="d5e95-139">在 [**選取仲裁**設定] 選項頁面上，按一下 [**選取仲裁見證**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-139">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="d5e95-140">在 [**選取仲裁見證**] 頁面上，按一下 [**設定檔案共用見證**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-140">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="d5e95-141">在 [**設定檔案共用見證**] 頁面上，輸入您要使用的檔案共用路徑，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-141">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="d5e95-142">在**確認**頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-142">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="d5e95-143">在群集中的每個伺服器上，在 [SQL Server Configuration Manager] 中啟用 AG 功能。</span><span class="sxs-lookup"><span data-stu-id="d5e95-143">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="d5e95-144">開啟 [SQL Server Configuration Manager]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-144">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="d5e95-145">在畫面左側的樹狀結構中，按一下 [ **Sql Server 服務**]，然後按兩下 [sql server 服務]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-145">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="d5e95-146">在 [**屬性**] 方塊中，選取 [ **alwayson**可用性] 索引標籤。選取 [**啟用 AlwaysOn 可用性群組**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d5e95-146">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="d5e95-147">出現提示時，請重新開機 SQL Server 服務。</span><span class="sxs-lookup"><span data-stu-id="d5e95-147">Restart the SQL Server service when prompted.</span></span>
   
6. <span data-ttu-id="d5e95-148">使用 [拓撲建立器] 來建立 [前端] 池，如在[商務用 Skype Server 中建立和發佈新拓撲中](../../deploy/install/create-and-publish-new-topology.md)所述。</span><span class="sxs-lookup"><span data-stu-id="d5e95-148">Use Topology Builder to create the Front End pool, as explained in [Create and publish new topology in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md).</span></span> <span data-ttu-id="d5e95-149">當您這麼做時，請將 AG 指定為池子的 SQL store。</span><span class="sxs-lookup"><span data-stu-id="d5e95-149">When you do, specify the AG as the SQL store for the pool.</span></span>
    
7. <span data-ttu-id="d5e95-150">建立 [可用性] 群組。</span><span class="sxs-lookup"><span data-stu-id="d5e95-150">Create the availability group.</span></span>
    
   - <span data-ttu-id="d5e95-151">開啟 [SQL Server Management Studio]，然後連線到 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="d5e95-151">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="d5e95-152">在物件資源管理器中，展開 [**永不在高可用性**] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="d5e95-152">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="d5e95-153">以滑鼠右鍵按一下 [**可用性群組**] 資料夾，然後按一下 [**新增可用性群組嚮導]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-153">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="d5e95-154">如果出現 [**簡介**] 頁面，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-154">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="d5e95-155">在 [**指定可用性群組名稱**] 頁面上，輸入可用性群組的名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-155">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="d5e95-156">在 [選取資料庫] 頁面中，選取您要包含在 [AlwaysOn 可用性] 群組中的資料庫。</span><span class="sxs-lookup"><span data-stu-id="d5e95-156">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="d5e95-157">然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-157">Then click **Next**.</span></span>
    
     <span data-ttu-id="d5e95-158">請勿在 [AlwaysOn 可用性] 群組中包含**ReportServer**、 **ReportServerTempDB**或持久聊天資料庫，因為這種情況不支援這些專案。</span><span class="sxs-lookup"><span data-stu-id="d5e95-158">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="d5e95-159">您可以在 [AlwaysOn 可用性] 群組中包含所有其他商務用 Skype 伺服器資料庫。</span><span class="sxs-lookup"><span data-stu-id="d5e95-159">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="d5e95-160">在 [**指定複本**] 頁面上，按一下 [**複本**] 索引標籤。然後按一下 [**新增複本**] 按鈕，並聯機到您加入為 Windows Server 容錯移轉叢集節點的其他 SQL 實例。</span><span class="sxs-lookup"><span data-stu-id="d5e95-160">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="d5e95-161">針對每個實例，選取 [**自動容錯移轉**] 和 [**同步提交**] 選項。</span><span class="sxs-lookup"><span data-stu-id="d5e95-161">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="d5e95-162">請勿選取 [**可讀的次要**] 選項。</span><span class="sxs-lookup"><span data-stu-id="d5e95-162">Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="d5e95-163">按一下 [**端點**] 索引標籤，並確認 [**埠號碼**] 設定為 [5022]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-163">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="d5e95-164">按一下 [**攔截器**] 索引標籤，然後選取 [**建立可用性群組偵聽程式]** 選項。</span><span class="sxs-lookup"><span data-stu-id="d5e95-164">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="d5e95-165">在 [該選項] 底下，輸入監聽器的名稱，並將**埠**設定為1433（此選項不支援其他埠）。</span><span class="sxs-lookup"><span data-stu-id="d5e95-165">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="d5e95-166">按一下 [**新增**]，然後在 [ **IPv4 位址**] 方塊中，提供您慣用的虛擬 IP 位址，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-166">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="d5e95-167">在 [**選取初始資料同步**處理] 頁面中，選取 [完整]，並指定複本可存取的資料夾，且兩個複本所使用的 SQL Server 服務帳戶都具有寫入權限。</span><span class="sxs-lookup"><span data-stu-id="d5e95-167">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="d5e95-168">然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-168">Then click **Next**.</span></span>
    
     <span data-ttu-id="d5e95-169">此檔案共用將在您初始化資料庫時暫時使用。</span><span class="sxs-lookup"><span data-stu-id="d5e95-169">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="d5e95-170">如果您正在處理大型資料庫，建議您手動初始化這些資料庫，以防您的網路頻寬無法容納資料庫備份的大小。</span><span class="sxs-lookup"><span data-stu-id="d5e95-170">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
   - <span data-ttu-id="d5e95-171">在驗證頁面中，確認所有驗證檢查都已成功完成，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-171">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="d5e95-172">在 [**摘要**] 頁面中，確認所有設定，然後按一下 [完成]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-172">In the **Summary** page, verify all settings and click Finish.</span></span>
      
8. <span data-ttu-id="d5e95-173">在已部署池和 AG 之後，請執行一些最終步驟，以確保 [AlwaysOn 可用性] 群組中的每個副本都有這些 SQL 登錄。</span><span class="sxs-lookup"><span data-stu-id="d5e95-173">After the pool and the AG are deployed, perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span> 
    
   - <span data-ttu-id="d5e95-174">開啟拓撲建立器，選取 [**從現有部署下載拓撲**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-174">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="d5e95-175">展開 [商務用 Skype 伺服器]、展開您的拓撲，然後展開 **[SQL Server 存放區**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-175">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="d5e95-176">以滑鼠右鍵按一下新 [AlwaysOn 可用性] 群組的 SQL 存放區，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-176">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
     - <span data-ttu-id="d5e95-177">在頁面底部的 [ **SQL SERVER FQDN** ] 方塊中，將值變更為 AG 監聽程式的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d5e95-177">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
   - <span data-ttu-id="d5e95-178">發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="d5e95-178">Publish the topology.</span></span> <span data-ttu-id="d5e95-179">從 [**動作**] 功能表按一下 [**拓撲**]，然後按一下 [**發佈**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-179">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="d5e95-180">然後在確認頁面中，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-180">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="d5e95-181">然後稍等幾分鐘，即可複製新的拓撲。</span><span class="sxs-lookup"><span data-stu-id="d5e95-181">Then wait a few minutes for the new topology to replicate.</span></span>
    
   - <span data-ttu-id="d5e95-182">開啟 SQL Server Management Studio，然後流覽到 AG。</span><span class="sxs-lookup"><span data-stu-id="d5e95-182">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="d5e95-183">將它容錯移轉到副複本。</span><span class="sxs-lookup"><span data-stu-id="d5e95-183">Fail it over to a secondary replica.</span></span>
    
   - <span data-ttu-id="d5e95-184">開啟商務用 Skype Server 管理命令介面，然後輸入下列 Cmdlet，以在此複製副本上建立 SQL 登錄：</span><span class="sxs-lookup"><span data-stu-id="d5e95-184">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
   ```powershell
   Install-CsDatabase -Update
   ```

   - <span data-ttu-id="d5e95-185">針對群組中的每個複本重複上述兩個步驟（將群組容錯移轉`Install-CsDatabase -Update`至次要複本，然後使用）。</span><span class="sxs-lookup"><span data-stu-id="d5e95-185">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a><span data-ttu-id="d5e95-186">在使用資料庫鏡像的現有資料庫池中部署 Alwayson 可用性群組</span><span class="sxs-lookup"><span data-stu-id="d5e95-186">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>
<span data-ttu-id="d5e95-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="d5e95-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="d5e95-188">如果您要升級到 AG 的池是貴組織的中央管理商店，您必須先將 CMS 移到另一個池中，才能升級此池。</span><span class="sxs-lookup"><span data-stu-id="d5e95-188">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="d5e95-189">使用 CsManagementServer Cmdlet 來移動池。</span><span class="sxs-lookup"><span data-stu-id="d5e95-189">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="d5e95-190">如果您的組織沒有另一個池，您可以暫時部署標準版伺服器，並將 CMS 移至此伺服器，然後再將您的池升級至 AG。</span><span class="sxs-lookup"><span data-stu-id="d5e95-190">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="d5e95-191">您可以開啟商務用 Skype Server 管理命令介面並輸入下列 Cmdlet，以將所有資料從鏡像轉移到主要節點。</span><span class="sxs-lookup"><span data-stu-id="d5e95-191">Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.</span></span>
    
   ```powershell
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    <span data-ttu-id="d5e95-192">針對池中的每個資料庫類型，重複這個 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d5e95-192">Repeat this cmdlet for each database type in the pool.</span></span> <span data-ttu-id="d5e95-193">您可以使用下列 Cmdlet 來尋找此池中儲存的所有資料庫類型。</span><span class="sxs-lookup"><span data-stu-id="d5e95-193">You can use the following cmdlet to find all the database types stored in this pool.</span></span>
     
   ```powershell
   Get-CsPool -Identity <Pool FQDN>
   ```

2. <span data-ttu-id="d5e95-194">使用拓撲產生器從池中移除資料庫鏡像。</span><span class="sxs-lookup"><span data-stu-id="d5e95-194">Use Topology Builder to remove database mirroring from the pool.</span></span>
    
   - <span data-ttu-id="d5e95-195">開啟拓撲建立器。</span><span class="sxs-lookup"><span data-stu-id="d5e95-195">Open Topology Builder.</span></span> <span data-ttu-id="d5e95-196">在您的拓撲中，展開 [**企業版前端池**]，以滑鼠右鍵按一下該池子的名稱，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-196">In your topology, expand **Enterprise Edition Front End Pools**, right-click the name of the pool, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="d5e95-197">針對池中的每個 SQL store 類型，清除 [**啟用 SQL Store 鏡像**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d5e95-197">For each type of SQL store in the pool, clear the **Enable SQL Store Mirroring** check box.</span></span>
    
3. <span data-ttu-id="d5e95-198">發佈變更的拓撲。</span><span class="sxs-lookup"><span data-stu-id="d5e95-198">Publish the changed topology.</span></span> <span data-ttu-id="d5e95-199">從 [**動作**] 功能表按一下 [**拓撲**]，然後按一下 [**發佈**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-199">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="d5e95-200">然後在確認頁面中，按一下 **[下一步]**</span><span class="sxs-lookup"><span data-stu-id="d5e95-200">Then in the confirmation page click **Next**</span></span>
    
4. <span data-ttu-id="d5e95-201">使用 SQL Server Management Studio 來中斷鏡像。</span><span class="sxs-lookup"><span data-stu-id="d5e95-201">Use SQL Server Management Studio to break the mirror.</span></span>
    
   - <span data-ttu-id="d5e95-202">開啟 SQL Server Management Studio，流覽至您的資料庫，以滑鼠右鍵按一下 [工作] **，然後按一下**[**鏡像**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-202">Open SQL Server Management Studio, navigate to your databases, right-click **Tasks** and click **Mirror**.</span></span> <span data-ttu-id="d5e95-203">然後按一下 [**移除鏡像**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-203">Then click **Remove Mirroring** and click **OK**.</span></span>
    
   - <span data-ttu-id="d5e95-204">針對要轉換為 AG 的池中的所有資料庫重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="d5e95-204">Repeat this for all databases in the pool which will be converted to an AG.</span></span>
    
5. <span data-ttu-id="d5e95-205">在所有要納入 AG 的資料庫伺服器上設定 [容錯移轉叢集] 功能。</span><span class="sxs-lookup"><span data-stu-id="d5e95-205">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="d5e95-206">在每個伺服器上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="d5e95-206">On each server, do the following</span></span>
    
   - <span data-ttu-id="d5e95-207">開啟 [伺服器管理員]，然後按一下 [**新增角色和功能**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-207">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="d5e95-208">按一下 **[下一步]** ，直到您到達 [**選取功能**] 方塊為止。</span><span class="sxs-lookup"><span data-stu-id="d5e95-208">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="d5e95-209">在這裡，選取 [**容錯移轉叢集**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d5e95-209">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="d5e95-210">在 [**新增容錯移轉叢集所需的功能？** ] 方塊中，按一下 [**新增功能**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-210">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="d5e95-211">按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-211">Click **Install**.</span></span>
    
6. <span data-ttu-id="d5e95-212">驗證群集設定。</span><span class="sxs-lookup"><span data-stu-id="d5e95-212">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="d5e95-213">在 [伺服器管理員] 中，按一下 [**工具**] 功能表，然後按一下 [**容錯移轉叢集管理器**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-213">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="d5e95-214">在畫面右側的 [**動作**] 底下，按一下 [**驗證配置**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-214">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="d5e95-215">在 [**開始之前**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-215">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="d5e95-216">選取要新增至群集的伺服器，然後按一下 [**執行所有測試**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-216">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="d5e95-217">在 [**摘要**] 方塊中，檢查嚮導所報告的任何錯誤。</span><span class="sxs-lookup"><span data-stu-id="d5e95-217">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="d5e95-218">然後按一下 **[完成]** 以完成驗證。</span><span class="sxs-lookup"><span data-stu-id="d5e95-218">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="d5e95-219">此嚮導可能會報告幾個警告，特別是如果您不是使用共用儲存空間。</span><span class="sxs-lookup"><span data-stu-id="d5e95-219">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="d5e95-220">您不需要使用共用儲存空間。</span><span class="sxs-lookup"><span data-stu-id="d5e95-220">You are not required to use shared storage.</span></span> <span data-ttu-id="d5e95-221">不過，如果您看到任何**錯誤**訊息，您必須先修正這些問題，然後才能繼續進行。</span><span class="sxs-lookup"><span data-stu-id="d5e95-221">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
7. <span data-ttu-id="d5e95-222">建立 Windows Server 容錯移轉叢集。</span><span class="sxs-lookup"><span data-stu-id="d5e95-222">Create the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="d5e95-223">在 [**容錯移轉叢集管理**] 嚮導中，以滑鼠右鍵按一下 [**容錯移轉叢集管理**]，然後按一下 [**建立群集**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-223">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="d5e95-224">在 [**開始之前**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-224">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="d5e95-225">新增 [群集名稱] 和 [IP 位址]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-225">Add the cluster name and IP address.</span></span> <span data-ttu-id="d5e95-226">驗證設定後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-226">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="d5e95-227">在確認頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-227">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="d5e95-228">建立群集之後，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-228">After the cluster is created, click **Finish**.</span></span>
    
8. <span data-ttu-id="d5e95-229">我們建議您將群集仲裁設定設定為使用檔案共用見證。</span><span class="sxs-lookup"><span data-stu-id="d5e95-229">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="d5e95-230">若要這樣做，請使用下列步驟：</span><span class="sxs-lookup"><span data-stu-id="d5e95-230">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="d5e95-231">以滑鼠右鍵按一下群集名稱，按一下 [**其他動作**]，然後按一下 [**設定群集仲裁設定**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-231">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="d5e95-232">在 [**選取仲裁**設定] 選項頁面上，按一下 [**選取仲裁見證**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-232">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="d5e95-233">在 [**選取仲裁見證**] 頁面上，按一下 [**設定檔案共用見證**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-233">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="d5e95-234">在 [**設定檔案共用見證**] 頁面上，輸入您要使用的檔案共用路徑，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-234">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="d5e95-235">在**確認**頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-235">On the **Confirmation** page, click **Next**.</span></span>
    
9. <span data-ttu-id="d5e95-236">在群集中的每個伺服器上，在 [SQL Server Configuration Manager] 中啟用 AG 功能。</span><span class="sxs-lookup"><span data-stu-id="d5e95-236">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="d5e95-237">開啟 [SQL Server Configuration Manager]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-237">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="d5e95-238">在畫面左側的樹狀結構中，按一下 [ **Sql Server 服務**]，然後按兩下 [sql server 服務]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-238">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="d5e95-239">在 [**屬性**] 方塊中，選取 [ **alwayson**可用性] 索引標籤。選取 [**啟用 AlwaysOn 可用性群組**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d5e95-239">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="d5e95-240">出現提示時，請重新開機 SQL Server 服務。</span><span class="sxs-lookup"><span data-stu-id="d5e95-240">Restart the SQL Server service when prompted.</span></span>
    
10. <span data-ttu-id="d5e95-241">建立 [可用性] 群組。</span><span class="sxs-lookup"><span data-stu-id="d5e95-241">Create the availability group.</span></span>
    
    - <span data-ttu-id="d5e95-242">開啟 [SQL Server Management Studio]，然後連線到 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="d5e95-242">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
    - <span data-ttu-id="d5e95-243">在物件資源管理器中，展開 [**永不在高可用性**] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="d5e95-243">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="d5e95-244">以滑鼠右鍵按一下 [**可用性群組**] 資料夾，然後按一下 [**新增可用性群組嚮導]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-244">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
    - <span data-ttu-id="d5e95-245">如果出現 [**簡介**] 頁面，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-245">If the **Introduction** page appears, click **Next**.</span></span>
    
    - <span data-ttu-id="d5e95-246">在 [**指定可用性群組名稱**] 頁面上，輸入可用性群組的名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-246">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
    - <span data-ttu-id="d5e95-247">在 [選取資料庫] 頁面中，選取您要包含在 [AlwaysOn 可用性] 群組中的資料庫。</span><span class="sxs-lookup"><span data-stu-id="d5e95-247">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="d5e95-248">然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-248">Then click **Next**.</span></span>
    
    <span data-ttu-id="d5e95-249">請勿在 [AlwaysOn 可用性] 群組中包含**ReportServer**、 **ReportServerTempDB**或持久聊天資料庫，因為這種情況不支援這些專案。</span><span class="sxs-lookup"><span data-stu-id="d5e95-249">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="d5e95-250">您可以在 [AlwaysOn 可用性] 群組中包含所有其他商務用 Skype 伺服器資料庫。</span><span class="sxs-lookup"><span data-stu-id="d5e95-250">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="d5e95-251">在 [**指定複本**] 頁面上，按一下 [**複本**] 索引標籤。然後按一下 [**新增複本**] 按鈕，並聯機到您加入為 Windows Server 容錯移轉叢集節點的其他 SQL 實例。</span><span class="sxs-lookup"><span data-stu-id="d5e95-251">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
    - <span data-ttu-id="d5e95-252">針對每個實例，選取 [**自動容錯移轉**] 和 [**同步提交**] 選項。</span><span class="sxs-lookup"><span data-stu-id="d5e95-252">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="d5e95-253">請勿選取 [**可讀的次要**] 選項。</span><span class="sxs-lookup"><span data-stu-id="d5e95-253">Do not select the **Readable Secondary** option.</span></span>
    
    - <span data-ttu-id="d5e95-254">按一下 [**端點**] 索引標籤，並確認 [**埠號碼**] 設定為 [5022]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-254">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
      - <span data-ttu-id="d5e95-255">按一下 [**攔截器**] 索引標籤，然後選取 [**建立可用性群組偵聽程式]** 選項。</span><span class="sxs-lookup"><span data-stu-id="d5e95-255">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="d5e95-256">在 [該選項] 底下，輸入監聽器的名稱，並將**埠**設定為1433（此選項不支援其他埠）。</span><span class="sxs-lookup"><span data-stu-id="d5e95-256">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
    - <span data-ttu-id="d5e95-257">按一下 [**新增**]，然後在 [ **IPv4 位址**] 方塊中，提供您慣用的虛擬 IP 位址，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-257">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
    - <span data-ttu-id="d5e95-258">在 [**選取初始資料同步**處理] 頁面中，選取 [完整]，並指定複本可存取的資料夾，且兩個複本所使用的 SQL Server 服務帳戶都具有寫入權限。</span><span class="sxs-lookup"><span data-stu-id="d5e95-258">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="d5e95-259">然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-259">Then click **Next**.</span></span>
    
    <span data-ttu-id="d5e95-260">此檔案共用將在您初始化資料庫時暫時使用。</span><span class="sxs-lookup"><span data-stu-id="d5e95-260">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="d5e95-261">如果您正在處理大型資料庫，建議您手動初始化這些資料庫，以防您的網路頻寬無法容納資料庫備份的大小。</span><span class="sxs-lookup"><span data-stu-id="d5e95-261">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="d5e95-262">在驗證頁面中，確認所有驗證檢查都已成功完成，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-262">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
    - <span data-ttu-id="d5e95-263">在 [**摘要**] 頁面中，確認所有設定，然後按一下 [完成]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-263">In the **Summary** page, verify all settings and click Finish.</span></span>
    
11. <span data-ttu-id="d5e95-264">建立新的市集中指定 AG 偵聽程式，並將舊鏡像的主體指定為 AG 的主要節點。</span><span class="sxs-lookup"><span data-stu-id="d5e95-264">Create a new store specifying the AG listener, and specifying the principal of the old mirror as the primary node of the AG.</span></span>
    
    - <span data-ttu-id="d5e95-265">開啟拓撲建立器。</span><span class="sxs-lookup"><span data-stu-id="d5e95-265">Open Topology Builder.</span></span> <span data-ttu-id="d5e95-266">在您的拓撲中，展開 [**共用元件**]，以滑鼠右鍵按一下 **[sql server**Store]，然後按一下 [**新增 sql server Store**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-266">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
    - <span data-ttu-id="d5e95-267">在 [**定義新的 SQL Store** ] 頁面中，先選取 [**高可用性設定**] 核取方塊，然後確認 [SQL AlwaysOn 可用性群組] 出現在下拉式方塊中。</span><span class="sxs-lookup"><span data-stu-id="d5e95-267">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
    - <span data-ttu-id="d5e95-268">在 [ **SQL Server 可用性偵聽程式 FQDN]** 方塊中，輸入您在建立可用性群組時所建立之監聽程式的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d5e95-268">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
    - <span data-ttu-id="d5e95-269">在 [ **SQL SERVER FQDN** ] 方塊中，輸入 AG 主要節點的 FQDN，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-269">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span> <span data-ttu-id="d5e95-270">這應該是此存放區之舊鏡像的主體。</span><span class="sxs-lookup"><span data-stu-id="d5e95-270">This should be the principal of the old mirror for this store.</span></span>
    
12. <span data-ttu-id="d5e95-271">將新的 AG 與前端池建立關聯。</span><span class="sxs-lookup"><span data-stu-id="d5e95-271">Associate the new AG with the Front End pool.</span></span>
    
    - <span data-ttu-id="d5e95-272">在拓撲建立器中，以滑鼠右鍵按一下要與 AG 關聯的 [泳池]，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-272">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="d5e95-273">在 [**關聯**性] 底下的 [ **SQL Server 存放區**] 方塊中，選取 AG。</span><span class="sxs-lookup"><span data-stu-id="d5e95-273">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="d5e95-274">針對您要移至 AG 的池中的任何其他資料庫，選取相同的群組。</span><span class="sxs-lookup"><span data-stu-id="d5e95-274">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
    - <span data-ttu-id="d5e95-275">當您確定所需的所有資料庫都設定為 AG 時，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-275">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
13. <span data-ttu-id="d5e95-276">發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="d5e95-276">Publish the topology.</span></span> <span data-ttu-id="d5e95-277">從 [**動作**] 功能表按一下 [**拓撲**]，然後按一下 [**發佈**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-277">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="d5e95-278">然後在確認頁面中，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-278">Then in the confirmation page click **Next**.</span></span>
    
14. <span data-ttu-id="d5e95-279">執行一些最終步驟，以確保 [AlwaysOn 可用性] 群組中的每個副本都有這些 SQL 登錄。</span><span class="sxs-lookup"><span data-stu-id="d5e95-279">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="d5e95-280">開啟拓撲建立器，選取 [**從現有部署下載拓撲**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-280">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="d5e95-281">展開 [商務用 Skype 伺服器]、展開您的拓撲，然後展開 **[SQL Server 存放區**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-281">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="d5e95-282">以滑鼠右鍵按一下新 AG 的 [SQL] 商店，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-282">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="d5e95-283">在頁面底部的 [ **SQL SERVER FQDN** ] 方塊中，將值變更為 AG 監聽程式的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d5e95-283">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="d5e95-284">發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="d5e95-284">Publish the topology.</span></span> <span data-ttu-id="d5e95-285">從 [**動作**] 功能表按一下 [**拓撲**]，然後按一下 [**發佈**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-285">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="d5e95-286">然後在確認頁面中，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-286">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="d5e95-287">然後稍等幾分鐘，即可複製新的拓撲。</span><span class="sxs-lookup"><span data-stu-id="d5e95-287">Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="d5e95-288">開啟 SQL Server Management Studio，然後流覽到 AG。</span><span class="sxs-lookup"><span data-stu-id="d5e95-288">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="d5e95-289">將它容錯移轉到副複本。</span><span class="sxs-lookup"><span data-stu-id="d5e95-289">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="d5e95-290">開啟商務用 Skype Server 管理命令介面，然後輸入下列 Cmdlet，以在此複製副本上建立 SQL 登錄：</span><span class="sxs-lookup"><span data-stu-id="d5e95-290">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
    ```powershell
    Install-CsDatabase -Update
    ```

    - <span data-ttu-id="d5e95-291">針對群組中的每個複本重複上述兩個步驟（將群組容錯移轉`Install-CsDatabase -Update`至次要複本，然後使用）。</span><span class="sxs-lookup"><span data-stu-id="d5e95-291">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a><span data-ttu-id="d5e95-292">在不使用資料庫鏡像的現有池上部署 Alwayson 可用性群組</span><span class="sxs-lookup"><span data-stu-id="d5e95-292">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>
<span data-ttu-id="d5e95-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="d5e95-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="d5e95-294">如果您要升級到 AG 的池是貴組織的中央管理商店，您必須先將 CMS 移到另一個池中，才能升級此池。</span><span class="sxs-lookup"><span data-stu-id="d5e95-294">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="d5e95-295">使用 CsManagementServer Cmdlet 來移動池。</span><span class="sxs-lookup"><span data-stu-id="d5e95-295">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="d5e95-296">如果您的組織沒有另一個池，您可以暫時部署標準版伺服器，並將 CMS 移至此伺服器，然後再將您的池升級至 AG。</span><span class="sxs-lookup"><span data-stu-id="d5e95-296">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="d5e95-297">在所有要納入 AG 的資料庫伺服器上設定 [容錯移轉叢集] 功能。</span><span class="sxs-lookup"><span data-stu-id="d5e95-297">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="d5e95-298">在每個伺服器上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="d5e95-298">On each server, do the following</span></span>
    
   - <span data-ttu-id="d5e95-299">開啟 [伺服器管理員]，然後按一下 [**新增角色和功能**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-299">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="d5e95-300">按一下 **[下一步]** ，直到您到達 [**選取功能**] 方塊為止。</span><span class="sxs-lookup"><span data-stu-id="d5e95-300">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="d5e95-301">在這裡，選取 [**容錯移轉叢集**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d5e95-301">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="d5e95-302">在 [**新增容錯移轉叢集所需的功能？** ] 方塊中，按一下 [**新增功能**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-302">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="d5e95-303">按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-303">Click **Install**.</span></span>
    
2. <span data-ttu-id="d5e95-304">驗證群集設定。</span><span class="sxs-lookup"><span data-stu-id="d5e95-304">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="d5e95-305">在 [伺服器管理員] 中，按一下 [**工具**] 功能表，然後按一下 [**容錯移轉叢集管理器**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-305">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="d5e95-306">在畫面右側的 [**動作**] 底下，按一下 [**驗證配置**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-306">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="d5e95-307">在 [**開始之前**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-307">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="d5e95-308">選取要新增至群集的伺服器，然後按一下 [**執行所有測試**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-308">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="d5e95-309">在 [**摘要**] 方塊中，檢查嚮導所報告的任何錯誤。</span><span class="sxs-lookup"><span data-stu-id="d5e95-309">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="d5e95-310">然後按一下 **[完成]** 以完成驗證。</span><span class="sxs-lookup"><span data-stu-id="d5e95-310">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="d5e95-311">此嚮導可能會報告幾個警告，特別是如果您不是使用共用儲存空間。</span><span class="sxs-lookup"><span data-stu-id="d5e95-311">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="d5e95-312">您不需要使用共用儲存空間。</span><span class="sxs-lookup"><span data-stu-id="d5e95-312">You are not required to use shared storage.</span></span> <span data-ttu-id="d5e95-313">不過，如果您看到任何**錯誤**訊息，您必須先修正這些問題，然後才能繼續進行。</span><span class="sxs-lookup"><span data-stu-id="d5e95-313">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="d5e95-314">建立 Windows Server 容錯移轉叢集（WSFC）。</span><span class="sxs-lookup"><span data-stu-id="d5e95-314">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="d5e95-315">在 [**容錯移轉叢集管理**] 嚮導中，以滑鼠右鍵按一下 [**容錯移轉叢集管理**]，然後按一下 [**建立群集**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-315">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="d5e95-316">在 [**開始之前**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-316">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="d5e95-317">新增 [群集名稱] 和 [IP 位址]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-317">Add the cluster name and IP address.</span></span> <span data-ttu-id="d5e95-318">驗證設定後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-318">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="d5e95-319">在確認頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-319">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="d5e95-320">建立群集之後，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-320">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="d5e95-321">我們建議您將群集仲裁設定設定為使用檔案共用見證。</span><span class="sxs-lookup"><span data-stu-id="d5e95-321">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="d5e95-322">若要這樣做，請使用下列步驟：</span><span class="sxs-lookup"><span data-stu-id="d5e95-322">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="d5e95-323">以滑鼠右鍵按一下群集名稱，按一下 [**其他動作**]，然後按一下 [**設定群集仲裁設定**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-323">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="d5e95-324">在 [**選取仲裁**設定] 選項頁面上，按一下 [**選取仲裁見證**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-324">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="d5e95-325">在 [**選取仲裁見證**] 頁面上，按一下 [**設定檔案共用見證**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-325">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="d5e95-326">在 [**設定檔案共用見證**] 頁面上，輸入您要使用的檔案共用路徑，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-326">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="d5e95-327">在**確認**頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-327">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="d5e95-328">在群集中的每個伺服器上，于 [SQL Server Configuration Manager] 中啟用 AG。</span><span class="sxs-lookup"><span data-stu-id="d5e95-328">On each server in the cluster, enable AG in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="d5e95-329">開啟 [SQL Server Configuration Manager]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-329">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="d5e95-330">在畫面左側的樹狀結構中，按一下 [ **Sql Server 服務**]，然後按兩下 [sql server 服務]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-330">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="d5e95-331">在 [**屬性**] 方塊中，選取 [ **alwayson**可用性] 索引標籤。選取 [**啟用 AlwaysOn 可用性群組**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d5e95-331">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="d5e95-332">出現提示時，請重新開機 SQL Server 服務。</span><span class="sxs-lookup"><span data-stu-id="d5e95-332">Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="d5e95-333">建立 [可用性] 群組。</span><span class="sxs-lookup"><span data-stu-id="d5e95-333">Create the availability group.</span></span>
    
   - <span data-ttu-id="d5e95-334">開啟 [SQL Server Management Studio]，然後連線到 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="d5e95-334">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="d5e95-335">在物件資源管理器中，展開 [**永不在高可用性**] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="d5e95-335">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="d5e95-336">以滑鼠右鍵按一下 [**可用性群組**] 資料夾，然後按一下 [**新增可用性群組嚮導]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-336">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="d5e95-337">如果出現 [**簡介**] 頁面，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-337">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="d5e95-338">在 [**指定可用性群組名稱**] 頁面上，輸入可用性群組的名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-338">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="d5e95-339">在 [選取資料庫] 頁面中，選取您要包含在 AG 中的資料庫。</span><span class="sxs-lookup"><span data-stu-id="d5e95-339">In the Select Databases page, select the databases that you want to include in the AG.</span></span> <span data-ttu-id="d5e95-340">然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-340">Then click **Next**.</span></span>
    
     <span data-ttu-id="d5e95-341">請勿在 AG 中包含**ReportServer**、 **ReportServerTempDB**或持久聊天資料庫，因為這種情況不支援這些專案。</span><span class="sxs-lookup"><span data-stu-id="d5e95-341">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AG, as these are not supported in this scenario.</span></span> <span data-ttu-id="d5e95-342">您可以在 AG 中包含所有其他商務用 Skype 伺服器資料庫。</span><span class="sxs-lookup"><span data-stu-id="d5e95-342">You can include all other Skype for Business Server databases in the AG.</span></span>
    
   - <span data-ttu-id="d5e95-343">在 [**指定複本**] 頁面上，按一下 [**複本**] 索引標籤。然後按一下 [**新增複本**] 按鈕，並聯機到您加入為 WSFC 節點的其他 SQL 實例。</span><span class="sxs-lookup"><span data-stu-id="d5e95-343">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the WSFC.</span></span>
    
   - <span data-ttu-id="d5e95-344">針對每個實例，選取 [**自動容錯移轉**] 和 [**同步提交**] 選項。</span><span class="sxs-lookup"><span data-stu-id="d5e95-344">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="d5e95-345">請勿選取 [**可讀的次要**] 選項。</span><span class="sxs-lookup"><span data-stu-id="d5e95-345">Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="d5e95-346">按一下 [**端點**] 索引標籤，並確認 [**埠號碼**] 設定為 [5022]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-346">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="d5e95-347">按一下 [**攔截器**] 索引標籤，然後選取 [**建立可用性群組偵聽程式]** 選項。</span><span class="sxs-lookup"><span data-stu-id="d5e95-347">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="d5e95-348">在 [該選項] 底下，輸入監聽器的名稱，並將**埠**設定為1433（此選項不支援其他埠）。</span><span class="sxs-lookup"><span data-stu-id="d5e95-348">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="d5e95-349">按一下 [**新增**]，然後在 [ **IPv4 位址**] 方塊中，提供您慣用的虛擬 IP 位址，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-349">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="d5e95-350">在 [**選取初始資料同步**處理] 頁面中，選取 [完整]，並指定複本可存取的資料夾，且兩個複本所使用的 SQL Server 服務帳戶都具有寫入權限。</span><span class="sxs-lookup"><span data-stu-id="d5e95-350">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="d5e95-351">然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-351">Then click **Next**.</span></span>
    
     <span data-ttu-id="d5e95-352">此檔案共用將在您初始化資料庫時暫時使用。</span><span class="sxs-lookup"><span data-stu-id="d5e95-352">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="d5e95-353">如果您正在處理大型資料庫，建議您手動初始化這些資料庫，以防您的網路頻寬無法容納資料庫備份的大小。</span><span class="sxs-lookup"><span data-stu-id="d5e95-353">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
     - <span data-ttu-id="d5e95-354">在驗證頁面中，確認所有驗證檢查都已成功完成，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-354">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="d5e95-355">在 [**摘要**] 頁面中，確認所有設定，然後按一下 [完成]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-355">In the **Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="d5e95-356">建立新的書店來指定 AG 監聽程式。</span><span class="sxs-lookup"><span data-stu-id="d5e95-356">Create a new store specifying the AG listener.</span></span>
    
   - <span data-ttu-id="d5e95-357">開啟拓撲建立器。</span><span class="sxs-lookup"><span data-stu-id="d5e95-357">Open Topology Builder.</span></span> <span data-ttu-id="d5e95-358">在您的拓撲中，展開 [**共用元件**]，以滑鼠右鍵按一下 **[sql server**Store]，然後按一下 [**新增 sql server Store**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-358">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
   - <span data-ttu-id="d5e95-359">在 [**定義新的 SQL Store** ] 頁面中，先選取 [**高可用性設定**] 核取方塊，然後確認 [SQL AlwaysOn 可用性群組] 出現在下拉式方塊中。</span><span class="sxs-lookup"><span data-stu-id="d5e95-359">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
   - <span data-ttu-id="d5e95-360">在 [ **SQL Server 可用性偵聽程式 FQDN]** 方塊中，輸入您在建立可用性群組時所建立之監聽程式的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d5e95-360">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
   - <span data-ttu-id="d5e95-361">在 [ **SQL SERVER FQDN** ] 方塊中，輸入 AG 主要節點的 FQDN，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-361">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span>
    
8. <span data-ttu-id="d5e95-362">將新的 [永遠開啟] 可用性群組與 [前端] 池建立關聯。</span><span class="sxs-lookup"><span data-stu-id="d5e95-362">Associate the new Always On Availability Group with the Front End pool.</span></span>
    
   - <span data-ttu-id="d5e95-363">在拓撲建立器中，以滑鼠右鍵按一下要與 AG 關聯的 [泳池]，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-363">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="d5e95-364">在 [**關聯**性] 底下的 [ **SQL Server 存放區**] 方塊中，選取 AG。</span><span class="sxs-lookup"><span data-stu-id="d5e95-364">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="d5e95-365">針對您要移至 AG 的池中的任何其他資料庫，選取相同的群組。</span><span class="sxs-lookup"><span data-stu-id="d5e95-365">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
   - <span data-ttu-id="d5e95-366">當您確定所需的所有資料庫都設定為 AG 時，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-366">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
9. <span data-ttu-id="d5e95-367">發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="d5e95-367">Publish the topology.</span></span> <span data-ttu-id="d5e95-368">從 [**動作**] 功能表按一下 [**拓撲**]，然後按一下 [**發佈**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-368">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="d5e95-369">然後在確認頁面中，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-369">Then in the confirmation page click **Next**.</span></span>
    
10. <span data-ttu-id="d5e95-370">執行一些最終步驟，以確保 AG 中的每個副本都有這些 SQL 登錄。</span><span class="sxs-lookup"><span data-stu-id="d5e95-370">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AG.</span></span>
    
    - <span data-ttu-id="d5e95-371">開啟拓撲建立器，選取 [**從現有部署下載拓撲**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-371">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="d5e95-372">展開 [商務用 Skype 伺服器]、展開您的拓撲，然後展開 **[SQL Server 存放區**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-372">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="d5e95-373">以滑鼠右鍵按一下新 AG 的 [SQL] 商店，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-373">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="d5e95-374">在頁面底部的 [ **SQL SERVER FQDN** ] 方塊中，將值變更為 AG 監聽程式的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d5e95-374">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="d5e95-375">發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="d5e95-375">Publish the topology.</span></span> <span data-ttu-id="d5e95-376">從 [**動作**] 功能表按一下 [**拓撲**]，然後按一下 [**發佈**]。</span><span class="sxs-lookup"><span data-stu-id="d5e95-376">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="d5e95-377">然後在確認頁面中，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d5e95-377">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="d5e95-378">然後稍等幾分鐘，即可複製新的拓撲。</span><span class="sxs-lookup"><span data-stu-id="d5e95-378">Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="d5e95-379">開啟 SQL Server Management Studio，然後流覽到 AG。</span><span class="sxs-lookup"><span data-stu-id="d5e95-379">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="d5e95-380">將它容錯移轉到副複本。</span><span class="sxs-lookup"><span data-stu-id="d5e95-380">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="d5e95-381">開啟商務用 Skype Server 管理命令介面，然後輸入下列 Cmdlet，以在此複製副本上建立 SQL 登錄：</span><span class="sxs-lookup"><span data-stu-id="d5e95-381">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
      ```powershell
      Install-CsDatabase -Update
      ```

      - <span data-ttu-id="d5e95-382">針對群組中的每個複本重複上述兩個步驟（將群組容錯移轉`Install-CsDatabase -Update`至次要複本，然後使用）。</span><span class="sxs-lookup"><span data-stu-id="d5e95-382">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
