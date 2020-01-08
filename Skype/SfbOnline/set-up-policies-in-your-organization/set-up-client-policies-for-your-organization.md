---
title: 設定組織的用戶端原則
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 用戶端原則可協助您判斷供使用者使用之商務用 Skype Online 的功能。例如，您可能會為部分使用者提供轉移檔案的許可權，而將此權利拒絕給其他使用者。
ms.openlocfilehash: d43094e8fbdbb25276b617f005cd71ce859d1362
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962561"
---
# <a name="set-up-client-policies-for-your-organization"></a><span data-ttu-id="0ecb9-103">設定組織的用戶端原則</span><span class="sxs-lookup"><span data-stu-id="0ecb9-103">Set up client policies for your organization</span></span>

<span data-ttu-id="0ecb9-104">用戶端原則可協助您判斷供使用者使用之商務用 Skype Online 的功能。例如，您可能會為部分使用者提供轉移檔案的許可權，而將此權利拒絕給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="0ecb9-104">Client policies help determine the features of Skype for Business Online that are made available to users; for example, you might give some users the right to transfer files while denying this right to other users.</span></span>
  
<span data-ttu-id="0ecb9-105">用戶端原則設定可以在建立原則時設定，或者您可以使用**CsClientPolicy** Cmdlet 來修改現有原則的設定。</span><span class="sxs-lookup"><span data-stu-id="0ecb9-105">Client policy settings can be configured at the time a policy is created, or you can use the **Set-CsClientPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-client-policies"></a><span data-ttu-id="0ecb9-106">設定您的用戶端原則</span><span class="sxs-lookup"><span data-stu-id="0ecb9-106">Set your client policies</span></span>

