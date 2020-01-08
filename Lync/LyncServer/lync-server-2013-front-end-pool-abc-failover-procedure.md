---
title: Lync Server 2013：前端集區 ABC 容錯移轉程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Front End pool ABC failover procedure
ms:assetid: 67763ad3-6796-45eb-a486-901f21ac1a95
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945635(v=OCS.15)
ms:contentKeyID: 51541486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87b6cb610d153374f6f4c9ba8a3c2798c50b88ad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-pool-abc-failover-procedure-in-lync-server-2013"></a><span data-ttu-id="85397-102">Lync Server 2013 中的前端集區 ABC 容錯移轉程序</span><span class="sxs-lookup"><span data-stu-id="85397-102">Front End pool ABC failover procedure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85397-103">_**主題上次修改日期：** 2014-05-22_</span><span class="sxs-lookup"><span data-stu-id="85397-103">_**Topic Last Modified:** 2014-05-22_</span></span>

<span data-ttu-id="85397-104">使用下列步驟來執行 ABC 容錯移轉程式。</span><span class="sxs-lookup"><span data-stu-id="85397-104">Use the following steps to perform the ABC failover procedure.</span></span> <span data-ttu-id="85397-105">此套裝程式含每個步驟的高層次描述，後面接著要針對每個步驟執行的命令和 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="85397-105">This procedure contains a high-level description of each step, followed by commands and cmdlets to be run for each step.</span></span>

<span data-ttu-id="85397-106">若要執行 Cmdlet，請使用 [以系統管理員身分執行] 來開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="85397-106">To run the cmdlets, open a Lync Server Management Shell using Run as Administrator.</span></span>

<div>

## <a name="to-perform-an-abc-failover"></a><span data-ttu-id="85397-107">執行 ABC 容錯移轉</span><span class="sxs-lookup"><span data-stu-id="85397-107">To Perform an ABC Failover</span></span>

1.  <span data-ttu-id="85397-108">檢查 [池 A] 是否為 [中央管理伺服器（CMS）] 主機。</span><span class="sxs-lookup"><span data-stu-id="85397-108">Check whether the pool A is the host for the Central Management Server (CMS).</span></span>
    
      - <span data-ttu-id="85397-109">執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="85397-109">Run the following cmdlet:</span></span>
        
            Get-CsService -CentralManagement
        
        <span data-ttu-id="85397-110">如果作用中 CMS 的 [身分識別] 欄位指向 [池 A] 的完整功能變數名稱（FQDN），則您可以使用此程式中的步驟2和3，先將中央管理伺服器容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="85397-110">If the Identity field of the active CMS points to the fully qualified domain name (FQDN) of Pool A, then you use steps 2 and 3 of this procedure to fail over the Central Management Server first.</span></span> <span data-ttu-id="85397-111">否則，請跳至步驟4。</span><span class="sxs-lookup"><span data-stu-id="85397-111">Otherwise, skip to step 4.</span></span>

2.  <span data-ttu-id="85397-112">透過執行下列 Cmdlet，將 CMS 容錯移轉到 [災害復原] 模式中的 [池 B]：</span><span class="sxs-lookup"><span data-stu-id="85397-112">Fail over the CMS to Pool B in disaster recovery mode by running the following cmdlet:</span></span>
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    <span data-ttu-id="85397-113">在您這樣做之後，建議您將 CMS 從 pool B 移到另一個現有的配對池，以獲得額外的復原能力。</span><span class="sxs-lookup"><span data-stu-id="85397-113">After you do this, we recommend that you move the CMS from pool B to another existing paired pool for extra resiliency.</span></span> <span data-ttu-id="85397-114">如需詳細資訊，請參閱[移動流覽 CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer).。。</span><span class="sxs-lookup"><span data-stu-id="85397-114">For details, see [Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)..</span></span>

