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
ms.openlocfilehash: 577d6bb312ae2b31f96fed5f3e5b02e84844adf6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-sql-mirroring-for-back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="f6c37-102">在 Lync Server 2013 中針對後端伺服器高可用性部署 SQL 鏡像</span><span class="sxs-lookup"><span data-stu-id="f6c37-102">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6c37-103">_**主題上次修改日期：** 2014-01-08_</span><span class="sxs-lookup"><span data-stu-id="f6c37-103">_**Topic Last Modified:** 2014-01-08_</span></span>

<span data-ttu-id="f6c37-104">若要得以部署 SQL 鏡像，您的伺服器至少必須執行 SQL Server 2008 R2。</span><span class="sxs-lookup"><span data-stu-id="f6c37-104">To be able to deploy SQL mirroring, your servers must run a minimum of SQL Server 2008 R2.</span></span> <span data-ttu-id="f6c37-105">此版本必須執行於以下所有相關伺服器：主要伺服器、鏡像伺服器、見證伺服器。</span><span class="sxs-lookup"><span data-stu-id="f6c37-105">This version must run on all the involved servers: the primary, mirror, and the witness.</span></span> <span data-ttu-id="f6c37-106">如需詳細資訊，請參閱 [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921) 。</span><span class="sxs-lookup"><span data-stu-id="f6c37-106">For details, see [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921).</span></span>

<span data-ttu-id="f6c37-107">一般而言，使用見證伺服器在兩個後端伺服器間設定 SQL 鏡像，需要下列各項：</span><span class="sxs-lookup"><span data-stu-id="f6c37-107">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>

  - <span data-ttu-id="f6c37-108">主要伺服器的 SQL Server 版本必須支援 SQL 鏡像。</span><span class="sxs-lookup"><span data-stu-id="f6c37-108">The primary server’s version of SQL Server must support SQL mirroring.</span></span>

  - <span data-ttu-id="f6c37-109">主要、鏡像與見證伺服器 (若已部署) 必須具有相同的 SQL Server 版本。</span><span class="sxs-lookup"><span data-stu-id="f6c37-109">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span>

  - <span data-ttu-id="f6c37-p102">主要與鏡像伺服器必須具有相同的 SQL Server 版本，見證伺服器可能有不同的版本。</span><span class="sxs-lookup"><span data-stu-id="f6c37-p102">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>

