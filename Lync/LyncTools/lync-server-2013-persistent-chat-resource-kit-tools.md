---
title: Lync Server 2013 持久聊天資源套件工具
description: Lync Server 2013 Persistent Chat Resource 工具組工具。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Persistent Chat Resource Kit Tools
ms:assetid: 7a34d2ba-eb25-4e22-92d1-b9baf81b102c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945599(v=OCS.15)
ms:contentKeyID: 51541423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 336e81c97da73da47eee654161a7d8d8956f9edb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542349"
---
# <a name="lync-server-2013-persistent-chat-resource-kit-tools"></a><span data-ttu-id="24f3a-103">Lync Server 2013 持久聊天資源套件工具</span><span class="sxs-lookup"><span data-stu-id="24f3a-103">Lync Server 2013 Persistent Chat Resource Kit Tools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24f3a-104">_**主題上次修改日期：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="24f3a-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="24f3a-105">Lync Server 2013 持續性聊天資源套件工具可協助您讓部署及管理 Lync Server 2013 Persistent Chat Server 的 IT 系統管理員更輕鬆進行日常工作。</span><span class="sxs-lookup"><span data-stu-id="24f3a-105">The Lync Server 2013 Persistent Chat Resource Kit tools help to make routine tasks easier for IT administrators who deploy and manage Lync Server 2013 Persistent Chat Server.</span></span> <span data-ttu-id="24f3a-106">除了安裝指示之外，本主題也會說明每個工具的用途及其用法範例。</span><span class="sxs-lookup"><span data-stu-id="24f3a-106">In addition to installation instructions, this topic describes the purpose of each tool, and examples of its use.</span></span>

<div>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="24f3a-107">安裝資源工具組工具</span><span class="sxs-lookup"><span data-stu-id="24f3a-107">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="24f3a-108">若要安裝 Lync Server 2013，資源工具組工具，請下載 **PersistentChatReskit.msi**。</span><span class="sxs-lookup"><span data-stu-id="24f3a-108">To install the Lync Server 2013, Resource Kit Tools, download **PersistentChatReskit.msi**.</span></span> <span data-ttu-id="24f3a-109">執行 **PersistentChatReskit.msi** 以執行簡單安裝。</span><span class="sxs-lookup"><span data-stu-id="24f3a-109">Run **PersistentChatReskit.msi** to do a simple installation.</span></span> <span data-ttu-id="24f3a-110">.Msi 會安裝下列路徑中的所有工具： \\ **Program Files \\ Microsoft Lync Server 2013 \\ Persistent Chat Server Resource 工具組**。</span><span class="sxs-lookup"><span data-stu-id="24f3a-110">The .msi installs all the tools in the following path: \\**Program Files\\ Microsoft Lync Server 2013\\Persistent Chat Server Resource Kit**.</span></span> <span data-ttu-id="24f3a-111">屬於自包含可執行檔的工具位於此資料夾中。</span><span class="sxs-lookup"><span data-stu-id="24f3a-111">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="24f3a-112">也有檔案的工具位於自己的子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="24f3a-112">Tools that also have files are in their own subfolders.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="24f3a-113">安裝 Lync Server 2013 （資源套件工具）之後，您必須安裝<STRONG>PsExec.exe</STRONG> ，並將<STRONG>PsExec.exe</STRONG>複製到下列路徑： \\ <STRONG>Program Files \ Microsoft Lync Server 2013 \ Persistent Chat Server Resource Kit\ChatStressTool</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="24f3a-113">After installing the Lync Server 2013, Resource Kit Tools, you must install <STRONG>PsExec.exe</STRONG> and copy <STRONG>PsExec.exe</STRONG> to the following path: \\<STRONG>Program Files\ Microsoft Lync Server 2013\Persistent Chat Server Resource Kit\ChatStressTool</STRONG>.</span></span> <span data-ttu-id="24f3a-114">如果您未複製 <STRONG>PsExec.exe</STRONG>，Persistent 聊天工具將會引發錯誤例外狀況，而不會正確執行。</span><span class="sxs-lookup"><span data-stu-id="24f3a-114">If you do not copy <STRONG>PsExec.exe</STRONG>, the Persistent Chat Stress Tool will throw an error exception, and not perform correctly.</span></span> <span data-ttu-id="24f3a-115">在執行工具之前，請先確定您符合此必要條件。</span><span class="sxs-lookup"><span data-stu-id="24f3a-115">Make sure that you meet this prerequisite requirement prior to running the tool.</span></span> <span data-ttu-id="24f3a-116">如需安裝 <STRONG>PsExec.exe</STRONG>的詳細資訊，請參閱 <A href="https://go.microsoft.com/fwlink/p/?linkid=282246">https://go.microsoft.com/fwlink/p/?LinkId=282246</A> 。</span><span class="sxs-lookup"><span data-stu-id="24f3a-116">For details about installing <STRONG>PsExec.exe</STRONG>, see <A href="https://go.microsoft.com/fwlink/p/?linkid=282246">https://go.microsoft.com/fwlink/p/?LinkId=282246</A>.</span></span>



</div>

</div>

<div>

## <a name="supported-environments"></a><span data-ttu-id="24f3a-117">支援的環境</span><span class="sxs-lookup"><span data-stu-id="24f3a-117">Supported Environments</span></span>

