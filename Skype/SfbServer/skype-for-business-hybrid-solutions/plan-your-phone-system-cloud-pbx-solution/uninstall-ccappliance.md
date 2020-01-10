---
title: Uninstall-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: CcAppliance Cmdlet 會從主機伺服器卸載執行中的商務用 Skype 雲端連接器 Edition 裝置。
ms.openlocfilehash: f37c3092103832c9efd3b24d2efbedf00e8f54ac
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003143"
---
# <a name="uninstall-ccappliance"></a><span data-ttu-id="2d6cb-103">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="2d6cb-103">Uninstall-CcAppliance</span></span>
 
<span data-ttu-id="2d6cb-104">CcAppliance Cmdlet 會從主機伺服器卸載執行中的商務用 Skype 雲端連接器 Edition 裝置。</span><span class="sxs-lookup"><span data-stu-id="2d6cb-104">The Uninstall-CcAppliance cmdlet uninstalls the running Skype for Business Cloud Connector Edition appliance from the host server.</span></span> 
  
```powershell
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="2d6cb-105">範例</span><span class="sxs-lookup"><span data-stu-id="2d6cb-105">Examples</span></span>
<span data-ttu-id="2d6cb-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2d6cb-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="2d6cb-107">範例 1</span><span class="sxs-lookup"><span data-stu-id="2d6cb-107">Example 1</span></span>

<span data-ttu-id="2d6cb-108">下列範例會從主機伺服器中耗盡並卸載雲端連接器裝置：</span><span class="sxs-lookup"><span data-stu-id="2d6cb-108">The following example drains and uninstalls the Cloud Connector appliance from the host server:</span></span>
  
```powershell
Uninstall-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="2d6cb-109">範例 2</span><span class="sxs-lookup"><span data-stu-id="2d6cb-109">Example 2</span></span>

<span data-ttu-id="2d6cb-110">下一個範例會在主機伺服器上排出並強行卸載正在執行的雲端連接器裝置，即使排出程式失敗：</span><span class="sxs-lookup"><span data-stu-id="2d6cb-110">The next example drains and forcibly uninstalls the running Cloud Connector appliance on the host server even if the drain process failed:</span></span>
  
```powershell
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a><span data-ttu-id="2d6cb-111">範例 3</span><span class="sxs-lookup"><span data-stu-id="2d6cb-111">Example 3</span></span>

<span data-ttu-id="2d6cb-112">下一個範例會卸載雲端連接器備份版本，而不需要使用者的確認：</span><span class="sxs-lookup"><span data-stu-id="2d6cb-112">The next example uninstalls a Cloud Connector backup version without the user's confirmation:</span></span>
  
```powershell
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a><span data-ttu-id="2d6cb-113">詳細描述</span><span class="sxs-lookup"><span data-stu-id="2d6cb-113">Detailed Description</span></span>
<span data-ttu-id="2d6cb-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2d6cb-114"></span></span>

<span data-ttu-id="2d6cb-115">如果您要卸載目前正在執行的雲端連接器版本，則會先在轉送伺服器和 Edge 伺服器上執行排出服務，以讓並行呼叫在卸載虛擬機器之前完成。</span><span class="sxs-lookup"><span data-stu-id="2d6cb-115">If you are uninstalling the current running version of Cloud Connector, drain services are first run on the Mediation Server and Edge Server to let concurrent calls finish before uninstalling the virtual machines.</span></span> <span data-ttu-id="2d6cb-116">如果您要卸載備份版本，就不會執行排出。</span><span class="sxs-lookup"><span data-stu-id="2d6cb-116">If you are uninstalling a backup version, draining is not performed.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="2d6cb-117">參數</span><span class="sxs-lookup"><span data-stu-id="2d6cb-117">Parameters</span></span>
<span data-ttu-id="2d6cb-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2d6cb-118"></span></span>

