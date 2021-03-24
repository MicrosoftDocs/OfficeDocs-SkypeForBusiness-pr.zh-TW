---
title: 系統管理員為個別使用者設定商務用 Skype 設定
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- LIL_Placement
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
description: '瞭解如何變更個別使用者的商務用 Skype 設定，例如：音訊和視訊會議、錄製通話和會議。 '
ms.openlocfilehash: 5ddad9b1502d0a271c20c412731c9872e247be1b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093387"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="90367-103">系統管理員：為個別使用者設定商務用 Skype 設定</span><span class="sxs-lookup"><span data-stu-id="90367-103">Admins: Configure Skype for Business settings for individual users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="90367-104">Microsoft Teams 系統管理中心已取代商務用 Skype 系統管理中心 (舊版) 。</span><span class="sxs-lookup"><span data-stu-id="90367-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="90367-105">管理商務用 Skype 的所有設定現在都位於 Teams 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="90367-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="90367-106">您必須被指派全域系統管理員或商務用 Skype 系統管理員的 Azure [AD](/azure/active-directory/roles/permissions-reference) 系統管理員角色，才能在 Teams 系統管理中心管理商務用 Skype 功能。</span><span class="sxs-lookup"><span data-stu-id="90367-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="90367-107">若要深入了解，請參閱[在 Microsoft Teams 系統管理中心中管理商務用 Skype 設定](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)。</span><span class="sxs-lookup"><span data-stu-id="90367-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="90367-108">本文將說明系統管理員如何為少數使用者設定商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="90367-108">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="90367-109">若要大量執行這些步驟，我們已提供您可以使用的 Windows PowerShell Cmdlet 連結。</span><span class="sxs-lookup"><span data-stu-id="90367-109">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="90367-110">若要允許 (或封鎖) 企業中的每個人與外部人員通訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="90367-110">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="90367-111">允許使用者與外部商務用[Skype](allow-users-to-contact-external-skype-for-business-users.md)使用者聯繫：您可以讓貴組織使用進一步商務用 Skype 功能 (共用桌面、尋找誰在線上等 ) 來與特定信任的 (聯盟) 企業的人員通訊。</span><span class="sxs-lookup"><span data-stu-id="90367-111">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="90367-112">本文也會說明如何封鎖與特定網域的通訊。</span><span class="sxs-lookup"><span data-stu-id="90367-112">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="90367-113">[讓商務用 Skype 使用者新增 Skype 連絡人](let-skype-for-business-users-add-skype-contacts.md)。</span><span class="sxs-lookup"><span data-stu-id="90367-113">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="90367-114">您可以讓貴組織使用商務用 Skype 搜尋並使用免費應用程式 Skype 的人員並 IM。</span><span class="sxs-lookup"><span data-stu-id="90367-114">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="90367-115">設定一位使用者的一般設定</span><span class="sxs-lookup"><span data-stu-id="90367-115">Configure general settings for one user</span></span>
<span data-ttu-id="90367-116"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="90367-116"><a name="__toc325019204"> </a></span></span>

