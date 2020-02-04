---
title: Lync Server 2013：還原託管中央管理儲存區的伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring the server hosting the Central Management store
ms:assetid: 3bd6c82c-07fb-4798-b8f9-e7c78a5a83d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202172(v=OCS.15)
ms:contentKeyID: 51541464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 976f486d096f7be59e2eef74eab7b03d6cc4bab0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733043"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-the-server-hosting-the-central-management-store-in-lync-server-2013"></a><span data-ttu-id="357f3-102">在 Lync Server 2013 中還原託管中央管理儲存區的伺服器</span><span class="sxs-lookup"><span data-stu-id="357f3-102">Restoring the server hosting the Central Management store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="357f3-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="357f3-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="357f3-104">Lync Server 部署只有一個中央管理存儲，複本會複製到執行 Lync Server 伺服器角色的每個伺服器。</span><span class="sxs-lookup"><span data-stu-id="357f3-104">A Lync Server deployment has a single Central Management store, a copy of which is replicated to each server running a Lync Server server role.</span></span> <span data-ttu-id="357f3-105">本主題說明如何還原託管中央管理存放區的後端伺服器或標準版伺服器。</span><span class="sxs-lookup"><span data-stu-id="357f3-105">This topic describes how to restore a Back End Server or Standard Edition server that hosts the Central Management store.</span></span>

<span data-ttu-id="357f3-106">若要尋找中央管理伺服器所在的池中，請開啟 [拓撲建立器]，按一下 [ **Lync Server**]，然後在右窗格的 [**中央管理伺服器**] 底下尋找。</span><span class="sxs-lookup"><span data-stu-id="357f3-106">To find the pool where the Central Management Server is located, open Topology Builder, click **Lync Server**, and look in the right pane under **Central Management Server**.</span></span>

<span data-ttu-id="357f3-107">如果裝載中央管理儲存體的後端伺服器位於鏡像設定中，而且鏡像資料庫仍在運作，我們建議您對這個仍正常運作的鏡像進行備份，然後在主要資料庫和使用此備份進行鏡像資料庫，請遵循下列還原程式。</span><span class="sxs-lookup"><span data-stu-id="357f3-107">If the Back End Server that hosts the Central Management store is in a mirrored setup and the mirror database is still functional, we recommend that you make a backup of this still-functioning mirror, and then perform a full restore on both the primary database and the mirror database, using this backup, by following the restoration procedure below.</span></span> <span data-ttu-id="357f3-108">這是必要的，因為背面端還原需要修改及發佈拓撲，而且只有在主要資料庫託管 CMS 正常運作時才能執行。</span><span class="sxs-lookup"><span data-stu-id="357f3-108">This is necessary because Back End restore requires modifying and publishing the topology, and this can be done only if the primary database hosting CMS is operational.</span></span> <span data-ttu-id="357f3-109">另請注意，如果無法發佈拓撲，則無法互換主要和鏡像資料庫角色。</span><span class="sxs-lookup"><span data-stu-id="357f3-109">Also note that the primary and mirror database roles cannot be interchanged if the topology cannot be published.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="357f3-110">如果沒有託管中央管理儲存區的後端伺服器或標準版伺服器失敗，請參閱<A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">在 Lync server 2013 中還原企業版後端伺服器</A>，或<A href="lync-server-2013-restoring-a-standard-edition-server.md">在 lync Server 2013 中還原標準版伺服器</A>。</span><span class="sxs-lookup"><span data-stu-id="357f3-110">If a Back End Server or Standard Edition server that does not host the Central Management store failed, see <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restoring an Enterprise Edition Back End Server in Lync Server 2013</A> or <A href="lync-server-2013-restoring-a-standard-edition-server.md">Restoring a Standard Edition server in Lync Server 2013</A>.</span></span> <span data-ttu-id="357f3-111">如果裝載中央管理儲存體的後端伺服器是在鏡像設定中，而且只有鏡像失敗，請參閱<A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">在 Lync Server 2013-mirror 中還原鏡像企業版後端伺服器</A>。</span><span class="sxs-lookup"><span data-stu-id="357f3-111">If a Back End Server that hosts the Central Management store is in a mirrored configuration and only the mirror failed, see <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</A>.</span></span> <span data-ttu-id="357f3-112">如果有任何其他伺服器失敗，請參閱<A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">在 Lync server 2013 中還原企業版成員伺服器</A>。</span><span class="sxs-lookup"><span data-stu-id="357f3-112">If any other server failed, see <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restoring an Enterprise Edition member server in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="357f3-113">我們建議您先取得系統的影像複本，然後再開始還原。</span><span class="sxs-lookup"><span data-stu-id="357f3-113">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="357f3-114">您可以使用這個影像做為復原點，以防還原期間發生的問題。</span><span class="sxs-lookup"><span data-stu-id="357f3-114">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="357f3-115">您可能會想要在安裝作業系統與 SQL Server 之後拍攝影像複本，並還原或重新註冊憑證。</span><span class="sxs-lookup"><span data-stu-id="357f3-115">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-the-central-management-store"></a><span data-ttu-id="357f3-116">若要還原中央管理存放區</span><span class="sxs-lookup"><span data-stu-id="357f3-116">To restore the Central Management store</span></span>

