---
title: Lync Server 2013：監視 Lync Server 效能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring Lync Server 2013 performance
ms:assetid: 2acfd720-6120-4816-a2d4-30476bd5cd0e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720910(v=OCS.15)
ms:contentKeyID: 63969592
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9610dddfa9748b7d28dfe040a36214f3f969826
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975809"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-lync-server-2013-performance"></a><span data-ttu-id="bbc69-102">監控 Lync Server 2013 效能</span><span class="sxs-lookup"><span data-stu-id="bbc69-102">Monitoring Lync Server 2013 performance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bbc69-103">_**主題上次修改日期：** 2014-05-15_</span><span class="sxs-lookup"><span data-stu-id="bbc69-103">_**Topic Last Modified:** 2014-05-15_</span></span>

<span data-ttu-id="bbc69-104">Lync Server 2013 的效能受多種因素影響，例如使用者設定檔、系統架構、軟體、硬體元件、協力廠商整合點（例如閘道和電話裝置、網路連線與效能、WindowsActive Directory 服務的設定和效能，以及 Windows 作業系統功能。</span><span class="sxs-lookup"><span data-stu-id="bbc69-104">Lync Server 2013 performance is affected by various factors such as user profiles, system architecture, software, hardware components, third-party integration points such as gateways and telephony equipment, network connectivity and performance, Windows Active Directory service configuration and performance in addition to the Windows operating system functionality.</span></span>

<span data-ttu-id="bbc69-105">在 Lync Server 2013 部署的核心是它是在其上執行的伺服器軟體和硬體。</span><span class="sxs-lookup"><span data-stu-id="bbc69-105">At the core of a Lync Server 2013 deployments’ performance is the server software and hardware it is implemented on.</span></span> <span data-ttu-id="bbc69-106">舉例來說，前端伺服器必須具備足夠的硬體資源，才能處理預期的（短期）使用者負載。</span><span class="sxs-lookup"><span data-stu-id="bbc69-106">As an example, a front-end server must have sufficient hardware resources to cope with the expected (short-term) user load.</span></span> <span data-ttu-id="bbc69-107">如果需要使用個別的前端伺服器來提供服務給10000使用者，則經過適當設定的伺服器必須符合預期的負載需求，才能最終協助確保最佳的最終使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="bbc69-107">If a respective front-end server is required to provide services to 10 thousand users, then an adequately configured server must meet the expected load requirements to ultimately help ensure the best possible end-user experience.</span></span>

<span data-ttu-id="bbc69-108">監視伺服器效能對於評估已部署的伺服器基礎結構是否有適用于日常峰值負載需求的硬體資源，非常重要。</span><span class="sxs-lookup"><span data-stu-id="bbc69-108">Monitoring server performance is therefore extremely important to gauge whether the implemented server infrastructure have suitable hardware resources for the day-to-day peak-load requirements.</span></span> <span data-ttu-id="bbc69-109">監視伺服器效能可協助識別系統瓶頸，讓管理員在最終使用者體驗受到影響之前套用糾正動作。</span><span class="sxs-lookup"><span data-stu-id="bbc69-109">Monitoring server performance helps identify system bottlenecks allowing administrators to apply corrective action before the end-user experience is affected.</span></span> <span data-ttu-id="bbc69-110">效能資料應該用於長期的容量規劃。</span><span class="sxs-lookup"><span data-stu-id="bbc69-110">The performance data should be used for long-term capacity planning.</span></span>

