---
title: Lync Server 2013：使用 Lync Server 管理命令介面安裝資料庫
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
ms.openlocfilehash: 8c617d323eb00476b53677b670c8cc6db0b8d05c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a><span data-ttu-id="2f6d4-102">在 Lync Server 2013 中使用 Lync Server 管理命令介面安裝資料庫</span><span class="sxs-lookup"><span data-stu-id="2f6d4-102">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f6d4-103">_**主題上次修改日期：** 2016-06-16_</span><span class="sxs-lookup"><span data-stu-id="2f6d4-103">_**Topic Last Modified:** 2016-06-16_</span></span>

<span data-ttu-id="2f6d4-104">伺服器管理員與 SQL Server 系統管理員之間的角色和職責之間的分離，可能會導致實現中的延遲。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-104">Separation of roles and responsibilities between server administrators and SQL Server administrators can result in delays in implementation.</span></span> <span data-ttu-id="2f6d4-105">Lync Server 2013 使用角色式存取控制（RBAC）來減輕這些困難。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-105">Lync Server 2013 uses role-based access control (RBAC) to mitigate these difficulties.</span></span> <span data-ttu-id="2f6d4-106">在某些情況下，SQL Server 系統管理員必須在 RBAC 以外的 SQL Server 服務器上管理資料庫的安裝。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-106">In some instances, the SQL Server administrator must manage the installation of databases on the SQL Server-based server outside RBAC.</span></span> <span data-ttu-id="2f6d4-107">Lync Server 2013 管理命令介面提供一種方式，讓 SQL Server 系統管理員執行 Windows PowerShell Cmdlet，以使用正確的資料與記錄檔來設定資料庫。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-107">The Lync Server 2013 Management Shell provides a way for the SQL Server administrator to run Windows PowerShell cmdlets designed to configure the databases with the correct data and log files.</span></span> <span data-ttu-id="2f6d4-108">如需詳細資訊，請參閱[Lync server 2013 中的 SQL Server 部署許可權](lync-server-2013-deployment-permissions-for-sql-server.md)。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-108">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="2f6d4-109">下列程式假設您至少安裝 Lync Server 2013 OCSCore、SQL Server 原生用戶端（sqlncli） Microsoft SQL Server 2012 管理物件、Microsoft sql server 2012 與 Microsoft SQL Server 2012 ADOMD.NET 的 CLR 類型。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-109">The following procedure assumes that at a minimum the Lync Server 2013 OCSCore.msi, SQL Server Native Client (sqlncli.msi) Microsoft SQL Server 2012 Management Objects, CLR Types for Microsoft SQL Server 2012 and Microsoft SQL Server 2012 ADOMD.NET are installed.</span></span> <span data-ttu-id="2f6d4-110">OCSCore 位於 \Setup\AMD64\Setup 目錄中的安裝媒體上。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-110">The OCSCore.msi is located on the installation media in the \Setup\AMD64\Setup directory.</span></span> <span data-ttu-id="2f6d4-111">剩餘的元件位於 \Setup\amd64。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-111">The remaining components are located in \Setup\amd64.</span></span> <span data-ttu-id="2f6d4-112">此外，Lync Server 2013 的 Active Directory 準備已順利完成。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-112">Additionally, Active Directory preparation for Lync Server 2013 has been successfully completed.</span></span>



</div>

<span data-ttu-id="2f6d4-113">**安裝-CsDatabase**是您用來安裝資料庫的 Windows PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-113">**Install-CsDatabase** is the Windows PowerShell cmdlet you use to install the databases.</span></span> <span data-ttu-id="2f6d4-114">**CsDatabase** Cmdlet 有大量的參數，這裡只會討論幾個參數。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-114">The **Install-CsDatabase** cmdlet has a large number of parameters, only a few of which are discussed here.</span></span> <span data-ttu-id="2f6d4-115">如需可能參數的詳細資訊，請參閱 Lync Server 2013 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-115">For details about the possible parameters, see the Lync Server 2013 Management Shell documentation.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="2f6d4-116">若要避免效能和可能的超時問題，請在參照 SQL Server 基礎伺服器時，永遠都使用完整的功能變數名稱（Fqdn）。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-116">To avoid performance and possible time-out issues, always use fully qualified domain names (FQDNs) when referring to SQL Server-based servers.</span></span> <span data-ttu-id="2f6d4-117">避免使用僅限主機名稱參照。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-117">Avoid using host name-only references.</span></span> <span data-ttu-id="2f6d4-118">例如，使用 sqlbe01.contoso.net，但請避免使用 SQLBE01。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-118">For example, use sqlbe01.contoso.net, but avoid using SQLBE01.</span></span>



