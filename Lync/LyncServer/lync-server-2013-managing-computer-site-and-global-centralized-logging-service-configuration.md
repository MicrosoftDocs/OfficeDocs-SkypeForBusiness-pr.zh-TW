---
title: 管理電腦、網站和全域集中式記錄服務設定
description: 管理電腦、網站和全域集中式記錄服務設定。
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
ms.openlocfilehash: 37dee125d69e17664fddd0c32feb3048ffcf91b5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570379"
---
# <a name="managing-computer-site-and-global-centralized-logging-service-configuration-in-lync-server-2013"></a><span data-ttu-id="67873-103">在 Lync Server 2013 中管理電腦、網站和全域集中式記錄服務設定</span><span class="sxs-lookup"><span data-stu-id="67873-103">Managing computer, site and global Centralized Logging Service configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67873-104">_**主題上次修改日期：** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="67873-104">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="67873-105">集中式記錄服務可以在包含單一電腦、電腦集區、網站範圍 (，也就是定義的網站（例如，包含部署) 中的電腦及集區集合的網站 Redmond）執行，也可以在全域範圍 (（即部署) 中的所有電腦與集區）的範圍內執行。</span><span class="sxs-lookup"><span data-stu-id="67873-105">The Centralized Logging Service can be run at a scope that includes a single computer, a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>

<span data-ttu-id="67873-106">若要使用 Lync Server 管理命令介面來設定集中式記錄服務範圍，您必須是 CsAdministrator 或 CsServerAdministrator 角色型存取控制 (RBAC) 安全性群組的成員，或是包含這兩個群組之任一個自訂 RBAC 角色的成員。</span><span class="sxs-lookup"><span data-stu-id="67873-106">To configure the Centralized Logging Service scope by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="67873-107">若要傳回所有獲指派此 Cmdlet 的 RBAC 角色清單 (包括您自行建立的自訂 RBAC 角色) ，請從 Lync Server 管理命令介面或 Windows PowerShell 提示中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="67873-107">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

<span data-ttu-id="67873-108">例如：</span><span class="sxs-lookup"><span data-stu-id="67873-108">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>


> [!NOTE]
> <span data-ttu-id="67873-109">Windows PowerShell 會提供更多選項及其他無法使用 CLSController.exe 所無法使用的設定選項。</span><span class="sxs-lookup"><span data-stu-id="67873-109">Windows PowerShell provides you more options and additional configuration options that are not available by using CLSController.exe.</span></span> <span data-ttu-id="67873-110">CLSController 提供一種快速、簡潔的方法來執行命令，但僅限於可用於 CLSController 的命令集。</span><span class="sxs-lookup"><span data-stu-id="67873-110">CLSController offers a quick, concise method to run commands, but is limited to the set of commands available for the CLSController.</span></span> <span data-ttu-id="67873-111">Windows PowerShell 不僅限於 CLSController 的命令處理器可使用的命令，而且提供更多的命令和一組更豐富的選項。</span><span class="sxs-lookup"><span data-stu-id="67873-111">Windows PowerShell is not limited to just the command available to the command processor of the CLSController, and provides a wider set of commands and a richer set of options.</span></span> <span data-ttu-id="67873-112">例如，CLSController.exe 確實為您提供了-電腦和–集區的範圍選項。</span><span class="sxs-lookup"><span data-stu-id="67873-112">For example, CLSController.exe does provide you with a scope options for –computers and –pools.</span></span> <span data-ttu-id="67873-113">透過 Windows PowerShell，您可以在大多數命令中指出電腦或集區，並在定義新案例時 (CLSController 具有有限數量的案例，而這些案例並非使用者可修改) 您可以定義網站或全域範圍。</span><span class="sxs-lookup"><span data-stu-id="67873-113">With Windows PowerShell, you can indicate computers or pools in most commands, and when you define new scenarios (CLSController has a finite number of scenarios that are not user modifiable) you can define a site or global scope.</span></span> <span data-ttu-id="67873-114">Windows PowerShell 的這項強大功能可讓您定義網站或全域範圍的案例，但限制實際記錄為電腦或集區。</span><span class="sxs-lookup"><span data-stu-id="67873-114">This powerful feature of Windows PowerShell enables you to define a scenario a site or global scope, but limit the actual logging to a computer or pool.</span></span><BR><span data-ttu-id="67873-115">您可以在 Windows PowerShell 或 CLSController 中執行的命令列命令之間有基本差異。</span><span class="sxs-lookup"><span data-stu-id="67873-115">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="67873-116">Windows PowerShell 提供豐富的方法來設定及定義案例，並以有意義的方式針對疑難排解案例重複使用這些案例。</span><span class="sxs-lookup"><span data-stu-id="67873-116">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="67873-117">雖然 CLSController 提供快速且有效的方式來發出命令並取得結果，但 CLSController 的命令設定會受限於您在命令列中使用的有限命令。</span><span class="sxs-lookup"><span data-stu-id="67873-117">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="67873-118">與 Windows PowerShell Cmdlet 不同的是，CLSController 無法定義新案例、管理網站或全域層級的範圍，以及無法動態設定之有限命令集的其他許多限制。</span><span class="sxs-lookup"><span data-stu-id="67873-118">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="67873-119">雖然 CLSController 提供快速執行的方法，但 Windows PowerShell 提供一種方法來擴充集中式記錄服務功能，以超越 CLSController 的可能。</span><span class="sxs-lookup"><span data-stu-id="67873-119">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span>



