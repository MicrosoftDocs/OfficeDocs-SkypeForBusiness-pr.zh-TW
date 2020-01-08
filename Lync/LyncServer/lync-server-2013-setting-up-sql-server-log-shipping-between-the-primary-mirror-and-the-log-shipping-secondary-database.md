---
title: Lync Server 2013：設定主要鏡像與記錄傳送次要資料庫之間的 SQL Server 記錄傳送
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database
ms:assetid: 4e8e9ce9-4301-47f2-a0c3-669afeb53295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204887(v=OCS.15)
ms:contentKeyID: 48184119
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3758e654826de42f6bf6bed8ead29ce03adb6ca5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982549"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-sql-server-log-shipping-between-the-primary-mirror-and-the-log-shipping-secondary-database-in-lync-server-2013"></a><span data-ttu-id="21abd-102">在 Lync Server 2013 中設定主要鏡像與記錄傳送次要資料庫之間的 SQL Server 記錄傳送</span><span class="sxs-lookup"><span data-stu-id="21abd-102">Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21abd-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="21abd-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="21abd-104">如果主要持久聊天資料庫發生故障，請執行下列步驟，繼續進行記錄傳送至其鏡像資料庫。</span><span class="sxs-lookup"><span data-stu-id="21abd-104">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>

1.  <span data-ttu-id="21abd-105">手動將主要持久聊天資料庫容錯移轉到鏡像。</span><span class="sxs-lookup"><span data-stu-id="21abd-105">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="21abd-106">這是使用 Lync Server 管理命令介面和**CsDatabaseFailover** Cmdlet 來完成。</span><span class="sxs-lookup"><span data-stu-id="21abd-106">This is done by using the Lync Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span> <span data-ttu-id="21abd-107">如需詳細資訊，請參閱在[Lync server 2013 中部署 SQL 鏡像以取得後端伺服器高可用性](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)的「使用 Lync Server 管理命令介面 Cmdlet」。</span><span class="sxs-lookup"><span data-stu-id="21abd-107">For details, see "Using Lync Server Management Shell Cmdlets" in [Deploying SQL mirroring for Back End Server high availability in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span></span>

2.  <span data-ttu-id="21abd-108">使用 SQL Server Management Studio，連線到主要持久聊天伺服器鏡像實例。</span><span class="sxs-lookup"><span data-stu-id="21abd-108">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>

3.  <span data-ttu-id="21abd-109">請確定 SQL Server 代理程式正在執行。</span><span class="sxs-lookup"><span data-stu-id="21abd-109">Be sure that the SQL Server Agent is running.</span></span>

4.  <span data-ttu-id="21abd-110">以滑鼠右鍵按一下 mgc 資料庫，然後按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="21abd-110">Right-click the mgc database, and then click **Properties**.</span></span>

5.  <span data-ttu-id="21abd-111">在 [**選取頁面**] 底下，按一下 [**事務記錄傳送**]。</span><span class="sxs-lookup"><span data-stu-id="21abd-111">Under **Select a page**, click **Transaction Log Shipping**.</span></span>

6.  <span data-ttu-id="21abd-112">選取 [將**此項啟用為記錄傳送設定的主要資料庫**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="21abd-112">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>

7.  <span data-ttu-id="21abd-113">在 [**事務記錄備份**] 底下，按一下 [**備份設定**]。</span><span class="sxs-lookup"><span data-stu-id="21abd-113">Under **Transaction log backups**, click **Backup Settings**.</span></span>

8.  <span data-ttu-id="21abd-114">在 [**備份檔案夾的網路路徑**] 方塊中，輸入您針對 [事務記錄備份] 資料夾建立之共用的網路路徑。</span><span class="sxs-lookup"><span data-stu-id="21abd-114">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>

9.  <span data-ttu-id="21abd-115">如果備份檔案夾位於主要伺服器上，請在 [**如果備份檔案夾位於主要伺服器上**] 中輸入備份檔案夾的本機路徑，請在 [資料夾] 方塊中輸入本機路徑。</span><span class="sxs-lookup"><span data-stu-id="21abd-115">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box.</span></span> <span data-ttu-id="21abd-116">（如果備份檔案夾不在主要伺服器上，您可以將此方塊保留空白。）</span><span class="sxs-lookup"><span data-stu-id="21abd-116">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="21abd-117">如果主伺服器上的 SQL Server 服務帳戶是在本機系統帳戶下執行，您必須在主要伺服器上建立您的備份檔案夾，並指定該資料夾的本機路徑。</span><span class="sxs-lookup"><span data-stu-id="21abd-117">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span>

    
    </div>

10. <span data-ttu-id="21abd-118">設定 [**刪除舊**檔的檔案]，並在參數**中不執行任何備份時發出警示**。</span><span class="sxs-lookup"><span data-stu-id="21abd-118">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>

11. <span data-ttu-id="21abd-119">查看 [**備份作業**] 底下 [**排程**] 方塊中所列的備份排程。</span><span class="sxs-lookup"><span data-stu-id="21abd-119">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="21abd-120">若要自訂您的安裝排程，請根據需要按一下 [**排程**]，然後調整 SQL Server 代理程式排程。</span><span class="sxs-lookup"><span data-stu-id="21abd-120">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="21abd-121">使用您在主要資料庫中使用的相同設定。</span><span class="sxs-lookup"><span data-stu-id="21abd-121">Use the same settings that you used for the primary database.</span></span>

    
    </div>

12. <span data-ttu-id="21abd-122">在 [**壓縮**] 底下，選取 **[使用預設伺服器設定**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="21abd-122">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>

13. <span data-ttu-id="21abd-123">在 [**次要伺服器實例與資料庫**] 底下，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="21abd-123">Under **Secondary server instances and databases**, click **Add**.</span></span>

14. <span data-ttu-id="21abd-124">按一下 **[連線]**，然後連線到您已設定為次要伺服器的 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="21abd-124">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>

15. <span data-ttu-id="21abd-125">在 [**次要資料庫**] 方塊中，從清單中選取**mgc**資料庫。</span><span class="sxs-lookup"><span data-stu-id="21abd-125">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>

16. <span data-ttu-id="21abd-126">在 [**初始化次要資料庫**] 索引標籤上，選取 [**否，次要資料庫已初始化**]。</span><span class="sxs-lookup"><span data-stu-id="21abd-126">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>

17. <span data-ttu-id="21abd-127">在 [**複製**檔案] 索引標籤上，于 [**複製的檔案目的地] 資料夾**中，輸入應將事務記錄備份複製到哪個資料夾的路徑，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="21abd-127">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**.</span></span> <span data-ttu-id="21abd-128">這個資料夾通常位於副伺服器上。</span><span class="sxs-lookup"><span data-stu-id="21abd-128">This folder is often located on the secondary server.</span></span>

18. <span data-ttu-id="21abd-129">開啟 [**腳本**設定] 下拉式清單，然後選取 [**腳本設定至新查詢] 視窗**。</span><span class="sxs-lookup"><span data-stu-id="21abd-129">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>

19. <span data-ttu-id="21abd-130">在 [新增查詢] 視窗的 [**資料庫屬性**] 中，按一下 **[確定]** 以開始設定程式。</span><span class="sxs-lookup"><span data-stu-id="21abd-130">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>

20. <span data-ttu-id="21abd-131">選取並執行查詢的前半部分（請參閱步驟18）至行：-- \* \* \* \* \* \*結束\* \* \* \* \* \*：要在主要：執行的腳本。</span><span class="sxs-lookup"><span data-stu-id="21abd-131">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="21abd-132">手動執行此腳本是必要的，因為 SQL Server Management Studio 不支援 SQL Server 記錄傳送設定中的多個主要資料庫。</span><span class="sxs-lookup"><span data-stu-id="21abd-132">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span>

    
    </div>

21. <span data-ttu-id="21abd-133">選取 [**取消**] 以關閉 [記錄檔案傳送設定] 面板，並建立能正確實現主要和鏡像資料庫（如果是容錯移轉）的記錄檔傳送的工作設定。</span><span class="sxs-lookup"><span data-stu-id="21abd-133">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>

22. <span data-ttu-id="21abd-134">手動將主要持久聊天資料庫容錯回復到主要。</span><span class="sxs-lookup"><span data-stu-id="21abd-134">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="21abd-135">這是使用 Lync Server 管理命令介面和**CsDatabaseFailover** Cmdlet 來完成。</span><span class="sxs-lookup"><span data-stu-id="21abd-135">This is done by using the Lync Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span> <span data-ttu-id="21abd-136">如需詳細資訊，請參閱在[Lync server 2013 中部署 SQL 鏡像以取得後端伺服器高可用性](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)的「使用 Lync Server 管理命令介面 Cmdlet」。</span><span class="sxs-lookup"><span data-stu-id="21abd-136">For details, see "Using Lync Server Management Shell Cmdlets" in [Deploying SQL mirroring for Back End Server high availability in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="21abd-137">請參閱</span><span class="sxs-lookup"><span data-stu-id="21abd-137">See Also</span></span>


[<span data-ttu-id="21abd-138">在 Lync Server 2013 中針對後端伺服器高可用性部署 SQL 鏡像</span><span class="sxs-lookup"><span data-stu-id="21abd-138">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
[<span data-ttu-id="21abd-139">在 Lync Server 2013 中針對後端伺服器高可用性部署 SQL 鏡像</span><span class="sxs-lookup"><span data-stu-id="21abd-139">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

