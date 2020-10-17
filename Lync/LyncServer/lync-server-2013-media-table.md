---
title: Lync Server 2013： Media 表格
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
ms.openlocfilehash: 369e1ace7e0f3f9326896373a640597360ded81d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516170"
---
# <a name="media-table-in-lync-server-2013"></a><span data-ttu-id="2250f-102">Lync Server 2013 中的媒體表格</span><span class="sxs-lookup"><span data-stu-id="2250f-102">Media table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2250f-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="2250f-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="2250f-p101">每一項記錄都代表對等工作階段所用的一種媒體類型。若某階段工作使用了一種以上的媒體類型，則在表格中會呈現多個記錄。</span><span class="sxs-lookup"><span data-stu-id="2250f-p101">Each record represents one media type used in a peer-to-peer session. One session would be represented by multiple records in the table, if more than one media type is used.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2250f-p102">您不應使用媒體資料表來計算工作階段的媒體持續期間。此資料表包含工作階段中的媒體交換訊號詳細資料。媒體交換是由 INVITE 要求來執行，且 StartTime 會指出 INVITE 傳送出來的時間。邀請時間不一定表示媒體開始時間，因為只有在接受工作階段後，媒體才會開始。EndTime 通常是指此工作階段的結束時間。</span><span class="sxs-lookup"><span data-stu-id="2250f-p102">The Media table should not be used to calculate the media duration for a session. This table contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session. The EndTime usually means the end time of this session.</span></span>



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
<th><span data-ttu-id="2250f-110">欄</span><span class="sxs-lookup"><span data-stu-id="2250f-110">Column</span></span></th>
<th><span data-ttu-id="2250f-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="2250f-111">Data Type</span></span></th>
<th><span data-ttu-id="2250f-112">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="2250f-112">Key/Index</span></span></th>
<th><span data-ttu-id="2250f-113">詳細資料</span><span class="sxs-lookup"><span data-stu-id="2250f-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2250f-114"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="2250f-114"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2250f-115">datetime</span><span class="sxs-lookup"><span data-stu-id="2250f-115">datetime</span></span></p></td>
<td><p><span data-ttu-id="2250f-116">主要，外部</span><span class="sxs-lookup"><span data-stu-id="2250f-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2250f-117">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="2250f-117">Time of session request.</span></span> <span data-ttu-id="2250f-118">其會與 <strong>SessionIdSeq</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="2250f-118">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="2250f-119">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="2250f-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2250f-120"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="2250f-120"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2250f-121">int</span><span class="sxs-lookup"><span data-stu-id="2250f-121">int</span></span></p></td>
<td><p><span data-ttu-id="2250f-122">主要，外部</span><span class="sxs-lookup"><span data-stu-id="2250f-122">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2250f-123">用來識別工作階段的識別碼。</span><span class="sxs-lookup"><span data-stu-id="2250f-123">ID number to identify the session.</span></span> <span data-ttu-id="2250f-124">會與 <strong>SessionIdTime</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="2250f-124">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="2250f-125">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="2250f-125">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2250f-126"><strong>MediaId</strong></span><span class="sxs-lookup"><span data-stu-id="2250f-126"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="2250f-127">Tinyint</span><span class="sxs-lookup"><span data-stu-id="2250f-127">tinyint</span></span></p></td>
<td><p><span data-ttu-id="2250f-128">主要，外部</span><span class="sxs-lookup"><span data-stu-id="2250f-128">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2250f-129">用於識別此媒體類型的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="2250f-129">Unique number identifying this media type.</span></span> <span data-ttu-id="2250f-130">如需詳細資訊，請參閱 <a href="lync-server-2013-medialist-table.md">Lync Server 2013 中的 MediaList 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="2250f-130">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2250f-131"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="2250f-131"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2250f-132">datetime</span><span class="sxs-lookup"><span data-stu-id="2250f-132">datetime</span></span></p></td>
<td><p><span data-ttu-id="2250f-133">主要</span><span class="sxs-lookup"><span data-stu-id="2250f-133">Primary</span></span></p></td>
<td><p><span data-ttu-id="2250f-p106">這是媒體要求傳送出來的時間，而不是實際的媒體開始時間。<strong>StartTime</strong> 會指出工作階段開始時間。</span><span class="sxs-lookup"><span data-stu-id="2250f-p106">This is the time that a media request was sent out, not the real media start time. <strong>StartTime</strong> includes the session setup time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2250f-136"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="2250f-136"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2250f-137">datetime</span><span class="sxs-lookup"><span data-stu-id="2250f-137">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2250f-138">這是工作階段結束時間。</span><span class="sxs-lookup"><span data-stu-id="2250f-138">This is the end time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

