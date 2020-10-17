---
title: Lync Server 2013：監控 Lync Server 效能
description: Lync Server 2013：監控 Lync Server 效能。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring Lync Server 2013 performance
ms:assetid: 2acfd720-6120-4816-a2d4-30476bd5cd0e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720910(v=OCS.15)
ms:contentKeyID: 63969592
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efe63a881c9db105fc36a1ccd0b0fdc15086a36f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548099"
---
# <a name="monitoring-lync-server-2013-performance"></a><span data-ttu-id="ec6cb-103">監視 Lync Server 2013 效能</span><span class="sxs-lookup"><span data-stu-id="ec6cb-103">Monitoring Lync Server 2013 performance</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec6cb-104">_**主題上次修改日期：** 2014-05-15_</span><span class="sxs-lookup"><span data-stu-id="ec6cb-104">_**Topic Last Modified:** 2014-05-15_</span></span>

<span data-ttu-id="ec6cb-105">Lync Server 2013 的效能受到各種因素的影響，例如使用者設定檔、系統架構、軟體、硬體元件、協力廠商整合點，例如閘道和電話語音設備、網路連線和效能、Windows Active Directory 服務設定和效能，以及 Windows 作業系統功能。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-105">Lync Server 2013 performance is affected by various factors such as user profiles, system architecture, software, hardware components, third-party integration points such as gateways and telephony equipment, network connectivity and performance, Windows Active Directory service configuration and performance in addition to the Windows operating system functionality.</span></span>

<span data-ttu-id="ec6cb-106">在 Lync Server 2013 部署的核心上，其效能是指執行它的伺服器軟體和硬體。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-106">At the core of a Lync Server 2013 deployments’ performance is the server software and hardware it is implemented on.</span></span> <span data-ttu-id="ec6cb-107">舉例來說，前端伺服器必須有足夠的硬體資源，才能處理預期的 (短期) 使用者負載。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-107">As an example, a front-end server must have sufficient hardware resources to cope with the expected (short-term) user load.</span></span> <span data-ttu-id="ec6cb-108">如果需要個別的前端伺服器來提供服務給10000使用者，則經過適當設定的伺服器必須符合預期的負載需求，才能最終協助確保最佳的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-108">If a respective front-end server is required to provide services to 10 thousand users, then an adequately configured server must meet the expected load requirements to ultimately help ensure the best possible end-user experience.</span></span>

<span data-ttu-id="ec6cb-109">因此，監控伺服器效能是極其重要的一點，就是衡量所實施的伺服器基礎結構是否具備日常峰值負載需求的硬體資源。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-109">Monitoring server performance is therefore extremely important to gauge whether the implemented server infrastructure have suitable hardware resources for the day-to-day peak-load requirements.</span></span> <span data-ttu-id="ec6cb-110">監控伺服器效能可協助識別系統瓶頸，讓系統管理員在使用者體驗受到影響之前套用糾正動作。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-110">Monitoring server performance helps identify system bottlenecks allowing administrators to apply corrective action before the end-user experience is affected.</span></span> <span data-ttu-id="ec6cb-111">效能資料應該用於長期容量規劃。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-111">The performance data should be used for long-term capacity planning.</span></span>

