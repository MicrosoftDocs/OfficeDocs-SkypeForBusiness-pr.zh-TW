---
title: Lync Server 2013：設定 Persistent Chat Server 主資料庫的 SQL Server 記錄傳送
description: Lync Server 2013：設定 Persistent Chat Server 主資料庫的 SQL Server 記錄傳送。
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
ms.openlocfilehash: 72b7e68bd0cb7b9f544b86a15204d3e832692ec1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554259"
---
# <a name="setting-up-sql-server-log-shipping-in-lync-server-2013-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="d5851-103">在 Lync Server 2013 中為 Persistent Chat Server 主資料庫設定 SQL Server 記錄傳送</span><span class="sxs-lookup"><span data-stu-id="d5851-103">Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5851-104">_**主題上次修改日期：** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="d5851-104">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="d5851-105">使用 SQL Server Management Studio 連線至 Persistent Chat Server 次要記錄傳送資料庫實例，並確定 SQL Server 代理程式正在執行中。</span><span class="sxs-lookup"><span data-stu-id="d5851-105">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span>

<span data-ttu-id="d5851-106">使用 SQL Server Management Studio 連線至 Persistent Chat 主要資料庫實例，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="d5851-106">Using SQL Server Management Studio connected to the Persistent Chat primary database instance, perform the following steps:</span></span>

1.  <span data-ttu-id="d5851-107">確定 SQL Server 代理程式正在執行中。</span><span class="sxs-lookup"><span data-stu-id="d5851-107">Be sure that the SQL Server Agent is running.</span></span>

2.  <span data-ttu-id="d5851-108">用滑鼠右鍵按一下 mgc 資料庫，然後按一下 **[屬性]**。</span><span class="sxs-lookup"><span data-stu-id="d5851-108">Right-click the mgc database, and then click **Properties**.</span></span>

3.  <span data-ttu-id="d5851-109">在 **[選取頁面]** 下，按一下 **[交易記錄傳送]**。</span><span class="sxs-lookup"><span data-stu-id="d5851-109">Under **Select a page**, click **Transaction Log Shipping**.</span></span>

4.  <span data-ttu-id="d5851-110">選取 **[將此啟用為記錄傳送組態的主要資料庫]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d5851-110">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>

5.  <span data-ttu-id="d5851-111">在 [交易記錄備份]\*\*\*\* 底下，按一下 [備份設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d5851-111">Under **Transaction log backups**, click **Backup Settings**.</span></span>

6.  <span data-ttu-id="d5851-112">在 [備份資料夾的網路路徑]\*\*\*\* 方塊中，輸入您為交易記錄備份資料夾建立之共用的網路路徑。</span><span class="sxs-lookup"><span data-stu-id="d5851-112">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>

7.  <span data-ttu-id="d5851-113">如果備份檔案夾位於主伺服器上，請輸入備份檔案夾的本機路徑（ \*\*如果備份檔案夾位於主伺服器上），請輸入資料夾的本機路徑 (例如： c： \\ backup) \*\* ] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="d5851-113">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\\backup)** box.</span></span> <span data-ttu-id="d5851-114"> (如果備份檔案夾不在主伺服器上，您可以將此方塊保留空白。 ) </span><span class="sxs-lookup"><span data-stu-id="d5851-114">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d5851-115">若主伺服器上的 SQL Server 服務帳戶是在本機系統帳戶之下執行，則必須在主伺服器上建立備份檔案夾，並指定該資料夾的本機路徑。</span><span class="sxs-lookup"><span data-stu-id="d5851-115">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span>

    
    </div>

8.  <span data-ttu-id="d5851-116">設定 **[指定刪除檔案的時限]** 和 **[如果未在此時間內進行備份，則發出警示]** 參數。</span><span class="sxs-lookup"><span data-stu-id="d5851-116">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>

