---
title: Lync Server 2013： AppliedBandwidthSource 表格
description: Lync Server 2013： AppliedBandwidthSource 表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppliedBandwidthSource table
ms:assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425725(v=OCS.15)
ms:contentKeyID: 48183638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dc22d3a978a99cb13317e2a32fdb65382ce106c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573499"
---
# <a name="appliedbandwidthsource-table-in-lync-server-2013"></a><span data-ttu-id="abeef-103">Lync Server 2013 中的 AppliedBandwidthSource 表格</span><span class="sxs-lookup"><span data-stu-id="abeef-103">AppliedBandwidthSource table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abeef-104">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="abeef-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="abeef-p101">AppliedBandwidthSource 表格是一種支援資料表，其中的每一項記錄都代表一種來源。</span><span class="sxs-lookup"><span data-stu-id="abeef-p101">The AppliedBandwidthSource table is a supporting table. Each record represents one source.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="abeef-107"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="abeef-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="abeef-108"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="abeef-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="abeef-109"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="abeef-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="abeef-110"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="abeef-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="abeef-111"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="abeef-111"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="abeef-112">int</span><span class="sxs-lookup"><span data-stu-id="abeef-112">int</span></span></p></td>
<td><p><span data-ttu-id="abeef-113">主要</span><span class="sxs-lookup"><span data-stu-id="abeef-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="abeef-114">用於識別來源的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="abeef-114">Unique number identifying the source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abeef-115"><strong>AppliedBandwidthSource</strong></span><span class="sxs-lookup"><span data-stu-id="abeef-115"><strong>AppliedBandwidthSource</strong></span></span></p></td>
<td><p><span data-ttu-id="abeef-116">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="abeef-116">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="abeef-117">Unique</span><span class="sxs-lookup"><span data-stu-id="abeef-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="abeef-p102">這是所採用的頻寬容量來源。其會說明頻寬限制的來源 (例如，「原則伺服器」、「TURN 伺服器」或「形式」)。</span><span class="sxs-lookup"><span data-stu-id="abeef-p102">This is the source of the bandwidth cap being imposed. It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

