---
title: 使用 PowerShell 為 Microsoft 團隊建立共同作業橫條圖的 Microsoft 團隊資源帳戶
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
description: 如需如何為 Microsoft 團隊部署共同作業橫條圖的相關資訊，請參閱本主題。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 0cb8043e0530c986b9ddcaa9a1022254939adfd2
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268029"
---
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a><span data-ttu-id="83d36-103">使用 PowerShell 建立 Microsoft 365 資源帳戶</span><span class="sxs-lookup"><span data-stu-id="83d36-103">Create a Microsoft 365 resource account using the PowerShell</span></span>

<span data-ttu-id="83d36-104">若要瞭解如何使用 PowerShell 為 Microsoft 團隊建立共同作業列的資源帳戶，請閱讀本主題。</span><span class="sxs-lookup"><span data-stu-id="83d36-104">Read this topic for information on how to create resource accounts for collaboration bars for Microsoft Teams using PowerShell.</span></span>

<span data-ttu-id="83d36-105">建立資源帳戶最簡單的方法是使用 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="83d36-105">The easiest way to create a resource account is by using the Microsoft 365 admin center.</span></span> <span data-ttu-id="83d36-106">[請參閱這篇文章以瞭解如何執行此](resource-account-ui.md)動作。</span><span class="sxs-lookup"><span data-stu-id="83d36-106">[See this article on how to do this](resource-account-ui.md).</span></span>

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a><span data-ttu-id="83d36-107">需求</span><span class="sxs-lookup"><span data-stu-id="83d36-107">Requirements</span></span>

<span data-ttu-id="83d36-108">在使用 Office 365 部署 Microsoft 團隊聊天室之前，請確定您已滿足需求。</span><span class="sxs-lookup"><span data-stu-id="83d36-108">Before you deploy Microsoft Teams Rooms with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="83d36-109">如需詳細資訊，請參閱為[Microsoft 團隊部署](collab-bar-deploy.md)共同作業條。</span><span class="sxs-lookup"><span data-stu-id="83d36-109">For more information, see [Deploy collaboration bars for Microsoft Teams](collab-bar-deploy.md).</span></span>

- <span data-ttu-id="83d36-110">如果您需要 [共同作業] 列的 PSTN 功能，您將需要 [電話系統授權]。</span><span class="sxs-lookup"><span data-stu-id="83d36-110">If you need PSTN capabilities for the collaboration bar, you will need Phone System license.</span></span>

- <span data-ttu-id="83d36-111">您的資源帳戶必須有 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="83d36-111">Your resource accounts must have Exchange mailboxes.</span></span> <span data-ttu-id="83d36-112">因為這些是資源帳戶，因此不需要 Exchange 授權。</span><span class="sxs-lookup"><span data-stu-id="83d36-112">As these are resource accounts, no Exchange license is required.</span></span> <span data-ttu-id="83d36-113">我們建議使用 [會議室] 授權來取得資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="83d36-113">We recommend the usage of the Meeting Rooms license for resource accounts.</span></span>


### <a name="add-a-resource-account"></a><span data-ttu-id="83d36-114">新增資源帳戶</span><span class="sxs-lookup"><span data-stu-id="83d36-114">Add a resource account</span></span>

1. <span data-ttu-id="83d36-115">[連線至 Exchange Online PowerShell]。</span><span class="sxs-lookup"><span data-stu-id="83d36-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="83d36-116">如需相關指示，請參閱連線[至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)。</span><span class="sxs-lookup"><span data-stu-id="83d36-116">For instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module).</span></span>

