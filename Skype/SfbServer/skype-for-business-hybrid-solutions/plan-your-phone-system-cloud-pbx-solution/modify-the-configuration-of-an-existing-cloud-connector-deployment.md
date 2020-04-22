---
title: 修改現有 Cloud Connector 部署的設定
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
ms.openlocfilehash: 77e9940e10cc356afbade5592bf41a0cdba66b0f
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779379"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a><span data-ttu-id="0fa34-103">修改現有 Cloud Connector 部署的設定</span><span class="sxs-lookup"><span data-stu-id="0fa34-103">Modify the configuration of an existing Cloud Connector deployment</span></span>
 
<span data-ttu-id="0fa34-104">遵循此主題中的步驟，修改現有商務用 Skype 雲端連接器 Edition 1.4.1 或更新版本的設定。</span><span class="sxs-lookup"><span data-stu-id="0fa34-104">Follow the steps in this topic to modify the configuration of an existing Skype for Business Cloud Connector Edition 1.4.1 or later deployment.</span></span> 
  
## <a name="modify-the-configuration-of-a-single-site"></a><span data-ttu-id="0fa34-105">修改單一網站的設定</span><span class="sxs-lookup"><span data-stu-id="0fa34-105">Modify the configuration of a single site</span></span>
<span data-ttu-id="0fa34-106"><a name="BKMK_SIngleSite"> </a></span><span class="sxs-lookup"><span data-stu-id="0fa34-106"><a name="BKMK_SIngleSite"> </a></span></span>

<span data-ttu-id="0fa34-107">如果網站中只有一個裝置，當您想要在部署裝置之後變更設定設定時，您可以修改 CloudConnector 檔案，並重新啟動部署。</span><span class="sxs-lookup"><span data-stu-id="0fa34-107">If there is only one appliance in the site, when you want to change the configuration settings after the appliance is deployed, you can modify the CloudConnector.ini file and start the deployment again.</span></span>
  
1. <span data-ttu-id="0fa34-108">執行下列 Cmdlet，以卸載主機伺服器上的所有現有虛擬機器：</span><span class="sxs-lookup"><span data-stu-id="0fa34-108">Run the following cmdlet to uninstall all existing virtual machines on the host server:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="0fa34-109">執行下列 Cmdlet 以取消登錄裝置：</span><span class="sxs-lookup"><span data-stu-id="0fa34-109">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="0fa34-110">更新裝置目錄中的 CloudConnector 檔案。</span><span class="sxs-lookup"><span data-stu-id="0fa34-110">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="0fa34-111">執行下列 Cmdlet 來更新設定：（此步驟僅適用于版本 2; 針對舊版，請跳至下一個步驟）。</span><span class="sxs-lookup"><span data-stu-id="0fa34-111">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="0fa34-112">請執行下列 Cmdlet 重新註冊裝置：</span><span class="sxs-lookup"><span data-stu-id="0fa34-112">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="0fa34-113">執行下列 Cmdlet 以安裝商務用 Skype Cloud Connector Edition：</span><span class="sxs-lookup"><span data-stu-id="0fa34-113">Run the following cmdlet to install Skype for Business Cloud Connector Edition:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

<span data-ttu-id="0fa34-114">如果網站中有一個以上的裝置，您必須遵循下列步驟，修改 CloudConnector 檔案，然後逐個重新部署裝置。</span><span class="sxs-lookup"><span data-stu-id="0fa34-114">If there is more than one appliance in the site, you'll need to follow these steps, modify the CloudConnector.ini file, and redeploy the appliances one by one.</span></span>
  
1. <span data-ttu-id="0fa34-115">執行下列 Cmdlet，以卸載目前裝置上的所有現有虛擬機器：</span><span class="sxs-lookup"><span data-stu-id="0fa34-115">Run the following cmdlet to uninstall all existing virtual machines on the current appliance:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="0fa34-116">執行下列 Cmdlet 以取消登錄裝置：</span><span class="sxs-lookup"><span data-stu-id="0fa34-116">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="0fa34-117">更新裝置目錄中的 CloudConnector 檔案。</span><span class="sxs-lookup"><span data-stu-id="0fa34-117">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="0fa34-118">執行下列 Cmdlet 來更新設定：（此步驟僅適用于版本 2; 針對舊版，請跳至下一個步驟）。</span><span class="sxs-lookup"><span data-stu-id="0fa34-118">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="0fa34-119">請執行下列 Cmdlet 重新註冊裝置：</span><span class="sxs-lookup"><span data-stu-id="0fa34-119">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="0fa34-120">在網站中的所有其他裝置上執行下列 Cmdlet，以挑選最新的設定：</span><span class="sxs-lookup"><span data-stu-id="0fa34-120">Run the following cmdlet on all other appliances in the site to pick up the latest configuration:</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

