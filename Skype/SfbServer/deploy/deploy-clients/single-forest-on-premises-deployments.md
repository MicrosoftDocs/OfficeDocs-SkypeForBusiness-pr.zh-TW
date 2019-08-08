---
title: Skype 會議室系統單一林內部部署
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: 若要瞭解如何在單一目錄林內部部署環境中部署 Skype 會議室系統, 請閱讀本主題。
ms.openlocfilehash: 107d4724defa11cbe506dcfa1b4f3c4725ee9910
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245865"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a><span data-ttu-id="0c0ac-103">Skype 會議室系統單一林內部部署</span><span class="sxs-lookup"><span data-stu-id="0c0ac-103">Skype Room System single forest on-premises deployments</span></span>
 
<span data-ttu-id="0c0ac-104">若要瞭解如何在單一目錄林內部部署環境中部署 Skype 會議室系統, 請閱讀本主題。</span><span class="sxs-lookup"><span data-stu-id="0c0ac-104">Read this topic to learn how to deploy Skype Room System in a single forest on-premises environment.</span></span>
  
<span data-ttu-id="0c0ac-105">本節概述在 Exchange Server 上提供 Skype 室系統帳戶的步驟, 以及在單一目錄林內部部署中託管的商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="0c0ac-105">This section provides an overview of the steps for provisioning the Skype Room System account on Exchange Server and Skype for Business Server hosted in a single forest on-premises deployment.</span></span>
  
## <a name="single-forest-on-premises-deployments"></a><span data-ttu-id="0c0ac-106">單一目錄林內部部署</span><span class="sxs-lookup"><span data-stu-id="0c0ac-106">Single forest on-premises deployments</span></span>

