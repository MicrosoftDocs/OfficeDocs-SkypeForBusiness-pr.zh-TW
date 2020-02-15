---
title: Lync Server 2013： 使用者表格
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
ms.openlocfilehash: 98a34028ebec126c8d5fc5ec838a22180ccb0fa7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-table-in-lync-server-2013"></a><span data-ttu-id="f6e44-102">Lync Server 2013 中的使用者表格</span><span class="sxs-lookup"><span data-stu-id="f6e44-102">User table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6e44-103">_**主題上次修改日期：** 2012年-10-02_</span><span class="sxs-lookup"><span data-stu-id="f6e44-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="f6e44-p101">User 表格是一種支援資料表，儲存資料庫中所記錄的工作階段之各參與使用者的清單。表格中的每筆記錄代表一位使用者。</span><span class="sxs-lookup"><span data-stu-id="f6e44-p101">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database. Each record in the table represents one user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f6e44-106"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="f6e44-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f6e44-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="f6e44-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f6e44-108"><strong>主索引鍵 /</strong></span><span class="sxs-lookup"><span data-stu-id="f6e44-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f6e44-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="f6e44-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f6e44-110"><strong>UserKey</strong></span><span class="sxs-lookup"><span data-stu-id="f6e44-110"><strong>UserKey</strong></span></span></p></td>
<td><p><span data-ttu-id="f6e44-111">int</span><span class="sxs-lookup"><span data-stu-id="f6e44-111">int</span></span></p></td>
<td><p><span data-ttu-id="f6e44-112">主要</span><span class="sxs-lookup"><span data-stu-id="f6e44-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="f6e44-113">用於識別此使用者的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="f6e44-113">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6e44-114"><strong>URI</strong></span><span class="sxs-lookup"><span data-stu-id="f6e44-114"><strong>URI</strong></span></span></p></td>
<td><p><span data-ttu-id="f6e44-115">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="f6e44-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f6e44-116">Unique</span><span class="sxs-lookup"><span data-stu-id="f6e44-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="f6e44-117">URI 字串。</span><span class="sxs-lookup"><span data-stu-id="f6e44-117">URI string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6e44-118"><strong>URIType</strong></span><span class="sxs-lookup"><span data-stu-id="f6e44-118"><strong>URIType</strong></span></span></p></td>
<td><p><span data-ttu-id="f6e44-119">int</span><span class="sxs-lookup"><span data-stu-id="f6e44-119">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f6e44-120">1 是未知的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="f6e44-120">1 is unknown URI type.</span></span></p>
<p><span data-ttu-id="f6e44-121">2 是使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="f6e44-121">2 is user URI.</span></span></p>
<p><span data-ttu-id="f6e44-122">4 是會議 URI。</span><span class="sxs-lookup"><span data-stu-id="f6e44-122">4 is conference URI.</span></span></p>
<p><span data-ttu-id="f6e44-123">8 是電話 URI。</span><span class="sxs-lookup"><span data-stu-id="f6e44-123">8 is phone URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6e44-124"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="f6e44-124"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="f6e44-125">int</span><span class="sxs-lookup"><span data-stu-id="f6e44-125">int</span></span></p></td>
<td><p><span data-ttu-id="f6e44-126">Foreign</span><span class="sxs-lookup"><span data-stu-id="f6e44-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f6e44-127">使用者的承租人，參考來源：Tenant 表格。</span><span class="sxs-lookup"><span data-stu-id="f6e44-127">Tenant of the user, referenced from tenant table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6e44-128"><strong>LastPoorCallTime</strong></span><span class="sxs-lookup"><span data-stu-id="f6e44-128"><strong>LastPoorCallTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f6e44-129">datetime</span><span class="sxs-lookup"><span data-stu-id="f6e44-129">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f6e44-130">最近一次使用者通話音訊品質不佳的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="f6e44-130">Latest time stamp when the user had a poor audio call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6e44-131"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="f6e44-131"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="f6e44-132">datetime</span><span class="sxs-lookup"><span data-stu-id="f6e44-132">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f6e44-133">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="f6e44-133">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

