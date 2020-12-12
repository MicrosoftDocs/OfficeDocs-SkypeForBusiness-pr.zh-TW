---
title: 管理 Microsoft Teams Exploratory 體驗
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: Admin
ms.reviewer: baluc
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: 未取得 Microsoft Teams 授權的 Microsoft 365 或 Office 365 使用者可以起始 Exploratory Teams 授權。
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: df06c03ab37a98c5ea4404d8dbd12703b07ad3ee
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611807"
---
# <a name="manage-the-microsoft-teams-exploratory-license"></a><span data-ttu-id="8bed1-103">管理 Microsoft Teams Exploratory 授權</span><span class="sxs-lookup"><span data-stu-id="8bed1-103">Manage the Microsoft Teams Exploratory license</span></span>

<span data-ttu-id="8bed1-p101">Microsoft Teams Exploratory 體驗可讓貴組織中擁有 Azure Active Directory (Azure AD) 和未取得 Teams 授權的使用者起始 Teams 探勘體驗。系統管理員可以為其組織中的使用者開啟或關閉這項功能。舊版 [Microsoft 商務雲端試用版](iw-trial-teams.md)現在已由 Teams Exploratory 體驗取代。</span><span class="sxs-lookup"><span data-stu-id="8bed1-p101">The Microsoft Teams Exploratory experience lets users in your organization who have Azure Active Directory (Azure AD) and aren't licensed for Teams initiate an exploratory experience of Teams. Admins can switch this feature on or off for users in their organization. The earlier [Microsoft Commercial Cloud Trial](iw-trial-teams.md) is now replaced by The Teams Exploratory experience.</span></span>

## <a name="whats-in-the-teams-exploratory-experience"></a><span data-ttu-id="8bed1-107">Microsoft Teams Exploratory 體驗有什麼內容</span><span class="sxs-lookup"><span data-stu-id="8bed1-107">What's in the Teams Exploratory experience</span></span>

<span data-ttu-id="8bed1-108">系統管理員將在 Teams Exploratory 體驗中看到的服務方案如下：</span><span class="sxs-lookup"><span data-stu-id="8bed1-108">The service plans that an admin will see as part of the Teams Exploratory experience are:</span></span>

