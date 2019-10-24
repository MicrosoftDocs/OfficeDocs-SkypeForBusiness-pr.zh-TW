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
ms.openlocfilehash: e7f019f2260b1e86b422f8b4238439fbd2f1607a
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2019
ms.locfileid: "37569542"
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="2119c-103">小組訪客存取檢查清單</span><span class="sxs-lookup"><span data-stu-id="2119c-103">Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="2119c-104">您可以根據貴組織的喜好設定，使用此檢查清單來協助您啟用及設定 Microsoft 團隊中的來賓存取功能。</span><span class="sxs-lookup"><span data-stu-id="2119c-104">Use this checklist to help you enable and configure the guest access feature in Microsoft Teams according to the preferences of your organization.</span></span>

> [!NOTE] 
> <span data-ttu-id="2119c-105">針對共同作業限制，請參閱[啟用 B2B 外部共同作業和管理可邀請來賓的人員](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)。</span><span class="sxs-lookup"><span data-stu-id="2119c-105">For collaboration restrictions see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="2119c-106">瞭解來賓的限制</span><span class="sxs-lookup"><span data-stu-id="2119c-106">Understand the limitations for guests</span></span>

<span data-ttu-id="2119c-107">來賓體驗會依設計而有所限制。</span><span class="sxs-lookup"><span data-stu-id="2119c-107">The guest experience has limitations by design.</span></span> <span data-ttu-id="2119c-108">請務必瞭解來賓體驗，不要嘗試修正不存在問題的內容。</span><span class="sxs-lookup"><span data-stu-id="2119c-108">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="2119c-109">例如，以下是 Microsoft 團隊中的來賓無法使用的一些功能清單：</span><span class="sxs-lookup"><span data-stu-id="2119c-109">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="2119c-110">商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="2119c-110">OneDrive for Business</span></span>
- <span data-ttu-id="2119c-111">團隊外的人員搜尋</span><span class="sxs-lookup"><span data-stu-id="2119c-111">People search outside of Teams</span></span>
- <span data-ttu-id="2119c-112">行事曆、排程的會議或會議詳細資料</span><span class="sxs-lookup"><span data-stu-id="2119c-112">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="2119c-113">通向</span><span class="sxs-lookup"><span data-stu-id="2119c-113">PSTN</span></span>
- <span data-ttu-id="2119c-114">組織結構</span><span class="sxs-lookup"><span data-stu-id="2119c-114">Organization chart</span></span>
- <span data-ttu-id="2119c-115">建立或修改團隊</span><span class="sxs-lookup"><span data-stu-id="2119c-115">Create or revise a team</span></span>
- <span data-ttu-id="2119c-116">流覽團隊</span><span class="sxs-lookup"><span data-stu-id="2119c-116">Browse for a team</span></span>
- <span data-ttu-id="2119c-117">將檔案上傳到人員對人聊天</span><span class="sxs-lookup"><span data-stu-id="2119c-117">Upload files to a person-to-person chat</span></span>
- <span data-ttu-id="2119c-118">如果訪客知道使用者的完整電子郵件識別碼，就能繼續搜尋並尋找他們的小組外的使用者。</span><span class="sxs-lookup"><span data-stu-id="2119c-118">Guests can still search and find users (outside their team) if they know the user's full email ID.</span></span> <span data-ttu-id="2119c-119">若要避免這種情況，IT 系統管理員可以使用可將來賓限制在自己的虛擬 GAL 中的模式，例如已設定[目錄搜尋的範圍](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search)。</span><span class="sxs-lookup"><span data-stu-id="2119c-119">To prevent this, IT admins can use patterns like [scoped directory search](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search) that have the ability to restrict Guests into their own virtual GAL.</span></span>

<span data-ttu-id="2119c-120">如需詳細資訊，請參閱[Office 365 群組中](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)[的來賓體驗是什麼](guest-experience.md)，以及來賓存取權。</span><span class="sxs-lookup"><span data-stu-id="2119c-120">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 Groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>

### <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="2119c-121">來賓存取與外部存取（同盟）</span><span class="sxs-lookup"><span data-stu-id="2119c-121">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

