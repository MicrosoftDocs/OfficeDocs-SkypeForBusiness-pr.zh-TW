---
title: 疑難排解您的 Cloud Connector 部署
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: 針對您的雲端連接器版本部署進行疑難排解。
ms.openlocfilehash: 3edc67d5887c21543e4cbb01a6057a0c657e95e3
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002073"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="d1a6f-103">疑難排解您的 Cloud Connector 部署</span><span class="sxs-lookup"><span data-stu-id="d1a6f-103">Troubleshoot your Cloud Connector deployment</span></span>
 
<span data-ttu-id="d1a6f-104">針對您的雲端連接器版本部署進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-104">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="d1a6f-105">本主題將說明雲端連接器版本部署常見問題的解決方案。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-105">This topic describes solutions to common issues with Cloud Connector Edition deployments.</span></span> <span data-ttu-id="d1a6f-106">如果您在撥打電話給公眾的交換電話網絡（PSTN）中遇到問題，您可以依照本主題中所述的解決方案來調查。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-106">If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="d1a6f-107">雲端連接器提供可自動解決某些問題的內建機制。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-107">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="d1a6f-108">自動偵測程式會尋找雲端連接器裝置的潛在問題，如有可能，您可以採取修正動作來解決這些問題，而不需管理員干預。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-108">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="d1a6f-109">偵測處理常式的運作方式如下：</span><span class="sxs-lookup"><span data-stu-id="d1a6f-109">The detection process works as follows:</span></span>
  
- <span data-ttu-id="d1a6f-110">**偵測順序：** 雲端連接器管理服務會每隔60秒執行一個處理常式，以偵測裝置是否已關閉。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-110">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="d1a6f-111">在雲端連接器版本2.0 及更新版本中，檢測程式會使用商務用 Skype 的 [商務用 Skype] 交換器來建立雲端連接器電腦的 PowerShell 連線;針對2.0 之前的版本，檢測程式會使用雲端連接器管理開關。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-111">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d1a6f-112">若要讓自動復原成功，主機和虛擬機器之間必須有通過主機網路交換器的網路連線。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-112">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="d1a6f-113">請務必檢查網路連線，以確保自動偵測和復原能夠成功完成。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-113">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="d1a6f-114">**監控：** 下列服務在雲端連接器版本2.0 和更新版本中受到監視：</span><span class="sxs-lookup"><span data-stu-id="d1a6f-114">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="d1a6f-115">虛擬機器未連線至雲端連接器公司或網際網路虛擬交換器</span><span class="sxs-lookup"><span data-stu-id="d1a6f-115">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="d1a6f-116">虛擬機器處於 [已儲存] 或 [已停止] 狀態</span><span class="sxs-lookup"><span data-stu-id="d1a6f-116">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="d1a6f-117">中央管理伺服器服務：複本、主要</span><span class="sxs-lookup"><span data-stu-id="d1a6f-117">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="d1a6f-118">中繼伺服器服務： REPLICA、RTCSRV 和 MEDSVC</span><span class="sxs-lookup"><span data-stu-id="d1a6f-118">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="d1a6f-119">Edge 伺服器服務： REPLICA、RTCSRV、RTCDATAPROXY、RTCMRAUTH、RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="d1a6f-119">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="d1a6f-120">在 Edge 伺服器上停用針對 CS RTCSRV 的入站防火牆規則，在轉送伺服器上的 CS RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="d1a6f-120">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="d1a6f-121">在雲端連接器版本1.4.2 中，只會監視下列服務：</span><span class="sxs-lookup"><span data-stu-id="d1a6f-121">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="d1a6f-122">中繼伺服器服務： RTCSRV 和 MEDSVC</span><span class="sxs-lookup"><span data-stu-id="d1a6f-122">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="d1a6f-123">Edge 伺服器服務： RTCSRV</span><span class="sxs-lookup"><span data-stu-id="d1a6f-123">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="d1a6f-124">**修復程式：** 如果任何受監視的服務已關閉，裝置會標示為關閉狀態，而且服務會停止並標示手動，直到所有問題都能解決為止。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-124">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="d1a6f-125">這會防止呼叫路由至可能會導致呼叫失敗的裝置。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-125">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="d1a6f-126">雲端連接器管理服務將會重試自動復原，如下所示</span><span class="sxs-lookup"><span data-stu-id="d1a6f-126">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="d1a6f-127">初始重試間隔是每十秒，最大間隔時間為1小時。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-127">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="d1a6f-128">在前三次的復原嘗試中，間隔時間為10秒。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-128">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="d1a6f-129">從第四個重試開始，間隔時間會增加前一個間隔時間的兩倍。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-129">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="d1a6f-130">例如，第四次重試會在20秒內執行，在40秒後會發生5次，依此類推。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-130">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="d1a6f-131">當達到一個小時的最大間隔時間時，每小時都會繼續進行一次的重試。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-131">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="d1a6f-132">當復原成功時，間隔和重試計數會設定為其初始值。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-132">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="d1a6f-133">如果重新開機管理服務，間隔和重試計數會重設為其初始值。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-133">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="d1a6f-134">疑難排解</span><span class="sxs-lookup"><span data-stu-id="d1a6f-134">Troubleshooting</span></span>

