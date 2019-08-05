---
title: 取消註冊-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: '[登出 CcAppliance] Cmdlet 會從線上租使用者配置中的 PSTN 網站登出目前的商務用 Skype 雲端連接器 Edition 裝置。'
ms.openlocfilehash: fafe374371cd01b2ec7c67ade89dd2a905e16d18
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190585"
---
# <a name="unregister-ccappliance"></a><span data-ttu-id="c5bb2-103">取消註冊-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="c5bb2-103">Unregister-CcAppliance</span></span>
 
<span data-ttu-id="c5bb2-104">[登出 CcAppliance] Cmdlet 會從線上租使用者配置中的 PSTN 網站登出目前的商務用 Skype 雲端連接器 Edition 裝置。</span><span class="sxs-lookup"><span data-stu-id="c5bb2-104">The Unregister-CcAppliance cmdlet unregisters the current Skype for Business Cloud Connector Edition appliance from a PSTN site in the online tenant configuration.</span></span>
  
```
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="c5bb2-105">範例</span><span class="sxs-lookup"><span data-stu-id="c5bb2-105">Examples</span></span>
<span data-ttu-id="c5bb2-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c5bb2-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="c5bb2-107">範例 1</span><span class="sxs-lookup"><span data-stu-id="c5bb2-107">Example 1</span></span>

<span data-ttu-id="c5bb2-108">下列範例會從線上租使用者配置中登出目前的裝置:</span><span class="sxs-lookup"><span data-stu-id="c5bb2-108">The following example unregisters a current appliance from the online tenant configuration:</span></span>
  
```
Unregister-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="c5bb2-109">範例 2</span><span class="sxs-lookup"><span data-stu-id="c5bb2-109">Example 2</span></span>

<span data-ttu-id="c5bb2-110">下一個範例會檢查在本機取消註冊的設定, 而不連接至線上租使用者設定:</span><span class="sxs-lookup"><span data-stu-id="c5bb2-110">The next example checks the configuration for unregistering locally without connecting to the online tenant configuration:</span></span>
  
```
Unregister-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="c5bb2-111">範例 3</span><span class="sxs-lookup"><span data-stu-id="c5bb2-111">Example 3</span></span>

<span data-ttu-id="c5bb2-112">下一個範例會將目前裝置的名稱 "Appliance1" 登出至 PSTN 網站 "Site1":</span><span class="sxs-lookup"><span data-stu-id="c5bb2-112">The next example unregisters the current appliance with the name "Appliance1" to PSTN site "Site1":</span></span>
  
```
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="c5bb2-113">詳細描述</span><span class="sxs-lookup"><span data-stu-id="c5bb2-113">Detailed Description</span></span>
<span data-ttu-id="c5bb2-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c5bb2-114"></span></span>

<span data-ttu-id="c5bb2-115">與 CcAppliance Cmdlet 類似, CloudConnector .ini 檔案中與 Edge 伺服器外部 FQDN 結合的 SiteName 會被視為 PSTN 網站身分識別。</span><span class="sxs-lookup"><span data-stu-id="c5bb2-115">Similar to the Register-CcAppliance cmdlet, SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity.</span></span> <span data-ttu-id="c5bb2-116">同樣地, ApplianceName 結合 CloudConnector .ini 檔案中的中繼伺服器 FQDN, 就會視為裝置身分識別。</span><span class="sxs-lookup"><span data-stu-id="c5bb2-116">Likewise, ApplianceName combined with the Mediation Server FQDN in the CloudConnector.ini file is considered an appliance identity.</span></span>
  
<span data-ttu-id="c5bb2-117">裝置取消註冊之後, 請重新開機雲端連接器管理服務, 並以 NetworkService 帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="c5bb2-117">After the appliance is unregistered, restart the Cloud Connector management service and log on as the NetworkService account.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="c5bb2-118">參數</span><span class="sxs-lookup"><span data-stu-id="c5bb2-118">Parameters</span></span>
<span data-ttu-id="c5bb2-119"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c5bb2-119"></span></span>

