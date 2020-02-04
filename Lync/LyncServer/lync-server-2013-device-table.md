---
title: Lync Server 2013：Device 表格
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
ms.openlocfilehash: 7fd06db1bd429526826962d5c3ad098642a3a42d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762411"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-table-in-lync-server-2013"></a><span data-ttu-id="a2f0f-102">Lync Server 2013 中的 Device 表格</span><span class="sxs-lookup"><span data-stu-id="a2f0f-102">Device table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2f0f-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="a2f0f-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="a2f0f-104">Device 資料表是一個支援資料表，可儲存各種捕獲或轉譯裝置的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a2f0f-104">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="a2f0f-105">資料表中的每一筆記錄代表一個裝置。</span><span class="sxs-lookup"><span data-stu-id="a2f0f-105">Each record in the table represents one device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a2f0f-106"><strong>左欄</strong></span><span class="sxs-lookup"><span data-stu-id="a2f0f-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="a2f0f-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="a2f0f-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="a2f0f-108"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="a2f0f-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="a2f0f-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="a2f0f-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2f0f-110"><strong>DeviceKey</strong></span><span class="sxs-lookup"><span data-stu-id="a2f0f-110"><strong>DeviceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="a2f0f-111">int</span><span class="sxs-lookup"><span data-stu-id="a2f0f-111">int</span></span></p></td>
<td><p><span data-ttu-id="a2f0f-112">首選</span><span class="sxs-lookup"><span data-stu-id="a2f0f-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="a2f0f-113">標識此裝置的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="a2f0f-113">Unique number identifying this device.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2f0f-114"><strong>DeviceName</strong></span><span class="sxs-lookup"><span data-stu-id="a2f0f-114"><strong>DeviceName</strong></span></span></p></td>
<td><p><span data-ttu-id="a2f0f-115">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="a2f0f-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a2f0f-116">DeviceName + DeviceType 是唯一的</span><span class="sxs-lookup"><span data-stu-id="a2f0f-116">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="a2f0f-117">裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="a2f0f-117">Device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2f0f-118"><strong>DeviceType</strong></span><span class="sxs-lookup"><span data-stu-id="a2f0f-118"><strong>DeviceType</strong></span></span></p></td>
<td><p><span data-ttu-id="a2f0f-119">稍微</span><span class="sxs-lookup"><span data-stu-id="a2f0f-119">bit</span></span></p></td>
<td><p><span data-ttu-id="a2f0f-120">DeviceName + DeviceType 是唯一的</span><span class="sxs-lookup"><span data-stu-id="a2f0f-120">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="a2f0f-121">裝置類型。</span><span class="sxs-lookup"><span data-stu-id="a2f0f-121">Device type.</span></span> <span data-ttu-id="a2f0f-122">1是擷取裝置，0是轉譯裝置。</span><span class="sxs-lookup"><span data-stu-id="a2f0f-122">1 is a capture device, 0 is a render device.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

