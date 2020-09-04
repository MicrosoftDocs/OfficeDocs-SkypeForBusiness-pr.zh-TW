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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: 疑難排解 Cloud Connector Edition 部署。
ms.openlocfilehash: 7a1caea67c5b5899c2dc0909ef771a57c7c50389
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359329"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="e719f-103">疑難排解您的 Cloud Connector 部署</span><span class="sxs-lookup"><span data-stu-id="e719f-103">Troubleshoot your Cloud Connector deployment</span></span>

> [!Important]
> <span data-ttu-id="e719f-104">雲端連接器 Edition 會于2021年7月31日和商務用 Skype Online 終止。</span><span class="sxs-lookup"><span data-stu-id="e719f-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="e719f-105">當您的組織升級至小組後，請瞭解如何使用 [直接路由](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)將您的內部部署電話語音網路連線到小組。</span><span class="sxs-lookup"><span data-stu-id="e719f-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="e719f-106">疑難排解 Cloud Connector Edition 部署。</span><span class="sxs-lookup"><span data-stu-id="e719f-106">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="e719f-107">本主題說明 Cloud Connector Edition 部署常見問題的解決方案。</span><span class="sxs-lookup"><span data-stu-id="e719f-107">This topic describes solutions to common issues with Cloud Connector Edition deployments.</span></span> <span data-ttu-id="e719f-108">如果您在撥打/撥出公用交換電話網路 (PSTN) 時遇到問題，您可以遵循本主題中所述的解決方案來進行調查。</span><span class="sxs-lookup"><span data-stu-id="e719f-108">If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="e719f-109">雲端連接器提供內建的機制，以自動解決某些問題。</span><span class="sxs-lookup"><span data-stu-id="e719f-109">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="e719f-110">自動偵測程式會尋找雲端連接器裝置的潛在問題，如果可能的話，請採取糾正動作來解決這些問題，而不需要系統管理員介入。</span><span class="sxs-lookup"><span data-stu-id="e719f-110">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="e719f-111">偵測過程的運作方式如下：</span><span class="sxs-lookup"><span data-stu-id="e719f-111">The detection process works as follows:</span></span>
  
- <span data-ttu-id="e719f-112">**偵測順序：** 雲端連接器管理服務每60秒會執行一次處理常式，以偵測裝置是否已停機。</span><span class="sxs-lookup"><span data-stu-id="e719f-112">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="e719f-113">在雲端連接器版本2.0 和更新版本中，偵測程式會使用商務用 Skype 交換器，進行與雲端連接器機器的 PowerShell 連線;在2.0 之前的版本中，偵測程式會使用雲端連接器管理參數。</span><span class="sxs-lookup"><span data-stu-id="e719f-113">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e719f-114">若要讓自動復原成功，主機和虛擬機器之間的網路連線必須透過主機網路交換器。</span><span class="sxs-lookup"><span data-stu-id="e719f-114">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="e719f-115">請務必檢查網路連線，以確保自動偵測和復原能夠成功。</span><span class="sxs-lookup"><span data-stu-id="e719f-115">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="e719f-116">**監視：** 以下是在雲端連接器版本2.0 和更新版本中監控的服務：</span><span class="sxs-lookup"><span data-stu-id="e719f-116">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="e719f-117">虛擬機器未連接至雲端連接器公司或網際網路虛擬交換器</span><span class="sxs-lookup"><span data-stu-id="e719f-117">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="e719f-118">虛擬機器的狀態為已儲存或已停止</span><span class="sxs-lookup"><span data-stu-id="e719f-118">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="e719f-119">中央管理伺服器服務：複本、主複本</span><span class="sxs-lookup"><span data-stu-id="e719f-119">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="e719f-120">轉送伺服器服務：複本、RTCSRV 及 MEDSVC</span><span class="sxs-lookup"><span data-stu-id="e719f-120">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="e719f-121">Edge Server services： REPLICA、RTCSRV、RTCDATAPROXY、RTCMRAUTH、RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="e719f-121">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="e719f-122">在 Edge server 上的 CS RTCSRV （轉送伺服器上的 CS RTCMEDSRV）停用輸入防火牆規則</span><span class="sxs-lookup"><span data-stu-id="e719f-122">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="e719f-123">在雲端連接器版本1.4.2 中，只會監控下列服務：</span><span class="sxs-lookup"><span data-stu-id="e719f-123">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="e719f-124">轉送伺服器服務： RTCSRV 和 MEDSVC</span><span class="sxs-lookup"><span data-stu-id="e719f-124">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="e719f-125">Edge Server 服務： RTCSRV</span><span class="sxs-lookup"><span data-stu-id="e719f-125">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="e719f-126">復原**處理常式：** 如果任何監控的服務已關機，裝置會標示為已關機，而且服務會停止並標示手動，直到解決所有問題為止。</span><span class="sxs-lookup"><span data-stu-id="e719f-126">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="e719f-127">這會使呼叫無法路由傳送至可能導致呼叫失敗的裝置。</span><span class="sxs-lookup"><span data-stu-id="e719f-127">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="e719f-128">Cloud Connector Management service 會重試自動復原，如下所示</span><span class="sxs-lookup"><span data-stu-id="e719f-128">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="e719f-129">初始重試間隔是每10秒，最大間隔時間為一小時。</span><span class="sxs-lookup"><span data-stu-id="e719f-129">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="e719f-130">在前三個復原嘗試中，間隔時間為10秒。</span><span class="sxs-lookup"><span data-stu-id="e719f-130">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="e719f-131">從第四個重試開始，間隔時間會增加先前間隔時間的兩倍。</span><span class="sxs-lookup"><span data-stu-id="e719f-131">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="e719f-132">例如，第四次重試會在20秒內發生，第五次則是在40秒內，依此類推。</span><span class="sxs-lookup"><span data-stu-id="e719f-132">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="e719f-133">達到一小時的最大間隔時間時，每小時會繼續嘗試一次。</span><span class="sxs-lookup"><span data-stu-id="e719f-133">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="e719f-134">復原成功時，間隔和重試次數會設定為其初始值。</span><span class="sxs-lookup"><span data-stu-id="e719f-134">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="e719f-135">如果重新開機管理服務，則間隔和重試次數會重設為其初始值。</span><span class="sxs-lookup"><span data-stu-id="e719f-135">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="e719f-136">疑難排解</span><span class="sxs-lookup"><span data-stu-id="e719f-136">Troubleshooting</span></span>