3.  <span data-ttu-id="85397-115">如果 [池 A] 包含 CMS，請將 [池 A] 中的 .LIS 設定匯入到 [池 B] 的 [.LIS] 資料庫（.Lis）中。</span><span class="sxs-lookup"><span data-stu-id="85397-115">If Pool A contains CMS, import the LIS configuration from pool A into pool B’s LIS database (Lis.mdf).</span></span> <span data-ttu-id="85397-116">只有當您定期備份不在 IIS 中的資料時，才能使用此功能。</span><span class="sxs-lookup"><span data-stu-id="85397-116">This will work only if you have been backing up LIS data on a regular basis.</span></span> <span data-ttu-id="85397-117">若要匯入 .LIS 配置，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="85397-117">To import the LIS configuration, run the following cmdlets:</span></span>
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  <span data-ttu-id="85397-118">將已備份的 Lync Server 回應群組服務工作流程從 [群組 A] 匯入到 [池 B] 中。</span><span class="sxs-lookup"><span data-stu-id="85397-118">Import backed-up Lync Server Response Group service workflows from pool A into pool B.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="85397-119"><STRONG>CsRgsConfiguration</STRONG> Cmdlet 目前會要求在 pool A 上的佇列和工作流程名稱與隊 B 上的佇列和工作流程名稱不同。如果名稱不是唯一的，當您執行<STRONG>Import CsRgsConfiguration</STRONG> Cmdlet 時會發生錯誤，且佇列和工作流程需要在 pool B 中重新命名，才能繼續執行匯<STRONG>入-CsRgsConfiguration</STRONG> Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="85397-119">Currently, the <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet requires that the queue and workflow names on pool A are distinct from the queue and workflow names on pool B. If the names are not distinct, you will get an error when running the <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet, and the queues and workflows will need to be renamed in pool B before proceeding with <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet.</span></span>

    
    </div>
    
    <span data-ttu-id="85397-120">您有兩個選項可將 [池 A] 的回應群組設定匯入到 pool B。您所使用的選項取決於您是否要覆寫池 B 的應用層級設定，以及 b A 中的應用層級設定。</span><span class="sxs-lookup"><span data-stu-id="85397-120">You have two options for importing the Response Group configuration from pool A to pool B. Which option you use depends on whether you want to overwrite the application-level settings of pool B with the application-level settings in pool A.</span></span>
    
      - <span data-ttu-id="85397-121">如果您想要覆寫 Pool B 設定，請使用**ReplaceExistingSettings**選項執行**Import CsRgsConfiguration** Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="85397-121">If you want to overwrite the Pool B settings, run the **Import-CsRgsConfiguration** cmdlet with the **ReplaceExistingSettings** option:</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - <span data-ttu-id="85397-122">如果您不想覆蓋 Pool B 設定，請使用不含**ReplaceExistingSettings**選項的**Import CsRgsConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="85397-122">If you do not want to overwrite the Pool B settings, use the **Import-CsRgsConfiguration** cmdlet without the **ReplaceExistingSettings** option.</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="85397-123">請記住，如果您不想覆寫備份池（池 B）的應用層級設定與主要池（池 A）的設定，當池 A 遺失時，池 A 的應用層級設定將會遺失，因為回應群組應用程式可以針對每個池只儲存一組應用層級設定。</span><span class="sxs-lookup"><span data-stu-id="85397-123">Keep in mind that if you do not want to overwrite the application-level settings of the backup pool (pool B) with the settings of the primary pool (pool A), pool A’s application-level settings will be lost if pool A is lost, because the Response Group application can store only one set of application-level settings per pool.</span></span> <span data-ttu-id="85397-124">部署 pool C 以取代 pool A 時，必須重新配置應用程式層級設定，包括預設的音樂保留音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="85397-124">When pool C is deployed to replace pool A, the application-level settings must be reconfigured, including the default music-on-hold audio file.</span></span>

    
    </div>

