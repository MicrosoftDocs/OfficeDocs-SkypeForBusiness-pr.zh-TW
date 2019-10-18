---
title: 虛擬化桌面基礎結構的團隊
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi
audience: admin
description: 瞭解如何在虛擬化桌面基礎結構（VDI）環境中執行 Microsoft 團隊。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4fa560347d7263dafafc4f98e031b3b267f8fb12
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570220"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="99c5b-103">虛擬化桌面基礎結構的團隊</span><span class="sxs-lookup"><span data-stu-id="99c5b-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="99c5b-104">本文將說明在虛擬化環境中使用 Microsoft 團隊的需求與限制。</span><span class="sxs-lookup"><span data-stu-id="99c5b-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="99c5b-105">什麼是 VDI？</span><span class="sxs-lookup"><span data-stu-id="99c5b-105">What is VDI?</span></span>

<span data-ttu-id="99c5b-106">虛擬桌面基礎結構（VDI）是虛擬化技術，可在資料中心的中央伺服器上託管桌面作業系統和應用程式。</span><span class="sxs-lookup"><span data-stu-id="99c5b-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="99c5b-107">這可讓使用者具備完全安全且相容的集中來源，為使用者提供完整的個人化桌面體驗。</span><span class="sxs-lookup"><span data-stu-id="99c5b-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span> 
 
<span data-ttu-id="99c5b-108">目前，虛擬化環境中的團隊可與專用的永久性虛擬化電腦（VM）共同提供共同作業和聊天功能的支援。</span><span class="sxs-lookup"><span data-stu-id="99c5b-108">Currently, Teams in a virtualized environment is available with support for collaboration and chat functionality with a dedicated persistent virtualized machine (VM).</span></span> <span data-ttu-id="99c5b-109">若要確保最佳的使用者體驗，請遵循本文中的指導方針。</span><span class="sxs-lookup"><span data-stu-id="99c5b-109">To ensure an optimal user experience, follow the guidance in this article.</span></span> 

## <a name="teams-requirements"></a><span data-ttu-id="99c5b-110">團隊需求</span><span class="sxs-lookup"><span data-stu-id="99c5b-110">Teams requirements</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality-in-teams"></a><span data-ttu-id="99c5b-111">設定原則以關閉小組中的通話與會議功能</span><span class="sxs-lookup"><span data-stu-id="99c5b-111">Set policies to turn off calling and meeting functionality in Teams</span></span>

<span data-ttu-id="99c5b-112">小組通話和會議體驗未針對 VDI 環境優化（即將推出）。</span><span class="sxs-lookup"><span data-stu-id="99c5b-112">The Teams calling and meeting experience isn't optimized for a VDI environment (coming soon).</span></span> <span data-ttu-id="99c5b-113">我們建議您設定使用者層級原則，以關閉小組中的通話與會議功能。</span><span class="sxs-lookup"><span data-stu-id="99c5b-113">We recommend you set user-level policies to turn off calling and meeting functionality in Teams.</span></span>

<span data-ttu-id="99c5b-114">您仍然可以使用小組桌面應用程式或 web 應用程式，選擇在 VDI 中完全執行團隊。</span><span class="sxs-lookup"><span data-stu-id="99c5b-114">You can still choose to run Teams fully in VDI using either the Teams desktop app or web app.</span></span> <span data-ttu-id="99c5b-115">不過，建議您設定原則，以避免損害使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="99c5b-115">However, we recommend that you set the policies to avoid compromising the user experience.</span></span>  

<span data-ttu-id="99c5b-116">策略變更可能需要幾個時間（幾個小時）才能傳播。</span><span class="sxs-lookup"><span data-stu-id="99c5b-116">It can take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="99c5b-117">如果您沒有立即看到特定帳戶的變更，請在幾個小時後再試一次。</span><span class="sxs-lookup"><span data-stu-id="99c5b-117">If you don’t see changes for a given account immediately, try again in a few hours.</span></span>

> [!NOTE]
> <span data-ttu-id="99c5b-118">當團隊通話和會議已針對虛擬桌面環境中的使用進行優化時，您可以復原這些原則，並允許使用者使用小組做為自己的習慣。</span><span class="sxs-lookup"><span data-stu-id="99c5b-118">When Teams calling and meetings are optimized for use in virtual desktop environments, you can revert these policies and allow users to use Teams as they normally would.</span></span> 

