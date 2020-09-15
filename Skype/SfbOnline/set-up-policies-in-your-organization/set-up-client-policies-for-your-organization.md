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
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 用戶端原則可協助您判斷供使用者使用之商務用 Skype Online 的功能。例如，您可能會為部分使用者提供轉移檔案的許可權，而將此權利拒絕給其他使用者。
ms.openlocfilehash: 3a7dd7a2840a4e94abe88c472e6dc5b0e1720704
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814352"
---
# <a name="set-up-client-policies-for-your-organization"></a><span data-ttu-id="f9cf7-103">設定組織的用戶端原則</span><span class="sxs-lookup"><span data-stu-id="f9cf7-103">Set up client policies for your organization</span></span>

<span data-ttu-id="f9cf7-104">用戶端原則可協助您判斷供使用者使用之商務用 Skype Online 的功能。例如，您可能會為部分使用者提供轉移檔案的許可權，而將此權利拒絕給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="f9cf7-104">Client policies help determine the features of Skype for Business Online that are made available to users; for example, you might give some users the right to transfer files while denying this right to other users.</span></span>
  
<span data-ttu-id="f9cf7-105">用戶端原則設定可以在建立原則時設定，或者您可以使用 **CsClientPolicy** Cmdlet 來修改現有原則的設定。</span><span class="sxs-lookup"><span data-stu-id="f9cf7-105">Client policy settings can be configured at the time a policy is created, or you can use the **Set-CsClientPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-client-policies"></a><span data-ttu-id="f9cf7-106">設定您的用戶端原則</span><span class="sxs-lookup"><span data-stu-id="f9cf7-106">Set your client policies</span></span>

