---
title: 使用 Start 進行集中式記錄服務以捕獲記錄
description: 使用 Start 進行集中式記錄服務以捕獲記錄。
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
ms.openlocfilehash: 6321af0b12f3650d3b741e65968849332b53af45
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580219"
---
# <a name="using-start-for-the-centralized-logging-service-to-capture-logs-in-lync-server-2013"></a><span data-ttu-id="e7293-103">使用 Start 進行集中式記錄服務以在 Lync Server 2013 中捕獲記錄</span><span class="sxs-lookup"><span data-stu-id="e7293-103">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7293-104">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="e7293-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="e7293-105">若要使用集中式記錄服務來捕獲追蹤記錄檔，您會發出命令，以開始登入一或多部電腦及集區。</span><span class="sxs-lookup"><span data-stu-id="e7293-105">To capture trace logs using the Centralized Logging Service, you issue a command to begin logging on one or more computers and pools.</span></span> <span data-ttu-id="e7293-106">您也可以發出參數，定義哪些電腦或集區、要執行哪些案例 (例如，AlwaysOn、其他預先定義的案例或您已建立的案例) 、哪些 Lync Server 元件 (例如，S4、SipStack) 追蹤。</span><span class="sxs-lookup"><span data-stu-id="e7293-106">You also issue parameters that define which computers or pools, what scenarios to run (for example, AlwaysOn, another predefined scenario, or a scenario you have created), what Lync Server components (for example, S4, SipStack) to trace.</span></span>

<span data-ttu-id="e7293-107">為了擷取正確的資訊，您必須確定使用正確的案例來收集問題的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e7293-107">To capture the right information, you need to make sure you use the right scenario to collect information that is relevant to the problem.</span></span> <span data-ttu-id="e7293-108">在集中式記錄服務中，案例是指根據伺服器元件的集合、記錄層級和旗標來開啟記錄的概念，其效率更高，而且在每個伺服器基礎上都必須定義這些元素時非常實用。</span><span class="sxs-lookup"><span data-stu-id="e7293-108">In the Centralized Logging Service, a scenario is the concept of turning logging on based on a collection of server components, logging levels, and flags, which is much more efficient and useful than having to define these elements on a per-server basis.</span></span> <span data-ttu-id="e7293-109">您可以定義及指定要執行的案例，這些案例會在基礎結構範圍內的所有伺服器和集區上持續執行。</span><span class="sxs-lookup"><span data-stu-id="e7293-109">You define and specify a scenario to run and the scenario is run consistently across all servers and pools in the scope of the infrastructure.</span></span>

<span data-ttu-id="e7293-p103">預設案例稱為 **AlwaysOn**。AlwaysOn 的預定目的是持續執行案例 (如案例名稱所指)。AlwaysOn 案例針對許多最常見的伺服器元件，收集資訊層級的資訊 (請注意，資訊記錄層次除了資訊訊息之外，還包含 [嚴重]、[錯誤] 及 [警告])。AlwaysOn 會收集發生問題前後及期間的資訊。這與之前的記錄工具 (例如 OCSLogger) 的一般行為大不相同。您會在發生問題之後執行 OCSLogger，這讓疑難排解工作更加困難，因為您擁有的資料只會被動回應，而無法主動解決問題。如果 AlwaysOn 所包含的資訊，不是您想要指向問題元件及指出修正步驟的資訊 (在 AlwaysOn 提供者的深度和廣度下，此情形並不常見)，AlwaysOn 會指出合理的資訊層級，以決定必須執行的其他動作，例如建立新的案例、收集其他資訊、執行其他搜尋以收集更集中的詳細資料等。</span><span class="sxs-lookup"><span data-stu-id="e7293-p103">The default scenario is called **AlwaysOn**. The intended purpose for AlwaysOn is to run the scenario constantly, as the name of the scenario implies. The AlwaysOn scenario collects Info level information (note that Info logging level includes Fatal, Error, and Warning in addition to Info messages) for many of the most common server components. AlwaysOn collects information before, during, and after a problem occurs. This differs dramatically from the typical behavior of previous logging tools such as OCSLogger. You ran OCSLogger after the problem had already occurred, making your troubleshooting efforts more difficult because the data that you have is reactive, not proactive. If AlwaysOn does not contain the information that you are looking for in order to point to the problem component and indicate a course of action to fix it (which is not likely given the breadth and depth of providers in AlwaysOn), it will indicate a reasonable level of information to determine what else you need to do, such as creating a new scenario, gather other information, run a different search to collect more focused details, and so on.</span></span>

