---
title: Lync Server 2013： 將 Stop 用於集中式記錄服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Stop for the Centralized Logging Service
ms:assetid: 09ac093e-8f30-4874-84b4-12548ac8c898
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687964(v=OCS.15)
ms:contentKeyID: 49733549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9f1c662081b5a92d53f0658859d9fdee1a038d2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138634"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-stop-for-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="15da5-102">將 Stop 用於 Lync Server 2013 中的集中式的記錄服務</span><span class="sxs-lookup"><span data-stu-id="15da5-102">Using Stop for the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15da5-103">_**主題上次修改日期：** 2012年-11-01_</span><span class="sxs-lookup"><span data-stu-id="15da5-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="15da5-104">您可以用 Stop-CsClsLogging Cmdlet 來停止目前執行中的記錄工作階段。</span><span class="sxs-lookup"><span data-stu-id="15da5-104">You can stop a currently running logging session with the Stop-CsClsLogging cmdlet.</span></span> <span data-ttu-id="15da5-105">一般來說，並沒有很多狀況會需要停止記錄工作階段。</span><span class="sxs-lookup"><span data-stu-id="15da5-105">Generally, there aren’t many situations in which you would need to stop a logging session.</span></span> <span data-ttu-id="15da5-106">例如，您不需要先停止記錄，就可以搜尋記錄及變更設定。</span><span class="sxs-lookup"><span data-stu-id="15da5-106">For example, you can search logs and change configurations without first needing to stop logging.</span></span> <span data-ttu-id="15da5-107">如果您有兩個案例正在執行，例如 AlwaysOn 和 UserReplicator，而您需要收集有關驗證的資訊，則必須先停止其中一個案例 (在全域、網站、集區或電腦範圍)，才能開始執行驗證案例。</span><span class="sxs-lookup"><span data-stu-id="15da5-107">If you have two scenarios running, for example AlwaysOn and UserReplicator, and you need to collect information related to Authentication, you will need to stop one of the other scenarios (at a global, site, pool or computer scope) before you can start running to Authentication scenario.</span></span> <span data-ttu-id="15da5-108">如需詳細資訊，請參閱＜[Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)＞。</span><span class="sxs-lookup"><span data-stu-id="15da5-108">For details, see [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="15da5-109">在判斷您可以在給定的部署部署、集區或電腦上執行哪些案例時，必須記得您有「每部電腦」<STRONG></STRONG>只能執行兩個案例的限制。</span><span class="sxs-lookup"><span data-stu-id="15da5-109">When determining what scenarios you can run on a given deployment, pool or computer, you need to remember that you are limited to running two scenarios <STRONG>per computer</STRONG>.</span></span> <span data-ttu-id="15da5-110">如果您要在集區上記錄活動，則應將集區當做單一實體來處理。</span><span class="sxs-lookup"><span data-stu-id="15da5-110">If you are logging activity on a pool, you should treat a pool as a single entity.</span></span> <span data-ttu-id="15da5-111">在大部分情況下，在集區中的每部電腦上執行不同的案例並沒有意義。</span><span class="sxs-lookup"><span data-stu-id="15da5-111">In most cases, it would not make sense to run different scenarios on each computer in a pool.</span></span> <span data-ttu-id="15da5-112">但是查看您收集資料的相關問題，並思考在整體部署中，哪個案例對給定電腦的影響最大，這就有意義了。</span><span class="sxs-lookup"><span data-stu-id="15da5-112">It does make sense to look at the problem that you are collecting data about and think about what scenario makes the most sense on a given computer in the overall deployment.</span></span> <span data-ttu-id="15da5-113">例如，如果您考慮 UserReplicator 案例，會有極少的值在 Edge Server 或 Edge 集區上執行 UserReplicator。</span><span class="sxs-lookup"><span data-stu-id="15da5-113">For example, if you consider the UserReplicator scenario, there would be very little value in running UserReplicator on an Edge Server or Edge pool.</span></span><BR><span data-ttu-id="15da5-p103">在了解問題及影響的範圍之後，應謹慎選擇要在哪些電腦和集區上執行什麼案例。雖然 AlwaysOn 案例對大範圍的應用有意義，因為它會收集各種提供者的資訊，但是特定案例對特定電腦或集區只有應用價值。此外，在未了解給定案例的價值之前，就隨機啟動記錄工作階段的話，要特別小心。如果您使用錯誤的案例，或是所使用的案例適合該工作，而您將案例套用在錯誤的範圍 (可能是全域、網站、集區或電腦)，所得到的問題資料可能不是很有用，就像根本沒有執行案例一樣。</span><span class="sxs-lookup"><span data-stu-id="15da5-p103">After you understand the problem and the scope of the impact, you should make careful choices about what scenarios to run on which computers and pools. While the AlwaysOn scenario makes sense for a wide scope application because it collects information on a wide variety of providers, specific scenarios only have application value on specific computers or pools. Also, you should take caution when randomly starting up a logging session without first understanding the value of a given scenario. If you use the wrong scenario, or if you use a scenario that is appropriate for the task and you apply the scenario at the wrong scope (be it global, site, pool, or computer), you can get questionable data that is not very useful—as if you didn't run the scenario at all.</span></span>



</div>

