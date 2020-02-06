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
description: 瞭解如何升級雲端連接器版本部署。
ms.openlocfilehash: d2f9d2a2720f67a2110ba97b7d100e5673a0015c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814141"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a><span data-ttu-id="6f266-103">升級至新版 Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="6f266-103">Upgrade to a new version of Cloud Connector</span></span>
 
<span data-ttu-id="6f266-104">瞭解如何升級雲端連接器版本部署。</span><span class="sxs-lookup"><span data-stu-id="6f266-104">Learn about how to upgrade your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="6f266-105">如果您已設定線上管理租使用者帳戶並啟用自動更新，您現有的商務用 Skype 雲端連接器版本部署將會根據您的自動更新時間範圍，自動升級至較新的版本configuration.</span><span class="sxs-lookup"><span data-stu-id="6f266-105">If you have set up an online management tenant account and enabled automatic updates, your existing deployment of Skype for Business Cloud Connector Edition will be upgraded to the newer version automatically—according to your automatic update time window configuration.</span></span> <span data-ttu-id="6f266-106">您也可以執行手動升級。</span><span class="sxs-lookup"><span data-stu-id="6f266-106">You can also perform a manual upgrade.</span></span> 
  
<span data-ttu-id="6f266-107">雲端連接器版本1.4.1 及更新版本會預設執行自動更新。</span><span class="sxs-lookup"><span data-stu-id="6f266-107">Cloud Connector Edition versions 1.4.1 and later perform automatic updates by default.</span></span> <span data-ttu-id="6f266-108">如果您想手動升級至最新版本（2.1），請參閱本主題稍後的[將單一網站升級至新版本](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade)。</span><span class="sxs-lookup"><span data-stu-id="6f266-108">If you want to upgrade to the latest version (2.1) manually, see [Upgrade a single site to a new version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) later in this topic.</span></span>
  
<span data-ttu-id="6f266-109">自動更新：需要雲端連接器服務正在執行。</span><span class="sxs-lookup"><span data-stu-id="6f266-109">Automatic update requires that the Cloud Connector service is running.</span></span> <span data-ttu-id="6f266-110">下列步驟說明自動更新的程式：</span><span class="sxs-lookup"><span data-stu-id="6f266-110">The following steps describe the process for automatic updates:</span></span>
  
- <span data-ttu-id="6f266-111">自動更新程式將根據您為自動更新所設定的排程來執行。</span><span class="sxs-lookup"><span data-stu-id="6f266-111">The automatic update process will run according to the schedule you have configured for automatic updates.</span></span>
    
- <span data-ttu-id="6f266-112">作業系統更新任務</span><span class="sxs-lookup"><span data-stu-id="6f266-112">Operating system update tasks</span></span>
    
  - <span data-ttu-id="6f266-113">檢查並下載適用于所有雲端連接器 Vm 的作業系統更新。</span><span class="sxs-lookup"><span data-stu-id="6f266-113">Check and download operating system updates to all Cloud Connector VMs.</span></span> 
    
  - <span data-ttu-id="6f266-114">逐一安裝並更新所有雲端連接器 Vm，然後重新開機。</span><span class="sxs-lookup"><span data-stu-id="6f266-114">Install and update all Cloud Connector VMs one by one and restart.</span></span>
    
  - <span data-ttu-id="6f266-115">重新開機雲端連接器 Vm 之後，請檢查是否需要另一個重新開機。</span><span class="sxs-lookup"><span data-stu-id="6f266-115">After the Cloud Connector VMs restart, check to see if another restart is needed.</span></span>
    
  - <span data-ttu-id="6f266-116">成功修正雲端連接器 Vm 之後，請重複執行雲端連接器主機電腦的程式。</span><span class="sxs-lookup"><span data-stu-id="6f266-116">After the Cloud Connector VMs have been successfully patched, repeat the process for the Cloud Connector host machine.</span></span>
    
  - <span data-ttu-id="6f266-117">雲端連接器主機電腦成功啟動之後，所有未完成的作業系統更新工作都會完成。</span><span class="sxs-lookup"><span data-stu-id="6f266-117">After the Cloud Connector host machine successfully boots up, any outstanding operating system update tasks are completed.</span></span>
    