<span data-ttu-id="e7293-117">集中式記錄服務提供兩種方式發出命令。</span><span class="sxs-lookup"><span data-stu-id="e7293-117">The Centralized Logging Service provides two ways to issue commands.</span></span> <span data-ttu-id="e7293-118">許多主題透過 Lync Server 管理命令介面使用 Windows PowerShell，已專注于 squarely。</span><span class="sxs-lookup"><span data-stu-id="e7293-118">A number of topics have been focused squarely on using Windows PowerShell through the Lync Server Management Shell.</span></span> <span data-ttu-id="e7293-119">使用許多複雜設定和命令的能力，可對 Windows PowerShell 以進行集中式記錄服務使用。</span><span class="sxs-lookup"><span data-stu-id="e7293-119">The ability to use a number of complex configurations and commands favors Windows PowerShell for Centralized Logging Service use.</span></span> <span data-ttu-id="e7293-120">由於 Windows PowerShell 透過 Lync Server 管理命令介面，在 Lync Server 中的所有功能幾乎都十分廣泛，所以只討論 Windows PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="e7293-120">Because Windows PowerShell through the Lync Server Management Shell is nearly ubiquitous for all functions in Lync Server, only the Windows PowerShell commands are discussed.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="e7293-121">如果您決定使用命令列中可用的有限命令集，您可以輸入 CLSController.exe 以取得的說明 <CODE>ClsController.exe</CODE> 。</span><span class="sxs-lookup"><span data-stu-id="e7293-121">If you decide to use the limited command set available from the command line, you can get help with CLSController.exe by typing <CODE>ClsController.exe</CODE>.</span></span> <span data-ttu-id="e7293-122">根據預設， <STRONG>ClsController.exe</STRONG> 會安裝在目錄 C:\Program Files\Microsoft Lync Server 2013 \ ClsAgent。</span><span class="sxs-lookup"><span data-stu-id="e7293-122">By default, <STRONG>ClsController.exe</STRONG> is installed in the directory C:\Program Files\Microsoft Lync Server 2013\ClsAgent.</span></span>



</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a><span data-ttu-id="e7293-123">使用基本命令以 Windows PowerShell 執行 Start-CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="e7293-123">To run Start-CsClsLogging with Windows PowerShell using basic commands</span></span>

1.  <span data-ttu-id="e7293-124">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="e7293-124">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e7293-125">輸入下列命令，以集中式記錄服務開機記錄案例：</span><span class="sxs-lookup"><span data-stu-id="e7293-125">Start a logging scenario with the Centralized Logging Service by typing the following:</span></span>
    
        Start-CsClsLogging -Scenario <name of scenario>
    
    <span data-ttu-id="e7293-126">例如，若要啟動 **AlwaysOn** 案例，請輸入：</span><span class="sxs-lookup"><span data-stu-id="e7293-126">For example, to start the **AlwaysOn** scenario, type:</span></span>
    
        Start-CsClsLogging -Scenario AlwaysOn
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="e7293-127">AlwaysOn 案例沒有預設期間。</span><span class="sxs-lookup"><span data-stu-id="e7293-127">The AlwaysOn scenario has no default duration.</span></span> <span data-ttu-id="e7293-128">此案例會一直執行，直到您使用 <STRONG>Stop-CsClsLogging</STRONG> Cmdlet 明確加以停止。</span><span class="sxs-lookup"><span data-stu-id="e7293-128">This scenario will run until you explicitly stop it with the <STRONG>Stop-CsClsLogging</STRONG> cmdlet.</span></span> <span data-ttu-id="e7293-129">如需詳細資訊，請參閱＜<A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>＞。</span><span class="sxs-lookup"><span data-stu-id="e7293-129">For details, see <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span></span> <span data-ttu-id="e7293-130">其他所有案例的預設期間為 4 小時。</span><span class="sxs-lookup"><span data-stu-id="e7293-130">For all other scenarios, the default duration is 4 hours.</span></span>

    
    </div>

