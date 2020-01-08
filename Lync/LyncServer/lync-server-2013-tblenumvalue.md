---
title: Lync Server 2013：tblEnumValue
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblEnumValue
ms:assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615025(v=OCS.15)
ms:contentKeyID: 48185040
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1758daf16575491960415647e4c9bc4b43920d26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="1c23f-102">Lync Server 2013 中的 tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="1c23f-102">tblEnumValue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c23f-103">_**主題上次修改日期：** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="1c23f-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="1c23f-104">tblEnumValue 是一種硬編碼資料表，其中包含在節點資料表中使用之屬性的可見度及行為值。</span><span class="sxs-lookup"><span data-stu-id="1c23f-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="1c23f-105">分欄</span><span class="sxs-lookup"><span data-stu-id="1c23f-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1c23f-106">左欄</span><span class="sxs-lookup"><span data-stu-id="1c23f-106">Column</span></span></th>
<th><span data-ttu-id="1c23f-107">類型</span><span class="sxs-lookup"><span data-stu-id="1c23f-107">Type</span></span></th>
<th><span data-ttu-id="1c23f-108">描述</span><span class="sxs-lookup"><span data-stu-id="1c23f-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c23f-109">valueID</span><span class="sxs-lookup"><span data-stu-id="1c23f-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="1c23f-110">Smallint，not null</span><span class="sxs-lookup"><span data-stu-id="1c23f-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="1c23f-111">值的識別碼。</span><span class="sxs-lookup"><span data-stu-id="1c23f-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c23f-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="1c23f-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="1c23f-113">Smallint，not null</span><span class="sxs-lookup"><span data-stu-id="1c23f-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="1c23f-114">屬性識別碼。</span><span class="sxs-lookup"><span data-stu-id="1c23f-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c23f-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="1c23f-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="1c23f-116">Nvarchar （256），not null</span><span class="sxs-lookup"><span data-stu-id="1c23f-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="1c23f-117">值的名稱。</span><span class="sxs-lookup"><span data-stu-id="1c23f-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="1c23f-118">鍵</span><span class="sxs-lookup"><span data-stu-id="1c23f-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1c23f-119">左欄</span><span class="sxs-lookup"><span data-stu-id="1c23f-119">Column</span></span></th>
<th><span data-ttu-id="1c23f-120">描述</span><span class="sxs-lookup"><span data-stu-id="1c23f-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c23f-121">valueID</span><span class="sxs-lookup"><span data-stu-id="1c23f-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="1c23f-122">主鍵。</span><span class="sxs-lookup"><span data-stu-id="1c23f-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c23f-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="1c23f-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="1c23f-124">在 tblEnumAttribute attributeID 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="1c23f-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="1c23f-125">資料表值</span><span class="sxs-lookup"><span data-stu-id="1c23f-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1c23f-126">valueID</span><span class="sxs-lookup"><span data-stu-id="1c23f-126">valueID</span></span></th>
<th><span data-ttu-id="1c23f-127">attributeID</span><span class="sxs-lookup"><span data-stu-id="1c23f-127">attributeID</span></span></th>
<th><span data-ttu-id="1c23f-128">attributeValue</span><span class="sxs-lookup"><span data-stu-id="1c23f-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c23f-129">pplx-2</span><span class="sxs-lookup"><span data-stu-id="1c23f-129">2</span></span></p></td>
<td><p><span data-ttu-id="1c23f-130">1</span><span class="sxs-lookup"><span data-stu-id="1c23f-130">1</span></span></p></td>
<td><p><span data-ttu-id="1c23f-131">私有</span><span class="sxs-lookup"><span data-stu-id="1c23f-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c23f-132">3</span><span class="sxs-lookup"><span data-stu-id="1c23f-132">3</span></span></p></td>
<td><p><span data-ttu-id="1c23f-133">1</span><span class="sxs-lookup"><span data-stu-id="1c23f-133">1</span></span></p></td>
<td><p><span data-ttu-id="1c23f-134">討論</span><span class="sxs-lookup"><span data-stu-id="1c23f-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c23f-135">4</span><span class="sxs-lookup"><span data-stu-id="1c23f-135">4</span></span></p></td>
<td><p><span data-ttu-id="1c23f-136">pplx-2</span><span class="sxs-lookup"><span data-stu-id="1c23f-136">2</span></span></p></td>
<td><p><span data-ttu-id="1c23f-137">標準</span><span class="sxs-lookup"><span data-stu-id="1c23f-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c23f-138">500</span><span class="sxs-lookup"><span data-stu-id="1c23f-138">5</span></span></p></td>
<td><p><span data-ttu-id="1c23f-139">pplx-2</span><span class="sxs-lookup"><span data-stu-id="1c23f-139">2</span></span></p></td>
<td><p><span data-ttu-id="1c23f-140">auditorium</span><span class="sxs-lookup"><span data-stu-id="1c23f-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c23f-141">6</span><span class="sxs-lookup"><span data-stu-id="1c23f-141">6</span></span></p></td>
<td><p><span data-ttu-id="1c23f-142">1</span><span class="sxs-lookup"><span data-stu-id="1c23f-142">1</span></span></p></td>
<td><p><span data-ttu-id="1c23f-143">開啟</span><span class="sxs-lookup"><span data-stu-id="1c23f-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="1c23f-144">請參閱</span><span class="sxs-lookup"><span data-stu-id="1c23f-144">See Also</span></span>


[<span data-ttu-id="1c23f-145">Lync Server 2013 中的 tblNode</span><span class="sxs-lookup"><span data-stu-id="1c23f-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

