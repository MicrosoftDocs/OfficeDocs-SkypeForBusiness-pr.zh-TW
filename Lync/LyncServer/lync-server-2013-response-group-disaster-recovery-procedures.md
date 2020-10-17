---
title: Lync Server 2013 回應群組災難修復程式
description: Lync Server 2013 回應群組嚴重損壞修復程式。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response group disaster recovery procedures
ms:assetid: b49577b7-0ca3-4f20-b614-f3a2a0046b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205186(v=OCS.15)
ms:contentKeyID: 48185171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9021fb75c8f937bfd298578a9241d6256d26d85
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563889"
---
# <a name="response-group-disaster-recovery-procedures-in-lync-server-2013"></a><span data-ttu-id="45905-103">Lync Server 2013 的回應群組嚴重損壞修復程式</span><span class="sxs-lookup"><span data-stu-id="45905-103">Response group disaster recovery procedures in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45905-104">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="45905-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="45905-105">在災害復原的容錯移轉階段期間，回應群組位在多個集區中：主要集區 (無法使用) 以及備份集區中。</span><span class="sxs-lookup"><span data-stu-id="45905-105">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool.</span></span> <span data-ttu-id="45905-106">兩個集區中的回應群組都有相同的名稱和相同的擁有者 (主要集區)，但其父系不同。</span><span class="sxs-lookup"><span data-stu-id="45905-106">The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span> <span data-ttu-id="45905-107">在這段時間內，回應群組 Cmdlet 的運作方式稍有不同。</span><span class="sxs-lookup"><span data-stu-id="45905-107">During this time, Response Group cmdlets work a little differently.</span></span> <span data-ttu-id="45905-108">請務必依照下列程式所指定的方法使用參數。</span><span class="sxs-lookup"><span data-stu-id="45905-108">Be sure to use parameters as specified in the following procedure.</span></span> <span data-ttu-id="45905-109">如需在容錯移轉階段內 Cmdlet 如何運作的詳細資訊，請參閱《 Lync Server 2013：在嚴重損壞復原期間復原回應群組」中的 NextHop 博客文章 [https://go.microsoft.com/fwlink/p/?LinkId=263957](https://go.microsoft.com/fwlink/p/?linkid=263957) 。</span><span class="sxs-lookup"><span data-stu-id="45905-109">For details about how cmdlets work during the failover phase, see NextHop blog article "Lync Server 2013: Recovering Response Groups During Disaster Recovery" at [https://go.microsoft.com/fwlink/p/?LinkId=263957](https://go.microsoft.com/fwlink/p/?linkid=263957).</span></span> <span data-ttu-id="45905-110">此博客文章也適用于已發行版本本的 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="45905-110">This blog article also applies to the released version of Lync Server 2013.</span></span>

<span data-ttu-id="45905-111">使用下列程式中的步驟來準備和執行 Lync Server 回應群組服務的嚴重損壞修復。</span><span class="sxs-lookup"><span data-stu-id="45905-111">Use the steps in the following procedure to prepare for and perform disaster recovery for Lync Server Response Group service.</span></span>

<div>

## <a name="to-fail-over-and-fail-back-response-group"></a><span data-ttu-id="45905-112">容錯移轉和容錯回復回應群組</span><span class="sxs-lookup"><span data-stu-id="45905-112">To fail over and fail back Response Group</span></span>

