---
title: Lync Server 2013：設定集中式記錄服務的提供者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring providers for Centralized Logging Service
ms:assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688082(v=OCS.15)
ms:contentKeyID: 49733678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec5d280d05089c4f1efc4fd8c54ab4841d24621d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535000"
---
# <a name="configuring-providers-for-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="a13d6-102">在 Lync Server 2013 中設定集中式記錄服務的提供者</span><span class="sxs-lookup"><span data-stu-id="a13d6-102">Configuring providers for Centralized Logging Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a13d6-103">_**主題上次修改日期：** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="a13d6-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="a13d6-104">集中式記錄服務中 *提供者* 的概念和設定是最重要的一點。</span><span class="sxs-lookup"><span data-stu-id="a13d6-104">The concepts and configuration of *providers* in Centralized Logging Service is one of the most important to grasp.</span></span> <span data-ttu-id="a13d6-105">*提供者*會直接對應至 lync server 追蹤模型中的 lync server server 角色元件。</span><span class="sxs-lookup"><span data-stu-id="a13d6-105">The *providers* map directly to Lync Server server role components in the Lync Server tracing model.</span></span> <span data-ttu-id="a13d6-106">提供者會定義將要追蹤的 Lync Server 2013 元件、郵件類型 (例如，要收集的郵件類型、嚴重、錯誤、警告) ，以及旗標 (例如 TF \_ Connection 或 tf the \_) 。</span><span class="sxs-lookup"><span data-stu-id="a13d6-106">The provider defines the components of a Lync Server 2013 that will be traced, the type of messages (for example, fatal, error, or warning) to collect, and the flags (for example, TF\_Connection or TF\_Diag).</span></span> <span data-ttu-id="a13d6-107">提供者是每個 Lync Server server role 中可追蹤的元件。</span><span class="sxs-lookup"><span data-stu-id="a13d6-107">Providers are the traceable components in each Lync Server server role.</span></span> <span data-ttu-id="a13d6-108">藉由使用提供者，可讓您定義在元件上追蹤的層級和類型 (例如 S4、SIPStack、IM 和目前狀態)。</span><span class="sxs-lookup"><span data-stu-id="a13d6-108">By using providers, you define the level and type of tracing on components (for example, S4, SIPStack, IM and Presence).</span></span> <span data-ttu-id="a13d6-109">定義的提供者會用於案例中，以針對處理特定問題狀況的某個邏輯集合來對所有提供者進行分組。</span><span class="sxs-lookup"><span data-stu-id="a13d6-109">The defined provider is used in a scenario to group all of the providers for a given logical collection that address a specific problem condition.</span></span>

