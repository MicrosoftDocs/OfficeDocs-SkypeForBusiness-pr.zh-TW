---
title: 'Lync Server 2013: tblPrincipalRole'
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
ms.openlocfilehash: d4da9525e81856989c5d5046e43b2277ca6a8b2a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalrole-in-lync-server-2013"></a><span data-ttu-id="bcd73-102">Lync Server 2013 中的 tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="bcd73-102">tblPrincipalRole in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bcd73-103">_**主題上次修改日期：** 2012年-09-12_</span><span class="sxs-lookup"><span data-stu-id="bcd73-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="bcd73-104">tblPrincipalRole 包含指派給節點的明確角色。</span><span class="sxs-lookup"><span data-stu-id="bcd73-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="bcd73-105">Columns</span><span class="sxs-lookup"><span data-stu-id="bcd73-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bcd73-106">欄</span><span class="sxs-lookup"><span data-stu-id="bcd73-106">Column</span></span></th>
<th><span data-ttu-id="bcd73-107">類型	</span><span class="sxs-lookup"><span data-stu-id="bcd73-107">Type</span></span></th>
<th><span data-ttu-id="bcd73-108">描述</span><span class="sxs-lookup"><span data-stu-id="bcd73-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bcd73-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="bcd73-109">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="bcd73-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="bcd73-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="bcd73-111">套用角色的節點識別碼。</span><span class="sxs-lookup"><span data-stu-id="bcd73-111">Node ID that the role applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcd73-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="bcd73-112">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="bcd73-113">int，非 null</span><span class="sxs-lookup"><span data-stu-id="bcd73-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="bcd73-114">主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="bcd73-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcd73-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="bcd73-115">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="bcd73-116">int，非 null</span><span class="sxs-lookup"><span data-stu-id="bcd73-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="bcd73-117">角色類型識別碼 （來自於 tblRoleType)。</span><span class="sxs-lookup"><span data-stu-id="bcd73-117">Role type ID (from tblRoleType).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcd73-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="bcd73-118">prinRoleUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="bcd73-119">int，非 null</span><span class="sxs-lookup"><span data-stu-id="bcd73-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="bcd73-120">上次更新此項目之主體的識別碼。</span><span class="sxs-lookup"><span data-stu-id="bcd73-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="bcd73-121">索引鍵</span><span class="sxs-lookup"><span data-stu-id="bcd73-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bcd73-122">欄</span><span class="sxs-lookup"><span data-stu-id="bcd73-122">Column</span></span></th>
<th><span data-ttu-id="bcd73-123">描述</span><span class="sxs-lookup"><span data-stu-id="bcd73-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bcd73-124">&lt;prinRoleNodeID，prinRolePrinID prinRoleTypeID&gt;</span><span class="sxs-lookup"><span data-stu-id="bcd73-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="bcd73-125">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="bcd73-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcd73-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="bcd73-126">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="bcd73-127">在 tblNode.nodeID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="bcd73-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcd73-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="bcd73-128">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="bcd73-129">在 tblPrincipal.prinID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="bcd73-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcd73-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="bcd73-130">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="bcd73-131">在 tblRoleType.rtypeID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="bcd73-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

