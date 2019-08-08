---
title: 設定常設聊天室伺服器的高可用性和災害復原
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: '摘要: 請閱讀本主題, 以瞭解如何在商務用 Skype Server 2015 中設定持續聊天伺服器的高可用性和災難復原。'
ms.openlocfilehash: cfc2843ceb3afba4813cc729856dcd35a4a6439e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240114"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="fda8a-103">設定常設聊天室伺服器的高可用性和災害復原</span><span class="sxs-lookup"><span data-stu-id="fda8a-103">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="fda8a-104">**摘要:** 請閱讀本主題, 以瞭解如何在商務用 Skype Server 2015 中設定持續聊天伺服器的高可用性和災害復原。</span><span class="sxs-lookup"><span data-stu-id="fda8a-104">**Summary:** Read this topic to learn how to configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="fda8a-105">商務用 Skype 伺服器支援後端伺服器的多種高可用性模式, 包括資料庫鏡像。</span><span class="sxs-lookup"><span data-stu-id="fda8a-105">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="fda8a-106">如需詳細資訊, 請參閱[在商務用 Skype Server 2015 中規劃高可用性和災害復原](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="fda8a-106">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="fda8a-107">永久聊天伺服器不支援 AlwaysOn 可用性群組。</span><span class="sxs-lookup"><span data-stu-id="fda8a-107">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="fda8a-108">在您針對高可用性和災害復原設定持續性聊天部署之前, 請務必熟悉在[商務用 Skype server 2015 中針對持續聊天伺服器進行高可用性和災難](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)復原的概念。</span><span class="sxs-lookup"><span data-stu-id="fda8a-108">Before you configure your Persistent Chat deployment for high availability and disaster recovery, be sure you are familiar with the concepts in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="fda8a-109">在這些主題中所述的持續聊天伺服器災害復原解決方案是在延伸持續性聊天伺服器池中建立的。</span><span class="sxs-lookup"><span data-stu-id="fda8a-109">The disaster recovery solution for Persistent Chat Server described in these topics is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="fda8a-110">規劃內容描述資源需求, 以及可為持續性聊天伺服器啟用高可用性和災難復原的延伸池拓撲, 包括使用 SQL Server 鏡像提供高可用性和 SQL Server 記錄傳送功能災害復原。</span><span class="sxs-lookup"><span data-stu-id="fda8a-110">The planning content describes resource requirements, and the stretched pool topology that enables high availability and disaster recovery for Persistent Chat Server, including using SQL Server mirroring for high availability and SQL Server log shipping for disaster recovery.</span></span>
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a><span data-ttu-id="fda8a-111">使用拓撲建立器來設定高可用性與災害復原</span><span class="sxs-lookup"><span data-stu-id="fda8a-111">Use Topology Builder to configure high availability and disaster recovery</span></span>

<span data-ttu-id="fda8a-112">在拓撲建立器內, 請執行下列步驟, 以設定持久聊天伺服器的高可用性和災害復原。</span><span class="sxs-lookup"><span data-stu-id="fda8a-112">Within Topology Builder, perform the following steps to configure high availability and disaster recovery for Persistent Chat Server.</span></span>
  
1. <span data-ttu-id="fda8a-113">新增鏡像資料庫與記錄傳送次要資料庫 SQL Server 書店。</span><span class="sxs-lookup"><span data-stu-id="fda8a-113">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>
    
