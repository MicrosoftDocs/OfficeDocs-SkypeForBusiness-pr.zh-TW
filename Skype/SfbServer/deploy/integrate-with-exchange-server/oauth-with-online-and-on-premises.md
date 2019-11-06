---
title: 商務用 Skype Online 與 Exchange server 之間的整合
ms.reviewer: cbland
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: 在 Exchange 內部部署與商務用 Skype Online 之間設定 OAuth 驗證，可啟用功能支援中所述的商務用 Skype 與 Exchange 整合功能。
ms.openlocfilehash: 1d64f8fe7b2d6dcf276ae34e74c84faf5c93f65a
ms.sourcegitcommit: 2b4fcf2561134b9f1b9a1b49401d97da1286e89d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/05/2019
ms.locfileid: "37979776"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a>在商務用 Skype Online 與 Exchange Server 之間設定整合與 OAuth 

設定 Exchange server 與商務用 Skype Online 之間的整合，可啟用[功能支援](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)中所述的商務用 Skype 與 Exchange 整合功能。

本主題適用于與 Exchange Server 2013 至2019的整合。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前，您需要知道什麼？

- 完成此工作所需的估計時間：15分鐘

-  您必須先獲指派許可權，才能執行此程式或程式。 若要查看您需要的許可權，請參閱[Exchange 與 Shell 基礎結構許可權](https://go.microsoft.com/fwlink/p/?LinkId=746511)主題。

- 如需有關適用于本主題中之程式的鍵盤快速鍵的詳細資訊，請參閱[Exchange 系統管理中心的鍵盤快速鍵]( https://go.microsoft.com/fwlink/p/?LinkId=746512)。

- 如需相容性的相關資訊，請參閱[商務用 Skype 與 Office app 的相容性](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office)。

## <a name="configure-integration-between-exchange-server-and-o365"></a>設定 Exchange Server 與 O365 之間的整合

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>步驟1：在 Exchange Server 和 O365 之間設定 OAuth 驗證

請執行下列文章中的步驟：

[在 Exchange 與 Exchange Online 組織之間設定 OAuth 驗證](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>步驟2：針對商務用 Skype Online 合作夥伴應用程式建立新的郵件使用者帳戶

此步驟是在 Exchange 伺服器上完成。 它會建立一個郵件使用者，並將適當的管理角色許可權指派給它。 這個帳戶將會在下一個步驟中使用。

為您的 Exchange 組織指定驗證的網域。 這個網域應該是用來做為內部部署 Exchange 帳戶的主要 SMTP 網域的同一個網域。 在下列程式中， \<這個網域稱為\>您的驗證網域。 此外， \<DomainControllerFQDN\>應該是網網域控制站的 FQDN。

``` Powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

這個命令會將新的郵件使用者從地址清單中隱藏。

``` Powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

接下來的兩個命令會將 [UserApplication] 和 [ArchiveApplication] 管理角色指派給這個新的帳戶。

``` Powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

``` Powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a>步驟3：針對商務用 Skype Online 建立及啟用合作夥伴應用程式 

建立新的合作夥伴應用程式，並將使用您剛建立的帳戶。 在您的內部部署 Exchange 組織中的 Exchange PowerShell 中執行下列命令。

``` Powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a>步驟4：匯出內部部署授權憑證

執行 PowerShell 腳本以匯出內部部署授權憑證，您將在下一個步驟中匯入到商務用 Skype Online 組織。

將下列文字儲存到一個名為的 PowerShell 腳本檔案中，例如 ExportAuthCert. ps1。

``` Powershell
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

在您的內部部署 Exchange 組織中的 Exchange PowerShell 中，執行您剛建立的 PowerShell 腳本。 例如： .\ExportAuthCert.ps1

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>步驟5：將內部部署授權憑證上傳到 Azure Active Directory ACS

接著，使用 Windows PowerShell 將您在上一個步驟中匯出的內部部署授權憑證上傳至 Azure Active Directory 存取控制服務（ACS）。 若要這樣做，必須先安裝適用于 Windows PowerShell Cmdlet 的 Azure Active Directory 模組。 如果沒有安裝，請移[https://aka.ms/aadposh](https://aka.ms/aadposh)至安裝適用于 Windows PowerShell 的 Azure Active Directory 模組。 在安裝 Windows PowerShell 的 Azure Active Directory 模組之後，請完成下列步驟。

1. 按一下 [**適用于 Windows powershell 的 Azure Active Directory 模組**] 快捷方式，以開啟已安裝 Azure AD Cmdlet 的 Windows PowerShell 工作區。 此步驟中的所有命令都將使用 Windows PowerShell for Azure Active Directory 主控台來執行。

2. 將下列文字儲存到一個名為的 PowerShell 腳本檔案，例如`UploadAuthCert.ps1`。

   ``` Powershell
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

3. 執行您在上一個步驟中建立的 PowerShell 腳本。 例如：`.\UploadAuthCert.ps1`

4. 啟動腳本之後，就會顯示 [認證] 對話方塊。 輸入您的 Microsoft Online Azure AD 組織的租使用者系統管理員帳號憑證。 執行腳本之後，請將 [Windows PowerShell for Azure AD 會話] 保持開啟。 您將在下一個步驟中使用此程式來執行 PowerShell 腳本。

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a>步驟6：確認憑證已上傳到商務用 Skype 服務主體
1. 在已開啟並驗證至 Azure Active Directory 的 PowerShell 中，執行下列動作：
```
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. 出現 ReturnKeyValues 提示時按下 Enter
3. 確認您看到的索引鍵是與您的 Exchange Oauth 憑證開始和結束日期相符的 [開始日期] 和 [結束] 資料

### <a name="verify-your-success"></a>驗證您的成功

驗證部分功能是否順利運作，以確認設定正確無誤。 

1. 在有混合式 Exchange 伺服器設定的組織中，確認有雲端語音信箱服務的商務用 Skype 使用者可以順利變更其語音信箱問候語。

2. 確認行動用戶端的交談歷程記錄會顯示在 Outlook [交談記錄] 資料夾中。

3. 在 [清除] 資料夾中，使用[EWSEditor](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/)確認已歸檔的聊天訊息會存放在使用者的內部部署信箱中。

或者，查看您的流量。 OAuth 握手中的流量確實是獨特的（且看起來不像基本驗證），特別是在領域中，您將會開始查看發行人流量，看起來像這樣： 00000004-0000-0ff1-ce00-000000000000 @ （有時候在@ 符號），在所傳遞的權杖中。 您不會看到 [使用者名稱] 或 [密碼]，也就是 OAuth 的端點。 但您會看到「Office」 issuer （在此例中，"4" 是商務用 Skype，以及您的訂閱領域）。

如果您想要確定您使用的是 OAuth 成功，請確認您知道要取得的內容，並瞭解流量應該看起來的樣子。 以下是您預期的做法，以下是[Microsoft 應用程式中的 OAuth 流量標準範例](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)（雖然它不使用重新整理權杖），而且還有 Fiddler 擴充[功能](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)可讓您在 OAuth JWT （JSON）中查看。網頁標記）。

以下是[一個設定一個範例](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/)，但是您可以使用任何您想要執行此程式的網路追蹤工具。

## <a name="related-topics"></a>相關主題

[在 Exchange 與 Exchange Online 組織之間設定 OAuth 驗證](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
