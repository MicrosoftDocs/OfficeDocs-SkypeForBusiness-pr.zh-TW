---
title: 在商務用 Skype Server 2015 中設定 Persistent Chat Server 的高可用性和嚴重損壞修復
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 摘要：閱讀此主題以瞭解如何在商務用 Skype Server 2015 中設定 Persistent Chat Server 的高可用性和嚴重損壞修復。
ms.openlocfilehash: 10d9e2eb76873cedc82daea817a732b8feb379da
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802133"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="586f2-103">在商務用 Skype Server 2015 中設定 Persistent Chat Server 的高可用性和嚴重損壞修復</span><span class="sxs-lookup"><span data-stu-id="586f2-103">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="586f2-104">**摘要：** 閱讀此主題以瞭解如何在商務用 Skype Server 2015 中設定 Persistent Chat Server 的高可用性和嚴重損壞修復。</span><span class="sxs-lookup"><span data-stu-id="586f2-104">**Summary:** Read this topic to learn how to configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="586f2-105">商務用 Skype 伺服器支援多種模式的後端伺服器（包括資料庫鏡像）高可用性。</span><span class="sxs-lookup"><span data-stu-id="586f2-105">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="586f2-106">如需詳細資訊，請參閱 [在商務用 Skype Server 2015 中規劃高可用性和嚴重損壞修復](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="586f2-106">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="586f2-107">Persistent Chat Server 不支援 AlwaysOn 可用性群組。</span><span class="sxs-lookup"><span data-stu-id="586f2-107">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 