<span data-ttu-id="d1a6f-135">以下是經常遇到問題的解決方案：</span><span class="sxs-lookup"><span data-stu-id="d1a6f-135">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="d1a6f-136">**問題：執行部署腳本時，部署失敗或停止回應。登入每個 VM 之後，該 IP 位址對於管理/內部/外部 NIC 而言遺失或不正確。**</span><span class="sxs-lookup"><span data-stu-id="d1a6f-136">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="d1a6f-137">**解決方式：** 這個問題無法自動解決。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-137">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="d1a6f-138">Nic 無法在執行時新增到 Vm 中。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-138">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="d1a6f-139">請在 hyper-v manager 中關閉並移除這些 Vm，然後執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="d1a6f-139">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="d1a6f-140">**問題：已安裝 Active Directory 伺服器與林之後，CMS 伺服器和/或中繼伺服器無法正確加入網域。**</span><span class="sxs-lookup"><span data-stu-id="d1a6f-140">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="d1a6f-141">**解決方式：** 若要解決此問題，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="d1a6f-141">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="d1a6f-142">登入 Active Directory 伺服器並確認已正確建立網域。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-142">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="d1a6f-143">登入 CMS/轉送伺服器，並確認已指派 [公司網路 NIC] 的有效 IP 位址，且有效的靜態 IP 和 DNS 已設定為 AD 伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-143">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="d1a6f-144">登入 CMS/轉送伺服器，然後開啟命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-144">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="d1a6f-145">請確定您可以 ping Active Directory 伺服器的 FQDN 和 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-145">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="d1a6f-146">如果您無法這樣做，可能是 IP 位址發生衝突。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-146">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="d1a6f-147">請嘗試為 Active Directory 指派新的 IP，並據此更新 CMS/轉送伺服器上的 DNS。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-147">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="d1a6f-148">**問題：您收到下列錯誤訊息：「移除-VMSwitch：移除虛擬乙太網路交換器時失敗。無法刪除虛擬交換器 [雲端連接器管理開關]，因為它正由執行虛擬機器或指派給子池。」**</span><span class="sxs-lookup"><span data-stu-id="d1a6f-148">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="d1a6f-149">**解決方式：** 在部署之後，不會刪除「雲端連接器管理開關」。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-149">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="d1a6f-150">如果您遇到此錯誤，請移至 Hyper-v 管理器並確認沒有虛擬機器仍與其連線。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-150">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="d1a6f-151">如果有虛擬機器仍處於線上狀態，請將它們斷開並刪除管理開關。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-151">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="d1a6f-152">如果管理開關仍無法刪除，請重新開機主機伺服器，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-152">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="d1a6f-153">**問題：您收到下列錯誤訊息：「服務 RTCMRAUTH 無法啟動。請檢查以確定該服務未停用。**</span><span class="sxs-lookup"><span data-stu-id="d1a6f-153">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d1a6f-154">這個問題只適用于1.4.2 之前的雲端連接器版本。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-154">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="d1a6f-155">啟動失敗也可能是因為這個前端伺服器先前已失敗（使用電腦容錯移轉）。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-155">The failure to start could also be because this Front End server was previously failed over (using computer fail over).</span></span> <span data-ttu-id="d1a6f-156">如果是這種情況，請喚醒呼叫返回（使用電腦的容錯回復）。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-156">If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="d1a6f-157">**解決方式：** 當 Edge 伺服器不根信任 CA 憑證或中間 CA 憑證時，在 Edge 伺服器上就會發生此問題。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-157">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server.</span></span> <span data-ttu-id="d1a6f-158">即使可匯入外部憑證，但已中斷憑證連結。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-158">Even if the external certificate can be imported but the certificate chain is broken.</span></span> <span data-ttu-id="d1a6f-159">在這種情況下，RTCMRAUTH 和/或 RTCSRV 服務無法啟動。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-159">Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="d1a6f-160">請將外部憑證的根 CA 憑證和所有中間 CA 憑證，手動匯入邊緣伺服器，然後重新開機 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-160">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server.</span></span> <span data-ttu-id="d1a6f-161">當您看到在 Edge 伺服器上開始的 RTCMRAUTH 和 RTCSRV 服務之後，請回到您的主機伺服器，以系統管理員身分啟動 PowerShell 主控台，然後執行下列 Cmdlet 以切換到新的部署：</span><span class="sxs-lookup"><span data-stu-id="d1a6f-161">After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="d1a6f-162">**問題：主機伺服器已在已套用 Windows 更新時重新開機，且由伺服器服務的呼叫失敗。**</span><span class="sxs-lookup"><span data-stu-id="d1a6f-162">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="d1a6f-163">**解決方式：** 如果您部署了高可用性環境，Microsoft 會提供一個 Cmdlet，在您手動檢查並安裝 Windows 更新時，協助您將一台主機（部署實例）移入或移出目前拓撲。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-163">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually.</span></span> <span data-ttu-id="d1a6f-164">使用下列步驟來完成此動作：</span><span class="sxs-lookup"><span data-stu-id="d1a6f-164">Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="d1a6f-165">在主機伺服器上，以系統管理員身分啟動 PowerShell 主控台，然後執行：</span><span class="sxs-lookup"><span data-stu-id="d1a6f-165">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

