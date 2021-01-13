---
title: Skype 會議室系統單一樹系內部部署
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: 閱讀此主題以瞭解如何在單一樹系內部部署環境中部署 Skype 會議室系統。
ms.openlocfilehash: 0449a5e909fa044df12766aec0a036bf97315386
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820753"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a><span data-ttu-id="f9995-103">Skype 會議室系統單一樹系內部部署</span><span class="sxs-lookup"><span data-stu-id="f9995-103">Skype Room System single forest on-premises deployments</span></span>
 
<span data-ttu-id="f9995-104">閱讀此主題以瞭解如何在單一樹系內部部署環境中部署 Skype 會議室系統。</span><span class="sxs-lookup"><span data-stu-id="f9995-104">Read this topic to learn how to deploy Skype Room System in a single forest on-premises environment.</span></span>
  
<span data-ttu-id="f9995-105">本節概述在 Exchange Server 上布建 Skype 室系統帳戶的步驟，以及在單一樹系內部部署中主控的商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="f9995-105">This section provides an overview of the steps for provisioning the Skype Room System account on Exchange Server and Skype for Business Server hosted in a single forest on-premises deployment.</span></span>
  
## <a name="single-forest-on-premises-deployments"></a><span data-ttu-id="f9995-106">單一樹系內部部署</span><span class="sxs-lookup"><span data-stu-id="f9995-106">Single forest on-premises deployments</span></span>

