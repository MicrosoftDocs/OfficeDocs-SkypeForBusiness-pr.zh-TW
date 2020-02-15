---
title: 'Lync Server 2013: tblScopePrincipal'
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
ms.openlocfilehash: ab3faccea0ba914ca17c9aefcd0ea112e5b58a96
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037473"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblscopeprincipal-in-lync-server-2013"></a><span data-ttu-id="f9277-102">Lync Server 2013 中的 tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="f9277-102">tblScopePrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9277-103">_**主題上次修改日期：** 2012年-09-12_</span><span class="sxs-lookup"><span data-stu-id="f9277-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="f9277-104">tblScopePrincipal 包含指派給節點的範圍。</span><span class="sxs-lookup"><span data-stu-id="f9277-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="f9277-105">Columns</span><span class="sxs-lookup"><span data-stu-id="f9277-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9277-106">欄</span><span class="sxs-lookup"><span data-stu-id="f9277-106">Column</span></span></th>
<th><span data-ttu-id="f9277-107">類型	</span><span class="sxs-lookup"><span data-stu-id="f9277-107">Type</span></span></th>
<th><span data-ttu-id="f9277-108">描述</span><span class="sxs-lookup"><span data-stu-id="f9277-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9277-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="f9277-109">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="f9277-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="f9277-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f9277-111">若要套用該範圍的節點識別碼。</span><span class="sxs-lookup"><span data-stu-id="f9277-111">Node ID that the scope applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9277-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="f9277-112">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="f9277-113">int，非 null</span><span class="sxs-lookup"><span data-stu-id="f9277-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f9277-114">主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="f9277-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9277-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="f9277-115">scopeIsDenied</span></span></p></td>
<td><p><span data-ttu-id="f9277-116">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="f9277-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="f9277-117">True 是表示如果範圍類型是 Deny;False 表示允許。</span><span class="sxs-lookup"><span data-stu-id="f9277-117">True if type of scope is Deny; False if Allow.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9277-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="f9277-118">scopeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="f9277-119">int，非 null</span><span class="sxs-lookup"><span data-stu-id="f9277-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f9277-120">上次更新此項目之主體的識別碼。</span><span class="sxs-lookup"><span data-stu-id="f9277-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="f9277-121">索引鍵</span><span class="sxs-lookup"><span data-stu-id="f9277-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9277-122">欄</span><span class="sxs-lookup"><span data-stu-id="f9277-122">Column</span></span></th>
<th><span data-ttu-id="f9277-123">描述</span><span class="sxs-lookup"><span data-stu-id="f9277-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9277-124">&lt;scopeNodeID scopePrinID&gt;</span><span class="sxs-lookup"><span data-stu-id="f9277-124">&lt;scopeNodeID, scopePrinID&gt;</span></span></p></td>
<td><p><span data-ttu-id="f9277-125">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="f9277-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9277-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="f9277-126">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="f9277-127">在 tblNode.nodeID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="f9277-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9277-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="f9277-128">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="f9277-129">在 tblPrincipal.prinID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="f9277-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

