---
title: Lync Server 2013：UriTypes 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UriTypes table
ms:assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398587(v=OCS.15)
ms:contentKeyID: 48184553
ms.date: 06/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 916f4e6b06bc8fab484d29f7fe88170025de01d2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974942"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="uritypes-table-in-lync-server-2013"></a><span data-ttu-id="5d2af-102">Lync Server 2013 中的 UriTypes 表格</span><span class="sxs-lookup"><span data-stu-id="5d2af-102">UriTypes table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d2af-103">_**主題上次修改日期：** 2015-06-16_</span><span class="sxs-lookup"><span data-stu-id="5d2af-103">_**Topic Last Modified:** 2015-06-16_</span></span>

<span data-ttu-id="5d2af-104">UriTypes 資料表包含在 Microsoft Lync Server 2013 中監控的不同 URI （統一資源識別項）類型。</span><span class="sxs-lookup"><span data-stu-id="5d2af-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5d2af-105">左欄</span><span class="sxs-lookup"><span data-stu-id="5d2af-105">Column</span></span></th>
<th><span data-ttu-id="5d2af-106">資料類型</span><span class="sxs-lookup"><span data-stu-id="5d2af-106">Data Type</span></span></th>
<th><span data-ttu-id="5d2af-107">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="5d2af-107">Key/Index</span></span></th>
<th><span data-ttu-id="5d2af-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="5d2af-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d2af-109"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="5d2af-109"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="5d2af-110">Tinyint</span><span class="sxs-lookup"><span data-stu-id="5d2af-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5d2af-111">首選</span><span class="sxs-lookup"><span data-stu-id="5d2af-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="5d2af-112">指派給 URI 類型的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="5d2af-112">Unique identifier assigned to a URI type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d2af-113"><strong>UriType</strong></span><span class="sxs-lookup"><span data-stu-id="5d2af-113"><strong>UriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5d2af-114">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="5d2af-114">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d2af-115">不同 URI 類型的描述。</span><span class="sxs-lookup"><span data-stu-id="5d2af-115">Descriptions of the different URI types.</span></span> <span data-ttu-id="5d2af-116">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="5d2af-116">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="5d2af-117">1–電話 Uri</span><span class="sxs-lookup"><span data-stu-id="5d2af-117">1 – Phone Uri</span></span></p></li>
<li><p><span data-ttu-id="5d2af-118">0–使用者 Uri</span><span class="sxs-lookup"><span data-stu-id="5d2af-118">0 – User Uri</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

