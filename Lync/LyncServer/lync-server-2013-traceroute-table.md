---
title: Lync Server 2013： TraceRoute 表格
description: Lync Server 2013： TraceRoute 表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: TraceRoute table
ms:assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205205(v=OCS.15)
ms:contentKeyID: 48185242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8af33e572065fbab1eaaaef684997e7f95edaed9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549059"
---
# <a name="traceroute-table-in-lync-server-2013"></a><span data-ttu-id="4d1e2-103">Lync Server 2013 中的 TraceRoute 表格</span><span class="sxs-lookup"><span data-stu-id="4d1e2-103">TraceRoute table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d1e2-104">_**主題上次修改日期：** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="4d1e2-104">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="4d1e2-105">TraceRoute 表格包含來自呼叫的路由資訊。</span><span class="sxs-lookup"><span data-stu-id="4d1e2-105">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="4d1e2-106">此表格已引進 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="4d1e2-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d1e2-107"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="4d1e2-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="4d1e2-108"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="4d1e2-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="4d1e2-109"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="4d1e2-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="4d1e2-110"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="4d1e2-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d1e2-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="4d1e2-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4d1e2-112">datetime</span><span class="sxs-lookup"><span data-stu-id="4d1e2-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="4d1e2-113">主要，外部</span><span class="sxs-lookup"><span data-stu-id="4d1e2-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="4d1e2-114">通話的開始日期與時間。</span><span class="sxs-lookup"><span data-stu-id="4d1e2-114">Date and time that the call began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d1e2-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="4d1e2-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4d1e2-116">int</span><span class="sxs-lookup"><span data-stu-id="4d1e2-116">int</span></span></p></td>
<td><p><span data-ttu-id="4d1e2-117">主要、外部</span><span class="sxs-lookup"><span data-stu-id="4d1e2-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="4d1e2-118">唯一識別碼，用來區分可能在相同日期和同一時間開始的多個通話。</span><span class="sxs-lookup"><span data-stu-id="4d1e2-118">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d1e2-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="4d1e2-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="4d1e2-120">Tinyint</span><span class="sxs-lookup"><span data-stu-id="4d1e2-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4d1e2-121">主要，外部</span><span class="sxs-lookup"><span data-stu-id="4d1e2-121">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="4d1e2-122">代表通話中使用的影片線條類型。</span><span class="sxs-lookup"><span data-stu-id="4d1e2-122">Represents the type of video line used in the call.</span></span> <span data-ttu-id="4d1e2-123">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="4d1e2-123">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="4d1e2-124">0–音訊</span><span class="sxs-lookup"><span data-stu-id="4d1e2-124">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="4d1e2-125">1–影片</span><span class="sxs-lookup"><span data-stu-id="4d1e2-125">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="4d1e2-126">2–全景影片</span><span class="sxs-lookup"><span data-stu-id="4d1e2-126">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="4d1e2-127">3–應用程式/桌面共用</span><span class="sxs-lookup"><span data-stu-id="4d1e2-127">3 – Application/Desktop sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d1e2-128"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="4d1e2-128"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="4d1e2-129">位</span><span class="sxs-lookup"><span data-stu-id="4d1e2-129">bit</span></span></p></td>
<td><p><span data-ttu-id="4d1e2-130">主要</span><span class="sxs-lookup"><span data-stu-id="4d1e2-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="4d1e2-131">撥出電話的端點。</span><span class="sxs-lookup"><span data-stu-id="4d1e2-131">Endpoint that placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d1e2-132"><strong>跳</strong></span><span class="sxs-lookup"><span data-stu-id="4d1e2-132"><strong>Hop</strong></span></span></p></td>
<td><p><span data-ttu-id="4d1e2-133">int</span><span class="sxs-lookup"><span data-stu-id="4d1e2-133">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4d1e2-134">網路躍點/</span><span class="sxs-lookup"><span data-stu-id="4d1e2-134">Network hop/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d1e2-135"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="4d1e2-135"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="4d1e2-136">int</span><span class="sxs-lookup"><span data-stu-id="4d1e2-136">int</span></span></p></td>
<td><p><span data-ttu-id="4d1e2-137">Foreign</span><span class="sxs-lookup"><span data-stu-id="4d1e2-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4d1e2-138">IP 位址的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="4d1e2-138">Unique identifier for the IP address.</span></span> <span data-ttu-id="4d1e2-139">IP 位址資訊會儲存在 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 的 IPAddress 表格</a>中。</span><span class="sxs-lookup"><span data-stu-id="4d1e2-139">IP address information is stored in the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d1e2-140"><strong>Rtt</strong></span><span class="sxs-lookup"><span data-stu-id="4d1e2-140"><strong>RTT</strong></span></span></p></td>
<td><p><span data-ttu-id="4d1e2-141">int</span><span class="sxs-lookup"><span data-stu-id="4d1e2-141">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4d1e2-142">往返時間。</span><span class="sxs-lookup"><span data-stu-id="4d1e2-142">Roundtrip time.</span></span> <span data-ttu-id="4d1e2-143">「往返時間」會測量語音資料包到達目的地所需的時間長度，然後傳回收到的通知。</span><span class="sxs-lookup"><span data-stu-id="4d1e2-143">The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