#### <a name="calling"></a><span data-ttu-id="99c5b-119">通話</span><span class="sxs-lookup"><span data-stu-id="99c5b-119">Calling</span></span>

<span data-ttu-id="99c5b-120">使用**CSTeamsCallingPolicy** Cmdlet 來控制是否允許使用者在私人和群組聊天中使用呼叫和呼叫選項。</span><span class="sxs-lookup"><span data-stu-id="99c5b-120">Use the **CSTeamsCallingPolicy** cmdlets to control whether users are allowed to use calling and calling options in private and group chats.</span></span> <span data-ttu-id="99c5b-121">以下是原則設定及建議值的清單。</span><span class="sxs-lookup"><span data-stu-id="99c5b-121">Here's the list of policy settings and recommended values.</span></span>

|<span data-ttu-id="99c5b-122">原則名稱</span><span class="sxs-lookup"><span data-stu-id="99c5b-122">Policy name</span></span>  |<span data-ttu-id="99c5b-123">說明</span><span class="sxs-lookup"><span data-stu-id="99c5b-123">Description</span></span> |<span data-ttu-id="99c5b-124">建議值</span><span class="sxs-lookup"><span data-stu-id="99c5b-124">Recommended value</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="99c5b-125">AllowCalling</span><span class="sxs-lookup"><span data-stu-id="99c5b-125">AllowCalling</span></span>    |<span data-ttu-id="99c5b-126">控制交互操作通話功能。</span><span class="sxs-lookup"><span data-stu-id="99c5b-126">Controls interop calling capabilities.</span></span> <span data-ttu-id="99c5b-127">開啟這項功能後，商務用 Skype 使用者就能與團隊使用者進行一對一通話（反之亦然）。</span><span class="sxs-lookup"><span data-stu-id="99c5b-127">Turning this on allows Skype for Business users to have one-on-one calls with Teams users and vice versa.</span></span>         |<span data-ttu-id="99c5b-128">設定為 False，以避免從商務用 Skype 使用者撥打電話給小組。</span><span class="sxs-lookup"><span data-stu-id="99c5b-128">Set to False to prevent calls from Skype for Business users landing in Teams.</span></span>          |
|<span data-ttu-id="99c5b-129">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="99c5b-129">AllowPrivateCalling</span></span>     | <span data-ttu-id="99c5b-130">控制是否在團隊用戶端左側的應用程式行中提供通話應用程式，以及使用者是否在私人聊天中看到通話和視頻通話選項</span><span class="sxs-lookup"><span data-stu-id="99c5b-130">Controls whether the Calling app is available in the app bar on the left side of the Teams client and whether users see Calling and Video call options in private chat</span></span>         |<span data-ttu-id="99c5b-131">設為 False，即可從小組左側的應用程式行中移除通話應用程式，以及移除 [私人聊天] 中的 [通話] 和 [視頻通話] 選項。</span><span class="sxs-lookup"><span data-stu-id="99c5b-131">Set to False to remove the Calling app from the app bar on the left side of Teams and to remove the Calling and Video call options in private chat.</span></span>          |

#### <a name="create-and-assign-a-calling-policy"></a><span data-ttu-id="99c5b-132">建立並指派通話原則</span><span class="sxs-lookup"><span data-stu-id="99c5b-132">Create and assign a calling policy</span></span>

1. <span data-ttu-id="99c5b-133">以系統管理員身分啟動 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="99c5b-133">Start a Windows PowerShell session as an administrator.</span></span>
2. <span data-ttu-id="99c5b-134">連線至 [Skype Online 連接器]。</span><span class="sxs-lookup"><span data-stu-id="99c5b-134">Connect to the Skype Online Connector.</span></span>

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. <span data-ttu-id="99c5b-135">查看通話原則選項的清單。</span><span class="sxs-lookup"><span data-stu-id="99c5b-135">View a list of calling policy options.</span></span>

       Get-CsTeamsCallingPolicy
 
4. <span data-ttu-id="99c5b-136">尋找已停用所有通話原則的內建原則選項。</span><span class="sxs-lookup"><span data-stu-id="99c5b-136">Look for the built-in policy option where all calling policies are disabled.</span></span> <span data-ttu-id="99c5b-137">它看起來像這樣。</span><span class="sxs-lookup"><span data-stu-id="99c5b-137">It looks like this.</span></span>
   
        Identity                        : Tag:DisallowCalling
        AllowCalling                    : False
        AllowPrivateCalling             : False
        AllowVoicemail                  : False
        AllowCallGroups                 : False
        AllowDelegation                 : False
        AllowUserControl                : False
        AllowCallForwardingToUser       : False
        AllowCallForwardingToPhone      : False
        PreventTollBypass               : False

