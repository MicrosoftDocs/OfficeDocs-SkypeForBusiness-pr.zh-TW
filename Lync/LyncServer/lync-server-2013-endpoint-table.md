---
title: Lync Server 2013：端點表格
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
ms.openlocfilehash: 3a71e59b6cf9b4143a5b984cc7b169279aa2cb57
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533320"
---
# <a name="endpoint-table-in-lync-server-2013"></a><span data-ttu-id="3dbe8-102">Lync Server 2013 中的端點表格</span><span class="sxs-lookup"><span data-stu-id="3dbe8-102">Endpoint table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3dbe8-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="3dbe8-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="3dbe8-104">端點表是一種支援資料表，可儲存已參與資料庫中記錄之會話之端點的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="3dbe8-104">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="3dbe8-105">資料表中的每一筆記錄都代表一個端點。</span><span class="sxs-lookup"><span data-stu-id="3dbe8-105">Each record in the table represents one endpoint.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3dbe8-106"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="3dbe8-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="3dbe8-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="3dbe8-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="3dbe8-108"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="3dbe8-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="3dbe8-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="3dbe8-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3dbe8-110"><strong>EndpointKey</strong></span><span class="sxs-lookup"><span data-stu-id="3dbe8-110"><strong>EndpointKey</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbe8-111">int</span><span class="sxs-lookup"><span data-stu-id="3dbe8-111">int</span></span></p></td>
<td><p><span data-ttu-id="3dbe8-112">主要</span><span class="sxs-lookup"><span data-stu-id="3dbe8-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="3dbe8-113">用於識別此端點的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="3dbe8-113">Unique number identifying this endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3dbe8-114"><strong>名稱</strong></span><span class="sxs-lookup"><span data-stu-id="3dbe8-114"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbe8-115">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="3dbe8-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3dbe8-116">Unique</span><span class="sxs-lookup"><span data-stu-id="3dbe8-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="3dbe8-117">端點名稱。</span><span class="sxs-lookup"><span data-stu-id="3dbe8-117">Endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3dbe8-118"><strong>作業系統</strong></span><span class="sxs-lookup"><span data-stu-id="3dbe8-118"><strong>OS</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbe8-119">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="3dbe8-119">nvarchar(128)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3dbe8-120">端點 (作業系統) 。</span><span class="sxs-lookup"><span data-stu-id="3dbe8-120">Operating system (OS) of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3dbe8-121"><strong>CPUName</strong></span><span class="sxs-lookup"><span data-stu-id="3dbe8-121"><strong>CPUName</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbe8-122">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="3dbe8-122">nvarchar(128)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3dbe8-123">端點的 CPU 名稱。</span><span class="sxs-lookup"><span data-stu-id="3dbe8-123">CPU name of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3dbe8-124"><strong>CPUNumberOfCores</strong></span><span class="sxs-lookup"><span data-stu-id="3dbe8-124"><strong>CPUNumberOfCores</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbe8-125">Smallint</span><span class="sxs-lookup"><span data-stu-id="3dbe8-125">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3dbe8-126">端點的 CPU 核心數目。</span><span class="sxs-lookup"><span data-stu-id="3dbe8-126">Number of CPU cores of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3dbe8-127"><strong>CPUProcessorSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="3dbe8-127"><strong>CPUProcessorSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbe8-128">int</span><span class="sxs-lookup"><span data-stu-id="3dbe8-128">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3dbe8-129">端點的 CPU 處理器速度。</span><span class="sxs-lookup"><span data-stu-id="3dbe8-129">CPU processor speed of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3dbe8-130"><strong>VirtualizationFlag</strong></span><span class="sxs-lookup"><span data-stu-id="3dbe8-130"><strong>VirtualizationFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbe8-131">Tinyint</span><span class="sxs-lookup"><span data-stu-id="3dbe8-131">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3dbe8-132">指出系統是否在虛擬化環境中執行的位旗標：</span><span class="sxs-lookup"><span data-stu-id="3dbe8-132">Bit flag that indicates if the system is running in a virtualized environment:</span></span></p>
<ul>
<li><p><span data-ttu-id="3dbe8-133">0x0000 –無</span><span class="sxs-lookup"><span data-stu-id="3dbe8-133">0x0000 – None</span></span></p></li>
<li><p><span data-ttu-id="3dbe8-134">0x0001 – HyperV</span><span class="sxs-lookup"><span data-stu-id="3dbe8-134">0x0001 – HyperV</span></span></p></li>
<li><p><span data-ttu-id="3dbe8-135">0x0002 – VMWare</span><span class="sxs-lookup"><span data-stu-id="3dbe8-135">0x0002 – VMWare</span></span></p></li>
<li><p><span data-ttu-id="3dbe8-136">0x0004 –虛擬 PC</span><span class="sxs-lookup"><span data-stu-id="3dbe8-136">0x0004 – Virtual PC</span></span></p></li>
<li><p><span data-ttu-id="3dbe8-137">0x0008 – Xen 電腦</span><span class="sxs-lookup"><span data-stu-id="3dbe8-137">0x0008 – Xen PC</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