> [!NOTE] 
> <span data-ttu-id="2119c-122">目前，Microsoft 團隊不支援來賓 inviter 角色。</span><span class="sxs-lookup"><span data-stu-id="2119c-122">Currently, Microsoft Teams does not support the guest inviter role.</span></span> <span data-ttu-id="2119c-123">在 Microsoft 團隊中，您至少必須將 [成員可以邀請] 切換開關設定為 [是]，才能使用來賓存取。</span><span class="sxs-lookup"><span data-stu-id="2119c-123">At a minimum the "members can invite" toggle must be set to "Yes" for guest access to work in Microsoft Teams.</span></span> <span data-ttu-id="2119c-124">如果您將「成員可以邀請」設定為 [否]，然後在 Office 365 群組和 Microsoft 團隊中啟用來賓存取，系統管理員可以控制您的目錄的來賓邀請。</span><span class="sxs-lookup"><span data-stu-id="2119c-124">If you set "members can invite" to "No" and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="2119c-125">來賓在目錄中後，就可以由非系統管理員成員，將它們新增至小組。</span><span class="sxs-lookup"><span data-stu-id="2119c-125">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="2119c-126">如果您的客人看到授權錯誤</span><span class="sxs-lookup"><span data-stu-id="2119c-126">If your guests are seeing license errors</span></span>

