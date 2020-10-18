---
title: Lync Server 2013： SessionCorrelation 表格
description: Lync Server 2013： SessionCorrelation 表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionCorrelation table
ms:assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398091(v=OCS.15)
ms:contentKeyID: 48183267
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 814b7e8539d89f87e7df60ceb03e70800553fb55
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579659"
---
# <a name="sessioncorrelation-table-in-lync-server-2013"></a><span data-ttu-id="a5497-103">Lync Server 2013 中的 SessionCorrelation 表格</span><span class="sxs-lookup"><span data-stu-id="a5497-103">SessionCorrelation table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5497-104">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="a5497-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="a5497-105">SessionCorrelation 表格是支援的表格。</span><span class="sxs-lookup"><span data-stu-id="a5497-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="a5497-106">每筆記錄代表一個用於關聯多個會話的 CorrelationID。</span><span class="sxs-lookup"><span data-stu-id="a5497-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a5497-107"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="a5497-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="a5497-108"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="a5497-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="a5497-109"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="a5497-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="a5497-110"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="a5497-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5497-111"><strong>校驗</strong></span><span class="sxs-lookup"><span data-stu-id="a5497-111"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="a5497-112">int</span><span class="sxs-lookup"><span data-stu-id="a5497-112">int</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5497-113"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="a5497-113"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="a5497-114">int</span><span class="sxs-lookup"><span data-stu-id="a5497-114">int</span></span></p></td>
<td><p><span data-ttu-id="a5497-115">主要</span><span class="sxs-lookup"><span data-stu-id="a5497-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="a5497-116">用於識別此 A/V 會議伺服器的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="a5497-116">Unique number identifying this A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5497-117"><strong>CorrelationID</strong></span><span class="sxs-lookup"><span data-stu-id="a5497-117"><strong>CorrelationID</strong></span></span></p></td>
<td><p><span data-ttu-id="a5497-118">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="a5497-118">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a5497-119">Unique</span><span class="sxs-lookup"><span data-stu-id="a5497-119">Unique</span></span></p></td>
<td><p><span data-ttu-id="a5497-120">關聯的會話會有相同的相互關聯識別碼。</span><span class="sxs-lookup"><span data-stu-id="a5497-120">Sessions that are correlated will have the same correlation ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5497-121"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="a5497-121"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="a5497-122">datetime</span><span class="sxs-lookup"><span data-stu-id="a5497-122">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a5497-123">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="a5497-123">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

