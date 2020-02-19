---
title: 'Lync Server 2013: IMReportSummary 表'
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
ms.openlocfilehash: 619f502f3671d5f8bfe66af2b157a9729ab0e952
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42131166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="imreportsummary-table-in-lync-server-2013"></a><span data-ttu-id="271f8-102">Lync Server 2013 中的 IMReportSummary 表</span><span class="sxs-lookup"><span data-stu-id="271f8-102">IMReportSummary table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="271f8-103">_**主題上次修改日期：** 2012年-08-20 個_</span><span class="sxs-lookup"><span data-stu-id="271f8-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="271f8-104">IMReportSummaryTable 會提供組織中保留之立即訊息工作階段的整體報告。</span><span class="sxs-lookup"><span data-stu-id="271f8-104">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="271f8-105">Microsoft Lync Server 2013 中已採用此表格。</span><span class="sxs-lookup"><span data-stu-id="271f8-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="271f8-106">欄</span><span class="sxs-lookup"><span data-stu-id="271f8-106">Column</span></span></th>
<th><span data-ttu-id="271f8-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="271f8-107">Data Type</span></span></th>
<th><span data-ttu-id="271f8-108">主索引鍵 /</span><span class="sxs-lookup"><span data-stu-id="271f8-108">Key/Index</span></span></th>
<th><span data-ttu-id="271f8-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="271f8-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="271f8-110"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="271f8-110"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="271f8-111">datetime</span><span class="sxs-lookup"><span data-stu-id="271f8-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="271f8-112">主要</span><span class="sxs-lookup"><span data-stu-id="271f8-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="271f8-113">立即訊息工作階段開始的日期及時間。</span><span class="sxs-lookup"><span data-stu-id="271f8-113">Date and time that the instant messaging session began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="271f8-114"><strong>TimePeriod</strong></span><span class="sxs-lookup"><span data-stu-id="271f8-114"><strong>TimePeriod</strong></span></span></p></td>
<td><p><span data-ttu-id="271f8-115">char(1)</span><span class="sxs-lookup"><span data-stu-id="271f8-115">char(1)</span></span></p></td>
<td><p><span data-ttu-id="271f8-116">主要</span><span class="sxs-lookup"><span data-stu-id="271f8-116">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="271f8-117"><strong>PoolFQDN</strong></span><span class="sxs-lookup"><span data-stu-id="271f8-117"><strong>PoolFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="271f8-118">nvarchar(257)</span><span class="sxs-lookup"><span data-stu-id="271f8-118">nvarchar(257)</span></span></p></td>
<td><p><span data-ttu-id="271f8-119">主要</span><span class="sxs-lookup"><span data-stu-id="271f8-119">Primary</span></span></p></td>
<td><p><span data-ttu-id="271f8-120">裝載此工作階段之集區的完整網域名稱。</span><span class="sxs-lookup"><span data-stu-id="271f8-120">Fully qualified domain name of the pool hosting the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="271f8-121"><strong>A</strong></span><span class="sxs-lookup"><span data-stu-id="271f8-121"><strong>AuthType</strong></span></span></p></td>
<td><p><span data-ttu-id="271f8-122">int</span><span class="sxs-lookup"><span data-stu-id="271f8-122">int</span></span></p></td>
<td><p><span data-ttu-id="271f8-123">主要</span><span class="sxs-lookup"><span data-stu-id="271f8-123">Primary</span></span></p></td>
<td><p><span data-ttu-id="271f8-124">電話的優先順序 (例如，緊急或非緊急)。</span><span class="sxs-lookup"><span data-stu-id="271f8-124">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="271f8-125">優先順序資訊都會儲存在<a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 中的 CallPriorities 表格</a>。</span><span class="sxs-lookup"><span data-stu-id="271f8-125">Priority information is stored in the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="271f8-126"><strong>SessionCount</strong></span><span class="sxs-lookup"><span data-stu-id="271f8-126"><strong>SessionCount</strong></span></span></p></td>
<td><p><span data-ttu-id="271f8-127">bigint</span><span class="sxs-lookup"><span data-stu-id="271f8-127">bigint</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="271f8-128"><strong>MsgCount</strong></span><span class="sxs-lookup"><span data-stu-id="271f8-128"><strong>MsgCount</strong></span></span></p></td>
<td><p><span data-ttu-id="271f8-129">bigint</span><span class="sxs-lookup"><span data-stu-id="271f8-129">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="271f8-130">工作階段期間交換的立即訊息總數。</span><span class="sxs-lookup"><span data-stu-id="271f8-130">Total number of instant messages exchanged during the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

