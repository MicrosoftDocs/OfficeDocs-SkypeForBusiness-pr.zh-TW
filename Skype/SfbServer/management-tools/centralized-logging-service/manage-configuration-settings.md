---
title: 管理商務用 Skype 2015 中集中式記錄服務組態設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: 摘要：瞭解如何在商務用 Skype Server 2015 中針對集中式記錄服務，進行檢索、更新及建立配置設定。
ms.openlocfilehash: 95aa05cfcd31acda8e78927d674f3a19dff7ef56
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816582"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="130e7-103">管理商務用 Skype 2015 中集中式記錄服務組態設定</span><span class="sxs-lookup"><span data-stu-id="130e7-103">Manage Centralized Logging Service configuration settings in Skype for Business Server 2015</span></span>

<span data-ttu-id="130e7-104">**摘要：** 瞭解如何在商務用 Skype Server 2015 中針對集中式記錄服務，進行檢索、更新及建立配置設定。</span><span class="sxs-lookup"><span data-stu-id="130e7-104">**Summary:** Learn how to retrieve, update, and create configuration settings for the Centralized Logging Service in Skype for Business Server 2015.</span></span>

<span data-ttu-id="130e7-105">集中式記錄服務由集中式記錄服務控制器（CLSController）所建立和使用的設定和參數加以控制和設定，以便將命令傳送到個別電腦的集中式記錄服務代理程式（CLSAgent).</span><span class="sxs-lookup"><span data-stu-id="130e7-105">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer's Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="130e7-106">Agent 會處理傳送給它的命令，（在 [開始] 命令中）會使用案例、提供者、追蹤持續時間及旗標的設定來開始根據所提供的配置資訊來收集追蹤記錄。</span><span class="sxs-lookup"><span data-stu-id="130e7-106">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="130e7-107">並非所有針對集中式記錄服務列出的 Windows PowerShell Cmdlet 都適用于商務用 Skype Server 2015 內部部署。</span><span class="sxs-lookup"><span data-stu-id="130e7-107">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Skype for Business Server 2015 on-premises deployments.</span></span> <span data-ttu-id="130e7-108">雖然這些程式可能看起來正常運作，但下列 Cmdlet 並非設計為與商務用 Skype Server 2015 內部部署部署搭配使用：</span><span class="sxs-lookup"><span data-stu-id="130e7-108">Although they may appear to work, the following cmdlets are not designed to function with Skype for Business Server 2015 on-premises deployments:</span></span>

