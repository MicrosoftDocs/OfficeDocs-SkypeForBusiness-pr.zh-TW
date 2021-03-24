---
title: 為商務用 Skype Server 2015 中的後端伺服器高可用性部署 SQL 鏡像
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
description: 若要得以部署 SQL 鏡像，您的伺服器至少必須執行 SQL Server 2008 R2。 此版本必須執行於以下所有相關伺服器：主要伺服器、鏡像伺服器、見證伺服器。 如需詳細資訊，請參閱累積更新套件9（適用于 SQL Server 2008 Service Pack 1）。
ms.openlocfilehash: 38c3e749b39cd510623232e9f29ace03a1c19f6c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100719"
---
# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a><span data-ttu-id="d169f-105">為商務用 Skype server 2015 中的後端伺服器高可用性部署 SQL 鏡像</span><span class="sxs-lookup"><span data-stu-id="d169f-105">Deploy SQL mirroring for Back End Server high availability in Skype for Business server 2015</span></span>


<span data-ttu-id="d169f-106">若要得以部署 SQL 鏡像，您的伺服器至少必須執行 SQL Server 2008 R2。</span><span class="sxs-lookup"><span data-stu-id="d169f-106">To be able to deploy SQL mirroring, your servers must run a minimum of SQL Server 2008 R2.</span></span> <span data-ttu-id="d169f-107">此版本必須執行於以下所有相關伺服器：主要伺服器、鏡像伺服器、見證伺服器。</span><span class="sxs-lookup"><span data-stu-id="d169f-107">This version must run on all the involved servers: the primary, mirror, and the witness.</span></span> <span data-ttu-id="d169f-108">如需詳細資訊，請參閱 [累積更新套件9（適用于 SQL Server 2008 Service Pack 1](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921)）。</span><span class="sxs-lookup"><span data-stu-id="d169f-108">For details, see [Cumulative update package 9 for SQL Server 2008 Service Pack 1](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).</span></span>

<span data-ttu-id="d169f-109">一般而言，使用見證伺服器在兩個後端伺服器間設定 SQL 鏡像，需要下列各項：</span><span class="sxs-lookup"><span data-stu-id="d169f-109">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>

- <span data-ttu-id="d169f-110">主伺服器的 SQL Server 版本必須支援 SQL 鏡像。</span><span class="sxs-lookup"><span data-stu-id="d169f-110">The primary server's version of SQL Server must support SQL mirroring.</span></span>

- <span data-ttu-id="d169f-111">主要、鏡像與見證伺服器 (若已部署) 必須具有相同的 SQL Server 版本。</span><span class="sxs-lookup"><span data-stu-id="d169f-111">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span>

- <span data-ttu-id="d169f-p103">主要與鏡像伺服器必須具有相同的 SQL Server 版本，見證伺服器可能有不同的版本。</span><span class="sxs-lookup"><span data-stu-id="d169f-p103">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>

<span data-ttu-id="d169f-114">如需有關見證角色支援哪些 SQL 版本的 SQL 最佳作法，請參閱 [資料庫鏡像見證](/sql/database-engine/database-mirroring/database-mirroring-witness)。</span><span class="sxs-lookup"><span data-stu-id="d169f-114">For SQL best practices in terms of what SQL versions are supported for a Witness role, see [Database Mirroring Witness](/sql/database-engine/database-mirroring/database-mirroring-witness).</span></span>

