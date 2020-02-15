---
title: 'Lync Server 2013: TraceRoute 表'
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
ms.openlocfilehash: afb8cfb65fdf8fdbb4c281127caafd394cb878af
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036493"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="traceroute-table-in-lync-server-2013"></a><span data-ttu-id="39932-102">Lync Server 2013 中的 TraceRoute 表</span><span class="sxs-lookup"><span data-stu-id="39932-102">TraceRoute table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39932-103">_**上次修改主題：** 2014年-02-21_</span><span class="sxs-lookup"><span data-stu-id="39932-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="39932-104">TraceRoute 表包含從呼叫路由資訊。</span><span class="sxs-lookup"><span data-stu-id="39932-104">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="39932-105">Microsoft Lync Server 2013 中已採用此表格。</span><span class="sxs-lookup"><span data-stu-id="39932-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39932-106"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="39932-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="39932-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="39932-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="39932-108"><strong>主索引鍵 /</strong></span><span class="sxs-lookup"><span data-stu-id="39932-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="39932-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="39932-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39932-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="39932-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="39932-111">datetime</span><span class="sxs-lookup"><span data-stu-id="39932-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="39932-112">主要、外部</span><span class="sxs-lookup"><span data-stu-id="39932-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="39932-113">日期和時間通話的開始。</span><span class="sxs-lookup"><span data-stu-id="39932-113">Date and time that the call began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39932-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="39932-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="39932-115">int</span><span class="sxs-lookup"><span data-stu-id="39932-115">int</span></span></p></td>
<td><p><span data-ttu-id="39932-116">主要、外部</span><span class="sxs-lookup"><span data-stu-id="39932-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="39932-117">用來區別同一日期，並在同一時間可能已開始之多個通話的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="39932-117">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39932-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="39932-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="39932-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="39932-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="39932-120">主要，外部</span><span class="sxs-lookup"><span data-stu-id="39932-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="39932-121">代表呼叫時所使用的視訊線的類型。</span><span class="sxs-lookup"><span data-stu-id="39932-121">Represents the type of video line used in the call.</span></span> <span data-ttu-id="39932-122">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="39932-122">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="39932-123">0 – 音訊</span><span class="sxs-lookup"><span data-stu-id="39932-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="39932-124">1 – 影片</span><span class="sxs-lookup"><span data-stu-id="39932-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="39932-125">2 – 全景視訊</span><span class="sxs-lookup"><span data-stu-id="39932-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="39932-126">3 – 應用程式/桌面共用</span><span class="sxs-lookup"><span data-stu-id="39932-126">3 – Application/Desktop sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39932-127"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="39932-127"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="39932-128">位元</span><span class="sxs-lookup"><span data-stu-id="39932-128">bit</span></span></p></td>
<td><p><span data-ttu-id="39932-129">主要</span><span class="sxs-lookup"><span data-stu-id="39932-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="39932-130">起始通話的端點。</span><span class="sxs-lookup"><span data-stu-id="39932-130">Endpoint that placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39932-131"><strong>一個躍點</strong></span><span class="sxs-lookup"><span data-stu-id="39932-131"><strong>Hop</strong></span></span></p></td>
<td><p><span data-ttu-id="39932-132">int</span><span class="sxs-lookup"><span data-stu-id="39932-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="39932-133">網路躍點 /</span><span class="sxs-lookup"><span data-stu-id="39932-133">Network hop/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39932-134"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="39932-134"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="39932-135">int</span><span class="sxs-lookup"><span data-stu-id="39932-135">int</span></span></p></td>
<td><p><span data-ttu-id="39932-136">Foreign</span><span class="sxs-lookup"><span data-stu-id="39932-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="39932-137">IP 位址的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="39932-137">Unique identifier for the IP address.</span></span> <span data-ttu-id="39932-138">IP 位址資訊都會儲存在<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表</a>。</span><span class="sxs-lookup"><span data-stu-id="39932-138">IP address information is stored in the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39932-139"><strong>RTT</strong></span><span class="sxs-lookup"><span data-stu-id="39932-139"><strong>RTT</strong></span></span></p></td>
<td><p><span data-ttu-id="39932-140">int</span><span class="sxs-lookup"><span data-stu-id="39932-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="39932-141">往返時間。</span><span class="sxs-lookup"><span data-stu-id="39932-141">Roundtrip time.</span></span> <span data-ttu-id="39932-142">往返時間來測量語音封包，以到達其目的地，然後傳送後已收到的通知所花費的時間的量。</span><span class="sxs-lookup"><span data-stu-id="39932-142">The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

