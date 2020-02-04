---
title: 管理電腦、網站和全域集中式記錄服務設定
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
ms.openlocfilehash: 8f714c82fdc4ade0fc70b0a977e32ef46b26914d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729333"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-computer-site-and-global-centralized-logging-service-configuration-in-lync-server-2013"></a><span data-ttu-id="d81bc-102">在 Lync Server 2013 中管理電腦、網站和全域集中式記錄服務設定</span><span class="sxs-lookup"><span data-stu-id="d81bc-102">Managing computer, site and global Centralized Logging Service configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d81bc-103">_**主題上次修改日期：** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="d81bc-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="d81bc-104">集中式記錄服務可以在包含單一電腦的範圍中執行，也就是在網站範圍（也就是已定義的網站（例如在您的部署中包含電腦和池集合的網站雷蒙德），或全域範圍（也就是在您部署中的所有電腦和池）。</span><span class="sxs-lookup"><span data-stu-id="d81bc-104">The Centralized Logging Service can be run at a scope that includes a single computer, a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>

<span data-ttu-id="d81bc-105">若要使用 Lync Server 管理命令介面設定集中式記錄服務範圍，您必須是 CsAdministrator 或 CsServerAdministrator 角色式存取控制（RBAC）安全性群組的成員，或是包含下列內容的自訂 RBAC 角色：這兩個群組的其中一個。</span><span class="sxs-lookup"><span data-stu-id="d81bc-105">To configure the Centralized Logging Service scope by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="d81bc-106">若要傳回已指派這個 Cmdlet 的所有 RBAC 角色清單（包括您自行建立的任何自訂 RBAC 角色），請從 Lync Server 管理命令介面或 Windows PowerShell 提示字元執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="d81bc-106">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

<span data-ttu-id="d81bc-107">例如：</span><span class="sxs-lookup"><span data-stu-id="d81bc-107">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>


> [!NOTE]
> <span data-ttu-id="d81bc-108">Windows PowerShell 提供其他選項和其他無法使用 CLSController 提供的配置選項。</span><span class="sxs-lookup"><span data-stu-id="d81bc-108">Windows PowerShell provides you more options and additional configuration options that are not available by using CLSController.exe.</span></span> <span data-ttu-id="d81bc-109">CLSController 提供一種快速、簡明的方法來執行命令，但僅限於可供 CLSController 使用的命令組。</span><span class="sxs-lookup"><span data-stu-id="d81bc-109">CLSController offers a quick, concise method to run commands, but is limited to the set of commands available for the CLSController.</span></span> <span data-ttu-id="d81bc-110">Windows PowerShell 不受限於 CLSController 命令處理器提供的命令，並提供更多組的命令及更豐富的選項。</span><span class="sxs-lookup"><span data-stu-id="d81bc-110">Windows PowerShell is not limited to just the command available to the command processor of the CLSController, and provides a wider set of commands and a richer set of options.</span></span> <span data-ttu-id="d81bc-111">例如，CLSController 會提供-電腦和– pool 的範圍選項。</span><span class="sxs-lookup"><span data-stu-id="d81bc-111">For example, CLSController.exe does provide you with a scope options for –computers and –pools.</span></span> <span data-ttu-id="d81bc-112">在 Windows PowerShell 中，您可以在大部分命令中指示電腦或池，當您定義新的案例時（CLSController 的案例不一定是使用者可修改的），您可以定義網站或全域範圍。</span><span class="sxs-lookup"><span data-stu-id="d81bc-112">With Windows PowerShell, you can indicate computers or pools in most commands, and when you define new scenarios (CLSController has a finite number of scenarios that are not user modifiable) you can define a site or global scope.</span></span> <span data-ttu-id="d81bc-113">Windows PowerShell 的這項強大功能可讓您定義網站或全域範圍的案例，但限制實際記錄到電腦或池。</span><span class="sxs-lookup"><span data-stu-id="d81bc-113">This powerful feature of Windows PowerShell enables you to define a scenario a site or global scope, but limit the actual logging to a computer or pool.</span></span><BR><span data-ttu-id="d81bc-114">您可以在 Windows PowerShell 或 CLSController 中執行的命令列命令之間有一些基本差異。</span><span class="sxs-lookup"><span data-stu-id="d81bc-114">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="d81bc-115">Windows PowerShell 提供豐富的方法來設定及定義案例，並以一種有意義的方式在疑難排解案例中重複使用這些案例。</span><span class="sxs-lookup"><span data-stu-id="d81bc-115">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="d81bc-116">雖然 CLSController 確實提供快速且高效的方式來發出命令並取得結果，但 CLSController 的命令會受到您在命令列中提供的有限命令的限制。</span><span class="sxs-lookup"><span data-stu-id="d81bc-116">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="d81bc-117">與 Windows PowerShell Cmdlet 不同，CLSController 無法定義新案例、管理網站或全域階層的範圍，以及無法動態設定之有限命令集的許多其他限制。</span><span class="sxs-lookup"><span data-stu-id="d81bc-117">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="d81bc-118">雖然 CLSController 提供快速執行的方法，但 Windows PowerShell 提供了一種方式，可讓集中式記錄服務功能延伸到可能的 CLSController 以外。</span><span class="sxs-lookup"><span data-stu-id="d81bc-118">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span>