<span data-ttu-id="a13d6-110">若要使用 Lync Server 管理命令介面來執行集中式記錄服務功能，您必須是 CsAdministrator 或 CsServerAdministrator 角色型存取控制 (RBAC) 安全性群組的成員，或是包含這兩個群組之一的自訂 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="a13d6-110">To run the Centralized Logging Service functions using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="a13d6-111">若要傳回所有角色型存取控制的清單 (RBAC) role 此 Cmdlet 已指派給 (包括您) 自行建立的任何自訂 RBAC 角色，請從 [Lync Server 管理命令介面] 或 [Windows PowerShell] 提示字元執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="a13d6-111">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="a13d6-112">例如：</span><span class="sxs-lookup"><span data-stu-id="a13d6-112">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="a13d6-113">本主題的其餘內容將特別針對定義提供者、修改提供者的方式，及提供者定義所包含的內容做討論，以使您的疑難排解作業獲得最佳成效。</span><span class="sxs-lookup"><span data-stu-id="a13d6-113">The remainder of this topic focuses on how to define providers, modify a provider and what a provider definition contains to optimize your troubleshooting.</span></span> <span data-ttu-id="a13d6-114">有兩種方式可發出集中式記錄服務命令。</span><span class="sxs-lookup"><span data-stu-id="a13d6-114">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="a13d6-115">在下列目錄中，您可以使用 \\ \\ \\ Microsoft Lync Server 2013 CLSAgent 中的目錄 C： Program Files 通用檔案中所 CLSController.exe 的預設值 \\ 。</span><span class="sxs-lookup"><span data-stu-id="a13d6-115">You can use the CLSController.exe that is located, by default, in the directory C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\CLSAgent.</span></span> <span data-ttu-id="a13d6-116">或者，您可以使用 Lync Server 管理命令介面來發出 Windows PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="a13d6-116">Or, you can use the Lync Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="a13d6-117">其中重要區別在於，當您在命令列上使用 CLSController.exe 時，選擇會侷限於提供者已定義好而無法變更的可用案例中，但您可以定義記錄層級。</span><span class="sxs-lookup"><span data-stu-id="a13d6-117">The important distinction is that when you use CLSController.exe at the command line there is a finite selection of scenarios available in which the providers are already defined and are not changeable, but you can define the log level.</span></span> <span data-ttu-id="a13d6-118">使用 Windows PowerShell，您可以定義在記錄會話中使用的新提供者，並對其建立、他們收集的內容，以及收集資料的層級有完全的控制權。</span><span class="sxs-lookup"><span data-stu-id="a13d6-118">By using Windows PowerShell, you can define new providers for use in your logging sessions, and have complete control over their creation, what they collect, and at what level they collect data.</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="a13d6-p104">如前所述，提供者的功能強大。不過，案例的作用卻更為強大，因為它們包含全部所需具體資訊，可用以在提供者代表的元件上設定和執行追蹤作業。若與做為提供者集合的案例進行約略比較，它就像執行包含數百個命令的批次檔，可用來收集大量資訊，而非在命令列上以一次一個的方式發行數百個命令。</span><span class="sxs-lookup"><span data-stu-id="a13d6-p104">As mentioned, providers are very powerful. However, scenarios are more powerful because they contain the embodiment of all information needed to set and execute tracing on the components that the providers represent. With scenarios being a collection of providers, this could be loosely compared to running a batch file containing hundreds of commands to collect a lot of information versus issuing hundreds of commands, one at a time, at the command line.</span></span><BR><span data-ttu-id="a13d6-122">集中式記錄服務會提供許多已經為您定義的案例，而不需要您深入瞭解提供者的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a13d6-122">Instead of requiring you to dig deeply into the details of providers, the Centralized Logging Service provides a number of scenarios that are already defined for you.</span></span> <span data-ttu-id="a13d6-123">所提供的案例涵蓋您可能會遭遇的絕大多數問題。</span><span class="sxs-lookup"><span data-stu-id="a13d6-123">The provided scenarios cover the vast majority of possible issues that you will encounter.</span></span> <span data-ttu-id="a13d6-124">在一些罕見的情況下，您可能需建立並定義提供者，並將其指派給案例。</span><span class="sxs-lookup"><span data-stu-id="a13d6-124">In rare cases, you may need to create and define providers and assign them to scenarios.</span></span> <span data-ttu-id="a13d6-125">我們強烈建議您在調查需求以建立新提供者和案例前，先熟悉所提供的每個案例。</span><span class="sxs-lookup"><span data-stu-id="a13d6-125">We strongly recommend that you become familiar with each of the scenarios provided before you investigate the need to create new providers and scenarios.</span></span> <span data-ttu-id="a13d6-126">您可在這裡找到建立提供者的資訊，以熟悉案例使用提供者元素收集追蹤資訊的方式，而此時並不會提供提供者本身的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a13d6-126">While information about creating providers is found here to familiarize you with how the scenarios use the provider elements to collect trace information, details on the providers themselves are not provided at this time.</span></span>



</div>

