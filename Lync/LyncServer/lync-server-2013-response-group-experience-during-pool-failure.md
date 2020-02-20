---
title: 集區失敗期間的 Lync Server 2013 回應群組經驗
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
ms.openlocfilehash: d3977d05c0916cc23f628c0af26be1cbc8a79990
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144790"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="7aec0-102">Lync Server 2013 中遇到集區失敗期間的回應群組</span><span class="sxs-lookup"><span data-stu-id="7aec0-102">Response group experience in Lync Server 2013 during pool failure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7aec0-103">_**主題上次修改日期：** 2012年-10-30_</span><span class="sxs-lookup"><span data-stu-id="7aec0-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="7aec0-104">本節詳細說明回應群組活動在下列階段所受到的影響：</span><span class="sxs-lookup"><span data-stu-id="7aec0-104">This section describes in detail how response group activity is affected in the following stages:</span></span>

  - <span data-ttu-id="7aec0-105">主要集區中發生中斷，但尚未起始容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="7aec0-105">An outage occurs in the primary pool, but failover is not yet initiated.</span></span>

  - <span data-ttu-id="7aec0-106">服務已容錯移轉至備用集區。</span><span class="sxs-lookup"><span data-stu-id="7aec0-106">Service is failed over to the backup pool.</span></span>

  - <span data-ttu-id="7aec0-107">服務已容錯回復至主要集區。</span><span class="sxs-lookup"><span data-stu-id="7aec0-107">Service is failed back to the primary pool.</span></span>

<div>

## <a name="user-experience-when-outage-occurs"></a><span data-ttu-id="7aec0-108">發生中斷時的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="7aec0-108">User Experience When Outage Occurs</span></span>

<span data-ttu-id="7aec0-109">當集區或網站發生中斷，但系統管理員尚未起始容錯移轉時，回應群組活動的處理方式如下表所述。</span><span class="sxs-lookup"><span data-stu-id="7aec0-109">When a pool or site outage occurs, but the administrator has not yet initiated failover, response group activity is handled as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7aec0-p101">在災害復原期間，通話行為會視主要集區回應群組是否已在復原期間匯入備份集區而有所不同。在下表中，匯入的回應群組參考代表主要集區回應群組已在災害復原模式期間匯入備份集區。</span><span class="sxs-lookup"><span data-stu-id="7aec0-p101">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="outage-occurs"></a><span data-ttu-id="7aec0-112">發生中斷</span><span class="sxs-lookup"><span data-stu-id="7aec0-112">Outage Occurs</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7aec0-113">通話類型或使用者動作</span><span class="sxs-lookup"><span data-stu-id="7aec0-113">Type of call or user action</span></span></th>
<th><span data-ttu-id="7aec0-114">中斷期間</span><span class="sxs-lookup"><span data-stu-id="7aec0-114">During outage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7aec0-115">連線至代理人的通話</span><span class="sxs-lookup"><span data-stu-id="7aec0-115">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7aec0-116">一般通話保持連線。</span><span class="sxs-lookup"><span data-stu-id="7aec0-116">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="7aec0-117">匿名通話中斷連線。</span><span class="sxs-lookup"><span data-stu-id="7aec0-117">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aec0-118">進行中的通話尚未連線至代理</span><span class="sxs-lookup"><span data-stu-id="7aec0-118">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="7aec0-119">通話中斷連線。</span><span class="sxs-lookup"><span data-stu-id="7aec0-119">Calls are disconnected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aec0-120">新通話</span><span class="sxs-lookup"><span data-stu-id="7aec0-120">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7aec0-121">通話中斷連線。</span><span class="sxs-lookup"><span data-stu-id="7aec0-121">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="7aec0-122">如果已匯入回應群組，通話會連線至備份集區，但是無法與位於主要集區的代理人連線。</span><span class="sxs-lookup"><span data-stu-id="7aec0-122">If response groups were imported, calls connect to backup pool, but agents homed in primary pool are unreachable.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aec0-123">代表回應群組的代理人通話</span><span class="sxs-lookup"><span data-stu-id="7aec0-123">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="7aec0-124">功能在此階段停用。</span><span class="sxs-lookup"><span data-stu-id="7aec0-124">Feature is disabled during this stage.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aec0-125">代理人登入與代理人資訊</span><span class="sxs-lookup"><span data-stu-id="7aec0-125">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7aec0-126">由主要集區擁有的代理群組可在代理主控台上檢視，但代理無法登入。</span><span class="sxs-lookup"><span data-stu-id="7aec0-126">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="7aec0-127">備用集區所擁有的代理人群組可在代理人主控台上檢視，且代理人可以登入。</span><span class="sxs-lookup"><span data-stu-id="7aec0-127">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="7aec0-128">匯入的代理人群組未顯示在代理人主控台上。</span><span class="sxs-lookup"><span data-stu-id="7aec0-128">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aec0-129">回應群組設定</span><span class="sxs-lookup"><span data-stu-id="7aec0-129">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7aec0-130">主要集區所擁有的回應群組可以檢視，視主要集區後端資料庫的可用性而定，但無法修改。</span><span class="sxs-lookup"><span data-stu-id="7aec0-130">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="7aec0-131">備份集區所擁有的回應群組可以檢視及修改。</span><span class="sxs-lookup"><span data-stu-id="7aec0-131">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="7aec0-132">匯入的回應群組無法與 Lync Server Control Panel 或 [回應群組組態工具] 中，檢視，但可使用 Lync Server 管理命令介面指令程式來設定。</span><span class="sxs-lookup"><span data-stu-id="7aec0-132">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="7aec0-133">容錯移轉期間的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="7aec0-133">User Experience During Failover</span></span>

