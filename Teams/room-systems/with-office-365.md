---
title: 使用 Office 365 部署 Microsoft 團隊聊天室
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: 如需有關如何使用 Office 365 部署 Microsoft 團隊聊天室的資訊, 請閱讀本主題。
ms.openlocfilehash: 9c1e14e9e5e7b32aa6ba4a1b08a2ae6ee8453d93
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243231"
---
# <a name="deploy-microsoft-teams-rooms-with-office-365"></a><span data-ttu-id="c8cce-103">使用 Office 365 部署 Microsoft 團隊聊天室</span><span class="sxs-lookup"><span data-stu-id="c8cce-103">Deploy Microsoft Teams Rooms with Office 365</span></span>

<span data-ttu-id="c8cce-104">如需有關如何使用 Office 365 (Microsoft 團隊或商務用 Skype 與 Exchange 都在線上) 部署 Microsoft 團隊聊天室的資訊, 請閱讀本主題。</span><span class="sxs-lookup"><span data-stu-id="c8cce-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Office 365, where Microsoft Teams or Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="c8cce-105">設定使用者帳戶最簡單的方法, 就是使用遠端 Windows PowerShell 進行設定。</span><span class="sxs-lookup"><span data-stu-id="c8cce-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="c8cce-106">Microsoft 提供[SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105), 此腳本將協助您建立新的使用者帳戶, 或驗證您所擁有的現有資源帳戶, 以協助您將它們轉換成相容的 Microsoft 團隊聊天室使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="c8cce-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="c8cce-107">如果您想要的話, 您可以依照下列步驟來設定您的 Microsoft 團隊聊天室裝置將會使用的帳戶。</span><span class="sxs-lookup"><span data-stu-id="c8cce-107">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="c8cce-108">需求</span><span class="sxs-lookup"><span data-stu-id="c8cce-108">Requirements</span></span>

