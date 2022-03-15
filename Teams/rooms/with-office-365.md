---
title: 使用 Microsoft Teams 會議室 部署Office 365
ms.author: czawideh
author: cazawideh
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
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: 請閱讀本主題，以瞭解如何使用 Microsoft Teams 會議室 部署Office 365。
ms.openlocfilehash: f54e7f7e201127b0a61c99f09fee2084378dbbd9
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503710"
---
# <a name="deploy-microsoft-teams-rooms-with-office-365"></a>使用 Microsoft Teams 會議室 部署Office 365

請閱讀本主題，以瞭解如何使用 Microsoft Teams 會議室 部署Office 365。

## <a name="requirements"></a>需求

使用 Microsoft Teams 會議室部署Office 365，請確定您符合需求。 詳細資訊，請參閱Microsoft Teams 會議室[需求](requirements.md)。

### <a name="add-a-resource-account"></a>新增資源帳戶

1. 連線 PowerShell Exchange Online PowerShell。 有關指示，[請參閱連線 PowerShell Exchange Online。](https://go.microsoft.com/fwlink/p/?linkid=396554)

2. 在 Exchange Online PowerShell 中，建立新會議室信箱或修改現有的會議室信箱。 根據預設，會議室信箱沒有關聯的帳戶。 當您建立或修改允許其驗證的會議室信箱時，您必須新增帳戶。

   - 若要建立新會議室信箱，請使用下列語法：

     ``` PowerShell
     New-Mailbox -Name '<Unique Name>' -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     此範例會使用下列設定來建立新會議室信箱：

     - 名稱：會議室 01

     - 別名：ConferenceRoom01

     - 帳戶：ConferenceRoom01@contoso.com

     - 帳戶密碼：P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -Name 'Conference Room 01' -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID 'ConferenceRoom01@contoso.com' -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - 若要修改現有的會議室信箱，請使用下列語法：

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     此範例啟用具有別名值 ConferenceRoom02 的現有會議室信箱的帳戶，並且將密碼設定為 9898P@$$W 0rd。

     ``` PowerShell
     Set-Mailbox -Identity 'ConferenceRoom02' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   有關詳細的語法和參數資訊，請參閱 [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) 和 [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox)。


3. 在 Exchange Online PowerShell 中，設定會議室信箱上的下列設定以改善會議體驗：

   - 自動化處理：自動接受 (信箱會自動直接做出會議室預約決策，而不需要人為介入。) 

   - AddOrganizerToSubject：$false (會議召集人不會新增到會議要求的主題中。) 

   - DeleteComments：$false (在傳入會議要求的郵件內文中保留任何文字。) 

   - DeleteSubject：$false (保留傳入會議要求的主題。) 

   - RemovePrivateProperty：$false (確保會議召集人在原始會議要求中所送出的私人標標維持為指定的狀態。) 

   - AddAdditionalResponse：$true (其他Response 參數指定的文字會新加到會議要求中。) 

   - 其他Response：「這是Microsoft Teams會議室！  (新增到會議要求的其他文字。) 

   此範例在名為 Project-Rigel-01 的會議室信箱上設定這些設定。

   ``` PowerShell
   Set-CalendarProcessing -Identity 'ConferenceRoom01' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse 'This is a Microsoft Teams meeting room!'
   ```

   有關詳細的語法和參數資訊，請參閱 [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing)。
   
4. 連線 MS Online PowerShell 會藉由使用 連線-MsolService -credential $cred powershell Cmdlet 來設定 Active Directory 值。 有關 Active Directory 的詳細資訊，請參閱 [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0)。 

   > [!NOTE]
   > [Azure Active Directory不支援 PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0)。 

5. 強烈建議您停用帳戶Teams 會議室到期。 以下是如何停用帳戶 ConferenceRoom01 密碼到期的範例：

    ``` PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -PasswordNeverExpires $true
    ```


1. 資源帳戶必須擁有有效的授權Office 365才能連接到Microsoft Teams。 您也需要為裝置帳戶指派使用位置，這決定您的帳戶可以使用哪些授權 SKUs。 您可以使用來 `Get-MsolAccountSku` 為租使用者Office 365 SKUS 清單。 您可以使用 Cmdlet 新增 `Set-MsolUserLicense` 授權。

   此範例會指派會議室授權給美國的使用者。

  ``` PowerShell
   Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM'
  ``` 


   有關詳細指示，請參閱使用[PowerShell 指派授權Office 365使用者帳戶](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)。


## <a name="validate"></a>驗證

若要驗證，您應該可以使用任何Microsoft Teams用戶端來登錄您建立的帳戶。

## <a name="see-also"></a>另請參閱
[使用額外的中繼資料更新會議室信箱，以提供更好的搜尋和會議室建議體驗](/powershell/module/exchange/set-place)

[設定帳戶Microsoft Teams 會議室](rooms-configure-accounts.md)

[規劃 Microsoft Teams 會議室](rooms-plan.md)

[部署 Microsoft Teams 會議室](rooms-deploy.md)

[設定 Microsoft Teams 會議室主控台](console.md)

[管理 Microsoft Teams 會議室](rooms-manage.md)

[Microsoft Teams 會議室授權](rooms-licensing.md)