2. <span data-ttu-id="d1a6f-166">檢查是否有任何可用的更新並安裝。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-166">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="d1a6f-167">在 PowerShell 主控台中，執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="d1a6f-167">In the PowerShell console, run the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    <span data-ttu-id="d1a6f-168">**問題：使用 PSTN 號碼從商務用 Skype 用戶端撥打電話時，無法邀請另一個 PSTN 號碼將呼叫升級到會議。**</span><span class="sxs-lookup"><span data-stu-id="d1a6f-168">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="d1a6f-169">**解決方式：** 若要解決此問題，請參閱[設定線上混合式轉送轉送伺服器設定](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer)。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-169">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="d1a6f-170">**問題：當您安裝 Active Directory server 時，系統會顯示關於 Windows Update 的警告訊息-「未啟用 Windows 自動更新。若要確保您新近安裝的角色或功能自動更新，請開啟 [Windows Update]。**</span><span class="sxs-lookup"><span data-stu-id="d1a6f-170">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="d1a6f-171">**解決方式：** 使用商務用 Skype 租使用者管理員認證啟動租使用者遠端 PowerShell 會話，然後執行下列 Cmdlet 來檢查網站的_EnableAutoUpdate_設定：</span><span class="sxs-lookup"><span data-stu-id="d1a6f-171">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="d1a6f-172">如果_EnableAutoUpdate_設定為**True**，您可以放心地忽略此警告訊息，因為 CCEManagement 服務將會處理針對虛擬機器與主機伺服器的下載與安裝 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-172">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="d1a6f-173">如果_EnableAutoUpdate_設定為**False**，請執行下列 Cmdlet 將它設定為**True**。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-173">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="d1a6f-174">或者，您也可以手動檢查並安裝更新。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-174">Alternatively, you can manually check for and install updates.</span></span> <span data-ttu-id="d1a6f-175">請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-175">See the next section.</span></span>
    
