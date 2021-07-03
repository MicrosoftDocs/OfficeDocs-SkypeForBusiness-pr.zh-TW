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
ms.openlocfilehash: 8803219c93a66d7094ce6ca1aa635f1fbff8580e
ms.sourcegitcommit: b39bd1de0219a9e3a3b0c97fc485c9578ddb643c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2021
ms.locfileid: "53230550"
---
# <a name="manage-the-microsoft-teams-exploratory-license"></a><span data-ttu-id="bcccc-103">管理 Microsoft Teams Exploratory 授權</span><span class="sxs-lookup"><span data-stu-id="bcccc-103">Manage the Microsoft Teams Exploratory license</span></span>

<span data-ttu-id="bcccc-p101">Microsoft Teams Exploratory 體驗可讓貴組織中擁有 Azure Active Directory (Azure AD) 和未取得 Teams 授權的使用者起始 Teams 探勘體驗。系統管理員可以為其組織中的使用者開啟或關閉這項功能。</span><span class="sxs-lookup"><span data-stu-id="bcccc-p101">The Microsoft Teams Exploratory experience lets users in your organization who have Azure Active Directory (Azure AD) and aren't licensed for Teams initiate an exploratory experience of Teams. Admins can switch this feature on or off for users in their organization.</span></span>

## <a name="whats-in-the-teams-exploratory-experience"></a><span data-ttu-id="bcccc-106">Microsoft Teams Exploratory 體驗有什麼內容</span><span class="sxs-lookup"><span data-stu-id="bcccc-106">What's in the Teams Exploratory experience</span></span>

<span data-ttu-id="bcccc-107">系統管理員將在 Teams Exploratory 體驗中看到的服務方案如下：</span><span class="sxs-lookup"><span data-stu-id="bcccc-107">The service plans that an admin will see as part of the Teams Exploratory experience are:</span></span>

- <span data-ttu-id="bcccc-108">Exchange Online (方案 1)</span><span class="sxs-lookup"><span data-stu-id="bcccc-108">Exchange Online (Plan 1)</span></span>
- <span data-ttu-id="bcccc-109">Microsoft 365 或 Office 365 的流程</span><span class="sxs-lookup"><span data-stu-id="bcccc-109">Flow for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="bcccc-110">MyAnalytics 的深入解析</span><span class="sxs-lookup"><span data-stu-id="bcccc-110">Insights by MyAnalytics</span></span>
- <span data-ttu-id="bcccc-111">Microsoft Forms (方案 E1)</span><span class="sxs-lookup"><span data-stu-id="bcccc-111">Microsoft Forms (Plan E1)</span></span>
- <span data-ttu-id="bcccc-112">Microsoft Planner</span><span class="sxs-lookup"><span data-stu-id="bcccc-112">Microsoft Planner</span></span>
- <span data-ttu-id="bcccc-113">Microsoft 搜尋</span><span class="sxs-lookup"><span data-stu-id="bcccc-113">Microsoft Search</span></span>
- <span data-ttu-id="bcccc-114">Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="bcccc-114">Microsoft StaffHub</span></span>
- <span data-ttu-id="bcccc-115">適用於 Microsoft 365 和 Office 365 E1 SKU 的 Microsoft Stream <sup>1</1></span><span class="sxs-lookup"><span data-stu-id="bcccc-115">Microsoft Stream for Microsoft 365 and Office 365 E1 SKUs <sup>1</1></span></span>
- <span data-ttu-id="bcccc-116">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bcccc-116">Microsoft Teams</span></span>
- <span data-ttu-id="bcccc-117">Microsoft 365 或 Office 365 的行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="bcccc-117">Mobile Device Management for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="bcccc-118">適用於 Office 365 的 Office 行動裝置應用程式</span><span class="sxs-lookup"><span data-stu-id="bcccc-118">Office Mobile Apps for Office 365</span></span>
- <span data-ttu-id="bcccc-119">Office Online</span><span class="sxs-lookup"><span data-stu-id="bcccc-119">Office Online</span></span>
- <span data-ttu-id="bcccc-120">適用於 Microsoft 365 或 Office 365 的 PowerApps</span><span class="sxs-lookup"><span data-stu-id="bcccc-120">PowerApps for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="bcccc-121">SharePoint Online (方案 1)</span><span class="sxs-lookup"><span data-stu-id="bcccc-121">SharePoint Online (Plan 1)</span></span>
- <span data-ttu-id="bcccc-122">Sway</span><span class="sxs-lookup"><span data-stu-id="bcccc-122">Sway</span></span>
- <span data-ttu-id="bcccc-123">To-Do (方案 1)</span><span class="sxs-lookup"><span data-stu-id="bcccc-123">To-Do (Plan 1)</span></span>
- <span data-ttu-id="bcccc-124">Whiteboard (方案 1)</span><span class="sxs-lookup"><span data-stu-id="bcccc-124">Whiteboard (Plan 1)</span></span>
- <span data-ttu-id="bcccc-125">Yammer Enterprise</span><span class="sxs-lookup"><span data-stu-id="bcccc-125">Yammer Enterprise</span></span>

  <span data-ttu-id="bcccc-p102"><sup>1</sup> 從使用 Microsoft Stream 變更為使用[商務用 OneDrive 和 SharePoint 來進行會議錄製](tmr-meeting-recording-change.md)，將會採取階段性的方式。推出時，您將可以加入此體驗。在 11 月，如果您想要繼續使用 Stream，則必須退出體驗。在 2021 年初的某個時候，我們將要求所有客戶使用商務用 OneDrive 和 SharePoint 來進行會議錄製。</span><span class="sxs-lookup"><span data-stu-id="bcccc-p102"><sup>1</sup> The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach. At launch, you'll be able to opt in to this experience. In November, you'll have to opt out if you want to continue using Stream. Sometime in early 2021, we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

