---
title: Lync Server 2013：針對集中式記錄服務使用停止功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Stop for the Centralized Logging Service
ms:assetid: 09ac093e-8f30-4874-84b4-12548ac8c898
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687964(v=OCS.15)
ms:contentKeyID: 49733549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 521328b688f90ca591abddb3e59e7d49ae771b15
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981823"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-stop-for-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="35639-102">在 Lync Server 2013 中針對集中式記錄服務使用停止功能</span><span class="sxs-lookup"><span data-stu-id="35639-102">Using Stop for the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35639-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="35639-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="35639-104">您可以停止目前正在執行的記錄會話與 CsClsLogging Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="35639-104">You can stop a currently running logging session with the Stop-CsClsLogging cmdlet.</span></span> <span data-ttu-id="35639-105">一般來說，在許多情況下，您不需要停止記錄會話。</span><span class="sxs-lookup"><span data-stu-id="35639-105">Generally, there aren’t many situations in which you would need to stop a logging session.</span></span> <span data-ttu-id="35639-106">例如，您可以搜尋記錄並變更配置，而不需要先停止記錄。</span><span class="sxs-lookup"><span data-stu-id="35639-106">For example, you can search logs and change configurations without first needing to stop logging.</span></span> <span data-ttu-id="35639-107">如果您有兩種情況（例如，AlwaysOn 和 UserReplicator），而您需要收集驗證的相關資訊，您必須先停止其他案例（全域、網站、池或電腦範圍），才能開始執行到驗證案例。</span><span class="sxs-lookup"><span data-stu-id="35639-107">If you have two scenarios running, for example AlwaysOn and UserReplicator, and you need to collect information related to Authentication, you will need to stop one of the other scenarios (at a global, site, pool or computer scope) before you can start running to Authentication scenario.</span></span> <span data-ttu-id="35639-108">如需詳細資訊，請參閱[停止 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)。</span><span class="sxs-lookup"><span data-stu-id="35639-108">For details, see [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="35639-109">在判斷您可以在指定的部署、池或電腦上執行哪些案例時，請記住，您只能在<STRONG>每台電腦</STRONG>上執行兩種案例。</span><span class="sxs-lookup"><span data-stu-id="35639-109">When determining what scenarios you can run on a given deployment, pool or computer, you need to remember that you are limited to running two scenarios <STRONG>per computer</STRONG>.</span></span> <span data-ttu-id="35639-110">如果您要記錄池中的活動，您應該將一個池視為單一實體。</span><span class="sxs-lookup"><span data-stu-id="35639-110">If you are logging activity on a pool, you should treat a pool as a single entity.</span></span> <span data-ttu-id="35639-111">在大部分的情況下，在池中的每個電腦上執行不同的案例不是很有意義的。</span><span class="sxs-lookup"><span data-stu-id="35639-111">In most cases, it would not make sense to run different scenarios on each computer in a pool.</span></span> <span data-ttu-id="35639-112">您可以在收集資料時查看問題，並思考在整個部署中的指定電腦上最有意義的案例，這是很有説明的。</span><span class="sxs-lookup"><span data-stu-id="35639-112">It does make sense to look at the problem that you are collecting data about and think about what scenario makes the most sense on a given computer in the overall deployment.</span></span> <span data-ttu-id="35639-113">例如，如果您認為 UserReplicator 案例，在 Edge 伺服器或 Edge 池中執行 UserReplicator 時，會有非常小的值。</span><span class="sxs-lookup"><span data-stu-id="35639-113">For example, if you consider the UserReplicator scenario, there would be very little value in running UserReplicator on an Edge Server or Edge pool.</span></span><BR><span data-ttu-id="35639-114">在您瞭解問題及影響範圍之後，您應該謹慎選擇要在哪些電腦和池中執行哪些案例。</span><span class="sxs-lookup"><span data-stu-id="35639-114">After you understand the problem and the scope of the impact, you should make careful choices about what scenarios to run on which computers and pools.</span></span> <span data-ttu-id="35639-115">雖然 AlwaysOn 作用中的應用程式會在各種提供者上收集資訊，但 AlwaysOn 情況是有意義的，因為它會在特定的電腦或池中只有應用程式值。</span><span class="sxs-lookup"><span data-stu-id="35639-115">While the AlwaysOn scenario makes sense for a wide scope application because it collects information on a wide variety of providers, specific scenarios only have application value on specific computers or pools.</span></span> <span data-ttu-id="35639-116">此外，您也應該小心地開機記錄會話，而不需要先瞭解特定案例的價值。</span><span class="sxs-lookup"><span data-stu-id="35639-116">Also, you should take caution when randomly starting up a logging session without first understanding the value of a given scenario.</span></span> <span data-ttu-id="35639-117">如果您使用的是錯誤的案例，或是您使用適合工作的案例，且您在錯誤的範圍（全域、網站、池或電腦）中套用案例，您就可以取得可疑的資料，這並不是很實用的，就像您沒有執行該案例一樣。</span><span class="sxs-lookup"><span data-stu-id="35639-117">If you use the wrong scenario, or if you use a scenario that is appropriate for the task and you apply the scenario at the wrong scope (be it global, site, pool, or computer), you can get questionable data that is not very useful—as if you didn't run the scenario at all.</span></span>



</div>

<span data-ttu-id="35639-118">若要使用 Lync Server 管理命令介面控制集中式記錄服務功能，您必須是 CsAdministrator 或 CsServerAdministrator 角色式存取控制（RBAC）安全性群組的成員，或是包含下列內容的自訂 RBAC 角色：這兩個群組的其中一個。</span><span class="sxs-lookup"><span data-stu-id="35639-118">To control the Centralized Logging Service functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="35639-119">若要傳回已指派這個 Cmdlet 的所有 RBAC 角色清單（包括您自行建立的任何自訂 RBAC 角色），請從 Lync Server 管理命令介面或 Windows PowerShell 提示字元執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="35639-119">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="35639-120">例如：</span><span class="sxs-lookup"><span data-stu-id="35639-120">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>

## <a name="to-stop-a-currently-running-centralized-logging-service-session"></a><span data-ttu-id="35639-121">停止目前正在執行的集中式記錄服務會話</span><span class="sxs-lookup"><span data-stu-id="35639-121">To stop a currently running Centralized Logging Service session</span></span>

1.  <span data-ttu-id="35639-122">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="35639-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="35639-123">在集中式記錄服務中輸入下列命令，以查詢目前正在執行的案例：</span><span class="sxs-lookup"><span data-stu-id="35639-123">Query the Centralized Logging Service to find out what scenarios are currently running by typing the following:</span></span>
    
        Show-CsClsLogging
    
    <span data-ttu-id="35639-124">呼叫 show-CsCl 之後![，在呼叫 CsCl](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "windows powershell 主控台")之後的 windows powershell 主控台</span><span class="sxs-lookup"><span data-stu-id="35639-124">![Windows PowerShell console after calling Show-CsCl](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "Windows PowerShell console after calling Show-CsCl")</span></span>
    
    <span data-ttu-id="35639-125">CsClsLogging 的結果就是執行中之案例的摘要，以及它們正在執行的範圍。</span><span class="sxs-lookup"><span data-stu-id="35639-125">The result of Show-CsClsLogging is a summary of the scenarios that are running and what scope they are running in.</span></span> <span data-ttu-id="35639-126">如需詳細資訊，請參閱[顯示-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)。</span><span class="sxs-lookup"><span data-stu-id="35639-126">For details, see [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging).</span></span>

3.  <span data-ttu-id="35639-127">若要停止目前正在執行的記錄會話與特定案例，請輸入：</span><span class="sxs-lookup"><span data-stu-id="35639-127">To stop a currently running logging session with a specific scenario, type:</span></span>
    
        Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
    
    <span data-ttu-id="35639-128">例如：</span><span class="sxs-lookup"><span data-stu-id="35639-128">For example:</span></span>
    
        Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
    
    <span data-ttu-id="35639-129">這個命令會在 pool01.contoso.net 上停止記錄 UserReplicatior 案例。</span><span class="sxs-lookup"><span data-stu-id="35639-129">This command will stop logging with the UserReplicatior scenario on pool01.contoso.net.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="35639-130">使用 UserReplicator 案例在這個記錄會話期間建立的記錄不會被刪除。</span><span class="sxs-lookup"><span data-stu-id="35639-130">Logs created during this logging session using the UserReplicator scenario are not deleted.</span></span> <span data-ttu-id="35639-131">您仍可使用 [搜尋-CsClsLogging] 命令來執行搜尋的記錄。</span><span class="sxs-lookup"><span data-stu-id="35639-131">The logging is still available for you to execute searches against using the Search-CsClsLogging command.</span></span> <span data-ttu-id="35639-132">如需詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">搜尋-CsClsLogging</A>。</span><span class="sxs-lookup"><span data-stu-id="35639-132">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</A>.</span></span>

    
    </div>

<span data-ttu-id="35639-133">作為開始 CsClsLogging 的操作命令，Stop CsClsLogging Cmdlet 會結束記錄會話，由案例定義，並保留記錄會話所建立的記錄。</span><span class="sxs-lookup"><span data-stu-id="35639-133">Acting as the companion command to Start-CsClsLogging, the Stop-CsClsLogging cmdlet ends the logging session, defined by scenarios, and retains the logs created by the logging session.</span></span> <span data-ttu-id="35639-134">您可以隨時在指定的電腦上執行兩種案例。</span><span class="sxs-lookup"><span data-stu-id="35639-134">You can run two scenarios on a given computer at any time.</span></span> <span data-ttu-id="35639-135">停止某個案例以使用其他案例收集資訊的方法，是您可以在大部分工作負載疑難排解期間執行的一般工作。</span><span class="sxs-lookup"><span data-stu-id="35639-135">The method of stopping one scenario to gather information using another scenario is a common task that you can perform during most workload troubleshooting.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="35639-136">請參閱</span><span class="sxs-lookup"><span data-stu-id="35639-136">See Also</span></span>


<span data-ttu-id="35639-137">[在 Lync Server 2013 中使用 [開始使用集中式記錄服務] 來捕獲記錄](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)</span><span class="sxs-lookup"><span data-stu-id="35639-137">[Using Start for the Centralized Logging Service to capture logs in Lync Server 2013](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)</span></span>  


[<span data-ttu-id="35639-138">Lync Server 2013 中的集中式記錄服務概覽</span><span class="sxs-lookup"><span data-stu-id="35639-138">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[<span data-ttu-id="35639-139">顯示-CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="35639-139">Show-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)  
[<span data-ttu-id="35639-140">開始-CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="35639-140">Start-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Start-CsClsLogging)  
[<span data-ttu-id="35639-141">停止 CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="35639-141">Stop-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

