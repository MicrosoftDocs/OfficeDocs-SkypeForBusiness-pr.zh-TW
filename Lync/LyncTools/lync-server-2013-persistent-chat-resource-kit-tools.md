---
title: Lync Server 2013 常設聊天室 Resource Kit 工具
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
ms.openlocfilehash: ffd95611f3033dff992092e3be93815bd0e01915
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-persistent-chat-resource-kit-tools"></a><span data-ttu-id="fcb5a-102">Lync Server 2013 常設聊天室 Resource Kit 工具</span><span class="sxs-lookup"><span data-stu-id="fcb5a-102">Lync Server 2013 Persistent Chat Resource Kit Tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fcb5a-103">_**上次修改主題：** 2013年-02-24_</span><span class="sxs-lookup"><span data-stu-id="fcb5a-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="fcb5a-104">Lync Server 2013 常設聊天室 Resource Kit 工具可協助簡化例行工作 IT 管理員部署及管理 Lync Server 2013 常設聊天室伺服器。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-104">The Lync Server 2013 Persistent Chat Resource Kit tools help to make routine tasks easier for IT administrators who deploy and manage Lync Server 2013 Persistent Chat Server.</span></span> <span data-ttu-id="fcb5a-105">安裝指示，除了本主題會說明每個工具和其使用範例的目的。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-105">In addition to installation instructions, this topic describes the purpose of each tool, and examples of its use.</span></span>

<div>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="fcb5a-106">Resource Kit 工具的安裝</span><span class="sxs-lookup"><span data-stu-id="fcb5a-106">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="fcb5a-107">若要安裝 Lync Server 2013 Resource Kit 工具，下載**PersistentChatReskit.msi**。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-107">To install the Lync Server 2013, Resource Kit Tools, download **PersistentChatReskit.msi**.</span></span> <span data-ttu-id="fcb5a-108">執行**PersistentChatReskit.msi**執行簡單的安裝。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-108">Run **PersistentChatReskit.msi** to do a simple installation.</span></span> <span data-ttu-id="fcb5a-109">.msi 安裝的所有工具在下列路徑： \\ **Program Files\\ Microsoft Lync Server 2013\\常設聊天室伺服器 Resource Kit**。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-109">The .msi installs all the tools in the following path: \\**Program Files\\ Microsoft Lync Server 2013\\Persistent Chat Server Resource Kit**.</span></span> <span data-ttu-id="fcb5a-110">是獨立的可執行檔的工具是此資料夾中。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-110">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="fcb5a-111">工具，也有檔案位於其自己的子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-111">Tools that also have files are in their own subfolders.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fcb5a-112">安裝 Lync Server 2013 Resource Kit 工具之後，您必須安裝<STRONG>PsExec.exe</STRONG>並將<STRONG>PsExec.exe</STRONG>複製到下列路徑： \\<STRONG>程式 Files\ Microsoft Lync Server 2013\Persistent 聊天伺服器資源 Kit\ChatStressTool</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-112">After installing the Lync Server 2013, Resource Kit Tools, you must install <STRONG>PsExec.exe</STRONG> and copy <STRONG>PsExec.exe</STRONG> to the following path: \\<STRONG>Program Files\ Microsoft Lync Server 2013\Persistent Chat Server Resource Kit\ChatStressTool</STRONG>.</span></span> <span data-ttu-id="fcb5a-113">如果您不要複製<STRONG>PsExec.exe</STRONG>，常設聊天室壓力工具會擲回錯誤的例外狀況，並不會正確地執行。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-113">If you do not copy <STRONG>PsExec.exe</STRONG>, the Persistent Chat Stress Tool will throw an error exception, and not perform correctly.</span></span> <span data-ttu-id="fcb5a-114">請確定您符合此必要條件的需求，再執行此工具。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-114">Make sure that you meet this prerequisite requirement prior to running the tool.</span></span> <span data-ttu-id="fcb5a-115">如需安裝<STRONG>PsExec.exe</STRONG>的詳細資訊，請參閱<A href="https://go.microsoft.com/fwlink/p/?linkid=282246">https://go.microsoft.com/fwlink/p/?LinkId=282246</A>。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-115">For details about installing <STRONG>PsExec.exe</STRONG>, see <A href="https://go.microsoft.com/fwlink/p/?linkid=282246">https://go.microsoft.com/fwlink/p/?LinkId=282246</A>.</span></span>



</div>

</div>

<div>

## <a name="supported-environments"></a><span data-ttu-id="fcb5a-116">支援的環境</span><span class="sxs-lookup"><span data-stu-id="fcb5a-116">Supported Environments</span></span>

