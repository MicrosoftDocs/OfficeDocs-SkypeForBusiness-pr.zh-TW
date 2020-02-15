---
title: 管理電腦、 網站及全域集中式記錄服務組態
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing computer, site and global Centralized Logging Service configuration
ms:assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688138(v=OCS.15)
ms:contentKeyID: 49733738
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b405cef9efd63956b6d676d751027318897f5e98
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043115"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-computer-site-and-global-centralized-logging-service-configuration-in-lync-server-2013"></a><span data-ttu-id="10a86-102">管理電腦、 網站及 Lync Server 2013 中全域的集中式記錄服務組態</span><span class="sxs-lookup"><span data-stu-id="10a86-102">Managing computer, site and global Centralized Logging Service configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10a86-103">_**上次修改主題：** 2014年-02-04_</span><span class="sxs-lookup"><span data-stu-id="10a86-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="10a86-104">在範圍內，其中包含在單一電腦集區的電腦，在網站範圍 （亦即已定義的網站包含一群電腦和集區部署中的 Redmond 網站等），或在全域範圍 （亦即，可以執行 the Centralized Logging Service所有電腦和集區部署中的)。</span><span class="sxs-lookup"><span data-stu-id="10a86-104">The Centralized Logging Service can be run at a scope that includes a single computer, a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>

<span data-ttu-id="10a86-105">若要使用 Lync Server 管理命令介面設定集中式記錄服務範圍，您必須是 CsAdministrator 或 CsServerAdministrator 角色型存取控制 (RBAC) 安全性群組或包含的自訂 RBAC 角色的成員其中一個這兩個群組。</span><span class="sxs-lookup"><span data-stu-id="10a86-105">To configure the Centralized Logging Service scope by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="10a86-106">若要傳回所有獲指派此 cmdlet 的 RBAC 角色清單 （包括您自行建立的任何自訂 RBAC 角色），請從 [Lync Server 管理命令介面或 Windows PowerShell 提示字元執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="10a86-106">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

<span data-ttu-id="10a86-107">例如：</span><span class="sxs-lookup"><span data-stu-id="10a86-107">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>


> [!NOTE]
> <span data-ttu-id="10a86-108">Windows PowerShell 提供更多選項] 和 [不使用 CLSController.exe 的額外的設定選項。</span><span class="sxs-lookup"><span data-stu-id="10a86-108">Windows PowerShell provides you more options and additional configuration options that are not available by using CLSController.exe.</span></span> <span data-ttu-id="10a86-109">CLSController 提供更快速且簡潔的方法，來執行命令，但限制為一組命令提供的 CLSController。</span><span class="sxs-lookup"><span data-stu-id="10a86-109">CLSController offers a quick, concise method to run commands, but is limited to the set of commands available for the CLSController.</span></span> <span data-ttu-id="10a86-110">Windows PowerShell 不限制為只供 CLSController 命令處理器命令，並提供一組更廣的命令和一組更豐富的選項。</span><span class="sxs-lookup"><span data-stu-id="10a86-110">Windows PowerShell is not limited to just the command available to the command processor of the CLSController, and provides a wider set of commands and a richer set of options.</span></span> <span data-ttu-id="10a86-111">例如，CLSController.exe 並未提供範圍] 選項 – 電腦和 – 集區。</span><span class="sxs-lookup"><span data-stu-id="10a86-111">For example, CLSController.exe does provide you with a scope options for –computers and –pools.</span></span> <span data-ttu-id="10a86-112">您可以使用 Windows PowerShell，指出電腦或集區中大部分的命令，並定義 （CLSController 會有數量有限的案例不是使用者可修改） 的新案例您可以定義網站或全域範圍。</span><span class="sxs-lookup"><span data-stu-id="10a86-112">With Windows PowerShell, you can indicate computers or pools in most commands, and when you define new scenarios (CLSController has a finite number of scenarios that are not user modifiable) you can define a site or global scope.</span></span> <span data-ttu-id="10a86-113">此強大的功能的 Windows PowerShell 可讓您定義案例網站或全域範圍，但限制的電腦或集區的實際記錄。</span><span class="sxs-lookup"><span data-stu-id="10a86-113">This powerful feature of Windows PowerShell enables you to define a scenario a site or global scope, but limit the actual logging to a computer or pool.</span></span><BR><span data-ttu-id="10a86-114">有您可以在 Windows PowerShell 或 CLSController 中執行命令列工具命令的基本差異。</span><span class="sxs-lookup"><span data-stu-id="10a86-114">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="10a86-115">Windows PowerShell 提供豐富的方法，來設定和定義案例中，以及在有意義的方法，讓您疑難排解案例中重複使用這些案例。</span><span class="sxs-lookup"><span data-stu-id="10a86-115">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="10a86-116">雖然 CLSController 並提供快速和有效率方式來發出命令，並取得結果，設定 CLSController 受限於有限的命令檔] 命令，您必須能從命令列。</span><span class="sxs-lookup"><span data-stu-id="10a86-116">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="10a86-117">不同的 Windows PowerShell cmdlet CLSController 無法定義新的案例中，管理在網站或全域層級及許多其他限制的一組有限的命令，無法以動態方式設定的範圍。</span><span class="sxs-lookup"><span data-stu-id="10a86-117">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="10a86-118">CLSController 提供快速執行，Windows PowerShell 提供方法來擴充以外的功能可能會在使用 CLSController 的集中式記錄服務功能。</span><span class="sxs-lookup"><span data-stu-id="10a86-118">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span>