7. <span data-ttu-id="0fa34-121">在目前的裝置上執行下列 Cmdlet 重新部署雲端連接器：</span><span class="sxs-lookup"><span data-stu-id="0fa34-121">Run the following cmdlet to redeploy Cloud Connector on the current appliance:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a><span data-ttu-id="0fa34-122">修改多個網站的設定</span><span class="sxs-lookup"><span data-stu-id="0fa34-122">Modify the configuration of multiple sites</span></span>
<span data-ttu-id="0fa34-123"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="0fa34-123"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="0fa34-124">若要在部署中修改多個網站的設定，請遵循單一網站的步驟，一次更新一個網站。</span><span class="sxs-lookup"><span data-stu-id="0fa34-124">To modify the configuration for multiple sites in a deployment, follow the steps for a single site, updating one site at a time.</span></span>
  
## <a name="modify-the-configuration-of-your-office-365-organization-to-enable-automatic-updates"></a><span data-ttu-id="0fa34-125">修改 Office 365 組織的設定以啟用自動更新</span><span class="sxs-lookup"><span data-stu-id="0fa34-125">Modify the configuration of your Office 365 organization to enable automatic updates</span></span>
<span data-ttu-id="0fa34-126"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="0fa34-126"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="0fa34-127">若要啟用作業系統自動更新和 Bits 自動更新，您必須使用商務用 Skype 租使用者系統管理員帳戶進行線上管理，並使用租使用者遠端 PowerShell，如下所示。</span><span class="sxs-lookup"><span data-stu-id="0fa34-127">To enable operating system automatic updates and Bits automatic updates, you must use the Skype for Business tenant admin account for online management and use tenant remote PowerShell as follows.</span></span>
  
<span data-ttu-id="0fa34-128">如果您停用作業系統自動更新或 Bits 自動更新，您的主機和虛擬機器可能會錯過重要的 Windows 更新，而雲端連接器將無法自動升級為新的版本。</span><span class="sxs-lookup"><span data-stu-id="0fa34-128">If you disabled operating system automatic updates or Bits automatic updates, your host and virtual machine may miss important Windows updates, and Cloud Connector will not upgrade to the new version automatically.</span></span> <span data-ttu-id="0fa34-129">強烈建議您啟用自動更新。</span><span class="sxs-lookup"><span data-stu-id="0fa34-129">It is highly recommended that you enable automatic updates.</span></span>
  
