---
title: 商務用 Skype Online 與 Exchange Server 之間的整合
ms.reviewer: cbland
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 02/17/2022
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: 在 Exchange 內部部署與商務用 Skype Online 之間設定 OAuth 驗證，可啟用功能支援中所述的商務用 Skype 和 Exchange 整合功能。
ms.openlocfilehash: 0b312dfde144f12a9c2db523ce4526153b445d59
ms.sourcegitcommit: e3931446943684db155bb3edf7d7e52d41775013
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2022
ms.locfileid: "65886640"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a>設定商務用 Skype Online 與 Exchange Server 之間的整合和 OAuth 

設定 Exchange Server 與商務用 Skype Online 之間的整合，可啟用 [功能支援](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)中所述的商務用 Skype 和 Exchange 整合功能。

本主題適用于與 Exchange Server 2013 到 2019 的整合。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 完成此工作的預估時間：15 分鐘

-  您必須已獲指派權限，才能執行此程序或這些程序。 若要查看您需要的許可權，請參閱 [Exchange 和 Shell 基礎結構許可權](/exchange/exchange-and-shell-infrastructure-permissions-exchange-2013-help) 主題。

- 如需適用於此主題中程序的快速鍵相關資訊，請參閱 [Exchange 系統管理中心的鍵盤快速鍵]( https://go.microsoft.com/fwlink/p/?LinkId=746512)。

- 如需相容性的資訊，請參閱 [商務用 Skype 與 Office 應用程式的相容性](../../plan-your-deployment/clients-and-devices/compatibility-with-office.md)。

## <a name="configure-integration-between-exchange-server-and-o365"></a>設定 Exchange Server 與 O365 之間的整合

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>步驟 1：設定 Exchange Server 與 O365 之間的 OAuth 驗證

執行下列文章中的步驟：

[設定 Exchange 與 Exchange Online 組織之間的 OAuth 驗證](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>步驟 2：為商務用 Skype Online 合作夥伴應用程式建立新的郵件使用者帳戶

此步驟是在 Exchange Server 上完成。 它會建立郵件使用者，並為其指派適當的管理角色許可權。 此帳戶接著會在下一個步驟中使用。

為您的 Exchange 組織指定已驗證的網域。 此網域應與用於內部部署 Exchange 帳戶的主要 SMTP 網域相同。 此網域在下列程式中稱為 \<your Verified Domain\> 。 此外， \<DomainControllerFQDN\> 應該是網域控制站的 FQDN。

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

此命令會從通訊清單中隱藏新的郵件使用者。

```powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

接下來的兩個命令會將 UserApplication 和 ArchiveApplication 管理角色指派給這個新帳戶。

```powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a>步驟 3：建立及啟用商務用 Skype Online 的合作夥伴應用程式 

建立新的合作夥伴應用程式，並使用您剛才建立的帳戶。 在內部部署 Exchange 組織的 Exchange PowerShell 中執行下列命令。

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a>步驟 4：匯出內部部署授權憑證

執行 PowerShell 腳本來匯出內部部署授權憑證，您將在下一個步驟中匯入至商務用 Skype Online 組織。

將下列文字儲存到 PowerShell 指令碼檔案 (例如 ExportAuthCert.ps1)。

```powershell
$thumbprint = (Get-AuthConfig).CurrentCertificateThumbprint
if((test-path $env:SYSTEMDRIVE\OAuthConfig) -eq $false) {
    md $env:SYSTEMDRIVE\OAuthConfig
}
cd $env:SYSTEMDRIVE\OAuthConfig
$oAuthCert = (dir Cert:\LocalMachine\My) | where {$_.Thumbprint -match $thumbprint}
$certType = [System.Security.Cryptography.X509Certificates.X509ContentType]::Cert
$certBytes = $oAuthCert.Export($certType)
$CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
[System.IO.File]::WriteAllBytes($CertFile, $certBytes)
```

在內部部署 Exchange 組織中的 Exchange PowerShell 中，執行您剛才建立的 PowerShell 腳本。 例如：.\ExportAuthCert.ps1

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>步驟 5：將內部部署授權憑證上傳至 Azure Active Directory ACS

接下來，使用 Windows PowerShell 將您在上一個步驟中匯出的內部部署授權憑證上傳至 Azure Active Directory 存取控制服務 (ACS) 。 若要這樣做，必須已安裝適用于 Windows PowerShell 的 Azure Active Directory 模組 Cmdlet。 如果未安裝，請移至 [https://aka.ms/aadposh](/previous-versions/azure/jj151815(v=azure.100)) 安裝適用于 Windows PowerShell 的 Azure Active Directory 模組。 安裝適用于 Windows PowerShell 的 Azure Active Directory 模組之後，請完成下列步驟。

1. 按一下 **適用于 Windows PowerShell 的 Azure Active Directory 模組** 快捷方式，開啟已安裝 Azure AD Cmdlet 的 Windows PowerShell 工作區。 此步驟中的所有命令都會使用 Windows PowerShell for Azure Active Directory 主控台來執行。

2. 將下列文字儲存至名為 的 PowerShell 腳本檔案，例如  `UploadAuthCert.ps1` 。

   ```powershell
   Connect-MsolService
   Import-Module MSOnline
   $CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
   $objFSO = New-Object -ComObject Scripting.FileSystemObject
   $CertFile = $objFSO.GetAbsolutePathName($CertFile);
   $cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
   $cer.Import($CertFile)
   $binCert = $cer.GetRawCertData();
   $credValue = [System.Convert]::ToBase64String($binCert)
   $ServiceName = "00000004-0000-0ff1-ce00-000000000000"
   $p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName
   New-MsolServicePrincipalCredential -AppPrincipalId $p.AppPrincipalId -Type asymmetric -Usage Verify -Value $credValue
   ```

3. 執行您在前一個步驟中建立的 PowerShell 指令碼。 例如：  `.\UploadAuthCert.ps1`

4. 啟動指令碼之後，即會顯示認證對話方塊。 輸入 Microsoft Online Azure AD 組織的租使用者系統管理員帳號憑證。 執行腳本之後，讓 Windows PowerShell for Azure AD 會話保持開啟。 您將在下一個步驟中以此工作階段執行 PowerShell 指令碼。

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a>步驟 6：確認憑證已上傳至商務用 Skype 服務主體
1. 在已開啟並向 Azure Active Directory 驗證的 PowerShell 中，執行下列命令

   ```powershell
   Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
   ```
2. 當系統提示您輸入 ReturnKeyValues 時，按 Enter 鍵
3. 確認您看到列出的金鑰具有符合 Exchange Oauth 憑證開始和結束日期的開始日期和結束資料

### <a name="verify-your-success"></a>確認您的成功

確認某些功能已順利運作，以確認設定正確無誤。 

1. 確認具有雲端語音信箱服務的商務用 Skype 使用者，在具有混合式 Exchange Server 設定的組織中，可以成功變更其語音信箱問候語。

2. 確認行動用戶端的交談歷程記錄顯示在 Outlook 對話記錄資料夾中。

3. 使用 [EWSEditor](/archive/blogs/webdav_101/where-to-get-ewseditor)確認封存的聊天訊息會存放在使用者內部部署信箱的 [清除] 資料夾中。

或者，查看您的流量。 OAuth 交握中的流量非常特別 (，看起來不像基本驗證) 特別是領域，您會開始看到如下所示的簽發者流量：000000004-0000-0ff1-ce00-000000000000 (@ 有時會在傳遞的權杖中，于 @ 符號) 之前使用 /。 您不會看到使用者名稱或密碼，也就是 OAuth 的點。 但您會看到 'Office' 簽發者 –在此案例中，'4' 是商務用 Skype – 以及您訂用帳戶的領域。

如果您想要確定您已成功使用 OAuth，請確定您知道預期的結果，並知道流量看起來應該的樣子。 以下是 [預期的情況](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)，以下是 [Microsoft 應用程式中 OAuth 流量](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  的一個相當標準範例 (讀取非常有説明，但它不會使用重新整理權杖) ，而且有 Fiddler 延伸模組可讓您查看 OAuth JWT (JSON Web 權杖) 。

以下是 [設定一個的範例](/archive/blogs/kaevans/updated-fiddler-oauth-inspector)，但您可以使用任何您想要執行此程式的網路追蹤工具。

## <a name="related-topics"></a>相關主題

[設定 Exchange 與 Exchange Online 組織之間的 OAuth 驗證](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
