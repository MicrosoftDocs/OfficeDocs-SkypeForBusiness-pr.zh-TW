---
title: Lync Server 2013：規劃回應群組災難修復
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for response group disaster recovery
ms:assetid: 14e0f5dc-77cd-42cd-a9c9-4d0da38fb1cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204699(v=OCS.15)
ms:contentKeyID: 48183482
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cc238665ecb0222ded43e438e9f9370b561b85d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530570"
---
# <a name="planning-for-response-group-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="1ea4b-102">在 Lync Server 2013 中規劃回應群組災難修復</span><span class="sxs-lookup"><span data-stu-id="1ea4b-102">Planning for response group disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ea4b-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1ea4b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1ea4b-104">本節說明為災害復原準備回應群組的一些方法，並提供災害復原程序的概觀。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-104">This section describes some ways to prepare response groups for disaster recovery and provides an overview of the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-response-group-disaster-recovery"></a><span data-ttu-id="1ea4b-105">準備回應群組災難修復</span><span class="sxs-lookup"><span data-stu-id="1ea4b-105">Preparing for Response Group Disaster Recovery</span></span>

<span data-ttu-id="1ea4b-106">當您準備及執行災害復原程序時，請記得下列事項。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-106">Keep the following in mind when you prepare for and carry out disaster recovery procedures.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1ea4b-107">在共存環境中，本檔中所述的嚴重損壞復原程式僅支援 Lync Server 2013 回應群組。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-107">In a coexistence environment, only the Lync Server 2013 response groups are supported for the disaster recovery procedures described in this document.</span></span>



</div>

  - <span data-ttu-id="1ea4b-108">在進行容量規劃時，請規劃災害復原。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-108">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="1ea4b-109">針對災害復原容量，一對集區中的每個集區都應該要能夠處理這兩個集區中所有回應群組的工作量。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-109">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of all the response groups in both pools.</span></span> <span data-ttu-id="1ea4b-110">如需有關回應群組容量規劃的詳細資訊，請參閱 [Lync Server 2013 中的「回應」群組的容量規劃](lync-server-2013-capacity-planning-for-response-group.md)。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-110">For details about Response Group capacity planning, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).</span></span>

  - <span data-ttu-id="1ea4b-111">在您部署回應群組應用程式的所有前端集區中，請定期備份所有的回應群組設定，並使用本檔中所述的匯出程式。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-111">Take regular backup copies of all the response group configurations in all the Front End pools where you deployed the Response Group application by using the export procedure described in this document.</span></span> <span data-ttu-id="1ea4b-112">如需詳細資訊，請參閱 [Lync Server 2013 中的回應群組嚴重損壞修復程式](lync-server-2013-response-group-disaster-recovery-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-112">For details, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span> <span data-ttu-id="1ea4b-113">將備份複本保存在安全的地方。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-113">Keep the backup copies in a safe location.</span></span>

  - <span data-ttu-id="1ea4b-114">針對回應群組應用程式，保留您使用的所有原始音訊檔的個別備份副本，包括任何錄製和暫止的檔。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-114">Keep a separate backup copy of all the original audio files you used for the Response Group application, including any recordings and music-on-hold files.</span></span> <span data-ttu-id="1ea4b-115">將備份檔案保存在安全的地方。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-115">Keep the backup files in a safe location.</span></span>

  - <span data-ttu-id="1ea4b-116">對於 Lync Server 2013 的嚴重損壞修復，所有的回應群組設定都必須在您的部署中具有唯一的名稱。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-116">For Lync Server 2013 disaster recovery, all Response Group settings must have unique names across your deployment.</span></span> <span data-ttu-id="1ea4b-117">此需求適用於工作流程、佇列、代理群組、假日集和營業時間。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-117">This requirement applies to workflows, queues, agent groups, holiday sets, and hours of business.</span></span> <span data-ttu-id="1ea4b-118">您應該在主要和備份集區仍作用時，以及在您需要起始任何容錯移轉程序之前，確認是否符合此需求。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-118">You should verify that this requirement is met when the primary and backup pools are still active, and before you need to initiate any failover procedure.</span></span> <span data-ttu-id="1ea4b-119">如果在將回應群組資料匯入備份集區時，發生名稱衝突，則匯入失敗。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-119">If you encounter name conflicts while importing response group data to the backup pool, the import fails.</span></span> <span data-ttu-id="1ea4b-120">若要完成匯入及容錯移轉程序，您必須將備份集區中的回應群組物件重新命名，以解決名稱衝突的問題，或是使用 **Import-CsRgsConfiguration** Cmdlet 搭配 –ResolveNameConflicts 參數來自動解決衝突，其會在回應群組物件後面加上唯一的識別號碼。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-120">To complete the import and failover procedure, you need to resolve the name conflicts by renaming the response group object in the backup pool or by using the **Import-CsRgsConfiguration** cmdlet with the –ResolveNameConflicts parameter to automatically resolve the conflict by appending a unique identifying number to the response group object.</span></span>

  - <span data-ttu-id="1ea4b-p105">一般而言，我們會建議您執行每日備份，但是如果您有大量變更，也許會想要排定更多次的備份。您在發生災害會遺失的資訊量，取決於備份的頻率，以及變更的頻率和數量。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-p105">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups. The amount of information you can lose in the event of a disaster depends on the frequency of your backups, as well as the frequency and volume of changes.</span></span>

  - <span data-ttu-id="1ea4b-123">您可以在發生災害或容錯移轉作業之前，就將回應群組匯入備份集區。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-123">It is possible to import response groups to a backup pool before a disaster or failover operation occurs.</span></span> <span data-ttu-id="1ea4b-124">以預先匯入回應群組可減少停機時間，因為在將來電路由傳送至備份組區之後，就可以在備份組區中還原 Lync Server 回應群組服務。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-124">Importing response groups in advance reduces downtime, because the Lync Server Response Group service can be restored in the backup pool as soon as calls are routed to the backup pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1ea4b-125">在容錯移轉完成之前，回應群組應用程式無法到達任何停用的集區中的代理程式。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-125">The Response Group application cannot reach any agents homed in an inactive pool until failover is complete.</span></span> <span data-ttu-id="1ea4b-126">在這段時間內，回應群組應用程式會處理呼叫，就像這些代理程式皆無法使用。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-126">During this time, the Response Group application processes calls as if those agents are unavailable.</span></span>

    
    </div>