1. <span data-ttu-id="0fa34-130">網站的 EnableAutoUpdate 屬性必須設定為 true （預設值）。</span><span class="sxs-lookup"><span data-stu-id="0fa34-130">The EnableAutoUpdate property of the site needs to be set to true (the default value).</span></span> <span data-ttu-id="0fa34-131">請執行下列 Cmdlet，確定 EnableAutoUpdate 設定為 true：</span><span class="sxs-lookup"><span data-stu-id="0fa34-131">Run the following cmdlet to make sure EnableAutoUpdate is set to true:</span></span>
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. <span data-ttu-id="0fa34-132">建立租使用者的自動更新時間範圍。</span><span class="sxs-lookup"><span data-stu-id="0fa34-132">Create auto update time window for the tenant.</span></span>
    
    <span data-ttu-id="0fa34-133">時段可以是每天、每週及每月。</span><span class="sxs-lookup"><span data-stu-id="0fa34-133">The time window can be daily, weekly and monthly.</span></span> <span data-ttu-id="0fa34-134">Windows 所有的時間都需要開始時間和持續時間。</span><span class="sxs-lookup"><span data-stu-id="0fa34-134">All the time windows need a start time and a duration.</span></span>
    
   - <span data-ttu-id="0fa34-135">針對每日時段，只需要開始時間和持續時間。</span><span class="sxs-lookup"><span data-stu-id="0fa34-135">For a daily time window, only start time and duration are needed.</span></span> 
    
   - <span data-ttu-id="0fa34-136">若為每週時段，需要天數，其可為一天或多天。</span><span class="sxs-lookup"><span data-stu-id="0fa34-136">For a weekly time window, days of week are needed, which can be a single day or multiple days.</span></span>
    
   - <span data-ttu-id="0fa34-137">在每月的時段中，可能會有兩種類型。</span><span class="sxs-lookup"><span data-stu-id="0fa34-137">For a monthly time window, there can be two types.</span></span> <span data-ttu-id="0fa34-138">第一種類型是指定一月中的第幾天，也就是一天。</span><span class="sxs-lookup"><span data-stu-id="0fa34-138">The first type is to specify the day of the month, which can be a single day.</span></span> <span data-ttu-id="0fa34-139">第二種類型是指定每月的周數，也就是一周中的天數，這兩者都可以是單一專案或多個專案。</span><span class="sxs-lookup"><span data-stu-id="0fa34-139">The second type is to specify the weeks of the month, along with days of the week, which both can be a single item or multiple items.</span></span>
    
   - <span data-ttu-id="0fa34-140">每個租使用者可定義20個時間視窗。</span><span class="sxs-lookup"><span data-stu-id="0fa34-140">Each tenant can have 20 time windows defined.</span></span> <span data-ttu-id="0fa34-141">將新租使用者的預設時段，當作作業系統更新和 Bits 更新的預設時間範圍而建立。</span><span class="sxs-lookup"><span data-stu-id="0fa34-141">The default time window will be created for a new tenant as the default time window for operating system update and Bits update.</span></span> <span data-ttu-id="0fa34-142">執行下列 Cmdlet 以設定每日、每週或每月時間的時段：</span><span class="sxs-lookup"><span data-stu-id="0fa34-142">Run the following cmdlet(s) to set the daily, weekly or monthly time window:</span></span>
    
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

   - <span data-ttu-id="0fa34-143">將更新時間視窗指派至網站。</span><span class="sxs-lookup"><span data-stu-id="0fa34-143">Assign update time windows to the site.</span></span> 
    
     <span data-ttu-id="0fa34-144">會個別設定 Bits 更新時間與 OS 更新時間視窗。</span><span class="sxs-lookup"><span data-stu-id="0fa34-144">The Bits update time and OS update time windows are configured separately.</span></span> <span data-ttu-id="0fa34-145">這兩者都可以指派一或多個時間視窗。</span><span class="sxs-lookup"><span data-stu-id="0fa34-145">Both of them can be assigned single or multiple time windows.</span></span> <span data-ttu-id="0fa34-146">每個時間範圍可指派給不同的網站和不同的目的（Bits 更新和 OS 更新）。</span><span class="sxs-lookup"><span data-stu-id="0fa34-146">Each time window can be assigned to different sites and different purpose (Bits update and OS update).</span></span> <span data-ttu-id="0fa34-147">執行下列 Cmdlet 來設定網站的時間範圍：</span><span class="sxs-lookup"><span data-stu-id="0fa34-147">Run the following cmdlet to set the time window for the site:</span></span> 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a><span data-ttu-id="0fa34-148">更新專用的租使用者系統管理員認證</span><span class="sxs-lookup"><span data-stu-id="0fa34-148">Update the dedicated tenant admin credentials</span></span>
<span data-ttu-id="0fa34-149"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="0fa34-149"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="0fa34-150">您可以從具有必要許可權的帳戶，從 Office 365 組織中取得雲端連接器的系統管理變更。</span><span class="sxs-lookup"><span data-stu-id="0fa34-150">Administrative changes in the Office 365 organization for Cloud Connector are made from an account with the needed permissions.</span></span> <span data-ttu-id="0fa34-151">在2.0 之前的雲端連接器版本中，該帳戶是專用的全域租使用者管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="0fa34-151">In Cloud Connector versions before 2.0, that account is a dedicated global tenant admin account.</span></span> <span data-ttu-id="0fa34-152">在雲端連接器版本2.0 和更新版本中，該帳戶可以是具有商務用 Skype 系統管理員許可權的 Office 365 帳戶。</span><span class="sxs-lookup"><span data-stu-id="0fa34-152">In Cloud Connector versions 2.0 and later, that account can be an Office 365 account with Skype for Business Administrator rights.</span></span>
  
