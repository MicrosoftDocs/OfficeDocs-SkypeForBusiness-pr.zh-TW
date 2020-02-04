---
title: Lync Server 2013：User 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User table
ms:assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398505(v=OCS.15)
ms:contentKeyID: 48184437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8256dec91c93ca6e8f0fd3cfff65280a417324e4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744443"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-table-in-lync-server-2013"></a><span data-ttu-id="860ef-102">Lync Server 2013 中的 User 表格</span><span class="sxs-lookup"><span data-stu-id="860ef-102">User table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="860ef-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="860ef-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="860ef-104">[使用者] 資料表是一個支援資料表，可儲存已參與資料庫中記錄之會話的各種使用者清單。</span><span class="sxs-lookup"><span data-stu-id="860ef-104">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="860ef-105">資料表中的每一筆記錄代表一個使用者。</span><span class="sxs-lookup"><span data-stu-id="860ef-105">Each record in the table represents one user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="860ef-106"><strong>左欄</strong></span><span class="sxs-lookup"><span data-stu-id="860ef-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="860ef-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="860ef-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="860ef-108"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="860ef-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="860ef-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="860ef-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="860ef-110"><strong>UserKey</strong></span><span class="sxs-lookup"><span data-stu-id="860ef-110"><strong>UserKey</strong></span></span></p></td>
<td><p><span data-ttu-id="860ef-111">int</span><span class="sxs-lookup"><span data-stu-id="860ef-111">int</span></span></p></td>
<td><p><span data-ttu-id="860ef-112">首選</span><span class="sxs-lookup"><span data-stu-id="860ef-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="860ef-113">標識此使用者的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="860ef-113">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="860ef-114"><strong>URL</strong></span><span class="sxs-lookup"><span data-stu-id="860ef-114"><strong>URI</strong></span></span></p></td>
<td><p><span data-ttu-id="860ef-115">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="860ef-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="860ef-116">唯一</span><span class="sxs-lookup"><span data-stu-id="860ef-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="860ef-117">URI 字串。</span><span class="sxs-lookup"><span data-stu-id="860ef-117">URI string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="860ef-118"><strong>URIType</strong></span><span class="sxs-lookup"><span data-stu-id="860ef-118"><strong>URIType</strong></span></span></p></td>
<td><p><span data-ttu-id="860ef-119">int</span><span class="sxs-lookup"><span data-stu-id="860ef-119">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="860ef-120">1是未知的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="860ef-120">1 is unknown URI type.</span></span></p>
<p><span data-ttu-id="860ef-121">2是使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="860ef-121">2 is user URI.</span></span></p>
<p><span data-ttu-id="860ef-122">4是會議 URI。</span><span class="sxs-lookup"><span data-stu-id="860ef-122">4 is conference URI.</span></span></p>
<p><span data-ttu-id="860ef-123">8是電話 URI。</span><span class="sxs-lookup"><span data-stu-id="860ef-123">8 is phone URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="860ef-124"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="860ef-124"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="860ef-125">int</span><span class="sxs-lookup"><span data-stu-id="860ef-125">int</span></span></p></td>
<td><p><span data-ttu-id="860ef-126">外</span><span class="sxs-lookup"><span data-stu-id="860ef-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="860ef-127">使用者的租使用者，從租使用者資料表參考。</span><span class="sxs-lookup"><span data-stu-id="860ef-127">Tenant of the user, referenced from tenant table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="860ef-128"><strong>LastPoorCallTime</strong></span><span class="sxs-lookup"><span data-stu-id="860ef-128"><strong>LastPoorCallTime</strong></span></span></p></td>
<td><p><span data-ttu-id="860ef-129">datetime</span><span class="sxs-lookup"><span data-stu-id="860ef-129">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="860ef-130">當使用者的語音通話不佳時，請使用最新的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="860ef-130">Latest time stamp when the user had a poor audio call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="860ef-131"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="860ef-131"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="860ef-132">datetime</span><span class="sxs-lookup"><span data-stu-id="860ef-132">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="860ef-133">僅供內部使用。</span><span class="sxs-lookup"><span data-stu-id="860ef-133">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

