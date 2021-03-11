---
title: 在 Microsoft Teams 中管理應用程式設定政策
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: rarang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在 Microsoft Teams 中為貴組織的使用者使用及管理應用程式設定政策。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: a58cbf682760249ee3b269d1765a265cc58d3022
ms.sourcegitcommit: 31a585cc0fe6350efacf3a7771d1e590d5e4233c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/10/2021
ms.locfileid: "50615089"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="c96f8-103">在 Microsoft Teams 中管理應用程式設定政策</span><span class="sxs-lookup"><span data-stu-id="c96f8-103">Manage app setup policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="c96f8-104">如果您已啟用整個組織的應用程式設定，允許與自訂應用程式互動，您可能尚未在 Microsoft Teams 系統管理中心看到應用程式設定政策。</span><span class="sxs-lookup"><span data-stu-id="c96f8-104">If you enabled the org-wide app setting, **Allow interaction with custom apps**, you might not see app setup policies yet in the Microsoft Teams admin center.</span></span> <span data-ttu-id="c96f8-105">目前正在推出，並即將在貴組織中推出。</span><span class="sxs-lookup"><span data-stu-id="c96f8-105">It's currently being rolled out and will be available soon in your organization.</span></span>

<span data-ttu-id="c96f8-106">系統管理員可以使用應用程式設定策略執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="c96f8-106">As an admin, you can use app setup policies to do the following tasks:</span></span>

- <span data-ttu-id="c96f8-107">自訂 Teams 以強調對使用者而言最重要的應用程式。</span><span class="sxs-lookup"><span data-stu-id="c96f8-107">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="c96f8-108">您可以選擇要釘選的應用程式，並設定其顯示順序。</span><span class="sxs-lookup"><span data-stu-id="c96f8-108">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="c96f8-109">釘上應用程式可讓您展示貴組織使用者所需的應用程式，包括由協力廠商或貴組織開發人員所建立的應用程式。</span><span class="sxs-lookup"><span data-stu-id="c96f8-109">Pinning apps lets you showcase apps that users in your organization need, including apps built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="c96f8-110">控制使用者是否可以將應用程式釘選到 Teams。</span><span class="sxs-lookup"><span data-stu-id="c96f8-110">Control whether users can pin apps to Teams.</span></span>
- <span data-ttu-id="c96f8-111">代表使用者安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="c96f8-111">Install apps on behalf of users.</span></span> <span data-ttu-id="c96f8-112">您可以選擇使用者啟動 Teams 時預設要安裝哪些應用程式。</span><span class="sxs-lookup"><span data-stu-id="c96f8-112">You choose which apps are installed by default for users when they start Teams.</span></span> <span data-ttu-id="c96f8-113">請記住，如果指派給他們的應用程式許可權政策允許，使用者仍然可以[](teams-app-permission-policies.md)自行安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="c96f8-113">Keep in mind that users can still install apps themselves if the [app permission policy](teams-app-permission-policies.md) that's assigned to them allows it.</span></span>

> [!Note]
> <span data-ttu-id="c96f8-114">對於系統管理員安裝的應用程式，使用者無法卸載這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="c96f8-114">For apps installed by admins, users can't uninstall those apps.</span></span>

<span data-ttu-id="c96f8-115">應用程式會釘到應用程式行，即 Teams 桌面用戶端側邊以及 Teams 行動用戶端 (iOS 和 Android) 底部的) 。</span><span class="sxs-lookup"><span data-stu-id="c96f8-115">Apps are pinned to the app bar, which is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="c96f8-116">Teams 桌面用戶端</span><span class="sxs-lookup"><span data-stu-id="c96f8-116">Teams desktop client</span></span>  |<span data-ttu-id="c96f8-117">Teams 行動用戶端</span><span class="sxs-lookup"><span data-stu-id="c96f8-117">Teams mobile client</span></span> |
|---------|---------|
|![Teams 桌面用戶端](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Teams 行動用戶端](media/mobile-app-ui.png)      |

