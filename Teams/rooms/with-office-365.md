---
title: 使用 Microsoft 365 或 Office 365 部署 Microsoft 團隊聊天室
ms.author: v-cichur
author: cichur
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
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: 如需有關如何使用 Microsoft 365 或 Office 365 （團隊或商務用 Skype 與 Exchange 都在線上）部署 Microsoft 團隊聊天室的資訊，請閱讀本主題。
ms.openlocfilehash: 4b5bd3967d3a1fcc8859cf4da8b039418819cb4e
ms.sourcegitcommit: 07afc959fec802db583e7111280d0035fdb6e412
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616887"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a><span data-ttu-id="49bc9-103">使用 Microsoft 365 或 Office 365 部署 Microsoft 團隊聊天室</span><span class="sxs-lookup"><span data-stu-id="49bc9-103">Deploy Microsoft Teams Rooms with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="49bc9-104">如需瞭解如何使用 Microsoft 365 或 Office 365 （Microsoft 團隊或商務用 Skype 與 Exchange 都在線上）部署 Microsoft 團隊聊天室的相關資訊，請參閱本主題。</span><span class="sxs-lookup"><span data-stu-id="49bc9-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, where Microsoft Teams or Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="49bc9-105">設定使用者帳戶最簡單的方法，就是使用遠端 Windows PowerShell 進行設定。</span><span class="sxs-lookup"><span data-stu-id="49bc9-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="49bc9-106">Microsoft 提供 [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)、可協助您建立新使用者帳戶的腳本，或驗證現有的資源帳戶，以協助您將它們轉換成相容的 Microsoft 團隊聊天室使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="49bc9-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="49bc9-107">如果您想要的話，您可以依照下列步驟來設定您的 Microsoft 團隊聊天室裝置將會使用的帳戶。</span><span class="sxs-lookup"><span data-stu-id="49bc9-107">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="49bc9-108">需求</span><span class="sxs-lookup"><span data-stu-id="49bc9-108">Requirements</span></span>