</div>

<div>

## <a name="response-group-disaster-recovery-process"></a><span data-ttu-id="1ea4b-127">回應群組災害復原程序</span><span class="sxs-lookup"><span data-stu-id="1ea4b-127">Response Group Disaster Recovery Process</span></span>

<span data-ttu-id="1ea4b-128">在發生災害時，您可以使用下列任一復原方式來復原回應群組：</span><span class="sxs-lookup"><span data-stu-id="1ea4b-128">In the event of a disaster, you can recover response groups by using either of the following recovery approaches:</span></span>

  - <span data-ttu-id="1ea4b-129">容錯移轉至備份集區，然後容錯回復至原始集區。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-129">Fail over to a backup pool and then fail back to the original pool.</span></span>

  - <span data-ttu-id="1ea4b-130">容錯移轉至備份集區，以不同的完整網域名稱 (FQDN) 建立新集區，然後將回應群組匯入新集區。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-130">Fail over to a backup pool, create a new pool with a different fully qualified domain name (FQDN), and then import the response groups to the new pool.</span></span>

<span data-ttu-id="1ea4b-p108">在災害復原的容錯移轉階段期間，回應群組位在多個集區中：主要集區 (無法使用) 以及備份集區中。兩個集區中的回應群組都有相同的名稱和相同的擁有者 (主要集區)，但其父系不同。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-p108">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool. The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span>

<span data-ttu-id="1ea4b-133">當您建立不同 FQDN 的新集區來進行復原時，需要在匯入回應群組時，將新集區指派為該回應群組的擁有者。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-133">When you recover by creating a new pool with a different FQDN, you need to assign the new pool as the owner of the response groups when you import them.</span></span> <span data-ttu-id="1ea4b-134">回應群組的擁有權會一直跟隨著原始集區，除非 (或直到) 您使用 –OverwriteOwner 參數搭配 **Import-CsRgsConfiguration** Cmdlet 來明確地重新指派擁有權。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-134">Ownership of response groups remains with the original pool unless or until you explicitly reassign ownership by using the –OverwriteOwner parameter with the **Import-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1ea4b-135">您也必須使用– OverwriteOwner 參數，如果您在復原 (期間重建集區，則回應群組資料庫會是空的) （不論您是否使用相同的 FQDN）。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-135">You also need to use the –OverwriteOwner parameter if you rebuilt the pool during the recovery (that is, the Response Group database is empty), whether or not you use the same FQDN.</span></span> <span data-ttu-id="1ea4b-136">如果您沒有重新建立集區，則不需使用 –OverwriteOwner 參數，但是每當您將回應群組匯入回主要集區時，都可以使用此參數。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-136">You do not need to use the –OverwriteOwner parameter if you did not rebuild the pool, but it is permissible to use this parameter whenever you import response groups back to the primary pool.</span></span>



