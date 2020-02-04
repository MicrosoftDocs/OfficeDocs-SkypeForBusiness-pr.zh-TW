---
title: Lync Server 2013：集區失敗期間的通話駐留體驗
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
ms.openlocfilehash: 59de3b7cc7490c84536cfbc1457c6486af52c33a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742963"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="844ca-102">集區失敗期間使用 Lync Server 2013 的通話駐留體驗</span><span class="sxs-lookup"><span data-stu-id="844ca-102">Call Park experience in Lync Server 2013 during pool failure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="844ca-103">_**主題上次修改日期：** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="844ca-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="844ca-104">當前端池由於未計畫的事件而無法使用時，已暫停但尚未檢索的通話會中斷連線。</span><span class="sxs-lookup"><span data-stu-id="844ca-104">When a Front End pool becomes unavailable due an unplanned incident, calls that have been parked but not yet retrieved are disconnected.</span></span> <span data-ttu-id="844ca-105">在容錯移轉至備份池期間，使用者會被重新導向至備份池，且處於復原模式。</span><span class="sxs-lookup"><span data-stu-id="844ca-105">During failover to a backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="844ca-106">在復原模式中，使用者不能停止通話，但可以保留通話並加以轉移。</span><span class="sxs-lookup"><span data-stu-id="844ca-106">While in resiliency mode, users cannot park calls, but they can place calls on hold and transfer them.</span></span> <span data-ttu-id="844ca-107">當容錯移轉完成後，就可以再次停用和檢索通話。</span><span class="sxs-lookup"><span data-stu-id="844ca-107">When failover is complete, calls can again be parked and retrieved as usual.</span></span> <span data-ttu-id="844ca-108">在回切期間，使用者不能停止呼叫，直到他們不在復原模式為止。</span><span class="sxs-lookup"><span data-stu-id="844ca-108">During failback, users cannot park calls until they are out of resiliency mode.</span></span>

<span data-ttu-id="844ca-109">在災害復原期間，已重新導向至備份池的使用者，如果是作為容錯移轉程式的一部分，則會使用在備份池中部署的通話駐留應用程式。</span><span class="sxs-lookup"><span data-stu-id="844ca-109">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application that is deployed in the backup pool.</span></span> <span data-ttu-id="844ca-110">因此，重新導向至備份池的使用者，請使用針對備份池中的通話駐留應用程式所設定的通話駐留設定。</span><span class="sxs-lookup"><span data-stu-id="844ca-110">Therefore, users who are redirected to the backup pool use the call park settings that are configured for the Call Park application in the backup pool.</span></span>

<span data-ttu-id="844ca-111">下表摘要列出災害復原階段的通話寄存體驗。</span><span class="sxs-lookup"><span data-stu-id="844ca-111">The following table summarizes the Call Park experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="844ca-112">災害復原期間的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="844ca-112">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="844ca-113">通話狀態</span><span class="sxs-lookup"><span data-stu-id="844ca-113">Call state</span></span></th>
<th><span data-ttu-id="844ca-114">當停機時間</span><span class="sxs-lookup"><span data-stu-id="844ca-114">When outage occurs</span></span></th>
<th><span data-ttu-id="844ca-115">在容錯移轉期間</span><span class="sxs-lookup"><span data-stu-id="844ca-115">During failover</span></span></th>
<th><span data-ttu-id="844ca-116">在回切期間</span><span class="sxs-lookup"><span data-stu-id="844ca-116">During failback</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="844ca-117">通話尚未停用</span><span class="sxs-lookup"><span data-stu-id="844ca-117">Call not yet parked</span></span></p></td>
<td><p><span data-ttu-id="844ca-118">通話仍保持連線，但無法停用。</span><span class="sxs-lookup"><span data-stu-id="844ca-118">Call remains connected, but cannot be parked.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="844ca-119">在容錯移轉期間，不能在使用者處於復原模式時停用通話，但可以保留並傳送。</span><span class="sxs-lookup"><span data-stu-id="844ca-119">During failover, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="844ca-120">當容錯移轉完成時，可以停用或檢索通話。</span><span class="sxs-lookup"><span data-stu-id="844ca-120">When failover completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="844ca-121">在回切期間，不能在使用者處於復原模式時停用通話，但可以保留並傳送。</span><span class="sxs-lookup"><span data-stu-id="844ca-121">During failback, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="844ca-122">當回切完成時，可以停用或檢索通話。</span><span class="sxs-lookup"><span data-stu-id="844ca-122">When failback completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="844ca-123">呼叫已暫停，但尚未檢索</span><span class="sxs-lookup"><span data-stu-id="844ca-123">Call parked, but not yet retrieved</span></span></p></td>
<td><p><span data-ttu-id="844ca-124">通話已中斷連線。</span><span class="sxs-lookup"><span data-stu-id="844ca-124">Call is disconnected.</span></span></p></td>
<td><p><span data-ttu-id="844ca-125">此狀態中沒有通話。</span><span class="sxs-lookup"><span data-stu-id="844ca-125">No calls in this state.</span></span></p></td>
<td><p><span data-ttu-id="844ca-126">通話仍保持停用。</span><span class="sxs-lookup"><span data-stu-id="844ca-126">Call remains parked.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="844ca-127">已檢索到 [寄存通話]</span><span class="sxs-lookup"><span data-stu-id="844ca-127">Parked call already retrieved</span></span></p></td>
<td><p><span data-ttu-id="844ca-128">通話仍保持連線。</span><span class="sxs-lookup"><span data-stu-id="844ca-128">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="844ca-129">通話仍保持連線。</span><span class="sxs-lookup"><span data-stu-id="844ca-129">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="844ca-130">通話仍保持連線。</span><span class="sxs-lookup"><span data-stu-id="844ca-130">Call remains connected.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