<span data-ttu-id="c96f8-120">若要查看系統管理員安裝的應用程式，請在應用程式欄中，使用者選取 **...Teams 電腦** 版和 Web 用戶端中的更多應用程式，在行動用戶端中向上滑動。</span><span class="sxs-lookup"><span data-stu-id="c96f8-120">To see the apps installed by admins, in the app bar, users select **... More apps** in the Teams desktop and web clients and swipe up in the mobile clients.</span></span>

<span data-ttu-id="c96f8-121">您可以在 Microsoft Teams 系統管理中心管理應用程式設定政策。</span><span class="sxs-lookup"><span data-stu-id="c96f8-121">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="c96f8-122">使用全域 (整個組織的預設) 或建立及指派自訂策略。</span><span class="sxs-lookup"><span data-stu-id="c96f8-122">Use the global (Org-wide default) policy or create and assign custom policies.</span></span>  <span data-ttu-id="c96f8-123">除非您建立並指派自訂原則，否則組織中的使用者將會自動取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="c96f8-123">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="c96f8-124">您必須是全域系統管理員或 Teams 服務系統管理員，才能管理這些原則。</span><span class="sxs-lookup"><span data-stu-id="c96f8-124">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="c96f8-125">您可以編輯全域原則中的設定，以包含您想要的應用程式。</span><span class="sxs-lookup"><span data-stu-id="c96f8-125">You edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="c96f8-126">若要為貴組織的不同使用者群組自訂 Teams，請建立並指派一或多個自訂策略。</span><span class="sxs-lookup"><span data-stu-id="c96f8-126">To customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

