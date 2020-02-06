---
title: Install-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: CcAppliance Cmdlet 會安裝商務用 Skype 雲端連接器 Edition 裝置，包括主機伺服器上的 AD、中央管理商店、中繼伺服器及 Edge 伺服器虛擬機器。
ms.openlocfilehash: fe1fab785e2681614f27035714b6ddead22b8707
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799873"
---
# <a name="install-ccappliance"></a><span data-ttu-id="5e3bc-103">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="5e3bc-103">Install-CcAppliance</span></span>
 
<span data-ttu-id="5e3bc-104">CcAppliance Cmdlet 會安裝商務用 Skype 雲端連接器 Edition 裝置，包括主機伺服器上的 AD、中央管理商店、中繼伺服器及 Edge 伺服器虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="5e3bc-104">The Install-CcAppliance cmdlet installs the Skype for Business Cloud Connector Edition appliance—including the AD, Central Management Store, Mediation Server, and Edge Server virtual machines—on the host server.</span></span> 
  
```powershell
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="5e3bc-105">範例</span><span class="sxs-lookup"><span data-stu-id="5e3bc-105">Examples</span></span>
<span data-ttu-id="5e3bc-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5e3bc-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="5e3bc-107">範例 1</span><span class="sxs-lookup"><span data-stu-id="5e3bc-107">Example 1</span></span>

<span data-ttu-id="5e3bc-108">下列範例會在主機伺服器上安裝新的雲端連接器裝置：</span><span class="sxs-lookup"><span data-stu-id="5e3bc-108">The following example installs a new Cloud Connector appliance on the host server:</span></span>
  
```powershell
Install-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="5e3bc-109">範例 2</span><span class="sxs-lookup"><span data-stu-id="5e3bc-109">Example 2</span></span>

<span data-ttu-id="5e3bc-110">下列範例會將雲端連接器升級至最新版本：</span><span class="sxs-lookup"><span data-stu-id="5e3bc-110">The following example upgrades Cloud Connector to the latest version:</span></span>
  
```powershell
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a><span data-ttu-id="5e3bc-111">範例 3</span><span class="sxs-lookup"><span data-stu-id="5e3bc-111">Example 3</span></span>

<span data-ttu-id="5e3bc-112">下列範例會移除主機伺服器上快取的所有雲端連接器認證，提示使用者再次指定所有認證資訊，然後再安裝雲端連接器：</span><span class="sxs-lookup"><span data-stu-id="5e3bc-112">The following example removes all Cloud Connector credentials cached on the host server, prompts the user to specify all credential information again, and then installs Cloud Connector:</span></span>
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a><span data-ttu-id="5e3bc-113">範例 4</span><span class="sxs-lookup"><span data-stu-id="5e3bc-113">Example 4</span></span>

<span data-ttu-id="5e3bc-114">下列範例顯示 PowerShell 主控台中的所有部署步驟：</span><span class="sxs-lookup"><span data-stu-id="5e3bc-114">The following example displays all deployment steps in the PowerShell console:</span></span>
  
```powershell
Install-CcAppliance -ShowStepsOnly
```

<span data-ttu-id="5e3bc-115">-ShowStepsOnly 參數僅供進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="5e3bc-115">The -ShowStepsOnly parameter is for troubleshooting only.</span></span>
  
### <a name="example-5"></a><span data-ttu-id="5e3bc-116">範例 5</span><span class="sxs-lookup"><span data-stu-id="5e3bc-116">Example 5</span></span>

<span data-ttu-id="5e3bc-117">下列範例會針對主機伺服器上的每個部署步驟產生設定檔。</span><span class="sxs-lookup"><span data-stu-id="5e3bc-117">The following example generates configuration files for each deployment step on the host server.</span></span> <span data-ttu-id="5e3bc-118">設定檔會儲存到主機\<伺服器\>上\\的 ApplianceRoot\>\Instances<版本 default\ExportedConfig 資料夾中：</span><span class="sxs-lookup"><span data-stu-id="5e3bc-118">Configuration files are saved to the \<ApplianceRoot\>\Instances\\<Version\>-default\ExportedConfig folder on the host server:</span></span>
  
```powershell
Install-CcAppliance -PrepareOnly
```

<span data-ttu-id="5e3bc-119">若要判斷裝置根目錄，請執行 CcApplianceDirectory Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5e3bc-119">To determine the appliance root, run the Get-CcApplianceDirectory cmdlet.</span></span> 
  
### <a name="example-6"></a><span data-ttu-id="5e3bc-120">範例6</span><span class="sxs-lookup"><span data-stu-id="5e3bc-120">Example 6</span></span>

<span data-ttu-id="5e3bc-121">在下列範例中，雲端連接器會執行部署步驟1、2和3，以建立虛擬交換器、建立 AD 虛擬機器，並在 AD server 上安裝網域服務。</span><span class="sxs-lookup"><span data-stu-id="5e3bc-121">In the following example, Cloud Connector runs deployment steps 1, 2, and 3 to create virtual switches, create an AD virtual machine, and install the domain service on the AD server.</span></span> <span data-ttu-id="5e3bc-122">如果步驟已執行，它會跳過步驟：</span><span class="sxs-lookup"><span data-stu-id="5e3bc-122">It skips the step if the step has already been executed:</span></span>
  
```powershell
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