<span data-ttu-id="bbc69-111">如果您要觀察的所有效能物件和計數器的詳細資訊都是透過[System Center Operations Manager 來監視 Lync Server 2013](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)，所以您應該遵循的一些效能計數器可讓管理員快速瞭解系統效能：</span><span class="sxs-lookup"><span data-stu-id="bbc69-111">While detailed information on all performance objects and counters to be observed is linked to in [Monitoring Lync Server 2013 with System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md), some performance counters that you should follow can provide administrators a quick view of the system performance:</span></span>

  - <span data-ttu-id="bbc69-112">為了追蹤前端伺服器的整體系統健康情況，良好的起點就是檢查處理器\\% 處理器時間。</span><span class="sxs-lookup"><span data-stu-id="bbc69-112">To track overall system health of the front-end server, a good starting point is to check Processor\\% Processor Time.</span></span> <span data-ttu-id="bbc69-113">此值應該總是低於80%。</span><span class="sxs-lookup"><span data-stu-id="bbc69-113">The value should always be below 80 percent.</span></span>

  - <span data-ttu-id="bbc69-114">若要追蹤由前端池使用的後端 SQL Server 資料庫軟體實例的效能，請監視下列效能計數器：</span><span class="sxs-lookup"><span data-stu-id="bbc69-114">To track the performance of the back end SQL Server database software instance used by the Front End pool, monitor the following performance counters:</span></span>
    
    <span data-ttu-id="bbc69-115">LC： USrv –00– DBStore\\USrv – 002-佇列延遲時間（毫秒）</span><span class="sxs-lookup"><span data-stu-id="bbc69-115">LC:USrv – 00 – DBStore\\Usrv – 002 – Queue Latency (msec)</span></span>
    
    <span data-ttu-id="bbc69-116">LC： USrv –00– DBStore\\USrv – 0 04 –過程間延遲時間（毫秒）</span><span class="sxs-lookup"><span data-stu-id="bbc69-116">LC:USrv – 00 – DBStore\\Usrv – 0 04– Sproc Latency (msec)</span></span>
    
    <span data-ttu-id="bbc69-117">穩定狀態的正常伺服器應該會顯示\<100 ms 延隔時間值。</span><span class="sxs-lookup"><span data-stu-id="bbc69-117">The healthy server at steady state should show \<100 ms latency values.</span></span> <span data-ttu-id="bbc69-118">當延隔時間達到12秒時，節流機制將會使用，這表示前端伺服器會開始將要求移到後端。</span><span class="sxs-lookup"><span data-stu-id="bbc69-118">The throttling mechanism will engage when latency reaches 12 seconds, which means the front-end server starts throttling requests to the back end.</span></span> <span data-ttu-id="bbc69-119">這會導致用戶端開始收到503伺服器太忙的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="bbc69-119">This causes clients to start to receive a 503 Server too busy error message.</span></span>

  - <span data-ttu-id="bbc69-120">若要追蹤前端伺服器的處理時間，請監視下列計數器：</span><span class="sxs-lookup"><span data-stu-id="bbc69-120">To track the processing time at the front-end server, monitor the following counter:</span></span>
    
    <span data-ttu-id="bbc69-121">LC： SIP-2007-載入管理\\sip-000-接收郵件的平均保留時間</span><span class="sxs-lookup"><span data-stu-id="bbc69-121">LC:SIP - 07 - Load Management\\SIP - 000 - Average Holding Time For Incoming Messages</span></span>
    
    <span data-ttu-id="bbc69-122">這是前端伺服器的另一種節流機制，這次是在前端處理時間較高時開始。</span><span class="sxs-lookup"><span data-stu-id="bbc69-122">This is another throttling mechanism on the front-end servers, this time starting when the processing time on the front end is high.</span></span> <span data-ttu-id="bbc69-123">如果平均處理時間超過6秒，伺服器會進入節流模式，且每個用戶端連線只允許一個未完成的事務。</span><span class="sxs-lookup"><span data-stu-id="bbc69-123">If average processing time is more than six seconds, the server goes into throttling mode and only allows one outstanding transaction per client connection.</span></span>

  - <span data-ttu-id="bbc69-124">若要追蹤 SQL 後端伺服器的記憶體問題，請監視下列計數器：</span><span class="sxs-lookup"><span data-stu-id="bbc69-124">To track memory issues at SQL Back End Server, monitor the following counter:</span></span>
    
    <span data-ttu-id="bbc69-125">SQL Server 緩衝區管理員\\頁生命預期</span><span class="sxs-lookup"><span data-stu-id="bbc69-125">SQL Server Buffer Manager\\Page life expectancy</span></span>
    
    <span data-ttu-id="bbc69-126">較低的值低於3600秒（以及高延遲寫入/秒和檢查點頁/秒），表示記憶體壓力。</span><span class="sxs-lookup"><span data-stu-id="bbc69-126">A low value, below 3600 seconds (together with high latency writes/sec and checkpoint pages/sec) indicates memory pressure.</span></span>

<div>

## <a name="additional-counters-to-view"></a><span data-ttu-id="bbc69-127">要查看的其他計數器</span><span class="sxs-lookup"><span data-stu-id="bbc69-127">Additional Counters to View</span></span>

