---
title: Lync Server 2013：tblEnumAttribute
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblEnumAttribute
ms:assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558617(v=OCS.15)
ms:contentKeyID: 48183523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2662f5d0ea9b55f8e3f5320b2e385157bef8bce9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblenumattribute-in-lync-server-2013"></a><span data-ttu-id="7df6b-102">Lync Server 2013 中的 tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="7df6b-102">tblEnumAttribute in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7df6b-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="7df6b-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="7df6b-104">tblEnumAttribute 是一種硬編碼資料表，其中包含在節點資料表中使用的 Visibility 和行為屬性。</span><span class="sxs-lookup"><span data-stu-id="7df6b-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="7df6b-105">分欄</span><span class="sxs-lookup"><span data-stu-id="7df6b-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7df6b-106">左欄</span><span class="sxs-lookup"><span data-stu-id="7df6b-106">Column</span></span></th>
<th><span data-ttu-id="7df6b-107">類型</span><span class="sxs-lookup"><span data-stu-id="7df6b-107">Type</span></span></th>
<th><span data-ttu-id="7df6b-108">描述</span><span class="sxs-lookup"><span data-stu-id="7df6b-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7df6b-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="7df6b-109">attributeID</span></span></p></td>
<td><p><span data-ttu-id="7df6b-110">Smallint，not null</span><span class="sxs-lookup"><span data-stu-id="7df6b-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="7df6b-111">屬性識別碼。</span><span class="sxs-lookup"><span data-stu-id="7df6b-111">ID of the attribute.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7df6b-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="7df6b-112">attributeName</span></span></p></td>
<td><p><span data-ttu-id="7df6b-113">Nvarchar （256），not null</span><span class="sxs-lookup"><span data-stu-id="7df6b-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="7df6b-114">屬性的名稱。</span><span class="sxs-lookup"><span data-stu-id="7df6b-114">Name of the attribute.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="7df6b-115">機碼</span><span class="sxs-lookup"><span data-stu-id="7df6b-115">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7df6b-116">左欄</span><span class="sxs-lookup"><span data-stu-id="7df6b-116">Column</span></span></th>
<th><span data-ttu-id="7df6b-117">描述</span><span class="sxs-lookup"><span data-stu-id="7df6b-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7df6b-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="7df6b-118">attributeID</span></span></p></td>
<td><p><span data-ttu-id="7df6b-119">主鍵。</span><span class="sxs-lookup"><span data-stu-id="7df6b-119">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="7df6b-120">資料表值</span><span class="sxs-lookup"><span data-stu-id="7df6b-120">Table Values</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7df6b-121">attributeID</span><span class="sxs-lookup"><span data-stu-id="7df6b-121">attributeID</span></span></th>
<th><span data-ttu-id="7df6b-122">attributeName</span><span class="sxs-lookup"><span data-stu-id="7df6b-122">attributeName</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7df6b-123">1</span><span class="sxs-lookup"><span data-stu-id="7df6b-123">1</span></span></p></td>
<td><p><span data-ttu-id="7df6b-124">看見.</span><span class="sxs-lookup"><span data-stu-id="7df6b-124">Visibility.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7df6b-125">pplx-2</span><span class="sxs-lookup"><span data-stu-id="7df6b-125">2</span></span></p></td>
<td><p><span data-ttu-id="7df6b-126">行為.</span><span class="sxs-lookup"><span data-stu-id="7df6b-126">Behavior.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="7df6b-127">請參閱</span><span class="sxs-lookup"><span data-stu-id="7df6b-127">See Also</span></span>


[<span data-ttu-id="7df6b-128">Lync Server 2013 中的 tblNode</span><span class="sxs-lookup"><span data-stu-id="7df6b-128">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