- <span data-ttu-id="8bed1-109">Exchange Online (方案 1)</span><span class="sxs-lookup"><span data-stu-id="8bed1-109">Exchange Online (Plan 1)</span></span>
- <span data-ttu-id="8bed1-110">Microsoft 365 或 Office 365 的流程</span><span class="sxs-lookup"><span data-stu-id="8bed1-110">Flow for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="8bed1-111">MyAnalytics 的深入解析</span><span class="sxs-lookup"><span data-stu-id="8bed1-111">Insights by MyAnalytics</span></span>
- <span data-ttu-id="8bed1-112">Microsoft Forms (方案 E1)</span><span class="sxs-lookup"><span data-stu-id="8bed1-112">Microsoft Forms (Plan E1)</span></span>
- <span data-ttu-id="8bed1-113">Microsoft Planner</span><span class="sxs-lookup"><span data-stu-id="8bed1-113">Microsoft Planner</span></span>
- <span data-ttu-id="8bed1-114">Microsoft 搜尋</span><span class="sxs-lookup"><span data-stu-id="8bed1-114">Microsoft Search</span></span>
- <span data-ttu-id="8bed1-115">Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="8bed1-115">Microsoft StaffHub</span></span>
- <span data-ttu-id="8bed1-116">適用於 Microsoft 365 和 Office 365 E1 SKU 的 Microsoft Stream <sup>1</1></span><span class="sxs-lookup"><span data-stu-id="8bed1-116">Microsoft Stream for Microsoft 365 and Office 365 E1 SKUs <sup>1</1></span></span>
- <span data-ttu-id="8bed1-117">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8bed1-117">Microsoft Teams</span></span>
- <span data-ttu-id="8bed1-118">Microsoft 365 或 Office 365 的行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="8bed1-118">Mobile Device Management for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="8bed1-119">適用於 Office 365 的 Office 行動裝置應用程式</span><span class="sxs-lookup"><span data-stu-id="8bed1-119">Office Mobile Apps for Office 365</span></span>
- <span data-ttu-id="8bed1-120">Office Online</span><span class="sxs-lookup"><span data-stu-id="8bed1-120">Office Online</span></span>
- <span data-ttu-id="8bed1-121">適用於 Microsoft 365 或 Office 365 的 PowerApps</span><span class="sxs-lookup"><span data-stu-id="8bed1-121">PowerApps for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="8bed1-122">SharePoint Online (方案 1)</span><span class="sxs-lookup"><span data-stu-id="8bed1-122">SharePoint Online (Plan 1)</span></span>
- <span data-ttu-id="8bed1-123">Sway</span><span class="sxs-lookup"><span data-stu-id="8bed1-123">Sway</span></span>
- <span data-ttu-id="8bed1-124">To-Do (方案 1)</span><span class="sxs-lookup"><span data-stu-id="8bed1-124">To-Do (Plan 1)</span></span>
- <span data-ttu-id="8bed1-125">Whiteboard (方案 1)</span><span class="sxs-lookup"><span data-stu-id="8bed1-125">Whiteboard (Plan 1)</span></span>
- <span data-ttu-id="8bed1-126">Yammer Enterprise</span><span class="sxs-lookup"><span data-stu-id="8bed1-126">Yammer Enterprise</span></span>

  <span data-ttu-id="8bed1-127"><sup>1</sup> 從使用 Microsoft Stream 到變更為使用[商務用 OneDrive 和 OneDrive 來進行會議錄製](tmr-meeting-recording-change.md)，將會採取階段性的方式。</span><span class="sxs-lookup"><span data-stu-id="8bed1-127"><sup>1</sup> The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach.</span></span> <span data-ttu-id="8bed1-128">啟動時，您將可以選擇加入此體驗。</span><span class="sxs-lookup"><span data-stu-id="8bed1-128">At launch, you'll be able to opt in to this experience.</span></span> <span data-ttu-id="8bed1-129">在 11 月，如果您想繼續使用 Stream，您將必須選擇退出。</span><span class="sxs-lookup"><span data-stu-id="8bed1-129">In November, you'll have to opt out if you want to continue using Stream.</span></span> <span data-ttu-id="8bed1-130">2021 年初，我們將要求所有客戶使用商務用 OneDrive 和 SharePoint 進行新的會議錄製。</span><span class="sxs-lookup"><span data-stu-id="8bed1-130">Sometime in early 2021, we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

## <a name="whos-eligible"></a><span data-ttu-id="8bed1-131">符合使用資格的對象</span><span class="sxs-lookup"><span data-stu-id="8bed1-131">Who's eligible</span></span>

<span data-ttu-id="8bed1-132">用戶符合 Teams Exploratory 體驗的標準，如果他們滿足以下條件：</span><span class="sxs-lookup"><span data-stu-id="8bed1-132">Users fit the criteria for a Teams Exploratory experience if they:</span></span>

- <span data-ttu-id="8bed1-133">有受管理的 Azure AD 網域電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="8bed1-133">Have a managed Azure AD domain email address.</span></span>
- <span data-ttu-id="8bed1-134">屬於具有付費訂閱的租用戶。</span><span class="sxs-lookup"><span data-stu-id="8bed1-134">Belong to a tenant with a paid subscription.</span></span>

