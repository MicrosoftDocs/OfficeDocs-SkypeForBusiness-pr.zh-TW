---
title: Lync Server 2013 集區失敗期間的回應群組經驗
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response group experience during pool failure
ms:assetid: 4e00fb38-64b1-4fd9-903d-7639177bc303
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204886(v=OCS.15)
ms:contentKeyID: 48184116
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad00afac363642106019269e86111f61eaca504e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723603"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="0222e-102">Lync Server 2013 中集區失敗期間的回應群組經驗</span><span class="sxs-lookup"><span data-stu-id="0222e-102">Response group experience in Lync Server 2013 during pool failure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0222e-103">_**主題上次修改日期：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="0222e-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="0222e-104">本節將詳細說明回應群組活動如何在下列階段受到影響：</span><span class="sxs-lookup"><span data-stu-id="0222e-104">This section describes in detail how response group activity is affected in the following stages:</span></span>

  - <span data-ttu-id="0222e-105">在主要的池中發生停機，但尚未啟動容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="0222e-105">An outage occurs in the primary pool, but failover is not yet initiated.</span></span>

  - <span data-ttu-id="0222e-106">服務已容錯移轉至備份池。</span><span class="sxs-lookup"><span data-stu-id="0222e-106">Service is failed over to the backup pool.</span></span>

  - <span data-ttu-id="0222e-107">服務傳回主要池失敗。</span><span class="sxs-lookup"><span data-stu-id="0222e-107">Service is failed back to the primary pool.</span></span>

<div>

## <a name="user-experience-when-outage-occurs"></a><span data-ttu-id="0222e-108">發生停機時的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="0222e-108">User Experience When Outage Occurs</span></span>

<span data-ttu-id="0222e-109">當池或網站發生停機，但系統管理員尚未啟動容錯移轉時，系統會處理回應群組活動，如下表所述。</span><span class="sxs-lookup"><span data-stu-id="0222e-109">When a pool or site outage occurs, but the administrator has not yet initiated failover, response group activity is handled as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0222e-110">在災害復原期間，視主要池回應群組是否已匯入到備份池中而定，呼叫的行為會有所不同。</span><span class="sxs-lookup"><span data-stu-id="0222e-110">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="0222e-111">在下表中，已匯入的回應群組的參照代表在災害復原模式中，主要的池回應群組已匯入到備份池中。</span><span class="sxs-lookup"><span data-stu-id="0222e-111">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="outage-occurs"></a><span data-ttu-id="0222e-112">發生中斷</span><span class="sxs-lookup"><span data-stu-id="0222e-112">Outage Occurs</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0222e-113">撥號類型或使用者動作</span><span class="sxs-lookup"><span data-stu-id="0222e-113">Type of call or user action</span></span></th>
<th><span data-ttu-id="0222e-114">在中斷期間</span><span class="sxs-lookup"><span data-stu-id="0222e-114">During outage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0222e-115">連線至代理程式的通話</span><span class="sxs-lookup"><span data-stu-id="0222e-115">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="0222e-116">定期通話仍保持連線。</span><span class="sxs-lookup"><span data-stu-id="0222e-116">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="0222e-117">匿名呼叫已中斷連線。</span><span class="sxs-lookup"><span data-stu-id="0222e-117">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0222e-118">尚未連線至代理程式的 [進行中] 通話</span><span class="sxs-lookup"><span data-stu-id="0222e-118">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="0222e-119">通話中斷連線。</span><span class="sxs-lookup"><span data-stu-id="0222e-119">Calls are disconnected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0222e-120">新的通話</span><span class="sxs-lookup"><span data-stu-id="0222e-120">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="0222e-121">通話中斷連線。</span><span class="sxs-lookup"><span data-stu-id="0222e-121">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="0222e-122">如果已匯入回應群組，則呼叫會連線至 [備份] 池，但主機駐留在主要池中的代理無法到達。</span><span class="sxs-lookup"><span data-stu-id="0222e-122">If response groups were imported, calls connect to backup pool, but agents homed in primary pool are unreachable.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0222e-123">代表回應群組的代理程式通話</span><span class="sxs-lookup"><span data-stu-id="0222e-123">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="0222e-124">在此階段停用功能。</span><span class="sxs-lookup"><span data-stu-id="0222e-124">Feature is disabled during this stage.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0222e-125">[代理程式登入] 和 [代理程式資訊]</span><span class="sxs-lookup"><span data-stu-id="0222e-125">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="0222e-126">主要池擁有的代理群組可以在代理程式主控台上查看，但代理程式無法登入。</span><span class="sxs-lookup"><span data-stu-id="0222e-126">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="0222e-127">備份池所擁有的代理群組可以在代理程式主控台上查看，而且代理程式可以登入。</span><span class="sxs-lookup"><span data-stu-id="0222e-127">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="0222e-128">[匯入的代理程式群組] 不會顯示在代理程式主控台上。</span><span class="sxs-lookup"><span data-stu-id="0222e-128">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0222e-129">回應群組設定</span><span class="sxs-lookup"><span data-stu-id="0222e-129">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="0222e-130">根據主要池後端資料庫的可用性，您可以查看主要池所擁有的回應群組，但不能加以修改。</span><span class="sxs-lookup"><span data-stu-id="0222e-130">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="0222e-131">備份池所擁有的回應群組可以查看及修改。</span><span class="sxs-lookup"><span data-stu-id="0222e-131">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="0222e-132">無法透過 Lync Server [控制台] 或 [回應群組設定] 工具來查看匯入的回應群組，但可以使用 Lync Server 管理命令介面 Cmdlet 進行設定。</span><span class="sxs-lookup"><span data-stu-id="0222e-132">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="0222e-133">容錯移轉期間的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="0222e-133">User Experience During Failover</span></span>

