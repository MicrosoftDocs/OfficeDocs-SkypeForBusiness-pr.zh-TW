---
title: Lync Server 2013：在嚴重損壞修復期間管理群組呼叫收取
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Group Call Pickup during disaster recovery
ms:assetid: 2d32f19f-c649-4a72-a4fb-edd338e3a7cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945618(v=OCS.15)
ms:contentKeyID: 51541455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f58894a00c853f04d5d4c6f995edc17683b12e9f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42218249"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="bca5a-102">在 Lync Server 2013 中管理「在災難修復」期間收取的群組呼叫</span><span class="sxs-lookup"><span data-stu-id="bca5a-102">Manage Group Call Pickup during disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bca5a-103">_**主題上次修改日期：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="bca5a-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="bca5a-104">當前端集區因未計畫的事件而變為無法使用時，服務便會容錯移轉至備份組區。</span><span class="sxs-lookup"><span data-stu-id="bca5a-104">When a Front End pool becomes unavailable due an unplanned incident, service is failed over to the backup pool.</span></span> <span data-ttu-id="bca5a-105">容錯移轉至備份組區時，會將使用者重新導向至備份組區，並以復原模式進行。</span><span class="sxs-lookup"><span data-stu-id="bca5a-105">During failover to the backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="bca5a-106">在復原模式中，使用者無法挑選其他使用者的來電，或讓其他使用者接聽來電。</span><span class="sxs-lookup"><span data-stu-id="bca5a-106">While in resiliency mode, users cannot pick up other users' calls or have their calls picked up by other users.</span></span> <span data-ttu-id="bca5a-107">容錯移轉完成時，使用者可以再次使用群組呼叫收取。</span><span class="sxs-lookup"><span data-stu-id="bca5a-107">When failover is complete, users can again use Group Call Pickup as usual.</span></span>

<span data-ttu-id="bca5a-108">在回切至主要集區時，會將使用者重新導向至主要集區，並以復原模式重新導向。</span><span class="sxs-lookup"><span data-stu-id="bca5a-108">During failback to the primary pool, users are redirected to the primary pool and are again in resiliency mode.</span></span> <span data-ttu-id="bca5a-109">除非使用者在復原模式下，否則無法使用群組呼叫收取功能。</span><span class="sxs-lookup"><span data-stu-id="bca5a-109">Group Call Pickup functionality is not available until the users are out of resiliency mode.</span></span>

<span data-ttu-id="bca5a-110">本節討論在嚴重損壞復原期間，群組呼叫收取的一些考慮，也說明使用者經驗。</span><span class="sxs-lookup"><span data-stu-id="bca5a-110">This section discusses some considerations for Group Call Pickup during disaster recovery and also describes the user experience.</span></span>

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a><span data-ttu-id="bca5a-111">在嚴重損壞修復期間，群組呼叫收取的考慮</span><span class="sxs-lookup"><span data-stu-id="bca5a-111">Considerations for Group Call Pickup During Disaster Recovery</span></span>

<span data-ttu-id="bca5a-112">在嚴重損壞復原期間，已被重新導向至備份組區的使用者，在容錯移轉過程中，會使用在備份組區中為呼叫收取群組號碼執行的通話駐留應用程式。</span><span class="sxs-lookup"><span data-stu-id="bca5a-112">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application running in the backup pool for the call pickup group numbers.</span></span> <span data-ttu-id="bca5a-113">因此，在嚴重損壞修復過程中支援群組呼叫收取，需要在主要集區和備份組區中部署及啟用通話駐留應用程式。</span><span class="sxs-lookup"><span data-stu-id="bca5a-113">Therefore, support for Group Call Pickup during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

<span data-ttu-id="bca5a-114">備份組區的容錯移轉程式完成後，必須將通話駐留軌道表格中的群組呼叫收取號碼範圍重新導向至備份組區。</span><span class="sxs-lookup"><span data-stu-id="bca5a-114">The Group Call Pickup number ranges in the call park orbit table must be redirected to the backup pool after the failover process to the backup pool is complete.</span></span> <span data-ttu-id="bca5a-115">當主要集區的回切處理常式完成後，必須重新導向主要集區的號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="bca5a-115">The number ranges must be redirected back to the primary pool after the failback process to the primary pool is complete.</span></span> <span data-ttu-id="bca5a-116">若要重新導向群組呼叫收取範圍，請使用**get-cscallparkorbit** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bca5a-116">To redirect the Group Call Pickup ranges, use the **Set-CsCallParkOrbit** cmdlet.</span></span>

<span data-ttu-id="bca5a-117">如果您使用不同的完整功能變數名稱來部署新集區 (FQDN) 取代主要集區，您必須將與主要集區相關聯的所有群組呼叫收取號碼範圍重新指派給新集區的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="bca5a-117">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Group Call Pickup number ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="bca5a-118">若要將號碼範圍重新指派給新的集區，您可以使用**get-cscallparkorbit 指令程式**。</span><span class="sxs-lookup"><span data-stu-id="bca5a-118">To reassign number ranges to the new pool, you can use the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="bca5a-119">如需**get-cscallparkorbit** Cmdlet 的詳細資訊，請參閱[set-get-cscallparkorbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)。</span><span class="sxs-lookup"><span data-stu-id="bca5a-119">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a><span data-ttu-id="bca5a-120">集區失敗期間的群組呼叫收取經驗</span><span class="sxs-lookup"><span data-stu-id="bca5a-120">Group Call Pickup Experience During Pool Failure</span></span>

