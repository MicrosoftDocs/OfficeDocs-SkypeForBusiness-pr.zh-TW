---
title: 疑難排解商務用 Skype Server 統計資料
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
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 摘要：閱讀此主題以針對商務用 Skype 伺服器的統計資料管理員部署進行疑難排解。
ms.openlocfilehash: ea3d6f66003841e893ebe2dcc5d3fe02d0da125b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821773"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="ca328-103">疑難排解商務用 Skype Server 統計資料</span><span class="sxs-lookup"><span data-stu-id="ca328-103">Troubleshoot Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="ca328-104">**摘要：** 閱讀此主題以針對商務用 Skype 伺服器的統計資料管理員部署進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="ca328-104">**Summary:** Read this topic to troubleshoot your deployment of Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="ca328-105">本主題說明如何透過描述您在應用程式事件記錄檔中看到的事件來疑難排解您的統計資料管理員部署，以及您可能採取的適當動作以修正事件。</span><span class="sxs-lookup"><span data-stu-id="ca328-105">This topic describes how to troubleshoot your Statistics Manager deployment by describing events you might see in the application event log, and appropriate actions you might take to rectify the event.</span></span> <span data-ttu-id="ca328-106">本主題包含下列各節：</span><span class="sxs-lookup"><span data-stu-id="ca328-106">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="ca328-107">代理程式事件</span><span class="sxs-lookup"><span data-stu-id="ca328-107">Agent events</span></span>](troubleshoot.md#BKMK_Agent)
    
