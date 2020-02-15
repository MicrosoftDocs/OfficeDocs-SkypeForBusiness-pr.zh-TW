---
title: 'Lync Server 2013: UserAgent 表格'
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
ms.openlocfilehash: 0ba13a18436c7a55ca68931ff2794fd584be84f9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007622"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragent-table-in-lync-server-2013"></a><span data-ttu-id="0cf87-102">Lync Server 2013 中的 UserAgent 表格</span><span class="sxs-lookup"><span data-stu-id="0cf87-102">UserAgent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0cf87-103">_**主題上次修改日期：** 2012年-05-25_</span><span class="sxs-lookup"><span data-stu-id="0cf87-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="0cf87-104">UserAgent 表格是一種支援資料表儲存的記錄資料庫中的工作階段的各種使用者代理程式清單。</span><span class="sxs-lookup"><span data-stu-id="0cf87-104">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="0cf87-105">在資料表中的每一筆記錄代表一個使用者代理程式</span><span class="sxs-lookup"><span data-stu-id="0cf87-105">Each record in the table represents one user agent</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0cf87-106"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="0cf87-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="0cf87-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="0cf87-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="0cf87-108"><strong>主索引鍵 /</strong></span><span class="sxs-lookup"><span data-stu-id="0cf87-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="0cf87-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="0cf87-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0cf87-110"><strong>UserAgentKey</strong></span><span class="sxs-lookup"><span data-stu-id="0cf87-110"><strong>UserAgentKey</strong></span></span></p></td>
<td><p><span data-ttu-id="0cf87-111">int</span><span class="sxs-lookup"><span data-stu-id="0cf87-111">int</span></span></p></td>
<td><p><span data-ttu-id="0cf87-112">主要</span><span class="sxs-lookup"><span data-stu-id="0cf87-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="0cf87-113">用於識別此使用者代理程式的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="0cf87-113">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cf87-114"><strong>UserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="0cf87-114"><strong>UserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="0cf87-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0cf87-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0cf87-116">Unique</span><span class="sxs-lookup"><span data-stu-id="0cf87-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="0cf87-117">使用者代理字串。</span><span class="sxs-lookup"><span data-stu-id="0cf87-117">User Agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0cf87-118"><strong>UAType</strong></span><span class="sxs-lookup"><span data-stu-id="0cf87-118"><strong>UAType</strong></span></span></p></td>
<td><p><span data-ttu-id="0cf87-119">smallint</span><span class="sxs-lookup"><span data-stu-id="0cf87-119">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0cf87-120">1 是中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="0cf87-120">1 is Mediation Server.</span></span></p>
<p><span data-ttu-id="0cf87-121">2 是 A / V 會議伺服器。</span><span class="sxs-lookup"><span data-stu-id="0cf87-121">2 is A/V Conferencing Server.</span></span></p>
<p><span data-ttu-id="0cf87-122">4 是 Lync。</span><span class="sxs-lookup"><span data-stu-id="0cf87-122">4 is Lync.</span></span></p>
<p><span data-ttu-id="0cf87-123">8 是 IP 電話。</span><span class="sxs-lookup"><span data-stu-id="0cf87-123">8 is IP Phone.</span></span></p>
<p><span data-ttu-id="0cf87-124">16 是 Live Meeting 主控台。</span><span class="sxs-lookup"><span data-stu-id="0cf87-124">16 is Live Meeting Console.</span></span></p>
<p><span data-ttu-id="0cf87-125">32 是部署驗證工具 (DVT)。</span><span class="sxs-lookup"><span data-stu-id="0cf87-125">32 is Deployment Validation Tool (DVT).</span></span></p>
<p><span data-ttu-id="0cf87-126">64 是 Macintosh 電腦上的 Lync。</span><span class="sxs-lookup"><span data-stu-id="0cf87-126">64 is Lync on Macintosh computers.</span></span></p>
<p><span data-ttu-id="0cf87-127">128 是 Office Communications Server 2007 R2 語音應答。</span><span class="sxs-lookup"><span data-stu-id="0cf87-127">128 is Office Communications Server 2007 R2 Attendant.</span></span></p>
<p><span data-ttu-id="0cf87-128">256 是會議宣告服務。</span><span class="sxs-lookup"><span data-stu-id="0cf87-128">256 is Conferencing Announcement service.</span></span></p>
<p><span data-ttu-id="0cf87-129">512 是會議自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="0cf87-129">512 is Conferencing Auto Attendant.</span></span></p>
<p><span data-ttu-id="0cf87-130">1024 是回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="0cf87-130">1024 is Response Group application.</span></span></p>
<p><span data-ttu-id="0cf87-131">2048 是外部語音控制。</span><span class="sxs-lookup"><span data-stu-id="0cf87-131">2048 is Outside Voice Control.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

