---
title: Lync Server 2013： PayloadDescription 表格
description: Lync Server 2013： PayloadDescription 表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PayloadDescription table
ms:assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412971(v=OCS.15)
ms:contentKeyID: 48185353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90ba6b3b85060601487b5b6d0d8747c5fbfa2a9a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557359"
---
# <a name="payloaddescription-table-in-lync-server-2013"></a><span data-ttu-id="2c659-103">Lync Server 2013 中的 PayloadDescription 表格</span><span class="sxs-lookup"><span data-stu-id="2c659-103">PayloadDescription table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c659-104">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="2c659-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="2c659-105">PayloadDescription 表格是支援的表格。</span><span class="sxs-lookup"><span data-stu-id="2c659-105">The PayloadDescription table is a supporting table.</span></span> <span data-ttu-id="2c659-106">每筆記錄代表一個編解碼器，在音訊或視頻會話中使用。</span><span class="sxs-lookup"><span data-stu-id="2c659-106">Each record represents one Codec, which is used in an audio or video session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2c659-107"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="2c659-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="2c659-108"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="2c659-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="2c659-109"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="2c659-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="2c659-110"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="2c659-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2c659-111"><strong>PayloadDescriptionKey</strong></span><span class="sxs-lookup"><span data-stu-id="2c659-111"><strong>PayloadDescriptionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="2c659-112">int</span><span class="sxs-lookup"><span data-stu-id="2c659-112">int</span></span></p></td>
<td><p><span data-ttu-id="2c659-113">主要</span><span class="sxs-lookup"><span data-stu-id="2c659-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="2c659-114">識別編解碼器的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="2c659-114">Unique number identifying the Codec.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c659-115"><strong>PayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="2c659-115"><strong>PayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="2c659-116">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="2c659-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2c659-117">Unique</span><span class="sxs-lookup"><span data-stu-id="2c659-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="2c659-118">編解碼器名稱。</span><span class="sxs-lookup"><span data-stu-id="2c659-118">Codec name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