<span data-ttu-id="fcb5a-117">以獲得最佳效能，Lync Server 2013 Resource Kit 工具應該安裝在相同的環境與相同規格所需的 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-117">For optimal performance, the Lync Server 2013, Resource Kit Tools should be installed in the same environment and with the same specifications that are required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="fcb5a-118">Resource Kit 工具概觀</span><span class="sxs-lookup"><span data-stu-id="fcb5a-118">Resource Kit Tools Overview</span></span>

<span data-ttu-id="fcb5a-119">以下是 Lync Server 2013 常設聊天室 Resource Kit 中所提供的工具。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-119">Here are the tools that are provided in the Lync Server 2013 Persistent Chat Resource Kit.</span></span> <span data-ttu-id="fcb5a-120">下節提供每一種工具，包括需求和範例流量的描述。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-120">The following section provides a description of each tool, including requirements and example usage.</span></span>

  - <span data-ttu-id="fcb5a-121">AffCheck</span><span class="sxs-lookup"><span data-stu-id="fcb5a-121">AffCheck</span></span>

  - <span data-ttu-id="fcb5a-122">ChatMonitoringSummary</span><span class="sxs-lookup"><span data-stu-id="fcb5a-122">ChatMonitoringSummary</span></span>

  - <span data-ttu-id="fcb5a-123">ChatStress 工具</span><span class="sxs-lookup"><span data-stu-id="fcb5a-123">ChatStress Tool</span></span>

  - <span data-ttu-id="fcb5a-124">ChatUpgradeVerifier</span><span class="sxs-lookup"><span data-stu-id="fcb5a-124">ChatUpgradeVerifier</span></span>

  - <span data-ttu-id="fcb5a-125">ChatUsageReport</span><span class="sxs-lookup"><span data-stu-id="fcb5a-125">ChatUsageReport</span></span>

  - <span data-ttu-id="fcb5a-126">ScheduleADSyncforPrincipal</span><span class="sxs-lookup"><span data-stu-id="fcb5a-126">ScheduleADSyncforPrincipal</span></span>

</div>

<div>

## <a name="affcheck"></a><span data-ttu-id="fcb5a-127">AffCheck</span><span class="sxs-lookup"><span data-stu-id="fcb5a-127">AffCheck</span></span>

<div>

## <a name="description"></a><span data-ttu-id="fcb5a-128">說明</span><span class="sxs-lookup"><span data-stu-id="fcb5a-128">Description</span></span>

<span data-ttu-id="fcb5a-129">AffCheck 工具確認常設聊天室後端資料庫的使用者和群組 affiliation 記錄符合的 Active Directory 網域服務。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-129">The AffCheck tool confirms that the Persistent Chat back-end database user and group affiliation records match that of Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="fcb5a-130">需求</span><span class="sxs-lookup"><span data-stu-id="fcb5a-130">Requirements</span></span>

<span data-ttu-id="fcb5a-131">使用網域聯結電腦上的 PersistentChatResKit 安裝程式安裝的工具。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-131">The tool is installed with the PersistentChatResKit installer on a domain joined machine.</span></span>

<span data-ttu-id="fcb5a-132">執行此工具會在其下的使用者帳戶必須具有 Active Directory 網域服務與常設聊天室後端資料庫的讀取權限。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-132">The user account under which the tool is run must have Read access to the Persistent Chat back-end database and Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="fcb5a-133">Usage</span><span class="sxs-lookup"><span data-stu-id="fcb5a-133">Usage</span></span>

<span data-ttu-id="fcb5a-134">組態檔中設定根據指示 AffCheck.exe.config 檔案並執行 AffCheck 工具不含命令列參數。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-134">Configure the AffCheck.exe.config file according to the instructions in the config file and run the AffCheck tool without command-line parameters.</span></span> <span data-ttu-id="fcb5a-135">以下是預設 AffCheck.exe.config 的內容。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-135">Following are the contents of the default AffCheck.exe.config.</span></span>

<span data-ttu-id="fcb5a-136">**AffCheck.exe.config:**</span><span class="sxs-lookup"><span data-stu-id="fcb5a-136">**AffCheck.exe.config:**</span></span>

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

## <a name="chatmonitoringsummary"></a><span data-ttu-id="fcb5a-137">ChatMonitoringSummary</span><span class="sxs-lookup"><span data-stu-id="fcb5a-137">ChatMonitoringSummary</span></span>

<div>

## <a name="description"></a><span data-ttu-id="fcb5a-138">說明</span><span class="sxs-lookup"><span data-stu-id="fcb5a-138">Description</span></span>

<span data-ttu-id="fcb5a-139">PersistentChatMonitoringSummary 工具會將常設聊天室監視資訊從監控資料庫移至指定的 CSV 記錄檔。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-139">The PersistentChatMonitoringSummary tool moves Persistent Chat monitoring information from the monitoring database into a specified CSV log file.</span></span>

