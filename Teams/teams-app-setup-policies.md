---
title: 在 Microsoft 團隊中管理 app 設定原則
author: lanachin
ms.author: v-lanac
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
description: 瞭解如何在 Microsoft 團隊中針對貴組織的使用者使用及管理 app 設定原則。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: a23d9f5196f2d537e00c6e049377f9a7d7488654
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611597"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="92402-103">在 Microsoft 團隊中管理 app 設定原則</span><span class="sxs-lookup"><span data-stu-id="92402-103">Manage app setup policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="92402-104">如果您已啟用整個組織內的應用程式設定， **允許與自訂應用程式互動**，您可能不會在 Microsoft 團隊系統管理中心看到 app 設定原則。</span><span class="sxs-lookup"><span data-stu-id="92402-104">If you enabled the org-wide app setting, **Allow interaction with custom apps**, you may not see app setup policies yet in the Microsoft Teams admin center.</span></span> <span data-ttu-id="92402-105">目前正在推出，且即將在您的組織中提供此功能。</span><span class="sxs-lookup"><span data-stu-id="92402-105">It's currently being rolled out and will be available soon in your organization.</span></span>

<span data-ttu-id="92402-106">做為管理員，您可以使用應用程式設定原則來執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="92402-106">As an admin, you can use app setup policies to do the following tasks:</span></span>

- <span data-ttu-id="92402-107">自訂 Teams 以強調對使用者而言最重要的應用程式。</span><span class="sxs-lookup"><span data-stu-id="92402-107">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="92402-108">您可以選擇要釘選的 app，並設定它們出現的順序。</span><span class="sxs-lookup"><span data-stu-id="92402-108">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="92402-109">釘選應用程式可讓您展示貴組織中的使用者所需的 app，包括由協力廠商或貴組織中的開發人員所建立的應用程式。</span><span class="sxs-lookup"><span data-stu-id="92402-109">Pinning apps lets you showcase apps that users in your organization need, including apps built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="92402-110">控制使用者是否可以將應用程式釘選到 Teams。</span><span class="sxs-lookup"><span data-stu-id="92402-110">Control whether users can pin apps to Teams.</span></span>
- <span data-ttu-id="92402-111">**(在預覽) 中** 代表使用者安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="92402-111">Install apps on behalf of users **(in preview)**.</span></span> <span data-ttu-id="92402-112">您可以選擇在使用者開始團隊時預設會為使用者安裝哪些 app。</span><span class="sxs-lookup"><span data-stu-id="92402-112">You choose which apps are installed by default for users when they start Teams.</span></span> <span data-ttu-id="92402-113">請記住，如果指派給他們的 [app 許可權原則](teams-app-permission-policies.md) 允許，使用者仍然可以自行安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="92402-113">Keep in mind that users can still install apps themselves if the [app permission policy](teams-app-permission-policies.md) that's assigned to them allows it.</span></span>

