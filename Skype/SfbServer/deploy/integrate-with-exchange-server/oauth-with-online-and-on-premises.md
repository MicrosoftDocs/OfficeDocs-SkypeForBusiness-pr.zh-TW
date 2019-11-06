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
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a><span data-ttu-id="1c848-103">在商務用 Skype Online 與 Exchange Server 之間設定整合與 OAuth</span><span class="sxs-lookup"><span data-stu-id="1c848-103">Configure Integration and OAuth between Skype for Business Online and Exchange Server</span></span> 

<span data-ttu-id="1c848-104">設定 Exchange server 與商務用 Skype Online 之間的整合，可啟用[功能支援](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)中所述的商務用 Skype 與 Exchange 整合功能。</span><span class="sxs-lookup"><span data-stu-id="1c848-104">Configuring integration between Exchange server and Skype for Business Online enables the Skype for Business and Exchange Integration features described in [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span>

<span data-ttu-id="1c848-105">本主題適用于與 Exchange Server 2013 至2019的整合。</span><span class="sxs-lookup"><span data-stu-id="1c848-105">This topic applies to integration with Exchange Server 2013 through 2019.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1c848-106">開始之前，您需要知道什麼？</span><span class="sxs-lookup"><span data-stu-id="1c848-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1c848-107">完成此工作所需的估計時間：15分鐘</span><span class="sxs-lookup"><span data-stu-id="1c848-107">Estimated time to complete this task: 15 minutes</span></span>

-  <span data-ttu-id="1c848-108">您必須先獲指派許可權，才能執行此程式或程式。</span><span class="sxs-lookup"><span data-stu-id="1c848-108">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="1c848-109">若要查看您需要的許可權，請參閱[Exchange 與 Shell 基礎結構許可權](https://go.microsoft.com/fwlink/p/?LinkId=746511)主題。</span><span class="sxs-lookup"><span data-stu-id="1c848-109">To see what permissions you need, see the [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) topic.</span></span>

- <span data-ttu-id="1c848-110">如需有關適用于本主題中之程式的鍵盤快速鍵的詳細資訊，請參閱[Exchange 系統管理中心的鍵盤快速鍵]( https://go.microsoft.com/fwlink/p/?LinkId=746512)。</span><span class="sxs-lookup"><span data-stu-id="1c848-110">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span></span>

- <span data-ttu-id="1c848-111">如需相容性的相關資訊，請參閱[商務用 Skype 與 Office app 的相容性](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office)。</span><span class="sxs-lookup"><span data-stu-id="1c848-111">For information about compatibility, see [Skype for Business compatibility with Office apps](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office).</span></span>

## <a name="configure-integration-between-exchange-server-and-o365"></a><span data-ttu-id="1c848-112">設定 Exchange Server 與 O365 之間的整合</span><span class="sxs-lookup"><span data-stu-id="1c848-112">Configure integration between Exchange Server and O365</span></span>

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a><span data-ttu-id="1c848-113">步驟1：在 Exchange Server 和 O365 之間設定 OAuth 驗證</span><span class="sxs-lookup"><span data-stu-id="1c848-113">Step 1: Configure OAuth authentication between Exchange Server and O365</span></span>

<span data-ttu-id="1c848-114">請執行下列文章中的步驟：</span><span class="sxs-lookup"><span data-stu-id="1c848-114">Perform the steps in the following article:</span></span>

[<span data-ttu-id="1c848-115">在 Exchange 與 Exchange Online 組織之間設定 OAuth 驗證</span><span class="sxs-lookup"><span data-stu-id="1c848-115">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a><span data-ttu-id="1c848-116">步驟2：針對商務用 Skype Online 合作夥伴應用程式建立新的郵件使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="1c848-116">Step 2: Create a new Mail User account for the Skype for Business Online Partner Application</span></span>

<span data-ttu-id="1c848-117">此步驟是在 Exchange 伺服器上完成。</span><span class="sxs-lookup"><span data-stu-id="1c848-117">This step is done on the Exchange server.</span></span> <span data-ttu-id="1c848-118">它會建立一個郵件使用者，並將適當的管理角色許可權指派給它。</span><span class="sxs-lookup"><span data-stu-id="1c848-118">It will create a mail user and assign it the appropriate management role rights.</span></span> <span data-ttu-id="1c848-119">這個帳戶將會在下一個步驟中使用。</span><span class="sxs-lookup"><span data-stu-id="1c848-119">This account will then be used in the next step.</span></span>

<span data-ttu-id="1c848-120">為您的 Exchange 組織指定驗證的網域。</span><span class="sxs-lookup"><span data-stu-id="1c848-120">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="1c848-121">這個網域應該是用來做為內部部署 Exchange 帳戶的主要 SMTP 網域的同一個網域。</span><span class="sxs-lookup"><span data-stu-id="1c848-121">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="1c848-122">在下列程式中， \<這個網域稱為\>您的驗證網域。</span><span class="sxs-lookup"><span data-stu-id="1c848-122">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span> <span data-ttu-id="1c848-123">此外， \<DomainControllerFQDN\>應該是網網域控制站的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1c848-123">Also, the \<DomainControllerFQDN\> should be the FQDN of a domain controller.</span></span>

``` Powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="1c848-124">這個命令會將新的郵件使用者從地址清單中隱藏。</span><span class="sxs-lookup"><span data-stu-id="1c848-124">This command will hide the new mail user from address lists.</span></span>

``` Powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="1c848-125">接下來的兩個命令會將 [UserApplication] 和 [ArchiveApplication] 管理角色指派給這個新的帳戶。</span><span class="sxs-lookup"><span data-stu-id="1c848-125">These next two commands will assign the UserApplication and ArchiveApplication management role to this new account.</span></span>

``` Powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

``` Powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a><span data-ttu-id="1c848-126">步驟3：針對商務用 Skype Online 建立及啟用合作夥伴應用程式</span><span class="sxs-lookup"><span data-stu-id="1c848-126">Step 3: Create and enable a Partner Application for Skype for Business Online</span></span> 

<span data-ttu-id="1c848-127">建立新的合作夥伴應用程式，並將使用您剛建立的帳戶。</span><span class="sxs-lookup"><span data-stu-id="1c848-127">Create a new partner application and will use the account you just created.</span></span> <span data-ttu-id="1c848-128">在您的內部部署 Exchange 組織中的 Exchange PowerShell 中執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="1c848-128">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

``` Powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a><span data-ttu-id="1c848-129">步驟4：匯出內部部署授權憑證</span><span class="sxs-lookup"><span data-stu-id="1c848-129">Step 4: Export the on-premises authorization certificate</span></span>

<span data-ttu-id="1c848-130">執行 PowerShell 腳本以匯出內部部署授權憑證，您將在下一個步驟中匯入到商務用 Skype Online 組織。</span><span class="sxs-lookup"><span data-stu-id="1c848-130">Run a PowerShell script to export the on-premises authorization certificate, which you will import to your Skype for Business Online organization in the next step.</span></span>

<span data-ttu-id="1c848-131">將下列文字儲存到一個名為的 PowerShell 腳本檔案中，例如 ExportAuthCert. ps1。</span><span class="sxs-lookup"><span data-stu-id="1c848-131">Save the following text to a PowerShell script file named, for example, ExportAuthCert.ps1.</span></span>

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

<span data-ttu-id="1c848-132">在您的內部部署 Exchange 組織中的 Exchange PowerShell 中，執行您剛建立的 PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="1c848-132">In Exchange PowerShell in your on-premises Exchange organization, run the PowerShell script that you just created.</span></span> <span data-ttu-id="1c848-133">例如： .\ExportAuthCert.ps1</span><span class="sxs-lookup"><span data-stu-id="1c848-133">For example: .\ExportAuthCert.ps1</span></span>

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a><span data-ttu-id="1c848-134">步驟5：將內部部署授權憑證上傳到 Azure Active Directory ACS</span><span class="sxs-lookup"><span data-stu-id="1c848-134">Step 5: Upload the on-premises authorization certificate to Azure Active Directory ACS</span></span>

<span data-ttu-id="1c848-135">接著，使用 Windows PowerShell 將您在上一個步驟中匯出的內部部署授權憑證上傳至 Azure Active Directory 存取控制服務（ACS）。</span><span class="sxs-lookup"><span data-stu-id="1c848-135">Next, use Windows PowerShell to upload the on-premises authorization certificate that you exported in the previous step to Azure Active Directory Access Control Services (ACS).</span></span> <span data-ttu-id="1c848-136">若要這樣做，必須先安裝適用于 Windows PowerShell Cmdlet 的 Azure Active Directory 模組。</span><span class="sxs-lookup"><span data-stu-id="1c848-136">To do this, the Azure Active Directory Module for Windows PowerShell cmdlets must already be installed.</span></span> <span data-ttu-id="1c848-137">如果沒有安裝，請移[https://aka.ms/aadposh](https://aka.ms/aadposh)至安裝適用于 Windows PowerShell 的 Azure Active Directory 模組。</span><span class="sxs-lookup"><span data-stu-id="1c848-137">If it's not installed, go to [https://aka.ms/aadposh](https://aka.ms/aadposh) to install the Azure Active Directory Module for Windows PowerShell.</span></span> <span data-ttu-id="1c848-138">在安裝 Windows PowerShell 的 Azure Active Directory 模組之後，請完成下列步驟。</span><span class="sxs-lookup"><span data-stu-id="1c848-138">Complete the following steps after the Azure Active Directory Module for Windows PowerShell is installed.</span></span>

1. <span data-ttu-id="1c848-139">按一下 [**適用于 Windows powershell 的 Azure Active Directory 模組**] 快捷方式，以開啟已安裝 Azure AD Cmdlet 的 Windows PowerShell 工作區。</span><span class="sxs-lookup"><span data-stu-id="1c848-139">Click the **Azure Active Directory Module for Windows PowerShell** shortcut to open a Windows PowerShell workspace that has the Azure AD cmdlets installed.</span></span> <span data-ttu-id="1c848-140">此步驟中的所有命令都將使用 Windows PowerShell for Azure Active Directory 主控台來執行。</span><span class="sxs-lookup"><span data-stu-id="1c848-140">All commands in this step will be run using the Windows PowerShell for Azure Active Directory console.</span></span>

2. <span data-ttu-id="1c848-141">將下列文字儲存到一個名為的 PowerShell 腳本檔案，例如`UploadAuthCert.ps1`。</span><span class="sxs-lookup"><span data-stu-id="1c848-141">Save the following text to a PowerShell script file named, for example,  `UploadAuthCert.ps1`.</span></span>

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

3. <span data-ttu-id="1c848-142">執行您在上一個步驟中建立的 PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="1c848-142">Run the PowerShell script that you created in the previous step.</span></span> <span data-ttu-id="1c848-143">例如：`.\UploadAuthCert.ps1`</span><span class="sxs-lookup"><span data-stu-id="1c848-143">For example:  `.\UploadAuthCert.ps1`</span></span>

4. <span data-ttu-id="1c848-144">啟動腳本之後，就會顯示 [認證] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="1c848-144">After you start the script, a credentials dialog box is displayed.</span></span> <span data-ttu-id="1c848-145">輸入您的 Microsoft Online Azure AD 組織的租使用者系統管理員帳號憑證。</span><span class="sxs-lookup"><span data-stu-id="1c848-145">Enter the credentials for the tenant administrator account of your Microsoft Online Azure AD organization.</span></span> <span data-ttu-id="1c848-146">執行腳本之後，請將 [Windows PowerShell for Azure AD 會話] 保持開啟。</span><span class="sxs-lookup"><span data-stu-id="1c848-146">After running the script, leave the Windows PowerShell for Azure AD session open.</span></span> <span data-ttu-id="1c848-147">您將在下一個步驟中使用此程式來執行 PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="1c848-147">You will use this to run a PowerShell script in the next step.</span></span>

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a><span data-ttu-id="1c848-148">步驟6：確認憑證已上傳到商務用 Skype 服務主體</span><span class="sxs-lookup"><span data-stu-id="1c848-148">Step 6: Verify that the Certificate has Uploaded to the Skype for Business Service Principal</span></span>
1. <span data-ttu-id="1c848-149">在已開啟並驗證至 Azure Active Directory 的 PowerShell 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="1c848-149">In the PowerShell opened and authenticated to Azure Active Directory, run the following</span></span>
```
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. <span data-ttu-id="1c848-150">出現 ReturnKeyValues 提示時按下 Enter</span><span class="sxs-lookup"><span data-stu-id="1c848-150">Press Enter when prompted for ReturnKeyValues</span></span>
3. <span data-ttu-id="1c848-151">確認您看到的索引鍵是與您的 Exchange Oauth 憑證開始和結束日期相符的 [開始日期] 和 [結束] 資料</span><span class="sxs-lookup"><span data-stu-id="1c848-151">Confirm you see a key listed with start date and end data that matches your Exchange Oauth certificate start and end dates</span></span>

### <a name="verify-your-success"></a><span data-ttu-id="1c848-152">驗證您的成功</span><span class="sxs-lookup"><span data-stu-id="1c848-152">Verify your success</span></span>

<span data-ttu-id="1c848-153">驗證部分功能是否順利運作，以確認設定正確無誤。</span><span class="sxs-lookup"><span data-stu-id="1c848-153">Verify that the configuration is correct by verifying some of the features are working successfully.</span></span> 

1. <span data-ttu-id="1c848-154">在有混合式 Exchange 伺服器設定的組織中，確認有雲端語音信箱服務的商務用 Skype 使用者可以順利變更其語音信箱問候語。</span><span class="sxs-lookup"><span data-stu-id="1c848-154">Confirm that Skype for Business users with Cloud Voicemail service, in an organization with a Hybrid Exchange Server configuration, can successfully change their voicemail greetings.</span></span>

2. <span data-ttu-id="1c848-155">確認行動用戶端的交談歷程記錄會顯示在 Outlook [交談記錄] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="1c848-155">Confirm conversation history for mobile clients is visible in the Outlook Conversation History folder.</span></span>

3. <span data-ttu-id="1c848-156">在 [清除] 資料夾中，使用[EWSEditor](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/)確認已歸檔的聊天訊息會存放在使用者的內部部署信箱中。</span><span class="sxs-lookup"><span data-stu-id="1c848-156">Confirm that archived chat messages are deposited in the user's on-premises mailbox in the Purges folder using [EWSEditor](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/).</span></span>

<span data-ttu-id="1c848-157">或者，查看您的流量。</span><span class="sxs-lookup"><span data-stu-id="1c848-157">Alternately, look at your traffic.</span></span> <span data-ttu-id="1c848-158">OAuth 握手中的流量確實是獨特的（且看起來不像基本驗證），特別是在領域中，您將會開始查看發行人流量，看起來像這樣： 00000004-0000-0ff1-ce00-000000000000 @ （有時候在@ 符號），在所傳遞的權杖中。</span><span class="sxs-lookup"><span data-stu-id="1c848-158">The traffic in an OAuth handshake is really distinctive (and doesn't look like Basic authentication), particularly around realms, where you’ll begin to see issuer traffic that looks like this: 00000004-0000-0ff1-ce00-000000000000@ (sometimes with a / before the @ sign), in the tokens that are being passed.</span></span> <span data-ttu-id="1c848-159">您不會看到 [使用者名稱] 或 [密碼]，也就是 OAuth 的端點。</span><span class="sxs-lookup"><span data-stu-id="1c848-159">You won’t see a username or password, which is the point of OAuth.</span></span> <span data-ttu-id="1c848-160">但您會看到「Office」 issuer （在此例中，"4" 是商務用 Skype，以及您的訂閱領域）。</span><span class="sxs-lookup"><span data-stu-id="1c848-160">But you will see   the ‘Office’ issuer – in this case ‘4’ is Skype for Business – and the realm of your subscription.</span></span>

<span data-ttu-id="1c848-161">如果您想要確定您使用的是 OAuth 成功，請確認您知道要取得的內容，並瞭解流量應該看起來的樣子。</span><span class="sxs-lookup"><span data-stu-id="1c848-161">If you want to be sure you’re successfully using OAuth, make certain you know what to expect and know what the traffic should look like.</span></span> <span data-ttu-id="1c848-162">以下是您預期的做法，以下是[Microsoft 應用程式中的 OAuth 流量標準範例](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)（雖然它不使用重新整理權杖），而且還有 Fiddler 擴充[功能](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)可讓您在 OAuth JWT （JSON）中查看。網頁標記）。</span><span class="sxs-lookup"><span data-stu-id="1c848-162">So [here’s what to expect](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), here’s a pretty standard [example of OAuth traffic in a Microsoft application](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (really helpful to read, though it doesn't use Refresh tokens), and there are Fiddler extensions that will let you look into your OAuth JWT (JSON Web Token).</span></span>

<span data-ttu-id="1c848-163">以下是[一個設定一個範例](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/)，但是您可以使用任何您想要執行此程式的網路追蹤工具。</span><span class="sxs-lookup"><span data-stu-id="1c848-163">Here's an [example of setting one up](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), but you can use any network tracing tool you like to undertake this process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1c848-164">相關主題</span><span class="sxs-lookup"><span data-stu-id="1c848-164">Related topics</span></span>

[<span data-ttu-id="1c848-165">在 Exchange 與 Exchange Online 組織之間設定 OAuth 驗證</span><span class="sxs-lookup"><span data-stu-id="1c848-165">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
