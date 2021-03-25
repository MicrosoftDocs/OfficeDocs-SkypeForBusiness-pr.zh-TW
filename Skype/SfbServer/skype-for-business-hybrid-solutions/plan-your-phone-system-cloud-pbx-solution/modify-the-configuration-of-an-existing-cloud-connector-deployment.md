---
title: 修改現有 Cloud Connector 部署的組態
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: 遵循此主題中的步驟，修改現有商務用 Skype 雲端連接器 Edition 1.4.1 或更新版本的設定。
ms.openlocfilehash: 7fdfdd5ac5a76ebbc3ac58e12a69e2e3af1330cd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109169"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a><span data-ttu-id="b6a6f-103">修改現有 Cloud Connector 部署的組態</span><span class="sxs-lookup"><span data-stu-id="b6a6f-103">Modify the configuration of an existing Cloud Connector deployment</span></span>

> [!Important]
> <span data-ttu-id="b6a6f-104">雲端連接器 Edition 會于2021年7月31日和商務用 Skype Online 終止。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="b6a6f-105">當您的組織升級至小組後，請瞭解如何使用 [直接路由](/MicrosoftTeams/direct-routing-landing-page)將您的內部部署電話語音網路連線到小組。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="b6a6f-106">遵循此主題中的步驟，修改現有商務用 Skype 雲端連接器 Edition 1.4.1 或更新版本的設定。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-106">Follow the steps in this topic to modify the configuration of an existing Skype for Business Cloud Connector Edition 1.4.1 or later deployment.</span></span> 
  
## <a name="modify-the-configuration-of-a-single-site"></a><span data-ttu-id="b6a6f-107">修改單一網站的設定</span><span class="sxs-lookup"><span data-stu-id="b6a6f-107">Modify the configuration of a single site</span></span>
<span data-ttu-id="b6a6f-108"><a name="BKMK_SIngleSite"> </a></span><span class="sxs-lookup"><span data-stu-id="b6a6f-108"><a name="BKMK_SIngleSite"> </a></span></span>

<span data-ttu-id="b6a6f-109">如果網站中只有一個裝置，當您想要在部署裝置之後變更設定設定時，您可以修改 CloudConnector.ini 檔案，然後重新開機部署。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-109">If there is only one appliance in the site, when you want to change the configuration settings after the appliance is deployed, you can modify the CloudConnector.ini file and start the deployment again.</span></span>
  
1. <span data-ttu-id="b6a6f-110">執行下列 Cmdlet，以卸載主機伺服器上的所有現有虛擬機器：</span><span class="sxs-lookup"><span data-stu-id="b6a6f-110">Run the following cmdlet to uninstall all existing virtual machines on the host server:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="b6a6f-111">執行下列 Cmdlet 以取消登錄裝置：</span><span class="sxs-lookup"><span data-stu-id="b6a6f-111">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="b6a6f-112">更新裝置目錄中的 CloudConnector.ini 檔案。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-112">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="b6a6f-113">執行下列 Cmdlet 來更新設定： (此步驟僅適用于版本 2;若為舊版，請跳至下一個步驟。 ) </span><span class="sxs-lookup"><span data-stu-id="b6a6f-113">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="b6a6f-114">請執行下列 Cmdlet 重新註冊裝置：</span><span class="sxs-lookup"><span data-stu-id="b6a6f-114">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="b6a6f-115">執行下列 Cmdlet 以安裝商務用 Skype Cloud Connector Edition：</span><span class="sxs-lookup"><span data-stu-id="b6a6f-115">Run the following cmdlet to install Skype for Business Cloud Connector Edition:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

<span data-ttu-id="b6a6f-116">如果網站中有一個以上的裝置，您必須遵循下列步驟，修改 CloudConnector.ini 檔案，然後逐個重新部署裝置。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-116">If there is more than one appliance in the site, you'll need to follow these steps, modify the CloudConnector.ini file, and redeploy the appliances one by one.</span></span>
  
