---
title: Lync Server 2013：容錯回復 Persistent Chat Server
description: Lync Server 2013：容錯回復 Persistent Chat Server。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back Persistent Chat Server
ms:assetid: 67b91de4-6ddc-43e6-9812-5e1aa84a7980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204970(v=OCS.15)
ms:contentKeyID: 48184396
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fa36562b3892c0e22960677ffcba4b862e708c4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567729"
---
# <a name="failing-back-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="84f97-103">在 Lync Server 2013 中容錯回復 Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="84f97-103">Failing back Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84f97-104">_**主題上次修改日期：** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="84f97-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="84f97-105">此程式概述從持久聊天伺服器失敗復原所需的步驟，以及從主要資料中心重新建立作業。</span><span class="sxs-lookup"><span data-stu-id="84f97-105">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>

<span data-ttu-id="84f97-106">在 Persistent Chat Server 失敗的情況下，主要資料中心會受到完全中斷，主要和鏡像資料庫將無法使用。</span><span class="sxs-lookup"><span data-stu-id="84f97-106">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="84f97-107">主要資料中心會容錯移轉至備份伺服器。</span><span class="sxs-lookup"><span data-stu-id="84f97-107">The primary data center fails over to the backup server.</span></span>

<span data-ttu-id="84f97-108">在備份主要資料中心，及重建伺服器後，下列程序會還原正常作業。</span><span class="sxs-lookup"><span data-stu-id="84f97-108">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="84f97-109">此程式假設主要資料中心已經從總中斷中復原，而且已使用拓撲產生器重新建立並重新安裝 mgc 資料庫和 mgccomp 資料庫。</span><span class="sxs-lookup"><span data-stu-id="84f97-109">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>

<span data-ttu-id="84f97-110">此程式也會假設在容錯移轉期間未部署任何新的鏡像和備份伺服器，而且部署的唯一伺服器就是備份伺服器及其鏡像伺服器，如在 [Lync server 2013 中的 [以容錯移轉持久聊天伺服器進行容錯移轉](lync-server-2013-failing-over-persistent-chat-server.md)] 中所定義。</span><span class="sxs-lookup"><span data-stu-id="84f97-110">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in [Failing over Persistent Chat Server in Lync Server 2013](lync-server-2013-failing-over-persistent-chat-server.md).</span></span>

<span data-ttu-id="84f97-111">災難導致主要伺服去失敗，作業轉移至備份伺服器，因為災難發生前設定就存在，設計這些步驟就是用來還原設定。</span><span class="sxs-lookup"><span data-stu-id="84f97-111">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>

<div>

## <a name="to-fail-back-persistent-chat-server"></a><span data-ttu-id="84f97-112">若要容錯回復 Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="84f97-112">To fail back Persistent Chat Server</span></span>

1.  <span data-ttu-id="84f97-113">使用 Lync Server 管理命令介面中的 Cmdlet，清除 Persistent Chat Server 作用中伺服器清單中的所有伺服器 `Set-CsPersistentChatActiveServer` 。</span><span class="sxs-lookup"><span data-stu-id="84f97-113">Clear all servers from the Persistent Chat Server Active Server list by using the `Set-CsPersistentChatActiveServer` cmdlet from the Lync Server Management Shell.</span></span> <span data-ttu-id="84f97-114">這會在回切期間停止所有持久聊天伺服器連線至 mgc 資料庫和 mgccomp 資料庫。</span><span class="sxs-lookup"><span data-stu-id="84f97-114">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="84f97-115">次要 Persistent Chat Server 後端伺服器上的 SQL Server 代理程式應以特權帳戶執行。</span><span class="sxs-lookup"><span data-stu-id="84f97-115">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="84f97-116">具體來說，帳戶必須包括：</span><span class="sxs-lookup"><span data-stu-id="84f97-116">Specifically, the account must include:</span></span> 
    > <UL>
    > <LI>
    > <P><span data-ttu-id="84f97-117">對備份所在位置之網路共用的讀取存取權。</span><span class="sxs-lookup"><span data-stu-id="84f97-117">Read access to the network share that backups are being placed in.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="84f97-118">對備份複製目的位置之特定本機目錄的寫入存取權。</span><span class="sxs-lookup"><span data-stu-id="84f97-118">Write access to the specific local directory that the backups are being copied to.</span></span></P></LI></UL>

    
    </div>

