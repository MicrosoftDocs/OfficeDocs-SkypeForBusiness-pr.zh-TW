---
title: 在商務用 Skype Server 2015 中開始或停止 CLS 記錄捕獲
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
description: 摘要：瞭解如何在商務用 Skype Server 2015 中啟動或停止集中式記錄服務記錄捕獲會話。
ms.openlocfilehash: cd6864b0d4d16e952f93fe321b49522028d76e5b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835133"
---
# <a name="start-or-stop-cls-log-capture-in-skype-for-business-server-2015"></a><span data-ttu-id="f2536-103">在商務用 Skype Server 2015 中開始或停止 CLS 記錄捕獲</span><span class="sxs-lookup"><span data-stu-id="f2536-103">Start or stop CLS log capture in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f2536-104">**摘要：** 瞭解如何在商務用 Skype Server 2015 中啟動或停止集中式記錄服務記錄捕獲會話。</span><span class="sxs-lookup"><span data-stu-id="f2536-104">**Summary:** Learn how to start or stop a Centralized Logging Service log capture session in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="f2536-105">若要使用集中式記錄服務來捕獲追蹤記錄檔，您會發出命令，以開始登入一或多部電腦及集區。</span><span class="sxs-lookup"><span data-stu-id="f2536-105">To capture trace logs using the Centralized Logging Service, you issue a command to begin logging on one or more computers and pools.</span></span> <span data-ttu-id="f2536-106">您也可以發出參數，定義哪些電腦或集區、要執行哪些案例 (例如，AlwaysOn、其他預先定義的案例或您已建立的案例) ， (的商務用 Skype Server 元件例如，S4，SipStack) 來追蹤。</span><span class="sxs-lookup"><span data-stu-id="f2536-106">You also issue parameters that define which computers or pools, what scenarios to run (for example, AlwaysOn, another predefined scenario, or a scenario you have created), what Skype for Business Server components (for example, S4, SipStack) to trace.</span></span>
  
<span data-ttu-id="f2536-107">為了擷取正確的資訊，您必須確定使用正確的案例來收集問題的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f2536-107">To capture the right information, you need to make sure you use the right scenario to collect information that is relevant to the problem.</span></span> <span data-ttu-id="f2536-108">在集中式記錄服務中，案例是指根據伺服器元件的集合、記錄層級和旗標來開啟記錄的概念，其效率更高，而且在每個伺服器基礎上都必須定義這些元素時非常實用。</span><span class="sxs-lookup"><span data-stu-id="f2536-108">In the Centralized Logging Service, a scenario is the concept of turning logging on based on a collection of server components, logging levels, and flags, which is much more efficient and useful than having to define these elements on a per-server basis.</span></span> <span data-ttu-id="f2536-109">您可以定義及指定要執行的案例，這些案例會在基礎結構範圍內的所有伺服器和集區上持續執行。</span><span class="sxs-lookup"><span data-stu-id="f2536-109">You define and specify a scenario to run and the scenario is run consistently across all servers and pools in the scope of the infrastructure.</span></span>
  
<span data-ttu-id="f2536-p103">預設案例稱為 **AlwaysOn**。AlwaysOn 的預定目的是持續執行案例 (如案例名稱所指)。AlwaysOn 案例針對許多最常見的伺服器元件，收集資訊層級的資訊 (請注意，資訊記錄層次除了資訊訊息之外，還包含 [嚴重]、[錯誤] 及 [警告])。AlwaysOn 會收集發生問題前後及期間的資訊。這與之前的記錄工具 (例如 OCSLogger) 的一般行為大不相同。您會在發生問題之後執行 OCSLogger，這讓疑難排解工作更加困難，因為您擁有的資料只會被動回應，而無法主動解決問題。如果 AlwaysOn 所包含的資訊，不是您想要指向問題元件及指出修正步驟的資訊 (在 AlwaysOn 提供者的深度和廣度下，此情形並不常見)，AlwaysOn 會指出合理的資訊層級，以決定必須執行的其他動作，例如建立新的案例、收集其他資訊、執行其他搜尋以收集更集中的詳細資料等。</span><span class="sxs-lookup"><span data-stu-id="f2536-p103">The default scenario is called **AlwaysOn**. The intended purpose for AlwaysOn is to run the scenario constantly, as the name of the scenario implies. The AlwaysOn scenario collects Info level information (note that Info logging level includes Fatal, Error, and Warning in addition to Info messages) for many of the most common server components. AlwaysOn collects information before, during, and after a problem occurs. This differs dramatically from the typical behavior of previous logging tools such as OCSLogger. You ran OCSLogger after the problem had already occurred, making your troubleshooting efforts more difficult because the data that you have is reactive, not proactive. If AlwaysOn does not contain the information that you are looking for in order to point to the problem component and indicate a course of action to fix it (which is not likely given the breadth and depth of providers in AlwaysOn), it will indicate a reasonable level of information to determine what else you need to do, such as creating a new scenario, gather other information, run a different search to collect more focused details, and so on.</span></span>
  