</div>

<span data-ttu-id="2f6d4-119">若要安裝資料庫，**安裝 CsDatabase**使用三種主要方法，將資料庫放在已準備好的 SQL server 型伺服器上：</span><span class="sxs-lookup"><span data-stu-id="2f6d4-119">For installing databases, **Install-CsDatabase** uses three primary methods for placing the databases onto the prepared SQL Server-based server:</span></span>

  - <span data-ttu-id="2f6d4-120">執行**安裝-** 不含 DatabasePaths 或 UseDefaultSqlPath 的 CsDatabase。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-120">Run **Install-CsDatabase** without DatabasePaths or UseDefaultSqlPath.</span></span> <span data-ttu-id="2f6d4-121">此 Cmdlet 使用內建演算法來判斷記錄和資料檔的最佳位置。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-121">The cmdlet uses a built in algorithm to determine the best placement for the log and data files.</span></span> <span data-ttu-id="2f6d4-122">此演算法只適用于獨立的 SQL Server 實現。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-122">The algorithm only works for stand-alone SQL Server implementations.</span></span>

  - <span data-ttu-id="2f6d4-123">使用 DatabasePaths 參數執行**安裝-CsDatabase** 。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-123">Run **Install-CsDatabase** with the DatabasePaths parameter.</span></span> <span data-ttu-id="2f6d4-124">如果定義 DatabasePaths 參數，則不會使用內建演算法來優化記錄和資料檔案位置。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-124">The built-in algorithm to optimize log and data file locations is not used if the DatabasePaths parameter is defined.</span></span> <span data-ttu-id="2f6d4-125">使用此參數可讓您定義將部署記錄及資料檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-125">Using this parameter allows you to define the locations where log and data files will be deployed.</span></span>

  - <span data-ttu-id="2f6d4-126">執行**安裝-CsDatabase**與 UseDefaultSqlPaths。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-126">Run **Install-CsDatabase** with UseDefaultSqlPaths.</span></span> <span data-ttu-id="2f6d4-127">這個選項不會使用內建演算法來優化記錄和資料檔案位置。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-127">This option does not use the built-in algorithm to optimize the log and data file locations.</span></span> <span data-ttu-id="2f6d4-128">根據 SQL Server 系統管理員設定的預設值來部署記錄和資料檔案。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-128">Log and data file are deployed according to the defaults set by the SQL Server administrator.</span></span> <span data-ttu-id="2f6d4-129">這些路徑通常是針對在 SQL Server 上自動記錄管理和資料檔案的目的而設定，且不與 Lync Server 2013 的設定相關聯。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-129">These paths are typically set for the purpose of automatic administration of log and data files on the SQL Server in advance, and are not associated with the setup of Lync Server 2013.</span></span>

  - <span data-ttu-id="2f6d4-130">DatabasePathMap 參數也可以用來明確指定每個資料庫及其各自記錄檔的位置。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-130">The DatabasePathMap parameter can also be used to explicitly specify a location for each database and its respective log file.</span></span>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a><span data-ttu-id="2f6d4-131">若要使用 Windows PowerShell Cmdlet 來設定 SQL Server 中央管理存放區</span><span class="sxs-lookup"><span data-stu-id="2f6d4-131">To use Windows PowerShell cmdlets to configure the SQL Server Central Management store</span></span>

1.  <span data-ttu-id="2f6d4-132">在任何電腦上，使用管理認證登入，在 SQL Server 服務器上建立資料庫。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-132">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="2f6d4-133">如需詳細資訊，請參閱[Lync server 2013 中的 SQL Server 部署許可權](lync-server-2013-deployment-permissions-for-sql-server.md)。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-133">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

2.  <span data-ttu-id="2f6d4-134">開啟 Lync Server 2013 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-134">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="2f6d4-135">如果您尚未調整 Windows PowerShell 的執行原則，您必須調整原則，以允許 Windows PowerShell 腳本執行。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-135">If you have not adjusted the execution policy for Windows PowerShell, you must adjust the policy to allow Windows PowerShell scripts to run.</span></span> <span data-ttu-id="2f6d4-136">如需詳細資訊，請參閱 "檢查執行原則[http://go.microsoft.com/fwlink/p/?linkId=203093](http://go.microsoft.com/fwlink/p/?linkid=203093)"。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-136">For details, see “Examining the Execution Policy” at [http://go.microsoft.com/fwlink/p/?linkId=203093](http://go.microsoft.com/fwlink/p/?linkid=203093).</span></span>