1.  <span data-ttu-id="45905-113">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="45905-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="45905-114">定期執行備份。</span><span class="sxs-lookup"><span data-stu-id="45905-114">Routinely perform backups.</span></span> <span data-ttu-id="45905-115">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="45905-115">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="45905-116">例如：</span><span class="sxs-lookup"><span data-stu-id="45905-116">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  <span data-ttu-id="45905-117">在中斷期間，在容錯移轉至備份組區之後，將回應群組匯入至備份組區。</span><span class="sxs-lookup"><span data-stu-id="45905-117">During an outage, after failover to the backup pool, import the response groups to the backup pool.</span></span> <span data-ttu-id="45905-118">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="45905-118">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="45905-119">如果您想要以主要集區中的設定取代備份組區中的應用層級設定，請加入–ReplaceExistingSettings 參數。</span><span class="sxs-lookup"><span data-stu-id="45905-119">If you want to replace the application-level settings in the backup pool with the settings from the primary pool, include the –ReplaceExistingSettings parameter.</span></span> <span data-ttu-id="45905-120">例如：</span><span class="sxs-lookup"><span data-stu-id="45905-120">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="45905-121">如果您未取代備份組區中的設定，且無法復原主要集區，主要集區設定將會遺失。</span><span class="sxs-lookup"><span data-stu-id="45905-121">If you do not replace the settings in the backup pool and the primary pool can't be recovered, the primary pool settings will be lost.</span></span> <span data-ttu-id="45905-122">如需詳細資訊，請參閱 <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">在 Lync Server 2013 中規劃回應群組</A>嚴重損壞修復。</span><span class="sxs-lookup"><span data-stu-id="45905-122">For details, see <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">Planning for response group disaster recovery in Lync Server 2013</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="45905-123">顯示匯入的回應群組，以確認匯入成功。</span><span class="sxs-lookup"><span data-stu-id="45905-123">Verify that the import was successful by displaying the imported response groups.</span></span> <span data-ttu-id="45905-124">匯入的回應群組仍然歸主要集區所有。</span><span class="sxs-lookup"><span data-stu-id="45905-124">The imported response groups are still owned by the primary pool.</span></span> <span data-ttu-id="45905-125">執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="45905-125">Do the following:</span></span>
    
      - <span data-ttu-id="45905-126">顯示主要集區所擁有之備份組區中的所有工作流程，並確認包括所有主要集區工作流程。</span><span class="sxs-lookup"><span data-stu-id="45905-126">Display all the workflows in the backup pool that are owned by the primary pool, and verify that all the primary pool workflows are included.</span></span> <span data-ttu-id="45905-127">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="45905-127">At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="45905-128">例如：</span><span class="sxs-lookup"><span data-stu-id="45905-128">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - <span data-ttu-id="45905-129">顯示主要集區所擁有之備份組區中的所有佇列，並確認所有主要集區佇列都已包含。</span><span class="sxs-lookup"><span data-stu-id="45905-129">Display all the queues in the backup pool that are owned by the primary pool, and verify that all the primary pool queues are included.</span></span> <span data-ttu-id="45905-130">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="45905-130">At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="45905-131">例如：</span><span class="sxs-lookup"><span data-stu-id="45905-131">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="45905-132">顯示主要集區所擁有之備份組區中的所有代理程式群組，並確認所有的主要集區代理程式群組都包含在內。</span><span class="sxs-lookup"><span data-stu-id="45905-132">Display all the agent groups in the backup pool that are owned by the primary pool, and verify that all the primary pool agent groups are included.</span></span> <span data-ttu-id="45905-133">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="45905-133">At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="45905-134">例如：</span><span class="sxs-lookup"><span data-stu-id="45905-134">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="45905-135">顯示主要集區所擁有之備份組區中的所有上班時間，並確認包括所有的主要集區工作。</span><span class="sxs-lookup"><span data-stu-id="45905-135">Display all the hours of business in the backup pool that are owned by the primary pool, and verify that all the primary pool hours of business are included.</span></span> <span data-ttu-id="45905-136">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="45905-136">At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="45905-137">例如：</span><span class="sxs-lookup"><span data-stu-id="45905-137">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="45905-138">顯示主要集區所擁有之備份組區中的所有假日集，並確認所有主要集區假日集皆已包含在內。</span><span class="sxs-lookup"><span data-stu-id="45905-138">Display all the holiday sets in the backup pool that are owned by the primary pool, and verify that all the primary pool holiday sets are included.</span></span> <span data-ttu-id="45905-139">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="45905-139">At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="45905-140">例如：</span><span class="sxs-lookup"><span data-stu-id="45905-140">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    <span data-ttu-id="45905-141">或者，您可以顯示備份組區中所有的回應群組，包括主要集區所擁有的所有回應群組，以及備份組區所擁有的任何回應群組，而不是–ShowAll 使用– Owner 參數。</span><span class="sxs-lookup"><span data-stu-id="45905-141">Alternatively, you can display all the response groups in the backup pool, including the ones owned by the primary pool and the ones owned by the backup pool by using the –ShowAll parameter instead of the –Owner parameter.</span></span> <span data-ttu-id="45905-142">例如：</span><span class="sxs-lookup"><span data-stu-id="45905-142">For example:</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="45905-143">您必須使用–ShowAll 參數或– Owner 參數。</span><span class="sxs-lookup"><span data-stu-id="45905-143">You must use either the –ShowAll parameter or the –Owner parameter.</span></span> <span data-ttu-id="45905-144">如果您不使用這兩個參數，您匯入到備份組區的回應群組將不會列在 Cmdlet 所傳回的結果中。</span><span class="sxs-lookup"><span data-stu-id="45905-144">If you do not use either of these parameters, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>

    
    </div>

