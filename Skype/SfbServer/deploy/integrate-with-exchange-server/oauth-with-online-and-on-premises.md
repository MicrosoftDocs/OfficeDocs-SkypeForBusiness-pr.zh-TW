---
title: 商務用 Skype 線上與 Exchange 伺服器之間的整合
ms.reviewer: cbland
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: 設定 Exchange 內部部署和商務用 Skype 線上之間的 OAuth 驗證，可啟用功能支援中所述的商務用 Skype 及 Exchange 整合功能。
ms.openlocfilehash: 8342fefa10fcd66cd7cd10c121b787a05a7a0401d5235bbc70b2412bb538e5e4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300279"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a>設定商務用 Skype 線上和 Exchange Server 之間的整合及 OAuth 

設定 Exchange server 與商務用 Skype Online 之間的整合，可啟用[功能支援](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)中所述的商務用 Skype 和 Exchange 整合功能。

本主題適用于與 Exchange Server 2013 到2019的整合。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 完成此工作的預估時間：15 分鐘

-  您必須已獲指派權限，才能執行此程序或這些程序。 若要查看您需要的許可權，請參閱[Exchange 和命令介面基礎結構許可權](/exchange/exchange-and-shell-infrastructure-permissions-exchange-2013-help)主題。

- 如需適用於此主題中程序的快速鍵相關資訊，請參閱 [Exchange 系統管理中心的鍵盤快速鍵]( https://go.microsoft.com/fwlink/p/?LinkId=746512)。

- 如需相容性的相關資訊，請參閱[商務用 Skype 與 Office 應用程式相容性](../../plan-your-deployment/clients-and-devices/compatibility-with-office.md)。

## <a name="configure-integration-between-exchange-server-and-o365"></a>設定 Exchange Server 和 O365 之間的整合

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>步驟1：設定 Exchange Server 和 O365 之間的 OAuth 驗證

執行下列文章中的步驟：

[設定 Exchange 與 Exchange Online 組織之間的 OAuth 驗證](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>步驟2：為商務用 Skype Online 夥伴應用程式建立新的郵件使用者帳戶

此步驟是在 Exchange 伺服器上完成。 它會建立郵件使用者，並為其指派適當的管理角色權力。 然後，將在下一個步驟中使用此帳戶。

為您的 Exchange 組織指定已驗證的網域。 這個網域應該是用來做為內部部署 Exchange 帳戶使用的主要 SMTP 網域的相同網域。 下列程式中稱為此網域 \<your Verified Domain\> 。 此外， \<DomainControllerFQDN\> 應為網域控制站的 FQDN。

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

此命令會將新的郵件使用者從通訊清單中隱藏。

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

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a>步驟3：建立及啟用商務用 Skype 線上的夥伴應用程式 

建立新的夥伴應用程式，並將使用您剛才建立的帳戶。 在內部部署 Exchange 組織的 Exchange PowerShell 中執行下列命令。

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a>步驟4：匯出內部部署授權憑證

執行 PowerShell 腳本，以匯出內部部署授權憑證，在下一個步驟中，您將匯入到商務用 Skype Online 組織。

將下列文字儲存到 PowerShell 指令碼檔案 (例如 ExportAuthCert.ps1)。

```powershell
$thumbprint = (Get-AuthConfig).CurrentCertificateThumbprint
if((test-path $env:SYSTEMDRIVE\OAuthConfig) -eq $false)
{
md $env:SYSTEMDRIVE\OAuthConfig
}
cd $env:SYSTEMDRIVE\OAuthConfig
$oAuthCert = (dir Cert:\LocalMachine\My) | where {$_.Thumbprint -match $thumbprint}
$certType = [System.Security.Cryptography.X509Certificates.X509ContentType]::Cert
$certBytes = $oAuthCert.Export($certType)
$CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
[System.IO.File]::WriteAllBytes($CertFile, $certBytes)
```

在內部部署 Exchange 組織 Exchange PowerShell 中，執行您剛才建立的 PowerShell 腳本。 例如： .\ExportAuthCert.ps1

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>步驟5：將內部部署授權憑證 Upload Azure Active Directory ACS

接下來，使用 Windows PowerShell 上載您在上一個步驟中匯出的內部部署授權憑證，以 Azure Active Directory (ACS) 的存取控制服務。 若要這麼做，必須已安裝 Windows PowerShell Cmdlet 的 Azure Active Directory 模組。 若未安裝，請移至，以 [https://aka.ms/aadposh](/previous-versions/azure/jj151815(v=azure.100)) 安裝 Windows PowerShell 的 Azure Active Directory 模組。 在安裝 Windows PowerShell 的 Azure Active Directory 模組後，請完成下列步驟。

1. 按一下 Windows PowerShell 快捷方式的 **Azure Active Directory 模組**，開啟已安裝 Azure AD Cmdlet 的 Windows PowerShell 工作區。 在此步驟中的所有命令，都將使用 Azure Active Directory 主控台的 Windows PowerShell 執行。

2. 將下列文字儲存至名為的 PowerShell 腳本檔案，例如  `UploadAuthCert.ps1` 。

   ```powershell
   Connect-MsolService;
   Import-Module msonlineextended;
   $CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
   $objFSO = New-Object -ComObject Scripting.FileSystemObject;
   $CertFile = $objFSO.GetAbsolutePathName($CertFile);
   $cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
   $cer.Import($CertFile);
   $binCert = $cer.GetRawCertData();
   $credValue = [System.Convert]::ToBase64String($binCert);
   $ServiceName = "00000004-0000-0ff1-ce00-000000000000";
   $p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName
   New-MsolServicePrincipalCredential -AppPrincipalId $p.AppPrincipalId -Type asymmetric -Usage Verify -Value $credValue
   ```

3. 執行您在前一個步驟中建立的 PowerShell 指令碼。 例如：  `.\UploadAuthCert.ps1`

4. 啟動指令碼之後，即會顯示認證對話方塊。 輸入您的 Microsoft Online Azure AD 組織之租使用者系統管理員帳戶的認證。 執行腳本後，請保持 Azure AD 會話的 Windows PowerShell 開啟。 您將在下一個步驟中以此工作階段執行 PowerShell 指令碼。

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a>步驟6：確認憑證已上傳至商務用 Skype 服務主體
1. 在 PowerShell 開啟和驗證以 Azure Active Directory 中，執行下列
```powershell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. 當系統提示 ReturnKeyValues 時按 Enter 鍵
3. 確認您會看到列出的 [開始日期] 和 [結束] 資料符合 Exchange 的 Oauth 憑證開始和結束日期的按鍵

### <a name="verify-your-success"></a>驗證您是否成功

驗證某些功能是否順利運作，以驗證設定是否正確。 

1. 在具有混合式 Exchange Server 設定的組織中，確認商務用 Skype 具有雲端語音信箱服務的使用者能夠成功變更其語音信箱問候語。

2. 確認行動用戶端的交談記錄會顯示在 [Outlook 交談記錄] 資料夾中。

3. 使用 [EWSEditor](/archive/blogs/webdav_101/where-to-get-ewseditor)，確認已封存的聊天訊息會存放在使用者的內部部署信箱中的 [清除] 資料夾中。

或者，查看您的流量。 OAuth 握手中的流量十分獨特 (而且看起來不像基本驗證) （特別是在領域之外），您可以在這裡看到如下所示的發行人流量： 00000004-0000-0ff1-ce00-000000000000 @ (有時候會在所傳遞的標記中使用 @ 符號) 。 您不會看到使用者名稱或密碼，也就是 OAuth 的點。 不過，您會看到「Office ' 簽發者–在此例中，為 "4" 是商務用 Skype –和您的訂閱領域。

如果您想要確定成功使用 OAuth，請確定您知道預期的內容，並知道流量應該類似。 以下是您 [預期的目標](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)，以下是 [Microsoft 應用 (程式中 OAuth 流量的](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  一個很好的標準範例，雖然它不會使用重新整理權杖) ，但仍有 Fiddler 擴充功能可讓您查看 OAuth JWT (JSON Web Token) 。

以下是 [一個設定的範例](/archive/blogs/kaevans/updated-fiddler-oauth-inspector)，但是您可以使用任何您想要執行此程式的網路追蹤工具。

## <a name="related-topics"></a>相關主題

[設定 Exchange 與 Exchange Online 組織之間的 OAuth 驗證](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)