- <span data-ttu-id="d1a6f-176">**問題：您收到錯誤訊息：無法註冊裝置，因為您目前的輸入/ \<配置\> SiteName \<或\> APPLIANCENAME \<或轉送伺服器\> FQDN \<或轉送伺服器 IP\>位址與現有的裝置發生衝突。移除衝突裝置或更新您的輸入/配置資訊，然後再次註冊。' 在執行 Register CcAppliance 時，將目前裝置註冊至線上。**</span><span class="sxs-lookup"><span data-stu-id="d1a6f-176">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="d1a6f-177">**解決方式：**\< \>ApplianceName 的\<值，中繼伺服器 FQDN\>和\<轉送伺服器 IP 位址\>必須是唯一的，且僅適用于一個裝置註冊。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-177">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="d1a6f-178">根據預設， \<ApplianceName\>來自于主機名稱。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-178">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="d1a6f-179">\<在配置 ini\>檔案\<中定義的仲介\>伺服器 FQDN 和轉送伺服器 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-179">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="d1a6f-180">例如，使用（ApplianceName = MyserverNew，中繼伺服器 FQDN = ms. contoso，轉送伺服器 IP 位址 = 10.10.10.10）登錄到 SiteName = [我的網站] （ApplianceName = Myserver，轉送伺服器 FQDN =ms.contoso.com、採集轉送伺服器 IP 位址 = 10.10.10.10），就會發生衝突。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-180">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="d1a6f-181">首先，請在 ApplianceRoot 目錄區段中查看您的 CloudConnector 檔案。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-181">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="d1a6f-182">您將會\<在\>檔案\<中取得網站\>伺服器\<FQDN 和轉送伺服器\> IP 位址值。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-182">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="d1a6f-183">\<ApplianceName\>是您的主機伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-183">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="d1a6f-184">接著，使用您的商務用 Skype 租使用者管理員認證啟動承租人遠端 PowerShell，然後執行下列 Cmdlet 來檢查已註冊的裝置。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-184">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="d1a6f-185">在識別任何衝突之後，您可以使用與已註冊裝置相符的資訊來更新 CloudConnector 檔案，或登出現有裝置以解決衝突。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-185">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- <span data-ttu-id="d1a6f-186">**問題：如果在主機上執行已部署的裝置，則 CcRunningVersion Cmdlet 會傳回空值。**</span><span class="sxs-lookup"><span data-stu-id="d1a6f-186">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
  <span data-ttu-id="d1a6f-187">**解決方式：** 當您從1.3.4 或1.3.8 升級至1.4.1 時，可能會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-187">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1.</span></span> <span data-ttu-id="d1a6f-188">在使用 .msi 安裝版本1.4.1 之後，您必須先執行`Register-CcAppliance` ，才能執行任何其他 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-188">After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet.</span></span> <span data-ttu-id="d1a6f-189">`Register-CcAppliance`會將 module 檔案從%UserProfile%\CloudConnector 遷移至%ProgramData%\CloudConnector。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-189">`Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector.</span></span> <span data-ttu-id="d1a6f-190">如果您遺漏了這個檔案，將會在%ProgramData%\CloudConnector 資料夾中建立新的 module .ini，並取代1.3.4 或1.3.8 的運行/備份版本資訊。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-190">If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
  <span data-ttu-id="d1a6f-191">比較%UserProfile%\CloudConnector 和%ProgramData%\CloudConnector 資料夾中的 boot.ini 檔案。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-191">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="d1a6f-192">如果有差異，請在%ProgramData%\CloudConnector 中刪除 module 檔案，然後重新`Register-CcAppliance`執行。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-192">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="d1a6f-193">您也可以手動修改檔案至正確的執行與備份版本。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-193">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="d1a6f-194">**問題：在您執行 CcVersion Cmdlet 以切換到不同于目前腳本版本的舊版版本之後，此舊版版本沒有高可用性支援。**</span><span class="sxs-lookup"><span data-stu-id="d1a6f-194">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="d1a6f-195">**解決方式：** 例如，您已從1.4.1 升級到1.4.2。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-195">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="d1a6f-196">您目前的腳本版本（可透過執行來決定`Get-CcVersion`）和執行中的版本，都可以透過執行兩`Get-CcRunningVersion`個1.4.2 來判斷。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-196">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="d1a6f-197">此時，如果您執行`Switch-CcVersion`以將執行中的版本切換回1.4.1，就不會有此舊版版本的高可用性支援。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-197">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="d1a6f-198">若要取得完整的高可用性支援，請切換回 [1.4.2]，讓執行的版本與腳本版本相同。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-198">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same.</span></span> <span data-ttu-id="d1a6f-199">如果您的1.4.2 部署遇到問題，請儘快卸載並重新安裝。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-199">If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="d1a6f-200">**問題：頒發給中央管理商店、中繼伺服器和 Edge 伺服器的憑證授權單位憑證或內部憑證接近到期或遭到破壞。**</span><span class="sxs-lookup"><span data-stu-id="d1a6f-200">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="d1a6f-201">**解決方式：** 商務用 Skype 憑證授權單位憑證有效期為五年。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-201">**Resolution:** Skype for Business certification authority certificates are valid for five years.</span></span> <span data-ttu-id="d1a6f-202">已頒發給中央管理商店、中繼伺服器和 Edge 伺服器的內部憑證有效期為兩年。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-202">Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d1a6f-203">在雲端連接器版本2.0 及更新版本中，CcServerCertificate Cmdlet 已變更為 Update-CcServerCertificate，而續租-CcCACertificate Cmdlet 已變更為 Update-CcCACertificate。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-203">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="d1a6f-204">如果將內部憑證頒發給中央管理儲存體、中繼伺服器和 Edge 伺服器的到期或遭到破壞，請執行 CcServerCertificate 或更新 CcServerCertificate Cmdlet 來更新您的憑證。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-204">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="d1a6f-205">如果憑證授權單位憑證即將到期，請執行 CcCACertificate 或更新 CcCACertificate Cmdlet 來更新您的憑證。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-205">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="d1a6f-206">**如果憑證授權單位憑證遭到破壞，且網站中只有一個裝置，請**執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="d1a6f-206">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="d1a6f-207">執行輸入 CcUpdate Cmdlet 來排出服務，並將裝置置於 [維護] 模式。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-207">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. <span data-ttu-id="d1a6f-208">執行下列 Cmdlet 來重設及建立新的憑證授權單位憑證及所有內部伺服器憑證：</span><span class="sxs-lookup"><span data-stu-id="d1a6f-208">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="d1a6f-209">在2.0 之前的雲端連接器版本：</span><span class="sxs-lookup"><span data-stu-id="d1a6f-209">For Cloud Connector releases before 2.0:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="d1a6f-210">或者，適用于雲端連接器版本2.0 及更新版本：</span><span class="sxs-lookup"><span data-stu-id="d1a6f-210">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. <span data-ttu-id="d1a6f-211">如果在閘道與中繼伺服器之間使用 TLS，請從裝置執行 Export CcRootCertificate Cmdlet，然後將匯出的憑證安裝至 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-211">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from the appliance, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="d1a6f-212">您可能也需要在閘道上重新頒發證書。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-212">You may also be required to re-issue the certificate on your gateway.</span></span>

   ```powershell
   Export-CcRootCertificate
   ```

4. <span data-ttu-id="d1a6f-213">執行 CcUpdate Cmdlet 以啟動服務並結束 [維護] 模式。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-213">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span>

   ```powershell
   Exit-CcUpdate
   ```


    <span data-ttu-id="d1a6f-214">**如果憑證授權單位憑證遭到破壞，且網站中有多個裝置，請**在網站中的每個裝置上執行下列連續步驟。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-214">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="d1a6f-215">Microsoft 建議您在非高峰使用時間執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-215">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
1. <span data-ttu-id="d1a6f-216">在第一個裝置上，執行 CcCertificationAuthorityFile Cmdlet，以清除\<SiteRoot\>目錄中的 CA 備份檔案。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-216">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. <span data-ttu-id="d1a6f-217">執行輸入 CcUpdate Cmdlet 來排出服務，並將每個裝置置於維護模式。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-217">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>

     ```powershell
     Enter-CcUpdate
     ```
    
