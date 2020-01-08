---
title: Lync Server 2013：tblPrincipalMeta
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalMeta
ms:assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615009(v=OCS.15)
ms:contentKeyID: 48184648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b9b067b9d04ecb32a3e43dbbd1f8435c00fa0c0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmeta-in-lync-server-2013"></a><span data-ttu-id="d5fca-102">Lync Server 2013 中的 tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="d5fca-102">tblPrincipalMeta in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5fca-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="d5fca-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="d5fca-104">tblPrincipalMeta 包含必須從 Active Directory 網域服務更新的主體。</span><span class="sxs-lookup"><span data-stu-id="d5fca-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>

### <a name="columns"></a><span data-ttu-id="d5fca-105">分欄</span><span class="sxs-lookup"><span data-stu-id="d5fca-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d5fca-106">左欄</span><span class="sxs-lookup"><span data-stu-id="d5fca-106">Column</span></span></th>
<th><span data-ttu-id="d5fca-107">類型</span><span class="sxs-lookup"><span data-stu-id="d5fca-107">Type</span></span></th>
<th><span data-ttu-id="d5fca-108">描述</span><span class="sxs-lookup"><span data-stu-id="d5fca-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d5fca-109">prinID</span><span class="sxs-lookup"><span data-stu-id="d5fca-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="d5fca-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="d5fca-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d5fca-111">Principal ID。</span><span class="sxs-lookup"><span data-stu-id="d5fca-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5fca-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="d5fca-112">prinAffiliationsDirty</span></span></p></td>
<td><p><span data-ttu-id="d5fca-113">bit、not null</span><span class="sxs-lookup"><span data-stu-id="d5fca-113">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="d5fca-114">如果必須重新整理承擔者隸屬關係，則為 True。</span><span class="sxs-lookup"><span data-stu-id="d5fca-114">True if principal affiliations have to be refreshed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5fca-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="d5fca-115">prinAttributesDirty</span></span></p></td>
<td><p><span data-ttu-id="d5fca-116">bit、not null</span><span class="sxs-lookup"><span data-stu-id="d5fca-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="d5fca-117">如果必須重新整理主體屬性，則為 True。</span><span class="sxs-lookup"><span data-stu-id="d5fca-117">True if principal attributes have to be refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5fca-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="d5fca-118">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="d5fca-119">bit、not null</span><span class="sxs-lookup"><span data-stu-id="d5fca-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="d5fca-120">如果主體已遭刪除，則為 True。</span><span class="sxs-lookup"><span data-stu-id="d5fca-120">True if the principal has been deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5fca-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="d5fca-121">tryCount</span></span></p></td>
<td><p><span data-ttu-id="d5fca-122">int</span><span class="sxs-lookup"><span data-stu-id="d5fca-122">int</span></span></p></td>
<td><p><span data-ttu-id="d5fca-123">嘗試從目前已發生過的 AD DS 重新整理主體的次數。</span><span class="sxs-lookup"><span data-stu-id="d5fca-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5fca-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="d5fca-124">lastTry</span></span></p></td>
<td><p><span data-ttu-id="d5fca-125">datetime</span><span class="sxs-lookup"><span data-stu-id="d5fca-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="d5fca-126">從最新嘗試重新整理主體的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="d5fca-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="d5fca-127">如果尚未嘗試重新整理，則可以是 null。</span><span class="sxs-lookup"><span data-stu-id="d5fca-127">Can be null if no refresh has been attempted yet.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5fca-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="d5fca-128">nextTry</span></span></p></td>
<td><p><span data-ttu-id="d5fca-129">datetime</span><span class="sxs-lookup"><span data-stu-id="d5fca-129">datetime</span></span></p></td>
<td><p><span data-ttu-id="d5fca-130">下一次排程重新整理的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="d5fca-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="d5fca-131">如果沒有排程進一步的重新整理，就可以是 null。</span><span class="sxs-lookup"><span data-stu-id="d5fca-131">Can be null if no further refresh has been scheduled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="d5fca-132">鍵</span><span class="sxs-lookup"><span data-stu-id="d5fca-132">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d5fca-133">左欄</span><span class="sxs-lookup"><span data-stu-id="d5fca-133">Column</span></span></th>
<th><span data-ttu-id="d5fca-134">描述</span><span class="sxs-lookup"><span data-stu-id="d5fca-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d5fca-135">prinID</span><span class="sxs-lookup"><span data-stu-id="d5fca-135">prinID</span></span></p></td>
<td><p><span data-ttu-id="d5fca-136">主鍵。</span><span class="sxs-lookup"><span data-stu-id="d5fca-136">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5fca-137">prinID</span><span class="sxs-lookup"><span data-stu-id="d5fca-137">prinID</span></span></p></td>
<td><p><span data-ttu-id="d5fca-138">在 tblPrincipal prinID 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="d5fca-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

