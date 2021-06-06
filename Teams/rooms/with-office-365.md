---
title: 使用 Microsoft Teams 會議室 或 Microsoft 365 部署Office 365
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
description: 請參閱本主題，瞭解如何使用 Microsoft Teams 會議室 或 Microsoft 365 部署Office 365，其中 Teams 或 商務用 Skype 和 Exchange 都位於線上。
ms.openlocfilehash: 64567cd9925a0a11d9e9b896c522a2c4bfe13f40
ms.sourcegitcommit: 3840d72f9ad1c0c7803dc3662a0318f558fe92ab
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739643"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a><span data-ttu-id="40d82-103">使用 Microsoft Teams 會議室 或 Microsoft 365 部署Office 365</span><span class="sxs-lookup"><span data-stu-id="40d82-103">Deploy Microsoft Teams Rooms with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="40d82-104">請閱讀本主題，瞭解如何使用 Microsoft Teams 會議室 或 Microsoft 365 部署Office 365，Microsoft Teams或商務用 Skype Exchange兩者。</span><span class="sxs-lookup"><span data-stu-id="40d82-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, where Microsoft Teams or Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="40d82-105">設定使用者帳戶最簡單的方法是使用遠端Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="40d82-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="40d82-106">Microsoft 提供[SkypeRoomProvisioningScript.ps1，](https://go.microsoft.com/fwlink/?linkid=870105)此腳本可協助建立新的使用者帳戶，或驗證您現有的資源帳戶，以便協助您將這些帳戶轉換為相容的Microsoft Teams 會議室使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="40d82-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="40d82-107">您可以按照下列步驟來設定您的裝置Microsoft Teams 會議室帳戶。</span><span class="sxs-lookup"><span data-stu-id="40d82-107">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="40d82-108">需求</span><span class="sxs-lookup"><span data-stu-id="40d82-108">Requirements</span></span>