2. <span data-ttu-id="83d36-117">在 Exchange Online PowerShell 中，建立新的會議室信箱或修改現有的會議室信箱。</span><span class="sxs-lookup"><span data-stu-id="83d36-117">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span>

   - <span data-ttu-id="83d36-118">若要建立新的會議室信箱，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="83d36-118">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="83d36-119">這個範例會使用下列設定建立新的會議室信箱：</span><span class="sxs-lookup"><span data-stu-id="83d36-119">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="83d36-120">Name （名稱）： Huddle-01</span><span class="sxs-lookup"><span data-stu-id="83d36-120">Name: Huddle-Room-01</span></span>

     - <span data-ttu-id="83d36-121">別名： HuddleRoom01</span><span class="sxs-lookup"><span data-stu-id="83d36-121">Alias: HuddleRoom01</span></span>

     - <span data-ttu-id="83d36-122">帳戶： huddleroom01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="83d36-122">Account: huddleroom01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="83d36-123">帳戶密碼： P@ $ $W 0rd242</span><span class="sxs-lookup"><span data-stu-id="83d36-123">Account password: P@$$W0rd242</span></span>

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - <span data-ttu-id="83d36-124">若要修改現有的會議室信箱，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="83d36-124">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="83d36-125">這個範例會為擁有別名值 HuddleRoom02 的現有聊天室信箱啟用帳戶，並將密碼設定為 808P@ $ $W 0rd。</span><span class="sxs-lookup"><span data-stu-id="83d36-125">This example enables the account for the existing room mailbox that has the alias value HuddleRoom02, and sets the password to 808P@$$W0rd.</span></span> <span data-ttu-id="83d36-126">請注意，由於現有的別名值，該帳戶將會 HuddleRoom02@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="83d36-126">Note that the account will be HuddleRoom02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="83d36-127">如需詳細的語法與參數資訊，請參閱[新增-信箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox)和[設定信箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="83d36-127">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="83d36-128">在 Exchange Online PowerShell 中，設定會議室信箱上的下列設定，以改善會議體驗：</span><span class="sxs-lookup"><span data-stu-id="83d36-128">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="83d36-129">AutomateProcessing： AutoAccept （會議召集人直接在沒有人工干預的情況下收到會議室保留決策：免費 = accept; 忙碌 = 拒絕。）</span><span class="sxs-lookup"><span data-stu-id="83d36-129">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="83d36-130">AddOrganizerToSubject： $false （會議召集人不會新增至會議邀請的主旨。）</span><span class="sxs-lookup"><span data-stu-id="83d36-130">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="83d36-131">DeleteComments： $false （在傳入會議邀請的郵件內文中保留任何文字。）</span><span class="sxs-lookup"><span data-stu-id="83d36-131">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="83d36-132">DeleteSubject： $false （請不要傳送會議邀請的主題）。</span><span class="sxs-lookup"><span data-stu-id="83d36-132">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="83d36-133">RemovePrivateProperty： $false （保證會議召集人在原始會議邀請中傳送的私人旗標保持在指定的時間。）</span><span class="sxs-lookup"><span data-stu-id="83d36-133">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="83d36-134">AddAdditionalResponse： $true （由 AdditionalResponse 參數指定的文字會新增至會議邀請。）</span><span class="sxs-lookup"><span data-stu-id="83d36-134">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="83d36-135">AdditionalResponse：「此聊天室有一個適用于 Microsoft 團隊的共同作業工具列！」</span><span class="sxs-lookup"><span data-stu-id="83d36-135">AdditionalResponse: "This room has a collaboration bar for Microsoft Teams!"</span></span> <span data-ttu-id="83d36-136">（要新增至會議邀請的其他文字）。</span><span class="sxs-lookup"><span data-stu-id="83d36-136">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="83d36-137">這個範例會在名為 Huddle-01 的聊天室信箱上設定這些設定。</span><span class="sxs-lookup"><span data-stu-id="83d36-137">This example configures these settings on the room mailbox named Huddle-Room-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   <span data-ttu-id="83d36-138">如需詳細的語法與參數資訊，請參閱[設定 CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)。</span><span class="sxs-lookup"><span data-stu-id="83d36-138">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="83d36-139">使用 PowerShell Cmdlet 連線至 MS Online PowerShell，以進行 Active Directory 設定 `Connect-MsolService -Credential $cred` 。</span><span class="sxs-lookup"><span data-stu-id="83d36-139">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="83d36-140">如需 Active Directory 的詳細資訊，請參閱[Azure ActiveDirectory （import-module msonline） 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="83d36-140">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="83d36-141">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)不受支援。</span><span class="sxs-lookup"><span data-stu-id="83d36-141">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

5. <span data-ttu-id="83d36-142">使用下列語法，將 huddleroom01@contoso.onmicrosoft.com 的密碼設定為不超過到期日：</span><span class="sxs-lookup"><span data-stu-id="83d36-142">Set the password for huddleroom01@contoso.onmicrosoft.com to not expire using the following syntax:</span></span>

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. <span data-ttu-id="83d36-143">資源帳戶必須擁有有效的 Office 365 授權，最好是會議室 SKU。</span><span class="sxs-lookup"><span data-stu-id="83d36-143">The resource account needs to have a valid Office 365 license, preferably the Meeting Room SKU.</span></span> <span data-ttu-id="83d36-144">您也需要將使用位置指派給您的裝置帳戶，這會決定您的帳戶可使用哪些授權 Sku。</span><span class="sxs-lookup"><span data-stu-id="83d36-144">You also need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="83d36-145">您可以用 `Get-MsolAccountSku` 來針對您的 Office 365 租使用者取得可用的 sku 清單。</span><span class="sxs-lookup"><span data-stu-id="83d36-145">You can use `Get-MsolAccountSku` to retrieve a list of available SKUs for your Office 365 tenant.</span></span>

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    <span data-ttu-id="83d36-146">您可以使用 [設定] MsolUserLicense 指派授權。</span><span class="sxs-lookup"><span data-stu-id="83d36-146">You can assign the license using Set-MsolUserLicense.</span></span> 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   <span data-ttu-id="83d36-147">如需詳細指示，請參閱[使用 Office 365 PowerShell 指派授權給使用者帳戶](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="83d36-147">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>




[<span data-ttu-id="83d36-148">使用 PowerShell 針對 Microsoft 團隊設定共同作業橫條圖的帳戶</span><span class="sxs-lookup"><span data-stu-id="83d36-148">Configure accounts for collaboration bars for Microsoft Teams using PowerShell</span></span>](resource-account-ps.md)

[<span data-ttu-id="83d36-149">為 Microsoft 團隊部署共同作業橫條圖</span><span class="sxs-lookup"><span data-stu-id="83d36-149">Deploy collaboration bars for Microsoft Teams</span></span>](collab-bar-deploy.md)

[<span data-ttu-id="83d36-150">Microsoft 團隊授權的共同作業條</span><span class="sxs-lookup"><span data-stu-id="83d36-150">Collaboration bars for Microsoft Teams Licensing</span></span>](../rooms/rooms-licensing.md)