3.  <span data-ttu-id="2f6d4-137">使用**CsDatabase** Cmdlet 來安裝中央管理存放區。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-137">Use the **Install-CsDatabase** cmdlet to install the Central Management store.</span></span>
    
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
    > <span data-ttu-id="2f6d4-138">報表參數是選擇性的，但如果您正在記錄安裝程式，則會很有用。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-138">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

4.  <span data-ttu-id="2f6d4-139">**安裝-CsDatabase – DatabasePaths**可以使用最多六個路徑參數，每個都定義了在 SQL Server 資料和記錄檔位置中定義的磁碟機路徑。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-139">**Install-CsDatabase –DatabasePaths** can use up to six path parameters, each defining the paths for the drives as defined in SQL Server Data and Log File Placement.</span></span> <span data-ttu-id="2f6d4-140">根據 Lync Server 2013 中資料庫設定的邏輯規則，磁碟機會解析成兩個、四個或六個的 bucket。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-140">By the logical rules of the database configuration in Lync Server 2013, drives are parsed out into buckets of two, four, or six.</span></span> <span data-ttu-id="2f6d4-141">視您的 SQL Server 設定和 bucket 數而定，您將會提供兩個路徑、四個路徑或六個路徑。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-141">Depending on your SQL Server configuration and the number of buckets, you will supply two paths, four paths, or six paths.</span></span>
    
    <span data-ttu-id="2f6d4-142">如果您有三個磁片磁碟機，記錄會取得優先順序，並會在之後散佈資料檔案。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-142">If you have three drives, the log gets priority and the data files are distributed after.</span></span> <span data-ttu-id="2f6d4-143">以6個磁碟機為基礎的 SQL Server server 設定範例：</span><span class="sxs-lookup"><span data-stu-id="2f6d4-143">An example for a SQL Server-based server configured with six drives:</span></span>
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  <span data-ttu-id="2f6d4-144">資料庫安裝完成後，您可以關閉 Lync Server 2013 管理命令介面，或繼續安裝在拓撲建立器中定義的 Lync Server 2013 設定的資料庫。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-144">When the database installation completes, you can close Lync Server 2013 Management Shell or proceed to the installation of the Lync Server 2013 configured databases defined in Topology Builder.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a><span data-ttu-id="2f6d4-145">若要使用 Windows PowerShell Cmdlet 來設定 SQL Server 拓撲設定的資料庫</span><span class="sxs-lookup"><span data-stu-id="2f6d4-145">To use Windows PowerShell cmdlets to configure the SQL Server topology configured databases</span></span>

1.  <span data-ttu-id="2f6d4-146">若要安裝 Lync Server 2013 的 [拓撲建立器] 設定資料庫，Lync Server 2013 系統管理員必須發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-146">To install the Topology Builder configured databases for Lync Server 2013, the Lync Server 2013 administrator must publish the topology.</span></span> <span data-ttu-id="2f6d4-147">如需詳細資訊，請參閱在部署檔中[發佈 Lync Server 2013 中的拓撲](lync-server-2013-publish-the-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-147">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="2f6d4-148">在任何電腦上，使用管理認證登入，在 SQL Server 服務器上建立資料庫。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-148">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="2f6d4-149">請參閱[Lync server 2013 中 SQL Server 的部署許可權](lync-server-2013-deployment-permissions-for-sql-server.md)主題。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-149">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2f6d4-150">若要設定 SQL Server 的資料庫，請確定用於執行以下所述步驟的 SQL Server 管理員帳戶也是執行 SQL Server 並按住中央管理的伺服器上的系統管理員群組（或對等）的成員。伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-150">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="2f6d4-151">若要檢查是否有任何其他需要 SQL Server 資料庫安裝或設定的 Lync Server 2013 池，這一點尤為重要。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-151">This is especially important to check for any additional Lync Server 2013 pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="2f6d4-152">例如，如果您要部署第二個池（pool02），但中央管理伺服器角色是由 pool01 所擁有。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-152">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="2f6d4-153">SQL Server 系統管理員群組（或對等）在 SQL Server 型資料庫上都必須有許可權。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-153">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="2f6d4-154">開啟 Lync Server 2013 管理命令介面（如果尚未開啟的話）。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-154">Open Lync Server 2013 Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="2f6d4-155">使用**CsDatabase** Cmdlet 來安裝 [拓撲建立器] 設定的資料庫。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-155">Use the **Install-CsDatabase** cmdlet to install the Topology Builder configured databases.</span></span>
    
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
    > <span data-ttu-id="2f6d4-156">報表參數是選擇性的，但如果您正在記錄安裝程式，則會很有用。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-156">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