1. <span data-ttu-id="b6a6f-117">執行下列 Cmdlet，以卸載目前裝置上的所有現有虛擬機器：</span><span class="sxs-lookup"><span data-stu-id="b6a6f-117">Run the following cmdlet to uninstall all existing virtual machines on the current appliance:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="b6a6f-118">執行下列 Cmdlet 以取消登錄裝置：</span><span class="sxs-lookup"><span data-stu-id="b6a6f-118">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="b6a6f-119">更新裝置目錄中的 CloudConnector.ini 檔案。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-119">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="b6a6f-120">執行下列 Cmdlet 來更新設定： (此步驟僅適用于版本 2;若為舊版，請跳至下一個步驟。 ) </span><span class="sxs-lookup"><span data-stu-id="b6a6f-120">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="b6a6f-121">請執行下列 Cmdlet 重新註冊裝置：</span><span class="sxs-lookup"><span data-stu-id="b6a6f-121">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="b6a6f-122">在網站中的所有其他裝置上執行下列 Cmdlet，以挑選最新的設定：</span><span class="sxs-lookup"><span data-stu-id="b6a6f-122">Run the following cmdlet on all other appliances in the site to pick up the latest configuration:</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

7. <span data-ttu-id="b6a6f-123">在目前的裝置上執行下列 Cmdlet 重新部署雲端連接器：</span><span class="sxs-lookup"><span data-stu-id="b6a6f-123">Run the following cmdlet to redeploy Cloud Connector on the current appliance:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a><span data-ttu-id="b6a6f-124">修改多個網站的設定</span><span class="sxs-lookup"><span data-stu-id="b6a6f-124">Modify the configuration of multiple sites</span></span>
<span data-ttu-id="b6a6f-125"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="b6a6f-125"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="b6a6f-126">若要在部署中修改多個網站的設定，請遵循單一網站的步驟，一次更新一個網站。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-126">To modify the configuration for multiple sites in a deployment, follow the steps for a single site, updating one site at a time.</span></span>
  
## <a name="modify-the-configuration-of-your-microsoft-365-or-office-365-organization-to-enable-automatic-updates"></a><span data-ttu-id="b6a6f-127">修改 Microsoft 365 或 Office 365 組織的設定以啟用自動更新</span><span class="sxs-lookup"><span data-stu-id="b6a6f-127">Modify the configuration of your Microsoft 365 or Office 365 organization to enable automatic updates</span></span>
<span data-ttu-id="b6a6f-128"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="b6a6f-128"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="b6a6f-129">若要啟用作業系統自動更新和 Bits 自動更新，您必須使用商務用 Skype 租使用者系統管理員帳戶進行線上管理，並使用租使用者遠端 PowerShell，如下所示。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-129">To enable operating system automatic updates and Bits automatic updates, you must use the Skype for Business tenant admin account for online management and use tenant remote PowerShell as follows.</span></span>
  
<span data-ttu-id="b6a6f-130">如果您停用作業系統自動更新或 Bits 自動更新，您的主機和虛擬機器可能會錯過重要的 Windows 更新，而雲端連接器將無法自動升級為新的版本。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-130">If you disabled operating system automatic updates or Bits automatic updates, your host and virtual machine may miss important Windows updates, and Cloud Connector will not upgrade to the new version automatically.</span></span> <span data-ttu-id="b6a6f-131">強烈建議您啟用自動更新。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-131">It is highly recommended that you enable automatic updates.</span></span>
  
