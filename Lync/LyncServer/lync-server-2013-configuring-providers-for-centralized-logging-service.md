---
title: Lync Server 2013：針對集中式記錄服務配置提供者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring providers for Centralized Logging Service
ms:assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688082(v=OCS.15)
ms:contentKeyID: 49733678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e11af1a56e3975f96e19dc43dff27aef1d512ec9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974822"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-providers-for-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="bd48a-102">在 Lync Server 2013 中組態集中式記錄服務的提供者</span><span class="sxs-lookup"><span data-stu-id="bd48a-102">Configuring providers for Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd48a-103">_**主題上次修改日期：** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="bd48a-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="bd48a-104">集中式記錄服務*提供者*的概念與設定是最重要的功能之一。</span><span class="sxs-lookup"><span data-stu-id="bd48a-104">The concepts and configuration of *providers* in Centralized Logging Service is one of the most important to grasp.</span></span> <span data-ttu-id="bd48a-105">*提供者*會直接對應到 lync server 追蹤模型中的 lync server server 角色元件。</span><span class="sxs-lookup"><span data-stu-id="bd48a-105">The *providers* map directly to Lync Server server role components in the Lync Server tracing model.</span></span> <span data-ttu-id="bd48a-106">提供者會定義要追蹤的 Lync Server 2013 元件、要收集的訊息類型（例如，致命、錯誤或警告），以及旗標（例如 TF\_CONNECTION 或 TF\_傳送程式）。</span><span class="sxs-lookup"><span data-stu-id="bd48a-106">The provider defines the components of a Lync Server 2013 that will be traced, the type of messages (for example, fatal, error, or warning) to collect, and the flags (for example, TF\_Connection or TF\_Diag).</span></span> <span data-ttu-id="bd48a-107">提供者是每個 Lync Server 伺服器角色中可追蹤的元件。</span><span class="sxs-lookup"><span data-stu-id="bd48a-107">Providers are the traceable components in each Lync Server server role.</span></span> <span data-ttu-id="bd48a-108">使用提供者，您可以定義元件的追蹤層級與類型（例如，S4、SIPStack、IM 和目前狀態）。</span><span class="sxs-lookup"><span data-stu-id="bd48a-108">By using providers, you define the level and type of tracing on components (for example, S4, SIPStack, IM and Presence).</span></span> <span data-ttu-id="bd48a-109">已定義的提供者會在案例中用來針對特定的邏輯集合，針對特定的問題條件來分組所有提供者。</span><span class="sxs-lookup"><span data-stu-id="bd48a-109">The defined provider is used in a scenario to group all of the providers for a given logical collection that address a specific problem condition.</span></span>