<span data-ttu-id="24f3a-118">為了達到最佳效能，Lync Server 2013，資源工具組工具應該安裝在相同的環境中，且使用 Lync Server 2013 所需的相同規格。</span><span class="sxs-lookup"><span data-stu-id="24f3a-118">For optimal performance, the Lync Server 2013, Resource Kit Tools should be installed in the same environment and with the same specifications that are required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="24f3a-119">資源工具組工具概述</span><span class="sxs-lookup"><span data-stu-id="24f3a-119">Resource Kit Tools Overview</span></span>

<span data-ttu-id="24f3a-120">以下是 Lync Server 2013 Persistent Chat Resource 工具組中所提供的工具。</span><span class="sxs-lookup"><span data-stu-id="24f3a-120">Here are the tools that are provided in the Lync Server 2013 Persistent Chat Resource Kit.</span></span> <span data-ttu-id="24f3a-121">下節提供每個工具的描述，包括需求和範例用法。</span><span class="sxs-lookup"><span data-stu-id="24f3a-121">The following section provides a description of each tool, including requirements and example usage.</span></span>

  - <span data-ttu-id="24f3a-122">AffCheck</span><span class="sxs-lookup"><span data-stu-id="24f3a-122">AffCheck</span></span>

  - <span data-ttu-id="24f3a-123">ChatMonitoringSummary</span><span class="sxs-lookup"><span data-stu-id="24f3a-123">ChatMonitoringSummary</span></span>

  - <span data-ttu-id="24f3a-124">ChatStress 工具</span><span class="sxs-lookup"><span data-stu-id="24f3a-124">ChatStress Tool</span></span>

  - <span data-ttu-id="24f3a-125">ChatUpgradeVerifier</span><span class="sxs-lookup"><span data-stu-id="24f3a-125">ChatUpgradeVerifier</span></span>

  - <span data-ttu-id="24f3a-126">ChatUsageReport</span><span class="sxs-lookup"><span data-stu-id="24f3a-126">ChatUsageReport</span></span>

  - <span data-ttu-id="24f3a-127">ScheduleADSyncforPrincipal</span><span class="sxs-lookup"><span data-stu-id="24f3a-127">ScheduleADSyncforPrincipal</span></span>

</div>

<div>

## <a name="affcheck"></a><span data-ttu-id="24f3a-128">AffCheck</span><span class="sxs-lookup"><span data-stu-id="24f3a-128">AffCheck</span></span>

<div>

## <a name="description"></a><span data-ttu-id="24f3a-129">描述</span><span class="sxs-lookup"><span data-stu-id="24f3a-129">Description</span></span>

<span data-ttu-id="24f3a-130">AffCheck 工具會確認 Persistent 後端資料庫使用者和群組從屬記錄符合 Active Directory 網域服務。</span><span class="sxs-lookup"><span data-stu-id="24f3a-130">The AffCheck tool confirms that the Persistent Chat back-end database user and group affiliation records match that of Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="24f3a-131">需求</span><span class="sxs-lookup"><span data-stu-id="24f3a-131">Requirements</span></span>

<span data-ttu-id="24f3a-132">工具是隨加入網域的機器上的 PersistentChatResKit 安裝程式一起安裝。</span><span class="sxs-lookup"><span data-stu-id="24f3a-132">The tool is installed with the PersistentChatResKit installer on a domain joined machine.</span></span>

<span data-ttu-id="24f3a-133">執行此工具的使用者帳戶必須具有對 Persistent 後端資料庫和 Active Directory 網域服務的讀取權限。</span><span class="sxs-lookup"><span data-stu-id="24f3a-133">The user account under which the tool is run must have Read access to the Persistent Chat back-end database and Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="24f3a-134">Usage</span><span class="sxs-lookup"><span data-stu-id="24f3a-134">Usage</span></span>

<span data-ttu-id="24f3a-135">根據 config 檔案中的指示設定 AffCheck.exe.config 檔案，並執行不含命令列參數的 AffCheck 工具。</span><span class="sxs-lookup"><span data-stu-id="24f3a-135">Configure the AffCheck.exe.config file according to the instructions in the config file and run the AffCheck tool without command-line parameters.</span></span> <span data-ttu-id="24f3a-136">以下是預設 AffCheck.exe.config 的內容。</span><span class="sxs-lookup"><span data-stu-id="24f3a-136">Following are the contents of the default AffCheck.exe.config.</span></span>

<span data-ttu-id="24f3a-137">**AffCheck.exe.config：**</span><span class="sxs-lookup"><span data-stu-id="24f3a-137">**AffCheck.exe.config:**</span></span>

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

## <a name="chatmonitoringsummary"></a><span data-ttu-id="24f3a-138">ChatMonitoringSummary</span><span class="sxs-lookup"><span data-stu-id="24f3a-138">ChatMonitoringSummary</span></span>

<div>

## <a name="description"></a><span data-ttu-id="24f3a-139">描述</span><span class="sxs-lookup"><span data-stu-id="24f3a-139">Description</span></span>

<span data-ttu-id="24f3a-140">PersistentChatMonitoringSummary 工具會將持續性聊天監控資訊從監控資料庫移至指定的 CSV 記錄檔。</span><span class="sxs-lookup"><span data-stu-id="24f3a-140">The PersistentChatMonitoringSummary tool moves Persistent Chat monitoring information from the monitoring database into a specified CSV log file.</span></span>