<span data-ttu-id="fcb5a-140">CSV 檔案會包含的常設聊天室工作階段的工作階段總數，成功的工作階段、 未預期的失敗，預期的失敗，會以明細與未預期的失敗的診斷識別碼、 失敗及錯誤描述的數字明細。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-140">The CSV file will contain a breakdown of Persistent Chat sessions by number of total sessions, successful sessions, unexpected failures, expected failures, and a breakdown of the unexpected failures by diagnostic ID, number of failures, and failure description.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="fcb5a-141">需求</span><span class="sxs-lookup"><span data-stu-id="fcb5a-141">Requirements</span></span>

<span data-ttu-id="fcb5a-142">具有監控資料庫的存取權的已加入網域的機器上安裝的常設聊天室 Resource Kit 工具。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-142">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Monitoring database.</span></span>

<span data-ttu-id="fcb5a-143">執行工具的使用者帳戶必須具備監控資料庫的讀取權限。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-143">The user account under which the tool runs must have Read access to the Monitoring database.</span></span>

<span data-ttu-id="fcb5a-144">該檔案，PersistentChatMonitoringSummary.exe.config，必須包含\<connectionStrings\> ] 區段中定義的連接字串至監控資料庫。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-144">The file, PersistentChatMonitoringSummary.exe.config, must contain a \<connectionStrings\> section that defines the connection string to the Monitoring database.</span></span> <span data-ttu-id="fcb5a-145">它也必須包含索引鍵的監視資料那裡，PersistentChatEndpointUri 並將產生的 CSV 檔案的位置的檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-145">It must also contain a key for the PersistentChatEndpointUri that the monitoring data will be gathered for, and a file path to a location for the CSV file that will be generated.</span></span> <span data-ttu-id="fcb5a-146">請參閱安裝的組態檔中的範例。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-146">Refer to the installed config file for examples.</span></span> <span data-ttu-id="fcb5a-147">檔案必須位於與工具相同的目錄。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-147">The file must be located in the same directory as the tool.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="fcb5a-148">Usage</span><span class="sxs-lookup"><span data-stu-id="fcb5a-148">Usage</span></span>

```Batch
    PersistentChatMonitoringSummary [-StartDateTime <date>] [-EndDateTime <date>]
```

<span data-ttu-id="fcb5a-149">這些參數定義資料的選取範圍：</span><span class="sxs-lookup"><span data-stu-id="fcb5a-149">These parameters define the selection of data:</span></span>

<span data-ttu-id="fcb5a-150">**StartDateTime:**（選用） 指定的選取範圍期間的開始日期。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-150">**StartDateTime:** Optionally specifies the start date of the selection period.</span></span> <span data-ttu-id="fcb5a-151">預設值： 1/1/1753年 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="fcb5a-151">Default: 1/1/1753 12:00:00 AM</span></span>

<span data-ttu-id="fcb5a-152">**EndDateTime:**（選用） 指定的選取範圍期間的最後一個日期。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-152">**EndDateTime:** Optionally specifies the last date of the selection period.</span></span> <span data-ttu-id="fcb5a-153">預設值： 現在</span><span class="sxs-lookup"><span data-stu-id="fcb5a-153">Default: Now</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="fcb5a-154">範例</span><span class="sxs-lookup"><span data-stu-id="fcb5a-154">Example</span></span>

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

## <a name="persistent-chat-stress-tool"></a><span data-ttu-id="fcb5a-155">常設聊天室壓力工具</span><span class="sxs-lookup"><span data-stu-id="fcb5a-155">Persistent Chat Stress Tool</span></span>

<div>

## <a name="description"></a><span data-ttu-id="fcb5a-156">說明</span><span class="sxs-lookup"><span data-stu-id="fcb5a-156">Description</span></span>

<span data-ttu-id="fcb5a-157">常設聊天室壓力工具提供簡單的方法來模擬的常設聊天室，來測試真實世界的效能，包括具有不同的使用者模型，才能滿足您的預期的使用情況的使用狀況。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-157">The Persistent Chat Stress tool provides an easy way to simulate usage of Persistent Chat to test real-world performance, including varied user models to better fit your expected usage scenarios.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="fcb5a-158">需求</span><span class="sxs-lookup"><span data-stu-id="fcb5a-158">Requirements</span></span>