<span data-ttu-id="bd48a-110">若要使用 Lync Server 管理命令介面執行集中式記錄服務功能，您必須是 CsAdministrator 或 CsServerAdministrator 角色式存取控制（RBAC）安全性群組的成員，或是包含下列其中一項的自訂 RBAC 角色：這兩個群組。</span><span class="sxs-lookup"><span data-stu-id="bd48a-110">To run the Centralized Logging Service functions using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="bd48a-111">若要傳回已指派這個 Cmdlet 的所有角色式存取控制（RBAC）角色的清單（包括您自行建立的任何自訂 RBAC 角色），請從 Lync Server 管理命令介面或 Windows PowerShell 提示字元執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="bd48a-111">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="bd48a-112">例如：</span><span class="sxs-lookup"><span data-stu-id="bd48a-112">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="bd48a-113">本主題的其餘部分將重點放在如何定義提供者、修改提供者以及提供者定義所包含的內容來優化您的疑難排解。</span><span class="sxs-lookup"><span data-stu-id="bd48a-113">The remainder of this topic focuses on how to define providers, modify a provider and what a provider definition contains to optimize your troubleshooting.</span></span> <span data-ttu-id="bd48a-114">有兩種方式可以發出集中式記錄服務命令。</span><span class="sxs-lookup"><span data-stu-id="bd48a-114">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="bd48a-115">在預設\\情況下，您可以使用 CLSController 中的 [目錄 C： Program files\\] （\\Microsoft Lync Server 2013\\CLSAgent）常見檔案。</span><span class="sxs-lookup"><span data-stu-id="bd48a-115">You can use the CLSController.exe that is located, by default, in the directory C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\CLSAgent.</span></span> <span data-ttu-id="bd48a-116">或者，您可以使用 Lync Server Management Shell 來頒發 Windows PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="bd48a-116">Or, you can use the Lync Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="bd48a-117">重要的區別是，當您在命令列中使用 CLSController 時，有一個有限的方案選擇，這些案例已定義且無法進行改變，但您可以定義記錄層級。</span><span class="sxs-lookup"><span data-stu-id="bd48a-117">The important distinction is that when you use CLSController.exe at the command line there is a finite selection of scenarios available in which the providers are already defined and are not changeable, but you can define the log level.</span></span> <span data-ttu-id="bd48a-118">使用 Windows PowerShell，您可以定義在記錄會話中使用的新提供者，並完全控制自己的建立、收集的內容，以及它們收集資料的層級。</span><span class="sxs-lookup"><span data-stu-id="bd48a-118">By using Windows PowerShell, you can define new providers for use in your logging sessions, and have complete control over their creation, what they collect, and at what level they collect data.</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="bd48a-119">如前文所述，提供者功能非常強大。</span><span class="sxs-lookup"><span data-stu-id="bd48a-119">As mentioned, providers are very powerful.</span></span> <span data-ttu-id="bd48a-120">不過，案例的功能更強大，因為它們包含在提供者所代表的元件上設定和執行追蹤所需的所有資訊的 embodiment。</span><span class="sxs-lookup"><span data-stu-id="bd48a-120">However, scenarios are more powerful because they contain the embodiment of all information needed to set and execute tracing on the components that the providers represent.</span></span> <span data-ttu-id="bd48a-121">隨著案例成為提供者集合，與執行的批次處理檔案相比，這可能是鬆散的，在命令列中，您可以使用包含上百個命令的批次檔案來收集大量的資訊，而不是一次發出一個命令。</span><span class="sxs-lookup"><span data-stu-id="bd48a-121">With scenarios being a collection of providers, this could be loosely compared to running a batch file containing hundreds of commands to collect a lot of information versus issuing hundreds of commands, one at a time, at the command line.</span></span><BR><span data-ttu-id="bd48a-122">[集中式記錄] 服務提供已為您定義的許多案例，而不是要求您深入瞭解提供者的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="bd48a-122">Instead of requiring you to dig deeply into the details of providers, the Centralized Logging Service provides a number of scenarios that are already defined for you.</span></span> <span data-ttu-id="bd48a-123">提供的案例涵蓋絕大多數您可能會遇到的問題。</span><span class="sxs-lookup"><span data-stu-id="bd48a-123">The provided scenarios cover the vast majority of possible issues that you will encounter.</span></span> <span data-ttu-id="bd48a-124">在少數情況下，您可能需要建立並定義提供者，並將其指派給案例。</span><span class="sxs-lookup"><span data-stu-id="bd48a-124">In rare cases, you may need to create and define providers and assign them to scenarios.</span></span> <span data-ttu-id="bd48a-125">我們強烈建議您先熟悉所提供的各個案例，然後再調查需要建立新的提供者和案例的需求。</span><span class="sxs-lookup"><span data-stu-id="bd48a-125">We strongly recommend that you become familiar with each of the scenarios provided before you investigate the need to create new providers and scenarios.</span></span> <span data-ttu-id="bd48a-126">您可以在這裡找到有關建立提供者的資訊，讓您熟悉案例如何使用提供者元素來收集追蹤資訊，目前不提供提供者本身的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="bd48a-126">While information about creating providers is found here to familiarize you with how the scenarios use the provider elements to collect trace information, details on the providers themselves are not provided at this time.</span></span>



</div>

