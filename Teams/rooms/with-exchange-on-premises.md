---
title: 使用Microsoft Teams 會議室部署Exchange部署
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
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: 請參閱本主題，瞭解如何在混合式環境中部署Microsoft Teams 會議室內部部署Exchange部署。
ms.openlocfilehash: 3931ba89dd4ad0dfd994fdf27a3f209275850116
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117351"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a><span data-ttu-id="2091b-103">在Microsoft Teams 會議室部署Exchange部署</span><span class="sxs-lookup"><span data-stu-id="2091b-103">Deploy Microsoft Teams Rooms with Exchange on premises</span></span>

<span data-ttu-id="2091b-104">請閱讀本主題，瞭解如何在混合式環境中Microsoft Teams 會議室內部部署Exchange內部部署或Microsoft Teams商務用 Skype部署。</span><span class="sxs-lookup"><span data-stu-id="2091b-104">Read this topic for information on how to deploy Microsoft Teams Rooms in a hybrid environment with Exchange on premises and Microsoft Teams or Skype for Business Online.</span></span>
  
<span data-ttu-id="2091b-105">如果貴組織有混合式服務，其中一些是內部部署，有些是線上託管，則您的組式取決於每個服務的託管位置。</span><span class="sxs-lookup"><span data-stu-id="2091b-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="2091b-106">本主題涵蓋內部部署Microsoft Teams 會議室Exchange的混合式部署。</span><span class="sxs-lookup"><span data-stu-id="2091b-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted on premises.</span></span> <span data-ttu-id="2091b-107">由於這類部署有許多不同的變化，因此無法針對所有部署提供詳細指示。</span><span class="sxs-lookup"><span data-stu-id="2091b-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="2091b-108">下列程式適用于許多配置。</span><span class="sxs-lookup"><span data-stu-id="2091b-108">The following process will work for many configurations.</span></span> <span data-ttu-id="2091b-109">如果此程式不適用於您的設定，建議您使用 Windows PowerShell來達到此處所記載的相同最終結果，以及其他部署選項。</span><span class="sxs-lookup"><span data-stu-id="2091b-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="2091b-110">Microsoft 提供[SkypeRoomProvisioningScript.ps1，](https://go.microsoft.com/fwlink/?linkid=870105)此腳本可協助建立新的使用者帳戶，或驗證您現有的資源帳戶，以便協助您將這些帳戶轉換為Microsoft Teams 會議室使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="2091b-110">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="2091b-111">您可以按照下列步驟來設定您的裝置Microsoft Teams 會議室帳戶。</span><span class="sxs-lookup"><span data-stu-id="2091b-111">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="2091b-112">需求</span><span class="sxs-lookup"><span data-stu-id="2091b-112">Requirements</span></span>

<span data-ttu-id="2091b-113">在內部Microsoft Teams 會議室部署Exchange，請確定您符合需求。</span><span class="sxs-lookup"><span data-stu-id="2091b-113">Before you deploy Microsoft Teams Rooms with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="2091b-114">詳細資訊，請參閱Microsoft Teams 會議室[需求](requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2091b-114">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="2091b-115">如果您要在內部Microsoft Teams 會議室部署Exchange，您將使用 Active Directory 管理工具為您的內部部署網域帳戶新增電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="2091b-115">If you are deploying Microsoft Teams Rooms with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="2091b-116">此帳戶會同步到 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="2091b-116">This account will be synced to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="2091b-117">您必須：</span><span class="sxs-lookup"><span data-stu-id="2091b-117">You will need to:</span></span>
  
- <span data-ttu-id="2091b-118">建立帳戶，然後與 Active Directory 同步處理帳戶。</span><span class="sxs-lookup"><span data-stu-id="2091b-118">Create an account and synchronize the account with Active Directory.</span></span>

- <span data-ttu-id="2091b-119">啟用遠端信箱並設定屬性。</span><span class="sxs-lookup"><span data-stu-id="2091b-119">Enable the remote mailbox and set properties.</span></span>

- <span data-ttu-id="2091b-120">指派授權Microsoft 365或Office 365授權。</span><span class="sxs-lookup"><span data-stu-id="2091b-120">Assign an Microsoft 365 or Office 365 license.</span></span>

- <span data-ttu-id="2091b-121">啟用裝置帳戶商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="2091b-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="2091b-122">若要啟用裝置帳戶，您的環境必須符合下列先決條件：</span><span class="sxs-lookup"><span data-stu-id="2091b-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>

  - <span data-ttu-id="2091b-123">您必須在方案或商務用 Skype中 (2) 或更Microsoft 365 Office 365方案。</span><span class="sxs-lookup"><span data-stu-id="2091b-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="2091b-124">該計畫需要支援會議功能。</span><span class="sxs-lookup"><span data-stu-id="2091b-124">The plan needs to support conferencing capability.</span></span>
  
  - <span data-ttu-id="2091b-125">如果您需要使用 pstN 企業語音 (電話) 電話服務提供者Microsoft Teams 會議室您需要使用 商務用 Skype 方案 3 (方案) 。</span><span class="sxs-lookup"><span data-stu-id="2091b-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Microsoft Teams Rooms you need Skype for Business Online (Plan 3).</span></span>

  - <span data-ttu-id="2091b-126">在將會議室帳戶Microsoft Teams或 商務用 Skype Online 時，電話號碼應在帳戶啟用為會議室帳戶之前指派。</span><span class="sxs-lookup"><span data-stu-id="2091b-126">When configuring a room account with Microsoft Teams or Skype for Business Online, the phone number should be assigned prior to the account being enabled as a room account.</span></span>
  
  - <span data-ttu-id="2091b-127">您的租使用者使用者必須擁有Exchange信箱。</span><span class="sxs-lookup"><span data-stu-id="2091b-127">Your tenant users must have Exchange mailboxes.</span></span>
  
  - <span data-ttu-id="2091b-128">您的 Microsoft Teams 會議室 帳戶需要 商務用 Skype Online (方案 2) 或 商務用 Skype Online (方案 3) 授權，但不需要 Exchange Online 授權。</span><span class="sxs-lookup"><span data-stu-id="2091b-128">Your Microsoft Teams Rooms account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>

- <span data-ttu-id="2091b-129">指派授權商務用 Skype Server您的帳戶Microsoft Teams 會議室授權。</span><span class="sxs-lookup"><span data-stu-id="2091b-129">Assign a Skype for Business Server license to your Microsoft Teams Rooms account.</span></span>

### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="2091b-130">建立帳戶並同步處理 Active Directory</span><span class="sxs-lookup"><span data-stu-id="2091b-130">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="2091b-131">在 **Active Directory 使用者** 與電腦工具中，以滑鼠右鍵按一下要建立您 Microsoft Teams 會議室 帳戶的資料夾或組織單位，按一下 [**新增**，然後按一下 **[使用者**> 。</span><span class="sxs-lookup"><span data-stu-id="2091b-131">In the **Active Directory Users and Computers** tool, right-click on the folder or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>

2. <span data-ttu-id="2091b-132">在全名方塊中輸入上一個 Cmdlet 的顯示名稱，將別名輸入到使用者 **登入名稱** 方塊中。 </span><span class="sxs-lookup"><span data-stu-id="2091b-132">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="2091b-133">按一下 **[下一步**。</span><span class="sxs-lookup"><span data-stu-id="2091b-133">Click **Next**.</span></span>

3. <span data-ttu-id="2091b-134">輸入此帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="2091b-134">Type the password for this account.</span></span> <span data-ttu-id="2091b-135">您必須重新輸入以進行驗證。</span><span class="sxs-lookup"><span data-stu-id="2091b-135">You'll need to retype it for verification.</span></span> <span data-ttu-id="2091b-136">請確定選取 **的唯** 一選項為密碼永不過期核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2091b-136">Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2091b-137">選取 **密碼永不過期** 是商務用 Skype Server Microsoft Teams 會議室。</span><span class="sxs-lookup"><span data-stu-id="2091b-137">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="2091b-138">您的網域規則可能會禁止不會過期的密碼。</span><span class="sxs-lookup"><span data-stu-id="2091b-138">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="2091b-139">如果是這樣，您必須為每個裝置帳戶Microsoft Teams 會議室例外。</span><span class="sxs-lookup"><span data-stu-id="2091b-139">If so, you'll need to create an exception for each Microsoft Teams Rooms device account.</span></span>
  
4. <span data-ttu-id="2091b-140">建立帳戶之後，請執行目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="2091b-140">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="2091b-141">完成後，請前往您系統管理中心Microsoft 365使用者頁面，並確認在先前步驟中建立的帳戶已合併至線上。</span><span class="sxs-lookup"><span data-stu-id="2091b-141">When it's complete, go to the users page in your Microsoft 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="2091b-142">啟用遠端信箱和設定屬性</span><span class="sxs-lookup"><span data-stu-id="2091b-142">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="2091b-143">[開啟 Exchange管理命令殼](/powershell/exchange/exchange-server/open-the-exchange-management-shell)，或使用[遠端 PowerShell Exchange伺服器。](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)</span><span class="sxs-lookup"><span data-stu-id="2091b-143">[Open the Exchange Management Shell](/powershell/exchange/exchange-server/open-the-exchange-management-shell) or [connect to your Exchange server using remote PowerShell](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="2091b-144">在 Exchange PowerShell 中，為帳戶建立信箱 (，執行下列命令) 啟用帳戶：</span><span class="sxs-lookup"><span data-stu-id="2091b-144">In Exchange PowerShell, create a mailbox for the account (mailbox-enable the account) by running the following command:</span></span>

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   <span data-ttu-id="2091b-145">有關詳細的語法和參數資訊，請參閱 [啟用信箱](/powershell/module/exchange/mailboxes/enable-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="2091b-145">For detailed syntax and parameter information, see [Enable-Mailbox](/powershell/module/exchange/mailboxes/enable-mailbox).</span></span>

3. <span data-ttu-id="2091b-146">在 Exchange PowerShell 中，設定會議室信箱上的下列設定以改善會議體驗：</span><span class="sxs-lookup"><span data-stu-id="2091b-146">In Exchange PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="2091b-147">自動化處理：自動 (會議召集人直接收到會議室預約決定，而不需要人為介入：free = accept;busy = decline.) </span><span class="sxs-lookup"><span data-stu-id="2091b-147">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="2091b-148">AddOrganizerToSubject：$false (會議召集人不會新增到會議要求的主題中。) </span><span class="sxs-lookup"><span data-stu-id="2091b-148">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="2091b-149">DeleteComments：$false (在傳入會議要求的郵件內文中保留任何文字。) </span><span class="sxs-lookup"><span data-stu-id="2091b-149">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="2091b-150">DeleteSubject：$false (保留傳入會議要求的主題。) </span><span class="sxs-lookup"><span data-stu-id="2091b-150">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="2091b-151">RemovePrivateProperty：$false (確保會議召集人在原始會議要求中所送出的私人標標維持為指定的狀態。) </span><span class="sxs-lookup"><span data-stu-id="2091b-151">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="2091b-152">AddAdditionalResponse：$true (其他Response 參數指定的文字會新加到會議要求中。) </span><span class="sxs-lookup"><span data-stu-id="2091b-152">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="2091b-153">其他Response：「這是Skype會議室！</span><span class="sxs-lookup"><span data-stu-id="2091b-153">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="2091b-154"> (新增到會議要求的其他文字。) </span><span class="sxs-lookup"><span data-stu-id="2091b-154">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="2091b-155">此範例在名為 Project-Rigel-01 的會議室信箱上設定這些設定。</span><span class="sxs-lookup"><span data-stu-id="2091b-155">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="2091b-156">有關詳細的語法和參數資訊，請參閱 [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing)。</span><span class="sxs-lookup"><span data-stu-id="2091b-156">For detailed syntax and parameter information, see [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

### <a name="assign-a-microsoft-365-or-office-365-license"></a><span data-ttu-id="2091b-157">指派授權Microsoft 365或Office 365授權</span><span class="sxs-lookup"><span data-stu-id="2091b-157">Assign a Microsoft 365 or Office 365 license</span></span>

1. <span data-ttu-id="2091b-158">連線Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="2091b-158">Connect to Azure Active Directory.</span></span> <span data-ttu-id="2091b-159">有關 Active Directory 的詳細資訊，請參閱 [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="2091b-159">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="2091b-160">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0)不支援。</span><span class="sxs-lookup"><span data-stu-id="2091b-160">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

2. <span data-ttu-id="2091b-161">裝置帳戶必須擁有有效的授權Microsoft 365授權Office 365，Exchange Microsoft Teams無法使用。</span><span class="sxs-lookup"><span data-stu-id="2091b-161">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams will not work.</span></span> <span data-ttu-id="2091b-162">如果您有授權，您必須將使用位置指派給裝置帳戶，這決定您的帳戶可以使用哪些授權 SKUs。</span><span class="sxs-lookup"><span data-stu-id="2091b-162">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="2091b-163">您可以使用 `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="2091b-163">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="2091b-164">以取回可用的 SKUS 清單。</span><span class="sxs-lookup"><span data-stu-id="2091b-164">to retrieve a list of available SKUs.</span></span>

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. <span data-ttu-id="2091b-165">接下來，您可以使用 `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="2091b-165">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense --> <span data-ttu-id="2091b-166">Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2091b-166">cmdlet.</span></span> <span data-ttu-id="2091b-167">在此案例中，$strLicense是您看到的 SKU 程式碼， (contoso：STANDARDPACK) 。</span><span class="sxs-lookup"><span data-stu-id="2091b-167">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

  ``` PowerShell
  Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
  Get-MsolAccountSku
  Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```

<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```  -->

   <span data-ttu-id="2091b-168">有關詳細指示，請參閱使用 PowerShell 指派授權[Office 365使用者帳戶](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="2091b-168">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="enable-the-device-account"></a><span data-ttu-id="2091b-169">啟用裝置帳戶</span><span class="sxs-lookup"><span data-stu-id="2091b-169">Enable the device account</span></span>

<span data-ttu-id="2091b-170">商務用 SkypeOnline PowerShell 用於管理線上和 Microsoft Teams 商務用 Skype服務。</span><span class="sxs-lookup"><span data-stu-id="2091b-170">Skype for Business Online PowerShell is used to manage services for both Microsoft Teams and Skype for Business Online.</span></span>

1. <span data-ttu-id="2091b-171">從電腦Windows PowerShell遠端會話，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2091b-171">Create a remote Windows PowerShell session from a PC as follows:</span></span>
> [!NOTE]
> <span data-ttu-id="2091b-172">商務用 Skype線上連接器是目前 PowerShell 模組Teams的一部分。</span><span class="sxs-lookup"><span data-stu-id="2091b-172">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="2091b-173">如果您使用的是最新版[PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)Teams版本，則不需要安裝 商務用 Skype 連線連接器。</span><span class="sxs-lookup"><span data-stu-id="2091b-173">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

   ``` Powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

2. <span data-ttu-id="2091b-174">取得帳戶的 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="2091b-174">Obtain SIP address of the account:</span></span>

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. <span data-ttu-id="2091b-175">**選。**</span><span class="sxs-lookup"><span data-stu-id="2091b-175">**Optional.**</span></span> <span data-ttu-id="2091b-176">如果您想要將電話號碼指派給帳戶，此時應執行作業。</span><span class="sxs-lookup"><span data-stu-id="2091b-176">If you want to assign a phone number to the account, the operation should be performed at this point.</span></span> <span data-ttu-id="2091b-177">如果您想要指派直接路由電話號碼：</span><span class="sxs-lookup"><span data-stu-id="2091b-177">If you want to assign a Direct Routing phone number:</span></span>

   ``` Powershell
    Set-CsUser -Identity $rm -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:+14255550012
    ```
    <span data-ttu-id="2091b-178">如果您要指派 Microsoft 提供的電話號碼，請使用下列 Cmdlet，將使用者預配置為通話方案授權：</span><span class="sxs-lookup"><span data-stu-id="2091b-178">If you're assigning a Microsoft provided phone number, use the cmdlet below after having provisioned the user with a Calling Plan license:</span></span>
    
    ``` Powershell
    Set-CsOnlineVoiceUser -Identity $rm -TelephoneNumber +14255550011 -LocationID xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
    ```
    
4. <span data-ttu-id="2091b-179">若要啟用您的Microsoft Teams 會議室帳戶，請執行此命令：</span><span class="sxs-lookup"><span data-stu-id="2091b-179">To enable your Microsoft Teams Rooms account, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="2091b-180">如果您不確定環境中要用於 RegistrarPool 參數的值，您可以使用此命令從現有使用者取得值：</span><span class="sxs-lookup"><span data-stu-id="2091b-180">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing user using this command:</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="2091b-181">指派授權給您的帳戶Microsoft Teams 會議室授權</span><span class="sxs-lookup"><span data-stu-id="2091b-181">Assign a license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="2091b-182">以租使用者系統管理員登入，開啟 Microsoft 365系統管理中心，然後按一下系統管理應用程式。</span><span class="sxs-lookup"><span data-stu-id="2091b-182">Log in as a tenant administrator, open the Microsoft 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="2091b-183">按一下 [ **使用者與群組** ，然後按一下 **[新增使用者、重設密碼等>**。</span><span class="sxs-lookup"><span data-stu-id="2091b-183">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="2091b-184">按一下 Microsoft Teams 會議室帳戶，然後按一下 [筆形圖示以編輯帳戶資訊。</span><span class="sxs-lookup"><span data-stu-id="2091b-184">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="2091b-185">按一下 **[授權>**。</span><span class="sxs-lookup"><span data-stu-id="2091b-185">Click **Licenses**.</span></span>
5. <span data-ttu-id="2091b-186">在 **指派授權** 中，商務用 Skype (方案 2) 或商務用 Skype (方案 3) 視您的授權和企業語音需求。</span><span class="sxs-lookup"><span data-stu-id="2091b-186">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="2091b-187">如果您想要在 企業語音 上使用方案 3 授權Microsoft Teams 會議室。</span><span class="sxs-lookup"><span data-stu-id="2091b-187">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="2091b-188">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="2091b-188">Click **Save**.</span></span>

<span data-ttu-id="2091b-189">若要驗證，您應該可以使用任何用戶端登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="2091b-189">For validation, you should be able to use any client to log in to this account.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="2091b-190">相關主題</span><span class="sxs-lookup"><span data-stu-id="2091b-190">Related topics</span></span>

[<span data-ttu-id="2091b-191">設定帳戶Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="2091b-191">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="2091b-192">規劃 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="2091b-192">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="2091b-193">部署 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="2091b-193">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="2091b-194">設定 Microsoft Teams 會議室主控台</span><span class="sxs-lookup"><span data-stu-id="2091b-194">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="2091b-195">管理 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="2091b-195">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)