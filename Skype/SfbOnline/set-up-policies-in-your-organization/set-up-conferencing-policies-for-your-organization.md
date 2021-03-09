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
description: 會議是商務用 Skype Online 的重要一部分：會議可讓使用者群組在線上一起觀看幻燈片和視訊、共用應用程式、交換檔案，以及進行通訊和共同合作。
ms.openlocfilehash: 9a2e18ad23eaa08813c87e83058ecc0dcd1dfec1
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569205"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a><span data-ttu-id="f0e1b-103">設定組織的會議原則</span><span class="sxs-lookup"><span data-stu-id="f0e1b-103">Set up conferencing policies for your organization</span></span>

<span data-ttu-id="f0e1b-104">會議是商務用 Skype Online 的重要一部分：會議可讓使用者群組在線上共同觀看幻燈片和視訊、共用應用程式、交換檔案，以及進行通訊和共同合作。</span><span class="sxs-lookup"><span data-stu-id="f0e1b-104">Conferencing is an important part of Skype for Business Online: conferencing enables groups of users to come together online to view slides and video, share applications, exchange files, and otherwise communicate and collaborate.</span></span>
  
<span data-ttu-id="f0e1b-105">對於您來說，保持對會議與會議設定的控制非常重要。</span><span class="sxs-lookup"><span data-stu-id="f0e1b-105">It's important for you to maintain control over conferences and conference settings.</span></span> <span data-ttu-id="f0e1b-106">在某些情況下，可能有安全性考慮：根據預設，任何人 ，包括未經驗證的使用者，都可以參與會議，並儲存會議期間散發的任何一張或多張講義。</span><span class="sxs-lookup"><span data-stu-id="f0e1b-106">In some cases, there might be security concerns: by default, anyone, including unauthenticated users, can participate in meetings and save any of the slides or handouts distributed during those meetings.</span></span> <span data-ttu-id="f0e1b-107">此外，偶爾可能也會有法律上的問題。</span><span class="sxs-lookup"><span data-stu-id="f0e1b-107">In addition, there might be occasional legal concerns.</span></span> <span data-ttu-id="f0e1b-108">例如，根據預設，會議參與者可以針對共用內容進行注釋;不過，這些注釋不會在會議被存檔時儲存。</span><span class="sxs-lookup"><span data-stu-id="f0e1b-108">For example, by default ,meeting participants are allowed to make annotations on shared content; however, these annotations are not saved when the meeting is archived.</span></span> <span data-ttu-id="f0e1b-109">如果貴組織需要保留所有電子通訊的記錄，您可能會想要停用注釋。</span><span class="sxs-lookup"><span data-stu-id="f0e1b-109">If your organization is required to keep a record of all electronic communication, you might want to disable annotations.</span></span> 
  
<span data-ttu-id="f0e1b-110">在商務用 Skype Online 中，會議是使用會議策略管理。</span><span class="sxs-lookup"><span data-stu-id="f0e1b-110">In Skype for Business Online, conferences are managed by using conferencing policies.</span></span> <span data-ttu-id="f0e1b-111">會議政策會決定可在會議中使用的功能，包括從會議是否可以包含 IP 音訊和視音訊到可參與會議人數的上限等所有專案。</span><span class="sxs-lookup"><span data-stu-id="f0e1b-111">Conferencing policies determine the features and capabilities that can be used in a conference, including everything from whether or not the conference can include IP audio and video to the maximum number of people who can attend a meeting.</span></span> <span data-ttu-id="f0e1b-112">會議策略可以在全域範圍或每個使用者範圍中進行。</span><span class="sxs-lookup"><span data-stu-id="f0e1b-112">Conferencing policies can be configured at the global scope or at the per-user scope.</span></span> <span data-ttu-id="f0e1b-113">這提供系統管理員在決定哪些功能可供哪些使用者使用時，擁有極大的彈性。</span><span class="sxs-lookup"><span data-stu-id="f0e1b-113">This provides administrators with enormous flexibility when it comes to deciding which capabilities will be made available to which users.</span></span>
  