<span data-ttu-id="bd48a-127">在[Lync Server 2013 中簡介集中式記錄服務](lync-server-2013-overview-of-the-centralized-logging-service.md)，定義案例中要使用之提供者的主要元素如下：</span><span class="sxs-lookup"><span data-stu-id="bd48a-127">Introduced in [Overview of the Centralized Logging Service in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), the key elements of defining a provider for use in a scenario are:</span></span>

  - <span data-ttu-id="bd48a-128">**提供者**   如果您熟悉 OCSLogger，提供者就是您選擇的元件，可告訴 OCSLogger 追蹤引擎應從哪個部分收集記錄。</span><span class="sxs-lookup"><span data-stu-id="bd48a-128">**Providers**   If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="bd48a-129">提供者是相同的元件，且在許多情況下，與 OCSLogger 中的元件名稱相同。</span><span class="sxs-lookup"><span data-stu-id="bd48a-129">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="bd48a-130">如果您不熟悉 OCSLogger，提供者是集中式記錄服務可以從中收集記錄的伺服器角色特定元件。</span><span class="sxs-lookup"><span data-stu-id="bd48a-130">If you are not familiar with OCSLogger, providers are server-role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="bd48a-131">在集中式記錄服務的情況下，CLSAgent 是集中式記錄服務的結構元件，可追蹤您在提供者配置中定義的元件。</span><span class="sxs-lookup"><span data-stu-id="bd48a-131">In the case of the Centralized Logging Service, the CLSAgent is the architectural part of the Centralized Logging Service that is doing the tracing of the components that you define in the providers configuration.</span></span>

  - <span data-ttu-id="bd48a-132">**記錄層級**   OCSLogger 提供的選項可為收集的資料選擇詳細層級。</span><span class="sxs-lookup"><span data-stu-id="bd48a-132">**Logging levels**   OCSLogger provided the option to choose a number of levels of detail for the data collected.</span></span> <span data-ttu-id="bd48a-133">這個功能是集中式記錄服務和案例的有機組成部分，且由**Type**參數定義。</span><span class="sxs-lookup"><span data-stu-id="bd48a-133">This feature is an integral part of the Centralized Logging Service and scenarios, and is defined by the **Type** parameter.</span></span> <span data-ttu-id="bd48a-134">您可以從下列選項中進行選擇：</span><span class="sxs-lookup"><span data-stu-id="bd48a-134">You can choose from the following:</span></span>
    
      - <span data-ttu-id="bd48a-135">**All**   會收集已定義提供者記錄中類型為致命、錯誤、警告及資訊的追蹤訊息。</span><span class="sxs-lookup"><span data-stu-id="bd48a-135">**All**   Collects trace messages of type fatal, error, warning, and info to the log for the defined provider.</span></span>
    
      - <span data-ttu-id="bd48a-136">**[致命**   ] 只會收集指出已定義的提供者失敗的追蹤訊息。</span><span class="sxs-lookup"><span data-stu-id="bd48a-136">**Fatal**   Collects only the trace messages that indicate a failure for the defined provider.</span></span>
    
      - <span data-ttu-id="bd48a-137">**錯誤**   ：只收集指出已定義之提供者的錯誤的追蹤訊息，以及致命的訊息。</span><span class="sxs-lookup"><span data-stu-id="bd48a-137">**Error**   Collects only the trace messages that indicate an error for the defined provider, plus fatal messages.</span></span>
    
      - <span data-ttu-id="bd48a-138">**警告**   ：只會收集指出已定義的提供者發出警告的追蹤訊息，以及致命及錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="bd48a-138">**Warning**   Collects only the trace messages that indicate a warning for the defined provider, plus fatal and error messages.</span></span>
    
      - <span data-ttu-id="bd48a-139">**[資訊**   ] 只會收集指出已定義提供者的資訊訊息的追蹤訊息，以及致命、錯誤和警告訊息。</span><span class="sxs-lookup"><span data-stu-id="bd48a-139">**Info**   Collects only the trace messages that indicate an informational message for the defined provider, plus fatal, error, and warning messages.</span></span>
    
      - <span data-ttu-id="bd48a-140">**詳細**   收集已定義提供者的所有類型為致命、錯誤、警告及資訊的追蹤訊息。</span><span class="sxs-lookup"><span data-stu-id="bd48a-140">**Verbose**   Collects all trace messages of type fatal, error, warning and info for the defined provider.</span></span>

  - <span data-ttu-id="bd48a-141">**旗標**   OCSLogger 提供選項，為每個提供者選擇一個定義您可以從追蹤檔案中檢索之資訊類型的提供者。</span><span class="sxs-lookup"><span data-stu-id="bd48a-141">**Flags**   OCSLogger provided the option to choose flags for each provider that defined what type of information you could retrieve from the trace files.</span></span> <span data-ttu-id="bd48a-142">您可以根據提供者選擇下列標誌：</span><span class="sxs-lookup"><span data-stu-id="bd48a-142">You can chose the following flags, based on the provider:</span></span>
    
      - <span data-ttu-id="bd48a-143">**TF\_** 連線   提供與連接相關的記錄專案。</span><span class="sxs-lookup"><span data-stu-id="bd48a-143">**TF\_Connection**   Provides connection-related log entries.</span></span> <span data-ttu-id="bd48a-144">這些記錄包含與特定元件建立的連線的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="bd48a-144">These logs include information about connections established to and from a particular component.</span></span> <span data-ttu-id="bd48a-145">這也可能包含大量的網路層級資訊（也就是不含連線概念的元件）。</span><span class="sxs-lookup"><span data-stu-id="bd48a-145">This may also include significant network-level information (that is, for components without the concept of a connection).</span></span>
    
      - <span data-ttu-id="bd48a-146">**TF\_security**   會提供與安全性有關的所有事件/記錄專案。</span><span class="sxs-lookup"><span data-stu-id="bd48a-146">**TF\_Security**   Provides all events/log entries related to security.</span></span> <span data-ttu-id="bd48a-147">例如，在 SipStack 中，這些是安全事件，例如網域驗證失敗，以及用戶端驗證/授權失敗。</span><span class="sxs-lookup"><span data-stu-id="bd48a-147">For example, for SipStack, these are security events such as domain validation failure, and client authentication/authorization failures.</span></span>
    
      - <span data-ttu-id="bd48a-148">**TF\_** diagnostics   提供診斷事件，可供您用來診斷元件或對元件進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="bd48a-148">**TF\_Diag**   Provides diagnostics events that you can use to diagnose or troubleshoot the component.</span></span> <span data-ttu-id="bd48a-149">例如，在 SipStack 中，這些是證書失敗，或 DNS 警告/錯誤。</span><span class="sxs-lookup"><span data-stu-id="bd48a-149">For example, for SipStack, these are certificate failures, or DNS warnings/errors.</span></span>
    
      - <span data-ttu-id="bd48a-150">**TF\_protocol**   提供通訊協定，例如 SIP 及組合的群組編解碼器套件訊息。</span><span class="sxs-lookup"><span data-stu-id="bd48a-150">**TF\_Protocol**   Provides protocol messages such as SIP and Combined Community Codec Pack messages.</span></span>
    
      - <span data-ttu-id="bd48a-151">**TF\_元件**   可讓您登入指定為提供者一部分的元件。</span><span class="sxs-lookup"><span data-stu-id="bd48a-151">**TF\_Component**   Enables logging on the components specified as part of the providers.</span></span>
    
      - <span data-ttu-id="bd48a-152">**[全部**   ] 會設定提供者可用的所有可用旗標。</span><span class="sxs-lookup"><span data-stu-id="bd48a-152">**All**   Sets all available flags available for the provider.</span></span>

