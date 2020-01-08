---
title: Lync Server 2013：tblPrincipalRole
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalRole
ms:assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615039(v=OCS.15)
ms:contentKeyID: 48185597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 560f454531060a8458c8c920a1e4c5921867f3e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975388"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalrole-in-lync-server-2013"></a><span data-ttu-id="9cd45-102">Lync Server 2013 中的 tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="9cd45-102">tblPrincipalRole in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9cd45-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="9cd45-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="9cd45-104">tblPrincipalRole 包含指派給節點的明確角色。</span><span class="sxs-lookup"><span data-stu-id="9cd45-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="9cd45-105">分欄</span><span class="sxs-lookup"><span data-stu-id="9cd45-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9cd45-106">左欄</span><span class="sxs-lookup"><span data-stu-id="9cd45-106">Column</span></span></th>
<th><span data-ttu-id="9cd45-107">類型</span><span class="sxs-lookup"><span data-stu-id="9cd45-107">Type</span></span></th>
<th><span data-ttu-id="9cd45-108">描述</span><span class="sxs-lookup"><span data-stu-id="9cd45-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9cd45-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="9cd45-109">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="9cd45-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="9cd45-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9cd45-111">角色所套用的節點識別碼。</span><span class="sxs-lookup"><span data-stu-id="9cd45-111">Node ID that the role applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9cd45-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="9cd45-112">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="9cd45-113">int，not null</span><span class="sxs-lookup"><span data-stu-id="9cd45-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9cd45-114">Principal ID。</span><span class="sxs-lookup"><span data-stu-id="9cd45-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9cd45-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="9cd45-115">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="9cd45-116">int，not null</span><span class="sxs-lookup"><span data-stu-id="9cd45-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9cd45-117">角色類型識別碼（從 tblRoleType）。</span><span class="sxs-lookup"><span data-stu-id="9cd45-117">Role type ID (from tblRoleType).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9cd45-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="9cd45-118">prinRoleUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="9cd45-119">int，not null</span><span class="sxs-lookup"><span data-stu-id="9cd45-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9cd45-120">上次更新此專案的主體 ID。</span><span class="sxs-lookup"><span data-stu-id="9cd45-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="9cd45-121">鍵</span><span class="sxs-lookup"><span data-stu-id="9cd45-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9cd45-122">左欄</span><span class="sxs-lookup"><span data-stu-id="9cd45-122">Column</span></span></th>
<th><span data-ttu-id="9cd45-123">描述</span><span class="sxs-lookup"><span data-stu-id="9cd45-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9cd45-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span><span class="sxs-lookup"><span data-stu-id="9cd45-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="9cd45-125">主鍵。</span><span class="sxs-lookup"><span data-stu-id="9cd45-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9cd45-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="9cd45-126">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="9cd45-127">在 tblNode 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="9cd45-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9cd45-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="9cd45-128">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="9cd45-129">在 tblPrincipal prinID 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="9cd45-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9cd45-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="9cd45-130">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="9cd45-131">在 tblRoleType rtypeID 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="9cd45-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

