---
title: 停用混合式完成僅限 Teams 的遷移
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
localization_priority: Normal
description: 本文包含停用混合成 Teams 和商務用 Skype 之雲端合併的一部分的詳細步驟。
ms.openlocfilehash: 97681f4e9306336874ba4d9428a273b1d31519db
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420838"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-teams-only"></a>停用混合式設定，僅完成 Teams 的遷移 

本文說明如何在解除您的內部部署商務用 Skype 環境之前停用混合式設定。 這是下列步驟的步驟2，以解除委任您的內部部署環境：

- 步驟 1. [將所有必要使用者從內部部署移至線上](decommission-move-on-prem-users.md)。

- **步驟2。停用您的混合式設定。**  (本文) 

- 步驟 3. [從內部部署向線上遷移混合應用程式端點](decommission-move-on-prem-endpoints.md)。

- 步驟 4： [移除您的內部部署商務用 Skype 部署](decommission-remove-on-prem.md)。

> [!NOTE]
> 步驟2和3應該在相同維護視窗中進行，因為任何現有的混合應用程式端點在步驟2和步驟3完成之間不會發現。

## <a name="overview"></a>概觀

將所有使用者從商務用 Skype 內部部署升級至僅 Microsoft 365 中 Teams 後，您就可以解除委任內部部署商務用 Skype 部署。 在您解除委任內部部署商務用 Skype 部署和移除任何硬體之前，您必須以邏輯方式從 Microsoft 365 中停用內部部署，方法是停用混合式。 停用混合式包含下列四個步驟：

1. 更新 DNS 記錄，使它指向 Microsoft 365。

2. 將您組織的共存模式變更為 [Teams]。

3. 停用 Microsoft 365 組織中的共用 sip 位址空間 (也稱為「分割網域」 ) 。

4. 停用內部部署中與 Microsoft 365 通訊的功能。

這些步驟會以邏輯方式將您的內部部署商務用 Skype Server 從 Microsoft 365 中部署，並確保您的組織完全 Teams。 本文提供每個步驟的詳細資料。 完成之後，您可以使用下列兩種方法之一來解除委任內部部署商務用 Skype 部署。

> [!Important] 
> 完成此邏輯分隔之後，來自內部部署 Active Directory 的 msRTCSIP 屬性仍然具有值，而且會繼續透過 Azure AD 連線同步處理到 Azure AD。 如何解除委任內部部署環境取決於您想要將這些屬性保留在原處，還是先從您的內部部署 Active Directory 加以清除。 請注意，在您從內部部署遷移之後清除內部部署 msRTCSIP 屬性，可能會導致使用者的服務遺失！ 稍後會說明兩個解除委任方法的詳細資料和折衷。

## <a name="detailed-steps"></a>詳細步驟

