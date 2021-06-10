---
title: 使用Microsoft Teams 會議室部署Exchange部署
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
description: 請參閱本主題，瞭解如何在混合式環境中部署Microsoft Teams 會議室內部部署Exchange部署。
ms.openlocfilehash: 3931ba89dd4ad0dfd994fdf27a3f209275850116
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117351"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>在Microsoft Teams 會議室部署Exchange部署

請閱讀本主題，瞭解如何在混合式環境中Microsoft Teams 會議室內部部署Exchange內部部署或Microsoft Teams商務用 Skype部署。
  
如果貴組織有混合式服務，其中一些是內部部署，有些是線上託管，則您的組式取決於每個服務的託管位置。 本主題涵蓋內部部署Microsoft Teams 會議室Exchange的混合式部署。 由於這類部署有許多不同的變化，因此無法針對所有部署提供詳細指示。 下列程式適用于許多配置。 如果此程式不適用於您的設定，建議您使用 Windows PowerShell來達到此處所記載的相同最終結果，以及其他部署選項。

Microsoft 提供[SkypeRoomProvisioningScript.ps1，](https://go.microsoft.com/fwlink/?linkid=870105)此腳本可協助建立新的使用者帳戶，或驗證您現有的資源帳戶，以便協助您將這些帳戶轉換為Microsoft Teams 會議室使用者帳戶。 您可以按照下列步驟來設定您的裝置Microsoft Teams 會議室帳戶。
  
## <a name="requirements"></a>需求

在內部Microsoft Teams 會議室部署Exchange，請確定您符合需求。 詳細資訊，請參閱Microsoft Teams 會議室[需求](requirements.md)。
  
如果您要在內部Microsoft Teams 會議室部署Exchange，您將使用 Active Directory 管理工具為您的內部部署網域帳戶新增電子郵件地址。 此帳戶會同步到 Microsoft 365 或 Office 365。 您必須：
  
- 建立帳戶，然後與 Active Directory 同步處理帳戶。

- 啟用遠端信箱並設定屬性。

- 指派授權Microsoft 365或Office 365授權。

- 啟用裝置帳戶商務用 Skype Server。 若要啟用裝置帳戶，您的環境必須符合下列先決條件：

  - 您必須在方案或商務用 Skype中 (2) 或更Microsoft 365 Office 365方案。 該計畫需要支援會議功能。
  
  - 如果您需要使用 pstN 企業語音 (電話) 電話服務提供者Microsoft Teams 會議室您需要使用 商務用 Skype 方案 3 (方案) 。

  - 在將會議室帳戶Microsoft Teams或 商務用 Skype Online 時，電話號碼應在帳戶啟用為會議室帳戶之前指派。
  
  - 您的租使用者使用者必須擁有Exchange信箱。
  
  - 您的 Microsoft Teams 會議室 帳戶需要 商務用 Skype Online (方案 2) 或 商務用 Skype Online (方案 3) 授權，但不需要 Exchange Online 授權。

- 指派授權商務用 Skype Server您的帳戶Microsoft Teams 會議室授權。

### <a name="create-an-account-and-synchronize-with-active-directory"></a>建立帳戶並同步處理 Active Directory

1. 在 **Active Directory 使用者** 與電腦工具中，以滑鼠右鍵按一下要建立您 Microsoft Teams 會議室 帳戶的資料夾或組織單位，按一下 [**新增**，然後按一下 **[使用者**> 。

2. 在全名方塊中輸入上一個 Cmdlet 的顯示名稱，將別名輸入到使用者 **登入名稱** 方塊中。  按一下 **[下一步**。

3. 輸入此帳戶的密碼。 您必須重新輸入以進行驗證。 請確定選取 **的唯** 一選項為密碼永不過期核取方塊。

    > [!NOTE]
    > 選取 **密碼永不過期** 是商務用 Skype Server Microsoft Teams 會議室。 您的網域規則可能會禁止不會過期的密碼。 如果是這樣，您必須為每個裝置帳戶Microsoft Teams 會議室例外。
  
4. 建立帳戶之後，請執行目錄同步處理。 完成後，請前往您系統管理中心Microsoft 365使用者頁面，並確認在先前步驟中建立的帳戶已合併至線上。

### <a name="enable-the-remote-mailbox-and-set-properties"></a>啟用遠端信箱和設定屬性

1. [開啟 Exchange管理命令殼](/powershell/exchange/exchange-server/open-the-exchange-management-shell)，或使用[遠端 PowerShell Exchange伺服器。](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)

2. 在 Exchange PowerShell 中，為帳戶建立信箱 (，執行下列命令) 啟用帳戶：

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   有關詳細的語法和參數資訊，請參閱 [啟用信箱](/powershell/module/exchange/mailboxes/enable-mailbox)。

3. 在 Exchange PowerShell 中，設定會議室信箱上的下列設定以改善會議體驗：

   - 自動化處理：自動 (會議召集人直接收到會議室預約決定，而不需要人為介入：free = accept;busy = decline.) 

   - AddOrganizerToSubject：$false (會議召集人不會新增到會議要求的主題中。) 

   - DeleteComments：$false (在傳入會議要求的郵件內文中保留任何文字。) 

   - DeleteSubject：$false (保留傳入會議要求的主題。) 

   - RemovePrivateProperty：$false (確保會議召集人在原始會議要求中所送出的私人標標維持為指定的狀態。) 

   - AddAdditionalResponse：$true (其他Response 參數指定的文字會新加到會議要求中。) 

   - 其他Response：「這是Skype會議室！  (新增到會議要求的其他文字。) 

   此範例在名為 Project-Rigel-01 的會議室信箱上設定這些設定。

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   有關詳細的語法和參數資訊，請參閱 [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing)。

### <a name="assign-a-microsoft-365-or-office-365-license"></a>指派授權Microsoft 365或Office 365授權

1. 連線Azure Active Directory。 有關 Active Directory 的詳細資訊，請參閱 [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0)。 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0)不支援。 

2. 裝置帳戶必須擁有有效的授權Microsoft 365授權Office 365，Exchange Microsoft Teams無法使用。 如果您有授權，您必須將使用位置指派給裝置帳戶，這決定您的帳戶可以使用哪些授權 SKUs。 您可以使用 `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> 以取回可用的 SKUS 清單。

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. 接下來，您可以使用 `Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> Cmdlet。 在此案例中，$strLicense是您看到的 SKU 程式碼， (contoso：STANDARDPACK) 。

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

   有關詳細指示，請參閱使用 PowerShell 指派授權[Office 365使用者帳戶](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)。

### <a name="enable-the-device-account"></a>啟用裝置帳戶

商務用 SkypeOnline PowerShell 用於管理線上和 Microsoft Teams 商務用 Skype服務。

1. 從電腦Windows PowerShell遠端會話，如下所示：
> [!NOTE]
> 商務用 Skype線上連接器是目前 PowerShell 模組Teams的一部分。
>
> 如果您使用的是最新版[PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)Teams版本，則不需要安裝 商務用 Skype 連線連接器。

   ``` Powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

2. 取得帳戶的 SIP 位址：

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. **選。** 如果您想要將電話號碼指派給帳戶，此時應執行作業。 如果您想要指派直接路由電話號碼：

   ``` Powershell
    Set-CsUser -Identity $rm -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:+14255550012
    ```
    如果您要指派 Microsoft 提供的電話號碼，請使用下列 Cmdlet，將使用者預配置為通話方案授權：
    
    ``` Powershell
    Set-CsOnlineVoiceUser -Identity $rm -TelephoneNumber +14255550011 -LocationID xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
    ```
    
4. 若要啟用您的Microsoft Teams 會議室帳戶，請執行此命令：

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   如果您不確定環境中要用於 RegistrarPool 參數的值，您可以使用此命令從現有使用者取得值：

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a>指派授權給您的帳戶Microsoft Teams 會議室授權

1. 以租使用者系統管理員登入，開啟 Microsoft 365系統管理中心，然後按一下系統管理應用程式。
2. 按一下 [ **使用者與群組** ，然後按一下 **[新增使用者、重設密碼等>**。
3. 按一下 Microsoft Teams 會議室帳戶，然後按一下 [筆形圖示以編輯帳戶資訊。
4. 按一下 **[授權>**。
5. 在 **指派授權** 中，商務用 Skype (方案 2) 或商務用 Skype (方案 3) 視您的授權和企業語音需求。 如果您想要在 企業語音 上使用方案 3 授權Microsoft Teams 會議室。
6. 按一下 [儲存]。

若要驗證，您應該可以使用任何用戶端登入此帳戶。
  
## <a name="related-topics"></a>相關主題

[設定帳戶Microsoft Teams 會議室](rooms-configure-accounts.md)

[規劃 Microsoft Teams 會議室](rooms-plan.md)
  
[部署 Microsoft Teams 會議室](rooms-deploy.md)
  
[設定 Microsoft Teams 會議室主控台](console.md)
  
[管理 Microsoft Teams 會議室](rooms-manage.md)