---
title: 商務用 Skype Server 統計資料的規劃
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 摘要：閱讀此主題以瞭解商務用 Skype Server 的統計資料管理員。
ms.openlocfilehash: cdc536abcbd1bd98c4a3c7ce974247a716865582
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821823"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="283bd-103">商務用 Skype Server 統計資料的規劃</span><span class="sxs-lookup"><span data-stu-id="283bd-103">Plan for Statistics Manager for Skype for Business Server</span></span>

<span data-ttu-id="283bd-104">**摘要：** 閱讀此主題以瞭解商務用 Skype Server 的統計資料管理員。</span><span class="sxs-lookup"><span data-stu-id="283bd-104">**Summary:** Read this topic to learn about Statistics Manager for Skype for Business Server.</span></span>

 <span data-ttu-id="283bd-105">商務用 Skype Server 的統計資料管理員是一種強大的工具，可讓您即時查看商務用 Skype 伺服器的健康情況和效能資料。</span><span class="sxs-lookup"><span data-stu-id="283bd-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="283bd-106">您可以每隔幾秒輪詢每數百部伺服器上的效能資料，並在統計資料管理員網站上立即查看結果。</span><span class="sxs-lookup"><span data-stu-id="283bd-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>

<span data-ttu-id="283bd-107">您可以使用 [統計資料管理員] 來找出持續效能問題、查看對環境所做的計畫變更，追蹤中斷的解決方式，以及其他更多的結果。</span><span class="sxs-lookup"><span data-stu-id="283bd-107">You can use Statistics Manager to identify ongoing performance issues, view the results of a planned change to your environment, track resolution of outages, and much more.</span></span> <span data-ttu-id="283bd-108">現成的統計資料管理員會使用重要健康情況指示器 (KHI) 閾值來設定，而且可以自訂以符合您的部署的獨特需求。</span><span class="sxs-lookup"><span data-stu-id="283bd-108">Out of the box, Statistics Manager is configured with Key Health Indicator (KHI) thresholds, and can be customized to suit your deployment's unique needs.</span></span>

