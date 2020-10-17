---
title: Lync Server 2013： SIPResponseMetaData 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIPResponseMetaData table
ms:assetid: cf723737-4a75-4352-829b-f4954aa59716
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205294(v=OCS.15)
ms:contentKeyID: 48185510
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2418851ed66500937dab92f2820c36a8d1afac3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519630"
---
# <a name="sipresponsemetadata-table-in-lync-server-2013"></a><span data-ttu-id="6ddb8-102">Lync Server 2013 中的 SIPResponseMetaData 表格</span><span class="sxs-lookup"><span data-stu-id="6ddb8-102">SIPResponseMetaData table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ddb8-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="6ddb8-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="6ddb8-104">SIPResponseMetaDataTable 包含 SIP 回應碼的清單，以及每個代碼的分類和定義。</span><span class="sxs-lookup"><span data-stu-id="6ddb8-104">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="6ddb8-105">這兩個代碼會在回應影響 SIP 裝置和 SIP 通訊會話的事件時產生;例如，回應碼403是在 SIP 裝置提出要求時產生，但是伺服器會謝絕該要求。</span><span class="sxs-lookup"><span data-stu-id="6ddb8-105">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>

<span data-ttu-id="6ddb8-106">此表格已引進 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="6ddb8-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6ddb8-107">欄</span><span class="sxs-lookup"><span data-stu-id="6ddb8-107">Column</span></span></th>
<th><span data-ttu-id="6ddb8-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="6ddb8-108">Data Type</span></span></th>
<th><span data-ttu-id="6ddb8-109">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="6ddb8-109">Key/Index</span></span></th>
<th><span data-ttu-id="6ddb8-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="6ddb8-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ddb8-111"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="6ddb8-111"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="6ddb8-112">int</span><span class="sxs-lookup"><span data-stu-id="6ddb8-112">int</span></span></p></td>
<td><p><span data-ttu-id="6ddb8-113">主要</span><span class="sxs-lookup"><span data-stu-id="6ddb8-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="6ddb8-114">代表 SIP 回應碼的數值。</span><span class="sxs-lookup"><span data-stu-id="6ddb8-114">Numeric value that represents the SIP response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ddb8-115"><strong>Class</strong></span><span class="sxs-lookup"><span data-stu-id="6ddb8-115"><strong>Class</strong></span></span></p></td>
<td><p><span data-ttu-id="6ddb8-116">int</span><span class="sxs-lookup"><span data-stu-id="6ddb8-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6ddb8-117">回應碼的一般分類。</span><span class="sxs-lookup"><span data-stu-id="6ddb8-117">General classification for the response code.</span></span> <span data-ttu-id="6ddb8-118">分類包括：</span><span class="sxs-lookup"><span data-stu-id="6ddb8-118">Classifications include:</span></span></p>
<ul>
<li><p><span data-ttu-id="6ddb8-119">1–資訊性回應</span><span class="sxs-lookup"><span data-stu-id="6ddb8-119">1 – Informational Responses</span></span></p></li>
<li><p><span data-ttu-id="6ddb8-120">2–成功的回應</span><span class="sxs-lookup"><span data-stu-id="6ddb8-120">2 – Successful Responses</span></span></p></li>
<li><p><span data-ttu-id="6ddb8-121">3–重新導向回應</span><span class="sxs-lookup"><span data-stu-id="6ddb8-121">3 – Redirection Responses</span></span></p></li>
<li><p><span data-ttu-id="6ddb8-122">4-用戶端失敗回應</span><span class="sxs-lookup"><span data-stu-id="6ddb8-122">4 – Client Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="6ddb8-123">5--伺服器失敗回應</span><span class="sxs-lookup"><span data-stu-id="6ddb8-123">5 -- Server Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="6ddb8-124">6–全域失敗回應</span><span class="sxs-lookup"><span data-stu-id="6ddb8-124">6 – Global Failure Response</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ddb8-125"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="6ddb8-125"><strong>Description</strong></span></span></p></td>
<td><p><span data-ttu-id="6ddb8-126">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="6ddb8-126">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6ddb8-127">SIP 回應碼的描述。</span><span class="sxs-lookup"><span data-stu-id="6ddb8-127">Description of the SIP response code.</span></span> <span data-ttu-id="6ddb8-128">例如，回應碼181的描述如下：</span><span class="sxs-lookup"><span data-stu-id="6ddb8-128">For example, response code 181 has the following description:</span></span></p>
<p><span data-ttu-id="6ddb8-129">轉接來電</span><span class="sxs-lookup"><span data-stu-id="6ddb8-129">Call Is Being Forwarded</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