<span data-ttu-id="f0e1b-114">您可以在建立策略時設定策略設定，或者您可以使用 **Set-CsConferencingPolicy** Cmdlet 來修改現有策略的設定。</span><span class="sxs-lookup"><span data-stu-id="f0e1b-114">Policy settings can be configured at the time a policy is created, or you can use the **Set-CsConferencingPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-conferencing-policies"></a><span data-ttu-id="f0e1b-115">設定您的會議政策</span><span class="sxs-lookup"><span data-stu-id="f0e1b-115">Set your conferencing policies</span></span>

> [!NOTE]
> <span data-ttu-id="f0e1b-116">針對商務用 Skype Online 中所有的會議政策設定，您必須使用 Windows PowerShell，而且不能使用商務用 **Skype 系統管理中心**。</span><span class="sxs-lookup"><span data-stu-id="f0e1b-116">For all of the conferencing policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 

### <a name="start-windows-powershell"></a><span data-ttu-id="f0e1b-117">啟動 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0e1b-117">Start Windows PowerShell</span></span>

 > [!Note]
> <span data-ttu-id="f0e1b-118">商務用 Skype Online Connector 目前是最新 Teams PowerShell 模組的一部分。</span><span class="sxs-lookup"><span data-stu-id="f0e1b-118">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="f0e1b-119">如果您使用的是最新的 Teams PowerShell 公開發行，則不需要安裝商務用 Skype Online Connector。</span><span class="sxs-lookup"><span data-stu-id="f0e1b-119">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="f0e1b-120">安裝 [Teams PowerShell 模組](https://docs.microsoft.com/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="f0e1b-120">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="f0e1b-121">開啟 Windows PowerShell 命令提示程式，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="f0e1b-121">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module 
   
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="f0e1b-122">如果您想要有關啟動 Windows PowerShell 的資訊，請參閱在單一 Windows PowerShell 視窗中連接到所有[Microsoft 365 或 Office 365](https://technet.microsoft.com/library/dn568015.aspx)服務，或設定[您的電腦以使用 Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="f0e1b-122">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
      
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a><span data-ttu-id="f0e1b-123">在會議期間封鎖檔案傳輸和桌面共用</span><span class="sxs-lookup"><span data-stu-id="f0e1b-123">Block file transfers and desktop sharing during meetings</span></span>

- <span data-ttu-id="f0e1b-124">若要為這些設定建立新策略，請執行：</span><span class="sxs-lookup"><span data-stu-id="f0e1b-124">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
   ```
   <span data-ttu-id="f0e1b-125">查看 [New-CsConferencingPolicy Cmdlet](https://technet.microsoft.com/library/mt779148.aspx) 的更多資訊。</span><span class="sxs-lookup"><span data-stu-id="f0e1b-125">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="f0e1b-126">若要將您建立的新政策授予貴組織的所有使用者，請執行：</span><span class="sxs-lookup"><span data-stu-id="f0e1b-126">To grant the new policy you created to all users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
   ```
   <span data-ttu-id="f0e1b-127">查看 [Grant-CsConferencingPolicy Cmdlet](https://technet.microsoft.com/library/mt779156.aspx) 的更多資訊。</span><span class="sxs-lookup"><span data-stu-id="f0e1b-127">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="f0e1b-128">如果您已經建立原則，您可以使用 [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) Cmdlet 對現有原則進行變更，然後使用[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) Cmdlet 將設定套用至您的使用者。</span><span class="sxs-lookup"><span data-stu-id="f0e1b-128">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a><span data-ttu-id="f0e1b-129">封鎖會議的錄製，並防止匿名會議參與者</span><span class="sxs-lookup"><span data-stu-id="f0e1b-129">Block recording of conferences and prevent anonymous meeting participants</span></span>

- <span data-ttu-id="f0e1b-130">若要為這些設定建立新策略，請執行：</span><span class="sxs-lookup"><span data-stu-id="f0e1b-130">To create a new policy for these settings, run:</span></span> 
   
   ```powershell
   New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
   ```
   <span data-ttu-id="f0e1b-131">查看 [New-CsConferencingPolicy Cmdlet](https://technet.microsoft.com/library/mt779148.aspx) 的更多資訊。</span><span class="sxs-lookup"><span data-stu-id="f0e1b-131">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="f0e1b-132">若要將您建立的新策略授予 Amos Marble，請執行：</span><span class="sxs-lookup"><span data-stu-id="f0e1b-132">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
    Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
   ```
   <span data-ttu-id="f0e1b-133">查看 [Grant-CsConferencingPolicy Cmdlet](https://technet.microsoft.com/library/mt779156.aspx) 的更多資訊。</span><span class="sxs-lookup"><span data-stu-id="f0e1b-133">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="f0e1b-134">如果您已經建立原則，您可以使用 [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) Cmdlet 對現有原則進行變更，然後使用 [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) Cmdlet 將設定套用至您的使用者。</span><span class="sxs-lookup"><span data-stu-id="f0e1b-134">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a><span data-ttu-id="f0e1b-135">封鎖匿名參與者，禁止錄製會議，以及禁止外部使用者存存會議內容</span><span class="sxs-lookup"><span data-stu-id="f0e1b-135">Block anonymous participants from recording meetings and external users from saving meeting content</span></span>

- <span data-ttu-id="f0e1b-136">若要為這些設定建立新策略，請執行：</span><span class="sxs-lookup"><span data-stu-id="f0e1b-136">To create a new policy for these settings, run:</span></span>  
   
   ```powershell
   New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
   ```
   <span data-ttu-id="f0e1b-137">查看 [New-CsConferencingPolicy Cmdlet](https://technet.microsoft.com/library/mt779148.aspx) 的更多資訊。</span><span class="sxs-lookup"><span data-stu-id="f0e1b-137">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="f0e1b-138">若要將您建立的新政策授予貴組織的所有使用者，請執行：</span><span class="sxs-lookup"><span data-stu-id="f0e1b-138">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
   ```

<span data-ttu-id="f0e1b-139">查看 [Grant-CsConferencingPolicy Cmdlet](https://technet.microsoft.com/library/mt779156.aspx) 的更多資訊。</span><span class="sxs-lookup"><span data-stu-id="f0e1b-139">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="f0e1b-140">如果您已經建立原則，您可以使用 [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) Cmdlet 對現有原則進行變更，然後使用[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) Cmdlet 將設定套用至您的使用者。</span><span class="sxs-lookup"><span data-stu-id="f0e1b-140">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="f0e1b-141">想要進一瞭解更多 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="f0e1b-141">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="f0e1b-142">Windows PowerShell 就是管理使用者，以及允許或禁止使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="f0e1b-142">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="f0e1b-143">使用 Windows PowerShell，您可以使用單點系統管理來管理 Microsoft 365 或 Office 365 和商務用 Skype Online，當您有多個任務作作時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="f0e1b-143">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="f0e1b-144">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="f0e1b-144">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f0e1b-145">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="f0e1b-145">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="f0e1b-146">為何要使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的六個原因</span><span class="sxs-lookup"><span data-stu-id="f0e1b-146">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="f0e1b-147">與只使用 Microsoft 365 系統管理中心相比，Windows PowerShell 在速度、簡化和生產力方面有許多優點，例如當您一次為許多使用者進行設定變更時。</span><span class="sxs-lookup"><span data-stu-id="f0e1b-147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="f0e1b-148">在下列主題中瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="f0e1b-148">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="f0e1b-149">使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="f0e1b-149">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="f0e1b-150">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="f0e1b-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="f0e1b-151">使用 Windows PowerShell 執行一般商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="f0e1b-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="f0e1b-152">相關主題</span><span class="sxs-lookup"><span data-stu-id="f0e1b-152">Related topics</span></span>
[<span data-ttu-id="f0e1b-153">建立自訂外部存取原則</span><span class="sxs-lookup"><span data-stu-id="f0e1b-153">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="f0e1b-154">封鎖點對點檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="f0e1b-154">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="f0e1b-155">設定組織的用戶端原則</span><span class="sxs-lookup"><span data-stu-id="f0e1b-155">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

  
 
