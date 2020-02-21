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
ms.openlocfilehash: 4166e25375c7ddd631b1ee7944ac703f21c9ba80
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="47b75-102">Lync Server 2013 中的 tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="47b75-102">tblEnumValue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47b75-103">_**主題上次修改日期：** 2012年-06-28_</span><span class="sxs-lookup"><span data-stu-id="47b75-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="47b75-104">tblEnumValue 是一種硬式編碼表格，包含節點表格中所用的屬性的可見度和行為值。</span><span class="sxs-lookup"><span data-stu-id="47b75-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="47b75-105">Columns</span><span class="sxs-lookup"><span data-stu-id="47b75-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47b75-106">欄</span><span class="sxs-lookup"><span data-stu-id="47b75-106">Column</span></span></th>
<th><span data-ttu-id="47b75-107">類型	</span><span class="sxs-lookup"><span data-stu-id="47b75-107">Type</span></span></th>
<th><span data-ttu-id="47b75-108">描述</span><span class="sxs-lookup"><span data-stu-id="47b75-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47b75-109">valueID</span><span class="sxs-lookup"><span data-stu-id="47b75-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="47b75-110">smallint，非 null</span><span class="sxs-lookup"><span data-stu-id="47b75-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="47b75-111">值的 ID。</span><span class="sxs-lookup"><span data-stu-id="47b75-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47b75-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="47b75-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="47b75-113">smallint，非 null</span><span class="sxs-lookup"><span data-stu-id="47b75-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="47b75-114">屬性的識別碼。</span><span class="sxs-lookup"><span data-stu-id="47b75-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47b75-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="47b75-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="47b75-116">nvarchar (256)，非 null</span><span class="sxs-lookup"><span data-stu-id="47b75-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="47b75-117">值的名稱。</span><span class="sxs-lookup"><span data-stu-id="47b75-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="47b75-118">索引鍵</span><span class="sxs-lookup"><span data-stu-id="47b75-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47b75-119">欄</span><span class="sxs-lookup"><span data-stu-id="47b75-119">Column</span></span></th>
<th><span data-ttu-id="47b75-120">描述</span><span class="sxs-lookup"><span data-stu-id="47b75-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47b75-121">valueID</span><span class="sxs-lookup"><span data-stu-id="47b75-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="47b75-122">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="47b75-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47b75-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="47b75-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="47b75-124">在 tblEnumAttribute.attributeID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="47b75-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="47b75-125">表格值</span><span class="sxs-lookup"><span data-stu-id="47b75-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47b75-126">valueID</span><span class="sxs-lookup"><span data-stu-id="47b75-126">valueID</span></span></th>
<th><span data-ttu-id="47b75-127">attributeID</span><span class="sxs-lookup"><span data-stu-id="47b75-127">attributeID</span></span></th>
<th><span data-ttu-id="47b75-128">attributeValue</span><span class="sxs-lookup"><span data-stu-id="47b75-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47b75-129">2</span><span class="sxs-lookup"><span data-stu-id="47b75-129">2</span></span></p></td>
<td><p><span data-ttu-id="47b75-130">1</span><span class="sxs-lookup"><span data-stu-id="47b75-130">1</span></span></p></td>
<td><p><span data-ttu-id="47b75-131">私用</span><span class="sxs-lookup"><span data-stu-id="47b75-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47b75-132">3</span><span class="sxs-lookup"><span data-stu-id="47b75-132">3</span></span></p></td>
<td><p><span data-ttu-id="47b75-133">1</span><span class="sxs-lookup"><span data-stu-id="47b75-133">1</span></span></p></td>
<td><p><span data-ttu-id="47b75-134">範圍</span><span class="sxs-lookup"><span data-stu-id="47b75-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47b75-135">4</span><span class="sxs-lookup"><span data-stu-id="47b75-135">4</span></span></p></td>
<td><p><span data-ttu-id="47b75-136">2</span><span class="sxs-lookup"><span data-stu-id="47b75-136">2</span></span></p></td>
<td><p><span data-ttu-id="47b75-137">一般</span><span class="sxs-lookup"><span data-stu-id="47b75-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47b75-138">5</span><span class="sxs-lookup"><span data-stu-id="47b75-138">5</span></span></p></td>
<td><p><span data-ttu-id="47b75-139">2</span><span class="sxs-lookup"><span data-stu-id="47b75-139">2</span></span></p></td>
<td><p><span data-ttu-id="47b75-140">視聽中心</span><span class="sxs-lookup"><span data-stu-id="47b75-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47b75-141">6 </span><span class="sxs-lookup"><span data-stu-id="47b75-141">6</span></span></p></td>
<td><p><span data-ttu-id="47b75-142">1</span><span class="sxs-lookup"><span data-stu-id="47b75-142">1</span></span></p></td>
<td><p><span data-ttu-id="47b75-143">開啟</span><span class="sxs-lookup"><span data-stu-id="47b75-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="47b75-144">另請參閱</span><span class="sxs-lookup"><span data-stu-id="47b75-144">See Also</span></span>


[<span data-ttu-id="47b75-145">Lync Server 2013 中的 tblNode</span><span class="sxs-lookup"><span data-stu-id="47b75-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

