---
title: 部署商務用 Skype Server 統計資料
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
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 摘要：閱讀此主題以瞭解如何部署商務用 Skype Server 的統計資料管理員。
ms.openlocfilehash: 79e07c29a5df4a5da239687708a9bb52e995d191
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814813"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="1d99b-103">部署商務用 Skype Server 統計資料</span><span class="sxs-lookup"><span data-stu-id="1d99b-103">Deploy Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="1d99b-104">**摘要：** 閱讀此主題以瞭解如何部署商務用 Skype Server 的統計資料管理員。</span><span class="sxs-lookup"><span data-stu-id="1d99b-104">**Summary:** Read this topic to learn how to deploy Statistics Manager for Skype for Business Server.</span></span>
  
 <span data-ttu-id="1d99b-105">商務用 Skype Server 的統計資料管理員是一種強大的工具，可讓您即時查看商務用 Skype 伺服器的健康情況和效能資料。</span><span class="sxs-lookup"><span data-stu-id="1d99b-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="1d99b-106">您可以每隔幾秒輪詢每數百部伺服器上的效能資料，並在統計資料管理員網站上立即查看結果。</span><span class="sxs-lookup"><span data-stu-id="1d99b-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>
  
<span data-ttu-id="1d99b-107">在您嘗試安裝統計資料管理員之前，請確定您已熟悉軟體、網路及硬體需求。</span><span class="sxs-lookup"><span data-stu-id="1d99b-107">Before you attempt to install Statistics Manager, be sure you are familiar with the software, networking, and hardware requirements.</span></span> <span data-ttu-id="1d99b-108">如需詳細資訊，請參閱 [規劃商務用 Skype Server 的統計資料管理員](plan.md)。</span><span class="sxs-lookup"><span data-stu-id="1d99b-108">For more information, see [Plan for Statistics Manager for Skype for Business Server](plan.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1d99b-109">若要從舊版的統計資料管理員升級，請參閱 [升級統計資料管理員以取得商務用 Skype Server](upgrade.md)。</span><span class="sxs-lookup"><span data-stu-id="1d99b-109">If you are upgrading from a previous version of Statistics Manager, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1d99b-110">在 Internet Explorer 11 +、Edge 20.10240 + 和 Chrome 46 + (目前的長綠版本) 上，已測試並正確地處理統計資料管理員網站。</span><span class="sxs-lookup"><span data-stu-id="1d99b-110">The Statistics Manager Website has been tested and works correctly on Internet Explorer 11+, Edge 20.10240+ , and Chrome 46+ (current evergreen version).</span></span> 
  
<span data-ttu-id="1d99b-111">您可以在中找到 [統計資料管理員] [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload) 。</span><span class="sxs-lookup"><span data-stu-id="1d99b-111">You can find the Statistics Manager downloadable at [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload).</span></span> 
  
<span data-ttu-id="1d99b-112">本主題包含下列各節：</span><span class="sxs-lookup"><span data-stu-id="1d99b-112">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="1d99b-113">部署統計資料管理員</span><span class="sxs-lookup"><span data-stu-id="1d99b-113">Deploy Statistics Manager</span></span>](deploy.md#BKMK_Deploy)
    
- [<span data-ttu-id="1d99b-114">疑難排解您的部署</span><span class="sxs-lookup"><span data-stu-id="1d99b-114">Troubleshoot your deployment</span></span>](deploy.md#BKMK_Troubleshoot)
    
- [<span data-ttu-id="1d99b-115">建立自我簽署憑證</span><span class="sxs-lookup"><span data-stu-id="1d99b-115">Create a self-signed certificate</span></span>](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a><span data-ttu-id="1d99b-116">部署統計資料管理員</span><span class="sxs-lookup"><span data-stu-id="1d99b-116">Deploy Statistics Manager</span></span>
<span data-ttu-id="1d99b-117"><a name="BKMK_Deploy"> </a></span><span class="sxs-lookup"><span data-stu-id="1d99b-117"><a name="BKMK_Deploy"> </a></span></span>

<span data-ttu-id="1d99b-118">若要部署統計資料管理員，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="1d99b-118">To deploy Statistics Manager, follow these steps:</span></span>
  
1. <span data-ttu-id="1d99b-119">安裝 Redis 的記憶體中快取系統，並確認您已安裝適當的憑證，以準備監聽器主機電腦。</span><span class="sxs-lookup"><span data-stu-id="1d99b-119">Prepare the Listener host machine by installing the Redis in-memory caching system, and by ensuring that you have installed the appropriate certificates.</span></span>
    
2. <span data-ttu-id="1d99b-120">在主機機器上安裝監聽器服務。</span><span class="sxs-lookup"><span data-stu-id="1d99b-120">Install the Listener service on the host machine.</span></span> 
    
3. <span data-ttu-id="1d99b-121">在主機電腦上安裝網站。</span><span class="sxs-lookup"><span data-stu-id="1d99b-121">Install the Website on the host machine.</span></span>
    
4. <span data-ttu-id="1d99b-122">在您想要監視的每一部商務用 Skype Server 電腦上安裝代理人。</span><span class="sxs-lookup"><span data-stu-id="1d99b-122">Install an Agent on each Skype for Business Server machine you wish to monitor.</span></span>
    
5. <span data-ttu-id="1d99b-123">匯入所監控之伺服器的拓撲。</span><span class="sxs-lookup"><span data-stu-id="1d99b-123">Import the topology for the servers you are monitoring.</span></span>
    
> [!NOTE]
> <span data-ttu-id="1d99b-124">Redis、攔截器服務和網站必須全部安裝在相同的主機電腦上。</span><span class="sxs-lookup"><span data-stu-id="1d99b-124">Redis, the Listener service, and the Website must all be installed on the same host machine.</span></span> <span data-ttu-id="1d99b-125">請確定主機電腦沒有安裝商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="1d99b-125">Be sure the host machine does not have Skype for Business Server installed.</span></span> 
  
### <a name="prepare-the-listener-host-machine"></a><span data-ttu-id="1d99b-126">準備監聽器主機電腦</span><span class="sxs-lookup"><span data-stu-id="1d99b-126">Prepare the Listener host machine</span></span>

<span data-ttu-id="1d99b-127">若要準備主機機，您需要安裝 Redis 的記憶體中快取系統，並確認電腦上有有效的憑證。</span><span class="sxs-lookup"><span data-stu-id="1d99b-127">To prepare the host machine, you will need to install the Redis in-memory caching system, and ensure that a valid certificate is on the machine.</span></span> <span data-ttu-id="1d99b-128">Microsoft 建議您安裝 Redis 3.0 的最新穩定組建。</span><span class="sxs-lookup"><span data-stu-id="1d99b-128">Microsoft recommends that you install the latest stable build of Redis 3.0.</span></span> <span data-ttu-id="1d99b-129">統計資料管理員版本2.0 已透過 Redis 3.2.100 進行測試。</span><span class="sxs-lookup"><span data-stu-id="1d99b-129">Statistics Manager version 2.0 was tested with Redis 3.2.100.</span></span> 
  
1. <span data-ttu-id="1d99b-130">從下列網站下載 Redis： [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis) 。</span><span class="sxs-lookup"><span data-stu-id="1d99b-130">Download Redis from the following site: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis).</span></span> 
    
    <span data-ttu-id="1d99b-131">未簽署的安裝程式可從 [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span><span class="sxs-lookup"><span data-stu-id="1d99b-131">Unsigned installers can be downloaded from [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span></span>
    
    <span data-ttu-id="1d99b-132">如有需要，可透過流行的套件管理員取得已簽署的二進位檔案： [Nuget](https://www.nuget.org/packages/Redis-64/) 和 [Choclatey](https://chocolatey.org/packages/redis-64)。</span><span class="sxs-lookup"><span data-stu-id="1d99b-132">If required, signed binaries are available through popular package managers: [Nuget](https://www.nuget.org/packages/Redis-64/) and [Choclatey](https://chocolatey.org/packages/redis-64).</span></span>
    
   - <span data-ttu-id="1d99b-133">執行提供的 msi 並依照提示執行。</span><span class="sxs-lookup"><span data-stu-id="1d99b-133">Run the provided msi and follow the prompts.</span></span>
    
   - <span data-ttu-id="1d99b-134">請勿勾選 [新增防火牆規則] 方塊。</span><span class="sxs-lookup"><span data-stu-id="1d99b-134">Do not check the box to add a firewall rule.</span></span>
    
2. <span data-ttu-id="1d99b-135">監聽器服務需要憑證。</span><span class="sxs-lookup"><span data-stu-id="1d99b-135">The Listener service requires a certificate.</span></span> <span data-ttu-id="1d99b-136">Microsoft 強烈建議您擁有由受信任的憑證授權單位單位簽署的憑證。</span><span class="sxs-lookup"><span data-stu-id="1d99b-136">Microsoft strongly recommends that you have a certificate signed by a trusted certificate authority.</span></span> 
    
    <span data-ttu-id="1d99b-137">如果您想要使用自我簽署的憑證，以在實驗室中進行測試，例如，請參閱 [建立自我簽署憑證](deploy.md#BKMK_SelfCert)。</span><span class="sxs-lookup"><span data-stu-id="1d99b-137">If you want to use a self-signed certificate--for testing purposes in a lab, for example--see [Create a self-signed certificate](deploy.md#BKMK_SelfCert).</span></span>
    
    <span data-ttu-id="1d99b-138">請注意，代理程式會使用憑證指紋驗證 (，而不是鏈式驗證) 。</span><span class="sxs-lookup"><span data-stu-id="1d99b-138">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="1d99b-139">因為可能會使用自我簽署的憑證，所以不會執行完整的憑證驗證。</span><span class="sxs-lookup"><span data-stu-id="1d99b-139">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>
    
### <a name="install-the-listener-service"></a><span data-ttu-id="1d99b-140">安裝攔截器服務</span><span class="sxs-lookup"><span data-stu-id="1d99b-140">Install the Listener service</span></span>

<span data-ttu-id="1d99b-141">執行 StatsManPerfAgentListener.msi，並指定下列專案，以在主機機器上安裝監聽器服務：</span><span class="sxs-lookup"><span data-stu-id="1d99b-141">Install the Listener service on the host machine by running the StatsManPerfAgentListener.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="1d99b-142">請參閱授權合約，如果同意，請選取 [ **我接受授權合約中的條款**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="1d99b-142">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="1d99b-143">在下一個頁面上，指定下列資訊：</span><span class="sxs-lookup"><span data-stu-id="1d99b-143">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="1d99b-144">**服務密碼：** 這是遠端代理程式將用來驗證監聽器服務的密碼。</span><span class="sxs-lookup"><span data-stu-id="1d99b-144">**Service Password:** This is the password the remote Agents will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="1d99b-145">**服務埠：** 這是攔截器將用來與代理程式通訊的 HTTPS 埠號碼。</span><span class="sxs-lookup"><span data-stu-id="1d99b-145">**Service Port:** This is the HTTPS port number that the Listener will use to communicate with the Agents.</span></span> <span data-ttu-id="1d99b-146">在安裝期間，將會允許透過本機防火牆的埠，建立 URL ACL，並將 SSL 憑證系結至此埠。</span><span class="sxs-lookup"><span data-stu-id="1d99b-146">During installation, this port will be allowed through the local firewall, a URL ACL will be created, and an SSL cert will be bound to this port.</span></span> <span data-ttu-id="1d99b-147">預設值為8443。</span><span class="sxs-lookup"><span data-stu-id="1d99b-147">The default is 8443.</span></span>
    
   - <span data-ttu-id="1d99b-148">**憑證指紋：** 這是監聽器將用來加密 HTTPS 通訊協定的憑證指紋。</span><span class="sxs-lookup"><span data-stu-id="1d99b-148">**Certificate Thumbprint:** This is the certificate thumbprint the Listener will use to encrypt the HTTPS protocol.</span></span> <span data-ttu-id="1d99b-149">網路服務必須具有私密金鑰的讀取權限。</span><span class="sxs-lookup"><span data-stu-id="1d99b-149">Network Service must have read access to the private key.</span></span>
    
     <span data-ttu-id="1d99b-150">按一下 [ **選取 ...** ] 按鈕，選擇指紋。</span><span class="sxs-lookup"><span data-stu-id="1d99b-150">Click the **Select...** button to choose the thumbprint.</span></span>
    
     <span data-ttu-id="1d99b-151">您可以使用 [憑證管理員] 或使用下列 PowerShell 命令，找到憑證指紋：</span><span class="sxs-lookup"><span data-stu-id="1d99b-151">You can find the Certificate thumbprint by using Certificate Manager or by using the following PowerShell command:</span></span>
    
       ```PowerShell
       Get-ChildItem -path cert:\LocalMachine\My
       ```

   - <span data-ttu-id="1d99b-152">**安裝目錄：** 這是二進位檔案安裝所在的目錄。</span><span class="sxs-lookup"><span data-stu-id="1d99b-152">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="1d99b-153">您可以使用 [ **流覽 ...]** 按鈕，將其變更為預設值。</span><span class="sxs-lookup"><span data-stu-id="1d99b-153">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="1d99b-154">**AppData 目錄：** 這是用來儲存記錄檔資料夾及其他資料的目錄。</span><span class="sxs-lookup"><span data-stu-id="1d99b-154">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="1d99b-155">您可以從預設值變更它。</span><span class="sxs-lookup"><span data-stu-id="1d99b-155">You may change it from the default.</span></span> <span data-ttu-id="1d99b-156">卸載時不會將其刪除。</span><span class="sxs-lookup"><span data-stu-id="1d99b-156">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="1d99b-157">按一下 **安裝**。</span><span class="sxs-lookup"><span data-stu-id="1d99b-157">Click **Install**.</span></span>
    
<span data-ttu-id="1d99b-158">若要驗證安裝，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="1d99b-158">To validate the installation, perform the following steps:</span></span>
  
1. <span data-ttu-id="1d99b-159">開啟瀏覽器並流覽至 https://localhost: \<service-port\> /healthcheck/</span><span class="sxs-lookup"><span data-stu-id="1d99b-159">Open a browser and navigate to https://localhost:\<service-port\>/healthcheck/</span></span>
    
    <span data-ttu-id="1d99b-160">除非您指定另一個埠) ，否則服務埠預設為 8443 (。</span><span class="sxs-lookup"><span data-stu-id="1d99b-160">By default, the service port is 8443 (unless you specified another port).</span></span>
    
2. <span data-ttu-id="1d99b-161">若要確定監聽器已正確安裝，請尋找下列專案：</span><span class="sxs-lookup"><span data-stu-id="1d99b-161">To ensure the Listener has installed properly, look for the following:</span></span>
    
   - <span data-ttu-id="1d99b-162">如果出現 [healthcheck] 頁面，表示監聽器安裝成功。</span><span class="sxs-lookup"><span data-stu-id="1d99b-162">If the healthcheck page shows up, the Listener installation was successful.</span></span>
    
   - <span data-ttu-id="1d99b-163">如果 KnownServerCount 是1或更高版本，就會建立與 Redis 的連接。</span><span class="sxs-lookup"><span data-stu-id="1d99b-163">If the KnownServerCount is 1 or higher,  the connection to Redis is established.</span></span>
    
   - <span data-ttu-id="1d99b-164">等候幾分鐘後，至少安裝了一個代理程式之後，請檢查 ValuesWritten 計數器是否為增量。</span><span class="sxs-lookup"><span data-stu-id="1d99b-164">After waiting a few minutes, and after at least one Agent has been installed, check to see that the ValuesWritten counter is incrementing.</span></span>
    
### <a name="install-the-website"></a><span data-ttu-id="1d99b-165">安裝網站</span><span class="sxs-lookup"><span data-stu-id="1d99b-165">Install the Website</span></span>

<span data-ttu-id="1d99b-166">執行 StatsManWebSite.msi (隨附于 [商務用 Skype Server，Real-Time 統計資料管理員 (64 位) ](https://www.microsoft.com/en-in/download/details.aspx?id=57518) ，並指定下列專案，以在主機機器上安裝網站：</span><span class="sxs-lookup"><span data-stu-id="1d99b-166">Install the Website on the host machine by running the StatsManWebSite.msi (included with [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)) and specifying the following:</span></span>
  
1. <span data-ttu-id="1d99b-167">請參閱授權合約，如果同意，請選取 [ **我接受授權合約中的條款**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="1d99b-167">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="1d99b-168">在下一個頁面上，指定下列資訊：</span><span class="sxs-lookup"><span data-stu-id="1d99b-168">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="1d99b-169">**服務埠：** 這是網站會接聽的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="1d99b-169">**Service Port:** This is the port number the web site will listen on.</span></span> <span data-ttu-id="1d99b-170">您可以稍後使用 IIS 管理員系結變更。</span><span class="sxs-lookup"><span data-stu-id="1d99b-170">You can change it later by using IIS manager binding.</span></span> <span data-ttu-id="1d99b-171">在安裝期間，將允許透過本機防火牆的埠。</span><span class="sxs-lookup"><span data-stu-id="1d99b-171">During installation, this port will be allowed through the local firewall.</span></span>
    
   - <span data-ttu-id="1d99b-172">**安裝目錄：** 這是二進位檔案安裝所在的目錄。</span><span class="sxs-lookup"><span data-stu-id="1d99b-172">**Install Dir:** This is the directory where the binaries will be installed.</span></span> <span data-ttu-id="1d99b-173">您可以使用 [ **流覽 ...]** 按鈕，將其變更為預設值。</span><span class="sxs-lookup"><span data-stu-id="1d99b-173">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="1d99b-174">**AppData 目錄：** 這是用來儲存記錄檔資料夾及其他資料的目錄。</span><span class="sxs-lookup"><span data-stu-id="1d99b-174">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="1d99b-175">您可以從預設值變更它。</span><span class="sxs-lookup"><span data-stu-id="1d99b-175">You may change it from the default.</span></span> <span data-ttu-id="1d99b-176">卸載時不會將其刪除。</span><span class="sxs-lookup"><span data-stu-id="1d99b-176">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="1d99b-177">按一下 **安裝**。</span><span class="sxs-lookup"><span data-stu-id="1d99b-177">Click **Install**.</span></span>
    
<span data-ttu-id="1d99b-178">若要查看網站，請開啟瀏覽器，然後流覽至： http://localhost ，webport \> /。</span><span class="sxs-lookup"><span data-stu-id="1d99b-178">To view the Website, open a browser, and navigate to: http://localhost,webport\>/.</span></span>
  
<span data-ttu-id="1d99b-179">若只要查看健康資訊，請開啟瀏覽器，然後流覽至： http://localhost: \<webport\> /healthcheck/。</span><span class="sxs-lookup"><span data-stu-id="1d99b-179">To view health information only, open a browser, and navigate to: http://localhost:\<webport\>/healthcheck/.</span></span>
  
<span data-ttu-id="1d99b-180">網頁埠號碼預設為8080。</span><span class="sxs-lookup"><span data-stu-id="1d99b-180">By default, the web port number is 8080.</span></span> <span data-ttu-id="1d99b-181">您可以使用 IIS 管理員變更網站的埠系結。</span><span class="sxs-lookup"><span data-stu-id="1d99b-181">You can change the port binding of the website by using IIS manager.</span></span>
  
<span data-ttu-id="1d99b-182">Web 安裝程式會新增稱為 StatsManWebSiteUsers 的本機安全性群組。</span><span class="sxs-lookup"><span data-stu-id="1d99b-182">The web installer adds a local security group, called StatsManWebSiteUsers.</span></span> <span data-ttu-id="1d99b-183">您可以將帳戶新增至此安全性群組，以授與網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="1d99b-183">You can add accounts to this security group to grant access to the Website.</span></span> 
  
### <a name="install-the-agents"></a><span data-ttu-id="1d99b-184">安裝代理程式</span><span class="sxs-lookup"><span data-stu-id="1d99b-184">Install the Agents</span></span>

<span data-ttu-id="1d99b-185">執行 StatsManPerfAgent.msi 並指定下列專案，以在每個要監視的商務用 Skype 伺服器上安裝代理程式：</span><span class="sxs-lookup"><span data-stu-id="1d99b-185">Install an Agent on each Skype for Business Server that you wish to monitor by running the StatsManPerfAgent.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="1d99b-186">請參閱授權合約，如果同意，請選取 [ **我接受授權合約中的條款**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="1d99b-186">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="1d99b-187">在下一個頁面上，指定下列資訊：</span><span class="sxs-lookup"><span data-stu-id="1d99b-187">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="1d99b-188">**服務密碼：** 這是遠端代理程式將用來驗證監聽器服務的密碼。</span><span class="sxs-lookup"><span data-stu-id="1d99b-188">**Service Password:** This is the password the remote agent will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="1d99b-189">**服務 URI：** 這是攔截器所在的 URI。</span><span class="sxs-lookup"><span data-stu-id="1d99b-189">**Service URI:** This is the URI where the Listener resides.</span></span> <span data-ttu-id="1d99b-190">它應該使用此 https://name:port 格式。</span><span class="sxs-lookup"><span data-stu-id="1d99b-190">It should use the https://name:port format.</span></span>
    
     <span data-ttu-id="1d99b-191">您可以使用 NETBIOS 名稱或 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1d99b-191">You can use a NETBIOS name or a FQDN.</span></span> <span data-ttu-id="1d99b-192">您可以在監聽器服務上使用同時指定為 **主題** 或 **主體替代名稱** 的名稱，但這不是必要條件。</span><span class="sxs-lookup"><span data-stu-id="1d99b-192">You can use the name that is also specified as the **Subject** or **Subject Alternative Names** of the certificate on the Listener service, but this is not a requirement.</span></span>
    
   - <span data-ttu-id="1d99b-193">**服務指紋：** 這是監聽器所使用之 SSL 憑證的指紋。</span><span class="sxs-lookup"><span data-stu-id="1d99b-193">**Service Thumbprint:** This is the thumbprint of the SSL certificate the Listener is using.</span></span> <span data-ttu-id="1d99b-194">代理程式會使用此指紋向監聽器進行驗證。</span><span class="sxs-lookup"><span data-stu-id="1d99b-194">The Agent will use this thumbprint to authenticate to the Listener.</span></span> <span data-ttu-id="1d99b-195"> (因為可能使用自我簽署的憑證，所以不會執行完整的憑證驗證。 ) </span><span class="sxs-lookup"><span data-stu-id="1d99b-195">(It will not do full certificate validation because it is possible to use self-signed certificates.)</span></span>
    
   - <span data-ttu-id="1d99b-196">**安裝目錄：** 這是二進位檔案安裝所在的目錄。</span><span class="sxs-lookup"><span data-stu-id="1d99b-196">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="1d99b-197">您可以使用 [ **流覽 ...]** 按鈕，將其變更為預設值。</span><span class="sxs-lookup"><span data-stu-id="1d99b-197">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="1d99b-198">**AppData 目錄：** 這是儲存 Logs 資料夾及加密 password.txt 檔案的目錄。</span><span class="sxs-lookup"><span data-stu-id="1d99b-198">**AppData Dir:** This is the directory where the Logs folder and the encrypted password.txt file will be stored.</span></span> <span data-ttu-id="1d99b-199">您可能會多謝從預設值變更。</span><span class="sxs-lookup"><span data-stu-id="1d99b-199">You may thanks change it from the default.</span></span> <span data-ttu-id="1d99b-200">卸載時不會將其刪除。</span><span class="sxs-lookup"><span data-stu-id="1d99b-200">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="1d99b-201">按一下 **安裝**。</span><span class="sxs-lookup"><span data-stu-id="1d99b-201">Click **Install**.</span></span>
    
<span data-ttu-id="1d99b-202">若要在許多機器上安裝代理程式，您可能想要在自動模式中執行這項作業。</span><span class="sxs-lookup"><span data-stu-id="1d99b-202">If you are installing an Agent on numerous machines, you will probably want to do this in unattended mode.</span></span> <span data-ttu-id="1d99b-203">例如：</span><span class="sxs-lookup"><span data-stu-id="1d99b-203">For example:</span></span> 
  
```console
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a><span data-ttu-id="1d99b-204">匯入拓撲</span><span class="sxs-lookup"><span data-stu-id="1d99b-204">Import the topology</span></span>
<span data-ttu-id="1d99b-205"><a name="BKMK_ImportTopology"> </a></span><span class="sxs-lookup"><span data-stu-id="1d99b-205"><a name="BKMK_ImportTopology"> </a></span></span>

<span data-ttu-id="1d99b-206">在安裝並執行統計資料管理員之後，您必須匯入商務用 Skype 伺服器拓撲，使統計資料管理員知道每一部伺服器的網站、集區和角色。</span><span class="sxs-lookup"><span data-stu-id="1d99b-206">After Statistics Manager is installed and running, you need to import the Skype for Business Server topology so that Statistics Manager knows the Site, Pool, and Role of each server.</span></span> <span data-ttu-id="1d99b-207">若要匯入商務用 Skype 伺服器拓撲，您將會使用 [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) Cmdlet，以取得組織中所使用之每個集區的相關資訊，然後將此資訊匯入至統計資料管理員。</span><span class="sxs-lookup"><span data-stu-id="1d99b-207">To import your Skype for Business Server topology, you will use the [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) cmdlet to retrieve information about each pool in use in your organization, then import this information into Statistics Manager.</span></span>
  
<span data-ttu-id="1d99b-208">若要匯入商務用 Skype 伺服器拓撲，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="1d99b-208">To import the Skype for Business Server topology, follow these steps:</span></span>
  
1. <span data-ttu-id="1d99b-209">在具有商務用 Skype 伺服器的主機上 PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="1d99b-209">On a host that has the Skype for Business Server PowerShell cmdlets:</span></span>
    
    <span data-ttu-id="1d99b-210">a.</span><span class="sxs-lookup"><span data-stu-id="1d99b-210">a.</span></span> <span data-ttu-id="1d99b-211">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="1d99b-211">Run the following command:</span></span> 
    
   ```PowerShell
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    <span data-ttu-id="1d99b-212">b.</span><span class="sxs-lookup"><span data-stu-id="1d99b-212">b.</span></span> <span data-ttu-id="1d99b-213">將 "mypoolinfo.xml" 檔複製到執行監聽器的伺服器。</span><span class="sxs-lookup"><span data-stu-id="1d99b-213">Copy the "mypoolinfo.xml" file to the server that runs the Listener.</span></span>
    
2. <span data-ttu-id="1d99b-214">在執行攔截器的主機上：</span><span class="sxs-lookup"><span data-stu-id="1d99b-214">On the host that runs the Listener:</span></span>
    
   <span data-ttu-id="1d99b-215">a.</span><span class="sxs-lookup"><span data-stu-id="1d99b-215">a.</span></span> <span data-ttu-id="1d99b-216">執行 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="1d99b-216">Run PowerShell.</span></span>
    
   <span data-ttu-id="1d99b-217">b.</span><span class="sxs-lookup"><span data-stu-id="1d99b-217">b.</span></span> <span data-ttu-id="1d99b-218">流覽至安裝攔截器的目錄。</span><span class="sxs-lookup"><span data-stu-id="1d99b-218">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="1d99b-219">預設值為：</span><span class="sxs-lookup"><span data-stu-id="1d99b-219">The default is:</span></span> 
    
   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. <span data-ttu-id="1d99b-220">若要確認要新增及更新的伺服器，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="1d99b-220">To confirm which servers are being added and updated, run the following command:</span></span>
    
   ```console
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

<span data-ttu-id="1d99b-221">下列命令可讓您查看所有選項：</span><span class="sxs-lookup"><span data-stu-id="1d99b-221">The following command enables you to view all options:</span></span>
  
```powershell
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

<span data-ttu-id="1d99b-222">若要查看您目前匯入的伺服器資訊，請執行下列腳本：</span><span class="sxs-lookup"><span data-stu-id="1d99b-222">To see your currently imported server information, run the following script:</span></span> 
  
```powershell
.\Get-StatsManServerInfo.ps1
```

<span data-ttu-id="1d99b-223">如果您想要監視不在商務用 Skype 伺服器拓撲中的伺服器--Exchange 伺服器，您可以在執行監聽器的主機上進行單一伺服器匯入。</span><span class="sxs-lookup"><span data-stu-id="1d99b-223">If you would like to monitor servers that are not in your Skype for Business Server topology--an Exchange Server, for example--you can do a single-server import on the host that runs the Listener.</span></span> <span data-ttu-id="1d99b-224">若要進行單一伺服器匯入，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="1d99b-224">To do a single-server import, follow these steps:</span></span>
  
1. <span data-ttu-id="1d99b-225">流覽至安裝攔截器的目錄。</span><span class="sxs-lookup"><span data-stu-id="1d99b-225">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="1d99b-226">預設值為：</span><span class="sxs-lookup"><span data-stu-id="1d99b-226">The default is:</span></span> 
    
   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. <span data-ttu-id="1d99b-227">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="1d99b-227">Run the following command:</span></span>
    
   ```powershell
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a><span data-ttu-id="1d99b-228">疑難排解您的部署</span><span class="sxs-lookup"><span data-stu-id="1d99b-228">Troubleshoot your deployment</span></span>
<span data-ttu-id="1d99b-229"><a name="BKMK_Troubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="1d99b-229"><a name="BKMK_Troubleshoot"> </a></span></span>

<span data-ttu-id="1d99b-230">若代理程式無法啟動，請檢查下列事項：</span><span class="sxs-lookup"><span data-stu-id="1d99b-230">If an Agent fails to start, check for the following:</span></span> 
  
- <span data-ttu-id="1d99b-231">代理程式是在統計資料管理員中註冊嗎？</span><span class="sxs-lookup"><span data-stu-id="1d99b-231">Is the agent registered in Statistics Manager?</span></span>
    
    1. <span data-ttu-id="1d99b-232">請確認您已遵循匯入拓撲的指示。</span><span class="sxs-lookup"><span data-stu-id="1d99b-232">Make sure you followed the instructions for importing the topology.</span></span> <span data-ttu-id="1d99b-233">請參閱匯 [入拓撲](deploy.md#BKMK_ImportTopology)。</span><span class="sxs-lookup"><span data-stu-id="1d99b-233">See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
        
    2. <span data-ttu-id="1d99b-234">如果代理程式位於拓撲中未列出的伺服器上 (例如，SQL AlwaysOn 叢集中的節點) ，您必須遵循匯 [入拓撲](deploy.md#BKMK_ImportTopology)中的指示手動新增代理程式。</span><span class="sxs-lookup"><span data-stu-id="1d99b-234">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
- <span data-ttu-id="1d99b-235">代理程式是否可以與監聽器聯繫？</span><span class="sxs-lookup"><span data-stu-id="1d99b-235">Can the Agent contact the Listener?</span></span>
    
    1. <span data-ttu-id="1d99b-236">請確定監聽器服務正在執行中。</span><span class="sxs-lookup"><span data-stu-id="1d99b-236">Make sure the Listener service is running.</span></span> 
        
        <span data-ttu-id="1d99b-237">若未執行，請確定 Redis 正在執行，然後嘗試重新開機監聽器。</span><span class="sxs-lookup"><span data-stu-id="1d99b-237">If it is not running, make sure Redis is running, and then try to restart the Listener.</span></span>
        
    2. <span data-ttu-id="1d99b-238">請確定監聽器服務已開啟埠，且代理人電腦可以與埠通訊。</span><span class="sxs-lookup"><span data-stu-id="1d99b-238">Make sure the port is open to the Listener service, and that the Agent computer can communicate with the port.</span></span>
    
- <span data-ttu-id="1d99b-239">若要確定統計資料管理員正在收集資料，您可以檢查 CSV 檔案，如下所示。</span><span class="sxs-lookup"><span data-stu-id="1d99b-239">To ensure that Statistics Manager is collecting data, you can check the CSV file as follows.</span></span> 
    
    <span data-ttu-id="1d99b-240">下列命令會檢索計數器儲存名稱：</span><span class="sxs-lookup"><span data-stu-id="1d99b-240">The following command retrieves the counter storage names:</span></span> 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    <span data-ttu-id="1d99b-241">下一個命令會為指定的計數器檢索值：</span><span class="sxs-lookup"><span data-stu-id="1d99b-241">The next command retrieves the values for the specified counters:</span></span> 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

<span data-ttu-id="1d99b-242">如需您可能會在應用程式事件記錄檔中看到之所有事件的詳細資訊，請參閱 [統計資料管理員以取得商務用 Skype 伺服器的疑難排解](troubleshoot.md)。</span><span class="sxs-lookup"><span data-stu-id="1d99b-242">For information about all the events you might see in the application event log, see [Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md).</span></span>
  
## <a name="create-a-self-signed-certificate"></a><span data-ttu-id="1d99b-243">建立自我簽署憑證</span><span class="sxs-lookup"><span data-stu-id="1d99b-243">Create a self-signed certificate</span></span>
<span data-ttu-id="1d99b-244"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="1d99b-244"><a name="BKMK_SelfCert"> </a></span></span>

<span data-ttu-id="1d99b-245">Microsoft 強烈建議您使用受信任的憑證授權單位單位所簽署的憑證。</span><span class="sxs-lookup"><span data-stu-id="1d99b-245">Microsoft strongly recommends that you use a certificate signed by a trusted certificate authority.</span></span> <span data-ttu-id="1d99b-246">不過，如果您想要使用自我簽署憑證以進行測試，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="1d99b-246">However, if you want to use a self-signed certificate for testing purposes, do the following:</span></span> 
  
1. <span data-ttu-id="1d99b-247">從 PowerShell 主控台，以系統管理員身分登入時，輸入下列專案：</span><span class="sxs-lookup"><span data-stu-id="1d99b-247">From a PowerShell console while logged on as Administrator, type the following:</span></span>
    
   ```powershell
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. <span data-ttu-id="1d99b-248">類型  `certlm.msc` 。</span><span class="sxs-lookup"><span data-stu-id="1d99b-248">Type  `certlm.msc`.</span></span> <span data-ttu-id="1d99b-249">這會開啟本機電腦的憑證管理員。</span><span class="sxs-lookup"><span data-stu-id="1d99b-249">This will open the Certificate Manager for the local machine.</span></span>
    
3. <span data-ttu-id="1d99b-250">流覽至 [ **個人**]，然後開啟 [ **憑證**]。</span><span class="sxs-lookup"><span data-stu-id="1d99b-250">Navigate to **Personal**, and then open **Certificates**.</span></span>
    
4. <span data-ttu-id="1d99b-251">以滑鼠右鍵按一下 [ **StatsManListener- \> 所有工作- \> 管理私密金鑰]。**</span><span class="sxs-lookup"><span data-stu-id="1d99b-251">Right click on **StatsManListener-\>All Tasks-\>Manage Private Keys…**</span></span>
    
5. <span data-ttu-id="1d99b-252">按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="1d99b-252">Click **Add**.</span></span>
    
6. <span data-ttu-id="1d99b-253">在 [ **輸入物件名稱來選取** ] 方塊中，輸入下列專案：網路服務</span><span class="sxs-lookup"><span data-stu-id="1d99b-253">In the **Enter the object names to select** box, type the following: Network Service</span></span>
    
7. <span data-ttu-id="1d99b-254">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="1d99b-254">Click **OK**.</span></span>
    
8. <span data-ttu-id="1d99b-255">在 [ **完全控制**] 底下，取消勾選 [ **允許** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1d99b-255">Under **Full Control**, un-check the **Allow** check box.</span></span> <span data-ttu-id="1d99b-256">只需要 (讀取權。 ) </span><span class="sxs-lookup"><span data-stu-id="1d99b-256">(Only Read access is necessary.)</span></span>
    
9. <span data-ttu-id="1d99b-257">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="1d99b-257">Click **OK**.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="1d99b-258">相關資訊</span><span class="sxs-lookup"><span data-stu-id="1d99b-258">For more information</span></span>
<span data-ttu-id="1d99b-259"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="1d99b-259"><a name="BKMK_SelfCert"> </a></span></span>

<span data-ttu-id="1d99b-260">如需詳細資訊，請參閱下列各主題：</span><span class="sxs-lookup"><span data-stu-id="1d99b-260">For more information, see the following:</span></span>
  
- [<span data-ttu-id="1d99b-261">商務用 Skype Server 統計資料的規劃</span><span class="sxs-lookup"><span data-stu-id="1d99b-261">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="1d99b-262">升級商務用 Skype Server 統計資料</span><span class="sxs-lookup"><span data-stu-id="1d99b-262">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
    
- <span data-ttu-id="1d99b-263">[商務用 Skype Server β的統計資料管理員疑難排解](troubleshoot.md)</span><span class="sxs-lookup"><span data-stu-id="1d99b-263">[Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md) ß</span></span>
