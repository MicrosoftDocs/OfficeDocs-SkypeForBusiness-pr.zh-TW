---
title: Lync Server 2013：Phones 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Phones table
ms:assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425923(v=OCS.15)
ms:contentKeyID: 48183996
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 920454a5db71c1e6f3cd2ea2ae1134d149b4f297
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981683"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phones-table-in-lync-server-2013"></a><span data-ttu-id="4559a-102">Lync Server 2013 中的 Phones 表格</span><span class="sxs-lookup"><span data-stu-id="4559a-102">Phones table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4559a-103">_**主題上次修改日期：** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="4559a-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="4559a-104">[電話] 資料表是支援表格。</span><span class="sxs-lookup"><span data-stu-id="4559a-104">The Phones table is a supporting table.</span></span> <span data-ttu-id="4559a-105">資料表中的每一筆記錄都儲存 VoIP 通話中有記錄在資料庫中的一個電話號碼的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="4559a-105">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4559a-106">左欄</span><span class="sxs-lookup"><span data-stu-id="4559a-106">Column</span></span></th>
<th><span data-ttu-id="4559a-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="4559a-107">Data Type</span></span></th>
<th><span data-ttu-id="4559a-108">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="4559a-108">Key/Index</span></span></th>
<th><span data-ttu-id="4559a-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="4559a-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4559a-110"><strong>PhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="4559a-110"><strong>PhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="4559a-111">int</span><span class="sxs-lookup"><span data-stu-id="4559a-111">int</span></span></p></td>
<td><p><span data-ttu-id="4559a-112">首選</span><span class="sxs-lookup"><span data-stu-id="4559a-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="4559a-113">標識此手機的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="4559a-113">Unique number identifying this phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4559a-114"><strong>PhoneUri</strong></span><span class="sxs-lookup"><span data-stu-id="4559a-114"><strong>PhoneUri</strong></span></span></p></td>
<td><p><span data-ttu-id="4559a-115">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="4559a-115">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4559a-116">電話號碼。</span><span class="sxs-lookup"><span data-stu-id="4559a-116">Phone number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4559a-117"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="4559a-117"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="4559a-118">dateTime</span><span class="sxs-lookup"><span data-stu-id="4559a-118">dateTime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4559a-119">時間戳記（僅供內部使用）。</span><span class="sxs-lookup"><span data-stu-id="4559a-119">Time stamp (for internal use only).</span></span></p>
<p><span data-ttu-id="4559a-120">此欄位是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="4559a-120">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