1. <span data-ttu-id="b6a6f-132">網站的 EnableAutoUpdate 屬性必須設定為 true (預設值) 。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-132">The EnableAutoUpdate property of the site needs to be set to true (the default value).</span></span> <span data-ttu-id="b6a6f-133">請執行下列 Cmdlet，確定 EnableAutoUpdate 設定為 true：</span><span class="sxs-lookup"><span data-stu-id="b6a6f-133">Run the following cmdlet to make sure EnableAutoUpdate is set to true:</span></span>
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. <span data-ttu-id="b6a6f-134">建立租使用者的自動更新時間範圍。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-134">Create auto update time window for the tenant.</span></span>
    
    <span data-ttu-id="b6a6f-135">時段可以是每天、每週及每月。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-135">The time window can be daily, weekly and monthly.</span></span> <span data-ttu-id="b6a6f-136">Windows 所有的時間都需要開始時間和持續時間。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-136">All the time windows need a start time and a duration.</span></span>
    
   - <span data-ttu-id="b6a6f-137">針對每日時段，只需要開始時間和持續時間。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-137">For a daily time window, only start time and duration are needed.</span></span> 
    
   - <span data-ttu-id="b6a6f-138">若為每週時段，需要天數，其可為一天或多天。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-138">For a weekly time window, days of week are needed, which can be a single day or multiple days.</span></span>
    
   - <span data-ttu-id="b6a6f-139">在每月的時段中，可能會有兩種類型。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-139">For a monthly time window, there can be two types.</span></span> <span data-ttu-id="b6a6f-140">第一種類型是指定一月中的第幾天，也就是一天。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-140">The first type is to specify the day of the month, which can be a single day.</span></span> <span data-ttu-id="b6a6f-141">第二種類型是指定每月的周數，也就是一周中的天數，這兩者都可以是單一專案或多個專案。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-141">The second type is to specify the weeks of the month, along with days of the week, which both can be a single item or multiple items.</span></span>
    
   - <span data-ttu-id="b6a6f-142">每個租使用者可定義20個時間視窗。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-142">Each tenant can have 20 time windows defined.</span></span> <span data-ttu-id="b6a6f-143">將新租使用者的預設時段，當作作業系統更新和 Bits 更新的預設時間範圍而建立。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-143">The default time window will be created for a new tenant as the default time window for operating system update and Bits update.</span></span> <span data-ttu-id="b6a6f-144">執行下列 Cmdlet (s) 設定每日、每週或每月的時間範圍：</span><span class="sxs-lookup"><span data-stu-id="b6a6f-144">Run the following cmdlet(s) to set the daily, weekly or monthly time window:</span></span>
    
   ```powershell
   New-CsTenantUpdateTimeWindow -Identity Night -Daily -StartTime 22:00 -Duration 6:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity WeekdayNight -Weekly -DaysOfWeek Monday,Tuesday,Wednesday,Thursday,Friday -StartTime 22:00 -Duration 4:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity FirstAndLastWeekend -Monthly -WeeksOfMonth First,Last -DaysOfWeek Sunday,Saturday -StartTime 0:00 -Duration 10:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity MidDayOfMonth -Monthly -DayOfMonth 15 -StartTime 0:00 -Duration 1.00:00
   ```

   - <span data-ttu-id="b6a6f-145">將更新時間視窗指派至網站。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-145">Assign update time windows to the site.</span></span> 
    
     <span data-ttu-id="b6a6f-146">會個別設定 Bits 更新時間與 OS 更新時間視窗。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-146">The Bits update time and OS update time windows are configured separately.</span></span> <span data-ttu-id="b6a6f-147">這兩者都可以指派一或多個時間視窗。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-147">Both of them can be assigned single or multiple time windows.</span></span> <span data-ttu-id="b6a6f-148">每個時段都可以指派至不同的網站，而不同的目的 (Bits 更新和 OS 更新) 。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-148">Each time window can be assigned to different sites and different purpose (Bits update and OS update).</span></span> <span data-ttu-id="b6a6f-149">執行下列 Cmdlet 來設定網站的時間範圍：</span><span class="sxs-lookup"><span data-stu-id="b6a6f-149">Run the following cmdlet to set the time window for the site:</span></span> 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a><span data-ttu-id="b6a6f-150">更新專用的租使用者系統管理員認證</span><span class="sxs-lookup"><span data-stu-id="b6a6f-150">Update the dedicated tenant admin credentials</span></span>
