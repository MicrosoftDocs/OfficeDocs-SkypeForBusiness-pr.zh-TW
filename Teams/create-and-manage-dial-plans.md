---
title: 建立及管理撥號方案
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 7af17c94-5f8f-4452-ae1d-01f495b4dc94
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: '瞭解如何在 Office 365 中建立呼叫撥號方案（PSTN 呼叫撥號方案），以及如何管理它們。 '
ms.openlocfilehash: 3b96c2f504096b3f77c7080feda1dac982f46e9c
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516669"
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="d5d70-103">建立及管理撥號方案</span><span class="sxs-lookup"><span data-stu-id="d5d70-103">Create and manage dial plans</span></span>

<span data-ttu-id="d5d70-104">在您規劃好組織的撥號方案並查明需要為呼叫路由建立的所有正常化規則之後，您必須使用 Windows PowerShell 來建立撥號方案並變更任何設定。</span><span class="sxs-lookup"><span data-stu-id="d5d70-104">After you have planned the dial plans for your organization and figured out all of the normalization rules that need to be created for call routing, you will need to use Windows PowerShell to create the dial plans and make any setting changes.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d5d70-105">商務用 Skype 系統管理中心無法用來建立和管理撥號方案。</span><span class="sxs-lookup"><span data-stu-id="d5d70-105">The Skype for Business admin center can't be used for creating and managing dial plans.</span></span> 
  
