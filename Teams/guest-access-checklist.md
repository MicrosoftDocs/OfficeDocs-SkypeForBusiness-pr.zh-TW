---
title: Microsoft 團隊來賓存取檢查清單
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: 瞭解如何在 Microsoft 團隊中開啟和設定來賓存取（作為全域或團隊管理員）。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 00b62f9ee3c436a547b76db122efb8b005f106e4
ms.sourcegitcommit: 875c854547b5d3ad838ad10c1eada3f0cddc8e66
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2020
ms.locfileid: "46655924"
---
<a name="microsoft-teams-guest-access-checklist"></a><span data-ttu-id="f0d6f-103">Microsoft 團隊來賓存取檢查清單</span><span class="sxs-lookup"><span data-stu-id="f0d6f-103">Microsoft Teams guest access checklist</span></span>
=========================================

<span data-ttu-id="f0d6f-104">使用此檢查清單可協助您開啟並設定 Microsoft 團隊中的來賓存取權。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-104">Use this checklist to help you turn on and configure guest access in Microsoft Teams.</span></span> <span data-ttu-id="f0d6f-105">您必須是全域系統管理員或團隊管理員，才能進行這些變更。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-105">You need to be a Global Administrator or a Teams Administrator to make these changes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f0d6f-106">您可能需要等候幾個小時，變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-106">You may have to wait a few hours for your changes to take effect.</span></span>

<span data-ttu-id="f0d6f-107">請觀看這段短片 (5:31 分鐘) ，瞭解如何在整個 Microsoft 365 （包括團隊）中開啟來賓存取。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-107">Watch this short video (5:31 minutes) to see how to turn on guest access throughout Microsoft 365, including Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a><span data-ttu-id="f0d6f-108">步驟1：在團隊的整個組織層級開啟來賓存取</span><span class="sxs-lookup"><span data-stu-id="f0d6f-108">Step 1: Turn on guest access at the Teams org-wide level</span></span>

