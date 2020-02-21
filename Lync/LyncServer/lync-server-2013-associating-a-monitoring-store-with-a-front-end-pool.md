---
title: Lync Server 2013： 建立與前端集區的關聯監控存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associating a monitoring store with a Front End pool
ms:assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205271(v=OCS.15)
ms:contentKeyID: 48185439
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfdff8863c0e629c99d0e64aca0b7f84dcb63a43
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205449"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associating-a-monitoring-store-with-a-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="466da-102">將監控存放區與 Lync Server 2013 中的前端集區產生關聯</span><span class="sxs-lookup"><span data-stu-id="466da-102">Associating a monitoring store with a Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="466da-103">_**上次修改主題：** 2013年-04-22_</span><span class="sxs-lookup"><span data-stu-id="466da-103">_**Topic Last Modified:** 2013-04-22_</span></span>

<span data-ttu-id="466da-104">在 [Microsoft Lync Server 2013 中已與監控存放區相關聯的前端集區只可收集監視資料，通常實行您的工作會定義在拓撲產生器的前端集區。</span><span class="sxs-lookup"><span data-stu-id="466da-104">In Microsoft Lync Server 2013 monitoring data can only be collected on Front End pools that have been associated with a monitoring store, a task typically carried out you define a Front End pool in Topology Builder.</span></span> <span data-ttu-id="466da-105">若要將監控存放區與新的前端集區產生關聯，請確定您選取 [定義新前端集區精靈] 的 [**選取功能**] 頁面上的選項**監視 （詳細通話記錄和品質經驗計量的記錄）** 。</span><span class="sxs-lookup"><span data-stu-id="466da-105">To associate a monitoring store with a new Front End pool, make sure that you select the option **Monitoring (call detail recording and logging of quality of experience metrics)** on the **Select Features** page of the Define New Front End Pool wizard.</span></span> <span data-ttu-id="466da-106">請注意，是否您選取此選項，您也必須指定 SQL 存放區才能完成這個精靈;不過，此儲存區不需要執行精靈時存在的。</span><span class="sxs-lookup"><span data-stu-id="466da-106">Note that, if you select this option, you must also specify a SQL store in order to complete the wizard; however, this store does not have to exist at the time you run the wizard.</span></span> <span data-ttu-id="466da-107">這表示，您可以先集區關聯監控存放區，然後稍後安裝和設定該儲存區。</span><span class="sxs-lookup"><span data-stu-id="466da-107">That means that you can first associate a pool with a monitoring store, then later setup and configure that store.</span></span>

<span data-ttu-id="466da-108">或者，您可以將關聯的現有前端集區新的或其他監控存放區，請完成下列程序：</span><span class="sxs-lookup"><span data-stu-id="466da-108">Alternatively, you can associate an existing Front End pool with a new or different monitoring store by completing the following procedure:</span></span>

1.  <span data-ttu-id="466da-109">按一下 [**開始]**、 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 拓撲產生器]**。</span><span class="sxs-lookup"><span data-stu-id="466da-109">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="466da-110">在 **[拓撲產生器]** 對話方塊中，選取 **[從現有的部署下載拓撲]**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="466da-110">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>

3.  <span data-ttu-id="466da-111">在 [另**存**新檔] 對話方塊中，輸入您目前的拓撲的檔案名稱，然後按一下 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="466da-111">In the **Save As** dialog box, enter a file name for your current topology and then click **Save**.</span></span> <span data-ttu-id="466da-112">儲存的拓撲可以稍後再擷取並重新發佈以防有新的拓撲的問題。</span><span class="sxs-lookup"><span data-stu-id="466da-112">The saved topology can later be retrieved and re-published in case there are problems with the new topology.</span></span>