<span data-ttu-id="0fa34-153">如果您的系統管理員帳號憑證變更于 Office 365，您也需要在您已部署的每個雲端連接器裝置上執行下列管理員 PowerShell 命令，以更新雲端連接器中的本機快取認證：</span><span class="sxs-lookup"><span data-stu-id="0fa34-153">If your admin account credentials change in Office 365, you also need to update the locally cached credentials in Cloud Connector by running the following Administrator PowerShell command on each Cloud Connector appliance you have deployed:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a><span data-ttu-id="0fa34-154">更新主伺服器的密碼</span><span class="sxs-lookup"><span data-stu-id="0fa34-154">Update the password for the host server</span></span>
<span data-ttu-id="0fa34-155"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="0fa34-155"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="0fa34-156">本節適用于雲端連接器版本2.0 和更新版本。</span><span class="sxs-lookup"><span data-stu-id="0fa34-156">This section is applicable to Cloud Connector version 2.0 and later.</span></span> 
  
<span data-ttu-id="0fa34-157">所有雲端連接器認證都儲存在下列檔案中： "%SystemDrive%\Programdata\Cloudconnector\credentials。\<CurrentUser\>.xml "。</span><span class="sxs-lookup"><span data-stu-id="0fa34-157">All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="0fa34-158">當主伺服器上的密碼變更時，您將需要更新本機儲存的認證。</span><span class="sxs-lookup"><span data-stu-id="0fa34-158">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
  
<span data-ttu-id="0fa34-159">若要在雲端連接器裝置上更新本機儲存的認證，請使用[CcCredential](get-cccredential.md)和[CcCredential](set-cccredential.md)指令程式，然後遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="0fa34-159">To update the locally stored credentials on the Cloud Connector appliance, use the [Get-CcCredential](get-cccredential.md) and [Set-CcCredential](set-cccredential.md) cmdlets and follow these steps:</span></span>
  
1. <span data-ttu-id="0fa34-160">執行下列命令，以取得稍後需要的密碼：</span><span class="sxs-lookup"><span data-stu-id="0fa34-160">Run the following commands to retrieve the passwords you will need later:</span></span> 
    
   - <span data-ttu-id="0fa34-161">CcCredential-AccountType DomainAdmin-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="0fa34-161">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="0fa34-162">CcCredential-AccountType VMAdmin-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="0fa34-162">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="0fa34-163">CcCredential-AccountType CceService-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="0fa34-163">Get-CcCredential -AccountType CceService -DisplayPassword</span></span>
    
2. <span data-ttu-id="0fa34-164">變更您的帳戶在主伺服器上的密碼。</span><span class="sxs-lookup"><span data-stu-id="0fa34-164">Change the password of your account on the host server.</span></span>
    
3. <span data-ttu-id="0fa34-165">重新開機主機伺服器。</span><span class="sxs-lookup"><span data-stu-id="0fa34-165">Restart the host server.</span></span>
    
4. <span data-ttu-id="0fa34-166">刪除下列檔案： "%SystemDrive%\Programdata\Cloudconnector\credentials。\<CurrentUser\>.xml "。</span><span class="sxs-lookup"><span data-stu-id="0fa34-166">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
5. <span data-ttu-id="0fa34-167">以系統管理員身分啟動 PowerShell 主控台，然後執行「Register-CcAppliance-Local」，以在描述之後重新輸入密碼。</span><span class="sxs-lookup"><span data-stu-id="0fa34-167">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="0fa34-168">請確定輸入的密碼與您在雲端連接器部署之前輸入的密碼相同。</span><span class="sxs-lookup"><span data-stu-id="0fa34-168">Be sure you enter the same password you entered before for the Cloud Connector deployment.</span></span>
    