5.  <span data-ttu-id="45905-145">撥打已匯入的回應群組，並確認已正確處理呼叫，以確認匯入是否成功。</span><span class="sxs-lookup"><span data-stu-id="45905-145">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="45905-146">要求是正式代理群組成員的代理人，以登入其備份組區中的代理人群組。</span><span class="sxs-lookup"><span data-stu-id="45905-146">Request agents who are members of formal agent groups to sign in to their agent groups in the backup pool.</span></span>

7.  <span data-ttu-id="45905-147">照常管理及修改匯入的回應群組。</span><span class="sxs-lookup"><span data-stu-id="45905-147">Manage and modify the imported response groups as usual.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="45905-148">當回應群組位於備份組區中時，您必須使用 Lync Server 管理命令介面來管理這些群組。</span><span class="sxs-lookup"><span data-stu-id="45905-148">While the response groups are in the backup pool, you need to use Lync Server Management Shell to manage them.</span></span> <span data-ttu-id="45905-149">您無法使用 Lync Server 控制台管理匯入到備份組區的回應群組。</span><span class="sxs-lookup"><span data-stu-id="45905-149">You cannot use Lync Server Control Panel to manage the response groups that you imported to the backup pool.</span></span>

    
    </div>

8.  <span data-ttu-id="45905-150">在還原主要集區並完成回切後，請將匯入的主要集區回應群組匯出至備份組區。</span><span class="sxs-lookup"><span data-stu-id="45905-150">After the primary pool is restored and failback is complete, export the primary pool response groups that were imported to the backup pool.</span></span> <span data-ttu-id="45905-151">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="45905-151">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  <span data-ttu-id="45905-152">將回應群組匯入回主要集區。</span><span class="sxs-lookup"><span data-stu-id="45905-152">Import the response groups back to the primary pool.</span></span> <span data-ttu-id="45905-153">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="45905-153">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    <span data-ttu-id="45905-154">例如：</span><span class="sxs-lookup"><span data-stu-id="45905-154">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="45905-155">如果您在復原期間重建集區，不論是否使用相同或不同的完整功能變數名稱 (FQDN) ，您必須使用– OverwriteOwner 參數。</span><span class="sxs-lookup"><span data-stu-id="45905-155">If you rebuild a pool during recovery, whether with the same or a different fully qualified domain name (FQDN), you need to use the –OverwriteOwner parameter.</span></span> <span data-ttu-id="45905-156">根據經驗的經驗，您可以在將回應群組匯回主要集區時，永遠使用– OverwriteOwner 參數。</span><span class="sxs-lookup"><span data-stu-id="45905-156">As a rule of thumb, you can always use the –OverwriteOwner parameter when you import response groups back to the primary pool.</span></span>

    
    </div>
    
    <span data-ttu-id="45905-157">如果您部署了具有相同或不同 FQDN 的新集區 () 取代主要集區，而您想要使用來自新集區之備份組區的應用層級設定，請包含–ReplaceExistingSettings 參數。</span><span class="sxs-lookup"><span data-stu-id="45905-157">If you deployed a new pool (with the same or a different FQDN) to replace the primary pool, and you want to use the application-level settings from the backup pool for the new pool, include the –ReplaceExistingSettings parameter.</span></span> <span data-ttu-id="45905-158">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="45905-158">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    <span data-ttu-id="45905-159">例如：</span><span class="sxs-lookup"><span data-stu-id="45905-159">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="45905-160">如果您不想要使用備份組區中的設定取代新集區的應用層級設定和預設的等候音樂音訊檔，新集區將會使用預設的應用層級設定。</span><span class="sxs-lookup"><span data-stu-id="45905-160">If you don't want to replace the application-level settings and default music-on-hold audio file for the new pool with the settings from the backup pool, the new pool will use the default application-level settings.</span></span>

    
    </div>

