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
description: 本文說明如何在解除委任內部部署環境之後管理屬性。
ms.openlocfilehash: b838b965430a007fa74320d7dbebdcf7ee36c3a9
ms.sourcegitcommit: 140c34f20f9cd48d7180ff03fddd60f5d1d3459f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2022
ms.locfileid: "65249015"
---
# <a name="decide-how-to-manage-attributes-after-decommissioning"></a>決定解除授權後如何管理屬性

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


根據預設，所有已啟用商務用 Skype Server，然後移至雲端的使用者，在您的內部部署的 Active Directory中仍會設定 msRTCSIP 屬性。 

這些屬性，特別是 msRTCSIP-PrimaryUserAddress)  (sip 位址，以及 msRTCSIP-Line)  (電話號碼，會繼續同步至Azure AD。 如果需要變更任何 msRTCSIP 屬性，則必須在內部部署的 Active Directory中進行這些變更，然後同步處理至Azure AD。 不過，移除商務用 Skype Server部署之後，商務用 Skype Server工具將無法管理這些屬性。

有兩個選項可用來處理這種情況：

1. 讓已啟用商務用 Skype伺服器帳戶的使用者保持原狀，並使用 Active Directory 工具管理 msRTCSIP 屬性。 此方法可確保移轉的使用者不會遺失服務，並可讓您移除 (，例如抹除) 伺服器，而不需要完全解除委任，以移除商務用 Skype Server部署。 不過，新授權的使用者不會在您的內部部署的 Active Directory中填入這些屬性，而且必須在線上管理。

2.  清除您內部部署的 Active Directory中已移轉使用者的所有 msRTCSIP 屬性，並使用線上工具管理這些屬性。 這個方法可讓現有和新使用者使用一致的管理方法。 不過，在內部部署解除委任程式期間，可能會導致服務暫時遺失。


## <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a>方法 1 - 管理 Active Directory 中使用者的 sip 位址和電話號碼

系統管理員可以管理從內部部署商務用 Skype Server移至雲端的使用者，即使在內部部署解除委任之後也一般。 

如果您想要變更使用者的 sip 位址或使用者的電話號碼 (，且 sip 位址或電話號碼在內部部署的 Active Directory) 中已經有值，您必須在內部部署的 Active Directory中進行變更，並讓 (的值) 流向Azure AD。 此方法不需要內部部署商務用 Skype Server。 相反地，您可以直接在內部部署的 Active Directory中修改這些屬性，使用Active Directory 消費者和電腦 MMC 嵌入式管理單元 (，如下) 所示，或使用 PowerShell。 如果您使用 MMC 嵌入式管理單元，請開啟使用者的 [屬性] 頁面，按一下 [屬性編輯器] 索引標籤，然後尋找要修改的適當屬性：

- 若要修改使用者的 sip 位址，請修改 `msRTCSIP-PrimaryUserAddress` 。

    > [!NOTE]
    > `ProxyAddresses`如果屬性包含 sip 位址，也請將該值更新為最佳做法。 雖然 O365 `msRTCSIP-PrimaryUserAddress` 會在填入時忽略 中的 sip 位址 `ProxyAddresses` ，但其他內部部署元件可能會使用它。

- 若要修改使用者的電話號碼，*如果已經有值，請* 修改 `msRTCSIP-Line` 。

  ![Active Directory 使用者和電腦工具。](../media/disable-hybrid-1.png)


- 如果使用者在移動之前原本沒有內部部署的值 `msRTCSIP-Line` ，您可以使用 `-PhoneNumber` Teams PowerShell 模組中[Set-CsPhoneNumberAssignment Cmdlet](/powershell/module/teams/set-csphonenumberassignment)中的 參數來修改電話號碼。

停用混合式之後建立的新使用者不需要執行這些步驟，而且可以直接在雲端中管理這些使用者。 如果您習慣使用這些方法的混合，並讓 msRTCSIP 屬性留在您的內部部署的 Active Directory中，您可以重新建立內部部署商務用 Skype伺服器的映射。 不過，如果您想要清除所有 msRTCSIP 屬性，並執行傳統的卸載商務用 Skype Server，請使用方法 2。


## <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a>方法 2 - 清除 Active Directory 中所有內部部署使用者的商務用 Skype屬性

此選項需要更多心力和適當的規劃，因為從內部部署商務用 Skype Server移至雲端的使用者必須重新布建。 這些使用者可以分類為兩個不同的類別：沒有電話系統的使用者和具有電話系統的使用者。 具有電話系統的使用者會在將電話號碼從內部部署的 Active Directory管理轉換為雲端時，遇到暫時遺失電話語音的情況。 **建議您在開始大量使用者作業之前，先執行涉及少數具有電話系統使用者的試驗。** 針對大型部署，使用者可以在不同的時間範圍中以較小的群組進行處理。 

> [!NOTE] 
> 對於具有相符 sip 位址和 UserPrincipalName 的使用者而言，此程式最簡單。 對於具有這兩個屬性中值不相符之使用者的組織，必須特別小心，如下所述，才能順利轉換。

> [!NOTE]
> 如果您已針對自動語音應答或通話佇列設定內部部署混合式應用程式端點，請務必先將這些端點移至Microsoft 365，再解除委任商務用 Skype Server。 如需詳細資訊，請參閱在 [解除委任內部部署環境之前移轉混合式應用程式端點](decommission-move-on-prem-endpoints.md)。  


1. 確認下列內部部署商務用 Skype PowerShell Cmdlet 會傳回空白結果。 空白的結果表示沒有任何使用者位於內部部署，且已移至Microsoft 365或已停用：

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. 執行下列內部部署商務用 Skype Server PowerShell Cmdlet 來匯出使用者資料，以記錄使用者目前的電話號碼 (LineUri) 、UserPrincipalName 和相關資訊：

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > 繼續開啟SfbUserSettings.csv檔案，並確認已成功匯出所有使用者資料。 建議您保留此檔案的複本。  請勿在下列步驟中使用此檔案來處理使用者。 

3. 建立檔案，其中包含要在下列步驟中使用的使用者群組。 成功完成第一個使用者群組之後，請繼續進行下一個使用者群組。 在下列範例中，會依字母順序選取使用者群組。 您可以根據符合您想要處理使用者之方式的準則來篩選使用者。

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > 在繼續開啟SfbUsers.csv檔案並確認使用者資料已成功匯出之前。 在稍後的步驟中，您將需要此檔案中的 LineUri (電話號碼) 、UserPrincipalName、SamAccountName 和 SipAddress。

4. 針對您已準備好更新的使用者集，從 active Directory 刪除與商務用 Skype Server相關的屬性資訊。  此程式有兩個步驟，如下所示。

   > [!Important] 
   > 執行此步驟之後的下一個AAD 同步迴圈之後，具有從內部部署商務用 Skype Server移至雲端之電話系統的使用者將無法撥打和接聽電話，直到步驟 8 順利完成，並在步驟 9 中確認為止。 此外，請確定您已根據步驟 2 儲存使用者的電話號碼和相關資訊，因為該步驟需要該資訊。

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   接下來，針對同一組使用者，使用 內部部署的 Active Directory PowerShell 清除 msRTCSIP-DeploymentLocator 的值：

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. 若要將 sip 位址值新增至 內部部署的 Active Directory proxyAddresses，請執行下列 內部部署的 Active Directory Module for Windows PowerShell Cmdlet。 此動作可防止依賴此屬性的互通性問題。 

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

6. 執行Azure AD 同步

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. 等候使用者布建完成。 您可以執行下列 Teams PowerShell 命令來監視使用者布建進度。 下列Teams PowerShell 命令會在程式完成時傳回空的結果。

   ```PowerShell
   Get-CsOnlineUser -Filter {IsSipEnabled -eq $True} | Where UserValidationErrors -ne $null | Select SipAddress,InterpretedUserType,UserValidationErrors
   ```

8. 若要指派電話號碼並啟用使用者電話系統，請執行下列Teams PowerShell 命令：


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
   >  如果您仍有商務用 Skype端點 (Skype用戶端或協力廠商電話) ，您也會想要將 -HostedVoiceMail 設定為 $true。 如果您的組織只針對啟用語音功能的使用者使用Teams端點，則此設定不適用於您的使用者。 

9. 確認已正確布建具有電話系統功能的使用者。 下列Teams PowerShell 命令會在程式完成時傳回空的結果。

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers)
   {
   if($user.LineUri)
        {
                $u=Get-CsOnlineUser -Identity $user.SipAddress
                if ($u.LineURI -ne $user.LineUri -or $u.EnterpriseVoiceEnabled -ne $true)
                {
                Get-CsOnlineUser -Identity $user.SipAddress | fl SipAddress, InterpretedUserType, OnPremLineURI, LineURI, EnterpriseVoiceEnabled
                }
        }
   }
   ``` 

10. 重複步驟 3 到 9，直到處理所有使用者為止。

11. 執行下列兩個 PowerShell 命令，確認已成功處理所有使用者。

    內部部署商務用 Skype Server內部部署 PowerShell 命令：

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 

    Teams PowerShell 命令：

    ```PowerShell
    Get-CsOnlineUser -Filter {IsSipEnabled -eq $True} | where {UserValidationErrors -ne $null} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, UserValidationErrors
    ``` 

12. 完成方法 2 中的所有步驟之後，請參閱將[混合式應用程式端點從內部部署移至線上](decommission-move-on-prem-endpoints.md)和[移除內部部署商務用 Skype Server](decommission-remove-on-prem.md)，以取得移除商務用 Skype Server內部部署的其他步驟。


## <a name="see-also"></a>另請參閱

- [Teams和商務用 Skype的雲端匯總](cloud-consolidation.md)

- [解除您的內部部署商務用 Skype 環境](decommission-on-prem-overview.md)