<span data-ttu-id="b6a6f-151"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="b6a6f-151"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="b6a6f-152">您可以使用具有必要許可權的帳戶，從 Microsoft 365 或 Office 365 組織中的雲端連接器進行管理變更。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-152">Administrative changes in the Microsoft 365 or Office 365 organization for Cloud Connector are made from an account with the needed permissions.</span></span> <span data-ttu-id="b6a6f-153">在2.0 之前的雲端連接器版本中，該帳戶是專用的全域租使用者管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-153">In Cloud Connector versions before 2.0, that account is a dedicated global tenant admin account.</span></span> <span data-ttu-id="b6a6f-154">在雲端連接器版本2.0 和更新版本中，該帳戶可以是具有商務用 Skype 系統管理員許可權的 Microsoft 365 或 Office 365 帳戶。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-154">In Cloud Connector versions 2.0 and later, that account can be a Microsoft 365 or Office 365 account with Skype for Business Administrator rights.</span></span>
  
<span data-ttu-id="b6a6f-155">如果您的系統管理員帳號憑證變更于 Microsoft 365 或 Office 365，您也需要在您已部署的每個雲端連接器裝置上執行下列管理員 PowerShell 命令，以更新雲端連接器中的本機快取認證：</span><span class="sxs-lookup"><span data-stu-id="b6a6f-155">If your admin account credentials change in Microsoft 365 or Office 365, you also need to update the locally cached credentials in Cloud Connector by running the following Administrator PowerShell command on each Cloud Connector appliance you have deployed:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a><span data-ttu-id="b6a6f-156">更新主伺服器的密碼</span><span class="sxs-lookup"><span data-stu-id="b6a6f-156">Update the password for the host server</span></span>
<span data-ttu-id="b6a6f-157"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="b6a6f-157"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="b6a6f-158">本節適用于雲端連接器版本2.0 和更新版本。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-158">This section is applicable to Cloud Connector version 2.0 and later.</span></span> 
  
<span data-ttu-id="b6a6f-159">所有雲端連接器認證都儲存在下列檔案中： "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> 。xml "。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-159">All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="b6a6f-160">當主伺服器上的密碼變更時，您將需要更新本機儲存的認證。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-160">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
  
<span data-ttu-id="b6a6f-161">若要在雲端連接器裝置上更新本機儲存的認證，請使用 [CcCredential](get-cccredential.md) 和 [CcCredential](set-cccredential.md) 指令程式，然後遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="b6a6f-161">To update the locally stored credentials on the Cloud Connector appliance, use the [Get-CcCredential](get-cccredential.md) and [Set-CcCredential](set-cccredential.md) cmdlets and follow these steps:</span></span>
  
1. <span data-ttu-id="b6a6f-162">執行下列命令，以取得稍後需要的密碼：</span><span class="sxs-lookup"><span data-stu-id="b6a6f-162">Run the following commands to retrieve the passwords you will need later:</span></span> 
    
   - <span data-ttu-id="b6a6f-163">Get-CcCredential AccountType DomainAdmin-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="b6a6f-163">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="b6a6f-164">Get-CcCredential AccountType VMAdmin-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="b6a6f-164">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="b6a6f-165">Get-CcCredential AccountType CceService-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="b6a6f-165">Get-CcCredential -AccountType CceService -DisplayPassword</span></span>
    
2. <span data-ttu-id="b6a6f-166">變更您的帳戶在主伺服器上的密碼。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-166">Change the password of your account on the host server.</span></span>
    
3. <span data-ttu-id="b6a6f-167">重新開機主機伺服器。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-167">Restart the host server.</span></span>
    
