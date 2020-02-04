---
title: Lync Server 2013：將監視存放區與前端池關聯
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
ms.openlocfilehash: 06cc3c85911b7581117a475d1e390aafdf760ca1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associating-a-monitoring-store-with-a-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="9baa4-102">在 Lync Server 2013 中將監控存放區與前端池關聯</span><span class="sxs-lookup"><span data-stu-id="9baa4-102">Associating a monitoring store with a Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9baa4-103">_**主題上次修改日期：** 2013-04-22_</span><span class="sxs-lookup"><span data-stu-id="9baa4-103">_**Topic Last Modified:** 2013-04-22_</span></span>

<span data-ttu-id="9baa4-104">在 Microsoft Lync Server 2013 中，監視資料只能在已與監視存放區相關聯的前端池上收集，通常會執行的工作是在拓撲建立器中定義 [前端] 池。</span><span class="sxs-lookup"><span data-stu-id="9baa4-104">In Microsoft Lync Server 2013 monitoring data can only be collected on Front End pools that have been associated with a monitoring store, a task typically carried out you define a Front End pool in Topology Builder.</span></span> <span data-ttu-id="9baa4-105">若要將監視存放區與新的前端池建立關聯，請務必在 [定義新的前端池] 嚮導的 [**選取功能**] 頁面上，選取 [**監視] （呼叫詳細資料記錄及記錄品質統計資料）** 的選項。</span><span class="sxs-lookup"><span data-stu-id="9baa4-105">To associate a monitoring store with a new Front End pool, make sure that you select the option **Monitoring (call detail recording and logging of quality of experience metrics)** on the **Select Features** page of the Define New Front End Pool wizard.</span></span> <span data-ttu-id="9baa4-106">請注意，如果您選取此選項，您也必須指定 SQL store 才能完成嚮導;不過，此存放區在您執行此嚮導時不一定要存在。</span><span class="sxs-lookup"><span data-stu-id="9baa4-106">Note that, if you select this option, you must also specify a SQL store in order to complete the wizard; however, this store does not have to exist at the time you run the wizard.</span></span> <span data-ttu-id="9baa4-107">這表示您可以先將一個池與監視存放區建立關聯，然後再設定該存放區。</span><span class="sxs-lookup"><span data-stu-id="9baa4-107">That means that you can first associate a pool with a monitoring store, then later setup and configure that store.</span></span>

<span data-ttu-id="9baa4-108">或者，您也可以透過完成下列程式，將現有的前端池與新的或不同的監視存放區建立關聯：</span><span class="sxs-lookup"><span data-stu-id="9baa4-108">Alternatively, you can associate an existing Front End pool with a new or different monitoring store by completing the following procedure:</span></span>

