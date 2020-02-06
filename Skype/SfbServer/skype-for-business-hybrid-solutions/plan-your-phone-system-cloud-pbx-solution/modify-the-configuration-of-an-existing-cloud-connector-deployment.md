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
description: 請依照本主題中的步驟，修改現有的商務用 Skype 雲端連接器 Edition 1.4.1 或更新版本的部署設定。
ms.openlocfilehash: 32a231ed85b94c09591adfcc6299cba704be267f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799433"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a><span data-ttu-id="55965-103">修改現有 Cloud Connector 部署的組態</span><span class="sxs-lookup"><span data-stu-id="55965-103">Modify the configuration of an existing Cloud Connector deployment</span></span>
 
<span data-ttu-id="55965-104">請依照本主題中的步驟，修改現有的商務用 Skype 雲端連接器 Edition 1.4.1 或更新版本的部署設定。</span><span class="sxs-lookup"><span data-stu-id="55965-104">Follow the steps in this topic to modify the configuration of an existing Skype for Business Cloud Connector Edition 1.4.1 or later deployment.</span></span> 
  
## <a name="modify-the-configuration-of-a-single-site"></a><span data-ttu-id="55965-105">修改單一網站的設定</span><span class="sxs-lookup"><span data-stu-id="55965-105">Modify the configuration of a single site</span></span>
<span data-ttu-id="55965-106"><a name="BKMK_SIngleSite"> </a></span><span class="sxs-lookup"><span data-stu-id="55965-106"><a name="BKMK_SIngleSite"> </a></span></span>

<span data-ttu-id="55965-107">如果網站中只有一個裝置，而您想要在部署裝置之後變更設定設定，您可以修改 CloudConnector 檔案並再次開始部署。</span><span class="sxs-lookup"><span data-stu-id="55965-107">If there is only one appliance in the site, when you want to change the configuration settings after the appliance is deployed, you can modify the CloudConnector.ini file and start the deployment again.</span></span>
  
1. <span data-ttu-id="55965-108">執行下列 Cmdlet 以卸載主機伺服器上所有現有的虛擬機器：</span><span class="sxs-lookup"><span data-stu-id="55965-108">Run the following cmdlet to uninstall all existing virtual machines on the host server:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="55965-109">執行下列 Cmdlet 以取消註冊裝置：</span><span class="sxs-lookup"><span data-stu-id="55965-109">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="55965-110">更新裝置目錄中的 CloudConnector 檔案。</span><span class="sxs-lookup"><span data-stu-id="55965-110">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="55965-111">執行下列 Cmdlet 來更新設定：（這個步驟僅適用于版本 2; 適用于舊版），請跳到下一個步驟。）</span><span class="sxs-lookup"><span data-stu-id="55965-111">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="55965-112">請執行下列 Cmdlet 再次註冊裝置：</span><span class="sxs-lookup"><span data-stu-id="55965-112">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="55965-113">執行下列 Cmdlet 來安裝商務用 Skype 雲端連接器版本：</span><span class="sxs-lookup"><span data-stu-id="55965-113">Run the following cmdlet to install Skype for Business Cloud Connector Edition:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

<span data-ttu-id="55965-114">如果網站中有一個以上的裝置，您必須遵循下列步驟，修改 CloudConnector 檔案，然後逐一重新部署裝置。</span><span class="sxs-lookup"><span data-stu-id="55965-114">If there is more than one appliance in the site, you'll need to follow these steps, modify the CloudConnector.ini file, and redeploy the appliances one by one.</span></span>
  
1. <span data-ttu-id="55965-115">執行下列 Cmdlet 以卸載目前裝置上所有現有的虛擬機器：</span><span class="sxs-lookup"><span data-stu-id="55965-115">Run the following cmdlet to uninstall all existing virtual machines on the current appliance:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="55965-116">執行下列 Cmdlet 以取消註冊裝置：</span><span class="sxs-lookup"><span data-stu-id="55965-116">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="55965-117">更新裝置目錄中的 CloudConnector 檔案。</span><span class="sxs-lookup"><span data-stu-id="55965-117">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="55965-118">執行下列 Cmdlet 來更新設定：（這個步驟僅適用于版本 2; 適用于舊版），請跳到下一個步驟。）</span><span class="sxs-lookup"><span data-stu-id="55965-118">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="55965-119">請執行下列 Cmdlet 再次註冊裝置：</span><span class="sxs-lookup"><span data-stu-id="55965-119">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="55965-120">在網站中的所有其他裝置上執行下列 Cmdlet，以取得最新的設定：</span><span class="sxs-lookup"><span data-stu-id="55965-120">Run the following cmdlet on all other appliances in the site to pick up the latest configuration:</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