10. <span data-ttu-id="45905-161">顯示匯入的回應群組設定，以確認匯入至主要集區成功。</span><span class="sxs-lookup"><span data-stu-id="45905-161">Verify that the import back to the primary pool was successful by displaying the imported response group configuration.</span></span> <span data-ttu-id="45905-162">執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="45905-162">Do the following:</span></span>
    
      - <span data-ttu-id="45905-163">顯示主要集區中的所有工作流程，並確認包括所有匯入的工作流程。</span><span class="sxs-lookup"><span data-stu-id="45905-163">Display all the workflows in the primary pool, and verify that all the imported workflows are included.</span></span> <span data-ttu-id="45905-164">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="45905-164">At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="45905-165">例如：</span><span class="sxs-lookup"><span data-stu-id="45905-165">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="45905-166">顯示主要集區中的所有佇列，並確認所有匯入的佇列都包含在內。</span><span class="sxs-lookup"><span data-stu-id="45905-166">Display all the queues in the primary pool, and verify that all the imported queues are included.</span></span> <span data-ttu-id="45905-167">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="45905-167">At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="45905-168">例如：</span><span class="sxs-lookup"><span data-stu-id="45905-168">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="45905-169">顯示主要集區中的所有代理程式群組，並確認所有匯入的 agent 群組都包含在內。</span><span class="sxs-lookup"><span data-stu-id="45905-169">Display all the agent groups in the primary pool, and verify that all the imported agent groups are included.</span></span> <span data-ttu-id="45905-170">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="45905-170">At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="45905-171">例如：</span><span class="sxs-lookup"><span data-stu-id="45905-171">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="45905-172">顯示主要集區中的所有上班時間，並確認包括所有匯入的公司內下班。</span><span class="sxs-lookup"><span data-stu-id="45905-172">Display all the hours of business in the primary pool, and verify that all the imported hours of business are included.</span></span> <span data-ttu-id="45905-173">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="45905-173">At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="45905-174">例如：</span><span class="sxs-lookup"><span data-stu-id="45905-174">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="45905-175">顯示主要集區中的所有假日集，並確認包括所有匯入的假日集。</span><span class="sxs-lookup"><span data-stu-id="45905-175">Display all the holiday sets in the primary pool, and verify that all the imported holiday sets are included.</span></span> <span data-ttu-id="45905-176">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="45905-176">At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="45905-177">例如：</span><span class="sxs-lookup"><span data-stu-id="45905-177">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. <span data-ttu-id="45905-178">撥打已匯入的回應群組，並確認已正確處理呼叫，以確認匯入是否成功。</span><span class="sxs-lookup"><span data-stu-id="45905-178">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

12. <span data-ttu-id="45905-179">（選用）從備份組區中移除主要集區所擁有的回應群組。</span><span class="sxs-lookup"><span data-stu-id="45905-179">Optionally, remove the response groups owned by the primary pool from the backup pool.</span></span> <span data-ttu-id="45905-180">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="45905-180">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    <span data-ttu-id="45905-181">例如：</span><span class="sxs-lookup"><span data-stu-id="45905-181">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="45905-182">此步驟會使用匯出的設定來建立新檔案，然後將其從備份組區中移除。</span><span class="sxs-lookup"><span data-stu-id="45905-182">This step creates a new file with the exported configuration, and then removes it from the backup pool.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