<span data-ttu-id="0fa34-169">根據預設，VmAdmin 和 DomainAdmin 會使用與 CceService 相同的密碼。</span><span class="sxs-lookup"><span data-stu-id="0fa34-169">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="0fa34-170">如果步驟1中傳回的 DomainAdmin、VMAdmin 和 CceService 密碼不同，您必須執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="0fa34-170">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
  
1. <span data-ttu-id="0fa34-171">執行 Set-CcCredential-AccountType DomainAdmin，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0fa34-171">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="0fa34-172">當系統提示您輸入舊帳號憑證時，請輸入您用於 CceService 密碼的認證。</span><span class="sxs-lookup"><span data-stu-id="0fa34-172">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="0fa34-173">當系統提示您輸入新的帳號憑證時，請輸入步驟1中所傳回之 DomainAdmin 密碼的密碼。</span><span class="sxs-lookup"><span data-stu-id="0fa34-173">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
2. <span data-ttu-id="0fa34-174">執行 Set-CcCredential-AccountType VmAdmin，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0fa34-174">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="0fa34-175">當系統提示您輸入舊帳號憑證時，請輸入您用於 CceService 密碼的認證。</span><span class="sxs-lookup"><span data-stu-id="0fa34-175">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="0fa34-176">當系統提示您輸入新的帳號憑證時，請輸入步驟1中所傳回之 VmAdmin 密碼的密碼。</span><span class="sxs-lookup"><span data-stu-id="0fa34-176">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
## <a name="update-the-password-for-the-cceservice-account"></a><span data-ttu-id="0fa34-177">更新 CceService 帳戶的密碼</span><span class="sxs-lookup"><span data-stu-id="0fa34-177">Update the password for the CceService account</span></span>
<span data-ttu-id="0fa34-178"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="0fa34-178"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="0fa34-179">本節適用于雲端連接器2.0.1 版及更新版本。</span><span class="sxs-lookup"><span data-stu-id="0fa34-179">This section is applicable to Cloud Connector version 2.0.1 and later.</span></span> 
  
<span data-ttu-id="0fa34-180">雲端連接器服務會執行雲端連接器管理服務。</span><span class="sxs-lookup"><span data-stu-id="0fa34-180">The Cloud Connector service runs the Cloud Connector Management service.</span></span> <span data-ttu-id="0fa34-181">在雲端連接器版本部署期間建立 CceService 帳戶，並儲存在下列檔案中： "%SystemDrive%\Programdata\Cloudconnector\credentials。\<CurrentUser\>.Xml "和"%SystemDrive%\Programdata\Cloudconnector\credentials。。CceService。</span><span class="sxs-lookup"><span data-stu-id="0fa34-181">The CceService account is created during the Cloud Connector Edition deployment and stored in the following files: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" and "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span></span>
  
<span data-ttu-id="0fa34-182">為了確保所有裝置都可以存取網站目錄共用，CceService 帳戶的密碼在網站中部署的所有裝置上都必須相同。</span><span class="sxs-lookup"><span data-stu-id="0fa34-182">To ensure that all appliances can access the site directory share, the password for the CceService account must be the same on all appliances deployed within the site.</span></span> <span data-ttu-id="0fa34-183">請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="0fa34-183">Keep the following in mind:</span></span>
  
- <span data-ttu-id="0fa34-184">根據預設，CceService 帳戶會設定為「密碼永不到期」。</span><span class="sxs-lookup"><span data-stu-id="0fa34-184">By default, the CceService account is configured as "Password never expires".</span></span> <span data-ttu-id="0fa34-185">當您更新密碼時，Microsoft 建議您保留此設定。</span><span class="sxs-lookup"><span data-stu-id="0fa34-185">When you update the password, Microsoft recommends keeping this configuration.</span></span>
    
- <span data-ttu-id="0fa34-186">您應該在非峰值使用期間更新密碼，並在自動更新時間範圍外更新 bits 或 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="0fa34-186">You should update the password during non-peak usage periods and outside of automatic update time windows for bits or Windows updates.</span></span> <span data-ttu-id="0fa34-187">當您更新密碼時，裝置必須耗盡並重新啟動，這需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="0fa34-187">When you update the password, the appliance needs to be drained and restarted, which takes some time.</span></span> <span data-ttu-id="0fa34-188">重新開機裝置會中斷自動更新作業。</span><span class="sxs-lookup"><span data-stu-id="0fa34-188">Restarting the appliance will interrupt automatic update operations.</span></span> 
    
