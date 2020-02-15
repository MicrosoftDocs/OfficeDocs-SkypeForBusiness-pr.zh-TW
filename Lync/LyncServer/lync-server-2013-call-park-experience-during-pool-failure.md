---
title: 集區失敗期間的 Lync Server 2013： 通話駐留經驗
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
ms.openlocfilehash: a89acc193f70ba5047a2f1c6362b957d182afdb5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044315"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="d80d6-102">Lync Server 2013 的集區失敗期間的通話駐留經驗</span><span class="sxs-lookup"><span data-stu-id="d80d6-102">Call Park experience in Lync Server 2013 during pool failure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d80d6-103">_**主題上次修改日期：** 2012年-09-10_</span><span class="sxs-lookup"><span data-stu-id="d80d6-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="d80d6-104">前端集區由於意外事件無法使用時，已駐留但尚未擷取通話中斷連線。</span><span class="sxs-lookup"><span data-stu-id="d80d6-104">When a Front End pool becomes unavailable due an unplanned incident, calls that have been parked but not yet retrieved are disconnected.</span></span> <span data-ttu-id="d80d6-105">容錯移轉期間至備份集區，使用者會重新導向至備份集區，且處於恢復能力模式。</span><span class="sxs-lookup"><span data-stu-id="d80d6-105">During failover to a backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="d80d6-106">在恢復能力模式時，使用者無法駐留通話，但他們可以撥打電話保留並將他們轉接。</span><span class="sxs-lookup"><span data-stu-id="d80d6-106">While in resiliency mode, users cannot park calls, but they can place calls on hold and transfer them.</span></span> <span data-ttu-id="d80d6-107">完成容錯移轉時，呼叫一次可駐留及擷取像平常一樣。</span><span class="sxs-lookup"><span data-stu-id="d80d6-107">When failover is complete, calls can again be parked and retrieved as usual.</span></span> <span data-ttu-id="d80d6-108">容錯回復期間，使用者無法駐留通話，除非經過退出恢復能力模式。</span><span class="sxs-lookup"><span data-stu-id="d80d6-108">During failback, users cannot park calls until they are out of resiliency mode.</span></span>

<span data-ttu-id="d80d6-109">嚴重損壞復原期間已重新導向至備份集區一部分的容錯移轉程序的使用者會使用備份集區中部署通話駐留應用程式。</span><span class="sxs-lookup"><span data-stu-id="d80d6-109">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application that is deployed in the backup pool.</span></span> <span data-ttu-id="d80d6-110">因此，會重新導向至備份集區的使用者會使用所設定的通話駐留設定的備份集區的通話駐留應用程式。</span><span class="sxs-lookup"><span data-stu-id="d80d6-110">Therefore, users who are redirected to the backup pool use the call park settings that are configured for the Call Park application in the backup pool.</span></span>

<span data-ttu-id="d80d6-111">下表摘要說明透過災難復原階段的通話駐留經驗。</span><span class="sxs-lookup"><span data-stu-id="d80d6-111">The following table summarizes the Call Park experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="d80d6-112">嚴重損壞復原期間的使用者經驗</span><span class="sxs-lookup"><span data-stu-id="d80d6-112">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d80d6-113">呼叫狀態</span><span class="sxs-lookup"><span data-stu-id="d80d6-113">Call state</span></span></th>
<th><span data-ttu-id="d80d6-114">發生中斷時</span><span class="sxs-lookup"><span data-stu-id="d80d6-114">When outage occurs</span></span></th>
<th><span data-ttu-id="d80d6-115">容錯移轉期間</span><span class="sxs-lookup"><span data-stu-id="d80d6-115">During failover</span></span></th>
<th><span data-ttu-id="d80d6-116">容錯回復期間</span><span class="sxs-lookup"><span data-stu-id="d80d6-116">During failback</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d80d6-117">尚未駐留通話</span><span class="sxs-lookup"><span data-stu-id="d80d6-117">Call not yet parked</span></span></p></td>
<td><p><span data-ttu-id="d80d6-118">通話保持連線，但無法駐留通話。</span><span class="sxs-lookup"><span data-stu-id="d80d6-118">Call remains connected, but cannot be parked.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d80d6-119">容錯移轉期間，當使用者處於復原模式，但可以保留與轉接無法駐留通話。</span><span class="sxs-lookup"><span data-stu-id="d80d6-119">During failover, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="d80d6-120">完成容錯移轉時，可以駐留與擷取通話。</span><span class="sxs-lookup"><span data-stu-id="d80d6-120">When failover completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="d80d6-121">容錯回復期間，當使用者處於復原模式，但可以保留與轉接無法駐留通話。</span><span class="sxs-lookup"><span data-stu-id="d80d6-121">During failback, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="d80d6-122">完成容錯回復時，可以駐留與擷取通話。</span><span class="sxs-lookup"><span data-stu-id="d80d6-122">When failback completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d80d6-123">通話已駐留，但尚未擷取</span><span class="sxs-lookup"><span data-stu-id="d80d6-123">Call parked, but not yet retrieved</span></span></p></td>
<td><p><span data-ttu-id="d80d6-124">通話已中斷。</span><span class="sxs-lookup"><span data-stu-id="d80d6-124">Call is disconnected.</span></span></p></td>
<td><p><span data-ttu-id="d80d6-125">沒有通話處於此狀態。</span><span class="sxs-lookup"><span data-stu-id="d80d6-125">No calls in this state.</span></span></p></td>
<td><p><span data-ttu-id="d80d6-126">通話保持駐留。</span><span class="sxs-lookup"><span data-stu-id="d80d6-126">Call remains parked.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d80d6-127">已擷取通話</span><span class="sxs-lookup"><span data-stu-id="d80d6-127">Parked call already retrieved</span></span></p></td>
<td><p><span data-ttu-id="d80d6-128">通話保持連線。</span><span class="sxs-lookup"><span data-stu-id="d80d6-128">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="d80d6-129">通話保持連線。</span><span class="sxs-lookup"><span data-stu-id="d80d6-129">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="d80d6-130">通話保持連線。</span><span class="sxs-lookup"><span data-stu-id="d80d6-130">Call remains connected.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

