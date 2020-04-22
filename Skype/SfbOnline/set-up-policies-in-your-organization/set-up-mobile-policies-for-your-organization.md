---
title: 設定組織的行動原則
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
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
description: 您可以使用行動裝置上的商務用 Skype app 來設定使用者連線到商務用 Skype Online 的方式，例如可讓使用者使用公司電話號碼（而不是行動電話號碼）在手機上撥打及接聽電話的功能。 行動原則也可以用於在撥打或接聽來電時，需要使用 Wi-fi 連線。
ms.openlocfilehash: ac8f94cb7203b3b0ee4698969db0b76cb1e31a49
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776258"
---
# <a name="set-up-mobile-policies-for-your-organization"></a><span data-ttu-id="e688b-104">設定組織的行動原則</span><span class="sxs-lookup"><span data-stu-id="e688b-104">Set up mobile policies for your organization</span></span>

<span data-ttu-id="e688b-105">您可以使用行動裝置上的商務用 Skype app 來設定使用者連線到商務用 Skype Online 的方式，例如可讓使用者使用公司電話號碼（而不是行動電話號碼）在手機上撥打及接聽電話的功能。</span><span class="sxs-lookup"><span data-stu-id="e688b-105">You can set up how your users connect to Skype for Business Online using the Skype for Business app on mobile devices, such as a feature that enables users to make and receive phone calls on their mobile phone by using their work phone number instead of their mobile phone number.</span></span> <span data-ttu-id="e688b-106">行動原則也可以用於在撥打或接聽來電時，需要使用 Wi-fi 連線。</span><span class="sxs-lookup"><span data-stu-id="e688b-106">Mobility policies can also be used to require Wi-Fi connections when making or receiving calls.</span></span>
  
<span data-ttu-id="e688b-107">行動原則設定可以在建立原則時設定，或者您可以使用**CsMobilityPolicy** Cmdlet 來修改現有原則的設定。</span><span class="sxs-lookup"><span data-stu-id="e688b-107">Mobile policy settings can be configured at the time a policy is created, or you can use the **Set-CsMobilityPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-mobile-policies"></a><span data-ttu-id="e688b-108">設定您的行動裝置原則</span><span class="sxs-lookup"><span data-stu-id="e688b-108">Set your mobile policies</span></span>

