---
title: 使用 Exchange 內部部署來部署 Microsoft 團隊聊天室
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: 請閱讀本主題，以瞭解如何使用 Exchange 內部部署在混合式環境中部署 Microsoft 團隊聊天室的相關資訊。
ms.openlocfilehash: f9f80f5b993b9be95e35c8178d996973558e2512
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662318"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>使用 Exchange 內部部署來部署 Microsoft 團隊聊天室

請閱讀本主題，瞭解如何使用 Exchange 內部部署、Microsoft 團隊或商務用 Skype Online，在混合式環境中部署 Microsoft 團隊聊天室。
  
如果您的組織有混合服務、部分裝載于內部部署和部分託管的網路，則您的設定將取決於託管每個服務的位置。 本主題涵蓋 Microsoft 團隊聊天室的混合式部署，Exchange 託管于內部部署。 因為這種類型的部署有這麼多不同的變化，所以不可能提供所有專案的詳細指示。 下列處理常式適用于許多設定。 如果程式不適合您的設定，建議您使用 Windows PowerShell 來取得與其他部署選項相同的最終結果。

Microsoft 提供 [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)、可協助您建立新使用者帳戶的腳本，或驗證現有的資源帳戶，以協助您將它們轉換成相容的 Microsoft 團隊聊天室使用者帳戶。 如果您想要的話，您可以依照下列步驟來設定您的 Microsoft 團隊聊天室裝置將會使用的帳戶。
  
## <a name="requirements"></a>需求

在使用 Exchange 內部部署部署 Microsoft 團隊聊天室之前，請確定您已滿足需求。 如需詳細資訊，請參閱 [Microsoft 團隊會議室需求](requirements.md)。
  
如果您是使用 Exchange 內部部署來部署 Microsoft 團隊聊天室，您將會使用 Active Directory 系統管理工具來為您的內部部署網域帳戶新增電子郵件地址。 此帳戶將會同步處理至 Microsoft 365 或 Office 365。 您將需要：
  
- 建立帳戶並將帳戶與 Active Directory 同步處理。

- 啟用遠端信箱並設定屬性。

- 指派 Microsoft 365 或 Office 365 授權。

- 在商務用 Skype Server 上啟用裝置帳戶。 若要啟用裝置帳戶，您的環境必須符合下列先決條件：

  - 您必須在 Microsoft 365 或 Office 365 方案中，將商務用 Skype Online (方案 2) 或更新版本。 方案需要支援會議功能。
  
  - 如果您需要企業語音 (PSTN 電話) 使用 windows 版商務用 Skype Online 的電話服務提供者，請 (方案 3) 。
  
  - 您的租使用者必須有 Exchange 信箱。
  
  - 您的 Microsoft 團隊會議室帳戶需要商務用 Skype Online (方案 2) 或商務用 Skype Online (方案 3) 授權，但不需要 Exchange Online 授權。

- 將商務用 Skype Server 授權指派給您的 Microsoft 團隊聊天室帳戶。

### <a name="create-an-account-and-synchronize-with-active-directory"></a>建立帳戶並與 Active Directory 同步處理

1. 在 [ **Active Directory 使用者和電腦** ] 工具中，以滑鼠右鍵按一下您要在其中建立 Microsoft 團隊房間帳戶的資料夾或組織單位，按一下 [ **新增**]，然後按一下 [ **使用者**]。

2. 在 [ **完整名稱** ] 方塊中輸入上一個 Cmdlet 的顯示名稱，然後在 [ **使用者登入名稱** ] 方塊中輸入別名。 按一下 **[下一步]**。

3. 輸入此帳戶的密碼。 您必須重新輸入，才能進行驗證。 確認 [ **密碼永不過期** ] 核取方塊是唯一選取的選項。

    > [!NOTE]
    > 選取 [ **密碼永不過期** ] 是 Microsoft 團隊聊天室的商務用 Skype 伺服器需求。 您的網域規則可能會禁止沒有過期的密碼。 如果是這樣，您將需要針對每個 Microsoft 團隊聊天室裝置帳戶建立例外狀況。
  
4. 建立帳戶之後，請執行目錄同步處理。 完成後，請移至 Microsoft 365 系統管理中心的 [使用者] 頁面，確認在先前步驟中建立的帳戶已合併至 [線上]。

### <a name="enable-the-remote-mailbox-and-set-properties"></a>啟用遠端信箱並設定屬性

1. [開啟 Exchange 管理命令](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) 介面或 [使用遠端 PowerShell 連線至您的 Exchange 伺服器](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)。

