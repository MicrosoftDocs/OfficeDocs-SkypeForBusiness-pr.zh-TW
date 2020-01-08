---
title: Lync Server 2013：VideoClientEvent 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VideoClientEvent table
ms:assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399039(v=OCS.15)
ms:contentKeyID: 48185891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79b428a639cee6fb0df04cc969b529c5bbbfb2c9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976135"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videoclientevent-table-in-lync-server-2013"></a><span data-ttu-id="07a1d-102">Lync Server 2013 中的 VideoClientEvent 表格</span><span class="sxs-lookup"><span data-stu-id="07a1d-102">VideoClientEvent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07a1d-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="07a1d-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="07a1d-104">每個記錄都包含視頻通話中某個端點的用戶端事件。</span><span class="sxs-lookup"><span data-stu-id="07a1d-104">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="07a1d-105">通常，一個通話有兩筆記錄，一個用於呼叫者，另一個用於被叫方。</span><span class="sxs-lookup"><span data-stu-id="07a1d-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="07a1d-106"><strong>左欄</strong></span><span class="sxs-lookup"><span data-stu-id="07a1d-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="07a1d-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="07a1d-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="07a1d-108"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="07a1d-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="07a1d-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="07a1d-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07a1d-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="07a1d-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="07a1d-111">datetime</span><span class="sxs-lookup"><span data-stu-id="07a1d-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="07a1d-112">首選</span><span class="sxs-lookup"><span data-stu-id="07a1d-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="07a1d-113">從<a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="07a1d-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07a1d-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="07a1d-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="07a1d-115">int</span><span class="sxs-lookup"><span data-stu-id="07a1d-115">int</span></span></p></td>
<td><p><span data-ttu-id="07a1d-116">首選</span><span class="sxs-lookup"><span data-stu-id="07a1d-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="07a1d-117">從<a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="07a1d-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07a1d-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="07a1d-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="07a1d-119">Tinyint</span><span class="sxs-lookup"><span data-stu-id="07a1d-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="07a1d-120">首選</span><span class="sxs-lookup"><span data-stu-id="07a1d-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="07a1d-121">從<a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="07a1d-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07a1d-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="07a1d-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="07a1d-123">稍微</span><span class="sxs-lookup"><span data-stu-id="07a1d-123">bit</span></span></p></td>
<td><p><span data-ttu-id="07a1d-124">首選</span><span class="sxs-lookup"><span data-stu-id="07a1d-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="07a1d-125">0：被方程式的資料</span><span class="sxs-lookup"><span data-stu-id="07a1d-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="07a1d-126">1：來電者的資料</span><span class="sxs-lookup"><span data-stu-id="07a1d-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07a1d-127"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="07a1d-127"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="07a1d-128">會話針對「錯誤」狀態觸發 LowBandwidth 事件的百分比。</span><span class="sxs-lookup"><span data-stu-id="07a1d-128">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="07a1d-129">可用的頻寬不足以取得可接受的語音體驗。</span><span class="sxs-lookup"><span data-stu-id="07a1d-129">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07a1d-130"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="07a1d-130"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="07a1d-131">會話針對「錯誤」狀態觸發 ReceiveSendQuality 事件的百分比。</span><span class="sxs-lookup"><span data-stu-id="07a1d-131">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="07a1d-132">在抖動或資料包遺失方面的網路品質很嚴重，而且會影響接收的音訊品質。</span><span class="sxs-lookup"><span data-stu-id="07a1d-132">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

