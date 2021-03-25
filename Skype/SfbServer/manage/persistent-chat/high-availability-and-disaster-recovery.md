---
title: 在商務用 Skype Server 2015 中管理 Persistent Chat Server 的高可用性和嚴重損壞修復
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: 摘要：瞭解如何在商務用 Skype Server 2015 中管理 Persistent Chat Server 的高可用性和嚴重損壞修復。
ms.openlocfilehash: 4fb3a38fadf2a8a063715e389718859dcc7ddbdd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122407"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="40c0f-103">在商務用 Skype Server 2015 中管理 Persistent Chat Server 的高可用性和嚴重損壞修復</span><span class="sxs-lookup"><span data-stu-id="40c0f-103">Manage high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="40c0f-104">**摘要：** 瞭解如何在商務用 Skype Server 2015 中管理 Persistent Chat Server 的高可用性和嚴重損壞修復。</span><span class="sxs-lookup"><span data-stu-id="40c0f-104">**Summary:** Learn how to manage Persistent Chat Server high availability and disaster recovery in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="40c0f-105">本主題說明如何容錯移轉和容錯回復持久聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="40c0f-105">This topic describes how to fail over and fail back Persistent Chat Server.</span></span> <span data-ttu-id="40c0f-106">閱讀本主題之前，請務必閱讀 [Plan For Persistent Chat server 的高可用性和嚴重損壞修復方案](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) ，以商務2015用 skype server [2015，設定 persistent chat server 的高可用性和嚴重損壞修復](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="40c0f-106">Before reading this topic, be sure to read [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) and [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>

