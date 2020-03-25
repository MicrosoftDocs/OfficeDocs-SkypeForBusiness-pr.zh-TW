---
title: Microsoft 團隊來賓存取檢查清單
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: 使用此檢查清單可協助您設定 Microsoft 團隊中的來賓存取權。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d5470d9ec2ec2d22d8f3b66bac09ba6c67b9982f
ms.sourcegitcommit: 0549714f17f9994cf832a303ec9bc58a537c3a51
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2020
ms.locfileid: "42951498"
---
<a name="microsoft-teams-guest-access-checklist"></a><span data-ttu-id="d6707-103">Microsoft 團隊來賓存取檢查清單</span><span class="sxs-lookup"><span data-stu-id="d6707-103">Microsoft Teams guest access checklist</span></span>
=========================================

<span data-ttu-id="d6707-104">使用此檢查清單可協助您開啟並設定 Microsoft 團隊中的來賓存取權。</span><span class="sxs-lookup"><span data-stu-id="d6707-104">Use this checklist to help you turn on and configure guest access in Microsoft Teams.</span></span> <span data-ttu-id="d6707-105">您必須是全域系統管理員或團隊管理員，才能進行這些變更。</span><span class="sxs-lookup"><span data-stu-id="d6707-105">You need to be a Global Administrator or a Teams Administrator to make these changes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d6707-106">您可能必須等候長達24小時，變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="d6707-106">You may have to wait up to 24 hours for your changes to take effect.</span></span> 

<span data-ttu-id="d6707-107">觀看這段短片（5:31 分鐘），瞭解如何在整個 Microsoft 365 （包括團隊）中開啟來賓存取。</span><span class="sxs-lookup"><span data-stu-id="d6707-107">Watch this short video (5:31 minutes) to see how to turn on guest access throughout Microsoft 365, including Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a><span data-ttu-id="d6707-108">步驟1：在團隊的整個組織層級開啟來賓存取</span><span class="sxs-lookup"><span data-stu-id="d6707-108">Step 1: Turn on guest access at the Teams org-wide level</span></span>

