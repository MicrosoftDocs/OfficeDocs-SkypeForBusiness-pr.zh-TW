---
title: Lync Server 2013：Conference 表格
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
ms.openlocfilehash: 4941dc3ef59630cd77cfb0f8a51407d15ca628f7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756977"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-table-in-lync-server-2013"></a><span data-ttu-id="bbfca-102">Lync Server 2013 中的 Conference 表格</span><span class="sxs-lookup"><span data-stu-id="bbfca-102">Conference table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bbfca-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="bbfca-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="bbfca-104">[會議] 表格是支援表格。</span><span class="sxs-lookup"><span data-stu-id="bbfca-104">The Conference table is a supporting table.</span></span> <span data-ttu-id="bbfca-105">每個記錄代表一個會議或點對點工作階段。</span><span class="sxs-lookup"><span data-stu-id="bbfca-105">Each record represents one conference or peer-to-peer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bbfca-106"><strong>左欄</strong></span><span class="sxs-lookup"><span data-stu-id="bbfca-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="bbfca-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="bbfca-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="bbfca-108"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="bbfca-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="bbfca-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="bbfca-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bbfca-110"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="bbfca-110"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="bbfca-111">int</span><span class="sxs-lookup"><span data-stu-id="bbfca-111">int</span></span></p></td>
<td><p><span data-ttu-id="bbfca-112">首選</span><span class="sxs-lookup"><span data-stu-id="bbfca-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="bbfca-113">標識此會議記錄的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="bbfca-113">Unique number identifying this conference record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bbfca-114"><strong>ConfURI</strong></span><span class="sxs-lookup"><span data-stu-id="bbfca-114"><strong>ConfURI</strong></span></span></p></td>
<td><p><span data-ttu-id="bbfca-115">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="bbfca-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="bbfca-116">唯一</span><span class="sxs-lookup"><span data-stu-id="bbfca-116">unique</span></span></p></td>
<td><p><span data-ttu-id="bbfca-117">會議 URI （如果這是會議），或 DialogID （如果這是點對點工作階段的話）。</span><span class="sxs-lookup"><span data-stu-id="bbfca-117">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bbfca-118"><strong>求和</strong></span><span class="sxs-lookup"><span data-stu-id="bbfca-118"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="bbfca-119">int</span><span class="sxs-lookup"><span data-stu-id="bbfca-119">int</span></span></p></td>
<td><p><span data-ttu-id="bbfca-120">index</span><span class="sxs-lookup"><span data-stu-id="bbfca-120">index</span></span></p></td>
<td><p><span data-ttu-id="bbfca-121">會議 URI 的校驗和。</span><span class="sxs-lookup"><span data-stu-id="bbfca-121">Checksum of the conference URI.</span></span> <span data-ttu-id="bbfca-122">這會在內部使用。</span><span class="sxs-lookup"><span data-stu-id="bbfca-122">This is used internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bbfca-123"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="bbfca-123"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="bbfca-124">datetime</span><span class="sxs-lookup"><span data-stu-id="bbfca-124">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bbfca-125">僅供內部使用。</span><span class="sxs-lookup"><span data-stu-id="bbfca-125">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