7. <span data-ttu-id="55965-121">在目前的裝置上執行下列 Cmdlet 來重新部署雲端連接器：</span><span class="sxs-lookup"><span data-stu-id="55965-121">Run the following cmdlet to redeploy Cloud Connector on the current appliance:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a><span data-ttu-id="55965-122">修改多個網站的設定</span><span class="sxs-lookup"><span data-stu-id="55965-122">Modify the configuration of multiple sites</span></span>
<span data-ttu-id="55965-123"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="55965-123"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="55965-124">若要在部署中修改多個網站的設定，請遵循單一網站的步驟，一次更新一個網站。</span><span class="sxs-lookup"><span data-stu-id="55965-124">To modify the configuration for multiple sites in a deployment, follow the steps for a single site, updating one site at a time.</span></span>
  
## <a name="modify-the-configuration-of-your-office-365-tenant-to-enable-automatic-updates"></a><span data-ttu-id="55965-125">修改 Office 365 租使用者的設定以啟用自動更新</span><span class="sxs-lookup"><span data-stu-id="55965-125">Modify the configuration of your Office 365 tenant to enable automatic updates</span></span>
<span data-ttu-id="55965-126"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="55965-126"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="55965-127">若要啟用作業系統自動更新和 Bits 自動更新，您必須使用商務用 Skype 租使用者系統管理員帳戶進行線上管理，並使用租使用者遠端 PowerShell，如下所示。</span><span class="sxs-lookup"><span data-stu-id="55965-127">To enable operating system automatic updates and Bits automatic updates, you must use the Skype for Business tenant admin account for online management and use tenant remote PowerShell as follows.</span></span>
  
<span data-ttu-id="55965-128">如果您已停用作業系統自動更新或 Bits 自動更新，您的主機和虛擬機器可能會錯過重要的 Windows 更新，而雲端連接器將無法自動升級至新版本。</span><span class="sxs-lookup"><span data-stu-id="55965-128">If you disabled operating system automatic updates or Bits automatic updates, your host and virtual machine may miss important Windows updates, and Cloud Connector will not upgrade to the new version automatically.</span></span> <span data-ttu-id="55965-129">強烈建議您啟用自動更新。</span><span class="sxs-lookup"><span data-stu-id="55965-129">It is highly recommended that you enable automatic updates.</span></span>
  
