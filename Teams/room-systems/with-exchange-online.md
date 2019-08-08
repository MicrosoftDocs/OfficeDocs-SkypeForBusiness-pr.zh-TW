---
title: 使用 Exchange Online 部署 Microsoft 團隊聊天室
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: 如需如何使用 Exchange Online 部署 Microsoft 團隊聊天室的詳細資訊, 請參閱本主題。
ms.openlocfilehash: 2d75e3e744f19d5bce6f323a2f80be8fd836bd61
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243242"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>使用 Exchange Online 部署 Microsoft 團隊聊天室

請閱讀本主題, 瞭解如何使用 Exchange Online 和商務用 Skype Server 內部部署來部署 Microsoft 團隊聊天室。
  
如果您的組織有混合服務、部分裝載于內部部署和部分託管的網路, 則您的設定將取決於託管每個服務的位置。 本主題涵蓋 Microsoft 團隊聊天室的混合式部署, 以及 Exchange 託管在線上。 因為這種類型的部署有這麼多不同的變化, 所以不可能提供所有專案的詳細指示。 下列處理常式適用于許多設定。 如果程式不適合您的設定, 建議您使用 Windows PowerShell 來取得與其他部署選項相同的最終結果。

設定使用者帳戶最簡單的方法, 就是使用遠端 Windows PowerShell 進行設定。 Microsoft 提供[SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105), 此腳本將協助您建立新的使用者帳戶, 或驗證您所擁有的現有資源帳戶, 以協助您將它們轉換成相容的 Microsoft 團隊聊天室使用者帳戶。 如果您想要的話, 您可以依照下列步驟來設定您的 Microsoft 團隊聊天室裝置將會使用的帳戶。

## <a name="requirements"></a>需求

在使用 Exchange Online 部署 Microsoft 團隊聊天室之前, 請確定您已滿足需求。 如需詳細資訊, 請參閱[Microsoft 團隊會議室需求](requirements.md)。
  
若要使用 Exchange Online 部署 Microsoft 團隊聊天室, 請遵循下列步驟。 請確定您有正確的許可權來執行相關的 Cmdlet。 

   > [!NOTE]
   >  此區段中的[Windows PowerShell Cmdlet 的 Azure Active Directory 模組](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)(例如, MsolUser) 已在設定 Microsoft 團隊聊天室裝置的帳戶中經過測試。 但其他 Cmdlet 可能可以運作, 但在這種特定情況下並未經過測試。
  
### <a name="create-an-account-and-set-exchange-properties"></a>建立帳戶並設定 Exchange 屬性

1. 在 PC 上啟動遠端 Windows PowerShell 會話, 並聯機至 Exchange Online, 如下所示:

``` Powershell
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
```

2. 建立會話之後, 您可以建立新的信箱並將其設為 RoomMailboxAccount, 或變更現有會議室信箱的設定。 這可讓帳戶在 Microsoft 團隊聊天室中進行驗證。

   如果您要變更現有的資源信箱:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    如果您要建立新的資源信箱:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 若要改善會議體驗, 您必須在使用者帳戶上設定 Exchange 屬性, 如下所示:

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```



### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>新增內部部署網域帳戶的電子郵件地址

1. 在**Active Directory 使用者和電腦廣告**工具中, 以滑鼠右鍵按一下您的 Microsoft 小組會議室帳戶將會在其中建立的容器或組織單位, 按一下 [**新增**], 然後按一下 [**使用者**]。
2. 從先前的 Cmdlet (將 [信箱] 或 [新信箱]) 中輸入 [顯示名稱] (身分識別) 至 [**完整名稱**] 方塊, 然後輸入別名至 [**使用者登入名稱**] 方塊。 按一下 **[下一步]**。
3. 輸入此帳戶的密碼。 您必須重新輸入, 才能進行驗證。 確認 [**密碼永不過期**] 核取方塊是唯一選取的選項。

    > [!NOTE]
    > 選取 [**密碼永不過期**] 是 Microsoft 團隊聊天室的商務用 Skype 伺服器需求。 您的網域規則可能會禁止沒有過期的密碼。 如果是這樣, 您將需要針對每個 Microsoft 團隊聊天室使用者帳戶建立例外狀況。
  
4. 按一下 **[完成]** 來建立帳戶。
5. 在您建立帳戶之後, 請執行目錄同步處理。 這可以透過在 PowerShell 中使用[Set MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0)來完成。 完成後, 請移至 [使用者] 頁面, 確認先前步驟中建立的兩個帳戶已合併。

### <a name="assign-an-office-365-license"></a>指派 Office 365 授權

1. 首先, 連線到 Azure AD 來套用某些帳戶設定。 您可以執行此 Cmdlet 來進行連線。 如需 Active Directory 的詳細資訊, 請參閱[Azure ActiveDirectory (import-module msonline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0)。 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0)不受支援。 

  ``` PowerShell
 Connect-MsolService -Credential $cred
  ```
<!--   ``` Powershell
   Connect-AzureAD -Credential $cred
   ``` -->

2. 使用者帳戶必須擁有有效的 Office 365 授權, 以確保 Exchange 和商務用 Skype 伺服器能夠正常運作。 如果您有授權, 您必須將使用位置指派給您的使用者帳戶, 這會決定您的帳戶可使用哪些授權 Sku。 您將會在下列步驟中進行作業。
3. 接下來, 使用`Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> 若要為您的 Office 365 租使用者取得可用的 Sku 清單。
4. 當您列出 Sku 之後, 您就可以使用`Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> Cmdlet. 在此情況下, $strLicense 是您所看到的 SKU 程式碼 (例如 contoso: STANDARDPACK)。 

  ```
    Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```
<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a>使用商務用 Skype Server 啟用使用者帳戶

1. 從電腦建立遠端 Windows PowerShell 會話, 如下所示:

    ``` Powershell
    Import-Module SkypeOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. 若要啟用商務用 Skype Server 的 Microsoft 團隊房間帳戶, 請執行此命令:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    如果您不確定要在您的環境中使用 RegistrarPool 參數的值, 您可以使用此命令從現有的商務用 Skype Server 使用者取得該值

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a>將商務用 Skype Server 授權指派給您的 Microsoft 團隊聊天室帳戶

1. 以租使用者管理員身分登入, 開啟 Office 365 系統管理中心入口網站, 然後按一下 [管理] 應用程式。
2. 按一下 [**使用者和群組**], 然後按一下 [**新增使用者、重設密碼等等**]。
3. 按一下 [Microsoft 團隊聊天室] 帳戶, 然後按一下手寫筆圖示, 即可編輯帳戶資訊。
4. 按一下 [**授權**]。
5. 在 [**指派授權**] 中, 選取 [商務用 Skype (方案 2)] 或 [商務用 Skype (方案 3)], 視您的授權和企業語音需求而定。 如果您想要在 Microsoft 團隊聊天室使用企業語音, 就必須使用 [方案3授權]。
6. 按一下 [**儲存**]。

針對驗證, 您應該能夠使用任何商務用 Skype 用戶端登入此帳戶。
  
## <a name="see-also"></a>另請參閱

[設定 Microsoft 團隊聊天室的帳戶](room-systems-v2-configure-accounts.md)

[規劃 Microsoft 團隊聊天室](skype-room-systems-v2-0.md)
  
[部署 Microsoft 團隊聊天室](room-systems-v2.md)
  
[設定 Microsoft 團隊聊天室主控台](console.md)
  
[管理 Microsoft 團隊聊天室](skype-room-systems-v2.md)