<span data-ttu-id="bbc69-128">有幾個主要的計數器是來自前端伺服器的整體健康情況。</span><span class="sxs-lookup"><span data-stu-id="bbc69-128">There are several key counters that are good indicators of overall health from the front end server.</span></span> <span data-ttu-id="bbc69-129">這不是一個完整的清單，而且不代表根本原因。</span><span class="sxs-lookup"><span data-stu-id="bbc69-129">This is not a comprehensive list and is not meant to identify root cause.</span></span> <span data-ttu-id="bbc69-130">這些計數器可讓您在伺服器健康情況中執行快速檢查。</span><span class="sxs-lookup"><span data-stu-id="bbc69-130">These counters will let you perform a quick check on your server health.</span></span> <span data-ttu-id="bbc69-131">我們建議在池中的每個伺服器上驗證這些計數器。</span><span class="sxs-lookup"><span data-stu-id="bbc69-131">We recommend verifying these counters on each of the servers in the pool.</span></span> <span data-ttu-id="bbc69-132">在伺服器健康時，請務必瞭解這些計數器值的內容。</span><span class="sxs-lookup"><span data-stu-id="bbc69-132">It is important to understand what these counter values are when your server is healthy.</span></span> <span data-ttu-id="bbc69-133">需要有基準，以瞭解在使用者體驗下降時所變更的內容。</span><span class="sxs-lookup"><span data-stu-id="bbc69-133">A baseline is required to understand what changed when the user experience is degraded.</span></span>

<span data-ttu-id="bbc69-134">前端伺服器可以指出可能是因為系統中其他人的瓶頸所造成的問題。</span><span class="sxs-lookup"><span data-stu-id="bbc69-134">The front-end server can indicate issues that may be caused by bottlenecks elsewhere in the system.</span></span> <span data-ttu-id="bbc69-135">這表示它是查看整體系統健康情況時的最佳開始位置。</span><span class="sxs-lookup"><span data-stu-id="bbc69-135">This means that it is the best place to start when looking at overall system health.</span></span>

<span data-ttu-id="bbc69-136">您首先要檢查的兩個額外計數器如下所示：</span><span class="sxs-lookup"><span data-stu-id="bbc69-136">Two additional counters to review first are as follows:</span></span>

<span data-ttu-id="bbc69-137">LC： USrv-00-DBStore\\USrv-002-佇列延遲時間（毫秒）</span><span class="sxs-lookup"><span data-stu-id="bbc69-137">LC:USrv-00-DBStore\\Usrv-002-Queue Latency (msec)</span></span>

<span data-ttu-id="bbc69-138">LC： USrv-00-DBStore\\USrv-004-過程中的延遲時間（毫秒）</span><span class="sxs-lookup"><span data-stu-id="bbc69-138">LC:USrv-00-DBStore\\Usrv-004-Sproc Latency (msec)</span></span>

<span data-ttu-id="bbc69-139">Queue 延隔時間計數器代表對後端所花費的時間要求，而 [處理常式延遲] 代表後端處理要求所需的時間。</span><span class="sxs-lookup"><span data-stu-id="bbc69-139">The queue latency counter represents the time that a request spent in the queue to the back end and the Sproc latency represents the time that it took for the back end to process the request.</span></span> <span data-ttu-id="bbc69-140">如有任何原因、後端的磁片、記憶體、網路及處理器都有問題，佇列延隔時間計數器就會很高。</span><span class="sxs-lookup"><span data-stu-id="bbc69-140">If, for any reason, disk, memory, network, and processor on the back end are in trouble, the queue latency counter will be high.</span></span>

<span data-ttu-id="bbc69-141">如果前端與後端之間有較高的網路延遲，也會有較高的功能。</span><span class="sxs-lookup"><span data-stu-id="bbc69-141">It can also be high if there is high network latency between the front end and the back end.</span></span> <span data-ttu-id="bbc69-142">什麼是可接受的佇列延遲？</span><span class="sxs-lookup"><span data-stu-id="bbc69-142">So what is acceptable queue latency?</span></span>

