---
title: 決定解除授權後如何管理屬性
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
description: 本文說明如何在解除委任您的內部部署環境之後管理屬性。
ms.openlocfilehash: 64a56b2fd5543179fbd9167721ad60699c6c4a23
ms.sourcegitcommit: 2e8daa3511cd198b3e0d43b153dd37a59cb21692
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2022
ms.locfileid: "62763787"
---
# <a name="decide-how-to-manage-attributes-after-decommissioning"></a>決定解除授權後如何管理屬性

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


根據預設，所有為商務用 Skype Server 啟用之後又移至雲端的使用者，仍然會在您的內部部署 Active Directory 中設定 msRTCSIP 屬性。 

這些屬性（特別是 sip 位址 (msRTCSIP-PrimaryUserAddress) 和電話號碼 (msRTCSIP 行) ）繼續同步處理至 Azure AD。 如果需要變更任何 msRTCSIP 屬性，則必須在內部部署 Active Directory 中進行這些變更，然後同步處理至 Azure AD。 不過，商務用 Skype Server 部署已移除之後，就無法使用商務用 Skype Server 工具來管理這些屬性。

有兩個選項可用於處理這種情況：

1. 保留已為商務用 Skype 伺服器帳戶啟用的使用者，並使用 Active Directory 工具管理 msRTCSIP 屬性。 此方法可確保未遷移使用者的服務遺失，並可讓您移除商務用 Skype Server 部署，方法是消除 (（例如，擦除) 伺服器，而不需完全解除委任）。 不過，新授權的使用者將不會在您的內部部署 Active Directory 中填入這些屬性，且必須在線上進行管理。

2.  從內部部署 Active Directory 中已遷移的使用者清除所有 msRTCSIP 屬性，並使用線上工具管理這些屬性。 此方法可讓現有和新使用者使用一致的管理方法。 不過，在內部部署解除委任過程中，可能會造成服務暫時遺失。


## <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a>方法 1-管理 Active Directory 中使用者的 sip 位址和電話號碼

管理員可以管理從內部部署商務用 Skype Server 移至雲端的使用者，即使在內部部署的部署解除委任後，也是如此。 

