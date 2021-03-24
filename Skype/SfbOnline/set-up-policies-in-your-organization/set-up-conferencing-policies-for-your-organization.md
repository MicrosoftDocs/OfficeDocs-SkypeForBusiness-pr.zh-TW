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
description: 會議是商務用 Skype Online 的一項重要內容：會議可讓使用者群組在線上共同查看幻燈片和視訊、共用應用程式、交換檔案，以及通訊和共同合作。
ms.openlocfilehash: f4c8831408ed5c17073456306c0f48add73161ff
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100519"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a><span data-ttu-id="b0c52-103">設定組織的會議原則</span><span class="sxs-lookup"><span data-stu-id="b0c52-103">Set up conferencing policies for your organization</span></span>

<span data-ttu-id="b0c52-104">會議是商務用 Skype Online 的一項重要內容：會議可讓使用者群組在線上共同查看幻燈片和視訊、共用應用程式、交換檔案，以及以其他方式通訊和共同合作。</span><span class="sxs-lookup"><span data-stu-id="b0c52-104">Conferencing is an important part of Skype for Business Online: conferencing enables groups of users to come together online to view slides and video, share applications, exchange files, and otherwise communicate and collaborate.</span></span>
  
<span data-ttu-id="b0c52-105">您必須維持對會議與會議設定的控制。</span><span class="sxs-lookup"><span data-stu-id="b0c52-105">It's important for you to maintain control over conferences and conference settings.</span></span> <span data-ttu-id="b0c52-106">在某些情況下，可能有安全性考慮：根據預設，任何人 ，包括未經驗證的使用者，都可以參與會議，並儲存這些會議期間散發的任何幻燈片或講義。</span><span class="sxs-lookup"><span data-stu-id="b0c52-106">In some cases, there might be security concerns: by default, anyone, including unauthenticated users, can participate in meetings and save any of the slides or handouts distributed during those meetings.</span></span> <span data-ttu-id="b0c52-107">此外，可能偶爾也會有法律上的問題。</span><span class="sxs-lookup"><span data-stu-id="b0c52-107">In addition, there might be occasional legal concerns.</span></span> <span data-ttu-id="b0c52-108">例如，根據預設，會議參與者可以針對共用內容進行注釋;不過，這些注釋不會在會議儲存時儲存。</span><span class="sxs-lookup"><span data-stu-id="b0c52-108">For example, by default ,meeting participants are allowed to make annotations on shared content; however, these annotations are not saved when the meeting is archived.</span></span> <span data-ttu-id="b0c52-109">如果貴組織需要保留所有電子通訊的記錄，您可能會想要停用注釋。</span><span class="sxs-lookup"><span data-stu-id="b0c52-109">If your organization is required to keep a record of all electronic communication, you might want to disable annotations.</span></span> 
  
<span data-ttu-id="b0c52-110">在商務用 Skype Online 中，會議是使用會議策略進行管理。</span><span class="sxs-lookup"><span data-stu-id="b0c52-110">In Skype for Business Online, conferences are managed by using conferencing policies.</span></span> <span data-ttu-id="b0c52-111">會議政策會決定可在會議中使用的功能，包括會議是否可以包含 IP 音訊和視像，以及可參加會議人數上限等所有專案。</span><span class="sxs-lookup"><span data-stu-id="b0c52-111">Conferencing policies determine the features and capabilities that can be used in a conference, including everything from whether or not the conference can include IP audio and video to the maximum number of people who can attend a meeting.</span></span> <span data-ttu-id="b0c52-112">會議策略可以在全域範圍或每個使用者範圍內進行配置。</span><span class="sxs-lookup"><span data-stu-id="b0c52-112">Conferencing policies can be configured at the global scope or at the per-user scope.</span></span> <span data-ttu-id="b0c52-113">當決定哪些功能可供哪些使用者使用時，這為系統管理員提供了極大的彈性。</span><span class="sxs-lookup"><span data-stu-id="b0c52-113">This provides administrators with enormous flexibility when it comes to deciding which capabilities will be made available to which users.</span></span>
  
<span data-ttu-id="b0c52-114">您可以在建立策略時設定策略設定，或者您可以使用 **Set-CsConferencingPolicy** Cmdlet 修改現有策略的設定。</span><span class="sxs-lookup"><span data-stu-id="b0c52-114">Policy settings can be configured at the time a policy is created, or you can use the **Set-CsConferencingPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-conferencing-policies"></a><span data-ttu-id="b0c52-115">設定您的會議策略</span><span class="sxs-lookup"><span data-stu-id="b0c52-115">Set your conferencing policies</span></span>

> [!NOTE]
> <span data-ttu-id="b0c52-116">針對商務用 Skype Online 中所有的會議策略設定，您必須使用 Windows PowerShell，而且您不得使用商務用 **Skype 系統管理中心**。</span><span class="sxs-lookup"><span data-stu-id="b0c52-116">For all of the conferencing policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 

### <a name="start-windows-powershell"></a><span data-ttu-id="b0c52-117">啟動 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b0c52-117">Start Windows PowerShell</span></span>

 > [!Note]