<span data-ttu-id="a13d6-127">簡介：在 [Lync Server 2013 中引入集中式記錄服務](lync-server-2013-overview-of-the-centralized-logging-service.md)，定義提供者以用於案例中的主要元素包括：</span><span class="sxs-lookup"><span data-stu-id="a13d6-127">Introduced in [Overview of the Centralized Logging Service in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), the key elements of defining a provider for use in a scenario are:</span></span>

  - <span data-ttu-id="a13d6-128">**提供者**    如果您熟悉 OCSLogger，提供者就是您所選擇的元件，以告知 OCSLogger 追蹤引擎應從何處收集記錄。</span><span class="sxs-lookup"><span data-stu-id="a13d6-128">**Providers**   If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="a13d6-129">提供者是相同的元件，在許多情況下，與 OCSLogger 中的元件具有相同的名稱。</span><span class="sxs-lookup"><span data-stu-id="a13d6-129">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="a13d6-130">如果您不熟悉 OCSLogger，提供者是集中式記錄服務可從中收集記錄的伺服器角色特定元件。</span><span class="sxs-lookup"><span data-stu-id="a13d6-130">If you are not familiar with OCSLogger, providers are server-role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="a13d6-131">在集中式記錄服務的情況下，CLSAgent 是集中式記錄服務的架構元件，它會執行您在提供者設定中所定義的元件追蹤。</span><span class="sxs-lookup"><span data-stu-id="a13d6-131">In the case of the Centralized Logging Service, the CLSAgent is the architectural part of the Centralized Logging Service that is doing the tracing of the components that you define in the providers configuration.</span></span>

  - <span data-ttu-id="a13d6-132">**記錄層級**    OCSLogger 提供選擇所收集資料的詳細資料層級的選項。</span><span class="sxs-lookup"><span data-stu-id="a13d6-132">**Logging levels**   OCSLogger provided the option to choose a number of levels of detail for the data collected.</span></span> <span data-ttu-id="a13d6-133">這項功能是集中式記錄服務和案例中不可或缺的一部分，並由 **Type** 參數定義。</span><span class="sxs-lookup"><span data-stu-id="a13d6-133">This feature is an integral part of the Centralized Logging Service and scenarios, and is defined by the **Type** parameter.</span></span> <span data-ttu-id="a13d6-134">您可以選擇下列項目：</span><span class="sxs-lookup"><span data-stu-id="a13d6-134">You can choose from the following:</span></span>
    
      - <span data-ttu-id="a13d6-135">**全部**    針對已定義的提供者，將類型為嚴重、錯誤、警告和資訊的追蹤訊息收集到記錄檔。</span><span class="sxs-lookup"><span data-stu-id="a13d6-135">**All**   Collects trace messages of type fatal, error, warning, and info to the log for the defined provider.</span></span>
    
      - <span data-ttu-id="a13d6-136">**致命**    只收集指出定義的提供者失敗的追蹤訊息。</span><span class="sxs-lookup"><span data-stu-id="a13d6-136">**Fatal**   Collects only the trace messages that indicate a failure for the defined provider.</span></span>
    
      - <span data-ttu-id="a13d6-137">**錯誤**    只收集指出已定義提供者的錯誤的追蹤訊息，以及致命的訊息。</span><span class="sxs-lookup"><span data-stu-id="a13d6-137">**Error**   Collects only the trace messages that indicate an error for the defined provider, plus fatal messages.</span></span>
    
      - <span data-ttu-id="a13d6-138">**警告**    只收集表示已定義提供者的警告的追蹤訊息，以及致命錯誤和錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="a13d6-138">**Warning**   Collects only the trace messages that indicate a warning for the defined provider, plus fatal and error messages.</span></span>
    
      - <span data-ttu-id="a13d6-139">**資訊**    只收集表明已定義的提供者的資訊訊息的追蹤訊息，加上嚴重、錯誤和警告訊息。</span><span class="sxs-lookup"><span data-stu-id="a13d6-139">**Info**   Collects only the trace messages that indicate an informational message for the defined provider, plus fatal, error, and warning messages.</span></span>
    
      - <span data-ttu-id="a13d6-140">**Verbose**    針對已定義的提供者，收集類型為嚴重、錯誤、警告和資訊的所有追蹤訊息。</span><span class="sxs-lookup"><span data-stu-id="a13d6-140">**Verbose**   Collects all trace messages of type fatal, error, warning and info for the defined provider.</span></span>

  - <span data-ttu-id="a13d6-141">**旗標**    OCSLogger 提供的選項可為定義您從追蹤檔案中取得的資訊類型的每個提供者選擇旗標。</span><span class="sxs-lookup"><span data-stu-id="a13d6-141">**Flags**   OCSLogger provided the option to choose flags for each provider that defined what type of information you could retrieve from the trace files.</span></span> <span data-ttu-id="a13d6-142">您可以依據提供者選擇下列旗標：</span><span class="sxs-lookup"><span data-stu-id="a13d6-142">You can chose the following flags, based on the provider:</span></span>
    
      - <span data-ttu-id="a13d6-143">**TF \_Connection**     提供連線相關的記錄專案。</span><span class="sxs-lookup"><span data-stu-id="a13d6-143">**TF\_Connection**   Provides connection-related log entries.</span></span> <span data-ttu-id="a13d6-144">這些記錄檔包含與特定元件建立之連接的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a13d6-144">These logs include information about connections established to and from a particular component.</span></span> <span data-ttu-id="a13d6-145">這也可能包括大量的網路層級資訊 (，也就是針對不含 connection) 概念的元件。</span><span class="sxs-lookup"><span data-stu-id="a13d6-145">This may also include significant network-level information (that is, for components without the concept of a connection).</span></span>
    
      - <span data-ttu-id="a13d6-146">**TF \_安全性**     提供所有與安全性相關的事件/記錄專案。</span><span class="sxs-lookup"><span data-stu-id="a13d6-146">**TF\_Security**   Provides all events/log entries related to security.</span></span> <span data-ttu-id="a13d6-147">例如，針對 SipStack，這些是安全性事件，例如網域驗證失敗，以及用戶端驗證/授權失敗。</span><span class="sxs-lookup"><span data-stu-id="a13d6-147">For example, for SipStack, these are security events such as domain validation failure, and client authentication/authorization failures.</span></span>
    
      - <span data-ttu-id="a13d6-148">**TF \_診斷**     程式提供診斷事件，可供您用來診斷或疑難排解元件。</span><span class="sxs-lookup"><span data-stu-id="a13d6-148">**TF\_Diag**   Provides diagnostics events that you can use to diagnose or troubleshoot the component.</span></span> <span data-ttu-id="a13d6-149">例如，針對 SipStack，這些是憑證失敗或 DNS 警告/錯誤。</span><span class="sxs-lookup"><span data-stu-id="a13d6-149">For example, for SipStack, these are certificate failures, or DNS warnings/errors.</span></span>
    
      - <span data-ttu-id="a13d6-150">**TF \_通訊協定**     提供通訊協定和組合的群組編解碼器封包訊息。</span><span class="sxs-lookup"><span data-stu-id="a13d6-150">**TF\_Protocol**   Provides protocol messages such as SIP and Combined Community Codec Pack messages.</span></span>
    
      - <span data-ttu-id="a13d6-151">**TF \_元件**     可對指定為提供者一部分的元件進行記錄。</span><span class="sxs-lookup"><span data-stu-id="a13d6-151">**TF\_Component**   Enables logging on the components specified as part of the providers.</span></span>
    
      - <span data-ttu-id="a13d6-152">**全部**    設定提供者可使用的所有可用旗標。</span><span class="sxs-lookup"><span data-stu-id="a13d6-152">**All**   Sets all available flags available for the provider.</span></span>

