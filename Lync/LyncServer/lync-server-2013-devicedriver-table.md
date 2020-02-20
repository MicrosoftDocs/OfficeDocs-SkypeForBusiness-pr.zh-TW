---
title: 'Lync Server 2013:: DeviceDriver 表格'
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
ms.openlocfilehash: 0a4638676371b2de3673fbb7ff805b401ffb00dc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="devicedriver-table-in-lync-server-2013"></a><span data-ttu-id="766eb-102">在 [Lync Server 2013: DeviceDriver 表格</span><span class="sxs-lookup"><span data-stu-id="766eb-102">DeviceDriver table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="766eb-103">_**主題上次修改日期：** 2012年-10-02_</span><span class="sxs-lookup"><span data-stu-id="766eb-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="766eb-104">: DeviceDriver 表格是一種支援資料表。</span><span class="sxs-lookup"><span data-stu-id="766eb-104">The DeviceDriver table is a supporting table.</span></span> <span data-ttu-id="766eb-105">每一筆記錄代表使用其中一個擷取裝置驅動程式，或轉換裝置。</span><span class="sxs-lookup"><span data-stu-id="766eb-105">Each record represents a driver used by either a capture device or render device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="766eb-106"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="766eb-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="766eb-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="766eb-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="766eb-108"><strong>主索引鍵 /</strong></span><span class="sxs-lookup"><span data-stu-id="766eb-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="766eb-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="766eb-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="766eb-110"><strong>DeviceDriverKey</strong></span><span class="sxs-lookup"><span data-stu-id="766eb-110"><strong>DeviceDriverKey</strong></span></span></p></td>
<td><p><span data-ttu-id="766eb-111">int</span><span class="sxs-lookup"><span data-stu-id="766eb-111">int</span></span></p></td>
<td><p><span data-ttu-id="766eb-112">主要</span><span class="sxs-lookup"><span data-stu-id="766eb-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="766eb-113">用於識別此裝置驅動程式記錄的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="766eb-113">Unique number identifying this device driver record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="766eb-114"><strong>: DeviceDriver</strong></span><span class="sxs-lookup"><span data-stu-id="766eb-114"><strong>DeviceDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="766eb-115">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="766eb-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="766eb-116">unique</span><span class="sxs-lookup"><span data-stu-id="766eb-116">unique</span></span></p></td>
<td><p><span data-ttu-id="766eb-117">裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="766eb-117">Device driver name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

