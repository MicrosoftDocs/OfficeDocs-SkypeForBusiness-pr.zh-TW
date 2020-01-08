---
title: Lync Server 2013 持續聊天資源套件工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2013 Persistent Chat Resource Kit Tools
ms:assetid: 7a34d2ba-eb25-4e22-92d1-b9baf81b102c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945599(v=OCS.15)
ms:contentKeyID: 51541423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c851be7bb7046021cc2d37c88ef03bdea60c95a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976022"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-persistent-chat-resource-kit-tools"></a><span data-ttu-id="89fa9-102">Lync Server 2013 持續聊天資源套件工具</span><span class="sxs-lookup"><span data-stu-id="89fa9-102">Lync Server 2013 Persistent Chat Resource Kit Tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89fa9-103">_**主題上次修改日期：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="89fa9-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="89fa9-104">Lync Server 2013 持續性聊天資源套件工具可協助您更輕鬆地為部署和管理 Lync Server 2013 持久聊天伺服器的 IT 系統管理員進行例行工作。</span><span class="sxs-lookup"><span data-stu-id="89fa9-104">The Lync Server 2013 Persistent Chat Resource Kit tools help to make routine tasks easier for IT administrators who deploy and manage Lync Server 2013 Persistent Chat Server.</span></span> <span data-ttu-id="89fa9-105">除了安裝指示之外，本主題還說明每個工具的用途，以及其用法範例。</span><span class="sxs-lookup"><span data-stu-id="89fa9-105">In addition to installation instructions, this topic describes the purpose of each tool, and examples of its use.</span></span>

<div>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="89fa9-106">資源套件工具的安裝</span><span class="sxs-lookup"><span data-stu-id="89fa9-106">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="89fa9-107">若要安裝 Lync Server 2013、資源套件工具，請下載**PersistentChatReskit**。</span><span class="sxs-lookup"><span data-stu-id="89fa9-107">To install the Lync Server 2013, Resource Kit Tools, download **PersistentChatReskit.msi**.</span></span> <span data-ttu-id="89fa9-108">執行**PersistentChatReskit**以進行簡單的安裝。</span><span class="sxs-lookup"><span data-stu-id="89fa9-108">Run **PersistentChatReskit.msi** to do a simple installation.</span></span> <span data-ttu-id="89fa9-109">.Msi 會安裝下列路徑中的所有工具： \\ **Program\\ Files Microsoft Lync Server 2013\\持續聊天伺服器資源套件**。</span><span class="sxs-lookup"><span data-stu-id="89fa9-109">The .msi installs all the tools in the following path: \\**Program Files\\ Microsoft Lync Server 2013\\Persistent Chat Server Resource Kit**.</span></span> <span data-ttu-id="89fa9-110">可自包含的可執行檔的工具位於此資料夾中。</span><span class="sxs-lookup"><span data-stu-id="89fa9-110">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="89fa9-111">也有檔案的工具位於自己的子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="89fa9-111">Tools that also have files are in their own subfolders.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="89fa9-112">安裝 Lync Server 2013、資源套件工具之後，您必須安裝<STRONG>psexec</STRONG>並將<STRONG>psexec</STRONG>複製到下列路徑： \\ <STRONG>Program Files \ Microsoft Lync Server 2013 \ 持續聊天伺服器資源 Kit\ChatStressTool</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="89fa9-112">After installing the Lync Server 2013, Resource Kit Tools, you must install <STRONG>PsExec.exe</STRONG> and copy <STRONG>PsExec.exe</STRONG> to the following path: \\<STRONG>Program Files\ Microsoft Lync Server 2013\Persistent Chat Server Resource Kit\ChatStressTool</STRONG>.</span></span> <span data-ttu-id="89fa9-113">如果您不復制<STRONG>PsExec</STRONG>，持續聊天的壓力工具將會引發錯誤例外狀況，且無法正確執行。</span><span class="sxs-lookup"><span data-stu-id="89fa9-113">If you do not copy <STRONG>PsExec.exe</STRONG>, the Persistent Chat Stress Tool will throw an error exception, and not perform correctly.</span></span> <span data-ttu-id="89fa9-114">在執行此工具前，請確定您符合這個必備需求。</span><span class="sxs-lookup"><span data-stu-id="89fa9-114">Make sure that you meet this prerequisite requirement prior to running the tool.</span></span> <span data-ttu-id="89fa9-115">如需有關安裝<STRONG>PsExec</STRONG>的詳細資訊， <A href="http://go.microsoft.com/fwlink/p/?linkid=282246">http://go.microsoft.com/fwlink/p/?LinkId=282246</A>請參閱。</span><span class="sxs-lookup"><span data-stu-id="89fa9-115">For details about installing <STRONG>PsExec.exe</STRONG>, see <A href="http://go.microsoft.com/fwlink/p/?linkid=282246">http://go.microsoft.com/fwlink/p/?LinkId=282246</A>.</span></span>



</div>

</div>

<div>

## <a name="supported-environments"></a><span data-ttu-id="89fa9-116">支援的環境</span><span class="sxs-lookup"><span data-stu-id="89fa9-116">Supported Environments</span></span>

<span data-ttu-id="89fa9-117">為了獲得最佳效能，Lync Server 2013、資源套件工具應該安裝在相同的環境中，且與 Lync Server 2013 所需的規格相同。</span><span class="sxs-lookup"><span data-stu-id="89fa9-117">For optimal performance, the Lync Server 2013, Resource Kit Tools should be installed in the same environment and with the same specifications that are required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="89fa9-118">資源套件工具概述</span><span class="sxs-lookup"><span data-stu-id="89fa9-118">Resource Kit Tools Overview</span></span>