<span data-ttu-id="f2536-117">集中式記錄服務提供兩種方式發出命令。</span><span class="sxs-lookup"><span data-stu-id="f2536-117">The Centralized Logging Service provides two ways to issue commands.</span></span> <span data-ttu-id="f2536-118">許多主題透過商務用 Skype Server 管理命令介面，以 Windows PowerShell 為重點 squarely。</span><span class="sxs-lookup"><span data-stu-id="f2536-118">A number of topics have been focused squarely on using Windows PowerShell through the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="f2536-119">使用許多複雜設定和命令的能力，可對 Windows PowerShell 以進行集中式記錄服務使用。</span><span class="sxs-lookup"><span data-stu-id="f2536-119">The ability to use a number of complex configurations and commands favors Windows PowerShell for Centralized Logging Service use.</span></span> <span data-ttu-id="f2536-120">由於 Windows PowerShell 透過商務用 Skype Server 管理命令介面幾乎到處是商務用 Skype Server 中的所有功能，因此只討論 Windows PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="f2536-120">Because Windows PowerShell through the Skype for Business Server Management Shell is nearly ubiquitous for all functions in Skype for Business Server, only the Windows PowerShell commands are discussed.</span></span> 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a><span data-ttu-id="f2536-121">使用基本命令以 Windows PowerShell 執行 Start-CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="f2536-121">To run Start-CsClsLogging with Windows PowerShell using basic commands</span></span>

1. <span data-ttu-id="f2536-122">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="f2536-122">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="f2536-123">輸入下列命令，以集中式記錄服務開機記錄案例：</span><span class="sxs-lookup"><span data-stu-id="f2536-123">Start a logging scenario with the Centralized Logging Service by typing the following:</span></span>
    
   ```PowerShell
   Start-CsClsLogging -Scenario <name of scenario>
   ```

    <span data-ttu-id="f2536-124">例如，若要啟動 **AlwaysOn** 案例，請輸入：</span><span class="sxs-lookup"><span data-stu-id="f2536-124">For example, to start the **AlwaysOn** scenario, type:</span></span>
    
   ```PowerShell
   Start-CsClsLogging -Scenario AlwaysOn
   ```

    > [!NOTE]
    > <span data-ttu-id="f2536-125">AlwaysOn 案例沒有預設期間。</span><span class="sxs-lookup"><span data-stu-id="f2536-125">The AlwaysOn scenario has no default duration.</span></span> <span data-ttu-id="f2536-126">此案例會一直執行，直到您使用 **Stop-CsClsLogging** Cmdlet 明確加以停止。</span><span class="sxs-lookup"><span data-stu-id="f2536-126">This scenario will run until you explicitly stop it with the **Stop-CsClsLogging** cmdlet.</span></span> <span data-ttu-id="f2536-127">如需詳細資訊，請參閱＜[Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)＞。</span><span class="sxs-lookup"><span data-stu-id="f2536-127">For details, see [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps).</span></span> <span data-ttu-id="f2536-128">其他所有案例的預設期間為 4 小時。</span><span class="sxs-lookup"><span data-stu-id="f2536-128">For all other scenarios, the default duration is 4 hours.</span></span> 
  
