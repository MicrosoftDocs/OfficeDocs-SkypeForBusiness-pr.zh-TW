---
title: Lync Server 2013： UserAgent 表格
description: Lync Server 2013： UserAgent 表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgent table
ms:assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398939(v=OCS.15)
ms:contentKeyID: 48185582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b701d8384313d0267dd566e0c32242f6cc077472
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558889"
---
# <a name="useragent-table-in-lync-server-2013"></a><span data-ttu-id="21f17-103">Lync Server 2013 中的 UserAgent 表格</span><span class="sxs-lookup"><span data-stu-id="21f17-103">UserAgent table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21f17-104">_**主題上次修改日期：** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="21f17-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="21f17-105">UserAgent 表格是一種支援表格，可儲存已參與資料庫中記錄之會話的各種使用者代理程式清單。</span><span class="sxs-lookup"><span data-stu-id="21f17-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="21f17-106">資料表中的每一筆記錄都代表一個使用者代理程式</span><span class="sxs-lookup"><span data-stu-id="21f17-106">Each record in the table represents one user agent</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="21f17-107"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="21f17-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="21f17-108"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="21f17-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="21f17-109"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="21f17-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="21f17-110"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="21f17-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21f17-111"><strong>UserAgentKey</strong></span><span class="sxs-lookup"><span data-stu-id="21f17-111"><strong>UserAgentKey</strong></span></span></p></td>
<td><p><span data-ttu-id="21f17-112">int</span><span class="sxs-lookup"><span data-stu-id="21f17-112">int</span></span></p></td>
<td><p><span data-ttu-id="21f17-113">主要</span><span class="sxs-lookup"><span data-stu-id="21f17-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="21f17-114">用於識別此使用者代理程式的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="21f17-114">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21f17-115"><strong>UserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="21f17-115"><strong>UserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="21f17-116">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="21f17-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="21f17-117">Unique</span><span class="sxs-lookup"><span data-stu-id="21f17-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="21f17-118">使用者代理程式字串。</span><span class="sxs-lookup"><span data-stu-id="21f17-118">User Agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21f17-119"><strong>UAType</strong></span><span class="sxs-lookup"><span data-stu-id="21f17-119"><strong>UAType</strong></span></span></p></td>
<td><p><span data-ttu-id="21f17-120">Smallint</span><span class="sxs-lookup"><span data-stu-id="21f17-120">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="21f17-121">1是轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="21f17-121">1 is Mediation Server.</span></span></p>
<p><span data-ttu-id="21f17-122">2是 A/V 的會議服務器。</span><span class="sxs-lookup"><span data-stu-id="21f17-122">2 is A/V Conferencing Server.</span></span></p>
<p><span data-ttu-id="21f17-123">4是 Lync。</span><span class="sxs-lookup"><span data-stu-id="21f17-123">4 is Lync.</span></span></p>
<p><span data-ttu-id="21f17-124">8是 IP 電話。</span><span class="sxs-lookup"><span data-stu-id="21f17-124">8 is IP Phone.</span></span></p>
<p><span data-ttu-id="21f17-125">16是 Live Meeting 主控台。</span><span class="sxs-lookup"><span data-stu-id="21f17-125">16 is Live Meeting Console.</span></span></p>
<p><span data-ttu-id="21f17-126">32是部署驗證工具 (DVT) 。</span><span class="sxs-lookup"><span data-stu-id="21f17-126">32 is Deployment Validation Tool (DVT).</span></span></p>
<p><span data-ttu-id="21f17-127">64是 Macintosh 電腦上的 Lync。</span><span class="sxs-lookup"><span data-stu-id="21f17-127">64 is Lync on Macintosh computers.</span></span></p>
<p><span data-ttu-id="21f17-128">128是 Office 通訊伺服器 2007 R2 語音應答。</span><span class="sxs-lookup"><span data-stu-id="21f17-128">128 is Office Communications Server 2007 R2 Attendant.</span></span></p>
<p><span data-ttu-id="21f17-129">256為會議宣告服務。</span><span class="sxs-lookup"><span data-stu-id="21f17-129">256 is Conferencing Announcement service.</span></span></p>
<p><span data-ttu-id="21f17-130">512為會議自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="21f17-130">512 is Conferencing Auto Attendant.</span></span></p>
<p><span data-ttu-id="21f17-131">1024是回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="21f17-131">1024 is Response Group application.</span></span></p>
<p><span data-ttu-id="21f17-132">2048超出語音控制。</span><span class="sxs-lookup"><span data-stu-id="21f17-132">2048 is Outside Voice Control.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

