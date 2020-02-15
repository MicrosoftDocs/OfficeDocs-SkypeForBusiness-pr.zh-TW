---
title: 'Lync Server 2013: VideoClientEvent 表格'
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
ms.openlocfilehash: 63a0bf66a7b09801bea94e8995757543511e298e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007262"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videoclientevent-table-in-lync-server-2013"></a><span data-ttu-id="ae8be-102">Lync Server 2013 中的 VideoClientEvent 表格</span><span class="sxs-lookup"><span data-stu-id="ae8be-102">VideoClientEvent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae8be-103">_**主題上次修改日期：** 2012年-10-02_</span><span class="sxs-lookup"><span data-stu-id="ae8be-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ae8be-104">每一筆記錄含有一個端點視訊通話中的用戶端事件。</span><span class="sxs-lookup"><span data-stu-id="ae8be-104">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="ae8be-105">通常，一次呼叫會有兩個記錄、 一個來電者，一個用於受話者。</span><span class="sxs-lookup"><span data-stu-id="ae8be-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ae8be-106"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="ae8be-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ae8be-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="ae8be-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ae8be-108"><strong>主索引鍵 /</strong></span><span class="sxs-lookup"><span data-stu-id="ae8be-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ae8be-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="ae8be-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ae8be-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="ae8be-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ae8be-111">datetime</span><span class="sxs-lookup"><span data-stu-id="ae8be-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="ae8be-112">主要</span><span class="sxs-lookup"><span data-stu-id="ae8be-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="ae8be-113">參考來源： <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的來源： MediaLine table</a>。</span><span class="sxs-lookup"><span data-stu-id="ae8be-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae8be-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ae8be-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ae8be-115">int</span><span class="sxs-lookup"><span data-stu-id="ae8be-115">int</span></span></p></td>
<td><p><span data-ttu-id="ae8be-116">主要</span><span class="sxs-lookup"><span data-stu-id="ae8be-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="ae8be-117">參考來源： <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的來源： MediaLine table</a>。</span><span class="sxs-lookup"><span data-stu-id="ae8be-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae8be-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="ae8be-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="ae8be-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="ae8be-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ae8be-120">主要</span><span class="sxs-lookup"><span data-stu-id="ae8be-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="ae8be-121">參考來源： <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的來源： MediaLine table</a>。</span><span class="sxs-lookup"><span data-stu-id="ae8be-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae8be-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="ae8be-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="ae8be-123">位元</span><span class="sxs-lookup"><span data-stu-id="ae8be-123">bit</span></span></p></td>
<td><p><span data-ttu-id="ae8be-124">主要</span><span class="sxs-lookup"><span data-stu-id="ae8be-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="ae8be-125">0： 受話者的資料</span><span class="sxs-lookup"><span data-stu-id="ae8be-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="ae8be-126">1： 發話者的資料</span><span class="sxs-lookup"><span data-stu-id="ae8be-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae8be-127"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="ae8be-127"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ae8be-128">工作階段百分比 LowBandwidth 事件引發 「 故障 」 狀態。</span><span class="sxs-lookup"><span data-stu-id="ae8be-128">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="ae8be-129">可用的頻寬不足的可接受的語音體驗。</span><span class="sxs-lookup"><span data-stu-id="ae8be-129">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae8be-130"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="ae8be-130"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ae8be-131">工作階段百分比 receivesendquality 「 故障 」 狀態。</span><span class="sxs-lookup"><span data-stu-id="ae8be-131">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="ae8be-132">在網路品質來說抖動或封包遺失相當嚴重，且會影響所接收的音訊品質。</span><span class="sxs-lookup"><span data-stu-id="ae8be-132">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

