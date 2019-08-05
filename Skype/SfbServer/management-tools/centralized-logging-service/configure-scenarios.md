---
title: 設定商務用 Skype 2015 中的集中式記錄服務的案例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: '摘要: 瞭解如何在商務用 Skype Server 2015 中建立、修改及移除集中式記錄服務的案例。'
ms.openlocfilehash: 89aa0c37dfb13f7614067b64e37ee9c9fb376331
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186817"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="63670-103">設定商務用 Skype 2015 中的集中式記錄服務的案例</span><span class="sxs-lookup"><span data-stu-id="63670-103">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="63670-104">**摘要:** 瞭解如何在商務用 Skype Server 2015 中建立、修改及移除集中式記錄服務的案例。</span><span class="sxs-lookup"><span data-stu-id="63670-104">**Summary:** Learn how to create, modify, and remove scenarios for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="63670-105">案例定義範圍 (即全域、網站、池或電腦), 以及要在集中式記錄服務中使用的提供者。</span><span class="sxs-lookup"><span data-stu-id="63670-105">Scenarios define the scope (that is, global, site, pool, or computer) and what providers to use in the Centralized Logging Service.</span></span> <span data-ttu-id="63670-106">使用案例, 您可以啟用或停用提供者的追蹤功能 (例如, S4、SIPStack、IM 和目前狀態)。</span><span class="sxs-lookup"><span data-stu-id="63670-106">By using scenarios, you enable or disable tracing on providers (for example, S4, SIPStack, IM, and Presence).</span></span> <span data-ttu-id="63670-107">透過設定案例, 您可以將特定的邏輯集合的所有提供者分組, 以解決特定問題的情況。</span><span class="sxs-lookup"><span data-stu-id="63670-107">By configuring a scenario, you can group all of the providers for a given logical collection that address a specific problem condition.</span></span> <span data-ttu-id="63670-108">如果您發現案例需要修改, 以符合您的疑難排解和記錄需求, 商務用 Skype Server 2015 調試工具提供了名為 ClsScenarioEdit 的 Windows PowerShell 模組, 其中包含 namedEdit-CsClsScenario 的函數。</span><span class="sxs-lookup"><span data-stu-id="63670-108">If you find that a scenario needs to be modified to meet your troubleshooting and logging needs, the Skype for Business Server 2015 Debug Tools provides you a Windows PowerShell module named ClsScenarioEdit.psm1 that contains a function namedEdit-CsClsScenario.</span></span> <span data-ttu-id="63670-109">模組的用途是編輯命名案例的屬性。</span><span class="sxs-lookup"><span data-stu-id="63670-109">The purpose of the module is to edit the properties of the named scenario.</span></span> <span data-ttu-id="63670-110">本主題提供此模組運作方式的範例。</span><span class="sxs-lookup"><span data-stu-id="63670-110">Examples of how this module works are provided in this topic.</span></span> <span data-ttu-id="63670-111">繼續進行之前, 請先下載商務用 Skype Server 2015[調試工具](https://go.microsoft.com/fwlink/p/?LinkId=285257)。</span><span class="sxs-lookup"><span data-stu-id="63670-111">Download the Skype for Business Server 2015 [Debugging Tools](https://go.microsoft.com/fwlink/p/?LinkId=285257) before going any further.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="63670-112">針對任何指定的範圍 (網站、全域、池或電腦), 您最多可以在任何指定時間執行兩種案例。</span><span class="sxs-lookup"><span data-stu-id="63670-112">For any given scope—site, global, pool or computer—you can run a maximum of two scenarios at any given time.</span></span> <span data-ttu-id="63670-113">若要判斷目前正在執行哪些案例, 請使用 Windows PowerShell 並[CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="63670-113">To determine which scenarios are currently running, use Windows PowerShell and [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span></span> <span data-ttu-id="63670-114">透過使用 Windows PowerShell 和[設定 CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps), 您可以動態變更正在執行的案例。</span><span class="sxs-lookup"><span data-stu-id="63670-114">By using Windows PowerShell and [Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps), you can dynamically change which scenarios are running.</span></span> <span data-ttu-id="63670-115">您可以修改記錄會話期間執行的案例, 以調整或精煉您要收集的資料, 以及從哪些提供者處。</span><span class="sxs-lookup"><span data-stu-id="63670-115">You can modify which scenarios are running during a logging session to adjust or refine the data you are collecting and from which providers.</span></span> 
  
