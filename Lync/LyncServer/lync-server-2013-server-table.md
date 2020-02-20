---
title: 'Lync Server 2013: Server 表格'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server table
ms:assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398801(v=OCS.15)
ms:contentKeyID: 48184890
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 399e759709acc3ca5b975a5beb8f3405e92bd605
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143939"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-table-in-lync-server-2013"></a><span data-ttu-id="4b57d-102">Lync Server 2013 中的 server 表格</span><span class="sxs-lookup"><span data-stu-id="4b57d-102">Server table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b57d-103">_**主題上次修改日期：** 2012年-10-02_</span><span class="sxs-lookup"><span data-stu-id="4b57d-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="4b57d-104">伺服器表格是一種支援資料表。</span><span class="sxs-lookup"><span data-stu-id="4b57d-104">The Server table is a supporting table.</span></span> <span data-ttu-id="4b57d-105">每筆記錄代表一部伺服器。</span><span class="sxs-lookup"><span data-stu-id="4b57d-105">Each record represents one server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4b57d-106"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="4b57d-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="4b57d-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="4b57d-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="4b57d-108"><strong>主索引鍵 /</strong></span><span class="sxs-lookup"><span data-stu-id="4b57d-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="4b57d-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="4b57d-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b57d-110"><strong>ServerKey</strong></span><span class="sxs-lookup"><span data-stu-id="4b57d-110"><strong>ServerKey</strong></span></span></p></td>
<td><p><span data-ttu-id="4b57d-111">int</span><span class="sxs-lookup"><span data-stu-id="4b57d-111">int</span></span></p></td>
<td><p><span data-ttu-id="4b57d-112">主要</span><span class="sxs-lookup"><span data-stu-id="4b57d-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="4b57d-113">識別伺服器的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="4b57d-113">Unique number identifying the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b57d-114"><strong>FQDNOrIP</strong></span><span class="sxs-lookup"><span data-stu-id="4b57d-114"><strong>FQDNOrIP</strong></span></span></p></td>
<td><p><span data-ttu-id="4b57d-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4b57d-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4b57d-116">index</span><span class="sxs-lookup"><span data-stu-id="4b57d-116">index</span></span></p></td>
<td><p><span data-ttu-id="4b57d-117">MAC 位址字串。</span><span class="sxs-lookup"><span data-stu-id="4b57d-117">MAC address string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b57d-118"><strong>ServerType</strong></span><span class="sxs-lookup"><span data-stu-id="4b57d-118"><strong>ServerType</strong></span></span></p></td>
<td><p><span data-ttu-id="4b57d-119">int</span><span class="sxs-lookup"><span data-stu-id="4b57d-119">int</span></span></p></td>
<td><p><span data-ttu-id="4b57d-120">Foreign</span><span class="sxs-lookup"><span data-stu-id="4b57d-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4b57d-121">1： 中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="4b57d-121">1: Mediation Server</span></span></p>
<p><span data-ttu-id="4b57d-122">2: A / V Conferencing Server16394: A / V Edge service32769: Gateway</span><span class="sxs-lookup"><span data-stu-id="4b57d-122">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b57d-123"><strong>PoolName</strong></span><span class="sxs-lookup"><span data-stu-id="4b57d-123"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="4b57d-124">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="4b57d-124">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4b57d-125">伺服器所屬的集區。</span><span class="sxs-lookup"><span data-stu-id="4b57d-125">Pool the server belongs to.</span></span> <span data-ttu-id="4b57d-126">僅適用於 A / V 會議伺服器。</span><span class="sxs-lookup"><span data-stu-id="4b57d-126">Only applicable for the A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b57d-127"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="4b57d-127"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="4b57d-128">datetime</span><span class="sxs-lookup"><span data-stu-id="4b57d-128">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4b57d-129">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="4b57d-129">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

