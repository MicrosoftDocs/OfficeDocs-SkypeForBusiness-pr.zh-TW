---
title: 升級至新版 Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: 瞭解如何升級 Cloud Connector Edition 部署。
ms.openlocfilehash: fea78c6b1b6ba3b2e644fef71d78b94aa3a244b7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109129"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a><span data-ttu-id="3ec60-103">升級至新版 Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="3ec60-103">Upgrade to a new version of Cloud Connector</span></span>

> [!Important]
> <span data-ttu-id="3ec60-104">雲端連接器 Edition 會于2021年7月31日和商務用 Skype Online 終止。</span><span class="sxs-lookup"><span data-stu-id="3ec60-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="3ec60-105">當您的組織升級至小組後，請瞭解如何使用 [直接路由](/MicrosoftTeams/direct-routing-landing-page)將您的內部部署電話語音網路連線到小組。</span><span class="sxs-lookup"><span data-stu-id="3ec60-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="3ec60-106">瞭解如何升級 Cloud Connector Edition 部署。</span><span class="sxs-lookup"><span data-stu-id="3ec60-106">Learn about how to upgrade your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="3ec60-107">如果您已設定線上管理租使用者帳戶並啟用自動更新，您現有的商務用 Skype 雲端連接器版本部署會根據您的自動更新時間範圍設定，自動升級為更新的版本。</span><span class="sxs-lookup"><span data-stu-id="3ec60-107">If you have set up an online management tenant account and enabled automatic updates, your existing deployment of Skype for Business Cloud Connector Edition will be upgraded to the newer version automatically—according to your automatic update time window configuration.</span></span> <span data-ttu-id="3ec60-108">您也可以執行手動升級。</span><span class="sxs-lookup"><span data-stu-id="3ec60-108">You can also perform a manual upgrade.</span></span> 
  
<span data-ttu-id="3ec60-109">Cloud Connector Edition Edition 1.4.1 及更新版本預設會執行自動更新。</span><span class="sxs-lookup"><span data-stu-id="3ec60-109">Cloud Connector Edition versions 1.4.1 and later perform automatic updates by default.</span></span> <span data-ttu-id="3ec60-110">若要以手動方式升級至最新版本 (2.1) ，請參閱本主題稍後的將 [單一網站升級至新版本](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) 。</span><span class="sxs-lookup"><span data-stu-id="3ec60-110">If you want to upgrade to the latest version (2.1) manually, see [Upgrade a single site to a new version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) later in this topic.</span></span>
  
<span data-ttu-id="3ec60-111">自動更新要求雲端連接器服務正在執行中。</span><span class="sxs-lookup"><span data-stu-id="3ec60-111">Automatic update requires that the Cloud Connector service is running.</span></span> <span data-ttu-id="3ec60-112">下列步驟說明自動更新的程式：</span><span class="sxs-lookup"><span data-stu-id="3ec60-112">The following steps describe the process for automatic updates:</span></span>
  
- <span data-ttu-id="3ec60-113">自動更新程式會根據您為自動更新所設定的排程來執行。</span><span class="sxs-lookup"><span data-stu-id="3ec60-113">The automatic update process will run according to the schedule you have configured for automatic updates.</span></span>
    
- <span data-ttu-id="3ec60-114">作業系統更新任務</span><span class="sxs-lookup"><span data-stu-id="3ec60-114">Operating system update tasks</span></span>
    
  - <span data-ttu-id="3ec60-115">檢查並下載所有雲端連接器 Vm 的作業系統更新。</span><span class="sxs-lookup"><span data-stu-id="3ec60-115">Check and download operating system updates to all Cloud Connector VMs.</span></span> 
    
  - <span data-ttu-id="3ec60-116">逐個安裝和更新所有雲端連接器 Vm，然後重新開機。</span><span class="sxs-lookup"><span data-stu-id="3ec60-116">Install and update all Cloud Connector VMs one by one and restart.</span></span>
    
  - <span data-ttu-id="3ec60-117">在雲端連接器 Vm 重新開機之後，請查看是否需要重新開機另一個。</span><span class="sxs-lookup"><span data-stu-id="3ec60-117">After the Cloud Connector VMs restart, check to see if another restart is needed.</span></span>
    
  - <span data-ttu-id="3ec60-118">成功修復雲端連接器 Vm 後，請針對雲端連接器主機機器重複此程式。</span><span class="sxs-lookup"><span data-stu-id="3ec60-118">After the Cloud Connector VMs have been successfully patched, repeat the process for the Cloud Connector host machine.</span></span>
    
  - <span data-ttu-id="3ec60-119">成功啟動雲端連接器主機電腦之後，就會完成任何未完成的作業系統更新任務。</span><span class="sxs-lookup"><span data-stu-id="3ec60-119">After the Cloud Connector host machine successfully boots up, any outstanding operating system update tasks are completed.</span></span>
    
