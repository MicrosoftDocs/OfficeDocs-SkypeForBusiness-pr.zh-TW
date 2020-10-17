---
title: Lync Server 2013：使用 Lync Server 管理命令介面安裝資料庫
description: Lync Server 2013：使用 Lync Server 管理命令介面進行資料庫安裝。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database installation using Lync Server Management Shell
ms:assetid: c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398832(v=OCS.15)
ms:contentKeyID: 48185401
ms.date: 06/16/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d572984c94d280723b12c5343a92ddfaa12d4f0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558179"
---
# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a><span data-ttu-id="2c944-103">在 Lync Server 2013 中使用 Lync Server 管理命令介面安裝資料庫</span><span class="sxs-lookup"><span data-stu-id="2c944-103">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c944-104">_**主題上次修改日期：** 2016-06-16_</span><span class="sxs-lookup"><span data-stu-id="2c944-104">_**Topic Last Modified:** 2016-06-16_</span></span>

<span data-ttu-id="2c944-105">伺服器管理員和 SQL Server 系統管理員之間的角色與責任的分離，可能會導致執行延遲。</span><span class="sxs-lookup"><span data-stu-id="2c944-105">Separation of roles and responsibilities between server administrators and SQL Server administrators can result in delays in implementation.</span></span> <span data-ttu-id="2c944-106">Lync Server 2013 使用以角色為基礎的存取控制 (RBAC) ，以減輕這些困難。</span><span class="sxs-lookup"><span data-stu-id="2c944-106">Lync Server 2013 uses role-based access control (RBAC) to mitigate these difficulties.</span></span> <span data-ttu-id="2c944-107">在某些情況下，SQL Server 系統管理員必須在不是以 SQL Server 為基礎的伺服器上，管理資料庫在 RBAC 之外的安裝。</span><span class="sxs-lookup"><span data-stu-id="2c944-107">In some instances, the SQL Server administrator must manage the installation of databases on the SQL Server-based server outside RBAC.</span></span> <span data-ttu-id="2c944-108">Lync Server 2013 管理命令介面提供一種方式，讓 SQL Server 管理員執行 Windows PowerShell Cmdlet，以設定具有正確資料和記錄檔的資料庫。</span><span class="sxs-lookup"><span data-stu-id="2c944-108">The Lync Server 2013 Management Shell provides a way for the SQL Server administrator to run Windows PowerShell cmdlets designed to configure the databases with the correct data and log files.</span></span> <span data-ttu-id="2c944-109">如需詳細資訊，請參閱 [Lync server 2013 中的 SQL Server 部署許可權](lync-server-2013-deployment-permissions-for-sql-server.md)。</span><span class="sxs-lookup"><span data-stu-id="2c944-109">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="2c944-110">下列程式假設最低的 Lync Server 2013 OCSCore.msi，SQL Server Native Client ( # A1) Microsoft SQL Server 2012 管理物件，已安裝 Microsoft SQL Server 2012 和 Microsoft SQL Server 2012 ADOMD.NET 的 CLR 類型。</span><span class="sxs-lookup"><span data-stu-id="2c944-110">The following procedure assumes that at a minimum the Lync Server 2013 OCSCore.msi, SQL Server Native Client (sqlncli.msi) Microsoft SQL Server 2012 Management Objects, CLR Types for Microsoft SQL Server 2012 and Microsoft SQL Server 2012 ADOMD.NET are installed.</span></span> <span data-ttu-id="2c944-111">OCSCore.msi 位於 \Setup\AMD64\Setup 目錄的安裝媒體中。</span><span class="sxs-lookup"><span data-stu-id="2c944-111">The OCSCore.msi is located on the installation media in the \Setup\AMD64\Setup directory.</span></span> <span data-ttu-id="2c944-112">其餘的元件位於 \Setup\amd64。</span><span class="sxs-lookup"><span data-stu-id="2c944-112">The remaining components are located in \Setup\amd64.</span></span> <span data-ttu-id="2c944-113">此外，Lync Server 2013 的 Active Directory 準備作業已成功完成。</span><span class="sxs-lookup"><span data-stu-id="2c944-113">Additionally, Active Directory preparation for Lync Server 2013 has been successfully completed.</span></span>



</div>

<span data-ttu-id="2c944-114">**Install-CsDatabase** 是用來安裝資料庫的 Windows PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2c944-114">**Install-CsDatabase** is the Windows PowerShell cmdlet you use to install the databases.</span></span> <span data-ttu-id="2c944-115">**Install-CsDatabase** Cmdlet 的參數數目很多，但這裡只有少數部分會加以討論。</span><span class="sxs-lookup"><span data-stu-id="2c944-115">The **Install-CsDatabase** cmdlet has a large number of parameters, only a few of which are discussed here.</span></span> <span data-ttu-id="2c944-116">如需可能的參數的詳細資訊，請參閱 Lync Server 2013 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="2c944-116">For details about the possible parameters, see the Lync Server 2013 Management Shell documentation.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="2c944-117">若要避免效能及可能的超時問題，請在參照 SQL Server 服務器的伺服器時，永遠 (Fqdn) 使用完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="2c944-117">To avoid performance and possible time-out issues, always use fully qualified domain names (FQDNs) when referring to SQL Server-based servers.</span></span> <span data-ttu-id="2c944-118">避免使用僅限主機名稱稱參照。</span><span class="sxs-lookup"><span data-stu-id="2c944-118">Avoid using host name-only references.</span></span> <span data-ttu-id="2c944-119">例如，使用 sqlbe01.contoso.net，但避免使用 SQLBE01。</span><span class="sxs-lookup"><span data-stu-id="2c944-119">For example, use sqlbe01.contoso.net, but avoid using SQLBE01.</span></span>



</div>

<span data-ttu-id="2c944-120">若要安裝資料庫， **Install-CsDatabase** 會使用三種主要方法將資料庫放入已準備好的 SQL server 伺服器上：</span><span class="sxs-lookup"><span data-stu-id="2c944-120">For installing databases, **Install-CsDatabase** uses three primary methods for placing the databases onto the prepared SQL Server-based server:</span></span>

  - <span data-ttu-id="2c944-121">在未 DatabasePaths 或 UseDefaultSqlPath 的情況下執行 **Install-CsDatabase** 。</span><span class="sxs-lookup"><span data-stu-id="2c944-121">Run **Install-CsDatabase** without DatabasePaths or UseDefaultSqlPath.</span></span> <span data-ttu-id="2c944-122">Cmdlet 會使用內建的演算法，判斷記錄檔及資料檔的最佳位置。</span><span class="sxs-lookup"><span data-stu-id="2c944-122">The cmdlet uses a built in algorithm to determine the best placement for the log and data files.</span></span> <span data-ttu-id="2c944-123">此演算法只適用于獨立的 SQL Server 實施。</span><span class="sxs-lookup"><span data-stu-id="2c944-123">The algorithm only works for stand-alone SQL Server implementations.</span></span>

  - <span data-ttu-id="2c944-124">使用 DatabasePaths 參數執行 **Install-CsDatabase** 。</span><span class="sxs-lookup"><span data-stu-id="2c944-124">Run **Install-CsDatabase** with the DatabasePaths parameter.</span></span> <span data-ttu-id="2c944-125">如果定義了 DatabasePaths 參數，則不會使用內建演算法來優化記錄及資料檔案位置。</span><span class="sxs-lookup"><span data-stu-id="2c944-125">The built-in algorithm to optimize log and data file locations is not used if the DatabasePaths parameter is defined.</span></span> <span data-ttu-id="2c944-126">使用此參數可讓您定義將部署記錄檔和資料檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="2c944-126">Using this parameter allows you to define the locations where log and data files will be deployed.</span></span>

  - <span data-ttu-id="2c944-127">使用 UseDefaultSqlPaths 執行 **Install-CsDatabase** 。</span><span class="sxs-lookup"><span data-stu-id="2c944-127">Run **Install-CsDatabase** with UseDefaultSqlPaths.</span></span> <span data-ttu-id="2c944-128">此選項不使用內建的演算法來優化記錄檔和資料檔案位置。</span><span class="sxs-lookup"><span data-stu-id="2c944-128">This option does not use the built-in algorithm to optimize the log and data file locations.</span></span> <span data-ttu-id="2c944-129">會根據 SQL Server 系統管理員所設定的預設值來部署記錄檔和資料檔案。</span><span class="sxs-lookup"><span data-stu-id="2c944-129">Log and data file are deployed according to the defaults set by the SQL Server administrator.</span></span> <span data-ttu-id="2c944-130">這些路徑通常是為了預先自動管理 SQL Server 上的記錄檔與資料檔的目的，不會與 Lync Server 2013 的設定產生關聯。</span><span class="sxs-lookup"><span data-stu-id="2c944-130">These paths are typically set for the purpose of automatic administration of log and data files on the SQL Server in advance, and are not associated with the setup of Lync Server 2013.</span></span>

  - <span data-ttu-id="2c944-131">DatabasePathMap 參數也可以用來明確指定每個資料庫及其各自記錄檔的位置。</span><span class="sxs-lookup"><span data-stu-id="2c944-131">The DatabasePathMap parameter can also be used to explicitly specify a location for each database and its respective log file.</span></span>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a><span data-ttu-id="2c944-132">使用 Windows PowerShell Cmdlet 來設定 SQL Server 中央管理存放區</span><span class="sxs-lookup"><span data-stu-id="2c944-132">To use Windows PowerShell cmdlets to configure the SQL Server Central Management store</span></span>

1.  <span data-ttu-id="2c944-133">在任何電腦上，請使用管理認證登入，以在 SQL Server 服務器上建立資料庫。</span><span class="sxs-lookup"><span data-stu-id="2c944-133">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="2c944-134">如需詳細資訊，請參閱 [Lync server 2013 中的 SQL Server 部署許可權](lync-server-2013-deployment-permissions-for-sql-server.md)。</span><span class="sxs-lookup"><span data-stu-id="2c944-134">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

2.  <span data-ttu-id="2c944-135">開啟 [Lync Server 2013 管理命令介面]。</span><span class="sxs-lookup"><span data-stu-id="2c944-135">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="2c944-136">如果您未調整 Windows PowerShell 的執行原則，則必須調整原則，以允許 Windows PowerShell 腳本執行。</span><span class="sxs-lookup"><span data-stu-id="2c944-136">If you have not adjusted the execution policy for Windows PowerShell, you must adjust the policy to allow Windows PowerShell scripts to run.</span></span> <span data-ttu-id="2c944-137">如需詳細資訊，請參閱 at 中的「檢查執行原則」 [https://go.microsoft.com/fwlink/p/?linkId=203093](https://go.microsoft.com/fwlink/p/?linkid=203093) 。</span><span class="sxs-lookup"><span data-stu-id="2c944-137">For details, see “Examining the Execution Policy” at [https://go.microsoft.com/fwlink/p/?linkId=203093](https://go.microsoft.com/fwlink/p/?linkid=203093).</span></span>

3.  <span data-ttu-id="2c944-138">使用 **Install-CsDatabase** Cmdlet 來安裝中央管理存放區。</span><span class="sxs-lookup"><span data-stu-id="2c944-138">Use the **Install-CsDatabase** cmdlet to install the Central Management store.</span></span>
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <fully qualified domain name of SQL Server> 
        -SqlInstanceName <named instance> -DatabasePaths <logfile path>,<database file path> 
        -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn sqlbe.contoso.net -SqlInstanceName rtc -DatabasePaths "C:\CSDB-Logs","C:\CSDB-CMS" -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="2c944-139">Report 參數是選用的，但如果您要記錄安裝程式，會很有用。</span><span class="sxs-lookup"><span data-stu-id="2c944-139">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

4.  <span data-ttu-id="2c944-140">**Install-CsDatabase – DatabasePaths** 最多可以使用六個路徑參數，每個參數都會定義在 SQL Server 資料和記錄檔放置中所定義的磁片磁碟機路徑。</span><span class="sxs-lookup"><span data-stu-id="2c944-140">**Install-CsDatabase –DatabasePaths** can use up to six path parameters, each defining the paths for the drives as defined in SQL Server Data and Log File Placement.</span></span> <span data-ttu-id="2c944-141">依照 Lync Server 2013 中的資料庫設定邏輯規則，會將磁片磁碟機分解成2、4或6的桶。</span><span class="sxs-lookup"><span data-stu-id="2c944-141">By the logical rules of the database configuration in Lync Server 2013, drives are parsed out into buckets of two, four, or six.</span></span> <span data-ttu-id="2c944-142">視您的 SQL Server 設定和 bucket 數目而定，您將會提供兩個路徑、四個路徑或六個路徑。</span><span class="sxs-lookup"><span data-stu-id="2c944-142">Depending on your SQL Server configuration and the number of buckets, you will supply two paths, four paths, or six paths.</span></span>
    
    <span data-ttu-id="2c944-143">如果您有三個磁片磁碟機，則記錄會取得優先順序，而且會將資料檔案散佈。</span><span class="sxs-lookup"><span data-stu-id="2c944-143">If you have three drives, the log gets priority and the data files are distributed after.</span></span> <span data-ttu-id="2c944-144">使用六個磁片磁碟機設定之 SQL Server 服務器的範例：</span><span class="sxs-lookup"><span data-stu-id="2c944-144">An example for a SQL Server-based server configured with six drives:</span></span>
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  <span data-ttu-id="2c944-145">資料庫安裝完成時，您可以關閉 Lync Server 2013 管理命令介面，或繼續安裝拓撲產生器中定義的 Lync Server 2013 設定的資料庫。</span><span class="sxs-lookup"><span data-stu-id="2c944-145">When the database installation completes, you can close Lync Server 2013 Management Shell or proceed to the installation of the Lync Server 2013 configured databases defined in Topology Builder.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a><span data-ttu-id="2c944-146">使用 Windows PowerShell Cmdlet 設定 SQL Server 拓撲設定的資料庫</span><span class="sxs-lookup"><span data-stu-id="2c944-146">To use Windows PowerShell cmdlets to configure the SQL Server topology configured databases</span></span>

1.  <span data-ttu-id="2c944-147">若要安裝 Lync Server 2013 的拓撲產生器設定資料庫，Lync Server 2013 管理員必須發行此拓撲。</span><span class="sxs-lookup"><span data-stu-id="2c944-147">To install the Topology Builder configured databases for Lync Server 2013, the Lync Server 2013 administrator must publish the topology.</span></span> <span data-ttu-id="2c944-148">如需詳細資訊，請參閱部署檔中的 [發行 Lync Server 2013 中的拓撲](lync-server-2013-publish-the-topology.md) 。</span><span class="sxs-lookup"><span data-stu-id="2c944-148">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="2c944-149">在任何電腦上，請使用管理認證登入，以在 SQL Server 服務器上建立資料庫。</span><span class="sxs-lookup"><span data-stu-id="2c944-149">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="2c944-150">請參閱 [Lync server 2013 中 SQL Server 的部署許可權](lync-server-2013-deployment-permissions-for-sql-server.md)主題。</span><span class="sxs-lookup"><span data-stu-id="2c944-150">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2c944-151">若要設定 SQL Server 資料庫的資料庫，請確定用來執行下列所述步驟的 SQL Server 系統管理員帳戶也是執行 SQL Server 之伺服器上的系統管理員群組 (或同等) 成員，並且持有中央管理伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="2c944-151">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="2c944-152">這對檢查是否有需要 SQL Server 資料庫安裝或設定的任何其他 Lync Server 2013 集區尤為重要。</span><span class="sxs-lookup"><span data-stu-id="2c944-152">This is especially important to check for any additional Lync Server 2013 pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="2c944-153">例如，如果您要部署第二個集區 (pool02) 但是中央管理伺服器角色是由 pool01 所保留。</span><span class="sxs-lookup"><span data-stu-id="2c944-153">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="2c944-154">SQL Server sysadmin 群組 (或同等) 都必須具備 SQL Server 資料庫上的許可權。</span><span class="sxs-lookup"><span data-stu-id="2c944-154">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="2c944-155">開啟 Lync Server 2013 管理命令介面（若尚未開啟）。</span><span class="sxs-lookup"><span data-stu-id="2c944-155">Open Lync Server 2013 Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="2c944-156">使用 **Install-CsDatabase** Cmdlet 安裝拓撲產生器設定的資料庫。</span><span class="sxs-lookup"><span data-stu-id="2c944-156">Use the **Install-CsDatabase** cmdlet to install the Topology Builder configured databases.</span></span>
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <fully qualified domain name of SQL Server> 
         -DatabasePaths <logfile path>,<database file path> -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe.contoso.net 
        -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="2c944-157">Report 參數是選用的，但如果您要記錄安裝程式，會很有用。</span><span class="sxs-lookup"><span data-stu-id="2c944-157">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

5.  <span data-ttu-id="2c944-158">資料庫安裝完成時，請關閉 [Lync Server 2013 管理命令介面]。</span><span class="sxs-lookup"><span data-stu-id="2c944-158">When the database installation completes, close Lync Server 2013 Management Shell.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a><span data-ttu-id="2c944-159">使用 Windows PowerShell Cmdlet 使用 DatabasePathMap 參數設定 SQL Server 拓撲</span><span class="sxs-lookup"><span data-stu-id="2c944-159">To use Windows PowerShell cmdlets to configure the SQL Server topology using the DatabasePathMap parameter</span></span>

1.  <span data-ttu-id="2c944-160">若要安裝 Lync Server 2013 的資料庫，Lync Server 系統管理員必須建立路徑，並根據一組預先定義的規則來部署資料庫檔案和記錄檔。</span><span class="sxs-lookup"><span data-stu-id="2c944-160">To install databases for Lync Server 2013, the Lync Server administrator must create the paths and deploy the databases files and log files according to a predefined set of rules.</span></span>

2.  <span data-ttu-id="2c944-161">在任何電腦上，請使用管理認證登入，以在 SQL Server 服務器上建立資料庫。</span><span class="sxs-lookup"><span data-stu-id="2c944-161">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="2c944-162">請參閱 [Lync server 2013 中 SQL Server 的部署許可權](lync-server-2013-deployment-permissions-for-sql-server.md)主題。</span><span class="sxs-lookup"><span data-stu-id="2c944-162">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2c944-163">若要設定 SQL Server 資料庫的資料庫，請確定用來執行下列所述步驟的 SQL Server 系統管理員帳戶也是執行 SQL Server 之伺服器上的系統管理員群組 (或同等) 成員，並且持有中央管理伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="2c944-163">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="2c944-164">這對檢查是否有需要 SQL Server 資料庫安裝或設定的任何其他 Lync Server 集區尤為重要。</span><span class="sxs-lookup"><span data-stu-id="2c944-164">This is especially important to check for any additional Lync Server pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="2c944-165">例如，如果您要部署第二個集區 (pool02) 但是中央管理伺服器角色是由 pool01 所保留。</span><span class="sxs-lookup"><span data-stu-id="2c944-165">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="2c944-166">SQL Server sysadmin 群組 (或同等) 都必須具備 SQL Server 資料庫上的許可權。</span><span class="sxs-lookup"><span data-stu-id="2c944-166">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="2c944-167">開啟 Lync Server 管理命令介面（若尚未開啟）。</span><span class="sxs-lookup"><span data-stu-id="2c944-167">Open Lync Server Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="2c944-168">使用 **Install-CsDatabase** Cmdlet 搭配 DatabasePathMap 參數和 PowerShell 雜湊表，以安裝拓撲產生器設定的資料庫。</span><span class="sxs-lookup"><span data-stu-id="2c944-168">Use the **Install-CsDatabase** cmdlet with the DatabasePathMap parameter and a PowerShell hash table to install the Topology Builder configured databases.</span></span>

5.  <span data-ttu-id="2c944-169">在範例程式碼中，您可以使用– DatabasePathMap 參數及定義的雜湊表，以細微的方式判斷定義的資料庫路徑，如下所示 (此範例會使用 "C： \\ CSData" ( 所有 \\ 的記錄 ( .ldf) 檔的所有資料庫的資料庫 .mdf) 檔案及 "c： CSLogFiles"。</span><span class="sxs-lookup"><span data-stu-id="2c944-169">In the example code, the paths defined for the databases can be determined in a granular manner by using the –DatabasePathMap parameter and a defined hash table as follows (the example uses “C:\\CSData” for all database (.mdf) files, and “C:\\CSLogFiles” for all log (.ldf) files.</span></span> <span data-ttu-id="2c944-170">Install-CsDatabase) 時，將會視需要建立資料夾：</span><span class="sxs-lookup"><span data-stu-id="2c944-170">Folder will be created as needed by Install-CsDatabase):</span></span>
    ```powershell
    $pathmap = @{
    "BackendStore:BlobStore:DbPath"="C:\CsData";"BackendStore:BlobStore:LogPath"="C:\CsLogFiles"
    "BackendStore:RtcSharedDatabase:DbPath"="C:\CsData";"BackendStore:RtcSharedDatabase:LogPath"="C:\CsLogFiles"
    "ABSStore:AbsDatabase:DbPath"="C:\CsData";"ABSStore:AbsDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:RgsConfigDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsConfigDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:RgsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsDynDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:CpsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:CpsDynDatabase:LogPath"="C:\CsLogFiles"
    "ArchivingStore:ArchivingDatabase:DbPath"="C:\CsData";"ArchivingStore:ArchivingDatabase:LogPath"="C:\CsLogFiles"
    "MonitoringStore:MonitoringDatabase:DbPath"="C:\CsData";"MonitoringStore:MonitoringDatabase:LogPath"="C:\CsLogFiles"
    "MonitoringStore:QoEMetricsDatabase:DbPath"="C:\CsData";"MonitoringStore:QoEMetricsDatabase:LogPath"="C:\CsLogFiles"
    }
    Install-CsDatabase -ConfigureDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
6.  <span data-ttu-id="2c944-171">因為資料庫和記錄檔是以其在目的地資料庫伺服器上的位置明確命名，所以您可以為每個服務類型的實際資料庫和記錄位置定義特定位置。</span><span class="sxs-lookup"><span data-stu-id="2c944-171">Because the database and log files are explicitly named with their location on the destination database server, you can define specific locations for each service type’s actual database and log location.</span></span> <span data-ttu-id="2c944-172">下列範例會將每個特定服務類型的資料庫放在不同的磁片上，並將關聯的記錄檔放在另一部。</span><span class="sxs-lookup"><span data-stu-id="2c944-172">The following example puts databases for each specific service type on separate disks, and associated log files on another.</span></span> <span data-ttu-id="2c944-173">例如：</span><span class="sxs-lookup"><span data-stu-id="2c944-173">For example:</span></span>
    
      - <span data-ttu-id="2c944-174">所有 RTC 資料庫為 "D： \\ RTCDatabase"</span><span class="sxs-lookup"><span data-stu-id="2c944-174">All RTC databases to “D:\\RTCDatabase”</span></span>
    
      - <span data-ttu-id="2c944-175">所有 RTC 記錄檔至 "E： \\ RTCLogs"</span><span class="sxs-lookup"><span data-stu-id="2c944-175">All RTC log files to “E:\\RTCLogs”</span></span>
    
      - <span data-ttu-id="2c944-176">所有應用程式存放區資料庫至 "F： \\ CPSDatabases"</span><span class="sxs-lookup"><span data-stu-id="2c944-176">All application store databases to “F:\\CPSDatabases”</span></span>
    
      - <span data-ttu-id="2c944-177">所有應用程式存放區記錄為 "G： \\ CPSLogs"</span><span class="sxs-lookup"><span data-stu-id="2c944-177">All application store logs to “G:\\CPSLogs”</span></span>
    
      - <span data-ttu-id="2c944-178">所有回應群組存放區資料庫為 "H： \\ RGSDatabases"</span><span class="sxs-lookup"><span data-stu-id="2c944-178">All response group store databases to “H:\\RGSDatabases”</span></span>
    
      - <span data-ttu-id="2c944-179">所有回應群組存放區記錄至 "I： \\ RGSLogs"</span><span class="sxs-lookup"><span data-stu-id="2c944-179">All response group store logs to “I:\\RGSLogs”</span></span>
    
      - <span data-ttu-id="2c944-180">所有通訊錄存放區資料庫至 "J： \\ ABSDatabases"</span><span class="sxs-lookup"><span data-stu-id="2c944-180">All address book store databases to “J:\\ABSDatabases”</span></span>
    
      - <span data-ttu-id="2c944-181">所有通訊錄儲存記錄檔至 "K： \\ ABSLogs"</span><span class="sxs-lookup"><span data-stu-id="2c944-181">All address book store log files to “K:\\ABSLogs”</span></span>
    
      - <span data-ttu-id="2c944-182">所有封存存放區資料庫至 "L： \\ ArchivingDatabases"</span><span class="sxs-lookup"><span data-stu-id="2c944-182">All archiving store databases to “L:\\ArchivingDatabases”</span></span>
    
      - <span data-ttu-id="2c944-183">所有封存儲存區記錄為 "M： \\ ArchivingLogs"</span><span class="sxs-lookup"><span data-stu-id="2c944-183">All archiving store logs to “M:\\ArchivingLogs”</span></span>
    
      - <span data-ttu-id="2c944-184">所有監控存放區資料庫至 "N： \\ MonitoringDatabases"</span><span class="sxs-lookup"><span data-stu-id="2c944-184">All monitoring store databases to “N:\\MonitoringDatabases”</span></span>
    
      - <span data-ttu-id="2c944-185">所有監控存放區記錄檔案為 "O： \\ MonitoringLogfiles"</span><span class="sxs-lookup"><span data-stu-id="2c944-185">All monitoring store log files to “O:\\MonitoringLogfiles”</span></span>
    
    <!-- end list -->
    
    ```powershell    
    $pathmap = @{
    "BackendStore:BlobStore:DbPath"="D:\RTCDatabase";"BackendStore:BlobStore:LogPath"="E:\RTCLogs"
    "BackendStore:RtcSharedDatabase:DbPath"="D:\RTCDatabase";"BackendStore:RtcSharedDatabase:LogPath"="E:\RTCLogs"
    "ABSStore:AbsDatabase:DbPath"="J:\ABSDatabases";"ABSStore:AbsDatabase:LogPath"="K:\ABSLogs"
    "ApplicationStore:RgsConfigDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsConfigDatabase:LogPath"="G:\CPSLogs"
    "ApplicationStore:RgsDynDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsDynDatabase:LogPath"="I:\RGSLogs"
    "ApplicationStore:CpsDynDatabase:DbPath"="F:\CPSDatabases";"ApplicationStore:CpsDynDatabase:LogPath"="G:\CsLogFiles"
    "ArchivingStore:ArchivingDatabase:DbPath"="M:\ArchivingLogs";"ArchivingStore:ArchivingDatabase:LogPath"="N:\MonitoringDatabases"
    "MonitoringStore:MonitoringDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:MonitoringDatabase:LogPath"="O:\MonitoringLogfiles"
    "MonitoringStore:QoEMetricsDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:QoEMetricsDatabase:LogPath"="O:\MonitoringLogfiles"
    }
    
    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
    
    <span data-ttu-id="2c944-186">使用– DatabasePathMap 參數，您可以定義任何邏輯磁片磁碟機號對應組合，為您的 SQL Server 效能與放置需求提供最佳的解決方案。</span><span class="sxs-lookup"><span data-stu-id="2c944-186">Using the –DatabasePathMap parameter, you can define any logical drive letter mapping combination that provides the best solution for your SQL Server performance and placement requirements.</span></span>

<span data-ttu-id="2c944-187">如果您使用 **DatabasePathMap** 方法來設定資料庫資料檔案和記錄檔，當您使用拓撲產生器時，您將需要略微變更正常的處理常式。</span><span class="sxs-lookup"><span data-stu-id="2c944-187">If you configure your database data files and log files by using the **DatabasePathMap** method, you will need to make a slight change to your normal process when using Topology Builder.</span></span> <span data-ttu-id="2c944-188">一般來說，您會定義拓撲選項、發行拓撲，並選擇部署資料庫選項。</span><span class="sxs-lookup"><span data-stu-id="2c944-188">Typically, you would define your topology choices, publish the topology, and choose to deploy the database selections.</span></span>

<span data-ttu-id="2c944-189">如果您已使用 **DatabasePathMap** ，您已完成拓撲產生器程式的第三個部分。</span><span class="sxs-lookup"><span data-stu-id="2c944-189">If you have used **DatabasePathMap** you have already accomplished the third part of the Topology Builder process.</span></span> <span data-ttu-id="2c944-190">在執行拓撲產生器的情況下，如果有完全設定的資料庫伺服器，您仍會定義所有的伺服器角色和選項，但取消選取此選項以建立資料庫。</span><span class="sxs-lookup"><span data-stu-id="2c944-190">In the case of having a completely configured database server in advance of running Topology Builder, you would still define all of your server roles and options, but deselect the option to create the databases.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

