---
title: Lync Server 2013： AppliedBandwidthSource 表格
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
ms.openlocfilehash: 289e3b2093bea001ee684945f17aee2ecb84927d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504990"
---
# <a name="appliedbandwidthsource-table-in-lync-server-2013"></a><span data-ttu-id="af170-102">Lync Server 2013 中的 AppliedBandwidthSource 表格</span><span class="sxs-lookup"><span data-stu-id="af170-102">AppliedBandwidthSource table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af170-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="af170-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="af170-p101">AppliedBandwidthSource 表格是一種支援資料表，其中的每一項記錄都代表一種來源。</span><span class="sxs-lookup"><span data-stu-id="af170-p101">The AppliedBandwidthSource table is a supporting table. Each record represents one source.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="af170-106"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="af170-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="af170-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="af170-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="af170-108"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="af170-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="af170-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="af170-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="af170-110"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="af170-110"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="af170-111">int</span><span class="sxs-lookup"><span data-stu-id="af170-111">int</span></span></p></td>
<td><p><span data-ttu-id="af170-112">主要</span><span class="sxs-lookup"><span data-stu-id="af170-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="af170-113">用於識別來源的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="af170-113">Unique number identifying the source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af170-114"><strong>AppliedBandwidthSource</strong></span><span class="sxs-lookup"><span data-stu-id="af170-114"><strong>AppliedBandwidthSource</strong></span></span></p></td>
<td><p><span data-ttu-id="af170-115">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="af170-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="af170-116">Unique</span><span class="sxs-lookup"><span data-stu-id="af170-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="af170-p102">這是所採用的頻寬容量來源。其會說明頻寬限制的來源 (例如，「原則伺服器」、「TURN 伺服器」或「形式」)。</span><span class="sxs-lookup"><span data-stu-id="af170-p102">This is the source of the bandwidth cap being imposed. It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

