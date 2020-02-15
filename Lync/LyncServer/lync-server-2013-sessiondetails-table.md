---
title: 'Lync Server 2013: SessionDetails 表格'
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
ms.openlocfilehash: fee9a2f2b59fc523224a778004b5c0beb041a12d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007742"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="69bbd-102">Lync Server 2013 中的 SessionDetails 表格</span><span class="sxs-lookup"><span data-stu-id="69bbd-102">SessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69bbd-103">_**主題上次修改日期：** 2012年-09-28_</span><span class="sxs-lookup"><span data-stu-id="69bbd-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="69bbd-104">每筆記錄代表一個對等工作階段，可以是 VoIP 對 VoIP 電話、雙方 IM 工作階段或其他工作階段類型。</span><span class="sxs-lookup"><span data-stu-id="69bbd-104">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="69bbd-105">您可以執行與[Lync Server 2013 中的媒體資料表格](lync-server-2013-media-table.md)來尋找每個媒體的詳細資料此工作階段相關資料表的聯結。</span><span class="sxs-lookup"><span data-stu-id="69bbd-105">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="69bbd-106">請注意，IsUser1IntegratedWithDeskPhone 和 IsUser2IntegratedWithDeskPhone 欄位已斷線從 Microsoft Lync Server 2013 中使用的 SessionDetails 表格。</span><span class="sxs-lookup"><span data-stu-id="69bbd-106">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69bbd-107">欄</span><span class="sxs-lookup"><span data-stu-id="69bbd-107">Column</span></span></th>
<th><span data-ttu-id="69bbd-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="69bbd-108">Data Type</span></span></th>
<th><span data-ttu-id="69bbd-109">主索引鍵 /</span><span class="sxs-lookup"><span data-stu-id="69bbd-109">Key/Index</span></span></th>
<th><span data-ttu-id="69bbd-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="69bbd-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69bbd-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="69bbd-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="69bbd-112">datetime</span><span class="sxs-lookup"><span data-stu-id="69bbd-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="69bbd-113">主要、外部</span><span class="sxs-lookup"><span data-stu-id="69bbd-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="69bbd-114">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="69bbd-114">Time of session request.</span></span> <span data-ttu-id="69bbd-115">其會與 <strong>SessionIdSeq</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="69bbd-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="69bbd-116"><a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="69bbd-116">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69bbd-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="69bbd-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="69bbd-118">int</span><span class="sxs-lookup"><span data-stu-id="69bbd-118">int</span></span></p></td>
<td><p><span data-ttu-id="69bbd-119">主要，外部</span><span class="sxs-lookup"><span data-stu-id="69bbd-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="69bbd-120">用來識別工作階段的識別碼。</span><span class="sxs-lookup"><span data-stu-id="69bbd-120">ID number to identify the session.</span></span> <span data-ttu-id="69bbd-121">搭配<strong>SessionIdTime</strong>用來唯一地識別 session.\* <a href="lync-server-2013-dialogs-table.md">Dialogs Lync Server 2013 中的表格</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="69bbd-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69bbd-122"><strong>相互關聯識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="69bbd-122"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="69bbd-123">唯一</span><span class="sxs-lookup"><span data-stu-id="69bbd-123">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69bbd-124">與多個工作階段相互關聯的 GUID。</span><span class="sxs-lookup"><span data-stu-id="69bbd-124">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69bbd-125"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="69bbd-125"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="69bbd-126">datetime</span><span class="sxs-lookup"><span data-stu-id="69bbd-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="69bbd-127">Foreign</span><span class="sxs-lookup"><span data-stu-id="69bbd-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69bbd-128">用來識別目前工作階段所取代之對話的識別碼。</span><span class="sxs-lookup"><span data-stu-id="69bbd-128">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="69bbd-129"><a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="69bbd-129">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69bbd-130"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="69bbd-130"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="69bbd-131">int</span><span class="sxs-lookup"><span data-stu-id="69bbd-131">int</span></span></p></td>
<td><p><span data-ttu-id="69bbd-132">Foreign</span><span class="sxs-lookup"><span data-stu-id="69bbd-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69bbd-133">用來識別工作階段的識別碼。</span><span class="sxs-lookup"><span data-stu-id="69bbd-133">ID number to identify the session.</span></span> <span data-ttu-id="69bbd-134">其會與 <strong>ReplacesDialogIdTime</strong> 搭配使用，專門用於識別此工作階段所取代的工作階段。</span><span class="sxs-lookup"><span data-stu-id="69bbd-134">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="69bbd-135"><a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="69bbd-135">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69bbd-136"><strong>User1Id</strong></span><span class="sxs-lookup"><span data-stu-id="69bbd-136"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="69bbd-137">int</span><span class="sxs-lookup"><span data-stu-id="69bbd-137">int</span></span></p></td>
<td><p><span data-ttu-id="69bbd-138">Foreign</span><span class="sxs-lookup"><span data-stu-id="69bbd-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69bbd-139">工作階段中某位使用者的識別碼。</span><span class="sxs-lookup"><span data-stu-id="69bbd-139">ID of one user in the session.</span></span> <span data-ttu-id="69bbd-140">請參閱如需詳細資訊，<a href="lync-server-2013-users-table.md">使用者在 Lync Server 2013 中的表格</a>。</span><span class="sxs-lookup"><span data-stu-id="69bbd-140">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69bbd-141"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="69bbd-141"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="69bbd-142">int</span><span class="sxs-lookup"><span data-stu-id="69bbd-142">int</span></span></p></td>
<td><p><span data-ttu-id="69bbd-143">Foreign</span><span class="sxs-lookup"><span data-stu-id="69bbd-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69bbd-144">工作階段中其他使用者的識別碼。</span><span class="sxs-lookup"><span data-stu-id="69bbd-144">ID of the other user in the session.</span></span> <span data-ttu-id="69bbd-145">請參閱如需詳細資訊，<a href="lync-server-2013-users-table.md">使用者在 Lync Server 2013 中的表格</a>。</span><span class="sxs-lookup"><span data-stu-id="69bbd-145">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69bbd-146"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="69bbd-146"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="69bbd-147">唯一</span><span class="sxs-lookup"><span data-stu-id="69bbd-147">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69bbd-148">識別工作階段中第一位使用者所使用之端點的 GUID。</span><span class="sxs-lookup"><span data-stu-id="69bbd-148">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="69bbd-149">Microsoft Lync Server 2013 中已採用此欄位。</span><span class="sxs-lookup"><span data-stu-id="69bbd-149">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69bbd-150"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="69bbd-150"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="69bbd-151">唯一</span><span class="sxs-lookup"><span data-stu-id="69bbd-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69bbd-152">識別工作階段中第二位使用者所使用之端點的 GUID。</span><span class="sxs-lookup"><span data-stu-id="69bbd-152">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="69bbd-153">Microsoft Lync Server 2013 中已採用此欄位。</span><span class="sxs-lookup"><span data-stu-id="69bbd-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69bbd-154"><strong>TargetUserId</strong></span><span class="sxs-lookup"><span data-stu-id="69bbd-154"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="69bbd-155">int</span><span class="sxs-lookup"><span data-stu-id="69bbd-155">int</span></span></p></td>
<td><p><span data-ttu-id="69bbd-156">Foreign</span><span class="sxs-lookup"><span data-stu-id="69bbd-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69bbd-157">SIP 要求中原始的目標使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="69bbd-157">The original To user URI in the SIP request.</span></span> <span data-ttu-id="69bbd-158">請參閱如需詳細資訊，<a href="lync-server-2013-users-table.md">使用者在 Lync Server 2013 中的表格</a>。</span><span class="sxs-lookup"><span data-stu-id="69bbd-158">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69bbd-159"><strong>SessionStartedById</strong></span><span class="sxs-lookup"><span data-stu-id="69bbd-159"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="69bbd-160">int</span><span class="sxs-lookup"><span data-stu-id="69bbd-160">int</span></span></p></td>
<td><p><span data-ttu-id="69bbd-161">Foreign</span><span class="sxs-lookup"><span data-stu-id="69bbd-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69bbd-162">起始工作階段之使用者的識別碼。</span><span class="sxs-lookup"><span data-stu-id="69bbd-162">ID of the user who started the session.</span></span> <span data-ttu-id="69bbd-163">請參閱如需詳細資訊，<a href="lync-server-2013-users-table.md">使用者在 Lync Server 2013 中的表格</a>。</span><span class="sxs-lookup"><span data-stu-id="69bbd-163">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69bbd-164"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="69bbd-164"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="69bbd-165">int</span><span class="sxs-lookup"><span data-stu-id="69bbd-165">int</span></span></p></td>
<td><p><span data-ttu-id="69bbd-166">Foreign</span><span class="sxs-lookup"><span data-stu-id="69bbd-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69bbd-167">指出來電者所代表之使用者的識別碼。</span><span class="sxs-lookup"><span data-stu-id="69bbd-167">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="69bbd-168">請參閱如需詳細資訊，<a href="lync-server-2013-users-table.md">使用者在 Lync Server 2013 中的表格</a>。</span><span class="sxs-lookup"><span data-stu-id="69bbd-168">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69bbd-169"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="69bbd-169"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="69bbd-170">int</span><span class="sxs-lookup"><span data-stu-id="69bbd-170">int</span></span></p></td>
<td><p><span data-ttu-id="69bbd-171">Foreign</span><span class="sxs-lookup"><span data-stu-id="69bbd-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69bbd-172">轉接此通話之使用者的識別碼。</span><span class="sxs-lookup"><span data-stu-id="69bbd-172">ID of the user by who the call is referred.</span></span> <span data-ttu-id="69bbd-173">請參閱如需詳細資訊，<a href="lync-server-2013-users-table.md">使用者在 Lync Server 2013 中的表格</a>。</span><span class="sxs-lookup"><span data-stu-id="69bbd-173">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69bbd-174"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="69bbd-174"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="69bbd-175">int</span><span class="sxs-lookup"><span data-stu-id="69bbd-175">int</span></span></p></td>
<td><p><span data-ttu-id="69bbd-176">Foreign</span><span class="sxs-lookup"><span data-stu-id="69bbd-176">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69bbd-177">用於此工作階段之前端伺服器的識別碼。</span><span class="sxs-lookup"><span data-stu-id="69bbd-177">ID of the front-end server used for this session.</span></span> <span data-ttu-id="69bbd-178">請參閱<a href="lync-server-2013-servers-table.md">Lync Server 2013 中的伺服器表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="69bbd-178">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69bbd-179"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="69bbd-179"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="69bbd-180">int</span><span class="sxs-lookup"><span data-stu-id="69bbd-180">int</span></span></p></td>
<td><p><span data-ttu-id="69bbd-181">Foreign</span><span class="sxs-lookup"><span data-stu-id="69bbd-181">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69bbd-182">擷取工作階段所在集區的識別碼。</span><span class="sxs-lookup"><span data-stu-id="69bbd-182">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="69bbd-183">請參閱如需詳細資訊，<a href="lync-server-2013-pools-table.md">在 Lync Server 2013 中的集區資料表</a>。</span><span class="sxs-lookup"><span data-stu-id="69bbd-183">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69bbd-184"><strong>ContentTypeID</strong></span><span class="sxs-lookup"><span data-stu-id="69bbd-184"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="69bbd-185">int</span><span class="sxs-lookup"><span data-stu-id="69bbd-185">int</span></span></p></td>
<td><p><span data-ttu-id="69bbd-186">Foreign</span><span class="sxs-lookup"><span data-stu-id="69bbd-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69bbd-187">工作階段中所使用的內容類型。</span><span class="sxs-lookup"><span data-stu-id="69bbd-187">Content type used in the session.</span></span> <span data-ttu-id="69bbd-188">請參閱<a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 中的 ContentTypes 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="69bbd-188">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69bbd-189"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="69bbd-189"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="69bbd-190">int</span><span class="sxs-lookup"><span data-stu-id="69bbd-190">int</span></span></p></td>
<td><p><span data-ttu-id="69bbd-191">Foreign</span><span class="sxs-lookup"><span data-stu-id="69bbd-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69bbd-192">使用者1 所使用的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="69bbd-192">Client version used by User1.</span></span> <span data-ttu-id="69bbd-193">請參閱<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="69bbd-193">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69bbd-194"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="69bbd-194"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="69bbd-195">int</span><span class="sxs-lookup"><span data-stu-id="69bbd-195">int</span></span></p></td>
<td><p><span data-ttu-id="69bbd-196">Foreign</span><span class="sxs-lookup"><span data-stu-id="69bbd-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69bbd-197">使用者2 所使用的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="69bbd-197">Client version used by User2.</span></span> <span data-ttu-id="69bbd-198">請參閱<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="69bbd-198">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69bbd-199"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="69bbd-199"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="69bbd-200">int</span><span class="sxs-lookup"><span data-stu-id="69bbd-200">int</span></span></p></td>
<td><p><span data-ttu-id="69bbd-201">Foreign</span><span class="sxs-lookup"><span data-stu-id="69bbd-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69bbd-202">使用者 1 所使用的 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="69bbd-202">Edge Server used by User1.</span></span> <span data-ttu-id="69bbd-203">請參閱<a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="69bbd-203">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69bbd-204"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="69bbd-204"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="69bbd-205">int</span><span class="sxs-lookup"><span data-stu-id="69bbd-205">int</span></span></p></td>
<td><p><span data-ttu-id="69bbd-206">Foreign</span><span class="sxs-lookup"><span data-stu-id="69bbd-206">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69bbd-207">使用者 2 所使用的 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="69bbd-207">Edge Server used by User2.</span></span> <span data-ttu-id="69bbd-208">請參閱<a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="69bbd-208">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69bbd-209"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="69bbd-209"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="69bbd-210">位元</span><span class="sxs-lookup"><span data-stu-id="69bbd-210">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69bbd-211">使用者 1 是否由內部登入。</span><span class="sxs-lookup"><span data-stu-id="69bbd-211">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69bbd-212"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="69bbd-212"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="69bbd-213">位元</span><span class="sxs-lookup"><span data-stu-id="69bbd-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69bbd-214">使用者 2 是否由內部登入。</span><span class="sxs-lookup"><span data-stu-id="69bbd-214">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69bbd-215"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="69bbd-215"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="69bbd-216">datetime</span><span class="sxs-lookup"><span data-stu-id="69bbd-216">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69bbd-217">第一個 INVITE 要求的時間。</span><span class="sxs-lookup"><span data-stu-id="69bbd-217">The time of the first INVITE request.</span></span> <span data-ttu-id="69bbd-218">此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。</span><span class="sxs-lookup"><span data-stu-id="69bbd-218">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="69bbd-219">如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="69bbd-219">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="69bbd-220">此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。</span><span class="sxs-lookup"><span data-stu-id="69bbd-220">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="69bbd-221">如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="69bbd-221">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69bbd-222"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="69bbd-222"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="69bbd-223">datetime</span><span class="sxs-lookup"><span data-stu-id="69bbd-223">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69bbd-224">回應第一個 INVITE 訊息的時間。</span><span class="sxs-lookup"><span data-stu-id="69bbd-224">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="69bbd-225">此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。</span><span class="sxs-lookup"><span data-stu-id="69bbd-225">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="69bbd-226">如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="69bbd-226">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69bbd-227"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="69bbd-227"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="69bbd-228">int</span><span class="sxs-lookup"><span data-stu-id="69bbd-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69bbd-p121">工作階段邀請的 SIP 回應碼。此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="69bbd-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69bbd-232"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="69bbd-232"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="69bbd-233">int</span><span class="sxs-lookup"><span data-stu-id="69bbd-233">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69bbd-234">從 SIP 標頭擷取而來的診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="69bbd-234">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69bbd-235"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="69bbd-235"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="69bbd-236">int</span><span class="sxs-lookup"><span data-stu-id="69bbd-236">int</span></span></p></td>
<td><p><span data-ttu-id="69bbd-237">Foreign</span><span class="sxs-lookup"><span data-stu-id="69bbd-237">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69bbd-238">通話優先順序。</span><span class="sxs-lookup"><span data-stu-id="69bbd-238">Call priority.</span></span> <span data-ttu-id="69bbd-239">請參閱<a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 中的 CallPriorities 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="69bbd-239">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69bbd-240"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="69bbd-240"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="69bbd-241">int</span><span class="sxs-lookup"><span data-stu-id="69bbd-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69bbd-242">工作階段期間使用者 1 所傳送的訊息數。</span><span class="sxs-lookup"><span data-stu-id="69bbd-242">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69bbd-243"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="69bbd-243"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="69bbd-244">int</span><span class="sxs-lookup"><span data-stu-id="69bbd-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69bbd-245">工作階段期間使用者 2 所傳送的訊息數。</span><span class="sxs-lookup"><span data-stu-id="69bbd-245">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69bbd-246"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="69bbd-246"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="69bbd-247">datetime</span><span class="sxs-lookup"><span data-stu-id="69bbd-247">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69bbd-248">工作階段結束的時間。</span><span class="sxs-lookup"><span data-stu-id="69bbd-248">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69bbd-249"><strong>MediaTypes</strong></span><span class="sxs-lookup"><span data-stu-id="69bbd-249"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="69bbd-250">int</span><span class="sxs-lookup"><span data-stu-id="69bbd-250">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69bbd-p123">指出此工作階段之媒體類型的位元集。下列為類型的定義：</span><span class="sxs-lookup"><span data-stu-id="69bbd-p123">A bit set that indicates the media type of this session. Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69bbd-253">IM</span><span class="sxs-lookup"><span data-stu-id="69bbd-253">IM</span></span></p></td>
<td><p><span data-ttu-id="69bbd-254">1 </span><span class="sxs-lookup"><span data-stu-id="69bbd-254">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69bbd-255">FILE_TRANSFER</span><span class="sxs-lookup"><span data-stu-id="69bbd-255">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="69bbd-256">2 </span><span class="sxs-lookup"><span data-stu-id="69bbd-256">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69bbd-257">REMOTE_ASSISTANCE</span><span class="sxs-lookup"><span data-stu-id="69bbd-257">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="69bbd-258">4 </span><span class="sxs-lookup"><span data-stu-id="69bbd-258">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69bbd-259">APP_SHARING</span><span class="sxs-lookup"><span data-stu-id="69bbd-259">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="69bbd-260">8 </span><span class="sxs-lookup"><span data-stu-id="69bbd-260">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69bbd-261">音訊</span><span class="sxs-lookup"><span data-stu-id="69bbd-261">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="69bbd-262">16 </span><span class="sxs-lookup"><span data-stu-id="69bbd-262">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69bbd-263">影片</span><span class="sxs-lookup"><span data-stu-id="69bbd-263">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="69bbd-264">32</span><span class="sxs-lookup"><span data-stu-id="69bbd-264">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69bbd-265">APP_INVITE</span><span class="sxs-lookup"><span data-stu-id="69bbd-265">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="69bbd-266">64</span><span class="sxs-lookup"><span data-stu-id="69bbd-266">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69bbd-267"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="69bbd-267"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="69bbd-268">smallint</span><span class="sxs-lookup"><span data-stu-id="69bbd-268">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69bbd-p124">指出使用者 1 屬性的位元集。下列是屬性的定義：</span><span class="sxs-lookup"><span data-stu-id="69bbd-p124">A bit set that indicates the User1 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="69bbd-271">0x01 - 與桌上電話整合</span><span class="sxs-lookup"><span data-stu-id="69bbd-271">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69bbd-272"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="69bbd-272"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="69bbd-273">smallint</span><span class="sxs-lookup"><span data-stu-id="69bbd-273">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69bbd-p125">指出使用者 2 屬性的位元集。下列是屬性的定義：</span><span class="sxs-lookup"><span data-stu-id="69bbd-p125">A bit set that indicates the User2 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="69bbd-276">0x01 - 與桌上電話整合</span><span class="sxs-lookup"><span data-stu-id="69bbd-276">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69bbd-277"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="69bbd-277"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="69bbd-278">smallint</span><span class="sxs-lookup"><span data-stu-id="69bbd-278">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69bbd-p126">指出通話屬性的位元設定。下列是屬性的定義：</span><span class="sxs-lookup"><span data-stu-id="69bbd-p126">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="69bbd-281">0x01 - 重試工作階段 1</span><span class="sxs-lookup"><span data-stu-id="69bbd-281">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="69bbd-282">0x02 - 由代理人代替回應群組撥出的通話</span><span class="sxs-lookup"><span data-stu-id="69bbd-282">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69bbd-283"><strong>處理</strong></span><span class="sxs-lookup"><span data-stu-id="69bbd-283"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="69bbd-284">位元</span><span class="sxs-lookup"><span data-stu-id="69bbd-284">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69bbd-285">供監控服務內部使用。</span><span class="sxs-lookup"><span data-stu-id="69bbd-285">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="69bbd-286">Microsoft Lync Server 2013 中已採用此欄位。</span><span class="sxs-lookup"><span data-stu-id="69bbd-286">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="69bbd-287">\*對於大多數的工作階段，SessionIdSeq 會有 1 的值。</span><span class="sxs-lookup"><span data-stu-id="69bbd-287">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="69bbd-288">如有多個工作階段的啟動時間完全相同，將只有一個工作階段的 SessionIdSeq 值會是 1，其餘工作階段皆是 2，依此類推。</span><span class="sxs-lookup"><span data-stu-id="69bbd-288">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