<span data-ttu-id="fcb5a-159">安裝到具有常設聊天室後端資料庫的存取權的已加入網域的機器上的常設聊天室 Resource Kit 工具。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-159">Install the Persistent Chat Resource Kit tools onto a domain-joined machine that has access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="fcb5a-160">除了這*控制站*台機器中，您將需要數個*載入*機器。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-160">In addition to this *controller* machine, you will need several *loader* machines.</span></span> <span data-ttu-id="fcb5a-161">針對使用者模型中的每個 10k 使用者，您必須至少 4 GB 的可用 RAM 載入機器上。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-161">For every 10K users in your user model, you will need at least 4GB of free RAM on a loader machine.</span></span> <span data-ttu-id="fcb5a-162">例如，與 80 K 使用者執行時，需要約 32 GB 的 RAM 散佈於載入程式的所有機器。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-162">For example, a run with 80K users will require about 32GB of RAM spread across all loader machines.</span></span> <span data-ttu-id="fcb5a-163">我們建議您具有至少三個載入機器，不論預期的負載。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-163">We recommend that you have at least three loader machines, regardless of expected load.</span></span>

<span data-ttu-id="fcb5a-164">載入機器必須.NET 4.5 架構，以及 Visual c + + 2012年可轉散發套件安裝。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-164">Loader machines must have the .NET 4.5 Framework as well as the Visual C++ 2012 Redistributable installed.</span></span>

</div>

<div>

## <a name="configuration"></a><span data-ttu-id="fcb5a-165">組態</span><span class="sxs-lookup"><span data-stu-id="fcb5a-165">Configuration</span></span>

<span data-ttu-id="fcb5a-166">將 ChatStressTool 檔案複製到可從載入程式的所有機器存取的共用資料夾。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-166">Copy ChatStressTool files into a shared folder accessible from all loader machines.</span></span>

