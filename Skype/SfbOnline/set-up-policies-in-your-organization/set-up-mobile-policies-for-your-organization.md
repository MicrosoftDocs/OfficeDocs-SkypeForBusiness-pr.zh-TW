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
description: 您可以在行動裝置上設定使用者如何使用商務用 Skype 應用程式連線到商務用 Skype Online，例如讓使用者使用公司電話號碼而非行動電話號碼，在行動電話上撥打和接聽電話的功能。 行動性政策也可用來要求Wi-Fi或接聽來電時必須連上電話。
ms.openlocfilehash: 36162c64490edf58bbfac5c7022bebf6f39595ca
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569195"
---
# <a name="set-up-mobile-policies-for-your-organization"></a><span data-ttu-id="50ca0-104">設定組織的行動原則</span><span class="sxs-lookup"><span data-stu-id="50ca0-104">Set up mobile policies for your organization</span></span>

<span data-ttu-id="50ca0-105">您可以在行動裝置上設定使用者如何使用商務用 Skype 應用程式連線到商務用 Skype Online，例如讓使用者使用公司電話號碼而非行動電話號碼，在行動電話上撥打和接聽電話的功能。</span><span class="sxs-lookup"><span data-stu-id="50ca0-105">You can set up how your users connect to Skype for Business Online using the Skype for Business app on mobile devices, such as a feature that enables users to make and receive phone calls on their mobile phone by using their work phone number instead of their mobile phone number.</span></span> <span data-ttu-id="50ca0-106">行動性政策也可用來要求Wi-Fi或接聽來電時必須連上電話。</span><span class="sxs-lookup"><span data-stu-id="50ca0-106">Mobility policies can also be used to require Wi-Fi connections when making or receiving calls.</span></span>
  
<span data-ttu-id="50ca0-107">行動原則設定可以在建立原則時設定，或者您可以使用 **Set-CsMobilityPolicy** Cmdlet 修改現有原則的設定。</span><span class="sxs-lookup"><span data-stu-id="50ca0-107">Mobile policy settings can be configured at the time a policy is created, or you can use the **Set-CsMobilityPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-mobile-policies"></a><span data-ttu-id="50ca0-108">設定行動策略</span><span class="sxs-lookup"><span data-stu-id="50ca0-108">Set your mobile policies</span></span>