<span data-ttu-id="ec6cb-112">在 [使用 System Center Operations Manager 監視 Lync Server 2013](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)的所有效能物件和計數器相關的詳細資訊中，您應該遵循的一些效能計數器，可讓系統管理員快速瞭解系統效能：</span><span class="sxs-lookup"><span data-stu-id="ec6cb-112">While detailed information on all performance objects and counters to be observed is linked to in [Monitoring Lync Server 2013 with System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md), some performance counters that you should follow can provide administrators a quick view of the system performance:</span></span>

  - <span data-ttu-id="ec6cb-113">為了追蹤前端伺服器的整體系統健康情況，良好的開始點是檢查處理器 \\ % Processor Time。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-113">To track overall system health of the front-end server, a good starting point is to check Processor\\% Processor Time.</span></span> <span data-ttu-id="ec6cb-114">該值應永遠低於80%。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-114">The value should always be below 80 percent.</span></span>

  - <span data-ttu-id="ec6cb-115">若要追蹤前端集區所使用的後端 SQL Server 資料庫軟體實例效能，請監視下列效能計數器：</span><span class="sxs-lookup"><span data-stu-id="ec6cb-115">To track the performance of the back end SQL Server database software instance used by the Front End pool, monitor the following performance counters:</span></span>
    
    <span data-ttu-id="ec6cb-116">LC： USrv –00– DBStore \\ USrv –002–佇列延遲 (毫秒) </span><span class="sxs-lookup"><span data-stu-id="ec6cb-116">LC:USrv – 00 – DBStore\\Usrv – 002 – Queue Latency (msec)</span></span>
    
    <span data-ttu-id="ec6cb-117">LC： USrv –00– DBStore \\ USrv – 0 04 –對等是延隔時間 (毫秒) </span><span class="sxs-lookup"><span data-stu-id="ec6cb-117">LC:USrv – 00 – DBStore\\Usrv – 0 04– Sproc Latency (msec)</span></span>
    
    <span data-ttu-id="ec6cb-118">處於穩定狀態的狀況良好伺服器應該會顯示 \< 100 毫秒的延遲值。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-118">The healthy server at steady state should show \<100 ms latency values.</span></span> <span data-ttu-id="ec6cb-119">當延遲達到12秒時，節流機制會接洽，這表示前端伺服器會對後端伺服器開始節流要求。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-119">The throttling mechanism will engage when latency reaches 12 seconds, which means the front-end server starts throttling requests to the back end.</span></span> <span data-ttu-id="ec6cb-120">這會導致用戶端無法接收503伺服器太忙碌的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-120">This causes clients to start to receive a 503 Server too busy error message.</span></span>

  - <span data-ttu-id="ec6cb-121">若要追蹤前端伺服器的處理時間，請監視下列計數器：</span><span class="sxs-lookup"><span data-stu-id="ec6cb-121">To track the processing time at the front-end server, monitor the following counter:</span></span>
    
    <span data-ttu-id="ec6cb-122">LC： SIP-07-Load Management \\ sip-000-內送郵件的平均保留時間</span><span class="sxs-lookup"><span data-stu-id="ec6cb-122">LC:SIP - 07 - Load Management\\SIP - 000 - Average Holding Time For Incoming Messages</span></span>
    
    <span data-ttu-id="ec6cb-123">在前端伺服器上，這是另一種節流機制，當前端的處理時間很高時，就會開始。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-123">This is another throttling mechanism on the front-end servers, this time starting when the processing time on the front end is high.</span></span> <span data-ttu-id="ec6cb-124">如果平均處理時間超過六秒，則伺服器會進入節流模式，且每個用戶端連接只允許一個未完成的交易。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-124">If average processing time is more than six seconds, the server goes into throttling mode and only allows one outstanding transaction per client connection.</span></span>

  - <span data-ttu-id="ec6cb-125">若要追蹤 SQL 後端伺服器的記憶體問題，請監視下列計數器：</span><span class="sxs-lookup"><span data-stu-id="ec6cb-125">To track memory issues at SQL Back End Server, monitor the following counter:</span></span>
    
    <span data-ttu-id="ec6cb-126">SQL Server 緩衝區管理員 \\ 頁面壽命預期</span><span class="sxs-lookup"><span data-stu-id="ec6cb-126">SQL Server Buffer Manager\\Page life expectancy</span></span>
    
    <span data-ttu-id="ec6cb-127">低值，低於3600秒 (和高延遲寫入次數/秒及檢查點頁數/秒) 表示記憶體壓力。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-127">A low value, below 3600 seconds (together with high latency writes/sec and checkpoint pages/sec) indicates memory pressure.</span></span>

<div>

## <a name="additional-counters-to-view"></a><span data-ttu-id="ec6cb-128">要查看的其他計數器</span><span class="sxs-lookup"><span data-stu-id="ec6cb-128">Additional Counters to View</span></span>

<span data-ttu-id="ec6cb-129">有幾個主要計數器是前端伺服器的整體健康情況很好的指示器。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-129">There are several key counters that are good indicators of overall health from the front end server.</span></span> <span data-ttu-id="ec6cb-130">這不是一個完整的清單，而且不是用來識別根本原因。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-130">This is not a comprehensive list and is not meant to identify root cause.</span></span> <span data-ttu-id="ec6cb-131">這些計數器可讓您對伺服器健康情況執行快速檢查。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-131">These counters will let you perform a quick check on your server health.</span></span> <span data-ttu-id="ec6cb-132">建議您在集區中的每一部伺服器上驗證這些計數器。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-132">We recommend verifying these counters on each of the servers in the pool.</span></span> <span data-ttu-id="ec6cb-133">請務必瞭解當伺服器狀況良好時，這些計數器值的含義。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-133">It is important to understand what these counter values are when your server is healthy.</span></span> <span data-ttu-id="ec6cb-134">需要有基準，以瞭解使用者體驗降級時所發生的變更。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-134">A baseline is required to understand what changed when the user experience is degraded.</span></span>

