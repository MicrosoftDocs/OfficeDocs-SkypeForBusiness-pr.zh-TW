---
title: Lync Server 2013 集區失敗期間的回應群組經驗
description: Lync Server 2013 集區失敗期間的回應群組經驗。
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
ms.openlocfilehash: 7d8d5904bc6934d4c330202bafa66d6dd8a16ff5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564569"
---
# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="1e524-103">在集區失敗期間，Lync Server 2013 的回應群組經驗</span><span class="sxs-lookup"><span data-stu-id="1e524-103">Response group experience in Lync Server 2013 during pool failure</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e524-104">_**主題上次修改日期：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="1e524-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="1e524-105">本節詳細說明回應群組活動在下列階段所受到的影響：</span><span class="sxs-lookup"><span data-stu-id="1e524-105">This section describes in detail how response group activity is affected in the following stages:</span></span>

  - <span data-ttu-id="1e524-106">主要集區中發生中斷，但尚未起始容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="1e524-106">An outage occurs in the primary pool, but failover is not yet initiated.</span></span>

  - <span data-ttu-id="1e524-107">服務已容錯移轉至備用集區。</span><span class="sxs-lookup"><span data-stu-id="1e524-107">Service is failed over to the backup pool.</span></span>

  - <span data-ttu-id="1e524-108">服務已容錯回復至主要集區。</span><span class="sxs-lookup"><span data-stu-id="1e524-108">Service is failed back to the primary pool.</span></span>

<div>

## <a name="user-experience-when-outage-occurs"></a><span data-ttu-id="1e524-109">發生中斷時的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="1e524-109">User Experience When Outage Occurs</span></span>

<span data-ttu-id="1e524-110">當集區或網站發生中斷，但系統管理員尚未起始容錯移轉時，回應群組活動的處理方式如下表所述。</span><span class="sxs-lookup"><span data-stu-id="1e524-110">When a pool or site outage occurs, but the administrator has not yet initiated failover, response group activity is handled as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1e524-p101">在災害復原期間，通話行為會視主要集區回應群組是否已在復原期間匯入備份集區而有所不同。在下表中，匯入的回應群組參考代表主要集區回應群組已在災害復原模式期間匯入備份集區。</span><span class="sxs-lookup"><span data-stu-id="1e524-p101">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="outage-occurs"></a><span data-ttu-id="1e524-113">發生中斷</span><span class="sxs-lookup"><span data-stu-id="1e524-113">Outage Occurs</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1e524-114">通話類型或使用者動作</span><span class="sxs-lookup"><span data-stu-id="1e524-114">Type of call or user action</span></span></th>
<th><span data-ttu-id="1e524-115">中斷期間</span><span class="sxs-lookup"><span data-stu-id="1e524-115">During outage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1e524-116">連線至代理人的通話</span><span class="sxs-lookup"><span data-stu-id="1e524-116">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1e524-117">一般通話保持連線。</span><span class="sxs-lookup"><span data-stu-id="1e524-117">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="1e524-118">匿名通話中斷連線。</span><span class="sxs-lookup"><span data-stu-id="1e524-118">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e524-119">進行中的通話尚未連線至代理</span><span class="sxs-lookup"><span data-stu-id="1e524-119">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="1e524-120">通話中斷連線。</span><span class="sxs-lookup"><span data-stu-id="1e524-120">Calls are disconnected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e524-121">新通話</span><span class="sxs-lookup"><span data-stu-id="1e524-121">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1e524-122">通話中斷連線。</span><span class="sxs-lookup"><span data-stu-id="1e524-122">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="1e524-123">如果已匯入回應群組，通話會連線至備份集區，但是無法與位於主要集區的代理人連線。</span><span class="sxs-lookup"><span data-stu-id="1e524-123">If response groups were imported, calls connect to backup pool, but agents homed in primary pool are unreachable.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e524-124">代表回應群組的代理人通話</span><span class="sxs-lookup"><span data-stu-id="1e524-124">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="1e524-125">功能在此階段停用。</span><span class="sxs-lookup"><span data-stu-id="1e524-125">Feature is disabled during this stage.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e524-126">代理人登入與代理人資訊</span><span class="sxs-lookup"><span data-stu-id="1e524-126">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1e524-127">主要集區所擁有的代理人群組可在代理人主控台上檢視，但代理人無法登入。</span><span class="sxs-lookup"><span data-stu-id="1e524-127">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="1e524-128">備份集區所擁有的代理人群組可在代理人主控台上檢視，且代理人可以登入。</span><span class="sxs-lookup"><span data-stu-id="1e524-128">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="1e524-129">匯入的代理人群組未顯示在代理人主控台上。</span><span class="sxs-lookup"><span data-stu-id="1e524-129">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e524-130">回應群組設定</span><span class="sxs-lookup"><span data-stu-id="1e524-130">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1e524-131">主要集區所擁有的回應群組可以檢視，視主要集區後端資料庫的可用性而定，但無法修改。</span><span class="sxs-lookup"><span data-stu-id="1e524-131">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="1e524-132">備份集區所擁有的回應群組可以檢視及修改。</span><span class="sxs-lookup"><span data-stu-id="1e524-132">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="1e524-133">無法使用 Lync Server 控制台或回應群組設定工具來查看已匯入的回應群組，但可使用 Lync Server 管理命令介面 Cmdlet 進行設定。</span><span class="sxs-lookup"><span data-stu-id="1e524-133">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="1e524-134">容錯移轉期間的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="1e524-134">User Experience During Failover</span></span>

