---
title: Register-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: CcAppliance Cmdlet 會在線上租使用者配置中，將裝置資訊註冊到 PSTN 網站。 裝置必須先註冊，才能由商務用 Skype 雲端連接器版本管理服務來部署和管理。
ms.openlocfilehash: 93f1fe59a199214615c5ecdf8445f6c363ce6bbe
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003303"
---
# <a name="register-ccappliance"></a><span data-ttu-id="12a33-104">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="12a33-104">Register-CcAppliance</span></span>
 
<span data-ttu-id="12a33-105">CcAppliance Cmdlet 會在線上租使用者配置中，將裝置資訊註冊到 PSTN 網站。</span><span class="sxs-lookup"><span data-stu-id="12a33-105">The Register-CcAppliance cmdlet registers appliance information to a PSTN site in an online tenant configuration.</span></span> <span data-ttu-id="12a33-106">裝置必須先註冊，才能由商務用 Skype 雲端連接器版本管理服務來部署和管理。</span><span class="sxs-lookup"><span data-stu-id="12a33-106">An appliance must be registered before it can be deployed and managed by the Skype for Business Cloud Connector Edition management service.</span></span>
  
```powershell
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="12a33-107">範例</span><span class="sxs-lookup"><span data-stu-id="12a33-107">Examples</span></span>
<span data-ttu-id="12a33-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="12a33-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="12a33-109">範例 1</span><span class="sxs-lookup"><span data-stu-id="12a33-109">Example 1</span></span>

<span data-ttu-id="12a33-110">下列範例會將目前的裝置資訊註冊到線上租使用者配置：</span><span class="sxs-lookup"><span data-stu-id="12a33-110">The following example registers the current appliance information to an online tenant configuration:</span></span>
  
```powershell
Register-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="12a33-111">範例 2</span><span class="sxs-lookup"><span data-stu-id="12a33-111">Example 2</span></span>

<span data-ttu-id="12a33-112">下一個範例會檢查在本機登記的配置，而不連接至線上租使用者設定：</span><span class="sxs-lookup"><span data-stu-id="12a33-112">The next example checks configuration for registration locally without connecting to an online tenant configuration:</span></span>
  
```powershell
Register-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="12a33-113">範例 3</span><span class="sxs-lookup"><span data-stu-id="12a33-113">Example 3</span></span>

<span data-ttu-id="12a33-114">下一個範例會將名稱為 "Appliance1" 的目前裝置註冊至 PSTN 網站 "Site1"：</span><span class="sxs-lookup"><span data-stu-id="12a33-114">The next example registers the current appliance with the name "Appliance1" to the PSTN site "Site1":</span></span>
  
```powershell
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="12a33-115">詳細描述</span><span class="sxs-lookup"><span data-stu-id="12a33-115">Detailed Description</span></span>
<span data-ttu-id="12a33-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="12a33-116"></span></span>

<span data-ttu-id="12a33-117">您必須提供租使用者管理員帳戶名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="12a33-117">You must provide the tenant admin account name and password.</span></span> <span data-ttu-id="12a33-118">使用您為雲端連接器線上管理所建立的帳戶。</span><span class="sxs-lookup"><span data-stu-id="12a33-118">Use the account you have created for Cloud Connector online management.</span></span> 
  
<span data-ttu-id="12a33-119">在版本1.4.2 及更新版本中，依照指示來提供外部憑證密碼、安全模式系統管理員密碼、網域管理員密碼，以及 VM 系統管理員密碼。</span><span class="sxs-lookup"><span data-stu-id="12a33-119">In release 1.4.2 and earlier, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="12a33-120">在發行2.0 及更新版本中，依照指示提供外部憑證密碼、CceService 密碼和 CABackupFile 密碼。</span><span class="sxs-lookup"><span data-stu-id="12a33-120">In release 2.0 and later, follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="12a33-121">註冊結束時，請重新開機雲端連接器管理服務，並以 CceService 帳戶登入服務。</span><span class="sxs-lookup"><span data-stu-id="12a33-121">At the end of registration, restart the Cloud Connector management service and log on to the services as CceService account.</span></span>
  
