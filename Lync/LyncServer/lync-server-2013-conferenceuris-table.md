---
title: 'Lync Server 2013: ConferenceUris 表格'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceUris table
ms:assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412854(v=OCS.15)
ms:contentKeyID: 48185160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4310c90bdf3381bf9a5b357d6b45c9252ab7136b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferenceuris-table-in-lync-server-2013"></a><span data-ttu-id="cd49b-102">Lync Server 2013 中的 ConferenceUris 表格</span><span class="sxs-lookup"><span data-stu-id="cd49b-102">ConferenceUris table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd49b-103">_**主題上次修改日期：** 2012年-05-25_</span><span class="sxs-lookup"><span data-stu-id="cd49b-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="cd49b-104">ConfereneUris 表格是一種支援資料表儲存各種會議記錄資料庫中的會議工作階段的 Uri 的清單。</span><span class="sxs-lookup"><span data-stu-id="cd49b-104">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="cd49b-105">在資料表中的每一筆記錄代表一個會議 URI。</span><span class="sxs-lookup"><span data-stu-id="cd49b-105">Each record in the table represents one conference URI.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cd49b-106">欄</span><span class="sxs-lookup"><span data-stu-id="cd49b-106">Column</span></span></th>
<th><span data-ttu-id="cd49b-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="cd49b-107">Data Type</span></span></th>
<th><span data-ttu-id="cd49b-108">主索引鍵 /</span><span class="sxs-lookup"><span data-stu-id="cd49b-108">Key/Index</span></span></th>
<th><span data-ttu-id="cd49b-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="cd49b-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cd49b-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="cd49b-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="cd49b-111">datetime</span><span class="sxs-lookup"><span data-stu-id="cd49b-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="cd49b-112">主要</span><span class="sxs-lookup"><span data-stu-id="cd49b-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="cd49b-113">時間戳記，供內部使用。</span><span class="sxs-lookup"><span data-stu-id="cd49b-113">Time stamp, Internal used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd49b-114"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="cd49b-114"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="cd49b-115">int</span><span class="sxs-lookup"><span data-stu-id="cd49b-115">int</span></span></p></td>
<td><p><span data-ttu-id="cd49b-116">主要</span><span class="sxs-lookup"><span data-stu-id="cd49b-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="cd49b-117">用於識別此會議 URI 的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="cd49b-117">Unique number identifying this conference URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd49b-118"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="cd49b-118"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="cd49b-119">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="cd49b-119">nvarchar(450)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cd49b-120">會議 URI。</span><span class="sxs-lookup"><span data-stu-id="cd49b-120">Conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd49b-121"><strong>總和檢查碼</strong></span><span class="sxs-lookup"><span data-stu-id="cd49b-121"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="cd49b-122">int</span><span class="sxs-lookup"><span data-stu-id="cd49b-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cd49b-123">ConferenceUri 總和檢查碼。</span><span class="sxs-lookup"><span data-stu-id="cd49b-123">Checksum of ConferenceUri.</span></span> <span data-ttu-id="cd49b-124">用來增加資料庫搜尋的速度。</span><span class="sxs-lookup"><span data-stu-id="cd49b-124">Used to increases the speed of database searches.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd49b-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="cd49b-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="cd49b-126">int</span><span class="sxs-lookup"><span data-stu-id="cd49b-126">int</span></span></p></td>
<td><p><span data-ttu-id="cd49b-127">Foreign</span><span class="sxs-lookup"><span data-stu-id="cd49b-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cd49b-128">URI 類型，例如 IM 會議，或 conf:audio conf:chat-視訊的音訊/視訊會議。</span><span class="sxs-lookup"><span data-stu-id="cd49b-128">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="cd49b-129">請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a>表如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="cd49b-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> table for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

