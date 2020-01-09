---
title: 開始或停止商務用 Skype 2015 中的 CLS 記錄擷取
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
ms.assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
description: 摘要：瞭解如何在商務用 Skype Server 2015 中啟動或停止集中式記錄服務記錄捕獲會話。
ms.openlocfilehash: b4da74e05a1eb6f6945f44c0c045c2292e7acca7
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991438"
---
# <a name="start-or-stop-cls-log-capture-in-skype-for-business-server-2015"></a><span data-ttu-id="fd39b-103">開始或停止商務用 Skype 2015 中的 CLS 記錄擷取</span><span class="sxs-lookup"><span data-stu-id="fd39b-103">Start or stop CLS log capture in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="fd39b-104">**摘要：** 瞭解如何在商務用 Skype Server 2015 中啟動或停止集中式記錄服務記錄捕獲會話。</span><span class="sxs-lookup"><span data-stu-id="fd39b-104">**Summary:** Learn how to start or stop a Centralized Logging Service log capture session in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="fd39b-105">若要使用集中式記錄服務來捕獲追蹤記錄，您需要發出命令，以便在一或多部電腦和池上開始記錄。</span><span class="sxs-lookup"><span data-stu-id="fd39b-105">To capture trace logs using the Centralized Logging Service, you issue a command to begin logging on one or more computers and pools.</span></span> <span data-ttu-id="fd39b-106">您也可以發出可定義哪些電腦或池、要執行的案例（例如，AlwaysOn、另一個預先定義的案例或您所建立的案例）的參數，以及要追蹤的商務用 Skype Server 元件（例如，S4、SipStack）。</span><span class="sxs-lookup"><span data-stu-id="fd39b-106">You also issue parameters that define which computers or pools, what scenarios to run (for example, AlwaysOn, another predefined scenario, or a scenario you have created), what Skype for Business Server components (for example, S4, SipStack) to trace.</span></span>
  
<span data-ttu-id="fd39b-107">若要捕獲正確的資訊，您必須確認使用正確的案例，才能收集與問題相關的資訊。</span><span class="sxs-lookup"><span data-stu-id="fd39b-107">To capture the right information, you need to make sure you use the right scenario to collect information that is relevant to the problem.</span></span> <span data-ttu-id="fd39b-108">在集中式記錄服務中，案例是根據伺服器元件集合、記錄層級和旗標來開啟記錄的概念，這比要在每個伺服器上定義這些元素更有效率且更有用。</span><span class="sxs-lookup"><span data-stu-id="fd39b-108">In the Centralized Logging Service, a scenario is the concept of turning logging on based on a collection of server components, logging levels, and flags, which is much more efficient and useful than having to define these elements on a per-server basis.</span></span> <span data-ttu-id="fd39b-109">您定義並指定要執行的案例，並在整個基礎結構範圍中的所有伺服器和池上一致地執行該案例。</span><span class="sxs-lookup"><span data-stu-id="fd39b-109">You define and specify a scenario to run and the scenario is run consistently across all servers and pools in the scope of the infrastructure.</span></span>
  
