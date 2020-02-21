---
title: 'Lync Server 2013: ErrorCategory 表'
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
ms.openlocfilehash: 3052aa95aa6cd846717aa98c5778531aeee6f7e2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="errorcategory-table-in-lync-server-2013"></a><span data-ttu-id="6d4b4-102">Lync Server 2013 中的 ErrorCategory 表</span><span class="sxs-lookup"><span data-stu-id="6d4b4-102">ErrorCategory table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d4b4-103">_**主題上次修改日期：** 2012年-08-20 個_</span><span class="sxs-lookup"><span data-stu-id="6d4b4-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="6d4b4-104">ErrorCategory 表包含每個 Microsoft Lync Server 2013 診斷分類的易記名稱。</span><span class="sxs-lookup"><span data-stu-id="6d4b4-104">The ErrorCategory table contains the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span> <span data-ttu-id="6d4b4-105">根據預設，Lync Server 2013 會使用下列分類：</span><span class="sxs-lookup"><span data-stu-id="6d4b4-105">By default, Lync Server 2013 uses the following classifications:</span></span>

  - <span data-ttu-id="6d4b4-106">0 -- 成功</span><span class="sxs-lookup"><span data-stu-id="6d4b4-106">0 -- Success</span></span>

  - <span data-ttu-id="6d4b4-107">1--預期的失敗</span><span class="sxs-lookup"><span data-stu-id="6d4b4-107">1 -- Expected failure</span></span>

  - <span data-ttu-id="6d4b4-108">2 – 未預期的失敗</span><span class="sxs-lookup"><span data-stu-id="6d4b4-108">2 – Unexpected failure</span></span>

<span data-ttu-id="6d4b4-109">Microsoft Lync Server 2013 中已採用此表格。</span><span class="sxs-lookup"><span data-stu-id="6d4b4-109">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6d4b4-110">欄</span><span class="sxs-lookup"><span data-stu-id="6d4b4-110">Column</span></span></th>
<th><span data-ttu-id="6d4b4-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="6d4b4-111">Data Type</span></span></th>
<th><span data-ttu-id="6d4b4-112">主索引鍵 /</span><span class="sxs-lookup"><span data-stu-id="6d4b4-112">Key/Index</span></span></th>
<th><span data-ttu-id="6d4b4-113">詳細資料</span><span class="sxs-lookup"><span data-stu-id="6d4b4-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d4b4-114"><strong>類別識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="6d4b4-114"><strong>CategoryId</strong></span></span></p></td>
<td><p><span data-ttu-id="6d4b4-115">tinyint</span><span class="sxs-lookup"><span data-stu-id="6d4b4-115">tinyint</span></span></p></td>
<td><p><span data-ttu-id="6d4b4-116">主要</span><span class="sxs-lookup"><span data-stu-id="6d4b4-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="6d4b4-117">分類的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="6d4b4-117">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d4b4-118"><strong>Name</strong></span><span class="sxs-lookup"><span data-stu-id="6d4b4-118"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="6d4b4-119">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6d4b4-119">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6d4b4-p102">指派給分類的值和易記名稱。允許的值為：</span><span class="sxs-lookup"><span data-stu-id="6d4b4-p102">Value and friendly name assigned to the classification. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="6d4b4-122">0 -- 成功</span><span class="sxs-lookup"><span data-stu-id="6d4b4-122">0 -- Success</span></span></p></li>
<li><p><span data-ttu-id="6d4b4-123">1--預期的失敗</span><span class="sxs-lookup"><span data-stu-id="6d4b4-123">1 -- Expected failure</span></span></p></li>
<li><p><span data-ttu-id="6d4b4-124">2 – 未預期的失敗</span><span class="sxs-lookup"><span data-stu-id="6d4b4-124">2 – Unexpected failure</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

