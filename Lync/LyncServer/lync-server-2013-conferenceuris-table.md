---
title: Lync Server 2013： ConferenceUris 表格
description: Lync Server 2013： ConferenceUris 表格。
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
ms.openlocfilehash: a142aa9ad1fe4d3ae92aa3e21aa9eee505457cbe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566739"
---
# <a name="conferenceuris-table-in-lync-server-2013"></a><span data-ttu-id="c9177-103">Lync Server 2013 中的 ConferenceUris 表格</span><span class="sxs-lookup"><span data-stu-id="c9177-103">ConferenceUris table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9177-104">_**主題上次修改日期：** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="c9177-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="c9177-105">ConfereneUris 表格是一種支援表格，可儲存參與于資料庫中的會議會話的各個會議 URIs 清單。</span><span class="sxs-lookup"><span data-stu-id="c9177-105">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="c9177-106">表格中的每一筆記錄都代表一個會議 URI。</span><span class="sxs-lookup"><span data-stu-id="c9177-106">Each record in the table represents one conference URI.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c9177-107">欄</span><span class="sxs-lookup"><span data-stu-id="c9177-107">Column</span></span></th>
<th><span data-ttu-id="c9177-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="c9177-108">Data Type</span></span></th>
<th><span data-ttu-id="c9177-109">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="c9177-109">Key/Index</span></span></th>
<th><span data-ttu-id="c9177-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="c9177-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9177-111"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="c9177-111"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="c9177-112">datetime</span><span class="sxs-lookup"><span data-stu-id="c9177-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="c9177-113">主要</span><span class="sxs-lookup"><span data-stu-id="c9177-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="c9177-114">時間戳記，內部使用。</span><span class="sxs-lookup"><span data-stu-id="c9177-114">Time stamp, Internal used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9177-115"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="c9177-115"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="c9177-116">int</span><span class="sxs-lookup"><span data-stu-id="c9177-116">int</span></span></p></td>
<td><p><span data-ttu-id="c9177-117">主要</span><span class="sxs-lookup"><span data-stu-id="c9177-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="c9177-118">用於識別此會議 URI 的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="c9177-118">Unique number identifying this conference URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9177-119"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="c9177-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="c9177-120">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="c9177-120">nvarchar(450)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9177-121">會議 URI。</span><span class="sxs-lookup"><span data-stu-id="c9177-121">Conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9177-122"><strong>校驗</strong></span><span class="sxs-lookup"><span data-stu-id="c9177-122"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="c9177-123">int</span><span class="sxs-lookup"><span data-stu-id="c9177-123">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c9177-124">ConferenceUri 的檢驗。</span><span class="sxs-lookup"><span data-stu-id="c9177-124">Checksum of ConferenceUri.</span></span> <span data-ttu-id="c9177-125">用於增加資料庫搜尋的速度。</span><span class="sxs-lookup"><span data-stu-id="c9177-125">Used to increases the speed of database searches.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9177-126"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="c9177-126"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="c9177-127">int</span><span class="sxs-lookup"><span data-stu-id="c9177-127">int</span></span></p></td>
<td><p><span data-ttu-id="c9177-128">Foreign</span><span class="sxs-lookup"><span data-stu-id="c9177-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c9177-129">URI 類型，例如會議：適用于 IM 會議或會議：音訊/視訊會議的音訊-影片。</span><span class="sxs-lookup"><span data-stu-id="c9177-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="c9177-130">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 表格中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="c9177-130">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> table for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