<span data-ttu-id="12a33-122">結合了 CloudConnector 檔案中 Edge 伺服器外部 FQDN 的 SiteName，被視為 PSTN 網站身分識別。</span><span class="sxs-lookup"><span data-stu-id="12a33-122">SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity.</span></span> <span data-ttu-id="12a33-123">如果 SiteName 和 Edge 伺服器外部 FQDN 都沒有用來註冊網站，將會在線上租使用者設定中為此裝置建立新的網站。</span><span class="sxs-lookup"><span data-stu-id="12a33-123">If neither the SiteName nor the Edge Server external FQDN has been used to register a site, a new site will be created for this appliance in an online tenant configuration.</span></span> <span data-ttu-id="12a33-124">如果找到 PSTN 網站身分識別，PSTN 網站就會使用這個身分識別，裝置就會登錄到這個 PSTN 網站。</span><span class="sxs-lookup"><span data-stu-id="12a33-124">If a PSTN site identity is found, a PSTN site will use this identity and the appliance will be registered to this PSTN site.</span></span> 
  
<span data-ttu-id="12a33-125">在下列情況下，Cmdlet 會失敗並指出已註冊 Site1：</span><span class="sxs-lookup"><span data-stu-id="12a33-125">In the following situation, the cmdlet will fail and indicate that Site1 is already registered:</span></span> 
  
- <span data-ttu-id="12a33-126">SiteName 是 Site1，而 Edge 伺服器外部 FQDN 則是 edgserver1.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="12a33-126">SiteName is Site1 and the Edge Server external FQDN is edgserver1.contoso.com.</span></span> 
    
- <span data-ttu-id="12a33-127">其 SiteName 為 Site1 且 Edge 伺服器外部 FQDN 為 edgserver.contoso.com 的 PSTN 網站。</span><span class="sxs-lookup"><span data-stu-id="12a33-127">A PSTN site whose SiteName is Site1 and Edge Server external FQDN is edgserver.contoso.com.</span></span>
    
- <span data-ttu-id="12a33-128">其 SiteName 為 NewSite 的 PSTN 網站，以及 Edge 伺服器外部 FQDN 已註冊 edgserver1.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="12a33-128">A PSTN site whose SiteName is NewSite and Edge Server external FQDN is edgserver1.contoso.com has been registered.</span></span> 
    
<span data-ttu-id="12a33-129">ApplianceName 結合 CloudConnector .ini 檔案中的中繼伺服器 FQDN，就被視為裝置身分識別。</span><span class="sxs-lookup"><span data-stu-id="12a33-129">ApplianceName combined with the Mediation Server FQDN in CloudConnector.ini file is considered an Appliance Identity.</span></span> <span data-ttu-id="12a33-130">如果 ApplianceName 和轉送伺服器 FQDN 都沒有用來註冊裝置，則會在線上租使用者設定中建立新的裝置。</span><span class="sxs-lookup"><span data-stu-id="12a33-130">If neither the ApplianceName nor the Mediation Server FQDN has been used to register an appliance, a new appliance will be created in the online tenant configuration.</span></span> <span data-ttu-id="12a33-131">如果裝置已註冊，Cmdlet 將會失敗。</span><span class="sxs-lookup"><span data-stu-id="12a33-131">If the appliance is already registered, the cmdlet will fail.</span></span>
  
<span data-ttu-id="12a33-132">在下列情況下，Cmdlet 將會失敗，並指出裝置已註冊：</span><span class="sxs-lookup"><span data-stu-id="12a33-132">In the following situation, the cmdlet will fail and indicate that the appliance is already registered:</span></span> 
  
- <span data-ttu-id="12a33-133">ApplianceName 是 Appliance1，而轉送伺服器 FQDN 是 ms1.vdomain.com。</span><span class="sxs-lookup"><span data-stu-id="12a33-133">ApplianceName is Appliance1 and Mediation server FQDN is ms1.vdomain.com.</span></span>
    
- <span data-ttu-id="12a33-134">在目前的 PSTN 網站中，如果裝置的名稱 Appliance1 和轉送伺服器 FQDN 是 ms.vdomain.com，或其名稱 NewAppliance 和轉送伺服器 FQDN 已登錄 ms1.vdomain.com 的裝置。</span><span class="sxs-lookup"><span data-stu-id="12a33-134">In the current PSTN site, if an appliance whose name Appliance1 and Mediation Server FQDN is ms.vdomain.com or an appliance whose name NewAppliance and Mediation server FQDN is ms1.vdomain.com has been registered.</span></span>
    