5. <span data-ttu-id="99c5b-138">將 DisallowCalling 內建原則選項套用至將在虛擬化環境中使用團隊的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="99c5b-138">Apply the DisallowCalling built-in policy option to all users who will be using Teams in a virtualized environment.</span></span>

        Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”

<span data-ttu-id="99c5b-139">如需團隊通話原則的詳細資訊，請參閱[設定 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="99c5b-139">For more information about Teams calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

#### <a name="meetings"></a><span data-ttu-id="99c5b-140">舉行</span><span class="sxs-lookup"><span data-stu-id="99c5b-140">Meetings</span></span>

<span data-ttu-id="99c5b-141">使用**CsTeamsMeetingPolicy** Cmdlet 來控制使用者可以建立的會議類型、在會議中可存取的功能，以及匿名及外部使用者可以使用的會議功能。</span><span class="sxs-lookup"><span data-stu-id="99c5b-141">Use the **CsTeamsMeetingPolicy** cmdlets to control the type of meetings that users can create, the features that they can access while in a meeting, and the meeting features that are available to anonymous and external users.</span></span> <span data-ttu-id="99c5b-142">以下是原則設定及建議值的清單。</span><span class="sxs-lookup"><span data-stu-id="99c5b-142">Here's the list of policy settings and recommended values.</span></span>

|<span data-ttu-id="99c5b-143">原則名稱</span><span class="sxs-lookup"><span data-stu-id="99c5b-143">Policy Name</span></span> |<span data-ttu-id="99c5b-144">說明</span><span class="sxs-lookup"><span data-stu-id="99c5b-144">Description</span></span>|<span data-ttu-id="99c5b-145">建議值</span><span class="sxs-lookup"><span data-stu-id="99c5b-145">Recommended Value</span></span>                   |
|-------------------|-----------------|-----------------------|
|<span data-ttu-id="99c5b-146">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="99c5b-146">AllowPrivateMeetingScheduling</span></span>  | <span data-ttu-id="99c5b-147">判斷是否允許使用者排程私人會議。</span><span class="sxs-lookup"><span data-stu-id="99c5b-147">Determines whether a user is allowed to schedule private meetings.</span></span>| <span data-ttu-id="99c5b-148">設為 False，禁止使用者排程私人會議。</span><span class="sxs-lookup"><span data-stu-id="99c5b-148">Set to False to prohibit the user from being able to schedule private meetings.</span></span>  |
|<span data-ttu-id="99c5b-149">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="99c5b-149">AllowChannelMeetingScheduling</span></span>  | <span data-ttu-id="99c5b-150">判斷是否允許使用者排程頻道會議。</span><span class="sxs-lookup"><span data-stu-id="99c5b-150">Determines whether a user is allowed to schedule channel meetings.</span></span> | <span data-ttu-id="99c5b-151">設為 False，禁止使用者排程頻道會議。</span><span class="sxs-lookup"><span data-stu-id="99c5b-151">Set to False to prohibit the user from being able to schedule channel meetings.</span></span>                       |
|<span data-ttu-id="99c5b-152">AllowMeetNow</span><span class="sxs-lookup"><span data-stu-id="99c5b-152">AllowMeetNow</span></span> |<span data-ttu-id="99c5b-153">判斷是否允許使用者建立或啟動臨時會議。</span><span class="sxs-lookup"><span data-stu-id="99c5b-153">Determines whether a user is allowed to create or start ad-hoc meetings.</span></span>              |  <span data-ttu-id="99c5b-154">將此值設定為 False，禁止使用者啟動即席會議。</span><span class="sxs-lookup"><span data-stu-id="99c5b-154">Set this to False to prohibit the user from being able to start ad-hoc meetings.</span></span>                     |
|<span data-ttu-id="99c5b-155">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="99c5b-155">ScreenSharingMode</span></span> | <span data-ttu-id="99c5b-156">決定允許使用者在通話或會議中共用其螢幕的模式。</span><span class="sxs-lookup"><span data-stu-id="99c5b-156">Determines the mode in which a user is allowed to share their screen in calls or meetings.</span></span> | <span data-ttu-id="99c5b-157">設為 [停用] 以禁止使用者共用其畫面</span><span class="sxs-lookup"><span data-stu-id="99c5b-157">Set to Disabled to prohibit the user from sharing their screens</span></span>                          |
|<span data-ttu-id="99c5b-158">AllowIPVideo</span><span class="sxs-lookup"><span data-stu-id="99c5b-158">AllowIPVideo</span></span> |<span data-ttu-id="99c5b-159">決定是否在使用者的會議或通話中啟用影片。</span><span class="sxs-lookup"><span data-stu-id="99c5b-159">Determines whether video is enabled in a user's meetings or calls.</span></span>                  |    <span data-ttu-id="99c5b-160">設為 False 以禁止使用者共用影片</span><span class="sxs-lookup"><span data-stu-id="99c5b-160">Set to False to prohibit the user from sharing their video</span></span>                                         |
| <span data-ttu-id="99c5b-161">AllowAnonymousUsersToDialOut</span><span class="sxs-lookup"><span data-stu-id="99c5b-161">AllowAnonymousUsersToDialOut</span></span> | <span data-ttu-id="99c5b-162">判斷是否允許匿名使用者撥出 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="99c5b-162">Determines whether anonymous users are allowed to dial out to a PSTN number.</span></span> | <span data-ttu-id="99c5b-163">設為 False 以禁止匿名使用者撥出</span><span class="sxs-lookup"><span data-stu-id="99c5b-163">Set to False to prohibit anonymous users from dialing out</span></span>                                  |
| <span data-ttu-id="99c5b-164">AllowAnonymousUsersToStartMeeting</span><span class="sxs-lookup"><span data-stu-id="99c5b-164">AllowAnonymousUsersToStartMeeting</span></span> | <span data-ttu-id="99c5b-165">判斷匿名使用者是否可以開始會議。</span><span class="sxs-lookup"><span data-stu-id="99c5b-165">Determines whether anonymous users can start a meeting.</span></span>     |  <span data-ttu-id="99c5b-166">設為 False 以禁止使用者開始會議</span><span class="sxs-lookup"><span data-stu-id="99c5b-166">Set to False to prohibit users from starting a meeting</span></span>                                            |
| <span data-ttu-id="99c5b-167">AllowOutlookAddIn</span><span class="sxs-lookup"><span data-stu-id="99c5b-167">AllowOutlookAddIn</span></span> |<span data-ttu-id="99c5b-168">決定使用者是否可以在 Outlook 桌面用戶端中排程團隊會議。</span><span class="sxs-lookup"><span data-stu-id="99c5b-168">Determines whether a user can schedule Teams meetings in the Outlook desktop client.</span></span>| <span data-ttu-id="99c5b-169">在 Outlook 桌面用戶端中設定為 False 以禁止使用者排程團隊會議</span><span class="sxs-lookup"><span data-stu-id="99c5b-169">Set to False to prohibit a user from  scheduling Teams meetings in the Outlook desktop client</span></span>|
| <span data-ttu-id="99c5b-170">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="99c5b-170">AllowParticipantGiveRequestControl</span></span>|<span data-ttu-id="99c5b-171">決定參與者是否可以要求或授與螢幕共用的控制權。</span><span class="sxs-lookup"><span data-stu-id="99c5b-171">Determines whether participants can request or give control of screen sharing.</span></span>| <span data-ttu-id="99c5b-172">設為 False 以禁止使用者在會議中授與要求控制權</span><span class="sxs-lookup"><span data-stu-id="99c5b-172">Set to False to prohibit the user from giving and requesting control in a meeting</span></span>    |
| <span data-ttu-id="99c5b-173">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="99c5b-173">AllowExternalParticipantGiveRequestControl</span></span> | <span data-ttu-id="99c5b-174">決定外部參與者是否可以要求或授與螢幕共用的控制權。</span><span class="sxs-lookup"><span data-stu-id="99c5b-174">Determines whether external participants can request or give control of screen sharing.</span></span>| <span data-ttu-id="99c5b-175">設為 False 以禁止外部使用者授與，要求在會議中進行控制</span><span class="sxs-lookup"><span data-stu-id="99c5b-175">Set to False to prohibit an external user from giving, requesting control in a meeting</span></span>|
|<span data-ttu-id="99c5b-176">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="99c5b-176">AllowPowerPointSharing</span></span>|<span data-ttu-id="99c5b-177">決定是否允許在使用者的會議中共用 PowerPoint。</span><span class="sxs-lookup"><span data-stu-id="99c5b-177">Determines whether PowerPoint sharing is allowed in a user’s meetings.</span></span> |<span data-ttu-id="99c5b-178">設為 False 以禁止使用者在會議中共用 PowerPoint 檔案</span><span class="sxs-lookup"><span data-stu-id="99c5b-178">Set to False to prohibit a user from sharing PowerPoint files in a meeting</span></span>  |
|<span data-ttu-id="99c5b-179">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="99c5b-179">AllowWhiteboard</span></span> | <span data-ttu-id="99c5b-180">判斷使用者的會議是否允許使用白板。</span><span class="sxs-lookup"><span data-stu-id="99c5b-180">Determines whether whiteboard is allowed in a user’s meetings.</span></span> |   <span data-ttu-id="99c5b-181">在會議中設定為 False 以禁止白板</span><span class="sxs-lookup"><span data-stu-id="99c5b-181">Set to False to prohibit whiteboard in a meeting</span></span> |
| <span data-ttu-id="99c5b-182">AllowTranscription</span><span class="sxs-lookup"><span data-stu-id="99c5b-182">AllowTranscription</span></span> |<span data-ttu-id="99c5b-183">判斷在使用者的會議中是否允許即時及/或會議後的標題和 transcriptions。</span><span class="sxs-lookup"><span data-stu-id="99c5b-183">Determines whether real-time and/or post-meeting captions and transcriptions are allowed in a user's meetings.</span></span>|    <span data-ttu-id="99c5b-184">設為 False 以禁止會議中的 [文字] 與 [標題]</span><span class="sxs-lookup"><span data-stu-id="99c5b-184">Set to False to prohibit transcription  and captions in a meeting</span></span>  |  
| <span data-ttu-id="99c5b-185">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="99c5b-185">AllowSharedNotes</span></span> | <span data-ttu-id="99c5b-186">決定是否允許使用者拍共用筆記。</span><span class="sxs-lookup"><span data-stu-id="99c5b-186">Determines whether users are allowed to take shared notes.</span></span> | <span data-ttu-id="99c5b-187">設為 False 以禁止使用者記錄共用筆記</span><span class="sxs-lookup"><span data-stu-id="99c5b-187">Set to False to prohibit users from taking shared notes</span></span> |
|<span data-ttu-id="99c5b-188">MediaBitRateKB</span><span class="sxs-lookup"><span data-stu-id="99c5b-188">MediaBitRateKB</span></span> |<span data-ttu-id="99c5b-189">決定會議中音訊/視頻/app 共用傳輸的媒體位元速率</span><span class="sxs-lookup"><span data-stu-id="99c5b-189">Determines the media bit rate for audio/video/app sharing transmissions in meetings</span></span>  | <span data-ttu-id="99c5b-190">建議的值為5000（5 MB）。</span><span class="sxs-lookup"><span data-stu-id="99c5b-190">Suggested value is 5000 (5 MB).</span></span> <span data-ttu-id="99c5b-191">您可以根據組織的需求變更它。</span><span class="sxs-lookup"><span data-stu-id="99c5b-191">You can change it based on your organization’s needs.</span></span>| 

#### <a name="create-and-assign-a-meeting-policy"></a><span data-ttu-id="99c5b-192">建立並指派會議原則</span><span class="sxs-lookup"><span data-stu-id="99c5b-192">Create and assign a meeting policy</span></span>

1. <span data-ttu-id="99c5b-193">以系統管理員身分啟動 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="99c5b-193">Start a Windows PowerShell session as an administrator.</span></span>
2. <span data-ttu-id="99c5b-194">連線至 [Skype Online 連接器]。</span><span class="sxs-lookup"><span data-stu-id="99c5b-194">Connect to the Skype Online Connector.</span></span>

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. <span data-ttu-id="99c5b-195">查看會議原則選項的清單。</span><span class="sxs-lookup"><span data-stu-id="99c5b-195">View a list of meeting policy options.</span></span>

       Get-CsTeamsMeetingPolicy
 
4. <span data-ttu-id="99c5b-196">尋找已停用所有會議原則的內建原則選項。</span><span class="sxs-lookup"><span data-stu-id="99c5b-196">Look for the built-in policy option where all meeting policies are disabled.</span></span> <span data-ttu-id="99c5b-197">它看起來像這樣。</span><span class="sxs-lookup"><span data-stu-id="99c5b-197">It looks like this.</span></span>
   
        Identity                                    : Tag:AllOff
        Description                                 :
        AllowChannelMeetingScheduling               : False
        AllowMeetNow                                : False
        AllowIPVideo                                : False
        AllowAnonymousUsersToDialOut                : False
        AllowAnonymousUsersToStartMeeting           : False
        AllowPrivateMeetingScheduling               : False
        AutoAdmittedUsers                           : False
        AllowCloudRecording                         : False
        AllowOutlookAddIn                           : False
        AllowPowerPointSharing                      : False
        AllowParticipantGiveRequestControl          : False
        AllowExternalParticipantGiveRequestControl  : False
        AllowSharedNotes                            : False
        AllowWhiteboard                             : False
        AllowTranscription                          : False
        MediaBitRateKb                              : False
        ScreenSharingMode                           : False

5. <span data-ttu-id="99c5b-198">將 AllOff 內建原則選項套用至將在虛擬化環境中使用團隊的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="99c5b-198">Apply the AllOff built-in policy option to all users who will be using Teams in a virtualized environment.</span></span> 

        Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”

 <span data-ttu-id="99c5b-199">如需團隊會議原則的詳細資訊，請參閱[設定 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="99c5b-199">For more information about Teams meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="99c5b-200">虛擬化提供者需求</span><span class="sxs-lookup"><span data-stu-id="99c5b-200">Virtualization provider requirements</span></span>

<span data-ttu-id="99c5b-201">團隊 app 已在主要的虛擬化解決方案提供者上驗證。</span><span class="sxs-lookup"><span data-stu-id="99c5b-201">The Teams app has been validated on leading virtualization solution providers.</span></span> <span data-ttu-id="99c5b-202">有了多個市場供應商，請諮詢您的虛擬化解決方案供應商，以確保符合最低需求。</span><span class="sxs-lookup"><span data-stu-id="99c5b-202">With multiple market providers, consult your virtualization solution provider to ensure minimum requirements are met.</span></span>

### <a name="virtual-machine-requirements"></a><span data-ttu-id="99c5b-203">虛擬機器需求</span><span class="sxs-lookup"><span data-stu-id="99c5b-203">Virtual Machine requirements</span></span>

<span data-ttu-id="99c5b-204">在虛擬化環境中，有各種不同的工作負載和使用者需求，以下是建議的最低 VM 配置。</span><span class="sxs-lookup"><span data-stu-id="99c5b-204">With the diverse workloads and user needs in a virtualized environment, the following is the minimum recommended VM configuration.</span></span>

|<span data-ttu-id="99c5b-205">參數</span><span class="sxs-lookup"><span data-stu-id="99c5b-205">Parameter</span></span>  |<span data-ttu-id="99c5b-206">單位</span><span class="sxs-lookup"><span data-stu-id="99c5b-206">Measure</span></span>  |
|---------|---------|
|<span data-ttu-id="99c5b-207">vCPU</span><span class="sxs-lookup"><span data-stu-id="99c5b-207">vCPU</span></span>    |  <span data-ttu-id="99c5b-208">2個核心</span><span class="sxs-lookup"><span data-stu-id="99c5b-208">2 cores</span></span>       |
|<span data-ttu-id="99c5b-209">RAM</span><span class="sxs-lookup"><span data-stu-id="99c5b-209">RAM</span></span>     |  <span data-ttu-id="99c5b-210">4 GB</span><span class="sxs-lookup"><span data-stu-id="99c5b-210">4 GB</span></span>      |
|<span data-ttu-id="99c5b-211">容量</span><span class="sxs-lookup"><span data-stu-id="99c5b-211">Storage</span></span>     | <span data-ttu-id="99c5b-212">8 GB</span><span class="sxs-lookup"><span data-stu-id="99c5b-212">8 GB</span></span>       |

### <a name="virtual-machine-operating-system-requirements"></a><span data-ttu-id="99c5b-213">虛擬機器作業系統需求</span><span class="sxs-lookup"><span data-stu-id="99c5b-213">Virtual Machine operating system requirements</span></span>

<span data-ttu-id="99c5b-214">VM 支援的作業系統如下：</span><span class="sxs-lookup"><span data-stu-id="99c5b-214">The supported operating systems for VM are:</span></span>

- <span data-ttu-id="99c5b-215">Windows 10 及更新版本</span><span class="sxs-lookup"><span data-stu-id="99c5b-215">Windows 10 and later</span></span>
- <span data-ttu-id="99c5b-216">Windows Server 2012 R2 及更新版本</span><span class="sxs-lookup"><span data-stu-id="99c5b-216">Windows Server 2012 R2 and later</span></span>

## <a name="install-teams-on-vdi"></a><span data-ttu-id="99c5b-217">在 VDI 上安裝團隊</span><span class="sxs-lookup"><span data-stu-id="99c5b-217">Install Teams on VDI</span></span>

<span data-ttu-id="99c5b-218">以下是部署團隊桌面應用程式的程式和工具。</span><span class="sxs-lookup"><span data-stu-id="99c5b-218">Here's the process and tools to deploy the Teams desktop app.</span></span> 

1. <span data-ttu-id="99c5b-219">根據環境，使用下列其中一個連結來下載團隊 MSI 套件。</span><span class="sxs-lookup"><span data-stu-id="99c5b-219">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="99c5b-220">我們建議使用64位作業系統的 VDI VM 64 位版本。</span><span class="sxs-lookup"><span data-stu-id="99c5b-220">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="99c5b-221">32位版本</span><span class="sxs-lookup"><span data-stu-id="99c5b-221">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="99c5b-222">64位版本</span><span class="sxs-lookup"><span data-stu-id="99c5b-222">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. <span data-ttu-id="99c5b-223">執行下列命令，將 MSI 安裝到 VDI VM （或完成更新）。</span><span class="sxs-lookup"><span data-stu-id="99c5b-223">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    <span data-ttu-id="99c5b-224">這會將小組安裝到程式檔。</span><span class="sxs-lookup"><span data-stu-id="99c5b-224">This installs Teams to Program Files.</span></span> <span data-ttu-id="99c5b-225">此時，黃金影像設定就完成了。</span><span class="sxs-lookup"><span data-stu-id="99c5b-225">At this point, the golden image setup is complete.</span></span>
 
    <span data-ttu-id="99c5b-226">下次互動式登入會話會啟動團隊並要求認證。</span><span class="sxs-lookup"><span data-stu-id="99c5b-226">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="99c5b-227">請注意，在 VDI 上使用 ALLUSER 屬性來安裝小組時，不可能停用自動啟動小組。</span><span class="sxs-lookup"><span data-stu-id="99c5b-227">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSER property.</span></span> 

3. <span data-ttu-id="99c5b-228">執行下列命令以從 VDI VM 卸載 MSI （或準備更新）。</span><span class="sxs-lookup"><span data-stu-id="99c5b-228">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    <span data-ttu-id="99c5b-229">這會從程式檔案中卸載小組。</span><span class="sxs-lookup"><span data-stu-id="99c5b-229">This uninstalls Teams from Program Files.</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="99c5b-230">已知問題與限制</span><span class="sxs-lookup"><span data-stu-id="99c5b-230">Known issues and limitations</span></span>

<span data-ttu-id="99c5b-231">下列是 VDI 上小組的已知問題與限制。</span><span class="sxs-lookup"><span data-stu-id="99c5b-231">The following are known issues and limitations for Teams on VDI.</span></span>

- <span data-ttu-id="99c5b-232">**共用工作階段主機類型部署**：共用工作階段主機類型部署（例如，共用非永久性 VM 設定）不在範圍內。</span><span class="sxs-lookup"><span data-stu-id="99c5b-232">**Shared session host type deployments**: Shared session host type deployments (for example, shared non-persistent VM configuration) aren't in scope.</span></span>
- <span data-ttu-id="99c5b-233">**通話與會議**：</span><span class="sxs-lookup"><span data-stu-id="99c5b-233">**Calling and meetings**:</span></span>

    - <span data-ttu-id="99c5b-234">通話和會議案例未針對 VDI 進行優化。</span><span class="sxs-lookup"><span data-stu-id="99c5b-234">Calling and meeting scenarios aren't optimized for VDI.</span></span> <span data-ttu-id="99c5b-235">這些案例的執行效果不佳。</span><span class="sxs-lookup"><span data-stu-id="99c5b-235">These scenarios will perform poorly.</span></span> <span data-ttu-id="99c5b-236">我們建議使用使用者層級原則，如在 [[團隊中關閉通話和會議功能](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams)] 區段中所述。</span><span class="sxs-lookup"><span data-stu-id="99c5b-236">We recommend using user-level policies as described in the [Set policies to turn off calling and meeting functionality in Teams](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) section.</span></span>  
    - <span data-ttu-id="99c5b-237">套用本文所述的原則，會影響使用通話與會議功能（視其他原則而定）可能會影響貴組織中的其他使用者。</span><span class="sxs-lookup"><span data-stu-id="99c5b-237">Applying the policies described in this article impacts the ability to use calling and meeting functionality, which depending on other policies, may affect other users in your organization.</span></span> <span data-ttu-id="99c5b-238">如果貴組織中的使用者使用非 VDI 用戶端，您可以選擇不套用原則。</span><span class="sxs-lookup"><span data-stu-id="99c5b-238">If users in your organization use non-VDI clients, you can choose to not apply the policies.</span></span>  

- <span data-ttu-id="99c5b-239">**加入由其他使用者所建立的通話與會議**：雖然原則限制使用者建立會議，但如果其他使用者從會議撥出會議，他們仍可加入會議。</span><span class="sxs-lookup"><span data-stu-id="99c5b-239">**Joining calls and meetings created by other users**: Although the policies restrict users from creating meetings, they can still join meetings if another user dials out to them from the meeting.</span></span> <span data-ttu-id="99c5b-240">在這些會議中，使用者共用影片的能力，使用白板和其他功能，取決於您是否使用 TeamsMeetingPolicy 停用這些功能。</span><span class="sxs-lookup"><span data-stu-id="99c5b-240">In these meetings, the user's ability to share video, use whiteboard and other features depend on whether you disabled those features using TeamsMeetingPolicy.</span></span>  
- <span data-ttu-id="99c5b-241">快取的**內容**：如果團隊在其中執行的虛擬環境不是持續性（在每個使用者會話結束時都會清除資料），使用者可能會發現內容重新整理導致效能下降，不論使用者是否存取相同前一個會話中的內容。</span><span class="sxs-lookup"><span data-stu-id="99c5b-241">**Cached content**: If the virtual environment in which Teams is running isn't persistent (and data is cleaned up at the end of each user session), users may notice performance degradation due to content refresh, regardless of whether the user accessed the same content in a previous session.</span></span>
- <span data-ttu-id="99c5b-242">**用戶端更新**： VDI 上的團隊不會自動更新每電腦 MSI 安裝。</span><span class="sxs-lookup"><span data-stu-id="99c5b-242">**Client updates**: Teams on VDI isn't automatically updated with per-machine MSI installation.</span></span> <span data-ttu-id="99c5b-243">您必須安裝新的 MSI 來更新 VM 影像，如在 VDI 的 [[安裝小組](#install-teams-on-vdi)] 區段中所述。</span><span class="sxs-lookup"><span data-stu-id="99c5b-243">You have to update the VM image by installing a new MSI as described in the [Install Teams on VDI](#install-teams-on-vdi) section.</span></span> <span data-ttu-id="99c5b-244">您必須卸載目前的版本，才能更新為較新的版本。</span><span class="sxs-lookup"><span data-stu-id="99c5b-244">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="99c5b-245">**使用者體驗**： vdi 環境中的小組使用者體驗可能與非 VDI 環境不同。</span><span class="sxs-lookup"><span data-stu-id="99c5b-245">**User experience**: The Teams user experience in a VDI environment may be different from a non-VDI environment.</span></span> <span data-ttu-id="99c5b-246">差異可能是因為環境中的原則設定和/或功能支援。</span><span class="sxs-lookup"><span data-stu-id="99c5b-246">The differences may be because of policy settings and/or feature support in the environment.</span></span>

<span data-ttu-id="99c5b-247">針對與 VDI 無關的小組已知問題，請參閱[Microsoft 團隊已知問題](Known-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="99c5b-247">For Teams known issues that aren't related to VDI, see [Known issues for Microsoft Teams](Known-issues.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="99c5b-248">相關主題</span><span class="sxs-lookup"><span data-stu-id="99c5b-248">Related topics</span></span>

- [<span data-ttu-id="99c5b-249">使用 MSI 安裝 Microsoft 團隊</span><span class="sxs-lookup"><span data-stu-id="99c5b-249">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)