<span data-ttu-id="90367-117">您必須擁有 [系統管理員許可權，才能](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="90367-117">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>

<span data-ttu-id="90367-118">![商務用 Skype 標誌圖示](../images/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="90367-118">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="90367-119">使用公司或學校帳戶來登錄。</span><span class="sxs-lookup"><span data-stu-id="90367-119">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="90367-120">選擇 **系統管理中心**  >  **商務用 Skype**。</span><span class="sxs-lookup"><span data-stu-id="90367-120">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="90367-121">選擇 **使用者**。</span><span class="sxs-lookup"><span data-stu-id="90367-121">Choose **Users**.</span></span>
    
    ![在商務用 Skype 系統管理中心，選擇使用者。](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="90367-123">選擇您想要編輯的使用者。</span><span class="sxs-lookup"><span data-stu-id="90367-123">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="90367-124">在右面板中 **，選擇編輯**。</span><span class="sxs-lookup"><span data-stu-id="90367-124">In the right panel, choose **Edit**.</span></span>
    
    ![選擇編輯圖示。](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="90367-126">在一 **般** 選項頁面上，選取或清除您想要變更的功能旁的核取方塊， **然後選擇儲存**。</span><span class="sxs-lookup"><span data-stu-id="90367-126">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="90367-127">**選項**</span><span class="sxs-lookup"><span data-stu-id="90367-127">**Option**</span></span>|<span data-ttu-id="90367-128">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="90367-128">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="90367-129">音訊和 HD 影片</span><span class="sxs-lookup"><span data-stu-id="90367-129">Audio and HD video</span></span>  <br/> |<span data-ttu-id="90367-130">允許此人錄製音訊會議、音訊和視訊會議，或不允許他們排程任何 (會議) 。</span><span class="sxs-lookup"><span data-stu-id="90367-130">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meetings (none).</span></span>  <br/> |
|<span data-ttu-id="90367-131">錄製交談和會議</span><span class="sxs-lookup"><span data-stu-id="90367-131">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="90367-132">選擇允許此人錄製哪些專案。</span><span class="sxs-lookup"><span data-stu-id="90367-132">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="90367-133">此選項不適用於商務用 Skype Basic。</span><span class="sxs-lookup"><span data-stu-id="90367-133">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="90367-134">針對合規性，請關閉未存檔的功能</span><span class="sxs-lookup"><span data-stu-id="90367-134">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="90367-135">如果您依法需要保留以電子方式儲存的資訊，請選擇這個選項。</span><span class="sxs-lookup"><span data-stu-id="90367-135">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="90367-136">選取此選項會關閉 Exchange 系統管理中心設定就地保留時未[](/exchange/security-and-compliance/in-place-and-litigation-holds)捕獲的功能。</span><span class="sxs-lookup"><span data-stu-id="90367-136">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](/exchange/security-and-compliance/in-place-and-litigation-holds) set up in the Exchange admin center.</span></span> <span data-ttu-id="90367-137">它會關閉下列功能：</span><span class="sxs-lookup"><span data-stu-id="90367-137">It turns off the following features:</span></span> <br/>  <span data-ttu-id="90367-138">使用立即訊息傳輸檔案</span><span class="sxs-lookup"><span data-stu-id="90367-138">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="90367-139">共用 OneNote 頁面</span><span class="sxs-lookup"><span data-stu-id="90367-139">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="90367-140">PowerPoint 注釋</span><span class="sxs-lookup"><span data-stu-id="90367-140">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="90367-141">若要大量設定這些設定，請使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="90367-141">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="90367-142">請參閱 [為 Windows PowerShell 設定您的電腦](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="90367-142">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="90367-143">封鎖外部通訊</span><span class="sxs-lookup"><span data-stu-id="90367-143">Block external communications</span></span>
<span data-ttu-id="90367-144"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="90367-144"><a name="__toc325019206"> </a></span></span>

<span data-ttu-id="90367-145">當您讓 [商務用 Skype 使用者為公司](let-skype-for-business-users-add-skype-contacts.md) 中的每個人新增 Skype 連絡人之後，您可以使用這些步驟選擇性地封鎖特定人員的外部通訊。</span><span class="sxs-lookup"><span data-stu-id="90367-145">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="90367-146">選擇 **使用者**，選取您想要停用其設定的使用者，然後選擇 **編輯編輯** ![ ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) 。</span><span class="sxs-lookup"><span data-stu-id="90367-146">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="90367-147">選擇 **外部通訊**，然後適當清除選項：</span><span class="sxs-lookup"><span data-stu-id="90367-147">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
   - <span data-ttu-id="90367-148">**外部商務** 用 Skype 使用者：如果您不希望使用者與在聯盟網域的商務用 Skype 使用者通訊，請清除此方塊。</span><span class="sxs-lookup"><span data-stu-id="90367-148">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
   - <span data-ttu-id="90367-149">**外部 Skype 使用者**：如果您不希望使用者能夠與使用 freeSkype 應用程式的人員通訊，請清除此方塊。</span><span class="sxs-lookup"><span data-stu-id="90367-149">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="90367-150">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="90367-150">Click **Save**.</span></span>
    
<span data-ttu-id="90367-151">若要大量設定這些設定，請使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="90367-151">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="90367-152">請參閱 [為 Windows PowerShell 設定您的電腦](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="90367-152">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="90367-153">編輯一個使用者的音訊會議設定</span><span class="sxs-lookup"><span data-stu-id="90367-153">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="90367-154"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="90367-154"><a name="__toc314837483"> </a></span></span>

1. <span data-ttu-id="90367-155">選擇 **使用者**，選取要編輯其音訊會議設定的使用者， **然後選擇編輯** ![ 編輯 ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) 。</span><span class="sxs-lookup"><span data-stu-id="90367-155">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="90367-156">選擇 **[音訊會議」，** 選取您的音訊會議提供者，輸入或變更要求的資訊，然後按一下 [ **儲存**。</span><span class="sxs-lookup"><span data-stu-id="90367-156">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="90367-157">**音訊會議設定**</span><span class="sxs-lookup"><span data-stu-id="90367-157">**Audio conferencing setting**</span></span>|<span data-ttu-id="90367-158">**描述**</span><span class="sxs-lookup"><span data-stu-id="90367-158">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="90367-159">**提供者名稱**</span><span class="sxs-lookup"><span data-stu-id="90367-159">**Provider name**</span></span> <br/> |<span data-ttu-id="90367-160">從清單中選擇您的提供者。</span><span class="sxs-lookup"><span data-stu-id="90367-160">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="90367-161">**必須撥打 (** 電話號碼) </span><span class="sxs-lookup"><span data-stu-id="90367-161">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="90367-162">對於協力廠商 ACP，這些電話號碼就是您從音訊會議提供者收到的號碼。</span><span class="sxs-lookup"><span data-stu-id="90367-162">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="90367-163">如果使用者使用 Microsoft 做為音訊會議提供者，這些號碼會設定在音訊會議橋接器上。</span><span class="sxs-lookup"><span data-stu-id="90367-163">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="90367-164">在商務用 Skype 和 Microsoft Teams 會議要求中，將數位格式格式化為您想要的數位。</span><span class="sxs-lookup"><span data-stu-id="90367-164">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="90367-165">**免付費號碼**</span><span class="sxs-lookup"><span data-stu-id="90367-165">**Toll-free number**</span></span> <br/> |<span data-ttu-id="90367-166">對於協力廠商 ACP，這些電話號碼就是您從音訊會議提供者收到的號碼。</span><span class="sxs-lookup"><span data-stu-id="90367-166">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="90367-167">如果使用者使用 Microsoft 做為音訊會議提供者，這些號碼會設定在音訊會議橋接器上。</span><span class="sxs-lookup"><span data-stu-id="90367-167">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="90367-168">在商務用 Skype 和 Microsoft Teams 會議要求中，格式化數位。</span><span class="sxs-lookup"><span data-stu-id="90367-168">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="90367-169">**會議 ID 和 PIN** (必須) </span><span class="sxs-lookup"><span data-stu-id="90367-169">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="90367-170">參與者 PIN 或會議代碼，用來加入此使用者排程的會議，且由協力廠商音訊會議提供者提供。</span><span class="sxs-lookup"><span data-stu-id="90367-170">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="90367-171">如果使用者使用 Microsoft 做為音訊會議提供者，則不需要這樣做。</span><span class="sxs-lookup"><span data-stu-id="90367-171">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="90367-172">若要大量設定這些設定，請使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="90367-172">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="90367-173">請參閱[設定邀請中包含的電話號碼](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md)[設定電腦以使用 Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="90367-173">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="90367-174">相關主題</span><span class="sxs-lookup"><span data-stu-id="90367-174">Related topics</span></span> 

[<span data-ttu-id="90367-175">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="90367-175">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="90367-176">商務用 Skype 和 Microsoft Teams 附加元件授權</span><span class="sxs-lookup"><span data-stu-id="90367-176">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
