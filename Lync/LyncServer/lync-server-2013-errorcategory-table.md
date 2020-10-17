---
title: Lync Server 2013： ErrorCategory 表格
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
ms.openlocfilehash: 7f21535c1806223e7687ceb24ee94a93fe15238d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533150"
---
# <a name="errorcategory-table-in-lync-server-2013"></a><span data-ttu-id="926d1-102">Lync Server 2013 中的 ErrorCategory 表格</span><span class="sxs-lookup"><span data-stu-id="926d1-102">ErrorCategory table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="926d1-103">_**主題上次修改日期：** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="926d1-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="926d1-104">ErrorCategory 表格包含每個 Microsoft Lync Server 2013 診斷分類的好記名稱。</span><span class="sxs-lookup"><span data-stu-id="926d1-104">The ErrorCategory table contains the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span> <span data-ttu-id="926d1-105">Lync Server 2013 預設會使用下列類別：</span><span class="sxs-lookup"><span data-stu-id="926d1-105">By default, Lync Server 2013 uses the following classifications:</span></span>

  - <span data-ttu-id="926d1-106">0 -- 成功</span><span class="sxs-lookup"><span data-stu-id="926d1-106">0 -- Success</span></span>

  - <span data-ttu-id="926d1-107">1--預期的失敗</span><span class="sxs-lookup"><span data-stu-id="926d1-107">1 -- Expected failure</span></span>

  - <span data-ttu-id="926d1-108">2 – 未預期的失敗</span><span class="sxs-lookup"><span data-stu-id="926d1-108">2 – Unexpected failure</span></span>

<span data-ttu-id="926d1-109">此表格已引進 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="926d1-109">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="926d1-110">欄</span><span class="sxs-lookup"><span data-stu-id="926d1-110">Column</span></span></th>
<th><span data-ttu-id="926d1-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="926d1-111">Data Type</span></span></th>
<th><span data-ttu-id="926d1-112">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="926d1-112">Key/Index</span></span></th>
<th><span data-ttu-id="926d1-113">詳細資料</span><span class="sxs-lookup"><span data-stu-id="926d1-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="926d1-114"><strong>CategoryId</strong></span><span class="sxs-lookup"><span data-stu-id="926d1-114"><strong>CategoryId</strong></span></span></p></td>
<td><p><span data-ttu-id="926d1-115">Tinyint</span><span class="sxs-lookup"><span data-stu-id="926d1-115">tinyint</span></span></p></td>
<td><p><span data-ttu-id="926d1-116">主要</span><span class="sxs-lookup"><span data-stu-id="926d1-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="926d1-117">分類的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="926d1-117">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="926d1-118"><strong>名稱</strong></span><span class="sxs-lookup"><span data-stu-id="926d1-118"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="926d1-119">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="926d1-119">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="926d1-p102">指派給分類的值和易記名稱。允許的值為：</span><span class="sxs-lookup"><span data-stu-id="926d1-p102">Value and friendly name assigned to the classification. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="926d1-122">0 -- 成功</span><span class="sxs-lookup"><span data-stu-id="926d1-122">0 -- Success</span></span></p></li>
<li><p><span data-ttu-id="926d1-123">1--預期的失敗</span><span class="sxs-lookup"><span data-stu-id="926d1-123">1 -- Expected failure</span></span></p></li>
<li><p><span data-ttu-id="926d1-124">2 – 未預期的失敗</span><span class="sxs-lookup"><span data-stu-id="926d1-124">2 – Unexpected failure</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