## <a name="whos-eligible"></a><span data-ttu-id="bcccc-130">符合使用資格的對象</span><span class="sxs-lookup"><span data-stu-id="bcccc-130">Who's eligible</span></span>

<span data-ttu-id="bcccc-131">用戶符合 Teams Exploratory 體驗的標準，如果他們滿足以下條件：</span><span class="sxs-lookup"><span data-stu-id="bcccc-131">Users fit the criteria for a Teams Exploratory experience if they:</span></span>

- <span data-ttu-id="bcccc-132">有受管理的 Azure AD 網域電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="bcccc-132">Have a managed Azure AD domain email address.</span></span>
- <span data-ttu-id="bcccc-133">屬於具有付費訂閱的租用戶。</span><span class="sxs-lookup"><span data-stu-id="bcccc-133">Belong to a tenant with a paid subscription.</span></span>
- <span data-ttu-id="bcccc-134">沒有有效的 Teams 授權。</span><span class="sxs-lookup"><span data-stu-id="bcccc-134">Do not have an active Teams license.</span></span>
- <span data-ttu-id="bcccc-135">不在已建立授權指派原則的租用戶中。</span><span class="sxs-lookup"><span data-stu-id="bcccc-135">Are not in a tenant where a license assignment policy was created.</span></span>

