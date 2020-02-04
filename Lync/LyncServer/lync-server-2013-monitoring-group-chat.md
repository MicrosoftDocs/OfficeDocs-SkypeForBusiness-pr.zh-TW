---
title: Lync Server 2013：監視群組聊天
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring group chat
ms:assetid: bddcf0be-ebf3-46bc-90c7-2576877734fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720924(v=OCS.15)
ms:contentKeyID: 63969648
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa350924503f430ec0494cc5e1eb17f7878084a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756847"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-group-chat-in-lync-server-2013"></a><span data-ttu-id="ddb20-102">在 Lync Server 2013 中監視群組聊天</span><span class="sxs-lookup"><span data-stu-id="ddb20-102">Monitoring group chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ddb20-103">_**主題上次修改日期：** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="ddb20-103">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="ddb20-104">我們強烈建議您執行 Microsoft 下載中心提供的最新[累計伺服器更新安裝程式](http://support.microsoft.com/kb/968802)，以改善效能。</span><span class="sxs-lookup"><span data-stu-id="ddb20-104">We highly recommend running the most recent [Cumulative Server Update Installer](http://support.microsoft.com/kb/968802) available on the Microsoft Download Center for performance improvements.</span></span>

<span data-ttu-id="ddb20-105">假設您執行的是最新累計更新，請使用下列壓力測試資料表，以瞭解您的群組聊天伺服器是否正在最佳健康情況下執行。</span><span class="sxs-lookup"><span data-stu-id="ddb20-105">Assuming you are running latest cumulative update, use the following stress test table for metrics to understand if your Group Chat Servers are running at optimal health.</span></span>

### <a name="test-environment-and-user-model"></a><span data-ttu-id="ddb20-106">測試環境與使用者模型</span><span class="sxs-lookup"><span data-stu-id="ddb20-106">Test environment and user model</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ddb20-107">群組聊天區中的三個群組聊天伺服器，每個都有 8 GB 的記憶體和8個處理器。</span><span class="sxs-lookup"><span data-stu-id="ddb20-107">Three Group Chat Servers in a Group Chat pool, each with 8 GB memory and 8 processors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ddb20-108">在企業版中，有兩個 Lync Server 2013 前端。</span><span class="sxs-lookup"><span data-stu-id="ddb20-108">Two Lync Server 2013 Front Ends in Enterprise Edition.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ddb20-109">60000在三個群組聊天伺服器上併發使用者。</span><span class="sxs-lookup"><span data-stu-id="ddb20-109">60,000 concurrent users across three Group Chat Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ddb20-110">由群組聊天池託管的25000頻道。</span><span class="sxs-lookup"><span data-stu-id="ddb20-110">25,000 channels hosted by Group Chat Pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ddb20-111">頻道大小：</span><span class="sxs-lookup"><span data-stu-id="ddb20-111">Channel Size:</span></span></p>
<ul>
<li><p><span data-ttu-id="ddb20-112">小型頻道大小：30</span><span class="sxs-lookup"><span data-stu-id="ddb20-112">Small Channel Size: 30</span></span></p></li>
<li><p><span data-ttu-id="ddb20-113">中等通道大小：150</span><span class="sxs-lookup"><span data-stu-id="ddb20-113">Medium Channel Size: 150</span></span></p></li>
<li><p><span data-ttu-id="ddb20-114">大型通道大小：2500</span><span class="sxs-lookup"><span data-stu-id="ddb20-114">Large Channel Size: 2500</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ddb20-115">頻道計數：</span><span class="sxs-lookup"><span data-stu-id="ddb20-115">Channel Count:</span></span></p>
<ul>
<li><p><span data-ttu-id="ddb20-116">數位小型頻道：24000</span><span class="sxs-lookup"><span data-stu-id="ddb20-116">Number small channels: 24,000</span></span></p></li>
<li><p><span data-ttu-id="ddb20-117">數位中型頻道800</span><span class="sxs-lookup"><span data-stu-id="ddb20-117">Number medium channels 800</span></span></p></li>
<li><p><span data-ttu-id="ddb20-118">將大型頻道編號24</span><span class="sxs-lookup"><span data-stu-id="ddb20-118">Number large channels 24</span></span></p></li>
<li><p><span data-ttu-id="ddb20-119">通道總24824</span><span class="sxs-lookup"><span data-stu-id="ddb20-119">Total Channels 24,824</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ddb20-120">邀請頻道：</span><span class="sxs-lookup"><span data-stu-id="ddb20-120">Invite channels:</span></span></p>
<ul>
<li><p><span data-ttu-id="ddb20-121">頻道的一半是邀請頻道</span><span class="sxs-lookup"><span data-stu-id="ddb20-121">Half the channels were invite channels</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ddb20-122">使用者加入的頻道數目：</span><span class="sxs-lookup"><span data-stu-id="ddb20-122">Number of channels a user joins:</span></span></p>
<ul>
<li><p><span data-ttu-id="ddb20-123">小：12</span><span class="sxs-lookup"><span data-stu-id="ddb20-123">Small: 12</span></span></p></li>
<li><p><span data-ttu-id="ddb20-124">中：2</span><span class="sxs-lookup"><span data-stu-id="ddb20-124">Medium: 2</span></span></p></li>
<li><p><span data-ttu-id="ddb20-125">大型：1</span><span class="sxs-lookup"><span data-stu-id="ddb20-125">Large: 1</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ddb20-126">聯接速率：</span><span class="sxs-lookup"><span data-stu-id="ddb20-126">Join rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="ddb20-127">每個伺服器共有10個總/秒、3.33/秒</span><span class="sxs-lookup"><span data-stu-id="ddb20-127">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ddb20-128">登出頻率：</span><span class="sxs-lookup"><span data-stu-id="ddb20-128">Logout rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="ddb20-129">每個伺服器共有10個總/秒、3.33/秒</span><span class="sxs-lookup"><span data-stu-id="ddb20-129">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ddb20-130">聊天速度：</span><span class="sxs-lookup"><span data-stu-id="ddb20-130">Chat rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="ddb20-131">每個伺服器總共20個總計/秒、6.66/秒</span><span class="sxs-lookup"><span data-stu-id="ddb20-131">20 total/second, 6.66/second per server</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="ddb20-132">使用不同的硬體規格或使用者設定檔時，可能會有下列效能計數器數值。</span><span class="sxs-lookup"><span data-stu-id="ddb20-132">The following performance counter numbers will likely vary when different hardware specifications or user profiles are used.</span></span>



</div>

### <a name="performance-counter-to-be-monitored"></a><span data-ttu-id="ddb20-133">要監視的效能計數器</span><span class="sxs-lookup"><span data-stu-id="ddb20-133">Performance counter to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ddb20-134">效能計數器</span><span class="sxs-lookup"><span data-stu-id="ddb20-134">Performance Counter</span></span></th>
<th><span data-ttu-id="ddb20-135">閾值</span><span class="sxs-lookup"><span data-stu-id="ddb20-135">Thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ddb20-136">Process （ChannelService）-&gt;處理器時間百分比</span><span class="sxs-lookup"><span data-stu-id="ddb20-136">Process(ChannelService)-&gt;%Processor Time</span></span></p></td>
<td><p><span data-ttu-id="ddb20-137">Min：0</span><span class="sxs-lookup"><span data-stu-id="ddb20-137">Min: 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

