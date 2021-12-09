---
title: 使用 Microsoft Teams 會議室 部署Exchange Online
ms.author: dstrome
author: dstrome
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
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: 請閱讀本主題，以瞭解如何在內部部署Microsoft Teams 會議室部署Exchange Online商務用 Skype Server部署。
ms.openlocfilehash: 8f8511f4dd05b6d2eb073aaab0a14305c9d67831
ms.sourcegitcommit: 1165a74b1d2e79e1a085b01e0e00f7c65483d729
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/08/2021
ms.locfileid: "61355632"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>使用 Microsoft Teams 會議室 部署Exchange Online

請閱讀本主題，以瞭解如何使用 Microsoft Teams 會議室 部署Exchange Online。
  
如果貴組織有混合式服務，其中一些是內部部署，有些是線上託管，則您的組式取決於每個服務的託管位置。 本主題涵蓋使用線上託管Microsoft Teams 會議室的Exchange部署。 由於這類部署有許多不同的變化，因此無法針對所有部署提供詳細指示。 下列程式適用于許多配置。 如果此程式不適用於您的設定，建議您使用 Windows PowerShell來達到此處所記載的相同最終結果，以及其他部署選項。

## <a name="requirements"></a>需求

使用 Microsoft Teams 會議室部署Exchange Online，請確定您符合需求。 詳細資訊，請參閱Microsoft Teams 會議室[需求](requirements.md)。
  
若要使用 Microsoft Teams 會議室 部署Exchange Online，請遵循下列步驟。 請確定您擁有執行關聯的 Cmdlet 的許可權。 

   > [!NOTE]
   >  本節 Azure Active Directory 中 Windows PowerShell [Cmdlet](/powershell/azure/active-directory/overview)的模組 (例如 Set-MsolUser) 已針對 Microsoft Teams 會議室 裝置設定帳戶進行測試。 不過，其他 Cmdlet 可能可以工作，但尚未在此特定情況下進行測試。

如果您部署 Active Directory Federation Services (AD FS) ，您可能必須先將使用者帳戶轉換為受管理的使用者，然後再執行這些步驟，然後在完成這些步驟後將使用者轉換回聯合使用者。
  
### <a name="create-an-account-and-set-exchange-properties"></a>建立帳戶並設定Exchange屬性

1. 在 PC 上Windows PowerShell遠端會話，並Exchange Online方式：

    ``` Powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline
    ```

2. 建立會話之後，您可以建立新信箱，並啟用為 RoomMailboxAccount，或變更現有會議室信箱的設定。 這會允許帳戶驗證至 Microsoft Teams 會議室。

   如果您要變更現有的資源信箱：

   ``` Powershell
   Set-Mailbox -Identity 'ConferenceRoom01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    如果您要建立新資源信箱：

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'ConferenceRoom01@contoso.com' -Alias ConferenceRoom01 -Name "Conference Room 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 若要改善會議體驗，您必須將使用者帳戶Exchange屬性設定如下：

   ``` Powershell
   Set-CalendarProcessing -Identity 'ConferenceRoom01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'ConferenceRoom01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>為您的內部部署網域帳戶新增電子郵件地址

1. 在 **Active Directory 使用者** 與電腦 AD 工具中，以滑鼠右鍵按一下要建立 Microsoft Teams 會議室 帳戶的容器或組織單位，按一下 [**新增**，然後按一下 **[使用者**> 。
2. 從先前的 Cmdlet (Set-Mailbox 或 New-Mailbox) 輸入顯示名稱 ( ) - 身分識別) ，將別名輸入到使用者 **登** 入名稱方塊中。  按一下 **[下一步**。
3. 輸入此帳戶的密碼。 您必須重新輸入以進行驗證。 請確定選取 **的唯** 一選項為密碼永不過期核取方塊。

    > [!NOTE]
    > 選取 **密碼永不過期** 是商務用 Skype Server Microsoft Teams 會議室。 您的網域規則可能會禁止不會過期的密碼。 如果是這樣，您必須為每個使用者帳戶建立例外Microsoft Teams 會議室例外。
  
4. 按一下 **[完成** 並建立帳戶。
5. 建立帳戶之後，請執行目錄同步處理。 您可以在 PowerShell 中使用 [Set-MsolDirSyncConfiguration 來](/powershell/module/msonline/set-msoldirsyncconfiguration) 完成這項工作。 完成時，請前往使用者頁面，並確認先前步驟所建立之兩個帳戶已合併。

### <a name="assign-a-microsoft-365-or-office-365-license"></a>指派授權Microsoft 365或Office 365授權

1. 首先，請Azure AD以申請一些帳戶設定。 您可以執行此 Cmdlet 以連接。 有關 Active Directory 的詳細資訊，請參閱 [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview)。

   > [!NOTE]
   > [Azure Active Directory不支援 PowerShell 2.0。](/powershell/azure/active-directory/overview)

    ``` PowerShell
   Connect-MsolService
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. 使用者帳戶必須擁有有效的授權Microsoft 365或Office 365，以確保Exchange有效。 如果您有授權，您必須將使用位置指派給使用者帳戶，這決定您的帳戶可以使用哪些授權 SKUs。 您將在下列步驟中進行作業。
3. 接下來，使用 `Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> 來為貴組織或組織Microsoft 365 SKUS Office 365清單。
4. 您可以使用 `Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> Cmdlet。 在這種情況下，系統Microsoft Teams 會議室標準版授權。 

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
    Get-MsolAccountSku
    Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses "contoso:MEETING_ROOM"
    ```
  <!--   ``` Powershell
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
     Get-AzureADSubscribedSku
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
     ``` -->

## <a name="related-topics"></a>相關主題

[設定帳戶Microsoft Teams 會議室](rooms-configure-accounts.md)

[規劃 Microsoft Teams 會議室](rooms-plan.md)
  
[部署 Microsoft Teams 會議室](rooms-deploy.md)
  
[設定 Microsoft Teams 會議室主控台](console.md)
  
[管理 Microsoft Teams 會議室](rooms-manage.md)