<span data-ttu-id="e719f-137">以下是經常發生問題的解決方案：</span><span class="sxs-lookup"><span data-stu-id="e719f-137">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="e719f-138">**問題：執行部署腳本時，部署失敗或停止回應。登入每個 VM 後，管理/內部/外部 NIC 的 IP 位址遺失或不正確。**</span><span class="sxs-lookup"><span data-stu-id="e719f-138">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="e719f-139">**解決方法：** 無法自動解決此問題。</span><span class="sxs-lookup"><span data-stu-id="e719f-139">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="e719f-140">在執行中時，無法將 Nic 新增至 Vm。</span><span class="sxs-lookup"><span data-stu-id="e719f-140">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="e719f-141">請關閉並移除 hyper-v 管理員中的這些 Vm，然後執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="e719f-141">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="e719f-142">**問題：安裝 Active Directory 伺服器和樹系之後，CMS 伺服器和（或）轉送伺服器並未正確加入網域。**</span><span class="sxs-lookup"><span data-stu-id="e719f-142">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="e719f-143">**解決方法：** 若要解決此問題，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="e719f-143">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="e719f-144">登入 Active Directory 伺服器，並確認已正確建立網域。</span><span class="sxs-lookup"><span data-stu-id="e719f-144">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="e719f-145">登入 CMS/轉送伺服器，並確認已指派有效的 IP 位址的 [商業網路 NIC]，且有效的靜態 IP 和 DNS 已設定為 AD Server 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="e719f-145">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="e719f-146">登入 CMS/轉送伺服器，並開啟命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="e719f-146">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="e719f-147">請確定您可以 ping Active Directory 伺服器的 FQDN 和 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="e719f-147">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="e719f-148">否則，可能會發生 IP 位址衝突。</span><span class="sxs-lookup"><span data-stu-id="e719f-148">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="e719f-149">請嘗試為 Active Directory 指派新的 IP，並據此更新 CMS/轉送伺服器上的 DNS。</span><span class="sxs-lookup"><span data-stu-id="e719f-149">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="e719f-150">**問題：您收到下列錯誤訊息：「Remove-VMSwitch：移除虛擬乙太網交換器時失敗。無法刪除虛擬交換器 ' Cloud Connector Management Switch '，因為它正由執行虛擬機器或指派給子集區使用。」**</span><span class="sxs-lookup"><span data-stu-id="e719f-150">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="e719f-151">**解決方法：** 部署之後，「雲端連接器管理參數」並未刪除。</span><span class="sxs-lookup"><span data-stu-id="e719f-151">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="e719f-152">如果您擊中此錯誤，請移至 Hyper-v 管理員，並確認仍然沒有虛擬機器與其連線。</span><span class="sxs-lookup"><span data-stu-id="e719f-152">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="e719f-153">如果虛擬機器仍已連線，請將其中斷連線並刪除管理參數。</span><span class="sxs-lookup"><span data-stu-id="e719f-153">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="e719f-154">若仍無法刪除管理參數，請重新開機主機伺服器，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="e719f-154">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="e719f-155">**問題：您收到下列錯誤訊息：「無法啟動服務 RTCMRAUTH。請確認服務未停用。**</span><span class="sxs-lookup"><span data-stu-id="e719f-155">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e719f-156">此問題只適用于1.4.2 之前的雲端連接器版本。</span><span class="sxs-lookup"><span data-stu-id="e719f-156">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="e719f-157">[無法啟動] 也可能是因為此前端伺服器先前利用電腦容錯移轉) 進行容錯移轉 (。</span><span class="sxs-lookup"><span data-stu-id="e719f-157">The failure to start could also be because this Front End server was previously failed over (using computer fail over).</span></span> <span data-ttu-id="e719f-158">如果是這種情況，請使用電腦的容錯回復) 來呼叫回 (。</span><span class="sxs-lookup"><span data-stu-id="e719f-158">If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="e719f-159">**解決方法：** 當 Edge Server 未根信任 CA 憑證或中間 CA 憑證時，Edge Server 上便會發生此問題。</span><span class="sxs-lookup"><span data-stu-id="e719f-159">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server.</span></span> <span data-ttu-id="e719f-160">即使可匯入外部憑證，但憑證鏈中斷。</span><span class="sxs-lookup"><span data-stu-id="e719f-160">Even if the external certificate can be imported but the certificate chain is broken.</span></span> <span data-ttu-id="e719f-161">在此情況下，RTCMRAUTH 和/或 RTCSRV 服務無法啟動。</span><span class="sxs-lookup"><span data-stu-id="e719f-161">Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="e719f-162">請將外部憑證的根 CA 憑證和所有中間 CA 憑證，手動匯入 Edge Server，然後重新開機 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="e719f-162">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server.</span></span> <span data-ttu-id="e719f-163">在 Edge Server 上看到 RTCMRAUTH 及 RTCSRV 服務後，請回到您的主機伺服器，以系統管理員身分啟動 PowerShell 主控台，然後執行下列 Cmdlet 以切換至新的部署：</span><span class="sxs-lookup"><span data-stu-id="e719f-163">After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="e719f-164">**問題：已套用 Windows 更新時，主伺服器已重新開機，且伺服器所提供的呼叫會失敗。**</span><span class="sxs-lookup"><span data-stu-id="e719f-164">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="e719f-165">**解決方法：** 如果您部署的是高可用性環境，Microsoft 會提供一個 Cmdlet，協助您在檢查並手動安裝 Windows 更新時，將一部主機器 (部署實例) 移入或移出目前的拓撲。</span><span class="sxs-lookup"><span data-stu-id="e719f-165">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually.</span></span> <span data-ttu-id="e719f-166">請使用下列步驟來完成這項作業：</span><span class="sxs-lookup"><span data-stu-id="e719f-166">Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="e719f-167">在主伺服器上，以系統管理員身分啟動 PowerShell 主控台，然後執行：</span><span class="sxs-lookup"><span data-stu-id="e719f-167">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

