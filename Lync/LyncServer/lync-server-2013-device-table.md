---
title: Lync Server 2013： 裝置表格
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
ms.openlocfilehash: 1040642874d2963292744eb2543c9ee265440fd2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="device-table-in-lync-server-2013"></a><span data-ttu-id="4104d-102">Lync Server 2013 中的裝置表格</span><span class="sxs-lookup"><span data-stu-id="4104d-102">Device table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4104d-103">_**主題上次修改日期：** 2012年-10-02_</span><span class="sxs-lookup"><span data-stu-id="4104d-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="4104d-104">裝置表格是儲存資訊的各種擷取一種支援資料表，或轉換裝置。</span><span class="sxs-lookup"><span data-stu-id="4104d-104">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="4104d-105">在資料表中的每一筆記錄代表一個裝置。</span><span class="sxs-lookup"><span data-stu-id="4104d-105">Each record in the table represents one device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4104d-106"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="4104d-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="4104d-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="4104d-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="4104d-108"><strong>主索引鍵 /</strong></span><span class="sxs-lookup"><span data-stu-id="4104d-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="4104d-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="4104d-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4104d-110"><strong>DeviceKey</strong></span><span class="sxs-lookup"><span data-stu-id="4104d-110"><strong>DeviceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="4104d-111">int</span><span class="sxs-lookup"><span data-stu-id="4104d-111">int</span></span></p></td>
<td><p><span data-ttu-id="4104d-112">主要</span><span class="sxs-lookup"><span data-stu-id="4104d-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="4104d-113">用於識別此裝置的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="4104d-113">Unique number identifying this device.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4104d-114"><strong>DeviceName</strong></span><span class="sxs-lookup"><span data-stu-id="4104d-114"><strong>DeviceName</strong></span></span></p></td>
<td><p><span data-ttu-id="4104d-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4104d-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4104d-116">DeviceName + DeviceType 是唯一</span><span class="sxs-lookup"><span data-stu-id="4104d-116">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="4104d-117">裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="4104d-117">Device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4104d-118"><strong>DeviceType</strong></span><span class="sxs-lookup"><span data-stu-id="4104d-118"><strong>DeviceType</strong></span></span></p></td>
<td><p><span data-ttu-id="4104d-119">位元</span><span class="sxs-lookup"><span data-stu-id="4104d-119">bit</span></span></p></td>
<td><p><span data-ttu-id="4104d-120">DeviceName + DeviceType 是唯一</span><span class="sxs-lookup"><span data-stu-id="4104d-120">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="4104d-121">裝置類型。</span><span class="sxs-lookup"><span data-stu-id="4104d-121">Device type.</span></span> <span data-ttu-id="4104d-122">1 是擷取裝置，0 轉換裝置。</span><span class="sxs-lookup"><span data-stu-id="4104d-122">1 is a capture device, 0 is a render device.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

