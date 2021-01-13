---
title: 在商務用 Skype Server 2015 中管理集中式記錄服務設定設定
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 摘要：瞭解如何在商務用 Skype Server 2015 中針對集中式記錄服務，來取得、更新及建立設定。
ms.openlocfilehash: dd292465d65116dc1f497a733ca8e010e57b9137
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835153"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="b7e5d-103">在商務用 Skype Server 2015 中管理集中式記錄服務設定設定</span><span class="sxs-lookup"><span data-stu-id="b7e5d-103">Manage Centralized Logging Service configuration settings in Skype for Business Server 2015</span></span>

<span data-ttu-id="b7e5d-104">**摘要：** 瞭解如何在商務用 Skype Server 2015 中針對集中式記錄服務，取得、更新及建立設定。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-104">**Summary:** Learn how to retrieve, update, and create configuration settings for the Centralized Logging Service in Skype for Business Server 2015.</span></span>

<span data-ttu-id="b7e5d-105">集中式記錄服務是由集中式記錄服務控制器 (CLSController) 所建立及使用的設定和參數來控制及設定，將命令傳送至個別電腦的集中式記錄服務代理 (CLSAgent) 。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-105">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer's Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="b7e5d-106">代理程式會處理傳送給它的命令， (並在開始命令) 使用案例的設定、提供者、追蹤持續時間及旗標開始根據所提供的設定資訊來收集追蹤記錄檔。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-106">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="b7e5d-107">並非針對集中式記錄服務所列出的所有 Windows PowerShell Cmdlet，都適用于商務用 Skype Server 2015 內部部署。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-107">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Skype for Business Server 2015 on-premises deployments.</span></span> <span data-ttu-id="b7e5d-108">雖然似乎可以運作，但下列 Cmdlet 並非設計為在商務用 Skype Server 2015 內部部署環境中運作：</span><span class="sxs-lookup"><span data-stu-id="b7e5d-108">Although they may appear to work, the following cmdlets are not designed to function with Skype for Business Server 2015 on-premises deployments:</span></span>

