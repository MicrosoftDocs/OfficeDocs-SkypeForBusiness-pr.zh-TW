---
title: Lync Server 2013： tblPrincipalInvites
description: Lync Server 2013： tblPrincipalInvites。
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
ms.openlocfilehash: d30d741864ed2a3cfbec8329215be33c21b3b262
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564669"
---
# <a name="tblprincipalinvites-in-lync-server-2013"></a><span data-ttu-id="60bb8-103">Lync Server 2013 中的 tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="60bb8-103">tblPrincipalInvites in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60bb8-104">_**主題上次修改日期：** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="60bb8-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="60bb8-105">tblPrincipalInvites 包含所有提供給啟動自動邀請的所有節點之佈建使用者的邀請。</span><span class="sxs-lookup"><span data-stu-id="60bb8-105">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>

### <a name="columns"></a><span data-ttu-id="60bb8-106">Columns</span><span class="sxs-lookup"><span data-stu-id="60bb8-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="60bb8-107">欄</span><span class="sxs-lookup"><span data-stu-id="60bb8-107">Column</span></span></th>
<th><span data-ttu-id="60bb8-108">類型</span><span class="sxs-lookup"><span data-stu-id="60bb8-108">Type</span></span></th>
<th><span data-ttu-id="60bb8-109">描述</span><span class="sxs-lookup"><span data-stu-id="60bb8-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="60bb8-110">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="60bb8-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="60bb8-111">int，非 null</span><span class="sxs-lookup"><span data-stu-id="60bb8-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="60bb8-112">主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="60bb8-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60bb8-113">尹雯德</span><span class="sxs-lookup"><span data-stu-id="60bb8-113">invID</span></span></p></td>
<td><p><span data-ttu-id="60bb8-114">int，非 null</span><span class="sxs-lookup"><span data-stu-id="60bb8-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="60bb8-115">從 tblLastInviteId 表格產生的唯一序號 (每個主體識別碼)。</span><span class="sxs-lookup"><span data-stu-id="60bb8-115">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60bb8-116">nodeID</span><span class="sxs-lookup"><span data-stu-id="60bb8-116">nodeID</span></span></p></td>
<td><p><span data-ttu-id="60bb8-117">int，非 null</span><span class="sxs-lookup"><span data-stu-id="60bb8-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="60bb8-118">節點識別碼 (僅限聊天室)。</span><span class="sxs-lookup"><span data-stu-id="60bb8-118">Node ID (chat room only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60bb8-119">createdOn</span><span class="sxs-lookup"><span data-stu-id="60bb8-119">createdOn</span></span></p></td>
<td><p><span data-ttu-id="60bb8-120">日期時間，非 null</span><span class="sxs-lookup"><span data-stu-id="60bb8-120">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="60bb8-121">建立的時間。</span><span class="sxs-lookup"><span data-stu-id="60bb8-121">Time of creation.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="60bb8-122">索引鍵</span><span class="sxs-lookup"><span data-stu-id="60bb8-122">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="60bb8-123">欄</span><span class="sxs-lookup"><span data-stu-id="60bb8-123">Column</span></span></th>
<th><span data-ttu-id="60bb8-124">描述</span><span class="sxs-lookup"><span data-stu-id="60bb8-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="60bb8-125">&lt;Tblprincipal.prinid，nodeID&gt;</span><span class="sxs-lookup"><span data-stu-id="60bb8-125">&lt;prinID, nodeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="60bb8-126">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="60bb8-126">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60bb8-127">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="60bb8-127">prinID</span></span></p></td>
<td><p><span data-ttu-id="60bb8-128">在 tblPrincipal.prinID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="60bb8-128">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60bb8-129">nodeID</span><span class="sxs-lookup"><span data-stu-id="60bb8-129">nodeID</span></span></p></td>
<td><p><span data-ttu-id="60bb8-130">在 tblNode.nodeID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="60bb8-130">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