> [!NOTE]
> <span data-ttu-id="50ca0-109">針對商務用 Skype Online 中所有的行動策略設定，您必須使用 Windows PowerShell，而且不能使用商務用 **Skype 系統管理中心**。 </span><span class="sxs-lookup"><span data-stu-id="50ca0-109">For all of the mobile policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="start-windows-powershell"></a><span data-ttu-id="50ca0-110">啟動 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="50ca0-110">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="50ca0-111">商務用 Skype Online Connector 目前是最新 Teams PowerShell 模組的一部分。</span><span class="sxs-lookup"><span data-stu-id="50ca0-111">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="50ca0-112">如果您使用的是最新的 Teams PowerShell 公開發行，則不需要安裝商務用 Skype Online Connector。</span><span class="sxs-lookup"><span data-stu-id="50ca0-112">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="50ca0-113">安裝 [Teams PowerShell 模組](https://docs.microsoft.com/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="50ca0-113">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="50ca0-114">開啟 Windows PowerShell 命令提示程式，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="50ca0-114">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="50ca0-115">如果您想要有關啟動 Windows PowerShell 的資訊，請參閱在單一 Windows PowerShell 視窗中連接到所有[Microsoft 365 或 Office 365](https://technet.microsoft.com/library/dn568015.aspx)服務，或設定[您的電腦以使用 Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="50ca0-115">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
   
### <a name="require-a-wifi-connection-for-video-for-a-user"></a><span data-ttu-id="50ca0-116">使用者需要視音訊的 WiFi 連接</span><span class="sxs-lookup"><span data-stu-id="50ca0-116">Require a WiFi connection for video for a user</span></span>

- <span data-ttu-id="50ca0-117">若要為這些設定建立新策略，請執行：</span><span class="sxs-lookup"><span data-stu-id="50ca0-117">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   <span data-ttu-id="50ca0-118">查看 [New-CsMobilityPolicy Cmdlet](https://technet.microsoft.com/library/mt779150.aspx) 的更多資訊。</span><span class="sxs-lookup"><span data-stu-id="50ca0-118">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="50ca0-119">若要將您建立的新政策授予貴組織的所有使用者，請執行：</span><span class="sxs-lookup"><span data-stu-id="50ca0-119">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   <span data-ttu-id="50ca0-120">查看 [Grant-CsMobilityPolicy Cmdlet](https://technet.microsoft.com/library/mt779149.aspx) 的更多資訊。</span><span class="sxs-lookup"><span data-stu-id="50ca0-120">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="50ca0-121">如果您已經建立原則，您可以使用 [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) Cmdlet 對現有原則進行變更，然後使用[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) Cmdlet 將設定套用至您的使用者。</span><span class="sxs-lookup"><span data-stu-id="50ca0-121">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a><span data-ttu-id="50ca0-122">防止使用者使用商務用 Skype 應用程式</span><span class="sxs-lookup"><span data-stu-id="50ca0-122">Prevent a user from using the Skype for Business app</span></span>

- <span data-ttu-id="50ca0-123">若要為這些設定建立新策略，請執行：</span><span class="sxs-lookup"><span data-stu-id="50ca0-123">To create a new policy for these settings, run:</span></span>
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  <span data-ttu-id="50ca0-124">查看 [New-CsMobilityPolicy Cmdlet](https://technet.microsoft.com/library/mt779150.aspx) 的更多資訊。</span><span class="sxs-lookup"><span data-stu-id="50ca0-124">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="50ca0-125">若要將您建立的新策略授予 Amos Marble，請執行：</span><span class="sxs-lookup"><span data-stu-id="50ca0-125">To grant the new policy you created to Amos Marble, run:</span></span>  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   <span data-ttu-id="50ca0-126">查看 [Grant-CsMobilityPolicy Cmdlet](https://technet.microsoft.com/library/mt779149.aspx) 的更多資訊。</span><span class="sxs-lookup"><span data-stu-id="50ca0-126">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="50ca0-127">如果您已經建立原則，您可以使用 [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) Cmdlet 對現有原則進行變更，然後使用 [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) Cmdlet 將設定套用至您的使用者。</span><span class="sxs-lookup"><span data-stu-id="50ca0-127">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a><span data-ttu-id="50ca0-128">防止使用者使用行動裝置撥打 IP 電話</span><span class="sxs-lookup"><span data-stu-id="50ca0-128">Prevent a user from making voice over IP calls using a mobile device</span></span>

- <span data-ttu-id="50ca0-129">若要為這些設定建立新策略，請執行：</span><span class="sxs-lookup"><span data-stu-id="50ca0-129">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   <span data-ttu-id="50ca0-130">查看 [New-CsMobilityPolicy Cmdlet](https://technet.microsoft.com/library/mt779150.aspx) 的更多資訊。</span><span class="sxs-lookup"><span data-stu-id="50ca0-130">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="50ca0-131">若要將您建立的新政策授予貴組織的所有使用者，請執行：</span><span class="sxs-lookup"><span data-stu-id="50ca0-131">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  <span data-ttu-id="50ca0-132">查看 [Grant-CsMobilityPolicy Cmdlet](https://technet.microsoft.com/library/mt779149.aspx) 的更多資訊。</span><span class="sxs-lookup"><span data-stu-id="50ca0-132">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
<span data-ttu-id="50ca0-133">如果您已經建立原則，您可以使用 [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) Cmdlet 對現有原則進行變更，然後使用[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) Cmdlet 將設定套用至您的使用者。</span><span class="sxs-lookup"><span data-stu-id="50ca0-133">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="50ca0-134">想要進一瞭解更多 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="50ca0-134">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="50ca0-135">Windows PowerShell 就是管理使用者，以及允許或禁止使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="50ca0-135">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="50ca0-136">使用 Windows PowerShell，您可以使用單點系統管理來管理 Microsoft 365 或 Office 365 和商務用 Skype Online，當您有多個任務作時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="50ca0-136">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="50ca0-137">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="50ca0-137">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="50ca0-138">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="50ca0-138">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="50ca0-139">為何要使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的六個原因</span><span class="sxs-lookup"><span data-stu-id="50ca0-139">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="50ca0-140">Windows PowerShell 在速度、簡易性和生產力方面有許多優點，比只使用 Microsoft 365 系統管理中心有許多優點，例如當您一次為許多使用者進行設定變更時。</span><span class="sxs-lookup"><span data-stu-id="50ca0-140">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="50ca0-141">在下列主題中瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="50ca0-141">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="50ca0-142">使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="50ca0-142">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="50ca0-143">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="50ca0-143">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="50ca0-144">使用 Windows PowerShell 執行一般商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="50ca0-144">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="50ca0-145">相關主題</span><span class="sxs-lookup"><span data-stu-id="50ca0-145">Related topics</span></span>
[<span data-ttu-id="50ca0-146">建立自訂外部存取原則</span><span class="sxs-lookup"><span data-stu-id="50ca0-146">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="50ca0-147">封鎖點對點檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="50ca0-147">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="50ca0-148">設定組織的用戶端原則</span><span class="sxs-lookup"><span data-stu-id="50ca0-148">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="50ca0-149">在組織中設定會議策略</span><span class="sxs-lookup"><span data-stu-id="50ca0-149">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
