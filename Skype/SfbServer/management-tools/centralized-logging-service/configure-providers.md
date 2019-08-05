---
title: 設定商務用 Skype 2015 中集中式記錄服務的提供者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
description: '摘要: 瞭解如何在商務用 Skype Server 2015 中設定集中式記錄服務的案例提供者。'
ms.openlocfilehash: a9987d99b2caf00acc92de92a8d997845ad8f921
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186823"
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="38d8f-103">設定商務用 Skype 2015 中集中式記錄服務的提供者</span><span class="sxs-lookup"><span data-stu-id="38d8f-103">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="38d8f-104">**摘要:** 瞭解如何在商務用 Skype Server 2015 中設定集中式記錄服務的案例提供者。</span><span class="sxs-lookup"><span data-stu-id="38d8f-104">**Summary:** Learn how to configure scenario providers for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="38d8f-105">集中式記錄服務提供者的概念與設定是最重要的功能之一。</span><span class="sxs-lookup"><span data-stu-id="38d8f-105">The concepts and configuration of providers in Centralized Logging Service is one of the most important to grasp.</span></span> <span data-ttu-id="38d8f-106">Theproviders [直接對應到商務用 skype 伺服器追蹤模型中的商務用 Skype Server 角色元件]。</span><span class="sxs-lookup"><span data-stu-id="38d8f-106">Theproviders map directly to Skype for Business Server server role components in the Skype for Business Server tracing model.</span></span> <span data-ttu-id="38d8f-107">提供者會定義要追蹤的商務用 Skype Server 2015 元件、要收集的訊息類型 (例如, 致命、錯誤或警告), 以及旗標 (例如 TF_Connection 或 TF_Diag)。</span><span class="sxs-lookup"><span data-stu-id="38d8f-107">The provider defines the components of a Skype for Business Server 2015 that will be traced, the type of messages (for example, fatal, error, or warning) to collect, and the flags (for example, TF_Connection or TF_Diag).</span></span> <span data-ttu-id="38d8f-108">提供者是每個商務用 Skype Server 伺服器角色中可追蹤的元件。</span><span class="sxs-lookup"><span data-stu-id="38d8f-108">Providers are the traceable components in each Skype for Business Server server role.</span></span> <span data-ttu-id="38d8f-109">使用提供者, 您可以定義元件的追蹤層級與類型 (例如, S4、SIPStack、IM 和目前狀態)。</span><span class="sxs-lookup"><span data-stu-id="38d8f-109">By using providers, you define the level and type of tracing on components (for example, S4, SIPStack, IM and Presence).</span></span> <span data-ttu-id="38d8f-110">已定義的提供者會在案例中用來針對特定的邏輯集合, 針對特定的問題條件來分組所有提供者。</span><span class="sxs-lookup"><span data-stu-id="38d8f-110">The defined provider is used in a scenario to group all of the providers for a given logical collection that address a specific problem condition.</span></span>
  