1. <span data-ttu-id="55965-130">網站的 EnableAutoUpdate 屬性必須設定為 true （預設值）。</span><span class="sxs-lookup"><span data-stu-id="55965-130">The EnableAutoUpdate property of the site needs to be set to true (the default value).</span></span> <span data-ttu-id="55965-131">請執行下列 Cmdlet，確認 EnableAutoUpdate 已設定為 true：</span><span class="sxs-lookup"><span data-stu-id="55965-131">Run the following cmdlet to make sure EnableAutoUpdate is set to true:</span></span>
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. <span data-ttu-id="55965-132">建立租使用者的自動更新時間範圍。</span><span class="sxs-lookup"><span data-stu-id="55965-132">Create auto update time window for the tenant.</span></span>
    
    <span data-ttu-id="55965-133">時間範圍可以是 [每日]、[每週] 和 [每月]。</span><span class="sxs-lookup"><span data-stu-id="55965-133">The time window can be daily, weekly and monthly.</span></span> <span data-ttu-id="55965-134">所有時間視窗都需要開始時間和持續時間。</span><span class="sxs-lookup"><span data-stu-id="55965-134">All the time windows need a start time and a duration.</span></span>
    
   - <span data-ttu-id="55965-135">針對每日時間範圍，只需要 [開始時間] 和 [持續時間]。</span><span class="sxs-lookup"><span data-stu-id="55965-135">For a daily time window, only start time and duration are needed.</span></span> 
    
   - <span data-ttu-id="55965-136">針對每週時間視窗，需要星期幾，可以是一天或幾天。</span><span class="sxs-lookup"><span data-stu-id="55965-136">For a weekly time window, days of week are needed, which can be a single day or multiple days.</span></span>
    
   - <span data-ttu-id="55965-137">針對每月的時間範圍，可以有兩種類型。</span><span class="sxs-lookup"><span data-stu-id="55965-137">For a monthly time window, there can be two types.</span></span> <span data-ttu-id="55965-138">第一種類型是指定月份中的日期，這可以是一天。</span><span class="sxs-lookup"><span data-stu-id="55965-138">The first type is to specify the day of the month, which can be a single day.</span></span> <span data-ttu-id="55965-139">第二種類型是指定月份的周數，以及每週的天數，兩者都可以是單一專案或多個專案。</span><span class="sxs-lookup"><span data-stu-id="55965-139">The second type is to specify the weeks of the month, along with days of the week, which both can be a single item or multiple items.</span></span>
    
   - <span data-ttu-id="55965-140">每個租使用者都可以定義20個時間視窗。</span><span class="sxs-lookup"><span data-stu-id="55965-140">Each tenant can have 20 time windows defined.</span></span> <span data-ttu-id="55965-141">系統會針對新的租使用者建立預設時間視窗，作為作業系統更新和 Bits 更新的預設時間範圍。</span><span class="sxs-lookup"><span data-stu-id="55965-141">The default time window will be created for a new tenant as the default time window for operating system update and Bits update.</span></span> <span data-ttu-id="55965-142">執行下列 Cmdlet 來設定 [每日]、[每週] 或 [每月] 時間範圍：</span><span class="sxs-lookup"><span data-stu-id="55965-142">Run the following cmdlet(s) to set the daily, weekly or monthly time window:</span></span>
    
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

   - <span data-ttu-id="55965-143">指派更新時間視窗至網站。</span><span class="sxs-lookup"><span data-stu-id="55965-143">Assign update time windows to the site.</span></span> 
    
     <span data-ttu-id="55965-144">Bits 更新時間與 OS 更新時間視窗是單獨設定的。</span><span class="sxs-lookup"><span data-stu-id="55965-144">The Bits update time and OS update time windows are configured separately.</span></span> <span data-ttu-id="55965-145">這兩者都可以指派為單一或多個時間視窗。</span><span class="sxs-lookup"><span data-stu-id="55965-145">Both of them can be assigned single or multiple time windows.</span></span> <span data-ttu-id="55965-146">每個時間視窗都可以指派給不同的網站，以及不同用途（Bits 更新與 OS 更新）。</span><span class="sxs-lookup"><span data-stu-id="55965-146">Each time window can be assigned to different sites and different purpose (Bits update and OS update).</span></span> <span data-ttu-id="55965-147">執行下列 Cmdlet 來設定網站的時間範圍：</span><span class="sxs-lookup"><span data-stu-id="55965-147">Run the following cmdlet to set the time window for the site:</span></span> 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a><span data-ttu-id="55965-148">更新專用租使用者管理員認證</span><span class="sxs-lookup"><span data-stu-id="55965-148">Update the dedicated tenant admin credentials</span></span>
<span data-ttu-id="55965-149"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="55965-149"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="55965-150">雲端連接器的 Office 365 租使用者的系統管理變更是從擁有所需許可權的帳戶中進行。</span><span class="sxs-lookup"><span data-stu-id="55965-150">Administrative changes in the Office 365 tenant for Cloud Connector are made from an account with the needed permissions.</span></span> <span data-ttu-id="55965-151">在2.0 之前的雲端連接器版本中，該帳戶是專用的全域租使用者管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="55965-151">In Cloud Connector versions before 2.0, that account is a dedicated global tenant admin account.</span></span> <span data-ttu-id="55965-152">在雲端連接器版本2.0 及更新版本中，該帳戶可以是擁有商務用 Skype 系統管理員許可權的 Office 365 帳戶。</span><span class="sxs-lookup"><span data-stu-id="55965-152">In Cloud Connector versions 2.0 and later, that account can be an Office 365 account with Skype for Business Administrator rights.</span></span>
  
