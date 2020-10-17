---
title: Lync Server 2013：子網表格
description: Lync Server 2013：子網表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Subnet table
ms:assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398582(v=OCS.15)
ms:contentKeyID: 48184544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d30c04ddf897e0a62551709b30211ba724a75cbf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546309"
---
# <a name="subnet-table-in-lync-server-2013"></a><span data-ttu-id="66543-103">Lync Server 2013 中的子網表格</span><span class="sxs-lookup"><span data-stu-id="66543-103">Subnet table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66543-104">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="66543-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="66543-p101">Subnet 表格是一種支援資料表。每筆記錄代表在網路組態設定中定義的一個子網路。</span><span class="sxs-lookup"><span data-stu-id="66543-p101">The Subnet table is a supporting table. Each record represents one subnet defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66543-107"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="66543-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="66543-108"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="66543-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="66543-109"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="66543-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="66543-110"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="66543-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66543-111"><strong>SubnetIP</strong></span><span class="sxs-lookup"><span data-stu-id="66543-111"><strong>SubnetIP</strong></span></span></p></td>
<td><p><span data-ttu-id="66543-112">int</span><span class="sxs-lookup"><span data-stu-id="66543-112">int</span></span></p></td>
<td><p><span data-ttu-id="66543-113">主要、外部</span><span class="sxs-lookup"><span data-stu-id="66543-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="66543-114">子網路 IP 的整數表示。</span><span class="sxs-lookup"><span data-stu-id="66543-114">Integer representation for the subnet IP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66543-115"><strong>SubnetMask</strong></span><span class="sxs-lookup"><span data-stu-id="66543-115"><strong>SubnetMask</strong></span></span></p></td>
<td><p><span data-ttu-id="66543-116">int</span><span class="sxs-lookup"><span data-stu-id="66543-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66543-117">子網路遮罩。</span><span class="sxs-lookup"><span data-stu-id="66543-117">Subnet mask.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66543-118"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="66543-118"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="66543-119">int</span><span class="sxs-lookup"><span data-stu-id="66543-119">int</span></span></p></td>
<td><p><span data-ttu-id="66543-120">Foreign</span><span class="sxs-lookup"><span data-stu-id="66543-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="66543-121">從 <a href="lync-server-2013-usersite-table.md">Lync Server 2013 的 UserSite 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="66543-121">Referenced from the <a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66543-122"><strong>SubnetDescription</strong></span><span class="sxs-lookup"><span data-stu-id="66543-122"><strong>SubnetDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="66543-123">Nvarchar (512) </span><span class="sxs-lookup"><span data-stu-id="66543-123">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66543-124">子網路的描述。</span><span class="sxs-lookup"><span data-stu-id="66543-124">The description for the subnet.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

