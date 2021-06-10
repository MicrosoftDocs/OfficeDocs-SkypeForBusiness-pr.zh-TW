---
title: 使用 powerShell Microsoft Teams共同Microsoft Teams資源帳戶
ms.author: mitressl
author: flinchbot
manager: ericwe
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: 請閱讀本主題，以瞭解如何部署共同Microsoft Teams。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 812fb4704661aa11d3388048fa044030cdb1ce00
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115601"
---
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a><span data-ttu-id="4ff1d-103">使用 PowerShell Microsoft 365資源帳戶</span><span class="sxs-lookup"><span data-stu-id="4ff1d-103">Create a Microsoft 365 resource account using the PowerShell</span></span>

<span data-ttu-id="4ff1d-104">請參閱本主題，以瞭解如何使用 PowerShell 建立共同Microsoft Teams資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-104">Read this topic for information on how to create resource accounts for collaboration bars for Microsoft Teams using PowerShell.</span></span>

<span data-ttu-id="4ff1d-105">建立資源帳戶最簡單的方法是使用 Microsoft 365管理中心。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-105">The easiest way to create a resource account is by using the Microsoft 365 admin center.</span></span> <span data-ttu-id="4ff1d-106">[請參閱這篇文章，瞭解如何執行此工作](resource-account-ui.md)。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-106">[See this article on how to do this](resource-account-ui.md).</span></span>

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a><span data-ttu-id="4ff1d-107">需求</span><span class="sxs-lookup"><span data-stu-id="4ff1d-107">Requirements</span></span>

<span data-ttu-id="4ff1d-108">使用 Microsoft Teams 會議室部署Office 365，請確定您符合需求。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-108">Before you deploy Microsoft Teams Rooms with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="4ff1d-109">詳細資訊，請參閱部署適用于 Microsoft Teams 的[共同Microsoft Teams。](collab-bar-deploy.md)</span><span class="sxs-lookup"><span data-stu-id="4ff1d-109">For more information, see [Deploy collaboration bars for Microsoft Teams](collab-bar-deploy.md).</span></span>

- <span data-ttu-id="4ff1d-110">如果您需要共同合作欄的 PSTN 功能，則需要電話系統授權。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-110">If you need PSTN capabilities for the collaboration bar, you will need Phone System license.</span></span>

- <span data-ttu-id="4ff1d-111">您的資源帳戶必須Exchange信箱。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-111">Your resource accounts must have Exchange mailboxes.</span></span> <span data-ttu-id="4ff1d-112">由於這些是資源帳戶，Exchange授權。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-112">As these are resource accounts, no Exchange license is required.</span></span> <span data-ttu-id="4ff1d-113">我們建議您使用資源帳戶的會議室授權。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-113">We recommend the usage of the Meeting Rooms license for resource accounts.</span></span>


### <a name="add-a-resource-account"></a><span data-ttu-id="4ff1d-114">新增資源帳戶</span><span class="sxs-lookup"><span data-stu-id="4ff1d-114">Add a resource account</span></span>

1. <span data-ttu-id="4ff1d-115">連線 PowerShell Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="4ff1d-116">有關指示，請參閱連線[powerShell Exchange Online。](/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)</span><span class="sxs-lookup"><span data-stu-id="4ff1d-116">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module).</span></span>