> [!NOTE] 
> <span data-ttu-id="586f2-108">商務用 Skype Server 2015 仍提供持續聊天，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="586f2-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="586f2-109">小組中提供相同的功能。</span><span class="sxs-lookup"><span data-stu-id="586f2-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="586f2-110">如需詳細資訊，請參閱 [Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="586f2-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="586f2-111">如果您需要使用持續聊天，您可以選擇將需要這項功能的使用者遷移至小組，或是繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="586f2-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="586f2-112">設定持續性聊天部署以取得高可用性和嚴重損壞修復之前，請務必熟悉在 [商務用 Skype server 2015 中規劃持續性聊天伺服器的高可用性和嚴重損壞修復](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)的概念。</span><span class="sxs-lookup"><span data-stu-id="586f2-112">Before you configure your Persistent Chat deployment for high availability and disaster recovery, be sure you are familiar with the concepts in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="586f2-113">下列主題中所述之 Persistent Chat Server 的嚴重損壞復原解決方案是在延伸的持久聊天伺服器集區上建立。</span><span class="sxs-lookup"><span data-stu-id="586f2-113">The disaster recovery solution for Persistent Chat Server described in these topics is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="586f2-114">規劃內容描述資源需求，以及可為 Persistent Chat Server 啟用高可用性和嚴重損壞修復的延伸集區拓撲，包括針對高可用性和 SQL Server 記錄傳送使用 SQL Server 鏡像，以進行嚴重損壞修復。</span><span class="sxs-lookup"><span data-stu-id="586f2-114">The planning content describes resource requirements, and the stretched pool topology that enables high availability and disaster recovery for Persistent Chat Server, including using SQL Server mirroring for high availability and SQL Server log shipping for disaster recovery.</span></span>
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a><span data-ttu-id="586f2-115">使用拓撲產生器來設定高可用性和嚴重損壞修復</span><span class="sxs-lookup"><span data-stu-id="586f2-115">Use Topology Builder to configure high availability and disaster recovery</span></span>

<span data-ttu-id="586f2-116">在 [拓撲產生器] 中，執行下列步驟，以設定 Persistent Chat Server 的高可用性和嚴重損壞修復。</span><span class="sxs-lookup"><span data-stu-id="586f2-116">Within Topology Builder, perform the following steps to configure high availability and disaster recovery for Persistent Chat Server.</span></span>
  
1. <span data-ttu-id="586f2-117">新增鏡像資料庫和記錄傳送次要資料庫 SQL Server 儲存區。</span><span class="sxs-lookup"><span data-stu-id="586f2-117">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>
    
2. <span data-ttu-id="586f2-118">編輯 Persistent Chat Server 服務屬性，使其：</span><span class="sxs-lookup"><span data-stu-id="586f2-118">Edit the Persistent Chat Server service properties to:</span></span>
    
    <span data-ttu-id="586f2-119">a.</span><span class="sxs-lookup"><span data-stu-id="586f2-119">a.</span></span> <span data-ttu-id="586f2-120">啟用主資料庫的鏡像。</span><span class="sxs-lookup"><span data-stu-id="586f2-120">Enable mirroring for the primary database.</span></span>
    
    <span data-ttu-id="586f2-121">b.</span><span class="sxs-lookup"><span data-stu-id="586f2-121">b.</span></span> <span data-ttu-id="586f2-122">新增主要鏡像 SQL Server 儲存區。</span><span class="sxs-lookup"><span data-stu-id="586f2-122">Add the primary mirror SQL Server store.</span></span>
    
    <span data-ttu-id="586f2-123">c.</span><span class="sxs-lookup"><span data-stu-id="586f2-123">c.</span></span> <span data-ttu-id="586f2-124">啟用 SQL Server 記錄傳送資料庫。</span><span class="sxs-lookup"><span data-stu-id="586f2-124">Enable the SQL Server Log Shipping database.</span></span>
    
    <span data-ttu-id="586f2-125">d.</span><span class="sxs-lookup"><span data-stu-id="586f2-125">d.</span></span> <span data-ttu-id="586f2-126">新增 SQL Server 記錄傳送次要 SQL Server 儲存區。</span><span class="sxs-lookup"><span data-stu-id="586f2-126">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    <span data-ttu-id="586f2-127">e.</span><span class="sxs-lookup"><span data-stu-id="586f2-127">e.</span></span> <span data-ttu-id="586f2-128">新增次要資料庫的 SQL Server 儲存區鏡像。</span><span class="sxs-lookup"><span data-stu-id="586f2-128">Add the SQL Server store mirror for the secondary database.</span></span>
    
    <span data-ttu-id="586f2-129">f.</span><span class="sxs-lookup"><span data-stu-id="586f2-129">f.</span></span> <span data-ttu-id="586f2-130">發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="586f2-130">Publish the topology.</span></span>
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="586f2-131">為 Persistent Chat Server 主資料庫設定 SQL Server 記錄傳送</span><span class="sxs-lookup"><span data-stu-id="586f2-131">Set up SQL Server log shipping for the Persistent Chat Server primary database</span></span>

<span data-ttu-id="586f2-132">使用 SQL Server Management Studio 連線至 Persistent Chat Server 次要記錄傳送資料庫實例，並確定 SQL Server 代理程式正在執行中。</span><span class="sxs-lookup"><span data-stu-id="586f2-132">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span> <span data-ttu-id="586f2-133">然後，連接至 Persistent Chat 主要資料庫實例，並執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="586f2-133">Then connect to the Persistent Chat primary database instance and perform the following steps:</span></span>
  
1. <span data-ttu-id="586f2-134">用滑鼠右鍵按一下 mgc 資料庫，然後按一下 **[屬性]**。</span><span class="sxs-lookup"><span data-stu-id="586f2-134">Right-click the mgc database, and then click **Properties**.</span></span>
    
2. <span data-ttu-id="586f2-135">在 **[選取頁面]** 下，按一下 **[交易記錄傳送]**。</span><span class="sxs-lookup"><span data-stu-id="586f2-135">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
3. <span data-ttu-id="586f2-136">選取 **[將此啟用為記錄傳送組態的主要資料庫]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="586f2-136">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
4. <span data-ttu-id="586f2-137">在 [交易記錄備份] 底下，按一下 [備份設定]。</span><span class="sxs-lookup"><span data-stu-id="586f2-137">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
5. <span data-ttu-id="586f2-138">在 [備份資料夾的網路路徑] 方塊中，輸入您為交易記錄備份資料夾建立之共用的網路路徑。</span><span class="sxs-lookup"><span data-stu-id="586f2-138">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>
    
6. <span data-ttu-id="586f2-p111">如果備份資料夾位在主要伺服器上，請在 [如果備份資料夾位於主要伺服器上，請輸入至該資料夾的本機路徑 (範例: c:\backup):] 方塊中輸入備份資料夾的本機路徑。(如果備份資料夾不在主要伺服器上，可將此方塊保留空白。)</span><span class="sxs-lookup"><span data-stu-id="586f2-p111">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\backup)** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="586f2-141">若主伺服器上的 SQL Server 服務帳戶是在本機系統帳戶之下執行，則必須在主伺服器上建立備份檔案夾，並指定該資料夾的本機路徑。</span><span class="sxs-lookup"><span data-stu-id="586f2-141">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
7. <span data-ttu-id="586f2-142">設定 **[指定刪除檔案的時限]** 和 **[如果未在此時間內進行備份，則發出警示]** 參數。</span><span class="sxs-lookup"><span data-stu-id="586f2-142">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
8. <span data-ttu-id="586f2-143">查看列在 **[備份作業]** 下的 **[排程]** 方塊中的備份排程。</span><span class="sxs-lookup"><span data-stu-id="586f2-143">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="586f2-144">若要自訂安裝的排程，請按一下 [ **排程**]，然後視需要調整 SQL Server 代理程式排程。</span><span class="sxs-lookup"><span data-stu-id="586f2-144">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>
    
