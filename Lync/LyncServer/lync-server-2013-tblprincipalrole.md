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
ms.openlocfilehash: 685e8ae3e767e3dc237da1698fd593a9c56021c8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalrole-in-lync-server-2013"></a><span data-ttu-id="7e439-102">Lync Server 2013 中的 tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="7e439-102">tblPrincipalRole in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e439-103">_**主題上次修改日期：** 2012年-09-12_</span><span class="sxs-lookup"><span data-stu-id="7e439-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="7e439-104">tblPrincipalRole 包含指派給節點的明確角色。</span><span class="sxs-lookup"><span data-stu-id="7e439-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="7e439-105">Columns</span><span class="sxs-lookup"><span data-stu-id="7e439-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e439-106">欄</span><span class="sxs-lookup"><span data-stu-id="7e439-106">Column</span></span></th>
<th><span data-ttu-id="7e439-107">類型	</span><span class="sxs-lookup"><span data-stu-id="7e439-107">Type</span></span></th>
<th><span data-ttu-id="7e439-108">描述</span><span class="sxs-lookup"><span data-stu-id="7e439-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e439-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="7e439-109">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="7e439-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="7e439-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="7e439-111">套用角色的節點識別碼。</span><span class="sxs-lookup"><span data-stu-id="7e439-111">Node ID that the role applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e439-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="7e439-112">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="7e439-113">int，非 null</span><span class="sxs-lookup"><span data-stu-id="7e439-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="7e439-114">主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="7e439-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e439-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="7e439-115">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="7e439-116">int，非 null</span><span class="sxs-lookup"><span data-stu-id="7e439-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="7e439-117">角色類型識別碼 （來自於 tblRoleType)。</span><span class="sxs-lookup"><span data-stu-id="7e439-117">Role type ID (from tblRoleType).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e439-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="7e439-118">prinRoleUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="7e439-119">int，非 null</span><span class="sxs-lookup"><span data-stu-id="7e439-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="7e439-120">上次更新此項目之主體的識別碼。</span><span class="sxs-lookup"><span data-stu-id="7e439-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="7e439-121">索引鍵</span><span class="sxs-lookup"><span data-stu-id="7e439-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e439-122">欄</span><span class="sxs-lookup"><span data-stu-id="7e439-122">Column</span></span></th>
<th><span data-ttu-id="7e439-123">描述</span><span class="sxs-lookup"><span data-stu-id="7e439-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e439-124">&lt;prinRoleNodeID，prinRolePrinID prinRoleTypeID&gt;</span><span class="sxs-lookup"><span data-stu-id="7e439-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="7e439-125">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="7e439-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e439-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="7e439-126">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="7e439-127">在 tblNode.nodeID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="7e439-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e439-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="7e439-128">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="7e439-129">在 tblPrincipal.prinID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="7e439-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e439-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="7e439-130">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="7e439-131">在 tblRoleType.rtypeID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="7e439-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