<span data-ttu-id="d169f-115">您可以使用拓撲產生器來部署 SQL 鏡像。</span><span class="sxs-lookup"><span data-stu-id="d169f-115">You use Topology Builder to deploy SQL mirroring.</span></span> <span data-ttu-id="d169f-116">您可以在 [拓撲產生器] 中選取一個選項，以鏡像資料庫，而拓撲產生器會設定鏡像 (包括設定見證，如果您想要在發行拓撲時) 。</span><span class="sxs-lookup"><span data-stu-id="d169f-116">You select an option in Topology Builder to mirror the databases, and Topology Builder sets up the mirroring (including setting up a witness, if you want) when you publish the topology.</span></span> <span data-ttu-id="d169f-117">請注意，設定或移除鏡像伺服器也會同時設定或移除見證伺服器。</span><span class="sxs-lookup"><span data-stu-id="d169f-117">Note that you set up or remove the witness at the same time you set up or remove the mirror.</span></span> <span data-ttu-id="d169f-118">僅部署或移除見證伺服器並無個別的命令。</span><span class="sxs-lookup"><span data-stu-id="d169f-118">There is no separate command to deploy or remove only a witness.</span></span>

<span data-ttu-id="d169f-119">若要設定伺服器鏡像，您必須先正確設定 SQL 資料庫權限。</span><span class="sxs-lookup"><span data-stu-id="d169f-119">To configure server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="d169f-120">如需詳細資訊，請參閱 [設定資料庫鏡像的登入帳戶或 AlwaysOn 可用性群組 (SQL Server) ](/sql/database-engine/database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability)。</span><span class="sxs-lookup"><span data-stu-id="d169f-120">For details, see [Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)](/sql/database-engine/database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability).</span></span>

<span data-ttu-id="d169f-121">有了 SQL 鏡像，資料庫復原模式會一律設為 **[完整]**，這表示您必須密切監控交易紀錄的大小並定期備份交易紀錄，以避免用盡後端伺服器上的磁碟機空間。</span><span class="sxs-lookup"><span data-stu-id="d169f-121">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers.</span></span> <span data-ttu-id="d169f-122">交易記錄的備份頻率取決於記錄的成長率，即根據使用者在前端集區上活動所發生的資料庫交易。</span><span class="sxs-lookup"><span data-stu-id="d169f-122">The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool.</span></span> <span data-ttu-id="d169f-123">建議您決定部署工作負載預期的交易記錄檔成長程度，以便據此進行規劃。</span><span class="sxs-lookup"><span data-stu-id="d169f-123">We recommend that you determine how much transaction log growth is expected for your deployment workload so that you can do the planning accordingly.</span></span> <span data-ttu-id="d169f-124">下列文章提供 SQL 備份以及記錄管理的其他資訊：</span><span class="sxs-lookup"><span data-stu-id="d169f-124">The following articles provide additional information on SQL backup and log management:</span></span>

- [<span data-ttu-id="d169f-125">資料庫恢復模型</span><span class="sxs-lookup"><span data-stu-id="d169f-125">Database recovery models</span></span>](/sql/relational-databases/backup-restore/recovery-models-sql-server)

- [<span data-ttu-id="d169f-126">備份概述</span><span class="sxs-lookup"><span data-stu-id="d169f-126">Backup overview</span></span>](/sql/relational-databases/backup-restore/backup-overview-sql-server)

- [<span data-ttu-id="d169f-127">備份交易記錄檔</span><span class="sxs-lookup"><span data-stu-id="d169f-127">Backup transaction log</span></span>](/sql/relational-databases/backup-restore/back-up-a-transaction-log-sql-server)

<span data-ttu-id="d169f-128">有了 SQL 鏡像，您可在建立集區時或在建立集區後設定鏡像的拓撲。</span><span class="sxs-lookup"><span data-stu-id="d169f-128">With SQL mirroring, you can either configure the topology for mirroring when you create the pools, or after the pools are already created.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d169f-129">只有當主要、鏡像及)  (見證伺服器都屬於相同的網域時，才支援使用拓撲產生器或 Cmdlet 來設定及移除 SQL 鏡像。</span><span class="sxs-lookup"><span data-stu-id="d169f-129">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="d169f-130">若要在不同網域的伺服器間設定 SQL 鏡像，請參閱 SQL Server 文件。</span><span class="sxs-lookup"><span data-stu-id="d169f-130">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d169f-131">每當您變更為後端資料庫鏡像關係時，皆必須重新啟動集區中的前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="d169f-131">Whenever you make a change to a Back End Database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span> <span data-ttu-id="d169f-132">> 若要變更鏡像的變更， (例如變更鏡像) 的位置），您必須使用拓撲產生器來執行下列三個步驟：</span><span class="sxs-lookup"><span data-stu-id="d169f-132">> For a change in mirroring, (such as changing the location of a mirror), you must use Topology Builder to perform these three steps:</span></span>