1.  <span data-ttu-id="357f3-117">從包含與失敗電腦相同的完整功能變數名稱（FQDN）的乾淨或新伺服器開始，安裝作業系統，然後還原或重新註冊證書。</span><span class="sxs-lookup"><span data-stu-id="357f3-117">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="357f3-118">遵循貴組織的伺服器部署程式來執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="357f3-118">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="357f3-119">從屬於 [RTCUniversalServerAdmins] 群組和 [本機管理員] 群組成員的使用者帳戶登入您要還原的伺服器。</span><span class="sxs-lookup"><span data-stu-id="357f3-119">From a user account that is a member of the RTCUniversalServerAdmins group and the Local Administrators group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="357f3-120">如果您要還原的是標準版伺服器，請將適當的檔案存放區從 $Backup 複製到伺服器上的檔案存放位置，然後共用資料夾，以還原檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="357f3-120">If you are restoring a Standard Edition server, restore the File Store by copying the appropriate File Store from $Backup to the File Store location on the server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="357f3-121">已還原之檔案存放區的路徑和檔案名應該與已備份的檔案存放區完全相同，以便使用檔案的元件可以存取它們。</span><span class="sxs-lookup"><span data-stu-id="357f3-121">The path and file name for the restored File Store should be exactly the same as the backed up File Store so that components that use the files can access them.</span></span>

    
    </div>

4.  <span data-ttu-id="357f3-122">請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="357f3-122">Do one of the following:</span></span>
    
      - <span data-ttu-id="357f3-123">如果您安裝的是標準版伺服器，請流覽至 Lync Server 安裝資料夾或媒體，然後啟動位於\\安裝程式\\Amd64\\setup.exe 的 lync server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="357f3-123">If you are installing a Standard Edition server, browse to the Lync Server installation folder or media, and then start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="357f3-124">在 [部署嚮導] 中，按一下 [**準備第一個標準版伺服器**]，然後遵循嚮導來安裝中央管理存放區。</span><span class="sxs-lookup"><span data-stu-id="357f3-124">In the Deployment Wizard, click **Prepare first Standard Edition server** and follow the wizard to install the Central Management store.</span></span>
    
      - <span data-ttu-id="357f3-125">如果您要安裝企業後端伺服器，請安裝 SQL Server 2012 或 SQL Server 2008 R2，並保持實例名稱與失敗前相同。</span><span class="sxs-lookup"><span data-stu-id="357f3-125">If you are installing an Enterprise Back End Server, install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="357f3-126">根據您要還原的伺服器和您的部署，伺服器可能會包含多個 collocated 或個別的資料庫。</span><span class="sxs-lookup"><span data-stu-id="357f3-126">Depending on the server that you are restoring and on your deployment, the server might include multiple collocated or separate databases.</span></span> <span data-ttu-id="357f3-127">遵循相同的程式，安裝您最初用來部署伺服器的 SQL Server，包括 SQL Server 許可權和登錄名。</span><span class="sxs-lookup"><span data-stu-id="357f3-127">Follow the same procedure to install SQL Server that you used originally to deploy the server, including SQL Server permissions and logins.</span></span>

        
        </div>

5.  <span data-ttu-id="357f3-128">從前端伺服器，啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="357f3-128">From a Front End Server, Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

6.  <span data-ttu-id="357f3-129">重新建立中央管理存放區。</span><span class="sxs-lookup"><span data-stu-id="357f3-129">Re-create the Central Management store.</span></span> <span data-ttu-id="357f3-130">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="357f3-130">At the command line, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    <span data-ttu-id="357f3-131">例如：</span><span class="sxs-lookup"><span data-stu-id="357f3-131">For example:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  <span data-ttu-id="357f3-132">針對中央管理存放區設定 Active Directory 網域服務控制點。</span><span class="sxs-lookup"><span data-stu-id="357f3-132">Set the Active Directory Domain Services control point for the Central Management store.</span></span> <span data-ttu-id="357f3-133">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="357f3-133">At the command line, type:</span></span>
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    <span data-ttu-id="357f3-134">例如：</span><span class="sxs-lookup"><span data-stu-id="357f3-134">For example:</span></span>
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="357f3-135">如果您遺失連接點，您可以重新執行這個 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="357f3-135">If you lose the connection point, you can rerun this cmdlet.</span></span>

    
    </div>

