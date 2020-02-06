---
title: Unregister-CcAppliance
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
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: '[登出 CcAppliance] Cmdlet 會從線上租使用者配置中的 PSTN 網站登出目前的商務用 Skype 雲端連接器 Edition 裝置。'
ms.openlocfilehash: 84a25321b6affda6b8783c40baa18a91b5b95ef5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824127"
---
# <a name="unregister-ccappliance"></a><span data-ttu-id="00145-103">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="00145-103">Unregister-CcAppliance</span></span>
 
<span data-ttu-id="00145-104">[登出 CcAppliance] Cmdlet 會從線上租使用者配置中的 PSTN 網站登出目前的商務用 Skype 雲端連接器 Edition 裝置。</span><span class="sxs-lookup"><span data-stu-id="00145-104">The Unregister-CcAppliance cmdlet unregisters the current Skype for Business Cloud Connector Edition appliance from a PSTN site in the online tenant configuration.</span></span>
  
```powershell
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="00145-105">範例</span><span class="sxs-lookup"><span data-stu-id="00145-105">Examples</span></span>
<span data-ttu-id="00145-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="00145-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="00145-107">範例 1</span><span class="sxs-lookup"><span data-stu-id="00145-107">Example 1</span></span>

<span data-ttu-id="00145-108">下列範例會從線上租使用者配置中登出目前的裝置：</span><span class="sxs-lookup"><span data-stu-id="00145-108">The following example unregisters a current appliance from the online tenant configuration:</span></span>
  
```powershell
Unregister-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="00145-109">範例 2</span><span class="sxs-lookup"><span data-stu-id="00145-109">Example 2</span></span>

<span data-ttu-id="00145-110">下一個範例會檢查在本機取消註冊的設定，而不連接至線上租使用者設定：</span><span class="sxs-lookup"><span data-stu-id="00145-110">The next example checks the configuration for unregistering locally without connecting to the online tenant configuration:</span></span>
  
```powershell
Unregister-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="00145-111">範例 3</span><span class="sxs-lookup"><span data-stu-id="00145-111">Example 3</span></span>

<span data-ttu-id="00145-112">下一個範例會將目前裝置的名稱 "Appliance1" 登出至 PSTN 網站 "Site1"：</span><span class="sxs-lookup"><span data-stu-id="00145-112">The next example unregisters the current appliance with the name "Appliance1" to PSTN site "Site1":</span></span>
  
```powershell
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="00145-113">詳細描述</span><span class="sxs-lookup"><span data-stu-id="00145-113">Detailed Description</span></span>
<span data-ttu-id="00145-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="00145-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="00145-115">與 CcAppliance Cmdlet 類似，CloudConnector .ini 檔案中與 Edge 伺服器外部 FQDN 結合的 SiteName 會被視為 PSTN 網站身分識別。</span><span class="sxs-lookup"><span data-stu-id="00145-115">Similar to the Register-CcAppliance cmdlet, SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity.</span></span> <span data-ttu-id="00145-116">同樣地，ApplianceName 結合 CloudConnector .ini 檔案中的中繼伺服器 FQDN，就會視為裝置身分識別。</span><span class="sxs-lookup"><span data-stu-id="00145-116">Likewise, ApplianceName combined with the Mediation Server FQDN in the CloudConnector.ini file is considered an appliance identity.</span></span>
  
<span data-ttu-id="00145-117">裝置取消註冊之後，請重新開機雲端連接器管理服務，並以 NetworkService 帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="00145-117">After the appliance is unregistered, restart the Cloud Connector management service and log on as the NetworkService account.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="00145-118">參數</span><span class="sxs-lookup"><span data-stu-id="00145-118">Parameters</span></span>
<span data-ttu-id="00145-119"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="00145-119"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="00145-120">**參數**</span><span class="sxs-lookup"><span data-stu-id="00145-120">**Parameter**</span></span>|<span data-ttu-id="00145-121">**必要**</span><span class="sxs-lookup"><span data-stu-id="00145-121">**Required**</span></span>|<span data-ttu-id="00145-122">**類型**</span><span class="sxs-lookup"><span data-stu-id="00145-122">**Type**</span></span>|<span data-ttu-id="00145-123">**說明**</span><span class="sxs-lookup"><span data-stu-id="00145-123">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="00145-124">名</span><span class="sxs-lookup"><span data-stu-id="00145-124">SiteName</span></span> <br/> |<span data-ttu-id="00145-125">選用</span><span class="sxs-lookup"><span data-stu-id="00145-125">Optional</span></span>  <br/> |<span data-ttu-id="00145-126">System.String</span><span class="sxs-lookup"><span data-stu-id="00145-126">System.String</span></span>  <br/> |<span data-ttu-id="00145-127">已登錄裝置的 PSTN 網站名稱。</span><span class="sxs-lookup"><span data-stu-id="00145-127">PSTN site name where the appliance is registered.</span></span> <span data-ttu-id="00145-128">CloudConnector 檔案中的 [預設值] 是 [SiteName] 值。</span><span class="sxs-lookup"><span data-stu-id="00145-128">Default value is SiteName value in CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="00145-129">ApplianceName</span><span class="sxs-lookup"><span data-stu-id="00145-129">ApplianceName</span></span>  <br/> |<span data-ttu-id="00145-130">選用</span><span class="sxs-lookup"><span data-stu-id="00145-130">Optional</span></span>  <br/> |<span data-ttu-id="00145-131">System.String</span><span class="sxs-lookup"><span data-stu-id="00145-131">System.String</span></span>  <br/> |<span data-ttu-id="00145-132">目前裝置的名稱。</span><span class="sxs-lookup"><span data-stu-id="00145-132">Name of the current appliance.</span></span> <span data-ttu-id="00145-133">[預設值] 是主機伺服器的電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="00145-133">Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="00145-134">局部</span><span class="sxs-lookup"><span data-stu-id="00145-134">Local</span></span>  <br/> |<span data-ttu-id="00145-135">選用</span><span class="sxs-lookup"><span data-stu-id="00145-135">Optional</span></span>  <br/> |<span data-ttu-id="00145-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="00145-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="00145-137">在不連線至線上租使用者設定的情況下，檢查要在本機登記的配置。</span><span class="sxs-lookup"><span data-stu-id="00145-137">Check configuration for registration locally without connecting to an online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="00145-138">輸入類型</span><span class="sxs-lookup"><span data-stu-id="00145-138">Input Types</span></span>
<span data-ttu-id="00145-139"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="00145-139"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="00145-140">無。</span><span class="sxs-lookup"><span data-stu-id="00145-140">None.</span></span> <span data-ttu-id="00145-141">[登出 CcAppliance] Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="00145-141">The Unregister-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="00145-142">傳回類型</span><span class="sxs-lookup"><span data-stu-id="00145-142">Return Types</span></span>
<span data-ttu-id="00145-143"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="00145-143"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="00145-144">無</span><span class="sxs-lookup"><span data-stu-id="00145-144">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="00145-145">另請參閱</span><span class="sxs-lookup"><span data-stu-id="00145-145">See also</span></span>
<span data-ttu-id="00145-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="00145-146"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="00145-147">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="00145-147">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="00145-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="00145-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="00145-149">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="00145-149">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="00145-150">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="00145-150">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  