## <a name="verifying-and-starting-remote-powershell"></a><span data-ttu-id="d5d70-106">驗證及啟動遠端 PowerShell</span><span class="sxs-lookup"><span data-stu-id="d5d70-106">Verifying and starting Remote PowerShell</span></span>

 <span data-ttu-id="d5d70-107">**檢查您執行的是 Windows PowerShell 版本3.0 或更高版本**</span><span class="sxs-lookup"><span data-stu-id="d5d70-107">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="d5d70-108">若要確認您執行的是版本3.0 或更高版本： [**開始] 功能表** > **Windows PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="d5d70-108">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="d5d70-109">在**Windows PowerShell**視窗中輸入 [_取得主機_]，以檢查版本。</span><span class="sxs-lookup"><span data-stu-id="d5d70-109">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="d5d70-110">如果您沒有版本3.0 或更高版本，您需要下載並安裝 Windows PowerShell 更新。</span><span class="sxs-lookup"><span data-stu-id="d5d70-110">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="d5d70-111">請參閱[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) ，以下載並更新 Windows PowerShell 至版本4.0。</span><span class="sxs-lookup"><span data-stu-id="d5d70-111">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="d5d70-112">出現提示時，請重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="d5d70-112">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="d5d70-113">您也需要安裝適用于商務用 Skype Online 的 Windows PowerShell 模組，這可讓您建立連線到商務用 Skype Online 的遠端 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="d5d70-113">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="d5d70-114">此模組只受64位電腦支援，可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。</span><span class="sxs-lookup"><span data-stu-id="d5d70-114">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="d5d70-115">如果出現提示，請重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="d5d70-115">Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="d5d70-116">如果您需要進一步瞭解，請參閱[在單一 Windows PowerShell 視窗中連線至所有 Office 365 服務](https://technet.microsoft.com/EN-US/library/dn568015.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d5d70-116">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
  
 <span data-ttu-id="d5d70-117">**啟動 Windows PowerShell 會話**</span><span class="sxs-lookup"><span data-stu-id="d5d70-117">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="d5d70-118">從 [**開始] 功能表** > 中的 [**Windows PowerShell**]。</span><span class="sxs-lookup"><span data-stu-id="d5d70-118">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="d5d70-119">在**Windows PowerShell**視窗中，執行下列動作以連線到您的 Office 365 組織：</span><span class="sxs-lookup"><span data-stu-id="d5d70-119">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d5d70-120">您在第一次使用商務用 Skype Online Windows PowerShell 模組時，您只需執行匯**入模組**命令。</span><span class="sxs-lookup"><span data-stu-id="d5d70-120">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
> 
>   ```
>     Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
>     $credential = Get-Credential
>     $session = New-CsOnlineSession -Credential $credential
>     Import-PSSession $session
>   ```

<span data-ttu-id="d5d70-121">如果您需要啟動 Windows PowerShell 的詳細資訊，請參閱[在單一 Windows powershell 視窗中連線至所有 Office 365 服務](https://technet.microsoft.com/EN-US/library/dn568015.aspx)，或[使用 Windows PowerShell 連線到商務用 Skype Online](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d5d70-121">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
## <a name="creating-and-managing-your-dial-plans"></a><span data-ttu-id="d5d70-122">建立及管理您的撥號方案</span><span class="sxs-lookup"><span data-stu-id="d5d70-122">Creating and managing your dial plans</span></span>

<span data-ttu-id="d5d70-123">您可以使用單一 Cmdlet 或 PowerShell 腳本來建立及管理租使用者撥號方案。</span><span class="sxs-lookup"><span data-stu-id="d5d70-123">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
### <a name="using-single-cmdlets"></a><span data-ttu-id="d5d70-124">使用單一 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="d5d70-124">Using single cmdlets</span></span>

- <span data-ttu-id="d5d70-125">若要建立新的撥號方案，請執行：</span><span class="sxs-lookup"><span data-stu-id="d5d70-125">To create a new dial plan, run:</span></span>
    
  ```
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="d5d70-126">如需其他範例和參數，請參閱[新 CsTenantDialPlan](https://technet.microsoft.com/library/mt775026.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d5d70-126">For other examples and parameters, see [New-CsTenantDialPlan](https://technet.microsoft.com/library/mt775026.aspx).</span></span>
    
- <span data-ttu-id="d5d70-127">若要對現有的撥號方案進行設定變更，請執行：</span><span class="sxs-lookup"><span data-stu-id="d5d70-127">To make setting changes to an existing dial plan, run:</span></span>
    
  ```
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="d5d70-128">如需其他範例和參數，請參閱[設定 CsTenantDialPlan](https://technet.microsoft.com/library/mt775023.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d5d70-128">For other examples and parameters, see [Set-CsTenantDialPlan](https://technet.microsoft.com/library/mt775023.aspx).</span></span>
    
- <span data-ttu-id="d5d70-129">若要將使用者新增至撥號方案，請執行：</span><span class="sxs-lookup"><span data-stu-id="d5d70-129">To add users to a dial plan, run:</span></span>
    
  ```
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="d5d70-130">如需其他範例和參數，請參閱[授與 CsTenantDialPlan](https://technet.microsoft.com/library/mt775021.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d5d70-130">For other examples and parameters, see [Grant-CsTenantDialPlan](https://technet.microsoft.com/library/mt775021.aspx).</span></span>
    
- <span data-ttu-id="d5d70-131">若要查看撥號計畫的設定，請執行：</span><span class="sxs-lookup"><span data-stu-id="d5d70-131">To view the settings on a dial plan, run:</span></span>
    
  ```
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="d5d70-132">如需其他範例和參數，請參閱[CsTenantDialPlan](https://technet.microsoft.com/library/mt775024.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d5d70-132">For other examples and parameters, see [Get-CsTenantDialPlan](https://technet.microsoft.com/library/mt775024.aspx).</span></span>
    
- <span data-ttu-id="d5d70-133">若要刪除撥號方案，請執行：</span><span class="sxs-lookup"><span data-stu-id="d5d70-133">To delete a dial plan, run:</span></span>
    
  ```
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="d5d70-134">如需其他範例和參數，請參閱[移除-CsTenantDialPlan](https://technet.microsoft.com/library/mt775020.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d5d70-134">For other examples and parameters, see [Remove-CsTenantDialPlan](https://technet.microsoft.com/library/mt775020.aspx).</span></span>
    
- <span data-ttu-id="d5d70-135">若要查看有效撥號方案的設定，請執行：</span><span class="sxs-lookup"><span data-stu-id="d5d70-135">To see the settings of the effective dial plan, run:</span></span>
    
  ```
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="d5d70-136">如需其他範例和參數，請參閱[CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775022.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d5d70-136">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775022.aspx).</span></span>
    
- <span data-ttu-id="d5d70-137">若要測試撥號方案的有效設定，請執行：</span><span class="sxs-lookup"><span data-stu-id="d5d70-137">To test the effective settings of a dial plan, run:</span></span>
    
  ```
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="d5d70-138">如需其他範例和參數，請參閱[測試 CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775025.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d5d70-138">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775025.aspx).</span></span>
    
### <a name="using-a-powershell-script"></a><span data-ttu-id="d5d70-139">使用 PowerShell 腳本</span><span class="sxs-lookup"><span data-stu-id="d5d70-139">Using a PowerShell script</span></span>

<span data-ttu-id="d5d70-140">執行此動作以刪除與租使用者撥號方案相關聯的正常化規則，而不需要先刪除租使用者撥號方案：</span><span class="sxs-lookup"><span data-stu-id="d5d70-140">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to deleting the tenant dial plan first:</span></span>
```
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="d5d70-141">執行此動作，將下列正常化規則新增至現有的租使用者撥號方案（名為 RedmondDialPlan）。</span><span class="sxs-lookup"><span data-stu-id="d5d70-141">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="d5d70-142">執行此操作，從現有的租使用者撥號方案（名為 RedmondDialPlan）移除下列正常化規則。</span><span class="sxs-lookup"><span data-stu-id="d5d70-142">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity DP1 -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="d5d70-143">當您想要檢查現有的正常化規則時，請執行下列動作，判斷您想要刪除的規則，然後使用其索引將它移除。</span><span class="sxs-lookup"><span data-stu-id="d5d70-143">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it.</span></span> <span data-ttu-id="d5d70-144">正常化規則陣列從索引0開始。</span><span class="sxs-lookup"><span data-stu-id="d5d70-144">The array of normalization rules starts with index 0.</span></span> <span data-ttu-id="d5d70-145">我們想要移除3位數的正常化規則，以便編制索引1。</span><span class="sxs-lookup"><span data-stu-id="d5d70-145">We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
```
Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules
Description         : 4-digit
Pattern             : ^(\\d{4})$
Translation         : +1426666$1
Name                : NR2
IsInternalExtension : False

Description         : 3-digit
Pattern             : ^(\\d{3})$
Translation         : +14255551$1
Name                : NR12
IsInternalExtension : False

$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[Number 1]
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="d5d70-146">執行此工作以找出已授與 RedmondDialPlan 租使用者撥號計畫的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="d5d70-146">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```
Get-CsOnlineuser | where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="d5d70-147">執行此程式以刪除擁有 HostingProvider sipfed.online.lync.com 之所有使用者的 policyname。</span><span class="sxs-lookup"><span data-stu-id="d5d70-147">Run this to delete policyname for all users who have HostingProvider sipfed.online.lync.com.</span></span>
```
Get-CsOnlineUser -Filter {HostingProvider -eq “sipfed.online.lync.com”} | Grant-CsTenantDialPlan -policyname $null
```

<span data-ttu-id="d5d70-148">執行這些程式，將名為 OPDP1 的現有內部部署撥號方案新增為貴組織的租使用者撥號計畫。</span><span class="sxs-lookup"><span data-stu-id="d5d70-148">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization.</span></span> <span data-ttu-id="d5d70-149">您必須先將內部部署撥號計畫儲存為 .xml 檔案，然後再用來建立新的租使用者撥號方案。</span><span class="sxs-lookup"><span data-stu-id="d5d70-149">You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="d5d70-150">執行此工作以將內部部署撥號計畫儲存到 .xml 檔案。</span><span class="sxs-lookup"><span data-stu-id="d5d70-150">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="d5d70-151">執行此工作來建立新的租使用者撥號方案。</span><span class="sxs-lookup"><span data-stu-id="d5d70-151">Run this to create the new tenant dial plan.</span></span>
  
```
$DPFileName = "dialplan.xml"
$DP = Import-Clixml $DPFileName
$NormRules = @()
ForEach($nr in $dp.NormalizationRules)
{
 $id1 = "Global/" +$nr.Name
$nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation  -IsInternalExtension $nr.IsInternalExtension -InMemory
$NormRules += $nr2
}
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="d5d70-152">想要深入瞭解 Windows Powershell 嗎？</span><span class="sxs-lookup"><span data-stu-id="d5d70-152">Want to know more about Windows Powershell?</span></span>

- <span data-ttu-id="d5d70-153">Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="d5d70-153">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="d5d70-154">在 Windows PowerShell 中，您可以使用單一管理點管理 Office 365 和商務用 Skype Online，當您有多個工作需要執行時，可簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="d5d70-154">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="d5d70-155">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="d5d70-155">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d5d70-156">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="d5d70-156">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="d5d70-157">為什麼需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="d5d70-157">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="d5d70-158">Windows PowerShell 在速度、簡潔性和生產率上都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者設定變更時。</span><span class="sxs-lookup"><span data-stu-id="d5d70-158">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="d5d70-159">請參閱下列主題，瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="d5d70-159">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="d5d70-160">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="d5d70-160">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="d5d70-161">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="d5d70-161">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="d5d70-162">使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="d5d70-162">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="d5d70-163">相關主題</span><span class="sxs-lookup"><span data-stu-id="d5d70-163">Related topics</span></span>
[<span data-ttu-id="d5d70-164">傳送電話號碼常見問題</span><span class="sxs-lookup"><span data-stu-id="d5d70-164">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="d5d70-165">通話方案所用的不同類型的電話號碼</span><span class="sxs-lookup"><span data-stu-id="d5d70-165">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="d5d70-166">管理貴組織的電話號碼</span><span class="sxs-lookup"><span data-stu-id="d5d70-166">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="d5d70-167">緊急通話條款與條件</span><span class="sxs-lookup"><span data-stu-id="d5d70-167">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

<span data-ttu-id="d5d70-168">[商務用 Skype Online：緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="d5d70-168">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