</div>

<span data-ttu-id="d81bc-119">在[搜尋 CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619189(v=OCS.15))（[顯示-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619173(v=OCS.15))、 [Start-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619190(v=OCS.15))、 [Stop-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15))、 [Sync-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619169(v=OCS.15))和[Update-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619170(v=OCS.15))命令）中，可以使用-電腦參數定義單一電腦範圍。</span><span class="sxs-lookup"><span data-stu-id="d81bc-119">A single computer scope can be defined during the execution of a [Search-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619189(v=OCS.15)), [Show-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619173(v=OCS.15)), [Start-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619190(v=OCS.15)), [Stop-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)), [Sync-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619169(v=OCS.15)) and [Update-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619170(v=OCS.15)) command using the –Computers parameter.</span></span> <span data-ttu-id="d81bc-120">-電腦參數會接受以逗號分隔的目的電腦完整功能變數名稱（Fqdn）清單。</span><span class="sxs-lookup"><span data-stu-id="d81bc-120">The –Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="d81bc-121">您也可以定義您想要執行記錄命令的 [彙集] 和 [逗號分隔的池清單]。</span><span class="sxs-lookup"><span data-stu-id="d81bc-121">You can also define –Pools and a comma separated list of pools that you want to run the logging commands on.</span></span>



</div>

<span data-ttu-id="d81bc-122">[網站] 和 [全域範圍] 是在**新**的、**集合**和**移除**集中式記錄服務 Cmdlet 中定義。</span><span class="sxs-lookup"><span data-stu-id="d81bc-122">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="d81bc-123">下列範例示範如何設定網站和全域範圍。</span><span class="sxs-lookup"><span data-stu-id="d81bc-123">The following examples demonstrate how to set a site and a global scope.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="d81bc-124">所顯示的命令可能包含其他章節所涵蓋的參數和概念。</span><span class="sxs-lookup"><span data-stu-id="d81bc-124">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="d81bc-125">這個範例命令是用來示範如何使用–身分<STRONG>識別</STRONG>參數來定義作用域，而其他參數則包括完整性並指定範圍。</span><span class="sxs-lookup"><span data-stu-id="d81bc-125">The example commands are intended to demonstrate the use of the <STRONG>–Identity</STRONG> parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="d81bc-126">如需<STRONG>設定 CsClsConfiguration</STRONG> Cmdlet 的詳細資料，請參閱作業檔中的<A href="https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15)">CsClsConfiguration</A> 。</span><span class="sxs-lookup"><span data-stu-id="d81bc-126">For details about the <STRONG>Set-CsClsConfiguration</STRONG> cmdlets, see <A href="https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15)">Set-CsClsConfiguration</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="d81bc-127">若要取得目前的集中式記錄服務設定</span><span class="sxs-lookup"><span data-stu-id="d81bc-127">To retrieve the current Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="d81bc-128">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="d81bc-128">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d81bc-129">在命令列提示處輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="d81bc-129">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration

<span data-ttu-id="d81bc-130">使用**新的 CsClsConfiguration**和**CsClsConfiguration** Cmdlet 來建立新的設定或更新現有的配置。</span><span class="sxs-lookup"><span data-stu-id="d81bc-130">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.</span></span>

<span data-ttu-id="d81bc-131">當您執行**CsClsConfiguration**時，它會顯示類似下列螢幕擷取畫面的資訊，其中的部署目前具有預設的全域設定，但未定義網站配置：</span><span class="sxs-lookup"><span data-stu-id="d81bc-131">When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>

