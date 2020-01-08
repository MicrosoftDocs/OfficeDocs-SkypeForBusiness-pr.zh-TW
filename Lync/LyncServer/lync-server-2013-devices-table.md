---
title: Lync Server 2013：Devices 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Devices table
ms:assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398351(v=OCS.15)
ms:contentKeyID: 48184169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f78e0b4ba3bb5271a2de43e423dfa4b3baf17cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="devices-table-in-lync-server-2013"></a><span data-ttu-id="59488-102">Lync Server 2013 中的 Devices 表格</span><span class="sxs-lookup"><span data-stu-id="59488-102">Devices table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59488-103">_**主題上次修改日期：** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="59488-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="59488-104">[裝置] 資料表是支援資料表。</span><span class="sxs-lookup"><span data-stu-id="59488-104">The Devices table is a supporting table.</span></span> <span data-ttu-id="59488-105">每筆記錄儲存一個裝置（電話機）的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="59488-105">Each record stores information about one device (desk phone).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="59488-106">左欄</span><span class="sxs-lookup"><span data-stu-id="59488-106">Column</span></span></th>
<th><span data-ttu-id="59488-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="59488-107">Data Type</span></span></th>
<th><span data-ttu-id="59488-108">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="59488-108">Key/Index</span></span></th>
<th><span data-ttu-id="59488-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="59488-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59488-110"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="59488-110"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="59488-111">int</span><span class="sxs-lookup"><span data-stu-id="59488-111">int</span></span></p></td>
<td><p><span data-ttu-id="59488-112">首選</span><span class="sxs-lookup"><span data-stu-id="59488-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="59488-113">識別這個硬體版本的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="59488-113">Unique number identifying this hardware version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59488-114"><strong>[Manufacturerid</strong></span><span class="sxs-lookup"><span data-stu-id="59488-114"><strong>ManufacturerId</strong></span></span></p></td>
<td><p><span data-ttu-id="59488-115">int</span><span class="sxs-lookup"><span data-stu-id="59488-115">int</span></span></p></td>
<td><p><span data-ttu-id="59488-116">外</span><span class="sxs-lookup"><span data-stu-id="59488-116">Foreign</span></span></p></td>
<td><p><span data-ttu-id="59488-117">此裝置的製造商。</span><span class="sxs-lookup"><span data-stu-id="59488-117">Manufacturer of this device.</span></span> <span data-ttu-id="59488-118">如需詳細資訊，請參閱<a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 中</a>的 [製造商] 資料表。</span><span class="sxs-lookup"><span data-stu-id="59488-118">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59488-119"><strong>HardwareVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="59488-119"><strong>HardwareVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="59488-120">int</span><span class="sxs-lookup"><span data-stu-id="59488-120">int</span></span></p></td>
<td><p><span data-ttu-id="59488-121">外</span><span class="sxs-lookup"><span data-stu-id="59488-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="59488-122">此裝置的硬體版本。</span><span class="sxs-lookup"><span data-stu-id="59488-122">Hardware version of this device.</span></span> <span data-ttu-id="59488-123">如需詳細資訊，請參閱<a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 中</a>的 [HardwareVersions] 資料表。</span><span class="sxs-lookup"><span data-stu-id="59488-123">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59488-124"><strong>MacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="59488-124"><strong>MacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="59488-125">Bigint</span><span class="sxs-lookup"><span data-stu-id="59488-125">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59488-126">MAC 位址</span><span class="sxs-lookup"><span data-stu-id="59488-126">MAC Address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

