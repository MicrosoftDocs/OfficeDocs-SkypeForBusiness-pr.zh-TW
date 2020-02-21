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
ms.openlocfilehash: 0a57e4a3c7a5fdcc1825c140cb6e26f8cede8dc1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214439"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalaffiliations-in-lync-server-2013"></a><span data-ttu-id="2ca96-102">Lync Server 2013 中的 Principalaffiliations</span><span class="sxs-lookup"><span data-stu-id="2ca96-102">tblPrincipalAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ca96-103">_**主題上次修改日期：** 2012年-09-12_</span><span class="sxs-lookup"><span data-stu-id="2ca96-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="2ca96-104">Principalaffiliations 包含主體關係，可描述位置，包括 Active Directory 網域服務的安全性群組，在 Active Directory 容器，在網域中的成員資格。</span><span class="sxs-lookup"><span data-stu-id="2ca96-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>

### <a name="columns"></a><span data-ttu-id="2ca96-105">Columns</span><span class="sxs-lookup"><span data-stu-id="2ca96-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ca96-106">欄</span><span class="sxs-lookup"><span data-stu-id="2ca96-106">Column</span></span></th>
<th><span data-ttu-id="2ca96-107">類型	</span><span class="sxs-lookup"><span data-stu-id="2ca96-107">Type</span></span></th>
<th><span data-ttu-id="2ca96-108">描述</span><span class="sxs-lookup"><span data-stu-id="2ca96-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ca96-109">principalID</span><span class="sxs-lookup"><span data-stu-id="2ca96-109">principalID</span></span></p></td>
<td><p><span data-ttu-id="2ca96-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="2ca96-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="2ca96-111">相關主體的識別碼。</span><span class="sxs-lookup"><span data-stu-id="2ca96-111">ID of the affiliated principal.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ca96-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="2ca96-112">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="2ca96-113">int，非 null</span><span class="sxs-lookup"><span data-stu-id="2ca96-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="2ca96-114">代表關係的主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="2ca96-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="2ca96-115">每個主體 （除了系統使用者類型） 都有也自我 affiliation。</span><span class="sxs-lookup"><span data-stu-id="2ca96-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ca96-116">index</span><span class="sxs-lookup"><span data-stu-id="2ca96-116">index</span></span></p></td>
<td><p><span data-ttu-id="2ca96-117">int，非 null</span><span class="sxs-lookup"><span data-stu-id="2ca96-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="2ca96-118">索引。</span><span class="sxs-lookup"><span data-stu-id="2ca96-118">Index.</span></span> <span data-ttu-id="2ca96-119">自我關係的值為-1，而且其他關係的也會增加循序 1 中每個&lt;principalID，affiliationId&gt; bucket。</span><span class="sxs-lookup"><span data-stu-id="2ca96-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each &lt;principalID, affiliationId&gt; bucket.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ca96-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="2ca96-120">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="2ca96-121">int，非 null</span><span class="sxs-lookup"><span data-stu-id="2ca96-121">int, not null</span></span></p></td>
<td><p><span data-ttu-id="2ca96-122">最近一次更新的主體。</span><span class="sxs-lookup"><span data-stu-id="2ca96-122">Principal that did the latest update.</span></span> <span data-ttu-id="2ca96-123">這通常是 1，這表示 Active Directory 同步處理。</span><span class="sxs-lookup"><span data-stu-id="2ca96-123">This is usually 1, which means Active Directory Sync.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="2ca96-124">索引鍵</span><span class="sxs-lookup"><span data-stu-id="2ca96-124">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ca96-125">Columns</span><span class="sxs-lookup"><span data-stu-id="2ca96-125">Columns</span></span></th>
<th><span data-ttu-id="2ca96-126">說明</span><span class="sxs-lookup"><span data-stu-id="2ca96-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ca96-127">&lt;principalID、 索引、 affiliationID&gt;</span><span class="sxs-lookup"><span data-stu-id="2ca96-127">&lt;principalID, index, affiliationID&gt;</span></span></p></td>
<td><p><span data-ttu-id="2ca96-128">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="2ca96-128">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ca96-129">principalID</span><span class="sxs-lookup"><span data-stu-id="2ca96-129">principalID</span></span></p></td>
<td><p><span data-ttu-id="2ca96-130">在 tblPrincipal.prinID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="2ca96-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ca96-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="2ca96-131">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="2ca96-132">在 tblPrincipal.prinID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="2ca96-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