1.  <span data-ttu-id="9baa4-109">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。</span><span class="sxs-lookup"><span data-stu-id="9baa4-109">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="9baa4-110">在 [**拓撲**建立器] 對話方塊中，選取 [**從現有的部署下載拓撲結構**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="9baa4-110">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>

3.  <span data-ttu-id="9baa4-111">在 [**另存**新檔] 對話方塊中，輸入目前拓撲的檔案名，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="9baa4-111">In the **Save As** dialog box, enter a file name for your current topology and then click **Save**.</span></span> <span data-ttu-id="9baa4-112">在新拓撲發生問題時，可以稍後檢索並重新發佈已儲存的拓撲。</span><span class="sxs-lookup"><span data-stu-id="9baa4-112">The saved topology can later be retrieved and re-published in case there are problems with the new topology.</span></span>

4.  <span data-ttu-id="9baa4-113">在 [拓撲建立器] 中，展開 [ **Lync Server 2013**]，展開包含 [前端] 池的網站名稱，然後按一下 [展開**企業版前端池**]。</span><span class="sxs-lookup"><span data-stu-id="9baa4-113">In Topology Builder, expand **Lync Server 2013**, expand the name of the site containing the Front End pool, then click expand **Enterprise Edition Front End pools**.</span></span>

5.  <span data-ttu-id="9baa4-114">以滑鼠右鍵按一下要與 [監視] 存放區相關聯的池子名稱，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="9baa4-114">Right-click the name of the pool to be associated with the monitoring store and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="9baa4-115">在 [**編輯屬性**] 對話方塊的 [**一般**] 索引標籤上，選取 [**監視] （CDR 與 QoE 度量）** ，然後從 [**監視 SQL server store** ] 下拉式清單中選取現有的 SQL server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="9baa4-115">In the **Edit Properties** dialog box, on the **General** tab, select the option **Monitoring (CDR and QoE metrics)** and then select an existing SQL Server database from the **Monitoring SQL Server store** dropdown list.</span></span> <span data-ttu-id="9baa4-116">（或者，按一下 [**新增**] 以將池與新的資料庫存放區建立關聯）。如果您選擇使用新的資料庫存放區，請在 [**定義新的 SQL store** ] 對話方塊中，于 [ **sql server FQDN** ] 方塊中輸入 sql server 電腦的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="9baa4-116">(Or, click **New** to associate the pool with a new database store.) If you choose to use a new database store then, in the **Define New SQL Store** dialog box, enter the fully qualified domain name of the SQL Server computer in the **Sql Server FQDN** box.</span></span> <span data-ttu-id="9baa4-117">如果您想要使用該存放區的預設 SQL Server 實例，請選取 [**預設實例**];否則，請選取 [**命名實例**]，然後在 [**命名實例**] 方塊中輸入實例名稱。</span><span class="sxs-lookup"><span data-stu-id="9baa4-117">If you want to use the default SQL Server instance for that store select **Default Instance**; otherwise select **Named Instance** and enter the instance name in the **Named Instance** box.</span></span>
    
    <span data-ttu-id="9baa4-118">[**編輯屬性**] 對話方塊也可讓您選擇為監視資料庫建立 SQL 鏡像（sql mirror 可讓您維護監視資料庫的兩份複本，一個複本儲存在監視儲存電腦上，另一個則在 SQL 鏡像電腦上）。</span><span class="sxs-lookup"><span data-stu-id="9baa4-118">The **Edit Properties** dialog box also gives you the option of creating a SQL mirror for your monitoring database (a SQL mirror enables you to maintain two copies of your monitoring database, one copy stored on the monitoring store computer and the other on the SQL mirror computer).</span></span> <span data-ttu-id="9baa4-119">若要啟用 [鏡像]，請選取 [T**他的 SQL 實例是在鏡像關聯中**]，然後在 [**鏡像埠號碼**] 方塊中輸入鏡像伺服器的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="9baa4-119">To enable mirroring, select T**his SQL instance is in mirroring relation** and enter the port number for the mirror server in the **Mirroring port number** box.</span></span>

7.  <span data-ttu-id="9baa4-120">在 [**編輯屬性**] 對話方塊中，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="9baa4-120">In the **Edit Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="9baa4-121">將監視存放區與前端池關聯之後，您必須發佈新的拓撲，變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="9baa4-121">After associating the monitoring store with a Front End pool you must publish the new topology before the changes take effect.</span></span> <span data-ttu-id="9baa4-122">若要發佈新的拓撲，請在拓撲建立器中完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="9baa4-122">To publish your new topology, complete the following steps in Topology Builder:</span></span>

1.  <span data-ttu-id="9baa4-123">按一下 [**動作**]，指向 [**拓撲**]，然後按一下 [**發佈**]。</span><span class="sxs-lookup"><span data-stu-id="9baa4-123">Click **Action**, point to **Topology**, and then click **Publish**.</span></span>

2.  <span data-ttu-id="9baa4-124">在 [發佈拓撲嚮導] 的 [**發佈拓撲**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="9baa4-124">In the Publish Topology wizard, on the **Publish the topology** page, click **Next**.</span></span>

3.  <span data-ttu-id="9baa4-125">在 [**發佈嚮導完成]** 頁面上，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="9baa4-125">On the **Publishing wizard complete** page, click **Finish**.</span></span>

<span data-ttu-id="9baa4-126">在拓撲發佈之後，您就可以在要主持監視存放區的電腦上安裝監視資料庫。</span><span class="sxs-lookup"><span data-stu-id="9baa4-126">After the topology has been published you can then install the monitoring database on the computer that will host the monitoring store.</span></span> <span data-ttu-id="9baa4-127">您可以使用 Lync Server 管理命令介面和 Windows PowerShell 來安裝監視資料庫。</span><span class="sxs-lookup"><span data-stu-id="9baa4-127">The monitoring database can be installed by using the Lync Server Management Shell and Windows PowerShell.</span></span> <span data-ttu-id="9baa4-128">若要在本機安裝資料庫（也就是在執行 Lync Server 管理命令介面的同一部電腦上安裝資料庫），請在適當的電腦上啟動管理命令介面，然後輸入下列命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="9baa4-128">To install the database locally (that is, to install the database on the same computer where you are running the Lync Server Management Shell), start the Management Shell on the appropriate computer, then type in the following command and press ENTER:</span></span>

    Install-CsDatabase -LocalDatabases

<span data-ttu-id="9baa4-129">當您執行上述命令時，安裝 CsDatabase 會讀取目前的 Lync 伺服器拓撲，判斷需要在本機電腦上安裝哪些資料庫，然後自動安裝並設定每個資料庫。</span><span class="sxs-lookup"><span data-stu-id="9baa4-129">When you run the preceding command, Install-CsDatabase will read the current Lync Server topology, determine which databases need to be installed on the local computer, and then automatically install and configure each of those databases.</span></span>

<span data-ttu-id="9baa4-130">若要在遠端電腦（也就是執行管理命令介面之電腦以外的電腦）上安裝資料庫，您必須至少包含兩個參數： ConfiguredDatabases 參數和 SqlServerFqdn 參數。</span><span class="sxs-lookup"><span data-stu-id="9baa4-130">To install the database on a remote computer (that is, a computer other than the computer where the Management Shell is running) you must include at least two parameters: the ConfiguredDatabases parameter and the SqlServerFqdn parameter.</span></span> <span data-ttu-id="9baa4-131">這些參數會告訴 CsDatabase Cmdlet 來檢索 Lync Server 拓撲，然後在 SqlServerFqdn 參數所指定的電腦上安裝並設定所需的資料庫。</span><span class="sxs-lookup"><span data-stu-id="9baa4-131">These parameters tell the Install-CsDatabase cmdlet to retrieve the Lync Server topology and then install and configure the required databases on the computer specified by the SqlServerFqdn parameter.</span></span> <span data-ttu-id="9baa4-132">SqlServerFqdn 參數必須使用代表要安裝資料庫之電腦之完整功能變數名稱的參數值。</span><span class="sxs-lookup"><span data-stu-id="9baa4-132">The SqlServerFqdn parameter must use a parameter value representing the fully qualified domain name of the computer where the databases are to be installed.</span></span>

<span data-ttu-id="9baa4-133">例如，這個命令會在電腦 atl-sql-001.litwareinc.com 上安裝監視資料庫：</span><span class="sxs-lookup"><span data-stu-id="9baa4-133">For example, this command installs the monitoring database on the computer atl-sql-001.litwareinc.com:</span></span>

    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com

<span data-ttu-id="9baa4-134">或者，您也可以在將主持監視存放區的電腦上執行 Lync Server 部署嚮導來安裝監視資料庫。</span><span class="sxs-lookup"><span data-stu-id="9baa4-134">Alternatively, you can install the monitoring database by running the Lync Server Deployment Wizard on the computer that will host the monitoring store.</span></span> <span data-ttu-id="9baa4-135">若要這樣做，請登入適當的電腦並完成下列程式：</span><span class="sxs-lookup"><span data-stu-id="9baa4-135">To do this, log on to the appropriate computer and complete the following procedure:</span></span>

1.  <span data-ttu-id="9baa4-136">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 部署嚮導]**。</span><span class="sxs-lookup"><span data-stu-id="9baa4-136">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="9baa4-137">在 [部署嚮導] 中，按一下 [**安裝或更新 Lync Server 系統**]。</span><span class="sxs-lookup"><span data-stu-id="9baa4-137">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="9baa4-138">在 [**部署**] 頁面的 [**步驟2：設定] 或 [移除 Lync Server 元件**] 底下，再次按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="9baa4-138">On the **Deploy** page, under **Step 2: Setup or Remove Lync Server Components**, click **Run Again**.</span></span>

4.  <span data-ttu-id="9baa4-139">在 [安裝 Lync Server 元件] 嚮導中，按一下 [**安裝 Lync server 元件**] 頁面上的 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="9baa4-139">In the Setup Lync Server components wizard, on the **Setup Lync Server components** page, click **Next**.</span></span>

5.  <span data-ttu-id="9baa4-140">在 [**指定要 MSIs 的路徑**] 頁面上，輸入檔案 Ocscore 的路徑（包含在 Lync Server 安裝媒體中的檔案），然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="9baa4-140">On the **Specify path to MSIs** page, type the path to the file Ocscore.msi (a file included with your Lync Server installation media) and then click **Next**.</span></span>

6.  <span data-ttu-id="9baa4-141">在 [**執行命令**] 頁面上，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="9baa4-141">On the **Executing Commands** page, click **Finish**.</span></span>

<span data-ttu-id="9baa4-142">若要確保所有必要的 Lync Server 服務都已啟動，請在 [**部署**] 頁面上，按一下 [標題] 下的 [**執行**] **： [啟動服務**]</span><span class="sxs-lookup"><span data-stu-id="9baa4-142">To ensure that all the required Lync Server services have started, click **Run** under the heading **Step 4: Start Services** on the **Deploy** page</span></span>

</div>

<span> </span>

</div>

</div>

</div>

