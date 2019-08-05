---
title: 使用 Exchange 內部部署來部署 Microsoft 團隊聊天室
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection: M365-voice
description: 請閱讀本主題, 以瞭解如何使用 Exchange 內部部署在混合式環境中部署 Microsoft 團隊聊天室的相關資訊。
ms.openlocfilehash: 7e855ece643d3412047b4d01a9250b17f699ac98
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36182319"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a><span data-ttu-id="55adf-103">使用 Exchange 內部部署來部署 Microsoft 團隊聊天室</span><span class="sxs-lookup"><span data-stu-id="55adf-103">Deploy Microsoft Teams Rooms with Exchange on premises</span></span>

<span data-ttu-id="55adf-104">請閱讀本主題, 瞭解如何使用 Exchange 內部部署、Microsoft 團隊或商務用 Skype Online, 在混合式環境中部署 Microsoft 團隊聊天室。</span><span class="sxs-lookup"><span data-stu-id="55adf-104">Read this topic for information on how to deploy Microsoft Teams Rooms in a hybrid environment with Exchange on premises and Microsoft Teams or Skype for Business Online.</span></span>
  
<span data-ttu-id="55adf-105">如果您的組織有混合服務、部分裝載于內部部署和部分託管的網路, 則您的設定將取決於託管每個服務的位置。</span><span class="sxs-lookup"><span data-stu-id="55adf-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="55adf-106">本主題涵蓋 Microsoft 團隊聊天室的混合式部署, Exchange 託管于內部部署。</span><span class="sxs-lookup"><span data-stu-id="55adf-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted on premises.</span></span> <span data-ttu-id="55adf-107">因為這種類型的部署有這麼多不同的變化, 所以不可能提供所有專案的詳細指示。</span><span class="sxs-lookup"><span data-stu-id="55adf-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="55adf-108">下列處理常式適用于許多設定。</span><span class="sxs-lookup"><span data-stu-id="55adf-108">The following process will work for many configurations.</span></span> <span data-ttu-id="55adf-109">如果程式不適合您的設定, 建議您使用 Windows PowerShell 來取得與其他部署選項相同的最終結果。</span><span class="sxs-lookup"><span data-stu-id="55adf-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="55adf-110">Microsoft 提供[SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105), 此腳本將協助您建立新的使用者帳戶, 或驗證您所擁有的現有資源帳戶, 以協助您將它們轉換成相容的 Microsoft 團隊聊天室使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="55adf-110">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="55adf-111">如果您想要的話, 您可以依照下列步驟來設定您的 Microsoft 團隊聊天室裝置將會使用的帳戶。</span><span class="sxs-lookup"><span data-stu-id="55adf-111">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="55adf-112">需求</span><span class="sxs-lookup"><span data-stu-id="55adf-112">Requirements</span></span>

