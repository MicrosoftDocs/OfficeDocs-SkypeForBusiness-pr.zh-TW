---
title: Lync Server 2013：DeviceDriver 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DeviceDriver table
ms:assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398844(v=OCS.15)
ms:contentKeyID: 48185449
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea4ab9ad8b2eda5388791c98c1e1da90d9bd5c65
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974691"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="devicedriver-table-in-lync-server-2013"></a><span data-ttu-id="def38-102">Lync Server 2013 中的 DeviceDriver 表格</span><span class="sxs-lookup"><span data-stu-id="def38-102">DeviceDriver table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="def38-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="def38-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="def38-104">DeviceDriver 資料表是支援資料表。</span><span class="sxs-lookup"><span data-stu-id="def38-104">The DeviceDriver table is a supporting table.</span></span> <span data-ttu-id="def38-105">每個記錄都代表擷取裝置或轉譯裝置所使用的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="def38-105">Each record represents a driver used by either a capture device or render device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="def38-106"><strong>左欄</strong></span><span class="sxs-lookup"><span data-stu-id="def38-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="def38-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="def38-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="def38-108"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="def38-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="def38-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="def38-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="def38-110"><strong>DeviceDriverKey</strong></span><span class="sxs-lookup"><span data-stu-id="def38-110"><strong>DeviceDriverKey</strong></span></span></p></td>
<td><p><span data-ttu-id="def38-111">int</span><span class="sxs-lookup"><span data-stu-id="def38-111">int</span></span></p></td>
<td><p><span data-ttu-id="def38-112">首選</span><span class="sxs-lookup"><span data-stu-id="def38-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="def38-113">識別此裝置驅動程式記錄的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="def38-113">Unique number identifying this device driver record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="def38-114"><strong>DeviceDriver</strong></span><span class="sxs-lookup"><span data-stu-id="def38-114"><strong>DeviceDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="def38-115">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="def38-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="def38-116">唯一</span><span class="sxs-lookup"><span data-stu-id="def38-116">unique</span></span></p></td>
<td><p><span data-ttu-id="def38-117">裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="def38-117">Device driver name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

