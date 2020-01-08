---
title: Lync Server 2013：規劃回應群組災害復原
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for response group disaster recovery
ms:assetid: 14e0f5dc-77cd-42cd-a9c9-4d0da38fb1cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204699(v=OCS.15)
ms:contentKeyID: 48183482
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70622364349eb83ecbc171cb3d5bf894ba03d3f9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978160"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-response-group-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="9b292-102">在 Lync Server 2013 中規劃回應群組災害復原</span><span class="sxs-lookup"><span data-stu-id="9b292-102">Planning for response group disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b292-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9b292-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="9b292-104">本節將說明一些針對災難復原準備回應群組的方法，並提供災害復原程式的概覽。</span><span class="sxs-lookup"><span data-stu-id="9b292-104">This section describes some ways to prepare response groups for disaster recovery and provides an overview of the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-response-group-disaster-recovery"></a><span data-ttu-id="9b292-105">準備回應群組災害復原</span><span class="sxs-lookup"><span data-stu-id="9b292-105">Preparing for Response Group Disaster Recovery</span></span>

<span data-ttu-id="9b292-106">當您準備及執行災害復原程式時，請記住下列事項。</span><span class="sxs-lookup"><span data-stu-id="9b292-106">Keep the following in mind when you prepare for and carry out disaster recovery procedures.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9b292-107">在共存環境中，本檔中所述的災難復原程式只支援 Lync Server 2013 回應群組。</span><span class="sxs-lookup"><span data-stu-id="9b292-107">In a coexistence environment, only the Lync Server 2013 response groups are supported for the disaster recovery procedures described in this document.</span></span>



