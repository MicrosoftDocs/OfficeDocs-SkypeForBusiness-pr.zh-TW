---
title: 建立和管理撥號對應表
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
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 瞭解如何建立和管理呼叫撥號方案（PSTN 呼叫撥號方案），以及管理它們的方式。
ms.openlocfilehash: 6a5f46772ed8eebb309ba8bd9eaeca6fddb35afa
ms.sourcegitcommit: 0fdc60840f45ff5b0a39a8ec4a21138f6cab49c9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/07/2020
ms.locfileid: "43160077"
---
# <a name="create-and-manage-dial-plans"></a>建立和管理撥號對應表

規劃貴組織的撥號方案並查明需要為呼叫路由建立的所有正常化規則之後，您就可以開始建立撥號方案了。 您可以使用 Microsoft 團隊系統管理中心或 Windows PowerShell 來建立及管理撥號方案。  

## <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft 團隊系統管理中心

### <a name="create-a-dial-plan"></a>建立撥號方案

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音** > **撥號方案**]。
2. 按一下 [**新增**]，然後輸入撥號方案的名稱和描述。
    ![顯示建立撥號方案之 [新增] 頁面的螢幕擷取畫面](media/create-dial-plan.png)
3. 在 [**撥號方案詳細資料**] 底下，如果使用者需要撥一或多個額外的前導數位（例如9）來取得外部線路，請指定外部撥號首碼。 若要執行此動作：
    1. 在 [**外部撥號首碼**] 方塊中，輸入外部撥號首碼。 前置詞最多可有四個字元（#、* 及0-9）。
    2. 開啟**優化的裝置撥號**。 如果您指定外部撥號首碼，您也必須開啟此設定以套用首碼，以便在您的組織以外進行通話。
4. 在 [**正常化規則**] 底下，針對撥號方案設定及建立一或多個[正常化規則](what-are-dial-plans.md#normalization-rules)。 每個撥號方案都必須至少有一個與它相關聯的正常化規則。  若要這樣做，請執行下列其中一項或多項操作：
    - 若要建立新的正常化規則，並將它與撥號方案建立關聯，請按一下 [**新增**]，然後定義規則。
    - 若要編輯已經與撥號方案相關聯的正常化規則，請按一下規則名稱左邊的，然後按一下 [**編輯**]，選取規則。 進行您想要的變更，然後按一下 [**儲存**]。
    - 若要從撥號方案中移除正常化規則，請按一下規則名稱左方，然後按一下 [**移除**]，即可選取規則。
5. 依您想要的順序排列正常化規則。 按一下 [**上移** **] 或 [下移]** ，即可變更清單中規則的位置。

    > [!NOTE]
    > 團隊會從上而下遍歷正常化規則清單，並使用與撥號號碼相符的第一個規則。 如果您設定撥號方案，讓撥入的號碼可以符合多個正常化規則，請確定更嚴格的規則排序在限制性較低的規則上方。

6. 按一下 [儲存]****。
7. 如果您想要測試撥號規劃，請在 [**測試撥號方案**] 下輸入電話號碼，然後按一下 [**測試**]。

### <a name="edit-a-dial-plan"></a>編輯撥號方案

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音** > **撥號方案**]。
2. 按一下撥號方案名稱左邊的，然後按一下 [**編輯**]，選取撥號方案。
3. 進行您想要的變更，然後按一下 [**儲存**]。

### <a name="add-users-to-a-dial-plan"></a>將使用者新增至撥號方案

1. 在 Microsoft 團隊系統管理中心的左導覽中，前往 [**使用者**]。
2. 按一下 [顯示名稱]，選取使用者。
3. 選取 [**原則**] 索引標籤。
4. 按一下指派原則右側的 [**編輯**]。
5. 從 [**撥號方案**] 下拉式功能表中，選取您要指派給使用者的撥號方案，然後按一下 [套用] **。**

## <a name="using-powershell"></a>使用 PowerShell
  
### <a name="verify-and-start-remote-powershell"></a>驗證並啟動遠端 PowerShell

 **檢查您執行的是 Windows PowerShell 版本3.0 或更新版本**
  
1. 若要確認您執行的是版本3.0 或更高版本： [**開始] 功能表** > **Windows PowerShell**。
    
2. 在**Windows PowerShell**視窗中輸入 [_取得主機_]，以檢查版本。
    
