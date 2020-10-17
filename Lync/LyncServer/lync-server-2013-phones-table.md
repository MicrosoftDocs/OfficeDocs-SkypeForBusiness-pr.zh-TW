---
title: Lync Server 2013：電話表格
description: Lync Server 2013：電話表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Phones table
ms:assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425923(v=OCS.15)
ms:contentKeyID: 48183996
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c62fffecd2442b79aefde77eb037dca4bffc9d4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554809"
---
# <a name="phones-table-in-lync-server-2013"></a><span data-ttu-id="45782-103">Lync Server 2013 中的電話表</span><span class="sxs-lookup"><span data-stu-id="45782-103">Phones table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45782-104">_**主題上次修改日期：** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="45782-104">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="45782-105">電話系表是支援的表格。</span><span class="sxs-lookup"><span data-stu-id="45782-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="45782-106">資料表中的每一筆記錄都儲存在包含資料庫中記錄的 VoIP 通話中相關的一個電話號碼相關資訊。</span><span class="sxs-lookup"><span data-stu-id="45782-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45782-107">欄</span><span class="sxs-lookup"><span data-stu-id="45782-107">Column</span></span></th>
<th><span data-ttu-id="45782-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="45782-108">Data Type</span></span></th>
<th><span data-ttu-id="45782-109">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="45782-109">Key/Index</span></span></th>
<th><span data-ttu-id="45782-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="45782-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45782-111"><strong>PhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="45782-111"><strong>PhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="45782-112">int</span><span class="sxs-lookup"><span data-stu-id="45782-112">int</span></span></p></td>
<td><p><span data-ttu-id="45782-113">主要</span><span class="sxs-lookup"><span data-stu-id="45782-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="45782-114">用於識別此電話的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="45782-114">Unique number identifying this phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45782-115"><strong>PhoneUri</strong></span><span class="sxs-lookup"><span data-stu-id="45782-115"><strong>PhoneUri</strong></span></span></p></td>
<td><p><span data-ttu-id="45782-116">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="45782-116">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="45782-117">電話號碼。</span><span class="sxs-lookup"><span data-stu-id="45782-117">Phone number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45782-118"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="45782-118"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="45782-119">Datetime</span><span class="sxs-lookup"><span data-stu-id="45782-119">dateTime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="45782-120">僅供內部使用) 的時間戳記 (。</span><span class="sxs-lookup"><span data-stu-id="45782-120">Time stamp (for internal use only).</span></span></p>
<p><span data-ttu-id="45782-121">此欄位是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="45782-121">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