<span data-ttu-id="fcb5a-167">建立使用者和通道的使用中執行的負荷：</span><span class="sxs-lookup"><span data-stu-id="fcb5a-167">Create users and channels for use in the stress run:</span></span>

  - <span data-ttu-id="fcb5a-168">建立會呼叫您的使用者模型的使用者數目、 啟用這些 lync，並將其常設聊天室原則設定為 [已啟用。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-168">Create as many users as your user model calls for, enable them for Lync, and set their Persistent Chat policy to Enabled.</span></span>

  - <span data-ttu-id="fcb5a-169">建立類別，您壓力通道，並建立多個會議室，視需要在該類別下。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-169">Create a category for your stress channels, and then create as many rooms as are needed under that category.</span></span> <span data-ttu-id="fcb5a-170">類別 （透過新增其 OU），它**允許**清單中應設有壓力的所有使用者和壓力會議室都應有的隱私權設定為**開啟**。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-170">The category should have all stress users in its **Allowed** list (by way of adding their OU), and stress rooms should have a privacy setting of **Open**.</span></span>

  - <span data-ttu-id="fcb5a-171">我們建議您建立額外的壓力聊天室。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-171">We recommend creating extra stress rooms.</span></span> <span data-ttu-id="fcb5a-172">您可以使用下列 Windows PowerShell 命令列介面命令來建立 50000 會議室：</span><span class="sxs-lookup"><span data-stu-id="fcb5a-172">You can create 50,000 rooms with the following Windows PowerShell command-line interface command:</span></span>
    ```Powershell
        for ($i = 0; $i -le 50000; $i++) { New-CsPersistentChatRoom -Category <parent category> -Name "StressChan_$i" -Privacy Open }
    ```    

<span data-ttu-id="fcb5a-173">編輯設定檔，以符合您的拓撲：</span><span class="sxs-lookup"><span data-stu-id="fcb5a-173">Edit the configuration files to fit your topology:</span></span>

<span data-ttu-id="fcb5a-174">在**LoaderProcess.exe.config**，變更 「 controller.contoso.com 」 控制器電腦的完整的網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-174">In **LoaderProcess.exe.config**, change “controller.contoso.com” to the controller machine’s fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="fcb5a-175">在 [ **StressLauncher.exe.config:**</span><span class="sxs-lookup"><span data-stu-id="fcb5a-175">In **StressLauncher.exe.config:**</span></span>

1.  <span data-ttu-id="fcb5a-176">將 「 LoaderBinary 」 設定值變更為共用的資料夾的路徑。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-176">Change the “LoaderBinary” setting value to the shared folder’s path.</span></span>

2.  <span data-ttu-id="fcb5a-177">變更 「 機器 」 / 「 AdminPassword 」 至已載入機器的系統管理存取權的認證。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-177">Change “AdminUser”/”AdminPassword” to credentials that have admin access to loader machines.</span></span>

3.  <span data-ttu-id="fcb5a-178">變更 「 ChannelCategory 」 名稱的壓力通道類別已建立在之下。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-178">Change “ChannelCategory” to the name of the category that stress channels have been created under.</span></span>

4.  <span data-ttu-id="fcb5a-179">變更 「 UserNamePattern 」 和 「 UserPasswordPattern 」 為範本相符壓力使用者認證。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-179">Change “UserNamePattern” and “UserPasswordPattern” to a template that matches your stress user credentials.</span></span> <span data-ttu-id="fcb5a-180">{0}會取代使用者的索引編號。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-180">{0} is replaced with the user’s index number.</span></span>

5.  <span data-ttu-id="fcb5a-181">將 「 網域 」 變更為您的測試拓撲的 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-181">Change “Domain” to the SIP domain of your test topology.</span></span>

6.  <span data-ttu-id="fcb5a-182">將 「 ConnectionString 」 變更為您常設聊天室後端資料庫連線字串。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-182">Change “ConnectionString” to a connection string for your Persistent Chat back-end database.</span></span>

7.  <span data-ttu-id="fcb5a-183">將 「 UserIndexStart 」 變更為第一個壓力使用者的索引。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-183">Change “UserIndexStart” to the index of the first stress user.</span></span>

8.  <span data-ttu-id="fcb5a-184">將 「 LyncFQDN 」 變更為前端集區的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-184">Change “LyncFQDN” to the FQDN of your Front End pool.</span></span>

9.  <span data-ttu-id="fcb5a-185">修改 「 機器 」 清單中包含的所有載入機器的機器名稱。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-185">Modify the “Machines” list to include machine names for all of your loader machines.</span></span>

10. <span data-ttu-id="fcb5a-186">變更服務端點的 baseAddress （預設值為 「 controller.contoso.com 」） 至您的控制器電腦的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-186">Change the baseAddress of the service endpoint (default is “controller.contoso.com”) to the FQDN of your controller machine.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="fcb5a-187">Usage</span><span class="sxs-lookup"><span data-stu-id="fcb5a-187">Usage</span></span>

<span data-ttu-id="fcb5a-188">完成設定之後，請開啟 StressLauncher.exe 控制器機器上。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-188">After configuration is complete, open StressLauncher.exe on the controller machine.</span></span> <span data-ttu-id="fcb5a-189">您可以啟動 StressLauncher 的任何使用者。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-189">You can launch StressLauncher as any user.</span></span> <span data-ttu-id="fcb5a-190">必須在組態檔中指定下載入機器，啟動載入程序的認證。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-190">The credentials under which the loader processes start on the loader machines must be specified in the config file.</span></span> <span data-ttu-id="fcb5a-191">您也必須提供具有讀取存取權的常設聊天室後端資料庫連線字串。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-191">You also must give a connection string that has Read access to the Persistent Chat back-end database.</span></span> <span data-ttu-id="fcb5a-192">如果此連接字串會使用整合式的 Windows 驗證，您必須啟動 StressLauncher 具有此存取權的使用者。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-192">If this connection string uses integrated Windows authentication, you must launch StressLauncher as a user that has this access.</span></span>

<span data-ttu-id="fcb5a-193">視需要變更的使用者模型設定。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-193">Alter the user model settings as needed.</span></span> <span data-ttu-id="fcb5a-194">按一下 [啟動執行**啟動載入**。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-194">Click **Start Load** to initiate a run.</span></span> <span data-ttu-id="fcb5a-195">後一分鐘左右，使用者就會開始正在登入，進度列會並開始以填滿。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-195">After a minute or so, users will start being signed in, and the progress bar will begin to fill.</span></span> <span data-ttu-id="fcb5a-196">此時，您可能可以控制站的機器 working 和採取效能測量。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-196">At this point, you may can the controller machine working and take performance measurements.</span></span>

</div>

</div>

<div>

## <a name="chatupgradeverifier"></a><span data-ttu-id="fcb5a-197">ChatUpgradeVerifier</span><span class="sxs-lookup"><span data-stu-id="fcb5a-197">ChatUpgradeVerifier</span></span>

<div>

## <a name="description"></a><span data-ttu-id="fcb5a-198">說明</span><span class="sxs-lookup"><span data-stu-id="fcb5a-198">Description</span></span>

<span data-ttu-id="fcb5a-199">ChatUpgradeVerifier 是常設聊天室的特定資料庫比較工具。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-199">ChatUpgradeVerifier is a Persistent Chat specific database comparison tool.</span></span> <span data-ttu-id="fcb5a-200">工具會比較 [群組聊天 2007 R2] 或 [群組聊天 2010年資料庫 (2007年/2010Db) 至常設聊天室 2013年資料庫 (2013Db)。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-200">The tool compares either the Group Chat 2007 R2 or Group Chat 2010 Database (2007/2010Db) to the Persistent Chat 2013 Database (2013Db).</span></span>

<span data-ttu-id="fcb5a-201">在工具會檢查，請逐一，每個類別，常設聊天室的會議室，和 2007年/2010Db 以查看它會出現在 2013Db 中增益集。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-201">The tool will check, one by one, each category, Persistent Chat room, and add-in in 2007/2010Db to see if it appears in the 2013Db.</span></span> <span data-ttu-id="fcb5a-202">比較包括檢查上類別、 聊天室，或增益集、 在 [範圍] 類別中，任何主體和任何主體角色上類別或聊天室中的所有設定。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-202">The comparison includes checking all settings on the category, chat room, or add-in, any principals in scope on the category, and any principal in a role on either the category or the chat room.</span></span> <span data-ttu-id="fcb5a-203">如果類別或聊天室未正確出現在 2013Db，差異就會輸出至衝突檔。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-203">If a category or a chat room does not appear correctly in the 2013Db, the differences will be output to a conflicts file.</span></span> <span data-ttu-id="fcb5a-204">如果在升級之後發生，2007年/2010Db 變更並再執行此工具之後，會有衝突檔差異輸出。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-204">If, after the upgrade has occurred, the 2007/2010Db is changed and then this tool is run, there will be a differences output to the conflicts file.</span></span> <span data-ttu-id="fcb5a-205">請注意，此應用程式資料庫比較只是工具並不會驗證升級程序。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-205">Note that this application is a database comparison tool only and does not validate the upgrade process.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="fcb5a-206">需求</span><span class="sxs-lookup"><span data-stu-id="fcb5a-206">Requirements</span></span>

<span data-ttu-id="fcb5a-207">具有常設聊天室後端資料庫 （先前和目前版本，如常設聊天室） 的存取權的已加入網域的機器上安裝的常設聊天室 Resource Kit 工具。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-207">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Persistent Chat back-end databases (previous and current versions for Persistent Chat).</span></span>

<span data-ttu-id="fcb5a-208">執行工具的使用者帳戶必須具備的常設聊天室資料庫的讀取權限。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-208">The user account under which the tool runs must have Read access to the Persistent Chat databases.</span></span>

<span data-ttu-id="fcb5a-209">ChatUpgradeVerifier.exe.config 檔案必須包含 GroupChat2007R2Db 參數或 GroupChat2010Db 參數，以連接字串至適當的群組聊天資料庫 （Groupchat 2007R2 或 2010年）。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-209">The ChatUpgradeVerifier.exe.config file must contain either the GroupChat2007R2Db parameter or the GroupChat2010Db parameter, with a connection string to the appropriate Group Chat database (either Groupchat 2007R2 or 2010).</span></span> <span data-ttu-id="fcb5a-210">它也必須包含一個 PersistentChat2013Db 參數，以常設聊天室 2013年資料庫的連接字串。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-210">It must also contain a PersistentChat2013Db parameter, with a connection string to the Persistent Chat 2013 database.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="fcb5a-211">Usage</span><span class="sxs-lookup"><span data-stu-id="fcb5a-211">Usage</span></span>

<span data-ttu-id="fcb5a-212">執行**ChatUpgradeVerifier**不含任何參數。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-212">Run **ChatUpgradeVerifier** without any parameters.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="fcb5a-213">範例</span><span class="sxs-lookup"><span data-stu-id="fcb5a-213">Example</span></span>

<span data-ttu-id="fcb5a-214">![執行 ChatUpgradeVerifier.exe。](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "執行 ChatUpgradeVerifier.exe。")</span><span class="sxs-lookup"><span data-stu-id="fcb5a-214">![Running ChatUpgradeVerifier.exe.](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "Running ChatUpgradeVerifier.exe.")</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-usage-report"></a><span data-ttu-id="fcb5a-215">常設聊天室使用情況報告</span><span class="sxs-lookup"><span data-stu-id="fcb5a-215">Persistent Chat Usage Report</span></span>

<div>

## <a name="description"></a><span data-ttu-id="fcb5a-216">說明</span><span class="sxs-lookup"><span data-stu-id="fcb5a-216">Description</span></span>

<span data-ttu-id="fcb5a-217">ChatUsageReport 工具產生 HTML 報告的常設聊天室服務流量。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-217">The ChatUsageReport tool generates an HTML report of Persistent Chat service usage.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="fcb5a-218">需求</span><span class="sxs-lookup"><span data-stu-id="fcb5a-218">Requirements</span></span>

<span data-ttu-id="fcb5a-219">具有常設聊天室後端資料庫的存取權的已加入網域的機器上安裝的常設聊天室 Resource Kit 工具。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-219">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="fcb5a-220">下執行此工具的使用者帳戶必須具備的常設聊天室後端資料庫的讀取權限。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-220">The user account under which the tool is run must have Read access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="fcb5a-221">該檔案，ChatUsageReport.exe.config，必須包含\<connectionStrings\> ] 區段中定義的連接字串的常設聊天室後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-221">The file, ChatUsageReport.exe.config, must contain a \<connectionStrings\> section defining the connection string to the Persistent Chat back-end database.</span></span> <span data-ttu-id="fcb5a-222">預設設定檔的內容會包含在這裡，供您參考。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-222">The contents of the default config file are included here, for your reference.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="fcb5a-223">Usage</span><span class="sxs-lookup"><span data-stu-id="fcb5a-223">Usage</span></span>

