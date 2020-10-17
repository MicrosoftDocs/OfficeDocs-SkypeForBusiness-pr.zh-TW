---
title: Lync Server 2013： VideoClientEvent 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoClientEvent table
ms:assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399039(v=OCS.15)
ms:contentKeyID: 48185891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9282af929757a4703f40537cb94d50761b1ac422
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527580"
---
# <a name="videoclientevent-table-in-lync-server-2013"></a><span data-ttu-id="63c3f-102">Lync Server 2013 中的 VideoClientEvent 表格</span><span class="sxs-lookup"><span data-stu-id="63c3f-102">VideoClientEvent table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63c3f-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="63c3f-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="63c3f-104">每個記錄在影片通話中包含一個端點的用戶端事件。</span><span class="sxs-lookup"><span data-stu-id="63c3f-104">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="63c3f-105">通常，一個呼叫有兩筆記錄，一個用於來電者，另一個用於呼叫者。</span><span class="sxs-lookup"><span data-stu-id="63c3f-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="63c3f-106"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="63c3f-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="63c3f-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="63c3f-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="63c3f-108"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="63c3f-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="63c3f-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="63c3f-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="63c3f-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="63c3f-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="63c3f-111">datetime</span><span class="sxs-lookup"><span data-stu-id="63c3f-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="63c3f-112">主要</span><span class="sxs-lookup"><span data-stu-id="63c3f-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="63c3f-113">從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="63c3f-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63c3f-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="63c3f-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="63c3f-115">int</span><span class="sxs-lookup"><span data-stu-id="63c3f-115">int</span></span></p></td>
<td><p><span data-ttu-id="63c3f-116">主要</span><span class="sxs-lookup"><span data-stu-id="63c3f-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="63c3f-117">從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="63c3f-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63c3f-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="63c3f-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="63c3f-119">Tinyint</span><span class="sxs-lookup"><span data-stu-id="63c3f-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="63c3f-120">主要</span><span class="sxs-lookup"><span data-stu-id="63c3f-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="63c3f-121">從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="63c3f-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63c3f-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="63c3f-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="63c3f-123">位</span><span class="sxs-lookup"><span data-stu-id="63c3f-123">bit</span></span></p></td>
<td><p><span data-ttu-id="63c3f-124">主要</span><span class="sxs-lookup"><span data-stu-id="63c3f-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="63c3f-125">0：被呼叫者的資料</span><span class="sxs-lookup"><span data-stu-id="63c3f-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="63c3f-126">1：來電者的資料</span><span class="sxs-lookup"><span data-stu-id="63c3f-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63c3f-127"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="63c3f-127"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="63c3f-128">會話百分比 LowBandwidth 事件引發「不良」狀態。</span><span class="sxs-lookup"><span data-stu-id="63c3f-128">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="63c3f-129">可用的頻寬不足以取得可接受的語音體驗。</span><span class="sxs-lookup"><span data-stu-id="63c3f-129">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63c3f-130"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="63c3f-130"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="63c3f-131">會話百分比已針對 ' 壞」狀態引發 ReceiveSendQuality 事件。</span><span class="sxs-lookup"><span data-stu-id="63c3f-131">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="63c3f-132">抖動或封包遺失方面的網路品質很嚴重，且會影響所接收的音訊品質。</span><span class="sxs-lookup"><span data-stu-id="63c3f-132">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