<span data-ttu-id="15da5-118">若要使用 Lync Server 管理命令介面來控制的集中式記錄服務功能，您必須是 CsAdministrator 或 CsServerAdministrator 角色型存取控制 (RBAC) 安全性群組或包含的自訂 RBAC 角色的成員其中一個這兩個群組。</span><span class="sxs-lookup"><span data-stu-id="15da5-118">To control the Centralized Logging Service functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="15da5-119">若要傳回所有獲指派此 cmdlet 的 RBAC 角色清單 （包括您自行建立的任何自訂 RBAC 角色），請從 [Lync Server 管理命令介面或 Windows PowerShell 提示字元執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="15da5-119">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="15da5-120">例如：</span><span class="sxs-lookup"><span data-stu-id="15da5-120">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>

## <a name="to-stop-a-currently-running-centralized-logging-service-session"></a><span data-ttu-id="15da5-121">若要停止目前正在執行的集中式記錄服務工作階段</span><span class="sxs-lookup"><span data-stu-id="15da5-121">To stop a currently running Centralized Logging Service session</span></span>

1.  <span data-ttu-id="15da5-122">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="15da5-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="15da5-123">查詢集中式記錄服務若要了解哪些案例目前正在執行輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="15da5-123">Query the Centralized Logging Service to find out what scenarios are currently running by typing the following:</span></span>
    
        Show-CsClsLogging
    
    <span data-ttu-id="15da5-124">![在呼叫 Show CsCl 後的 Windows PowerShell 主控台](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "在呼叫 Show CsCl 後的 Windows PowerShell 主控台")</span><span class="sxs-lookup"><span data-stu-id="15da5-124">![Windows PowerShell console after calling Show-CsCl](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "Windows PowerShell console after calling Show-CsCl")</span></span>
    
    <span data-ttu-id="15da5-125">Show-CsClsLogging 的結果是執行中案例及其執行範圍的摘要。</span><span class="sxs-lookup"><span data-stu-id="15da5-125">The result of Show-CsClsLogging is a summary of the scenarios that are running and what scope they are running in.</span></span> <span data-ttu-id="15da5-126">如需詳細資訊，請參閱＜[Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)＞。</span><span class="sxs-lookup"><span data-stu-id="15da5-126">For details, see [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging).</span></span>

3.  <span data-ttu-id="15da5-127">若要停止使用特定案例的目前執行中記錄工作階段，請輸入：</span><span class="sxs-lookup"><span data-stu-id="15da5-127">To stop a currently running logging session with a specific scenario, type:</span></span>
    
        Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
    
    <span data-ttu-id="15da5-128">例如：</span><span class="sxs-lookup"><span data-stu-id="15da5-128">For example:</span></span>
    
        Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
    
    <span data-ttu-id="15da5-129">此命令將會停止 pool01.contoso.net 上使用 UserReplicatior 案例的記錄。</span><span class="sxs-lookup"><span data-stu-id="15da5-129">This command will stop logging with the UserReplicatior scenario on pool01.contoso.net.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="15da5-130">在此記錄工作階段期間，使用 UserReplicator 案例來建立的記錄並不會刪除。</span><span class="sxs-lookup"><span data-stu-id="15da5-130">Logs created during this logging session using the UserReplicator scenario are not deleted.</span></span> <span data-ttu-id="15da5-131">您還是可以使用該記錄來執行使用 Search-CsClsLogging 命令的搜尋作業。</span><span class="sxs-lookup"><span data-stu-id="15da5-131">The logging is still available for you to execute searches against using the Search-CsClsLogging command.</span></span> <span data-ttu-id="15da5-132">如需詳細資訊，請參閱＜<A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</A>＞。</span><span class="sxs-lookup"><span data-stu-id="15da5-132">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</A>.</span></span>

    
    </div>

<span data-ttu-id="15da5-p107">Stop-CsClsLogging Cmdlet 與 Start-CsClsLogging 搭配使用時，會結束記錄工作階段 (由案例定義)，並保留記錄工作階段所建立的記錄。您隨時都可以在給定的電腦上執行兩個案例。用一個案例停止另一個案例來收集資訊的方法，是在大部分工作量疑難排解期間都可以執行的常用工作。</span><span class="sxs-lookup"><span data-stu-id="15da5-p107">Acting as the companion command to Start-CsClsLogging, the Stop-CsClsLogging cmdlet ends the logging session, defined by scenarios, and retains the logs created by the logging session. You can run two scenarios on a given computer at any time. The method of stopping one scenario to gather information using another scenario is a common task that you can perform during most workload troubleshooting.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="15da5-136">另請參閱</span><span class="sxs-lookup"><span data-stu-id="15da5-136">See Also</span></span>


[<span data-ttu-id="15da5-137">將 Start 用於集中式記錄服務以擷取在 Lync Server 2013 中的記錄</span><span class="sxs-lookup"><span data-stu-id="15da5-137">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)  


[<span data-ttu-id="15da5-138">Lync Server 2013 中的集中式的記錄服務概觀</span><span class="sxs-lookup"><span data-stu-id="15da5-138">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[<span data-ttu-id="15da5-139">Show-csclslogging</span><span class="sxs-lookup"><span data-stu-id="15da5-139">Show-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)  
[<span data-ttu-id="15da5-140">Start-csclslogging</span><span class="sxs-lookup"><span data-stu-id="15da5-140">Start-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Start-CsClsLogging)  
[<span data-ttu-id="15da5-141">Stop-csclslogging</span><span class="sxs-lookup"><span data-stu-id="15da5-141">Stop-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

