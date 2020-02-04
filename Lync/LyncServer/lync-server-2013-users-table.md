---
title: Lync Server 2013：Users 表格
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
ms.openlocfilehash: c2be643f8a593af01ee47ad93d3910d44ee86e48
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744323"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="users-table-in-lync-server-2013"></a><span data-ttu-id="1210d-102">Lync Server 2013 中的 Users 表格</span><span class="sxs-lookup"><span data-stu-id="1210d-102">Users table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1210d-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="1210d-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="1210d-104">[使用者] 資料表是支援表格。</span><span class="sxs-lookup"><span data-stu-id="1210d-104">The Users table is a supporting table.</span></span> <span data-ttu-id="1210d-105">資料表中的每一筆記錄都儲存有關在資料庫中有記錄的通話或會話中涉及之一個使用者的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="1210d-105">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1210d-106">左欄</span><span class="sxs-lookup"><span data-stu-id="1210d-106">Column</span></span></th>
<th><span data-ttu-id="1210d-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="1210d-107">Data Type</span></span></th>
<th><span data-ttu-id="1210d-108">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="1210d-108">Key/Index</span></span></th>
<th><span data-ttu-id="1210d-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="1210d-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1210d-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="1210d-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="1210d-111">datetime</span><span class="sxs-lookup"><span data-stu-id="1210d-111">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1210d-112">內部使用的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="1210d-112">Time stamp for internal use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1210d-113"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="1210d-113"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="1210d-114">int</span><span class="sxs-lookup"><span data-stu-id="1210d-114">int</span></span></p></td>
<td><p><span data-ttu-id="1210d-115">首選</span><span class="sxs-lookup"><span data-stu-id="1210d-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="1210d-116">標識此使用者的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="1210d-116">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1210d-117"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="1210d-117"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="1210d-118">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="1210d-118">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1210d-119">使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="1210d-119">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1210d-120"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="1210d-120"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="1210d-121">int</span><span class="sxs-lookup"><span data-stu-id="1210d-121">int</span></span></p></td>
<td><p><span data-ttu-id="1210d-122">外</span><span class="sxs-lookup"><span data-stu-id="1210d-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1210d-123">此使用者的租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="1210d-123">This user’s Tenant ID.</span></span> <span data-ttu-id="1210d-124">如需詳細資訊，請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中</a>的 [承租人] 資料表。</span><span class="sxs-lookup"><span data-stu-id="1210d-124">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1210d-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="1210d-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="1210d-126">int</span><span class="sxs-lookup"><span data-stu-id="1210d-126">int</span></span></p></td>
<td><p><span data-ttu-id="1210d-127">外</span><span class="sxs-lookup"><span data-stu-id="1210d-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1210d-128">此使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="1210d-128">This user’s URI type.</span></span> <span data-ttu-id="1210d-129">如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</span><span class="sxs-lookup"><span data-stu-id="1210d-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