|<span data-ttu-id="2d6cb-119">**參數**</span><span class="sxs-lookup"><span data-stu-id="2d6cb-119">**Parameter**</span></span>|<span data-ttu-id="2d6cb-120">**必要**</span><span class="sxs-lookup"><span data-stu-id="2d6cb-120">**Required**</span></span>|<span data-ttu-id="2d6cb-121">**類型**</span><span class="sxs-lookup"><span data-stu-id="2d6cb-121">**Type**</span></span>|<span data-ttu-id="2d6cb-122">**描述**</span><span class="sxs-lookup"><span data-stu-id="2d6cb-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="2d6cb-123">版本</span><span class="sxs-lookup"><span data-stu-id="2d6cb-123">Version</span></span> <br/> | <span data-ttu-id="2d6cb-124">選用</span><span class="sxs-lookup"><span data-stu-id="2d6cb-124">Optional</span></span> <br/> |<span data-ttu-id="2d6cb-125">System.String</span><span class="sxs-lookup"><span data-stu-id="2d6cb-125">System.String</span></span>  <br/> | <span data-ttu-id="2d6cb-126">將從主機伺服器卸載的雲端連接器版本。</span><span class="sxs-lookup"><span data-stu-id="2d6cb-126">The version of Cloud Connector that will be uninstalled from the host server.</span></span> <span data-ttu-id="2d6cb-127">如果未指定，請卸載目前的執行版本。</span><span class="sxs-lookup"><span data-stu-id="2d6cb-127">If not specified, uninstall the current running version.</span></span> <br/> |
|<span data-ttu-id="2d6cb-128">Force</span><span class="sxs-lookup"><span data-stu-id="2d6cb-128">Force</span></span>  <br/> |<span data-ttu-id="2d6cb-129">選用</span><span class="sxs-lookup"><span data-stu-id="2d6cb-129">Optional</span></span>  <br/> |<span data-ttu-id="2d6cb-130">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="2d6cb-130">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="2d6cb-131">如果要卸載目前的執行中的版本，請嘗試在卸載虛擬電腦前排出中繼伺服器與 Edge 伺服器上的伺服器。</span><span class="sxs-lookup"><span data-stu-id="2d6cb-131">If uninstalling the current running version, attempt to drain servers on Mediation Server and Edge Server before uninstalling the virtual machines.</span></span> <span data-ttu-id="2d6cb-132">如果您指定了 "Force" 開關，即使排出服務失敗，虛擬機器也將會卸載。</span><span class="sxs-lookup"><span data-stu-id="2d6cb-132">If you specify the "Force" switch, even if the drain services fail, the virtual machines will be uninstalled.</span></span> <span data-ttu-id="2d6cb-133">這個參數只是用來卸載目前的運行版本。</span><span class="sxs-lookup"><span data-stu-id="2d6cb-133">This parameter is only used to uninstall the current running version.</span></span>  <br/> |
|<span data-ttu-id="2d6cb-134">Confirm</span><span class="sxs-lookup"><span data-stu-id="2d6cb-134">Confirm</span></span>  <br/> |<span data-ttu-id="2d6cb-135">選用</span><span class="sxs-lookup"><span data-stu-id="2d6cb-135">Optional</span></span>  <br/> |<span data-ttu-id="2d6cb-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="2d6cb-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="2d6cb-137">要求使用者確認卸載虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="2d6cb-137">Ask user's confirmation to uninstall the virtual machines.</span></span> <span data-ttu-id="2d6cb-138">預設值為 TRUE。</span><span class="sxs-lookup"><span data-stu-id="2d6cb-138">Default value is TRUE.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="2d6cb-139">輸入類型</span><span class="sxs-lookup"><span data-stu-id="2d6cb-139">Input Types</span></span>
<span data-ttu-id="2d6cb-140"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2d6cb-140"></span></span>

<span data-ttu-id="2d6cb-141">無。</span><span class="sxs-lookup"><span data-stu-id="2d6cb-141">None.</span></span> <span data-ttu-id="2d6cb-142">CcAppliance Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="2d6cb-142">The Uninstall-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="2d6cb-143">傳回類型</span><span class="sxs-lookup"><span data-stu-id="2d6cb-143">Return Types</span></span>
<span data-ttu-id="2d6cb-144"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2d6cb-144"></span></span>

<span data-ttu-id="2d6cb-145">無</span><span class="sxs-lookup"><span data-stu-id="2d6cb-145">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2d6cb-146">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2d6cb-146">See also</span></span>
<span data-ttu-id="2d6cb-147"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2d6cb-147"></span></span>

[<span data-ttu-id="2d6cb-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="2d6cb-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="2d6cb-149">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="2d6cb-149">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="2d6cb-150">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="2d6cb-150">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="2d6cb-151">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="2d6cb-151">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