-  <span data-ttu-id="130e7-109">**CsClsRegion Cmdlet：** [CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) 、[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps)、 [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)及[Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="130e7-109">**CsClsRegion cmdlets:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps), and [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).</span></span>
-  <span data-ttu-id="130e7-110">**CsClsSearchTerm Cmdlet：** [CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps)和[Set CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="130e7-110">**CsClsSearchTerm cmdlets:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) and [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span></span>
-  <span data-ttu-id="130e7-111">**CsClsSecurityGroup Cmdlet：** [CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps)、 [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps)、 [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)及[Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="130e7-111">**CsClsSecurityGroup cmdlets:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps),  [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps), and [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).</span></span>

<span data-ttu-id="130e7-112">在這些 Cmdlet 中定義的設定將不會受到影響或導致任何不利的行為，但它們的設計目的是與 Microsoft Office 365 搭配使用，且不會在內部部署部署中產生預期的結果。</span><span class="sxs-lookup"><span data-stu-id="130e7-112">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft Office 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="130e7-113">這不表示這些 Cmdlet 在內部部署部署中無法使用，但其使用方式是本檔中未涵蓋的更高級主題。</span><span class="sxs-lookup"><span data-stu-id="130e7-113">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>

<span data-ttu-id="130e7-114">集中式記錄服務可以在包含單一電腦或電腦池的範圍內執行，在網站範圍（也就是已定義的網站（例如在您的部署中包含電腦和池集合的網站雷蒙德），或在全域範圍中（也就是在您部署中的所有電腦和池）。</span><span class="sxs-lookup"><span data-stu-id="130e7-114">The Centralized Logging Service can be run at a scope that includes a single computer or a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>

<span data-ttu-id="130e7-115">若要使用商務用 Skype Server Management Shell 來設定集中式記錄服務範圍，您必須是 CsAdministrator 或 CsServerAdministrator 角色式存取控制（RBAC）安全性群組的成員，或是您的自訂 RBAC 角色。包含這兩個群組中的任一個。</span><span class="sxs-lookup"><span data-stu-id="130e7-115">To configure the Centralized Logging Service scope by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="130e7-116">若要傳回已指派這個 Cmdlet 的所有 RBAC 角色清單（包括您自行建立的任何自訂 RBAC 角色），請從商務用 Skype Server 管理命令介面或 Windows PowerShell 提示中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="130e7-116">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

<span data-ttu-id="130e7-117">例如：</span><span class="sxs-lookup"><span data-stu-id="130e7-117">For example:</span></span>

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> <span data-ttu-id="130e7-118">您可以在 Windows PowerShell 或 CLSController 中執行的命令列命令之間有一些基本差異。</span><span class="sxs-lookup"><span data-stu-id="130e7-118">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="130e7-119">Windows PowerShell 提供豐富的方法來設定及定義案例，並以一種有意義的方式在疑難排解案例中重複使用這些案例。</span><span class="sxs-lookup"><span data-stu-id="130e7-119">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="130e7-120">雖然 CLSController 確實提供快速且高效的方式來發出命令並取得結果，但 CLSController 的命令會受到您在命令列中提供的有限命令的限制。</span><span class="sxs-lookup"><span data-stu-id="130e7-120">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="130e7-121">與 Windows PowerShell Cmdlet 不同，CLSController 無法定義新案例、管理網站或全域階層的範圍，以及無法動態設定之有限命令集的許多其他限制。</span><span class="sxs-lookup"><span data-stu-id="130e7-121">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="130e7-122">雖然 CLSController 提供快速執行的方法，但 Windows PowerShell 提供了一種方式，可讓集中式記錄服務功能延伸到可能的 CLSController 以外。</span><span class="sxs-lookup"><span data-stu-id="130e7-122">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span>

<span data-ttu-id="130e7-123">您可以在[搜尋 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps)（[顯示-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps)、 [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps)、 [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)、 [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps)和[Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps)命令）中，使用-電腦參數定義單一電腦範圍。</span><span class="sxs-lookup"><span data-stu-id="130e7-123">A single computer scope can be defined during the execution of a [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) and [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) command using the -Computers parameter.</span></span> <span data-ttu-id="130e7-124">-電腦參數接受以逗號分隔的目的電腦完整功能變數名稱（Fqdn）清單。</span><span class="sxs-lookup"><span data-stu-id="130e7-124">The -Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>

> [!TIP]
> <span data-ttu-id="130e7-125">您也可以定義池以及要執行記錄命令的逗號分隔的 [池] 清單。</span><span class="sxs-lookup"><span data-stu-id="130e7-125">You can also define -Pools and a comma separated list of pools that you want to run the logging commands on.</span></span>

<span data-ttu-id="130e7-126">[網站] 和 [全域範圍] 是在**新**的、**集合**和**移除**集中式記錄服務 Cmdlet 中定義。</span><span class="sxs-lookup"><span data-stu-id="130e7-126">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="130e7-127">下列範例示範如何設定網站和全域範圍。</span><span class="sxs-lookup"><span data-stu-id="130e7-127">The following examples demonstrate how to set a site and a global scope.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="130e7-128">所顯示的命令可能包含其他章節所涵蓋的參數和概念。</span><span class="sxs-lookup"><span data-stu-id="130e7-128">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="130e7-129">這個範例命令是用來示範如何使用身分**識別**參數來定義作用域，而其他參數則包括完整性並指定範圍。</span><span class="sxs-lookup"><span data-stu-id="130e7-129">The example commands are intended to demonstrate the use of the **-Identity** parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="130e7-130">如需**設定 CsClsConfiguration** Cmdlet 的詳細資料，請參閱作業檔中的[CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="130e7-130">For details about the **Set-CsClsConfiguration** cmdlets, see [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) in the Operations documentation.</span></span>

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="130e7-131">若要取得目前的集中式記錄服務設定</span><span class="sxs-lookup"><span data-stu-id="130e7-131">To retrieve the current Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="130e7-132">啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="130e7-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="130e7-133">在命令列提示處輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="130e7-133">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration
   ```

<span data-ttu-id="130e7-134">使用**新的 CsClsConfiguration**和**CsClsConfiguration** Cmdlet 來建立新的設定或更新現有的配置。當您執行**CsClsConfiguration**時，它會顯示類似下列螢幕擷取畫面的資訊，其中的部署目前具有預設的全域設定，但未定義網站配置：</span><span class="sxs-lookup"><span data-stu-id="130e7-134">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>

![Get-CsClsConfiguration 輸出範例。](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="130e7-136">從電腦當地商店中取得目前的集中式記錄服務設定</span><span class="sxs-lookup"><span data-stu-id="130e7-136">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1. <span data-ttu-id="130e7-137">啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="130e7-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="130e7-138">在命令列提示處輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="130e7-138">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

<span data-ttu-id="130e7-139">當您使用**CsClsConfiguration**未指定任何參數的第一個範例時，該命令會參照資料的中央管理儲存體。</span><span class="sxs-lookup"><span data-stu-id="130e7-139">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="130e7-140">如果您指定參數 LocalStore，命令會參照電腦 LocalStore，而不是中央管理儲存體。</span><span class="sxs-lookup"><span data-stu-id="130e7-140">If you specify the parameter -LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="130e7-141">若要檢索目前定義的案例清單</span><span class="sxs-lookup"><span data-stu-id="130e7-141">To retrieve a listing of scenarios currently defined</span></span>

1. <span data-ttu-id="130e7-142">啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="130e7-142">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="130e7-143">在命令列提示處輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="130e7-143">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    <span data-ttu-id="130e7-144">例如，若要檢索在全域範圍內定義的案例：</span><span class="sxs-lookup"><span data-stu-id="130e7-144">For example, to retrieve the scenarios that is defined at the global scope:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

<span data-ttu-id="130e7-145">Cmdlet **CsClsConfiguration**會始終顯示屬於指定範圍之設定的情況。</span><span class="sxs-lookup"><span data-stu-id="130e7-145">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope's configuration.</span></span> <span data-ttu-id="130e7-146">在大多數情況下，不會顯示所有案例，而且會被截斷。</span><span class="sxs-lookup"><span data-stu-id="130e7-146">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="130e7-147">此處使用的命令會列出所有案例，以及使用哪些提供者、設定和標誌的部分資訊。</span><span class="sxs-lookup"><span data-stu-id="130e7-147">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="130e7-148">使用 Windows PowerShell 來更新集中式記錄服務的全域範圍</span><span class="sxs-lookup"><span data-stu-id="130e7-148">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="130e7-149">啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="130e7-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="130e7-150">在命令列提示處輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="130e7-150">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="130e7-151">例如：</span><span class="sxs-lookup"><span data-stu-id="130e7-151">For example:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

<span data-ttu-id="130e7-152">此命令會告知部署中每個電腦和池中的 CLSAgent，將描摹檔案的滾動更新大小設定為 40 mb。</span><span class="sxs-lookup"><span data-stu-id="130e7-152">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes.</span></span> <span data-ttu-id="130e7-153">所有網站中的電腦和池都會受到命令的影響，並將其設定的追蹤記錄滾動更新值設為 40 mb。</span><span class="sxs-lookup"><span data-stu-id="130e7-153">Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="130e7-154">使用 Windows PowerShell 來更新集中式記錄服務的網站範圍</span><span class="sxs-lookup"><span data-stu-id="130e7-154">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="130e7-155">啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="130e7-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="130e7-156">在命令列提示處輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="130e7-156">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="130e7-157">例如：</span><span class="sxs-lookup"><span data-stu-id="130e7-157">For example:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> <span data-ttu-id="130e7-158">如範例所述，記錄檔的預設位置是%TEMP%\Tracing。</span><span class="sxs-lookup"><span data-stu-id="130e7-158">As noted in the example, the default location of the log files is %TEMP%\Tracing.</span></span> <span data-ttu-id="130e7-159">不過，因為實際 CLSAgent 正在寫入檔案並 CSLAgent [以網路服務執行]，因此% TEMP% 變數會展開為%WINDIR%\ServiceProfiles\NetworkService\AppData\Local。</span><span class="sxs-lookup"><span data-stu-id="130e7-159">However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span>

<span data-ttu-id="130e7-160">此命令會告知 [網站雷蒙德] 中每個電腦和池中的 CLSAgent，將 [追蹤檔案] 上的 [翻轉] 值的大小設定為 40 mb。</span><span class="sxs-lookup"><span data-stu-id="130e7-160">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes.</span></span> <span data-ttu-id="130e7-161">在其他網站中的電腦和池不會受到命令影響，而且會繼續使用目前已設定的追蹤記錄滾動更新值（預設為 20 mb），或在記錄會話開始時使用。</span><span class="sxs-lookup"><span data-stu-id="130e7-161">Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>
### <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="130e7-162">若要建立新的集中式記錄服務設定</span><span class="sxs-lookup"><span data-stu-id="130e7-162">To create a new Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="130e7-163">啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="130e7-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="130e7-164">在命令列提示處輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="130e7-164">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > <span data-ttu-id="130e7-165">新-CsClsConfiguration 提供大量選用設定的存取權。</span><span class="sxs-lookup"><span data-stu-id="130e7-165">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="130e7-166">如需設定選項的詳細資訊，請參閱[CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)及[瞭解集中式記錄服務設定設定](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx)。</span><span class="sxs-lookup"><span data-stu-id="130e7-166">For details about the configuration options, see [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) and [Understanding Centralized Logging Service Configuration Settings](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).</span></span>

<span data-ttu-id="130e7-167">例如，若要建立新的設定，以定義快取檔案的網路資料夾、滾動更新記錄檔的時間週期，以及記錄檔的滾動盤大小，您可以輸入：</span><span class="sxs-lookup"><span data-stu-id="130e7-167">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

<span data-ttu-id="130e7-168">您應該仔細規劃新配置的建立，以及如何定義集中式記錄服務的新屬性。</span><span class="sxs-lookup"><span data-stu-id="130e7-168">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="130e7-169">您應該小心地進行變更，並確認您已瞭解對您能否正確記錄問題案例的影響。</span><span class="sxs-lookup"><span data-stu-id="130e7-169">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="130e7-170">您應該對設定進行變更，以增強您記錄管理的能力，讓您能夠在出現問題時進行問題的疑難排解。</span><span class="sxs-lookup"><span data-stu-id="130e7-170">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="130e7-171">移除現有的集中式記錄服務設定</span><span class="sxs-lookup"><span data-stu-id="130e7-171">To remove an existing Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="130e7-172">啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="130e7-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="130e7-173">在命令列提示處輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="130e7-173">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

<span data-ttu-id="130e7-174">例如，若要移除您建立的集中式記錄服務設定以增加記錄檔滾動時間，請增加滾動更新記錄檔大小，並將記錄檔案快取位置設定為網路共用，如下所示：</span><span class="sxs-lookup"><span data-stu-id="130e7-174">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> <span data-ttu-id="130e7-175">這是在「建立新的集中式記錄服務設定」過程中建立的新設定。</span><span class="sxs-lookup"><span data-stu-id="130e7-175">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span>

<span data-ttu-id="130e7-176">如果您選擇移除網站層級的設定，網站將會使用全域設定。</span><span class="sxs-lookup"><span data-stu-id="130e7-176">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>
## <a name="see-also"></a><span data-ttu-id="130e7-177">另請參閱</span><span class="sxs-lookup"><span data-stu-id="130e7-177">See also</span></span>

[<span data-ttu-id="130e7-178">設定商務用 Skype 2015 中集中式記錄服務的提供者</span><span class="sxs-lookup"><span data-stu-id="130e7-178">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-providers.md)

[<span data-ttu-id="130e7-179">設定商務用 Skype 2015 中的集中式記錄服務的案例</span><span class="sxs-lookup"><span data-stu-id="130e7-179">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-scenarios.md)

[<span data-ttu-id="130e7-180">商務用 Skype 2015 中的集中式記錄服務</span><span class="sxs-lookup"><span data-stu-id="130e7-180">Centralized Logging Service in Skype for Business 2015</span></span>](centralized-logging-service.md)

[<span data-ttu-id="130e7-181">Set-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="130e7-181">Set-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="130e7-182">CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="130e7-182">Get-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="130e7-183">New-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="130e7-183">New-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="130e7-184">移除-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="130e7-184">Remove-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