3. 如果您沒有版本3.0 或更新版本，請下載並安裝 Windows PowerShell 更新。 請參閱[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) ，以下載並更新 Windows PowerShell 至版本4.0。 出現提示時，請重新開機電腦。
    
4. 您也需要安裝適用于商務用 Skype Online 的 Windows PowerShell 模組，這可讓您建立連線到商務用 Skype Online 的遠端 Windows PowerShell 會話。 您可以在[商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上，下載此模組（只有64位電腦支援）。 如果出現提示，請重新開機電腦。
    
若要深入瞭解，請參閱[在單一 Windows PowerShell 視窗中連接至所有 Office 365 服務](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)。
  
 **啟動 Windows PowerShell 會話**
  
1. 按一下 [**啟動** > **Windows PowerShell**]。
    
2. 在**Windows PowerShell**視窗中，執行下列動作以連線到您的 Office 365 組織：
    
    > [!NOTE]
    > 您在第一次使用商務用 Skype Online Windows PowerShell 模組時，您只需執行匯**入模組**命令。
  

    ```PowerShell
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
    ```
  
### <a name="create-and-manage-your-dial-plans"></a>建立及管理您的撥號方案

您可以使用單一 Cmdlet 或 PowerShell 腳本來建立及管理租使用者撥號方案。
  
#### <a name="using-single-cmdlets"></a>使用單一 Cmdlet

- 若要建立新的撥號方案，請執行：
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    如需其他範例和參數，請參閱[新 CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan)。
    
- 若要編輯現有撥號方案的設定，請執行：
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    如需其他範例和參數，請參閱[設定 CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan)。
    
- 若要將使用者新增至撥號方案，請執行：
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    如需其他範例和參數，請參閱[授與 CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan)。
    
- 若要查看撥號計畫的設定，請執行：
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    如需其他範例和參數，請參閱[CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps)。
    
- 若要刪除撥號方案，請執行：
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    如需其他範例和參數，請參閱[移除-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps)。
    
- 若要查看有效撥號方案的設定，請執行：
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    如需其他範例和參數，請參閱[CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan)。
    
- 若要測試撥號方案的有效設定，請執行：
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    如需其他範例和參數，請參閱[測試 CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps)。
    
#### <a name="using-a-powershell-script"></a>使用 PowerShell 腳本

執行此動作以刪除與租使用者撥號方案相關聯的正常化規則，而不需要先刪除租使用者撥號方案：
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
執行此動作，將下列正常化規則新增至現有的租使用者撥號方案（名為 RedmondDialPlan）。
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
執行此操作，從現有的租使用者撥號方案（名為 RedmondDialPlan）移除下列正常化規則。
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

當您想要檢查現有的正常化規則時，請執行下列動作，判斷您想要刪除的規則，然後使用其索引將它移除。 正常化規則陣列從索引0開始。 我們想要移除3位數的正常化規則，以便編制索引1。
  
```PowerShell
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

$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[1]
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

執行此工作以找出已授與 RedmondDialPlan 租使用者撥號計畫的所有使用者。
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

執行此 TenantDialPlan，以移除所有擁有 sipfed.online.lync.com HostingProvider 的使用者指派的任何。
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq “sipfed.online.lync.com”} | Grant-CsTenantDialPlan -policyname $null
```

執行這些程式，將名為 OPDP1 的現有內部部署撥號方案新增為貴組織的租使用者撥號計畫。 您必須先將內部部署撥號計畫儲存為 .xml 檔案，然後再用來建立新的租使用者撥號方案。
  
執行此工作以將內部部署撥號計畫儲存到 .xml 檔案。
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

執行此工作來建立新的租使用者撥號方案。
  
```PowerShell
$DPFileName = "dialplan.xml"
$dp = Import-Clixml $DPFileName
$NormRules = @()
ForEach($nr in $dp.NormalizationRules)
{
 $id1 = "Global/" + $nr.Name
 $nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation -IsInternalExtension $nr.IsInternalExtension -InMemory
 $NormRules += $nr2
}
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```
    
## <a name="related-topics"></a>相關主題

- [什麼是撥號對應表？](what-are-dial-plans.md)
- [移轉電話號碼的常見問題](transferring-phone-numbers-common-questions.md)
- [通話方案所用的不同類型的電話號碼](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [緊急通話條款及條件](emergency-calling-terms-and-conditions.md)
- [緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
- [Teams PowerShell 概觀](teams-powershell-overview.md)