<span data-ttu-id="fd39b-110">預設案例稱為 [ **AlwaysOn**]。</span><span class="sxs-lookup"><span data-stu-id="fd39b-110">The default scenario is called **AlwaysOn**.</span></span> <span data-ttu-id="fd39b-111">AlwaysOn 的預期用途是經常執行該案例，因為案例的名稱所隱含。</span><span class="sxs-lookup"><span data-stu-id="fd39b-111">The intended purpose for AlwaysOn is to run the scenario constantly, as the name of the scenario implies.</span></span> <span data-ttu-id="fd39b-112">AlwaysOn 案例會收集資訊層級資訊（請注意，資訊記錄層級除了資訊訊息之外，還包含許多最常見伺服器元件的致命、錯誤和警告）。</span><span class="sxs-lookup"><span data-stu-id="fd39b-112">The AlwaysOn scenario collects Info level information (note that Info logging level includes Fatal, Error, and Warning in addition to Info messages) for many of the most common server components.</span></span> <span data-ttu-id="fd39b-113">AlwaysOn 會在問題發生之前、期間及之後收集資訊。</span><span class="sxs-lookup"><span data-stu-id="fd39b-113">AlwaysOn collects information before, during, and after a problem occurs.</span></span> <span data-ttu-id="fd39b-114">這與前一筆記錄工具（例如 OCSLogger）的一般行為有顯著的差異。</span><span class="sxs-lookup"><span data-stu-id="fd39b-114">This differs dramatically from the typical behavior of previous logging tools such as OCSLogger.</span></span> <span data-ttu-id="fd39b-115">您在問題發生之後執行了 OCSLogger，因為您所擁有的資料是被動而非主動，所以您的疑難排解工作變得更困難。</span><span class="sxs-lookup"><span data-stu-id="fd39b-115">You ran OCSLogger after the problem had already occurred, making your troubleshooting efforts more difficult because the data that you have is reactive, not proactive.</span></span> <span data-ttu-id="fd39b-116">如果 AlwaysOn 不包含您要尋找的資訊，而是要指向問題元件，並指出一個動作程式來修正它（不太可能是在 AlwaysOn 中提供提供者的廣度與深度），它會指出適當的資訊層級rmation 以判斷您需要執行的其他動作，例如建立新案例、收集其他資訊、執行不同的搜尋，以收集更專注的詳細資料等等。</span><span class="sxs-lookup"><span data-stu-id="fd39b-116">If AlwaysOn does not contain the information that you are looking for in order to point to the problem component and indicate a course of action to fix it (which is not likely given the breadth and depth of providers in AlwaysOn), it will indicate a reasonable level of information to determine what else you need to do, such as creating a new scenario, gather other information, run a different search to collect more focused details, and so on.</span></span>
  
<span data-ttu-id="fd39b-117">集中式記錄服務提供兩種方式來發出命令。</span><span class="sxs-lookup"><span data-stu-id="fd39b-117">The Centralized Logging Service provides two ways to issue commands.</span></span> <span data-ttu-id="fd39b-118">您可以透過商務用 Skype Server Management 命令介面，在 Windows PowerShell 中，有許多主題是焦點恰好。</span><span class="sxs-lookup"><span data-stu-id="fd39b-118">A number of topics have been focused squarely on using Windows PowerShell through the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="fd39b-119">使用許多複雜的設定和命令的能力，有利於使用 Windows PowerShell 來集中式記錄服務。</span><span class="sxs-lookup"><span data-stu-id="fd39b-119">The ability to use a number of complex configurations and commands favors Windows PowerShell for Centralized Logging Service use.</span></span> <span data-ttu-id="fd39b-120">因為 Windows PowerShell 透過商務用 Skype Server 管理命令介面幾乎無處不在商務用 Skype Server 中的所有功能，所以只討論 Windows PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="fd39b-120">Because Windows PowerShell through the Skype for Business Server Management Shell is nearly ubiquitous for all functions in Skype for Business Server, only the Windows PowerShell commands are discussed.</span></span> 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a><span data-ttu-id="fd39b-121">使用基本命令在 Windows PowerShell 中執行開始 CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="fd39b-121">To run Start-CsClsLogging with Windows PowerShell using basic commands</span></span>

