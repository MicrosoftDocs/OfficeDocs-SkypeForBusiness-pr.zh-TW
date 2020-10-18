---
title: Lync Server 2013： tblPrincipalRole
description: Lync Server 2013： tblPrincipalRole。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalRole
ms:assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615039(v=OCS.15)
ms:contentKeyID: 48185597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f58ffda3136c254ee77f14d33dcb42af5d172c4a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573629"
---
# <a name="tblprincipalrole-in-lync-server-2013"></a><span data-ttu-id="30b63-103">Lync Server 2013 中的 tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="30b63-103">tblPrincipalRole in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30b63-104">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="30b63-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="30b63-105">tblPrincipalRole 包含指派給節點的明確角色。</span><span class="sxs-lookup"><span data-stu-id="30b63-105">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="30b63-106">Columns</span><span class="sxs-lookup"><span data-stu-id="30b63-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="30b63-107">欄</span><span class="sxs-lookup"><span data-stu-id="30b63-107">Column</span></span></th>
<th><span data-ttu-id="30b63-108">類型</span><span class="sxs-lookup"><span data-stu-id="30b63-108">Type</span></span></th>
<th><span data-ttu-id="30b63-109">描述</span><span class="sxs-lookup"><span data-stu-id="30b63-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30b63-110">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="30b63-110">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="30b63-111">int，非 null</span><span class="sxs-lookup"><span data-stu-id="30b63-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="30b63-112">套用角色的節點識別碼。</span><span class="sxs-lookup"><span data-stu-id="30b63-112">Node ID that the role applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30b63-113">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="30b63-113">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="30b63-114">int，非 null</span><span class="sxs-lookup"><span data-stu-id="30b63-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="30b63-115">主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="30b63-115">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30b63-116">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="30b63-116">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="30b63-117">int，非 null</span><span class="sxs-lookup"><span data-stu-id="30b63-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="30b63-118">TblRoleType) 的角色類型識別碼 (。</span><span class="sxs-lookup"><span data-stu-id="30b63-118">Role type ID (from tblRoleType).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30b63-119">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="30b63-119">prinRoleUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="30b63-120">int，非 null</span><span class="sxs-lookup"><span data-stu-id="30b63-120">int, not null</span></span></p></td>
<td><p><span data-ttu-id="30b63-121">最後更新此專案的主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="30b63-121">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="30b63-122">索引鍵</span><span class="sxs-lookup"><span data-stu-id="30b63-122">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="30b63-123">欄</span><span class="sxs-lookup"><span data-stu-id="30b63-123">Column</span></span></th>
<th><span data-ttu-id="30b63-124">描述</span><span class="sxs-lookup"><span data-stu-id="30b63-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30b63-125">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span><span class="sxs-lookup"><span data-stu-id="30b63-125">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="30b63-126">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="30b63-126">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30b63-127">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="30b63-127">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="30b63-128">在 tblNode.nodeID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="30b63-128">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30b63-129">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="30b63-129">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="30b63-130">在 tblPrincipal.prinID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="30b63-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30b63-131">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="30b63-131">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="30b63-132">在 tblRoleType.rtypeID 表格中查閱的外鍵。</span><span class="sxs-lookup"><span data-stu-id="30b63-132">Foreign key with lookup in tblRoleType.rtypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

