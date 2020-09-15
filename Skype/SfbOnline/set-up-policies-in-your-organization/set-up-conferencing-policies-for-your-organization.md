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
description: 會議是商務用 Skype Online 的重要部分：「會議」可讓使用者群組線上進行，以查看投影片和影片、共用應用程式、exchange 檔案，以及其他溝通與共同作業。
ms.openlocfilehash: f5b420b9a5f288a0c733d3dfdc7ebc45fb323f32
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814752"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a><span data-ttu-id="b7694-103">設定組織的會議原則</span><span class="sxs-lookup"><span data-stu-id="b7694-103">Set up conferencing policies for your organization</span></span>

<span data-ttu-id="b7694-104">會議是商務用 Skype Online 的重要部分：「會議」可讓使用者群組線上進行，以查看投影片和影片、共用應用程式、exchange 檔案，以及其他溝通與共同作業。</span><span class="sxs-lookup"><span data-stu-id="b7694-104">Conferencing is an important part of Skype for Business Online: conferencing enables groups of users to come together online to view slides and video, share applications, exchange files, and otherwise communicate and collaborate.</span></span>
  
<span data-ttu-id="b7694-105">您必須維持對會議與會議設定的控制權，這一點非常重要。</span><span class="sxs-lookup"><span data-stu-id="b7694-105">It's important for you to maintain control over conferences and conference settings.</span></span> <span data-ttu-id="b7694-106">在某些情況下，可能會發生安全性問題：根據預設，任何人（包括未經驗證的使用者）都可以參與會議，並儲存在這些會議中散佈的任何投影片或講義。</span><span class="sxs-lookup"><span data-stu-id="b7694-106">In some cases, there might be security concerns: by default, anyone, including unauthenticated users, can participate in meetings and save any of the slides or handouts distributed during those meetings.</span></span> <span data-ttu-id="b7694-107">此外，可能還有一些偶然的法律問題。</span><span class="sxs-lookup"><span data-stu-id="b7694-107">In addition, there might be occasional legal concerns.</span></span> <span data-ttu-id="b7694-108">例如，在預設情況下，會議參與者可以在共用內容上加上批註;不過，當會議封存時，這些注釋不會儲存。</span><span class="sxs-lookup"><span data-stu-id="b7694-108">For example, by default ,meeting participants are allowed to make annotations on shared content; however, these annotations are not saved when the meeting is archived.</span></span> <span data-ttu-id="b7694-109">如果您的組織必須保留所有電子通訊的記錄，您可能會想要停用注釋。</span><span class="sxs-lookup"><span data-stu-id="b7694-109">If your organization is required to keep a record of all electronic communication, you might want to disable annotations.</span></span> 
  
<span data-ttu-id="b7694-110">在商務用 Skype Online 中，會議是透過會議原則來管理。</span><span class="sxs-lookup"><span data-stu-id="b7694-110">In Skype for Business Online, conferences are managed by using conferencing policies.</span></span> <span data-ttu-id="b7694-111">會議原則決定可在會議中使用的功能和功能，包括不論會議是否可將 IP 音訊與影片加入會議的人數上限。</span><span class="sxs-lookup"><span data-stu-id="b7694-111">Conferencing policies determine the features and capabilities that can be used in a conference, including everything from whether or not the conference can include IP audio and video to the maximum number of people who can attend a meeting.</span></span> <span data-ttu-id="b7694-112">您可以在全域範圍或針對每個使用者範圍設定會議原則。</span><span class="sxs-lookup"><span data-stu-id="b7694-112">Conferencing policies can be configured at the global scope or at the per-user scope.</span></span> <span data-ttu-id="b7694-113">這可讓系統管理員在決定將哪些功能提供給哪些使用者時，提供巨大的彈性。</span><span class="sxs-lookup"><span data-stu-id="b7694-113">This provides administrators with enormous flexibility when it comes to deciding which capabilities will be made available to which users.</span></span>
  