<span data-ttu-id="0222e-134">當系統管理員將容錯移轉喚醒至備份池時，會在容錯移轉期間和之後處理回應群組活動，如下表所述。</span><span class="sxs-lookup"><span data-stu-id="0222e-134">When an administrator invokes failover to a backup pool, response group activity is handled during and after the failover as described in the following table.</span></span> <span data-ttu-id="0222e-135">第一欄會說明可能發生的活動類型。</span><span class="sxs-lookup"><span data-stu-id="0222e-135">The first column describes the type of activity that might be taking place.</span></span> <span data-ttu-id="0222e-136">中間欄會說明如何在短時間內處理每個活動，以進行容錯移轉至備份池。</span><span class="sxs-lookup"><span data-stu-id="0222e-136">The middle column describes how each activity is handled during the brief time that it takes to fail over to the backup pool.</span></span> <span data-ttu-id="0222e-137">最後一欄說明在容錯移轉程式完成後，以及針對主要池進行備份池之後，該活動在該期間的處理方式。</span><span class="sxs-lookup"><span data-stu-id="0222e-137">The last column describes how the activity is handled for the duration, after the failover process is complete and the backup pool is standing in for the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0222e-138">在災害復原期間，視主要池回應群組是否已匯入到備份池中而定，呼叫的行為會有所不同。</span><span class="sxs-lookup"><span data-stu-id="0222e-138">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="0222e-139">在下表中，已匯入的回應群組的參照代表在災害復原模式中，主要的池回應群組已匯入到備份池中。</span><span class="sxs-lookup"><span data-stu-id="0222e-139">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="failover-is-initiated"></a><span data-ttu-id="0222e-140">已啟動容錯移轉</span><span class="sxs-lookup"><span data-stu-id="0222e-140">Failover Is Initiated</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0222e-141">撥號類型或使用者動作</span><span class="sxs-lookup"><span data-stu-id="0222e-141">Type of call or user action</span></span></th>
<th><span data-ttu-id="0222e-142">在容錯移轉期間</span><span class="sxs-lookup"><span data-stu-id="0222e-142">During Failover</span></span></th>
<th><span data-ttu-id="0222e-143">容錯移轉完成後</span><span class="sxs-lookup"><span data-stu-id="0222e-143">After Failover Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0222e-144">連線至代理程式的通話</span><span class="sxs-lookup"><span data-stu-id="0222e-144">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="0222e-145">定期通話仍保持連線。</span><span class="sxs-lookup"><span data-stu-id="0222e-145">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="0222e-146">匿名呼叫已中斷連線。</span><span class="sxs-lookup"><span data-stu-id="0222e-146">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="0222e-147">定期通話仍保持連線。</span><span class="sxs-lookup"><span data-stu-id="0222e-147">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="0222e-148">若是已匯入的回應群組，已到達備份池的匿名呼叫仍會保持連線。</span><span class="sxs-lookup"><span data-stu-id="0222e-148">For imported response groups, anonymous calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0222e-149">尚未連線至代理程式的 [進行中] 通話</span><span class="sxs-lookup"><span data-stu-id="0222e-149">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="0222e-150">通話中斷連線。</span><span class="sxs-lookup"><span data-stu-id="0222e-150">Calls are disconnected.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="0222e-151">如果無法匯入回應群組，就不會有任何通話處於此狀態。</span><span class="sxs-lookup"><span data-stu-id="0222e-151">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="0222e-152">若是已匯入的回應群組，已到達備份池的通話仍會保持連線。</span><span class="sxs-lookup"><span data-stu-id="0222e-152">For imported response groups, calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0222e-153">新的通話</span><span class="sxs-lookup"><span data-stu-id="0222e-153">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="0222e-154">通話中斷連線。</span><span class="sxs-lookup"><span data-stu-id="0222e-154">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="0222e-155">針對匯入的回應群組，呼叫會連線至備份池，但無法取得駐留在主要池中的代理程式。</span><span class="sxs-lookup"><span data-stu-id="0222e-155">For imported response groups, calls connect to the backup pool, but agents homed in the primary pool are unreachable.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="0222e-156">如果無法匯入回應群組，通話會中斷連線。</span><span class="sxs-lookup"><span data-stu-id="0222e-156">If response groups were not imported, calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="0222e-157">在匯入的回應群組中，呼叫會連線至 [備份] 池。</span><span class="sxs-lookup"><span data-stu-id="0222e-157">For imported response groups, calls connect to the backup pool.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0222e-158">代表回應群組的代理程式通話</span><span class="sxs-lookup"><span data-stu-id="0222e-158">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="0222e-159">在此階段停用功能</span><span class="sxs-lookup"><span data-stu-id="0222e-159">Feature is disabled during this stage</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="0222e-160">如果無法匯入回應群組，通話就會失敗。</span><span class="sxs-lookup"><span data-stu-id="0222e-160">If response groups were not imported, calls fail.</span></span></p></li>
<li><p><span data-ttu-id="0222e-161">如果是匯入的回應群組，通話就會成功。</span><span class="sxs-lookup"><span data-stu-id="0222e-161">For imported response groups, calls succeed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0222e-162">[代理程式登入] 和 [代理程式資訊]</span><span class="sxs-lookup"><span data-stu-id="0222e-162">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="0222e-163">主要池擁有的代理群組可以在代理程式主控台上查看，但代理程式無法登入。</span><span class="sxs-lookup"><span data-stu-id="0222e-163">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="0222e-164">備份池所擁有的代理群組可以在代理程式主控台上查看，而且代理程式可以登入。</span><span class="sxs-lookup"><span data-stu-id="0222e-164">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="0222e-165">匯入的代理程式群組會顯示在代理程式主控台上，且代理程式可以登入。</span><span class="sxs-lookup"><span data-stu-id="0222e-165">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="0222e-166">主要池擁有的代理群組可以在代理程式主控台上查看，但代理程式無法登入。</span><span class="sxs-lookup"><span data-stu-id="0222e-166">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="0222e-167">備份池所擁有的代理群組可以在代理程式主控台上查看，而且代理程式可以登入。</span><span class="sxs-lookup"><span data-stu-id="0222e-167">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="0222e-168">匯入的代理程式群組會顯示在代理程式主控台上，且代理程式可以登入。</span><span class="sxs-lookup"><span data-stu-id="0222e-168">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0222e-169">回應群組設定</span><span class="sxs-lookup"><span data-stu-id="0222e-169">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="0222e-170">根據主要池後端資料庫的可用性，您可以查看主要池所擁有的回應群組，但不能加以修改。</span><span class="sxs-lookup"><span data-stu-id="0222e-170">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="0222e-171">備份池所擁有的回應群組可以查看及修改。</span><span class="sxs-lookup"><span data-stu-id="0222e-171">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="0222e-172">無法透過 Lync Server [控制台] 或 [回應群組設定] 工具來查看匯入的回應群組，但可以使用 Lync Server 管理命令介面 Cmdlet 進行設定。</span><span class="sxs-lookup"><span data-stu-id="0222e-172">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="0222e-173">根據後端資料庫的可用性，您可以查看主要池所擁有的回應群組，但不能加以修改。</span><span class="sxs-lookup"><span data-stu-id="0222e-173">Response groups owned by the primary pool can be viewed, depending on the availability of the back end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="0222e-174">備份池所擁有的回應群組可以查看及修改。</span><span class="sxs-lookup"><span data-stu-id="0222e-174">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="0222e-175">無法透過 Lync Server [控制台] 或 [回應群組設定] 工具來查看匯入的回應群組，但可以使用 Lync Server 管理命令介面 Cmdlet 進行設定。</span><span class="sxs-lookup"><span data-stu-id="0222e-175">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="0222e-176">在回切期間的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="0222e-176">User Experience During Failback</span></span>