<span data-ttu-id="c8cce-109">在使用 Office 365 部署 Microsoft 團隊聊天室之前, 請確定您已滿足需求。</span><span class="sxs-lookup"><span data-stu-id="c8cce-109">Before you deploy Microsoft Teams Rooms with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="c8cce-110">如需詳細資訊, 請參閱[Microsoft 團隊會議室需求](requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c8cce-110">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>

<span data-ttu-id="c8cce-111">若要啟用商務用 Skype, 您必須具備下列各項:</span><span class="sxs-lookup"><span data-stu-id="c8cce-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="c8cce-112">Office 365 方案中的商務用 Skype Online (方案2或企業方案) 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="c8cce-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Office 365 plan.</span></span> <span data-ttu-id="c8cce-113">方案需要允許電話撥入式會議功能。</span><span class="sxs-lookup"><span data-stu-id="c8cce-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="c8cce-114">如果您需要來自會議的撥入功能, 您將需要音訊會議和電話系統授權。</span><span class="sxs-lookup"><span data-stu-id="c8cce-114">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="c8cce-115">如果您需要來自會議的撥出功能, 您需要國內或國內和國際通話方案。</span><span class="sxs-lookup"><span data-stu-id="c8cce-115">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span>

- <span data-ttu-id="c8cce-116">您的租使用者必須有 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="c8cce-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="c8cce-117">您的 Microsoft 團隊會議室帳戶至少需要商務用 Skype Online (方案 2) 授權, 但不需要 Exchange Online 授權。</span><span class="sxs-lookup"><span data-stu-id="c8cce-117">Your Microsoft Teams Rooms account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="c8cce-118">如需詳細資訊, 請參閱[Microsoft 團隊聊天室授權](skype-room-systems-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="c8cce-118">See [Microsoft Teams Rooms licenses](skype-room-systems-v2.md) for details.</span></span>

<span data-ttu-id="c8cce-119">如需商務用 Skype Online 方案的詳細資料, 請參閱[商務用 Skype Online 服務說明](https://technet.microsoft.com/library/jj822172.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c8cce-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="c8cce-120">新增裝置帳戶</span><span class="sxs-lookup"><span data-stu-id="c8cce-120">Add a device account</span></span>

1. <span data-ttu-id="c8cce-121">[連線至 Exchange Online PowerShell]。</span><span class="sxs-lookup"><span data-stu-id="c8cce-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="c8cce-122">如需相關指示, 請參閱連線[至 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="c8cce-122">For instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

2. <span data-ttu-id="c8cce-123">在 Exchange Online PowerShell 中, 建立新的會議室信箱或修改現有的會議室信箱。</span><span class="sxs-lookup"><span data-stu-id="c8cce-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="c8cce-124">根據預設, 會議室信箱沒有相關聯的帳戶, 因此, 當您建立或修改允許該帳戶透過 Skype 會議室系統 v2 進行驗證的聊天室信箱時, 您將需要新增帳戶。</span><span class="sxs-lookup"><span data-stu-id="c8cce-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="c8cce-125">若要建立新的會議室信箱, 請使用下列語法:</span><span class="sxs-lookup"><span data-stu-id="c8cce-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="c8cce-126">這個範例會使用下列設定建立新的會議室信箱:</span><span class="sxs-lookup"><span data-stu-id="c8cce-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="c8cce-127">名稱: 專案-Rigel-01</span><span class="sxs-lookup"><span data-stu-id="c8cce-127">Name: Project-Rigel-01</span></span>

     - <span data-ttu-id="c8cce-128">別名: ProjectRigel01</span><span class="sxs-lookup"><span data-stu-id="c8cce-128">Alias: ProjectRigel01</span></span>

     - <span data-ttu-id="c8cce-129">帳戶: ProjectRigel01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="c8cce-129">Account: ProjectRigel01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="c8cce-130">帳戶密碼: P @ $ $W 0rd5959</span><span class="sxs-lookup"><span data-stu-id="c8cce-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Project-Rigel-01" -Alias ProjectRigel01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID ProjectRigel01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="c8cce-131">若要修改現有的會議室信箱, 請使用下列語法:</span><span class="sxs-lookup"><span data-stu-id="c8cce-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="c8cce-132">這個範例會為擁有別名值 ProjectRigel02 的現有聊天室信箱啟用帳戶, 並將密碼設定為 9898P @ $ $W 0rd。</span><span class="sxs-lookup"><span data-stu-id="c8cce-132">This example enables the account for the existing room mailbox that has the alias value ProjectRigel02, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="c8cce-133">請注意, 由於現有的別名值, 該帳戶將會 ProjectRigel02@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="c8cce-133">Note that the account will be ProjectRigel02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity ProjectRigel02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="c8cce-134">如需詳細的語法與參數資訊, 請參閱[新增-信箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox)和[設定信箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="c8cce-134">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="c8cce-135">在 Exchange Online PowerShell 中, 設定會議室信箱上的下列設定, 以改善會議體驗:</span><span class="sxs-lookup"><span data-stu-id="c8cce-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="c8cce-136">AutomateProcessing: AutoAccept (會議召集人直接在沒有人工干預的情況下收到會議室保留決策: 免費 = accept; 忙碌 = 拒絕。)</span><span class="sxs-lookup"><span data-stu-id="c8cce-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="c8cce-137">AddOrganizerToSubject: $false (會議召集人不會新增至會議邀請的主旨。)</span><span class="sxs-lookup"><span data-stu-id="c8cce-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="c8cce-138">DeleteComments: $false (在傳入會議邀請的郵件內文中保留任何文字。)</span><span class="sxs-lookup"><span data-stu-id="c8cce-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="c8cce-139">DeleteSubject: $false (請不要傳送會議邀請的主題)。</span><span class="sxs-lookup"><span data-stu-id="c8cce-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="c8cce-140">RemovePrivateProperty: $false (保證會議召集人在原始會議邀請中傳送的私人旗標保持在指定的時間。)</span><span class="sxs-lookup"><span data-stu-id="c8cce-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="c8cce-141">AddAdditionalResponse: $true (由 AdditionalResponse 參數指定的文字會新增至會議邀請。)</span><span class="sxs-lookup"><span data-stu-id="c8cce-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="c8cce-142">AdditionalResponse: 「這是 Skype 會議室!」</span><span class="sxs-lookup"><span data-stu-id="c8cce-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="c8cce-143">(要新增至會議邀請的其他文字)。</span><span class="sxs-lookup"><span data-stu-id="c8cce-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="c8cce-144">這個範例會在名為 Project-Rigel-01 的聊天室信箱上設定這些設定。</span><span class="sxs-lookup"><span data-stu-id="c8cce-144">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="c8cce-145">如需詳細的語法與參數資訊, 請參閱[設定 CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)。</span><span class="sxs-lookup"><span data-stu-id="c8cce-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="c8cce-146">使用`Connect-MsolService -Credential $cred` PowerShell Cmdlet 連線至 MS Online PowerShell, 以進行 Active Directory 設定。</span><span class="sxs-lookup"><span data-stu-id="c8cce-146">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="c8cce-147">如需 Active Directory 的詳細資訊, 請參閱[Azure ActiveDirectory (import-module msonline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="c8cce-147">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="c8cce-148">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0)不受支援。</span><span class="sxs-lookup"><span data-stu-id="c8cce-148">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

5. <span data-ttu-id="c8cce-149">如果您不希望密碼到期, 請使用下列語法:</span><span class="sxs-lookup"><span data-stu-id="c8cce-149">If you do not want the password to expire, use the following syntax:</span></span>

    ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
    ```
<!--
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   <span data-ttu-id="c8cce-150">這個範例會將帳戶 ProjectRigel01@contoso.onmicrosoft.com 的密碼設為永不過期。</span><span class="sxs-lookup"><span data-stu-id="c8cce-150">This example sets the password for the account ProjectRigel01@contoso.onmicrosoft.com to never expire.</span></span>

  ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName ProjectRigel01@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   <span data-ttu-id="c8cce-151">您也可以執行下列命令, 以設定帳戶的電話號碼:</span><span class="sxs-lookup"><span data-stu-id="c8cce-151">You can also set a phone number for the account by running the following command:</span></span>

  ``` PowerShell
    Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. <span data-ttu-id="c8cce-152">裝置帳戶必須具備有效的 Office 365 授權, 或是 Exchange 與 Microsoft 團隊或商務用 Skype 將無法運作。</span><span class="sxs-lookup"><span data-stu-id="c8cce-152">The device account needs to have a valid Office 365 license, or Exchange and Microsoft Teams or Skype for Business will not work.</span></span> <span data-ttu-id="c8cce-153">如果您有授權, 您必須將使用位置指派給您的裝置帳戶, 這會決定您的帳戶可使用哪些授權 Sku。</span><span class="sxs-lookup"><span data-stu-id="c8cce-153">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="c8cce-154">您可以使用`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="c8cce-154">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="c8cce-155">若要為您的 Office 365 租使用者取得可用的 Sku 清單, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="c8cce-155">to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>

  ``` Powershell
  Get-MsolAccountSku
  ```
<!--
   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   <span data-ttu-id="c8cce-156">接下來, 您可以使用`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="c8cce-156">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!--Set-AzureADUserLicense --> <span data-ttu-id="c8cce-157">Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c8cce-157">cmdlet.</span></span> <span data-ttu-id="c8cce-158">在此情況下, $strLicense 是您所看到的 SKU 程式碼 (例如 contoso: STANDARDPACK)。</span><span class="sxs-lookup"><span data-stu-id="c8cce-158">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

  ``` PowerShell
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
  ``` 
<!-- 
   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```   -->

   <span data-ttu-id="c8cce-159">如需詳細指示, 請參閱[使用 Office 365 PowerShell 指派授權給使用者帳戶](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="c8cce-159">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

7. <span data-ttu-id="c8cce-160">接下來, 您必須在商務用 Skype 中啟用裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="c8cce-160">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="c8cce-161">請確定您的環境符合[Microsoft 團隊會議室需求](requirements.md)中定義的需求。</span><span class="sxs-lookup"><span data-stu-id="c8cce-161">Be sure your environment meets the requirements defined in [Microsoft Teams Rooms requirements](requirements.md).</span></span>

   <span data-ttu-id="c8cce-162">啟動遠端[Windows PowerShell 會話](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell), 如下所示 (請務必[安裝商務用 Skype Online PowerShell 元件](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span><span class="sxs-lookup"><span data-stu-id="c8cce-162">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="c8cce-163">接下來, 請執行下列 Cmdlet, 為商務用 Skype Server 啟用您的 Microsoft 團隊房間帳戶:</span><span class="sxs-lookup"><span data-stu-id="c8cce-163">Next, enable your Microsoft Teams Rooms account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   <span data-ttu-id="c8cce-164">從要設定的新使用者帳戶取得 RegistrarPool 資訊, 如下例所示:</span><span class="sxs-lookup"><span data-stu-id="c8cce-164">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

    ``` Powershell
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > <span data-ttu-id="c8cce-165">可能不會在與租使用者帳戶相同的註冊機構池中建立新的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="c8cce-165">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="c8cce-166">上述命令會防止由於這種情況而導致帳戶設定發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="c8cce-166">The command above will prevent errors in account setup due to this situation.</span></span>

<span data-ttu-id="c8cce-167">完成上述步驟後, 若要啟用 microsoft 團隊或商務用 Skype Online 中的 Microsoft 小組聊天室帳戶, 您必須將授權指派給 Microsoft 團隊聊天室裝置。</span><span class="sxs-lookup"><span data-stu-id="c8cce-167">After you've completed the preceding steps to enable your Microsoft Teams Rooms account in Microsoft Teams or Skype for Business Online, you need to assign a license to Microsoft Teams Rooms device.</span></span> <span data-ttu-id="c8cce-168">使用 Office 365 系統管理中心入口網站, 將商務用 Skype Online (方案 2) 或商務用 Skype Online (方案 3) 授權指派到裝置。</span><span class="sxs-lookup"><span data-stu-id="c8cce-168">Using the Office 365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>

### <a name="assign-a-license-to-your-account"></a><span data-ttu-id="c8cce-169">指派授權給您的帳戶</span><span class="sxs-lookup"><span data-stu-id="c8cce-169">Assign a license to your account</span></span>

1. <span data-ttu-id="c8cce-170">以租使用者管理員身分登入, 開啟 Office 365 系統管理中心入口網站, 然後按一下 [管理] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="c8cce-170">Login as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>

2. <span data-ttu-id="c8cce-171">按一下 [**使用者和群組**], 然後按一下 [**新增使用者、重設密碼**等等]。</span><span class="sxs-lookup"><span data-stu-id="c8cce-171">Click **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>

3. <span data-ttu-id="c8cce-172">選取 [Microsoft 團隊聊天室] 帳戶, 然後按一下或輕觸手寫筆圖示, 也就是 [編輯]。</span><span class="sxs-lookup"><span data-stu-id="c8cce-172">Select the Microsoft Teams Rooms account, and then click or tap the pen icon, which means edit.</span></span>

4. <span data-ttu-id="c8cce-173">按一下 [**授權**] 選項。</span><span class="sxs-lookup"><span data-stu-id="c8cce-173">Click on the **Licenses** option.</span></span>

5. <span data-ttu-id="c8cce-174">在 [**指派授權**] 區段中, 您必須選取 [商務用 skype Online (方案 2)] 或 [商務用 skype Online (方案 3)], 這取決於您的授權, 以及您在需要企業語音時所決定的內容。</span><span class="sxs-lookup"><span data-stu-id="c8cce-174">In the **Assign licenses** section, you need to select Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3), depending on your licensing and what you've decided in terms of needing Enterprise Voice.</span></span> <span data-ttu-id="c8cce-175">如果您想要在 Microsoft 團隊聊天室使用雲端 PBX, 您必須使用 [方案3授權]。</span><span class="sxs-lookup"><span data-stu-id="c8cce-175">You'll have to use a Plan 3 license if you want to use Cloud PBX on Microsoft Teams Rooms.</span></span> <span data-ttu-id="c8cce-176">您至少需要 CloudPBX 才能進行語音連線。</span><span class="sxs-lookup"><span data-stu-id="c8cce-176">Minimally you will need CloudPBX for voice connectivity.</span></span> <span data-ttu-id="c8cce-177">然後根據 PSTN 連接方法設定混合式語音或 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="c8cce-177">Then configure hybrid voice or PSTN calling based on the PSTN connectivity method.</span></span> <span data-ttu-id="c8cce-178">如需詳細資訊, 請參閱[Microsoft 團隊聊天室授權](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)。</span><span class="sxs-lookup"><span data-stu-id="c8cce-178">See [Microsoft Teams Rooms licenses](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) for more details.</span></span>

6. <span data-ttu-id="c8cce-179">按一下 [**儲存**] 以完成工作。</span><span class="sxs-lookup"><span data-stu-id="c8cce-179">Click **Save** to complete the task.</span></span>

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="c8cce-180">範例: Exchange Online 和商務用 Skype Online 中的房間帳戶設定</span><span class="sxs-lookup"><span data-stu-id="c8cce-180">Sample: Room account setup in Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="c8cce-181">Exchange Online PowerShell 命令:</span><span class="sxs-lookup"><span data-stu-id="c8cce-181">Exchange Online PowerShell commands:</span></span>

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept-AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

<span data-ttu-id="c8cce-182">Azure Active Directory PowerShell 命令:</span><span class="sxs-lookup"><span data-stu-id="c8cce-182">Azure Active Directory PowerShell commands:</span></span>

``` PowerShell
Set-MsolUser -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```

<!-- 
``` PowerShell
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```  -->

<span data-ttu-id="c8cce-183">商務用 Skype PowerShell 命令:</span><span class="sxs-lookup"><span data-stu-id="c8cce-183">Skype for Business PowerShell command:</span></span>

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> <span data-ttu-id="c8cce-184">這會新增 CloudPBX 和 PSTNCallingDomesticAndInternational。</span><span class="sxs-lookup"><span data-stu-id="c8cce-184">This adds CloudPBX and PSTNCallingDomesticAndInternational.</span></span> <span data-ttu-id="c8cce-185">此外, 您必須使用系統管理員介面指派電話號碼。</span><span class="sxs-lookup"><span data-stu-id="c8cce-185">Additionally, you will need to use the Admin interface to assign a phone number.</span></span>

## <a name="validate"></a><span data-ttu-id="c8cce-186">核實</span><span class="sxs-lookup"><span data-stu-id="c8cce-186">Validate</span></span>

<span data-ttu-id="c8cce-187">針對驗證, 您應該能夠使用任何商務用 Skype 用戶端登入您所建立的帳戶。</span><span class="sxs-lookup"><span data-stu-id="c8cce-187">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="c8cce-188">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c8cce-188">See also</span></span>

[<span data-ttu-id="c8cce-189">設定 Microsoft 團隊聊天室的帳戶</span><span class="sxs-lookup"><span data-stu-id="c8cce-189">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="c8cce-190">規劃 Microsoft 團隊聊天室</span><span class="sxs-lookup"><span data-stu-id="c8cce-190">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)

[<span data-ttu-id="c8cce-191">部署 Microsoft 團隊聊天室</span><span class="sxs-lookup"><span data-stu-id="c8cce-191">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)

[<span data-ttu-id="c8cce-192">設定 Microsoft 團隊聊天室主控台</span><span class="sxs-lookup"><span data-stu-id="c8cce-192">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="c8cce-193">管理 Microsoft 團隊聊天室</span><span class="sxs-lookup"><span data-stu-id="c8cce-193">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)

[<span data-ttu-id="c8cce-194">Microsoft 團隊聊天室授權</span><span class="sxs-lookup"><span data-stu-id="c8cce-194">Microsoft Teams Rooms Licensing</span></span>](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md)