</div>

<span data-ttu-id="10a86-119">在單一電腦範圍可以定義[Search-csclslogging](https://technet.microsoft.com/library/JJ619189(v=OCS.15))、 [Show-csclslogging](https://technet.microsoft.com/library/JJ619173(v=OCS.15))、 [Start-csclslogging](https://technet.microsoft.com/library/JJ619190(v=OCS.15))、 [Stop-csclslogging](https://technet.microsoft.com/library/JJ619180(v=OCS.15))、 [Sync-csclslogging](https://technet.microsoft.com/library/JJ619169(v=OCS.15))及[Update-csclslogging](https://technet.microsoft.com/library/JJ619170(v=OCS.15))命令使用的執行期間將 – Computers 參數。</span><span class="sxs-lookup"><span data-stu-id="10a86-119">A single computer scope can be defined during the execution of a [Search-CsClsLogging](https://technet.microsoft.com/library/JJ619189(v=OCS.15)), [Show-CsClsLogging](https://technet.microsoft.com/library/JJ619173(v=OCS.15)), [Start-CsClsLogging](https://technet.microsoft.com/library/JJ619190(v=OCS.15)), [Stop-CsClsLogging](https://technet.microsoft.com/library/JJ619180(v=OCS.15)), [Sync-CsClsLogging](https://technet.microsoft.com/library/JJ619169(v=OCS.15)) and [Update-CsClsLogging](https://technet.microsoft.com/library/JJ619170(v=OCS.15)) command using the –Computers parameter.</span></span> <span data-ttu-id="10a86-120">– 電腦參數可接受的在目標電腦的完整的網域名稱 (Fqdn) 以逗號分隔清單。</span><span class="sxs-lookup"><span data-stu-id="10a86-120">The –Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="10a86-121">您也可以定義 – 集區以及您想要執行記錄命令的集區的逗號分隔清單。</span><span class="sxs-lookup"><span data-stu-id="10a86-121">You can also define –Pools and a comma separated list of pools that you want to run the logging commands on.</span></span>



</div>

<span data-ttu-id="10a86-122">網站和全域範圍定義**New-**、 **Set-**、 和**Remove-** Centralized Logging Service cmdlet。</span><span class="sxs-lookup"><span data-stu-id="10a86-122">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="10a86-123">下列範例會示範如何設定網站及全域範圍。</span><span class="sxs-lookup"><span data-stu-id="10a86-123">The following examples demonstrate how to set a site and a global scope.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="10a86-124">參數和其他章節中所述的概念，可能會包含所示的命令。</span><span class="sxs-lookup"><span data-stu-id="10a86-124">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="10a86-125">範例命令主要在示範如何使用<STRONG>– Identity</STRONG>參數，以定義範圍，以及其他參數都包含在內的完整性，並指定範圍。</span><span class="sxs-lookup"><span data-stu-id="10a86-125">The example commands are intended to demonstrate the use of the <STRONG>–Identity</STRONG> parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="10a86-126">如需<STRONG>Set-csclsconfiguration</STRONG> cmdlet 的詳細資訊，請參閱作業文件中的<A href="https://technet.microsoft.com/library/JJ619182(v=OCS.15)">Set-csclsconfiguration</A> 。</span><span class="sxs-lookup"><span data-stu-id="10a86-126">For details about the <STRONG>Set-CsClsConfiguration</STRONG> cmdlets, see <A href="https://technet.microsoft.com/library/JJ619182(v=OCS.15)">Set-CsClsConfiguration</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="10a86-127">若要擷取目前的集中式記錄服務組態</span><span class="sxs-lookup"><span data-stu-id="10a86-127">To retrieve the current Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="10a86-128">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="10a86-128">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="10a86-129">在命令列提示字元處輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="10a86-129">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration

<span data-ttu-id="10a86-130">使用**New-csclsconfiguration**和**Set-csclsconfiguration** cmdlet 來建立新的設定或更新現有的組態。</span><span class="sxs-lookup"><span data-stu-id="10a86-130">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.</span></span>

<span data-ttu-id="10a86-131">當您執行**Get-csclsconfiguration**時，它會顯示類似以下螢幕擷取畫面，其中的部署目前具備預設的全域設定，但定義任何網站設定的資訊：</span><span class="sxs-lookup"><span data-stu-id="10a86-131">When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>

<span data-ttu-id="10a86-132">![從 Get-csclsconfiguration 輸出的範例。](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "從 Get-csclsconfiguration 輸出的範例。")</span><span class="sxs-lookup"><span data-stu-id="10a86-132">![Sample output from Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Sample output from Get-CsClsConfiguration.")</span></span>

</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="10a86-133">若要從電腦本機存放區擷取目前的集中式記錄服務組態</span><span class="sxs-lookup"><span data-stu-id="10a86-133">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1.  <span data-ttu-id="10a86-134">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="10a86-134">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="10a86-135">在命令列提示字元處輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="10a86-135">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration -LocalStore

<span data-ttu-id="10a86-136">當您使用的第一個範例**Get-csclsconfiguration**沒有指定任何參數，命令參照的中央管理存放區的資料。</span><span class="sxs-lookup"><span data-stu-id="10a86-136">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="10a86-137">如果您指定參數 – LocalStore，此命令會參考電腦 LocalStore 而不是中央管理存放區。</span><span class="sxs-lookup"><span data-stu-id="10a86-137">If you specify the parameter –LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>

</div>

<div>

## <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="10a86-138">若要擷取目前定義的案例清單</span><span class="sxs-lookup"><span data-stu-id="10a86-138">To retrieve a listing of scenarios currently defined</span></span>

1.  <span data-ttu-id="10a86-139">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="10a86-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="10a86-140">在命令列提示字元處輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="10a86-140">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    <span data-ttu-id="10a86-141">例如，若要擷取定義於全域範圍的案例：</span><span class="sxs-lookup"><span data-stu-id="10a86-141">For example, to retrieve the scenarios that is defined at the global scope:</span></span>
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

<span data-ttu-id="10a86-142">**Get-csclsconfiguration**指令程式永遠會顯示在指定的範圍設定的一部分的案例。</span><span class="sxs-lookup"><span data-stu-id="10a86-142">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope’s configuration.</span></span> <span data-ttu-id="10a86-143">在大多數情況下，所有案例不會顯示，並無條件捨去。</span><span class="sxs-lookup"><span data-stu-id="10a86-143">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="10a86-144">在這裡使用的命令會列出所有的案例和部分資訊何種提供者]，[設定]，並使用旗標。</span><span class="sxs-lookup"><span data-stu-id="10a86-144">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>

</div>

<div>

## <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="10a86-145">若要使用 Windows PowerShell 更新 the Centralized Logging Service 全域範圍</span><span class="sxs-lookup"><span data-stu-id="10a86-145">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1.  <span data-ttu-id="10a86-146">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="10a86-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="10a86-147">在命令列提示字元處輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="10a86-147">Type the following at the command-line prompt:</span></span>
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    <span data-ttu-id="10a86-148">例如：</span><span class="sxs-lookup"><span data-stu-id="10a86-148">For example:</span></span>
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

<span data-ttu-id="10a86-149">此命令告知 clsagent 的通訊上每個電腦和集區中部署，以設定為 40 mb 的追蹤檔案變換值的大小。</span><span class="sxs-lookup"><span data-stu-id="10a86-149">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes.</span></span> <span data-ttu-id="10a86-150">電腦和集區中的所有網站都受到命令，並會將其設定的追蹤記錄檔變換值設定為 40 mb。</span><span class="sxs-lookup"><span data-stu-id="10a86-150">Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>

</div>

<div>

## <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="10a86-151">若要使用 Windows PowerShell 更新集中式記錄服務的站台範圍</span><span class="sxs-lookup"><span data-stu-id="10a86-151">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1.  <span data-ttu-id="10a86-152">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="10a86-152">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="10a86-153">在命令列提示字元處輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="10a86-153">Type the following at the command-line prompt:</span></span>
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    <span data-ttu-id="10a86-154">例如：</span><span class="sxs-lookup"><span data-stu-id="10a86-154">For example:</span></span>
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="10a86-155">此範例所述，記錄檔的預設位置是 %temp%\tracing。</span><span class="sxs-lookup"><span data-stu-id="10a86-155">As noted in the example, the default location of the log files is %TEMP%\Tracing.</span></span> <span data-ttu-id="10a86-156">不過，因為它是實際 clsagent 的通訊寫入檔案，且 CSLAgent 執行為網路服務，%TEMP%變數就會展開成 %windir%\serviceprofiles\networkservice\appdata\local 中。</span><span class="sxs-lookup"><span data-stu-id="10a86-156">However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span>

    
    </div>

<span data-ttu-id="10a86-157">命令會告知 clsagent 的通訊，每個電腦和集區中設定為 40 mb 的追蹤檔案變換值的大小 Redmond 網站上。</span><span class="sxs-lookup"><span data-stu-id="10a86-157">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes.</span></span> <span data-ttu-id="10a86-158">電腦和集區中的其他網站不會受到命令，並要繼續使用定義預設 (20 mb) 或啟動記錄工作階段期間的目前設定的追蹤記錄檔變換值。</span><span class="sxs-lookup"><span data-stu-id="10a86-158">Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>

</div>

<div>

## <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="10a86-159">若要建立新的集中式記錄服務組態</span><span class="sxs-lookup"><span data-stu-id="10a86-159">To create a new Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="10a86-160">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="10a86-160">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="10a86-161">在命令列提示字元處輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="10a86-161">Type the following at the command-line prompt:</span></span>
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="10a86-162">New-csclsconfiguration 會提供存取權大量選用的組態設定。</span><span class="sxs-lookup"><span data-stu-id="10a86-162">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="10a86-163">如需組態選項的詳細資訊，請參閱<A href="https://technet.microsoft.com/library/JJ619179(v=OCS.15)">Get-csclsconfiguration</A>和<A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">Lync Server 2013 中的瞭解集中式記錄服務組態設定</A>。</span><span class="sxs-lookup"><span data-stu-id="10a86-163">For details about the configuration options, see <A href="https://technet.microsoft.com/library/JJ619179(v=OCS.15)">Get-CsClsConfiguration</A> and <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">Understanding Centralized Logging Service configuration settings in Lync Server 2013</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="10a86-164">例如，若要建立新的設定來定義快取檔案，變換記錄檔的時間週期] 與 [記錄檔的變換大小的網路資料夾會輸入：</span><span class="sxs-lookup"><span data-stu-id="10a86-164">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

<span data-ttu-id="10a86-165">您應仔細規劃建立新的組態，以及如何針對 the Centralized Logging Service 定義新的屬性。</span><span class="sxs-lookup"><span data-stu-id="10a86-165">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="10a86-166">您應該謹慎進行變更，並確定您了解影響上您要適當地記錄問題案例的能力。</span><span class="sxs-lookup"><span data-stu-id="10a86-166">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="10a86-167">您應該將增強您能夠管理記錄檔大小的組態和變換期間，這樣它就會發生時，解決問題，進行變更。</span><span class="sxs-lookup"><span data-stu-id="10a86-167">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>

</div>

<div>

## <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="10a86-168">若要移除現有的集中式記錄服務組態</span><span class="sxs-lookup"><span data-stu-id="10a86-168">To remove an existing Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="10a86-169">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="10a86-169">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="10a86-170">在命令列提示字元處輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="10a86-170">Type the following at the command-line prompt:</span></span>
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    <span data-ttu-id="10a86-171">例如，若要移除您建立來提高記錄檔變換時間的集中式記錄服務組態，增加變換記錄檔的大小，並設定的記錄檔快取位置到網路共用，如下所示：</span><span class="sxs-lookup"><span data-stu-id="10a86-171">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="10a86-172">這是在 「 建立新的集中式記錄服務組態。 」 程序中建立的新組態</span><span class="sxs-lookup"><span data-stu-id="10a86-172">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span>

    
    </div>

<span data-ttu-id="10a86-173">如果您選擇移除網站層級設定，網站會使用全域設定。</span><span class="sxs-lookup"><span data-stu-id="10a86-173">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="10a86-174">另請參閱</span><span class="sxs-lookup"><span data-stu-id="10a86-174">See Also</span></span>


[<span data-ttu-id="10a86-175">Lync Server 2013 中的集中式的記錄服務概觀</span><span class="sxs-lookup"><span data-stu-id="10a86-175">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[<span data-ttu-id="10a86-176">管理 Lync Server 2013 中的集中式記錄服務組態設定</span><span class="sxs-lookup"><span data-stu-id="10a86-176">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
<span data-ttu-id="10a86-177">[Set-csclsconfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="10a86-177">[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span></span>  
<span data-ttu-id="10a86-178">[Get-csclsconfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="10a86-178">[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span></span>  
<span data-ttu-id="10a86-179">[New-csclsconfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="10a86-179">[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span></span>  
<span data-ttu-id="10a86-180">[Remove-csclsconfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="10a86-180">[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