1. <span data-ttu-id="d169f-133">從舊鏡像伺服器移除鏡像。</span><span class="sxs-lookup"><span data-stu-id="d169f-133">Remove mirroring from the old mirror server.</span></span>

2. <span data-ttu-id="d169f-134">將鏡像新增至新鏡像伺服器。</span><span class="sxs-lookup"><span data-stu-id="d169f-134">Add mirroring to the new mirror server.</span></span>

3. <span data-ttu-id="d169f-135">發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="d169f-135">Publish the topology.</span></span>

> [!NOTE]
> <span data-ttu-id="d169f-136">必須針對要寫入的鏡像檔案建立檔案共用，而且執行 SQL Server 與 SQL 代理程式的服務必須具有讀取/寫入存取權。</span><span class="sxs-lookup"><span data-stu-id="d169f-136">A file share has to be created for the mirror files to be written to, and the service that SQL Server and SQL Agent are running under needs read/write access.</span></span> <span data-ttu-id="d169f-137">如果 SQL Server 服務是在 [網路服務] 內容下執行，您可以將 \<Domain\> \\ \> 主體伺服器和鏡像 SQL SERVER 的<SQLSERVERNAME $ 新增至 [共用] 許可權。</span><span class="sxs-lookup"><span data-stu-id="d169f-137">If the SQL Server service is running under the context of Network Service, you can add \<Domain\>\\<SQLSERVERNAME\>$ of both the Principal and Mirror SQL Servers to the share permissions.</span></span> <span data-ttu-id="d169f-138">$ 對識別這是電腦帳戶很重要。</span><span class="sxs-lookup"><span data-stu-id="d169f-138">The $ is important to identify that this is a computer account.</span></span>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a><span data-ttu-id="d169f-139">在拓撲產生器中建立集區時設定 SQL 鏡像</span><span class="sxs-lookup"><span data-stu-id="d169f-139">To configure SQL mirroring while creating a pool in Topology Builder</span></span>

1. <span data-ttu-id="d169f-140">在 **[定義 SQL 存放區]** 頁面上，按一下 **[SQL 存放區]** 方塊旁邊的 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="d169f-140">On the **Define the SQL Store** page, click **New** next to the **SQL store** box.</span></span>

2. <span data-ttu-id="d169f-141">在 **[定義新的 SQL 存放區]** 頁面上，指定主要存放區，並選取 **[此 SQL 執行個體為鏡像關係]**，接著指定 SQL 鏡像連接埠號碼 (預設值為 5022)，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d169f-141">On the **Define new SQL Store** page, specify the primary store, select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default is 5022), and then click **OK**.</span></span>

3. <span data-ttu-id="d169f-142">返回 **[定義 SQL 存放區]** 頁面，選取 **[啟用 SQL 存放區鏡像]**。</span><span class="sxs-lookup"><span data-stu-id="d169f-142">Back on the **Define the SQL store** page, select **Enable SQL Store mirroring**.</span></span>

4. <span data-ttu-id="d169f-p110">在 **[定義新的 SQL 存放區]** 頁面中，指定要做為鏡像使用的 SQL 存放區。選取 **[此 SQL 執行個體為鏡像關係]**，指定連接埠號碼 (預設值為 5022)，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d169f-p110">In the **Define new SQL Store** page, specify the SQL store to be used as the mirror. Select **This SQL instance is in mirroring relation**, specify the port number (the default is 5022), and then click **OK**.</span></span>