<span data-ttu-id="55965-153">如果您的系統管理員帳號憑證變更在 Office 365 中，您也需要在部署的每個雲端連接器裝置上執行下列系統管理員 PowerShell 命令，以更新雲端連接器中的本機快取認證：</span><span class="sxs-lookup"><span data-stu-id="55965-153">If your admin account credentials change in Office 365, you also need to update the locally cached credentials in Cloud Connector by running the following Administrator PowerShell command on each Cloud Connector appliance you have deployed:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a><span data-ttu-id="55965-154">更新主機伺服器的密碼</span><span class="sxs-lookup"><span data-stu-id="55965-154">Update the password for the host server</span></span>
<span data-ttu-id="55965-155"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="55965-155"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="55965-156">本節適用于雲端連接器版本2.0 及更新版本。</span><span class="sxs-lookup"><span data-stu-id="55965-156">This section is applicable to Cloud Connector version 2.0 and later.</span></span> 
  
<span data-ttu-id="55965-157">所有雲端連接器認證都儲存在下列檔案中： "%SystemDrive%\Programdata\Cloudconnector\credentials。\<CurrentUser\>.xml "。</span><span class="sxs-lookup"><span data-stu-id="55965-157">All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="55965-158">當主機伺服器上的密碼變更時，您將需要更新本機儲存的認證。</span><span class="sxs-lookup"><span data-stu-id="55965-158">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
  
<span data-ttu-id="55965-159">若要在雲端連接器裝置上更新本機儲存的認證，請使用[CcCredential](get-cccredential.md)和[CcCredential](set-cccredential.md) Cmdlet，然後依照下列步驟進行：</span><span class="sxs-lookup"><span data-stu-id="55965-159">To update the locally stored credentials on the Cloud Connector appliance, use the [Get-CcCredential](get-cccredential.md) and [Set-CcCredential](set-cccredential.md) cmdlets and follow these steps:</span></span>
  
1. <span data-ttu-id="55965-160">執行下列命令，以在稍後檢索您需要的密碼：</span><span class="sxs-lookup"><span data-stu-id="55965-160">Run the following commands to retrieve the passwords you will need later:</span></span> 
    
   - <span data-ttu-id="55965-161">CcCredential-AccountType DomainAdmin-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="55965-161">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="55965-162">CcCredential-AccountType VMAdmin-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="55965-162">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="55965-163">CcCredential-AccountType CceService-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="55965-163">Get-CcCredential -AccountType CceService -DisplayPassword</span></span>
    
2. <span data-ttu-id="55965-164">變更主機伺服器上您帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="55965-164">Change the password of your account on the host server.</span></span>
    
3. <span data-ttu-id="55965-165">重新開機主機伺服器。</span><span class="sxs-lookup"><span data-stu-id="55965-165">Restart the host server.</span></span>
    
4. <span data-ttu-id="55965-166">刪除下列檔案： "%SystemDrive%\Programdata\Cloudconnector\credentials。\<CurrentUser\>.xml "。</span><span class="sxs-lookup"><span data-stu-id="55965-166">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
5. <span data-ttu-id="55965-167">以系統管理員身分啟動 PowerShell 主控台，然後執行「Register-CcAppliance-Local」，在描述之後重新輸入密碼。</span><span class="sxs-lookup"><span data-stu-id="55965-167">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="55965-168">請務必輸入您在雲端連接器部署之前所輸入的密碼。</span><span class="sxs-lookup"><span data-stu-id="55965-168">Be sure you enter the same password you entered before for the Cloud Connector deployment.</span></span>
    
<span data-ttu-id="55965-169">根據預設，VmAdmin 和 DomainAdmin 使用與 CceService 相同的密碼。</span><span class="sxs-lookup"><span data-stu-id="55965-169">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="55965-170">如果在步驟1中傳回的 DomainAdmin、VMAdmin 和 CceService 密碼不同，您必須執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="55965-170">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
  
