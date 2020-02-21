---
title: 'Lync Server 2013: Devices 表格'
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
ms.openlocfilehash: 8906519253445ea67f3fa674a9a1315f8f6cf18b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213499"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="devices-table-in-lync-server-2013"></a><span data-ttu-id="e93cd-102">Lync Server 2013 中的裝置表格</span><span class="sxs-lookup"><span data-stu-id="e93cd-102">Devices table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e93cd-103">_**主題上次修改日期：** 2012年-05-25_</span><span class="sxs-lookup"><span data-stu-id="e93cd-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="e93cd-p101">Devices 表格是一種支援資料表。每筆記錄儲存一部裝置 (電話機) 的資訊。</span><span class="sxs-lookup"><span data-stu-id="e93cd-p101">The Devices table is a supporting table. Each record stores information about one device (desk phone).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e93cd-106">欄</span><span class="sxs-lookup"><span data-stu-id="e93cd-106">Column</span></span></th>
<th><span data-ttu-id="e93cd-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="e93cd-107">Data Type</span></span></th>
<th><span data-ttu-id="e93cd-108">主索引鍵 /</span><span class="sxs-lookup"><span data-stu-id="e93cd-108">Key/Index</span></span></th>
<th><span data-ttu-id="e93cd-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="e93cd-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e93cd-110"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="e93cd-110"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="e93cd-111">int</span><span class="sxs-lookup"><span data-stu-id="e93cd-111">int</span></span></p></td>
<td><p><span data-ttu-id="e93cd-112">主要</span><span class="sxs-lookup"><span data-stu-id="e93cd-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="e93cd-113">用於識別此硬體版本的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="e93cd-113">Unique number identifying this hardware version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e93cd-114"><strong>ManufacturerId</strong></span><span class="sxs-lookup"><span data-stu-id="e93cd-114"><strong>ManufacturerId</strong></span></span></p></td>
<td><p><span data-ttu-id="e93cd-115">int</span><span class="sxs-lookup"><span data-stu-id="e93cd-115">int</span></span></p></td>
<td><p><span data-ttu-id="e93cd-116">Foreign</span><span class="sxs-lookup"><span data-stu-id="e93cd-116">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e93cd-117">此裝置的製造商。</span><span class="sxs-lookup"><span data-stu-id="e93cd-117">Manufacturer of this device.</span></span> <span data-ttu-id="e93cd-118">請參閱<a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 中的 Manufacturers 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e93cd-118">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e93cd-119"><strong>HardwareVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="e93cd-119"><strong>HardwareVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="e93cd-120">int</span><span class="sxs-lookup"><span data-stu-id="e93cd-120">int</span></span></p></td>
<td><p><span data-ttu-id="e93cd-121">Foreign</span><span class="sxs-lookup"><span data-stu-id="e93cd-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e93cd-122">此裝置的硬體版本。</span><span class="sxs-lookup"><span data-stu-id="e93cd-122">Hardware version of this device.</span></span> <span data-ttu-id="e93cd-123">請參閱<a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 中的 HardwareVersions 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e93cd-123">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e93cd-124"><strong>MacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="e93cd-124"><strong>MacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="e93cd-125">bigint</span><span class="sxs-lookup"><span data-stu-id="e93cd-125">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e93cd-126">MAC 位址</span><span class="sxs-lookup"><span data-stu-id="e93cd-126">MAC Address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

