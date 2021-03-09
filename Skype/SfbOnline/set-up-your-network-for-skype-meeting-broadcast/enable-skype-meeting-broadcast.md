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
description: 在貴組織的人員可以使用 Skype 會議廣播之前，您需要啟用 Skype 會議廣播。 若要這麼做，您必須知道如何使用 Windows PowerShell。 如果您不知道 Windows PowerShell，請考慮雇用 Microsoft 合作夥伴來執行此步驟。
ms.openlocfilehash: fed56c850d1d909bdd72bda0eb8c1dcd24df0f10
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2021
ms.locfileid: "50568889"
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="627fc-105">啟用 Skype 會議廣播</span><span class="sxs-lookup"><span data-stu-id="627fc-105">Enable Skype Meeting Broadcast</span></span>

> [!IMPORTANT]
> <span data-ttu-id="627fc-106">商務用 Skype Online 將于 2021 年 7 月 31 日終止服務存取權。</span><span class="sxs-lookup"><span data-stu-id="627fc-106">Skype for Business Online is retiring on July 31, 2021, at which time access to the service will end.</span></span> <span data-ttu-id="627fc-107">我們鼓勵客戶開始升級至 Microsoft 365 中通訊和團隊合作的核心用戶端 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="627fc-107">We encourage customers to begin the upgrade to Microsoft Teams, the core client for communications and teamwork in Microsoft 365.</span></span>

<span data-ttu-id="627fc-108">在貴組織的人員可以使用 Skype 會議廣播之前，您需要啟用 Skype 會議廣播。</span><span class="sxs-lookup"><span data-stu-id="627fc-108">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it.</span></span> <span data-ttu-id="627fc-109">若要這麼做，您必須知道如何使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="627fc-109">To do this, you need to know how to use Windows PowerShell.</span></span> <span data-ttu-id="627fc-110">如果您不知道 Windows PowerShell，請考慮雇用 Microsoft [合作夥伴](https://go.microsoft.com/fwlink/?linkid=391089) 來執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="627fc-110">If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>



> [!NOTE]
> <span data-ttu-id="627fc-111">Microsoft Teams 系統管理中心已取代商務用 Skype 系統管理中心 (舊版) 。</span><span class="sxs-lookup"><span data-stu-id="627fc-111">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="627fc-112">管理商務用 Skype 的所有設定現在都位於 Teams 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="627fc-112">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="627fc-113">您必須被指派全域系統管理員或商務用 Skype 系統管理員 [的 Azure AD](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) 系統管理員角色，才能在 Teams 系統管理中心管理商務用 Skype 功能。</span><span class="sxs-lookup"><span data-stu-id="627fc-113">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="627fc-114">若要深入了解，請參閱[在 Microsoft Teams 系統管理中心中管理商務用 Skype 設定](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)。</span><span class="sxs-lookup"><span data-stu-id="627fc-114">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="627fc-115">使用商務用 Skype 系統管理中心啟用 Skype 會議廣播</span><span class="sxs-lookup"><span data-stu-id="627fc-115">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

<span data-ttu-id="627fc-116">![商務用 Skype 標誌圖示](../images/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="627fc-116">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="627fc-117">使用全域系統管理員帳戶或商務用 Skype 系統管理員帳戶在 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) .</span><span class="sxs-lookup"><span data-stu-id="627fc-117">Sign in with your global admin account or Skype for Business admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="627fc-118">在系統管理中心，請前往 **系統管理中心**  >  **Teams。**</span><span class="sxs-lookup"><span data-stu-id="627fc-118">In the admin center, go to **Admin centers** > **Teams**.</span></span>
    
3. <span data-ttu-id="627fc-119">在 **Teams 系統管理中心**，前往 **舊版入口網站**  >  **Online 會議**  >  **廣播會議**，然後選取 **啟用 Skype 會議廣播**。</span><span class="sxs-lookup"><span data-stu-id="627fc-119">In the **Teams admin center**, go to **Legacy portal** > **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="627fc-120">使用 PowerShell 啟用 Skype 會議廣播</span><span class="sxs-lookup"><span data-stu-id="627fc-120">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="627fc-121">安裝 [Teams PowerShell 模組](https://docs.microsoft.com/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="627fc-121">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="627fc-122">開啟 Windows PowerShell 命令提示程式，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="627fc-122">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
3. <span data-ttu-id="627fc-123">請確認您目前的 Skype 會議廣播設置，請進行：</span><span class="sxs-lookup"><span data-stu-id="627fc-123">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    <span data-ttu-id="627fc-124">確認參數  _EnableBroadcastMeeting 已_ 設為 `False` 。</span><span class="sxs-lookup"><span data-stu-id="627fc-124">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Skype 會議廣播啟用組織 Cmdlet。](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. <span data-ttu-id="627fc-126">為貴組織啟用 Skype 會議廣播，請進行：</span><span class="sxs-lookup"><span data-stu-id="627fc-126">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    <span data-ttu-id="627fc-127">您可以再次進行，確認已啟用  `Get-CsBroadcastMeetingConfiguration` 該設定。</span><span class="sxs-lookup"><span data-stu-id="627fc-127">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Skype 會議廣播啟用組織 Cmdlet。](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="627fc-129">進行變更之後，最多可能需要一小時，Skype 會議廣播入口網站才生效。</span><span class="sxs-lookup"><span data-stu-id="627fc-129">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
10. <span data-ttu-id="627fc-130">您的使用者現在可以與公司中的其他使用者召開廣播會議。</span><span class="sxs-lookup"><span data-stu-id="627fc-130">Your users can now hold broadcast meetings with other users in your business.</span></span> <span data-ttu-id="627fc-131">若要開始使用，請將它們指向什麼是 [Skype 會議廣播？](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span><span class="sxs-lookup"><span data-stu-id="627fc-131">To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="627fc-132">設定您的網路以廣播與外部出席者的會議</span><span class="sxs-lookup"><span data-stu-id="627fc-132">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="627fc-133">如果您有防火牆，而且想要與公司外部人員 (非聯盟企業) 一起保留廣播，您需要使用以下指示設定您的網路：設定 Skype 會議廣播 [的網路](set-up-your-network-for-skype-meeting-broadcast.md)。</span><span class="sxs-lookup"><span data-stu-id="627fc-133">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="627fc-134">如果您還沒有防火牆的安裝經驗，請考慮雇用 [Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) 合作夥伴來執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="627fc-134">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="627fc-135">若要略過此步驟，改為將另一個企業新增到您的聯盟，請參閱允許使用者 [與外部商務用 Skype 使用者聯繫](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)。</span><span class="sxs-lookup"><span data-stu-id="627fc-135">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="627fc-136">相關主題</span><span class="sxs-lookup"><span data-stu-id="627fc-136">Related topics</span></span>

[<span data-ttu-id="627fc-137">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="627fc-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[<span data-ttu-id="627fc-138">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="627fc-138">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 