4.  <span data-ttu-id="466da-113">在拓撲產生器中，依序展開 [ **Lync Server 2013**中，展開包含前端集區]，網站的名稱，然後按一下以展開 [ **Enterprise Edition 前端集區**。</span><span class="sxs-lookup"><span data-stu-id="466da-113">In Topology Builder, expand **Lync Server 2013**, expand the name of the site containing the Front End pool, then click expand **Enterprise Edition Front End pools**.</span></span>

5.  <span data-ttu-id="466da-114">以滑鼠右鍵按一下與監控存放區產生關聯，然後按一下 [**編輯內容**之集區的名稱。</span><span class="sxs-lookup"><span data-stu-id="466da-114">Right-click the name of the pool to be associated with the monitoring store and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="466da-115">在 [**編輯內容**] 對話方塊的 [**一般**] 索引標籤中選取 [**監控 （CDR 和 QoE 計量）** ] 選項，然後從 [**監控 SQL Server 儲存區**] 下拉式清單中選取現有的 SQL Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="466da-115">In the **Edit Properties** dialog box, on the **General** tab, select the option **Monitoring (CDR and QoE metrics)** and then select an existing SQL Server database from the **Monitoring SQL Server store** dropdown list.</span></span> <span data-ttu-id="466da-116">（或者，按一下 [**新增**]，以新的資料庫存放區建立關聯的集區）。如果您選擇使用新的資料庫儲存區，然後在 [**定義新 SQL 存放區**] 對話方塊中，輸入 [ **Sql Server FQDN** ] 方塊中的 SQL Server 電腦的完整的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="466da-116">(Or, click **New** to associate the pool with a new database store.) If you choose to use a new database store then, in the **Define New SQL Store** dialog box, enter the fully qualified domain name of the SQL Server computer in the **Sql Server FQDN** box.</span></span> <span data-ttu-id="466da-117">如果您想要針對該儲存區選取 [**預設執行個體**; 使用預設 SQL Server 執行個體否則請選擇 [**具名執行個體**，然後在**具名執行個體]** 方塊中輸入的執行個體名稱。</span><span class="sxs-lookup"><span data-stu-id="466da-117">If you want to use the default SQL Server instance for that store select **Default Instance**; otherwise select **Named Instance** and enter the instance name in the **Named Instance** box.</span></span>
    
    <span data-ttu-id="466da-118">[**編輯內容**] 對話方塊也會提供您建立 SQL 鏡像監控資料庫 （SQL 鏡像可讓您維護兩個副本的監控資料庫、 一個副本儲存在監控 SQL 鏡像電腦上儲存的電腦，而另一個） 的選項。</span><span class="sxs-lookup"><span data-stu-id="466da-118">The **Edit Properties** dialog box also gives you the option of creating a SQL mirror for your monitoring database (a SQL mirror enables you to maintain two copies of your monitoring database, one copy stored on the monitoring store computer and the other on the SQL mirror computer).</span></span> <span data-ttu-id="466da-119">若要啟用鏡像，請選取 T**他 SQL 執行個體為鏡像關係]** ，輸入 [**鏡像連接埠號碼**] 方塊中的鏡像伺服器的連接埠號碼。</span><span class="sxs-lookup"><span data-stu-id="466da-119">To enable mirroring, select T**his SQL instance is in mirroring relation** and enter the port number for the mirror server in the **Mirroring port number** box.</span></span>

7.  <span data-ttu-id="466da-120">在 [**編輯內容**] 對話方塊中，按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="466da-120">In the **Edit Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="466da-121">之後將監控存放區與前端集區產生關聯中，您必須發佈新拓撲前所做的變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="466da-121">After associating the monitoring store with a Front End pool you must publish the new topology before the changes take effect.</span></span> <span data-ttu-id="466da-122">若要發行新拓撲，完成下列步驟在拓撲產生器：</span><span class="sxs-lookup"><span data-stu-id="466da-122">To publish your new topology, complete the following steps in Topology Builder:</span></span>

1.  <span data-ttu-id="466da-123">按一下 [**動作]**，並指向 [**拓撲**]，然後按一下 [**發佈**]。</span><span class="sxs-lookup"><span data-stu-id="466da-123">Click **Action**, point to **Topology**, and then click **Publish**.</span></span>

2.  <span data-ttu-id="466da-124">在 [發行拓撲精靈] 上 [**發行拓撲**] 頁面中，按一下 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="466da-124">In the Publish Topology wizard, on the **Publish the topology** page, click **Next**.</span></span>

3.  <span data-ttu-id="466da-125">在 **[發行精靈完成]** 頁面上，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="466da-125">On the **Publishing wizard complete** page, click **Finish**.</span></span>

<span data-ttu-id="466da-126">已發行拓撲之後就可以安裝監控資料庫將裝載監控存放區的電腦上。</span><span class="sxs-lookup"><span data-stu-id="466da-126">After the topology has been published you can then install the monitoring database on the computer that will host the monitoring store.</span></span> <span data-ttu-id="466da-127">可以透過使用 Lync Server 管理命令介面和 Windows PowerShell 安裝監控資料庫。</span><span class="sxs-lookup"><span data-stu-id="466da-127">The monitoring database can be installed by using the Lync Server Management Shell and Windows PowerShell.</span></span> <span data-ttu-id="466da-128">若要安裝在本機上的資料庫 (亦即執行 Lync Server 管理命令介面的相同電腦上安裝資料庫)，啟動 Management Shell 上適當的電腦，然後輸入下列命令並按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="466da-128">To install the database locally (that is, to install the database on the same computer where you are running the Lync Server Management Shell), start the Management Shell on the appropriate computer, then type in the following command and press ENTER:</span></span>

    Install-CsDatabase -LocalDatabases

<span data-ttu-id="466da-129">當您執行上述命令時，Install-csdatabase 將讀取目前的 Lync Server 拓撲、 判斷哪些資料庫需要安裝在本機電腦，然後再自動安裝和設定每一個資料庫。</span><span class="sxs-lookup"><span data-stu-id="466da-129">When you run the preceding command, Install-CsDatabase will read the current Lync Server topology, determine which databases need to be installed on the local computer, and then automatically install and configure each of those databases.</span></span>

<span data-ttu-id="466da-130">若要安裝資料庫 （也就是管理命令介面執行所在之電腦以外的電腦） 的遠端電腦上，您必須包含至少兩個參數： ConfiguredDatabases 參數與 SqlServerFqdn 參數。</span><span class="sxs-lookup"><span data-stu-id="466da-130">To install the database on a remote computer (that is, a computer other than the computer where the Management Shell is running) you must include at least two parameters: the ConfiguredDatabases parameter and the SqlServerFqdn parameter.</span></span> <span data-ttu-id="466da-131">這些參數會告訴 Install-csdatabase 指令程式來擷取 Lync Server 拓撲，然後安裝並設定必要的資料庫 SqlServerFqdn 參數所指定的電腦上。</span><span class="sxs-lookup"><span data-stu-id="466da-131">These parameters tell the Install-CsDatabase cmdlet to retrieve the Lync Server topology and then install and configure the required databases on the computer specified by the SqlServerFqdn parameter.</span></span> <span data-ttu-id="466da-132">SqlServerFqdn 參數必須使用參數值，代表電腦的完整的網域名稱之資料庫的安裝位置。</span><span class="sxs-lookup"><span data-stu-id="466da-132">The SqlServerFqdn parameter must use a parameter value representing the fully qualified domain name of the computer where the databases are to be installed.</span></span>

<span data-ttu-id="466da-133">例如，此命令在電腦 atl-sql-001.litwareinc.com 安裝監控資料庫的 sql-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="466da-133">For example, this command installs the monitoring database on the computer atl-sql-001.litwareinc.com:</span></span>

    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com

<span data-ttu-id="466da-134">或者，您可以藉由將裝載監控存放區的電腦上執行 Lync Server 部署精靈安裝監控資料庫。</span><span class="sxs-lookup"><span data-stu-id="466da-134">Alternatively, you can install the monitoring database by running the Lync Server Deployment Wizard on the computer that will host the monitoring store.</span></span> <span data-ttu-id="466da-135">若要這麼做，請登入適當的電腦，然後完成下列程序：</span><span class="sxs-lookup"><span data-stu-id="466da-135">To do this, log on to the appropriate computer and complete the following procedure:</span></span>

1.  <span data-ttu-id="466da-136">按一下 [**開始]**、 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 部署精靈**。</span><span class="sxs-lookup"><span data-stu-id="466da-136">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="466da-137">在部署精靈中按一下 **[安裝或更新 Lync Server 系統]**。</span><span class="sxs-lookup"><span data-stu-id="466da-137">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="466da-138">在 [**部署**] 頁面上 [**步驟 2： 安裝或移除 Lync Server 元件**，按一下 [**再執行一次**。</span><span class="sxs-lookup"><span data-stu-id="466da-138">On the **Deploy** page, under **Step 2: Setup or Remove Lync Server Components**, click **Run Again**.</span></span>

4.  <span data-ttu-id="466da-139">在 [安裝 Lync Server 元件精靈] 在**安裝 Lync Server 元件**] 頁面上，按一下 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="466da-139">In the Setup Lync Server components wizard, on the **Setup Lync Server components** page, click **Next**.</span></span>

5.  <span data-ttu-id="466da-140">在 [**指定 Msi 的路徑**] 頁面上輸入 ocscore.msi 檔 （包含 Lync Server 安裝媒體檔案） 的路徑，然後按一下 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="466da-140">On the **Specify path to MSIs** page, type the path to the file Ocscore.msi (a file included with your Lync Server installation media) and then click **Next**.</span></span>

6.  <span data-ttu-id="466da-141">在 **[執行命令]** 頁面上，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="466da-141">On the **Executing Commands** page, click **Finish**.</span></span>

<span data-ttu-id="466da-142">若要確保所需的 Lync Server 服務已啟動，請按一下 [**執行**] 標題下**步驟 4： 啟動服務**在 [**部署**] 頁面</span><span class="sxs-lookup"><span data-stu-id="466da-142">To ensure that all the required Lync Server services have started, click **Run** under the heading **Step 4: Start Services** on the **Deploy** page</span></span>

</div>

<span> </span>

</div>

</div>

</div>