9. <span data-ttu-id="586f2-145">在 [壓縮] 底下選取 [使用預設伺服器設定]，然後按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="586f2-145">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>
    
10. <span data-ttu-id="586f2-146">在 [次要伺服器執行個體與資料庫] 底下，按一下 [新增]。</span><span class="sxs-lookup"><span data-stu-id="586f2-146">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
11. <span data-ttu-id="586f2-147">按一下 **[連線]** ，並聯機至您已設定為次要伺服器的 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="586f2-147">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
12. <span data-ttu-id="586f2-148">在 **[次要資料庫]** 方塊中，從清單中選取 **[mgc]** 資料庫。</span><span class="sxs-lookup"><span data-stu-id="586f2-148">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
13. <span data-ttu-id="586f2-149">在 [ **初始化次要資料庫** ] 索引標籤上，選擇 [ **是]，產生主資料庫的完整備份，並將其還原至次要資料庫 (，並在) 中建立次要資料庫**。</span><span class="sxs-lookup"><span data-stu-id="586f2-149">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>
    
14. <span data-ttu-id="586f2-p113">在 [複製檔案] 索引標籤上的 [複製之檔案的目的資料夾] 方塊中，輸入複製交易記錄備份的目的資料夾路徑。此資料夾通常位在次要伺服器上。</span><span class="sxs-lookup"><span data-stu-id="586f2-p113">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied. This folder is often located on the secondary server.</span></span>
    
15. <span data-ttu-id="586f2-152">在 [複製工作] 底下，注意列示在 [排程] 方塊中的複製排程。</span><span class="sxs-lookup"><span data-stu-id="586f2-152">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="586f2-153">若要自訂安裝的排程，請按一下 [ **排程**]，然後視需要調整 SQL Server 代理程式排程。</span><span class="sxs-lookup"><span data-stu-id="586f2-153">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="586f2-154">此排程應與備份排程大致相同。</span><span class="sxs-lookup"><span data-stu-id="586f2-154">This schedule should be approximately the same as the backup schedule.</span></span>
    
16. <span data-ttu-id="586f2-155">在 [還原] 索引標籤上的 [還原備份時的資料庫狀態] 底下，選擇 [不復原模式] 選項。</span><span class="sxs-lookup"><span data-stu-id="586f2-155">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>
    
17. <span data-ttu-id="586f2-156">在 [延遲還原備份至少:] 底下，選取 [0 分鐘]。</span><span class="sxs-lookup"><span data-stu-id="586f2-156">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>
    
