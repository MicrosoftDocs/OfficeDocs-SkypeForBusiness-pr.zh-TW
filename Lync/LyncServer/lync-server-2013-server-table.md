---
title: Lync Server 2013：伺服器表格
description: Lync Server 2013：伺服器表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server table
ms:assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398801(v=OCS.15)
ms:contentKeyID: 48184890
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00990a91aec64063480d96a16380171990913ad4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576519"
---
# <a name="server-table-in-lync-server-2013"></a><span data-ttu-id="ef1c6-103">Lync Server 2013 中的伺服器表格</span><span class="sxs-lookup"><span data-stu-id="ef1c6-103">Server table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef1c6-104">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ef1c6-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ef1c6-105">伺服器資料表是支援的表格。</span><span class="sxs-lookup"><span data-stu-id="ef1c6-105">The Server table is a supporting table.</span></span> <span data-ttu-id="ef1c6-106">每筆記錄代表一部伺服器。</span><span class="sxs-lookup"><span data-stu-id="ef1c6-106">Each record represents one server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ef1c6-107"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="ef1c6-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ef1c6-108"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="ef1c6-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ef1c6-109"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="ef1c6-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ef1c6-110"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="ef1c6-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ef1c6-111"><strong>ServerKey</strong></span><span class="sxs-lookup"><span data-stu-id="ef1c6-111"><strong>ServerKey</strong></span></span></p></td>
<td><p><span data-ttu-id="ef1c6-112">int</span><span class="sxs-lookup"><span data-stu-id="ef1c6-112">int</span></span></p></td>
<td><p><span data-ttu-id="ef1c6-113">主要</span><span class="sxs-lookup"><span data-stu-id="ef1c6-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="ef1c6-114">用於識別伺服器的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="ef1c6-114">Unique number identifying the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef1c6-115"><strong>FQDNOrIP</strong></span><span class="sxs-lookup"><span data-stu-id="ef1c6-115"><strong>FQDNOrIP</strong></span></span></p></td>
<td><p><span data-ttu-id="ef1c6-116">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="ef1c6-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ef1c6-117">index</span><span class="sxs-lookup"><span data-stu-id="ef1c6-117">index</span></span></p></td>
<td><p><span data-ttu-id="ef1c6-118">MAC 位址字串。</span><span class="sxs-lookup"><span data-stu-id="ef1c6-118">MAC address string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef1c6-119"><strong>ServerType</strong></span><span class="sxs-lookup"><span data-stu-id="ef1c6-119"><strong>ServerType</strong></span></span></p></td>
<td><p><span data-ttu-id="ef1c6-120">int</span><span class="sxs-lookup"><span data-stu-id="ef1c6-120">int</span></span></p></td>
<td><p><span data-ttu-id="ef1c6-121">Foreign</span><span class="sxs-lookup"><span data-stu-id="ef1c6-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ef1c6-122">1：轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="ef1c6-122">1: Mediation Server</span></span></p>
<p><span data-ttu-id="ef1c6-123">2： A/V 會議 Server16394： A/V Edge service32769：閘道</span><span class="sxs-lookup"><span data-stu-id="ef1c6-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef1c6-124"><strong>PoolName</strong></span><span class="sxs-lookup"><span data-stu-id="ef1c6-124"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="ef1c6-125">Nvarchar (512) </span><span class="sxs-lookup"><span data-stu-id="ef1c6-125">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ef1c6-126">伺服器所屬的集區。</span><span class="sxs-lookup"><span data-stu-id="ef1c6-126">Pool the server belongs to.</span></span> <span data-ttu-id="ef1c6-127">僅適用于 A/V 會議伺服器。</span><span class="sxs-lookup"><span data-stu-id="ef1c6-127">Only applicable for the A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef1c6-128"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="ef1c6-128"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="ef1c6-129">datetime</span><span class="sxs-lookup"><span data-stu-id="ef1c6-129">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ef1c6-130">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="ef1c6-130">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

