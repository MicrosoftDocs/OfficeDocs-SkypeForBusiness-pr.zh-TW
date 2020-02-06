---
title: 部署商務用 Skype Server 的通話品質儀表板
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 摘要：瞭解通話品質儀表板的部署程式。 [通話品質儀表板] 是商務用 Skype Server 的工具。
ms.openlocfilehash: ccfb19bf8069bf72d52d7399b012d81af72e4110
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816852"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a><span data-ttu-id="5ac10-104">部署商務用 Skype Server 的通話品質儀表板</span><span class="sxs-lookup"><span data-stu-id="5ac10-104">Deploy Call Quality Dashboard for Skype for Business Server</span></span>
 
<span data-ttu-id="5ac10-105">**摘要：** 瞭解通話品質儀表板的部署程式。</span><span class="sxs-lookup"><span data-stu-id="5ac10-105">**Summary:** Learn about the deployment process for Call Quality Dashboard.</span></span> <span data-ttu-id="5ac10-106">[通話品質儀表板] 是商務用 Skype Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="5ac10-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
## <a name="deployment-overview"></a><span data-ttu-id="5ac10-107">部署概述</span><span class="sxs-lookup"><span data-stu-id="5ac10-107">Deployment Overview</span></span>

<span data-ttu-id="5ac10-108">通話品質儀表板（CQD）包含三個主要元件：</span><span class="sxs-lookup"><span data-stu-id="5ac10-108">Call Quality Dashboard (CQD) consists of three major components:</span></span>
  
- <span data-ttu-id="5ac10-109">[封存**資料庫**]，其中會複製並儲存 [經驗] （QoE）資料的品質。</span><span class="sxs-lookup"><span data-stu-id="5ac10-109">**Archive Database**, where the Quality of Experience (QoE) data is replicated and stored.</span></span>
    
- <span data-ttu-id="5ac10-110">**多維資料集**，其中 QoE 封存資料庫的資料會根據優化和快速存取進行匯總。</span><span class="sxs-lookup"><span data-stu-id="5ac10-110">**Cube**, where data from QoE Archive database is aggregated for optimized and fast access.</span></span>
    
- <span data-ttu-id="5ac10-111">**入口網站**，使用者可以在此輕鬆地查詢及視覺化 QoE 資料。</span><span class="sxs-lookup"><span data-stu-id="5ac10-111">**Portal**, where users can easily query and visualize QoE data.</span></span>
    