5. <span data-ttu-id="d169f-145">若您想要此鏡像的見證，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="d169f-145">If you want a witness for this mirror, do the following:</span></span>

    <span data-ttu-id="d169f-146">a.</span><span class="sxs-lookup"><span data-stu-id="d169f-146">a.</span></span> <span data-ttu-id="d169f-147">選取 **[使用 SQL 鏡像見證啟用自動容錯移轉]**。</span><span class="sxs-lookup"><span data-stu-id="d169f-147">Select **Use SQL mirroring witness to enable automatic failover**.</span></span>

    <span data-ttu-id="d169f-148">b.</span><span class="sxs-lookup"><span data-stu-id="d169f-148">b.</span></span> <span data-ttu-id="d169f-149">在 **[定義 SQL 存放區]** 頁面中，選取 **[使用 SQL 鏡像見證啟用自動容錯移轉]**，並指定 SQL 存放區做為見證使用。</span><span class="sxs-lookup"><span data-stu-id="d169f-149">In the **Define the SQL Store** page, select **Use SQL mirroring witness to enable automatic failover**, and specify the SQL store to be used as the witness.</span></span>

    <span data-ttu-id="d169f-150">c.</span><span class="sxs-lookup"><span data-stu-id="d169f-150">c.</span></span> <span data-ttu-id="d169f-151">指定連接埠號碼 (預設值為 7022)，並按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d169f-151">Specify the port number (the default is 7022) and click **OK**.</span></span>

6. <span data-ttu-id="d169f-152">在您完成定義您的前端集區和拓撲中的所有其他角色後，請使用拓撲產生器來發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="d169f-152">After you are done defining your Front End pool and all other roles in your topology, use Topology Builder to publish the topology.</span></span> <span data-ttu-id="d169f-153">當發佈拓撲時，如果主控中央管理存放區的前端集區已啟用 SQL 鏡像，您將會看到同時建立主要和鏡像 SQL 存放區資料庫的選項。</span><span class="sxs-lookup"><span data-stu-id="d169f-153">When the topology is published, if the Front End pool that hosts Central Management store has SQL mirroring enabled, you will see an option to create both primary and mirror SQL store databases.</span></span>

    <span data-ttu-id="d169f-154">按一下 **[設定]**，輸入做為鏡像備份檔案共用的路徑。</span><span class="sxs-lookup"><span data-stu-id="d169f-154">Click **Settings**, and type the path to use as the file share for the mirroring backup.</span></span>

    <span data-ttu-id="d169f-p115">依序按一下 **[確定]** 及 **[下一步]** 以建立資料庫和發行拓撲，即會部署鏡像與見證 (若已指定)。</span><span class="sxs-lookup"><span data-stu-id="d169f-p115">Click **OK** and then **Next** to create the databases and publish the topology. The mirroring and the witness (if specified) will be deployed.</span></span>

<span data-ttu-id="d169f-157">您可以使用拓撲產生器編輯現有集區的屬性，以啟用 SQL 鏡像。</span><span class="sxs-lookup"><span data-stu-id="d169f-157">You can use Topology Builder to edit the properties of an already existing pool to enable SQL mirroring.</span></span>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a><span data-ttu-id="d169f-158">在拓撲產生器中將 SQL 鏡像新增至現有前端集區</span><span class="sxs-lookup"><span data-stu-id="d169f-158">To add SQL mirroring to an existing Front End pool in Topology Builder</span></span>

1. <span data-ttu-id="d169f-159">在 [拓撲產生器] 中，以滑鼠右鍵按一下集區，然後按一下 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="d169f-159">In Topology Builder, right-click the pool and then click **Edit Properties**.</span></span>

2. <span data-ttu-id="d169f-160">選取 **[啟用 SQL 存放區鏡像]**，然後按一下 **[鏡像 SQL 存放區]** 旁邊的 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="d169f-160">Select **Enable SQL Store Mirroring**, and then click **New** next to **Mirroring SQL Store**.</span></span>

