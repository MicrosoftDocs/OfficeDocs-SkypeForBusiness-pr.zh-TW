---
title: 使用 powerShell Microsoft Teams共同Microsoft Teams資源帳戶
ms.author: czawideh
author: cazawideh
manager: ericwe
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: 請閱讀本主題，以瞭解如何部署共同Microsoft Teams。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 0bbafdfbfc9fb7e9b637216aeb9e5a0d6b470533
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503910"
---
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a>使用 PowerShell Microsoft 365建立資源帳戶

請參閱本主題，以瞭解如何使用 PowerShell 為共同Microsoft Teams建立資源帳戶。

建立資源帳戶最簡單的方法是使用Microsoft 365 系統管理中心。 [請參閱本文，瞭解如何執行此工作](resource-account-ui.md)。

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a>需求

使用 Microsoft Teams 會議室部署Office 365，請確定您符合需求。 詳細資訊，請參閱[部署共同Microsoft Teams](collab-bar-deploy.md)。

- 如果您需要共同合作欄的 PSTN 功能，則需要電話系統授權。

- 您的資源帳戶必須Exchange信箱。 由於這些是資源帳戶，Exchange授權。 我們建議您使用資源帳戶的會議室授權。


### <a name="add-a-resource-account"></a>新增資源帳戶

1. 連線 PowerShell Exchange Online PowerShell。 有關指示，[請參閱連線 PowerShell Exchange Online。](/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)

2. 在 Exchange Online PowerShell 中，建立新會議室信箱或修改現有的會議室信箱。

   - 若要建立新會議室信箱，請使用下列語法：

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     此範例會使用下列設定來建立新會議室信箱：

     - 名稱：Huddle-Room-01

     - 別名：HuddleRoom01

     - 帳戶：huddleroom01@contoso.onmicrosoft.com

     - 帳戶密碼：P@$$W 0rd242

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - 若要修改現有的會議室信箱，請使用下列語法：

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     此範例啟用具有 HuddleRoom02 別名的現有會議室信箱的帳戶，並且將密碼設定為 808P@$$W 0rd。 請注意，由於現有的別名 HuddleRoom02@contoso.onmicrosoft.com 帳戶將會無法使用。

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   有關詳細的語法和參數資訊，請參閱 [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) 和 [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox)。


3. 在 Exchange Online PowerShell 中，設定會議室信箱上的下列設定以改善會議體驗：

   - 自動化處理：自動接受 (會議召集人直接收到會議室預約決定，而不需要人為介入：free = accept;busy = decline.) 

   - AddOrganizerToSubject：$false (會議召集人不會新增到會議要求的主題中。) 

   - DeleteComments：$false (在傳入會議要求的郵件內文中保留任何文字。) 

   - DeleteSubject：$false (保留傳入會議要求的主題。) 

   - RemovePrivateProperty：$false (確保會議召集人在原始會議要求中所送出的私人標標維持為指定的狀態。) 

   - AddAdditionalResponse：$true (其他Response 參數指定的文字會新加到會議要求中。) 

   - 其他Response：「這個會議室有一個共同Microsoft Teams！  (新增到會議要求的其他文字。) 

   此範例在名為 Huddle-Room-01 的會議室信箱上設定這些設定。

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   有關詳細的語法和參數資訊，請參閱 [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing)。

4. 連線 MS Online PowerShell，以使用 Powershell Cmdlet 來 `Connect-MsolService -Credential $cred` 設定 Active Directory。   有關 Active Directory 的詳細資訊，請參閱 [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0)。 

   > [!NOTE]
   > [Azure Active Directory不支援 PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0)。 

5. 使用下列語法 huddleroom01@contoso.onmicrosoft.com 密碼，讓密碼不會過期：

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. 資源帳戶需要有有效的授權Office 365，最好是會議室 SKU。 您也需要為裝置帳戶指派使用位置，這決定您的帳戶可以使用哪些授權 SKUs。 您可以使用來 `Get-MsolAccountSku` 為租使用者Office 365 SKUS 清單。

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    您可以使用 Set-MsolUserLicense 指派授權。 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   有關詳細指示，請參閱使用[PowerShell 指派授權Office 365使用者帳戶](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)。




[使用 PowerShell 設定共同Microsoft Teams欄的帳戶](resource-account-ps.md)

[部署共同Microsoft Teams](collab-bar-deploy.md)

[適用于授權Microsoft Teams共同合作橫條圖](../rooms/rooms-licensing.md)