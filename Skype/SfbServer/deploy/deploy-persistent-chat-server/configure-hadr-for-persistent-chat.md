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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 摘要：請閱讀本主題，以瞭解如何在商務用 Skype Server 2015 中設定持續聊天伺服器的高可用性和災難復原。
ms.openlocfilehash: 81fcc37ecbdf513decd89481c8a651404d91294a
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41795524"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="2df34-103">設定常設聊天室伺服器的高可用性和災害復原</span><span class="sxs-lookup"><span data-stu-id="2df34-103">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2df34-104">**摘要：** 請閱讀本主題，以瞭解如何在商務用 Skype Server 2015 中設定持續聊天伺服器的高可用性和災害復原。</span><span class="sxs-lookup"><span data-stu-id="2df34-104">**Summary:** Read this topic to learn how to configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="2df34-105">商務用 Skype 伺服器支援後端伺服器的多種高可用性模式，包括資料庫鏡像。</span><span class="sxs-lookup"><span data-stu-id="2df34-105">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="2df34-106">如需詳細資訊，請參閱[在商務用 Skype Server 2015 中規劃高可用性和災害復原](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="2df34-106">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="2df34-107">永久聊天伺服器不支援 AlwaysOn 可用性群組。</span><span class="sxs-lookup"><span data-stu-id="2df34-107">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 

> [!NOTE] 
> <span data-ttu-id="2df34-108">商務用 Skype Server 2015 提供持續聊天，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="2df34-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="2df34-109">團隊中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="2df34-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="2df34-110">如需詳細資訊，請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="2df34-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="2df34-111">如果您需要使用持續聊天，您可以選擇將需要此功能的使用者遷移至小組，或繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="2df34-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="2df34-112">在您針對高可用性和災害復原設定持續性聊天部署之前，請務必熟悉在[商務用 Skype server 2015 中針對持續聊天伺服器進行高可用性和災難](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)復原的概念。</span><span class="sxs-lookup"><span data-stu-id="2df34-112">Before you configure your Persistent Chat deployment for high availability and disaster recovery, be sure you are familiar with the concepts in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="2df34-113">在這些主題中所述的持續聊天伺服器災害復原解決方案是在延伸持續性聊天伺服器池中建立的。</span><span class="sxs-lookup"><span data-stu-id="2df34-113">The disaster recovery solution for Persistent Chat Server described in these topics is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="2df34-114">規劃內容描述資源需求，以及可為持續性聊天伺服器啟用高可用性和災難復原的延伸池拓撲，包括使用 SQL Server 鏡像提供高可用性和 SQL Server 記錄傳送功能災害復原。</span><span class="sxs-lookup"><span data-stu-id="2df34-114">The planning content describes resource requirements, and the stretched pool topology that enables high availability and disaster recovery for Persistent Chat Server, including using SQL Server mirroring for high availability and SQL Server log shipping for disaster recovery.</span></span>
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a><span data-ttu-id="2df34-115">使用拓撲建立器來設定高可用性與災害復原</span><span class="sxs-lookup"><span data-stu-id="2df34-115">Use Topology Builder to configure high availability and disaster recovery</span></span>

<span data-ttu-id="2df34-116">在拓撲建立器內，請執行下列步驟，以設定持久聊天伺服器的高可用性和災害復原。</span><span class="sxs-lookup"><span data-stu-id="2df34-116">Within Topology Builder, perform the following steps to configure high availability and disaster recovery for Persistent Chat Server.</span></span>
  
1. <span data-ttu-id="2df34-117">新增鏡像資料庫與記錄傳送次要資料庫 SQL Server 書店。</span><span class="sxs-lookup"><span data-stu-id="2df34-117">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>
    
2. <span data-ttu-id="2df34-118">編輯持續聊天伺服器的服務屬性至：</span><span class="sxs-lookup"><span data-stu-id="2df34-118">Edit the Persistent Chat Server service properties to:</span></span>
    
    <span data-ttu-id="2df34-119">是.</span><span class="sxs-lookup"><span data-stu-id="2df34-119">a.</span></span> <span data-ttu-id="2df34-120">針對主要資料庫啟用鏡像。</span><span class="sxs-lookup"><span data-stu-id="2df34-120">Enable mirroring for the primary database.</span></span>
    
    <span data-ttu-id="2df34-121">乙.</span><span class="sxs-lookup"><span data-stu-id="2df34-121">b.</span></span> <span data-ttu-id="2df34-122">新增主鏡像 SQL Server 存放區。</span><span class="sxs-lookup"><span data-stu-id="2df34-122">Add the primary mirror SQL Server store.</span></span>
    
    <span data-ttu-id="2df34-123">c-clip.</span><span class="sxs-lookup"><span data-stu-id="2df34-123">c.</span></span> <span data-ttu-id="2df34-124">啟用 SQL Server 記錄傳送資料庫。</span><span class="sxs-lookup"><span data-stu-id="2df34-124">Enable the SQL Server Log Shipping database.</span></span>
    
    <span data-ttu-id="2df34-125">希望.</span><span class="sxs-lookup"><span data-stu-id="2df34-125">d.</span></span> <span data-ttu-id="2df34-126">新增 SQL Server 記錄傳送的次要 SQL Server store。</span><span class="sxs-lookup"><span data-stu-id="2df34-126">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    <span data-ttu-id="2df34-127">e.</span><span class="sxs-lookup"><span data-stu-id="2df34-127">e.</span></span> <span data-ttu-id="2df34-128">為次要資料庫新增 SQL Server store 鏡像。</span><span class="sxs-lookup"><span data-stu-id="2df34-128">Add the SQL Server store mirror for the secondary database.</span></span>
    
    <span data-ttu-id="2df34-129">°.</span><span class="sxs-lookup"><span data-stu-id="2df34-129">f.</span></span> <span data-ttu-id="2df34-130">發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="2df34-130">Publish the topology.</span></span>
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="2df34-131">針對持續聊天伺服器主資料庫設定 SQL Server 記錄傳送</span><span class="sxs-lookup"><span data-stu-id="2df34-131">Set up SQL Server log shipping for the Persistent Chat Server primary database</span></span>

<span data-ttu-id="2df34-132">使用 SQL Server Management Studio，連線至持續聊天伺服器次要記錄傳送資料庫實例，並確認 SQL Server 代理程式正在執行。</span><span class="sxs-lookup"><span data-stu-id="2df34-132">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span> <span data-ttu-id="2df34-133">然後，連線到 [持續聊天] 主要資料庫實例，並執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="2df34-133">Then connect to the Persistent Chat primary database instance and perform the following steps:</span></span>
  
1. <span data-ttu-id="2df34-134">以滑鼠右鍵按一下 mgc 資料庫，然後按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="2df34-134">Right-click the mgc database, and then click **Properties**.</span></span>
    
2. <span data-ttu-id="2df34-135">在 [**選取頁面**] 底下，按一下 [**事務記錄傳送**]。</span><span class="sxs-lookup"><span data-stu-id="2df34-135">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
3. <span data-ttu-id="2df34-136">選取 [將**此項啟用為記錄傳送設定的主要資料庫**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2df34-136">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
4. <span data-ttu-id="2df34-137">在 [**事務記錄備份**] 底下，按一下 [**備份設定**]。</span><span class="sxs-lookup"><span data-stu-id="2df34-137">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
5. <span data-ttu-id="2df34-138">在 [**備份檔案夾的網路路徑**] 方塊中，輸入您針對 [事務記錄備份] 資料夾建立之共用的網路路徑。</span><span class="sxs-lookup"><span data-stu-id="2df34-138">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>
    
6. <span data-ttu-id="2df34-139">如果備份檔案夾位於主要伺服器上，請在 [如果備份檔案夾位於主要伺服器上] 中輸入備份檔案夾的本機路徑 **，請輸入資料夾的本機路徑（範例： c:\backup）** 方塊。</span><span class="sxs-lookup"><span data-stu-id="2df34-139">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\backup)** box.</span></span> <span data-ttu-id="2df34-140">（如果備份檔案夾不在主要伺服器上，您可以將此方塊保留空白。）</span><span class="sxs-lookup"><span data-stu-id="2df34-140">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="2df34-141">如果主伺服器上的 SQL Server 服務帳戶是在本機系統帳戶下執行，您必須在主要伺服器上建立您的備份檔案夾，並指定該資料夾的本機路徑。</span><span class="sxs-lookup"><span data-stu-id="2df34-141">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
7. <span data-ttu-id="2df34-142">設定 [**刪除舊**檔的檔案]，並在參數**中不執行任何備份時發出警示**。</span><span class="sxs-lookup"><span data-stu-id="2df34-142">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
8. <span data-ttu-id="2df34-143">查看 [**備份作業**] 底下 [**排程**] 方塊中所列的備份排程。</span><span class="sxs-lookup"><span data-stu-id="2df34-143">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="2df34-144">若要自訂您的安裝排程，請按一下 [**排程**]，然後根據需要調整 SQL Server 代理程式排程。</span><span class="sxs-lookup"><span data-stu-id="2df34-144">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>
    
9. <span data-ttu-id="2df34-145">在 [**壓縮**] 底下，選取 **[使用預設伺服器設定**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="2df34-145">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>
    
10. <span data-ttu-id="2df34-146">在 [**次要伺服器實例與資料庫**] 底下，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="2df34-146">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
11. <span data-ttu-id="2df34-147">按一下 **[連線]** 並聯機到您已設定為次要伺服器的 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="2df34-147">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
12. <span data-ttu-id="2df34-148">在 [**次要資料庫**] 方塊中，從清單中選取**mgc**資料庫。</span><span class="sxs-lookup"><span data-stu-id="2df34-148">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
13. <span data-ttu-id="2df34-149">在 [**初始化次要資料庫**] 索引標籤上，選擇 [**是]、[產生主資料庫的完整備份]，然後將它還原到次要資料庫（如果不存在，則建立次要資料庫）**。</span><span class="sxs-lookup"><span data-stu-id="2df34-149">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>
    
14. <span data-ttu-id="2df34-150">在 [**複製**檔案] 索引標籤的 [複製的檔案**目的地資料夾**] 方塊中，輸入應將事務記錄備份複製到其中的資料夾路徑。</span><span class="sxs-lookup"><span data-stu-id="2df34-150">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied.</span></span> <span data-ttu-id="2df34-151">這個資料夾通常位於副伺服器上。</span><span class="sxs-lookup"><span data-stu-id="2df34-151">This folder is often located on the secondary server.</span></span>
    
15. <span data-ttu-id="2df34-152">請注意，[**複製作業**] 底下 [**排程**] 方塊中所列的複製排程。</span><span class="sxs-lookup"><span data-stu-id="2df34-152">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="2df34-153">若要自訂您的安裝排程，請按一下 [**排程**]，然後根據需要調整 SQL Server 代理程式排程。</span><span class="sxs-lookup"><span data-stu-id="2df34-153">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="2df34-154">此排程應該與備份排程大致相同。</span><span class="sxs-lookup"><span data-stu-id="2df34-154">This schedule should be approximately the same as the backup schedule.</span></span>
    
16. <span data-ttu-id="2df34-155">在 [**還原**] 索引標籤上，在 [**還原備份時資料庫狀態**] 底下，選擇 [**無復原模式]** 選項。</span><span class="sxs-lookup"><span data-stu-id="2df34-155">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>
    
17. <span data-ttu-id="2df34-156">在 [**延遲還原備份至少：**] 底下，選取 [ **0 分鐘**]。</span><span class="sxs-lookup"><span data-stu-id="2df34-156">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>
    
18. <span data-ttu-id="2df34-157">在 [警示] 底下，選擇 [**如果沒有進行任何還原**]。</span><span class="sxs-lookup"><span data-stu-id="2df34-157">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>
    
19. <span data-ttu-id="2df34-158">查看 [**還原作業**] 底下 [**排程**] 方塊中所列的還原排程。</span><span class="sxs-lookup"><span data-stu-id="2df34-158">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="2df34-159">若要自訂您的安裝排程，請按一下 [**排程**]，根據需要調整 SQL Server 代理排程，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="2df34-159">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="2df34-160">此排程應該與備份排程大致相同。</span><span class="sxs-lookup"><span data-stu-id="2df34-160">This schedule should be approximately the same as the backup schedule.</span></span>
    
20. <span data-ttu-id="2df34-161">在 [**資料庫屬性**] 對話方塊中，按一下 **[確定]** 以開始設定程式。</span><span class="sxs-lookup"><span data-stu-id="2df34-161">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a><span data-ttu-id="2df34-162">在主要鏡像與次要資料庫之間設定 SQL Server 記錄傳送</span><span class="sxs-lookup"><span data-stu-id="2df34-162">Set up SQL Server log shipping between the primary mirror and the secondary database</span></span>

<span data-ttu-id="2df34-163">如果主要持久聊天資料庫發生故障，請執行下列步驟，繼續進行記錄傳送至其鏡像資料庫。</span><span class="sxs-lookup"><span data-stu-id="2df34-163">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>
  
1. <span data-ttu-id="2df34-164">手動將主要持久聊天資料庫容錯移轉到鏡像。</span><span class="sxs-lookup"><span data-stu-id="2df34-164">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="2df34-165">這是使用商務用 Skype 伺服器管理命令介面和**CsDatabaseFailover** Cmdlet 來完成。</span><span class="sxs-lookup"><span data-stu-id="2df34-165">This is done by using the Skype for Business Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    
2. <span data-ttu-id="2df34-166">使用 SQL Server Management Studio，連線到主要持久聊天伺服器鏡像實例。</span><span class="sxs-lookup"><span data-stu-id="2df34-166">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>
    
3. <span data-ttu-id="2df34-167">請確定 SQL Server 代理程式正在執行。</span><span class="sxs-lookup"><span data-stu-id="2df34-167">Be sure that the SQL Server Agent is running.</span></span>
    
4. <span data-ttu-id="2df34-168">以滑鼠右鍵按一下 mgc 資料庫，然後按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="2df34-168">Right-click the mgc database, and then click **Properties**.</span></span>
    
5. <span data-ttu-id="2df34-169">在 [**選取頁面**] 底下，按一下 [**事務記錄傳送**]。</span><span class="sxs-lookup"><span data-stu-id="2df34-169">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
6. <span data-ttu-id="2df34-170">選取 [將**此項啟用為記錄傳送設定的主要資料庫**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2df34-170">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
7. <span data-ttu-id="2df34-171">在 [**事務記錄備份**] 底下，按一下 [**備份設定**]。</span><span class="sxs-lookup"><span data-stu-id="2df34-171">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
8. <span data-ttu-id="2df34-172">在 [**備份檔案夾的網路路徑**] 方塊中，輸入您針對 [事務記錄備份] 資料夾建立之共用的網路路徑。</span><span class="sxs-lookup"><span data-stu-id="2df34-172">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>
    
9. <span data-ttu-id="2df34-173">如果備份檔案夾位於主要伺服器上，請在 [**如果備份檔案夾位於主要伺服器上**] 中輸入備份檔案夾的本機路徑，請在 [資料夾] 方塊中輸入本機路徑。</span><span class="sxs-lookup"><span data-stu-id="2df34-173">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box.</span></span> <span data-ttu-id="2df34-174">（如果備份檔案夾不在主要伺服器上，您可以將此方塊保留空白。）</span><span class="sxs-lookup"><span data-stu-id="2df34-174">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="2df34-175">如果主伺服器上的 SQL Server 服務帳戶是在本機系統帳戶下執行，您必須在主要伺服器上建立您的備份檔案夾，並指定該資料夾的本機路徑。</span><span class="sxs-lookup"><span data-stu-id="2df34-175">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
10. <span data-ttu-id="2df34-176">設定 [**刪除舊**檔的檔案]，並在參數**中不執行任何備份時發出警示**。</span><span class="sxs-lookup"><span data-stu-id="2df34-176">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
11. <span data-ttu-id="2df34-177">查看 [**備份作業**] 底下 [**排程**] 方塊中所列的備份排程。</span><span class="sxs-lookup"><span data-stu-id="2df34-177">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="2df34-178">若要自訂您的安裝排程，請根據需要按一下 [**排程**]，然後調整 SQL Server 代理程式排程。</span><span class="sxs-lookup"><span data-stu-id="2df34-178">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="2df34-179">使用您在主要資料庫中使用的相同設定。</span><span class="sxs-lookup"><span data-stu-id="2df34-179">Use the same settings that you used for the primary database.</span></span> 
  
12. <span data-ttu-id="2df34-180">在 [**壓縮**] 底下，選取 **[使用預設伺服器設定**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="2df34-180">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>
    
13. <span data-ttu-id="2df34-181">在 [**次要伺服器實例與資料庫**] 底下，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="2df34-181">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
14. <span data-ttu-id="2df34-182">按一下 **[連線]**，然後連線到您已設定為次要伺服器的 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="2df34-182">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
15. <span data-ttu-id="2df34-183">在 [**次要資料庫**] 方塊中，從清單中選取**mgc**資料庫。</span><span class="sxs-lookup"><span data-stu-id="2df34-183">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
16. <span data-ttu-id="2df34-184">在 [**初始化次要資料庫**] 索引標籤上，選取 [**否，次要資料庫已初始化**]。</span><span class="sxs-lookup"><span data-stu-id="2df34-184">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>
    
17. <span data-ttu-id="2df34-185">在 [**複製**檔案] 索引標籤上，于 [**複製的檔案目的地] 資料夾**中，輸入應將事務記錄備份複製到哪個資料夾的路徑，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="2df34-185">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**.</span></span> <span data-ttu-id="2df34-186">這個資料夾通常位於副伺服器上。</span><span class="sxs-lookup"><span data-stu-id="2df34-186">This folder is often located on the secondary server.</span></span>
    
18. <span data-ttu-id="2df34-187">開啟 [**腳本**設定] 下拉式清單，然後選取 [**腳本設定至新查詢] 視窗**。</span><span class="sxs-lookup"><span data-stu-id="2df34-187">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>
    
19. <span data-ttu-id="2df34-188">在 [新增查詢] 視窗的 [**資料庫屬性**] 中，按一下 **[確定]** 以開始設定程式。</span><span class="sxs-lookup"><span data-stu-id="2df34-188">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>
    
20. <span data-ttu-id="2df34-189">選取並執行查詢的前半部分（請參閱步驟18）至行：-- \* \* \* \* \* \*結束\* \* \* \* \* \*：要在主要：執行的腳本。</span><span class="sxs-lookup"><span data-stu-id="2df34-189">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="2df34-190">手動執行此腳本是必要的，因為 SQL Server Management Studio 不支援 SQL Server 記錄傳送設定中的多個主要資料庫。</span><span class="sxs-lookup"><span data-stu-id="2df34-190">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span> 
  
21. <span data-ttu-id="2df34-191">選取 [**取消**] 以關閉 [記錄檔案傳送設定] 面板，並建立能正確實現主要和鏡像資料庫（如果是容錯移轉）的記錄檔傳送的工作設定。</span><span class="sxs-lookup"><span data-stu-id="2df34-191">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>
    
22. <span data-ttu-id="2df34-192">手動將主要持久聊天資料庫容錯回復到主要。</span><span class="sxs-lookup"><span data-stu-id="2df34-192">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="2df34-193">這是使用商務用 Skype 伺服器管理命令介面和**CsDatabaseFailover** Cmdlet 來完成。</span><span class="sxs-lookup"><span data-stu-id="2df34-193">This is done by using the Skype for Business Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    