</div>

  - <span data-ttu-id="9b292-108">在您進行容量規劃時規劃災害復原。</span><span class="sxs-lookup"><span data-stu-id="9b292-108">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="9b292-109">針對災害復原容量，配對池中的每個池都應該能夠處理兩個池中所有回應群組的工作量。</span><span class="sxs-lookup"><span data-stu-id="9b292-109">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of all the response groups in both pools.</span></span> <span data-ttu-id="9b292-110">如需回應群組容量規劃的詳細資料，請參閱[Lync Server 2013 中的 [回應] 群組容量規劃](lync-server-2013-capacity-planning-for-response-group.md)。</span><span class="sxs-lookup"><span data-stu-id="9b292-110">For details about Response Group capacity planning, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).</span></span>

  - <span data-ttu-id="9b292-111">使用本文所述的 export 程式，在您部署回應群組應用程式的所有前端池中，定期執行所有回應群組設定的一般備份複本。</span><span class="sxs-lookup"><span data-stu-id="9b292-111">Take regular backup copies of all the response group configurations in all the Front End pools where you deployed the Response Group application by using the export procedure described in this document.</span></span> <span data-ttu-id="9b292-112">如需詳細資訊，請參閱[Lync Server 2013 中的回應群組災害復原程式](lync-server-2013-response-group-disaster-recovery-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="9b292-112">For details, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span> <span data-ttu-id="9b292-113">將備份複本保留在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="9b292-113">Keep the backup copies in a safe location.</span></span>

  - <span data-ttu-id="9b292-114">針對您用於回應群組應用程式的所有原始音訊檔案，保留一個單獨的備份複本，包括任何錄製和音樂保留中的檔案。</span><span class="sxs-lookup"><span data-stu-id="9b292-114">Keep a separate backup copy of all the original audio files you used for the Response Group application, including any recordings and music-on-hold files.</span></span> <span data-ttu-id="9b292-115">將備份檔案保留在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="9b292-115">Keep the backup files in a safe location.</span></span>

  - <span data-ttu-id="9b292-116">針對 Lync Server 2013 災害復原，所有回應群組設定在您的部署中都必須有唯一的名稱。</span><span class="sxs-lookup"><span data-stu-id="9b292-116">For Lync Server 2013 disaster recovery, all Response Group settings must have unique names across your deployment.</span></span> <span data-ttu-id="9b292-117">此需求適用于工作流程、[佇列]、[代理群組]、[假日集] 和 [工作時間]。</span><span class="sxs-lookup"><span data-stu-id="9b292-117">This requirement applies to workflows, queues, agent groups, holiday sets, and hours of business.</span></span> <span data-ttu-id="9b292-118">當主要和備份池仍在使用中時，以及在您需要啟動任何容錯移轉程式之前，您應該確認符合此需求。</span><span class="sxs-lookup"><span data-stu-id="9b292-118">You should verify that this requirement is met when the primary and backup pools are still active, and before you need to initiate any failover procedure.</span></span> <span data-ttu-id="9b292-119">如果您在將回應群組資料匯入到備份區時遇到名稱衝突，匯入就會失敗。</span><span class="sxs-lookup"><span data-stu-id="9b292-119">If you encounter name conflicts while importing response group data to the backup pool, the import fails.</span></span> <span data-ttu-id="9b292-120">若要完成匯入及容錯移轉程式，您必須先重新命名備份池中的回應群組物件，或使用**CsRgsConfiguration** Cmdlet 和– ResolveNameConflicts 參數來解決名稱衝突，方法是將唯一識別號碼附加至回應群組物件，以自動解決衝突。</span><span class="sxs-lookup"><span data-stu-id="9b292-120">To complete the import and failover procedure, you need to resolve the name conflicts by renaming the response group object in the backup pool or by using the **Import-CsRgsConfiguration** cmdlet with the –ResolveNameConflicts parameter to automatically resolve the conflict by appending a unique identifying number to the response group object.</span></span>

  - <span data-ttu-id="9b292-121">一般來說，我們建議您執行每日備份，但如果您有大量的變更，您可能會想要排程更頻繁的備份。</span><span class="sxs-lookup"><span data-stu-id="9b292-121">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups.</span></span> <span data-ttu-id="9b292-122">災難事件中可能會遺失的資訊量，取決於備份頻率，以及變更的頻率與數量。</span><span class="sxs-lookup"><span data-stu-id="9b292-122">The amount of information you can lose in the event of a disaster depends on the frequency of your backups, as well as the frequency and volume of changes.</span></span>

  - <span data-ttu-id="9b292-123">您可以在發生災難或容錯移轉作業之前，將回應群組匯入到備份池。</span><span class="sxs-lookup"><span data-stu-id="9b292-123">It is possible to import response groups to a backup pool before a disaster or failover operation occurs.</span></span> <span data-ttu-id="9b292-124">快速匯入回應群組會減少停機時間，因為呼叫傳送至備份池之後，就可以在備份池中還原 Lync Server 回應群組服務。</span><span class="sxs-lookup"><span data-stu-id="9b292-124">Importing response groups in advance reduces downtime, because the Lync Server Response Group service can be restored in the backup pool as soon as calls are routed to the backup pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9b292-125">在容錯移轉完成之前，回應群組應用程式無法到達任何駐留在非作用中的池中的代理程式。</span><span class="sxs-lookup"><span data-stu-id="9b292-125">The Response Group application cannot reach any agents homed in an inactive pool until failover is complete.</span></span> <span data-ttu-id="9b292-126">在此期間，回應群組應用程式會處理呼叫，就好像這些代理無法使用一樣。</span><span class="sxs-lookup"><span data-stu-id="9b292-126">During this time, the Response Group application processes calls as if those agents are unavailable.</span></span>

    
    </div>

</div>

<div>

## <a name="response-group-disaster-recovery-process"></a><span data-ttu-id="9b292-127">回應群組災害復原程式</span><span class="sxs-lookup"><span data-stu-id="9b292-127">Response Group Disaster Recovery Process</span></span>

<span data-ttu-id="9b292-128">在發生災難的情況下，您可以使用下列其中一種恢復方法來復原回應群組：</span><span class="sxs-lookup"><span data-stu-id="9b292-128">In the event of a disaster, you can recover response groups by using either of the following recovery approaches:</span></span>

  - <span data-ttu-id="9b292-129">容錯移轉到備份池，然後將容錯回復回原始池。</span><span class="sxs-lookup"><span data-stu-id="9b292-129">Fail over to a backup pool and then fail back to the original pool.</span></span>

  - <span data-ttu-id="9b292-130">容錯移轉到備份池中，使用不同的完整功能變數名稱（FQDN）建立新的池，然後將回應群組匯入新的池中。</span><span class="sxs-lookup"><span data-stu-id="9b292-130">Fail over to a backup pool, create a new pool with a different fully qualified domain name (FQDN), and then import the response groups to the new pool.</span></span>

<span data-ttu-id="9b292-131">在災害復原的容錯移轉階段，回應群組位於多個池中： [主要] 池中（即無法使用）及 [備份] 池中。</span><span class="sxs-lookup"><span data-stu-id="9b292-131">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool.</span></span> <span data-ttu-id="9b292-132">兩個彙集中的回應群組都有相同的名稱和相同的擁有者（主要池），但它們擁有不同的父項。</span><span class="sxs-lookup"><span data-stu-id="9b292-132">The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span>

<span data-ttu-id="9b292-133">當您使用不同的 FQDN 建立新的池來復原時，您必須將新的池指派為在您匯入時將它指派給回應群組的擁有者。</span><span class="sxs-lookup"><span data-stu-id="9b292-133">When you recover by creating a new pool with a different FQDN, you need to assign the new pool as the owner of the response groups when you import them.</span></span> <span data-ttu-id="9b292-134">回應群組的擁有者仍會保留在原始池中，除非或在您明確地重新指派擁有權的情況下，將-OverwriteOwner 參數與**Import CsRgsConfiguration** Cmdlet 結合使用。</span><span class="sxs-lookup"><span data-stu-id="9b292-134">Ownership of response groups remains with the original pool unless or until you explicitly reassign ownership by using the –OverwriteOwner parameter with the **Import-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9b292-135">如果您在復原期間重建池（亦即回應群組資料庫為空白），無論您是否使用相同的 FQDN，您也必須使用– OverwriteOwner 參數。</span><span class="sxs-lookup"><span data-stu-id="9b292-135">You also need to use the –OverwriteOwner parameter if you rebuilt the pool during the recovery (that is, the Response Group database is empty), whether or not you use the same FQDN.</span></span> <span data-ttu-id="9b292-136">如果您沒有重建該池，就不需要使用– OverwriteOwner 參數，但只要將回應群組匯入主要的池中，就可以使用這個參數。</span><span class="sxs-lookup"><span data-stu-id="9b292-136">You do not need to use the –OverwriteOwner parameter if you did not rebuild the pool, but it is permissible to use this parameter whenever you import response groups back to the primary pool.</span></span>



</div>

<span data-ttu-id="9b292-137">每個 pool 只能定義一組應用層回應群組設定設定。</span><span class="sxs-lookup"><span data-stu-id="9b292-137">You can define only one set of application-level Response Group configuration settings per pool.</span></span> <span data-ttu-id="9b292-138">這些設定包括預設的 [隨用音樂保留] 設定、預設的 [音樂保留] 音訊檔案、[代理程式 ringback 寬限期]，以及 [通話內容] 設定。</span><span class="sxs-lookup"><span data-stu-id="9b292-138">These settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="9b292-139">若要查看這些設定，請執行**CsRgsConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9b292-139">To view these configuration settings, run the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="9b292-140">如需**CsRgsConfiguration** Cmdlet 的詳細資訊，請參閱[CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="9b292-140">For details about the **Get-CsRgsConfiguration** cmdlet, see [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).</span></span>

<span data-ttu-id="9b292-141">您可以使用**CsRgsConfiguration** Cmdlet 和– ReplaceExistingSettings 參數，將這些應用程式層級的設定從一個池中轉移到另一個，但這樣做會覆寫目的地池中的設定。</span><span class="sxs-lookup"><span data-stu-id="9b292-141">You can transfer these application-level settings from one pool to another by using the **Import-CsRgsConfiguration** cmdlet with the –ReplaceExistingSettings parameter, but doing so overrides the settings in the destination pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9b292-142">關於將設定轉移至另一個池的限制式，只適用于應用程式層級設定和預設的音樂保留音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="9b292-142">This constraint about transferring settings to another pool is true only for the application-level settings and the default music-on-hold audio file.</span></span> <span data-ttu-id="9b292-143">它不適用於 [代理群組]、[佇列]、[工作流程]、[上班時間] 和 [假日集]。</span><span class="sxs-lookup"><span data-stu-id="9b292-143">It does not apply to agent groups, queues, workflows, business hours, and holiday sets.</span></span>



</div>

<span data-ttu-id="9b292-144">如果您不想在災難期間取代備份池中的應用層級設定，且無法復原主要池，則主要池中的應用層級設定將會遺失。</span><span class="sxs-lookup"><span data-stu-id="9b292-144">If you don't want to replace the application-level settings in the backup pool during a disaster and the primary pool can't be recovered, the application-level settings from the primary pool will be lost.</span></span> <span data-ttu-id="9b292-145">如果您需要在恢復期間建立新的池來取代主要池，您可以使用相同的 FQDN 或不同的 FQDN，來復原原始的應用層級設定。</span><span class="sxs-lookup"><span data-stu-id="9b292-145">If you need to create a new pool to replace the primary pool during recovery, either with the same FQDN or with a different FQDN, you can't recover the original application-level settings.</span></span> <span data-ttu-id="9b292-146">在這種情況下，您需要使用這些設定來設定新的池子，並包含 [音樂保留] 音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="9b292-146">In this case, you need to configure the new pool with these settings and include the music-on-hold audio file.</span></span>

<span data-ttu-id="9b292-147">如果您決定使用**Import CsRgsConfiguration** Cmdlet，在災難期間將應用程式層級設定從主要池中傳送到備份池，您可以在恢復期間將這些設定從主要池轉移到新的池中，就與從主要的池中轉移到備份池一樣。</span><span class="sxs-lookup"><span data-stu-id="9b292-147">If you decide to use the **Import-CsRgsConfiguration** cmdlet to transfer application-level settings from the primary pool to the backup pool during a disaster, you can then transfer the settings from the backup pool to the new pool during recovery in the same way that you transferred them from the primary pool to the backup pool.</span></span>

<span data-ttu-id="9b292-148">下表是說明復原群組中所涉及之步驟的概覽。</span><span class="sxs-lookup"><span data-stu-id="9b292-148">The following table is an overview of the steps involved in recovering response groups.</span></span>

<span data-ttu-id="9b292-149">如需執行這些步驟的詳細資訊，請參閱[Lync Server 2013 中的回應群組災害復原程式](lync-server-2013-response-group-disaster-recovery-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="9b292-149">For details about performing these steps, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span>

### <a name="response-group-disaster-recovery-steps"></a><span data-ttu-id="9b292-150">回應群組災害復原步驟</span><span class="sxs-lookup"><span data-stu-id="9b292-150">Response Group Disaster Recovery Steps</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9b292-151">分</span><span class="sxs-lookup"><span data-stu-id="9b292-151">Phase</span></span></th>
<th><span data-ttu-id="9b292-152">步驟</span><span class="sxs-lookup"><span data-stu-id="9b292-152">Steps</span></span></th>
<th><span data-ttu-id="9b292-153">必要的群組和角色</span><span class="sxs-lookup"><span data-stu-id="9b292-153">Required groups and roles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b292-154">在中斷前</span><span class="sxs-lookup"><span data-stu-id="9b292-154">Before outage</span></span></p></td>
<td><p><span data-ttu-id="9b292-155">定期執行<strong>Export CsRgsConfiguration</strong> Cmdlet，在部署回應群組應用程式的所有前端池中，建立所有回應群組設定的備份。</span><span class="sxs-lookup"><span data-stu-id="9b292-155">On a routine basis, run the <strong>Export-CsRgsConfiguration</strong> cmdlet to create backups of all Response Group configurations in all Front End pools where Response Group application is deployed.</span></span></p></td>
<td><p><span data-ttu-id="9b292-156">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="9b292-156">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="9b292-157">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="9b292-157">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b292-158">在中斷期間</span><span class="sxs-lookup"><span data-stu-id="9b292-158">During outage</span></span></p></td>
<td><p><span data-ttu-id="9b292-159">執行匯<strong>入-CsRgsConfiguration</strong> Cmdlet，將備份的 Lync Server 回應群組服務設定從主要池中匯入到備份池。</span><span class="sxs-lookup"><span data-stu-id="9b292-159">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the backed up Lync Server Response Group service configuration from the primary pool to the backup pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="9b292-160">如果您想要將備份池中的應用層回應群組設定取代為主要池中的設定，請使用– ReplaceExistingSettings 參數。</span><span class="sxs-lookup"><span data-stu-id="9b292-160">Use the –ReplaceExistingSettings parameter if you want to replace application-level Response Group settings in the backup pool with the settings from the primary pool.</span></span> <span data-ttu-id="9b292-161">如果您沒有將應用程式層級設定從主要池轉移到備份池，且無法復原主要池，您將會遺失主要池中的設定。</span><span class="sxs-lookup"><span data-stu-id="9b292-161">If you do not transfer the application-level settings from the primary pool to the backup pool, and the primary pool can't be recovered, you will lose the settings from the primary pool.</span></span>


</div></td>
<td><p><span data-ttu-id="9b292-162">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="9b292-162">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="9b292-163">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="9b292-163">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b292-164">匯入之後</span><span class="sxs-lookup"><span data-stu-id="9b292-164">After importing</span></span></p></td>
<td><p><span data-ttu-id="9b292-165">執行回應群組 Cmdlet 時，請使用– ShowAll 參數（顯示所有回應群組）或– Owner 參數（若要只顯示已匯入的回應群組），以驗證是否已將所有回應群組設定匯入到備份池中。</span><span class="sxs-lookup"><span data-stu-id="9b292-165">Run Response Group cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were imported to the backup pool.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="9b292-166">如果您不使用– ShowAll 參數或– Owner 參數，您匯入到備份池中的回應群組將不會列在 Cmdlet 所傳回的結果中。</span><span class="sxs-lookup"><span data-stu-id="9b292-166">If you do not use either the –ShowAll parameter or the –Owner parameter, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>


</div>
<p><span data-ttu-id="9b292-167">執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="9b292-167">Run the following cmdlets:</span></span></p>
<ul>
<li><p><span data-ttu-id="9b292-168"><strong>CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="9b292-168"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="9b292-169"><strong>CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="9b292-169"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="9b292-170"><strong>CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="9b292-170"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="9b292-171"><strong>CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="9b292-171"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="9b292-172"><strong>Get-CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="9b292-172"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9b292-173">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="9b292-173">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="9b292-174">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="9b292-174">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b292-175">容錯移轉之後</span><span class="sxs-lookup"><span data-stu-id="9b292-175">After failover</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="9b292-176">將測試呼叫放到已匯入到備份池中的回應群組，並確認正確處理該通話。</span><span class="sxs-lookup"><span data-stu-id="9b292-176">Place a test call to a response group that was imported to the backup pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="9b292-177">所有正式代理程式都必須重新登入其備份池上的正式群組。</span><span class="sxs-lookup"><span data-stu-id="9b292-177">All formal agents must sign in again to their formal groups on backup pool.</span></span></p></li>
<li><p><span data-ttu-id="9b292-178">管理設定變更：</span><span class="sxs-lookup"><span data-stu-id="9b292-178">Manage configuration changes:</span></span></p>
<p><span data-ttu-id="9b292-179">備份池中的回應群組（無論是匯入到備份池或由備份池所擁有），都可以在中斷期間修改為正常。</span><span class="sxs-lookup"><span data-stu-id="9b292-179">Response groups in the backup pool, whether imported to the backup pool or owned by the backup pool, can be modified as usual during the outage.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="9b292-180">您必須使用 Lync Server 管理命令介面來管理您匯入到備份池中的回應群組。</span><span class="sxs-lookup"><span data-stu-id="9b292-180">You must use Lync Server Management Shell to manage the response groups that you imported to the backup pool.</span></span> <span data-ttu-id="9b292-181">當這些回應群組位於備份池中時，您無法使用 Lync Server [控制台] 管理這些回應群組。</span><span class="sxs-lookup"><span data-stu-id="9b292-181">You cannot use Lync Server Control Panel to manage these response groups while they are in the backup pool.</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="9b292-182">不適用</span><span class="sxs-lookup"><span data-stu-id="9b292-182">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b292-183">在恢復之後，在回切前</span><span class="sxs-lookup"><span data-stu-id="9b292-183">After recovery, before failback</span></span></p></td>
<td><p><span data-ttu-id="9b292-184">執行<strong>匯出-CsRgsConfiguration</strong> Cmdlet，指定-Source 參數作為備份池，並將– Owner （擁有者）參數做為主要池，以匯出來自備份池中的主要池所擁有的回應群組。</span><span class="sxs-lookup"><span data-stu-id="9b292-184">Run the <strong>Export-CsRgsConfiguration</strong> cmdlet specifying the -Source parameter as the backup pool and the –Owner parameter as the primary pool to export the response groups owned by the primary pool from the backup pool.</span></span></p></td>
<td><p><span data-ttu-id="9b292-185">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="9b292-185">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="9b292-186">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="9b292-186">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b292-187">回切後</span><span class="sxs-lookup"><span data-stu-id="9b292-187">After failback</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="9b292-188">執行匯<strong>入-CsRgsConfiguration</strong> Cmdlet，將回應群組匯入到主要池。</span><span class="sxs-lookup"><span data-stu-id="9b292-188">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the response groups back to the primary pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="9b292-189">如果無法復原主要池，且您要部署新的池來取代它，請使用– ReplaceExistingSettings 參數，將應用程式層級設定從備份池中轉移到新的池中。</span><span class="sxs-lookup"><span data-stu-id="9b292-189">If the primary pool can't be recovered and you deploy a new pool to replace it, use the –ReplaceExistingSettings parameter to transfer the application-level settings from the backup pool to the new pool.</span></span> <span data-ttu-id="9b292-190">如果您沒有從備份池中轉移設定，新的池會使用預設設定。</span><span class="sxs-lookup"><span data-stu-id="9b292-190">If you do not transfer the settings from the backup pool, the new pool will use the default settings.</span></span>


</div></li>
<li><p><span data-ttu-id="9b292-191">請執行下列 Cmdlet 與– ShowAll 參數（以顯示所有回應群組）或– Owner 參數（若要只顯示匯入的回應群組），以確認所有回應群組設定都已成功匯入到主要池中：</span><span class="sxs-lookup"><span data-stu-id="9b292-191">Run the following cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were successfully imported back to the primary pool:</span></span></p>
<ul>
<li><p><span data-ttu-id="9b292-192"><strong>CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="9b292-192"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="9b292-193"><strong>CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="9b292-193"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="9b292-194"><strong>CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="9b292-194"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="9b292-195"><strong>CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="9b292-195"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="9b292-196"><strong>Get-CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="9b292-196"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="9b292-197">將測試呼叫放到已匯入到主要池的回應群組，並確認正確處理該通話。</span><span class="sxs-lookup"><span data-stu-id="9b292-197">Place a test call to a response group that was imported back to the primary pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="9b292-198">您也可以在備份池中執行<strong>Export CsRgsConfiguration</strong> Cmdlet 與– RemoveExportedConfiguration 參數，將主要池所擁有的回應群組從備份池中移除。</span><span class="sxs-lookup"><span data-stu-id="9b292-198">Optionally, run the <strong>Export-CsRgsConfiguration</strong> cmdlet on the backup pool with the –RemoveExportedConfiguration parameter to remove the response groups owned by the primary pool from the backup pool.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9b292-199">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="9b292-199">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="9b292-200">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="9b292-200">CsResponseGroupAdministrator</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