<div>

## <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a><span data-ttu-id="bd48a-153">若要查看現有集中式記錄服務案例提供者的相關資訊</span><span class="sxs-lookup"><span data-stu-id="bd48a-153">To review information about existing Centralized Logging Service scenario providers</span></span>

1.  <span data-ttu-id="bd48a-154">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="bd48a-154">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="bd48a-155">若要查看現有提供者的設定，請輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="bd48a-155">To review the configuration of existing providers, type the following:</span></span>
    
        Get-CsClsScenario -Identity <scope and scenario name> 
    
    <span data-ttu-id="bd48a-156">例如，若要查看全域會議助理的相關資訊，請輸入：</span><span class="sxs-lookup"><span data-stu-id="bd48a-156">For example, to review information about the global conferencing attendant, type:</span></span>
    
        Get-CsClsScenario -Identity "global/CAA"
    
    <span data-ttu-id="bd48a-157">該命令會顯示包含相關聯標誌、設定和元件的提供者清單。</span><span class="sxs-lookup"><span data-stu-id="bd48a-157">The command displays a list of providers with the associated flags, settings, and components.</span></span> <span data-ttu-id="bd48a-158">如果顯示的資訊不足，或者清單對於預設的 Windows PowerShell 清單格式而言太長，您可以透過定義不同的輸出方法來顯示其他資訊。</span><span class="sxs-lookup"><span data-stu-id="bd48a-158">If the information displayed is not enough or the list is too long for the default Windows PowerShell list format, you can display additional information by defining a different output method.</span></span> <span data-ttu-id="bd48a-159">若要這樣做，請輸入：</span><span class="sxs-lookup"><span data-stu-id="bd48a-159">To do this, type:</span></span>
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    <span data-ttu-id="bd48a-160">這個命令的輸出會以五行格式顯示每個提供者，其中包含提供者名稱、記錄類型、記錄層級、旗標、GUID 和角色，每個提供者都在個別的行上。</span><span class="sxs-lookup"><span data-stu-id="bd48a-160">The output of this command displays each provider displayed in a five line format with the provider name, type of logging, logging level, flags, GUID, and role, each one on a separate line.</span></span>

