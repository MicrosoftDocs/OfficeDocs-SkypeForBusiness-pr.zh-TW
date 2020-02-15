---
title: 修改現有的雲端連接器部署的組態
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
description: 遵循此主題以便修改現有的 Skype 商務雲端連接器 Edition 1.4.1 或更新版本的部署的組態中的步驟。
ms.openlocfilehash: 4c2c0b8ad5340cd4ae4275f1ac009bf3d9d3ec0b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018004"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a><span data-ttu-id="a5107-103">修改現有的雲端連接器部署的組態</span><span class="sxs-lookup"><span data-stu-id="a5107-103">Modify the configuration of an existing Cloud Connector deployment</span></span>
 
<span data-ttu-id="a5107-104">遵循此主題以便修改現有的 Skype 商務雲端連接器 Edition 1.4.1 或更新版本的部署的組態中的步驟。</span><span class="sxs-lookup"><span data-stu-id="a5107-104">Follow the steps in this topic to modify the configuration of an existing Skype for Business Cloud Connector Edition 1.4.1 or later deployment.</span></span> 
  
## <a name="modify-the-configuration-of-a-single-site"></a><span data-ttu-id="a5107-105">修改單一站台的組態</span><span class="sxs-lookup"><span data-stu-id="a5107-105">Modify the configuration of a single site</span></span>
<span data-ttu-id="a5107-106"><a name="BKMK_SIngleSite"> </a></span><span class="sxs-lookup"><span data-stu-id="a5107-106"><a name="BKMK_SIngleSite"> </a></span></span>

<span data-ttu-id="a5107-107">如果沒有在網站中，只有一個 appliance 時您想要變更的組態設定，裝置所傳入部署之後，您可以修改 CloudConnector.ini 檔案，並開始重新部署。</span><span class="sxs-lookup"><span data-stu-id="a5107-107">If there is only one appliance in the site, when you want to change the configuration settings after the appliance is deployed, you can modify the CloudConnector.ini file and start the deployment again.</span></span>
  
1. <span data-ttu-id="a5107-108">執行下列 cmdlet 以解除安裝所有現有的主機伺服器上的虛擬機器：</span><span class="sxs-lookup"><span data-stu-id="a5107-108">Run the following cmdlet to uninstall all existing virtual machines on the host server:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="a5107-109">執行下列 cmdlet 以取消登錄該裝置：</span><span class="sxs-lookup"><span data-stu-id="a5107-109">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="a5107-110">更新 CloudConnector.ini 目錄中的檔案應用裝置。</span><span class="sxs-lookup"><span data-stu-id="a5107-110">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="a5107-111">執行下列 cmdlet 以更新設定: （時，才適用第 2 版; 舊版此步驟，請跳到下一步）。</span><span class="sxs-lookup"><span data-stu-id="a5107-111">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="a5107-112">執行下列 cmdlet 以重新註冊裝置所傳入：</span><span class="sxs-lookup"><span data-stu-id="a5107-112">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="a5107-113">執行下列 cmdlet 以安裝 Skype for Business 雲端連接器版：</span><span class="sxs-lookup"><span data-stu-id="a5107-113">Run the following cmdlet to install Skype for Business Cloud Connector Edition:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

<span data-ttu-id="a5107-114">如果有多個 appliance 站台中，您需要遵循這些步驟，修改 CloudConnector.ini 檔案，並重新部署設備逐一。</span><span class="sxs-lookup"><span data-stu-id="a5107-114">If there is more than one appliance in the site, you'll need to follow these steps, modify the CloudConnector.ini file, and redeploy the appliances one by one.</span></span>
  
