---
title: Lync Server 2013： 設定 SQL Server 記錄傳送的常設聊天室伺服器主要資料庫
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
ms.openlocfilehash: d91697baca93da3e4e9ea8c446ce42e02309e6f1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-sql-server-log-shipping-in-lync-server-2013-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="90cad-102">設定 SQL Server 記錄傳送 Lync Server 2013 中針對常設聊天室伺服器主要資料庫</span><span class="sxs-lookup"><span data-stu-id="90cad-102">Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90cad-103">_**主題上次修改日期：** 2012年-11-12_</span><span class="sxs-lookup"><span data-stu-id="90cad-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="90cad-104">使用 SQL Server Management Studio，連線至 Persistent Chat Server 次要記錄傳送資料庫執行個體，並確定 SQL Server 代理程式正在執行。</span><span class="sxs-lookup"><span data-stu-id="90cad-104">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span>

<span data-ttu-id="90cad-105">使用 SQL Server Management Studio 連線至常設聊天室主要資料庫執行個體，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="90cad-105">Using SQL Server Management Studio connected to the Persistent Chat primary database instance, perform the following steps:</span></span>

1.  <span data-ttu-id="90cad-106">請務必為執行 SQL Server 代理程式。</span><span class="sxs-lookup"><span data-stu-id="90cad-106">Be sure that the SQL Server Agent is running.</span></span>

2.  <span data-ttu-id="90cad-107">用滑鼠右鍵按一下 mgc 資料庫，然後按一下 **[屬性]**。</span><span class="sxs-lookup"><span data-stu-id="90cad-107">Right-click the mgc database, and then click **Properties**.</span></span>

3.  <span data-ttu-id="90cad-108">在 **[選取頁面]** 下，按一下 **[交易記錄傳送]**。</span><span class="sxs-lookup"><span data-stu-id="90cad-108">Under **Select a page**, click **Transaction Log Shipping**.</span></span>

4.  <span data-ttu-id="90cad-109">選取 **[將此啟用為記錄傳送組態的主要資料庫]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="90cad-109">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>

5.  <span data-ttu-id="90cad-110">在 [交易記錄備份]\*\*\*\* 底下，按一下 [備份設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="90cad-110">Under **Transaction log backups**, click **Backup Settings**.</span></span>

6.  <span data-ttu-id="90cad-111">在 [備份資料夾的網路路徑]\*\*\*\* 方塊中，輸入您為交易記錄備份資料夾建立之共用的網路路徑。</span><span class="sxs-lookup"><span data-stu-id="90cad-111">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>

7.  <span data-ttu-id="90cad-112">如果備份資料夾位於主要伺服器上，輸入備份資料夾中的本機路徑**如果備份資料夾位於主要伺服器上，輸入該資料夾的本機路徑 (範例： c:\\備份)** ] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="90cad-112">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\\backup)** box.</span></span> <span data-ttu-id="90cad-113">（如果備份資料夾不是在主要伺服器上，您可以將保留此方塊空白。）</span><span class="sxs-lookup"><span data-stu-id="90cad-113">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="90cad-114">如果您主要的伺服器上的 SQL Server 服務帳戶是本機系統帳戶之下執行，您必須在主要伺服器上建立備份資料夾，並指定該資料夾的本機路徑。</span><span class="sxs-lookup"><span data-stu-id="90cad-114">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span>

    
    </div>

8.  <span data-ttu-id="90cad-115">設定 **[指定刪除檔案的時限]** 和 **[如果未在此時間內進行備份，則發出警示]** 參數。</span><span class="sxs-lookup"><span data-stu-id="90cad-115">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>

9.  <span data-ttu-id="90cad-116">查看列在 **[備份作業]** 下的 **[排程]** 方塊中的備份排程。</span><span class="sxs-lookup"><span data-stu-id="90cad-116">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="90cad-117">若要自訂安裝的排程，按一下 [**排程**]，並調整所需的 SQL Server 代理程式排程。</span><span class="sxs-lookup"><span data-stu-id="90cad-117">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>