<span data-ttu-id="bcccc-p103">必須啟用使用者才能註冊應用程式和試用版 (於 Microsoft 365 系統管理中心)。如需詳細資訊，請參閱本文稍後的[管理 Teams Exploratory 體驗](#manage-the-teams-exploratory-experience)。</span><span class="sxs-lookup"><span data-stu-id="bcccc-p103">Users must be enabled to sign up for apps and trials (in the Microsoft 365 admin center). For more information, see [Manage the Teams Exploratory experience](#manage-the-teams-exploratory-experience), later in this article.</span></span>

## <a name="who-isnt-eligible"></a><span data-ttu-id="bcccc-138">不符合使用資格的對象</span><span class="sxs-lookup"><span data-stu-id="bcccc-138">Who isn't eligible</span></span>

<span data-ttu-id="bcccc-139">使用者在以下情況不符合條件：</span><span class="sxs-lookup"><span data-stu-id="bcccc-139">Users don't fit the criteria if they:</span></span>

- <span data-ttu-id="bcccc-140">目前或先前具有付費、未付款或試用版授權的 Teams</span><span class="sxs-lookup"><span data-stu-id="bcccc-140">Currently or previously had Teams from a paid, unpaid, or trial license</span></span>
- <span data-ttu-id="bcccc-141">位於至少使用過/收到過一個特殊 COVID 特殊優惠的租使用者中。</span><span class="sxs-lookup"><span data-stu-id="bcccc-141">Are in a tenant that used/received at least one special COVID offer.</span></span>

<span data-ttu-id="bcccc-142">如果您是整合合作夥伴客戶，或是 GCC、GCC High、DoD 或 EDU 客戶，則貴組織不符合使用資格。</span><span class="sxs-lookup"><span data-stu-id="bcccc-142">Your organization isn't eligible for this offer if you're a Syndication Partner Customer or a GCC, GCC High, DoD, or EDU customer.</span></span>

## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a><span data-ttu-id="bcccc-143">使用者註冊 Teams Exploratory 體驗的方式</span><span class="sxs-lookup"><span data-stu-id="bcccc-143">How users sign up for the Teams Exploratory experience</span></span>

<span data-ttu-id="bcccc-144">合格的使用者可以透過登入 Teams 電腦版或網頁版 ([teams.microsoft.com](https://teams.microsoft.com)) 來註冊取得 Teams Exploratory 體驗。</span><span class="sxs-lookup"><span data-stu-id="bcccc-144">Eligible users can sign up for the Teams Exploratory experience by signing in to Teams from the desktop or web ([teams.microsoft.com](https://teams.microsoft.com)).</span></span> <span data-ttu-id="bcccc-145">目前不支援透過行動裝置啟用 Exploratory。</span><span class="sxs-lookup"><span data-stu-id="bcccc-145">At this time, enabling Exploratory through mobile is not supported.</span></span> <span data-ttu-id="bcccc-146">使用者註冊後，系統會自動指派此授權，且租用戶系統管理員在組織中的人員第一次啟動 Teams Exploratory 體驗時，將會收到電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="bcccc-146">When they sign up, they'll be assigned this license automatically and the tenant admin will receive an email notification the first time someone in your org starts the Teams Exploratory experience.</span></span>

## <a name="manage-the-teams-exploratory-experience"></a><span data-ttu-id="bcccc-147">管理 Teams Exploratory 體驗</span><span class="sxs-lookup"><span data-stu-id="bcccc-147">Manage the Teams Exploratory experience</span></span>

<span data-ttu-id="bcccc-148">Teams Exploratory 體驗應由個別使用者起始，而您可能無法代表使用者員工起始此服務。</span><span class="sxs-lookup"><span data-stu-id="bcccc-148">The Teams Exploratory experience is meant to be initiated by individual end users, and you can't initiate this offer on behalf of end-user employees.</span></span>

<span data-ttu-id="bcccc-p105">Teams Exploratory 體驗隨附 Exchange Online 授權，但在系統管理員指派之前，不會指派給使用者。如果使用者沒有 Exchange 授權，且系統管理員尚未指派 Exchange Online 授權，則使用者將無法在 Teams 中排程會議，且可能會遺失其他 Teams 功能。</span><span class="sxs-lookup"><span data-stu-id="bcccc-p105">The Teams Exploratory experience comes with an Exchange Online license, but it won't be assigned to the user until the admin assigns it. If the user doesn't have an Exchange license already, and the admin has yet to assign the Exchange Online license, the user won't be able to schedule meetings in Teams and might be missing other Teams functionality.</span></span>

<span data-ttu-id="bcccc-151">系統管理員可以使用 **試用版應用程式和服務** 切換功能來停用使用者在其組織內執行 Teams Exploratory 體驗。</span><span class="sxs-lookup"><span data-stu-id="bcccc-151">Admins can disable the ability for end users to run the Teams Exploratory experience within their organization by using the **Trial apps and services** switch.</span></span>

### <a name="prevent-users-from-installing-trial-apps-and-services"></a><span data-ttu-id="bcccc-152">防止使用者安裝試用版應用程式和服務</span><span class="sxs-lookup"><span data-stu-id="bcccc-152">Prevent users from installing trial apps and services</span></span>

<span data-ttu-id="bcccc-153">您可以關閉使用者安裝試用版應用程式和服務的功能，即可防止使用者執行 Teams Exploratory 體驗。</span><span class="sxs-lookup"><span data-stu-id="bcccc-153">You can turn off a user's ability to install trial apps and services, which would prevent the user from running the Teams Exploratory experience.</span></span>

1. <span data-ttu-id="bcccc-154">從 [Microsoft 365 系統管理中心]，移至 **[設定]** > **[組織設定]**、選取 **[服務]**，然後選取 **[使用者所擁有的應用程式與服務]**。</span><span class="sxs-lookup"><span data-stu-id="bcccc-154">From the Microsoft 365 admin center, go to **Settings** > **Org settings**, select **Services**, and then select **User owned apps and services**.</span></span>

    ![系統管理中心的 [服務] 頁面](media/iw-trial-services.png)

2. <span data-ttu-id="bcccc-156">取消選取 **[讓使用者安裝試用版的應用程式與服務]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bcccc-156">Clear the check mark from **Let users install trial apps and services**.</span></span>

    ![系統管理中心的 [使用者所擁有的應用程式與服務] 頁面](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > <span data-ttu-id="bcccc-158">如果貴組織不符合 Teams Exploratory 使用資格，您將不會看到 **[讓使用者安裝試用版的應用程式與服務]** 選項。</span><span class="sxs-lookup"><span data-stu-id="bcccc-158">If your organization is ineligible for the Teams Exploratory experience, you won't see the **Let users install trial apps and services** option.</span></span>

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a><span data-ttu-id="bcccc-159">管理具有包含 Teams 授權使用者的可用性</span><span class="sxs-lookup"><span data-stu-id="bcccc-159">Manage availability for a user with a license that includes Teams</span></span>

<span data-ttu-id="bcccc-p106">已獲派含 Teams 授權的使用者不符合 Teams Exploratory 體驗的使用資格。開啟 Teams 服務方案後，使用者就可以登入並使用 Teams。如果服務方案已停用，則使用者無法登入，也無法使用 Teams Exploratory 體驗。您必須具備系統管理員權限。</span><span class="sxs-lookup"><span data-stu-id="bcccc-p106">A user who is assigned a license that includes Teams isn't eligible for the Teams Exploratory experience. When the Teams service plan is turned on, the user can sign in and use Teams. If the service plan is disabled, the user can't sign in and the Teams Exploratory experience isn't available. You must have admin privileges.</span></span>

<span data-ttu-id="bcccc-164">若要關閉對 Teams 的存取：</span><span class="sxs-lookup"><span data-stu-id="bcccc-164">To turn off access to Teams:</span></span>

1. <span data-ttu-id="bcccc-165">在 Microsoft 365 系統管理中心，選取 **[使用者]**  >  **[作用中的使用者]**。</span><span class="sxs-lookup"><span data-stu-id="bcccc-165">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="bcccc-166">選取使用者名稱旁的方塊。</span><span class="sxs-lookup"><span data-stu-id="bcccc-166">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="bcccc-167">在 **[產品授權]** 列中，選擇 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="bcccc-167">In the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="bcccc-168">在 **[產品授權]** 窗格中，將開關切換至 **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="bcccc-168">In the **Product licenses** pane, switch the toggle to **Off**.</span></span>

    ![系統管理中心的 [產品授權] 頁面。](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a><span data-ttu-id="bcccc-170">管理已在使用 Teams Exploratory 體驗之使用者的 Teams 可用性</span><span class="sxs-lookup"><span data-stu-id="bcccc-170">Manage Teams availability for users who are already using the Teams Exploratory experience</span></span>

<span data-ttu-id="bcccc-p107">如果使用者正在執行 Teams Exploratory 體驗，您可以移除授權或服務方案將它關閉。您必須具備系統管理員權限。</span><span class="sxs-lookup"><span data-stu-id="bcccc-p107">If a user is running the Teams Exploratory experience, you can turn it off by removing the license or service plan. You must have admin privileges.</span></span>

<span data-ttu-id="bcccc-173">若要關閉 Teams Exploratory 體驗授權：</span><span class="sxs-lookup"><span data-stu-id="bcccc-173">To turn off the Teams Exploratory experience license:</span></span>

1. <span data-ttu-id="bcccc-174">在 Microsoft 365 系統管理中心，選取 **[使用者]**  >  **[作用中的使用者]**。</span><span class="sxs-lookup"><span data-stu-id="bcccc-174">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="bcccc-175">選取使用者名稱旁的方塊。</span><span class="sxs-lookup"><span data-stu-id="bcccc-175">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="bcccc-176">在 **[產品授權]** 列中，選擇 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="bcccc-176">In the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="bcccc-177">在 **[產品授權]** 窗格中，將此探勘授權的開關切換至 **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="bcccc-177">In the **Product licenses** pane, switch the toggle for this exploratory license to **Off**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bcccc-178">組織中的第一個使用者啟動 Teams Exploratory 體驗之後，將會出現 [Teams Exploratory] 切換開關。</span><span class="sxs-lookup"><span data-stu-id="bcccc-178">The Teams Exploratory toggle switch will appear after the first user in the organization launches the Teams Exploratory experience.</span></span>

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a><span data-ttu-id="bcccc-179">管理適用於擁有 Teams Exploratory 授權之使用者的 Teams</span><span class="sxs-lookup"><span data-stu-id="bcccc-179">Manage Teams for users who have the Teams Exploratory license</span></span>

<span data-ttu-id="bcccc-p108">您可以管理擁有 Teams Exploratory 授權的使用者，就像您管理擁有一般付費授權的使用者一般。如需詳細資訊，請參閱[管理組織的 Teams 設定](enable-features-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="bcccc-p108">You can manage users who have the Teams Exploratory license just like you manage users who have a regular paid license. For more information, see [Manage Teams settings for your organization](enable-features-office-365.md).</span></span>

### <a name="upgrade-users-from-teams-exploratory"></a><span data-ttu-id="bcccc-182">從 Teams Exploratory 升級使用者</span><span class="sxs-lookup"><span data-stu-id="bcccc-182">Upgrade users from Teams Exploratory</span></span>

<span data-ttu-id="bcccc-183">您必須擁有系統管理員權限以從 Teams Exploratory 升級使用者。</span><span class="sxs-lookup"><span data-stu-id="bcccc-183">You must have admin privileges to upgrade users from Teams Exploratory.</span></span> <span data-ttu-id="bcccc-184">如需詳細資訊，請參閱 [從 Teams Exploratory 升級使用者](upgrade-from-teams-exploratory.md)。</span><span class="sxs-lookup"><span data-stu-id="bcccc-184">For more information see [Upgrade users from the Teams Exploratory trial](upgrade-from-teams-exploratory.md).</span></span>

> [!NOTE]
> <span data-ttu-id="bcccc-p110">如果 Teams Exploratory 授權結束且未將使用者立即升級至包含 Teams 的訂閱，則在 30 天寬限期之後失去 Teams 存取權。再經過另一個 30 天之後，其資料會遭到刪除。一旦將新授權指派給使用者以再次啟用 Teams 功能，則如果在寬限期時間範圍內新增使用者，則所有內容仍將存在。</span><span class="sxs-lookup"><span data-stu-id="bcccc-p110">If the Teams Exploratory license ends and a user isn't immediately upgraded to a subscription that includes Teams, they lose access to Teams after a 30-days grace period. Another 30 days after which, the data is deleted. The user still exists in Azure Active Directory. Once a new license is assigned to the user to enable Teams functionality again, all content will still exist if the user is added within the grace period time frame.</span></span>

### <a name="remove-a-teams-exploratory-license"></a><span data-ttu-id="bcccc-189">移除 Teams Exploratory 授權</span><span class="sxs-lookup"><span data-stu-id="bcccc-189">Remove a Teams Exploratory license</span></span>

- <span data-ttu-id="bcccc-190">如果您想要透過 PowerShell 移除此授權，請參閱：[使用 Office 365 PowerShell 從使用者帳戶移除授權](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="bcccc-190">If you would like to remove this license by using PowerShell, see: [Remove licenses from user accounts with Office 365 PowerShell](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span></span>

- <span data-ttu-id="bcccc-191">如果您想要透過系統管理入口網站移除此授權，請參閱：[從貴組織刪除使用者](/microsoft-365/admin/add-users/delete-a-user)</span><span class="sxs-lookup"><span data-stu-id="bcccc-191">If you would like to remove this license through the admin portal, see: [Delete a user from your organization](/microsoft-365/admin/add-users/delete-a-user)</span></span>

## <a name="what-is-the-data-retention-policy"></a><span data-ttu-id="bcccc-192">什麼是資料保留原則</span><span class="sxs-lookup"><span data-stu-id="bcccc-192">What is the data retention policy</span></span>

<span data-ttu-id="bcccc-193">請參閲 [Microsoft 365 訂閱資訊](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="bcccc-193">See [Microsoft 365 subscription information](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).</span></span>

## <a name="how-long-does-the-teams-exploratory-experience-last"></a><span data-ttu-id="bcccc-194">Teams Exploratory 體驗持續時間</span><span class="sxs-lookup"><span data-stu-id="bcccc-194">How long does the Teams Exploratory experience last</span></span>

<span data-ttu-id="bcccc-195">自 2021 年年初起，Teams Exploratory 將以 12 個月訂閱形式 (從使用者初始註冊起) 提供所有新客戶使用。</span><span class="sxs-lookup"><span data-stu-id="bcccc-195">As of early 2021, Teams Exploratory is available as a 12 month subscription (from initial user sign-up) for all new customers.</span></span> <span data-ttu-id="bcccc-196">新的 Teams Exploratory 訂閱會在組織中的第一個使用者註冊 Teams Exploratory 時開始，並且會在 12 個月之後到期。</span><span class="sxs-lookup"><span data-stu-id="bcccc-196">The new Teams Exploratory subscription starts when the first user in an organization signs-up for Teams Exploratory and it will expire after 12 months.</span></span> <span data-ttu-id="bcccc-197">由於 12 個月是從第一位使用者註冊日期開始，到期日將對相同租用戶中的所有使用者套用。</span><span class="sxs-lookup"><span data-stu-id="bcccc-197">The expiry date will apply to all users in the same tenant as the 12-month term begins on the first user's sign-up date.</span></span>

> [!NOTE]
> <span data-ttu-id="bcccc-198">體驗的結束日期在組織層級設定，表示它會套用至相同組織中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="bcccc-198">The end date for the experience is configured at an organization level, meaning it will apply to all users in the same organization.</span></span> <span data-ttu-id="bcccc-199">例如，使用者 1 在 2021 年 1 月 1 日註冊取得訂閱。</span><span class="sxs-lookup"><span data-stu-id="bcccc-199">For example, User 1 signs up for the subscription on January 1, 2021.</span></span> <span data-ttu-id="bcccc-200">這會起始 2021 年 12 月 31 日的訂閱結束日期。</span><span class="sxs-lookup"><span data-stu-id="bcccc-200">This initiates a subscription end-date of December 31, 2021.</span></span> <span data-ttu-id="bcccc-201">另一位使用者，使用者 2 在 2021 年 10 月 1 日註冊取得訂閱。</span><span class="sxs-lookup"><span data-stu-id="bcccc-201">Another user, User 2, signs up for the subscription on October 1, 2021.</span></span> <span data-ttu-id="bcccc-202">使用者 2 可以使用 Teams Exploratory 兩個月，因為其結束日期將為 2021 年 12 月 31 日，因為他們與使用者 1 屬於相同組織的訂閱。</span><span class="sxs-lookup"><span data-stu-id="bcccc-202">User 2 can use Teams Exploratory for two months, as their end-date will be December 31, 2021 because they're under the same organization's subscription as User 1.</span></span>

### <a name="what-should-administrators-do-at-the-end-of-the-12-month-teams-exploratory-experience"></a><span data-ttu-id="bcccc-203">在 12 個月的 Teams Exploratory 體驗結束時，系統管理員應該執行什麼動作</span><span class="sxs-lookup"><span data-stu-id="bcccc-203">What should administrators do at the end of the 12 month Teams Exploratory experience</span></span>

<span data-ttu-id="bcccc-204">在 12 個月訂閱結束時，系統管理員應將所有 Teams Exploratory 使用者轉換成包括 Teams 在內的付費授權。</span><span class="sxs-lookup"><span data-stu-id="bcccc-204">At the end of the 12 month subscription, administrators should convert all Teams Exploratory users to a paid license that includes Teams.</span></span> <span data-ttu-id="bcccc-205">確保在 Teams Exploratory 訂閱到期之前完成此工作是非常重要的，以避免對使用者的體驗造成中斷。</span><span class="sxs-lookup"><span data-stu-id="bcccc-205">It is vital to ensure this is completed before the Teams Exploratory subscription expires to avoid any disruption to user's experience.</span></span>


> [!NOTE]
> <span data-ttu-id="bcccc-206">在前一個 Exploratory 體驗授權到期後的 3 個月內客戶將被停用並封鎖開始新 Explaratory 授權。</span><span class="sxs-lookup"><span data-stu-id="bcccc-206">Customers will be disabled and blocked from starting a new Exploratory trial licenses for 3 months past the expiration of their previous Exploratory trial license.</span></span>

<span data-ttu-id="bcccc-207">如需詳細資訊，請參閱本文上方的 [從 Teams Exploratory 升級使用者](#upgrade-users-from-teams-exploratory)。</span><span class="sxs-lookup"><span data-stu-id="bcccc-207">For more information, see [Upgrade users from Teams Exploratory](#upgrade-users-from-teams-exploratory), above in this article.</span></span>