1. <span data-ttu-id="55965-171">執行 CcCredential-AccountType DomainAdmin，如下所示：</span><span class="sxs-lookup"><span data-stu-id="55965-171">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="55965-172">當系統提示您輸入舊帳號憑證時，請輸入您用於 CceService 密碼的認證。</span><span class="sxs-lookup"><span data-stu-id="55965-172">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="55965-173">當系統提示您輸入新的帳號憑證時，請輸入步驟1中傳回之 DomainAdmin 密碼的密碼。</span><span class="sxs-lookup"><span data-stu-id="55965-173">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
2. <span data-ttu-id="55965-174">執行 CcCredential-AccountType VmAdmin，如下所示：</span><span class="sxs-lookup"><span data-stu-id="55965-174">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="55965-175">當系統提示您輸入舊帳號憑證時，請輸入您用於 CceService 密碼的認證。</span><span class="sxs-lookup"><span data-stu-id="55965-175">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="55965-176">當系統提示您輸入新的帳號憑證時，請輸入步驟1中傳回之 VmAdmin 密碼的密碼。</span><span class="sxs-lookup"><span data-stu-id="55965-176">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
## <a name="update-the-password-for-the-cceservice-account"></a><span data-ttu-id="55965-177">更新 CceService 帳戶的密碼</span><span class="sxs-lookup"><span data-stu-id="55965-177">Update the password for the CceService account</span></span>
<span data-ttu-id="55965-178"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="55965-178"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="55965-179">本節適用于雲端連接器版本2.0.1 及更新版本。</span><span class="sxs-lookup"><span data-stu-id="55965-179">This section is applicable to Cloud Connector version 2.0.1 and later.</span></span> 
  
<span data-ttu-id="55965-180">雲端連接器服務會執行雲端連接器管理服務。</span><span class="sxs-lookup"><span data-stu-id="55965-180">The Cloud Connector service runs the Cloud Connector Management service.</span></span> <span data-ttu-id="55965-181">CceService 帳戶是在雲端連接器版本部署期間建立，並儲存在下列檔案中： "%SystemDrive%\Programdata\Cloudconnector\credentials。\<CurrentUser\>.Xml "和"%SystemDrive%\Programdata\Cloudconnector\credentials。。CceService "。</span><span class="sxs-lookup"><span data-stu-id="55965-181">The CceService account is created during the Cloud Connector Edition deployment and stored in the following files: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" and "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span></span>
  
<span data-ttu-id="55965-182">若要確保所有裝置都能存取網站目錄共用，在網站中部署的所有裝置上，CceService 帳戶的密碼都必須相同。</span><span class="sxs-lookup"><span data-stu-id="55965-182">To ensure that all appliances can access the site directory share, the password for the CceService account must be the same on all appliances deployed within the site.</span></span> <span data-ttu-id="55965-183">請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="55965-183">Keep the following in mind:</span></span>
  
- <span data-ttu-id="55965-184">根據預設，CceService 帳戶會設定為「密碼永不過期」。</span><span class="sxs-lookup"><span data-stu-id="55965-184">By default, the CceService account is configured as "Password never expires".</span></span> <span data-ttu-id="55965-185">更新密碼時，Microsoft 建議您保留此設定。</span><span class="sxs-lookup"><span data-stu-id="55965-185">When you update the password, Microsoft recommends keeping this configuration.</span></span>
    
- <span data-ttu-id="55965-186">您應該在非高峰使用期間更新密碼，並在自動更新時間範圍之外的 bits 或 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="55965-186">You should update the password during non-peak usage periods and outside of automatic update time windows for bits or Windows updates.</span></span> <span data-ttu-id="55965-187">當您更新密碼時，裝置必須排出並重新啟動，這需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="55965-187">When you update the password, the appliance needs to be drained and restarted, which takes some time.</span></span> <span data-ttu-id="55965-188">重新開機裝置將會中斷自動更新作業。</span><span class="sxs-lookup"><span data-stu-id="55965-188">Restarting the appliance will interrupt automatic update operations.</span></span> 
    