3. <span data-ttu-id="d1a6f-218">在第一個裝置上，執行下列 Cmdlet 來重設及建立新的憑證授權單位憑證及所有內部伺服器憑證：</span><span class="sxs-lookup"><span data-stu-id="d1a6f-218">On the first appliance, run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
     <span data-ttu-id="d1a6f-219">在2.0 之前的雲端連接器版本：</span><span class="sxs-lookup"><span data-stu-id="d1a6f-219">For Cloud Connector releases before 2.0:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     <span data-ttu-id="d1a6f-220">或者，適用于雲端連接器版本2.0 及更新版本：</span><span class="sxs-lookup"><span data-stu-id="d1a6f-220">Or for Cloud Connector release 2.0 and later:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. <span data-ttu-id="d1a6f-221">在第一個裝置上，執行下列 Cmdlet，將 CA 檔案備份到\<SiteRoot\>資料夾。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-221">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span>
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. <span data-ttu-id="d1a6f-222">在所有其他裝置的同一網站中，執行下列命令以使用 CA 備份檔案，讓裝置全都使用相同的根憑證，然後要求新的憑證。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-222">On all other appliance's in the same site, run the following commands to consume the CA backup files, so that the appliances all use the same root certificate, and then request new certificates.</span></span> 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. <span data-ttu-id="d1a6f-223">如果在閘道與中繼伺服器之間使用 TLS，請從網站中的任何裝置執行 Export CcRootCertificate Cmdlet，然後將匯出的憑證安裝至 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-223">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="d1a6f-224">您可能也需要在閘道上重新頒發證書。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-224">You may also be required to re-issue the certificate on your gateway.</span></span>
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. <span data-ttu-id="d1a6f-225">執行 CcUpdate Cmdlet 以啟動服務並結束 [維護] 模式。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-225">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- <span data-ttu-id="d1a6f-226">**問題：您在雲端連接器管理服務記錄中收到下列錯誤訊息，"C:\Program Files\Skype for Business 雲端連接器 Edition\ManagementService\CceManagementService.log"： CceService 錯誤：0：將狀態報表給 online 時出現意外的例外狀況：系統管理。 CmdletInvocationException：登入使用者全域租\<使用者系統管理員\>失敗。請建立新的認證物件，確認您使用的是正確的使用者名稱和密碼。---\>**</span><span class="sxs-lookup"><span data-stu-id="d1a6f-226">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="d1a6f-227">**解決方式：** Office 365 全域租使用者管理員認證已在註冊雲端連接器裝置之後進行變更。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-227">**Resolution:** The Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="d1a6f-228">若要在雲端連接器裝置上更新本機儲存的認證，請從主機裝置上的系統管理員 PowerShell 執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="d1a6f-228">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- <span data-ttu-id="d1a6f-229">**問題：在您針對部署所用的主機伺服器帳戶變更密碼之後，您會收到下列錯誤訊息：「ConvertTo-SecureString：不能在指定狀態中使用的金鑰」。商務用%ProgramFiles%\Skype 中的雲端連接器Edition\ManagementService\CceManagementService.log 或執行 CcCredential Cmdlet 時的狀態。**</span><span class="sxs-lookup"><span data-stu-id="d1a6f-229">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="d1a6f-230">**解決方式：** 所有雲端連接器認證都儲存在下列檔案中： "%SystemDrive%\Programdata\Cloudconnector\credentials。\<CurrentUser\>.xml "。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-230">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="d1a6f-231">當主機伺服器上的密碼變更時，您將需要更新本機儲存的認證。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-231">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="d1a6f-232">**如果您執行的是雲端連接器版本1.4.2，請**依照下列步驟重新產生所有雲端連接器密碼：</span><span class="sxs-lookup"><span data-stu-id="d1a6f-232">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  1. <span data-ttu-id="d1a6f-233">重新開機主機伺服器。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-233">Restart the host server.</span></span>
    
  2. <span data-ttu-id="d1a6f-234">刪除下列檔案： "%SystemDrive%\Programdata\Cloudconnector\credentials。\<CurrentUser\>.xml "。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-234">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
  3. <span data-ttu-id="d1a6f-235">以系統管理員身分啟動 PowerShell 主控台，然後執行「Register-CcAppliance-Local」，在描述之後重新輸入密碼。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-235">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="d1a6f-236">輸入您在雲端連接器部署之前所輸入的密碼。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-236">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
     <span data-ttu-id="d1a6f-237">**如果您執行的是雲端連接器版本2.0 或更新版本，請**遵循下列步驟來重新產生所有雲端連接器密碼：</span><span class="sxs-lookup"><span data-stu-id="d1a6f-237">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  4. <span data-ttu-id="d1a6f-238">重新開機主機伺服器。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-238">Restart the host server.</span></span>
    
  5. <span data-ttu-id="d1a6f-239">刪除下列檔案： "%SystemDrive%\Programdata\Cloudconnector\credentials。\<CurrentUser\>.xml "。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-239">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
  6. <span data-ttu-id="d1a6f-240">以系統管理員身分啟動 PowerShell 主控台，然後執行「Register-CcAppliance-Local」，在描述之後重新輸入密碼。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-240">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
     <span data-ttu-id="d1a6f-241">如果使用雲端連接器版本1.4.2 產生快取的密碼檔，請在出現提示時，使用 CceService 密碼的 VMAdmin 密碼。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-241">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted.</span></span> <span data-ttu-id="d1a6f-242">針對所有其他帳戶，輸入您在雲端連接器部署之前輸入的相同密碼。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-242">Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
     <span data-ttu-id="d1a6f-243">如果使用雲端連接器版本1.4.2 產生的快取密碼檔，且 DomainAdmin 和 VMAdmin 密碼不同，您必須執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="d1a6f-243">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
  7. <span data-ttu-id="d1a6f-244">執行 CcCredential-AccountType DomainAdmin，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d1a6f-244">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
  8. <span data-ttu-id="d1a6f-245">當系統提示您輸入舊帳號憑證時，請輸入您用於 CceService 密碼的認證。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-245">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  9. <span data-ttu-id="d1a6f-246">當系統提示您輸入新的帳號憑證時，請輸入您之前所用之 DomainAdmin 密碼的密碼。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-246">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
     <span data-ttu-id="d1a6f-247">如果使用雲端連接器版本2.0 或更新版本產生的快取密碼檔案，則根據預設，VmAdmin 和 DomainAdmin 使用與 CceService 相同的密碼。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-247">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="d1a6f-248">如果您變更了 DomainAdmin 和 VMAdmin 密碼，您必須執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="d1a6f-248">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
  10. <span data-ttu-id="d1a6f-249">執行 CcCredential-AccountType DomainAdmin，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d1a6f-249">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
       1. <span data-ttu-id="d1a6f-250">當系統提示您輸入舊帳號憑證時，請輸入您用於 CceService 密碼的認證</span><span class="sxs-lookup"><span data-stu-id="d1a6f-250">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="d1a6f-251">當系統提示您輸入新的帳號憑證時，請輸入您之前所用之 DomainAdmin 密碼的密碼。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-251">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
  11. <span data-ttu-id="d1a6f-252">執行 CcCredential-AccountType VmAdmin，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d1a6f-252">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
       1. <span data-ttu-id="d1a6f-253">當系統提示您輸入舊帳號憑證時，請輸入您用於 CceService 密碼的認證</span><span class="sxs-lookup"><span data-stu-id="d1a6f-253">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="d1a6f-254">當系統提示您輸入新的帳號憑證時，請輸入您之前所用之 VmAdmin 密碼的密碼。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-254">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- <span data-ttu-id="d1a6f-255">**問題：使用雲端連接器版本2.1 及更新版本時，在裝置上執行寄存器 CcAppliance 或其他 Cmdlet 時，您會收到錯誤訊息，例如：「For Each 物件：在這個物件上找不到屬性 ' Common」。確認屬性存在。在 C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1：681字元： 14 "**</span><span class="sxs-lookup"><span data-stu-id="d1a6f-255">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="d1a6f-256">**解決方式：** 雲端連接器2.1 及更新版本需要 .NET Framework 4.6.1 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-256">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="d1a6f-257">請將裝置上的 .NET Framework 更新為4.6.1 或更新版本，然後再次執行 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-257">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>

