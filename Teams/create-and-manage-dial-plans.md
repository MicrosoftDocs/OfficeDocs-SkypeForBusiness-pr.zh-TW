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
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: '瞭解如何在 Office 365 中建立呼叫撥號方案 (PSTN 呼叫撥號方案), 以及如何管理它們。 '
ms.openlocfilehash: 5254a2d63abeffa0b3452ed309d49272affcaf05
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2019
ms.locfileid: "36184365"
---
# <a name="create-and-manage-dial-plans"></a>建立及管理撥號方案

在您規劃好組織的撥號方案並查明需要為呼叫路由建立的所有正常化規則之後, 您必須使用 Windows PowerShell 來建立撥號方案並變更任何設定。
  
> [!NOTE]
> 商務用 Skype 系統管理中心無法用來建立和管理撥號方案。 
  
## <a name="verifying-and-starting-remote-powershell"></a>驗證及啟動遠端 PowerShell

 **檢查您執行的是 Windows PowerShell 版本3.0 或更高版本**
  
1. 若要確認您執行的是版本3.0 或更高版本: [**開始] 功能表** > **Windows PowerShell**。
    
2. 在**Windows PowerShell**視窗中輸入 [_取得主機_], 以檢查版本。
    
3. 如果您沒有版本3.0 或更高版本, 您需要下載並安裝 Windows PowerShell 更新。 請參閱[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) , 以下載並更新 Windows PowerShell 至版本4.0。 出現提示時, 請重新開機電腦。
    
4. 您也需要安裝適用于商務用 Skype Online 的 Windows PowerShell 模組, 這可讓您建立連線到商務用 Skype Online 的遠端 Windows PowerShell 會話。 此模組只受64位電腦支援, 可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。 如果出現提示, 請重新開機電腦。
    
如果您需要進一步瞭解, 請參閱[在單一 Windows PowerShell 視窗中連線至所有 Office 365 服務](https://technet.microsoft.com/EN-US/library/dn568015.aspx)。
  
 **啟動 Windows PowerShell 會話**
  
1. 從 [**開始] 功能表** > 中的 [**Windows PowerShell**]。
    
2. 在**Windows PowerShell**視窗中, 執行下列動作以連線到您的 Office 365 組織:
    
    > [!NOTE]
    > 您在第一次使用商務用 Skype Online Windows PowerShell 模組時, 您只需執行匯**入模組**命令。
  
> 
>   ```
>     Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
>     $credential = Get-Credential
>     $session = New-CsOnlineSession -Credential $credential
>     Import-PSSession $session
>   ```

如果您需要啟動 Windows PowerShell 的詳細資訊, 請參閱[在單一 Windows powershell 視窗中連線至所有 Office 365 服務](https://technet.microsoft.com/EN-US/library/dn568015.aspx), 或[使用 Windows PowerShell 連線到商務用 Skype Online](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)。
  
## <a name="creating-and-managing-your-dial-plans"></a>建立及管理您的撥號方案

您可以使用單一 Cmdlet 或 PowerShell 腳本來建立及管理租使用者撥號方案。
  
### <a name="using-single-cmdlets"></a>使用單一 Cmdlet

- 若要建立新的撥號方案, 請執行:
    
  ```
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    如需其他範例和參數, 請參閱[新 CsTenantDialPlan](https://technet.microsoft.com/library/mt775026.aspx)。
    
- 若要對現有的撥號方案進行設定變更, 請執行:
    
  ```
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    如需其他範例和參數, 請參閱[設定 CsTenantDialPlan](https://technet.microsoft.com/library/mt775023.aspx)。
    
- 若要將使用者新增至撥號方案, 請執行:
    
  ```
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    如需其他範例和參數, 請參閱[授與 CsTenantDialPlan](https://technet.microsoft.com/library/mt775021.aspx)。
    
- 若要查看撥號計畫的設定, 請執行:
    
  ```
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    如需其他範例和參數, 請參閱[CsTenantDialPlan](https://technet.microsoft.com/library/mt775024.aspx)。
    
- 若要刪除撥號方案, 請執行:
    
  ```
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    如需其他範例和參數, 請參閱[移除-CsTenantDialPlan](https://technet.microsoft.com/library/mt775020.aspx)。
    
- 若要查看有效撥號方案的設定, 請執行:
    
  ```
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    如需其他範例和參數, 請參閱[CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775022.aspx)。
    
- 若要測試撥號方案的有效設定, 請執行:
    
  ```
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255551234 -Identity 1849827b-a810-40a8-8f77-e94250d4680b_US_TenantDialPlanRedmond
  ```

    如需其他範例和參數, 請參閱[測試 CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775025.aspx)。
    
### <a name="using-a-powershell-script"></a>使用 PowerShell 腳本

執行此動作以刪除與租使用者撥號方案相關聯的正常化規則, 而不需要先刪除租使用者撥號方案:
```
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
執行此動作, 將下列正常化規則新增至現有的租使用者撥號方案 (名為 RedmondDialPlan)。
```
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
執行此操作, 從現有的租使用者撥號方案 (名為 RedmondDialPlan) 移除下列正常化規則。
```
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity DP1 -NormalizationRules @{remove=$nr1}
```

當您想要檢查現有的正常化規則時, 請執行下列動作, 判斷您想要刪除的規則, 然後使用其索引將它移除。 正常化規則陣列從索引0開始。 我們想要移除3位數的正常化規則, 以便編制索引1。
  
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

執行此工作以找出已授與 RedmondDialPlan 租使用者撥號計畫的所有使用者。
  
```
Get-CsOnlineuser | where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

執行此程式以刪除擁有 HostingProvider sipfed.online.lync.com 之所有使用者的 policyname。
```
Get-CsOnlineUser -Filter {HostingProvider -eq “sipfed.online.lync.com”} | Grant-CsTenantDialPlan -policyname $null
```

執行這些程式, 將名為 OPDP1 的現有內部部署撥號方案新增為貴組織的租使用者撥號計畫。 您必須先將內部部署撥號計畫儲存為 .xml 檔案, 然後再用來建立新的租使用者撥號方案。
  
執行此工作以將內部部署撥號計畫儲存到 .xml 檔案。
  
```
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

執行此工作來建立新的租使用者撥號方案。
  
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
## <a name="want-to-know-more-about-windows-powershell"></a>想要深入瞭解 Windows Powershell 嗎？

- Windows PowerShell 全部說明如何管理使用者, 以及允許或不允許的使用者執行。 在 Windows PowerShell 中, 您可以使用單一管理點管理 Office 365 和商務用 Skype Online, 當您有多個工作需要執行時, 可簡化日常作業。 若要開始使用 Windows PowerShell, 請參閱以下主題:
    
  - [Windows PowerShell 與 Lync Online 的簡介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [為什麼需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell 在速度、簡潔性和生產率上都有許多優點, 只是使用 Microsoft 365 系統管理中心, 例如當您在一次為多位使用者設定變更時。 請參閱下列主題, 瞭解這些優點:
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理商務用 Skype Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>相關主題
[傳送電話號碼常見問題](transferring-phone-numbers-common-questions.md)

[通話方案所用的不同類型的電話號碼](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[緊急通話條款與條件](emergency-calling-terms-and-conditions.md)

[商務用 Skype Online: 緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
