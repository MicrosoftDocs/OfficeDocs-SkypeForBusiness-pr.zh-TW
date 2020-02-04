---
title: Lync Server 2013：針對常設聊天室伺服器主要資料庫設定 SQL Server 記錄傳送
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up SQL Server Log Shipping for the Persistent Chat Server primary database
ms:assetid: 088ea1c2-d592-4a11-b3b8-f1e2f8beae93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204653(v=OCS.15)
ms:contentKeyID: 48183337
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae44d410ef165cdd4f77b877afcfb9349dd0ec00
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764569"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-sql-server-log-shipping-in-lync-server-2013-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="634d2-102">在 Lync Server 2013 中針對常設聊天室伺服器主要資料庫設定 SQL Server 記錄傳送</span><span class="sxs-lookup"><span data-stu-id="634d2-102">Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="634d2-103">_**主題上次修改日期：** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="634d2-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="634d2-104">使用 SQL Server Management Studio，連線至持續聊天伺服器次要記錄傳送資料庫實例，並確認 SQL Server 代理程式正在執行。</span><span class="sxs-lookup"><span data-stu-id="634d2-104">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span>

<span data-ttu-id="634d2-105">如果您使用的 SQL Server Management Studio 已連接至持續聊天的主要資料庫實例，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="634d2-105">Using SQL Server Management Studio connected to the Persistent Chat primary database instance, perform the following steps:</span></span>

1.  <span data-ttu-id="634d2-106">請確定 SQL Server 代理程式正在執行。</span><span class="sxs-lookup"><span data-stu-id="634d2-106">Be sure that the SQL Server Agent is running.</span></span>

2.  <span data-ttu-id="634d2-107">以滑鼠右鍵按一下 mgc 資料庫，然後按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="634d2-107">Right-click the mgc database, and then click **Properties**.</span></span>

3.  <span data-ttu-id="634d2-108">在 [**選取頁面**] 底下，按一下 [**事務記錄傳送**]。</span><span class="sxs-lookup"><span data-stu-id="634d2-108">Under **Select a page**, click **Transaction Log Shipping**.</span></span>

4.  <span data-ttu-id="634d2-109">選取 [將**此項啟用為記錄傳送設定的主要資料庫**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="634d2-109">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>

5.  <span data-ttu-id="634d2-110">在 [**事務記錄備份**] 底下，按一下 [**備份設定**]。</span><span class="sxs-lookup"><span data-stu-id="634d2-110">Under **Transaction log backups**, click **Backup Settings**.</span></span>

6.  <span data-ttu-id="634d2-111">在 [**備份檔案夾的網路路徑**] 方塊中，輸入您針對 [事務記錄備份] 資料夾建立之共用的網路路徑。</span><span class="sxs-lookup"><span data-stu-id="634d2-111">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>

7.  <span data-ttu-id="634d2-112">如果備份檔案夾位於主要伺服器上，請在 [如果備份檔案夾位於主要伺服器上] 中輸入備份檔案夾的本機路徑 **，請輸入資料夾的本機路徑（範例： [c：\\備份]）** ] 方塊。</span><span class="sxs-lookup"><span data-stu-id="634d2-112">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\\backup)** box.</span></span> <span data-ttu-id="634d2-113">（如果備份檔案夾不在主要伺服器上，您可以將此方塊保留空白。）</span><span class="sxs-lookup"><span data-stu-id="634d2-113">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="634d2-114">如果主伺服器上的 SQL Server 服務帳戶是在本機系統帳戶下執行，您必須在主要伺服器上建立您的備份檔案夾，並指定該資料夾的本機路徑。</span><span class="sxs-lookup"><span data-stu-id="634d2-114">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span>

    
    </div>

8.  <span data-ttu-id="634d2-115">設定 [**刪除舊**檔的檔案]，並在參數**中不執行任何備份時發出警示**。</span><span class="sxs-lookup"><span data-stu-id="634d2-115">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>