<span data-ttu-id="38d8f-111">若要使用商務用 Skype Server Management 命令介面執行集中式記錄服務功能, 您必須是 CsAdministrator 或 CsServerAdministrator 角色的存取控制 (RBAC) 安全性群組的成員, 或是一個自訂的 RBAC 角色,包含這兩個群組中的任一個。</span><span class="sxs-lookup"><span data-stu-id="38d8f-111">To run the Centralized Logging Service functions using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="38d8f-112">若要傳回已指派這個 Cmdlet 的所有角色式存取控制 (RBAC) 角色的清單 (包括您自行建立的任何自訂 RBAC 角色), 請從商務用 Skype Server Management 命令介面或 Windows PowerShell 中執行下列命令。提示符</span><span class="sxs-lookup"><span data-stu-id="38d8f-112">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="38d8f-113">例如：</span><span class="sxs-lookup"><span data-stu-id="38d8f-113">For example:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="38d8f-114">本主題的其餘部分將重點放在如何定義提供者、修改提供者以及提供者定義所包含的內容來優化您的疑難排解。</span><span class="sxs-lookup"><span data-stu-id="38d8f-114">The remainder of this topic focuses on how to define providers, modify a provider and what a provider definition contains to optimize your troubleshooting.</span></span> <span data-ttu-id="38d8f-115">有兩種方式可以發出集中式記錄服務命令。</span><span class="sxs-lookup"><span data-stu-id="38d8f-115">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="38d8f-116">您可以在 [商務伺服器 2015 \ CLSAgent] 的 [目錄 C:\Program Files\Common Files\Skype 中, 使用預設位置的 CLSController。</span><span class="sxs-lookup"><span data-stu-id="38d8f-116">You can use the CLSController.exe that is located, by default, in the directory C:\Program Files\Common Files\Skype for Business Server 2015\CLSAgent.</span></span> <span data-ttu-id="38d8f-117">或者, 您可以使用商務用 Skype Server Management Shell 來頒發 Windows PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="38d8f-117">Or, you can use the Skype for Business Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="38d8f-118">使用 Windows PowerShell, 您可以定義在記錄會話中使用的新提供者, 並完全控制自己的建立、收集的內容, 以及它們收集資料的層級。</span><span class="sxs-lookup"><span data-stu-id="38d8f-118">By using Windows PowerShell, you can define new providers for use in your logging sessions, and have complete control over their creation, what they collect, and at what level they collect data.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="38d8f-119">如前文所述, 提供者功能非常強大。</span><span class="sxs-lookup"><span data-stu-id="38d8f-119">As mentioned, providers are very powerful.</span></span> <span data-ttu-id="38d8f-120">不過, 案例的功能更強大, 因為它們包含在提供者所代表的元件上設定和執行追蹤所需的所有資訊的 embodiment。</span><span class="sxs-lookup"><span data-stu-id="38d8f-120">However, scenarios are more powerful because they contain the embodiment of all information needed to set and execute tracing on the components that the providers represent.</span></span> <span data-ttu-id="38d8f-121">隨著案例成為提供者集合, 與執行的批次處理檔案相比, 這可能是鬆散的, 在命令列中, 您可以使用包含上百個命令的批次檔案來收集大量的資訊, 而不是一次發出一個命令。</span><span class="sxs-lookup"><span data-stu-id="38d8f-121">With scenarios being a collection of providers, this could be loosely compared to running a batch file containing hundreds of commands to collect a lot of information versus issuing hundreds of commands, one at a time, at the command line.</span></span> 
  
<span data-ttu-id="38d8f-122">[集中式記錄] 服務提供已為您定義的許多案例, 而不是要求您深入瞭解提供者的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="38d8f-122">Instead of requiring you to dig deeply into the details of providers, the Centralized Logging Service provides a number of scenarios that are already defined for you.</span></span> <span data-ttu-id="38d8f-123">提供的案例涵蓋絕大多數您可能會遇到的問題。</span><span class="sxs-lookup"><span data-stu-id="38d8f-123">The provided scenarios cover the vast majority of possible issues that you will encounter.</span></span> <span data-ttu-id="38d8f-124">在少數情況下, 您可能需要建立並定義提供者, 並將其指派給案例。</span><span class="sxs-lookup"><span data-stu-id="38d8f-124">In rare cases, you may need to create and define providers and assign them to scenarios.</span></span> <span data-ttu-id="38d8f-125">我們強烈建議您先熟悉所提供的各個案例, 然後再調查需要建立新的提供者和案例的需求。</span><span class="sxs-lookup"><span data-stu-id="38d8f-125">We strongly recommend that you become familiar with each of the scenarios provided before you investigate the need to create new providers and scenarios.</span></span> <span data-ttu-id="38d8f-126">您可以在這裡找到有關建立提供者的資訊, 讓您熟悉案例如何使用提供者元素來收集追蹤資訊, 目前不提供提供者本身的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="38d8f-126">While information about creating providers is found here to familiarize you with how the scenarios use the provider elements to collect trace information, details on the providers themselves are not provided at this time.</span></span> 
  
<span data-ttu-id="38d8f-127">在[商務用 Skype 2015 的集中式記錄服務](centralized-logging-service.md)中引入, 定義用來在方案中使用之提供者的主要元素如下:</span><span class="sxs-lookup"><span data-stu-id="38d8f-127">Introduced in [Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md), the key elements of defining a provider for use in a scenario are:</span></span>
  
- <span data-ttu-id="38d8f-128">**提供者**如果您熟悉 OCSLogger, 提供者就是您選擇的元件, 可讓您告訴 OCSLogger 追蹤引擎應該從哪個部分收集記錄。</span><span class="sxs-lookup"><span data-stu-id="38d8f-128">**Providers** If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="38d8f-129">提供者是相同的元件, 且在許多情況下, 與 OCSLogger 中的元件名稱相同。</span><span class="sxs-lookup"><span data-stu-id="38d8f-129">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="38d8f-130">如果您不熟悉 OCSLogger, 提供者是集中式記錄服務可以從中收集記錄的伺服器角色特定元件。</span><span class="sxs-lookup"><span data-stu-id="38d8f-130">If you are not familiar with OCSLogger, providers are server-role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="38d8f-131">在集中式記錄服務的情況下, CLSAgent 是集中式記錄服務的結構元件, 可追蹤您在提供者配置中定義的元件。</span><span class="sxs-lookup"><span data-stu-id="38d8f-131">In the case of the Centralized Logging Service, the CLSAgent is the architectural part of the Centralized Logging Service that is doing the tracing of the components that you define in the providers configuration.</span></span>
    
- <span data-ttu-id="38d8f-132">**記錄層級**OCSLogger 提供選項, 可為收集的資料選擇多個詳細資料層級。</span><span class="sxs-lookup"><span data-stu-id="38d8f-132">**Logging levels** OCSLogger provided the option to choose a number of levels of detail for the data collected.</span></span> <span data-ttu-id="38d8f-133">這個功能是集中式記錄服務和案例的有機組成部分, 且由**Type**參數定義。</span><span class="sxs-lookup"><span data-stu-id="38d8f-133">This feature is an integral part of the Centralized Logging Service and scenarios, and is defined by the **Type** parameter.</span></span> <span data-ttu-id="38d8f-134">您可以從下列選項中進行選擇:</span><span class="sxs-lookup"><span data-stu-id="38d8f-134">You can choose from the following:</span></span>
    
  - <span data-ttu-id="38d8f-135">**全部**收集已定義提供者記錄的 [致命]、[錯誤]、[警告]、[詳細] 和 [調試資訊] 類型的追蹤訊息。</span><span class="sxs-lookup"><span data-stu-id="38d8f-135">**All** Collects trace messages of type fatal, error, warning, verbose, and debug info to the log for the defined provider.</span></span>
    
  - <span data-ttu-id="38d8f-136">**致命**只收集定義為 "致命" 的追蹤訊息。</span><span class="sxs-lookup"><span data-stu-id="38d8f-136">**Fatal** Collects only the trace messages defined as "Fatal."</span></span>
    
  - <span data-ttu-id="38d8f-137">**錯誤**只收集定義為「錯誤」或「致命」的追蹤訊息。</span><span class="sxs-lookup"><span data-stu-id="38d8f-137">**Error** Collects only the trace messages defined as "Error" or "Fatal."</span></span>
    
  - <span data-ttu-id="38d8f-138">**警告**只收集 "Warning"、"錯誤" 和 "致命" 類型的追蹤訊息。</span><span class="sxs-lookup"><span data-stu-id="38d8f-138">**Warning** Collects only the trace messages of type "Warning," "Error" and "Fatal."</span></span>
    
  - <span data-ttu-id="38d8f-139">**資訊**只收集指出已定義之提供者的資訊訊息的追蹤訊息, 以及致命、錯誤和警告訊息。</span><span class="sxs-lookup"><span data-stu-id="38d8f-139">**Info** Collects only the trace messages that indicate an informational message for the defined provider, plus fatal, error, and warning messages.</span></span>
    
  - <span data-ttu-id="38d8f-140">**詳細**資訊收集已定義提供者之 [致命]、[錯誤]、[警告] 和 [詳細] 類型的所有追蹤訊息。</span><span class="sxs-lookup"><span data-stu-id="38d8f-140">**Verbose** Collects all trace messages of type fatal, error, warning and verbose for the defined provider.</span></span>
    
  - <span data-ttu-id="38d8f-141">**調試 (調試**) 實質上相當於已定義提供者的「全部」, 收集類型為致命、錯誤、警告、資訊、詳細及調試的痕跡。</span><span class="sxs-lookup"><span data-stu-id="38d8f-141">**Debug** this is essentially an equivalent of 'All' - collects traces of type Fatal, Error, Warning, Info, Verbose and Debug for the defined provider.</span></span>
    
- <span data-ttu-id="38d8f-142">**旗標**OCSLogger 提供選項, 為每個提供者選擇您可以從追蹤檔案中檢索之資訊類型的每個提供者的標記。</span><span class="sxs-lookup"><span data-stu-id="38d8f-142">**Flags** OCSLogger provided the option to choose flags for each provider that defined what type of information you could retrieve from the trace files.</span></span> <span data-ttu-id="38d8f-143">您可以根據提供者選擇下列標誌:</span><span class="sxs-lookup"><span data-stu-id="38d8f-143">You can chose the following flags, based on the provider:</span></span>
    
  - <span data-ttu-id="38d8f-144">**TF_Connection**提供與連接相關的記錄專案。</span><span class="sxs-lookup"><span data-stu-id="38d8f-144">**TF_Connection** Provides connection-related log entries.</span></span> <span data-ttu-id="38d8f-145">這些記錄包含與特定元件建立的連線的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="38d8f-145">These logs include information about connections established to and from a particular component.</span></span> <span data-ttu-id="38d8f-146">這也可能包含大量的網路層級資訊 (也就是不含連線概念的元件)。</span><span class="sxs-lookup"><span data-stu-id="38d8f-146">This may also include significant network-level information (that is, for components without the concept of a connection).</span></span>
    
  - <span data-ttu-id="38d8f-147">**TF_Security**提供與安全性有關的所有事件/記錄專案。</span><span class="sxs-lookup"><span data-stu-id="38d8f-147">**TF_Security** Provides all events/log entries related to security.</span></span> <span data-ttu-id="38d8f-148">例如, 在 SipStack 中, 這些是安全事件, 例如網域驗證失敗, 以及用戶端驗證/授權失敗。</span><span class="sxs-lookup"><span data-stu-id="38d8f-148">For example, for SipStack, these are security events such as domain validation failure, and client authentication/authorization failures.</span></span>
    
  - <span data-ttu-id="38d8f-149">**TF_Diag**提供診斷事件, 您可以用來診斷或疑難排解元件。</span><span class="sxs-lookup"><span data-stu-id="38d8f-149">**TF_Diag** Provides diagnostics events that you can use to diagnose or troubleshoot the component.</span></span> <span data-ttu-id="38d8f-150">例如, 在 SipStack 中, 這些是證書失敗, 或 DNS 警告/錯誤。</span><span class="sxs-lookup"><span data-stu-id="38d8f-150">For example, for SipStack, these are certificate failures, or DNS warnings/errors.</span></span>
    
  - <span data-ttu-id="38d8f-151">**TF_Protocol**提供通訊協定, 例如 SIP 及組合的群組編解碼器套件訊息。</span><span class="sxs-lookup"><span data-stu-id="38d8f-151">**TF_Protocol** Provides protocol messages such as SIP and Combined Community Codec Pack messages.</span></span>
    
  - <span data-ttu-id="38d8f-152">**TF_Component**啟用記錄提供者指定的元件。</span><span class="sxs-lookup"><span data-stu-id="38d8f-152">**TF_Component** Enables logging on the components specified as part of the providers.</span></span>
    
  - <span data-ttu-id="38d8f-153">**全部**設定提供者可用的所有可用旗標。</span><span class="sxs-lookup"><span data-stu-id="38d8f-153">**All** Sets all available flags available for the provider.</span></span>
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a><span data-ttu-id="38d8f-154">若要查看現有集中式記錄服務案例提供者的相關資訊</span><span class="sxs-lookup"><span data-stu-id="38d8f-154">To review information about existing Centralized Logging Service scenario providers</span></span>

1. <span data-ttu-id="38d8f-155">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="38d8f-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="38d8f-156">若要查看現有提供者的設定, 請輸入下列內容:</span><span class="sxs-lookup"><span data-stu-id="38d8f-156">To review the configuration of existing providers, type the following:</span></span>
    
   ```
   Get-CsClsScenario -Identity <scope and scenario name>
   ```

    <span data-ttu-id="38d8f-157">例如, 若要查看全域會議助理的相關資訊, 請輸入:</span><span class="sxs-lookup"><span data-stu-id="38d8f-157">For example, to review information about the global conferencing attendant, type:</span></span>
    
   ```
   Get-CsClsScenario -Identity "global/CAA"
   ```

    <span data-ttu-id="38d8f-158">該命令會顯示包含相關聯標誌、設定和元件的提供者清單。</span><span class="sxs-lookup"><span data-stu-id="38d8f-158">The command displays a list of providers with the associated flags, settings, and components.</span></span> <span data-ttu-id="38d8f-159">如果顯示的資訊不足, 或者清單對於預設的 Windows PowerShell 清單格式而言太長, 您可以透過定義不同的輸出方法來顯示其他資訊。</span><span class="sxs-lookup"><span data-stu-id="38d8f-159">If the information displayed is not enough or the list is too long for the default Windows PowerShell list format, you can display additional information by defining a different output method.</span></span> <span data-ttu-id="38d8f-160">若要這樣做, 請輸入:</span><span class="sxs-lookup"><span data-stu-id="38d8f-160">To do this, type:</span></span>
    
   ```
   Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
   ```

    <span data-ttu-id="38d8f-161">這個命令的輸出會以五行格式顯示每個提供者, 其中包含提供者名稱、記錄類型、記錄層級、旗標、GUID 和角色, 每個提供者都在個別的行上。</span><span class="sxs-lookup"><span data-stu-id="38d8f-161">The output of this command displays each provider displayed in a five line format with the provider name, type of logging, logging level, flags, GUID, and role, each one on a separate line.</span></span> 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a><span data-ttu-id="38d8f-162">定義新的集中式記錄服務案例提供者</span><span class="sxs-lookup"><span data-stu-id="38d8f-162">To define a new Centralized Logging Service scenario provider</span></span>

1. <span data-ttu-id="38d8f-163">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="38d8f-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="38d8f-164">案例提供者包含要追蹤的元件、要使用的旗標, 以及要收集的詳細資料層級。</span><span class="sxs-lookup"><span data-stu-id="38d8f-164">A scenario provider consists of a component to trace, flags to use, and a level of detail to collect.</span></span> <span data-ttu-id="38d8f-165">若要執行此動作, 請輸入:</span><span class="sxs-lookup"><span data-stu-id="38d8f-165">You do this by typing:</span></span>
    
   ```
   $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
   ```

    <span data-ttu-id="38d8f-166">例如, [追蹤提供者] 定義定義要收集哪些內容, 以及從 Lyss 提供者的詳細資料層級看起來如下:</span><span class="sxs-lookup"><span data-stu-id="38d8f-166">For example, a trace provider definition that defines what to collect and to what level of detail from the Lyss provider looks like the following:</span></span>
    
   ```
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
   ```

<span data-ttu-id="38d8f-167">層級會收集致命、錯誤、警告及資訊訊息。</span><span class="sxs-lookup"><span data-stu-id="38d8f-167">The -Level collects fatal, error, warning, and information messages.</span></span> <span data-ttu-id="38d8f-168">所使用的標誌全都是為 Lyss 提供者所定義的, 且包含 TF_Connection、TF_Diag 和 TF_Protocol。定義 $LyssProvider 變數之後, 您可以使用**新的-CsClsScenario** Cmdlet 來收集來自 Lyss 提供者的追蹤。</span><span class="sxs-lookup"><span data-stu-id="38d8f-168">The flags used are all of those defined for the Lyss provider, and include TF_Connection, TF_Diag and TF_Protocol.After the variable $LyssProvider is defined, you can use it with the **New-CsClsScenario** cmdlet to collect traces from the Lyss provider.</span></span> <span data-ttu-id="38d8f-169">若要完成建立並將提供者指派給新的案例, 請輸入:</span><span class="sxs-lookup"><span data-stu-id="38d8f-169">To complete the creation and assignment of the provider to a new scenario, type:</span></span>

```
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

<span data-ttu-id="38d8f-170">其中 $LyssProvider 是包含使用**新 CsClsProvider**建立之已定義之案例的變數。</span><span class="sxs-lookup"><span data-stu-id="38d8f-170">Where $LyssProvider is the variable containing the defined scenario created with **New-CsClsProvider**.</span></span>
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a><span data-ttu-id="38d8f-171">變更現有的集中式記錄服務案例提供者</span><span class="sxs-lookup"><span data-stu-id="38d8f-171">To change an existing Centralized Logging Service scenario provider</span></span>

1. <span data-ttu-id="38d8f-172">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="38d8f-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="38d8f-173">若要更新或變更現有提供者的設定, 請輸入:</span><span class="sxs-lookup"><span data-stu-id="38d8f-173">To update or change the configuration of an existing provider, type:</span></span>
    
   ```
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
   ```

    <span data-ttu-id="38d8f-174">然後, 您可以輸入下列內容來更新案例以指派提供者:</span><span class="sxs-lookup"><span data-stu-id="38d8f-174">You then update the scenario to assign the provider by typing the following:</span></span>
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
   ```

<span data-ttu-id="38d8f-175">此命令的最終結果是案例網站: [雷德蒙]/[RedmondLyssInfo] 會針對指派給它的提供者更新旗標和層級。</span><span class="sxs-lookup"><span data-stu-id="38d8f-175">The end result of the command is that the scenario site:Redmond/RedmondLyssInfo will have updated flags and level for the provider assigned to it.</span></span> <span data-ttu-id="38d8f-176">您可以使用 [取得 CsClsScenario] 來查看新案例。</span><span class="sxs-lookup"><span data-stu-id="38d8f-176">You can view the new scenario by using Get-CsClsScenario.</span></span> <span data-ttu-id="38d8f-177">如需詳細資訊, 請參閱[CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="38d8f-177">For details, see [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span></span>
> [!CAUTION]
> <span data-ttu-id="38d8f-178">**新的-ClsCsProvider**不會檢查以判斷旗標是否有效。</span><span class="sxs-lookup"><span data-stu-id="38d8f-178">**New-ClsCsProvider** does not check to determine whether the flags are valid.</span></span> <span data-ttu-id="38d8f-179">確認旗標 (例如 TF_DIAG 或 TF_CONNECTION) 拼寫正確無誤。</span><span class="sxs-lookup"><span data-stu-id="38d8f-179">Make sure that the spelling of the flags (for example, TF_DIAG or TF_CONNECTION) is spelled correctly.</span></span> <span data-ttu-id="38d8f-180">如果旗標沒有正確拼寫, 提供者就無法傳回預期的記錄資訊。</span><span class="sxs-lookup"><span data-stu-id="38d8f-180">If the flags are not spelled correctly, the provider cannot return the expected log information.</span></span>
  
<span data-ttu-id="38d8f-181">如果您想要在此案例中新增其他提供者, 請輸入下列專案:</span><span class="sxs-lookup"><span data-stu-id="38d8f-181">If you want to add additional providers to this scenario, type the following:</span></span>

```
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

<span data-ttu-id="38d8f-182">每個使用 Add 指令定義的提供者, 都已使用**新的-CsClsProvider**程式進行定義。</span><span class="sxs-lookup"><span data-stu-id="38d8f-182">Where each provider defined with the Add directive has already been defined using the **New-CsClsProvider** process.</span></span>
### <a name="to-remove-a-scenario-provider"></a><span data-ttu-id="38d8f-183">移除案例提供者</span><span class="sxs-lookup"><span data-stu-id="38d8f-183">To remove a scenario provider</span></span>

1. <span data-ttu-id="38d8f-184">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="38d8f-184">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="38d8f-185">提供的 Cmdlet 可讓您更新現有的提供者, 並建立新的提供者。</span><span class="sxs-lookup"><span data-stu-id="38d8f-185">The cmdlets provided allow you to update existing providers and create new providers.</span></span> <span data-ttu-id="38d8f-186">若要移除提供者, 您必須使用提供者參數的 Replace 指令來**設定-CsClsScenario**。</span><span class="sxs-lookup"><span data-stu-id="38d8f-186">To remove a provider, you must use the Replace directive for the Provider parameter to **Set-CsClsScenario**.</span></span> <span data-ttu-id="38d8f-187">完全移除提供者的唯一方式是將它替換成相同名稱的重新定義提供者, 並使用 Update 指令。</span><span class="sxs-lookup"><span data-stu-id="38d8f-187">The only way to completely remove a provider is to replace it with a redefined provider of the same name and use the Update directive.</span></span> <span data-ttu-id="38d8f-188">例如, 我們的提供者 LyssProvider 是使用 WPP 作為記錄類型、將 level 設定為 Debug, 以及旗標和 TF_DIAG 來定義。</span><span class="sxs-lookup"><span data-stu-id="38d8f-188">For example, our provider LyssProvider is defined with WPP as the log type, level set to Debug, and flags set are TF_CONNECTION and TF_DIAG.</span></span> <span data-ttu-id="38d8f-189">您必須將 [旗標] 變更為 [全部]。</span><span class="sxs-lookup"><span data-stu-id="38d8f-189">You need to change the flags to "All".</span></span> <span data-ttu-id="38d8f-190">若要變更提供者, 請輸入下列內容:</span><span class="sxs-lookup"><span data-stu-id="38d8f-190">To change the provider, type the following:</span></span>
    
   ```
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"
   ```

   ```
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}
   ```

3. <span data-ttu-id="38d8f-191">如果您想要完全移除某個案例, 以及與其相關聯的提供者, 請輸入下列內容:</span><span class="sxs-lookup"><span data-stu-id="38d8f-191">If you want to completely remove a scenario and the providers associated with it, type the following:</span></span>
    
   ```
   Remove-CsClsScenario -Identity <scope and name of scenario>
   ```

    <span data-ttu-id="38d8f-192">例如：</span><span class="sxs-lookup"><span data-stu-id="38d8f-192">For example:</span></span>
    
   ```
   Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
   ```

    > [!CAUTION]
    > <span data-ttu-id="38d8f-193">Cmdlet**移除-CsClsScenario**不會提示您進行確認。</span><span class="sxs-lookup"><span data-stu-id="38d8f-193">The cmdlet **Remove-CsClsScenario** does not prompt you for confirmation.</span></span> <span data-ttu-id="38d8f-194">隨後會刪除該案例, 以及已指派給它的提供者。</span><span class="sxs-lookup"><span data-stu-id="38d8f-194">The scenario is deleted, along with the providers that were assigned to it.</span></span> <span data-ttu-id="38d8f-195">您可以重新執行用來建立該案例的命令來重新建立。</span><span class="sxs-lookup"><span data-stu-id="38d8f-195">You can recreate the scenario by re-running the commands used to create it initially.</span></span> <span data-ttu-id="38d8f-196">沒有復原已移除之案例或提供者的程式。</span><span class="sxs-lookup"><span data-stu-id="38d8f-196">There is no procedure to recover removed scenarios or providers.</span></span>
  
<span data-ttu-id="38d8f-197">當您使用**CsClsScenario** Cmdlet 移除案例時, 您會完全移除範圍中的案例。</span><span class="sxs-lookup"><span data-stu-id="38d8f-197">When you remove a scenario by using the **Remove-CsClsScenario** cmdlet, you completely remove the scenario from the scope.</span></span> <span data-ttu-id="38d8f-198">若要使用您所建立的案例, 以及該案例中的提供者, 您可以建立新的提供者, 並將它們指派給新的案例。</span><span class="sxs-lookup"><span data-stu-id="38d8f-198">To use the scenarios that you created and the providers that were a part of the scenario, you create new providers and assign them to a new scenario.</span></span>
## <a name="see-also"></a><span data-ttu-id="38d8f-199">另請參閱</span><span class="sxs-lookup"><span data-stu-id="38d8f-199">See also</span></span>

[<span data-ttu-id="38d8f-200">CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="38d8f-200">Get-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="38d8f-201">新-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="38d8f-201">New-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="38d8f-202">移除-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="38d8f-202">Remove-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="38d8f-203">Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="38d8f-203">Set-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="38d8f-204">新-CsClsProvider</span><span class="sxs-lookup"><span data-stu-id="38d8f-204">New-CsClsProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps)
