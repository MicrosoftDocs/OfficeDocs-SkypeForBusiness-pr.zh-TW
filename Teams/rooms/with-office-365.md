---
title: 使用 Microsoft 365 或 Office 365 部署 Microsoft 團隊聊天室
ms.author: v-lanac
author: lanachin
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
description: 如需有關如何使用 Microsoft 365 或 Office 365 （團隊或商務用 Skype 與 Exchange 都在線上）部署 Microsoft 團隊聊天室的資訊，請閱讀本主題。
ms.openlocfilehash: 2b7574b54782140e3f082c8c3859c9caee7712eb
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905275"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a>使用 Microsoft 365 或 Office 365 部署 Microsoft 團隊聊天室

如需有關如何使用 Office 365 （Microsoft 團隊或商務用 Skype 與 Exchange 都在線上）部署 Microsoft 團隊聊天室的資訊，請閱讀本主題。

設定使用者帳戶最簡單的方法，就是使用遠端 Windows PowerShell 進行設定。 Microsoft 提供[SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105)，此腳本將協助您建立新的使用者帳戶，或驗證您所擁有的現有資源帳戶，以協助您將它們轉換成相容的 Microsoft 團隊聊天室使用者帳戶。 如果您想要的話，您可以依照下列步驟來設定您的 Microsoft 團隊聊天室裝置將會使用的帳戶。

## <a name="requirements"></a>需求

在使用 Office 365 部署 Microsoft 團隊聊天室之前，請確定您已滿足需求。 如需詳細資訊，請參閱[Microsoft 團隊會議室需求](requirements.md)。

若要啟用商務用 Skype，您必須具備下列各項：

- Office 365 方案中的商務用 Skype Online （方案2或企業方案）或更高版本。 方案需要允許電話撥入式會議功能。

- 如果您需要來自會議的撥入功能，您將需要音訊會議和電話系統授權。  如果您需要來自會議的撥出功能，您需要音訊會議授權。

- 您的租使用者必須有 Exchange 信箱。

- 您的 Microsoft 團隊會議室帳戶至少需要商務用 Skype Online （方案2）授權，但不需要 Exchange Online 授權。 如需詳細資訊，請參閱[Microsoft 團隊聊天室授權](rooms-licensing.md)。

