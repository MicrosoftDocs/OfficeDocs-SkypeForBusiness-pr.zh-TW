---
title: Lync Server 2013： SIPResponseMetaData 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SIPResponseMetaData table
ms:assetid: cf723737-4a75-4352-829b-f4954aa59716
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205294(v=OCS.15)
ms:contentKeyID: 48185510
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31df563172cce2e6ac9780511665ef563532a7d9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sipresponsemetadata-table-in-lync-server-2013"></a><span data-ttu-id="73f7f-102">Lync Server 2013 中的 SIPResponseMetaData 表格</span><span class="sxs-lookup"><span data-stu-id="73f7f-102">SIPResponseMetaData table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73f7f-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="73f7f-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="73f7f-104">SIPResponseMetaDataTable 包含 SIP 回應代碼清單，以及每個代碼的分類與定義。</span><span class="sxs-lookup"><span data-stu-id="73f7f-104">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="73f7f-105">系統會產生這些代碼，以回應影響 SIP 裝置和 SIP 通訊會話的事件;例如，回應碼403是在 SIP 裝置提出要求時產生，但伺服器會拒絕服從該要求。</span><span class="sxs-lookup"><span data-stu-id="73f7f-105">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>

<span data-ttu-id="73f7f-106">此表格是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="73f7f-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="73f7f-107">左欄</span><span class="sxs-lookup"><span data-stu-id="73f7f-107">Column</span></span></th>
<th><span data-ttu-id="73f7f-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="73f7f-108">Data Type</span></span></th>
<th><span data-ttu-id="73f7f-109">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="73f7f-109">Key/Index</span></span></th>
<th><span data-ttu-id="73f7f-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="73f7f-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73f7f-111"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="73f7f-111"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="73f7f-112">int</span><span class="sxs-lookup"><span data-stu-id="73f7f-112">int</span></span></p></td>
<td><p><span data-ttu-id="73f7f-113">首選</span><span class="sxs-lookup"><span data-stu-id="73f7f-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="73f7f-114">代表 SIP 回應代碼的數值。</span><span class="sxs-lookup"><span data-stu-id="73f7f-114">Numeric value that represents the SIP response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73f7f-115"><strong>靜態類</strong></span><span class="sxs-lookup"><span data-stu-id="73f7f-115"><strong>Class</strong></span></span></p></td>
<td><p><span data-ttu-id="73f7f-116">int</span><span class="sxs-lookup"><span data-stu-id="73f7f-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73f7f-117">回應代碼的一般分類。</span><span class="sxs-lookup"><span data-stu-id="73f7f-117">General classification for the response code.</span></span> <span data-ttu-id="73f7f-118">分類包括：</span><span class="sxs-lookup"><span data-stu-id="73f7f-118">Classifications include:</span></span></p>
<ul>
<li><p><span data-ttu-id="73f7f-119">1–資訊回應</span><span class="sxs-lookup"><span data-stu-id="73f7f-119">1 – Informational Responses</span></span></p></li>
<li><p><span data-ttu-id="73f7f-120">2–成功回應</span><span class="sxs-lookup"><span data-stu-id="73f7f-120">2 – Successful Responses</span></span></p></li>
<li><p><span data-ttu-id="73f7f-121">3–重新導向回應</span><span class="sxs-lookup"><span data-stu-id="73f7f-121">3 – Redirection Responses</span></span></p></li>
<li><p><span data-ttu-id="73f7f-122">4–用戶端失敗回應</span><span class="sxs-lookup"><span data-stu-id="73f7f-122">4 – Client Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="73f7f-123">5--伺服器失敗回應</span><span class="sxs-lookup"><span data-stu-id="73f7f-123">5 -- Server Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="73f7f-124">6-全域失敗回應</span><span class="sxs-lookup"><span data-stu-id="73f7f-124">6 – Global Failure Response</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73f7f-125"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="73f7f-125"><strong>Description</strong></span></span></p></td>
<td><p><span data-ttu-id="73f7f-126">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="73f7f-126">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73f7f-127">SIP 回應代碼的描述。</span><span class="sxs-lookup"><span data-stu-id="73f7f-127">Description of the SIP response code.</span></span> <span data-ttu-id="73f7f-128">例如，回應代碼181具有下列描述：</span><span class="sxs-lookup"><span data-stu-id="73f7f-128">For example, response code 181 has the following description:</span></span></p>
<p><span data-ttu-id="73f7f-129">呼叫正在轉寄</span><span class="sxs-lookup"><span data-stu-id="73f7f-129">Call Is Being Forwarded</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

