---
title: Lync Server 2013：tblPrincipalInvites
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalInvites
ms:assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558650(v=OCS.15)
ms:contentKeyID: 48184141
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75d842772c8c0e02352eacf7f80711aa79c29461
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731523"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalinvites-in-lync-server-2013"></a><span data-ttu-id="1d4c2-102">Lync Server 2013 中的 tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="1d4c2-102">tblPrincipalInvites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d4c2-103">_**主題上次修改日期：** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="1d4c2-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="1d4c2-104">tblPrincipalInvites 包含所有擁有自動邀請之節點之已預配使用者的邀請。</span><span class="sxs-lookup"><span data-stu-id="1d4c2-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>

### <a name="columns"></a><span data-ttu-id="1d4c2-105">分欄</span><span class="sxs-lookup"><span data-stu-id="1d4c2-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1d4c2-106">左欄</span><span class="sxs-lookup"><span data-stu-id="1d4c2-106">Column</span></span></th>
<th><span data-ttu-id="1d4c2-107">類型</span><span class="sxs-lookup"><span data-stu-id="1d4c2-107">Type</span></span></th>
<th><span data-ttu-id="1d4c2-108">說明</span><span class="sxs-lookup"><span data-stu-id="1d4c2-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d4c2-109">prinID</span><span class="sxs-lookup"><span data-stu-id="1d4c2-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="1d4c2-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="1d4c2-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="1d4c2-111">Principal ID。</span><span class="sxs-lookup"><span data-stu-id="1d4c2-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d4c2-112">invID</span><span class="sxs-lookup"><span data-stu-id="1d4c2-112">invID</span></span></p></td>
<td><p><span data-ttu-id="1d4c2-113">int，not null</span><span class="sxs-lookup"><span data-stu-id="1d4c2-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="1d4c2-114">從 tblLastInviteId 資料表產生的唯一順序編號（每個主體識別碼）。</span><span class="sxs-lookup"><span data-stu-id="1d4c2-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d4c2-115">個</span><span class="sxs-lookup"><span data-stu-id="1d4c2-115">nodeID</span></span></p></td>
<td><p><span data-ttu-id="1d4c2-116">int，not null</span><span class="sxs-lookup"><span data-stu-id="1d4c2-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="1d4c2-117">節點識別碼（僅適用于聊天室）。</span><span class="sxs-lookup"><span data-stu-id="1d4c2-117">Node ID (chat room only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d4c2-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="1d4c2-118">createdOn</span></span></p></td>
<td><p><span data-ttu-id="1d4c2-119">datetime、not null</span><span class="sxs-lookup"><span data-stu-id="1d4c2-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="1d4c2-120">建立時間。</span><span class="sxs-lookup"><span data-stu-id="1d4c2-120">Time of creation.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="1d4c2-121">鍵</span><span class="sxs-lookup"><span data-stu-id="1d4c2-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1d4c2-122">左欄</span><span class="sxs-lookup"><span data-stu-id="1d4c2-122">Column</span></span></th>
<th><span data-ttu-id="1d4c2-123">說明</span><span class="sxs-lookup"><span data-stu-id="1d4c2-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d4c2-124">&lt;prinID、&gt;</span><span class="sxs-lookup"><span data-stu-id="1d4c2-124">&lt;prinID, nodeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="1d4c2-125">主鍵。</span><span class="sxs-lookup"><span data-stu-id="1d4c2-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d4c2-126">prinID</span><span class="sxs-lookup"><span data-stu-id="1d4c2-126">prinID</span></span></p></td>
<td><p><span data-ttu-id="1d4c2-127">在 tblPrincipal prinID 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="1d4c2-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d4c2-128">個</span><span class="sxs-lookup"><span data-stu-id="1d4c2-128">nodeID</span></span></p></td>
<td><p><span data-ttu-id="1d4c2-129">在 tblNode 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="1d4c2-129">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

