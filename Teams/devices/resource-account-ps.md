---
title: 使用 PowerShell 為 Microsoft 團隊建立共同作業橫條圖的 Microsoft 團隊資源帳戶
ms.author: mitressl
author: flinchbot
manager: ericwe
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: 如需如何為 Microsoft 團隊部署共同作業橫條圖的相關資訊，請參閱本主題。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 0cb8043e0530c986b9ddcaa9a1022254939adfd2
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268029"
---
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a>使用 PowerShell 建立 Microsoft 365 資源帳戶

若要瞭解如何使用 PowerShell 為 Microsoft 團隊建立共同作業列的資源帳戶，請閱讀本主題。

建立資源帳戶最簡單的方法是使用 Microsoft 365 系統管理中心。 [請參閱這篇文章以瞭解如何執行此](resource-account-ui.md)動作。

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a>需求

在使用 Office 365 部署 Microsoft 團隊聊天室之前，請確定您已滿足需求。 如需詳細資訊，請參閱為[Microsoft 團隊部署](collab-bar-deploy.md)共同作業條。

- 如果您需要 [共同作業] 列的 PSTN 功能，您將需要 [電話系統授權]。

- 您的資源帳戶必須有 Exchange 信箱。 因為這些是資源帳戶，因此不需要 Exchange 授權。 我們建議使用 [會議室] 授權來取得資源帳戶。


### <a name="add-a-resource-account"></a>新增資源帳戶

1. [連線至 Exchange Online PowerShell]。 如需相關指示，請參閱連線[至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)。

2. 在 Exchange Online PowerShell 中，建立新的會議室信箱或修改現有的會議室信箱。

   - 若要建立新的會議室信箱，請使用下列語法：

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     這個範例會使用下列設定建立新的會議室信箱：

     - Name （名稱）： Huddle-01

     - 別名： HuddleRoom01

     - 帳戶： huddleroom01@contoso.onmicrosoft.com

     - 帳戶密碼： P@ $ $W 0rd242

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - 若要修改現有的會議室信箱，請使用下列語法：

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     這個範例會為擁有別名值 HuddleRoom02 的現有聊天室信箱啟用帳戶，並將密碼設定為 808P@ $ $W 0rd。 請注意，由於現有的別名值，該帳戶將會 HuddleRoom02@contoso.onmicrosoft.com。

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   如需詳細的語法與參數資訊，請參閱[新增-信箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox)和[設定信箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)。


3. 在 Exchange Online PowerShell 中，設定會議室信箱上的下列設定，以改善會議體驗：

   - AutomateProcessing： AutoAccept （會議召集人直接在沒有人工干預的情況下收到會議室保留決策：免費 = accept; 忙碌 = 拒絕。）

   - AddOrganizerToSubject： $false （會議召集人不會新增至會議邀請的主旨。）

   - DeleteComments： $false （在傳入會議邀請的郵件內文中保留任何文字。）

   - DeleteSubject： $false （請不要傳送會議邀請的主題）。

   - RemovePrivateProperty： $false （保證會議召集人在原始會議邀請中傳送的私人旗標保持在指定的時間。）

   - AddAdditionalResponse： $true （由 AdditionalResponse 參數指定的文字會新增至會議邀請。）

   - AdditionalResponse：「此聊天室有一個適用于 Microsoft 團隊的共同作業工具列！」 （要新增至會議邀請的其他文字）。

   這個範例會在名為 Huddle-01 的聊天室信箱上設定這些設定。

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   如需詳細的語法與參數資訊，請參閱[設定 CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)。

4. 使用 PowerShell Cmdlet 連線至 MS Online PowerShell，以進行 Active Directory 設定 `Connect-MsolService -Credential $cred` 。   如需 Active Directory 的詳細資訊，請參閱[Azure ActiveDirectory （import-module msonline） 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)。 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)不受支援。 

5. 使用下列語法，將 huddleroom01@contoso.onmicrosoft.com 的密碼設定為不超過到期日：

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. 資源帳戶必須擁有有效的 Office 365 授權，最好是會議室 SKU。 您也需要將使用位置指派給您的裝置帳戶，這會決定您的帳戶可使用哪些授權 Sku。 您可以用 `Get-MsolAccountSku` 來針對您的 Office 365 租使用者取得可用的 sku 清單。

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    您可以使用 [設定] MsolUserLicense 指派授權。 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   如需詳細指示，請參閱[使用 Office 365 PowerShell 指派授權給使用者帳戶](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)。




[使用 PowerShell 針對 Microsoft 團隊設定共同作業橫條圖的帳戶](resource-account-ps.md)

[為 Microsoft 團隊部署共同作業橫條圖](collab-bar-deploy.md)

[Microsoft 團隊授權的共同作業條](../rooms/rooms-licensing.md)