<div>

## <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a><span data-ttu-id="a13d6-153">若要查看現有集中式記錄服務案例提供者的相關資訊</span><span class="sxs-lookup"><span data-stu-id="a13d6-153">To review information about existing Centralized Logging Service scenario providers</span></span>

1.  <span data-ttu-id="a13d6-154">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="a13d6-154">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a13d6-155">若要檢視現有提供者的設定，請輸入下列項目：</span><span class="sxs-lookup"><span data-stu-id="a13d6-155">To review the configuration of existing providers, type the following:</span></span>
    
        Get-CsClsScenario -Identity <scope and scenario name> 
    
    <span data-ttu-id="a13d6-156">例如，若要檢視全域會議服務員的資訊，請輸入：</span><span class="sxs-lookup"><span data-stu-id="a13d6-156">For example, to review information about the global conferencing attendant, type:</span></span>
    
        Get-CsClsScenario -Identity "global/CAA"
    
    <span data-ttu-id="a13d6-157">命令會顯示內含相關旗標、設定和元件的提供者清單。</span><span class="sxs-lookup"><span data-stu-id="a13d6-157">The command displays a list of providers with the associated flags, settings, and components.</span></span> <span data-ttu-id="a13d6-158">如果顯示的資訊不夠，或是預設 Windows PowerShell 清單格式的清單過長，您可以透過定義不同的輸出方法來顯示其他資訊。</span><span class="sxs-lookup"><span data-stu-id="a13d6-158">If the information displayed is not enough or the list is too long for the default Windows PowerShell list format, you can display additional information by defining a different output method.</span></span> <span data-ttu-id="a13d6-159">若要進行這項作業，請輸入：</span><span class="sxs-lookup"><span data-stu-id="a13d6-159">To do this, type:</span></span>
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    <span data-ttu-id="a13d6-160">此命令的輸出會以五行的格式顯示每名提供者，其中包含提供者名稱、記錄類型、記錄層次、旗標、GUID 和角色，每個項目位於個別一行。</span><span class="sxs-lookup"><span data-stu-id="a13d6-160">The output of this command displays each provider displayed in a five line format with the provider name, type of logging, logging level, flags, GUID, and role, each one on a separate line.</span></span>