- <span data-ttu-id="d1a6f-258">**問題：使用雲端連接器版本2.1 時，當您執行安裝 CcAppliance 時，您會收到錯誤訊息，例如：「無法安裝新實例，出現錯誤：無法設定「State」，因為只有字串可以做為值來設定 XmlNode 屬性」**</span><span class="sxs-lookup"><span data-stu-id="d1a6f-258">**Issue: With Cloud Connector Edition 2.1, when running Install-CcAppliance, you receive an error message such as: "Failed to install new instance with error: Cannot set "State" because only strings can be used as values to set XmlNode properties"**</span></span>

   <span data-ttu-id="d1a6f-259">**解決方式：** 在 Cloudconnector 的 [常見] 區段底下，請新增「State」 config，如下所示： CountryCode = 美國州 = WA 市 = 雷蒙德</span><span class="sxs-lookup"><span data-stu-id="d1a6f-259">**Resolution:** In Cloudconnector.ini, under the [Common] section, please add the “State” config as below:  CountryCode=US  State=WA  City=Redmond</span></span>

   <span data-ttu-id="d1a6f-260">"State" 行將不是強制性的，但無法從 Cloudconnector 檔案中移除 [省/市/自治區] 行。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-260">It is not mandatory for the "State" line to have value, however the "State" line cannot be removed from the Cloudconnector.ini file.</span></span>

