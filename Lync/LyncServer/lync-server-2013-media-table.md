---
title: Lync Server 2013：媒體資料表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media table
ms:assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398268(v=OCS.15)
ms:contentKeyID: 48183568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da8b3aaff56e782307f3146fdcee7d4410340198
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-table-in-lync-server-2013"></a><span data-ttu-id="fef1c-102">Lync Server 2013 中的媒體資料表格</span><span class="sxs-lookup"><span data-stu-id="fef1c-102">Media table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fef1c-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="fef1c-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="fef1c-104">每個記錄代表點對點工作階段中所使用的一種媒體類型。</span><span class="sxs-lookup"><span data-stu-id="fef1c-104">Each record represents one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="fef1c-105">如果使用一個以上的媒體類型，則資料表中的多筆記錄會代表一個會話。</span><span class="sxs-lookup"><span data-stu-id="fef1c-105">One session would be represented by multiple records in the table, if more than one media type is used.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fef1c-106">媒體資料表不應該用來計算會話的媒體持續時間。</span><span class="sxs-lookup"><span data-stu-id="fef1c-106">The Media table should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="fef1c-107">此表格包含會話中媒體交換的信號詳細資料。</span><span class="sxs-lookup"><span data-stu-id="fef1c-107">This table contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="fef1c-108">媒體交換是由邀請要求所完成，而 StartTime 則會指出邀請的傳送時間。邀請時間不一定代表媒體開始時間，因為媒體只有在 sessionee 接受會話之後才會啟動。</span><span class="sxs-lookup"><span data-stu-id="fef1c-108">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session.</span></span> <span data-ttu-id="fef1c-109">[EndTime] 通常代表這個會話的結束時間。</span><span class="sxs-lookup"><span data-stu-id="fef1c-109">The EndTime usually means the end time of this session.</span></span>



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
<th><span data-ttu-id="fef1c-110">左欄</span><span class="sxs-lookup"><span data-stu-id="fef1c-110">Column</span></span></th>
<th><span data-ttu-id="fef1c-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="fef1c-111">Data Type</span></span></th>
<th><span data-ttu-id="fef1c-112">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="fef1c-112">Key/Index</span></span></th>
<th><span data-ttu-id="fef1c-113">詳細資料</span><span class="sxs-lookup"><span data-stu-id="fef1c-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fef1c-114"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="fef1c-114"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fef1c-115">datetime</span><span class="sxs-lookup"><span data-stu-id="fef1c-115">datetime</span></span></p></td>
<td><p><span data-ttu-id="fef1c-116">主要、外部</span><span class="sxs-lookup"><span data-stu-id="fef1c-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="fef1c-117">會話要求的時間。</span><span class="sxs-lookup"><span data-stu-id="fef1c-117">Time of session request.</span></span> <span data-ttu-id="fef1c-118">與<strong>SessionIdSeq</strong>搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="fef1c-118">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="fef1c-119">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="fef1c-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fef1c-120"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="fef1c-120"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fef1c-121">int</span><span class="sxs-lookup"><span data-stu-id="fef1c-121">int</span></span></p></td>
<td><p><span data-ttu-id="fef1c-122">主要、外部</span><span class="sxs-lookup"><span data-stu-id="fef1c-122">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="fef1c-123">識別會話的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="fef1c-123">ID number to identify the session.</span></span> <span data-ttu-id="fef1c-124">與<strong>SessionIdTime</strong>搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="fef1c-124">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="fef1c-125">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="fef1c-125">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fef1c-126"><strong>MediaId</strong></span><span class="sxs-lookup"><span data-stu-id="fef1c-126"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="fef1c-127">Tinyint</span><span class="sxs-lookup"><span data-stu-id="fef1c-127">tinyint</span></span></p></td>
<td><p><span data-ttu-id="fef1c-128">主要、外部</span><span class="sxs-lookup"><span data-stu-id="fef1c-128">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="fef1c-129">識別這個媒體類型的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="fef1c-129">Unique number identifying this media type.</span></span> <span data-ttu-id="fef1c-130">如需詳細資訊，請參閱<a href="lync-server-2013-medialist-table.md">Lync Server 2013 中</a>的 [MediaList] 資料表。</span><span class="sxs-lookup"><span data-stu-id="fef1c-130">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fef1c-131"><strong>開始</strong></span><span class="sxs-lookup"><span data-stu-id="fef1c-131"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fef1c-132">datetime</span><span class="sxs-lookup"><span data-stu-id="fef1c-132">datetime</span></span></p></td>
<td><p><span data-ttu-id="fef1c-133">首選</span><span class="sxs-lookup"><span data-stu-id="fef1c-133">Primary</span></span></p></td>
<td><p><span data-ttu-id="fef1c-134">這是傳送媒體要求的時間，而不是真正的媒體啟動時間。</span><span class="sxs-lookup"><span data-stu-id="fef1c-134">This is the time that a media request was sent out, not the real media start time.</span></span> <span data-ttu-id="fef1c-135"><strong>StartTime</strong>包含會話設定時間。</span><span class="sxs-lookup"><span data-stu-id="fef1c-135"><strong>StartTime</strong> includes the session setup time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fef1c-136"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="fef1c-136"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fef1c-137">datetime</span><span class="sxs-lookup"><span data-stu-id="fef1c-137">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fef1c-138">這是會話的結束時間。</span><span class="sxs-lookup"><span data-stu-id="fef1c-138">This is the end time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