<span data-ttu-id="f6c37-112">如需有關見證角色支援哪些 SQL 版本的 SQL 最佳作法，請參閱 MSDN Library 中的「資料庫鏡像見證」 [https://go.microsoft.com/fwlink/p/?LinkId=247345](https://go.microsoft.com/fwlink/p/?linkid=247345) 。</span><span class="sxs-lookup"><span data-stu-id="f6c37-112">For SQL best practices in terms of what SQL versions are supported for a Witness role, see "Database Mirroring Witness" in the MSDN Library at [https://go.microsoft.com/fwlink/p/?LinkId=247345](https://go.microsoft.com/fwlink/p/?linkid=247345).</span></span>

<span data-ttu-id="f6c37-113">您可以使用拓撲產生器來部署 SQL 鏡像。</span><span class="sxs-lookup"><span data-stu-id="f6c37-113">You use Topology Builder to deploy SQL mirroring.</span></span> <span data-ttu-id="f6c37-114">您可以在 [拓撲產生器] 中選取一個選項，以鏡像資料庫，而拓撲產生器會設定鏡像 (包括設定見證，如果您想要在發行拓撲時) 。</span><span class="sxs-lookup"><span data-stu-id="f6c37-114">You select an option in Topology Builder to mirror the databases, and Topology Builder sets up the mirroring (including setting up a witness, if you want) when you publish the topology.</span></span> <span data-ttu-id="f6c37-115">請注意，設定或移除鏡像伺服器也會同時設定或移除見證伺服器。</span><span class="sxs-lookup"><span data-stu-id="f6c37-115">Note that you set up or remove the witness at the same time you set up or remove the mirror.</span></span> <span data-ttu-id="f6c37-116">僅部署或移除見證伺服器並無個別的命令。</span><span class="sxs-lookup"><span data-stu-id="f6c37-116">There is no separate command to deploy or remove only a witness.</span></span>

<span data-ttu-id="f6c37-117">若要設定伺服器鏡像，您必須先正確設定 SQL 資料庫權限。</span><span class="sxs-lookup"><span data-stu-id="f6c37-117">To configure server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="f6c37-118">如需詳細資訊，請參閱設定資料庫鏡像的登入帳戶或 AlwaysOn 可用性群組 (SQL Server) " [https://go.microsoft.com/fwlink/p/?LinkId=268454](https://go.microsoft.com/fwlink/p/?linkid=268454) 。</span><span class="sxs-lookup"><span data-stu-id="f6c37-118">For details, see "Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268454](https://go.microsoft.com/fwlink/p/?linkid=268454).</span></span>

<span data-ttu-id="f6c37-p105">有了 SQL 鏡像，資料庫復原模式會一律設為 **[完整]**，這表示您必須密切監控交易紀錄的大小並定期備份交易紀錄，以避免用盡後端伺服器上的磁碟機空間。交易記錄的備份頻率取決於記錄的成長率，即根據使用者在前端集區上活動所發生的資料庫交易。建議您針對 Lync 部署工作負載判斷交易記錄的預期成長率，以便進行相應的規劃。下列文章提供 SQL 備份以及記錄管理的其他資訊：</span><span class="sxs-lookup"><span data-stu-id="f6c37-p105">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers. The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool. We recommend that you determine how much transaction log growth is expected for your Lync deployment workload so that you can do the planning accordingly. The following articles provide additional information on SQL backup and log management:</span></span>

  - <span data-ttu-id="f6c37-123">資料庫復原模型： "Recovery 模型 (SQL Server) "，網址為[https://go.microsoft.com/fwlink/p/?LinkId=268446](https://go.microsoft.com/fwlink/p/?linkid=268446)</span><span class="sxs-lookup"><span data-stu-id="f6c37-123">Database recovery models: "Recovery Models (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268446](https://go.microsoft.com/fwlink/p/?linkid=268446)</span></span>

  - <span data-ttu-id="f6c37-124">備份概述：「備份概述 (SQL Server) "[https://go.microsoft.com/fwlink/p/?LinkId=268449](https://go.microsoft.com/fwlink/p/?linkid=268449)</span><span class="sxs-lookup"><span data-stu-id="f6c37-124">Backup overview: "Backup Overview (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268449](https://go.microsoft.com/fwlink/p/?linkid=268449)</span></span>

  - <span data-ttu-id="f6c37-125">備份交易記錄檔：「備份 SQL Server (的交易記錄檔) 」[https://go.microsoft.com/fwlink/p/?LinkId=268452](https://go.microsoft.com/fwlink/p/?linkid=268452)</span><span class="sxs-lookup"><span data-stu-id="f6c37-125">Backup transaction log: "Backup a Transaction Log (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268452](https://go.microsoft.com/fwlink/p/?linkid=268452)</span></span>

<span data-ttu-id="f6c37-126">有了 SQL 鏡像，您可在建立集區時或在建立集區後設定鏡像的拓撲。</span><span class="sxs-lookup"><span data-stu-id="f6c37-126">With SQL mirroring, you can either configure the topology for mirroring when you create the pools, or after the pools are already created.</span></span>



> [!IMPORTANT]
> <span data-ttu-id="f6c37-127">只有當主要、鏡像及)  (見證伺服器都屬於相同的網域時，才支援使用拓撲產生器或 Cmdlet 來設定及移除 SQL 鏡像。</span><span class="sxs-lookup"><span data-stu-id="f6c37-127">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="f6c37-128">若要在不同網域的伺服器間設定 SQL 鏡像，請參閱 SQL Server 文件。</span><span class="sxs-lookup"><span data-stu-id="f6c37-128">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span>





> [!IMPORTANT]
> <span data-ttu-id="f6c37-129">每當您變更為後端資料庫鏡像關係時，皆必須重新啟動集區中的前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="f6c37-129">Whenever you make a change to a Back End Database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span><BR><span data-ttu-id="f6c37-130">如需鏡像的變更， (例如變更鏡像) 的位置），您必須使用拓撲產生器來執行下列三個步驟：</span><span class="sxs-lookup"><span data-stu-id="f6c37-130">For a change in mirroring, (such as changing the location of a mirror), you must use Topology Builder to perform these three steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="f6c37-131">從舊鏡像伺服器移除鏡像。</span><span class="sxs-lookup"><span data-stu-id="f6c37-131">Remove mirroring from the old mirror server.</span></span></P>
> <LI>
> <P><span data-ttu-id="f6c37-132">將鏡像新增至新鏡像伺服器。</span><span class="sxs-lookup"><span data-stu-id="f6c37-132">Add mirroring to the new mirror server.</span></span></P>
> <LI>
> <P><span data-ttu-id="f6c37-133">發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="f6c37-133">Publish the topology.</span></span></P></LI></OL>




> [!NOTE]
> <span data-ttu-id="f6c37-134">必須針對要寫入的鏡像檔案建立檔案共用，而且執行 SQL Server 與 SQL 代理程式的服務必須具有讀取/寫入存取權。</span><span class="sxs-lookup"><span data-stu-id="f6c37-134">A file share has to be created for the mirror files to be written to, and the service that SQL Server and SQL Agent are running under needs read/write access.</span></span> <span data-ttu-id="f6c37-135">如果 SQL Server 服務是在 [網路服務] 內容下執行，您可以將 &lt; &gt; &lt; &gt; 主體和鏡像 SQL server 的網域&#92;SQLSERVERNAME $ 新增至 [共用] 許可權。</span><span class="sxs-lookup"><span data-stu-id="f6c37-135">If the SQL Server service is running under the context of Network Service, you can add &lt;Domain&gt;&#92;&lt;SQLSERVERNAME&gt;$ of both the Principal and Mirror SQL Servers to the share permissions.</span></span> <span data-ttu-id="f6c37-136">$ 對識別這是電腦帳戶很重要。</span><span class="sxs-lookup"><span data-stu-id="f6c37-136">The $ is important to identify that this is a computer account.</span></span>


<div>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a><span data-ttu-id="f6c37-137">在拓撲產生器中建立集區時設定 SQL 鏡像</span><span class="sxs-lookup"><span data-stu-id="f6c37-137">To configure SQL mirroring while creating a pool in Topology Builder</span></span>

1.  <span data-ttu-id="f6c37-138">在 **[定義 SQL 存放區]** 頁面上，按一下 **[SQL 存放區]** 方塊旁邊的 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="f6c37-138">On the **Define the SQL Store** page, click **New** next to the **SQL store** box.</span></span>

2.  <span data-ttu-id="f6c37-139">在 **[定義新的 SQL 存放區]** 頁面上，指定主要存放區，並選取 **[此 SQL 執行個體為鏡像關係]**，接著指定 SQL 鏡像連接埠號碼 (預設值為 5022)，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f6c37-139">On the **Define new SQL Store** page, specify the primary store, select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default is 5022), and then click **OK**.</span></span>

3.  <span data-ttu-id="f6c37-140">返回 **[定義 SQL 存放區]** 頁面，選取 **[啟用 SQL 存放區鏡像]**。</span><span class="sxs-lookup"><span data-stu-id="f6c37-140">Back on the **Define the SQL store** page, select **Enable SQL Store mirroring**.</span></span>

4.  <span data-ttu-id="f6c37-p108">在 **[定義新的 SQL 存放區]** 頁面中，指定要做為鏡像使用的 SQL 存放區。選取 **[此 SQL 執行個體為鏡像關係]**，指定連接埠號碼 (預設值為 5022)，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f6c37-p108">In the **Define new SQL Store** page, specify the SQL store to be used as the mirror. Select **This SQL instance is in mirroring relation**, specify the port number (the default is 5022), and then click **OK**.</span></span>

5.  <span data-ttu-id="f6c37-143">若您想要此鏡像的見證，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="f6c37-143">If you want a witness for this mirror, do the following:</span></span>
    
    1.  <span data-ttu-id="f6c37-144">選取 **[使用 SQL 鏡像見證啟用自動容錯移轉]**。</span><span class="sxs-lookup"><span data-stu-id="f6c37-144">Select **Use SQL mirroring witness to enable automatic failover**.</span></span>
    
    2.  <span data-ttu-id="f6c37-145">在 **[定義 SQL 存放區]** 頁面中，選取 **[使用 SQL 鏡像見證啟用自動容錯移轉]**，並指定 SQL 存放區做為見證使用。</span><span class="sxs-lookup"><span data-stu-id="f6c37-145">In the **Define the SQL Store** page, select **Use SQL mirroring witness to enable automatic failover**, and specify the SQL store to be used as the witness.</span></span>
    
    3.  <span data-ttu-id="f6c37-146">指定連接埠號碼 (預設值為 7022)，並按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f6c37-146">Specify the port number (the default is 7022) and click **OK**.</span></span>

6.  <span data-ttu-id="f6c37-147">在您完成定義您的前端集區和拓撲中的所有其他角色後，請使用拓撲產生器來發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="f6c37-147">After you are done defining your Front End pool and all other roles in your topology, use Topology Builder to publish the topology.</span></span> <span data-ttu-id="f6c37-148">當發佈拓撲時，如果主控中央管理存放區的前端集區已啟用 SQL 鏡像，您將會看到同時建立主要和鏡像 SQL 存放區資料庫的選項。</span><span class="sxs-lookup"><span data-stu-id="f6c37-148">When the topology is published, if the Front End pool that hosts Central Management store has SQL mirroring enabled, you will see an option to create both primary and mirror SQL store databases.</span></span>
    
    <span data-ttu-id="f6c37-149">按一下 **[設定]**，輸入做為鏡像備份檔案共用的路徑。</span><span class="sxs-lookup"><span data-stu-id="f6c37-149">Click **Settings**, and type the path to use as the file share for the mirroring backup.</span></span>
    
    <span data-ttu-id="f6c37-p110">依序按一下 **[確定]** 及 **[下一步]** 以建立資料庫和發行拓撲，即會部署鏡像與見證 (若已指定)。</span><span class="sxs-lookup"><span data-stu-id="f6c37-p110">Click **OK** and then **Next** to create the databases and publish the topology. The mirroring and the witness (if specified) will be deployed.</span></span>

<span data-ttu-id="f6c37-152">您可以使用拓撲產生器編輯現有集區的屬性，以啟用 SQL 鏡像。</span><span class="sxs-lookup"><span data-stu-id="f6c37-152">You can use Topology Builder to edit the properties of an already existing pool to enable SQL mirroring.</span></span>

</div>

<div>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a><span data-ttu-id="f6c37-153">在拓撲產生器中將 SQL 鏡像新增至現有前端集區</span><span class="sxs-lookup"><span data-stu-id="f6c37-153">To add SQL mirroring to an existing Front End pool in Topology Builder</span></span>

1.  <span data-ttu-id="f6c37-154">在 [拓撲產生器] 中，以滑鼠右鍵按一下集區，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="f6c37-154">In Topology Builder, right-click the pool and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="f6c37-155">選取 **[啟用 SQL 存放區鏡像]**，然後按一下 **[鏡像 SQL 存放區]** 旁邊的 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="f6c37-155">Select **Enable SQL Store Mirroring**, and then click **New** next to **Mirroring SQL Store**.</span></span>

3.  <span data-ttu-id="f6c37-156">指定您要做為鏡像使用的 SQL 存放區。</span><span class="sxs-lookup"><span data-stu-id="f6c37-156">Specify the SQL store that you want to use as the mirror.</span></span>

4.  <span data-ttu-id="f6c37-157">選取 **[此 SQL 執行個體為鏡像關係]**，指定 SQL 鏡像連接埠號碼 (預設值為 5022)，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f6c37-157">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number the default port is 5022), and then click **OK**.</span></span>

5.  <span data-ttu-id="f6c37-158">如果您要設定見證，請選取 **[使用 SQL 鏡像見證啟用自動容錯移轉]**，再按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="f6c37-158">If you want to configure a witness, select **Use SQL mirroring witness to enable automatic failover**, and click **New**.</span></span>

6.  <span data-ttu-id="f6c37-159">指定您要做為見證使用的 SQL 存放區。</span><span class="sxs-lookup"><span data-stu-id="f6c37-159">Specify the SQL store that you want to use as the witness.</span></span>

7.  <span data-ttu-id="f6c37-160">選取 **[此 SQL 執行個體為鏡像關係]**，指定 SQL 鏡像連接埠號碼 (預設值為 7022)，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f6c37-160">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default port is 7022), and then click **OK**.</span></span>

8.  <span data-ttu-id="f6c37-161">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f6c37-161">Click **OK**.</span></span>

9.  <span data-ttu-id="f6c37-p111">發行拓撲。執行此動作時，系統會提示您安裝資料庫。</span><span class="sxs-lookup"><span data-stu-id="f6c37-p111">Publish the topology. When you do so, you will be prompted to install the database.</span></span>
    
    <span data-ttu-id="f6c37-164">在拓撲發佈過程中，系統會要求您定義檔共用路徑。</span><span class="sxs-lookup"><span data-stu-id="f6c37-164">During the topology publishing process, you will be asked to define a file share path.</span></span> <span data-ttu-id="f6c37-165">參與鏡像的 SQL 伺服器必須具有此檔案共用的讀/寫存取權，才可建立鏡像。</span><span class="sxs-lookup"><span data-stu-id="f6c37-165">The SQL Servers that participate in the mirroring must have read/write access to this file share for the mirror to be established.</span></span>

<span data-ttu-id="f6c37-166">然後，您必須在進入下個程序前安裝資料庫。</span><span class="sxs-lookup"><span data-stu-id="f6c37-166">You must then install the database before going on to the next procedure.</span></span>

<span data-ttu-id="f6c37-167">在設定 SQL 鏡像時，請務必牢記下列事項：</span><span class="sxs-lookup"><span data-stu-id="f6c37-167">You should keep the following in mind when setting up SQL mirroring:</span></span>

  - <span data-ttu-id="f6c37-168">如果已存在鏡像端點，將會以定義的連接埠加以重複使用，而且會略過在拓撲中指定的其他連接埠。</span><span class="sxs-lookup"><span data-stu-id="f6c37-168">If a mirroring endpoint already exists, it will be reused using the ports defined there, and will ignore the ones you specify in the topology.</span></span>

  - <span data-ttu-id="f6c37-p113">在相同伺服器上為其他應用程式配置的連接埠 (包含為其他 SQL 執行個體配置的)，均不應用於隨時可取用的已安裝 SQL 執行個體。這表示，如果您有一個以上的 SQL 執行個體安裝於相同的伺服器上，不得使用相同的連接埠進行鏡像處理。如需詳細資訊，請參閱以下文章：</span><span class="sxs-lookup"><span data-stu-id="f6c37-p113">Any port already allocated for other applications on the same server, including those for other SQL instances, should not be used for the installed SQL instances at hand. This implies that if you have more than one SQL instance installed on the same server, they must not use the same port for mirroring. For details, see the following articles:</span></span>
    
      - <span data-ttu-id="f6c37-172">在 MSDN Library 中的「指定伺服器網路位址 (資料庫鏡像) 」[https://go.microsoft.com/fwlink/p/?LinkId=247346](https://go.microsoft.com/fwlink/p/?linkid=247346)</span><span class="sxs-lookup"><span data-stu-id="f6c37-172">"Specify a Server Network Address (Database Mirroring)" in the MSDN Library at [https://go.microsoft.com/fwlink/p/?LinkId=247346](https://go.microsoft.com/fwlink/p/?linkid=247346)</span></span>
    
      - <span data-ttu-id="f6c37-173">「資料庫鏡像端點 (SQL Server) "[https://go.microsoft.com/fwlink/p/?LinkId=247347](https://go.microsoft.com/fwlink/p/?linkid=247347)</span><span class="sxs-lookup"><span data-stu-id="f6c37-173">"The Database Mirroring Endpoint (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=247347](https://go.microsoft.com/fwlink/p/?linkid=247347)</span></span>

</div>

<div>

## <a name="using-lync-server-management-shell-cmdlets-to-set-up-sql-mirroring"></a><span data-ttu-id="f6c37-174">使用 Lync Server 管理命令介面 Cmdlet 設定 SQL 鏡像</span><span class="sxs-lookup"><span data-stu-id="f6c37-174">Using Lync Server Management Shell Cmdlets to Set Up SQL Mirroring</span></span>

<span data-ttu-id="f6c37-175">設定鏡像最簡單的方法是使用拓撲產生器，但您也可以使用 Cmdlet 來執行。</span><span class="sxs-lookup"><span data-stu-id="f6c37-175">The easiest way to set up mirroring is by using Topology Builder, but you can also do so using cmdlets.</span></span>

1.  <span data-ttu-id="f6c37-176">開啟 Lync Server 管理命令介面視窗，並執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="f6c37-176">Open a Lync Server Management Shell window and run the following cmdlet:</span></span>
    
        Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose 
    
    <span data-ttu-id="f6c37-177">例如：</span><span class="sxs-lookup"><span data-stu-id="f6c37-177">For example:</span></span>
    
        Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose 
    
    <span data-ttu-id="f6c37-178">您會看到下列訊息：</span><span class="sxs-lookup"><span data-stu-id="f6c37-178">You will see the following:</span></span>
    
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

2.  <span data-ttu-id="f6c37-179">請確認下列各項：</span><span class="sxs-lookup"><span data-stu-id="f6c37-179">Verify the following:</span></span>
    
      - <span data-ttu-id="f6c37-180">如果在主要 SQL Server e04-ocs 中啟用 Windows 防火牆，則可以透過防火牆存取埠5022。 \_ lsipt 本機 \\ rtc。</span><span class="sxs-lookup"><span data-stu-id="f6c37-180">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the primary SQL Server e04-ocs.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="f6c37-181">如果已在鏡像 SQL Server K16-ocs 中啟用 Windows 防火牆，則可以透過防火牆存取埠5022。 \_ lsipt 本機 \\ rtc。</span><span class="sxs-lookup"><span data-stu-id="f6c37-181">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the mirror SQL Server K16-ocs.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="f6c37-182">如果在見證 SQL Server AB14-lct 中啟用 Windows 防火牆，則可以透過防火牆存取埠7022。 \_ lsipt 本機 \\ rtc。</span><span class="sxs-lookup"><span data-stu-id="f6c37-182">Port 7022 is accessible through the firewall if Windows Firewall is enabled in the witness SQL Server AB14-lct.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="f6c37-183">在所有主要和鏡像 SQL server 上執行 SQL Server 的帳戶都具有檔案共用 E04 的讀取/寫入權限 \\ \\ -OCS \\ csdatabackup</span><span class="sxs-lookup"><span data-stu-id="f6c37-183">Accounts running the SQL Servers on all primary and mirror SQL servers have read/write permission to the file share \\\\E04-OCS\\csdatabackup</span></span>
    
      - <span data-ttu-id="f6c37-p114">確認 Windows Management Instrumentation (WMI) 提供者正執行於所有伺服器上。Cmdlet 會使用此提供者尋找執行於所有主要、鏡像及見證伺服器的 SQL Server 服務帳戶資訊。</span><span class="sxs-lookup"><span data-stu-id="f6c37-p114">Verify that the Windows Management Instrumentation (WMI) provider is running on all these servers. The cmdlet uses this provider to find the account information for SQL Server services running on all primary, mirror and witness servers.</span></span>
    
      - <span data-ttu-id="f6c37-186">確認執行此 Cmdlet 的帳戶具有權限，可為所有鏡像伺服器建立資料與記錄檔的資料夾。</span><span class="sxs-lookup"><span data-stu-id="f6c37-186">Verify that the account running this cmdlet has permission to create the folders for the data and log files for all the mirror servers.</span></span>
    
      - <span data-ttu-id="f6c37-p115">請注意，SQL 執行個體用以執行的使用者帳戶必須具有檔案共用的讀取/寫入權限。如果檔案共用在其他的伺服器上，而且 SQL 執行個體執行本機系統帳戶，您必須將檔案共用權限授與託管 SQL 執行個體的伺服器。</span><span class="sxs-lookup"><span data-stu-id="f6c37-p115">Note that the user account that the SQL instance uses to run must have read/write permission to the file share. If the file share is on a different server, and the SQL instance runs a local system account, you must grant file share permissions to the server that hosts the SQL instance.</span></span>

3.  <span data-ttu-id="f6c37-189">輸入 A 並按 ENTER 鍵。</span><span class="sxs-lookup"><span data-stu-id="f6c37-189">Type A and press ENTER.</span></span>
    
    <span data-ttu-id="f6c37-190">即會設定鏡像。</span><span class="sxs-lookup"><span data-stu-id="f6c37-190">The mirroring will be configured.</span></span>

<span data-ttu-id="f6c37-191">**Install-CsMirrorDatabase** 會安裝鏡像伺服器，並設定位於主要 SQL 存放區所有資料庫的鏡像。</span><span class="sxs-lookup"><span data-stu-id="f6c37-191">**Install-CsMirrorDatabase** installs the mirror and configures mirroring for all the databases that are present on the primary SQL store.</span></span> <span data-ttu-id="f6c37-192">如果您只想要設定指定資料庫的鏡像，可使用 DatabaseType 選項；或是，如果您想要設定所有 (但部分除外) 資料庫的鏡像，則可使用 ExcludeDatabaseList 選項，並搭配資料庫名稱以逗號分隔的清單加以排除。</span><span class="sxs-lookup"><span data-stu-id="f6c37-192">If you want to configure mirroring for only specific databases, you can use the –DatabaseType option, or if you want to configure mirroring for all databases except for a few, you can use the -ExcludeDatabaseList option, along with a comma-separated list of database names to exclude.</span></span>

<span data-ttu-id="f6c37-193">例如，如果您將下列選項新增至 **Install-CsMirrorDatabase**，所有資料庫即會作鏡像處理，Rtcab 和 Rtcxds 除外。</span><span class="sxs-lookup"><span data-stu-id="f6c37-193">For example, if you add the following option to **Install-CsMirrorDatabase**, all databases except rtcab and rtcxds will be mirrored.</span></span>

`-ExcludeDatabaseList rtcab,rtcxds`

<span data-ttu-id="f6c37-194">例如，如果您將下列選項新增至 **Install-CsMirrorDatabase**，則只有 Rtcab、Rtcshared 及 Rtcxds 資料庫會作鏡像處理。</span><span class="sxs-lookup"><span data-stu-id="f6c37-194">For example, if you add the following option to **Install-CsMirrorDatabase**, only the rtcab, rtcshared, and rtcxds databases will be mirrored.</span></span>

`-DatabaseType User`

</div>

<div>

## <a name="removing-or-changing-sql-mirroring"></a><span data-ttu-id="f6c37-195">移除或變更 SQL 鏡像</span><span class="sxs-lookup"><span data-stu-id="f6c37-195">Removing or Changing SQL Mirroring</span></span>

<span data-ttu-id="f6c37-p117">若要在拓撲產生器中移除集區的 SQL 鏡像，您必須先使用 Cmdlet 將 SQL Server 中的鏡像移除，然後，您可使用拓撲產生器從拓撲移除鏡像。若要移除 SQL Server 中的鏡像，請使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="f6c37-p117">To remove the SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server. You can then use Topology Builder to remove the mirror from the topology. To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="f6c37-199">例如，若要移除鏡像並捨棄使用者資料庫的資料庫，請輸入：</span><span class="sxs-lookup"><span data-stu-id="f6c37-199">For example, to remove mirroring and drop the databases for the User databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="f6c37-200">此 `-DropExistingDatabasesOnMirror` 選項會從鏡像中刪除受影響的資料庫。</span><span class="sxs-lookup"><span data-stu-id="f6c37-200">The `-DropExistingDatabasesOnMirror` option causes the affected databases to be deleted from the mirror.</span></span>

<span data-ttu-id="f6c37-201">此外，若要從拓撲移除鏡像伺服器，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="f6c37-201">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="f6c37-202">在拓撲產生器中，以滑鼠右鍵按一下集區，再按一下 **[編輯內容]**。</span><span class="sxs-lookup"><span data-stu-id="f6c37-202">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="f6c37-203">取消核取 **[啟用 SQL 存放區鏡像]** 並按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f6c37-203">Uncheck **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="f6c37-204">發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="f6c37-204">Publish the topology.</span></span>

</div>

<div>

## <a name="removing-a-mirroring-witness"></a><span data-ttu-id="f6c37-205">移除鏡像見證</span><span class="sxs-lookup"><span data-stu-id="f6c37-205">Removing a Mirroring Witness</span></span>

<span data-ttu-id="f6c37-206">如果您需要從後端伺服器鏡像設定中移除見證，請使用此程式。</span><span class="sxs-lookup"><span data-stu-id="f6c37-206">Use this procedure if you need to remove the witness from a Back End Server mirroring configuration.</span></span>

1.  <span data-ttu-id="f6c37-207">在拓撲產生器中，以滑鼠右鍵按一下集區，再按一下 **[編輯內容]**。</span><span class="sxs-lookup"><span data-stu-id="f6c37-207">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="f6c37-208">取消核取 **[使用 SQL Server 鏡像見證啟用自動容錯移轉]**，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f6c37-208">Uncheck **Use SQL Server mirroring witness to enable automatic failover** and click **OK**.</span></span>

3.  <span data-ttu-id="f6c37-209">發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="f6c37-209">Publish the topology.</span></span>
    
    <span data-ttu-id="f6c37-210">發行拓撲之後，拓撲產生器會顯示一則訊息，其中包含下列各項：</span><span class="sxs-lookup"><span data-stu-id="f6c37-210">After publishing the topology, Topology Builder you will see a message that includes the following</span></span>
    
        Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
    
    <span data-ttu-id="f6c37-211">不過，請不要執行該步驟，也不要像那樣輸入 `Uninstall-CsMirrorDatabase` ，否則會卸載整個鏡像設定。</span><span class="sxs-lookup"><span data-stu-id="f6c37-211">However, do not follow that step, and do not type `Uninstall-CsMirrorDatabase` as that would uninstall the entire mirroring configuration.</span></span>

4.  <span data-ttu-id="f6c37-212">若要從 SQL Server 設定中只移除見證，請依照「從資料庫鏡像會話移除見證 (SQL Server) 」中的指示進行 [https://go.microsoft.com/fwlink/p/?LinkId=268456](https://go.microsoft.com/fwlink/p/?linkid=268456) 。</span><span class="sxs-lookup"><span data-stu-id="f6c37-212">To remove just the witness from the SQL Server configuration, follow the instructions in "Remove the Witness from a Database Mirroring Session (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268456](https://go.microsoft.com/fwlink/p/?linkid=268456).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