2. <span data-ttu-id="fda8a-114">編輯持續聊天伺服器的服務屬性至:</span><span class="sxs-lookup"><span data-stu-id="fda8a-114">Edit the Persistent Chat Server service properties to:</span></span>
    
    <span data-ttu-id="fda8a-115">是.</span><span class="sxs-lookup"><span data-stu-id="fda8a-115">a.</span></span> <span data-ttu-id="fda8a-116">針對主要資料庫啟用鏡像。</span><span class="sxs-lookup"><span data-stu-id="fda8a-116">Enable mirroring for the primary database.</span></span>
    
    <span data-ttu-id="fda8a-117">乙.</span><span class="sxs-lookup"><span data-stu-id="fda8a-117">b.</span></span> <span data-ttu-id="fda8a-118">新增主鏡像 SQL Server 存放區。</span><span class="sxs-lookup"><span data-stu-id="fda8a-118">Add the primary mirror SQL Server store.</span></span>
    
    <span data-ttu-id="fda8a-119">c-clip.</span><span class="sxs-lookup"><span data-stu-id="fda8a-119">c.</span></span> <span data-ttu-id="fda8a-120">啟用 SQL Server 記錄傳送資料庫。</span><span class="sxs-lookup"><span data-stu-id="fda8a-120">Enable the SQL Server Log Shipping database.</span></span>
    
    <span data-ttu-id="fda8a-121">希望.</span><span class="sxs-lookup"><span data-stu-id="fda8a-121">d.</span></span> <span data-ttu-id="fda8a-122">新增 SQL Server 記錄傳送的次要 SQL Server store。</span><span class="sxs-lookup"><span data-stu-id="fda8a-122">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    <span data-ttu-id="fda8a-123">e.</span><span class="sxs-lookup"><span data-stu-id="fda8a-123">e.</span></span> <span data-ttu-id="fda8a-124">為次要資料庫新增 SQL Server store 鏡像。</span><span class="sxs-lookup"><span data-stu-id="fda8a-124">Add the SQL Server store mirror for the secondary database.</span></span>
    
    <span data-ttu-id="fda8a-125">°.</span><span class="sxs-lookup"><span data-stu-id="fda8a-125">f.</span></span> <span data-ttu-id="fda8a-126">發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="fda8a-126">Publish the topology.</span></span>
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="fda8a-127">針對持續聊天伺服器主資料庫設定 SQL Server 記錄傳送</span><span class="sxs-lookup"><span data-stu-id="fda8a-127">Set up SQL Server log shipping for the Persistent Chat Server primary database</span></span>

<span data-ttu-id="fda8a-128">使用 SQL Server Management Studio, 連線至持續聊天伺服器次要記錄傳送資料庫實例, 並確認 SQL Server 代理程式正在執行。</span><span class="sxs-lookup"><span data-stu-id="fda8a-128">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span> <span data-ttu-id="fda8a-129">然後, 連線到 [持續聊天] 主要資料庫實例, 並執行下列步驟:</span><span class="sxs-lookup"><span data-stu-id="fda8a-129">Then connect to the Persistent Chat primary database instance and perform the following steps:</span></span>
  
1. <span data-ttu-id="fda8a-130">以滑鼠右鍵按一下 mgc 資料庫, 然後按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="fda8a-130">Right-click the mgc database, and then click **Properties**.</span></span>
    
2. <span data-ttu-id="fda8a-131">在 [**選取頁面**] 底下, 按一下 [**事務記錄傳送**]。</span><span class="sxs-lookup"><span data-stu-id="fda8a-131">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
3. <span data-ttu-id="fda8a-132">選取 [將**此項啟用為記錄傳送設定的主要資料庫**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="fda8a-132">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
4. <span data-ttu-id="fda8a-133">在 [**事務記錄備份**] 底下, 按一下 [**備份設定**]。</span><span class="sxs-lookup"><span data-stu-id="fda8a-133">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
5. <span data-ttu-id="fda8a-134">在 [**備份檔案夾的網路路徑**] 方塊中, 輸入您針對 [事務記錄備份] 資料夾建立之共用的網路路徑。</span><span class="sxs-lookup"><span data-stu-id="fda8a-134">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>
    
6. <span data-ttu-id="fda8a-135">如果備份檔案夾位於主要伺服器上, 請在 [如果備份檔案夾位於主要伺服器上] 中輸入備份檔案夾的本機路徑 **, 請輸入資料夾的本機路徑 (範例: c:\backup)** 方塊。</span><span class="sxs-lookup"><span data-stu-id="fda8a-135">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\backup)** box.</span></span> <span data-ttu-id="fda8a-136">(如果備份檔案夾不在主要伺服器上, 您可以將此方塊保留空白。)</span><span class="sxs-lookup"><span data-stu-id="fda8a-136">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="fda8a-137">如果主伺服器上的 SQL Server 服務帳戶是在本機系統帳戶下執行, 您必須在主要伺服器上建立您的備份檔案夾, 並指定該資料夾的本機路徑。</span><span class="sxs-lookup"><span data-stu-id="fda8a-137">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
7. <span data-ttu-id="fda8a-138">設定 [**刪除舊**檔的檔案], 並在參數**中不執行任何備份時發出警示**。</span><span class="sxs-lookup"><span data-stu-id="fda8a-138">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
8. <span data-ttu-id="fda8a-139">查看 [**備份作業**] 底下 [**排程**] 方塊中所列的備份排程。</span><span class="sxs-lookup"><span data-stu-id="fda8a-139">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="fda8a-140">若要自訂您的安裝排程, 請按一下 [**排程**], 然後根據需要調整 SQL Server 代理程式排程。</span><span class="sxs-lookup"><span data-stu-id="fda8a-140">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>
    
