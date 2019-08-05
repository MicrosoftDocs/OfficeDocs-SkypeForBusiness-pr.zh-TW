---
title: 規劃商務用 Skype Server 的統計資料管理員
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: '摘要: 請閱讀本主題, 瞭解商務用 Skype Server 的統計資料管理員。'
ms.openlocfilehash: a58ca8ea8ed2d612e00a0705bb28e8d6fe95eb45
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193142"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="7593a-103">規劃商務用 Skype Server 的統計資料管理員</span><span class="sxs-lookup"><span data-stu-id="7593a-103">Plan for Statistics Manager for Skype for Business Server</span></span>

<span data-ttu-id="7593a-104">**摘要:** 若要瞭解商務用 Skype Server 的統計資料管理員, 請閱讀本主題。</span><span class="sxs-lookup"><span data-stu-id="7593a-104">**Summary:** Read this topic to learn about Statistics Manager for Skype for Business Server.</span></span>

 <span data-ttu-id="7593a-105">商務用 Skype Server 的 [統計資料管理員] 是一種強大的工具, 可讓您即時查看商務用 Skype Server 健康情況和效能資料。</span><span class="sxs-lookup"><span data-stu-id="7593a-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="7593a-106">您可以每隔幾秒在數百個伺服器上輪詢效能資料, 並立即在統計資料管理器網站上查看結果。</span><span class="sxs-lookup"><span data-stu-id="7593a-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>

<span data-ttu-id="7593a-107">您可以使用 [統計資料管理器] 來找出持續的效能問題、查看已規劃變更對您的環境的結果、追蹤中斷的解決方式等等。</span><span class="sxs-lookup"><span data-stu-id="7593a-107">You can use Statistics Manager to identify ongoing performance issues, view the results of a planned change to your environment, track resolution of outages, and much more.</span></span> <span data-ttu-id="7593a-108">在該框中, 統計管理員是使用金鑰健康情況指標 (KHI) 閾值來設定, 而且可以根據您的部署的獨特需求加以自訂。</span><span class="sxs-lookup"><span data-stu-id="7593a-108">Out of the box, Statistics Manager is configured with Key Health Indicator (KHI) thresholds, and can be customized to suit your deployment's unique needs.</span></span>