<span data-ttu-id="5e3bc-123">SkipExistingObjects 參數必須與步驟參數搭配使用。</span><span class="sxs-lookup"><span data-stu-id="5e3bc-123">The SkipExistingObjects parameter must be used in conjunction with the Steps parameter.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5e3bc-124">步驟參數僅供疑難排解之用。</span><span class="sxs-lookup"><span data-stu-id="5e3bc-124">The Steps parameter is for troubleshooting purposes only.</span></span> <span data-ttu-id="5e3bc-125">請勿使用此參數來部署裝置，或升級處於服務中的裝置。</span><span class="sxs-lookup"><span data-stu-id="5e3bc-125">Do not use this parameter to deploy an appliance or to upgrade an appliance that is in service.</span></span> 
  
<span data-ttu-id="5e3bc-126">若要判斷部署的步驟，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="5e3bc-126">To determine the steps of the deployment, run the following command:</span></span>
  
<span data-ttu-id="5e3bc-127">安裝-CcAppliance-ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="5e3bc-127">Install-CcAppliance -ShowStepsOnly</span></span>
  
## <a name="detailed-description"></a><span data-ttu-id="5e3bc-128">詳細描述</span><span class="sxs-lookup"><span data-stu-id="5e3bc-128">Detailed Description</span></span>
<span data-ttu-id="5e3bc-129"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="5e3bc-129"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="5e3bc-130">CcAppliance Cmdlet 是用來將雲端連接器部署到新裝置，或將現有裝置升級至最新版本。</span><span class="sxs-lookup"><span data-stu-id="5e3bc-130">The Install-CcAppliance cmdlet is used to deploy Cloud Connector to a new appliance or to upgrade an existing appliance to the latest version.</span></span>
  
