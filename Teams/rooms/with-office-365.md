---
title: 使用 Microsoft 365 或 Office 365 部署 Microsoft Teams 會議室
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: 請閱讀本主題，瞭解如何使用 Microsoft 365 或 Office 365 部署 Microsoft Teams 會議室，其中 Teams 或商務用 Skype 和 Exchange 都位於線上。
ms.openlocfilehash: 7a25fb17e4b9fce4a51c6e2be5828ecafff59894
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569119"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a>使用 Microsoft 365 或 Office 365 部署 Microsoft Teams 會議室

請閱讀本主題，瞭解如何使用 Microsoft 365 或 Office 365 部署 Microsoft Teams 會議室，其中 Microsoft Teams 或商務用 Skype 和 Exchange 都位於線上。

設定使用者帳戶最簡單的方法是使用遠端 Windows PowerShell 進行設定。 Microsoft 提供 [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)，這個腳本可協助建立新使用者帳戶，或驗證您現有的資源帳戶，以便將它們轉換為相容的 Microsoft Teams 會議室使用者帳戶。 您可以視需要遵循下列步驟來設定 Microsoft Teams 會議室裝置將會使用的帳戶。

## <a name="requirements"></a>需求

使用 Microsoft 365 或 Office 365 部署 Microsoft Teams 會議室之前，請確定您符合要求。 詳細資訊請參閱 Microsoft [Teams 會議室需求](requirements.md)。

若要啟用商務用 Skype，您必須有下列專案：

- 商務用 Skype Online (Microsoft 365 或 Office 365 方案) 方案 2 或企業型方案或更高版本。 此方案需要允許電話撥入式會議功能。

- 如果您需要會議的電話撥入功能，您需要音訊會議和電話系統授權。  如果您需要會議撥出功能，您需要音訊會議授權。

- 您的租使用者使用者必須擁有 Exchange 信箱。

- 您的 Microsoft Teams 會議室帳戶至少需要商務用 Skype Online (方案 2) 授權，但不需要 Exchange Online 授權。 請參閱 [Microsoft Teams 會議室授權](rooms-licensing.md) 以瞭解詳細資料。

