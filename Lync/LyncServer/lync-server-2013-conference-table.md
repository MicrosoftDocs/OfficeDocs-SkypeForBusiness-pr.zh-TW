---
title: Lync Server 2013：會議表格
description: Lync Server 2013：會議表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference table
ms:assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425762(v=OCS.15)
ms:contentKeyID: 48183700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 565725b527399cb3be55c649dfd74d8bcb5f13a2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550659"
---
# <a name="conference-table-in-lync-server-2013"></a><span data-ttu-id="0cd87-103">Lync Server 2013 中的會議表格</span><span class="sxs-lookup"><span data-stu-id="0cd87-103">Conference table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0cd87-104">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="0cd87-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="0cd87-p101">會議表格是一種支援資料表，其中的每一項記錄都代表一個會議或對等工作階段。</span><span class="sxs-lookup"><span data-stu-id="0cd87-p101">The Conference table is a supporting table. Each record represents one conference or peer-to-peer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0cd87-107"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="0cd87-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="0cd87-108"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="0cd87-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="0cd87-109"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="0cd87-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="0cd87-110"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="0cd87-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0cd87-111"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="0cd87-111"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="0cd87-112">int</span><span class="sxs-lookup"><span data-stu-id="0cd87-112">int</span></span></p></td>
<td><p><span data-ttu-id="0cd87-113">主要</span><span class="sxs-lookup"><span data-stu-id="0cd87-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="0cd87-114">用於識別此會議記錄的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="0cd87-114">Unique number identifying this conference record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cd87-115"><strong>ConfURI</strong></span><span class="sxs-lookup"><span data-stu-id="0cd87-115"><strong>ConfURI</strong></span></span></p></td>
<td><p><span data-ttu-id="0cd87-116">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="0cd87-116">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="0cd87-117">unique</span><span class="sxs-lookup"><span data-stu-id="0cd87-117">unique</span></span></p></td>
<td><p><span data-ttu-id="0cd87-118">會議 URI (若為會議)，或 DialogID (若為點對點工作階段)。</span><span class="sxs-lookup"><span data-stu-id="0cd87-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0cd87-119"><strong>校驗</strong></span><span class="sxs-lookup"><span data-stu-id="0cd87-119"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="0cd87-120">int</span><span class="sxs-lookup"><span data-stu-id="0cd87-120">int</span></span></p></td>
<td><p><span data-ttu-id="0cd87-121">index</span><span class="sxs-lookup"><span data-stu-id="0cd87-121">index</span></span></p></td>
<td><p><span data-ttu-id="0cd87-p102">會議 URI 的總和檢查碼。僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="0cd87-p102">Checksum of the conference URI. This is used internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cd87-124"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="0cd87-124"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="0cd87-125">datetime</span><span class="sxs-lookup"><span data-stu-id="0cd87-125">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0cd87-126">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="0cd87-126">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