<span data-ttu-id="bca5a-121">下表摘要說明透過嚴重損壞修復的群組呼叫收取經驗。</span><span class="sxs-lookup"><span data-stu-id="bca5a-121">The following table summarizes the Group Call Pickup experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="bca5a-122">發生嚴重損壞修復的使用者經驗</span><span class="sxs-lookup"><span data-stu-id="bca5a-122">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bca5a-123">通話狀態</span><span class="sxs-lookup"><span data-stu-id="bca5a-123">Call state</span></span></th>
<th><span data-ttu-id="bca5a-124">容錯移轉至備份組區</span><span class="sxs-lookup"><span data-stu-id="bca5a-124">Failover to backup pool</span></span></th>
<th><span data-ttu-id="bca5a-125">回切至主要集區</span><span class="sxs-lookup"><span data-stu-id="bca5a-125">Failback to primary pool</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bca5a-126">新通話</span><span class="sxs-lookup"><span data-stu-id="bca5a-126">New calls</span></span></p></td>
<td><p><span data-ttu-id="bca5a-127"><strong>容錯移轉過程中：</strong></span><span class="sxs-lookup"><span data-stu-id="bca5a-127"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="bca5a-128">使用者在復原模式中無法使用群組呼叫收取</span><span class="sxs-lookup"><span data-stu-id="bca5a-128">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="bca5a-129"><strong>容錯移轉完成之後：</strong></span><span class="sxs-lookup"><span data-stu-id="bca5a-129"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="bca5a-130">當使用者不在恢復能力和群組呼叫收取號碼範圍重新導向至備份組區時可用的群組通話收取</span><span class="sxs-lookup"><span data-stu-id="bca5a-130">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected to backup pool</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bca5a-131"><strong>在回切過程中：</strong></span><span class="sxs-lookup"><span data-stu-id="bca5a-131"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="bca5a-132">使用者在復原模式中無法使用群組呼叫收取</span><span class="sxs-lookup"><span data-stu-id="bca5a-132">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="bca5a-133"><strong>容錯回復完成後：</strong></span><span class="sxs-lookup"><span data-stu-id="bca5a-133"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="bca5a-134">當使用者不在恢復能力和群組呼叫收取號碼範圍重新導向至主要集區時可用的群組通話收取</span><span class="sxs-lookup"><span data-stu-id="bca5a-134">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected back to primary pool</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bca5a-135">群組呼叫收取佇列中的通話</span><span class="sxs-lookup"><span data-stu-id="bca5a-135">Calls in Group Call Pickup queue</span></span></p></td>
<td><p><span data-ttu-id="bca5a-136"><strong>容錯移轉過程中：</strong></span><span class="sxs-lookup"><span data-stu-id="bca5a-136"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="bca5a-137">佇列中的通話無法透過群組叫用收取應答。</span><span class="sxs-lookup"><span data-stu-id="bca5a-137">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="bca5a-138"><strong>容錯移轉完成之後：</strong></span><span class="sxs-lookup"><span data-stu-id="bca5a-138"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="bca5a-139">這種狀態沒有來電</span><span class="sxs-lookup"><span data-stu-id="bca5a-139">No calls in this state</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bca5a-140"><strong>在回切過程中：</strong></span><span class="sxs-lookup"><span data-stu-id="bca5a-140"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="bca5a-141">佇列中的通話無法透過群組叫用收取應答。</span><span class="sxs-lookup"><span data-stu-id="bca5a-141">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="bca5a-142"><strong>容錯回復完成後：</strong></span><span class="sxs-lookup"><span data-stu-id="bca5a-142"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="bca5a-143">佇列中的通話無法透過群組叫用收取應答。</span><span class="sxs-lookup"><span data-stu-id="bca5a-143">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bca5a-144">已建立通話</span><span class="sxs-lookup"><span data-stu-id="bca5a-144">Established call</span></span></p></td>
<td><p><span data-ttu-id="bca5a-145"><strong>容錯移轉過程中：</strong></span><span class="sxs-lookup"><span data-stu-id="bca5a-145"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="bca5a-146">通話保持連線</span><span class="sxs-lookup"><span data-stu-id="bca5a-146">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="bca5a-147"><strong>容錯移轉完成之後：</strong></span><span class="sxs-lookup"><span data-stu-id="bca5a-147"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="bca5a-148">通話保持連線</span><span class="sxs-lookup"><span data-stu-id="bca5a-148">Calls stay connected</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bca5a-149"><strong>在回切過程中：</strong></span><span class="sxs-lookup"><span data-stu-id="bca5a-149"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="bca5a-150">通話保持連線</span><span class="sxs-lookup"><span data-stu-id="bca5a-150">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="bca5a-151"><strong>容錯回復完成後：</strong></span><span class="sxs-lookup"><span data-stu-id="bca5a-151"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="bca5a-152">通話保持連線</span><span class="sxs-lookup"><span data-stu-id="bca5a-152">Calls stay connected</span></span></p></li>
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

