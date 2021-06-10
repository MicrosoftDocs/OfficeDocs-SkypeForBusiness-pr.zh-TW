---
title: 管理應用程式中的應用程式設定Microsoft Teams
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
description: 瞭解如何在組織中Microsoft Teams應用程式設定策略。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: ebfcff8ce7215e34e3c17e9c09f3a56d249d5b40
ms.sourcegitcommit: 1ee9b1857f472a5b95352f7471c0cf21be6ea0c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2021
ms.locfileid: "52059197"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="1f8ba-103">管理應用程式中的應用程式設定Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1f8ba-103">Manage app setup policies in Microsoft Teams</span></span>

<span data-ttu-id="1f8ba-104">做為系統管理員，您可以使用應用程式設定策略執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="1f8ba-104">As an admin, you can use app setup policies to do the following tasks:</span></span>

- <span data-ttu-id="1f8ba-105">自訂 Teams 以強調對使用者而言最重要的應用程式。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-105">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="1f8ba-106">您可以選擇要釘選的應用程式，並設定其顯示順序。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-106">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="1f8ba-107">釘上應用程式可讓您展示貴組織中使用者所需的應用程式，包括由協力廠商或貴組織的開發人員所建立的應用程式。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-107">Pinning apps lets you showcase apps that users in your organization need, including apps built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="1f8ba-108">控制使用者是否可以將應用程式釘選到 Teams。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-108">Control whether users can pin apps to Teams.</span></span>
- <span data-ttu-id="1f8ba-109">代表使用者安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-109">Install apps on behalf of users.</span></span> <span data-ttu-id="1f8ba-110">您可以選擇使用者啟動應用程式時，預設會安裝Teams。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-110">You choose which apps are installed by default for users when they start Teams.</span></span> <span data-ttu-id="1f8ba-111">請記住，如果指派給使用者的應用程式許可權政策允許，使用者仍可[](teams-app-permission-policies.md)自行安裝 App。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-111">Keep in mind that users can still install apps themselves if the [app permission policy](teams-app-permission-policies.md) that's assigned to them allows it.</span></span>

> [!Note]
> <span data-ttu-id="1f8ba-112">對於系統管理員安裝的 App，使用者無法卸載這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-112">For apps installed by admins, users can't uninstall those apps.</span></span>

