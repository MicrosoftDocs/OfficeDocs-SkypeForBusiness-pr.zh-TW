---
title: 管理 Microsoft 團隊中的 app 許可權原則
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
description: 瞭解 Microsoft 團隊中的 app 許可權原則，以及如何使用它們來控制貴組織中的使用者可以使用哪些應用程式。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 15698c7eeb12187ccc510a42b9a6e2120a7907cc
ms.sourcegitcommit: 2467ece95e100a3a3cc2be3538d8eb7d878b3663
ms.contentlocale: zh-TW
ms.lasthandoff: 07/06/2020
ms.locfileid: "45042987"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a><span data-ttu-id="2a4e5-103">管理 Microsoft 團隊中的 app 許可權原則</span><span class="sxs-lookup"><span data-stu-id="2a4e5-103">Manage app permission policies in Microsoft Teams</span></span>

<span data-ttu-id="2a4e5-104">身為系統管理員，您可以使用應用程式權限原則來控制組織中 Microsoft Teams 使用者可使用的應用程式。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-104">As an admin, you can use app permission policies to control what apps are available to Microsoft Teams users in your organization.</span></span> <span data-ttu-id="2a4e5-105">您可以允許或封鎖由 Microsoft、協力廠商及貴組織發佈的所有 app 或特定應用程式。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-105">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span> <span data-ttu-id="2a4e5-106">當您封鎖應用程式時，擁有原則的使用者將無法從 Teams 應用程式商店安裝該應用程式。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-106">When you block an app, users who have the policy are unable to install it from the Teams app store.</span></span> <span data-ttu-id="2a4e5-107">您必須是全域系統管理員或 Teams 服務系統管理員，才能管理這些原則。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-107">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="2a4e5-108">您可以在 Microsoft 團隊系統管理中心管理 app 許可權原則。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-108">You manage app permission policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="2a4e5-109">您可以使用全域（組織範圍預設值）原則，或建立並指派自訂原則。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-109">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="2a4e5-110">除非您建立並指派自訂原則，否則貴組織中的使用者將會自動取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="2a4e5-111">在您編輯或指派原則之後，可能需要幾個小時的時間，變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-111">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

![App 許可權原則的螢幕擷取畫面](media/app-permission-policies.png)

> [!NOTE]
> <span data-ttu-id="2a4e5-113">整個組織內的應用程式設定會覆寫全域原則和您建立並指派給使用者的任何自訂原則。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-113">Org-wide app settings override the global policy and any custom policies that you create and assign to users.</span></span>

<span data-ttu-id="2a4e5-114">如果您的組織已在團隊中，您在 Microsoft 365 系統管理中心的 [整個租使用者]**設定**中所設定的應用程式設定會反映在 [[管理應用程式](manage-apps.md)] 頁面上的 [組織內應用程式設定] 中。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-114">If your organization is already on Teams, the app settings you configured in **Tenant-wide settings** in the Microsoft 365 admin center are reflected in org-wide app settings on the [Manage apps](manage-apps.md) page.</span></span> <span data-ttu-id="2a4e5-115">如果您是團隊新手，且剛開始使用，則預設會允許全域原則中的所有 app。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-115">If you're new to Teams and just getting started, by default, all apps are allowed in the global policy.</span></span> <span data-ttu-id="2a4e5-116">這包含由 Microsoft、協力廠商及貴組織發佈的應用程式。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-116">This includes apps published by Microsoft, third-parties, and your organization.</span></span>

<span data-ttu-id="2a4e5-117">例如，您想要封鎖所有協力廠商應用程式，並允許 Microsoft 針對貴組織中的人力資源小組特定應用程式。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-117">Say, for example, you want to block all third-party apps and allow specific apps from Microsoft for the HR team in your organization.</span></span> <span data-ttu-id="2a4e5-118">首先，您會移至 [[管理應用程式](manage-apps.md)] 頁面，並確認您想要在人力資源團隊中允許的應用程式可在組織層級使用。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-118">First, you would go to the [Manage apps](manage-apps.md) page and make sure that the apps that you want to allow for the HR team are allowed at the org level.</span></span> <span data-ttu-id="2a4e5-119">接著，建立名為 HR App 許可權原則的自訂原則，將它設定為 [封鎖] 並允許您想要的 app，然後將它指派給 HR 小組的使用者。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-119">Then, create a custom policy named HR App Permission Policy, set it to block and allow the apps that you want, and assign it to users on the HR team.</span></span>

