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
description: '瞭解如何變更個別使用者的商務用 Skype 設定，例如音訊與視訊會議、通話和會議的錄製。 '
ms.openlocfilehash: d6054db4bfdd8b161dca427237a10d70ba558fcb
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41769686"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="50e3a-103">系統管理員：針對個別使用者設定商務用 Skype 設定</span><span class="sxs-lookup"><span data-stu-id="50e3a-103">Admins: Configure Skype for Business settings for individual users</span></span>

<span data-ttu-id="50e3a-104">本文說明管理員如何為少數使用者設定商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="50e3a-104">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="50e3a-105">若要大量執行這些步驟，我們提供了您可以使用的 Windows PowerShell Cmdlet 連結。</span><span class="sxs-lookup"><span data-stu-id="50e3a-105">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="50e3a-106">若要允許（或封鎖）貴公司中的每個人都與外部人員通訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="50e3a-106">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="50e3a-107">[允許使用者與外部商務用 skype 使用者取得聯繫](allow-users-to-contact-external-skype-for-business-users.md)：您可以讓您的組織使用高級商務用 skype 功能（共用桌面、尋找誰在線上，等等）與特定信任（同盟）業務中的人員進行通訊。</span><span class="sxs-lookup"><span data-stu-id="50e3a-107">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="50e3a-108">本文也說明如何封鎖與特定網域的通訊。</span><span class="sxs-lookup"><span data-stu-id="50e3a-108">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="50e3a-109">[讓商務用 Skype 使用者新增 skype 連絡人](let-skype-for-business-users-add-skype-contacts.md)。</span><span class="sxs-lookup"><span data-stu-id="50e3a-109">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="50e3a-110">您可以讓您的組織使用商務用 Skype 來搜尋與使用 Skype 的 IM 人員（免費應用程式）。</span><span class="sxs-lookup"><span data-stu-id="50e3a-110">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="50e3a-111">設定一位使用者的一般設定</span><span class="sxs-lookup"><span data-stu-id="50e3a-111">Configure general settings for one user</span></span>
<span data-ttu-id="50e3a-112"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="50e3a-112"><a name="__toc325019204"> </a></span></span>

<span data-ttu-id="50e3a-113">您必須具備系統[管理員許可權](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)才能執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="50e3a-113">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>