<span data-ttu-id="1e524-p102">當系統管理員叫用容錯移轉至備份集區時，回應群組活動會在容錯移轉期間和之後處理，如下表所述。第一欄說明可能發生的活動類型。中間一欄說明各活動在容錯移轉至備份集區的短時間內的處理方式。最後一欄說明在容錯移轉程序完成之後以及備份集區代替主要集區時，這段期間活動的處理方式。</span><span class="sxs-lookup"><span data-stu-id="1e524-p102">When an administrator invokes failover to a backup pool, response group activity is handled during and after the failover as described in the following table. The first column describes the type of activity that might be taking place. The middle column describes how each activity is handled during the brief time that it takes to fail over to the backup pool. The last column describes how the activity is handled for the duration, after the failover process is complete and the backup pool is standing in for the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1e524-p103">在災害復原期間，通話行為會視主要集區回應群組是否已在復原期間匯入備份集區而有所不同。在下表中，匯入的回應群組參考代表主要集區回應群組已在災害復原模式期間匯入備份集區。</span><span class="sxs-lookup"><span data-stu-id="1e524-p103">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="failover-is-initiated"></a><span data-ttu-id="1e524-141">已起始容錯移轉</span><span class="sxs-lookup"><span data-stu-id="1e524-141">Failover Is Initiated</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1e524-142">通話類型或使用者動作</span><span class="sxs-lookup"><span data-stu-id="1e524-142">Type of call or user action</span></span></th>
<th><span data-ttu-id="1e524-143">容錯移轉期間</span><span class="sxs-lookup"><span data-stu-id="1e524-143">During Failover</span></span></th>
<th><span data-ttu-id="1e524-144">容錯移轉完成之後</span><span class="sxs-lookup"><span data-stu-id="1e524-144">After Failover Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1e524-145">連線至代理人的通話</span><span class="sxs-lookup"><span data-stu-id="1e524-145">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1e524-146">一般通話保持連線。</span><span class="sxs-lookup"><span data-stu-id="1e524-146">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="1e524-147">匿名通話中斷連線。</span><span class="sxs-lookup"><span data-stu-id="1e524-147">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="1e524-148">一般通話保持連線。</span><span class="sxs-lookup"><span data-stu-id="1e524-148">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="1e524-149">對於匯入的回應群組，已連至備份集區的匿名通話會保持連線。</span><span class="sxs-lookup"><span data-stu-id="1e524-149">For imported response groups, anonymous calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e524-150">進行中的通話尚未連線至代理</span><span class="sxs-lookup"><span data-stu-id="1e524-150">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="1e524-151">通話中斷連線。</span><span class="sxs-lookup"><span data-stu-id="1e524-151">Calls are disconnected.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1e524-152">如果沒有匯入回應群組，這個階段就沒有通話。</span><span class="sxs-lookup"><span data-stu-id="1e524-152">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="1e524-153">對於匯入的回應群組，已連至備份集區的通話會保持連線。</span><span class="sxs-lookup"><span data-stu-id="1e524-153">For imported response groups, calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e524-154">新通話</span><span class="sxs-lookup"><span data-stu-id="1e524-154">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1e524-155">通話中斷連線。</span><span class="sxs-lookup"><span data-stu-id="1e524-155">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="1e524-156">對於匯入的回應群組，通話會連線至備份集區，但是無法與位於主要集區的代理人連線。</span><span class="sxs-lookup"><span data-stu-id="1e524-156">For imported response groups, calls connect to the backup pool, but agents homed in the primary pool are unreachable.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="1e524-157">如果沒有匯入回應群組，通話會中斷連線。</span><span class="sxs-lookup"><span data-stu-id="1e524-157">If response groups were not imported, calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="1e524-158">對於匯入的回應群組，通話會連線至備份集區。</span><span class="sxs-lookup"><span data-stu-id="1e524-158">For imported response groups, calls connect to the backup pool.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e524-159">代表回應群組的代理人通話</span><span class="sxs-lookup"><span data-stu-id="1e524-159">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="1e524-160">功能在此階段停用</span><span class="sxs-lookup"><span data-stu-id="1e524-160">Feature is disabled during this stage</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1e524-161">如果沒有匯入回應群組，通話會失敗。</span><span class="sxs-lookup"><span data-stu-id="1e524-161">If response groups were not imported, calls fail.</span></span></p></li>
<li><p><span data-ttu-id="1e524-162">對於匯入的回應群組，通話成功。</span><span class="sxs-lookup"><span data-stu-id="1e524-162">For imported response groups, calls succeed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e524-163">代理登入與代理資訊</span><span class="sxs-lookup"><span data-stu-id="1e524-163">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1e524-164">主要集區所擁有的代理人群組可在代理人主控台上檢視，但代理人無法登入。</span><span class="sxs-lookup"><span data-stu-id="1e524-164">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="1e524-165">備份集區所擁有的代理人群組可在代理人主控台上檢視，且代理人可以登入。</span><span class="sxs-lookup"><span data-stu-id="1e524-165">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="1e524-166">匯入的代理人群組顯示在代理人主控台上，且代理人可以登入。</span><span class="sxs-lookup"><span data-stu-id="1e524-166">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="1e524-167">主要集區所擁有的代理人群組可在代理人主控台上檢視，但代理人無法登入。</span><span class="sxs-lookup"><span data-stu-id="1e524-167">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="1e524-168">備份集區所擁有的代理人群組可在代理人主控台上檢視，且代理人可以登入。</span><span class="sxs-lookup"><span data-stu-id="1e524-168">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="1e524-169">匯入的代理人群組顯示在代理人主控台上，且代理人可以登入。</span><span class="sxs-lookup"><span data-stu-id="1e524-169">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e524-170">回應群組設定</span><span class="sxs-lookup"><span data-stu-id="1e524-170">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1e524-171">主要集區所擁有的回應群組可以檢視，視主要集區後端資料庫的可用性而定，但無法修改。</span><span class="sxs-lookup"><span data-stu-id="1e524-171">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="1e524-172">備份集區所擁有的回應群組可以檢視及修改。</span><span class="sxs-lookup"><span data-stu-id="1e524-172">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="1e524-173">無法使用 Lync Server 控制台或回應群組設定工具來查看已匯入的回應群組，但可使用 Lync Server 管理命令介面 Cmdlet 進行設定。</span><span class="sxs-lookup"><span data-stu-id="1e524-173">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="1e524-174">主要集區所擁有的回應群組可以檢視，視主要集區後端資料庫的可用性而定，但無法修改。</span><span class="sxs-lookup"><span data-stu-id="1e524-174">Response groups owned by the primary pool can be viewed, depending on the availability of the back end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="1e524-175">備份集區所擁有的回應群組可以檢視及修改。</span><span class="sxs-lookup"><span data-stu-id="1e524-175">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="1e524-176">無法使用 Lync Server 控制台或回應群組設定工具來查看已匯入的回應群組，但可使用 Lync Server 管理命令介面 Cmdlet 進行設定。</span><span class="sxs-lookup"><span data-stu-id="1e524-176">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="1e524-177">容錯回復期間的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="1e524-177">User Experience During Failback</span></span>