<span data-ttu-id="283bd-109">在內部部署中，您可以在單一伺服器主控所有伺服器端統計資料管理員元件的內部部署中部署統計資料管理員。</span><span class="sxs-lookup"><span data-stu-id="283bd-109">You can deploy Statistics Manager in an on-premises deployment in which a single server hosts all of the server-side Statistics Manager components.</span></span> <span data-ttu-id="283bd-110">如需部署統計資料管理員的詳細資訊，請參閱 [部署統計資料管理員以取得商務用 Skype Server](deploy.md)。</span><span class="sxs-lookup"><span data-stu-id="283bd-110">For more information about deploying Statistics Manager, see [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span> <span data-ttu-id="283bd-111">如果您已有統計資料管理員的現有部署，但尚未升級為版本2.0，請參閱 [release 2.0 的新功能](plan.md#BKMK_WhatsNew) 和 [升級統計資料管理員以取得商務用 Skype Server](upgrade.md)。</span><span class="sxs-lookup"><span data-stu-id="283bd-111">If you already have an existing deployment of Statistics Manager, but you have not yet upgraded to Release 2.0, see [What's new in Release 2.0](plan.md#BKMK_WhatsNew) and [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

<span data-ttu-id="283bd-112">本主題包含下列各節：</span><span class="sxs-lookup"><span data-stu-id="283bd-112">This topic contains the following sections:</span></span>

- [<span data-ttu-id="283bd-113">特性和功能</span><span class="sxs-lookup"><span data-stu-id="283bd-113">Features and capabilities</span></span>](plan.md#BKMK_Features)

- [<span data-ttu-id="283bd-114">版本2.0 的新功能</span><span class="sxs-lookup"><span data-stu-id="283bd-114">What's new in Release 2.0</span></span>](plan.md#BKMK_WhatsNew)

- [<span data-ttu-id="283bd-115">元件</span><span class="sxs-lookup"><span data-stu-id="283bd-115">Components</span></span>](plan.md#BKMK_Components)

- [<span data-ttu-id="283bd-116">內部部署</span><span class="sxs-lookup"><span data-stu-id="283bd-116">On-premises deployment</span></span>](plan.md#BKMK_DeploymentOptions)

- [<span data-ttu-id="283bd-117">需求</span><span class="sxs-lookup"><span data-stu-id="283bd-117">Requirements</span></span>](plan.md#BKMK_Requirements)

- [<span data-ttu-id="283bd-118">安全性注意事項</span><span class="sxs-lookup"><span data-stu-id="283bd-118">Security considerations</span></span>](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a><span data-ttu-id="283bd-119">特性和功能</span><span class="sxs-lookup"><span data-stu-id="283bd-119">Features and capabilities</span></span>
<span data-ttu-id="283bd-120"><a name="BKMK_Features"> </a></span><span class="sxs-lookup"><span data-stu-id="283bd-120"><a name="BKMK_Features"> </a></span></span>

<span data-ttu-id="283bd-121">統計資料管理員可讓您：</span><span class="sxs-lookup"><span data-stu-id="283bd-121">Statistics Manager allows you to:</span></span>

- <span data-ttu-id="283bd-122">即時查看所有伺服器的原始資料。</span><span class="sxs-lookup"><span data-stu-id="283bd-122">View raw data for all servers in real time.</span></span> <span data-ttu-id="283bd-123"> (資料會以極高的速率進行抽樣，並在小於一秒內傳送至網站。 ) </span><span class="sxs-lookup"><span data-stu-id="283bd-123">(Data is sampled at a very high rate and sent to the website in less than one second.)</span></span>

- <span data-ttu-id="283bd-124">查看針對特定角色進行匯總的資料;例如，前端伺服器、轉送伺服器、Edge Server 等等。</span><span class="sxs-lookup"><span data-stu-id="283bd-124">View data that is aggregated for a specific role; for example, Front End Server, Mediation Server, Edge Server, and so on.</span></span>

- <span data-ttu-id="283bd-125">向下流覽以查看特定網站、網站內特定集區的資料，以及集區中的特定伺服器。</span><span class="sxs-lookup"><span data-stu-id="283bd-125">Drill down to view data for specific sites, specific pools within the site, and then specific servers within the pool.</span></span>

- <span data-ttu-id="283bd-126">建立自訂圖表，以預設顯示所選的計數器。</span><span class="sxs-lookup"><span data-stu-id="283bd-126">Create custom charts so that chosen counters are shown by default.</span></span>

- <span data-ttu-id="283bd-127">僅在 X 軸和 y 軸上，或在 X 軸上進行縮放及平移。</span><span class="sxs-lookup"><span data-stu-id="283bd-127">Zoom and pan on both the x- and y- axes or on the x-axis only.</span></span>

- <span data-ttu-id="283bd-128">使用日期範圍或時間點來篩選資料。</span><span class="sxs-lookup"><span data-stu-id="283bd-128">Use date ranges or points in time to filter data.</span></span>

- <span data-ttu-id="283bd-129">根據建立的主要健康情況指示器，查看伺服器效能 (KHIs) 。</span><span class="sxs-lookup"><span data-stu-id="283bd-129">View server performance based on established key health indicators (KHIs).</span></span> <span data-ttu-id="283bd-130">KHIs 代表具有定義之狀況良好範圍的效能計數器集合。</span><span class="sxs-lookup"><span data-stu-id="283bd-130">KHIs represent a collection of performance counters with a defined healthy range.</span></span>

- <span data-ttu-id="283bd-131">查看每個計數器的詳細度量。</span><span class="sxs-lookup"><span data-stu-id="283bd-131">View detailed metrics for each counter.</span></span>

- <span data-ttu-id="283bd-132">比較多個人口或伺服器上的資料。</span><span class="sxs-lookup"><span data-stu-id="283bd-132">Compare data across multiple populations or servers.</span></span>

- <span data-ttu-id="283bd-133">View 潛在的計數器報告，以找出未向儀表板服務報告目前資料的代理人。</span><span class="sxs-lookup"><span data-stu-id="283bd-133">View latent counter reports to identify agents that are not reporting current data to the dashboard service.</span></span>

- <span data-ttu-id="283bd-134">將圖表資料的特定實例儲存至檔案。</span><span class="sxs-lookup"><span data-stu-id="283bd-134">Save a particular instance of chart data to a file.</span></span>

- <span data-ttu-id="283bd-135">即時查看 KHIs，包含更新。</span><span class="sxs-lookup"><span data-stu-id="283bd-135">View KHIs in real time, including updates.</span></span> <span data-ttu-id="283bd-136">如果啟用 [歷程記錄] 視圖，只會顯示新的失敗。</span><span class="sxs-lookup"><span data-stu-id="283bd-136">If the history view is enabled, only new failures are shown.</span></span>

  - <span data-ttu-id="283bd-137">一次查看所有 KHIs</span><span class="sxs-lookup"><span data-stu-id="283bd-137">View all KHIs at one time</span></span>

  - <span data-ttu-id="283bd-138">透過伺服器 (景觀 view 查看 KHIs) </span><span class="sxs-lookup"><span data-stu-id="283bd-138">View KHIs by server (Landscape view)</span></span>

  - <span data-ttu-id="283bd-139">View KHI 定義</span><span class="sxs-lookup"><span data-stu-id="283bd-139">View KHI definitions</span></span>

## <a name="whats-new-in-release-20"></a><span data-ttu-id="283bd-140">版本2.0 的新功能</span><span class="sxs-lookup"><span data-stu-id="283bd-140">What's new in Release 2.0</span></span>
<span data-ttu-id="283bd-141"><a name="BKMK_WhatsNew"> </a></span><span class="sxs-lookup"><span data-stu-id="283bd-141"><a name="BKMK_WhatsNew"> </a></span></span>

<span data-ttu-id="283bd-142">下列說明版本2.0 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="283bd-142">The following describes what's new in Release 2.0.</span></span> <span data-ttu-id="283bd-143">如果您有現有的統計資料管理員部署，但尚未升級，請參閱 [升級統計資料管理員以取得商務用 Skype Server](upgrade.md)。</span><span class="sxs-lookup"><span data-stu-id="283bd-143">If you have an existing deployment of Statistics Manager and you've not yet upgraded, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

- <span data-ttu-id="283bd-144">已針對 Edge Media、Fabric Health、集區容錯移轉和註冊案例新增方案視圖。</span><span class="sxs-lookup"><span data-stu-id="283bd-144">Scenario views have been added for Edge Media, Fabric Health, Pool Failover and Registration scenarios.</span></span>

- <span data-ttu-id="283bd-145">已為 SQL server 新增許多新的計數器、商務用 Skype 使用計數器等等。</span><span class="sxs-lookup"><span data-stu-id="283bd-145">Many new counters have been added for SQL servers, more Skype for Business usage counters, and so on.</span></span>

- <span data-ttu-id="283bd-146">與統計資料管理員代理程式的監看員節點整合–如果在監看員節點上安裝代理程式，它會將綜合交易統計資料包告為計數器傳回統計資料管理員。</span><span class="sxs-lookup"><span data-stu-id="283bd-146">Watcher node integration for the Statistics Manager Agent - if the Agent is installed on a watcher node, it will report synthetic transaction statistics as counters back to Statistics Manager.</span></span>

- <span data-ttu-id="283bd-147">許多可靠性和效能的增強功能。</span><span class="sxs-lookup"><span data-stu-id="283bd-147">Numerous reliability and performance improvements.</span></span>

<span data-ttu-id="283bd-148">若要驗證您正在執行的統計資料管理員網站版本：</span><span class="sxs-lookup"><span data-stu-id="283bd-148">To verify the version of the Statistics Manager Website you are running:</span></span>

- <span data-ttu-id="283bd-149">在檔案瀏覽器中，開啟 (的預設目錄) C:\Program Files\Skype for Business Server StatsMan WebSite\bin</span><span class="sxs-lookup"><span data-stu-id="283bd-149">In File Explorer, open (default directory) C:\Program Files\Skype for Business Server StatsMan WebSite\bin</span></span>

- <span data-ttu-id="283bd-150">在 StatsManHubWebSite.dll 上按一下滑鼠右鍵，並查看其屬性</span><span class="sxs-lookup"><span data-stu-id="283bd-150">Right click on StatsManHubWebSite.dll and view its properties</span></span>

- <span data-ttu-id="283bd-151">產品版本將會顯示在描述詳細資料中。</span><span class="sxs-lookup"><span data-stu-id="283bd-151">The product version will be shown in the Description details.</span></span>

## <a name="components"></a><span data-ttu-id="283bd-152">元件</span><span class="sxs-lookup"><span data-stu-id="283bd-152">Components</span></span>
<span data-ttu-id="283bd-153"><a name="BKMK_Components"> </a></span><span class="sxs-lookup"><span data-stu-id="283bd-153"><a name="BKMK_Components"> </a></span></span>

<span data-ttu-id="283bd-154">統計資料管理員包含下列元件：</span><span class="sxs-lookup"><span data-stu-id="283bd-154">Statistics Manager consists of the following components:</span></span>

- <span data-ttu-id="283bd-155">**代理。**</span><span class="sxs-lookup"><span data-stu-id="283bd-155">**Agent.**</span></span> <span data-ttu-id="283bd-156">在每個受監視伺服器上執行的輕量代理程式。</span><span class="sxs-lookup"><span data-stu-id="283bd-156">A lightweight agent that runs on each monitored server.</span></span> <span data-ttu-id="283bd-157">代理程式允許具有本機匯總的效能計數器的可設定高率輪詢。</span><span class="sxs-lookup"><span data-stu-id="283bd-157">The Agent allows configurable high rate polling of performance counters with local aggregation.</span></span>

- <span data-ttu-id="283bd-158">**聽眾。**</span><span class="sxs-lookup"><span data-stu-id="283bd-158">**Listener.**</span></span> <span data-ttu-id="283bd-159">伺服器端 API，會從所有代理程式接收資料，並在人口中匯總資料。</span><span class="sxs-lookup"><span data-stu-id="283bd-159">The server side API that receives data from all Agents, and aggregates data across populations.</span></span>

- <span data-ttu-id="283bd-160">**樞紐。**</span><span class="sxs-lookup"><span data-stu-id="283bd-160">**Hub.**</span></span> <span data-ttu-id="283bd-161">會做為系統的用戶端 API，在網頁伺服器上執行 (s) ，並為透過網站所連接的用戶端提供即時資料更新。</span><span class="sxs-lookup"><span data-stu-id="283bd-161">Serves as the client API for the system, runs on the web server(s), and provides real-time data updates to clients connected via the website.</span></span> <span data-ttu-id="283bd-162"> (會在網站 msi 中自動安裝 Hub。 ) </span><span class="sxs-lookup"><span data-stu-id="283bd-162">(The Hub is automatically installed as part of the Website msi.)</span></span>

- <span data-ttu-id="283bd-163">**網站。**</span><span class="sxs-lookup"><span data-stu-id="283bd-163">**Website.**</span></span> <span data-ttu-id="283bd-164">一種使用者介面，可將系統中所有可用的功能集中在一起。</span><span class="sxs-lookup"><span data-stu-id="283bd-164">A user interface that pulls together all the features available in the system.</span></span>

<span data-ttu-id="283bd-165">此外，[統計資料管理員] 也需要 **Redis**，這是一種開放來源的資料結構伺服器，供記憶體快取之用。</span><span class="sxs-lookup"><span data-stu-id="283bd-165">In addition, Statistics Manager requires **Redis**, an open-sourced data structure server for in-memory caching.</span></span> <span data-ttu-id="283bd-166">如需下載 Redis 的詳細資訊，請參閱 [部署統計資料管理員](deploy.md#BKMK_Deploy) 。</span><span class="sxs-lookup"><span data-stu-id="283bd-166">For more information about downloading Redis, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy) .</span></span>

## <a name="on-premises-deployment"></a><span data-ttu-id="283bd-167">內部部署</span><span class="sxs-lookup"><span data-stu-id="283bd-167">On-premises deployment</span></span>
<span data-ttu-id="283bd-168"><a name="BKMK_DeploymentOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="283bd-168"><a name="BKMK_DeploymentOptions"> </a></span></span>

<span data-ttu-id="283bd-169">在內部部署中，單一伺服器會裝載所有伺服器端統計資料管理員元件。</span><span class="sxs-lookup"><span data-stu-id="283bd-169">In an on-premises deployment, a single server hosts all of the server-side Statistics Manager components.</span></span>

<span data-ttu-id="283bd-170">下圖顯示內部部署，其中的統計資料管理員網站、Hub、接聽程式和 Redis 快取系統會主控于單一機器上。</span><span class="sxs-lookup"><span data-stu-id="283bd-170">The following diagram shows an on-premises deployment, in which the Statistics Manager Website, Hub, Listener, and Redis caching system are hosted on a single machine.</span></span> <span data-ttu-id="283bd-171">統計資料管理員監控三個商務用 Skype 伺服器，每個伺服器都有一個代理程式將資料傳送至監聽器。</span><span class="sxs-lookup"><span data-stu-id="283bd-171">Statistics Manager is monitoring three Skype for Business servers, each of which have a single Agent transmitting data to the Listener.</span></span> <span data-ttu-id="283bd-172">使用者連線到單一網站，以查看統計資料管理員匯總的所有資料：</span><span class="sxs-lookup"><span data-stu-id="283bd-172">Users connect to a single Website to view all data aggregated by Statistics Manager:</span></span>

![內部部署的統計管理員](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a><span data-ttu-id="283bd-174">需求</span><span class="sxs-lookup"><span data-stu-id="283bd-174">Requirements</span></span>
<span data-ttu-id="283bd-175"><a name="BKMK_Requirements"> </a></span><span class="sxs-lookup"><span data-stu-id="283bd-175"><a name="BKMK_Requirements"> </a></span></span>

<span data-ttu-id="283bd-176">在您部署統計資料管理員之前，您必須考慮下列軟體、網路及硬體需求。</span><span class="sxs-lookup"><span data-stu-id="283bd-176">You will need to consider the following software, networking, and hardware requirements before you deploy Statistics Manager.</span></span>

### <a name="software-requirements"></a><span data-ttu-id="283bd-177">軟體需求</span><span class="sxs-lookup"><span data-stu-id="283bd-177">Software requirements</span></span>

- <span data-ttu-id="283bd-178">Windows Server 2016 和2019</span><span class="sxs-lookup"><span data-stu-id="283bd-178">Windows Server 2016 and 2019</span></span>

- <span data-ttu-id="283bd-179">IIS (會自動安裝) </span><span class="sxs-lookup"><span data-stu-id="283bd-179">IIS (automatically installed)</span></span>

- <span data-ttu-id="283bd-180">Redis</span><span class="sxs-lookup"><span data-stu-id="283bd-180">Redis</span></span>

- <span data-ttu-id="283bd-181">統計資料管理員服務 (會自動安裝) </span><span class="sxs-lookup"><span data-stu-id="283bd-181">Statistics Manager services (automatically installed)</span></span>

- <span data-ttu-id="283bd-182">PSExec-需要進行遠端代理程式部署</span><span class="sxs-lookup"><span data-stu-id="283bd-182">PSExec - Required to do remote agent deployment</span></span>

- <span data-ttu-id="283bd-183">.NET 4.5 (隨附于 2012 R2) -代理程式和伺服器端元件所需的元件</span><span class="sxs-lookup"><span data-stu-id="283bd-183">.NET 4.5 (included with 2012 R2) - Required for agents and server-side components</span></span>
- <span data-ttu-id="283bd-184">下載 [商務用 Skype 伺服器、Real-Time 統計資料管理員 (64 位) ](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span><span class="sxs-lookup"><span data-stu-id="283bd-184">Download the [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="283bd-185">網路需求</span><span class="sxs-lookup"><span data-stu-id="283bd-185">Networking requirements</span></span>


|<span data-ttu-id="283bd-186">**主控伺服器**</span><span class="sxs-lookup"><span data-stu-id="283bd-186">**Hosting server**</span></span>|<span data-ttu-id="283bd-187">**Agents**</span><span class="sxs-lookup"><span data-stu-id="283bd-187">**Agents**</span></span>|<span data-ttu-id="283bd-188">**聽眾**</span><span class="sxs-lookup"><span data-stu-id="283bd-188">**Listener**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="283bd-189">最小十億位元全雙工網路。</span><span class="sxs-lookup"><span data-stu-id="283bd-189">Minimum gigabit full duplex networking.</span></span>  <br/> |<span data-ttu-id="283bd-190">輸出 TCP 埠 8443 (可自訂的埠號碼) 與監聽器通訊。</span><span class="sxs-lookup"><span data-stu-id="283bd-190">Outbound TCP port 8443 (customizable port number) to communicate with the Listener.</span></span>  <br/> |<span data-ttu-id="283bd-191">監聽器埠在所有伺服器上都必須相同。</span><span class="sxs-lookup"><span data-stu-id="283bd-191">The Listener port must be the same on all servers.</span></span>  <br/> |
|<span data-ttu-id="283bd-192">輸入 TCP 埠80或443開啟以主控網站。</span><span class="sxs-lookup"><span data-stu-id="283bd-192">Inbound TCP port 80 or 443 open to host the website.</span></span>  <br/> |||
|<span data-ttu-id="283bd-193">輸入 TCP 埠 8443 (可自訂的埠號碼) 供代理程式與其通訊。</span><span class="sxs-lookup"><span data-stu-id="283bd-193">Inbound TCP port 8443 (customizable port number) for the agents to communicate with it.</span></span>  <br/> |||

<span data-ttu-id="283bd-194">在安裝期間，會自動建立監聽器和網站的防火牆埠。</span><span class="sxs-lookup"><span data-stu-id="283bd-194">During installation, firewall ports for the Listener and the Website are automatically created.</span></span> <span data-ttu-id="283bd-195">針對代理程式，安裝會假設預設允許輸出 TCP 連線。</span><span class="sxs-lookup"><span data-stu-id="283bd-195">For the Agents, the installation assumes that outbound TCP connections are allowed by default.</span></span>

### <a name="hardware-requirements"></a><span data-ttu-id="283bd-196">硬體需求</span><span class="sxs-lookup"><span data-stu-id="283bd-196">Hardware requirements</span></span>

<span data-ttu-id="283bd-197">在內部部署中，一部伺服器主控所有伺服器端統計資料管理員元件的伺服器，平均有 16 GB RAM 和 4 CPU 的伺服器應該能夠每秒支援大約150的範例。</span><span class="sxs-lookup"><span data-stu-id="283bd-197">In an on-premises deployment, in which a single server hosts all of the server-side Statistics Manager components, a server with 16 GB of RAM and 4 CPU's should be able to support about 150 samples per second on average.</span></span> <span data-ttu-id="283bd-198">若要判斷您可以支援多少計數器/代理程式，請使用下列計算：</span><span class="sxs-lookup"><span data-stu-id="283bd-198">To determine how many counters/agents you can support, use the following calculation:</span></span>

<span data-ttu-id="283bd-199">100 server \* 80 計數器 \* 1 每分鐘從每個代理程式/60 秒 = 每秒大約133樣本。</span><span class="sxs-lookup"><span data-stu-id="283bd-199">100 servers \*80 counters \* 1 sample per minute from each agent / 60 seconds = ~ 133 samples per second.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="283bd-200">安全考量</span><span class="sxs-lookup"><span data-stu-id="283bd-200">Security considerations</span></span>
<span data-ttu-id="283bd-201"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="283bd-201"><a name="BKMK_Security"> </a></span></span>

<span data-ttu-id="283bd-202">伺服器間的所有流量都會加密。</span><span class="sxs-lookup"><span data-stu-id="283bd-202">All traffic between servers is encrypted.</span></span>

- <span data-ttu-id="283bd-203">加密 HTTPS 流量) 預設會透過埠 8443 (傳送，而不是從 Agent 傳送至監聽器伺服器。</span><span class="sxs-lookup"><span data-stu-id="283bd-203">Encrypted HTTPS traffic will be sent over port 8443 (by default) from the Agent to the Listener server.</span></span>

- <span data-ttu-id="283bd-204">代理程式會驗證服務器上的 SSL 指紋，以確保監聽器伺服器是預期的收件者。</span><span class="sxs-lookup"><span data-stu-id="283bd-204">The Agent will verify the SSL thumbprint on the server to ensure the Listener server is the expected recipient.</span></span> <span data-ttu-id="283bd-205">請注意，代理程式會使用憑證指紋驗證 (，而不是鏈式驗證) 。</span><span class="sxs-lookup"><span data-stu-id="283bd-205">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="283bd-206">因為可能會使用自我簽署的憑證，所以不會執行完整的憑證驗證。</span><span class="sxs-lookup"><span data-stu-id="283bd-206">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>

- <span data-ttu-id="283bd-207">當代理程式滿意後，該監聽器便會透過監聽器所驗證的方式來顯示密碼。</span><span class="sxs-lookup"><span data-stu-id="283bd-207">After the Agent is satisfied the Listener is authentic, a password will be presented by the Agent which is then verified by the Listener.</span></span>

- <span data-ttu-id="283bd-208">代理程式會在連接到監聽器時，開始傳輸效能資料。</span><span class="sxs-lookup"><span data-stu-id="283bd-208">The Agent begins transmitting performance data over the connection to the Listener.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="283bd-209">相關資訊</span><span class="sxs-lookup"><span data-stu-id="283bd-209">For more information</span></span>
<span data-ttu-id="283bd-210"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="283bd-210"><a name="BKMK_Security"> </a></span></span>

<span data-ttu-id="283bd-211">如需詳細資訊，請參閱下列各主題：</span><span class="sxs-lookup"><span data-stu-id="283bd-211">For more information, see the following:</span></span>

- [<span data-ttu-id="283bd-212">部署商務用 Skype Server 統計資料</span><span class="sxs-lookup"><span data-stu-id="283bd-212">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)

- [<span data-ttu-id="283bd-213">升級商務用 Skype Server 統計資料</span><span class="sxs-lookup"><span data-stu-id="283bd-213">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)

- [<span data-ttu-id="283bd-214">疑難排解商務用 Skype Server 統計資料</span><span class="sxs-lookup"><span data-stu-id="283bd-214">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
