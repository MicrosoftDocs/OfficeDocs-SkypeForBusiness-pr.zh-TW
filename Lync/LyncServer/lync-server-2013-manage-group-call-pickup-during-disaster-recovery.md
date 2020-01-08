---
title: Lync Server 2013：管理在災害復原期間進行挑選的群組呼叫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manage Group Call Pickup during disaster recovery
ms:assetid: 2d32f19f-c649-4a72-a4fb-edd338e3a7cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945618(v=OCS.15)
ms:contentKeyID: 51541455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bed21a672dfecab4c3cc8d828fd40f52bd82a363
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977534"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="51c79-102">在 Lync Server 2013 的災害復原期間管理群組呼叫挑選</span><span class="sxs-lookup"><span data-stu-id="51c79-102">Manage Group Call Pickup during disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51c79-103">_**主題上次修改日期：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="51c79-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="51c79-104">當前端池由於未計畫的事件而無法使用時，服務就會失敗轉移至備份池。</span><span class="sxs-lookup"><span data-stu-id="51c79-104">When a Front End pool becomes unavailable due an unplanned incident, service is failed over to the backup pool.</span></span> <span data-ttu-id="51c79-105">在容錯移轉至備份池期間，使用者會被重新導向至備份池，且處於復原模式。</span><span class="sxs-lookup"><span data-stu-id="51c79-105">During failover to the backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="51c79-106">在復原模式中，使用者無法挑選其他使用者的通話，或由其他使用者接聽來電。</span><span class="sxs-lookup"><span data-stu-id="51c79-106">While in resiliency mode, users cannot pick up other users' calls or have their calls picked up by other users.</span></span> <span data-ttu-id="51c79-107">當容錯移轉完成時，使用者可以再次使用群組呼叫拾取。</span><span class="sxs-lookup"><span data-stu-id="51c79-107">When failover is complete, users can again use Group Call Pickup as usual.</span></span>

<span data-ttu-id="51c79-108">在回切至主要池期間，使用者會被重新導向到主要池，且再次處於復原模式。</span><span class="sxs-lookup"><span data-stu-id="51c79-108">During failback to the primary pool, users are redirected to the primary pool and are again in resiliency mode.</span></span> <span data-ttu-id="51c79-109">[群組呼叫] 功能無法使用，直到使用者不在復原模式為止。</span><span class="sxs-lookup"><span data-stu-id="51c79-109">Group Call Pickup functionality is not available until the users are out of resiliency mode.</span></span>

<span data-ttu-id="51c79-110">本節討論災害復原期間群組通話拾取的一些考慮，同時也說明使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="51c79-110">This section discusses some considerations for Group Call Pickup during disaster recovery and also describes the user experience.</span></span>

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a><span data-ttu-id="51c79-111">在災害復原期間進行群組呼叫挑選的考慮</span><span class="sxs-lookup"><span data-stu-id="51c79-111">Considerations for Group Call Pickup During Disaster Recovery</span></span>

<span data-ttu-id="51c79-112">在災害復原期間，已重新導向至備份池的使用者，如果是作為容錯移轉程式的一部分，則會使用在備份池中為呼叫挑選群組編號執行的通話駐留應用程式。</span><span class="sxs-lookup"><span data-stu-id="51c79-112">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application running in the backup pool for the call pickup group numbers.</span></span> <span data-ttu-id="51c79-113">因此，在災害復原期間對群組呼叫挑選的支援，必須在主要池和備份池中部署並啟用呼叫駐留應用程式。</span><span class="sxs-lookup"><span data-stu-id="51c79-113">Therefore, support for Group Call Pickup during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

<span data-ttu-id="51c79-114">在備份池完成容錯移轉程式後，必須將 [通話駐留軌道] 表格中的群組呼叫挑選編號範圍重新導向至備份池。</span><span class="sxs-lookup"><span data-stu-id="51c79-114">The Group Call Pickup number ranges in the call park orbit table must be redirected to the backup pool after the failover process to the backup pool is complete.</span></span> <span data-ttu-id="51c79-115">在回切處理常式完成後，必須將數位範圍重新導向到主要池。</span><span class="sxs-lookup"><span data-stu-id="51c79-115">The number ranges must be redirected back to the primary pool after the failback process to the primary pool is complete.</span></span> <span data-ttu-id="51c79-116">若要重新導向群組呼叫範圍，請使用**CsCallParkOrbit** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="51c79-116">To redirect the Group Call Pickup ranges, use the **Set-CsCallParkOrbit** cmdlet.</span></span>

<span data-ttu-id="51c79-117">如果您使用不同的完整功能變數名稱（FQDN）部署新的池來取代主要池，您必須將與主要池相關聯的所有群組呼叫拾取號碼範圍重新指派給新的池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="51c79-117">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Group Call Pickup number ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="51c79-118">若要將數位範圍重新指派給新的池中，您可以使用**CsCallParkOrbit** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="51c79-118">To reassign number ranges to the new pool, you can use the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="51c79-119">如需**CsCallParkOrbit** Cmdlet 的詳細資訊，請參閱[設定 CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)。</span><span class="sxs-lookup"><span data-stu-id="51c79-119">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a><span data-ttu-id="51c79-120">在池失敗期間的群組呼叫裝貨體驗</span><span class="sxs-lookup"><span data-stu-id="51c79-120">Group Call Pickup Experience During Pool Failure</span></span>