3. <span data-ttu-id="d169f-161">指定您要做為鏡像使用的 SQL 存放區。</span><span class="sxs-lookup"><span data-stu-id="d169f-161">Specify the SQL store that you want to use as the mirror.</span></span>

4. <span data-ttu-id="d169f-162">選取 **[此 SQL 執行個體為鏡像關係]**，指定 SQL 鏡像連接埠號碼 (預設值為 5022)，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d169f-162">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number the default port is 5022), and then click **OK**.</span></span>

5. <span data-ttu-id="d169f-163">如果您要設定見證，請選取 **[使用 SQL 鏡像見證啟用自動容錯移轉]**，再按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="d169f-163">If you want to configure a witness, select **Use SQL mirroring witness to enable automatic failover**, and click **New**.</span></span>

6. <span data-ttu-id="d169f-164">指定您要做為見證使用的 SQL 存放區。</span><span class="sxs-lookup"><span data-stu-id="d169f-164">Specify the SQL store that you want to use as the witness.</span></span>

7. <span data-ttu-id="d169f-165">選取 **[此 SQL 執行個體為鏡像關係]**，指定 SQL 鏡像連接埠號碼 (預設值為 7022)，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d169f-165">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default port is 7022), and then click **OK**.</span></span>

8. <span data-ttu-id="d169f-166">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d169f-166">Click **OK**.</span></span>

9. <span data-ttu-id="d169f-p116">發行拓撲。執行此動作時，系統會提示您安裝資料庫。</span><span class="sxs-lookup"><span data-stu-id="d169f-p116">Publish the topology. When you do so, you will be prompted to install the database.</span></span>

    <span data-ttu-id="d169f-169">在拓撲發佈過程中，系統會要求您定義檔共用路徑。</span><span class="sxs-lookup"><span data-stu-id="d169f-169">During the topology publishing process, you will be asked to define a file share path.</span></span> <span data-ttu-id="d169f-170">參與鏡像的 SQL 伺服器必須具有此檔案共用的讀/寫存取權，才可建立鏡像。</span><span class="sxs-lookup"><span data-stu-id="d169f-170">The SQL Servers that participate in the mirroring must have read/write access to this file share for the mirror to be established.</span></span>

<span data-ttu-id="d169f-171">然後，您必須在進入下個程序前安裝資料庫。</span><span class="sxs-lookup"><span data-stu-id="d169f-171">You must then install the database before going on to the next procedure.</span></span>

<span data-ttu-id="d169f-172">在設定 SQL 鏡像時，請務必牢記下列事項：</span><span class="sxs-lookup"><span data-stu-id="d169f-172">You should keep the following in mind when setting up SQL mirroring:</span></span>

- <span data-ttu-id="d169f-173">如果已存在鏡像端點，將會以定義的連接埠加以重複使用，而且會略過在拓撲中指定的其他連接埠。</span><span class="sxs-lookup"><span data-stu-id="d169f-173">If a mirroring endpoint already exists, it will be reused using the ports defined there, and will ignore the ones you specify in the topology.</span></span>

- <span data-ttu-id="d169f-p118">在相同伺服器上為其他應用程式配置的連接埠 (包含為其他 SQL 執行個體配置的)，均不應用於隨時可取用的已安裝 SQL 執行個體。這表示，如果您有一個以上的 SQL 執行個體安裝於相同的伺服器上，不得使用相同的連接埠進行鏡像處理。如需詳細資訊，請參閱以下文章：</span><span class="sxs-lookup"><span data-stu-id="d169f-p118">Any port already allocated for other applications on the same server, including those for other SQL instances, should not be used for the installed SQL instances at hand. This implies that if you have more than one SQL instance installed on the same server, they must not use the same port for mirroring. For details, see the following articles:</span></span>

  - [<span data-ttu-id="d169f-177">指定伺服器網路位址 (資料庫鏡像) </span><span class="sxs-lookup"><span data-stu-id="d169f-177">Specify a Server Network Address (Database Mirroring)</span></span>](/sql/database-engine/database-mirroring/specify-a-server-network-address-database-mirroring)

  - [<span data-ttu-id="d169f-178">資料庫鏡像端點 (SQL Server) </span><span class="sxs-lookup"><span data-stu-id="d169f-178">The Database Mirroring Endpoint (SQL Server)</span></span>](/sql/database-engine/database-mirroring/the-database-mirroring-endpoint-sql-server)

