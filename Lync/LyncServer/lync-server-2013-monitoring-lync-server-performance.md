---
title: Lync Server 2013： 監視 Lync 伺服器的效能
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
ms.openlocfilehash: ee7fbb69583a62ac50548bdae11a1a5681398e98
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048066"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-lync-server-2013-performance"></a><span data-ttu-id="cc986-102">監控的 Lync Server 2013 效能</span><span class="sxs-lookup"><span data-stu-id="cc986-102">Monitoring Lync Server 2013 performance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc986-103">_**上次修改主題：** 2014年-05-15_</span><span class="sxs-lookup"><span data-stu-id="cc986-103">_**Topic Last Modified:** 2014-05-15_</span></span>

<span data-ttu-id="cc986-104">Lync Server 2013 效能會受到各種因素影響，例如使用者設定檔、 系統架構、 軟體、 硬體元件、 第三方整合 points 例如閘道和電話語音設備，網路連線能力與效能，WindowsActive Directory 服務設定和除了 Windows 作業系統功能的效能。</span><span class="sxs-lookup"><span data-stu-id="cc986-104">Lync Server 2013 performance is affected by various factors such as user profiles, system architecture, software, hardware components, third-party integration points such as gateways and telephony equipment, network connectivity and performance, Windows Active Directory service configuration and performance in addition to the Windows operating system functionality.</span></span>

<span data-ttu-id="cc986-105">Lync Server 2013 的核心部署的效能是伺服器軟體和硬體實作。</span><span class="sxs-lookup"><span data-stu-id="cc986-105">At the core of a Lync Server 2013 deployments’ performance is the server software and hardware it is implemented on.</span></span> <span data-ttu-id="cc986-106">做為範例，前端伺服器必須有足夠的硬體資源，以應付預期 （短期） 的使用者負載。</span><span class="sxs-lookup"><span data-stu-id="cc986-106">As an example, a front-end server must have sufficient hardware resources to cope with the expected (short-term) user load.</span></span> <span data-ttu-id="cc986-107">如果各自的前端伺服器需要 10 千位使用者提供服務，適當地設定的伺服器必須符合預期的負載需求，以最終可協助您確保最佳的可能的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="cc986-107">If a respective front-end server is required to provide services to 10 thousand users, then an adequately configured server must meet the expected load requirements to ultimately help ensure the best possible end-user experience.</span></span>

<span data-ttu-id="cc986-108">監視伺服器效能因此是非常重要的事評量實作的伺服器基礎結構是否有適當的硬體資源的每日的尖峰負載需求。</span><span class="sxs-lookup"><span data-stu-id="cc986-108">Monitoring server performance is therefore extremely important to gauge whether the implemented server infrastructure have suitable hardware resources for the day-to-day peak-load requirements.</span></span> <span data-ttu-id="cc986-109">監視伺服器效能可協助識別系統的瓶頸，允許系統管理員將套用矯正措施，才會影響使用者經驗。</span><span class="sxs-lookup"><span data-stu-id="cc986-109">Monitoring server performance helps identify system bottlenecks allowing administrators to apply corrective action before the end-user experience is affected.</span></span> <span data-ttu-id="cc986-110">效能資料應用於長期容量計劃。</span><span class="sxs-lookup"><span data-stu-id="cc986-110">The performance data should be used for long-term capacity planning.</span></span>

