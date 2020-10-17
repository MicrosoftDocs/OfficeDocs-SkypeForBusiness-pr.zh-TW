---
title: Lync Server 2013： ConferenceUris 表格
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
ms.openlocfilehash: e9142be1b2d46a7d7634394970d07dfa450a22e1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529170"
---
# <a name="conferenceuris-table-in-lync-server-2013"></a><span data-ttu-id="43c58-102">Lync Server 2013 中的 ConferenceUris 表格</span><span class="sxs-lookup"><span data-stu-id="43c58-102">ConferenceUris table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43c58-103">_**主題上次修改日期：** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="43c58-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="43c58-104">ConfereneUris 表格是一種支援表格，可儲存參與于資料庫中的會議會話的各個會議 URIs 清單。</span><span class="sxs-lookup"><span data-stu-id="43c58-104">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="43c58-105">表格中的每一筆記錄都代表一個會議 URI。</span><span class="sxs-lookup"><span data-stu-id="43c58-105">Each record in the table represents one conference URI.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43c58-106">欄</span><span class="sxs-lookup"><span data-stu-id="43c58-106">Column</span></span></th>
<th><span data-ttu-id="43c58-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="43c58-107">Data Type</span></span></th>
<th><span data-ttu-id="43c58-108">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="43c58-108">Key/Index</span></span></th>
<th><span data-ttu-id="43c58-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="43c58-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43c58-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="43c58-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="43c58-111">datetime</span><span class="sxs-lookup"><span data-stu-id="43c58-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="43c58-112">主要</span><span class="sxs-lookup"><span data-stu-id="43c58-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="43c58-113">時間戳記，內部使用。</span><span class="sxs-lookup"><span data-stu-id="43c58-113">Time stamp, Internal used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43c58-114"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="43c58-114"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="43c58-115">int</span><span class="sxs-lookup"><span data-stu-id="43c58-115">int</span></span></p></td>
<td><p><span data-ttu-id="43c58-116">主要</span><span class="sxs-lookup"><span data-stu-id="43c58-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="43c58-117">用於識別此會議 URI 的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="43c58-117">Unique number identifying this conference URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43c58-118"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="43c58-118"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="43c58-119">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="43c58-119">nvarchar(450)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="43c58-120">會議 URI。</span><span class="sxs-lookup"><span data-stu-id="43c58-120">Conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43c58-121"><strong>校驗</strong></span><span class="sxs-lookup"><span data-stu-id="43c58-121"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="43c58-122">int</span><span class="sxs-lookup"><span data-stu-id="43c58-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="43c58-123">ConferenceUri 的檢驗。</span><span class="sxs-lookup"><span data-stu-id="43c58-123">Checksum of ConferenceUri.</span></span> <span data-ttu-id="43c58-124">用於增加資料庫搜尋的速度。</span><span class="sxs-lookup"><span data-stu-id="43c58-124">Used to increases the speed of database searches.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43c58-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="43c58-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="43c58-126">int</span><span class="sxs-lookup"><span data-stu-id="43c58-126">int</span></span></p></td>
<td><p><span data-ttu-id="43c58-127">Foreign</span><span class="sxs-lookup"><span data-stu-id="43c58-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="43c58-128">URI 類型，例如會議：適用于 IM 會議或會議：音訊/視訊會議的音訊-影片。</span><span class="sxs-lookup"><span data-stu-id="43c58-128">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="43c58-129">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 表格中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="43c58-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> table for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

