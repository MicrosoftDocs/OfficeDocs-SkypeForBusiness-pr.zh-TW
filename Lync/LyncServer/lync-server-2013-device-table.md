---
title: Lync Server 2013： Device 表格
description: Lync Server 2013： Device table。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device table
ms:assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398930(v=OCS.15)
ms:contentKeyID: 48185544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46de64a49eace52d62cbd6384fcae680b5c511b9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575639"
---
# <a name="device-table-in-lync-server-2013"></a><span data-ttu-id="a8d84-103">Lync Server 2013 中的裝置表格</span><span class="sxs-lookup"><span data-stu-id="a8d84-103">Device table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8d84-104">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="a8d84-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="a8d84-105">Device 表是一種支援資料表，可儲存各種捕獲或呈現裝置的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a8d84-105">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="a8d84-106">資料表中的每一筆記錄都代表一個裝置。</span><span class="sxs-lookup"><span data-stu-id="a8d84-106">Each record in the table represents one device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a8d84-107"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="a8d84-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="a8d84-108"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="a8d84-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="a8d84-109"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="a8d84-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="a8d84-110"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="a8d84-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a8d84-111"><strong>DeviceKey</strong></span><span class="sxs-lookup"><span data-stu-id="a8d84-111"><strong>DeviceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="a8d84-112">int</span><span class="sxs-lookup"><span data-stu-id="a8d84-112">int</span></span></p></td>
<td><p><span data-ttu-id="a8d84-113">主要</span><span class="sxs-lookup"><span data-stu-id="a8d84-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="a8d84-114">用於識別此裝置的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="a8d84-114">Unique number identifying this device.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8d84-115"><strong>DeviceName</strong></span><span class="sxs-lookup"><span data-stu-id="a8d84-115"><strong>DeviceName</strong></span></span></p></td>
<td><p><span data-ttu-id="a8d84-116">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="a8d84-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a8d84-117">DeviceName + DeviceType 是唯一的</span><span class="sxs-lookup"><span data-stu-id="a8d84-117">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="a8d84-118">裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="a8d84-118">Device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a8d84-119"><strong>DeviceType</strong></span><span class="sxs-lookup"><span data-stu-id="a8d84-119"><strong>DeviceType</strong></span></span></p></td>
<td><p><span data-ttu-id="a8d84-120">位</span><span class="sxs-lookup"><span data-stu-id="a8d84-120">bit</span></span></p></td>
<td><p><span data-ttu-id="a8d84-121">DeviceName + DeviceType 是唯一的</span><span class="sxs-lookup"><span data-stu-id="a8d84-121">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="a8d84-122">裝置類型。</span><span class="sxs-lookup"><span data-stu-id="a8d84-122">Device type.</span></span> <span data-ttu-id="a8d84-123">1是捕獲裝置，0代表呈現裝置。</span><span class="sxs-lookup"><span data-stu-id="a8d84-123">1 is a capture device, 0 is a render device.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

