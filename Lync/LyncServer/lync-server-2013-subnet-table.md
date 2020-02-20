---
title: 'Lync Server 2013: Subnet 表格'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Subnet table
ms:assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398582(v=OCS.15)
ms:contentKeyID: 48184544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9cdf1ded3a63d790db78476b91a458d07921200a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142489"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="subnet-table-in-lync-server-2013"></a><span data-ttu-id="0833b-102">Lync Server 2013 中的子網路表格</span><span class="sxs-lookup"><span data-stu-id="0833b-102">Subnet table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0833b-103">_**主題上次修改日期：** 2012年-10-02_</span><span class="sxs-lookup"><span data-stu-id="0833b-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="0833b-p101">Subnet 表格是一種支援資料表。每筆記錄代表在網路組態設定中定義的一個子網路。</span><span class="sxs-lookup"><span data-stu-id="0833b-p101">The Subnet table is a supporting table. Each record represents one subnet defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0833b-106"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="0833b-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="0833b-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="0833b-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="0833b-108"><strong>主索引鍵 /</strong></span><span class="sxs-lookup"><span data-stu-id="0833b-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="0833b-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="0833b-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0833b-110"><strong>SubnetIP</strong></span><span class="sxs-lookup"><span data-stu-id="0833b-110"><strong>SubnetIP</strong></span></span></p></td>
<td><p><span data-ttu-id="0833b-111">int</span><span class="sxs-lookup"><span data-stu-id="0833b-111">int</span></span></p></td>
<td><p><span data-ttu-id="0833b-112">主要、外部</span><span class="sxs-lookup"><span data-stu-id="0833b-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="0833b-113">子網路 IP 的整數表示。</span><span class="sxs-lookup"><span data-stu-id="0833b-113">Integer representation for the subnet IP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0833b-114"><strong>子網路遮罩</strong></span><span class="sxs-lookup"><span data-stu-id="0833b-114"><strong>SubnetMask</strong></span></span></p></td>
<td><p><span data-ttu-id="0833b-115">int</span><span class="sxs-lookup"><span data-stu-id="0833b-115">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0833b-116">子網路遮罩。</span><span class="sxs-lookup"><span data-stu-id="0833b-116">Subnet mask.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0833b-117"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="0833b-117"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="0833b-118">int</span><span class="sxs-lookup"><span data-stu-id="0833b-118">int</span></span></p></td>
<td><p><span data-ttu-id="0833b-119">Foreign</span><span class="sxs-lookup"><span data-stu-id="0833b-119">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0833b-120">參考來源<a href="lync-server-2013-usersite-table.md">: UserSite table Lync Server 2013 中</a>。</span><span class="sxs-lookup"><span data-stu-id="0833b-120">Referenced from the <a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0833b-121"><strong>SubnetDescription</strong></span><span class="sxs-lookup"><span data-stu-id="0833b-121"><strong>SubnetDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="0833b-122">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="0833b-122">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0833b-123">子網路的描述。</span><span class="sxs-lookup"><span data-stu-id="0833b-123">The description for the subnet.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

