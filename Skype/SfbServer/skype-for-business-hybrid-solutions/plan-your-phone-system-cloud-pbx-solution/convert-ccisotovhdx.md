---
title: Convert-CcIsoToVhdx
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
ms.assetid: 216abec2-d354-4ee3-9999-0a6b350a4a5f
description: Convert CcIsoToVhdx Cmdlet 會使用客戶提供的 Windows Server 2012 R2 ISO 檔案來建立基本虛擬硬碟檔案（VHDX）。 在部署商務用 Skype 雲端連接器版本期間，會用到 VHDX 檔案。
ms.openlocfilehash: f6b16c27b82919f24b9ee0e3094fb03fffa6443b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802423"
---
# <a name="convert-ccisotovhdx"></a><span data-ttu-id="89a15-104">Convert-CcIsoToVhdx</span><span class="sxs-lookup"><span data-stu-id="89a15-104">Convert-CcIsoToVhdx</span></span>
 
<span data-ttu-id="89a15-105">Convert CcIsoToVhdx Cmdlet 會使用客戶提供的 Windows Server 2012 R2 ISO 檔案來建立基本虛擬硬碟檔案（VHDX）。</span><span class="sxs-lookup"><span data-stu-id="89a15-105">The Convert-CcIsoToVhdx cmdlet creates a base virtual hard disk file (VHDX) using a customer supplied Windows Server 2012 R2 ISO file.</span></span> <span data-ttu-id="89a15-106">在部署商務用 Skype 雲端連接器版本期間，會用到 VHDX 檔案。</span><span class="sxs-lookup"><span data-stu-id="89a15-106">The VHDX file will be used during the deployment of Skype for Business Cloud Connector Edition.</span></span>
  
