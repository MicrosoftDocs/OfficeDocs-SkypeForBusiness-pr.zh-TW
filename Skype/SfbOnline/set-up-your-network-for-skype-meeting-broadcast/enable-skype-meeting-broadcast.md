---
title: 啟用 Skype 會議廣播
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
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
- SMB
description: 在貴組織中的人員可以使用 Skype 會議廣播之前，您必須先啟用它。 若要這樣做，您必須知道如何使用 Windows PowerShell。 如果您不知道 Windows PowerShell，請考慮聘用 Microsoft 合作夥伴來為您執行此步驟。
ms.openlocfilehash: 601cef096b032dd387de6d84bb7e676dc08054ec
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739051"
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="c5569-105">啟用 Skype 會議廣播</span><span class="sxs-lookup"><span data-stu-id="c5569-105">Enable Skype Meeting Broadcast</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5569-106">Microsoft 團隊系統管理中心已將商務用 Skype 系統管理中心 (舊版入口網站) 。</span><span class="sxs-lookup"><span data-stu-id="c5569-106">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="c5569-107">管理商務用 Skype 的所有設定現在都是在團隊系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="c5569-107">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="c5569-108">若要深入瞭解，請參閱在 [Microsoft 團隊系統管理中心管理商務用 Skype 設定](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)。</span><span class="sxs-lookup"><span data-stu-id="c5569-108">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="c5569-109">在貴組織中的人員可以使用 Skype 會議廣播之前，您必須先啟用它。</span><span class="sxs-lookup"><span data-stu-id="c5569-109">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it.</span></span> <span data-ttu-id="c5569-110">若要這樣做，您必須知道如何使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c5569-110">To do this, you need to know how to use Windows PowerShell.</span></span> <span data-ttu-id="c5569-111">如果您不知道 Windows PowerShell，請考慮聘用 [Microsoft 合作夥伴](https://go.microsoft.com/fwlink/?linkid=391089) 來為您執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="c5569-111">If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="c5569-112">使用商務用 Skype 系統管理中心啟用 Skype 會議廣播</span><span class="sxs-lookup"><span data-stu-id="c5569-112">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

<span data-ttu-id="c5569-113">![商務用 Skype 標誌圖示](../images/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="c5569-113">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="c5569-114">使用您的全域系統管理員帳戶或商務用 Skype 系統管理中心帳戶登入 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) 。</span><span class="sxs-lookup"><span data-stu-id="c5569-114">Sign in with your global admin account or Skype for Business admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="c5569-115">在系統管理中心中，移至 [系統**管理中心**]  >  **小組**。</span><span class="sxs-lookup"><span data-stu-id="c5569-115">In the admin center, go to **Admin centers** > **Teams**.</span></span>
    
3. <span data-ttu-id="c5569-116">在**團隊系統管理中心**中，移至**舊版入口網站**  >  **線上會議**  >  **廣播會議**，然後選取 [**啟用 Skype 會議廣播**]。</span><span class="sxs-lookup"><span data-stu-id="c5569-116">In the **Teams admin center**, go to **Legacy portal** > **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="c5569-117">使用 PowerShell 啟用 Skype 會議廣播</span><span class="sxs-lookup"><span data-stu-id="c5569-117">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="c5569-118">確認您執行的是 Windows PowerShell 版本3.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="c5569-118">Verify that you are running version 3.0 or higher of Windows PowerShell.</span></span>
    
2. <span data-ttu-id="c5569-119">若要確認您執行的是版本3.0 或更高版本： [**開始] 功能表**  >  **Windows PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="c5569-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
3. <span data-ttu-id="c5569-120">在**Windows PowerShell**視窗中輸入 [_取得主機_]，以檢查版本。</span><span class="sxs-lookup"><span data-stu-id="c5569-120">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
4. <span data-ttu-id="c5569-121">如果您沒有版本3.0 或更高版本，您需要下載並安裝 Windows PowerShell 更新。</span><span class="sxs-lookup"><span data-stu-id="c5569-121">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="c5569-122">請參閱 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) ，以下載並更新 Windows PowerShell 至版本4.0。</span><span class="sxs-lookup"><span data-stu-id="c5569-122">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="c5569-123">出現提示時，請重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="c5569-123">Restart your computer when you are prompted.</span></span>
    