- [<span data-ttu-id="ca328-108">攔截器事件</span><span class="sxs-lookup"><span data-stu-id="ca328-108">Listener events</span></span>](troubleshoot.md#BKMK_Listener)
    
- [<span data-ttu-id="ca328-109">網站問題</span><span class="sxs-lookup"><span data-stu-id="ca328-109">Website issues</span></span>](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a><span data-ttu-id="ca328-110">代理程式事件</span><span class="sxs-lookup"><span data-stu-id="ca328-110">Agent events</span></span>
<span data-ttu-id="ca328-111"><a name="BKMK_Agent"> </a></span><span class="sxs-lookup"><span data-stu-id="ca328-111"><a name="BKMK_Agent"> </a></span></span>

- <span data-ttu-id="ca328-112">**1000** -無法安裝處理器 Limiter (工作物件) -未知原因</span><span class="sxs-lookup"><span data-stu-id="ca328-112">**1000** — Unable to setup processor limiter (Job Object) — Unknown reason</span></span>
    
- <span data-ttu-id="ca328-113">**1001** -不允許程式 (可能在工作物件中的處理常式限制) </span><span class="sxs-lookup"><span data-stu-id="ca328-113">**1001** — Process limiting isn't allowed on the process (probably already inside a Job Object)</span></span>
    
    <span data-ttu-id="ca328-114">代理程式會在 Windows 工作物件內執行，以自動限制記憶體佔用量。</span><span class="sxs-lookup"><span data-stu-id="ca328-114">The Agent runs inside of a Windows Job Object to automatically limit its memory footprint.</span></span> <span data-ttu-id="ca328-115">如果代理程式不會啟動，且事件記錄檔中有這些事件專案，則無法在伺服器上具現化此工作物件。</span><span class="sxs-lookup"><span data-stu-id="ca328-115">If the agent will not start and these event entries are present in the event log, the Job Object is not able to be instantiated on the server.</span></span> <span data-ttu-id="ca328-116">若要解決此問題，您可以變更 config 檔案中的值來移除上限記憶體限制：</span><span class="sxs-lookup"><span data-stu-id="ca328-116">To work around this, the upper memory limit can be removed by changing a value in the config file:</span></span>
    
  ```console
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    <span data-ttu-id="ca328-117">搜尋 "MaxProcessMemoryMB"，並將值變更為 "0"，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ca328-117">Search for "MaxProcessMemoryMB" and change the value to "0" as shown:</span></span>
    
  ```xml
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > <span data-ttu-id="ca328-118">如果進行此變更，則代理程式通常仍會消耗 \< 100 MB 的記憶體，但是不會因為預設，強制限制為 300 mb。</span><span class="sxs-lookup"><span data-stu-id="ca328-118">If this change is made, the Agent will generally still consume \< 100 MB of memory, however it will not be forcefully limited to 300 MB as is the default.</span></span> <span data-ttu-id="ca328-119">如果進行此變更，我們建議您密切監控記憶體使用量，以確保代理程式不會在其主機電腦上消耗大量的記憶體。</span><span class="sxs-lookup"><span data-stu-id="ca328-119">If this change is made, we recommend closely monitoring memory usage to ensure the Agent does not consume a large amount of memory on its host machine.</span></span> 
  
- <span data-ttu-id="ca328-120">**2000** -用戶端初始化失敗</span><span class="sxs-lookup"><span data-stu-id="ca328-120">**2000** — Client initialization failure</span></span>
    
- <span data-ttu-id="ca328-121">**2001**—沒有任何來源 IP 上的服務連接可進行</span><span class="sxs-lookup"><span data-stu-id="ca328-121">**2001**— No connection could be made to the service on any source IP</span></span>
    
    <span data-ttu-id="ca328-122">若代理程式無法連線至監聽器電腦，請檢查下列各項：</span><span class="sxs-lookup"><span data-stu-id="ca328-122">If the Agent cannot connect to the Listener computer, check the following:</span></span>
    
    1. <span data-ttu-id="ca328-123">確定監聽器電腦上的監聽器服務正在執行中。</span><span class="sxs-lookup"><span data-stu-id="ca328-123">Ensure the Listener service is running on the Listener computer.</span></span> <span data-ttu-id="ca328-124">如果不是，請確定 Redis 在該伺服器上執行，然後重新開機監聽器服務。</span><span class="sxs-lookup"><span data-stu-id="ca328-124">If not, ensure Redis is running on that server and then restart the Listener service.</span></span>
        
        <span data-ttu-id="ca328-125">檢查監聽器電腦上的統計資料管理員事件記錄，以確保統計資料管理員偵聽程式服務本身沒有任何問題。</span><span class="sxs-lookup"><span data-stu-id="ca328-125">Check the Statistics Manager event log on the Listener computer to ensure there are no issues with the Statistics Manager Listener service itself.</span></span>
        
    2. <span data-ttu-id="ca328-126">使用連通性工具（例如 telnet），以驗證代理程式電腦與正確埠上的監聽器的連線能力。</span><span class="sxs-lookup"><span data-stu-id="ca328-126">Use a connectivity tool such as telnet to verify connectivity from the Agent computer to the Listener on the correct port.</span></span>
        
        <span data-ttu-id="ca328-127">如果不是，請確定已在監聽器電腦上為監聽器電腦連線的網路類型啟用內送防火牆規則，以 (私/public/網域) 。</span><span class="sxs-lookup"><span data-stu-id="ca328-127">If not, make sure the incoming firewall rule is enabled on the Listener computer for the network type that the Listener computer is connected to (private/public/domain).</span></span> <span data-ttu-id="ca328-128">如果監聽器電腦未加入網域，網路可能會列為 public，而且在此情況下，將不會預設會套用隨統計資料管理員安裝的防火牆規則。</span><span class="sxs-lookup"><span data-stu-id="ca328-128">If the Listener computer is not joined to a domain, the network may be listed as public and in that case the firewall rules installed with Statistics Manager will not apply by default.</span></span>
    
- <span data-ttu-id="ca328-129">**4000** -從監聽器下載伺服器資訊失敗 (未知原因) </span><span class="sxs-lookup"><span data-stu-id="ca328-129">**4000** — Failure to download Server Info from Listener (unknown reason)</span></span>
    
  - <span data-ttu-id="ca328-130">**4001** -在監聽器拓撲中找不到伺服器</span><span class="sxs-lookup"><span data-stu-id="ca328-130">**4001** — Server Not Found in Listener Topology</span></span>
    
    <span data-ttu-id="ca328-131">如果伺服器順利連接至監聽器，但未將伺服器新增至攔截器快取中的拓撲，便會發生此錯誤。</span><span class="sxs-lookup"><span data-stu-id="ca328-131">This error will occur if the server is successfully connecting to the Listener, but the server was not added to the topology in the Listener's cache.</span></span> <span data-ttu-id="ca328-132">解析度選項：</span><span class="sxs-lookup"><span data-stu-id="ca328-132">Resolution options:</span></span>
    
  - <span data-ttu-id="ca328-133">請確認您已遵循匯入拓撲的指示。</span><span class="sxs-lookup"><span data-stu-id="ca328-133">Make sure you followed the instructions for importing the topology.</span></span> <span data-ttu-id="ca328-134">請參閱匯 [入拓撲](deploy.md#BKMK_ImportTopology)。</span><span class="sxs-lookup"><span data-stu-id="ca328-134">See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span> 
    
  - <span data-ttu-id="ca328-135">如果代理程式位於拓撲中未列出的伺服器上 (例如，SQL AlwaysOn 叢集中的節點) ，您必須遵循匯 [入拓撲](deploy.md#BKMK_ImportTopology)中的指示手動新增代理程式。</span><span class="sxs-lookup"><span data-stu-id="ca328-135">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="ca328-136">**4002** -不正確監聽器密碼</span><span class="sxs-lookup"><span data-stu-id="ca328-136">**4002** — Invalid Listener Password</span></span>
    
    <span data-ttu-id="ca328-137">代理程式嘗試使用的加密密碼與監聽器本身的服務密碼不相符。</span><span class="sxs-lookup"><span data-stu-id="ca328-137">The encrypted password that the agent is attempting to use does not match the service password on the Listener itself.</span></span> <span data-ttu-id="ca328-138">卸載代理程式，然後使用正確的服務密碼重新安裝。</span><span class="sxs-lookup"><span data-stu-id="ca328-138">Uninstall the Agent and re-install it using the correct service password.</span></span>
    
  - <span data-ttu-id="ca328-139">**4003** -憑證指紋不符</span><span class="sxs-lookup"><span data-stu-id="ca328-139">**4003** — Certificate Thumbprint Mismatch</span></span>
    
    <span data-ttu-id="ca328-140">在安裝時間提供給代理程式的憑證指紋與偵聽程式目前使用的憑證上的指紋不相符，因此會拒絕連線。</span><span class="sxs-lookup"><span data-stu-id="ca328-140">The certificate thumbprint given to the Agent at install time does not match the thumbprint on the certificate the Listener is currently using and therefore the connection will be refused.</span></span> <span data-ttu-id="ca328-141">卸載代理程式，然後使用正確的憑證指紋重新安裝。</span><span class="sxs-lookup"><span data-stu-id="ca328-141">Uninstall the Agent and re-install it using the correct certificate thumbprint.</span></span>
    
  - <span data-ttu-id="ca328-142">**4004** -回應或 HttpStatusCode 無效</span><span class="sxs-lookup"><span data-stu-id="ca328-142">**4004** — Invalid Response or HttpStatusCode</span></span>
    
    <span data-ttu-id="ca328-143">攔截器未以預期的狀態回應。</span><span class="sxs-lookup"><span data-stu-id="ca328-143">The Listener is not responding with an expected status.</span></span> 
    
  - <span data-ttu-id="ca328-144">如果連線已代理，請檢查 proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="ca328-144">If the connection is proxied, check the proxy configuration.</span></span>
    
  - <span data-ttu-id="ca328-145">檢查監聽器電腦的 StatsMan 記錄是否有其設定問題。</span><span class="sxs-lookup"><span data-stu-id="ca328-145">Check the Listener computer's StatsMan log for issues with its configuration.</span></span>
    
  - <span data-ttu-id="ca328-146">**4005** -無法反序列化 XML</span><span class="sxs-lookup"><span data-stu-id="ca328-146">**4005** — Couldn't de-serialize the XML</span></span>
    
    <span data-ttu-id="ca328-147">監聽器伺服器上的伺服器資訊已損毀，或代理程式與監聽器電腦之間的版本不相符。</span><span class="sxs-lookup"><span data-stu-id="ca328-147">The server info on the Listener server is corrupt or there may be a version mismatch between the Agent and the Listener computers.</span></span> <span data-ttu-id="ca328-148">確定版本相符，並檢查攔截器事件記錄檔是否有問題。</span><span class="sxs-lookup"><span data-stu-id="ca328-148">Ensure the versions match and check the Listener event log for issues.</span></span>
    
## <a name="listener-events"></a><span data-ttu-id="ca328-149">攔截器事件</span><span class="sxs-lookup"><span data-stu-id="ca328-149">Listener events</span></span>
<span data-ttu-id="ca328-150"><a name="BKMK_Listener"> </a></span><span class="sxs-lookup"><span data-stu-id="ca328-150"><a name="BKMK_Listener"> </a></span></span>

- <span data-ttu-id="ca328-151">**10000** —啟動失敗未知原因 (這些是無法復原，而且此服務會因結果而停止/損毀) </span><span class="sxs-lookup"><span data-stu-id="ca328-151">**10000** — Startup failure Unknown reason (these are unrecoverable and the service will stop/crash as a result)</span></span>
    
  - <span data-ttu-id="ca328-152">**10001** —設定問題</span><span class="sxs-lookup"><span data-stu-id="ca328-152">**10001** — Configuration problem</span></span>
    
    <span data-ttu-id="ca328-153">一般來說，當 [listener_install_location] \PerfAgentListener.exe.config 檔案已手動修改，且應用程式無法讀取時，就會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="ca328-153">Generally this will occur when the [listener_install_location]\PerfAgentListener.exe.config file has been modified by hand and cannot be read by the application.</span></span>
    
  - <span data-ttu-id="ca328-154">**10002** -HTTP 攔截器初始化錯誤</span><span class="sxs-lookup"><span data-stu-id="ca328-154">**10002** — HTTP Listener initialization error</span></span>
    
    <span data-ttu-id="ca328-155">當安裝時 URL ACL 未正確設定，或 SSL 憑證無效時，通常會記錄此事件。</span><span class="sxs-lookup"><span data-stu-id="ca328-155">This event will generally be logged when the URL ACL has not been set properly during installation or the SSL Cert is invalid.</span></span> <span data-ttu-id="ca328-156">確定您的設定中的憑證是有效的。</span><span class="sxs-lookup"><span data-stu-id="ca328-156">Ensure the certificate in your configuration is valid.</span></span> <span data-ttu-id="ca328-157">如果是，請根據 [部署統計資料管理員](deploy.md#BKMK_Deploy)中的指示重新安裝攔截器。</span><span class="sxs-lookup"><span data-stu-id="ca328-157">If it is, reinstall the Listener according to the instructions in [Deploy Statistics Manager](deploy.md#BKMK_Deploy).</span></span>
    
  - <span data-ttu-id="ca328-158">**10003** — Redis 失敗</span><span class="sxs-lookup"><span data-stu-id="ca328-158">**10003** — Redis failure</span></span>
    
  - <span data-ttu-id="ca328-159">**10004** —快取基礎結構失敗</span><span class="sxs-lookup"><span data-stu-id="ca328-159">**10004** — Caching infrastructure failure</span></span>
    
  - <span data-ttu-id="ca328-160">**10007** — redis 中儲存的設定 () </span><span class="sxs-lookup"><span data-stu-id="ca328-160">**10007** — Settings (stored in redis)</span></span>
    
    <span data-ttu-id="ca328-161">攔截器無法連絡 Redis，或從快取中取得格式正確的資料，而且無法啟動。</span><span class="sxs-lookup"><span data-stu-id="ca328-161">The Listener could not contact Redis or retrieve well-formed data from the cache and could not start.</span></span> <span data-ttu-id="ca328-162">確定伺服器上已啟動並正確設定 Redis 服務。</span><span class="sxs-lookup"><span data-stu-id="ca328-162">Ensure the Redis service is started and configured properly on the server.</span></span>
    
  - <span data-ttu-id="ca328-163">**10005** --伺服器資訊檢索/剖析</span><span class="sxs-lookup"><span data-stu-id="ca328-163">**10005** — Server info retrieval/parsing</span></span>
    
    <span data-ttu-id="ca328-164">Redis 快取中的拓撲資訊無效。</span><span class="sxs-lookup"><span data-stu-id="ca328-164">The topology information in the Redis cache is invalid.</span></span> <span data-ttu-id="ca328-165">首先，嘗試重新開機 Redis 和監聽器。</span><span class="sxs-lookup"><span data-stu-id="ca328-165">First, attempt to restart Redis and the Listener.</span></span> <span data-ttu-id="ca328-166">如果錯誤仍然存在，請參閱匯 [入拓撲](deploy.md#BKMK_ImportTopology) 以重新建立拓撲資料。</span><span class="sxs-lookup"><span data-stu-id="ca328-166">If the error persists, see [Import the topology](deploy.md#BKMK_ImportTopology) to recreate the topology data.</span></span>
    
- <span data-ttu-id="ca328-167">**10100** — Redis PING 中斷</span><span class="sxs-lookup"><span data-stu-id="ca328-167">**10100** — Redis PING outage</span></span>
    
  - <span data-ttu-id="ca328-168">**10101** --Redis PING 連續中斷 (每60秒) </span><span class="sxs-lookup"><span data-stu-id="ca328-168">**10101** — Redis PING continued outage (every 60 seconds)</span></span>
    
  - <span data-ttu-id="ca328-169">**30100** —還原 Redis PING 中斷</span><span class="sxs-lookup"><span data-stu-id="ca328-169">**30100** — Redis PING outage restored</span></span>
    
    <span data-ttu-id="ca328-170">當監聽器無法連線至 Redis 時，將會記錄這些事件。</span><span class="sxs-lookup"><span data-stu-id="ca328-170">These will be logged when the Listener cannot connect to Redis.</span></span> <span data-ttu-id="ca328-171">確定已啟動 Redis，且接聽程式和 Redis 之間的網路連線可供使用。</span><span class="sxs-lookup"><span data-stu-id="ca328-171">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="ca328-172">**10200** — Redis 寫入中斷</span><span class="sxs-lookup"><span data-stu-id="ca328-172">**10200** — Redis Write outage</span></span>
    
  - <span data-ttu-id="ca328-173">**10201** （Redis 寫入中斷 (每60秒繼續) </span><span class="sxs-lookup"><span data-stu-id="ca328-173">**10201** — Redis Write outage continued (every 60 seconds)</span></span>
    
  - <span data-ttu-id="ca328-174">**30100** — Redis 寫入中斷已解決</span><span class="sxs-lookup"><span data-stu-id="ca328-174">**30100** — Redis Write outage resolved</span></span>
    
    <span data-ttu-id="ca328-175">當監聽器無法寫入 Redis 快取時，將會記錄這些事件。</span><span class="sxs-lookup"><span data-stu-id="ca328-175">These will be logged when the Listener cannot write to the Redis cache.</span></span> <span data-ttu-id="ca328-176">確定已啟動 Redis，且接聽程式和 Redis 之間的網路連線可供使用。</span><span class="sxs-lookup"><span data-stu-id="ca328-176">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="ca328-177">**30000** -成功啟動</span><span class="sxs-lookup"><span data-stu-id="ca328-177">**30000** — Successfully started</span></span>
    
    <span data-ttu-id="ca328-178">在每次啟動監聽器時進行記錄。</span><span class="sxs-lookup"><span data-stu-id="ca328-178">Logged each time the Listener is started.</span></span>
    
- <span data-ttu-id="ca328-179">**22000** —統計資料管理員代理程式的初始化成功。</span><span class="sxs-lookup"><span data-stu-id="ca328-179">**22000** — Initialization of Statistics Manager Agent succeeded.</span></span>
    
- <span data-ttu-id="ca328-180">**23000** —初始化 EventLogQueryManager 成功 (第一次或失敗之後) </span><span class="sxs-lookup"><span data-stu-id="ca328-180">**23000** — Initialization of EventLogQueryManager succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="ca328-181">**24000** —初始化 serverinfo 成功 (第一次或失敗之後) </span><span class="sxs-lookup"><span data-stu-id="ca328-181">**24000** — Initialization of serverinfo succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="ca328-182">**25000** -當您無法開機自檢 (或初次成功開機自檢後，監聽器會傳回線上) </span><span class="sxs-lookup"><span data-stu-id="ca328-182">**25000** — Listener is back online after failing to post (or first successful post)</span></span>
    
- <span data-ttu-id="ca328-183">**5000** —從離線的監聽器開始發佈資料</span><span class="sxs-lookup"><span data-stu-id="ca328-183">**5000** — Start of listener offline for posting data</span></span>
    
- <span data-ttu-id="ca328-184">**5001** -攔截器在長期間內仍保持離線狀態</span><span class="sxs-lookup"><span data-stu-id="ca328-184">**5001** — Listener is still offline for an extended period</span></span>
    
    <span data-ttu-id="ca328-185">這些事件對於監控/警示/清除問題非常有用。</span><span class="sxs-lookup"><span data-stu-id="ca328-185">These events can be useful for monitoring/alerting/clearing issues.</span></span>
    
## <a name="website-issues"></a><span data-ttu-id="ca328-186">網站問題</span><span class="sxs-lookup"><span data-stu-id="ca328-186">Website issues</span></span>
<span data-ttu-id="ca328-187"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="ca328-187"><a name="BKMK_Website"> </a></span></span>

- <span data-ttu-id="ca328-188">Chrome 中的重複登入提示-這是在1.1 版中已解決的錯誤。</span><span class="sxs-lookup"><span data-stu-id="ca328-188">Repetitive login prompts in Chrome - this was a bug that has been resolved in version 1.1.</span></span> <span data-ttu-id="ca328-189">如果您在 Chrome 瀏覽器中看到重複的登入提示，請確定您已升級至最新版本的統計資料管理員。</span><span class="sxs-lookup"><span data-stu-id="ca328-189">Be sure you have upgraded to the latest version of Statistics Manager if you are seeing repeated login prompts in the Chrome browser.</span></span> <span data-ttu-id="ca328-190">若要驗證您正在執行的網站版本：</span><span class="sxs-lookup"><span data-stu-id="ca328-190">To verify the version of the website you are running:</span></span>
    
  - <span data-ttu-id="ca328-191">在檔案資源管理器中，開啟 (預設目錄) </span><span class="sxs-lookup"><span data-stu-id="ca328-191">In File Explorer, open (default directory)</span></span>
    
  - <span data-ttu-id="ca328-192">在 StatsManHubWebSite.dll 上按一下滑鼠右鍵，然後查看其屬性。</span><span class="sxs-lookup"><span data-stu-id="ca328-192">Right click on StatsManHubWebSite.dll and view its properties.</span></span>
    
  - <span data-ttu-id="ca328-193">如果在 KHI 橫向模式或 [計數器詳細資料] 視圖中找不到電腦，請確定它是網站和集區的成員。</span><span class="sxs-lookup"><span data-stu-id="ca328-193">If a computer cannot be found in the KHI Landscape view or the Counter Details view, make sure it is a member of a Site and a Pool.</span></span> <span data-ttu-id="ca328-194">如果不是，則不會出現在這些視圖中。</span><span class="sxs-lookup"><span data-stu-id="ca328-194">If it is not, it will not appear in those views.</span></span> <span data-ttu-id="ca328-195">如需在拓撲中定義伺服器的網站和集區的詳細資訊，請參閱匯 [入拓撲](deploy.md#BKMK_ImportTopology)。</span><span class="sxs-lookup"><span data-stu-id="ca328-195">For information about defining a site and pool for a server in the topology, see [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="ca328-196">產品版本將會顯示在描述詳細資料中。</span><span class="sxs-lookup"><span data-stu-id="ca328-196">The product version will be shown in the Description details.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="ca328-197">相關資訊</span><span class="sxs-lookup"><span data-stu-id="ca328-197">For more information</span></span>
<span data-ttu-id="ca328-198"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="ca328-198"><a name="BKMK_Website"> </a></span></span>

<span data-ttu-id="ca328-199">如需詳細資訊，請參閱下列各主題：</span><span class="sxs-lookup"><span data-stu-id="ca328-199">For more information, see the following:</span></span>
  
- [<span data-ttu-id="ca328-200">商務用 Skype Server 統計資料的規劃</span><span class="sxs-lookup"><span data-stu-id="ca328-200">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="ca328-201">部署商務用 Skype Server 統計資料</span><span class="sxs-lookup"><span data-stu-id="ca328-201">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="ca328-202">升級商務用 Skype Server 統計資料</span><span class="sxs-lookup"><span data-stu-id="ca328-202">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