9. <span data-ttu-id="fda8a-141">在 [**壓縮**] 底下, 選取 **[使用預設伺服器設定**], 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="fda8a-141">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>
    
10. <span data-ttu-id="fda8a-142">在 [**次要伺服器實例與資料庫**] 底下, 按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="fda8a-142">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
11. <span data-ttu-id="fda8a-143">按一下 **[連線]** 並聯機到您已設定為次要伺服器的 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="fda8a-143">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
12. <span data-ttu-id="fda8a-144">在 [**次要資料庫**] 方塊中, 從清單中選取**mgc**資料庫。</span><span class="sxs-lookup"><span data-stu-id="fda8a-144">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
13. <span data-ttu-id="fda8a-145">在 [**初始化次要資料庫**] 索引標籤上, 選擇 [**是]、[產生主資料庫的完整備份], 然後將它還原到次要資料庫 (如果不存在, 則建立次要資料庫)**。</span><span class="sxs-lookup"><span data-stu-id="fda8a-145">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>
    
14. <span data-ttu-id="fda8a-146">在 [**複製**檔案] 索引標籤的 [複製的檔案**目的地資料夾**] 方塊中, 輸入應將事務記錄備份複製到其中的資料夾路徑。</span><span class="sxs-lookup"><span data-stu-id="fda8a-146">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied.</span></span> <span data-ttu-id="fda8a-147">這個資料夾通常位於副伺服器上。</span><span class="sxs-lookup"><span data-stu-id="fda8a-147">This folder is often located on the secondary server.</span></span>
    
15. <span data-ttu-id="fda8a-148">請注意, [**複製作業**] 底下 [**排程**] 方塊中所列的複製排程。</span><span class="sxs-lookup"><span data-stu-id="fda8a-148">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="fda8a-149">若要自訂您的安裝排程, 請按一下 [**排程**], 然後根據需要調整 SQL Server 代理程式排程。</span><span class="sxs-lookup"><span data-stu-id="fda8a-149">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="fda8a-150">此排程應該與備份排程大致相同。</span><span class="sxs-lookup"><span data-stu-id="fda8a-150">This schedule should be approximately the same as the backup schedule.</span></span>
    
16. <span data-ttu-id="fda8a-151">在 [**還原**] 索引標籤上, 在 [**還原備份時資料庫狀態**] 底下, 選擇 [**無復原模式]** 選項。</span><span class="sxs-lookup"><span data-stu-id="fda8a-151">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>
    
17. <span data-ttu-id="fda8a-152">在 [**延遲還原備份至少:**] 底下, 選取 [ **0 分鐘**]。</span><span class="sxs-lookup"><span data-stu-id="fda8a-152">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>
    
18. <span data-ttu-id="fda8a-153">在 [警示] 底下, 選擇 [**如果沒有進行任何還原**]。</span><span class="sxs-lookup"><span data-stu-id="fda8a-153">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>
    
