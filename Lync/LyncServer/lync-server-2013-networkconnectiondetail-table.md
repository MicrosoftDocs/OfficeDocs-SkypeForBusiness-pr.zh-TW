---
title: 'Lync Server 2013: NetworkConnectionDetail 表'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: NetworkConnectionDetail table
ms:assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205185(v=OCS.15)
ms:contentKeyID: 48185170
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 784e229ee16bfee0e9e828f1df7f06a98e898eb4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043855"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="networkconnectiondetail-table-in-lync-server-2013"></a><span data-ttu-id="d408e-102">Lync Server 2013 中的 NetworkConnectionDetail 表</span><span class="sxs-lookup"><span data-stu-id="d408e-102">NetworkConnectionDetail table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d408e-103">_**主題上次修改日期：** 2012年-10-02_</span><span class="sxs-lookup"><span data-stu-id="d408e-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="d408e-104">NetworkConnectionDetail 表將網路連線類型對應至用在經驗品質資料庫其他地方的網路連線識別碼。</span><span class="sxs-lookup"><span data-stu-id="d408e-104">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="d408e-105">Microsoft Lync Server 2013 中已採用此表格。</span><span class="sxs-lookup"><span data-stu-id="d408e-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d408e-106"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="d408e-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d408e-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="d408e-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d408e-108"><strong>主索引鍵 /</strong></span><span class="sxs-lookup"><span data-stu-id="d408e-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d408e-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="d408e-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d408e-110"><strong>NetworkConnectionDetailKey</strong></span><span class="sxs-lookup"><span data-stu-id="d408e-110"><strong>NetworkConnectionDetailKey</strong></span></span></p></td>
<td><p><span data-ttu-id="d408e-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="d408e-111">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d408e-112">主要</span><span class="sxs-lookup"><span data-stu-id="d408e-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="d408e-113">網路連線類型的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="d408e-113">Unique identifier for the network connection type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d408e-114"><strong>NetworkConnectionDetail</strong></span><span class="sxs-lookup"><span data-stu-id="d408e-114"><strong>NetworkConnectionDetail</strong></span></span></p></td>
<td><p><span data-ttu-id="d408e-115">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="d408e-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d408e-116">Unique</span><span class="sxs-lookup"><span data-stu-id="d408e-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="d408e-117">會對應至 NetworkConnectionDetailKey 的網路連線類型。</span><span class="sxs-lookup"><span data-stu-id="d408e-117">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="d408e-118">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="d408e-118">Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="d408e-119">0-有線</span><span class="sxs-lookup"><span data-stu-id="d408e-119">0 -- Wired</span></span></p></li>
<li><p><span data-ttu-id="d408e-120">1--WiFi</span><span class="sxs-lookup"><span data-stu-id="d408e-120">1 -- WiFi</span></span></p></li>
<li><p><span data-ttu-id="d408e-121">2--乙太網路</span><span class="sxs-lookup"><span data-stu-id="d408e-121">2 -- Ethernet</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

