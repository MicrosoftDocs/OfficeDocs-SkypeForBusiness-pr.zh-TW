---
title: 'Lync Server 2013: VoipDetails 表格'
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
ms.openlocfilehash: d459262d5126dc6d55f930b20e54cbb1e69e04e9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210912"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="b2ba1-102">Lync Server 2013 中的 VoipDetails 表格</span><span class="sxs-lookup"><span data-stu-id="b2ba1-102">VoipDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2ba1-103">_**主題上次修改日期：** 2012年-09-28_</span><span class="sxs-lookup"><span data-stu-id="b2ba1-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b2ba1-104">每筆記錄代表一通雙方通話，其中至少一位使用者為 VoIP 使用者。</span><span class="sxs-lookup"><span data-stu-id="b2ba1-104">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2ba1-105">欄</span><span class="sxs-lookup"><span data-stu-id="b2ba1-105">Column</span></span></th>
<th><span data-ttu-id="b2ba1-106">資料類型</span><span class="sxs-lookup"><span data-stu-id="b2ba1-106">Data Type</span></span></th>
<th><span data-ttu-id="b2ba1-107">主索引鍵 /</span><span class="sxs-lookup"><span data-stu-id="b2ba1-107">Key/Index</span></span></th>
<th><span data-ttu-id="b2ba1-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="b2ba1-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2ba1-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="b2ba1-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b2ba1-110">datetime</span><span class="sxs-lookup"><span data-stu-id="b2ba1-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="b2ba1-111">主要</span><span class="sxs-lookup"><span data-stu-id="b2ba1-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="b2ba1-112">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="b2ba1-112">Time of session request.</span></span> <span data-ttu-id="b2ba1-113">其會與 <strong>SessionIdSeq</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="b2ba1-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="b2ba1-114"><a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="b2ba1-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2ba1-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b2ba1-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b2ba1-116">int</span><span class="sxs-lookup"><span data-stu-id="b2ba1-116">int</span></span></p></td>
<td><p><span data-ttu-id="b2ba1-117">主要</span><span class="sxs-lookup"><span data-stu-id="b2ba1-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="b2ba1-118">用來識別工作階段的識別碼。</span><span class="sxs-lookup"><span data-stu-id="b2ba1-118">ID number to identify the session.</span></span> <span data-ttu-id="b2ba1-119">會與 <strong>SessionIdTime</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="b2ba1-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="b2ba1-120"><a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="b2ba1-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2ba1-121"><strong>FromNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="b2ba1-121"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="b2ba1-122">int</span><span class="sxs-lookup"><span data-stu-id="b2ba1-122">int</span></span></p></td>
<td><p><span data-ttu-id="b2ba1-123">Foreign</span><span class="sxs-lookup"><span data-stu-id="b2ba1-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b2ba1-124">發話者的 <strong>PhoneId</strong>。</span><span class="sxs-lookup"><span data-stu-id="b2ba1-124"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="b2ba1-125">請參閱<a href="lync-server-2013-phones-table.md">Lync Server 2013 中的 Phones 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="b2ba1-125">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="b2ba1-126">若非 NULL，且 <strong>FromGatewayId</strong> 亦非 NULL，代表發話者為 PSTN 使用者。</span><span class="sxs-lookup"><span data-stu-id="b2ba1-126">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2ba1-127"><strong>ConnectedNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="b2ba1-127"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="b2ba1-128">int</span><span class="sxs-lookup"><span data-stu-id="b2ba1-128">int</span></span></p></td>
<td><p><span data-ttu-id="b2ba1-129">Foreign</span><span class="sxs-lookup"><span data-stu-id="b2ba1-129">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b2ba1-130">受話者的 <strong>PhoneId</strong>。</span><span class="sxs-lookup"><span data-stu-id="b2ba1-130"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="b2ba1-131">請參閱<a href="lync-server-2013-phones-table.md">Lync Server 2013 中的 Phones 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="b2ba1-131">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="b2ba1-132">若非 NULL，且 <strong>ToGatewayId</strong> 亦非 NULL，代表受話者為 PSTN 使用者。</span><span class="sxs-lookup"><span data-stu-id="b2ba1-132">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2ba1-133"><strong>FromMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="b2ba1-133"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="b2ba1-134">int</span><span class="sxs-lookup"><span data-stu-id="b2ba1-134">int</span></span></p></td>
<td><p><span data-ttu-id="b2ba1-135">Foreign</span><span class="sxs-lookup"><span data-stu-id="b2ba1-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b2ba1-136">通話的來源中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="b2ba1-136">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="b2ba1-137">請參閱<a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="b2ba1-137">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2ba1-138"><strong>ToMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="b2ba1-138"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="b2ba1-139">int</span><span class="sxs-lookup"><span data-stu-id="b2ba1-139">int</span></span></p></td>
<td><p><span data-ttu-id="b2ba1-140">Foreign</span><span class="sxs-lookup"><span data-stu-id="b2ba1-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b2ba1-141">通話的目標中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="b2ba1-141">The Mediation Server called is going to.</span></span> <span data-ttu-id="b2ba1-142">請參閱<a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="b2ba1-142">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2ba1-143"><strong>FromGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="b2ba1-143"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="b2ba1-144">int</span><span class="sxs-lookup"><span data-stu-id="b2ba1-144">int</span></span></p></td>
<td><p><span data-ttu-id="b2ba1-145">Foreign</span><span class="sxs-lookup"><span data-stu-id="b2ba1-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b2ba1-146">通話的來源閘道。</span><span class="sxs-lookup"><span data-stu-id="b2ba1-146">Gateway the call is coming from.</span></span> <span data-ttu-id="b2ba1-147">請參閱<a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的 Gateways 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="b2ba1-147">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2ba1-148"><strong>ToGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="b2ba1-148"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="b2ba1-149">int</span><span class="sxs-lookup"><span data-stu-id="b2ba1-149">int</span></span></p></td>
<td><p><span data-ttu-id="b2ba1-150">Foreign</span><span class="sxs-lookup"><span data-stu-id="b2ba1-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b2ba1-151">通話的目標閘道。</span><span class="sxs-lookup"><span data-stu-id="b2ba1-151">Gateway the call is going to.</span></span> <span data-ttu-id="b2ba1-152">請參閱<a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的 Gateways 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="b2ba1-152">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2ba1-153"><strong>DisconnectedbyURIId</strong></span><span class="sxs-lookup"><span data-stu-id="b2ba1-153"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="b2ba1-154">int</span><span class="sxs-lookup"><span data-stu-id="b2ba1-154">int</span></span></p></td>
<td><p><span data-ttu-id="b2ba1-155">Foreign</span><span class="sxs-lookup"><span data-stu-id="b2ba1-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b2ba1-156">中斷通話之使用者的 URI (若該使用者有 URI 的話)。</span><span class="sxs-lookup"><span data-stu-id="b2ba1-156">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="b2ba1-157">請參閱如需詳細資訊，<a href="lync-server-2013-users-table.md">使用者在 Lync Server 2013 中的表格</a>。</span><span class="sxs-lookup"><span data-stu-id="b2ba1-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2ba1-158"><strong>DisconnectedbyPhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="b2ba1-158"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="b2ba1-159">int</span><span class="sxs-lookup"><span data-stu-id="b2ba1-159">int</span></span></p></td>
<td><p><span data-ttu-id="b2ba1-160">Foreign</span><span class="sxs-lookup"><span data-stu-id="b2ba1-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b2ba1-161">中斷通話之電話的識別碼 (若通話是從電話所中斷的話)。</span><span class="sxs-lookup"><span data-stu-id="b2ba1-161">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="b2ba1-162">請參閱<a href="lync-server-2013-phones-table.md">Lync Server 2013 中的 Phones 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="b2ba1-162">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