1. *更新 DNS 以指向 Microsoft 365。* 組織的外部 DNS 必須更新內部部署組織，使商務用 Skype 記錄指向 Microsoft 365 而非內部部署。 特別是：

    |Record type (記錄類型)|名稱|TTL|Priority (優先順序)|Weight (權數)|Port (連接埠)|Value (值)|
    |---|---|---|---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100|1 |5061|<span>sipfed。Com|
    |SRV|_sip._tls|3600|100|1 |443|<span>sipdir。Com|
    |CNAME| lyncdiscover|   3600| | | |<span>webdir。Com|
    |CNAME| sip|    3600| | | | <span>sipdir。Com|

    此外，如果存在) 可刪除，則為符合或撥入 (的 CNAME 記錄。 最後，您應該移除內部網路中商務用 Skype 的任何 DNS 記錄。

    > [!Note] 
    > 在極少的情況下，將 DNS 設定為組織的內部部署與 Microsoft 365，可能會造成其他一些組織的同盟停止運作，直到其他組織更新其同盟設定為止：
    >
    > - 任何使用舊版直接同盟模型的同盟組織 (又稱為允許的夥伴伺服器) ，都必須更新其組織的允許網域專案，以移除 proxy FQDN。 這種舊版同盟模型不是以 DNS SRV 記錄為基礎，因此當您的組織移至雲端時，此設定將會到期。
    > 
    > - 任何沒有啟用 sipfed <span> 之主機服務提供者的同盟組織。com 必須更新其設定，才能啟用該功能。 只有在同盟組織完全存在於內部部署，且決不會與任何混合式或線上租使用者同盟的情況下，才可能出現這種情況。 在此情況下，與這些組織的同盟必須啟用其主機服務提供者後，才能運作。
    >
    > 如果您懷疑任何同盟協力廠商可能使用的是直接同盟或尚未與任何線上或混合組織同盟，我們建議您在準備完成對雲端的遷移時，向他們傳送此資訊的通訊。

2.  *將您組織的共存模式變更為 [Teams]。* 這可確保您組織中的任何新使用者永遠都建立為僅 Teams 使用者。 此外，嘗試將租使用者模式變更為 Teams 只會自動檢查是否存在步驟1中已錯過的任何內部部署 DNS 記錄，並在輸出中識別這些記錄。  只有在更新 organizaiton 的所有 DNS 記錄之後，才能將租使用者模式變更為 Teams 才會失敗。 若要將租使用者模式變更為 Teams 只從 Teams PowerShell] 視窗執行下列命令。

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
     ```
或者，您也可以使用 Teams 系統管理中心，將租使用者共存模式變更為 TeamsOnly，在 [整個組織設定] 下，> "Teams Upgrade]。    
    
3.  *停用 Microsoft 365 組織中的共用 sip 位址空間。* 以下的命令必須從 Teams PowerShell] 視窗中完成。

     ```PowerShell
     Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
     ```
 
4.  *停用內部部署中與 Microsoft 365 通訊的功能。* 以下是必須從內部部署 PowerShell 視窗執行的命令：

     ```PowerShell
     Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
     ```

## <a name="managing-attributes-after-moving-users-from-on-premises-to-the-cloud"></a>在將使用者從內部部署移至雲端之後管理屬性

根據預設，先前為商務用 Skype Server 啟用之後又移至雲端的所有使用者，仍然會在您的內部部署 Active Directory 中設定 msRTCSIP 屬性。 這些屬性在特定 sip 位址 (msRTCSIP-PrimaryUserAddress) 和可能的電話號碼 (msRTCSIP 行) ，請繼續同步處理至 Azure AD。 如果需要變更任何 msRTCSIP 屬性，必須在內部部署 Active Directory 中進行這些變更，然後同步處理至 Azure AD。 不過，商務用 Skype Server 部署已移除之後，就無法使用商務用 Skype Server 工具來管理這些屬性。

有兩個選項可用於處理這種情況：

1. 保留已為商務用 Skype 伺服器帳戶啟用的使用者，並使用 Active Directory 工具管理 msRTCSIP 屬性。 這可確保已遷移使用者沒有服務遺失，而且可讓您透過消除 (（例如，擦除) 伺服器，而不需完全退役）來輕鬆移除商務用 Skype Server 部署。 不過，新授權的使用者將不會在您的內部部署 Active Directory 中填入這些屬性，且必須在線上進行管理。

2.  從內部部署 Active Directory 中已遷移的使用者清除所有 msRTCSIP 屬性，並使用線上工具管理這些屬性。 這個方法可讓現有和新使用者使用一致的管理方法，但在內部部署解除委任程式中，可能會導致服務暫時遺失。


### <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a>方法 1-管理 Active Directory 中使用者的 sip 位址和電話號碼

管理員可以管理先前已從內部部署商務用 Skype Server 移至雲端的使用者，即使已解除內部部署的部署也是一樣。 若要變更使用者的 sip 位址或使用者的電話號碼 (而且 sip 位址或電話號碼在內部部署 Active Directory) 中已有值，您必須在內部部署 Active Directory 中執行這項作業，並讓) 流向 Azure AD 的值 (s。 這不需要內部部署商務用 Skype Server。 相反地，您可以使用 Active Directory 使用者和電腦 MMC 嵌入式管理單元來直接修改內部部署 Active Directory 中的這些屬性 (，如) 所示，或是使用 PowerShell。 如果您使用的是 MMC 嵌入式管理單元，請開啟使用者的 [屬性] 頁面，按一下 [屬性編輯器] 索引標籤，然後尋找適當的屬性進行修改：

- 若要修改使用者的 sip 位址，請修改 `msRTCSIP-PrimaryUserAddress` 。

    > [!NOTE]
    > 如果 `ProxyAddresses` 屬性包含 sip 位址，也會將此值更新為最佳作法。 雖然所填入的 sip 位址 `ProxyAddresses` 已在 O365 中忽略，但 `msRTCSIP-PrimaryUserAddress` 其他內部部署元件也可以使用它。

- 若要修改使用者的電話號碼，請修改 `msRTCSIP-Line` *是否已有值*。

  ![Active Directory 使用者和電腦工具](../media/disable-hybrid-1.png)
  
-  如果使用者在 `msRTCSIP-Line` 移動之前沒有內部部署的值，您可以使用 `onpremLineUri` 商務用 Skype 線上 PowerShell 模組中[Set-CsUser Cmdlet](/powershell/module/skype/set-csuser?view=skype-ps)中的-參數修改電話號碼。

在您停用混合式之後所建立的新使用者，這些使用者不需要這些步驟，而且可以直接在雲端中管理這些使用者。 如果您習慣使用這些方法的組合，以及在內部部署 Active Directory 中就地保留 msRTCSIP 屬性，則可以直接重新鏡像內部部署商務用 Skype 伺服器。 不過，如果您想要清除所有 msRTCSIP 屬性，並執行商務用 Skype Server 的傳統卸載，請使用方法2。


### <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a>方法 2-清除 Active Directory 中所有內部部署使用者的商務用 Skype 屬性

這個選項需要額外的工作量並適當地規劃，因為先前已從內部部署商務用 Skype Server 移至雲端的使用者需要重新布建。 這些使用者可以分為兩種不同的類別：沒有電話系統的使用者和具有電話系統的使用者。 在將電話號碼從內部部署 Active Directory 中管理到雲端時，具有電話系統的使用者將會經歷暫時遺失電話語音的情況。 **建議您在開始大量使用者作業之前，先使用少量的使用者與電話系統執行試驗。** 對於大型部署，使用者可以在不同時間視窗的較小群組中處理。 

> [!NOTE] 
> 此程式最簡單的情況是具有相符 sip 位址及 UserPrincipalName 的使用者。 如果組織的使用者在這兩個屬性之間具有非符合性值，請特別注意，以順利進行轉換。

> [!NOTE]
> 如果您已設定自動語音應答或通話佇列的內部部署混合應用程式端點，請務必在解除委任商務用 Skype Server 之前，將這些端點移至 Microsoft 365。


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

3. 使用下列步驟建立包含一組使用者的檔案。 在第一組使用者成功完成之後，請繼續進行下一組使用者。 在下列範例中，會依字母順序選取使用者群組，但您可以依據符合您要處理使用者之方式的準則來篩選使用者。

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > 繼續開啟的 SfbUsers.csv 檔案，並確認已順利匯出使用者資料。 在稍後的步驟中，您將需要 LineUri (電話號碼) 、UserPrincipalName、SamAccountName 和 SipAddress。

4. 針對您準備更新的使用者集合，從 active Directory 中刪除與商務用 Skype Server 相關的屬性資訊。  此處理程式有兩個步驟，如下所示。

   > [!Important] 
   > 在執行此步驟後的下一個 AAD 同步週期之後，具有先前從內部部署商務用 Skype Server 移至雲端的電話系統使用者將無法進行呼叫，直到步驟8成功完成並確認步驟9中。 此外，請確定您已將使用者的電話號碼和相關資訊儲存為步驟2，因為該步驟需要該資訊。

 
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

5. 針對 Windows PowerShell Cmdlet 執行下列內部部署 active directory 模組，將 sip 位址值新增回內部部署 Active directory proxyAddresses。 這會防止依賴此屬性的互通性問題。 

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

7. 等候使用者布建完成。 您可以執行下列商務用 Skype 線上 PowerShell 命令，以監視使用者布建進度。 下列商務用 Skype 線上 PowerShell 命令會在很快的處理常式完成時傳回空的結果。

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. 執行下列商務用 Skype 線上 PowerShell 命令指派電話號碼，並為使用者啟用電話系統：
     
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   if($user.LineUri)
        {
                Set-CsUser -Identity $user.SipAddress -OnPremLineURI $user.LineUri -EnterpriseVoiceEnabled $True
        }
   }
    ```

   > [!Note]
   >  如果您仍然有商務用 Skype 端點 (Skype 用戶端或協力廠商電話) ，您也會想要將 HostedVoiceMail 設定為 $true。 如果您的組織只對啟用語音的使用者使用 Teams 端點，則此設定不適用於您的使用者。 

9. 確認已正確布建電話系統功能的使用者。 下列商務用 Skype 線上 PowerShell 命令會在很快的處理常式完成時傳回空的結果。

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
    商務用 Skype線上 PowerShell 命令：

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 
12. 在方法2中完成所有步驟之後，請參閱[將混合應用程式端點從內部部署移至線上](decommission-move-on-prem-endpoints.md)，並[移除內部部署商務用 Skype Server](decommission-remove-on-prem.md) ，以取得其他步驟，以移除您的商務用 Skype Server 內部部署。


## <a name="see-also"></a>請參閱

- [Teams 與商務用 Skype 的雲整合](cloud-consolidation.md)

- [解除您的內部部署商務用 Skype 環境](decommission-on-prem-overview.md)

