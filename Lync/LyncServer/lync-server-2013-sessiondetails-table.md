---
title: Lync Server 2013： SessionDetails 表格
description: Lync Server 2013： SessionDetails 表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionDetails table
ms:assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398589(v=OCS.15)
ms:contentKeyID: 48184559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd927f784fb0f2a835c896824105fe8bb112c7a1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569929"
---
# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="69780-103">Lync Server 2013 中的 SessionDetails 表格</span><span class="sxs-lookup"><span data-stu-id="69780-103">SessionDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69780-104">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="69780-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="69780-105">每筆記錄代表一個對等工作階段，可以是 VoIP 對 VoIP 電話、雙方 IM 工作階段或其他工作階段類型。</span><span class="sxs-lookup"><span data-stu-id="69780-105">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="69780-106">您可以對 [Lync Server 2013 中的媒體表](lync-server-2013-media-table.md) 執行表格加入，以找出此會話中所涉及之每個媒體的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="69780-106">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="69780-107">請注意，IsUser1IntegratedWithDeskPhone 和 IsUser2IntegratedWithDeskPhone 欄位已經從 Microsoft Lync Server 2013 中使用的 SessionDetails 表格中刪除。</span><span class="sxs-lookup"><span data-stu-id="69780-107">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69780-108">欄</span><span class="sxs-lookup"><span data-stu-id="69780-108">Column</span></span></th>
<th><span data-ttu-id="69780-109">資料類型</span><span class="sxs-lookup"><span data-stu-id="69780-109">Data Type</span></span></th>
<th><span data-ttu-id="69780-110">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="69780-110">Key/Index</span></span></th>
<th><span data-ttu-id="69780-111">詳細資料</span><span class="sxs-lookup"><span data-stu-id="69780-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69780-112"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="69780-112"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="69780-113">datetime</span><span class="sxs-lookup"><span data-stu-id="69780-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="69780-114">主要，外部</span><span class="sxs-lookup"><span data-stu-id="69780-114">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="69780-115">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="69780-115">Time of session request.</span></span> <span data-ttu-id="69780-116">其會與 <strong>SessionIdSeq</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="69780-116">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="69780-117">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="69780-117">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69780-118"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="69780-118"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="69780-119">int</span><span class="sxs-lookup"><span data-stu-id="69780-119">int</span></span></p></td>
<td><p><span data-ttu-id="69780-120">主要，外部</span><span class="sxs-lookup"><span data-stu-id="69780-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="69780-121">用來識別工作階段的識別碼。</span><span class="sxs-lookup"><span data-stu-id="69780-121">ID number to identify the session.</span></span> <span data-ttu-id="69780-122">與 <strong>SessionIdTime</strong> 搭配使用，以唯一識別會話。 \* 如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="69780-122">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69780-123"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="69780-123"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="69780-124">唯一</span><span class="sxs-lookup"><span data-stu-id="69780-124">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69780-125">與多個工作階段相互關聯的 GUID。</span><span class="sxs-lookup"><span data-stu-id="69780-125">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69780-126"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="69780-126"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="69780-127">datetime</span><span class="sxs-lookup"><span data-stu-id="69780-127">datetime</span></span></p></td>
<td><p><span data-ttu-id="69780-128">Foreign</span><span class="sxs-lookup"><span data-stu-id="69780-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69780-129">用來識別目前工作階段所取代之對話的識別碼。</span><span class="sxs-lookup"><span data-stu-id="69780-129">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="69780-130">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="69780-130">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69780-131"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="69780-131"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="69780-132">int</span><span class="sxs-lookup"><span data-stu-id="69780-132">int</span></span></p></td>
<td><p><span data-ttu-id="69780-133">Foreign</span><span class="sxs-lookup"><span data-stu-id="69780-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69780-134">用來識別工作階段的識別碼。</span><span class="sxs-lookup"><span data-stu-id="69780-134">ID number to identify the session.</span></span> <span data-ttu-id="69780-135">其會與 <strong>ReplacesDialogIdTime</strong> 搭配使用，專門用於識別此工作階段所取代的工作階段。</span><span class="sxs-lookup"><span data-stu-id="69780-135">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="69780-136">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="69780-136">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69780-137"><strong>User1Id</strong></span><span class="sxs-lookup"><span data-stu-id="69780-137"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="69780-138">int</span><span class="sxs-lookup"><span data-stu-id="69780-138">int</span></span></p></td>
<td><p><span data-ttu-id="69780-139">Foreign</span><span class="sxs-lookup"><span data-stu-id="69780-139">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69780-140">工作階段中某位使用者的識別碼。</span><span class="sxs-lookup"><span data-stu-id="69780-140">ID of one user in the session.</span></span> <span data-ttu-id="69780-141">如需詳細資訊，請參閱 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="69780-141">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69780-142"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="69780-142"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="69780-143">int</span><span class="sxs-lookup"><span data-stu-id="69780-143">int</span></span></p></td>
<td><p><span data-ttu-id="69780-144">Foreign</span><span class="sxs-lookup"><span data-stu-id="69780-144">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69780-145">工作階段中其他使用者的識別碼。</span><span class="sxs-lookup"><span data-stu-id="69780-145">ID of the other user in the session.</span></span> <span data-ttu-id="69780-146">如需詳細資訊，請參閱 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="69780-146">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69780-147"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="69780-147"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="69780-148">唯一</span><span class="sxs-lookup"><span data-stu-id="69780-148">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69780-149">識別工作階段中第一位使用者所使用之端點的 GUID。</span><span class="sxs-lookup"><span data-stu-id="69780-149">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="69780-150">此欄位是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="69780-150">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69780-151"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="69780-151"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="69780-152">唯一</span><span class="sxs-lookup"><span data-stu-id="69780-152">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69780-153">識別工作階段中第二位使用者所使用之端點的 GUID。</span><span class="sxs-lookup"><span data-stu-id="69780-153">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="69780-154">此欄位是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="69780-154">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69780-155"><strong>TargetUserId</strong></span><span class="sxs-lookup"><span data-stu-id="69780-155"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="69780-156">int</span><span class="sxs-lookup"><span data-stu-id="69780-156">int</span></span></p></td>
<td><p><span data-ttu-id="69780-157">Foreign</span><span class="sxs-lookup"><span data-stu-id="69780-157">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69780-158">SIP 要求中原始的目標使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="69780-158">The original To user URI in the SIP request.</span></span> <span data-ttu-id="69780-159">如需詳細資訊，請參閱 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="69780-159">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69780-160"><strong>SessionStartedById</strong></span><span class="sxs-lookup"><span data-stu-id="69780-160"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="69780-161">int</span><span class="sxs-lookup"><span data-stu-id="69780-161">int</span></span></p></td>
<td><p><span data-ttu-id="69780-162">Foreign</span><span class="sxs-lookup"><span data-stu-id="69780-162">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69780-163">起始工作階段之使用者的識別碼。</span><span class="sxs-lookup"><span data-stu-id="69780-163">ID of the user who started the session.</span></span> <span data-ttu-id="69780-164">如需詳細資訊，請參閱 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="69780-164">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69780-165"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="69780-165"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="69780-166">int</span><span class="sxs-lookup"><span data-stu-id="69780-166">int</span></span></p></td>
<td><p><span data-ttu-id="69780-167">Foreign</span><span class="sxs-lookup"><span data-stu-id="69780-167">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69780-168">指出來電者所代表之使用者的識別碼。</span><span class="sxs-lookup"><span data-stu-id="69780-168">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="69780-169">如需詳細資訊，請參閱 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="69780-169">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69780-170"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="69780-170"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="69780-171">int</span><span class="sxs-lookup"><span data-stu-id="69780-171">int</span></span></p></td>
<td><p><span data-ttu-id="69780-172">Foreign</span><span class="sxs-lookup"><span data-stu-id="69780-172">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69780-173">轉接此通話之使用者的識別碼。</span><span class="sxs-lookup"><span data-stu-id="69780-173">ID of the user by who the call is referred.</span></span> <span data-ttu-id="69780-174">如需詳細資訊，請參閱 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="69780-174">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69780-175"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="69780-175"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="69780-176">int</span><span class="sxs-lookup"><span data-stu-id="69780-176">int</span></span></p></td>
<td><p><span data-ttu-id="69780-177">Foreign</span><span class="sxs-lookup"><span data-stu-id="69780-177">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69780-178">用於此工作階段之前端伺服器的識別碼。</span><span class="sxs-lookup"><span data-stu-id="69780-178">ID of the front-end server used for this session.</span></span> <span data-ttu-id="69780-179">如需詳細資訊，請參閱 <a href="lync-server-2013-servers-table.md">Lync Server 2013 中的 Servers 資料表</a> 。</span><span class="sxs-lookup"><span data-stu-id="69780-179">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69780-180"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="69780-180"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="69780-181">int</span><span class="sxs-lookup"><span data-stu-id="69780-181">int</span></span></p></td>
<td><p><span data-ttu-id="69780-182">Foreign</span><span class="sxs-lookup"><span data-stu-id="69780-182">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69780-183">擷取工作階段所在集區的識別碼。</span><span class="sxs-lookup"><span data-stu-id="69780-183">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="69780-184">如需詳細資訊，請參閱 <a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 pool 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="69780-184">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69780-185"><strong>ContentTypeID</strong></span><span class="sxs-lookup"><span data-stu-id="69780-185"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="69780-186">int</span><span class="sxs-lookup"><span data-stu-id="69780-186">int</span></span></p></td>
<td><p><span data-ttu-id="69780-187">Foreign</span><span class="sxs-lookup"><span data-stu-id="69780-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69780-188">工作階段中所使用的內容類型。</span><span class="sxs-lookup"><span data-stu-id="69780-188">Content type used in the session.</span></span> <span data-ttu-id="69780-189">如需詳細資訊，請參閱 <a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 中的 ContentTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="69780-189">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69780-190"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="69780-190"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="69780-191">int</span><span class="sxs-lookup"><span data-stu-id="69780-191">int</span></span></p></td>
<td><p><span data-ttu-id="69780-192">Foreign</span><span class="sxs-lookup"><span data-stu-id="69780-192">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69780-193">使用者1 所使用的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="69780-193">Client version used by User1.</span></span> <span data-ttu-id="69780-194">如需詳細資訊，請參閱 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="69780-194">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69780-195"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="69780-195"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="69780-196">int</span><span class="sxs-lookup"><span data-stu-id="69780-196">int</span></span></p></td>
<td><p><span data-ttu-id="69780-197">Foreign</span><span class="sxs-lookup"><span data-stu-id="69780-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69780-198">使用者2 所使用的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="69780-198">Client version used by User2.</span></span> <span data-ttu-id="69780-199">如需詳細資訊，請參閱 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="69780-199">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69780-200"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="69780-200"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="69780-201">int</span><span class="sxs-lookup"><span data-stu-id="69780-201">int</span></span></p></td>
<td><p><span data-ttu-id="69780-202">Foreign</span><span class="sxs-lookup"><span data-stu-id="69780-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69780-203">使用者 1 所使用的 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="69780-203">Edge Server used by User1.</span></span> <span data-ttu-id="69780-204">如需詳細資訊，請參閱 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="69780-204">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69780-205"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="69780-205"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="69780-206">int</span><span class="sxs-lookup"><span data-stu-id="69780-206">int</span></span></p></td>
<td><p><span data-ttu-id="69780-207">Foreign</span><span class="sxs-lookup"><span data-stu-id="69780-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69780-208">使用者 2 所使用的 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="69780-208">Edge Server used by User2.</span></span> <span data-ttu-id="69780-209">如需詳細資訊，請參閱 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="69780-209">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69780-210"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="69780-210"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="69780-211">位</span><span class="sxs-lookup"><span data-stu-id="69780-211">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69780-212">使用者 1 是否由內部登入。</span><span class="sxs-lookup"><span data-stu-id="69780-212">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69780-213"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="69780-213"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="69780-214">位</span><span class="sxs-lookup"><span data-stu-id="69780-214">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69780-215">使用者 2 是否由內部登入。</span><span class="sxs-lookup"><span data-stu-id="69780-215">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69780-216"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="69780-216"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="69780-217">datetime</span><span class="sxs-lookup"><span data-stu-id="69780-217">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69780-218">第一個 INVITE 要求的時間。</span><span class="sxs-lookup"><span data-stu-id="69780-218">The time of the first INVITE request.</span></span> <span data-ttu-id="69780-219">此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。</span><span class="sxs-lookup"><span data-stu-id="69780-219">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="69780-220">如果沒有 INVITE 訊息，則會使用第一個相關 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="69780-220">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="69780-221">此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。</span><span class="sxs-lookup"><span data-stu-id="69780-221">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="69780-222">如果沒有 INVITE 訊息，則會使用第一個相關 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="69780-222">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69780-223"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="69780-223"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="69780-224">datetime</span><span class="sxs-lookup"><span data-stu-id="69780-224">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69780-225">回應第一個 INVITE 訊息的時間。</span><span class="sxs-lookup"><span data-stu-id="69780-225">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="69780-226">此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。</span><span class="sxs-lookup"><span data-stu-id="69780-226">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="69780-227">如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="69780-227">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69780-228"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="69780-228"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="69780-229">int</span><span class="sxs-lookup"><span data-stu-id="69780-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69780-p121">工作階段邀請的 SIP 回應碼。此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="69780-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69780-233"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="69780-233"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="69780-234">int</span><span class="sxs-lookup"><span data-stu-id="69780-234">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69780-235">從 SIP 標頭擷取而來的診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="69780-235">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69780-236"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="69780-236"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="69780-237">int</span><span class="sxs-lookup"><span data-stu-id="69780-237">int</span></span></p></td>
<td><p><span data-ttu-id="69780-238">Foreign</span><span class="sxs-lookup"><span data-stu-id="69780-238">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69780-239">通話優先順序。</span><span class="sxs-lookup"><span data-stu-id="69780-239">Call priority.</span></span> <span data-ttu-id="69780-240">如需詳細資訊，請參閱 <a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 中的 CallPriorities 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="69780-240">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69780-241"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="69780-241"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="69780-242">int</span><span class="sxs-lookup"><span data-stu-id="69780-242">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69780-243">工作階段期間使用者 1 所傳送的訊息數。</span><span class="sxs-lookup"><span data-stu-id="69780-243">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69780-244"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="69780-244"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="69780-245">int</span><span class="sxs-lookup"><span data-stu-id="69780-245">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69780-246">工作階段期間使用者 2 所傳送的訊息數。</span><span class="sxs-lookup"><span data-stu-id="69780-246">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69780-247"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="69780-247"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="69780-248">datetime</span><span class="sxs-lookup"><span data-stu-id="69780-248">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69780-249">工作階段結束的時間。</span><span class="sxs-lookup"><span data-stu-id="69780-249">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69780-250"><strong>MediaTypes</strong></span><span class="sxs-lookup"><span data-stu-id="69780-250"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="69780-251">int</span><span class="sxs-lookup"><span data-stu-id="69780-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69780-p123">指出此工作階段之媒體類型的位元集。下列為類型的定義：</span><span class="sxs-lookup"><span data-stu-id="69780-p123">A bit set that indicates the media type of this session. Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69780-254">我</span><span class="sxs-lookup"><span data-stu-id="69780-254">IM</span></span></p></td>
<td><p><span data-ttu-id="69780-255">1 </span><span class="sxs-lookup"><span data-stu-id="69780-255">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69780-256">FILE_TRANSFER</span><span class="sxs-lookup"><span data-stu-id="69780-256">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="69780-257">第</span><span class="sxs-lookup"><span data-stu-id="69780-257">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69780-258">REMOTE_ASSISTANCE</span><span class="sxs-lookup"><span data-stu-id="69780-258">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="69780-259">4 </span><span class="sxs-lookup"><span data-stu-id="69780-259">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69780-260">APP_SHARING</span><span class="sxs-lookup"><span data-stu-id="69780-260">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="69780-261">8 </span><span class="sxs-lookup"><span data-stu-id="69780-261">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69780-262">音訊</span><span class="sxs-lookup"><span data-stu-id="69780-262">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="69780-263">16 </span><span class="sxs-lookup"><span data-stu-id="69780-263">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69780-264">視頻</span><span class="sxs-lookup"><span data-stu-id="69780-264">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="69780-265">32</span><span class="sxs-lookup"><span data-stu-id="69780-265">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69780-266">APP_INVITE</span><span class="sxs-lookup"><span data-stu-id="69780-266">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="69780-267">64</span><span class="sxs-lookup"><span data-stu-id="69780-267">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69780-268"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="69780-268"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="69780-269">Smallint</span><span class="sxs-lookup"><span data-stu-id="69780-269">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69780-p124">指出使用者 1 屬性的位元集。下列是屬性的定義：</span><span class="sxs-lookup"><span data-stu-id="69780-p124">A bit set that indicates the User1 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="69780-272">0x01 - 與桌上電話整合</span><span class="sxs-lookup"><span data-stu-id="69780-272">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69780-273"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="69780-273"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="69780-274">Smallint</span><span class="sxs-lookup"><span data-stu-id="69780-274">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69780-p125">指出使用者 2 屬性的位元集。下列是屬性的定義：</span><span class="sxs-lookup"><span data-stu-id="69780-p125">A bit set that indicates the User2 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="69780-277">0x01 - 與桌上電話整合</span><span class="sxs-lookup"><span data-stu-id="69780-277">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69780-278"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="69780-278"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="69780-279">Smallint</span><span class="sxs-lookup"><span data-stu-id="69780-279">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69780-p126">指出通話屬性的位元設定。下列是屬性的定義：</span><span class="sxs-lookup"><span data-stu-id="69780-p126">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="69780-282">0x01 - 重試工作階段 1</span><span class="sxs-lookup"><span data-stu-id="69780-282">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="69780-283">0x02 - 由代理人代替回應群組撥出的通話</span><span class="sxs-lookup"><span data-stu-id="69780-283">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69780-284"><strong>處理</strong></span><span class="sxs-lookup"><span data-stu-id="69780-284"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="69780-285">位</span><span class="sxs-lookup"><span data-stu-id="69780-285">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69780-286">供監控服務內部使用。</span><span class="sxs-lookup"><span data-stu-id="69780-286">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="69780-287">此欄位是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="69780-287">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="69780-288">\* 對於大部分的會話，SessionIdSeq 的值會是1。</span><span class="sxs-lookup"><span data-stu-id="69780-288">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="69780-289">如有多個工作階段的啟動時間完全相同，將只有一個工作階段的 SessionIdSeq 值會是 1，其餘工作階段皆是 2，依此類推。</span><span class="sxs-lookup"><span data-stu-id="69780-289">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