<span data-ttu-id="bbc69-143">在12秒後，前端伺服器會開始將要求傳送到後端伺服器。</span><span class="sxs-lookup"><span data-stu-id="bbc69-143">At 12 seconds, the Front End Servers start throttling requests to the Back End Servers.</span></span> <span data-ttu-id="bbc69-144">這表示伺服器已開始將伺服器太忙-503 錯誤傳回給用戶端。</span><span class="sxs-lookup"><span data-stu-id="bbc69-144">This means the servers start returning Server too busy – 503 errors to the clients.</span></span> <span data-ttu-id="bbc69-145">良好的伺服器應在穩定狀態的 DBStore 佇列延遲時間少於100毫秒，但在伺服器剛連線且使用者同時登入的時段內，該計數器可能相當高，您甚至可能會在數秒內看到它。</span><span class="sxs-lookup"><span data-stu-id="bbc69-145">A healthy server should have less than 100 msec DBStore queue latencies at steady state, but during times where the server has just come online and users are all logging in at the same time, that counter can be very high and you may even see it hit multiple seconds.</span></span>

<span data-ttu-id="bbc69-146">您可能會有負載平衡設定，您可以在其中部署含多個前端伺服器的池，以及設定為「最少連線數」的負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="bbc69-146">You may have a load-balanced configuration, where you have a pool deployed with multiple front-end servers and a load balancer that is configured for "least number of connections."</span></span> <span data-ttu-id="bbc69-147">在這種情況下，如果已重新開機一個前端伺服器，則嘗試重新連線的所有使用者都會指向重新開機的伺服器，因為該伺服器與其他的池成員相比有較少的連接。</span><span class="sxs-lookup"><span data-stu-id="bbc69-147">In this case, if one front-end server is restarted, then all users who attempt to reconnect will be pointed to the restarted server, because that server will have fewer connections compared to the other pool members.</span></span> <span data-ttu-id="bbc69-148">在此期間，可能會在其他的池成員不在這段時間內超載個別的前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="bbc69-148">During this time, the respective front-end server may be overloaded while the other pool members are not.</span></span>

<span data-ttu-id="bbc69-149">我們建議您在下班時間進行維護，以減少效能影響，因為使用者不會同時與伺服器連線。</span><span class="sxs-lookup"><span data-stu-id="bbc69-149">We recommend that you perform maintenance during off-hours to reduce the performance affect as users will not all be competing to connect to the server at the same time.</span></span>

<span data-ttu-id="bbc69-150">如果前兩個效能計數器較高，則最可能的瓶頸就是 SQL 後端伺服器。</span><span class="sxs-lookup"><span data-stu-id="bbc69-150">If the previous two performance counters are high, the most likely bottleneck is the SQL Back End Server.</span></span> <span data-ttu-id="bbc69-151">下一步要確認的元件如下所示：</span><span class="sxs-lookup"><span data-stu-id="bbc69-151">The next components to confirm are as follows:</span></span>

  - <span data-ttu-id="bbc69-152">SQL Server CPU 是否太高？</span><span class="sxs-lookup"><span data-stu-id="bbc69-152">Is the SQL Server CPU too high?</span></span> <span data-ttu-id="bbc69-153">例如，它大於80% 嗎？</span><span class="sxs-lookup"><span data-stu-id="bbc69-153">For example, is it greater than 80 percent?</span></span>

  - <span data-ttu-id="bbc69-154">磁片延遲是高嗎？</span><span class="sxs-lookup"><span data-stu-id="bbc69-154">Is the disk latency high?</span></span>

<span data-ttu-id="bbc69-155">在理想世界中，您有足夠的 RAM 在記憶體中同時擁有 RTC 與 RTCDYN 資料庫。</span><span class="sxs-lookup"><span data-stu-id="bbc69-155">In an ideal world, you have enough RAM to have both the RTC and RTCDYN databases in memory.</span></span> <span data-ttu-id="bbc69-156">接著，伺服器只需要存取磁片，就是寫入記錄檔並刷新資料庫。</span><span class="sxs-lookup"><span data-stu-id="bbc69-156">Then, the only reason the server would be accessing the disk, is to write to the log files and flush to the databases.</span></span> <span data-ttu-id="bbc69-157">測試顯示，12 GB 的 RAM 已足夠用於100000使用者部署。</span><span class="sxs-lookup"><span data-stu-id="bbc69-157">Tests have shown that 12 GB of RAM is sufficient for 100 thousand user deployments.</span></span> <span data-ttu-id="bbc69-158">這假設 RTC 與 RTCDYN 資料庫的大小小於 12 GB。</span><span class="sxs-lookup"><span data-stu-id="bbc69-158">This assumes that the RTC and RTCDYN databases size totals less than 12 GB.</span></span> <span data-ttu-id="bbc69-159">如果您的資料庫大於該大小，您可能需要額外的記憶體。</span><span class="sxs-lookup"><span data-stu-id="bbc69-159">If your databases are larger than that, then you may need additional memory.</span></span>

