---
title: Lync Server 2013：VoipDetails 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VoipDetails table
ms:assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398566(v=OCS.15)
ms:contentKeyID: 48184522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f13087202b15cf9b25f0c32741c396c48f628908
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758555"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="b6f0d-102">Lync Server 2013 中的 VoipDetails 表格</span><span class="sxs-lookup"><span data-stu-id="b6f0d-102">VoipDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6f0d-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b6f0d-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b6f0d-104">每個記錄代表 1 2 方通話，其中至少有一個使用者是 VoIP 使用者。</span><span class="sxs-lookup"><span data-stu-id="b6f0d-104">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b6f0d-105">左欄</span><span class="sxs-lookup"><span data-stu-id="b6f0d-105">Column</span></span></th>
<th><span data-ttu-id="b6f0d-106">資料類型</span><span class="sxs-lookup"><span data-stu-id="b6f0d-106">Data Type</span></span></th>
<th><span data-ttu-id="b6f0d-107">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="b6f0d-107">Key/Index</span></span></th>
<th><span data-ttu-id="b6f0d-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="b6f0d-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b6f0d-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="b6f0d-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b6f0d-110">datetime</span><span class="sxs-lookup"><span data-stu-id="b6f0d-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="b6f0d-111">首選</span><span class="sxs-lookup"><span data-stu-id="b6f0d-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="b6f0d-112">會話要求的時間。</span><span class="sxs-lookup"><span data-stu-id="b6f0d-112">Time of session request.</span></span> <span data-ttu-id="b6f0d-113">與<strong>SessionIdSeq</strong>搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="b6f0d-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="b6f0d-114">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="b6f0d-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6f0d-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b6f0d-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b6f0d-116">int</span><span class="sxs-lookup"><span data-stu-id="b6f0d-116">int</span></span></p></td>
<td><p><span data-ttu-id="b6f0d-117">首選</span><span class="sxs-lookup"><span data-stu-id="b6f0d-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="b6f0d-118">識別會話的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="b6f0d-118">ID number to identify the session.</span></span> <span data-ttu-id="b6f0d-119">與<strong>SessionIdTime</strong>搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="b6f0d-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="b6f0d-120">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="b6f0d-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6f0d-121"><strong>FromNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="b6f0d-121"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="b6f0d-122">int</span><span class="sxs-lookup"><span data-stu-id="b6f0d-122">int</span></span></p></td>
<td><p><span data-ttu-id="b6f0d-123">外</span><span class="sxs-lookup"><span data-stu-id="b6f0d-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b6f0d-124">來電者的<strong>PhoneId</strong> 。</span><span class="sxs-lookup"><span data-stu-id="b6f0d-124"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="b6f0d-125">如需詳細資訊，請參閱<a href="lync-server-2013-phones-table.md">Lync Server 2013 中</a>的 [電話] 資料表。</span><span class="sxs-lookup"><span data-stu-id="b6f0d-125">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="b6f0d-126">如果 not Null 且<strong>FromGatewayId</strong>不是 null，則呼叫者是 PSTN 使用者。</span><span class="sxs-lookup"><span data-stu-id="b6f0d-126">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6f0d-127"><strong>ConnectedNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="b6f0d-127"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="b6f0d-128">int</span><span class="sxs-lookup"><span data-stu-id="b6f0d-128">int</span></span></p></td>
<td><p><span data-ttu-id="b6f0d-129">外</span><span class="sxs-lookup"><span data-stu-id="b6f0d-129">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b6f0d-130">呼叫接收器的<strong>PhoneId</strong> 。</span><span class="sxs-lookup"><span data-stu-id="b6f0d-130"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="b6f0d-131">如需詳細資訊，請參閱<a href="lync-server-2013-phones-table.md">Lync Server 2013 中</a>的 [電話] 資料表。</span><span class="sxs-lookup"><span data-stu-id="b6f0d-131">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="b6f0d-132">如果 not Null 且<strong>ToGatewayId</strong>不是 null，則呼叫接收器是 PSTN 使用者。</span><span class="sxs-lookup"><span data-stu-id="b6f0d-132">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6f0d-133"><strong>FromMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="b6f0d-133"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="b6f0d-134">int</span><span class="sxs-lookup"><span data-stu-id="b6f0d-134">int</span></span></p></td>
<td><p><span data-ttu-id="b6f0d-135">外</span><span class="sxs-lookup"><span data-stu-id="b6f0d-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b6f0d-136">呼叫來源的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="b6f0d-136">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="b6f0d-137">如需詳細資訊，請參閱<a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中</a>的 [MediationServers] 資料表。</span><span class="sxs-lookup"><span data-stu-id="b6f0d-137">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6f0d-138"><strong>ToMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="b6f0d-138"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="b6f0d-139">int</span><span class="sxs-lookup"><span data-stu-id="b6f0d-139">int</span></span></p></td>
<td><p><span data-ttu-id="b6f0d-140">外</span><span class="sxs-lookup"><span data-stu-id="b6f0d-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b6f0d-141">呼叫的中繼伺服器將要移至。</span><span class="sxs-lookup"><span data-stu-id="b6f0d-141">The Mediation Server called is going to.</span></span> <span data-ttu-id="b6f0d-142">如需詳細資訊，請參閱<a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中</a>的 [MediationServers] 資料表。</span><span class="sxs-lookup"><span data-stu-id="b6f0d-142">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6f0d-143"><strong>FromGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="b6f0d-143"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="b6f0d-144">int</span><span class="sxs-lookup"><span data-stu-id="b6f0d-144">int</span></span></p></td>
<td><p><span data-ttu-id="b6f0d-145">外</span><span class="sxs-lookup"><span data-stu-id="b6f0d-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b6f0d-146">通話來源的閘道。</span><span class="sxs-lookup"><span data-stu-id="b6f0d-146">Gateway the call is coming from.</span></span> <span data-ttu-id="b6f0d-147">如需詳細資訊，請參閱<a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的 [閘道] 資料表</a>。</span><span class="sxs-lookup"><span data-stu-id="b6f0d-147">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6f0d-148"><strong>ToGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="b6f0d-148"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="b6f0d-149">int</span><span class="sxs-lookup"><span data-stu-id="b6f0d-149">int</span></span></p></td>
<td><p><span data-ttu-id="b6f0d-150">外</span><span class="sxs-lookup"><span data-stu-id="b6f0d-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b6f0d-151">通話的閘道。</span><span class="sxs-lookup"><span data-stu-id="b6f0d-151">Gateway the call is going to.</span></span> <span data-ttu-id="b6f0d-152">如需詳細資訊，請參閱<a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的 [閘道] 資料表</a>。</span><span class="sxs-lookup"><span data-stu-id="b6f0d-152">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6f0d-153"><strong>DisconnectedbyURIId</strong></span><span class="sxs-lookup"><span data-stu-id="b6f0d-153"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="b6f0d-154">int</span><span class="sxs-lookup"><span data-stu-id="b6f0d-154">int</span></span></p></td>
<td><p><span data-ttu-id="b6f0d-155">外</span><span class="sxs-lookup"><span data-stu-id="b6f0d-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b6f0d-156">中斷通話的使用者 URI （如果使用者有 URI）。</span><span class="sxs-lookup"><span data-stu-id="b6f0d-156">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="b6f0d-157">如需詳細資訊，請參閱<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 [使用者] 資料表。</span><span class="sxs-lookup"><span data-stu-id="b6f0d-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6f0d-158"><strong>DisconnectedbyPhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="b6f0d-158"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="b6f0d-159">int</span><span class="sxs-lookup"><span data-stu-id="b6f0d-159">int</span></span></p></td>
<td><p><span data-ttu-id="b6f0d-160">外</span><span class="sxs-lookup"><span data-stu-id="b6f0d-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b6f0d-161">中斷通話的電話的識別碼已從手機中斷連線。</span><span class="sxs-lookup"><span data-stu-id="b6f0d-161">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="b6f0d-162">如需詳細資訊，請參閱<a href="lync-server-2013-phones-table.md">Lync Server 2013 中</a>的 [電話] 資料表。</span><span class="sxs-lookup"><span data-stu-id="b6f0d-162">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

