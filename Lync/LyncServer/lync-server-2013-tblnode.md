---
title: Lync Server 2013： tblNode
description: Lync Server 2013： tblNode。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblNode
ms:assetid: a31d2961-aa83-4286-a12e-15d279c95f19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615024(v=OCS.15)
ms:contentKeyID: 48184960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0a5d630621c32cbc54501249c7a679bf4023c60
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547549"
---
# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="57c8d-103">Lync Server 2013 中的 tblNode</span><span class="sxs-lookup"><span data-stu-id="57c8d-103">tblNode in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57c8d-104">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="57c8d-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="57c8d-105">tblNode 包含類別或聊天室節點的物件樹 () Lync Server 2013 控制台和管理 Cmdlet 中的管理。</span><span class="sxs-lookup"><span data-stu-id="57c8d-105">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="57c8d-106">Columns</span><span class="sxs-lookup"><span data-stu-id="57c8d-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="57c8d-107">欄</span><span class="sxs-lookup"><span data-stu-id="57c8d-107">Column</span></span></th>
<th><span data-ttu-id="57c8d-108">類型</span><span class="sxs-lookup"><span data-stu-id="57c8d-108">Type</span></span></th>
<th><span data-ttu-id="57c8d-109">描述</span><span class="sxs-lookup"><span data-stu-id="57c8d-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57c8d-110">nodeID</span><span class="sxs-lookup"><span data-stu-id="57c8d-110">nodeID</span></span></p></td>
<td><p><span data-ttu-id="57c8d-111">int，非 null</span><span class="sxs-lookup"><span data-stu-id="57c8d-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="57c8d-112">節點識別碼 (唯一編號) 。</span><span class="sxs-lookup"><span data-stu-id="57c8d-112">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57c8d-113">nodeGuid</span><span class="sxs-lookup"><span data-stu-id="57c8d-113">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="57c8d-114">GUID，非 null</span><span class="sxs-lookup"><span data-stu-id="57c8d-114">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="57c8d-115">節點 GUID。</span><span class="sxs-lookup"><span data-stu-id="57c8d-115">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57c8d-116">parentID</span><span class="sxs-lookup"><span data-stu-id="57c8d-116">parentID</span></span></p></td>
<td><p><span data-ttu-id="57c8d-117">int</span><span class="sxs-lookup"><span data-stu-id="57c8d-117">int</span></span></p></td>
<td><p><span data-ttu-id="57c8d-118">父系的節點識別碼。</span><span class="sxs-lookup"><span data-stu-id="57c8d-118">Node ID of parent.</span></span> <span data-ttu-id="57c8d-119">識別碼為 1) 的根節點 (也會將其本身包含為上層。</span><span class="sxs-lookup"><span data-stu-id="57c8d-119">The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57c8d-120">nodeType</span><span class="sxs-lookup"><span data-stu-id="57c8d-120">nodeType</span></span></p></td>
<td><p><span data-ttu-id="57c8d-121">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="57c8d-121">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="57c8d-122">True 是表示如果節點為類別。</span><span class="sxs-lookup"><span data-stu-id="57c8d-122">True if the node is a category.</span></span></p>
<p><span data-ttu-id="57c8d-123">False 表示節點為聊天室。</span><span class="sxs-lookup"><span data-stu-id="57c8d-123">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57c8d-124">nodeName</span><span class="sxs-lookup"><span data-stu-id="57c8d-124">nodeName</span></span></p></td>
<td><p><span data-ttu-id="57c8d-125">nvarchar (256)，非 null</span><span class="sxs-lookup"><span data-stu-id="57c8d-125">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="57c8d-126">節點名稱。</span><span class="sxs-lookup"><span data-stu-id="57c8d-126">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57c8d-127">nodeDesc</span><span class="sxs-lookup"><span data-stu-id="57c8d-127">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="57c8d-128">nvarchar (256)，非 null</span><span class="sxs-lookup"><span data-stu-id="57c8d-128">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="57c8d-129">節點描述。</span><span class="sxs-lookup"><span data-stu-id="57c8d-129">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57c8d-130">邀請</span><span class="sxs-lookup"><span data-stu-id="57c8d-130">invite</span></span></p></td>
<td><p><span data-ttu-id="57c8d-131">位</span><span class="sxs-lookup"><span data-stu-id="57c8d-131">bit</span></span></p></td>
<td><p><span data-ttu-id="57c8d-132">類別：</span><span class="sxs-lookup"><span data-stu-id="57c8d-132">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="57c8d-133">True 是表示如果邀請已開啟。</span><span class="sxs-lookup"><span data-stu-id="57c8d-133">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="57c8d-134">為 False，則邀請為關閉狀態。</span><span class="sxs-lookup"><span data-stu-id="57c8d-134">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="57c8d-135">會議室：</span><span class="sxs-lookup"><span data-stu-id="57c8d-135">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="57c8d-136">False 如果邀請已關 (會覆寫父類別) 。</span><span class="sxs-lookup"><span data-stu-id="57c8d-136">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="57c8d-137">如果 [邀請] 設定繼承自父系類別，則為 Null。</span><span class="sxs-lookup"><span data-stu-id="57c8d-137">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57c8d-138">登錄</span><span class="sxs-lookup"><span data-stu-id="57c8d-138">logged</span></span></p></td>
<td><p><span data-ttu-id="57c8d-139">位</span><span class="sxs-lookup"><span data-stu-id="57c8d-139">bit</span></span></p></td>
<td><p><span data-ttu-id="57c8d-140">類別：</span><span class="sxs-lookup"><span data-stu-id="57c8d-140">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="57c8d-141">True 是表示如果聊天記錄開啟。</span><span class="sxs-lookup"><span data-stu-id="57c8d-141">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="57c8d-142">為 False，則聊天記錄為關閉狀態。</span><span class="sxs-lookup"><span data-stu-id="57c8d-142">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="57c8d-143">會議室：</span><span class="sxs-lookup"><span data-stu-id="57c8d-143">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="57c8d-144">空。</span><span class="sxs-lookup"><span data-stu-id="57c8d-144">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57c8d-145">filePost</span><span class="sxs-lookup"><span data-stu-id="57c8d-145">filePost</span></span></p></td>
<td><p><span data-ttu-id="57c8d-146">位</span><span class="sxs-lookup"><span data-stu-id="57c8d-146">bit</span></span></p></td>
<td><p><span data-ttu-id="57c8d-147">類別：</span><span class="sxs-lookup"><span data-stu-id="57c8d-147">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="57c8d-148">True 是表示如果允許檔案上傳。</span><span class="sxs-lookup"><span data-stu-id="57c8d-148">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="57c8d-149">False 表示不允許檔案上傳。</span><span class="sxs-lookup"><span data-stu-id="57c8d-149">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="57c8d-150">會議室：</span><span class="sxs-lookup"><span data-stu-id="57c8d-150">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="57c8d-151">空。</span><span class="sxs-lookup"><span data-stu-id="57c8d-151">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57c8d-152">禁用</span><span class="sxs-lookup"><span data-stu-id="57c8d-152">disabled</span></span></p></td>
<td><p><span data-ttu-id="57c8d-153">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="57c8d-153">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="57c8d-154">True 是表示如果停用聊天室。</span><span class="sxs-lookup"><span data-stu-id="57c8d-154">True if the chat room is disabled.</span></span> <span data-ttu-id="57c8d-155">僅適用于聊天室。</span><span class="sxs-lookup"><span data-stu-id="57c8d-155">Applies only to chat rooms.</span></span> <span data-ttu-id="57c8d-156"> (類別為 False。 ) </span><span class="sxs-lookup"><span data-stu-id="57c8d-156">(False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57c8d-157">行為</span><span class="sxs-lookup"><span data-stu-id="57c8d-157">behavior</span></span></p></td>
<td><p><span data-ttu-id="57c8d-158">smallint，非 null</span><span class="sxs-lookup"><span data-stu-id="57c8d-158">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="57c8d-159">在 EnumValue table) 中查閱 (行為：</span><span class="sxs-lookup"><span data-stu-id="57c8d-159">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="57c8d-160">4：正常 (一般聊天室) 。</span><span class="sxs-lookup"><span data-stu-id="57c8d-160">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="57c8d-161">5：視聽中心 (視聽中心聊天室，只有簡報者可以參與) 。</span><span class="sxs-lookup"><span data-stu-id="57c8d-161">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="57c8d-162">僅適用于聊天室。</span><span class="sxs-lookup"><span data-stu-id="57c8d-162">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57c8d-163">visibility</span><span class="sxs-lookup"><span data-stu-id="57c8d-163">visibility</span></span></p></td>
<td><p><span data-ttu-id="57c8d-164">smallint，非 null</span><span class="sxs-lookup"><span data-stu-id="57c8d-164">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="57c8d-165">EnumValue table) 上查看的可見度 (：</span><span class="sxs-lookup"><span data-stu-id="57c8d-165">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="57c8d-166">2：私人</span><span class="sxs-lookup"><span data-stu-id="57c8d-166">2: Private</span></span></p></li>
<li><p><span data-ttu-id="57c8d-167">3：範圍</span><span class="sxs-lookup"><span data-stu-id="57c8d-167">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="57c8d-168">6：開啟</span><span class="sxs-lookup"><span data-stu-id="57c8d-168">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="57c8d-169">僅適用于聊天室。</span><span class="sxs-lookup"><span data-stu-id="57c8d-169">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57c8d-170">siopID</span><span class="sxs-lookup"><span data-stu-id="57c8d-170">siopID</span></span></p></td>
<td><p><span data-ttu-id="57c8d-171">GUID</span><span class="sxs-lookup"><span data-stu-id="57c8d-171">GUID</span></span></p></td>
<td><p><span data-ttu-id="57c8d-172">Add-In GUID （如果增益集與此聊天室關聯）。</span><span class="sxs-lookup"><span data-stu-id="57c8d-172">Add-In GUID if an add-in is associated with this chat room.</span></span> <span data-ttu-id="57c8d-173"> (類別沒有增益集。 ) </span><span class="sxs-lookup"><span data-stu-id="57c8d-173">(Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="57c8d-174">增益集資訊會在 SiopWhiteList 表格中進行查閱。</span><span class="sxs-lookup"><span data-stu-id="57c8d-174">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57c8d-175">nodeAddedBy</span><span class="sxs-lookup"><span data-stu-id="57c8d-175">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="57c8d-176">int，非 null</span><span class="sxs-lookup"><span data-stu-id="57c8d-176">int, not null</span></span></p></td>
<td><p><span data-ttu-id="57c8d-177">建立此節點之主體的識別碼。</span><span class="sxs-lookup"><span data-stu-id="57c8d-177">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57c8d-178">nodeAddedOn</span><span class="sxs-lookup"><span data-stu-id="57c8d-178">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="57c8d-179">bigint，非 null</span><span class="sxs-lookup"><span data-stu-id="57c8d-179">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="57c8d-180">建立節點的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="57c8d-180">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57c8d-181">nodeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="57c8d-181">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="57c8d-182">int，非 null</span><span class="sxs-lookup"><span data-stu-id="57c8d-182">int, not null</span></span></p></td>
<td><p><span data-ttu-id="57c8d-183">進行此節點之最新更新之主體的識別碼。</span><span class="sxs-lookup"><span data-stu-id="57c8d-183">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57c8d-184">nodeUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="57c8d-184">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="57c8d-185">bigint，非 null</span><span class="sxs-lookup"><span data-stu-id="57c8d-185">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="57c8d-186">此節點最新更新的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="57c8d-186">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57c8d-187">purgedOn</span><span class="sxs-lookup"><span data-stu-id="57c8d-187">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="57c8d-188">datetime</span><span class="sxs-lookup"><span data-stu-id="57c8d-188">datetime</span></span></p></td>
<td><p><span data-ttu-id="57c8d-189">最新的清除作業時間 (從影響此節點 tblPrincipalRole 表格) 移除 tblScopedPrincipal 資料表和角色中的範圍。</span><span class="sxs-lookup"><span data-stu-id="57c8d-189">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node.</span></span> <span data-ttu-id="57c8d-190">這是由聊天服務的內部快取更新機制使用。</span><span class="sxs-lookup"><span data-stu-id="57c8d-190">This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="57c8d-191">索引鍵</span><span class="sxs-lookup"><span data-stu-id="57c8d-191">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="57c8d-192">欄</span><span class="sxs-lookup"><span data-stu-id="57c8d-192">Column</span></span></th>
<th><span data-ttu-id="57c8d-193">描述</span><span class="sxs-lookup"><span data-stu-id="57c8d-193">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57c8d-194">nodeID</span><span class="sxs-lookup"><span data-stu-id="57c8d-194">nodeID</span></span></p></td>
<td><p><span data-ttu-id="57c8d-195">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="57c8d-195">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57c8d-196">行為</span><span class="sxs-lookup"><span data-stu-id="57c8d-196">behavior</span></span></p></td>
<td><p><span data-ttu-id="57c8d-197">在 tblEnumValue.valueID 表格中查閱的外鍵。</span><span class="sxs-lookup"><span data-stu-id="57c8d-197">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57c8d-198">visibility</span><span class="sxs-lookup"><span data-stu-id="57c8d-198">visibility</span></span></p></td>
<td><p><span data-ttu-id="57c8d-199">在 tblEnumValue.valueID 表格中查閱的外鍵。</span><span class="sxs-lookup"><span data-stu-id="57c8d-199">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57c8d-200">parentID</span><span class="sxs-lookup"><span data-stu-id="57c8d-200">parentID</span></span></p></td>
<td><p><span data-ttu-id="57c8d-201">在 tblNode.nodeID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="57c8d-201">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57c8d-202">siopID</span><span class="sxs-lookup"><span data-stu-id="57c8d-202">siopID</span></span></p></td>
<td><p><span data-ttu-id="57c8d-203">在 tblSiopWhiteList.siopId 表格中查閱的外鍵。</span><span class="sxs-lookup"><span data-stu-id="57c8d-203">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

