---
title: 'Lync Server 2013: Phones 表格'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Phones table
ms:assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425923(v=OCS.15)
ms:contentKeyID: 48183996
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f7a03cdad1e3b080bb62db31ea1796e14cd2887
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215469"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="phones-table-in-lync-server-2013"></a><span data-ttu-id="6894e-102">Lync Server 2013 中的 phones 表格</span><span class="sxs-lookup"><span data-stu-id="6894e-102">Phones table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6894e-103">_**主題上次修改日期：** 2012年-08-20 個_</span><span class="sxs-lookup"><span data-stu-id="6894e-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="6894e-104">Phones 表格是一種支援資料表。</span><span class="sxs-lookup"><span data-stu-id="6894e-104">The Phones table is a supporting table.</span></span> <span data-ttu-id="6894e-105">在資料表中的每一筆記錄儲存一個電話號碼中擁有記錄資料庫中的 VoIP 通話的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="6894e-105">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6894e-106">欄</span><span class="sxs-lookup"><span data-stu-id="6894e-106">Column</span></span></th>
<th><span data-ttu-id="6894e-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="6894e-107">Data Type</span></span></th>
<th><span data-ttu-id="6894e-108">主索引鍵 /</span><span class="sxs-lookup"><span data-stu-id="6894e-108">Key/Index</span></span></th>
<th><span data-ttu-id="6894e-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="6894e-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6894e-110"><strong>PhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="6894e-110"><strong>PhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="6894e-111">int</span><span class="sxs-lookup"><span data-stu-id="6894e-111">int</span></span></p></td>
<td><p><span data-ttu-id="6894e-112">主要</span><span class="sxs-lookup"><span data-stu-id="6894e-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="6894e-113">用於識別此電話的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="6894e-113">Unique number identifying this phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6894e-114"><strong>PhoneUri</strong></span><span class="sxs-lookup"><span data-stu-id="6894e-114"><strong>PhoneUri</strong></span></span></p></td>
<td><p><span data-ttu-id="6894e-115">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="6894e-115">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6894e-116">電話號碼。</span><span class="sxs-lookup"><span data-stu-id="6894e-116">Phone number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6894e-117"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="6894e-117"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="6894e-118">dateTime</span><span class="sxs-lookup"><span data-stu-id="6894e-118">dateTime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6894e-119">時間戳記 （僅限內部使用）。</span><span class="sxs-lookup"><span data-stu-id="6894e-119">Time stamp (for internal use only).</span></span></p>
<p><span data-ttu-id="6894e-120">Microsoft Lync Server 2013 中已採用此欄位。</span><span class="sxs-lookup"><span data-stu-id="6894e-120">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

