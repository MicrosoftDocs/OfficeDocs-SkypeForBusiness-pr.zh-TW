---
title: 'Lync Server 2013: Endpoint 表格'
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
ms.openlocfilehash: 201e2ae3b44f59f0edb128f58af6c18e18e51931
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042230"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="endpoint-table-in-lync-server-2013"></a><span data-ttu-id="35465-102">Lync Server 2013 中的 endpoint 表格</span><span class="sxs-lookup"><span data-stu-id="35465-102">Endpoint table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35465-103">_**主題上次修改日期：** 2012年-10-02_</span><span class="sxs-lookup"><span data-stu-id="35465-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="35465-104">Endpoint 表格是一種支援資料表儲存記錄資料庫中的工作階段的端點的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="35465-104">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="35465-105">在資料表中的每一筆記錄代表一個端點。</span><span class="sxs-lookup"><span data-stu-id="35465-105">Each record in the table represents one endpoint.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="35465-106"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="35465-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="35465-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="35465-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="35465-108"><strong>主索引鍵 /</strong></span><span class="sxs-lookup"><span data-stu-id="35465-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="35465-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="35465-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="35465-110"><strong>EndpointKey</strong></span><span class="sxs-lookup"><span data-stu-id="35465-110"><strong>EndpointKey</strong></span></span></p></td>
<td><p><span data-ttu-id="35465-111">int</span><span class="sxs-lookup"><span data-stu-id="35465-111">int</span></span></p></td>
<td><p><span data-ttu-id="35465-112">主要</span><span class="sxs-lookup"><span data-stu-id="35465-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="35465-113">用於識別此端點的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="35465-113">Unique number identifying this endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35465-114"><strong>名稱</strong></span><span class="sxs-lookup"><span data-stu-id="35465-114"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="35465-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="35465-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="35465-116">Unique</span><span class="sxs-lookup"><span data-stu-id="35465-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="35465-117">端點名稱。</span><span class="sxs-lookup"><span data-stu-id="35465-117">Endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35465-118"><strong>OS</strong></span><span class="sxs-lookup"><span data-stu-id="35465-118"><strong>OS</strong></span></span></p></td>
<td><p><span data-ttu-id="35465-119">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="35465-119">nvarchar(128)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="35465-120">作業系統 (OS) 的端點。</span><span class="sxs-lookup"><span data-stu-id="35465-120">Operating system (OS) of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35465-121"><strong>CPUName</strong></span><span class="sxs-lookup"><span data-stu-id="35465-121"><strong>CPUName</strong></span></span></p></td>
<td><p><span data-ttu-id="35465-122">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="35465-122">nvarchar(128)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="35465-123">端點的 CPU 名稱。</span><span class="sxs-lookup"><span data-stu-id="35465-123">CPU name of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35465-124"><strong>CPUNumberOfCores</strong></span><span class="sxs-lookup"><span data-stu-id="35465-124"><strong>CPUNumberOfCores</strong></span></span></p></td>
<td><p><span data-ttu-id="35465-125">smallint</span><span class="sxs-lookup"><span data-stu-id="35465-125">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="35465-126">端點的 CPU 核心數。</span><span class="sxs-lookup"><span data-stu-id="35465-126">Number of CPU cores of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35465-127"><strong>CPUProcessorSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="35465-127"><strong>CPUProcessorSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="35465-128">int</span><span class="sxs-lookup"><span data-stu-id="35465-128">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="35465-129">端點的 CPU 處理器速度。</span><span class="sxs-lookup"><span data-stu-id="35465-129">CPU processor speed of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35465-130"><strong>VirtualizationFlag</strong></span><span class="sxs-lookup"><span data-stu-id="35465-130"><strong>VirtualizationFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="35465-131">tinyint</span><span class="sxs-lookup"><span data-stu-id="35465-131">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="35465-132">位元旗幟，指出是否在虛擬環境中執行系統：</span><span class="sxs-lookup"><span data-stu-id="35465-132">Bit flag that indicates if the system is running in a virtualized environment:</span></span></p>
<ul>
<li><p><span data-ttu-id="35465-133">0x0000 – 無</span><span class="sxs-lookup"><span data-stu-id="35465-133">0x0000 – None</span></span></p></li>
<li><p><span data-ttu-id="35465-134">0x0001 – HyperV</span><span class="sxs-lookup"><span data-stu-id="35465-134">0x0001 – HyperV</span></span></p></li>
<li><p><span data-ttu-id="35465-135">0x0002 – VMWare</span><span class="sxs-lookup"><span data-stu-id="35465-135">0x0002 – VMWare</span></span></p></li>
<li><p><span data-ttu-id="35465-136">0x0004 – 虛擬電腦</span><span class="sxs-lookup"><span data-stu-id="35465-136">0x0004 – Virtual PC</span></span></p></li>
<li><p><span data-ttu-id="35465-137">0x0008 – Xen 電腦</span><span class="sxs-lookup"><span data-stu-id="35465-137">0x0008 – Xen PC</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