<span data-ttu-id="89fa9-119">以下是 Lync Server 2013 持續聊天資源套件中提供的工具。</span><span class="sxs-lookup"><span data-stu-id="89fa9-119">Here are the tools that are provided in the Lync Server 2013 Persistent Chat Resource Kit.</span></span> <span data-ttu-id="89fa9-120">下節提供每個工具的描述，包括需求與範例用法。</span><span class="sxs-lookup"><span data-stu-id="89fa9-120">The following section provides a description of each tool, including requirements and example usage.</span></span>

  - <span data-ttu-id="89fa9-121">AffCheck</span><span class="sxs-lookup"><span data-stu-id="89fa9-121">AffCheck</span></span>

  - <span data-ttu-id="89fa9-122">ChatMonitoringSummary</span><span class="sxs-lookup"><span data-stu-id="89fa9-122">ChatMonitoringSummary</span></span>

  - <span data-ttu-id="89fa9-123">ChatStress 工具</span><span class="sxs-lookup"><span data-stu-id="89fa9-123">ChatStress Tool</span></span>

  - <span data-ttu-id="89fa9-124">ChatUpgradeVerifier</span><span class="sxs-lookup"><span data-stu-id="89fa9-124">ChatUpgradeVerifier</span></span>

  - <span data-ttu-id="89fa9-125">ChatUsageReport</span><span class="sxs-lookup"><span data-stu-id="89fa9-125">ChatUsageReport</span></span>

  - <span data-ttu-id="89fa9-126">ScheduleADSyncforPrincipal</span><span class="sxs-lookup"><span data-stu-id="89fa9-126">ScheduleADSyncforPrincipal</span></span>

</div>

<div>

## <a name="affcheck"></a><span data-ttu-id="89fa9-127">AffCheck</span><span class="sxs-lookup"><span data-stu-id="89fa9-127">AffCheck</span></span>

<div>

## <a name="description"></a><span data-ttu-id="89fa9-128">描述</span><span class="sxs-lookup"><span data-stu-id="89fa9-128">Description</span></span>

<span data-ttu-id="89fa9-129">AffCheck 工具會確認持久的聊天后端資料庫使用者和群組隸屬關係記錄與 Active Directory 網域服務相符。</span><span class="sxs-lookup"><span data-stu-id="89fa9-129">The AffCheck tool confirms that the Persistent Chat back-end database user and group affiliation records match that of Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="89fa9-130">需求</span><span class="sxs-lookup"><span data-stu-id="89fa9-130">Requirements</span></span>

<span data-ttu-id="89fa9-131">此工具是與加入網域的電腦上的 PersistentChatResKit 安裝程式一起安裝。</span><span class="sxs-lookup"><span data-stu-id="89fa9-131">The tool is installed with the PersistentChatResKit installer on a domain joined machine.</span></span>

<span data-ttu-id="89fa9-132">運行該工具的使用者帳戶必須具備永久聊天后端資料庫和 Active Directory 網域服務的讀取存取權。</span><span class="sxs-lookup"><span data-stu-id="89fa9-132">The user account under which the tool is run must have Read access to the Persistent Chat back-end database and Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="89fa9-133">用法</span><span class="sxs-lookup"><span data-stu-id="89fa9-133">Usage</span></span>

<span data-ttu-id="89fa9-134">根據 config 檔案中的指示來設定 AffCheck 檔案，並在不含命令列參數的情況下執行 AffCheck 工具。</span><span class="sxs-lookup"><span data-stu-id="89fa9-134">Configure the AffCheck.exe.config file according to the instructions in the config file and run the AffCheck tool without command-line parameters.</span></span> <span data-ttu-id="89fa9-135">以下是預設 AffCheck 的內容。</span><span class="sxs-lookup"><span data-stu-id="89fa9-135">Following are the contents of the default AffCheck.exe.config.</span></span>