- <span data-ttu-id="d1a6f-261">**問題：您收到下列錯誤訊息：「卸載-WindowsImage：卸載-WindowsImage 失敗」。安裝或升級雲端連接器版本時，錯誤碼 = 0xc1550115 "。**</span><span class="sxs-lookup"><span data-stu-id="d1a6f-261">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="d1a6f-262">**解決方式：** 以系統管理員身分啟動 PowerShell 主控台，請執行「DISM-清理-Wim」。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-262">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="d1a6f-263">這將會清除所有 troubled 影像。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-263">This will clean up all troubled images.</span></span> <span data-ttu-id="d1a6f-264">再次執行安裝-CcAppliance，或等待 bits 自動升級。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-264">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="d1a6f-265">**問題：在 HA 環境中部署第一個雲端連接器裝置失敗**</span><span class="sxs-lookup"><span data-stu-id="d1a6f-265">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="d1a6f-266">**解決方式：** 您所採取的步驟取決於部署失敗的原因：</span><span class="sxs-lookup"><span data-stu-id="d1a6f-266">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="d1a6f-267">如果第一個雲端連接器裝置發生故障，而且您無法判斷失敗的原因，您必須再次安裝裝置，直到部署成功為止，然後再安裝其他裝置。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-267">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="d1a6f-268">如果第一個雲端連接器裝置出現問題，例如外部憑證問題，您可能可以修正問題，而不需重新安裝裝置。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-268">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="d1a6f-269">然後，您就可以使用租使用者遠端 PowerShell，將部署標示為成功，如下所示。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-269">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="d1a6f-270">（如果第一次部署成功，您也可以使用下列步驟，但由於某種原因，雲端連接器無法成功報告部署。）</span><span class="sxs-lookup"><span data-stu-id="d1a6f-270">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="d1a6f-271">若要取得第一個雲端連接器裝置的身分識別（GUID），請執行 CsHybridPSTNAppliance Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-271">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="d1a6f-272">若要將裝置標示為已成功部署，請執行設定 CsCceApplianceDeploymentStatus，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d1a6f-272">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- <span data-ttu-id="d1a6f-273">**問題：您需要在主機伺服器或虛擬機器上手動檢查並安裝 Windows 更新。**</span><span class="sxs-lookup"><span data-stu-id="d1a6f-273">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
   <span data-ttu-id="d1a6f-274">**解決方式：** 我們建議您利用商務用 Skype 雲端連接器版本所提供的自動作業系統更新。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-274">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition.</span></span> <span data-ttu-id="d1a6f-275">在裝置註冊以進行線上管理且已啟用自動 OS 更新之後，主機伺服器和虛擬機器將根據 OS 更新時間視窗設定，自動檢查並安裝 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-275">After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
   <span data-ttu-id="d1a6f-276">如果您需要手動檢查並安裝 Windows 更新，請按照本節中適用于您的部署類型的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-276">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment.</span></span> <span data-ttu-id="d1a6f-277">您應該規劃同時更新主機伺服器與同時執行的虛擬機器，以將更新所需的停機時間降至最低。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-277">You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
   <span data-ttu-id="d1a6f-278">如果您想要的話，您可以使用 Windows Server Update Services （WSUS）伺服器來提供雲端連接器伺服器的更新。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-278">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers.</span></span> <span data-ttu-id="d1a6f-279">只需確認將 Windows 更新設定為 [**不**自動安裝]。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-279">Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
   <span data-ttu-id="d1a6f-280">如需如何手動更新雲端連接器部署的相關資訊，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-280">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- <span data-ttu-id="d1a6f-281">**問題：雲端連接器更新至新組建時，不會更新雲端連接器 Cmdlet。**</span><span class="sxs-lookup"><span data-stu-id="d1a6f-281">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="d1a6f-282">當自動更新發生時，當 PowerShell 視窗保持開啟時，有時會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-282">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
  <span data-ttu-id="d1a6f-283">**解決方式：** 若要載入更新的 Cmdlet，您可以執行下列其中一項步驟：</span><span class="sxs-lookup"><span data-stu-id="d1a6f-283">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
   - <span data-ttu-id="d1a6f-284">在雲端連接器裝置上關閉 PowerShell，然後重新開啟 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-284">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
     - <span data-ttu-id="d1a6f-285">或者，您可以執行匯入-模組 CloudConnector。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-285">Or, you can run Import-Module CloudConnector -Force.</span></span> 
 
-   <span data-ttu-id="d1a6f-286">**問題：「「Stop-CsWindowsService」這一詞無法辨識為 Cmdlet、函數、腳本檔案或可執行檔程式的名稱。嘗試執行 Enter-CcUpdate Cmdlet 時發生錯誤。**</span><span class="sxs-lookup"><span data-stu-id="d1a6f-286">**Issue: "The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet, function, script file, or operable program." error when attempting to run Enter-CcUpdate cmdlet.**</span></span>

    <span data-ttu-id="d1a6f-287">**解決方式：** 刪除 $HOME \AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache 檔案。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-287">**Resolution:** Delete the $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache file.</span></span>
<span data-ttu-id="d1a6f-288">PowerShell 會將此檔案建立為一個由它所找到之模組的 Cmdlet 的快取，這樣就不必在每次重新分析所有模組，就是使其變得很慢。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-288">PowerShell creates this file as a cache of cmdlets from modules that it finds so that it doesn’t have to re-analyze all the modules each time as that would make things really slow.</span></span> <span data-ttu-id="d1a6f-289">很可能是部分檔案損壞，當它從快取回時，在 PowerShell 中提供誤導性的結果。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-289">Most likely, there was some file corruption that provided misleading results to PowerShell when it was reading back from that cache.</span></span>

