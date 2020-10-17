---
title: Lync Server 2013：前端集區 ABC 容錯移轉程式
description: Lync Server 2013：前端集區 ABC 容錯移轉程式。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool ABC failover procedure
ms:assetid: 67763ad3-6796-45eb-a486-901f21ac1a95
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945635(v=OCS.15)
ms:contentKeyID: 51541486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b86f196d53afdc1dcad6fe41191c2aa1582f717e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567139"
---
# <a name="front-end-pool-abc-failover-procedure-in-lync-server-2013"></a><span data-ttu-id="a71d6-103">Lync Server 2013 中的前端集區 ABC 容錯移轉程式</span><span class="sxs-lookup"><span data-stu-id="a71d6-103">Front End pool ABC failover procedure in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a71d6-104">_**主題上次修改日期：** 2014-05-22_</span><span class="sxs-lookup"><span data-stu-id="a71d6-104">_**Topic Last Modified:** 2014-05-22_</span></span>

<span data-ttu-id="a71d6-105">使用下列步驟來執行 ABC 容錯移轉程式。</span><span class="sxs-lookup"><span data-stu-id="a71d6-105">Use the following steps to perform the ABC failover procedure.</span></span> <span data-ttu-id="a71d6-106">此套裝程式含每個步驟的高階描述，以及要針對每個步驟執行的命令和 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a71d6-106">This procedure contains a high-level description of each step, followed by commands and cmdlets to be run for each step.</span></span>

<span data-ttu-id="a71d6-107">若要執行 Cmdlet，請使用 [以系統管理員身分執行] 開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="a71d6-107">To run the cmdlets, open a Lync Server Management Shell using Run as Administrator.</span></span>

<div>

## <a name="to-perform-an-abc-failover"></a><span data-ttu-id="a71d6-108">若要執行 ABC 容錯移轉</span><span class="sxs-lookup"><span data-stu-id="a71d6-108">To Perform an ABC Failover</span></span>

