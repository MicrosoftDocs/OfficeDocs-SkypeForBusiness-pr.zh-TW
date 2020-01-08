---
title: Lync Server 2013：SessionDetails 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SessionDetails table
ms:assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398589(v=OCS.15)
ms:contentKeyID: 48184559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faebef9ad03370c2fa969d3b119f13b88d1d3173
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977274"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="4ead1-102">Lync Server 2013 中的 SessionDetails 表格</span><span class="sxs-lookup"><span data-stu-id="4ead1-102">SessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ead1-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="4ead1-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="4ead1-104">每個記錄代表一個點對點工作階段，這可能是 VoIP VoIP 通話、兩方 IM 會話或其他類型的會話。</span><span class="sxs-lookup"><span data-stu-id="4ead1-104">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="4ead1-105">您可以[在 Lync Server 2013 中使用媒體資料表](lync-server-2013-media-table.md)加入表格，以尋找此會話中所涉及之每個媒體的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="4ead1-105">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="4ead1-106">請注意，IsUser1IntegratedWithDeskPhone 和 IsUser2IntegratedWithDeskPhone 欄位已從 Microsoft Lync Server 2013 中使用的 SessionDetails 資料表中刪除。</span><span class="sxs-lookup"><span data-stu-id="4ead1-106">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4ead1-107">左欄</span><span class="sxs-lookup"><span data-stu-id="4ead1-107">Column</span></span></th>
<th><span data-ttu-id="4ead1-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="4ead1-108">Data Type</span></span></th>
<th><span data-ttu-id="4ead1-109">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="4ead1-109">Key/Index</span></span></th>
<th><span data-ttu-id="4ead1-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="4ead1-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4ead1-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="4ead1-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4ead1-112">datetime</span><span class="sxs-lookup"><span data-stu-id="4ead1-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="4ead1-113">主要、外部</span><span class="sxs-lookup"><span data-stu-id="4ead1-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ead1-114">會話要求的時間。</span><span class="sxs-lookup"><span data-stu-id="4ead1-114">Time of session request.</span></span> <span data-ttu-id="4ead1-115">與<strong>SessionIdSeq</strong>搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="4ead1-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="4ead1-116">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="4ead1-116">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ead1-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="4ead1-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4ead1-118">int</span><span class="sxs-lookup"><span data-stu-id="4ead1-118">int</span></span></p></td>
<td><p><span data-ttu-id="4ead1-119">主要、外部</span><span class="sxs-lookup"><span data-stu-id="4ead1-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ead1-120">識別會話的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="4ead1-120">ID number to identify the session.</span></span> <span data-ttu-id="4ead1-121">與<strong>SessionIdTime</strong>搭配使用，以唯一識別會話。 \* 如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="4ead1-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ead1-122"><strong>Id</strong></span><span class="sxs-lookup"><span data-stu-id="4ead1-122"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="4ead1-123">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="4ead1-123">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4ead1-124">要關聯多個會話的 GUID。</span><span class="sxs-lookup"><span data-stu-id="4ead1-124">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ead1-125"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="4ead1-125"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4ead1-126">datetime</span><span class="sxs-lookup"><span data-stu-id="4ead1-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="4ead1-127">外</span><span class="sxs-lookup"><span data-stu-id="4ead1-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ead1-128">[識別碼] 編號，找出目前會話所取代的對話方塊。</span><span class="sxs-lookup"><span data-stu-id="4ead1-128">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="4ead1-129">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="4ead1-129">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ead1-130"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="4ead1-130"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4ead1-131">int</span><span class="sxs-lookup"><span data-stu-id="4ead1-131">int</span></span></p></td>
<td><p><span data-ttu-id="4ead1-132">外</span><span class="sxs-lookup"><span data-stu-id="4ead1-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ead1-133">識別會話的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="4ead1-133">ID number to identify the session.</span></span> <span data-ttu-id="4ead1-134">與<strong>ReplacesDialogIdTime</strong>搭配使用，可唯一識別此會話所取代的會話。</span><span class="sxs-lookup"><span data-stu-id="4ead1-134">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="4ead1-135">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="4ead1-135">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ead1-136"><strong>User1Id</strong></span><span class="sxs-lookup"><span data-stu-id="4ead1-136"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="4ead1-137">int</span><span class="sxs-lookup"><span data-stu-id="4ead1-137">int</span></span></p></td>
<td><p><span data-ttu-id="4ead1-138">外</span><span class="sxs-lookup"><span data-stu-id="4ead1-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ead1-139">會話中一個使用者的 ID。</span><span class="sxs-lookup"><span data-stu-id="4ead1-139">ID of one user in the session.</span></span> <span data-ttu-id="4ead1-140">如需詳細資訊，請參閱<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 [使用者] 資料表。</span><span class="sxs-lookup"><span data-stu-id="4ead1-140">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ead1-141"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="4ead1-141"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="4ead1-142">int</span><span class="sxs-lookup"><span data-stu-id="4ead1-142">int</span></span></p></td>
<td><p><span data-ttu-id="4ead1-143">外</span><span class="sxs-lookup"><span data-stu-id="4ead1-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ead1-144">會話中其他使用者的 ID。</span><span class="sxs-lookup"><span data-stu-id="4ead1-144">ID of the other user in the session.</span></span> <span data-ttu-id="4ead1-145">如需詳細資訊，請參閱<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 [使用者] 資料表。</span><span class="sxs-lookup"><span data-stu-id="4ead1-145">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ead1-146"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="4ead1-146"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="4ead1-147">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="4ead1-147">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4ead1-148">識別會話中第一個使用者所使用端點的 GUID。</span><span class="sxs-lookup"><span data-stu-id="4ead1-148">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="4ead1-149">此欄位是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="4ead1-149">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ead1-150"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="4ead1-150"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="4ead1-151">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="4ead1-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4ead1-152">GUID，可識別會話中第二位使用者使用的端點。</span><span class="sxs-lookup"><span data-stu-id="4ead1-152">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="4ead1-153">此欄位是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="4ead1-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ead1-154"><strong>TargetUserId</strong></span><span class="sxs-lookup"><span data-stu-id="4ead1-154"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="4ead1-155">int</span><span class="sxs-lookup"><span data-stu-id="4ead1-155">int</span></span></p></td>
<td><p><span data-ttu-id="4ead1-156">外</span><span class="sxs-lookup"><span data-stu-id="4ead1-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ead1-157">SIP 要求中的原始使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="4ead1-157">The original To user URI in the SIP request.</span></span> <span data-ttu-id="4ead1-158">如需詳細資訊，請參閱<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 [使用者] 資料表。</span><span class="sxs-lookup"><span data-stu-id="4ead1-158">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ead1-159"><strong>SessionStartedById</strong></span><span class="sxs-lookup"><span data-stu-id="4ead1-159"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="4ead1-160">int</span><span class="sxs-lookup"><span data-stu-id="4ead1-160">int</span></span></p></td>
<td><p><span data-ttu-id="4ead1-161">外</span><span class="sxs-lookup"><span data-stu-id="4ead1-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ead1-162">啟動會話的使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="4ead1-162">ID of the user who started the session.</span></span> <span data-ttu-id="4ead1-163">如需詳細資訊，請參閱<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 [使用者] 資料表。</span><span class="sxs-lookup"><span data-stu-id="4ead1-163">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ead1-164"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="4ead1-164"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="4ead1-165">int</span><span class="sxs-lookup"><span data-stu-id="4ead1-165">int</span></span></p></td>
<td><p><span data-ttu-id="4ead1-166">外</span><span class="sxs-lookup"><span data-stu-id="4ead1-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ead1-167">表示呼叫者代表者的使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="4ead1-167">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="4ead1-168">如需詳細資訊，請參閱<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 [使用者] 資料表。</span><span class="sxs-lookup"><span data-stu-id="4ead1-168">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ead1-169"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="4ead1-169"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="4ead1-170">int</span><span class="sxs-lookup"><span data-stu-id="4ead1-170">int</span></span></p></td>
<td><p><span data-ttu-id="4ead1-171">外</span><span class="sxs-lookup"><span data-stu-id="4ead1-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ead1-172">呼叫者的使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="4ead1-172">ID of the user by who the call is referred.</span></span> <span data-ttu-id="4ead1-173">如需詳細資訊，請參閱<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 [使用者] 資料表。</span><span class="sxs-lookup"><span data-stu-id="4ead1-173">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ead1-174"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="4ead1-174"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="4ead1-175">int</span><span class="sxs-lookup"><span data-stu-id="4ead1-175">int</span></span></p></td>
<td><p><span data-ttu-id="4ead1-176">外</span><span class="sxs-lookup"><span data-stu-id="4ead1-176">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ead1-177">此會話所用的前端伺服器 ID。</span><span class="sxs-lookup"><span data-stu-id="4ead1-177">ID of the front-end server used for this session.</span></span> <span data-ttu-id="4ead1-178">如需詳細資訊，請參閱<a href="lync-server-2013-servers-table.md">Lync Server 2013 中</a>的 [伺服器] 資料表。</span><span class="sxs-lookup"><span data-stu-id="4ead1-178">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ead1-179"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="4ead1-179"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="4ead1-180">int</span><span class="sxs-lookup"><span data-stu-id="4ead1-180">int</span></span></p></td>
<td><p><span data-ttu-id="4ead1-181">外</span><span class="sxs-lookup"><span data-stu-id="4ead1-181">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ead1-182">捕獲會話的池 ID。</span><span class="sxs-lookup"><span data-stu-id="4ead1-182">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="4ead1-183">如需詳細資訊，請參閱<a href="lync-server-2013-pools-table.md">Lync Server 2013 中</a>的 [pool] 資料表。</span><span class="sxs-lookup"><span data-stu-id="4ead1-183">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ead1-184"><strong>ContentTypeID</strong></span><span class="sxs-lookup"><span data-stu-id="4ead1-184"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="4ead1-185">int</span><span class="sxs-lookup"><span data-stu-id="4ead1-185">int</span></span></p></td>
<td><p><span data-ttu-id="4ead1-186">外</span><span class="sxs-lookup"><span data-stu-id="4ead1-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ead1-187">會話中使用的內容類型。</span><span class="sxs-lookup"><span data-stu-id="4ead1-187">Content type used in the session.</span></span> <span data-ttu-id="4ead1-188">如需詳細資訊，請參閱<a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 中</a>的 [主控] 資料表。</span><span class="sxs-lookup"><span data-stu-id="4ead1-188">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ead1-189"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="4ead1-189"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="4ead1-190">int</span><span class="sxs-lookup"><span data-stu-id="4ead1-190">int</span></span></p></td>
<td><p><span data-ttu-id="4ead1-191">外</span><span class="sxs-lookup"><span data-stu-id="4ead1-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ead1-192">[User1] 使用的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="4ead1-192">Client version used by User1.</span></span> <span data-ttu-id="4ead1-193">如需詳細資訊，請參閱<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中</a>的 [ClientVersions] 資料表。</span><span class="sxs-lookup"><span data-stu-id="4ead1-193">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ead1-194"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="4ead1-194"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="4ead1-195">int</span><span class="sxs-lookup"><span data-stu-id="4ead1-195">int</span></span></p></td>
<td><p><span data-ttu-id="4ead1-196">外</span><span class="sxs-lookup"><span data-stu-id="4ead1-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ead1-197">由者使用的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="4ead1-197">Client version used by User2.</span></span> <span data-ttu-id="4ead1-198">如需詳細資訊，請參閱<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中</a>的 [ClientVersions] 資料表。</span><span class="sxs-lookup"><span data-stu-id="4ead1-198">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ead1-199"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="4ead1-199"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="4ead1-200">int</span><span class="sxs-lookup"><span data-stu-id="4ead1-200">int</span></span></p></td>
<td><p><span data-ttu-id="4ead1-201">外</span><span class="sxs-lookup"><span data-stu-id="4ead1-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ead1-202">[User1] 使用的邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="4ead1-202">Edge Server used by User1.</span></span> <span data-ttu-id="4ead1-203">如需詳細資訊，請參閱<a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中</a>的 [EdgeServers] 資料表。</span><span class="sxs-lookup"><span data-stu-id="4ead1-203">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ead1-204"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="4ead1-204"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="4ead1-205">int</span><span class="sxs-lookup"><span data-stu-id="4ead1-205">int</span></span></p></td>
<td><p><span data-ttu-id="4ead1-206">外</span><span class="sxs-lookup"><span data-stu-id="4ead1-206">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ead1-207">由者使用的邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="4ead1-207">Edge Server used by User2.</span></span> <span data-ttu-id="4ead1-208">如需詳細資訊，請參閱<a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中</a>的 [EdgeServers] 資料表。</span><span class="sxs-lookup"><span data-stu-id="4ead1-208">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ead1-209"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="4ead1-209"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="4ead1-210">稍微</span><span class="sxs-lookup"><span data-stu-id="4ead1-210">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4ead1-211">User1 是否已從內部登入。</span><span class="sxs-lookup"><span data-stu-id="4ead1-211">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ead1-212"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="4ead1-212"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="4ead1-213">稍微</span><span class="sxs-lookup"><span data-stu-id="4ead1-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4ead1-214">您是否已從內部或非登入</span><span class="sxs-lookup"><span data-stu-id="4ead1-214">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ead1-215"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="4ead1-215"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4ead1-216">datetime</span><span class="sxs-lookup"><span data-stu-id="4ead1-216">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4ead1-217">第一次邀請要求的時間。</span><span class="sxs-lookup"><span data-stu-id="4ead1-217">The time of the first INVITE request.</span></span> <span data-ttu-id="4ead1-218">這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。</span><span class="sxs-lookup"><span data-stu-id="4ead1-218">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="4ead1-219">如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。</span><span class="sxs-lookup"><span data-stu-id="4ead1-219">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="4ead1-220">這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。</span><span class="sxs-lookup"><span data-stu-id="4ead1-220">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="4ead1-221">如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。</span><span class="sxs-lookup"><span data-stu-id="4ead1-221">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ead1-222"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="4ead1-222"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4ead1-223">datetime</span><span class="sxs-lookup"><span data-stu-id="4ead1-223">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4ead1-224">回應第一個邀請訊息的時間。</span><span class="sxs-lookup"><span data-stu-id="4ead1-224">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="4ead1-225">這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。</span><span class="sxs-lookup"><span data-stu-id="4ead1-225">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="4ead1-226">如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。</span><span class="sxs-lookup"><span data-stu-id="4ead1-226">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ead1-227"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="4ead1-227"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="4ead1-228">int</span><span class="sxs-lookup"><span data-stu-id="4ead1-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4ead1-229">SIP 回應程式碼加入會話邀請。</span><span class="sxs-lookup"><span data-stu-id="4ead1-229">SIP response code to the session invitation.</span></span> <span data-ttu-id="4ead1-230">這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。</span><span class="sxs-lookup"><span data-stu-id="4ead1-230">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="4ead1-231">如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。</span><span class="sxs-lookup"><span data-stu-id="4ead1-231">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ead1-232"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="4ead1-232"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="4ead1-233">int</span><span class="sxs-lookup"><span data-stu-id="4ead1-233">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4ead1-234">從 SIP 標頭捕獲的診斷 ID。</span><span class="sxs-lookup"><span data-stu-id="4ead1-234">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ead1-235"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="4ead1-235"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="4ead1-236">int</span><span class="sxs-lookup"><span data-stu-id="4ead1-236">int</span></span></p></td>
<td><p><span data-ttu-id="4ead1-237">外</span><span class="sxs-lookup"><span data-stu-id="4ead1-237">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4ead1-238">通話優先順序。</span><span class="sxs-lookup"><span data-stu-id="4ead1-238">Call priority.</span></span> <span data-ttu-id="4ead1-239">如需詳細資訊，請參閱<a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 中</a>的 [CallPriorities] 資料表。</span><span class="sxs-lookup"><span data-stu-id="4ead1-239">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ead1-240"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="4ead1-240"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="4ead1-241">int</span><span class="sxs-lookup"><span data-stu-id="4ead1-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4ead1-242">在會話期間由 User1 傳送的訊息數目。</span><span class="sxs-lookup"><span data-stu-id="4ead1-242">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ead1-243"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="4ead1-243"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="4ead1-244">int</span><span class="sxs-lookup"><span data-stu-id="4ead1-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4ead1-245">在會話期間由方法2傳送的訊息數目。</span><span class="sxs-lookup"><span data-stu-id="4ead1-245">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ead1-246"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="4ead1-246"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4ead1-247">datetime</span><span class="sxs-lookup"><span data-stu-id="4ead1-247">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4ead1-248">會話結束時的時間。</span><span class="sxs-lookup"><span data-stu-id="4ead1-248">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ead1-249"><strong>MediaTypes</strong></span><span class="sxs-lookup"><span data-stu-id="4ead1-249"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="4ead1-250">int</span><span class="sxs-lookup"><span data-stu-id="4ead1-250">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4ead1-251">一個位組，指明此會話的媒體類型。</span><span class="sxs-lookup"><span data-stu-id="4ead1-251">A bit set that indicates the media type of this session.</span></span> <span data-ttu-id="4ead1-252">所列的是以下類型的定義：</span><span class="sxs-lookup"><span data-stu-id="4ead1-252">Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4ead1-253">IM</span><span class="sxs-lookup"><span data-stu-id="4ead1-253">IM</span></span></p></td>
<td><p><span data-ttu-id="4ead1-254">1</span><span class="sxs-lookup"><span data-stu-id="4ead1-254">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ead1-255">FILE_TRANSFER</span><span class="sxs-lookup"><span data-stu-id="4ead1-255">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="4ead1-256">pplx-2</span><span class="sxs-lookup"><span data-stu-id="4ead1-256">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ead1-257">REMOTE_ASSISTANCE</span><span class="sxs-lookup"><span data-stu-id="4ead1-257">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="4ead1-258">4</span><span class="sxs-lookup"><span data-stu-id="4ead1-258">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ead1-259">APP_SHARING</span><span class="sxs-lookup"><span data-stu-id="4ead1-259">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="4ead1-260">型</span><span class="sxs-lookup"><span data-stu-id="4ead1-260">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ead1-261">音訊</span><span class="sxs-lookup"><span data-stu-id="4ead1-261">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="4ead1-262">位</span><span class="sxs-lookup"><span data-stu-id="4ead1-262">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ead1-263">顯示器</span><span class="sxs-lookup"><span data-stu-id="4ead1-263">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="4ead1-264">32</span><span class="sxs-lookup"><span data-stu-id="4ead1-264">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ead1-265">APP_INVITE</span><span class="sxs-lookup"><span data-stu-id="4ead1-265">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="4ead1-266">64</span><span class="sxs-lookup"><span data-stu-id="4ead1-266">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ead1-267"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="4ead1-267"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="4ead1-268">Smallint</span><span class="sxs-lookup"><span data-stu-id="4ead1-268">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4ead1-269">指示 User1 屬性的位組。</span><span class="sxs-lookup"><span data-stu-id="4ead1-269">A bit set that indicates the User1 attributes.</span></span> <span data-ttu-id="4ead1-270">下列屬性定義如下所示：</span><span class="sxs-lookup"><span data-stu-id="4ead1-270">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="4ead1-271">0x01-與桌面電話整合</span><span class="sxs-lookup"><span data-stu-id="4ead1-271">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ead1-272"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="4ead1-272"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="4ead1-273">Smallint</span><span class="sxs-lookup"><span data-stu-id="4ead1-273">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4ead1-274">指示使用2屬性的位組。</span><span class="sxs-lookup"><span data-stu-id="4ead1-274">A bit set that indicates the User2 attributes.</span></span> <span data-ttu-id="4ead1-275">下列屬性定義如下所示：</span><span class="sxs-lookup"><span data-stu-id="4ead1-275">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="4ead1-276">0x01-與桌面電話整合</span><span class="sxs-lookup"><span data-stu-id="4ead1-276">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ead1-277"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="4ead1-277"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="4ead1-278">Smallint</span><span class="sxs-lookup"><span data-stu-id="4ead1-278">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4ead1-279">指明通話屬性的位組。</span><span class="sxs-lookup"><span data-stu-id="4ead1-279">A bit set that indicates the call attributes.</span></span> <span data-ttu-id="4ead1-280">下列屬性定義如下所示：</span><span class="sxs-lookup"><span data-stu-id="4ead1-280">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="4ead1-281">0x01-重新嘗試會話</span><span class="sxs-lookup"><span data-stu-id="4ead1-281">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="4ead1-282">0x02-代理代表回應群組所做的通話</span><span class="sxs-lookup"><span data-stu-id="4ead1-282">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ead1-283"><strong>預處理</strong></span><span class="sxs-lookup"><span data-stu-id="4ead1-283"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="4ead1-284">稍微</span><span class="sxs-lookup"><span data-stu-id="4ead1-284">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4ead1-285">供監視服務內部使用。</span><span class="sxs-lookup"><span data-stu-id="4ead1-285">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="4ead1-286">此欄位是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="4ead1-286">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4ead1-287">\*在大部分的會話中，SessionIdSeq 將會有1的值。</span><span class="sxs-lookup"><span data-stu-id="4ead1-287">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="4ead1-288">如果多個會話的開始時間完全相同，則 SessionIdSeq 會是1，另一個會是2，依此類推。</span><span class="sxs-lookup"><span data-stu-id="4ead1-288">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

