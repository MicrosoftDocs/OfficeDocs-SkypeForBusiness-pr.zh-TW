---
title: 從商務語音移至Teams 電話授權
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- m365initiative-voice
search.appverid: MET150
description: 瞭解如何將您的商務語音授權變更為Teams 電話授權。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 39e374175b4ba0a7613405305c4db3baa0e69171
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/13/2022
ms.locfileid: "66046128"
---
# <a name="move-from-business-voice-to-teams-phone-licenses"></a>從商務語音移至Teams 電話授權

到 2022 年 6 月底為止，將淘汰 Business Voice，因此我們[建議企業切換到Microsoft Teams 電話含通話方案套件組合授權](https://techcommunity.microsoft.com/t5/small-and-medium-business-blog/teams-phone-with-calling-plan-available-in-33-markets-on-january/ba-p/2967643)。

Business Voice 搭售下列三Teams附加元件授權：

- **Microsoft Teams** 中雲端型電話系統Microsoft Teams 電話。
- 會議電話撥入式會議和撥出式會議的 **音訊** 會議。
- 國內公用交換電話網路 (PSTN) 連線的 Microsoft **通話方案**。

現有的商務語音客戶不會自動轉換為新的授權模式。

本文適用于需要將其商務語音授權變更為Microsoft Teams 電話和音訊會議授權，同時維護相同功能的 IT 系統管理員。

## <a name="acquire-new-licenses"></a>取得新授權

在更換商務語音授權之前，您必須先為使用者購買取代授權。

您需要授權才能提供這些功能：

- 音訊會議
- 雲端式電話系統
- PSTN 連線能力

請根據您的需求，使用下表來判斷要購買哪些授權：

| 舊授權方案 | 建議的授權方案 | 描述 |
| ---------------- | ------------------------ | ----------- |
| 附帶通話方案的 Business Voice | 含通話方案的 Teams 電話 | 提供雲端型電話系統功能，以及以 Microsoft 做為 PSTN 提供者的國內通話方案。 |
| 不含通話方案的商務語音 | Teams 電話標準方案 | 提供可[透過協力廠商 PSTN 提供者使用電信業者連線或直接路由與通話方案](pstn-connectivity.md)結合的雲端型電話系統功能 |
| 商務語音 (任何版本)  | Microsoft Team 音訊會議選取 [撥出] 或 [音訊會議] | 提供撥入和撥出功能給授權使用者召集的會議出席者 |

## <a name="how-to-update-licenses"></a>如何更新授權

您有四種方式可以更新您的授權：

- 單一使用者授權會透過Microsoft 365 系統管理中心更新。
- 透過Microsoft 365 系統管理中心大量使用者授權更新。
- 使用 PowerShell 腳本大量更新使用者授權。
- 使用 Azure 群組授權進行大量使用者授權更新。

# <a name="option-1-single-user-in-admin-center"></a>[選項 1：系統管理中心的單一使用者](#tab/single-user)

### <a name="option-1-single-user-license-update-via-microsoft-365-admin-center"></a>選項 1：單一使用者授權透過Microsoft 365 系統管理中心更新

若要更新單一使用者，您可以使用Microsoft 365 系統管理中心。

1. 移至 [admin.microsoft.com](https://admin.microsoft.com/) ，並使用租使用者系統管理員認證登入。
1. 流覽至 **[使用者**  >  **作用中使用者]**，然後選取想要的使用者。
1. 選取清單工具列上的 **[管理產品授權** ]。
1. 在 [ **授權與應用程式]** 畫面上，取消選取商務語音授權。
    > [!IMPORTANT]
    > 請勿儲存變更。 如果您儲存變更而不新增新的授權，使用者帳戶將會遭到撤銷，且電話號碼會被取消指派。
1. 取消選取商務語音之後，請檢查新的Teams 電話和音訊會議授權。
1. 現在您可以選取 [儲存變更]，安全地儲存 **變更**。

使用者的授權將會更新，且不應影響服務可用性。

# <a name="option-2-bulk-users-in-admin-center"></a>[選項 2：系統管理中心的大量使用者](#tab/bulk-users-admin-center)

### <a name="option-2-bulk-user-license-update-via-microsoft-365-admin-center"></a>選項 2：透過 Microsoft 365 系統管理中心 大量使用者授權更新

若要大量更新多個使用者的授權，您可以使用Microsoft 365 系統管理中心。 選取的使用者將擁有相同的授權方案指派。

1. 移至 [admin.microsoft.com](https://admin.microsoft.com/) ，並使用租使用者系統管理員認證登入。
1. 流覽至 **[使用者**  >  **作用中使用者]**，然後選取所有想要的使用者。  
1. 選取清單工具列上的 **[管理產品授權** ]。
1. 在 [ **您要如何處理這些使用者的授權？** ] 提示中，選取 **[取代：取消指派現有授權並指派新授權]** 選項。
    > [!IMPORTANT]
    > **[取代]** 選項會移除所選使用者的所有現有授權。  因此，您必須為使用者選取想要的授權狀態，包括任何其他使用中的授權，例如Microsoft 365 商務進階版。
    >
    > 此外，如果選取的使用者有不同的基本授權設定，則會使用您選取的授權覆寫這些設定，這可能會影響Microsoft 365的其他區域。
    >
    > 對於具有混合授權設定的租使用者，建議您搭配 [PowerShell 腳本使用大量更新選項](#option-3-bulk-user-license-update-using-a-powershell-script)。
1. 在 [ **授權與應用程式]** 畫面上，取消選取商務語音授權。
    > [!IMPORTANT]
    > 請勿儲存變更。 如果您儲存變更而不新增新的授權，則會撤銷所選使用者的帳戶，以及未指派的電話號碼。
1. 取消選取商務語音之後，請檢查新的Teams 電話和音訊會議授權。
1. 現在您可以選取 [儲存變更]，安全地儲存 **變更**。
  使用者的授權將會更新，且不應影響服務可用性。

# <a name="option-3-bulk-users-via-powershell"></a>[選項 3：透過 PowerShell 大量使用者](#tab/powershell)

### <a name="option-3-bulk-user-license-update-using-a-powershell-script"></a>選項 3：使用 PowerShell 腳本大量更新使用者授權

使用 PowerShell 腳本取代商務語音授權方案是大多數案例的有效解決方案。  

若要使用此方法，您將遵循下列一般步驟：

1. 取得您目前商務語音授權的租使用者特定授權方案識別碼。
1. 取得新Teams 電話和音訊會議授權方案的租使用者特定識別碼。
1. 驗證新的授權方案是否與目前的商務語音授權具有相同的服務方案。
1. 尋找獲得商務語音 (授權的租使用者使用者，或是修改腳本以包含篩選，以在需要時選取使用者子集) 。
1. 使用Teams 電話和音訊會議方案更新使用者的授權設定。

> [!IMPORTANT]
> 提供的腳本為程式碼範例。 腳本不應該像目前一樣複製，並在生產租使用者中執行，而不需針對您的特定環境進行測試、驗證和自訂。

### <a name="how-to-bulk-update-licenses-using-powershell"></a>如何使用 PowerShell 大量更新授權

1. 安裝並匯入 AzureAD PowerShell 模組。

    ```powershell
    Install-Module AzureAD
    Import-Module AzureAD
    ```

1. 連線至您的Microsoft 365租使用者，並提供租使用者系統管理員認證。

    ```powershell
    Connect-AzureAD
    ```

1. 使用下列命令，列出租使用者中的所有授權套件。

    ```powershell
    Get-AzureADSubscribedSku
    ```

1. 請使用下表來識別即將被取代的商務語音附加元件授權方案。

    | SKU 代碼 | 授權類型 |
    | -------- | ------------ |
    | BUSINESS_VOICE_MED | 商務語音通話方案 - 加拿大 |
    | BUSINESS_VOICE | 商務語音通話方案 - 英國 |
    | BUSINESS_VOICE_MED2_TELCO | 商務語音通話方案 - 美國 |
    | BUSINESS_VOICE_DIRECTROUTING | 不含通話方案的商務語音 |
    | BUSINESS_VOICE_DIRECTROUTING_MED | 不使用通話方案的商務語音 - 美國 |

    > [!NOTE]
    > 此檔中提供的腳本假設您的租使用者中有單一商務用 SKU 代碼語音。  
    >
    > 如果您有多個商務語音 SKU，您必須針對每個 SKU 代碼調整腳本或多次執行腳本。

1. 建立名為 `$skuSourceBV` . 的 PowerShell 變數。
    1. 請務必將標籤取代 `SkuPartNumber` 為租使用者的商務語音 SKU 代碼。
    1. 在此範例中 `BUSINESS_VOICE_MED2_TELCO` ，我們使用的是 SKU 代碼。

    ```powershell
    $skuSourceBV = Get-AzureADSubscribedSku  | where {$_.SkuPartNumber -eq "BUSINESS_VOICE_MED2_TELCO"}
    ```

1. 請使用下表來識別您的新Teams 電話和音訊會議授權 SKU 代碼。

    | SKU 代碼 | 授權類型 |
    | -------- | ------------ |
    | MCOTEAMS_ESSENTIALS | 含通話方案的 Teams 電話 |
    | MCOEV | Teams 電話標準方案 (無通話方案)  |
    | MCOMEETADV | 音訊會議 |
    | Microsoft_Teams_Audio_Conferencing_select_dial_out | Microsoft Teams音訊會議] 選取 [撥出] |

1. 建立 PowerShell 變數以儲存唯一的Teams 電話和音訊會議 SKU 代碼。
    1. 請務必將標籤取代 `SkuPartNumber` 為您租使用者中可用的 SKU 代碼。
    1. 在此範例中 `MCOTEAM_ESSENTIALS` ，我們使用的是和 `MCOMEETADV` SKU 代碼。

        ```powershell
        $skuTargetTPCP = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOTEAMS_ESSENTIALS"}
        $skuTargetAC = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOMEETADV"} 
        ```

1. 執行此腳本以從來源 SKU 收集必要的服務方案資料至唯一物件。

     ```powershell
     $servicePlan_Phone = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*EV*"}
    $servicePlan_AC = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*MEET*"}
    $servicePlan_CP = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*PSTN*"}
    ```

1. 在繼續之前，請先驗證來源 SKU (Business Voice) 和目標 SKU (Teams 電話 和音訊會議) 是否包含相同的服務方案。
    1. 不相符可能會觸發授權變更，而中斷使用者的語音和音訊會議服務。
    2. 建立變數以驗證來源 SKU 中的所有服務方案是否會以相同的目標服務方案取代。

        ```powershell
        $validated_TP = $false
        $validated_AC = $false
        $validated_CP = $false
        ```

    3. 如果來源商務語音授權未包含通話方案，請勿檢查。

        ```powershell
        if($skuSourceBV.ServicePlans.Count -eq 2) { $validated_CP = $true }
        ```

    4. 確認來源 SKU 中的所有服務方案在目標 SKU 中是否有相符的服務方案。

        ```powershell
        For ($i=0; $i -le $skuSourceBV.ServicePlans.Count ; $i++) {
        if($validated_TP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_Phone)) { $validated_TP = $true } }
        if($validated_AC -eq $false) { if($skuTargetAC.ServicePlans.Contains($servicePlan_AC)) { $validated_AC = $true } }
        if($validated_CP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_CP)) { $validated_CP = $true } }
        }
        ```

    5. 如果目標 SKU 中有服務方案遺失，您可能會中斷使用者的服務可用性，而您的腳本應該會停止處理。

        ```powershell
        if($validated_TP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Teams Phone." ; exit }
        if($validated_AC -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Audio Conferencing." ; exit }
        if($validated_CP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Calling Plan." ; exit }
        ```

1. 如果一切正常，請準備 PowerShell 物件以對使用者物件執行更新作業。 `AssignedLicenses`請使用此物件。

    ```powershell
    $LicenseAddTPCP = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
    $LicenseAddTPCP.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetTPCP.SkuPartNumber -EQ).SkuID
    $LicenseAddAC = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
    $LicenseAddAC.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetAC.SkuPartNumber -EQ).SkuID
    
    $LicensesToUpdate = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
    $LicensesToUpdate.AddLicenses += ($LicenseAddTPCP)
    $LicensesToUpdate.AddLicenses += ($LicenseAddAC)
    $LicensesToUpdate.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuSourceBV.SkuPartNumber -EQ).SkuID
    ```

1. 接下來，取得已指派商務語音授權的使用者清單，並將其儲存在名為 `$usersLicensedOldSKU` . 的清單中。

    ```powershell
    $usersLicensedOldSKU = New-Object System.Collections.Generic.List[Microsoft.Open.AzureAD.Model.User]
    
    Get-AzureAdUser | ForEach { $BVlicensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If($_.AssignedLicenses[$i].SkuId -eq $skuSourceBV.SkuId) { $BVlicensed=$true } } ; If( $BVlicensed -eq $true) { $usersLicensedOldSKU.Add($_)} }
    ```

1. 現在，使用新的使用者清單，執行更新活動以移除商務語音授權，並使用 ``$LicensesToUpdate`` 您先前建立的物件來新增Teams 電話和音訊會議授權。

    ```powershell
    $usersLicensedOldSKU | ForEach { Set-AzureADUserLicense -ObjectId $_.ObjectId -AssignedLicenses $LicensesToUpdate; Write-Host "Completed Update of user " $_.UserPrincipalName;  }
    ```

> [!NOTE]
> 如果您沒有足夠的可用Teams 電話和/或音訊會議授權來取代商務語音，您會在使用者指派期間收到使用 **SKU GUID 訂閱未收到任何可用授權** 的錯誤。只要授權集區出現。

### <a name="full-script"></a>完整腳本

```powershell
#Install the AzureAD module when required
Install-Module AzureAD
#Import the AzureAD module so you can use the commandlets
Import-Module AzureAD

#Connect to your tenant
Connect-AzureAD

#When necessary, uncomment and use this commandlet to list all the licenses in the tenant and identify which license packages are required
#Get-AzureADSubscribedSku

##Replace the SKU codes below to match your desired scenario
$skuSourceBV = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "BUSINESS_VOICE_MED2_TELCO"}
$skuTargetTP = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOTEAMS_ESSENTIALS"}
$skuTargetAC = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOMEETADV"}

##Replace the SKU codes below to match your desired scenario
$servicePlan_Phone = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*EV*"}
$servicePlan_AC = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*MEET*"}
$servicePlan_CP = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*PSTN*"}

##Create variables to validate if all Service Plans in the source SKU will be replaced with the same target service plan
$validated_TP = $false
$validated_AC = $false
$validated_CP = $false

##If source Business Voice has no Calling Plan included, do not check
if($skuSourceBV.ServicePlans.Count -eq 2) { $validated_CP = $true }

##Verify if all service plans in source SKU have a matching service plan in target SKU
For ($i=0; $i -le $skuSourceBV.ServicePlans.Count ; $i++) { 
    if($validated_TP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_Phone)) { $validated_TP = $true } }
    if($validated_AC -eq $false) { if($skuTargetAC.ServicePlans.Contains($servicePlan_AC)) { $validated_AC = $true } }
    if($validated_CP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_CP)) { $validated_CP = $true } }
}

##If there's a missing service plan in the target sku, we might impact service availability for a user and therefore stop processing
if($validated_TP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Teams Phone." ; exit } 
if($validated_AC -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Audio Conferencing." ; exit } 
if($validated_CP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Calling Plan." ; exit } 


##Prepare variables and update
$LicenseAddTP = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$LicenseAddTP.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetTP.SkuPartNumber -EQ).SkuID
$LicenseAddAC = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$LicenseAddAC.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetAC.SkuPartNumber -EQ).SkuID
$LicensesToUpdate = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToUpdate.AddLicenses += ($LicenseAddTP)
$LicensesToUpdate.AddLicenses += ($LicenseAddAC)
$LicensesToUpdate.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuSourceBV.SkuPartNumber -EQ).SkuID

$usersLicensedOldSKU = New-Object System.Collections.Generic.List[Microsoft.Open.AzureAD.Model.User]
Get-AzureAdUser | ForEach { $BVlicensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If($_.AssignedLicenses[$i].SkuId -eq $skuSourceBV.SkuId) { $BVlicensed=$true } } ; If( $BVlicensed -eq $true) { $usersLicensedOldSKU.Add($_)} }

$usersLicensedOldSKU | ForEach { Set-AzureADUserLicense -ObjectId $_.ObjectId -AssignedLicenses $LicensesToUpdate; Write-Host "Completed Update of user " $_.UserPrincipalName;  }
```

# <a name="option-4-bulk-users-with-azure-group-based-licensing"></a>[選項 4：大量使用 Azure 群組授權的使用者](#tab/azure-licensing)

### <a name="option-4-bulk-user-license-update-using-azure-group-based-licensing"></a>選項 4：使用 Azure 群組授權大量更新使用者授權

Azure 群組授權管理可讓您將訂閱和服務方案指派給群組。

這個方法可確保：

- 授權會指派給群組的所有成員。
- 任何加入群組的新成員都會獲派適當的授權。
- 當成員從群組中移除時，也會移除這些授權。

您必須驗證 [群組授權的授權需求](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)。

> [!NOTE]
> 對於這個方法，授權更新必須以單一步驟進行處理。
>
> 建議您編譯已指派商務語音授權的現有群組清單，先選取小型測試使用者群組，然後以慣用的新授權方案取代授權方案指派。

### <a name="how-to-bulk-update-licenses-using-group-based-licensing"></a>如何使用群組授權大量更新授權

1. 移至 [portal.azure.com](https://portal.azure.com) ，並使用系統管理員認證登入。
1. 移至 **[Azure Active Directory**]，然後在左側功能表上選取 [**授權]**。
1. 若要確認哪些群組已指派商務語音授權，請選擇 **[所有產品]** ，然後選取 [商務語音] 方案。
1. 選 **取 [授權群組** ] 或 **[授權使用者]**。 您會在右側窗格中找到授權群組清單。
1. 選取組名以開啟群組作業詳細資料。
1. 選 **取 [作業]** 以修改指派給此群組的授權。
1. 核取您取得以取代 Business Voice 之授權方案前面的方塊。
1. 取消核取Microsoft 365 商務語音授權方案前面的方塊。
1. 選取 [儲存 **]**。
1. 選取組名以返回群組。 您會看到橫幅，指出 **授權變更擱置中**。
1. 選取 **[重處理** ] 以強制更新授權指派。

---

## <a name="validate-user-license-updates"></a>驗證使用者授權更新

完成所選方法之後，請驗證使用者授權是否已正確更新。

1. 移至[Microsoft 365 系統管理中心](https://admin.microsoft.com)，並使用系統管理員認證登入。
1. 流覽至 **[使用者**  >  **作用中使用者]**，然後選取測試使用者。
1. 選取工具列上的 **[管理產品授權** ]。
1. 在 [ **授權與應用程式** ] 畫面上，檢閱他們已指派給哪些授權。

如果所有目標使用者都已指派正確的授權，表示您已完成將商務語音授權更新為Teams 電話和音訊會議授權。