2.  <span data-ttu-id="84f97-119">停用備份 MGC 資料庫上的鏡像：</span><span class="sxs-lookup"><span data-stu-id="84f97-119">Disable mirroring on the backup mgc database:</span></span>
    
    1.  <span data-ttu-id="84f97-120">使用 SQL Server Management Studio 連線至備份 mgc 實例。</span><span class="sxs-lookup"><span data-stu-id="84f97-120">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
    2.  <span data-ttu-id="84f97-121">用滑鼠右鍵按一下 MGC 資料庫，指向 **[工作]**，然後按一下 **[鏡像]**。</span><span class="sxs-lookup"><span data-stu-id="84f97-121">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
    3.  <span data-ttu-id="84f97-122">按一下 **[移除鏡像]**。</span><span class="sxs-lookup"><span data-stu-id="84f97-122">Click **Remove Mirroring**.</span></span>
    
    4.  <span data-ttu-id="84f97-123">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="84f97-123">Click **OK**.</span></span>
    
    5.  <span data-ttu-id="84f97-124">使用 Mgccomp 資料庫執行相同步驟。</span><span class="sxs-lookup"><span data-stu-id="84f97-124">Perform the same steps with the mgccomp database.</span></span>

3.  <span data-ttu-id="84f97-125">備份 MGC 資料庫以便將其還原至新的主要資料庫：</span><span class="sxs-lookup"><span data-stu-id="84f97-125">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
    1.  <span data-ttu-id="84f97-126">使用 SQL Server Management Studio 連線至備份 mgc 實例。</span><span class="sxs-lookup"><span data-stu-id="84f97-126">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
    2.  <span data-ttu-id="84f97-p105">用滑鼠右鍵按一下 MGC 資料庫，指向 **[工作]**，然後按一下 **[備份]**。**[備份資料庫]** 對話方塊隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="84f97-p105">Right-click the mgc database, point to **Tasks**, and then click **Back Up**. The **Back Up Database** dialog box appears.</span></span>
    
    3.  <span data-ttu-id="84f97-129">在 **[備份類型]** 中選取 **[完整]**。</span><span class="sxs-lookup"><span data-stu-id="84f97-129">In **Backup type**, select **Full**.</span></span>
    
    4.  <span data-ttu-id="84f97-130">針對 **[備份元件]** 按一下 **[資料庫]**。</span><span class="sxs-lookup"><span data-stu-id="84f97-130">For **Backup component**, click **Database**.</span></span>
    
    5.  <span data-ttu-id="84f97-131">接受 **[名稱]** 中建議的預設備份組名稱，或為備份組輸入不同名稱。</span><span class="sxs-lookup"><span data-stu-id="84f97-131">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
    6.  <span data-ttu-id="84f97-132">*\<Optional\>* 在 [ **描述**] 中，輸入備份組的描述。</span><span class="sxs-lookup"><span data-stu-id="84f97-132">*\<Optional\>* In **Description**, enter a description of the backup set.</span></span>
    
    7.  <span data-ttu-id="84f97-133">從目的地清單移除預設備份位置。</span><span class="sxs-lookup"><span data-stu-id="84f97-133">Remove the default backup location from the destination list.</span></span>
    
    8.  <span data-ttu-id="84f97-p106">使用您為記錄傳送建立的共用位置路徑來將檔案新增至清單。主要資料庫和備份資料庫均可使用此路徑。</span><span class="sxs-lookup"><span data-stu-id="84f97-p106">Add a file to the list by using the path to the share location that you established for log shipping. This path is available to the primary database and to the backup database.</span></span>
    
    9.  <span data-ttu-id="84f97-136">按一下 **[確定]** 以關閉對話方塊並開始備份程序。</span><span class="sxs-lookup"><span data-stu-id="84f97-136">Click **OK** to close the dialog box and begin the backup process.</span></span>

