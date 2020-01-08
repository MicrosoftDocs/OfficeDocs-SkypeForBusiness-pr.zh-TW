---
title: Lync Server 2013： IMReportSummary 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IMReportSummary table
ms:assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204753(v=OCS.15)
ms:contentKeyID: 48183673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2254bafe059cc1a4bc6436580e9d604711f5fb3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976066"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="imreportsummary-table-in-lync-server-2013"></a><span data-ttu-id="bb944-102">Lync Server 2013 中的 IMReportSummary 表格</span><span class="sxs-lookup"><span data-stu-id="bb944-102">IMReportSummary table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb944-103">_**主題上次修改日期：** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="bb944-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="bb944-104">IMReportSummaryTable 會提供組織中的立即訊息會話的整體報告。</span><span class="sxs-lookup"><span data-stu-id="bb944-104">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="bb944-105">此表格是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="bb944-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb944-106">左欄</span><span class="sxs-lookup"><span data-stu-id="bb944-106">Column</span></span></th>
<th><span data-ttu-id="bb944-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="bb944-107">Data Type</span></span></th>
<th><span data-ttu-id="bb944-108">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="bb944-108">Key/Index</span></span></th>
<th><span data-ttu-id="bb944-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="bb944-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb944-110"><strong>開始</strong></span><span class="sxs-lookup"><span data-stu-id="bb944-110"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bb944-111">datetime</span><span class="sxs-lookup"><span data-stu-id="bb944-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="bb944-112">首選</span><span class="sxs-lookup"><span data-stu-id="bb944-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="bb944-113">立即訊息會話開始的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="bb944-113">Date and time that the instant messaging session began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb944-114"><strong>TimePeriod</strong></span><span class="sxs-lookup"><span data-stu-id="bb944-114"><strong>TimePeriod</strong></span></span></p></td>
<td><p><span data-ttu-id="bb944-115">char （1）</span><span class="sxs-lookup"><span data-stu-id="bb944-115">char(1)</span></span></p></td>
<td><p><span data-ttu-id="bb944-116">首選</span><span class="sxs-lookup"><span data-stu-id="bb944-116">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb944-117"><strong>PoolFQDN</strong></span><span class="sxs-lookup"><span data-stu-id="bb944-117"><strong>PoolFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="bb944-118">Nvarchar （257）</span><span class="sxs-lookup"><span data-stu-id="bb944-118">nvarchar(257)</span></span></p></td>
<td><p><span data-ttu-id="bb944-119">首選</span><span class="sxs-lookup"><span data-stu-id="bb944-119">Primary</span></span></p></td>
<td><p><span data-ttu-id="bb944-120">主持會話之池的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="bb944-120">Fully qualified domain name of the pool hosting the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb944-121"><strong>AuthType</strong></span><span class="sxs-lookup"><span data-stu-id="bb944-121"><strong>AuthType</strong></span></span></p></td>
<td><p><span data-ttu-id="bb944-122">int</span><span class="sxs-lookup"><span data-stu-id="bb944-122">int</span></span></p></td>
<td><p><span data-ttu-id="bb944-123">首選</span><span class="sxs-lookup"><span data-stu-id="bb944-123">Primary</span></span></p></td>
<td><p><span data-ttu-id="bb944-124">通話的優先順序（例如，緊急或非緊急）。</span><span class="sxs-lookup"><span data-stu-id="bb944-124">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="bb944-125">優先順序資訊會儲存在<a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 的 CallPriorities 表格中</a>。</span><span class="sxs-lookup"><span data-stu-id="bb944-125">Priority information is stored in the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb944-126"><strong>SessionCount</strong></span><span class="sxs-lookup"><span data-stu-id="bb944-126"><strong>SessionCount</strong></span></span></p></td>
<td><p><span data-ttu-id="bb944-127">Bigint</span><span class="sxs-lookup"><span data-stu-id="bb944-127">bigint</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb944-128"><strong>MsgCount</strong></span><span class="sxs-lookup"><span data-stu-id="bb944-128"><strong>MsgCount</strong></span></span></p></td>
<td><p><span data-ttu-id="bb944-129">Bigint</span><span class="sxs-lookup"><span data-stu-id="bb944-129">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bb944-130">會話期間交換的立即訊息總數。</span><span class="sxs-lookup"><span data-stu-id="bb944-130">Total number of instant messages exchanged during the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