> [!NOTE]
> <span data-ttu-id="40c0f-107">商務用 Skype Server 2015 仍提供持續聊天，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="40c0f-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="40c0f-108">小組中提供相同的功能。</span><span class="sxs-lookup"><span data-stu-id="40c0f-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="40c0f-109">如需詳細資訊，請參閱 [Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="40c0f-109">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="40c0f-110">如果您需要使用持續聊天，您可以選擇將需要這項功能的使用者遷移至小組，或是繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="40c0f-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="fail-over-persistent-chat-server"></a><span data-ttu-id="40c0f-111">容錯移轉 Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="40c0f-111">Fail over Persistent Chat Server</span></span>

<span data-ttu-id="40c0f-112">Persistent Chat Server 的容錯移轉是設計為主要是手動處理常式。</span><span class="sxs-lookup"><span data-stu-id="40c0f-112">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>
  
<span data-ttu-id="40c0f-113">容錯移轉程式的假設是在次要資料中心啟動並執行，但主要 Persistent Chat 資料庫所在的 Persistent Chat Server 服務完全無法使用，包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="40c0f-113">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>
  
- <span data-ttu-id="40c0f-114">Persistent Chat Server 主資料庫和 Persistent Chat Server 鏡像資料庫已停機。</span><span class="sxs-lookup"><span data-stu-id="40c0f-114">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>
    
- <span data-ttu-id="40c0f-115">商務用 Skype Server 前端伺服器已關機。</span><span class="sxs-lookup"><span data-stu-id="40c0f-115">Skype for Business Server Front End Server is down.</span></span>
    
<span data-ttu-id="40c0f-116">此程序主要有兩個基本步驟：</span><span class="sxs-lookup"><span data-stu-id="40c0f-116">The procedure is based on two basic steps:</span></span>
  
- <span data-ttu-id="40c0f-117">復原主要 Persistent Chat database (mgc) 。</span><span class="sxs-lookup"><span data-stu-id="40c0f-117">Recover the primary Persistent Chat database (mgc).</span></span>
    
- <span data-ttu-id="40c0f-118">建立新主要資料庫的鏡像。</span><span class="sxs-lookup"><span data-stu-id="40c0f-118">Establish mirroring for the new primary database.</span></span>
    
<span data-ttu-id="40c0f-119">Persistent Chat 規範資料庫 (mgccomp) 未進行容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="40c0f-119">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="40c0f-120">此資料庫的內容僅為暫時性，且會在規範介面卡處理資料時被清除。</span><span class="sxs-lookup"><span data-stu-id="40c0f-120">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="40c0f-121">您的責任是 Persistent Chat Administrator，可正確管理配接器輸出以避免資料遺失。</span><span class="sxs-lookup"><span data-stu-id="40c0f-121">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>
  
<span data-ttu-id="40c0f-122">若要容錯移轉 Persistent Chat Server：</span><span class="sxs-lookup"><span data-stu-id="40c0f-122">To fail over Persistent Chat Server:</span></span>
  
1. <span data-ttu-id="40c0f-123">從 Persistent Chat Server 備份記錄傳送資料庫中移除記錄傳送。</span><span class="sxs-lookup"><span data-stu-id="40c0f-123">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
   - <span data-ttu-id="40c0f-124">使用 SQL Server Management Studio，連接至 Persistent Chat Server backup mgc 資料庫所在的資料庫實例。</span><span class="sxs-lookup"><span data-stu-id="40c0f-124">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
   - <span data-ttu-id="40c0f-125">開啟 Master 資料庫的查詢視窗。</span><span class="sxs-lookup"><span data-stu-id="40c0f-125">Open a query window to the master database.</span></span>
    
   - <span data-ttu-id="40c0f-126">使用下列命令移除記錄傳送：</span><span class="sxs-lookup"><span data-stu-id="40c0f-126">Use the following command to drop log shipping:</span></span>
    
   ```SQL
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. <span data-ttu-id="40c0f-127">從備份共用複製所有未複製的備份檔案至備份伺服器的複製目的地資料夾。</span><span class="sxs-lookup"><span data-stu-id="40c0f-127">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>
    
3. <span data-ttu-id="40c0f-128">依序將所有未套用的交易記錄備份套用至次要資料庫。</span><span class="sxs-lookup"><span data-stu-id="40c0f-128">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="40c0f-129">如需詳細資訊，請參閱 how [to：將交易記錄備份 (Transact-SQL) ](/previous-versions/sql/sql-server-2008-r2/ms187607(v=sql.105))。</span><span class="sxs-lookup"><span data-stu-id="40c0f-129">For details, see [How to: Apply a Transaction Log Backup (Transact-SQL)](/previous-versions/sql/sql-server-2008-r2/ms187607(v=sql.105)).</span></span>
    
4. <span data-ttu-id="40c0f-p105">若要使備份 mgc 資料庫上線。請使用步驟 1b 中開啟的查詢視窗，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="40c0f-p105">Bring the backup mgc database online. Using the query window that opens in step 1b, do the following:</span></span>
    
   - <span data-ttu-id="40c0f-132">結束所有 mgc 資料庫的連線 (若有連線)：</span><span class="sxs-lookup"><span data-stu-id="40c0f-132">End all connections to the mgc database, if there are any:</span></span>
    
   - <span data-ttu-id="40c0f-133">**exec sp_who2** 來識別 mgc 資料庫的連線。</span><span class="sxs-lookup"><span data-stu-id="40c0f-133">**exec sp_who2** to identify connections to the mgc database.</span></span>
    
   - <span data-ttu-id="40c0f-134">**kill \<spid\>** 以結束這些連線。</span><span class="sxs-lookup"><span data-stu-id="40c0f-134">**kill \<spid\>** to end these connections.</span></span>
    
   - <span data-ttu-id="40c0f-135">使資料庫上線：</span><span class="sxs-lookup"><span data-stu-id="40c0f-135">Bring the database online:</span></span>
    
   - <span data-ttu-id="40c0f-136">**restore database mgc with recovery**。</span><span class="sxs-lookup"><span data-stu-id="40c0f-136">**restore database mgc with recovery**.</span></span>
    
5. <span data-ttu-id="40c0f-137">在商務用 Skype Server 管理命令介面中，使用命令 **Set-CsPersistentChatState 身分識別 "服務： atl-cs-001.litwareinc.com"-PoolState FailedOver** ，以容錯移轉至 mgc 備份資料庫。</span><span class="sxs-lookup"><span data-stu-id="40c0f-137">In Skype for Business Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="40c0f-138">請務必將 Persistent Chat 集區的完整功能變數名稱取代為 atl-cs-001.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="40c0f-138">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="40c0f-139">現在 mgc 備份資料庫已是主要資料庫。</span><span class="sxs-lookup"><span data-stu-id="40c0f-139">The mgc backup database now serves as the primary database.</span></span>
    
6. <span data-ttu-id="40c0f-140">在商務用 Skype Server 管理命令介面中，使用 **Install-CsMirrorDatabase** Cmdlet 來建立現在用作主資料庫之備份資料庫的高可用性鏡像。</span><span class="sxs-lookup"><span data-stu-id="40c0f-140">In Skype for Business Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="40c0f-141">使用備份資料庫執行個體作為主要資料庫，而使用備份鏡像資料庫執行個體作為鏡像執行個體。</span><span class="sxs-lookup"><span data-stu-id="40c0f-141">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="40c0f-142">此鏡像並不是安裝程式期間，最初為主要資料庫設定的鏡像。</span><span class="sxs-lookup"><span data-stu-id="40c0f-142">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span>
    
7. <span data-ttu-id="40c0f-143">設定 Persistent Chat Server active server。</span><span class="sxs-lookup"><span data-stu-id="40c0f-143">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="40c0f-144">從商務用 Skype Server 管理命令介面，使用 **Set-CsPersistentChatActiveServer** Cmdlet 來設定作用中的伺服器清單。</span><span class="sxs-lookup"><span data-stu-id="40c0f-144">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="40c0f-145">所有作用中的伺服器必須位於與新主要資料庫相同的資料中心，或位於具有低延遲/高頻寬資料庫連線的資料中心內。</span><span class="sxs-lookup"><span data-stu-id="40c0f-145">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
    <span data-ttu-id="40c0f-146">此時，從 Persistent Chat Server 主資料庫到 Persistent Chat Server backup 資料庫的容錯移轉已成功完成。</span><span class="sxs-lookup"><span data-stu-id="40c0f-146">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>
    
## <a name="fail-back-persistent-chat-server"></a><span data-ttu-id="40c0f-147">容錯回復 Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="40c0f-147">Fail back Persistent Chat Server</span></span>

<span data-ttu-id="40c0f-148">此程式概述從持久聊天伺服器失敗復原所需的步驟，以及從主要資料中心重新建立作業。</span><span class="sxs-lookup"><span data-stu-id="40c0f-148">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>
  
<span data-ttu-id="40c0f-149">在 Persistent Chat Server 失敗的情況下，主要資料中心會受到完全中斷，主要和鏡像資料庫將無法使用。</span><span class="sxs-lookup"><span data-stu-id="40c0f-149">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="40c0f-150">主要資料中心會容錯移轉至備份伺服器。</span><span class="sxs-lookup"><span data-stu-id="40c0f-150">The primary data center fails over to the backup server.</span></span>
  
<span data-ttu-id="40c0f-151">在備份主要資料中心，及重建伺服器後，下列程序會還原正常作業。</span><span class="sxs-lookup"><span data-stu-id="40c0f-151">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="40c0f-152">此程式假設主要資料中心已經從總中斷中復原，而且已使用拓撲產生器重新建立並重新安裝 mgc 資料庫和 mgccomp 資料庫。</span><span class="sxs-lookup"><span data-stu-id="40c0f-152">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>
  
<span data-ttu-id="40c0f-153">此程式也會假設在容錯移轉期間未部署任何新的鏡像和備份伺服器，而且部署的唯一伺服器是備份伺服器及其鏡像伺服器，如先前容錯移轉 Persistent Chat Server 所定義。</span><span class="sxs-lookup"><span data-stu-id="40c0f-153">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in Fail over Persistent Chat Server previously.</span></span>
  
<span data-ttu-id="40c0f-154">災難導致主要伺服去失敗，作業轉移至備份伺服器，因為災難發生前設定就存在，設計這些步驟就是用來還原設定。</span><span class="sxs-lookup"><span data-stu-id="40c0f-154">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>
  
1. <span data-ttu-id="40c0f-155">使用商務用 Skype Server 管理命令介面中的 **Set-CsPersistentChatActiveServer** Cmdlet，從 Persistent Chat server 作用中伺服器清單清除所有伺服器。</span><span class="sxs-lookup"><span data-stu-id="40c0f-155">Clear all servers from the Persistent Chat Server Active Server list by using the **Set-CsPersistentChatActiveServer** cmdlet from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="40c0f-156">這會在回切期間停止所有持久聊天伺服器連線至 mgc 資料庫和 mgccomp 資料庫。</span><span class="sxs-lookup"><span data-stu-id="40c0f-156">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="40c0f-157">次要 Persistent Chat Server 後端伺服器上的 SQL Server 代理程式應以特權帳戶執行。</span><span class="sxs-lookup"><span data-stu-id="40c0f-157">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="40c0f-158">具體來說，帳戶必須包括：</span><span class="sxs-lookup"><span data-stu-id="40c0f-158">Specifically, the account must include:</span></span> 
  
   - <span data-ttu-id="40c0f-159">對備份所在位置之網路共用的讀取存取權。</span><span class="sxs-lookup"><span data-stu-id="40c0f-159">Read access to the network share that backups are being placed in.</span></span>
    
   - <span data-ttu-id="40c0f-160">對備份複製目的位置之特定本機目錄的寫入存取權。</span><span class="sxs-lookup"><span data-stu-id="40c0f-160">Write access to the specific local directory that the backups are being copied to.</span></span>
    
2. <span data-ttu-id="40c0f-161">停用備份 MGC 資料庫上的鏡像：</span><span class="sxs-lookup"><span data-stu-id="40c0f-161">Disable mirroring on the backup mgc database:</span></span>
    
   - <span data-ttu-id="40c0f-162">使用 SQL Server Management Studio 連線至備份 mgc 實例。</span><span class="sxs-lookup"><span data-stu-id="40c0f-162">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="40c0f-163">用滑鼠右鍵按一下 MGC 資料庫，指向 **[工作]**，然後按一下 **[鏡像]**。</span><span class="sxs-lookup"><span data-stu-id="40c0f-163">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
   - <span data-ttu-id="40c0f-164">按一下 **[移除鏡像]**。</span><span class="sxs-lookup"><span data-stu-id="40c0f-164">Click **Remove Mirroring**.</span></span>
    
   - <span data-ttu-id="40c0f-165">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="40c0f-165">Click **OK**.</span></span>
    
   - <span data-ttu-id="40c0f-166">使用 Mgccomp 資料庫執行相同步驟。</span><span class="sxs-lookup"><span data-stu-id="40c0f-166">Perform the same steps with the mgccomp database.</span></span>
    
3. <span data-ttu-id="40c0f-167">備份 MGC 資料庫以便將其還原至新的主要資料庫：</span><span class="sxs-lookup"><span data-stu-id="40c0f-167">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
   - <span data-ttu-id="40c0f-168">使用 SQL Server Management Studio 連線至備份 mgc 實例。</span><span class="sxs-lookup"><span data-stu-id="40c0f-168">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="40c0f-p113">用滑鼠右鍵按一下 MGC 資料庫，指向 **[工作]**，然後按一下 **[備份]**。**[備份資料庫]** 對話方塊隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="40c0f-p113">Right-click the mgc database, point to **Tasks**, and then click **Back Up**. The **Back Up Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="40c0f-171">在 **[備份類型]** 中選取 **[完整]**。</span><span class="sxs-lookup"><span data-stu-id="40c0f-171">In **Backup type**, select **Full**.</span></span>
    
   - <span data-ttu-id="40c0f-172">針對 **[備份元件]** 按一下 **[資料庫]**。</span><span class="sxs-lookup"><span data-stu-id="40c0f-172">For **Backup component**, click **Database**.</span></span>
    
   - <span data-ttu-id="40c0f-173">接受 **[名稱]** 中建議的預設備份組名稱，或為備份組輸入不同名稱。</span><span class="sxs-lookup"><span data-stu-id="40c0f-173">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
   -  <span data-ttu-id="40c0f-174">*\<Optional\>*  在 [ **描述**] 中，輸入備份組的描述。</span><span class="sxs-lookup"><span data-stu-id="40c0f-174">*\<Optional\>*  In **Description**, enter a description of the backup set.</span></span>
    
   - <span data-ttu-id="40c0f-175">從目的地清單移除預設備份位置。</span><span class="sxs-lookup"><span data-stu-id="40c0f-175">Remove the default backup location from the destination list.</span></span>
    
   - <span data-ttu-id="40c0f-p114">使用您為記錄傳送建立的共用位置路徑來將檔案新增至清單。主要資料庫和備份資料庫均可使用此路徑。</span><span class="sxs-lookup"><span data-stu-id="40c0f-p114">Add a file to the list by using the path to the share location that you established for log shipping. This path is available to the primary database and to the backup database.</span></span>
    
   - <span data-ttu-id="40c0f-178">按一下 **[確定]** 以關閉對話方塊並開始備份程序。</span><span class="sxs-lookup"><span data-stu-id="40c0f-178">Click **OK** to close the dialog box and begin the backup process.</span></span>
    
4. <span data-ttu-id="40c0f-179">使用先前步驟中建立的備份資料庫來還原主要資料庫。</span><span class="sxs-lookup"><span data-stu-id="40c0f-179">Restore the primary database by using the backup database created in the previous step.</span></span>
    
   - <span data-ttu-id="40c0f-180">使用 SQL Server Management Studio 連線至主要 mgc 實例。</span><span class="sxs-lookup"><span data-stu-id="40c0f-180">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
   - <span data-ttu-id="40c0f-p115">以滑鼠右鍵按一下 MGC 資料庫，依序指向 **[工作]** 和 **[還原]**，然後按一下 **[資料庫]**。**[還原資料庫]** 對話方塊隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="40c0f-p115">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**. The **Restore Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="40c0f-183">選取 **[來源裝置]**。</span><span class="sxs-lookup"><span data-stu-id="40c0f-183">Select **From Device**.</span></span>
    
   - <span data-ttu-id="40c0f-p116">按一下開啟 **[指定備份]** 對話方塊的 [瀏覽] 按鈕。在 **[備份媒體]** 中，選取 **[檔案]**。按一下 **[新增]**，選取您在步驟 3 中建立的備份檔案，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="40c0f-p116">Click the browse button, which opens the **Specify Backup** dialog box. In **Backup media**, select **File**. Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
   - <span data-ttu-id="40c0f-187">在 **[選取要還原的備份組]** 中選取備份。</span><span class="sxs-lookup"><span data-stu-id="40c0f-187">In **Select the backup sets to restore**, select the backup.</span></span>
    
   - <span data-ttu-id="40c0f-188">在 **[選取頁面]** 窗格中按一下 **[選項]**。</span><span class="sxs-lookup"><span data-stu-id="40c0f-188">Click **Options** in the **Select a page** pane.</span></span>
    
   - <span data-ttu-id="40c0f-189">在 **[還原選項]** 中選取 **[覆寫現有資料庫]**。</span><span class="sxs-lookup"><span data-stu-id="40c0f-189">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
   - <span data-ttu-id="40c0f-190">在 **[復原狀態]** 中選取 **[讓資料庫保持備妥可用]**。</span><span class="sxs-lookup"><span data-stu-id="40c0f-190">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
   - <span data-ttu-id="40c0f-191">按一下 **[確定]** 開始復原程序。</span><span class="sxs-lookup"><span data-stu-id="40c0f-191">Click **OK** to begin the restoration process.</span></span>
    
5. <span data-ttu-id="40c0f-192">為主資料庫設定 SQL Server 記錄傳送。</span><span class="sxs-lookup"><span data-stu-id="40c0f-192">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="40c0f-193">請遵循在 [商務用 Skype server 2015 中設定 Persistent Chat server 的高可用性和嚴重損壞修復中](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) 的程式，以建立主要 mgc 資料庫的記錄傳送。</span><span class="sxs-lookup"><span data-stu-id="40c0f-193">Follow the procedures in [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) to establish log shipping for the primary mgc database.</span></span>
    
6. <span data-ttu-id="40c0f-194">設定 Persistent Chat Server active server。</span><span class="sxs-lookup"><span data-stu-id="40c0f-194">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="40c0f-195">從商務用 Skype Server 管理命令介面，使用 **Set-CsPersistentChatActiveServer** Cmdlet 來設定作用中的伺服器清單。</span><span class="sxs-lookup"><span data-stu-id="40c0f-195">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="40c0f-196">所有作用中的伺服器必須位於與新主要資料庫相同的資料中心，或位於具有低延遲/高頻寬資料庫連線的資料中心內。</span><span class="sxs-lookup"><span data-stu-id="40c0f-196">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
<span data-ttu-id="40c0f-197">若要將集區還原至正常狀態，請執行下列 Windows PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="40c0f-197">To restore the pool to its normal state run the following Windows PowerShell command:</span></span>
  
```PowerShell
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

<span data-ttu-id="40c0f-198">如需詳細資訊，請參閱 [Set-CsPersistentChatState](/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="40c0f-198">For more information, see the help topic for the [Set-CsPersistentChatState](/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) cmdlet.</span></span>