1. <span data-ttu-id="a5107-115">執行下列 cmdlet 以解除安裝所有目前 appliance 上現有的虛擬機器：</span><span class="sxs-lookup"><span data-stu-id="a5107-115">Run the following cmdlet to uninstall all existing virtual machines on the current appliance:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="a5107-116">執行下列 cmdlet 以取消登錄該裝置：</span><span class="sxs-lookup"><span data-stu-id="a5107-116">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="a5107-117">更新 CloudConnector.ini 目錄中的檔案應用裝置。</span><span class="sxs-lookup"><span data-stu-id="a5107-117">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="a5107-118">執行下列 cmdlet 以更新設定: （時，才適用第 2 版; 舊版此步驟，請跳到下一步）。</span><span class="sxs-lookup"><span data-stu-id="a5107-118">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="a5107-119">執行下列 cmdlet 以重新註冊裝置所傳入：</span><span class="sxs-lookup"><span data-stu-id="a5107-119">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="a5107-120">所有其他設備中挑選最新的設定備份的網站上執行下列 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a5107-120">Run the following cmdlet on all other appliances in the site to pick up the latest configuration:</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

7. <span data-ttu-id="a5107-121">執行下列 cmdlet 以目前 appliance 上部署雲端連接器：</span><span class="sxs-lookup"><span data-stu-id="a5107-121">Run the following cmdlet to redeploy Cloud Connector on the current appliance:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a><span data-ttu-id="a5107-122">修改多個站台的組態</span><span class="sxs-lookup"><span data-stu-id="a5107-122">Modify the configuration of multiple sites</span></span>
<span data-ttu-id="a5107-123"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="a5107-123"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="a5107-124">若要修改的組態中部署多個站台，請依照下列單一站台，一次更新一個站台的步驟。</span><span class="sxs-lookup"><span data-stu-id="a5107-124">To modify the configuration for multiple sites in a deployment, follow the steps for a single site, updating one site at a time.</span></span>
  
## <a name="modify-the-configuration-of-your-office-365-tenant-to-enable-automatic-updates"></a><span data-ttu-id="a5107-125">修改 Office 365 租用戶啟用自動更新的組態</span><span class="sxs-lookup"><span data-stu-id="a5107-125">Modify the configuration of your Office 365 tenant to enable automatic updates</span></span>
<span data-ttu-id="a5107-126"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="a5107-126"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="a5107-127">若要啟用作業系統自動更新 」 和 「 位元自動更新，您必須使用用 Skype online 管理的企業租用戶系統管理員帳戶及租用戶遠端 PowerShell，如下所示的使用。</span><span class="sxs-lookup"><span data-stu-id="a5107-127">To enable operating system automatic updates and Bits automatic updates, you must use the Skype for Business tenant admin account for online management and use tenant remote PowerShell as follows.</span></span>
  