<span data-ttu-id="8bed1-p103">必須啟用使用者才能註冊應用程式和試用版 (於 Microsoft 365 系統管理中心)。如需詳細資訊，請參閱本文稍後的[管理 Teams Exploratory 體驗](#manage-the-teams-exploratory-experience)。</span><span class="sxs-lookup"><span data-stu-id="8bed1-p103">Users must be enabled to sign up for apps and trials (in the Microsoft 365 admin center). For more information, see [Manage the Teams Exploratory experience](#manage-the-teams-exploratory-experience), later in this article.</span></span>

## <a name="who-isnt-eligible"></a><span data-ttu-id="8bed1-137">不符合使用資格的對象</span><span class="sxs-lookup"><span data-stu-id="8bed1-137">Who isn't eligible</span></span>

<span data-ttu-id="8bed1-138">使用者在以下情況不符合條件：</span><span class="sxs-lookup"><span data-stu-id="8bed1-138">Users don't fit the criteria if they:</span></span>

- <span data-ttu-id="8bed1-139">目前或先前具有付費、未付款或試用版授權的 Teams</span><span class="sxs-lookup"><span data-stu-id="8bed1-139">Currently or previously had Teams from a paid, unpaid, or trial license</span></span>
- <span data-ttu-id="8bed1-140">位於至少使用過/收到過一個特殊 COVID 特殊優惠的租使用者中。</span><span class="sxs-lookup"><span data-stu-id="8bed1-140">Are in a tenant that used/received at least one special COVID offer.</span></span>

<span data-ttu-id="8bed1-141">如果您是整合合作夥伴客戶，或是 GCC、GCC High、DoD 或 EDU 客戶，則貴組織不符合使用資格。</span><span class="sxs-lookup"><span data-stu-id="8bed1-141">Your organization isn't eligible for this offer if you're a Syndication Partner Customer or a GCC, GCC High, DoD, or EDU customer.</span></span>

## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a><span data-ttu-id="8bed1-142">使用者註冊 Teams Exploratory 體驗的方式</span><span class="sxs-lookup"><span data-stu-id="8bed1-142">How users sign up for the Teams Exploratory experience</span></span>

<span data-ttu-id="8bed1-143">合格的使用者可以透過登入 Teams 電腦版或網頁版 ([teams.microsoft.com](https://teams.microsoft.com)) 來註冊取得 Teams Exploratory 體驗。</span><span class="sxs-lookup"><span data-stu-id="8bed1-143">Eligible users can sign up for the Teams Exploratory experience by signing in to Teams from the desktop or web ([teams.microsoft.com](https://teams.microsoft.com)).</span></span> <span data-ttu-id="8bed1-144">目前不支援透過行動裝置啟用 Exploratory。</span><span class="sxs-lookup"><span data-stu-id="8bed1-144">At this time, enabling Exploratory through mobile is not supported.</span></span> <span data-ttu-id="8bed1-145">使用者註冊後，系統會自動指派此授權，且租用戶系統管理員在組織中的人員第一次啟動 Teams Exploratory 體驗時，將會收到電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="8bed1-145">When they sign up, they'll be assigned this license automatically and the tenant admin will receive an email notification the first time someone in your org starts the Teams Exploratory experience.</span></span>

## <a name="manage-the-teams-exploratory-experience"></a><span data-ttu-id="8bed1-146">管理 Teams Exploratory 體驗</span><span class="sxs-lookup"><span data-stu-id="8bed1-146">Manage the Teams Exploratory experience</span></span>

<span data-ttu-id="8bed1-147">Teams Exploratory 體驗應由個別使用者起始，而您可能無法代表使用者員工起始此服務。</span><span class="sxs-lookup"><span data-stu-id="8bed1-147">The Teams Exploratory experience is meant to be initiated by individual end users, and you can't initiate this offer on behalf of end-user employees.</span></span>

<span data-ttu-id="8bed1-p105">Teams Exploratory 體驗隨附 Exchange Online 授權，但在系統管理員指派之前，不會指派給使用者。如果使用者沒有 Exchange 授權，且系統管理員尚未指派 Exchange Online 授權，則使用者將無法在 Teams 中排程會議，且可能會遺失其他 Teams 功能。</span><span class="sxs-lookup"><span data-stu-id="8bed1-p105">The Teams Exploratory experience comes with an Exchange Online license, but it won't be assigned to the user until the admin assigns it. If the user doesn't have an Exchange license already, and the admin has yet to assign the Exchange Online license, the user won't be able to schedule meetings in Teams and might be missing other Teams functionality.</span></span>

<span data-ttu-id="8bed1-150">系統管理員可以使用 **試用版應用程式和服務** 切換功能來停用使用者在其組織內執行 Teams Exploratory 體驗。</span><span class="sxs-lookup"><span data-stu-id="8bed1-150">Admins can disable the ability for end users to run the Teams Exploratory experience within their organization by using the **Trial apps and services** switch.</span></span>

### <a name="prevent-users-from-installing-trial-apps-and-services"></a><span data-ttu-id="8bed1-151">防止使用者安裝試用版應用程式和服務</span><span class="sxs-lookup"><span data-stu-id="8bed1-151">Prevent users from installing trial apps and services</span></span>

<span data-ttu-id="8bed1-152">您可以關閉使用者安裝試用版應用程式和服務的功能，即可防止使用者執行 Teams Exploratory 體驗。</span><span class="sxs-lookup"><span data-stu-id="8bed1-152">You can turn off a user's ability to install trial apps and services, which would prevent the user from running the Teams Exploratory experience.</span></span>

1. <span data-ttu-id="8bed1-153">從 [Microsoft 365 系統管理中心]，移至 **[設定]** > **[組織設定]**、選取 **[服務]**，然後選取 **[使用者所擁有的應用程式與服務]**。</span><span class="sxs-lookup"><span data-stu-id="8bed1-153">From the Microsoft 365 admin center, go to **Settings** > **Org settings**, select **Services**, and then select **User owned apps and services**.</span></span>

    ![系統管理中心的 [服務] 頁面](media/iw-trial-services.png)

2. <span data-ttu-id="8bed1-155">取消選取 **[讓使用者安裝試用版的應用程式與服務]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8bed1-155">Clear the check mark from **Let users install trial apps and services**.</span></span>

    ![系統管理中心的 [使用者所擁有的應用程式與服務] 頁面](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > <span data-ttu-id="8bed1-157">如果貴組織不符合 Teams Exploratory 使用資格，您將不會看到 **[讓使用者安裝試用版的應用程式與服務]** 選項。</span><span class="sxs-lookup"><span data-stu-id="8bed1-157">If your organization is ineligible for the Teams Exploratory experience, you won't see the **Let users install trial apps and services** option.</span></span>

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a><span data-ttu-id="8bed1-158">管理具有包含 Teams 授權使用者的可用性</span><span class="sxs-lookup"><span data-stu-id="8bed1-158">Manage availability for a user with a license that includes Teams</span></span>

<span data-ttu-id="8bed1-p106">已獲派含 Teams 授權的使用者不符合 Teams Exploratory 體驗的使用資格。開啟 Teams 服務方案後，使用者就可以登入並使用 Teams。如果服務方案已停用，則使用者無法登入，也無法使用 Teams Exploratory 體驗。您必須具備系統管理員權限。</span><span class="sxs-lookup"><span data-stu-id="8bed1-p106">A user who is assigned a license that includes Teams isn't eligible for the Teams Exploratory experience. When the Teams service plan is turned on, the user can sign in and use Teams. If the service plan is disabled, the user can't sign in and the Teams Exploratory experience isn't available. You must have admin privileges.</span></span>

<span data-ttu-id="8bed1-163">若要關閉對 Teams 的存取：</span><span class="sxs-lookup"><span data-stu-id="8bed1-163">To turn off access to Teams:</span></span>

1. <span data-ttu-id="8bed1-164">在 Microsoft 365 系統管理中心，選取 **[使用者]**  >  **[作用中的使用者]**。</span><span class="sxs-lookup"><span data-stu-id="8bed1-164">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="8bed1-165">選取使用者名稱旁的方塊。</span><span class="sxs-lookup"><span data-stu-id="8bed1-165">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="8bed1-166">在 **[產品授權]** 列中，選擇 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="8bed1-166">In the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="8bed1-167">在 **[產品授權]** 窗格中，將開關切換至 **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="8bed1-167">In the **Product licenses** pane, switch the toggle to **Off**.</span></span>

    ![系統管理中心的 [產品授權] 頁面。](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a><span data-ttu-id="8bed1-169">管理已在使用 Teams Exploratory 體驗之使用者的 Teams 可用性</span><span class="sxs-lookup"><span data-stu-id="8bed1-169">Manage Teams availability for users who are already using the Teams Exploratory experience</span></span>

<span data-ttu-id="8bed1-p107">如果使用者正在執行 Teams Exploratory 體驗，您可以移除授權或服務方案將它關閉。您必須具備系統管理員權限。</span><span class="sxs-lookup"><span data-stu-id="8bed1-p107">If a user is running the Teams Exploratory experience, you can turn it off by removing the license or service plan. You must have admin privileges.</span></span>

<span data-ttu-id="8bed1-172">若要關閉 Teams Exploratory 體驗授權：</span><span class="sxs-lookup"><span data-stu-id="8bed1-172">To turn off the Teams Exploratory experience license:</span></span>

1. <span data-ttu-id="8bed1-173">在 Microsoft 365 系統管理中心，選取 **[使用者]**  >  **[作用中的使用者]**。</span><span class="sxs-lookup"><span data-stu-id="8bed1-173">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="8bed1-174">選取使用者名稱旁的方塊。</span><span class="sxs-lookup"><span data-stu-id="8bed1-174">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="8bed1-175">在 **[產品授權]** 列中，選擇 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="8bed1-175">In the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="8bed1-176">在 **[產品授權]** 窗格中，將此探勘授權的開關切換至 **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="8bed1-176">In the **Product licenses** pane, switch the toggle for this exploratory license to **Off**.</span></span>

    >[!Note]
    ><span data-ttu-id="8bed1-177">組織中的第一個使用者啟動 Teams Exploratory 體驗之後，將會出現 [Teams Exploratory] 切換開關。</span><span class="sxs-lookup"><span data-stu-id="8bed1-177">The Teams Exploratory toggle switch will appear after the first user in the organization launches the Teams Exploratory experience.</span></span>

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a><span data-ttu-id="8bed1-178">管理適用於擁有 Teams Exploratory 授權之使用者的 Teams</span><span class="sxs-lookup"><span data-stu-id="8bed1-178">Manage Teams for users who have the Teams Exploratory license</span></span>

<span data-ttu-id="8bed1-p108">您可以管理擁有 Teams Exploratory 授權的使用者，就像您管理擁有一般付費授權的使用者一般。如需詳細資訊，請參閱[管理組織的 Teams 設定](enable-features-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="8bed1-p108">You can manage users who have the Teams Exploratory license just like you manage users who have a regular paid license. For more information, see [Manage Teams settings for your organization](enable-features-office-365.md).</span></span>

### <a name="upgrade-users-from-the-teams-exploratory-license"></a><span data-ttu-id="8bed1-181">從 Teams Exploratory 授權升級使用者</span><span class="sxs-lookup"><span data-stu-id="8bed1-181">Upgrade users from the Teams Exploratory license</span></span>

<span data-ttu-id="8bed1-182">若要從 Teams Exploratory 授權升級使用者 (您必須擁有系統管理員權限)，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="8bed1-182">To upgrade users from the Teams Exploratory license (you must have admin privileges), do the following tasks:</span></span>

1. <span data-ttu-id="8bed1-183">購買包括 Teams 的訂閱。</span><span class="sxs-lookup"><span data-stu-id="8bed1-183">Purchase a subscription that includes Teams.</span></span>

2. <span data-ttu-id="8bed1-184">從使用者移除 Teams Exploratory 訂閱。</span><span class="sxs-lookup"><span data-stu-id="8bed1-184">Remove the Teams Exploratory subscription from the user.</span></span>

3. <span data-ttu-id="8bed1-185">指派新購買的授權。</span><span class="sxs-lookup"><span data-stu-id="8bed1-185">Assign the newly purchased license.</span></span>

<span data-ttu-id="8bed1-186">如需詳細資訊，請參閱 [Microsoft Teams 服務描述](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="8bed1-186">For more information, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

> [!NOTE]
> <span data-ttu-id="8bed1-p109">如果 Teams Exploratory 授權結束，並且使用者沒有立即陞級至包含 Teams 的訂閱，那麼他們有 30 天的寬限期，然後其後 30 天過後資料將被删除。使用者仍然存在於 Azure Active Directory 中。一旦將新授權指派給使用者以再次啟用 Teams 功能，則如果在寬限期時間範圍內新增使用者，則所有內容仍將存在。</span><span class="sxs-lookup"><span data-stu-id="8bed1-p109">If the Teams Exploratory license ends and a user isn't immediately upgraded to a subscription that includes Teams, they have 30 days of grace period and then another 30 days after which time the data is going to be deleted. The user still exists in Azure Active Directory. Once a new license is assigned to the user to enable Teams functionality again, all content will still exist if the user is added within the grace period time frame.</span></span>

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a><span data-ttu-id="8bed1-190">舊版 Microsoft Teams 商業雲端試用版授權會發生什麼情況</span><span class="sxs-lookup"><span data-stu-id="8bed1-190">What happens to legacy Microsoft Teams Commercial Cloud Trial licenses</span></span>

<span data-ttu-id="8bed1-p110">自 2020 年 2 月起，符合資格的使用者就可以開始使用最新的 Microsoft Teams Exploratory 體驗。所有舊版 Teams 商務雲端試用版授權將在試用到期之前，自動轉換為新方案。</span><span class="sxs-lookup"><span data-stu-id="8bed1-p110">As of February 2020, eligible users can begin using the latest Microsoft Teams Exploratory experience. All legacy Teams Commercial Cloud Trial licenses will be automatically converted to the new offer before their trial expires.</span></span>

<span data-ttu-id="8bed1-p111">當使用者第一次登入過期的 Teams 商務雲端試用版時，系統會自動將 Teams Exploratory 體驗授權指派給該使用者。使用者在登入之後才會進行轉換。</span><span class="sxs-lookup"><span data-stu-id="8bed1-p111">When users sign in to their expired Teams Commercial Cloud Trial for the first time, we automatically assign a Teams Exploratory experience license to those users. Users aren't converted until they sign in.</span></span>

### <a name="remove-a-teams-exploratory-license"></a><span data-ttu-id="8bed1-195">移除 Teams Exploratory 授權</span><span class="sxs-lookup"><span data-stu-id="8bed1-195">Remove a Teams Exploratory license</span></span>

- <span data-ttu-id="8bed1-196">如果您想要透過 PowerShell 移除此授權，請參閱：[使用 Office 365 PowerShell 從使用者帳戶移除授權](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="8bed1-196">If you would like to remove this license by using PowerShell, see: [Remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span></span>

- <span data-ttu-id="8bed1-197">如果您想要透過系統管理入口網站移除此授權，請參閱：[從貴組織刪除使用者](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)</span><span class="sxs-lookup"><span data-stu-id="8bed1-197">If you would like to remove this license through the admin portal, see: [Delete a user from your organization](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)</span></span>

## <a name="what-is-the-data-retention-policy"></a><span data-ttu-id="8bed1-198">什麼是資料保留原則</span><span class="sxs-lookup"><span data-stu-id="8bed1-198">What is the data retention policy</span></span>

<span data-ttu-id="8bed1-199">請參閲 [Microsoft 365 訂閱資訊](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="8bed1-199">See [Microsoft 365 subscription information](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).</span></span>

## <a name="how-long-does-the-teams-exploratory-experience-last"></a><span data-ttu-id="8bed1-200">Teams Exploratory 體驗持續時間</span><span class="sxs-lookup"><span data-stu-id="8bed1-200">How long does the Teams Exploratory experience last</span></span>

<span data-ttu-id="8bed1-201">Microsoft Teams Exploratory 體驗可免費使用 12 個月 (從第一位使用者註冊開始) 加上 30 天的寬限期。</span><span class="sxs-lookup"><span data-stu-id="8bed1-201">The Microsoft Teams Exploratory experience is available at no additional cost for 12 months (from initial user sign-up) plus an additional 30 day grace period.</span></span> <span data-ttu-id="8bed1-202">屆時 Microsoft Exploratory 體驗授權的使用者將需要移至包括 Teams 的付費授權。</span><span class="sxs-lookup"><span data-stu-id="8bed1-202">At that time, end users on a Microsoft Exploratory experience license will need to move to a paid license that includes Teams.</span></span> <span data-ttu-id="8bed1-203">相同租用戶中的所有使用者適用相同的結束日期，即第一位使用者註冊日期開始的 12 個月。</span><span class="sxs-lookup"><span data-stu-id="8bed1-203">The same end date will apply to all users on the same tenant, with the 12-month term starting on the first user’s sign-up date.</span></span>

### <a name="what-happens-if-an-end-user-initiates-the-microsoft-teams-exploratory-experience-just-before-the-anniversary-or-renewal-date"></a><span data-ttu-id="8bed1-204">如果使用者在週年日或續約日到期前起始 Microsoft Teams Exploratory 體驗，會發生什麼情況</span><span class="sxs-lookup"><span data-stu-id="8bed1-204">What happens if an end user initiates the Microsoft Teams Exploratory experience just before the anniversary or renewal date</span></span>

<span data-ttu-id="8bed1-205">在您的 **合約週年日** 或 **續約** 日 90 天內起始的 Microsoft Teams Exploratory 體驗授權，直到下一個週年日或續約週期為止前，都不需移到付費授權。</span><span class="sxs-lookup"><span data-stu-id="8bed1-205">Microsoft Teams Exploratory experience licenses initiated within 90 days of your **agreement anniversary** or **renewal** won't be required to move to a paid license until the subsequent anniversary or renewal cycle.</span></span>

### <a name="what-if-my-agreement-doesnt-have-an-anniversary-or-yearly-renewal-date-for-example-month-to-month-agreements"></a><span data-ttu-id="8bed1-206">如果我的合約沒有週年日或每年續約日期 (例如月對月合約)，該怎麼辦</span><span class="sxs-lookup"><span data-stu-id="8bed1-206">What if my agreement doesn’t have an anniversary or yearly renewal date (for example, month-to-month agreements)</span></span>

<span data-ttu-id="8bed1-207">對於沒有周年紀念日或每年續約日期的合約，在第一位使用者啟用 Microsoft Teams Exploratory 體驗授權後的第二年將被視為周年紀念日或續約日期。</span><span class="sxs-lookup"><span data-stu-id="8bed1-207">For agreements without an anniversary or yearly renewal date, the subsequent year after the first end user activates the Microsoft Teams Exploratory experience licenses will be treated as the anniversary or renewal date.</span></span> <span data-ttu-id="8bed1-208">根據本文中所述原則，必須在每年的該日期之前將擁有 Microsoft Teams Exploratory 授權的使用者轉換為付費授權。</span><span class="sxs-lookup"><span data-stu-id="8bed1-208">Users on the Microsoft Teams Exploratory license must be converted to a paid license by that date each year, according to the policies outlined in this article.</span></span>

<span data-ttu-id="8bed1-209">例如，如果第一位使用者在 2020 年 6 月 19 日啟用了 Microsoft Teams Exploratory，則他們和客戶租用戶中的所有其他合格使用者必須在 2021 年 6 月 19 日之前轉換為 Teams 的付費授權。</span><span class="sxs-lookup"><span data-stu-id="8bed1-209">For example, if the first end user activates Microsoft Teams Exploratory on June 19, 2020, then they and all other eligible users in the customer tenant must convert to a paid license with Teams by June 19, 2021.</span></span>

> [!Note]
> <span data-ttu-id="8bed1-210">在前一個 Exploratory 體驗授權到期後的 3 個月內客戶將被停用並封鎖開始新 Explaratory 授權。</span><span class="sxs-lookup"><span data-stu-id="8bed1-210">Customers will be disabled and blocked from starting a new Exploratory trial licenses for 3 months past the expiration of their previous Exploratory trial license.</span></span>
