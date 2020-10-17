---
title: Lync Server 2013： Media 表格
description: Lync Server 2013： Media 表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media table
ms:assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398268(v=OCS.15)
ms:contentKeyID: 48183568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31e30d1f91c59b8e3aa7915fc0d513618d0f709f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558029"
---
# <a name="media-table-in-lync-server-2013"></a><span data-ttu-id="e7ad6-103">Lync Server 2013 中的媒體表格</span><span class="sxs-lookup"><span data-stu-id="e7ad6-103">Media table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7ad6-104">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="e7ad6-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="e7ad6-p101">每一項記錄都代表對等工作階段所用的一種媒體類型。若某階段工作使用了一種以上的媒體類型，則在表格中會呈現多個記錄。</span><span class="sxs-lookup"><span data-stu-id="e7ad6-p101">Each record represents one media type used in a peer-to-peer session. One session would be represented by multiple records in the table, if more than one media type is used.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e7ad6-p102">您不應使用媒體資料表來計算工作階段的媒體持續期間。此資料表包含工作階段中的媒體交換訊號詳細資料。媒體交換是由 INVITE 要求來執行，且 StartTime 會指出 INVITE 傳送出來的時間。邀請時間不一定表示媒體開始時間，因為只有在接受工作階段後，媒體才會開始。EndTime 通常是指此工作階段的結束時間。</span><span class="sxs-lookup"><span data-stu-id="e7ad6-p102">The Media table should not be used to calculate the media duration for a session. This table contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session. The EndTime usually means the end time of this session.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e7ad6-111">欄</span><span class="sxs-lookup"><span data-stu-id="e7ad6-111">Column</span></span></th>
<th><span data-ttu-id="e7ad6-112">資料類型</span><span class="sxs-lookup"><span data-stu-id="e7ad6-112">Data Type</span></span></th>
<th><span data-ttu-id="e7ad6-113">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="e7ad6-113">Key/Index</span></span></th>
<th><span data-ttu-id="e7ad6-114">詳細資料</span><span class="sxs-lookup"><span data-stu-id="e7ad6-114">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e7ad6-115"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e7ad6-115"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e7ad6-116">datetime</span><span class="sxs-lookup"><span data-stu-id="e7ad6-116">datetime</span></span></p></td>
<td><p><span data-ttu-id="e7ad6-117">主要，外部</span><span class="sxs-lookup"><span data-stu-id="e7ad6-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e7ad6-118">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="e7ad6-118">Time of session request.</span></span> <span data-ttu-id="e7ad6-119">其會與 <strong>SessionIdSeq</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="e7ad6-119">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="e7ad6-120">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="e7ad6-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7ad6-121"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e7ad6-121"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e7ad6-122">int</span><span class="sxs-lookup"><span data-stu-id="e7ad6-122">int</span></span></p></td>
<td><p><span data-ttu-id="e7ad6-123">主要，外部</span><span class="sxs-lookup"><span data-stu-id="e7ad6-123">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e7ad6-124">用來識別工作階段的識別碼。</span><span class="sxs-lookup"><span data-stu-id="e7ad6-124">ID number to identify the session.</span></span> <span data-ttu-id="e7ad6-125">會與 <strong>SessionIdTime</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="e7ad6-125">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="e7ad6-126">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="e7ad6-126">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7ad6-127"><strong>MediaId</strong></span><span class="sxs-lookup"><span data-stu-id="e7ad6-127"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="e7ad6-128">Tinyint</span><span class="sxs-lookup"><span data-stu-id="e7ad6-128">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e7ad6-129">主要，外部</span><span class="sxs-lookup"><span data-stu-id="e7ad6-129">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e7ad6-130">用於識別此媒體類型的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="e7ad6-130">Unique number identifying this media type.</span></span> <span data-ttu-id="e7ad6-131">如需詳細資訊，請參閱 <a href="lync-server-2013-medialist-table.md">Lync Server 2013 中的 MediaList 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="e7ad6-131">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7ad6-132"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="e7ad6-132"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e7ad6-133">datetime</span><span class="sxs-lookup"><span data-stu-id="e7ad6-133">datetime</span></span></p></td>
<td><p><span data-ttu-id="e7ad6-134">主要</span><span class="sxs-lookup"><span data-stu-id="e7ad6-134">Primary</span></span></p></td>
<td><p><span data-ttu-id="e7ad6-p106">這是媒體要求傳送出來的時間，而不是實際的媒體開始時間。<strong>StartTime</strong> 會指出工作階段開始時間。</span><span class="sxs-lookup"><span data-stu-id="e7ad6-p106">This is the time that a media request was sent out, not the real media start time. <strong>StartTime</strong> includes the session setup time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7ad6-137"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="e7ad6-137"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e7ad6-138">datetime</span><span class="sxs-lookup"><span data-stu-id="e7ad6-138">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e7ad6-139">這是工作階段結束時間。</span><span class="sxs-lookup"><span data-stu-id="e7ad6-139">This is the end time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

