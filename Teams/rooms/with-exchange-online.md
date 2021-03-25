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
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a><span data-ttu-id="abf1a-103">使用 Exchange Online 部署 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="abf1a-103">Deploy Microsoft Teams Rooms with Exchange Online</span></span>

<span data-ttu-id="abf1a-104">請閱讀本主題，以瞭解如何使用 Exchange Online 部署 Microsoft Teams 會議室，以及商務用 Skype Server 內部部署。</span><span class="sxs-lookup"><span data-stu-id="abf1a-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Exchange Online and Skype for Business Server on-premises.</span></span>
  
<span data-ttu-id="abf1a-105">如果貴組織有混合式服務，其中一些是內部部署，有些是線上託管，則您的組式取決於每個服務的託管位置。</span><span class="sxs-lookup"><span data-stu-id="abf1a-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="abf1a-106">本主題涵蓋線上託管 Exchange 的 Microsoft Teams 會議室混合式部署。</span><span class="sxs-lookup"><span data-stu-id="abf1a-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted online.</span></span> <span data-ttu-id="abf1a-107">由於這類部署有許多不同的變化，因此無法針對所有部署提供詳細指示。</span><span class="sxs-lookup"><span data-stu-id="abf1a-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="abf1a-108">下列程式適用于許多配置。</span><span class="sxs-lookup"><span data-stu-id="abf1a-108">The following process will work for many configurations.</span></span> <span data-ttu-id="abf1a-109">如果此程式不適用於您的設定，建議您使用 Windows PowerShell 達到與本文所述相同的最終結果，以及其他部署選項。</span><span class="sxs-lookup"><span data-stu-id="abf1a-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="abf1a-110">設定使用者帳戶最簡單的方法是使用遠端 Windows PowerShell 來設定使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="abf1a-110">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="abf1a-111">Microsoft 提供 [SkypeRoomProvisioningScript.ps1， ](https://go.microsoft.com/fwlink/?linkid=870105)此腳本可協助建立新的使用者帳戶，或驗證您現有的資源帳戶，以便協助您將帳戶轉換為相容的 Microsoft Teams 會議室使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="abf1a-111">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="abf1a-112">視需要，您可以遵循下列步驟來設定 Microsoft Teams 會議室裝置將會使用的帳戶。</span><span class="sxs-lookup"><span data-stu-id="abf1a-112">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="abf1a-113">需求</span><span class="sxs-lookup"><span data-stu-id="abf1a-113">Requirements</span></span>

<span data-ttu-id="abf1a-114">使用 Exchange Online 部署 Microsoft Teams 會議室之前，請確定您符合需求。</span><span class="sxs-lookup"><span data-stu-id="abf1a-114">Before you deploy Microsoft Teams Rooms with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="abf1a-115">詳細資訊，請參閱 [Microsoft Teams 會議室需求](requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="abf1a-115">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="abf1a-116">若要使用 Exchange Online 部署 Microsoft Teams 會議室，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="abf1a-116">To deploy Microsoft Teams Rooms with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="abf1a-117">請確定您擁有執行關聯的 Cmdlet 的許可權。</span><span class="sxs-lookup"><span data-stu-id="abf1a-117">Be sure you have the right permissions to run the associated cmdlets.</span></span> 

   > [!NOTE]
   >  <span data-ttu-id="abf1a-118">本節 [中的 Windows PowerShell](/powershell/azure/active-directory/overview?view=azureadps-1.0) Azure Active Directory 模組 Cmdlet (例如 Set-MsolUser) 已經過設定 Microsoft Teams 會議室裝置帳戶的測試。</span><span class="sxs-lookup"><span data-stu-id="abf1a-118">The [Azure Active Directory Module for Windows PowerShell cmdlets](/powershell/azure/active-directory/overview?view=azureadps-1.0) in this section (for example,  Set-MsolUser) have been tested in setting up accounts for Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="abf1a-119">不過，其他 Cmdlet 可能可以工作，但尚未在此特定情況下進行測試。</span><span class="sxs-lookup"><span data-stu-id="abf1a-119">It's possible that other cmdlets may work, however, they haven't been tested in this specific scenario.</span></span>

<span data-ttu-id="abf1a-120">如果您部署 Active Directory Federation Services (AD FS) ，您可能必須先將使用者帳戶轉換為受管理的使用者，然後再執行這些步驟，然後在完成這些步驟後將使用者轉換回聯盟使用者。</span><span class="sxs-lookup"><span data-stu-id="abf1a-120">If you deployed Active Directory Federation Services (AD FS), you may have to convert the user account to a managed user before you follow these steps, and then convert the user back to a federated user after you complete these steps.</span></span>
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="abf1a-121">建立帳戶並設定 Exchange 屬性</span><span class="sxs-lookup"><span data-stu-id="abf1a-121">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="abf1a-122">在 PC 上啟動遠端 Windows PowerShell 會話，然後連線到 Exchange Online，如下所示：</span><span class="sxs-lookup"><span data-stu-id="abf1a-122">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org = 'contoso.microsoft.com'
    $cred = Get-Credential $admin@$org
    $sess = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
    Import-PSSession $sess -DisableNameChecking
    ```

2. <span data-ttu-id="abf1a-123">建立會話之後，您可以建立新信箱並啟用為 RoomMailboxAccount，或變更現有會議室信箱的設定。</span><span class="sxs-lookup"><span data-stu-id="abf1a-123">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="abf1a-124">這會允許帳戶驗證至 Microsoft Teams 會議室。</span><span class="sxs-lookup"><span data-stu-id="abf1a-124">This will allow the account to authenticate into Microsoft Teams Rooms.</span></span>

   <span data-ttu-id="abf1a-125">如果您要變更現有的資源信箱：</span><span class="sxs-lookup"><span data-stu-id="abf1a-125">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECT01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="abf1a-126">如果您要建立新資源信箱：</span><span class="sxs-lookup"><span data-stu-id="abf1a-126">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECT01@contoso.com' -Alias PROJECT01 -Name "Project--01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="abf1a-127">若要改善會議體驗，您必須在使用者帳戶上設定 Exchange 屬性，如下所示：</span><span class="sxs-lookup"><span data-stu-id="abf1a-127">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="abf1a-128">為您的內部部署網域帳戶新增電子郵件地址</span><span class="sxs-lookup"><span data-stu-id="abf1a-128">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="abf1a-129">在 **Active Directory 使用者和電腦 AD** 工具中，以滑鼠右鍵按一下要建立 Microsoft Teams 會議室帳戶的容器或組織單位，按一下 [ **新增**，然後按一下 **[使用者**> 。</span><span class="sxs-lookup"><span data-stu-id="abf1a-129">In **Active Directory Users and Computers AD** tool, right-click on the container or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>
2. <span data-ttu-id="abf1a-130">從先前的 Cmdlet (Set-Mailbox 或 New-Mailbox) 輸入顯示名稱 ( ) - 身分識別) ，將別名輸入到使用者 **登** 入名稱方塊。</span><span class="sxs-lookup"><span data-stu-id="abf1a-130">Type the display name (- Identity ) from the prior cmdlet (Set-Mailbox or New-Mailbox) into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="abf1a-131">按一下 **[下一步**。</span><span class="sxs-lookup"><span data-stu-id="abf1a-131">Click **Next**.</span></span>
3. <span data-ttu-id="abf1a-132">輸入此帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="abf1a-132">Type the password for this account.</span></span> <span data-ttu-id="abf1a-133">您必須重新輸入以進行驗證。</span><span class="sxs-lookup"><span data-stu-id="abf1a-133">You'll need to retype it for verification.</span></span> <span data-ttu-id="abf1a-134">請確定選取 **的唯** 一選項為密碼永不過期核取方塊。</span><span class="sxs-lookup"><span data-stu-id="abf1a-134">Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="abf1a-135">選取 **密碼永不過期** 是 Microsoft Teams 會議室商務用 Skype Server 的一項需求。</span><span class="sxs-lookup"><span data-stu-id="abf1a-135">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="abf1a-136">您的網域規則可能會禁止密碼過期。</span><span class="sxs-lookup"><span data-stu-id="abf1a-136">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="abf1a-137">如果是這樣，您必須為每個 Microsoft Teams 會議室使用者帳戶建立例外。</span><span class="sxs-lookup"><span data-stu-id="abf1a-137">If so, you'll need to create an exception for each Microsoft Teams Rooms user account.</span></span>
  
4. <span data-ttu-id="abf1a-138">按一下 **[完成** 並建立帳戶。</span><span class="sxs-lookup"><span data-stu-id="abf1a-138">Click **Finish** to create the account.</span></span>
5. <span data-ttu-id="abf1a-139">建立帳戶之後，請執行目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="abf1a-139">After you have created the account, run a directory synchronization.</span></span> <span data-ttu-id="abf1a-140">您可以在 PowerShell 中使用 [Set-MsolDirSyncConfiguration 來](/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) 完成這項工作。</span><span class="sxs-lookup"><span data-stu-id="abf1a-140">This can be accomplished by using [Set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) in PowerShell.</span></span> <span data-ttu-id="abf1a-141">完成時，請前往使用者頁面，並確認先前步驟所建立之兩個帳戶已合併。</span><span class="sxs-lookup"><span data-stu-id="abf1a-141">When that is complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

### <a name="assign-a-microsoft-365-or-office-365-license"></a><span data-ttu-id="abf1a-142">指派 Microsoft 365 或 Office 365 授權</span><span class="sxs-lookup"><span data-stu-id="abf1a-142">Assign a Microsoft 365 or Office 365 license</span></span>

1. <span data-ttu-id="abf1a-143">首先，請連接到 Azure AD 以申請一些帳戶設定。</span><span class="sxs-lookup"><span data-stu-id="abf1a-143">First, connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="abf1a-144">您可以執行此 Cmdlet 以連接。</span><span class="sxs-lookup"><span data-stu-id="abf1a-144">You can run this cmdlet to connect.</span></span> <span data-ttu-id="abf1a-145">有關 Active Directory 的詳細資訊，請參閱 [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="abf1a-145">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

   > [!NOTE]
   > <span data-ttu-id="abf1a-146">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) 不受支援。</span><span class="sxs-lookup"><span data-stu-id="abf1a-146">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span>

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. <span data-ttu-id="abf1a-147">使用者帳戶必須擁有有效的 Microsoft 365 或 Office 365 授權，以確保 Exchange 和商務用 Skype Server 能夠工作。</span><span class="sxs-lookup"><span data-stu-id="abf1a-147">The user account needs to have a valid Microsoft 365 or Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="abf1a-148">如果您有授權，您必須將使用位置指派給使用者帳戶，這決定您的帳戶可以使用哪些授權 SKUs。</span><span class="sxs-lookup"><span data-stu-id="abf1a-148">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="abf1a-149">您將在下列步驟中進行作業。</span><span class="sxs-lookup"><span data-stu-id="abf1a-149">You'll make the assignment in a following step.</span></span>
3. <span data-ttu-id="abf1a-150">接下來，使用 `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="abf1a-150">Next, use `Get-MsolAccountSku`</span></span> <!--Get-AzureADSubscribedSku--> <span data-ttu-id="abf1a-151">以針對您的 Microsoft 365 或 Office 365 組織，來取回可用的 SUS 清單。</span><span class="sxs-lookup"><span data-stu-id="abf1a-151">to retrieve a list of available SKUs for your Microsoft 365 or Office 365 organization.</span></span>
4. <span data-ttu-id="abf1a-152">列出 SKUs 之後，您可以使用 `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="abf1a-152">Once you list out the SKUs, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense--> <span data-ttu-id="abf1a-153">Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="abf1a-153">cmdlet.</span></span> <span data-ttu-id="abf1a-154">在此案例中，$strLicense是您看到的 SKU 程式碼， (contoso：STANDARDPACK) 。</span><span class="sxs-lookup"><span data-stu-id="abf1a-154">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span> 

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

### <a name="enable-the-user-account-with-skype-for-business-server"></a><span data-ttu-id="abf1a-155">使用商務用 Skype Server 啟用使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="abf1a-155">Enable the user account with Skype for Business Server</span></span>

1. <span data-ttu-id="abf1a-156">從電腦建立遠端 Windows PowerShell 會話，如下所示：</span><span class="sxs-lookup"><span data-stu-id="abf1a-156">Create a remote Windows PowerShell session from a PC as follows:</span></span>

> [!NOTE]
> <span data-ttu-id="abf1a-157">商務用 Skype Online Connector 目前是 Teams PowerShell 最新模組的一部分。</span><span class="sxs-lookup"><span data-stu-id="abf1a-157">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="abf1a-158">如果您使用的是最新的 [Teams PowerShell 公開發行](https://www.powershellgallery.com/packages/MicrosoftTeams/)，則不需要安裝商務用 Skype Online 連接器。</span><span class="sxs-lookup"><span data-stu-id="abf1a-158">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

    ``` Powershell
    # When using Teams PowerShell Module
    Import-Module MicrosoftTeams
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

2. <span data-ttu-id="abf1a-159">若要啟用商務用 Skype Server 的 Microsoft Teams 會議室帳戶，請執行此命令：</span><span class="sxs-lookup"><span data-stu-id="abf1a-159">To enable your Microsoft Teams Rooms account for Skype for Business Server, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="abf1a-160">如果您不確定環境中要用於 RegistrarPool 參數的值，您可以使用此命令從現有的商務用 Skype Server 使用者取得值</span><span class="sxs-lookup"><span data-stu-id="abf1a-160">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="abf1a-161">將商務用 Skype Server 授權指派至您的 Microsoft Teams 會議室帳戶</span><span class="sxs-lookup"><span data-stu-id="abf1a-161">Assign a Skype for Business Server license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="abf1a-162">以租使用者系統管理員登入，開啟 Microsoft 365 系統管理中心，然後按一下系統管理應用程式。</span><span class="sxs-lookup"><span data-stu-id="abf1a-162">Log in as a tenant administrator, open the Microsoft 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="abf1a-163">按一下 [ **使用者與群組** ，然後按一下 **[新增使用者、重設密碼等>**。</span><span class="sxs-lookup"><span data-stu-id="abf1a-163">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="abf1a-164">按一下 Microsoft Teams 會議室帳戶，然後按一下觸控筆圖示以編輯帳戶資訊。</span><span class="sxs-lookup"><span data-stu-id="abf1a-164">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="abf1a-165">按一下 **[授權>**。</span><span class="sxs-lookup"><span data-stu-id="abf1a-165">Click **Licenses**.</span></span>
5. <span data-ttu-id="abf1a-166">在 **指派授權** 中， (方案 2) 或商務用 Skype (方案 3) 視您的授權和企業語音需求。</span><span class="sxs-lookup"><span data-stu-id="abf1a-166">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="abf1a-167">如果您想要在 Microsoft Teams 會議室使用企業語音，您必須使用方案 3 授權。</span><span class="sxs-lookup"><span data-stu-id="abf1a-167">You'll have to use a Plan 3 license if you want to use Enterprise Voice on Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="abf1a-168">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="abf1a-168">Click **Save**.</span></span>

<span data-ttu-id="abf1a-169">若要進行驗證，您應該可以使用任何商務用 Skype 用戶端登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="abf1a-169">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>

> [!NOTE]
> <span data-ttu-id="abf1a-170">如果您目前使用 E1、E3、E4 或 E5 SKUS 與商務用 Skype 方案 2 與音訊會議或電話系統及通話方案，這些將會繼續使用。</span><span class="sxs-lookup"><span data-stu-id="abf1a-170">If you're currently using E1, E3, E4, or E5 SKUs with Skype for Business Plan 2 with Audio Conferencing or with Phone System and a Calling Plan, these will continue to work.</span></span> <span data-ttu-id="abf1a-171">不過，您應該考慮在目前的授權到期後，使用 [Teams 會議室](rooms-licensing.md)授權更新中所述的更簡單的授權模型。</span><span class="sxs-lookup"><span data-stu-id="abf1a-171">However, you should consider moving to a simpler licensing model as described in [Teams Meeting Room Licensing Update](rooms-licensing.md), after current licenses expire.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="abf1a-172">如果您使用的是商務用 Skype 方案 2，則只能在商務用 Skype 模式使用 Microsoft Teams 會議室，這表示所有會議都是商務用 Skype 會議。</span><span class="sxs-lookup"><span data-stu-id="abf1a-172">If you're using Skype for Business Plan 2, you can only use the Microsoft Teams Rooms in Skype for Business Only mode, meaning all of your meetings will be Skype for Business meetings.</span></span> <span data-ttu-id="abf1a-173">為了啟用您的會議室進行 Microsoft Teams 會議，我們建議您購買會議室授權。</span><span class="sxs-lookup"><span data-stu-id="abf1a-173">In order to enable your meeting room for Microsoft Teams meetings, we recommend you purchase the Meeting Room license.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="abf1a-174">相關主題</span><span class="sxs-lookup"><span data-stu-id="abf1a-174">Related topics</span></span>

[<span data-ttu-id="abf1a-175">設定 Microsoft Teams 會議室的帳戶</span><span class="sxs-lookup"><span data-stu-id="abf1a-175">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="abf1a-176">規劃 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="abf1a-176">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="abf1a-177">部署 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="abf1a-177">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="abf1a-178">設定 Microsoft Teams 會議室主控台</span><span class="sxs-lookup"><span data-stu-id="abf1a-178">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="abf1a-179">管理 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="abf1a-179">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)