<span data-ttu-id="24f3a-141">CSV 檔案會包含持續性聊天會話的分解，依總數：會話總數、成功的會話、意外失敗、預期的失敗，以及診斷識別碼、失敗次數和失敗描述的失敗的失敗情況。</span><span class="sxs-lookup"><span data-stu-id="24f3a-141">The CSV file will contain a breakdown of Persistent Chat sessions by number of total sessions, successful sessions, unexpected failures, expected failures, and a breakdown of the unexpected failures by diagnostic ID, number of failures, and failure description.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="24f3a-142">需求</span><span class="sxs-lookup"><span data-stu-id="24f3a-142">Requirements</span></span>

<span data-ttu-id="24f3a-143">在有權存取監控資料庫的已加入網域的機器上安裝 Persistent Chat Resource 工具組工具。</span><span class="sxs-lookup"><span data-stu-id="24f3a-143">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Monitoring database.</span></span>

<span data-ttu-id="24f3a-144">執行工具所使用的使用者帳戶，必須具備監控資料庫的讀取權限。</span><span class="sxs-lookup"><span data-stu-id="24f3a-144">The user account under which the tool runs must have Read access to the Monitoring database.</span></span>

<span data-ttu-id="24f3a-145">檔案（PersistentChatMonitoringSummary.exe.config）必須包含一個 \<connectionStrings\> 區段，以定義監控資料庫的連接字串。</span><span class="sxs-lookup"><span data-stu-id="24f3a-145">The file, PersistentChatMonitoringSummary.exe.config, must contain a \<connectionStrings\> section that defines the connection string to the Monitoring database.</span></span> <span data-ttu-id="24f3a-146">它還必須包含要針對其收集監控資料之 PersistentChatEndpointUri 的索引鍵，以及將產生之 CSV 檔案位置的檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="24f3a-146">It must also contain a key for the PersistentChatEndpointUri that the monitoring data will be gathered for, and a file path to a location for the CSV file that will be generated.</span></span> <span data-ttu-id="24f3a-147">如需範例，請參閱已安裝的設定檔。</span><span class="sxs-lookup"><span data-stu-id="24f3a-147">Refer to the installed config file for examples.</span></span> <span data-ttu-id="24f3a-148">檔案必須與工具位於相同的目錄中。</span><span class="sxs-lookup"><span data-stu-id="24f3a-148">The file must be located in the same directory as the tool.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="24f3a-149">Usage</span><span class="sxs-lookup"><span data-stu-id="24f3a-149">Usage</span></span>

```Batch
    PersistentChatMonitoringSummary [-StartDateTime <date>] [-EndDateTime <date>]
```

<span data-ttu-id="24f3a-150">這些參數會定義資料的選取專案：</span><span class="sxs-lookup"><span data-stu-id="24f3a-150">These parameters define the selection of data:</span></span>

<span data-ttu-id="24f3a-151">**StartDateTime：** （選用）指定選取期間的開始日期。</span><span class="sxs-lookup"><span data-stu-id="24f3a-151">**StartDateTime:** Optionally specifies the start date of the selection period.</span></span> <span data-ttu-id="24f3a-152">預設值： 1/1/1753 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="24f3a-152">Default: 1/1/1753 12:00:00 AM</span></span>

<span data-ttu-id="24f3a-153">**EndDateTime：** （選用）指定選取期間的最後一個日期。</span><span class="sxs-lookup"><span data-stu-id="24f3a-153">**EndDateTime:** Optionally specifies the last date of the selection period.</span></span> <span data-ttu-id="24f3a-154">預設值：現在</span><span class="sxs-lookup"><span data-stu-id="24f3a-154">Default: Now</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="24f3a-155">範例</span><span class="sxs-lookup"><span data-stu-id="24f3a-155">Example</span></span>

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

## <a name="persistent-chat-stress-tool"></a><span data-ttu-id="24f3a-156">Persistent Chat 應力工具</span><span class="sxs-lookup"><span data-stu-id="24f3a-156">Persistent Chat Stress Tool</span></span>

<div>

## <a name="description"></a><span data-ttu-id="24f3a-157">描述</span><span class="sxs-lookup"><span data-stu-id="24f3a-157">Description</span></span>

<span data-ttu-id="24f3a-158">Persistent Chat 應力工具提供一種簡單的方法，可模擬持續性聊天的使用方式，以測試實際效能，包括各種使用者模型，以更好地符合預期的使用案例。</span><span class="sxs-lookup"><span data-stu-id="24f3a-158">The Persistent Chat Stress tool provides an easy way to simulate usage of Persistent Chat to test real-world performance, including varied user models to better fit your expected usage scenarios.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="24f3a-159">需求</span><span class="sxs-lookup"><span data-stu-id="24f3a-159">Requirements</span></span>

<span data-ttu-id="24f3a-160">將 Persistent Chat Resource 工具組工具安裝至可存取 Persistent 後端資料庫的已加入網域的電腦上。</span><span class="sxs-lookup"><span data-stu-id="24f3a-160">Install the Persistent Chat Resource Kit tools onto a domain-joined machine that has access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="24f3a-161">除了此 *控制器* 電腦之外，您還需要數個 *載入程式* 電腦。</span><span class="sxs-lookup"><span data-stu-id="24f3a-161">In addition to this *controller* machine, you will need several *loader* machines.</span></span> <span data-ttu-id="24f3a-162">針對使用者模型中的每個10K 使用者，您至少要有4GB 載入器電腦上的可用記憶體。</span><span class="sxs-lookup"><span data-stu-id="24f3a-162">For every 10K users in your user model, you will need at least 4GB of free RAM on a loader machine.</span></span> <span data-ttu-id="24f3a-163">例如，以80K 使用者執行的使用者將需要所有載入程式電腦上的 RAM 散佈32GB。</span><span class="sxs-lookup"><span data-stu-id="24f3a-163">For example, a run with 80K users will require about 32GB of RAM spread across all loader machines.</span></span> <span data-ttu-id="24f3a-164">建議您至少有三個載入程式電腦，不論預期的負載為何。</span><span class="sxs-lookup"><span data-stu-id="24f3a-164">We recommend that you have at least three loader machines, regardless of expected load.</span></span>