<span data-ttu-id="ec6cb-135">前端伺服器可以指出可能是由系統中其他地方的瓶頸所造成的問題。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-135">The front-end server can indicate issues that may be caused by bottlenecks elsewhere in the system.</span></span> <span data-ttu-id="ec6cb-136">這表示在查看整體系統健康情況時，最佳的開始位置。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-136">This means that it is the best place to start when looking at overall system health.</span></span>

<span data-ttu-id="ec6cb-137">以下是另一個複查的計數器：</span><span class="sxs-lookup"><span data-stu-id="ec6cb-137">Two additional counters to review first are as follows:</span></span>

<span data-ttu-id="ec6cb-138">LC： USrv-00-DBStore \\ USrv-002-佇列延遲 (毫秒) </span><span class="sxs-lookup"><span data-stu-id="ec6cb-138">LC:USrv-00-DBStore\\Usrv-002-Queue Latency (msec)</span></span>

<span data-ttu-id="ec6cb-139">LC： USrv-00-DBStore \\ USrv-004 (-) </span><span class="sxs-lookup"><span data-stu-id="ec6cb-139">LC:USrv-00-DBStore\\Usrv-004-Sproc Latency (msec)</span></span>

<span data-ttu-id="ec6cb-140">佇列延遲計數器代表佇列中對後端的要求所花費的時間，而處理常式延遲代表後端處理要求所需的時間。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-140">The queue latency counter represents the time that a request spent in the queue to the back end and the Sproc latency represents the time that it took for the back end to process the request.</span></span> <span data-ttu-id="ec6cb-141">若由於任何原因，在後端的磁片、記憶體、網路及處理器都有問題，佇列延遲計數器會高。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-141">If, for any reason, disk, memory, network, and processor on the back end are in trouble, the queue latency counter will be high.</span></span>

<span data-ttu-id="ec6cb-142">如果前端和後端之間有較高的網路延遲，也會有高的速度。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-142">It can also be high if there is high network latency between the front end and the back end.</span></span> <span data-ttu-id="ec6cb-143">那麼，哪些是可接受的佇列延遲？</span><span class="sxs-lookup"><span data-stu-id="ec6cb-143">So what is acceptable queue latency?</span></span>

<span data-ttu-id="ec6cb-144">在12秒，前端伺服器會對後端伺服器開始節流要求。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-144">At 12 seconds, the Front End Servers start throttling requests to the Back End Servers.</span></span> <span data-ttu-id="ec6cb-145">這表示伺服器開始傳回伺服器太忙碌–503錯誤到用戶端。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-145">This means the servers start returning Server too busy – 503 errors to the clients.</span></span> <span data-ttu-id="ec6cb-146">狀況良好的伺服器應該在穩定狀態下的 DBStore 佇列延遲小於100毫秒，但是在伺服器剛剛線上並且使用者同時登入的時段內，該計數器可能會非常高，甚至您可能會看到在數秒內發生一次。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-146">A healthy server should have less than 100 msec DBStore queue latencies at steady state, but during times where the server has just come online and users are all logging in at the same time, that counter can be very high and you may even see it hit multiple seconds.</span></span>

<span data-ttu-id="ec6cb-147">您可以使用負載平衡設定，在此設定中，您可以使用多部前端伺服器部署集區，以及設定為「最少連線數目」的負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-147">You may have a load-balanced configuration, where you have a pool deployed with multiple front-end servers and a load balancer that is configured for "least number of connections."</span></span> <span data-ttu-id="ec6cb-148">在此情況下，如果有一部前端伺服器已重新開機，則嘗試重新連接的所有使用者都將指向重新開機的伺服器，因為該伺服器與其他集區成員相比，其連接較少。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-148">In this case, if one front-end server is restarted, then all users who attempt to reconnect will be pointed to the restarted server, because that server will have fewer connections compared to the other pool members.</span></span> <span data-ttu-id="ec6cb-149">在這段時間內，個別的前端伺服器可能會超載，而另一個集區成員則不會。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-149">During this time, the respective front-end server may be overloaded while the other pool members are not.</span></span>

<span data-ttu-id="ec6cb-150">建議您在離時執行維護，以降低效能影響，因為使用者不會同時連接至伺服器。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-150">We recommend that you perform maintenance during off-hours to reduce the performance affect as users will not all be competing to connect to the server at the same time.</span></span>