> [!NOTE]
> <span data-ttu-id="e688b-109">針對商務用 Skype Online 中的所有行動原則設定，您必須使用 Windows PowerShell，而且您**無法使用商務用** **Skype 系統管理中心**。</span><span class="sxs-lookup"><span data-stu-id="e688b-109">For all of the mobile policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="e688b-110">驗證並啟動 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e688b-110">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="e688b-111">**檢查您執行的是 Windows PowerShell 版本3.0 或更高版本**</span><span class="sxs-lookup"><span data-stu-id="e688b-111">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="e688b-112">若要確認您執行的是版本3.0 或更高版本： [**開始] 功能表** > **Windows PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="e688b-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="e688b-113">在**Windows PowerShell**視窗中輸入 [_取得主機_]，以檢查版本。</span><span class="sxs-lookup"><span data-stu-id="e688b-113">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="e688b-114">如果您沒有版本3.0 或更高版本，您需要下載並安裝 Windows PowerShell 更新。</span><span class="sxs-lookup"><span data-stu-id="e688b-114">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="e688b-115">請參閱[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) ，以下載並更新 Windows PowerShell 至版本4.0。</span><span class="sxs-lookup"><span data-stu-id="e688b-115">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="e688b-116">出現提示時，請重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="e688b-116">Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="e688b-117">您也需要安裝適用于商務用 Skype Online 的 Windows PowerShell 模組，這可讓您建立連線到商務用 Skype Online 的遠端 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="e688b-117">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="e688b-118">此模組只受64位電腦支援，可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。</span><span class="sxs-lookup"><span data-stu-id="e688b-118">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="e688b-119">如果出現提示，請重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="e688b-119">Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="e688b-120">如果您需要進一步瞭解，請參閱[在單一 Windows PowerShell 視窗中連線至所有 Office 365 服務](https://technet.microsoft.com/library/dn568015.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e688b-120">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="e688b-121">**啟動 Windows PowerShell 會話**</span><span class="sxs-lookup"><span data-stu-id="e688b-121">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="e688b-122">從 [**開始] 功能表** > 中的 [**Windows PowerShell**]。</span><span class="sxs-lookup"><span data-stu-id="e688b-122">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="e688b-123">在**Windows PowerShell**視窗中，執行下列動作以連線至您的 Microsoft 365 或 Office 365：</span><span class="sxs-lookup"><span data-stu-id="e688b-123">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
        
        > [!NOTE]
        > <span data-ttu-id="e688b-124">您在第一次使用商務用 Skype Online Windows PowerShell 模組時，您只需執行匯**入模組**命令。</span><span class="sxs-lookup"><span data-stu-id="e688b-124">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

       ```PowerShell      
        Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   <span data-ttu-id="e688b-125">如果您需要啟動 Windows PowerShell 的詳細資訊，請參閱[在單一 Windows powershell 視窗中連線至所有 Office 365 服務](https://technet.microsoft.com/library/dn568015.aspx)，或[設定您的 windows powershell 電腦](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="e688b-125">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

### <a name="require-a-wifi-connection-for-video-for-a-user"></a><span data-ttu-id="e688b-126">使用者需要一個 WiFi 連線才能取得影片</span><span class="sxs-lookup"><span data-stu-id="e688b-126">Require a WiFi connection for video for a user</span></span>

- <span data-ttu-id="e688b-127">若要為這些設定建立新的原則，請執行：</span><span class="sxs-lookup"><span data-stu-id="e688b-127">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   <span data-ttu-id="e688b-128">如需進一步瞭解，請參閱[新版 CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e688b-128">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="e688b-129">若要將您建立的新原則授與貴組織中的所有使用者，請執行：</span><span class="sxs-lookup"><span data-stu-id="e688b-129">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   <span data-ttu-id="e688b-130">如需[CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) Cmdlet 的詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="e688b-130">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="e688b-131">如果您已建立原則，您可以使用[CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) Cmdlet 來變更現有的原則，然後使用[授與 CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) Cmdlet 將設定套用到您的使用者。</span><span class="sxs-lookup"><span data-stu-id="e688b-131">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a><span data-ttu-id="e688b-132">防止使用者使用商務用 Skype 應用程式</span><span class="sxs-lookup"><span data-stu-id="e688b-132">Prevent a user from using the Skype for Business app</span></span>

- <span data-ttu-id="e688b-133">若要為這些設定建立新的原則，請執行：</span><span class="sxs-lookup"><span data-stu-id="e688b-133">To create a new policy for these settings, run:</span></span>
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  <span data-ttu-id="e688b-134">如需進一步瞭解，請參閱[新版 CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e688b-134">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="e688b-135">若要將您建立的新原則授與 Amos 大理石，請執行：</span><span class="sxs-lookup"><span data-stu-id="e688b-135">To grant the new policy you created to Amos Marble, run:</span></span>  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   <span data-ttu-id="e688b-136">如需[CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) Cmdlet 的詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="e688b-136">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="e688b-137">如果您已建立原則，您可以使用[CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) Cmdlet 來變更現有的原則，然後使用[授與 CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) Cmdlet 將設定套用到您的使用者。</span><span class="sxs-lookup"><span data-stu-id="e688b-137">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a><span data-ttu-id="e688b-138">防止使用者使用行動裝置撥打電話給 IP 電話</span><span class="sxs-lookup"><span data-stu-id="e688b-138">Prevent a user from making voice over IP calls using a mobile device</span></span>

- <span data-ttu-id="e688b-139">若要為這些設定建立新的原則，請執行：</span><span class="sxs-lookup"><span data-stu-id="e688b-139">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   <span data-ttu-id="e688b-140">如需進一步瞭解，請參閱[新版 CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e688b-140">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="e688b-141">若要將您建立的新原則授與貴組織中的所有使用者，請執行：</span><span class="sxs-lookup"><span data-stu-id="e688b-141">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  <span data-ttu-id="e688b-142">如需[CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) Cmdlet 的詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="e688b-142">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
<span data-ttu-id="e688b-143">如果您已建立原則，您可以使用[CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) Cmdlet 來變更現有的原則，然後使用[授與 CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) Cmdlet 將設定套用到您的使用者。</span><span class="sxs-lookup"><span data-stu-id="e688b-143">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="e688b-144">想要深入瞭解 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="e688b-144">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="e688b-145">Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="e688b-145">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="e688b-146">在 Windows PowerShell 中，您可以使用單一管理點管理 Office 365 和商務用 Skype Online，當您有多個工作需要執行時，可簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="e688b-146">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="e688b-147">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="e688b-147">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="e688b-148">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="e688b-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="e688b-149">您可能會想要使用 Windows PowerShell 來管理 Office 365 的六個原因</span><span class="sxs-lookup"><span data-stu-id="e688b-149">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="e688b-150">Windows PowerShell 在速度、簡潔性和生產率上都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者設定變更時。</span><span class="sxs-lookup"><span data-stu-id="e688b-150">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="e688b-151">請參閱下列主題，瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="e688b-151">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="e688b-152">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="e688b-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="e688b-153">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="e688b-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="e688b-154">使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="e688b-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="e688b-155">相關主題</span><span class="sxs-lookup"><span data-stu-id="e688b-155">Related topics</span></span>
[<span data-ttu-id="e688b-156">建立自訂外部存取原則</span><span class="sxs-lookup"><span data-stu-id="e688b-156">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="e688b-157">封鎖點對端檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="e688b-157">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="e688b-158">設定組織的用戶端原則</span><span class="sxs-lookup"><span data-stu-id="e688b-158">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="e688b-159">在組織中設定會議原則</span><span class="sxs-lookup"><span data-stu-id="e688b-159">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