```Powershell
    ChatUsageReport [-StartDate {date}] [-EndDate {date}] [-TopActiveUsers {n}] [-TopActiveRooms {n}] [-LeastActiveRooms {n}] [-RoomsInactiveSince {Date}] [-OutputFolder {path}]
```
<span data-ttu-id="fcb5a-224">這些參數定義資料的選取範圍：</span><span class="sxs-lookup"><span data-stu-id="fcb5a-224">These parameters define the selection of data:</span></span>

<span data-ttu-id="fcb5a-225">**StartDate:**（選用） 指定 UTC 的開始日期的選取範圍期間。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-225">**StartDate:** Optionally specifies the UTC start date of the selection period.</span></span> <span data-ttu-id="fcb5a-226">預設值： 最早日期</span><span class="sxs-lookup"><span data-stu-id="fcb5a-226">Default: Earliest Date</span></span>

<span data-ttu-id="fcb5a-227">**EndDate:**（選用） 指定的選取範圍期間的 UTC 結束日期。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-227">**EndDate:** Optionally specifies the UTC end date of the selection period.</span></span> <span data-ttu-id="fcb5a-228">預設值： 現在</span><span class="sxs-lookup"><span data-stu-id="fcb5a-228">Default: Now</span></span>

<span data-ttu-id="fcb5a-229">這些參數定義方式並要顯示的資料：</span><span class="sxs-lookup"><span data-stu-id="fcb5a-229">These parameters define how and what data is displayed:</span></span>

