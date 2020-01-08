---
title: Lync Server 2013：AppliedBandwidthSource 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AppliedBandwidthSource table
ms:assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425725(v=OCS.15)
ms:contentKeyID: 48183638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f4c7d78353a60ad4c3bf9a7ff3efb363bd01c82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977236"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appliedbandwidthsource-table-in-lync-server-2013"></a><span data-ttu-id="87ec9-102">Lync Server 2013 中的 AppliedBandwidthSource 表格</span><span class="sxs-lookup"><span data-stu-id="87ec9-102">AppliedBandwidthSource table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87ec9-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="87ec9-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="87ec9-104">AppliedBandwidthSource 資料表是支援資料表。</span><span class="sxs-lookup"><span data-stu-id="87ec9-104">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="87ec9-105">每個記錄代表一個來源。</span><span class="sxs-lookup"><span data-stu-id="87ec9-105">Each record represents one source.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87ec9-106"><strong>左欄</strong></span><span class="sxs-lookup"><span data-stu-id="87ec9-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="87ec9-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="87ec9-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="87ec9-108"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="87ec9-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="87ec9-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="87ec9-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87ec9-110"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="87ec9-110"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="87ec9-111">int</span><span class="sxs-lookup"><span data-stu-id="87ec9-111">int</span></span></p></td>
<td><p><span data-ttu-id="87ec9-112">首選</span><span class="sxs-lookup"><span data-stu-id="87ec9-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="87ec9-113">標識來源的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="87ec9-113">Unique number identifying the source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87ec9-114"><strong>AppliedBandwidthSource</strong></span><span class="sxs-lookup"><span data-stu-id="87ec9-114"><strong>AppliedBandwidthSource</strong></span></span></p></td>
<td><p><span data-ttu-id="87ec9-115">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="87ec9-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="87ec9-116">唯一</span><span class="sxs-lookup"><span data-stu-id="87ec9-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="87ec9-117">這是強加頻寬上限的來源。</span><span class="sxs-lookup"><span data-stu-id="87ec9-117">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="87ec9-118">它描述頻寬限制的來源（例如，「原則伺服器」、「轉換伺服器」或「模態」）。</span><span class="sxs-lookup"><span data-stu-id="87ec9-118">It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