3. <span data-ttu-id="f2536-129">按 Enter 鍵執行命令。</span><span class="sxs-lookup"><span data-stu-id="f2536-129">Press Enter to run the command.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="f2536-130">可能需要一點時間 (30 到 60 秒) 才能執行命令，並接收部署中的電腦傳回的狀態。</span><span class="sxs-lookup"><span data-stu-id="f2536-130">It may take a short amount of time (30 to 60 seconds) for the commands to run and to receive the status back from the computers in your deployment.</span></span> 
  
     ![執行 Start-CsClsLogging。](../../media/Ops_CLS_Show_and_Start_ClsLogging.jpg)
  
4. <span data-ttu-id="f2536-132">若要開始另一種情況，請使用 **Start-CsClsLogging** Cmdlet 及其他案例的名稱來執行，如下所示 (例如，案例 **驗證**) ：</span><span class="sxs-lookup"><span data-stu-id="f2536-132">To start another scenario, use the **Start-CsClsLogging** cmdlet with the name of the additional scenario to run as follows (for example, the scenario **Authentication**):</span></span>
    
   ```PowerShell
   Start-CsClsLogging -Scenario Authentication
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="f2536-133">在任何時候，最多可以在任何指定的電腦上執行兩個案例。</span><span class="sxs-lookup"><span data-stu-id="f2536-133">You can have a total of two scenarios running on any given computer at any time.</span></span> <span data-ttu-id="f2536-134">如果命令的範圍為全域，部署中的所有電腦都會執行這些案例。</span><span class="sxs-lookup"><span data-stu-id="f2536-134">If the command is global in scope, all of the computers in your deployment will run the scenario or scenarios.</span></span> <span data-ttu-id="f2536-135">若要啟動第三個案例，您必須從要執行新案例的電腦、集區、網站或全域範圍停止記錄。</span><span class="sxs-lookup"><span data-stu-id="f2536-135">To start a third scenario, you must stop logging on the computer, pool, site, or global scope that you want to run the new scenario on.</span></span> <span data-ttu-id="f2536-136">如果已啟動全域範圍，您可以在一或多部電腦和集區上停止記錄一或兩個案例。</span><span class="sxs-lookup"><span data-stu-id="f2536-136">If you have started a global scope, you can stop logging for one or both of the scenarios on one or more computers and pools.</span></span> 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a><span data-ttu-id="f2536-137">使用 Windows PowerShell 使用 advanced 命令執行 Start-CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="f2536-137">To run Start-CsClsLogging with Windows PowerShell using advanced commands</span></span>

1. <span data-ttu-id="f2536-138">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="f2536-138">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="f2536-139">您可以使用其他參數管理記錄命令。</span><span class="sxs-lookup"><span data-stu-id="f2536-139">Additional parameters are available to manage the logging commands.</span></span> <span data-ttu-id="f2536-140">您可以使用-Duration 來調整案例的執行時間長度。</span><span class="sxs-lookup"><span data-stu-id="f2536-140">You can use -Duration to adjust the length of time for the scenario to run.</span></span> <span data-ttu-id="f2536-141">您也可以定義電腦、電腦完整功能變數名稱的清單 (Fqdn) 以逗號分隔的集區清單，以逗號分隔，以供您要執行記錄的集區的 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="f2536-141">You also can define -Computers, a list of computer fully qualified domain names (FQDNs) separated by a comma, or -Pools, a comma separated list of FQDNs for pools that you want to run logging on.</span></span>
    
    <span data-ttu-id="f2536-142">您為集區 "pool01.contoso.net" 上的 UserReplicator 案例開始記錄會話。</span><span class="sxs-lookup"><span data-stu-id="f2536-142">You start a logging session for the UserReplicator scenario on the pool "pool01.contoso.net".</span></span> <span data-ttu-id="f2536-143">您也可以將記錄工作階段期間定義為 8 小時。</span><span class="sxs-lookup"><span data-stu-id="f2536-143">You also define the duration of the logging session at 8 hours.</span></span> <span data-ttu-id="f2536-144">若要執行這項操作，請輸入：</span><span class="sxs-lookup"><span data-stu-id="f2536-144">To do this, type:</span></span>
    
   ```PowerShell
   Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
   ```

    <span data-ttu-id="f2536-145">成功執行此案例會傳回類似如下的結果：</span><span class="sxs-lookup"><span data-stu-id="f2536-145">The successful execution of this scenario returns a result like the following:</span></span>
    
     ![執行 Start-CsClsLogging。](../../media/Ops_CsClsLogging_UserReplicator_Exp.jpg)
  
<span data-ttu-id="f2536-147">請注意，在此範例中，AlwaysOn 案例和 UserReplicator 案例都在執行中。</span><span class="sxs-lookup"><span data-stu-id="f2536-147">Note that in this example, the AlwaysOn scenario is running and the UserReplicator scenario is running.</span></span> 
    
## <a name="stop-the-centralized-logging-service-log-capture"></a><span data-ttu-id="f2536-148">停止集中式記錄服務記錄捕獲</span><span class="sxs-lookup"><span data-stu-id="f2536-148">Stop the Centralized Logging Service log capture</span></span>
<span data-ttu-id="f2536-149"><a name="stop"> </a></span><span class="sxs-lookup"><span data-stu-id="f2536-149"><a name="stop"> </a></span></span>

<span data-ttu-id="f2536-150">您可以用 Stop-CsClsLogging Cmdlet 來停止目前執行中的記錄工作階段。</span><span class="sxs-lookup"><span data-stu-id="f2536-150">You can stop a currently running logging session with the Stop-CsClsLogging cmdlet.</span></span> <span data-ttu-id="f2536-151">一般來說，在許多情況下，您不需要停止記錄會話。</span><span class="sxs-lookup"><span data-stu-id="f2536-151">Generally, there aren't many situations in which you would need to stop a logging session.</span></span> <span data-ttu-id="f2536-152">例如，您不需要先停止記錄，就可以搜尋記錄及變更設定。</span><span class="sxs-lookup"><span data-stu-id="f2536-152">For example, you can search logs and change configurations without first needing to stop logging.</span></span> <span data-ttu-id="f2536-153">如果您有兩個案例正在執行，例如 AlwaysOn 和 UserReplicator，而您需要收集有關驗證的資訊，則必須先停止其中一個案例 (在全域、網站、集區或電腦範圍)，才能開始執行驗證案例。</span><span class="sxs-lookup"><span data-stu-id="f2536-153">If you have two scenarios running, for example AlwaysOn and UserReplicator, and you need to collect information related to Authentication, you will need to stop one of the other scenarios (at a global, site, pool or computer scope) before you can start running to Authentication scenario.</span></span> <span data-ttu-id="f2536-154">如需詳細資訊，請參閱＜[Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)＞。</span><span class="sxs-lookup"><span data-stu-id="f2536-154">For details, see [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f2536-155">在決定您可以在指定的部署、集區或電腦上執行哪些案例時，您必須記得 **每台電腦** 都限制執行兩個案例： AlwaysOn 和一個自訂案例。</span><span class="sxs-lookup"><span data-stu-id="f2536-155">When determining what scenarios you can run on a given deployment, pool or computer, you need to remember that you are limited to running two scenarios **per computer**: AlwaysOn and one custom scenario.</span></span> <span data-ttu-id="f2536-156">如果您要在集區上記錄活動，則應將集區當做單一實體來處理。</span><span class="sxs-lookup"><span data-stu-id="f2536-156">If you are logging activity on a pool, you should treat a pool as a single entity.</span></span> <span data-ttu-id="f2536-157">在大部分情況下，在集區中的每部電腦上執行不同的案例並沒有意義。</span><span class="sxs-lookup"><span data-stu-id="f2536-157">In most cases, it would not make sense to run different scenarios on each computer in a pool.</span></span> <span data-ttu-id="f2536-158">但是查看您收集資料的相關問題，並思考在整體部署中，哪個案例對給定電腦的影響最大，這就有意義了。</span><span class="sxs-lookup"><span data-stu-id="f2536-158">It does make sense to look at the problem that you are collecting data about and think about what scenario makes the most sense on a given computer in the overall deployment.</span></span> <span data-ttu-id="f2536-159">例如，如果您考慮 UserReplicator 案例，在 Edge Server 或 Edge 集區上執行 UserReplicator 時，會有很小的價值。</span><span class="sxs-lookup"><span data-stu-id="f2536-159">For example, if you consider the UserReplicator scenario, there would be very little value in running UserReplicator on an Edge Server or Edge pool.</span></span> 
  
<span data-ttu-id="f2536-p111">在了解問題及影響的範圍之後，應謹慎選擇要在哪些電腦和集區上執行什麼案例。雖然 AlwaysOn 案例對大範圍的應用有意義，因為它會收集各種提供者的資訊，但是特定案例對特定電腦或集區只有應用價值。此外，在未了解給定案例的價值之前，就隨機啟動記錄工作階段的話，要特別小心。如果您使用錯誤的案例，或是所使用的案例適合該工作，而您將案例套用在錯誤的範圍 (可能是全域、網站、集區或電腦)，所得到的問題資料可能不是很有用，就像根本沒有執行案例一樣。</span><span class="sxs-lookup"><span data-stu-id="f2536-p111">After you understand the problem and the scope of the impact, you should make careful choices about what scenarios to run on which computers and pools. While the AlwaysOn scenario makes sense for a wide scope application because it collects information on a wide variety of providers, specific scenarios only have application value on specific computers or pools. Also, you should take caution when randomly starting up a logging session without first understanding the value of a given scenario. If you use the wrong scenario, or if you use a scenario that is appropriate for the task and you apply the scenario at the wrong scope (be it global, site, pool, or computer), you can get questionable data that is not very useful—as if you didn't run the scenario at all.</span></span>
  
<span data-ttu-id="f2536-164">若要使用商務用 Skype Server 管理命令介面來控制集中式記錄服務功能，您必須是 CsAdministrator 或 CsServerAdministrator 角色型存取控制 (RBAC) 安全性群組的成員，或是包含這兩個群組之任一個自訂 RBAC 角色的成員。</span><span class="sxs-lookup"><span data-stu-id="f2536-164">To control the Centralized Logging Service functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="f2536-165">若要傳回所有獲指派此 Cmdlet 的 RBAC 角色清單 (包含您自行建立的自訂 RBAC 角色) ，請從商務用 Skype Server 管理命令介面或 Windows PowerShell 提示中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="f2536-165">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="f2536-166">例如：</span><span class="sxs-lookup"><span data-stu-id="f2536-166">For example:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> <span data-ttu-id="f2536-167">您可能會想知道：現在已經啟用記錄，記錄檔會保留在何處？</span><span class="sxs-lookup"><span data-stu-id="f2536-167">So you may be wondering: Now that you've enabled logging, where are the logs kept?</span></span> <span data-ttu-id="f2536-168">由於您將使用傳送至 CLS 代理程式的管理命令介面查詢，存取儲存在記錄檔中的資訊，因此您可以將結果輸出成幾種可能的檔案格式，在每一部伺服器上，CLS 代理程式都可以保留其記錄，但實際上並無重要的瞭解。</span><span class="sxs-lookup"><span data-stu-id="f2536-168">Since you'll access the information stored in the logs using management shell queries sent to the CLS Agents, and you can output the results to several possible file formats, where on each server a CLS Agent keeps its records isn't actually important to know.</span></span>  <span data-ttu-id="f2536-169">您可以使用各種工具（包括Snooper.exe及可讀取文字檔的任何工具）將記錄檔儲存至您指定的位置，包括和任何可讀取文字檔的工具，例如 **Notepad.exe**。</span><span class="sxs-lookup"><span data-stu-id="f2536-169">The log files can be saved to a location you specify and  read and analyzed using a variety of tools, including **Snooper.exe** and any tool that can read a text file, such as **Notepad.exe**.</span></span> <span data-ttu-id="f2536-170">Snooper.exe 是商務用 Skype Server 2015 調試工具的一部分，可供 [網頁下載](https://go.microsoft.com/fwlink/p/?LinkId=285257)使用。</span><span class="sxs-lookup"><span data-stu-id="f2536-170">Snooper.exe is part of the Skype for Business Server 2015 Debug Tools and is available as a [Web download](https://go.microsoft.com/fwlink/p/?LinkId=285257).</span></span>

### <a name="to-stop-a-currently-running-centralized-logging-service-session"></a><span data-ttu-id="f2536-171">停止目前執行中的集中式記錄服務會話</span><span class="sxs-lookup"><span data-stu-id="f2536-171">To stop a currently running Centralized Logging Service session</span></span>

1. <span data-ttu-id="f2536-172">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="f2536-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="f2536-173">輸入下列命令來查詢集中式記錄服務，以找出目前正在執行的案例：</span><span class="sxs-lookup"><span data-stu-id="f2536-173">Query the Centralized Logging Service to find out what scenarios are currently running by typing the following:</span></span>
    
   ```PowerShell
   Show-CsClsLogging
   ```

   ![呼叫 Show-CsCl 後的 Windows PowerShell 主控台](../../media/Ops_Show_Stop_CsClsLogging.jpg)
  
   <span data-ttu-id="f2536-175">Show-CsClsLogging 的結果是執行中案例及其執行範圍的摘要。</span><span class="sxs-lookup"><span data-stu-id="f2536-175">The result of Show-CsClsLogging is a summary of the scenarios that are running and what scope they are running in.</span></span> <span data-ttu-id="f2536-176">如需詳細資訊，請參閱＜[Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps)＞。</span><span class="sxs-lookup"><span data-stu-id="f2536-176">For details, see [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps).</span></span>
    
3. <span data-ttu-id="f2536-177">若要停止使用特定案例的目前執行中記錄工作階段，請輸入：</span><span class="sxs-lookup"><span data-stu-id="f2536-177">To stop a currently running logging session with a specific scenario, type:</span></span>
    
   ```PowerShell
   Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
   ```
   <span data-ttu-id="f2536-178">例如：</span><span class="sxs-lookup"><span data-stu-id="f2536-178">For example:</span></span>
    
   ```PowerShell
   Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
   ```

   <span data-ttu-id="f2536-179">此命令將會停止 pool01.contoso.net 上使用 UserReplicatior 案例的記錄。</span><span class="sxs-lookup"><span data-stu-id="f2536-179">This command will stop logging with the UserReplicatior scenario on pool01.contoso.net.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f2536-180">在此記錄工作階段期間，使用 UserReplicator 案例來建立的記錄並不會刪除。</span><span class="sxs-lookup"><span data-stu-id="f2536-180">Logs created during this logging session using the UserReplicator scenario are not deleted.</span></span> <span data-ttu-id="f2536-181">您還是可以使用該記錄來執行使用 Search-CsClsLogging 命令的搜尋作業。</span><span class="sxs-lookup"><span data-stu-id="f2536-181">The logging is still available for you to execute searches against using the Search-CsClsLogging command.</span></span> <span data-ttu-id="f2536-182">如需詳細資訊，請參閱＜[Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps)＞。</span><span class="sxs-lookup"><span data-stu-id="f2536-182">For details, see [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps).</span></span> 
  
<span data-ttu-id="f2536-p116">Stop-CsClsLogging Cmdlet 與 Start-CsClsLogging 搭配使用時，會結束記錄工作階段 (由案例定義)，並保留記錄工作階段所建立的記錄。您隨時都可以在給定的電腦上執行兩個案例。用一個案例停止另一個案例來收集資訊的方法，是在大部分工作量疑難排解期間都可以執行的常用工作。</span><span class="sxs-lookup"><span data-stu-id="f2536-p116">Acting as the companion command to Start-CsClsLogging, the Stop-CsClsLogging cmdlet ends the logging session, defined by scenarios, and retains the logs created by the logging session. You can run two scenarios on a given computer at any time. The method of stopping one scenario to gather information using another scenario is a common task that you can perform during most workload troubleshooting.</span></span>
## <a name="see-also"></a><span data-ttu-id="f2536-186">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f2536-186">See also</span></span>
<span data-ttu-id="f2536-187"><a name="stop"> </a></span><span class="sxs-lookup"><span data-stu-id="f2536-187"><a name="stop"> </a></span></span>

[<span data-ttu-id="f2536-188">商務用 Skype 2015 中的集中式記錄服務</span><span class="sxs-lookup"><span data-stu-id="f2536-188">Centralized Logging Service in Skype for Business 2015</span></span>](centralized-logging-service.md)