<span data-ttu-id="b7694-114">原則設定可以在建立原則時設定，或者您可以使用 **CsConferencingPolicy** Cmdlet 來修改現有原則的設定。</span><span class="sxs-lookup"><span data-stu-id="b7694-114">Policy settings can be configured at the time a policy is created, or you can use the **Set-CsConferencingPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-conferencing-policies"></a><span data-ttu-id="b7694-115">設定您的會議原則</span><span class="sxs-lookup"><span data-stu-id="b7694-115">Set your conferencing policies</span></span>

> [!NOTE]
> <span data-ttu-id="b7694-116">針對商務用 Skype Online 中的所有會議原則設定，您必須使用 Windows PowerShell，而且您 **無法使用商務用** **Skype 系統管理中心**。</span><span class="sxs-lookup"><span data-stu-id="b7694-116">For all of the conferencing policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="b7694-117">驗證並啟動 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7694-117">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="b7694-118">**檢查您執行的是 Windows PowerShell 版本3.0 或更高版本**</span><span class="sxs-lookup"><span data-stu-id="b7694-118">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="b7694-119">若要確認您執行的是版本3.0 或更高版本： [**開始] 功能表**  >  **Windows PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="b7694-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="b7694-120">在**Windows PowerShell**視窗中輸入 [_取得主機_]，以檢查版本。</span><span class="sxs-lookup"><span data-stu-id="b7694-120">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="b7694-121">如果您沒有版本3.0 或更高版本，您需要下載並安裝 Windows PowerShell 更新。</span><span class="sxs-lookup"><span data-stu-id="b7694-121">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="b7694-122">請參閱 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) ，以下載並更新 Windows PowerShell 至版本4.0。</span><span class="sxs-lookup"><span data-stu-id="b7694-122">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="b7694-123">出現提示時，請重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="b7694-123">Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="b7694-124">您也需要安裝 Windows PowerShell 模組供團隊使用，讓您建立連線到商務用 Skype Online 的遠端 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="b7694-124">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span>
    
    <span data-ttu-id="b7694-125">如果您需要進一步瞭解，請參閱 [在單一 Windows PowerShell 視窗中連線至所有 Microsoft 365 或 Office 365 服務](https://technet.microsoft.com/library/dn568015.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b7694-125">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="b7694-126">**啟動 Windows PowerShell 會話**</span><span class="sxs-lookup"><span data-stu-id="b7694-126">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="b7694-127">從 [**開始] 功能表**中的 [  >  **Windows PowerShell**]。</span><span class="sxs-lookup"><span data-stu-id="b7694-127">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="b7694-128">在 **Windows PowerShell** 視窗中，執行下列動作以連線至您的 Microsoft 365 或 Office 365：</span><span class="sxs-lookup"><span data-stu-id="b7694-128">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
        
     > [!NOTE]
     > <span data-ttu-id="b7694-129">商務用 Skype Online 連接器目前是最新團隊 PowerShell 模組的一部分。</span><span class="sxs-lookup"><span data-stu-id="b7694-129">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
     >
     > <span data-ttu-id="b7694-130">如果您使用的是最新的 [團隊 PowerShell 公開發行](https://www.powershellgallery.com/packages/MicrosoftTeams/)，就不需要安裝商務用 Skype Online 連接器。</span><span class="sxs-lookup"><span data-stu-id="b7694-130">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

       ```PowerShell      
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   <span data-ttu-id="b7694-131">如果您需要啟動 Windows PowerShell 的詳細資訊，請參閱 [在單一 Windows powershell 視窗中連線至所有 Microsoft 365 或 Office 365 服務](https://technet.microsoft.com/library/dn568015.aspx) ，或 [設定您的 windows powershell 電腦](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="b7694-131">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a><span data-ttu-id="b7694-132">在會議期間封鎖檔案傳輸與桌面共用</span><span class="sxs-lookup"><span data-stu-id="b7694-132">Block file transfers and desktop sharing during meetings</span></span>

- <span data-ttu-id="b7694-133">若要為這些設定建立新的原則，請執行：</span><span class="sxs-lookup"><span data-stu-id="b7694-133">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
   ```
   <span data-ttu-id="b7694-134">如需進一步瞭解，請參閱 [新版 CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b7694-134">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="b7694-135">若要將您建立的新原則授與貴組織中的所有使用者，請執行：</span><span class="sxs-lookup"><span data-stu-id="b7694-135">To grant the new policy you created to all users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
   ```
   <span data-ttu-id="b7694-136">如需 [CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) Cmdlet 的詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="b7694-136">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="b7694-137">如果您已建立原則，您可以使用 [CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) Cmdlet 來變更現有的原則，然後使用[授與 CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) Cmdlet 將設定套用到您的使用者。</span><span class="sxs-lookup"><span data-stu-id="b7694-137">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a><span data-ttu-id="b7694-138">封鎖會議錄製並防止匿名會議參與者</span><span class="sxs-lookup"><span data-stu-id="b7694-138">Block recording of conferences and prevent anonymous meeting participants</span></span>

- <span data-ttu-id="b7694-139">若要為這些設定建立新的原則，請執行：</span><span class="sxs-lookup"><span data-stu-id="b7694-139">To create a new policy for these settings, run:</span></span> 
   
   ```powershell
   New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
   ```
   <span data-ttu-id="b7694-140">如需進一步瞭解，請參閱 [新版 CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b7694-140">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="b7694-141">若要將您建立的新原則授與 Amos 大理石，請執行：</span><span class="sxs-lookup"><span data-stu-id="b7694-141">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
    Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
   ```
   <span data-ttu-id="b7694-142">如需 [CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) Cmdlet 的詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="b7694-142">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="b7694-143">如果您已建立原則，您可以使用 [CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) Cmdlet 來變更現有的原則，然後使用 [授與 CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) Cmdlet 將設定套用到您的使用者。</span><span class="sxs-lookup"><span data-stu-id="b7694-143">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a><span data-ttu-id="b7694-144">封鎖匿名參與者的錄製會議與外部使用者無法儲存會議內容</span><span class="sxs-lookup"><span data-stu-id="b7694-144">Block anonymous participants from recording meetings and external users from saving meeting content</span></span>

- <span data-ttu-id="b7694-145">若要為這些設定建立新的原則，請執行：</span><span class="sxs-lookup"><span data-stu-id="b7694-145">To create a new policy for these settings, run:</span></span>  
   
   ```powershell
   New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
   ```
   <span data-ttu-id="b7694-146">如需進一步瞭解，請參閱 [新版 CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b7694-146">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="b7694-147">若要將您建立的新原則授與貴組織中的所有使用者，請執行：</span><span class="sxs-lookup"><span data-stu-id="b7694-147">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
   ```

<span data-ttu-id="b7694-148">如需 [CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) Cmdlet 的詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="b7694-148">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="b7694-149">如果您已建立原則，您可以使用 [CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) Cmdlet 來變更現有的原則，然後使用[授與 CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) Cmdlet 將設定套用到您的使用者。</span><span class="sxs-lookup"><span data-stu-id="b7694-149">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="b7694-150">想要深入瞭解 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="b7694-150">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="b7694-151">Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="b7694-151">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="b7694-152">在 Windows PowerShell 中，您可以使用單一管理點管理 Microsoft 365 或 Office 365 及商務用 Skype Online，當您有多個工作需要執行時，可簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="b7694-152">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="b7694-153">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="b7694-153">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="b7694-154">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="b7694-154">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="b7694-155">您可能會想要使用 Windows PowerShell 來管理 Microsoft 365 或 Office 365 的六個原因</span><span class="sxs-lookup"><span data-stu-id="b7694-155">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="b7694-156">Windows PowerShell 在速度、簡潔性和生產率上都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者設定變更時。</span><span class="sxs-lookup"><span data-stu-id="b7694-156">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="b7694-157">請參閱下列主題，瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="b7694-157">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="b7694-158">使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="b7694-158">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="b7694-159">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="b7694-159">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="b7694-160">使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="b7694-160">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="b7694-161">相關主題</span><span class="sxs-lookup"><span data-stu-id="b7694-161">Related topics</span></span>
[<span data-ttu-id="b7694-162">建立自訂外部存取原則</span><span class="sxs-lookup"><span data-stu-id="b7694-162">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="b7694-163">封鎖點對端檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="b7694-163">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="b7694-164">設定組織的用戶端原則</span><span class="sxs-lookup"><span data-stu-id="b7694-164">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

  
 