<span data-ttu-id="24f3a-165">載入程式機器必須已安裝 .NET 4.5 Framework 和 Visual c + + 2012 可轉散發元件。</span><span class="sxs-lookup"><span data-stu-id="24f3a-165">Loader machines must have the .NET 4.5 Framework as well as the Visual C++ 2012 Redistributable installed.</span></span>

</div>

<div>

## <a name="configuration"></a><span data-ttu-id="24f3a-166">組態</span><span class="sxs-lookup"><span data-stu-id="24f3a-166">Configuration</span></span>

<span data-ttu-id="24f3a-167">將 ChatStressTool 檔案複製到可從所有載入程式機器存取的共用資料夾。</span><span class="sxs-lookup"><span data-stu-id="24f3a-167">Copy ChatStressTool files into a shared folder accessible from all loader machines.</span></span>

<span data-ttu-id="24f3a-168">建立用於壓力執行的使用者和通道：</span><span class="sxs-lookup"><span data-stu-id="24f3a-168">Create users and channels for use in the stress run:</span></span>

  - <span data-ttu-id="24f3a-169">建立您的使用者模型所撥打的任意數目的使用者、啟用 Lync 的使用者，並將其 Persistent 聊天原則設定為 [啟用]。</span><span class="sxs-lookup"><span data-stu-id="24f3a-169">Create as many users as your user model calls for, enable them for Lync, and set their Persistent Chat policy to Enabled.</span></span>

  - <span data-ttu-id="24f3a-170">建立壓力通道的類別，然後建立該類別下所需的任意會議室。</span><span class="sxs-lookup"><span data-stu-id="24f3a-170">Create a category for your stress channels, and then create as many rooms as are needed under that category.</span></span> <span data-ttu-id="24f3a-171">類別應該會在其 **允許** 的清單中有所有壓力使用者 (以加入其 OU) 的方式，而壓力房間應具備 **開啟**的隱私權設定。</span><span class="sxs-lookup"><span data-stu-id="24f3a-171">The category should have all stress users in its **Allowed** list (by way of adding their OU), and stress rooms should have a privacy setting of **Open**.</span></span>

  - <span data-ttu-id="24f3a-172">我們建議您建立額外的壓力房間。</span><span class="sxs-lookup"><span data-stu-id="24f3a-172">We recommend creating extra stress rooms.</span></span> <span data-ttu-id="24f3a-173">您可以使用下列 Windows PowerShell 命令列介面命令來建立50000聊天室：</span><span class="sxs-lookup"><span data-stu-id="24f3a-173">You can create 50,000 rooms with the following Windows PowerShell command-line interface command:</span></span>
    ```Powershell
        for ($i = 0; $i -le 50000; $i++) { New-CsPersistentChatRoom -Category <parent category> -Name "StressChan_$i" -Privacy Open }
    ```    

<span data-ttu-id="24f3a-174">編輯設定檔，以符合您的拓撲：</span><span class="sxs-lookup"><span data-stu-id="24f3a-174">Edit the configuration files to fit your topology:</span></span>

<span data-ttu-id="24f3a-175">在 **LoaderProcess.exe.config**中，將 "controller.contoso.com" 變更為 controller MACHINE (FQDN) 的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="24f3a-175">In **LoaderProcess.exe.config**, change “controller.contoso.com” to the controller machine’s fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="24f3a-176">在 **StressLauncher.exe.config 中：**</span><span class="sxs-lookup"><span data-stu-id="24f3a-176">In **StressLauncher.exe.config:**</span></span>

1.  <span data-ttu-id="24f3a-177">將 "LoaderBinary" 設定值變更為共用資料夾的路徑。</span><span class="sxs-lookup"><span data-stu-id="24f3a-177">Change the “LoaderBinary” setting value to the shared folder’s path.</span></span>

2.  <span data-ttu-id="24f3a-178">將 "AdminUser"/"AdminPassword" 變更為具備載入程式電腦系統管理員存取權的認證。</span><span class="sxs-lookup"><span data-stu-id="24f3a-178">Change “AdminUser”/”AdminPassword” to credentials that have admin access to loader machines.</span></span>

3.  <span data-ttu-id="24f3a-179">將 "ChannelCategory" 變更為已在其下建立壓力通道的類別名稱。</span><span class="sxs-lookup"><span data-stu-id="24f3a-179">Change “ChannelCategory” to the name of the category that stress channels have been created under.</span></span>

4.  <span data-ttu-id="24f3a-180">將 "UserNamePattern" 和 "UserPasswordPattern" 變更為符合您的壓力使用者認證的範本。</span><span class="sxs-lookup"><span data-stu-id="24f3a-180">Change “UserNamePattern” and “UserPasswordPattern” to a template that matches your stress user credentials.</span></span> <span data-ttu-id="24f3a-181">{0} 會取代為使用者的索引編號。</span><span class="sxs-lookup"><span data-stu-id="24f3a-181">{0} is replaced with the user’s index number.</span></span>