- <span data-ttu-id="55965-189">當您變更 CceService 帳戶密碼時，您必須指定所有認證，並在本機儲存的檔案中進行更新。</span><span class="sxs-lookup"><span data-stu-id="55965-189">When you change the CceService account password, you will need to specify all the credentials and update them in the locally stored file.</span></span> 
    
<span data-ttu-id="55965-190">針對屬於同一個 PSTN 網站的每個裝置，您必須指定下列專案：</span><span class="sxs-lookup"><span data-stu-id="55965-190">For each appliance that belongs to the same PSTN site, you will need to specify the following:</span></span> 
  
1. <span data-ttu-id="55965-191">執行下列命令，以取得您稍後會用到的帳戶名稱和密碼：</span><span class="sxs-lookup"><span data-stu-id="55965-191">Run the following commands to retrieve the account names and passwords that you will use later:</span></span>
    
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

2. <span data-ttu-id="55965-192">執行輸入 CcUpdate Cmdlet 來排出裝置，並將它移到 [手動維護模式]。</span><span class="sxs-lookup"><span data-stu-id="55965-192">Run the Enter-CcUpdate cmdlet to drain the appliance and move it into manual maintenance mode.</span></span>
    
3. <span data-ttu-id="55965-193">更新主機伺服器上的 CceService 帳戶密碼。</span><span class="sxs-lookup"><span data-stu-id="55965-193">Update the password of the CceService account on the host server.</span></span>
    
4. <span data-ttu-id="55965-194">重新開機主機伺服器。</span><span class="sxs-lookup"><span data-stu-id="55965-194">Restart the host server.</span></span>
    
5. <span data-ttu-id="55965-195">執行 Restore CcCredentials Cmdlet，以在描述之後重新輸入密碼。</span><span class="sxs-lookup"><span data-stu-id="55965-195">Run the Restore-CcCredentials cmdlet to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="55965-196">請確認您輸入的密碼與您在雲端連接器部署之前所輸入的密碼相同，但 CceService 帳戶除外。</span><span class="sxs-lookup"><span data-stu-id="55965-196">Be sure you enter the same password you entered before for the Cloud Connector deployment except for the CceService account.</span></span> <span data-ttu-id="55965-197">針對 CceService 帳戶，輸入您的新密碼。</span><span class="sxs-lookup"><span data-stu-id="55965-197">For the CceService account, enter your new password.</span></span> <span data-ttu-id="55965-198">請確定 CceService 帳戶的新密碼對於 PSTN 網站中的所有裝置都是相同的。</span><span class="sxs-lookup"><span data-stu-id="55965-198">Be sure the new password for the CceService account is the same for all appliances in the PSTN site.</span></span>
    
6. <span data-ttu-id="55965-199">根據預設，VmAdmin 和 DomainAdmin 使用與 CceService 相同的密碼。</span><span class="sxs-lookup"><span data-stu-id="55965-199">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="55965-200">如果在步驟1中傳回的 DomainAdmin、VMAdmin 和 CceService 密碼不同，您必須執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="55965-200">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
    
7. <span data-ttu-id="55965-201">執行 CcCredential-AccountType DomainAdmin，如下所示：</span><span class="sxs-lookup"><span data-stu-id="55965-201">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
   - <span data-ttu-id="55965-202">當系統提示您輸入舊帳號憑證時，請輸入您用於 CceService 密碼的認證。</span><span class="sxs-lookup"><span data-stu-id="55965-202">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="55965-203">當系統提示您輸入新的帳號憑證時，請輸入步驟1中傳回之 DomainAdmin 密碼的密碼。</span><span class="sxs-lookup"><span data-stu-id="55965-203">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
8. <span data-ttu-id="55965-204">執行 CcCredential-AccountType VmAdmin，如下所示：</span><span class="sxs-lookup"><span data-stu-id="55965-204">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
   - <span data-ttu-id="55965-205">當系統提示您輸入舊帳號憑證時，請輸入您用於 CceService 密碼的認證。</span><span class="sxs-lookup"><span data-stu-id="55965-205">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="55965-206">當系統提示您輸入新的帳號憑證時，請輸入步驟1中傳回之 VmAdmin 密碼的密碼。</span><span class="sxs-lookup"><span data-stu-id="55965-206">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