> [!NOTE]
> <span data-ttu-id="2a4e5-120">如果您是在 Microsoft 365 政府社區雲端（GCC）環境中部署團隊，請參閱[管理 microsoft 365 政府的整個組織結構設定](#manage-org-wide-app-settings-for-microsoft-365-government)，以深入瞭解適用于 GCC 的協力廠商應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-120">If you deployed Teams in a Microsoft 365 Government Community Cloud (GCC) environment, see [Manage org-wide app settings for Microsoft 365 Government](#manage-org-wide-app-settings-for-microsoft-365-government) to learn more about third-party app settings that are unique to GCC.</span></span>

## <a name="create-a-custom-app-permission-policy"></a><span data-ttu-id="2a4e5-121">建立自訂應用程式許可權原則</span><span class="sxs-lookup"><span data-stu-id="2a4e5-121">Create a custom app permission policy</span></span>

<span data-ttu-id="2a4e5-122">如果您想要控制貴組織中不同群組使用者的可用應用程式，請建立並指派一或多個自訂應用程式許可權原則。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-122">If you want to control the apps that are available for different groups of users in your organization, create and assign one or more custom app permission policies.</span></span> <span data-ttu-id="2a4e5-123">您可以根據 Microsoft、協力廠商或您的組織發佈的應用程式，建立並指派個別的自訂原則。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-123">You can create and assign separate custom policies based on whether apps are published by Microsoft, third-parties, or your organization.</span></span> <span data-ttu-id="2a4e5-124">您必須知道，在您建立自訂原則之後，如果已停用組織內應用程式設定中的協力廠商應用程式，就無法變更它。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-124">It's important to know that after you create a custom policy, you can't change it if third-party apps are disabled in org-wide app settings.</span></span>

1. <span data-ttu-id="2a4e5-125">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**]  >  **許可權原則**。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-125">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="2a4e5-126">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-126">Click **Add**.</span></span> <br>
    <span data-ttu-id="2a4e5-127">![新應用程式許可權原則的螢幕擷取畫面](media/app-permission-policies-new-policy.png)</span><span class="sxs-lookup"><span data-stu-id="2a4e5-127">![Screenshot of new app permission policy](media/app-permission-policies-new-policy.png)</span></span>
3. <span data-ttu-id="2a4e5-128">輸入原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-128">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="2a4e5-129">在 [ **Microsoft app**]、[**協力廠商應用**程式] 和 [**自訂應用程式**] 底下，選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="2a4e5-129">Under **Microsoft apps**, **Third-party apps**, and **Custom apps**, select one of the following:</span></span>

    - <span data-ttu-id="2a4e5-130">**允許所有 app**</span><span class="sxs-lookup"><span data-stu-id="2a4e5-130">**Allow all apps**</span></span>
    - <span data-ttu-id="2a4e5-131">**允許特定的 app 和封鎖所有人**</span><span class="sxs-lookup"><span data-stu-id="2a4e5-131">**Allow specific apps and block all others**</span></span>
    - <span data-ttu-id="2a4e5-132">**封鎖特定應用程式並允許所有其他 app**</span><span class="sxs-lookup"><span data-stu-id="2a4e5-132">**Block specific apps and allow all others**</span></span>
    - <span data-ttu-id="2a4e5-133">**封鎖所有 app**</span><span class="sxs-lookup"><span data-stu-id="2a4e5-133">**Block all apps**</span></span>