5.  <span data-ttu-id="85397-125">執行下列 Cmdlet 來顯示已匯入的回應群組，以驗證回應群組設定已成功匯入。</span><span class="sxs-lookup"><span data-stu-id="85397-125">Verify that the Response Group configuration import was successful by running the following cmdlets to display the imported response groups.</span></span> <span data-ttu-id="85397-126">請注意，已匯入的回應群組仍由 A pool A 所擁有。</span><span class="sxs-lookup"><span data-stu-id="85397-126">Note that the imported response groups are still owned by pool A.</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  <span data-ttu-id="85397-127">針對未指定的數位，請將使用「宣告」的未指派數位範圍，移至從池 A 到 pool B 的所選宣告服務。若要執行此動作：</span><span class="sxs-lookup"><span data-stu-id="85397-127">For Unassigned Numbers, move the Unassigned Number ranges that are using "Announcement" as the selected announcement service from pool A to pool B. To do so:</span></span>
    
      - <span data-ttu-id="85397-128">重新建立部署在 pool B 上的 [pool A] 中的所有宣告。如果您在 [池 A] 中部署公告時使用任何音訊檔案，則需要這些檔案才能在 pool B 中重新建立公告。若要在 pool B 中重新建立宣告，請使用**CsAnnouncement** Cmdlet，並將 pool b 作為父項服務。</span><span class="sxs-lookup"><span data-stu-id="85397-128">Re-create all announcements that were deployed in pool A on pool B. If any audio files were used when deploying the announcements in pool A, these files will be needed to re-create the announcements in pool B. To re-create the announcements in pool B, use the **New-CsAnnouncement** cmdlets, with pool B as the Parent service.</span></span>
    
      - <span data-ttu-id="85397-129">已將目標為宣告的所有未指派數位範圍定為在 pool B 中新部署的宣告。針對 a 池 A 的宣告，針對每個未指派的編號範圍執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="85397-129">Retarget all the Unassigned Number ranges that are targeting an announcement in pool A to the newly deployed announcements in pool B. Run the following cmdlet for every Unassigned Number range targeting an announcement of pool A:</span></span>
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="85397-130">對於使用「Exchange UM」做為選取的宣告服務的未指定編號範圍，不需要此步驟。</span><span class="sxs-lookup"><span data-stu-id="85397-130">This step is not required for unassigned number ranges that use "Exchange UM" as the selected announcement service.</span></span>

    
    </div>

7.  <span data-ttu-id="85397-131">您可以執行下列 Cmdlet，將 [災害復原] （DR）模式中的 [池 A] 容錯移轉到 [池 B]：</span><span class="sxs-lookup"><span data-stu-id="85397-131">Fail over Pool A to Pool B in Disaster Recovery (DR) mode, by running the following cmdlet:</span></span>
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  <span data-ttu-id="85397-132">組建池 C，但不在 pool C 上啟動任何服務。</span><span class="sxs-lookup"><span data-stu-id="85397-132">Build pool C, but do not start any services on pool C.</span></span>
    
    <span data-ttu-id="85397-133">請注意，您可以使用步驟5和6同時執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="85397-133">Note that this step can be carried out concurrently with steps 5 and 6.</span></span>

9.  <span data-ttu-id="85397-134">執行下列 Cmdlet，強制將駐留在 pool A 的使用者移至 pool C：</span><span class="sxs-lookup"><span data-stu-id="85397-134">Force users homed on pool A to move to pool C by running the following cmdlet:</span></span>
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    <span data-ttu-id="85397-135">此時，駐留在 [池 A] 的使用者就會開始遇到服務中斷的問題。</span><span class="sxs-lookup"><span data-stu-id="85397-135">At this point, users homed on pool A will begin to experience a service outage.</span></span> <span data-ttu-id="85397-136">這個中斷會持續至步驟16，在 pool C 上開始進行點服務。</span><span class="sxs-lookup"><span data-stu-id="85397-136">This outage will continue until step 16, at which point services are started on pool C.</span></span>

