---
title: Lync Server 2013：Users 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Users table
ms:assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412791(v=OCS.15)
ms:contentKeyID: 48185032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6acc63c2271b5ab58e168d0f0f662c6cb3653aac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974191"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="users-table-in-lync-server-2013"></a><span data-ttu-id="d2121-102">Lync Server 2013 中的 Users 表格</span><span class="sxs-lookup"><span data-stu-id="d2121-102">Users table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2121-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="d2121-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="d2121-104">[使用者] 資料表是支援表格。</span><span class="sxs-lookup"><span data-stu-id="d2121-104">The Users table is a supporting table.</span></span> <span data-ttu-id="d2121-105">資料表中的每一筆記錄都儲存有關在資料庫中有記錄的通話或會話中涉及之一個使用者的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d2121-105">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d2121-106">左欄</span><span class="sxs-lookup"><span data-stu-id="d2121-106">Column</span></span></th>
<th><span data-ttu-id="d2121-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="d2121-107">Data Type</span></span></th>
<th><span data-ttu-id="d2121-108">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="d2121-108">Key/Index</span></span></th>
<th><span data-ttu-id="d2121-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="d2121-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d2121-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="d2121-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="d2121-111">datetime</span><span class="sxs-lookup"><span data-stu-id="d2121-111">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d2121-112">內部使用的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="d2121-112">Time stamp for internal use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2121-113"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="d2121-113"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="d2121-114">int</span><span class="sxs-lookup"><span data-stu-id="d2121-114">int</span></span></p></td>
<td><p><span data-ttu-id="d2121-115">首選</span><span class="sxs-lookup"><span data-stu-id="d2121-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="d2121-116">標識此使用者的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="d2121-116">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2121-117"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="d2121-117"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="d2121-118">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="d2121-118">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d2121-119">使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="d2121-119">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2121-120"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="d2121-120"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="d2121-121">int</span><span class="sxs-lookup"><span data-stu-id="d2121-121">int</span></span></p></td>
<td><p><span data-ttu-id="d2121-122">外</span><span class="sxs-lookup"><span data-stu-id="d2121-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d2121-123">此使用者的租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="d2121-123">This user’s Tenant ID.</span></span> <span data-ttu-id="d2121-124">如需詳細資訊，請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中</a>的 [承租人] 資料表。</span><span class="sxs-lookup"><span data-stu-id="d2121-124">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2121-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="d2121-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="d2121-126">int</span><span class="sxs-lookup"><span data-stu-id="d2121-126">int</span></span></p></td>
<td><p><span data-ttu-id="d2121-127">外</span><span class="sxs-lookup"><span data-stu-id="d2121-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d2121-128">此使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="d2121-128">This user’s URI type.</span></span> <span data-ttu-id="d2121-129">如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</span><span class="sxs-lookup"><span data-stu-id="d2121-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

