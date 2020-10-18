---
title: Lync Server 2013：端點表格
description: Lync Server 2013： Endpoint table。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Endpoint table
ms:assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398327(v=OCS.15)
ms:contentKeyID: 48184098
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 614872eee41b5d8e56da4b96cf5bbe3a4a1cf4d2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575619"
---
# <a name="endpoint-table-in-lync-server-2013"></a><span data-ttu-id="8f16c-103">Lync Server 2013 中的端點表格</span><span class="sxs-lookup"><span data-stu-id="8f16c-103">Endpoint table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f16c-104">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="8f16c-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="8f16c-105">端點表是一種支援資料表，可儲存已參與資料庫中記錄之會話之端點的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="8f16c-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="8f16c-106">資料表中的每一筆記錄都代表一個端點。</span><span class="sxs-lookup"><span data-stu-id="8f16c-106">Each record in the table represents one endpoint.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8f16c-107"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="8f16c-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="8f16c-108"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="8f16c-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="8f16c-109"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="8f16c-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="8f16c-110"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="8f16c-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f16c-111"><strong>EndpointKey</strong></span><span class="sxs-lookup"><span data-stu-id="8f16c-111"><strong>EndpointKey</strong></span></span></p></td>
<td><p><span data-ttu-id="8f16c-112">int</span><span class="sxs-lookup"><span data-stu-id="8f16c-112">int</span></span></p></td>
<td><p><span data-ttu-id="8f16c-113">主要</span><span class="sxs-lookup"><span data-stu-id="8f16c-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="8f16c-114">用於識別此端點的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="8f16c-114">Unique number identifying this endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f16c-115"><strong>名稱</strong></span><span class="sxs-lookup"><span data-stu-id="8f16c-115"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="8f16c-116">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="8f16c-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8f16c-117">Unique</span><span class="sxs-lookup"><span data-stu-id="8f16c-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="8f16c-118">端點名稱。</span><span class="sxs-lookup"><span data-stu-id="8f16c-118">Endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f16c-119"><strong>作業系統</strong></span><span class="sxs-lookup"><span data-stu-id="8f16c-119"><strong>OS</strong></span></span></p></td>
<td><p><span data-ttu-id="8f16c-120">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="8f16c-120">nvarchar(128)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8f16c-121">端點 (作業系統) 。</span><span class="sxs-lookup"><span data-stu-id="8f16c-121">Operating system (OS) of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f16c-122"><strong>CPUName</strong></span><span class="sxs-lookup"><span data-stu-id="8f16c-122"><strong>CPUName</strong></span></span></p></td>
<td><p><span data-ttu-id="8f16c-123">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="8f16c-123">nvarchar(128)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8f16c-124">端點的 CPU 名稱。</span><span class="sxs-lookup"><span data-stu-id="8f16c-124">CPU name of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f16c-125"><strong>CPUNumberOfCores</strong></span><span class="sxs-lookup"><span data-stu-id="8f16c-125"><strong>CPUNumberOfCores</strong></span></span></p></td>
<td><p><span data-ttu-id="8f16c-126">Smallint</span><span class="sxs-lookup"><span data-stu-id="8f16c-126">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8f16c-127">端點的 CPU 核心數目。</span><span class="sxs-lookup"><span data-stu-id="8f16c-127">Number of CPU cores of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f16c-128"><strong>CPUProcessorSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="8f16c-128"><strong>CPUProcessorSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="8f16c-129">int</span><span class="sxs-lookup"><span data-stu-id="8f16c-129">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8f16c-130">端點的 CPU 處理器速度。</span><span class="sxs-lookup"><span data-stu-id="8f16c-130">CPU processor speed of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f16c-131"><strong>VirtualizationFlag</strong></span><span class="sxs-lookup"><span data-stu-id="8f16c-131"><strong>VirtualizationFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="8f16c-132">Tinyint</span><span class="sxs-lookup"><span data-stu-id="8f16c-132">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8f16c-133">指出系統是否在虛擬化環境中執行的位旗標：</span><span class="sxs-lookup"><span data-stu-id="8f16c-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span></p>
<ul>
<li><p><span data-ttu-id="8f16c-134">0x0000 –無</span><span class="sxs-lookup"><span data-stu-id="8f16c-134">0x0000 – None</span></span></p></li>
<li><p><span data-ttu-id="8f16c-135">0x0001 – HyperV</span><span class="sxs-lookup"><span data-stu-id="8f16c-135">0x0001 – HyperV</span></span></p></li>
<li><p><span data-ttu-id="8f16c-136">0x0002 – VMWare</span><span class="sxs-lookup"><span data-stu-id="8f16c-136">0x0002 – VMWare</span></span></p></li>
<li><p><span data-ttu-id="8f16c-137">0x0004 –虛擬 PC</span><span class="sxs-lookup"><span data-stu-id="8f16c-137">0x0004 – Virtual PC</span></span></p></li>
<li><p><span data-ttu-id="8f16c-138">0x0008 – Xen 電腦</span><span class="sxs-lookup"><span data-stu-id="8f16c-138">0x0008 – Xen PC</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