## <a name="using-skype-for-business-server-2015-management-shell-cmdlets-to-set-up-sql-mirroring"></a><span data-ttu-id="d169f-179">使用商務用 Skype Server 2015 管理命令介面 Cmdlet 來設定 SQL 鏡像</span><span class="sxs-lookup"><span data-stu-id="d169f-179">Using Skype for Business Server 2015 Management Shell Cmdlets to Set Up SQL Mirroring</span></span>

<span data-ttu-id="d169f-180">設定鏡像最簡單的方法是使用拓撲產生器，但您也可以使用 Cmdlet 來執行。</span><span class="sxs-lookup"><span data-stu-id="d169f-180">The easiest way to set up mirroring is by using Topology Builder, but you can also do so using cmdlets.</span></span>

1. <span data-ttu-id="d169f-181">開啟商務用 Skype Server 2015 管理命令介面視窗，並執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="d169f-181">Open a Skype for Business Server 2015 Management Shell window and run the following cmdlet:</span></span>

   ```powershell
   Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose
   ```

    <span data-ttu-id="d169f-182">例如：</span><span class="sxs-lookup"><span data-stu-id="d169f-182">For example:</span></span>

   ```powershell
   Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose
   ```

    <span data-ttu-id="d169f-183">您會看到下列訊息：</span><span class="sxs-lookup"><span data-stu-id="d169f-183">You will see the following:</span></span>

   <pre>
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
   </pre>

2. <span data-ttu-id="d169f-184">請確認下列各項：</span><span class="sxs-lookup"><span data-stu-id="d169f-184">Verify the following:</span></span>

    - <span data-ttu-id="d169f-185">如果 Windows 防火牆已於主要 SQL Server e04-ocs.los_a.lsipt.local\rtc 中啟用，連接埠 5022 可透過防火牆進行存取。</span><span class="sxs-lookup"><span data-stu-id="d169f-185">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the primary SQL Server e04-ocs.los_a.lsipt.local\rtc.</span></span>

    - <span data-ttu-id="d169f-186">如果 Windows 防火牆已於鏡像 SQL Server K16-ocs.los_a.lsipt.local\rtc 中啟用，連接埠 5022 可透過防火牆進行存取。</span><span class="sxs-lookup"><span data-stu-id="d169f-186">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the mirror SQL Server K16-ocs.los_a.lsipt.local\rtc.</span></span>

    - <span data-ttu-id="d169f-187">如果 Windows 防火牆已於見證 SQL Server AB14-lct.los_a.lsipt.local\rtc 中啟用，連接埠 7022 可透過防火牆進行存取。</span><span class="sxs-lookup"><span data-stu-id="d169f-187">Port 7022 is accessible through the firewall if Windows Firewall is enabled in the witness SQL Server AB14-lct.los_a.lsipt.local\rtc.</span></span>

   - <span data-ttu-id="d169f-188">在所有主要和鏡像 SQL server 上執行 SQL Server 的帳戶具有檔案共用 E04-OCS\csdatabackup 的讀取/寫入權限。 \\</span><span class="sxs-lookup"><span data-stu-id="d169f-188">Accounts running the SQL Servers on all primary and mirror SQL servers have read/write permission to the file share \\E04-OCS\csdatabackup</span></span>

   - <span data-ttu-id="d169f-p119">確認 Windows Management Instrumentation (WMI) 提供者正執行於所有伺服器上。Cmdlet 會使用此提供者尋找執行於所有主要、鏡像及見證伺服器的 SQL Server 服務帳戶資訊。</span><span class="sxs-lookup"><span data-stu-id="d169f-p119">Verify that the Windows Management Instrumentation (WMI) provider is running on all these servers. The cmdlet uses this provider to find the account information for SQL Server services running on all primary, mirror and witness servers.</span></span>

   - <span data-ttu-id="d169f-191">確認執行此 Cmdlet 的帳戶具有權限，可為所有鏡像伺服器建立資料與記錄檔的資料夾。</span><span class="sxs-lookup"><span data-stu-id="d169f-191">Verify that the account running this cmdlet has permission to create the folders for the data and log files for all the mirror servers.</span></span>

   - <span data-ttu-id="d169f-p120">請注意，SQL 執行個體用以執行的使用者帳戶必須具有檔案共用的讀取/寫入權限。如果檔案共用在其他的伺服器上，而且 SQL 執行個體執行本機系統帳戶，您必須將檔案共用權限授與託管 SQL 執行個體的伺服器。</span><span class="sxs-lookup"><span data-stu-id="d169f-p120">Note that the user account that the SQL instance uses to run must have read/write permission to the file share. If the file share is on a different server, and the SQL instance runs a local system account, you must grant file share permissions to the server that hosts the SQL instance.</span></span>

