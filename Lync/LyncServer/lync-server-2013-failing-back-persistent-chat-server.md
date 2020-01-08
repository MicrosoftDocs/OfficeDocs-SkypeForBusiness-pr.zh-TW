---
title: Lync Server 2013：容錯回復常設聊天室伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing back Persistent Chat Server
ms:assetid: 67b91de4-6ddc-43e6-9812-5e1aa84a7980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204970(v=OCS.15)
ms:contentKeyID: 48184396
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d79c25d153de81906fcaf9355a543d31cb8fe0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977878"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="53dd4-102">在 Lync Server 2013 中容錯回復常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="53dd4-102">Failing back Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53dd4-103">_**主題上次修改日期：** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="53dd4-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="53dd4-104">此程式概述從持續聊天伺服器失敗復原所需的步驟，以及從主要資料中心重新建立作業。</span><span class="sxs-lookup"><span data-stu-id="53dd4-104">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>

<span data-ttu-id="53dd4-105">在持續聊天伺服器發生故障期間，主要資料中心會受到完全停機，且主要和鏡像資料庫無法使用。</span><span class="sxs-lookup"><span data-stu-id="53dd4-105">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="53dd4-106">主要資料中心會容錯移轉至備份伺服器。</span><span class="sxs-lookup"><span data-stu-id="53dd4-106">The primary data center fails over to the backup server.</span></span>

<span data-ttu-id="53dd4-107">下列程式會在主要資料中心重新開機後還原正常作業，且已重建伺服器。</span><span class="sxs-lookup"><span data-stu-id="53dd4-107">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="53dd4-108">此程式假設主要資料中心已從總停機中復原，且 mgc 資料庫和 mgccomp 資料庫已使用拓撲產生器重建並重新安裝。</span><span class="sxs-lookup"><span data-stu-id="53dd4-108">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>

<span data-ttu-id="53dd4-109">此程式也假設在容錯移轉期間沒有部署新的鏡像與備份伺服器，且部署的伺服器是備份伺服器及其鏡像伺服器，如在[Lync server 2013 的 [永久聊天伺服器] 中](lync-server-2013-failing-over-persistent-chat-server.md)定義。</span><span class="sxs-lookup"><span data-stu-id="53dd4-109">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in [Failing over Persistent Chat Server in Lync Server 2013](lync-server-2013-failing-over-persistent-chat-server.md).</span></span>

<span data-ttu-id="53dd4-110">這些步驟的設計目的是要在災難發生之前，復原配置，從而將主要伺服器的容錯移轉到備份伺服器。</span><span class="sxs-lookup"><span data-stu-id="53dd4-110">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>

<div>

## <a name="to-fail-back-persistent-chat-server"></a><span data-ttu-id="53dd4-111">若要自動容錯回復持久聊天伺服器</span><span class="sxs-lookup"><span data-stu-id="53dd4-111">To fail back Persistent Chat Server</span></span>

1.  <span data-ttu-id="53dd4-112">使用 Lync Server 管理命令介面中的`Set-CsPersistentChatActiveServer` Cmdlet，從 [永久聊天伺服器] 活動伺服器清單中清除 [所有伺服器]。</span><span class="sxs-lookup"><span data-stu-id="53dd4-112">Clear all servers from the Persistent Chat Server Active Server list by using the `Set-CsPersistentChatActiveServer` cmdlet from the Lync Server Management Shell.</span></span> <span data-ttu-id="53dd4-113">這會在回切期間停止連線到 mgc 資料庫和 mgccomp 資料庫的所有持久聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="53dd4-113">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="53dd4-114">次要持續聊天伺服器上的 SQL Server 代理程式應該在特許帳戶下執行。</span><span class="sxs-lookup"><span data-stu-id="53dd4-114">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="53dd4-115">具體說來，帳戶必須包括：</span><span class="sxs-lookup"><span data-stu-id="53dd4-115">Specifically, the account must include:</span></span> 
    > <UL>
    > <LI>
    > <P><span data-ttu-id="53dd4-116">讀取備份所要加入的網路共用的存取權。</span><span class="sxs-lookup"><span data-stu-id="53dd4-116">Read access to the network share that backups are being placed in.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="53dd4-117">寫入要複本備份之特定本機目錄的存取權。</span><span class="sxs-lookup"><span data-stu-id="53dd4-117">Write access to the specific local directory that the backups are being copied to.</span></span></P></LI></UL>

    
    </div>

