---
title: Lync Server 2013：集區失敗期間的通話駐留體驗
description: Lync Server 2013：集區失敗期間的通話駐留體驗。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park experience during pool failure
ms:assetid: f6303e69-8771-492a-9e8b-c3d7ba231309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205383(v=OCS.15)
ms:contentKeyID: 48185831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b97a0af13d378b0753979c32b6d5ffe7a525cf0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565269"
---
# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="59f78-103">集區失敗期間的 Lync Server 2013 中的通話駐留體驗</span><span class="sxs-lookup"><span data-stu-id="59f78-103">Call Park experience in Lync Server 2013 during pool failure</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59f78-104">_**主題上次修改日期：** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="59f78-104">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="59f78-105">當前端集區因未計畫的事件而變為無法使用時，已寄存但尚未找回的來電會中斷連線。</span><span class="sxs-lookup"><span data-stu-id="59f78-105">When a Front End pool becomes unavailable due an unplanned incident, calls that have been parked but not yet retrieved are disconnected.</span></span> <span data-ttu-id="59f78-106">容錯移轉至備份組區時，會將使用者重新導向至備份組區，並以復原模式進行。</span><span class="sxs-lookup"><span data-stu-id="59f78-106">During failover to a backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="59f78-107">在復原模式中，使用者無法寄存通話，但是可以保留通話，並將其轉接。</span><span class="sxs-lookup"><span data-stu-id="59f78-107">While in resiliency mode, users cannot park calls, but they can place calls on hold and transfer them.</span></span> <span data-ttu-id="59f78-108">容錯移轉完成之後，就可以再照常停用和找回通話。</span><span class="sxs-lookup"><span data-stu-id="59f78-108">When failover is complete, calls can again be parked and retrieved as usual.</span></span> <span data-ttu-id="59f78-109">在回切期間內，使用者將無法寄存通話，直到其無法恢復執行模式為止。</span><span class="sxs-lookup"><span data-stu-id="59f78-109">During failback, users cannot park calls until they are out of resiliency mode.</span></span>

<span data-ttu-id="59f78-110">在嚴重損壞復原期間，已被重新導向至備份組區的使用者，在容錯移轉過程中，會使用部署于備份組區中的通話駐留應用程式。</span><span class="sxs-lookup"><span data-stu-id="59f78-110">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application that is deployed in the backup pool.</span></span> <span data-ttu-id="59f78-111">因此，重新導向至備份組區的使用者，會使用針對備份組區中的通話駐留應用程式所設定的通話駐留設定。</span><span class="sxs-lookup"><span data-stu-id="59f78-111">Therefore, users who are redirected to the backup pool use the call park settings that are configured for the Call Park application in the backup pool.</span></span>

<span data-ttu-id="59f78-112">下表摘要說明災難復原階段的通話駐留體驗。</span><span class="sxs-lookup"><span data-stu-id="59f78-112">The following table summarizes the Call Park experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="59f78-113">發生嚴重損壞修復的使用者經驗</span><span class="sxs-lookup"><span data-stu-id="59f78-113">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="59f78-114">通話狀態</span><span class="sxs-lookup"><span data-stu-id="59f78-114">Call state</span></span></th>
<th><span data-ttu-id="59f78-115">當中斷發生時</span><span class="sxs-lookup"><span data-stu-id="59f78-115">When outage occurs</span></span></th>
<th><span data-ttu-id="59f78-116">容錯移轉期間</span><span class="sxs-lookup"><span data-stu-id="59f78-116">During failover</span></span></th>
<th><span data-ttu-id="59f78-117">回復期間</span><span class="sxs-lookup"><span data-stu-id="59f78-117">During failback</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59f78-118">尚未寄存通話</span><span class="sxs-lookup"><span data-stu-id="59f78-118">Call not yet parked</span></span></p></td>
<td><p><span data-ttu-id="59f78-119">通話保持連線，但無法寄存。</span><span class="sxs-lookup"><span data-stu-id="59f78-119">Call remains connected, but cannot be parked.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="59f78-120">在容錯移轉期間，使用者處於復原模式，無法駐留通話，但可保留與轉接通話。</span><span class="sxs-lookup"><span data-stu-id="59f78-120">During failover, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="59f78-121">容錯移轉完成時，可以寄存及取回通話。</span><span class="sxs-lookup"><span data-stu-id="59f78-121">When failover completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="59f78-122">在回復期間，使用者處於復原模式，無法駐留通話，但可保留與轉接通話。</span><span class="sxs-lookup"><span data-stu-id="59f78-122">During failback, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="59f78-123">當回切完成時，可以寄存及取回通話。</span><span class="sxs-lookup"><span data-stu-id="59f78-123">When failback completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59f78-124">通話已寄存，但尚未找回</span><span class="sxs-lookup"><span data-stu-id="59f78-124">Call parked, but not yet retrieved</span></span></p></td>
<td><p><span data-ttu-id="59f78-125">通話中斷連線。</span><span class="sxs-lookup"><span data-stu-id="59f78-125">Call is disconnected.</span></span></p></td>
<td><p><span data-ttu-id="59f78-126">沒有處於此狀態的來電。</span><span class="sxs-lookup"><span data-stu-id="59f78-126">No calls in this state.</span></span></p></td>
<td><p><span data-ttu-id="59f78-127">通話保持寄存狀態。</span><span class="sxs-lookup"><span data-stu-id="59f78-127">Call remains parked.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59f78-128">已找回寄存通話</span><span class="sxs-lookup"><span data-stu-id="59f78-128">Parked call already retrieved</span></span></p></td>
<td><p><span data-ttu-id="59f78-129">通話保持連線。</span><span class="sxs-lookup"><span data-stu-id="59f78-129">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="59f78-130">通話保持連線。</span><span class="sxs-lookup"><span data-stu-id="59f78-130">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="59f78-131">通話保持連線。</span><span class="sxs-lookup"><span data-stu-id="59f78-131">Call remains connected.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

