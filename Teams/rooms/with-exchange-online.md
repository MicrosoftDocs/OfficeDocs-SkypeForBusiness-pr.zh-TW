---
title: 使用 Exchange Online 部署 Microsoft 團隊聊天室
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: 如需如何使用 Exchange Online 部署 Microsoft 團隊聊天室的詳細資訊，請參閱本主題。
ms.openlocfilehash: fc403e2553fce157737b1bdda75c821563e6b0dd
ms.sourcegitcommit: 9bead87a7f4c4e71f19f8980e9dce2b979735055
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/23/2020
ms.locfileid: "41268871"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a><span data-ttu-id="f4b0d-103">使用 Exchange Online 部署 Microsoft 團隊聊天室</span><span class="sxs-lookup"><span data-stu-id="f4b0d-103">Deploy Microsoft Teams Rooms with Exchange Online</span></span>

<span data-ttu-id="f4b0d-104">請閱讀本主題，瞭解如何使用 Exchange Online 和商務用 Skype Server 內部部署來部署 Microsoft 團隊聊天室。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Exchange Online and Skype for Business Server on-premises.</span></span>
  
<span data-ttu-id="f4b0d-105">如果您的組織有混合服務、部分裝載于內部部署和部分託管的網路，則您的設定將取決於託管每個服務的位置。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="f4b0d-106">本主題涵蓋 Microsoft 團隊聊天室的混合式部署，以及 Exchange 託管在線上。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted online.</span></span> <span data-ttu-id="f4b0d-107">因為這種類型的部署有這麼多不同的變化，所以不可能提供所有專案的詳細指示。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="f4b0d-108">下列處理常式適用于許多設定。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-108">The following process will work for many configurations.</span></span> <span data-ttu-id="f4b0d-109">如果程式不適合您的設定，建議您使用 Windows PowerShell 來取得與其他部署選項相同的最終結果。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="f4b0d-110">設定使用者帳戶最簡單的方法，就是使用遠端 Windows PowerShell 進行設定。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-110">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="f4b0d-111">Microsoft 提供[SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105)，此腳本將協助您建立新的使用者帳戶，或驗證您所擁有的現有資源帳戶，以協助您將它們轉換成相容的 Microsoft 團隊聊天室使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-111">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="f4b0d-112">如果您想要的話，您可以依照下列步驟來設定您的 Microsoft 團隊聊天室裝置將會使用的帳戶。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-112">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="f4b0d-113">需求</span><span class="sxs-lookup"><span data-stu-id="f4b0d-113">Requirements</span></span>

<span data-ttu-id="f4b0d-114">在使用 Exchange Online 部署 Microsoft 團隊聊天室之前，請確定您已滿足需求。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-114">Before you deploy Microsoft Teams Rooms with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="f4b0d-115">如需詳細資訊，請參閱[Microsoft 團隊會議室需求](requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-115">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="f4b0d-116">若要使用 Exchange Online 部署 Microsoft 團隊聊天室，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-116">To deploy Microsoft Teams Rooms with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="f4b0d-117">請確定您有正確的許可權來執行相關的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-117">Be sure you have the right permissions to run the associated cmdlets.</span></span> 

   > [!NOTE]
   >  <span data-ttu-id="f4b0d-118">此區段中的[Windows PowerShell Cmdlet 的 Azure Active Directory 模組](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)（例如，MsolUser）已在設定 Microsoft 團隊聊天室裝置的帳戶中經過測試。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-118">The [Azure Active Directory Module for Windows PowerShell cmdlets](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) in this section (for example,  Set-MsolUser) have been tested in setting up accounts for Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="f4b0d-119">但其他 Cmdlet 可能可以運作，但在這種特定情況下並未經過測試。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-119">It's possible that other cmdlets may work, however, they haven't been tested in this specific scenario.</span></span>
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="f4b0d-120">建立帳戶並設定 Exchange 屬性</span><span class="sxs-lookup"><span data-stu-id="f4b0d-120">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="f4b0d-121">在 PC 上啟動遠端 Windows PowerShell 會話，並聯機至 Exchange Online，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f4b0d-121">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>

``` Powershell
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
Import-PSSession $Session -DisableNameChecking
```