5.  <span data-ttu-id="24f3a-182">將 "Domain" 變更為測試拓撲的 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="24f3a-182">Change “Domain” to the SIP domain of your test topology.</span></span>

6.  <span data-ttu-id="24f3a-183">將 "ConnectionString" 變更為您的持久聊天后端資料庫的連接字串。</span><span class="sxs-lookup"><span data-stu-id="24f3a-183">Change “ConnectionString” to a connection string for your Persistent Chat back-end database.</span></span>

7.  <span data-ttu-id="24f3a-184">將 "UserIndexStart" 變更為第一個應力使用者的索引。</span><span class="sxs-lookup"><span data-stu-id="24f3a-184">Change “UserIndexStart” to the index of the first stress user.</span></span>

8.  <span data-ttu-id="24f3a-185">將 "LyncFQDN" 變更為前端集區的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="24f3a-185">Change “LyncFQDN” to the FQDN of your Front End pool.</span></span>

9.  <span data-ttu-id="24f3a-186">修改「電腦」清單，以包含所有載入程式機器的電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="24f3a-186">Modify the “Machines” list to include machine names for all of your loader machines.</span></span>

10. <span data-ttu-id="24f3a-187">變更服務 (端點的 baseAddress 預設值為 "controller.contoso.com" ) 至您的控制器機器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="24f3a-187">Change the baseAddress of the service endpoint (default is “controller.contoso.com”) to the FQDN of your controller machine.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="24f3a-188">Usage</span><span class="sxs-lookup"><span data-stu-id="24f3a-188">Usage</span></span>

<span data-ttu-id="24f3a-189">設定完成後，請開啟控制器機器上的 StressLauncher.exe。</span><span class="sxs-lookup"><span data-stu-id="24f3a-189">After configuration is complete, open StressLauncher.exe on the controller machine.</span></span> <span data-ttu-id="24f3a-190">您可以以任何使用者的身分啟動 StressLauncher。</span><span class="sxs-lookup"><span data-stu-id="24f3a-190">You can launch StressLauncher as any user.</span></span> <span data-ttu-id="24f3a-191">必須在 config 檔案中指定增益集電腦上開機載入程式處理的認證。</span><span class="sxs-lookup"><span data-stu-id="24f3a-191">The credentials under which the loader processes start on the loader machines must be specified in the config file.</span></span> <span data-ttu-id="24f3a-192">您也必須提供可讀取持久聊天后端資料庫之讀取權的連接字串。</span><span class="sxs-lookup"><span data-stu-id="24f3a-192">You also must give a connection string that has Read access to the Persistent Chat back-end database.</span></span> <span data-ttu-id="24f3a-193">如果此連線字串使用整合式 Windows 驗證，您必須以具有這種存取權的使用者身分啟動 StressLauncher。</span><span class="sxs-lookup"><span data-stu-id="24f3a-193">If this connection string uses integrated Windows authentication, you must launch StressLauncher as a user that has this access.</span></span>

<span data-ttu-id="24f3a-194">視需要變更使用者模型設定。</span><span class="sxs-lookup"><span data-stu-id="24f3a-194">Alter the user model settings as needed.</span></span> <span data-ttu-id="24f3a-195">按一下 [ **開始載入** ] 以啟動 run。</span><span class="sxs-lookup"><span data-stu-id="24f3a-195">Click **Start Load** to initiate a run.</span></span> <span data-ttu-id="24f3a-196">一分鐘之後，使用者就會開始登入，進度列就會開始填滿。</span><span class="sxs-lookup"><span data-stu-id="24f3a-196">After a minute or so, users will start being signed in, and the progress bar will begin to fill.</span></span> <span data-ttu-id="24f3a-197">此時，您可能可以運作控制器機器並取得效能度量。</span><span class="sxs-lookup"><span data-stu-id="24f3a-197">At this point, you may can the controller machine working and take performance measurements.</span></span>

</div>

</div>

<div>

## <a name="chatupgradeverifier"></a><span data-ttu-id="24f3a-198">ChatUpgradeVerifier</span><span class="sxs-lookup"><span data-stu-id="24f3a-198">ChatUpgradeVerifier</span></span>

<div>

## <a name="description"></a><span data-ttu-id="24f3a-199">描述</span><span class="sxs-lookup"><span data-stu-id="24f3a-199">Description</span></span>

<span data-ttu-id="24f3a-200">ChatUpgradeVerifier 是一種持續聊天特有的資料庫比較工具。</span><span class="sxs-lookup"><span data-stu-id="24f3a-200">ChatUpgradeVerifier is a Persistent Chat specific database comparison tool.</span></span> <span data-ttu-id="24f3a-201">該工具會將群組聊天 2007 R2 或群組聊天2010資料庫 (2007/2010Db) 與 Persistent Chat 2013 資料庫 (2013Db) 進行比較。</span><span class="sxs-lookup"><span data-stu-id="24f3a-201">The tool compares either the Group Chat 2007 R2 or Group Chat 2010 Database (2007/2010Db) to the Persistent Chat 2013 Database (2013Db).</span></span>

