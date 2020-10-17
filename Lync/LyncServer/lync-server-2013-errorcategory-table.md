---
title: Lync Server 2013： ErrorCategory 表格
description: Lync Server 2013： ErrorCategory 表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorCategory table
ms:assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204675(v=OCS.15)
ms:contentKeyID: 48183425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8154c73f33b5dad62a338335a960553cfc06ec13
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546429"
---
# <a name="errorcategory-table-in-lync-server-2013"></a><span data-ttu-id="a441b-103">Lync Server 2013 中的 ErrorCategory 表格</span><span class="sxs-lookup"><span data-stu-id="a441b-103">ErrorCategory table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a441b-104">_**主題上次修改日期：** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="a441b-104">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="a441b-105">ErrorCategory 表格包含每個 Microsoft Lync Server 2013 診斷分類的好記名稱。</span><span class="sxs-lookup"><span data-stu-id="a441b-105">The ErrorCategory table contains the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span> <span data-ttu-id="a441b-106">Lync Server 2013 預設會使用下列類別：</span><span class="sxs-lookup"><span data-stu-id="a441b-106">By default, Lync Server 2013 uses the following classifications:</span></span>

  - <span data-ttu-id="a441b-107">0 -- 成功</span><span class="sxs-lookup"><span data-stu-id="a441b-107">0 -- Success</span></span>

  - <span data-ttu-id="a441b-108">1--預期的失敗</span><span class="sxs-lookup"><span data-stu-id="a441b-108">1 -- Expected failure</span></span>

  - <span data-ttu-id="a441b-109">2 – 未預期的失敗</span><span class="sxs-lookup"><span data-stu-id="a441b-109">2 – Unexpected failure</span></span>

<span data-ttu-id="a441b-110">此表格已引進 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="a441b-110">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a441b-111">欄</span><span class="sxs-lookup"><span data-stu-id="a441b-111">Column</span></span></th>
<th><span data-ttu-id="a441b-112">資料類型</span><span class="sxs-lookup"><span data-stu-id="a441b-112">Data Type</span></span></th>
<th><span data-ttu-id="a441b-113">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="a441b-113">Key/Index</span></span></th>
<th><span data-ttu-id="a441b-114">詳細資料</span><span class="sxs-lookup"><span data-stu-id="a441b-114">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a441b-115"><strong>CategoryId</strong></span><span class="sxs-lookup"><span data-stu-id="a441b-115"><strong>CategoryId</strong></span></span></p></td>
<td><p><span data-ttu-id="a441b-116">Tinyint</span><span class="sxs-lookup"><span data-stu-id="a441b-116">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a441b-117">主要</span><span class="sxs-lookup"><span data-stu-id="a441b-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="a441b-118">分類的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="a441b-118">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a441b-119"><strong>名稱</strong></span><span class="sxs-lookup"><span data-stu-id="a441b-119"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="a441b-120">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="a441b-120">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a441b-p102">指派給分類的值和易記名稱。允許的值為：</span><span class="sxs-lookup"><span data-stu-id="a441b-p102">Value and friendly name assigned to the classification. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="a441b-123">0 -- 成功</span><span class="sxs-lookup"><span data-stu-id="a441b-123">0 -- Success</span></span></p></li>
<li><p><span data-ttu-id="a441b-124">1--預期的失敗</span><span class="sxs-lookup"><span data-stu-id="a441b-124">1 -- Expected failure</span></span></p></li>
<li><p><span data-ttu-id="a441b-125">2 – 未預期的失敗</span><span class="sxs-lookup"><span data-stu-id="a441b-125">2 – Unexpected failure</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

