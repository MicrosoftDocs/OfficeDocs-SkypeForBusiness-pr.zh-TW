---
title: 使用「開始」進行集中式記錄服務來捕獲記錄
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Start for the Centralized Logging Service to capture logs
ms:assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687958(v=OCS.15)
ms:contentKeyID: 49733543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75090036b7120c8af7cda132c26d5b4fb02d3dab
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-start-for-the-centralized-logging-service-to-capture-logs-in-lync-server-2013"></a><span data-ttu-id="6008d-102">在 Lync Server 2013 中使用 [開始使用集中式記錄服務] 來捕獲記錄</span><span class="sxs-lookup"><span data-stu-id="6008d-102">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6008d-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="6008d-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="6008d-104">若要使用集中式記錄服務來捕獲追蹤記錄，您需要發出命令，以便在一或多部電腦和池上開始記錄。</span><span class="sxs-lookup"><span data-stu-id="6008d-104">To capture trace logs using the Centralized Logging Service, you issue a command to begin logging on one or more computers and pools.</span></span> <span data-ttu-id="6008d-105">您也可以發出定義哪些電腦或池、要執行哪些情況（例如，AlwaysOn、另一個預先定義的案例或您所建立之案例）的參數，以及要追蹤哪些 Lync Server 元件（例如，S4、SipStack）。</span><span class="sxs-lookup"><span data-stu-id="6008d-105">You also issue parameters that define which computers or pools, what scenarios to run (for example, AlwaysOn, another predefined scenario, or a scenario you have created), what Lync Server components (for example, S4, SipStack) to trace.</span></span>

<span data-ttu-id="6008d-106">若要捕獲正確的資訊，您必須確認使用正確的案例，才能收集與問題相關的資訊。</span><span class="sxs-lookup"><span data-stu-id="6008d-106">To capture the right information, you need to make sure you use the right scenario to collect information that is relevant to the problem.</span></span> <span data-ttu-id="6008d-107">在集中式記錄服務中，案例是根據伺服器元件集合、記錄層級和旗標來開啟記錄的概念，這比要在每個伺服器上定義這些元素更有效率且更有用。</span><span class="sxs-lookup"><span data-stu-id="6008d-107">In the Centralized Logging Service, a scenario is the concept of turning logging on based on a collection of server components, logging levels, and flags, which is much more efficient and useful than having to define these elements on a per-server basis.</span></span> <span data-ttu-id="6008d-108">您定義並指定要執行的案例，並在整個基礎結構範圍中的所有伺服器和池上一致地執行該案例。</span><span class="sxs-lookup"><span data-stu-id="6008d-108">You define and specify a scenario to run and the scenario is run consistently across all servers and pools in the scope of the infrastructure.</span></span>

<span data-ttu-id="6008d-109">預設案例稱為 [ **AlwaysOn**]。</span><span class="sxs-lookup"><span data-stu-id="6008d-109">The default scenario is called **AlwaysOn**.</span></span> <span data-ttu-id="6008d-110">AlwaysOn 的預期用途是經常執行該案例，因為案例的名稱所隱含。</span><span class="sxs-lookup"><span data-stu-id="6008d-110">The intended purpose for AlwaysOn is to run the scenario constantly, as the name of the scenario implies.</span></span> <span data-ttu-id="6008d-111">AlwaysOn 案例會收集資訊層級資訊（請注意，資訊記錄層級除了資訊訊息之外，還包含許多最常見伺服器元件的致命、錯誤和警告）。</span><span class="sxs-lookup"><span data-stu-id="6008d-111">The AlwaysOn scenario collects Info level information (note that Info logging level includes Fatal, Error, and Warning in addition to Info messages) for many of the most common server components.</span></span> <span data-ttu-id="6008d-112">AlwaysOn 會在問題發生之前、期間及之後收集資訊。</span><span class="sxs-lookup"><span data-stu-id="6008d-112">AlwaysOn collects information before, during, and after a problem occurs.</span></span> <span data-ttu-id="6008d-113">這與前一筆記錄工具（例如 OCSLogger）的一般行為有顯著的差異。</span><span class="sxs-lookup"><span data-stu-id="6008d-113">This differs dramatically from the typical behavior of previous logging tools such as OCSLogger.</span></span> <span data-ttu-id="6008d-114">您在問題發生之後執行了 OCSLogger，因為您所擁有的資料是被動而非主動，所以您的疑難排解工作變得更困難。</span><span class="sxs-lookup"><span data-stu-id="6008d-114">You ran OCSLogger after the problem had already occurred, making your troubleshooting efforts more difficult because the data that you have is reactive, not proactive.</span></span> <span data-ttu-id="6008d-115">如果 AlwaysOn 不包含您要尋找的資訊，而是要指向問題元件，並指出一個動作程式來修正它（不太可能是在 AlwaysOn 中提供提供者的廣度與深度），它會指出適當的資訊層級rmation 以判斷您需要執行的其他動作，例如建立新案例、收集其他資訊、執行不同的搜尋，以收集更專注的詳細資料等等。</span><span class="sxs-lookup"><span data-stu-id="6008d-115">If AlwaysOn does not contain the information that you are looking for in order to point to the problem component and indicate a course of action to fix it (which is not likely given the breadth and depth of providers in AlwaysOn), it will indicate a reasonable level of information to determine what else you need to do, such as creating a new scenario, gather other information, run a different search to collect more focused details, and so on.</span></span>