<span data-ttu-id="cc986-111">時的所有效能物件及觀察到的計數器的詳細的資訊連結至[與 System Center Operations Manager 監視 Lync Server 2013](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)中，您應該遵循一些效能計數器可以提供系統管理員快速檢視的系統效能：</span><span class="sxs-lookup"><span data-stu-id="cc986-111">While detailed information on all performance objects and counters to be observed is linked to in [Monitoring Lync Server 2013 with System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md), some performance counters that you should follow can provide administrators a quick view of the system performance:</span></span>

  - <span data-ttu-id="cc986-112">若要追蹤的前端伺服器的整體系統健康狀況，不錯的起點是檢查處理器\\%Processor Time。</span><span class="sxs-lookup"><span data-stu-id="cc986-112">To track overall system health of the front-end server, a good starting point is to check Processor\\% Processor Time.</span></span> <span data-ttu-id="cc986-113">值應該永遠低於 80%。</span><span class="sxs-lookup"><span data-stu-id="cc986-113">The value should always be below 80 percent.</span></span>

  - <span data-ttu-id="cc986-114">若要追蹤的後端 SQL Server 資料庫軟體執行個體前端集區所使用的效能，請監視下列效能計數器：</span><span class="sxs-lookup"><span data-stu-id="cc986-114">To track the performance of the back end SQL Server database software instance used by the Front End pool, monitor the following performance counters:</span></span>
    
    <span data-ttu-id="cc986-115">LC:USrv – 00 – DBStore\\Usrv – 002 – 佇列延遲 （毫秒）</span><span class="sxs-lookup"><span data-stu-id="cc986-115">LC:USrv – 00 – DBStore\\Usrv – 002 – Queue Latency (msec)</span></span>
    
    <span data-ttu-id="cc986-116">LC:USrv – 00 – DBStore\\Usrv – 0 04 – 預存程序延遲 （毫秒）</span><span class="sxs-lookup"><span data-stu-id="cc986-116">LC:USrv – 00 – DBStore\\Usrv – 0 04– Sproc Latency (msec)</span></span>
    
    <span data-ttu-id="cc986-117">穩定狀態的狀況良好伺服器應會顯示\<100 毫秒的延遲時間值。</span><span class="sxs-lookup"><span data-stu-id="cc986-117">The healthy server at steady state should show \<100 ms latency values.</span></span> <span data-ttu-id="cc986-118">節流機制會從事延遲達到 12 秒，的表示前端伺服器啟動節流要求給後端。</span><span class="sxs-lookup"><span data-stu-id="cc986-118">The throttling mechanism will engage when latency reaches 12 seconds, which means the front-end server starts throttling requests to the back end.</span></span> <span data-ttu-id="cc986-119">這會導致用戶端開始接收 503 伺服器過於忙碌錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="cc986-119">This causes clients to start to receive a 503 Server too busy error message.</span></span>

  - <span data-ttu-id="cc986-120">若要追蹤的前端伺服器的處理時間，請監視下列計數器：</span><span class="sxs-lookup"><span data-stu-id="cc986-120">To track the processing time at the front-end server, monitor the following counter:</span></span>
    
    <span data-ttu-id="cc986-121">LC:SIP-07-負載管理\\SIP-000-平均內送郵件的保留時間</span><span class="sxs-lookup"><span data-stu-id="cc986-121">LC:SIP - 07 - Load Management\\SIP - 000 - Average Holding Time For Incoming Messages</span></span>
    
    <span data-ttu-id="cc986-122">這是另一個節流處理機制，在前端伺服器，這次啟動時，前端的處理時間很高。</span><span class="sxs-lookup"><span data-stu-id="cc986-122">This is another throttling mechanism on the front-end servers, this time starting when the processing time on the front end is high.</span></span> <span data-ttu-id="cc986-123">如果平均處理時間是 6 秒以上，伺服器會進入節流的模式，並只允許一個未完成的交易，每個用戶端連線。</span><span class="sxs-lookup"><span data-stu-id="cc986-123">If average processing time is more than six seconds, the server goes into throttling mode and only allows one outstanding transaction per client connection.</span></span>

  - <span data-ttu-id="cc986-124">若要追蹤在 SQL 後端伺服器的記憶體問題，請監視下列計數器：</span><span class="sxs-lookup"><span data-stu-id="cc986-124">To track memory issues at SQL Back End Server, monitor the following counter:</span></span>
    
    <span data-ttu-id="cc986-125">SQL Server 緩衝區管理員\\頁面 life expectancy</span><span class="sxs-lookup"><span data-stu-id="cc986-125">SQL Server Buffer Manager\\Page life expectancy</span></span>
    
    <span data-ttu-id="cc986-126">低的值，下方 3600 秒 （搭配高延遲寫入次數/秒和檢查點頁面/秒） 會指出記憶體不足。</span><span class="sxs-lookup"><span data-stu-id="cc986-126">A low value, below 3600 seconds (together with high latency writes/sec and checkpoint pages/sec) indicates memory pressure.</span></span>

<div>

## <a name="additional-counters-to-view"></a><span data-ttu-id="cc986-127">若要檢視其他計數器</span><span class="sxs-lookup"><span data-stu-id="cc986-127">Additional Counters to View</span></span>