<span data-ttu-id="1f8ba-113">應用程式會釘到應用程式欄，即 Teams 桌面用戶端側邊以及 Teams 行動用戶端 (iOS 和 Android) 。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-113">Apps are pinned to the app bar, which is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="1f8ba-114">Teams桌面用戶端</span><span class="sxs-lookup"><span data-stu-id="1f8ba-114">Teams desktop client</span></span>  |<span data-ttu-id="1f8ba-115">Teams 行動用戶端</span><span class="sxs-lookup"><span data-stu-id="1f8ba-115">Teams mobile client</span></span> |
|---------|---------|
|![桌面Teams用戶端](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![手機Teams用戶端](media/mobile-app-ui.png)      |

<span data-ttu-id="1f8ba-118">若要查看系統管理員安裝的應用程式，請在應用程式欄中選取 **...在桌面** 和 web 用戶端Teams更多應用程式，然後向上滑動到行動用戶端。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-118">To see the apps installed by admins, in the app bar, users select **... More apps** in the Teams desktop and web clients and swipe up in the mobile clients.</span></span>

<span data-ttu-id="1f8ba-119">您可以在系統管理中心管理Microsoft Teams設定政策。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-119">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="1f8ba-120">使用全域 (整個組織的預設) ，或建立及指派自訂策略。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-120">Use the global (Org-wide default) policy or create and assign custom policies.</span></span>  <span data-ttu-id="1f8ba-121">除非您建立並指派自訂原則，否則組織中的使用者將會自動取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-121">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="1f8ba-122">您必須是全域系統管理員或 Teams 服務系統管理員，才能管理這些原則。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-122">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="1f8ba-123">您可以編輯全域原則中的設定，以包含您想要的應用程式。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-123">You edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="1f8ba-124">若要自訂Teams組織中不同使用者群組的使用者，請建立並指派一或多個自訂策略。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-124">To customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

![應用程式設定政策頁面](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="1f8ba-126">如果您有Teams，您必須知道全域原則中的作業應用程式預設為釘點，即使目前未在全域原則中列出。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-126">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="1f8ba-127">它會是用戶端上釘上應用程式清單中的第四Teams App。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-127">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="1f8ba-128">建立自訂應用程式設定策略</span><span class="sxs-lookup"><span data-stu-id="1f8ba-128">Create a custom app setup policy</span></span>

<span data-ttu-id="1f8ba-129">您可以使用系統管理Microsoft Teams建立自訂策略。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-129">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="1f8ba-130">在系統管理中心的左側導Microsoft Teams，請前往 Teams **設定**  >  **政策**。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-130">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="1f8ba-131">選取 [新增 **]**。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-131">Select **Add**.</span></span>

   ![新增應用程式設定政策頁面](media/app-setup-policies-add.png)

3. <span data-ttu-id="1f8ba-133">輸入原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-133">Enter a name and description for the policy.</span></span>

4. <span data-ttu-id="1f8ba-134">視您是否要讓使用者上傳 **自訂** Upload，開啟或關閉自訂應用程式Teams。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-134">Turn on or turn off **Upload custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span> <span data-ttu-id="1f8ba-135">如果全組織 App 設定中已關閉 **允許第** 三方應用程式， [則無法變更此設定](manage-apps.md#manage-org-wide-app-settings)。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-135">You can't change this setting if **Allow third-party apps** is turned off in [org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>

5. <span data-ttu-id="1f8ba-136">開啟或關閉 **允許使用者釘點**，取決於您是否要讓使用者將應用程式釘到 App 欄來個人化其 App 欄。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-136">Turn on or turn off **Allow user pinning**, depending on whether you want to let users personalize their app bar by pinning apps to it.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1f8ba-137">**Microsoft 365 政府社群雲端 (GCC) 、 (GCC** GCC高和 DoD Teams系統管理中心提供允許使用者釘) 設定，但目前沒有作用。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-137">The **Allow user pinning** setting is available in the Teams admin center in Microsoft 365 Government Community Cloud (GCC) environments (GCC, GCC High and DoD), but currently it has no effect.</span></span>

6. <span data-ttu-id="1f8ba-138">若要為使用者安裝應用程式，請執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="1f8ba-138">To install apps for users, do the following tasks:</span></span>

    1. <span data-ttu-id="1f8ba-139">在 **安裝的應用程式下**，選取 新增 **應用程式**。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-139">Under **Installed apps**, select **Add apps**.</span></span>

    2. <span data-ttu-id="1f8ba-140">在新增 **已安裝的應用程式窗格中**，搜尋使用者啟動應用程式時要自動安裝Teams。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-140">In the **Add installed apps** pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="1f8ba-141">您也可以根據應用程式權限原則篩選應用程式。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-141">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="1f8ba-142">當您選擇您的應用程式清單時，請選取 **新增**。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-142">When you've chosen your list of apps, select **Add**.</span></span>

       ![新增已安裝的應用程式窗格](media/app-setup-policies-add-installed-apps.png)

7. <span data-ttu-id="1f8ba-144">若要釘上應用程式，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="1f8ba-144">To pin apps, do the following steps:</span></span>

    1. <span data-ttu-id="1f8ba-145">在 **已釘選的 App** 下，選取 新增 **應用程式**。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-145">Under **Pinned apps**, select **Add apps**.</span></span>

    2. <span data-ttu-id="1f8ba-146">在新增 **釘選的應用程式窗格中** ，搜尋您想要新增的應用程式，然後選取 **新增**。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-146">In the **Add pinned apps** pane, search for the apps you want to add, and then select **Add**.</span></span> <span data-ttu-id="1f8ba-147">您也可以根據應用程式權限原則篩選應用程式。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-147">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="1f8ba-148">當您選擇要釘選的應用程式清單時， **請選取** 新增 。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-148">When you've chosen your list of apps to pin, select **Add**.</span></span>

       ![新增釘上應用程式窗格](media/app-setup-policies-add-apps.png)

    3. <span data-ttu-id="1f8ba-150">以您希望 App 在應用程式中顯示的順序排列Teams，然後選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-150">Arrange the apps in the order that you want them to appear in Teams, and then select **Save**.</span></span>

       ![釘上應用程式區段](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="1f8ba-152">編輯應用程式設定策略</span><span class="sxs-lookup"><span data-stu-id="1f8ba-152">Edit an app setup policy</span></span>

<span data-ttu-id="1f8ba-153">您可以使用系統管理Microsoft Teams編輯策略，包括您 (全組織的預設) 策略和自訂策略。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-153">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="1f8ba-154">在系統管理中心的左側導Microsoft Teams，請前往 Teams **設定**  >  **政策**。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-154">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="1f8ba-155">按一下原則名稱左側來選取原則，然後選取 [編輯 **]**。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-155">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>

3. <span data-ttu-id="1f8ba-156">從此處，進行您需要的變更。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-156">From here, make the changes that you want.</span></span>

4. <span data-ttu-id="1f8ba-157">選取 [儲存 **]**。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-157">Select **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="1f8ba-158">指派自訂應用程式設定策略給使用者</span><span class="sxs-lookup"><span data-stu-id="1f8ba-158">Assign a custom app setup policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a><span data-ttu-id="1f8ba-159">常見問題集</span><span class="sxs-lookup"><span data-stu-id="1f8ba-159">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="1f8ba-160">使用應用程式設定策略</span><span class="sxs-lookup"><span data-stu-id="1f8ba-160">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="1f8ba-161">系統管理中心內建的應用程式設定Microsoft Teams政策</span><span class="sxs-lookup"><span data-stu-id="1f8ba-161">What built-in app setup policies are included in the Microsoft Teams admin center</span></span>

- <span data-ttu-id="1f8ba-162">**全域 (全組織的預設) ：** 除非您指派其他原則，否則此預設原則會適用于貴組織中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-162">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="1f8ba-163">編輯全域原則以釘上使用者最重要的應用程式。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-163">Edit the global policy to pin apps that are most important for your users.</span></span>

- <span data-ttu-id="1f8ba-164">**FrontlineWorker：** 此政策適用于前線員工。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-164">**FrontlineWorker**: This policy is for Frontline Workers.</span></span> <span data-ttu-id="1f8ba-165">您可以將它指派給貴組織的前線工作人員。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-165">You can assign it to Frontline Workers in your organization.</span></span> <span data-ttu-id="1f8ba-166">您必須知道，就像您建立自訂策略一樣，您必須將策略指派給使用者，讓設定保持有效。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-166">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="1f8ba-167">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span><span class="sxs-lookup"><span data-stu-id="1f8ba-167">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="1f8ba-168">為什麼我在新增釘上的應用程式窗格中找不到應用程式</span><span class="sxs-lookup"><span data-stu-id="1f8ba-168">Why can't I find an app in the Add pinned apps pane</span></span>

<span data-ttu-id="1f8ba-169">並非所有應用程式都可以透過應用程式設定Teams釘釘至其他應用程式。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-169">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="1f8ba-170">某些應用程式可能不支援此功能。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-170">Some apps may not support this functionality.</span></span> <span data-ttu-id="1f8ba-171">若要尋找可釘上的應用程式，請搜尋在新增釘上 App 窗格中 **的應用程式** 。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-171">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="1f8ba-172">具有個人範圍 (靜態) 和 bot 的定位點可以釘釘到 Teams 桌面用戶端，這些應用程式可在新增釘上的應用程式窗格中 **使用**。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-172">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="1f8ba-173">請記住，應用程式Teams會列出所有Teams應用程式。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-173">Keep in mind that the Teams app store lists all Teams apps.</span></span> <span data-ttu-id="1f8ba-174">新增 **釘上應用程式窗格** 僅包含可透過Teams釘釘至應用程式。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-174">The **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span>

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="1f8ba-175">我是教育Teams管理員。我需要知道教育用應用程式中的應用程式設定Teams政策</span><span class="sxs-lookup"><span data-stu-id="1f8ba-175">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education</span></span>

<span data-ttu-id="1f8ba-176">教育用應用程式無法Teams通話應用程式。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-176">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="1f8ba-177">當您建立新的自訂應用程式設定策略時，通話應用程式會顯示在應用程式清單中。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-177">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="1f8ba-178">不過，應用程式不會釘Teams用戶端，Teams使用者不會在 Teams 中看到通話應用程式。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-178">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span>

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a><span data-ttu-id="1f8ba-179">可新增多少個釘點應用程式至策略</span><span class="sxs-lookup"><span data-stu-id="1f8ba-179">How many pinned apps can be added to a policy</span></span>

<span data-ttu-id="1f8ba-180">在 iOS 和 Android 手機上，Teams至少 (兩個 app) 。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-180">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="1f8ba-181">如果策略少於兩個 App，行動用戶端不會反映該策略設定，而是會繼續使用現有的設定。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-181">If a policy has fewer than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

<span data-ttu-id="1f8ba-182">您可以新增到策略的釘點 App 數量沒有限制。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-182">There's no limit on the number of pinned apps you can add to a policy.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="1f8ba-183">政策變更生效需要多久時間</span><span class="sxs-lookup"><span data-stu-id="1f8ba-183">How long does it take for policy changes to take effect</span></span>

<span data-ttu-id="1f8ba-184">編輯或指派原則之後，變更可能需要幾個小時的時間才會生效。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-184">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="1f8ba-185">使用者體驗</span><span class="sxs-lookup"><span data-stu-id="1f8ba-185">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="1f8ba-186">使用者如何在應用程式中查看所有已釘Teams</span><span class="sxs-lookup"><span data-stu-id="1f8ba-186">How can users see all their pinned apps in Teams</span></span>

<span data-ttu-id="1f8ba-187">若要查看已釘住使用者的所有 App，使用者可能需要根據已安裝的應用程式數量及其用戶端視窗Teams執行下列操作。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-187">To view all apps that are pinned for a user, users might have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="1f8ba-188">Teams桌面用戶端</span><span class="sxs-lookup"><span data-stu-id="1f8ba-188">Teams desktop client</span></span> |<span data-ttu-id="1f8ba-189">Teams 行動用戶端</span><span class="sxs-lookup"><span data-stu-id="1f8ba-189">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="1f8ba-190">在應用程式欄的 Teams中，選取 **...更多應用程式**。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-190">In the app bar on the side of Teams, select **... More apps**.</span></span>| <span data-ttu-id="1f8ba-191">在靠近應用程式底部的應用程式Teams向上滑動。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-191">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![桌面用戶端Teams更多應用程式](media/app-setup-policies-desktop-more-apps.png)<br>   |![行動用戶端中的Teams應用程式](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="1f8ba-194">我需要知道行動Teams體驗</span><span class="sxs-lookup"><span data-stu-id="1f8ba-194">What do I need to know about the Teams mobile experience</span></span>

<span data-ttu-id="1f8ba-195">iOS Teams Android (的手機用戶端) 靜態選項卡支援個人 App。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-195">The Teams mobile clients (iOS and Android) support personal apps with static tabs.</span></span> <span data-ttu-id="1f8ba-196">固定到桌面Teams的應用程式會顯示在Teams用戶端中。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-196">Apps pinned to the Teams desktop client will appear in the Teams mobile clients.</span></span> <span data-ttu-id="1f8ba-197">個人 Bot 會顯示在行動用戶端上的聊天中。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-197">Personal bots will appear in Chat on mobile clients.</span></span>

<span data-ttu-id="1f8ba-198">協力廠商應用程式 (可從 Store Teams下載) ，才能在行動版上顯示。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-198">Third-party apps (which can be downloaded from Teams Store) need to be approved before they show up on mobile.</span></span> <span data-ttu-id="1f8ba-199">如果系統管理員釘釘了未經 Microsoft for Mobile Teams的應用程式，它會顯示在桌上出版上，但不會顯示在行動版上。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-199">If an admin pins an app, which is unapproved by Microsoft for Mobile, it will show up on the Teams Desktop, but not show up on mobile.</span></span> <span data-ttu-id="1f8ba-200">請參閱 [行動用戶端](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients) 以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-200">See [Mobile clients](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients) for more information.</span></span>

<span data-ttu-id="1f8ba-201">有了Teams用戶端，使用者會看到核心 Teams 應用程式，例如活動、聊天和 Teams，而且您可以釘上 Microsoft 的一些第一方應用程式，例如 Shifts。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-201">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="1f8ba-202">使用者可以變更透過策略釘上的應用程式順序嗎？</span><span class="sxs-lookup"><span data-stu-id="1f8ba-202">Can users change the order of apps pinned through a policy</span></span>

<span data-ttu-id="1f8ba-203">如果使用者開啟了允許使用者釘選選項，Teams桌面和行動用戶端上的釘選應用程式順序。 </span><span class="sxs-lookup"><span data-stu-id="1f8ba-203">Users can change the order of their pinned apps on Teams desktop and mobile clients if the **Allow user pinning** option is turned on.</span></span> <span data-ttu-id="1f8ba-204">使用者無法變更在 Web 用戶端上釘Teams的順序。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-204">Users can't change the order of their pinned apps on Teams web clients.</span></span>

#### <a name="does-user-pinning-take-precedence"></a><span data-ttu-id="1f8ba-205">使用者釘點是否優先</span><span class="sxs-lookup"><span data-stu-id="1f8ba-205">Does user pinning take precedence</span></span>

<span data-ttu-id="1f8ba-206">系統管理圖釘永遠優先。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-206">Admin pins always take precedence.</span></span> <span data-ttu-id="1f8ba-207">如果開啟 **了允許使用者釘選** 選項，使用者就會在系統管理員釘選的 App 下方保留已釘選的應用程式。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-207">If the **Allow user pinning** option is turned on, then users will retain their pinned apps below admin pinned apps.</span></span> <span data-ttu-id="1f8ba-208">如果 **關閉允許使用者** 釘選選項，則使用者將失去其預先存在的圖釘，且只有系統管理員釘選的應用程式會存在於應用程式欄中。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-208">If the **Allow user pinning** option is turned off, then users will lose their pre-existing pins, and only admin-pinned apps will be present in the app bar.</span></span>

### <a name="custom-teams-apps"></a><span data-ttu-id="1f8ba-209">自訂Teams應用程式</span><span class="sxs-lookup"><span data-stu-id="1f8ba-209">Custom Teams apps</span></span>

<span data-ttu-id="1f8ba-210">我的組織已建立自訂 Teams 應用程式，併發布至 AppSource 或租使用者應用程式目錄，但是當應用程式釘釘到 Teams 中的應用程式欄時，應用程式圖示不會如預期顯示。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-210">My organization built a custom Teams app and published it, either to AppSource or the tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="1f8ba-211">如何修正此問題</span><span class="sxs-lookup"><span data-stu-id="1f8ba-211">How do I fix it</span></span>

<span data-ttu-id="1f8ba-212">提交應用程式之前，請務必遵循標誌指導方針。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-212">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="1f8ba-213">若要深入瞭解，請參閱賣方 [儀表板提交檢查清單](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)。</span><span class="sxs-lookup"><span data-stu-id="1f8ba-213">To learn more, see [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span></span>

## <a name="related-topics"></a><span data-ttu-id="1f8ba-214">相關主題</span><span class="sxs-lookup"><span data-stu-id="1f8ba-214">Related topics</span></span>

[<span data-ttu-id="1f8ba-215">在 Teams 中管理應用程式的設定</span><span class="sxs-lookup"><span data-stu-id="1f8ba-215">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="1f8ba-216">在 Teams 中將原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="1f8ba-216">Assign policies to your users in Teams</span></span>](assign-policies.md)
