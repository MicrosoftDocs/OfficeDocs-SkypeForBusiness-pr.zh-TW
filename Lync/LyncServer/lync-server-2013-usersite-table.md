---
title: 'Lync Server 2013:: UserSite 表格'
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
ms.openlocfilehash: 39119f423f1bc06b6f51f9f18cbbf39d670c7270
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212919"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="usersite-table-in-lync-server-2013"></a><span data-ttu-id="32b23-102">在 [Lync Server 2013: UserSite 表格</span><span class="sxs-lookup"><span data-stu-id="32b23-102">UserSite table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32b23-103">_**主題上次修改日期：** 2010年-11-09_</span><span class="sxs-lookup"><span data-stu-id="32b23-103">_**Topic Last Modified:** 2010-11-09_</span></span>

<span data-ttu-id="32b23-p101">UserSite 表格是一種支援資料表，其中的每一項記錄都代表網路組態設定中定義的一個使用者網站。</span><span class="sxs-lookup"><span data-stu-id="32b23-p101">The UserSite table is a supporting table. Each record represents one user site defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="32b23-106"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="32b23-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="32b23-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="32b23-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="32b23-108"><strong>主索引鍵 /</strong></span><span class="sxs-lookup"><span data-stu-id="32b23-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="32b23-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="32b23-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32b23-110"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="32b23-110"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="32b23-111">int</span><span class="sxs-lookup"><span data-stu-id="32b23-111">int</span></span></p></td>
<td><p><span data-ttu-id="32b23-112">主要</span><span class="sxs-lookup"><span data-stu-id="32b23-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="32b23-113">用於識別使用者網站的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="32b23-113">Unique number identifying the user site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32b23-114"><strong>UserSiteName</strong></span><span class="sxs-lookup"><span data-stu-id="32b23-114"><strong>UserSiteName</strong></span></span></p></td>
<td><p><span data-ttu-id="32b23-115">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="32b23-115">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="32b23-116">Unique</span><span class="sxs-lookup"><span data-stu-id="32b23-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="32b23-117">使用者網站名稱。</span><span class="sxs-lookup"><span data-stu-id="32b23-117">User site’s name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32b23-118"><strong>RegionKey</strong></span><span class="sxs-lookup"><span data-stu-id="32b23-118"><strong>RegionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="32b23-119">int</span><span class="sxs-lookup"><span data-stu-id="32b23-119">int</span></span></p></td>
<td><p><span data-ttu-id="32b23-120">Foreign</span><span class="sxs-lookup"><span data-stu-id="32b23-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="32b23-121">參考來源： <a href="lync-server-2013-region-table.md">Region table Lync Server 2013 中</a>。</span><span class="sxs-lookup"><span data-stu-id="32b23-121">Referenced from <a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