5. <span data-ttu-id="c5569-124">您也需要安裝適用于商務用 Skype Online 的 Windows PowerShell 模組，這可讓您建立連線到商務用 Skype Online 的遠端 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="c5569-124">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="c5569-125">此模組只受64位電腦支援，可從 [適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。</span><span class="sxs-lookup"><span data-stu-id="c5569-125">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="c5569-126">如果出現提示，請重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="c5569-126">Restart your computer if you are prompted.</span></span>
    
6. <span data-ttu-id="c5569-127">從 [ **開始] 功能表**中，選擇 [ **Windows PowerShell**]。</span><span class="sxs-lookup"><span data-stu-id="c5569-127">From the **Start Menu**, choose **Windows PowerShell**.</span></span>
    
7. <span data-ttu-id="c5569-128">在 **Windows PowerShell** 視窗中，執行下列動作以連線至您的 Microsoft 365 或 Office 365：</span><span class="sxs-lookup"><span data-stu-id="c5569-128">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
   ```PowerShell
   $Credential = get-credential
   $O365Session = New-CsOnlineSession -Credential $credential
   Import-PSSession $O365Session
   ```

8. <span data-ttu-id="c5569-129">執行下列動作，以確認您目前的 Skype 會議廣播設定：</span><span class="sxs-lookup"><span data-stu-id="c5569-129">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    <span data-ttu-id="c5569-130">確認 [參數  _EnableBroadcastMeeting_ ] 已設定為 `False` 。</span><span class="sxs-lookup"><span data-stu-id="c5569-130">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Skype 會議廣播啟用組織 Cmdlet。](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. <span data-ttu-id="c5569-132">執行下列動作，為您的組織啟用 Skype 會議廣播：</span><span class="sxs-lookup"><span data-stu-id="c5569-132">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    <span data-ttu-id="c5569-133">您可以再次執行，確認已啟用該設定  `Get-CsBroadcastMeetingConfiguration` 。</span><span class="sxs-lookup"><span data-stu-id="c5569-133">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Skype 會議廣播啟用組織 Cmdlet。](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="c5569-135">進行變更之後，可能需要長達一小時的時間，才能在 Skype 會議廣播入口網站中生效。</span><span class="sxs-lookup"><span data-stu-id="c5569-135">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
10. <span data-ttu-id="c5569-136">您的使用者現在可以在您的企業中與其他使用者一起舉行廣播會議。</span><span class="sxs-lookup"><span data-stu-id="c5569-136">Your users can now hold broadcast meetings with other users in your business.</span></span> <span data-ttu-id="c5569-137">若要開始使用，請將其指向 [什麼是 Skype 會議廣播？](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span><span class="sxs-lookup"><span data-stu-id="c5569-137">To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="c5569-138">將您的網路設定為與外部出席者進行廣播會議</span><span class="sxs-lookup"><span data-stu-id="c5569-138">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="c5569-139">如果您有防火牆，而您想要在不是聯盟商務) 的 (企業以外的人員中，進行廣播，您必須使用下列指示來設定您的網路： [為您的 Skype 會議廣播設定您的網路](set-up-your-network-for-skype-meeting-broadcast.md)。</span><span class="sxs-lookup"><span data-stu-id="c5569-139">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="c5569-140">如果您不熟悉如何設定防火牆，請考慮聘用 [Microsoft 合作夥伴](https://go.microsoft.com/fwlink/?linkid=391089) 來為您執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="c5569-140">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="c5569-141">若要略過此步驟，而改為將其他公司新增到您的同盟，請參閱 [允許使用者聯繫外部商務用 Skype 使用者](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)。</span><span class="sxs-lookup"><span data-stu-id="c5569-141">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="c5569-142">相關主題</span><span class="sxs-lookup"><span data-stu-id="c5569-142">Related topics</span></span>

[<span data-ttu-id="c5569-143">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="c5569-143">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[<span data-ttu-id="c5569-144">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="c5569-144">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 