<span data-ttu-id="fcb5a-230">**TopActiveUsers:** 如果指定此參數，報表會在選取時段內就在聊天室中包含方面的使用者已張貼的訊息數目 n 個最活躍的使用者。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-230">**TopActiveUsers:** If this is specified, the report will include the n most active users in terms of the number of messages the user has posted in the chat room for the selected period.</span></span> <span data-ttu-id="fcb5a-231">預設值：10</span><span class="sxs-lookup"><span data-stu-id="fcb5a-231">Default: 10</span></span>

<span data-ttu-id="fcb5a-232">**TopActiveRooms:** 如果指定此參數，報表會包含在選取時段內聊天室中張貼的訊息數目方面 n 最活躍聊天室。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-232">**TopActiveRooms:** If this is specified, the report will include the n most active chat rooms in terms of the number of messages posted in the room for the selected period.</span></span> <span data-ttu-id="fcb5a-233">預設值：10</span><span class="sxs-lookup"><span data-stu-id="fcb5a-233">Default: 10</span></span>

<span data-ttu-id="fcb5a-234">**LeastActiveRooms:** 如果指定此參數，報告都會包含 n 至少作用中的聊天室數方面的聊天室中張貼在選取時段內的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-234">**LeastActiveRooms:** If this is specified, the report will include the n least active chat rooms in terms of the number of messages posted in the chat room for the selected period.</span></span> <span data-ttu-id="fcb5a-235">聊天室必須至少一個張貼的訊息。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-235">Rooms will have at least one message posted.</span></span> <span data-ttu-id="fcb5a-236">預設值：10</span><span class="sxs-lookup"><span data-stu-id="fcb5a-236">Default: 10</span></span>

<span data-ttu-id="fcb5a-237">**RoomsInactiveSince:** 如果指定此參數，報表會包含指定日期之後已停用的聊天室清單。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-237">**RoomsInactiveSince:** If this is specified, the report will include a list of chat rooms that have been inactive since the specified date.</span></span> <span data-ttu-id="fcb5a-238">預設值： 整個時間</span><span class="sxs-lookup"><span data-stu-id="fcb5a-238">Default: Entire Time</span></span>

<span data-ttu-id="fcb5a-239">**OutputFolder:** 要放置 ChatUsageReport.html 和 graph 圖像] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-239">**OutputFolder:** The folder where the ChatUsageReport.html and the graph images will be placed.</span></span> <span data-ttu-id="fcb5a-240">這必須定義在組態檔中或在命令列上。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-240">This must be defined in the config file or on the command line.</span></span>