![CQD 元件](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
<span data-ttu-id="5ac10-113">QoE 封存的設定程式會涉及建立 QoE 封存資料庫、部署 SQL Server 儲存程式，以將來源 QoE 指標資料庫中的資料移至 QoE 封存資料庫，並設定 SQL Server 代理程式作業來執行已儲存的檔案定期間隔的程式。</span><span class="sxs-lookup"><span data-stu-id="5ac10-113">The setup process for QoE Archive involves creating the QoE Archive database, deploying a SQL Server stored procedure that will move the data from the source QoE Metrics database into QoE Archive database, and setting up the SQL Server Agent job to execute the stored procedure at a regular interval.</span></span> 
  
<span data-ttu-id="5ac10-114">多維資料集部署會取得使用者在 QoE 封存所在位置的資訊、部署立方體，並設定一般的 SQL Server 代理程式作業，以便定期重新整理立方體。</span><span class="sxs-lookup"><span data-stu-id="5ac10-114">Cube deployment gets information from the user on where the QoE Archive is located, deploys the cube, and sets up a regular SQL Server agent job that will refresh the cube at a regular interval.</span></span>
  
<span data-ttu-id="5ac10-115">[入口網站安裝] 會建立儲存 CQD 使用者與每個使用者的報表/查詢對應的知識庫資料庫。</span><span class="sxs-lookup"><span data-stu-id="5ac10-115">Portal install creates a Repository database that stores the mapping of CQD users to each user's reports/queries.</span></span> <span data-ttu-id="5ac10-116">接著，它會設定 IIS web 應用程式，讓使用者可以查看預先定義的報告集，以及自訂和建立自己的查詢，以視覺化立方體中的資料。</span><span class="sxs-lookup"><span data-stu-id="5ac10-116">It then sets up an IIS web application which is the dashboard where users can see a pre-defined set of reports as well as customize and create their own queries to visualize data from the cube.</span></span> <span data-ttu-id="5ac10-117">入口網站安裝會建立兩個額外的 web 應用程式，讓使用者以程式設計方式存取儲存庫和立方體。</span><span class="sxs-lookup"><span data-stu-id="5ac10-117">The portal install creates two additional web applications that exposes APIs for users to programmatically access the repository and the cube.</span></span> <span data-ttu-id="5ac10-118">（這些 Api 也是由儀表板內部使用。）</span><span class="sxs-lookup"><span data-stu-id="5ac10-118">(These APIs are used internally by the dashboard as well.)</span></span>
  

|<span data-ttu-id="5ac10-119">**分**</span><span class="sxs-lookup"><span data-stu-id="5ac10-119">**Phase**</span></span>|<span data-ttu-id="5ac10-120">**步驟**</span><span class="sxs-lookup"><span data-stu-id="5ac10-120">**Steps**</span></span>|<span data-ttu-id="5ac10-121">**角色與群組成員資格**</span><span class="sxs-lookup"><span data-stu-id="5ac10-121">**Roles and group membership**</span></span>|<span data-ttu-id="5ac10-122">**文件**</span><span class="sxs-lookup"><span data-stu-id="5ac10-122">**Documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5ac10-123">安裝必備的硬體和軟體。</span><span class="sxs-lookup"><span data-stu-id="5ac10-123">Install prerequisite hardware and software.</span></span>  <br/> |<span data-ttu-id="5ac10-124">決定 CQD 設定，然後選擇要執行安裝的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="5ac10-124">Decide on the CQD configuration, and choose a SQL Server from which to perform the install.</span></span>  <br/> |<span data-ttu-id="5ac10-125">屬於本機管理員群組成員的網域使用者。</span><span class="sxs-lookup"><span data-stu-id="5ac10-125">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="5ac10-126">部署檔中的「安裝前需求」一節。</span><span class="sxs-lookup"><span data-stu-id="5ac10-126">"Pre-install Requirements" section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="5ac10-127">安裝 CQD。</span><span class="sxs-lookup"><span data-stu-id="5ac10-127">Install CQD.</span></span>  <br/> |<span data-ttu-id="5ac10-128">在部署檔後執行 MSI。</span><span class="sxs-lookup"><span data-stu-id="5ac10-128">Run the MSI following the deployment document.</span></span>  <br/> |<span data-ttu-id="5ac10-129">若要執行設定，安裝帳戶必須是本機系統管理員群組成員的網域使用者，以及在監視伺服器上擁有 QoE 度量值資料庫的讀取權限。</span><span class="sxs-lookup"><span data-stu-id="5ac10-129">To perform the setup, the installing account must be a domain user who is a member of the local administrators group and have read access to QoE Metrics database on the Monitoring Server.</span></span>  <br/> |<span data-ttu-id="5ac10-130">[部署] 檔中的 [帳戶和部署步驟] 區段。</span><span class="sxs-lookup"><span data-stu-id="5ac10-130">"Accounts and Deployment Steps" sections in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="5ac10-131">授與使用者存取權。</span><span class="sxs-lookup"><span data-stu-id="5ac10-131">Grant user access.</span></span>  <br/> |<span data-ttu-id="5ac10-132">若要管理使用者對入口網站的授權，我們建議使用 IIS 7.0 中引入的 URL 授權。</span><span class="sxs-lookup"><span data-stu-id="5ac10-132">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="5ac10-133">如需詳細資訊，請參閱[瞭解 IIS 7.0 URL 授權](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)。</span><span class="sxs-lookup"><span data-stu-id="5ac10-133">For more information, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>  <br/> |<span data-ttu-id="5ac10-134">屬於本機管理員群組成員的網域使用者。</span><span class="sxs-lookup"><span data-stu-id="5ac10-134">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="5ac10-135">在部署檔中管理入口網站區段的使用者存取權。</span><span class="sxs-lookup"><span data-stu-id="5ac10-135">Managing User Access for the Portal section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="5ac10-136">[選用]：提供子網對應資訊。</span><span class="sxs-lookup"><span data-stu-id="5ac10-136">Optional: Provide subnet mapping information.</span></span>  <br/> |<span data-ttu-id="5ac10-137">在 QoE 封存資料庫中填入網路及建立對應資料表。</span><span class="sxs-lookup"><span data-stu-id="5ac10-137">Populate network and building mapping tables in QoE Archive database.</span></span>  <br/> |<span data-ttu-id="5ac10-138">具有 QoE 封存資料庫寫入存取權的帳戶。</span><span class="sxs-lookup"><span data-stu-id="5ac10-138">An account with write access to the QoE Archive database.</span></span>  <br/> |<span data-ttu-id="5ac10-139">使用者檔中的「提供子網資訊」一節。</span><span class="sxs-lookup"><span data-stu-id="5ac10-139">"Supplying Subnet Information" section in the user documentation.</span></span>  <br/> |
   


<span data-ttu-id="5ac10-140">部署通話品質儀表板涉及設定基礎結構及安裝軟體。</span><span class="sxs-lookup"><span data-stu-id="5ac10-140">Deployment of Call Quality Dashboard involves setting up the infrastructure and installing the software.</span></span> <span data-ttu-id="5ac10-141">下列程式會概述此程式。</span><span class="sxs-lookup"><span data-stu-id="5ac10-141">The following procedure outlines the process.</span></span>
  
## <a name="deployment-steps"></a><span data-ttu-id="5ac10-142">部署步驟</span><span class="sxs-lookup"><span data-stu-id="5ac10-142">Deployment Steps</span></span>

1. <span data-ttu-id="5ac10-143">將 CallQualityDashboard 複製到要安裝 CQD 封存資料庫元件的電腦（這是安裝了 SQL Server 的電腦）。</span><span class="sxs-lookup"><span data-stu-id="5ac10-143">Copy the CallQualityDashboard.msi to the machine where the archive database component of CQD is to be installed (this is the machine that has SQL Server installed).</span></span> 
    
2. <span data-ttu-id="5ac10-144">執行 MSI （Windows 會提示您使用系統管理員許可權執行）。</span><span class="sxs-lookup"><span data-stu-id="5ac10-144">Execute the MSI (Windows will prompt to run with administrator privilege, do so).</span></span> 
    
3. <span data-ttu-id="5ac10-145">接受 EULA。</span><span class="sxs-lookup"><span data-stu-id="5ac10-145">Accept the EULA.</span></span>
    
4. <span data-ttu-id="5ac10-146">選取與通話品質儀表板元件相關的檔案所在的目的地資料夾，或接受預設位置。</span><span class="sxs-lookup"><span data-stu-id="5ac10-146">Select the destination folder where files related to Call Quality Dashboard components will be located or accept the default location.</span></span>
    
5. <span data-ttu-id="5ac10-147">選取 [所有功能]。</span><span class="sxs-lookup"><span data-stu-id="5ac10-147">Select all features.</span></span>
    
6. <span data-ttu-id="5ac10-148">在 [QoE 封存設定] 頁面上，提供下列資訊：</span><span class="sxs-lookup"><span data-stu-id="5ac10-148">At the QoE Archive Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="5ac10-149">**QoE 度量值 SQL Server：** QoE 度量資料庫所在位置的 SQL Server 實例名稱（這將是資料來源）。</span><span class="sxs-lookup"><span data-stu-id="5ac10-149">**QoE Metrics SQL Server:** SQL Server instance name for where the QoE Metrics DB is located (this will be the data source).</span></span>
    
   - <span data-ttu-id="5ac10-150">**QoE 封存 SQL Server 名稱：** 這是唯讀欄位，且已修正本機電腦的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="5ac10-150">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="5ac10-151">封存資料庫只能安裝在本機電腦上。</span><span class="sxs-lookup"><span data-stu-id="5ac10-151">Archive DB can be installed only on the local machine.</span></span>
    
   - <span data-ttu-id="5ac10-152">**QoE 封存 SQL Server 實例：** 要在其中建立封存資料庫的本機 SQL Server 實例名稱。</span><span class="sxs-lookup"><span data-stu-id="5ac10-152">**QoE Archive SQL Server Instance:** A local SQL Server instance name for where the Archive DB is to be created.</span></span> <span data-ttu-id="5ac10-153">若要使用預設的 SQL Server 實例，請將此欄位留白。</span><span class="sxs-lookup"><span data-stu-id="5ac10-153">To use a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="5ac10-154">若要使用命名的 SQL Server 實例，請指定實例名稱（例如，在 ""\"之後的名稱）。</span><span class="sxs-lookup"><span data-stu-id="5ac10-154">To use a named SQL Server instance, specify the instance name (e.g. the name after the "\").</span></span>
    
   - <span data-ttu-id="5ac10-155">**QoE 封存資料庫：** 根據預設，此選項會設定為 [建立新資料庫]。</span><span class="sxs-lookup"><span data-stu-id="5ac10-155">**QoE Archive Database:** By default, this option is set to "Create new database".</span></span> <span data-ttu-id="5ac10-156">由於不支援封存資料庫升級，因此如果現有封存資料庫的架構與要安裝的組建相同，就可以使用 [使用現有的資料庫] 選項的唯一情況。</span><span class="sxs-lookup"><span data-stu-id="5ac10-156">Since Archive DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Archive database has the same schema as the build to be installed.</span></span>
    
   - <span data-ttu-id="5ac10-157">**資料庫檔案目錄：** 存放封存資料庫之資料庫檔案（.mdf 和 .ldf）的路徑。</span><span class="sxs-lookup"><span data-stu-id="5ac10-157">**Database File Directory:** Path to where the database files (.mdf and .ldf) for the Archive DB should be placed.</span></span> <span data-ttu-id="5ac10-158">這應該是與作業系統分開的磁片磁碟機（建議的硬體設定中的 HDD2）。</span><span class="sxs-lookup"><span data-stu-id="5ac10-158">This should be on a drive (HDD2 in the recommended hardware configuration) separate from the OS.</span></span> <span data-ttu-id="5ac10-159">請注意，因為檔案名已在安裝中修正，所以建議您不要使用沒有檔案的空白目錄。</span><span class="sxs-lookup"><span data-stu-id="5ac10-159">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="5ac10-160">**使用多個分區：** 預設值會設定為 [多個分區]，這需要商務智慧版本或企業版的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="5ac10-160">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="5ac10-161">針對標準版，請選取 [單一分區] 選項。</span><span class="sxs-lookup"><span data-stu-id="5ac10-161">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="5ac10-162">請注意，如果使用單一分區，cube 處理效能可能會受到影響。</span><span class="sxs-lookup"><span data-stu-id="5ac10-162">Note that cube processing performance may be impacted if Single Partition is used.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="5ac10-163">安裝程式完成後，就無法變更 [使用多重分區的選取範圍] 選項。</span><span class="sxs-lookup"><span data-stu-id="5ac10-163">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="5ac10-164">若要變更它，需要先卸載立方體功能，然後使用 [控制台] 中的 [變更] 選項重新安裝。</span><span class="sxs-lookup"><span data-stu-id="5ac10-164">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span> 
  
   - <span data-ttu-id="5ac10-165">[分區] 檔案**目錄：** 要放置 QoE 封存資料庫分區的路徑。</span><span class="sxs-lookup"><span data-stu-id="5ac10-165">**Partition File Directory:** Path to where the partitions for the QoE Archive database should be placed.</span></span> <span data-ttu-id="5ac10-166">這應該是在磁碟機上（建議的硬體設定中的 HDD3），與 OS 磁片磁碟機及 SQL 資料庫記錄檔磁碟機不同。</span><span class="sxs-lookup"><span data-stu-id="5ac10-166">This should be on a drive (HDD3 in the recommended hardware configuration) separate from the OS drive and SQL database log files drive.</span></span> <span data-ttu-id="5ac10-167">請注意，因為檔案名已在安裝中修正，所以建議您不要使用沒有檔案的空白目錄。</span><span class="sxs-lookup"><span data-stu-id="5ac10-167">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="5ac10-168">**SQL 代理作業使用者-使用者名稱&amp;密碼：** 網域服務帳戶名稱和密碼（遮罩），會用來執行 SQL Server 代理作業的「QoE 封存資料」步驟（這會執行儲存程式，以將資料從 QoE 量度 DB 提取到封存資料庫），因此，此帳戶必須具備對 QoE 公制 DB 的讀取存取權，如 [帳戶] 區段中所述。</span><span class="sxs-lookup"><span data-stu-id="5ac10-168">**SQL Agent Job User - User Name &amp; Password:** Domain service account name and password (masked) that will be used to run the "QoE Archive Data" step of the SQL Server Agent job (which will run the stored procedure to fetch data from QoE Metrics DB into Archive DB, so this account must have read access to QoE Metrics DB, as indicated under Accounts section.</span></span> <span data-ttu-id="5ac10-169">這個帳戶也需要在 QoE 封存 SQL Server 實例中擁有登入。</span><span class="sxs-lookup"><span data-stu-id="5ac10-169">This account also needs to have a login in the QoE Archive SQL Server Instance).</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="5ac10-170">運行 SQL Server 實例的帳戶（例如 NT SERVICE\MSSQLSERVER）必須具備上述所給之目錄的存取/許可權，才能成功安裝。</span><span class="sxs-lookup"><span data-stu-id="5ac10-170">The account that the SQL Server instance is running under, such as NT SERVICE\MSSQLSERVER, must have access/permission to the directories given above for the installation to succeed.</span></span> <span data-ttu-id="5ac10-171">如需詳細資訊，請參閱[設定資料庫引擎存取的檔案系統許可權](https://msdn.microsoft.com/en-us/library/jj219062%28v=sql.110%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5ac10-171">For details, see [Configure File System Permissions for Database Engine Access](https://msdn.microsoft.com/en-us/library/jj219062%28v=sql.110%29.aspx)</span></span>
  
7. <span data-ttu-id="5ac10-172">按一下 [下一步] 時，安裝程式將執行必要的檢查，並在遇到任何問題時報告。</span><span class="sxs-lookup"><span data-stu-id="5ac10-172">Upon clicking next, the installer will perform pre-requisite checks and report if any issues are encountered.</span></span> <span data-ttu-id="5ac10-173">當所有的先決條件檢查完成時，安裝程式會移至 [立方體設定] 頁面。</span><span class="sxs-lookup"><span data-stu-id="5ac10-173">When all pre-requisite checks pass, the installer will go to the Cube Configuration page.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="5ac10-174">如果安裝程式顯示警告訊息，指出 QoE 封存 SQL Server 實例的 SQL Server 代理服務目前未執行，則可以繼續安裝，但請確定 SQL Agent 服務正在執行，並將啟動類型設定為[自動]，讓排程的作業執行。</span><span class="sxs-lookup"><span data-stu-id="5ac10-174">If the installer shows a warning message that the SQL Server Agent service for the QoE Archive SQL Server instance is currently not running, installation can proceed, but post installation please make sure that SQL Agent service is running and set the Startup type to Automatic so that the scheduled Job runs.</span></span> 
  
8. <span data-ttu-id="5ac10-175">在 [立方體設定] 頁面上，提供下列資訊：</span><span class="sxs-lookup"><span data-stu-id="5ac10-175">At Cube Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="5ac10-176">**QoE 封存 SQL Server 名稱：** 這是唯讀欄位，且已修正本機電腦的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="5ac10-176">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="5ac10-177">只能從擁有 QoE 封存資料庫的電腦（注意）安裝 Cube。</span><span class="sxs-lookup"><span data-stu-id="5ac10-177">Cube can be installed only from the machine that has QoE Archive database (Note.</span></span> <span data-ttu-id="5ac10-178">立方體本身可能已安裝在遠端電腦上。</span><span class="sxs-lookup"><span data-stu-id="5ac10-178">Cube itself may be installed on a remote machine.</span></span> <span data-ttu-id="5ac10-179">請參閱下圖）</span><span class="sxs-lookup"><span data-stu-id="5ac10-179">See below)</span></span>
    
   - <span data-ttu-id="5ac10-180">**QoE 封存 SQL Server 實例：** QoE 封存資料庫所在位置的 SQL Server 實例名稱。</span><span class="sxs-lookup"><span data-stu-id="5ac10-180">**QoE Archive SQL Server Instance:** SQL Server instance name for where the QoE Archive DB is located.</span></span> <span data-ttu-id="5ac10-181">若要指定預設的 SQL Server 實例，請將此欄位留白。</span><span class="sxs-lookup"><span data-stu-id="5ac10-181">To specify a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="5ac10-182">若要指定命名的 SQL Server 實例，請輸入實例名稱（例如，在 ""\"之後的名稱）。</span><span class="sxs-lookup"><span data-stu-id="5ac10-182">To specify a named SQL Server instance, enter the instance name (e.g. the name after the "\").</span></span> <span data-ttu-id="5ac10-183">如果已選取 [QoE 封存元件] 進行安裝，此欄位將會預先填入 [QoE 封存設定] 頁面上提供的值。</span><span class="sxs-lookup"><span data-stu-id="5ac10-183">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
   - <span data-ttu-id="5ac10-184">**立方體分析伺服器：** 要在其中建立多維資料集的 SQL Server Analysis Services 實例名稱。</span><span class="sxs-lookup"><span data-stu-id="5ac10-184">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is to be created.</span></span> <span data-ttu-id="5ac10-185">這可以是不同的電腦，但安裝使用者必須是目標 SQL Server Analysis Service 實例之伺服器系統管理員的成員。</span><span class="sxs-lookup"><span data-stu-id="5ac10-185">This can be a different machine but the installing user has to be a member of Server administrators of the target SQL Server Analysis Service instance.</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="5ac10-186">如需有關設定 Analysis Services Server 系統管理員許可權的詳細資訊，請參閱[授與伺服器管理員許可權（Analysis Services）](https://msdn.microsoft.com/en-us/library/ms174561.aspx)</span><span class="sxs-lookup"><span data-stu-id="5ac10-186">For more information about configuring Analysis Services Server Administrator Permissions, see [Grant Server Administrator Permissions (Analysis Services)](https://msdn.microsoft.com/en-us/library/ms174561.aspx)</span></span>
  
   - <span data-ttu-id="5ac10-187">**使用多個分區：** 預設值會設定為 [多個分區]，這需要商務智慧版本或企業版的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="5ac10-187">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="5ac10-188">針對標準版，請選取 [單一分區] 選項。</span><span class="sxs-lookup"><span data-stu-id="5ac10-188">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="5ac10-189">請注意，如果使用單一分區，cube 處理效能可能會受到影響。</span><span class="sxs-lookup"><span data-stu-id="5ac10-189">Note that cube processing performance may be impacted if Single Partition is used .</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="5ac10-190">安裝程式完成後，就無法變更 [使用多重分區的選取範圍] 選項。</span><span class="sxs-lookup"><span data-stu-id="5ac10-190">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="5ac10-191">若要變更它，需要先卸載立方體功能，然後使用 [控制台] 中的 [變更] 選項重新安裝。</span><span class="sxs-lookup"><span data-stu-id="5ac10-191">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span>
  
   - <span data-ttu-id="5ac10-192">**立方體使用者-使用者名稱&amp;密碼：** 將觸發 cube 處理的網域服務帳戶名稱和密碼（遮罩）。</span><span class="sxs-lookup"><span data-stu-id="5ac10-192">**Cube User - User Name &amp; Password:** Domain service account name and password (masked) that will trigger the cube processing.</span></span> <span data-ttu-id="5ac10-193">如果您已選取安裝的 QoE 封存元件，此欄位將會預先填入 SQL 代理作業使用者的 [封存設定] 頁面上提供的值，但我們建議您指定不同的網域服務帳戶，以便讓安裝程式能夠授與所需的許可權最低。</span><span class="sxs-lookup"><span data-stu-id="5ac10-193">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the Archive Configuration page for the SQL Agent Job User, but we recommend specifying a different domain service account so that Setup can grant the least required privilege to it.</span></span>
    
9. <span data-ttu-id="5ac10-194">按一下 [下一步] 時，將會執行另一輪驗證，且會報告任何問題。</span><span class="sxs-lookup"><span data-stu-id="5ac10-194">When clicking next, another round of validation will be performed and any issue will be reported.</span></span> <span data-ttu-id="5ac10-195">成功完成驗證之後，安裝程式會移至入口網站設定頁面。</span><span class="sxs-lookup"><span data-stu-id="5ac10-195">Upon successful completion of the validation, the installer will go to the Portal Configuration page.</span></span> 
    
10. <span data-ttu-id="5ac10-196">在入口網站設定頁面上，提供下列資訊：</span><span class="sxs-lookup"><span data-stu-id="5ac10-196">At Portal Configuration page, provide the following information:</span></span>
    
    - <span data-ttu-id="5ac10-197">**QoE 封存 SQL Server：** QoE 封存資料庫所在位置的 SQL Server 實例名稱。</span><span class="sxs-lookup"><span data-stu-id="5ac10-197">**QoE Archive SQL Server:** SQL Server instance name for where the QoE Archive database is located.</span></span> <span data-ttu-id="5ac10-198">請注意，與 [QoE 封存配置] 頁面和 [立方體設定] 頁面不同，電腦名稱稱並未修正且必須提供。</span><span class="sxs-lookup"><span data-stu-id="5ac10-198">Note that unlike the QoE Archive Configuration page and the Cube Configuration page, the machine name is not fixed and must be provided.</span></span> <span data-ttu-id="5ac10-199">如果已選取 [QoE 封存元件] 進行安裝，此欄位將會預先填入 [QoE 封存設定] 頁面上提供的值。</span><span class="sxs-lookup"><span data-stu-id="5ac10-199">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
    - <span data-ttu-id="5ac10-200">**立方體分析伺服器：** 多維資料集所在位置的 SQL Server Analysis 服務實例名稱。</span><span class="sxs-lookup"><span data-stu-id="5ac10-200">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is located.</span></span> <span data-ttu-id="5ac10-201">如果已為安裝選取 [Cube 元件]，此欄位將會預先填入 [Cube 設定] 頁面上提供的值。</span><span class="sxs-lookup"><span data-stu-id="5ac10-201">If Cube component was selected for the install, this field will be pre-populated with the value provided on the Cube Configuration page.</span></span>
    
    - <span data-ttu-id="5ac10-202">**知識庫 SQL Server：** 要建立知識庫資料庫的 SQL Server 實例名稱。</span><span class="sxs-lookup"><span data-stu-id="5ac10-202">**Repository SQL Server:** SQL Server instance name where the Repository database is to be created.</span></span> <span data-ttu-id="5ac10-203">如果 QoE 封存資料庫所在位置的 SQL Server 實例名稱是在設定（在其他元件中）之前提供，此欄位將會預先填入 QoE 封存資料庫 SQL Server 實例名稱。</span><span class="sxs-lookup"><span data-stu-id="5ac10-203">If the SQL Server instance name for where the QoE Archive database is located has been provided earlier in the setup (in other components), this field will be pre-populated with the QoE Archive DB SQL Server instance name.</span></span> <span data-ttu-id="5ac10-204">這可以是任何 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="5ac10-204">This can be any SQL Server instance.</span></span>
    
    - <span data-ttu-id="5ac10-205">**知識庫資料庫：** 根據預設，此選項會設定為 [建立新資料庫]。</span><span class="sxs-lookup"><span data-stu-id="5ac10-205">**Repository Database:** By default the option is set to "Create new database".</span></span> <span data-ttu-id="5ac10-206">由於知識庫 DB 升級不受支援，因此，使用 [使用現有的資料庫] 選項的唯一情況是，如果現有的知識庫資料庫的架構與您要安裝的組建相同。</span><span class="sxs-lookup"><span data-stu-id="5ac10-206">Since Repository DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Repository DB has the same schema as the build to be installed.</span></span>
    
    - <span data-ttu-id="5ac10-207">**IIS 應用程式池使用者-使用者&amp;名稱密碼：** IIS 應用程式池應該在其下執行的帳戶。</span><span class="sxs-lookup"><span data-stu-id="5ac10-207">**IIS App Pool User - User Name &amp; Password:** The account that the IIS application pool should execute under.</span></span> <span data-ttu-id="5ac10-208">如果已選取內建的系統帳戶，[使用者名稱] 和 [密碼] 欄位就會呈現灰色。</span><span class="sxs-lookup"><span data-stu-id="5ac10-208">The User Name and Password fields will be grayed out if built-in system accounts are selected.</span></span> <span data-ttu-id="5ac10-209">只有在下拉式方塊中選取了 [其他] 時，才會啟用這些欄位，讓使用者可以輸入網域服務帳戶資訊。</span><span class="sxs-lookup"><span data-stu-id="5ac10-209">These fields will only be enabled if "Other" is selected from the drop down box so the user can enter the domain service account information.</span></span>
    
11. <span data-ttu-id="5ac10-210">按一下 [下一步] 時，將會完成最後一輪驗證，以確保使用所提供的認證和電腦上提供的 IIS 來存取 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="5ac10-210">When clicking next, the final round of validation will be done to ensure that the SQL Server instances are accessible using the credentials provided and that IIS is available on the machine.</span></span> <span data-ttu-id="5ac10-211">成功完成驗證之後，安裝程式將會繼續進行設定。</span><span class="sxs-lookup"><span data-stu-id="5ac10-211">Upon successful completion of the validation, the installer will proceed with the setup.</span></span> 
    
<span data-ttu-id="5ac10-212">安裝程式完成後，最可能的原因是 SQL Server 代理程式作業將在進行中，執行 QoE 資料的初始載入和 cube 處理。</span><span class="sxs-lookup"><span data-stu-id="5ac10-212">When the installer is done, most likely the SQL Server Agent job will be in progress, doing the initial load of the QoE data and the cube processing.</span></span> <span data-ttu-id="5ac10-213">根據 QoE 中的資料量，入口網站將沒有可供查看的資料。</span><span class="sxs-lookup"><span data-stu-id="5ac10-213">Depending on the amount of data in QoE, the portal will not have data available for viewing yet.</span></span> <span data-ttu-id="5ac10-214">若要查看資料載入與 cube 處理的狀態，請移至`http://<machinename>/CQD/#/Health`。</span><span class="sxs-lookup"><span data-stu-id="5ac10-214">To check on the status of the data load and cube processing, go to  `http://<machinename>/CQD/#/Health`.</span></span> 
> [!NOTE]
> <span data-ttu-id="5ac10-215">請注意，檢查下載 cube 處理狀態的 URL 會區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="5ac10-215">Note that the URL for checking the status of the download cube processing is case sensitive.</span></span> <span data-ttu-id="5ac10-216">如果您輸入「健康情況」，URL 將無法運作。</span><span class="sxs-lookup"><span data-stu-id="5ac10-216">If you enter 'health' the URL will not work.</span></span> <span data-ttu-id="5ac10-217">您必須在 URL 結尾處輸入 "Health"，並加上大寫的 H。</span><span class="sxs-lookup"><span data-stu-id="5ac10-217">You must enter 'Health' at the end of the URL with a capital H.</span></span> 
  
<span data-ttu-id="5ac10-218">如果啟用 [偵錯模式]，就會顯示詳細的記錄訊息。</span><span class="sxs-lookup"><span data-stu-id="5ac10-218">Detailed log messages will be shown if debug mode is enabled.</span></span> <span data-ttu-id="5ac10-219">若要啟用 [偵錯模式]，請移至 **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config**，並更新下列行，以將此值設定為**True**：</span><span class="sxs-lookup"><span data-stu-id="5ac10-219">To enable debug mode, go to **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config**, and update the following line so the value is set to **True**:</span></span>

```
<add key="QoEDataLib.DebugMode" value="True" /> 
```

<span data-ttu-id="5ac10-220">您可以透過存取主要入口網站`http://<machinename>/CQD`頁面。</span><span class="sxs-lookup"><span data-stu-id="5ac10-220">The main portal page is accessible via  `http://<machinename>/CQD`.</span></span> 
## <a name="managing-user-access-for-the-portal"></a><span data-ttu-id="5ac10-221">管理入口網站的使用者存取權</span><span class="sxs-lookup"><span data-stu-id="5ac10-221">Managing User Access for the Portal</span></span>

<span data-ttu-id="5ac10-222">若要管理使用者對入口網站的授權，我們建議使用 IIS 7.0 中引入的 URL 授權。</span><span class="sxs-lookup"><span data-stu-id="5ac10-222">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="5ac10-223">如需有關 IIS 安全性的詳細資訊，請參閱[瞭解 iis 7.0 URL 授權](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)。</span><span class="sxs-lookup"><span data-stu-id="5ac10-223">For more information on IIS security, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>
  
<span data-ttu-id="5ac10-224">任何網站或 web 應用程式都會繼承針對整個 IIS 所設定的預設 URL 授權，通常是「允許所有使用者」。</span><span class="sxs-lookup"><span data-stu-id="5ac10-224">Any web site or web application inherit the default URL Authorization configured for the entire IIS, which is typically "Allow All Users".</span></span> <span data-ttu-id="5ac10-225">如果存取入口網站需要更嚴格的限制，系統管理員可以編輯「授權規則」，只授與特定使用者群組的存取權。</span><span class="sxs-lookup"><span data-stu-id="5ac10-225">If access to the Portal needs to be more restrictive, then administrators can grant access to only the specific group of users by editing the "Authorization Rules".</span></span>
  
![部署通話品質-IIS 中的授權規則](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> <span data-ttu-id="5ac10-227">[授權規則] 圖示不會與 [ASP.NET] 區段下的 [.NET 授權] 混淆，這是一種不同的授權機制。</span><span class="sxs-lookup"><span data-stu-id="5ac10-227">The Authorization Rules icon is not to be confused with the ".NET Authorization" under the ASP.NET section, which is a different authorization mechanism.</span></span> 
  
<span data-ttu-id="5ac10-228">系統管理員應該先移除繼承的 [允許所有使用者] 規則。</span><span class="sxs-lookup"><span data-stu-id="5ac10-228">Administrators should first remove the inherited "Allow All Users" rule.</span></span> <span data-ttu-id="5ac10-229">這可防止任何非授權的使用者存取入口網站。</span><span class="sxs-lookup"><span data-stu-id="5ac10-229">This prevents any non-authorized users from accessing the Portal.</span></span>
  
![部署 CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
<span data-ttu-id="5ac10-231">接著，系統管理員應該新增「允許」規則，並給予特定使用者存取入口網站的許可權。</span><span class="sxs-lookup"><span data-stu-id="5ac10-231">Next, administrators should add new Allow Rules and give specific users the permission to access the Portal.</span></span> <span data-ttu-id="5ac10-232">建議建立名為 "CQDPortalUsers" 的本機群組來管理使用者。</span><span class="sxs-lookup"><span data-stu-id="5ac10-232">It is recommended that a local Group called "CQDPortalUsers" be created to manage the users.</span></span>
  
![部署通話品質儀表板](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
<span data-ttu-id="5ac10-234">配置詳細資料儲存在位於入口網站物理目錄的 web.config 中。</span><span class="sxs-lookup"><span data-stu-id="5ac10-234">The configuration details are stored in the web.config located at the Portal's physical directory.</span></span>
  
```XML
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

<span data-ttu-id="5ac10-235">下一步是設定 CQD 的儀表板。</span><span class="sxs-lookup"><span data-stu-id="5ac10-235">The next step is to configure the dashboard of the CQD.</span></span> <span data-ttu-id="5ac10-236">當使用者由 IIS 驗證之後，他們將必須擁有 CQD 目錄的檔案許可權，才能存取網頁入口網站內容。</span><span class="sxs-lookup"><span data-stu-id="5ac10-236">After users are authenticated by IIS, they will have to have file permissions on the CQD directory in order to access the web portal content.</span></span> <span data-ttu-id="5ac10-237">您可以透過 CQD 目錄屬性的 [安全性] 索引標籤變更 Acl，以新增個別的使用者或群組;不過，建議的方法是讓檔案許可權保持不變。</span><span class="sxs-lookup"><span data-stu-id="5ac10-237">It is possible to change the ACLs through the security tab of the CQD directory properties to add individual users or groups; however the recommended approach is to leave the file permissions untouched.</span></span> <span data-ttu-id="5ac10-238">相反地，請將 IIS 設定變更為使用 IIS 輔助進程來存取 CQD 目錄，不論驗證哪個使用者。</span><span class="sxs-lookup"><span data-stu-id="5ac10-238">Instead, change the IIS setting to use the IIS worker process to access the CQD directory no matter which user is authenticated.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="5ac10-239">請務必為 CQD 應用程式變更此設定，而不是針對兩個 API 應用程式： QoEDataService 和 QoERepositoryService。</span><span class="sxs-lookup"><span data-stu-id="5ac10-239">It is important to only change this setting for the CQD application, and not for the two API applications: QoEDataService and QoERepositoryService.</span></span> 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a><span data-ttu-id="5ac10-240">為 CQD 設定檔案存取（儀表板）</span><span class="sxs-lookup"><span data-stu-id="5ac10-240">Configuring File Access for the CQD (Dashboard)</span></span>

1. <span data-ttu-id="5ac10-241">開啟 CQD 的 [設定編輯器]。</span><span class="sxs-lookup"><span data-stu-id="5ac10-241">Open the Configuration Editor for CQD.</span></span>
    
     ![部署通話品質儀表板](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. <span data-ttu-id="5ac10-243">在 [節] 底下，選擇 [ **system.webserver/serverRuntime**]。</span><span class="sxs-lookup"><span data-stu-id="5ac10-243">Under Section, choose **system.webServer/serverRuntime**.</span></span>
    
     ![部署通話品質儀表板](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. <span data-ttu-id="5ac10-245">將 authenticatedUserOverride 變更為**UseWorkerProcessUser**。</span><span class="sxs-lookup"><span data-stu-id="5ac10-245">Change authenticatedUserOverride to **UseWorkerProcessUser**.</span></span>
    
     ![部署通話品質儀表板-配置編輯器](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. <span data-ttu-id="5ac10-247">按一下**頁面**右側的 [套用]。</span><span class="sxs-lookup"><span data-stu-id="5ac10-247">Click **Apply** on the right-hand side of the page.</span></span>
    
## <a name="known-issues"></a><span data-ttu-id="5ac10-248">已知問題</span><span class="sxs-lookup"><span data-stu-id="5ac10-248">Known Issues</span></span>

### <a name="the-cqd-shows-no-data-after-deployment"></a><span data-ttu-id="5ac10-249">部署之後，CQD 不會顯示任何資料</span><span class="sxs-lookup"><span data-stu-id="5ac10-249">The CQD shows no data after deployment</span></span>

<span data-ttu-id="5ac10-250">您可能會收到下列錯誤：</span><span class="sxs-lookup"><span data-stu-id="5ac10-250">You may receive the following error:</span></span>

<span data-ttu-id="5ac10-251">*我們無法在多維資料集中執行查詢。使用 [查詢編輯器] 修改查詢並修正任何問題。此外，請確定多維資料集可以存取。*</span><span class="sxs-lookup"><span data-stu-id="5ac10-251">*We couldn’t perform the query while running it on the Cube. Use the Query Editor to modify the query and fix any issues. Also make sure that the Cube is accessible.*</span></span>

<span data-ttu-id="5ac10-252">這表示在 CQD 中使用多維資料集之前，必須先在 SQL Server Analysis Services 中處理。</span><span class="sxs-lookup"><span data-stu-id="5ac10-252">This means that the cube must be processed in SQL Server Analysis Services prior to being used in CQD.</span></span> <span data-ttu-id="5ac10-253">您可以遵循下列步驟來解決此問題：</span><span class="sxs-lookup"><span data-stu-id="5ac10-253">You can resolve this by following these steps:</span></span>

1. <span data-ttu-id="5ac10-254">開啟 SQL Management Studio，然後選取 [ **Analysis Services**]。</span><span class="sxs-lookup"><span data-stu-id="5ac10-254">Open SQL Management Studio and select **Analysis Services**.</span></span>

2. <span data-ttu-id="5ac10-255">展開**QoECube**物件，選取 [ **QoE 公制**]，以滑鼠右鍵按一下，然後選擇 **[流覽]**。</span><span class="sxs-lookup"><span data-stu-id="5ac10-255">Expand the **QoECube** object, select **QoE Metric**, right-click, and then choose **Browse**.</span></span> 

    <span data-ttu-id="5ac10-256">如果這會傳回空白瀏覽器，則該立方體尚未繼續進行。</span><span class="sxs-lookup"><span data-stu-id="5ac10-256">If this returns empty browser, the cube hasn’t been proceed yet.</span></span>

3. <span data-ttu-id="5ac10-257">以滑鼠右鍵按一下 [ **QoE 公制**angain]，然後選擇 [**處理**]。</span><span class="sxs-lookup"><span data-stu-id="5ac10-257">Right-click **QoE Metric** angain and choose **Process**.</span></span>

4. <span data-ttu-id="5ac10-258">處理完成時，請再次以滑鼠右鍵按一下物件，然後選擇 **[流覽]** ，確認瀏覽器頁面現在顯示資料。</span><span class="sxs-lookup"><span data-stu-id="5ac10-258">When processing is complete, right-click the object again, and choose **Browse** to confirm that the browser page now shows data.</span></span> 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a><span data-ttu-id="5ac10-259">使用者無法登入，因為安裝程式無法在 IIS 中建立正確的設定</span><span class="sxs-lookup"><span data-stu-id="5ac10-259">Users have trouble logging in because installer fails to create the correct settings in IIS</span></span>

<span data-ttu-id="5ac10-260">在少數情況下，安裝程式無法在 IIS 中建立正確的設定。</span><span class="sxs-lookup"><span data-stu-id="5ac10-260">In rare cases, the installer fails to create the correct settings in IIS.</span></span> <span data-ttu-id="5ac10-261">若要允許使用者登入 CQD，必須進行手動變更。</span><span class="sxs-lookup"><span data-stu-id="5ac10-261">Manual change is required to allow users to log into the CQD.</span></span> <span data-ttu-id="5ac10-262">如果使用者無法登入，請依照下列步驟進行：</span><span class="sxs-lookup"><span data-stu-id="5ac10-262">If users are having trouble logging in, please follow these steps:</span></span>
  
1. <span data-ttu-id="5ac10-263">開啟 [啟動 IIS 管理員]，然後流覽至 [預設網站]。</span><span class="sxs-lookup"><span data-stu-id="5ac10-263">Open up IIS Manager, and navigate to Default Web Site.</span></span>
    
     ![部署通話品質儀表板](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. <span data-ttu-id="5ac10-265">按一下 [驗證]。</span><span class="sxs-lookup"><span data-stu-id="5ac10-265">Click on "Authentication".</span></span> <span data-ttu-id="5ac10-266">如果「匿名驗證」、「ASP.NET 模擬」、「表單驗證」和「Windows 驗證」與下列設定不符，請手動變更這些設定，以符合以下設定。</span><span class="sxs-lookup"><span data-stu-id="5ac10-266">If the "Anonymous Authentication", "ASP.NET Impersonation", "Form Authentication", and "Windows Authentication" do not match the settings shown below, manually change them to match the settings below.</span></span> <span data-ttu-id="5ac10-267">所有其他的驗證機制都應該停用。</span><span class="sxs-lookup"><span data-stu-id="5ac10-267">All other authentication mechanisms should be disabled.</span></span>
    
     ![部署通話品質儀表板](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. <span data-ttu-id="5ac10-269">針對「Windows 驗證」，請按一下右側的 [高級設定]。</span><span class="sxs-lookup"><span data-stu-id="5ac10-269">For "Windows Authentication", click on Advanced Settings on the right-hand side.</span></span>
    
     ![部署通話品質儀表板](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. <span data-ttu-id="5ac10-271">將 [延伸保護] 設定為接受並核取 [啟用核心模式驗證] 方塊。</span><span class="sxs-lookup"><span data-stu-id="5ac10-271">Set "Extended Protection" to Accept and check the "Enable Kernel-mode authentication" box.</span></span>
    
     ![部署通話品質儀表板](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. <span data-ttu-id="5ac10-273">針對「預設網站」底下的每個「CQD」、「QoEDataService」和「QoERepositoryService」專案，重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="5ac10-273">Repeat the above steps for each of the "CQD", "QoEDataService", and "QoERepositoryService" entries below "Default Web Site".</span></span>
    
<span data-ttu-id="5ac10-274">針對 HTTP 和 HTTPS 埠系結，安裝程式將會在預設埠號碼（HTTP 的埠80，以及 HTTPS 的埠443）上建立埠系結。</span><span class="sxs-lookup"><span data-stu-id="5ac10-274">For HTTP and HTTPS port bindings the installer will create port bindings on the default port numbers (port 80 for HTTP and port 443 for HTTPS).</span></span> <span data-ttu-id="5ac10-275">如果電腦上有另一個網站使用這些系結，就會發生衝突，且無法預測 IIS 行為。</span><span class="sxs-lookup"><span data-stu-id="5ac10-275">If there is another website on the machine that uses these bindings, there will be a conflict and the IIS behavior cannot be predicted.</span></span> <span data-ttu-id="5ac10-276">避免這個問題的最佳方式，就是在安裝 CQD 之前，先確定沒有任何其他網站對應到埠80和443。</span><span class="sxs-lookup"><span data-stu-id="5ac10-276">The best way to avoid this problem is to make sure that no other websites are mapped to ports 80 and 443 before installing CQD.</span></span> 
  
<span data-ttu-id="5ac10-277">若要在 IIS 中啟用 SSL/TLS，並強迫使用者透過安全的 HTTPS （而不是 HTTP）連線：</span><span class="sxs-lookup"><span data-stu-id="5ac10-277">To enable SSL/TLS in IIS and force users to connect via secure HTTPS instead of HTTP:</span></span>
  
1. <span data-ttu-id="5ac10-278">在 IIS 中設定安全通訊端層，請參閱[在 iis 7 中配置安全通訊端層](https://technet.microsoft.com/en-us/library/cc771438%28v=ws.10%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5ac10-278">Configure Secure Sockets Layer in IIS, see [Configuring Secure Sockets Layer in IIS 7](https://technet.microsoft.com/en-us/library/cc771438%28v=ws.10%29.aspx).</span></span> <span data-ttu-id="5ac10-279">完成後，[ `http`取代`https`為]。</span><span class="sxs-lookup"><span data-stu-id="5ac10-279">Once done, replace  `http` with `https`.</span></span>
    
2. <span data-ttu-id="5ac10-280">如需在 SQL Server 連線中啟用 TLS 的指示，請參閱[如何使用 Microsoft 管理主控台針對 SQL Server 實例啟用 SSL 加密](https://support.microsoft.com/en-us/kb/316898/)。</span><span class="sxs-lookup"><span data-stu-id="5ac10-280">For instructions on enabling TLS in the SQL Server connections, see [How to enable SSL encryption for an instance of SQL Server by using Microsoft Management Console](https://support.microsoft.com/en-us/kb/316898/).</span></span>
    
## <a name="cube-sync-fails"></a><span data-ttu-id="5ac10-281">Cube 同步處理失敗</span><span class="sxs-lookup"><span data-stu-id="5ac10-281">Cube Sync Fails</span></span>

<span data-ttu-id="5ac10-282">QoEMetrics 可能會包含一些以使用者時鐘為基礎的無效記錄。</span><span class="sxs-lookup"><span data-stu-id="5ac10-282">QoEMetrics may contain some invalid records based on end user clocks.</span></span> <span data-ttu-id="5ac10-283">如果時間偏差大於 60 yrs，立方體匯入將會失敗。</span><span class="sxs-lookup"><span data-stu-id="5ac10-283">If the time skew is greater than 60 yrs, the cube import will fail.</span></span>
  
 <span data-ttu-id="5ac10-284">使用下列選取範圍，查看最小和最大 StartTime/EndTime。</span><span class="sxs-lookup"><span data-stu-id="5ac10-284">Check the Min and Max StartTime/EndTime using the selections below.</span></span> <span data-ttu-id="5ac10-285">在過去和遙遠的未來，尋找並刪除記錄，可能會被忽視，而且會中斷同步處理常式。</span><span class="sxs-lookup"><span data-stu-id="5ac10-285">Look for and delete records in the far past and very distant future, they can be disregarded and they will break up the sync processes.</span></span>
  
- <span data-ttu-id="5ac10-286">從 CqdPartitionedStreamView 選取 [最小值] （StartTime）</span><span class="sxs-lookup"><span data-stu-id="5ac10-286">Select MIN(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="5ac10-287">從 CqdPartitionedStreamView 選取 [最大值] （StartTime）</span><span class="sxs-lookup"><span data-stu-id="5ac10-287">Select MAX(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="5ac10-288">從 CqdPartitionedStreamView 選取 [最小值] （EndTime）</span><span class="sxs-lookup"><span data-stu-id="5ac10-288">Select MIN(EndTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="5ac10-289">從 CqdPartitionedStreamView 選取 [最大值] （EndTime）</span><span class="sxs-lookup"><span data-stu-id="5ac10-289">Select MAX(EndTime) FROM CqdPartitionedStreamView</span></span>
    
## <a name="post-install-tasks"></a><span data-ttu-id="5ac10-290">安裝後的工作</span><span class="sxs-lookup"><span data-stu-id="5ac10-290">Post-install tasks</span></span>

### <a name="importing-buildings-and-networks"></a><span data-ttu-id="5ac10-291">匯入建築物和網路</span><span class="sxs-lookup"><span data-stu-id="5ac10-291">Importing Buildings and Networks</span></span>

<span data-ttu-id="5ac10-292">安裝 CQD 之後，請執行下列配置工作：</span><span class="sxs-lookup"><span data-stu-id="5ac10-292">After Installing CQD, perform the following configuration tasks:</span></span>
  
1. <span data-ttu-id="5ac10-293">定義建築物類型（建議使用）</span><span class="sxs-lookup"><span data-stu-id="5ac10-293">Define Building types (recommended)</span></span>
    
2. <span data-ttu-id="5ac10-294">定義建築物擁有權類型（建議使用）</span><span class="sxs-lookup"><span data-stu-id="5ac10-294">Define Building Ownership types (recommended)</span></span>
    
3. <span data-ttu-id="5ac10-295">定義網路類型（強烈建議）</span><span class="sxs-lookup"><span data-stu-id="5ac10-295">Define Network types (highly recommended)</span></span>
    
4. <span data-ttu-id="5ac10-296">匯入建築物（建議使用）</span><span class="sxs-lookup"><span data-stu-id="5ac10-296">Import Buildings (recommended)</span></span>
    
5. <span data-ttu-id="5ac10-297">匯入子網（建議使用）</span><span class="sxs-lookup"><span data-stu-id="5ac10-297">Import Subnets (recommended)</span></span>
    
### <a name="define-building-types"></a><span data-ttu-id="5ac10-298">定義建築物類型</span><span class="sxs-lookup"><span data-stu-id="5ac10-298">Define Building Types</span></span>

<span data-ttu-id="5ac10-299">建築物類型是用來描述您組織內的不同建築物定義或類型。</span><span class="sxs-lookup"><span data-stu-id="5ac10-299">Building types are used to describe the different buildings definitions or types within your organization.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="5ac10-300">此步驟是選擇性的，但建議使用。</span><span class="sxs-lookup"><span data-stu-id="5ac10-300">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="5ac10-301">範例</span><span class="sxs-lookup"><span data-stu-id="5ac10-301">Examples</span></span>
  
- <span data-ttu-id="5ac10-302">設</span><span class="sxs-lookup"><span data-stu-id="5ac10-302">Headquarters</span></span>
    
- <span data-ttu-id="5ac10-303">遠端辦公室</span><span class="sxs-lookup"><span data-stu-id="5ac10-303">Remote Office</span></span>
    
- <span data-ttu-id="5ac10-304">共同冒險的位置</span><span class="sxs-lookup"><span data-stu-id="5ac10-304">Joint-venture location</span></span>
    
  <span data-ttu-id="5ac10-305">**範例 SQL 語法**</span><span class="sxs-lookup"><span data-stu-id="5ac10-305">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

<span data-ttu-id="5ac10-306">BuildingTypeId 和 BuildingTypeDesc 參數是必要的。</span><span class="sxs-lookup"><span data-stu-id="5ac10-306">The BuildingTypeId and BuildingTypeDesc parameters are required.</span></span>
  
### <a name="define-building-ownership-types"></a><span data-ttu-id="5ac10-307">定義建築物擁有權類型</span><span class="sxs-lookup"><span data-stu-id="5ac10-307">Define Building Ownership Types</span></span>

<span data-ttu-id="5ac10-308">擁有權類型是用來區分擁有的與租用的資產。</span><span class="sxs-lookup"><span data-stu-id="5ac10-308">Ownership types are used to distinguish owned vs leased assets.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5ac10-309">此步驟是選擇性的，但建議使用。</span><span class="sxs-lookup"><span data-stu-id="5ac10-309">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="5ac10-310">範例</span><span class="sxs-lookup"><span data-stu-id="5ac10-310">Examples</span></span>
  
- <span data-ttu-id="5ac10-311">Contoso 租您的非&amp;RE F</span><span class="sxs-lookup"><span data-stu-id="5ac10-311">Contoso Leased non-RE&amp;F</span></span>
    
- <span data-ttu-id="5ac10-312">Contoso 租賃 RE&amp;F</span><span class="sxs-lookup"><span data-stu-id="5ac10-312">Contoso Leased RE&amp;F</span></span>
    
- <span data-ttu-id="5ac10-313">Contoso 擁有</span><span class="sxs-lookup"><span data-stu-id="5ac10-313">Contoso Owned</span></span>
    
- <span data-ttu-id="5ac10-314">子公司租</span><span class="sxs-lookup"><span data-stu-id="5ac10-314">Subsidiary Leased</span></span>
    
  <span data-ttu-id="5ac10-315">**範例 SQL 語法**</span><span class="sxs-lookup"><span data-stu-id="5ac10-315">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO
[dbo].[CqdBuildingOwnershipType]
([OwnershipTypeId],
[OwnershipTypeDesc]
)

VALUES
(1,
'Contoso Owned'
)
```

<span data-ttu-id="5ac10-316">OwnershipTypeId 和 OwnershipTypeDesc 參數是必要的。</span><span class="sxs-lookup"><span data-stu-id="5ac10-316">The OwnershipTypeId and OwnershipTypeDesc parameters are required.</span></span> 
  
### <a name="define-network-names"></a><span data-ttu-id="5ac10-317">定義網路名稱</span><span class="sxs-lookup"><span data-stu-id="5ac10-317">Define Network Names</span></span>

<span data-ttu-id="5ac10-318">網路類型是用來描述組織內部不同類型的網路。</span><span class="sxs-lookup"><span data-stu-id="5ac10-318">Network Types are used to describe different types of networks within the organization.</span></span> <span data-ttu-id="5ac10-319">這可讓您篩選（或篩選掉）特定的網路類型。</span><span class="sxs-lookup"><span data-stu-id="5ac10-319">This gives you the ability to filter on (or filter out) specific Network Types.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5ac10-320">強烈建議定義網路名稱，但它是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="5ac10-320">It is highly recommended to define Network Names, but it is optional.</span></span> <span data-ttu-id="5ac10-321">如果您決定不定義網路名稱，請確定每個 CqdNetwork 專案都有 BuildingId 0。</span><span class="sxs-lookup"><span data-stu-id="5ac10-321">If you decide to not define network names, ensure the each CqdNetwork entry has a BuildingId of 0.</span></span> 
  
<span data-ttu-id="5ac10-322">範例</span><span class="sxs-lookup"><span data-stu-id="5ac10-322">Examples</span></span>
  
- <span data-ttu-id="5ac10-323">點對點</span><span class="sxs-lookup"><span data-stu-id="5ac10-323">VPN</span></span>
    
- <span data-ttu-id="5ac10-324">實驗</span><span class="sxs-lookup"><span data-stu-id="5ac10-324">LAB</span></span>
    
  <span data-ttu-id="5ac10-325">**範例 SQL 語法**</span><span class="sxs-lookup"><span data-stu-id="5ac10-325">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

<span data-ttu-id="5ac10-326">NetworkNameID 和 NetworkName 參數是必要的，NetworkType 參數是選擇性的，但建議使用。</span><span class="sxs-lookup"><span data-stu-id="5ac10-326">The NetworkNameID and NetworkName parameters are required, the NetworkType parameter is optional but recommended.</span></span>
  
### <a name="import-buildings"></a><span data-ttu-id="5ac10-327">匯入建築物</span><span class="sxs-lookup"><span data-stu-id="5ac10-327">Import Buildings</span></span>

<span data-ttu-id="5ac10-328">匯入建築物可讓您取得建立特定深入見解（WiFi/有線等的每個建築物較差的通話）。</span><span class="sxs-lookup"><span data-stu-id="5ac10-328">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="5ac10-329">此步驟是選擇性的，但建議使用。</span><span class="sxs-lookup"><span data-stu-id="5ac10-329">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="5ac10-330">在匯入新的組建之前，您應該已經識別出預先定義的 BuildingKey。</span><span class="sxs-lookup"><span data-stu-id="5ac10-330">Before you Import a new building you should already have a predefined BuildingKey identified.</span></span> <span data-ttu-id="5ac10-331">若要這樣做，請發出 [從 CqdBuilding 中選取 MAX （BuildingKey）] SQL 命令，以找出目前的值，並將1加到結果中。</span><span class="sxs-lookup"><span data-stu-id="5ac10-331">To do that, issue the "SELECT MAX(BuildingKey) FROM CqdBuilding" SQL command to identify the current value and add 1 to the result.</span></span>
  
 <span data-ttu-id="5ac10-332">**範例 SQL 語法**</span><span class="sxs-lookup"><span data-stu-id="5ac10-332">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdBuilding] 
( [BuildingKey]
,[BuildingName]
,[BuildingShortName]
,[OwnershipTypeId],
[BuildingTypeId]
)
VALUES
(2, 'Ann Arbor', 'AA', 0, 0)
```

<span data-ttu-id="5ac10-333">BuildingKey、BuildingName、BuildingShortName、OwnershipTypeId、BuildingTypeId 參數是必要的，其他參數是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="5ac10-333">The BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId parameters are required, the other parameters are optional.</span></span>
  
### <a name="import-subnets"></a><span data-ttu-id="5ac10-334">匯入子網</span><span class="sxs-lookup"><span data-stu-id="5ac10-334">Import Subnets</span></span>

<span data-ttu-id="5ac10-335">匯入建築物可讓您取得建立特定深入見解（WiFi/有線等的每個建築物較差的通話）。</span><span class="sxs-lookup"><span data-stu-id="5ac10-335">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="5ac10-336">此步驟是選擇性的，但建議使用。</span><span class="sxs-lookup"><span data-stu-id="5ac10-336">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="5ac10-337">匯入子網並將其對應至在上一個步驟中匯入的建築物。</span><span class="sxs-lookup"><span data-stu-id="5ac10-337">Import Subnets and map them to the Buildings imported in the last step.</span></span> <span data-ttu-id="5ac10-338">如果您決定不要填入 NetworkName，請確定此表格中的每個專案都使用0的 NetworkNameID。</span><span class="sxs-lookup"><span data-stu-id="5ac10-338">If you decided not to populate NetworkName, ensure each entry in this table uses a NetworkNameID of 0.</span></span>
  
 <span data-ttu-id="5ac10-339">**範例 SQL 語法**</span><span class="sxs-lookup"><span data-stu-id="5ac10-339">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',0,1,'2015-11-11')
```

<span data-ttu-id="5ac10-340">Network 及 UpdatedDate 參數是必要的，其他參數則是選用的。</span><span class="sxs-lookup"><span data-stu-id="5ac10-340">The Network, and UpdatedDate parameters are required, the other parameters are optional.</span></span>
  
### <a name="optional-bssid"></a><span data-ttu-id="5ac10-341">選用： BSSID</span><span class="sxs-lookup"><span data-stu-id="5ac10-341">Optional: BSSID</span></span>

<span data-ttu-id="5ac10-342">填入 BSSID 資訊後，您可以透過控制器或無線電提供額外的 WiFi 資料流程關聯。</span><span class="sxs-lookup"><span data-stu-id="5ac10-342">Populating BSSID information gives you additional WiFi stream correlation by controller or radio.</span></span> <span data-ttu-id="5ac10-343">這與透過組建或子網進行篩選之外。</span><span class="sxs-lookup"><span data-stu-id="5ac10-343">This is in addition to filtering by building or subnet.</span></span> 
  
 <span data-ttu-id="5ac10-344">**範例 SQL 語法**</span><span class="sxs-lookup"><span data-stu-id="5ac10-344">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdBssid]
([Ap],
[Bss],
[Building],
[ess],
[phy]
)
VALUES
('AP1','00-00-00-00-00-00','Aruba AP 1','Controller1','bgn')
```

<span data-ttu-id="5ac10-345">**CqdBssidTable 詳細資料**</span><span class="sxs-lookup"><span data-stu-id="5ac10-345">**CqdBssidTable Details**</span></span>

|<span data-ttu-id="5ac10-346">**如 CQD 所示**</span><span class="sxs-lookup"><span data-stu-id="5ac10-346">**As shown in CQD**</span></span>|<span data-ttu-id="5ac10-347">**CQDBssid 資料表**</span><span class="sxs-lookup"><span data-stu-id="5ac10-347">**CQDBssid Table**</span></span>|<span data-ttu-id="5ac10-348">**輸入範例**</span><span class="sxs-lookup"><span data-stu-id="5ac10-348">**Example inputs**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5ac10-349">Ap NName</span><span class="sxs-lookup"><span data-stu-id="5ac10-349">Ap NName</span></span>  <br/> |<span data-ttu-id="5ac10-350">應付</span><span class="sxs-lookup"><span data-stu-id="5ac10-350">AP</span></span>  <br/> |<span data-ttu-id="5ac10-351">AP1</span><span class="sxs-lookup"><span data-stu-id="5ac10-351">AP1</span></span>  <br/> |
|<span data-ttu-id="5ac10-352">BBssid</span><span class="sxs-lookup"><span data-stu-id="5ac10-352">BBssid</span></span>  <br/> |<span data-ttu-id="5ac10-353">面臨</span><span class="sxs-lookup"><span data-stu-id="5ac10-353">BSS</span></span>  <br/> |<span data-ttu-id="5ac10-354">00-00-00-00-00-00 （您必須使用分隔符號 fformat）</span><span class="sxs-lookup"><span data-stu-id="5ac10-354">00-00-00-00-00-00 (you must use the delimited fformat)</span></span>  <br/> |
|<span data-ttu-id="5ac10-355">審計員</span><span class="sxs-lookup"><span data-stu-id="5ac10-355">Controller</span></span>  <br/> |<span data-ttu-id="5ac10-356">創建</span><span class="sxs-lookup"><span data-stu-id="5ac10-356">Building</span></span>  <br/> |<span data-ttu-id="5ac10-357">Aruba AP 7</span><span class="sxs-lookup"><span data-stu-id="5ac10-357">Aruba AP 7</span></span>  <br/> |
|<span data-ttu-id="5ac10-358">裝置</span><span class="sxs-lookup"><span data-stu-id="5ac10-358">Device</span></span>  <br/> |<span data-ttu-id="5ac10-359">員工</span><span class="sxs-lookup"><span data-stu-id="5ac10-359">ess</span></span>  <br/> |<span data-ttu-id="5ac10-360">Controller1</span><span class="sxs-lookup"><span data-stu-id="5ac10-360">Controller1</span></span>  <br/> |
|<span data-ttu-id="5ac10-361">收發</span><span class="sxs-lookup"><span data-stu-id="5ac10-361">Radio</span></span>  <br/> |<span data-ttu-id="5ac10-362">phy</span><span class="sxs-lookup"><span data-stu-id="5ac10-362">phy</span></span>  <br/> |<span data-ttu-id="5ac10-363">bgn</span><span class="sxs-lookup"><span data-stu-id="5ac10-363">bgn</span></span>  <br/> |
   
### <a name="processing-the-imported-data"></a><span data-ttu-id="5ac10-364">處理匯入的資料</span><span class="sxs-lookup"><span data-stu-id="5ac10-364">Processing the imported data</span></span>

<span data-ttu-id="5ac10-365">根據預設，在您匯入建立/網路資料之後，只會套用到在該時間點之後產生的記錄。</span><span class="sxs-lookup"><span data-stu-id="5ac10-365">By default, after you import building/network data it will only apply to records generated after that point in time.</span></span> 
  
<span data-ttu-id="5ac10-366">若要使用這個新資料來標記所有先前的記錄，您必須執行 CqdUpdateBuilding 的儲存程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5ac10-366">To tag all the previous records with this new data, you will need to run the CqdUpdateBuilding stored procedure as shown below:</span></span> 
  
<span data-ttu-id="5ac10-367">賦予它您第一筆記錄的日期（找出在 CqdPartitionedStreamView SQL 命令中使用 Select MIN （StartTime））、明天的結束時間，最後兩個值為 Null。</span><span class="sxs-lookup"><span data-stu-id="5ac10-367">Give it the date of your first record (identify that using the Select MIN(StartTime) FROM CqdPartitionedStreamView SQL command ), an EndDate of tomorrow, then NULL for the last two values.</span></span>
  
<span data-ttu-id="5ac10-368">資料與資料流程資料關聯之後，SSIS 立方體需要重新處理所有記錄。</span><span class="sxs-lookup"><span data-stu-id="5ac10-368">Once the data is associated with stream data, the SSIS Cube needs to reprocess all records.</span></span> <span data-ttu-id="5ac10-369">大量新增 BSSID/ISP 資料時，也會套用這種情況。</span><span class="sxs-lookup"><span data-stu-id="5ac10-369">This also applies when bulk adding BSSID/ISP data.</span></span> <span data-ttu-id="5ac10-370">確認已選取 [程式已滿]。</span><span class="sxs-lookup"><span data-stu-id="5ac10-370">Ensure that "Process Full" is selected.</span></span>
  