4. <span data-ttu-id="b6a6f-168">刪除下列檔案： "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> 。xml "。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-168">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
5. <span data-ttu-id="b6a6f-169">以系統管理員身分啟動 PowerShell 主控台，然後執行「Register-CcAppliance-Local」，以在描述之後重新輸入密碼。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-169">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="b6a6f-170">請確定輸入的密碼與您在雲端連接器部署之前輸入的密碼相同。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-170">Be sure you enter the same password you entered before for the Cloud Connector deployment.</span></span>
    
<span data-ttu-id="b6a6f-171">根據預設，VmAdmin 和 DomainAdmin 會使用與 CceService 相同的密碼。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-171">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="b6a6f-172">如果步驟1中傳回的 DomainAdmin、VMAdmin 和 CceService 密碼不同，您必須執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="b6a6f-172">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
  
1. <span data-ttu-id="b6a6f-173">執行 Set-CcCredential AccountType DomainAdmin，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b6a6f-173">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="b6a6f-174">當系統提示您輸入舊帳號憑證時，請輸入您用於 CceService 密碼的認證。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-174">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="b6a6f-175">當系統提示您輸入新的帳號憑證時，請輸入步驟1中所傳回之 DomainAdmin 密碼的密碼。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-175">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
2. <span data-ttu-id="b6a6f-176">執行 Set-CcCredential AccountType VmAdmin，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b6a6f-176">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="b6a6f-177">當系統提示您輸入舊帳號憑證時，請輸入您用於 CceService 密碼的認證。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-177">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="b6a6f-178">當系統提示您輸入新的帳號憑證時，請輸入步驟1中所傳回之 VmAdmin 密碼的密碼。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-178">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
## <a name="update-the-password-for-the-cceservice-account"></a><span data-ttu-id="b6a6f-179">更新 CceService 帳戶的密碼</span><span class="sxs-lookup"><span data-stu-id="b6a6f-179">Update the password for the CceService account</span></span>
<span data-ttu-id="b6a6f-180"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="b6a6f-180"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="b6a6f-181">本節適用于雲端連接器2.0.1 版及更新版本。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-181">This section is applicable to Cloud Connector version 2.0.1 and later.</span></span> 
  
<span data-ttu-id="b6a6f-182">雲端連接器服務會執行雲端連接器管理服務。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-182">The Cloud Connector service runs the Cloud Connector Management service.</span></span> <span data-ttu-id="b6a6f-183">在雲端連接器版本部署期間建立 CceService 帳戶，並儲存在下列檔案中： "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> 。xml "和"% 系統磁片% \Programdata\Cloudconnector\credentials..CceService.xml "。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-183">The CceService account is created during the Cloud Connector Edition deployment and stored in the following files: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" and "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span></span>
  
<span data-ttu-id="b6a6f-184">為了確保所有裝置都可以存取網站目錄共用，CceService 帳戶的密碼在網站中部署的所有裝置上都必須相同。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-184">To ensure that all appliances can access the site directory share, the password for the CceService account must be the same on all appliances deployed within the site.</span></span> <span data-ttu-id="b6a6f-185">請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="b6a6f-185">Keep the following in mind:</span></span>
  
- <span data-ttu-id="b6a6f-186">根據預設，CceService 帳戶會設定為「密碼永不到期」。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-186">By default, the CceService account is configured as "Password never expires".</span></span> <span data-ttu-id="b6a6f-187">當您更新密碼時，Microsoft 建議您保留此設定。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-187">When you update the password, Microsoft recommends keeping this configuration.</span></span>
    
- <span data-ttu-id="b6a6f-188">您應該在非峰值使用期間更新密碼，並在自動更新時間範圍外更新 bits 或 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-188">You should update the password during non-peak usage periods and outside of automatic update time windows for bits or Windows updates.</span></span> <span data-ttu-id="b6a6f-189">當您更新密碼時，裝置必須耗盡並重新啟動，這需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-189">When you update the password, the appliance needs to be drained and restarted, which takes some time.</span></span> <span data-ttu-id="b6a6f-190">重新開機裝置會中斷自動更新作業。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-190">Restarting the appliance will interrupt automatic update operations.</span></span> 
    
