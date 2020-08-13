---
title: Lync Server 2013：設定 SQL Server 叢集
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server clustering
ms:assetid: d7b52ef1-573c-48ed-bb94-34e37b49645c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383982(v=OCS.15)
ms:contentKeyID: 56472032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59c02a5ab417a17c7c81b2c495ce96e6948aebc7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179890"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-clustering-for-lync-server-2013"></a><span data-ttu-id="7f9d1-102">設定 Lync Server 2013 的 SQL Server 叢集</span><span class="sxs-lookup"><span data-stu-id="7f9d1-102">Configure SQL Server clustering for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f9d1-103">_**主題上次修改日期：** 2014-01-10_</span><span class="sxs-lookup"><span data-stu-id="7f9d1-103">_**Topic Last Modified:** 2014-01-10_</span></span>

<span data-ttu-id="7f9d1-104">Microsoft Lync Server 2013 支援 SQL Server 2012 和 SQL Server 2008 R2 的群集。</span><span class="sxs-lookup"><span data-stu-id="7f9d1-104">Microsoft Lync Server 2013 supports clustering for SQL Server 2012 and SQL Server 2008 R2.</span></span> <span data-ttu-id="7f9d1-105">如需支援內容的詳細資訊，請參閱[Lync Server 2013 中的資料庫軟體支援](lync-server-2013-database-software-support.md)。</span><span class="sxs-lookup"><span data-stu-id="7f9d1-105">For details about what is supported, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span>

<span data-ttu-id="7f9d1-106">安裝及部署 Enterprise Edition 前端伺服器及後端資料庫之前，您應該先安裝及設定 SQL Server 叢集。</span><span class="sxs-lookup"><span data-stu-id="7f9d1-106">You should set up and configure the SQL Server cluster before you install and deploy the Enterprise Edition Front End Server and back-end database.</span></span> <span data-ttu-id="7f9d1-107">如需 SQL Server 2012 中容錯移轉叢集的最佳作法和設定指示，請參閱 <https://technet.microsoft.com/library/hh231721.aspx> 。</span><span class="sxs-lookup"><span data-stu-id="7f9d1-107">For best practices and setup instructions for failover clustering in SQL Server 2012, see <https://technet.microsoft.com/library/hh231721.aspx>.</span></span> <span data-ttu-id="7f9d1-108">如需 SQL Server 2008 中的容錯移轉叢集，請參閱 <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx> 。</span><span class="sxs-lookup"><span data-stu-id="7f9d1-108">For failover clustering in SQL Server 2008, see <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx>.</span></span>

<span data-ttu-id="7f9d1-109">在安裝 SQL Server 時，應安裝 SQL Server Management Studio 以管理資料庫的位置與記錄檔位置。</span><span class="sxs-lookup"><span data-stu-id="7f9d1-109">When you install SQL Server, you should install SQL Server Management Studio to manage the locations for database and log file locations.</span></span> <span data-ttu-id="7f9d1-110">您在安裝 SQL Server 時，可以選用性元件的形式安裝 SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="7f9d1-110">SQL Server Management Studio is installed as an optional component when you install SQL Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7f9d1-111">若要在 SQL Server 伺服器上安裝及部署資料庫，您必須是資料庫檔案安裝所在之 SQL Server 伺服器的 SQL Server sysadmin 群組成員。</span><span class="sxs-lookup"><span data-stu-id="7f9d1-111">To install and deploy the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmin group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="7f9d1-112">如果您不是 SQL Server sysadmin 群組的成員，則必須要求將自己新增至該群組，直到資料庫檔案完成部署為止。</span><span class="sxs-lookup"><span data-stu-id="7f9d1-112">If you are not a member of the SQL Server sysadmin group, you will need to request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="7f9d1-113">如果您無法成為 sysadmin 群組的成員，則應將用以設定及部署資料庫的指令碼提供給 SQL Server 資料庫系統管理員。</span><span class="sxs-lookup"><span data-stu-id="7f9d1-113">If you cannot be made a member of the sysadmin group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="7f9d1-114">如需適當的使用者權限及完成程式所需許可權的詳細資訊，請參閱<A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013 中的 SQL Server 部署許可權</A>。</span><span class="sxs-lookup"><span data-stu-id="7f9d1-114">For details about the proper user rights and permissions that you need to accomplish the procedures, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-sql-server-clustering"></a><span data-ttu-id="7f9d1-115">設定 SQL Server 叢集</span><span class="sxs-lookup"><span data-stu-id="7f9d1-115">To configure SQL Server clustering</span></span>

