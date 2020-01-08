---
title: Lync Server 2013：PayloadDescription 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PayloadDescription table
ms:assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412971(v=OCS.15)
ms:contentKeyID: 48185353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a8d18f87b9a4f5de556ec827447f0020b7a47f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="payloaddescription-table-in-lync-server-2013"></a><span data-ttu-id="d557e-102">Lync Server 2013 中的 PayloadDescription 表格</span><span class="sxs-lookup"><span data-stu-id="d557e-102">PayloadDescription table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d557e-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="d557e-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="d557e-104">PayloadDescription 資料表是支援資料表。</span><span class="sxs-lookup"><span data-stu-id="d557e-104">The PayloadDescription table is a supporting table.</span></span> <span data-ttu-id="d557e-105">每個記錄代表一個在音訊或視頻會話中使用的編解碼器。</span><span class="sxs-lookup"><span data-stu-id="d557e-105">Each record represents one Codec, which is used in an audio or video session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d557e-106"><strong>左欄</strong></span><span class="sxs-lookup"><span data-stu-id="d557e-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d557e-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="d557e-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d557e-108"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="d557e-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d557e-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="d557e-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d557e-110"><strong>PayloadDescriptionKey</strong></span><span class="sxs-lookup"><span data-stu-id="d557e-110"><strong>PayloadDescriptionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="d557e-111">int</span><span class="sxs-lookup"><span data-stu-id="d557e-111">int</span></span></p></td>
<td><p><span data-ttu-id="d557e-112">首選</span><span class="sxs-lookup"><span data-stu-id="d557e-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="d557e-113">識別編解碼器的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="d557e-113">Unique number identifying the Codec.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d557e-114"><strong>PayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="d557e-114"><strong>PayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="d557e-115">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="d557e-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d557e-116">唯一</span><span class="sxs-lookup"><span data-stu-id="d557e-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="d557e-117">編解碼器名稱。</span><span class="sxs-lookup"><span data-stu-id="d557e-117">Codec name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

