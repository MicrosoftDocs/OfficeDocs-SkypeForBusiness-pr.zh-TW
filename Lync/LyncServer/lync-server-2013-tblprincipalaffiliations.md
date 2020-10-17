---
title: Lync Server 2013： tblPrincipalAffiliations
description: Lync Server 2013： tblPrincipalAffiliations。
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
ms.openlocfilehash: 01c373147a58300e64f22e60e989a777c59b2653
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547479"
---
# <a name="tblprincipalaffiliations-in-lync-server-2013"></a><span data-ttu-id="6dc86-103">Lync Server 2013 中的 tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="6dc86-103">tblPrincipalAffiliations in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6dc86-104">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="6dc86-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="6dc86-105">tblPrincipalAffiliations 包含主體隸屬關係，描述位置中的成員資格，包括 Active directory 網域服務安全性群組、Active Directory 容器中的網域。</span><span class="sxs-lookup"><span data-stu-id="6dc86-105">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>

### <a name="columns"></a><span data-ttu-id="6dc86-106">Columns</span><span class="sxs-lookup"><span data-stu-id="6dc86-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6dc86-107">欄</span><span class="sxs-lookup"><span data-stu-id="6dc86-107">Column</span></span></th>
<th><span data-ttu-id="6dc86-108">類型</span><span class="sxs-lookup"><span data-stu-id="6dc86-108">Type</span></span></th>
<th><span data-ttu-id="6dc86-109">描述</span><span class="sxs-lookup"><span data-stu-id="6dc86-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6dc86-110">principalID</span><span class="sxs-lookup"><span data-stu-id="6dc86-110">principalID</span></span></p></td>
<td><p><span data-ttu-id="6dc86-111">int，非 null</span><span class="sxs-lookup"><span data-stu-id="6dc86-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="6dc86-112">附屬主體的識別碼。</span><span class="sxs-lookup"><span data-stu-id="6dc86-112">ID of the affiliated principal.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6dc86-113">affiliationID</span><span class="sxs-lookup"><span data-stu-id="6dc86-113">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="6dc86-114">int，非 null</span><span class="sxs-lookup"><span data-stu-id="6dc86-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="6dc86-115">代表隸屬關係之主體的識別碼。</span><span class="sxs-lookup"><span data-stu-id="6dc86-115">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="6dc86-116">除了系統使用者類型) 之外，每個主體 (都具有自我從屬。</span><span class="sxs-lookup"><span data-stu-id="6dc86-116">Each principal (except system-user-types) has a self-affiliation as well.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6dc86-117">index</span><span class="sxs-lookup"><span data-stu-id="6dc86-117">index</span></span></p></td>
<td><p><span data-ttu-id="6dc86-118">int，非 null</span><span class="sxs-lookup"><span data-stu-id="6dc86-118">int, not null</span></span></p></td>
<td><p><span data-ttu-id="6dc86-119">指數。</span><span class="sxs-lookup"><span data-stu-id="6dc86-119">Index.</span></span> <span data-ttu-id="6dc86-120">「自我隸屬關係」的值是-1，另一個隸屬關係會依序從每個 &lt; principalID、affiliationId bucket 中的1增加 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="6dc86-120">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each &lt;principalID, affiliationId&gt; bucket.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6dc86-121">updatedBy</span><span class="sxs-lookup"><span data-stu-id="6dc86-121">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="6dc86-122">int，非 null</span><span class="sxs-lookup"><span data-stu-id="6dc86-122">int, not null</span></span></p></td>
<td><p><span data-ttu-id="6dc86-123">進行最新更新的主體。</span><span class="sxs-lookup"><span data-stu-id="6dc86-123">Principal that did the latest update.</span></span> <span data-ttu-id="6dc86-124">這通常是1，表示 Active Directory 同步處理。</span><span class="sxs-lookup"><span data-stu-id="6dc86-124">This is usually 1, which means Active Directory Sync.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="6dc86-125">索引鍵</span><span class="sxs-lookup"><span data-stu-id="6dc86-125">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6dc86-126">Columns</span><span class="sxs-lookup"><span data-stu-id="6dc86-126">Columns</span></span></th>
<th><span data-ttu-id="6dc86-127">描述</span><span class="sxs-lookup"><span data-stu-id="6dc86-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6dc86-128">&lt;principalID、index、affiliationID&gt;</span><span class="sxs-lookup"><span data-stu-id="6dc86-128">&lt;principalID, index, affiliationID&gt;</span></span></p></td>
<td><p><span data-ttu-id="6dc86-129">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="6dc86-129">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6dc86-130">principalID</span><span class="sxs-lookup"><span data-stu-id="6dc86-130">principalID</span></span></p></td>
<td><p><span data-ttu-id="6dc86-131">在 tblPrincipal.prinID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="6dc86-131">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6dc86-132">affiliationID</span><span class="sxs-lookup"><span data-stu-id="6dc86-132">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="6dc86-133">在 tblPrincipal.prinID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="6dc86-133">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