<span data-ttu-id="5e3bc-131">如果您有新的裝置，請務必先閱讀 [為雲端連接器準備您的環境]，然後執行 CcAppliance Cmdlet 來註冊裝置，然後執行安裝 CcAppliance Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5e3bc-131">If you have a new appliance, be sure to read Prepare your environment for Cloud Connector first, run the Register-CcAppliance cmdlet to register the appliance, and then run the Install-CcAppliance cmdlet.</span></span> <span data-ttu-id="5e3bc-132">如需詳細資訊，請參閱[在雲端連接器中部署單一網站](deploy-a-single-site-in-cloud-connector.md)，並[在雲端連接器中部署多個網站](deploy-multiple-sites-in-cloud-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="5e3bc-132">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
<span data-ttu-id="5e3bc-133">如果您已部署雲端連接器，且想要升級，請依照[升級至新版雲端連接器](upgrade-to-a-new-version-of-cloud-connector.md)中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="5e3bc-133">If you have an existing deployment of Cloud Connector and you want to upgrade, please follow the instructions in [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>
  
## <a name="parameters"></a><span data-ttu-id="5e3bc-134">參數</span><span class="sxs-lookup"><span data-stu-id="5e3bc-134">Parameters</span></span>
<span data-ttu-id="5e3bc-135"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="5e3bc-135"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="5e3bc-136">**參數**</span><span class="sxs-lookup"><span data-stu-id="5e3bc-136">**Parameter**</span></span>|<span data-ttu-id="5e3bc-137">**必要**</span><span class="sxs-lookup"><span data-stu-id="5e3bc-137">**Required**</span></span>|<span data-ttu-id="5e3bc-138">**類型**</span><span class="sxs-lookup"><span data-stu-id="5e3bc-138">**Type**</span></span>|<span data-ttu-id="5e3bc-139">**說明**</span><span class="sxs-lookup"><span data-stu-id="5e3bc-139">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5e3bc-140">PrepareOnly</span><span class="sxs-lookup"><span data-stu-id="5e3bc-140">PrepareOnly</span></span>  <br/> |<span data-ttu-id="5e3bc-141">選用</span><span class="sxs-lookup"><span data-stu-id="5e3bc-141">Optional</span></span>  <br/> |<span data-ttu-id="5e3bc-142">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="5e3bc-142">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="5e3bc-143">針對每個部署步驟產生設定檔。</span><span class="sxs-lookup"><span data-stu-id="5e3bc-143">Generate configuration files for each deployment step.</span></span> <span data-ttu-id="5e3bc-144">此參數僅供疑難排解。</span><span class="sxs-lookup"><span data-stu-id="5e3bc-144">This parameter is for troubleshooting only.</span></span> <br/> |
|<span data-ttu-id="5e3bc-145">ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="5e3bc-145">ShowStepsOnly</span></span>  <br/> |<span data-ttu-id="5e3bc-146">選用</span><span class="sxs-lookup"><span data-stu-id="5e3bc-146">Optional</span></span>  <br/> |<span data-ttu-id="5e3bc-147">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="5e3bc-147">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="5e3bc-148">只顯示部署步驟名稱。</span><span class="sxs-lookup"><span data-stu-id="5e3bc-148">Display deployment step names only.</span></span> <span data-ttu-id="5e3bc-149">此參數僅供疑難排解。</span><span class="sxs-lookup"><span data-stu-id="5e3bc-149">This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="5e3bc-150">SkipExistingObjects</span><span class="sxs-lookup"><span data-stu-id="5e3bc-150">SkipExistingObjects</span></span>  <br/> |<span data-ttu-id="5e3bc-151">選用</span><span class="sxs-lookup"><span data-stu-id="5e3bc-151">Optional</span></span>  <br/> |<span data-ttu-id="5e3bc-152">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="5e3bc-152">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="5e3bc-153">這個參數必須與步驟參數搭配使用。</span><span class="sxs-lookup"><span data-stu-id="5e3bc-153">This parameter must be used in conjunction with the Steps parameter.</span></span> <span data-ttu-id="5e3bc-154">此參數僅供疑難排解。</span><span class="sxs-lookup"><span data-stu-id="5e3bc-154">This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="5e3bc-155">步驟</span><span class="sxs-lookup"><span data-stu-id="5e3bc-155">Steps</span></span>  <br/> |<span data-ttu-id="5e3bc-156">選用</span><span class="sxs-lookup"><span data-stu-id="5e3bc-156">Optional</span></span>  <br/> |<span data-ttu-id="5e3bc-157">System.object</span><span class="sxs-lookup"><span data-stu-id="5e3bc-157">System.Array</span></span>  <br/> |<span data-ttu-id="5e3bc-158">執行部署步驟。</span><span class="sxs-lookup"><span data-stu-id="5e3bc-158">Run the deployment steps.</span></span> <span data-ttu-id="5e3bc-159">此參數僅供疑難排解。</span><span class="sxs-lookup"><span data-stu-id="5e3bc-159">This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="5e3bc-160">升級</span><span class="sxs-lookup"><span data-stu-id="5e3bc-160">Upgrade</span></span>  <br/> |<span data-ttu-id="5e3bc-161">選用</span><span class="sxs-lookup"><span data-stu-id="5e3bc-161">Optional</span></span>  <br/> |<span data-ttu-id="5e3bc-162">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="5e3bc-162">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="5e3bc-163">將現有的雲端連接器升級至最新版本。</span><span class="sxs-lookup"><span data-stu-id="5e3bc-163">Upgrade existing Cloud Connector to the latest version.</span></span>  <br/> |
|<span data-ttu-id="5e3bc-164">UpdateAllCredentials</span><span class="sxs-lookup"><span data-stu-id="5e3bc-164">UpdateAllCredentials</span></span>  <br/> |<span data-ttu-id="5e3bc-165">選用</span><span class="sxs-lookup"><span data-stu-id="5e3bc-165">Optional</span></span>  <br/> |<span data-ttu-id="5e3bc-166">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="5e3bc-166">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="5e3bc-167">在快取中移除所有雲端連接器認證。</span><span class="sxs-lookup"><span data-stu-id="5e3bc-167">Remove all Cloud Connector credentials in the cache.</span></span> <span data-ttu-id="5e3bc-168">提示使用者指定新的安裝認證資訊。</span><span class="sxs-lookup"><span data-stu-id="5e3bc-168">Prompt the user to specify new credential information for the installation.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="5e3bc-169">輸入類型</span><span class="sxs-lookup"><span data-stu-id="5e3bc-169">Input Types</span></span>
<span data-ttu-id="5e3bc-170"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5e3bc-170"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="5e3bc-171">無。</span><span class="sxs-lookup"><span data-stu-id="5e3bc-171">None.</span></span> <span data-ttu-id="5e3bc-172">CcAppliance Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="5e3bc-172">The Install-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="5e3bc-173">傳回類型</span><span class="sxs-lookup"><span data-stu-id="5e3bc-173">Return Types</span></span>
<span data-ttu-id="5e3bc-174"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5e3bc-174"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="5e3bc-175">無</span><span class="sxs-lookup"><span data-stu-id="5e3bc-175">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5e3bc-176">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5e3bc-176">See also</span></span>
<span data-ttu-id="5e3bc-177"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5e3bc-177"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="5e3bc-178">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="5e3bc-178">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="5e3bc-179">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="5e3bc-179">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="5e3bc-180">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="5e3bc-180">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="5e3bc-181">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="5e3bc-181">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

