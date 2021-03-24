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
description: 用戶端政策可協助判斷可供使用者使用的商務用 Skype Online 功能;例如，您可以給予部分使用者傳輸檔案的權利，同時拒絕將這項權利授予其他使用者。
ms.openlocfilehash: 3706e6b4fafe15aa8b799170001af61b837968da
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100529"
---
# <a name="set-up-client-policies-for-your-organization"></a><span data-ttu-id="41ebc-103">設定組織的用戶端原則</span><span class="sxs-lookup"><span data-stu-id="41ebc-103">Set up client policies for your organization</span></span>

<span data-ttu-id="41ebc-104">用戶端政策可協助判斷可供使用者使用的商務用 Skype Online 功能;例如，您可以給予部分使用者傳輸檔案的權利，同時拒絕將這項權利授予其他使用者。</span><span class="sxs-lookup"><span data-stu-id="41ebc-104">Client policies help determine the features of Skype for Business Online that are made available to users; for example, you might give some users the right to transfer files while denying this right to other users.</span></span>
  
<span data-ttu-id="41ebc-105">您可以在建立策略時設定用戶端策略設定，或者您可以使用 **Set-CsClientPolicy** Cmdlet 修改現有策略的設定。</span><span class="sxs-lookup"><span data-stu-id="41ebc-105">Client policy settings can be configured at the time a policy is created, or you can use the **Set-CsClientPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-client-policies"></a><span data-ttu-id="41ebc-106">設定用戶端策略</span><span class="sxs-lookup"><span data-stu-id="41ebc-106">Set your client policies</span></span>

> [!NOTE]
> <span data-ttu-id="41ebc-107">針對商務用 Skype Online 中所有的用戶端策略設定，您必須使用 Windows PowerShell，而且您不得使用 **商務用 Skype 系統管理中心**。 </span><span class="sxs-lookup"><span data-stu-id="41ebc-107">For all of the client policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="start-windows-powershell"></a><span data-ttu-id="41ebc-108">啟動 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="41ebc-108">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="41ebc-109">商務用 Skype Online Connector 目前是 Teams PowerShell 最新模組的一部分。</span><span class="sxs-lookup"><span data-stu-id="41ebc-109">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="41ebc-110">如果您使用的是最新的 Teams PowerShell 公開發行，則不需要安裝商務用 Skype Online 連接器。</span><span class="sxs-lookup"><span data-stu-id="41ebc-110">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="41ebc-111">安裝 [Teams PowerShell 模組](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="41ebc-111">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="41ebc-112">開啟 Windows PowerShell 命令提示符，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="41ebc-112">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="41ebc-113">如果您想要啟動 Windows PowerShell 的更多相關資訊，請參閱在單一 Windows PowerShell 視窗中連接到所有 [Microsoft 365 或 Office 365 服務](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) ，或設定 [電腦以使用 Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="41ebc-113">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
 
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a><span data-ttu-id="41ebc-114">停用圖釋和目前狀態通知，並防止保存 IMS</span><span class="sxs-lookup"><span data-stu-id="41ebc-114">Disable emoticons and presence notifications and prevent saving of IMs</span></span>

- <span data-ttu-id="41ebc-115">若要為這些設定建立新策略，請執行：</span><span class="sxs-lookup"><span data-stu-id="41ebc-115">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  <span data-ttu-id="41ebc-116">請參閱 [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="41ebc-116">See more on the [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="41ebc-117">若要將您建立的新政策授予貴組織中所有使用者，請執行：</span><span class="sxs-lookup"><span data-stu-id="41ebc-117">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  <span data-ttu-id="41ebc-118">請參閱 [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="41ebc-118">See more on the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet.</span></span>
    
<span data-ttu-id="41ebc-119">如果您已經建立原則，您可以使用 [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) Cmdlet 對現有原則進行變更，然後使用 [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) Cmdlet 將設定套用給使用者。</span><span class="sxs-lookup"><span data-stu-id="41ebc-119">If you have already created a policy, you can use the [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet to apply the settings to your users.</span></span>
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a><span data-ttu-id="41ebc-120">啟用 URL 或超連結在 IMs 中可按一下</span><span class="sxs-lookup"><span data-stu-id="41ebc-120">Enable URLs or hyperlinks to be clickable in IMs</span></span>

- <span data-ttu-id="41ebc-121">若要為這些設定建立新策略，請執行：</span><span class="sxs-lookup"><span data-stu-id="41ebc-121">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  <span data-ttu-id="41ebc-122">請參閱 [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="41ebc-122">See more on the [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="41ebc-123">若要將您建立的新政策授予貴組織中所有使用者，請執行：</span><span class="sxs-lookup"><span data-stu-id="41ebc-123">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  <span data-ttu-id="41ebc-124">請參閱 [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="41ebc-124">See more on the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet.</span></span>
    
<span data-ttu-id="41ebc-125">如果您已經建立原則，您可以使用 [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) Cmdlet 對現有原則進行變更，然後使用 [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) Cmdlet 將設定套用給使用者。</span><span class="sxs-lookup"><span data-stu-id="41ebc-125">If you have already created a policy, you can use the [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet to apply the settings to your users.</span></span>
  
### <a name="prevent-showing-recent-contacts"></a><span data-ttu-id="41ebc-126">防止顯示最近的連絡人</span><span class="sxs-lookup"><span data-stu-id="41ebc-126">Prevent showing recent contacts</span></span>

- <span data-ttu-id="41ebc-127">若要為這些設定建立新策略，請執行：</span><span class="sxs-lookup"><span data-stu-id="41ebc-127">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  <span data-ttu-id="41ebc-128">請參閱 [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="41ebc-128">See more on the [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="41ebc-129">若要將您建立的新政策授予 Amos Marble，請執行：</span><span class="sxs-lookup"><span data-stu-id="41ebc-129">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  <span data-ttu-id="41ebc-130">請參閱 [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="41ebc-130">See more on the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet.</span></span>
    
  <span data-ttu-id="41ebc-131">如果您已經建立原則，您可以使用 [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) Cmdlet 對現有原則進行變更，然後使用 [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) Cmdlet 將設定套用給使用者。</span><span class="sxs-lookup"><span data-stu-id="41ebc-131">If you have already created a policy, you can use the [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="41ebc-132">想要進一瞭解 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="41ebc-132">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="41ebc-133">Windows PowerShell 就是管理使用者，以及允許或不允許使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="41ebc-133">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="41ebc-134">使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365 和商務用 Skype Online，當您有多個工作需要執行時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="41ebc-134">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="41ebc-135">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="41ebc-135">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="41ebc-136">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="41ebc-136">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="41ebc-137">您可能會想要使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的六個原因</span><span class="sxs-lookup"><span data-stu-id="41ebc-137">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="41ebc-138">Windows PowerShell 比使用 Microsoft 365 系統管理中心在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。</span><span class="sxs-lookup"><span data-stu-id="41ebc-138">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="41ebc-139">請從下列主題瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="41ebc-139">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="41ebc-140">[使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="41ebc-140">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="41ebc-141">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="41ebc-141">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="41ebc-142">使用 Windows PowerShell 執行常見的商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="41ebc-142">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="41ebc-143">相關主題</span><span class="sxs-lookup"><span data-stu-id="41ebc-143">Related topics</span></span>
[<span data-ttu-id="41ebc-144">建立自訂外部存取原則</span><span class="sxs-lookup"><span data-stu-id="41ebc-144">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="41ebc-145">封鎖點到點檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="41ebc-145">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="41ebc-146">在組織中設定會議策略</span><span class="sxs-lookup"><span data-stu-id="41ebc-146">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
