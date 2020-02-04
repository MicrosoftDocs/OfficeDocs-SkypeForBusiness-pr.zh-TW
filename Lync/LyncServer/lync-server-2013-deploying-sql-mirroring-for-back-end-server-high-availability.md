---
title: 針對後端伺服器高可用性部署 SQL 鏡像
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying SQL mirroring for Back End Server high availability
ms:assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204992(v=OCS.15)
ms:contentKeyID: 48184451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a37c554faf81795363522378160abf5081084f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-sql-mirroring-for-back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="dd4a5-102">在 Lync Server 2013 中針對後端伺服器高可用性部署 SQL 鏡像</span><span class="sxs-lookup"><span data-stu-id="dd4a5-102">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd4a5-103">_**主題上次修改日期：** 2014-01-08_</span><span class="sxs-lookup"><span data-stu-id="dd4a5-103">_**Topic Last Modified:** 2014-01-08_</span></span>

<span data-ttu-id="dd4a5-104">若要能夠部署 SQL 鏡像，您的伺服器必須執行至少 SQL Server 2008 R2。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-104">To be able to deploy SQL mirroring, your servers must run a minimum of SQL Server 2008 R2.</span></span> <span data-ttu-id="dd4a5-105">這個版本必須在所有涉及的伺服器上執行：主要、鏡像和見證。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-105">This version must run on all the involved servers: the primary, mirror, and the witness.</span></span> <span data-ttu-id="dd4a5-106">如需詳細資訊[http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921)，請參閱。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-106">For details, see [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921).</span></span>

<span data-ttu-id="dd4a5-107">一般來說，在具有見證的兩台後端伺服器之間設定 SQL 鏡像需要下列事項：</span><span class="sxs-lookup"><span data-stu-id="dd4a5-107">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>

  - <span data-ttu-id="dd4a5-108">主伺服器版本的 SQL Server 必須支援 SQL 鏡像。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-108">The primary server’s version of SQL Server must support SQL mirroring.</span></span>

  - <span data-ttu-id="dd4a5-109">[主要]、[鏡像] 和 [見證伺服器] （如果已部署）必須有相同版本的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-109">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span>

  - <span data-ttu-id="dd4a5-110">主要和鏡像必須擁有相同版本的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-110">The primary and the mirror must have the same edition of SQL Server.</span></span> <span data-ttu-id="dd4a5-111">見證可能會有不同的版本。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-111">The witness may have a different edition.</span></span>