```powershell
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a><span data-ttu-id="89a15-107">參數</span><span class="sxs-lookup"><span data-stu-id="89a15-107">Parameters</span></span>

|<span data-ttu-id="89a15-108">**參數**</span><span class="sxs-lookup"><span data-stu-id="89a15-108">**Parameter**</span></span>|<span data-ttu-id="89a15-109">**必要**</span><span class="sxs-lookup"><span data-stu-id="89a15-109">**Required**</span></span>|<span data-ttu-id="89a15-110">**類型**</span><span class="sxs-lookup"><span data-stu-id="89a15-110">**Type**</span></span>|<span data-ttu-id="89a15-111">**說明**</span><span class="sxs-lookup"><span data-stu-id="89a15-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="89a15-112">IsoFilePath</span><span class="sxs-lookup"><span data-stu-id="89a15-112">IsoFilePath</span></span>  <br/> | <span data-ttu-id="89a15-113">必要</span><span class="sxs-lookup"><span data-stu-id="89a15-113">Required</span></span> <br/> |<span data-ttu-id="89a15-114">System.String</span><span class="sxs-lookup"><span data-stu-id="89a15-114">System.String</span></span>  <br/> | <span data-ttu-id="89a15-115">Windows Server 2012 R2 ISO 檔案的路徑。</span><span class="sxs-lookup"><span data-stu-id="89a15-115">The path to the Windows Server 2012 R2 ISO file.</span></span> <br/> |
|<span data-ttu-id="89a15-116">GeneralizeOnly</span><span class="sxs-lookup"><span data-stu-id="89a15-116">GeneralizeOnly</span></span>  <br/> |<span data-ttu-id="89a15-117">選用</span><span class="sxs-lookup"><span data-stu-id="89a15-117">Optional</span></span>  <br/> |<span data-ttu-id="89a15-118">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="89a15-118">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="89a15-119">如果轉換過程在 Windows 更新期間失敗，您可以嘗試設定網路/proxy 並手動更新 Windows。</span><span class="sxs-lookup"><span data-stu-id="89a15-119">If the conversion process fails during Windows update, you can try to configure a network/proxy and update Windows manually.</span></span> <span data-ttu-id="89a15-120">手動工作完成後，您可以使用-GeneralizeOnly 參數執行此 Cmdlet，這會完成剩餘的作業。</span><span class="sxs-lookup"><span data-stu-id="89a15-120">After the manual work is done, you can run this cmdlet with the -GeneralizeOnly parameter and it will complete the remaining jobs.</span></span>  <br/> |
|<span data-ttu-id="89a15-121">PauseBeforeUpdate</span><span class="sxs-lookup"><span data-stu-id="89a15-121">PauseBeforeUpdate</span></span>  <br/> |<span data-ttu-id="89a15-122">選用</span><span class="sxs-lookup"><span data-stu-id="89a15-122">Optional</span></span>  <br/> |<span data-ttu-id="89a15-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="89a15-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="89a15-124">若要更新 Windows，可能需要基本 VM 上的部分手動網路/proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="89a15-124">To update Windows, some manual network/proxy configuration on the base VM might be necessary.</span></span> <span data-ttu-id="89a15-125">如果提供此參數，轉換處理常式將會在 Windows 更新之前暫停。</span><span class="sxs-lookup"><span data-stu-id="89a15-125">The conversion process will pause before Windows update if this parameter is provided.</span></span> <span data-ttu-id="89a15-126">手動設定完成後，您就可以繼續處理常式。</span><span class="sxs-lookup"><span data-stu-id="89a15-126">After the manual configuration is done, you can resume the process.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="89a15-127">範例</span><span class="sxs-lookup"><span data-stu-id="89a15-127">Examples</span></span>
<span data-ttu-id="89a15-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="89a15-128"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="89a15-129">範例 1</span><span class="sxs-lookup"><span data-stu-id="89a15-129">Example 1</span></span>

<span data-ttu-id="89a15-130">下列範例會使用位於 "C：\ Windows_Server_2012_R2-EN-US-x64" 的 Windows Server 2012 R2 ISO 檔案來準備基 VHDX 檔案：</span><span class="sxs-lookup"><span data-stu-id="89a15-130">The following example prepares the base VHDX file using a Windows Server 2012 R2 ISO file located at "C:\Windows_Server_2012_R2-EN-US-x64.ISO":</span></span> 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a><span data-ttu-id="89a15-131">範例 2</span><span class="sxs-lookup"><span data-stu-id="89a15-131">Example 2</span></span>

<span data-ttu-id="89a15-132">如果 Convert CcIsoToVhdx Cmdlet 在 Windows 更新期間失敗，可能是因為網路/proxy 配置不正確。</span><span class="sxs-lookup"><span data-stu-id="89a15-132">If the Convert-CcIsoToVhdx cmdlet fails during Windows update, it's probably because of incorrect network/proxy configuration.</span></span> <span data-ttu-id="89a15-133">您可以依照錯誤訊息中的指示進行，然後登入基礎虛擬機器來修正問題並手動更新 Windows。</span><span class="sxs-lookup"><span data-stu-id="89a15-133">You can follow the instructions in the error message and log on to the base virtual machine to fix the issue and update Windows manually.</span></span> <span data-ttu-id="89a15-134">手動工作完成後，請使用-GeneralizeOnly 參數再次執行 Cmdlet，以完成剩餘的作業：</span><span class="sxs-lookup"><span data-stu-id="89a15-134">After the manual work is done, run the cmdlet again with the -GeneralizeOnly parameter to complete the remaining jobs:</span></span> 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a><span data-ttu-id="89a15-135">範例 3</span><span class="sxs-lookup"><span data-stu-id="89a15-135">Example 3</span></span>

<span data-ttu-id="89a15-136">如果需要手動設定才能更新 Windows，您可以使用-PauseBeforeUpdate 參數。</span><span class="sxs-lookup"><span data-stu-id="89a15-136">If manual configuration is necessary to update Windows, you can use the -PauseBeforeUpdate parameter.</span></span> <span data-ttu-id="89a15-137">使用此參數時，雲端連接器會在 Windows 更新程式之前暫停。</span><span class="sxs-lookup"><span data-stu-id="89a15-137">With this parameter, Cloud Connector will pause before the Windows update process.</span></span> <span data-ttu-id="89a15-138">然後，您就可以完成手動設定並繼續進行轉換程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="89a15-138">You can then complete the manual configuration and resume the conversion process as follows:</span></span>
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="89a15-139">詳細描述</span><span class="sxs-lookup"><span data-stu-id="89a15-139">Detailed Description</span></span>
<span data-ttu-id="89a15-140"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="89a15-140"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="89a15-141">Convert CcIsoToVhdx Cmdlet 會先建立基底 VM，安裝雲端連接器所依賴的一些基本元件，然後再安裝 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="89a15-141">The Convert-CcIsoToVhdx cmdlet creates a base VM first, installs some basic components that Cloud Connector depends on, and then installs Windows updates.</span></span> <span data-ttu-id="89a15-142">最後，它會 generalizes 虛擬機器（sysprep），以取得雲端連接器裝置的虛擬機器將會使用的基 VHDX 檔案。</span><span class="sxs-lookup"><span data-stu-id="89a15-142">Finally, it generalizes the virtual machine (sysprep) to get a base VHDX file that will be used by the virtual machines of a Cloud Connector appliance.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="89a15-143">輸入類型</span><span class="sxs-lookup"><span data-stu-id="89a15-143">Input Types</span></span>
<span data-ttu-id="89a15-144"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="89a15-144"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="89a15-145">無。</span><span class="sxs-lookup"><span data-stu-id="89a15-145">None.</span></span> <span data-ttu-id="89a15-146">Convert CcIsoToVhdx Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="89a15-146">The Convert-CcIsoToVhdx cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="89a15-147">傳回類型</span><span class="sxs-lookup"><span data-stu-id="89a15-147">Return Types</span></span>
<span data-ttu-id="89a15-148"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="89a15-148"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="89a15-149">無</span><span class="sxs-lookup"><span data-stu-id="89a15-149">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="89a15-150">另請參閱</span><span class="sxs-lookup"><span data-stu-id="89a15-150">See also</span></span>
<span data-ttu-id="89a15-151"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="89a15-151"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="89a15-152">無</span><span class="sxs-lookup"><span data-stu-id="89a15-152">None</span></span>
  

