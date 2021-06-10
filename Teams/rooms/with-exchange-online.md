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
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: 請閱讀本主題，以瞭解如何在內部部署Microsoft Teams 會議室部署Exchange Online商務用 Skype Server部署。
ms.openlocfilehash: 2f92f85ddf39c5e1a813492b3092eeeef9b77e4c
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796677"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a><span data-ttu-id="53e3b-103">使用 Microsoft Teams 會議室 部署Exchange Online</span><span class="sxs-lookup"><span data-stu-id="53e3b-103">Deploy Microsoft Teams Rooms with Exchange Online</span></span>

<span data-ttu-id="53e3b-104">請閱讀本主題，以瞭解如何在內部部署Microsoft Teams 會議室部署Exchange Online商務用 Skype Server部署。</span><span class="sxs-lookup"><span data-stu-id="53e3b-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Exchange Online and Skype for Business Server on-premises.</span></span>
  
<span data-ttu-id="53e3b-105">如果貴組織有混合式服務，其中一些是內部部署，有些是線上託管，則您的組式取決於每個服務的託管位置。</span><span class="sxs-lookup"><span data-stu-id="53e3b-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="53e3b-106">本主題涵蓋使用線上託管Microsoft Teams 會議室的Exchange部署。</span><span class="sxs-lookup"><span data-stu-id="53e3b-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted online.</span></span> <span data-ttu-id="53e3b-107">由於這類部署有許多不同的變化，因此無法針對所有部署提供詳細指示。</span><span class="sxs-lookup"><span data-stu-id="53e3b-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="53e3b-108">下列程式適用于許多配置。</span><span class="sxs-lookup"><span data-stu-id="53e3b-108">The following process will work for many configurations.</span></span> <span data-ttu-id="53e3b-109">如果此程式不適用於您的設定，建議您使用 Windows PowerShell來達到此處所記載的相同最終結果，以及其他部署選項。</span><span class="sxs-lookup"><span data-stu-id="53e3b-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="53e3b-110">設定使用者帳戶最簡單的方法是使用遠端Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="53e3b-110">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="53e3b-111">Microsoft 提供[SkypeRoomProvisioningScript.ps1，](https://go.microsoft.com/fwlink/?linkid=870105)此腳本可協助建立新的使用者帳戶，或驗證您現有的資源帳戶，以便協助您將這些帳戶轉換為相容的Microsoft Teams 會議室使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="53e3b-111">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="53e3b-112">您可以按照下列步驟來設定您的裝置Microsoft Teams 會議室帳戶。</span><span class="sxs-lookup"><span data-stu-id="53e3b-112">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="53e3b-113">需求</span><span class="sxs-lookup"><span data-stu-id="53e3b-113">Requirements</span></span>

<span data-ttu-id="53e3b-114">使用 Microsoft Teams 會議室部署Exchange Online，請確定您符合需求。</span><span class="sxs-lookup"><span data-stu-id="53e3b-114">Before you deploy Microsoft Teams Rooms with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="53e3b-115">詳細資訊，請參閱Microsoft Teams 會議室[需求](requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="53e3b-115">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="53e3b-116">若要使用 Microsoft Teams 會議室 部署Exchange Online，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="53e3b-116">To deploy Microsoft Teams Rooms with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="53e3b-117">請確定您擁有執行關聯 Cmdlet 的許可權。</span><span class="sxs-lookup"><span data-stu-id="53e3b-117">Be sure you have the right permissions to run the associated cmdlets.</span></span> 

   > [!NOTE]
   >  <span data-ttu-id="53e3b-118">本節 Azure Active Directory 中 Windows PowerShell [Cmdlet](/powershell/azure/active-directory/overview?view=azureadps-1.0)的模組 (例如 Set-MsolUser) 已針對 Microsoft Teams 會議室 裝置設定帳戶進行測試。</span><span class="sxs-lookup"><span data-stu-id="53e3b-118">The [Azure Active Directory Module for Windows PowerShell cmdlets](/powershell/azure/active-directory/overview?view=azureadps-1.0) in this section (for example,  Set-MsolUser) have been tested in setting up accounts for Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="53e3b-119">不過，其他 Cmdlet 可能可以工作，但尚未在此特定情況下進行測試。</span><span class="sxs-lookup"><span data-stu-id="53e3b-119">It's possible that other cmdlets may work, however, they haven't been tested in this specific scenario.</span></span>

<span data-ttu-id="53e3b-120">如果您部署 Active Directory Federation Services (AD FS) ，您可能必須先將使用者帳戶轉換成受管理的使用者，然後再執行這些步驟，然後在完成這些步驟後將使用者轉換回聯合使用者。</span><span class="sxs-lookup"><span data-stu-id="53e3b-120">If you deployed Active Directory Federation Services (AD FS), you may have to convert the user account to a managed user before you follow these steps, and then convert the user back to a federated user after you complete these steps.</span></span>
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="53e3b-121">建立帳戶並設定Exchange屬性</span><span class="sxs-lookup"><span data-stu-id="53e3b-121">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="53e3b-122">在 PC 上Windows PowerShell遠端會話，並Exchange Online方式：</span><span class="sxs-lookup"><span data-stu-id="53e3b-122">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org = 'contoso.microsoft.com'
    $cred = Get-Credential $admin@$org
    $sess = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
    Import-PSSession $sess -DisableNameChecking
    ```

2. <span data-ttu-id="53e3b-123">建立會話之後，您可以建立新信箱並啟用為 RoomMailboxAccount，或變更現有會議室信箱的設定。</span><span class="sxs-lookup"><span data-stu-id="53e3b-123">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="53e3b-124">這樣一來，帳戶就會Microsoft Teams 會議室。</span><span class="sxs-lookup"><span data-stu-id="53e3b-124">This will allow the account to authenticate into Microsoft Teams Rooms.</span></span>

   <span data-ttu-id="53e3b-125">如果您要變更現有的資源信箱：</span><span class="sxs-lookup"><span data-stu-id="53e3b-125">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECT01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="53e3b-126">如果您要建立新資源信箱：</span><span class="sxs-lookup"><span data-stu-id="53e3b-126">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECT01@contoso.com' -Alias PROJECT01 -Name "Project--01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="53e3b-127">若要改善會議體驗，您必須將使用者帳戶Exchange屬性設定如下：</span><span class="sxs-lookup"><span data-stu-id="53e3b-127">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="53e3b-128">為您的內部部署網域帳戶新增電子郵件地址</span><span class="sxs-lookup"><span data-stu-id="53e3b-128">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="53e3b-129">在 **Active Directory 使用者和電腦 AD** 工具中，以滑鼠右鍵按一下要建立 Microsoft Teams 會議室 帳戶的容器或組織單位，按一下 [**新增**，然後按一下 **[使用者**。</span><span class="sxs-lookup"><span data-stu-id="53e3b-129">In **Active Directory Users and Computers AD** tool, right-click on the container or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>
2. <span data-ttu-id="53e3b-130">從先前的 Cmdlet (Set-Mailbox 或 New-Mailbox) 輸入顯示名稱 ( ) - 身分識別) ，將別名輸入到使用者 **登** 入名稱方塊。</span><span class="sxs-lookup"><span data-stu-id="53e3b-130">Type the display name (- Identity ) from the prior cmdlet (Set-Mailbox or New-Mailbox) into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="53e3b-131">按一下 **[下一步**。</span><span class="sxs-lookup"><span data-stu-id="53e3b-131">Click **Next**.</span></span>
3. <span data-ttu-id="53e3b-132">輸入此帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="53e3b-132">Type the password for this account.</span></span> <span data-ttu-id="53e3b-133">您必須重新輸入以進行驗證。</span><span class="sxs-lookup"><span data-stu-id="53e3b-133">You'll need to retype it for verification.</span></span> <span data-ttu-id="53e3b-134">請確定選取 **的唯** 一選項為密碼永不過期核取方塊。</span><span class="sxs-lookup"><span data-stu-id="53e3b-134">Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="53e3b-135">選取 **密碼永不過期** 是商務用 Skype Server Microsoft Teams 會議室。</span><span class="sxs-lookup"><span data-stu-id="53e3b-135">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="53e3b-136">您的網域規則可能會禁止密碼過期。</span><span class="sxs-lookup"><span data-stu-id="53e3b-136">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="53e3b-137">如果是這樣，您必須為每個使用者帳戶建立例外Microsoft Teams 會議室例外。</span><span class="sxs-lookup"><span data-stu-id="53e3b-137">If so, you'll need to create an exception for each Microsoft Teams Rooms user account.</span></span>
  
4. <span data-ttu-id="53e3b-138">按一下 **[完成** 並建立帳戶。</span><span class="sxs-lookup"><span data-stu-id="53e3b-138">Click **Finish** to create the account.</span></span>
5. <span data-ttu-id="53e3b-139">建立帳戶之後，請執行目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="53e3b-139">After you have created the account, run a directory synchronization.</span></span> <span data-ttu-id="53e3b-140">您可以在 PowerShell 中使用 [Set-MsolDirSyncConfiguration 來](/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) 完成這項工作。</span><span class="sxs-lookup"><span data-stu-id="53e3b-140">This can be accomplished by using [Set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) in PowerShell.</span></span> <span data-ttu-id="53e3b-141">完成後，請前往使用者頁面，並確認在先前步驟中建立的帳戶已合併。</span><span class="sxs-lookup"><span data-stu-id="53e3b-141">When that is complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

### <a name="assign-a-microsoft-365-or-office-365-license"></a><span data-ttu-id="53e3b-142">指派授權Microsoft 365或Office 365授權</span><span class="sxs-lookup"><span data-stu-id="53e3b-142">Assign a Microsoft 365 or Office 365 license</span></span>

1. <span data-ttu-id="53e3b-143">首先，請連接到 Azure AD 以申請一些帳戶設定。</span><span class="sxs-lookup"><span data-stu-id="53e3b-143">First, connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="53e3b-144">您可以執行此 Cmdlet 以連接。</span><span class="sxs-lookup"><span data-stu-id="53e3b-144">You can run this cmdlet to connect.</span></span> <span data-ttu-id="53e3b-145">有關 Active Directory 的詳細資訊，請參閱 [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="53e3b-145">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

   > [!NOTE]
   > <span data-ttu-id="53e3b-146">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0)不支援。</span><span class="sxs-lookup"><span data-stu-id="53e3b-146">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span>

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. <span data-ttu-id="53e3b-147">使用者帳戶必須擁有有效的授權Microsoft 365或Office 365，以確保Exchange商務用 Skype Server有效。</span><span class="sxs-lookup"><span data-stu-id="53e3b-147">The user account needs to have a valid Microsoft 365 or Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="53e3b-148">如果您有授權，您必須將使用位置指派給使用者帳戶，這決定您的帳戶可以使用哪些授權 SKUs。</span><span class="sxs-lookup"><span data-stu-id="53e3b-148">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="53e3b-149">您將在下列步驟中進行作業。</span><span class="sxs-lookup"><span data-stu-id="53e3b-149">You'll make the assignment in a following step.</span></span>
3. <span data-ttu-id="53e3b-150">接下來，使用 `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="53e3b-150">Next, use `Get-MsolAccountSku`</span></span> <!--Get-AzureADSubscribedSku--> <span data-ttu-id="53e3b-151">來為貴組織或組織Microsoft 365 SKus Office 365清單。</span><span class="sxs-lookup"><span data-stu-id="53e3b-151">to retrieve a list of available SKUs for your Microsoft 365 or Office 365 organization.</span></span>
4. <span data-ttu-id="53e3b-152">列出 SKUs 之後，您可以使用 `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="53e3b-152">Once you list out the SKUs, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense--> <span data-ttu-id="53e3b-153">Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="53e3b-153">cmdlet.</span></span> <span data-ttu-id="53e3b-154">在此案例中，$strLicense是您看到的 SKU 程式碼， (contoso：STANDARDPACK) 。</span><span class="sxs-lookup"><span data-stu-id="53e3b-154">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span> 

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

### <a name="enable-the-user-account-with-skype-for-business-server"></a><span data-ttu-id="53e3b-155">啟用使用者帳戶商務用 Skype Server</span><span class="sxs-lookup"><span data-stu-id="53e3b-155">Enable the user account with Skype for Business Server</span></span>

> [!NOTE]
> <span data-ttu-id="53e3b-156">如果您設定只Teams 會議室加入Microsoft Teams，則不需要執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="53e3b-156">If you're setting up Teams Rooms to only join Microsoft Teams meetings, you don't need to do the following steps.</span></span> <span data-ttu-id="53e3b-157">只有在您想要啟用支援 商務用 Skype 時，才需要下列商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="53e3b-157">The following steps are only required if you want to enable support for Skype for Business.</span></span>

1. <span data-ttu-id="53e3b-158">從電腦Windows PowerShell遠端會話，如下所示：</span><span class="sxs-lookup"><span data-stu-id="53e3b-158">Create a remote Windows PowerShell session from a PC as follows:</span></span>

> [!NOTE]
> <span data-ttu-id="53e3b-159">商務用 Skype線上連接器是目前 PowerShell 模組Teams的一部分。</span><span class="sxs-lookup"><span data-stu-id="53e3b-159">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="53e3b-160">如果您使用的是最新版[PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)Teams版本，則不需要安裝 商務用 Skype 連線連接器。</span><span class="sxs-lookup"><span data-stu-id="53e3b-160">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

    ``` Powershell
    # When using Teams PowerShell Module
    Import-Module MicrosoftTeams
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

2. <span data-ttu-id="53e3b-161">若要啟用Microsoft Teams 會議室帳戶商務用 Skype Server，請執行此命令：</span><span class="sxs-lookup"><span data-stu-id="53e3b-161">To enable your Microsoft Teams Rooms account for Skype for Business Server, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="53e3b-162">如果您不確定環境中要用於 RegistrarPool 參數的值，您可以使用此命令從現有 商務用 Skype Server取得值</span><span class="sxs-lookup"><span data-stu-id="53e3b-162">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="53e3b-163">指派授權商務用 Skype Server您的帳戶Microsoft Teams 會議室授權</span><span class="sxs-lookup"><span data-stu-id="53e3b-163">Assign a Skype for Business Server license to your Microsoft Teams Rooms account</span></span>

> [!NOTE]
> <span data-ttu-id="53e3b-164">如果您設定只Teams 會議室加入Microsoft Teams，則不需要執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="53e3b-164">If you're setting up Teams Rooms to only join Microsoft Teams meetings, you don't need to do the following steps.</span></span> <span data-ttu-id="53e3b-165">只有在您想要啟用支援 商務用 Skype 時，才需要下列商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="53e3b-165">The following steps are only required if you want to enable support for Skype for Business.</span></span>

1. <span data-ttu-id="53e3b-166">以租使用者系統管理員登入，開啟 Microsoft 365系統管理中心，然後按一下系統管理應用程式。</span><span class="sxs-lookup"><span data-stu-id="53e3b-166">Log in as a tenant administrator, open the Microsoft 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="53e3b-167">按一下 [ **使用者與群組** ，然後按一下 **[新增使用者、重設密碼等>**。</span><span class="sxs-lookup"><span data-stu-id="53e3b-167">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="53e3b-168">按一下 Microsoft Teams 會議室帳戶，然後按一下 [筆形圖示以編輯帳戶資訊。</span><span class="sxs-lookup"><span data-stu-id="53e3b-168">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="53e3b-169">按一下 **[授權>**。</span><span class="sxs-lookup"><span data-stu-id="53e3b-169">Click **Licenses**.</span></span>
5. <span data-ttu-id="53e3b-170">在 **指派授權** 中，商務用 Skype (方案 2) 或商務用 Skype (方案 3) 視您的授權和企業語音需求。</span><span class="sxs-lookup"><span data-stu-id="53e3b-170">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="53e3b-171">如果您想要在 企業語音 上使用方案 3 授權Microsoft Teams 會議室。</span><span class="sxs-lookup"><span data-stu-id="53e3b-171">You'll have to use a Plan 3 license if you want to use Enterprise Voice on Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="53e3b-172">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="53e3b-172">Click **Save**.</span></span>

<span data-ttu-id="53e3b-173">若要驗證，您應該可以使用任何商務用 Skype登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="53e3b-173">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>

> [!NOTE]
> <span data-ttu-id="53e3b-174">如果您目前使用 E1、E3、E4 或 E5 SKUS，且使用 商務用 Skype 方案 2 與音訊會議或 電話系統 和通話方案，這些將會繼續使用。</span><span class="sxs-lookup"><span data-stu-id="53e3b-174">If you're currently using E1, E3, E4, or E5 SKUs with Skype for Business Plan 2 with Audio Conferencing or with Phone System and a Calling Plan, these will continue to work.</span></span> <span data-ttu-id="53e3b-175">不過，您應該考慮在目前的授權到期後，使用 Teams 會議室[授權更新中所述](rooms-licensing.md)的更簡單的授權模型。</span><span class="sxs-lookup"><span data-stu-id="53e3b-175">However, you should consider moving to a simpler licensing model as described in [Teams Meeting Room Licensing Update](rooms-licensing.md), after current licenses expire.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="53e3b-176">如果您使用的是方案 2 商務用 Skype，則只能在 Microsoft Teams 會議室 模式使用 商務用 Skype，也就是說，所有會議都會商務用 Skype會議。</span><span class="sxs-lookup"><span data-stu-id="53e3b-176">If you're using Skype for Business Plan 2, you can only use the Microsoft Teams Rooms in Skype for Business Only mode, meaning all of your meetings will be Skype for Business meetings.</span></span> <span data-ttu-id="53e3b-177">為了啟用會議室Microsoft Teams會議，建議您購買會議室授權。</span><span class="sxs-lookup"><span data-stu-id="53e3b-177">In order to enable your meeting room for Microsoft Teams meetings, we recommend you purchase the Meeting Room license.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="53e3b-178">相關主題</span><span class="sxs-lookup"><span data-stu-id="53e3b-178">Related topics</span></span>

[<span data-ttu-id="53e3b-179">設定帳戶Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="53e3b-179">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="53e3b-180">規劃 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="53e3b-180">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="53e3b-181">部署 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="53e3b-181">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="53e3b-182">設定 Microsoft Teams 會議室主控台</span><span class="sxs-lookup"><span data-stu-id="53e3b-182">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="53e3b-183">管理 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="53e3b-183">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