2. <span data-ttu-id="e719f-168">檢查是否有更新，並安裝任何可用的。</span><span class="sxs-lookup"><span data-stu-id="e719f-168">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="e719f-169">在 PowerShell 主控台中，執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="e719f-169">In the PowerShell console, run the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    <span data-ttu-id="e719f-170">**問題：從使用 PSTN 號碼的商務用 Skype 用戶端撥出電話時，邀請其他 PSTN 號碼無法將通話呈報給會議。**</span><span class="sxs-lookup"><span data-stu-id="e719f-170">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="e719f-171">**解決方法：** 若要解決此問題，請參閱 [設定線上混合轉送伺服器設定](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer)。</span><span class="sxs-lookup"><span data-stu-id="e719f-171">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="e719f-172">**問題：當您安裝 Active Directory 伺服器時，會顯示關於 Windows 更新的警告訊息-「未啟用 Windows 自動更新」。若要確定您新近安裝的角色或功能會自動更新，請開啟 [Windows 更新]。**</span><span class="sxs-lookup"><span data-stu-id="e719f-172">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="e719f-173">**解決方法：** 使用商務用 Skype 租使用者系統管理員認證啟動租使用者遠端 PowerShell 會話，然後執行下列 Cmdlet 以檢查網站的 _EnableAutoUpdate_ 設定：</span><span class="sxs-lookup"><span data-stu-id="e719f-173">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="e719f-174">如果  _EnableAutoUpdate_ 設定為 **True**，您就可以放心忽略此警告訊息，因為 CCEManagement 服務會同時針對虛擬機器及主機伺服器處理下載及安裝 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="e719f-174">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="e719f-175">如果  _EnableAutoUpdate_ 設定為 **False**，請執行下列 Cmdlet 將它設定為 **True**。</span><span class="sxs-lookup"><span data-stu-id="e719f-175">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="e719f-176">或者，您也可以手動檢查並安裝更新。</span><span class="sxs-lookup"><span data-stu-id="e719f-176">Alternatively, you can manually check for and install updates.</span></span> <span data-ttu-id="e719f-177">請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="e719f-177">See the next section.</span></span>
    