2.  <span data-ttu-id="53dd4-118">停用備份 mgc 資料庫上的鏡像：</span><span class="sxs-lookup"><span data-stu-id="53dd4-118">Disable mirroring on the backup mgc database:</span></span>
    
    1.  <span data-ttu-id="53dd4-119">使用 SQL Server Management Studio，連線至備份 mgc 實例。</span><span class="sxs-lookup"><span data-stu-id="53dd4-119">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
    2.  <span data-ttu-id="53dd4-120">以滑鼠右鍵按一下 mgc 資料庫，指向 [**任務**]，然後按一下 [**鏡像**]。</span><span class="sxs-lookup"><span data-stu-id="53dd4-120">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
    3.  <span data-ttu-id="53dd4-121">按一下 [**移除鏡像**]。</span><span class="sxs-lookup"><span data-stu-id="53dd4-121">Click **Remove Mirroring**.</span></span>
    
    4.  <span data-ttu-id="53dd4-122">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="53dd4-122">Click **OK**.</span></span>
    
    5.  <span data-ttu-id="53dd4-123">對 mgccomp 資料庫執行相同的步驟。</span><span class="sxs-lookup"><span data-stu-id="53dd4-123">Perform the same steps with the mgccomp database.</span></span>

3.  <span data-ttu-id="53dd4-124">備份 mgc 資料庫，以便將它還原到新的主資料庫：</span><span class="sxs-lookup"><span data-stu-id="53dd4-124">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
    1.  <span data-ttu-id="53dd4-125">使用 SQL Server Management Studio，連線至備份 mgc 實例。</span><span class="sxs-lookup"><span data-stu-id="53dd4-125">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
    2.  <span data-ttu-id="53dd4-126">以滑鼠右鍵按一下 mgc 資料庫，指向 [**任務**]，然後按一下 [**備份**]。</span><span class="sxs-lookup"><span data-stu-id="53dd4-126">Right-click the mgc database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="53dd4-127">[**備份資料庫**] 對話方塊隨即出現。</span><span class="sxs-lookup"><span data-stu-id="53dd4-127">The **Back Up Database** dialog box appears.</span></span>
    
    3.  <span data-ttu-id="53dd4-128">在 [**備份類型**] 中，選取 [**全**選]。</span><span class="sxs-lookup"><span data-stu-id="53dd4-128">In **Backup type**, select **Full**.</span></span>
    
    4.  <span data-ttu-id="53dd4-129">針對 [**備份元件**]，按一下 [**資料庫**]。</span><span class="sxs-lookup"><span data-stu-id="53dd4-129">For **Backup component**, click **Database**.</span></span>
    
    5.  <span data-ttu-id="53dd4-130">要麼接受**名稱**中建議的預設備份組名稱，要麼為備份組輸入不同的名稱。</span><span class="sxs-lookup"><span data-stu-id="53dd4-130">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
    6.  <span data-ttu-id="53dd4-131">\* \<選用\> \*在 [**描述**] 中，輸入備份組的描述。</span><span class="sxs-lookup"><span data-stu-id="53dd4-131">*\<Optional\>* In **Description**, enter a description of the backup set.</span></span>
    
    7.  <span data-ttu-id="53dd4-132">從目的地清單移除預設備份位置。</span><span class="sxs-lookup"><span data-stu-id="53dd4-132">Remove the default backup location from the destination list.</span></span>
    
    8.  <span data-ttu-id="53dd4-133">使用您為記錄傳送建立的共用位置路徑，將檔案新增至清單。</span><span class="sxs-lookup"><span data-stu-id="53dd4-133">Add a file to the list by using the path to the share location that you established for log shipping.</span></span> <span data-ttu-id="53dd4-134">這個路徑可供主要資料庫和備份資料庫使用。</span><span class="sxs-lookup"><span data-stu-id="53dd4-134">This path is available to the primary database and to the backup database.</span></span>
    
    9.  <span data-ttu-id="53dd4-135">按一下 **[確定**] 以關閉對話方塊並開始備份程式。</span><span class="sxs-lookup"><span data-stu-id="53dd4-135">Click **OK** to close the dialog box and begin the backup process.</span></span>