## <a name="parameters"></a><span data-ttu-id="12a33-135">參數</span><span class="sxs-lookup"><span data-stu-id="12a33-135">Parameters</span></span>
<span data-ttu-id="12a33-136"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="12a33-136"></span></span>

|<span data-ttu-id="12a33-137">**參數**</span><span class="sxs-lookup"><span data-stu-id="12a33-137">**Parameter**</span></span>|<span data-ttu-id="12a33-138">**必要**</span><span class="sxs-lookup"><span data-stu-id="12a33-138">**Required**</span></span>|<span data-ttu-id="12a33-139">**類型**</span><span class="sxs-lookup"><span data-stu-id="12a33-139">**Type**</span></span>|<span data-ttu-id="12a33-140">**描述**</span><span class="sxs-lookup"><span data-stu-id="12a33-140">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="12a33-141">名</span><span class="sxs-lookup"><span data-stu-id="12a33-141">SiteName</span></span>  <br/> |<span data-ttu-id="12a33-142">選用</span><span class="sxs-lookup"><span data-stu-id="12a33-142">Optional</span></span>  <br/> |<span data-ttu-id="12a33-143">System.String</span><span class="sxs-lookup"><span data-stu-id="12a33-143">System.String</span></span>  <br/> |<span data-ttu-id="12a33-144">已登錄裝置的 PSTN 網站名稱。</span><span class="sxs-lookup"><span data-stu-id="12a33-144">PSTN site name to which the appliance is registered.</span></span> <span data-ttu-id="12a33-145">CloudConnector 檔案中的 [預設值] 是 [SiteName] 值。</span><span class="sxs-lookup"><span data-stu-id="12a33-145">Default value is SiteName value in the CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="12a33-146">ApplianceName</span><span class="sxs-lookup"><span data-stu-id="12a33-146">ApplianceName</span></span>  <br/> |<span data-ttu-id="12a33-147">選用</span><span class="sxs-lookup"><span data-stu-id="12a33-147">Optional</span></span>  <br/> |<span data-ttu-id="12a33-148">System.String</span><span class="sxs-lookup"><span data-stu-id="12a33-148">System.String</span></span>  <br/> |<span data-ttu-id="12a33-149">目前裝置的名稱。</span><span class="sxs-lookup"><span data-stu-id="12a33-149">Name of the current appliance.</span></span> <span data-ttu-id="12a33-150">[預設值] 是主機伺服器的電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="12a33-150">Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="12a33-151">局部</span><span class="sxs-lookup"><span data-stu-id="12a33-151">Local</span></span>  <br/> |<span data-ttu-id="12a33-152">選用</span><span class="sxs-lookup"><span data-stu-id="12a33-152">Optional</span></span>  <br/> |<span data-ttu-id="12a33-153">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="12a33-153">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="12a33-154">在不連線至線上租使用者設定的情況下，檢查要在本機登記的設定。</span><span class="sxs-lookup"><span data-stu-id="12a33-154">Check configurations for registration locally without connecting to online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="12a33-155">輸入類型</span><span class="sxs-lookup"><span data-stu-id="12a33-155">Input Types</span></span>
<span data-ttu-id="12a33-156"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="12a33-156"></span></span>

<span data-ttu-id="12a33-157">無。</span><span class="sxs-lookup"><span data-stu-id="12a33-157">None.</span></span> <span data-ttu-id="12a33-158">CcAppliance Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="12a33-158">The Register-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="12a33-159">傳回類型</span><span class="sxs-lookup"><span data-stu-id="12a33-159">Return Types</span></span>
<span data-ttu-id="12a33-160"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="12a33-160"></span></span>

<span data-ttu-id="12a33-161">無</span><span class="sxs-lookup"><span data-stu-id="12a33-161">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="12a33-162">另請參閱</span><span class="sxs-lookup"><span data-stu-id="12a33-162">See also</span></span>
<span data-ttu-id="12a33-163"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="12a33-163"></span></span>

[<span data-ttu-id="12a33-164">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="12a33-164">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="12a33-165">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="12a33-165">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="12a33-166">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="12a33-166">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="12a33-167">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="12a33-167">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

