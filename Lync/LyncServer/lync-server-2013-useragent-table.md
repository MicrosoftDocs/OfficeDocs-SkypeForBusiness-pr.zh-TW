---
title: Lync Server 2013：UserAgent 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserAgent table
ms:assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398939(v=OCS.15)
ms:contentKeyID: 48185582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09bb2e3a71f81014bcb08952c03b59c93ac6a62f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978128"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragent-table-in-lync-server-2013"></a><span data-ttu-id="26402-102">Lync Server 2013 中的 UserAgent 表格</span><span class="sxs-lookup"><span data-stu-id="26402-102">UserAgent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26402-103">_**主題上次修改日期：** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="26402-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="26402-104">UserAgent 資料表是一種支援資料表，可儲存已參與資料庫中記錄之會話的各種使用者代理程式清單。</span><span class="sxs-lookup"><span data-stu-id="26402-104">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="26402-105">資料表中的每一筆記錄代表一個使用者代理程式</span><span class="sxs-lookup"><span data-stu-id="26402-105">Each record in the table represents one user agent</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="26402-106"><strong>左欄</strong></span><span class="sxs-lookup"><span data-stu-id="26402-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="26402-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="26402-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="26402-108"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="26402-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="26402-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="26402-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="26402-110"><strong>UserAgentKey</strong></span><span class="sxs-lookup"><span data-stu-id="26402-110"><strong>UserAgentKey</strong></span></span></p></td>
<td><p><span data-ttu-id="26402-111">int</span><span class="sxs-lookup"><span data-stu-id="26402-111">int</span></span></p></td>
<td><p><span data-ttu-id="26402-112">首選</span><span class="sxs-lookup"><span data-stu-id="26402-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="26402-113">標識此使用者代理程式的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="26402-113">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26402-114"><strong>UserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="26402-114"><strong>UserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="26402-115">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="26402-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="26402-116">唯一</span><span class="sxs-lookup"><span data-stu-id="26402-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="26402-117">使用者代理程式字串。</span><span class="sxs-lookup"><span data-stu-id="26402-117">User Agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26402-118"><strong>UAType</strong></span><span class="sxs-lookup"><span data-stu-id="26402-118"><strong>UAType</strong></span></span></p></td>
<td><p><span data-ttu-id="26402-119">Smallint</span><span class="sxs-lookup"><span data-stu-id="26402-119">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="26402-120">1是中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="26402-120">1 is Mediation Server.</span></span></p>
<p><span data-ttu-id="26402-121">2是 A/V 會議伺服器。</span><span class="sxs-lookup"><span data-stu-id="26402-121">2 is A/V Conferencing Server.</span></span></p>
<p><span data-ttu-id="26402-122">4為 Lync。</span><span class="sxs-lookup"><span data-stu-id="26402-122">4 is Lync.</span></span></p>
<p><span data-ttu-id="26402-123">8為 IP 電話。</span><span class="sxs-lookup"><span data-stu-id="26402-123">8 is IP Phone.</span></span></p>
<p><span data-ttu-id="26402-124">16為 Live Meeting 主控台。</span><span class="sxs-lookup"><span data-stu-id="26402-124">16 is Live Meeting Console.</span></span></p>
<p><span data-ttu-id="26402-125">32是部署驗證工具（DVT）。</span><span class="sxs-lookup"><span data-stu-id="26402-125">32 is Deployment Validation Tool (DVT).</span></span></p>
<p><span data-ttu-id="26402-126">64是 Macintosh 電腦上的 Lync。</span><span class="sxs-lookup"><span data-stu-id="26402-126">64 is Lync on Macintosh computers.</span></span></p>
<p><span data-ttu-id="26402-127">128是 Office 通訊伺服器 2007 R2 助理。</span><span class="sxs-lookup"><span data-stu-id="26402-127">128 is Office Communications Server 2007 R2 Attendant.</span></span></p>
<p><span data-ttu-id="26402-128">256是會議宣告服務。</span><span class="sxs-lookup"><span data-stu-id="26402-128">256 is Conferencing Announcement service.</span></span></p>
<p><span data-ttu-id="26402-129">512是會議自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="26402-129">512 is Conferencing Auto Attendant.</span></span></p>
<p><span data-ttu-id="26402-130">1024為回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="26402-130">1024 is Response Group application.</span></span></p>
<p><span data-ttu-id="26402-131">2048超出語音控制。</span><span class="sxs-lookup"><span data-stu-id="26402-131">2048 is Outside Voice Control.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