3. <span data-ttu-id="d169f-194">輸入 A 並按 ENTER 鍵。</span><span class="sxs-lookup"><span data-stu-id="d169f-194">Type A and press ENTER.</span></span>

    <span data-ttu-id="d169f-195">即會設定鏡像。</span><span class="sxs-lookup"><span data-stu-id="d169f-195">The mirroring will be configured.</span></span>

    <span data-ttu-id="d169f-196">**Install-CsMirrorDatabase** 會安裝鏡像伺服器，並設定位於主要 SQL 存放區所有資料庫的鏡像。</span><span class="sxs-lookup"><span data-stu-id="d169f-196">**Install-CsMirrorDatabase** installs the mirror and configures mirroring for all the databases that are present on the primary SQL store.</span></span> <span data-ttu-id="d169f-197">如果您只想要為特定資料庫設定鏡像，您可以使用-DatabaseType 選項，或者，如果您想要設定所有資料庫的鏡像，除了少數以外，您可以使用-ExcludeDatabaseList 選項，以及以逗號分隔的資料庫名稱清單來排除。</span><span class="sxs-lookup"><span data-stu-id="d169f-197">If you want to configure mirroring for only specific databases, you can use the -DatabaseType option, or if you want to configure mirroring for all databases except for a few, you can use the -ExcludeDatabaseList option, along with a comma-separated list of database names to exclude.</span></span>

    <span data-ttu-id="d169f-198">例如，如果您將下列選項新增至 **Install-CsMirrorDatabase**，所有資料庫即會作鏡像處理，Rtcab 和 Rtcxds 除外。</span><span class="sxs-lookup"><span data-stu-id="d169f-198">For example, if you add the following option to **Install-CsMirrorDatabase**, all databases except rtcab and rtcxds will be mirrored.</span></span>

    `-ExcludeDatabaseList rtcab,rtcxds`

   <span data-ttu-id="d169f-199">例如，如果您將下列選項新增至 **Install-CsMirrorDatabase**，則只有 Rtcab、Rtcshared 及 Rtcxds 資料庫會作鏡像處理。</span><span class="sxs-lookup"><span data-stu-id="d169f-199">For example, if you add the following option to **Install-CsMirrorDatabase**, only the rtcab, rtcshared, and rtcxds databases will be mirrored.</span></span>

    `-DatabaseType User`

## <a name="removing-or-changing-sql-mirroring"></a><span data-ttu-id="d169f-200">移除或變更 SQL 鏡像</span><span class="sxs-lookup"><span data-stu-id="d169f-200">Removing or Changing SQL Mirroring</span></span>