5.  <span data-ttu-id="2f6d4-157">資料庫安裝完成後，請關閉 Lync Server 2013 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-157">When the database installation completes, close Lync Server 2013 Management Shell.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a><span data-ttu-id="2f6d4-158">若要使用 Windows PowerShell Cmdlet 來使用 DatabasePathMap 參數設定 SQL Server 拓撲</span><span class="sxs-lookup"><span data-stu-id="2f6d4-158">To use Windows PowerShell cmdlets to configure the SQL Server topology using the DatabasePathMap parameter</span></span>

1.  <span data-ttu-id="2f6d4-159">若要安裝 Lync Server 2013 的資料庫，Lync Server 管理員必須根據預先定義的一組規則來建立路徑，並部署資料庫檔案和記錄檔案。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-159">To install databases for Lync Server 2013, the Lync Server administrator must create the paths and deploy the databases files and log files according to a predefined set of rules.</span></span>

2.  <span data-ttu-id="2f6d4-160">在任何電腦上，使用管理認證登入，在 SQL Server 服務器上建立資料庫。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-160">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="2f6d4-161">請參閱[Lync server 2013 中 SQL Server 的部署許可權](lync-server-2013-deployment-permissions-for-sql-server.md)主題。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-161">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2f6d4-162">若要設定 SQL Server 的資料庫，請確定用於執行以下所述步驟的 SQL Server 管理員帳戶也是執行 SQL Server 並按住中央管理的伺服器上的系統管理員群組（或對等）的成員。伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-162">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="2f6d4-163">若要檢查任何需要 SQL Server 資料庫安裝或設定的其他 Lync 伺服器池，這一點尤為重要。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-163">This is especially important to check for any additional Lync Server pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="2f6d4-164">例如，如果您要部署第二個池（pool02），但中央管理伺服器角色是由 pool01 所擁有。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-164">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="2f6d4-165">SQL Server 系統管理員群組（或對等）在 SQL Server 型資料庫上都必須有許可權。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-165">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="2f6d4-166">開啟 Lync Server 管理命令介面（如果尚未開啟的話）。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-166">Open Lync Server Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="2f6d4-167">使用**CsDatabase** Cmdlet 與 DatabasePathMap 參數和 PowerShell 雜湊表來安裝拓撲建立器設定的資料庫。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-167">Use the **Install-CsDatabase** cmdlet with the DatabasePathMap parameter and a PowerShell hash table to install the Topology Builder configured databases.</span></span>