<span data-ttu-id="7593a-109">您可以在內部部署中部署統計資料管理器, 其中單一伺服器會託管所有伺服器端統計資料管理器元件。</span><span class="sxs-lookup"><span data-stu-id="7593a-109">You can deploy Statistics Manager in an on-premises deployment in which a single server hosts all of the server-side Statistics Manager components.</span></span> <span data-ttu-id="7593a-110">如需有關部署統計管理員的詳細資訊, 請參閱[部署商務用 Skype Server 的統計資料管理器](deploy.md)。</span><span class="sxs-lookup"><span data-stu-id="7593a-110">For more information about deploying Statistics Manager, see [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span> <span data-ttu-id="7593a-111">如果您已有現有的統計資料管理員部署, 但您尚未升級至發行 2.0, 請參閱[版本2.0 的新增功能](plan.md#BKMK_WhatsNew)和[商務用 Skype Server 的 [升級統計資料管理員]](upgrade.md)。</span><span class="sxs-lookup"><span data-stu-id="7593a-111">If you already have an existing deployment of Statistics Manager, but you have not yet upgraded to Release 2.0, see [What's new in Release 2.0](plan.md#BKMK_WhatsNew) and [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

<span data-ttu-id="7593a-112">本主題包含下列各節:</span><span class="sxs-lookup"><span data-stu-id="7593a-112">This topic contains the following sections:</span></span>

- [<span data-ttu-id="7593a-113">功能與功能</span><span class="sxs-lookup"><span data-stu-id="7593a-113">Features and capabilities</span></span>](plan.md#BKMK_Features)

- [<span data-ttu-id="7593a-114">版本2.0 的新功能</span><span class="sxs-lookup"><span data-stu-id="7593a-114">What's new in Release 2.0</span></span>](plan.md#BKMK_WhatsNew)

- [<span data-ttu-id="7593a-115">元件</span><span class="sxs-lookup"><span data-stu-id="7593a-115">Components</span></span>](plan.md#BKMK_Components)

- [<span data-ttu-id="7593a-116">內部部署</span><span class="sxs-lookup"><span data-stu-id="7593a-116">On-premises deployment</span></span>](plan.md#BKMK_DeploymentOptions)

- [<span data-ttu-id="7593a-117">需求</span><span class="sxs-lookup"><span data-stu-id="7593a-117">Requirements</span></span>](plan.md#BKMK_Requirements)

- [<span data-ttu-id="7593a-118">安全性考慮</span><span class="sxs-lookup"><span data-stu-id="7593a-118">Security considerations</span></span>](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a><span data-ttu-id="7593a-119">功能與功能</span><span class="sxs-lookup"><span data-stu-id="7593a-119">Features and capabilities</span></span>
<span data-ttu-id="7593a-120"><a name="BKMK_Features"> </a></span><span class="sxs-lookup"><span data-stu-id="7593a-120"></span></span>

<span data-ttu-id="7593a-121">[統計資料管理器] 可讓您:</span><span class="sxs-lookup"><span data-stu-id="7593a-121">Statistics Manager allows you to:</span></span>

- <span data-ttu-id="7593a-122">即時查看所有伺服器的原始資料。</span><span class="sxs-lookup"><span data-stu-id="7593a-122">View raw data for all servers in real time.</span></span> <span data-ttu-id="7593a-123">(以極高的速率取樣資料, 並以少於一秒的時間傳送到網站。)</span><span class="sxs-lookup"><span data-stu-id="7593a-123">(Data is sampled at a very high rate and sent to the website in less than one second.)</span></span>

- <span data-ttu-id="7593a-124">針對特定角色來查看匯總的資料;例如, [前端伺服器]、[中繼伺服器]、[Edge 伺服器] 等等。</span><span class="sxs-lookup"><span data-stu-id="7593a-124">View data that is aggregated for a specific role; for example, Front End Server, Mediation Server, Edge Server, and so on.</span></span>

- <span data-ttu-id="7593a-125">向下切入以查看特定網站的資料、網站內的特定 pool, 以及池中的特定伺服器。</span><span class="sxs-lookup"><span data-stu-id="7593a-125">Drill down to view data for specific sites, specific pools within the site, and then specific servers within the pool.</span></span>

- <span data-ttu-id="7593a-126">建立自訂圖表, 以便預設顯示所選的計數器。</span><span class="sxs-lookup"><span data-stu-id="7593a-126">Create custom charts so that chosen counters are shown by default.</span></span>

- <span data-ttu-id="7593a-127">在 X 軸與 y 軸上, 或只在 X 軸上縮放和平移。</span><span class="sxs-lookup"><span data-stu-id="7593a-127">Zoom and pan on both the x- and y- axes or on the x-axis only.</span></span>

- <span data-ttu-id="7593a-128">使用日期範圍或時間點來篩選資料。</span><span class="sxs-lookup"><span data-stu-id="7593a-128">Use date ranges or points in time to filter data.</span></span>

- <span data-ttu-id="7593a-129">根據已建立的金鑰健康情況指示 (KHIs) 來查看伺服器效能。</span><span class="sxs-lookup"><span data-stu-id="7593a-129">View server performance based on established key health indicators (KHIs).</span></span> <span data-ttu-id="7593a-130">KHIs 代表已定義正常範圍的效能計數器集合。</span><span class="sxs-lookup"><span data-stu-id="7593a-130">KHIs represent a collection of performance counters with a defined healthy range.</span></span>

- <span data-ttu-id="7593a-131">查看每個計數器的詳細度量單位。</span><span class="sxs-lookup"><span data-stu-id="7593a-131">View detailed metrics for each counter.</span></span>

- <span data-ttu-id="7593a-132">比較多個人口或伺服器上的資料。</span><span class="sxs-lookup"><span data-stu-id="7593a-132">Compare data across multiple populations or servers.</span></span>

- <span data-ttu-id="7593a-133">查看潛在的計數器報告, 找出未向儀表板服務報告目前資料的代理程式。</span><span class="sxs-lookup"><span data-stu-id="7593a-133">View latent counter reports to identify agents that are not reporting current data to the dashboard service.</span></span>

- <span data-ttu-id="7593a-134">將圖表資料的特定實例儲存至檔案。</span><span class="sxs-lookup"><span data-stu-id="7593a-134">Save a particular instance of chart data to a file.</span></span>

- <span data-ttu-id="7593a-135">即時查看 KHIs, 包括更新。</span><span class="sxs-lookup"><span data-stu-id="7593a-135">View KHIs in real time, including updates.</span></span> <span data-ttu-id="7593a-136">如果已啟用 [歷程記錄] 視圖, 就只會顯示新的失敗。</span><span class="sxs-lookup"><span data-stu-id="7593a-136">If the history view is enabled, only new failures are shown.</span></span>

  - <span data-ttu-id="7593a-137">一次查看所有 KHIs</span><span class="sxs-lookup"><span data-stu-id="7593a-137">View all KHIs at one time</span></span>

  - <span data-ttu-id="7593a-138">依伺服器查看 KHIs (橫向視圖)</span><span class="sxs-lookup"><span data-stu-id="7593a-138">View KHIs by server (Landscape view)</span></span>

  - <span data-ttu-id="7593a-139">查看 KHI 定義</span><span class="sxs-lookup"><span data-stu-id="7593a-139">View KHI definitions</span></span>

## <a name="whats-new-in-release-20"></a><span data-ttu-id="7593a-140">版本2.0 的新功能</span><span class="sxs-lookup"><span data-stu-id="7593a-140">What's new in Release 2.0</span></span>
<span data-ttu-id="7593a-141"><a name="BKMK_WhatsNew"> </a></span><span class="sxs-lookup"><span data-stu-id="7593a-141"></span></span>

<span data-ttu-id="7593a-142">下列說明版本2.0 的新增功能。</span><span class="sxs-lookup"><span data-stu-id="7593a-142">The following describes what's new in Release 2.0.</span></span> <span data-ttu-id="7593a-143">如果您已有部署的統計資料管理員, 但尚未升級, 請參閱[商務用 Skype Server 的升級統計資料管理器](upgrade.md)。</span><span class="sxs-lookup"><span data-stu-id="7593a-143">If you have an existing deployment of Statistics Manager and you've not yet upgraded, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

- <span data-ttu-id="7593a-144">已針對 Edge 媒體、結構健康情況、池容錯移轉及註冊案例新增案例視圖。</span><span class="sxs-lookup"><span data-stu-id="7593a-144">Scenario views have been added for Edge Media, Fabric Health, Pool Failover and Registration scenarios.</span></span>

- <span data-ttu-id="7593a-145">已為 SQL server 新增許多新的計數器、更多商務用 Skype 使用量計數器等。</span><span class="sxs-lookup"><span data-stu-id="7593a-145">Many new counters have been added for SQL servers, more Skype for Business usage counters, and so on.</span></span>

- <span data-ttu-id="7593a-146">[統計資料管理員] 代理程式的 [觀察程式節點整合]-如果該代理程式已安裝在監視者節點上, 它會將綜合交易處理統計資料包告為計數器傳回統計資料管理員。</span><span class="sxs-lookup"><span data-stu-id="7593a-146">Watcher node integration for the Statistics Manager Agent - if the Agent is installed on a watcher node, it will report synthetic transaction statistics as counters back to Statistics Manager.</span></span>

- <span data-ttu-id="7593a-147">許多可靠性和效能的改進。</span><span class="sxs-lookup"><span data-stu-id="7593a-147">Numerous reliability and performance improvements.</span></span>

<span data-ttu-id="7593a-148">若要確認您執行的統計資料管理器網站版本是否正常:</span><span class="sxs-lookup"><span data-stu-id="7593a-148">To verify the version of the Statistics Manager Website you are running:</span></span>

- <span data-ttu-id="7593a-149">在檔案資源管理器中, 開啟 (預設目錄) C:\Program Files\Skype for Business Server StatsMan WebSite\bin</span><span class="sxs-lookup"><span data-stu-id="7593a-149">In File Explorer, open (default directory) C:\Program Files\Skype for Business Server StatsMan WebSite\bin</span></span>

- <span data-ttu-id="7593a-150">以滑鼠右鍵按一下 [StatsManHubWebSite] 並查看其屬性</span><span class="sxs-lookup"><span data-stu-id="7593a-150">Right click on StatsManHubWebSite.dll and view its properties</span></span>

- <span data-ttu-id="7593a-151">產品版本將會顯示在描述詳細資料中。</span><span class="sxs-lookup"><span data-stu-id="7593a-151">The product version will be shown in the Description details.</span></span>

## <a name="components"></a><span data-ttu-id="7593a-152">元件</span><span class="sxs-lookup"><span data-stu-id="7593a-152">Components</span></span>
<span data-ttu-id="7593a-153"><a name="BKMK_Components"> </a></span><span class="sxs-lookup"><span data-stu-id="7593a-153"></span></span>

<span data-ttu-id="7593a-154">[統計資料管理器] 由下列元件組成:</span><span class="sxs-lookup"><span data-stu-id="7593a-154">Statistics Manager consists of the following components:</span></span>

- <span data-ttu-id="7593a-155">**代理程式.**</span><span class="sxs-lookup"><span data-stu-id="7593a-155">**Agent.**</span></span> <span data-ttu-id="7593a-156">在每個受監視的伺服器上執行的輕型代理程式。</span><span class="sxs-lookup"><span data-stu-id="7593a-156">A lightweight agent that runs on each monitored server.</span></span> <span data-ttu-id="7593a-157">代理程式允許可設定的高速率輪詢與本機集合的效能。</span><span class="sxs-lookup"><span data-stu-id="7593a-157">The Agent allows configurable high rate polling of performance counters with local aggregation.</span></span>

- <span data-ttu-id="7593a-158">**接聽程式.**</span><span class="sxs-lookup"><span data-stu-id="7593a-158">**Listener.**</span></span> <span data-ttu-id="7593a-159">從所有代理程式接收資料的伺服器端 API, 以及跨人口匯總資料。</span><span class="sxs-lookup"><span data-stu-id="7593a-159">The server side API that receives data from all Agents, and aggregates data across populations.</span></span>

- <span data-ttu-id="7593a-160">**中樞.**</span><span class="sxs-lookup"><span data-stu-id="7593a-160">**Hub.**</span></span> <span data-ttu-id="7593a-161">充當系統的用戶端 API, 在 web 伺服器上執行, 並提供透過網站連線的用戶端即時資料更新。</span><span class="sxs-lookup"><span data-stu-id="7593a-161">Serves as the client API for the system, runs on the web server(s), and provides real-time data updates to clients connected via the website.</span></span> <span data-ttu-id="7593a-162">(中樞會自動安裝為網站 msi 的一部分)。</span><span class="sxs-lookup"><span data-stu-id="7593a-162">(The Hub is automatically installed as part of the Website msi.)</span></span>

- <span data-ttu-id="7593a-163">**Web.**</span><span class="sxs-lookup"><span data-stu-id="7593a-163">**Website.**</span></span> <span data-ttu-id="7593a-164">可將系統中所有可用功能集中在一起的使用者介面。</span><span class="sxs-lookup"><span data-stu-id="7593a-164">A user interface that pulls together all the features available in the system.</span></span>

<span data-ttu-id="7593a-165">此外, 統計資料管理員還需要**Redis**, 也就是用來進行記憶體中快取的開放式資料結構伺服器。</span><span class="sxs-lookup"><span data-stu-id="7593a-165">In addition, Statistics Manager requires **Redis**, an open-sourced data structure server for in-memory caching.</span></span> <span data-ttu-id="7593a-166">如需有關下載 Redis 的詳細資訊, 請參閱[部署統計資料管理器](deploy.md#BKMK_Deploy)。</span><span class="sxs-lookup"><span data-stu-id="7593a-166">For more information about downloading Redis, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy) .</span></span>

## <a name="on-premises-deployment"></a><span data-ttu-id="7593a-167">內部部署</span><span class="sxs-lookup"><span data-stu-id="7593a-167">On-premises deployment</span></span>
<span data-ttu-id="7593a-168"><a name="BKMK_DeploymentOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="7593a-168"></span></span>

<span data-ttu-id="7593a-169">在內部部署的部署中, 單一伺服器會託管所有伺服器端統計資料管理員元件。</span><span class="sxs-lookup"><span data-stu-id="7593a-169">In an on-premises deployment, a single server hosts all of the server-side Statistics Manager components.</span></span>

<span data-ttu-id="7593a-170">下圖顯示內部部署, 其中統計管理員網站、中樞、偵聽程式及 Redis 緩存系統都是在單一電腦上託管。</span><span class="sxs-lookup"><span data-stu-id="7593a-170">The following diagram shows an on-premises deployment, in which the Statistics Manager Website, Hub, Listener, and Redis caching system are hosted on a single machine.</span></span> <span data-ttu-id="7593a-171">[統計資料管理員] 正在監視三個商務用 Skype 伺服器, 每一個都有一個代理程式將資料傳送到監聽器。</span><span class="sxs-lookup"><span data-stu-id="7593a-171">Statistics Manager is monitoring three Skype for Business servers, each of which have a single Agent transmitting data to the Listener.</span></span> <span data-ttu-id="7593a-172">使用者連線到單一網站, 以查看統計資料管理員匯總的所有資料:</span><span class="sxs-lookup"><span data-stu-id="7593a-172">Users connect to a single Website to view all data aggregated by Statistics Manager:</span></span>

![統計管理員內部部署](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a><span data-ttu-id="7593a-174">需求</span><span class="sxs-lookup"><span data-stu-id="7593a-174">Requirements</span></span>
<span data-ttu-id="7593a-175"><a name="BKMK_Requirements"> </a></span><span class="sxs-lookup"><span data-stu-id="7593a-175"></span></span>

<span data-ttu-id="7593a-176">在部署統計資料管理器之前, 您必須先考慮下列軟體、網路和硬體需求。</span><span class="sxs-lookup"><span data-stu-id="7593a-176">You will need to consider the following software, networking, and hardware requirements before you deploy Statistics Manager.</span></span>

### <a name="software-requirements"></a><span data-ttu-id="7593a-177">軟體需求</span><span class="sxs-lookup"><span data-stu-id="7593a-177">Software requirements</span></span>

- <span data-ttu-id="7593a-178">Windows Server 2016 和2019</span><span class="sxs-lookup"><span data-stu-id="7593a-178">Windows Server 2016 and 2019</span></span>

- <span data-ttu-id="7593a-179">IIS (自動安裝)</span><span class="sxs-lookup"><span data-stu-id="7593a-179">IIS (automatically installed)</span></span>

- <span data-ttu-id="7593a-180">Redis</span><span class="sxs-lookup"><span data-stu-id="7593a-180">Redis</span></span>

- <span data-ttu-id="7593a-181">Statistics 管理員服務 (自動安裝)</span><span class="sxs-lookup"><span data-stu-id="7593a-181">Statistics Manager services (automatically installed)</span></span>

- <span data-ttu-id="7593a-182">PSExec-需要執行遠端代理程式部署</span><span class="sxs-lookup"><span data-stu-id="7593a-182">PSExec - Required to do remote agent deployment</span></span>

- <span data-ttu-id="7593a-183">.NET 4.5 (隨附于 2012 R2)-代理程式和伺服器端元件所需</span><span class="sxs-lookup"><span data-stu-id="7593a-183">.NET 4.5 (included with 2012 R2) - Required for agents and server-side components</span></span>
- <span data-ttu-id="7593a-184">下載[商務用 Skype Server、即時統計資料管理器 (64 位)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span><span class="sxs-lookup"><span data-stu-id="7593a-184">Download the [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="7593a-185">網路需求</span><span class="sxs-lookup"><span data-stu-id="7593a-185">Networking requirements</span></span>


|<span data-ttu-id="7593a-186">**主機伺服器**</span><span class="sxs-lookup"><span data-stu-id="7593a-186">**Hosting server**</span></span>|<span data-ttu-id="7593a-187">**代理程式**</span><span class="sxs-lookup"><span data-stu-id="7593a-187">**Agents**</span></span>|<span data-ttu-id="7593a-188">**接聽程式**</span><span class="sxs-lookup"><span data-stu-id="7593a-188">**Listener**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7593a-189">最低十億位元全雙工網路。</span><span class="sxs-lookup"><span data-stu-id="7593a-189">Minimum gigabit full duplex networking.</span></span>  <br/> |<span data-ttu-id="7593a-190">輸出 TCP 埠 8443 (可自訂埠號碼) 與監聽器通訊。</span><span class="sxs-lookup"><span data-stu-id="7593a-190">Outbound TCP port 8443 (customizable port number) to communicate with the Listener.</span></span>  <br/> |<span data-ttu-id="7593a-191">偵聽程式埠在所有伺服器上都必須是相同的。</span><span class="sxs-lookup"><span data-stu-id="7593a-191">The Listener port must be the same on all servers.</span></span>  <br/> |
|<span data-ttu-id="7593a-192">輸入 TCP 埠80或443開啟以託管網站。</span><span class="sxs-lookup"><span data-stu-id="7593a-192">Inbound TCP port 80 or 443 open to host the website.</span></span>  <br/> |||
|<span data-ttu-id="7593a-193">入站 TCP 埠 8443 (可自訂埠號碼), 可供代理程式與其通訊。</span><span class="sxs-lookup"><span data-stu-id="7593a-193">Inbound TCP port 8443 (customizable port number) for the agents to communicate with it.</span></span>  <br/> |||

<span data-ttu-id="7593a-194">在安裝期間, 系統會自動建立監聽器和網站的防火牆埠。</span><span class="sxs-lookup"><span data-stu-id="7593a-194">During installation, firewall ports for the Listener and the Website are automatically created.</span></span> <span data-ttu-id="7593a-195">針對代理程式, 安裝會假設預設允許出站 TCP 連線。</span><span class="sxs-lookup"><span data-stu-id="7593a-195">For the Agents, the installation assumes that outbound TCP connections are allowed by default.</span></span>

### <a name="hardware-requirements"></a><span data-ttu-id="7593a-196">硬體需求</span><span class="sxs-lookup"><span data-stu-id="7593a-196">Hardware requirements</span></span>

<span data-ttu-id="7593a-197">在內部部署中, 單一伺服器會將所有伺服器端統計資料管理器元件組成一個主機, 且有 16 GB RAM 和4個 CPU 的伺服器應該能夠支援每秒平均150樣本。</span><span class="sxs-lookup"><span data-stu-id="7593a-197">In an on-premises deployment, in which a single server hosts all of the server-side Statistics Manager components, a server with 16 GB of RAM and 4 CPU's should be able to support about 150 samples per second on average.</span></span> <span data-ttu-id="7593a-198">若要判斷您可以支援多少計數器/代理程式, 請使用下列計算:</span><span class="sxs-lookup"><span data-stu-id="7593a-198">To determine how many counters/agents you can support, use the following calculation:</span></span>

<span data-ttu-id="7593a-199">100 server \*80 每\*秒從每個代理程式/60 秒的每分鐘樣本1樣本 = 大約每秒133樣本。</span><span class="sxs-lookup"><span data-stu-id="7593a-199">100 servers \*80 counters \* 1 sample per minute from each agent / 60 seconds = ~ 133 samples per second.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="7593a-200">安全性考慮</span><span class="sxs-lookup"><span data-stu-id="7593a-200">Security considerations</span></span>
<span data-ttu-id="7593a-201"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="7593a-201"></span></span>

<span data-ttu-id="7593a-202">伺服器之間的所有流量都會經過加密。</span><span class="sxs-lookup"><span data-stu-id="7593a-202">All traffic between servers is encrypted.</span></span>

- <span data-ttu-id="7593a-203">加密的 HTTPS 流量會透過埠 8443 (預設) 傳送到偵聽程式伺服器。</span><span class="sxs-lookup"><span data-stu-id="7593a-203">Encrypted HTTPS traffic will be sent over port 8443 (by default) from the Agent to the Listener server.</span></span>

- <span data-ttu-id="7593a-204">Agent 將在伺服器上驗證 SSL 指紋, 以確保監聽器伺服器為預期的收件者。</span><span class="sxs-lookup"><span data-stu-id="7593a-204">The Agent will verify the SSL thumbprint on the server to ensure the Listener server is the expected recipient.</span></span> <span data-ttu-id="7593a-205">請注意, 代理程式會使用證書指紋驗證 (而不是鏈式驗證)。</span><span class="sxs-lookup"><span data-stu-id="7593a-205">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="7593a-206">因為可以使用自我簽署的憑證, 所以它不會進行完整的憑證驗證。</span><span class="sxs-lookup"><span data-stu-id="7593a-206">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>

- <span data-ttu-id="7593a-207">在符合代理程式的真實情況下, 系統會透過監聽器驗證該代理程式來出示該密碼。</span><span class="sxs-lookup"><span data-stu-id="7593a-207">After the Agent is satisfied the Listener is authentic, a password will be presented by the Agent which is then verified by the Listener.</span></span>

- <span data-ttu-id="7593a-208">代理程式會開始以連線到監聽器的連線來傳送效能資料。</span><span class="sxs-lookup"><span data-stu-id="7593a-208">The Agent begins transmitting performance data over the connection to the Listener.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="7593a-209">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="7593a-209">For more information</span></span>
<span data-ttu-id="7593a-210"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="7593a-210"></span></span>

<span data-ttu-id="7593a-211">如需詳細資訊, 請參閱下列內容:</span><span class="sxs-lookup"><span data-stu-id="7593a-211">For more information, see the following:</span></span>

- [<span data-ttu-id="7593a-212">部署商務用 Skype Server 的統計資料管理器</span><span class="sxs-lookup"><span data-stu-id="7593a-212">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)

- [<span data-ttu-id="7593a-213">商務用 Skype Server 的升級統計資料管理員</span><span class="sxs-lookup"><span data-stu-id="7593a-213">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)

- [<span data-ttu-id="7593a-214">疑難排解商務用 Skype Server 的統計管理員</span><span class="sxs-lookup"><span data-stu-id="7593a-214">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