- <span data-ttu-id="b6a6f-191">當您變更 CceService 帳戶密碼時，您必須指定所有的認證，並在本機儲存的檔案中進行更新。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-191">When you change the CceService account password, you will need to specify all the credentials and update them in the locally stored file.</span></span> 
    
<span data-ttu-id="b6a6f-192">針對屬於相同 PSTN 網站的每一個裝置，您必須指定下列各項：</span><span class="sxs-lookup"><span data-stu-id="b6a6f-192">For each appliance that belongs to the same PSTN site, you will need to specify the following:</span></span> 
  
1. <span data-ttu-id="b6a6f-193">執行下列命令，以取得稍後將使用的帳戶名稱和密碼：</span><span class="sxs-lookup"><span data-stu-id="b6a6f-193">Run the following commands to retrieve the account names and passwords that you will use later:</span></span>
    
   ```powershell
   Get-CcCredential -AccountType TenantAdmin -DisplayPassword
   Get-CcCredential -AccountType TenantAdmin
   Get-CcCredential -AccountType OMSWorkspace -DisplayPassword
   Get-CcCredential -AccountType OMSWorkspace 
   Get-CcCredential -AccountType ExternalCert -DisplayPassword
   Get-CcCredential -AccountType CABackupFile -DisplayPassword
   Get-CcCredential -AccountType CceService -DisplayPassword
   Get-CcCredential -AccountType VMAdmin -DisplayPassword
   Get-CcCredential -AccountType DomainAdmin -DisplayPassword
   ```

2. <span data-ttu-id="b6a6f-194">執行 Enter-CcUpdate Cmdlet 以耗盡裝置，並將其移入手動維護模式。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-194">Run the Enter-CcUpdate cmdlet to drain the appliance and move it into manual maintenance mode.</span></span>
    
3. <span data-ttu-id="b6a6f-195">更新主伺服器上 CceService 帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-195">Update the password of the CceService account on the host server.</span></span>
    
4. <span data-ttu-id="b6a6f-196">重新開機主機伺服器。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-196">Restart the host server.</span></span>
    
5. <span data-ttu-id="b6a6f-197">執行 Restore-CcCredentials Cmdlet，以在描述之後重新輸入密碼。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-197">Run the Restore-CcCredentials cmdlet to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="b6a6f-198">請確定輸入的密碼與您在雲端連接器部署之前所輸入的密碼相同，但 CceService 帳戶除外。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-198">Be sure you enter the same password you entered before for the Cloud Connector deployment except for the CceService account.</span></span> <span data-ttu-id="b6a6f-199">若為 CceService 帳戶，請輸入新的密碼。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-199">For the CceService account, enter your new password.</span></span> <span data-ttu-id="b6a6f-200">請確定 CceService 帳戶的新密碼對 PSTN 網站中的所有裝置都是相同的。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-200">Be sure the new password for the CceService account is the same for all appliances in the PSTN site.</span></span>
    
6. <span data-ttu-id="b6a6f-201">根據預設，VmAdmin 和 DomainAdmin 會使用與 CceService 相同的密碼。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-201">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="b6a6f-202">如果步驟1中傳回的 DomainAdmin、VMAdmin 和 CceService 密碼不同，您必須執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="b6a6f-202">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
    
7. <span data-ttu-id="b6a6f-203">執行 Set-CcCredential AccountType DomainAdmin，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b6a6f-203">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
   - <span data-ttu-id="b6a6f-204">當系統提示您輸入舊帳號憑證時，請輸入您用於 CceService 密碼的認證。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-204">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="b6a6f-205">當系統提示您輸入新的帳號憑證時，請輸入步驟1中所傳回之 DomainAdmin 密碼的密碼。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-205">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