9.  <span data-ttu-id="d5851-117">查看列在 **[備份作業]** 下的 **[排程]** 方塊中的備份排程。</span><span class="sxs-lookup"><span data-stu-id="d5851-117">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="d5851-118">若要自訂安裝的排程，請按一下 [ **排程**]，然後視需要調整 SQL Server 代理程式排程。</span><span class="sxs-lookup"><span data-stu-id="d5851-118">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>

10. <span data-ttu-id="d5851-119">在 [壓縮]\*\*\*\* 底下選取 [使用預設伺服器設定]\*\*\*\*，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d5851-119">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>

11. <span data-ttu-id="d5851-120">在 [次要伺服器執行個體與資料庫]\*\*\*\* 底下，按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d5851-120">Under **Secondary server instances and databases**, click **Add**.</span></span>

12. <span data-ttu-id="d5851-121">按一下 **[連線]** ，並聯機至您已設定為次要伺服器的 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="d5851-121">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>

13. <span data-ttu-id="d5851-122">在 **[次要資料庫]** 方塊中，從清單中選取 **[mgc]** 資料庫。</span><span class="sxs-lookup"><span data-stu-id="d5851-122">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>

14. <span data-ttu-id="d5851-123">在 [ **初始化次要資料庫** ] 索引標籤上，選擇 [ \*\*是]，產生主資料庫的完整備份，並將其還原至次要資料庫 (，並在) 中建立次要資料庫 \*\*。</span><span class="sxs-lookup"><span data-stu-id="d5851-123">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>

15. <span data-ttu-id="d5851-p103">在 [複製檔案]\*\*\*\* 索引標籤上的 [複製之檔案的目的資料夾]\*\*\*\* 方塊中，輸入複製交易記錄備份的目的資料夾路徑。此資料夾通常位在次要伺服器上。</span><span class="sxs-lookup"><span data-stu-id="d5851-p103">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied. This folder is often located on the secondary server.</span></span>

16. <span data-ttu-id="d5851-126">在 [複製工作]\*\*\*\* 底下，注意列示在 [排程]\*\*\*\* 方塊中的複製排程。</span><span class="sxs-lookup"><span data-stu-id="d5851-126">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="d5851-127">若要自訂安裝的排程，請按一下 [ **排程**]，然後視需要調整 SQL Server 代理程式排程。</span><span class="sxs-lookup"><span data-stu-id="d5851-127">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="d5851-128">此排程應與備份排程大致相同。</span><span class="sxs-lookup"><span data-stu-id="d5851-128">This schedule should be approximately the same as the backup schedule.</span></span>

17. <span data-ttu-id="d5851-129">在 [還原]\*\*\*\* 索引標籤上的 [還原備份時的資料庫狀態]\*\*\*\* 底下，選擇 [不復原模式]\*\*\*\* 選項。</span><span class="sxs-lookup"><span data-stu-id="d5851-129">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>

18. <span data-ttu-id="d5851-130">在 [延遲還原備份至少:]\*\*\*\* 底下，選取 [0 分鐘]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d5851-130">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>

19. <span data-ttu-id="d5851-131">在 [如果未在此時間內進行還原，則發出警示]\*\*\*\* 底下，選擇警示臨界值。</span><span class="sxs-lookup"><span data-stu-id="d5851-131">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>

20. <span data-ttu-id="d5851-132">在 [還原工作]\*\*\*\* 底下，查看列示在 [排程]\*\*\*\* 方塊中的還原排程。</span><span class="sxs-lookup"><span data-stu-id="d5851-132">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="d5851-133">若要自訂安裝的排程，請按一下 [ **排程**]，並視需要調整 SQL Server 代理程式排程，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d5851-133">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="d5851-134">此排程應與備份排程大致相同。</span><span class="sxs-lookup"><span data-stu-id="d5851-134">This schedule should be approximately the same as the backup schedule.</span></span>

21. <span data-ttu-id="d5851-135">在 [資料庫內容]\*\*\*\* 對話方塊上按一下 [確定]\*\*\*\*，即開始設定程序。</span><span class="sxs-lookup"><span data-stu-id="d5851-135">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

