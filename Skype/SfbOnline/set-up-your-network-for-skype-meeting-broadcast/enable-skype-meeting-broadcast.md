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
description: 在貴組織中人員使用會議廣播Skype之前，您必須啟用它。 若要這麼做，您必須知道如何使用Windows PowerShell。 如果您不知道Windows PowerShell，請考慮雇用 Microsoft 合作夥伴來執行此步驟。
ms.openlocfilehash: 6cdd7f12483025697b139203907f87f9cd3dc764
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237009"
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="29390-105">啟用 Skype 會議廣播</span><span class="sxs-lookup"><span data-stu-id="29390-105">Enable Skype Meeting Broadcast</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> <span data-ttu-id="29390-106">商務用 SkypeOnline 將于 2021 年 7 月 31 日終止服務存取權。</span><span class="sxs-lookup"><span data-stu-id="29390-106">Skype for Business Online is retiring on July 31, 2021, at which time access to the service will end.</span></span> <span data-ttu-id="29390-107">我們鼓勵客戶開始升級至 Microsoft Teams 中通訊和團隊合作的核心用戶端 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="29390-107">We encourage customers to begin the upgrade to Microsoft Teams, the core client for communications and teamwork in Microsoft 365.</span></span>

<span data-ttu-id="29390-108">在貴組織中人員使用會議廣播Skype之前，您必須啟用它。</span><span class="sxs-lookup"><span data-stu-id="29390-108">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it.</span></span> <span data-ttu-id="29390-109">若要這麼做，您必須知道如何使用Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="29390-109">To do this, you need to know how to use Windows PowerShell.</span></span> <span data-ttu-id="29390-110">如果您不知道Windows PowerShell，請考慮雇用[Microsoft 合作夥伴](https://go.microsoft.com/fwlink/?linkid=391089)來執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="29390-110">If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>



> [!NOTE]
> <span data-ttu-id="29390-111">系統Microsoft Teams系統管理中心已取代 商務用 Skype 系統管理中心 (舊版) 。</span><span class="sxs-lookup"><span data-stu-id="29390-111">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="29390-112">系統管理中心商務用 Skype所有管理Teams設定。</span><span class="sxs-lookup"><span data-stu-id="29390-112">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="29390-113">您必須指派全域系統管理員或系統管理員的[Azure AD](/azure/active-directory/roles/permissions-reference)系統管理員角色商務用 Skype，才能商務用 Skype系統管理中心Teams功能。</span><span class="sxs-lookup"><span data-stu-id="29390-113">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="29390-114">若要深入了解，請參閱[在 Microsoft Teams 系統管理中心中管理商務用 Skype 設定](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)。</span><span class="sxs-lookup"><span data-stu-id="29390-114">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="29390-115">使用 Skype 系統管理中心啟用商務用 Skype廣播</span><span class="sxs-lookup"><span data-stu-id="29390-115">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

<span data-ttu-id="29390-116">![商務用 Skype 標誌圖示](../images/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="29390-116">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="29390-117">使用全域系統管理員帳戶或 商務用 Skype 系統管理員帳戶來登錄 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) 。</span><span class="sxs-lookup"><span data-stu-id="29390-117">Sign in with your global admin account or Skype for Business admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="29390-118">在系統管理中心，前往 **系統管理**  >  **中心Teams。**</span><span class="sxs-lookup"><span data-stu-id="29390-118">In the admin center, go to **Admin centers** > **Teams**.</span></span>
    
3. <span data-ttu-id="29390-119">在 Teams **系統** 管理中心，前往舊版入口網站Online 會議 廣播會議，然後選取 Skype  >    >  \*\*\*\*\*\*會議廣播\*\*。</span><span class="sxs-lookup"><span data-stu-id="29390-119">In the **Teams admin center**, go to **Legacy portal** > **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="29390-120">使用 powerShell Skype會議廣播</span><span class="sxs-lookup"><span data-stu-id="29390-120">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="29390-121">安裝[powerShell Teams模組](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="29390-121">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="29390-122">開啟 Windows PowerShell命令提示符，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="29390-122">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
3. <span data-ttu-id="29390-123">請Skype會議廣播的目前狀態：</span><span class="sxs-lookup"><span data-stu-id="29390-123">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    <span data-ttu-id="29390-124">確認參數  _EnableBroadcastMeeting 設定_ 為 `False` 。</span><span class="sxs-lookup"><span data-stu-id="29390-124">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Skype會議廣播啟用組織 Cmdlet。](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. <span data-ttu-id="29390-126">請Skype組織啟用會議廣播：</span><span class="sxs-lookup"><span data-stu-id="29390-126">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    <span data-ttu-id="29390-127">您可以再次進行，確認已啟用  `Get-CsBroadcastMeetingConfiguration` 設定。</span><span class="sxs-lookup"><span data-stu-id="29390-127">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Skype會議廣播啟用組織 Cmdlet。](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="29390-129">進行變更之後，最多可能需要一小時，Skype會議廣播入口網站生效。</span><span class="sxs-lookup"><span data-stu-id="29390-129">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
10. <span data-ttu-id="29390-130">您的使用者現在可以與公司中的其他使用者召開廣播會議。</span><span class="sxs-lookup"><span data-stu-id="29390-130">Your users can now hold broadcast meetings with other users in your business.</span></span> <span data-ttu-id="29390-131">若要開始使用，請指向會議廣播Skype[內容？](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span><span class="sxs-lookup"><span data-stu-id="29390-131">To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="29390-132">設定您的網路以廣播與外部出席者的會議</span><span class="sxs-lookup"><span data-stu-id="29390-132">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="29390-133">如果您有防火牆，而且想要與公司外部人員 (非聯盟企業) 進行廣播，您必須使用以下指示來設定您的網路：設定您的網路以Skype 會議[廣播](set-up-your-network-for-skype-meeting-broadcast.md)。</span><span class="sxs-lookup"><span data-stu-id="29390-133">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="29390-134">如果您沒有防火牆的組組經驗，請考慮雇用 [Microsoft 合作夥伴](https://go.microsoft.com/fwlink/?linkid=391089) 來執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="29390-134">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="29390-135">若要略過此步驟，改為將另一個企業新增到您的聯盟，請參閱允許使用者與外部使用者[商務用 Skype聯絡](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)。</span><span class="sxs-lookup"><span data-stu-id="29390-135">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="29390-136">相關主題</span><span class="sxs-lookup"><span data-stu-id="29390-136">Related topics</span></span>

[<span data-ttu-id="29390-137">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="29390-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
[<span data-ttu-id="29390-138">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="29390-138">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