</div>

<span data-ttu-id="1ea4b-137">您只能為每個集區定義一組應用層級回應群組設定設定。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-137">You can define only one set of application-level Response Group configuration settings per pool.</span></span> <span data-ttu-id="1ea4b-138">這些設定包括預設等候音樂組態、預設等候音樂音訊檔案、代理回電寬限期，以及呼叫內容組態。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-138">These settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="1ea4b-139">若要檢視這些組態設定，請執行 **Get-CsRgsConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-139">To view these configuration settings, run the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="1ea4b-140">如需 **Get-CsRgsConfiguration** Cmdlet 的詳細資訊，請參閱 [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-140">For details about the **Get-CsRgsConfiguration** cmdlet, see [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).</span></span>

<span data-ttu-id="1ea4b-141">您可以使用 **Import-CsRgsConfiguration** Cmdlet 搭配 –ReplaceExistingSettings 參數，將這些應用程式層級設定從一個集區轉移到另一個集區，但是這麼做會覆寫目的集區中的設定。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-141">You can transfer these application-level settings from one pool to another by using the **Import-CsRgsConfiguration** cmdlet with the –ReplaceExistingSettings parameter, but doing so overrides the settings in the destination pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1ea4b-p112">此有關將設定轉移到另一個集區的限制，僅適用於應用程式層級設定和預設等候音樂音訊檔案，不適用於代理群組、佇列、工作流程、營業時間和假日集。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-p112">This constraint about transferring settings to another pool is true only for the application-level settings and the default music-on-hold audio file. It does not apply to agent groups, queues, workflows, business hours, and holiday sets.</span></span>



</div>

<span data-ttu-id="1ea4b-p113">如果您不想在災害期間取代備份集區中的應用程式層級設定，而且主要集區無法復原，主要集區的應用程式層級設定將會遺失。如果您需要在復原期間建立新集區來取代主要集區，無論是使用相同的 FQDN 或不同的 FQDN，您都無法復原原始應用程式層級設定。在此情況下，您需要設定使用這些設定的新集區，並包含等候音樂音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-p113">If you don't want to replace the application-level settings in the backup pool during a disaster and the primary pool can't be recovered, the application-level settings from the primary pool will be lost. If you need to create a new pool to replace the primary pool during recovery, either with the same FQDN or with a different FQDN, you can't recover the original application-level settings. In this case, you need to configure the new pool with these settings and include the music-on-hold audio file.</span></span>

<span data-ttu-id="1ea4b-147">如果您決定使用 **Import-CsRgsConfiguration** Cmdlet，在災害期間將應用程式層級設定從主要集區轉移到備份集區，您可以在復原期間將這些設定從備份集區轉移到新集區，方法就和您將其從主要集區轉移到備份集區一樣。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-147">If you decide to use the **Import-CsRgsConfiguration** cmdlet to transfer application-level settings from the primary pool to the backup pool during a disaster, you can then transfer the settings from the backup pool to the new pool during recovery in the same way that you transferred them from the primary pool to the backup pool.</span></span>

<span data-ttu-id="1ea4b-148">下表是有關復原回應群組的步驟概觀。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-148">The following table is an overview of the steps involved in recovering response groups.</span></span>