8. <span data-ttu-id="b6a6f-206">執行 Set-CcCredential AccountType VmAdmin，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b6a6f-206">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
   - <span data-ttu-id="b6a6f-207">當系統提示您輸入舊帳號憑證時，請輸入您用於 CceService 密碼的認證。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-207">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="b6a6f-208">當系統提示您輸入新的帳號憑證時，請輸入步驟1中所傳回之 VmAdmin 密碼的密碼。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-208">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
9. <span data-ttu-id="b6a6f-209">執行 Exit-CcUpdate Cmdlet，將裝置移出手動維護模式。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-209">Run the Exit-CcUpdate cmdlet to move the appliance out of manual maintenance mode.</span></span>
    
10. <span data-ttu-id="b6a6f-210">在相同 PSTN 網站中的所有裝置上完成這些步驟之後，請在網站根目錄中刪除下列檔案：</span><span class="sxs-lookup"><span data-stu-id="b6a6f-210">After you complete these steps on all appliances in the same PSTN site, delete the following files in the site root directory:</span></span>
    
    - <span data-ttu-id="b6a6f-211">CcLockFile</span><span class="sxs-lookup"><span data-stu-id="b6a6f-211">CcLockFile</span></span>
    
    - <span data-ttu-id="b6a6f-212">Site_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="b6a6f-212">Site_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="b6a6f-213">Tenant_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="b6a6f-213">Tenant_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="b6a6f-214">TenantConfigLock_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="b6a6f-214">TenantConfigLock_\<Edge External Sip Pool fqdn\></span></span>
    
## <a name="add-a-new-sip-domain"></a><span data-ttu-id="b6a6f-215">新增 SIP 網域</span><span class="sxs-lookup"><span data-stu-id="b6a6f-215">Add a new SIP domain</span></span>
<span data-ttu-id="b6a6f-216"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="b6a6f-216"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="b6a6f-217">若要將新的 SIP 網域 (或多個 SIP 網域新增至現有的雲端連接器部署) ，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="b6a6f-217">To add a new SIP domain (or multiple SIP domains) to your existing Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="b6a6f-218">請確認您已完成在 Microsoft 365 或 Office 365 中更新網域的步驟，並且具備新增 DNS 記錄的能力。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-218">Make sure you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="b6a6f-219">如需如何在 Microsoft 365 或 Office 365 中設定網域的詳細資訊，請參閱 [Add a domain To Microsoft 365 Or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-219">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="b6a6f-220">使用新的 SIP 網域或網域更新雲端連接器的設定檔。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-220">Update the Cloud Connector configuration file with the new SIP domain or domains.</span></span>
    
3. <span data-ttu-id="b6a6f-221">針對您的雲端連接器設定中所定義的每個 SIP 網域，向新的 Edge 外部憑證要求 sip 的其他 SAN 名稱。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-221">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="b6a6f-222">設定新 Edge 外部憑證的路徑，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b6a6f-222">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="b6a6f-223">依照指示 [修改單一網站的](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) 設定或 [修改多個網站的](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)設定。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-223">Follow the instructions to [Modify the configuration of a single site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) or [Modify the configuration of multiple sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span></span>
    
## <a name="modify-the-primary-sip-domain"></a><span data-ttu-id="b6a6f-224">修改主要 SIP 網域</span><span class="sxs-lookup"><span data-stu-id="b6a6f-224">Modify the primary SIP domain</span></span>
<span data-ttu-id="b6a6f-225"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="b6a6f-225"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="b6a6f-226">如果您需要在您的雲端連接器部署中變更主要 SIP 網域，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="b6a6f-226">If you need to change the primary SIP domain in your Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="b6a6f-227">請確認您已完成在 Microsoft 365 或 Office 365 中更新網域的步驟，並且具備新增 DNS 記錄的能力。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-227">Make sure you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="b6a6f-228">如需如何在 Microsoft 365 或 Office 365 中設定網域的詳細資訊，請參閱 [Add a domain To Microsoft 365 Or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-228">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="b6a6f-229">使用新的 SIP 網域更新雲端連接器的設定檔。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-229">Update the Cloud Connector configuration file with the new SIP domain.</span></span>
    