1.  <span data-ttu-id="7f9d1-116">完成 SQL Server 叢集的安裝和設定之後，您可以使用 SQL server 叢集的) 設定 (中所設定的 SQL server 實例虛擬叢集名稱，在拓撲產生器中定義 SQL Server 存放區，並使用 SQL Server 資料庫的設定。</span><span class="sxs-lookup"><span data-stu-id="7f9d1-116">After you have completed the installation and configuration of SQL Server clustering, you define the SQL Server store in Topology Builder by using the SQL Server instance virtual cluster name (as configured in the setup for SQL Server clustering) and the instance name of the SQL Server database.</span></span> <span data-ttu-id="7f9d1-117">不同於單一 SQL Server 伺服器，針對叢集 SQL Server 伺服器，您會使用虛擬節點完整網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="7f9d1-117">Different from a single SQL Server-based server, you will use the virtual node fully qualified domain name (FQDN) for a clustered SQL Server-based server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7f9d1-118">您不需要為拓撲產生器設定個別的 Windows Server 叢集節點。</span><span class="sxs-lookup"><span data-stu-id="7f9d1-118">The individual Windows Server cluster nodes do not have to be configured for Topology Builder.</span></span> <span data-ttu-id="7f9d1-119">您將只會使用虛擬 SQL Server 叢集名稱。</span><span class="sxs-lookup"><span data-stu-id="7f9d1-119">You will use only the virtual SQL Server cluster name.</span></span>

    
    </div>

2.  <span data-ttu-id="7f9d1-120">如果您使用拓撲產生器來部署資料庫，您必須是 SQL Server 系統管理員群組的成員。</span><span class="sxs-lookup"><span data-stu-id="7f9d1-120">If you are using Topology Builder to deploy your databases, you must be a member of the SQL Server sysadmin group.</span></span> <span data-ttu-id="7f9d1-121">如果您是 SQL Server sysadmin 群組的成員，但是您在網域中沒有許可權 (例如，SQL Server 資料庫系統管理員角色) ，則您具有建立資料庫的許可權，但無法在 Lync Server 中讀取必要的資訊。</span><span class="sxs-lookup"><span data-stu-id="7f9d1-121">If you are a member of the SQL Server sysadmin group, but you do not have privileges in the domain (for example, a SQL Server database administrator role), then you have the rights to create the databases but not to read necessary information in Lync Server.</span></span> <span data-ttu-id="7f9d1-122">如需部署 Lync Server 所需之使用者權利的詳細資訊，請參閱[Lync server 2013 中的 SQL Server 部署許可權](lync-server-2013-deployment-permissions-for-sql-server.md)。</span><span class="sxs-lookup"><span data-stu-id="7f9d1-122">For details about the user rights and permissions necessary to deploying Lync Server, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

3.  <span data-ttu-id="7f9d1-p108">使用 SQL Server Management Studio，確定資料庫資料夾與記錄檔資料夾的預設值均正確對應至 SQL Server 叢集中的共用磁碟。如果您要使用拓撲產生器建立資料庫，則必須執行此程序。</span><span class="sxs-lookup"><span data-stu-id="7f9d1-p108">Ensure that the database folder and log files folder defaults are mapped correctly to the shared disks in the SQL Server cluster by using SQL Server Management Studio. This is a required procedure if you will create databases by using Topology Builder.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7f9d1-125">如果您未安裝 SQL Server Management Studio，可於此時安裝，方法是重新執行 SQL Server 安裝，然後將管理工具選取為現有 SQL Server 部署的新增功能。</span><span class="sxs-lookup"><span data-stu-id="7f9d1-125">If you did not install SQL Server Management Studio, you can install it by rerunning the SQL Server installation, and then selecting the management tool as an added feature for the existing SQL Server deployment.</span></span>

    
    </div>

4.  <span data-ttu-id="7f9d1-126">使用拓撲產生器或 Windows PowerShell Cmdlet，為 SQL Server 服務器安裝資料庫。</span><span class="sxs-lookup"><span data-stu-id="7f9d1-126">Install the databases for the SQL Server-based server by using either Topology Builder or Windows PowerShell cmdlets.</span></span> <span data-ttu-id="7f9d1-127">若要使用拓撲產生器，請使用下列程式。</span><span class="sxs-lookup"><span data-stu-id="7f9d1-127">To use Topology Builder, use the following procedure.</span></span> <span data-ttu-id="7f9d1-128">若要使用 Windows PowerShell Cmdlet，請參閱[在 Lync server 2013 中使用 Lync Server 管理命令介面進行資料庫安裝](lync-server-2013-database-installation-using-lync-server-management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="7f9d1-128">To use Windows PowerShell cmdlets, see [Database installation using Lync Server Management Shell in Lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="to-create-databases-using-topology-builder"></a><span data-ttu-id="7f9d1-129">使用拓撲產生器建立資料庫</span><span class="sxs-lookup"><span data-stu-id="7f9d1-129">To create databases using Topology Builder</span></span>

1.  <span data-ttu-id="7f9d1-130">啟動拓撲產生器：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。</span><span class="sxs-lookup"><span data-stu-id="7f9d1-130">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="7f9d1-131">下列程式假設您已在拓撲產生器中定義及設定拓撲。</span><span class="sxs-lookup"><span data-stu-id="7f9d1-131">The following procedure assumes that you have defined and configured your topology in Topology Builder.</span></span> <span data-ttu-id="7f9d1-132">如需定義拓撲的詳細資訊，請參閱<A href="lync-server-2013-defining-and-configuring-the-topology.md">在 Lync Server 2013 中定義及設定拓撲</A>。</span><span class="sxs-lookup"><span data-stu-id="7f9d1-132">For details about defining your topology, see<A href="lync-server-2013-defining-and-configuring-the-topology.md">Defining and configuring the topology in Lync Server 2013</A>.</span></span> <span data-ttu-id="7f9d1-133">若要使用拓撲產生器來發行拓撲及設定資料庫，您必須以具有正確使用者權限與群組成員資格的使用者身分登入。</span><span class="sxs-lookup"><span data-stu-id="7f9d1-133">To use Topology Builder to publish the topology and configure the database, you must log on as a user with the correct user rights and group memberships.</span></span> <span data-ttu-id="7f9d1-134">如需有關必要許可權和群組成員資格的詳細資訊，請參閱<A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013 中的 SQL Server 部署許可權</A>。</span><span class="sxs-lookup"><span data-stu-id="7f9d1-134">For details about the required rights and group memberships, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="7f9d1-135">在 [拓撲產生器] 中，當您發佈拓撲時，請在 [**建立資料庫**] 頁面上，按一下 [**高級**]。</span><span class="sxs-lookup"><span data-stu-id="7f9d1-135">In Topology Builder, as you publish the topology, on the **Create databases** page, click **Advanced**.</span></span>

3.  <span data-ttu-id="7f9d1-p111">**[選取資料庫檔案位置]** 頁面上有兩個選項，可決定資料庫檔案部署至 SQL Server 叢集的方式。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="7f9d1-p111">The **Select Database File Location** page has two options that determine how the database files will be deployed to the SQL Server cluster. Select one of the following:</span></span>
    
      - <span data-ttu-id="7f9d1-138">**自動判斷資料庫檔案位置。**</span><span class="sxs-lookup"><span data-stu-id="7f9d1-138">**Automatically determine the database file location.**</span></span> <span data-ttu-id="7f9d1-139">此選項會使用演算法，根據 SQL Server 伺服器上的磁碟機設定來決定資料庫記錄檔與資料檔的位置。</span><span class="sxs-lookup"><span data-stu-id="7f9d1-139">This selection uses an algorithm to determine the database log and data file locations based on the drive configuration on the SQL Server-based server.</span></span> <span data-ttu-id="7f9d1-140">檔案將以此方式分配，以期達到最佳效能。</span><span class="sxs-lookup"><span data-stu-id="7f9d1-140">The files will be distributed in such a way as to attempt to provide optimal performance.</span></span>
    
      - <span data-ttu-id="7f9d1-141">[使用 SQL Server 執行個體預設值]。</span><span class="sxs-lookup"><span data-stu-id="7f9d1-141">Use SQL Server instance defaults.</span></span> <span data-ttu-id="7f9d1-142">選取此選項後，將會根據 SQL Server 執行個體設定安裝記錄檔與資料檔。</span><span class="sxs-lookup"><span data-stu-id="7f9d1-142">Selecting this option will install the log and data files according to the SQL Server instance settings.</span></span> <span data-ttu-id="7f9d1-143">在資料庫檔案部署至 SQL Server 後，SQL Server 資料庫系統管理員可能會依據您特定的 SQL Server 設定需求而重新配置檔案位置，以期達到最佳效能。</span><span class="sxs-lookup"><span data-stu-id="7f9d1-143">After deployment of the database files to the SQL Server, your SQL Server database administrator may want to relocate the files to optimize performance for your particular SQL Server configuration requirements.</span></span>

4.  <span data-ttu-id="7f9d1-144">完成拓撲發行作業，並確認作業期間未發生任何錯誤。</span><span class="sxs-lookup"><span data-stu-id="7f9d1-144">Complete the publishing of the topology and confirm that there were no errors during the operation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