<span data-ttu-id="7aec0-p102">當系統管理員叫用容錯移轉至備份集區時，回應群組活動會在容錯移轉期間和之後處理，如下表所述。第一欄說明可能發生的活動類型。中間一欄說明各活動在容錯移轉至備份集區的短時間內的處理方式。最後一欄說明在容錯移轉程序完成之後以及備份集區代替主要集區時，這段期間活動的處理方式。</span><span class="sxs-lookup"><span data-stu-id="7aec0-p102">When an administrator invokes failover to a backup pool, response group activity is handled during and after the failover as described in the following table. The first column describes the type of activity that might be taking place. The middle column describes how each activity is handled during the brief time that it takes to fail over to the backup pool. The last column describes how the activity is handled for the duration, after the failover process is complete and the backup pool is standing in for the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7aec0-p103">在災害復原期間，通話行為會視主要集區回應群組是否已在復原期間匯入備份集區而有所不同。在下表中，匯入的回應群組參考代表主要集區回應群組已在災害復原模式期間匯入備份集區。</span><span class="sxs-lookup"><span data-stu-id="7aec0-p103">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="failover-is-initiated"></a><span data-ttu-id="7aec0-140">已起始容錯移轉</span><span class="sxs-lookup"><span data-stu-id="7aec0-140">Failover Is Initiated</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7aec0-141">通話類型或使用者動作</span><span class="sxs-lookup"><span data-stu-id="7aec0-141">Type of call or user action</span></span></th>
<th><span data-ttu-id="7aec0-142">容錯移轉期間</span><span class="sxs-lookup"><span data-stu-id="7aec0-142">During Failover</span></span></th>
<th><span data-ttu-id="7aec0-143">容錯移轉完成之後</span><span class="sxs-lookup"><span data-stu-id="7aec0-143">After Failover Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7aec0-144">連線至代理人的通話</span><span class="sxs-lookup"><span data-stu-id="7aec0-144">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7aec0-145">一般通話保持連線。</span><span class="sxs-lookup"><span data-stu-id="7aec0-145">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="7aec0-146">匿名通話中斷連線。</span><span class="sxs-lookup"><span data-stu-id="7aec0-146">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="7aec0-147">一般通話保持連線。</span><span class="sxs-lookup"><span data-stu-id="7aec0-147">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="7aec0-148">對於匯入的回應群組，已連至備份集區的匿名通話會保持連線。</span><span class="sxs-lookup"><span data-stu-id="7aec0-148">For imported response groups, anonymous calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aec0-149">進行中的通話尚未連線至代理</span><span class="sxs-lookup"><span data-stu-id="7aec0-149">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="7aec0-150">通話中斷連線。</span><span class="sxs-lookup"><span data-stu-id="7aec0-150">Calls are disconnected.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7aec0-151">如果沒有匯入回應群組，這個階段就沒有通話。</span><span class="sxs-lookup"><span data-stu-id="7aec0-151">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="7aec0-152">對於匯入的回應群組，已連至備份集區的通話會保持連線。</span><span class="sxs-lookup"><span data-stu-id="7aec0-152">For imported response groups, calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aec0-153">新通話</span><span class="sxs-lookup"><span data-stu-id="7aec0-153">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7aec0-154">通話中斷連線。</span><span class="sxs-lookup"><span data-stu-id="7aec0-154">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="7aec0-155">對於匯入的回應群組，通話會連線至備份集區，但是無法與位於主要集區的代理人連線。</span><span class="sxs-lookup"><span data-stu-id="7aec0-155">For imported response groups, calls connect to the backup pool, but agents homed in the primary pool are unreachable.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="7aec0-156">如果沒有匯入回應群組，通話會中斷連線。</span><span class="sxs-lookup"><span data-stu-id="7aec0-156">If response groups were not imported, calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="7aec0-157">對於匯入的回應群組，通話會連線至備份集區。</span><span class="sxs-lookup"><span data-stu-id="7aec0-157">For imported response groups, calls connect to the backup pool.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aec0-158">代表回應群組的代理人通話</span><span class="sxs-lookup"><span data-stu-id="7aec0-158">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="7aec0-159">功能在此階段停用</span><span class="sxs-lookup"><span data-stu-id="7aec0-159">Feature is disabled during this stage</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7aec0-160">如果沒有匯入回應群組，通話會失敗。</span><span class="sxs-lookup"><span data-stu-id="7aec0-160">If response groups were not imported, calls fail.</span></span></p></li>
<li><p><span data-ttu-id="7aec0-161">對於匯入的回應群組，通話成功。</span><span class="sxs-lookup"><span data-stu-id="7aec0-161">For imported response groups, calls succeed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aec0-162">代理登入與代理資訊</span><span class="sxs-lookup"><span data-stu-id="7aec0-162">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7aec0-163">由主要集區擁有的代理群組可在代理主控台上檢視，但代理無法登入。</span><span class="sxs-lookup"><span data-stu-id="7aec0-163">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="7aec0-164">備用集區所擁有的代理人群組可在代理人主控台上檢視，且代理人可以登入。</span><span class="sxs-lookup"><span data-stu-id="7aec0-164">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="7aec0-165">匯入的代理人群組顯示在代理人主控台上，且代理人可以登入。</span><span class="sxs-lookup"><span data-stu-id="7aec0-165">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="7aec0-166">主要集區所擁有的代理人群組可在代理人主控台上檢視，但代理人無法登入。</span><span class="sxs-lookup"><span data-stu-id="7aec0-166">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="7aec0-167">備用集區所擁有的代理人群組可在代理人主控台上檢視，且代理人可以登入。</span><span class="sxs-lookup"><span data-stu-id="7aec0-167">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="7aec0-168">匯入的代理人群組顯示在代理人主控台上，且代理人可以登入。</span><span class="sxs-lookup"><span data-stu-id="7aec0-168">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aec0-169">回應群組設定</span><span class="sxs-lookup"><span data-stu-id="7aec0-169">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7aec0-170">主要集區所擁有的回應群組可以檢視，視主要集區後端資料庫的可用性而定，但無法修改。</span><span class="sxs-lookup"><span data-stu-id="7aec0-170">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="7aec0-171">備份集區所擁有的回應群組可以檢視及修改。</span><span class="sxs-lookup"><span data-stu-id="7aec0-171">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="7aec0-172">匯入的回應群組無法與 Lync Server Control Panel 或 [回應群組組態工具] 中，檢視，但可使用 Lync Server 管理命令介面指令程式來設定。</span><span class="sxs-lookup"><span data-stu-id="7aec0-172">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="7aec0-173">主要集區所擁有的回應群組可以檢視，視主要集區後端資料庫的可用性而定，但無法修改。</span><span class="sxs-lookup"><span data-stu-id="7aec0-173">Response groups owned by the primary pool can be viewed, depending on the availability of the back end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="7aec0-174">備份集區所擁有的回應群組可以檢視及修改。</span><span class="sxs-lookup"><span data-stu-id="7aec0-174">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="7aec0-175">匯入的回應群組無法與 Lync Server Control Panel 或 [回應群組組態工具] 中，檢視，但可使用 Lync Server 管理命令介面指令程式來設定。</span><span class="sxs-lookup"><span data-stu-id="7aec0-175">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="7aec0-176">容錯回復期間的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="7aec0-176">User Experience During Failback</span></span>