<span data-ttu-id="0222e-177">當管理員將回切移至主要池時，系統會在回切期間和之後處理回應群組活動，如下表所述。</span><span class="sxs-lookup"><span data-stu-id="0222e-177">When an administrator invokes failback to the primary pool, response group activity is handled during and after the failback as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0222e-178">在災害復原期間，視主要池回應群組是否已匯入到備份池中而定，呼叫的行為會有所不同。</span><span class="sxs-lookup"><span data-stu-id="0222e-178">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="0222e-179">在下表中，已匯入的回應群組的參照代表在災害復原模式中，主要的池回應群組已匯入到備份池中。</span><span class="sxs-lookup"><span data-stu-id="0222e-179">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="call-handling-in-failback"></a><span data-ttu-id="0222e-180">回切中的呼叫處理</span><span class="sxs-lookup"><span data-stu-id="0222e-180">Call Handling in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0222e-181">撥號類型或使用者動作</span><span class="sxs-lookup"><span data-stu-id="0222e-181">Type of call or user action</span></span></th>
<th><span data-ttu-id="0222e-182">在回切期間</span><span class="sxs-lookup"><span data-stu-id="0222e-182">During Failback</span></span></th>
<th><span data-ttu-id="0222e-183">在回切完成後</span><span class="sxs-lookup"><span data-stu-id="0222e-183">After Failback Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0222e-184">連線至代理程式的通話</span><span class="sxs-lookup"><span data-stu-id="0222e-184">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="0222e-185">定期通話仍保持連線。</span><span class="sxs-lookup"><span data-stu-id="0222e-185">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="0222e-186">如果無法匯入回應群組，就不會有任何匿名通話處於此狀態。</span><span class="sxs-lookup"><span data-stu-id="0222e-186">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="0222e-187">在匯入的回應群組中，匿名通話仍保持連線。</span><span class="sxs-lookup"><span data-stu-id="0222e-187">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="0222e-188">定期通話仍保持連線。</span><span class="sxs-lookup"><span data-stu-id="0222e-188">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="0222e-189">如果無法匯入回應群組，就不會有任何匿名通話處於此狀態。</span><span class="sxs-lookup"><span data-stu-id="0222e-189">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="0222e-190">在匯入的回應群組中，匿名通話仍保持連線。</span><span class="sxs-lookup"><span data-stu-id="0222e-190">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0222e-191">尚未連線至代理程式的 [進行中] 通話</span><span class="sxs-lookup"><span data-stu-id="0222e-191">In progress calls not yet connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="0222e-192">如果無法匯入回應群組，就不會有任何通話處於此狀態。</span><span class="sxs-lookup"><span data-stu-id="0222e-192">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="0222e-193">在匯入的回應群組中，通話會中斷連線。</span><span class="sxs-lookup"><span data-stu-id="0222e-193">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="0222e-194">如果無法匯入回應群組，就不會有任何通話處於此狀態。</span><span class="sxs-lookup"><span data-stu-id="0222e-194">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="0222e-195">在匯入的回應群組中，通話會中斷連線。</span><span class="sxs-lookup"><span data-stu-id="0222e-195">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0222e-196">新的通話</span><span class="sxs-lookup"><span data-stu-id="0222e-196">New calls</span></span></p></td>
<td><p><span data-ttu-id="0222e-197">呼叫會連接到主要池，但駐留在主要池中的代理程式無法到達。</span><span class="sxs-lookup"><span data-stu-id="0222e-197">Calls connect to the primary pool, but agents homed in the primary pool are unreachable.</span></span></p></td>
<td><p><span data-ttu-id="0222e-198">呼叫會連接到主要池。</span><span class="sxs-lookup"><span data-stu-id="0222e-198">Calls connect to the primary pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0222e-199">代表回應群組的代理程式通話</span><span class="sxs-lookup"><span data-stu-id="0222e-199">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="0222e-200">在此階段停用功能。</span><span class="sxs-lookup"><span data-stu-id="0222e-200">Feature is disabled during this stage.</span></span></p></td>
<td><p><span data-ttu-id="0222e-201">通話成功。</span><span class="sxs-lookup"><span data-stu-id="0222e-201">Calls succeed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0222e-202">[代理程式登入] 和 [代理程式資訊]</span><span class="sxs-lookup"><span data-stu-id="0222e-202">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="0222e-203">主要池擁有的代理群組可以在代理程式主控台上查看，但代理程式無法登入。</span><span class="sxs-lookup"><span data-stu-id="0222e-203">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="0222e-204">備份池所擁有的代理群組可以在代理程式主控台上查看，而且代理程式可以登入。</span><span class="sxs-lookup"><span data-stu-id="0222e-204">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="0222e-205">匯入的代理程式群組會顯示在代理程式主控台上，且代理程式可以登入。</span><span class="sxs-lookup"><span data-stu-id="0222e-205">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="0222e-206">主要池所擁有的代理群組可以在代理程式主控台上查看，而且代理程式可以登入。</span><span class="sxs-lookup"><span data-stu-id="0222e-206">Agent groups owned by the primary pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="0222e-207">備份池所擁有的代理群組可以在代理程式主控台上查看，而且代理程式可以登入。</span><span class="sxs-lookup"><span data-stu-id="0222e-207">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="0222e-208">[匯入的代理程式群組] 不會顯示在代理程式主控台上。</span><span class="sxs-lookup"><span data-stu-id="0222e-208">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0222e-209">回應群組設定</span><span class="sxs-lookup"><span data-stu-id="0222e-209">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="0222e-210">根據主要池後端資料庫的可用性，您可以查看主要池所擁有的回應群組，但不能加以修改。</span><span class="sxs-lookup"><span data-stu-id="0222e-210">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="0222e-211">備份池所擁有的回應群組可以查看及修改。</span><span class="sxs-lookup"><span data-stu-id="0222e-211">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="0222e-212">無法透過 Lync Server [控制台] 或 [回應群組設定] 工具來查看匯入的回應群組，但可以使用 Lync Server 管理命令介面 Cmdlet 進行設定。</span><span class="sxs-lookup"><span data-stu-id="0222e-212">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="0222e-213">主要池擁有的回應群組可以查看和修改。</span><span class="sxs-lookup"><span data-stu-id="0222e-213">Response groups owned by the primary pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="0222e-214">備份池所擁有的回應群組可以查看及修改。</span><span class="sxs-lookup"><span data-stu-id="0222e-214">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="0222e-215">無法透過 Lync Server [控制台] 或 [回應群組設定] 工具來查看匯入的回應群組，但可以使用 Lync Server 管理命令介面 Cmdlet 進行設定。</span><span class="sxs-lookup"><span data-stu-id="0222e-215">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

