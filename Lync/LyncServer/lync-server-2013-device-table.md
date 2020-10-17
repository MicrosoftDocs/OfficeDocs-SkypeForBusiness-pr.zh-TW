---
title: Lync Server 2013： Device 表格
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
ms.openlocfilehash: 8bd5b62059329d9a2277e28f1a2ae08c25384bde
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522430"
---
# <a name="device-table-in-lync-server-2013"></a><span data-ttu-id="f89e0-102">Lync Server 2013 中的裝置表格</span><span class="sxs-lookup"><span data-stu-id="f89e0-102">Device table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f89e0-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="f89e0-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="f89e0-104">Device 表是一種支援資料表，可儲存各種捕獲或呈現裝置的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f89e0-104">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="f89e0-105">資料表中的每一筆記錄都代表一個裝置。</span><span class="sxs-lookup"><span data-stu-id="f89e0-105">Each record in the table represents one device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f89e0-106"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="f89e0-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f89e0-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="f89e0-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f89e0-108"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="f89e0-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f89e0-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="f89e0-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f89e0-110"><strong>DeviceKey</strong></span><span class="sxs-lookup"><span data-stu-id="f89e0-110"><strong>DeviceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="f89e0-111">int</span><span class="sxs-lookup"><span data-stu-id="f89e0-111">int</span></span></p></td>
<td><p><span data-ttu-id="f89e0-112">主要</span><span class="sxs-lookup"><span data-stu-id="f89e0-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="f89e0-113">用於識別此裝置的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="f89e0-113">Unique number identifying this device.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f89e0-114"><strong>DeviceName</strong></span><span class="sxs-lookup"><span data-stu-id="f89e0-114"><strong>DeviceName</strong></span></span></p></td>
<td><p><span data-ttu-id="f89e0-115">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="f89e0-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f89e0-116">DeviceName + DeviceType 是唯一的</span><span class="sxs-lookup"><span data-stu-id="f89e0-116">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="f89e0-117">裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="f89e0-117">Device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f89e0-118"><strong>DeviceType</strong></span><span class="sxs-lookup"><span data-stu-id="f89e0-118"><strong>DeviceType</strong></span></span></p></td>
<td><p><span data-ttu-id="f89e0-119">位</span><span class="sxs-lookup"><span data-stu-id="f89e0-119">bit</span></span></p></td>
<td><p><span data-ttu-id="f89e0-120">DeviceName + DeviceType 是唯一的</span><span class="sxs-lookup"><span data-stu-id="f89e0-120">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="f89e0-121">裝置類型。</span><span class="sxs-lookup"><span data-stu-id="f89e0-121">Device type.</span></span> <span data-ttu-id="f89e0-122">1是捕獲裝置，0代表呈現裝置。</span><span class="sxs-lookup"><span data-stu-id="f89e0-122">1 is a capture device, 0 is a render device.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