- <span data-ttu-id="6f266-118">雲端連接器更新任務</span><span class="sxs-lookup"><span data-stu-id="6f266-118">Cloud Connector update tasks</span></span>
    
  - <span data-ttu-id="6f266-119">從下載網站下載並檢查版本檔案。</span><span class="sxs-lookup"><span data-stu-id="6f266-119">Download and check the version file from the download site.</span></span>
    
  - <span data-ttu-id="6f266-120">下載新的版本 .msi 檔案。</span><span class="sxs-lookup"><span data-stu-id="6f266-120">Download the new version .msi file.</span></span> 
    
  - <span data-ttu-id="6f266-121">卸載舊的 msi 檔案;安裝新的 msi 檔案。</span><span class="sxs-lookup"><span data-stu-id="6f266-121">Uninstall the old msi file; install the new msi file.</span></span>
    
  - <span data-ttu-id="6f266-122">下載新版本的商務用 Skype bits。</span><span class="sxs-lookup"><span data-stu-id="6f266-122">Download the new version of Skype for Business bits.</span></span>
    
  - <span data-ttu-id="6f266-123">呼叫 CcAppliance 註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="6f266-123">Register the appliance by calling Register-CcAppliance.</span></span>
    
  - <span data-ttu-id="6f266-124">安裝新的雲端連接器版本。</span><span class="sxs-lookup"><span data-stu-id="6f266-124">Install the new Cloud Connector version.</span></span>
    
  - <span data-ttu-id="6f266-125">排出舊裝置，並將網路連線切換至新裝置。</span><span class="sxs-lookup"><span data-stu-id="6f266-125">Drain the old appliance and switch the network connection to the new appliance.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="6f266-126">當雲端連接器更新至新組建時，可能無法更新雲端連接器 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6f266-126">When Cloud Connector updates to a new build, Cloud Connector cmdlets might not be updated.</span></span> <span data-ttu-id="6f266-127">例如，如果在自動更新發生時，將會保持開啟 PowerShell 視窗，就會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="6f266-127">This can happen, for example, if a PowerShell window is left open while automatic update occurs.</span></span> <span data-ttu-id="6f266-128">若要載入更新的 Cmdlet，您可以執行下列其中一項步驟： > 在雲端連接器裝置上關閉 PowerShell，然後重新開啟 PowerShell。 > 或，您可以執行匯入-Module CloudConnector-Force。</span><span class="sxs-lookup"><span data-stu-id="6f266-128">To load the updated cmdlets, you can do either of the following steps:>  Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.>  Or, you can run Import-Module CloudConnector -Force.</span></span>
  
## <a name="upgrade-a-single-site-to-a-new-version"></a><span data-ttu-id="6f266-129">將單一網站升級為新的版本</span><span class="sxs-lookup"><span data-stu-id="6f266-129">Upgrade a single site to a new version</span></span>
<span data-ttu-id="6f266-130"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="6f266-130"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="6f266-131">如果您想要升級的網站中只有一個裝置，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="6f266-131">If there is only one appliance in the site you want to upgrade, do the following:</span></span>
  
1. <span data-ttu-id="6f266-132">在 [\*\*控制台\> \> \*\*] 的 [程式和功能] 中卸載現有的雲端連接器版本。</span><span class="sxs-lookup"><span data-stu-id="6f266-132">Uninstall the existing Cloud Connector version in **Control Panel \> Programs \> Programs and Features**.</span></span>
    
2. <span data-ttu-id="6f266-133">從[https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)安裝新版本的 CloudConnector。</span><span class="sxs-lookup"><span data-stu-id="6f266-133">Install the new version of CloudConnector.msi from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span>
    