<span data-ttu-id="d169f-p122">若要在拓撲產生器中移除集區的 SQL 鏡像，您必須先使用 Cmdlet 將 SQL Server 中的鏡像移除，然後，您可使用拓撲產生器從拓撲移除鏡像。若要移除 SQL Server 中的鏡像，請使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="d169f-p122">To remove the SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server. You can then use Topology Builder to remove the mirror from the topology. To remove the mirror in SQL Server, use the following cmdlet:</span></span>

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]
```

<span data-ttu-id="d169f-204">例如，若要移除鏡像並捨棄使用者資料庫的資料庫，請輸入：</span><span class="sxs-lookup"><span data-stu-id="d169f-204">For example, to remove mirroring and drop the databases for the User databases, type the following:</span></span>

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror
```

<span data-ttu-id="d169f-205">此  `-DropExistingDatabasesOnMirror` 選項會從鏡像中刪除受影響的資料庫。</span><span class="sxs-lookup"><span data-stu-id="d169f-205">The  `-DropExistingDatabasesOnMirror` option causes the affected databases to be deleted from the mirror.</span></span>

<span data-ttu-id="d169f-206">此外，若要從拓撲移除鏡像伺服器，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="d169f-206">Then, to remove the mirror from the topology, do the following:</span></span>

1. <span data-ttu-id="d169f-207">在拓撲產生器中，以滑鼠右鍵按一下集區，再按一下 **[編輯內容]**。</span><span class="sxs-lookup"><span data-stu-id="d169f-207">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2. <span data-ttu-id="d169f-208">取消核取 **[啟用 SQL 存放區鏡像]** 並按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d169f-208">Uncheck **Enable SQL Store Mirroring** and click **OK**.</span></span>

3. <span data-ttu-id="d169f-209">發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="d169f-209">Publish the topology.</span></span>

## <a name="removing-a-mirroring-witness"></a><span data-ttu-id="d169f-210">移除鏡像見證</span><span class="sxs-lookup"><span data-stu-id="d169f-210">Removing a Mirroring Witness</span></span>

<span data-ttu-id="d169f-211">如果您需要從後端伺服器鏡像設定中移除見證，請使用此程式。</span><span class="sxs-lookup"><span data-stu-id="d169f-211">Use this procedure if you need to remove the witness from a Back End Server mirroring configuration.</span></span>

1. <span data-ttu-id="d169f-212">在拓撲產生器中，以滑鼠右鍵按一下集區，再按一下 **[編輯內容]**。</span><span class="sxs-lookup"><span data-stu-id="d169f-212">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2. <span data-ttu-id="d169f-213">取消核取 **[使用 SQL Server 鏡像見證啟用自動容錯移轉]**，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d169f-213">Uncheck **Use SQL Server mirroring witness to enable automatic failover** and click **OK**.</span></span>

3. <span data-ttu-id="d169f-214">發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="d169f-214">Publish the topology.</span></span>

    <span data-ttu-id="d169f-215">發行拓撲之後，拓撲產生器會顯示一則訊息，其中包含下列各項：</span><span class="sxs-lookup"><span data-stu-id="d169f-215">After publishing the topology, Topology Builder you will see a message that includes the following</span></span>

   ```console
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    <span data-ttu-id="d169f-216">不過，請不要執行該步驟，也不要像那樣輸入  `Uninstall-CsMirrorDatabase` ，否則會卸載整個鏡像設定。</span><span class="sxs-lookup"><span data-stu-id="d169f-216">However, do not follow that step, and do not type  `Uninstall-CsMirrorDatabase` as that would uninstall the entire mirroring configuration.</span></span>

4. <span data-ttu-id="d169f-217">若要從 SQL Server 設定只移除見證，請依照 [從資料庫鏡像會話移除見證 (SQL server) ](/sql/database-engine/database-mirroring/remove-the-witness-from-a-database-mirroring-session-sql-server)中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="d169f-217">To remove just the witness from the SQL Server configuration, follow the instructions in [Remove the Witness from a Database Mirroring Session (SQL Server)](/sql/database-engine/database-mirroring/remove-the-witness-from-a-database-mirroring-session-sql-server).</span></span>