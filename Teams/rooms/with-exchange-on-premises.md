---
title: 使用 Exchange 內部部署部署 Microsoft Teams 會議室
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
description: 請閱讀本主題，以瞭解如何在混合式環境中與 Exchange 內部部署部署 Microsoft Teams 會議室。
ms.openlocfilehash: fcf7216a4fcadee1e81ef11b5310b9d0a88e378a
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460513"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a><span data-ttu-id="cf08c-103">在內部部署 Exchange 部署 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="cf08c-103">Deploy Microsoft Teams Rooms with Exchange on premises</span></span>

<span data-ttu-id="cf08c-104">請閱讀本主題，以瞭解如何在混合式環境中部署 Microsoft Teams 會議室與 Exchange 內部部署和 Microsoft Teams 或商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="cf08c-104">Read this topic for information on how to deploy Microsoft Teams Rooms in a hybrid environment with Exchange on premises and Microsoft Teams or Skype for Business Online.</span></span>
  
<span data-ttu-id="cf08c-105">如果貴組織混合使用各種服務，其中一些是內部部署，另一部分則由線上託管，則您的組配置取決於每個服務的託管位置。</span><span class="sxs-lookup"><span data-stu-id="cf08c-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="cf08c-106">本主題涵蓋內部部署的 Microsoft Teams 會議室與 Exchange 的混合式部署。</span><span class="sxs-lookup"><span data-stu-id="cf08c-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted on premises.</span></span> <span data-ttu-id="cf08c-107">由於這種類型的部署有許多不同的變化，因此無法針對所有部署提供詳細指示。</span><span class="sxs-lookup"><span data-stu-id="cf08c-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="cf08c-108">下列程式適用于許多組配置。</span><span class="sxs-lookup"><span data-stu-id="cf08c-108">The following process will work for many configurations.</span></span> <span data-ttu-id="cf08c-109">如果此程式適用于您的設定，建議您使用 Windows PowerShell 來達到與本文所述相同的最終結果，以及其他部署選項。</span><span class="sxs-lookup"><span data-stu-id="cf08c-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="cf08c-110">Microsoft 提供 [SkypeRoomProvisioningScript.ps1， ](https://go.microsoft.com/fwlink/?linkid=870105)此腳本可協助建立新使用者帳戶，或驗證您現有的資源帳戶，以便將它們轉換為相容的 Microsoft Teams 會議室使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="cf08c-110">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="cf08c-111">您可以視需要遵循下列步驟來設定 Microsoft Teams 會議室裝置將會使用的帳戶。</span><span class="sxs-lookup"><span data-stu-id="cf08c-111">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="cf08c-112">需求</span><span class="sxs-lookup"><span data-stu-id="cf08c-112">Requirements</span></span>

<span data-ttu-id="cf08c-113">在部署內部部署 Exchange 的 Microsoft Teams 會議室之前，請確定您符合需求。</span><span class="sxs-lookup"><span data-stu-id="cf08c-113">Before you deploy Microsoft Teams Rooms with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="cf08c-114">詳細資訊請參閱 Microsoft [Teams 會議室需求](requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cf08c-114">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="cf08c-115">如果您要在內部部署具有 Exchange 的 Microsoft Teams 會議室，您將使用 Active Directory 管理工具為您的內部部署網域帳戶新增電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="cf08c-115">If you are deploying Microsoft Teams Rooms with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="cf08c-116">這個帳戶將會同步到 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="cf08c-116">This account will be synced to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="cf08c-117">您必須：</span><span class="sxs-lookup"><span data-stu-id="cf08c-117">You will need to:</span></span>
  
- <span data-ttu-id="cf08c-118">建立帳戶，並同步處理帳戶與 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="cf08c-118">Create an account and synchronize the account with Active Directory.</span></span>

- <span data-ttu-id="cf08c-119">啟用遠端信箱並設定屬性。</span><span class="sxs-lookup"><span data-stu-id="cf08c-119">Enable the remote mailbox and set properties.</span></span>

- <span data-ttu-id="cf08c-120">指派 Microsoft 365 或 Office 365 授權。</span><span class="sxs-lookup"><span data-stu-id="cf08c-120">Assign an Microsoft 365 or Office 365 license.</span></span>

- <span data-ttu-id="cf08c-121">使用商務用 Skype Server 啟用裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="cf08c-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="cf08c-122">若要啟用裝置帳戶，您的環境必須符合下列先決條件：</span><span class="sxs-lookup"><span data-stu-id="cf08c-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>

  - <span data-ttu-id="cf08c-123">您的 Microsoft 365 或 Office 365 方案 (商務用 Skype Online) 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="cf08c-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="cf08c-124">此方案需要支援會議功能。</span><span class="sxs-lookup"><span data-stu-id="cf08c-124">The plan needs to support conferencing capability.</span></span>
  
  - <span data-ttu-id="cf08c-125">如果您需要企業語音 (PSTN 電話) 使用 Microsoft Teams 會議室的電話服務提供者，您需要商務用 Skype Online (方案 3) 。</span><span class="sxs-lookup"><span data-stu-id="cf08c-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Microsoft Teams Rooms you need Skype for Business Online (Plan 3).</span></span>
  
  - <span data-ttu-id="cf08c-126">您的租使用者使用者必須擁有 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="cf08c-126">Your tenant users must have Exchange mailboxes.</span></span>
  
  - <span data-ttu-id="cf08c-127">您的 Microsoft Teams 會議室帳戶確實需要商務用 Skype Online (方案 2) 或商務用 Skype Online (方案 3) 授權，但不需要 Exchange Online 授權。</span><span class="sxs-lookup"><span data-stu-id="cf08c-127">Your Microsoft Teams Rooms account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>

- <span data-ttu-id="cf08c-128">指派商務用 Skype Server 授權給 Microsoft Teams 會議室帳戶。</span><span class="sxs-lookup"><span data-stu-id="cf08c-128">Assign a Skype for Business Server license to your Microsoft Teams Rooms account.</span></span>

### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="cf08c-129">建立帳戶並同步處理 Active Directory</span><span class="sxs-lookup"><span data-stu-id="cf08c-129">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="cf08c-130">在 **Active Directory** 使用者與電腦工具中，以滑鼠右鍵按一下要建立 Microsoft Teams 會議室帳戶的資料夾或組織單位，按一下 [ **新增**，然後按一下 **[使用者**。</span><span class="sxs-lookup"><span data-stu-id="cf08c-130">In the **Active Directory Users and Computers** tool, right-click on the folder or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>

2. <span data-ttu-id="cf08c-131">在全名方塊中輸入上一個 Cmdlet 的顯示名稱，將別名輸入到 **使用者登入名稱** 方塊。 </span><span class="sxs-lookup"><span data-stu-id="cf08c-131">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="cf08c-132">按一下 [ **下一步**。</span><span class="sxs-lookup"><span data-stu-id="cf08c-132">Click **Next**.</span></span>

3. <span data-ttu-id="cf08c-133">輸入此帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="cf08c-133">Type the password for this account.</span></span> <span data-ttu-id="cf08c-134">您必須重新輸入以進行驗證。</span><span class="sxs-lookup"><span data-stu-id="cf08c-134">You'll need to retype it for verification.</span></span> <span data-ttu-id="cf08c-135">請確定選取 **的唯一選項是** 密碼永不過期核取方塊。</span><span class="sxs-lookup"><span data-stu-id="cf08c-135">Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cf08c-136">選取 **密碼永不過期** 是 Microsoft Teams 會議室商務用 Skype Server 的一項要求。</span><span class="sxs-lookup"><span data-stu-id="cf08c-136">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="cf08c-137">您的網域規則可能會禁止密碼過期。</span><span class="sxs-lookup"><span data-stu-id="cf08c-137">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="cf08c-138">若是如此，您必須為每個 Microsoft Teams 會議室裝置帳戶建立例外。</span><span class="sxs-lookup"><span data-stu-id="cf08c-138">If so, you'll need to create an exception for each Microsoft Teams Rooms device account.</span></span>
  
4. <span data-ttu-id="cf08c-139">建立帳戶之後，請執行目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="cf08c-139">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="cf08c-140">完成後，請前往 Microsoft 365 系統管理中心的使用者頁面，並確認先前步驟建立的帳戶已合併至線上。</span><span class="sxs-lookup"><span data-stu-id="cf08c-140">When it's complete, go to the users page in your Microsoft 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="cf08c-141">啟用遠端信箱和設定屬性</span><span class="sxs-lookup"><span data-stu-id="cf08c-141">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="cf08c-142">[開啟 Exchange 管理命令區](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell)[，或使用遠端 PowerShell 連接到 Exchange 伺服器](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)。</span><span class="sxs-lookup"><span data-stu-id="cf08c-142">[Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) or [connect to your Exchange server using remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="cf08c-143">在 Exchange PowerShell 中，為帳戶建立 (信箱，以執行下列) 啟用帳戶：</span><span class="sxs-lookup"><span data-stu-id="cf08c-143">In Exchange PowerShell, create a mailbox for the account (mailbox-enable the account) by running the following command:</span></span>

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   <span data-ttu-id="cf08c-144">有關詳細的語法和參數資訊，請參閱[Enable-Mailbox。](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox)</span><span class="sxs-lookup"><span data-stu-id="cf08c-144">For detailed syntax and parameter information, see [Enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).</span></span>

3. <span data-ttu-id="cf08c-145">在 Exchange PowerShell 中，在會議室信箱上設定下列設定以改善會議體驗：</span><span class="sxs-lookup"><span data-stu-id="cf08c-145">In Exchange PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="cf08c-146">自動化處理：自動接受 (會議召集人直接收到會議室預約決定，無需人工介入：free = accept;busy = decline.) </span><span class="sxs-lookup"><span data-stu-id="cf08c-146">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="cf08c-147">AddOrganizerToSubject：$false (會議召集人不會新增到會議要求的主題中。) </span><span class="sxs-lookup"><span data-stu-id="cf08c-147">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="cf08c-148">DeleteComments：$false (會議要求的郵件內文保留任何文字。) </span><span class="sxs-lookup"><span data-stu-id="cf08c-148">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="cf08c-149">DeleteSubject：$false (保留傳入會議要求的主題。) </span><span class="sxs-lookup"><span data-stu-id="cf08c-149">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="cf08c-150">RemovePrivateProperty：$false (確保會議召集人在原始會議要求中所送出的私人標號維持為指定狀態。) </span><span class="sxs-lookup"><span data-stu-id="cf08c-150">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="cf08c-151">AddAdditionalResponse：$true (AdditionalResponse 參數指定的文字會新增到會議要求中。) </span><span class="sxs-lookup"><span data-stu-id="cf08c-151">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="cf08c-152">其他Response：「這是 Skype 會議室！</span><span class="sxs-lookup"><span data-stu-id="cf08c-152">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="cf08c-153"> (新增到會議要求的其他文字。) </span><span class="sxs-lookup"><span data-stu-id="cf08c-153">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="cf08c-154">此範例在名為 Project-Rigel-01 的會議室信箱上設定這些設定。</span><span class="sxs-lookup"><span data-stu-id="cf08c-154">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="cf08c-155">有關詳細的語法和參數資訊，請參閱[Set-CalendarProcessing。](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)</span><span class="sxs-lookup"><span data-stu-id="cf08c-155">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

### <a name="assign-a-microsoft-365-or-office-365-license"></a><span data-ttu-id="cf08c-156">指派 Microsoft 365 或 Office 365 授權</span><span class="sxs-lookup"><span data-stu-id="cf08c-156">Assign a Microsoft 365 or Office 365 license</span></span>

1. <span data-ttu-id="cf08c-157">連接到 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="cf08c-157">Connect to Azure Active Directory.</span></span> <span data-ttu-id="cf08c-158">有關 Active Directory 的詳細資訊，請參閱[Azure ActiveDirectory (MSOnline) 1.0。](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="cf08c-158">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="cf08c-159">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) 不受支援。</span><span class="sxs-lookup"><span data-stu-id="cf08c-159">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

2. <span data-ttu-id="cf08c-160">裝置帳戶必須擁有有效的 Microsoft 365 或 Office 365 授權，否則 Exchange 和 Microsoft Teams 無法工作。</span><span class="sxs-lookup"><span data-stu-id="cf08c-160">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams will not work.</span></span> <span data-ttu-id="cf08c-161">如果您有授權，您必須將使用位置指派給裝置帳戶，這決定您的帳戶可以使用哪些授權 SKUS。</span><span class="sxs-lookup"><span data-stu-id="cf08c-161">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="cf08c-162">您可以使用 `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="cf08c-162">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="cf08c-163">以取回可用的 SKUS 清單。</span><span class="sxs-lookup"><span data-stu-id="cf08c-163">to retrieve a list of available SKUs.</span></span>

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. <span data-ttu-id="cf08c-164">接下來，您可以使用 `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="cf08c-164">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense --> <span data-ttu-id="cf08c-165">Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cf08c-165">cmdlet.</span></span> <span data-ttu-id="cf08c-166">在此案例中，$strLicense是您看到的 SKU (例如 contoso：STANDARDPACK) 。</span><span class="sxs-lookup"><span data-stu-id="cf08c-166">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

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

   <span data-ttu-id="cf08c-167">有關詳細指示，請參閱使用 [Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)指派授權給使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="cf08c-167">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="enable-the-device-account"></a><span data-ttu-id="cf08c-168">啟用裝置帳戶</span><span class="sxs-lookup"><span data-stu-id="cf08c-168">Enable the device account</span></span>

<span data-ttu-id="cf08c-169">商務用 Skype Online PowerShell 可用來管理 Microsoft Teams 和商務用 Skype Online 的服務。</span><span class="sxs-lookup"><span data-stu-id="cf08c-169">Skype for Business Online PowerShell is used to manage services for both Microsoft Teams and Skype for Business Online.</span></span>

1. <span data-ttu-id="cf08c-170">從電腦建立遠端 Windows PowerShell 會話，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cf08c-170">Create a remote Windows PowerShell session from a PC as follows:</span></span>
> [!NOTE]
> <span data-ttu-id="cf08c-171">商務用 Skype Online Connector 目前是最新 Teams PowerShell 模組的一部分。</span><span class="sxs-lookup"><span data-stu-id="cf08c-171">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="cf08c-172">如果您使用的是最新的 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)公開發行，則不需要安裝商務用 Skype Online Connector。</span><span class="sxs-lookup"><span data-stu-id="cf08c-172">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

   ``` Powershell
   Import-Module -Name MicrosoftTeams  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="cf08c-173">取得帳戶的 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="cf08c-173">Obtain SIP address of the account:</span></span>

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. <span data-ttu-id="cf08c-174">若要啟用您的 Microsoft Teams 會議室帳戶，請執行此命令：</span><span class="sxs-lookup"><span data-stu-id="cf08c-174">To enable your Microsoft Teams Rooms account, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="cf08c-175">如果您不確定要用於您環境中 RegistrarPool 參數的值，可以使用此命令從現有使用者取得值：</span><span class="sxs-lookup"><span data-stu-id="cf08c-175">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing user using this command:</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="cf08c-176">指派授權給 Microsoft Teams 會議室帳戶</span><span class="sxs-lookup"><span data-stu-id="cf08c-176">Assign a license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="cf08c-177">以租使用者系統管理員的名登入、開啟 Microsoft 365 系統管理中心，然後按一下系統管理應用程式。</span><span class="sxs-lookup"><span data-stu-id="cf08c-177">Log in as a tenant administrator, open the Microsoft 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="cf08c-178">按一下使用者 **和群組，** 然後按一下 **[新增使用者、重設密碼等等**。</span><span class="sxs-lookup"><span data-stu-id="cf08c-178">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="cf08c-179">按一下 Microsoft Teams 會議室帳戶，然後按一下筆圖示以編輯帳戶資訊。</span><span class="sxs-lookup"><span data-stu-id="cf08c-179">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="cf08c-180">按一下 **[授權**。</span><span class="sxs-lookup"><span data-stu-id="cf08c-180">Click **Licenses**.</span></span>
5. <span data-ttu-id="cf08c-181">在 **指派授權** 中，根據您的授權和企業語音 (，選取商務用 Skype (方案 2) 或商務用 Skype (方案 3) 。</span><span class="sxs-lookup"><span data-stu-id="cf08c-181">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="cf08c-182">如果您想要在 Microsoft Teams 會議室使用企業語音，您必須使用方案 3 授權。</span><span class="sxs-lookup"><span data-stu-id="cf08c-182">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="cf08c-183">按一下 [儲存 **]**。</span><span class="sxs-lookup"><span data-stu-id="cf08c-183">Click **Save**.</span></span>

<span data-ttu-id="cf08c-184">若要驗證，您應該可以使用任何用戶端登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="cf08c-184">For validation, you should be able to use any client to log in to this account.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="cf08c-185">相關主題</span><span class="sxs-lookup"><span data-stu-id="cf08c-185">Related topics</span></span>

[<span data-ttu-id="cf08c-186">設定 Microsoft Teams 會議室的帳戶</span><span class="sxs-lookup"><span data-stu-id="cf08c-186">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="cf08c-187">規劃 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="cf08c-187">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="cf08c-188">部署 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="cf08c-188">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="cf08c-189">設定 Microsoft Teams 會議室主控台</span><span class="sxs-lookup"><span data-stu-id="cf08c-189">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="cf08c-190">管理 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="cf08c-190">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
