---
title: '使用Microsoft Teams 會議室內部部署Exchange混合式 (部署) '
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: 請參閱本主題，瞭解如何在混合式環境中部署Microsoft Teams 會議室內部部署Exchange部署。
ms.openlocfilehash: ea05ef6b6bf6e13ee907d84d1d48200c0cea5a09
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767226"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises-hybrid"></a>在Microsoft Teams 會議室部署Exchange混合式 (部署) 

請閱讀本主題，瞭解如何在混合式環境中Microsoft Teams 會議室內部部署Exchange部署Microsoft Teams。
  
如果貴組織有混合式服務，其中一些是內部部署，有些是線上託管，則您的組式取決於每個服務的託管位置。 本主題涵蓋使用內部部署Microsoft Teams 會議室Exchange的混合式部署。 由於這類部署有許多不同的變化，因此無法針對所有部署提供詳細指示。 下列程式適用于許多配置。 如果此程式不適用於您的設定，建議您使用 Windows PowerShell來達到此處所記載的相同最終結果，以及其他部署選項。
  
## <a name="requirements"></a>需求

在內部Microsoft Teams 會議室部署Exchange，請確定您符合需求。 詳細資訊，請參閱Microsoft Teams 會議室[需求](requirements.md)。

### <a name="enable-the-remote-mailbox-and-set-properties"></a>啟用遠端信箱和設定屬性

1. [開啟 Exchange管理命令殼](/powershell/exchange/exchange-server/open-the-exchange-management-shell)，或使用遠端[PowerShell Exchange伺服器。](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)

2. 在 Exchange PowerShell 中，建立新會議室信箱或修改現有的會議室信箱。 根據預設，會議室信箱沒有關聯的帳戶，因此當您建立或修改會議室信箱時，您必須新增帳戶，以便使用 Microsoft Teams。

   - 若要建立新會議室信箱，請使用下列語法：

     ``` PowerShell
     New-Mailbox -UserPrincipalName <UPN> -Name <String> -Alias <String> -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```
     
     此範例會使用下列設定來建立新會議室信箱：

     - 帳戶：ConferenceRoom01@contoso.com
  
     - 名稱：ConferenceRoom01

     - 別名：ConferenceRoom01

     - 帳戶密碼：P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - 若要修改現有的會議室信箱，請使用下列語法：

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     此範例啟用具有別名值 ConferenceRoom02 的現有會議室信箱的帳戶，並且將密碼設定為 9898P@$$W 0rd。 請注意，帳戶會因為 ConferenceRoom02@contoso.com 別名值而無法使用。

     ``` PowerShell
     Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   有關詳細的語法和參數資訊，請參閱 [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) 和 [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox)。

3. 在 Exchange PowerShell 中，設定會議室信箱上的下列設定以改善會議體驗：

   - 自動化處理：自動 (會議召集人直接收到會議室預約決定，而不需要人為介入。) 

   - AddOrganizerToSubject：$false (會議召集人不會新增到會議要求的主題中。) 

   - DeleteComments：$false (在傳入會議要求的郵件內文中保留任何文字。) 

   - DeleteSubject：$false (保留傳入會議要求的主題。) 

   - RemovePrivateProperty：$false (確保會議召集人在原始會議要求中所送出的私人標標維持為指定的狀態。) 

   - AddAdditionalResponse：$true (其他Response 參數指定的文字會新加到會議要求中。) 

   - 其他Response：「這是Microsoft Teams會議室！  (新增到會議要求的其他文字。) 

   此範例在名為 ConferenceRoom01 的會議室信箱上設定這些設定。

   ```PowerShell
   Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

   有關詳細的語法和參數資訊，請參閱 [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing)。

### <a name="set-password-to-never-expire"></a>設定密碼永不過期

1. 在 **Active Directory 使用者與電腦** 工具中，尋找 Microsoft Teams 會議室帳戶，以滑鼠右鍵按一下該帳戶，然後選取 **[內容**> 。

2. 選取 [ **密碼永不過期」** 核取方塊，然後按一下 [ **確定**。

   > [!NOTE]
   > 選取 **密碼永不過期** 是密碼Microsoft Teams 會議室。 您的網域規則可能會禁止不會過期的密碼。 如果是這樣，您必須為每個帳戶建立例外Microsoft Teams 會議室例外。

### <a name="assign-a-microsoft-365-or-office-365-license"></a>指派授權Microsoft 365或Office 365授權

1. 連線Azure Active Directory。 有關此Azure Active Directory，請參閱[Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0)。 

   > [!NOTE]
   > [Azure Active Directory不支援 PowerShell 2.0。](/powershell/azure/active-directory/overview?view=azureadps-2.0) 

2. 資源帳戶必須擁有有效的授權Microsoft 365授權Office 365，否則Exchange Microsoft Teams無效。 如果您有授權，您必須將使用位置指派給資源帳戶，這決定您的帳戶可以使用哪些授權 SKUs。 您可以使用 `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> 以取回可用的 SKUS 清單。

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

3. 接下來，您可以使用 `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> Cmdlet。 此範例新增會議室授權至帳戶：

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

若要驗證，您應該可以使用任何用戶端登入此帳戶。
  
## <a name="related-topics"></a>相關主題

[設定帳戶Microsoft Teams 會議室](rooms-configure-accounts.md)

[規劃 Microsoft Teams 會議室](rooms-plan.md)
  
[部署 Microsoft Teams 會議室](rooms-deploy.md)
  
[設定 Microsoft Teams 會議室主控台](console.md)
  
[管理 Microsoft Teams 會議室](rooms-manage.md)
