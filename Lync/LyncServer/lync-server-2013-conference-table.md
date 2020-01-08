---
title: Lync Server 2013：Conference 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference table
ms:assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425762(v=OCS.15)
ms:contentKeyID: 48183700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f57f7baf017507da44677cc475c99d192fe868f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982434"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-table-in-lync-server-2013"></a><span data-ttu-id="ccc0c-102">Lync Server 2013 中的 Conference 表格</span><span class="sxs-lookup"><span data-stu-id="ccc0c-102">Conference table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ccc0c-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ccc0c-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ccc0c-104">[會議] 表格是支援表格。</span><span class="sxs-lookup"><span data-stu-id="ccc0c-104">The Conference table is a supporting table.</span></span> <span data-ttu-id="ccc0c-105">每個記錄代表一個會議或點對點工作階段。</span><span class="sxs-lookup"><span data-stu-id="ccc0c-105">Each record represents one conference or peer-to-peer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ccc0c-106"><strong>左欄</strong></span><span class="sxs-lookup"><span data-stu-id="ccc0c-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ccc0c-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="ccc0c-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ccc0c-108"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="ccc0c-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ccc0c-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="ccc0c-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ccc0c-110"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="ccc0c-110"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="ccc0c-111">int</span><span class="sxs-lookup"><span data-stu-id="ccc0c-111">int</span></span></p></td>
<td><p><span data-ttu-id="ccc0c-112">首選</span><span class="sxs-lookup"><span data-stu-id="ccc0c-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="ccc0c-113">標識此會議記錄的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="ccc0c-113">Unique number identifying this conference record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccc0c-114"><strong>ConfURI</strong></span><span class="sxs-lookup"><span data-stu-id="ccc0c-114"><strong>ConfURI</strong></span></span></p></td>
<td><p><span data-ttu-id="ccc0c-115">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="ccc0c-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ccc0c-116">唯一</span><span class="sxs-lookup"><span data-stu-id="ccc0c-116">unique</span></span></p></td>
<td><p><span data-ttu-id="ccc0c-117">會議 URI （如果這是會議），或 DialogID （如果這是點對點工作階段的話）。</span><span class="sxs-lookup"><span data-stu-id="ccc0c-117">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccc0c-118"><strong>求和</strong></span><span class="sxs-lookup"><span data-stu-id="ccc0c-118"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="ccc0c-119">int</span><span class="sxs-lookup"><span data-stu-id="ccc0c-119">int</span></span></p></td>
<td><p><span data-ttu-id="ccc0c-120">index</span><span class="sxs-lookup"><span data-stu-id="ccc0c-120">index</span></span></p></td>
<td><p><span data-ttu-id="ccc0c-121">會議 URI 的校驗和。</span><span class="sxs-lookup"><span data-stu-id="ccc0c-121">Checksum of the conference URI.</span></span> <span data-ttu-id="ccc0c-122">這會在內部使用。</span><span class="sxs-lookup"><span data-stu-id="ccc0c-122">This is used internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccc0c-123"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="ccc0c-123"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="ccc0c-124">datetime</span><span class="sxs-lookup"><span data-stu-id="ccc0c-124">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccc0c-125">僅供內部使用。</span><span class="sxs-lookup"><span data-stu-id="ccc0c-125">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

