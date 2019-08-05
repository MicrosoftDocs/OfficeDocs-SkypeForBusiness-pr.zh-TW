---
title: 管理常設聊天室伺服器的高可用性和災害復原
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: '摘要: 瞭解如何在商務用 Skype Server 2015 中管理持久聊天伺服器的高可用性和災害復原。'
ms.openlocfilehash: ff30bcdd99a4c92bd8fbd8f0a5c4bcedd8aa63b0
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2019
ms.locfileid: "36194065"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="254f0-103">管理常設聊天室伺服器的高可用性和災害復原</span><span class="sxs-lookup"><span data-stu-id="254f0-103">Manage high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="254f0-104">**摘要:** 瞭解如何在商務用 Skype Server 2015 中管理持久聊天伺服器的高可用性和災害復原。</span><span class="sxs-lookup"><span data-stu-id="254f0-104">**Summary:** Learn how to manage Persistent Chat Server high availability and disaster recovery in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="254f0-105">本主題說明如何進行容錯移轉及自動容錯回復持久聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="254f0-105">This topic describes how to fail over and fail back Persistent Chat Server.</span></span> <span data-ttu-id="254f0-106">在閱讀本主題之前, 請務必閱讀適用于[商務用 Skype server 2015 中持續性聊天伺服器的高可用性和災難復原方案](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md), 以及[在 Skype 中設定持續聊天伺服器的高可用性與災難復原商務伺服器 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="254f0-106">Before reading this topic, be sure to read [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) and [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>

> [!NOTE]
> <span data-ttu-id="254f0-107">商務用 Skype Server 2015 提供持續聊天, 但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="254f0-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="254f0-108">團隊中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="254f0-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="254f0-109">如需詳細資訊, 請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="254f0-109">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="254f0-110">如果您需要使用持續聊天, 您可以選擇將需要此功能的使用者遷移至小組, 或繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="254f0-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="fail-over-persistent-chat-server"></a><span data-ttu-id="254f0-111">永久聊天伺服器容錯移轉</span><span class="sxs-lookup"><span data-stu-id="254f0-111">Fail over Persistent Chat Server</span></span>

<span data-ttu-id="254f0-112">持續性聊天伺服器的容錯移轉主要是手動程式設計。</span><span class="sxs-lookup"><span data-stu-id="254f0-112">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>
  
<span data-ttu-id="254f0-113">容錯移轉程式的假設是次要資料中心已啟動且正在執行, 但主要持久聊天資料庫所在的持久聊天伺服器服務完全無法使用, 包括下列各項:</span><span class="sxs-lookup"><span data-stu-id="254f0-113">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>
  
- <span data-ttu-id="254f0-114">持續聊天伺服器主資料庫和持續聊天伺服器鏡像資料庫已關閉。</span><span class="sxs-lookup"><span data-stu-id="254f0-114">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>
    
- <span data-ttu-id="254f0-115">商務用 Skype Server 前端伺服器已關閉。</span><span class="sxs-lookup"><span data-stu-id="254f0-115">Skype for Business Server Front End Server is down.</span></span>
    
<span data-ttu-id="254f0-116">此程式是以兩個基本步驟為基礎:</span><span class="sxs-lookup"><span data-stu-id="254f0-116">The procedure is based on two basic steps:</span></span>
  
- <span data-ttu-id="254f0-117">復原主要持久聊天資料庫 (mgc)。</span><span class="sxs-lookup"><span data-stu-id="254f0-117">Recover the primary Persistent Chat database (mgc).</span></span>
    
- <span data-ttu-id="254f0-118">為新的主資料庫建立鏡像。</span><span class="sxs-lookup"><span data-stu-id="254f0-118">Establish mirroring for the new primary database.</span></span>
    
<span data-ttu-id="254f0-119">永久聊天規範資料庫 (mgccomp) 未進行容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="254f0-119">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="254f0-120">此資料庫的內容是暫時性的, 而且會在合規性配接器處理資料時清除。</span><span class="sxs-lookup"><span data-stu-id="254f0-120">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="254f0-121">您的責任是永久聊天管理員, 正確管理配接器輸出以避免資料遺失。</span><span class="sxs-lookup"><span data-stu-id="254f0-121">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>
  
<span data-ttu-id="254f0-122">若要容錯移轉持久聊天伺服器:</span><span class="sxs-lookup"><span data-stu-id="254f0-122">To fail over Persistent Chat Server:</span></span>
  
1. <span data-ttu-id="254f0-123">從持續聊天伺服器備份記錄傳送資料庫中移除記錄傳送。</span><span class="sxs-lookup"><span data-stu-id="254f0-123">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
   - <span data-ttu-id="254f0-124">使用 SQL Server Management Studio, 連線到持久聊天伺服器備份 mgc 資料庫所在的資料庫實例。</span><span class="sxs-lookup"><span data-stu-id="254f0-124">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
   - <span data-ttu-id="254f0-125">開啟 [查詢] 視窗至 [主資料庫]。</span><span class="sxs-lookup"><span data-stu-id="254f0-125">Open a query window to the master database.</span></span>
    
   - <span data-ttu-id="254f0-126">使用下列命令來刪除記錄傳送:</span><span class="sxs-lookup"><span data-stu-id="254f0-126">Use the following command to drop log shipping:</span></span>
    
   ```
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. <span data-ttu-id="254f0-127">將備份共用中的任何 uncopied 備份檔案複製到備份伺服器的 [複製目的地] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="254f0-127">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>
    
3. <span data-ttu-id="254f0-128">將任何未套用的事務記錄備份以順序套用到次要資料庫。</span><span class="sxs-lookup"><span data-stu-id="254f0-128">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="254f0-129">如需詳細資訊, 請參閱[如何: 套用事務記錄備份 (transact-sql)](https://go.microsoft.com/fwlink/p/?linkid=247428)。</span><span class="sxs-lookup"><span data-stu-id="254f0-129">For details, see [How to: Apply a Transaction Log Backup (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).</span></span>
    
4. <span data-ttu-id="254f0-130">讓備份 mgc 資料庫在線上。</span><span class="sxs-lookup"><span data-stu-id="254f0-130">Bring the backup mgc database online.</span></span> <span data-ttu-id="254f0-131">使用在步驟1b 中開啟的 [查詢] 視窗, 執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="254f0-131">Using the query window that opens in step 1b, do the following:</span></span>
    
   - <span data-ttu-id="254f0-132">結束所有 mgc 資料庫連線 (如果有的話):</span><span class="sxs-lookup"><span data-stu-id="254f0-132">End all connections to the mgc database, if there are any:</span></span>
    
   - <span data-ttu-id="254f0-133">**exec sp_who2** , 以找出 mgc 資料庫的連線。</span><span class="sxs-lookup"><span data-stu-id="254f0-133">**exec sp_who2** to identify connections to the mgc database.</span></span>
    
   - <span data-ttu-id="254f0-134">\*\*kill \<spid\> \*\*以結束這些連線。</span><span class="sxs-lookup"><span data-stu-id="254f0-134">**kill \<spid\>** to end these connections.</span></span>
    
   - <span data-ttu-id="254f0-135">讓資料庫處於線上狀態:</span><span class="sxs-lookup"><span data-stu-id="254f0-135">Bring the database online:</span></span>
    
   - <span data-ttu-id="254f0-136">**使用恢復來還原資料庫 mgc**。</span><span class="sxs-lookup"><span data-stu-id="254f0-136">**restore database mgc with recovery**.</span></span>
    
5. <span data-ttu-id="254f0-137">在商務用 Skype Server Management 命令介面中, 使用命令**CsPersistentChatState 身分識別 "服務: atl-cs-001.litwareinc.com"-PoolState FailedOver**容錯移轉至 mgc 備份資料庫。</span><span class="sxs-lookup"><span data-stu-id="254f0-137">In Skype for Business Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="254f0-138">請務必以 atl-cs-001.litwareinc.com 的持久聊天池來取代完整的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="254f0-138">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="254f0-139">Mgc 備份資料庫現在是作為主要資料庫。</span><span class="sxs-lookup"><span data-stu-id="254f0-139">The mgc backup database now serves as the primary database.</span></span>
    
6. <span data-ttu-id="254f0-140">在商務用 Skype Server Management 命令介面中, 使用**CsMirrorDatabase** Cmdlet 來為現在作為主要資料庫的備份資料庫建立高可用性鏡像。</span><span class="sxs-lookup"><span data-stu-id="254f0-140">In Skype for Business Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="254f0-141">使用備份資料庫實例作為主要資料庫, 將備份鏡像資料庫實例做為鏡像實例。</span><span class="sxs-lookup"><span data-stu-id="254f0-141">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="254f0-142">這與在安裝期間最初為主要資料庫設定的同一個鏡像。</span><span class="sxs-lookup"><span data-stu-id="254f0-142">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span>
    
7. <span data-ttu-id="254f0-143">設定持續聊天伺服器的使用中伺服器。</span><span class="sxs-lookup"><span data-stu-id="254f0-143">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="254f0-144">從商務用 Skype Server Management Shell, 使用**CsPersistentChatActiveServer** Cmdlet 來設定作用中伺服器的清單。</span><span class="sxs-lookup"><span data-stu-id="254f0-144">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="254f0-145">所有的作用中伺服器都必須位於與新的主資料庫相同的資料中心內, 或是在具有低延遲/高頻寬連接的資料中心中。</span><span class="sxs-lookup"><span data-stu-id="254f0-145">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
    <span data-ttu-id="254f0-146">此時, 來自持久聊天伺服器主要資料庫的容錯移轉至持續聊天伺服器備份資料庫成功完成。</span><span class="sxs-lookup"><span data-stu-id="254f0-146">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>
    
## <a name="fail-back-persistent-chat-server"></a><span data-ttu-id="254f0-147">容錯回復持久聊天伺服器</span><span class="sxs-lookup"><span data-stu-id="254f0-147">Fail back Persistent Chat Server</span></span>

<span data-ttu-id="254f0-148">此程式概述從持續聊天伺服器失敗復原所需的步驟, 以及從主要資料中心重新建立作業。</span><span class="sxs-lookup"><span data-stu-id="254f0-148">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>
  
<span data-ttu-id="254f0-149">在持續聊天伺服器發生故障期間, 主要資料中心會受到完全停機, 且主要和鏡像資料庫無法使用。</span><span class="sxs-lookup"><span data-stu-id="254f0-149">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="254f0-150">主要資料中心會容錯移轉至備份伺服器。</span><span class="sxs-lookup"><span data-stu-id="254f0-150">The primary data center fails over to the backup server.</span></span>
  
<span data-ttu-id="254f0-151">下列程式會在主要資料中心重新開機後還原正常作業, 且已重建伺服器。</span><span class="sxs-lookup"><span data-stu-id="254f0-151">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="254f0-152">此程式假設主要資料中心已從總停機中復原, 且 mgc 資料庫和 mgccomp 資料庫已使用拓撲產生器重建並重新安裝。</span><span class="sxs-lookup"><span data-stu-id="254f0-152">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>
  
<span data-ttu-id="254f0-153">此程式也假設在容錯移轉期間, 沒有部署新的鏡像與備份伺服器, 而且部署的伺服器是備份伺服器及其鏡像伺服器 (在先前的 [容錯移轉前聊天伺服器] 中定義)。</span><span class="sxs-lookup"><span data-stu-id="254f0-153">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in Fail over Persistent Chat Server previously.</span></span>
  
<span data-ttu-id="254f0-154">這些步驟的設計目的是要在災難發生之前, 復原配置, 從而將主要伺服器的容錯移轉到備份伺服器。</span><span class="sxs-lookup"><span data-stu-id="254f0-154">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>
  
1. <span data-ttu-id="254f0-155">從商務用 Skype Server Management Shell 中使用**CsPersistentChatActiveServer** Cmdlet, 以清除永久聊天伺服器作用中伺服器清單中的所有伺服器。</span><span class="sxs-lookup"><span data-stu-id="254f0-155">Clear all servers from the Persistent Chat Server Active Server list by using the **Set-CsPersistentChatActiveServer** cmdlet from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="254f0-156">這會在回切期間停止連線到 mgc 資料庫和 mgccomp 資料庫的所有持久聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="254f0-156">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="254f0-157">次要持續聊天伺服器上的 SQL Server 代理程式應該在特許帳戶下執行。</span><span class="sxs-lookup"><span data-stu-id="254f0-157">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="254f0-158">具體說來, 帳戶必須包括:</span><span class="sxs-lookup"><span data-stu-id="254f0-158">Specifically, the account must include:</span></span> 
  
   - <span data-ttu-id="254f0-159">讀取備份所要加入的網路共用的存取權。</span><span class="sxs-lookup"><span data-stu-id="254f0-159">Read access to the network share that backups are being placed in.</span></span>
    
   - <span data-ttu-id="254f0-160">寫入要複本備份之特定本機目錄的存取權。</span><span class="sxs-lookup"><span data-stu-id="254f0-160">Write access to the specific local directory that the backups are being copied to.</span></span>
    
2. <span data-ttu-id="254f0-161">停用備份 mgc 資料庫上的鏡像:</span><span class="sxs-lookup"><span data-stu-id="254f0-161">Disable mirroring on the backup mgc database:</span></span>
    
   - <span data-ttu-id="254f0-162">使用 SQL Server Management Studio, 連線至備份 mgc 實例。</span><span class="sxs-lookup"><span data-stu-id="254f0-162">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="254f0-163">以滑鼠右鍵按一下 mgc 資料庫, 指向 [**任務**], 然後按一下 [**鏡像**]。</span><span class="sxs-lookup"><span data-stu-id="254f0-163">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
   - <span data-ttu-id="254f0-164">按一下 [**移除鏡像**]。</span><span class="sxs-lookup"><span data-stu-id="254f0-164">Click **Remove Mirroring**.</span></span>
    
   - <span data-ttu-id="254f0-165">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="254f0-165">Click **OK**.</span></span>
    
   - <span data-ttu-id="254f0-166">對 mgccomp 資料庫執行相同的步驟。</span><span class="sxs-lookup"><span data-stu-id="254f0-166">Perform the same steps with the mgccomp database.</span></span>
    
3. <span data-ttu-id="254f0-167">備份 mgc 資料庫, 以便將它還原到新的主資料庫:</span><span class="sxs-lookup"><span data-stu-id="254f0-167">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
   - <span data-ttu-id="254f0-168">使用 SQL Server Management Studio, 連線至備份 mgc 實例。</span><span class="sxs-lookup"><span data-stu-id="254f0-168">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="254f0-169">以滑鼠右鍵按一下 mgc 資料庫, 指向 [**任務**], 然後按一下 [**備份**]。</span><span class="sxs-lookup"><span data-stu-id="254f0-169">Right-click the mgc database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="254f0-170">[**備份資料庫**] 對話方塊隨即出現。</span><span class="sxs-lookup"><span data-stu-id="254f0-170">The **Back Up Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="254f0-171">在 [**備份類型**] 中, 選取 [**全**選]。</span><span class="sxs-lookup"><span data-stu-id="254f0-171">In **Backup type**, select **Full**.</span></span>
    
   - <span data-ttu-id="254f0-172">針對 [**備份元件**], 按一下 [**資料庫**]。</span><span class="sxs-lookup"><span data-stu-id="254f0-172">For **Backup component**, click **Database**.</span></span>
    
   - <span data-ttu-id="254f0-173">要麼接受**名稱**中建議的預設備份組名稱, 要麼為備份組輸入不同的名稱。</span><span class="sxs-lookup"><span data-stu-id="254f0-173">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
   -  <span data-ttu-id="254f0-174">\* \<選用\> \* 在 [**描述**] 中, 輸入備份組的描述。</span><span class="sxs-lookup"><span data-stu-id="254f0-174">*\<Optional\>*  In **Description**, enter a description of the backup set.</span></span>
    
   - <span data-ttu-id="254f0-175">從目的地清單移除預設備份位置。</span><span class="sxs-lookup"><span data-stu-id="254f0-175">Remove the default backup location from the destination list.</span></span>
    
   - <span data-ttu-id="254f0-176">使用您為記錄傳送建立的共用位置路徑, 將檔案新增至清單。</span><span class="sxs-lookup"><span data-stu-id="254f0-176">Add a file to the list by using the path to the share location that you established for log shipping.</span></span> <span data-ttu-id="254f0-177">這個路徑可供主要資料庫和備份資料庫使用。</span><span class="sxs-lookup"><span data-stu-id="254f0-177">This path is available to the primary database and to the backup database.</span></span>
    
   - <span data-ttu-id="254f0-178">按一下 **[確定**] 以關閉對話方塊並開始備份程式。</span><span class="sxs-lookup"><span data-stu-id="254f0-178">Click **OK** to close the dialog box and begin the backup process.</span></span>
    
4. <span data-ttu-id="254f0-179">使用在上一個步驟中建立的備份資料庫來還原主要資料庫。</span><span class="sxs-lookup"><span data-stu-id="254f0-179">Restore the primary database by using the backup database created in the previous step.</span></span>
    
   - <span data-ttu-id="254f0-180">使用 SQL Server Management Studio, 連線到主要的 mgc 實例。</span><span class="sxs-lookup"><span data-stu-id="254f0-180">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
   - <span data-ttu-id="254f0-181">以滑鼠右鍵按一下 mgc 資料庫, 指向 [**任務**], 指向 [**還原**], 然後按一下 [**資料庫**]。</span><span class="sxs-lookup"><span data-stu-id="254f0-181">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**.</span></span> <span data-ttu-id="254f0-182">[**還原資料庫**] 對話方塊隨即出現。</span><span class="sxs-lookup"><span data-stu-id="254f0-182">The **Restore Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="254f0-183">選取 [**從裝置**]。</span><span class="sxs-lookup"><span data-stu-id="254f0-183">Select **From Device**.</span></span>
    
   - <span data-ttu-id="254f0-184">按一下 [流覽] 按鈕, 即可開啟 [**指定備份**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="254f0-184">Click the browse button, which opens the **Specify Backup** dialog box.</span></span> <span data-ttu-id="254f0-185">在 [**備份媒體**] \*\*\*\* 中, 選取 [檔案]。</span><span class="sxs-lookup"><span data-stu-id="254f0-185">In **Backup media**, select **File**.</span></span> <span data-ttu-id="254f0-186">按一下 [**新增**], 選取您在步驟3中建立的備份檔案, 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="254f0-186">Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
   - <span data-ttu-id="254f0-187">在 [**選取要還原的備份組**] 中, 選取 [備份]。</span><span class="sxs-lookup"><span data-stu-id="254f0-187">In **Select the backup sets to restore**, select the backup.</span></span>
    
   - <span data-ttu-id="254f0-188">按一下 [**選取頁面**] 窗格中的 [**選項**]。</span><span class="sxs-lookup"><span data-stu-id="254f0-188">Click **Options** in the **Select a page** pane.</span></span>
    
   - <span data-ttu-id="254f0-189">在 [**還原選項**] 中, 選取 **[覆寫現有的資料庫**]。</span><span class="sxs-lookup"><span data-stu-id="254f0-189">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
   - <span data-ttu-id="254f0-190">在 [**恢復狀態**] 中, 選取 **[讓資料庫可供使用**]。</span><span class="sxs-lookup"><span data-stu-id="254f0-190">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
   - <span data-ttu-id="254f0-191">按一下 **[確定]** 以開始還原程式。</span><span class="sxs-lookup"><span data-stu-id="254f0-191">Click **OK** to begin the restoration process.</span></span>
    
5. <span data-ttu-id="254f0-192">為主要資料庫設定 SQL Server 記錄傳送。</span><span class="sxs-lookup"><span data-stu-id="254f0-192">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="254f0-193">請遵循在[商務用 Skype server 2015 中設定持續聊天伺服器的高可用性和災難](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)復原中的程式, 以建立主要 mgc 資料庫的記錄傳送。</span><span class="sxs-lookup"><span data-stu-id="254f0-193">Follow the procedures in [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) to establish log shipping for the primary mgc database.</span></span>
    
6. <span data-ttu-id="254f0-194">設定持續聊天伺服器的使用中伺服器。</span><span class="sxs-lookup"><span data-stu-id="254f0-194">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="254f0-195">從商務用 Skype Server Management Shell, 使用**CsPersistentChatActiveServer** Cmdlet 來設定作用中伺服器的清單。</span><span class="sxs-lookup"><span data-stu-id="254f0-195">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="254f0-196">所有的作用中伺服器都必須位於與新的主資料庫相同的資料中心內, 或是在具有低延遲/高頻寬連接的資料中心中。</span><span class="sxs-lookup"><span data-stu-id="254f0-196">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
<span data-ttu-id="254f0-197">若要將池還原到其正常狀態, 請執行下列 Windows PowerShell 命令:</span><span class="sxs-lookup"><span data-stu-id="254f0-197">To restore the pool to its normal state run the following Windows PowerShell command:</span></span>
  
```
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

<span data-ttu-id="254f0-198">如需詳細資訊, 請參閱[CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="254f0-198">For more information, see the help topic for the [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) cmdlet.</span></span>
  