</div>

<span data-ttu-id="67873-120">使用– computer 參數，可在執行 [Search-CsClsLogging](https://technet.microsoft.com/library/JJ619189(v=OCS.15))、 [Show-CsClsLogging](https://technet.microsoft.com/library/JJ619173(v=OCS.15))、 [Start-CsClsLogging](https://technet.microsoft.com/library/JJ619190(v=OCS.15))、 [Stop-CsClsLogging](https://technet.microsoft.com/library/JJ619180(v=OCS.15))、 [Sync-CsClsLogging](https://technet.microsoft.com/library/JJ619169(v=OCS.15)) 和 [Update-CsClsLogging](https://technet.microsoft.com/library/JJ619170(v=OCS.15)) 命令期間定義單一電腦範圍。</span><span class="sxs-lookup"><span data-stu-id="67873-120">A single computer scope can be defined during the execution of a [Search-CsClsLogging](https://technet.microsoft.com/library/JJ619189(v=OCS.15)), [Show-CsClsLogging](https://technet.microsoft.com/library/JJ619173(v=OCS.15)), [Start-CsClsLogging](https://technet.microsoft.com/library/JJ619190(v=OCS.15)), [Stop-CsClsLogging](https://technet.microsoft.com/library/JJ619180(v=OCS.15)), [Sync-CsClsLogging](https://technet.microsoft.com/library/JJ619169(v=OCS.15)) and [Update-CsClsLogging](https://technet.microsoft.com/library/JJ619170(v=OCS.15)) command using the –Computers parameter.</span></span> <span data-ttu-id="67873-121">– Computer 參數會接受以逗號分隔的完整功能變數名稱清單，該清單是目的電腦的 (Fqdn) 。</span><span class="sxs-lookup"><span data-stu-id="67873-121">The –Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="67873-122">您也可以定義集區和以逗號分隔的集區清單，您想要在其上執行記錄指令。</span><span class="sxs-lookup"><span data-stu-id="67873-122">You can also define –Pools and a comma separated list of pools that you want to run the logging commands on.</span></span>



</div>

<span data-ttu-id="67873-123">網站和全域範圍是在 **新的**、 **集合**及 **移除** 集中式記錄服務 Cmdlet 中定義。</span><span class="sxs-lookup"><span data-stu-id="67873-123">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="67873-124">下列範例會示範如何設定網站和全域範圍。</span><span class="sxs-lookup"><span data-stu-id="67873-124">The following examples demonstrate how to set a site and a global scope.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="67873-125">所顯示的命令可能包含其他章節中所涵蓋的參數和概念。</span><span class="sxs-lookup"><span data-stu-id="67873-125">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="67873-126">範例命令的目的是為了示範如何使用 <STRONG>-Identity</STRONG> 參數來定義範圍，並包含其他參數，以進行完整性及指定範圍。</span><span class="sxs-lookup"><span data-stu-id="67873-126">The example commands are intended to demonstrate the use of the <STRONG>–Identity</STRONG> parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="67873-127">如需 <STRONG>Set-CsClsConfiguration</STRONG> Cmdlet 的詳細資訊，請參閱 Operations 檔中的 <A href="https://technet.microsoft.com/library/JJ619182(v=OCS.15)">Set-CsClsConfiguration</A> 。</span><span class="sxs-lookup"><span data-stu-id="67873-127">For details about the <STRONG>Set-CsClsConfiguration</STRONG> cmdlets, see <A href="https://technet.microsoft.com/library/JJ619182(v=OCS.15)">Set-CsClsConfiguration</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="67873-128">若要取得目前的集中式記錄服務設定</span><span class="sxs-lookup"><span data-stu-id="67873-128">To retrieve the current Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="67873-129">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="67873-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="67873-130">在命令列提示字元處，輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="67873-130">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration

<span data-ttu-id="67873-131">使用 **New-CsClsConfiguration** 和 **Set-CsClsConfiguration** Cmdlet 來建立新的設定或更新現有的設定。</span><span class="sxs-lookup"><span data-stu-id="67873-131">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.</span></span>

<span data-ttu-id="67873-132">當您執行 **Get-CsClsConfiguration**時，它會顯示與下列螢幕擷取畫面類似的資訊，其中的部署目前具有預設全域設定，但未定義網站配置：</span><span class="sxs-lookup"><span data-stu-id="67873-132">When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>

<span data-ttu-id="67873-133">![Get-CsClsConfiguration 的輸出範例。](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Get-CsClsConfiguration 的輸出範例。")</span><span class="sxs-lookup"><span data-stu-id="67873-133">![Sample output from Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Sample output from Get-CsClsConfiguration.")</span></span>

</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="67873-134">從電腦本地存放區中取得目前的集中式記錄服務設定</span><span class="sxs-lookup"><span data-stu-id="67873-134">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1.  <span data-ttu-id="67873-135">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="67873-135">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="67873-136">在命令列提示字元處，輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="67873-136">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration -LocalStore

<span data-ttu-id="67873-137">當您使用第一個範例，其中 **Get-CsClsConfiguration** 未指定任何參數時，此命令會參考資料的中央管理存放區。</span><span class="sxs-lookup"><span data-stu-id="67873-137">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="67873-138">如果您指定參數– LocalStore，此命令會參照電腦 LocalStore 而非中央管理存放區。</span><span class="sxs-lookup"><span data-stu-id="67873-138">If you specify the parameter –LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>

</div>

<div>

## <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="67873-139">若要取得目前定義的案例清單</span><span class="sxs-lookup"><span data-stu-id="67873-139">To retrieve a listing of scenarios currently defined</span></span>

1.  <span data-ttu-id="67873-140">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="67873-140">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="67873-141">在命令列提示字元處，輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="67873-141">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    <span data-ttu-id="67873-142">例如，若要檢索在全域範圍內定義的案例：</span><span class="sxs-lookup"><span data-stu-id="67873-142">For example, to retrieve the scenarios that is defined at the global scope:</span></span>
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

<span data-ttu-id="67873-143">Cmdlet **Get-CsClsConfiguration** 一定會顯示屬於特定範圍設定之部分的案例。</span><span class="sxs-lookup"><span data-stu-id="67873-143">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope’s configuration.</span></span> <span data-ttu-id="67873-144">在大多數情況下，不會顯示所有案例，而且會被截斷。</span><span class="sxs-lookup"><span data-stu-id="67873-144">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="67873-145">此處所用的命令會列出使用的提供者、設定及旗標的所有案例及部分資訊。</span><span class="sxs-lookup"><span data-stu-id="67873-145">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>

</div>

<div>

## <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="67873-146">使用 Windows PowerShell 更新集中式記錄服務的全域範圍</span><span class="sxs-lookup"><span data-stu-id="67873-146">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1.  <span data-ttu-id="67873-147">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="67873-147">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="67873-148">在命令列提示字元處，輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="67873-148">Type the following at the command-line prompt:</span></span>
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    <span data-ttu-id="67873-149">例如：</span><span class="sxs-lookup"><span data-stu-id="67873-149">For example:</span></span>
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

<span data-ttu-id="67873-150">命令會告訴部署中每台電腦及集區上的 CLSAgent，將追蹤檔案的變換值大小設定為 40 mb。</span><span class="sxs-lookup"><span data-stu-id="67873-150">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes.</span></span> <span data-ttu-id="67873-151">所有網站中的電腦與集區都會受到命令的影響，並會將其設定的追蹤記錄檔翻轉值設定為 40 mb。</span><span class="sxs-lookup"><span data-stu-id="67873-151">Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>

</div>

<div>

## <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="67873-152">使用 Windows PowerShell 更新集中式記錄服務的網站範圍</span><span class="sxs-lookup"><span data-stu-id="67873-152">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1.  <span data-ttu-id="67873-153">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="67873-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="67873-154">在命令列提示字元處，輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="67873-154">Type the following at the command-line prompt:</span></span>
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    <span data-ttu-id="67873-155">例如：</span><span class="sxs-lookup"><span data-stu-id="67873-155">For example:</span></span>
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="67873-156">如範例中所述，記錄檔的預設位置是%TEMP%\Tracing。</span><span class="sxs-lookup"><span data-stu-id="67873-156">As noted in the example, the default location of the log files is %TEMP%\Tracing.</span></span> <span data-ttu-id="67873-157">不過，由於實際 CLSAgent 是寫入檔案，而 CSLAgent 以網路服務方式執行，所以%TEMP% 變數會擴充為%WINDIR%\ServiceProfiles\NetworkService\AppData\Local。</span><span class="sxs-lookup"><span data-stu-id="67873-157">However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span>

    
    </div>

<span data-ttu-id="67873-158">命令會告訴 site Redmond 中每一部電腦及集區上的 CLSAgent，將追蹤檔案的變換值大小設定為 40 mb。</span><span class="sxs-lookup"><span data-stu-id="67873-158">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes.</span></span> <span data-ttu-id="67873-159">其他網站中的電腦及集區不會受到命令的影響，而且會繼續使用目前設定的追蹤記錄檔滾動更新值，此值是由預設 (20 mb) 或開始記錄會話期間所定義。</span><span class="sxs-lookup"><span data-stu-id="67873-159">Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>

</div>

<div>

## <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="67873-160">若要建立新的集中式記錄服務設定</span><span class="sxs-lookup"><span data-stu-id="67873-160">To create a new Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="67873-161">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="67873-161">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="67873-162">在命令列提示字元處，輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="67873-162">Type the following at the command-line prompt:</span></span>
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="67873-163">New-CsClsConfiguration 提供大量選用設定設定的存取權。</span><span class="sxs-lookup"><span data-stu-id="67873-163">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="67873-164">如需設定選項的詳細資訊，請參閱 <A href="https://technet.microsoft.com/library/JJ619179(v=OCS.15)">Get-CsClsConfiguration</A> 及 <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">瞭解 Lync Server 2013 中的集中式記錄服務設定設定</A>。</span><span class="sxs-lookup"><span data-stu-id="67873-164">For details about the configuration options, see <A href="https://technet.microsoft.com/library/JJ619179(v=OCS.15)">Get-CsClsConfiguration</A> and <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">Understanding Centralized Logging Service configuration settings in Lync Server 2013</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="67873-165">例如，若要建立新的設定以定義快取檔案的網路資料夾、滾動表檔的記錄檔和翻轉大小的時間週期，您可以輸入：</span><span class="sxs-lookup"><span data-stu-id="67873-165">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

<span data-ttu-id="67873-166">您應該仔細規劃新設定的建立，以及如何定義集中式記錄服務的新屬性。</span><span class="sxs-lookup"><span data-stu-id="67873-166">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="67873-167">您應謹慎進行變更，並確定您瞭解能夠正確記錄問題案例的影響。</span><span class="sxs-lookup"><span data-stu-id="67873-167">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="67873-168">您應該對設定進行變更，以增強您記錄管理大小的能力，以及可在發生問題時進行問題解決的翻轉期間。</span><span class="sxs-lookup"><span data-stu-id="67873-168">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>

</div>

<div>

## <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="67873-169">移除現有的集中式記錄服務設定</span><span class="sxs-lookup"><span data-stu-id="67873-169">To remove an existing Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="67873-170">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="67873-170">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="67873-171">在命令列提示字元處，輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="67873-171">Type the following at the command-line prompt:</span></span>
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    <span data-ttu-id="67873-172">例如，若要移除您已建立的集中式記錄服務設定，以增加記錄檔翻轉時間、增加翻轉記錄檔大小，並將記錄檔快取位置設為網路共用，如下所示：</span><span class="sxs-lookup"><span data-stu-id="67873-172">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="67873-173">這是在「建立新的集中式記錄服務設定」過程中建立的新設定。</span><span class="sxs-lookup"><span data-stu-id="67873-173">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span>

    
    </div>

<span data-ttu-id="67873-174">如果您選擇移除網站層級設定，則網站會使用通用設定。</span><span class="sxs-lookup"><span data-stu-id="67873-174">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="67873-175">另請參閱</span><span class="sxs-lookup"><span data-stu-id="67873-175">See Also</span></span>


[<span data-ttu-id="67873-176">Lync Server 2013 中的集中式記錄服務概述</span><span class="sxs-lookup"><span data-stu-id="67873-176">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[<span data-ttu-id="67873-177">在 Lync Server 2013 中管理集中式記錄服務設定設定</span><span class="sxs-lookup"><span data-stu-id="67873-177">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
<span data-ttu-id="67873-178">[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="67873-178">[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span></span>  
<span data-ttu-id="67873-179">[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="67873-179">[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span></span>  
<span data-ttu-id="67873-180">[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="67873-180">[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span></span>  
<span data-ttu-id="67873-181">[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="67873-181">[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