4.  <span data-ttu-id="53dd4-136">使用在上一個步驟中建立的備份資料庫來還原主要資料庫。</span><span class="sxs-lookup"><span data-stu-id="53dd4-136">Restore the primary database by using the backup database created in the previous step.</span></span>
    
    1.  <span data-ttu-id="53dd4-137">使用 SQL Server Management Studio，連線到主要的 mgc 實例。</span><span class="sxs-lookup"><span data-stu-id="53dd4-137">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
    2.  <span data-ttu-id="53dd4-138">以滑鼠右鍵按一下 mgc 資料庫，指向 [**任務**]，指向 [**還原**]，然後按一下 [**資料庫**]。</span><span class="sxs-lookup"><span data-stu-id="53dd4-138">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**.</span></span> <span data-ttu-id="53dd4-139">[**還原資料庫**] 對話方塊隨即出現。</span><span class="sxs-lookup"><span data-stu-id="53dd4-139">The **Restore Database** dialog box appears.</span></span>
    
    3.  <span data-ttu-id="53dd4-140">選取 [**從裝置**]。</span><span class="sxs-lookup"><span data-stu-id="53dd4-140">Select **From Device**.</span></span>
    
    4.  <span data-ttu-id="53dd4-141">按一下 [流覽] 按鈕，即可開啟 [**指定備份**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="53dd4-141">Click the browse button, which opens the **Specify Backup** dialog box.</span></span> <span data-ttu-id="53dd4-142">在 [**備份媒體**] 中 **，選取 [** 檔案]。</span><span class="sxs-lookup"><span data-stu-id="53dd4-142">In **Backup media**, select **File**.</span></span> <span data-ttu-id="53dd4-143">按一下 [**新增**]，選取您在步驟3中建立的備份檔案，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="53dd4-143">Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
    5.  <span data-ttu-id="53dd4-144">在 [**選取要還原的備份組**] 中，選取 [備份]。</span><span class="sxs-lookup"><span data-stu-id="53dd4-144">In **Select the backup sets to restore**, select the backup.</span></span>
    
    6.  <span data-ttu-id="53dd4-145">按一下 [**選取頁面**] 窗格中的 [**選項**]。</span><span class="sxs-lookup"><span data-stu-id="53dd4-145">Click **Options** in the **Select a page** pane.</span></span>
    
    7.  <span data-ttu-id="53dd4-146">在 [**還原選項**] 中，選取 **[覆寫現有的資料庫**]。</span><span class="sxs-lookup"><span data-stu-id="53dd4-146">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
    8.  <span data-ttu-id="53dd4-147">在 [**恢復狀態**] 中，選取 **[讓資料庫可供使用**]。</span><span class="sxs-lookup"><span data-stu-id="53dd4-147">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
    9.  <span data-ttu-id="53dd4-148">按一下 **[確定]** 以開始還原程式。</span><span class="sxs-lookup"><span data-stu-id="53dd4-148">Click **OK** to begin the restoration process.</span></span>

5.  <span data-ttu-id="53dd4-149">為主要資料庫設定 SQL Server 記錄傳送。</span><span class="sxs-lookup"><span data-stu-id="53dd4-149">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="53dd4-150">請依照在[Lync server 2013 中設定持久聊天伺服器以取得高可用性和災難復原等](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)程式，為主要的 mgc 資料庫建立記錄傳送。</span><span class="sxs-lookup"><span data-stu-id="53dd4-150">Follow the procedures in [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) to establish log shipping for the primary mgc database.</span></span>

6.  <span data-ttu-id="53dd4-151">設定持續聊天伺服器的使用中伺服器。</span><span class="sxs-lookup"><span data-stu-id="53dd4-151">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="53dd4-152">從 Lync Server 管理命令介面，使用**CsPersistentChatActiveServer** Cmdlet 來設定作用中伺服器的清單。</span><span class="sxs-lookup"><span data-stu-id="53dd4-152">From the Lync Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="53dd4-153">所有的作用中伺服器都必須位於與新的主資料庫相同的資料中心內，或是在具有低延遲/高頻寬連接的資料中心中。</span><span class="sxs-lookup"><span data-stu-id="53dd4-153">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span>

    
    </div>

<span data-ttu-id="53dd4-154">將池還原至其正常狀態時，請執行下列 Windows PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="53dd4-154">The restore the pool to its normal state run the following Windows PowerShell command:</span></span>

    Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal

<span data-ttu-id="53dd4-155">如需詳細資訊，請參閱[CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="53dd4-155">See the help topic for the [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) cmdlet for more information.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

