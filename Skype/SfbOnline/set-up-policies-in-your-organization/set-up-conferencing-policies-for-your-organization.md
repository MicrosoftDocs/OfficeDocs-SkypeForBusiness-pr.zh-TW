---
title: 設定組織的會議原則
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9957722b-b542-49ad-8ec8-5569df7fb08b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 會議是線上商務用 Skype的一項重要內容：會議可讓使用者群組在線上共同查看幻燈片和視訊、共用應用程式、交換檔案，以及以其他方式通訊和共同合作。
ms.openlocfilehash: 84037d571bf6f9dc3451793678a6d1b650492bd9
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240075"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a><span data-ttu-id="851bb-103">設定組織的會議原則</span><span class="sxs-lookup"><span data-stu-id="851bb-103">Set up conferencing policies for your organization</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="851bb-104">會議是線上商務用 Skype的一項重要內容：會議可讓使用者群組在線上共同查看幻燈片和視訊、共用應用程式、交換檔案，以及以其他方式通訊和共同合作。</span><span class="sxs-lookup"><span data-stu-id="851bb-104">Conferencing is an important part of Skype for Business Online: conferencing enables groups of users to come together online to view slides and video, share applications, exchange files, and otherwise communicate and collaborate.</span></span>
  
<span data-ttu-id="851bb-105">您必須維持對會議與會議設定的控制。</span><span class="sxs-lookup"><span data-stu-id="851bb-105">It's important for you to maintain control over conferences and conference settings.</span></span> <span data-ttu-id="851bb-106">在某些情況下，可能有安全性考慮：根據預設，任何人 ，包括未經驗證的使用者，都可以參與會議，並儲存這些會議期間散發的任何幻燈片或講義。</span><span class="sxs-lookup"><span data-stu-id="851bb-106">In some cases, there might be security concerns: by default, anyone, including unauthenticated users, can participate in meetings and save any of the slides or handouts distributed during those meetings.</span></span> <span data-ttu-id="851bb-107">此外，可能偶爾也會有法律上的問題。</span><span class="sxs-lookup"><span data-stu-id="851bb-107">In addition, there might be occasional legal concerns.</span></span> <span data-ttu-id="851bb-108">例如，根據預設，會議參與者可以針對共用內容進行注釋;不過，這些注釋不會在會議儲存時儲存。</span><span class="sxs-lookup"><span data-stu-id="851bb-108">For example, by default ,meeting participants are allowed to make annotations on shared content; however, these annotations are not saved when the meeting is archived.</span></span> <span data-ttu-id="851bb-109">如果貴組織需要保留所有電子通訊的記錄，您可能會想要停用注釋。</span><span class="sxs-lookup"><span data-stu-id="851bb-109">If your organization is required to keep a record of all electronic communication, you might want to disable annotations.</span></span> 
  
<span data-ttu-id="851bb-110">在 商務用 Skype Online 中，會議會使用會議策略進行管理。</span><span class="sxs-lookup"><span data-stu-id="851bb-110">In Skype for Business Online, conferences are managed by using conferencing policies.</span></span> <span data-ttu-id="851bb-111">會議政策會決定可在會議中使用的功能，包括會議是否可以包含 IP 音訊和視像，以及可參加會議人數上限等所有專案。</span><span class="sxs-lookup"><span data-stu-id="851bb-111">Conferencing policies determine the features and capabilities that can be used in a conference, including everything from whether or not the conference can include IP audio and video to the maximum number of people who can attend a meeting.</span></span> <span data-ttu-id="851bb-112">會議策略可以在全域範圍或每個使用者範圍內進行配置。</span><span class="sxs-lookup"><span data-stu-id="851bb-112">Conferencing policies can be configured at the global scope or at the per-user scope.</span></span> <span data-ttu-id="851bb-113">當決定哪些功能可供哪些使用者使用時，這為系統管理員提供了極大的彈性。</span><span class="sxs-lookup"><span data-stu-id="851bb-113">This provides administrators with enormous flexibility when it comes to deciding which capabilities will be made available to which users.</span></span>
  
<span data-ttu-id="851bb-114">您可以在建立策略時設定策略設定，或者您可以使用 **Set-CsConferencingPolicy** Cmdlet 修改現有策略的設定。</span><span class="sxs-lookup"><span data-stu-id="851bb-114">Policy settings can be configured at the time a policy is created, or you can use the **Set-CsConferencingPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-conferencing-policies"></a><span data-ttu-id="851bb-115">設定您的會議策略</span><span class="sxs-lookup"><span data-stu-id="851bb-115">Set your conferencing policies</span></span>

> [!NOTE]
> <span data-ttu-id="851bb-116">對於 商務用 Skype Online 中所有的會議Windows PowerShell，您不得使用 商務用 Skype **系統管理中心**。 </span><span class="sxs-lookup"><span data-stu-id="851bb-116">For all of the conferencing policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 

### <a name="start-windows-powershell"></a><span data-ttu-id="851bb-117">開始Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="851bb-117">Start Windows PowerShell</span></span>

 > [!Note]
