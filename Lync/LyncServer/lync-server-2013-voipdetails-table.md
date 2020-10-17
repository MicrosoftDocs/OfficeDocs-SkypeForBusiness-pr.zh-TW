---
title: Lync Server 2013： VoipDetails 表格
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
ms.openlocfilehash: 26feac5b9995aa1a8444029442adcb9c935083d3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535410"
---
# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="41811-102">Lync Server 2013 中的 VoipDetails 表格</span><span class="sxs-lookup"><span data-stu-id="41811-102">VoipDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41811-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="41811-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="41811-104">每筆記錄代表一通雙方通話，其中至少一位使用者為 VoIP 使用者。</span><span class="sxs-lookup"><span data-stu-id="41811-104">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41811-105">欄</span><span class="sxs-lookup"><span data-stu-id="41811-105">Column</span></span></th>
<th><span data-ttu-id="41811-106">資料類型</span><span class="sxs-lookup"><span data-stu-id="41811-106">Data Type</span></span></th>
<th><span data-ttu-id="41811-107">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="41811-107">Key/Index</span></span></th>
<th><span data-ttu-id="41811-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="41811-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41811-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="41811-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="41811-110">datetime</span><span class="sxs-lookup"><span data-stu-id="41811-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="41811-111">主要</span><span class="sxs-lookup"><span data-stu-id="41811-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="41811-112">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="41811-112">Time of session request.</span></span> <span data-ttu-id="41811-113">其會與 <strong>SessionIdSeq</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="41811-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="41811-114">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="41811-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41811-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="41811-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="41811-116">int</span><span class="sxs-lookup"><span data-stu-id="41811-116">int</span></span></p></td>
<td><p><span data-ttu-id="41811-117">主要</span><span class="sxs-lookup"><span data-stu-id="41811-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="41811-118">用來識別工作階段的識別碼。</span><span class="sxs-lookup"><span data-stu-id="41811-118">ID number to identify the session.</span></span> <span data-ttu-id="41811-119">會與 <strong>SessionIdTime</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="41811-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="41811-120">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="41811-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41811-121"><strong>FromNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="41811-121"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="41811-122">int</span><span class="sxs-lookup"><span data-stu-id="41811-122">int</span></span></p></td>
<td><p><span data-ttu-id="41811-123">Foreign</span><span class="sxs-lookup"><span data-stu-id="41811-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="41811-124">發話者的 <strong>PhoneId</strong>。</span><span class="sxs-lookup"><span data-stu-id="41811-124"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="41811-125">如需詳細資訊，請參閱 <a href="lync-server-2013-phones-table.md">Lync Server 2013 中</a> 的 [電話] 表格。</span><span class="sxs-lookup"><span data-stu-id="41811-125">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="41811-126">若非 NULL，且 <strong>FromGatewayId</strong> 亦非 NULL，代表發話者為 PSTN 使用者。</span><span class="sxs-lookup"><span data-stu-id="41811-126">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41811-127"><strong>ConnectedNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="41811-127"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="41811-128">int</span><span class="sxs-lookup"><span data-stu-id="41811-128">int</span></span></p></td>
<td><p><span data-ttu-id="41811-129">Foreign</span><span class="sxs-lookup"><span data-stu-id="41811-129">Foreign</span></span></p></td>
<td><p><span data-ttu-id="41811-130">受話者的 <strong>PhoneId</strong>。</span><span class="sxs-lookup"><span data-stu-id="41811-130"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="41811-131">如需詳細資訊，請參閱 <a href="lync-server-2013-phones-table.md">Lync Server 2013 中</a> 的 [電話] 表格。</span><span class="sxs-lookup"><span data-stu-id="41811-131">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="41811-132">若非 NULL，且 <strong>ToGatewayId</strong> 亦非 NULL，代表受話者為 PSTN 使用者。</span><span class="sxs-lookup"><span data-stu-id="41811-132">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41811-133"><strong>FromMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="41811-133"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="41811-134">int</span><span class="sxs-lookup"><span data-stu-id="41811-134">int</span></span></p></td>
<td><p><span data-ttu-id="41811-135">Foreign</span><span class="sxs-lookup"><span data-stu-id="41811-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="41811-136">通話的來源中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="41811-136">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="41811-137">如需詳細資訊，請參閱 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="41811-137">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41811-138"><strong>ToMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="41811-138"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="41811-139">int</span><span class="sxs-lookup"><span data-stu-id="41811-139">int</span></span></p></td>
<td><p><span data-ttu-id="41811-140">Foreign</span><span class="sxs-lookup"><span data-stu-id="41811-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="41811-141">通話的目標中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="41811-141">The Mediation Server called is going to.</span></span> <span data-ttu-id="41811-142">如需詳細資訊，請參閱 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="41811-142">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41811-143"><strong>FromGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="41811-143"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="41811-144">int</span><span class="sxs-lookup"><span data-stu-id="41811-144">int</span></span></p></td>
<td><p><span data-ttu-id="41811-145">Foreign</span><span class="sxs-lookup"><span data-stu-id="41811-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="41811-146">通話的來源閘道。</span><span class="sxs-lookup"><span data-stu-id="41811-146">Gateway the call is coming from.</span></span> <span data-ttu-id="41811-147">如需詳細資訊，請參閱 <a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的閘道表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="41811-147">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41811-148"><strong>ToGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="41811-148"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="41811-149">int</span><span class="sxs-lookup"><span data-stu-id="41811-149">int</span></span></p></td>
<td><p><span data-ttu-id="41811-150">Foreign</span><span class="sxs-lookup"><span data-stu-id="41811-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="41811-151">通話的目標閘道。</span><span class="sxs-lookup"><span data-stu-id="41811-151">Gateway the call is going to.</span></span> <span data-ttu-id="41811-152">如需詳細資訊，請參閱 <a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的閘道表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="41811-152">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41811-153"><strong>DisconnectedbyURIId</strong></span><span class="sxs-lookup"><span data-stu-id="41811-153"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="41811-154">int</span><span class="sxs-lookup"><span data-stu-id="41811-154">int</span></span></p></td>
<td><p><span data-ttu-id="41811-155">Foreign</span><span class="sxs-lookup"><span data-stu-id="41811-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="41811-156">中斷通話之使用者的 URI (若該使用者有 URI 的話)。</span><span class="sxs-lookup"><span data-stu-id="41811-156">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="41811-157">如需詳細資訊，請參閱 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="41811-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41811-158"><strong>DisconnectedbyPhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="41811-158"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="41811-159">int</span><span class="sxs-lookup"><span data-stu-id="41811-159">int</span></span></p></td>
<td><p><span data-ttu-id="41811-160">Foreign</span><span class="sxs-lookup"><span data-stu-id="41811-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="41811-161">中斷通話之電話的識別碼 (若通話是從電話所中斷的話)。</span><span class="sxs-lookup"><span data-stu-id="41811-161">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="41811-162">如需詳細資訊，請參閱 <a href="lync-server-2013-phones-table.md">Lync Server 2013 中</a> 的 [電話] 表格。</span><span class="sxs-lookup"><span data-stu-id="41811-162">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