<span data-ttu-id="49bc9-109">在使用 Microsoft 365 或 Office 365 部署 Microsoft 團隊聊天室之前，請確定您已滿足需求。</span><span class="sxs-lookup"><span data-stu-id="49bc9-109">Before you deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="49bc9-110">如需詳細資訊，請參閱 [Microsoft 團隊會議室需求](requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="49bc9-110">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>

<span data-ttu-id="49bc9-111">若要啟用商務用 Skype，您必須具備下列各項：</span><span class="sxs-lookup"><span data-stu-id="49bc9-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="49bc9-112">商務用 Skype Online (方案2，或您的 Microsoft 365 或 Office 365 方案中的企業級方案) 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="49bc9-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="49bc9-113">方案需要允許電話撥入式會議功能。</span><span class="sxs-lookup"><span data-stu-id="49bc9-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="49bc9-114">如果您需要來自會議的撥入功能，您將需要音訊會議和電話系統授權。</span><span class="sxs-lookup"><span data-stu-id="49bc9-114">If you need dial-in capabilities from a meeting, you will need an Audio Conferencing and Phone System license.</span></span>  <span data-ttu-id="49bc9-115">如果您需要來自會議的撥出功能，您需要音訊會議授權。</span><span class="sxs-lookup"><span data-stu-id="49bc9-115">If you need dial-out capabilities from a meeting, you will need an Audio Conferencing license.</span></span>

- <span data-ttu-id="49bc9-116">您的租使用者必須有 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="49bc9-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="49bc9-117">您的 Microsoft 團隊會議室帳戶至少需要商務用 Skype Online (方案 2) 授權，但不需要 Exchange Online 授權。</span><span class="sxs-lookup"><span data-stu-id="49bc9-117">Your Microsoft Teams Rooms account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="49bc9-118">如需詳細資訊，請參閱 [Microsoft 團隊聊天室授權](rooms-licensing.md) 。</span><span class="sxs-lookup"><span data-stu-id="49bc9-118">See [Microsoft Teams Rooms licenses](rooms-licensing.md) for details.</span></span>

<span data-ttu-id="49bc9-119">如需商務用 Skype Online 方案的詳細資料，請參閱 [商務用 Skype Online 服務說明](https://technet.microsoft.com/library/jj822172.aspx)。</span><span class="sxs-lookup"><span data-stu-id="49bc9-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="49bc9-120">新增裝置帳戶</span><span class="sxs-lookup"><span data-stu-id="49bc9-120">Add a device account</span></span>

1. <span data-ttu-id="49bc9-121">[連線至 Exchange Online PowerShell]。</span><span class="sxs-lookup"><span data-stu-id="49bc9-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="49bc9-122">如需相關指示，請參閱連線 [至 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="49bc9-122">For instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

2. <span data-ttu-id="49bc9-123">在 Exchange Online PowerShell 中，建立新的會議室信箱或修改現有的會議室信箱。</span><span class="sxs-lookup"><span data-stu-id="49bc9-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="49bc9-124">根據預設，會議室信箱沒有相關聯的帳戶，因此，當您建立或修改允許該帳戶透過 Skype 會議室系統 v2 進行驗證的聊天室信箱時，您將需要新增帳戶。</span><span class="sxs-lookup"><span data-stu-id="49bc9-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="49bc9-125">若要建立新的會議室信箱，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="49bc9-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="49bc9-126">這個範例會使用下列設定建立新的會議室信箱：</span><span class="sxs-lookup"><span data-stu-id="49bc9-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="49bc9-127">名稱： Rigel-01</span><span class="sxs-lookup"><span data-stu-id="49bc9-127">Name: Rigel-01</span></span>

     - <span data-ttu-id="49bc9-128">別名： Rigel1</span><span class="sxs-lookup"><span data-stu-id="49bc9-128">Alias: Rigel1</span></span>

     - <span data-ttu-id="49bc9-129">帳戶： Rigel1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="49bc9-129">Account: Rigel1@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="49bc9-130">帳戶密碼： P@ $ $W 0rd5959</span><span class="sxs-lookup"><span data-stu-id="49bc9-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="49bc9-131">若要修改現有的會議室信箱，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="49bc9-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="49bc9-132">這個範例會為擁有別名值 Rigel2 的現有聊天室信箱啟用帳戶，並將密碼設定為 9898P@ $ $W 0rd。</span><span class="sxs-lookup"><span data-stu-id="49bc9-132">This example enables the account for the existing room mailbox that has the alias value Rigel2, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="49bc9-133">請注意，由於現有的別名值，該帳戶將會 Rigel2@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="49bc9-133">Note that the account will be Rigel2@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="49bc9-134">如需詳細的語法與參數資訊，請參閱 [新增-信箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) 和 [設定信箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="49bc9-134">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>

3. <span data-ttu-id="49bc9-135">在 Exchange Online PowerShell 中，設定會議室信箱上的下列設定，以改善會議體驗：</span><span class="sxs-lookup"><span data-stu-id="49bc9-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="49bc9-136">AutomateProcessing： AutoAccept (會議召集人直接在沒有人工干預的情況下收到會議室保留決策：閑 = 接受;忙碌 = 拒絕. ) </span><span class="sxs-lookup"><span data-stu-id="49bc9-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="49bc9-137">AddOrganizerToSubject： $false (會議召集人不會新增至會議邀請的主旨。 ) </span><span class="sxs-lookup"><span data-stu-id="49bc9-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="49bc9-138">DeleteComments： $false (保留傳入會議邀請郵件內文中的任何文字。 ) </span><span class="sxs-lookup"><span data-stu-id="49bc9-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="49bc9-139">DeleteSubject： $false (保持收到的會議邀請主題。 ) </span><span class="sxs-lookup"><span data-stu-id="49bc9-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="49bc9-140">RemovePrivateProperty： $false (可確保在原始會議邀請中由會議召集人所傳送的私人標誌保持為已指定。 ) </span><span class="sxs-lookup"><span data-stu-id="49bc9-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="49bc9-141">AddAdditionalResponse： $true (會將 AdditionalResponse 參數指定的文字新增至會議邀請。 ) </span><span class="sxs-lookup"><span data-stu-id="49bc9-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="49bc9-142">AdditionalResponse：「這是 Skype 會議室！」</span><span class="sxs-lookup"><span data-stu-id="49bc9-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="49bc9-143"> (要新增至會議邀請的其他文字。 ) </span><span class="sxs-lookup"><span data-stu-id="49bc9-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="49bc9-144">這個範例會在房間信箱（名為 Rigel-01）上設定這些設定。</span><span class="sxs-lookup"><span data-stu-id="49bc9-144">This example configures these settings on the room mailbox named Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="49bc9-145">如需詳細的語法與參數資訊，請參閱 [設定 CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)。</span><span class="sxs-lookup"><span data-stu-id="49bc9-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="49bc9-146">使用 PowerShell Cmdlet 連線至 MS Online PowerShell，以進行 Active Directory 設定 `Connect-MsolService -Credential $cred` 。</span><span class="sxs-lookup"><span data-stu-id="49bc9-146">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` PowerShell cmdlet.</span></span> <span data-ttu-id="49bc9-147">如需 Active Directory 的詳細資料，請參閱 [Azure ActiveDirectory (import-module msonline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="49bc9-147">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

   > [!NOTE]
   > <span data-ttu-id="49bc9-148">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) 不受支援。</span><span class="sxs-lookup"><span data-stu-id="49bc9-148">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span>

5. <span data-ttu-id="49bc9-149">如果您不希望密碼到期，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="49bc9-149">If you do not want the password to expire, use the following syntax:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   <span data-ttu-id="49bc9-150">這個範例會將帳戶 Rigel1@contoso.onmicrosoft.com 的密碼設為永不過期。</span><span class="sxs-lookup"><span data-stu-id="49bc9-150">This example sets the password for the account Rigel1@contoso.onmicrosoft.com to never expire.</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -PasswordNeverExpires $true
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -EnforceChangePasswordPolicy $false
   ``` -->

   <span data-ttu-id="49bc9-151">您也可以執行下列命令，以設定帳戶的電話號碼：</span><span class="sxs-lookup"><span data-stu-id="49bc9-151">You can also set a phone number for the account by running the following command:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. <span data-ttu-id="49bc9-152">裝置帳戶必須擁有有效的 Microsoft 365 或 Office 365 授權，或是 Exchange 與 Microsoft 團隊或商務用 Skype 將無法運作。</span><span class="sxs-lookup"><span data-stu-id="49bc9-152">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams or Skype for Business will not work.</span></span> <span data-ttu-id="49bc9-153">如果您有授權，您必須將使用位置指派給您的裝置帳戶，這會決定您的帳戶可使用哪些授權 Sku。</span><span class="sxs-lookup"><span data-stu-id="49bc9-153">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="49bc9-154">您可以使用 `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="49bc9-154">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="49bc9-155">若要為您的 Microsoft 365 或 Office 365 組織取得可用的 Sku 清單，請按照下列步驟操作：</span><span class="sxs-lookup"><span data-stu-id="49bc9-155">to retrieve a list of available SKUs for your Microsoft 365 or Office 365 organization as follows:</span></span>

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   <span data-ttu-id="49bc9-156">接下來，您可以使用 `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="49bc9-156">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!--Set-AzureADUserLicense --> <span data-ttu-id="49bc9-157">Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="49bc9-157">cmdlet.</span></span> <span data-ttu-id="49bc9-158">這個範例會將會議室授權新增至帳戶：</span><span class="sxs-lookup"><span data-stu-id="49bc9-158">This example adds the Meeting Room license to the account:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   <span data-ttu-id="49bc9-159">如需詳細指示，請參閱 [使用 Office 365 PowerShell 指派授權給使用者帳戶](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="49bc9-159">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

   <span data-ttu-id="49bc9-160">您也可以將電話系統功能新增到此帳戶，但必須先進行設定。</span><span class="sxs-lookup"><span data-stu-id="49bc9-160">You can also add Phone System capabilities to this account, but you have to configure it first.</span></span> <span data-ttu-id="49bc9-161">如需詳細資訊，請參閱 [什麼是 [電話系統](../what-is-phone-system-in-office-365.md) ]。</span><span class="sxs-lookup"><span data-stu-id="49bc9-161">See [What is Phone System?](../what-is-phone-system-in-office-365.md) for more details.</span></span> <span data-ttu-id="49bc9-162">這個範例新增 PSTN 國內和國際通話方案：</span><span class="sxs-lookup"><span data-stu-id="49bc9-162">This example adds the PSTN Domestic and International Calling Plan:</span></span>

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "Contoso:MCOPSTN2"
   ```

7. <span data-ttu-id="49bc9-163">接下來，您必須在商務用 Skype 中啟用裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="49bc9-163">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="49bc9-164">請確定您的環境符合 [Microsoft 團隊會議室需求](requirements.md)中定義的需求。</span><span class="sxs-lookup"><span data-stu-id="49bc9-164">Be sure your environment meets the requirements defined in [Microsoft Teams Rooms requirements](requirements.md).</span></span>

   <span data-ttu-id="49bc9-165">啟動遠端 [Windows PowerShell 會話](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) 的方式如下 (務必在) [安裝商務用 Skype Online PowerShell 元件](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) ：</span><span class="sxs-lookup"><span data-stu-id="49bc9-165">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

> [!NOTE]
> <span data-ttu-id="49bc9-166">商務用 Skype Online 連接器目前是最新團隊 PowerShell 模組的一部分。</span><span class="sxs-lookup"><span data-stu-id="49bc9-166">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="49bc9-167">如果您使用的是最新的 [團隊 PowerShell 公開發行](https://www.powershellgallery.com/packages/MicrosoftTeams/)，就不需要安裝商務用 Skype Online 連接器。</span><span class="sxs-lookup"><span data-stu-id="49bc9-167">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

   ``` Powershell
   Import-Module -Name MicrosoftTeams  
   $cssess = New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="49bc9-168">從要設定的新使用者帳戶取得 RegistrarPool 資訊，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="49bc9-168">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

   ``` Powershell
    Get-CsOnlineUser -Identity "Rigel1@contoso.onmicrosoft.com" | Select -Expand RegistrarPool
   ```

   <span data-ttu-id="49bc9-169">接下來，請執行下列 Cmdlet，為商務用 Skype Server 啟用您的 Microsoft 團隊房間帳戶：</span><span class="sxs-lookup"><span data-stu-id="49bc9-169">Next, enable your Microsoft Teams Rooms account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity "Rigel1@contoso.onmicrosoft.com" -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   > [!NOTE]
   > <span data-ttu-id="49bc9-170">可能不會在與租使用者帳戶相同的註冊機構池中建立新的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="49bc9-170">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="49bc9-171">上述命令會防止由於這種情況而導致帳戶設定發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="49bc9-171">The command above will prevent errors in account setup due to this situation.</span></span>

## <a name="validate"></a><span data-ttu-id="49bc9-172">核實</span><span class="sxs-lookup"><span data-stu-id="49bc9-172">Validate</span></span>

<span data-ttu-id="49bc9-173">針對驗證，您應該能夠使用任何商務用 Skype 用戶端登入您所建立的帳戶。</span><span class="sxs-lookup"><span data-stu-id="49bc9-173">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="49bc9-174">另請參閱</span><span class="sxs-lookup"><span data-stu-id="49bc9-174">See also</span></span>

[<span data-ttu-id="49bc9-175">設定 Microsoft 團隊聊天室的帳戶</span><span class="sxs-lookup"><span data-stu-id="49bc9-175">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="49bc9-176">規劃 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="49bc9-176">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="49bc9-177">部署 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="49bc9-177">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)

[<span data-ttu-id="49bc9-178">設定 Microsoft Teams 會議室主控台</span><span class="sxs-lookup"><span data-stu-id="49bc9-178">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="49bc9-179">管理 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="49bc9-179">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)

[<span data-ttu-id="49bc9-180">Microsoft 團隊聊天室授權</span><span class="sxs-lookup"><span data-stu-id="49bc9-180">Microsoft Teams Rooms Licensing</span></span>](rooms-licensing.md)
