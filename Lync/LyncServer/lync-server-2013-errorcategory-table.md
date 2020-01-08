---
title: Lync Server 2013： ErrorCategory 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ErrorCategory table
ms:assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204675(v=OCS.15)
ms:contentKeyID: 48183425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9bd9cebf26a147b00873c17372eca77f0a11f2d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974927"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorcategory-table-in-lync-server-2013"></a><span data-ttu-id="2bedb-102">Lync Server 2013 中的 ErrorCategory 表格</span><span class="sxs-lookup"><span data-stu-id="2bedb-102">ErrorCategory table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2bedb-103">_**主題上次修改日期：** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="2bedb-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="2bedb-104">ErrorCategory 表格包含每個 Microsoft Lync Server 2013 診斷分類的易記名稱。</span><span class="sxs-lookup"><span data-stu-id="2bedb-104">The ErrorCategory table contains the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span> <span data-ttu-id="2bedb-105">根據預設，Lync Server 2013 會使用下列分類：</span><span class="sxs-lookup"><span data-stu-id="2bedb-105">By default, Lync Server 2013 uses the following classifications:</span></span>

  - <span data-ttu-id="2bedb-106">0--成功</span><span class="sxs-lookup"><span data-stu-id="2bedb-106">0 -- Success</span></span>

  - <span data-ttu-id="2bedb-107">1--預期失敗</span><span class="sxs-lookup"><span data-stu-id="2bedb-107">1 -- Expected failure</span></span>

  - <span data-ttu-id="2bedb-108">2-意外失敗</span><span class="sxs-lookup"><span data-stu-id="2bedb-108">2 – Unexpected failure</span></span>

<span data-ttu-id="2bedb-109">此表格是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="2bedb-109">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2bedb-110">左欄</span><span class="sxs-lookup"><span data-stu-id="2bedb-110">Column</span></span></th>
<th><span data-ttu-id="2bedb-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="2bedb-111">Data Type</span></span></th>
<th><span data-ttu-id="2bedb-112">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="2bedb-112">Key/Index</span></span></th>
<th><span data-ttu-id="2bedb-113">詳細資料</span><span class="sxs-lookup"><span data-stu-id="2bedb-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2bedb-114"><strong>Id</strong></span><span class="sxs-lookup"><span data-stu-id="2bedb-114"><strong>CategoryId</strong></span></span></p></td>
<td><p><span data-ttu-id="2bedb-115">Tinyint</span><span class="sxs-lookup"><span data-stu-id="2bedb-115">tinyint</span></span></p></td>
<td><p><span data-ttu-id="2bedb-116">首選</span><span class="sxs-lookup"><span data-stu-id="2bedb-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="2bedb-117">分類的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="2bedb-117">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2bedb-118"><strong>名稱</strong></span><span class="sxs-lookup"><span data-stu-id="2bedb-118"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="2bedb-119">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="2bedb-119">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2bedb-120">指派給分類的值和易記名稱。</span><span class="sxs-lookup"><span data-stu-id="2bedb-120">Value and friendly name assigned to the classification.</span></span> <span data-ttu-id="2bedb-121">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="2bedb-121">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="2bedb-122">0--成功</span><span class="sxs-lookup"><span data-stu-id="2bedb-122">0 -- Success</span></span></p></li>
<li><p><span data-ttu-id="2bedb-123">1--預期失敗</span><span class="sxs-lookup"><span data-stu-id="2bedb-123">1 -- Expected failure</span></span></p></li>
<li><p><span data-ttu-id="2bedb-124">2-意外失敗</span><span class="sxs-lookup"><span data-stu-id="2bedb-124">2 – Unexpected failure</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