<span data-ttu-id="2119c-127">Microsoft 團隊中的來賓存取使用 Azure Active Directory （Azure AD）商務用企業（B2B）和授權模型。</span><span class="sxs-lookup"><span data-stu-id="2119c-127">Guest access in Microsoft Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="2119c-128">如果您看到授權錯誤，請務必閱讀[B2B 授權指南](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)，瞭解貴組織擁有的授權需求，讓您的使用者能夠邀請來賓加入您的組織。</span><span class="sxs-lookup"><span data-stu-id="2119c-128">If you’re seeing licensing errors, make sure to read the [B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to understand the licensing requirements your organization has so that your users are able to invite guests to your organization.</span></span>

<span data-ttu-id="2119c-129">請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="2119c-129">A few things to remember:</span></span>

- <span data-ttu-id="2119c-130">來賓是您組織外部的使用者。</span><span class="sxs-lookup"><span data-stu-id="2119c-130">Guests are users outside your organization.</span></span> <span data-ttu-id="2119c-131">您的員工、現場承包商、現場代理商等不能新增為來賓。</span><span class="sxs-lookup"><span data-stu-id="2119c-131">Your employees, onsite contractors, onsite agents, and so on can't be added as guests.</span></span> <span data-ttu-id="2119c-132">同樣適用于您的公司。</span><span class="sxs-lookup"><span data-stu-id="2119c-132">The same applies to your affiliates.</span></span>
- <span data-ttu-id="2119c-133">來賓授權會根據邀請的組織數來計算。</span><span class="sxs-lookup"><span data-stu-id="2119c-133">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="2119c-134">當您計算所需的授權數量時，請考慮這麼做。</span><span class="sxs-lookup"><span data-stu-id="2119c-134">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="2119c-135">無論受邀者是來自另一個 Office 365 租使用者，還是正在使用其個人電子郵件地址，都會針對您的組織計算授權。</span><span class="sxs-lookup"><span data-stu-id="2119c-135">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a><span data-ttu-id="2119c-136">□步驟1：設定 Azure AD 企業對企業中的設定</span><span class="sxs-lookup"><span data-stu-id="2119c-136">□  Step 1: Configure settings in Azure AD business-to-business</span></span>

1. <span data-ttu-id="2119c-137">以租使用者管理員的身分登入[Azure 入口網站](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="2119c-137">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="2119c-138">選取 [ **Azure Active Directory** > **使用者** > ]**使用者設定**。</span><span class="sxs-lookup"><span data-stu-id="2119c-138">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="2119c-139">在 [**外部使用者**] 底下，選取 [**管理外部**共同作業設定]。</span><span class="sxs-lookup"><span data-stu-id="2119c-139">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="2119c-140">您也可以從 [**組織關聯**] 頁面取得外部共同作業**設定**。</span><span class="sxs-lookup"><span data-stu-id="2119c-140">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="2119c-141">在 Azure Active Directory 中的 [**管理**] 底下，移至 [**組織關聯** > ]**設定**。</span><span class="sxs-lookup"><span data-stu-id="2119c-141">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="2119c-142">在 [**外部**共同作業設定] 頁面上，選擇您要啟用的原則。</span><span class="sxs-lookup"><span data-stu-id="2119c-142">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

  - <span data-ttu-id="2119c-143">**來賓使用者許可權有限**：此原則會判斷您目錄中來賓的許可權。</span><span class="sxs-lookup"><span data-stu-id="2119c-143">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="2119c-144">選取 **[是]** 來封鎖特定目錄工作的訪客，例如列舉使用者、群組或其他目錄資源。</span><span class="sxs-lookup"><span data-stu-id="2119c-144">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="2119c-145">選取 [**否**]，為來賓提供與目錄中的一般使用者相同的目錄資料存取權。</span><span class="sxs-lookup"><span data-stu-id="2119c-145">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
   - <span data-ttu-id="2119c-146">**來賓 inviter 角色中的管理員和使用者可以邀請**：若要允許「來賓 inviter」角色中的系統管理員和使用者邀請客人，請將此原則設定為 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="2119c-146">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
   - <span data-ttu-id="2119c-147">**成員可以邀請**：若要允許目錄的非系統管理員成員邀請客人，請將此原則設定為 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="2119c-147">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes**.</span></span>
   
       > [!NOTE]
       > <span data-ttu-id="2119c-148">如果您設定 [**成員可以**在 Office 365 群組和 Microsoft 團隊中邀請您**不**想再啟用來賓存取]，系統管理員可以控制您的目錄的來賓邀請。</span><span class="sxs-lookup"><span data-stu-id="2119c-148">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="2119c-149">來賓在目錄中後，就可以由非系統管理員成員，將它們新增至小組。</span><span class="sxs-lookup"><span data-stu-id="2119c-149">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span> <span data-ttu-id="2119c-150">如需詳細資訊，請參閱[授權 Microsoft 團隊中的來賓存取](Teams-dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="2119c-150">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
   
   - <span data-ttu-id="2119c-151">**客人可以邀請**：若要讓客人邀請其他客人，請將此原則設定為 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="2119c-151">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
   - <span data-ttu-id="2119c-152">**啟用電子郵件的一次性密碼（預覽版）**：如需一次性密碼功能的詳細資訊，請參閱[電子郵件一次性密碼驗證（預覽版）](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode)。</span><span class="sxs-lookup"><span data-stu-id="2119c-152">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>

   - <span data-ttu-id="2119c-153">共同作業**限制**：如需有關允許或封鎖特定網域之邀請的詳細資訊，請參閱[允許或封鎖來自特定組織的 B2B 使用者邀請](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)。</span><span class="sxs-lookup"><span data-stu-id="2119c-153">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
    
## <a name="-step-2-configure-office-365-groups"></a><span data-ttu-id="2119c-154">□步驟2：設定 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="2119c-154">□ Step 2: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="2119c-155">在 Microsoft 365 系統管理中心，移至 [**設定** > **服務] & [增益集** > ]**Office 365 群組**。</span><span class="sxs-lookup"><span data-stu-id="2119c-155">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="2119c-156">確認將**組織存取群組內容外的群組成員**設定為 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="2119c-156">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="2119c-157">如果關閉此設定，來賓將無法存取任何群組內容。</span><span class="sxs-lookup"><span data-stu-id="2119c-157">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="2119c-158">確認 **[允許群組擁有者將組織外部的人員新增至群組**] 已設定為 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="2119c-158">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="2119c-159">如果關閉此設定，小組擁有者將無法新增來賓。</span><span class="sxs-lookup"><span data-stu-id="2119c-159">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="2119c-160">此設定至少必須開啟才能支援來賓存取。</span><span class="sxs-lookup"><span data-stu-id="2119c-160">At a minimum, this setting must be On to support guest access.</span></span>

     ![螢幕擷取畫面顯示 Office 365 群組的切換](media/guest-access-checklist-office365.png)

<span data-ttu-id="2119c-162">如需設定這些設定的詳細指示，請參閱[管理 office 365 群組中的來賓存取](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150)，以及[控制 office 365 群組中的來賓存取權](Teams-dependencies.md#control-guest-access-in-office-365-groups)。</span><span class="sxs-lookup"><span data-stu-id="2119c-162">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="2119c-163">□步驟3：啟用租使用者層級的來賓存取權</span><span class="sxs-lookup"><span data-stu-id="2119c-163">□ Step 3: Enable guest access at the tenant level</span></span>

<span data-ttu-id="2119c-164">您必須至少針對**Microsoft 團隊系統管理中心**的 microsoft 團隊開啟來賓存取權。</span><span class="sxs-lookup"><span data-stu-id="2119c-164">At a minimum, you must turn on guest access for Microsoft Teams under the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="2119c-165">在 [團隊管理中心] 中，選取 [全**組織性設定** > **來賓存取**]。</span><span class="sxs-lookup"><span data-stu-id="2119c-165">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="2119c-166">將 [**允許 Microsoft 團隊中的來賓存取權**] 切換為 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="2119c-166">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![螢幕擷取畫面顯示 [團隊設定] 切換開關的範例](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="2119c-168">在此相同頁面上，設定您所需的任何其他來賓設定。</span><span class="sxs-lookup"><span data-stu-id="2119c-168">On this same page, configure any other guest settings that you require.</span></span>
4. <span data-ttu-id="2119c-169">按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="2119c-169">Click **Save**.</span></span>

<span data-ttu-id="2119c-170">如需詳細指示，請參閱[開啟或關閉 Microsoft 團隊的來賓存取權](set-up-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="2119c-170">For detailed instructions, see [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="--step-4-configure-sharing-in-office-365"></a><span data-ttu-id="2119c-171">□步驟4：在 Office 365 中設定共用</span><span class="sxs-lookup"><span data-stu-id="2119c-171">□  Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="2119c-172">請確定使用者可以新增來賓。</span><span class="sxs-lookup"><span data-stu-id="2119c-172">Make sure that users can add guests.</span></span> <span data-ttu-id="2119c-173">做法如下：</span><span class="sxs-lookup"><span data-stu-id="2119c-173">Here's how:</span></span>

1. <span data-ttu-id="2119c-174">在 Microsoft 365 系統管理中心中，移至 [**設定** > **安全性] & [隱私權**]。</span><span class="sxs-lookup"><span data-stu-id="2119c-174">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![螢幕擷取畫面顯示服務設定的範例](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="2119c-176">在 [**共用**] 中，選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="2119c-176">In **Sharing**, select **Edit**.</span></span>

     ![螢幕擷取畫面顯示共用設定切換的範例](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="2119c-178">設定 [**讓使用者將新的來賓新增至此組織** **]，然後**按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="2119c-178">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![螢幕擷取畫面顯示共用設定切換的範例](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> <span data-ttu-id="2119c-180">這個設定相當於 Azure AD 中的 [**使用者設定** > **] 中的**[**成員可以邀請**] 設定。</span><span class="sxs-lookup"><span data-stu-id="2119c-180">This setting is equivalent to the **Members can invite** setting in  **User settings** > **External users**  in Azure AD.</span></span>  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="2119c-181">□步驟5：驗證 SharePoint 中的共用設定</span><span class="sxs-lookup"><span data-stu-id="2119c-181">□ Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="2119c-182">登入 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="2119c-182">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="2119c-183">按一下 [系統**管理中心**]，然後選取 [ **SharePoint**]。</span><span class="sxs-lookup"><span data-stu-id="2119c-183">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="2119c-184">在 SharePoint 系統管理中心中，選取 [**共用**]。</span><span class="sxs-lookup"><span data-stu-id="2119c-184">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="2119c-185">確定*沒有*選取 [不**允許在您的組織外共用**] 選項。</span><span class="sxs-lookup"><span data-stu-id="2119c-185">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![螢幕擷取畫面顯示 SparePoint Online 設定切換開關的範例。](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a><span data-ttu-id="2119c-187">□步驟6：啟用頻道的特定設定</span><span class="sxs-lookup"><span data-stu-id="2119c-187">□ Step 6: Enable specific settings for channels</span></span> 

<span data-ttu-id="2119c-188">在團隊應用程式的個別小組層級，設定來賓許可權，讓來賓可以建立、更新及刪除頻道。</span><span class="sxs-lookup"><span data-stu-id="2119c-188">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="2119c-189">除了管理員之外，小組擁有者還可以設定此設定。</span><span class="sxs-lookup"><span data-stu-id="2119c-189">In addition to admins,  team owners can configure this setting.</span></span>

![螢幕擷取畫面顯示 [團隊/頻道設定] 切換開關的範例](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="2119c-191">如需詳細資訊（包括操作說明影片），請參閱[Microsoft 團隊中的來賓存取權](guest-access.md)。</span><span class="sxs-lookup"><span data-stu-id="2119c-191">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="2119c-192">疑難排解</span><span class="sxs-lookup"><span data-stu-id="2119c-192">Troubleshooting</span></span>

<span data-ttu-id="2119c-193">如果您在 Microsoft 團隊中新增來賓時遇到問題，請參閱[來賓存取疑難排解指南](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797)。</span><span class="sxs-lookup"><span data-stu-id="2119c-193">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