<span data-ttu-id="ec6cb-151">如果先前的兩個效能計數器很高，則最可能的瓶頸是 SQL 後端伺服器。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-151">If the previous two performance counters are high, the most likely bottleneck is the SQL Back End Server.</span></span> <span data-ttu-id="ec6cb-152">下一個要確認的元件如下：</span><span class="sxs-lookup"><span data-stu-id="ec6cb-152">The next components to confirm are as follows:</span></span>

  - <span data-ttu-id="ec6cb-153">SQL Server CPU 是否太高？</span><span class="sxs-lookup"><span data-stu-id="ec6cb-153">Is the SQL Server CPU too high?</span></span> <span data-ttu-id="ec6cb-154">例如，它是否大於80%？</span><span class="sxs-lookup"><span data-stu-id="ec6cb-154">For example, is it greater than 80 percent?</span></span>

  - <span data-ttu-id="ec6cb-155">磁片延遲是高？</span><span class="sxs-lookup"><span data-stu-id="ec6cb-155">Is the disk latency high?</span></span>

<span data-ttu-id="ec6cb-156">在理想的世界中，您有足夠的 RAM，可在記憶體中同時使用 RTC 和 RTCDYN 資料庫。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-156">In an ideal world, you have enough RAM to have both the RTC and RTCDYN databases in memory.</span></span> <span data-ttu-id="ec6cb-157">然後，伺服器存取磁片的唯一原因是寫入記錄檔並與資料庫齊。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-157">Then, the only reason the server would be accessing the disk, is to write to the log files and flush to the databases.</span></span> <span data-ttu-id="ec6cb-158">測試顯示有 12 GB 的 RAM 足以供100000使用者部署使用。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-158">Tests have shown that 12 GB of RAM is sufficient for 100 thousand user deployments.</span></span> <span data-ttu-id="ec6cb-159">這假設 RTC 和 RTCDYN 資料庫的大小總和小於 12 GB。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-159">This assumes that the RTC and RTCDYN databases size totals less than 12 GB.</span></span> <span data-ttu-id="ec6cb-160">如果您的資料庫大於該數量，您可能需要額外的記憶體。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-160">If your databases are larger than that, then you may need additional memory.</span></span>

<span data-ttu-id="ec6cb-161">您可以查看 SQL server 緩衝區管理員頁面壽命效能計數器，以判斷您的 SQL Server 是否需要額外的 RAM。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-161">You can determine whether your SQL Server requires additional RAM by reviewing the SQL Server Buffer Manager page life expectancy performance counter.</span></span> <span data-ttu-id="ec6cb-162">小於3600的值表示記憶體壓力。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-162">A value less than 3,600 indicates memory pressure.</span></span> <span data-ttu-id="ec6cb-163">如果您有足夠的記憶體，您也應該在資料庫磁片磁碟機上看到一點很少的讀取權，因為 SQL Server 應該只寫入資料庫。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-163">You should also see little to no reads on your database drive if you have sufficient memory because SQL Server should only be writing to the database.</span></span>

<span data-ttu-id="ec6cb-164">在伺服器處理時間很高的情況中，Lync Server 2013 前端伺服器中會有額外的節流機制。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-164">There is an additional throttling mechanism in a Lync Server 2013 Front End Server that starts if the server processing time is high.</span></span> <span data-ttu-id="ec6cb-165">只有在 SQL Server 的延遲很高時，才會啟用 DBStore 延遲節流。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-165">The DBStore latency throttling is only enabled if the latency to the SQL Server is high.</span></span> <span data-ttu-id="ec6cb-166">啟用此種節流的其中一個範例是，如果前端伺服器受 CPU 限制。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-166">One example in which such throttling is enabled is if the front-end server is CPU-bound.</span></span>

<span data-ttu-id="ec6cb-167">如果平均處理時間 (LC：在伺服器上的內送 \*\* \\ 郵件的平均保留時間) \*\* 超過六秒，則伺服器會進入節流模式，並只為使用者提供每個用戶端連線一個未完成的交易。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-167">If the average processing time **(LC:SIP-07-Load Management\\SIP-000-Average Holding Time For Incoming Messages)** on the server exceeds six seconds, then the server goes into throttling mode and only gives users one outstanding transaction per client connection.</span></span> <span data-ttu-id="ec6cb-168">當處理時間降至三秒後，伺服器會中斷節流模式，並為使用者提供每個用戶端連線20個未完成的交易。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-168">Once the processing time drops to three seconds, then the server drops out of throttling mode and gives users up to 20 outstanding transactions per client connection.</span></span> <span data-ttu-id="ec6cb-169">每當特定連線的交易數目超過上述閾值時，連線就會標示為「流程式控制制」。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-169">Whenever the number of transactions on a specific connection exceeds the threshold above, the connection is marked as flow controlled.</span></span> <span data-ttu-id="ec6cb-170">結果是伺服器不會在其上張貼任何接收，而且 **LC： SIP-01 對等 \\ 流程式控制制** 的連線計數器會遞增。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-170">The result is the server does not post any receives on it, and the **LC:SIP-01-Peers\\Flow Controlled Connections** counter is incremented.</span></span> <span data-ttu-id="ec6cb-171">如果連接保持流程式控制制狀態一分鐘以上，則伺服器會將其關閉。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-171">If a connection stays in a flow-controlled state for more than one minute, then the server closes it.</span></span> <span data-ttu-id="ec6cb-172">它會以遲緩方式進行。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-172">It does so lazily.</span></span> <span data-ttu-id="ec6cb-173">當它有機會檢查連線時，它會判斷它是否被限制過長，如果超過一分鐘，就會關閉。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-173">When it has an opportunity to check the connection, it determines whether it was throttled for too long and closes it if it has more than one minute.</span></span>