<span data-ttu-id="0c0ac-107">如果您已經有會議室的資源信箱, 可以使用該帳戶。</span><span class="sxs-lookup"><span data-stu-id="0c0ac-107">If you already have a resource mailbox account for the conferencing room, you can use it.</span></span> <span data-ttu-id="0c0ac-108">否則, 您將需要建立一個新的。</span><span class="sxs-lookup"><span data-stu-id="0c0ac-108">Otherwise, you will need to create a new one.</span></span> <span data-ttu-id="0c0ac-109">您可以使用 Exchange 管理命令介面 (PowerShell) 或 Exchange 管理主控台來建立新的資源信箱帳戶。</span><span class="sxs-lookup"><span data-stu-id="0c0ac-109">You can use either Exchange Management Shell (PowerShell) or Exchange Management Console to create a new resource mailbox account.</span></span> <span data-ttu-id="0c0ac-110">我們建議您使用新的 (刪除舊信箱, 並重新建立) Skype 會議室系統資源信箱。</span><span class="sxs-lookup"><span data-stu-id="0c0ac-110">We recommend using a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="0c0ac-111">請務必先備份信箱資料, 然後再將其匯出為使用 Outlook 用戶端重新建立的信箱 (如需詳細資訊, 請參閱匯出或備份郵件、行事曆、工作及連絡人)。</span><span class="sxs-lookup"><span data-stu-id="0c0ac-111">Make sure to back up mailbox data before deleting and then export it back to the re-created mailbox using the Outlook client (see Export or back up messages, calendar, tasks, and contacts for more information).</span></span> <span data-ttu-id="0c0ac-112">若要透過刪除信箱來還原遺失的會議, 請參閱[連接或還原已刪除的信箱](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0c0ac-112">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="0c0ac-113">若要使用現有的資源信箱帳戶 (例如, LRS-01), 請遵循下列步驟:</span><span class="sxs-lookup"><span data-stu-id="0c0ac-113">To use an existing resource mailbox account (for example, LRS-01) follow the steps below:</span></span>
  
1. <span data-ttu-id="0c0ac-114">執行下列 Exchange 管理 PowerShell 命令:</span><span class="sxs-lookup"><span data-stu-id="0c0ac-114">Run the following Exchange Management PowerShell command:</span></span>
    
   ```
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. <span data-ttu-id="0c0ac-115">如果您打算建立新的信箱, 請針對單一的林內部部署 Exchange 組織, 執行下列命令:</span><span class="sxs-lookup"><span data-stu-id="0c0ac-115">If you plan to create a new mailbox, then, for a single forest on-premises Exchange organization, run the following command:</span></span>
    
   ```
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   <span data-ttu-id="0c0ac-116">上述範例會在 Active Directory 中建立已啟用的使用者帳戶, 以及內部部署 Exchange 組織中會議室的會議室信箱。</span><span class="sxs-lookup"><span data-stu-id="0c0ac-116">The above example creates an enabled user account in Active Directory and a room mailbox for a conference room in an on-premises Exchange organization.</span></span> <span data-ttu-id="0c0ac-117">RoomMailboxPassword 參數會指定使用者帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="0c0ac-117">The RoomMailboxPassword parameter specifies the password for the user account.</span></span>
    
3. <span data-ttu-id="0c0ac-118">將帳戶設定為透過接受/拒絕會議來自動解決衝突。</span><span class="sxs-lookup"><span data-stu-id="0c0ac-118">Configure the account to automatically resolve conflicts by accepting/rejecting meetings.</span></span> <span data-ttu-id="0c0ac-119">Exchange 中的 Skype 會議室系統隨附的會議室帳戶可由個人管理, 但請注意, 直到個別人接受會議時, 才會顯示在 Skype 會議室系統的主畫面行事曆上。</span><span class="sxs-lookup"><span data-stu-id="0c0ac-119">Skype Room System-equipped conference room accounts in Exchange can be managed by individuals, but note that until the individual accepts a meeting it will not appear on the Skype Room System home screen calendar.</span></span>
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   <span data-ttu-id="0c0ac-120">如需可用的完整命令集, 請參閱設定 CalendarProcessing。</span><span class="sxs-lookup"><span data-stu-id="0c0ac-120">For a complete set of commands available, see Set-CalendarProcessing.</span></span>
    
   <span data-ttu-id="0c0ac-121">若要提醒會議召集人在 Outlook 中讓會議成為線上商務用 Skype 會議, 請執行下列命令來設定新帳戶的寄件提醒:</span><span class="sxs-lookup"><span data-stu-id="0c0ac-121">To remind meeting organizers to make the meeting an online Skype for Business meeting in Outlook, run the following command to set up a MailTip for the new account:</span></span> 
    
   ```
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. <span data-ttu-id="0c0ac-122">使用下列命令來設定當地語系化的字串。</span><span class="sxs-lookup"><span data-stu-id="0c0ac-122">Use the following commands to configure localized strings.</span></span> <span data-ttu-id="0c0ac-123">如果您的組織需要, 您也可以新增自訂翻譯:</span><span class="sxs-lookup"><span data-stu-id="0c0ac-123">If required by your organization, you can also add custom translations:</span></span> 
   ```
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. <span data-ttu-id="0c0ac-124">[選用]: 設定會議接受文字, 為使用者供應商務用 Skype 會議室的相關資訊, 以及在排程及加入會議時預期的情況。</span><span class="sxs-lookup"><span data-stu-id="0c0ac-124">Optional: Configure meeting acceptance text that provides users with information about Skype for Business Meeting Room, and what to expect when they schedule and join meetings.</span></span> 
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a><span data-ttu-id="0c0ac-125">檢查 Active Directory 中的資源信箱帳戶</span><span class="sxs-lookup"><span data-stu-id="0c0ac-125">Check Resource Mailbox Account in Active Directory</span></span>

<span data-ttu-id="0c0ac-126">上述步驟1中由 Exchange 所建立的會議室信箱帳戶可能是 Active Directory 中已停用的使用者物件。</span><span class="sxs-lookup"><span data-stu-id="0c0ac-126">The conference room mailbox account created by Exchange in step 1 above might be a disabled user object in Active Directory.</span></span> <span data-ttu-id="0c0ac-127">如果 Active Directory 中的帳戶已停用, Skype 會議室系統就無法使用 Kerberos/NTLM 驗證登入或進行驗證。</span><span class="sxs-lookup"><span data-stu-id="0c0ac-127">Skype Room System cannot sign in or authenticate by using Kerberos/NTLM authentication if the account is disabled in Active Directory.</span></span> <span data-ttu-id="0c0ac-128">Skype 聊天室系統用戶端必須能夠針對 Exchange Web 服務進行驗證, 以取得行事曆設定, 而且也必須能夠使用白板內容傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="0c0ac-128">The Skype Room System client must be able to authenticate against Exchange Web Services to retrieve calendar settings, and must also be able to send email with whiteboard contents.</span></span> 
  
<span data-ttu-id="0c0ac-129">因此, 如果帳戶已停用, 您必須執行下列動作, 才能在 Active Directory 中啟用這個帳戶:</span><span class="sxs-lookup"><span data-stu-id="0c0ac-129">Therefore, if the account is disabled, you must enable this account in Active Directory by doing the following:</span></span> 
  
1. <span data-ttu-id="0c0ac-130">在 Active Directory 中, 執行下列命令以啟用帳戶登入:</span><span class="sxs-lookup"><span data-stu-id="0c0ac-130">In Active Directory, run the following command to enable account log on:</span></span> 
    
   ```
   Set-ADAccountPassword -Identity LRS01
   ```

   <span data-ttu-id="0c0ac-131">執行此命令時, 系統會提示您輸入目前的密碼, 然後重新輸入密碼兩次以進行確認。</span><span class="sxs-lookup"><span data-stu-id="0c0ac-131">Running this command will prompt you to enter the current password, and then to re-enter the password twice for confirmation.</span></span>
    
2. <span data-ttu-id="0c0ac-132">設定密碼之後, 請執行下列命令以啟用帳戶:</span><span class="sxs-lookup"><span data-stu-id="0c0ac-132">Once the password is set, run the following command to enable the account:</span></span> 
    
   ```
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a><span data-ttu-id="0c0ac-133">啟用商務用 Skype 的 Skype 會議室系統帳戶</span><span class="sxs-lookup"><span data-stu-id="0c0ac-133">Enabling Skype Room System Accounts for Skype for Business</span></span>

<span data-ttu-id="0c0ac-134">本節概述針對您的會議室帳戶啟用商務用 Skype 所需的步驟, 將會在 Skype 會議室系統上設定。</span><span class="sxs-lookup"><span data-stu-id="0c0ac-134">This section provides an overview of the steps required to enable Skype for Business for your conference room account, which will be configured on Skype Room System.</span></span> 
  
<span data-ttu-id="0c0ac-135">在您為會議室建立資源信箱帳戶之後, 請使用商務用 Skype Server Management Shell 來啟用商務用 Skype 服務的 Skype 會議室系統帳戶。</span><span class="sxs-lookup"><span data-stu-id="0c0ac-135">After you create a resource mailbox account for the conferencing rooms, use Skype for Business Server Management Shell to enable Skype Room System accounts for Skype for Business services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0c0ac-136">下列程式假設您已在 Active Directory 中啟用 Skype 會議室系統帳戶。</span><span class="sxs-lookup"><span data-stu-id="0c0ac-136">The following procedure assumes that you have enabled the Skype Room System account in Active Directory.</span></span> 
  
1. <span data-ttu-id="0c0ac-137">執行下列命令, 在商務用 Skype 伺服器池中啟用 Skype 會議室系統帳戶:</span><span class="sxs-lookup"><span data-stu-id="0c0ac-137">Run the following command to enable the Skype Room System account on a Skype for Business Server pool:</span></span>
    
   ```
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. <span data-ttu-id="0c0ac-138">[選用]: 允許此帳戶透過啟用企業語音帳戶來撥打和接聽 PSTN 電話。</span><span class="sxs-lookup"><span data-stu-id="0c0ac-138">Optional: Allow this account to make and receive PSTN phone calls by enabling the account for Enterprise Voice.</span></span> <span data-ttu-id="0c0ac-139">Skype 室系統不需要企業版語音, 但如果您不啟用企業語音, Skype 聊天室系統用戶端將無法提供 PSTN 撥號功能:</span><span class="sxs-lookup"><span data-stu-id="0c0ac-139">Enterprise Voice is not required for Skype Room System, but if you do not enable it for Enterprise Voice, the Skype Room System client won't be able to provide PSTN dialing functionality:</span></span>
    
   ```
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="0c0ac-140">如果您為 Skype 會議室系統會議室帳戶啟用企業版語音, 請務必設定適合您組織的受限制語音原則。</span><span class="sxs-lookup"><span data-stu-id="0c0ac-140">If you enable Enterprise Voice for the Skype Room System conference room account, make sure to configure a restricted Voice Policy suitable for your organization.</span></span> <span data-ttu-id="0c0ac-141">如果商務用 Skype 會議室是公開提供的資源, 任何人都可以使用它來加入會議 (無論是排程的或點對點的)。</span><span class="sxs-lookup"><span data-stu-id="0c0ac-141">If the Skype for Business Meeting Room is a publicly available resource, anyone could use it to join a meeting, either scheduled or ad hoc.</span></span> <span data-ttu-id="0c0ac-142">加入會議之後, 該人員就可以撥出任何號碼。</span><span class="sxs-lookup"><span data-stu-id="0c0ac-142">After joining a meeting, the person could dial out to any number.</span></span> <span data-ttu-id="0c0ac-143">在商務用 Skype Server 中, 「從會議撥出」功能會使用使用者的語音原則, 在此案例中, 用來加入會議的 Skype 房間系統帳戶。</span><span class="sxs-lookup"><span data-stu-id="0c0ac-143">In Skype for Business Server, the dial-out from conferences feature uses the voice policy of the user, in this case the Skype Room System account used to join the meeting.</span></span> <span data-ttu-id="0c0ac-144">在舊版的 Lync Server 中, 會使用召集人的語音原則。</span><span class="sxs-lookup"><span data-stu-id="0c0ac-144">In earlier versions of Lync Server, the voice policy of the organizer is used.</span></span> <span data-ttu-id="0c0ac-145">因此, 如果舊版 Lync Server 的使用者排程會議室, 並邀請 Skype 會議室系統房間帳戶, 任何人都可以使用商務用 Skype 會議室加入會議, 而且可以撥打電話給任何國家/地區或國際電話[數位], 只要允許召集人撥打這些號碼即可。</span><span class="sxs-lookup"><span data-stu-id="0c0ac-145">Therefore, if a user of an earlier version of Lync Server schedules a meeting room and invites the Skype Room System room account, anyone could use the Skype for Business Meeting Room to join the meeting and could dial any national/regional or international phone number, as long as the organizer is allowed to dial those numbers.</span></span> 
  