9.  <span data-ttu-id="634d2-116">查看 [**備份作業**] 底下 [**排程**] 方塊中所列的備份排程。</span><span class="sxs-lookup"><span data-stu-id="634d2-116">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="634d2-117">若要自訂您的安裝排程，請按一下 [**排程**]，然後根據需要調整 SQL Server 代理程式排程。</span><span class="sxs-lookup"><span data-stu-id="634d2-117">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>

10. <span data-ttu-id="634d2-118">在 [**壓縮**] 底下，選取 **[使用預設伺服器設定**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="634d2-118">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>

11. <span data-ttu-id="634d2-119">在 [**次要伺服器實例與資料庫**] 底下，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="634d2-119">Under **Secondary server instances and databases**, click **Add**.</span></span>

12. <span data-ttu-id="634d2-120">按一下 **[連線]** 並聯機到您已設定為次要伺服器的 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="634d2-120">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>

13. <span data-ttu-id="634d2-121">在 [**次要資料庫**] 方塊中，從清單中選取**mgc**資料庫。</span><span class="sxs-lookup"><span data-stu-id="634d2-121">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>

14. <span data-ttu-id="634d2-122">在 [**初始化次要資料庫**] 索引標籤上，選擇 [**是]、[產生主資料庫的完整備份]，然後將它還原到次要資料庫（如果不存在，則建立次要資料庫）**。</span><span class="sxs-lookup"><span data-stu-id="634d2-122">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>

15. <span data-ttu-id="634d2-123">在 [**複製**檔案] 索引標籤的 [複製的檔案**目的地資料夾**] 方塊中，輸入應將事務記錄備份複製到其中的資料夾路徑。</span><span class="sxs-lookup"><span data-stu-id="634d2-123">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied.</span></span> <span data-ttu-id="634d2-124">這個資料夾通常位於副伺服器上。</span><span class="sxs-lookup"><span data-stu-id="634d2-124">This folder is often located on the secondary server.</span></span>

16. <span data-ttu-id="634d2-125">請注意，[**複製作業**] 底下 [**排程**] 方塊中所列的複製排程。</span><span class="sxs-lookup"><span data-stu-id="634d2-125">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="634d2-126">若要自訂您的安裝排程，請按一下 [**排程**]，然後根據需要調整 SQL Server 代理程式排程。</span><span class="sxs-lookup"><span data-stu-id="634d2-126">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="634d2-127">此排程應該與備份排程大致相同。</span><span class="sxs-lookup"><span data-stu-id="634d2-127">This schedule should be approximately the same as the backup schedule.</span></span>

17. <span data-ttu-id="634d2-128">在 [**還原**] 索引標籤上，在 [**還原備份時資料庫狀態**] 底下，選擇 [**無復原模式]** 選項。</span><span class="sxs-lookup"><span data-stu-id="634d2-128">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>

18. <span data-ttu-id="634d2-129">在 [**延遲還原備份至少：**] 底下，選取 [ **0 分鐘**]。</span><span class="sxs-lookup"><span data-stu-id="634d2-129">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>

19. <span data-ttu-id="634d2-130">在 [警示] 底下，選擇 [**如果沒有進行任何還原**]。</span><span class="sxs-lookup"><span data-stu-id="634d2-130">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>

20. <span data-ttu-id="634d2-131">查看 [**還原作業**] 底下 [**排程**] 方塊中所列的還原排程。</span><span class="sxs-lookup"><span data-stu-id="634d2-131">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="634d2-132">若要自訂您的安裝排程，請按一下 [**排程**]，根據需要調整 SQL Server 代理排程，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="634d2-132">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="634d2-133">此排程應該與備份排程大致相同。</span><span class="sxs-lookup"><span data-stu-id="634d2-133">This schedule should be approximately the same as the backup schedule.</span></span>

21. <span data-ttu-id="634d2-134">在 [**資料庫屬性**] 對話方塊中，按一下 **[確定]** 以開始設定程式。</span><span class="sxs-lookup"><span data-stu-id="634d2-134">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