<span data-ttu-id="cc986-128">有幾個重要計數器中，從前端伺服器的整體健康狀況良好的指標。</span><span class="sxs-lookup"><span data-stu-id="cc986-128">There are several key counters that are good indicators of overall health from the front end server.</span></span> <span data-ttu-id="cc986-129">這並不完整的清單，而不是找出根本原因。</span><span class="sxs-lookup"><span data-stu-id="cc986-129">This is not a comprehensive list and is not meant to identify root cause.</span></span> <span data-ttu-id="cc986-130">這些計數器會讓您快速上執行檢查伺服器健康狀況。</span><span class="sxs-lookup"><span data-stu-id="cc986-130">These counters will let you perform a quick check on your server health.</span></span> <span data-ttu-id="cc986-131">我們建議您確認每個集區中的伺服器上這些計數器。</span><span class="sxs-lookup"><span data-stu-id="cc986-131">We recommend verifying these counters on each of the servers in the pool.</span></span> <span data-ttu-id="cc986-132">請務必了解這些計數器的值為何當您的伺服器狀況良好。</span><span class="sxs-lookup"><span data-stu-id="cc986-132">It is important to understand what these counter values are when your server is healthy.</span></span> <span data-ttu-id="cc986-133">[比較基準，才能了解發生變更時的使用者經驗會變慢。</span><span class="sxs-lookup"><span data-stu-id="cc986-133">A baseline is required to understand what changed when the user experience is degraded.</span></span>

<span data-ttu-id="cc986-134">前端伺服器可以指出可能導致瓶頸別處系統中的問題。</span><span class="sxs-lookup"><span data-stu-id="cc986-134">The front-end server can indicate issues that may be caused by bottlenecks elsewhere in the system.</span></span> <span data-ttu-id="cc986-135">這表示它是以啟動時查看整體系統健康狀況的最佳位置。</span><span class="sxs-lookup"><span data-stu-id="cc986-135">This means that it is the best place to start when looking at overall system health.</span></span>

<span data-ttu-id="cc986-136">若要檢閱的兩個其他計數器先如下：</span><span class="sxs-lookup"><span data-stu-id="cc986-136">Two additional counters to review first are as follows:</span></span>

<span data-ttu-id="cc986-137">LC:USrv-00-DBStore\\Usrv 002 Get-queue 延遲 （毫秒）</span><span class="sxs-lookup"><span data-stu-id="cc986-137">LC:USrv-00-DBStore\\Usrv-002-Queue Latency (msec)</span></span>

<span data-ttu-id="cc986-138">LC:USrv-00-DBStore\\Usrv-004-預存程序延遲 （毫秒）</span><span class="sxs-lookup"><span data-stu-id="cc986-138">LC:USrv-00-DBStore\\Usrv-004-Sproc Latency (msec)</span></span>

<span data-ttu-id="cc986-139">佇列延遲計數器代表要求在佇列中的後端所花費的時間和預存程序延遲代表端處理要求所花的時間。</span><span class="sxs-lookup"><span data-stu-id="cc986-139">The queue latency counter represents the time that a request spent in the queue to the back end and the Sproc latency represents the time that it took for the back end to process the request.</span></span> <span data-ttu-id="cc986-140">如果有任何原因磁碟、 記憶體、 網路和後端上的處理器位於問題，佇列延遲計數器會很高。</span><span class="sxs-lookup"><span data-stu-id="cc986-140">If, for any reason, disk, memory, network, and processor on the back end are in trouble, the queue latency counter will be high.</span></span>

<span data-ttu-id="cc986-141">它也可以是高如果沒有前端及後端之間的高網路延遲。</span><span class="sxs-lookup"><span data-stu-id="cc986-141">It can also be high if there is high network latency between the front end and the back end.</span></span> <span data-ttu-id="cc986-142">那麼可接受的佇列延遲是什麼？</span><span class="sxs-lookup"><span data-stu-id="cc986-142">So what is acceptable queue latency?</span></span>

<span data-ttu-id="cc986-143">在 12 秒，前端伺服器，開始節流在後端伺服器的要求。</span><span class="sxs-lookup"><span data-stu-id="cc986-143">At 12 seconds, the Front End Servers start throttling requests to the Back End Servers.</span></span> <span data-ttu-id="cc986-144">這表示伺服器開始傳回伺服器過於忙碌 – 用戶端 503 錯誤。</span><span class="sxs-lookup"><span data-stu-id="cc986-144">This means the servers start returning Server too busy – 503 errors to the clients.</span></span> <span data-ttu-id="cc986-145">狀況良好伺服器應有小於 100 毫秒 DBStore 佇列延遲，在穩定狀態，但時段，其中伺服器已剛上線和使用者所有記錄在此同時，計數器可以是非常高，而且您甚至可能會看到它瀏覽多個的秒數。</span><span class="sxs-lookup"><span data-stu-id="cc986-145">A healthy server should have less than 100 msec DBStore queue latencies at steady state, but during times where the server has just come online and users are all logging in at the same time, that counter can be very high and you may even see it hit multiple seconds.</span></span>

<span data-ttu-id="cc986-146">您可能必須在負載平衡組態中，您必須部署多部前端伺服器與已設定為 「 最低連線數目。 」 負載平衡器集區的位置</span><span class="sxs-lookup"><span data-stu-id="cc986-146">You may have a load-balanced configuration, where you have a pool deployed with multiple front-end servers and a load balancer that is configured for "least number of connections."</span></span> <span data-ttu-id="cc986-147">在此情況下，如果重新啟動一部前端伺服器，然後嘗試重新連線的所有使用者將會都指向重新啟動伺服器上，因為該伺服器會有較少相較於其他集區成員的連線。</span><span class="sxs-lookup"><span data-stu-id="cc986-147">In this case, if one front-end server is restarted, then all users who attempt to reconnect will be pointed to the restarted server, because that server will have fewer connections compared to the other pool members.</span></span> <span data-ttu-id="cc986-148">在這段時間，而其他集區成員都是不可能超載各自的前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="cc986-148">During this time, the respective front-end server may be overloaded while the other pool members are not.</span></span>

<span data-ttu-id="cc986-149">我們建議您為使用者都會並非所有競爭連接到伺服器，同時降低的效能影響於離峰時段執行維護。</span><span class="sxs-lookup"><span data-stu-id="cc986-149">We recommend that you perform maintenance during off-hours to reduce the performance affect as users will not all be competing to connect to the server at the same time.</span></span>

<span data-ttu-id="cc986-150">如果先前兩個效能計數器太高，很可能是瓶頸是 SQL 後端伺服器。</span><span class="sxs-lookup"><span data-stu-id="cc986-150">If the previous two performance counters are high, the most likely bottleneck is the SQL Back End Server.</span></span> <span data-ttu-id="cc986-151">若要確認的下一個元件如下所示：</span><span class="sxs-lookup"><span data-stu-id="cc986-151">The next components to confirm are as follows:</span></span>

  - <span data-ttu-id="cc986-152">是 SQL Server CPU 太高？</span><span class="sxs-lookup"><span data-stu-id="cc986-152">Is the SQL Server CPU too high?</span></span> <span data-ttu-id="cc986-153">例如，是否大於 80%？</span><span class="sxs-lookup"><span data-stu-id="cc986-153">For example, is it greater than 80 percent?</span></span>

  - <span data-ttu-id="cc986-154">是高磁碟延遲？</span><span class="sxs-lookup"><span data-stu-id="cc986-154">Is the disk latency high?</span></span>

<span data-ttu-id="cc986-155">在理想的世界，您有足夠的 RAM，可在記憶體中有 RTC 和 RTCDYN 資料庫。</span><span class="sxs-lookup"><span data-stu-id="cc986-155">In an ideal world, you have enough RAM to have both the RTC and RTCDYN databases in memory.</span></span> <span data-ttu-id="cc986-156">然後，伺服器會存取磁碟的唯一原因是寫入記錄檔，並清除資料庫。</span><span class="sxs-lookup"><span data-stu-id="cc986-156">Then, the only reason the server would be accessing the disk, is to write to the log files and flush to the databases.</span></span> <span data-ttu-id="cc986-157">測試有 12 GB 的 RAM 是足夠的 100 千位使用者部署時顯示。</span><span class="sxs-lookup"><span data-stu-id="cc986-157">Tests have shown that 12 GB of RAM is sufficient for 100 thousand user deployments.</span></span> <span data-ttu-id="cc986-158">本範例假設 RTC 和 RTCDYN 資料庫大小總計小於 12 GB。</span><span class="sxs-lookup"><span data-stu-id="cc986-158">This assumes that the RTC and RTCDYN databases size totals less than 12 GB.</span></span> <span data-ttu-id="cc986-159">如果您的資料庫大於，您可能需要額外的記憶體。</span><span class="sxs-lookup"><span data-stu-id="cc986-159">If your databases are larger than that, then you may need additional memory.</span></span>

<span data-ttu-id="cc986-160">您可以決定是否在 SQL Server 需要的額外 RAM 檢閱 SQL Server 緩衝區管理員] 頁面上 life expectancy 效能計數器。</span><span class="sxs-lookup"><span data-stu-id="cc986-160">You can determine whether your SQL Server requires additional RAM by reviewing the SQL Server Buffer Manager page life expectancy performance counter.</span></span> <span data-ttu-id="cc986-161">小於 3600 的值會指出記憶體不足。</span><span class="sxs-lookup"><span data-stu-id="cc986-161">A value less than 3,600 indicates memory pressure.</span></span> <span data-ttu-id="cc986-162">您也應該查看資料庫磁碟機上一點為未讀取，如果您有足夠的記憶體，因為 SQL Server 只應寫入至資料庫。</span><span class="sxs-lookup"><span data-stu-id="cc986-162">You should also see little to no reads on your database drive if you have sufficient memory because SQL Server should only be writing to the database.</span></span>