- <span data-ttu-id="3ec60-120">雲端連接器更新任務</span><span class="sxs-lookup"><span data-stu-id="3ec60-120">Cloud Connector update tasks</span></span>
    
  - <span data-ttu-id="3ec60-121">從下載網站下載並檢查版本檔案。</span><span class="sxs-lookup"><span data-stu-id="3ec60-121">Download and check the version file from the download site.</span></span>
    
  - <span data-ttu-id="3ec60-122">下載新的版本 .msi 檔案。</span><span class="sxs-lookup"><span data-stu-id="3ec60-122">Download the new version .msi file.</span></span> 
    
  - <span data-ttu-id="3ec60-123">卸載舊的 msi 檔案;安裝新的 msi 檔案。</span><span class="sxs-lookup"><span data-stu-id="3ec60-123">Uninstall the old msi file; install the new msi file.</span></span>
    
  - <span data-ttu-id="3ec60-124">下載新版本的商務用 Skype bits。</span><span class="sxs-lookup"><span data-stu-id="3ec60-124">Download the new version of Skype for Business bits.</span></span>
    
  - <span data-ttu-id="3ec60-125">呼叫 CcAppliance 註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="3ec60-125">Register the appliance by calling Register-CcAppliance.</span></span>
    
  - <span data-ttu-id="3ec60-126">安裝新的雲端連接器版本。</span><span class="sxs-lookup"><span data-stu-id="3ec60-126">Install the new Cloud Connector version.</span></span>
    
  - <span data-ttu-id="3ec60-127">排出舊裝置，並將網路連接切換至新裝置。</span><span class="sxs-lookup"><span data-stu-id="3ec60-127">Drain the old appliance and switch the network connection to the new appliance.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="3ec60-128">當 Cloud Connector 更新至新的組建時，可能不會更新雲端連接器 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3ec60-128">When Cloud Connector updates to a new build, Cloud Connector cmdlets might not be updated.</span></span> <span data-ttu-id="3ec60-129">例如，如果在執行自動更新時，會讓 PowerShell 視窗保持開啟狀態，就會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="3ec60-129">This can happen, for example, if a PowerShell window is left open while automatic update occurs.</span></span> <span data-ttu-id="3ec60-130">若要載入更新的指令程式，您可以執行下列其中一個步驟： > 在雲端連接器裝置上關閉 PowerShell，然後重新開啟 PowerShell。 > 或，您可以執行 Import-Module CloudConnector-Force。</span><span class="sxs-lookup"><span data-stu-id="3ec60-130">To load the updated cmdlets, you can do either of the following steps:>  Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.>  Or, you can run Import-Module CloudConnector -Force.</span></span>
  
## <a name="upgrade-a-single-site-to-a-new-version"></a><span data-ttu-id="3ec60-131">將單一網站升級為新版本</span><span class="sxs-lookup"><span data-stu-id="3ec60-131">Upgrade a single site to a new version</span></span>
<span data-ttu-id="3ec60-132"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="3ec60-132"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="3ec60-133">如果您要升級的網站中只有一個裝置，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="3ec60-133">If there is only one appliance in the site you want to upgrade, do the following:</span></span>
  
1. <span data-ttu-id="3ec60-134">在 [控制台] 的 [程式 **\> \> 和功能**] 中卸載現有的雲端連接器版本。</span><span class="sxs-lookup"><span data-stu-id="3ec60-134">Uninstall the existing Cloud Connector version in **Control Panel \> Programs \> Programs and Features**.</span></span>
    
2. <span data-ttu-id="3ec60-135">從安裝新版本的 CloudConnector.msi [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) 。</span><span class="sxs-lookup"><span data-stu-id="3ec60-135">Install the new version of CloudConnector.msi from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span>
    