10. <span data-ttu-id="85397-137">執行下列 Cmdlet，強制將 [池 A] 的會議目錄移至 [pool C]：</span><span class="sxs-lookup"><span data-stu-id="85397-137">Force the conference directory of pool A to move to pool C by running the following cmdlet:</span></span>
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. <span data-ttu-id="85397-138">執行下列 Cmdlet，強迫會議自動語音應答（CAA）連絡人物件從 [池 A] 移至 [pool C]：</span><span class="sxs-lookup"><span data-stu-id="85397-138">Force the Conference Auto Attendant (CAA) Contact Object to move from pool A to pool C by running the following cmdlet:</span></span>
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. <span data-ttu-id="85397-139">從 pool B 將會議內容複寫到 pool C。</span><span class="sxs-lookup"><span data-stu-id="85397-139">Copy conference content from pool B to pool C.</span></span>

13. <span data-ttu-id="85397-140">從 pool B 匯出使用者資料，並執行下列 Cmdlet，將使用者資料匯入到 pool C：</span><span class="sxs-lookup"><span data-stu-id="85397-140">Export user data from pool B and import the user data into pool C by running the following cmdlets:</span></span>
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. <span data-ttu-id="85397-141">將已備份的通話駐留應用程式資料從 [池 A] 還原到 [pool C]，然後將 [池 A] 的 [通話駐留軌道] 範圍指派給 pool C。</span><span class="sxs-lookup"><span data-stu-id="85397-141">Restore backed-up Call Park application data from pool A into pool C and assign the Call Park orbit ranges of pool A to pool C.</span></span>
    
      - <span data-ttu-id="85397-142">您可以透過 Lync Server 的 [控制台] 或 [Lync Server 管理命令介面]，將 [池 A] 的 [通話駐留] 軌道投影範圍重新指派給 pool C。</span><span class="sxs-lookup"><span data-stu-id="85397-142">You can reassign a Call Park orbit range of pool A to pool C either through the Lync Server Control Panel or the Lync Server Management Shell.</span></span> <span data-ttu-id="85397-143">針對 Lync Server 管理命令介面，請針對指派給 pool A 的每個通話駐留軌道範圍執行下列 Cmdlet （請注意，身分識別參數會參照屬於 pool A 的通話駐留軌道的範圍）：</span><span class="sxs-lookup"><span data-stu-id="85397-143">For the Lync Server Management Shell, run the following cmdlet for every Call Park orbit range assigned to pool A (note that the Identity parameter refers to the Call Park Orbit Ranges that belong to pool A):</span></span>
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - <span data-ttu-id="85397-144">如果在 [A] （池 A）中針對通話駐留設定了自訂的 [保留的音樂保留]，請在 pool C 中還原通話駐留自訂的音樂封存檔案。</span><span class="sxs-lookup"><span data-stu-id="85397-144">If a customized music-on-hold has been configured for Call Park in pool A, restore the Call Park customized music-on-hold file in pool C.</span></span>
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        <span data-ttu-id="85397-145">例如：</span><span class="sxs-lookup"><span data-stu-id="85397-145">For example:</span></span>
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - <span data-ttu-id="85397-146">最後，使用**CsCpsConfiguration** Cmdlet，在 pool C 上重新配置通話駐留設定。</span><span class="sxs-lookup"><span data-stu-id="85397-146">Finally, reconfigure the Call Park settings on pool C by using the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="85397-147">通話駐留應用程式在每個池中只能儲存一組設定和一個自訂的音樂保留音訊檔案，而且這些設定不會在災難事件中備份或保留。</span><span class="sxs-lookup"><span data-stu-id="85397-147">The Call Park application can store only one set of settings and one customized music-on-hold audio file per pool, and these settings are not backed up or preserved in the event of a disaster.</span></span>