9. <span data-ttu-id="55965-207">執行 Exit CcUpdate Cmdlet，將裝置移出手動維護模式。</span><span class="sxs-lookup"><span data-stu-id="55965-207">Run the Exit-CcUpdate cmdlet to move the appliance out of manual maintenance mode.</span></span>
    
10. <span data-ttu-id="55965-208">在同一 PSTN 網站中的所有裝置上完成這些步驟之後，請在網站根目錄中刪除下列檔案：</span><span class="sxs-lookup"><span data-stu-id="55965-208">After you complete these steps on all appliances in the same PSTN site, delete the following files in the site root directory:</span></span>
    
    - <span data-ttu-id="55965-209">CcLockFile</span><span class="sxs-lookup"><span data-stu-id="55965-209">CcLockFile</span></span>
    
    - <span data-ttu-id="55965-210">Site_\<邊緣外部 Sip 池 fqdn\></span><span class="sxs-lookup"><span data-stu-id="55965-210">Site_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="55965-211">Tenant_\<邊緣外部 Sip 池 fqdn\></span><span class="sxs-lookup"><span data-stu-id="55965-211">Tenant_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="55965-212">TenantConfigLock_\<邊緣外部 Sip 池 fqdn\></span><span class="sxs-lookup"><span data-stu-id="55965-212">TenantConfigLock_\<Edge External Sip Pool fqdn\></span></span>
    