1.  <span data-ttu-id="a71d6-109">檢查集區 A 是否為中央管理伺服器的主機 (CMS) 。</span><span class="sxs-lookup"><span data-stu-id="a71d6-109">Check whether the pool A is the host for the Central Management Server (CMS).</span></span>
    
      - <span data-ttu-id="a71d6-110">執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="a71d6-110">Run the following cmdlet:</span></span>
        
            Get-CsService -CentralManagement
        
        <span data-ttu-id="a71d6-111">如果作用中 CMS 的 [身分識別] 欄位指向「集區 A 的 FQDN) 的完整功能變數名稱 (，則您可以使用此程式的步驟2和步驟3，先對中央管理伺服器進行容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="a71d6-111">If the Identity field of the active CMS points to the fully qualified domain name (FQDN) of Pool A, then you use steps 2 and 3 of this procedure to fail over the Central Management Server first.</span></span> <span data-ttu-id="a71d6-112">否則，請跳至步驟4。</span><span class="sxs-lookup"><span data-stu-id="a71d6-112">Otherwise, skip to step 4.</span></span>

2.  <span data-ttu-id="a71d6-113">執行下列 Cmdlet，以在嚴重損壞復原模式中將 CMS 容錯移轉至集區 B：</span><span class="sxs-lookup"><span data-stu-id="a71d6-113">Fail over the CMS to Pool B in disaster recovery mode by running the following cmdlet:</span></span>
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    <span data-ttu-id="a71d6-114">執行這項作業之後，建議您將 CMS 從集區 B 移至另一個現有的配對集區，以取得額外的復原能力。</span><span class="sxs-lookup"><span data-stu-id="a71d6-114">After you do this, we recommend that you move the CMS from pool B to another existing paired pool for extra resiliency.</span></span> <span data-ttu-id="a71d6-115">如需詳細資訊，請參閱 [Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)。</span><span class="sxs-lookup"><span data-stu-id="a71d6-115">For details, see [Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)..</span></span>

3.  <span data-ttu-id="a71d6-116">如果集區 A 包含 CMS，請將 .LIS 設定從集區 A 匯入集區 B 的 .LIS 資料庫 (.Lis) 中。</span><span class="sxs-lookup"><span data-stu-id="a71d6-116">If Pool A contains CMS, import the LIS configuration from pool A into pool B’s LIS database (Lis.mdf).</span></span> <span data-ttu-id="a71d6-117">只有在您已定期備份 .LIS 資料時，才可使用此功能。</span><span class="sxs-lookup"><span data-stu-id="a71d6-117">This will work only if you have been backing up LIS data on a regular basis.</span></span> <span data-ttu-id="a71d6-118">若要匯入 .LIS 設定，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="a71d6-118">To import the LIS configuration, run the following cmdlets:</span></span>
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  <span data-ttu-id="a71d6-119">將已備份的 Lync Server 回應群組服務工作流程從集區 A 匯入集區 B。</span><span class="sxs-lookup"><span data-stu-id="a71d6-119">Import backed-up Lync Server Response Group service workflows from pool A into pool B.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a71d6-120">目前， <STRONG>Import-CsRgsConfiguration</STRONG> Cmdlet 要求集區 a 上的佇列和工作流程名稱與集區 B 上的佇列和工作流程名稱不同。如果名稱不具差異，當您執行 <STRONG>Import-CsRgsConfiguration</STRONG> Cmdlet 時，將會發生錯誤，而且在繼續進行 <STRONG>Import-CsRgsConfiguration</STRONG> Cmdlet 之前，必須先在集區 B 中重新命名佇列和工作流程。</span><span class="sxs-lookup"><span data-stu-id="a71d6-120">Currently, the <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet requires that the queue and workflow names on pool A are distinct from the queue and workflow names on pool B. If the names are not distinct, you will get an error when running the <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet, and the queues and workflows will need to be renamed in pool B before proceeding with <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet.</span></span>

    
    </div>
    
    <span data-ttu-id="a71d6-121">您有兩個選項可將「集區 A」的回應群組設定匯入至集區 B。使用哪個選項取決於您是否要覆寫集區 B 的應用層級設定與集區 A 中的應用層級設定。</span><span class="sxs-lookup"><span data-stu-id="a71d6-121">You have two options for importing the Response Group configuration from pool A to pool B. Which option you use depends on whether you want to overwrite the application-level settings of pool B with the application-level settings in pool A.</span></span>
    
      - <span data-ttu-id="a71d6-122">如果您想要覆寫集區 B 設定，請使用**ReplaceExistingSettings**選項來執行**Import-CsRgsConfiguration** Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="a71d6-122">If you want to overwrite the Pool B settings, run the **Import-CsRgsConfiguration** cmdlet with the **ReplaceExistingSettings** option:</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - <span data-ttu-id="a71d6-123">如果您不想要覆寫集區 B 設定，請使用不含**ReplaceExistingSettings**選項的**Import-CsRgsConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a71d6-123">If you do not want to overwrite the Pool B settings, use the **Import-CsRgsConfiguration** cmdlet without the **ReplaceExistingSettings** option.</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="a71d6-124">請注意，如果您不想要使用主要集區的設定覆寫備份組區的應用層級設定 (集區 B)  (集區 A) ，集區 A 的應用層級設定會在遺失集區 A 時遺失，因為回應群組應用程式只能在每個集區中儲存一組應用層級設定。</span><span class="sxs-lookup"><span data-stu-id="a71d6-124">Keep in mind that if you do not want to overwrite the application-level settings of the backup pool (pool B) with the settings of the primary pool (pool A), pool A’s application-level settings will be lost if pool A is lost, because the Response Group application can store only one set of application-level settings per pool.</span></span> <span data-ttu-id="a71d6-125">當部署集區 C 以取代集區 A 時，必須重新設定應用層級設定，包括預設的等候音樂音訊檔。</span><span class="sxs-lookup"><span data-stu-id="a71d6-125">When pool C is deployed to replace pool A, the application-level settings must be reconfigured, including the default music-on-hold audio file.</span></span>

    
    </div>

5.  <span data-ttu-id="a71d6-126">執行下列 Cmdlet 以顯示匯入的回應群組，確認回應群組設定匯入成功。</span><span class="sxs-lookup"><span data-stu-id="a71d6-126">Verify that the Response Group configuration import was successful by running the following cmdlets to display the imported response groups.</span></span> <span data-ttu-id="a71d6-127">請注意，匯入的回應群組仍然歸集區 A 所有。</span><span class="sxs-lookup"><span data-stu-id="a71d6-127">Note that the imported response groups are still owned by pool A.</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  <span data-ttu-id="a71d6-128">若未指派號碼，請將使用「宣告」的未指派號碼範圍，移至集區 A 至集區 B 的選取宣告服務。若要執行此動作：</span><span class="sxs-lookup"><span data-stu-id="a71d6-128">For Unassigned Numbers, move the Unassigned Number ranges that are using "Announcement" as the selected announcement service from pool A to pool B. To do so:</span></span>
    
      - <span data-ttu-id="a71d6-129">重新建立部署于集區 B 上集區 A 中的所有宣告。如果在集區 A 中部署宣告時使用任何音訊檔案，則需要這些檔案，以在集區 B 中重新建立宣告。若要在集區 B 中重新建立宣告，請使用 **New-CsAnnouncement** Cmdlet，搭配集區 b 做為上級服務。</span><span class="sxs-lookup"><span data-stu-id="a71d6-129">Re-create all announcements that were deployed in pool A on pool B. If any audio files were used when deploying the announcements in pool A, these files will be needed to re-create the announcements in pool B. To re-create the announcements in pool B, use the **New-CsAnnouncement** cmdlets, with pool B as the Parent service.</span></span>
    
      - <span data-ttu-id="a71d6-130">將所有以集區 A 宣告為宣告的未指派號碼範圍，都重新導向至集區 B 中新近部署的宣告。針對針對集區 A 宣告的每個未指派號碼範圍，執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="a71d6-130">Retarget all the Unassigned Number ranges that are targeting an announcement in pool A to the newly deployed announcements in pool B. Run the following cmdlet for every Unassigned Number range targeting an announcement of pool A:</span></span>
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a71d6-131">若未指派的號碼範圍使用「Exchange UM」做為選取的宣告服務，則不需要此步驟。</span><span class="sxs-lookup"><span data-stu-id="a71d6-131">This step is not required for unassigned number ranges that use "Exchange UM" as the selected announcement service.</span></span>

    
    </div>

7.  <span data-ttu-id="a71d6-132">執行下列 Cmdlet，將嚴重損壞修復 (DR) 模式中的集區 A 容錯移轉至集區 B：</span><span class="sxs-lookup"><span data-stu-id="a71d6-132">Fail over Pool A to Pool B in Disaster Recovery (DR) mode, by running the following cmdlet:</span></span>
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  <span data-ttu-id="a71d6-133">組建集區 C，但不啟動集區 C 上的任何服務。</span><span class="sxs-lookup"><span data-stu-id="a71d6-133">Build pool C, but do not start any services on pool C.</span></span>
    
    <span data-ttu-id="a71d6-134">請注意，您可以使用步驟5和6同時執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="a71d6-134">Note that this step can be carried out concurrently with steps 5 and 6.</span></span>

9.  <span data-ttu-id="a71d6-135">執行下列 Cmdlet，強制將駐留在集區 A 上的使用者移至集區 C：</span><span class="sxs-lookup"><span data-stu-id="a71d6-135">Force users homed on pool A to move to pool C by running the following cmdlet:</span></span>
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    <span data-ttu-id="a71d6-136">此時，位於集區 A 的使用者將開始經歷服務中斷。</span><span class="sxs-lookup"><span data-stu-id="a71d6-136">At this point, users homed on pool A will begin to experience a service outage.</span></span> <span data-ttu-id="a71d6-137">這種中斷會繼續進行，直到第16步，在集區 C 上啟動了點服務。</span><span class="sxs-lookup"><span data-stu-id="a71d6-137">This outage will continue until step 16, at which point services are started on pool C.</span></span>

10. <span data-ttu-id="a71d6-138">執行下列 Cmdlet，強制集區 A 的會議目錄移至集區 C：</span><span class="sxs-lookup"><span data-stu-id="a71d6-138">Force the conference directory of pool A to move to pool C by running the following cmdlet:</span></span>
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. <span data-ttu-id="a71d6-139">執行下列 Cmdlet，強制會議自動語音應答 (CAA) Contact 物件從集區 A 移至集區 C：</span><span class="sxs-lookup"><span data-stu-id="a71d6-139">Force the Conference Auto Attendant (CAA) Contact Object to move from pool A to pool C by running the following cmdlet:</span></span>
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. <span data-ttu-id="a71d6-140">將會議內容從集區 B 複製到集區 C。</span><span class="sxs-lookup"><span data-stu-id="a71d6-140">Copy conference content from pool B to pool C.</span></span>

13. <span data-ttu-id="a71d6-141">從集區 B 匯出使用者資料，並執行下列 Cmdlet，將使用者資料匯入集區 C：</span><span class="sxs-lookup"><span data-stu-id="a71d6-141">Export user data from pool B and import the user data into pool C by running the following cmdlets:</span></span>
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. <span data-ttu-id="a71d6-142">將從集區 A 備份的通話駐留應用程式資料還原到集區 C，並將集區 A 的通話駐留軌道範圍指派給集區 C。</span><span class="sxs-lookup"><span data-stu-id="a71d6-142">Restore backed-up Call Park application data from pool A into pool C and assign the Call Park orbit ranges of pool A to pool C.</span></span>
    
      - <span data-ttu-id="a71d6-143">您可以透過 Lync Server 控制台或 Lync Server 管理命令介面，將集區 A 的通話駐留軌道範圍重新指派至集區 C。</span><span class="sxs-lookup"><span data-stu-id="a71d6-143">You can reassign a Call Park orbit range of pool A to pool C either through the Lync Server Control Panel or the Lync Server Management Shell.</span></span> <span data-ttu-id="a71d6-144">針對 Lync Server 管理命令介面，針對指派給集區 A (的每個通話駐留軌道範圍執行下列 Cmdlet。請注意，Identity 參數是指屬於集區 A) 的通話駐留軌道範圍：</span><span class="sxs-lookup"><span data-stu-id="a71d6-144">For the Lync Server Management Shell, run the following cmdlet for every Call Park orbit range assigned to pool A (note that the Identity parameter refers to the Call Park Orbit Ranges that belong to pool A):</span></span>
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - <span data-ttu-id="a71d6-145">如果已針對集區 A 中的通話駐留設定自訂的已等候音樂，請在集區 C 中還原通話駐留自訂的封存暫停檔案。</span><span class="sxs-lookup"><span data-stu-id="a71d6-145">If a customized music-on-hold has been configured for Call Park in pool A, restore the Call Park customized music-on-hold file in pool C.</span></span>
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        <span data-ttu-id="a71d6-146">例如：</span><span class="sxs-lookup"><span data-stu-id="a71d6-146">For example:</span></span>
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - <span data-ttu-id="a71d6-147">最後，使用 **Set-CsCpsConfiguration** Cmdlet 重新設定集區 C 上的通話駐留設定。</span><span class="sxs-lookup"><span data-stu-id="a71d6-147">Finally, reconfigure the Call Park settings on pool C by using the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="a71d6-148">通話駐留應用程式只能為每個集區儲存一組設定及一個自訂的音樂暫止音訊檔，而且在發生嚴重損壞時，不會備份或保留這些設定。</span><span class="sxs-lookup"><span data-stu-id="a71d6-148">The Call Park application can store only one set of settings and one customized music-on-hold audio file per pool, and these settings are not backed up or preserved in the event of a disaster.</span></span>

15. <span data-ttu-id="a71d6-149">如果持續性聊天的下一個躍點集區指向集區 A，請建立併發行拓撲變更，使下一個躍點伺服器指向集區 C。</span><span class="sxs-lookup"><span data-stu-id="a71d6-149">If the next hop pool for Persistent Chat is pointing to pool A, make and publish topology changes so that the next hop server points to pool C.</span></span>
    
      - <span data-ttu-id="a71d6-150">在 [拓撲產生器] 中，將 Persistent Chat 集區變更為指向 [集區 C] 做為下一個躍點。</span><span class="sxs-lookup"><span data-stu-id="a71d6-150">In Topology Builder, change the Persistent Chat pool to point to Pool C as its next hop.</span></span> <span data-ttu-id="a71d6-151">若要這麼做，請在 Persistent Chat 集區上按一下滑鼠右鍵，然後按一下 [ **一般** ] 索引標籤，然後在 **[下一個躍點集區]** 中輸入集區 C 的名稱。</span><span class="sxs-lookup"><span data-stu-id="a71d6-151">To do so, right-click on the Persistent Chat pool, then click the **General** tab, and then type the name of Pool C in **Next Hop Pool**.</span></span>
    
      - <span data-ttu-id="a71d6-152">執行下列 Cmdlet，以在集區 C 上啟動服務：</span><span class="sxs-lookup"><span data-stu-id="a71d6-152">Start services on pool C by running the following cmdlet:</span></span>
        
            Start-csWindowsService
    
    <span data-ttu-id="a71d6-153">此時，使用者最初位於集區 A 上的服務中斷會結束。</span><span class="sxs-lookup"><span data-stu-id="a71d6-153">At this point, the service outage ends for users originally homed on pool A.</span></span>

16. <span data-ttu-id="a71d6-154">執行下列 Cmdlet，從集區 A 所擁有的集區 B 匯出 Lync Server 回應群組服務工作流程，以匯入集區 C：</span><span class="sxs-lookup"><span data-stu-id="a71d6-154">Export Lync Server Response Group service workflows from pool B owned by pool A for import into pool C by running the following cmdlet:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. <span data-ttu-id="a71d6-155">將 Lync Server 回應群組服務工作流程匯入集區 B 的集區 C。</span><span class="sxs-lookup"><span data-stu-id="a71d6-155">Import Lync Server Response Group service workflows into pool C from pool B.</span></span>
    
    <span data-ttu-id="a71d6-156">您有兩個選項可將回應群組設定從集區 B 匯入集區 C。使用哪個選項取決於您是否要使用集區 B 中的應用層級設定來覆寫集區 C 的應用層級設定。</span><span class="sxs-lookup"><span data-stu-id="a71d6-156">You have two options are for importing the Response Group configuration from pool B to pool C. Which option you use depends on whether you want to overwrite the application-level settings of pool C with the application-level settings in pool B.</span></span>
    
      - <span data-ttu-id="a71d6-157">如果您想要覆寫集區 C 設定，請使用**ReplaceExistingSettings**選項執行**Import-CsRgsConfiguration** Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="a71d6-157">If you want to overwrite the Pool C settings, run the **Import-CsRgsConfiguration** cmdlet with the **ReplaceExistingSettings** option:</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - <span data-ttu-id="a71d6-158">如果您不想要覆寫集區 C 設定，請使用不含**ReplaceExistingSettings**選項的**Import-CsRgsConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a71d6-158">If you do not want to overwrite the Pool C settings, use the **Import-CsRgsConfiguration** cmdlet without the **ReplaceExistingSettings** option.</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="a71d6-159">請注意，如果您不想要使用備份組區的設定覆寫集區 C 的應用層級設定 (集區 B) ，集區 B 的應用層級設定會遺失，因為回應群組應用程式只能為每個集區儲存一組應用層級設定。</span><span class="sxs-lookup"><span data-stu-id="a71d6-159">Keep in mind that if you do not want to overwrite the application-level settings of Pool C with the settings of the backup pool (pool B), pool B’s application-level settings will be lost because the Response Group application can store only one set of application-level settings per pool.</span></span>

    
    </div>

18. <span data-ttu-id="a71d6-160">執行下列 Cmdlet 以顯示已匯入至集區 C 的回應群組，確認回應群組設定匯入成功。</span><span class="sxs-lookup"><span data-stu-id="a71d6-160">Verify that the Response Group configuration import was successful by running the following cmdlets to display the response groups that have been imported to Pool C.</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. <span data-ttu-id="a71d6-161">在集區 C 中驗證匯入的設定之後，移除集區 B 的主要集區所擁有的回應群組。這會將回應群組的停機時間降至最低。</span><span class="sxs-lookup"><span data-stu-id="a71d6-161">When the imported configuration has been verified in pool C, remove the response groups owned by the primary pool from pool B. This will minimize the downtime of the response groups.</span></span>
    
    <span data-ttu-id="a71d6-162">此步驟會使用匯出的設定來建立新檔案，然後從集區 B 中移除檔案。</span><span class="sxs-lookup"><span data-stu-id="a71d6-162">This step creates a new file with the exported configuration, and then removes the file from pool B.</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. <span data-ttu-id="a71d6-163">移至集區 C 從集區 A 移至集區 B 的未指派號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="a71d6-163">Move to pool C the Unassigned Number ranges that were moved from pool A to pool B.</span></span>
    
      - <span data-ttu-id="a71d6-164">在集區 C 中重新建立從集區 B 的集區 A 重新建立的所有宣告。如果在部署要移動的宣告時使用任何音訊檔案，您必須使用這些檔案，以在集區 C 中重新建立宣告。若要在集區 C 中重新建立宣告，請使用 **New-CsAnnouncement** Cmdlet 搭配集區 c 做為上級服務。</span><span class="sxs-lookup"><span data-stu-id="a71d6-164">Re-create in pool C all announcements that were re-created from pool A in pool B. If any audio files were used when deploying the announcements to be moved, you will need to use these files to re-create the announcements in pool C. To re-create the announcements in pool C, use the **New-CsAnnouncement** cmdlets, with pool C as the Parent service.</span></span>
    
      - <span data-ttu-id="a71d6-165">重新定向至集區 C 從集區 A 重新置放至集區 B 的所有未指派號碼範圍。請針對需要重新置放的每個未指派號碼範圍，執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="a71d6-165">Retarget to pool C all the unassigned number ranges that were retargeted from pool A to pool B. Run the following cmdlet for every Unassigned Number range that needs to be retargeted:</span></span>
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      - <span data-ttu-id="a71d6-166"> (選用) 從集區 B 中移除如果已不再在集區 B 中使用，則會在集區 C 中重新建立的宣告。若要移除宣告，請使用 **remove-CsAnnouncement** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a71d6-166">(Optional) Remove from pool B the announcements that were re-created in pool C if they are no longer in use in pool B. To remove announcements, use the **Remove-CsAnnouncement** cmdlet.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a71d6-167">對於使用「Exchange UM」做為宣告服務的未指派號碼範圍，不需要此步驟。</span><span class="sxs-lookup"><span data-stu-id="a71d6-167">This step is not required for unassigned number ranges that use "Exchange UM" as the announcement service.</span></span>

        
        </div>

21. <span data-ttu-id="a71d6-168">執行下列 Cmdlet，清除集區 B 中集區 B 的使用者資料：</span><span class="sxs-lookup"><span data-stu-id="a71d6-168">Clean up user data of pool A in pool B by running the following cmdlet:</span></span>
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. <span data-ttu-id="a71d6-169">請在拓撲產生器中執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="a71d6-169">Do the following in Topology Builder:</span></span>
    
      - <span data-ttu-id="a71d6-170">Unpair 集區 A 及集區 B。對集區 B 和集區 C。然後從拓撲移除集區 A，然後發佈它。</span><span class="sxs-lookup"><span data-stu-id="a71d6-170">Unpair pool A and pool B. Pair pool B and pool C. Then remove Pool A from the topology and publish it.</span></span> <span data-ttu-id="a71d6-171">若要這麼做︰</span><span class="sxs-lookup"><span data-stu-id="a71d6-171">To do so:</span></span>
        
          - <span data-ttu-id="a71d6-172">在 [拓撲產生器] 中，以滑鼠右鍵按一下 [集區 B]，然後按一下 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="a71d6-172">In Topology Builder, right-click on Pool B, and then click **Edit Properties**.</span></span>
        
          - <span data-ttu-id="a71d6-173">按一下左窗格中的 [ **復原** ]。</span><span class="sxs-lookup"><span data-stu-id="a71d6-173">Click **Resiliency** in the left pane.</span></span>
        
          - <span data-ttu-id="a71d6-174">在 [ **關聯備份組**區] 下方的方塊中，選取 [集區 C]。請注意，關聯的備份組區選擇方塊最初會顯示集區 A，因為集區 B 先前與此集區相關聯。</span><span class="sxs-lookup"><span data-stu-id="a71d6-174">In the box below **Associated Backup Pool**, select Pool C. Note that the Associated Backup Pool selection box will initially display pool A, because pool B was previously associated with this pool.</span></span>
        
          - <span data-ttu-id="a71d6-175">選取 [語音自動容錯移轉和容錯回復]\*\*\*\*，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a71d6-175">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
            
            <span data-ttu-id="a71d6-176">現在當您檢視此集區的詳細資料時，會在右窗格的 [恢復]\*\*\*\* 中顯示關聯的集區。</span><span class="sxs-lookup"><span data-stu-id="a71d6-176">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span>
        
          - <span data-ttu-id="a71d6-177">在主控台樹中，以滑鼠右鍵按一下 [集區 A]，然後按一下 [刪除]。</span><span class="sxs-lookup"><span data-stu-id="a71d6-177">In the console tree, right-click pool A, and then click Delete.</span></span>
        
          - <span data-ttu-id="a71d6-178">發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="a71d6-178">Publish the topology.</span></span>

23. <span data-ttu-id="a71d6-179">在集區 C 上執行啟動應用程式以安裝備份服務應用程式，然後從集區 C 中本機電腦上的部署資料夾中執行下列動作，以啟動備份服務應用程式：</span><span class="sxs-lookup"><span data-stu-id="a71d6-179">Run the bootstrapping application on pool C to install the backup service application, and then start the backup service application by running the following from the deployment folder on a local machine in pool C:</span></span>
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. <span data-ttu-id="a71d6-180">執行下列 Cmdlet，以重新開機集區 B 上的備份服務應用程式：</span><span class="sxs-lookup"><span data-stu-id="a71d6-180">Restart the backup service application on pool B by running the following cmdlets:</span></span>
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. <span data-ttu-id="a71d6-181">如果集區 C 是 Standard Edition (SE) 集區和集區 B 有 CMS，請執行下列 Cmdlet 手動在集區 C 上安裝 CMS 資料庫：</span><span class="sxs-lookup"><span data-stu-id="a71d6-181">If pool C is a Standard Edition (SE) Pool and pool B has CMS, install the CMS database manually on pool C by running the following cmdlet:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. <span data-ttu-id="a71d6-182">呼叫備份服務，從集區 B 同步處理舊的會議內容，並將該內容從集區 B 同步處理至 a 集區 c 之前所產生的集區 C，並同步處理從集區 C 開始，並將 B 和 C 成對在一起時產生的集區 B 的新會議內容。</span><span class="sxs-lookup"><span data-stu-id="a71d6-182">Invoke the backup service to sync old conferencing content from pool B to pool C that was generated before pairing B and C together, and to sync new conferencing content from pool C to pool B that was generated after starting pool C and before B and C were paired together.</span></span> <span data-ttu-id="a71d6-183">若要這麼做，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="a71d6-183">To do so, run the following cmdlets:</span></span>
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. <span data-ttu-id="a71d6-184">針對與集區 A 相關聯的每個 Survivable 分支裝置 X：</span><span class="sxs-lookup"><span data-stu-id="a71d6-184">For each Survivable Branch Appliance X associated with pool A:</span></span>
    
      - <span data-ttu-id="a71d6-185">執行下列 Cmdlet 以關閉 SBA X：</span><span class="sxs-lookup"><span data-stu-id="a71d6-185">Shut down SBA X by running the following cmdlet:</span></span>
        
            Stop-CsWindowsService
    
      - <span data-ttu-id="a71d6-186">建立包含位於 SBA X 上的使用者清單的檔案。當使用者移回步驟30中的 SBA X 時，就會需要該清單。</span><span class="sxs-lookup"><span data-stu-id="a71d6-186">Create a file that contains a list of users homed on SBA X. The list will be needed when the users are moved back to SBA X in step 30.</span></span> <span data-ttu-id="a71d6-187">若要這麼做，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="a71d6-187">To do so, run the following cmdlet:</span></span>
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - <span data-ttu-id="a71d6-188">執行下列 Cmdlet，強制將位於 SBA X 的使用者移至集區 C：</span><span class="sxs-lookup"><span data-stu-id="a71d6-188">Force users homed on SBA X to move to pool C by running the following cmdlet:</span></span>
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - <span data-ttu-id="a71d6-189">先執行下列 Cmdlet，更新這些使用者的資料：</span><span class="sxs-lookup"><span data-stu-id="a71d6-189">Update the data of these users by first running the following cmdlets:</span></span>
        
            Convert-csUserData -InputFile <Data file exported from PoolB> -OutputFile c:\Logs\ExportedUserData.xml -TargetVersionLync2010 
            $a=get-csuser -Filter {RegistrarPool -eq "FQDN of SBA X"} | select SipAddress
            foreach($x in $a) {$x.SipAddress.Substring(4) >> users.txt}
        
        <span data-ttu-id="a71d6-190">然後執行下列腳本：</span><span class="sxs-lookup"><span data-stu-id="a71d6-190">And then run this script:</span></span>
        
            $users=gc c:\logs\users.txt
            foreach ($user in $users)
            {
            Update-CsUserData -FileName c:\logs\exportedUserDAta.xml -UserFilter $user - 
            }
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a71d6-191">在將使用者移至集區 C 之前，會針對位於 Sba 且與集區 A 關聯的使用者執行服務中斷。</span><span class="sxs-lookup"><span data-stu-id="a71d6-191">A service outage will occur for users who are homed on SBAs that are associated with pool A until these users are moved to pool C.</span></span>

        
        </div>

28. <span data-ttu-id="a71d6-192">在 [拓撲產生器] 中，針對先前與集區 A 相關聯的每個 SBA X 執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="a71d6-192">In Topology Builder, for each SBA X previously associated with Pool A, do the following:</span></span>
    
      - <span data-ttu-id="a71d6-193">變更與集區 C 的關聯。若要這麼做，請按一下分支網站，展開 [Survivable 分支裝置] 或 [伺服器] 節點，然後按一下 [ **Survivable Branch 裝置**]。</span><span class="sxs-lookup"><span data-stu-id="a71d6-193">Change the association to Pool C. To do so, click the branch site, expand the Survivable Branch Appliances or Servers node, and click **Survivable Branch Appliance**.</span></span> <span data-ttu-id="a71d6-194">然後選取前端集區，此 Survivable Branch 裝置將會連線至集區 C 的 **使用者服務集** 區，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a71d6-194">Then select the **Front End pool, User Services Pool** that this Survivable Branch Appliance will connect to as Pool C, and then click **Next**.</span></span>
    
      - <span data-ttu-id="a71d6-195">發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="a71d6-195">Publish the topology.</span></span> <span data-ttu-id="a71d6-196">若要執行此動作，請在主控台樹中，以滑鼠右鍵按一下新的 **Survivable Branch 裝置**，按一下 [ **拓撲**]，然後按一下 [ **發佈**]。</span><span class="sxs-lookup"><span data-stu-id="a71d6-196">To do so, in the console tree, right-click the new **Survivable Branch Appliance**, click **Topology**, and then click **Publish**.</span></span>

29. <span data-ttu-id="a71d6-197">對於現在與集區 C 相關聯的每個 SBA X：</span><span class="sxs-lookup"><span data-stu-id="a71d6-197">For each SBA X now associated with pool C:</span></span>
    
      - <span data-ttu-id="a71d6-198">在 survivable branch 裝置上執行下列 Cmdlet，以啟動 SBA X：</span><span class="sxs-lookup"><span data-stu-id="a71d6-198">Start SBA X by running the following cmdlet on the survivable branch appliance:</span></span>
        
            Start-CsWindowsService
    
      - <span data-ttu-id="a71d6-199">執行下列 Cmdlet，將原來位於 SBA X 的使用者，從集區 C 移至 SBA X。</span><span class="sxs-lookup"><span data-stu-id="a71d6-199">Move users who were originally homed on SBA X from pool C to SBA X by running the following cmdlet.</span></span>
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

</div>

</div>

<span> </span>

</div>

</div>

</div>

