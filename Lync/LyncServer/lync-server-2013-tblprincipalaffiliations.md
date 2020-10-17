---
title: Lync Server 2013： tblPrincipalAffiliations
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
ms.openlocfilehash: ec2ef70b70ff496852a753a9e15a38f80de1509b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523740"
---
# <a name="tblprincipalaffiliations-in-lync-server-2013"></a><span data-ttu-id="e77c5-102">Lync Server 2013 中的 tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="e77c5-102">tblPrincipalAffiliations in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e77c5-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="e77c5-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="e77c5-104">tblPrincipalAffiliations 包含主體隸屬關係，描述位置中的成員資格，包括 Active directory 網域服務安全性群組、Active Directory 容器中的網域。</span><span class="sxs-lookup"><span data-stu-id="e77c5-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>

### <a name="columns"></a><span data-ttu-id="e77c5-105">Columns</span><span class="sxs-lookup"><span data-stu-id="e77c5-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e77c5-106">欄</span><span class="sxs-lookup"><span data-stu-id="e77c5-106">Column</span></span></th>
<th><span data-ttu-id="e77c5-107">類型</span><span class="sxs-lookup"><span data-stu-id="e77c5-107">Type</span></span></th>
<th><span data-ttu-id="e77c5-108">描述</span><span class="sxs-lookup"><span data-stu-id="e77c5-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e77c5-109">principalID</span><span class="sxs-lookup"><span data-stu-id="e77c5-109">principalID</span></span></p></td>
<td><p><span data-ttu-id="e77c5-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="e77c5-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e77c5-111">附屬主體的識別碼。</span><span class="sxs-lookup"><span data-stu-id="e77c5-111">ID of the affiliated principal.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e77c5-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="e77c5-112">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="e77c5-113">int，非 null</span><span class="sxs-lookup"><span data-stu-id="e77c5-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e77c5-114">代表隸屬關係之主體的識別碼。</span><span class="sxs-lookup"><span data-stu-id="e77c5-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="e77c5-115">除了系統使用者類型) 之外，每個主體 (都具有自我從屬。</span><span class="sxs-lookup"><span data-stu-id="e77c5-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e77c5-116">index</span><span class="sxs-lookup"><span data-stu-id="e77c5-116">index</span></span></p></td>
<td><p><span data-ttu-id="e77c5-117">int，非 null</span><span class="sxs-lookup"><span data-stu-id="e77c5-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e77c5-118">指數。</span><span class="sxs-lookup"><span data-stu-id="e77c5-118">Index.</span></span> <span data-ttu-id="e77c5-119">「自我隸屬關係」的值是-1，另一個隸屬關係會依序從每個 &lt; principalID、affiliationId bucket 中的1增加 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="e77c5-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each &lt;principalID, affiliationId&gt; bucket.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e77c5-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="e77c5-120">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="e77c5-121">int，非 null</span><span class="sxs-lookup"><span data-stu-id="e77c5-121">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e77c5-122">進行最新更新的主體。</span><span class="sxs-lookup"><span data-stu-id="e77c5-122">Principal that did the latest update.</span></span> <span data-ttu-id="e77c5-123">這通常是1，表示 Active Directory 同步處理。</span><span class="sxs-lookup"><span data-stu-id="e77c5-123">This is usually 1, which means Active Directory Sync.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="e77c5-124">索引鍵</span><span class="sxs-lookup"><span data-stu-id="e77c5-124">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e77c5-125">Columns</span><span class="sxs-lookup"><span data-stu-id="e77c5-125">Columns</span></span></th>
<th><span data-ttu-id="e77c5-126">描述</span><span class="sxs-lookup"><span data-stu-id="e77c5-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e77c5-127">&lt;principalID、index、affiliationID&gt;</span><span class="sxs-lookup"><span data-stu-id="e77c5-127">&lt;principalID, index, affiliationID&gt;</span></span></p></td>
<td><p><span data-ttu-id="e77c5-128">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="e77c5-128">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e77c5-129">principalID</span><span class="sxs-lookup"><span data-stu-id="e77c5-129">principalID</span></span></p></td>
<td><p><span data-ttu-id="e77c5-130">在 tblPrincipal.prinID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="e77c5-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e77c5-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="e77c5-131">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="e77c5-132">在 tblPrincipal.prinID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="e77c5-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