-   <span data-ttu-id="d1a6f-290">**問題：「匯入-模組 CloudConnector」產生錯誤「匯入-模組：由於在任何模組目錄中都找不到有效的模組檔案，因此無法載入指定的模組 "CloudConnector"**</span><span class="sxs-lookup"><span data-stu-id="d1a6f-290">**Issue: “Import-Module CloudConnector” generates error “Import-Module: The specified module “CloudConnector” was not loaded because no valid module file was found in any module directory”**</span></span>

    <span data-ttu-id="d1a6f-291">**解析**</span><span class="sxs-lookup"><span data-stu-id="d1a6f-291">**Resolution:**</span></span>
    - <span data-ttu-id="d1a6f-292">確認 [c:\Program Files\WindowsPowerShell\Modules] 底下確實存在 CloudConnector 模組</span><span class="sxs-lookup"><span data-stu-id="d1a6f-292">Validate that indeed the CloudConnector module exists under c:\Program Files\WindowsPowerShell\Modules</span></span>
    
    - <span data-ttu-id="d1a6f-293">在此位置下驗證 CloudConnector 模組之後，可以變更將路徑儲存至模組位置的 PSModulePath 環境變數：</span><span class="sxs-lookup"><span data-stu-id="d1a6f-293">After validating that CloudConnector module exists under this location, the PSModulePath environment variable storing the path to the locations of the modules can be changed:</span></span>
    
     <span data-ttu-id="d1a6f-294">是.</span><span class="sxs-lookup"><span data-stu-id="d1a6f-294">a.</span></span> <span data-ttu-id="d1a6f-295">暫時變更：以系統管理員身分啟動 Powershell，然後執行下列命令： $env:P SModulePath = $env:P SModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span><span class="sxs-lookup"><span data-stu-id="d1a6f-295">Temporary change: Start Powershell as an Administrator and run the following command: $env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span></span>
        
     <span data-ttu-id="d1a6f-296">乙.</span><span class="sxs-lookup"><span data-stu-id="d1a6f-296">b.</span></span> <span data-ttu-id="d1a6f-297">若要永久性變更，請以系統管理員的身分啟動 PowerShell，然後逐個執行下列命令： $CurrentValue = [環境]：： GetEnvironmentVariable （"PSModulePath"，"Machine"） SetEnvironmentVariable （"PSModulePath"，$CurrentValue + ";C:\Program Files\WindowsPowerShell\Modules "，" 電腦 "）</span><span class="sxs-lookup"><span data-stu-id="d1a6f-297">For persistent change, Start PowerShell as an Administrator and run the following commands, one by one: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span></span>

    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="d1a6f-298">手動安裝 Windows 更新</span><span class="sxs-lookup"><span data-stu-id="d1a6f-298">Install Windows updates manually</span></span>

<span data-ttu-id="d1a6f-299">如果您不想在您的環境中使用自動更新，請依照下列步驟手動檢查並套用 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-299">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="d1a6f-300">檢查並安裝 Windows 更新可能需要重新開機伺服器。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-300">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="d1a6f-301">當主機伺服器重新開機時，使用者將無法使用雲端連接器來撥打或接聽電話。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-301">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="d1a6f-302">您可以在更新進行時，手動檢查並安裝更新，然後在您選擇的時間內，根據需要重新開機電腦，以避免服務中斷。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-302">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="d1a6f-303">若要手動檢查更新，請連線到每個主機伺服器，然後開啟 [**控制台**]。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-303">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="d1a6f-304">選取 [**系統及\>安全性] 視窗更新**，然後根據您的環境管理更新和伺服器重新開機。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-304">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="d1a6f-305">如果網站中只有一個裝置，請連線至每個虛擬機器，然後開啟 [**控制台**]。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-305">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="d1a6f-306">選取 [**系統及\>安全性] 視窗更新**，然後視需要設定更新和伺服器重新開機。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-306">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="d1a6f-307">如果網站中有一個以上的裝置，則在更新期間，使用者將無法存取要更新並重新啟動的實例。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-307">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates.</span></span> <span data-ttu-id="d1a6f-308">使用者會連接到部署中的其他實例，直到所有的虛擬機器和所有的商務用 Skype 服務在更新完成之後，在虛擬機器上開始。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-308">Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed.</span></span> <span data-ttu-id="d1a6f-309">若要避免任何可能的服務中斷，您可以在套用更新時從 HA 中移除該實例，並在完成時將它還原。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-309">To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete.</span></span> <span data-ttu-id="d1a6f-310">若要執行此動作：</span><span class="sxs-lookup"><span data-stu-id="d1a6f-310">To do so:</span></span>
    
1. <span data-ttu-id="d1a6f-311">在每個主機伺服器上，以系統管理員身分開啟 PowerShell 主控台。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-311">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="d1a6f-312">使用下列 Cmdlet 從 HA 中移除實例：</span><span class="sxs-lookup"><span data-stu-id="d1a6f-312">Remove the instance from HA with the following cmdlet:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    <span data-ttu-id="d1a6f-313">依照單一實例的步驟，手動套用更新並重新啟動虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-313">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="d1a6f-314">使用下列 Cmdlet，將實例設回 HA：</span><span class="sxs-lookup"><span data-stu-id="d1a6f-314">Set the instance back to HA with the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

<span data-ttu-id="d1a6f-315">針對多網站部署，請針對部署中的每個網站執行單一網站的步驟，一次將更新套用至一個網站。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-315">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="d1a6f-316">在雲端連接器主機電腦上安裝防毒軟體的秘訣</span><span class="sxs-lookup"><span data-stu-id="d1a6f-316">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="d1a6f-317">如果您需要在雲端連接器主機電腦上安裝防毒軟體，您必須新增下列排除專案：</span><span class="sxs-lookup"><span data-stu-id="d1a6f-317">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="d1a6f-318">每個電腦上的 [本機裝置目錄]。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-318">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="d1a6f-319">每個電腦上的遠端網站目錄。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-319">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="d1a6f-320">電腦上的本機網站目錄會託管共用網站根資料夾。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-320">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="d1a6f-321">商務用雲端連接器版%ProgramFiles%\Skype</span><span class="sxs-lookup"><span data-stu-id="d1a6f-321">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="d1a6f-322">%ALLUSERSPROFILE%\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="d1a6f-322">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="d1a6f-323">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="d1a6f-323">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="d1a6f-324">處理常式 ManagementService 的程式。</span><span class="sxs-lookup"><span data-stu-id="d1a6f-324">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>