<span data-ttu-id="cc986-163">在 [Lync Server 2013 Front End Server 啟動如果伺服器的處理時間是高沒有額外的節流機制。</span><span class="sxs-lookup"><span data-stu-id="cc986-163">There is an additional throttling mechanism in a Lync Server 2013 Front End Server that starts if the server processing time is high.</span></span> <span data-ttu-id="cc986-164">DBStore 延遲節流設定才會啟用 SQL server 的延遲是高。</span><span class="sxs-lookup"><span data-stu-id="cc986-164">The DBStore latency throttling is only enabled if the latency to the SQL Server is high.</span></span> <span data-ttu-id="cc986-165">在其中啟用這類節流的一個範例是如果前端伺服器 CPU 繫結。</span><span class="sxs-lookup"><span data-stu-id="cc986-165">One example in which such throttling is enabled is if the front-end server is CPU-bound.</span></span>

<span data-ttu-id="cc986-166">如果的平均處理時間 **(LC:SIP-07-負載管理\\SIP 000-平均保留的內送郵件的時間)** 伺服器上超過 6 秒，則伺服器會進入節流模式，並僅提供使用者一個未完成的交易，每個用戶端連線。</span><span class="sxs-lookup"><span data-stu-id="cc986-166">If the average processing time **(LC:SIP-07-Load Management\\SIP-000-Average Holding Time For Incoming Messages)** on the server exceeds six seconds, then the server goes into throttling mode and only gives users one outstanding transaction per client connection.</span></span> <span data-ttu-id="cc986-167">一旦的處理時間減到三秒鐘，伺服器會捨棄節流模式，並提供使用者最多 20 個未完成的交易，每個用戶端連線。</span><span class="sxs-lookup"><span data-stu-id="cc986-167">Once the processing time drops to three seconds, then the server drops out of throttling mode and gives users up to 20 outstanding transactions per client connection.</span></span> <span data-ttu-id="cc986-168">每當的特定連接上的交易數目超過上述的閾值，連線會標示為流量控制。</span><span class="sxs-lookup"><span data-stu-id="cc986-168">Whenever the number of transactions on a specific connection exceeds the threshold above, the connection is marked as flow controlled.</span></span> <span data-ttu-id="cc986-169">結果是在伺服器不會將任何上，會收到和**LC:SIP-01-對等\\流程控制連線**計數器會遞增。</span><span class="sxs-lookup"><span data-stu-id="cc986-169">The result is the server does not post any receives on it, and the **LC:SIP-01-Peers\\Flow Controlled Connections** counter is incremented.</span></span> <span data-ttu-id="cc986-170">如果連線保持在流程控制的狀態為一分鐘以上，然後再將伺服器關閉它。</span><span class="sxs-lookup"><span data-stu-id="cc986-170">If a connection stays in a flow-controlled state for more than one minute, then the server closes it.</span></span> <span data-ttu-id="cc986-171">它會延遲。</span><span class="sxs-lookup"><span data-stu-id="cc986-171">It does so lazily.</span></span> <span data-ttu-id="cc986-172">當它有機會檢查連線時，它會決定是否受到節流的時間太長，並關閉它是否一分鐘以上。</span><span class="sxs-lookup"><span data-stu-id="cc986-172">When it has an opportunity to check the connection, it determines whether it was throttled for too long and closes it if it has more than one minute.</span></span>

<span data-ttu-id="cc986-173">以下是兩個節流機制，且沒有一個摘要項目，如果有的話，節流伺服器正在執行的效能計數器。</span><span class="sxs-lookup"><span data-stu-id="cc986-173">These are the two throttling mechanisms and there is one performance counter that summarizes what, if any, throttling the server is performing.</span></span>

<span data-ttu-id="cc986-174">**LC:SIP-04-回應\\SIP 053 本機 503 回應/秒**</span><span class="sxs-lookup"><span data-stu-id="cc986-174">**LC:SIP-04-Responses\\SIP-053-Local 503 Responses/sec**</span></span>

  - <span data-ttu-id="cc986-175">在先前的計數器中的 「 本機 」 指的是在本機字詞產生回應。</span><span class="sxs-lookup"><span data-stu-id="cc986-175">The term "Local" in the previous counter refers to locally generated responses.</span></span>

  - <span data-ttu-id="cc986-176">503 代碼會對應至伺服器無法使用，其中您應該不會看到任何 503 代碼的狀況良好的伺服器上。</span><span class="sxs-lookup"><span data-stu-id="cc986-176">The 503 code corresponds to server unavailable—where you should not see any 503 codes on a healthy server.</span></span> <span data-ttu-id="cc986-177">在期間伺服器只上線之後, 您可能會看到一些 503 代碼。</span><span class="sxs-lookup"><span data-stu-id="cc986-177">During the period after a server is just brought online, you may see some 503 codes.</span></span> <span data-ttu-id="cc986-178">當所有的使用者登入且伺服器回到穩定狀態時，應該那里任何其他的 503 代碼。</span><span class="sxs-lookup"><span data-stu-id="cc986-178">When all of the users sign back in and the server returns to a stable state, there should no additional 503 codes.</span></span>

<span data-ttu-id="cc986-179">**LC:SIP-04-回應\\SIP 074 本機 504 回應/秒**</span><span class="sxs-lookup"><span data-stu-id="cc986-179">**LC:SIP-04-Responses\\SIP-074-Local 504 Responses/sec**</span></span>

<span data-ttu-id="cc986-180">此效能計數器會指出與其他伺服器的連線問題，它可以表示連線故障或連線的延遲。</span><span class="sxs-lookup"><span data-stu-id="cc986-180">This performance counter indicates connectivity issues with other servers and it can indicate failures to connect or delays in connecting.</span></span> <span data-ttu-id="cc986-181">如果您看到 504 錯誤，然後應該檢查下列效能計數器。</span><span class="sxs-lookup"><span data-stu-id="cc986-181">If you are seeing 504 errors then the following performance counter should be checked.</span></span>

<span data-ttu-id="cc986-182">**LC:SIP-01-對等\\SIP-017-傳送待處理**</span><span class="sxs-lookup"><span data-stu-id="cc986-182">**LC:SIP-01-Peers\\SIP-017-Sends Outstanding**</span></span>

<span data-ttu-id="cc986-183">此計數器會指出數目傳出排入佇列的要求和回應。</span><span class="sxs-lookup"><span data-stu-id="cc986-183">This counter indicates the number of outgoing queued requests and responses.</span></span> <span data-ttu-id="cc986-184">如果此計數器偏高，則問題是很有可能不是在本機伺服器上。</span><span class="sxs-lookup"><span data-stu-id="cc986-184">If this counter is high then the issue is most likely not on the local server.</span></span> <span data-ttu-id="cc986-185">請注意，此計數器可以是高網路延遲問題時。</span><span class="sxs-lookup"><span data-stu-id="cc986-185">Note that this counter can be high if there are network latency issues.</span></span> <span data-ttu-id="cc986-186">它也可能表示區域網路介面卡，發生問題，但更有可能的原因是此問題： 在遠端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="cc986-186">It could also indicate issues with the local network adapter, but is more likely caused by an issue on a remote server.</span></span> <span data-ttu-id="cc986-187">當多載嘗試彼此的集區時，此計數器會很有可能很高 Director 伺服器上。</span><span class="sxs-lookup"><span data-stu-id="cc986-187">This counter would most likely be high on a Director server when the pool it is trying to communicate with is overloaded.</span></span> <span data-ttu-id="cc986-188">使用此計數器機碼是要查看的執行個體，而不只是總計。</span><span class="sxs-lookup"><span data-stu-id="cc986-188">The key with this counter is to look at the instances, not just the total.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