<span data-ttu-id="7aec0-177">當系統管理員叫用容錯回復至主要集區時，回應群組活動會在容錯回復期間和之後處理，如下表所述。</span><span class="sxs-lookup"><span data-stu-id="7aec0-177">When an administrator invokes failback to the primary pool, response group activity is handled during and after the failback as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7aec0-p104">在災害復原期間，通話行為會視主要集區回應群組是否已在復原期間匯入備份集區而有所不同。在下表中，匯入的回應群組參考代表主要集區回應群組已在災害復原模式期間匯入備份集區。</span><span class="sxs-lookup"><span data-stu-id="7aec0-p104">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="call-handling-in-failback"></a><span data-ttu-id="7aec0-180">容錯回復時的通話處理</span><span class="sxs-lookup"><span data-stu-id="7aec0-180">Call Handling in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7aec0-181">通話類型或使用者動作</span><span class="sxs-lookup"><span data-stu-id="7aec0-181">Type of call or user action</span></span></th>
<th><span data-ttu-id="7aec0-182">容錯回復期間</span><span class="sxs-lookup"><span data-stu-id="7aec0-182">During Failback</span></span></th>
<th><span data-ttu-id="7aec0-183">容錯回復完成之後</span><span class="sxs-lookup"><span data-stu-id="7aec0-183">After Failback Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7aec0-184">連線至代理人的通話</span><span class="sxs-lookup"><span data-stu-id="7aec0-184">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7aec0-185">一般通話保持連線。</span><span class="sxs-lookup"><span data-stu-id="7aec0-185">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="7aec0-186">如果沒有匯入回應群組，就沒有匿名通話處於此狀態。</span><span class="sxs-lookup"><span data-stu-id="7aec0-186">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="7aec0-187">對於匯入的回應群組，匿名通話會保持連線。</span><span class="sxs-lookup"><span data-stu-id="7aec0-187">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="7aec0-188">一般通話保持連線。</span><span class="sxs-lookup"><span data-stu-id="7aec0-188">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="7aec0-189">如果沒有匯入回應群組，就沒有匿名通話處於此狀態。</span><span class="sxs-lookup"><span data-stu-id="7aec0-189">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="7aec0-190">對於匯入的回應群組，匿名通話會保持連線。</span><span class="sxs-lookup"><span data-stu-id="7aec0-190">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aec0-191">進行中的通話尚未連線至代理人</span><span class="sxs-lookup"><span data-stu-id="7aec0-191">In progress calls not yet connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7aec0-192">如果沒有匯入回應群組，就沒有通話處於此狀態。</span><span class="sxs-lookup"><span data-stu-id="7aec0-192">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="7aec0-193">對於匯入的回應群組，通話將會中斷連線。</span><span class="sxs-lookup"><span data-stu-id="7aec0-193">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="7aec0-194">如果沒有匯入回應群組，就沒有通話處於此狀態。</span><span class="sxs-lookup"><span data-stu-id="7aec0-194">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="7aec0-195">對於匯入的回應群組，通話將會中斷連線。</span><span class="sxs-lookup"><span data-stu-id="7aec0-195">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aec0-196">新通話</span><span class="sxs-lookup"><span data-stu-id="7aec0-196">New calls</span></span></p></td>
<td><p><span data-ttu-id="7aec0-197">通話會連線至主要集區，但是無法與位於主要集區的代理人連線。</span><span class="sxs-lookup"><span data-stu-id="7aec0-197">Calls connect to the primary pool, but agents homed in the primary pool are unreachable.</span></span></p></td>
<td><p><span data-ttu-id="7aec0-198">通話連線至主要集區。</span><span class="sxs-lookup"><span data-stu-id="7aec0-198">Calls connect to the primary pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aec0-199">代表回應群組的代理人通話</span><span class="sxs-lookup"><span data-stu-id="7aec0-199">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="7aec0-200">功能在此階段停用。</span><span class="sxs-lookup"><span data-stu-id="7aec0-200">Feature is disabled during this stage.</span></span></p></td>
<td><p><span data-ttu-id="7aec0-201">通話成功。</span><span class="sxs-lookup"><span data-stu-id="7aec0-201">Calls succeed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aec0-202">代理人登入與代理人資訊</span><span class="sxs-lookup"><span data-stu-id="7aec0-202">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7aec0-203">由主要集區擁有的代理群組可在代理主控台上檢視，但代理無法登入。</span><span class="sxs-lookup"><span data-stu-id="7aec0-203">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="7aec0-204">備用集區所擁有的代理人群組可在代理人主控台上檢視，且代理人可以登入。</span><span class="sxs-lookup"><span data-stu-id="7aec0-204">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="7aec0-205">匯入的代理人群組顯示在代理人主控台上，且代理人可以登入。</span><span class="sxs-lookup"><span data-stu-id="7aec0-205">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="7aec0-206">主要集區所擁有的代理人群組可在代理人主控台上檢視，且代理人可以登入。</span><span class="sxs-lookup"><span data-stu-id="7aec0-206">Agent groups owned by the primary pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="7aec0-207">備份集區所擁有的代理人群組可在代理人主控台上檢視，且代理人可以登入。</span><span class="sxs-lookup"><span data-stu-id="7aec0-207">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="7aec0-208">匯入的代理人群組未顯示在代理人主控台上。</span><span class="sxs-lookup"><span data-stu-id="7aec0-208">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aec0-209">回應群組設定</span><span class="sxs-lookup"><span data-stu-id="7aec0-209">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7aec0-210">主要集區所擁有的回應群組可以檢視，視主要集區後端資料庫的可用性而定，但無法修改。</span><span class="sxs-lookup"><span data-stu-id="7aec0-210">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="7aec0-211">備份集區所擁有的回應群組可以檢視及修改。</span><span class="sxs-lookup"><span data-stu-id="7aec0-211">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="7aec0-212">匯入的回應群組無法與 Lync Server Control Panel 或 [回應群組組態工具] 中，檢視，但可使用 Lync Server 管理命令介面指令程式來設定。</span><span class="sxs-lookup"><span data-stu-id="7aec0-212">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="7aec0-213">主要集區所擁有的回應群組可以檢視及修改。</span><span class="sxs-lookup"><span data-stu-id="7aec0-213">Response groups owned by the primary pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="7aec0-214">備份集區所擁有的回應群組可以檢視及修改。</span><span class="sxs-lookup"><span data-stu-id="7aec0-214">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="7aec0-215">匯入的回應群組無法與 Lync Server Control Panel 或 [回應群組組態工具] 中，檢視，但可使用 Lync Server 管理命令介面指令程式來設定。</span><span class="sxs-lookup"><span data-stu-id="7aec0-215">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
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