4.  <span data-ttu-id="84f97-137">使用先前步驟中建立的備份資料庫來還原主要資料庫。</span><span class="sxs-lookup"><span data-stu-id="84f97-137">Restore the primary database by using the backup database created in the previous step.</span></span>
    
    1.  <span data-ttu-id="84f97-138">使用 SQL Server Management Studio 連線至主要 mgc 實例。</span><span class="sxs-lookup"><span data-stu-id="84f97-138">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
    2.  <span data-ttu-id="84f97-p107">以滑鼠右鍵按一下 MGC 資料庫，依序指向 **[工作]** 和 **[還原]**，然後按一下 **[資料庫]**。**[還原資料庫]** 對話方塊隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="84f97-p107">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**. The **Restore Database** dialog box appears.</span></span>
    
    3.  <span data-ttu-id="84f97-141">選取 **[來源裝置]**。</span><span class="sxs-lookup"><span data-stu-id="84f97-141">Select **From Device**.</span></span>
    
    4.  <span data-ttu-id="84f97-p108">按一下開啟 **[指定備份]** 對話方塊的 [瀏覽] 按鈕。在 **[備份媒體]** 中，選取 **[檔案]**。按一下 **[新增]**，選取您在步驟 3 中建立的備份檔案，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="84f97-p108">Click the browse button, which opens the **Specify Backup** dialog box. In **Backup media**, select **File**. Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
    5.  <span data-ttu-id="84f97-145">在 **[選取要還原的備份組]** 中選取備份。</span><span class="sxs-lookup"><span data-stu-id="84f97-145">In **Select the backup sets to restore**, select the backup.</span></span>
    
    6.  <span data-ttu-id="84f97-146">在 **[選取頁面]** 窗格中按一下 **[選項]**。</span><span class="sxs-lookup"><span data-stu-id="84f97-146">Click **Options** in the **Select a page** pane.</span></span>
    
    7.  <span data-ttu-id="84f97-147">在 **[還原選項]** 中選取 **[覆寫現有資料庫]**。</span><span class="sxs-lookup"><span data-stu-id="84f97-147">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
    8.  <span data-ttu-id="84f97-148">在 **[復原狀態]** 中選取 **[讓資料庫保持備妥可用]**。</span><span class="sxs-lookup"><span data-stu-id="84f97-148">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
    9.  <span data-ttu-id="84f97-149">按一下 **[確定]** 開始復原程序。</span><span class="sxs-lookup"><span data-stu-id="84f97-149">Click **OK** to begin the restoration process.</span></span>

5.  <span data-ttu-id="84f97-150">為主資料庫設定 SQL Server 記錄傳送。</span><span class="sxs-lookup"><span data-stu-id="84f97-150">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="84f97-151">請遵循在 [Lync server 2013 中設定 Persistent Chat Server 以取得高可用性和嚴重損壞修復](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) 的程式，以建立主要 mgc 資料庫的記錄傳送。</span><span class="sxs-lookup"><span data-stu-id="84f97-151">Follow the procedures in [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) to establish log shipping for the primary mgc database.</span></span>

6.  <span data-ttu-id="84f97-152">設定 Persistent Chat Server active server。</span><span class="sxs-lookup"><span data-stu-id="84f97-152">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="84f97-153">從 Lync Server 管理命令介面，使用 **Set-CsPersistentChatActiveServer** Cmdlet 來設定作用中的伺服器清單。</span><span class="sxs-lookup"><span data-stu-id="84f97-153">From the Lync Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="84f97-154">所有作用中的伺服器必須位於與新主要資料庫相同的資料中心，或位於具有低延遲/高頻寬資料庫連線的資料中心內。</span><span class="sxs-lookup"><span data-stu-id="84f97-154">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span>

    
    </div>

<span data-ttu-id="84f97-155">將集區還原至正常狀態會執行下列 Windows PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="84f97-155">The restore the pool to its normal state run the following Windows PowerShell command:</span></span>

    Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal

<span data-ttu-id="84f97-156">如需詳細資訊，請參閱 [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="84f97-156">See the help topic for the [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) cmdlet for more information.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

