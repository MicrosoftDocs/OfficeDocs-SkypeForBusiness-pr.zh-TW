---
title: Lync Server 2013： UserSite 表格
description: Lync Server 2013： UserSite 表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserSite table
ms:assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398256(v=OCS.15)
ms:contentKeyID: 48183552
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e0fb3149b9378bbfd3f14da8176eed226e4f57f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548619"
---
# <a name="usersite-table-in-lync-server-2013"></a><span data-ttu-id="656ec-103">Lync Server 2013 中的 UserSite 表格</span><span class="sxs-lookup"><span data-stu-id="656ec-103">UserSite table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="656ec-104">_**主題上次修改日期：** 2010-11-09_</span><span class="sxs-lookup"><span data-stu-id="656ec-104">_**Topic Last Modified:** 2010-11-09_</span></span>

<span data-ttu-id="656ec-p101">UserSite 表格是一種支援資料表，其中的每一項記錄都代表網路組態設定中定義的一個使用者網站。</span><span class="sxs-lookup"><span data-stu-id="656ec-p101">The UserSite table is a supporting table. Each record represents one user site defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="656ec-107"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="656ec-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="656ec-108"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="656ec-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="656ec-109"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="656ec-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="656ec-110"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="656ec-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="656ec-111"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="656ec-111"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="656ec-112">int</span><span class="sxs-lookup"><span data-stu-id="656ec-112">int</span></span></p></td>
<td><p><span data-ttu-id="656ec-113">主要</span><span class="sxs-lookup"><span data-stu-id="656ec-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="656ec-114">用於識別使用者網站的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="656ec-114">Unique number identifying the user site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="656ec-115"><strong>UserSiteName</strong></span><span class="sxs-lookup"><span data-stu-id="656ec-115"><strong>UserSiteName</strong></span></span></p></td>
<td><p><span data-ttu-id="656ec-116">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="656ec-116">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="656ec-117">Unique</span><span class="sxs-lookup"><span data-stu-id="656ec-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="656ec-118">使用者網站名稱。</span><span class="sxs-lookup"><span data-stu-id="656ec-118">User site’s name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="656ec-119"><strong>RegionKey</strong></span><span class="sxs-lookup"><span data-stu-id="656ec-119"><strong>RegionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="656ec-120">int</span><span class="sxs-lookup"><span data-stu-id="656ec-120">int</span></span></p></td>
<td><p><span data-ttu-id="656ec-121">Foreign</span><span class="sxs-lookup"><span data-stu-id="656ec-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="656ec-122"><a href="lync-server-2013-region-table.md">Lync Server 2013 中</a>的 [從地區表參考]。</span><span class="sxs-lookup"><span data-stu-id="656ec-122">Referenced from <a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