</div>

<div>

## <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a><span data-ttu-id="bd48a-161">定義新的集中式記錄服務案例提供者</span><span class="sxs-lookup"><span data-stu-id="bd48a-161">To define a new Centralized Logging Service scenario provider</span></span>

1.  <span data-ttu-id="bd48a-162">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="bd48a-162">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="bd48a-163">案例提供者包含要追蹤的元件、要使用的旗標，以及要收集的詳細資料層級。</span><span class="sxs-lookup"><span data-stu-id="bd48a-163">A scenario provider consists of a component to trace, flags to use, and a level of detail to collect.</span></span> <span data-ttu-id="bd48a-164">若要執行此動作，請輸入：</span><span class="sxs-lookup"><span data-stu-id="bd48a-164">You do this by typing:</span></span>
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    <span data-ttu-id="bd48a-165">例如，[追蹤提供者] 定義定義要收集哪些內容，以及從 Lyss 提供者的詳細資料層級看起來如下：</span><span class="sxs-lookup"><span data-stu-id="bd48a-165">For example, a trace provider definition that defines what to collect and to what level of detail from the Lyss provider looks like the following:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

<span data-ttu-id="bd48a-166">– Level 會收集致命、錯誤、警告及資訊訊息。</span><span class="sxs-lookup"><span data-stu-id="bd48a-166">The –Level collects fatal, error, warning, and information messages.</span></span> <span data-ttu-id="bd48a-167">所使用的標誌全都是為 Lyss 提供者所定義的，並且包含\_tf CONNECTION、\_tf 診斷和\_TF 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="bd48a-167">The flags used are all of those defined for the Lyss provider, and include TF\_Connection, TF\_Diag and TF\_Protocol.</span></span>

<span data-ttu-id="bd48a-168">在定義 $LyssProvider 變數之後，您可以將它與**新的-CsClsScenario** Cmdlet 搭配使用，以從 Lyss 提供者收集蹤跡。</span><span class="sxs-lookup"><span data-stu-id="bd48a-168">After the variable $LyssProvider is defined, you can use it with the **New-CsClsScenario** cmdlet to collect traces from the Lyss provider.</span></span> <span data-ttu-id="bd48a-169">若要完成建立並將提供者指派給新的案例，請輸入：</span><span class="sxs-lookup"><span data-stu-id="bd48a-169">To complete the creation and assignment of the provider to a new scenario, type:</span></span>

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

<span data-ttu-id="bd48a-170">其中 $LyssProvider 是包含使用**新 CsClsProvider**建立之已定義之案例的變數。</span><span class="sxs-lookup"><span data-stu-id="bd48a-170">Where $LyssProvider is the variable containing the defined scenario created with **New-CsClsProvider**.</span></span>