1. <span data-ttu-id="fd39b-122">啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="fd39b-122">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="fd39b-123">輸入以下內容，以集中式記錄服務開機記錄案例：</span><span class="sxs-lookup"><span data-stu-id="fd39b-123">Start a logging scenario with the Centralized Logging Service by typing the following:</span></span>
    
   ```PowerShell
   Start-CsClsLogging -Scenario <name of scenario>
   ```

    <span data-ttu-id="fd39b-124">例如，若要啟動**AlwaysOn**案例，請輸入：</span><span class="sxs-lookup"><span data-stu-id="fd39b-124">For example, to start the **AlwaysOn** scenario, type:</span></span>
    
   ```PowerShell
   Start-CsClsLogging -Scenario AlwaysOn
   ```

    > [!NOTE]
    > <span data-ttu-id="fd39b-125">AlwaysOn 案例沒有預設的持續時間。</span><span class="sxs-lookup"><span data-stu-id="fd39b-125">The AlwaysOn scenario has no default duration.</span></span> <span data-ttu-id="fd39b-126">這個案例將會在您明確地停止使用**CsClsLogging** Cmdlet 之前執行。</span><span class="sxs-lookup"><span data-stu-id="fd39b-126">This scenario will run until you explicitly stop it with the **Stop-CsClsLogging** cmdlet.</span></span> <span data-ttu-id="fd39b-127">如需詳細資訊，請參閱[停止 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="fd39b-127">For details, see [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps).</span></span> <span data-ttu-id="fd39b-128">在所有其他案例中，預設期間是4小時。</span><span class="sxs-lookup"><span data-stu-id="fd39b-128">For all other scenarios, the default duration is 4 hours.</span></span> 
  
3. <span data-ttu-id="fd39b-129">按 Enter 以執行命令。</span><span class="sxs-lookup"><span data-stu-id="fd39b-129">Press Enter to run the command.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="fd39b-130">您可能需要花很短的時間（30到60秒），才能執行這些命令，並從您的部署中的電腦接收傳回的狀態。</span><span class="sxs-lookup"><span data-stu-id="fd39b-130">It may take a short amount of time (30 to 60 seconds) for the commands to run and to receive the status back from the computers in your deployment.</span></span> 
  
     ![執行 Start-CsClsLogging。](../../media/Ops_CLS_Show_and_Start_ClsLogging.jpg)
  
4. <span data-ttu-id="fd39b-132">若要開始其他案例，請使用**CsClsLogging** Cmdlet 及其他案例的名稱來執行，如下所示（例如，案例**驗證**）：</span><span class="sxs-lookup"><span data-stu-id="fd39b-132">To start another scenario, use the **Start-CsClsLogging** cmdlet with the name of the additional scenario to run as follows (for example, the scenario **Authentication**):</span></span>
    
   ```PowerShell
   Start-CsClsLogging -Scenario Authentication
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="fd39b-133">您可以隨時在任何指定電腦上執行兩種情況。</span><span class="sxs-lookup"><span data-stu-id="fd39b-133">You can have a total of two scenarios running on any given computer at any time.</span></span> <span data-ttu-id="fd39b-134">如果命令是全域在範圍中，則您部署中的所有電腦都會執行案例或案例。</span><span class="sxs-lookup"><span data-stu-id="fd39b-134">If the command is global in scope, all of the computers in your deployment will run the scenario or scenarios.</span></span> <span data-ttu-id="fd39b-135">若要開始第三個案例，您必須停止記錄您想要在其上執行新案例的電腦、池、網站或全域範圍。</span><span class="sxs-lookup"><span data-stu-id="fd39b-135">To start a third scenario, you must stop logging on the computer, pool, site, or global scope that you want to run the new scenario on.</span></span> <span data-ttu-id="fd39b-136">如果您已開始全域範圍，您可以在一或多部電腦和池上停止記錄一或兩個案例的記錄。</span><span class="sxs-lookup"><span data-stu-id="fd39b-136">If you have started a global scope, you can stop logging for one or both of the scenarios on one or more computers and pools.</span></span> 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a><span data-ttu-id="fd39b-137">使用 [高級命令] 在 Windows PowerShell 中執行開始 CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="fd39b-137">To run Start-CsClsLogging with Windows PowerShell using advanced commands</span></span>

1. <span data-ttu-id="fd39b-138">啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="fd39b-138">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="fd39b-139">還有其他參數可供您記錄管理命令。</span><span class="sxs-lookup"><span data-stu-id="fd39b-139">Additional parameters are available to manage the logging commands.</span></span> <span data-ttu-id="fd39b-140">您可以使用 [持續時間] 來調整案例執行的時間長度。</span><span class="sxs-lookup"><span data-stu-id="fd39b-140">You can use -Duration to adjust the length of time for the scenario to run.</span></span> <span data-ttu-id="fd39b-141">您也可以定義電腦（一份電腦完整功能變數名稱（Fqdn），由逗號或池分隔，您想要執行記錄的池以逗號分隔的 Fqdn 清單。</span><span class="sxs-lookup"><span data-stu-id="fd39b-141">You also can define -Computers, a list of computer fully qualified domain names (FQDNs) separated by a comma, or -Pools, a comma separated list of FQDNs for pools that you want to run logging on.</span></span>
    
    <span data-ttu-id="fd39b-142">您在「pool01.contoso.net」的 [UserReplicator] 案例中開機記錄會話。</span><span class="sxs-lookup"><span data-stu-id="fd39b-142">You start a logging session for the UserReplicator scenario on the pool "pool01.contoso.net".</span></span> <span data-ttu-id="fd39b-143">您也可以在8小時定義記錄會話的持續時間。</span><span class="sxs-lookup"><span data-stu-id="fd39b-143">You also define the duration of the logging session at 8 hours.</span></span> <span data-ttu-id="fd39b-144">若要這樣做，請輸入：</span><span class="sxs-lookup"><span data-stu-id="fd39b-144">To do this, type:</span></span>
    
   ```PowerShell
   Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
   ```

    <span data-ttu-id="fd39b-145">這個案例的成功執行會傳回如下所示的結果：</span><span class="sxs-lookup"><span data-stu-id="fd39b-145">The successful execution of this scenario returns a result like the following:</span></span>
    
     ![執行 Start-CsClsLogging。](../../media/Ops_CsClsLogging_UserReplicator_Exp.jpg)
  
<span data-ttu-id="fd39b-147">請注意，在這個範例中，AlwaysOn 案例正在執行，且 UserReplicator 案例正在執行。</span><span class="sxs-lookup"><span data-stu-id="fd39b-147">Note that in this example, the AlwaysOn scenario is running and the UserReplicator scenario is running.</span></span> 
    
## <a name="stop-the-centralized-logging-service-log-capture"></a><span data-ttu-id="fd39b-148">停止集中式記錄服務記錄捕獲</span><span class="sxs-lookup"><span data-stu-id="fd39b-148">Stop the Centralized Logging Service log capture</span></span>
<span data-ttu-id="fd39b-149"><a name="stop"> </a></span><span class="sxs-lookup"><span data-stu-id="fd39b-149"></span></span>

<span data-ttu-id="fd39b-150">您可以停止目前正在執行的記錄會話與 CsClsLogging Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fd39b-150">You can stop a currently running logging session with the Stop-CsClsLogging cmdlet.</span></span> <span data-ttu-id="fd39b-151">一般來說，在許多情況下，您不需要停止記錄會話。</span><span class="sxs-lookup"><span data-stu-id="fd39b-151">Generally, there aren't many situations in which you would need to stop a logging session.</span></span> <span data-ttu-id="fd39b-152">例如，您可以搜尋記錄並變更配置，而不需要先停止記錄。</span><span class="sxs-lookup"><span data-stu-id="fd39b-152">For example, you can search logs and change configurations without first needing to stop logging.</span></span> <span data-ttu-id="fd39b-153">如果您有兩種情況（例如，AlwaysOn 和 UserReplicator），而您需要收集驗證的相關資訊，您必須先停止其他案例（全域、網站、池或電腦範圍），才能開始執行到驗證案例。</span><span class="sxs-lookup"><span data-stu-id="fd39b-153">If you have two scenarios running, for example AlwaysOn and UserReplicator, and you need to collect information related to Authentication, you will need to stop one of the other scenarios (at a global, site, pool or computer scope) before you can start running to Authentication scenario.</span></span> <span data-ttu-id="fd39b-154">如需詳細資訊，請參閱[停止 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="fd39b-154">For details, see [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="fd39b-155">在決定您可以在指定的部署、池或電腦上執行哪些案例時，您必須記住，**每個電腦**只能執行兩個案例： AlwaysOn 與一個自訂案例。</span><span class="sxs-lookup"><span data-stu-id="fd39b-155">When determining what scenarios you can run on a given deployment, pool or computer, you need to remember that you are limited to running two scenarios **per computer**: AlwaysOn and one custom scenario.</span></span> <span data-ttu-id="fd39b-156">如果您要記錄池中的活動，您應該將一個池視為單一實體。</span><span class="sxs-lookup"><span data-stu-id="fd39b-156">If you are logging activity on a pool, you should treat a pool as a single entity.</span></span> <span data-ttu-id="fd39b-157">在大部分的情況下，在池中的每個電腦上執行不同的案例不是很有意義的。</span><span class="sxs-lookup"><span data-stu-id="fd39b-157">In most cases, it would not make sense to run different scenarios on each computer in a pool.</span></span> <span data-ttu-id="fd39b-158">您可以在收集資料時查看問題，並思考在整個部署中的指定電腦上最有意義的案例，這是很有説明的。</span><span class="sxs-lookup"><span data-stu-id="fd39b-158">It does make sense to look at the problem that you are collecting data about and think about what scenario makes the most sense on a given computer in the overall deployment.</span></span> <span data-ttu-id="fd39b-159">例如，如果您認為 UserReplicator 案例，在 Edge 伺服器或 Edge 池中執行 UserReplicator 時，會有非常小的值。</span><span class="sxs-lookup"><span data-stu-id="fd39b-159">For example, if you consider the UserReplicator scenario, there would be very little value in running UserReplicator on an Edge Server or Edge pool.</span></span> 
  
<span data-ttu-id="fd39b-160">在您瞭解問題及影響範圍之後，您應該謹慎選擇要在哪些電腦和池中執行哪些案例。</span><span class="sxs-lookup"><span data-stu-id="fd39b-160">After you understand the problem and the scope of the impact, you should make careful choices about what scenarios to run on which computers and pools.</span></span> <span data-ttu-id="fd39b-161">雖然 AlwaysOn 作用中的應用程式會在各種提供者上收集資訊，但 AlwaysOn 情況是有意義的，因為它會在特定的電腦或池中只有應用程式值。</span><span class="sxs-lookup"><span data-stu-id="fd39b-161">While the AlwaysOn scenario makes sense for a wide scope application because it collects information on a wide variety of providers, specific scenarios only have application value on specific computers or pools.</span></span> <span data-ttu-id="fd39b-162">此外，您也應該小心地開機記錄會話，而不需要先瞭解特定案例的價值。</span><span class="sxs-lookup"><span data-stu-id="fd39b-162">Also, you should take caution when randomly starting up a logging session without first understanding the value of a given scenario.</span></span> <span data-ttu-id="fd39b-163">如果您使用的是錯誤的案例，或是您使用適合工作的案例，且您在錯誤的範圍（全域、網站、池或電腦）中套用案例，您就可以取得可疑的資料，這並不是很實用的，就像您沒有執行該案例一樣。</span><span class="sxs-lookup"><span data-stu-id="fd39b-163">If you use the wrong scenario, or if you use a scenario that is appropriate for the task and you apply the scenario at the wrong scope (be it global, site, pool, or computer), you can get questionable data that is not very useful—as if you didn't run the scenario at all.</span></span>
  
<span data-ttu-id="fd39b-164">若要使用商務用 Skype Server Management 命令介面控制集中式記錄服務的功能，您必須是 CsAdministrator 或 CsServerAdministrator 角色的存取控制（RBAC）安全性群組的成員，或是自訂的 RBAC 角色包含這兩個群組的其中一個。</span><span class="sxs-lookup"><span data-stu-id="fd39b-164">To control the Centralized Logging Service functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="fd39b-165">若要傳回已指派這個 Cmdlet 的所有 RBAC 角色清單（包括您自行建立的任何自訂 RBAC 角色），請從商務用 Skype Server 管理命令介面或 Windows PowerShell 提示中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="fd39b-165">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="fd39b-166">例如：</span><span class="sxs-lookup"><span data-stu-id="fd39b-166">For example:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> <span data-ttu-id="fd39b-167">您可能會想知道：現在您已啟用記錄功能，這些記錄會保留在哪裡？</span><span class="sxs-lookup"><span data-stu-id="fd39b-167">So you may be wondering: Now that you've enabled logging, where are the logs kept?</span></span> <span data-ttu-id="fd39b-168">由於您將使用傳送至 CLS 代理程式的管理命令介面查詢來存取儲存在記錄中的資訊，因此您可以將結果輸出為幾種可能的檔案格式，而在每個伺服器上，CLS 代理程式都能讓其記錄保持不太重要的意義。</span><span class="sxs-lookup"><span data-stu-id="fd39b-168">Since you'll access the information stored in the logs using management shell queries sent to the CLS Agents, and you can output the results to several possible file formats, where on each server a CLS Agent keeps its records isn't actually important to know.</span></span>  <span data-ttu-id="fd39b-169">記錄檔可以儲存在您指定的位置，並使用各種不同的工具讀取及分析，包括**Snooper**及任何可讀取文字檔（例如**notepad.exe**）的工具。</span><span class="sxs-lookup"><span data-stu-id="fd39b-169">The log files can be saved to a location you specify and  read and analyzed using a variety of tools, including **Snooper.exe** and any tool that can read a text file, such as **Notepad.exe**.</span></span> <span data-ttu-id="fd39b-170">Snooper 是商務用 Skype Server 2015 調試工具的一部分，可在[網頁版下載](https://go.microsoft.com/fwlink/p/?LinkId=285257)中取得。</span><span class="sxs-lookup"><span data-stu-id="fd39b-170">Snooper.exe is part of the Skype for Business Server 2015 Debug Tools and is available as a [Web download](https://go.microsoft.com/fwlink/p/?LinkId=285257).</span></span>

### <a name="to-stop-a-currently-running-centralized-logging-service-session"></a><span data-ttu-id="fd39b-171">停止目前正在執行的集中式記錄服務會話</span><span class="sxs-lookup"><span data-stu-id="fd39b-171">To stop a currently running Centralized Logging Service session</span></span>

1. <span data-ttu-id="fd39b-172">啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="fd39b-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="fd39b-173">在集中式記錄服務中輸入下列命令，以查詢目前正在執行的案例：</span><span class="sxs-lookup"><span data-stu-id="fd39b-173">Query the Centralized Logging Service to find out what scenarios are currently running by typing the following:</span></span>
    
   ```PowerShell
   Show-CsClsLogging
   ```

   ![呼叫 Show-CsCl 之後的 Windows PowerShell 主控台](../../media/Ops_Show_Stop_CsClsLogging.jpg)
  
   <span data-ttu-id="fd39b-175">CsClsLogging 的結果就是執行中之案例的摘要，以及它們正在執行的範圍。</span><span class="sxs-lookup"><span data-stu-id="fd39b-175">The result of Show-CsClsLogging is a summary of the scenarios that are running and what scope they are running in.</span></span> <span data-ttu-id="fd39b-176">如需詳細資訊，請參閱[顯示-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="fd39b-176">For details, see [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps).</span></span>
    
3. <span data-ttu-id="fd39b-177">若要停止目前正在執行的記錄會話與特定案例，請輸入：</span><span class="sxs-lookup"><span data-stu-id="fd39b-177">To stop a currently running logging session with a specific scenario, type:</span></span>
    
   ```PowerShell
   Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
   ```
   <span data-ttu-id="fd39b-178">例如：</span><span class="sxs-lookup"><span data-stu-id="fd39b-178">For example:</span></span>
    
   ```PowerShell
   Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
   ```

   <span data-ttu-id="fd39b-179">這個命令會在 pool01.contoso.net 上停止記錄 UserReplicatior 案例。</span><span class="sxs-lookup"><span data-stu-id="fd39b-179">This command will stop logging with the UserReplicatior scenario on pool01.contoso.net.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fd39b-180">使用 UserReplicator 案例在這個記錄會話期間建立的記錄不會被刪除。</span><span class="sxs-lookup"><span data-stu-id="fd39b-180">Logs created during this logging session using the UserReplicator scenario are not deleted.</span></span> <span data-ttu-id="fd39b-181">您仍可使用 [搜尋-CsClsLogging] 命令來執行搜尋的記錄。</span><span class="sxs-lookup"><span data-stu-id="fd39b-181">The logging is still available for you to execute searches against using the Search-CsClsLogging command.</span></span> <span data-ttu-id="fd39b-182">如需詳細資訊，請參閱[搜尋-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="fd39b-182">For details, see [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps).</span></span> 
  
<span data-ttu-id="fd39b-183">作為開始 CsClsLogging 的操作命令，Stop CsClsLogging Cmdlet 會結束記錄會話，由案例定義，並保留記錄會話所建立的記錄。</span><span class="sxs-lookup"><span data-stu-id="fd39b-183">Acting as the companion command to Start-CsClsLogging, the Stop-CsClsLogging cmdlet ends the logging session, defined by scenarios, and retains the logs created by the logging session.</span></span> <span data-ttu-id="fd39b-184">您可以隨時在指定的電腦上執行兩種案例。</span><span class="sxs-lookup"><span data-stu-id="fd39b-184">You can run two scenarios on a given computer at any time.</span></span> <span data-ttu-id="fd39b-185">停止某個案例以使用其他案例收集資訊的方法，是您可以在大部分工作負載疑難排解期間執行的一般工作。</span><span class="sxs-lookup"><span data-stu-id="fd39b-185">The method of stopping one scenario to gather information using another scenario is a common task that you can perform during most workload troubleshooting.</span></span>
## <a name="see-also"></a><span data-ttu-id="fd39b-186">另請參閱</span><span class="sxs-lookup"><span data-stu-id="fd39b-186">See also</span></span>
<span data-ttu-id="fd39b-187"><a name="stop"> </a></span><span class="sxs-lookup"><span data-stu-id="fd39b-187"></span></span>

[<span data-ttu-id="fd39b-188">商務用 Skype 2015 中的集中式記錄服務</span><span class="sxs-lookup"><span data-stu-id="fd39b-188">Centralized Logging Service in Skype for Business 2015</span></span>](centralized-logging-service.md)
