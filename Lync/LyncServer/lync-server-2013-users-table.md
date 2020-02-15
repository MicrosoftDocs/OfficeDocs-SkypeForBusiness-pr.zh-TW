---
title: 'Lync Server 2013: Users 表格'
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
ms.openlocfilehash: 67663afbd9e5b61b1b24478e003db91c5be511e3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046056"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="users-table-in-lync-server-2013"></a><span data-ttu-id="82aee-102">Lync Server 2013 中的使用者表格</span><span class="sxs-lookup"><span data-stu-id="82aee-102">Users table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82aee-103">_**主題上次修改日期：** 2012年-09-28_</span><span class="sxs-lookup"><span data-stu-id="82aee-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="82aee-104">Users 表格是一種支援資料表。</span><span class="sxs-lookup"><span data-stu-id="82aee-104">The Users table is a supporting table.</span></span> <span data-ttu-id="82aee-105">表格中的每一筆記錄的通話或資料庫中擁有記錄的工作階段中儲存一位使用者的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="82aee-105">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="82aee-106">欄</span><span class="sxs-lookup"><span data-stu-id="82aee-106">Column</span></span></th>
<th><span data-ttu-id="82aee-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="82aee-107">Data Type</span></span></th>
<th><span data-ttu-id="82aee-108">主索引鍵 /</span><span class="sxs-lookup"><span data-stu-id="82aee-108">Key/Index</span></span></th>
<th><span data-ttu-id="82aee-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="82aee-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82aee-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="82aee-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="82aee-111">datetime</span><span class="sxs-lookup"><span data-stu-id="82aee-111">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="82aee-112">供內部使用的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="82aee-112">Time stamp for internal use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82aee-113"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="82aee-113"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="82aee-114">int</span><span class="sxs-lookup"><span data-stu-id="82aee-114">int</span></span></p></td>
<td><p><span data-ttu-id="82aee-115">主要</span><span class="sxs-lookup"><span data-stu-id="82aee-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="82aee-116">用於識別此使用者的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="82aee-116">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82aee-117"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="82aee-117"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="82aee-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="82aee-118">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="82aee-119">使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="82aee-119">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82aee-120"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="82aee-120"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="82aee-121">int</span><span class="sxs-lookup"><span data-stu-id="82aee-121">int</span></span></p></td>
<td><p><span data-ttu-id="82aee-122">Foreign</span><span class="sxs-lookup"><span data-stu-id="82aee-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="82aee-123">此使用者的租用戶識別碼。</span><span class="sxs-lookup"><span data-stu-id="82aee-123">This user’s Tenant ID.</span></span> <span data-ttu-id="82aee-124">請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租用戶表</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="82aee-124">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82aee-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="82aee-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="82aee-126">int</span><span class="sxs-lookup"><span data-stu-id="82aee-126">int</span></span></p></td>
<td><p><span data-ttu-id="82aee-127">Foreign</span><span class="sxs-lookup"><span data-stu-id="82aee-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="82aee-128">此使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="82aee-128">This user’s URI type.</span></span> <span data-ttu-id="82aee-129">請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="82aee-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

