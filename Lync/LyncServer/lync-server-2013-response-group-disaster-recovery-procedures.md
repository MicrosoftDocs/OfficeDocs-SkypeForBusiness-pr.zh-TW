---
title: Lync Server 2013 回應群組災害復原程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response group disaster recovery procedures
ms:assetid: b49577b7-0ca3-4f20-b614-f3a2a0046b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205186(v=OCS.15)
ms:contentKeyID: 48185171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7f28f13d1acdbdae58b1aadd6f73871af270b7d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975489"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-disaster-recovery-procedures-in-lync-server-2013"></a><span data-ttu-id="718fc-102">Lync Server 2013 中的回應群組災害復原程序</span><span class="sxs-lookup"><span data-stu-id="718fc-102">Response group disaster recovery procedures in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="718fc-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="718fc-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="718fc-104">在災害復原的容錯移轉階段，回應群組位於多個池中： [主要] 池中（即無法使用）及 [備份] 池中。</span><span class="sxs-lookup"><span data-stu-id="718fc-104">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool.</span></span> <span data-ttu-id="718fc-105">兩個彙集中的回應群組都有相同的名稱和相同的擁有者（主要池），但它們擁有不同的父項。</span><span class="sxs-lookup"><span data-stu-id="718fc-105">The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span> <span data-ttu-id="718fc-106">在這段時間內，回應群組 Cmdlet 的運作方式稍有不同。</span><span class="sxs-lookup"><span data-stu-id="718fc-106">During this time, Response Group cmdlets work a little differently.</span></span> <span data-ttu-id="718fc-107">請務必使用下列程式中所指定的參數。</span><span class="sxs-lookup"><span data-stu-id="718fc-107">Be sure to use parameters as specified in the following procedure.</span></span> <span data-ttu-id="718fc-108">如需有關 Cmdlet 在容錯移轉階段運作方式的詳細資訊，請參閱 NextHop 博客文章「Lync Server 2013：在災害復原期間[http://go.microsoft.com/fwlink/p/?LinkId=263957](http://go.microsoft.com/fwlink/p/?linkid=263957)復原回應群組」。</span><span class="sxs-lookup"><span data-stu-id="718fc-108">For details about how cmdlets work during the failover phase, see NextHop blog article "Lync Server 2013: Recovering Response Groups During Disaster Recovery" at [http://go.microsoft.com/fwlink/p/?LinkId=263957](http://go.microsoft.com/fwlink/p/?linkid=263957).</span></span> <span data-ttu-id="718fc-109">此博客文章也適用于 Lync Server 2013 的發行版本。</span><span class="sxs-lookup"><span data-stu-id="718fc-109">This blog article also applies to the released version of Lync Server 2013.</span></span>

<span data-ttu-id="718fc-110">使用下列程式中的步驟來準備並執行 Lync Server 回應群組服務的災害復原。</span><span class="sxs-lookup"><span data-stu-id="718fc-110">Use the steps in the following procedure to prepare for and perform disaster recovery for Lync Server Response Group service.</span></span>

<div>

## <a name="to-fail-over-and-fail-back-response-group"></a><span data-ttu-id="718fc-111">容錯移轉及容錯回復回應群組</span><span class="sxs-lookup"><span data-stu-id="718fc-111">To fail over and fail back Response Group</span></span>

1.  <span data-ttu-id="718fc-112">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="718fc-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="718fc-113">定期執行備份。</span><span class="sxs-lookup"><span data-stu-id="718fc-113">Routinely perform backups.</span></span> <span data-ttu-id="718fc-114">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="718fc-114">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="718fc-115">例如：</span><span class="sxs-lookup"><span data-stu-id="718fc-115">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  <span data-ttu-id="718fc-116">在中斷期間，在容錯移轉至備份池之後，將回應群組匯入到備份區。</span><span class="sxs-lookup"><span data-stu-id="718fc-116">During an outage, after failover to the backup pool, import the response groups to the backup pool.</span></span> <span data-ttu-id="718fc-117">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="718fc-117">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="718fc-118">如果您想要將備份池中的應用層級設定取代為主要池中的設定，請包含– ReplaceExistingSettings 參數。</span><span class="sxs-lookup"><span data-stu-id="718fc-118">If you want to replace the application-level settings in the backup pool with the settings from the primary pool, include the –ReplaceExistingSettings parameter.</span></span> <span data-ttu-id="718fc-119">例如：</span><span class="sxs-lookup"><span data-stu-id="718fc-119">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="718fc-120">如果您不取代備份池中的設定，且無法復原主要池，主要池設定將會遺失。</span><span class="sxs-lookup"><span data-stu-id="718fc-120">If you do not replace the settings in the backup pool and the primary pool can't be recovered, the primary pool settings will be lost.</span></span> <span data-ttu-id="718fc-121">如需詳細資訊，請參閱<A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">在 Lync Server 2013 中規劃回應群組災害復原</A>。</span><span class="sxs-lookup"><span data-stu-id="718fc-121">For details, see <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">Planning for response group disaster recovery in Lync Server 2013</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="718fc-122">顯示已匯入的回應群組，以確認已成功匯入。</span><span class="sxs-lookup"><span data-stu-id="718fc-122">Verify that the import was successful by displaying the imported response groups.</span></span> <span data-ttu-id="718fc-123">匯入的回應群組仍為主要池所擁有。</span><span class="sxs-lookup"><span data-stu-id="718fc-123">The imported response groups are still owned by the primary pool.</span></span> <span data-ttu-id="718fc-124">請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="718fc-124">Do the following:</span></span>
    
      - <span data-ttu-id="718fc-125">顯示主要池擁有之備份池中的所有工作流程，並確認所有主要池工作流程都包含在其中。</span><span class="sxs-lookup"><span data-stu-id="718fc-125">Display all the workflows in the backup pool that are owned by the primary pool, and verify that all the primary pool workflows are included.</span></span> <span data-ttu-id="718fc-126">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="718fc-126">At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="718fc-127">例如：</span><span class="sxs-lookup"><span data-stu-id="718fc-127">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - <span data-ttu-id="718fc-128">顯示主要池擁有之備份池中的所有佇列，並確認所有的主要池佇列都已包含。</span><span class="sxs-lookup"><span data-stu-id="718fc-128">Display all the queues in the backup pool that are owned by the primary pool, and verify that all the primary pool queues are included.</span></span> <span data-ttu-id="718fc-129">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="718fc-129">At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="718fc-130">例如：</span><span class="sxs-lookup"><span data-stu-id="718fc-130">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="718fc-131">顯示主要池擁有之備份池中的所有代理群組，並確認所有的主要池代理程式群組都包含在其中。</span><span class="sxs-lookup"><span data-stu-id="718fc-131">Display all the agent groups in the backup pool that are owned by the primary pool, and verify that all the primary pool agent groups are included.</span></span> <span data-ttu-id="718fc-132">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="718fc-132">At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="718fc-133">例如：</span><span class="sxs-lookup"><span data-stu-id="718fc-133">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="718fc-134">在主要池擁有的備份池中顯示所有的商務用時數，並確認已包含所有的主要池時間。</span><span class="sxs-lookup"><span data-stu-id="718fc-134">Display all the hours of business in the backup pool that are owned by the primary pool, and verify that all the primary pool hours of business are included.</span></span> <span data-ttu-id="718fc-135">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="718fc-135">At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="718fc-136">例如：</span><span class="sxs-lookup"><span data-stu-id="718fc-136">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="718fc-137">在主要池擁有的備份池中顯示所有假日集，並確認所有主要池假日集都包含在內。</span><span class="sxs-lookup"><span data-stu-id="718fc-137">Display all the holiday sets in the backup pool that are owned by the primary pool, and verify that all the primary pool holiday sets are included.</span></span> <span data-ttu-id="718fc-138">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="718fc-138">At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="718fc-139">例如：</span><span class="sxs-lookup"><span data-stu-id="718fc-139">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    <span data-ttu-id="718fc-140">或者，您也可以在備份池中顯示所有的回應群組，包括主要池所擁有的全部回應群組，以及由備份池所擁有的所有回應群組，而不是使用– Owner （擁有者）參數。</span><span class="sxs-lookup"><span data-stu-id="718fc-140">Alternatively, you can display all the response groups in the backup pool, including the ones owned by the primary pool and the ones owned by the backup pool by using the –ShowAll parameter instead of the –Owner parameter.</span></span> <span data-ttu-id="718fc-141">例如：</span><span class="sxs-lookup"><span data-stu-id="718fc-141">For example:</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="718fc-142">您必須使用– ShowAll 參數或– Owner 參數。</span><span class="sxs-lookup"><span data-stu-id="718fc-142">You must use either the –ShowAll parameter or the –Owner parameter.</span></span> <span data-ttu-id="718fc-143">如果您不使用這兩個參數中的任何一個，您匯入到備份池中的回應群組將不會列在 Cmdlet 所傳回的結果中。</span><span class="sxs-lookup"><span data-stu-id="718fc-143">If you do not use either of these parameters, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>

    
    </div>

5.  <span data-ttu-id="718fc-144">將呼叫撥入到已匯入的回應群組，並確認正確處理通話，以確認匯入成功。</span><span class="sxs-lookup"><span data-stu-id="718fc-144">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="718fc-145">要求是正式代理群組成員的代理，在備份池中登入其代理群組。</span><span class="sxs-lookup"><span data-stu-id="718fc-145">Request agents who are members of formal agent groups to sign in to their agent groups in the backup pool.</span></span>

7.  <span data-ttu-id="718fc-146">照常管理及修改匯入的回應群組。</span><span class="sxs-lookup"><span data-stu-id="718fc-146">Manage and modify the imported response groups as usual.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="718fc-147">當回應群組位於 [備份] 池中時，您必須使用 Lync Server Management Shell 來管理它們。</span><span class="sxs-lookup"><span data-stu-id="718fc-147">While the response groups are in the backup pool, you need to use Lync Server Management Shell to manage them.</span></span> <span data-ttu-id="718fc-148">您無法使用 Lync Server [控制台] 來管理您匯入到備份池中的回應群組。</span><span class="sxs-lookup"><span data-stu-id="718fc-148">You cannot use Lync Server Control Panel to manage the response groups that you imported to the backup pool.</span></span>

    
    </div>

8.  <span data-ttu-id="718fc-149">在主要池已還原且已完成回切之後，請匯出已匯入到備份池中的主要池回應群組。</span><span class="sxs-lookup"><span data-stu-id="718fc-149">After the primary pool is restored and failback is complete, export the primary pool response groups that were imported to the backup pool.</span></span> <span data-ttu-id="718fc-150">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="718fc-150">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  <span data-ttu-id="718fc-151">將回應群組匯入到主要池。</span><span class="sxs-lookup"><span data-stu-id="718fc-151">Import the response groups back to the primary pool.</span></span> <span data-ttu-id="718fc-152">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="718fc-152">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    <span data-ttu-id="718fc-153">例如：</span><span class="sxs-lookup"><span data-stu-id="718fc-153">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="718fc-154">如果您在恢復期間重建一個池（無論是使用相同或不同的完整功能變數名稱（FQDN）），則必須使用– OverwriteOwner 參數。</span><span class="sxs-lookup"><span data-stu-id="718fc-154">If you rebuild a pool during recovery, whether with the same or a different fully qualified domain name (FQDN), you need to use the –OverwriteOwner parameter.</span></span> <span data-ttu-id="718fc-155">就拇指而言，當您將回應群組匯入到主要池中時，您隨時可以使用– OverwriteOwner 參數。</span><span class="sxs-lookup"><span data-stu-id="718fc-155">As a rule of thumb, you can always use the –OverwriteOwner parameter when you import response groups back to the primary pool.</span></span>

    
    </div>
    
    <span data-ttu-id="718fc-156">如果您已部署新的池（具有相同或不同的 FQDN）來取代主要池，且您想要使用來自新池之備份池中的應用層級設定，請包含– ReplaceExistingSettings 參數。</span><span class="sxs-lookup"><span data-stu-id="718fc-156">If you deployed a new pool (with the same or a different FQDN) to replace the primary pool, and you want to use the application-level settings from the backup pool for the new pool, include the –ReplaceExistingSettings parameter.</span></span> <span data-ttu-id="718fc-157">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="718fc-157">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    <span data-ttu-id="718fc-158">例如：</span><span class="sxs-lookup"><span data-stu-id="718fc-158">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="718fc-159">如果您不想要使用備份池中的設定取代應用程式層級設定和預設的音樂保留音訊檔案，新的池會使用預設的應用層級設定。</span><span class="sxs-lookup"><span data-stu-id="718fc-159">If you don't want to replace the application-level settings and default music-on-hold audio file for the new pool with the settings from the backup pool, the new pool will use the default application-level settings.</span></span>

    
    </div>

10. <span data-ttu-id="718fc-160">顯示已匯入的回應群組設定，以確認匯入到主要池成功。</span><span class="sxs-lookup"><span data-stu-id="718fc-160">Verify that the import back to the primary pool was successful by displaying the imported response group configuration.</span></span> <span data-ttu-id="718fc-161">請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="718fc-161">Do the following:</span></span>
    
      - <span data-ttu-id="718fc-162">在主要池中顯示所有工作流程，並確認所有已匯入的工作流程都包含在其中。</span><span class="sxs-lookup"><span data-stu-id="718fc-162">Display all the workflows in the primary pool, and verify that all the imported workflows are included.</span></span> <span data-ttu-id="718fc-163">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="718fc-163">At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="718fc-164">例如：</span><span class="sxs-lookup"><span data-stu-id="718fc-164">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="718fc-165">顯示主要池中的所有佇列，並確認所有已匯入的佇列都包含在其中。</span><span class="sxs-lookup"><span data-stu-id="718fc-165">Display all the queues in the primary pool, and verify that all the imported queues are included.</span></span> <span data-ttu-id="718fc-166">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="718fc-166">At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="718fc-167">例如：</span><span class="sxs-lookup"><span data-stu-id="718fc-167">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="718fc-168">顯示主要池中的所有代理程式群組，並確認所有已匯入的代理程式群組都已包含。</span><span class="sxs-lookup"><span data-stu-id="718fc-168">Display all the agent groups in the primary pool, and verify that all the imported agent groups are included.</span></span> <span data-ttu-id="718fc-169">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="718fc-169">At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="718fc-170">例如：</span><span class="sxs-lookup"><span data-stu-id="718fc-170">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="718fc-171">在主要區中顯示所有的商務用時數，並確認已包含所有的匯入時間。</span><span class="sxs-lookup"><span data-stu-id="718fc-171">Display all the hours of business in the primary pool, and verify that all the imported hours of business are included.</span></span> <span data-ttu-id="718fc-172">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="718fc-172">At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="718fc-173">例如：</span><span class="sxs-lookup"><span data-stu-id="718fc-173">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="718fc-174">在主要區中顯示所有假日集，並確認所有匯入的假日集都包含在內。</span><span class="sxs-lookup"><span data-stu-id="718fc-174">Display all the holiday sets in the primary pool, and verify that all the imported holiday sets are included.</span></span> <span data-ttu-id="718fc-175">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="718fc-175">At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="718fc-176">例如：</span><span class="sxs-lookup"><span data-stu-id="718fc-176">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. <span data-ttu-id="718fc-177">將呼叫撥入到已匯入的回應群組，並確認正確處理通話，以確認匯入成功。</span><span class="sxs-lookup"><span data-stu-id="718fc-177">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

12. <span data-ttu-id="718fc-178">或者，您也可以從備份池中移除主要池所擁有的回應群組。</span><span class="sxs-lookup"><span data-stu-id="718fc-178">Optionally, remove the response groups owned by the primary pool from the backup pool.</span></span> <span data-ttu-id="718fc-179">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="718fc-179">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    <span data-ttu-id="718fc-180">例如：</span><span class="sxs-lookup"><span data-stu-id="718fc-180">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="718fc-181">這個步驟會以匯出的設定建立新的檔案，然後從備份池中移除該檔案。</span><span class="sxs-lookup"><span data-stu-id="718fc-181">This step creates a new file with the exported configuration, and then removes it from the backup pool.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