</div>

<div>

## <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a><span data-ttu-id="a13d6-161">若要定義新的集中式記錄服務案例提供者</span><span class="sxs-lookup"><span data-stu-id="a13d6-161">To define a new Centralized Logging Service scenario provider</span></span>

1.  <span data-ttu-id="a13d6-162">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="a13d6-162">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a13d6-p113">案例提供者是由待追蹤的元件、要使用的旗標和收集的詳細資料等級所組成。若要進行這項作業，請輸入：</span><span class="sxs-lookup"><span data-stu-id="a13d6-p113">A scenario provider consists of a component to trace, flags to use, and a level of detail to collect. You do this by typing:</span></span>
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    <span data-ttu-id="a13d6-165">例如，追蹤提供者的定義會定義收集的項目及來自如下所示之 Lyss 提供者的詳細資料層級：</span><span class="sxs-lookup"><span data-stu-id="a13d6-165">For example, a trace provider definition that defines what to collect and to what level of detail from the Lyss provider looks like the following:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

<span data-ttu-id="a13d6-166">–Level 會收集嚴重、錯誤、警告和資訊訊息。</span><span class="sxs-lookup"><span data-stu-id="a13d6-166">The –Level collects fatal, error, warning, and information messages.</span></span> <span data-ttu-id="a13d6-167">使用的旗標全都為 Lyss 提供者所定義，並包含 TF \_ Connection、tf \_ 診斷和 TF \_ Protocol。</span><span class="sxs-lookup"><span data-stu-id="a13d6-167">The flags used are all of those defined for the Lyss provider, and include TF\_Connection, TF\_Diag and TF\_Protocol.</span></span>

<span data-ttu-id="a13d6-168">在定義變數 $LyssProvider 之後，您可以透過 **New-CsClsScenario** Cmdlet 加以使用，以便收集來自 Lyss 提供者的追蹤。</span><span class="sxs-lookup"><span data-stu-id="a13d6-168">After the variable $LyssProvider is defined, you can use it with the **New-CsClsScenario** cmdlet to collect traces from the Lyss provider.</span></span> <span data-ttu-id="a13d6-169">若要完成建立提供者，或將其指派給新案例，請輸入：</span><span class="sxs-lookup"><span data-stu-id="a13d6-169">To complete the creation and assignment of the provider to a new scenario, type:</span></span>

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

<span data-ttu-id="a13d6-170">當中的 $LyssProvider 是變數，其中包含與 **New-CsClsProvider** 一起建立之已定義的案例。</span><span class="sxs-lookup"><span data-stu-id="a13d6-170">Where $LyssProvider is the variable containing the defined scenario created with **New-CsClsProvider**.</span></span>

</div>

<div>

