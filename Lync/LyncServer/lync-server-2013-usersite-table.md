---
title: Lync Server 2013：UserSite 表格
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
ms.openlocfilehash: 7e316fe33ac77784a681a71b9cabd0613bb1cc1b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="usersite-table-in-lync-server-2013"></a><span data-ttu-id="c8def-102">Lync Server 2013 中的 UserSite 表格</span><span class="sxs-lookup"><span data-stu-id="c8def-102">UserSite table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8def-103">_**主題上次修改日期：** 2010-11-09_</span><span class="sxs-lookup"><span data-stu-id="c8def-103">_**Topic Last Modified:** 2010-11-09_</span></span>

<span data-ttu-id="c8def-104">UserSite 資料表是支援資料表。</span><span class="sxs-lookup"><span data-stu-id="c8def-104">The UserSite table is a supporting table.</span></span> <span data-ttu-id="c8def-105">每個記錄代表 [網路設定] 中定義的一個使用者網站。</span><span class="sxs-lookup"><span data-stu-id="c8def-105">Each record represents one user site defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8def-106"><strong>左欄</strong></span><span class="sxs-lookup"><span data-stu-id="c8def-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="c8def-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="c8def-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="c8def-108"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="c8def-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="c8def-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="c8def-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8def-110"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="c8def-110"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="c8def-111">int</span><span class="sxs-lookup"><span data-stu-id="c8def-111">int</span></span></p></td>
<td><p><span data-ttu-id="c8def-112">首選</span><span class="sxs-lookup"><span data-stu-id="c8def-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="c8def-113">識別使用者網站的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="c8def-113">Unique number identifying the user site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8def-114"><strong>UserSiteName</strong></span><span class="sxs-lookup"><span data-stu-id="c8def-114"><strong>UserSiteName</strong></span></span></p></td>
<td><p><span data-ttu-id="c8def-115">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="c8def-115">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c8def-116">唯一</span><span class="sxs-lookup"><span data-stu-id="c8def-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="c8def-117">使用者網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="c8def-117">User site’s name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8def-118"><strong>RegionKey</strong></span><span class="sxs-lookup"><span data-stu-id="c8def-118"><strong>RegionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="c8def-119">int</span><span class="sxs-lookup"><span data-stu-id="c8def-119">int</span></span></p></td>
<td><p><span data-ttu-id="c8def-120">外</span><span class="sxs-lookup"><span data-stu-id="c8def-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c8def-121">從<a href="lync-server-2013-region-table.md">Lync Server 2013 的地區資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="c8def-121">Referenced from <a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