<span data-ttu-id="24f3a-202">在 2007/2010Db 中，該工具會逐一檢查一個、每個類別、持續聊天室和增益集，以查看它是否出現在2013Db 中。</span><span class="sxs-lookup"><span data-stu-id="24f3a-202">The tool will check, one by one, each category, Persistent Chat room, and add-in in 2007/2010Db to see if it appears in the 2013Db.</span></span> <span data-ttu-id="24f3a-203">比較包含檢查類別、聊天室或增益集、類別範圍中的任何主體，以及類別或聊天室中某一角色的任何主體的所有設定。</span><span class="sxs-lookup"><span data-stu-id="24f3a-203">The comparison includes checking all settings on the category, chat room, or add-in, any principals in scope on the category, and any principal in a role on either the category or the chat room.</span></span> <span data-ttu-id="24f3a-204">當2013Db 中的類別或聊天室未正確顯示時，會將差異輸出至衝突檔案。</span><span class="sxs-lookup"><span data-stu-id="24f3a-204">If a category or a chat room does not appear correctly in the 2013Db, the differences will be output to a conflicts file.</span></span> <span data-ttu-id="24f3a-205">在升級完成之後，如果發生升級，則會變更 2007/2010Db，然後執行此工具時，會有差異輸出到衝突檔案。</span><span class="sxs-lookup"><span data-stu-id="24f3a-205">If, after the upgrade has occurred, the 2007/2010Db is changed and then this tool is run, there will be a differences output to the conflicts file.</span></span> <span data-ttu-id="24f3a-206">請注意，此應用程式只是資料庫比較工具，不會驗證升級程式。</span><span class="sxs-lookup"><span data-stu-id="24f3a-206">Note that this application is a database comparison tool only and does not validate the upgrade process.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="24f3a-207">需求</span><span class="sxs-lookup"><span data-stu-id="24f3a-207">Requirements</span></span>