如需商務用 Skype Online 方案的詳細資料，請參閱[商務用 Skype Online 服務說明](https://technet.microsoft.com/library/jj822172.aspx)。

### <a name="add-a-device-account"></a>新增裝置帳戶

1. [連線至 Exchange Online PowerShell]。 如需相關指示，請參閱連線[至 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。

2. 在 Exchange Online PowerShell 中，建立新的會議室信箱或修改現有的會議室信箱。 根據預設，會議室信箱沒有相關聯的帳戶，因此，當您建立或修改允許該帳戶透過 Skype 會議室系統 v2 進行驗證的聊天室信箱時，您將需要新增帳戶。

   - 若要建立新的會議室信箱，請使用下列語法：

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     這個範例會使用下列設定建立新的會議室信箱：

     - 名稱：專案-Rigel-01

     - 別名： ProjectRigel01

     - 帳戶： ProjectRigel01@contoso.onmicrosoft.com

     - 帳戶密碼： P@ $ $W 0rd5959

     ``` PowerShell
     New-Mailbox -Name "Project-Rigel-01" -Alias ProjectRigel01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID ProjectRigel01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - 若要修改現有的會議室信箱，請使用下列語法：

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     這個範例會為擁有別名值 ProjectRigel02 的現有聊天室信箱啟用帳戶，並將密碼設定為 9898P@ $ $W 0rd。 請注意，由於現有的別名值，該帳戶將會 ProjectRigel02@contoso.onmicrosoft.com。

     ``` PowerShell
     Set-Mailbox -Identity ProjectRigel02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   如需詳細的語法與參數資訊，請參閱[新增-信箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox)和[設定信箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)。


3. 在 Exchange Online PowerShell 中，設定會議室信箱上的下列設定，以改善會議體驗：

   - AutomateProcessing： AutoAccept （會議召集人直接在沒有人工干預的情況下收到會議室保留決策：免費 = accept; 忙碌 = 拒絕。）

   - AddOrganizerToSubject： $false （會議召集人不會新增至會議邀請的主旨。）

   - DeleteComments： $false （在傳入會議邀請的郵件內文中保留任何文字。）

   - DeleteSubject： $false （請不要傳送會議邀請的主題）。

   - RemovePrivateProperty： $false （保證會議召集人在原始會議邀請中傳送的私人旗標保持在指定的時間。）

   - AddAdditionalResponse： $true （由 AdditionalResponse 參數指定的文字會新增至會議邀請。）

   - AdditionalResponse：「這是 Skype 會議室！」 （要新增至會議邀請的其他文字）。

   這個範例會在名為 Project-Rigel-01 的聊天室信箱上設定這些設定。

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   如需詳細的語法與參數資訊，請參閱[設定 CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)。

4. 使用`Connect-MsolService -Credential $cred` PowerShell Cmdlet 連線至 MS Online PowerShell，以進行 Active Directory 設定。   如需 Active Directory 的詳細資訊，請參閱[Azure ActiveDirectory （import-module msonline） 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)。 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)不受支援。 

5. 如果您不希望密碼到期，請使用下列語法：

    ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
    ```
<!--
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   這個範例會將帳戶 ProjectRigel01@contoso.onmicrosoft.com 的密碼設為永不過期。

  ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName ProjectRigel01@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   您也可以執行下列命令，以設定帳戶的電話號碼：

  ``` PowerShell
    Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. 裝置帳戶必須具備有效的 Office 365 授權，或是 Exchange 與 Microsoft 團隊或商務用 Skype 將無法運作。 如果您有授權，您必須將使用位置指派給您的裝置帳戶，這會決定您的帳戶可使用哪些授權 Sku。 您可以使用`Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> 若要為您的 Office 365 組織取得可用的 Sku 清單，請按照下列步驟操作：

  ``` Powershell
  Get-MsolAccountSku
  ```
<!--
   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   接下來，您可以使用`Set-MsolUserLicense` <!--Set-AzureADUserLicense --> Cmdlet. 在此情況下，$strLicense 是您所看到的 SKU 程式碼（例如 contoso： STANDARDPACK）。

  ``` PowerShell
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
  ``` 
<!-- 
   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```   -->

   如需詳細指示，請參閱[使用 Office 365 PowerShell 指派授權給使用者帳戶](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)。

7. 接下來，您必須在商務用 Skype 中啟用裝置帳戶。 請確定您的環境符合[Microsoft 團隊會議室需求](requirements.md)中定義的需求。

   啟動遠端[Windows PowerShell 會話](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)，如下所示（請務必[安裝商務用 Skype Online PowerShell 元件](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)）：

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   接下來，請執行下列 Cmdlet，為商務用 Skype Server 啟用您的 Microsoft 團隊房間帳戶：

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   從要設定的新使用者帳戶取得 RegistrarPool 資訊，如下例所示：

    ``` Powershell
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > 可能不會在與租使用者帳戶相同的註冊機構池中建立新的使用者帳戶。 上述命令會防止由於這種情況而導致帳戶設定發生錯誤。

完成上述步驟後，若要啟用 microsoft 團隊或商務用 Skype Online 中的 Microsoft 小組聊天室帳戶，您必須將授權指派給 Microsoft 團隊聊天室裝置。 使用 Office 365 系統管理中心入口網站，將商務用 Skype Online （方案2）或商務用 Skype Online （方案3）授權指派到裝置。

### <a name="assign-a-license-to-your-account"></a>指派授權給您的帳戶

1. 以租使用者管理員身分登入，開啟 Office 365 系統管理中心入口網站，然後按一下 [管理] 應用程式。

2. 按一下 [**使用者和群組**]，然後按一下 [**新增使用者、重設密碼**等等]。

3. 選取 [Microsoft 團隊聊天室] 帳戶，然後按一下或輕觸手寫筆圖示，也就是 [編輯]。

4. 按一下 [**授權**] 選項。

5. 在 [**指派授權**] 區段中，您必須選取 [商務用 skype Online （方案2）] 或 [商務用 skype Online （方案3）]，這取決於您的授權，以及您在需要企業語音時所決定的內容。 如果您想要在 Microsoft 團隊聊天室使用雲端 PBX，您必須使用 [方案3授權]。 您至少需要 CloudPBX 才能進行語音連線。 然後根據 PSTN 連接方法設定混合式語音或 PSTN 通話。 如需詳細資訊，請參閱[Microsoft 團隊聊天室授權](rooms-licensing.md)。

6. 按一下 [**儲存**] 以完成工作。

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a>範例： Exchange Online 和商務用 Skype Online 中的房間帳戶設定

Exchange Online PowerShell 命令：

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept-AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

Azure Active Directory PowerShell 命令：

``` PowerShell
Set-MsolUser -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```

<!-- 
``` PowerShell
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```  -->

商務用 Skype PowerShell 命令：

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> 這會新增 CloudPBX 和 PSTNCallingDomesticAndInternational。 此外，您必須使用系統管理員介面指派電話號碼。

## <a name="validate"></a>核實

針對驗證，您應該能夠使用任何商務用 Skype 用戶端登入您所建立的帳戶。

## <a name="see-also"></a>另請參閱

[設定 Microsoft 團隊聊天室的帳戶](rooms-configure-accounts.md)

[規劃 Microsoft Teams 會議室](rooms-plan.md)

[部署 Microsoft Teams 會議室](rooms-deploy.md)

[設定 Microsoft Teams 會議室主控台](console.md)

[管理 Microsoft Teams 會議室](rooms-manage.md)

[Microsoft 團隊聊天室授權](rooms-licensing.md)
