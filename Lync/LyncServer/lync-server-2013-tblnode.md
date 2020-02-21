---
title: 'Lync Server 2013: tblNode'
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
ms.openlocfilehash: 459b5393f255ade4e510f17c11beccf2f38f7cfc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="e00ee-102">Lync Server 2013 中的 tblNode</span><span class="sxs-lookup"><span data-stu-id="e00ee-102">tblNode in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e00ee-103">_**主題上次修改日期：** 2012年-09-12_</span><span class="sxs-lookup"><span data-stu-id="e00ee-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="e00ee-104">tblNode 受管理的 Lync Server 2013 控制台和系統管理指令程式中會包含物件樹狀目錄 （含有類別或聊天室節點）。</span><span class="sxs-lookup"><span data-stu-id="e00ee-104">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="e00ee-105">Columns</span><span class="sxs-lookup"><span data-stu-id="e00ee-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e00ee-106">欄</span><span class="sxs-lookup"><span data-stu-id="e00ee-106">Column</span></span></th>
<th><span data-ttu-id="e00ee-107">類型	</span><span class="sxs-lookup"><span data-stu-id="e00ee-107">Type</span></span></th>
<th><span data-ttu-id="e00ee-108">描述</span><span class="sxs-lookup"><span data-stu-id="e00ee-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e00ee-109">節點識別碼</span><span class="sxs-lookup"><span data-stu-id="e00ee-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="e00ee-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="e00ee-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e00ee-111">節點識別碼 （唯一號碼）。</span><span class="sxs-lookup"><span data-stu-id="e00ee-111">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e00ee-112">nodeGuid</span><span class="sxs-lookup"><span data-stu-id="e00ee-112">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="e00ee-113">GUID，非 null</span><span class="sxs-lookup"><span data-stu-id="e00ee-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="e00ee-114">節點 GUID。</span><span class="sxs-lookup"><span data-stu-id="e00ee-114">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e00ee-115">parentID</span><span class="sxs-lookup"><span data-stu-id="e00ee-115">parentID</span></span></p></td>
<td><p><span data-ttu-id="e00ee-116">int</span><span class="sxs-lookup"><span data-stu-id="e00ee-116">int</span></span></p></td>
<td><p><span data-ttu-id="e00ee-117">父代的節點識別碼。</span><span class="sxs-lookup"><span data-stu-id="e00ee-117">Node ID of parent.</span></span> <span data-ttu-id="e00ee-118">根節點 （以識別碼 1) 會包含本身作為父也。</span><span class="sxs-lookup"><span data-stu-id="e00ee-118">The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e00ee-119">nodeType</span><span class="sxs-lookup"><span data-stu-id="e00ee-119">nodeType</span></span></p></td>
<td><p><span data-ttu-id="e00ee-120">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="e00ee-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="e00ee-121">如果該節點是類別，則為 true。</span><span class="sxs-lookup"><span data-stu-id="e00ee-121">True if the node is a category.</span></span></p>
<p><span data-ttu-id="e00ee-122">如果該節點是聊天室，則為 false。</span><span class="sxs-lookup"><span data-stu-id="e00ee-122">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e00ee-123">節點</span><span class="sxs-lookup"><span data-stu-id="e00ee-123">nodeName</span></span></p></td>
<td><p><span data-ttu-id="e00ee-124">nvarchar (256)，非 null</span><span class="sxs-lookup"><span data-stu-id="e00ee-124">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="e00ee-125">節點名稱。</span><span class="sxs-lookup"><span data-stu-id="e00ee-125">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e00ee-126">nodeDesc</span><span class="sxs-lookup"><span data-stu-id="e00ee-126">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="e00ee-127">nvarchar (256)，非 null</span><span class="sxs-lookup"><span data-stu-id="e00ee-127">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="e00ee-128">節點描述。</span><span class="sxs-lookup"><span data-stu-id="e00ee-128">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e00ee-129">邀請</span><span class="sxs-lookup"><span data-stu-id="e00ee-129">invite</span></span></p></td>
<td><p><span data-ttu-id="e00ee-130">位元</span><span class="sxs-lookup"><span data-stu-id="e00ee-130">bit</span></span></p></td>
<td><p><span data-ttu-id="e00ee-131">對於類別：</span><span class="sxs-lookup"><span data-stu-id="e00ee-131">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="e00ee-132">如果啟用 invite，則為 true。</span><span class="sxs-lookup"><span data-stu-id="e00ee-132">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="e00ee-133">若關閉 invite，則為 false。</span><span class="sxs-lookup"><span data-stu-id="e00ee-133">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="e00ee-134">對於會議室：</span><span class="sxs-lookup"><span data-stu-id="e00ee-134">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="e00ee-135">若關閉 invite，則為 false （覆寫父系類別）。</span><span class="sxs-lookup"><span data-stu-id="e00ee-135">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="e00ee-136">如果從父系類別繼承的設定 invite，則為 null。</span><span class="sxs-lookup"><span data-stu-id="e00ee-136">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e00ee-137">登入</span><span class="sxs-lookup"><span data-stu-id="e00ee-137">logged</span></span></p></td>
<td><p><span data-ttu-id="e00ee-138">位元</span><span class="sxs-lookup"><span data-stu-id="e00ee-138">bit</span></span></p></td>
<td><p><span data-ttu-id="e00ee-139">對於類別：</span><span class="sxs-lookup"><span data-stu-id="e00ee-139">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="e00ee-140">如果聊天記錄，則為 true。</span><span class="sxs-lookup"><span data-stu-id="e00ee-140">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="e00ee-141">如果聊天歷程記錄已關閉，則為 false。</span><span class="sxs-lookup"><span data-stu-id="e00ee-141">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="e00ee-142">對於會議室：</span><span class="sxs-lookup"><span data-stu-id="e00ee-142">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="e00ee-143">Null。</span><span class="sxs-lookup"><span data-stu-id="e00ee-143">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e00ee-144">filePost</span><span class="sxs-lookup"><span data-stu-id="e00ee-144">filePost</span></span></p></td>
<td><p><span data-ttu-id="e00ee-145">位元</span><span class="sxs-lookup"><span data-stu-id="e00ee-145">bit</span></span></p></td>
<td><p><span data-ttu-id="e00ee-146">對於類別：</span><span class="sxs-lookup"><span data-stu-id="e00ee-146">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="e00ee-147">如果允許檔案上傳，則為 true。</span><span class="sxs-lookup"><span data-stu-id="e00ee-147">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="e00ee-148">如果不允許檔案上傳，則為 false。</span><span class="sxs-lookup"><span data-stu-id="e00ee-148">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="e00ee-149">對於會議室：</span><span class="sxs-lookup"><span data-stu-id="e00ee-149">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="e00ee-150">Null。</span><span class="sxs-lookup"><span data-stu-id="e00ee-150">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e00ee-151">停用</span><span class="sxs-lookup"><span data-stu-id="e00ee-151">disabled</span></span></p></td>
<td><p><span data-ttu-id="e00ee-152">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="e00ee-152">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="e00ee-153">如果已停用聊天室，則為 true。</span><span class="sxs-lookup"><span data-stu-id="e00ee-153">True if the chat room is disabled.</span></span> <span data-ttu-id="e00ee-154">僅適用於聊天室。</span><span class="sxs-lookup"><span data-stu-id="e00ee-154">Applies only to chat rooms.</span></span> <span data-ttu-id="e00ee-155">(False 類別)。</span><span class="sxs-lookup"><span data-stu-id="e00ee-155">(False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e00ee-156">行為</span><span class="sxs-lookup"><span data-stu-id="e00ee-156">behavior</span></span></p></td>
<td><p><span data-ttu-id="e00ee-157">smallint，非 null</span><span class="sxs-lookup"><span data-stu-id="e00ee-157">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="e00ee-158">行為 （在 EnumValue 表格中查閱）：</span><span class="sxs-lookup"><span data-stu-id="e00ee-158">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="e00ee-159">4： 一般 （一般聊天室）。</span><span class="sxs-lookup"><span data-stu-id="e00ee-159">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="e00ee-160">5： 視聽中心 （視聽中心聊天室，只有簡報者可以參與）。</span><span class="sxs-lookup"><span data-stu-id="e00ee-160">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="e00ee-161">僅適用於聊天室。</span><span class="sxs-lookup"><span data-stu-id="e00ee-161">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e00ee-162">visibility</span><span class="sxs-lookup"><span data-stu-id="e00ee-162">visibility</span></span></p></td>
<td><p><span data-ttu-id="e00ee-163">smallint，非 null</span><span class="sxs-lookup"><span data-stu-id="e00ee-163">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="e00ee-164">可見度 （在 EnumValue 表格中查閱）：</span><span class="sxs-lookup"><span data-stu-id="e00ee-164">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="e00ee-165">2： 私用</span><span class="sxs-lookup"><span data-stu-id="e00ee-165">2: Private</span></span></p></li>
<li><p><span data-ttu-id="e00ee-166">3： 範圍</span><span class="sxs-lookup"><span data-stu-id="e00ee-166">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="e00ee-167">6： 開啟</span><span class="sxs-lookup"><span data-stu-id="e00ee-167">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="e00ee-168">僅適用於聊天室。</span><span class="sxs-lookup"><span data-stu-id="e00ee-168">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e00ee-169">siopID</span><span class="sxs-lookup"><span data-stu-id="e00ee-169">siopID</span></span></p></td>
<td><p><span data-ttu-id="e00ee-170">GUID</span><span class="sxs-lookup"><span data-stu-id="e00ee-170">GUID</span></span></p></td>
<td><p><span data-ttu-id="e00ee-171">增益集的 GUID 如果增益集是此聊天室相關聯。</span><span class="sxs-lookup"><span data-stu-id="e00ee-171">Add-In GUID if an add-in is associated with this chat room.</span></span> <span data-ttu-id="e00ee-172">（類別不需要增益集。）</span><span class="sxs-lookup"><span data-stu-id="e00ee-172">(Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="e00ee-173">增益集的資訊會在 SiopWhiteList 表格中查閱。</span><span class="sxs-lookup"><span data-stu-id="e00ee-173">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e00ee-174">nodeAddedBy</span><span class="sxs-lookup"><span data-stu-id="e00ee-174">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="e00ee-175">int，非 null</span><span class="sxs-lookup"><span data-stu-id="e00ee-175">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e00ee-176">建立此節點之主體的識別碼。</span><span class="sxs-lookup"><span data-stu-id="e00ee-176">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e00ee-177">nodeAddedOn</span><span class="sxs-lookup"><span data-stu-id="e00ee-177">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="e00ee-178">bigint，非 null</span><span class="sxs-lookup"><span data-stu-id="e00ee-178">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="e00ee-179">節點建立的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="e00ee-179">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e00ee-180">nodeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="e00ee-180">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="e00ee-181">int，非 null</span><span class="sxs-lookup"><span data-stu-id="e00ee-181">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e00ee-182">最近一次更新此節點之主體的識別碼。</span><span class="sxs-lookup"><span data-stu-id="e00ee-182">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e00ee-183">nodeUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="e00ee-183">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="e00ee-184">bigint，非 null</span><span class="sxs-lookup"><span data-stu-id="e00ee-184">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="e00ee-185">最近一次此節點更新的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="e00ee-185">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e00ee-186">purgedOn</span><span class="sxs-lookup"><span data-stu-id="e00ee-186">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="e00ee-187">datetime</span><span class="sxs-lookup"><span data-stu-id="e00ee-187">datetime</span></span></p></td>
<td><p><span data-ttu-id="e00ee-188">最新清除作業 （移除從 tblScopedPrincipal 表格的範圍，以及從 tblPrincipalRole 表格角色），此節點會受到影響的時間。</span><span class="sxs-lookup"><span data-stu-id="e00ee-188">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node.</span></span> <span data-ttu-id="e00ee-189">這會使用聊天服務的內部快取更新機制。</span><span class="sxs-lookup"><span data-stu-id="e00ee-189">This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="e00ee-190">索引鍵</span><span class="sxs-lookup"><span data-stu-id="e00ee-190">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e00ee-191">欄</span><span class="sxs-lookup"><span data-stu-id="e00ee-191">Column</span></span></th>
<th><span data-ttu-id="e00ee-192">描述</span><span class="sxs-lookup"><span data-stu-id="e00ee-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e00ee-193">節點識別碼</span><span class="sxs-lookup"><span data-stu-id="e00ee-193">nodeID</span></span></p></td>
<td><p><span data-ttu-id="e00ee-194">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="e00ee-194">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e00ee-195">行為</span><span class="sxs-lookup"><span data-stu-id="e00ee-195">behavior</span></span></p></td>
<td><p><span data-ttu-id="e00ee-196">在 tblEnumValue.valueID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="e00ee-196">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e00ee-197">visibility</span><span class="sxs-lookup"><span data-stu-id="e00ee-197">visibility</span></span></p></td>
<td><p><span data-ttu-id="e00ee-198">在 tblEnumValue.valueID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="e00ee-198">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e00ee-199">parentID</span><span class="sxs-lookup"><span data-stu-id="e00ee-199">parentID</span></span></p></td>
<td><p><span data-ttu-id="e00ee-200">在 tblNode.nodeID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="e00ee-200">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e00ee-201">siopID</span><span class="sxs-lookup"><span data-stu-id="e00ee-201">siopID</span></span></p></td>
<td><p><span data-ttu-id="e00ee-202">在 tblSiopWhiteList.siopId 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="e00ee-202">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

