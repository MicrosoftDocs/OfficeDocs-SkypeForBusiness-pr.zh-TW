---
title: 'Lync Server 2013: Principalaffiliations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalAffiliations
ms:assetid: 45fd8484-5837-44d2-85bb-45c83546607c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558642(v=OCS.15)
ms:contentKeyID: 48183993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2900a2ca780cfc239cb7045ea564bbba581f2f55
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142029"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalaffiliations-in-lync-server-2013"></a><span data-ttu-id="173b9-102">Lync Server 2013 中的 Principalaffiliations</span><span class="sxs-lookup"><span data-stu-id="173b9-102">tblPrincipalAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="173b9-103">_**主題上次修改日期：** 2012年-09-12_</span><span class="sxs-lookup"><span data-stu-id="173b9-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="173b9-104">Principalaffiliations 包含主體關係，可描述位置，包括 Active Directory 網域服務的安全性群組，在 Active Directory 容器，在網域中的成員資格。</span><span class="sxs-lookup"><span data-stu-id="173b9-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>

### <a name="columns"></a><span data-ttu-id="173b9-105">Columns</span><span class="sxs-lookup"><span data-stu-id="173b9-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="173b9-106">欄</span><span class="sxs-lookup"><span data-stu-id="173b9-106">Column</span></span></th>
<th><span data-ttu-id="173b9-107">類型	</span><span class="sxs-lookup"><span data-stu-id="173b9-107">Type</span></span></th>
<th><span data-ttu-id="173b9-108">描述</span><span class="sxs-lookup"><span data-stu-id="173b9-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="173b9-109">principalID</span><span class="sxs-lookup"><span data-stu-id="173b9-109">principalID</span></span></p></td>
<td><p><span data-ttu-id="173b9-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="173b9-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="173b9-111">相關主體的識別碼。</span><span class="sxs-lookup"><span data-stu-id="173b9-111">ID of the affiliated principal.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="173b9-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="173b9-112">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="173b9-113">int，非 null</span><span class="sxs-lookup"><span data-stu-id="173b9-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="173b9-114">代表關係的主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="173b9-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="173b9-115">每個主體 （除了系統使用者類型） 都有也自我 affiliation。</span><span class="sxs-lookup"><span data-stu-id="173b9-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="173b9-116">index</span><span class="sxs-lookup"><span data-stu-id="173b9-116">index</span></span></p></td>
<td><p><span data-ttu-id="173b9-117">int，非 null</span><span class="sxs-lookup"><span data-stu-id="173b9-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="173b9-118">索引。</span><span class="sxs-lookup"><span data-stu-id="173b9-118">Index.</span></span> <span data-ttu-id="173b9-119">自我關係的值為-1，而且其他關係的也會增加循序 1 中每個&lt;principalID，affiliationId&gt; bucket。</span><span class="sxs-lookup"><span data-stu-id="173b9-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each &lt;principalID, affiliationId&gt; bucket.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="173b9-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="173b9-120">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="173b9-121">int，非 null</span><span class="sxs-lookup"><span data-stu-id="173b9-121">int, not null</span></span></p></td>
<td><p><span data-ttu-id="173b9-122">最近一次更新的主體。</span><span class="sxs-lookup"><span data-stu-id="173b9-122">Principal that did the latest update.</span></span> <span data-ttu-id="173b9-123">這通常是 1，這表示 Active Directory 同步處理。</span><span class="sxs-lookup"><span data-stu-id="173b9-123">This is usually 1, which means Active Directory Sync.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="173b9-124">索引鍵</span><span class="sxs-lookup"><span data-stu-id="173b9-124">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="173b9-125">Columns</span><span class="sxs-lookup"><span data-stu-id="173b9-125">Columns</span></span></th>
<th><span data-ttu-id="173b9-126">描述</span><span class="sxs-lookup"><span data-stu-id="173b9-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="173b9-127">&lt;principalID、 索引、 affiliationID&gt;</span><span class="sxs-lookup"><span data-stu-id="173b9-127">&lt;principalID, index, affiliationID&gt;</span></span></p></td>
<td><p><span data-ttu-id="173b9-128">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="173b9-128">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="173b9-129">principalID</span><span class="sxs-lookup"><span data-stu-id="173b9-129">principalID</span></span></p></td>
<td><p><span data-ttu-id="173b9-130">在 tblPrincipal.prinID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="173b9-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="173b9-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="173b9-131">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="173b9-132">在 tblPrincipal.prinID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="173b9-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