- <span data-ttu-id="e719f-178">**問題：您收到錯誤訊息：無法註冊裝置，因為您目前的輸入/ \<SiteName\> 設定 \<ApplianceName\> 或 \<Mediation Server FQDN\> \<Mediation Server IP Address\> 與現有裝置 (s) 有衝突。移除衝突裝置或更新輸入/設定資訊，然後再註冊一次。' 當執行 CcAppliance 註冊目前裝置至線上時。**</span><span class="sxs-lookup"><span data-stu-id="e719f-178">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="e719f-179">**解決方法：** 的值 \<ApplianceName\> ， \<Mediation Server FQDN\> 且 \<Mediation Server IP Address\> 必須是唯一的，且僅適用于一個裝置註冊。</span><span class="sxs-lookup"><span data-stu-id="e719f-179">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="e719f-180">根據預設，來自 \<ApplianceName\> 主機名稱。</span><span class="sxs-lookup"><span data-stu-id="e719f-180">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="e719f-181">\<Mediation Server FQDN\> 和 \<Mediation Server IP Address\> 定義在設定 ini 檔案中。</span><span class="sxs-lookup"><span data-stu-id="e719f-181">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="e719f-182">例如，使用 (ApplianceName = MyserverNew，轉送伺服器 FQDN = 10.10.10.10) 以登錄 SiteName = MySite，但是如果有已註冊的裝置 (ApplianceName = Myserver，轉送伺服器 FQDN =，轉送伺服器的 IP 位址 = 10.10.10.10) ，您就會發生衝突。。</span><span class="sxs-lookup"><span data-stu-id="e719f-182">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="e719f-183">首先，請在 ApplianceRoot 目錄區段中檢查您的 CloudConnector.ini 檔案。</span><span class="sxs-lookup"><span data-stu-id="e719f-183">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="e719f-184">您將取得 \<SiteName\> 檔案 \<Mediation Server FQDN\> \<Mediation Server IP Address\> 中的和值。</span><span class="sxs-lookup"><span data-stu-id="e719f-184">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="e719f-185">\<ApplianceName\> 是您的主機伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="e719f-185">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="e719f-186">其次，使用商務用 Skype 租使用者系統管理員認證來啟動租使用者遠端 PowerShell，然後執行下列 Cmdlet 以檢查註冊的裝置 (s) 。</span><span class="sxs-lookup"><span data-stu-id="e719f-186">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="e719f-187">在識別任何衝突之後，您可以使用符合註冊裝置的資訊來更新 CloudConnector.ini 檔案，或取消註冊現有裝置以解決衝突。</span><span class="sxs-lookup"><span data-stu-id="e719f-187">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- <span data-ttu-id="e719f-188">**問題：如果主機上有已部署的裝置，CcRunningVersion Cmdlet 會傳回空值。**</span><span class="sxs-lookup"><span data-stu-id="e719f-188">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
  <span data-ttu-id="e719f-189">**解決方法：** 當您從1.3.4 或1.3.8 升級至1.4.1 時，可能會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="e719f-189">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1.</span></span> <span data-ttu-id="e719f-190">使用 .msi 安裝版本1.4.1 之後，您必須先執行， `Register-CcAppliance` 再執行任何其他 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e719f-190">After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet.</span></span> <span data-ttu-id="e719f-191">`Register-CcAppliance` 會將 module.ini 檔案從%UserProfile%\CloudConnector 遷移至%ProgramData%\CloudConnector。</span><span class="sxs-lookup"><span data-stu-id="e719f-191">`Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector.</span></span> <span data-ttu-id="e719f-192">如果您錯過了它，將會在%ProgramData%\CloudConnector 資料夾中建立新的 module.ini，並取代1.3.4 或1.3.8 的執行/備份版本資訊。</span><span class="sxs-lookup"><span data-stu-id="e719f-192">If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
  <span data-ttu-id="e719f-193">比較%UserProfile%\CloudConnector 和%ProgramData%\CloudConnector 資料夾中的 module.ini 檔案。</span><span class="sxs-lookup"><span data-stu-id="e719f-193">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="e719f-194">如果有差異，請刪除%ProgramData%\CloudConnector 中的 module.ini 檔案，然後重新執行  `Register-CcAppliance` 。</span><span class="sxs-lookup"><span data-stu-id="e719f-194">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="e719f-195">您也可以手動將檔案修改為正確的執行和備份版本。</span><span class="sxs-lookup"><span data-stu-id="e719f-195">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="e719f-196">**問題：當您執行 CcVersion 指令程式來切換至與目前腳本版本不同的舊版本時，此舊版本沒有高可用性支援。**</span><span class="sxs-lookup"><span data-stu-id="e719f-196">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="e719f-197">**解決方法：** 例如，您已從1.4.1 升級到1.4.2。</span><span class="sxs-lookup"><span data-stu-id="e719f-197">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="e719f-198">您目前的腳本版本（可以透過執行 `Get-CcVersion` ）和您的執行版本（這  `Get-CcRunningVersion` 兩種都是1.4.2）所決定。</span><span class="sxs-lookup"><span data-stu-id="e719f-198">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="e719f-199">在此情況下，如果您執行將執行 `Switch-CcVersion` 中的版本切換回1.4.1，則此舊版本將無法提供高可用性支援。</span><span class="sxs-lookup"><span data-stu-id="e719f-199">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="e719f-200">若要取得完整的高可用性支援，請切換回舊版，使執行的版本和腳本版本相同。</span><span class="sxs-lookup"><span data-stu-id="e719f-200">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same.</span></span> <span data-ttu-id="e719f-201">如果您遇到1.4.2 部署的問題，請儘快卸載並重新安裝。</span><span class="sxs-lookup"><span data-stu-id="e719f-201">If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="e719f-202">**問題：對中央管理存放區、轉送伺服器和 Edge Server 發出的憑證授權憑證或內部憑證接近到期或遭到洩漏。**</span><span class="sxs-lookup"><span data-stu-id="e719f-202">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="e719f-203">**解決方法：** 商務用 Skype 憑證授權憑證在五年之內有效。</span><span class="sxs-lookup"><span data-stu-id="e719f-203">**Resolution:** Skype for Business certification authority certificates are valid for five years.</span></span> <span data-ttu-id="e719f-204">發佈至中央管理存放區、轉送伺服器和 Edge Server 的內部憑證是兩年有效。</span><span class="sxs-lookup"><span data-stu-id="e719f-204">Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e719f-205">在雲端連接器版本2.0 和更新版本中，CcServerCertificate Cmdlet 已變更為 CcServerCertificate，且 CcCACertificate Cmdlet 已變更為 Update-CcCACertificate。</span><span class="sxs-lookup"><span data-stu-id="e719f-205">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="e719f-206">如果向中央管理存放區、轉送伺服器和 Edge Server 發行的內部憑證接近到期或遭到損害，請執行 CcServerCertificate 或 Update-CcServerCertificate Cmdlet 來更新您的憑證。</span><span class="sxs-lookup"><span data-stu-id="e719f-206">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="e719f-207">如果憑證授權單位憑證接近到期，請執行 CcCACertificate 或 Update-CcCACertificate Cmdlet 來更新憑證。</span><span class="sxs-lookup"><span data-stu-id="e719f-207">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="e719f-208">**如果憑證授權單位憑證遭到損害，且網站中只有一個裝置，請** 執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="e719f-208">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="e719f-209">執行 Enter-CcUpdate 指令程式以排出服務，並將裝置置於維護模式。</span><span class="sxs-lookup"><span data-stu-id="e719f-209">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. <span data-ttu-id="e719f-210">執行下列 Cmdlet 以重設及建立新的憑證授權單位憑證和所有內部伺服器憑證：</span><span class="sxs-lookup"><span data-stu-id="e719f-210">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="e719f-211">在2.0 之前的雲端連接器版本：</span><span class="sxs-lookup"><span data-stu-id="e719f-211">For Cloud Connector releases before 2.0:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="e719f-212">或適用于雲端連接器版本2.0 和更新版本：</span><span class="sxs-lookup"><span data-stu-id="e719f-212">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. <span data-ttu-id="e719f-213">如果閘道和轉送伺服器之間使用 TLS，請從裝置執行 Export-CcRootCertificate 指令程式，然後將匯出的憑證安裝到您的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="e719f-213">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from the appliance, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="e719f-214">您可能還需要重新簽發您的閘道上的憑證。</span><span class="sxs-lookup"><span data-stu-id="e719f-214">You may also be required to re-issue the certificate on your gateway.</span></span>

   ```powershell
   Export-CcRootCertificate
   ```

4. <span data-ttu-id="e719f-215">執行 CcUpdate 指令程式，以啟動服務並退出維護模式。</span><span class="sxs-lookup"><span data-stu-id="e719f-215">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span>

   ```powershell
   Exit-CcUpdate
   ```


    <span data-ttu-id="e719f-216">**如果憑證授權單位憑證遭到損害，且網站中有多個裝置，請** 在網站的每部裝置中執行下列順序步驟。</span><span class="sxs-lookup"><span data-stu-id="e719f-216">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="e719f-217">Microsoft 建議您在非峰使用時間內執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="e719f-217">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
1. <span data-ttu-id="e719f-218">在第一個裝置上，執行 CcCertificationAuthorityFile Cmdlet 以清除目錄中的 CA 備份檔案 \<SiteRoot\> 。</span><span class="sxs-lookup"><span data-stu-id="e719f-218">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. <span data-ttu-id="e719f-219">執行 Enter-CcUpdate 指令程式以排出服務，並將每個裝置置於維護模式。</span><span class="sxs-lookup"><span data-stu-id="e719f-219">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>

     ```powershell
     Enter-CcUpdate
     ```
    