> [!NOTE]
> <span data-ttu-id="0ecb9-107">針對商務用 Skype Online 中的所有用戶端原則設定，您必須使用 Windows PowerShell，而且您**無法使用商務用** **Skype 系統管理中心**。</span><span class="sxs-lookup"><span data-stu-id="0ecb9-107">For all of the client policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="0ecb9-108">驗證並啟動 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0ecb9-108">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="0ecb9-109">**檢查您執行的是 Windows PowerShell 版本3.0 或更高版本**</span><span class="sxs-lookup"><span data-stu-id="0ecb9-109">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="0ecb9-110">若要確認您執行的是版本3.0 或更高版本： [**開始] 功能表** > **Windows PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="0ecb9-110">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="0ecb9-111">在**Windows PowerShell**視窗中輸入 [_取得主機_]，以檢查版本。</span><span class="sxs-lookup"><span data-stu-id="0ecb9-111">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="0ecb9-112">如果您沒有版本3.0 或更高版本，您需要下載並安裝 Windows PowerShell 更新。</span><span class="sxs-lookup"><span data-stu-id="0ecb9-112">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="0ecb9-113">請參閱[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) ，以下載並更新 Windows PowerShell 至版本4.0。</span><span class="sxs-lookup"><span data-stu-id="0ecb9-113">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="0ecb9-114">出現提示時，請重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="0ecb9-114">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="0ecb9-115">您也需要安裝適用于商務用 Skype Online 的 Windows PowerShell 模組，這可讓您建立連線到商務用 Skype Online 的遠端 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="0ecb9-115">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="0ecb9-116">此模組只受64位電腦支援，可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。</span><span class="sxs-lookup"><span data-stu-id="0ecb9-116">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="0ecb9-117">如果出現提示，請重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="0ecb9-117">Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="0ecb9-118">如果您需要進一步瞭解，請參閱[在單一 Windows PowerShell 視窗中連線至所有 Office 365 服務](https://technet.microsoft.com/library/dn568015.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0ecb9-118">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="0ecb9-119">**啟動 Windows PowerShell 會話**</span><span class="sxs-lookup"><span data-stu-id="0ecb9-119">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="0ecb9-120">從 [**開始] 功能表** > 中的 [**Windows PowerShell**]。</span><span class="sxs-lookup"><span data-stu-id="0ecb9-120">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="0ecb9-121">在**Windows PowerShell**視窗中，執行下列動作以連線到您的 Office 365 組織：</span><span class="sxs-lookup"><span data-stu-id="0ecb9-121">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0ecb9-122">您在第一次使用商務用 Skype Online Windows PowerShell 模組時，您只需執行匯**入模組**命令。</span><span class="sxs-lookup"><span data-stu-id="0ecb9-122">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

   ```PowerShell      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   <span data-ttu-id="0ecb9-123">如果您需要啟動 Windows PowerShell 的詳細資訊，請參閱[在單一 Windows powershell 視窗中連線至所有 Office 365 服務](https://technet.microsoft.com/library/dn568015.aspx)，或[設定您的 windows powershell 電腦](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="0ecb9-123">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a><span data-ttu-id="0ecb9-124">停用圖釋和目前狀態通知，並防止儲存 Im</span><span class="sxs-lookup"><span data-stu-id="0ecb9-124">Disable emoticons and presence notifications and prevent saving of IMs</span></span>

- <span data-ttu-id="0ecb9-125">若要為這些設定建立新的原則，請執行：</span><span class="sxs-lookup"><span data-stu-id="0ecb9-125">To create a new policy for these settings, run:</span></span>
    
> 
>   ```PowerShell
>   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
>   ```

  <span data-ttu-id="0ecb9-126">如需進一步瞭解，請參閱[新版 CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0ecb9-126">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="0ecb9-127">若要將您建立的新原則授與貴組織中的所有使用者，請執行：</span><span class="sxs-lookup"><span data-stu-id="0ecb9-127">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
> 
>   ```PowerShell
>   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
>   ```

  <span data-ttu-id="0ecb9-128">如需[CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) Cmdlet 的詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="0ecb9-128">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="0ecb9-129">如果您已建立原則，您可以使用[CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) Cmdlet 來變更現有的原則，然後使用[授與 CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) Cmdlet 將設定套用到您的使用者。</span><span class="sxs-lookup"><span data-stu-id="0ecb9-129">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a><span data-ttu-id="0ecb9-130">讓 Url 或超連結在 Im 中可按一下</span><span class="sxs-lookup"><span data-stu-id="0ecb9-130">Enable URLs or hyperlinks to be clickable in IMs</span></span>

- <span data-ttu-id="0ecb9-131">若要為這些設定建立新的原則，請執行：</span><span class="sxs-lookup"><span data-stu-id="0ecb9-131">To create a new policy for these settings, run:</span></span>
    
> 
>   ```PowerShell
>   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
>   ```

  <span data-ttu-id="0ecb9-132">如需進一步瞭解，請參閱[新版 CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0ecb9-132">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="0ecb9-133">若要將您建立的新原則授與貴組織中的所有使用者，請執行：</span><span class="sxs-lookup"><span data-stu-id="0ecb9-133">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
> 
>   ```PowerShell
>   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
>   ```

  <span data-ttu-id="0ecb9-134">如需[CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) Cmdlet 的詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="0ecb9-134">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="0ecb9-135">如果您已建立原則，您可以使用[CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) Cmdlet 來變更現有的原則，然後使用[授與 CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) Cmdlet 將設定套用到您的使用者。</span><span class="sxs-lookup"><span data-stu-id="0ecb9-135">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="prevent-showing-recent-contacts"></a><span data-ttu-id="0ecb9-136">避免顯示最近的連絡人</span><span class="sxs-lookup"><span data-stu-id="0ecb9-136">Prevent showing recent contacts</span></span>

- <span data-ttu-id="0ecb9-137">若要為這些設定建立新的原則，請執行：</span><span class="sxs-lookup"><span data-stu-id="0ecb9-137">To create a new policy for these settings, run:</span></span>
  > 
  > ```PowerShell
  > New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
  > ```

  <span data-ttu-id="0ecb9-138">如需進一步瞭解，請參閱[新版 CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0ecb9-138">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="0ecb9-139">若要將您建立的新原則授與 Amos 大理石，請執行：</span><span class="sxs-lookup"><span data-stu-id="0ecb9-139">To grant the new policy you created to Amos Marble, run:</span></span>
  > 
  > ```PowerShell
  > Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
  > ```

  <span data-ttu-id="0ecb9-140">如需[CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) Cmdlet 的詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="0ecb9-140">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="0ecb9-141">如果您已建立原則，您可以使用[CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) Cmdlet 來變更現有的原則，然後使用[授與 CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) Cmdlet 將設定套用到您的使用者。</span><span class="sxs-lookup"><span data-stu-id="0ecb9-141">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="0ecb9-142">想要深入瞭解 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="0ecb9-142">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="0ecb9-143">Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="0ecb9-143">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="0ecb9-144">在 Windows PowerShell 中，您可以使用單一管理點管理 Office 365 和商務用 Skype Online，當您有多個工作需要執行時，可簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="0ecb9-144">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="0ecb9-145">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="0ecb9-145">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="0ecb9-146">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="0ecb9-146">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="0ecb9-147">您可能會想要使用 Windows PowerShell 來管理 Office 365 的六個原因</span><span class="sxs-lookup"><span data-stu-id="0ecb9-147">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="0ecb9-148">Windows PowerShell 在速度、簡潔性和生產率上都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者設定變更時。</span><span class="sxs-lookup"><span data-stu-id="0ecb9-148">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="0ecb9-149">請參閱下列主題，瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="0ecb9-149">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="0ecb9-150">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="0ecb9-150">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="0ecb9-151">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="0ecb9-151">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="0ecb9-152">使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="0ecb9-152">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="0ecb9-153">相關主題</span><span class="sxs-lookup"><span data-stu-id="0ecb9-153">Related topics</span></span>
[<span data-ttu-id="0ecb9-154">建立自訂外部存取原則</span><span class="sxs-lookup"><span data-stu-id="0ecb9-154">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="0ecb9-155">封鎖點對端檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="0ecb9-155">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="0ecb9-156">在組織中設定會議原則</span><span class="sxs-lookup"><span data-stu-id="0ecb9-156">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
