---
title: Lync Server 2013：CallPriorities 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: CallPriorities table
ms:assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398093(v=OCS.15)
ms:contentKeyID: 48183275
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fdf08f1dfa8cd04b29f6edb6604a57ab5ec9e822
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="callpriorities-table-in-lync-server-2013"></a><span data-ttu-id="2af47-102">Lync Server 2013 中的 CallPriorities 表格</span><span class="sxs-lookup"><span data-stu-id="2af47-102">CallPriorities table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2af47-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="2af47-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="2af47-104">CallPriorities 資料表是一個靜態資料表，可儲存可能的通話優先順序清單，例如「緊急」、「緊急」或「標準」。</span><span class="sxs-lookup"><span data-stu-id="2af47-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as ‘emergency’, ‘urgent’, or ‘normal’.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2af47-105">左欄</span><span class="sxs-lookup"><span data-stu-id="2af47-105">Column</span></span></th>
<th><span data-ttu-id="2af47-106">資料類型</span><span class="sxs-lookup"><span data-stu-id="2af47-106">Data Type</span></span></th>
<th><span data-ttu-id="2af47-107">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="2af47-107">Key/Index</span></span></th>
<th><span data-ttu-id="2af47-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="2af47-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2af47-109"><strong>PriorityId</strong></span><span class="sxs-lookup"><span data-stu-id="2af47-109"><strong>PriorityId</strong></span></span></p></td>
<td><p><span data-ttu-id="2af47-110">Tinyint</span><span class="sxs-lookup"><span data-stu-id="2af47-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="2af47-111">首選</span><span class="sxs-lookup"><span data-stu-id="2af47-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2af47-112"><strong>優先順序</strong></span><span class="sxs-lookup"><span data-stu-id="2af47-112"><strong>Priority</strong></span></span></p></td>
<td><p><span data-ttu-id="2af47-113">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="2af47-113">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2af47-114">允許的值：</span><span class="sxs-lookup"><span data-stu-id="2af47-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="2af47-115">0-未知</span><span class="sxs-lookup"><span data-stu-id="2af47-115">0 - Unknown</span></span></p></li>
<li><p><span data-ttu-id="2af47-116">1-非緊急</span><span class="sxs-lookup"><span data-stu-id="2af47-116">1 – Non-Urgent</span></span></p></li>
<li><p><span data-ttu-id="2af47-117">2-標準</span><span class="sxs-lookup"><span data-stu-id="2af47-117">2 - Normal</span></span></p></li>
<li><p><span data-ttu-id="2af47-118">3-緊急</span><span class="sxs-lookup"><span data-stu-id="2af47-118">3 - Urgent</span></span></p></li>
<li><p><span data-ttu-id="2af47-119">4-緊急</span><span class="sxs-lookup"><span data-stu-id="2af47-119">4 - Emergency</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