</div>

<div>

## <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a><span data-ttu-id="bd48a-171">變更現有的集中式記錄服務案例提供者</span><span class="sxs-lookup"><span data-stu-id="bd48a-171">To change an existing Centralized Logging Service scenario provider</span></span>

1.  <span data-ttu-id="bd48a-172">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="bd48a-172">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="bd48a-173">若要更新或變更現有提供者的設定，請輸入：</span><span class="sxs-lookup"><span data-stu-id="bd48a-173">To update or change the configuration of an existing provider, type:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
    
    <span data-ttu-id="bd48a-174">然後，您可以輸入下列內容來更新案例以指派提供者：</span><span class="sxs-lookup"><span data-stu-id="bd48a-174">You then update the scenario to assign the provider by typing the following:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

<span data-ttu-id="bd48a-175">此命令的最終結果是案例網站： [雷德蒙]/[RedmondLyssInfo] 會針對指派給它的提供者更新旗標和層級。</span><span class="sxs-lookup"><span data-stu-id="bd48a-175">The end result of the command is that the scenario site:Redmond/RedmondLyssInfo will have updated flags and level for the provider assigned to it.</span></span> <span data-ttu-id="bd48a-176">您可以使用 [取得 CsClsScenario] 來查看新案例。</span><span class="sxs-lookup"><span data-stu-id="bd48a-176">You can view the new scenario by using Get-CsClsScenario.</span></span> <span data-ttu-id="bd48a-177">如需詳細資訊，請參閱[CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)。</span><span class="sxs-lookup"><span data-stu-id="bd48a-177">For details, see [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario).</span></span>

<div class="">


> [!WARNING]  
> <span data-ttu-id="bd48a-178"><STRONG>新的-ClsCsProvider</STRONG>不會檢查以判斷旗標是否有效。</span><span class="sxs-lookup"><span data-stu-id="bd48a-178"><STRONG>New-ClsCsProvider</STRONG> does not check to determine whether the flags are valid.</span></span> <span data-ttu-id="bd48a-179">請確定旗標（例如 TF_DIAG 或 TF_CONNECTION）拼寫正確無誤。</span><span class="sxs-lookup"><span data-stu-id="bd48a-179">Make sure that the spelling of the flags (for example, TF_DIAG or TF_CONNECTION) is spelled correctly.</span></span> <span data-ttu-id="bd48a-180">如果旗標沒有正確拼寫，提供者就無法傳回預期的記錄資訊。</span><span class="sxs-lookup"><span data-stu-id="bd48a-180">If the flags are not spelled correctly, the provider cannot return the expected log information.</span></span>



</div>

<span data-ttu-id="bd48a-181">如果您想要在此案例中新增其他提供者，請輸入下列專案：</span><span class="sxs-lookup"><span data-stu-id="bd48a-181">If you want to add additional providers to this scenario, type the following:</span></span>

    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}

<span data-ttu-id="bd48a-182">每個使用 Add 指令定義的提供者，都已使用**新的-CsClsProvider**程式進行定義。</span><span class="sxs-lookup"><span data-stu-id="bd48a-182">Where each provider defined with the Add directive has already been defined using the **New-CsClsProvider** process.</span></span>

</div>

<div>

## <a name="to-remove-a-scenario-provider"></a><span data-ttu-id="bd48a-183">移除案例提供者</span><span class="sxs-lookup"><span data-stu-id="bd48a-183">To remove a scenario provider</span></span>