## <a name="add-a-new-sip-domain"></a><span data-ttu-id="55965-213">新增 SIP 網域</span><span class="sxs-lookup"><span data-stu-id="55965-213">Add a new SIP domain</span></span>
<span data-ttu-id="55965-214"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="55965-214"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="55965-215">若要將新的 SIP 網域（或多個 SIP 網域）新增到您現有的雲端連接器部署，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="55965-215">To add a new SIP domain (or multiple SIP domains) to your existing Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="55965-216">請確定您已完成 Office 365 中更新網域的步驟，並具備新增 DNS 記錄的功能。</span><span class="sxs-lookup"><span data-stu-id="55965-216">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="55965-217">如需如何在 Office 365 中設定網域的詳細資訊，請參閱[將網域新增至 office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。</span><span class="sxs-lookup"><span data-stu-id="55965-217">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="55965-218">使用新的 SIP 網域或網域更新雲端連接器設定檔。</span><span class="sxs-lookup"><span data-stu-id="55965-218">Update the Cloud Connector configuration file with the new SIP domain or domains.</span></span>
    
3. <span data-ttu-id="55965-219">針對您的雲端連接器設定中定義的每個 SIP 網域，要求新的 Edge 外部憑證。</span><span class="sxs-lookup"><span data-stu-id="55965-219">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="55965-220">針對新的邊緣外部憑證設定路徑，如下所示：</span><span class="sxs-lookup"><span data-stu-id="55965-220">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="55965-221">依照指示來[修改單一網站的](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite)設定，或[修改多個網站的](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)設定。</span><span class="sxs-lookup"><span data-stu-id="55965-221">Follow the instructions to [Modify the configuration of a single site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) or [Modify the configuration of multiple sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span></span>
    
## <a name="modify-the-primary-sip-domain"></a><span data-ttu-id="55965-222">修改主要 SIP 網域</span><span class="sxs-lookup"><span data-stu-id="55965-222">Modify the primary SIP domain</span></span>
<span data-ttu-id="55965-223"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="55965-223"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="55965-224">如果您需要在雲端連接器部署中變更主要 SIP 網域，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="55965-224">If you need to change the primary SIP domain in your Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="55965-225">請確定您已完成 Office 365 中更新網域的步驟，並具備新增 DNS 記錄的功能。</span><span class="sxs-lookup"><span data-stu-id="55965-225">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="55965-226">如需如何在 Office 365 中設定網域的詳細資訊，請參閱[將網域新增至 office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。</span><span class="sxs-lookup"><span data-stu-id="55965-226">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="55965-227">使用新的 SIP 網域更新雲端連接器設定檔。</span><span class="sxs-lookup"><span data-stu-id="55965-227">Update the Cloud Connector configuration file with the new SIP domain.</span></span>
    
3. <span data-ttu-id="55965-228">針對您的雲端連接器設定中定義的每個 SIP 網域，要求新的 Edge 外部憑證。</span><span class="sxs-lookup"><span data-stu-id="55965-228">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="55965-229">針對新的邊緣外部憑證設定路徑，如下所示：</span><span class="sxs-lookup"><span data-stu-id="55965-229">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="55965-230">在雲端連接器上的系統管理員 PowerShell 中執行下列 Cmdlet，以移除網站中每個裝置的租使用者註冊：</span><span class="sxs-lookup"><span data-stu-id="55965-230">Remove the tenant registration for each appliance in a site by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    <span data-ttu-id="55965-231">在商務用 Skype Online PowerShell 中執行下列 Cmdlet，以移除每個網站的網站註冊：</span><span class="sxs-lookup"><span data-stu-id="55965-231">Remove the site registration for each site by running the following cmdlet in Skype for Business Online PowerShell:</span></span>
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    <span data-ttu-id="55965-232">在雲端連接器上的系統管理員 PowerShell 中執行下列 Cmdlet，以卸載每個裝置：</span><span class="sxs-lookup"><span data-stu-id="55965-232">Uninstall each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     <span data-ttu-id="55965-233">在雲端連接器上的系統管理員 PowerShell 中執行下列 Cmdlet，以登錄每個裝置：</span><span class="sxs-lookup"><span data-stu-id="55965-233">Register each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     <span data-ttu-id="55965-234">透過在雲端連接器上的系統管理員 PowerShell 中執行下列 Cmdlet，逐個安裝每個裝置：</span><span class="sxs-lookup"><span data-stu-id="55965-234">Install each appliance, one by one, by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a><span data-ttu-id="55965-235">以新憑證取代外部邊緣憑證</span><span class="sxs-lookup"><span data-stu-id="55965-235">Replace the external Edge certificate with a new certificate</span></span>
<span data-ttu-id="55965-236"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="55965-236"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="55965-237">當您需要取代雲端連接器裝置上的外部邊緣憑證時，您必須取得新的邊緣憑證、準備包含私人金鑰和完整憑證連結的 PFX 檔案，然後在每個裝置上執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="55965-237">When you need to replace the external Edge certificate on your Cloud Connector appliances, you will need to obtain a new Edge certificate, prepare the PFX file containing the Private Key and full certificate chain, and then do the following on each appliance:</span></span>
  
1. <span data-ttu-id="55965-238">使用 Enter CcUpdate Cmdlet 將裝置置於 [維護] 模式。</span><span class="sxs-lookup"><span data-stu-id="55965-238">Put the appliance in maintenance mode by using the Enter-CcUpdate cmdlet.</span></span>
    
2. <span data-ttu-id="55965-239">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="55965-239">Run the following command:</span></span> 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    <span data-ttu-id="55965-240">如果新憑證的密碼與舊版相同，則會成功匯入。</span><span class="sxs-lookup"><span data-stu-id="55965-240">If the password of the new certificate is the same as the old, the import will be successful.</span></span> <span data-ttu-id="55965-241">如果密碼不同，您會收到錯誤訊息，指出密碼錯誤，而且您必須執行 CcAppliance Cmdlet 與-Local 參數，然後重複步驟2，以重設密碼。</span><span class="sxs-lookup"><span data-stu-id="55965-241">If the password is different, you will receive an error that the password is wrong, and you will need to reset the password by running the Register-CcAppliance cmdlet with the -Local parameter, and then repeating step 2.</span></span> 
    
4. <span data-ttu-id="55965-242">使用 CcUpdate Cmdlet 讓裝置離開維護模式。</span><span class="sxs-lookup"><span data-stu-id="55965-242">Take the appliance out of maintenance mode by using the Exit -CcUpdate cmdlet.</span></span>
    

