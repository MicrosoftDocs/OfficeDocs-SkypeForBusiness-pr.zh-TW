---
title: Lync Server 2013：使用者表格
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
ms.openlocfilehash: ed3f2372621b2b098a6b235d1bdc151ddac054bf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530160"
---
# <a name="user-table-in-lync-server-2013"></a><span data-ttu-id="35d0d-102">Lync Server 2013 中的使用者表格</span><span class="sxs-lookup"><span data-stu-id="35d0d-102">User table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35d0d-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="35d0d-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="35d0d-p101">User 表格是一種支援資料表，儲存資料庫中所記錄的工作階段之各參與使用者的清單。表格中的每筆記錄代表一位使用者。</span><span class="sxs-lookup"><span data-stu-id="35d0d-p101">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database. Each record in the table represents one user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="35d0d-106"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="35d0d-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="35d0d-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="35d0d-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="35d0d-108"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="35d0d-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="35d0d-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="35d0d-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="35d0d-110"><strong>UserKey</strong></span><span class="sxs-lookup"><span data-stu-id="35d0d-110"><strong>UserKey</strong></span></span></p></td>
<td><p><span data-ttu-id="35d0d-111">int</span><span class="sxs-lookup"><span data-stu-id="35d0d-111">int</span></span></p></td>
<td><p><span data-ttu-id="35d0d-112">主要</span><span class="sxs-lookup"><span data-stu-id="35d0d-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="35d0d-113">用於識別此使用者的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="35d0d-113">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35d0d-114"><strong>URI</strong></span><span class="sxs-lookup"><span data-stu-id="35d0d-114"><strong>URI</strong></span></span></p></td>
<td><p><span data-ttu-id="35d0d-115">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="35d0d-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="35d0d-116">Unique</span><span class="sxs-lookup"><span data-stu-id="35d0d-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="35d0d-117">URI 字串。</span><span class="sxs-lookup"><span data-stu-id="35d0d-117">URI string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35d0d-118"><strong>URIType</strong></span><span class="sxs-lookup"><span data-stu-id="35d0d-118"><strong>URIType</strong></span></span></p></td>
<td><p><span data-ttu-id="35d0d-119">int</span><span class="sxs-lookup"><span data-stu-id="35d0d-119">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="35d0d-120">1 是未知的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="35d0d-120">1 is unknown URI type.</span></span></p>
<p><span data-ttu-id="35d0d-121">2 是使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="35d0d-121">2 is user URI.</span></span></p>
<p><span data-ttu-id="35d0d-122">4 是會議 URI。</span><span class="sxs-lookup"><span data-stu-id="35d0d-122">4 is conference URI.</span></span></p>
<p><span data-ttu-id="35d0d-123">8 是電話 URI。</span><span class="sxs-lookup"><span data-stu-id="35d0d-123">8 is phone URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35d0d-124"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="35d0d-124"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="35d0d-125">int</span><span class="sxs-lookup"><span data-stu-id="35d0d-125">int</span></span></p></td>
<td><p><span data-ttu-id="35d0d-126">Foreign</span><span class="sxs-lookup"><span data-stu-id="35d0d-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="35d0d-127">使用者的承租人，參考來源：Tenant 表格。</span><span class="sxs-lookup"><span data-stu-id="35d0d-127">Tenant of the user, referenced from tenant table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35d0d-128"><strong>LastPoorCallTime</strong></span><span class="sxs-lookup"><span data-stu-id="35d0d-128"><strong>LastPoorCallTime</strong></span></span></p></td>
<td><p><span data-ttu-id="35d0d-129">datetime</span><span class="sxs-lookup"><span data-stu-id="35d0d-129">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="35d0d-130">最近一次使用者通話音訊品質不佳的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="35d0d-130">Latest time stamp when the user had a poor audio call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35d0d-131"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="35d0d-131"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="35d0d-132">datetime</span><span class="sxs-lookup"><span data-stu-id="35d0d-132">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="35d0d-133">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="35d0d-133">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