<span data-ttu-id="6008d-116">集中式記錄服務提供兩種方式來發出命令。</span><span class="sxs-lookup"><span data-stu-id="6008d-116">The Centralized Logging Service provides two ways to issue commands.</span></span> <span data-ttu-id="6008d-117">您可以透過 Lync Server 管理命令介面，在 Windows PowerShell 中，有許多主題是以焦點恰好的方式進行。</span><span class="sxs-lookup"><span data-stu-id="6008d-117">A number of topics have been focused squarely on using Windows PowerShell through the Lync Server Management Shell.</span></span> <span data-ttu-id="6008d-118">使用許多複雜的設定和命令的能力，有利於使用 Windows PowerShell 來集中式記錄服務。</span><span class="sxs-lookup"><span data-stu-id="6008d-118">The ability to use a number of complex configurations and commands favors Windows PowerShell for Centralized Logging Service use.</span></span> <span data-ttu-id="6008d-119">因為 Windows PowerShell 透過 Lync server 管理命令介面幾乎無處不在 Lync Server 中的所有函數，所以只討論 Windows PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="6008d-119">Because Windows PowerShell through the Lync Server Management Shell is nearly ubiquitous for all functions in Lync Server, only the Windows PowerShell commands are discussed.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="6008d-120">如果您決定使用可從命令列使用的有限命令集，您可以輸入<CODE>ClsController.exe</CODE>CLSController 以取得協助。</span><span class="sxs-lookup"><span data-stu-id="6008d-120">If you decide to use the limited command set available from the command line, you can get help with CLSController.exe by typing <CODE>ClsController.exe</CODE>.</span></span> <span data-ttu-id="6008d-121">根據預設， <STRONG>ClsController</STRONG>會安裝在目錄 C:\Program Files\Microsoft Lync Server 2013 \ ClsAgent 中。</span><span class="sxs-lookup"><span data-stu-id="6008d-121">By default, <STRONG>ClsController.exe</STRONG> is installed in the directory C:\Program Files\Microsoft Lync Server 2013\ClsAgent.</span></span>



</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a><span data-ttu-id="6008d-122">使用基本命令在 Windows PowerShell 中執行開始 CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="6008d-122">To run Start-CsClsLogging with Windows PowerShell using basic commands</span></span>

1.  <span data-ttu-id="6008d-123">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="6008d-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="6008d-124">輸入以下內容，以集中式記錄服務開機記錄案例：</span><span class="sxs-lookup"><span data-stu-id="6008d-124">Start a logging scenario with the Centralized Logging Service by typing the following:</span></span>
    
        Start-CsClsLogging -Scenario <name of scenario>
    
    <span data-ttu-id="6008d-125">例如，若要啟動**AlwaysOn**案例，請輸入：</span><span class="sxs-lookup"><span data-stu-id="6008d-125">For example, to start the **AlwaysOn** scenario, type:</span></span>
    
        Start-CsClsLogging -Scenario AlwaysOn
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="6008d-126">AlwaysOn 案例沒有預設的持續時間。</span><span class="sxs-lookup"><span data-stu-id="6008d-126">The AlwaysOn scenario has no default duration.</span></span> <span data-ttu-id="6008d-127">這個案例將會在您明確地停止使用<STRONG>CsClsLogging</STRONG> Cmdlet 之前執行。</span><span class="sxs-lookup"><span data-stu-id="6008d-127">This scenario will run until you explicitly stop it with the <STRONG>Stop-CsClsLogging</STRONG> cmdlet.</span></span> <span data-ttu-id="6008d-128">如需詳細資訊，請參閱<A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)">停止 CsClsLogging</A>。</span><span class="sxs-lookup"><span data-stu-id="6008d-128">For details, see <A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span></span> <span data-ttu-id="6008d-129">在所有其他案例中，預設期間是4小時。</span><span class="sxs-lookup"><span data-stu-id="6008d-129">For all other scenarios, the default duration is 4 hours.</span></span>

    
    </div>