5. <span data-ttu-id="2a4e5-134">如果您已選取 [**允許特定應用程式並封鎖其他 app**]，請新增您想要允許的應用程式：</span><span class="sxs-lookup"><span data-stu-id="2a4e5-134">If you selected **Allow specific apps and block others**, add the apps that you want to allow:</span></span>

    1. <span data-ttu-id="2a4e5-135">選取 [**允許應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-135">Select **Allow apps**.</span></span>
    1. <span data-ttu-id="2a4e5-136">搜尋您要允許的應用程式，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-136">Search for the apps that you want to allow, and then click **Add**.</span></span> <span data-ttu-id="2a4e5-137">搜尋結果會篩選到應用程式發行者（**Microsoft**app、**協力廠商應用程式**或**自訂應用程式**）。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-137">The search results are filtered to the app publisher (**Microsoft apps**, **Third-party apps**, or **Custom apps**).</span></span>
    1. <span data-ttu-id="2a4e5-138">當您選取 app 清單後，請按一下 [**允許**]。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-138">When you've chosen the list of apps, click **Allow**.</span></span> 

6. <span data-ttu-id="2a4e5-139">同樣地，如果您已選取 [**封鎖特定應用程式並允許所有人**]，請搜尋並新增您想要封鎖的應用程式，然後按一下 [**封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-139">Similarly, if you selected **Block specific apps and allow all others**, search for and add the apps that you want to block, and then click **Block**.</span></span>
7. <span data-ttu-id="2a4e5-140">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-140">Click **Save**.</span></span>

## <a name="edit-an-app-permission-policy"></a><span data-ttu-id="2a4e5-141">編輯應用程式許可權原則</span><span class="sxs-lookup"><span data-stu-id="2a4e5-141">Edit an app permission policy</span></span>

<span data-ttu-id="2a4e5-142">您可以使用 Microsoft 團隊系統管理中心來編輯原則，包括您建立的全域原則和自訂原則。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-142">You can use the Microsoft Teams admin center to edit a policy, including the global policy and custom policies that you create.</span></span>

1. <span data-ttu-id="2a4e5-143">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**]  >  **許可權原則**。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-143">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="2a4e5-144">按一下原則名稱左邊的，然後按一下 [**編輯**]，選取原則。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-144">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="2a4e5-145">您可以從這裡進行所要的變更。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-145">From here, make the changes that you want.</span></span> <span data-ttu-id="2a4e5-146">您可以根據應用程式發行者管理設定，然後根據 [允許/封鎖] 設定新增及移除應用程式。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-146">You can manage settings based on the app publisher and add and remove apps based on the allow/block setting.</span></span>
4. <span data-ttu-id="2a4e5-147">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-147">Click **Save**.</span></span>

## <a name="assign-a-custom-app-permission-policy-to-users"></a><span data-ttu-id="2a4e5-148">將自訂應用程式許可權原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="2a4e5-148">Assign a custom app permission policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="manage-org-wide-app-settings-for-microsoft-365-government"></a><span data-ttu-id="2a4e5-149">管理 Microsoft 365 政府的整個組織性應用程式設定</span><span class="sxs-lookup"><span data-stu-id="2a4e5-149">Manage org-wide app settings for Microsoft 365 Government</span></span>  

<span data-ttu-id="2a4e5-150">在 Microsoft 365 政府版的團隊部署中，請務必瞭解下列關於適用于 GCC 的協力廠商應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-150">In a Microsoft 365 Government - GCC deployment of Teams, it's important to know the following about third-party app settings, which are unique to GCC.</span></span>

<span data-ttu-id="2a4e5-151">在 GCC 中，預設會封鎖所有協力廠商應用程式。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-151">In GCC, all third-party apps are blocked by default.</span></span> <span data-ttu-id="2a4e5-152">此外，您會在 Microsoft 團隊系統管理中心的 [應用程式許可權原則] 頁面上，看到有關管理協力廠商應用程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-152">Additionally, you'll see the following note about managing third-party apps on the app permission policies page in the Microsoft Teams admin center.</span></span>

![在 GCC 中應用程式許可權原則的螢幕擷取畫面](media/app-permission-policies-gcc.png)

<span data-ttu-id="2a4e5-154">使用整個組織的 app 設定來控制使用者是否可以安裝協力廠商應用程式。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-154">Use org-wide app settings to control whether users can install third-party apps.</span></span> <span data-ttu-id="2a4e5-155">全組織式應用程式設定會控制所有使用者的行為，並覆寫指派給使用者的任何其他應用程式許可權原則。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-155">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="2a4e5-156">您可以使用它們來控制惡意或有問題的 app。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-156">You can use them to control malicious or problematic apps.</span></span>

1. <span data-ttu-id="2a4e5-157">在 [**許可權原則**] 頁面上，選取 [**全組織式應用程式設定**]。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-157">On the **Permission policies** page, select **Org-wide app settings**.</span></span> <span data-ttu-id="2a4e5-158">接著，您可以在面板中設定您想要的設定。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-158">You can then configure the settings you want in the panel.</span></span>

    ![整個組織內的應用程式設定的螢幕擷取畫面](media/app-permission-policies-gcc-org-wide.png)
    
2. <span data-ttu-id="2a4e5-160">在**協力廠商應用程式**下，關閉或開啟這些設定以控制對協力廠商應用程式的存取：</span><span class="sxs-lookup"><span data-stu-id="2a4e5-160">Under **Third-party apps**, turn off or turn on these settings to control access to third-party apps:</span></span>

    - <span data-ttu-id="2a4e5-161">**允許協力廠商應用程式**：控制使用者是否可以使用協力廠商應用程式。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-161">**Allow third-party apps**: This controls whether users can use third-party apps.</span></span> <span data-ttu-id="2a4e5-162">如果您關閉此設定，您的使用者將無法安裝或使用任何協力廠商應用程式。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-162">If you turn off this setting, your users won't be able to install or use any third-party apps.</span></span> <span data-ttu-id="2a4e5-163">在 Microsoft 365 政府版的團隊部署中，此設定預設為關閉。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-163">In a Microsoft 365 Government - GCC deployment of Teams, this setting is off by default.</span></span>
    - <span data-ttu-id="2a4e5-164">**允許預設發佈至商店的任何新的協力廠商應用程式**：這會控制發佈至 [小組] 應用程式商店的新的協力廠商應用程式是否會自動在小組中提供。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-164">**Allow any new third-party apps published to the store by default**: This controls whether new third-party apps that are published to the Teams app store become automatically available in Teams.</span></span> <span data-ttu-id="2a4e5-165">如果您允許協力廠商應用程式，則只能設定此選項。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-165">You can only set this option if you allow third-party apps.</span></span>

3. <span data-ttu-id="2a4e5-166">在 [**封鎖的應用程式**] 底下，新增您想要封鎖在整個組織中的 app。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-166">Under **Blocked apps**, add the apps you want to block across your organization.</span></span> <span data-ttu-id="2a4e5-167">在 Microsoft 365 政府版的團隊部署中，所有協力廠商應用程式預設都會新增到此清單。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-167">In a Microsoft 365 Government - GCC deployment of Teams, all third-party apps are added to this list by default.</span></span> <span data-ttu-id="2a4e5-168">針對您想要在組織中允許的任何協力廠商應用程式，請從這個封鎖的應用程式清單中移除 app。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-168">For any third-party app you want to allow in your organization, remove the app from this blocked apps list.</span></span> <span data-ttu-id="2a4e5-169">當您封鎖 app 的整個應用程式時，系統會自動封鎖所有使用者的 app，不論應用程式許可權原則是否允許該應用程式。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-169">When you block an app org-wide, the app is automatically blocked for all your users, regardless of whether it's allowed in any app permission policies</span></span>
4. <span data-ttu-id="2a4e5-170">按一下 [**儲存**以組織範圍內的應用程式設定] 生效。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-170">Click **Save** for org-wide app settings to take effect.</span></span>

<span data-ttu-id="2a4e5-171">如前文所述，若要允許協力廠商應用程式，您可以編輯及使用全域（組織範圍預設值）原則，或建立並指派自訂原則。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-171">As mentioned earlier, to allow third-party apps, you can either edit and use the global (Org-wide default) policy or create and assign custom policies.</span></span>

## <a name="faq"></a><span data-ttu-id="2a4e5-172">常見問題集</span><span class="sxs-lookup"><span data-stu-id="2a4e5-172">FAQ</span></span>

### <a name="working-with-app-permission-policies"></a><span data-ttu-id="2a4e5-173">使用應用程式許可權原則</span><span class="sxs-lookup"><span data-stu-id="2a4e5-173">Working with app permission policies</span></span>

#### <a name="what-app-interactions-do-permission-policies-affect"></a><span data-ttu-id="2a4e5-174">許可權原則會影響哪些 app 互動？</span><span class="sxs-lookup"><span data-stu-id="2a4e5-174">What app interactions do permission policies affect?</span></span>
<span data-ttu-id="2a4e5-175">許可權原則可控制使用者的安裝、探索及互動，以控制應用程式的使用狀況。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-175">Permission policies govern app usage by controlling installation, discovery, and interaction for end users.</span></span> <span data-ttu-id="2a4e5-176">無論指派的許可權原則為何，管理員仍可管理 Microsoft 團隊系統管理中心中的 app。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-176">Admins can still manage apps in the Microsoft Teams admin center regardless of the permission policies assigned to them.</span></span>

#### <a name="can-i-control-line-of-business-lob-apps"></a><span data-ttu-id="2a4e5-177">我可以控制商務用線（LOB）應用程式嗎？</span><span class="sxs-lookup"><span data-stu-id="2a4e5-177">Can I control line of business (LOB) apps?</span></span>
<span data-ttu-id="2a4e5-178">是的，您可以使用應用程式許可權原則來控制自訂（LOB）應用程式的推出與發佈。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-178">Yes, you can use app permission policies to control the rollout and distribution of custom (LOB) apps.</span></span> <span data-ttu-id="2a4e5-179">您可以建立自訂原則或編輯全域原則，以根據貴組織的需求來允許或封鎖自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-179">You can create a custom policy or edit the global policy to allow or block custom apps based on the needs of your organization.</span></span>

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a><span data-ttu-id="2a4e5-180">App 許可權原則如何與釘選的 app 和 app 設定原則相關？</span><span class="sxs-lookup"><span data-stu-id="2a4e5-180">How do app permission policies relate to pinned apps and app setup policies?</span></span>

<span data-ttu-id="2a4e5-181">您可以將應用程式設定原則與 app 許可權原則搭配使用。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-181">You can use app setup policies together with app permission policies.</span></span> <span data-ttu-id="2a4e5-182">已從使用者的已啟用應用程式集中選取預先固定的 app。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-182">Pre-pinned apps are selected from the set of enabled apps for a user.</span></span> <span data-ttu-id="2a4e5-183">此外，如果使用者有應用程式許可權原則，而該策略封鎖 app 設定原則中的 app，該 app 就不會出現在小組中。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-183">Additionally, if a user has an app permission policy that blocks an app in their app setup policy, that app won't appear in Teams.</span></span>

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps"></a><span data-ttu-id="2a4e5-184">我可以使用應用程式許可權原則來限制上傳自訂應用程式嗎？</span><span class="sxs-lookup"><span data-stu-id="2a4e5-184">Can I use app permission policies to restrict uploading custom apps?</span></span>

<span data-ttu-id="2a4e5-185">您可以在 [**管理**app] 頁面上使用整個組織的設定，或按一下 [應用程式設定原則]，限制您的組織上傳自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-185">You can use org-wide settings on the **Manage apps** page, or app setup policies to restrict uploading custom apps for your organization.</span></span>  

<span data-ttu-id="2a4e5-186">若要限制特定使用者上傳自訂應用程式，請使用自訂 app 原則。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-186">To restrict specific users from uploading custom apps, use custom app policies.</span></span> <span data-ttu-id="2a4e5-187">若要深入瞭解，請參閱[管理團隊中的自訂應用程式原則和設定](teams-custom-app-policies-and-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-187">To learn more, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a><span data-ttu-id="2a4e5-188">封鎖應用程式適用于團隊行動用戶端嗎？</span><span class="sxs-lookup"><span data-stu-id="2a4e5-188">Does blocking an app apply to Teams mobile clients?</span></span>

<span data-ttu-id="2a4e5-189">是的，當您封鎖應用程式時，該應用程式會在所有團隊用戶端間封鎖。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-189">Yes, when you block an app, that app is blocked across all Teams clients.</span></span>  

### <a name="user-experience"></a><span data-ttu-id="2a4e5-190">使用者體驗</span><span class="sxs-lookup"><span data-stu-id="2a4e5-190">User experience</span></span>

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a><span data-ttu-id="2a4e5-191">當應用程式遭到封鎖時，使用者有何體驗？</span><span class="sxs-lookup"><span data-stu-id="2a4e5-191">What does a user experience when an app is blocked?</span></span>

<span data-ttu-id="2a4e5-192">使用者無法與封鎖的 app 或其功能（例如 bot、索引標籤和訊息延伸）互動。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-192">Users can't interact with a blocked app or its capabilities, such bots, tabs, and messaging extensions.</span></span> <span data-ttu-id="2a4e5-193">在共用的內容（例如小組或群組聊天）中，機器人仍可以傳送訊息給該內容的所有參與者。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-193">In a shared context, such as a team or group chat, bots can still send messages to all participants of that context.</span></span> <span data-ttu-id="2a4e5-194">小組會在應用程式遭到封鎖時向使用者顯示。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-194">Teams indicates to the user when an app is blocked.</span></span>

<span data-ttu-id="2a4e5-195">例如，當應用程式遭到封鎖時，使用者就不能執行下列任何一項動作：</span><span class="sxs-lookup"><span data-stu-id="2a4e5-195">For example, when an app is blocked, users can't do any of the following:</span></span>

- <span data-ttu-id="2a4e5-196">將 app 新增至個人或加入聊天或團隊</span><span class="sxs-lookup"><span data-stu-id="2a4e5-196">Add the app personally or to a chat or team</span></span>
- <span data-ttu-id="2a4e5-197">傳送訊息給應用程式的 bot</span><span class="sxs-lookup"><span data-stu-id="2a4e5-197">Send messages to the app’s bot</span></span>
- <span data-ttu-id="2a4e5-198">執行傳送資訊回到應用程式的按鈕動作，例如可操作的訊息</span><span class="sxs-lookup"><span data-stu-id="2a4e5-198">Perform button actions that send information back to the app, such as actionable messages</span></span>  
- <span data-ttu-id="2a4e5-199">[查看] 應用程式的索引標籤</span><span class="sxs-lookup"><span data-stu-id="2a4e5-199">View the app’s tab</span></span>
- <span data-ttu-id="2a4e5-200">設定連接器接收通知</span><span class="sxs-lookup"><span data-stu-id="2a4e5-200">Set up connectors to receive notifications</span></span>
- <span data-ttu-id="2a4e5-201">使用應用程式的訊息延伸</span><span class="sxs-lookup"><span data-stu-id="2a4e5-201">Use the app’s messaging extension</span></span>

<span data-ttu-id="2a4e5-202">舊版入口網站允許您在組織階層控制應用程式，這表示當應用程式遭到封鎖時，系統會封鎖組織中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-202">The legacy portal allowed controlling apps at the organization level, which means when an app is blocked, it's blocked for all users in the organization.</span></span> <span data-ttu-id="2a4e5-203">封鎖 [[管理應用程式](manage-apps.md)] 頁面上的應用程式的運作方式與此完全相同。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-203">Blocking an app on the [Manage apps](manage-apps.md) page works exactly the same way.</span></span>

<span data-ttu-id="2a4e5-204">針對指派給特定使用者的 app 許可權原則，如果允許並封鎖具有機器人或連接器功能的應用程式，而且如果只允許共用內容中的部分使用者使用該應用程式，則群組聊天或頻道的成員不具備該應用程式的許可權，就能看到由 bot 或連接器張貼的訊息歷程記錄和訊息。，但無法與它互動。</span><span class="sxs-lookup"><span data-stu-id="2a4e5-204">For app permission policies assigned to specific users, if an app with bot or connector capability was allowed and then blocked, and if the app is then allowed only for some users in a shared context, members of a group chat or channel that don't have permission to that app can see the message history and messages that were posted by the bot or connector, but can't interact with it.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2a4e5-205">相關主題</span><span class="sxs-lookup"><span data-stu-id="2a4e5-205">Related topics</span></span>

[<span data-ttu-id="2a4e5-206">在 Teams 中的應用程式系統管理設定</span><span class="sxs-lookup"><span data-stu-id="2a4e5-206">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="2a4e5-207">指派策略給小組中的使用者</span><span class="sxs-lookup"><span data-stu-id="2a4e5-207">Assign policies to your users in Teams</span></span>](assign-policies.md)