<span data-ttu-id="d81bc-132">![Get-CsClsConfiguration 輸出範例。](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Get-CsClsConfiguration 輸出範例。")</span><span class="sxs-lookup"><span data-stu-id="d81bc-132">![Sample output from Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Sample output from Get-CsClsConfiguration.")</span></span>

</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="d81bc-133">從電腦當地商店中取得目前的集中式記錄服務設定</span><span class="sxs-lookup"><span data-stu-id="d81bc-133">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1.  <span data-ttu-id="d81bc-134">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="d81bc-134">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d81bc-135">在命令列提示處輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="d81bc-135">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration -LocalStore

<span data-ttu-id="d81bc-136">當您使用**CsClsConfiguration**未指定任何參數的第一個範例時，該命令會參照資料的中央管理儲存體。</span><span class="sxs-lookup"><span data-stu-id="d81bc-136">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="d81bc-137">如果您指定參數-LocalStore，命令會參照電腦 LocalStore，而不是中央管理儲存體。</span><span class="sxs-lookup"><span data-stu-id="d81bc-137">If you specify the parameter –LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>

</div>

<div>

## <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="d81bc-138">若要檢索目前定義的案例清單</span><span class="sxs-lookup"><span data-stu-id="d81bc-138">To retrieve a listing of scenarios currently defined</span></span>

1.  <span data-ttu-id="d81bc-139">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="d81bc-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d81bc-140">在命令列提示處輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="d81bc-140">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    <span data-ttu-id="d81bc-141">例如，若要檢索在全域範圍內定義的案例：</span><span class="sxs-lookup"><span data-stu-id="d81bc-141">For example, to retrieve the scenarios that is defined at the global scope:</span></span>
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

<span data-ttu-id="d81bc-142">Cmdlet **CsClsConfiguration**會始終顯示屬於指定範圍之設定的情況。</span><span class="sxs-lookup"><span data-stu-id="d81bc-142">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope’s configuration.</span></span> <span data-ttu-id="d81bc-143">在大多數情況下，不會顯示所有案例，而且會被截斷。</span><span class="sxs-lookup"><span data-stu-id="d81bc-143">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="d81bc-144">此處使用的命令會列出所有案例，以及使用哪些提供者、設定和標誌的部分資訊。</span><span class="sxs-lookup"><span data-stu-id="d81bc-144">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>

</div>

<div>

## <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="d81bc-145">使用 Windows PowerShell 來更新集中式記錄服務的全域範圍</span><span class="sxs-lookup"><span data-stu-id="d81bc-145">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1.  <span data-ttu-id="d81bc-146">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="d81bc-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d81bc-147">在命令列提示處輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="d81bc-147">Type the following at the command-line prompt:</span></span>
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    <span data-ttu-id="d81bc-148">例如：</span><span class="sxs-lookup"><span data-stu-id="d81bc-148">For example:</span></span>
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

<span data-ttu-id="d81bc-149">此命令會告知部署中每個電腦和池中的 CLSAgent，將描摹檔案的滾動更新大小設定為 40 mb。</span><span class="sxs-lookup"><span data-stu-id="d81bc-149">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes.</span></span> <span data-ttu-id="d81bc-150">所有網站中的電腦和池都會受到命令的影響，並將其設定的追蹤記錄滾動更新值設為 40 mb。</span><span class="sxs-lookup"><span data-stu-id="d81bc-150">Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>

</div>

<div>

## <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="d81bc-151">使用 Windows PowerShell 來更新集中式記錄服務的網站範圍</span><span class="sxs-lookup"><span data-stu-id="d81bc-151">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1.  <span data-ttu-id="d81bc-152">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="d81bc-152">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d81bc-153">在命令列提示處輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="d81bc-153">Type the following at the command-line prompt:</span></span>
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    <span data-ttu-id="d81bc-154">例如：</span><span class="sxs-lookup"><span data-stu-id="d81bc-154">For example:</span></span>
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="d81bc-155">如範例所述，記錄檔的預設位置是%TEMP%\Tracing。</span><span class="sxs-lookup"><span data-stu-id="d81bc-155">As noted in the example, the default location of the log files is %TEMP%\Tracing.</span></span> <span data-ttu-id="d81bc-156">不過，因為實際 CLSAgent 正在寫入檔案並 CSLAgent [以網路服務執行]，因此% TEMP% 變數會展開為%WINDIR%\ServiceProfiles\NetworkService\AppData\Local。</span><span class="sxs-lookup"><span data-stu-id="d81bc-156">However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span>

    
    </div>

