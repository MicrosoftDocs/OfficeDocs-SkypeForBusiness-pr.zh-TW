---
title: 'Lync Server 2013: tblEnumAttribute'
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
ms.openlocfilehash: 67bce18c46b4286afe287ab04a76b71e73b7a5a3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblenumattribute-in-lync-server-2013"></a><span data-ttu-id="c6f48-102">Lync Server 2013 中的 tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="c6f48-102">tblEnumAttribute in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6f48-103">_**主題上次修改日期：** 2012年-09-12_</span><span class="sxs-lookup"><span data-stu-id="c6f48-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="c6f48-104">tblEnumAttribute 表格是一種硬式編碼的表格，其中含有節點表格中所用的可見度及行為屬性。</span><span class="sxs-lookup"><span data-stu-id="c6f48-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="c6f48-105">Columns</span><span class="sxs-lookup"><span data-stu-id="c6f48-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6f48-106">欄</span><span class="sxs-lookup"><span data-stu-id="c6f48-106">Column</span></span></th>
<th><span data-ttu-id="c6f48-107">類型	</span><span class="sxs-lookup"><span data-stu-id="c6f48-107">Type</span></span></th>
<th><span data-ttu-id="c6f48-108">描述</span><span class="sxs-lookup"><span data-stu-id="c6f48-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6f48-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="c6f48-109">attributeID</span></span></p></td>
<td><p><span data-ttu-id="c6f48-110">smallint，非 null</span><span class="sxs-lookup"><span data-stu-id="c6f48-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="c6f48-111">屬性的識別碼。</span><span class="sxs-lookup"><span data-stu-id="c6f48-111">ID of the attribute.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6f48-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="c6f48-112">attributeName</span></span></p></td>
<td><p><span data-ttu-id="c6f48-113">nvarchar (256)，非 null</span><span class="sxs-lookup"><span data-stu-id="c6f48-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="c6f48-114">屬性名稱。</span><span class="sxs-lookup"><span data-stu-id="c6f48-114">Name of the attribute.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="c6f48-115">索引鍵</span><span class="sxs-lookup"><span data-stu-id="c6f48-115">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6f48-116">欄</span><span class="sxs-lookup"><span data-stu-id="c6f48-116">Column</span></span></th>
<th><span data-ttu-id="c6f48-117">描述</span><span class="sxs-lookup"><span data-stu-id="c6f48-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6f48-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="c6f48-118">attributeID</span></span></p></td>
<td><p><span data-ttu-id="c6f48-119">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="c6f48-119">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="c6f48-120">表格值</span><span class="sxs-lookup"><span data-stu-id="c6f48-120">Table Values</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6f48-121">attributeID</span><span class="sxs-lookup"><span data-stu-id="c6f48-121">attributeID</span></span></th>
<th><span data-ttu-id="c6f48-122">attributeName</span><span class="sxs-lookup"><span data-stu-id="c6f48-122">attributeName</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6f48-123">1</span><span class="sxs-lookup"><span data-stu-id="c6f48-123">1</span></span></p></td>
<td><p><span data-ttu-id="c6f48-124">可見性。</span><span class="sxs-lookup"><span data-stu-id="c6f48-124">Visibility.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6f48-125">2</span><span class="sxs-lookup"><span data-stu-id="c6f48-125">2</span></span></p></td>
<td><p><span data-ttu-id="c6f48-126">行為。</span><span class="sxs-lookup"><span data-stu-id="c6f48-126">Behavior.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="c6f48-127">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c6f48-127">See Also</span></span>


[<span data-ttu-id="c6f48-128">Lync Server 2013 中的 tblNode</span><span class="sxs-lookup"><span data-stu-id="c6f48-128">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

