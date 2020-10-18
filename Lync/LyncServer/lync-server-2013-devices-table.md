---
title: Lync Server 2013：裝置表格
description: Lync Server 2013：裝置表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Devices table
ms:assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398351(v=OCS.15)
ms:contentKeyID: 48184169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 763e1788e2874f9f9831c089ffe8fa077621b030
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576239"
---
# <a name="devices-table-in-lync-server-2013"></a><span data-ttu-id="b2559-103">Lync Server 2013 中的 [裝置] 表格</span><span class="sxs-lookup"><span data-stu-id="b2559-103">Devices table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2559-104">_**主題上次修改日期：** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="b2559-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="b2559-p101">Devices 表格是一種支援資料表。每筆記錄儲存一部裝置 (電話機) 的資訊。</span><span class="sxs-lookup"><span data-stu-id="b2559-p101">The Devices table is a supporting table. Each record stores information about one device (desk phone).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2559-107">欄</span><span class="sxs-lookup"><span data-stu-id="b2559-107">Column</span></span></th>
<th><span data-ttu-id="b2559-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="b2559-108">Data Type</span></span></th>
<th><span data-ttu-id="b2559-109">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="b2559-109">Key/Index</span></span></th>
<th><span data-ttu-id="b2559-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="b2559-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2559-111"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="b2559-111"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="b2559-112">int</span><span class="sxs-lookup"><span data-stu-id="b2559-112">int</span></span></p></td>
<td><p><span data-ttu-id="b2559-113">主要</span><span class="sxs-lookup"><span data-stu-id="b2559-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="b2559-114">用於識別此硬體版本的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="b2559-114">Unique number identifying this hardware version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2559-115"><strong>ManufacturerId</strong></span><span class="sxs-lookup"><span data-stu-id="b2559-115"><strong>ManufacturerId</strong></span></span></p></td>
<td><p><span data-ttu-id="b2559-116">int</span><span class="sxs-lookup"><span data-stu-id="b2559-116">int</span></span></p></td>
<td><p><span data-ttu-id="b2559-117">Foreign</span><span class="sxs-lookup"><span data-stu-id="b2559-117">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b2559-118">此裝置的製造商。</span><span class="sxs-lookup"><span data-stu-id="b2559-118">Manufacturer of this device.</span></span> <span data-ttu-id="b2559-119">如需詳細資訊，請參閱 <a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 中的製造商表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="b2559-119">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2559-120"><strong>HardwareVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="b2559-120"><strong>HardwareVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="b2559-121">int</span><span class="sxs-lookup"><span data-stu-id="b2559-121">int</span></span></p></td>
<td><p><span data-ttu-id="b2559-122">Foreign</span><span class="sxs-lookup"><span data-stu-id="b2559-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b2559-123">此裝置的硬體版本。</span><span class="sxs-lookup"><span data-stu-id="b2559-123">Hardware version of this device.</span></span> <span data-ttu-id="b2559-124">如需詳細資訊，請參閱 <a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 中的 HardwareVersions 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="b2559-124">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2559-125"><strong>MacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="b2559-125"><strong>MacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="b2559-126">Bigint</span><span class="sxs-lookup"><span data-stu-id="b2559-126">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b2559-127">MAC 位址</span><span class="sxs-lookup"><span data-stu-id="b2559-127">MAC Address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