|<span data-ttu-id="c5bb2-120">**參數**</span><span class="sxs-lookup"><span data-stu-id="c5bb2-120">**Parameter**</span></span>|<span data-ttu-id="c5bb2-121">**必要**</span><span class="sxs-lookup"><span data-stu-id="c5bb2-121">**Required**</span></span>|<span data-ttu-id="c5bb2-122">**類型**</span><span class="sxs-lookup"><span data-stu-id="c5bb2-122">**Type**</span></span>|<span data-ttu-id="c5bb2-123">**說明**</span><span class="sxs-lookup"><span data-stu-id="c5bb2-123">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="c5bb2-124">名</span><span class="sxs-lookup"><span data-stu-id="c5bb2-124">SiteName</span></span> <br/> |<span data-ttu-id="c5bb2-125">選用</span><span class="sxs-lookup"><span data-stu-id="c5bb2-125">Optional</span></span>  <br/> |<span data-ttu-id="c5bb2-126">System.String</span><span class="sxs-lookup"><span data-stu-id="c5bb2-126">System.String</span></span>  <br/> |<span data-ttu-id="c5bb2-127">已登錄裝置的 PSTN 網站名稱。</span><span class="sxs-lookup"><span data-stu-id="c5bb2-127">PSTN site name where the appliance is registered.</span></span> <span data-ttu-id="c5bb2-128">CloudConnector 檔案中的 [預設值] 是 [SiteName] 值。</span><span class="sxs-lookup"><span data-stu-id="c5bb2-128">Default value is SiteName value in CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="c5bb2-129">ApplianceName</span><span class="sxs-lookup"><span data-stu-id="c5bb2-129">ApplianceName</span></span>  <br/> |<span data-ttu-id="c5bb2-130">選用</span><span class="sxs-lookup"><span data-stu-id="c5bb2-130">Optional</span></span>  <br/> |<span data-ttu-id="c5bb2-131">System.String</span><span class="sxs-lookup"><span data-stu-id="c5bb2-131">System.String</span></span>  <br/> |<span data-ttu-id="c5bb2-132">目前裝置的名稱。</span><span class="sxs-lookup"><span data-stu-id="c5bb2-132">Name of the current appliance.</span></span> <span data-ttu-id="c5bb2-133">[預設值] 是主機伺服器的電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="c5bb2-133">Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="c5bb2-134">局部</span><span class="sxs-lookup"><span data-stu-id="c5bb2-134">Local</span></span>  <br/> |<span data-ttu-id="c5bb2-135">選用</span><span class="sxs-lookup"><span data-stu-id="c5bb2-135">Optional</span></span>  <br/> |<span data-ttu-id="c5bb2-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="c5bb2-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="c5bb2-137">在不連線至線上租使用者設定的情況下, 檢查要在本機登記的配置。</span><span class="sxs-lookup"><span data-stu-id="c5bb2-137">Check configuration for registration locally without connecting to an online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="c5bb2-138">輸入類型</span><span class="sxs-lookup"><span data-stu-id="c5bb2-138">Input Types</span></span>
<span data-ttu-id="c5bb2-139"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c5bb2-139"></span></span>

<span data-ttu-id="c5bb2-140">無。</span><span class="sxs-lookup"><span data-stu-id="c5bb2-140">None.</span></span> <span data-ttu-id="c5bb2-141">[登出 CcAppliance] Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="c5bb2-141">The Unregister-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="c5bb2-142">傳回類型</span><span class="sxs-lookup"><span data-stu-id="c5bb2-142">Return Types</span></span>
<span data-ttu-id="c5bb2-143"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c5bb2-143"></span></span>

<span data-ttu-id="c5bb2-144">無</span><span class="sxs-lookup"><span data-stu-id="c5bb2-144">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c5bb2-145">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c5bb2-145">See also</span></span>
<span data-ttu-id="c5bb2-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c5bb2-146"></span></span>

[<span data-ttu-id="c5bb2-147">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="c5bb2-147">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="c5bb2-148">安裝-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="c5bb2-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="c5bb2-149">卸載-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="c5bb2-149">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="c5bb2-150">發佈-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="c5bb2-150">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  

