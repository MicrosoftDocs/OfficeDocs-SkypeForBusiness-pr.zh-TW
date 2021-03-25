---
title: 使用 Exchange Online 部署 Microsoft Teams 會議室
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
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: 請閱讀本主題，以瞭解如何使用 Exchange Online 部署 Microsoft Teams 會議室，以及商務用 Skype Server 內部部署。
ms.openlocfilehash: 5e3446349be8aaef666c02c73370758027736181
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117341"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>使用 Exchange Online 部署 Microsoft Teams 會議室

請閱讀本主題，以瞭解如何使用 Exchange Online 部署 Microsoft Teams 會議室，以及商務用 Skype Server 內部部署。
  
如果貴組織有混合式服務，其中一些是內部部署，有些是線上託管，則您的組式取決於每個服務的託管位置。 本主題涵蓋線上託管 Exchange 的 Microsoft Teams 會議室混合式部署。 由於這類部署有許多不同的變化，因此無法針對所有部署提供詳細指示。 下列程式適用于許多配置。 如果此程式不適用於您的設定，建議您使用 Windows PowerShell 達到與本文所述相同的最終結果，以及其他部署選項。

設定使用者帳戶最簡單的方法是使用遠端 Windows PowerShell 來設定使用者帳戶。 Microsoft 提供 [SkypeRoomProvisioningScript.ps1， ](https://go.microsoft.com/fwlink/?linkid=870105)此腳本可協助建立新的使用者帳戶，或驗證您現有的資源帳戶，以便協助您將帳戶轉換為相容的 Microsoft Teams 會議室使用者帳戶。 視需要，您可以遵循下列步驟來設定 Microsoft Teams 會議室裝置將會使用的帳戶。

## <a name="requirements"></a>需求

使用 Exchange Online 部署 Microsoft Teams 會議室之前，請確定您符合需求。 詳細資訊，請參閱 [Microsoft Teams 會議室需求](requirements.md)。
  
若要使用 Exchange Online 部署 Microsoft Teams 會議室，請遵循下列步驟。 請確定您擁有執行關聯的 Cmdlet 的許可權。 

   > [!NOTE]
   >  本節 [中的 Windows PowerShell](/powershell/azure/active-directory/overview?view=azureadps-1.0) Azure Active Directory 模組 Cmdlet (例如 Set-MsolUser) 已經過設定 Microsoft Teams 會議室裝置帳戶的測試。 不過，其他 Cmdlet 可能可以工作，但尚未在此特定情況下進行測試。

如果您部署 Active Directory Federation Services (AD FS) ，您可能必須先將使用者帳戶轉換為受管理的使用者，然後再執行這些步驟，然後在完成這些步驟後將使用者轉換回聯盟使用者。
  
### <a name="create-an-account-and-set-exchange-properties"></a>建立帳戶並設定 Exchange 屬性

1. 在 PC 上啟動遠端 Windows PowerShell 會話，然後連線到 Exchange Online，如下所示：

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org = 'contoso.microsoft.com'
    $cred = Get-Credential $admin@$org
    $sess = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
    Import-PSSession $sess -DisableNameChecking
    ```

2. 建立會話之後，您可以建立新信箱並啟用為 RoomMailboxAccount，或變更現有會議室信箱的設定。 這會允許帳戶驗證至 Microsoft Teams 會議室。

   如果您要變更現有的資源信箱：

   ``` Powershell
   Set-Mailbox -Identity 'PROJECT01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    如果您要建立新資源信箱：

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECT01@contoso.com' -Alias PROJECT01 -Name "Project--01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 若要改善會議體驗，您必須在使用者帳戶上設定 Exchange 屬性，如下所示：

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>為您的內部部署網域帳戶新增電子郵件地址

1. 在 **Active Directory 使用者和電腦 AD** 工具中，以滑鼠右鍵按一下要建立 Microsoft Teams 會議室帳戶的容器或組織單位，按一下 [ **新增**，然後按一下 **[使用者**> 。
2. 從先前的 Cmdlet (Set-Mailbox 或 New-Mailbox) 輸入顯示名稱 ( ) - 身分識別) ，將別名輸入到使用者 **登** 入名稱方塊。 按一下 **[下一步**。
3. 輸入此帳戶的密碼。 您必須重新輸入以進行驗證。 請確定選取 **的唯** 一選項為密碼永不過期核取方塊。

    > [!NOTE]
    > 選取 **密碼永不過期** 是 Microsoft Teams 會議室商務用 Skype Server 的一項需求。 您的網域規則可能會禁止密碼過期。 如果是這樣，您必須為每個 Microsoft Teams 會議室使用者帳戶建立例外。
  
4. 按一下 **[完成** 並建立帳戶。
5. 建立帳戶之後，請執行目錄同步處理。 您可以在 PowerShell 中使用 [Set-MsolDirSyncConfiguration 來](/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) 完成這項工作。 完成時，請前往使用者頁面，並確認先前步驟所建立之兩個帳戶已合併。

### <a name="assign-a-microsoft-365-or-office-365-license"></a>指派 Microsoft 365 或 Office 365 授權

1. 首先，請連接到 Azure AD 以申請一些帳戶設定。 您可以執行此 Cmdlet 以連接。 有關 Active Directory 的詳細資訊，請參閱 [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0)。

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) 不受支援。

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. 使用者帳戶必須擁有有效的 Microsoft 365 或 Office 365 授權，以確保 Exchange 和商務用 Skype Server 能夠工作。 如果您有授權，您必須將使用位置指派給使用者帳戶，這決定您的帳戶可以使用哪些授權 SKUs。 您將在下列步驟中進行作業。
3. 接下來，使用 `Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> 以針對您的 Microsoft 365 或 Office 365 組織，來取回可用的 SUS 清單。
4. 列出 SKUs 之後，您可以使用 `Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> Cmdlet。 在此案例中，$strLicense是您看到的 SKU 程式碼， (contoso：STANDARDPACK) 。 

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
    Get-MsolAccountSku
    Set-MsolUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
    ```
  <!--   ``` Powershell
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
     Get-AzureADSubscribedSku
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
     ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a>使用商務用 Skype Server 啟用使用者帳戶

1. 從電腦建立遠端 Windows PowerShell 會話，如下所示：

> [!NOTE]
> 商務用 Skype Online Connector 目前是 Teams PowerShell 最新模組的一部分。
>
> 如果您使用的是最新的 [Teams PowerShell 公開發行](https://www.powershellgallery.com/packages/MicrosoftTeams/)，則不需要安裝商務用 Skype Online 連接器。

    ``` Powershell
    # When using Teams PowerShell Module
    Import-Module MicrosoftTeams
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

2. 若要啟用商務用 Skype Server 的 Microsoft Teams 會議室帳戶，請執行此命令：

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    如果您不確定環境中要用於 RegistrarPool 參數的值，您可以使用此命令從現有的商務用 Skype Server 使用者取得值

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a>將商務用 Skype Server 授權指派至您的 Microsoft Teams 會議室帳戶

1. 以租使用者系統管理員登入，開啟 Microsoft 365 系統管理中心，然後按一下系統管理應用程式。
2. 按一下 [ **使用者與群組** ，然後按一下 **[新增使用者、重設密碼等>**。
3. 按一下 Microsoft Teams 會議室帳戶，然後按一下觸控筆圖示以編輯帳戶資訊。
4. 按一下 **[授權>**。
5. 在 **指派授權** 中， (方案 2) 或商務用 Skype (方案 3) 視您的授權和企業語音需求。 如果您想要在 Microsoft Teams 會議室使用企業語音，您必須使用方案 3 授權。
6. 按一下 [儲存]。

若要進行驗證，您應該可以使用任何商務用 Skype 用戶端登入此帳戶。

> [!NOTE]
> 如果您目前使用 E1、E3、E4 或 E5 SKUS 與商務用 Skype 方案 2 與音訊會議或電話系統及通話方案，這些將會繼續使用。 不過，您應該考慮在目前的授權到期後，使用 [Teams 會議室](rooms-licensing.md)授權更新中所述的更簡單的授權模型。

> [!IMPORTANT]
> 如果您使用的是商務用 Skype 方案 2，則只能在商務用 Skype 模式使用 Microsoft Teams 會議室，這表示所有會議都是商務用 Skype 會議。 為了啟用您的會議室進行 Microsoft Teams 會議，我們建議您購買會議室授權。
  
## <a name="related-topics"></a>相關主題

[設定 Microsoft Teams 會議室的帳戶](rooms-configure-accounts.md)

[規劃 Microsoft Teams 會議室](rooms-plan.md)
  
[部署 Microsoft Teams 會議室](rooms-deploy.md)
  
[設定 Microsoft Teams 會議室主控台](console.md)
  
[管理 Microsoft Teams 會議室](rooms-manage.md)