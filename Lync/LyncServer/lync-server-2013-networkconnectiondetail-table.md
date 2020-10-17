---
title: Lync Server 2013： NetworkConnectionDetail 表格
description: Lync Server 2013： NetworkConnectionDetail 表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: NetworkConnectionDetail table
ms:assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205185(v=OCS.15)
ms:contentKeyID: 48185170
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcd0f429999b6629826a9f9369d154afe3c1af2f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561399"
---
# <a name="networkconnectiondetail-table-in-lync-server-2013"></a><span data-ttu-id="b75e5-103">Lync Server 2013 中的 NetworkConnectionDetail 表格</span><span class="sxs-lookup"><span data-stu-id="b75e5-103">NetworkConnectionDetail table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b75e5-104">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="b75e5-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="b75e5-105">NetworkConnectionDetail 表會將網路連線類型對應至其他在經驗品質資料庫中使用的網路連線識別碼。</span><span class="sxs-lookup"><span data-stu-id="b75e5-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="b75e5-106">此表格已引進 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="b75e5-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b75e5-107"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="b75e5-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="b75e5-108"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="b75e5-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="b75e5-109"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="b75e5-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="b75e5-110"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="b75e5-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b75e5-111"><strong>NetworkConnectionDetailKey</strong></span><span class="sxs-lookup"><span data-stu-id="b75e5-111"><strong>NetworkConnectionDetailKey</strong></span></span></p></td>
<td><p><span data-ttu-id="b75e5-112">Tinyint</span><span class="sxs-lookup"><span data-stu-id="b75e5-112">tinyint</span></span></p></td>
<td><p><span data-ttu-id="b75e5-113">主要</span><span class="sxs-lookup"><span data-stu-id="b75e5-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="b75e5-114">網路連線類型的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="b75e5-114">Unique identifier for the network connection type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b75e5-115"><strong>NetworkConnectionDetail</strong></span><span class="sxs-lookup"><span data-stu-id="b75e5-115"><strong>NetworkConnectionDetail</strong></span></span></p></td>
<td><p><span data-ttu-id="b75e5-116">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="b75e5-116">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b75e5-117">Unique</span><span class="sxs-lookup"><span data-stu-id="b75e5-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="b75e5-118">對應至 NetworkConnectionDetailKey 的網路連線類型。</span><span class="sxs-lookup"><span data-stu-id="b75e5-118">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="b75e5-119">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="b75e5-119">Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="b75e5-120">0--有線</span><span class="sxs-lookup"><span data-stu-id="b75e5-120">0 -- Wired</span></span></p></li>
<li><p><span data-ttu-id="b75e5-121">1--WiFi</span><span class="sxs-lookup"><span data-stu-id="b75e5-121">1 -- WiFi</span></span></p></li>
<li><p><span data-ttu-id="b75e5-122">2--乙太網路</span><span class="sxs-lookup"><span data-stu-id="b75e5-122">2 -- Ethernet</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