<span data-ttu-id="f9995-107">如果您已經有會議室的資源信箱帳戶，您可以使用它。</span><span class="sxs-lookup"><span data-stu-id="f9995-107">If you already have a resource mailbox account for the conferencing room, you can use it.</span></span> <span data-ttu-id="f9995-108">否則，您將需要建立一個新的。</span><span class="sxs-lookup"><span data-stu-id="f9995-108">Otherwise, you will need to create a new one.</span></span> <span data-ttu-id="f9995-109">您可以使用 Exchange 管理命令介面 (PowerShell) 或 Exchange 管理主控台來建立新的資源信箱帳戶。</span><span class="sxs-lookup"><span data-stu-id="f9995-109">You can use either Exchange Management Shell (PowerShell) or Exchange Management Console to create a new resource mailbox account.</span></span> <span data-ttu-id="f9995-110">我們建議使用新的 (刪除舊的信箱，並為 Skype 會議室系統重新建立) 資源信箱。</span><span class="sxs-lookup"><span data-stu-id="f9995-110">We recommend using a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="f9995-111">請務必先備份信箱資料，然後再將其匯出回使用 Outlook 用戶端重新建立的信箱 (請參閱匯出或備份郵件、行事曆、工作和連絡人，以取得詳細資訊) 。</span><span class="sxs-lookup"><span data-stu-id="f9995-111">Make sure to back up mailbox data before deleting and then export it back to the re-created mailbox using the Outlook client (see Export or back up messages, calendar, tasks, and contacts for more information).</span></span> <span data-ttu-id="f9995-112">若要還原因刪除信箱而遺失的會議，請參閱連線 [或還原已刪除的信箱](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="f9995-112">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="f9995-113">若要使用現有的資源信箱帳戶 (例如，LRS-01) 請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="f9995-113">To use an existing resource mailbox account (for example, LRS-01) follow the steps below:</span></span>
  
1. <span data-ttu-id="f9995-114">執行下列 Exchange Management PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="f9995-114">Run the following Exchange Management PowerShell command:</span></span>
    
   ```powershell
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. <span data-ttu-id="f9995-115">如果您想要建立新的信箱，請針對單一樹系內部部署 Exchange 組織執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="f9995-115">If you plan to create a new mailbox, then, for a single forest on-premises Exchange organization, run the following command:</span></span>
    
   ```powershell
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   <span data-ttu-id="f9995-116">上述範例會在 Active Directory 中建立已啟用的使用者帳戶，並在內部部署 Exchange 組織中的會議室信箱中建立會議室信箱。</span><span class="sxs-lookup"><span data-stu-id="f9995-116">The above example creates an enabled user account in Active Directory and a room mailbox for a conference room in an on-premises Exchange organization.</span></span> <span data-ttu-id="f9995-117">RoomMailboxPassword 參數能指定使用者帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="f9995-117">The RoomMailboxPassword parameter specifies the password for the user account.</span></span>
    
3. <span data-ttu-id="f9995-118">透過接受/拒絕會議，將帳戶設定為自動解決衝突。</span><span class="sxs-lookup"><span data-stu-id="f9995-118">Configure the account to automatically resolve conflicts by accepting/rejecting meetings.</span></span> <span data-ttu-id="f9995-119">Exchange 的 Skype 會議室系統配備的會議室帳戶可由個人管理，但請注意，直到個別人接受會議時，它才會顯示在 Skype 室系統主畫面行事曆上。</span><span class="sxs-lookup"><span data-stu-id="f9995-119">Skype Room System-equipped conference room accounts in Exchange can be managed by individuals, but note that until the individual accepts a meeting it will not appear on the Skype Room System home screen calendar.</span></span>
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   <span data-ttu-id="f9995-120">如需一組完整的可用命令，請參閱 Set-CalendarProcessing。</span><span class="sxs-lookup"><span data-stu-id="f9995-120">For a complete set of commands available, see Set-CalendarProcessing.</span></span>
    
   <span data-ttu-id="f9995-121">若要提醒會議召集人使會議成為 Outlook 中的線上商務用 Skype 會議，請執行下列命令來設定新帳戶的 MailTip：</span><span class="sxs-lookup"><span data-stu-id="f9995-121">To remind meeting organizers to make the meeting an online Skype for Business meeting in Outlook, run the following command to set up a MailTip for the new account:</span></span> 
    
   ```powershell
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. <span data-ttu-id="f9995-122">使用下列命令來設定當地語系化的字串。</span><span class="sxs-lookup"><span data-stu-id="f9995-122">Use the following commands to configure localized strings.</span></span> <span data-ttu-id="f9995-123">如果您的組織需要，您也可以新增自訂翻譯：</span><span class="sxs-lookup"><span data-stu-id="f9995-123">If required by your organization, you can also add custom translations:</span></span> 
   ```powershell
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. <span data-ttu-id="f9995-124">選用：設定會議接受文字，以提供使用者商務用 Skype 會議室的相關資訊，以及排程及加入會議時預期的專案。</span><span class="sxs-lookup"><span data-stu-id="f9995-124">Optional: Configure meeting acceptance text that provides users with information about Skype for Business Meeting Room, and what to expect when they schedule and join meetings.</span></span> 
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a><span data-ttu-id="f9995-125">檢查 Active Directory 中的資源信箱帳戶</span><span class="sxs-lookup"><span data-stu-id="f9995-125">Check Resource Mailbox Account in Active Directory</span></span>

<span data-ttu-id="f9995-126">在上述步驟1中由 Exchange 所建立的會議室信箱帳戶可能是 Active Directory 中已停用的使用者物件。</span><span class="sxs-lookup"><span data-stu-id="f9995-126">The conference room mailbox account created by Exchange in step 1 above might be a disabled user object in Active Directory.</span></span> <span data-ttu-id="f9995-127">如果在 Active Directory 中停用帳戶，則 Skype 會議室系統無法使用 Kerberos/NTLM 驗證來登入或驗證。</span><span class="sxs-lookup"><span data-stu-id="f9995-127">Skype Room System cannot sign in or authenticate by using Kerberos/NTLM authentication if the account is disabled in Active Directory.</span></span> <span data-ttu-id="f9995-128">Skype 聊天室系統用戶端必須能夠對 Exchange Web 服務進行驗證，以取得行事曆設定，也必須能夠使用白板內容傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="f9995-128">The Skype Room System client must be able to authenticate against Exchange Web Services to retrieve calendar settings, and must also be able to send email with whiteboard contents.</span></span> 
  
<span data-ttu-id="f9995-129">因此，如果停用帳戶，您必須執行下列動作，以在 Active Directory 中啟用此帳戶：</span><span class="sxs-lookup"><span data-stu-id="f9995-129">Therefore, if the account is disabled, you must enable this account in Active Directory by doing the following:</span></span> 
  
1. <span data-ttu-id="f9995-130">在 Active Directory 中執行下列命令，以啟用帳戶登入：</span><span class="sxs-lookup"><span data-stu-id="f9995-130">In Active Directory, run the following command to enable account log on:</span></span> 
    
   ```powershell
   Set-ADAccountPassword -Identity LRS01
   ```

   <span data-ttu-id="f9995-131">執行此命令時，會提示您輸入目前的密碼，然後重新輸入密碼兩次進行確認。</span><span class="sxs-lookup"><span data-stu-id="f9995-131">Running this command will prompt you to enter the current password, and then to re-enter the password twice for confirmation.</span></span>
    
2. <span data-ttu-id="f9995-132">設定密碼後，請執行下列命令來啟用帳戶：</span><span class="sxs-lookup"><span data-stu-id="f9995-132">Once the password is set, run the following command to enable the account:</span></span> 
    
   ```powershell
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a><span data-ttu-id="f9995-133">啟用商務用 Skype 的 Skype 會議室系統帳戶</span><span class="sxs-lookup"><span data-stu-id="f9995-133">Enabling Skype Room System Accounts for Skype for Business</span></span>

<span data-ttu-id="f9995-134">本節概述為您的會議室帳戶啟用商務用 Skype 所需的步驟，該帳戶會在 Skype 會議室系統上進行設定。</span><span class="sxs-lookup"><span data-stu-id="f9995-134">This section provides an overview of the steps required to enable Skype for Business for your conference room account, which will be configured on Skype Room System.</span></span> 
  
<span data-ttu-id="f9995-135">在您為會議房建立資源信箱帳戶後，請使用商務用 Skype Server 管理命令介面來啟用商務用 Skype 服務的 Skype 會議室系統帳戶。</span><span class="sxs-lookup"><span data-stu-id="f9995-135">After you create a resource mailbox account for the conferencing rooms, use Skype for Business Server Management Shell to enable Skype Room System accounts for Skype for Business services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f9995-136">下列程式假設您已在 Active Directory 中啟用 Skype 會議室系統帳戶。</span><span class="sxs-lookup"><span data-stu-id="f9995-136">The following procedure assumes that you have enabled the Skype Room System account in Active Directory.</span></span> 
  
1. <span data-ttu-id="f9995-137">執行下列命令，啟用商務用 Skype 伺服器集區上的 Skype 聊天室系統帳戶：</span><span class="sxs-lookup"><span data-stu-id="f9995-137">Run the following command to enable the Skype Room System account on a Skype for Business Server pool:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. <span data-ttu-id="f9995-138">選用：允許此帳戶透過啟用 Enterprise Voice 的帳戶來撥打及接收 PSTN 電話。</span><span class="sxs-lookup"><span data-stu-id="f9995-138">Optional: Allow this account to make and receive PSTN phone calls by enabling the account for Enterprise Voice.</span></span> <span data-ttu-id="f9995-139">[！注意事項] 對於 Skype 室系統不需要 Enterprise Voice，但如果您不啟用 Enterprise Voice，則 Skype 會議室系統用戶端將無法提供 PSTN 撥號功能：</span><span class="sxs-lookup"><span data-stu-id="f9995-139">Enterprise Voice is not required for Skype Room System, but if you do not enable it for Enterprise Voice, the Skype Room System client won't be able to provide PSTN dialing functionality:</span></span>
    
   ```powershell
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="f9995-140">如果您為 Skype 聊天室系統會議室帳戶啟用 Enterprise Voice，請務必設定適用于您組織的受限制語音原則。</span><span class="sxs-lookup"><span data-stu-id="f9995-140">If you enable Enterprise Voice for the Skype Room System conference room account, make sure to configure a restricted Voice Policy suitable for your organization.</span></span> <span data-ttu-id="f9995-141">如果商務用 Skype 會議室是公開提供的資源，任何人都可以使用該會議室加入會議，無論是排程或即席會議。</span><span class="sxs-lookup"><span data-stu-id="f9995-141">If the Skype for Business Meeting Room is a publicly available resource, anyone could use it to join a meeting, either scheduled or ad hoc.</span></span> <span data-ttu-id="f9995-142">加入會議之後，使用者可以撥出任何號碼。</span><span class="sxs-lookup"><span data-stu-id="f9995-142">After joining a meeting, the person could dial out to any number.</span></span> <span data-ttu-id="f9995-143">在商務用 Skype Server 中，「從會議撥出」功能使用使用者的語音原則，在此案例中是用來加入會議的 Skype 會議室系統帳戶。</span><span class="sxs-lookup"><span data-stu-id="f9995-143">In Skype for Business Server, the dial-out from conferences feature uses the voice policy of the user, in this case the Skype Room System account used to join the meeting.</span></span> <span data-ttu-id="f9995-144">在舊版的 Lync Server 中，會使用召集人的語音原則。</span><span class="sxs-lookup"><span data-stu-id="f9995-144">In earlier versions of Lync Server, the voice policy of the organizer is used.</span></span> <span data-ttu-id="f9995-145">因此，如果舊版 Lync Server 的使用者排程會議室和邀請商務用 skype 會議室帳戶，任何人都可以使用商務用 Skype 會議室加入會議，而且可以撥打任何國內/地區或國際電話號碼，只要召集人可以撥打這些號碼。</span><span class="sxs-lookup"><span data-stu-id="f9995-145">Therefore, if a user of an earlier version of Lync Server schedules a meeting room and invites the Skype Room System room account, anyone could use the Skype for Business Meeting Room to join the meeting and could dial any national/regional or international phone number, as long as the organizer is allowed to dial those numbers.</span></span> 
  