<span data-ttu-id="51c79-121">下表摘要列出透過災難復原階段的群組通話體驗。</span><span class="sxs-lookup"><span data-stu-id="51c79-121">The following table summarizes the Group Call Pickup experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="51c79-122">災害復原期間的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="51c79-122">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="51c79-123">通話狀態</span><span class="sxs-lookup"><span data-stu-id="51c79-123">Call state</span></span></th>
<th><span data-ttu-id="51c79-124">容錯移轉至備份池</span><span class="sxs-lookup"><span data-stu-id="51c79-124">Failover to backup pool</span></span></th>
<th><span data-ttu-id="51c79-125">回切至主要池</span><span class="sxs-lookup"><span data-stu-id="51c79-125">Failback to primary pool</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="51c79-126">新的通話</span><span class="sxs-lookup"><span data-stu-id="51c79-126">New calls</span></span></p></td>
<td><p><span data-ttu-id="51c79-127"><strong>在容錯移轉處理期間：</strong></span><span class="sxs-lookup"><span data-stu-id="51c79-127"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="51c79-128">使用者處於復原模式時無法使用群組呼叫挑選</span><span class="sxs-lookup"><span data-stu-id="51c79-128">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="51c79-129"><strong>容錯移轉完成後：</strong></span><span class="sxs-lookup"><span data-stu-id="51c79-129"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="51c79-130">當使用者離開復原，且群組呼叫挑選號碼範圍被重新導向至備份池時，可以使用群組通話裝貨</span><span class="sxs-lookup"><span data-stu-id="51c79-130">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected to backup pool</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="51c79-131"><strong>在回切進程期間：</strong></span><span class="sxs-lookup"><span data-stu-id="51c79-131"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="51c79-132">使用者處於復原模式時無法使用群組呼叫挑選</span><span class="sxs-lookup"><span data-stu-id="51c79-132">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="51c79-133"><strong>回切完成後：</strong></span><span class="sxs-lookup"><span data-stu-id="51c79-133"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="51c79-134">當使用者不能復原且群組呼叫挑選號碼範圍被重新導向到主要池時，可以使用群組通話裝貨</span><span class="sxs-lookup"><span data-stu-id="51c79-134">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected back to primary pool</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51c79-135">在群組呼叫分揀佇列中通話</span><span class="sxs-lookup"><span data-stu-id="51c79-135">Calls in Group Call Pickup queue</span></span></p></td>
<td><p><span data-ttu-id="51c79-136"><strong>在容錯移轉處理期間：</strong></span><span class="sxs-lookup"><span data-stu-id="51c79-136"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="51c79-137">無法透過群組呼叫挑選來應答佇列中的通話。</span><span class="sxs-lookup"><span data-stu-id="51c79-137">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="51c79-138"><strong>容錯移轉完成後：</strong></span><span class="sxs-lookup"><span data-stu-id="51c79-138"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="51c79-139">此狀態中沒有通話</span><span class="sxs-lookup"><span data-stu-id="51c79-139">No calls in this state</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="51c79-140"><strong>在回切進程期間：</strong></span><span class="sxs-lookup"><span data-stu-id="51c79-140"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="51c79-141">無法透過群組呼叫挑選來應答佇列中的通話。</span><span class="sxs-lookup"><span data-stu-id="51c79-141">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="51c79-142"><strong>回切完成後：</strong></span><span class="sxs-lookup"><span data-stu-id="51c79-142"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="51c79-143">無法透過群組呼叫挑選來應答佇列中的通話。</span><span class="sxs-lookup"><span data-stu-id="51c79-143">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51c79-144">已建立通話</span><span class="sxs-lookup"><span data-stu-id="51c79-144">Established call</span></span></p></td>
<td><p><span data-ttu-id="51c79-145"><strong>在容錯移轉處理期間：</strong></span><span class="sxs-lookup"><span data-stu-id="51c79-145"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="51c79-146">通話保持連線</span><span class="sxs-lookup"><span data-stu-id="51c79-146">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="51c79-147"><strong>容錯移轉完成後：</strong></span><span class="sxs-lookup"><span data-stu-id="51c79-147"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="51c79-148">通話保持連線</span><span class="sxs-lookup"><span data-stu-id="51c79-148">Calls stay connected</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="51c79-149"><strong>在回切進程期間：</strong></span><span class="sxs-lookup"><span data-stu-id="51c79-149"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="51c79-150">通話保持連線</span><span class="sxs-lookup"><span data-stu-id="51c79-150">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="51c79-151"><strong>回切完成後：</strong></span><span class="sxs-lookup"><span data-stu-id="51c79-151"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="51c79-152">通話保持連線</span><span class="sxs-lookup"><span data-stu-id="51c79-152">Calls stay connected</span></span></p></li>
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

