---
title: Lync Server 2013：ConferenceUris 表格
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
ms.openlocfilehash: 3cacbaf4e8c7c826ae2e00e9c86b44cc8387f315
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferenceuris-table-in-lync-server-2013"></a><span data-ttu-id="79ea1-102">Lync Server 2013 中的 ConferenceUris 表格</span><span class="sxs-lookup"><span data-stu-id="79ea1-102">ConferenceUris table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79ea1-103">_**主題上次修改日期：** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="79ea1-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="79ea1-104">ConfereneUris 資料表是一個支援資料表，可儲存已參與在資料庫中的會議會話的各種會議 Uri 清單。</span><span class="sxs-lookup"><span data-stu-id="79ea1-104">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="79ea1-105">資料表中的每一筆記錄代表一個會議 URI。</span><span class="sxs-lookup"><span data-stu-id="79ea1-105">Each record in the table represents one conference URI.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79ea1-106">左欄</span><span class="sxs-lookup"><span data-stu-id="79ea1-106">Column</span></span></th>
<th><span data-ttu-id="79ea1-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="79ea1-107">Data Type</span></span></th>
<th><span data-ttu-id="79ea1-108">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="79ea1-108">Key/Index</span></span></th>
<th><span data-ttu-id="79ea1-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="79ea1-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79ea1-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="79ea1-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="79ea1-111">datetime</span><span class="sxs-lookup"><span data-stu-id="79ea1-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="79ea1-112">首選</span><span class="sxs-lookup"><span data-stu-id="79ea1-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="79ea1-113">時間戳記，內部使用。</span><span class="sxs-lookup"><span data-stu-id="79ea1-113">Time stamp, Internal used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79ea1-114"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="79ea1-114"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="79ea1-115">int</span><span class="sxs-lookup"><span data-stu-id="79ea1-115">int</span></span></p></td>
<td><p><span data-ttu-id="79ea1-116">首選</span><span class="sxs-lookup"><span data-stu-id="79ea1-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="79ea1-117">標識此會議 URI 的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="79ea1-117">Unique number identifying this conference URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79ea1-118"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="79ea1-118"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="79ea1-119">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="79ea1-119">nvarchar(450)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="79ea1-120">會議 URI。</span><span class="sxs-lookup"><span data-stu-id="79ea1-120">Conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79ea1-121"><strong>求和</strong></span><span class="sxs-lookup"><span data-stu-id="79ea1-121"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="79ea1-122">int</span><span class="sxs-lookup"><span data-stu-id="79ea1-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="79ea1-123">ConferenceUri 的校驗和。</span><span class="sxs-lookup"><span data-stu-id="79ea1-123">Checksum of ConferenceUri.</span></span> <span data-ttu-id="79ea1-124">用來提高資料庫搜尋的速度。</span><span class="sxs-lookup"><span data-stu-id="79ea1-124">Used to increases the speed of database searches.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79ea1-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="79ea1-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="79ea1-126">int</span><span class="sxs-lookup"><span data-stu-id="79ea1-126">int</span></span></p></td>
<td><p><span data-ttu-id="79ea1-127">外</span><span class="sxs-lookup"><span data-stu-id="79ea1-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="79ea1-128">URI 類型，例如會議： IM 會議的聊天或會議：音訊/視訊會議的音訊-視頻。</span><span class="sxs-lookup"><span data-stu-id="79ea1-128">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="79ea1-129">如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 資料表中</a>的 [UriTypes] 資料表。</span><span class="sxs-lookup"><span data-stu-id="79ea1-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> table for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

