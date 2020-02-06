---
title: 部署商務用 Skype Server 統計資料
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 摘要：請閱讀本主題，以瞭解如何部署商務用 Skype Server 的統計資料管理器。
ms.openlocfilehash: 44aad14970716f00550255855d251919a767a268
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803963"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="96667-103">部署商務用 Skype Server 統計資料</span><span class="sxs-lookup"><span data-stu-id="96667-103">Deploy Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="96667-104">**摘要：** 若要瞭解如何部署商務用 Skype Server 的統計資料管理器，請閱讀本主題。</span><span class="sxs-lookup"><span data-stu-id="96667-104">**Summary:** Read this topic to learn how to deploy Statistics Manager for Skype for Business Server.</span></span>
  
 <span data-ttu-id="96667-105">商務用 Skype Server 的 [統計資料管理員] 是一種強大的工具，可讓您即時查看商務用 Skype Server 健康情況和效能資料。</span><span class="sxs-lookup"><span data-stu-id="96667-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="96667-106">您可以每隔幾秒在數百個伺服器上輪詢效能資料，並立即在統計資料管理器網站上查看結果。</span><span class="sxs-lookup"><span data-stu-id="96667-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>
  
<span data-ttu-id="96667-107">在您嘗試安裝 [統計資料管理器] 之前，請務必熟悉軟體、網路和硬體需求。</span><span class="sxs-lookup"><span data-stu-id="96667-107">Before you attempt to install Statistics Manager, be sure you are familiar with the software, networking, and hardware requirements.</span></span> <span data-ttu-id="96667-108">如需詳細資訊，請參閱[規劃商務用 Skype Server 的統計管理員方案](plan.md)。</span><span class="sxs-lookup"><span data-stu-id="96667-108">For more information, see [Plan for Statistics Manager for Skype for Business Server](plan.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="96667-109">如果您是從舊版的統計資料管理員升級，請參閱[商務用 Skype Server 的升級統計資料管理器](upgrade.md)。</span><span class="sxs-lookup"><span data-stu-id="96667-109">If you are upgrading from a previous version of Statistics Manager, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="96667-110">[統計資料管理器] 網站已在 Internet Explorer 11 +、Edge 20.10240 + 和 Chrome 46 + （目前的長綠版本）上經過測試和正常運作。</span><span class="sxs-lookup"><span data-stu-id="96667-110">The Statistics Manager Website has been tested and works correctly on Internet Explorer 11+, Edge 20.10240+ , and Chrome 46+ (current evergreen version).</span></span> 
  
<span data-ttu-id="96667-111">您可以在[https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload)下載 [統計資料管理器] 中找到。</span><span class="sxs-lookup"><span data-stu-id="96667-111">You can find the Statistics Manager downloadable at [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload).</span></span> 
  
<span data-ttu-id="96667-112">本主題包含下列各節：</span><span class="sxs-lookup"><span data-stu-id="96667-112">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="96667-113">部署統計資料管理員</span><span class="sxs-lookup"><span data-stu-id="96667-113">Deploy Statistics Manager</span></span>](deploy.md#BKMK_Deploy)
    
- [<span data-ttu-id="96667-114">疑難排解您的部署</span><span class="sxs-lookup"><span data-stu-id="96667-114">Troubleshoot your deployment</span></span>](deploy.md#BKMK_Troubleshoot)
    
- [<span data-ttu-id="96667-115">建立自我簽署憑證</span><span class="sxs-lookup"><span data-stu-id="96667-115">Create a self-signed certificate</span></span>](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a><span data-ttu-id="96667-116">部署統計資料管理員</span><span class="sxs-lookup"><span data-stu-id="96667-116">Deploy Statistics Manager</span></span>
<span data-ttu-id="96667-117"><a name="BKMK_Deploy"> </a></span><span class="sxs-lookup"><span data-stu-id="96667-117"><a name="BKMK_Deploy"> </a></span></span>

<span data-ttu-id="96667-118">若要部署統計管理員，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="96667-118">To deploy Statistics Manager, follow these steps:</span></span>
  
1. <span data-ttu-id="96667-119">您可以安裝 Redis 的記憶體內部緩存系統，並確保您已安裝適當的憑證，以準備監聽器主機電腦。</span><span class="sxs-lookup"><span data-stu-id="96667-119">Prepare the Listener host machine by installing the Redis in-memory caching system, and by ensuring that you have installed the appropriate certificates.</span></span>
    
2. <span data-ttu-id="96667-120">在主機電腦上安裝監聽器服務。</span><span class="sxs-lookup"><span data-stu-id="96667-120">Install the Listener service on the host machine.</span></span> 
    
3. <span data-ttu-id="96667-121">在主機電腦上安裝網站。</span><span class="sxs-lookup"><span data-stu-id="96667-121">Install the Website on the host machine.</span></span>
    
4. <span data-ttu-id="96667-122">在您想要監視的每個商務用 Skype 伺服器電腦上安裝代理程式。</span><span class="sxs-lookup"><span data-stu-id="96667-122">Install an Agent on each Skype for Business Server machine you wish to monitor.</span></span>
    
5. <span data-ttu-id="96667-123">匯入您要監視之伺服器的拓撲。</span><span class="sxs-lookup"><span data-stu-id="96667-123">Import the topology for the servers you are monitoring.</span></span>
    
> [!NOTE]
> <span data-ttu-id="96667-124">Redis、監聽器服務和網站必須全部安裝在同一個主機電腦上。</span><span class="sxs-lookup"><span data-stu-id="96667-124">Redis, the Listener service, and the Website must all be installed on the same host machine.</span></span> <span data-ttu-id="96667-125">確定主機電腦沒有安裝商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="96667-125">Be sure the host machine does not have Skype for Business Server installed.</span></span> 
  
### <a name="prepare-the-listener-host-machine"></a><span data-ttu-id="96667-126">準備監聽器主機機</span><span class="sxs-lookup"><span data-stu-id="96667-126">Prepare the Listener host machine</span></span>

<span data-ttu-id="96667-127">若要準備主機機，您必須安裝 Redis 的記憶體內緩存系統，並確保電腦上有有效的憑證。</span><span class="sxs-lookup"><span data-stu-id="96667-127">To prepare the host machine, you will need to install the Redis in-memory caching system, and ensure that a valid certificate is on the machine.</span></span> <span data-ttu-id="96667-128">Microsoft 建議您安裝 Redis 3.0 的最新穩定組建。</span><span class="sxs-lookup"><span data-stu-id="96667-128">Microsoft recommends that you install the latest stable build of Redis 3.0.</span></span> <span data-ttu-id="96667-129">已使用 Redis 3.2.100 測試統計資料管理員版本2.0。</span><span class="sxs-lookup"><span data-stu-id="96667-129">Statistics Manager version 2.0 was tested with Redis 3.2.100.</span></span> 
  
1. <span data-ttu-id="96667-130">從下列網站下載 Redis： [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis)。</span><span class="sxs-lookup"><span data-stu-id="96667-130">Download Redis from the following site: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis).</span></span> 
    
    <span data-ttu-id="96667-131">無法從下載未簽名的安裝程式[https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span><span class="sxs-lookup"><span data-stu-id="96667-131">Unsigned installers can be downloaded from [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span></span>
    
    <span data-ttu-id="96667-132">如有需要，可透過流行的套件管理員提供已簽署的二進位檔案： [Nuget](https://www.nuget.org/packages/Redis-64/)與[Choclatey](https://chocolatey.org/packages/redis-64)。</span><span class="sxs-lookup"><span data-stu-id="96667-132">If required, signed binaries are available through popular package managers: [Nuget](https://www.nuget.org/packages/Redis-64/) and [Choclatey](https://chocolatey.org/packages/redis-64).</span></span>
    
   - <span data-ttu-id="96667-133">執行提供的 msi，然後依照提示進行。</span><span class="sxs-lookup"><span data-stu-id="96667-133">Run the provided msi and follow the prompts.</span></span>
    
   - <span data-ttu-id="96667-134">請勿選取方塊來新增防火牆規則。</span><span class="sxs-lookup"><span data-stu-id="96667-134">Do not check the box to add a firewall rule.</span></span>
    
2. <span data-ttu-id="96667-135">監聽器服務需要證書。</span><span class="sxs-lookup"><span data-stu-id="96667-135">The Listener service requires a certificate.</span></span> <span data-ttu-id="96667-136">Microsoft 強烈建議您擁有由受信任的憑證頒發機構簽署的憑證。</span><span class="sxs-lookup"><span data-stu-id="96667-136">Microsoft strongly recommends that you have a certificate signed by a trusted certificate authority.</span></span> 
    
    <span data-ttu-id="96667-137">例如，如果您想要在 lab 中使用自我簽署憑證，以進行測試，請參閱[建立自我簽署憑證](deploy.md#BKMK_SelfCert)。</span><span class="sxs-lookup"><span data-stu-id="96667-137">If you want to use a self-signed certificate--for testing purposes in a lab, for example--see [Create a self-signed certificate](deploy.md#BKMK_SelfCert).</span></span>
    
    <span data-ttu-id="96667-138">請注意，代理程式會使用證書指紋驗證（而不是鏈式驗證）。</span><span class="sxs-lookup"><span data-stu-id="96667-138">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="96667-139">因為可以使用自我簽署的憑證，所以它不會進行完整的憑證驗證。</span><span class="sxs-lookup"><span data-stu-id="96667-139">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>
    
### <a name="install-the-listener-service"></a><span data-ttu-id="96667-140">安裝偵聽程式服務</span><span class="sxs-lookup"><span data-stu-id="96667-140">Install the Listener service</span></span>

<span data-ttu-id="96667-141">若要在主機電腦上安裝監聽器服務，請執行 StatsManPerfAgentListener 並指定下列專案：</span><span class="sxs-lookup"><span data-stu-id="96667-141">Install the Listener service on the host machine by running the StatsManPerfAgentListener.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="96667-142">查看授權協定，如果您同意，請選取 **[我接受授權合約中的條款**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="96667-142">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="96667-143">在下一個頁面上，指定下列資訊：</span><span class="sxs-lookup"><span data-stu-id="96667-143">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="96667-144">**服務密碼：** 這是遠端代理程式將用來驗證監聽器服務的密碼。</span><span class="sxs-lookup"><span data-stu-id="96667-144">**Service Password:** This is the password the remote Agents will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="96667-145">**服務埠：** 這是監聽器將用來與 Agent 通訊的 HTTPS 埠號碼。</span><span class="sxs-lookup"><span data-stu-id="96667-145">**Service Port:** This is the HTTPS port number that the Listener will use to communicate with the Agents.</span></span> <span data-ttu-id="96667-146">在安裝期間，系統會允許透過本機防火牆使用這個埠，將會建立 URL ACL，且 SSL 憑證會系結到這個埠。</span><span class="sxs-lookup"><span data-stu-id="96667-146">During installation, this port will be allowed through the local firewall, a URL ACL will be created, and an SSL cert will be bound to this port.</span></span> <span data-ttu-id="96667-147">預設值為8443。</span><span class="sxs-lookup"><span data-stu-id="96667-147">The default is 8443.</span></span>
    
   - <span data-ttu-id="96667-148">**憑證指紋：** 這是監聽器將用來加密 HTTPS 通訊協定的憑證指紋。</span><span class="sxs-lookup"><span data-stu-id="96667-148">**Certificate Thumbprint:** This is the certificate thumbprint the Listener will use to encrypt the HTTPS protocol.</span></span> <span data-ttu-id="96667-149">網路服務必須擁有私密金鑰的讀取存取權。</span><span class="sxs-lookup"><span data-stu-id="96667-149">Network Service must have read access to the private key.</span></span>
    
     <span data-ttu-id="96667-150">按一下 [**選取 ...** ] 按鈕來選擇指紋。</span><span class="sxs-lookup"><span data-stu-id="96667-150">Click the **Select...** button to choose the thumbprint.</span></span>
    
     <span data-ttu-id="96667-151">您可以使用 [憑證管理員] 或使用下列 PowerShell 命令，找到證書指紋：</span><span class="sxs-lookup"><span data-stu-id="96667-151">You can find the Certificate thumbprint by using Certificate Manager or by using the following PowerShell command:</span></span>
    
   ```PowerShell
   Get-ChildItem -path cert:\LocalMachine\My
   ```

   - <span data-ttu-id="96667-152">**安裝目錄：** 這是將安裝二進位檔案的目錄。</span><span class="sxs-lookup"><span data-stu-id="96667-152">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="96667-153">您可以使用 [**流覽 ...]** 按鈕來變更預設值。</span><span class="sxs-lookup"><span data-stu-id="96667-153">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="96667-154">**AppData Dir：** 這是儲存 [記錄] 資料夾及其他資料的目錄。</span><span class="sxs-lookup"><span data-stu-id="96667-154">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="96667-155">您可以變更預設值。</span><span class="sxs-lookup"><span data-stu-id="96667-155">You may change it from the default.</span></span> <span data-ttu-id="96667-156">卸載時不會刪除該檔案。</span><span class="sxs-lookup"><span data-stu-id="96667-156">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="96667-157">按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="96667-157">Click **Install**.</span></span>
    
<span data-ttu-id="96667-158">若要驗證安裝，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="96667-158">To validate the installation, perform the following steps:</span></span>
  
1. <span data-ttu-id="96667-159">開啟瀏覽器並流覽至https://localhost:\<service-port\>/healthcheck/</span><span class="sxs-lookup"><span data-stu-id="96667-159">Open a browser and navigate to https://localhost:\<service-port\>/healthcheck/</span></span>
    
    <span data-ttu-id="96667-160">根據預設，服務埠是8443（除非您已指定另一個埠）。</span><span class="sxs-lookup"><span data-stu-id="96667-160">By default, the service port is 8443 (unless you specified another port).</span></span>
    
2. <span data-ttu-id="96667-161">若要確保監聽器已正確安裝，請尋找下列各項：</span><span class="sxs-lookup"><span data-stu-id="96667-161">To ensure the Listener has installed properly, look for the following:</span></span>
    
   - <span data-ttu-id="96667-162">如果 healthcheck 頁面出現，表示已成功安裝監聽器。</span><span class="sxs-lookup"><span data-stu-id="96667-162">If the healthcheck page shows up, the Listener installation was successful.</span></span>
    
   - <span data-ttu-id="96667-163">如果 KnownServerCount 是1或更新版本，就會建立與 Redis 的連線。</span><span class="sxs-lookup"><span data-stu-id="96667-163">If the KnownServerCount is 1 or higher,  the connection to Redis is established.</span></span>
    
   - <span data-ttu-id="96667-164">在等待幾分鐘之後，且至少已安裝一個代理之後，請檢查 ValuesWritten 計數器是否為 [遞增]。</span><span class="sxs-lookup"><span data-stu-id="96667-164">After waiting a few minutes, and after at least one Agent has been installed, check to see that the ValuesWritten counter is incrementing.</span></span>
    
### <a name="install-the-website"></a><span data-ttu-id="96667-165">安裝網站</span><span class="sxs-lookup"><span data-stu-id="96667-165">Install the Website</span></span>

<span data-ttu-id="96667-166">您可以執行 StatsManWebSite （隨附于[商務用 Skype Server、即時統計管理員（64位）](https://www.microsoft.com/en-in/download/details.aspx?id=57518)）並指定下列專案，在主機電腦上安裝網站：</span><span class="sxs-lookup"><span data-stu-id="96667-166">Install the Website on the host machine by running the StatsManWebSite.msi (included with [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)) and specifying the following:</span></span>
  
1. <span data-ttu-id="96667-167">查看授權協定，如果您同意，請選取 **[我接受授權合約中的條款**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="96667-167">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="96667-168">在下一個頁面上，指定下列資訊：</span><span class="sxs-lookup"><span data-stu-id="96667-168">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="96667-169">**服務埠：** 這是網站將接聽的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="96667-169">**Service Port:** This is the port number the web site will listen on.</span></span> <span data-ttu-id="96667-170">您可以稍後使用 IIS 管理器系結來變更它。</span><span class="sxs-lookup"><span data-stu-id="96667-170">You can change it later by using IIS manager binding.</span></span> <span data-ttu-id="96667-171">在安裝期間，系統會允許透過本機防火牆使用這個埠。</span><span class="sxs-lookup"><span data-stu-id="96667-171">During installation, this port will be allowed through the local firewall.</span></span>
    
   - <span data-ttu-id="96667-172">**安裝目錄：** 這是將安裝二進位檔案的目錄。</span><span class="sxs-lookup"><span data-stu-id="96667-172">**Install Dir:** This is the directory where the binaries will be installed.</span></span> <span data-ttu-id="96667-173">您可以使用 [**流覽 ...]** 按鈕來變更預設值。</span><span class="sxs-lookup"><span data-stu-id="96667-173">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="96667-174">**AppData Dir：** 這是儲存 [記錄] 資料夾及其他資料的目錄。</span><span class="sxs-lookup"><span data-stu-id="96667-174">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="96667-175">您可以變更預設值。</span><span class="sxs-lookup"><span data-stu-id="96667-175">You may change it from the default.</span></span> <span data-ttu-id="96667-176">卸載時不會刪除該檔案。</span><span class="sxs-lookup"><span data-stu-id="96667-176">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="96667-177">按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="96667-177">Click **Install**.</span></span>
    
<span data-ttu-id="96667-178">若要查看網站，請開啟瀏覽器，然後流覽至http://localhost：，\>webport/。</span><span class="sxs-lookup"><span data-stu-id="96667-178">To view the Website, open a browser, and navigate to: http://localhost,webport\>/.</span></span>
  
<span data-ttu-id="96667-179">若要只查看健康情況資訊，請開啟瀏覽器，然後http://localhost:\<webport\>/healthcheck/流覽至：。</span><span class="sxs-lookup"><span data-stu-id="96667-179">To view health information only, open a browser, and navigate to: http://localhost:\<webport\>/healthcheck/.</span></span>
  
<span data-ttu-id="96667-180">根據預設，web 埠號碼是8080。</span><span class="sxs-lookup"><span data-stu-id="96667-180">By default, the web port number is 8080.</span></span> <span data-ttu-id="96667-181">您可以使用 [IIS 管理器] 變更網站的埠系結。</span><span class="sxs-lookup"><span data-stu-id="96667-181">You can change the port binding of the website by using IIS manager.</span></span>
  
<span data-ttu-id="96667-182">Web 安裝程式會新增一個名為 StatsManWebSiteUsers 的本地安全性群組。</span><span class="sxs-lookup"><span data-stu-id="96667-182">The web installer adds a local security group, called StatsManWebSiteUsers.</span></span> <span data-ttu-id="96667-183">您可以將帳戶新增至此安全性群組，以授與網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="96667-183">You can add accounts to this security group to grant access to the Website.</span></span> 
  
### <a name="install-the-agents"></a><span data-ttu-id="96667-184">安裝代理程式</span><span class="sxs-lookup"><span data-stu-id="96667-184">Install the Agents</span></span>

<span data-ttu-id="96667-185">透過執行 StatsManPerfAgent 並指定下列專案，在您想要監視的每個商務用 Skype 伺服器上安裝代理程式：</span><span class="sxs-lookup"><span data-stu-id="96667-185">Install an Agent on each Skype for Business Server that you wish to monitor by running the StatsManPerfAgent.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="96667-186">查看授權協定，如果您同意，請選取 **[我接受授權合約中的條款**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="96667-186">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="96667-187">在下一個頁面上，指定下列資訊：</span><span class="sxs-lookup"><span data-stu-id="96667-187">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="96667-188">**服務密碼：** 這是遠端代理程式將用來驗證監聽器服務的密碼。</span><span class="sxs-lookup"><span data-stu-id="96667-188">**Service Password:** This is the password the remote agent will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="96667-189">**服務 URI：** 這是監聽器所駐留的 URI。</span><span class="sxs-lookup"><span data-stu-id="96667-189">**Service URI:** This is the URI where the Listener resides.</span></span> <span data-ttu-id="96667-190">它應該使用https://name:port格式。</span><span class="sxs-lookup"><span data-stu-id="96667-190">It should use the https://name:port format.</span></span>
    
     <span data-ttu-id="96667-191">您可以使用 NETBIOS 名稱或 FQDN。</span><span class="sxs-lookup"><span data-stu-id="96667-191">You can use a NETBIOS name or a FQDN.</span></span> <span data-ttu-id="96667-192">您可以在偵聽程式服務上使用同時指定為**主題**或**消費者替換名稱**的名稱，但這不是必需的。</span><span class="sxs-lookup"><span data-stu-id="96667-192">You can use the name that is also specified as the **Subject** or **Subject Alternative Names** of the certificate on the Listener service, but this is not a requirement.</span></span>
    
   - <span data-ttu-id="96667-193">**服務指紋：** 這是監聽器所使用之 SSL 憑證的指紋。</span><span class="sxs-lookup"><span data-stu-id="96667-193">**Service Thumbprint:** This is the thumbprint of the SSL certificate the Listener is using.</span></span> <span data-ttu-id="96667-194">代理程式將使用這個指紋來向監聽器進行驗證。</span><span class="sxs-lookup"><span data-stu-id="96667-194">The Agent will use this thumbprint to authenticate to the Listener.</span></span> <span data-ttu-id="96667-195">（它將不會執行完整的憑證驗證，因為可以使用自我簽署的憑證）。</span><span class="sxs-lookup"><span data-stu-id="96667-195">(It will not do full certificate validation because it is possible to use self-signed certificates.)</span></span>
    
   - <span data-ttu-id="96667-196">**安裝目錄：** 這是將安裝二進位檔案的目錄。</span><span class="sxs-lookup"><span data-stu-id="96667-196">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="96667-197">您可以使用 [**流覽 ...]** 按鈕來變更預設值。</span><span class="sxs-lookup"><span data-stu-id="96667-197">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="96667-198">**AppData Dir：** 這是儲存 [記錄] 資料夾及加密的密碼 .txt 檔案的目錄。</span><span class="sxs-lookup"><span data-stu-id="96667-198">**AppData Dir:** This is the directory where the Logs folder and the encrypted password.txt file will be stored.</span></span> <span data-ttu-id="96667-199">您可能會感謝您將它變更為預設值。</span><span class="sxs-lookup"><span data-stu-id="96667-199">You may thanks change it from the default.</span></span> <span data-ttu-id="96667-200">卸載時不會刪除該檔案。</span><span class="sxs-lookup"><span data-stu-id="96667-200">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="96667-201">按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="96667-201">Click **Install**.</span></span>
    
<span data-ttu-id="96667-202">如果您要在許多電腦上安裝代理程式，您可能會想要在無人參與模式下執行。</span><span class="sxs-lookup"><span data-stu-id="96667-202">If you are installing an Agent on numerous machines, you will probably want to do this in unattended mode.</span></span> <span data-ttu-id="96667-203">例如：</span><span class="sxs-lookup"><span data-stu-id="96667-203">For example:</span></span> 
  
```
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a><span data-ttu-id="96667-204">匯入拓撲</span><span class="sxs-lookup"><span data-stu-id="96667-204">Import the topology</span></span>
<span data-ttu-id="96667-205"><a name="BKMK_ImportTopology"> </a></span><span class="sxs-lookup"><span data-stu-id="96667-205"><a name="BKMK_ImportTopology"> </a></span></span>

<span data-ttu-id="96667-206">安裝並執行 [統計資料管理器] 之後，您必須匯入商務用 Skype Server 拓撲，以便統計資料管理員知道每個伺服器的網站、池和角色。</span><span class="sxs-lookup"><span data-stu-id="96667-206">After Statistics Manager is installed and running, you need to import the Skype for Business Server topology so that Statistics Manager knows the Site, Pool, and Role of each server.</span></span> <span data-ttu-id="96667-207">若要匯入商務用 Skype Server 拓朴，您將會使用[CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) Cmdlet 來檢索貴組織中使用的每個池的相關資訊，然後將此資訊匯入到 Statistics 管理員。</span><span class="sxs-lookup"><span data-stu-id="96667-207">To import your Skype for Business Server topology, you will use the [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) cmdlet to retrieve information about each pool in use in your organization, then import this information into Statistics Manager.</span></span>
  
<span data-ttu-id="96667-208">若要匯入商務用 Skype Server 拓撲，請依照下列步驟進行：</span><span class="sxs-lookup"><span data-stu-id="96667-208">To import the Skype for Business Server topology, follow these steps:</span></span>
  
1. <span data-ttu-id="96667-209">在有商務用 Skype Server PowerShell Cmdlet 的主機上：</span><span class="sxs-lookup"><span data-stu-id="96667-209">On a host that has the Skype for Business Server PowerShell cmdlets:</span></span>
    
    <span data-ttu-id="96667-210">是.</span><span class="sxs-lookup"><span data-stu-id="96667-210">a.</span></span> <span data-ttu-id="96667-211">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="96667-211">Run the following command:</span></span> 
    
   ```PowerShell
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    <span data-ttu-id="96667-212">乙.</span><span class="sxs-lookup"><span data-stu-id="96667-212">b.</span></span> <span data-ttu-id="96667-213">將 "mypoolinfo" 檔案複製到執行監聽程式的伺服器。</span><span class="sxs-lookup"><span data-stu-id="96667-213">Copy the "mypoolinfo.xml" file to the server that runs the Listener.</span></span>
    
2. <span data-ttu-id="96667-214">在執行監聽程式的主機上：</span><span class="sxs-lookup"><span data-stu-id="96667-214">On the host that runs the Listener:</span></span>
    
   <span data-ttu-id="96667-215">是.</span><span class="sxs-lookup"><span data-stu-id="96667-215">a.</span></span> <span data-ttu-id="96667-216">執行 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="96667-216">Run PowerShell.</span></span>
    
   <span data-ttu-id="96667-217">乙.</span><span class="sxs-lookup"><span data-stu-id="96667-217">b.</span></span> <span data-ttu-id="96667-218">流覽至安裝監聽器的目錄。</span><span class="sxs-lookup"><span data-stu-id="96667-218">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="96667-219">預設值為：</span><span class="sxs-lookup"><span data-stu-id="96667-219">The default is:</span></span> 
    
   ```PowerShell
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. <span data-ttu-id="96667-220">若要確認要新增及更新的伺服器，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="96667-220">To confirm which servers are being added and updated, run the following command:</span></span>
    
   ```PowerShell
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

<span data-ttu-id="96667-221">下列命令可讓您查看所有選項：</span><span class="sxs-lookup"><span data-stu-id="96667-221">The following command enables you to view all options:</span></span>
  
```PowerShell
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

<span data-ttu-id="96667-222">若要查看您目前已匯入的伺服器資訊，請執行下列腳本：</span><span class="sxs-lookup"><span data-stu-id="96667-222">To see your currently imported server information, run the following script:</span></span> 
  
```PowerShell
.\Get-StatsManServerInfo.ps1
```

<span data-ttu-id="96667-223">如果您想要監視不在商務用 Skype Server 拓撲中的伺服器（例如 Exchange 伺服器），您可以在執行監聽程式的主機上執行單一伺服器匯入。</span><span class="sxs-lookup"><span data-stu-id="96667-223">If you would like to monitor servers that are not in your Skype for Business Server topology--an Exchange Server, for example--you can do a single-server import on the host that runs the Listener.</span></span> <span data-ttu-id="96667-224">若要執行單伺服器匯入，請依照下列步驟進行：</span><span class="sxs-lookup"><span data-stu-id="96667-224">To do a single-server import, follow these steps:</span></span>
  
1. <span data-ttu-id="96667-225">流覽至安裝監聽器的目錄。</span><span class="sxs-lookup"><span data-stu-id="96667-225">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="96667-226">預設值為：</span><span class="sxs-lookup"><span data-stu-id="96667-226">The default is:</span></span> 
    
   ```
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. <span data-ttu-id="96667-227">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="96667-227">Run the following command:</span></span>
    
   ```
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a><span data-ttu-id="96667-228">疑難排解您的部署</span><span class="sxs-lookup"><span data-stu-id="96667-228">Troubleshoot your deployment</span></span>
<span data-ttu-id="96667-229"><a name="BKMK_Troubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="96667-229"><a name="BKMK_Troubleshoot"> </a></span></span>

<span data-ttu-id="96667-230">如果代理程式無法啟動，請檢查下列專案：</span><span class="sxs-lookup"><span data-stu-id="96667-230">If an Agent fails to start, check for the following:</span></span> 
  
- <span data-ttu-id="96667-231">代理程式是在 [統計資料管理器] 中註冊的嗎？</span><span class="sxs-lookup"><span data-stu-id="96667-231">Is the agent registered in Statistics Manager?</span></span>
    
1. <span data-ttu-id="96667-232">請確定您已按照匯入拓撲的指示進行。</span><span class="sxs-lookup"><span data-stu-id="96667-232">Make sure you followed the instructions for importing the topology.</span></span> <span data-ttu-id="96667-233">請參閱匯[入拓撲](deploy.md#BKMK_ImportTopology)。</span><span class="sxs-lookup"><span data-stu-id="96667-233">See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
2. <span data-ttu-id="96667-234">如果該代理位於拓撲中未列出的伺服器上（例如，SQL AlwaysOn 群集中的節點），您將需要按照匯[入拓撲](deploy.md#BKMK_ImportTopology)中的指示手動新增該代理程式。</span><span class="sxs-lookup"><span data-stu-id="96667-234">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
- <span data-ttu-id="96667-235">工程師可以與監聽器聯繫嗎？</span><span class="sxs-lookup"><span data-stu-id="96667-235">Can the Agent contact the Listener?</span></span>
    
1. <span data-ttu-id="96667-236">確認偵聽程式服務正在執行。</span><span class="sxs-lookup"><span data-stu-id="96667-236">Make sure the Listener service is running.</span></span> 
    
    <span data-ttu-id="96667-237">如果沒有執行，請確定 Redis 正在執行，然後嘗試重新開機偵聽程式。</span><span class="sxs-lookup"><span data-stu-id="96667-237">If it is not running, make sure Redis is running, and then try to restart the Listener.</span></span>
    
2. <span data-ttu-id="96667-238">確定該埠已開啟到監聽器服務，且代理程式電腦可以與該埠進行通訊。</span><span class="sxs-lookup"><span data-stu-id="96667-238">Make sure the port is open to the Listener service, and that the Agent computer can communicate with the port.</span></span>
    
- <span data-ttu-id="96667-239">若要確保統計資料管理員收集資料，您可以檢查 CSV 檔案，如下所示。</span><span class="sxs-lookup"><span data-stu-id="96667-239">To ensure that Statistics Manager is collecting data, you can check the CSV file as follows.</span></span> 
    
    <span data-ttu-id="96667-240">下列命令會檢索計數器儲存名稱：</span><span class="sxs-lookup"><span data-stu-id="96667-240">The following command retrieves the counter storage names:</span></span> 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    <span data-ttu-id="96667-241">下一個命令會檢索指定計數器的值：</span><span class="sxs-lookup"><span data-stu-id="96667-241">The next command retrieves the values for the specified counters:</span></span> 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

<span data-ttu-id="96667-242">如需您在應用程式事件日誌中可能會看到的所有事件的相關資訊，請參閱[疑難排解商務用 Skype Server 的統計資料管理員](troubleshoot.md)。</span><span class="sxs-lookup"><span data-stu-id="96667-242">For information about all the events you might see in the application event log, see [Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md).</span></span>
  
## <a name="create-a-self-signed-certificate"></a><span data-ttu-id="96667-243">建立自我簽署憑證</span><span class="sxs-lookup"><span data-stu-id="96667-243">Create a self-signed certificate</span></span>
<span data-ttu-id="96667-244"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="96667-244"><a name="BKMK_SelfCert"> </a></span></span>

<span data-ttu-id="96667-245">Microsoft 強烈建議您使用由受信任的憑證頒發機構簽署的憑證。</span><span class="sxs-lookup"><span data-stu-id="96667-245">Microsoft strongly recommends that you use a certificate signed by a trusted certificate authority.</span></span> <span data-ttu-id="96667-246">不過，如果您想要使用自行簽署式憑證來進行測試，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="96667-246">However, if you want to use a self-signed certificate for testing purposes, do the following:</span></span> 
  
1. <span data-ttu-id="96667-247">在以系統管理員身分登入的情況下，從 PowerShell 主控台輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="96667-247">From a PowerShell console while logged on as Administrator, type the following:</span></span>
    
   ```PowerShell
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. <span data-ttu-id="96667-248">類型`certlm.msc`。</span><span class="sxs-lookup"><span data-stu-id="96667-248">Type  `certlm.msc`.</span></span> <span data-ttu-id="96667-249">這將會開啟本機電腦的 [認證管理員]。</span><span class="sxs-lookup"><span data-stu-id="96667-249">This will open the Certificate Manager for the local machine.</span></span>
    
3. <span data-ttu-id="96667-250">流覽至 [**個人**]，然後開啟 [**憑證**]。</span><span class="sxs-lookup"><span data-stu-id="96667-250">Navigate to **Personal**, and then open **Certificates**.</span></span>
    
4. <span data-ttu-id="96667-251">以滑鼠右鍵按一下 [ **StatsManListener-\>所有\>任務-管理私人金鑰]。**</span><span class="sxs-lookup"><span data-stu-id="96667-251">Right click on **StatsManListener-\>All Tasks-\>Manage Private Keys…**</span></span>
    
5. <span data-ttu-id="96667-252">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="96667-252">Click **Add**.</span></span>
    
6. <span data-ttu-id="96667-253">在 [**輸入要選取的物件名稱**] 方塊中，輸入下列內容： Network Service</span><span class="sxs-lookup"><span data-stu-id="96667-253">In the **Enter the object names to select** box, type the following: Network Service</span></span>
    
7. <span data-ttu-id="96667-254">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="96667-254">Click **OK**.</span></span>
    
8. <span data-ttu-id="96667-255">在 [**完全控制**] 底下，取消選取 [**允許**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="96667-255">Under **Full Control**, un-check the **Allow** check box.</span></span> <span data-ttu-id="96667-256">（只需要 [讀取存取]。）</span><span class="sxs-lookup"><span data-stu-id="96667-256">(Only Read access is necessary.)</span></span>
    
9. <span data-ttu-id="96667-257">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="96667-257">Click **OK**.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="96667-258">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="96667-258">For more information</span></span>
<span data-ttu-id="96667-259"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="96667-259"><a name="BKMK_SelfCert"> </a></span></span>

<span data-ttu-id="96667-260">如需詳細資訊，請參閱下列內容：</span><span class="sxs-lookup"><span data-stu-id="96667-260">For more information, see the following:</span></span>
  
- [<span data-ttu-id="96667-261">商務用 Skype Server 統計資料的規劃</span><span class="sxs-lookup"><span data-stu-id="96667-261">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="96667-262">升級商務用 Skype Server 統計資料</span><span class="sxs-lookup"><span data-stu-id="96667-262">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
    
- <span data-ttu-id="96667-263">[商務用 Skype Server ß的統計資料管理員疑難排解](troubleshoot.md)</span><span class="sxs-lookup"><span data-stu-id="96667-263">[Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md) ß</span></span>