3. <span data-ttu-id="3ec60-136">確認您已安裝版本的 CloudConnector.ini 檔案，且已更新環境所需的所有值。</span><span class="sxs-lookup"><span data-stu-id="3ec60-136">Confirm that you have the CloudConnector.ini file for the version you are installing, and that you have updated all of the required values for your environment.</span></span> <span data-ttu-id="3ec60-137">您無法使用舊版本中的 .ini 檔案。</span><span class="sxs-lookup"><span data-stu-id="3ec60-137">You cannot use the .ini file from a previous release.</span></span> <span data-ttu-id="3ec60-138">如果您要升級 Cloud Connector，請參閱主題 Prepare a [Cloud connector 裝置](prepare-your-cloud-connector-appliance.md) ，並確認 SiteName 和 EnableReferSupport 設定為正確的 CloudConnector.ini 檔案中的值。</span><span class="sxs-lookup"><span data-stu-id="3ec60-138">If you are upgrading Cloud Connector, please refer to the topic [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md) and make sure SiteName and EnableReferSupport are set to the correct value in the CloudConnector.ini file.</span></span>
    
4. <span data-ttu-id="3ec60-139">以系統管理員身分啟動 PowerShell 主控台，並執行下列 Cmdlet 來註冊目前的裝置：</span><span class="sxs-lookup"><span data-stu-id="3ec60-139">Start a PowerShell console as administrator and run the following cmdlet to register the current appliance:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

5. <span data-ttu-id="3ec60-140">執行下列 Cmdlet 以下載最新版本：</span><span class="sxs-lookup"><span data-stu-id="3ec60-140">Run the following cmdlet to download the latest version:</span></span>
    
   ```powershell
   Start-CcDownload
   ```

6. <span data-ttu-id="3ec60-141">執行下列 Cmdlet 來開始安裝：</span><span class="sxs-lookup"><span data-stu-id="3ec60-141">Run the following cmdlet to start the installation:</span></span> 
    
   ```powershell
   Install-CcAppliance -Upgrade
   ```

7. <span data-ttu-id="3ec60-142">執行下列 Cmdlet 以啟動新的部署並關閉先前版本：</span><span class="sxs-lookup"><span data-stu-id="3ec60-142">Run the following cmdlet to activate the new deployment and turn off the previous version:</span></span>
    
   ```powershell
   Switch-CcVersion
   ```

<span data-ttu-id="3ec60-143">如果網站中有一個以上的裝置，請依照上述步驟逐個升級每一個裝置。</span><span class="sxs-lookup"><span data-stu-id="3ec60-143">If there is more than one appliance in the site, please follow the preceding steps to upgrade each appliance one by one.</span></span>
  
<span data-ttu-id="3ec60-144">如果您想要更新域管理員、虛擬機器管理員、安全模式管理員及承租人系統管理員認證，您可以使用  _UpdateAllCredentials_ 參數來執行 Cmdlet，以重設所有認證：</span><span class="sxs-lookup"><span data-stu-id="3ec60-144">If you want to update Domain administrator, Virtual machine administrator, Safe Mode administrator and Tenant administrator credentials, you can run the cmdlet with the  _UpdateAllCredentials_ parameter to reset all credentials:</span></span>
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

<span data-ttu-id="3ec60-145">然後，當您開始升級為新版本時，您將會提升以輸入新的認證。</span><span class="sxs-lookup"><span data-stu-id="3ec60-145">Then, when you start to upgrade to a new version, you will be promoted to input the new credentials.</span></span> 
  
<span data-ttu-id="3ec60-146">如果您只想要重設租使用者系統管理員認證，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3ec60-146">If you only want to reset your Tenant administrator credentials, run the following cmdlet:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a><span data-ttu-id="3ec60-147">將多個網站升級至新版本</span><span class="sxs-lookup"><span data-stu-id="3ec60-147">Upgrade multiple sites to a new version</span></span>
<span data-ttu-id="3ec60-148"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="3ec60-148"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="3ec60-149">遵循升級單一網站的步驟，一次為部署中的每個網站升級一個網站。</span><span class="sxs-lookup"><span data-stu-id="3ec60-149">Follow the steps for upgrading a single site, upgrading one site at a time for each site in your deployment.</span></span> <span data-ttu-id="3ec60-150">升級每個網站後，請確定並 [驗證您的雲端連接器部署](validate-your-cloud-connector-deployment.md) 。</span><span class="sxs-lookup"><span data-stu-id="3ec60-150">Make sure and [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) after upgrading each site.</span></span>
