---
title: Lync Server 2013： Users 表格
description: Lync Server 2013： Users 表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Users table
ms:assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412791(v=OCS.15)
ms:contentKeyID: 48185032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b1418e162a04e46ee0dfeca082aa66b0665fc77
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548629"
---
# <a name="users-table-in-lync-server-2013"></a><span data-ttu-id="4a540-103">Lync Server 2013 中的使用者表格</span><span class="sxs-lookup"><span data-stu-id="4a540-103">Users table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a540-104">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="4a540-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="4a540-105">[使用者] 表格是支援表格。</span><span class="sxs-lookup"><span data-stu-id="4a540-105">The Users table is a supporting table.</span></span> <span data-ttu-id="4a540-106">資料表中的每一筆記錄都儲存在具有資料庫中記錄的通話或會話中的一個使用者相關資訊。</span><span class="sxs-lookup"><span data-stu-id="4a540-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4a540-107">欄</span><span class="sxs-lookup"><span data-stu-id="4a540-107">Column</span></span></th>
<th><span data-ttu-id="4a540-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="4a540-108">Data Type</span></span></th>
<th><span data-ttu-id="4a540-109">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="4a540-109">Key/Index</span></span></th>
<th><span data-ttu-id="4a540-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="4a540-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a540-111"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="4a540-111"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="4a540-112">datetime</span><span class="sxs-lookup"><span data-stu-id="4a540-112">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4a540-113">內部使用的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="4a540-113">Time stamp for internal use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a540-114"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="4a540-114"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="4a540-115">int</span><span class="sxs-lookup"><span data-stu-id="4a540-115">int</span></span></p></td>
<td><p><span data-ttu-id="4a540-116">主要</span><span class="sxs-lookup"><span data-stu-id="4a540-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="4a540-117">用於識別此使用者的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="4a540-117">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a540-118"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="4a540-118"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="4a540-119">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="4a540-119">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4a540-120">使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="4a540-120">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a540-121"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="4a540-121"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="4a540-122">int</span><span class="sxs-lookup"><span data-stu-id="4a540-122">int</span></span></p></td>
<td><p><span data-ttu-id="4a540-123">Foreign</span><span class="sxs-lookup"><span data-stu-id="4a540-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4a540-124">此使用者的租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="4a540-124">This user’s Tenant ID.</span></span> <span data-ttu-id="4a540-125">如需詳細資訊，請參閱 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的承租人資料表</a> 。</span><span class="sxs-lookup"><span data-stu-id="4a540-125">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a540-126"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="4a540-126"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="4a540-127">int</span><span class="sxs-lookup"><span data-stu-id="4a540-127">int</span></span></p></td>
<td><p><span data-ttu-id="4a540-128">Foreign</span><span class="sxs-lookup"><span data-stu-id="4a540-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4a540-129">此使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="4a540-129">This user’s URI type.</span></span> <span data-ttu-id="4a540-130">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="4a540-130">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