<span data-ttu-id="f0d6f-109">您必須是團隊服務管理員，才能進行這些變更。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-109">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="f0d6f-110">請參閱[使用團隊管理員角色管理團隊](https://docs.microsoft.com/microsoftteams/using-admin-roles)，瞭解如何取得管理員角色和許可權。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-110">See [Use Teams administrator roles to manage Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="f0d6f-111">在 [團隊管理中心] 中，選取 [全**組織性設定**  >  **來賓存取**]。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-111">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="f0d6f-112">將 [**允許 Microsoft 團隊中的來賓存取權**] 切換為 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-112">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![螢幕擷取畫面顯示 [團隊設定] 切換開關的範例](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="f0d6f-114">在此相同頁面上，開啟或關閉來賓的**通話**、**會議**和**訊息**設定。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-114">On this same page, turn on or turn off **Calling**, **Meeting**, and **Messaging** settings for guests.</span></span>
4. <span data-ttu-id="f0d6f-115">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-115">Click **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="f0d6f-116">如果您使用的是 Azure Active Directory、SharePoint Online 和 Microsoft 365 群組中的預設設定，您可能已完成來賓存取。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-116">If you're using default settings in Azure Active Directory, SharePoint Online, and Microsoft 365 Groups, you may be done configuring guest access.</span></span> <span data-ttu-id="f0d6f-117">在這種情況下，您可以略過其餘的步驟。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-117">In this case, you can skip the rest of the steps.</span></span> <span data-ttu-id="f0d6f-118">如果您不確定，或者您使用的是 AAD、SharePoint Online 或 Microsoft 365 群組的自訂設定，請繼續執行此檢查清單中的其餘步驟。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-118">If you're not sure, or if you're using custom settings for AAD, SharePoint Online, or Microsoft 365 Groups, continue with the rest of the steps in this checklist.</span></span>

## <a name="step-2-configure-azure-ad-business-to-business-settings"></a><span data-ttu-id="f0d6f-119">步驟2：設定 Azure AD 企業對企業設定</span><span class="sxs-lookup"><span data-stu-id="f0d6f-119">Step 2: Configure Azure AD business-to-business settings</span></span>

<span data-ttu-id="f0d6f-120">這些是支援小組中來賓存取權的 Azure AD 設定。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-120">These are the Azure AD settings that support guest access in Teams.</span></span> <span data-ttu-id="f0d6f-121">設定好這些設定之後，您就可以在小組中[新增](add-guests.md)和[管理來賓](manage-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-121">Once these settings are configured, you'll be able to [add](add-guests.md) and [manage guests](manage-guests.md) in Teams.</span></span>

1. <span data-ttu-id="f0d6f-122">以租使用者管理員的身分登入[Azure 入口網站](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-122">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="f0d6f-123">選取 [ **Azure Active Directory**  >  **使用者**]  >  **使用者設定**。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-123">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="f0d6f-124">在 [**外部使用者**] 底下，選取 [**管理外部**共同作業設定]。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-124">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="f0d6f-125">您也可以從 [**組織關聯**] 頁面取得外部共同作業**設定**。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-125">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="f0d6f-126">在 Azure Active Directory 中的 [**管理**] 底下，移至 [**組織關聯**]  >  **設定**。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-126">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="f0d6f-127">在 [**外部**共同作業設定] 頁面上，選擇您要啟用的原則。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-127">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

    - <span data-ttu-id="f0d6f-128">**來賓使用者許可權有限**：此原則會判斷您目錄中來賓的許可權。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-128">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="f0d6f-129">選取 **[是]** 來封鎖特定目錄工作的訪客，例如列舉使用者、群組或其他目錄資源。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-129">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="f0d6f-130">選取 [**否**]，為來賓提供與目錄中的一般使用者相同的目錄資料存取權。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-130">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
     - <span data-ttu-id="f0d6f-131">**來賓 inviter 角色中的管理員和使用者可以邀請**：若要允許「來賓 inviter」角色中的系統管理員和使用者邀請客人，請將此原則設定為 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-131">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
     - <span data-ttu-id="f0d6f-132">**成員可邀請**：若要允許您目錄中的非系統管理員成員邀請來賓，請將此原則設定為 [是]\*\*\*\* (建議使用)。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-132">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes** (recommended).</span></span> <span data-ttu-id="f0d6f-133">如果您希望只讓系統管理員新增來賓，可以將此原則設定為 [否]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-133">If you prefer that only admins be able to add guests, you can set this policy to **No**.</span></span> <span data-ttu-id="f0d6f-134">請記住，設定為 [否]\*\*\*\* 將會限制非系統管理員小組擁有者的來賓體驗；他們只能在已由系統管理員在 AAD 中新增的 Teams 中新增來賓。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-134">Keep in mind that setting **No** will limit the guest experience for non-admin teams owners; they'll only be able to add guests in Teams that have already been added in AAD by the admin.</span></span>
     - <span data-ttu-id="f0d6f-135">**客人可以邀請**：若要讓客人邀請其他客人，請將此原則設定為 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-135">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
         > [!IMPORTANT]
         > <span data-ttu-id="f0d6f-136">Teams 目前不支援來賓邀請者角色，因此，即使您將 **[來賓可邀請]** 設定為 **[是]**，來賓仍無法在 Teams 中邀請其他來賓。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-136">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
     - <span data-ttu-id="f0d6f-137">針對**來賓 (預覽) 啟用電子郵件一次性密碼**：如需一次性密碼功能的詳細資訊，請參閱以[電子郵件傳送一次性密碼驗證 (預覽) ](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode)。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-137">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
     - <span data-ttu-id="f0d6f-138">共同作業**限制**：如需有關允許或封鎖特定網域之邀請的詳細資訊，請參閱[允許或封鎖來自特定組織的 B2B 使用者邀請](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-138">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
        > [!NOTE]
        > <span data-ttu-id="f0d6f-139">如需共同作業限制，請參閱[啟用 B2B 外部共同作業和管理可邀請來賓的人員](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-139">For collaboration restrictions, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

    <span data-ttu-id="f0d6f-140">如需有關控制誰可以邀請來賓的詳細資訊，請參閱[委派 Azure Active Directory B2B 共同作業邀請](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-140">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

## <a name="step-3-configure-microsoft-365-groups"></a><span data-ttu-id="f0d6f-141">步驟3：設定 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="f0d6f-141">Step 3: Configure Microsoft 365 Groups</span></span>

1. <span data-ttu-id="f0d6f-142">在 Microsoft 365 系統管理中心中，移至 [**設定**  >  **組織設定**]，按一下 [**服務**]，然後選取 [ **Microsoft 365 群組**]。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-142">In the Microsoft 365 admin center, go to **Settings** > **Org Settings**, click **Services**, and then select **Microsoft 365 Groups**.</span></span>

     ![螢幕擷取畫面顯示 Microsoft 365 群組設定](media/guest-access-checklist-services-settings.png)
2. <span data-ttu-id="f0d6f-144">確認已選取 [**允許組織存取群組內容外的群組成員**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-144">Make sure that the **Let group members outside the organization access group content** check box is selected.</span></span> <span data-ttu-id="f0d6f-145">如果未選取此設定，來賓將無法存取任何群組內容。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-145">If this setting is not selected, guests won't be able to access any group content.</span></span>

    ![螢幕擷取畫面顯示 Microsoft 365 群組設定](media/guest-access-checklist-office365.png)
3. <span data-ttu-id="f0d6f-147">確認已選取 [**允許群組擁有者將組織外的人員新增至群組**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-147">Make sure that the **Let group owners add people outside the organization to groups** check box is selected.</span></span> <span data-ttu-id="f0d6f-148">如果未選取此設定，小組擁有者將無法新增來賓。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-148">If this setting is not selected, team owners won't be able to add new guests.</span></span> <span data-ttu-id="f0d6f-149">此設定至少必須開啟才能支援來賓存取。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-149">At a minimum, this setting must be on to support guest access.</span></span>

<span data-ttu-id="f0d6f-150">如需設定這些設定的詳細指示，請參閱[管理 microsoft 365 群組中的來賓存取](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150)及[控制 microsoft 365 群組中的來賓存取權](Teams-dependencies.md#control-guest-access-in-microsoft-365-groups)。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-150">For detailed instructions about configuring these settings, see [Manage guest access in Microsoft 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Microsoft 365 Groups](Teams-dependencies.md#control-guest-access-in-microsoft-365-groups).</span></span>

## <a name="step-4-configure-sharing-in-microsoft-365"></a><span data-ttu-id="f0d6f-151">步驟4：在 Microsoft 365 中設定共用</span><span class="sxs-lookup"><span data-stu-id="f0d6f-151">Step 4: Configure sharing in Microsoft 365</span></span>

<span data-ttu-id="f0d6f-152">請確定使用者可以新增來賓。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-152">Make sure that users can add guests.</span></span> <span data-ttu-id="f0d6f-153">做法如下：</span><span class="sxs-lookup"><span data-stu-id="f0d6f-153">Here's how:</span></span>

1. <span data-ttu-id="f0d6f-154">在 Microsoft 365 系統管理中心中，移至 [**設定**  >  **組織設定**]，按一下 [**安全性 & 隱私權**]，然後選取 [**共用**]。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-154">In the Microsoft 365 admin center, go to **Settings** > **Org Settings**, click **Security & privacy**, and then select **Sharing**.</span></span>

     ![螢幕擷取畫面顯示服務設定的範例](media/guest-access-checklist-security-privacy-settings.png)

2. <span data-ttu-id="f0d6f-156">選取 [**允許使用者將新的來賓新增至此組織**] 核取方塊，然後按一下 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-156">Select the **Let users add new guests to this organization** check box, and then click **Save changes**.</span></span>

     ![螢幕擷取畫面顯示共用設定切換的範例](media/guest-access-checklist-sharing-setting.png)

    > [!NOTE]
    > <span data-ttu-id="f0d6f-158">這個設定相當於 Azure AD 中的 [**使用者設定**] 中的 [**成員可以邀請**] 設定  >  **External users** 。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-158">This setting is equivalent to the **Members can invite** setting in **User settings** > **External users** in Azure AD.</span></span>  

## <a name="step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="f0d6f-159">步驟5：驗證 SharePoint 中的共用設定</span><span class="sxs-lookup"><span data-stu-id="f0d6f-159">Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="f0d6f-160">登入 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-160">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="f0d6f-161">選取 [系統**管理中心**] 底下的 [ **SharePoint**]。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-161">Under **Admin centers**, select  **SharePoint**.</span></span>
3. <span data-ttu-id="f0d6f-162">在新的 SharePoint 系統管理中心的 [**網站**] 底下，選取 [作用中的**網站**]。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-162">In the new SharePoint admin center,  under **Sites**, select **Active sites**.</span></span>

    ![SharePoint 系統管理中心的作用中網站](media/guest-access-checklist-SPOSettings0.png)

3. <span data-ttu-id="f0d6f-164">選取網站，然後按一下 [**共用**]。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-164">Select the site, and then click **Sharing**.</span></span>
4. <span data-ttu-id="f0d6f-165">確定該選項已設定為 [**任何人**] 或 [**現有來賓**]。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-165">Make sure that the option is set to **Anyone** or **New and existing guests**.</span></span>

     ![螢幕擷取畫面顯示 SharePoint Online 設定切換開關的範例](media/guest-access-checklist-SPOSettings1.png)

## <a name="step-6-set-up-guest-user-permissions"></a><span data-ttu-id="f0d6f-167">步驟6：設定來賓使用者許可權</span><span class="sxs-lookup"><span data-stu-id="f0d6f-167">Step 6: Set up guest user permissions</span></span>

<span data-ttu-id="f0d6f-168">在團隊應用程式的個別小組層級，設定來賓許可權來控制來賓是否可以建立、更新或刪除頻道。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-168">In the Teams application, at the individual team level, configure guest permissions that control whether guests can create, update, or delete channels.</span></span> <span data-ttu-id="f0d6f-169">小組管理員和小組擁有者可以設定這些設定。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-169">Teams admins as well as team owners can configure these settings.</span></span>

![螢幕擷取畫面顯示 [團隊/頻道設定] 切換開關的範例](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="f0d6f-171">若要深入瞭解來賓存取，請參閱[小組中的來賓存取權](guest-access.md)及[開啟或關閉 Microsoft 團隊的來賓存取權](set-up-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-171">To learn more about guest access, see [Guest access in Teams](guest-access.md) and [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>

## <a name="step-7-turn-on-anonymous-users-can-join-a-meeting-if-you-want-guests-to-join-meetings"></a><span data-ttu-id="f0d6f-172">步驟7：如果您想要來賓加入會議，請開啟「匿名使用者可以加入會議」</span><span class="sxs-lookup"><span data-stu-id="f0d6f-172">Step 7: Turn on "Anonymous users can join a meeting" if you want guests to join meetings</span></span>

<span data-ttu-id="f0d6f-173">如果您想要來賓加入會議，請開啟 Microsoft 團隊系統管理中心的 [**匿名使用者可以加入會議**] 設定。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-173">If you want guests to join meetings, turn on the **Anonymous users can join a meeting** setting in the Microsoft Teams admin center.</span></span> 

1. <span data-ttu-id="f0d6f-174">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**會議**  >  **會議設定**]。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-174">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting settings**.</span></span>

2. <span data-ttu-id="f0d6f-175">在 [參與者]\*\*\*\* 底下，開啟 [匿名使用者可加入會議]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-175">Under **Participants**, turn on **Anonymous users can join a meeting**.</span></span>

<span data-ttu-id="f0d6f-176">若要深入瞭解，請參閱[在團隊中管理會議設定](meeting-settings-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="f0d6f-176">To learn more, see [Manage meeting settings in Teams](meeting-settings-in-teams.md).</span></span> 

## <a name="troubleshooting"></a><span data-ttu-id="f0d6f-177">疑難排解</span><span class="sxs-lookup"><span data-stu-id="f0d6f-177">Troubleshooting</span></span>

<span data-ttu-id="f0d6f-178">如果您在設定來賓存取或在小組中新增來賓時遇到問題，請使用下列資源來協助您：</span><span class="sxs-lookup"><span data-stu-id="f0d6f-178">If you have problems setting up guest access or adding guests in Teams, use these resources to help you:</span></span>

[<span data-ttu-id="f0d6f-179">針對 Microsoft Teams 中的來賓存取問題進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="f0d6f-179">Troubleshoot problems with guest access in Microsoft Teams</span></span>](troubleshoot-guest-access.md)

[<span data-ttu-id="f0d6f-180">團隊疑難排解</span><span class="sxs-lookup"><span data-stu-id="f0d6f-180">Teams troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)
