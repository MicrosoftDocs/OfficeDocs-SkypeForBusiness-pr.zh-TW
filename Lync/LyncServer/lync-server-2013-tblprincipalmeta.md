---
title: Lync Server 2013： tblPrincipalMeta
description: Lync Server 2013： tblPrincipalMeta。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMeta
ms:assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615009(v=OCS.15)
ms:contentKeyID: 48184648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 899fd1e450dac52afa56c1ee1de86da82b2db309
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573639"
---
# <a name="tblprincipalmeta-in-lync-server-2013"></a><span data-ttu-id="750d9-103">Lync Server 2013 中的 tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="750d9-103">tblPrincipalMeta in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="750d9-104">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="750d9-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="750d9-105">tblPrincipalMeta 包含必須從 Active Directory 網域服務重新整理的主體。</span><span class="sxs-lookup"><span data-stu-id="750d9-105">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>

### <a name="columns"></a><span data-ttu-id="750d9-106">Columns</span><span class="sxs-lookup"><span data-stu-id="750d9-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="750d9-107">欄</span><span class="sxs-lookup"><span data-stu-id="750d9-107">Column</span></span></th>
<th><span data-ttu-id="750d9-108">類型</span><span class="sxs-lookup"><span data-stu-id="750d9-108">Type</span></span></th>
<th><span data-ttu-id="750d9-109">描述</span><span class="sxs-lookup"><span data-stu-id="750d9-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="750d9-110">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="750d9-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="750d9-111">int，非 null</span><span class="sxs-lookup"><span data-stu-id="750d9-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="750d9-112">主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="750d9-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="750d9-113">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="750d9-113">prinAffiliationsDirty</span></span></p></td>
<td><p><span data-ttu-id="750d9-114">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="750d9-114">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="750d9-115">若主體關係必須重新整理，則為 True。</span><span class="sxs-lookup"><span data-stu-id="750d9-115">True if principal affiliations have to be refreshed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="750d9-116">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="750d9-116">prinAttributesDirty</span></span></p></td>
<td><p><span data-ttu-id="750d9-117">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="750d9-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="750d9-118">若主體屬性必須重新整理，則為 True。</span><span class="sxs-lookup"><span data-stu-id="750d9-118">True if principal attributes have to be refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="750d9-119">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="750d9-119">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="750d9-120">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="750d9-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="750d9-121">若主體已刪除，則為 True。</span><span class="sxs-lookup"><span data-stu-id="750d9-121">True if the principal has been deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="750d9-122">tryCount</span><span class="sxs-lookup"><span data-stu-id="750d9-122">tryCount</span></span></p></td>
<td><p><span data-ttu-id="750d9-123">int</span><span class="sxs-lookup"><span data-stu-id="750d9-123">int</span></span></p></td>
<td><p><span data-ttu-id="750d9-124">至今嘗試從 AD DS 重新整理主體的次數。</span><span class="sxs-lookup"><span data-stu-id="750d9-124">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="750d9-125">lastTry</span><span class="sxs-lookup"><span data-stu-id="750d9-125">lastTry</span></span></p></td>
<td><p><span data-ttu-id="750d9-126">datetime</span><span class="sxs-lookup"><span data-stu-id="750d9-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="750d9-p101">最近一次嘗試重新整理主體的時間戳記。若尚未重新整理過，可以是 null。</span><span class="sxs-lookup"><span data-stu-id="750d9-p101">Time stamp from the latest attempt to refresh the principal. Can be null if no refresh has been attempted yet.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="750d9-129">nextTry</span><span class="sxs-lookup"><span data-stu-id="750d9-129">nextTry</span></span></p></td>
<td><p><span data-ttu-id="750d9-130">datetime</span><span class="sxs-lookup"><span data-stu-id="750d9-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="750d9-p102">排定下次重新整理時間戳記。若未排定之後的重新整理，可以是 null。</span><span class="sxs-lookup"><span data-stu-id="750d9-p102">Time stamp for the next scheduled refresh. Can be null if no further refresh has been scheduled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="750d9-133">索引鍵</span><span class="sxs-lookup"><span data-stu-id="750d9-133">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="750d9-134">欄</span><span class="sxs-lookup"><span data-stu-id="750d9-134">Column</span></span></th>
<th><span data-ttu-id="750d9-135">描述</span><span class="sxs-lookup"><span data-stu-id="750d9-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="750d9-136">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="750d9-136">prinID</span></span></p></td>
<td><p><span data-ttu-id="750d9-137">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="750d9-137">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="750d9-138">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="750d9-138">prinID</span></span></p></td>
<td><p><span data-ttu-id="750d9-139">在 tblPrincipal.prinID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="750d9-139">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

