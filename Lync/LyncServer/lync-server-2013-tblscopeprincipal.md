---
title: Lync Server 2013： tblScopePrincipal
description: Lync Server 2013： tblScopePrincipal。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblScopePrincipal
ms:assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558639(v=OCS.15)
ms:contentKeyID: 48184009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63315f8525e5c2f05fe54a0f9ed9e8a97b9e8bce
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555609"
---
# <a name="tblscopeprincipal-in-lync-server-2013"></a><span data-ttu-id="376fb-103">Lync Server 2013 中的 tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="376fb-103">tblScopePrincipal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="376fb-104">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="376fb-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="376fb-105">tblScopePrincipal 包含指派給節點的範圍。</span><span class="sxs-lookup"><span data-stu-id="376fb-105">tblScopePrincipal contains scopes assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="376fb-106">Columns</span><span class="sxs-lookup"><span data-stu-id="376fb-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="376fb-107">欄</span><span class="sxs-lookup"><span data-stu-id="376fb-107">Column</span></span></th>
<th><span data-ttu-id="376fb-108">類型</span><span class="sxs-lookup"><span data-stu-id="376fb-108">Type</span></span></th>
<th><span data-ttu-id="376fb-109">描述</span><span class="sxs-lookup"><span data-stu-id="376fb-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="376fb-110">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="376fb-110">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="376fb-111">int，非 null</span><span class="sxs-lookup"><span data-stu-id="376fb-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="376fb-112">套用範圍的節點識別碼。</span><span class="sxs-lookup"><span data-stu-id="376fb-112">Node ID that the scope applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="376fb-113">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="376fb-113">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="376fb-114">int，非 null</span><span class="sxs-lookup"><span data-stu-id="376fb-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="376fb-115">主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="376fb-115">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="376fb-116">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="376fb-116">scopeIsDenied</span></span></p></td>
<td><p><span data-ttu-id="376fb-117">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="376fb-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="376fb-118">True 是表示如果範圍的類型是 Deny;False 表示允許。</span><span class="sxs-lookup"><span data-stu-id="376fb-118">True if type of scope is Deny; False if Allow.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="376fb-119">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="376fb-119">scopeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="376fb-120">int，非 null</span><span class="sxs-lookup"><span data-stu-id="376fb-120">int, not null</span></span></p></td>
<td><p><span data-ttu-id="376fb-121">最後更新此專案的主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="376fb-121">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="376fb-122">索引鍵</span><span class="sxs-lookup"><span data-stu-id="376fb-122">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="376fb-123">欄</span><span class="sxs-lookup"><span data-stu-id="376fb-123">Column</span></span></th>
<th><span data-ttu-id="376fb-124">描述</span><span class="sxs-lookup"><span data-stu-id="376fb-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="376fb-125">&lt;scopeNodeID, scopePrinID&gt;</span><span class="sxs-lookup"><span data-stu-id="376fb-125">&lt;scopeNodeID, scopePrinID&gt;</span></span></p></td>
<td><p><span data-ttu-id="376fb-126">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="376fb-126">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="376fb-127">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="376fb-127">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="376fb-128">在 tblNode.nodeID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="376fb-128">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="376fb-129">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="376fb-129">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="376fb-130">在 tblPrincipal.prinID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="376fb-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

