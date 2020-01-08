---
title: Lync Server 2013：tblScopePrincipal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblScopePrincipal
ms:assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558639(v=OCS.15)
ms:contentKeyID: 48184009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ece5ae542060835aefa05edb6e08b766293e2ac1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblscopeprincipal-in-lync-server-2013"></a><span data-ttu-id="9c968-102">Lync Server 2013 中的 tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="9c968-102">tblScopePrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c968-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="9c968-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="9c968-104">tblScopePrincipal 包含指派給節點的作用中。</span><span class="sxs-lookup"><span data-stu-id="9c968-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="9c968-105">分欄</span><span class="sxs-lookup"><span data-stu-id="9c968-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c968-106">左欄</span><span class="sxs-lookup"><span data-stu-id="9c968-106">Column</span></span></th>
<th><span data-ttu-id="9c968-107">類型</span><span class="sxs-lookup"><span data-stu-id="9c968-107">Type</span></span></th>
<th><span data-ttu-id="9c968-108">描述</span><span class="sxs-lookup"><span data-stu-id="9c968-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c968-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="9c968-109">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="9c968-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="9c968-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9c968-111">作用中所適用的節點識別碼。</span><span class="sxs-lookup"><span data-stu-id="9c968-111">Node ID that the scope applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c968-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="9c968-112">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="9c968-113">int，not null</span><span class="sxs-lookup"><span data-stu-id="9c968-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9c968-114">Principal ID。</span><span class="sxs-lookup"><span data-stu-id="9c968-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c968-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="9c968-115">scopeIsDenied</span></span></p></td>
<td><p><span data-ttu-id="9c968-116">bit、not null</span><span class="sxs-lookup"><span data-stu-id="9c968-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="9c968-117">如果範圍類型為 Deny，則為 True;如果允許，則為 False。</span><span class="sxs-lookup"><span data-stu-id="9c968-117">True if type of scope is Deny; False if Allow.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c968-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="9c968-118">scopeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="9c968-119">int，not null</span><span class="sxs-lookup"><span data-stu-id="9c968-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9c968-120">上次更新此專案的主體 ID。</span><span class="sxs-lookup"><span data-stu-id="9c968-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="9c968-121">鍵</span><span class="sxs-lookup"><span data-stu-id="9c968-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c968-122">左欄</span><span class="sxs-lookup"><span data-stu-id="9c968-122">Column</span></span></th>
<th><span data-ttu-id="9c968-123">描述</span><span class="sxs-lookup"><span data-stu-id="9c968-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c968-124">&lt;scopeNodeID, scopePrinID&gt;</span><span class="sxs-lookup"><span data-stu-id="9c968-124">&lt;scopeNodeID, scopePrinID&gt;</span></span></p></td>
<td><p><span data-ttu-id="9c968-125">主鍵。</span><span class="sxs-lookup"><span data-stu-id="9c968-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c968-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="9c968-126">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="9c968-127">在 tblNode 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="9c968-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c968-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="9c968-128">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="9c968-129">在 tblPrincipal prinID 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="9c968-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