如果您想要變更使用者的 sip 位址或使用者的電話號碼 (而且 sip 位址或電話號碼在內部部署 Active Directory) 中已有值，您必須在內部部署 Active Directory 中進行變更，並讓) 流程中的值 (s Azure AD。 此方法不需要內部部署商務用 Skype Server。 相反地，您可以使用 Active Directory 使用者和電腦 MMC 嵌入式管理單元來直接修改內部部署 Active Directory 中的這些屬性 (，如) 所示，或是使用 PowerShell。 如果您使用的是 MMC 嵌入式管理單元，請開啟使用者的 [內容] 頁面，按一下 [屬性編輯器] 索引標籤，然後尋找適當的屬性進行修改：

- 若要修改使用者的 sip 位址，請修改 `msRTCSIP-PrimaryUserAddress` 。

    > [!NOTE]
    > `ProxyAddresses`如果屬性包含 sip 位址，也會將此值更新為最佳作法。 雖然所填入的 sip 位址已在 O365 `msRTCSIP-PrimaryUserAddress` 中 `ProxyAddresses` 忽略，但其他內部部署元件也可以使用它。

- 若要修改使用者的電話號碼，請修改 `msRTCSIP-Line` *是否已有值*。

  ![[Active Directory 使用者和電腦] 工具。](../media/disable-hybrid-1.png)


- 如果使用者在移動之前沒有內部部署的值 `msRTCSIP-Line` ，您可以使用 `-PhoneNumber` Teams PowerShell 模組的[CsPhoneNumberAssignment 指令程式](/powershell/module/teams/set-csphonenumberassignment)中的參數修改電話號碼。

在您停用混合式之後所建立的新使用者，這些使用者不需要這些步驟，而且可以直接在雲端中管理這些使用者。 如果您習慣搭配使用這些方法，並在內部部署 Active Directory 中就地保留 msRTCSIP 屬性，您可以重新鏡像內部部署商務用 Skype 伺服器。 不過，如果您想要清除所有 msRTCSIP 屬性，並執行商務用 Skype Server 的傳統卸載，請使用方法2。


## <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a>方法 2-清除 Active Directory 中所有內部部署使用者的商務用 Skype 屬性

這個選項需要更多的工作量及適當的規劃，因為從內部部署商務用 Skype Server 移至雲端的使用者必須重新布建。 這些使用者可以分為兩種不同的類別：沒有電話系統的使用者和具有電話系統的使用者。 在將電話號碼從內部部署 Active Directory 中管理到雲端時，具有電話系統的使用者將會經歷暫時遺失電話語音的情況。 **建議您在開始大量使用者作業之前，先使用少量的使用者與電話系統執行試驗。** 在大型部署中，使用者可以在不同時間視窗的較小群組中處理。 

> [!NOTE] 
> 此程式最簡單的情況是具有相符 sip 位址及 UserPrincipalName 的使用者。 如果組織的使用者在這兩個屬性之間具有非符合性值，請特別注意，以順利進行轉換。

> [!NOTE]
> 如果您已設定自動語音應答或通話佇列的內部部署混合應用程式端點，請務必在解除委任商務用 Skype Server 之前，將這些端點移至 Microsoft 365。 如需詳細資訊，請參閱 [在解除您的內部部署環境之前遷移混合應用程式端點](decommission-move-on-prem-endpoints.md)。  


1. 確認下列內部部署商務用 Skype PowerShell Cmdlet 會傳回空的結果。 空的結果表示沒有使用者位於內部部署，且已移至 Microsoft 365 或已停用：

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. 執行下列內部部署商務用 Skype Server PowerShell Cmdlet 以匯出使用者資料，以記錄使用者的目前電話號碼 (LineUri) 、UserPrincipalName 及相關資訊：

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > 繼續開啟 SfbUserSettings.csv 的檔案，並確認所有使用者資料都已成功匯出之前。 建議保留此檔案的副本。  請勿在下列步驟中將此檔案用於處理使用者。 

3. 使用下列步驟建立包含一組使用者的檔案。 在第一組使用者成功完成之後，請繼續進行下一組使用者。 在下列範例中，會依字母順序選取使用者群組。 您可以依據符合您要處理使用者之方式的準則來篩選使用者。

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > 繼續開啟的 SfbUsers.csv 檔案，並確認已順利匯出使用者資料。 在稍後的步驟中，您將需要 LineUri (電話號碼) 、UserPrincipalName、SamAccountName 和 SipAddress。

4. 針對您準備更新的使用者集合，從 active Directory 中刪除與商務用 Skype Server 相關的屬性資訊。  此過程有兩個步驟，如下所示。

   > [!Important] 
   > 在執行此步驟後的下一個 AAD 同步週期後，已從內部部署商務用 Skype Server 移至雲端的電話系統使用者將無法進行呼叫，直到步驟8成功完成並確認步驟9中。 此外，請確定您已將使用者的電話號碼和相關資訊儲存為步驟2，因為該步驟需要該資訊。

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   接下來，針對同一組使用者，使用內部部署 Active Directory PowerShell: 清除 msRTCSIP-DeploymentLocator 的值

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. 若要將 sip 位址值新增回內部部署 Active directory proxyAddresses，請在 Windows PowerShell Cmdlet 中執行下列內部部署 active directory 模組。 此巨集指令可防止依賴此屬性的互通性問題。 

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
     $userUpn=$user.UserPrincipalName
     $userSip=$user.SipAddress
     $proxies=Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" -properties * | Select-Object @{Name="proxyAddresses";Expression={$_.proxyAddresses}}
     if(($null -eq $proxies) -or ($proxies.proxyAddresses -NotContains $userSip))
     {
             Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" | Set-ADUser -Add @{"proxyAddresses"=$user.SipAddress}
     }
   }
   ```

6. 執行 Azure AD 同步

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. 等候使用者布建完成。 您可以執行下列 Teams PowerShell 命令，以監視使用者布建進度。 下列 Teams PowerShell 命令會在很快處理常式完成時傳回空的結果。

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. 若要指派電話號碼並為使用者啟用電話系統，請執行下列 Teams PowerShell 命令：


   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   if($user.LineUri)
        {
             Set-CsPhoneNumberAssignment -Identity $user.SipAddress -PhoneNumber $user.LineUri.Replace("tel:","") -PhoneNumberType DirectRouting
        }
   }
   ```

   > [!Note]
   >  如果您仍然有商務用 Skype 端點 (Skype 用戶端或協力廠商電話) ，您也要將 HostedVoiceMail 設定為 $true。 如果您的組織只對啟用語音的使用者使用 Teams 端點，則此設定不適用於您的使用者。 

9. 確認已正確布建電話系統功能的使用者。 下列 Teams PowerShell 命令會在很快處理常式完成時傳回空的結果。

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers)
   {
   if($user.LineUri)
        {
                $u=Get-CsOnlineUser -Identity $user.SipAddress
                if ($u.LineURI -ne $user.LineUri -or $u.EnterpriseVoiceEnabled -ne $true)
                {
                Get-CsOnlineUser -Identity $user.SipAddress | fl SipAddress, InterpretedUserType, OnPremLineURI, LineURI, EnterpriseVoiceEnabled, HostedVoicemail
                }
        }
   }
   ``` 

10. 重複步驟3到9，直到處理所有使用者為止。

11. 執行下列兩個 PowerShell 命令，確認已成功處理所有使用者。

    內部部署商務用 Skype Server 內部部署 PowerShell 命令：

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 

    Teams PowerShell 命令：

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 

12. 在方法2中完成所有步驟之後，請參閱[將混合應用程式端點從內部部署移至線上](decommission-move-on-prem-endpoints.md)，並[移除內部部署商務用 Skype Server](decommission-remove-on-prem.md) ，以取得其他步驟，以移除您的商務用 Skype Server 內部部署。


## <a name="see-also"></a>另請參閱

- [Teams 與商務用 Skype 的雲整合](cloud-consolidation.md)

- [解除您的內部部署商務用 Skype 環境](decommission-on-prem-overview.md)