![應用程式設定政策頁面](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="c96f8-128">如果您有 Teams 教育課程，請注意，全域原則中預設會釘上作業應用程式，即使目前未在全域原則中顯示。</span><span class="sxs-lookup"><span data-stu-id="c96f8-128">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="c96f8-129">它將是 Teams 用戶端上釘定應用程式清單中的第四個應用程式。</span><span class="sxs-lookup"><span data-stu-id="c96f8-129">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="c96f8-130">建立自訂應用程式設定政策</span><span class="sxs-lookup"><span data-stu-id="c96f8-130">Create a custom app setup policy</span></span>

<span data-ttu-id="c96f8-131">您可以使用 Microsoft Teams 系統管理中心建立自訂策略。</span><span class="sxs-lookup"><span data-stu-id="c96f8-131">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="c96f8-132">在 Microsoft Teams 系統管理中心的左側流覽中，前往 **Teams 應用程式**  >  **設定政策**。</span><span class="sxs-lookup"><span data-stu-id="c96f8-132">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="c96f8-133">選取 [新增 **]**。</span><span class="sxs-lookup"><span data-stu-id="c96f8-133">Select **Add**.</span></span>

   ![新增應用程式設定政策頁面](media/app-setup-policies-add.png)

3. <span data-ttu-id="c96f8-135">輸入原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="c96f8-135">Enter a name and description for the policy.</span></span>

4. <span data-ttu-id="c96f8-136">視您是否 **要讓使用者將** 自訂應用程式上傳至 Teams，開啟或關閉上傳自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="c96f8-136">Turn on or turn off **Upload custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span> <span data-ttu-id="c96f8-137">如果全組織 App 設定中已關閉允許協力廠商應用程式，您即[無法變更此設定](manage-apps.md#manage-org-wide-app-settings)。</span><span class="sxs-lookup"><span data-stu-id="c96f8-137">You can't change this setting if **Allow third-party apps** is turned off in [org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>

5. <span data-ttu-id="c96f8-138">視您是否要讓使用者將應用程式 **釘** 上以個人化其應用程式行，請開啟或關閉允許使用者釘釘。</span><span class="sxs-lookup"><span data-stu-id="c96f8-138">Turn on or turn off **Allow user pinning**, depending on whether you want to let users personalize their app bar by pinning apps to it.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c96f8-139">Microsoft  365 政府社群雲端 (GCC) 環境 (GCC、GCC High 和 DoD) 中的 Teams 系統管理中心提供允許使用者釘釘設定，但目前沒有作用。</span><span class="sxs-lookup"><span data-stu-id="c96f8-139">The **Allow user pinning** setting is available in the Teams admin center in Microsoft 365 Government Community Cloud (GCC) environments (GCC, GCC High and DoD), but currently it has no effect.</span></span>

6. <span data-ttu-id="c96f8-140">若要為使用者安裝應用程式，請執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="c96f8-140">To install apps for users, do the following tasks:</span></span>

    1. <span data-ttu-id="c96f8-141">在 **已安裝的應用程式下**，選取 **新增應用程式**。</span><span class="sxs-lookup"><span data-stu-id="c96f8-141">Under **Installed apps**, select **Add apps**.</span></span>

    2. <span data-ttu-id="c96f8-142">在新增 **已安裝的應用程式窗格中** ，搜尋您想要在使用者啟動 Teams 時自動安裝的應用程式。</span><span class="sxs-lookup"><span data-stu-id="c96f8-142">In the **Add installed apps** pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="c96f8-143">您也可以根據應用程式權限原則來篩選應用程式。</span><span class="sxs-lookup"><span data-stu-id="c96f8-143">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="c96f8-144">當您選擇您的應用程式清單時， **請選取新增**。</span><span class="sxs-lookup"><span data-stu-id="c96f8-144">When you've chosen your list of apps, select **Add**.</span></span>

       ![新增已安裝的應用程式窗格](media/app-setup-policies-add-installed-apps.png)

7. <span data-ttu-id="c96f8-146">若要釘上應用程式，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="c96f8-146">To pin apps, do the following steps:</span></span>

    1. <span data-ttu-id="c96f8-147">在 **釘選的應用程式下**，選取新增 **應用程式**。</span><span class="sxs-lookup"><span data-stu-id="c96f8-147">Under **Pinned apps**, select **Add apps**.</span></span>

    2. <span data-ttu-id="c96f8-148">在新增釘 **選的應用程式窗格中** ，搜尋您想要新增的應用程式， **然後選取新增**。</span><span class="sxs-lookup"><span data-stu-id="c96f8-148">In the **Add pinned apps** pane, search for the apps you want to add, and then select **Add**.</span></span> <span data-ttu-id="c96f8-149">您也可以根據應用程式權限原則來篩選應用程式。</span><span class="sxs-lookup"><span data-stu-id="c96f8-149">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="c96f8-150">當您選擇要釘選的應用程式清單時， **請選取新增**。</span><span class="sxs-lookup"><span data-stu-id="c96f8-150">When you've chosen your list of apps to pin, select **Add**.</span></span>

       ![新增釘上的應用程式窗格](media/app-setup-policies-add-apps.png)

    3. <span data-ttu-id="c96f8-152">以您想要在 Teams 中顯示的順序排列應用程式， **然後選取儲存**。</span><span class="sxs-lookup"><span data-stu-id="c96f8-152">Arrange the apps in the order that you want them to appear in Teams, and then select **Save**.</span></span>

       ![釘上的應用程式區段](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="c96f8-154">編輯應用程式設定政策</span><span class="sxs-lookup"><span data-stu-id="c96f8-154">Edit an app setup policy</span></span>

<span data-ttu-id="c96f8-155">您可以使用 Microsoft Teams 系統管理中心編輯政策，包括 (全組織的預設) 和您建立自訂政策。</span><span class="sxs-lookup"><span data-stu-id="c96f8-155">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="c96f8-156">在 Microsoft Teams 系統管理中心的左側流覽中，前往 **Teams 應用程式**  >  **設定政策**。</span><span class="sxs-lookup"><span data-stu-id="c96f8-156">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="c96f8-157">按一下政策名稱的左側以選取該政策， **然後選取編輯**。</span><span class="sxs-lookup"><span data-stu-id="c96f8-157">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>

3. <span data-ttu-id="c96f8-158">從此處，進行您需要的變更。</span><span class="sxs-lookup"><span data-stu-id="c96f8-158">From here, make the changes that you want.</span></span>

4. <span data-ttu-id="c96f8-159">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="c96f8-159">Select **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="c96f8-160">指派自訂應用程式設定政策給使用者</span><span class="sxs-lookup"><span data-stu-id="c96f8-160">Assign a custom app setup policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a><span data-ttu-id="c96f8-161">常見問題集</span><span class="sxs-lookup"><span data-stu-id="c96f8-161">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="c96f8-162">使用應用程式設定政策</span><span class="sxs-lookup"><span data-stu-id="c96f8-162">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="c96f8-163">Microsoft Teams 系統管理中心包含哪些內建應用程式設定政策</span><span class="sxs-lookup"><span data-stu-id="c96f8-163">What built-in app setup policies are included in the Microsoft Teams admin center</span></span>

- <span data-ttu-id="c96f8-164">**全域 (全組織預設) ：** 除非您指派其他原則，否則此預設原則會適用于貴組織中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="c96f8-164">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="c96f8-165">編輯全域原則以釘上對使用者最重要的應用程式。</span><span class="sxs-lookup"><span data-stu-id="c96f8-165">Edit the global policy to pin apps that are most important for your users.</span></span>

- <span data-ttu-id="c96f8-166">**FrontlineWorker：** 此政策適用于前線工作人員。</span><span class="sxs-lookup"><span data-stu-id="c96f8-166">**FrontlineWorker**: This policy is for Frontline Workers.</span></span> <span data-ttu-id="c96f8-167">您可以將它指派給貴組織的前線工作人員。</span><span class="sxs-lookup"><span data-stu-id="c96f8-167">You can assign it to Frontline Workers in your organization.</span></span> <span data-ttu-id="c96f8-168">請注意，您必須像您建立自訂策略一樣，將設定指派給使用者，設定為使用中。</span><span class="sxs-lookup"><span data-stu-id="c96f8-168">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="c96f8-169">詳細資訊，請前往本文的指派自訂 [應用程式設定政策給使用者](#assign-a-custom-app-setup-policy-to-users) 一節。</span><span class="sxs-lookup"><span data-stu-id="c96f8-169">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="c96f8-170">為什麼我在新增釘寄的應用程式窗格中找不到應用程式</span><span class="sxs-lookup"><span data-stu-id="c96f8-170">Why can't I find an app in the Add pinned apps pane</span></span>

<span data-ttu-id="c96f8-171">並非所有應用程式都可以透過應用程式設定政策釘釘到 Teams。</span><span class="sxs-lookup"><span data-stu-id="c96f8-171">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="c96f8-172">某些應用程式可能不支援此功能。</span><span class="sxs-lookup"><span data-stu-id="c96f8-172">Some apps may not support this functionality.</span></span> <span data-ttu-id="c96f8-173">若要尋找可釘上的應用程式，請搜尋在新增釘上 App **窗格中的應用程式** 。</span><span class="sxs-lookup"><span data-stu-id="c96f8-173">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="c96f8-174">具有個人範圍的定位點 (靜態) 和 Bot 可以釘釘到 Teams 桌面用戶端，這些應用程式可在新增釘上的應用程式 **窗格中** 使用。</span><span class="sxs-lookup"><span data-stu-id="c96f8-174">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="c96f8-175">請記住，Teams App Store 會列出所有 Teams 應用程式。</span><span class="sxs-lookup"><span data-stu-id="c96f8-175">Keep in mind that the Teams app store lists all Teams apps.</span></span> <span data-ttu-id="c96f8-176">新增 **釘上的應用程式窗格** 僅包含可透過策略釘寄到 Teams 的應用程式。</span><span class="sxs-lookup"><span data-stu-id="c96f8-176">The **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span>

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="c96f8-177">我是 Teams 教育用系統管理員。關於 Teams 教育用 App 設定政策，我需要知道哪些資訊</span><span class="sxs-lookup"><span data-stu-id="c96f8-177">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education</span></span>

<span data-ttu-id="c96f8-178">Teams 教育用中無法使用通話應用程式。</span><span class="sxs-lookup"><span data-stu-id="c96f8-178">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="c96f8-179">當您建立新的自訂應用程式設定政策時，通話應用程式會顯示在應用程式清單中。</span><span class="sxs-lookup"><span data-stu-id="c96f8-179">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="c96f8-180">不過，應用程式未釘釘到 Teams 用戶端，而 Teams 教育用使用者不會在 Teams 中看到通話應用程式。</span><span class="sxs-lookup"><span data-stu-id="c96f8-180">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span>

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a><span data-ttu-id="c96f8-181">可新增多少個釘點應用程式至策略</span><span class="sxs-lookup"><span data-stu-id="c96f8-181">How many pinned apps can be added to a policy</span></span>

<span data-ttu-id="c96f8-182">iOS 和 Android (中，至少必須釘) 。</span><span class="sxs-lookup"><span data-stu-id="c96f8-182">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="c96f8-183">如果一個策略少於兩個 App，行動用戶端不會反映該策略設定，而是繼續使用現有的設定。</span><span class="sxs-lookup"><span data-stu-id="c96f8-183">If a policy has fewer than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

<span data-ttu-id="c96f8-184">您可以新增到策略的釘上 App 數量沒有限制。</span><span class="sxs-lookup"><span data-stu-id="c96f8-184">There's no limit on the number of pinned apps you can add to a policy.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="c96f8-185">政策變更生效需要多久時間？</span><span class="sxs-lookup"><span data-stu-id="c96f8-185">How long does it take for policy changes to take effect</span></span>

<span data-ttu-id="c96f8-186">編輯或指派原則之後，變更可能需要幾個小時的時間才會生效。</span><span class="sxs-lookup"><span data-stu-id="c96f8-186">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="c96f8-187">使用者體驗</span><span class="sxs-lookup"><span data-stu-id="c96f8-187">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="c96f8-188">使用者如何在 Teams 中查看所有釘寄的應用程式</span><span class="sxs-lookup"><span data-stu-id="c96f8-188">How can users see all their pinned apps in Teams</span></span>

<span data-ttu-id="c96f8-189">若要查看已釘寄給使用者的所有應用程式，使用者可能必須執行下列操作，視已安裝的應用程式數量及其 Teams 用戶端視窗的大小。</span><span class="sxs-lookup"><span data-stu-id="c96f8-189">To view all apps that are pinned for a user, users might have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="c96f8-190">Teams 桌面用戶端</span><span class="sxs-lookup"><span data-stu-id="c96f8-190">Teams desktop client</span></span> |<span data-ttu-id="c96f8-191">Teams 行動用戶端</span><span class="sxs-lookup"><span data-stu-id="c96f8-191">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="c96f8-192">在 Teams 側邊的應用程式欄中，選取 **...更多應用程式**。</span><span class="sxs-lookup"><span data-stu-id="c96f8-192">In the app bar on the side of Teams, select **... More apps**.</span></span>| <span data-ttu-id="c96f8-193">在 Teams 底部附近的應用程式行中，向上滑動。</span><span class="sxs-lookup"><span data-stu-id="c96f8-193">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![Teams 桌面用戶端中的更多應用程式](media/app-setup-policies-desktop-more-apps.png)<br>   |![Teams 行動用戶端中的更多應用程式](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="c96f8-196">關於 Teams 行動體驗，我需要知道哪些資訊</span><span class="sxs-lookup"><span data-stu-id="c96f8-196">What do I need to know about the Teams mobile experience</span></span>

<span data-ttu-id="c96f8-197">iOS (Android) Teams 行動用戶端目前不支援使用靜態選項卡的個人 App。</span><span class="sxs-lookup"><span data-stu-id="c96f8-197">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="c96f8-198">根據政策中設定的應用程式，釘寄到 Teams 桌面用戶端的應用程式可能不會顯示在 Teams 行動用戶端中。</span><span class="sxs-lookup"><span data-stu-id="c96f8-198">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="c96f8-199">個人 Bot 仍然會出現在行動用戶端上的聊天中。</span><span class="sxs-lookup"><span data-stu-id="c96f8-199">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="c96f8-200">有了 Teams 行動用戶端，使用者會看到核心的 Teams 應用程式，例如活動、聊天和 Teams，而且您可以釘上 Microsoft 的一些第一方應用程式，例如 Shifts。</span><span class="sxs-lookup"><span data-stu-id="c96f8-200">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="c96f8-201">使用者可以變更透過政策釘寄的應用程式順序嗎？</span><span class="sxs-lookup"><span data-stu-id="c96f8-201">Can users change the order of apps pinned through a policy</span></span>

<span data-ttu-id="c96f8-202">如果開啟了允許使用者釘選選項，使用者就可以在 Teams 桌面及行動用戶端上變更釘選應用程式的順序。</span><span class="sxs-lookup"><span data-stu-id="c96f8-202">Users can change the order of their pinned apps on Teams desktop and mobile clients if the **Allow user pinning** option is turned on.</span></span> <span data-ttu-id="c96f8-203">使用者無法變更在 Teams Web 用戶端上釘上 App 的順序。</span><span class="sxs-lookup"><span data-stu-id="c96f8-203">Users can't change the order of their pinned apps on Teams web clients.</span></span>

#### <a name="does-user-pinning-take-precedence"></a><span data-ttu-id="c96f8-204">使用者釘取是否優先</span><span class="sxs-lookup"><span data-stu-id="c96f8-204">Does user pinning take precedence</span></span>

<span data-ttu-id="c96f8-205">如果指派給使用者的應用程式設定政策已變更為封鎖使用者 App 釘釘，Teams 會移除釘上至應用程式欄的任何應用程式。</span><span class="sxs-lookup"><span data-stu-id="c96f8-205">If the app setup policy assigned to the user is changed to block user app pinning, Teams removes any apps pinned to the app bar.</span></span> <span data-ttu-id="c96f8-206">如果系統變更此政策以允許使用者釘上應用程式，使用者必須重新釘上先前釘上的應用程式。</span><span class="sxs-lookup"><span data-stu-id="c96f8-206">If the policy is then changed to allow user app pinning, users must repin their previously pinned apps.</span></span>

### <a name="custom-teams-apps"></a><span data-ttu-id="c96f8-207">自訂 Teams 應用程式</span><span class="sxs-lookup"><span data-stu-id="c96f8-207">Custom Teams apps</span></span>

<span data-ttu-id="c96f8-208">我的組織已建立自訂的 Teams 應用程式，併發布到 AppSource 或租使用者應用程式目錄，但是當應用程式釘到 Teams 中的應用程式行時，應用程式圖示不會如預期顯示。</span><span class="sxs-lookup"><span data-stu-id="c96f8-208">My organization built a custom Teams app and published it, either to AppSource or the tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="c96f8-209">如何修正此問題</span><span class="sxs-lookup"><span data-stu-id="c96f8-209">How do I fix it</span></span>

<span data-ttu-id="c96f8-210">提交應用程式之前，請務必遵循標誌指導方針。</span><span class="sxs-lookup"><span data-stu-id="c96f8-210">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="c96f8-211">若要深入瞭解，請參閱銷售 [者儀表板提交檢查清單](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)。</span><span class="sxs-lookup"><span data-stu-id="c96f8-211">To learn more, see [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c96f8-212">相關主題</span><span class="sxs-lookup"><span data-stu-id="c96f8-212">Related topics</span></span>

[<span data-ttu-id="c96f8-213">在 Teams 中管理應用程式的設定</span><span class="sxs-lookup"><span data-stu-id="c96f8-213">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="c96f8-214">在 Teams 中將原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="c96f8-214">Assign policies to your users in Teams</span></span>](assign-policies.md)