8.  <span data-ttu-id="357f3-136">從 $Backup 匯入集中式管理儲存資料。</span><span class="sxs-lookup"><span data-stu-id="357f3-136">Import the Central Management store data from $Backup.</span></span> <span data-ttu-id="357f3-137">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="357f3-137">At the command line, type:</span></span>
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    <span data-ttu-id="357f3-138">例如：</span><span class="sxs-lookup"><span data-stu-id="357f3-138">For example:</span></span>
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  <span data-ttu-id="357f3-139">啟用您剛進行的變更。</span><span class="sxs-lookup"><span data-stu-id="357f3-139">Enable the changes you have just made.</span></span> <span data-ttu-id="357f3-140">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="357f3-140">At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="357f3-141">啟用拓撲之後，您就可以在資料庫中找到 [拓撲] 檔。</span><span class="sxs-lookup"><span data-stu-id="357f3-141">After you enable the topology, you can find the topology document in the database.</span></span>

    
    </div>

10. <span data-ttu-id="357f3-142">如果您要還原的是託管 CMS 的企業版後端伺服器，或者您需要重新建立 CMS 的鏡像，請依照此步驟進行。</span><span class="sxs-lookup"><span data-stu-id="357f3-142">If you are restoring an Enterprise Edition Back End Server that also hosted the CMS, or if you need to re-create a mirror of the CMS, then follow this step.</span></span> <span data-ttu-id="357f3-143">否則，請跳至步驟11。</span><span class="sxs-lookup"><span data-stu-id="357f3-143">Otherwise, skip to step 11.</span></span>
    
    <span data-ttu-id="357f3-144">您可以執行下列動作來安裝獨立資料庫：</span><span class="sxs-lookup"><span data-stu-id="357f3-144">Install the stand-alone databases by doing the following:</span></span>
    
    1.  <span data-ttu-id="357f3-145">啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。</span><span class="sxs-lookup"><span data-stu-id="357f3-145">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="357f3-146">按一下 [**從現有部署下載拓朴**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="357f3-146">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="357f3-147">選取拓撲，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="357f3-147">Select the topology, and then click **Save**.</span></span> <span data-ttu-id="357f3-148">按一下 **[是]** 以確認您的選取專案。</span><span class="sxs-lookup"><span data-stu-id="357f3-148">Click **Yes** to confirm your selection.</span></span>
    
    4.  <span data-ttu-id="357f3-149">以滑鼠右鍵按一下**Lync Server 2013**節點，然後按一下 [**安裝資料庫**]。</span><span class="sxs-lookup"><span data-stu-id="357f3-149">Right-click the **Lync Server 2013** node, and then click **Install Database**.</span></span>
    
    5.  <span data-ttu-id="357f3-150">遵循 [**安裝資料庫**] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="357f3-150">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="357f3-151">如果您要還原此伺服器中央管理儲存體以外的資料庫，請在 [**建立資料庫**] 頁面上，選取您要重建的資料庫。</span><span class="sxs-lookup"><span data-stu-id="357f3-151">If you are restoring a database other than the Central Management store on this server, on the **Create databases** page, select the databases you want to recreate.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="357f3-152">[<STRONG>建立資料庫</STRONG>] 頁面上只會顯示獨立的資料庫。</span><span class="sxs-lookup"><span data-stu-id="357f3-152">Only stand-alone databases are displayed on the <STRONG>Create databases</STRONG> page.</span></span> <span data-ttu-id="357f3-153">Collocated 資料庫是在您執行 Lync Server 部署嚮導時建立的。</span><span class="sxs-lookup"><span data-stu-id="357f3-153">Collocated databases are created when you run the Lync Server Deployment Wizard.</span></span>

        
        </div>
    
    6.  <span data-ttu-id="357f3-154">如果您要還原鏡像的後端伺服器，請繼續按照嚮導中的其餘步驟進行，直到您收到建立鏡像資料庫的提示。</span><span class="sxs-lookup"><span data-stu-id="357f3-154">If you are restoring a mirrored Back End Server, continue to follow the rest of the wizard until you come to a prompt of Create Mirror Database.</span></span> <span data-ttu-id="357f3-155">選取您要安裝的資料庫，並完成程式。</span><span class="sxs-lookup"><span data-stu-id="357f3-155">Select the database you want to install, and complete the process.</span></span>
    
    7.  <span data-ttu-id="357f3-156">依照嚮導的其餘部分進行，然後按一下 **[完成**]。</span><span class="sxs-lookup"><span data-stu-id="357f3-156">Follow the rest of the wizard, and then click **Finish**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="357f3-157">您可以使用<STRONG>CsDatabase</STRONG> Cmdlet 來建立每個資料庫，以及<STRONG>安裝 CsMirrorDatabase</STRONG> Cmdlet 來設定鏡像，而不需要執行拓撲建立器。</span><span class="sxs-lookup"><span data-stu-id="357f3-157">Instead of running Topology Builder, you can use the <STRONG>Install-CsDatabase</STRONG> cmdlet to create each database, and the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="357f3-158">如需詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">安裝 CsDatabase</A>及<A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">安裝 CsMirrorDatabase</A>。</span><span class="sxs-lookup"><span data-stu-id="357f3-158">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">Install-CsDatabase</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">Install-CsMirrorDatabase</A>.</span></span>

    
    </div>

11. <span data-ttu-id="357f3-159">如果您要還原的是標準版伺服器，請流覽至 Lync Server 安裝資料夾或媒體，然後啟動位於\\安裝程式\\Amd64\\setup.exe 的 lync server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="357f3-159">If you are restoring a Standard Edition server, browse to the Lync Server installation folder or media, and start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="357f3-160">使用 Lync Server 部署嚮導來執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="357f3-160">Use the Lync Server Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="357f3-161">執行**步驟1：安裝本機配置存放區**以安裝本機配置檔案。</span><span class="sxs-lookup"><span data-stu-id="357f3-161">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="357f3-162">執行**步驟2：設定或移除 Lync Server 元件**以安裝 lync server 伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="357f3-162">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server roles.</span></span>
    
    3.  <span data-ttu-id="357f3-163">執行**步驟3：要求、安裝或指派憑證**來指派憑證。</span><span class="sxs-lookup"><span data-stu-id="357f3-163">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="357f3-164">執行**步驟4：啟動服務**以在伺服器上啟動服務。</span><span class="sxs-lookup"><span data-stu-id="357f3-164">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="357f3-165">如需執行 [部署嚮導] 的詳細資訊，請參閱您要還原之伺服器角色的部署檔。</span><span class="sxs-lookup"><span data-stu-id="357f3-165">For details about running the Deployment Wizard, see the Deployment documentation for the server role that you are restoring.</span></span>

12. <span data-ttu-id="357f3-166">若要還原使用者資料，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="357f3-166">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="357f3-167">從 $Backup\\將 ExportedUserData 複製到本機目錄。</span><span class="sxs-lookup"><span data-stu-id="357f3-167">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="357f3-168">您必須先停止 Lync services，才能還原使用者資料。</span><span class="sxs-lookup"><span data-stu-id="357f3-168">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="357f3-169">若要這麼做，請輸入：</span><span class="sxs-lookup"><span data-stu-id="357f3-169">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    3.  <span data-ttu-id="357f3-170">若要還原使用者資料，請在命令列輸入：</span><span class="sxs-lookup"><span data-stu-id="357f3-170">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="357f3-171">例如：</span><span class="sxs-lookup"><span data-stu-id="357f3-171">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  <span data-ttu-id="357f3-172">輸入以下內容以重新開機 Lync services：</span><span class="sxs-lookup"><span data-stu-id="357f3-172">Restart Lync services by typing:</span></span>
        
            Start-CsWindowsService

13. <span data-ttu-id="357f3-173">將位置資訊資料還原到中央管理儲存區。</span><span class="sxs-lookup"><span data-stu-id="357f3-173">Restore Location Information data to the Central Management store.</span></span> <span data-ttu-id="357f3-174">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="357f3-174">At the command line, type:</span></span>
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    <span data-ttu-id="357f3-175">例如：</span><span class="sxs-lookup"><span data-stu-id="357f3-175">For example:</span></span>
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. <span data-ttu-id="357f3-176">如果您已在此 pool 或標準版伺服器上部署回應群組，請還原回應群組設定資料。</span><span class="sxs-lookup"><span data-stu-id="357f3-176">If you deployed Response Group on this pool or Standard Edition server, restore the Response Group configuration data.</span></span> <span data-ttu-id="357f3-177">如需詳細資訊，請參閱[在 Lync Server 2013 中還原回應群組設定](lync-server-2013-restoring-response-group-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="357f3-177">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

15. <span data-ttu-id="357f3-178">如果您要還原包含封存或監視資料庫的後端伺服器，請使用 SQL Server 管理工具（例如 SQL Server Management Studio）還原封存或監視資料。</span><span class="sxs-lookup"><span data-stu-id="357f3-178">If you are restoring a Back End Server that includes Archiving or Monitoring databases, restore the Archiving or Monitoring data by using a SQL Server management tool, such as SQL Server Management Studio.</span></span> <span data-ttu-id="357f3-179">如需詳細資訊，請參閱[在 Lync Server 2013 中還原監視或封存資料](lync-server-2013-restoring-monitoring-or-archiving-data.md)。</span><span class="sxs-lookup"><span data-stu-id="357f3-179">For details, see [Restoring monitoring or archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