> <span data-ttu-id="b0c52-118">商務用 Skype Online Connector 目前是 Teams PowerShell 最新模組的一部分。</span><span class="sxs-lookup"><span data-stu-id="b0c52-118">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="b0c52-119">如果您使用的是最新的 Teams PowerShell 公開發行，則不需要安裝商務用 Skype Online 連接器。</span><span class="sxs-lookup"><span data-stu-id="b0c52-119">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="b0c52-120">安裝 [Teams PowerShell 模組](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="b0c52-120">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="b0c52-121">開啟 Windows PowerShell 命令提示符，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="b0c52-121">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module 
   
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="b0c52-122">如果您想要啟動 Windows PowerShell 的更多相關資訊，請參閱在單一 Windows PowerShell 視窗中連接到所有 [Microsoft 365 或 Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) 服務，或設定 [電腦以使用 Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="b0c52-122">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
      
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a><span data-ttu-id="b0c52-123">在會議期間封鎖檔案傳輸和桌面共用</span><span class="sxs-lookup"><span data-stu-id="b0c52-123">Block file transfers and desktop sharing during meetings</span></span>

- <span data-ttu-id="b0c52-124">若要為這些設定建立新策略，請執行：</span><span class="sxs-lookup"><span data-stu-id="b0c52-124">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
   ```
   <span data-ttu-id="b0c52-125">請參閱 [New-CsConferencingIngPolicy](/powershell/module/skype/New-CsConferencingPolicy) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b0c52-125">See more on the [New-CsConferencingPolicy](/powershell/module/skype/New-CsConferencingPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="b0c52-126">若要將您建立的新政策授予貴組織的所有使用者，請執行：</span><span class="sxs-lookup"><span data-stu-id="b0c52-126">To grant the new policy you created to all users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
   ```
   <span data-ttu-id="b0c52-127">請參閱 [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b0c52-127">See more on the [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet.</span></span>
    
  <span data-ttu-id="b0c52-128">如果您已經建立原則，您可以使用 [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) Cmdlet 對現有原則進行變更，然後使用[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) Cmdlet 將設定套用給使用者。</span><span class="sxs-lookup"><span data-stu-id="b0c52-128">If you have already created a policy, you can use the [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a><span data-ttu-id="b0c52-129">封鎖會議錄製，並防止匿名會議參與者</span><span class="sxs-lookup"><span data-stu-id="b0c52-129">Block recording of conferences and prevent anonymous meeting participants</span></span>

- <span data-ttu-id="b0c52-130">若要為這些設定建立新策略，請執行：</span><span class="sxs-lookup"><span data-stu-id="b0c52-130">To create a new policy for these settings, run:</span></span> 
   
   ```powershell
   New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
   ```
   <span data-ttu-id="b0c52-131">請參閱 [New-CsConferencingIngPolicy](/powershell/module/skype/New-CsConferencingPolicy) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b0c52-131">See more on the [New-CsConferencingPolicy](/powershell/module/skype/New-CsConferencingPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="b0c52-132">若要將您建立的新政策授予 Amos Marble，請執行：</span><span class="sxs-lookup"><span data-stu-id="b0c52-132">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
    Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
   ```
   <span data-ttu-id="b0c52-133">請參閱 [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b0c52-133">See more on the [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet.</span></span>
    
<span data-ttu-id="b0c52-134">如果您已經建立原則，您可以使用 [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) Cmdlet 對現有原則進行變更，然後使用 [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) Cmdlet 將設定套用給使用者。</span><span class="sxs-lookup"><span data-stu-id="b0c52-134">If you have already created a policy, you can use the [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a><span data-ttu-id="b0c52-135">封鎖匿名參與者錄製會議，以及禁止外部使用者保存會議內容</span><span class="sxs-lookup"><span data-stu-id="b0c52-135">Block anonymous participants from recording meetings and external users from saving meeting content</span></span>

- <span data-ttu-id="b0c52-136">若要為這些設定建立新策略，請執行：</span><span class="sxs-lookup"><span data-stu-id="b0c52-136">To create a new policy for these settings, run:</span></span>  
   
   ```powershell
   New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
   ```
   <span data-ttu-id="b0c52-137">請參閱 [New-CsConferencingIngPolicy](/powershell/module/skype/New-CsConferencingPolicy) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b0c52-137">See more on the [New-CsConferencingPolicy](/powershell/module/skype/New-CsConferencingPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="b0c52-138">若要將您建立的新政策授予貴組織中所有使用者，請執行：</span><span class="sxs-lookup"><span data-stu-id="b0c52-138">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
   ```

<span data-ttu-id="b0c52-139">請參閱 [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b0c52-139">See more on the [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet.</span></span>
    
<span data-ttu-id="b0c52-140">如果您已經建立原則，您可以使用 [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) Cmdlet 對現有原則進行變更，然後使用[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) Cmdlet 將設定套用給使用者。</span><span class="sxs-lookup"><span data-stu-id="b0c52-140">If you have already created a policy, you can use the [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="b0c52-141">想要進一瞭解 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="b0c52-141">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="b0c52-142">Windows PowerShell 就是管理使用者，以及允許或不允許使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="b0c52-142">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="b0c52-143">使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365 和商務用 Skype Online，當您有多個工作需要執行時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="b0c52-143">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="b0c52-144">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="b0c52-144">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="b0c52-145">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="b0c52-145">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="b0c52-146">您可能會想要使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的六個原因</span><span class="sxs-lookup"><span data-stu-id="b0c52-146">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="b0c52-147">Windows PowerShell 比使用 Microsoft 365 系統管理中心在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。</span><span class="sxs-lookup"><span data-stu-id="b0c52-147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="b0c52-148">請從下列主題瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="b0c52-148">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="b0c52-149">[使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="b0c52-149">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="b0c52-150">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="b0c52-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="b0c52-151">使用 Windows PowerShell 執行常見的商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="b0c52-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a><span data-ttu-id="b0c52-152">相關主題</span><span class="sxs-lookup"><span data-stu-id="b0c52-152">Related topics</span></span>
[<span data-ttu-id="b0c52-153">建立自訂外部存取原則</span><span class="sxs-lookup"><span data-stu-id="b0c52-153">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="b0c52-154">封鎖點到點檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="b0c52-154">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="b0c52-155">設定組織的用戶端原則</span><span class="sxs-lookup"><span data-stu-id="b0c52-155">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

  