- <span data-ttu-id="0fa34-189">當您變更 CceService 帳戶密碼時，您必須指定所有的認證，並在本機儲存的檔案中進行更新。</span><span class="sxs-lookup"><span data-stu-id="0fa34-189">When you change the CceService account password, you will need to specify all the credentials and update them in the locally stored file.</span></span> 
    
<span data-ttu-id="0fa34-190">針對屬於相同 PSTN 網站的每一個裝置，您必須指定下列各項：</span><span class="sxs-lookup"><span data-stu-id="0fa34-190">For each appliance that belongs to the same PSTN site, you will need to specify the following:</span></span> 
  
1. <span data-ttu-id="0fa34-191">執行下列命令，以取得稍後將使用的帳戶名稱和密碼：</span><span class="sxs-lookup"><span data-stu-id="0fa34-191">Run the following commands to retrieve the account names and passwords that you will use later:</span></span>
    
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

2. <span data-ttu-id="0fa34-192">執行 CcUpdate 指令程式以耗盡裝置，並將其移入手動維護模式。</span><span class="sxs-lookup"><span data-stu-id="0fa34-192">Run the Enter-CcUpdate cmdlet to drain the appliance and move it into manual maintenance mode.</span></span>
    
3. <span data-ttu-id="0fa34-193">更新主伺服器上 CceService 帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="0fa34-193">Update the password of the CceService account on the host server.</span></span>
    
4. <span data-ttu-id="0fa34-194">重新開機主機伺服器。</span><span class="sxs-lookup"><span data-stu-id="0fa34-194">Restart the host server.</span></span>
    
5. <span data-ttu-id="0fa34-195">執行 CcCredentials 指令程式，以在描述之後重新輸入密碼。</span><span class="sxs-lookup"><span data-stu-id="0fa34-195">Run the Restore-CcCredentials cmdlet to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="0fa34-196">請確定輸入的密碼與您在雲端連接器部署之前所輸入的密碼相同，但 CceService 帳戶除外。</span><span class="sxs-lookup"><span data-stu-id="0fa34-196">Be sure you enter the same password you entered before for the Cloud Connector deployment except for the CceService account.</span></span> <span data-ttu-id="0fa34-197">若為 CceService 帳戶，請輸入新的密碼。</span><span class="sxs-lookup"><span data-stu-id="0fa34-197">For the CceService account, enter your new password.</span></span> <span data-ttu-id="0fa34-198">請確定 CceService 帳戶的新密碼對 PSTN 網站中的所有裝置都是相同的。</span><span class="sxs-lookup"><span data-stu-id="0fa34-198">Be sure the new password for the CceService account is the same for all appliances in the PSTN site.</span></span>
    
6. <span data-ttu-id="0fa34-199">根據預設，VmAdmin 和 DomainAdmin 會使用與 CceService 相同的密碼。</span><span class="sxs-lookup"><span data-stu-id="0fa34-199">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="0fa34-200">如果步驟1中傳回的 DomainAdmin、VMAdmin 和 CceService 密碼不同，您必須執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="0fa34-200">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
    
7. <span data-ttu-id="0fa34-201">執行 Set-CcCredential-AccountType DomainAdmin，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0fa34-201">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
   - <span data-ttu-id="0fa34-202">當系統提示您輸入舊帳號憑證時，請輸入您用於 CceService 密碼的認證。</span><span class="sxs-lookup"><span data-stu-id="0fa34-202">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="0fa34-203">當系統提示您輸入新的帳號憑證時，請輸入步驟1中所傳回之 DomainAdmin 密碼的密碼。</span><span class="sxs-lookup"><span data-stu-id="0fa34-203">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
8. <span data-ttu-id="0fa34-204">執行 Set-CcCredential-AccountType VmAdmin，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0fa34-204">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
   - <span data-ttu-id="0fa34-205">當系統提示您輸入舊帳號憑證時，請輸入您用於 CceService 密碼的認證。</span><span class="sxs-lookup"><span data-stu-id="0fa34-205">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="0fa34-206">當系統提示您輸入新的帳號憑證時，請輸入步驟1中所傳回之 VmAdmin 密碼的密碼。</span><span class="sxs-lookup"><span data-stu-id="0fa34-206">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