15. <span data-ttu-id="85397-148">如果持續聊天的下一個躍點池是指向 [池 A]，請發出併發布拓撲變更，讓下一個躍點伺服器指向 [池 C]。</span><span class="sxs-lookup"><span data-stu-id="85397-148">If the next hop pool for Persistent Chat is pointing to pool A, make and publish topology changes so that the next hop server points to pool C.</span></span>
    
      - <span data-ttu-id="85397-149">在 [拓撲建立器] 中，將 [永久聊天] 池變更為指向 [池 C] 作為下一個躍點。</span><span class="sxs-lookup"><span data-stu-id="85397-149">In Topology Builder, change the Persistent Chat pool to point to Pool C as its next hop.</span></span> <span data-ttu-id="85397-150">若要這樣做，請以滑鼠右鍵按一下 [永久聊天] 池，然後按一下 [**一般**] 索引標籤，然後在 **[下一個躍點] 池中**輸入 [pool C] 的名稱。</span><span class="sxs-lookup"><span data-stu-id="85397-150">To do so, right-click on the Persistent Chat pool, then click the **General** tab, and then type the name of Pool C in **Next Hop Pool**.</span></span>
    
      - <span data-ttu-id="85397-151">執行下列 Cmdlet，即可在 pool C 上啟動服務：</span><span class="sxs-lookup"><span data-stu-id="85397-151">Start services on pool C by running the following cmdlet:</span></span>
        
            Start-csWindowsService
    
    <span data-ttu-id="85397-152">此時，使用者最初駐留在池 A 的服務中斷會結束。</span><span class="sxs-lookup"><span data-stu-id="85397-152">At this point, the service outage ends for users originally homed on pool A.</span></span>

16. <span data-ttu-id="85397-153">若要匯入到 pool C，請執行下列 Cmdlet，匯出 Lync Server 回應群組服務工作流程（由 pool A 擁有）：</span><span class="sxs-lookup"><span data-stu-id="85397-153">Export Lync Server Response Group service workflows from pool B owned by pool A for import into pool C by running the following cmdlet:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. <span data-ttu-id="85397-154">從 pool B 將 Lync Server 回應群組服務工作流程匯入到 pool C。</span><span class="sxs-lookup"><span data-stu-id="85397-154">Import Lync Server Response Group service workflows into pool C from pool B.</span></span>
    
    <span data-ttu-id="85397-155">從 pool B 將回應群組設定匯入到 pool C 時，您有兩個選項。您所使用的選項，取決於您是否要覆寫 pool C 的應用層級設定與 pool B 中的應用層級設定。</span><span class="sxs-lookup"><span data-stu-id="85397-155">You have two options are for importing the Response Group configuration from pool B to pool C. Which option you use depends on whether you want to overwrite the application-level settings of pool C with the application-level settings in pool B.</span></span>
    
      - <span data-ttu-id="85397-156">如果您想要覆寫 [Pool C] （設定），請使用**ReplaceExistingSettings**選項執行匯**入 CsRgsConfiguration** Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="85397-156">If you want to overwrite the Pool C settings, run the **Import-CsRgsConfiguration** cmdlet with the **ReplaceExistingSettings** option:</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - <span data-ttu-id="85397-157">如果您不想覆蓋 Pool C 設定，請使用不含**ReplaceExistingSettings**選項的**Import CsRgsConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="85397-157">If you do not want to overwrite the Pool C settings, use the **Import-CsRgsConfiguration** cmdlet without the **ReplaceExistingSettings** option.</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="85397-158">請記住，如果您不想使用備份池（Pool B）的設定來覆寫 Pool C 的應用層級設定，池 B 的應用層級設定將會遺失，因為回應群組應用程式只能儲存一組應用程式層級每個池的設定。</span><span class="sxs-lookup"><span data-stu-id="85397-158">Keep in mind that if you do not want to overwrite the application-level settings of Pool C with the settings of the backup pool (pool B), pool B’s application-level settings will be lost because the Response Group application can store only one set of application-level settings per pool.</span></span>

    
    </div>