3. <span data-ttu-id="b6a6f-230">針對您的雲端連接器設定中所定義的每個 SIP 網域，向新的 Edge 外部憑證要求 sip 的其他 SAN 名稱。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-230">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="b6a6f-231">設定新 Edge 外部憑證的路徑，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b6a6f-231">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="b6a6f-232">在雲端連接器的系統管理員 PowerShell 中執行下列指令程式，以移除網站中每一個裝置的承租人註冊。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-232">Remove the tenant registration for each appliance in a site by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    <span data-ttu-id="b6a6f-233">在商務用 Skype Online PowerShell: 中執行下列 Cmdlet，以移除每個網站的網站註冊。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-233">Remove the site registration for each site by running the following cmdlet in Skype for Business Online PowerShell:</span></span>
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    <span data-ttu-id="b6a6f-234">在 Cloud Connector 上的系統管理員 PowerShell 中執行下列 Cmdlet，以卸載每個裝置：</span><span class="sxs-lookup"><span data-stu-id="b6a6f-234">Uninstall each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     <span data-ttu-id="b6a6f-235">在 Cloud Connector 上的系統管理員 PowerShell 中執行下列 Cmdlet，以登錄每個裝置：</span><span class="sxs-lookup"><span data-stu-id="b6a6f-235">Register each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     <span data-ttu-id="b6a6f-236">逐個安裝每一個裝置，在雲端連接器的系統管理員 PowerShell 中執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b6a6f-236">Install each appliance, one by one, by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a><span data-ttu-id="b6a6f-237">以新憑證取代外部 Edge 憑證</span><span class="sxs-lookup"><span data-stu-id="b6a6f-237">Replace the external Edge certificate with a new certificate</span></span>
<span data-ttu-id="b6a6f-238"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="b6a6f-238"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="b6a6f-239">當您需要取代雲端連接器裝置上的外部 Edge 憑證時，您必須取得新的 Edge 憑證，準備包含私密金鑰和完整憑證鏈的 PFX 檔案，然後在每個裝置上執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="b6a6f-239">When you need to replace the external Edge certificate on your Cloud Connector appliances, you will need to obtain a new Edge certificate, prepare the PFX file containing the Private Key and full certificate chain, and then do the following on each appliance:</span></span>
  
1. <span data-ttu-id="b6a6f-240">使用 Enter-CcUpdate Cmdlet，將裝置置於維護模式。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-240">Put the appliance in maintenance mode by using the Enter-CcUpdate cmdlet.</span></span>
    
2. <span data-ttu-id="b6a6f-241">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="b6a6f-241">Run the following command:</span></span> 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    <span data-ttu-id="b6a6f-242">如果新憑證的密碼與舊憑證相同，則匯入將會成功。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-242">If the password of the new certificate is the same as the old, the import will be successful.</span></span> <span data-ttu-id="b6a6f-243">如果密碼不同，您會收到錯誤訊息，指出密碼錯誤，您必須使用-Local 參數執行 Register-CcAppliance Cmdlet 來重設密碼，然後重複步驟2。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-243">If the password is different, you will receive an error that the password is wrong, and you will need to reset the password by running the Register-CcAppliance cmdlet with the -Local parameter, and then repeating step 2.</span></span> 
    
4. <span data-ttu-id="b6a6f-244">使用 CcUpdate 指令程式，讓裝置停止維護模式。</span><span class="sxs-lookup"><span data-stu-id="b6a6f-244">Take the appliance out of maintenance mode by using the Exit -CcUpdate cmdlet.</span></span>
