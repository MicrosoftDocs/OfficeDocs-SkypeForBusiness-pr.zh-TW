---
title: Lync Server 2013： TraceRoute 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: TraceRoute table
ms:assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205205(v=OCS.15)
ms:contentKeyID: 48185242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1dd0f9bc3bd900d71a316bf2ff1ab7612a51194
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982420"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="traceroute-table-in-lync-server-2013"></a><span data-ttu-id="64ccb-102">Lync Server 2013 中的 TraceRoute 表格</span><span class="sxs-lookup"><span data-stu-id="64ccb-102">TraceRoute table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64ccb-103">_**主題上次修改日期：** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="64ccb-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="64ccb-104">TraceRoute 表格包含來自呼叫的路由資訊。</span><span class="sxs-lookup"><span data-stu-id="64ccb-104">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="64ccb-105">此表格是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="64ccb-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="64ccb-106"><strong>左欄</strong></span><span class="sxs-lookup"><span data-stu-id="64ccb-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="64ccb-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="64ccb-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="64ccb-108"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="64ccb-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="64ccb-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="64ccb-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="64ccb-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="64ccb-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="64ccb-111">datetime</span><span class="sxs-lookup"><span data-stu-id="64ccb-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="64ccb-112">主要、外部</span><span class="sxs-lookup"><span data-stu-id="64ccb-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="64ccb-113">通話的開始日期和時間。</span><span class="sxs-lookup"><span data-stu-id="64ccb-113">Date and time that the call began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64ccb-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="64ccb-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="64ccb-115">int</span><span class="sxs-lookup"><span data-stu-id="64ccb-115">int</span></span></p></td>
<td><p><span data-ttu-id="64ccb-116">主要、外部</span><span class="sxs-lookup"><span data-stu-id="64ccb-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="64ccb-117">唯一識別碼，用來區分可能已在相同日期和同一時間開始的多個通話。</span><span class="sxs-lookup"><span data-stu-id="64ccb-117">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64ccb-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="64ccb-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="64ccb-119">Tinyint</span><span class="sxs-lookup"><span data-stu-id="64ccb-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="64ccb-120">主要、外部</span><span class="sxs-lookup"><span data-stu-id="64ccb-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="64ccb-121">代表通話中使用的影片線條類型。</span><span class="sxs-lookup"><span data-stu-id="64ccb-121">Represents the type of video line used in the call.</span></span> <span data-ttu-id="64ccb-122">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="64ccb-122">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="64ccb-123">0-音訊</span><span class="sxs-lookup"><span data-stu-id="64ccb-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="64ccb-124">1–影片</span><span class="sxs-lookup"><span data-stu-id="64ccb-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="64ccb-125">2-全景影片</span><span class="sxs-lookup"><span data-stu-id="64ccb-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="64ccb-126">3-應用程式/桌面共用</span><span class="sxs-lookup"><span data-stu-id="64ccb-126">3 – Application/Desktop sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64ccb-127"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="64ccb-127"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="64ccb-128">稍微</span><span class="sxs-lookup"><span data-stu-id="64ccb-128">bit</span></span></p></td>
<td><p><span data-ttu-id="64ccb-129">首選</span><span class="sxs-lookup"><span data-stu-id="64ccb-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="64ccb-130">放置通話的端點。</span><span class="sxs-lookup"><span data-stu-id="64ccb-130">Endpoint that placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64ccb-131"><strong>中繼站</strong></span><span class="sxs-lookup"><span data-stu-id="64ccb-131"><strong>Hop</strong></span></span></p></td>
<td><p><span data-ttu-id="64ccb-132">int</span><span class="sxs-lookup"><span data-stu-id="64ccb-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="64ccb-133">Network hop/</span><span class="sxs-lookup"><span data-stu-id="64ccb-133">Network hop/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64ccb-134"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="64ccb-134"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="64ccb-135">int</span><span class="sxs-lookup"><span data-stu-id="64ccb-135">int</span></span></p></td>
<td><p><span data-ttu-id="64ccb-136">外</span><span class="sxs-lookup"><span data-stu-id="64ccb-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="64ccb-137">IP 位址的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="64ccb-137">Unique identifier for the IP address.</span></span> <span data-ttu-id="64ccb-138">IP 位址資訊會儲存在<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013</a>的 [IPAddress] 資料表中。</span><span class="sxs-lookup"><span data-stu-id="64ccb-138">IP address information is stored in the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64ccb-139"><strong>RTT</strong></span><span class="sxs-lookup"><span data-stu-id="64ccb-139"><strong>RTT</strong></span></span></p></td>
<td><p><span data-ttu-id="64ccb-140">int</span><span class="sxs-lookup"><span data-stu-id="64ccb-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="64ccb-141">往返時間。</span><span class="sxs-lookup"><span data-stu-id="64ccb-141">Roundtrip time.</span></span> <span data-ttu-id="64ccb-142">往返時間會測量語音資料包達到目的地所需的時間長度，然後傳回接收的通知。</span><span class="sxs-lookup"><span data-stu-id="64ccb-142">The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