> <span data-ttu-id="851bb-118">商務用 Skype線上連接器是目前 PowerShell 模組Teams的一部分。</span><span class="sxs-lookup"><span data-stu-id="851bb-118">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="851bb-119">如果您使用的是最新版 PowerShell Teams版本，則不需要安裝 商務用 Skype 連接器。</span><span class="sxs-lookup"><span data-stu-id="851bb-119">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="851bb-120">安裝[powerShell Teams模組](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="851bb-120">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="851bb-121">開啟 Windows PowerShell命令提示符，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="851bb-121">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module 
   
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="851bb-122">如果您想要啟動 Windows PowerShell 功能連線，請參閱在單一 Microsoft 365 視窗中Office 365 [Windows PowerShell](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)所有 Microsoft 365 或 Office 365 服務，或設定您的電腦[Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="851bb-122">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
      
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a><span data-ttu-id="851bb-123">在會議期間封鎖檔案傳輸和桌面共用</span><span class="sxs-lookup"><span data-stu-id="851bb-123">Block file transfers and desktop sharing during meetings</span></span>

- <span data-ttu-id="851bb-124">若要為這些設定建立新策略，請執行：</span><span class="sxs-lookup"><span data-stu-id="851bb-124">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
   ```
   <span data-ttu-id="851bb-125">請參閱 [New-CsConferencingPolicy](/powershell/module/skype/New-CsConferencingPolicy) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="851bb-125">See more on the [New-CsConferencingPolicy](/powershell/module/skype/New-CsConferencingPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="851bb-126">若要將您建立的新政策授予貴組織的所有使用者，請執行：</span><span class="sxs-lookup"><span data-stu-id="851bb-126">To grant the new policy you created to all users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
   ```
   <span data-ttu-id="851bb-127">請參閱 [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="851bb-127">See more on the [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet.</span></span>
    
  <span data-ttu-id="851bb-128">如果您已經建立原則，您可以使用 [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) Cmdlet 對現有原則進行變更，然後使用[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) Cmdlet 將設定套用給使用者。</span><span class="sxs-lookup"><span data-stu-id="851bb-128">If you have already created a policy, you can use the [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a><span data-ttu-id="851bb-129">封鎖會議錄製，並防止匿名會議參與者</span><span class="sxs-lookup"><span data-stu-id="851bb-129">Block recording of conferences and prevent anonymous meeting participants</span></span>

- <span data-ttu-id="851bb-130">若要為這些設定建立新策略，請執行：</span><span class="sxs-lookup"><span data-stu-id="851bb-130">To create a new policy for these settings, run:</span></span> 
   
   ```powershell
   New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
   ```
   <span data-ttu-id="851bb-131">請參閱 [New-CsConferencingPolicy](/powershell/module/skype/New-CsConferencingPolicy) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="851bb-131">See more on the [New-CsConferencingPolicy](/powershell/module/skype/New-CsConferencingPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="851bb-132">若要將您建立的新政策授予 Amos Marble，請執行：</span><span class="sxs-lookup"><span data-stu-id="851bb-132">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
    Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
   ```
   <span data-ttu-id="851bb-133">請參閱 [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="851bb-133">See more on the [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet.</span></span>
    
<span data-ttu-id="851bb-134">如果您已經建立原則，您可以使用 [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) Cmdlet 對現有原則進行變更，然後使用 [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) Cmdlet 將設定套用給使用者。</span><span class="sxs-lookup"><span data-stu-id="851bb-134">If you have already created a policy, you can use the [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a><span data-ttu-id="851bb-135">封鎖匿名參與者錄製會議，以及禁止外部使用者保存會議內容</span><span class="sxs-lookup"><span data-stu-id="851bb-135">Block anonymous participants from recording meetings and external users from saving meeting content</span></span>

- <span data-ttu-id="851bb-136">若要為這些設定建立新策略，請執行：</span><span class="sxs-lookup"><span data-stu-id="851bb-136">To create a new policy for these settings, run:</span></span>  
   
   ```powershell
   New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
   ```
   <span data-ttu-id="851bb-137">請參閱 [New-CsConferencingPolicy](/powershell/module/skype/New-CsConferencingPolicy) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="851bb-137">See more on the [New-CsConferencingPolicy](/powershell/module/skype/New-CsConferencingPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="851bb-138">若要將您建立的新政策授予貴組織中所有使用者，請執行：</span><span class="sxs-lookup"><span data-stu-id="851bb-138">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
   ```

<span data-ttu-id="851bb-139">請參閱 [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="851bb-139">See more on the [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet.</span></span>
    
<span data-ttu-id="851bb-140">如果您已經建立原則，您可以使用 [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) Cmdlet 對現有原則進行變更，然後使用[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) Cmdlet 將設定套用給使用者。</span><span class="sxs-lookup"><span data-stu-id="851bb-140">If you have already created a policy, you can use the [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="851bb-141">想要進一Windows PowerShell？</span><span class="sxs-lookup"><span data-stu-id="851bb-141">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="851bb-142">Windows PowerShell管理使用者，以及允許或不允許使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="851bb-142">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="851bb-143">使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365 和 商務用 Skype Online，當您有多個工作需要執行時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="851bb-143">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="851bb-144">若要開始使用Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="851bb-144">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="851bb-145">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="851bb-145">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="851bb-146">您可能會想要使用 Windows PowerShell 管理Microsoft 365或Office 365</span><span class="sxs-lookup"><span data-stu-id="851bb-146">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="851bb-147">Windows PowerShell使用系統管理中心時，Microsoft 365在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。</span><span class="sxs-lookup"><span data-stu-id="851bb-147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="851bb-148">請從下列主題瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="851bb-148">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="851bb-149">[使用 Microsoft 365 管理Microsoft 365或Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="851bb-149">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="851bb-150">使用 Windows PowerShell 管理 商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="851bb-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="851bb-151">使用Windows PowerShell執行線上商務用 Skype管理工作</span><span class="sxs-lookup"><span data-stu-id="851bb-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a><span data-ttu-id="851bb-152">相關主題</span><span class="sxs-lookup"><span data-stu-id="851bb-152">Related topics</span></span>
[<span data-ttu-id="851bb-153">建立自訂外部存取原則</span><span class="sxs-lookup"><span data-stu-id="851bb-153">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="851bb-154">封鎖點到點檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="851bb-154">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="851bb-155">設定組織的用戶端原則</span><span class="sxs-lookup"><span data-stu-id="851bb-155">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

  
