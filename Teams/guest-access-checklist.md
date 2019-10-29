---
title: Microsoft 團隊來賓存取檢查清單
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: 使用此檢查清單可協助您設定 Microsoft 團隊中的來賓存取權。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04594f578d2375f69c38243251ee64506880d00e
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/28/2019
ms.locfileid: "37753318"
---
<a name="microsoft-teams-guest-access-checklist"></a><span data-ttu-id="7c7c2-103">Microsoft 團隊來賓存取檢查清單</span><span class="sxs-lookup"><span data-stu-id="7c7c2-103">Microsoft Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="7c7c2-104">使用此檢查清單可協助您開啟並設定 Microsoft 團隊中的來賓存取權。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-104">Use this checklist to help you turn on and configure guest access in Microsoft Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7c7c2-105">您可能必須等候長達24小時，變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-105">You may have to wait up to 24 hours for your changes to take effect.</span></span> 



## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a><span data-ttu-id="7c7c2-106">步驟1：在團隊的整個組織層級開啟來賓存取</span><span class="sxs-lookup"><span data-stu-id="7c7c2-106">Step 1: Turn on guest access at the Teams org-wide level</span></span>

<span data-ttu-id="7c7c2-107">若要開啟來賓存取，請移至**Microsoft 團隊系統管理中心**。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-107">To turn on guest access, go to the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="7c7c2-108">在 [團隊管理中心] 中，選取 [全**組織性設定** > **來賓存取**]。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-108">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="7c7c2-109">將 [**允許 Microsoft 團隊中的來賓存取權**] 切換為 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-109">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![螢幕擷取畫面顯示 [團隊設定] 切換開關的範例](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="7c7c2-111">在此相同頁面上，開啟或關閉來賓的**通話**、**會議**和**訊息**設定。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-111">On this same page, turn on or turn off **Calling**, **Meeting**, and **Messaging** settings for guests.</span></span>
4. <span data-ttu-id="7c7c2-112">按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-112">Click **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="7c7c2-113">如果您使用的是 Azure Active Directory、SharePoint Online 和 Office 365 群組中的預設設定，您可能已完成來賓存取。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-113">If you're using default settings in Azure Active Directory, SharePoint Online, and Office 365 Groups, you may be done configuring guest access.</span></span> <span data-ttu-id="7c7c2-114">在這種情況下，您可以略過其餘的步驟。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-114">In this case, you can skip the rest of the steps.</span></span> <span data-ttu-id="7c7c2-115">如果您不確定，或者您使用的是 AAD、SharePoint Online 或 Office 365 群組的自訂設定，請繼續執行此檢查清單中的其餘步驟。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-115">If you're not sure, or if you're using custom settings for AAD, SharePoint Online, or Office 365 Groups, continue with the rest of the steps in this checklist.</span></span>


## <a name="step-2-configure-azure-ad-business-to-business-settings"></a><span data-ttu-id="7c7c2-116">步驟2：設定 Azure AD 企業對企業設定</span><span class="sxs-lookup"><span data-stu-id="7c7c2-116">Step 2: Configure Azure AD business-to-business settings</span></span>