<span data-ttu-id="24f3a-208">在已加入網域的機器上安裝 Persistent chat Resource 工具組工具，該機器可以存取持久聊天)  (舊版和目前版本。</span><span class="sxs-lookup"><span data-stu-id="24f3a-208">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Persistent Chat back-end databases (previous and current versions for Persistent Chat).</span></span>

<span data-ttu-id="24f3a-209">執行此工具的使用者帳戶必須具有對 Persistent 聊天資料庫的讀取權限。</span><span class="sxs-lookup"><span data-stu-id="24f3a-209">The user account under which the tool runs must have Read access to the Persistent Chat databases.</span></span>

<span data-ttu-id="24f3a-210">ChatUpgradeVerifier.exe.config 檔必須包含 GroupChat2007R2Db 參數或 GroupChat2010Db 參數，並將連接字串連至適當群組聊天資料庫 (Groupchat.contoso Nm-opsmgr-2007r2-2nd 或 2010) 。</span><span class="sxs-lookup"><span data-stu-id="24f3a-210">The ChatUpgradeVerifier.exe.config file must contain either the GroupChat2007R2Db parameter or the GroupChat2010Db parameter, with a connection string to the appropriate Group Chat database (either Groupchat 2007R2 or 2010).</span></span> <span data-ttu-id="24f3a-211">它還必須包含 PersistentChat2013Db 參數，並將連接字串連至 Persistent Chat 2013 資料庫。</span><span class="sxs-lookup"><span data-stu-id="24f3a-211">It must also contain a PersistentChat2013Db parameter, with a connection string to the Persistent Chat 2013 database.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="24f3a-212">Usage</span><span class="sxs-lookup"><span data-stu-id="24f3a-212">Usage</span></span>

<span data-ttu-id="24f3a-213">執行不含任何參數的 **ChatUpgradeVerifier** 。</span><span class="sxs-lookup"><span data-stu-id="24f3a-213">Run **ChatUpgradeVerifier** without any parameters.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="24f3a-214">範例</span><span class="sxs-lookup"><span data-stu-id="24f3a-214">Example</span></span>

<span data-ttu-id="24f3a-215">![執行 ChatUpgradeVerifier.exe。](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "執行 ChatUpgradeVerifier.exe。")</span><span class="sxs-lookup"><span data-stu-id="24f3a-215">![Running ChatUpgradeVerifier.exe.](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "Running ChatUpgradeVerifier.exe.")</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-usage-report"></a><span data-ttu-id="24f3a-216">Persistent Chat 使用方式報告</span><span class="sxs-lookup"><span data-stu-id="24f3a-216">Persistent Chat Usage Report</span></span>

<div>

## <a name="description"></a><span data-ttu-id="24f3a-217">描述</span><span class="sxs-lookup"><span data-stu-id="24f3a-217">Description</span></span>

<span data-ttu-id="24f3a-218">ChatUsageReport 工具會產生持久聊天服務使用方式的 HTML 報告。</span><span class="sxs-lookup"><span data-stu-id="24f3a-218">The ChatUsageReport tool generates an HTML report of Persistent Chat service usage.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="24f3a-219">需求</span><span class="sxs-lookup"><span data-stu-id="24f3a-219">Requirements</span></span>

<span data-ttu-id="24f3a-220">在具有 Persistent Chat 後端資料庫存取權的已加入網域的機器上安裝 Persistent Chat Resource 工具組工具。</span><span class="sxs-lookup"><span data-stu-id="24f3a-220">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="24f3a-221">執行此工具的使用者帳戶必須具有對 Persistent 後端資料庫的讀取權限。</span><span class="sxs-lookup"><span data-stu-id="24f3a-221">The user account under which the tool is run must have Read access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="24f3a-222">檔案 ChatUsageReport.exe.config，必須包含一個區段，用以 \<connectionStrings\> 定義持久聊天后端資料庫的連接字串。</span><span class="sxs-lookup"><span data-stu-id="24f3a-222">The file, ChatUsageReport.exe.config, must contain a \<connectionStrings\> section defining the connection string to the Persistent Chat back-end database.</span></span> <span data-ttu-id="24f3a-223">預設的設定檔內容會包含在這裡供您參考。</span><span class="sxs-lookup"><span data-stu-id="24f3a-223">The contents of the default config file are included here, for your reference.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="24f3a-224">Usage</span><span class="sxs-lookup"><span data-stu-id="24f3a-224">Usage</span></span>

```Powershell
    ChatUsageReport [-StartDate {date}] [-EndDate {date}] [-TopActiveUsers {n}] [-TopActiveRooms {n}] [-LeastActiveRooms {n}] [-RoomsInactiveSince {Date}] [-OutputFolder {path}]
```
<span data-ttu-id="24f3a-225">這些參數會定義資料的選取專案：</span><span class="sxs-lookup"><span data-stu-id="24f3a-225">These parameters define the selection of data:</span></span>

<span data-ttu-id="24f3a-226">**StartDate：** （選用）指定選取期間的 UTC 開始日期。</span><span class="sxs-lookup"><span data-stu-id="24f3a-226">**StartDate:** Optionally specifies the UTC start date of the selection period.</span></span> <span data-ttu-id="24f3a-227">預設值：最早日期</span><span class="sxs-lookup"><span data-stu-id="24f3a-227">Default: Earliest Date</span></span>

<span data-ttu-id="24f3a-228">**EndDate：** （選用）指定選取期間的 UTC 結束日期。</span><span class="sxs-lookup"><span data-stu-id="24f3a-228">**EndDate:** Optionally specifies the UTC end date of the selection period.</span></span> <span data-ttu-id="24f3a-229">預設值：現在</span><span class="sxs-lookup"><span data-stu-id="24f3a-229">Default: Now</span></span>

<span data-ttu-id="24f3a-230">這些參數定義顯示資料的方式和方式：</span><span class="sxs-lookup"><span data-stu-id="24f3a-230">These parameters define how and what data is displayed:</span></span>

<span data-ttu-id="24f3a-231">**TopActiveUsers：** 如果指定此值，則報告將會包含 n 個最活躍的使用者，其條件是使用者在選取的期間內已在聊天室中張貼的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="24f3a-231">**TopActiveUsers:** If this is specified, the report will include the n most active users in terms of the number of messages the user has posted in the chat room for the selected period.</span></span> <span data-ttu-id="24f3a-232">預設值：10</span><span class="sxs-lookup"><span data-stu-id="24f3a-232">Default: 10</span></span>

<span data-ttu-id="24f3a-233">**TopActiveRooms：** 如果指定此值，則報告將會包含 n 個最活躍的聊天室，其條件是針對所選期間在會議室中張貼的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="24f3a-233">**TopActiveRooms:** If this is specified, the report will include the n most active chat rooms in terms of the number of messages posted in the room for the selected period.</span></span> <span data-ttu-id="24f3a-234">預設值：10</span><span class="sxs-lookup"><span data-stu-id="24f3a-234">Default: 10</span></span>

<span data-ttu-id="24f3a-235">**LeastActiveRooms：** 如果指定此值，則報告將會包含 n 個最少的使用中聊天室，其條件是針對所選期間在聊天室中張貼的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="24f3a-235">**LeastActiveRooms:** If this is specified, the report will include the n least active chat rooms in terms of the number of messages posted in the chat room for the selected period.</span></span> <span data-ttu-id="24f3a-236">會議室至少會有一封發表郵件。</span><span class="sxs-lookup"><span data-stu-id="24f3a-236">Rooms will have at least one message posted.</span></span> <span data-ttu-id="24f3a-237">預設值：10</span><span class="sxs-lookup"><span data-stu-id="24f3a-237">Default: 10</span></span>

<span data-ttu-id="24f3a-238">**RoomsInactiveSince：** 如果指定此專案，報告將會包含從指定的日期起已非使用中的聊天室清單。</span><span class="sxs-lookup"><span data-stu-id="24f3a-238">**RoomsInactiveSince:** If this is specified, the report will include a list of chat rooms that have been inactive since the specified date.</span></span> <span data-ttu-id="24f3a-239">預設值：整個時間</span><span class="sxs-lookup"><span data-stu-id="24f3a-239">Default: Entire Time</span></span>

<span data-ttu-id="24f3a-240">**OutputFolder：** 會放置 ChatUsageReport.html 與圖形影像的資料夾。</span><span class="sxs-lookup"><span data-stu-id="24f3a-240">**OutputFolder:** The folder where the ChatUsageReport.html and the graph images will be placed.</span></span> <span data-ttu-id="24f3a-241">這必須在 config 檔案或命令列上定義。</span><span class="sxs-lookup"><span data-stu-id="24f3a-241">This must be defined in the config file or on the command line.</span></span>

<span data-ttu-id="24f3a-242">您也可以在與工具位於相同目錄的 ChatUsageReport.exe.config 檔案中指定所有的命令列參數值。</span><span class="sxs-lookup"><span data-stu-id="24f3a-242">All of the command line parameter values can also be specified in the ChatUsageReport.exe.config file that is located in the same directory as the tool.</span></span> <span data-ttu-id="24f3a-243">如果在設定檔和命令列中指定任何值，則命令列值將會覆寫 config 檔值。</span><span class="sxs-lookup"><span data-stu-id="24f3a-243">If any value is specified in both the config file and the command line, the command line value will override the config file value.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="24f3a-244">輸出</span><span class="sxs-lookup"><span data-stu-id="24f3a-244">Output</span></span>

<span data-ttu-id="24f3a-245">報告會永遠包含下列輸出：</span><span class="sxs-lookup"><span data-stu-id="24f3a-245">The report will always include the following output:</span></span>

  - <span data-ttu-id="24f3a-246">在選取的期間內，最高排名個最活躍的聊天室，郵件投遞的數目。</span><span class="sxs-lookup"><span data-stu-id="24f3a-246">Top n most active chat rooms by number of message posts for selected period.</span></span>

  - <span data-ttu-id="24f3a-247">最高排名的前 n 個最活躍的使用者選取期間的郵件投遞數目。</span><span class="sxs-lookup"><span data-stu-id="24f3a-247">Top n most active users by number of message posts for selected period.</span></span>

  - <span data-ttu-id="24f3a-248">在選取的期間內，最小的使用中聊天室的郵件投遞數目。</span><span class="sxs-lookup"><span data-stu-id="24f3a-248">Top n least active chat rooms by number of message posts for selected period.</span></span>

  - <span data-ttu-id="24f3a-249">在資料庫整個生命週期中非使用中或自指定日期之後的聊天室。</span><span class="sxs-lookup"><span data-stu-id="24f3a-249">Chat rooms that are inactive for the entire life of the database, or since the specified date.</span></span>

  - <span data-ttu-id="24f3a-250">所選期間的每日郵件投遞趨勢。</span><span class="sxs-lookup"><span data-stu-id="24f3a-250">Daily message post trend for selected period.</span></span>

  - <span data-ttu-id="24f3a-251">所選期間的每週郵件投遞趨勢。</span><span class="sxs-lookup"><span data-stu-id="24f3a-251">Weekly message post trend for selected period.</span></span>

  - <span data-ttu-id="24f3a-252">所選期間的每月郵件投遞趨勢。</span><span class="sxs-lookup"><span data-stu-id="24f3a-252">Monthly message post trend for selected period.</span></span>

  - <span data-ttu-id="24f3a-253">所選期間內的郵件投遞總數。</span><span class="sxs-lookup"><span data-stu-id="24f3a-253">Total message posts for selected period.</span></span>

  - <span data-ttu-id="24f3a-254">已啟用的會議室總數。</span><span class="sxs-lookup"><span data-stu-id="24f3a-254">Total number of enabled rooms.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="24f3a-255">範例</span><span class="sxs-lookup"><span data-stu-id="24f3a-255">Example</span></span>

<span data-ttu-id="24f3a-256">下列範例會產生整年2001的使用方式報告，並將報表放在 ChatUsageReport.exe.config 所指定的 OutputFolder 中。</span><span class="sxs-lookup"><span data-stu-id="24f3a-256">The following example generates a usage report for the entire year 2001 and places the report in the OutputFolder specified in the ChatUsageReport.exe.config.</span></span>

```Powershell
    ChatUsageReport -RoomsInactiveSince 06-20-2010
```
<span data-ttu-id="24f3a-257">ChatUsageReport.exe.config：</span><span class="sxs-lookup"><span data-stu-id="24f3a-257">ChatUsageReport.exe.config:</span></span>

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

## <a name="scheduleadsyncforprincipal"></a><span data-ttu-id="24f3a-258">ScheduleADSyncForPrincipal</span><span class="sxs-lookup"><span data-stu-id="24f3a-258">ScheduleADSyncForPrincipal</span></span>

<div>

## <a name="description"></a><span data-ttu-id="24f3a-259">描述</span><span class="sxs-lookup"><span data-stu-id="24f3a-259">Description</span></span>

<span data-ttu-id="24f3a-260">ScheduleADSyncForPrincipal 是 Microsoft SQL Server 2012 腳本，當連線至 Persistent Chat 後端資料庫時，必須直接在 SQL Server Management Studio 中執行。</span><span class="sxs-lookup"><span data-stu-id="24f3a-260">ScheduleADSyncForPrincipal is a Microsoft SQL Server 2012 script that must be run directly from within SQL Server Management Studio when connected to the Persistent Chat back-end database.</span></span> <span data-ttu-id="24f3a-261">此腳本可讓您強制持續聊天將使用者的記錄同步處理至 Active Directory 網域服務的使用者，而不是等待排程的同步處理時間。</span><span class="sxs-lookup"><span data-stu-id="24f3a-261">This script enables you to force Persistent Chat to synchronize its records of a user with those of Active Directory Domain Services, rather than waiting for the scheduled synchronization time.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="24f3a-262">需求</span><span class="sxs-lookup"><span data-stu-id="24f3a-262">Requirements</span></span>

<span data-ttu-id="24f3a-263">執行腳本的使用者帳戶必須具有對 Persistent 後端資料庫的擁有者存取權。</span><span class="sxs-lookup"><span data-stu-id="24f3a-263">The user account under which the script is run must have owner access to the Persistent Chat back-end database.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="24f3a-264">Usage</span><span class="sxs-lookup"><span data-stu-id="24f3a-264">Usage</span></span>

<span data-ttu-id="24f3a-265">預設腳本的內容如下：</span><span class="sxs-lookup"><span data-stu-id="24f3a-265">Following are the contents of the default script:</span></span>

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