5.  <span data-ttu-id="2f6d4-168">在範例程式碼中，您可以使用– DatabasePathMap 參數和定義的雜湊表，以精細的方式來判斷為資料庫定義的路徑，如下所示（這個範例針對\\所有的資料庫（.mdf）檔案使用 "c： CSData"，而\\[c： CSLogFiles] 則代表所有記錄（.ldf）檔案。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-168">In the example code, the paths defined for the databases can be determined in a granular manner by using the –DatabasePathMap parameter and a defined hash table as follows (the example uses “C:\\CSData” for all database (.mdf) files, and “C:\\CSLogFiles” for all log (.ldf) files.</span></span> <span data-ttu-id="2f6d4-169">您可以視安裝所需建立資料夾-CsDatabase）：</span><span class="sxs-lookup"><span data-stu-id="2f6d4-169">Folder will be created as needed by Install-CsDatabase):</span></span>
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
6.  <span data-ttu-id="2f6d4-170">因為資料庫和記錄檔案是在目的地資料庫伺服器上以其位置明確命名，所以您可以針對每個服務類型的實際資料庫和記錄位置定義特定位置。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-170">Because the database and log files are explicitly named with their location on the destination database server, you can define specific locations for each service type’s actual database and log location.</span></span> <span data-ttu-id="2f6d4-171">下列範例會將每個特定服務類型的資料庫放在不同磁片上，並將相關聯的記錄檔案放在另一個磁片上。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-171">The following example puts databases for each specific service type on separate disks, and associated log files on another.</span></span> <span data-ttu-id="2f6d4-172">例如：</span><span class="sxs-lookup"><span data-stu-id="2f6d4-172">For example:</span></span>
    
      - <span data-ttu-id="2f6d4-173">所有 RTC 資料庫都設為 "\\D： RTCDatabase"</span><span class="sxs-lookup"><span data-stu-id="2f6d4-173">All RTC databases to “D:\\RTCDatabase”</span></span>
    
      - <span data-ttu-id="2f6d4-174">所有 RTC 記錄檔案到 "E：\\RTCLogs"</span><span class="sxs-lookup"><span data-stu-id="2f6d4-174">All RTC log files to “E:\\RTCLogs”</span></span>
    
      - <span data-ttu-id="2f6d4-175">所有應用程式將資料庫儲存到 "\\F： CPSDatabases"</span><span class="sxs-lookup"><span data-stu-id="2f6d4-175">All application store databases to “F:\\CPSDatabases”</span></span>
    
      - <span data-ttu-id="2f6d4-176">所有應用程式商店記錄到 "G\\： CPSLogs"</span><span class="sxs-lookup"><span data-stu-id="2f6d4-176">All application store logs to “G:\\CPSLogs”</span></span>
    
      - <span data-ttu-id="2f6d4-177">所有回應群組將資料庫儲存到 "H\\： RGSDatabases"</span><span class="sxs-lookup"><span data-stu-id="2f6d4-177">All response group store databases to “H:\\RGSDatabases”</span></span>
    
      - <span data-ttu-id="2f6d4-178">所有回應群組商店記錄到「I：\\RGSLogs」</span><span class="sxs-lookup"><span data-stu-id="2f6d4-178">All response group store logs to “I:\\RGSLogs”</span></span>
    
      - <span data-ttu-id="2f6d4-179">所有通訊錄將資料庫儲存到 "J\\： ABSDatabases"</span><span class="sxs-lookup"><span data-stu-id="2f6d4-179">All address book store databases to “J:\\ABSDatabases”</span></span>
    
      - <span data-ttu-id="2f6d4-180">所有通訊錄將記錄檔儲存到 "K\\： ABSLogs"</span><span class="sxs-lookup"><span data-stu-id="2f6d4-180">All address book store log files to “K:\\ABSLogs”</span></span>
    
      - <span data-ttu-id="2f6d4-181">所有封存儲存資料庫到 "L：\\ArchivingDatabases"</span><span class="sxs-lookup"><span data-stu-id="2f6d4-181">All archiving store databases to “L:\\ArchivingDatabases”</span></span>
    
      - <span data-ttu-id="2f6d4-182">所有封存存放區記錄到 "M\\： ArchivingLogs"</span><span class="sxs-lookup"><span data-stu-id="2f6d4-182">All archiving store logs to “M:\\ArchivingLogs”</span></span>
    
      - <span data-ttu-id="2f6d4-183">所有監視商店資料庫到 "N：\\MonitoringDatabases"</span><span class="sxs-lookup"><span data-stu-id="2f6d4-183">All monitoring store databases to “N:\\MonitoringDatabases”</span></span>
    
      - <span data-ttu-id="2f6d4-184">所有監視商店記錄檔案到 "O：\\MonitoringLogfiles"</span><span class="sxs-lookup"><span data-stu-id="2f6d4-184">All monitoring store log files to “O:\\MonitoringLogfiles”</span></span>
    
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
    
    <span data-ttu-id="2f6d4-185">您可以使用– DatabasePathMap 參數定義任何邏輯磁片磁碟機字母對應，為您的 SQL Server 效能和位置需求提供最佳解決方案。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-185">Using the –DatabasePathMap parameter, you can define any logical drive letter mapping combination that provides the best solution for your SQL Server performance and placement requirements.</span></span>

<span data-ttu-id="2f6d4-186">如果您使用**DatabasePathMap**方法來設定資料庫資料檔和記錄檔案，則在使用拓撲建立器時，您必須稍加變更您的標準程式。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-186">If you configure your database data files and log files by using the **DatabasePathMap** method, you will need to make a slight change to your normal process when using Topology Builder.</span></span> <span data-ttu-id="2f6d4-187">通常，您會定義拓撲選項、發佈拓撲，以及選擇部署資料庫選項。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-187">Typically, you would define your topology choices, publish the topology, and choose to deploy the database selections.</span></span>

<span data-ttu-id="2f6d4-188">如果您已使用**DatabasePathMap** ，就表示您已經完成拓撲建立程式的第三個部分。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-188">If you have used **DatabasePathMap** you have already accomplished the third part of the Topology Builder process.</span></span> <span data-ttu-id="2f6d4-189">如果您在執行拓撲建立器之前有完全配置的資料庫伺服器，您仍然可以定義所有伺服器角色和選項，但不需選取此選項即可建立資料庫。</span><span class="sxs-lookup"><span data-stu-id="2f6d4-189">In the case of having a completely configured database server in advance of running Topology Builder, you would still define all of your server roles and options, but deselect the option to create the databases.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

