---
title: Lync Server 2013 回應群組災難修復程式
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
ms.openlocfilehash: 254f9e95edfb445d996948a17064ae460dbdb7d8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214869"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="response-group-disaster-recovery-procedures-in-lync-server-2013"></a><span data-ttu-id="d41ee-102">Lync Server 2013 的回應群組嚴重損壞修復程式</span><span class="sxs-lookup"><span data-stu-id="d41ee-102">Response group disaster recovery procedures in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d41ee-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d41ee-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d41ee-104">在災害復原的容錯移轉階段期間，回應群組位在多個集區中：主要集區 (無法使用) 以及備份集區中。</span><span class="sxs-lookup"><span data-stu-id="d41ee-104">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool.</span></span> <span data-ttu-id="d41ee-105">兩個集區中的回應群組都有相同的名稱和相同的擁有者 (主要集區)，但其父系不同。</span><span class="sxs-lookup"><span data-stu-id="d41ee-105">The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span> <span data-ttu-id="d41ee-106">在這段時間內，回應群組 Cmdlet 的運作方式稍有不同。</span><span class="sxs-lookup"><span data-stu-id="d41ee-106">During this time, Response Group cmdlets work a little differently.</span></span> <span data-ttu-id="d41ee-107">請務必依照下列程式所指定的方法使用參數。</span><span class="sxs-lookup"><span data-stu-id="d41ee-107">Be sure to use parameters as specified in the following procedure.</span></span> <span data-ttu-id="d41ee-108">如需在容錯移轉階段內 Cmdlet 如何運作的詳細資訊，請參閱《 Lync Server 2013：在嚴重損壞復原期間復原回應群組」中的 NextHop 博客文章 [https://go.microsoft.com/fwlink/p/?LinkId=263957](https://go.microsoft.com/fwlink/p/?linkid=263957) 。</span><span class="sxs-lookup"><span data-stu-id="d41ee-108">For details about how cmdlets work during the failover phase, see NextHop blog article "Lync Server 2013: Recovering Response Groups During Disaster Recovery" at [https://go.microsoft.com/fwlink/p/?LinkId=263957](https://go.microsoft.com/fwlink/p/?linkid=263957).</span></span> <span data-ttu-id="d41ee-109">此博客文章也適用于已發行版本本的 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="d41ee-109">This blog article also applies to the released version of Lync Server 2013.</span></span>

<span data-ttu-id="d41ee-110">使用下列程式中的步驟來準備和執行 Lync Server 回應群組服務的嚴重損壞修復。</span><span class="sxs-lookup"><span data-stu-id="d41ee-110">Use the steps in the following procedure to prepare for and perform disaster recovery for Lync Server Response Group service.</span></span>

<div>

## <a name="to-fail-over-and-fail-back-response-group"></a><span data-ttu-id="d41ee-111">容錯移轉和容錯回復回應群組</span><span class="sxs-lookup"><span data-stu-id="d41ee-111">To fail over and fail back Response Group</span></span>

1.  <span data-ttu-id="d41ee-112">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="d41ee-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d41ee-113">定期執行備份。</span><span class="sxs-lookup"><span data-stu-id="d41ee-113">Routinely perform backups.</span></span> <span data-ttu-id="d41ee-114">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="d41ee-114">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="d41ee-115">例如：</span><span class="sxs-lookup"><span data-stu-id="d41ee-115">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  <span data-ttu-id="d41ee-116">在中斷期間，在容錯移轉至備份組區之後，將回應群組匯入至備份組區。</span><span class="sxs-lookup"><span data-stu-id="d41ee-116">During an outage, after failover to the backup pool, import the response groups to the backup pool.</span></span> <span data-ttu-id="d41ee-117">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="d41ee-117">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="d41ee-118">如果您想要以主要集區中的設定取代備份組區中的應用層級設定，請加入–ReplaceExistingSettings 參數。</span><span class="sxs-lookup"><span data-stu-id="d41ee-118">If you want to replace the application-level settings in the backup pool with the settings from the primary pool, include the –ReplaceExistingSettings parameter.</span></span> <span data-ttu-id="d41ee-119">例如：</span><span class="sxs-lookup"><span data-stu-id="d41ee-119">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="d41ee-120">如果您未取代備份組區中的設定，且無法復原主要集區，主要集區設定將會遺失。</span><span class="sxs-lookup"><span data-stu-id="d41ee-120">If you do not replace the settings in the backup pool and the primary pool can't be recovered, the primary pool settings will be lost.</span></span> <span data-ttu-id="d41ee-121">如需詳細資訊，請參閱 <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">在 Lync Server 2013 中規劃回應群組</A>嚴重損壞修復。</span><span class="sxs-lookup"><span data-stu-id="d41ee-121">For details, see <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">Planning for response group disaster recovery in Lync Server 2013</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="d41ee-122">顯示匯入的回應群組，以確認匯入成功。</span><span class="sxs-lookup"><span data-stu-id="d41ee-122">Verify that the import was successful by displaying the imported response groups.</span></span> <span data-ttu-id="d41ee-123">匯入的回應群組仍然歸主要集區所有。</span><span class="sxs-lookup"><span data-stu-id="d41ee-123">The imported response groups are still owned by the primary pool.</span></span> <span data-ttu-id="d41ee-124">執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="d41ee-124">Do the following:</span></span>
    
      - <span data-ttu-id="d41ee-125">顯示主要集區所擁有之備份組區中的所有工作流程，並確認包括所有主要集區工作流程。</span><span class="sxs-lookup"><span data-stu-id="d41ee-125">Display all the workflows in the backup pool that are owned by the primary pool, and verify that all the primary pool workflows are included.</span></span> <span data-ttu-id="d41ee-126">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="d41ee-126">At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="d41ee-127">例如：</span><span class="sxs-lookup"><span data-stu-id="d41ee-127">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - <span data-ttu-id="d41ee-128">顯示主要集區所擁有之備份組區中的所有佇列，並確認所有主要集區佇列都已包含。</span><span class="sxs-lookup"><span data-stu-id="d41ee-128">Display all the queues in the backup pool that are owned by the primary pool, and verify that all the primary pool queues are included.</span></span> <span data-ttu-id="d41ee-129">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="d41ee-129">At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="d41ee-130">例如：</span><span class="sxs-lookup"><span data-stu-id="d41ee-130">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="d41ee-131">顯示主要集區所擁有之備份組區中的所有代理程式群組，並確認所有的主要集區代理程式群組都包含在內。</span><span class="sxs-lookup"><span data-stu-id="d41ee-131">Display all the agent groups in the backup pool that are owned by the primary pool, and verify that all the primary pool agent groups are included.</span></span> <span data-ttu-id="d41ee-132">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="d41ee-132">At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="d41ee-133">例如：</span><span class="sxs-lookup"><span data-stu-id="d41ee-133">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="d41ee-134">顯示主要集區所擁有之備份組區中的所有上班時間，並確認包括所有的主要集區工作。</span><span class="sxs-lookup"><span data-stu-id="d41ee-134">Display all the hours of business in the backup pool that are owned by the primary pool, and verify that all the primary pool hours of business are included.</span></span> <span data-ttu-id="d41ee-135">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="d41ee-135">At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="d41ee-136">例如：</span><span class="sxs-lookup"><span data-stu-id="d41ee-136">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="d41ee-137">顯示主要集區所擁有之備份組區中的所有假日集，並確認所有主要集區假日集皆已包含在內。</span><span class="sxs-lookup"><span data-stu-id="d41ee-137">Display all the holiday sets in the backup pool that are owned by the primary pool, and verify that all the primary pool holiday sets are included.</span></span> <span data-ttu-id="d41ee-138">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="d41ee-138">At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="d41ee-139">例如：</span><span class="sxs-lookup"><span data-stu-id="d41ee-139">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    <span data-ttu-id="d41ee-140">或者，您可以顯示備份組區中所有的回應群組，包括主要集區所擁有的所有回應群組，以及備份組區所擁有的任何回應群組，而不是–ShowAll 使用– Owner 參數。</span><span class="sxs-lookup"><span data-stu-id="d41ee-140">Alternatively, you can display all the response groups in the backup pool, including the ones owned by the primary pool and the ones owned by the backup pool by using the –ShowAll parameter instead of the –Owner parameter.</span></span> <span data-ttu-id="d41ee-141">例如：</span><span class="sxs-lookup"><span data-stu-id="d41ee-141">For example:</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d41ee-142">您必須使用–ShowAll 參數或– Owner 參數。</span><span class="sxs-lookup"><span data-stu-id="d41ee-142">You must use either the –ShowAll parameter or the –Owner parameter.</span></span> <span data-ttu-id="d41ee-143">如果您不使用這兩個參數，您匯入到備份組區的回應群組將不會列在 Cmdlet 所傳回的結果中。</span><span class="sxs-lookup"><span data-stu-id="d41ee-143">If you do not use either of these parameters, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>

    
    </div>

5.  <span data-ttu-id="d41ee-144">撥打已匯入的回應群組，並確認已正確處理呼叫，以確認匯入是否成功。</span><span class="sxs-lookup"><span data-stu-id="d41ee-144">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="d41ee-145">要求是正式代理群組成員的代理人，以登入其備份組區中的代理人群組。</span><span class="sxs-lookup"><span data-stu-id="d41ee-145">Request agents who are members of formal agent groups to sign in to their agent groups in the backup pool.</span></span>

7.  <span data-ttu-id="d41ee-146">照常管理及修改匯入的回應群組。</span><span class="sxs-lookup"><span data-stu-id="d41ee-146">Manage and modify the imported response groups as usual.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d41ee-147">當回應群組位於備份組區中時，您必須使用 Lync Server 管理命令介面來管理這些群組。</span><span class="sxs-lookup"><span data-stu-id="d41ee-147">While the response groups are in the backup pool, you need to use Lync Server Management Shell to manage them.</span></span> <span data-ttu-id="d41ee-148">您無法使用 Lync Server 控制台管理匯入到備份組區的回應群組。</span><span class="sxs-lookup"><span data-stu-id="d41ee-148">You cannot use Lync Server Control Panel to manage the response groups that you imported to the backup pool.</span></span>

    
    </div>

8.  <span data-ttu-id="d41ee-149">在還原主要集區並完成回切後，請將匯入的主要集區回應群組匯出至備份組區。</span><span class="sxs-lookup"><span data-stu-id="d41ee-149">After the primary pool is restored and failback is complete, export the primary pool response groups that were imported to the backup pool.</span></span> <span data-ttu-id="d41ee-150">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="d41ee-150">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  <span data-ttu-id="d41ee-151">將回應群組匯入回主要集區。</span><span class="sxs-lookup"><span data-stu-id="d41ee-151">Import the response groups back to the primary pool.</span></span> <span data-ttu-id="d41ee-152">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="d41ee-152">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    <span data-ttu-id="d41ee-153">例如：</span><span class="sxs-lookup"><span data-stu-id="d41ee-153">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d41ee-154">如果您在復原期間重建集區，不論是否使用相同或不同的完整功能變數名稱 (FQDN) ，您必須使用– OverwriteOwner 參數。</span><span class="sxs-lookup"><span data-stu-id="d41ee-154">If you rebuild a pool during recovery, whether with the same or a different fully qualified domain name (FQDN), you need to use the –OverwriteOwner parameter.</span></span> <span data-ttu-id="d41ee-155">根據經驗的經驗，您可以在將回應群組匯回主要集區時，永遠使用– OverwriteOwner 參數。</span><span class="sxs-lookup"><span data-stu-id="d41ee-155">As a rule of thumb, you can always use the –OverwriteOwner parameter when you import response groups back to the primary pool.</span></span>

    
    </div>
    
    <span data-ttu-id="d41ee-156">如果您部署了具有相同或不同 FQDN 的新集區 () 取代主要集區，而您想要使用來自新集區之備份組區的應用層級設定，請包含–ReplaceExistingSettings 參數。</span><span class="sxs-lookup"><span data-stu-id="d41ee-156">If you deployed a new pool (with the same or a different FQDN) to replace the primary pool, and you want to use the application-level settings from the backup pool for the new pool, include the –ReplaceExistingSettings parameter.</span></span> <span data-ttu-id="d41ee-157">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="d41ee-157">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    <span data-ttu-id="d41ee-158">例如：</span><span class="sxs-lookup"><span data-stu-id="d41ee-158">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d41ee-159">如果您不想要使用備份組區中的設定取代新集區的應用層級設定和預設的等候音樂音訊檔，新集區將會使用預設的應用層級設定。</span><span class="sxs-lookup"><span data-stu-id="d41ee-159">If you don't want to replace the application-level settings and default music-on-hold audio file for the new pool with the settings from the backup pool, the new pool will use the default application-level settings.</span></span>

    
    </div>

10. <span data-ttu-id="d41ee-160">顯示匯入的回應群組設定，以確認匯入至主要集區成功。</span><span class="sxs-lookup"><span data-stu-id="d41ee-160">Verify that the import back to the primary pool was successful by displaying the imported response group configuration.</span></span> <span data-ttu-id="d41ee-161">執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="d41ee-161">Do the following:</span></span>
    
      - <span data-ttu-id="d41ee-162">顯示主要集區中的所有工作流程，並確認包括所有匯入的工作流程。</span><span class="sxs-lookup"><span data-stu-id="d41ee-162">Display all the workflows in the primary pool, and verify that all the imported workflows are included.</span></span> <span data-ttu-id="d41ee-163">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="d41ee-163">At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="d41ee-164">例如：</span><span class="sxs-lookup"><span data-stu-id="d41ee-164">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="d41ee-165">顯示主要集區中的所有佇列，並確認所有匯入的佇列都包含在內。</span><span class="sxs-lookup"><span data-stu-id="d41ee-165">Display all the queues in the primary pool, and verify that all the imported queues are included.</span></span> <span data-ttu-id="d41ee-166">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="d41ee-166">At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="d41ee-167">例如：</span><span class="sxs-lookup"><span data-stu-id="d41ee-167">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="d41ee-168">顯示主要集區中的所有代理程式群組，並確認所有匯入的 agent 群組都包含在內。</span><span class="sxs-lookup"><span data-stu-id="d41ee-168">Display all the agent groups in the primary pool, and verify that all the imported agent groups are included.</span></span> <span data-ttu-id="d41ee-169">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="d41ee-169">At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="d41ee-170">例如：</span><span class="sxs-lookup"><span data-stu-id="d41ee-170">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="d41ee-171">顯示主要集區中的所有上班時間，並確認包括所有匯入的公司內下班。</span><span class="sxs-lookup"><span data-stu-id="d41ee-171">Display all the hours of business in the primary pool, and verify that all the imported hours of business are included.</span></span> <span data-ttu-id="d41ee-172">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="d41ee-172">At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="d41ee-173">例如：</span><span class="sxs-lookup"><span data-stu-id="d41ee-173">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="d41ee-174">顯示主要集區中的所有假日集，並確認包括所有匯入的假日集。</span><span class="sxs-lookup"><span data-stu-id="d41ee-174">Display all the holiday sets in the primary pool, and verify that all the imported holiday sets are included.</span></span> <span data-ttu-id="d41ee-175">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="d41ee-175">At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="d41ee-176">例如：</span><span class="sxs-lookup"><span data-stu-id="d41ee-176">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. <span data-ttu-id="d41ee-177">撥打已匯入的回應群組，並確認已正確處理呼叫，以確認匯入是否成功。</span><span class="sxs-lookup"><span data-stu-id="d41ee-177">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

12. <span data-ttu-id="d41ee-178">（選用）從備份組區中移除主要集區所擁有的回應群組。</span><span class="sxs-lookup"><span data-stu-id="d41ee-178">Optionally, remove the response groups owned by the primary pool from the backup pool.</span></span> <span data-ttu-id="d41ee-179">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="d41ee-179">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    <span data-ttu-id="d41ee-180">例如：</span><span class="sxs-lookup"><span data-stu-id="d41ee-180">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d41ee-181">此步驟會使用匯出的設定來建立新檔案，然後將其從備份組區中移除。</span><span class="sxs-lookup"><span data-stu-id="d41ee-181">This step creates a new file with the exported configuration, and then removes it from the backup pool.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