<span data-ttu-id="dd4a5-112">如需針對見證角色支援哪些 SQL 版本的 SQL 最佳做法，請參閱 MSDN 文件庫中的「資料庫鏡像見證」 [http://go.microsoft.com/fwlink/p/?LinkId=247345](http://go.microsoft.com/fwlink/p/?linkid=247345)。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-112">For SQL best practices in terms of what SQL versions are supported for a Witness role, see "Database Mirroring Witness" in the MSDN Library at [http://go.microsoft.com/fwlink/p/?LinkId=247345](http://go.microsoft.com/fwlink/p/?linkid=247345).</span></span>

<span data-ttu-id="dd4a5-113">您可以使用拓撲產生器來部署 SQL 鏡像。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-113">You use Topology Builder to deploy SQL mirroring.</span></span> <span data-ttu-id="dd4a5-114">您可以在 [拓撲建立器] 中選取一個選項來鏡像資料庫，而 [拓撲建立器] 會在您發佈拓撲時設定鏡像（包括設定見證）。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-114">You select an option in Topology Builder to mirror the databases, and Topology Builder sets up the mirroring (including setting up a witness, if you want) when you publish the topology.</span></span> <span data-ttu-id="dd4a5-115">請注意，您可以在設定或移除鏡像的同時，設定或移除見證。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-115">Note that you set up or remove the witness at the same time you set up or remove the mirror.</span></span> <span data-ttu-id="dd4a5-116">不需要單獨部署或移除見證的個別命令。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-116">There is no separate command to deploy or remove only a witness.</span></span>

<span data-ttu-id="dd4a5-117">若要設定伺服器鏡像，您必須先正確設定 SQL 資料庫許可權。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-117">To configure server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="dd4a5-118">如需詳細資訊，請參閱 [設定資料庫鏡像或 AlwaysOn 可用性群組（SQL Server）的登入[http://go.microsoft.com/fwlink/p/?LinkId=268454](http://go.microsoft.com/fwlink/p/?linkid=268454)帳戶]。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-118">For details, see "Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268454](http://go.microsoft.com/fwlink/p/?linkid=268454).</span></span>

<span data-ttu-id="dd4a5-119">有了 SQL 鏡像，資料庫復原模式永遠都設為**Full**，這表示您必須密切監視事務日誌大小，並定期備份事務日誌，以免在後端伺服器上耗盡磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-119">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers.</span></span> <span data-ttu-id="dd4a5-120">事務記錄備份的頻率取決於記錄的增長率，而這取決於前端池中使用者活動所產生的資料庫事務。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-120">The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool.</span></span> <span data-ttu-id="dd4a5-121">我們建議您決定 Lync 部署工作負載預期的事務日誌增長量，讓您可以據此進行規劃。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-121">We recommend that you determine how much transaction log growth is expected for your Lync deployment workload so that you can do the planning accordingly.</span></span> <span data-ttu-id="dd4a5-122">下列文章提供有關 SQL 備份與記錄管理的其他資訊：</span><span class="sxs-lookup"><span data-stu-id="dd4a5-122">The following articles provide additional information on SQL backup and log management:</span></span>

  - <span data-ttu-id="dd4a5-123">資料庫恢復模型：「恢復模型（SQL Server）」[http://go.microsoft.com/fwlink/p/?LinkId=268446](http://go.microsoft.com/fwlink/p/?linkid=268446)</span><span class="sxs-lookup"><span data-stu-id="dd4a5-123">Database recovery models: "Recovery Models (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268446](http://go.microsoft.com/fwlink/p/?linkid=268446)</span></span>

  - <span data-ttu-id="dd4a5-124">備份概述：「備份概述（SQL Server）」[http://go.microsoft.com/fwlink/p/?LinkId=268449](http://go.microsoft.com/fwlink/p/?linkid=268449)</span><span class="sxs-lookup"><span data-stu-id="dd4a5-124">Backup overview: "Backup Overview (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268449](http://go.microsoft.com/fwlink/p/?linkid=268449)</span></span>

  - <span data-ttu-id="dd4a5-125">備份事務日誌： [備份事務記錄檔（SQL Server）][http://go.microsoft.com/fwlink/p/?LinkId=268452](http://go.microsoft.com/fwlink/p/?linkid=268452)</span><span class="sxs-lookup"><span data-stu-id="dd4a5-125">Backup transaction log: "Backup a Transaction Log (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268452](http://go.microsoft.com/fwlink/p/?linkid=268452)</span></span>

<span data-ttu-id="dd4a5-126">有了 SQL 鏡像，您可以在建立池時，或在已建立池之後，設定拓撲以進行鏡像。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-126">With SQL mirroring, you can either configure the topology for mirroring when you create the pools, or after the pools are already created.</span></span>



> [!IMPORTANT]
> <span data-ttu-id="dd4a5-127">只有在主要、鏡像和見證（如果需要）伺服器都屬於同一個網域時，才支援使用拓撲建立器或 Cmdlet 來設定及移除 SQL 鏡像。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-127">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="dd4a5-128">如果您想要在不同網域中的伺服器之間設定 SQL 鏡像，請參閱您的 SQL Server 檔。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-128">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span>





> [!IMPORTANT]
> <span data-ttu-id="dd4a5-129">每當您對後端資料庫鏡像關聯進行變更時，您必須重新開機池中的所有前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-129">Whenever you make a change to a Back End Database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span><BR><span data-ttu-id="dd4a5-130">如需鏡像變更（例如變更鏡像的位置），您必須使用拓撲建立器來執行這三個步驟：</span><span class="sxs-lookup"><span data-stu-id="dd4a5-130">For a change in mirroring, (such as changing the location of a mirror), you must use Topology Builder to perform these three steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="dd4a5-131">從舊的鏡像伺服器移除鏡像。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-131">Remove mirroring from the old mirror server.</span></span></P>
> <LI>
> <P><span data-ttu-id="dd4a5-132">將 [鏡像] 新增至新的鏡像伺服器。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-132">Add mirroring to the new mirror server.</span></span></P>
> <LI>
> <P><span data-ttu-id="dd4a5-133">發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-133">Publish the topology.</span></span></P></LI></OL>




> [!NOTE]
> <span data-ttu-id="dd4a5-134">必須針對要寫入的鏡像檔案建立檔案共用，而且 SQL Server 和 SQL 代理程式在其上執行的服務需要讀/寫存取權。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-134">A file share has to be created for the mirror files to be written to, and the service that SQL Server and SQL Agent are running under needs read/write access.</span></span> <span data-ttu-id="dd4a5-135">如果 SQL Server 服務是在網路服務的內容下執行，您可以將網域&lt; &gt;&#92;&lt;SQLSERVERNAME&gt;$ 的使用者新增至主體和鏡像 SQL server，以進行共用許可權。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-135">If the SQL Server service is running under the context of Network Service, you can add &lt;Domain&gt;&#92;&lt;SQLSERVERNAME&gt;$ of both the Principal and Mirror SQL Servers to the share permissions.</span></span> <span data-ttu-id="dd4a5-136">$ 對於確認這是電腦帳戶而言，這是很重要的。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-136">The $ is important to identify that this is a computer account.</span></span>


<div>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a><span data-ttu-id="dd4a5-137">在拓撲建立器中建立池時設定 SQL 鏡像</span><span class="sxs-lookup"><span data-stu-id="dd4a5-137">To configure SQL mirroring while creating a pool in Topology Builder</span></span>

1.  <span data-ttu-id="dd4a5-138">在 [**定義 SQL store** ] 頁面上，按一下 [ **SQL 存放區**] 方塊旁的 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-138">On the **Define the SQL Store** page, click **New** next to the **SQL store** box.</span></span>

2.  <span data-ttu-id="dd4a5-139">在 [**定義新的 SQL**市集中] 頁面上，指定主要商店，選取 [**此 sql 實例是在鏡像關聯中**]，指定 sql 鏡像埠號碼（預設值為5022），然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-139">On the **Define new SQL Store** page, specify the primary store, select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default is 5022), and then click **OK**.</span></span>

3.  <span data-ttu-id="dd4a5-140">回到 [**定義 sql store** ] 頁面上，選取 [**啟用 SQL store 鏡像**]。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-140">Back on the **Define the SQL store** page, select **Enable SQL Store mirroring**.</span></span>

4.  <span data-ttu-id="dd4a5-141">在 [**定義新的 SQL store** ] 頁面中，指定要用來做為鏡像的 SQL 存放區。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-141">In the **Define new SQL Store** page, specify the SQL store to be used as the mirror.</span></span> <span data-ttu-id="dd4a5-142">選取 [**這個 SQL 實例是在鏡像關聯中**]，指定埠號碼（預設值為5022），然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-142">Select **This SQL instance is in mirroring relation**, specify the port number (the default is 5022), and then click **OK**.</span></span>

5.  <span data-ttu-id="dd4a5-143">如果您想要此鏡像的見證，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="dd4a5-143">If you want a witness for this mirror, do the following:</span></span>
    
    1.  <span data-ttu-id="dd4a5-144">選取 **[使用 SQL 鏡像見證] 來啟用自動容錯移轉**。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-144">Select **Use SQL mirroring witness to enable automatic failover**.</span></span>
    
    2.  <span data-ttu-id="dd4a5-145">在 [**定義 SQL 書店**] 頁面中，選取 **[使用 SQL 鏡像見證來啟用自動容錯移轉**]，然後指定要用作見證的 SQL Store。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-145">In the **Define the SQL Store** page, select **Use SQL mirroring witness to enable automatic failover**, and specify the SQL store to be used as the witness.</span></span>
    
    3.  <span data-ttu-id="dd4a5-146">指定埠號碼（預設值為7022），然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-146">Specify the port number (the default is 7022) and click **OK**.</span></span>

6.  <span data-ttu-id="dd4a5-147">在拓撲中定義完您的 [前端] 池及所有其他角色之後，請使用 [拓撲建立器] 發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-147">After you are done defining your Front End pool and all other roles in your topology, use Topology Builder to publish the topology.</span></span> <span data-ttu-id="dd4a5-148">當拓撲發佈時，如果主機中央管理儲存區的前端池已啟用 SQL 鏡像，您會看到建立主要和鏡像 SQL store 資料庫的選項。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-148">When the topology is published, if the Front End pool that hosts Central Management store has SQL mirroring enabled, you will see an option to create both primary and mirror SQL store databases.</span></span>
    
    <span data-ttu-id="dd4a5-149">按一下 [**設定**]，然後輸入要做為鏡像備份之檔案共用使用的路徑。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-149">Click **Settings**, and type the path to use as the file share for the mirroring backup.</span></span>
    
    <span data-ttu-id="dd4a5-150">按一下 **[確定]** ，然後按一下 **[下一步**]，建立資料庫併發布拓撲。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-150">Click **OK** and then **Next** to create the databases and publish the topology.</span></span> <span data-ttu-id="dd4a5-151">將會部署鏡像與見證（如果已指定）。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-151">The mirroring and the witness (if specified) will be deployed.</span></span>

<span data-ttu-id="dd4a5-152">您可以使用 [拓撲建立器] 來編輯已存在的 [池] 的屬性，以啟用 SQL 鏡像。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-152">You can use Topology Builder to edit the properties of an already existing pool to enable SQL mirroring.</span></span>

</div>

<div>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a><span data-ttu-id="dd4a5-153">在拓撲建立器中新增 SQL 鏡像至現有的前端池</span><span class="sxs-lookup"><span data-stu-id="dd4a5-153">To add SQL mirroring to an existing Front End pool in Topology Builder</span></span>

1.  <span data-ttu-id="dd4a5-154">在拓撲建立器中，以滑鼠右鍵按一下該池子，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-154">In Topology Builder, right-click the pool and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="dd4a5-155">選取 [**啟用 SQL Store 鏡像**]，然後按一下 [**鏡像 SQL store**] 旁的 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-155">Select **Enable SQL Store Mirroring**, and then click **New** next to **Mirroring SQL Store**.</span></span>

3.  <span data-ttu-id="dd4a5-156">指定您要用來做為鏡像的 SQL 存放區。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-156">Specify the SQL store that you want to use as the mirror.</span></span>

4.  <span data-ttu-id="dd4a5-157">選取 [**這個 sql 實例是在鏡像關聯中**]，指定 [SQL 鏡像埠號碼] 預設埠為5022），然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-157">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number the default port is 5022), and then click **OK**.</span></span>

5.  <span data-ttu-id="dd4a5-158">如果您想要設定見證，請選取 **[使用 SQL 鏡像見證來啟用自動容錯移轉**]，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-158">If you want to configure a witness, select **Use SQL mirroring witness to enable automatic failover**, and click **New**.</span></span>

6.  <span data-ttu-id="dd4a5-159">指定您要用來做為見證的 SQL store。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-159">Specify the SQL store that you want to use as the witness.</span></span>

7.  <span data-ttu-id="dd4a5-160">選取 [**這個 sql 實例是在鏡像關聯中**]，指定 SQL 鏡像埠號碼（預設埠為7022），然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-160">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default port is 7022), and then click **OK**.</span></span>

8.  <span data-ttu-id="dd4a5-161">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-161">Click **OK**.</span></span>

9.  <span data-ttu-id="dd4a5-162">發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-162">Publish the topology.</span></span> <span data-ttu-id="dd4a5-163">當您這麼做時，系統會提示您安裝資料庫。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-163">When you do so, you will be prompted to install the database.</span></span>
    
    <span data-ttu-id="dd4a5-164">在拓撲發佈程式期間，系統會要求您定義檔案共用路徑。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-164">During the topology publishing process, you will be asked to define a file share path.</span></span> <span data-ttu-id="dd4a5-165">參與鏡像的 SQL 伺服器必須擁有此檔案共用的讀/寫存取權，才能建立鏡像。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-165">The SQL Servers that participate in the mirroring must have read/write access to this file share for the mirror to be established.</span></span>

<span data-ttu-id="dd4a5-166">接著，您必須先安裝資料庫，然後再繼續進行下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-166">You must then install the database before going on to the next procedure.</span></span>

<span data-ttu-id="dd4a5-167">設定 SQL 鏡像時，請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="dd4a5-167">You should keep the following in mind when setting up SQL mirroring:</span></span>

  - <span data-ttu-id="dd4a5-168">如果鏡像端點已存在，則會使用在該處定義的埠來重複使用它，並將略過您在拓撲中指定的埠。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-168">If a mirroring endpoint already exists, it will be reused using the ports defined there, and will ignore the ones you specify in the topology.</span></span>

  - <span data-ttu-id="dd4a5-169">已針對相同伺服器上的其他應用程式（包括適用于其他 SQL 實例的任何埠）已分配的任何埠，都不應該用於目前已安裝的 SQL 實例。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-169">Any port already allocated for other applications on the same server, including those for other SQL instances, should not be used for the installed SQL instances at hand.</span></span> <span data-ttu-id="dd4a5-170">這表示如果您在同一個伺服器上安裝了多個 SQL 實例，就不一定要使用相同的埠進行鏡像。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-170">This implies that if you have more than one SQL instance installed on the same server, they must not use the same port for mirroring.</span></span> <span data-ttu-id="dd4a5-171">如需詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="dd4a5-171">For details, see the following articles:</span></span>
    
      - <span data-ttu-id="dd4a5-172">[MSDN Library] 中的 [指定伺服器網路位址（資料庫鏡像）][http://go.microsoft.com/fwlink/p/?LinkId=247346](http://go.microsoft.com/fwlink/p/?linkid=247346)</span><span class="sxs-lookup"><span data-stu-id="dd4a5-172">"Specify a Server Network Address (Database Mirroring)" in the MSDN Library at [http://go.microsoft.com/fwlink/p/?LinkId=247346](http://go.microsoft.com/fwlink/p/?linkid=247346)</span></span>
    
      - <span data-ttu-id="dd4a5-173">「資料庫鏡像端點（SQL Server）」[http://go.microsoft.com/fwlink/p/?LinkId=247347](http://go.microsoft.com/fwlink/p/?linkid=247347)</span><span class="sxs-lookup"><span data-stu-id="dd4a5-173">"The Database Mirroring Endpoint (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=247347](http://go.microsoft.com/fwlink/p/?linkid=247347)</span></span>

</div>

<div>

## <a name="using-lync-server-management-shell-cmdlets-to-set-up-sql-mirroring"></a><span data-ttu-id="dd4a5-174">使用 Lync Server 管理命令介面 Cmdlet 來設定 SQL 鏡像</span><span class="sxs-lookup"><span data-stu-id="dd4a5-174">Using Lync Server Management Shell Cmdlets to Set Up SQL Mirroring</span></span>

<span data-ttu-id="dd4a5-175">設定鏡像最簡單的方法是使用拓撲建立器，不過您也可以使用 Cmdlet 來執行此操作。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-175">The easiest way to set up mirroring is by using Topology Builder, but you can also do so using cmdlets.</span></span>

1.  <span data-ttu-id="dd4a5-176">開啟 Lync Server 管理命令介面視窗，並執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="dd4a5-176">Open a Lync Server Management Shell window and run the following cmdlet:</span></span>
    
        Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose 
    
    <span data-ttu-id="dd4a5-177">例如：</span><span class="sxs-lookup"><span data-stu-id="dd4a5-177">For example:</span></span>
    
        Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose 
    
    <span data-ttu-id="dd4a5-178">您會看到下列內容：</span><span class="sxs-lookup"><span data-stu-id="dd4a5-178">You will see the following:</span></span>
    
        Database Name:rtcxds 
                Data File:D:\CsData\BackendStore\rtc\DbPath\rtcxds.mdf 
                 Log File:D:\CsData\BackendStore\rtc\LogPath\rtcxds.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rtcshared 
                Data File:D:\CsData\BackendStore\rtc\DbPath\rtcshared.mdf 
                 Log File:D:\CsData\BackendStore\rtc\LogPath\rtcshared.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rtcab 
                Data File:D:\CsData\ABSStore\rtc\DbPath\rtcab.mdf 
                 Log File:D:\CsData\ABSStore\rtc\LogPath\rtcab.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rgsconfig 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsconfig.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsconfig.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rgsdyn 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsdyn.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsdyn.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:cpsdyn 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\cpsdyn.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\cpsdyn.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:xds 
                Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\xds.mdf 
                 Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\xds.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:lis 
                Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\lis.mdf 
                 Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\lis.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$
        [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): 

2.  <span data-ttu-id="dd4a5-179">確認下列事項：</span><span class="sxs-lookup"><span data-stu-id="dd4a5-179">Verify the following:</span></span>
    
      - <span data-ttu-id="dd4a5-180">如果在主要 SQL Server e04-ocs 中啟用 Windows 防火牆，則可透過防火牆存取埠5022。\_本機\\rtc。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-180">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the primary SQL Server e04-ocs.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="dd4a5-181">如果在鏡像 SQL Server K16-ocs 中啟用 Windows 防火牆，則可透過防火牆存取埠5022。\_本機\\rtc。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-181">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the mirror SQL Server K16-ocs.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="dd4a5-182">如果在見證 SQL Server AB14-lct 中啟用 Windows 防火牆，則可透過防火牆存取埠7022。\_本機\\rtc。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-182">Port 7022 is accessible through the firewall if Windows Firewall is enabled in the witness SQL Server AB14-lct.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="dd4a5-183">在所有主要和鏡像 SQL 伺服器上執行 SQL server 的帳戶，都有讀取/寫入檔案共用\\ \\E04 的許可權\\-OCS csdatabackup</span><span class="sxs-lookup"><span data-stu-id="dd4a5-183">Accounts running the SQL Servers on all primary and mirror SQL servers have read/write permission to the file share \\\\E04-OCS\\csdatabackup</span></span>
    
      - <span data-ttu-id="dd4a5-184">確認 Windows 管理工具（WMI）提供者正在所有這些伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-184">Verify that the Windows Management Instrumentation (WMI) provider is running on all these servers.</span></span> <span data-ttu-id="dd4a5-185">這個 Cmdlet 使用這個提供者來尋找在所有主要、鏡像伺服器和見證伺服器上執行之 SQL Server 服務的帳戶資訊。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-185">The cmdlet uses this provider to find the account information for SQL Server services running on all primary, mirror and witness servers.</span></span>
    
      - <span data-ttu-id="dd4a5-186">確認執行此 Cmdlet 的帳戶具有為所有鏡像伺服器的資料和記錄檔案建立資料夾的許可權。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-186">Verify that the account running this cmdlet has permission to create the folders for the data and log files for all the mirror servers.</span></span>
    
      - <span data-ttu-id="dd4a5-187">請注意，SQL 實例執行所用的使用者帳戶必須具備檔案共用的讀/寫許可權。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-187">Note that the user account that the SQL instance uses to run must have read/write permission to the file share.</span></span> <span data-ttu-id="dd4a5-188">如果檔案共用位於不同的伺服器上，且 SQL 實例執行的是本機系統帳戶，則您必須將檔案共用許可權授與託管 SQL 實例的伺服器。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-188">If the file share is on a different server, and the SQL instance runs a local system account, you must grant file share permissions to the server that hosts the SQL instance.</span></span>

3.  <span data-ttu-id="dd4a5-189">輸入 A，然後按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-189">Type A and press ENTER.</span></span>
    
    <span data-ttu-id="dd4a5-190">將會設定鏡像。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-190">The mirroring will be configured.</span></span>

<span data-ttu-id="dd4a5-191">**安裝-CsMirrorDatabase**會安裝鏡像，並針對主要 SQL 市集中存在的所有資料庫設定鏡像。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-191">**Install-CsMirrorDatabase** installs the mirror and configures mirroring for all the databases that are present on the primary SQL store.</span></span> <span data-ttu-id="dd4a5-192">如果您只想針對特定的資料庫設定鏡像，您可以使用– DatabaseType 選項，或者，如果您想要針對除幾個資料庫以外的所有資料庫設定鏡像，您可以使用-ExcludeDatabaseList 選項，以及逗號分隔的資料庫清單要排除的名稱。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-192">If you want to configure mirroring for only specific databases, you can use the –DatabaseType option, or if you want to configure mirroring for all databases except for a few, you can use the -ExcludeDatabaseList option, along with a comma-separated list of database names to exclude.</span></span>

<span data-ttu-id="dd4a5-193">例如，如果您將下列選項新增至**安裝-CsMirrorDatabase**，除了 rtcab 和 rtcxds 以外的所有資料庫都將會進行鏡像。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-193">For example, if you add the following option to **Install-CsMirrorDatabase**, all databases except rtcab and rtcxds will be mirrored.</span></span>

`-ExcludeDatabaseList rtcab,rtcxds`

<span data-ttu-id="dd4a5-194">例如，如果您將下列選項新增至**安裝-CsMirrorDatabase**，則只會鏡像 rtcab、rtcshared 和 rtcxds 資料庫。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-194">For example, if you add the following option to **Install-CsMirrorDatabase**, only the rtcab, rtcshared, and rtcxds databases will be mirrored.</span></span>

`-DatabaseType User`

</div>

<div>

## <a name="removing-or-changing-sql-mirroring"></a><span data-ttu-id="dd4a5-195">移除或變更 SQL 鏡像</span><span class="sxs-lookup"><span data-stu-id="dd4a5-195">Removing or Changing SQL Mirroring</span></span>

<span data-ttu-id="dd4a5-196">若要在拓撲建立器中移除池的 SQL 鏡像，您必須先使用 Cmdlet，才能在 SQL Server 中移除該鏡像。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-196">To remove the SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server.</span></span> <span data-ttu-id="dd4a5-197">然後，您就可以使用 [拓撲建立器] 從拓撲中移除鏡像。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-197">You can then use Topology Builder to remove the mirror from the topology.</span></span> <span data-ttu-id="dd4a5-198">若要在 SQL Server 中移除鏡像，請使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="dd4a5-198">To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="dd4a5-199">例如，若要移除鏡像並刪除使用者資料庫的資料庫，請輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="dd4a5-199">For example, to remove mirroring and drop the databases for the User databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="dd4a5-200">此`-DropExistingDatabasesOnMirror`選項會使受影響的資料庫從鏡像中刪除。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-200">The `-DropExistingDatabasesOnMirror` option causes the affected databases to be deleted from the mirror.</span></span>

<span data-ttu-id="dd4a5-201">接著，若要從拓撲中移除鏡像，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="dd4a5-201">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="dd4a5-202">在拓撲建立器中，以滑鼠右鍵按一下該池，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-202">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="dd4a5-203">取消核取 [**啟用 SQL Store 鏡像**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-203">Uncheck **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="dd4a5-204">發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-204">Publish the topology.</span></span>

</div>

<div>

## <a name="removing-a-mirroring-witness"></a><span data-ttu-id="dd4a5-205">移除鏡像見證</span><span class="sxs-lookup"><span data-stu-id="dd4a5-205">Removing a Mirroring Witness</span></span>

<span data-ttu-id="dd4a5-206">如果您需要從後端伺服器鏡像設定中移除見證，請使用此程式。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-206">Use this procedure if you need to remove the witness from a Back End Server mirroring configuration.</span></span>

1.  <span data-ttu-id="dd4a5-207">在拓撲建立器中，以滑鼠右鍵按一下該池，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-207">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="dd4a5-208">取消核取 **[使用 SQL Server 鏡像見證來啟用自動容錯移轉**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-208">Uncheck **Use SQL Server mirroring witness to enable automatic failover** and click **OK**.</span></span>

3.  <span data-ttu-id="dd4a5-209">發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-209">Publish the topology.</span></span>
    
    <span data-ttu-id="dd4a5-210">發佈拓撲之後，您會看到一則訊息，其中包含下列內容</span><span class="sxs-lookup"><span data-stu-id="dd4a5-210">After publishing the topology, Topology Builder you will see a message that includes the following</span></span>
    
        Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
    
    <span data-ttu-id="dd4a5-211">不過，請勿遵循該步驟，而且不要輸入`Uninstall-CsMirrorDatabase` ，否則就會卸載整個鏡像設定。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-211">However, do not follow that step, and do not type `Uninstall-CsMirrorDatabase` as that would uninstall the entire mirroring configuration.</span></span>

4.  <span data-ttu-id="dd4a5-212">若要只從 SQL Server 設定中移除見證，請依照「從資料庫鏡像會話中移除見證伺服器（SQL Server）」中的指示[http://go.microsoft.com/fwlink/p/?LinkId=268456](http://go.microsoft.com/fwlink/p/?linkid=268456)進行。</span><span class="sxs-lookup"><span data-stu-id="dd4a5-212">To remove just the witness from the SQL Server configuration, follow the instructions in "Remove the Witness from a Database Mirroring Session (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268456](http://go.microsoft.com/fwlink/p/?linkid=268456).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