<span data-ttu-id="1e524-178">當系統管理員叫用容錯回復至主要集區時，回應群組活動會在容錯回復期間和之後處理，如下表所述。</span><span class="sxs-lookup"><span data-stu-id="1e524-178">When an administrator invokes failback to the primary pool, response group activity is handled during and after the failback as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1e524-p104">在災害復原期間，通話行為會視主要集區回應群組是否已在復原期間匯入備份集區而有所不同。在下表中，匯入的回應群組參考代表主要集區回應群組已在災害復原模式期間匯入備份集區。</span><span class="sxs-lookup"><span data-stu-id="1e524-p104">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="call-handling-in-failback"></a><span data-ttu-id="1e524-181">容錯回復時的通話處理</span><span class="sxs-lookup"><span data-stu-id="1e524-181">Call Handling in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1e524-182">通話類型或使用者動作</span><span class="sxs-lookup"><span data-stu-id="1e524-182">Type of call or user action</span></span></th>
<th><span data-ttu-id="1e524-183">容錯回復期間</span><span class="sxs-lookup"><span data-stu-id="1e524-183">During Failback</span></span></th>
<th><span data-ttu-id="1e524-184">容錯回復完成之後</span><span class="sxs-lookup"><span data-stu-id="1e524-184">After Failback Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1e524-185">連線至代理人的通話</span><span class="sxs-lookup"><span data-stu-id="1e524-185">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1e524-186">一般通話保持連線。</span><span class="sxs-lookup"><span data-stu-id="1e524-186">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="1e524-187">如果沒有匯入回應群組，就沒有匿名通話處於此狀態。</span><span class="sxs-lookup"><span data-stu-id="1e524-187">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="1e524-188">對於匯入的回應群組，匿名通話會保持連線。</span><span class="sxs-lookup"><span data-stu-id="1e524-188">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="1e524-189">一般通話保持連線。</span><span class="sxs-lookup"><span data-stu-id="1e524-189">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="1e524-190">如果沒有匯入回應群組，就沒有匿名通話處於此狀態。</span><span class="sxs-lookup"><span data-stu-id="1e524-190">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="1e524-191">對於匯入的回應群組，匿名通話會保持連線。</span><span class="sxs-lookup"><span data-stu-id="1e524-191">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e524-192">進行中的通話尚未連線至代理人</span><span class="sxs-lookup"><span data-stu-id="1e524-192">In progress calls not yet connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1e524-193">如果沒有匯入回應群組，就沒有通話處於此狀態。</span><span class="sxs-lookup"><span data-stu-id="1e524-193">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="1e524-194">對於匯入的回應群組，通話將會中斷連線。</span><span class="sxs-lookup"><span data-stu-id="1e524-194">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="1e524-195">如果沒有匯入回應群組，就沒有通話處於此狀態。</span><span class="sxs-lookup"><span data-stu-id="1e524-195">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="1e524-196">對於匯入的回應群組，通話將會中斷連線。</span><span class="sxs-lookup"><span data-stu-id="1e524-196">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e524-197">新通話</span><span class="sxs-lookup"><span data-stu-id="1e524-197">New calls</span></span></p></td>
<td><p><span data-ttu-id="1e524-198">通話會連線至主要集區，但是無法與位於主要集區的代理人連線。</span><span class="sxs-lookup"><span data-stu-id="1e524-198">Calls connect to the primary pool, but agents homed in the primary pool are unreachable.</span></span></p></td>
<td><p><span data-ttu-id="1e524-199">通話連線至主要集區。</span><span class="sxs-lookup"><span data-stu-id="1e524-199">Calls connect to the primary pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e524-200">代表回應群組的代理人通話</span><span class="sxs-lookup"><span data-stu-id="1e524-200">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="1e524-201">功能在此階段停用。</span><span class="sxs-lookup"><span data-stu-id="1e524-201">Feature is disabled during this stage.</span></span></p></td>
<td><p><span data-ttu-id="1e524-202">通話成功。</span><span class="sxs-lookup"><span data-stu-id="1e524-202">Calls succeed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e524-203">代理人登入與代理人資訊</span><span class="sxs-lookup"><span data-stu-id="1e524-203">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1e524-204">主要集區所擁有的代理人群組可在代理人主控台上檢視，但代理人無法登入。</span><span class="sxs-lookup"><span data-stu-id="1e524-204">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="1e524-205">備份集區所擁有的代理人群組可在代理人主控台上檢視，且代理人可以登入。</span><span class="sxs-lookup"><span data-stu-id="1e524-205">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="1e524-206">匯入的代理人群組顯示在代理人主控台上，且代理人可以登入。</span><span class="sxs-lookup"><span data-stu-id="1e524-206">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="1e524-207">主要集區所擁有的代理人群組可在代理人主控台上檢視，且代理人可以登入。</span><span class="sxs-lookup"><span data-stu-id="1e524-207">Agent groups owned by the primary pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="1e524-208">備份集區所擁有的代理人群組可在代理人主控台上檢視，且代理人可以登入。</span><span class="sxs-lookup"><span data-stu-id="1e524-208">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="1e524-209">匯入的代理人群組未顯示在代理人主控台上。</span><span class="sxs-lookup"><span data-stu-id="1e524-209">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e524-210">回應群組設定</span><span class="sxs-lookup"><span data-stu-id="1e524-210">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1e524-211">主要集區所擁有的回應群組可以檢視，視主要集區後端資料庫的可用性而定，但無法修改。</span><span class="sxs-lookup"><span data-stu-id="1e524-211">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="1e524-212">備份集區所擁有的回應群組可以檢視及修改。</span><span class="sxs-lookup"><span data-stu-id="1e524-212">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="1e524-213">無法使用 Lync Server 控制台或回應群組設定工具來查看已匯入的回應群組，但可使用 Lync Server 管理命令介面 Cmdlet 進行設定。</span><span class="sxs-lookup"><span data-stu-id="1e524-213">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="1e524-214">主要集區所擁有的回應群組可以檢視及修改。</span><span class="sxs-lookup"><span data-stu-id="1e524-214">Response groups owned by the primary pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="1e524-215">備份集區所擁有的回應群組可以檢視及修改。</span><span class="sxs-lookup"><span data-stu-id="1e524-215">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="1e524-216">無法使用 Lync Server 控制台或回應群組設定工具來查看已匯入的回應群組，但可使用 Lync Server 管理命令介面 Cmdlet 進行設定。</span><span class="sxs-lookup"><span data-stu-id="1e524-216">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
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

