---
title: Lync Server 2013： VoipDetails 表格
description: Lync Server 2013： VoipDetails 表格。
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
ms.openlocfilehash: f23d991c1d577a15717de2572d744e1b65ba6bab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566279"
---
# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="8dce5-103">Lync Server 2013 中的 VoipDetails 表格</span><span class="sxs-lookup"><span data-stu-id="8dce5-103">VoipDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8dce5-104">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="8dce5-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="8dce5-105">每筆記錄代表一通雙方通話，其中至少一位使用者為 VoIP 使用者。</span><span class="sxs-lookup"><span data-stu-id="8dce5-105">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8dce5-106">欄</span><span class="sxs-lookup"><span data-stu-id="8dce5-106">Column</span></span></th>
<th><span data-ttu-id="8dce5-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="8dce5-107">Data Type</span></span></th>
<th><span data-ttu-id="8dce5-108">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="8dce5-108">Key/Index</span></span></th>
<th><span data-ttu-id="8dce5-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="8dce5-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8dce5-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="8dce5-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8dce5-111">datetime</span><span class="sxs-lookup"><span data-stu-id="8dce5-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="8dce5-112">主要</span><span class="sxs-lookup"><span data-stu-id="8dce5-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="8dce5-113">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="8dce5-113">Time of session request.</span></span> <span data-ttu-id="8dce5-114">其會與 <strong>SessionIdSeq</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="8dce5-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="8dce5-115">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="8dce5-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dce5-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="8dce5-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="8dce5-117">int</span><span class="sxs-lookup"><span data-stu-id="8dce5-117">int</span></span></p></td>
<td><p><span data-ttu-id="8dce5-118">主要</span><span class="sxs-lookup"><span data-stu-id="8dce5-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="8dce5-119">用來識別工作階段的識別碼。</span><span class="sxs-lookup"><span data-stu-id="8dce5-119">ID number to identify the session.</span></span> <span data-ttu-id="8dce5-120">會與 <strong>SessionIdTime</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="8dce5-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="8dce5-121">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="8dce5-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dce5-122"><strong>FromNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="8dce5-122"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="8dce5-123">int</span><span class="sxs-lookup"><span data-stu-id="8dce5-123">int</span></span></p></td>
<td><p><span data-ttu-id="8dce5-124">Foreign</span><span class="sxs-lookup"><span data-stu-id="8dce5-124">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8dce5-125">發話者的 <strong>PhoneId</strong>。</span><span class="sxs-lookup"><span data-stu-id="8dce5-125"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="8dce5-126">如需詳細資訊，請參閱 <a href="lync-server-2013-phones-table.md">Lync Server 2013 中</a> 的 [電話] 表格。</span><span class="sxs-lookup"><span data-stu-id="8dce5-126">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="8dce5-127">若非 NULL，且 <strong>FromGatewayId</strong> 亦非 NULL，代表發話者為 PSTN 使用者。</span><span class="sxs-lookup"><span data-stu-id="8dce5-127">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dce5-128"><strong>ConnectedNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="8dce5-128"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="8dce5-129">int</span><span class="sxs-lookup"><span data-stu-id="8dce5-129">int</span></span></p></td>
<td><p><span data-ttu-id="8dce5-130">Foreign</span><span class="sxs-lookup"><span data-stu-id="8dce5-130">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8dce5-131">受話者的 <strong>PhoneId</strong>。</span><span class="sxs-lookup"><span data-stu-id="8dce5-131"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="8dce5-132">如需詳細資訊，請參閱 <a href="lync-server-2013-phones-table.md">Lync Server 2013 中</a> 的 [電話] 表格。</span><span class="sxs-lookup"><span data-stu-id="8dce5-132">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="8dce5-133">若非 NULL，且 <strong>ToGatewayId</strong> 亦非 NULL，代表受話者為 PSTN 使用者。</span><span class="sxs-lookup"><span data-stu-id="8dce5-133">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dce5-134"><strong>FromMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="8dce5-134"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="8dce5-135">int</span><span class="sxs-lookup"><span data-stu-id="8dce5-135">int</span></span></p></td>
<td><p><span data-ttu-id="8dce5-136">Foreign</span><span class="sxs-lookup"><span data-stu-id="8dce5-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8dce5-137">通話的來源中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="8dce5-137">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="8dce5-138">如需詳細資訊，請參閱 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="8dce5-138">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dce5-139"><strong>ToMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="8dce5-139"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="8dce5-140">int</span><span class="sxs-lookup"><span data-stu-id="8dce5-140">int</span></span></p></td>
<td><p><span data-ttu-id="8dce5-141">Foreign</span><span class="sxs-lookup"><span data-stu-id="8dce5-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8dce5-142">通話的目標中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="8dce5-142">The Mediation Server called is going to.</span></span> <span data-ttu-id="8dce5-143">如需詳細資訊，請參閱 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="8dce5-143">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dce5-144"><strong>FromGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="8dce5-144"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="8dce5-145">int</span><span class="sxs-lookup"><span data-stu-id="8dce5-145">int</span></span></p></td>
<td><p><span data-ttu-id="8dce5-146">Foreign</span><span class="sxs-lookup"><span data-stu-id="8dce5-146">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8dce5-147">通話的來源閘道。</span><span class="sxs-lookup"><span data-stu-id="8dce5-147">Gateway the call is coming from.</span></span> <span data-ttu-id="8dce5-148">如需詳細資訊，請參閱 <a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的閘道表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="8dce5-148">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dce5-149"><strong>ToGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="8dce5-149"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="8dce5-150">int</span><span class="sxs-lookup"><span data-stu-id="8dce5-150">int</span></span></p></td>
<td><p><span data-ttu-id="8dce5-151">Foreign</span><span class="sxs-lookup"><span data-stu-id="8dce5-151">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8dce5-152">通話的目標閘道。</span><span class="sxs-lookup"><span data-stu-id="8dce5-152">Gateway the call is going to.</span></span> <span data-ttu-id="8dce5-153">如需詳細資訊，請參閱 <a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的閘道表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="8dce5-153">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dce5-154"><strong>DisconnectedbyURIId</strong></span><span class="sxs-lookup"><span data-stu-id="8dce5-154"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="8dce5-155">int</span><span class="sxs-lookup"><span data-stu-id="8dce5-155">int</span></span></p></td>
<td><p><span data-ttu-id="8dce5-156">Foreign</span><span class="sxs-lookup"><span data-stu-id="8dce5-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8dce5-157">中斷通話之使用者的 URI (若該使用者有 URI 的話)。</span><span class="sxs-lookup"><span data-stu-id="8dce5-157">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="8dce5-158">如需詳細資訊，請參閱 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="8dce5-158">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dce5-159"><strong>DisconnectedbyPhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="8dce5-159"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="8dce5-160">int</span><span class="sxs-lookup"><span data-stu-id="8dce5-160">int</span></span></p></td>
<td><p><span data-ttu-id="8dce5-161">Foreign</span><span class="sxs-lookup"><span data-stu-id="8dce5-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8dce5-162">中斷通話之電話的識別碼 (若通話是從電話所中斷的話)。</span><span class="sxs-lookup"><span data-stu-id="8dce5-162">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="8dce5-163">如需詳細資訊，請參閱 <a href="lync-server-2013-phones-table.md">Lync Server 2013 中</a> 的 [電話] 表格。</span><span class="sxs-lookup"><span data-stu-id="8dce5-163">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