<span data-ttu-id="55adf-113">在使用 Exchange 內部部署部署 Microsoft 團隊聊天室之前, 請確定您已滿足需求。</span><span class="sxs-lookup"><span data-stu-id="55adf-113">Before you deploy Microsoft Teams Rooms with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="55adf-114">如需詳細資訊, 請參閱[Microsoft 團隊會議室需求](requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="55adf-114">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="55adf-115">如果您是使用 Exchange 內部部署來部署 Microsoft 團隊聊天室, 您將會使用 Active Directory 系統管理工具來為您的內部部署網域帳戶新增電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="55adf-115">If you are deploying Microsoft Teams Rooms with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="55adf-116">此帳戶將會同步處理到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="55adf-116">This account will be synced to Office 365.</span></span> <span data-ttu-id="55adf-117">您將需要:</span><span class="sxs-lookup"><span data-stu-id="55adf-117">You will need to:</span></span>
  
- <span data-ttu-id="55adf-118">建立帳戶並將帳戶與 Active Directory 同步處理。</span><span class="sxs-lookup"><span data-stu-id="55adf-118">Create an account and synchronize the account with Active Directory.</span></span>

- <span data-ttu-id="55adf-119">啟用遠端信箱並設定屬性。</span><span class="sxs-lookup"><span data-stu-id="55adf-119">Enable the remote mailbox and set properties.</span></span>

- <span data-ttu-id="55adf-120">指派 Office 365 授權。</span><span class="sxs-lookup"><span data-stu-id="55adf-120">Assign an Office 365 license.</span></span>

- <span data-ttu-id="55adf-121">在商務用 Skype Server 上啟用裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="55adf-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="55adf-122">若要啟用裝置帳戶, 您的環境必須符合下列先決條件:</span><span class="sxs-lookup"><span data-stu-id="55adf-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>

  - <span data-ttu-id="55adf-123">您必須在 Office 365 方案中有商務用 Skype Online (方案 2) 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="55adf-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Office 365 plan.</span></span> <span data-ttu-id="55adf-124">方案需要支援會議功能。</span><span class="sxs-lookup"><span data-stu-id="55adf-124">The plan needs to support conferencing capability.</span></span>
  
  - - <span data-ttu-id="55adf-125">如果您需要企業語音 (PSTN 電話), 請在您需要商務用 Skype Online (方案 3) 中使用電話服務提供者進行 Microsoft 團隊聊天室。</span><span class="sxs-lookup"><span data-stu-id="55adf-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Microsoft Teams Rooms you need Skype for Business Online (Plan 3).</span></span>
  
  - - <span data-ttu-id="55adf-126">您的租使用者必須有 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="55adf-126">Your tenant users must have Exchange mailboxes.</span></span>
  
  - - <span data-ttu-id="55adf-127">您的 Microsoft 團隊會議室帳戶需要商務用 Skype Online (方案 2) 或商務用 Skype Online (方案 3) 授權, 但不需要 Exchange Online 授權。</span><span class="sxs-lookup"><span data-stu-id="55adf-127">Your Microsoft Teams Rooms account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>

- <span data-ttu-id="55adf-128">將商務用 Skype Server 授權指派給您的 Microsoft 團隊聊天室帳戶。</span><span class="sxs-lookup"><span data-stu-id="55adf-128">Assign a Skype for Business Server license to your Microsoft Teams Rooms account.</span></span>

### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="55adf-129">建立帳戶並與 Active Directory 同步處理</span><span class="sxs-lookup"><span data-stu-id="55adf-129">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="55adf-130">在 [ **Active Directory 使用者和電腦**] 工具中, 以滑鼠右鍵按一下您要在其中建立 Microsoft 團隊房間帳戶的資料夾或組織單位, 按一下 [**新增**], 然後按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="55adf-130">In the **Active Directory Users and Computers** tool, right-click on the folder or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>

2. <span data-ttu-id="55adf-131">在 [**完整名稱**] 方塊中輸入上一個 Cmdlet 的顯示名稱, 然後在 [**使用者登入名稱**] 方塊中輸入別名。</span><span class="sxs-lookup"><span data-stu-id="55adf-131">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="55adf-132">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="55adf-132">Click **Next**.</span></span>

3. <span data-ttu-id="55adf-133">輸入此帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="55adf-133">Type the password for this account.</span></span> <span data-ttu-id="55adf-134">您必須重新輸入, 才能進行驗證。</span><span class="sxs-lookup"><span data-stu-id="55adf-134">You'll need to retype it for verification.</span></span> <span data-ttu-id="55adf-135">確認 [**密碼永不過期**] 核取方塊是唯一選取的選項。</span><span class="sxs-lookup"><span data-stu-id="55adf-135">Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="55adf-136">選取 [**密碼永不過期**] 是 Microsoft 團隊聊天室的商務用 Skype 伺服器需求。</span><span class="sxs-lookup"><span data-stu-id="55adf-136">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="55adf-137">您的網域規則可能會禁止沒有過期的密碼。</span><span class="sxs-lookup"><span data-stu-id="55adf-137">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="55adf-138">如果是這樣, 您將需要針對每個 Microsoft 團隊聊天室裝置帳戶建立例外狀況。</span><span class="sxs-lookup"><span data-stu-id="55adf-138">If so, you'll need to create an exception for each Microsoft Teams Rooms device account.</span></span>
  
4. <span data-ttu-id="55adf-139">建立帳戶之後, 請執行目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="55adf-139">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="55adf-140">完成後, 請移至 Microsoft 365 系統管理中心的 [使用者] 頁面, 確認在先前步驟中建立的帳戶已合併至 [線上]。</span><span class="sxs-lookup"><span data-stu-id="55adf-140">When it's complete, go to the users page in your Microsoft 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="55adf-141">啟用遠端信箱並設定屬性</span><span class="sxs-lookup"><span data-stu-id="55adf-141">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="55adf-142">[開啟 Exchange 管理命令](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell)介面或[使用遠端 PowerShell 連線至您的 Exchange 伺服器](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)。</span><span class="sxs-lookup"><span data-stu-id="55adf-142">[Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) or [connect to your Exchange server using remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="55adf-143">在 Exchange PowerShell 中, 執行下列命令, 為帳戶 (信箱啟用帳戶) 包裝箱提供信箱:</span><span class="sxs-lookup"><span data-stu-id="55adf-143">In Exchange PowerShell, crate a mailbox for the account (mailbox-enable the account)by running the following command:</span></span>

   ``` Powershell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   <span data-ttu-id="55adf-144">如需詳細的語法與參數資訊, 請參閱[啟用-信箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="55adf-144">For detailed syntax and parameter information, see [Enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).</span></span>

3. <span data-ttu-id="55adf-145">在 Exchange PowerShell 中, 設定會議室信箱上的下列設定, 以改善會議體驗:</span><span class="sxs-lookup"><span data-stu-id="55adf-145">In Exchange PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="55adf-146">AutomateProcessing: AutoAccept (會議召集人直接在沒有人工干預的情況下收到會議室保留決策: 免費 = accept; 忙碌 = 拒絕。)</span><span class="sxs-lookup"><span data-stu-id="55adf-146">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="55adf-147">AddOrganizerToSubject: $false (會議召集人不會新增至會議邀請的主旨。)</span><span class="sxs-lookup"><span data-stu-id="55adf-147">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="55adf-148">DeleteComments: $false (在傳入會議邀請的郵件內文中保留任何文字。)</span><span class="sxs-lookup"><span data-stu-id="55adf-148">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="55adf-149">DeleteSubject: $false (請不要傳送會議邀請的主題)。</span><span class="sxs-lookup"><span data-stu-id="55adf-149">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="55adf-150">RemovePrivateProperty: $false (保證會議召集人在原始會議邀請中傳送的私人旗標保持在指定的時間。)</span><span class="sxs-lookup"><span data-stu-id="55adf-150">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="55adf-151">AddAdditionalResponse: $true (由 AdditionalResponse 參數指定的文字會新增至會議邀請。)</span><span class="sxs-lookup"><span data-stu-id="55adf-151">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="55adf-152">AdditionalResponse: 「這是 Skype 會議室!」</span><span class="sxs-lookup"><span data-stu-id="55adf-152">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="55adf-153">(要新增至會議邀請的其他文字)。</span><span class="sxs-lookup"><span data-stu-id="55adf-153">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="55adf-154">這個範例會在名為 Project-Rigel-01 的聊天室信箱上設定這些設定。</span><span class="sxs-lookup"><span data-stu-id="55adf-154">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="55adf-155">如需詳細的語法與參數資訊, 請參閱[設定 CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)。</span><span class="sxs-lookup"><span data-stu-id="55adf-155">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

### <a name="assign-an-office-365-license"></a><span data-ttu-id="55adf-156">指派 Office 365 授權</span><span class="sxs-lookup"><span data-stu-id="55adf-156">Assign an Office 365 license</span></span>

1. <span data-ttu-id="55adf-157">連線至 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="55adf-157">Connect to Azure Active Directory.</span></span> <span data-ttu-id="55adf-158">如需 Active Directory 的詳細資訊, 請參閱[Azure ActiveDirectory (import-module msonline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="55adf-158">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="55adf-159">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0)不受支援。</span><span class="sxs-lookup"><span data-stu-id="55adf-159">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

2. <span data-ttu-id="55adf-160">裝置帳戶必須具備有效的 Office 365 授權, 否則 Exchange 與 Microsoft 團隊將無法運作。</span><span class="sxs-lookup"><span data-stu-id="55adf-160">The device account needs to have a valid Office 365 license, or Exchange and Microsoft Teams will not work.</span></span> <span data-ttu-id="55adf-161">如果您有授權, 您必須將使用位置指派給您的裝置帳戶, 這會決定您的帳戶可使用哪些授權 Sku。</span><span class="sxs-lookup"><span data-stu-id="55adf-161">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="55adf-162">您可以使用`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="55adf-162">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="55adf-163">以取得可用的 Sku 清單。</span><span class="sxs-lookup"><span data-stu-id="55adf-163">to retrieve a list of available SKUs.</span></span>

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. <span data-ttu-id="55adf-164">接下來, 您可以使用`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="55adf-164">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense --> <span data-ttu-id="55adf-165">Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="55adf-165">cmdlet.</span></span> <span data-ttu-id="55adf-166">在此情況下, $strLicense 是您所看到的 SKU 程式碼 (例如 contoso: STANDARDPACK)。</span><span class="sxs-lookup"><span data-stu-id="55adf-166">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

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

   <span data-ttu-id="55adf-167">如需詳細指示, 請參閱[使用 Office 365 PowerShell 指派授權給使用者帳戶](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="55adf-167">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="enable-the-device-account"></a><span data-ttu-id="55adf-168">啟用裝置帳戶</span><span class="sxs-lookup"><span data-stu-id="55adf-168">Enable the device account</span></span>

<span data-ttu-id="55adf-169">商務用 skype Online PowerShell 是用來管理 Microsoft 團隊和商務用 Skype Online 的服務。</span><span class="sxs-lookup"><span data-stu-id="55adf-169">Skype for Business Online PowerShell is used to manage services for both Microsoft Teams and Skype for Business Online.</span></span>

1. <span data-ttu-id="55adf-170">從電腦建立遠端 Windows PowerShell 會話, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="55adf-170">Create a remote Windows PowerShell session from a PC as follows:</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="55adf-171">若要啟用您的 Microsoft 團隊聊天室帳戶, 請執行此命令:</span><span class="sxs-lookup"><span data-stu-id="55adf-171">To enable your Microsoft Teams Rooms account, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="55adf-172">如果您不確定要在您的環境中使用 RegistrarPool 參數的值, 您可以使用此命令從現有的使用者取得值:</span><span class="sxs-lookup"><span data-stu-id="55adf-172">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing user using this command:</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="55adf-173">將授權指派給您的 Microsoft 團隊聊天室帳戶</span><span class="sxs-lookup"><span data-stu-id="55adf-173">Assign a license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="55adf-174">以租使用者管理員身分登入, 開啟 Office 365 系統管理中心入口網站, 然後按一下 [管理] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="55adf-174">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
2. <span data-ttu-id="55adf-175">按一下 [**使用者和群組**], 然後按一下 [**新增使用者、重設密碼等等**]。</span><span class="sxs-lookup"><span data-stu-id="55adf-175">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="55adf-176">按一下 [Microsoft 團隊聊天室] 帳戶, 然後按一下手寫筆圖示, 即可編輯帳戶資訊。</span><span class="sxs-lookup"><span data-stu-id="55adf-176">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="55adf-177">按一下 [**授權**]。</span><span class="sxs-lookup"><span data-stu-id="55adf-177">Click **Licenses**.</span></span>
5. <span data-ttu-id="55adf-178">在 [**指派授權**] 中, 選取 [商務用 Skype (方案 2)] 或 [商務用 Skype (方案 3)], 視您的授權和企業語音需求而定。</span><span class="sxs-lookup"><span data-stu-id="55adf-178">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="55adf-179">如果您想要在 Microsoft 團隊聊天室使用企業語音, 您必須使用 [方案3授權]。</span><span class="sxs-lookup"><span data-stu-id="55adf-179">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="55adf-180">按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="55adf-180">Click **Save**.</span></span>

<span data-ttu-id="55adf-181">針對驗證, 您應該可以使用任何用戶端登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="55adf-181">For validation, you should be able to use any client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="55adf-182">另請參閱</span><span class="sxs-lookup"><span data-stu-id="55adf-182">See also</span></span>

[<span data-ttu-id="55adf-183">設定 Microsoft 團隊聊天室的帳戶</span><span class="sxs-lookup"><span data-stu-id="55adf-183">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="55adf-184">規劃 Microsoft 團隊聊天室</span><span class="sxs-lookup"><span data-stu-id="55adf-184">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)
  
[<span data-ttu-id="55adf-185">部署 Microsoft 團隊聊天室</span><span class="sxs-lookup"><span data-stu-id="55adf-185">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="55adf-186">設定 Microsoft 團隊聊天室主控台</span><span class="sxs-lookup"><span data-stu-id="55adf-186">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="55adf-187">管理 Microsoft 團隊聊天室</span><span class="sxs-lookup"><span data-stu-id="55adf-187">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