<span data-ttu-id="d6707-109">若要開啟來賓存取，請移至**Microsoft 團隊系統管理中心**。</span><span class="sxs-lookup"><span data-stu-id="d6707-109">To turn on guest access, go to the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="d6707-110">在 [團隊管理中心] 中，選取 [全**組織性設定** > **來賓存取**]。</span><span class="sxs-lookup"><span data-stu-id="d6707-110">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="d6707-111">將 [**允許 Microsoft 團隊中的來賓存取權**] 切換為 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="d6707-111">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![螢幕擷取畫面顯示 [團隊設定] 切換開關的範例](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="d6707-113">在此相同頁面上，開啟或關閉來賓的**通話**、**會議**和**訊息**設定。</span><span class="sxs-lookup"><span data-stu-id="d6707-113">On this same page, turn on or turn off **Calling**, **Meeting**, and **Messaging** settings for guests.</span></span>
4. <span data-ttu-id="d6707-114">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d6707-114">Click **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="d6707-115">如果您使用的是 Azure Active Directory、SharePoint Online 和 Office 365 群組中的預設設定，您可能已完成來賓存取。</span><span class="sxs-lookup"><span data-stu-id="d6707-115">If you're using default settings in Azure Active Directory, SharePoint Online, and Office 365 Groups, you may be done configuring guest access.</span></span> <span data-ttu-id="d6707-116">在這種情況下，您可以略過其餘的步驟。</span><span class="sxs-lookup"><span data-stu-id="d6707-116">In this case, you can skip the rest of the steps.</span></span> <span data-ttu-id="d6707-117">如果您不確定，或者您使用的是 AAD、SharePoint Online 或 Office 365 群組的自訂設定，請繼續執行此檢查清單中的其餘步驟。</span><span class="sxs-lookup"><span data-stu-id="d6707-117">If you're not sure, or if you're using custom settings for AAD, SharePoint Online, or Office 365 Groups, continue with the rest of the steps in this checklist.</span></span>

## <a name="step-2-configure-azure-ad-business-to-business-settings"></a><span data-ttu-id="d6707-118">步驟2：設定 Azure AD 企業對企業設定</span><span class="sxs-lookup"><span data-stu-id="d6707-118">Step 2: Configure Azure AD business-to-business settings</span></span>

<span data-ttu-id="d6707-119">這些是支援小組中來賓存取權的 Azure AD 設定。</span><span class="sxs-lookup"><span data-stu-id="d6707-119">These are the Azure AD settings that support guest access in Teams.</span></span> <span data-ttu-id="d6707-120">設定好這些設定之後，您就可以在小組中[新增](add-guests.md)和[管理來賓](manage-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="d6707-120">Once these settings are configured, you'll be able to [add](add-guests.md) and [manage guests](manage-guests.md) in Teams.</span></span>

1. <span data-ttu-id="d6707-121">以租使用者管理員的身分登入[Azure 入口網站](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="d6707-121">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="d6707-122">選取 [ **Azure Active Directory** > **使用者** > ]**使用者設定**。</span><span class="sxs-lookup"><span data-stu-id="d6707-122">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="d6707-123">在 [**外部使用者**] 底下，選取 [**管理外部**共同作業設定]。</span><span class="sxs-lookup"><span data-stu-id="d6707-123">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="d6707-124">您也可以從 [**組織關聯**] 頁面取得外部共同作業**設定**。</span><span class="sxs-lookup"><span data-stu-id="d6707-124">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="d6707-125">在 Azure Active Directory 中的 [**管理**] 底下，移至 [**組織關聯** > ]**設定**。</span><span class="sxs-lookup"><span data-stu-id="d6707-125">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="d6707-126">在 [**外部**共同作業設定] 頁面上，選擇您要啟用的原則。</span><span class="sxs-lookup"><span data-stu-id="d6707-126">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

    - <span data-ttu-id="d6707-127">**來賓使用者許可權有限**：此原則會判斷您目錄中來賓的許可權。</span><span class="sxs-lookup"><span data-stu-id="d6707-127">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="d6707-128">選取 **[是]** 來封鎖特定目錄工作的訪客，例如列舉使用者、群組或其他目錄資源。</span><span class="sxs-lookup"><span data-stu-id="d6707-128">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="d6707-129">選取 [**否**]，為來賓提供與目錄中的一般使用者相同的目錄資料存取權。</span><span class="sxs-lookup"><span data-stu-id="d6707-129">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
     - <span data-ttu-id="d6707-130">**來賓 inviter 角色中的管理員和使用者可以邀請**：若要允許「來賓 inviter」角色中的系統管理員和使用者邀請客人，請將此原則設定為 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="d6707-130">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
     - <span data-ttu-id="d6707-131">**成員可邀請**：若要允許您目錄中的非系統管理員成員邀請來賓，請將此原則設定為 [是]\*\*\*\* (建議使用)。</span><span class="sxs-lookup"><span data-stu-id="d6707-131">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes** (recommended).</span></span> <span data-ttu-id="d6707-132">如果您希望只讓系統管理員新增來賓，可以將此原則設定為 [否]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d6707-132">If you prefer that only admins be able to add guests, you can set this policy to **No**.</span></span> <span data-ttu-id="d6707-133">請記住，設定為 [否]\*\*\*\* 將會限制非系統管理員小組擁有者的來賓體驗；他們只能在已由系統管理員在 AAD 中新增的 Teams 中新增來賓。</span><span class="sxs-lookup"><span data-stu-id="d6707-133">Keep in mind that setting **No** will limit the guest experience for non-admin teams owners; they'll only be able to add guests in Teams that have already been added in AAD by the admin.</span></span>
     - <span data-ttu-id="d6707-134">**客人可以邀請**：若要讓客人邀請其他客人，請將此原則設定為 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="d6707-134">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
         > [!IMPORTANT]
         > <span data-ttu-id="d6707-135">Teams 目前不支援來賓邀請者角色，因此，即使您將 **[來賓可邀請]** 設定為 **[是]**，來賓仍無法在 Teams 中邀請其他來賓。</span><span class="sxs-lookup"><span data-stu-id="d6707-135">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
     - <span data-ttu-id="d6707-136">**啟用電子郵件的一次性密碼（預覽版）**：如需一次性密碼功能的詳細資訊，請參閱[電子郵件一次性密碼驗證（預覽版）](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode)。</span><span class="sxs-lookup"><span data-stu-id="d6707-136">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
     - <span data-ttu-id="d6707-137">共同作業**限制**：如需有關允許或封鎖特定網域之邀請的詳細資訊，請參閱[允許或封鎖來自特定組織的 B2B 使用者邀請](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)。</span><span class="sxs-lookup"><span data-stu-id="d6707-137">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
        > [!NOTE]
        > <span data-ttu-id="d6707-138">如需共同作業限制，請參閱[啟用 B2B 外部共同作業和管理可邀請來賓的人員](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)。</span><span class="sxs-lookup"><span data-stu-id="d6707-138">For collaboration restrictions, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>
      
    <span data-ttu-id="d6707-139">如需有關控制誰可以邀請來賓的詳細資訊，請參閱[委派 Azure Active Directory B2B 共同作業邀請](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)。</span><span class="sxs-lookup"><span data-stu-id="d6707-139">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

## <a name="step-3-configure-office-365-groups"></a><span data-ttu-id="d6707-140">步驟3：設定 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="d6707-140">Step 3: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="d6707-141">在 Microsoft 365 系統管理中心中，移至 [**設定** > **設定**]，按一下 [**服務**]，然後選取 [ **Office 365 群組**]。</span><span class="sxs-lookup"><span data-stu-id="d6707-141">In the Microsoft 365 admin center, go to **Settings** > **Settings**, click **Services**, and then select **Office 365 Groups**.</span></span>

     ![螢幕擷取畫面顯示 Office 365 群組設定](media/guest-access-checklist-services-settings.png)
2. <span data-ttu-id="d6707-143">確認已選取 [**允許組織存取群組內容外的群組成員**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d6707-143">Make sure that the **Let group members outside the organization access group content** check box is selected.</span></span> <span data-ttu-id="d6707-144">如果未選取此設定，來賓將無法存取任何群組內容。</span><span class="sxs-lookup"><span data-stu-id="d6707-144">If this setting is not selected, guests won't be able to access any group content.</span></span>

    ![螢幕擷取畫面顯示 Office 365 群組設定](media/guest-access-checklist-office365.png)
3. <span data-ttu-id="d6707-146">確認已選取 [**允許群組擁有者將組織外的人員新增至群組**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d6707-146">Make sure that the **Let group owners add people outside the organization to groups** check box is selected.</span></span> <span data-ttu-id="d6707-147">如果未選取此設定，小組擁有者將無法新增來賓。</span><span class="sxs-lookup"><span data-stu-id="d6707-147">If this setting is not selected, team owners won't be able to add new guests.</span></span> <span data-ttu-id="d6707-148">此設定至少必須開啟才能支援來賓存取。</span><span class="sxs-lookup"><span data-stu-id="d6707-148">At a minimum, this setting must be on to support guest access.</span></span>

<span data-ttu-id="d6707-149">如需設定這些設定的詳細指示，請參閱[管理 office 365 群組中的來賓存取](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150)，以及[控制 office 365 群組中的來賓存取權](Teams-dependencies.md#control-guest-access-in-office-365-groups)。</span><span class="sxs-lookup"><span data-stu-id="d6707-149">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>

## <a name="step-4-configure-sharing-in-office-365"></a><span data-ttu-id="d6707-150">步驟4：在 Office 365 中設定共用</span><span class="sxs-lookup"><span data-stu-id="d6707-150">Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="d6707-151">請確定使用者可以新增來賓。</span><span class="sxs-lookup"><span data-stu-id="d6707-151">Make sure that users can add guests.</span></span> <span data-ttu-id="d6707-152">做法如下：</span><span class="sxs-lookup"><span data-stu-id="d6707-152">Here's how:</span></span>

1. <span data-ttu-id="d6707-153">在 Microsoft 365 系統管理中心中，移至 [**設定** > **設定**]，按一下 [**安全性 & 隱私權**]，然後選取 [**共用**]。</span><span class="sxs-lookup"><span data-stu-id="d6707-153">In the Microsoft 365 admin center, go to **Settings** > **Settings**, click **Security & privacy**, and then select **Sharing**.</span></span>

     ![螢幕擷取畫面顯示服務設定的範例](media/guest-access-checklist-security-privacy-settings.png)
 
2. <span data-ttu-id="d6707-155">選取 [**允許使用者將新的來賓新增至此組織**] 核取方塊，然後按一下 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="d6707-155">Select the **Let users add new guests to this organization** check box, and then click **Save changes**.</span></span>

     ![螢幕擷取畫面顯示共用設定切換的範例](media/guest-access-checklist-sharing-setting.png)
 
    > [!NOTE]
    > <span data-ttu-id="d6707-157">這個設定相當於 Azure AD 中的 [**使用者設定** > **] 中的**[**成員可以邀請**] 設定。</span><span class="sxs-lookup"><span data-stu-id="d6707-157">This setting is equivalent to the **Members can invite** setting in **User settings** > **External users** in Azure AD.</span></span>  

## <a name="step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="d6707-158">步驟5：驗證 SharePoint 中的共用設定</span><span class="sxs-lookup"><span data-stu-id="d6707-158">Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="d6707-159">登入 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="d6707-159">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="d6707-160">選取 [系統**管理中心**] 底下的 [ **SharePoint**]。</span><span class="sxs-lookup"><span data-stu-id="d6707-160">Under **Admin centers**, select  **SharePoint**.</span></span>
3. <span data-ttu-id="d6707-161">在新的 SharePoint 系統管理中心的 [**網站**] 底下，選取 [作用中的**網站**]。</span><span class="sxs-lookup"><span data-stu-id="d6707-161">In the new SharePoint admin center,  under **Sites**, select **Active sites**.</span></span>

    ![SharePoint 系統管理中心的作用中網站](media/guest-access-checklist-SPOSettings0.png)

3. <span data-ttu-id="d6707-163">選取網站，然後按一下 [**共用**]。</span><span class="sxs-lookup"><span data-stu-id="d6707-163">Select the site, and then click **Sharing**.</span></span>
4. <span data-ttu-id="d6707-164">確定該選項已設定為 [**任何人**] 或 [**現有來賓**]。</span><span class="sxs-lookup"><span data-stu-id="d6707-164">Make sure that the option is set to **Anyone** or **New and existing guests**.</span></span>

     ![螢幕擷取畫面顯示 SharePoint Online 設定切換開關的範例](media/guest-access-checklist-SPOSettings1.png)

## <a name="step-6-set-up-guest-user-permissions"></a><span data-ttu-id="d6707-166">步驟6：設定來賓使用者許可權</span><span class="sxs-lookup"><span data-stu-id="d6707-166">Step 6: Set up guest user permissions</span></span>

<span data-ttu-id="d6707-167">在團隊應用程式的個別小組層級，設定來賓許可權來控制來賓是否可以建立、更新或刪除頻道。</span><span class="sxs-lookup"><span data-stu-id="d6707-167">In the Teams application, at the individual team level, configure guest permissions that control whether guests can create, update, or delete channels.</span></span> <span data-ttu-id="d6707-168">小組管理員和小組擁有者可以設定這些設定。</span><span class="sxs-lookup"><span data-stu-id="d6707-168">Teams admins as well as team owners can configure these settings.</span></span>

![螢幕擷取畫面顯示 [團隊/頻道設定] 切換開關的範例](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="d6707-170">若要深入瞭解來賓存取，請參閱[小組中的來賓存取權](guest-access.md)及[開啟或關閉 Microsoft 團隊的來賓存取權](set-up-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="d6707-170">To learn more about guest access, see [Guest access in Teams](guest-access.md) and [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="d6707-171">疑難排解</span><span class="sxs-lookup"><span data-stu-id="d6707-171">Troubleshooting</span></span>

<span data-ttu-id="d6707-172">如果您在設定來賓存取或在小組中新增來賓時遇到問題，請使用下列資源來協助您：</span><span class="sxs-lookup"><span data-stu-id="d6707-172">If you have problems setting up guest access or adding guests in Teams, use these resources to help you:</span></span>

[<span data-ttu-id="d6707-173">針對 Microsoft 團隊中的來賓存取問題進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="d6707-173">Troubleshoot problems with guest access in Microsoft Teams</span></span>](troubleshoot-guest-access.md)

[<span data-ttu-id="d6707-174">團隊疑難排解</span><span class="sxs-lookup"><span data-stu-id="d6707-174">Teams troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)
