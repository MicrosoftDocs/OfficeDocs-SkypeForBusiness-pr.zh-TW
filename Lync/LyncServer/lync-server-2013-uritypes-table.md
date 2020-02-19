---
title: 'Lync Server 2013: UriTypes 表格'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UriTypes table
ms:assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398587(v=OCS.15)
ms:contentKeyID: 48184553
ms.date: 06/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10b123caa837fbdc9bbea9fc8a524b47c4950822
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140876"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="uritypes-table-in-lync-server-2013"></a><span data-ttu-id="54921-102">Lync Server 2013 中的 UriTypes 表格</span><span class="sxs-lookup"><span data-stu-id="54921-102">UriTypes table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54921-103">_**主題上次修改日期：** 2015年-06-16_</span><span class="sxs-lookup"><span data-stu-id="54921-103">_**Topic Last Modified:** 2015-06-16_</span></span>

<span data-ttu-id="54921-104">UriTypes 表格包含不同在 Microsoft Lync Server 2013 中監視的統一資源識別元 （URI) 類型。</span><span class="sxs-lookup"><span data-stu-id="54921-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="54921-105">欄</span><span class="sxs-lookup"><span data-stu-id="54921-105">Column</span></span></th>
<th><span data-ttu-id="54921-106">資料類型</span><span class="sxs-lookup"><span data-stu-id="54921-106">Data Type</span></span></th>
<th><span data-ttu-id="54921-107">主索引鍵 /</span><span class="sxs-lookup"><span data-stu-id="54921-107">Key/Index</span></span></th>
<th><span data-ttu-id="54921-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="54921-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54921-109"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="54921-109"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="54921-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="54921-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="54921-111">主要</span><span class="sxs-lookup"><span data-stu-id="54921-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="54921-112">指派給 URI 類型的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="54921-112">Unique identifier assigned to a URI type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54921-113"><strong>UriType</strong></span><span class="sxs-lookup"><span data-stu-id="54921-113"><strong>UriType</strong></span></span></p></td>
<td><p><span data-ttu-id="54921-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="54921-114">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="54921-p101">不同 URI 類型的描述。允許值為：</span><span class="sxs-lookup"><span data-stu-id="54921-p101">Descriptions of the different URI types. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="54921-117">1 – 電話 Uri</span><span class="sxs-lookup"><span data-stu-id="54921-117">1 – Phone Uri</span></span></p></li>
<li><p><span data-ttu-id="54921-118">0 – 使用者 Uri</span><span class="sxs-lookup"><span data-stu-id="54921-118">0 – User Uri</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

