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
ms.openlocfilehash: 15936a805e45ce17ec35822bb02980b4d47499b8
ms.sourcegitcommit: 1165a74b1d2e79e1a085b01e0e00f7c65483d729
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/08/2021
ms.locfileid: "61355612"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises-hybrid"></a>在Microsoft Teams 會議室部署Exchange混合式Exchange部署 () 

請閱讀本主題，瞭解如何在混合式環境中Microsoft Teams 會議室內部部署Exchange部署Microsoft Teams。
  
如果貴組織有混合式服務，其中一些是內部部署，有些是線上託管，則您的組式取決於每個服務的託管位置。 本主題涵蓋使用內部部署Microsoft Teams 會議室Exchange的混合式部署。 由於這類部署有許多不同的變化，因此無法針對所有部署提供詳細指示。 下列程式適用于許多配置。 如果此程式不適用於您的設定，建議您使用 Windows PowerShell來達到此處所記載的相同最終結果，以及其他部署選項。
  
## <a name="requirements"></a>需求

在內部Microsoft Teams 會議室部署Exchange，請確定您符合需求。 詳細資訊，請參閱Microsoft Teams 會議室[需求](requirements.md)。
  
如果您是使用內部Microsoft Teams 會議室部署Exchange，您將使用 Active Directory 管理工具為您的內部部署網域帳戶新增電子郵件地址。 此帳戶會同步到 Microsoft 365 或 Office 365。 您必須：
  
- 建立帳戶，並同步處理帳戶Azure Active Directory。

- 啟用遠端信箱並設定屬性。

- 指派授權Microsoft 365或Office 365授權。

### <a name="create-an-account-and-synchronize-with-azure-active-directory"></a>建立帳戶並Azure Active Directory

1. 在 **Active Directory 使用者** 與電腦工具中，以滑鼠右鍵按一下要建立您 Microsoft Teams 會議室 帳戶的資料夾或組織單位，按一下 [**新增**，然後按一下 **[使用者**> 。

2. 在全名方塊中輸入顯示名稱，將別名輸入到使用者 **登入名稱** 方塊中。 按一下 **[下一步**。

3. 輸入此帳戶的密碼。 您必須重新輸入以進行驗證。 請確定選取 **的唯** 一選項為密碼永不過期核取方塊。

    > [!NOTE]
    > 選取 **密碼永不過期** 是密碼Microsoft Teams 會議室。 您的網域規則可能會禁止不會過期的密碼。 如果是這樣，您必須為每個帳戶建立例外Microsoft Teams 會議室例外。
  
4. 建立帳戶之後，請執行目錄同步處理。 完成後，請前往您帳戶的使用者頁面Microsoft 365 系統管理中心並確認先前步驟中建立的帳戶已同步到線上。

### <a name="enable-the-remote-mailbox-and-set-properties"></a>啟用遠端信箱和設定屬性

1. [開啟 Exchange管理命令殼](/powershell/exchange/exchange-server/open-the-exchange-management-shell)，或使用遠端[PowerShell Exchange伺服器。](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)

2. 在 Exchange PowerShell 中，為帳戶建立信箱 (信箱，) 下列命令來啟用帳戶：

   ```PowerShell
   Enable-Mailbox ConferenceRoom01@contoso.com -Room
   ```

   有關詳細的語法和參數資訊，請參閱 [啟用信箱](/powershell/module/exchange/mailboxes/enable-mailbox)。

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

### <a name="assign-a-microsoft-365-or-office-365-license"></a>指派授權Microsoft 365或Office 365授權

1. 連線Azure Active Directory。 有關此Azure Active Directory，請參閱[Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0)。 

   > [!NOTE]
   > [Azure Active Directory不支援 PowerShell 2.0。](/powershell/azure/active-directory/overview?view=azureadps-2.0) 

2. 資源帳戶必須擁有有效的授權Microsoft 365授權Office 365，Exchange Microsoft Teams無法使用。 如果您有授權，您必須將使用位置指派給資源帳戶，這決定您的帳戶可以使用哪些授權 SKUs。 您可以使用 `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> 以取回可用的 SKUS 清單。

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. 接下來，您可以使用 `Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> Cmdlet。 在此案例中，$strLicense就是您看到的 SKU 程式碼， (contoso：STANDARDPACK) 。

  ``` PowerShell
  Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
  Get-MsolAccountSku
  Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses $strLicense
  ```

<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```  -->

   有關詳細指示，請參閱使用 PowerShell 指派授權[Office 365使用者帳戶](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)。

若要驗證，您應該可以使用任何用戶端登入此帳戶。
  
## <a name="related-topics"></a>相關主題

[設定帳戶Microsoft Teams 會議室](rooms-configure-accounts.md)

[規劃 Microsoft Teams 會議室](rooms-plan.md)
  
[部署 Microsoft Teams 會議室](rooms-deploy.md)
  
[設定 Microsoft Teams 會議室主控台](console.md)
  
[管理 Microsoft Teams 會議室](rooms-manage.md)
