---
title: 'Lync Server 2013: SessionCorrelation 表格'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionCorrelation table
ms:assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398091(v=OCS.15)
ms:contentKeyID: 48183267
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9551cf5824d5f13f6167f2aaeb301ab619f6209b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051265"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessioncorrelation-table-in-lync-server-2013"></a><span data-ttu-id="d9b58-102">Lync Server 2013 中的 SessionCorrelation 表格</span><span class="sxs-lookup"><span data-stu-id="d9b58-102">SessionCorrelation table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9b58-103">_**主題上次修改日期：** 2012年-10-02_</span><span class="sxs-lookup"><span data-stu-id="d9b58-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="d9b58-104">SessionCorrelation 表格是一種支援資料表。</span><span class="sxs-lookup"><span data-stu-id="d9b58-104">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="d9b58-105">每筆記錄代表一個 CorrelationID 是用來建立多個工作階段之間的關係。</span><span class="sxs-lookup"><span data-stu-id="d9b58-105">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d9b58-106"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="d9b58-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d9b58-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="d9b58-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d9b58-108"><strong>主索引鍵 /</strong></span><span class="sxs-lookup"><span data-stu-id="d9b58-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d9b58-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="d9b58-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d9b58-110"><strong>總和檢查碼</strong></span><span class="sxs-lookup"><span data-stu-id="d9b58-110"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="d9b58-111">int</span><span class="sxs-lookup"><span data-stu-id="d9b58-111">int</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9b58-112"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="d9b58-112"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="d9b58-113">int</span><span class="sxs-lookup"><span data-stu-id="d9b58-113">int</span></span></p></td>
<td><p><span data-ttu-id="d9b58-114">主要</span><span class="sxs-lookup"><span data-stu-id="d9b58-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="d9b58-115">唯一的數字識別這部 A / V 會議伺服器。</span><span class="sxs-lookup"><span data-stu-id="d9b58-115">Unique number identifying this A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9b58-116"><strong>相互關聯識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="d9b58-116"><strong>CorrelationID</strong></span></span></p></td>
<td><p><span data-ttu-id="d9b58-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d9b58-117">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d9b58-118">Unique</span><span class="sxs-lookup"><span data-stu-id="d9b58-118">Unique</span></span></p></td>
<td><p><span data-ttu-id="d9b58-119">相互關聯的工作階段會有相同的相互關聯識別碼。</span><span class="sxs-lookup"><span data-stu-id="d9b58-119">Sessions that are correlated will have the same correlation ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9b58-120"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="d9b58-120"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="d9b58-121">datetime</span><span class="sxs-lookup"><span data-stu-id="d9b58-121">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d9b58-122">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="d9b58-122">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

