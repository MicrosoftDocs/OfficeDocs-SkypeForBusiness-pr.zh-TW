---
title: Lync Server 2013：裝置表格
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
ms.openlocfilehash: c5fdc4c3b20bdd60d2c8013b79a15bdfd30b56af
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536930"
---
# <a name="devices-table-in-lync-server-2013"></a><span data-ttu-id="08085-102">Lync Server 2013 中的 [裝置] 表格</span><span class="sxs-lookup"><span data-stu-id="08085-102">Devices table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08085-103">_**主題上次修改日期：** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="08085-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="08085-p101">Devices 表格是一種支援資料表。每筆記錄儲存一部裝置 (電話機) 的資訊。</span><span class="sxs-lookup"><span data-stu-id="08085-p101">The Devices table is a supporting table. Each record stores information about one device (desk phone).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="08085-106">欄</span><span class="sxs-lookup"><span data-stu-id="08085-106">Column</span></span></th>
<th><span data-ttu-id="08085-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="08085-107">Data Type</span></span></th>
<th><span data-ttu-id="08085-108">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="08085-108">Key/Index</span></span></th>
<th><span data-ttu-id="08085-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="08085-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08085-110"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="08085-110"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="08085-111">int</span><span class="sxs-lookup"><span data-stu-id="08085-111">int</span></span></p></td>
<td><p><span data-ttu-id="08085-112">主要</span><span class="sxs-lookup"><span data-stu-id="08085-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="08085-113">用於識別此硬體版本的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="08085-113">Unique number identifying this hardware version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08085-114"><strong>ManufacturerId</strong></span><span class="sxs-lookup"><span data-stu-id="08085-114"><strong>ManufacturerId</strong></span></span></p></td>
<td><p><span data-ttu-id="08085-115">int</span><span class="sxs-lookup"><span data-stu-id="08085-115">int</span></span></p></td>
<td><p><span data-ttu-id="08085-116">Foreign</span><span class="sxs-lookup"><span data-stu-id="08085-116">Foreign</span></span></p></td>
<td><p><span data-ttu-id="08085-117">此裝置的製造商。</span><span class="sxs-lookup"><span data-stu-id="08085-117">Manufacturer of this device.</span></span> <span data-ttu-id="08085-118">如需詳細資訊，請參閱 <a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 中的製造商表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="08085-118">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08085-119"><strong>HardwareVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="08085-119"><strong>HardwareVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="08085-120">int</span><span class="sxs-lookup"><span data-stu-id="08085-120">int</span></span></p></td>
<td><p><span data-ttu-id="08085-121">Foreign</span><span class="sxs-lookup"><span data-stu-id="08085-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="08085-122">此裝置的硬體版本。</span><span class="sxs-lookup"><span data-stu-id="08085-122">Hardware version of this device.</span></span> <span data-ttu-id="08085-123">如需詳細資訊，請參閱 <a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 中的 HardwareVersions 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="08085-123">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08085-124"><strong>MacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="08085-124"><strong>MacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="08085-125">Bigint</span><span class="sxs-lookup"><span data-stu-id="08085-125">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="08085-126">MAC 位址</span><span class="sxs-lookup"><span data-stu-id="08085-126">MAC Address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

