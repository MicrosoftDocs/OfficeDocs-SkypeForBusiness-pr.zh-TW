---
title: Lync Server 2013：監控群組聊天
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
ms.openlocfilehash: cf44bbaa00412de24af21c493fd05b88bd6259af
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531930"
---
# <a name="monitoring-group-chat-in-lync-server-2013"></a><span data-ttu-id="906eb-102">在 Lync Server 2013 中監控群組聊天</span><span class="sxs-lookup"><span data-stu-id="906eb-102">Monitoring group chat in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="906eb-103">_**主題上次修改日期：** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="906eb-103">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="906eb-104">強烈建議您在 Microsoft 下載中心上執行最新的 [累積伺服器更新安裝程式](https://support.microsoft.com/kb/968802) ，以改善效能。</span><span class="sxs-lookup"><span data-stu-id="906eb-104">We highly recommend running the most recent [Cumulative Server Update Installer](https://support.microsoft.com/kb/968802) available on the Microsoft Download Center for performance improvements.</span></span>

<span data-ttu-id="906eb-105">假設您正在執行最新的累計更新，請使用下列壓力測試表格，以瞭解您的群組聊天伺服器是否在最佳狀況下執行。</span><span class="sxs-lookup"><span data-stu-id="906eb-105">Assuming you are running latest cumulative update, use the following stress test table for metrics to understand if your Group Chat Servers are running at optimal health.</span></span>

### <a name="test-environment-and-user-model"></a><span data-ttu-id="906eb-106">測試環境和使用者模型</span><span class="sxs-lookup"><span data-stu-id="906eb-106">Test environment and user model</span></span>

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
<td><p><span data-ttu-id="906eb-107">群組聊天集區中的三個群組聊天伺服器，每個都有 8 GB 的記憶體和8個處理器。</span><span class="sxs-lookup"><span data-stu-id="906eb-107">Three Group Chat Servers in a Group Chat pool, each with 8 GB memory and 8 processors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="906eb-108">Enterprise Edition 中的兩部 Lync Server 2013 前端。</span><span class="sxs-lookup"><span data-stu-id="906eb-108">Two Lync Server 2013 Front Ends in Enterprise Edition.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="906eb-109">60000三個群組聊天伺服器的並行使用者。</span><span class="sxs-lookup"><span data-stu-id="906eb-109">60,000 concurrent users across three Group Chat Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="906eb-110">由群組聊天集區主控的25000通道。</span><span class="sxs-lookup"><span data-stu-id="906eb-110">25,000 channels hosted by Group Chat Pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="906eb-111">通道大小：</span><span class="sxs-lookup"><span data-stu-id="906eb-111">Channel Size:</span></span></p>
<ul>
<li><p><span data-ttu-id="906eb-112">小通道大小：30</span><span class="sxs-lookup"><span data-stu-id="906eb-112">Small Channel Size: 30</span></span></p></li>
<li><p><span data-ttu-id="906eb-113">中型通道大小：150</span><span class="sxs-lookup"><span data-stu-id="906eb-113">Medium Channel Size: 150</span></span></p></li>
<li><p><span data-ttu-id="906eb-114">大通道大小：2500</span><span class="sxs-lookup"><span data-stu-id="906eb-114">Large Channel Size: 2500</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="906eb-115">通道計數：</span><span class="sxs-lookup"><span data-stu-id="906eb-115">Channel Count:</span></span></p>
<ul>
<li><p><span data-ttu-id="906eb-116">數位小型通道：24000</span><span class="sxs-lookup"><span data-stu-id="906eb-116">Number small channels: 24,000</span></span></p></li>
<li><p><span data-ttu-id="906eb-117">數位中型通道800</span><span class="sxs-lookup"><span data-stu-id="906eb-117">Number medium channels 800</span></span></p></li>
<li><p><span data-ttu-id="906eb-118">數位大通道24</span><span class="sxs-lookup"><span data-stu-id="906eb-118">Number large channels 24</span></span></p></li>
<li><p><span data-ttu-id="906eb-119">通道總數24824</span><span class="sxs-lookup"><span data-stu-id="906eb-119">Total Channels 24,824</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="906eb-120">邀請通道：</span><span class="sxs-lookup"><span data-stu-id="906eb-120">Invite channels:</span></span></p>
<ul>
<li><p><span data-ttu-id="906eb-121">一半通道邀請通道</span><span class="sxs-lookup"><span data-stu-id="906eb-121">Half the channels were invite channels</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="906eb-122">使用者加入的通道數目：</span><span class="sxs-lookup"><span data-stu-id="906eb-122">Number of channels a user joins:</span></span></p>
<ul>
<li><p><span data-ttu-id="906eb-123">Small：12</span><span class="sxs-lookup"><span data-stu-id="906eb-123">Small: 12</span></span></p></li>
<li><p><span data-ttu-id="906eb-124">中：2</span><span class="sxs-lookup"><span data-stu-id="906eb-124">Medium: 2</span></span></p></li>
<li><p><span data-ttu-id="906eb-125">大：1</span><span class="sxs-lookup"><span data-stu-id="906eb-125">Large: 1</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="906eb-126">聯接率：</span><span class="sxs-lookup"><span data-stu-id="906eb-126">Join rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="906eb-127">每個伺服器每秒10個總計/秒、3.33/秒</span><span class="sxs-lookup"><span data-stu-id="906eb-127">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="906eb-128">登出率：</span><span class="sxs-lookup"><span data-stu-id="906eb-128">Logout rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="906eb-129">每個伺服器每秒10個總計/秒、3.33/秒</span><span class="sxs-lookup"><span data-stu-id="906eb-129">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="906eb-130">交談速度：</span><span class="sxs-lookup"><span data-stu-id="906eb-130">Chat rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="906eb-131">每個伺服器總共20個、每秒 6.66/秒</span><span class="sxs-lookup"><span data-stu-id="906eb-131">20 total/second, 6.66/second per server</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="906eb-132">使用不同的硬體規格或使用者設定檔時，可能會發生下列效能計數器數目。</span><span class="sxs-lookup"><span data-stu-id="906eb-132">The following performance counter numbers will likely vary when different hardware specifications or user profiles are used.</span></span>



</div>

### <a name="performance-counter-to-be-monitored"></a><span data-ttu-id="906eb-133">要監視的效能計數器</span><span class="sxs-lookup"><span data-stu-id="906eb-133">Performance counter to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="906eb-134">效能計數器</span><span class="sxs-lookup"><span data-stu-id="906eb-134">Performance Counter</span></span></th>
<th><span data-ttu-id="906eb-135">閾 值</span><span class="sxs-lookup"><span data-stu-id="906eb-135">Thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="906eb-136">處理 (ChannelService) &gt; 處理器時間</span><span class="sxs-lookup"><span data-stu-id="906eb-136">Process(ChannelService)-&gt;%Processor Time</span></span></p></td>
<td><p><span data-ttu-id="906eb-137">最小值：0</span><span class="sxs-lookup"><span data-stu-id="906eb-137">Min: 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