3.  <span data-ttu-id="6008d-130">按 Enter 以執行命令。</span><span class="sxs-lookup"><span data-stu-id="6008d-130">Press Enter to run the command.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="6008d-131">您可能需要花很短的時間（30到60秒），才能執行這些命令，並從您的部署中的電腦接收傳回的狀態。</span><span class="sxs-lookup"><span data-stu-id="6008d-131">It may take a short amount of time (30 to 60 seconds) for the commands to run and to receive the status back from the computers in your deployment.</span></span>

    
    </div>
    
    <span data-ttu-id="6008d-132">![執行 Start-CsClsLogging。](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "執行 Start-CsClsLogging。")</span><span class="sxs-lookup"><span data-stu-id="6008d-132">![Running Start-CsClsLogging.](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Running Start-CsClsLogging.")</span></span>

4.  <span data-ttu-id="6008d-133">若要開始其他案例，請使用**CsClsLogging** Cmdlet 及其他案例的名稱來執行，如下所示（例如，案例**驗證**）：</span><span class="sxs-lookup"><span data-stu-id="6008d-133">To start another scenario, use the **Start-CsClsLogging** cmdlet with the name of the additional scenario to run as follows (for example, the scenario **Authentication**):</span></span>
    
        Start-CsClsLogging -Scenario Authentication
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="6008d-134">您可以隨時在任何指定電腦上執行兩種情況。</span><span class="sxs-lookup"><span data-stu-id="6008d-134">You can have a total of two scenarios running on any given computer at any time.</span></span> <span data-ttu-id="6008d-135">如果命令是全域在範圍中，則您部署中的所有電腦都會執行案例或案例。</span><span class="sxs-lookup"><span data-stu-id="6008d-135">If the command is global in scope, all of the computers in your deployment will run the scenario or scenarios.</span></span> <span data-ttu-id="6008d-136">若要開始第三個案例，您必須停止記錄您想要在其上執行新案例的電腦、池、網站或全域範圍。</span><span class="sxs-lookup"><span data-stu-id="6008d-136">To start a third scenario, you must stop logging on the computer, pool, site, or global scope that you want to run the new scenario on.</span></span> <span data-ttu-id="6008d-137">如果您已開始全域範圍，您可以在一或多部電腦和池上停止記錄一或兩個案例的記錄。</span><span class="sxs-lookup"><span data-stu-id="6008d-137">If you have started a global scope, you can stop logging for one or both of the scenarios on one or more computers and pools.</span></span> <span data-ttu-id="6008d-138">如需管理正在執行哪些案例的詳細資訊，請參閱<A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">在 Lync Server 2013 中針對集中式記錄服務使用 [停止</A>]，然後<A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)">CsClsLogging [停止</A>]。</span><span class="sxs-lookup"><span data-stu-id="6008d-138">For details about managing which scenarios are running, see <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">Using Stop for the Centralized Logging Service in Lync Server 2013</A> and <A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a><span data-ttu-id="6008d-139">使用 [高級命令] 在 Windows PowerShell 中執行開始 CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="6008d-139">To run Start-CsClsLogging with Windows PowerShell using advanced commands</span></span>

1.  <span data-ttu-id="6008d-140">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="6008d-140">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="6008d-141">還有其他參數可供您記錄管理命令。</span><span class="sxs-lookup"><span data-stu-id="6008d-141">Additional parameters are available to manage the logging commands.</span></span> <span data-ttu-id="6008d-142">您可以使用-Duration 來調整案例執行的時間長度。</span><span class="sxs-lookup"><span data-stu-id="6008d-142">You can use –Duration to adjust the length of time for the scenario to run.</span></span> <span data-ttu-id="6008d-143">您也可以在電腦上定義電腦的完整功能變數名稱（Fqdn）清單，並以逗號（或-Pool）分隔，您想要執行記錄的池以逗號分隔的 Fqdn 清單。</span><span class="sxs-lookup"><span data-stu-id="6008d-143">You also can define –Computers, a list of computer fully qualified domain names (FQDNs) separated by a comma, or –Pools, a comma separated list of FQDNs for pools that you want to run logging on.</span></span>
    
    <span data-ttu-id="6008d-144">您在「pool01.contoso.net」的 [ *UserReplicator* ] 案例中開機記錄會話。</span><span class="sxs-lookup"><span data-stu-id="6008d-144">You start a logging session for the *UserReplicator* scenario on the pool "pool01.contoso.net".</span></span> <span data-ttu-id="6008d-145">您也可以在8小時定義記錄會話的持續時間。</span><span class="sxs-lookup"><span data-stu-id="6008d-145">You also define the duration of the logging session at 8 hours.</span></span> <span data-ttu-id="6008d-146">若要這樣做，請輸入：</span><span class="sxs-lookup"><span data-stu-id="6008d-146">To do this, type:</span></span>
    
        Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
    
    <span data-ttu-id="6008d-147">這個案例的成功執行會傳回如下所示的結果：</span><span class="sxs-lookup"><span data-stu-id="6008d-147">The successful execution of this scenario returns a result like the following:</span></span>
    
    <span data-ttu-id="6008d-148">![執行 Start-CsClsLogging。](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "執行 Start-CsClsLogging。")</span><span class="sxs-lookup"><span data-stu-id="6008d-148">![Running Start-CsClsLogging.](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Running Start-CsClsLogging.")</span></span>
    
    <span data-ttu-id="6008d-149">請注意，在這個範例中，AlwaysOn 案例正在執行，且 UserReplicator 案例正在執行。</span><span class="sxs-lookup"><span data-stu-id="6008d-149">Note that in this example, the AlwaysOn scenario is running and the UserReplicator scenario is running.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6008d-150">請參閱</span><span class="sxs-lookup"><span data-stu-id="6008d-150">See Also</span></span>


[<span data-ttu-id="6008d-151">Lync Server 2013 中的集中式記錄服務概覽</span><span class="sxs-lookup"><span data-stu-id="6008d-151">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