<span data-ttu-id="d81bc-157">此命令會告知 [網站雷蒙德] 中每個電腦和池中的 CLSAgent，將 [追蹤檔案] 上的 [翻轉] 值的大小設定為 40 mb。</span><span class="sxs-lookup"><span data-stu-id="d81bc-157">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes.</span></span> <span data-ttu-id="d81bc-158">在其他網站中的電腦和池不會受到命令影響，而且會繼續使用目前已設定的追蹤記錄滾動更新值（預設為 20 mb），或在記錄會話開始時使用。</span><span class="sxs-lookup"><span data-stu-id="d81bc-158">Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>

</div>

<div>

## <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="d81bc-159">若要建立新的集中式記錄服務設定</span><span class="sxs-lookup"><span data-stu-id="d81bc-159">To create a new Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="d81bc-160">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="d81bc-160">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d81bc-161">在命令列提示處輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="d81bc-161">Type the following at the command-line prompt:</span></span>
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="d81bc-162">新-CsClsConfiguration 提供大量選用設定的存取權。</span><span class="sxs-lookup"><span data-stu-id="d81bc-162">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="d81bc-163">如需設定選項的詳細資訊， <A href="https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15)"></A>請參閱<A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">在 Lync Server 2013 中 CsClsConfiguration 及瞭解集中式記錄服務設定設定</A>。</span><span class="sxs-lookup"><span data-stu-id="d81bc-163">For details about the configuration options, see <A href="https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15)">Get-CsClsConfiguration</A> and <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">Understanding Centralized Logging Service configuration settings in Lync Server 2013</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="d81bc-164">例如，若要建立新的設定，以定義快取檔案的網路資料夾、滾動更新記錄檔的時間週期，以及記錄檔的滾動盤大小，您可以輸入：</span><span class="sxs-lookup"><span data-stu-id="d81bc-164">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

<span data-ttu-id="d81bc-165">您應該仔細規劃新配置的建立，以及如何定義集中式記錄服務的新屬性。</span><span class="sxs-lookup"><span data-stu-id="d81bc-165">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="d81bc-166">您應該小心地進行變更，並確認您已瞭解對您能否正確記錄問題案例的影響。</span><span class="sxs-lookup"><span data-stu-id="d81bc-166">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="d81bc-167">您應該對設定進行變更，以增強您記錄管理的能力，讓您能夠在出現問題時進行問題的疑難排解。</span><span class="sxs-lookup"><span data-stu-id="d81bc-167">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>

</div>

<div>

## <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="d81bc-168">移除現有的集中式記錄服務設定</span><span class="sxs-lookup"><span data-stu-id="d81bc-168">To remove an existing Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="d81bc-169">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="d81bc-169">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d81bc-170">在命令列提示處輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="d81bc-170">Type the following at the command-line prompt:</span></span>
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    <span data-ttu-id="d81bc-171">例如，若要移除您建立的集中式記錄服務設定以增加記錄檔滾動時間，請增加滾動更新記錄檔大小，並將記錄檔案快取位置設定為網路共用，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d81bc-171">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="d81bc-172">這是在「建立新的集中式記錄服務設定」過程中建立的新設定。</span><span class="sxs-lookup"><span data-stu-id="d81bc-172">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span>

    
    </div>

<span data-ttu-id="d81bc-173">如果您選擇移除網站層級的設定，網站將會使用全域設定。</span><span class="sxs-lookup"><span data-stu-id="d81bc-173">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d81bc-174">請參閱</span><span class="sxs-lookup"><span data-stu-id="d81bc-174">See Also</span></span>


[<span data-ttu-id="d81bc-175">Lync Server 2013 中的集中式記錄服務概覽</span><span class="sxs-lookup"><span data-stu-id="d81bc-175">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[<span data-ttu-id="d81bc-176">在 Lync Server 2013 中管理集中式記錄服務設定設定</span><span class="sxs-lookup"><span data-stu-id="d81bc-176">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
<span data-ttu-id="d81bc-177">[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d81bc-177">[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))</span></span>  
<span data-ttu-id="d81bc-178">[CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d81bc-178">[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))</span></span>  
<span data-ttu-id="d81bc-179">[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d81bc-179">[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))</span></span>  
<span data-ttu-id="d81bc-180">[移除-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d81bc-180">[Remove-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

