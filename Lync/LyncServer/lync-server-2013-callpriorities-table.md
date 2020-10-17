---
title: Lync Server 2013： CallPriorities 表格
description: Lync Server 2013： CallPriorities 表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CallPriorities table
ms:assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398093(v=OCS.15)
ms:contentKeyID: 48183275
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe3cd1639921c63630e157744dbc8af22c50fac7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565179"
---
# <a name="callpriorities-table-in-lync-server-2013"></a><span data-ttu-id="4a41c-103">Lync Server 2013 中的 CallPriorities 表格</span><span class="sxs-lookup"><span data-stu-id="4a41c-103">CallPriorities table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a41c-104">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="4a41c-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="4a41c-105">CallPriorities 表格是靜態表格，可儲存通話可能優先順序的清單 (如「緊急」、「急」或「一般」)。</span><span class="sxs-lookup"><span data-stu-id="4a41c-105">The CallPriorities table is a static table that stores the list of possible call priorities, such as ‘emergency’, ‘urgent’, or ‘normal’.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4a41c-106">欄</span><span class="sxs-lookup"><span data-stu-id="4a41c-106">Column</span></span></th>
<th><span data-ttu-id="4a41c-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="4a41c-107">Data Type</span></span></th>
<th><span data-ttu-id="4a41c-108">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="4a41c-108">Key/Index</span></span></th>
<th><span data-ttu-id="4a41c-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="4a41c-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a41c-110"><strong>PriorityId</strong></span><span class="sxs-lookup"><span data-stu-id="4a41c-110"><strong>PriorityId</strong></span></span></p></td>
<td><p><span data-ttu-id="4a41c-111">Tinyint</span><span class="sxs-lookup"><span data-stu-id="4a41c-111">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4a41c-112">主要</span><span class="sxs-lookup"><span data-stu-id="4a41c-112">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a41c-113"><strong>優先順序</strong></span><span class="sxs-lookup"><span data-stu-id="4a41c-113"><strong>Priority</strong></span></span></p></td>
<td><p><span data-ttu-id="4a41c-114">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="4a41c-114">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4a41c-115">允許的值：</span><span class="sxs-lookup"><span data-stu-id="4a41c-115">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="4a41c-116">0 - 未知</span><span class="sxs-lookup"><span data-stu-id="4a41c-116">0 - Unknown</span></span></p></li>
<li><p><span data-ttu-id="4a41c-117">1 - 非緊急</span><span class="sxs-lookup"><span data-stu-id="4a41c-117">1 – Non-Urgent</span></span></p></li>
<li><p><span data-ttu-id="4a41c-118">2 - 一般</span><span class="sxs-lookup"><span data-stu-id="4a41c-118">2 - Normal</span></span></p></li>
<li><p><span data-ttu-id="4a41c-119">3 - 急</span><span class="sxs-lookup"><span data-stu-id="4a41c-119">3 - Urgent</span></span></p></li>
<li><p><span data-ttu-id="4a41c-120">4 - 緊急</span><span class="sxs-lookup"><span data-stu-id="4a41c-120">4 - Emergency</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