19. <span data-ttu-id="fda8a-154">查看 [**還原作業**] 底下 [**排程**] 方塊中所列的還原排程。</span><span class="sxs-lookup"><span data-stu-id="fda8a-154">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="fda8a-155">若要自訂您的安裝排程, 請按一下 [**排程**], 根據需要調整 SQL Server 代理排程, 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="fda8a-155">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="fda8a-156">此排程應該與備份排程大致相同。</span><span class="sxs-lookup"><span data-stu-id="fda8a-156">This schedule should be approximately the same as the backup schedule.</span></span>
    
20. <span data-ttu-id="fda8a-157">在 [**資料庫屬性**] 對話方塊中, 按一下 **[確定]** 以開始設定程式。</span><span class="sxs-lookup"><span data-stu-id="fda8a-157">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a><span data-ttu-id="fda8a-158">在主要鏡像與次要資料庫之間設定 SQL Server 記錄傳送</span><span class="sxs-lookup"><span data-stu-id="fda8a-158">Set up SQL Server log shipping between the primary mirror and the secondary database</span></span>

<span data-ttu-id="fda8a-159">如果主要持久聊天資料庫發生故障, 請執行下列步驟, 繼續進行記錄傳送至其鏡像資料庫。</span><span class="sxs-lookup"><span data-stu-id="fda8a-159">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>
  
1. <span data-ttu-id="fda8a-160">手動將主要持久聊天資料庫容錯移轉到鏡像。</span><span class="sxs-lookup"><span data-stu-id="fda8a-160">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="fda8a-161">這是使用商務用 Skype 伺服器管理命令介面和**CsDatabaseFailover** Cmdlet 來完成。</span><span class="sxs-lookup"><span data-stu-id="fda8a-161">This is done by using the Skype for Business Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    
2. <span data-ttu-id="fda8a-162">使用 SQL Server Management Studio, 連線到主要持久聊天伺服器鏡像實例。</span><span class="sxs-lookup"><span data-stu-id="fda8a-162">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>
    
3. <span data-ttu-id="fda8a-163">請確定 SQL Server 代理程式正在執行。</span><span class="sxs-lookup"><span data-stu-id="fda8a-163">Be sure that the SQL Server Agent is running.</span></span>
    
4. <span data-ttu-id="fda8a-164">以滑鼠右鍵按一下 mgc 資料庫, 然後按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="fda8a-164">Right-click the mgc database, and then click **Properties**.</span></span>
    
