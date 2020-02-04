---
title: Lync Server 2013：tblNode
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
ms.openlocfilehash: 24ba45d9ba650a9de4359d64e3281fb488b6a279
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="d1538-102">Lync Server 2013 中的 tblNode</span><span class="sxs-lookup"><span data-stu-id="d1538-102">tblNode in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1538-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="d1538-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="d1538-104">tblNode 包含在 Lync Server 2013 [控制台] 和 [管理 Cmdlet] 中管理的物件樹狀結構（具有類別或聊天室節點）。</span><span class="sxs-lookup"><span data-stu-id="d1538-104">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="d1538-105">分欄</span><span class="sxs-lookup"><span data-stu-id="d1538-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1538-106">左欄</span><span class="sxs-lookup"><span data-stu-id="d1538-106">Column</span></span></th>
<th><span data-ttu-id="d1538-107">類型</span><span class="sxs-lookup"><span data-stu-id="d1538-107">Type</span></span></th>
<th><span data-ttu-id="d1538-108">說明</span><span class="sxs-lookup"><span data-stu-id="d1538-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1538-109">個</span><span class="sxs-lookup"><span data-stu-id="d1538-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="d1538-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="d1538-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d1538-111">節點識別碼（唯一編號）。</span><span class="sxs-lookup"><span data-stu-id="d1538-111">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1538-112">nodeGuid</span><span class="sxs-lookup"><span data-stu-id="d1538-112">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="d1538-113">GUID，不是 null</span><span class="sxs-lookup"><span data-stu-id="d1538-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="d1538-114">節點 GUID。</span><span class="sxs-lookup"><span data-stu-id="d1538-114">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1538-115">parentID</span><span class="sxs-lookup"><span data-stu-id="d1538-115">parentID</span></span></p></td>
<td><p><span data-ttu-id="d1538-116">int</span><span class="sxs-lookup"><span data-stu-id="d1538-116">int</span></span></p></td>
<td><p><span data-ttu-id="d1538-117">父級的節點識別碼。</span><span class="sxs-lookup"><span data-stu-id="d1538-117">Node ID of parent.</span></span> <span data-ttu-id="d1538-118">根節點（含 ID 1）也會將它本身包含在父級中。</span><span class="sxs-lookup"><span data-stu-id="d1538-118">The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1538-119">nodeType</span><span class="sxs-lookup"><span data-stu-id="d1538-119">nodeType</span></span></p></td>
<td><p><span data-ttu-id="d1538-120">bit、not null</span><span class="sxs-lookup"><span data-stu-id="d1538-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="d1538-121">如果節點是類別，則為 True。</span><span class="sxs-lookup"><span data-stu-id="d1538-121">True if the node is a category.</span></span></p>
<p><span data-ttu-id="d1538-122">如果該節點是聊天室，則為 False。</span><span class="sxs-lookup"><span data-stu-id="d1538-122">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1538-123">nodeName</span><span class="sxs-lookup"><span data-stu-id="d1538-123">nodeName</span></span></p></td>
<td><p><span data-ttu-id="d1538-124">Nvarchar （256），not null</span><span class="sxs-lookup"><span data-stu-id="d1538-124">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="d1538-125">節點名稱。</span><span class="sxs-lookup"><span data-stu-id="d1538-125">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1538-126">nodeDesc</span><span class="sxs-lookup"><span data-stu-id="d1538-126">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="d1538-127">Nvarchar （256），not null</span><span class="sxs-lookup"><span data-stu-id="d1538-127">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="d1538-128">[節點描述]。</span><span class="sxs-lookup"><span data-stu-id="d1538-128">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1538-129">參加</span><span class="sxs-lookup"><span data-stu-id="d1538-129">invite</span></span></p></td>
<td><p><span data-ttu-id="d1538-130">稍微</span><span class="sxs-lookup"><span data-stu-id="d1538-130">bit</span></span></p></td>
<td><p><span data-ttu-id="d1538-131">針對類別：</span><span class="sxs-lookup"><span data-stu-id="d1538-131">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="d1538-132">如果邀請開啟，則為 True。</span><span class="sxs-lookup"><span data-stu-id="d1538-132">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="d1538-133">如果邀請關閉，則為 False。</span><span class="sxs-lookup"><span data-stu-id="d1538-133">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="d1538-134">會議室：</span><span class="sxs-lookup"><span data-stu-id="d1538-134">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="d1538-135">如果邀請關閉，則為 False （覆寫上層類別）。</span><span class="sxs-lookup"><span data-stu-id="d1538-135">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="d1538-136">如果 [邀請] 設定繼承自上層類別，則為 Null。</span><span class="sxs-lookup"><span data-stu-id="d1538-136">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1538-137">註冊</span><span class="sxs-lookup"><span data-stu-id="d1538-137">logged</span></span></p></td>
<td><p><span data-ttu-id="d1538-138">稍微</span><span class="sxs-lookup"><span data-stu-id="d1538-138">bit</span></span></p></td>
<td><p><span data-ttu-id="d1538-139">針對類別：</span><span class="sxs-lookup"><span data-stu-id="d1538-139">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="d1538-140">如果聊天記錄開啟，則為 True。</span><span class="sxs-lookup"><span data-stu-id="d1538-140">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="d1538-141">如果聊天記錄為關閉，則為 False。</span><span class="sxs-lookup"><span data-stu-id="d1538-141">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="d1538-142">會議室：</span><span class="sxs-lookup"><span data-stu-id="d1538-142">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="d1538-143">非.</span><span class="sxs-lookup"><span data-stu-id="d1538-143">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1538-144">filePost</span><span class="sxs-lookup"><span data-stu-id="d1538-144">filePost</span></span></p></td>
<td><p><span data-ttu-id="d1538-145">稍微</span><span class="sxs-lookup"><span data-stu-id="d1538-145">bit</span></span></p></td>
<td><p><span data-ttu-id="d1538-146">針對類別：</span><span class="sxs-lookup"><span data-stu-id="d1538-146">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="d1538-147">如果允許檔案上傳，則為 True。</span><span class="sxs-lookup"><span data-stu-id="d1538-147">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="d1538-148">如果不允許檔案上傳，則為 False。</span><span class="sxs-lookup"><span data-stu-id="d1538-148">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="d1538-149">會議室：</span><span class="sxs-lookup"><span data-stu-id="d1538-149">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="d1538-150">非.</span><span class="sxs-lookup"><span data-stu-id="d1538-150">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1538-151">禁止</span><span class="sxs-lookup"><span data-stu-id="d1538-151">disabled</span></span></p></td>
<td><p><span data-ttu-id="d1538-152">bit、not null</span><span class="sxs-lookup"><span data-stu-id="d1538-152">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="d1538-153">如果停用聊天室，則為 True。</span><span class="sxs-lookup"><span data-stu-id="d1538-153">True if the chat room is disabled.</span></span> <span data-ttu-id="d1538-154">僅適用于聊天室。</span><span class="sxs-lookup"><span data-stu-id="d1538-154">Applies only to chat rooms.</span></span> <span data-ttu-id="d1538-155">（[類別] 為 False）。</span><span class="sxs-lookup"><span data-stu-id="d1538-155">(False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1538-156">行為</span><span class="sxs-lookup"><span data-stu-id="d1538-156">behavior</span></span></p></td>
<td><p><span data-ttu-id="d1538-157">Smallint，not null</span><span class="sxs-lookup"><span data-stu-id="d1538-157">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="d1538-158">行為（在 EnumValue 資料表中查閱）：</span><span class="sxs-lookup"><span data-stu-id="d1538-158">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="d1538-159">4：標準（標準聊天室）。</span><span class="sxs-lookup"><span data-stu-id="d1538-159">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="d1538-160">5： Auditorium （Auditorium 聊天室，只有簡報者可以參與）。</span><span class="sxs-lookup"><span data-stu-id="d1538-160">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="d1538-161">僅適用于聊天室。</span><span class="sxs-lookup"><span data-stu-id="d1538-161">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1538-162">看見</span><span class="sxs-lookup"><span data-stu-id="d1538-162">visibility</span></span></p></td>
<td><p><span data-ttu-id="d1538-163">Smallint，not null</span><span class="sxs-lookup"><span data-stu-id="d1538-163">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="d1538-164">可見度（在 EnumValue 表格上查閱）：</span><span class="sxs-lookup"><span data-stu-id="d1538-164">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="d1538-165">2：私人</span><span class="sxs-lookup"><span data-stu-id="d1538-165">2: Private</span></span></p></li>
<li><p><span data-ttu-id="d1538-166">3：範圍</span><span class="sxs-lookup"><span data-stu-id="d1538-166">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="d1538-167">6：開啟</span><span class="sxs-lookup"><span data-stu-id="d1538-167">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="d1538-168">僅適用于聊天室。</span><span class="sxs-lookup"><span data-stu-id="d1538-168">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1538-169">siopID</span><span class="sxs-lookup"><span data-stu-id="d1538-169">siopID</span></span></p></td>
<td><p><span data-ttu-id="d1538-170">GUID</span><span class="sxs-lookup"><span data-stu-id="d1538-170">GUID</span></span></p></td>
<td><p><span data-ttu-id="d1538-171">增益集 GUID （如果增益集與此聊天室相關聯）。</span><span class="sxs-lookup"><span data-stu-id="d1538-171">Add-In GUID if an add-in is associated with this chat room.</span></span> <span data-ttu-id="d1538-172">（類別沒有增益集）。</span><span class="sxs-lookup"><span data-stu-id="d1538-172">(Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="d1538-173">增益集資訊是在 SiopWhiteList 表格中尋找。</span><span class="sxs-lookup"><span data-stu-id="d1538-173">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1538-174">nodeAddedBy</span><span class="sxs-lookup"><span data-stu-id="d1538-174">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="d1538-175">int，not null</span><span class="sxs-lookup"><span data-stu-id="d1538-175">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d1538-176">建立此節點之主體的 ID。</span><span class="sxs-lookup"><span data-stu-id="d1538-176">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1538-177">nodeAddedOn</span><span class="sxs-lookup"><span data-stu-id="d1538-177">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="d1538-178">Bigint，not null</span><span class="sxs-lookup"><span data-stu-id="d1538-178">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="d1538-179">節點建立的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="d1538-179">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1538-180">nodeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="d1538-180">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="d1538-181">int，not null</span><span class="sxs-lookup"><span data-stu-id="d1538-181">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d1538-182">已執行此節點最新更新之主體的 ID。</span><span class="sxs-lookup"><span data-stu-id="d1538-182">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1538-183">nodeUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="d1538-183">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="d1538-184">Bigint，not null</span><span class="sxs-lookup"><span data-stu-id="d1538-184">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="d1538-185">此節點最新更新的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="d1538-185">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1538-186">purgedOn</span><span class="sxs-lookup"><span data-stu-id="d1538-186">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="d1538-187">datetime</span><span class="sxs-lookup"><span data-stu-id="d1538-187">datetime</span></span></p></td>
<td><p><span data-ttu-id="d1538-188">最新清除作業的時間（從 tblScopedPrincipal 資料表中移除作用中的範圍，以及從 tblPrincipalRole 資料表移除角色），這會影響這個節點。</span><span class="sxs-lookup"><span data-stu-id="d1538-188">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node.</span></span> <span data-ttu-id="d1538-189">這是由聊天服務的內部快取機制所使用。</span><span class="sxs-lookup"><span data-stu-id="d1538-189">This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="d1538-190">鍵</span><span class="sxs-lookup"><span data-stu-id="d1538-190">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1538-191">左欄</span><span class="sxs-lookup"><span data-stu-id="d1538-191">Column</span></span></th>
<th><span data-ttu-id="d1538-192">說明</span><span class="sxs-lookup"><span data-stu-id="d1538-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1538-193">個</span><span class="sxs-lookup"><span data-stu-id="d1538-193">nodeID</span></span></p></td>
<td><p><span data-ttu-id="d1538-194">主鍵。</span><span class="sxs-lookup"><span data-stu-id="d1538-194">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1538-195">行為</span><span class="sxs-lookup"><span data-stu-id="d1538-195">behavior</span></span></p></td>
<td><p><span data-ttu-id="d1538-196">在 tblEnumValue valueID 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="d1538-196">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1538-197">看見</span><span class="sxs-lookup"><span data-stu-id="d1538-197">visibility</span></span></p></td>
<td><p><span data-ttu-id="d1538-198">在 tblEnumValue valueID 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="d1538-198">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1538-199">parentID</span><span class="sxs-lookup"><span data-stu-id="d1538-199">parentID</span></span></p></td>
<td><p><span data-ttu-id="d1538-200">在 tblNode 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="d1538-200">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1538-201">siopID</span><span class="sxs-lookup"><span data-stu-id="d1538-201">siopID</span></span></p></td>
<td><p><span data-ttu-id="d1538-202">在 tblSiopWhiteList siopId 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="d1538-202">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

