---
title: Lync Server 2013： IMReportSummary 表格
description: Lync Server 2013： IMReportSummary 表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IMReportSummary table
ms:assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204753(v=OCS.15)
ms:contentKeyID: 48183673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfafa81d1605845b29a3627321fcbc0f72ca7ac7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547739"
---
# <a name="imreportsummary-table-in-lync-server-2013"></a><span data-ttu-id="1a482-103">Lync Server 2013 中的 IMReportSummary 表格</span><span class="sxs-lookup"><span data-stu-id="1a482-103">IMReportSummary table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a482-104">_**主題上次修改日期：** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="1a482-104">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="1a482-105">IMReportSummaryTable 會提供組織中保留之立即訊息工作階段的整體報告。</span><span class="sxs-lookup"><span data-stu-id="1a482-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="1a482-106">此表格已引進 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="1a482-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1a482-107">欄</span><span class="sxs-lookup"><span data-stu-id="1a482-107">Column</span></span></th>
<th><span data-ttu-id="1a482-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="1a482-108">Data Type</span></span></th>
<th><span data-ttu-id="1a482-109">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="1a482-109">Key/Index</span></span></th>
<th><span data-ttu-id="1a482-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="1a482-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1a482-111"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="1a482-111"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1a482-112">datetime</span><span class="sxs-lookup"><span data-stu-id="1a482-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="1a482-113">主要</span><span class="sxs-lookup"><span data-stu-id="1a482-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="1a482-114">立即訊息工作階段開始的日期及時間。</span><span class="sxs-lookup"><span data-stu-id="1a482-114">Date and time that the instant messaging session began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a482-115"><strong>TimePeriod</strong></span><span class="sxs-lookup"><span data-stu-id="1a482-115"><strong>TimePeriod</strong></span></span></p></td>
<td><p><span data-ttu-id="1a482-116">char (1) </span><span class="sxs-lookup"><span data-stu-id="1a482-116">char(1)</span></span></p></td>
<td><p><span data-ttu-id="1a482-117">主要</span><span class="sxs-lookup"><span data-stu-id="1a482-117">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a482-118"><strong>PoolFQDN</strong></span><span class="sxs-lookup"><span data-stu-id="1a482-118"><strong>PoolFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="1a482-119">Nvarchar (257) </span><span class="sxs-lookup"><span data-stu-id="1a482-119">nvarchar(257)</span></span></p></td>
<td><p><span data-ttu-id="1a482-120">主要</span><span class="sxs-lookup"><span data-stu-id="1a482-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="1a482-121">裝載此工作階段之集區的完整網域名稱。</span><span class="sxs-lookup"><span data-stu-id="1a482-121">Fully qualified domain name of the pool hosting the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a482-122"><strong>AuthType</strong></span><span class="sxs-lookup"><span data-stu-id="1a482-122"><strong>AuthType</strong></span></span></p></td>
<td><p><span data-ttu-id="1a482-123">int</span><span class="sxs-lookup"><span data-stu-id="1a482-123">int</span></span></p></td>
<td><p><span data-ttu-id="1a482-124">主要</span><span class="sxs-lookup"><span data-stu-id="1a482-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="1a482-125">電話的優先順序 (例如，緊急或非緊急)。</span><span class="sxs-lookup"><span data-stu-id="1a482-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="1a482-126">優先順序資訊會儲存在 <a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 的 CallPriorities 表格</a>中。</span><span class="sxs-lookup"><span data-stu-id="1a482-126">Priority information is stored in the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a482-127"><strong>SessionCount</strong></span><span class="sxs-lookup"><span data-stu-id="1a482-127"><strong>SessionCount</strong></span></span></p></td>
<td><p><span data-ttu-id="1a482-128">Bigint</span><span class="sxs-lookup"><span data-stu-id="1a482-128">bigint</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a482-129"><strong>MsgCount</strong></span><span class="sxs-lookup"><span data-stu-id="1a482-129"><strong>MsgCount</strong></span></span></p></td>
<td><p><span data-ttu-id="1a482-130">Bigint</span><span class="sxs-lookup"><span data-stu-id="1a482-130">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1a482-131">工作階段期間交換的立即訊息總數。</span><span class="sxs-lookup"><span data-stu-id="1a482-131">Total number of instant messages exchanged during the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