2. <span data-ttu-id="4ff1d-117">在 Exchange Online PowerShell 中，建立新會議室信箱或修改現有的會議室信箱。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-117">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span>

   - <span data-ttu-id="4ff1d-118">若要建立新會議室信箱，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="4ff1d-118">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="4ff1d-119">此範例會使用下列設定來建立新會議室信箱：</span><span class="sxs-lookup"><span data-stu-id="4ff1d-119">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="4ff1d-120">名稱：Huddle-Room-01</span><span class="sxs-lookup"><span data-stu-id="4ff1d-120">Name: Huddle-Room-01</span></span>

     - <span data-ttu-id="4ff1d-121">別名：HuddleRoom01</span><span class="sxs-lookup"><span data-stu-id="4ff1d-121">Alias: HuddleRoom01</span></span>

     - <span data-ttu-id="4ff1d-122">帳戶：huddleroom01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="4ff1d-122">Account: huddleroom01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="4ff1d-123">帳戶密碼：P@$$W 0rd242</span><span class="sxs-lookup"><span data-stu-id="4ff1d-123">Account password: P@$$W0rd242</span></span>

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - <span data-ttu-id="4ff1d-124">若要修改現有的會議室信箱，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="4ff1d-124">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="4ff1d-125">此範例啟用具有 HuddleRoom02 別名的現有會議室信箱的帳戶，並且將密碼設定為 808P@$$W 0rd。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-125">This example enables the account for the existing room mailbox that has the alias value HuddleRoom02, and sets the password to 808P@$$W0rd.</span></span> <span data-ttu-id="4ff1d-126">請注意，由於現有的別名值 HuddleRoom02@contoso.onmicrosoft.com 帳戶將會更新。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-126">Note that the account will be HuddleRoom02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="4ff1d-127">有關詳細的語法和參數資訊，請參閱 [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) 和 [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-127">For detailed syntax and parameter information, see [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="4ff1d-128">在 Exchange Online PowerShell 中，設定會議室信箱上的下列設定以改善會議體驗：</span><span class="sxs-lookup"><span data-stu-id="4ff1d-128">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="4ff1d-129">自動化處理：自動 (會議召集人直接收到會議室預約決定，而不需要人為介入：free = accept;busy = decline.) </span><span class="sxs-lookup"><span data-stu-id="4ff1d-129">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="4ff1d-130">AddOrganizerToSubject：$false (會議召集人不會新增到會議要求的主題中。) </span><span class="sxs-lookup"><span data-stu-id="4ff1d-130">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="4ff1d-131">DeleteComments：$false (在傳入會議要求的郵件內文中保留任何文字。) </span><span class="sxs-lookup"><span data-stu-id="4ff1d-131">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="4ff1d-132">DeleteSubject：$false (保留傳入會議要求的主題。) </span><span class="sxs-lookup"><span data-stu-id="4ff1d-132">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="4ff1d-133">RemovePrivateProperty：$false (確保會議召集人在原始會議要求中所送出的私人標標維持為指定的狀態。) </span><span class="sxs-lookup"><span data-stu-id="4ff1d-133">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="4ff1d-134">AddAdditionalResponse：$true (其他Response 參數指定的文字會新加到會議要求中。) </span><span class="sxs-lookup"><span data-stu-id="4ff1d-134">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="4ff1d-135">其他Response：「這個會議室有一個共同Microsoft Teams！</span><span class="sxs-lookup"><span data-stu-id="4ff1d-135">AdditionalResponse: "This room has a collaboration bar for Microsoft Teams!"</span></span> <span data-ttu-id="4ff1d-136"> (新增到會議要求的其他文字。) </span><span class="sxs-lookup"><span data-stu-id="4ff1d-136">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="4ff1d-137">此範例在名為 Huddle-Room-01 的會議室信箱上設定這些設定。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-137">This example configures these settings on the room mailbox named Huddle-Room-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   <span data-ttu-id="4ff1d-138">有關詳細的語法和參數資訊，請參閱 [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing)。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-138">For detailed syntax and parameter information, see [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="4ff1d-139">連線 MS Online PowerShell，以使用 `Connect-MsolService -Credential $cred` Powershell Cmdlet 來設定 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-139">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="4ff1d-140">有關 Active Directory 的詳細資訊，請參閱 [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-140">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="4ff1d-141">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0)不支援。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-141">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

5. <span data-ttu-id="4ff1d-142">使用下列語法 huddleroom01@contoso.onmicrosoft.com 密碼，讓密碼不會過期：</span><span class="sxs-lookup"><span data-stu-id="4ff1d-142">Set the password for huddleroom01@contoso.onmicrosoft.com to not expire using the following syntax:</span></span>

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. <span data-ttu-id="4ff1d-143">資源帳戶需要有有效的授權Office 365，最好是會議室 SKU。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-143">The resource account needs to have a valid Office 365 license, preferably the Meeting Room SKU.</span></span> <span data-ttu-id="4ff1d-144">您也需要為裝置帳戶指派使用位置，這決定您的帳戶可以使用哪些授權 SKUs。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-144">You also need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="4ff1d-145">您可以使用來為租使用者Office 365 `Get-MsolAccountSku` SKUS 清單。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-145">You can use `Get-MsolAccountSku` to retrieve a list of available SKUs for your Office 365 tenant.</span></span>

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    <span data-ttu-id="4ff1d-146">您可以使用 Set-MsolUserLicense 指派授權。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-146">You can assign the license using Set-MsolUserLicense.</span></span> 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   <span data-ttu-id="4ff1d-147">有關詳細指示，請參閱使用 PowerShell 指派授權[Office 365使用者帳戶](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="4ff1d-147">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>




[<span data-ttu-id="4ff1d-148">使用 PowerShell 為共同Microsoft Teams設定帳戶</span><span class="sxs-lookup"><span data-stu-id="4ff1d-148">Configure accounts for collaboration bars for Microsoft Teams using PowerShell</span></span>](resource-account-ps.md)

[<span data-ttu-id="4ff1d-149">部署共同Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4ff1d-149">Deploy collaboration bars for Microsoft Teams</span></span>](collab-bar-deploy.md)

[<span data-ttu-id="4ff1d-150">適用于授權Microsoft Teams共同合作橫條圖</span><span class="sxs-lookup"><span data-stu-id="4ff1d-150">Collaboration bars for Microsoft Teams Licensing</span></span>](../rooms/rooms-licensing.md)