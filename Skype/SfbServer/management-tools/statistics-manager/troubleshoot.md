---
title: 疑難排解商務用 Skype Server 的統計管理員
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: '摘要: 請閱讀本主題, 以針對商務用 Skype Server 的統計管理員部署進行疑難排解。'
ms.openlocfilehash: b85ee6593413cce0aa5b7c76901dbbc6099107fd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193141"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="2e808-103">疑難排解商務用 Skype Server 的統計管理員</span><span class="sxs-lookup"><span data-stu-id="2e808-103">Troubleshoot Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="2e808-104">**摘要:** 閱讀本主題以針對商務用 Skype Server 的統計管理員部署進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="2e808-104">**Summary:** Read this topic to troubleshoot your deployment of Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="2e808-105">本主題描述如何透過描述您在應用程式事件日誌中看到的事件, 以及您可以採取以修正事件的適當動作來疑難排解統計資料管理員部署。</span><span class="sxs-lookup"><span data-stu-id="2e808-105">This topic describes how to troubleshoot your Statistics Manager deployment by describing events you might see in the application event log, and appropriate actions you might take to rectify the event.</span></span> <span data-ttu-id="2e808-106">本主題包含下列各節:</span><span class="sxs-lookup"><span data-stu-id="2e808-106">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="2e808-107">代理程式事件</span><span class="sxs-lookup"><span data-stu-id="2e808-107">Agent events</span></span>](troubleshoot.md#BKMK_Agent)
    