3.  <span data-ttu-id="e7293-131">按 Enter 鍵執行命令。</span><span class="sxs-lookup"><span data-stu-id="e7293-131">Press Enter to run the command.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="e7293-132">可能需要一點時間 (30 到 60 秒) 才能執行命令，並接收部署中的電腦傳回的狀態。</span><span class="sxs-lookup"><span data-stu-id="e7293-132">It may take a short amount of time (30 to 60 seconds) for the commands to run and to receive the status back from the computers in your deployment.</span></span>

    
    </div>
    
    <span data-ttu-id="e7293-133">![執行 Start-CsClsLogging。](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "執行 Start-CsClsLogging。")</span><span class="sxs-lookup"><span data-stu-id="e7293-133">![Running Start-CsClsLogging.](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Running Start-CsClsLogging.")</span></span>

4.  <span data-ttu-id="e7293-134">若要開始另一種情況，請使用 **Start-CsClsLogging** Cmdlet 及其他案例的名稱來執行，如下所示 (例如，案例 **驗證**) ：</span><span class="sxs-lookup"><span data-stu-id="e7293-134">To start another scenario, use the **Start-CsClsLogging** cmdlet with the name of the additional scenario to run as follows (for example, the scenario **Authentication**):</span></span>
    
        Start-CsClsLogging -Scenario Authentication
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="e7293-135">在任何時候，最多可以在任何指定的電腦上執行兩個案例。</span><span class="sxs-lookup"><span data-stu-id="e7293-135">You can have a total of two scenarios running on any given computer at any time.</span></span> <span data-ttu-id="e7293-136">如果命令的範圍為全域，部署中的所有電腦都會執行這些案例。</span><span class="sxs-lookup"><span data-stu-id="e7293-136">If the command is global in scope, all of the computers in your deployment will run the scenario or scenarios.</span></span> <span data-ttu-id="e7293-137">若要啟動第三個案例，您必須從要執行新案例的電腦、集區、網站或全域範圍停止記錄。</span><span class="sxs-lookup"><span data-stu-id="e7293-137">To start a third scenario, you must stop logging on the computer, pool, site, or global scope that you want to run the new scenario on.</span></span> <span data-ttu-id="e7293-138">如果已啟動全域範圍，您可以在一或多部電腦和集區上停止記錄一或兩個案例。</span><span class="sxs-lookup"><span data-stu-id="e7293-138">If you have started a global scope, you can stop logging for one or both of the scenarios on one or more computers and pools.</span></span> <span data-ttu-id="e7293-139">如需有關管理正在執行之案例的詳細資訊，請參閱<A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">在 Lync Server 2013 和 Stop-CsClsLogging 中使用「集中式記錄」服務的 Using Stop</A> 。 <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A></span><span class="sxs-lookup"><span data-stu-id="e7293-139">For details about managing which scenarios are running, see <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">Using Stop for the Centralized Logging Service in Lync Server 2013</A> and <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a><span data-ttu-id="e7293-140">使用 Windows PowerShell 使用 advanced 命令執行 Start-CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="e7293-140">To run Start-CsClsLogging with Windows PowerShell using advanced commands</span></span>

1.  <span data-ttu-id="e7293-141">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="e7293-141">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e7293-142">您可以使用其他參數管理記錄命令。</span><span class="sxs-lookup"><span data-stu-id="e7293-142">Additional parameters are available to manage the logging commands.</span></span> <span data-ttu-id="e7293-143">您可以使用 –Duration 調整執行案例的時間長度。</span><span class="sxs-lookup"><span data-stu-id="e7293-143">You can use –Duration to adjust the length of time for the scenario to run.</span></span> <span data-ttu-id="e7293-144">您也可以定義 –Computers，以逗號分隔列出完整網域名稱 (FQDN)；或定義 –Pools，以逗號分隔列出執行記錄所在集區的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e7293-144">You also can define –Computers, a list of computer fully qualified domain names (FQDNs) separated by a comma, or –Pools, a comma separated list of FQDNs for pools that you want to run logging on.</span></span>
    
    <span data-ttu-id="e7293-145">您為集區 "pool01.contoso.net" 上的 *UserReplicator* 案例開始記錄會話。</span><span class="sxs-lookup"><span data-stu-id="e7293-145">You start a logging session for the *UserReplicator* scenario on the pool "pool01.contoso.net".</span></span> <span data-ttu-id="e7293-146">您也可以將記錄工作階段期間定義為 8 小時。</span><span class="sxs-lookup"><span data-stu-id="e7293-146">You also define the duration of the logging session at 8 hours.</span></span> <span data-ttu-id="e7293-147">若要執行這項操作，請輸入：</span><span class="sxs-lookup"><span data-stu-id="e7293-147">To do this, type:</span></span>
    
        Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
    
    <span data-ttu-id="e7293-148">成功執行此案例會傳回類似如下的結果：</span><span class="sxs-lookup"><span data-stu-id="e7293-148">The successful execution of this scenario returns a result like the following:</span></span>
    
    <span data-ttu-id="e7293-149">![執行 Start-CsClsLogging。](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "執行 Start-CsClsLogging。")</span><span class="sxs-lookup"><span data-stu-id="e7293-149">![Running Start-CsClsLogging.](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Running Start-CsClsLogging.")</span></span>
    
    <span data-ttu-id="e7293-150">請注意，在此範例中，AlwaysOn 案例和 UserReplicator 案例都在執行中。</span><span class="sxs-lookup"><span data-stu-id="e7293-150">Note that in this example, the AlwaysOn scenario is running and the UserReplicator scenario is running.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e7293-151">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e7293-151">See Also</span></span>


[<span data-ttu-id="e7293-152">Lync Server 2013 中的集中式記錄服務概述</span><span class="sxs-lookup"><span data-stu-id="e7293-152">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