<span data-ttu-id="89fa9-136">**AffCheck：**</span><span class="sxs-lookup"><span data-stu-id="89fa9-136">**AffCheck.exe.config:**</span></span>

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <appSettings>
        <!--Domain Controller IP Address-->
        <add key="LDAP" value="LDAP://0.0.0.0/"/>
        
        <!-- Domain DN  This is case sensitive, it must match exactly-->
        <add key="DomainComponent" value ="DC=DOMAIN,DC=COM"/>
        
        <!--Domain Administrator Login and Password-->
        <add key="DomainLogin" value="DOMAIN\Administrator"/>
        <add key="DomainPassword" value ="password"/>
        
        <!-- Connection string to Group Chat Database-->
        <add key="ConnectionString" value="data source=SQL_SERVER\INSTANCE;initial catalog=DATABASE_NAME;integrated security=SSPI"/>
        
        <!--Check group affiliations-->
        <add key="CheckGroups" value="true"/>
        
        <!--Check user affilations-->
        <add key="CheckUsers" value="true"/>
        
        <!--List all affiliations if there is a mismatch between database and active directory-->
        <add key="ListAffiliations" value="true"/>
    
        <!--If you need to offset the results of the number of affilations in AD(can be negative to add to AD parent count)-->
        <add key="Offset" value ="0"/>
    
        <!--If you need to ignore certain parents, provide a semi colon delimitted list.-->
        <add key="Ignore" value ="DC=uatest,DC=test,DC=contoso,DC=com;DC=test,DC=contoso,DC=com"/>
      </appSettings>
    </configuration>
  ```
</div>

</div>

<div>

## <a name="chatmonitoringsummary"></a><span data-ttu-id="89fa9-137">ChatMonitoringSummary</span><span class="sxs-lookup"><span data-stu-id="89fa9-137">ChatMonitoringSummary</span></span>

<div>

## <a name="description"></a><span data-ttu-id="89fa9-138">描述</span><span class="sxs-lookup"><span data-stu-id="89fa9-138">Description</span></span>

<span data-ttu-id="89fa9-139">PersistentChatMonitoringSummary 工具會將持續聊天監視資訊從監視資料庫移至指定的 CSV 記錄檔。</span><span class="sxs-lookup"><span data-stu-id="89fa9-139">The PersistentChatMonitoringSummary tool moves Persistent Chat monitoring information from the monitoring database into a specified CSV log file.</span></span>

<span data-ttu-id="89fa9-140">CSV 檔案將會包含持續交談會話的細目分類，包括總會話數、成功的會話、意外的失敗、預期的失敗，以及診斷識別碼、失敗數與失敗描述所造成的意外失敗細目分類。</span><span class="sxs-lookup"><span data-stu-id="89fa9-140">The CSV file will contain a breakdown of Persistent Chat sessions by number of total sessions, successful sessions, unexpected failures, expected failures, and a breakdown of the unexpected failures by diagnostic ID, number of failures, and failure description.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="89fa9-141">需求</span><span class="sxs-lookup"><span data-stu-id="89fa9-141">Requirements</span></span>

<span data-ttu-id="89fa9-142">在可存取監視資料庫的已加入網域的電腦上，安裝持續式聊天資源套件工具。</span><span class="sxs-lookup"><span data-stu-id="89fa9-142">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Monitoring database.</span></span>

<span data-ttu-id="89fa9-143">執行工具所使用的使用者帳戶必須具備監視資料庫的讀取存取權。</span><span class="sxs-lookup"><span data-stu-id="89fa9-143">The user account under which the tool runs must have Read access to the Monitoring database.</span></span>

<span data-ttu-id="89fa9-144">檔案（PersistentChatMonitoringSummary）必須包含一個\<connectionStrings\>節，以定義監視資料庫的連線字串。</span><span class="sxs-lookup"><span data-stu-id="89fa9-144">The file, PersistentChatMonitoringSummary.exe.config, must contain a \<connectionStrings\> section that defines the connection string to the Monitoring database.</span></span> <span data-ttu-id="89fa9-145">它也必須包含要收集監視資料之 PersistentChatEndpointUri 的索引鍵，以及將產生的 CSV 檔案位置的檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="89fa9-145">It must also contain a key for the PersistentChatEndpointUri that the monitoring data will be gathered for, and a file path to a location for the CSV file that will be generated.</span></span> <span data-ttu-id="89fa9-146">如需範例，請參閱已安裝的設定檔。</span><span class="sxs-lookup"><span data-stu-id="89fa9-146">Refer to the installed config file for examples.</span></span> <span data-ttu-id="89fa9-147">檔案必須與工具位於同一個目錄中。</span><span class="sxs-lookup"><span data-stu-id="89fa9-147">The file must be located in the same directory as the tool.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="89fa9-148">用法</span><span class="sxs-lookup"><span data-stu-id="89fa9-148">Usage</span></span>

```Batch
    PersistentChatMonitoringSummary [-StartDateTime <date>] [-EndDateTime <date>]
```

<span data-ttu-id="89fa9-149">這些參數定義資料的選取範圍：</span><span class="sxs-lookup"><span data-stu-id="89fa9-149">These parameters define the selection of data:</span></span>

<span data-ttu-id="89fa9-150">**StartDateTime：** 或者，您也可以指定選取期間的開始日期。</span><span class="sxs-lookup"><span data-stu-id="89fa9-150">**StartDateTime:** Optionally specifies the start date of the selection period.</span></span> <span data-ttu-id="89fa9-151">預設值： 1/1/1753 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="89fa9-151">Default: 1/1/1753 12:00:00 AM</span></span>

<span data-ttu-id="89fa9-152">**EndDateTime：** 或者，您也可以指定選取期間的最後一個日期。</span><span class="sxs-lookup"><span data-stu-id="89fa9-152">**EndDateTime:** Optionally specifies the last date of the selection period.</span></span> <span data-ttu-id="89fa9-153">預設值： Now</span><span class="sxs-lookup"><span data-stu-id="89fa9-153">Default: Now</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="89fa9-154">範例</span><span class="sxs-lookup"><span data-stu-id="89fa9-154">Example</span></span>

```Batch
    C:\Users\Administrator.VDOMAIN>Desktop\PersistentChatMonitoringSummary.exe
    Reading database connection information, Persistent Chat endpoint uri, and csv output path information from the application config file...
    Connecting to Monitoring database with connection string specified in the application config file...
    Gathering Persistent Chat Session Summary information between "1/1/1753 12:00:00 AM" and "11/19/2012 10:11:25 AM" for Persistent Chat Endpoint Uri "persistentChatEndpointUri@domain.com"...
    Press enter to continue or hit ctr-c if these settings are incorrect...
    
    The summary information about Persistent Chat sessions from the Monitoring database has been output to C:\PersistentChatMonitoring_dd4ace24-4c8a-4a3d-8fd4-591bdfacf47b.csv
    Press enter to exit...