- [<span data-ttu-id="2e808-108">偵聽程式事件</span><span class="sxs-lookup"><span data-stu-id="2e808-108">Listener events</span></span>](troubleshoot.md#BKMK_Listener)
    
- [<span data-ttu-id="2e808-109">網站問題</span><span class="sxs-lookup"><span data-stu-id="2e808-109">Website issues</span></span>](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a><span data-ttu-id="2e808-110">代理程式事件</span><span class="sxs-lookup"><span data-stu-id="2e808-110">Agent events</span></span>
<span data-ttu-id="2e808-111"><a name="BKMK_Agent"> </a></span><span class="sxs-lookup"><span data-stu-id="2e808-111"></span></span>

- <span data-ttu-id="2e808-112">**1000** -無法設定處理器 Limiter (工作物件)-未知原因</span><span class="sxs-lookup"><span data-stu-id="2e808-112">**1000** — Unable to setup processor limiter (Job Object) — Unknown reason</span></span>
    
- <span data-ttu-id="2e808-113">**1001** -進程不允許程式限制 (可能是工作物件內)</span><span class="sxs-lookup"><span data-stu-id="2e808-113">**1001** — Process limiting isn't allowed on the process (probably already inside a Job Object)</span></span>
    
    <span data-ttu-id="2e808-114">Agent 會在 Windows 工作物件內執行, 以自動限制其記憶體需求量。</span><span class="sxs-lookup"><span data-stu-id="2e808-114">The Agent runs inside of a Windows Job Object to automatically limit its memory footprint.</span></span> <span data-ttu-id="2e808-115">如果代理程式無法啟動, 且事件記錄中存在這些事件專案, 則無法在伺服器上將工作物件具現化。</span><span class="sxs-lookup"><span data-stu-id="2e808-115">If the agent will not start and these event entries are present in the event log, the Job Object is not able to be instantiated on the server.</span></span> <span data-ttu-id="2e808-116">若要解決此問題, 您可以變更 config 檔案中的值來移除上限記憶體限制:</span><span class="sxs-lookup"><span data-stu-id="2e808-116">To work around this, the upper memory limit can be removed by changing a value in the config file:</span></span>
    
  ```
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    <span data-ttu-id="2e808-117">搜尋 "MaxProcessMemoryMB", 然後將值變更為 "0", 如下所示:</span><span class="sxs-lookup"><span data-stu-id="2e808-117">Search for "MaxProcessMemoryMB" and change the value to "0" as shown:</span></span>
    
  ```
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > <span data-ttu-id="2e808-118">如果進行這項變更, 則代理程式通常仍會\<佔用 100 MB 的記憶體, 但在預設情況下, 它不會被強制限制為 300 mb。</span><span class="sxs-lookup"><span data-stu-id="2e808-118">If this change is made, the Agent will generally still consume \< 100 MB of memory, however it will not be forcefully limited to 300 MB as is the default.</span></span> <span data-ttu-id="2e808-119">如果進行這項變更, 我們建議您密切監視記憶體使用量, 以確保代理程式不會在其主機電腦上佔用大量記憶體。</span><span class="sxs-lookup"><span data-stu-id="2e808-119">If this change is made, we recommend closely monitoring memory usage to ensure the Agent does not consume a large amount of memory on its host machine.</span></span> 
  
- <span data-ttu-id="2e808-120">**2000** -用戶端初始化失敗</span><span class="sxs-lookup"><span data-stu-id="2e808-120">**2000** — Client initialization failure</span></span>
    
- <span data-ttu-id="2e808-121">**2001**-在任何來源 IP 上無法與服務建立連線</span><span class="sxs-lookup"><span data-stu-id="2e808-121">**2001**— No connection could be made to the service on any source IP</span></span>
    
    <span data-ttu-id="2e808-122">如果代理程式無法連線至監聽器電腦, 請檢查下列專案:</span><span class="sxs-lookup"><span data-stu-id="2e808-122">If the Agent cannot connect to the Listener computer, check the following:</span></span>
    
1. <span data-ttu-id="2e808-123">確定偵聽程式服務正在監聽程式電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="2e808-123">Ensure the Listener service is running on the Listener computer.</span></span> <span data-ttu-id="2e808-124">如果不是, 請確定 Redis 正在該伺服器上執行, 然後重新開機監聽器服務。</span><span class="sxs-lookup"><span data-stu-id="2e808-124">If not, ensure Redis is running on that server and then restart the Listener service.</span></span>
    
    <span data-ttu-id="2e808-125">檢查偵聽程式電腦上的統計資料管理員事件記錄, 以確保統計資料管理員攔截器服務本身沒有任何問題。</span><span class="sxs-lookup"><span data-stu-id="2e808-125">Check the Statistics Manager event log on the Listener computer to ensure there are no issues with the Statistics Manager Listener service itself.</span></span>
    
2. <span data-ttu-id="2e808-126">使用連接工具 (例如 telnet) 來驗證從代理程式電腦到正確埠上的監聽器的連線性。</span><span class="sxs-lookup"><span data-stu-id="2e808-126">Use a connectivity tool such as telnet to verify connectivity from the Agent computer to the Listener on the correct port.</span></span>
    
    <span data-ttu-id="2e808-127">如果不是, 請確定已針對監聽器電腦所連接的網路類型 (私人/公用/網域), 在監聽器電腦上啟用 [接收] 防火牆規則。</span><span class="sxs-lookup"><span data-stu-id="2e808-127">If not, make sure the incoming firewall rule is enabled on the Listener computer for the network type that the Listener computer is connected to (private/public/domain).</span></span> <span data-ttu-id="2e808-128">如果監聽器電腦沒有加入網域, 網路可能會列為公用, 而且在該情況下, 安裝了 [統計資料管理器] 的防火牆規則預設不會套用。</span><span class="sxs-lookup"><span data-stu-id="2e808-128">If the Listener computer is not joined to a domain, the network may be listed as public and in that case the firewall rules installed with Statistics Manager will not apply by default.</span></span>
    
- <span data-ttu-id="2e808-129">**4000** -從偵聽程式下載伺服器資訊失敗 (不明原因)</span><span class="sxs-lookup"><span data-stu-id="2e808-129">**4000** — Failure to download Server Info from Listener (unknown reason)</span></span>
    
  - <span data-ttu-id="2e808-130">**4001** -在偵聽程式拓撲中找不到伺服器</span><span class="sxs-lookup"><span data-stu-id="2e808-130">**4001** — Server Not Found in Listener Topology</span></span>
    
    <span data-ttu-id="2e808-131">如果伺服器已成功連線到偵聽程式, 但未將伺服器新增到攔截器快取的拓撲中, 就會發生此錯誤。</span><span class="sxs-lookup"><span data-stu-id="2e808-131">This error will occur if the server is successfully connecting to the Listener, but the server was not added to the topology in the Listener's cache.</span></span> <span data-ttu-id="2e808-132">解析度選項:</span><span class="sxs-lookup"><span data-stu-id="2e808-132">Resolution options:</span></span>
    
  - <span data-ttu-id="2e808-133">請確定您已按照匯入拓撲的指示進行。</span><span class="sxs-lookup"><span data-stu-id="2e808-133">Make sure you followed the instructions for importing the topology.</span></span> <span data-ttu-id="2e808-134">請參閱匯[入拓撲](deploy.md#BKMK_ImportTopology)。</span><span class="sxs-lookup"><span data-stu-id="2e808-134">See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span> 
    
  - <span data-ttu-id="2e808-135">如果該代理位於拓撲中未列出的伺服器上 (例如, SQL AlwaysOn 群集中的節點), 您將需要按照匯[入拓撲](deploy.md#BKMK_ImportTopology)中的指示手動新增該代理程式。</span><span class="sxs-lookup"><span data-stu-id="2e808-135">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="2e808-136">**4002** -不正確監聽器密碼</span><span class="sxs-lookup"><span data-stu-id="2e808-136">**4002** — Invalid Listener Password</span></span>
    
    <span data-ttu-id="2e808-137">代理程式嘗試使用的加密密碼與監聽器本身的服務密碼不相符。</span><span class="sxs-lookup"><span data-stu-id="2e808-137">The encrypted password that the agent is attempting to use does not match the service password on the Listener itself.</span></span> <span data-ttu-id="2e808-138">卸載該代理程式, 然後使用正確的服務密碼重新安裝。</span><span class="sxs-lookup"><span data-stu-id="2e808-138">Uninstall the Agent and re-install it using the correct service password.</span></span>
    
  - <span data-ttu-id="2e808-139">**4003** -憑證指紋不相符</span><span class="sxs-lookup"><span data-stu-id="2e808-139">**4003** — Certificate Thumbprint Mismatch</span></span>
    
    <span data-ttu-id="2e808-140">在安裝時間提供給 Agent 的憑證指紋與監聽器目前使用的憑證上的指紋不相符, 因此連線將遭到拒絕。</span><span class="sxs-lookup"><span data-stu-id="2e808-140">The certificate thumbprint given to the Agent at install time does not match the thumbprint on the certificate the Listener is currently using and therefore the connection will be refused.</span></span> <span data-ttu-id="2e808-141">卸載該代理程式, 然後使用正確的憑證指紋重新安裝。</span><span class="sxs-lookup"><span data-stu-id="2e808-141">Uninstall the Agent and re-install it using the correct certificate thumbprint.</span></span>
    
  - <span data-ttu-id="2e808-142">**4004** -不正確回應或 HttpStatusCode</span><span class="sxs-lookup"><span data-stu-id="2e808-142">**4004** — Invalid Response or HttpStatusCode</span></span>
    
    <span data-ttu-id="2e808-143">監聽器沒有回應預期的狀態。</span><span class="sxs-lookup"><span data-stu-id="2e808-143">The Listener is not responding with an expected status.</span></span> 
    
  - <span data-ttu-id="2e808-144">如果連線是已設定代理的, 請檢查 proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="2e808-144">If the connection is proxied, check the proxy configuration.</span></span>
    
  - <span data-ttu-id="2e808-145">檢查監聽器電腦的 StatsMan 記錄是否有其設定的問題。</span><span class="sxs-lookup"><span data-stu-id="2e808-145">Check the Listener computer's StatsMan log for issues with its configuration.</span></span>
    
  - <span data-ttu-id="2e808-146">**4005** -無法反序列化 XML</span><span class="sxs-lookup"><span data-stu-id="2e808-146">**4005** — Couldn't de-serialize the XML</span></span>
    
    <span data-ttu-id="2e808-147">監聽器伺服器上的伺服器資訊已損壞, 或是代理程式與監聽器電腦之間可能有版本不相符的問題。</span><span class="sxs-lookup"><span data-stu-id="2e808-147">The server info on the Listener server is corrupt or there may be a version mismatch between the Agent and the Listener computers.</span></span> <span data-ttu-id="2e808-148">請確定版本相符, 然後檢查監聽器事件記錄檔是否有問題。</span><span class="sxs-lookup"><span data-stu-id="2e808-148">Ensure the versions match and check the Listener event log for issues.</span></span>
    
## <a name="listener-events"></a><span data-ttu-id="2e808-149">偵聽程式事件</span><span class="sxs-lookup"><span data-stu-id="2e808-149">Listener events</span></span>
<span data-ttu-id="2e808-150"><a name="BKMK_Listener"> </a></span><span class="sxs-lookup"><span data-stu-id="2e808-150"></span></span>

- <span data-ttu-id="2e808-151">**10000** -啟動失敗不明原因 (這些無法還原, 且服務會因結果而停止/損毀)</span><span class="sxs-lookup"><span data-stu-id="2e808-151">**10000** — Startup failure Unknown reason (these are unrecoverable and the service will stop/crash as a result)</span></span>
    
  - <span data-ttu-id="2e808-152">**10001** -配置問題</span><span class="sxs-lookup"><span data-stu-id="2e808-152">**10001** — Configuration problem</span></span>
    
    <span data-ttu-id="2e808-153">一般來說, 當 [listener_install_location] \PerfAgentListener.exe.config 檔案已手動修改且無法由應用程式讀取時, 就會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="2e808-153">Generally this will occur when the [listener_install_location]\PerfAgentListener.exe.config file has been modified by hand and cannot be read by the application.</span></span>
    
  - <span data-ttu-id="2e808-154">**10002** -HTTP 偵聽程式初始化錯誤</span><span class="sxs-lookup"><span data-stu-id="2e808-154">**10002** — HTTP Listener initialization error</span></span>
    
    <span data-ttu-id="2e808-155">當在安裝期間未正確設定 URL ACL 或 SSL 憑證無效時, 通常會記錄這個事件。</span><span class="sxs-lookup"><span data-stu-id="2e808-155">This event will generally be logged when the URL ACL has not been set properly during installation or the SSL Cert is invalid.</span></span> <span data-ttu-id="2e808-156">確定您的設定中的憑證有效。</span><span class="sxs-lookup"><span data-stu-id="2e808-156">Ensure the certificate in your configuration is valid.</span></span> <span data-ttu-id="2e808-157">如果是, 請根據 [[部署統計資料管理器](deploy.md#BKMK_Deploy)] 中的指示來重新安裝該偵聽程式。</span><span class="sxs-lookup"><span data-stu-id="2e808-157">If it is, reinstall the Listener according to the instructions in [Deploy Statistics Manager](deploy.md#BKMK_Deploy).</span></span>
    
  - <span data-ttu-id="2e808-158">**10003** -Redis 失敗</span><span class="sxs-lookup"><span data-stu-id="2e808-158">**10003** — Redis failure</span></span>
    
  - <span data-ttu-id="2e808-159">**10004** -緩存基礎結構失敗</span><span class="sxs-lookup"><span data-stu-id="2e808-159">**10004** — Caching infrastructure failure</span></span>
    
  - <span data-ttu-id="2e808-160">**10007** -設定 (儲存在 redis 中)</span><span class="sxs-lookup"><span data-stu-id="2e808-160">**10007** — Settings (stored in redis)</span></span>
    
    <span data-ttu-id="2e808-161">監聽器無法與 Redis 聯繫, 或從快取中取得格式正確的資料, 但無法啟動。</span><span class="sxs-lookup"><span data-stu-id="2e808-161">The Listener could not contact Redis or retrieve well-formed data from the cache and could not start.</span></span> <span data-ttu-id="2e808-162">確認已在伺服器上啟動並正確設定 Redis 服務。</span><span class="sxs-lookup"><span data-stu-id="2e808-162">Ensure the Redis service is started and configured properly on the server.</span></span>
    
  - <span data-ttu-id="2e808-163">**10005** -伺服器資訊檢索/分析</span><span class="sxs-lookup"><span data-stu-id="2e808-163">**10005** — Server info retrieval/parsing</span></span>
    
    <span data-ttu-id="2e808-164">Redis 快取中的拓撲資訊無效。</span><span class="sxs-lookup"><span data-stu-id="2e808-164">The topology information in the Redis cache is invalid.</span></span> <span data-ttu-id="2e808-165">首先, 請嘗試重新開機 Redis 和偵聽程式。</span><span class="sxs-lookup"><span data-stu-id="2e808-165">First, attempt to restart Redis and the Listener.</span></span> <span data-ttu-id="2e808-166">如果錯誤持續出現, 請參閱匯[入拓撲](deploy.md#BKMK_ImportTopology), 以重新建立拓撲資料。</span><span class="sxs-lookup"><span data-stu-id="2e808-166">If the error persists, see [Import the topology](deploy.md#BKMK_ImportTopology) to recreate the topology data.</span></span>
    
- <span data-ttu-id="2e808-167">**10100** -Redis PING 中斷</span><span class="sxs-lookup"><span data-stu-id="2e808-167">**10100** — Redis PING outage</span></span>
    
  - <span data-ttu-id="2e808-168">**10101** -Redis PING 連續停機 (每60秒)</span><span class="sxs-lookup"><span data-stu-id="2e808-168">**10101** — Redis PING continued outage (every 60 seconds)</span></span>
    
  - <span data-ttu-id="2e808-169">**30100** -已還原 Redis PING 中斷</span><span class="sxs-lookup"><span data-stu-id="2e808-169">**30100** — Redis PING outage restored</span></span>
    
    <span data-ttu-id="2e808-170">當監聽器無法連線至 Redis 時, 就會記錄這些訊息。</span><span class="sxs-lookup"><span data-stu-id="2e808-170">These will be logged when the Listener cannot connect to Redis.</span></span> <span data-ttu-id="2e808-171">確保 Redis 已啟動, 且可以使用偵聽程式與 Redis 之間的網路連線。</span><span class="sxs-lookup"><span data-stu-id="2e808-171">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="2e808-172">**10200** -Redis 寫入中斷</span><span class="sxs-lookup"><span data-stu-id="2e808-172">**10200** — Redis Write outage</span></span>
    
  - <span data-ttu-id="2e808-173">**10201** -繼續 Redis 寫入停止 (每隔60秒)</span><span class="sxs-lookup"><span data-stu-id="2e808-173">**10201** — Redis Write outage continued (every 60 seconds)</span></span>
    
  - <span data-ttu-id="2e808-174">**30100** -已解決 Redis 寫入中斷問題</span><span class="sxs-lookup"><span data-stu-id="2e808-174">**30100** — Redis Write outage resolved</span></span>
    
    <span data-ttu-id="2e808-175">當監聽器無法寫入 Redis 快取時, 就會記錄這些訊息。</span><span class="sxs-lookup"><span data-stu-id="2e808-175">These will be logged when the Listener cannot write to the Redis cache.</span></span> <span data-ttu-id="2e808-176">確保 Redis 已啟動, 且可以使用偵聽程式與 Redis 之間的網路連線。</span><span class="sxs-lookup"><span data-stu-id="2e808-176">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="2e808-177">**30000** -成功啟動</span><span class="sxs-lookup"><span data-stu-id="2e808-177">**30000** — Successfully started</span></span>
    
    <span data-ttu-id="2e808-178">在每次啟動監聽器時記錄。</span><span class="sxs-lookup"><span data-stu-id="2e808-178">Logged each time the Listener is started.</span></span>
    
- <span data-ttu-id="2e808-179">**22000** -統計資料管理器代理程式的初始化成功。</span><span class="sxs-lookup"><span data-stu-id="2e808-179">**22000** — Initialization of Statistics Manager Agent succeeded.</span></span>
    
- <span data-ttu-id="2e808-180">**23000** -初始化 EventLogQueryManager 成功 (第一次或失敗之後)</span><span class="sxs-lookup"><span data-stu-id="2e808-180">**23000** — Initialization of EventLogQueryManager succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="2e808-181">**24000** -初始化 serverinfo 成功 (第一次或失敗之後)</span><span class="sxs-lookup"><span data-stu-id="2e808-181">**24000** — Initialization of serverinfo succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="2e808-182">**25000** -監聽器在無法開機自檢 (或第一次成功張貼) 後回到線上</span><span class="sxs-lookup"><span data-stu-id="2e808-182">**25000** — Listener is back online after failing to post (or first successful post)</span></span>
    
- <span data-ttu-id="2e808-183">**5000** -在離線時啟動監聽器以進行資料張貼</span><span class="sxs-lookup"><span data-stu-id="2e808-183">**5000** — Start of listener offline for posting data</span></span>
    
- <span data-ttu-id="2e808-184">**5001** -監聽器在延長期間內仍處於離線狀態</span><span class="sxs-lookup"><span data-stu-id="2e808-184">**5001** — Listener is still offline for an extended period</span></span>
    
    <span data-ttu-id="2e808-185">這些事件對於監視/觸發/清除問題可能很有用。</span><span class="sxs-lookup"><span data-stu-id="2e808-185">These events can be useful for monitoring/alerting/clearing issues.</span></span>
    
## <a name="website-issues"></a><span data-ttu-id="2e808-186">網站問題</span><span class="sxs-lookup"><span data-stu-id="2e808-186">Website issues</span></span>
<span data-ttu-id="2e808-187"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="2e808-187"></span></span>

- <span data-ttu-id="2e808-188">Chrome 中重複的登入提示-這是已在版本1.1 中解決的錯誤。</span><span class="sxs-lookup"><span data-stu-id="2e808-188">Repetitive login prompts in Chrome - this was a bug that has been resolved in version 1.1.</span></span> <span data-ttu-id="2e808-189">如果您在 Chrome 瀏覽器中看到重複的登入提示, 請確定您已升級至最新版本的統計資料管理員。</span><span class="sxs-lookup"><span data-stu-id="2e808-189">Be sure you have upgraded to the latest version of Statistics Manager if you are seeing repeated login prompts in the Chrome browser.</span></span> <span data-ttu-id="2e808-190">若要確認您正在執行的網站版本:</span><span class="sxs-lookup"><span data-stu-id="2e808-190">To verify the version of the website you are running:</span></span>
    
  - <span data-ttu-id="2e808-191">在檔案資源管理器中開啟 (預設目錄)</span><span class="sxs-lookup"><span data-stu-id="2e808-191">In File Explorer, open (default directory)</span></span>
    
  - <span data-ttu-id="2e808-192">以滑鼠右鍵按一下 [StatsManHubWebSite], 並查看其屬性。</span><span class="sxs-lookup"><span data-stu-id="2e808-192">Right click on StatsManHubWebSite.dll and view its properties.</span></span>
    
  - <span data-ttu-id="2e808-193">如果在 KHI 橫向視圖或 [計數器詳細資料] 視圖中找不到電腦, 請確定它是網站和池的成員。</span><span class="sxs-lookup"><span data-stu-id="2e808-193">If a computer cannot be found in the KHI Landscape view or the Counter Details view, make sure it is a member of a Site and a Pool.</span></span> <span data-ttu-id="2e808-194">如果不是, 就不會出現在這些視圖中。</span><span class="sxs-lookup"><span data-stu-id="2e808-194">If it is not, it will not appear in those views.</span></span> <span data-ttu-id="2e808-195">如需在拓撲中定義伺服器的網站和池的相關資訊, 請參閱匯[入拓撲](deploy.md#BKMK_ImportTopology)。</span><span class="sxs-lookup"><span data-stu-id="2e808-195">For information about defining a site and pool for a server in the topology, see [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="2e808-196">產品版本將會顯示在描述詳細資料中。</span><span class="sxs-lookup"><span data-stu-id="2e808-196">The product version will be shown in the Description details.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="2e808-197">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="2e808-197">For more information</span></span>
<span data-ttu-id="2e808-198"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="2e808-198"></span></span>

<span data-ttu-id="2e808-199">如需詳細資訊, 請參閱下列內容:</span><span class="sxs-lookup"><span data-stu-id="2e808-199">For more information, see the following:</span></span>
  
- [<span data-ttu-id="2e808-200">規劃商務用 Skype Server 的統計資料管理員</span><span class="sxs-lookup"><span data-stu-id="2e808-200">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="2e808-201">部署商務用 Skype Server 的統計資料管理器</span><span class="sxs-lookup"><span data-stu-id="2e808-201">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="2e808-202">商務用 Skype Server 的升級統計資料管理員</span><span class="sxs-lookup"><span data-stu-id="2e808-202">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
