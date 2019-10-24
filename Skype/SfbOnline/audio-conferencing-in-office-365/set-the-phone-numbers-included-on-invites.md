---
title: 在商務用 Skype Online 中設定邀請中包含的電話號碼
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '取得建立呼叫者加入商務用 Skype Online 會議的預設電話號碼的步驟。 '
ms.openlocfilehash: b7f86f114601bf4e1658a65b5a8d6520c2785e1c
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/18/2019
ms.locfileid: "37642368"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a><span data-ttu-id="93f25-103">在商務用 Skype Online 中設定邀請中包含的電話號碼</span><span class="sxs-lookup"><span data-stu-id="93f25-103">Set the phone numbers included on invites in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="93f25-104">如需 Microsoft 團隊中會議邀請電話號碼的相關資訊，請參閱[在 Microsoft 團隊中設定邀請中所包含的電話號碼](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="93f25-104">For information about meeting invite phone numbers in Microsoft Teams, see [Set the phone numbers included on invites in Microsoft Teams](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams).</span></span>

<span data-ttu-id="93f25-105">Office 365 中的音訊會議可讓貴組織中的使用者建立商務用 Skype 會議，然後允許使用者使用電話撥入這些會議。</span><span class="sxs-lookup"><span data-stu-id="93f25-105">Audio Conferencing in Office 365 enables users in your organization to create Skype for Business meetings, and then allow users to dial in to those meetings using a phone.</span></span> <span data-ttu-id="93f25-106">在 Office 365 中，您可以選擇使用 Microsoft 音訊會議橋接器或由已核准的音訊會議提供者（ACP）託管的協力廠商音訊會議橋。</span><span class="sxs-lookup"><span data-stu-id="93f25-106">In Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span></span>
  
> [!NOTE]
> <span data-ttu-id="93f25-107">沒有一個資源包含所有撥入號碼的音訊會議清單。</span><span class="sxs-lookup"><span data-stu-id="93f25-107">There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing.</span></span> <span data-ttu-id="93f25-108">如果您想要查看您所在地區或國家/地區是否有撥入電話號碼，請使用商務用 Skype 系統**管理中心** > **語音** > **電話號碼** **，按一下 [** 新增]，然後輸入**新的服務號碼**.</span><span class="sxs-lookup"><span data-stu-id="93f25-108">If you are looking to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add** then **New Service Numbers**.</span></span> <span data-ttu-id="93f25-109">使用 [**國家/地區**]、[**州/地區**] 和 [**城市**] 的清單來篩選您的搜尋。 > 此外，如果您正在尋找免費的服務號碼，請從 [**省/市/自治區**] 清單中選取 [**免付費電話**]。</span><span class="sxs-lookup"><span data-stu-id="93f25-109">Use the lists for **Country/Region**, **State/Region** and **City** to filter your search.> Also, if you are looking for toll free service numbers, select **Toll-Free** from the **State/Region** list.</span></span>
  
<span data-ttu-id="93f25-110">「會議橋接」會為您的組織提供一組撥入電話號碼。</span><span class="sxs-lookup"><span data-stu-id="93f25-110">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="93f25-111">所有這些專案都可以用來加入會議召集人所建立的會議，但您可以選取哪些專案會包含在他們的會議邀請中。</span><span class="sxs-lookup"><span data-stu-id="93f25-111">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="93f25-112">在會議召集人的會議邀請中，最多隻能有一個付費電話號碼，還有一個免付費電話號碼，在每個會議邀請的底部，都會開啟完整的清單，其中包含可用於加入會議的所有電話撥入電話號碼。</span><span class="sxs-lookup"><span data-stu-id="93f25-112">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a><span data-ttu-id="93f25-113">設定會議召集人的預設撥入電話號碼</span><span class="sxs-lookup"><span data-stu-id="93f25-113">Set the default dial-in phone number for a meeting organizer</span></span>

1. <span data-ttu-id="93f25-114">使用您的公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="93f25-114">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="93f25-115">選擇系統**管理中心** > **的商務用 Skype**。</span><span class="sxs-lookup"><span data-stu-id="93f25-115">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="93f25-116">選擇 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="93f25-116">Choose **Users**.</span></span>
    
    ![顯示在商務用 Skype 系統管理中心中選取使用者](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. <span data-ttu-id="93f25-118">選擇您要編輯的使用者：</span><span class="sxs-lookup"><span data-stu-id="93f25-118">Choose the users you want to edit:</span></span>
    
   - <span data-ttu-id="93f25-119">若要選取單一使用者，請選取該使用者的名稱。</span><span class="sxs-lookup"><span data-stu-id="93f25-119">To select a single user, select the user's name.</span></span>
    
   - <span data-ttu-id="93f25-120">若要選取頁面上的所有使用者，請選取清單頂端 [**顯示名稱**] 旁的方塊。</span><span class="sxs-lookup"><span data-stu-id="93f25-120">To select all users on the page, select the box next to **Display name** at the top of the list.</span></span>
    
   - <span data-ttu-id="93f25-121">若要選取多個使用者，請選取每個使用者名稱旁的方塊。</span><span class="sxs-lookup"><span data-stu-id="93f25-121">To select multiple users, select the box next to each user's name.</span></span>
    
5. <span data-ttu-id="93f25-122">在右面板中，選擇 [Edit] （**編輯**）。</span><span class="sxs-lookup"><span data-stu-id="93f25-122">In the right panel, choose **Edit**.</span></span>
    
    ![選擇 [編輯] 圖示。](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="93f25-124">選擇 [**音訊會議**]。</span><span class="sxs-lookup"><span data-stu-id="93f25-124">Choose **Audio conferencing**.</span></span>
    
7. <span data-ttu-id="93f25-125">在 [**屬性**] 頁面的 [**提供者名稱**] 清單中，選擇使用者的提供者。</span><span class="sxs-lookup"><span data-stu-id="93f25-125">On the **Properties** page, in the **Provider name** list, choose the provider for the user.</span></span> <span data-ttu-id="93f25-126">視提供者而定，請完成下列方塊。</span><span class="sxs-lookup"><span data-stu-id="93f25-126">Depending on the provider, complete the following boxes.</span></span>
    
   - <span data-ttu-id="93f25-127">**Microsoft 是提供者**：使用**預設的付費電話號碼**和**預設的免付費電話號碼**清單來選取使用者的預設號碼。</span><span class="sxs-lookup"><span data-stu-id="93f25-127">**Microsoft is the provider**: Use the **Default toll number** and **Default toll-free number** lists to select the default numbers for the user.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="93f25-128">您必須先將至少一個免付費電話號碼指派給您的會議橋接器，才能將其設為使用者的預設免付費電話號碼。</span><span class="sxs-lookup"><span data-stu-id="93f25-128">At least one toll-free number must be assigned to your conferencing bridge before it can be set as the default toll-free number of a user.</span></span> <span data-ttu-id="93f25-129">若要取得免付費電話號碼，請參閱[取得商務用 Skype 的服務電話號碼](/microsoftteams/getting-service-phone-numbers)。</span><span class="sxs-lookup"><span data-stu-id="93f25-129">To get a toll-free number, see [Getting service phone numbers for Skype for Business](/microsoftteams/getting-service-phone-numbers).</span></span> 
  
   - <span data-ttu-id="93f25-130">**協力廠商是提供者**：使用 [**付費電話號碼**] 和 [**免付費電話號碼**] 欄位輸入使用者的號碼。</span><span class="sxs-lookup"><span data-stu-id="93f25-130">**A third-party is the provider**: Use the **Toll number** and **Toll-free number** fields to enter the numbers for the user.</span></span>


## <a name="reset-audio-conferencing-phone-numbers"></a><span data-ttu-id="93f25-131">重設音訊會議電話號碼</span><span class="sxs-lookup"><span data-stu-id="93f25-131">Reset audio conferencing phone numbers</span></span>

1. <span data-ttu-id="93f25-132">在**商務用 Skype 系統管理中心**中，選擇 [**音訊會議**]。</span><span class="sxs-lookup"><span data-stu-id="93f25-132">In the **Skype for Business admin center**, choose **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="93f25-133">在頁面頂端，選擇 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="93f25-133">At the top of the page, choose **Users**.</span></span>
    
3. <span data-ttu-id="93f25-134">選擇您要重設的使用者，然後在 [動作] 窗格中，按一下 [**清除**]。</span><span class="sxs-lookup"><span data-stu-id="93f25-134">Choose the users you want to reset, and then in the Action pane, click **Clear**.</span></span>
    
<span data-ttu-id="93f25-135">根據預設，當您變更使用者的會議設定時，系統會傳送電子郵件給使用者。</span><span class="sxs-lookup"><span data-stu-id="93f25-135">By default, when you change a user's conferencing settings, an email is sent to the user.</span></span> <span data-ttu-id="93f25-136">若要變更此設定，請參閱[在音訊會議設定變更時啟用或停用傳送電子郵件](enable-or-disable-sending-emails-when-their-settings-change.md)。</span><span class="sxs-lookup"><span data-stu-id="93f25-136">To change this, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="93f25-137">當您變更使用者的音訊會議設定時，必須更新週期性及未來的商務用 Skype 會議，並傳送給出席者。</span><span class="sxs-lookup"><span data-stu-id="93f25-137">When you change a user's audio conferencing settings, recurring and future Skype for Business meetings must be updated and sent to attendees.</span></span> 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="93f25-138">想知道如何使用 Windows PowerShell 進行管理嗎？</span><span class="sxs-lookup"><span data-stu-id="93f25-138">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="93f25-139">若要節省時間或將這項作業自動化，您可以使用[get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617688) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="93f25-139">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet.</span></span>
    
- <span data-ttu-id="93f25-140">使用[get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617688) Cmdlet 來變更特定使用者的預設付費或免付費電話號碼。</span><span class="sxs-lookup"><span data-stu-id="93f25-140">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>
    
    <span data-ttu-id="93f25-141">若要變更使用者的預設免付費電話號碼，請執行：</span><span class="sxs-lookup"><span data-stu-id="93f25-141">To change the default toll-free number for a user, run:</span></span>
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- <span data-ttu-id="93f25-142">使用**CsOnlineDialInConferencingUserDefaultNumber** Cmdlet 根據原始預設號碼或其位置來變更預設的付費或免付費使用者數目。</span><span class="sxs-lookup"><span data-stu-id="93f25-142">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="93f25-143">若要尋找 BridgeID，請使用**CsOnlineDialInConferencingBridge** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="93f25-143">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge** cmdlet.</span></span>
  
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - <span data-ttu-id="93f25-144">若要為所有不含1到 + 18005551234 的使用者設定預設免付費電話號碼，請執行：</span><span class="sxs-lookup"><span data-stu-id="93f25-144">To set the default toll-free number for all users without one to +18005551234, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - <span data-ttu-id="93f25-145">若要將擁有 + 18005551234 的所有使用者的預設免付費電話號碼改為預設的免付費電話號碼至 + 18005551239，請執行：</span><span class="sxs-lookup"><span data-stu-id="93f25-145">To change the default toll-free number of all users that have +18005551234 as their default toll-free number to +18005551239, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="93f25-146">若要將美國所有使用者的預設免付費電話號碼設定為 + 18005551234，請執行：</span><span class="sxs-lookup"><span data-stu-id="93f25-146">To set the default toll-free number of all users located in the U.S. to +18005551234, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
  ## <a name="want-to-learn-more-about-windows-powershell"></a><span data-ttu-id="93f25-147">想要深入瞭解 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="93f25-147">Want to learn more about Windows PowerShell?</span></span>
- <span data-ttu-id="93f25-148">若要使用 Windows PowerShell，請參閱管理使用者和允許或不允許的使用者。</span><span class="sxs-lookup"><span data-stu-id="93f25-148">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="93f25-149">在 Windows PowerShell 中，您可以使用單一管理點管理 Office 365 和商務用 Skype Online，當您有多個工作需要執行時，可簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="93f25-149">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="93f25-150">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="93f25-150">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="93f25-151">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="93f25-151">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="93f25-152">為什麼需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="93f25-152">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="93f25-153">Windows PowerShell 在速度、簡潔性和生產率上都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者設定變更時。</span><span class="sxs-lookup"><span data-stu-id="93f25-153">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="93f25-154">請參閱下列主題，瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="93f25-154">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="93f25-155">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="93f25-155">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="93f25-156">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="93f25-156">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="93f25-157">使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="93f25-157">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="93f25-158">相關主題</span><span class="sxs-lookup"><span data-stu-id="93f25-158">Related topics</span></span>

[<span data-ttu-id="93f25-159">在 Office 365 中試用或購買音訊會議</span><span class="sxs-lookup"><span data-stu-id="93f25-159">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
