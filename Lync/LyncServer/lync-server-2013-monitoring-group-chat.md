---
title: Lync Server 2013： 監控群組聊天
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
ms.openlocfilehash: cb82eedd9d9578aeb4120136c1896267cde35392
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051135"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-group-chat-in-lync-server-2013"></a><span data-ttu-id="ace1c-102">Lync Server 2013 中的監視群組聊天</span><span class="sxs-lookup"><span data-stu-id="ace1c-102">Monitoring group chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ace1c-103">_**上次修改主題：** 2014年-08-04_</span><span class="sxs-lookup"><span data-stu-id="ace1c-103">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="ace1c-104">我們強烈建議的效能改進 Microsoft 下載中心上執行提供最新[累計伺服器更新安裝程式](http://support.microsoft.com/kb/968802)。</span><span class="sxs-lookup"><span data-stu-id="ace1c-104">We highly recommend running the most recent [Cumulative Server Update Installer](http://support.microsoft.com/kb/968802) available on the Microsoft Download Center for performance improvements.</span></span>

<span data-ttu-id="ace1c-105">假設您正在執行最新累計更新，使用下列計量壓力測試表了解是否您群組聊天伺服器正在執行在最佳的狀況。</span><span class="sxs-lookup"><span data-stu-id="ace1c-105">Assuming you are running latest cumulative update, use the following stress test table for metrics to understand if your Group Chat Servers are running at optimal health.</span></span>

### <a name="test-environment-and-user-model"></a><span data-ttu-id="ace1c-106">測試環境與使用者模型</span><span class="sxs-lookup"><span data-stu-id="ace1c-106">Test environment and user model</span></span>

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
<td><p><span data-ttu-id="ace1c-107">三部群組聊天伺服器的 Group Chat 集區、 每個需要 8 GB 記憶體和 8 處理器。</span><span class="sxs-lookup"><span data-stu-id="ace1c-107">Three Group Chat Servers in a Group Chat pool, each with 8 GB memory and 8 processors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ace1c-108">兩個 Lync Server 2013 Enterprise Edition 中結束前方。</span><span class="sxs-lookup"><span data-stu-id="ace1c-108">Two Lync Server 2013 Front Ends in Enterprise Edition.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ace1c-109">跨三個群組聊天伺服器的 60000 位並行使用者。</span><span class="sxs-lookup"><span data-stu-id="ace1c-109">60,000 concurrent users across three Group Chat Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ace1c-110">群組聊天集區所主控的 25000 通道。</span><span class="sxs-lookup"><span data-stu-id="ace1c-110">25,000 channels hosted by Group Chat Pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ace1c-111">通道大小：</span><span class="sxs-lookup"><span data-stu-id="ace1c-111">Channel Size:</span></span></p>
<ul>
<li><p><span data-ttu-id="ace1c-112">小型通道大小： 30</span><span class="sxs-lookup"><span data-stu-id="ace1c-112">Small Channel Size: 30</span></span></p></li>
<li><p><span data-ttu-id="ace1c-113">中型通道大小： 150</span><span class="sxs-lookup"><span data-stu-id="ace1c-113">Medium Channel Size: 150</span></span></p></li>
<li><p><span data-ttu-id="ace1c-114">大型通道大小： 2500年</span><span class="sxs-lookup"><span data-stu-id="ace1c-114">Large Channel Size: 2500</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ace1c-115">通道計數：</span><span class="sxs-lookup"><span data-stu-id="ace1c-115">Channel Count:</span></span></p>
<ul>
<li><p><span data-ttu-id="ace1c-116">數字小通道： 24000</span><span class="sxs-lookup"><span data-stu-id="ace1c-116">Number small channels: 24,000</span></span></p></li>
<li><p><span data-ttu-id="ace1c-117">數字中型通道 800</span><span class="sxs-lookup"><span data-stu-id="ace1c-117">Number medium channels 800</span></span></p></li>
<li><p><span data-ttu-id="ace1c-118">數字大型通道 24</span><span class="sxs-lookup"><span data-stu-id="ace1c-118">Number large channels 24</span></span></p></li>
<li><p><span data-ttu-id="ace1c-119">總通道 24,824</span><span class="sxs-lookup"><span data-stu-id="ace1c-119">Total Channels 24,824</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ace1c-120">邀請通道：</span><span class="sxs-lookup"><span data-stu-id="ace1c-120">Invite channels:</span></span></p>
<ul>
<li><p><span data-ttu-id="ace1c-121">一半的通道已邀請通道</span><span class="sxs-lookup"><span data-stu-id="ace1c-121">Half the channels were invite channels</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ace1c-122">使用者加入的通道數目：</span><span class="sxs-lookup"><span data-stu-id="ace1c-122">Number of channels a user joins:</span></span></p>
<ul>
<li><p><span data-ttu-id="ace1c-123">小型： 12</span><span class="sxs-lookup"><span data-stu-id="ace1c-123">Small: 12</span></span></p></li>
<li><p><span data-ttu-id="ace1c-124">中型： 2</span><span class="sxs-lookup"><span data-stu-id="ace1c-124">Medium: 2</span></span></p></li>
<li><p><span data-ttu-id="ace1c-125">大型： 1</span><span class="sxs-lookup"><span data-stu-id="ace1c-125">Large: 1</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ace1c-126">加入速率：</span><span class="sxs-lookup"><span data-stu-id="ace1c-126">Join rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="ace1c-127">10 總計/秒，每部伺服器的 3.33/秒</span><span class="sxs-lookup"><span data-stu-id="ace1c-127">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ace1c-128">登出率：</span><span class="sxs-lookup"><span data-stu-id="ace1c-128">Logout rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="ace1c-129">10 總計/秒，每部伺服器的 3.33/秒</span><span class="sxs-lookup"><span data-stu-id="ace1c-129">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ace1c-130">聊天速率：</span><span class="sxs-lookup"><span data-stu-id="ace1c-130">Chat rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="ace1c-131">20 總計/秒，6.66] / 秒每個伺服器</span><span class="sxs-lookup"><span data-stu-id="ace1c-131">20 total/second, 6.66/second per server</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="ace1c-132">使用不同的硬體規格或使用者設定檔時，可能會有所不同下列效能計數器數字。</span><span class="sxs-lookup"><span data-stu-id="ace1c-132">The following performance counter numbers will likely vary when different hardware specifications or user profiles are used.</span></span>



</div>

### <a name="performance-counter-to-be-monitored"></a><span data-ttu-id="ace1c-133">要監視的效能計數器</span><span class="sxs-lookup"><span data-stu-id="ace1c-133">Performance counter to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ace1c-134">效能計數器</span><span class="sxs-lookup"><span data-stu-id="ace1c-134">Performance Counter</span></span></th>
<th><span data-ttu-id="ace1c-135">臨界值</span><span class="sxs-lookup"><span data-stu-id="ace1c-135">Thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ace1c-136">Process(ChannelService)-&gt;%處理器時間</span><span class="sxs-lookup"><span data-stu-id="ace1c-136">Process(ChannelService)-&gt;%Processor Time</span></span></p></td>
<td><p><span data-ttu-id="ace1c-137">最小值： 0</span><span class="sxs-lookup"><span data-stu-id="ace1c-137">Min: 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

