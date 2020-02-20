---
title: 'Lync Server 2013: AppliedBandwidthSource 表格'
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
ms.openlocfilehash: f251f507a11c2254487a99d6e6ea217e8918fe4d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147136"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="appliedbandwidthsource-table-in-lync-server-2013"></a><span data-ttu-id="78664-102">Lync Server 2013 中的 AppliedBandwidthSource 表格</span><span class="sxs-lookup"><span data-stu-id="78664-102">AppliedBandwidthSource table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78664-103">_**主題上次修改日期：** 2012年-10-02_</span><span class="sxs-lookup"><span data-stu-id="78664-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="78664-p101">AppliedBandwidthSource 表格是一種支援資料表，其中的每一項記錄都代表一種來源。</span><span class="sxs-lookup"><span data-stu-id="78664-p101">The AppliedBandwidthSource table is a supporting table. Each record represents one source.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="78664-106"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="78664-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="78664-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="78664-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="78664-108"><strong>主索引鍵 /</strong></span><span class="sxs-lookup"><span data-stu-id="78664-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="78664-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="78664-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="78664-110"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="78664-110"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="78664-111">int</span><span class="sxs-lookup"><span data-stu-id="78664-111">int</span></span></p></td>
<td><p><span data-ttu-id="78664-112">主要</span><span class="sxs-lookup"><span data-stu-id="78664-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="78664-113">用於識別來源的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="78664-113">Unique number identifying the source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78664-114"><strong>AppliedBandwidthSource</strong></span><span class="sxs-lookup"><span data-stu-id="78664-114"><strong>AppliedBandwidthSource</strong></span></span></p></td>
<td><p><span data-ttu-id="78664-115">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="78664-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="78664-116">Unique</span><span class="sxs-lookup"><span data-stu-id="78664-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="78664-p102">這是所採用的頻寬容量來源。其會說明頻寬限制的來源 (例如，「原則伺服器」、「TURN 伺服器」或「形式」)。</span><span class="sxs-lookup"><span data-stu-id="78664-p102">This is the source of the bandwidth cap being imposed. It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

