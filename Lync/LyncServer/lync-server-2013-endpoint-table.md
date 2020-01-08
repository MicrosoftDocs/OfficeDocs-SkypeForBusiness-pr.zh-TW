---
title: Lync Server 2013：Endpoint 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Endpoint table
ms:assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398327(v=OCS.15)
ms:contentKeyID: 48184098
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cedf4d85cefd8a9fefb9f0ee4608f4a290fdc09
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974599"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="endpoint-table-in-lync-server-2013"></a><span data-ttu-id="27e7a-102">Lync Server 2013 中的 Endpoint 表格</span><span class="sxs-lookup"><span data-stu-id="27e7a-102">Endpoint table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27e7a-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="27e7a-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="27e7a-104">端點資料表是一個支援資料表，可儲存已參與在資料庫中記錄會話之端點的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="27e7a-104">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="27e7a-105">資料表中的每一筆記錄代表一個端點。</span><span class="sxs-lookup"><span data-stu-id="27e7a-105">Each record in the table represents one endpoint.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27e7a-106"><strong>左欄</strong></span><span class="sxs-lookup"><span data-stu-id="27e7a-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="27e7a-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="27e7a-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="27e7a-108"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="27e7a-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="27e7a-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="27e7a-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27e7a-110"><strong>EndpointKey</strong></span><span class="sxs-lookup"><span data-stu-id="27e7a-110"><strong>EndpointKey</strong></span></span></p></td>
<td><p><span data-ttu-id="27e7a-111">int</span><span class="sxs-lookup"><span data-stu-id="27e7a-111">int</span></span></p></td>
<td><p><span data-ttu-id="27e7a-112">首選</span><span class="sxs-lookup"><span data-stu-id="27e7a-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="27e7a-113">標識此端點的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="27e7a-113">Unique number identifying this endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27e7a-114"><strong>名稱</strong></span><span class="sxs-lookup"><span data-stu-id="27e7a-114"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="27e7a-115">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="27e7a-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="27e7a-116">唯一</span><span class="sxs-lookup"><span data-stu-id="27e7a-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="27e7a-117">端點名稱。</span><span class="sxs-lookup"><span data-stu-id="27e7a-117">Endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27e7a-118"><strong>OS</strong></span><span class="sxs-lookup"><span data-stu-id="27e7a-118"><strong>OS</strong></span></span></p></td>
<td><p><span data-ttu-id="27e7a-119">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="27e7a-119">nvarchar(128)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="27e7a-120">端點的作業系統（OS）。</span><span class="sxs-lookup"><span data-stu-id="27e7a-120">Operating system (OS) of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27e7a-121"><strong>CPUName</strong></span><span class="sxs-lookup"><span data-stu-id="27e7a-121"><strong>CPUName</strong></span></span></p></td>
<td><p><span data-ttu-id="27e7a-122">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="27e7a-122">nvarchar(128)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="27e7a-123">端點的 CPU 名稱。</span><span class="sxs-lookup"><span data-stu-id="27e7a-123">CPU name of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27e7a-124"><strong>CPUNumberOfCores</strong></span><span class="sxs-lookup"><span data-stu-id="27e7a-124"><strong>CPUNumberOfCores</strong></span></span></p></td>
<td><p><span data-ttu-id="27e7a-125">Smallint</span><span class="sxs-lookup"><span data-stu-id="27e7a-125">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="27e7a-126">端點的 CPU 核心數。</span><span class="sxs-lookup"><span data-stu-id="27e7a-126">Number of CPU cores of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27e7a-127"><strong>CPUProcessorSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="27e7a-127"><strong>CPUProcessorSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="27e7a-128">int</span><span class="sxs-lookup"><span data-stu-id="27e7a-128">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="27e7a-129">端點的 CPU 處理器速度。</span><span class="sxs-lookup"><span data-stu-id="27e7a-129">CPU processor speed of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27e7a-130"><strong>VirtualizationFlag</strong></span><span class="sxs-lookup"><span data-stu-id="27e7a-130"><strong>VirtualizationFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="27e7a-131">Tinyint</span><span class="sxs-lookup"><span data-stu-id="27e7a-131">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="27e7a-132">表示系統是否正在虛擬化環境中執行的位標誌：</span><span class="sxs-lookup"><span data-stu-id="27e7a-132">Bit flag that indicates if the system is running in a virtualized environment:</span></span></p>
<ul>
<li><p><span data-ttu-id="27e7a-133">0x0000 –無</span><span class="sxs-lookup"><span data-stu-id="27e7a-133">0x0000 – None</span></span></p></li>
<li><p><span data-ttu-id="27e7a-134">0x0001 – HyperV</span><span class="sxs-lookup"><span data-stu-id="27e7a-134">0x0001 – HyperV</span></span></p></li>
<li><p><span data-ttu-id="27e7a-135">0x0002-VMWare</span><span class="sxs-lookup"><span data-stu-id="27e7a-135">0x0002 – VMWare</span></span></p></li>
<li><p><span data-ttu-id="27e7a-136">0x0004 –虛擬電腦</span><span class="sxs-lookup"><span data-stu-id="27e7a-136">0x0004 – Virtual PC</span></span></p></li>
<li><p><span data-ttu-id="27e7a-137">0x0008 – Xen 電腦</span><span class="sxs-lookup"><span data-stu-id="27e7a-137">0x0008 – Xen PC</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