<span data-ttu-id="63670-116">若要使用商務用 Skype Server Management Shell 來執行集中式記錄服務功能, 您必須是 CsAdministrator 或 CsServerAdministrator 角色的存取控制 (RBAC) 安全性群組的成員, 或是一個自訂的 RBAC 角色,包含這兩個群組中的任一個。</span><span class="sxs-lookup"><span data-stu-id="63670-116">To run the Centralized Logging Service functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="63670-117">若要傳回這個 Cmdlet 已獲指派的所有 RBAC 角色清單, 包括您自行建立的任何自訂 RBAC 角色, 請從商務用 Skype Server 管理命令介面或 Windows PowerShell 提示中執行下列命令:</span><span class="sxs-lookup"><span data-stu-id="63670-117">To return a list of all the RBAC roles this cmdlet has been assigned to, including any custom RBAC roles you have created yourself, run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="63670-118">例如：</span><span class="sxs-lookup"><span data-stu-id="63670-118">For example:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="63670-119">本主題的其餘部分將重點放在如何定義案例、修改案例、檢索正在執行的案例、移除案例, 以及指定案例中所包含的專案, 以優化您的疑難排解。</span><span class="sxs-lookup"><span data-stu-id="63670-119">The remainder of this topic focuses on how to define a scenario, modify a scenario, retrieve what scenarios are running, remove a scenario, and specify what a scenario contains to optimize your troubleshooting.</span></span> <span data-ttu-id="63670-120">您可以使用商務用 Skype Server Management Shell 來頒發 Windows PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="63670-120">You can use the Skype for Business Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="63670-121">當您使用 Windows PowerShell 時, 您可以定義在記錄會話中使用的新案例。</span><span class="sxs-lookup"><span data-stu-id="63670-121">When you use Windows PowerShell, you can define new scenarios for use in your logging sessions.</span></span>
  
<span data-ttu-id="63670-122">在商務用[Skype 2015 的集中式記錄服務](centralized-logging-service.md)中引入, 案例的元素如下:</span><span class="sxs-lookup"><span data-stu-id="63670-122">As introduced in [Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md), the elements of a scenario are:</span></span>
  
- <span data-ttu-id="63670-123">**提供者**如果您熟悉 OCSLogger, 提供者就是您選擇的元件, 可讓您告訴 OCSLogger 追蹤引擎應該從哪個部分收集記錄。</span><span class="sxs-lookup"><span data-stu-id="63670-123">**Providers** If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="63670-124">提供者是相同的元件, 且在許多情況下, 與 OCSLogger 中的元件名稱相同。</span><span class="sxs-lookup"><span data-stu-id="63670-124">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="63670-125">如果您不熟悉 OCSLogger, 提供者是集中式記錄服務可以從中收集記錄的伺服器角色特定元件。</span><span class="sxs-lookup"><span data-stu-id="63670-125">If you are not familiar with OCSLogger, providers are server role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="63670-126">如需提供者設定的詳細資料, 請參閱[在商務用 Skype Server 2015 中設定集中式記錄服務的提供者](configure-providers.md)。</span><span class="sxs-lookup"><span data-stu-id="63670-126">For details about the configuration of providers, see [Configure providers for Centralized Logging Service in Skype for Business Server 2015](configure-providers.md).</span></span>
    