<span data-ttu-id="bbc69-160">您可以透過查看 SQL server 緩衝區管理員頁面生命預期效能計數器，判斷您的 SQL Server 是否需要額外的 RAM。</span><span class="sxs-lookup"><span data-stu-id="bbc69-160">You can determine whether your SQL Server requires additional RAM by reviewing the SQL Server Buffer Manager page life expectancy performance counter.</span></span> <span data-ttu-id="bbc69-161">小於3600的值表示記憶體壓力。</span><span class="sxs-lookup"><span data-stu-id="bbc69-161">A value less than 3,600 indicates memory pressure.</span></span> <span data-ttu-id="bbc69-162">如果您有足夠的記憶體，您也應該在資料庫磁片磁碟機上看不到讀取權，因為 SQL Server 只能寫入資料庫。</span><span class="sxs-lookup"><span data-stu-id="bbc69-162">You should also see little to no reads on your database drive if you have sufficient memory because SQL Server should only be writing to the database.</span></span>

<span data-ttu-id="bbc69-163">Lync Server 2013 前端伺服器會在伺服器處理時間較高的情況下，啟動其他節流機制。</span><span class="sxs-lookup"><span data-stu-id="bbc69-163">There is an additional throttling mechanism in a Lync Server 2013 Front End Server that starts if the server processing time is high.</span></span> <span data-ttu-id="bbc69-164">只有在 SQL Server 的延遲時間很高時，才會啟用 DBStore 延遲節流。</span><span class="sxs-lookup"><span data-stu-id="bbc69-164">The DBStore latency throttling is only enabled if the latency to the SQL Server is high.</span></span> <span data-ttu-id="bbc69-165">啟用這種節流的其中一個範例是，如果前端伺服器是 CPU 界限的。</span><span class="sxs-lookup"><span data-stu-id="bbc69-165">One example in which such throttling is enabled is if the front-end server is CPU-bound.</span></span>

<span data-ttu-id="bbc69-166">如果在伺服器上的平均處理時間 **（LC：\\以 LC 為單位）** ，在伺服器上超過6秒，則伺服器會進入節流模式，而且每個用戶端連線只給予使用者一個未完成的事務。</span><span class="sxs-lookup"><span data-stu-id="bbc69-166">If the average processing time **(LC:SIP-07-Load Management\\SIP-000-Average Holding Time For Incoming Messages)** on the server exceeds six seconds, then the server goes into throttling mode and only gives users one outstanding transaction per client connection.</span></span> <span data-ttu-id="bbc69-167">在處理時間下降到三秒之後，伺服器會中斷節流模式，並為每個用戶端連線提供20個未完成的事務。</span><span class="sxs-lookup"><span data-stu-id="bbc69-167">Once the processing time drops to three seconds, then the server drops out of throttling mode and gives users up to 20 outstanding transactions per client connection.</span></span> <span data-ttu-id="bbc69-168">每當特定連線的事務數目超過上述閾值時，該連線就會標示為 [流程式控制制]。</span><span class="sxs-lookup"><span data-stu-id="bbc69-168">Whenever the number of transactions on a specific connection exceeds the threshold above, the connection is marked as flow controlled.</span></span> <span data-ttu-id="bbc69-169">結果是伺服器不會在其上張貼任何接收，而且**LC： SIP-\\01-對等流程式控制制**連線計數器會遞增。</span><span class="sxs-lookup"><span data-stu-id="bbc69-169">The result is the server does not post any receives on it, and the **LC:SIP-01-Peers\\Flow Controlled Connections** counter is incremented.</span></span> <span data-ttu-id="bbc69-170">如果連接在流程式控制制狀態持續一分鐘以上，則伺服器會將它關閉。</span><span class="sxs-lookup"><span data-stu-id="bbc69-170">If a connection stays in a flow-controlled state for more than one minute, then the server closes it.</span></span> <span data-ttu-id="bbc69-171">它會延遲進行。</span><span class="sxs-lookup"><span data-stu-id="bbc69-171">It does so lazily.</span></span> <span data-ttu-id="bbc69-172">當它有機會檢查連線時，會判斷是否已將它限制太長，並在超過一分鐘之後關閉它。</span><span class="sxs-lookup"><span data-stu-id="bbc69-172">When it has an opportunity to check the connection, it determines whether it was throttled for too long and closes it if it has more than one minute.</span></span>

