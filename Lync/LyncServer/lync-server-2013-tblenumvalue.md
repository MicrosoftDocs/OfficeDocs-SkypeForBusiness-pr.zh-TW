---
title: 'Lync Server 2013: tblEnumValue'
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
ms.openlocfilehash: d182a3689ae38d4117b45d6590bb2ccd08c0a8b7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="aec6d-102">Lync Server 2013 中的 tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="aec6d-102">tblEnumValue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aec6d-103">_**主題上次修改日期：** 2012年-06-28_</span><span class="sxs-lookup"><span data-stu-id="aec6d-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="aec6d-104">tblEnumValue 是一種硬式編碼表格，包含節點表格中所用的屬性的可見度和行為值。</span><span class="sxs-lookup"><span data-stu-id="aec6d-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="aec6d-105">Columns</span><span class="sxs-lookup"><span data-stu-id="aec6d-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aec6d-106">欄</span><span class="sxs-lookup"><span data-stu-id="aec6d-106">Column</span></span></th>
<th><span data-ttu-id="aec6d-107">類型	</span><span class="sxs-lookup"><span data-stu-id="aec6d-107">Type</span></span></th>
<th><span data-ttu-id="aec6d-108">描述</span><span class="sxs-lookup"><span data-stu-id="aec6d-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aec6d-109">valueID</span><span class="sxs-lookup"><span data-stu-id="aec6d-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="aec6d-110">smallint，非 null</span><span class="sxs-lookup"><span data-stu-id="aec6d-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="aec6d-111">值的 ID。</span><span class="sxs-lookup"><span data-stu-id="aec6d-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aec6d-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="aec6d-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="aec6d-113">smallint，非 null</span><span class="sxs-lookup"><span data-stu-id="aec6d-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="aec6d-114">屬性的識別碼。</span><span class="sxs-lookup"><span data-stu-id="aec6d-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aec6d-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="aec6d-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="aec6d-116">nvarchar (256)，非 null</span><span class="sxs-lookup"><span data-stu-id="aec6d-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="aec6d-117">值的名稱。</span><span class="sxs-lookup"><span data-stu-id="aec6d-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="aec6d-118">索引鍵</span><span class="sxs-lookup"><span data-stu-id="aec6d-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aec6d-119">欄</span><span class="sxs-lookup"><span data-stu-id="aec6d-119">Column</span></span></th>
<th><span data-ttu-id="aec6d-120">描述</span><span class="sxs-lookup"><span data-stu-id="aec6d-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aec6d-121">valueID</span><span class="sxs-lookup"><span data-stu-id="aec6d-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="aec6d-122">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="aec6d-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aec6d-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="aec6d-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="aec6d-124">在 tblEnumAttribute.attributeID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="aec6d-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="aec6d-125">表格值</span><span class="sxs-lookup"><span data-stu-id="aec6d-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aec6d-126">valueID</span><span class="sxs-lookup"><span data-stu-id="aec6d-126">valueID</span></span></th>
<th><span data-ttu-id="aec6d-127">attributeID</span><span class="sxs-lookup"><span data-stu-id="aec6d-127">attributeID</span></span></th>
<th><span data-ttu-id="aec6d-128">attributeValue</span><span class="sxs-lookup"><span data-stu-id="aec6d-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aec6d-129">2 </span><span class="sxs-lookup"><span data-stu-id="aec6d-129">2</span></span></p></td>
<td><p><span data-ttu-id="aec6d-130">1 </span><span class="sxs-lookup"><span data-stu-id="aec6d-130">1</span></span></p></td>
<td><p><span data-ttu-id="aec6d-131">私用</span><span class="sxs-lookup"><span data-stu-id="aec6d-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aec6d-132">3 </span><span class="sxs-lookup"><span data-stu-id="aec6d-132">3</span></span></p></td>
<td><p><span data-ttu-id="aec6d-133">1 </span><span class="sxs-lookup"><span data-stu-id="aec6d-133">1</span></span></p></td>
<td><p><span data-ttu-id="aec6d-134">範圍</span><span class="sxs-lookup"><span data-stu-id="aec6d-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aec6d-135">4 </span><span class="sxs-lookup"><span data-stu-id="aec6d-135">4</span></span></p></td>
<td><p><span data-ttu-id="aec6d-136">2 </span><span class="sxs-lookup"><span data-stu-id="aec6d-136">2</span></span></p></td>
<td><p><span data-ttu-id="aec6d-137">一般</span><span class="sxs-lookup"><span data-stu-id="aec6d-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aec6d-138">5 </span><span class="sxs-lookup"><span data-stu-id="aec6d-138">5</span></span></p></td>
<td><p><span data-ttu-id="aec6d-139">2 </span><span class="sxs-lookup"><span data-stu-id="aec6d-139">2</span></span></p></td>
<td><p><span data-ttu-id="aec6d-140">視聽中心</span><span class="sxs-lookup"><span data-stu-id="aec6d-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aec6d-141">6 </span><span class="sxs-lookup"><span data-stu-id="aec6d-141">6</span></span></p></td>
<td><p><span data-ttu-id="aec6d-142">1 </span><span class="sxs-lookup"><span data-stu-id="aec6d-142">1</span></span></p></td>
<td><p><span data-ttu-id="aec6d-143">開啟</span><span class="sxs-lookup"><span data-stu-id="aec6d-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="aec6d-144">另請參閱</span><span class="sxs-lookup"><span data-stu-id="aec6d-144">See Also</span></span>


[<span data-ttu-id="aec6d-145">Lync Server 2013 中的 tblNode</span><span class="sxs-lookup"><span data-stu-id="aec6d-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