```

</div>

</div>

<div>

## <a name="persistent-chat-stress-tool"></a><span data-ttu-id="89fa9-155">持續聊天的壓力工具</span><span class="sxs-lookup"><span data-stu-id="89fa9-155">Persistent Chat Stress Tool</span></span>

<div>

## <a name="description"></a><span data-ttu-id="89fa9-156">描述</span><span class="sxs-lookup"><span data-stu-id="89fa9-156">Description</span></span>

<span data-ttu-id="89fa9-157">持續聊天的壓力工具提供一種簡單的方法來模擬持久聊天的使用方式，以測試真實世界的效能，包括各種使用者模型，以更適合您預期的使用方式。</span><span class="sxs-lookup"><span data-stu-id="89fa9-157">The Persistent Chat Stress tool provides an easy way to simulate usage of Persistent Chat to test real-world performance, including varied user models to better fit your expected usage scenarios.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="89fa9-158">需求</span><span class="sxs-lookup"><span data-stu-id="89fa9-158">Requirements</span></span>

<span data-ttu-id="89fa9-159">將持續性聊天資源套件工具安裝在可存取持久聊天后端資料庫的網域加入的電腦上。</span><span class="sxs-lookup"><span data-stu-id="89fa9-159">Install the Persistent Chat Resource Kit tools onto a domain-joined machine that has access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="89fa9-160">除了此*控制器*電腦之外，您還需要幾個*載入程式*電腦。</span><span class="sxs-lookup"><span data-stu-id="89fa9-160">In addition to this *controller* machine, you will need several *loader* machines.</span></span> <span data-ttu-id="89fa9-161">針對使用者模型中的每個10K 使用者，您在載入程式電腦上至少需要4GB 的可用 RAM。</span><span class="sxs-lookup"><span data-stu-id="89fa9-161">For every 10K users in your user model, you will need at least 4GB of free RAM on a loader machine.</span></span> <span data-ttu-id="89fa9-162">例如，執行80K 的使用者將需要在所有載入程式電腦上散佈 32GB RAM。</span><span class="sxs-lookup"><span data-stu-id="89fa9-162">For example, a run with 80K users will require about 32GB of RAM spread across all loader machines.</span></span> <span data-ttu-id="89fa9-163">建議您至少擁有三個載入程式電腦，而不考慮預期的載入。</span><span class="sxs-lookup"><span data-stu-id="89fa9-163">We recommend that you have at least three loader machines, regardless of expected load.</span></span>

<span data-ttu-id="89fa9-164">載入程式電腦必須裝有 .NET 4.5 架構以及安裝 Visual c + + 2012 可再發行的元件。</span><span class="sxs-lookup"><span data-stu-id="89fa9-164">Loader machines must have the .NET 4.5 Framework as well as the Visual C++ 2012 Redistributable installed.</span></span>

</div>

<div>

## <a name="configuration"></a><span data-ttu-id="89fa9-165">Configuration</span><span class="sxs-lookup"><span data-stu-id="89fa9-165">Configuration</span></span>

<span data-ttu-id="89fa9-166">將 ChatStressTool 檔案複製到可從所有載入程式電腦存取的共用資料夾。</span><span class="sxs-lookup"><span data-stu-id="89fa9-166">Copy ChatStressTool files into a shared folder accessible from all loader machines.</span></span>

<span data-ttu-id="89fa9-167">建立使用者和頻道，以在壓力執行中使用：</span><span class="sxs-lookup"><span data-stu-id="89fa9-167">Create users and channels for use in the stress run:</span></span>

  - <span data-ttu-id="89fa9-168">建立與您的使用者模型通話對應的使用者數目、啟用 Lync 並將其持續聊天原則設定為 [啟用]。</span><span class="sxs-lookup"><span data-stu-id="89fa9-168">Create as many users as your user model calls for, enable them for Lync, and set their Persistent Chat policy to Enabled.</span></span>

  - <span data-ttu-id="89fa9-169">為您的壓力通道建立類別，然後根據該類別所需建立的會議室。</span><span class="sxs-lookup"><span data-stu-id="89fa9-169">Create a category for your stress channels, and then create as many rooms as are needed under that category.</span></span> <span data-ttu-id="89fa9-170">該類別應該將所有壓力使用者放在其**允許**清單中（透過新增其 OU），而壓力室應該有**開啟**的隱私權設定。</span><span class="sxs-lookup"><span data-stu-id="89fa9-170">The category should have all stress users in its **Allowed** list (by way of adding their OU), and stress rooms should have a privacy setting of **Open**.</span></span>

  - <span data-ttu-id="89fa9-171">我們建議您建立額外的壓力房間。</span><span class="sxs-lookup"><span data-stu-id="89fa9-171">We recommend creating extra stress rooms.</span></span> <span data-ttu-id="89fa9-172">您可以使用下列 Windows PowerShell 命令列介面命令來建立50000聊天室：</span><span class="sxs-lookup"><span data-stu-id="89fa9-172">You can create 50,000 rooms with the following Windows PowerShell command-line interface command:</span></span>
    ```Powershell
        for ($i = 0; $i -le 50000; $i++) { New-CsPersistentChatRoom -Category <parent category> -Name "StressChan_$i" -Privacy Open }
    ```    

<span data-ttu-id="89fa9-173">編輯設定檔以符合您的拓撲：</span><span class="sxs-lookup"><span data-stu-id="89fa9-173">Edit the configuration files to fit your topology:</span></span>

<span data-ttu-id="89fa9-174">在**LoaderProcess**中，將 "controller.contoso.com" 變更為控制器電腦的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="89fa9-174">In **LoaderProcess.exe.config**, change “controller.contoso.com” to the controller machine’s fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="89fa9-175">在**StressLauncher：**</span><span class="sxs-lookup"><span data-stu-id="89fa9-175">In **StressLauncher.exe.config:**</span></span>

1.  <span data-ttu-id="89fa9-176">將 "LoaderBinary" 設定值變更為共用資料夾的路徑。</span><span class="sxs-lookup"><span data-stu-id="89fa9-176">Change the “LoaderBinary” setting value to the shared folder’s path.</span></span>

2.  <span data-ttu-id="89fa9-177">將 "AdminUser"/"AdminPassword" 變更為具備載入程式電腦系統管理員存取權的認證。</span><span class="sxs-lookup"><span data-stu-id="89fa9-177">Change “AdminUser”/”AdminPassword” to credentials that have admin access to loader machines.</span></span>

3.  <span data-ttu-id="89fa9-178">將 "ChannelCategory" 變更為已建立應力通道的類別名稱。</span><span class="sxs-lookup"><span data-stu-id="89fa9-178">Change “ChannelCategory” to the name of the category that stress channels have been created under.</span></span>

4.  <span data-ttu-id="89fa9-179">將 "UserNamePattern" 和 "UserPasswordPattern" 變更為符合您的壓力使用者認證的範本。</span><span class="sxs-lookup"><span data-stu-id="89fa9-179">Change “UserNamePattern” and “UserPasswordPattern” to a template that matches your stress user credentials.</span></span> <span data-ttu-id="89fa9-180">{0}會以使用者的索引號碼取代。</span><span class="sxs-lookup"><span data-stu-id="89fa9-180">{0} is replaced with the user’s index number.</span></span>

5.  <span data-ttu-id="89fa9-181">將 "Domain" 變更為您測試拓朴的 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="89fa9-181">Change “Domain” to the SIP domain of your test topology.</span></span>

6.  <span data-ttu-id="89fa9-182">將 "ConnectionString" 變更為持續式聊天后端資料庫的連線字串。</span><span class="sxs-lookup"><span data-stu-id="89fa9-182">Change “ConnectionString” to a connection string for your Persistent Chat back-end database.</span></span>

7.  <span data-ttu-id="89fa9-183">將 "UserIndexStart" 變更為第一個壓力使用者的索引。</span><span class="sxs-lookup"><span data-stu-id="89fa9-183">Change “UserIndexStart” to the index of the first stress user.</span></span>

8.  <span data-ttu-id="89fa9-184">將 "LyncFQDN" 變更為您的前臺端池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="89fa9-184">Change “LyncFQDN” to the FQDN of your Front End pool.</span></span>

9.  <span data-ttu-id="89fa9-185">修改 [電腦] 清單，以包含所有載入程式電腦的電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="89fa9-185">Modify the “Machines” list to include machine names for all of your loader machines.</span></span>

10. <span data-ttu-id="89fa9-186">將服務端點的 baseAddress （預設為 "controller.contoso.com"）變更為控制器電腦的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="89fa9-186">Change the baseAddress of the service endpoint (default is “controller.contoso.com”) to the FQDN of your controller machine.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="89fa9-187">用法</span><span class="sxs-lookup"><span data-stu-id="89fa9-187">Usage</span></span>

<span data-ttu-id="89fa9-188">完成設定之後，請在控制器電腦上開啟 StressLauncher。</span><span class="sxs-lookup"><span data-stu-id="89fa9-188">After configuration is complete, open StressLauncher.exe on the controller machine.</span></span> <span data-ttu-id="89fa9-189">您可以以任何使用者的身分啟動 StressLauncher。</span><span class="sxs-lookup"><span data-stu-id="89fa9-189">You can launch StressLauncher as any user.</span></span> <span data-ttu-id="89fa9-190">在載入程式電腦上開機載入程式的認證，必須在 config 檔案中指定。</span><span class="sxs-lookup"><span data-stu-id="89fa9-190">The credentials under which the loader processes start on the loader machines must be specified in the config file.</span></span> <span data-ttu-id="89fa9-191">您也必須提供具有永久聊天后端資料庫讀取存取權的連線字串。</span><span class="sxs-lookup"><span data-stu-id="89fa9-191">You also must give a connection string that has Read access to the Persistent Chat back-end database.</span></span> <span data-ttu-id="89fa9-192">如果這個連線字串使用集成的 Windows 驗證，您必須以擁有此存取權的使用者身分啟動 StressLauncher。</span><span class="sxs-lookup"><span data-stu-id="89fa9-192">If this connection string uses integrated Windows authentication, you must launch StressLauncher as a user that has this access.</span></span>

<span data-ttu-id="89fa9-193">視需要變更使用者模型設定。</span><span class="sxs-lookup"><span data-stu-id="89fa9-193">Alter the user model settings as needed.</span></span> <span data-ttu-id="89fa9-194">按一下 [**開始載入**] 以啟動執行。</span><span class="sxs-lookup"><span data-stu-id="89fa9-194">Click **Start Load** to initiate a run.</span></span> <span data-ttu-id="89fa9-195">一分鐘之後，使用者就會開始登入，進度列就會開始進行填入。</span><span class="sxs-lookup"><span data-stu-id="89fa9-195">After a minute or so, users will start being signed in, and the progress bar will begin to fill.</span></span> <span data-ttu-id="89fa9-196">此時，控制器電腦可能能正常運作並採取效能測量。</span><span class="sxs-lookup"><span data-stu-id="89fa9-196">At this point, you may can the controller machine working and take performance measurements.</span></span>

</div>

</div>

<div>

## <a name="chatupgradeverifier"></a><span data-ttu-id="89fa9-197">ChatUpgradeVerifier</span><span class="sxs-lookup"><span data-stu-id="89fa9-197">ChatUpgradeVerifier</span></span>

<div>

## <a name="description"></a><span data-ttu-id="89fa9-198">描述</span><span class="sxs-lookup"><span data-stu-id="89fa9-198">Description</span></span>

<span data-ttu-id="89fa9-199">ChatUpgradeVerifier 是一種持續聊天的特定資料庫比較工具。</span><span class="sxs-lookup"><span data-stu-id="89fa9-199">ChatUpgradeVerifier is a Persistent Chat specific database comparison tool.</span></span> <span data-ttu-id="89fa9-200">此工具會將群組聊天 2007 R2 或群組聊天2010資料庫（2007/2010Db）與永久聊天2013資料庫（2013Db）進行比較。</span><span class="sxs-lookup"><span data-stu-id="89fa9-200">The tool compares either the Group Chat 2007 R2 or Group Chat 2010 Database (2007/2010Db) to the Persistent Chat 2013 Database (2013Db).</span></span>

<span data-ttu-id="89fa9-201">此工具會逐一檢查、每個類別、持續聊天室，以及 2007/2010Db 中的增益集，以查看它是否出現在2013Db 中。</span><span class="sxs-lookup"><span data-stu-id="89fa9-201">The tool will check, one by one, each category, Persistent Chat room, and add-in in 2007/2010Db to see if it appears in the 2013Db.</span></span> <span data-ttu-id="89fa9-202">比較包括檢查類別、聊天室、增益集、類別範圍中的所有設定，以及類別或聊天室上角色中的任何承擔者。</span><span class="sxs-lookup"><span data-stu-id="89fa9-202">The comparison includes checking all settings on the category, chat room, or add-in, any principals in scope on the category, and any principal in a role on either the category or the chat room.</span></span> <span data-ttu-id="89fa9-203">如果在2013Db 中沒有正確顯示類別或聊天室，則會將差異輸出到衝突檔案。</span><span class="sxs-lookup"><span data-stu-id="89fa9-203">If a category or a chat room does not appear correctly in the 2013Db, the differences will be output to a conflicts file.</span></span> <span data-ttu-id="89fa9-204">如果在進行升級之後，會變更 2007/2010Db，然後執行此工具，就會有與衝突檔案有關的差異輸出。</span><span class="sxs-lookup"><span data-stu-id="89fa9-204">If, after the upgrade has occurred, the 2007/2010Db is changed and then this tool is run, there will be a differences output to the conflicts file.</span></span> <span data-ttu-id="89fa9-205">請注意，此應用程式只是資料庫比較工具，不會驗證升級程式。</span><span class="sxs-lookup"><span data-stu-id="89fa9-205">Note that this application is a database comparison tool only and does not validate the upgrade process.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="89fa9-206">需求</span><span class="sxs-lookup"><span data-stu-id="89fa9-206">Requirements</span></span>

<span data-ttu-id="89fa9-207">在已加入網域的電腦上，安裝持續式聊天資源套件工具（可存取持續聊天后端資料庫）。</span><span class="sxs-lookup"><span data-stu-id="89fa9-207">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Persistent Chat back-end databases (previous and current versions for Persistent Chat).</span></span>

<span data-ttu-id="89fa9-208">執行工具所使用的使用者帳戶必須具備對持續聊天資料庫的讀取存取權。</span><span class="sxs-lookup"><span data-stu-id="89fa9-208">The user account under which the tool runs must have Read access to the Persistent Chat databases.</span></span>

<span data-ttu-id="89fa9-209">ChatUpgradeVerifier 檔案必須包含 GroupChat2007R2Db 參數或 GroupChat2010Db 參數，並將連接字串連至適當的群組聊天資料庫（Groupchat 2007R2 或2010）。</span><span class="sxs-lookup"><span data-stu-id="89fa9-209">The ChatUpgradeVerifier.exe.config file must contain either the GroupChat2007R2Db parameter or the GroupChat2010Db parameter, with a connection string to the appropriate Group Chat database (either Groupchat 2007R2 or 2010).</span></span> <span data-ttu-id="89fa9-210">它也必須包含 PersistentChat2013Db 參數，以及將連接字串連至持久聊天2013資料庫。</span><span class="sxs-lookup"><span data-stu-id="89fa9-210">It must also contain a PersistentChat2013Db parameter, with a connection string to the Persistent Chat 2013 database.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="89fa9-211">用法</span><span class="sxs-lookup"><span data-stu-id="89fa9-211">Usage</span></span>

<span data-ttu-id="89fa9-212">不需任何參數就能執行**ChatUpgradeVerifier** 。</span><span class="sxs-lookup"><span data-stu-id="89fa9-212">Run **ChatUpgradeVerifier** without any parameters.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="89fa9-213">範例</span><span class="sxs-lookup"><span data-stu-id="89fa9-213">Example</span></span>

<span data-ttu-id="89fa9-214">執行![ChatUpgradeVerifier。]執行(images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "ChatUpgradeVerifier。")</span><span class="sxs-lookup"><span data-stu-id="89fa9-214">![Running ChatUpgradeVerifier.exe.](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "Running ChatUpgradeVerifier.exe.")</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-usage-report"></a><span data-ttu-id="89fa9-215">持續聊天使用方式報告</span><span class="sxs-lookup"><span data-stu-id="89fa9-215">Persistent Chat Usage Report</span></span>

<div>

## <a name="description"></a><span data-ttu-id="89fa9-216">描述</span><span class="sxs-lookup"><span data-stu-id="89fa9-216">Description</span></span>

<span data-ttu-id="89fa9-217">ChatUsageReport 工具會產生持續聊天服務用法的 HTML 報告。</span><span class="sxs-lookup"><span data-stu-id="89fa9-217">The ChatUsageReport tool generates an HTML report of Persistent Chat service usage.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="89fa9-218">需求</span><span class="sxs-lookup"><span data-stu-id="89fa9-218">Requirements</span></span>

<span data-ttu-id="89fa9-219">在有權存取持久聊天后端資料庫的網域加入電腦上，安裝持續式聊天資源套件工具。</span><span class="sxs-lookup"><span data-stu-id="89fa9-219">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="89fa9-220">運行該工具的使用者帳戶必須具備永久聊天后端資料庫的讀取存取權。</span><span class="sxs-lookup"><span data-stu-id="89fa9-220">The user account under which the tool is run must have Read access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="89fa9-221">檔案（ChatUsageReport）必須包含一個\<connectionStrings\>區段，以定義持續聊天后端資料庫的連線字串。</span><span class="sxs-lookup"><span data-stu-id="89fa9-221">The file, ChatUsageReport.exe.config, must contain a \<connectionStrings\> section defining the connection string to the Persistent Chat back-end database.</span></span> <span data-ttu-id="89fa9-222">預設設定檔的內容如下所示，供您參考。</span><span class="sxs-lookup"><span data-stu-id="89fa9-222">The contents of the default config file are included here, for your reference.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="89fa9-223">用法</span><span class="sxs-lookup"><span data-stu-id="89fa9-223">Usage</span></span>

```Powershell
    ChatUsageReport [-StartDate {date}] [-EndDate {date}] [-TopActiveUsers {n}] [-TopActiveRooms {n}] [-LeastActiveRooms {n}] [-RoomsInactiveSince {Date}] [-OutputFolder {path}]