> [!NOTE]
> <span data-ttu-id="f9cf7-107">針對商務用 Skype Online 中的所有用戶端原則設定，您必須使用 Windows PowerShell，而且您 **無法使用商務用** **Skype 系統管理中心**。</span><span class="sxs-lookup"><span data-stu-id="f9cf7-107">For all of the client policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="f9cf7-108">驗證並啟動 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f9cf7-108">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="f9cf7-109">**檢查您執行的是 Windows PowerShell 版本3.0 或更高版本**</span><span class="sxs-lookup"><span data-stu-id="f9cf7-109">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="f9cf7-110">若要確認您執行的是版本3.0 或更高版本： [**開始] 功能表**  >  **Windows PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="f9cf7-110">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="f9cf7-111">在**Windows PowerShell**視窗中輸入 [_取得主機_]，以檢查版本。</span><span class="sxs-lookup"><span data-stu-id="f9cf7-111">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="f9cf7-112">如果您沒有版本3.0 或更高版本，您需要下載並安裝 Windows PowerShell 更新。</span><span class="sxs-lookup"><span data-stu-id="f9cf7-112">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="f9cf7-113">請參閱 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) ，以下載並更新 Windows PowerShell 至版本4.0。</span><span class="sxs-lookup"><span data-stu-id="f9cf7-113">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="f9cf7-114">出現提示時，請重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="f9cf7-114">Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="f9cf7-115">您也需要安裝 Windows PowerShell 模組供團隊使用，讓您建立連線到商務用 Skype Online 的遠端 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="f9cf7-115">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> 
    
    <span data-ttu-id="f9cf7-116">如果您需要進一步瞭解，請參閱 [在單一 Windows PowerShell 視窗中連線至所有 Microsoft 365 或 Office 365 服務](https://technet.microsoft.com/library/dn568015.aspx)。</span><span class="sxs-lookup"><span data-stu-id="f9cf7-116">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="f9cf7-117">**啟動 Windows PowerShell 會話**</span><span class="sxs-lookup"><span data-stu-id="f9cf7-117">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="f9cf7-118">從 [**開始] 功能表**中的 [  >  **Windows PowerShell**]。</span><span class="sxs-lookup"><span data-stu-id="f9cf7-118">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="f9cf7-119">在 **Windows PowerShell** 視窗中，執行下列動作以連線至您的 Microsoft 365 或 Office 365：</span><span class="sxs-lookup"><span data-stu-id="f9cf7-119">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f9cf7-120">商務用 Skype Online 連接器目前是最新團隊 PowerShell 模組的一部分。</span><span class="sxs-lookup"><span data-stu-id="f9cf7-120">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
    >
    > <span data-ttu-id="f9cf7-121">如果您使用的是最新的 [團隊 PowerShell 公開發行](https://www.powershellgallery.com/packages/MicrosoftTeams/)，就不需要安裝商務用 Skype Online 連接器。</span><span class="sxs-lookup"><span data-stu-id="f9cf7-121">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

       ```powershell
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session 
       ```
<span data-ttu-id="f9cf7-122">如果您需要啟動 Windows PowerShell 的詳細資訊，請參閱 [在單一 Windows powershell 視窗中連線至所有 Microsoft 365 或 Office 365 服務](https://technet.microsoft.com/library/dn568015.aspx) ，或 [設定您的 windows powershell 電腦](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="f9cf7-122">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a><span data-ttu-id="f9cf7-123">停用圖釋和目前狀態通知，並防止儲存 Im</span><span class="sxs-lookup"><span data-stu-id="f9cf7-123">Disable emoticons and presence notifications and prevent saving of IMs</span></span>

- <span data-ttu-id="f9cf7-124">若要為這些設定建立新的原則，請執行：</span><span class="sxs-lookup"><span data-stu-id="f9cf7-124">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  <span data-ttu-id="f9cf7-125">如需進一步瞭解，請參閱 [新版 CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f9cf7-125">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="f9cf7-126">若要將您建立的新原則授與貴組織中的所有使用者，請執行：</span><span class="sxs-lookup"><span data-stu-id="f9cf7-126">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  <span data-ttu-id="f9cf7-127">如需 [CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) Cmdlet 的詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="f9cf7-127">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="f9cf7-128">如果您已建立原則，您可以使用 [CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) Cmdlet 來變更現有的原則，然後使用 [授與 CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) Cmdlet 將設定套用到您的使用者。</span><span class="sxs-lookup"><span data-stu-id="f9cf7-128">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a><span data-ttu-id="f9cf7-129">讓 Url 或超連結在 Im 中可按一下</span><span class="sxs-lookup"><span data-stu-id="f9cf7-129">Enable URLs or hyperlinks to be clickable in IMs</span></span>

- <span data-ttu-id="f9cf7-130">若要為這些設定建立新的原則，請執行：</span><span class="sxs-lookup"><span data-stu-id="f9cf7-130">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  <span data-ttu-id="f9cf7-131">如需進一步瞭解，請參閱 [新版 CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f9cf7-131">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="f9cf7-132">若要將您建立的新原則授與貴組織中的所有使用者，請執行：</span><span class="sxs-lookup"><span data-stu-id="f9cf7-132">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  <span data-ttu-id="f9cf7-133">如需 [CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) Cmdlet 的詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="f9cf7-133">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="f9cf7-134">如果您已建立原則，您可以使用 [CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) Cmdlet 來變更現有的原則，然後使用 [授與 CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) Cmdlet 將設定套用到您的使用者。</span><span class="sxs-lookup"><span data-stu-id="f9cf7-134">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="prevent-showing-recent-contacts"></a><span data-ttu-id="f9cf7-135">避免顯示最近的連絡人</span><span class="sxs-lookup"><span data-stu-id="f9cf7-135">Prevent showing recent contacts</span></span>

- <span data-ttu-id="f9cf7-136">若要為這些設定建立新的原則，請執行：</span><span class="sxs-lookup"><span data-stu-id="f9cf7-136">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  <span data-ttu-id="f9cf7-137">如需進一步瞭解，請參閱 [新版 CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f9cf7-137">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="f9cf7-138">若要將您建立的新原則授與 Amos 大理石，請執行：</span><span class="sxs-lookup"><span data-stu-id="f9cf7-138">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  <span data-ttu-id="f9cf7-139">如需 [CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) Cmdlet 的詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="f9cf7-139">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="f9cf7-140">如果您已建立原則，您可以使用 [CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) Cmdlet 來變更現有的原則，然後使用 [授與 CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) Cmdlet 將設定套用到您的使用者。</span><span class="sxs-lookup"><span data-stu-id="f9cf7-140">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="f9cf7-141">想要深入瞭解 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="f9cf7-141">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="f9cf7-142">Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="f9cf7-142">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="f9cf7-143">在 Windows PowerShell 中，您可以使用單一管理點管理 Microsoft 365 或 Office 365 及商務用 Skype Online，當您有多個工作需要執行時，可簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="f9cf7-143">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="f9cf7-144">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="f9cf7-144">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f9cf7-145">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="f9cf7-145">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="f9cf7-146">您可能會想要使用 Windows PowerShell 來管理 Microsoft 365 或 Office 365 的六個原因</span><span class="sxs-lookup"><span data-stu-id="f9cf7-146">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="f9cf7-147">Windows PowerShell 在速度、簡潔性和生產率上都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者設定變更時。</span><span class="sxs-lookup"><span data-stu-id="f9cf7-147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="f9cf7-148">請參閱下列主題，瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="f9cf7-148">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="f9cf7-149">使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="f9cf7-149">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="f9cf7-150">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="f9cf7-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="f9cf7-151">使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="f9cf7-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="f9cf7-152">相關主題</span><span class="sxs-lookup"><span data-stu-id="f9cf7-152">Related topics</span></span>
[<span data-ttu-id="f9cf7-153">建立自訂外部存取原則</span><span class="sxs-lookup"><span data-stu-id="f9cf7-153">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="f9cf7-154">封鎖點對端檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="f9cf7-154">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="f9cf7-155">在組織中設定會議原則</span><span class="sxs-lookup"><span data-stu-id="f9cf7-155">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
