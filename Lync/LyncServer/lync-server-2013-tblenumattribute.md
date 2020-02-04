---
title: Lync Server 2013：tblEnumAttribute
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
ms.openlocfilehash: 73ac5a7cf26c97b31daf5785a90fac102c50e480
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblenumattribute-in-lync-server-2013"></a><span data-ttu-id="4a5e7-102">Lync Server 2013 中的 tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="4a5e7-102">tblEnumAttribute in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a5e7-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="4a5e7-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="4a5e7-104">tblEnumAttribute 是一種硬編碼資料表，其中包含在節點資料表中使用的 Visibility 和行為屬性。</span><span class="sxs-lookup"><span data-stu-id="4a5e7-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="4a5e7-105">分欄</span><span class="sxs-lookup"><span data-stu-id="4a5e7-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4a5e7-106">左欄</span><span class="sxs-lookup"><span data-stu-id="4a5e7-106">Column</span></span></th>
<th><span data-ttu-id="4a5e7-107">類型</span><span class="sxs-lookup"><span data-stu-id="4a5e7-107">Type</span></span></th>
<th><span data-ttu-id="4a5e7-108">說明</span><span class="sxs-lookup"><span data-stu-id="4a5e7-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a5e7-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="4a5e7-109">attributeID</span></span></p></td>
<td><p><span data-ttu-id="4a5e7-110">Smallint，not null</span><span class="sxs-lookup"><span data-stu-id="4a5e7-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="4a5e7-111">屬性識別碼。</span><span class="sxs-lookup"><span data-stu-id="4a5e7-111">ID of the attribute.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a5e7-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="4a5e7-112">attributeName</span></span></p></td>
<td><p><span data-ttu-id="4a5e7-113">Nvarchar （256），not null</span><span class="sxs-lookup"><span data-stu-id="4a5e7-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="4a5e7-114">屬性的名稱。</span><span class="sxs-lookup"><span data-stu-id="4a5e7-114">Name of the attribute.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="4a5e7-115">機碼</span><span class="sxs-lookup"><span data-stu-id="4a5e7-115">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4a5e7-116">左欄</span><span class="sxs-lookup"><span data-stu-id="4a5e7-116">Column</span></span></th>
<th><span data-ttu-id="4a5e7-117">說明</span><span class="sxs-lookup"><span data-stu-id="4a5e7-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a5e7-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="4a5e7-118">attributeID</span></span></p></td>
<td><p><span data-ttu-id="4a5e7-119">主鍵。</span><span class="sxs-lookup"><span data-stu-id="4a5e7-119">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="4a5e7-120">資料表值</span><span class="sxs-lookup"><span data-stu-id="4a5e7-120">Table Values</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4a5e7-121">attributeID</span><span class="sxs-lookup"><span data-stu-id="4a5e7-121">attributeID</span></span></th>
<th><span data-ttu-id="4a5e7-122">attributeName</span><span class="sxs-lookup"><span data-stu-id="4a5e7-122">attributeName</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a5e7-123">1</span><span class="sxs-lookup"><span data-stu-id="4a5e7-123">1</span></span></p></td>
<td><p><span data-ttu-id="4a5e7-124">看見.</span><span class="sxs-lookup"><span data-stu-id="4a5e7-124">Visibility.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a5e7-125">2</span><span class="sxs-lookup"><span data-stu-id="4a5e7-125">2</span></span></p></td>
<td><p><span data-ttu-id="4a5e7-126">行為.</span><span class="sxs-lookup"><span data-stu-id="4a5e7-126">Behavior.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="4a5e7-127">請參閱</span><span class="sxs-lookup"><span data-stu-id="4a5e7-127">See Also</span></span>


[<span data-ttu-id="4a5e7-128">Lync Server 2013 中的 tblNode</span><span class="sxs-lookup"><span data-stu-id="4a5e7-128">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