```
<span data-ttu-id="89fa9-224">這些參數定義資料的選取範圍：</span><span class="sxs-lookup"><span data-stu-id="89fa9-224">These parameters define the selection of data:</span></span>

<span data-ttu-id="89fa9-225">開始**日期：**（選擇性）指定選取期間的 UTC 開始日期。</span><span class="sxs-lookup"><span data-stu-id="89fa9-225">**StartDate:** Optionally specifies the UTC start date of the selection period.</span></span> <span data-ttu-id="89fa9-226">預設值：最早日期</span><span class="sxs-lookup"><span data-stu-id="89fa9-226">Default: Earliest Date</span></span>

<span data-ttu-id="89fa9-227">**結束日期：**（選擇性）指定選取期間的 UTC 結束日期。</span><span class="sxs-lookup"><span data-stu-id="89fa9-227">**EndDate:** Optionally specifies the UTC end date of the selection period.</span></span> <span data-ttu-id="89fa9-228">預設值： Now</span><span class="sxs-lookup"><span data-stu-id="89fa9-228">Default: Now</span></span>

<span data-ttu-id="89fa9-229">這些參數定義資料的顯示方式及顯示方式：</span><span class="sxs-lookup"><span data-stu-id="89fa9-229">These parameters define how and what data is displayed:</span></span>

<span data-ttu-id="89fa9-230">**TopActiveUsers：** 如果指定此選項，報告將會包含 n 個最活躍的使用者，就是使用者在所選期間在聊天室中張貼的訊息數目。</span><span class="sxs-lookup"><span data-stu-id="89fa9-230">**TopActiveUsers:** If this is specified, the report will include the n most active users in terms of the number of messages the user has posted in the chat room for the selected period.</span></span> <span data-ttu-id="89fa9-231">預設值：10</span><span class="sxs-lookup"><span data-stu-id="89fa9-231">Default: 10</span></span>

<span data-ttu-id="89fa9-232">**TopActiveRooms：** 如果指定此選項，報告將會包含 n 個最活躍的聊天室，就是在所選期間內的會議室中張貼的訊息數目。</span><span class="sxs-lookup"><span data-stu-id="89fa9-232">**TopActiveRooms:** If this is specified, the report will include the n most active chat rooms in terms of the number of messages posted in the room for the selected period.</span></span> <span data-ttu-id="89fa9-233">預設值：10</span><span class="sxs-lookup"><span data-stu-id="89fa9-233">Default: 10</span></span>

<span data-ttu-id="89fa9-234">**LeastActiveRooms：** 如果已指定此選項，報告將會包含 n 個最小作用中的聊天室，就是在所選期間的聊天室中張貼的訊息數目。</span><span class="sxs-lookup"><span data-stu-id="89fa9-234">**LeastActiveRooms:** If this is specified, the report will include the n least active chat rooms in terms of the number of messages posted in the chat room for the selected period.</span></span> <span data-ttu-id="89fa9-235">會議室將至少公佈一封郵件。</span><span class="sxs-lookup"><span data-stu-id="89fa9-235">Rooms will have at least one message posted.</span></span> <span data-ttu-id="89fa9-236">預設值：10</span><span class="sxs-lookup"><span data-stu-id="89fa9-236">Default: 10</span></span>

<span data-ttu-id="89fa9-237">**RoomsInactiveSince：** 如果指定此選項，報告將會包含自指定日期之後處於非作用中狀態的聊天室清單。</span><span class="sxs-lookup"><span data-stu-id="89fa9-237">**RoomsInactiveSince:** If this is specified, the report will include a list of chat rooms that have been inactive since the specified date.</span></span> <span data-ttu-id="89fa9-238">預設值：整個時間</span><span class="sxs-lookup"><span data-stu-id="89fa9-238">Default: Entire Time</span></span>

<span data-ttu-id="89fa9-239">**OutputFolder：** 將放置 ChatUsageReport 及圖形影像的資料夾。</span><span class="sxs-lookup"><span data-stu-id="89fa9-239">**OutputFolder:** The folder where the ChatUsageReport.html and the graph images will be placed.</span></span> <span data-ttu-id="89fa9-240">這必須在 config 檔案或命令列中定義。</span><span class="sxs-lookup"><span data-stu-id="89fa9-240">This must be defined in the config file or on the command line.</span></span>

<span data-ttu-id="89fa9-241">您也可以在與工具位於同一個目錄中的 ChatUsageReport 檔案中，指定所有的命令列參數值。</span><span class="sxs-lookup"><span data-stu-id="89fa9-241">All of the command line parameter values can also be specified in the ChatUsageReport.exe.config file that is located in the same directory as the tool.</span></span> <span data-ttu-id="89fa9-242">如果在 config 檔案和命令列中都指定了任何值，命令列值將會覆寫 config 檔值。</span><span class="sxs-lookup"><span data-stu-id="89fa9-242">If any value is specified in both the config file and the command line, the command line value will override the config file value.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="89fa9-243">收</span><span class="sxs-lookup"><span data-stu-id="89fa9-243">Output</span></span>

<span data-ttu-id="89fa9-244">報告將永遠包含下列輸出：</span><span class="sxs-lookup"><span data-stu-id="89fa9-244">The report will always include the following output:</span></span>

  - <span data-ttu-id="89fa9-245">最多 n 個最活躍的聊天室，由所選時段內的訊息文章數量所組成。</span><span class="sxs-lookup"><span data-stu-id="89fa9-245">Top n most active chat rooms by number of message posts for selected period.</span></span>

  - <span data-ttu-id="89fa9-246">最多 n 個作用中的使用者，由所選時段內的郵件投遞數來排列。</span><span class="sxs-lookup"><span data-stu-id="89fa9-246">Top n most active users by number of message posts for selected period.</span></span>

  - <span data-ttu-id="89fa9-247">前 n 個最小作用中的聊天室，由所選時段內的訊息文章數量所組成。</span><span class="sxs-lookup"><span data-stu-id="89fa9-247">Top n least active chat rooms by number of message posts for selected period.</span></span>

  - <span data-ttu-id="89fa9-248">在資料庫的整個生命週期中，或從指定的日期起停用的聊天室。</span><span class="sxs-lookup"><span data-stu-id="89fa9-248">Chat rooms that are inactive for the entire life of the database, or since the specified date.</span></span>

  - <span data-ttu-id="89fa9-249">所選期間的每日訊息後續趨勢。</span><span class="sxs-lookup"><span data-stu-id="89fa9-249">Daily message post trend for selected period.</span></span>

  - <span data-ttu-id="89fa9-250">所選期間的每週訊息張貼趨勢。</span><span class="sxs-lookup"><span data-stu-id="89fa9-250">Weekly message post trend for selected period.</span></span>

  - <span data-ttu-id="89fa9-251">所選期間的每月訊息文章趨勢。</span><span class="sxs-lookup"><span data-stu-id="89fa9-251">Monthly message post trend for selected period.</span></span>

  - <span data-ttu-id="89fa9-252">所選期間內的郵件投遞總數。</span><span class="sxs-lookup"><span data-stu-id="89fa9-252">Total message posts for selected period.</span></span>

  - <span data-ttu-id="89fa9-253">已啟用的會議室總數。</span><span class="sxs-lookup"><span data-stu-id="89fa9-253">Total number of enabled rooms.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="89fa9-254">範例</span><span class="sxs-lookup"><span data-stu-id="89fa9-254">Example</span></span>

<span data-ttu-id="89fa9-255">下列範例會產生整個2001年的使用方式報告，並將報告放在 ChatUsageReport 中指定的 OutputFolder 中。</span><span class="sxs-lookup"><span data-stu-id="89fa9-255">The following example generates a usage report for the entire year 2001 and places the report in the OutputFolder specified in the ChatUsageReport.exe.config.</span></span>

```Powershell
    ChatUsageReport -RoomsInactiveSince 06-20-2010