3. <span data-ttu-id="e719f-220">在第一個裝置上，執行下列 Cmdlet 以重設及建立新的憑證授權單位憑證和所有內部伺服器憑證：</span><span class="sxs-lookup"><span data-stu-id="e719f-220">On the first appliance, run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
     <span data-ttu-id="e719f-221">在2.0 之前的雲端連接器版本：</span><span class="sxs-lookup"><span data-stu-id="e719f-221">For Cloud Connector releases before 2.0:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     <span data-ttu-id="e719f-222">或適用于雲端連接器版本2.0 和更新版本：</span><span class="sxs-lookup"><span data-stu-id="e719f-222">Or for Cloud Connector release 2.0 and later:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. <span data-ttu-id="e719f-223">在第一個裝置上，執行下列 Cmdlet，將 CA 檔案備份到 \<SiteRoot\> 資料夾。</span><span class="sxs-lookup"><span data-stu-id="e719f-223">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span>
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. <span data-ttu-id="e719f-224">在所有其他裝置的相同網站中執行下列命令，以使用 CA 備份檔案，讓裝置都使用相同的根憑證，然後要求新的憑證。</span><span class="sxs-lookup"><span data-stu-id="e719f-224">On all other appliance's in the same site, run the following commands to consume the CA backup files, so that the appliances all use the same root certificate, and then request new certificates.</span></span> 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. <span data-ttu-id="e719f-225">如果閘道和轉送伺服器之間使用 TLS，請從網站的任何裝置執行 Export-CcRootCertificate 指令程式，然後將匯出的憑證安裝到您的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="e719f-225">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="e719f-226">您可能還需要重新簽發您的閘道上的憑證。</span><span class="sxs-lookup"><span data-stu-id="e719f-226">You may also be required to re-issue the certificate on your gateway.</span></span>
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. <span data-ttu-id="e719f-227">執行 CcUpdate 指令程式，以啟動服務並退出維護模式。</span><span class="sxs-lookup"><span data-stu-id="e719f-227">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- <span data-ttu-id="e719f-228">**問題：您在雲端連接器管理服務記錄中收到下列錯誤訊息：「C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log "： CceService 錯誤：0：向線上報告狀態時出現意外例外狀況：。 CmdletInvocationException： \<Global Tenant Admin\> 為使用者登入失敗。請建立新的身分憑證物件，確定您已使用正確的使用者名稱和密碼。---\>**</span><span class="sxs-lookup"><span data-stu-id="e719f-228">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="e719f-229">**解決方法：** Microsoft 365 或 Office 365 全域租使用者系統管理員認證自雲端連接器裝置註冊後已變更。</span><span class="sxs-lookup"><span data-stu-id="e719f-229">**Resolution:** The Microsoft 365 or Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="e719f-230">若要在雲端連接器裝置上更新本機儲存的認證，請從主機裝置上的系統管理員 PowerShell 執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="e719f-230">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- <span data-ttu-id="e719f-231">**問題：在您變更用於部署之主機伺服器帳戶的密碼之後，您會收到下列錯誤訊息：「ConvertTo-SecureString：在指定的狀態中使用的機碼無效。」在%ProgramFiles%\Skype for Business 雲端 Connector Edition\ManagementService\CceManagementService.log 或執行 CcCredential Cmdlet。**</span><span class="sxs-lookup"><span data-stu-id="e719f-231">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="e719f-232">**解決方法：** 所有雲端連接器認證都儲存在下列檔案中： "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> 。xml "。</span><span class="sxs-lookup"><span data-stu-id="e719f-232">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="e719f-233">當主伺服器上的密碼變更時，您將需要更新本機儲存的認證。</span><span class="sxs-lookup"><span data-stu-id="e719f-233">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="e719f-234">**如果您正在執行雲端連接器版本1.4.2，請** 遵循下列步驟重新產生所有雲端連接器密碼：</span><span class="sxs-lookup"><span data-stu-id="e719f-234">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  1. <span data-ttu-id="e719f-235">重新開機主機伺服器。</span><span class="sxs-lookup"><span data-stu-id="e719f-235">Restart the host server.</span></span>
    
  2. <span data-ttu-id="e719f-236">刪除下列檔案： "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> 。xml "。</span><span class="sxs-lookup"><span data-stu-id="e719f-236">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
  3. <span data-ttu-id="e719f-237">以系統管理員身分啟動 PowerShell 主控台，然後執行「Register-CcAppliance-Local」，以在描述之後重新輸入密碼。</span><span class="sxs-lookup"><span data-stu-id="e719f-237">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="e719f-238">輸入您在雲端連接器部署之前輸入的相同密碼。</span><span class="sxs-lookup"><span data-stu-id="e719f-238">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
     <span data-ttu-id="e719f-239">**如果您正在執行 Cloud connector 版本2.0 或更新版本，請** 遵循下列步驟來重新產生所有雲端連接器密碼：</span><span class="sxs-lookup"><span data-stu-id="e719f-239">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  4. <span data-ttu-id="e719f-240">重新開機主機伺服器。</span><span class="sxs-lookup"><span data-stu-id="e719f-240">Restart the host server.</span></span>
    
  5. <span data-ttu-id="e719f-241">刪除下列檔案： "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> 。xml "。</span><span class="sxs-lookup"><span data-stu-id="e719f-241">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
  6. <span data-ttu-id="e719f-242">以系統管理員身分啟動 PowerShell 主控台，然後執行「Register-CcAppliance-Local」，以在描述之後重新輸入密碼。</span><span class="sxs-lookup"><span data-stu-id="e719f-242">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
     <span data-ttu-id="e719f-243">若快取密碼檔是以雲端連接器版本1.4.2 產生，請在提示時使用 CceService 密碼的 VMAdmin 密碼。</span><span class="sxs-lookup"><span data-stu-id="e719f-243">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted.</span></span> <span data-ttu-id="e719f-244">輸入您在雲端連接器部署之前輸入的相同密碼，供所有其他帳戶用。</span><span class="sxs-lookup"><span data-stu-id="e719f-244">Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
     <span data-ttu-id="e719f-245">若快取密碼檔是以雲端連接器版本1.4.2 產生，且 DomainAdmin 和 VMAdmin 密碼不同，您必須執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="e719f-245">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
  7. <span data-ttu-id="e719f-246">執行 Set-CcCredential-AccountType DomainAdmin，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e719f-246">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
  8. <span data-ttu-id="e719f-247">當系統提示您輸入舊帳號憑證時，請輸入您用於 CceService 密碼的認證。</span><span class="sxs-lookup"><span data-stu-id="e719f-247">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  9. <span data-ttu-id="e719f-248">當系統提示您輸入新的帳號憑證時，請輸入您之前所用之 DomainAdmin 密碼的密碼。</span><span class="sxs-lookup"><span data-stu-id="e719f-248">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
     <span data-ttu-id="e719f-249">若快取密碼檔是以 Cloud Connector 版本2.0 或更新版本產生，則根據預設，VmAdmin 和 DomainAdmin 會使用與 CceService 相同的密碼。</span><span class="sxs-lookup"><span data-stu-id="e719f-249">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="e719f-250">如果您變更了 DomainAdmin 和 VMAdmin 密碼，您必須執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="e719f-250">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
  10. <span data-ttu-id="e719f-251">執行 Set-CcCredential-AccountType DomainAdmin，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e719f-251">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
       1. <span data-ttu-id="e719f-252">當系統提示您輸入舊帳號憑證時，請輸入您用於 CceService 密碼的認證</span><span class="sxs-lookup"><span data-stu-id="e719f-252">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="e719f-253">當系統提示您輸入新的帳號憑證時，請輸入您之前所用之 DomainAdmin 密碼的密碼。</span><span class="sxs-lookup"><span data-stu-id="e719f-253">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
  11. <span data-ttu-id="e719f-254">執行 Set-CcCredential-AccountType VmAdmin，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e719f-254">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
       1. <span data-ttu-id="e719f-255">當系統提示您輸入舊帳號憑證時，請輸入您用於 CceService 密碼的認證</span><span class="sxs-lookup"><span data-stu-id="e719f-255">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="e719f-256">當系統提示您輸入新的帳號憑證時，請輸入您之前所用之 VmAdmin 密碼的密碼。</span><span class="sxs-lookup"><span data-stu-id="e719f-256">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- <span data-ttu-id="e719f-257">**問題：使用雲端連接器版本2.1 和更新版本時，在裝置上執行 CcAppliance 或其他 Cmdlet 時，會收到一則錯誤訊息，例如，針對每個物件： "the the the the the property the the the the the the the the the the the the the the the the the the the the確認該屬性存在。C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1： 681 char： 14 "**</span><span class="sxs-lookup"><span data-stu-id="e719f-257">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="e719f-258">**解決方法：** Cloud Connector 2.1 和更新版本需要 .NET Framework 4.6.1 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="e719f-258">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="e719f-259">請將裝置上的 .NET Framework 更新為版本4.6.1 或更新版本，然後再次執行 Cmdlet () 。</span><span class="sxs-lookup"><span data-stu-id="e719f-259">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>