18. <span data-ttu-id="586f2-157">在 [如果未在此時間內進行還原，則發出警示] 底下，選擇警示臨界值。</span><span class="sxs-lookup"><span data-stu-id="586f2-157">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>
    
19. <span data-ttu-id="586f2-158">在 [還原工作] 底下，查看列示在 [排程] 方塊中的還原排程。</span><span class="sxs-lookup"><span data-stu-id="586f2-158">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="586f2-159">若要自訂安裝的排程，請按一下 [ **排程**]，並視需要調整 SQL Server 代理程式排程，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="586f2-159">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="586f2-160">此排程應與備份排程大致相同。</span><span class="sxs-lookup"><span data-stu-id="586f2-160">This schedule should be approximately the same as the backup schedule.</span></span>
    
20. <span data-ttu-id="586f2-161">在 [資料庫內容] 對話方塊上按一下 [確定]，即開始設定程序。</span><span class="sxs-lookup"><span data-stu-id="586f2-161">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a><span data-ttu-id="586f2-162">設定主要鏡像與次要資料庫之間的 SQL Server 記錄傳送</span><span class="sxs-lookup"><span data-stu-id="586f2-162">Set up SQL Server log shipping between the primary mirror and the secondary database</span></span>

<span data-ttu-id="586f2-163">若主要持久聊天資料庫容錯移轉至其鏡像資料庫，請執行下列步驟，以繼續進行記錄傳送。</span><span class="sxs-lookup"><span data-stu-id="586f2-163">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>
  
1. <span data-ttu-id="586f2-164">手動將主要持久聊天資料庫容錯移轉至鏡像。</span><span class="sxs-lookup"><span data-stu-id="586f2-164">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="586f2-165">這是透過商務用 Skype Server 管理命令介面和 **Invoke-CsDatabaseFailover** Cmdlet 來完成。</span><span class="sxs-lookup"><span data-stu-id="586f2-165">This is done by using the Skype for Business Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    
2. <span data-ttu-id="586f2-166">使用 SQL Server Management Studio 連線至主要 Persistent Chat Server 鏡像實例。</span><span class="sxs-lookup"><span data-stu-id="586f2-166">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>
    
3. <span data-ttu-id="586f2-167">確定 SQL Server 代理程式正在執行中。</span><span class="sxs-lookup"><span data-stu-id="586f2-167">Be sure that the SQL Server Agent is running.</span></span>
    
4. <span data-ttu-id="586f2-168">用滑鼠右鍵按一下 mgc 資料庫，然後按一下 **[屬性]**。</span><span class="sxs-lookup"><span data-stu-id="586f2-168">Right-click the mgc database, and then click **Properties**.</span></span>
    
5. <span data-ttu-id="586f2-169">在 **[選取頁面]** 下，按一下 **[交易記錄傳送]**。</span><span class="sxs-lookup"><span data-stu-id="586f2-169">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
6. <span data-ttu-id="586f2-170">選取 **[將此啟用為記錄傳送組態的主要資料庫]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="586f2-170">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
7. <span data-ttu-id="586f2-171">在 **[交易記錄備份]** 下，按一下 **[備份設定]**。</span><span class="sxs-lookup"><span data-stu-id="586f2-171">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
8. <span data-ttu-id="586f2-172">在 **[備份資料夾的網路路徑]** 方塊中，鍵入您為異動記錄備份資料夾所建立的共用的網路路徑。</span><span class="sxs-lookup"><span data-stu-id="586f2-172">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>
    
