---
title: Lync Server 2013： tblEnumAttribute
description: Lync Server 2013： tblEnumAttribute。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblEnumAttribute
ms:assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558617(v=OCS.15)
ms:contentKeyID: 48183523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca979a68e758ad47b691ac704f24c68c1841938a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571389"
---
# <a name="tblenumattribute-in-lync-server-2013"></a><span data-ttu-id="cf537-103">Lync Server 2013 中的 tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="cf537-103">tblEnumAttribute in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf537-104">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="cf537-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="cf537-105">tblEnumAttribute 表格是一種硬式編碼的表格，其中含有節點表格中所用的可見度及行為屬性。</span><span class="sxs-lookup"><span data-stu-id="cf537-105">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="cf537-106">Columns</span><span class="sxs-lookup"><span data-stu-id="cf537-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf537-107">欄</span><span class="sxs-lookup"><span data-stu-id="cf537-107">Column</span></span></th>
<th><span data-ttu-id="cf537-108">類型</span><span class="sxs-lookup"><span data-stu-id="cf537-108">Type</span></span></th>
<th><span data-ttu-id="cf537-109">描述</span><span class="sxs-lookup"><span data-stu-id="cf537-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf537-110">attributeID:</span><span class="sxs-lookup"><span data-stu-id="cf537-110">attributeID</span></span></p></td>
<td><p><span data-ttu-id="cf537-111">smallint，非 null</span><span class="sxs-lookup"><span data-stu-id="cf537-111">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="cf537-112">屬性的識別碼。</span><span class="sxs-lookup"><span data-stu-id="cf537-112">ID of the attribute.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf537-113">attributeName</span><span class="sxs-lookup"><span data-stu-id="cf537-113">attributeName</span></span></p></td>
<td><p><span data-ttu-id="cf537-114">nvarchar (256)，非 null</span><span class="sxs-lookup"><span data-stu-id="cf537-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="cf537-115">屬性名稱。</span><span class="sxs-lookup"><span data-stu-id="cf537-115">Name of the attribute.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="cf537-116">索引鍵</span><span class="sxs-lookup"><span data-stu-id="cf537-116">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf537-117">欄</span><span class="sxs-lookup"><span data-stu-id="cf537-117">Column</span></span></th>
<th><span data-ttu-id="cf537-118">描述</span><span class="sxs-lookup"><span data-stu-id="cf537-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf537-119">attributeID:</span><span class="sxs-lookup"><span data-stu-id="cf537-119">attributeID</span></span></p></td>
<td><p><span data-ttu-id="cf537-120">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="cf537-120">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="cf537-121">表格值</span><span class="sxs-lookup"><span data-stu-id="cf537-121">Table Values</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf537-122">attributeID:</span><span class="sxs-lookup"><span data-stu-id="cf537-122">attributeID</span></span></th>
<th><span data-ttu-id="cf537-123">attributeName</span><span class="sxs-lookup"><span data-stu-id="cf537-123">attributeName</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf537-124">1 </span><span class="sxs-lookup"><span data-stu-id="cf537-124">1</span></span></p></td>
<td><p><span data-ttu-id="cf537-125">知名度。</span><span class="sxs-lookup"><span data-stu-id="cf537-125">Visibility.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf537-126">第</span><span class="sxs-lookup"><span data-stu-id="cf537-126">2</span></span></p></td>
<td><p><span data-ttu-id="cf537-127">行為。</span><span class="sxs-lookup"><span data-stu-id="cf537-127">Behavior.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="cf537-128">另請參閱</span><span class="sxs-lookup"><span data-stu-id="cf537-128">See Also</span></span>


[<span data-ttu-id="cf537-129">Lync Server 2013 中的 tblNode</span><span class="sxs-lookup"><span data-stu-id="cf537-129">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