- <span data-ttu-id="63670-127">身分**識別**參數身分設定案例的範圍和名稱。</span><span class="sxs-lookup"><span data-stu-id="63670-127">**Identity** The parameter -Identity sets the scope and name of the scenario.</span></span> <span data-ttu-id="63670-128">例如, 您可以設定範圍 "global", 並以 "LyssServiceScenario" 識別案例。</span><span class="sxs-lookup"><span data-stu-id="63670-128">For example, you could set a scope of "global" and identify the scenario with "LyssServiceScenario".</span></span> <span data-ttu-id="63670-129">當您結合兩個時, 您會定義身分識別 (例如, "global/LyssServiceScenario")。</span><span class="sxs-lookup"><span data-stu-id="63670-129">When you combine the two, you define the Identity (for example, "global/LyssServiceScenario").</span></span>
    
    <span data-ttu-id="63670-130">您也可以使用-Name 和-Parent 參數。</span><span class="sxs-lookup"><span data-stu-id="63670-130">Optionally, you can use the -Name and -Parent parameters.</span></span> <span data-ttu-id="63670-131">您可以定義 Name 參數來唯一識別該案例。</span><span class="sxs-lookup"><span data-stu-id="63670-131">You define the Name parameter to uniquely identify the scenario.</span></span> <span data-ttu-id="63670-132">如果您使用 [名稱], 您也必須使用上層將案例新增至 [全域] 或 [網站]。</span><span class="sxs-lookup"><span data-stu-id="63670-132">If you use Name, you must also use Parent to add the scenario to either global or site.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="63670-133">如果您使用 Name 和 Parent 參數, 就不能使用 **-身分識別**參數。</span><span class="sxs-lookup"><span data-stu-id="63670-133">If you use the Name and Parent parameters, you cannot use the **-Identity** parameter.</span></span>
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="63670-134">使用新的-CsClsScenario Cmdlet 建立新的案例</span><span class="sxs-lookup"><span data-stu-id="63670-134">To create a new scenario with the New-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="63670-135">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="63670-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="63670-136">若要建立記錄會話的新案例, 請使用[新的-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps)並定義案例的名稱 (也就是唯一識別該案例的方式)。</span><span class="sxs-lookup"><span data-stu-id="63670-136">To create a new scenario for a logging session, use [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) and define the name of the scenario (that is, how it will be uniquely identified).</span></span> <span data-ttu-id="63670-137">從 WPP (也就是 Windows 軟體追蹤預處理程式及預設值)、EventLog (也就是 Windows 事件記錄檔格式) 或 IISLog (也就是以 IIS 日誌檔案格式為基礎的 ASCII 格式檔案), 選擇一種記錄格式。</span><span class="sxs-lookup"><span data-stu-id="63670-137">Choose a type of logging format from WPP (that is, Windows software tracing preprocessor and is the default), EventLog (that is, Windows event log format), or IISLog (that is, ASCII format file based on the IIS log file format).</span></span> <span data-ttu-id="63670-138">接著, 定義階層 (如本主題中的記錄層級所定義), 以及旗標 (如本主題中的 [旗標] 所定義)。</span><span class="sxs-lookup"><span data-stu-id="63670-138">Next, define Level (as the defined under Logging Levels in this topic), and Flags (as defined under Flags in this topic).</span></span>
    
    <span data-ttu-id="63670-139">在這個範例案例中, 我們使用 LyssProvider 做為範例提供者變數。</span><span class="sxs-lookup"><span data-stu-id="63670-139">For this example scenario, we use LyssProvider as the example provider variable.</span></span>
    
    <span data-ttu-id="63670-140">若要使用定義的選項建立案例, 請輸入:</span><span class="sxs-lookup"><span data-stu-id="63670-140">To create a scenario using the options defined, type:</span></span>
    
   ```
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    <span data-ttu-id="63670-141">例如：</span><span class="sxs-lookup"><span data-stu-id="63670-141">For example:</span></span>
    
   ```
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    <span data-ttu-id="63670-142">使用-Name 和-Parent 替代格式:</span><span class="sxs-lookup"><span data-stu-id="63670-142">The alternate format using -Name and -Parent:</span></span>
    
   ```
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="63670-143">使用新的-CsClsScenario Cmdlet 來建立多個提供者的新案例</span><span class="sxs-lookup"><span data-stu-id="63670-143">To create a new scenario with multiple providers with the New-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="63670-144">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="63670-144">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="63670-145">每個範圍限制在兩個案例中。</span><span class="sxs-lookup"><span data-stu-id="63670-145">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="63670-146">不過, 您不受限於一組提供者數目的限制。</span><span class="sxs-lookup"><span data-stu-id="63670-146">However, you are not limited to a set number of providers.</span></span> <span data-ttu-id="63670-147">在這個範例中, 假設我們已建立三個提供者, 而且您想要將這三個程式指派給您所定義的情況。</span><span class="sxs-lookup"><span data-stu-id="63670-147">In this example, assume that we have created three providers, and you want to assign all three to the scenario you are defining.</span></span> <span data-ttu-id="63670-148">提供者變數名稱為 LyssProvider、ABServerProvider 和 SIPStackProvider。</span><span class="sxs-lookup"><span data-stu-id="63670-148">The provider variable names are LyssProvider, ABServerProvider, and SIPStackProvider.</span></span> <span data-ttu-id="63670-149">若要定義多個提供者並將其指派給某個案例, 請在商務用 Skype Server Management 命令介面或 Windows PowerShell 命令提示字元輸入以下內容:</span><span class="sxs-lookup"><span data-stu-id="63670-149">To define and assign multiple providers to a scenario, type the following at a Skype for Business Server Management Shell or Windows PowerShell command prompt:</span></span>
    
   ```
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > <span data-ttu-id="63670-150">就像在 Windows PowerShell 中已知一樣, 建立使用`@{<variable>=<value1>, <value2>, <value>…}`的雜湊值資料表的慣例是已知的 assplatting。</span><span class="sxs-lookup"><span data-stu-id="63670-150">As it is known in Windows PowerShell, the convention for creating a hash table of values using  `@{<variable>=<value1>, <value2>, <value>…}` is known assplatting.</span></span> <span data-ttu-id="63670-151">如需有關 Windows PowerShell 中 splatting 的詳細[https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760)資訊, 請參閱。</span><span class="sxs-lookup"><span data-stu-id="63670-151">For details about splatting in Windows PowerShell, see [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760).</span></span> 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a><span data-ttu-id="63670-152">使用 CsClsScenario Cmdlet 修改現有的案例</span><span class="sxs-lookup"><span data-stu-id="63670-152">To modify an existing scenario with the Set-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="63670-153">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="63670-153">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="63670-154">每個範圍限制在兩個案例中。</span><span class="sxs-lookup"><span data-stu-id="63670-154">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="63670-155">您可以隨時變更正在執行的案例, 即使正在進行記錄捕獲會話也一樣。</span><span class="sxs-lookup"><span data-stu-id="63670-155">You can change which scenarios are running at any time, even when a logging capture session is in process.</span></span> <span data-ttu-id="63670-156">如果您重新定義執行中的案例, 目前的記錄會話將停止使用已移除的案例, 然後開始使用新的案例。</span><span class="sxs-lookup"><span data-stu-id="63670-156">If you redefine the running scenarios, the current logging session will stop using the scenario that was removed and then begin using the new scenario.</span></span> <span data-ttu-id="63670-157">不過, 已移除之案例所捕獲的記錄資訊會保留在捕獲的記錄中。</span><span class="sxs-lookup"><span data-stu-id="63670-157">However, the logging information that was captured with the removed scenario remains in the captured logs.</span></span> <span data-ttu-id="63670-158">若要定義新的案例, 請執行下列動作 (也就是假設已將已定義的提供者加上名為 "S4Provider"):</span><span class="sxs-lookup"><span data-stu-id="63670-158">To define a new scenario, do the following (that is, assuming the addition of an already defined provider named "S4Provider"):</span></span>
    
   ```
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
   ```

    <span data-ttu-id="63670-159">例如：</span><span class="sxs-lookup"><span data-stu-id="63670-159">For example:</span></span>
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
   ```

    <span data-ttu-id="63670-160">如果您想要取代提供者, 請定義單一提供者或逗號分隔的提供者清單, 以取代目前的集合。</span><span class="sxs-lookup"><span data-stu-id="63670-160">If you want to replace providers, define a single provider or a comma separated list of providers to replace the current set.</span></span> <span data-ttu-id="63670-161">如果您只想要取代其中一個提供者, 請將目前的提供者新增至新的提供者, 以建立一組新的提供者, 以包含新的提供者與現有的提供者。</span><span class="sxs-lookup"><span data-stu-id="63670-161">If you only want to replace one of many providers, add the current providers with the new providers to create a new set of providers that contains both new providers and existing providers.</span></span> <span data-ttu-id="63670-162">若要將所有提供者替換成新的集合, 請輸入下列內容:</span><span class="sxs-lookup"><span data-stu-id="63670-162">To replace all providers with a new set, type the following:</span></span>
    
   ```
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
   ```

    <span data-ttu-id="63670-163">例如, 若要以 $LyssServiceProvider 取代目前的一組 $LyssProvider、$ABServerProvider 及 $SIPStackProvider:</span><span class="sxs-lookup"><span data-stu-id="63670-163">For example, to replace the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider:</span></span>
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
   ```

    <span data-ttu-id="63670-164">若要只用 $LyssServiceProvider 的目前 $LyssProvider 集合、$ABServerProvider 和 $SIPStackProvider 來取代 $LyssProvider 提供者, 請輸入下列內容:</span><span class="sxs-lookup"><span data-stu-id="63670-164">To replace just the $LyssProvider provider from the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider, type the following:</span></span>
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
   ```

### <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a><span data-ttu-id="63670-165">使用 CsClsScenario Cmdlet 移除現有的案例</span><span class="sxs-lookup"><span data-stu-id="63670-165">To remove an existing scenario with the Remove-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="63670-166">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="63670-166">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="63670-167">如果您想要移除先前定義的案例, 請輸入下列專案:</span><span class="sxs-lookup"><span data-stu-id="63670-167">If you want to remove a scenario that has been previously defined, type the following:</span></span>
    
   ```
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    <span data-ttu-id="63670-168">例如, 若要移除已定義的案例網站: 雷德蒙/LyssServiceScenario:</span><span class="sxs-lookup"><span data-stu-id="63670-168">For example, to remove the defined scenario site:Redmond/LyssServiceScenario:</span></span>
    
   ```
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

<span data-ttu-id="63670-169">**CsClsScenario** Cmdlet 會移除指定的案例, 但已捕獲的跟蹤仍可供您在記錄中搜尋。</span><span class="sxs-lookup"><span data-stu-id="63670-169">The **Remove-CsClsScenario** cmdlet removes the specified scenario, but the traces that have been captured are still available in the logs for you to search on.</span></span>
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a><span data-ttu-id="63670-170">使用 ClsScenarioEdit psm1 模組載入和卸載編輯 CsClsScenario Cmdlet</span><span class="sxs-lookup"><span data-stu-id="63670-170">To load and unload the Edit-CsClsScenario cmdlet using the ClsScenarioEdit.psm1 module</span></span>

1. <span data-ttu-id="63670-171">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="63670-171">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="63670-172">ClsScenarioEdit psm1 模組是作為單獨的網頁下載提供。</span><span class="sxs-lookup"><span data-stu-id="63670-172">The ClsScenarioEdit.psm1 module is provided as a separate Web download.</span></span> <span data-ttu-id="63670-173">模組是商務用 Skype Server 2015 調試工具的一部分。</span><span class="sxs-lookup"><span data-stu-id="63670-173">The module is part of the Skype for Business Server 2015 Debugging tools.</span></span> <span data-ttu-id="63670-174">根據預設, 調試工具會安裝在商務用 Server 2015 \ 調試工具的目錄 C:\Program Files\Skype 中。</span><span class="sxs-lookup"><span data-stu-id="63670-174">By default, the debugging tools are installed in the directory C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> 
  
2. <span data-ttu-id="63670-175">在 Windows PowerShell 中, 鍵入:</span><span class="sxs-lookup"><span data-stu-id="63670-175">From the Windows PowerShell, type:</span></span>
    
   ```
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > <span data-ttu-id="63670-176">成功載入模組時, 會將您傳回 Windows PowerShell 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="63670-176">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="63670-177">若要確認是否已載入模組, 且可以使用編輯 CsClsScenario, 請輸入`Get-Help Edit-CsClsScenario`。</span><span class="sxs-lookup"><span data-stu-id="63670-177">To confirm that the module is loaded and that Edit-CsClsScenario is available, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="63670-178">您應該會看到 EditCsClsScenario 語法的基本摘要。</span><span class="sxs-lookup"><span data-stu-id="63670-178">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span> 
  
