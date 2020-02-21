---
title: 'Lync Server 2013: SIPResponseMetaData 資料表'
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
ms.openlocfilehash: 0143bdd74b955f2cba5f68540be7c969f748aa47
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sipresponsemetadata-table-in-lync-server-2013"></a><span data-ttu-id="d2076-102">Lync Server 2013 中的 SIPResponseMetaData 資料表</span><span class="sxs-lookup"><span data-stu-id="d2076-102">SIPResponseMetaData table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2076-103">_**主題上次修改日期：** 2012年-09-28_</span><span class="sxs-lookup"><span data-stu-id="d2076-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="d2076-104">SIPResponseMetaDataTable 包含 SIP 回應碼的分類和定義每個這些代碼的清單。</span><span class="sxs-lookup"><span data-stu-id="d2076-104">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="d2076-105">這些代碼而產生的影響 SIP 裝置的事件回應及的 SIP 通訊工作階段;例如，SIP 裝置提出要求，但伺服器拒絕以受限於該要求時，都會產生回應碼 403。</span><span class="sxs-lookup"><span data-stu-id="d2076-105">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>

<span data-ttu-id="d2076-106">Microsoft Lync Server 2013 中已採用此表格。</span><span class="sxs-lookup"><span data-stu-id="d2076-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d2076-107">欄</span><span class="sxs-lookup"><span data-stu-id="d2076-107">Column</span></span></th>
<th><span data-ttu-id="d2076-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="d2076-108">Data Type</span></span></th>
<th><span data-ttu-id="d2076-109">主索引鍵 /</span><span class="sxs-lookup"><span data-stu-id="d2076-109">Key/Index</span></span></th>
<th><span data-ttu-id="d2076-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="d2076-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d2076-111"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="d2076-111"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="d2076-112">int</span><span class="sxs-lookup"><span data-stu-id="d2076-112">int</span></span></p></td>
<td><p><span data-ttu-id="d2076-113">主要</span><span class="sxs-lookup"><span data-stu-id="d2076-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="d2076-114">代表 SIP 回應碼的數值。</span><span class="sxs-lookup"><span data-stu-id="d2076-114">Numeric value that represents the SIP response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2076-115"><strong>類別</strong></span><span class="sxs-lookup"><span data-stu-id="d2076-115"><strong>Class</strong></span></span></p></td>
<td><p><span data-ttu-id="d2076-116">int</span><span class="sxs-lookup"><span data-stu-id="d2076-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d2076-117">一般的回應碼的分類。</span><span class="sxs-lookup"><span data-stu-id="d2076-117">General classification for the response code.</span></span> <span data-ttu-id="d2076-118">分類包括：</span><span class="sxs-lookup"><span data-stu-id="d2076-118">Classifications include:</span></span></p>
<ul>
<li><p><span data-ttu-id="d2076-119">1 – 資訊回應</span><span class="sxs-lookup"><span data-stu-id="d2076-119">1 – Informational Responses</span></span></p></li>
<li><p><span data-ttu-id="d2076-120">2 – 成功回應</span><span class="sxs-lookup"><span data-stu-id="d2076-120">2 – Successful Responses</span></span></p></li>
<li><p><span data-ttu-id="d2076-121">3 – 重新導向回應</span><span class="sxs-lookup"><span data-stu-id="d2076-121">3 – Redirection Responses</span></span></p></li>
<li><p><span data-ttu-id="d2076-122">4 – 用戶端失敗回應</span><span class="sxs-lookup"><span data-stu-id="d2076-122">4 – Client Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="d2076-123">5 – 伺服器失敗回應</span><span class="sxs-lookup"><span data-stu-id="d2076-123">5 -- Server Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="d2076-124">6 – 全域失敗回應</span><span class="sxs-lookup"><span data-stu-id="d2076-124">6 – Global Failure Response</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2076-125"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="d2076-125"><strong>Description</strong></span></span></p></td>
<td><p><span data-ttu-id="d2076-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d2076-126">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d2076-127">SIP 回應碼的描述。</span><span class="sxs-lookup"><span data-stu-id="d2076-127">Description of the SIP response code.</span></span> <span data-ttu-id="d2076-128">例如，回應碼 181 有下列描述：</span><span class="sxs-lookup"><span data-stu-id="d2076-128">For example, response code 181 has the following description:</span></span></p>
<p><span data-ttu-id="d2076-129">已轉接通話</span><span class="sxs-lookup"><span data-stu-id="d2076-129">Call Is Being Forwarded</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