- <span data-ttu-id="e719f-260">**問題：使用雲端連接器 Edition 2.1 時，當執行 CcAppliance 時，會收到錯誤訊息，例如：「未能安裝新的實例，錯誤：無法設定「狀態」，因為只有字串可以做為值以設定 XmlNode 屬性」**</span><span class="sxs-lookup"><span data-stu-id="e719f-260">**Issue: With Cloud Connector Edition 2.1, when running Install-CcAppliance, you receive an error message such as: "Failed to install new instance with error: Cannot set "State" because only strings can be used as values to set XmlNode properties"**</span></span>

   <span data-ttu-id="e719f-261">**解決方法：** 在 Cloudconnector.ini 中的 [通用] 區段下，請新增「State」 config，如下所示： CountryCode = US State = 華盛頓市 = Redmond</span><span class="sxs-lookup"><span data-stu-id="e719f-261">**Resolution:** In Cloudconnector.ini, under the [Common] section, please add the “State” config as below:  CountryCode=US  State=WA  City=Redmond</span></span>

   <span data-ttu-id="e719f-262">「狀態」列必須具有值，但無法從 Cloudconnector.ini 檔移除「狀態」行。</span><span class="sxs-lookup"><span data-stu-id="e719f-262">It is not mandatory for the "State" line to have value, however the "State" line cannot be removed from the Cloudconnector.ini file.</span></span>