## <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a><span data-ttu-id="a13d6-171">變更現有的集中式記錄服務案例提供者</span><span class="sxs-lookup"><span data-stu-id="a13d6-171">To change an existing Centralized Logging Service scenario provider</span></span>

1.  <span data-ttu-id="a13d6-172">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="a13d6-172">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a13d6-173">若要更新或變更現有提供者的設定，請輸入：</span><span class="sxs-lookup"><span data-stu-id="a13d6-173">To update or change the configuration of an existing provider, type:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
    
    <span data-ttu-id="a13d6-174">然後您可輸入下列項目來更新案例，以指派提供者：</span><span class="sxs-lookup"><span data-stu-id="a13d6-174">You then update the scenario to assign the provider by typing the following:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

<span data-ttu-id="a13d6-175">命令的最終結果是，案例 site:Redmond/RedmondLyssInfo 會有更新的旗標和層級供指派給案例的提供者使用。</span><span class="sxs-lookup"><span data-stu-id="a13d6-175">The end result of the command is that the scenario site:Redmond/RedmondLyssInfo will have updated flags and level for the provider assigned to it.</span></span> <span data-ttu-id="a13d6-176">您可以使用 Get-CsClsScenario 檢視新案例。</span><span class="sxs-lookup"><span data-stu-id="a13d6-176">You can view the new scenario by using Get-CsClsScenario.</span></span> <span data-ttu-id="a13d6-177">如需詳細資訊，請參閱 [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)。</span><span class="sxs-lookup"><span data-stu-id="a13d6-177">For details, see [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario).</span></span>

<div class="">


> [!WARNING]  
> <span data-ttu-id="a13d6-178"><STRONG>New-ClsCsProvider</STRONG> 不會進行檢查來決定旗標是否有效。</span><span class="sxs-lookup"><span data-stu-id="a13d6-178"><STRONG>New-ClsCsProvider</STRONG> does not check to determine whether the flags are valid.</span></span> <span data-ttu-id="a13d6-179">請確認旗標的拼字 (例如 TF_DIAG 或 TF_CONNECTION) 正確無誤。</span><span class="sxs-lookup"><span data-stu-id="a13d6-179">Make sure that the spelling of the flags (for example, TF_DIAG or TF_CONNECTION) is spelled correctly.</span></span> <span data-ttu-id="a13d6-180">如果旗標的拼字不正確，提供者就無法傳回預期的記錄資訊。</span><span class="sxs-lookup"><span data-stu-id="a13d6-180">If the flags are not spelled correctly, the provider cannot return the expected log information.</span></span>



</div>

<span data-ttu-id="a13d6-181">如果您想要將其他提供者新增至此案例，請輸入下列項目：</span><span class="sxs-lookup"><span data-stu-id="a13d6-181">If you want to add additional providers to this scenario, type the following:</span></span>

    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}

<span data-ttu-id="a13d6-182">在那裏，使用「新增」指示詞加以定義的每個提供者，都已經使用 **New-CsClsProvider** 程序加以定義。</span><span class="sxs-lookup"><span data-stu-id="a13d6-182">Where each provider defined with the Add directive has already been defined using the **New-CsClsProvider** process.</span></span>

</div>

<div>

## <a name="to-remove-a-scenario-provider"></a><span data-ttu-id="a13d6-183">移除案例提供者</span><span class="sxs-lookup"><span data-stu-id="a13d6-183">To remove a scenario provider</span></span>