<span data-ttu-id="bbc69-173">這些是兩種節流機制，且有一個效能計數器，用於匯總伺服器所執行的功能（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="bbc69-173">These are the two throttling mechanisms and there is one performance counter that summarizes what, if any, throttling the server is performing.</span></span>

<span data-ttu-id="bbc69-174">**LC： SIP-04-回應\\SIP-053-本機503回應/秒**</span><span class="sxs-lookup"><span data-stu-id="bbc69-174">**LC:SIP-04-Responses\\SIP-053-Local 503 Responses/sec**</span></span>

  - <span data-ttu-id="bbc69-175">前一個計數器中的「Local」一詞指的是本機產生的回應。</span><span class="sxs-lookup"><span data-stu-id="bbc69-175">The term "Local" in the previous counter refers to locally generated responses.</span></span>

  - <span data-ttu-id="bbc69-176">503程式碼對應至伺服器無法使用，您不應該在正常的伺服器上看到任何503程式碼。</span><span class="sxs-lookup"><span data-stu-id="bbc69-176">The 503 code corresponds to server unavailable—where you should not see any 503 codes on a healthy server.</span></span> <span data-ttu-id="bbc69-177">在伺服器剛連線之後的期間，您可能會看到一些503代碼。</span><span class="sxs-lookup"><span data-stu-id="bbc69-177">During the period after a server is just brought online, you may see some 503 codes.</span></span> <span data-ttu-id="bbc69-178">當所有使用者重新登入，且伺服器回到穩定狀態時，則不應該有額外的503代碼。</span><span class="sxs-lookup"><span data-stu-id="bbc69-178">When all of the users sign back in and the server returns to a stable state, there should no additional 503 codes.</span></span>

<span data-ttu-id="bbc69-179">**LC： SIP-04-回應\\SIP-074-本機504回應/秒**</span><span class="sxs-lookup"><span data-stu-id="bbc69-179">**LC:SIP-04-Responses\\SIP-074-Local 504 Responses/sec**</span></span>

<span data-ttu-id="bbc69-180">這個效能計數器代表其他伺服器的連線問題，而且可能會指出連線失敗或連接延遲。</span><span class="sxs-lookup"><span data-stu-id="bbc69-180">This performance counter indicates connectivity issues with other servers and it can indicate failures to connect or delays in connecting.</span></span> <span data-ttu-id="bbc69-181">如果您看到504錯誤，則應該核取下列效能計數器。</span><span class="sxs-lookup"><span data-stu-id="bbc69-181">If you are seeing 504 errors then the following performance counter should be checked.</span></span>

<span data-ttu-id="bbc69-182">**LC： SIP-01-對\\等 sip-017-傳送未完成**</span><span class="sxs-lookup"><span data-stu-id="bbc69-182">**LC:SIP-01-Peers\\SIP-017-Sends Outstanding**</span></span>

<span data-ttu-id="bbc69-183">這個計數器代表傳出的排隊要求和回應數目。</span><span class="sxs-lookup"><span data-stu-id="bbc69-183">This counter indicates the number of outgoing queued requests and responses.</span></span> <span data-ttu-id="bbc69-184">如果這個計數器較高，則問題很可能不在本機伺服器上。</span><span class="sxs-lookup"><span data-stu-id="bbc69-184">If this counter is high then the issue is most likely not on the local server.</span></span> <span data-ttu-id="bbc69-185">請注意，如果有網路延遲問題，這個計數器可能會很高。</span><span class="sxs-lookup"><span data-stu-id="bbc69-185">Note that this counter can be high if there are network latency issues.</span></span> <span data-ttu-id="bbc69-186">這也可能表示本機網路介面卡出現問題，但較可能是由遠端伺服器上的問題所造成。</span><span class="sxs-lookup"><span data-stu-id="bbc69-186">It could also indicate issues with the local network adapter, but is more likely caused by an issue on a remote server.</span></span> <span data-ttu-id="bbc69-187">當您嘗試與之通訊的池超載時，控制器伺服器上最可能會有較高的計數器。</span><span class="sxs-lookup"><span data-stu-id="bbc69-187">This counter would most likely be high on a Director server when the pool it is trying to communicate with is overloaded.</span></span> <span data-ttu-id="bbc69-188">這個計數器的主要目的是查看實例，而不只是合計。</span><span class="sxs-lookup"><span data-stu-id="bbc69-188">The key with this counter is to look at the instances, not just the total.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