- <span data-ttu-id="e719f-263">**問題：您收到下列錯誤訊息：「卸裝-WindowsImage： WindowsImage 失敗」。在安裝或升級 Cloud Connector Edition 時，錯誤代碼 = 0xc1550115 "。**</span><span class="sxs-lookup"><span data-stu-id="e719f-263">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="e719f-264">**解決方法：** 以系統管理員身分啟動 PowerShell 主控台，請執行「DISM-清除-Wim '」。</span><span class="sxs-lookup"><span data-stu-id="e719f-264">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="e719f-265">這會清除所有的 troubled 影像。</span><span class="sxs-lookup"><span data-stu-id="e719f-265">This will clean up all troubled images.</span></span> <span data-ttu-id="e719f-266">再次執行 Install-CcAppliance，或等候 bits 自動升級。</span><span class="sxs-lookup"><span data-stu-id="e719f-266">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="e719f-267">**問題：在 HA 環境中部署第一個雲端連接器裝置失敗**</span><span class="sxs-lookup"><span data-stu-id="e719f-267">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="e719f-268">**解決方法：** 您採取的步驟取決於部署失敗的原因：</span><span class="sxs-lookup"><span data-stu-id="e719f-268">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="e719f-269">如果第一個雲端連接器裝置失敗，而且您無法判斷失敗的原因，則必須重新安裝裝置，直到部署成功為止，然後再安裝其他裝置。</span><span class="sxs-lookup"><span data-stu-id="e719f-269">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="e719f-270">如果第一個雲端連接器裝置因次要問題而失敗，例如外部憑證問題，您可能能夠修正問題，而不需重新安裝裝置。</span><span class="sxs-lookup"><span data-stu-id="e719f-270">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="e719f-271">然後，您可以使用租使用者 remote PowerShell，將部署標示為成功，如下所示。</span><span class="sxs-lookup"><span data-stu-id="e719f-271">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="e719f-272"> (您也可以在第一次部署成功時使用下列步驟，但由於某些原因，Cloud Connector 無法報告部署成功。 ) </span><span class="sxs-lookup"><span data-stu-id="e719f-272">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="e719f-273">若要取得第一個雲端連接器裝置的身分識別 (GUID) ，請執行 CsHybridPSTNAppliance Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e719f-273">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="e719f-274">若要將裝置標示為已成功部署，請執行 CsCceApplianceDeploymentStatus，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e719f-274">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- <span data-ttu-id="e719f-275">**問題：您必須在主伺服器或虛擬機器上手動檢查並安裝 Windows 更新。**</span><span class="sxs-lookup"><span data-stu-id="e719f-275">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
   <span data-ttu-id="e719f-276">**解決方法：** 建議您利用商務用 Skype 雲端連接器 Edition 所提供的自動化作業系統更新。</span><span class="sxs-lookup"><span data-stu-id="e719f-276">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition.</span></span> <span data-ttu-id="e719f-277">在註冊裝置以供線上管理及自動作業系統更新啟用之後，主伺服器及虛擬機器將會根據作業系統更新時間視窗設定，自動檢查並安裝 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="e719f-277">After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
   <span data-ttu-id="e719f-278">如果您需要手動檢查並安裝 Windows 更新，請遵循本節中適用于您的部署類型的步驟。</span><span class="sxs-lookup"><span data-stu-id="e719f-278">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment.</span></span> <span data-ttu-id="e719f-279">您應該同時規劃同時更新主機伺服器及同時在其上執行的虛擬機器，以將更新所需的停機時間降至最低。</span><span class="sxs-lookup"><span data-stu-id="e719f-279">You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
   <span data-ttu-id="e719f-280">如果您願意，您可以使用 Windows Server Update Services (WSUS) 伺服器來提供雲端連接器伺服器的更新。</span><span class="sxs-lookup"><span data-stu-id="e719f-280">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers.</span></span> <span data-ttu-id="e719f-281">請務必將 Windows 更新設定為 **不** 會自動安裝。</span><span class="sxs-lookup"><span data-stu-id="e719f-281">Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
   <span data-ttu-id="e719f-282">如需如何手動更新雲端連接器部署的詳細資訊，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="e719f-282">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- <span data-ttu-id="e719f-283">**問題：當 Cloud Connector 更新至新的組建時，不會更新雲端連接器 Cmdlet。**</span><span class="sxs-lookup"><span data-stu-id="e719f-283">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="e719f-284">當自動更新發生時，當 PowerShell 視窗保持開啟狀態時，有時會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="e719f-284">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
  <span data-ttu-id="e719f-285">**解決方法：** 若要載入更新的 Cmdlet，您可以執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="e719f-285">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
   - <span data-ttu-id="e719f-286">關閉雲端連接器裝置上的 PowerShell，然後重新開啟 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="e719f-286">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
     - <span data-ttu-id="e719f-287">或者，您可以 Import-Module CloudConnector-Force 執行。</span><span class="sxs-lookup"><span data-stu-id="e719f-287">Or, you can run Import-Module CloudConnector -Force.</span></span> 
 
-   <span data-ttu-id="e719f-288">**問題：「字詞 ' Stop-CsWindowsService ' 不會被辨識為 Cmdlet、function、script file 或 run program 的名稱。嘗試執行 CcUpdate 指令程式時發生錯誤。**</span><span class="sxs-lookup"><span data-stu-id="e719f-288">**Issue: "The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet, function, script file, or operable program." error when attempting to run Enter-CcUpdate cmdlet.**</span></span>

    <span data-ttu-id="e719f-289">**解決方法：** 刪除 $HOME 的 \AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache 檔案。</span><span class="sxs-lookup"><span data-stu-id="e719f-289">**Resolution:** Delete the $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache file.</span></span>
<span data-ttu-id="e719f-290">PowerShell 會將此檔案建立為其所找到之模組的指令程式快取，這樣就不必每次重新分析所有的模組，這樣做會使事情變得非常緩慢。</span><span class="sxs-lookup"><span data-stu-id="e719f-290">PowerShell creates this file as a cache of cmdlets from modules that it finds so that it doesn’t have to re-analyze all the modules each time as that would make things really slow.</span></span> <span data-ttu-id="e719f-291">在從該快取中讀取郵件時，可能會有一些檔案損毀，提供要 PowerShell 的誤導結果。</span><span class="sxs-lookup"><span data-stu-id="e719f-291">Most likely, there was some file corruption that provided misleading results to PowerShell when it was reading back from that cache.</span></span>