3. <span data-ttu-id="6f266-134">確認您已安裝您要安裝的版本的 CloudConnector 檔案，並已更新您的環境所需的所有值。</span><span class="sxs-lookup"><span data-stu-id="6f266-134">Confirm that you have the CloudConnector.ini file for the version you are installing, and that you have updated all of the required values for your environment.</span></span> <span data-ttu-id="6f266-135">您無法從先前的發行版本中使用 .ini 檔案。</span><span class="sxs-lookup"><span data-stu-id="6f266-135">You cannot use the .ini file from a previous release.</span></span> <span data-ttu-id="6f266-136">如果您要升級雲端連接器，請參閱[準備雲端連接器裝置](prepare-your-cloud-connector-appliance.md)主題，確定 SiteName 與 EnableReferSupport 已在 CloudConnector 檔案中設定正確的值。</span><span class="sxs-lookup"><span data-stu-id="6f266-136">If you are upgrading Cloud Connector, please refer to the topic [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md) and make sure SiteName and EnableReferSupport are set to the correct value in the CloudConnector.ini file.</span></span>
    
4. <span data-ttu-id="6f266-137">以系統管理員身分啟動 PowerShell 主控台，並執行下列 Cmdlet 來註冊目前的裝置：</span><span class="sxs-lookup"><span data-stu-id="6f266-137">Start a PowerShell console as administrator and run the following cmdlet to register the current appliance:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

5. <span data-ttu-id="6f266-138">執行下列 Cmdlet 以下載最新版本：</span><span class="sxs-lookup"><span data-stu-id="6f266-138">Run the following cmdlet to download the latest version:</span></span>
    
   ```powershell
   Start-CcDownload
   ```

6. <span data-ttu-id="6f266-139">執行下列 Cmdlet 以開始安裝：</span><span class="sxs-lookup"><span data-stu-id="6f266-139">Run the following cmdlet to start the installation:</span></span> 
    
   ```powershell
   Install-CcAppliance -Upgrade
   ```

7. <span data-ttu-id="6f266-140">執行下列 Cmdlet 以啟動新的部署，然後關閉舊版：</span><span class="sxs-lookup"><span data-stu-id="6f266-140">Run the following cmdlet to activate the new deployment and turn off the previous version:</span></span>
    
   ```powershell
   Switch-CcVersion
   ```

<span data-ttu-id="6f266-141">如果網站中有一個以上的裝置，請依照上述步驟逐一升級每個裝置。</span><span class="sxs-lookup"><span data-stu-id="6f266-141">If there is more than one appliance in the site, please follow the preceding steps to upgrade each appliance one by one.</span></span>
  
<span data-ttu-id="6f266-142">如果您想要更新網域系統管理員、虛擬機器系統管理員、安全模式管理員和租使用者管理員認證，您可以使用_UpdateAllCredentials_參數執行 Cmdlet，以重設所有認證：</span><span class="sxs-lookup"><span data-stu-id="6f266-142">If you want to update Domain administrator, Virtual machine administrator, Safe Mode administrator and Tenant administrator credentials, you can run the cmdlet with the  _UpdateAllCredentials_ parameter to reset all credentials:</span></span>
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

<span data-ttu-id="6f266-143">接著，當您開始升級至新版本時，您將會升級，以輸入新的認證。</span><span class="sxs-lookup"><span data-stu-id="6f266-143">Then, when you start to upgrade to a new version, you will be promoted to input the new credentials.</span></span> 
  
<span data-ttu-id="6f266-144">如果您只想要重設您的租使用者系統管理員認證，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="6f266-144">If you only want to reset your Tenant administrator credentials, run the following cmdlet:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a><span data-ttu-id="6f266-145">將多個網站升級至新版本</span><span class="sxs-lookup"><span data-stu-id="6f266-145">Upgrade multiple sites to a new version</span></span>
<span data-ttu-id="6f266-146"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="6f266-146"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="6f266-147">遵循升級單一網站的步驟，一次為部署中的每個網站升級一個網站。</span><span class="sxs-lookup"><span data-stu-id="6f266-147">Follow the steps for upgrading a single site, upgrading one site at a time for each site in your deployment.</span></span> <span data-ttu-id="6f266-148">在升級每個網站之後，請確認並[驗證您的雲端連接器部署](validate-your-cloud-connector-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="6f266-148">Make sure and [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) after upgrading each site.</span></span>
  

