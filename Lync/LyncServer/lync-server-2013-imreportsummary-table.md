---
title: Lync Server 2013： IMReportSummary 表格
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
ms.openlocfilehash: a7a6be73d31892b5a0d5a3a5b10ad136f92afbf5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="imreportsummary-table-in-lync-server-2013"></a><span data-ttu-id="ebf65-102">Lync Server 2013 中的 IMReportSummary 表格</span><span class="sxs-lookup"><span data-stu-id="ebf65-102">IMReportSummary table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ebf65-103">_**主題上次修改日期：** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="ebf65-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="ebf65-104">IMReportSummaryTable 會提供組織中的立即訊息會話的整體報告。</span><span class="sxs-lookup"><span data-stu-id="ebf65-104">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="ebf65-105">此表格是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="ebf65-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ebf65-106">左欄</span><span class="sxs-lookup"><span data-stu-id="ebf65-106">Column</span></span></th>
<th><span data-ttu-id="ebf65-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="ebf65-107">Data Type</span></span></th>
<th><span data-ttu-id="ebf65-108">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="ebf65-108">Key/Index</span></span></th>
<th><span data-ttu-id="ebf65-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="ebf65-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ebf65-110"><strong>開始</strong></span><span class="sxs-lookup"><span data-stu-id="ebf65-110"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ebf65-111">datetime</span><span class="sxs-lookup"><span data-stu-id="ebf65-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="ebf65-112">首選</span><span class="sxs-lookup"><span data-stu-id="ebf65-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="ebf65-113">立即訊息會話開始的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="ebf65-113">Date and time that the instant messaging session began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ebf65-114"><strong>TimePeriod</strong></span><span class="sxs-lookup"><span data-stu-id="ebf65-114"><strong>TimePeriod</strong></span></span></p></td>
<td><p><span data-ttu-id="ebf65-115">char （1）</span><span class="sxs-lookup"><span data-stu-id="ebf65-115">char(1)</span></span></p></td>
<td><p><span data-ttu-id="ebf65-116">首選</span><span class="sxs-lookup"><span data-stu-id="ebf65-116">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ebf65-117"><strong>PoolFQDN</strong></span><span class="sxs-lookup"><span data-stu-id="ebf65-117"><strong>PoolFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="ebf65-118">Nvarchar （257）</span><span class="sxs-lookup"><span data-stu-id="ebf65-118">nvarchar(257)</span></span></p></td>
<td><p><span data-ttu-id="ebf65-119">首選</span><span class="sxs-lookup"><span data-stu-id="ebf65-119">Primary</span></span></p></td>
<td><p><span data-ttu-id="ebf65-120">主持會話之池的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="ebf65-120">Fully qualified domain name of the pool hosting the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ebf65-121"><strong>AuthType</strong></span><span class="sxs-lookup"><span data-stu-id="ebf65-121"><strong>AuthType</strong></span></span></p></td>
<td><p><span data-ttu-id="ebf65-122">int</span><span class="sxs-lookup"><span data-stu-id="ebf65-122">int</span></span></p></td>
<td><p><span data-ttu-id="ebf65-123">首選</span><span class="sxs-lookup"><span data-stu-id="ebf65-123">Primary</span></span></p></td>
<td><p><span data-ttu-id="ebf65-124">通話的優先順序（例如，緊急或非緊急）。</span><span class="sxs-lookup"><span data-stu-id="ebf65-124">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="ebf65-125">優先順序資訊會儲存在<a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 的 CallPriorities 表格中</a>。</span><span class="sxs-lookup"><span data-stu-id="ebf65-125">Priority information is stored in the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ebf65-126"><strong>SessionCount</strong></span><span class="sxs-lookup"><span data-stu-id="ebf65-126"><strong>SessionCount</strong></span></span></p></td>
<td><p><span data-ttu-id="ebf65-127">Bigint</span><span class="sxs-lookup"><span data-stu-id="ebf65-127">bigint</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ebf65-128"><strong>MsgCount</strong></span><span class="sxs-lookup"><span data-stu-id="ebf65-128"><strong>MsgCount</strong></span></span></p></td>
<td><p><span data-ttu-id="ebf65-129">Bigint</span><span class="sxs-lookup"><span data-stu-id="ebf65-129">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ebf65-130">會話期間交換的立即訊息總數。</span><span class="sxs-lookup"><span data-stu-id="ebf65-130">Total number of instant messages exchanged during the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

