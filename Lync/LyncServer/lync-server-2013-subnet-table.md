---
title: Lync Server 2013：Subnet 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Subnet table
ms:assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398582(v=OCS.15)
ms:contentKeyID: 48184544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20318d0ed2f487efccda81936b113044f75e2618
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976103"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="subnet-table-in-lync-server-2013"></a><span data-ttu-id="8dd91-102">Lync Server 2013 中的 Subnet 表格</span><span class="sxs-lookup"><span data-stu-id="8dd91-102">Subnet table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8dd91-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="8dd91-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="8dd91-104">子網資料表是支援表格。</span><span class="sxs-lookup"><span data-stu-id="8dd91-104">The Subnet table is a supporting table.</span></span> <span data-ttu-id="8dd91-105">每個記錄代表 [網路設定] 中定義的一個子網。</span><span class="sxs-lookup"><span data-stu-id="8dd91-105">Each record represents one subnet defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8dd91-106"><strong>左欄</strong></span><span class="sxs-lookup"><span data-stu-id="8dd91-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="8dd91-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="8dd91-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="8dd91-108"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="8dd91-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="8dd91-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="8dd91-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8dd91-110"><strong>SubnetIP</strong></span><span class="sxs-lookup"><span data-stu-id="8dd91-110"><strong>SubnetIP</strong></span></span></p></td>
<td><p><span data-ttu-id="8dd91-111">int</span><span class="sxs-lookup"><span data-stu-id="8dd91-111">int</span></span></p></td>
<td><p><span data-ttu-id="8dd91-112">主要、外部</span><span class="sxs-lookup"><span data-stu-id="8dd91-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="8dd91-113">子網 IP 的整數表示。</span><span class="sxs-lookup"><span data-stu-id="8dd91-113">Integer representation for the subnet IP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dd91-114"><strong>SubnetMask</strong></span><span class="sxs-lookup"><span data-stu-id="8dd91-114"><strong>SubnetMask</strong></span></span></p></td>
<td><p><span data-ttu-id="8dd91-115">int</span><span class="sxs-lookup"><span data-stu-id="8dd91-115">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8dd91-116">子網路遮罩。</span><span class="sxs-lookup"><span data-stu-id="8dd91-116">Subnet mask.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dd91-117"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="8dd91-117"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="8dd91-118">int</span><span class="sxs-lookup"><span data-stu-id="8dd91-118">int</span></span></p></td>
<td><p><span data-ttu-id="8dd91-119">外</span><span class="sxs-lookup"><span data-stu-id="8dd91-119">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8dd91-120">從<a href="lync-server-2013-usersite-table.md">Lync Server 2013 的 UserSite 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="8dd91-120">Referenced from the <a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dd91-121"><strong>SubnetDescription</strong></span><span class="sxs-lookup"><span data-stu-id="8dd91-121"><strong>SubnetDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="8dd91-122">Nvarchar （512）</span><span class="sxs-lookup"><span data-stu-id="8dd91-122">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8dd91-123">子網的描述。</span><span class="sxs-lookup"><span data-stu-id="8dd91-123">The description for the subnet.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