<span data-ttu-id="50e3a-114">![](../images/sfb-logo-30x30.png) **使用商務用 skype 系統管理中心**顯示商務用 skype 標誌的圖示</span><span class="sxs-lookup"><span data-stu-id="50e3a-114">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="50e3a-115">使用您的公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="50e3a-115">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="50e3a-116">選擇系統**管理中心** > **的商務用 Skype**。</span><span class="sxs-lookup"><span data-stu-id="50e3a-116">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="50e3a-117">選擇 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="50e3a-117">Choose **Users**.</span></span>
    
    ![在商務用 Skype 系統管理中心中，選擇 [使用者]。](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="50e3a-119">選擇您要編輯的使用者。</span><span class="sxs-lookup"><span data-stu-id="50e3a-119">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="50e3a-120">在右面板中，選擇 [Edit] （**編輯**）。</span><span class="sxs-lookup"><span data-stu-id="50e3a-120">In the right panel, choose **Edit**.</span></span>
    
    ![選擇 [編輯] 圖示。](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="50e3a-122">在 [**一般**] 選項頁面上，選取或清除您想要變更之功能旁的核取方塊，然後選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="50e3a-122">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="50e3a-123">**件**</span><span class="sxs-lookup"><span data-stu-id="50e3a-123">**Option**</span></span>|<span data-ttu-id="50e3a-124">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="50e3a-124">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="50e3a-125">音訊及 HD 影片</span><span class="sxs-lookup"><span data-stu-id="50e3a-125">Audio and HD video</span></span>  <br/> |<span data-ttu-id="50e3a-126">允許此人錄製音訊會議、音訊及視訊會議，或不允許他們排程任何會議（無）。</span><span class="sxs-lookup"><span data-stu-id="50e3a-126">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meetings (none).</span></span>  <br/> |
|<span data-ttu-id="50e3a-127">記錄交談和會議</span><span class="sxs-lookup"><span data-stu-id="50e3a-127">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="50e3a-128">選擇 [允許此人錄製的內容]。</span><span class="sxs-lookup"><span data-stu-id="50e3a-128">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="50e3a-129">[商務用 Skype 基本版] 無法使用此選項。</span><span class="sxs-lookup"><span data-stu-id="50e3a-129">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="50e3a-130">針對合規性，請關閉未存檔的功能</span><span class="sxs-lookup"><span data-stu-id="50e3a-130">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="50e3a-131">如果您在法律上需要保留電子儲存資訊，請選擇此選項。</span><span class="sxs-lookup"><span data-stu-id="50e3a-131">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="50e3a-132">選取此選項會關閉您在 Exchange 系統管理中心設定[就地保留](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx)時不會捕獲的功能。</span><span class="sxs-lookup"><span data-stu-id="50e3a-132">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) set up in the Exchange admin center.</span></span> <span data-ttu-id="50e3a-133">它會關閉下列功能：</span><span class="sxs-lookup"><span data-stu-id="50e3a-133">It turns off the following features:</span></span> <br/>  <span data-ttu-id="50e3a-134">使用立即訊息傳輸檔案</span><span class="sxs-lookup"><span data-stu-id="50e3a-134">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="50e3a-135">共用的 OneNote 頁面</span><span class="sxs-lookup"><span data-stu-id="50e3a-135">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="50e3a-136">PowerPoint 注釋</span><span class="sxs-lookup"><span data-stu-id="50e3a-136">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="50e3a-137">若要大量設定這些設定，請使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="50e3a-137">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="50e3a-138">請參閱[設定您的 Windows PowerShell 電腦](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="50e3a-138">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="50e3a-139">封鎖外部通訊</span><span class="sxs-lookup"><span data-stu-id="50e3a-139">Block external communications</span></span>
<span data-ttu-id="50e3a-140"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="50e3a-140"><a name="__toc325019206"> </a></span></span>

<span data-ttu-id="50e3a-141">在您[讓商務用 skype 使用者](let-skype-for-business-users-add-skype-contacts.md)為公司中的每個人新增 Skype 連絡人之後，您就可以使用這些步驟選擇性地封鎖特定人員的外部通訊。</span><span class="sxs-lookup"><span data-stu-id="50e3a-141">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="50e3a-142">選擇 [**使用者**]，選取您要停用其設定的使用者，然後選擇 [](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png)**編輯** ![編輯]。</span><span class="sxs-lookup"><span data-stu-id="50e3a-142">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="50e3a-143">選擇 [**外部通訊**]，然後視需要清除這些選項：</span><span class="sxs-lookup"><span data-stu-id="50e3a-143">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
   - <span data-ttu-id="50e3a-144">**外部商務用 Skype 使用者**：如果您不想讓使用者能夠與聯盟網域中的商務用 skype 使用者通訊，請清除此方塊。</span><span class="sxs-lookup"><span data-stu-id="50e3a-144">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
   - <span data-ttu-id="50e3a-145">**外部 Skype 使用者**：如果您不希望使用者能夠與使用 freeSkype 應用程式的人員進行通訊，請清除此方塊。</span><span class="sxs-lookup"><span data-stu-id="50e3a-145">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="50e3a-146">按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="50e3a-146">Click **Save**.</span></span>
    
<span data-ttu-id="50e3a-147">若要大量設定這些設定，請使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="50e3a-147">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="50e3a-148">請參閱[設定您的 Windows PowerShell 電腦](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="50e3a-148">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="50e3a-149">編輯一位使用者的音訊會議設定</span><span class="sxs-lookup"><span data-stu-id="50e3a-149">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="50e3a-150"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="50e3a-150"><a name="__toc314837483"> </a></span></span>

1. <span data-ttu-id="50e3a-151">選擇 [**使用者**]，選取您要進行 wan 編輯之音訊會議設定的使用者，然後選擇 [](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png)**編輯** ![編輯]。</span><span class="sxs-lookup"><span data-stu-id="50e3a-151">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="50e3a-152">選擇 [**音訊會議**]，選取您的音訊會議提供者，輸入或變更要求的資訊，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="50e3a-152">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="50e3a-153">**音訊會議設定**</span><span class="sxs-lookup"><span data-stu-id="50e3a-153">**Audio conferencing setting**</span></span>|<span data-ttu-id="50e3a-154">**說明**</span><span class="sxs-lookup"><span data-stu-id="50e3a-154">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="50e3a-155">**提供者名稱**</span><span class="sxs-lookup"><span data-stu-id="50e3a-155">**Provider name**</span></span> <br/> |<span data-ttu-id="50e3a-156">從清單中選擇您的提供者。</span><span class="sxs-lookup"><span data-stu-id="50e3a-156">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="50e3a-157">**付費電話號碼**（必要）</span><span class="sxs-lookup"><span data-stu-id="50e3a-157">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="50e3a-158">針對協力廠商 ACP，這些電話號碼是您從音訊會議提供者接收到的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="50e3a-158">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="50e3a-159">如果使用者使用 Microsoft 做為音訊會議提供者，則會是在音訊會議橋接器上設定的號碼。</span><span class="sxs-lookup"><span data-stu-id="50e3a-159">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="50e3a-160">將數位格式化為想要在商務用 Skype 和 Microsoft 團隊會議邀請中顯示的數位。</span><span class="sxs-lookup"><span data-stu-id="50e3a-160">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="50e3a-161">**免付費電話號碼**</span><span class="sxs-lookup"><span data-stu-id="50e3a-161">**Toll-free number**</span></span> <br/> |<span data-ttu-id="50e3a-162">針對協力廠商 ACP，這些電話號碼是您從音訊會議提供者接收到的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="50e3a-162">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="50e3a-163">如果使用者使用 Microsoft 做為音訊會議提供者，則會是在音訊會議橋接器上設定的號碼。</span><span class="sxs-lookup"><span data-stu-id="50e3a-163">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="50e3a-164">將數位格式化為想要在商務用 Skype 和 Microsoft 團隊會議邀請中顯示的數位。</span><span class="sxs-lookup"><span data-stu-id="50e3a-164">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="50e3a-165">**會議 ID 與 PIN** （必要）</span><span class="sxs-lookup"><span data-stu-id="50e3a-165">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="50e3a-166">參與者 PIN （或會議程式碼），用來加入由這個使用者排程的會議，以及由協力廠商音訊會議提供者提供的會議。</span><span class="sxs-lookup"><span data-stu-id="50e3a-166">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="50e3a-167">如果使用者使用 Microsoft 作為音訊會議提供者，就不需要這麼做。</span><span class="sxs-lookup"><span data-stu-id="50e3a-167">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="50e3a-168">若要大量設定這些設定，請使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="50e3a-168">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="50e3a-169">請參閱[設定邀請中包含的電話號碼](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md)[設定您的 Windows PowerShell 電腦](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="50e3a-169">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="50e3a-170">相關主題</span><span class="sxs-lookup"><span data-stu-id="50e3a-170">Related topics</span></span> 

[<span data-ttu-id="50e3a-171">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="50e3a-171">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="50e3a-172">商務用 Skype 和 Microsoft 團隊附加元件授權</span><span class="sxs-lookup"><span data-stu-id="50e3a-172">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
