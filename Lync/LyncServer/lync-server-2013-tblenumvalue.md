---
title: Lync Server 2013： tblEnumValue
description: Lync Server 2013： tblEnumValue。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblEnumValue
ms:assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615025(v=OCS.15)
ms:contentKeyID: 48185040
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 159f90bb96c367fcb3e11725a582a9993080d3fd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571369"
---
# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="11977-103">Lync Server 2013 中的 tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="11977-103">tblEnumValue in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11977-104">_**主題上次修改日期：** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="11977-104">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="11977-105">tblEnumValue 是包含在節點表格中所使用之屬性的 Visibility 和行為值的硬編碼表格。</span><span class="sxs-lookup"><span data-stu-id="11977-105">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="11977-106">Columns</span><span class="sxs-lookup"><span data-stu-id="11977-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11977-107">欄</span><span class="sxs-lookup"><span data-stu-id="11977-107">Column</span></span></th>
<th><span data-ttu-id="11977-108">類型</span><span class="sxs-lookup"><span data-stu-id="11977-108">Type</span></span></th>
<th><span data-ttu-id="11977-109">描述</span><span class="sxs-lookup"><span data-stu-id="11977-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11977-110">valueID</span><span class="sxs-lookup"><span data-stu-id="11977-110">valueID</span></span></p></td>
<td><p><span data-ttu-id="11977-111">smallint，非 null</span><span class="sxs-lookup"><span data-stu-id="11977-111">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="11977-112">值的識別碼。</span><span class="sxs-lookup"><span data-stu-id="11977-112">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11977-113">attributeID:</span><span class="sxs-lookup"><span data-stu-id="11977-113">attributeID</span></span></p></td>
<td><p><span data-ttu-id="11977-114">smallint，非 null</span><span class="sxs-lookup"><span data-stu-id="11977-114">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="11977-115">屬性的識別碼。</span><span class="sxs-lookup"><span data-stu-id="11977-115">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11977-116">attributeValue</span><span class="sxs-lookup"><span data-stu-id="11977-116">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="11977-117">nvarchar (256)，非 null</span><span class="sxs-lookup"><span data-stu-id="11977-117">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="11977-118">值的名稱。</span><span class="sxs-lookup"><span data-stu-id="11977-118">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="11977-119">索引鍵</span><span class="sxs-lookup"><span data-stu-id="11977-119">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11977-120">欄</span><span class="sxs-lookup"><span data-stu-id="11977-120">Column</span></span></th>
<th><span data-ttu-id="11977-121">描述</span><span class="sxs-lookup"><span data-stu-id="11977-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11977-122">valueID</span><span class="sxs-lookup"><span data-stu-id="11977-122">valueID</span></span></p></td>
<td><p><span data-ttu-id="11977-123">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="11977-123">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11977-124">attributeID:</span><span class="sxs-lookup"><span data-stu-id="11977-124">attributeID</span></span></p></td>
<td><p><span data-ttu-id="11977-125">在 tblEnumAttribute.attributeID 表格中查閱的外鍵。</span><span class="sxs-lookup"><span data-stu-id="11977-125">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="11977-126">表格值</span><span class="sxs-lookup"><span data-stu-id="11977-126">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11977-127">valueID</span><span class="sxs-lookup"><span data-stu-id="11977-127">valueID</span></span></th>
<th><span data-ttu-id="11977-128">attributeID:</span><span class="sxs-lookup"><span data-stu-id="11977-128">attributeID</span></span></th>
<th><span data-ttu-id="11977-129">attributeValue</span><span class="sxs-lookup"><span data-stu-id="11977-129">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11977-130">第</span><span class="sxs-lookup"><span data-stu-id="11977-130">2</span></span></p></td>
<td><p><span data-ttu-id="11977-131">1 </span><span class="sxs-lookup"><span data-stu-id="11977-131">1</span></span></p></td>
<td><p><span data-ttu-id="11977-132">私人</span><span class="sxs-lookup"><span data-stu-id="11977-132">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11977-133">個</span><span class="sxs-lookup"><span data-stu-id="11977-133">3</span></span></p></td>
<td><p><span data-ttu-id="11977-134">1 </span><span class="sxs-lookup"><span data-stu-id="11977-134">1</span></span></p></td>
<td><p><span data-ttu-id="11977-135">範圍</span><span class="sxs-lookup"><span data-stu-id="11977-135">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11977-136">4 </span><span class="sxs-lookup"><span data-stu-id="11977-136">4</span></span></p></td>
<td><p><span data-ttu-id="11977-137">第</span><span class="sxs-lookup"><span data-stu-id="11977-137">2</span></span></p></td>
<td><p><span data-ttu-id="11977-138">正常</span><span class="sxs-lookup"><span data-stu-id="11977-138">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11977-139">5 </span><span class="sxs-lookup"><span data-stu-id="11977-139">5</span></span></p></td>
<td><p><span data-ttu-id="11977-140">第</span><span class="sxs-lookup"><span data-stu-id="11977-140">2</span></span></p></td>
<td><p><span data-ttu-id="11977-141">禮堂</span><span class="sxs-lookup"><span data-stu-id="11977-141">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11977-142">6 </span><span class="sxs-lookup"><span data-stu-id="11977-142">6</span></span></p></td>
<td><p><span data-ttu-id="11977-143">1 </span><span class="sxs-lookup"><span data-stu-id="11977-143">1</span></span></p></td>
<td><p><span data-ttu-id="11977-144">打開</span><span class="sxs-lookup"><span data-stu-id="11977-144">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="11977-145">另請參閱</span><span class="sxs-lookup"><span data-stu-id="11977-145">See Also</span></span>


[<span data-ttu-id="11977-146">Lync Server 2013 中的 tblNode</span><span class="sxs-lookup"><span data-stu-id="11977-146">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