2. 在 Exchange PowerShell 中， (信箱建立信箱，方法是執行下列命令以啟用帳戶) ：

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   如需詳細的語法與參數資訊，請參閱 [啟用-信箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox)。

3. 在 Exchange PowerShell 中，設定會議室信箱上的下列設定，以改善會議體驗：

   - AutomateProcessing： AutoAccept (會議召集人直接在沒有人工干預的情況下收到會議室保留決策：閑 = 接受;忙碌 = 拒絕. ) 

   - AddOrganizerToSubject： $false (會議召集人不會新增至會議邀請的主旨。 ) 

   - DeleteComments： $false (保留傳入會議邀請郵件內文中的任何文字。 ) 

   - DeleteSubject： $false (保持收到的會議邀請主題。 ) 

   - RemovePrivateProperty： $false (可確保在原始會議邀請中由會議召集人所傳送的私人標誌保持為已指定。 ) 

   - AddAdditionalResponse： $true (會將 AdditionalResponse 參數指定的文字新增至會議邀請。 ) 

   - AdditionalResponse：「這是 Skype 會議室！」  (要新增至會議邀請的其他文字。 ) 

   這個範例會在名為 Project-Rigel-01 的聊天室信箱上設定這些設定。

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   如需詳細的語法與參數資訊，請參閱 [設定 CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)。

### <a name="assign-a-microsoft-365-or-office-365-license"></a>指派 Microsoft 365 或 Office 365 授權

1. 連線至 Azure Active Directory。 如需 Active Directory 的詳細資料，請參閱 [Azure ActiveDirectory (import-module msonline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)。 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) 不受支援。 

2. 裝置帳戶必須具備有效的 Microsoft 365 或 Office 365 授權，否則 Exchange 與 Microsoft 團隊將無法運作。 如果您有授權，您必須將使用位置指派給您的裝置帳戶，這會決定您的帳戶可使用哪些授權 Sku。 您可以使用 `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> 以取得可用的 Sku 清單。

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. 接下來，您可以使用 `Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> Cmdlet. 在此案例中，$strLicense 是您所看到的 SKU 程式碼 (例如 contoso： STANDARDPACK) 。

  ``` PowerShell
  Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
  Get-MsolAccountSku
  Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```

<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```  -->

   如需詳細指示，請參閱 [使用 Office 365 PowerShell 指派授權給使用者帳戶](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)。

### <a name="enable-the-device-account"></a>啟用裝置帳戶

商務用 skype Online PowerShell 是用來管理 Microsoft 團隊和商務用 Skype Online 的服務。

1. 從電腦建立遠端 Windows PowerShell 會話，如下所示：
> [!NOTE]
> 商務用 Skype Online 連接器目前是最新團隊 PowerShell 模組的一部分。
>
> 如果您使用的是最新的 [團隊 PowerShell 公開發行](https://www.powershellgallery.com/packages/MicrosoftTeams/)，就不需要安裝商務用 Skype Online 連接器。

   ``` Powershell
   Import-Module -Name MicrosoftTeams  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. 取得帳戶的 SIP 位址：

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. 若要啟用您的 Microsoft 團隊聊天室帳戶，請執行此命令：

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   如果您不確定要在您的環境中使用 RegistrarPool 參數的值，您可以使用此命令從現有的使用者取得值：

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a>將授權指派給您的 Microsoft 團隊聊天室帳戶

1. 以租使用者管理員身分登入，開啟 Microsoft 365 系統管理中心，然後按一下 [管理] 應用程式。
2. 按一下 [ **使用者和群組** ]，然後按一下 [ **新增使用者、重設密碼等等**]。
3. 按一下 [Microsoft 團隊聊天室] 帳戶，然後按一下手寫筆圖示，即可編輯帳戶資訊。
4. 按一下 [ **授權**]。
5. 在 [ **指派授權**] 中，選取 [商務用 Skype (方案 2]) 或 [商務用 skype] (方案 3) ，視您的授權和企業語音需求而定。 如果您想要在 Microsoft 團隊聊天室使用企業語音，您必須使用 [方案3授權]。
6. 按一下 [儲存]。

針對驗證，您應該可以使用任何用戶端登入此帳戶。
  
## <a name="related-topics"></a>相關主題

[設定 Microsoft 團隊聊天室的帳戶](rooms-configure-accounts.md)

[規劃 Microsoft Teams 會議室](rooms-plan.md)
  
[部署 Microsoft Teams 會議室](rooms-deploy.md)
  
[設定 Microsoft Teams 會議室主控台](console.md)
  
[管理 Microsoft Teams 會議室](rooms-manage.md)