5. <span data-ttu-id="fda8a-165">在 [**選取頁面**] 底下, 按一下 [**事務記錄傳送**]。</span><span class="sxs-lookup"><span data-stu-id="fda8a-165">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
6. <span data-ttu-id="fda8a-166">選取 [將**此項啟用為記錄傳送設定的主要資料庫**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="fda8a-166">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
7. <span data-ttu-id="fda8a-167">在 [**事務記錄備份**] 底下, 按一下 [**備份設定**]。</span><span class="sxs-lookup"><span data-stu-id="fda8a-167">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
8. <span data-ttu-id="fda8a-168">在 [**備份檔案夾的網路路徑**] 方塊中, 輸入您針對 [事務記錄備份] 資料夾建立之共用的網路路徑。</span><span class="sxs-lookup"><span data-stu-id="fda8a-168">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>
    
9. <span data-ttu-id="fda8a-169">如果備份檔案夾位於主要伺服器上, 請在 [**如果備份檔案夾位於主要伺服器上**] 中輸入備份檔案夾的本機路徑, 請在 [資料夾] 方塊中輸入本機路徑。</span><span class="sxs-lookup"><span data-stu-id="fda8a-169">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box.</span></span> <span data-ttu-id="fda8a-170">(如果備份檔案夾不在主要伺服器上, 您可以將此方塊保留空白。)</span><span class="sxs-lookup"><span data-stu-id="fda8a-170">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="fda8a-171">如果主伺服器上的 SQL Server 服務帳戶是在本機系統帳戶下執行, 您必須在主要伺服器上建立您的備份檔案夾, 並指定該資料夾的本機路徑。</span><span class="sxs-lookup"><span data-stu-id="fda8a-171">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
10. <span data-ttu-id="fda8a-172">設定 [**刪除舊**檔的檔案], 並在參數**中不執行任何備份時發出警示**。</span><span class="sxs-lookup"><span data-stu-id="fda8a-172">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
11. <span data-ttu-id="fda8a-173">查看 [**備份作業**] 底下 [**排程**] 方塊中所列的備份排程。</span><span class="sxs-lookup"><span data-stu-id="fda8a-173">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="fda8a-174">若要自訂您的安裝排程, 請根據需要按一下 [**排程**], 然後調整 SQL Server 代理程式排程。</span><span class="sxs-lookup"><span data-stu-id="fda8a-174">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="fda8a-175">使用您在主要資料庫中使用的相同設定。</span><span class="sxs-lookup"><span data-stu-id="fda8a-175">Use the same settings that you used for the primary database.</span></span> 
  
12. <span data-ttu-id="fda8a-176">在 [**壓縮**] 底下, 選取 **[使用預設伺服器設定**], 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="fda8a-176">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>
    
13. <span data-ttu-id="fda8a-177">在 [**次要伺服器實例與資料庫**] 底下, 按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="fda8a-177">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
14. <span data-ttu-id="fda8a-178">按一下 **[連線]**, 然後連線到您已設定為次要伺服器的 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="fda8a-178">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
15. <span data-ttu-id="fda8a-179">在 [**次要資料庫**] 方塊中, 從清單中選取**mgc**資料庫。</span><span class="sxs-lookup"><span data-stu-id="fda8a-179">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
16. <span data-ttu-id="fda8a-180">在 [**初始化次要資料庫**] 索引標籤上, 選取 [**否, 次要資料庫已初始化**]。</span><span class="sxs-lookup"><span data-stu-id="fda8a-180">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>
    
17. <span data-ttu-id="fda8a-181">在 [**複製**檔案] 索引標籤上, 于 [**複製的檔案目的地] 資料夾**中, 輸入應將事務記錄備份複製到哪個資料夾的路徑, 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="fda8a-181">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**.</span></span> <span data-ttu-id="fda8a-182">這個資料夾通常位於副伺服器上。</span><span class="sxs-lookup"><span data-stu-id="fda8a-182">This folder is often located on the secondary server.</span></span>
    
18. <span data-ttu-id="fda8a-183">開啟 [**腳本**設定] 下拉式清單, 然後選取 [**腳本設定至新查詢] 視窗**。</span><span class="sxs-lookup"><span data-stu-id="fda8a-183">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>
    
19. <span data-ttu-id="fda8a-184">在 [新增查詢] 視窗的 [**資料庫屬性**] 中, 按一下 **[確定]** 以開始設定程式。</span><span class="sxs-lookup"><span data-stu-id="fda8a-184">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>
    
20. <span data-ttu-id="fda8a-185">選取並執行查詢的前半部分 (請參閱步驟 18) 至行:-- \* \* \* \* \* \*結束\* \* \* \* \* \*: 要在主要: 執行的腳本。</span><span class="sxs-lookup"><span data-stu-id="fda8a-185">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="fda8a-186">手動執行此腳本是必要的, 因為 SQL Server Management Studio 不支援 SQL Server 記錄傳送設定中的多個主要資料庫。</span><span class="sxs-lookup"><span data-stu-id="fda8a-186">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span> 
  
21. <span data-ttu-id="fda8a-187">選取 [**取消**] 以關閉 [記錄檔案傳送設定] 面板, 並建立能正確實現主要和鏡像資料庫 (如果是容錯移轉) 的記錄檔傳送的工作設定。</span><span class="sxs-lookup"><span data-stu-id="fda8a-187">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>
    
22. <span data-ttu-id="fda8a-188">手動將主要持久聊天資料庫容錯回復到主要。</span><span class="sxs-lookup"><span data-stu-id="fda8a-188">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="fda8a-189">這是使用商務用 Skype 伺服器管理命令介面和**CsDatabaseFailover** Cmdlet 來完成。</span><span class="sxs-lookup"><span data-stu-id="fda8a-189">This is done by using the Skype for Business Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    