<span data-ttu-id="a5107-128">如果您停用作業系統自動更新 」 或 「 位元自動更新，「 主機 」 和 「 虛擬機器可能遺漏重要的 Windows 更新，以及雲端連接器不會自動升級到新版本。</span><span class="sxs-lookup"><span data-stu-id="a5107-128">If you disabled operating system automatic updates or Bits automatic updates, your host and virtual machine may miss important Windows updates, and Cloud Connector will not upgrade to the new version automatically.</span></span> <span data-ttu-id="a5107-129">強烈建議您啟用 [自動更新。</span><span class="sxs-lookup"><span data-stu-id="a5107-129">It is highly recommended that you enable automatic updates.</span></span>
  
1. <span data-ttu-id="a5107-130">站台的 EnableAutoUpdate 屬性必須設為 true （預設值）。</span><span class="sxs-lookup"><span data-stu-id="a5107-130">The EnableAutoUpdate property of the site needs to be set to true (the default value).</span></span> <span data-ttu-id="a5107-131">執行下列 cmdlet 以確保 EnableAutoUpdate 設為 true:</span><span class="sxs-lookup"><span data-stu-id="a5107-131">Run the following cmdlet to make sure EnableAutoUpdate is set to true:</span></span>
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. <span data-ttu-id="a5107-132">租用戶中建立自動更新時間間隔。</span><span class="sxs-lookup"><span data-stu-id="a5107-132">Create auto update time window for the tenant.</span></span>
    
    <span data-ttu-id="a5107-133">每日、 每週及每月，可以是時間範圍。</span><span class="sxs-lookup"><span data-stu-id="a5107-133">The time window can be daily, weekly and monthly.</span></span> <span data-ttu-id="a5107-134">所有時間 windows 都需要開始時間] 和 [持續時間。</span><span class="sxs-lookup"><span data-stu-id="a5107-134">All the time windows need a start time and a duration.</span></span>
    
   - <span data-ttu-id="a5107-135">針對每日時間] 視窗中，所需僅 [開始時間] 和 [持續時間。</span><span class="sxs-lookup"><span data-stu-id="a5107-135">For a daily time window, only start time and duration are needed.</span></span> 
    
   - <span data-ttu-id="a5107-136">是每週的時間視窗，所需的一週的天數，可以是一天或數天。</span><span class="sxs-lookup"><span data-stu-id="a5107-136">For a weekly time window, days of week are needed, which can be a single day or multiple days.</span></span>
    
   - <span data-ttu-id="a5107-137">針對每月的時間範圍，可以有兩種類型。</span><span class="sxs-lookup"><span data-stu-id="a5107-137">For a monthly time window, there can be two types.</span></span> <span data-ttu-id="a5107-138">第一個類型是指定月份日期，可以是一天。</span><span class="sxs-lookup"><span data-stu-id="a5107-138">The first type is to specify the day of the month, which can be a single day.</span></span> <span data-ttu-id="a5107-139">第二個類型是月的指定、 週，這兩個可以是月的單一項目或多個項目以及星期數。</span><span class="sxs-lookup"><span data-stu-id="a5107-139">The second type is to specify the weeks of the month, along with days of the week, which both can be a single item or multiple items.</span></span>
    
   - <span data-ttu-id="a5107-140">每個租用戶可以有 20 次 windows 定義。</span><span class="sxs-lookup"><span data-stu-id="a5107-140">Each tenant can have 20 time windows defined.</span></span> <span data-ttu-id="a5107-141">預設的 [時間] 視窗將會建立新租用戶，為作業系統更新] 和 [位元更新預設時間範圍。</span><span class="sxs-lookup"><span data-stu-id="a5107-141">The default time window will be created for a new tenant as the default time window for operating system update and Bits update.</span></span> <span data-ttu-id="a5107-142">執行下列 cmdlet(s) 若要設定的每日、 每週或每月時段：</span><span class="sxs-lookup"><span data-stu-id="a5107-142">Run the following cmdlet(s) to set the daily, weekly or monthly time window:</span></span>
    
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

   - <span data-ttu-id="a5107-143">將更新時間 windows 指派至網站。</span><span class="sxs-lookup"><span data-stu-id="a5107-143">Assign update time windows to the site.</span></span> 
    
     <span data-ttu-id="a5107-144">位元更新時間和 OS 更新時間 windows 會個別設定。</span><span class="sxs-lookup"><span data-stu-id="a5107-144">The Bits update time and OS update time windows are configured separately.</span></span> <span data-ttu-id="a5107-145">兩者都可以指派單一或多個時間 windows。</span><span class="sxs-lookup"><span data-stu-id="a5107-145">Both of them can be assigned single or multiple time windows.</span></span> <span data-ttu-id="a5107-146">每個時間間隔可以指派給不同的站台和不同用途 （位元更新和 OS 更新）。</span><span class="sxs-lookup"><span data-stu-id="a5107-146">Each time window can be assigned to different sites and different purpose (Bits update and OS update).</span></span> <span data-ttu-id="a5107-147">執行下列 cmdlet 以設定網站的 [時間] 視窗：</span><span class="sxs-lookup"><span data-stu-id="a5107-147">Run the following cmdlet to set the time window for the site:</span></span> 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a><span data-ttu-id="a5107-148">更新專用的租用戶系統管理員認證</span><span class="sxs-lookup"><span data-stu-id="a5107-148">Update the dedicated tenant admin credentials</span></span>
<span data-ttu-id="a5107-149"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="a5107-149"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="a5107-150">從具有必要的權限的帳戶進行雲端連接器在 Office 365 租用戶中的系統管理變更。</span><span class="sxs-lookup"><span data-stu-id="a5107-150">Administrative changes in the Office 365 tenant for Cloud Connector are made from an account with the needed permissions.</span></span> <span data-ttu-id="a5107-151">在雲端連接器版本 2.0 之前，該帳戶是專用的全域租用戶系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="a5107-151">In Cloud Connector versions before 2.0, that account is a dedicated global tenant admin account.</span></span> <span data-ttu-id="a5107-152">在雲端連接器版本 2.0 和更新版本，該帳戶可以是 Office 365 帳戶與 Skype 商務系統管理員權限。</span><span class="sxs-lookup"><span data-stu-id="a5107-152">In Cloud Connector versions 2.0 and later, that account can be an Office 365 account with Skype for Business Administrator rights.</span></span>
  
<span data-ttu-id="a5107-153">如果您的系統管理員帳戶認證變更 Office 365 中，您也需要您已部署每個雲端連接器 appliance 上執行下列系統管理員的 PowerShell 命令來更新雲端連接器中的本機快取的認證：</span><span class="sxs-lookup"><span data-stu-id="a5107-153">If your admin account credentials change in Office 365, you also need to update the locally cached credentials in Cloud Connector by running the following Administrator PowerShell command on each Cloud Connector appliance you have deployed:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a><span data-ttu-id="a5107-154">更新主機伺服器的密碼</span><span class="sxs-lookup"><span data-stu-id="a5107-154">Update the password for the host server</span></span>
<span data-ttu-id="a5107-155"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="a5107-155"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="a5107-156">此區段可用於雲端連接器第 2.0 版及更新版本。</span><span class="sxs-lookup"><span data-stu-id="a5107-156">This section is applicable to Cloud Connector version 2.0 and later.</span></span> 
  
<span data-ttu-id="a5107-157">所有雲端連接器認證會都儲存在下列檔案:"%systemdrive%\programdata\cloudconnector\credentials。\<CurrentUser\>.xml 」。</span><span class="sxs-lookup"><span data-stu-id="a5107-157">All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="a5107-158">在主機伺服器上的密碼變更時，您必須更新本機已儲存的認證。</span><span class="sxs-lookup"><span data-stu-id="a5107-158">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
  
<span data-ttu-id="a5107-159">若要更新雲端連接器 appliance 上本機已儲存的認證，使用[Get-CcCredential](get-cccredential.md)和[設定 CcCredential](set-cccredential.md)指令程式，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="a5107-159">To update the locally stored credentials on the Cloud Connector appliance, use the [Get-CcCredential](get-cccredential.md) and [Set-CcCredential](set-cccredential.md) cmdlets and follow these steps:</span></span>
  
1. <span data-ttu-id="a5107-160">執行下列命令，以擷取您稍後需要密碼：</span><span class="sxs-lookup"><span data-stu-id="a5107-160">Run the following commands to retrieve the passwords you will need later:</span></span> 
    
   - <span data-ttu-id="a5107-161">取得 CcCredential-AccountType DomainAdmin DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="a5107-161">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="a5107-162">取得 CcCredential-AccountType VMAdmin DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="a5107-162">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="a5107-163">取得 CcCredential-AccountType CceService DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="a5107-163">Get-CcCredential -AccountType CceService -DisplayPassword</span></span>
    
2. <span data-ttu-id="a5107-164">變更您在主機伺服器上的帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="a5107-164">Change the password of your account on the host server.</span></span>
    
3. <span data-ttu-id="a5107-165">重新啟動主應用程式伺服器。</span><span class="sxs-lookup"><span data-stu-id="a5107-165">Restart the host server.</span></span>
    
4. <span data-ttu-id="a5107-166">刪除下列檔案:"%systemdrive%\programdata\cloudconnector\credentials。\<CurrentUser\>.xml 」。</span><span class="sxs-lookup"><span data-stu-id="a5107-166">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
5. <span data-ttu-id="a5107-167">啟動 PowerShell 主控台，身為管理員，然後再執行 「 註冊 CcAppliance-本機 「 重新輸入密碼描述。</span><span class="sxs-lookup"><span data-stu-id="a5107-167">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="a5107-168">請確定您輸入您所輸入之前的雲端連接器部署相同的密碼。</span><span class="sxs-lookup"><span data-stu-id="a5107-168">Be sure you enter the same password you entered before for the Cloud Connector deployment.</span></span>
    
<span data-ttu-id="a5107-169">根據預設，VmAdmin 和 DomainAdmin 會使用相同的密碼作為 CceService。</span><span class="sxs-lookup"><span data-stu-id="a5107-169">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="a5107-170">如果步驟 1 中傳回 DomainAdmin、 VMAdmin，以及 CceService 密碼不同，您必須執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="a5107-170">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
  
1. <span data-ttu-id="a5107-171">執行設定 CcCredential AccountType DomainAdmin 如下所示：</span><span class="sxs-lookup"><span data-stu-id="a5107-171">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="a5107-172">時提示輸入舊的帳戶認證，請輸入您用於 CceService 密碼的認證。</span><span class="sxs-lookup"><span data-stu-id="a5107-172">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="a5107-173">時提示輸入新的帳戶認證，請在步驟 1 中傳回的 DomainAdmin 密碼輸入密碼。</span><span class="sxs-lookup"><span data-stu-id="a5107-173">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
2. <span data-ttu-id="a5107-174">執行設定 CcCredential AccountType VmAdmin 如下所示：</span><span class="sxs-lookup"><span data-stu-id="a5107-174">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="a5107-175">時提示輸入舊的帳戶認證，請輸入您用於 CceService 密碼的認證。</span><span class="sxs-lookup"><span data-stu-id="a5107-175">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="a5107-176">時提示輸入新的帳戶認證，請在步驟 1 中傳回的 VmAdmin 密碼輸入密碼。</span><span class="sxs-lookup"><span data-stu-id="a5107-176">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
## <a name="update-the-password-for-the-cceservice-account"></a><span data-ttu-id="a5107-177">更新 CceService 帳戶的密碼</span><span class="sxs-lookup"><span data-stu-id="a5107-177">Update the password for the CceService account</span></span>
<span data-ttu-id="a5107-178"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="a5107-178"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="a5107-179">此區段可用於雲端連接器 2.0.1 版及更新版本。</span><span class="sxs-lookup"><span data-stu-id="a5107-179">This section is applicable to Cloud Connector version 2.0.1 and later.</span></span> 
  
<span data-ttu-id="a5107-180">雲端連接器服務會執行雲端連接器管理服務。</span><span class="sxs-lookup"><span data-stu-id="a5107-180">The Cloud Connector service runs the Cloud Connector Management service.</span></span> <span data-ttu-id="a5107-181">CceService 帳戶是在雲端連接器 Edition 部署期間建立並儲存在下列檔案:"%systemdrive%\programdata\cloudconnector\credentials。\<CurrentUser\>.xml 」 和 「 %systemdrive%\programdata\cloudconnector\credentials..CceService.xml 」。</span><span class="sxs-lookup"><span data-stu-id="a5107-181">The CceService account is created during the Cloud Connector Edition deployment and stored in the following files: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" and "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span></span>
  
<span data-ttu-id="a5107-182">若要確保所有設備可以都存取的網站目錄共用，CceService 帳戶的密碼必須部署站台內的所有設備相同。</span><span class="sxs-lookup"><span data-stu-id="a5107-182">To ensure that all appliances can access the site directory share, the password for the CceService account must be the same on all appliances deployed within the site.</span></span> <span data-ttu-id="a5107-183">請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="a5107-183">Keep the following in mind:</span></span>
  
- <span data-ttu-id="a5107-184">根據預設，CceService 帳戶已設定為 「 密碼永不過期 」。</span><span class="sxs-lookup"><span data-stu-id="a5107-184">By default, the CceService account is configured as "Password never expires".</span></span> <span data-ttu-id="a5107-185">當您更新密碼時，Microsoft 建議保持這種組態。</span><span class="sxs-lookup"><span data-stu-id="a5107-185">When you update the password, Microsoft recommends keeping this configuration.</span></span>
    
- <span data-ttu-id="a5107-186">您應該在非尖峰使用時段和外部的位元或 Windows 更新的 [自動更新時間 windows 更新密碼。</span><span class="sxs-lookup"><span data-stu-id="a5107-186">You should update the password during non-peak usage periods and outside of automatic update time windows for bits or Windows updates.</span></span> <span data-ttu-id="a5107-187">當您更新密碼時，裝置所傳入必須清空並重新啟動，這需要花一些時間。</span><span class="sxs-lookup"><span data-stu-id="a5107-187">When you update the password, the appliance needs to be drained and restarted, which takes some time.</span></span> <span data-ttu-id="a5107-188">重新啟動該裝置將會中斷自動更新作業。</span><span class="sxs-lookup"><span data-stu-id="a5107-188">Restarting the appliance will interrupt automatic update operations.</span></span> 
    
- <span data-ttu-id="a5107-189">當您變更 CceService 帳戶密碼時，您必須指定所有的認證，並加以更新在本機儲存檔案。</span><span class="sxs-lookup"><span data-stu-id="a5107-189">When you change the CceService account password, you will need to specify all the credentials and update them in the locally stored file.</span></span> 
    
<span data-ttu-id="a5107-190">屬於相同的 PSTN 網站每個 appliance，您必須指定下列項目：</span><span class="sxs-lookup"><span data-stu-id="a5107-190">For each appliance that belongs to the same PSTN site, you will need to specify the following:</span></span> 
  
1. <span data-ttu-id="a5107-191">執行下列命令，以擷取的帳戶名稱和密碼，您將在稍後使用：</span><span class="sxs-lookup"><span data-stu-id="a5107-191">Run the following commands to retrieve the account names and passwords that you will use later:</span></span>
    
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

2. <span data-ttu-id="a5107-192">執行 redirect-message appliance，並將它移到手動維護模式 Enter CcUpdate cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a5107-192">Run the Enter-CcUpdate cmdlet to drain the appliance and move it into manual maintenance mode.</span></span>
    
3. <span data-ttu-id="a5107-193">更新主機伺服器上的 CceService 帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="a5107-193">Update the password of the CceService account on the host server.</span></span>
    
4. <span data-ttu-id="a5107-194">重新啟動主應用程式伺服器。</span><span class="sxs-lookup"><span data-stu-id="a5107-194">Restart the host server.</span></span>
    
5. <span data-ttu-id="a5107-195">執行還原 CcCredentials 指令程式重新輸入密碼描述。</span><span class="sxs-lookup"><span data-stu-id="a5107-195">Run the Restore-CcCredentials cmdlet to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="a5107-196">請確定您輸入您所輸入之前的雲端連接器部署，但不包括 CceService 帳戶相同的密碼。</span><span class="sxs-lookup"><span data-stu-id="a5107-196">Be sure you enter the same password you entered before for the Cloud Connector deployment except for the CceService account.</span></span> <span data-ttu-id="a5107-197">CceService 帳戶] 中，輸入新的密碼。</span><span class="sxs-lookup"><span data-stu-id="a5107-197">For the CceService account, enter your new password.</span></span> <span data-ttu-id="a5107-198">請確定 CceService 帳戶的新密碼是相同的 PSTN 站台中的所有設備。</span><span class="sxs-lookup"><span data-stu-id="a5107-198">Be sure the new password for the CceService account is the same for all appliances in the PSTN site.</span></span>
    
6. <span data-ttu-id="a5107-199">根據預設，VmAdmin 和 DomainAdmin 會使用相同的密碼作為 CceService。</span><span class="sxs-lookup"><span data-stu-id="a5107-199">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="a5107-200">如果步驟 1 中傳回 DomainAdmin、 VMAdmin，以及 CceService 密碼不同，您必須執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="a5107-200">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
    
7. <span data-ttu-id="a5107-201">執行設定 CcCredential AccountType DomainAdmin 如下所示：</span><span class="sxs-lookup"><span data-stu-id="a5107-201">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
   - <span data-ttu-id="a5107-202">時提示輸入舊的帳戶認證，請輸入您用於 CceService 密碼的認證。</span><span class="sxs-lookup"><span data-stu-id="a5107-202">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="a5107-203">時提示輸入新的帳戶認證，請在步驟 1 中傳回的 DomainAdmin 密碼輸入密碼。</span><span class="sxs-lookup"><span data-stu-id="a5107-203">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
8. <span data-ttu-id="a5107-204">執行設定 CcCredential AccountType VmAdmin 如下所示：</span><span class="sxs-lookup"><span data-stu-id="a5107-204">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
   - <span data-ttu-id="a5107-205">時提示輸入舊的帳戶認證，請輸入您用於 CceService 密碼的認證。</span><span class="sxs-lookup"><span data-stu-id="a5107-205">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="a5107-206">時提示輸入新的帳戶認證，請在步驟 1 中傳回的 VmAdmin 密碼輸入密碼。</span><span class="sxs-lookup"><span data-stu-id="a5107-206">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
9. <span data-ttu-id="a5107-207">執行結束 CcUpdate cmdlet 來移動裝置所傳入手動維護模式。</span><span class="sxs-lookup"><span data-stu-id="a5107-207">Run the Exit-CcUpdate cmdlet to move the appliance out of manual maintenance mode.</span></span>
    
10. <span data-ttu-id="a5107-208">完成這些步驟在相同的 PSTN 站台中的所有設備之後，刪除的網站根目錄中的下列檔案：</span><span class="sxs-lookup"><span data-stu-id="a5107-208">After you complete these steps on all appliances in the same PSTN site, delete the following files in the site root directory:</span></span>
    
    - <span data-ttu-id="a5107-209">CcLockFile</span><span class="sxs-lookup"><span data-stu-id="a5107-209">CcLockFile</span></span>
    
    - <span data-ttu-id="a5107-210">Site_\<Edge 外部 Sip 集區 fqdn\></span><span class="sxs-lookup"><span data-stu-id="a5107-210">Site_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="a5107-211">Tenant_\<Edge 外部 Sip 集區 fqdn\></span><span class="sxs-lookup"><span data-stu-id="a5107-211">Tenant_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="a5107-212">TenantConfigLock_\<Edge 外部 Sip 集區 fqdn\></span><span class="sxs-lookup"><span data-stu-id="a5107-212">TenantConfigLock_\<Edge External Sip Pool fqdn\></span></span>
    
## <a name="add-a-new-sip-domain"></a><span data-ttu-id="a5107-213">新增新的 SIP 網域</span><span class="sxs-lookup"><span data-stu-id="a5107-213">Add a new SIP domain</span></span>
<span data-ttu-id="a5107-214"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="a5107-214"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="a5107-215">若要新增您現有的雲端連接器部署新的 SIP 網域 （或多個 SIP 網域），執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="a5107-215">To add a new SIP domain (or multiple SIP domains) to your existing Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="a5107-216">請確定您已完成的步驟來更新 Office 365 中的網域，並有能力新增 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="a5107-216">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="a5107-217">如需如何設定 Office 365 中的網域的詳細資訊，請參閱[新增網域至 Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。</span><span class="sxs-lookup"><span data-stu-id="a5107-217">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="a5107-218">使用新的 SIP 網域] 或 [網域更新雲端連接器組態檔。</span><span class="sxs-lookup"><span data-stu-id="a5107-218">Update the Cloud Connector configuration file with the new SIP domain or domains.</span></span>
    
3. <span data-ttu-id="a5107-219">要求新的 Edge 外部憑證 sip.domain 每個 SIP 網域雲端連接器組態中所定義的其他 SAN (英文） 名稱。</span><span class="sxs-lookup"><span data-stu-id="a5107-219">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="a5107-220">設定新的 Edge 外部憑證的路徑，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a5107-220">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="a5107-221">若要[修改的單一站台組態](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite)] 或 [[修改的多個站台組態](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)，請遵循指示。</span><span class="sxs-lookup"><span data-stu-id="a5107-221">Follow the instructions to [Modify the configuration of a single site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) or [Modify the configuration of multiple sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span></span>
    
## <a name="modify-the-primary-sip-domain"></a><span data-ttu-id="a5107-222">修改的主要 SIP 網域</span><span class="sxs-lookup"><span data-stu-id="a5107-222">Modify the primary SIP domain</span></span>
<span data-ttu-id="a5107-223"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="a5107-223"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="a5107-224">如果您要變更定域機組連接器部署中的主要 SIP 網域，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="a5107-224">If you need to change the primary SIP domain in your Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="a5107-225">請確定您已完成的步驟來更新 Office 365 中的網域，並有能力新增 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="a5107-225">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="a5107-226">如需如何設定 Office 365 中的網域的詳細資訊，請參閱[新增網域至 Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。</span><span class="sxs-lookup"><span data-stu-id="a5107-226">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="a5107-227">使用新的 SIP 網域來更新雲端連接器組態檔。</span><span class="sxs-lookup"><span data-stu-id="a5107-227">Update the Cloud Connector configuration file with the new SIP domain.</span></span>
    
3. <span data-ttu-id="a5107-228">要求新的 Edge 外部憑證 sip.domain 每個 SIP 網域雲端連接器組態中所定義的其他 SAN (英文） 名稱。</span><span class="sxs-lookup"><span data-stu-id="a5107-228">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="a5107-229">設定新的 Edge 外部憑證的路徑，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a5107-229">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="a5107-230">移除網站中每個 appliance 的租用戶註冊雲端連接器上系統管理員 PowerShell 中執行下列 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a5107-230">Remove the tenant registration for each appliance in a site by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    <span data-ttu-id="a5107-231">移除的每個網站的網站註冊商務 Online powershell 中 Skype 執行下列 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a5107-231">Remove the site registration for each site by running the following cmdlet in Skype for Business Online PowerShell:</span></span>
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    <span data-ttu-id="a5107-232">解除安裝每個 appliance 雲端連接器上系統管理員 PowerShell 中執行下列 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a5107-232">Uninstall each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     <span data-ttu-id="a5107-233">登錄每個 appliance 雲端連接器上系統管理員 PowerShell 中執行下列 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a5107-233">Register each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     <span data-ttu-id="a5107-234">安裝每個 appliance，一個接著一個，藉由雲端連接器上系統管理員 PowerShell 中執行下列 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a5107-234">Install each appliance, one by one, by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a><span data-ttu-id="a5107-235">外部邊緣憑證取代為新的憑證</span><span class="sxs-lookup"><span data-stu-id="a5107-235">Replace the external Edge certificate with a new certificate</span></span>
<span data-ttu-id="a5107-236"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="a5107-236"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="a5107-237">當您要取代上您雲端連接器設備的外部邊緣憑證時，您必須取得新的邊緣憑證，準備 PFX 檔案包含私密金鑰及整個憑證鏈結，然後執行下列每個 appliance 上：</span><span class="sxs-lookup"><span data-stu-id="a5107-237">When you need to replace the external Edge certificate on your Cloud Connector appliances, you will need to obtain a new Edge certificate, prepare the PFX file containing the Private Key and full certificate chain, and then do the following on each appliance:</span></span>
  
1. <span data-ttu-id="a5107-238">使用 Enter CcUpdate 指令程式會處於維護模式裝置所傳入。</span><span class="sxs-lookup"><span data-stu-id="a5107-238">Put the appliance in maintenance mode by using the Enter-CcUpdate cmdlet.</span></span>
    
2. <span data-ttu-id="a5107-239">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="a5107-239">Run the following command:</span></span> 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    <span data-ttu-id="a5107-240">如果舊的相同新憑證的密碼，匯入將會成功。</span><span class="sxs-lookup"><span data-stu-id="a5107-240">If the password of the new certificate is the same as the old, the import will be successful.</span></span> <span data-ttu-id="a5107-241">如果密碼不同，您會收到錯誤，密碼錯誤，且您想要執行註冊 CcAppliance 指令程式重設密碼使用-Local 參數，，然後重複步驟 2。</span><span class="sxs-lookup"><span data-stu-id="a5107-241">If the password is different, you will receive an error that the password is wrong, and you will need to reset the password by running the Register-CcAppliance cmdlet with the -Local parameter, and then repeating step 2.</span></span> 
    
4. <span data-ttu-id="a5107-242">需要裝置所傳入退出維護模式使用 Exit CcUpdate 指令程式。</span><span class="sxs-lookup"><span data-stu-id="a5107-242">Take the appliance out of maintenance mode by using the Exit -CcUpdate cmdlet.</span></span>
    

