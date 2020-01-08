---
title: Lync Server 2013：tblPrincipalAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalAffiliations
ms:assetid: 45fd8484-5837-44d2-85bb-45c83546607c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558642(v=OCS.15)
ms:contentKeyID: 48183993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb5f6400de1c71b4d11101871b2dadedd232a9ce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalaffiliations-in-lync-server-2013"></a><span data-ttu-id="b57de-102">Lync Server 2013 中的 tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="b57de-102">tblPrincipalAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b57de-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="b57de-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="b57de-104">tblPrincipalAffiliations 包含描述位置中的成員資格的主要隸屬關係，包括 Active directory 網域服務安全性群組（在 Active Directory 容器中，在網域中）。</span><span class="sxs-lookup"><span data-stu-id="b57de-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>

### <a name="columns"></a><span data-ttu-id="b57de-105">分欄</span><span class="sxs-lookup"><span data-stu-id="b57de-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b57de-106">左欄</span><span class="sxs-lookup"><span data-stu-id="b57de-106">Column</span></span></th>
<th><span data-ttu-id="b57de-107">類型</span><span class="sxs-lookup"><span data-stu-id="b57de-107">Type</span></span></th>
<th><span data-ttu-id="b57de-108">描述</span><span class="sxs-lookup"><span data-stu-id="b57de-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b57de-109">principalID</span><span class="sxs-lookup"><span data-stu-id="b57de-109">principalID</span></span></p></td>
<td><p><span data-ttu-id="b57de-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="b57de-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b57de-111">附屬原則的 ID。</span><span class="sxs-lookup"><span data-stu-id="b57de-111">ID of the affiliated principal.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b57de-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="b57de-112">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="b57de-113">int，not null</span><span class="sxs-lookup"><span data-stu-id="b57de-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b57de-114">代表隸屬關係的承擔者 ID。</span><span class="sxs-lookup"><span data-stu-id="b57de-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="b57de-115">每個主體（除系統使用者類型之外）都有自我隸屬關係。</span><span class="sxs-lookup"><span data-stu-id="b57de-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b57de-116">index</span><span class="sxs-lookup"><span data-stu-id="b57de-116">index</span></span></p></td>
<td><p><span data-ttu-id="b57de-117">int，not null</span><span class="sxs-lookup"><span data-stu-id="b57de-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b57de-118">Index.</span><span class="sxs-lookup"><span data-stu-id="b57de-118">Index.</span></span> <span data-ttu-id="b57de-119">自我隸屬關係的值是-1，而其他隸屬關係則會依序從每個&lt;PrincipalID、affiliationId&gt; bucket 中的1增加。</span><span class="sxs-lookup"><span data-stu-id="b57de-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each &lt;principalID, affiliationId&gt; bucket.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b57de-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="b57de-120">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="b57de-121">int，not null</span><span class="sxs-lookup"><span data-stu-id="b57de-121">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b57de-122">已進行最新更新的主體。</span><span class="sxs-lookup"><span data-stu-id="b57de-122">Principal that did the latest update.</span></span> <span data-ttu-id="b57de-123">這通常是1，這表示 Active Directory 同步處理。</span><span class="sxs-lookup"><span data-stu-id="b57de-123">This is usually 1, which means Active Directory Sync.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="b57de-124">鍵</span><span class="sxs-lookup"><span data-stu-id="b57de-124">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b57de-125">分欄</span><span class="sxs-lookup"><span data-stu-id="b57de-125">Columns</span></span></th>
<th><span data-ttu-id="b57de-126">描述</span><span class="sxs-lookup"><span data-stu-id="b57de-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b57de-127">&lt;principalID、index、affiliationID&gt;</span><span class="sxs-lookup"><span data-stu-id="b57de-127">&lt;principalID, index, affiliationID&gt;</span></span></p></td>
<td><p><span data-ttu-id="b57de-128">主鍵。</span><span class="sxs-lookup"><span data-stu-id="b57de-128">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b57de-129">principalID</span><span class="sxs-lookup"><span data-stu-id="b57de-129">principalID</span></span></p></td>
<td><p><span data-ttu-id="b57de-130">在 tblPrincipal prinID 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="b57de-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b57de-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="b57de-131">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="b57de-132">在 tblPrincipal prinID 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="b57de-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