有關商務用 Skype Online 方案的詳細資訊，請參閱 [商務用 Skype Online 服務描述](https://technet.microsoft.com/library/jj822172.aspx)。

### <a name="add-a-device-account"></a>新增裝置帳戶

1. 連線至 Exchange Online PowerShell。 有關指示，請參閱[連線到 Exchange Online PowerShell。](https://go.microsoft.com/fwlink/p/?linkid=396554)

2. 在 Exchange Online PowerShell 中，建立新會議室信箱或修改現有的會議室信箱。 根據預設，會議室信箱沒有相關聯的帳戶，因此當您建立或修改會議室信箱時，您必須新增帳戶，以便使用 Skype Room Systems v2 進行驗證。

   - 若要建立新會議室信箱，請使用下列語法：

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     此範例會使用下列設定來建立新會議室信箱：

     - 名稱：Rigel-01

     - 別名：Rigel1

     - 帳戶：Rigel1@contoso.onmicrosoft.com

     - 帳戶密碼：P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - 若要修改現有的會議室信箱，請使用下列語法：

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     此範例會啟用具有 Alias 值 Rigel2 的現有會議室信箱帳戶，並且將密碼設定為 9898P@$$W 0rd。 請注意，由於現有的別名Rigel2@contoso.onmicrosoft.com帳戶將會被刪除。

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   有關詳細的語法和參數資訊，請參閱[New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox)和[Set-Mailbox。](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)

3. 在 Exchange Online PowerShell 中，在會議室信箱上設定下列設定以改善會議體驗：

   - 自動化處理：自動接受 (會議召集人直接收到會議室預約決定，無需人工介入：free = accept;busy = decline.) 

   - AddOrganizerToSubject：$false (會議召集人不會新增到會議要求的主題中。) 

   - DeleteComments：$false (會議要求的郵件內文保留任何文字。) 

   - DeleteSubject：$false (保留傳入會議要求的主題。) 

   - RemovePrivateProperty：$false (確保會議召集人在原始會議要求中所送出的私人旗標維持為指定狀態。) 

   - AddAdditionalResponse：$true (AdditionalResponse 參數指定的文字會新增到會議要求中。) 

   - 其他Response：「這是 Skype 會議室！  (新增到會議要求的其他文字。) 

   此範例在名為 Rigel-01 的會議室信箱上設定這些設定。

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   有關詳細的語法和參數資訊，請參閱[Set-CalendarProcessing。](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)

4. 請連線到 MS Online PowerShell，以使用 `Connect-MsolService -Credential $cred` PowerShell Cmdlet 進行 Active Directory 設定。 有關 Active Directory 的詳細資訊，請參閱[Azure ActiveDirectory (MSOnline) 1.0。](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) 不受支援。

5. 如果您不希望密碼過期，請使用下列語法：

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   此範例會設定帳戶的密碼Rigel1@contoso.onmicrosoft.com永不過期。

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -PasswordNeverExpires $true
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -EnforceChangePasswordPolicy $false
   ``` -->

   您也可以執行下列命令來設定帳戶的電話號碼：

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

> [!NOTE]
> 如果密碼未設定為永不過期，當帳戶到達到期日時，該帳戶將不再在裝置上登錄。 然後需要變更帳戶的密碼，同時也需要在當地更新的 。在 12 月 24 日之後，系統就會更新該裝置。

6. 裝置帳戶必須擁有有效的 Microsoft 365 或 Office 365 授權，否則 Exchange 和 Microsoft Teams 或商務用 Skype 無法工作。 如果您有授權，您必須將使用位置指派給裝置帳戶，這決定您的帳戶可以使用哪些授權 SKUS。 您可以使用 `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> 來為 Microsoft 365 或 Office 365 組織取回可用的 SUS 清單，如下所示：

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   接下來，您可以使用 `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> Cmdlet。 此範例會將會議室授權新增到帳戶：

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   有關詳細指示，請參閱使用 [Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)指派授權給使用者帳戶。

   您也可以將電話系統功能新增到此帳戶，但您必須先進行設定。 請參閱 [什麼是電話系統？](../what-is-phone-system-in-office-365.md) 以進一步查看詳細資料。 此範例會新增國內及國際 PSTN 通話方案：

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "Contoso:MCOPSTN2"
   ```

7. 接下來，您需要使用商務用 Skype 啟用裝置帳戶。 請確定您的環境符合 Microsoft Teams [會議室中定義的需求](requirements.md)。

   啟動遠端 [Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) 會話，如下所示 (安裝 [商務用 Skype Online PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) 元件) ：

> [!NOTE]
> 商務用 Skype Online Connector 目前是最新 Teams PowerShell 模組的一部分。
>
> 如果您使用的是最新的 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)公開發行，則不需要安裝商務用 Skype Online Connector。

   ``` Powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

   從正在設定的新使用者帳戶取得 RegistrarPool 資訊，如以下範例所示：

   ``` Powershell
    Get-CsOnlineUser -Identity "Rigel1@contoso.onmicrosoft.com" | Select -Expand RegistrarPool
   ```

   接下來，執行下列 Cmdlet 以啟用商務用 Skype Server 的 Microsoft Teams 會議室帳戶：

   ``` Powershell
   Enable-CsMeetingRoom -Identity "Rigel1@contoso.onmicrosoft.com" -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   > [!NOTE]
   > 新使用者帳戶可能不會與租使用者中現有的使用者帳戶在同一個註冊機構資料庫上建立。 上述命令可防止帳戶設定因此情況而發生錯誤。

## <a name="validate"></a>驗證

若要驗證，您應該可以使用任何商務用 Skype 用戶端來使用您的建立的帳戶。

## <a name="see-also"></a>另請參閱

[設定 Microsoft Teams 會議室的帳戶](rooms-configure-accounts.md)

[規劃 Microsoft Teams 會議室](rooms-plan.md)

[部署 Microsoft Teams 會議室](rooms-deploy.md)

[設定 Microsoft Teams 會議室主控台](console.md)

[管理 Microsoft Teams 會議室](rooms-manage.md)

[Microsoft Teams 會議室授權](rooms-licensing.md)