<span data-ttu-id="92402-114">應用程式會釘選到應用程式行，這是位於團隊桌面用戶端的列，而在團隊行動用戶端 (iOS 和 Android) 。</span><span class="sxs-lookup"><span data-stu-id="92402-114">Apps are pinned to the app bar, which is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="92402-115">團隊桌面用戶端</span><span class="sxs-lookup"><span data-stu-id="92402-115">Teams desktop client</span></span>  |<span data-ttu-id="92402-116">團隊行動用戶端</span><span class="sxs-lookup"><span data-stu-id="92402-116">Teams mobile client</span></span> |
|---------|---------|
|![團隊桌面用戶端](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![團隊行動用戶端](media/mobile-app-ui.png)      |

<span data-ttu-id="92402-119">若要查看其預先安裝的應用程式，請在應用程式行中，使用者選取 **.。。** 團隊桌面及網頁用戶端中的其他應用程式，並在行動用戶端中向上滑動。</span><span class="sxs-lookup"><span data-stu-id="92402-119">To see their pre-installed apps, in the app bar, users select **... More apps** in the Teams desktop and web clients and swipe up in the mobile clients.</span></span>

<span data-ttu-id="92402-120">您可以在 Microsoft [團隊管理中心] 管理 app 設定原則。</span><span class="sxs-lookup"><span data-stu-id="92402-120">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="92402-121">使用全域 (組織範圍的預設) 原則，或建立並指派自訂原則。</span><span class="sxs-lookup"><span data-stu-id="92402-121">Use the global (Org-wide default) policy or create and assign custom policies.</span></span>  <span data-ttu-id="92402-122">除非您建立並指派自訂原則，否則貴組織中的使用者將會自動取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="92402-122">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="92402-123">您必須是全域系統管理員或 Teams 服務系統管理員，才能管理這些原則。</span><span class="sxs-lookup"><span data-stu-id="92402-123">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="92402-124">您編輯全域原則中的設定，以包含您想要的 app。</span><span class="sxs-lookup"><span data-stu-id="92402-124">You edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="92402-125">若要針對貴組織中不同群組的使用者自訂小組，請建立並指派一或多個自訂原則。</span><span class="sxs-lookup"><span data-stu-id="92402-125">To customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

![[應用程式設定原則] 頁面](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="92402-127">如果您有教育版小組，請務必知道作業 app 預設會在全域原則中固定，即使您目前不會看到它列在全域原則中也一樣。</span><span class="sxs-lookup"><span data-stu-id="92402-127">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="92402-128">它將是團隊用戶端上固定應用程式清單中的第四個應用程式。</span><span class="sxs-lookup"><span data-stu-id="92402-128">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="92402-129">建立自訂應用程式設定原則</span><span class="sxs-lookup"><span data-stu-id="92402-129">Create a custom app setup policy</span></span>

<span data-ttu-id="92402-130">您可以使用 Microsoft 團隊系統管理中心來建立自訂原則。</span><span class="sxs-lookup"><span data-stu-id="92402-130">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="92402-131">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**  >  **設定原則**]。</span><span class="sxs-lookup"><span data-stu-id="92402-131">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="92402-132">選取 [新增 **]**。</span><span class="sxs-lookup"><span data-stu-id="92402-132">Select **Add**.</span></span>

   ![[新增應用程式設定原則] 頁面](media/app-setup-policies-add.png)
    
3. <span data-ttu-id="92402-134">輸入原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="92402-134">Enter a name and description for the policy.</span></span>

4. <span data-ttu-id="92402-135">開啟或關閉 [上 **傳自訂應用程式**]，視您是否要讓使用者將自訂應用程式上傳至團隊而定。</span><span class="sxs-lookup"><span data-stu-id="92402-135">Turn on or turn off **Upload custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span> <span data-ttu-id="92402-136">如果 [ **允許協力廠商應用** 程式在 [組織內的應用程式設定](manage-apps.md#manage-org-wide-app-settings)中關閉]，您就無法變更此設定。</span><span class="sxs-lookup"><span data-stu-id="92402-136">You can't change this setting if **Allow third-party apps** is turned off in [org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>

5. <span data-ttu-id="92402-137">開啟或關閉 [ **允許使用者釘** 用]，視您是否要讓使用者將應用程式釘選到自己的應用程式行。</span><span class="sxs-lookup"><span data-stu-id="92402-137">Turn on or turn off **Allow user pinning**, depending on whether you want to let users personalize their app bar by pinning apps to it.</span></span>

   > [!NOTE]
   > <span data-ttu-id="92402-138">[ **允許使用者釘** 選] 設定可在 Microsoft 365 政府社區中的 [團隊管理中心] (gcc) 環境 (GCC、gcc 高和 DoD) 中，但目前它沒有任何作用。</span><span class="sxs-lookup"><span data-stu-id="92402-138">The **Allow user pinning** setting is available in the Teams admin center in Microsoft 365 Government Community Cloud (GCC) environments (GCC, GCC High and DoD), but currently it has no effect.</span></span>

6. <span data-ttu-id="92402-139">若要為使用者安裝應用程式 **(在預覽) 中**，請執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="92402-139">To install apps for users **(in preview)**, do the following tasks:</span></span>

    1. <span data-ttu-id="92402-140">在 [ **已安裝的 app**] 底下，選取 [ **新增 app**]。</span><span class="sxs-lookup"><span data-stu-id="92402-140">Under **Installed apps**, select **Add apps**.</span></span>
    
    2. <span data-ttu-id="92402-141">在 [ **新增已安裝的應用程式** ] 窗格中，搜尋您想要在使用者開始團隊時自動安裝的應用程式。</span><span class="sxs-lookup"><span data-stu-id="92402-141">In the **Add installed apps** pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="92402-142">您也可以依應用程式許可權原則篩選 app。</span><span class="sxs-lookup"><span data-stu-id="92402-142">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="92402-143">當您選取 app 清單後，請選取 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="92402-143">When you've chosen your list of apps, select **Add**.</span></span>

       ![[新增已安裝的應用程式] 窗格](media/app-setup-policies-add-installed-apps.png)

7. <span data-ttu-id="92402-145">若要釘選應用程式，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="92402-145">To pin apps, do the following:</span></span>

    1. <span data-ttu-id="92402-146">在 [ **固定應用程式**] 底下，選取 [ **新增應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="92402-146">Under **Pinned apps**, select **Add apps**.</span></span>
    
    2. <span data-ttu-id="92402-147">在 [ **新增釘選的應用程式** ] 窗格中，搜尋您要新增的應用程式，然後選取 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="92402-147">In the **Add pinned apps** pane, search for the apps you want to add, and then select **Add**.</span></span> <span data-ttu-id="92402-148">您也可以依應用程式許可權原則篩選 app。</span><span class="sxs-lookup"><span data-stu-id="92402-148">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="92402-149">當您選擇要釘選的 app 清單時，請選取 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="92402-149">When you've chosen your list of apps to pin, select **Add**.</span></span>

       ![[新增釘選的 app] 窗格](media/app-setup-policies-add-apps.png)

    3. <span data-ttu-id="92402-151">依您希望它們出現在團隊中的順序排列 app，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="92402-151">Arrange the apps in the order that you want them to appear in Teams, and then select **Save**.</span></span>

       ![[釘選的 app] 區段](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="92402-153">編輯應用程式設定原則</span><span class="sxs-lookup"><span data-stu-id="92402-153">Edit an app setup policy</span></span>

<span data-ttu-id="92402-154">您可以使用 Microsoft 團隊系統管理中心來編輯原則，包括全域 (組織內的預設) 原則，以及您建立的自訂原則。</span><span class="sxs-lookup"><span data-stu-id="92402-154">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="92402-155">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**  >  **設定原則**]。</span><span class="sxs-lookup"><span data-stu-id="92402-155">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="92402-156">按一下原則名稱左邊的，然後選取 [ **編輯**]，選取原則。</span><span class="sxs-lookup"><span data-stu-id="92402-156">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>

3. <span data-ttu-id="92402-157">您可以從這裡進行所要的變更。</span><span class="sxs-lookup"><span data-stu-id="92402-157">From here, make the changes that you want.</span></span>

4. <span data-ttu-id="92402-158">選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="92402-158">Select **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="92402-159">將自訂應用程式設定原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="92402-159">Assign a custom app setup policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a><span data-ttu-id="92402-160">常見問題集</span><span class="sxs-lookup"><span data-stu-id="92402-160">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="92402-161">使用應用程式設定原則</span><span class="sxs-lookup"><span data-stu-id="92402-161">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="92402-162">Microsoft 團隊系統管理中心包含哪些內建應用程式設定原則</span><span class="sxs-lookup"><span data-stu-id="92402-162">What built-in app setup policies are included in the Microsoft Teams admin center</span></span>

- <span data-ttu-id="92402-163">**全域 (組織範圍的預設)**：此預設原則適用于貴組織中的所有使用者，除非您指派其他原則。</span><span class="sxs-lookup"><span data-stu-id="92402-163">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="92402-164">編輯 [全域原則]，將最重要的 app 釘選到您的使用者。</span><span class="sxs-lookup"><span data-stu-id="92402-164">Edit the global policy to pin apps that are most important for your users.</span></span>

- <span data-ttu-id="92402-165">**FirstLineWorker**：此原則適用于第一線員工工作者。</span><span class="sxs-lookup"><span data-stu-id="92402-165">**FirstLineWorker**: This policy is for Firstline Workers.</span></span> <span data-ttu-id="92402-166">您可以將它指派給貴組織中的第一線員工工作人員。</span><span class="sxs-lookup"><span data-stu-id="92402-166">You can assign it to Firstline Workers in your organization.</span></span> <span data-ttu-id="92402-167">請務必注意，您所建立的自訂原則，您必須將原則指派給使用者，才能讓設定生效。</span><span class="sxs-lookup"><span data-stu-id="92402-167">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="92402-168">如需詳細資訊，請移至本文的將 [自訂應用程式設定原則指派給 [使用者](#assign-a-custom-app-setup-policy-to-users) ] 區段。</span><span class="sxs-lookup"><span data-stu-id="92402-168">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="92402-169">為什麼我無法在 [新增釘選的 app] 窗格中找到應用程式</span><span class="sxs-lookup"><span data-stu-id="92402-169">Why can't I find an app in the Add pinned apps pane</span></span>

<span data-ttu-id="92402-170">並非所有 app 都可透過應用程式設定原則釘選到團隊。</span><span class="sxs-lookup"><span data-stu-id="92402-170">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="92402-171">有些應用程式可能不支援此功能。</span><span class="sxs-lookup"><span data-stu-id="92402-171">Some apps may not support this functionality.</span></span> <span data-ttu-id="92402-172">若要尋找可釘選的 app，請在 [ **新增釘** 選的 app] 窗格中搜尋應用程式。</span><span class="sxs-lookup"><span data-stu-id="92402-172">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="92402-173">具有個人作用中的索引標籤 (靜態] 索引標籤可釘選到 [ **新增釘選的應用程式** ] 窗格中，) 和 bot 都可以固定在小組桌面用戶端。</span><span class="sxs-lookup"><span data-stu-id="92402-173">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="92402-174">請記住，[團隊] app store 會列出所有團隊應用程式。</span><span class="sxs-lookup"><span data-stu-id="92402-174">Keep in mind that the Teams app store lists all Teams apps.</span></span> <span data-ttu-id="92402-175">[ **新增釘** 選的 app] 窗格只會包含可透過原則釘選至團隊的 app。</span><span class="sxs-lookup"><span data-stu-id="92402-175">The **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span>

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="92402-176">我是教育版管理員的團隊。在教育版團隊中，關於 app 設定原則，我需要知道什麼？</span><span class="sxs-lookup"><span data-stu-id="92402-176">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education</span></span>

<span data-ttu-id="92402-177">在教育版小組中無法使用通話應用程式。</span><span class="sxs-lookup"><span data-stu-id="92402-177">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="92402-178">當您建立新的自訂應用程式設定原則時，通話 app 會顯示在應用程式清單中。</span><span class="sxs-lookup"><span data-stu-id="92402-178">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="92402-179">不過，應用程式不會釘選到團隊用戶端與教育版小組，也不會在團隊中看到 [通話] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="92402-179">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span>

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a><span data-ttu-id="92402-180">可將多少固定 app 新增至原則</span><span class="sxs-lookup"><span data-stu-id="92402-180">How many pinned apps can be added to a policy</span></span>

<span data-ttu-id="92402-181">必須將兩個 app 全部釘選至團隊行動用戶端 (iOS 和 Android) 。</span><span class="sxs-lookup"><span data-stu-id="92402-181">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="92402-182">如果原則的 app 少於兩個，行動用戶端不會反映原則設定，而是會繼續使用現有的設定。</span><span class="sxs-lookup"><span data-stu-id="92402-182">If a policy has fewer than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

<span data-ttu-id="92402-183">您可以新增至原則的固定 app 數目沒有限制。</span><span class="sxs-lookup"><span data-stu-id="92402-183">There's no limit on the number of pinned apps you can add to a policy.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="92402-184">原則變更要花多久時間才能生效</span><span class="sxs-lookup"><span data-stu-id="92402-184">How long does it take for policy changes to take effect</span></span>

<span data-ttu-id="92402-185">在您編輯或指派原則之後，可能需要幾個小時的時間，變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="92402-185">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="92402-186">使用者體驗</span><span class="sxs-lookup"><span data-stu-id="92402-186">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="92402-187">使用者如何在團隊中查看所有釘選的 app</span><span class="sxs-lookup"><span data-stu-id="92402-187">How can users see all their pinned apps in Teams</span></span>

<span data-ttu-id="92402-188">若要查看針對使用者釘選的所有 app，使用者可能必須執行下列動作，視已安裝的應用程式數量以及其小組用戶端視窗的大小而定。</span><span class="sxs-lookup"><span data-stu-id="92402-188">To view all apps that are pinned for a user, users might have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="92402-189">團隊桌面用戶端</span><span class="sxs-lookup"><span data-stu-id="92402-189">Teams desktop client</span></span> |<span data-ttu-id="92402-190">團隊行動用戶端</span><span class="sxs-lookup"><span data-stu-id="92402-190">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="92402-191">在團隊側面的應用程式行中，選取 **.。。其他應用程式**。</span><span class="sxs-lookup"><span data-stu-id="92402-191">In the app bar on the side of Teams, select **... More apps**.</span></span>| <span data-ttu-id="92402-192">在團隊底部附近的 [應用程式行] 中，向上滑動。</span><span class="sxs-lookup"><span data-stu-id="92402-192">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![團隊桌面用戶端中的其他應用程式](media/app-setup-policies-desktop-more-apps.png)<br>   |![團隊行動用戶端中的其他應用程式](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="92402-195">我需要知道的關於小組行動體驗的相關資訊</span><span class="sxs-lookup"><span data-stu-id="92402-195">What do I need to know about the Teams mobile experience</span></span>

<span data-ttu-id="92402-196"> (iOS 和 Android) 的小組行動用戶端目前不支援使用靜態索引標籤的個人 app。</span><span class="sxs-lookup"><span data-stu-id="92402-196">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="92402-197">根據原則中設定的應用程式，釘選到團隊行動用戶端的應用程式可能不會出現在小組行動用戶端中。</span><span class="sxs-lookup"><span data-stu-id="92402-197">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="92402-198">在行動用戶端上，個人機器人仍會出現在聊天中。</span><span class="sxs-lookup"><span data-stu-id="92402-198">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="92402-199">透過團隊行動用戶端，使用者將會看到核心團隊 app （例如活動、交談和團隊），而且您可以將某些協力廠商應用程式釘選到 Microsoft （例如倒班）。</span><span class="sxs-lookup"><span data-stu-id="92402-199">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="92402-200">使用者可以變更透過原則釘選的 app 順序</span><span class="sxs-lookup"><span data-stu-id="92402-200">Can users change the order of apps pinned through a policy</span></span>

<span data-ttu-id="92402-201">如果開啟 [ **允許使用者釘** 選] 選項，使用者就可以變更其在團隊桌面和行動用戶端上的固定 app 順序。</span><span class="sxs-lookup"><span data-stu-id="92402-201">Users can change the order of their pinned apps on Teams desktop and mobile clients if the **Allow user pinning** option is turned on.</span></span> <span data-ttu-id="92402-202">使用者無法在團隊 web 用戶端變更其固定應用程式的順序。</span><span class="sxs-lookup"><span data-stu-id="92402-202">Users can't change the order of their pinned apps on Teams web clients.</span></span>

#### <a name="does-user-pinning-take-precedence"></a><span data-ttu-id="92402-203">使用者釘選優先</span><span class="sxs-lookup"><span data-stu-id="92402-203">Does user pinning take precedence</span></span>

<span data-ttu-id="92402-204">如果指派給使用者的 app 設定原則已變更為 [封鎖使用者 app 釘選]，小組會移除任何釘選到應用程式行的應用程式。</span><span class="sxs-lookup"><span data-stu-id="92402-204">If the app setup policy assigned to the user is changed to block user app pinning, Teams removes any apps pinned to the app bar.</span></span> <span data-ttu-id="92402-205">如果隨後將原則變更為 [允許使用者 app 釘選]，使用者就必須重新固定其先前釘駐留的 app。</span><span class="sxs-lookup"><span data-stu-id="92402-205">If the policy is then changed to allow user app pinning, users must re-pin their previously pinned apps.</span></span>

### <a name="custom-teams-apps"></a><span data-ttu-id="92402-206">自訂團隊應用程式</span><span class="sxs-lookup"><span data-stu-id="92402-206">Custom Teams apps</span></span>

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a><span data-ttu-id="92402-207">我的組織已建立自訂團隊應用程式，並將其發佈至 AppSource 或租使用者目錄，但是當 app 釘選到 [團隊] 中的應用程式行時，應用程式圖示不會顯示為預期。</span><span class="sxs-lookup"><span data-stu-id="92402-207">My organization built a custom Teams app and published it, either to AppSource or the tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="92402-208">如何修正此問題</span><span class="sxs-lookup"><span data-stu-id="92402-208">How do I fix it</span></span>

<span data-ttu-id="92402-209">在提交 app 之前，請務必遵循標誌指導方針。</span><span class="sxs-lookup"><span data-stu-id="92402-209">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="92402-210">若要深入瞭解，請參閱 [賣方儀表板提交的檢查清單](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)。</span><span class="sxs-lookup"><span data-stu-id="92402-210">To learn more, see [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span></span>

## <a name="related-topics"></a><span data-ttu-id="92402-211">相關主題</span><span class="sxs-lookup"><span data-stu-id="92402-211">Related topics</span></span>

[<span data-ttu-id="92402-212">在 Teams 中的應用程式系統管理設定</span><span class="sxs-lookup"><span data-stu-id="92402-212">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="92402-213">指派策略給小組中的使用者</span><span class="sxs-lookup"><span data-stu-id="92402-213">Assign policies to your users in Teams</span></span>](assign-policies.md)
