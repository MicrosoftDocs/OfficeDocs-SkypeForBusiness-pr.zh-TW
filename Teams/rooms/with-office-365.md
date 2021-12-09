---
title: 使用 Microsoft Teams 會議室 或 Microsoft 365 部署Office 365
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: 請閱讀本主題，瞭解如何使用 Microsoft Teams 會議室 或 Microsoft 365 部署Office 365，其中 Teams 或 商務用 Skype Exchange都位於線上。
ms.openlocfilehash: e3f72c86f88ab449b48b80d6bef06d0858c44b53
ms.sourcegitcommit: 1165a74b1d2e79e1a085b01e0e00f7c65483d729
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/08/2021
ms.locfileid: "61355642"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a>使用 Microsoft Teams 會議室 或 Microsoft 365 部署Office 365

請閱讀本主題，瞭解如何使用 Microsoft Teams 會議室 或 Microsoft 365 部署Office 365，Microsoft Teams和Exchange線上。

## <a name="requirements"></a>需求

在以 Microsoft Teams 會議室 或 Microsoft 365 部署Office 365，請確定您符合需求。 詳細資訊，請參閱Microsoft Teams 會議室[需求](requirements.md)。

### <a name="add-a-resource-account"></a>新增資源帳戶

1. 連線 PowerShell Exchange Online。 有關指示，請參閱連線[PowerShell Exchange Online。](/powershell/exchange/connect-to-exchange-online-powershell)

2. 在 Exchange Online PowerShell 中，建立新會議室信箱或修改現有的會議室信箱。 根據預設，會議室信箱沒有關聯的帳戶，因此當您建立或修改會議室信箱時，您必須新增帳戶，以便使用 Microsoft Teams。

   - 若要建立新會議室信箱，請使用下列語法：

     ``` PowerShell
     New-Mailbox -MicrosoftOnlineServicesID <Office365 ID> -Name <String> -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```
     此範例會使用下列設定來建立新會議室信箱：

     - 帳戶：ConferenceRoom01@contoso.com
  
     - 名稱：ConferenceRoom01

     - 別名：ConferenceRoom01

     - 帳戶密碼：P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -MicrosoftOnlineServicesID ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - 若要修改現有的會議室信箱，請使用下列語法：

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     此範例啟用具有別名值 ConferenceRoom02 的現有會議室信箱的帳戶，並且將密碼設定為 9898P@$$W 0rd。 請注意，由於現有的別名 ConferenceRoom02@contoso.com 帳戶將會無法使用。

     ``` PowerShell
     Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   有關詳細的語法和參數資訊，請參閱 [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) 和 [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox)。

3. 在 Exchange Online PowerShell 中，設定會議室信箱上的下列設定以改善會議體驗：

   - 自動化處理：自動 (會議召集人直接收到會議室預約決定，而不需要人為介入。) 

   - AddOrganizerToSubject：$false (會議召集人不會新增到會議要求的主題中。) 

   - DeleteComments：$false (在傳入會議要求的郵件內文中保留任何文字。) 

   - DeleteSubject：$false (保留傳入會議要求的主題。) 

   - RemovePrivateProperty：$false (確保會議召集人在原始會議要求中所送出的私人標標維持為指定的狀態。) 

   - AddAdditionalResponse：$true (其他Response 參數指定的文字會新加到會議要求中。) 

   - 其他Response：「這是Microsoft Teams會議室！  (新增到會議要求的其他文字。) 

   此範例在名為 ConferenceRoom01 的會議室信箱上設定這些設定。

   ``` PowerShell
   Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

   有關詳細的語法和參數資訊，請參閱 [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing)。

4. 連線 MS Online PowerShell，以使用 `Connect-MsolService`PowerShell Cmdlet。 有關 Active Directory 的詳細資訊，請參閱 [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0)。

   > [!NOTE]
   > [Azure Active Directory不支援 PowerShell 2.0。](/powershell/azure/active-directory/overview?view=azureadps-2.0)

5. 使用下列語法將密碼設為永不過期：

   ```PowerShell
   Set-MsolUser -UserPrincipalName <UPN> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   此範例會設定帳戶的密碼 ConferenceRoom01@contoso.onmicrosoft.com 永不過期。

   ```PowerShell
   Set-MsolUser -UserPrincipalName "ConferenceRoom01@contoso.com" -PasswordNeverExpires $true
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -EnforceChangePasswordPolicy $false
   ``` -->

   您也可以執行下列命令來設定帳戶的電話號碼：

   ```PowerShell
   Set-MsolUser -UserPrincipalName <UPN> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

    > [!NOTE]
    > 如果密碼未設定為永不過期，當帳戶到達到期日時，該帳戶將不再在裝置上登錄。 然後必須變更帳戶的密碼，並且也會在 Teams 會議室。 密碼到期時，Teams 會議室無法加入會議。

6. 資源帳戶必須擁有有效的授權Microsoft 365授權Office 365，Exchange Microsoft Teams無法使用。 如果您有授權，您必須將使用位置指派給資源帳戶，這決定您的帳戶可以使用哪些授權 SKUs。 您可以使用 `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> 以如下方式為貴組織或Microsoft 365 Office 365可用的 SKUS 清單：

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   接下來，您可以使用 `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> Cmdlet。 此範例新增會議室授權至帳戶：

   ```PowerShell
   Set-MsolUser -UserPrincipalName "ConferenceRoom01@contoso.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName "ConferenceRoom01@contoso.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   有關詳細指示，請參閱使用 PowerShell 指派授權[Office 365使用者帳戶](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)。

   您也可以新增電話系統功能至此帳戶，但您必須先進行設定。 請參閱[什麼是電話系統？](../what-is-phone-system-in-office-365.md)以進一步查看詳細資料。 此範例新增 PSTN 國內及國際通話方案：

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName ConferenceRoom01@contoso.com -AddLicenses "Contoso:MCOPSTN2"
   ```


## <a name="validate"></a>驗證

若要驗證，您應該可以使用任何Microsoft Teams用戶端來登錄您建立的帳戶。

## <a name="see-also"></a>另請參閱

[設定帳戶Microsoft Teams 會議室](rooms-configure-accounts.md)

[規劃 Microsoft Teams 會議室](rooms-plan.md)

[部署 Microsoft Teams 會議室](rooms-deploy.md)

[設定 Microsoft Teams 會議室主控台](console.md)

[管理 Microsoft Teams 會議室](rooms-manage.md)

[Microsoft Teams 會議室授權](rooms-licensing.md)
