---
title: Lync Server 2013：Device 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Device table
ms:assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398930(v=OCS.15)
ms:contentKeyID: 48185544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 974898f6c3fa96dd9356a0a9eed1e3fab09d288b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976747"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-table-in-lync-server-2013"></a><span data-ttu-id="63ef5-102">Lync Server 2013 中的 Device 表格</span><span class="sxs-lookup"><span data-stu-id="63ef5-102">Device table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63ef5-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="63ef5-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="63ef5-104">Device 資料表是一個支援資料表，可儲存各種捕獲或轉譯裝置的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="63ef5-104">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="63ef5-105">資料表中的每一筆記錄代表一個裝置。</span><span class="sxs-lookup"><span data-stu-id="63ef5-105">Each record in the table represents one device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="63ef5-106"><strong>左欄</strong></span><span class="sxs-lookup"><span data-stu-id="63ef5-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="63ef5-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="63ef5-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="63ef5-108"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="63ef5-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="63ef5-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="63ef5-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="63ef5-110"><strong>DeviceKey</strong></span><span class="sxs-lookup"><span data-stu-id="63ef5-110"><strong>DeviceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="63ef5-111">int</span><span class="sxs-lookup"><span data-stu-id="63ef5-111">int</span></span></p></td>
<td><p><span data-ttu-id="63ef5-112">首選</span><span class="sxs-lookup"><span data-stu-id="63ef5-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="63ef5-113">標識此裝置的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="63ef5-113">Unique number identifying this device.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63ef5-114"><strong>DeviceName</strong></span><span class="sxs-lookup"><span data-stu-id="63ef5-114"><strong>DeviceName</strong></span></span></p></td>
<td><p><span data-ttu-id="63ef5-115">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="63ef5-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63ef5-116">DeviceName + DeviceType 是唯一的</span><span class="sxs-lookup"><span data-stu-id="63ef5-116">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="63ef5-117">裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="63ef5-117">Device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63ef5-118"><strong>DeviceType</strong></span><span class="sxs-lookup"><span data-stu-id="63ef5-118"><strong>DeviceType</strong></span></span></p></td>
<td><p><span data-ttu-id="63ef5-119">稍微</span><span class="sxs-lookup"><span data-stu-id="63ef5-119">bit</span></span></p></td>
<td><p><span data-ttu-id="63ef5-120">DeviceName + DeviceType 是唯一的</span><span class="sxs-lookup"><span data-stu-id="63ef5-120">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="63ef5-121">裝置類型。</span><span class="sxs-lookup"><span data-stu-id="63ef5-121">Device type.</span></span> <span data-ttu-id="63ef5-122">1是擷取裝置，0是轉譯裝置。</span><span class="sxs-lookup"><span data-stu-id="63ef5-122">1 is a capture device, 0 is a render device.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