2. <span data-ttu-id="f4b0d-122">建立會話之後，您可以建立新的信箱並將其設為 RoomMailboxAccount，或變更現有會議室信箱的設定。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-122">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="f4b0d-123">這可讓帳戶在 Microsoft 團隊聊天室中進行驗證。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-123">This will allow the account to authenticate into Microsoft Teams Rooms.</span></span>

   <span data-ttu-id="f4b0d-124">如果您要變更現有的資源信箱：</span><span class="sxs-lookup"><span data-stu-id="f4b0d-124">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="f4b0d-125">如果您要建立新的資源信箱：</span><span class="sxs-lookup"><span data-stu-id="f4b0d-125">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="f4b0d-126">若要改善會議體驗，您必須在使用者帳戶上設定 Exchange 屬性，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f4b0d-126">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```



### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="f4b0d-127">新增內部部署網域帳戶的電子郵件地址</span><span class="sxs-lookup"><span data-stu-id="f4b0d-127">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="f4b0d-128">在**Active Directory 使用者和電腦廣告**工具中，以滑鼠右鍵按一下您的 Microsoft 小組會議室帳戶將會在其中建立的容器或組織單位，按一下 [**新增**]，然後按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-128">In **Active Directory Users and Computers AD** tool, right-click on the container or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>
2. <span data-ttu-id="f4b0d-129">從先前的 Cmdlet （將 [信箱] 或 [新信箱]）中輸入 [顯示名稱] （身分識別）至 [**完整名稱**] 方塊，然後輸入別名至 [**使用者登入名稱**] 方塊。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-129">Type the display name (- Identity ) from the prior cmdlet (Set-Mailbox or New-Mailbox) into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="f4b0d-130">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-130">Click **Next**.</span></span>
3. <span data-ttu-id="f4b0d-131">輸入此帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-131">Type the password for this account.</span></span> <span data-ttu-id="f4b0d-132">您必須重新輸入，才能進行驗證。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-132">You'll need to retype it for verification.</span></span> <span data-ttu-id="f4b0d-133">確認 [**密碼永不過期**] 核取方塊是唯一選取的選項。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-133">Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f4b0d-134">選取 [**密碼永不過期**] 是 Microsoft 團隊聊天室的商務用 Skype 伺服器需求。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-134">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="f4b0d-135">您的網域規則可能會禁止沒有過期的密碼。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-135">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="f4b0d-136">如果是這樣，您將需要針對每個 Microsoft 團隊聊天室使用者帳戶建立例外狀況。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-136">If so, you'll need to create an exception for each Microsoft Teams Rooms user account.</span></span>
  
4. <span data-ttu-id="f4b0d-137">按一下 **[完成]** 來建立帳戶。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-137">Click **Finish** to create the account.</span></span>
5. <span data-ttu-id="f4b0d-138">在您建立帳戶之後，請執行目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-138">After you have created the account, run a directory synchronization.</span></span> <span data-ttu-id="f4b0d-139">這可以透過在 PowerShell 中使用[Set MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0)來完成。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-139">This can be accomplished by using [Set-MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) in PowerShell.</span></span> <span data-ttu-id="f4b0d-140">完成後，請移至 [使用者] 頁面，確認先前步驟中建立的兩個帳戶已合併。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-140">When that is complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

### <a name="assign-an-office-365-license"></a><span data-ttu-id="f4b0d-141">指派 Office 365 授權</span><span class="sxs-lookup"><span data-stu-id="f4b0d-141">Assign an Office 365 license</span></span>