1.  <span data-ttu-id="a13d6-184">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="a13d6-184">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a13d6-185">所提供的 Cmdlet 可讓您新增現有的提供者以及建立新的提供者。</span><span class="sxs-lookup"><span data-stu-id="a13d6-185">The cmdlets provided allow you to update existing providers and create new providers.</span></span> <span data-ttu-id="a13d6-186">若要移除提供者，您必須針對 **Set-CsClsScenario** 的 Provider 參數使用 Replace 指示詞。</span><span class="sxs-lookup"><span data-stu-id="a13d6-186">To remove a provider, you must use the Replace directive for the Provider parameter to **Set-CsClsScenario**.</span></span> <span data-ttu-id="a13d6-187">完全移除提供者的唯一方式，是以相同名稱之重新定義的提供者來加以取代，並使用 Update 指示詞。</span><span class="sxs-lookup"><span data-stu-id="a13d6-187">The only way to completely remove a provider is to replace it with a redefined provider of the same name and use the Update directive.</span></span> <span data-ttu-id="a13d6-188">例如，我們的提供者 LyssProvider 會定義為 WPP 為記錄類型、設定為調試的層級，而旗標為 TF \_ CONNECTION 和 tf the \_ 。</span><span class="sxs-lookup"><span data-stu-id="a13d6-188">For example, our provider LyssProvider is defined with WPP as the log type, level set to Debug, and flags set are TF\_CONNECTION and TF\_DIAG.</span></span> <span data-ttu-id="a13d6-189">您需將旗標變更為“All”。</span><span class="sxs-lookup"><span data-stu-id="a13d6-189">You need to change the flags to “All”.</span></span> <span data-ttu-id="a13d6-190">若要變更提供者，請輸入下列項目：</span><span class="sxs-lookup"><span data-stu-id="a13d6-190">To change the provider, type the following:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"

     &nbsp;
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}

3.  <span data-ttu-id="a13d6-191">若要完全移除某案例和與其相關的提供者，請輸入下列項目：</span><span class="sxs-lookup"><span data-stu-id="a13d6-191">If you want to completely remove a scenario and the providers associated with it, type the following:</span></span>
    
        Remove-CsClsScenario -Identity <scope and name of scenario>
    
    <span data-ttu-id="a13d6-192">例如：</span><span class="sxs-lookup"><span data-stu-id="a13d6-192">For example:</span></span>
    
        Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
    
    <div class="">
    

    > [!WARNING]  
    > <span data-ttu-id="a13d6-193">Cmdlet <STRONG>Remove-CsClsScenario</STRONG> 不會提示您進行確認。</span><span class="sxs-lookup"><span data-stu-id="a13d6-193">The cmdlet <STRONG>Remove-CsClsScenario</STRONG> does not prompt you for confirmation.</span></span> <span data-ttu-id="a13d6-194">案例會連同指派給它的提供者一併遭刪除。</span><span class="sxs-lookup"><span data-stu-id="a13d6-194">The scenario is deleted, along with the providers that were assigned to it.</span></span> <span data-ttu-id="a13d6-195">您可以重新執行一開始用來建立案例的命令以重新建立案例。</span><span class="sxs-lookup"><span data-stu-id="a13d6-195">You can recreate the scenario by re-running the commands used to create it initially.</span></span> <span data-ttu-id="a13d6-196">您無法還原遭移除的案例或提供者。</span><span class="sxs-lookup"><span data-stu-id="a13d6-196">There is no procedure to recover removed scenarios or providers.</span></span>

    
    </div>

<span data-ttu-id="a13d6-197">在使用 **Remove-CsClsScenario** Cmdlet 移除案例時，您可以將案例從範圍完全移除。</span><span class="sxs-lookup"><span data-stu-id="a13d6-197">When you remove a scenario by using the **Remove-CsClsScenario** cmdlet, you completely remove the scenario from the scope.</span></span> <span data-ttu-id="a13d6-198">若要使用您建立的案例，及使用做為案例之一部分的提供者，您需建立新的提供者，並將其指派給新的案例。</span><span class="sxs-lookup"><span data-stu-id="a13d6-198">To use the scenarios that you created and the providers that were a part of the scenario, you create new providers and assign them to a new scenario.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a13d6-199">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a13d6-199">See Also</span></span>


[<span data-ttu-id="a13d6-200">Get-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="a13d6-200">Get-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)  
[<span data-ttu-id="a13d6-201">New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="a13d6-201">New-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClsScenario)  
[<span data-ttu-id="a13d6-202">Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="a13d6-202">Remove-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsClsScenario)  
[<span data-ttu-id="a13d6-203">Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="a13d6-203">Set-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario)  
[<span data-ttu-id="a13d6-204">New-CsClsProvider</span><span class="sxs-lookup"><span data-stu-id="a13d6-204">New-CsClsProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