18. <span data-ttu-id="85397-159">執行下列 Cmdlet 以驗證已匯入到 Pool C 的回應群組，以確認回應群組設定已成功匯入。</span><span class="sxs-lookup"><span data-stu-id="85397-159">Verify that the Response Group configuration import was successful by running the following cmdlets to display the response groups that have been imported to Pool C.</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. <span data-ttu-id="85397-160">在 pool C 中驗證匯入的設定後，請從 pool B 移除主要池所擁有的回應群組。這將會將回應群組的停機時間降至最低。</span><span class="sxs-lookup"><span data-stu-id="85397-160">When the imported configuration has been verified in pool C, remove the response groups owned by the primary pool from pool B. This will minimize the downtime of the response groups.</span></span>
    
    <span data-ttu-id="85397-161">此步驟會使用匯出的設定來建立新檔案，然後從 B 文件庫移除檔案。</span><span class="sxs-lookup"><span data-stu-id="85397-161">This step creates a new file with the exported configuration, and then removes the file from pool B.</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. <span data-ttu-id="85397-162">移至 pool C 從 [池 A] 移至 [池 B] 的 [未指定的數位範圍]。</span><span class="sxs-lookup"><span data-stu-id="85397-162">Move to pool C the Unassigned Number ranges that were moved from pool A to pool B.</span></span>
    
      - <span data-ttu-id="85397-163">在 pool C 中重新建立已從 B 池 B 中的 [池 A] 重新建立的所有宣告。如果您在部署要移動的宣告時使用任何音訊檔案，您將需要使用這些檔案來重新建立在 pool C 中的宣告。若要在 pool C 中重新建立宣告，請使用**CsAnnouncement** Cmdlet （含 pool c）作為父項服務。</span><span class="sxs-lookup"><span data-stu-id="85397-163">Re-create in pool C all announcements that were re-created from pool A in pool B. If any audio files were used when deploying the announcements to be moved, you will need to use these files to re-create the announcements in pool C. To re-create the announcements in pool C, use the **New-CsAnnouncement** cmdlets, with pool C as the Parent service.</span></span>
    
      - <span data-ttu-id="85397-164">從 A 池 A 重新置放至池 B 的所有未指派數位範圍，都是從 b 開始。針對需要重新置放的每個未指定編號範圍執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="85397-164">Retarget to pool C all the unassigned number ranges that were retargeted from pool A to pool B. Run the following cmdlet for every Unassigned Number range that needs to be retargeted:</span></span>
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      - <span data-ttu-id="85397-165">可選從 pool B 中移除如果在 pool B 中不再使用，則是在 pool C 中重新建立的宣告。若要移除宣告，請使用**CsAnnouncement** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="85397-165">(Optional) Remove from pool B the announcements that were re-created in pool C if they are no longer in use in pool B. To remove announcements, use the **Remove-CsAnnouncement** cmdlet.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="85397-166">對於使用「Exchange UM」做為宣告服務的未指定編號範圍，不需要此步驟。</span><span class="sxs-lookup"><span data-stu-id="85397-166">This step is not required for unassigned number ranges that use "Exchange UM" as the announcement service.</span></span>

        
        </div>