9. <span data-ttu-id="0fa34-207">執行 CcUpdate Cmdlet，將裝置移出手動維護模式。</span><span class="sxs-lookup"><span data-stu-id="0fa34-207">Run the Exit-CcUpdate cmdlet to move the appliance out of manual maintenance mode.</span></span>
    
10. <span data-ttu-id="0fa34-208">在相同 PSTN 網站中的所有裝置上完成這些步驟之後，請在網站根目錄中刪除下列檔案：</span><span class="sxs-lookup"><span data-stu-id="0fa34-208">After you complete these steps on all appliances in the same PSTN site, delete the following files in the site root directory:</span></span>
    
    - <span data-ttu-id="0fa34-209">CcLockFile</span><span class="sxs-lookup"><span data-stu-id="0fa34-209">CcLockFile</span></span>
    
    - <span data-ttu-id="0fa34-210">Site_\<Edge 外部 Sip 集區 fqdn\></span><span class="sxs-lookup"><span data-stu-id="0fa34-210">Site_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="0fa34-211">Tenant_\<Edge 外部 Sip 集區 fqdn\></span><span class="sxs-lookup"><span data-stu-id="0fa34-211">Tenant_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="0fa34-212">TenantConfigLock_\<Edge 外部 Sip 集區 fqdn\></span><span class="sxs-lookup"><span data-stu-id="0fa34-212">TenantConfigLock_\<Edge External Sip Pool fqdn\></span></span>
    