<span data-ttu-id="ec6cb-174">這兩種節流機制及一個效能計數器會摘要伺服器執行的節流（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-174">These are the two throttling mechanisms and there is one performance counter that summarizes what, if any, throttling the server is performing.</span></span>

<span data-ttu-id="ec6cb-175">**LC： SIP-2004-回應 \\ SIP-053-本機503回應/秒**</span><span class="sxs-lookup"><span data-stu-id="ec6cb-175">**LC:SIP-04-Responses\\SIP-053-Local 503 Responses/sec**</span></span>

  - <span data-ttu-id="ec6cb-176">先前計數器中的字詞 "Local" 是指在本機產生的回應。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-176">The term "Local" in the previous counter refers to locally generated responses.</span></span>

  - <span data-ttu-id="ec6cb-177">503程式碼會對應至伺服器無法使用，在此情況下，您應該不會在狀況良好的伺服器上看到任何503代碼。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-177">The 503 code corresponds to server unavailable—where you should not see any 503 codes on a healthy server.</span></span> <span data-ttu-id="ec6cb-178">在伺服器剛進入線上的期間內，您可能會看到一些503碼。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-178">During the period after a server is just brought online, you may see some 503 codes.</span></span> <span data-ttu-id="ec6cb-179">當所有使用者重新登入，且伺服器回到穩定狀態時，就不應該有其他503碼。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-179">When all of the users sign back in and the server returns to a stable state, there should no additional 503 codes.</span></span>

<span data-ttu-id="ec6cb-180">**LC： SIP-2004-回應 \\ SIP-074-本機504回應/秒**</span><span class="sxs-lookup"><span data-stu-id="ec6cb-180">**LC:SIP-04-Responses\\SIP-074-Local 504 Responses/sec**</span></span>

<span data-ttu-id="ec6cb-181">這個效能計數器會指出其他伺服器的連線問題，也可能表示連線失敗或延遲連接。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-181">This performance counter indicates connectivity issues with other servers and it can indicate failures to connect or delays in connecting.</span></span> <span data-ttu-id="ec6cb-182">如果您看到504錯誤，則應該檢查下列效能計數器。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-182">If you are seeing 504 errors then the following performance counter should be checked.</span></span>

<span data-ttu-id="ec6cb-183">**LC： SIP-01-對等 \\ SIP-017-傳送未完成**</span><span class="sxs-lookup"><span data-stu-id="ec6cb-183">**LC:SIP-01-Peers\\SIP-017-Sends Outstanding**</span></span>

<span data-ttu-id="ec6cb-184">此計數器會指出傳出的排隊要求和回應數目。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-184">This counter indicates the number of outgoing queued requests and responses.</span></span> <span data-ttu-id="ec6cb-185">如果此計數器很高，表示此問題很可能不是在本機伺服器上。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-185">If this counter is high then the issue is most likely not on the local server.</span></span> <span data-ttu-id="ec6cb-186">請注意，如果發生網路延遲問題，此計數器可能會很高。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-186">Note that this counter can be high if there are network latency issues.</span></span> <span data-ttu-id="ec6cb-187">它也可能會指出本機網路介面卡的問題，但較可能是由遠端伺服器上的問題所造成。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-187">It could also indicate issues with the local network adapter, but is more likely caused by an issue on a remote server.</span></span> <span data-ttu-id="ec6cb-188">當伺服器嘗試與其通訊的集區超載時，此計數器很可能會在 Director 伺服器上很高。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-188">This counter would most likely be high on a Director server when the pool it is trying to communicate with is overloaded.</span></span> <span data-ttu-id="ec6cb-189">這個計數器的主要是查看實例，而不只是查看總數。</span><span class="sxs-lookup"><span data-stu-id="ec6cb-189">The key with this counter is to look at the instances, not just the total.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

