---
title: 商務用 Skype Online 與 Exchange server 之間的整合
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
description: 設定 Exchange 內部部署和商務用 Skype Online 之間的 OAuth 驗證，可啟用功能支援中所述的商務用 Skype 和 Exchange 整合功能。
ms.openlocfilehash: 342362926ad0af169acd6c9af4715008425e71c7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109709"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a><span data-ttu-id="96052-103">設定商務用 Skype Online 與 Exchange Server 之間的整合及 OAuth</span><span class="sxs-lookup"><span data-stu-id="96052-103">Configure Integration and OAuth between Skype for Business Online and Exchange Server</span></span> 

<span data-ttu-id="96052-104">設定 Exchange server 與商務用 Skype Online 之間的整合，可啟用 [功能支援](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)中所述的商務用 Skype 和 Exchange 整合功能。</span><span class="sxs-lookup"><span data-stu-id="96052-104">Configuring integration between Exchange server and Skype for Business Online enables the Skype for Business and Exchange Integration features described in [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span>

<span data-ttu-id="96052-105">本主題適用于與 Exchange Server 2013 到2019的整合。</span><span class="sxs-lookup"><span data-stu-id="96052-105">This topic applies to integration with Exchange Server 2013 through 2019.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="96052-106">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="96052-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="96052-107">完成此工作的預估時間：15 分鐘</span><span class="sxs-lookup"><span data-stu-id="96052-107">Estimated time to complete this task: 15 minutes</span></span>

-  <span data-ttu-id="96052-108">您必須已獲指派權限，才能執行此程序或這些程序。</span><span class="sxs-lookup"><span data-stu-id="96052-108">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="96052-109">若要查看您需要的許可權，請參閱 [Exchange 及命令介面基礎結構許可權](/exchange/exchange-and-shell-infrastructure-permissions-exchange-2013-help) 主題。</span><span class="sxs-lookup"><span data-stu-id="96052-109">To see what permissions you need, see the [Exchange and Shell infrastructure permissions](/exchange/exchange-and-shell-infrastructure-permissions-exchange-2013-help) topic.</span></span>

- <span data-ttu-id="96052-110">如需適用於此主題中程序的快速鍵相關資訊，請參閱 [Exchange 系統管理中心的鍵盤快速鍵]( https://go.microsoft.com/fwlink/p/?LinkId=746512)。</span><span class="sxs-lookup"><span data-stu-id="96052-110">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span></span>

- <span data-ttu-id="96052-111">如需相容性的相關資訊，請參閱 [商務用 Skype 相容性與 Office 應用程式](../../plan-your-deployment/clients-and-devices/compatibility-with-office.md)。</span><span class="sxs-lookup"><span data-stu-id="96052-111">For information about compatibility, see [Skype for Business compatibility with Office apps](../../plan-your-deployment/clients-and-devices/compatibility-with-office.md).</span></span>

## <a name="configure-integration-between-exchange-server-and-o365"></a><span data-ttu-id="96052-112">設定 Exchange Server 和 O365 之間的整合</span><span class="sxs-lookup"><span data-stu-id="96052-112">Configure integration between Exchange Server and O365</span></span>

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a><span data-ttu-id="96052-113">步驟1：設定 Exchange Server 和 O365 之間的 OAuth 驗證</span><span class="sxs-lookup"><span data-stu-id="96052-113">Step 1: Configure OAuth authentication between Exchange Server and O365</span></span>

<span data-ttu-id="96052-114">執行下列文章中的步驟：</span><span class="sxs-lookup"><span data-stu-id="96052-114">Perform the steps in the following article:</span></span>

[<span data-ttu-id="96052-115">設定 Exchange 與 Exchange Online 組織之間的 OAuth 驗證</span><span class="sxs-lookup"><span data-stu-id="96052-115">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a><span data-ttu-id="96052-116">步驟2：為商務用 Skype Online 夥伴應用程式建立新的郵件使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="96052-116">Step 2: Create a new Mail User account for the Skype for Business Online Partner Application</span></span>

<span data-ttu-id="96052-117">此步驟是在 Exchange 伺服器上完成。</span><span class="sxs-lookup"><span data-stu-id="96052-117">This step is done on the Exchange server.</span></span> <span data-ttu-id="96052-118">它會建立郵件使用者，並為其指派適當的管理角色權力。</span><span class="sxs-lookup"><span data-stu-id="96052-118">It will create a mail user and assign it the appropriate management role rights.</span></span> <span data-ttu-id="96052-119">然後，將在下一個步驟中使用此帳戶。</span><span class="sxs-lookup"><span data-stu-id="96052-119">This account will then be used in the next step.</span></span>

<span data-ttu-id="96052-120">為您的 Exchange 組織指定已驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="96052-120">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="96052-121">這個網域應該是用來做為內部部署 Exchange 帳戶使用的主要 SMTP 網域的相同網域。</span><span class="sxs-lookup"><span data-stu-id="96052-121">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="96052-122">下列程式中稱為此網域 \<your Verified Domain\> 。</span><span class="sxs-lookup"><span data-stu-id="96052-122">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span> <span data-ttu-id="96052-123">此外， \<DomainControllerFQDN\> 應為網域控制站的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="96052-123">Also, the \<DomainControllerFQDN\> should be the FQDN of a domain controller.</span></span>

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="96052-124">此命令會將新的郵件使用者從通訊清單中隱藏。</span><span class="sxs-lookup"><span data-stu-id="96052-124">This command will hide the new mail user from address lists.</span></span>

```powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="96052-125">接下來的兩個命令會將 UserApplication 和 ArchiveApplication 管理角色指派給這個新帳戶。</span><span class="sxs-lookup"><span data-stu-id="96052-125">These next two commands will assign the UserApplication and ArchiveApplication management role to this new account.</span></span>

```powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a><span data-ttu-id="96052-126">步驟3：建立及啟用商務用 Skype Online 的夥伴應用程式</span><span class="sxs-lookup"><span data-stu-id="96052-126">Step 3: Create and enable a Partner Application for Skype for Business Online</span></span> 

<span data-ttu-id="96052-127">建立新的夥伴應用程式，並將使用您剛才建立的帳戶。</span><span class="sxs-lookup"><span data-stu-id="96052-127">Create a new partner application and will use the account you just created.</span></span> <span data-ttu-id="96052-128">在內部部署 Exchange 組織的 Exchange PowerShell 中執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="96052-128">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a><span data-ttu-id="96052-129">步驟4：匯出內部部署授權憑證</span><span class="sxs-lookup"><span data-stu-id="96052-129">Step 4: Export the on-premises authorization certificate</span></span>

<span data-ttu-id="96052-130">執行 PowerShell 腳本，以匯出內部部署授權憑證，在下一個步驟中，您將匯入商務用 Skype Online 組織。</span><span class="sxs-lookup"><span data-stu-id="96052-130">Run a PowerShell script to export the on-premises authorization certificate, which you will import to your Skype for Business Online organization in the next step.</span></span>

<span data-ttu-id="96052-131">將下列文字儲存到 PowerShell 指令碼檔案 (例如 ExportAuthCert.ps1)。</span><span class="sxs-lookup"><span data-stu-id="96052-131">Save the following text to a PowerShell script file named, for example, ExportAuthCert.ps1.</span></span>

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

<span data-ttu-id="96052-132">在內部部署 Exchange 組織的 Exchange PowerShell 中，執行您剛才建立的 PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="96052-132">In Exchange PowerShell in your on-premises Exchange organization, run the PowerShell script that you just created.</span></span> <span data-ttu-id="96052-133">例如： .\ExportAuthCert.ps1</span><span class="sxs-lookup"><span data-stu-id="96052-133">For example: .\ExportAuthCert.ps1</span></span>

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a><span data-ttu-id="96052-134">步驟5：將內部部署授權憑證上傳至 Azure Active Directory ACS</span><span class="sxs-lookup"><span data-stu-id="96052-134">Step 5: Upload the on-premises authorization certificate to Azure Active Directory ACS</span></span>

<span data-ttu-id="96052-135">接下來，使用 Windows PowerShell，將您在上一個步驟中匯出的內部部署授權憑證上傳至 Azure Active Directory 存取控制服務 (ACS) 。</span><span class="sxs-lookup"><span data-stu-id="96052-135">Next, use Windows PowerShell to upload the on-premises authorization certificate that you exported in the previous step to Azure Active Directory Access Control Services (ACS).</span></span> <span data-ttu-id="96052-136">若要這麼做，必須已安裝 Windows PowerShell Cmdlet 的 Azure Active Directory 模組。</span><span class="sxs-lookup"><span data-stu-id="96052-136">To do this, the Azure Active Directory Module for Windows PowerShell cmdlets must already be installed.</span></span> <span data-ttu-id="96052-137">若未安裝，請移至 [https://aka.ms/aadposh](/previous-versions/azure/jj151815(v=azure.100)) 安裝 Azure Active Directory Module For Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="96052-137">If it's not installed, go to [https://aka.ms/aadposh](/previous-versions/azure/jj151815(v=azure.100)) to install the Azure Active Directory Module for Windows PowerShell.</span></span> <span data-ttu-id="96052-138">安裝 Windows PowerShell 的 Azure Active Directory 模組後，請完成下列步驟。</span><span class="sxs-lookup"><span data-stu-id="96052-138">Complete the following steps after the Azure Active Directory Module for Windows PowerShell is installed.</span></span>

1. <span data-ttu-id="96052-139">按一下 [ **適用于 windows 的 Azure Active Directory 模組] PowerShell** 快捷方式，開啟已安裝 Azure AD Cmdlet 的 Windows PowerShell workspace。</span><span class="sxs-lookup"><span data-stu-id="96052-139">Click the **Azure Active Directory Module for Windows PowerShell** shortcut to open a Windows PowerShell workspace that has the Azure AD cmdlets installed.</span></span> <span data-ttu-id="96052-140">在此步驟中的所有命令，都將使用適用于 Azure Active Directory 主控台的 Windows PowerShell 執行。</span><span class="sxs-lookup"><span data-stu-id="96052-140">All commands in this step will be run using the Windows PowerShell for Azure Active Directory console.</span></span>

2. <span data-ttu-id="96052-141">將下列文字儲存至名為的 PowerShell 腳本檔案，例如  `UploadAuthCert.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="96052-141">Save the following text to a PowerShell script file named, for example,  `UploadAuthCert.ps1`.</span></span>

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

3. <span data-ttu-id="96052-142">執行您在前一個步驟中建立的 PowerShell 指令碼。</span><span class="sxs-lookup"><span data-stu-id="96052-142">Run the PowerShell script that you created in the previous step.</span></span> <span data-ttu-id="96052-143">例如：  `.\UploadAuthCert.ps1`</span><span class="sxs-lookup"><span data-stu-id="96052-143">For example:  `.\UploadAuthCert.ps1`</span></span>

4. <span data-ttu-id="96052-144">啟動指令碼之後，即會顯示認證對話方塊。</span><span class="sxs-lookup"><span data-stu-id="96052-144">After you start the script, a credentials dialog box is displayed.</span></span> <span data-ttu-id="96052-145">輸入您的 Microsoft Online Azure AD 組織之租使用者系統管理員帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="96052-145">Enter the credentials for the tenant administrator account of your Microsoft Online Azure AD organization.</span></span> <span data-ttu-id="96052-146">執行腳本後，請保持 Windows PowerShell Azure AD 會話開啟狀態。</span><span class="sxs-lookup"><span data-stu-id="96052-146">After running the script, leave the Windows PowerShell for Azure AD session open.</span></span> <span data-ttu-id="96052-147">您將在下一個步驟中以此工作階段執行 PowerShell 指令碼。</span><span class="sxs-lookup"><span data-stu-id="96052-147">You will use this to run a PowerShell script in the next step.</span></span>

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a><span data-ttu-id="96052-148">步驟6：確認憑證已上傳至商務用 Skype 服務主體</span><span class="sxs-lookup"><span data-stu-id="96052-148">Step 6: Verify that the Certificate has Uploaded to the Skype for Business Service Principal</span></span>
1. <span data-ttu-id="96052-149">在 [PowerShell 開啟及驗證至 Azure Active Directory 中，執行下列</span><span class="sxs-lookup"><span data-stu-id="96052-149">In the PowerShell opened and authenticated to Azure Active Directory, run the following</span></span>
```powershell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. <span data-ttu-id="96052-150">當系統提示 ReturnKeyValues 時按 Enter 鍵</span><span class="sxs-lookup"><span data-stu-id="96052-150">Press Enter when prompted for ReturnKeyValues</span></span>
3. <span data-ttu-id="96052-151">請確認您會看到列出與 Exchange Oauth 憑證開始和結束日期相符的 [開始日期] 和 [結束] 資料的按鍵</span><span class="sxs-lookup"><span data-stu-id="96052-151">Confirm you see a key listed with start date and end data that matches your Exchange Oauth certificate start and end dates</span></span>

### <a name="verify-your-success"></a><span data-ttu-id="96052-152">驗證您是否成功</span><span class="sxs-lookup"><span data-stu-id="96052-152">Verify your success</span></span>

<span data-ttu-id="96052-153">驗證某些功能是否順利運作，以驗證設定是否正確。</span><span class="sxs-lookup"><span data-stu-id="96052-153">Verify that the configuration is correct by verifying some of the features are working successfully.</span></span> 

1. <span data-ttu-id="96052-154">請確認在具有混合 Exchange 伺服器設定的組織中，使用雲端語音信箱服務的商務用 Skype 使用者可以成功變更其語音信箱問候語。</span><span class="sxs-lookup"><span data-stu-id="96052-154">Confirm that Skype for Business users with Cloud Voicemail service, in an organization with a Hybrid Exchange Server configuration, can successfully change their voicemail greetings.</span></span>

2. <span data-ttu-id="96052-155">確認行動用戶端的交談記錄會顯示在 Outlook [交談記錄] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="96052-155">Confirm conversation history for mobile clients is visible in the Outlook Conversation History folder.</span></span>

3. <span data-ttu-id="96052-156">使用 [EWSEditor](/archive/blogs/webdav_101/where-to-get-ewseditor)，確認已封存的聊天訊息會存放在使用者的內部部署信箱中的 [清除] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="96052-156">Confirm that archived chat messages are deposited in the user's on-premises mailbox in the Purges folder using [EWSEditor](/archive/blogs/webdav_101/where-to-get-ewseditor).</span></span>

<span data-ttu-id="96052-157">或者，查看您的流量。</span><span class="sxs-lookup"><span data-stu-id="96052-157">Alternately, look at your traffic.</span></span> <span data-ttu-id="96052-158">OAuth 握手中的流量十分獨特 (而且看起來不像基本驗證) （特別是在領域之外），您可以在這裡看到如下所示的發行人流量： 00000004-0000-0ff1-ce00-000000000000 @ (有時候會在所傳遞的標記中使用 @ 符號) 。</span><span class="sxs-lookup"><span data-stu-id="96052-158">The traffic in an OAuth handshake is really distinctive (and doesn't look like Basic authentication), particularly around realms, where you’ll begin to see issuer traffic that looks like this: 00000004-0000-0ff1-ce00-000000000000@ (sometimes with a / before the @ sign), in the tokens that are being passed.</span></span> <span data-ttu-id="96052-159">您不會看到使用者名稱或密碼，也就是 OAuth 的點。</span><span class="sxs-lookup"><span data-stu-id="96052-159">You won’t see a username or password, which is the point of OAuth.</span></span> <span data-ttu-id="96052-160">不過，您會看到「Office」簽發者–在此案例中，"4" 是商務用 Skype –以及您訂閱的領域。</span><span class="sxs-lookup"><span data-stu-id="96052-160">But you will see   the ‘Office’ issuer – in this case ‘4’ is Skype for Business – and the realm of your subscription.</span></span>

<span data-ttu-id="96052-161">如果您想要確定成功使用 OAuth，請確定您知道預期的內容，並知道流量應該類似。</span><span class="sxs-lookup"><span data-stu-id="96052-161">If you want to be sure you’re successfully using OAuth, make certain you know what to expect and know what the traffic should look like.</span></span> <span data-ttu-id="96052-162">以下是您 [預期的目標](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)，以下是 [Microsoft 應用 (程式中 OAuth 流量的](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  一個很好的標準範例，雖然它不會使用重新整理權杖) ，但仍有 Fiddler 擴充功能可讓您查看 OAuth JWT (JSON Web Token) 。</span><span class="sxs-lookup"><span data-stu-id="96052-162">So [here’s what to expect](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), here’s a pretty standard [example of OAuth traffic in a Microsoft application](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (really helpful to read, though it doesn't use Refresh tokens), and there are Fiddler extensions that will let you look into your OAuth JWT (JSON Web Token).</span></span>

<span data-ttu-id="96052-163">以下是 [一個設定的範例](/archive/blogs/kaevans/updated-fiddler-oauth-inspector)，但是您可以使用任何您想要執行此程式的網路追蹤工具。</span><span class="sxs-lookup"><span data-stu-id="96052-163">Here's an [example of setting one up](/archive/blogs/kaevans/updated-fiddler-oauth-inspector), but you can use any network tracing tool you like to undertake this process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="96052-164">相關主題</span><span class="sxs-lookup"><span data-stu-id="96052-164">Related topics</span></span>

[<span data-ttu-id="96052-165">設定 Exchange 與 Exchange Online 組織之間的 OAuth 驗證</span><span class="sxs-lookup"><span data-stu-id="96052-165">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)