9. <span data-ttu-id="586f2-p117">如果備份資料夾位於主要伺服器上，請在 **[如果備份資料夾位於主要伺服器上，請輸入至該資料夾的本機路徑]** 方塊中鍵入備份資料夾的本機路徑 (如果備份資料夾不是在主要伺服器上，您可以不要選取此方塊)。</span><span class="sxs-lookup"><span data-stu-id="586f2-p117">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="586f2-175">若主伺服器上的 SQL Server 服務帳戶是在本機系統帳戶之下執行，則必須在主伺服器上建立備份檔案夾，並指定該資料夾的本機路徑。</span><span class="sxs-lookup"><span data-stu-id="586f2-175">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
10. <span data-ttu-id="586f2-176">設定 **[指定刪除檔案的時限]** 和 **[如果未在此時間內進行備份，則發出警示]** 參數。</span><span class="sxs-lookup"><span data-stu-id="586f2-176">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
11. <span data-ttu-id="586f2-177">查看列在 **[備份作業]** 下的 **[排程]** 方塊中的備份排程。</span><span class="sxs-lookup"><span data-stu-id="586f2-177">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="586f2-178">若要自訂安裝的排程，請按一下 [ **排程**]，然後視需要調整 SQL Server 代理程式排程。</span><span class="sxs-lookup"><span data-stu-id="586f2-178">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="586f2-179">使用和主要資料庫相同的設定。</span><span class="sxs-lookup"><span data-stu-id="586f2-179">Use the same settings that you used for the primary database.</span></span> 
  
12. <span data-ttu-id="586f2-180">在 **[壓縮]** 下，選取 **[使用預設伺服器設定]**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="586f2-180">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>
    
13. <span data-ttu-id="586f2-181">在 **[次要伺服器執行個體與資料庫]** 下，按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="586f2-181">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
14. <span data-ttu-id="586f2-182">按一下 **[連線]**，然後連線至您已設定為次要伺服器的 SQL Server 的執行個體。</span><span class="sxs-lookup"><span data-stu-id="586f2-182">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
15. <span data-ttu-id="586f2-183">在 **[次要資料庫]** 方塊中，從清單中選取 **[mgc]** 資料庫。</span><span class="sxs-lookup"><span data-stu-id="586f2-183">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
16. <span data-ttu-id="586f2-184">在 **[初始化次要資料庫]** 索引標籤上，選取選項 **[否，次要資料庫已初始化]**。</span><span class="sxs-lookup"><span data-stu-id="586f2-184">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>
    
17. <span data-ttu-id="586f2-p119">在 **[複製檔案]** 索引標籤的 **[複製之檔案的目的資料夾]** 中，鍵入應複製異動記錄備份的資料夾的路徑，然後按一下 **[確定]**。這個資料夾通常位於次要伺服器上。</span><span class="sxs-lookup"><span data-stu-id="586f2-p119">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**. This folder is often located on the secondary server.</span></span>
    
18. <span data-ttu-id="586f2-187">開啟 **[指令碼設定]** 下拉式清單，然後選取 **[編寫組態的指令碼至新增查詢視窗]**。</span><span class="sxs-lookup"><span data-stu-id="586f2-187">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>
    
19. <span data-ttu-id="586f2-188">在新增查詢視窗的 **[資料庫屬性]** 中，按一下 **[確定]** 開始設定程序。</span><span class="sxs-lookup"><span data-stu-id="586f2-188">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>
    
20. <span data-ttu-id="586f2-189">選取並執行查詢的前半部 (請參閱 step 18) 至行：-- \* \* \* \* \* \* End： Script to 執行主要： \* \* \* \* \* \* 。</span><span class="sxs-lookup"><span data-stu-id="586f2-189">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="586f2-190">手動執行這個腳本是必要的，因為 SQL Server Management Studio 不支援 SQL Server 記錄傳送設定中的多個主資料庫。</span><span class="sxs-lookup"><span data-stu-id="586f2-190">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span> 
  
21. <span data-ttu-id="586f2-191">選取 **[取消]** 以關閉記錄檔傳送設定面板，然後建立工作設定，正確實作主要和鏡像資料庫 (若容錯移轉) 的記錄檔傳送。</span><span class="sxs-lookup"><span data-stu-id="586f2-191">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>
    
22. <span data-ttu-id="586f2-192">手動將主要持久聊天資料庫回復回主要。</span><span class="sxs-lookup"><span data-stu-id="586f2-192">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="586f2-193">這是透過商務用 Skype Server 管理命令介面和 **Invoke-CsDatabaseFailover** Cmdlet 來完成。</span><span class="sxs-lookup"><span data-stu-id="586f2-193">This is done by using the Skype for Business Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    

