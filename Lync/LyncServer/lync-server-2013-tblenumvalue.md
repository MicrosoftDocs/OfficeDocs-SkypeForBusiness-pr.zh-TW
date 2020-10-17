---
title: Lync Server 2013： tblEnumValue
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
ms.openlocfilehash: 79d1b68cd10858812a1310ebbd1f2caae913da75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509320"
---
# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="85b76-102">Lync Server 2013 中的 tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="85b76-102">tblEnumValue in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85b76-103">_**主題上次修改日期：** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="85b76-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="85b76-104">tblEnumValue 是包含在節點表格中所使用之屬性的 Visibility 和行為值的硬編碼表格。</span><span class="sxs-lookup"><span data-stu-id="85b76-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="85b76-105">Columns</span><span class="sxs-lookup"><span data-stu-id="85b76-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85b76-106">欄</span><span class="sxs-lookup"><span data-stu-id="85b76-106">Column</span></span></th>
<th><span data-ttu-id="85b76-107">類型</span><span class="sxs-lookup"><span data-stu-id="85b76-107">Type</span></span></th>
<th><span data-ttu-id="85b76-108">描述</span><span class="sxs-lookup"><span data-stu-id="85b76-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85b76-109">valueID</span><span class="sxs-lookup"><span data-stu-id="85b76-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="85b76-110">smallint，非 null</span><span class="sxs-lookup"><span data-stu-id="85b76-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="85b76-111">值的識別碼。</span><span class="sxs-lookup"><span data-stu-id="85b76-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85b76-112">attributeID:</span><span class="sxs-lookup"><span data-stu-id="85b76-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="85b76-113">smallint，非 null</span><span class="sxs-lookup"><span data-stu-id="85b76-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="85b76-114">屬性的識別碼。</span><span class="sxs-lookup"><span data-stu-id="85b76-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85b76-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="85b76-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="85b76-116">nvarchar (256)，非 null</span><span class="sxs-lookup"><span data-stu-id="85b76-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="85b76-117">值的名稱。</span><span class="sxs-lookup"><span data-stu-id="85b76-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="85b76-118">索引鍵</span><span class="sxs-lookup"><span data-stu-id="85b76-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85b76-119">欄</span><span class="sxs-lookup"><span data-stu-id="85b76-119">Column</span></span></th>
<th><span data-ttu-id="85b76-120">描述</span><span class="sxs-lookup"><span data-stu-id="85b76-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85b76-121">valueID</span><span class="sxs-lookup"><span data-stu-id="85b76-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="85b76-122">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="85b76-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85b76-123">attributeID:</span><span class="sxs-lookup"><span data-stu-id="85b76-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="85b76-124">在 tblEnumAttribute.attributeID 表格中查閱的外鍵。</span><span class="sxs-lookup"><span data-stu-id="85b76-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="85b76-125">表格值</span><span class="sxs-lookup"><span data-stu-id="85b76-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85b76-126">valueID</span><span class="sxs-lookup"><span data-stu-id="85b76-126">valueID</span></span></th>
<th><span data-ttu-id="85b76-127">attributeID:</span><span class="sxs-lookup"><span data-stu-id="85b76-127">attributeID</span></span></th>
<th><span data-ttu-id="85b76-128">attributeValue</span><span class="sxs-lookup"><span data-stu-id="85b76-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85b76-129">第</span><span class="sxs-lookup"><span data-stu-id="85b76-129">2</span></span></p></td>
<td><p><span data-ttu-id="85b76-130">1 </span><span class="sxs-lookup"><span data-stu-id="85b76-130">1</span></span></p></td>
<td><p><span data-ttu-id="85b76-131">私人</span><span class="sxs-lookup"><span data-stu-id="85b76-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85b76-132">個</span><span class="sxs-lookup"><span data-stu-id="85b76-132">3</span></span></p></td>
<td><p><span data-ttu-id="85b76-133">1 </span><span class="sxs-lookup"><span data-stu-id="85b76-133">1</span></span></p></td>
<td><p><span data-ttu-id="85b76-134">範圍</span><span class="sxs-lookup"><span data-stu-id="85b76-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85b76-135">4 </span><span class="sxs-lookup"><span data-stu-id="85b76-135">4</span></span></p></td>
<td><p><span data-ttu-id="85b76-136">第</span><span class="sxs-lookup"><span data-stu-id="85b76-136">2</span></span></p></td>
<td><p><span data-ttu-id="85b76-137">正常</span><span class="sxs-lookup"><span data-stu-id="85b76-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85b76-138">5 </span><span class="sxs-lookup"><span data-stu-id="85b76-138">5</span></span></p></td>
<td><p><span data-ttu-id="85b76-139">第</span><span class="sxs-lookup"><span data-stu-id="85b76-139">2</span></span></p></td>
<td><p><span data-ttu-id="85b76-140">禮堂</span><span class="sxs-lookup"><span data-stu-id="85b76-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85b76-141">6 </span><span class="sxs-lookup"><span data-stu-id="85b76-141">6</span></span></p></td>
<td><p><span data-ttu-id="85b76-142">1 </span><span class="sxs-lookup"><span data-stu-id="85b76-142">1</span></span></p></td>
<td><p><span data-ttu-id="85b76-143">打開</span><span class="sxs-lookup"><span data-stu-id="85b76-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="85b76-144">另請參閱</span><span class="sxs-lookup"><span data-stu-id="85b76-144">See Also</span></span>


[<span data-ttu-id="85b76-145">Lync Server 2013 中的 tblNode</span><span class="sxs-lookup"><span data-stu-id="85b76-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