1. <span data-ttu-id="7c7c2-117">以租使用者管理員的身分登入[Azure 入口網站](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-117">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="7c7c2-118">選取 [ **Azure Active Directory** > **使用者** > ]**使用者設定**。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-118">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="7c7c2-119">在 [**外部使用者**] 底下，選取 [**管理外部**共同作業設定]。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-119">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="7c7c2-120">您也可以從 [**組織關聯**] 頁面取得外部共同作業**設定**。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-120">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="7c7c2-121">在 Azure Active Directory 中的 [**管理**] 底下，移至 [**組織關聯** > ]**設定**。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-121">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="7c7c2-122">在 [**外部**共同作業設定] 頁面上，選擇您要啟用的原則。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-122">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

  - <span data-ttu-id="7c7c2-123">**來賓使用者許可權有限**：此原則會判斷您目錄中來賓的許可權。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-123">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="7c7c2-124">選取 **[是]** 來封鎖特定目錄工作的訪客，例如列舉使用者、群組或其他目錄資源。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-124">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="7c7c2-125">選取 [**否**]，為來賓提供與目錄中的一般使用者相同的目錄資料存取權。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-125">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
   - <span data-ttu-id="7c7c2-126">**來賓 inviter 角色中的管理員和使用者可以邀請**：若要允許「來賓 inviter」角色中的系統管理員和使用者邀請客人，請將此原則設定為 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-126">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
   - <span data-ttu-id="7c7c2-127">**成員可以邀請**：若要允許目錄的非系統管理員成員邀請客人，請將此原則設定為 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-127">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes**.</span></span>
   
       > [!NOTE]
       > <span data-ttu-id="7c7c2-128">如果您設定 [**成員可以**在 Office 365 群組和 Microsoft 團隊中邀請您**不**想再啟用來賓存取]，系統管理員可以控制您的目錄的來賓邀請。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-128">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="7c7c2-129">來賓在目錄中後，就可以由非系統管理員成員，將它們新增至小組。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-129">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span> <span data-ttu-id="7c7c2-130">如需詳細資訊，請參閱[授權 Microsoft 團隊中的來賓存取](Teams-dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-130">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
       > [!IMPORTANT]
       > <span data-ttu-id="7c7c2-131">若要讓來賓存取權在團隊中運作，您必須將成員設定為 [**可以邀請\*\*\*\*是]**。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-131">For guest access to work at all in Teams, you must set **Members can invite** to **Yes**.</span></span>   
   - <span data-ttu-id="7c7c2-132">**客人可以邀請**：若要讓客人邀請其他客人，請將此原則設定為 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-132">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
       > [!IMPORTANT]
       > <span data-ttu-id="7c7c2-133">目前，小組不支援來賓 inviter 角色，因此即使您將**客人**設定為 **[邀請]**，來賓也無法在團隊中邀請其他來賓。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-133">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
   - <span data-ttu-id="7c7c2-134">**啟用電子郵件的一次性密碼（預覽版）**：如需一次性密碼功能的詳細資訊，請參閱[電子郵件一次性密碼驗證（預覽版）](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode)。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-134">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
   - <span data-ttu-id="7c7c2-135">共同作業**限制**：如需有關允許或封鎖特定網域之邀請的詳細資訊，請參閱[允許或封鎖來自特定組織的 B2B 使用者邀請](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-135">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
      > [!NOTE]
      > <span data-ttu-id="7c7c2-136">如需共同作業限制，請參閱[啟用 B2B 外部共同作業和管理可邀請來賓的人員](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-136">For collaboration restrictions, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>
      
 
<span data-ttu-id="7c7c2-137">如需控制誰可以邀請來賓的詳細資訊，請參閱針對[Azure Active DIRECTORY B2B 共同作業委派邀請](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-137">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>


## <a name="step-3-configure-office-365-groups"></a><span data-ttu-id="7c7c2-138">步驟3：設定 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="7c7c2-138">Step 3: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="7c7c2-139">在 Microsoft 365 系統管理中心，移至 [**設定** > **服務] & [增益集** > ]**Office 365 群組**。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-139">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="7c7c2-140">確認將**組織存取群組內容外的群組成員**設定為 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-140">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="7c7c2-141">如果關閉此設定，來賓將無法存取任何群組內容。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-141">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="7c7c2-142">確認 **[允許群組擁有者將組織外部的人員新增至群組**] 已設定為 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-142">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="7c7c2-143">如果關閉此設定，小組擁有者將無法新增來賓。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-143">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="7c7c2-144">此設定至少必須開啟才能支援來賓存取。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-144">At a minimum, this setting must be On to support guest access.</span></span>

     ![螢幕擷取畫面顯示 Office 365 群組的切換](media/guest-access-checklist-office365.png)

<span data-ttu-id="7c7c2-146">如需設定這些設定的詳細指示，請參閱[管理 office 365 群組中的來賓存取](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150)，以及[控制 office 365 群組中的來賓存取權](Teams-dependencies.md#control-guest-access-in-office-365-groups)。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-146">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>
 

## <a name="step-4-configure-sharing-in-office-365"></a><span data-ttu-id="7c7c2-147">步驟4：在 Office 365 中設定共用</span><span class="sxs-lookup"><span data-stu-id="7c7c2-147">Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="7c7c2-148">請確定使用者可以新增來賓。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-148">Make sure that users can add guests.</span></span> <span data-ttu-id="7c7c2-149">做法如下：</span><span class="sxs-lookup"><span data-stu-id="7c7c2-149">Here's how:</span></span>

1. <span data-ttu-id="7c7c2-150">在 Microsoft 365 系統管理中心中，移至 [**設定** > **安全性] & [隱私權**]。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-150">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![螢幕擷取畫面顯示服務設定的範例](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="7c7c2-152">在 [**共用**] 中，選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-152">In **Sharing**, select **Edit**.</span></span>

     ![螢幕擷取畫面顯示共用設定切換的範例](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="7c7c2-154">設定 [**讓使用者將新的來賓新增至此組織** **]，然後**按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-154">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![螢幕擷取畫面顯示共用設定切換的範例](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> <span data-ttu-id="7c7c2-156">這個設定相當於 Azure AD 中的 [**使用者設定** > **] 中的**[**成員可以邀請**] 設定。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-156">This setting is equivalent to the **Members can invite** setting in **User settings** > **External users** in Azure AD.</span></span>  


## <a name="step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="7c7c2-157">步驟5：驗證 SharePoint 中的共用設定</span><span class="sxs-lookup"><span data-stu-id="7c7c2-157">Step 5: Verify sharing setting in SharePoint</span></span>

<span data-ttu-id="7c7c2-158">這個小一點的大腦 teaser。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-158">This one's a bit of a brain teaser.</span></span> <span data-ttu-id="7c7c2-159">如果您已在 SharePoint 系統管理中心選取 [**不允許在您的組織外共用**] 設定，小組中的來賓存取就無法運作。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-159">Guest access in Teams doesn't work if the **Don't allow sharing outside your organization** setting is selected in the SharePoint admin center.</span></span>

1. <span data-ttu-id="7c7c2-160">登入 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-160">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="7c7c2-161">按一下 [系統**管理中心**]，然後選取 [ **SharePoint**]。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-161">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="7c7c2-162">在 SharePoint 系統管理中心中，選取 [**共用**]。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-162">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="7c7c2-163">確定*沒有*選取 [不**允許在您的組織外共用**] 選項。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-163">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![螢幕擷取畫面顯示 SparePoint Online 設定切換開關的範例。](media/guest-access-checklist-SPOSettings1.png)


## <a name="step-6-set-up-guest-user-permissions"></a><span data-ttu-id="7c7c2-165">步驟6：設定來賓使用者許可權</span><span class="sxs-lookup"><span data-stu-id="7c7c2-165">Step 6: Set up guest user permissions</span></span>

<span data-ttu-id="7c7c2-166">在團隊應用程式的個別小組層級，設定來賓許可權來控制來賓是否可以建立、更新或刪除頻道。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-166">In the Teams application, at the individual team level, configure guest permissions that control whether guests can create, update, or delete channels.</span></span> <span data-ttu-id="7c7c2-167">小組管理員和小組擁有者可以設定這些設定。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-167">Teams admins as well as team owners can configure these settings.</span></span>

![螢幕擷取畫面顯示 [團隊/頻道設定] 切換開關的範例](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="7c7c2-169">若要深入瞭解來賓存取，請參閱[小組中的來賓存取權](guest-access.md)及[開啟或關閉 Microsoft 團隊的來賓存取權](set-up-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="7c7c2-169">To learn more about guest access, see [Guest access in Teams](guest-access.md) and [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="7c7c2-170">疑難排解</span><span class="sxs-lookup"><span data-stu-id="7c7c2-170">Troubleshooting</span></span>

<span data-ttu-id="7c7c2-171">如果您在設定來賓存取或在小組中新增來賓時遇到問題，請使用下列資源來協助您：</span><span class="sxs-lookup"><span data-stu-id="7c7c2-171">If you have problems setting up guest access or adding guests in Teams, use these resources to help you:</span></span>

[<span data-ttu-id="7c7c2-172">針對 Microsoft 團隊中的來賓存取問題進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="7c7c2-172">Troubleshoot problems with guest access in Microsoft Teams</span></span>](troubleshoot-guest-access.md)

[<span data-ttu-id="7c7c2-173">團隊疑難排解</span><span class="sxs-lookup"><span data-stu-id="7c7c2-173">Teams troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)



