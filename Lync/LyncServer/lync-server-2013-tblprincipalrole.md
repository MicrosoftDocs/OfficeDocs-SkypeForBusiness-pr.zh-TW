---
title: Lync Server 2013： tblPrincipalRole
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
ms.openlocfilehash: 76dda06baa4e5fab51ca44586f7f8fce00860695
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523610"
---
# <a name="tblprincipalrole-in-lync-server-2013"></a><span data-ttu-id="322a3-102">Lync Server 2013 中的 tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="322a3-102">tblPrincipalRole in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="322a3-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="322a3-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="322a3-104">tblPrincipalRole 包含指派給節點的明確角色。</span><span class="sxs-lookup"><span data-stu-id="322a3-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="322a3-105">Columns</span><span class="sxs-lookup"><span data-stu-id="322a3-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="322a3-106">欄</span><span class="sxs-lookup"><span data-stu-id="322a3-106">Column</span></span></th>
<th><span data-ttu-id="322a3-107">類型</span><span class="sxs-lookup"><span data-stu-id="322a3-107">Type</span></span></th>
<th><span data-ttu-id="322a3-108">描述</span><span class="sxs-lookup"><span data-stu-id="322a3-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="322a3-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="322a3-109">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="322a3-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="322a3-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="322a3-111">套用角色的節點識別碼。</span><span class="sxs-lookup"><span data-stu-id="322a3-111">Node ID that the role applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322a3-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="322a3-112">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="322a3-113">int，非 null</span><span class="sxs-lookup"><span data-stu-id="322a3-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="322a3-114">主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="322a3-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322a3-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="322a3-115">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="322a3-116">int，非 null</span><span class="sxs-lookup"><span data-stu-id="322a3-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="322a3-117">TblRoleType) 的角色類型識別碼 (。</span><span class="sxs-lookup"><span data-stu-id="322a3-117">Role type ID (from tblRoleType).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322a3-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="322a3-118">prinRoleUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="322a3-119">int，非 null</span><span class="sxs-lookup"><span data-stu-id="322a3-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="322a3-120">最後更新此專案的主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="322a3-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="322a3-121">索引鍵</span><span class="sxs-lookup"><span data-stu-id="322a3-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="322a3-122">欄</span><span class="sxs-lookup"><span data-stu-id="322a3-122">Column</span></span></th>
<th><span data-ttu-id="322a3-123">描述</span><span class="sxs-lookup"><span data-stu-id="322a3-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="322a3-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span><span class="sxs-lookup"><span data-stu-id="322a3-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="322a3-125">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="322a3-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322a3-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="322a3-126">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="322a3-127">在 tblNode.nodeID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="322a3-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322a3-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="322a3-128">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="322a3-129">在 tblPrincipal.prinID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="322a3-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322a3-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="322a3-130">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="322a3-131">在 tblRoleType.rtypeID 表格中查閱的外鍵。</span><span class="sxs-lookup"><span data-stu-id="322a3-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