1. <span data-ttu-id="f4b0d-142">首先，連線到 Azure AD 來套用某些帳戶設定。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-142">First, connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="f4b0d-143">您可以執行此 Cmdlet 來進行連線。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-143">You can run this cmdlet to connect.</span></span> <span data-ttu-id="f4b0d-144">如需 Active Directory 的詳細資訊，請參閱[Azure ActiveDirectory （import-module msonline） 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-144">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="f4b0d-145">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)不受支援。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-145">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

  ``` PowerShell
 Connect-MsolService -Credential $cred
  ```
<!--   ``` Powershell
   Connect-AzureAD -Credential $cred
   ``` -->

2. <span data-ttu-id="f4b0d-146">使用者帳戶必須擁有有效的 Office 365 授權，以確保 Exchange 和商務用 Skype 伺服器能夠正常運作。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-146">The user account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="f4b0d-147">如果您有授權，您必須將使用位置指派給您的使用者帳戶，這會決定您的帳戶可使用哪些授權 Sku。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-147">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="f4b0d-148">您將會在下列步驟中進行作業。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-148">You'll make the assignment in a following step.</span></span>
3. <span data-ttu-id="f4b0d-149">接下來，使用`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="f4b0d-149">Next, use `Get-MsolAccountSku`</span></span> <!--Get-AzureADSubscribedSku--> <span data-ttu-id="f4b0d-150">若要為您的 Office 365 租使用者取得可用的 Sku 清單。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-150">to retrieve a list of available SKUs for your Office 365 tenant.</span></span>
4. <span data-ttu-id="f4b0d-151">當您列出 Sku 之後，您就可以使用`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="f4b0d-151">Once you list out the SKUs, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense--> <span data-ttu-id="f4b0d-152">Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f4b0d-152">cmdlet.</span></span> <span data-ttu-id="f4b0d-153">在此情況下，$strLicense 是您所看到的 SKU 程式碼（例如 contoso： STANDARDPACK）。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-153">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span> 

  ```PowerShell
    Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```
<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a><span data-ttu-id="f4b0d-154">使用商務用 Skype Server 啟用使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="f4b0d-154">Enable the user account with Skype for Business Server</span></span>

1. <span data-ttu-id="f4b0d-155">從電腦建立遠端 Windows PowerShell 會話，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f4b0d-155">Create a remote Windows PowerShell session from a PC as follows:</span></span>

    ``` Powershell
    Import-Module SkypeOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="f4b0d-156">若要啟用商務用 Skype Server 的 Microsoft 團隊房間帳戶，請執行此命令：</span><span class="sxs-lookup"><span data-stu-id="f4b0d-156">To enable your Microsoft Teams Rooms account for Skype for Business Server, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="f4b0d-157">如果您不確定要在您的環境中使用 RegistrarPool 參數的值，您可以使用此命令從現有的商務用 Skype Server 使用者取得該值</span><span class="sxs-lookup"><span data-stu-id="f4b0d-157">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="f4b0d-158">將商務用 Skype Server 授權指派給您的 Microsoft 團隊聊天室帳戶</span><span class="sxs-lookup"><span data-stu-id="f4b0d-158">Assign a Skype for Business Server license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="f4b0d-159">以租使用者管理員身分登入，開啟 Office 365 系統管理中心入口網站，然後按一下 [管理] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-159">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
2. <span data-ttu-id="f4b0d-160">按一下 [**使用者和群組**]，然後按一下 [**新增使用者、重設密碼等等**]。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-160">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="f4b0d-161">按一下 [Microsoft 團隊聊天室] 帳戶，然後按一下手寫筆圖示，即可編輯帳戶資訊。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-161">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="f4b0d-162">按一下 [**授權**]。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-162">Click **Licenses**.</span></span>
5. <span data-ttu-id="f4b0d-163">在 [**指派授權**] 中，選取 [商務用 Skype （方案2）] 或 [商務用 Skype （方案3）]，視您的授權和企業語音需求而定。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-163">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="f4b0d-164">如果您想要在 Microsoft 團隊聊天室使用企業語音，就必須使用 [方案3授權]。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-164">You'll have to use a Plan 3 license if you want to use Enterprise Voice on Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="f4b0d-165">按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-165">Click **Save**.</span></span>

<span data-ttu-id="f4b0d-166">針對驗證，您應該能夠使用任何商務用 Skype 用戶端登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="f4b0d-166">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f4b0d-167">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f4b0d-167">See also</span></span>

[<span data-ttu-id="f4b0d-168">設定 Microsoft 團隊聊天室的帳戶</span><span class="sxs-lookup"><span data-stu-id="f4b0d-168">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="f4b0d-169">規劃 Microsoft 團隊聊天室</span><span class="sxs-lookup"><span data-stu-id="f4b0d-169">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="f4b0d-170">部署 Microsoft 團隊聊天室</span><span class="sxs-lookup"><span data-stu-id="f4b0d-170">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="f4b0d-171">設定 Microsoft 團隊聊天室主控台</span><span class="sxs-lookup"><span data-stu-id="f4b0d-171">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="f4b0d-172">管理 Microsoft 團隊聊天室</span><span class="sxs-lookup"><span data-stu-id="f4b0d-172">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