<span data-ttu-id="1ea4b-149">如需執行這些步驟的詳細資訊，請參閱 [Lync Server 2013 中的回應群組嚴重損壞修復程式](lync-server-2013-response-group-disaster-recovery-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-149">For details about performing these steps, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span>

### <a name="response-group-disaster-recovery-steps"></a><span data-ttu-id="1ea4b-150">回應群組災害復原步驟</span><span class="sxs-lookup"><span data-stu-id="1ea4b-150">Response Group Disaster Recovery Steps</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ea4b-151">階段</span><span class="sxs-lookup"><span data-stu-id="1ea4b-151">Phase</span></span></th>
<th><span data-ttu-id="1ea4b-152">步驟</span><span class="sxs-lookup"><span data-stu-id="1ea4b-152">Steps</span></span></th>
<th><span data-ttu-id="1ea4b-153">所需群組和角色</span><span class="sxs-lookup"><span data-stu-id="1ea4b-153">Required groups and roles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ea4b-154">系統中斷之前</span><span class="sxs-lookup"><span data-stu-id="1ea4b-154">Before outage</span></span></p></td>
<td><p><span data-ttu-id="1ea4b-155">請定期執行 <strong>Export-CsRgsConfiguration</strong> Cmdlet，以在部署回應群組應用程式的所有前端集區中，建立所有回應群組設定的備份。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-155">On a routine basis, run the <strong>Export-CsRgsConfiguration</strong> cmdlet to create backups of all Response Group configurations in all Front End pools where Response Group application is deployed.</span></span></p></td>
<td><p><span data-ttu-id="1ea4b-156">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="1ea4b-156">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="1ea4b-157">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="1ea4b-157">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ea4b-158">系統中斷期間</span><span class="sxs-lookup"><span data-stu-id="1ea4b-158">During outage</span></span></p></td>
<td><p><span data-ttu-id="1ea4b-159">執行 <strong>Import-CsRgsConfiguration</strong> Cmdlet，將備份的 Lync Server 回應群組服務設定從主要集區匯入至備份組區。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-159">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the backed up Lync Server Response Group service configuration from the primary pool to the backup pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="1ea4b-160">如果您想要以主要集區的設定取代備份組區中的應用層回應群組設定，請使用–ReplaceExistingSettings 參數。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-160">Use the –ReplaceExistingSettings parameter if you want to replace application-level Response Group settings in the backup pool with the settings from the primary pool.</span></span> <span data-ttu-id="1ea4b-161">如果您不將應用程式層級設定從主要集區轉移到備份集區，而且主要集區無法復原，您將會遺失主要集區的設定。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-161">If you do not transfer the application-level settings from the primary pool to the backup pool, and the primary pool can't be recovered, you will lose the settings from the primary pool.</span></span>


</div></td>
<td><p><span data-ttu-id="1ea4b-162">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="1ea4b-162">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="1ea4b-163">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="1ea4b-163">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ea4b-164">匯入之後</span><span class="sxs-lookup"><span data-stu-id="1ea4b-164">After importing</span></span></p></td>
<td><p><span data-ttu-id="1ea4b-165">使用–ShowAll 參數 (執行回應群組指令程式，以顯示所有回應群組) 或「–擁有者」參數 (只顯示匯入的回應群組) ，以確認所有回應群組設定已匯入備份組區。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-165">Run Response Group cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were imported to the backup pool.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="1ea4b-166">如果您不使用 –ShowAll 參數，也不使用 –Owner 參數，您匯入備份集區的回應群組將不會列示在 Cmdlet 傳回的結果中。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-166">If you do not use either the –ShowAll parameter or the –Owner parameter, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>


</div>
<p><span data-ttu-id="1ea4b-167">執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="1ea4b-167">Run the following cmdlets:</span></span></p>
<ul>
<li><p><span data-ttu-id="1ea4b-168"><strong>Get-CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="1ea4b-168"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="1ea4b-169"><strong>Get-CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="1ea4b-169"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="1ea4b-170"><strong>Get-CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="1ea4b-170"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="1ea4b-171"><strong>Get-CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="1ea4b-171"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="1ea4b-172"><strong>Get-CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="1ea4b-172"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="1ea4b-173">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="1ea4b-173">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="1ea4b-174">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="1ea4b-174">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ea4b-175">容錯移轉之後</span><span class="sxs-lookup"><span data-stu-id="1ea4b-175">After failover</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1ea4b-176">撥打測試通話至已匯入備份集區的回應群組，確認可正確處理該通話。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-176">Place a test call to a response group that was imported to the backup pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="1ea4b-177">所有正式代理程式都必須再次登入備份集區上的正式群組。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-177">All formal agents must sign in again to their formal groups on backup pool.</span></span></p></li>
<li><p><span data-ttu-id="1ea4b-178">管理組態變更：</span><span class="sxs-lookup"><span data-stu-id="1ea4b-178">Manage configuration changes:</span></span></p>
<p><span data-ttu-id="1ea4b-179">在系統中斷期間，仍可像平常一樣修改備份集區中的回應群組 (無論是匯入備份集區或為備份集區所擁有)。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-179">Response groups in the backup pool, whether imported to the backup pool or owned by the backup pool, can be modified as usual during the outage.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="1ea4b-180">您必須使用 Lync Server 管理命令介面來管理已匯入備份組區的回應群組。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-180">You must use Lync Server Management Shell to manage the response groups that you imported to the backup pool.</span></span> <span data-ttu-id="1ea4b-181">在備份組區中時，您無法使用 Lync Server 控制台管理這些回應群組。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-181">You cannot use Lync Server Control Panel to manage these response groups while they are in the backup pool.</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="1ea4b-182">不適用</span><span class="sxs-lookup"><span data-stu-id="1ea4b-182">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ea4b-183">復原之後，容錯回復之前</span><span class="sxs-lookup"><span data-stu-id="1ea4b-183">After recovery, before failback</span></span></p></td>
<td><p><span data-ttu-id="1ea4b-184">執行 <strong>Export-CsRgsConfiguration</strong> Cmdlet，將 -Source 參數指定為備份集區，將 –Owner 參數指定為主要集區，以從備份集區匯出主要集區擁有的回應群組。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-184">Run the <strong>Export-CsRgsConfiguration</strong> cmdlet specifying the -Source parameter as the backup pool and the –Owner parameter as the primary pool to export the response groups owned by the primary pool from the backup pool.</span></span></p></td>
<td><p><span data-ttu-id="1ea4b-185">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="1ea4b-185">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="1ea4b-186">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="1ea4b-186">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ea4b-187">容錯回復之後</span><span class="sxs-lookup"><span data-stu-id="1ea4b-187">After failback</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1ea4b-188">執行 <strong>Import-CsRgsConfiguration</strong> Cmdlet，將回應群組匯入回主要集區。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-188">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the response groups back to the primary pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="1ea4b-p116">如果無法復原主要集區，而您部署新的集區來將其取代，請使用 –ReplaceExistingSettings 參數，將應用程式層級設定從備份集區轉移到新集區。如果您沒有從備份集區轉移設定，新集區將會使用預設設定。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-p116">If the primary pool can't be recovered and you deploy a new pool to replace it, use the –ReplaceExistingSettings parameter to transfer the application-level settings from the backup pool to the new pool. If you do not transfer the settings from the backup pool, the new pool will use the default settings.</span></span>


</div></li>
<li><p><span data-ttu-id="1ea4b-191">執行下列 Cmdlet 搭配 –ShowAll 參數 (顯示所有回應群組) 或 –Owner 參數 (只顯示匯入的回應群組)，以確認所有回應群組組態都已成功匯入回主要集區：</span><span class="sxs-lookup"><span data-stu-id="1ea4b-191">Run the following cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were successfully imported back to the primary pool:</span></span></p>
<ul>
<li><p><span data-ttu-id="1ea4b-192"><strong>Get-CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="1ea4b-192"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="1ea4b-193"><strong>Get-CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="1ea4b-193"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="1ea4b-194"><strong>Get-CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="1ea4b-194"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="1ea4b-195"><strong>Get-CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="1ea4b-195"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="1ea4b-196"><strong>Get-CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="1ea4b-196"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="1ea4b-197">撥打測試通話至已匯入回主要集區的回應群組，確認可正確處理該通話。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-197">Place a test call to a response group that was imported back to the primary pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="1ea4b-198">(選用) 在備份集區上執行 <strong>Export-CsRgsConfiguration</strong> Cmdlet 搭配 –RemoveExportedConfiguration 參數，將主要集區擁有的回應群組從備份集區移除。</span><span class="sxs-lookup"><span data-stu-id="1ea4b-198">Optionally, run the <strong>Export-CsRgsConfiguration</strong> cmdlet on the backup pool with the –RemoveExportedConfiguration parameter to remove the response groups owned by the primary pool from the backup pool.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="1ea4b-199">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="1ea4b-199">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="1ea4b-200">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="1ea4b-200">CsResponseGroupAdministrator</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

