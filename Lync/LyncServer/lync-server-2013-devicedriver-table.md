---
title: Lync Server 2013： DeviceDriver 表格
description: Lync Server 2013： DeviceDriver 表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DeviceDriver table
ms:assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398844(v=OCS.15)
ms:contentKeyID: 48185449
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d81e2e27ff5196112c6057c429f924e5b1c3e4b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565969"
---
# <a name="devicedriver-table-in-lync-server-2013"></a><span data-ttu-id="7b72d-103">Lync Server 2013 中的 DeviceDriver 表格</span><span class="sxs-lookup"><span data-stu-id="7b72d-103">DeviceDriver table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b72d-104">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="7b72d-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="7b72d-105">DeviceDriver 表格是支援的表格。</span><span class="sxs-lookup"><span data-stu-id="7b72d-105">The DeviceDriver table is a supporting table.</span></span> <span data-ttu-id="7b72d-106">每筆記錄都代表一個捕獲裝置或轉譯裝置使用的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="7b72d-106">Each record represents a driver used by either a capture device or render device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b72d-107"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="7b72d-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="7b72d-108"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="7b72d-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="7b72d-109"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="7b72d-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="7b72d-110"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="7b72d-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b72d-111"><strong>DeviceDriverKey</strong></span><span class="sxs-lookup"><span data-stu-id="7b72d-111"><strong>DeviceDriverKey</strong></span></span></p></td>
<td><p><span data-ttu-id="7b72d-112">int</span><span class="sxs-lookup"><span data-stu-id="7b72d-112">int</span></span></p></td>
<td><p><span data-ttu-id="7b72d-113">主要</span><span class="sxs-lookup"><span data-stu-id="7b72d-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="7b72d-114">用於識別此裝置磁碟機記錄的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="7b72d-114">Unique number identifying this device driver record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b72d-115"><strong>DeviceDriver</strong></span><span class="sxs-lookup"><span data-stu-id="7b72d-115"><strong>DeviceDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="7b72d-116">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="7b72d-116">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7b72d-117">unique</span><span class="sxs-lookup"><span data-stu-id="7b72d-117">unique</span></span></p></td>
<td><p><span data-ttu-id="7b72d-118">裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="7b72d-118">Device driver name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