## <a name="add-a-new-sip-domain"></a><span data-ttu-id="0fa34-213">新增 SIP 網域</span><span class="sxs-lookup"><span data-stu-id="0fa34-213">Add a new SIP domain</span></span>
<span data-ttu-id="0fa34-214"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="0fa34-214"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="0fa34-215">若要將新的 SIP 網域（或多個 SIP 網域）新增至現有的雲端連接器部署，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="0fa34-215">To add a new SIP domain (or multiple SIP domains) to your existing Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="0fa34-216">請確認您已完成在 Office 365 更新您的網域的步驟，並且具備新增 DNS 記錄的能力。</span><span class="sxs-lookup"><span data-stu-id="0fa34-216">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="0fa34-217">如需如何在 Office 365 中設定網域的相關資訊，請參閱[Add a domain To Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。</span><span class="sxs-lookup"><span data-stu-id="0fa34-217">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="0fa34-218">使用新的 SIP 網域或網域更新雲端連接器的設定檔。</span><span class="sxs-lookup"><span data-stu-id="0fa34-218">Update the Cloud Connector configuration file with the new SIP domain or domains.</span></span>
    
3. <span data-ttu-id="0fa34-219">針對您的雲端連接器設定中所定義的每個 SIP 網域，向新的 Edge 外部憑證要求 sip 的其他 SAN 名稱。</span><span class="sxs-lookup"><span data-stu-id="0fa34-219">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="0fa34-220">設定新 Edge 外部憑證的路徑，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0fa34-220">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="0fa34-221">依照指示[修改單一網站的](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite)設定或[修改多個網站的](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)設定。</span><span class="sxs-lookup"><span data-stu-id="0fa34-221">Follow the instructions to [Modify the configuration of a single site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) or [Modify the configuration of multiple sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span></span>
    
## <a name="modify-the-primary-sip-domain"></a><span data-ttu-id="0fa34-222">修改主要 SIP 網域</span><span class="sxs-lookup"><span data-stu-id="0fa34-222">Modify the primary SIP domain</span></span>
<span data-ttu-id="0fa34-223"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="0fa34-223"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="0fa34-224">如果您需要在您的雲端連接器部署中變更主要 SIP 網域，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="0fa34-224">If you need to change the primary SIP domain in your Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="0fa34-225">請確認您已完成在 Office 365 更新您的網域的步驟，並且具備新增 DNS 記錄的能力。</span><span class="sxs-lookup"><span data-stu-id="0fa34-225">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="0fa34-226">如需如何在 Office 365 中設定網域的相關資訊，請參閱[Add a domain To Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。</span><span class="sxs-lookup"><span data-stu-id="0fa34-226">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="0fa34-227">使用新的 SIP 網域更新雲端連接器的設定檔。</span><span class="sxs-lookup"><span data-stu-id="0fa34-227">Update the Cloud Connector configuration file with the new SIP domain.</span></span>
    
3. <span data-ttu-id="0fa34-228">針對您的雲端連接器設定中所定義的每個 SIP 網域，向新的 Edge 外部憑證要求 sip 的其他 SAN 名稱。</span><span class="sxs-lookup"><span data-stu-id="0fa34-228">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="0fa34-229">設定新 Edge 外部憑證的路徑，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0fa34-229">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="0fa34-230">在雲端連接器的系統管理員 PowerShell 中執行下列指令程式，以移除網站中每一個裝置的承租人註冊。</span><span class="sxs-lookup"><span data-stu-id="0fa34-230">Remove the tenant registration for each appliance in a site by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    <span data-ttu-id="0fa34-231">在商務用 Skype Online PowerShell: 中執行下列 Cmdlet，以移除每個網站的網站註冊。</span><span class="sxs-lookup"><span data-stu-id="0fa34-231">Remove the site registration for each site by running the following cmdlet in Skype for Business Online PowerShell:</span></span>
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    <span data-ttu-id="0fa34-232">在 Cloud Connector 上的系統管理員 PowerShell 中執行下列 Cmdlet，以卸載每個裝置：</span><span class="sxs-lookup"><span data-stu-id="0fa34-232">Uninstall each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     <span data-ttu-id="0fa34-233">在 Cloud Connector 上的系統管理員 PowerShell 中執行下列 Cmdlet，以登錄每個裝置：</span><span class="sxs-lookup"><span data-stu-id="0fa34-233">Register each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     <span data-ttu-id="0fa34-234">逐個安裝每一個裝置，在雲端連接器的系統管理員 PowerShell 中執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="0fa34-234">Install each appliance, one by one, by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a><span data-ttu-id="0fa34-235">以新憑證取代外部 Edge 憑證</span><span class="sxs-lookup"><span data-stu-id="0fa34-235">Replace the external Edge certificate with a new certificate</span></span>
<span data-ttu-id="0fa34-236"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="0fa34-236"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="0fa34-237">當您需要取代雲端連接器裝置上的外部 Edge 憑證時，您必須取得新的 Edge 憑證，準備包含私密金鑰和完整憑證鏈的 PFX 檔案，然後在每個裝置上執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="0fa34-237">When you need to replace the external Edge certificate on your Cloud Connector appliances, you will need to obtain a new Edge certificate, prepare the PFX file containing the Private Key and full certificate chain, and then do the following on each appliance:</span></span>
  
1. <span data-ttu-id="0fa34-238">使用 Enter-CcUpdate 指令程式，讓裝置進入維護模式。</span><span class="sxs-lookup"><span data-stu-id="0fa34-238">Put the appliance in maintenance mode by using the Enter-CcUpdate cmdlet.</span></span>
    
2. <span data-ttu-id="0fa34-239">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0fa34-239">Run the following command:</span></span> 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    <span data-ttu-id="0fa34-240">如果新憑證的密碼與舊憑證相同，則匯入將會成功。</span><span class="sxs-lookup"><span data-stu-id="0fa34-240">If the password of the new certificate is the same as the old, the import will be successful.</span></span> <span data-ttu-id="0fa34-241">如果密碼不同，您會收到錯誤，指出密碼錯誤，您必須使用-Local 參數執行 CcAppliance Cmdlet 來重設密碼，然後重複步驟2。</span><span class="sxs-lookup"><span data-stu-id="0fa34-241">If the password is different, you will receive an error that the password is wrong, and you will need to reset the password by running the Register-CcAppliance cmdlet with the -Local parameter, and then repeating step 2.</span></span> 
    
4. <span data-ttu-id="0fa34-242">使用 CcUpdate 指令程式，讓裝置停止維護模式。</span><span class="sxs-lookup"><span data-stu-id="0fa34-242">Take the appliance out of maintenance mode by using the Exit -CcUpdate cmdlet.</span></span>
    