-  <span data-ttu-id="b7e5d-109">**CsClsRegion Cmdlet：** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) 、[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps)、 [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)及 [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-109">**CsClsRegion cmdlets:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps), and [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).</span></span>
-  <span data-ttu-id="b7e5d-110">**CsClsSearchTerm Cmdlet：** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) 和 [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-110">**CsClsSearchTerm cmdlets:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) and [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span></span>
-  <span data-ttu-id="b7e5d-111">**CsClsSecurityGroup Cmdlet：** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps)、 [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps)、  [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)及 [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-111">**CsClsSecurityGroup cmdlets:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps),  [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps), and [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).</span></span>

<span data-ttu-id="b7e5d-112">在這些 Cmdlet 中定義的設定將不會妨礙或導致任何不良行為，但其設計目的是用於 Microsoft 365 或 Office 365，而且不會在內部部署部署中產生預期的結果。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-112">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft 365 or Office 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="b7e5d-113">這並不是說，在內部部署中不會使用這些 Cmdlet，但是其使用是本檔中未涵蓋的更高級主題。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-113">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>

<span data-ttu-id="b7e5d-114">集中式記錄服務可以在包含單一電腦或電腦集區的範圍中執行，也就是在網站範圍 (，也就是定義的網站（例如，包含部署) 中的電腦及集區集合），或是全域範圍 (也就是部署) 中的所有電腦及集區。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-114">The Centralized Logging Service can be run at a scope that includes a single computer or a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>

<span data-ttu-id="b7e5d-115">若要使用商務用 Skype Server 管理命令介面來設定集中式記錄服務範圍，您必須是 CsAdministrator 或 CsServerAdministrator 角色型存取控制 (RBAC) 安全性群組的成員，或是包含這兩個群組之任一個自訂 RBAC 角色的成員。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-115">To configure the Centralized Logging Service scope by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="b7e5d-116">若要傳回所有獲指派此 Cmdlet 的 RBAC 角色清單 (包含您自行建立的自訂 RBAC 角色) ，請從商務用 Skype Server 管理命令介面或 Windows PowerShell 提示中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="b7e5d-116">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

<span data-ttu-id="b7e5d-117">例如：</span><span class="sxs-lookup"><span data-stu-id="b7e5d-117">For example:</span></span>

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> <span data-ttu-id="b7e5d-118">您可以在 Windows PowerShell 或 CLSController 中執行的命令列命令之間有基本差異。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-118">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="b7e5d-119">Windows PowerShell 提供豐富的方法來設定及定義案例，並以有意義的方式針對疑難排解案例重複使用這些案例。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-119">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="b7e5d-120">雖然 CLSController 提供快速且有效的方式來發出命令並取得結果，但 CLSController 的命令設定會受限於您在命令列中使用的有限命令。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-120">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="b7e5d-121">與 Windows PowerShell Cmdlet 不同的是，CLSController 無法定義新案例、管理網站或全域層級的範圍，以及無法動態設定之有限命令集的其他許多限制。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-121">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="b7e5d-122">雖然 CLSController 提供快速執行的方法，但 Windows PowerShell 提供一種方法來擴充集中式記錄服務功能，以超越 CLSController 的可能。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-122">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span>

<span data-ttu-id="b7e5d-123">您可以在使用-computer 參數的 [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps)、 [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps)、 [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps)、 [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)、 [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) 和 [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) 命令的執行期間定義單一電腦範圍。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-123">A single computer scope can be defined during the execution of a [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) and [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) command using the -Computers parameter.</span></span> <span data-ttu-id="b7e5d-124">-Computer 參數會接受以逗號分隔的完整功能變數名稱清單， (Fqdn) 目的電腦。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-124">The -Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>

> [!TIP]
> <span data-ttu-id="b7e5d-125">您也可以定義集區和以逗號分隔的集區清單，您想要在其上執行記錄指令。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-125">You can also define -Pools and a comma separated list of pools that you want to run the logging commands on.</span></span>

<span data-ttu-id="b7e5d-126">網站和全域範圍是在 **新的**、 **集合** 及 **移除** 集中式記錄服務 Cmdlet 中定義。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-126">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="b7e5d-127">下列範例會示範如何設定網站和全域範圍。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-127">The following examples demonstrate how to set a site and a global scope.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b7e5d-128">所顯示的命令可能包含其他章節中所涵蓋的參數和概念。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-128">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="b7e5d-129">範例命令的目的是為了示範如何使用 **-Identity** 參數定義範圍，並包含其他參數的完整性，並指定範圍。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-129">The example commands are intended to demonstrate the use of the **-Identity** parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="b7e5d-130">如需 **Set-CsClsConfiguration** Cmdlet 的詳細資訊，請參閱 Operations 檔中的 [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-130">For details about the **Set-CsClsConfiguration** cmdlets, see [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) in the Operations documentation.</span></span>

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="b7e5d-131">若要取得目前的集中式記錄服務設定</span><span class="sxs-lookup"><span data-stu-id="b7e5d-131">To retrieve the current Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="b7e5d-132">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="b7e5d-133">在命令列提示字元處，輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="b7e5d-133">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration
   ```

<span data-ttu-id="b7e5d-134">使用 **New-CsClsConfiguration** 和 **Set-CsClsConfiguration** Cmdlet 來建立新的設定或更新現有的設定。當您執行 **Get-CsClsConfiguration** 時，它會顯示與下列螢幕擷取畫面類似的資訊，其中的部署目前具有預設全域設定，但未定義網站配置：</span><span class="sxs-lookup"><span data-stu-id="b7e5d-134">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>

![Get-CsClsConfiguration 的輸出範例。](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="b7e5d-136">從電腦本地存放區中取得目前的集中式記錄服務設定</span><span class="sxs-lookup"><span data-stu-id="b7e5d-136">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1. <span data-ttu-id="b7e5d-137">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="b7e5d-138">在命令列提示字元處，輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="b7e5d-138">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

<span data-ttu-id="b7e5d-139">當您使用第一個範例，其中 **Get-CsClsConfiguration** 未指定任何參數時，此命令會參考資料的中央管理存放區。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-139">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="b7e5d-140">如果您指定參數 LocalStore，此命令會參照電腦 LocalStore 而非中央管理存放區。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-140">If you specify the parameter -LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="b7e5d-141">若要取得目前定義的案例清單</span><span class="sxs-lookup"><span data-stu-id="b7e5d-141">To retrieve a listing of scenarios currently defined</span></span>

1. <span data-ttu-id="b7e5d-142">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-142">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="b7e5d-143">在命令列提示字元處，輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="b7e5d-143">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    <span data-ttu-id="b7e5d-144">例如，若要檢索在全域範圍內定義的案例：</span><span class="sxs-lookup"><span data-stu-id="b7e5d-144">For example, to retrieve the scenarios that is defined at the global scope:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

<span data-ttu-id="b7e5d-145">Cmdlet **Get-CsClsConfiguration** 一定會顯示屬於特定範圍設定之部分的案例。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-145">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope's configuration.</span></span> <span data-ttu-id="b7e5d-146">在大多數情況下，不會顯示所有案例，而且會被截斷。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-146">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="b7e5d-147">此處所用的命令會列出使用的提供者、設定及旗標的所有案例及部分資訊。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-147">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="b7e5d-148">使用 Windows PowerShell 更新集中式記錄服務的全域範圍</span><span class="sxs-lookup"><span data-stu-id="b7e5d-148">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="b7e5d-149">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="b7e5d-150">在命令列提示字元處，輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="b7e5d-150">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="b7e5d-151">例如：</span><span class="sxs-lookup"><span data-stu-id="b7e5d-151">For example:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

<span data-ttu-id="b7e5d-152">命令會告訴部署中每台電腦及集區上的 CLSAgent，將追蹤檔案的變換值大小設定為 40 mb。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-152">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes.</span></span> <span data-ttu-id="b7e5d-153">所有網站中的電腦與集區都會受到命令的影響，並會將其設定的追蹤記錄檔翻轉值設定為 40 mb。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-153">Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="b7e5d-154">使用 Windows PowerShell 更新集中式記錄服務的網站範圍</span><span class="sxs-lookup"><span data-stu-id="b7e5d-154">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="b7e5d-155">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="b7e5d-156">在命令列提示字元處，輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="b7e5d-156">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="b7e5d-157">例如：</span><span class="sxs-lookup"><span data-stu-id="b7e5d-157">For example:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> <span data-ttu-id="b7e5d-158">如範例中所述，記錄檔的預設位置是%TEMP%\Tracing。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-158">As noted in the example, the default location of the log files is %TEMP%\Tracing.</span></span> <span data-ttu-id="b7e5d-159">不過，由於實際 CLSAgent 是寫入檔案，而 CSLAgent 以網路服務方式執行，所以%TEMP% 變數會擴充為%WINDIR%\ServiceProfiles\NetworkService\AppData\Local。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-159">However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span>

<span data-ttu-id="b7e5d-160">命令會告訴 site Redmond 中每一部電腦及集區上的 CLSAgent，將追蹤檔案的變換值大小設定為 40 mb。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-160">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes.</span></span> <span data-ttu-id="b7e5d-161">其他網站中的電腦及集區不會受到命令的影響，而且會繼續使用目前設定的追蹤記錄檔滾動更新值，此值是由預設 (20 mb) 或開始記錄會話期間所定義。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-161">Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>
### <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="b7e5d-162">若要建立新的集中式記錄服務設定</span><span class="sxs-lookup"><span data-stu-id="b7e5d-162">To create a new Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="b7e5d-163">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="b7e5d-164">在命令列提示字元處，輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="b7e5d-164">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > <span data-ttu-id="b7e5d-165">New-CsClsConfiguration 提供大量選用設定設定的存取權。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-165">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="b7e5d-166">如需設定選項的詳細資訊，請參閱 [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) 和 [瞭解集中式記錄服務設定設定](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-166">For details about the configuration options, see [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) and [Understanding Centralized Logging Service Configuration Settings](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).</span></span>

<span data-ttu-id="b7e5d-167">例如，若要建立新的設定以定義快取檔案的網路資料夾、滾動表檔的記錄檔和翻轉大小的時間週期，您可以輸入：</span><span class="sxs-lookup"><span data-stu-id="b7e5d-167">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

<span data-ttu-id="b7e5d-168">您應該仔細規劃新設定的建立，以及如何定義集中式記錄服務的新屬性。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-168">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="b7e5d-169">您應謹慎進行變更，並確定您瞭解能夠正確記錄問題案例的影響。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-169">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="b7e5d-170">您應該對設定進行變更，以增強您記錄管理大小的能力，以及可在發生問題時進行問題解決的翻轉期間。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-170">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="b7e5d-171">移除現有的集中式記錄服務設定</span><span class="sxs-lookup"><span data-stu-id="b7e5d-171">To remove an existing Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="b7e5d-172">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="b7e5d-173">在命令列提示字元處，輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="b7e5d-173">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

<span data-ttu-id="b7e5d-174">例如，若要移除您已建立的集中式記錄服務設定，以增加記錄檔翻轉時間、增加翻轉記錄檔大小，並將記錄檔快取位置設為網路共用，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b7e5d-174">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> <span data-ttu-id="b7e5d-175">這是在「建立新的集中式記錄服務設定」過程中建立的新設定。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-175">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span>

<span data-ttu-id="b7e5d-176">如果您選擇移除網站層級設定，則網站會使用通用設定。</span><span class="sxs-lookup"><span data-stu-id="b7e5d-176">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>
## <a name="see-also"></a><span data-ttu-id="b7e5d-177">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b7e5d-177">See also</span></span>

[<span data-ttu-id="b7e5d-178">在商務用 Skype Server 2015 中設定集中式記錄服務的提供者</span><span class="sxs-lookup"><span data-stu-id="b7e5d-178">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-providers.md)

[<span data-ttu-id="b7e5d-179">在商務用 Skype Server 2015 中設定集中式記錄服務的案例</span><span class="sxs-lookup"><span data-stu-id="b7e5d-179">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-scenarios.md)

[<span data-ttu-id="b7e5d-180">商務用 Skype 2015 中的集中式記錄服務</span><span class="sxs-lookup"><span data-stu-id="b7e5d-180">Centralized Logging Service in Skype for Business 2015</span></span>](centralized-logging-service.md)

[<span data-ttu-id="b7e5d-181">Set-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="b7e5d-181">Set-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="b7e5d-182">Get-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="b7e5d-182">Get-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="b7e5d-183">New-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="b7e5d-183">New-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="b7e5d-184">Remove-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="b7e5d-184">Remove-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