10. <span data-ttu-id="90cad-118">在 [壓縮]\*\*\*\* 底下選取 [使用預設伺服器設定]\*\*\*\*，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="90cad-118">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>

11. <span data-ttu-id="90cad-119">在 [次要伺服器執行個體與資料庫]\*\*\*\* 底下，按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="90cad-119">Under **Secondary server instances and databases**, click **Add**.</span></span>

12. <span data-ttu-id="90cad-120">按一下 [**連線**]，並連線至您已設定為次要伺服器的 SQL Server 執行個體。</span><span class="sxs-lookup"><span data-stu-id="90cad-120">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>

13. <span data-ttu-id="90cad-121">在 **[次要資料庫]** 方塊中，從清單中選取 **[mgc]** 資料庫。</span><span class="sxs-lookup"><span data-stu-id="90cad-121">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>

14. <span data-ttu-id="90cad-122">在 [**初始化次要資料庫**] 索引標籤上選擇選項**是，產生主要資料庫的完整備份還原至次要資料庫 （並建立次要資料庫若存在）**。</span><span class="sxs-lookup"><span data-stu-id="90cad-122">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>

15. <span data-ttu-id="90cad-p103">在 [複製檔案]\*\*\*\* 索引標籤上的 [複製之檔案的目的資料夾]\*\*\*\* 方塊中，輸入複製交易記錄備份的目的資料夾路徑。此資料夾通常位在次要伺服器上。</span><span class="sxs-lookup"><span data-stu-id="90cad-p103">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied. This folder is often located on the secondary server.</span></span>

16. <span data-ttu-id="90cad-125">在 [複製工作]\*\*\*\* 底下，注意列示在 [排程]\*\*\*\* 方塊中的複製排程。</span><span class="sxs-lookup"><span data-stu-id="90cad-125">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="90cad-126">若要自訂安裝的排程，按一下 [**排程**]，並調整所需的 SQL Server 代理程式排程。</span><span class="sxs-lookup"><span data-stu-id="90cad-126">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="90cad-127">此排程應與備份排程大致相同。</span><span class="sxs-lookup"><span data-stu-id="90cad-127">This schedule should be approximately the same as the backup schedule.</span></span>

17. <span data-ttu-id="90cad-128">在 [還原]\*\*\*\* 索引標籤上的 [還原備份時的資料庫狀態]\*\*\*\* 底下，選擇 [不復原模式]\*\*\*\* 選項。</span><span class="sxs-lookup"><span data-stu-id="90cad-128">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>

18. <span data-ttu-id="90cad-129">在 [延遲還原備份至少:]\*\*\*\* 底下，選取 [0 分鐘]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="90cad-129">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>

19. <span data-ttu-id="90cad-130">在 [如果未在此時間內進行還原，則發出警示]\*\*\*\* 底下，選擇警示臨界值。</span><span class="sxs-lookup"><span data-stu-id="90cad-130">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>

20. <span data-ttu-id="90cad-131">在 [還原工作]\*\*\*\* 底下，查看列示在 [排程]\*\*\*\* 方塊中的還原排程。</span><span class="sxs-lookup"><span data-stu-id="90cad-131">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="90cad-132">若要自訂安裝的排程，請按一下 [**排程**]、 調整 SQL Server 代理程式排程，視需要，並按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="90cad-132">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="90cad-133">此排程應與備份排程大致相同。</span><span class="sxs-lookup"><span data-stu-id="90cad-133">This schedule should be approximately the same as the backup schedule.</span></span>

21. <span data-ttu-id="90cad-134">在 [資料庫內容]\*\*\*\* 對話方塊上按一下 [確定]\*\*\*\*，即開始設定程序。</span><span class="sxs-lookup"><span data-stu-id="90cad-134">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

