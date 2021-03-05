---
title: 使用 Exchange 內部部署部署 Microsoft Teams 會議室
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
description: 請閱讀本主題，以瞭解如何在混合式環境中與 Exchange 內部部署部署 Microsoft Teams 會議室。
ms.openlocfilehash: fcf7216a4fcadee1e81ef11b5310b9d0a88e378a
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460513"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>在內部部署 Exchange 部署 Microsoft Teams 會議室

請閱讀本主題，以瞭解如何在混合式環境中部署 Microsoft Teams 會議室與 Exchange 內部部署和 Microsoft Teams 或商務用 Skype Online。
  
如果貴組織混合使用各種服務，其中一些是內部部署，另一部分則由線上託管，則您的組配置取決於每個服務的託管位置。 本主題涵蓋內部部署的 Microsoft Teams 會議室與 Exchange 的混合式部署。 由於這種類型的部署有許多不同的變化，因此無法針對所有部署提供詳細指示。 下列程式適用于許多組配置。 如果此程式適用于您的設定，建議您使用 Windows PowerShell 來達到與本文所述相同的最終結果，以及其他部署選項。

Microsoft 提供 [SkypeRoomProvisioningScript.ps1， ](https://go.microsoft.com/fwlink/?linkid=870105)此腳本可協助建立新使用者帳戶，或驗證您現有的資源帳戶，以便將它們轉換為相容的 Microsoft Teams 會議室使用者帳戶。 您可以視需要遵循下列步驟來設定 Microsoft Teams 會議室裝置將會使用的帳戶。
  
## <a name="requirements"></a>需求

在部署內部部署 Exchange 的 Microsoft Teams 會議室之前，請確定您符合需求。 詳細資訊請參閱 Microsoft [Teams 會議室需求](requirements.md)。
  
如果您要在內部部署具有 Exchange 的 Microsoft Teams 會議室，您將使用 Active Directory 管理工具為您的內部部署網域帳戶新增電子郵件地址。 這個帳戶將會同步到 Microsoft 365 或 Office 365。 您必須：
  
- 建立帳戶，並同步處理帳戶與 Active Directory。

- 啟用遠端信箱並設定屬性。

- 指派 Microsoft 365 或 Office 365 授權。

- 使用商務用 Skype Server 啟用裝置帳戶。 若要啟用裝置帳戶，您的環境必須符合下列先決條件：

  - 您的 Microsoft 365 或 Office 365 方案 (商務用 Skype Online) 或更高版本。 此方案需要支援會議功能。
  
  - 如果您需要企業語音 (PSTN 電話) 使用 Microsoft Teams 會議室的電話服務提供者，您需要商務用 Skype Online (方案 3) 。
  
  - 您的租使用者使用者必須擁有 Exchange 信箱。
  
  - 您的 Microsoft Teams 會議室帳戶確實需要商務用 Skype Online (方案 2) 或商務用 Skype Online (方案 3) 授權，但不需要 Exchange Online 授權。

- 指派商務用 Skype Server 授權給 Microsoft Teams 會議室帳戶。

### <a name="create-an-account-and-synchronize-with-active-directory"></a>建立帳戶並同步處理 Active Directory

1. 在 **Active Directory** 使用者與電腦工具中，以滑鼠右鍵按一下要建立 Microsoft Teams 會議室帳戶的資料夾或組織單位，按一下 [ **新增**，然後按一下 **[使用者**。

2. 在全名方塊中輸入上一個 Cmdlet 的顯示名稱，將別名輸入到 **使用者登入名稱** 方塊。  按一下 [ **下一步**。

3. 輸入此帳戶的密碼。 您必須重新輸入以進行驗證。 請確定選取 **的唯一選項是** 密碼永不過期核取方塊。

    > [!NOTE]
    > 選取 **密碼永不過期** 是 Microsoft Teams 會議室商務用 Skype Server 的一項要求。 您的網域規則可能會禁止密碼過期。 若是如此，您必須為每個 Microsoft Teams 會議室裝置帳戶建立例外。
  
4. 建立帳戶之後，請執行目錄同步處理。 完成後，請前往 Microsoft 365 系統管理中心的使用者頁面，並確認先前步驟建立的帳戶已合併至線上。

### <a name="enable-the-remote-mailbox-and-set-properties"></a>啟用遠端信箱和設定屬性

1. [開啟 Exchange 管理命令區](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell)[，或使用遠端 PowerShell 連接到 Exchange 伺服器](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)。

2. 在 Exchange PowerShell 中，為帳戶建立 (信箱，以執行下列) 啟用帳戶：

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   有關詳細的語法和參數資訊，請參閱[Enable-Mailbox。](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox)

3. 在 Exchange PowerShell 中，在會議室信箱上設定下列設定以改善會議體驗：

   - 自動化處理：自動接受 (會議召集人直接收到會議室預約決定，無需人工介入：free = accept;busy = decline.) 

   - AddOrganizerToSubject：$false (會議召集人不會新增到會議要求的主題中。) 

   - DeleteComments：$false (會議要求的郵件內文保留任何文字。) 

   - DeleteSubject：$false (保留傳入會議要求的主題。) 

   - RemovePrivateProperty：$false (確保會議召集人在原始會議要求中所送出的私人標號維持為指定狀態。) 

   - AddAdditionalResponse：$true (AdditionalResponse 參數指定的文字會新增到會議要求中。) 

   - 其他Response：「這是 Skype 會議室！  (新增到會議要求的其他文字。) 

   此範例在名為 Project-Rigel-01 的會議室信箱上設定這些設定。

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   有關詳細的語法和參數資訊，請參閱[Set-CalendarProcessing。](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)

### <a name="assign-a-microsoft-365-or-office-365-license"></a>指派 Microsoft 365 或 Office 365 授權

1. 連接到 Azure Active Directory。 有關 Active Directory 的詳細資訊，請參閱[Azure ActiveDirectory (MSOnline) 1.0。](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) 不受支援。 

2. 裝置帳戶必須擁有有效的 Microsoft 365 或 Office 365 授權，否則 Exchange 和 Microsoft Teams 無法工作。 如果您有授權，您必須將使用位置指派給裝置帳戶，這決定您的帳戶可以使用哪些授權 SKUS。 您可以使用 `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> 以取回可用的 SKUS 清單。

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. 接下來，您可以使用 `Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> Cmdlet。 在此案例中，$strLicense是您看到的 SKU (例如 contoso：STANDARDPACK) 。

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

   有關詳細指示，請參閱使用 [Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)指派授權給使用者帳戶。

### <a name="enable-the-device-account"></a>啟用裝置帳戶

商務用 Skype Online PowerShell 可用來管理 Microsoft Teams 和商務用 Skype Online 的服務。

1. 從電腦建立遠端 Windows PowerShell 會話，如下所示：
> [!NOTE]
> 商務用 Skype Online Connector 目前是最新 Teams PowerShell 模組的一部分。
>
> 如果您使用的是最新的 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)公開發行，則不需要安裝商務用 Skype Online Connector。

   ``` Powershell
   Import-Module -Name MicrosoftTeams  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. 取得帳戶的 SIP 位址：

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. 若要啟用您的 Microsoft Teams 會議室帳戶，請執行此命令：

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   如果您不確定要用於您環境中 RegistrarPool 參數的值，可以使用此命令從現有使用者取得值：

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a>指派授權給 Microsoft Teams 會議室帳戶

1. 以租使用者系統管理員的名登入、開啟 Microsoft 365 系統管理中心，然後按一下系統管理應用程式。
2. 按一下使用者 **和群組，** 然後按一下 **[新增使用者、重設密碼等等**。
3. 按一下 Microsoft Teams 會議室帳戶，然後按一下筆圖示以編輯帳戶資訊。
4. 按一下 **[授權**。
5. 在 **指派授權** 中，根據您的授權和企業語音 (，選取商務用 Skype (方案 2) 或商務用 Skype (方案 3) 。 如果您想要在 Microsoft Teams 會議室使用企業語音，您必須使用方案 3 授權。
6. 按一下 [儲存 **]**。

若要驗證，您應該可以使用任何用戶端登入此帳戶。
  
## <a name="related-topics"></a>相關主題

[設定 Microsoft Teams 會議室的帳戶](rooms-configure-accounts.md)

[規劃 Microsoft Teams 會議室](rooms-plan.md)
  
[部署 Microsoft Teams 會議室](rooms-deploy.md)
  
[設定 Microsoft Teams 會議室主控台](console.md)
  
[管理 Microsoft Teams 會議室](rooms-manage.md)