21. <span data-ttu-id="85397-167">在 pool B 中，執行下列 Cmdlet，以清除 pool A 的使用者資料：</span><span class="sxs-lookup"><span data-stu-id="85397-167">Clean up user data of pool A in pool B by running the following cmdlet:</span></span>
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. <span data-ttu-id="85397-168">在拓撲建立器中執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="85397-168">Do the following in Topology Builder:</span></span>
    
      - <span data-ttu-id="85397-169">取消配對 pool A 和 pool B. 配對池 B 和 pool C。然後從拓撲中移除 [池 A]，然後發佈它。</span><span class="sxs-lookup"><span data-stu-id="85397-169">Unpair pool A and pool B. Pair pool B and pool C. Then remove Pool A from the topology and publish it.</span></span> <span data-ttu-id="85397-170">若要執行此動作：</span><span class="sxs-lookup"><span data-stu-id="85397-170">To do so:</span></span>
        
          - <span data-ttu-id="85397-171">在拓撲建立器中，以滑鼠右鍵按一下 [池 B]，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="85397-171">In Topology Builder, right-click on Pool B, and then click **Edit Properties**.</span></span>
        
          - <span data-ttu-id="85397-172">按一下左窗格中的 [**復原**]。</span><span class="sxs-lookup"><span data-stu-id="85397-172">Click **Resiliency** in the left pane.</span></span>
        
          - <span data-ttu-id="85397-173">在 [關聯的**備份] 池**下方的方塊中，選取 [池 C]。請注意，關聯的備份池選取方塊最初會顯示池 A，因為「池 B」先前已與此池建立關聯。</span><span class="sxs-lookup"><span data-stu-id="85397-173">In the box below **Associated Backup Pool**, select Pool C. Note that the Associated Backup Pool selection box will initially display pool A, because pool B was previously associated with this pool.</span></span>
        
          - <span data-ttu-id="85397-174">選取 [**自動容錯移轉及語音回切**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="85397-174">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
            
            <span data-ttu-id="85397-175">當您查看此池的詳細資料時，關聯的池現在會出現在右窗格中的 [**復原**] 底下。</span><span class="sxs-lookup"><span data-stu-id="85397-175">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span>
        
          - <span data-ttu-id="85397-176">在主控台樹中，以滑鼠右鍵按一下 [池 A]，然後按一下 [刪除]。</span><span class="sxs-lookup"><span data-stu-id="85397-176">In the console tree, right-click pool A, and then click Delete.</span></span>
        
          - <span data-ttu-id="85397-177">發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="85397-177">Publish the topology.</span></span>

23. <span data-ttu-id="85397-178">在 pool C 上執行引導應用程式，以安裝備份服務應用程式，然後從 pool C 中的本機電腦上的 [部署] 資料夾中執行下列命令，以啟動備份服務應用程式：</span><span class="sxs-lookup"><span data-stu-id="85397-178">Run the bootstrapping application on pool C to install the backup service application, and then start the backup service application by running the following from the deployment folder on a local machine in pool C:</span></span>
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. <span data-ttu-id="85397-179">執行下列 Cmdlet，在 pool B 上重新開機備份服務應用程式：</span><span class="sxs-lookup"><span data-stu-id="85397-179">Restart the backup service application on pool B by running the following cmdlets:</span></span>
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. <span data-ttu-id="85397-180">如果 pool C 是標準版（SE）池，且 pool B 有 CMS，請執行下列 Cmdlet，在 pool C 上手動安裝 CMS 資料庫：</span><span class="sxs-lookup"><span data-stu-id="85397-180">If pool C is a Standard Edition (SE) Pool and pool B has CMS, install the CMS database manually on pool C by running the following cmdlet:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. <span data-ttu-id="85397-181">喚醒呼叫 [備份服務]，將舊的會議內容從 pool B 同步處理到在配對 B 和 C 之前產生的 pool C，並將從 pool C 開始的新會議內容同步處理到在啟動池子 C 之後所產生的 pool B，並將 B 和 C 的組合在一起。</span><span class="sxs-lookup"><span data-stu-id="85397-181">Invoke the backup service to sync old conferencing content from pool B to pool C that was generated before pairing B and C together, and to sync new conferencing content from pool C to pool B that was generated after starting pool C and before B and C were paired together.</span></span> <span data-ttu-id="85397-182">若要這樣做，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="85397-182">To do so, run the following cmdlets:</span></span>
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. <span data-ttu-id="85397-183">針對每個與 [池 A] 相關聯的 Survivable 分支裝置 X：</span><span class="sxs-lookup"><span data-stu-id="85397-183">For each Survivable Branch Appliance X associated with pool A:</span></span>
    
      - <span data-ttu-id="85397-184">執行下列 Cmdlet 以關閉 SBA X：</span><span class="sxs-lookup"><span data-stu-id="85397-184">Shut down SBA X by running the following cmdlet:</span></span>
        
            Stop-CsWindowsService
    
      - <span data-ttu-id="85397-185">建立一個檔案，其中包含駐留在 SBA X 上的使用者清單。當使用者移回步驟30中的 SBA X 時，就會需要該清單。</span><span class="sxs-lookup"><span data-stu-id="85397-185">Create a file that contains a list of users homed on SBA X. The list will be needed when the users are moved back to SBA X in step 30.</span></span> <span data-ttu-id="85397-186">若要這樣做，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="85397-186">To do so, run the following cmdlet:</span></span>
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - <span data-ttu-id="85397-187">透過執行下列 Cmdlet，強迫駐留在 SBA X 的使用者移至 pool C：</span><span class="sxs-lookup"><span data-stu-id="85397-187">Force users homed on SBA X to move to pool C by running the following cmdlet:</span></span>
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - <span data-ttu-id="85397-188">首先執行下列 Cmdlet 來更新這些使用者的資料：</span><span class="sxs-lookup"><span data-stu-id="85397-188">Update the data of these users by first running the following cmdlets:</span></span>
        
            Convert-csUserData -InputFile <Data file exported from PoolB> -OutputFile c:\Logs\ExportedUserData.xml -TargetVersionLync2010 
            $a=get-csuser -Filter {RegistrarPool -eq "FQDN of SBA X"} | select SipAddress
            foreach($x in $a) {$x.SipAddress.Substring(4) >> users.txt}
        
        <span data-ttu-id="85397-189">然後執行此腳本：</span><span class="sxs-lookup"><span data-stu-id="85397-189">And then run this script:</span></span>
        
            $users=gc c:\logs\users.txt
            foreach ($user in $users)
            {
            Update-CsUserData -FileName c:\logs\exportedUserDAta.xml -UserFilter $user - 
            }
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="85397-190">系統會針對駐留在 SBAs 的使用者，與 [池 A] 關聯，直到這些使用者移至 [池 C] 為止，才會發生服務中斷。</span><span class="sxs-lookup"><span data-stu-id="85397-190">A service outage will occur for users who are homed on SBAs that are associated with pool A until these users are moved to pool C.</span></span>

        
        </div>

28. <span data-ttu-id="85397-191">在 [拓撲建立器] 中，針對先前與 [池 A] 關聯的每個 SBA X 執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="85397-191">In Topology Builder, for each SBA X previously associated with Pool A, do the following:</span></span>
    
      - <span data-ttu-id="85397-192">變更與 Pool C 的關聯。若要這樣做，請按一下分支網站，展開 [Survivable 分支裝置] 或 [伺服器] 節點，然後按一下 [ **Survivable 分支裝置**]。</span><span class="sxs-lookup"><span data-stu-id="85397-192">Change the association to Pool C. To do so, click the branch site, expand the Survivable Branch Appliances or Servers node, and click **Survivable Branch Appliance**.</span></span> <span data-ttu-id="85397-193">然後選取 [**前端] 池、** 這個 Survivable 分支裝置將會連線至 [池 C] 的 [使用者服務] 池，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="85397-193">Then select the **Front End pool, User Services Pool** that this Survivable Branch Appliance will connect to as Pool C, and then click **Next**.</span></span>
    
      - <span data-ttu-id="85397-194">發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="85397-194">Publish the topology.</span></span> <span data-ttu-id="85397-195">若要這樣做，請在主控台樹中，以滑鼠右鍵按一下新的**Survivable 分支裝置**，按一下 [**拓撲**]，然後按一下 [**發佈**]。</span><span class="sxs-lookup"><span data-stu-id="85397-195">To do so, in the console tree, right-click the new **Survivable Branch Appliance**, click **Topology**, and then click **Publish**.</span></span>

29. <span data-ttu-id="85397-196">針對現在與 pool C 關聯的每個 SBA X：</span><span class="sxs-lookup"><span data-stu-id="85397-196">For each SBA X now associated with pool C:</span></span>
    
      - <span data-ttu-id="85397-197">在 survivable 分支裝置上執行下列 Cmdlet，即可開始 SBA X：</span><span class="sxs-lookup"><span data-stu-id="85397-197">Start SBA X by running the following cmdlet on the survivable branch appliance:</span></span>
        
            Start-CsWindowsService
    
      - <span data-ttu-id="85397-198">透過執行下列 Cmdlet，將最初駐留在 SBA X 的使用者從 pool C 移至 SBA X。</span><span class="sxs-lookup"><span data-stu-id="85397-198">Move users who were originally homed on SBA X from pool C to SBA X by running the following cmdlet.</span></span>
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

</div>

</div>

<span> </span>

</div>

</div>

</div>