<span data-ttu-id="40d82-109">在以 Microsoft Teams 會議室 或 Microsoft 365 部署Office 365，請確定您符合需求。</span><span class="sxs-lookup"><span data-stu-id="40d82-109">Before you deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="40d82-110">詳細資訊，請參閱Microsoft Teams 會議室[需求](requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="40d82-110">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>

<span data-ttu-id="40d82-111">若要啟用商務用 Skype，您必須有下列專案：</span><span class="sxs-lookup"><span data-stu-id="40d82-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="40d82-112">商務用 Skype線上 (方案 2，或Enterprise方案或) 或Microsoft 365或Office 365型計畫。</span><span class="sxs-lookup"><span data-stu-id="40d82-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="40d82-113">方案必須允許電話撥入式會議功能。</span><span class="sxs-lookup"><span data-stu-id="40d82-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="40d82-114">如果您需要會議中的撥入功能，您需要音訊會議電話系統授權。</span><span class="sxs-lookup"><span data-stu-id="40d82-114">If you need dial-in capabilities from a meeting, you will need an Audio Conferencing and Phone System license.</span></span>  <span data-ttu-id="40d82-115">如果您需要會議撥出功能，您需要音訊會議授權。</span><span class="sxs-lookup"><span data-stu-id="40d82-115">If you need dial-out capabilities from a meeting, you will need an Audio Conferencing license.</span></span>

- <span data-ttu-id="40d82-116">您的租使用者使用者必須擁有Exchange信箱。</span><span class="sxs-lookup"><span data-stu-id="40d82-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="40d82-117">您的 Microsoft Teams 會議室帳戶至少需要 商務用 Skype 方案 2 (授權) ，但不需要授權Exchange Online授權。</span><span class="sxs-lookup"><span data-stu-id="40d82-117">Your Microsoft Teams Rooms account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="40d82-118">請參閱[Microsoft Teams 會議室授權](rooms-licensing.md)以瞭解詳細資料。</span><span class="sxs-lookup"><span data-stu-id="40d82-118">See [Microsoft Teams Rooms licenses](rooms-licensing.md) for details.</span></span>

<span data-ttu-id="40d82-119">有關線上方案商務用 Skype詳細資料，請參閱 商務用 Skype[線上服務描述](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)。</span><span class="sxs-lookup"><span data-stu-id="40d82-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="40d82-120">新增裝置帳戶</span><span class="sxs-lookup"><span data-stu-id="40d82-120">Add a device account</span></span>

1. <span data-ttu-id="40d82-121">連線 PowerShell Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="40d82-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="40d82-122">有關指示，請參閱連線[powerShell Exchange Online。](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="40d82-122">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="40d82-123">在 Exchange Online PowerShell 中，建立新會議室信箱或修改現有的會議室信箱。</span><span class="sxs-lookup"><span data-stu-id="40d82-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="40d82-124">根據預設，會議室信箱沒有關聯的帳戶，因此當您建立或修改會議室信箱時，您必須新增帳戶，以便使用 Skype 會議室系統 v2 進行驗證。</span><span class="sxs-lookup"><span data-stu-id="40d82-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="40d82-125">若要建立新會議室信箱，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="40d82-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="40d82-126">此範例會使用下列設定來建立新會議室信箱：</span><span class="sxs-lookup"><span data-stu-id="40d82-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="40d82-127">名稱：Rigel-01</span><span class="sxs-lookup"><span data-stu-id="40d82-127">Name: Rigel-01</span></span>

     - <span data-ttu-id="40d82-128">別名：Rigel1</span><span class="sxs-lookup"><span data-stu-id="40d82-128">Alias: Rigel1</span></span>

     - <span data-ttu-id="40d82-129">帳戶：Rigel1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="40d82-129">Account: Rigel1@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="40d82-130">帳戶密碼：P@$$W 0rd5959</span><span class="sxs-lookup"><span data-stu-id="40d82-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="40d82-131">若要修改現有的會議室信箱，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="40d82-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="40d82-132">此範例啟用具有 Aliasel2 別名的現有會議室信箱的帳戶，並且將密碼設定為 9898P@$$W 0rd。</span><span class="sxs-lookup"><span data-stu-id="40d82-132">This example enables the account for the existing room mailbox that has the alias value Rigel2, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="40d82-133">請注意，由於現有的別名 Rigel2@contoso.onmicrosoft.com 帳戶將會無法使用。</span><span class="sxs-lookup"><span data-stu-id="40d82-133">Note that the account will be Rigel2@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="40d82-134">有關詳細的語法和參數資訊，請參閱 [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) 和 [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="40d82-134">For detailed syntax and parameter information, see [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).</span></span>

3. <span data-ttu-id="40d82-135">在 Exchange Online PowerShell 中，設定會議室信箱上的下列設定以改善會議體驗：</span><span class="sxs-lookup"><span data-stu-id="40d82-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="40d82-136">自動化處理：自動 (會議召集人直接收到會議室預約決定，而不需要人為介入：free = accept;busy = decline.) </span><span class="sxs-lookup"><span data-stu-id="40d82-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="40d82-137">AddOrganizerToSubject：$false (會議召集人不會新增到會議要求的主題中。) </span><span class="sxs-lookup"><span data-stu-id="40d82-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="40d82-138">DeleteComments：$false (在傳入會議要求的郵件內文中保留任何文字。) </span><span class="sxs-lookup"><span data-stu-id="40d82-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="40d82-139">DeleteSubject：$false (保留傳入會議要求的主題。) </span><span class="sxs-lookup"><span data-stu-id="40d82-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="40d82-140">RemovePrivateProperty：$false (確保會議召集人在原始會議要求中所送出的私人標標維持為指定的狀態。) </span><span class="sxs-lookup"><span data-stu-id="40d82-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="40d82-141">AddAdditionalResponse：$true (其他Response 參數指定的文字會新加到會議要求中。) </span><span class="sxs-lookup"><span data-stu-id="40d82-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="40d82-142">其他Response：「這是Skype會議室！</span><span class="sxs-lookup"><span data-stu-id="40d82-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="40d82-143"> (新增到會議要求的其他文字。) </span><span class="sxs-lookup"><span data-stu-id="40d82-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="40d82-144">此範例在名為 Rigel-01 的會議室信箱上設定這些設定。</span><span class="sxs-lookup"><span data-stu-id="40d82-144">This example configures these settings on the room mailbox named Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="40d82-145">有關詳細的語法和參數資訊，請參閱 [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing)。</span><span class="sxs-lookup"><span data-stu-id="40d82-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="40d82-146">連線 MS Online PowerShell，以使用 `Connect-MsolService -Credential $cred` PowerShell Cmdlet 來設定 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="40d82-146">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` PowerShell cmdlet.</span></span> <span data-ttu-id="40d82-147">有關 Active Directory 的詳細資訊，請參閱 [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="40d82-147">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

   > [!NOTE]
   > <span data-ttu-id="40d82-148">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0)不支援。</span><span class="sxs-lookup"><span data-stu-id="40d82-148">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span>

5. <span data-ttu-id="40d82-149">如果您不希望密碼過期，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="40d82-149">If you do not want the password to expire, use the following syntax:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   <span data-ttu-id="40d82-150">此範例會設定帳戶的密碼 Rigel1@contoso.onmicrosoft.com 永不過期。</span><span class="sxs-lookup"><span data-stu-id="40d82-150">This example sets the password for the account Rigel1@contoso.onmicrosoft.com to never expire.</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -PasswordNeverExpires $true
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -EnforceChangePasswordPolicy $false
   ``` -->

   <span data-ttu-id="40d82-151">您也可以執行下列命令來設定帳戶的電話號碼：</span><span class="sxs-lookup"><span data-stu-id="40d82-151">You can also set a phone number for the account by running the following command:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

    > [!NOTE]
    > <span data-ttu-id="40d82-152">如果密碼未設定為永不過期，當帳戶到達到期日時，該帳戶將不再在裝置上登錄。</span><span class="sxs-lookup"><span data-stu-id="40d82-152">If the password is not set to Never Expire, the account will no longer sign in on the device when the account reaches the expiry period.</span></span> <span data-ttu-id="40d82-153">然後，帳戶的密碼必須變更，並且也會在900-900-19999-20100-20100-201199-2013-46-46-46</span><span class="sxs-lookup"><span data-stu-id="40d82-153">The password will then need to be changed for the account and also updated locally on the MTR device.</span></span>

6. <span data-ttu-id="40d82-154">裝置帳戶必須擁有有效的授權Microsoft 365授權Office 365，Exchange Microsoft Teams或商務用 Skype將無效。</span><span class="sxs-lookup"><span data-stu-id="40d82-154">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams or Skype for Business will not work.</span></span> <span data-ttu-id="40d82-155">如果您有授權，您必須將使用位置指派給裝置帳戶，這決定您的帳戶可以使用哪些授權 SKUs。</span><span class="sxs-lookup"><span data-stu-id="40d82-155">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="40d82-156">您可以使用 `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="40d82-156">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="40d82-157">以如下方式為貴組織或Microsoft 365 Office 365可用的 SKUS 清單：</span><span class="sxs-lookup"><span data-stu-id="40d82-157">to retrieve a list of available SKUs for your Microsoft 365 or Office 365 organization as follows:</span></span>

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   <span data-ttu-id="40d82-158">接下來，您可以使用 `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="40d82-158">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!--Set-AzureADUserLicense --> <span data-ttu-id="40d82-159">Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="40d82-159">cmdlet.</span></span> <span data-ttu-id="40d82-160">此範例新增會議室授權至帳戶：</span><span class="sxs-lookup"><span data-stu-id="40d82-160">This example adds the Meeting Room license to the account:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   <span data-ttu-id="40d82-161">有關詳細指示，請參閱使用 PowerShell 指派授權[Office 365使用者帳戶](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="40d82-161">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

   <span data-ttu-id="40d82-162">您也可以新增電話系統功能至此帳戶，但您必須先進行設定。</span><span class="sxs-lookup"><span data-stu-id="40d82-162">You can also add Phone System capabilities to this account, but you have to configure it first.</span></span> <span data-ttu-id="40d82-163">請參閱[什麼是電話系統？](../what-is-phone-system-in-office-365.md)以進一步瞭解詳細資料。</span><span class="sxs-lookup"><span data-stu-id="40d82-163">See [What is Phone System?](../what-is-phone-system-in-office-365.md) for more details.</span></span> <span data-ttu-id="40d82-164">此範例新增 PSTN 國內及國際通話方案：</span><span class="sxs-lookup"><span data-stu-id="40d82-164">This example adds the PSTN Domestic and International Calling Plan:</span></span>

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "Contoso:MCOPSTN2"
   ```

    > [!NOTE]
    > <span data-ttu-id="40d82-165">如果您將會議Teams 會議室只以原生Microsoft Teams加入會議，則不應該繼續進行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="40d82-165">If you are configuring Teams Rooms to only natively join Microsoft Teams meetings, you should not proceed with the following step.</span></span> <span data-ttu-id="40d82-166">只有在您同時啟用內部部署商務用 Skype才能執行下列操作。</span><span class="sxs-lookup"><span data-stu-id="40d82-166">The following is only required if you will also be enabling support for Skype for Business on-premises.</span></span>

7. <span data-ttu-id="40d82-167">若要啟用具有內部部署商務用 Skype裝置帳戶，請確定您的環境符合 Microsoft Teams 會議室[定義的需求](requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="40d82-167">To enable the device account with Skype for Business on-premises, be sure your environment meets the requirements defined in [Microsoft Teams Rooms requirements](requirements.md).</span></span>

   <span data-ttu-id="40d82-168">啟動遠端[Windows PowerShell會話](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)， (請務必在 商務用 Skype [PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)元件) ：</span><span class="sxs-lookup"><span data-stu-id="40d82-168">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

   > [!NOTE]
   > <span data-ttu-id="40d82-169">商務用 Skype線上連接器是目前 PowerShell 模組Teams的一部分。</span><span class="sxs-lookup"><span data-stu-id="40d82-169">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
   >
   > <span data-ttu-id="40d82-170">如果您使用的是最新版[PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)Teams版本，則不需要安裝 商務用 Skype 連線連接器。</span><span class="sxs-lookup"><span data-stu-id="40d82-170">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

   ``` Powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

   <span data-ttu-id="40d82-171">從正在設定的新使用者帳戶取得 RegistrarPool 資訊，如此範例所示：</span><span class="sxs-lookup"><span data-stu-id="40d82-171">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

   ``` Powershell
    Get-CsOnlineUser -Identity "Rigel1@contoso.onmicrosoft.com" | Select -Expand RegistrarPool
   ```

   <span data-ttu-id="40d82-172">接下來，請Microsoft Teams 會議室 Cmdlet 商務用 Skype Server您的帳戶：</span><span class="sxs-lookup"><span data-stu-id="40d82-172">Next, enable your Microsoft Teams Rooms account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity "Rigel1@contoso.onmicrosoft.com" -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   > [!NOTE]
   > <span data-ttu-id="40d82-173">新使用者帳戶可能不會與租使用者中現有的使用者帳戶在同一個註冊機構資料庫上建立。</span><span class="sxs-lookup"><span data-stu-id="40d82-173">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="40d82-174">上述命令會防止帳戶設定中因此情況而發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="40d82-174">The command above will prevent errors in account setup due to this situation.</span></span>

## <a name="validate"></a><span data-ttu-id="40d82-175">驗證</span><span class="sxs-lookup"><span data-stu-id="40d82-175">Validate</span></span>

<span data-ttu-id="40d82-176">若要驗證，您應該可以使用任何商務用 Skype用戶端來登錄您建立的帳戶。</span><span class="sxs-lookup"><span data-stu-id="40d82-176">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="40d82-177">另請參閱</span><span class="sxs-lookup"><span data-stu-id="40d82-177">See also</span></span>

[<span data-ttu-id="40d82-178">設定帳戶Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="40d82-178">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="40d82-179">規劃 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="40d82-179">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="40d82-180">部署 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="40d82-180">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)

[<span data-ttu-id="40d82-181">設定 Microsoft Teams 會議室主控台</span><span class="sxs-lookup"><span data-stu-id="40d82-181">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="40d82-182">管理 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="40d82-182">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)

[<span data-ttu-id="40d82-183">Microsoft Teams 會議室發 牌</span><span class="sxs-lookup"><span data-stu-id="40d82-183">Microsoft Teams Rooms Licensing</span></span>](rooms-licensing.md)