<span data-ttu-id="fcb5a-241">所有命令列參數的值也可以指定 ChatUsageReport.exe.config 檔案位於工具的相同目錄中。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-241">All of the command line parameter values can also be specified in the ChatUsageReport.exe.config file that is located in the same directory as the tool.</span></span> <span data-ttu-id="fcb5a-242">如果未指定任何值，組態檔和命令列中，命令列的值會覆寫設定檔值。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-242">If any value is specified in both the config file and the command line, the command line value will override the config file value.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="fcb5a-243">輸出</span><span class="sxs-lookup"><span data-stu-id="fcb5a-243">Output</span></span>

<span data-ttu-id="fcb5a-244">報表永遠會包含下列輸出：</span><span class="sxs-lookup"><span data-stu-id="fcb5a-244">The report will always include the following output:</span></span>

  - <span data-ttu-id="fcb5a-245">所選期間內張貼 top n 最活躍聊天室的訊息數目。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-245">Top n most active chat rooms by number of message posts for selected period.</span></span>

  - <span data-ttu-id="fcb5a-246">最 n 最活躍的使用者所選取的期間的郵件文章數。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-246">Top n most active users by number of message posts for selected period.</span></span>

  - <span data-ttu-id="fcb5a-247">所選期間內張貼 top n 至少 active 聊天室的訊息數目。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-247">Top n least active chat rooms by number of message posts for selected period.</span></span>

  - <span data-ttu-id="fcb5a-248">非作用中的整個生命週期的資料庫，或指定日期之後的聊天室。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-248">Chat rooms that are inactive for the entire life of the database, or since the specified date.</span></span>

  - <span data-ttu-id="fcb5a-249">每日訊息張貼趨勢針對選取的期間。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-249">Daily message post trend for selected period.</span></span>

  - <span data-ttu-id="fcb5a-250">每週的郵件所選期間內張貼趨勢。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-250">Weekly message post trend for selected period.</span></span>

  - <span data-ttu-id="fcb5a-251">針對每月訊息張貼趨勢選取期間。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-251">Monthly message post trend for selected period.</span></span>

  - <span data-ttu-id="fcb5a-252">所選期間內張貼訊息總數。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-252">Total message posts for selected period.</span></span>

  - <span data-ttu-id="fcb5a-253">已啟用的聊天室總數。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-253">Total number of enabled rooms.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="fcb5a-254">範例</span><span class="sxs-lookup"><span data-stu-id="fcb5a-254">Example</span></span>

<span data-ttu-id="fcb5a-255">下列範例會使用情況報告產生整個 2001 年的並置於 OutputFolder ChatUsageReport.exe.config 中指定的報表。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-255">The following example generates a usage report for the entire year 2001 and places the report in the OutputFolder specified in the ChatUsageReport.exe.config.</span></span>

```Powershell
    ChatUsageReport -RoomsInactiveSince 06-20-2010
```
<span data-ttu-id="fcb5a-256">ChatUsageReport.exe.config:</span><span class="sxs-lookup"><span data-stu-id="fcb5a-256">ChatUsageReport.exe.config:</span></span>

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

## <a name="scheduleadsyncforprincipal"></a><span data-ttu-id="fcb5a-257">ScheduleADSyncForPrincipal</span><span class="sxs-lookup"><span data-stu-id="fcb5a-257">ScheduleADSyncForPrincipal</span></span>

<div>

## <a name="description"></a><span data-ttu-id="fcb5a-258">說明</span><span class="sxs-lookup"><span data-stu-id="fcb5a-258">Description</span></span>

<span data-ttu-id="fcb5a-259">ScheduleADSyncForPrincipal 是必須在 SQL Server Management Studio 連線至常設聊天室後端資料庫時的 [直接從執行 Microsoft SQL Server 2012 指令碼。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-259">ScheduleADSyncForPrincipal is a Microsoft SQL Server 2012 script that must be run directly from within SQL Server Management Studio when connected to the Persistent Chat back-end database.</span></span> <span data-ttu-id="fcb5a-260">此指令碼可讓您強制常設聊天室與進行同步處理其記錄的使用者的 Active Directory 網域服務，而不是等待排定的同步處理的時間。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-260">This script enables you to force Persistent Chat to synchronize its records of a user with those of Active Directory Domain Services, rather than waiting for the scheduled synchronization time.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="fcb5a-261">需求</span><span class="sxs-lookup"><span data-stu-id="fcb5a-261">Requirements</span></span>

<span data-ttu-id="fcb5a-262">在其下執行指令碼的使用者帳戶必須擁有者存取權的常設聊天室後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="fcb5a-262">The user account under which the script is run must have owner access to the Persistent Chat back-end database.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="fcb5a-263">Usage</span><span class="sxs-lookup"><span data-stu-id="fcb5a-263">Usage</span></span>

<span data-ttu-id="fcb5a-264">以下是預設的指令碼的內容：</span><span class="sxs-lookup"><span data-stu-id="fcb5a-264">Following are the contents of the default script:</span></span>

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

