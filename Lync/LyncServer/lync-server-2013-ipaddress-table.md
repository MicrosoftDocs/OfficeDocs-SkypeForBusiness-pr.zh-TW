---
title: Lync Server 2013： IPAddress 表
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
ms.openlocfilehash: 6344319fbdf581a5e51a1f61e141833910e9e29f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733463"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipaddress-table-in-lync-server-2013"></a><span data-ttu-id="e1bb5-102">Lync Server 2013 中的 [IPAddress] 表格</span><span class="sxs-lookup"><span data-stu-id="e1bb5-102">IPAddress table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1bb5-103">_**主題上次修改日期：** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="e1bb5-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="e1bb5-104">[IPAddress] 表格會將 IP 位址對應至 [經驗] 資料庫中其他位置使用的唯一 IP 位址識別碼。</span><span class="sxs-lookup"><span data-stu-id="e1bb5-104">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="e1bb5-105">此表格是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="e1bb5-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e1bb5-106"><strong>左欄</strong></span><span class="sxs-lookup"><span data-stu-id="e1bb5-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e1bb5-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="e1bb5-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e1bb5-108"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="e1bb5-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e1bb5-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="e1bb5-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e1bb5-110"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="e1bb5-110"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="e1bb5-111">int</span><span class="sxs-lookup"><span data-stu-id="e1bb5-111">int</span></span></p></td>
<td><p><span data-ttu-id="e1bb5-112">首選</span><span class="sxs-lookup"><span data-stu-id="e1bb5-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="e1bb5-113">指定 IP 位址的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="e1bb5-113">Unique identifier for the specified IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1bb5-114"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="e1bb5-114"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="e1bb5-115">Varchar （50）</span><span class="sxs-lookup"><span data-stu-id="e1bb5-115">varchar(50)</span></span></p></td>
<td><p><span data-ttu-id="e1bb5-116">唯一</span><span class="sxs-lookup"><span data-stu-id="e1bb5-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="e1bb5-117">對應至 IpAddressKey 的唯一 IP 位址（例如，189.168.1.1）。</span><span class="sxs-lookup"><span data-stu-id="e1bb5-117">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="e1bb5-118">這可能是 IPv4 或 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="e1bb5-118">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