```
<span data-ttu-id="89fa9-256">ChatUsageReport：</span><span class="sxs-lookup"><span data-stu-id="89fa9-256">ChatUsageReport.exe.config:</span></span>

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <connectionStrings>
        <!-- The PersistentChat connection string must be defined in this file. -->
        <add name="PersistentChat" connectionString="Data Source=contoso.com\RTC;Initial Catalog=mgc;Integrated Security=SSPI"/>
      </connectionStrings>
      <appSettings>
        <!-- The OutputFolder must be defined here or on the command line. -->
        <add key="OutputFolder" value="."/>
        <!-- The values below are the same as the application defaults. -->
        <add key="StartDate" value="01/01/0001"/>
        <add key="EndDate" value="12/31/9999"/>
        <add key="TopActiveUsers" value="10"/>
        <add key="TopActiveRooms" value="10"/>
        <add key="LeastActiveRooms" value="10"/>
        <add key="RoomsInactiveSince" value="01/01/0001"/>
      </appSettings>
    </configuration></configuration>
```
</div>

</div>

<div>

## <a name="scheduleadsyncforprincipal"></a><span data-ttu-id="89fa9-257">ScheduleADSyncForPrincipal</span><span class="sxs-lookup"><span data-stu-id="89fa9-257">ScheduleADSyncForPrincipal</span></span>