3. <span data-ttu-id="63670-179">若要卸載模組, 請輸入:</span><span class="sxs-lookup"><span data-stu-id="63670-179">To unload the modules, type:</span></span>
    
   ```
   Remove-Module ClsController
   ```

    > [!TIP]
    > <span data-ttu-id="63670-180">成功卸載該模組後, 就會傳回您至 Windows PowerShell 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="63670-180">Successful unloading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="63670-181">若要確認已卸載該模組, 請`Get-Help Edit-CsClsScenario`輸入。</span><span class="sxs-lookup"><span data-stu-id="63670-181">To confirm that the module is unloaded, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="63670-182">Windows PowerShell 會嘗試找出 Cmdlet 的說明並失敗。</span><span class="sxs-lookup"><span data-stu-id="63670-182">Windows PowerShell will attempt to locate the help for the cmdlet and fail.</span></span> 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="63670-183">使用 [編輯 ClsController] 模組從案例中移除現有的提供者</span><span class="sxs-lookup"><span data-stu-id="63670-183">To remove an existing provider from a scenario with the Edit-ClsController module</span></span>

1. <span data-ttu-id="63670-184">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="63670-184">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="63670-185">在 Windows PowerShell 中, 鍵入:</span><span class="sxs-lookup"><span data-stu-id="63670-185">From the Windows PowerShell, type:</span></span>
    
   ```
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > <span data-ttu-id="63670-186">成功載入模組時, 會將您傳回 Windows PowerShell 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="63670-186">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="63670-187">若要確認是否已載入模組, 且可以使用編輯 CsClsScenario, 請輸入`Get-Help Edit-CsClsScenario`。</span><span class="sxs-lookup"><span data-stu-id="63670-187">To confirm that the module is loaded and that Edit-CsClsScenario is available, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="63670-188">您應該會看到 EditCsClsScenario 語法的基本摘要。</span><span class="sxs-lookup"><span data-stu-id="63670-188">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span> 
  
3. <span data-ttu-id="63670-189">若要從 AlwaysOn 案例中移除提供者, 請輸入:</span><span class="sxs-lookup"><span data-stu-id="63670-189">To remove a provider from the AlwaysOn scenario, type:</span></span>
    
   ```
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
   ```

   <span data-ttu-id="63670-190">例如:</span><span class="sxs-lookup"><span data-stu-id="63670-190">For Example:</span></span>
    
   ```
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
   ```

   <span data-ttu-id="63670-191">參數 ScenarioName 和 ProviderName 是位置 (也就是說, 它們必須在命令列的預期位置中定義) 參數。</span><span class="sxs-lookup"><span data-stu-id="63670-191">The parameters ScenarioName and ProviderName are positional (that is, they must be defined in the expected position in the command line) parameters.</span></span> <span data-ttu-id="63670-192">如果案例名稱是位於第二個位置, 且提供者的位置是以位置1為 Cmdlet 的名稱, 則無需要明確定義參數名稱。</span><span class="sxs-lookup"><span data-stu-id="63670-192">The parameter name does not have to be explicitly defined if the scenario name is in position two and the provider is in position three, relative to the name of the cmdlet as position one.</span></span> <span data-ttu-id="63670-193">使用這項資訊, 前一個命令會輸入如下:</span><span class="sxs-lookup"><span data-stu-id="63670-193">Using this information, the previous command would be typed as:</span></span>
    
   ```
   Edit-CsClsScenario AlwaysOn ChatServer -Remove
   ```

   <span data-ttu-id="63670-194">放置參數值的位置只適用于案例與提供者。</span><span class="sxs-lookup"><span data-stu-id="63670-194">The positional placing of the parameter values applies only to -Scenario and -Provider.</span></span> <span data-ttu-id="63670-195">所有其他參數都必須明確定義。</span><span class="sxs-lookup"><span data-stu-id="63670-195">All other parameters must be explicitly defined.</span></span>
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="63670-196">使用編輯 ClsController 模組將提供者新增到案例</span><span class="sxs-lookup"><span data-stu-id="63670-196">To add a provider to a scenario with the Edit-ClsController module</span></span>

1. <span data-ttu-id="63670-197">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="63670-197">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="63670-198">若要將提供者新增至 AlwaysOn 案例, 請輸入:</span><span class="sxs-lookup"><span data-stu-id="63670-198">To add a provider to the AlwaysOn scenario, type:</span></span>
    
   ```
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    <span data-ttu-id="63670-199">例如:</span><span class="sxs-lookup"><span data-stu-id="63670-199">For Example:</span></span>
    
   ```
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    <span data-ttu-id="63670-200">-Loglevel 可以是 [致命]、[錯誤]、[警告]、[資訊]、[調試] 或 [全部] 的類型。</span><span class="sxs-lookup"><span data-stu-id="63670-200">-Loglevel can be of the type Fatal, Error, Warning, Info, Verbose, Debug, or All.</span></span> <span data-ttu-id="63670-201">-Flags 可以是提供者所支援的任何標誌, 例如 TF_COMPONENT、TF_DIAG。</span><span class="sxs-lookup"><span data-stu-id="63670-201">-Flags can be any of the flags that the provider supports, such as TF_COMPONENT, TF_DIAG.</span></span> <span data-ttu-id="63670-202">-標誌也可以是 ALL 值</span><span class="sxs-lookup"><span data-stu-id="63670-202">-Flags can also be of value ALL</span></span>
    
   <span data-ttu-id="63670-203">您也可以使用 Cmdlet 的位置功能, 在前面的範例中進行輸入。</span><span class="sxs-lookup"><span data-stu-id="63670-203">The previous example can also be typed using the positional feature of the cmdlet.</span></span> <span data-ttu-id="63670-204">例如, 若要將提供者 ChatServer 新增至 AlwaysOn 案例, 請輸入:</span><span class="sxs-lookup"><span data-stu-id="63670-204">For example, to add the provider ChatServer to the AlwaysOn scenario, type:</span></span>
    
   ```
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```
