---
title: Lync Server 2013： IPAddress 表格
description: Lync Server 2013： IPAddress 表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IPAddress table
ms:assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205077(v=OCS.15)
ms:contentKeyID: 48184771
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d987281fc310a3a179fa99f2aae51b0764349dd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575009"
---
# <a name="ipaddress-table-in-lync-server-2013"></a><span data-ttu-id="dee07-103">Lync Server 2013 中的 IPAddress 表格</span><span class="sxs-lookup"><span data-stu-id="dee07-103">IPAddress table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dee07-104">_**主題上次修改日期：** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="dee07-104">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="dee07-105">IPAddress 表會將 IP 位址對應至在經驗品質資料庫中其他地方使用的唯一 IP 位址識別碼。</span><span class="sxs-lookup"><span data-stu-id="dee07-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="dee07-106">此表格已引進 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="dee07-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dee07-107"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="dee07-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="dee07-108"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="dee07-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="dee07-109"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="dee07-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="dee07-110"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="dee07-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dee07-111"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="dee07-111"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="dee07-112">int</span><span class="sxs-lookup"><span data-stu-id="dee07-112">int</span></span></p></td>
<td><p><span data-ttu-id="dee07-113">主要</span><span class="sxs-lookup"><span data-stu-id="dee07-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="dee07-114">指定之 IP 位址的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="dee07-114">Unique identifier for the specified IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dee07-115"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="dee07-115"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="dee07-116">Varchar (50) </span><span class="sxs-lookup"><span data-stu-id="dee07-116">varchar(50)</span></span></p></td>
<td><p><span data-ttu-id="dee07-117">Unique</span><span class="sxs-lookup"><span data-stu-id="dee07-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="dee07-118">唯一的 IP 位址 (例如，189.168.1.1) 會對應至 IpAddressKey。</span><span class="sxs-lookup"><span data-stu-id="dee07-118">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="dee07-119">這可以是 IPv4 或 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="dee07-119">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