<div>

## <a name="description"></a><span data-ttu-id="89fa9-258">描述</span><span class="sxs-lookup"><span data-stu-id="89fa9-258">Description</span></span>

<span data-ttu-id="89fa9-259">ScheduleADSyncForPrincipal 是 Microsoft SQL Server 2012 腳本，在連線至持久聊天后端資料庫時，必須直接在 SQL Server Management Studio 中執行。</span><span class="sxs-lookup"><span data-stu-id="89fa9-259">ScheduleADSyncForPrincipal is a Microsoft SQL Server 2012 script that must be run directly from within SQL Server Management Studio when connected to the Persistent Chat back-end database.</span></span> <span data-ttu-id="89fa9-260">此腳本可讓您強制持續聊天與 Active Directory 網域服務的使用者記錄同步處理，而不是等待排程的同步處理時間。</span><span class="sxs-lookup"><span data-stu-id="89fa9-260">This script enables you to force Persistent Chat to synchronize its records of a user with those of Active Directory Domain Services, rather than waiting for the scheduled synchronization time.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="89fa9-261">需求</span><span class="sxs-lookup"><span data-stu-id="89fa9-261">Requirements</span></span>

<span data-ttu-id="89fa9-262">執行腳本的使用者帳戶必須擁有持久聊天后端資料庫的擁有者存取權。</span><span class="sxs-lookup"><span data-stu-id="89fa9-262">The user account under which the script is run must have owner access to the Persistent Chat back-end database.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="89fa9-263">用法</span><span class="sxs-lookup"><span data-stu-id="89fa9-263">Usage</span></span>

<span data-ttu-id="89fa9-264">以下是預設腳本的內容：</span><span class="sxs-lookup"><span data-stu-id="89fa9-264">Following are the contents of the default script:</span></span>

```Powershell
    /*
    This script will schedule a principal for a forced AD synchronization cycle
    
    If you're using Sql Server Management Studio, pressing Ctrl+Shift+M will 
    allow you to specify values for the template parameter.
    */
    
        insert into
          tblPrincipalMeta
          (
           prinID
          ,prinAffiliationsDirty
          ,prinAttributesDirty
          ,prinDeleted
          )
          select
            prinID
           ,1
           ,1
           ,0
          from
            tblPrincipal
          where
            prinID not in (select prinID from tblPrincipalMeta) and
            prinID = <PrinID,int,0>
     
        update
          tblPrincipalMeta
        set
          prinAffiliationsDirty = 1
         ,prinAttributesDirty = 1
         ,tryCount = 0
         ,nextTry = null
        where
         prinID = <PrinID,int,0>
```

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

