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
- seo-marvel-apr2020
description: 瞭解如何使用系統管理中心Microsoft Teams或Windows PowerShell PSTN 撥號方案 (撥號方案) 。
ms.openlocfilehash: 59867dfe49436635f690ff9f5d56a2be36e553ec
ms.sourcegitcommit: 127f9fdf05b93ee3af4244224e1c32a45d73d3ee
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/21/2021
ms.locfileid: "53046230"
---
# <a name="create-and-manage-dial-plans"></a>建立和管理撥號對應表

規劃組織的撥號方案，並找出呼叫路由需要建立的所有標準化規則之後，就可以建立撥號方案了。 使用具有有效授權Teams系統管理員帳戶，您可以使用 Microsoft Teams或Windows PowerShell建立和管理撥號方案。  

## <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

### <a name="create-a-dial-plan"></a>建立撥號方案

1. 在系統管理中心的左側導Microsoft Teams，請前往 **語音**  >  **撥號方案**。
2. 按一下 **[新增**」，然後輸入撥號方案的名稱和描述。
    ![顯示建立撥號方案之新增頁面的螢幕擷取畫面](media/create-dial-plan.png)
3. 在 **撥號方案詳細資料** 下，指定外部撥號首碼，如果使用者需要撥打一或多個額外的前導 (例如 9) 以取得外部線路。 若要這麼做：
    1. 在外部 **撥號首碼** 方塊中，輸入外部撥號首碼。 首碼最多四個字元 (#、*和 0-9) 。
    2. 開啟優化 **的裝置撥號**。 如果您指定外部撥號首碼，您也必須開啟此設定，才能使用首碼，才能在組織外撥打電話。
4. 在 **標準化規則** 下，為撥號方案設定一 [或多個標準化](what-are-dial-plans.md#normalization-rules) 規則並關聯。 每個撥號方案都必須至少有一個與其相關聯的標準化規則。  若要這麼做，請執行下列一或多個操作：
    - 若要建立新常態化規則並將其與撥號方案建立關聯，請按一下 [ **新增**，然後定義規則。
    - 若要編輯已與撥號方案相關聯的標準化規則，請按一下規則名稱左側以選取規則，然後按一下 [ **編輯**。 進行您想要的變更，然後按一下 [ **儲存**。
    - 若要從撥號方案移除標準化規則，請按一下規則名稱左側以選取規則，然後按一下 [ **移除**。
5. 以您想要的順序排列標準化規則。 按一下 **[上移** 或 **下** 移以變更規則在清單中的位置。

    > [!NOTE]
    > Teams由上而下，從上而下移動標準化規則清單，並使用符合撥號號碼的第一個規則。 如果您設定撥號方案，讓撥號號碼可以比對多個標準化規則，請確定較嚴格的規則會排序在較不嚴格的規則上方。 如果您設定了將撥號號碼正規化的撥號方案，但不含 「+」，通話服務會嘗試使用租使用者和區域撥號方案規則再次嘗試將號碼正規化。 為了避免重複常態化，建議所有標準化規則都會導致數位以"+"開始。 直接路由客戶可以使用 [主幹翻譯](direct-routing-translate-numbers.md) 規則來移除 「+」。如果需要的話。 

6. 按一下 [儲存]。
7. 如果您想要測試撥號方案，請在 [測試撥號方案> 下輸入電話號碼，然後按一下 [**測試**。

### <a name="edit-a-dial-plan"></a>編輯撥號方案

1. 在系統管理中心的左側導Microsoft Teams，請前往 **語音**  >  **撥號方案**。
2. 按一下撥號方案名稱左側的撥號方案，然後按一下 [編輯」，以選取 **撥號方案**。
3. 進行您想要的變更，然後按一下 [ **儲存**。

### <a name="assign-a-dial-plan-to-users"></a>指派撥號方案給使用者

您以指派策略的方式指派撥號方案。 [!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="using-powershell"></a>使用 PowerShell
  
### <a name="start-powershell"></a>啟動 PowerShell
- 開啟 Windows PowerShell命令提示符，然後執行下列命令：

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
  
### <a name="create-and-manage-your-dial-plans"></a>建立和管理撥號方案

您可以使用單一 Cmdlet 或 PowerShell 腳本來建立和管理租使用者撥號方案。
  
#### <a name="using-single-cmdlets"></a>使用單一 Cmdlet

- 若要建立新的撥號方案，請執行：
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    有關其他範例和參數，請參閱 [New-CsTenantDialPlan](/powershell/module/skype/new-cstenantdialplan)。
    
- 若要編輯現有撥號方案設定，請執行：
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    有關其他範例和參數，請參閱 [Set-CsTenantDialPlan](/powershell/module/skype/set-cstenantdialplan)。
    
- 若要將使用者新增到撥號方案，請執行：
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    有關其他範例和參數，請參閱 [Grant-CsTenantDialPlan](/powershell/module/skype/grant-cstenantdialplan)。
    
- 若要在撥號方案上查看設定，請執行：
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    有關其他範例和參數，請參閱 [Get-CsTenantDialPlan](/powershell/module/skype/get-cstenantdialplan?view=skype-ps)。
    
- 若要刪除撥號方案，請執行：
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    有關其他範例和參數，請參閱 [Remove-CsTenantDialPlan](/powershell/module/skype/remove-cstenantdialplan?view=skype-ps)。
    
- 若要查看有效撥號計畫的設定，請執行：
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    有關其他範例和參數，請參閱 [Get-CsEffectiveTenantDialPlan](/powershell/module/skype/get-cseffectivetenantdialplan)。
    
- 若要測試撥號方案的有效設定，請執行：
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    有關其他範例和參數，請參閱 [Test-CsEffectiveTenantDialPlan](/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps)。
    
#### <a name="using-a-powershell-script"></a>使用 PowerShell 腳本

執行此操作以刪除與租使用者撥號方案相關聯的標準化規則，而不需要先刪除租使用者撥號方案：
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
執行此程式，將下列標準化規則新增到名為 RedmondDialPlan 的現有租使用者撥號方案。
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
執行此程式，從名為 RedmondDialPlan 的現有租使用者撥號方案移除下列標準化規則。
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

當您也想要檢查現有的標準化規則、決定要刪除哪些規則，然後使用其索引來移除規則時，請執行下列操作。 標準化規則的陣列會以索引 0 開始。 我們要移除 3 位數的標準化規則，因此這是索引 1。
  
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

執行此程式以尋找所有獲得 RedmondDialPlan 租使用者撥號方案的使用者。
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

執行此程式以移除所有擁有 HostingProvider sipfed.online.lync.com。
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq "sipfed.online.lync.com"} | Grant-CsTenantDialPlan -policyname $null
```

執行這些操作，將名為 OPDP1 的現有內部部署撥號方案新增為貴組織的租使用者撥號方案。 您需要先將內部部署撥號方案儲存到.xml，然後使用它來建立新的租使用者撥號方案。
  
執行此操作，將內部部署撥號方案儲存到.xml檔案。
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

執行此程式以建立新的租使用者撥號方案。
  
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
- [移轉電話號碼的常見問題](./phone-number-calling-plans/port-order-overview.md)
- [用於通話方案的各種電話號碼](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [緊急通話條款及條件](emergency-calling-terms-and-conditions.md)
- [緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
- [Teams PowerShell 概觀](teams-powershell-overview.md)
