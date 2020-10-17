---
title: Lync Server 2013： tblNode
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
ms.openlocfilehash: 1e6070f6a575466d9ce7063c588e5d470e047d52
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523810"
---
# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="8a2a0-102">Lync Server 2013 中的 tblNode</span><span class="sxs-lookup"><span data-stu-id="8a2a0-102">tblNode in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a2a0-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="8a2a0-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="8a2a0-104">tblNode 包含類別或聊天室節點的物件樹 () Lync Server 2013 控制台和管理 Cmdlet 中的管理。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-104">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="8a2a0-105">Columns</span><span class="sxs-lookup"><span data-stu-id="8a2a0-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8a2a0-106">欄</span><span class="sxs-lookup"><span data-stu-id="8a2a0-106">Column</span></span></th>
<th><span data-ttu-id="8a2a0-107">類型</span><span class="sxs-lookup"><span data-stu-id="8a2a0-107">Type</span></span></th>
<th><span data-ttu-id="8a2a0-108">描述</span><span class="sxs-lookup"><span data-stu-id="8a2a0-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8a2a0-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="8a2a0-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="8a2a0-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-111">節點識別碼 (唯一編號) 。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-111">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a2a0-112">nodeGuid</span><span class="sxs-lookup"><span data-stu-id="8a2a0-112">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-113">GUID，非 null</span><span class="sxs-lookup"><span data-stu-id="8a2a0-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-114">節點 GUID。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-114">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a2a0-115">parentID</span><span class="sxs-lookup"><span data-stu-id="8a2a0-115">parentID</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-116">int</span><span class="sxs-lookup"><span data-stu-id="8a2a0-116">int</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-117">父系的節點識別碼。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-117">Node ID of parent.</span></span> <span data-ttu-id="8a2a0-118">識別碼為 1) 的根節點 (也會將其本身包含為上層。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-118">The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a2a0-119">nodeType</span><span class="sxs-lookup"><span data-stu-id="8a2a0-119">nodeType</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-120">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="8a2a0-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-121">True 是表示如果節點為類別。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-121">True if the node is a category.</span></span></p>
<p><span data-ttu-id="8a2a0-122">False 表示節點為聊天室。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-122">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a2a0-123">nodeName</span><span class="sxs-lookup"><span data-stu-id="8a2a0-123">nodeName</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-124">nvarchar (256)，非 null</span><span class="sxs-lookup"><span data-stu-id="8a2a0-124">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-125">節點名稱。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-125">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a2a0-126">nodeDesc</span><span class="sxs-lookup"><span data-stu-id="8a2a0-126">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-127">nvarchar (256)，非 null</span><span class="sxs-lookup"><span data-stu-id="8a2a0-127">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-128">節點描述。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-128">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a2a0-129">邀請</span><span class="sxs-lookup"><span data-stu-id="8a2a0-129">invite</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-130">位</span><span class="sxs-lookup"><span data-stu-id="8a2a0-130">bit</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-131">類別：</span><span class="sxs-lookup"><span data-stu-id="8a2a0-131">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="8a2a0-132">True 是表示如果邀請已開啟。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-132">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="8a2a0-133">為 False，則邀請為關閉狀態。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-133">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="8a2a0-134">會議室：</span><span class="sxs-lookup"><span data-stu-id="8a2a0-134">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="8a2a0-135">False 如果邀請已關 (會覆寫父類別) 。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-135">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="8a2a0-136">如果 [邀請] 設定繼承自父系類別，則為 Null。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-136">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a2a0-137">登錄</span><span class="sxs-lookup"><span data-stu-id="8a2a0-137">logged</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-138">位</span><span class="sxs-lookup"><span data-stu-id="8a2a0-138">bit</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-139">類別：</span><span class="sxs-lookup"><span data-stu-id="8a2a0-139">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="8a2a0-140">True 是表示如果聊天記錄開啟。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-140">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="8a2a0-141">為 False，則聊天記錄為關閉狀態。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-141">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="8a2a0-142">會議室：</span><span class="sxs-lookup"><span data-stu-id="8a2a0-142">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="8a2a0-143">空。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-143">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a2a0-144">filePost</span><span class="sxs-lookup"><span data-stu-id="8a2a0-144">filePost</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-145">位</span><span class="sxs-lookup"><span data-stu-id="8a2a0-145">bit</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-146">類別：</span><span class="sxs-lookup"><span data-stu-id="8a2a0-146">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="8a2a0-147">True 是表示如果允許檔案上傳。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-147">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="8a2a0-148">False 表示不允許檔案上傳。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-148">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="8a2a0-149">會議室：</span><span class="sxs-lookup"><span data-stu-id="8a2a0-149">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="8a2a0-150">空。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-150">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a2a0-151">禁用</span><span class="sxs-lookup"><span data-stu-id="8a2a0-151">disabled</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-152">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="8a2a0-152">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-153">True 是表示如果停用聊天室。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-153">True if the chat room is disabled.</span></span> <span data-ttu-id="8a2a0-154">僅適用于聊天室。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-154">Applies only to chat rooms.</span></span> <span data-ttu-id="8a2a0-155"> (類別為 False。 ) </span><span class="sxs-lookup"><span data-stu-id="8a2a0-155">(False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a2a0-156">行為</span><span class="sxs-lookup"><span data-stu-id="8a2a0-156">behavior</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-157">smallint，非 null</span><span class="sxs-lookup"><span data-stu-id="8a2a0-157">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-158">在 EnumValue table) 中查閱 (行為：</span><span class="sxs-lookup"><span data-stu-id="8a2a0-158">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="8a2a0-159">4：正常 (一般聊天室) 。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-159">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="8a2a0-160">5：視聽中心 (視聽中心聊天室，只有簡報者可以參與) 。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-160">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="8a2a0-161">僅適用于聊天室。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-161">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a2a0-162">visibility</span><span class="sxs-lookup"><span data-stu-id="8a2a0-162">visibility</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-163">smallint，非 null</span><span class="sxs-lookup"><span data-stu-id="8a2a0-163">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-164">EnumValue table) 上查看的可見度 (：</span><span class="sxs-lookup"><span data-stu-id="8a2a0-164">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="8a2a0-165">2：私人</span><span class="sxs-lookup"><span data-stu-id="8a2a0-165">2: Private</span></span></p></li>
<li><p><span data-ttu-id="8a2a0-166">3：範圍</span><span class="sxs-lookup"><span data-stu-id="8a2a0-166">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="8a2a0-167">6：開啟</span><span class="sxs-lookup"><span data-stu-id="8a2a0-167">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="8a2a0-168">僅適用于聊天室。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-168">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a2a0-169">siopID</span><span class="sxs-lookup"><span data-stu-id="8a2a0-169">siopID</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-170">GUID</span><span class="sxs-lookup"><span data-stu-id="8a2a0-170">GUID</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-171">Add-In GUID （如果增益集與此聊天室關聯）。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-171">Add-In GUID if an add-in is associated with this chat room.</span></span> <span data-ttu-id="8a2a0-172"> (類別沒有增益集。 ) </span><span class="sxs-lookup"><span data-stu-id="8a2a0-172">(Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="8a2a0-173">增益集資訊會在 SiopWhiteList 表格中進行查閱。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-173">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a2a0-174">nodeAddedBy</span><span class="sxs-lookup"><span data-stu-id="8a2a0-174">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-175">int，非 null</span><span class="sxs-lookup"><span data-stu-id="8a2a0-175">int, not null</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-176">建立此節點之主體的識別碼。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-176">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a2a0-177">nodeAddedOn</span><span class="sxs-lookup"><span data-stu-id="8a2a0-177">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-178">bigint，非 null</span><span class="sxs-lookup"><span data-stu-id="8a2a0-178">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-179">建立節點的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-179">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a2a0-180">nodeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="8a2a0-180">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-181">int，非 null</span><span class="sxs-lookup"><span data-stu-id="8a2a0-181">int, not null</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-182">進行此節點之最新更新之主體的識別碼。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-182">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a2a0-183">nodeUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="8a2a0-183">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-184">bigint，非 null</span><span class="sxs-lookup"><span data-stu-id="8a2a0-184">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-185">此節點最新更新的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-185">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a2a0-186">purgedOn</span><span class="sxs-lookup"><span data-stu-id="8a2a0-186">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-187">datetime</span><span class="sxs-lookup"><span data-stu-id="8a2a0-187">datetime</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-188">最新的清除作業時間 (從影響此節點 tblPrincipalRole 表格) 移除 tblScopedPrincipal 資料表和角色中的範圍。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-188">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node.</span></span> <span data-ttu-id="8a2a0-189">這是由聊天服務的內部快取更新機制使用。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-189">This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="8a2a0-190">索引鍵</span><span class="sxs-lookup"><span data-stu-id="8a2a0-190">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8a2a0-191">欄</span><span class="sxs-lookup"><span data-stu-id="8a2a0-191">Column</span></span></th>
<th><span data-ttu-id="8a2a0-192">描述</span><span class="sxs-lookup"><span data-stu-id="8a2a0-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8a2a0-193">nodeID</span><span class="sxs-lookup"><span data-stu-id="8a2a0-193">nodeID</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-194">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-194">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a2a0-195">行為</span><span class="sxs-lookup"><span data-stu-id="8a2a0-195">behavior</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-196">在 tblEnumValue.valueID 表格中查閱的外鍵。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-196">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a2a0-197">visibility</span><span class="sxs-lookup"><span data-stu-id="8a2a0-197">visibility</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-198">在 tblEnumValue.valueID 表格中查閱的外鍵。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-198">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a2a0-199">parentID</span><span class="sxs-lookup"><span data-stu-id="8a2a0-199">parentID</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-200">在 tblNode.nodeID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-200">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a2a0-201">siopID</span><span class="sxs-lookup"><span data-stu-id="8a2a0-201">siopID</span></span></p></td>
<td><p><span data-ttu-id="8a2a0-202">在 tblSiopWhiteList.siopId 表格中查閱的外鍵。</span><span class="sxs-lookup"><span data-stu-id="8a2a0-202">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