-   <span data-ttu-id="e719f-292">**問題： "Import-Module CloudConnector" 產生錯誤 "Import-Module：指定的模組" CloudConnector "未載入，因為在任何模組目錄中找不到有效的模組檔案"**</span><span class="sxs-lookup"><span data-stu-id="e719f-292">**Issue: “Import-Module CloudConnector” generates error “Import-Module: The specified module “CloudConnector” was not loaded because no valid module file was found in any module directory”**</span></span>

    <span data-ttu-id="e719f-293">**解決方案：**</span><span class="sxs-lookup"><span data-stu-id="e719f-293">**Resolution:**</span></span>
    - <span data-ttu-id="e719f-294">驗證 CloudConnector 模組是否確實存在於 c:\Program Files\WindowsPowerShell\Modules</span><span class="sxs-lookup"><span data-stu-id="e719f-294">Validate that indeed the CloudConnector module exists under c:\Program Files\WindowsPowerShell\Modules</span></span>
    
    - <span data-ttu-id="e719f-295">在驗證 CloudConnector 模組存在於此位置下之後，可以變更儲存模組位置路徑的 PSModulePath 環境變數：</span><span class="sxs-lookup"><span data-stu-id="e719f-295">After validating that CloudConnector module exists under this location, the PSModulePath environment variable storing the path to the locations of the modules can be changed:</span></span>
    
     <span data-ttu-id="e719f-296">a.</span><span class="sxs-lookup"><span data-stu-id="e719f-296">a.</span></span> <span data-ttu-id="e719f-297">暫時變更：以系統管理員身分啟動 Powershell，並執行下列命令： $env:P SModulePath = $env:P SModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span><span class="sxs-lookup"><span data-stu-id="e719f-297">Temporary change: Start Powershell as an Administrator and run the following command: $env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span></span>
        
     <span data-ttu-id="e719f-298">b.</span><span class="sxs-lookup"><span data-stu-id="e719f-298">b.</span></span> <span data-ttu-id="e719f-299">針對持續變更，以系統管理員身分啟動 PowerShell，並執行下列命令之一： $CurrentValue = [環境]：： GetEnvironmentVariable ( "PSModulePath"，"Machine" ) SetEnvironmentVariable ( "PSModulePath"，$CurrentValue + ";C:\Program Files\WindowsPowerShell\Modules "，" Machine ") </span><span class="sxs-lookup"><span data-stu-id="e719f-299">For persistent change, Start PowerShell as an Administrator and run the following commands, one by one: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span></span>

    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="e719f-300">手動安裝 Windows 更新</span><span class="sxs-lookup"><span data-stu-id="e719f-300">Install Windows updates manually</span></span>

<span data-ttu-id="e719f-301">如果您不想要在環境中使用自動更新，請遵循下列步驟，手動檢查並套用 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="e719f-301">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="e719f-302">檢查並安裝 Windows 更新可能需要重新開機伺服器。</span><span class="sxs-lookup"><span data-stu-id="e719f-302">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="e719f-303">當主機伺服器重新開機時，使用者將無法使用雲端連接器撥打或接聽電話。</span><span class="sxs-lookup"><span data-stu-id="e719f-303">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="e719f-304">您可以手動檢查並安裝更新，以控制更新何時進行，然後在您選擇避免服務中斷時，視需要重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="e719f-304">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="e719f-305">若要手動檢查更新，請連線至每個主機伺服器，然後開啟 [ **控制台**]。</span><span class="sxs-lookup"><span data-stu-id="e719f-305">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="e719f-306">選取 [ **系統及安全性] [ \> Windows 更新**]，然後視您的環境，管理更新和伺服器重新開機。</span><span class="sxs-lookup"><span data-stu-id="e719f-306">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="e719f-307">如果網站中只有一個裝置，請連接到每一部虛擬機器，然後開啟 [ **控制台**]。</span><span class="sxs-lookup"><span data-stu-id="e719f-307">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="e719f-308">選取 [ **系統及安全性] [ \> Windows 更新**]，然後視需要設定更新和伺服器重新開機。</span><span class="sxs-lookup"><span data-stu-id="e719f-308">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="e719f-309">如果網站中有多部裝置，則在更新期間，使用者無法存取已更新並重新啟動的實例。</span><span class="sxs-lookup"><span data-stu-id="e719f-309">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates.</span></span> <span data-ttu-id="e719f-310">使用者將會連線至部署中的其他實例，直到更新完成後，所有虛擬機器和商務用 Skype 服務都會在虛擬機器上開始。</span><span class="sxs-lookup"><span data-stu-id="e719f-310">Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed.</span></span> <span data-ttu-id="e719f-311">若要避免任何可能中斷服務的情況，您可以在應用更新時從 HA 移除實例，然後在完成時還原。</span><span class="sxs-lookup"><span data-stu-id="e719f-311">To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete.</span></span> <span data-ttu-id="e719f-312">若要這麼做︰</span><span class="sxs-lookup"><span data-stu-id="e719f-312">To do so:</span></span>
    
1. <span data-ttu-id="e719f-313">在每一部主伺服器上，以系統管理員身分開啟 PowerShell 主控台。</span><span class="sxs-lookup"><span data-stu-id="e719f-313">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="e719f-314">使用下列 Cmdlet 從 HA 中移除實例：</span><span class="sxs-lookup"><span data-stu-id="e719f-314">Remove the instance from HA with the following cmdlet:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    <span data-ttu-id="e719f-315">依照單一實例的步驟，手動套用更新並重新啟動虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="e719f-315">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="e719f-316">使用下列 Cmdlet，將實例設回 HA：</span><span class="sxs-lookup"><span data-stu-id="e719f-316">Set the instance back to HA with the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

<span data-ttu-id="e719f-317">針對多網站部署，針對部署中的每個網站執行單一網站的步驟，一次套用一個網站的更新。</span><span class="sxs-lookup"><span data-stu-id="e719f-317">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="e719f-318">在雲端連接器主機機器上安裝防毒軟體時的秘訣</span><span class="sxs-lookup"><span data-stu-id="e719f-318">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="e719f-319">如果您需要在雲端連接器主機機器上安裝防毒軟體，您必須新增下列排除專案：</span><span class="sxs-lookup"><span data-stu-id="e719f-319">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="e719f-320">在每個機器上的本機裝置目錄。</span><span class="sxs-lookup"><span data-stu-id="e719f-320">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="e719f-321">每個電腦上的遠端網站目錄。</span><span class="sxs-lookup"><span data-stu-id="e719f-321">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="e719f-322">電腦上的本機網站目錄會裝載共用網站根資料夾。</span><span class="sxs-lookup"><span data-stu-id="e719f-322">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="e719f-323">%ProgramFiles%\Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="e719f-323">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="e719f-324">%ALLUSERSPROFILE%\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="e719f-324">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="e719f-325">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="e719f-325">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="e719f-326">處理常式 Microsoft.Rtc.CCE.ManagementService.exe。</span><span class="sxs-lookup"><span data-stu-id="e719f-326">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>