1.  <span data-ttu-id="bd48a-184">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="bd48a-184">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="bd48a-185">提供的 Cmdlet 可讓您更新現有的提供者，並建立新的提供者。</span><span class="sxs-lookup"><span data-stu-id="bd48a-185">The cmdlets provided allow you to update existing providers and create new providers.</span></span> <span data-ttu-id="bd48a-186">若要移除提供者，您必須使用提供者參數的 Replace 指令來**設定-CsClsScenario**。</span><span class="sxs-lookup"><span data-stu-id="bd48a-186">To remove a provider, you must use the Replace directive for the Provider parameter to **Set-CsClsScenario**.</span></span> <span data-ttu-id="bd48a-187">完全移除提供者的唯一方式是將它替換成相同名稱的重新定義提供者，並使用 Update 指令。</span><span class="sxs-lookup"><span data-stu-id="bd48a-187">The only way to completely remove a provider is to replace it with a redefined provider of the same name and use the Update directive.</span></span> <span data-ttu-id="bd48a-188">例如，我們的提供者 LyssProvider 定義了 WPP 作為記錄類型、將層級設為 Debug，以及旗標與\_TF （tf\_）的組合。</span><span class="sxs-lookup"><span data-stu-id="bd48a-188">For example, our provider LyssProvider is defined with WPP as the log type, level set to Debug, and flags set are TF\_CONNECTION and TF\_DIAG.</span></span> <span data-ttu-id="bd48a-189">您必須將 [旗標] 變更為 [全部]。</span><span class="sxs-lookup"><span data-stu-id="bd48a-189">You need to change the flags to “All”.</span></span> <span data-ttu-id="bd48a-190">若要變更提供者，請輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="bd48a-190">To change the provider, type the following:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"

     &nbsp;
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}

3.  <span data-ttu-id="bd48a-191">如果您想要完全移除某個案例，以及與其相關聯的提供者，請輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="bd48a-191">If you want to completely remove a scenario and the providers associated with it, type the following:</span></span>
    
        Remove-CsClsScenario -Identity <scope and name of scenario>
    
    <span data-ttu-id="bd48a-192">例如：</span><span class="sxs-lookup"><span data-stu-id="bd48a-192">For example:</span></span>
    
        Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
    
    <div class="">
    

    > [!WARNING]  
    > <span data-ttu-id="bd48a-193">Cmdlet<STRONG>移除-CsClsScenario</STRONG>不會提示您進行確認。</span><span class="sxs-lookup"><span data-stu-id="bd48a-193">The cmdlet <STRONG>Remove-CsClsScenario</STRONG> does not prompt you for confirmation.</span></span> <span data-ttu-id="bd48a-194">隨後會刪除該案例，以及已指派給它的提供者。</span><span class="sxs-lookup"><span data-stu-id="bd48a-194">The scenario is deleted, along with the providers that were assigned to it.</span></span> <span data-ttu-id="bd48a-195">您可以重新執行用來建立該案例的命令來重新建立。</span><span class="sxs-lookup"><span data-stu-id="bd48a-195">You can recreate the scenario by re-running the commands used to create it initially.</span></span> <span data-ttu-id="bd48a-196">沒有復原已移除之案例或提供者的程式。</span><span class="sxs-lookup"><span data-stu-id="bd48a-196">There is no procedure to recover removed scenarios or providers.</span></span>

    
    </div>

<span data-ttu-id="bd48a-197">當您使用**CsClsScenario** Cmdlet 移除案例時，您會完全移除範圍中的案例。</span><span class="sxs-lookup"><span data-stu-id="bd48a-197">When you remove a scenario by using the **Remove-CsClsScenario** cmdlet, you completely remove the scenario from the scope.</span></span> <span data-ttu-id="bd48a-198">若要使用您所建立的案例，以及該案例中的提供者，您可以建立新的提供者，並將它們指派給新的案例。</span><span class="sxs-lookup"><span data-stu-id="bd48a-198">To use the scenarios that you created and the providers that were a part of the scenario, you create new providers and assign them to a new scenario.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bd48a-199">請參閱</span><span class="sxs-lookup"><span data-stu-id="bd48a-199">See Also</span></span>


[<span data-ttu-id="bd48a-200">CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="bd48a-200">Get-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)  
[<span data-ttu-id="bd48a-201">新-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="bd48a-201">New-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClsScenario)  
[<span data-ttu-id="bd48a-202">移除-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="bd48a-202">Remove-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsClsScenario)  
[<span data-ttu-id="bd48a-203">Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="bd48a-203">Set-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario)  
[<span data-ttu-id="bd48a-204">新-CsClsProvider</span><span class="sxs-lookup"><span data-stu-id="bd48a-204">New-CsClsProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

