---
title: 在 Microsoft Teams 中管理應用程式權限原則
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
description: 了解 Microsoft Teams 中的應用程式權限原則，以及如何使用這些原則來控制組織中使用者可使用的應用程式。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 73b583493a57141fef3c120fa2eb134cbaa8a500
ms.sourcegitcommit: cfef9dd41cac0df83bd02b35036d8f8f1b472feb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51697738"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a><span data-ttu-id="f5eba-103">在 Microsoft Teams 中管理應用程式權限原則</span><span class="sxs-lookup"><span data-stu-id="f5eba-103">Manage app permission policies in Microsoft Teams</span></span>

<span data-ttu-id="f5eba-104">身為系統管理員，您可以使用應用程式權限原則來控制組織中 Microsoft Teams 使用者可使用的應用程式。</span><span class="sxs-lookup"><span data-stu-id="f5eba-104">As an admin, you can use app permission policies to control what apps are available to Microsoft Teams users in your organization.</span></span> <span data-ttu-id="f5eba-105">您可以允許或封鎖所有應用程式，或是由 Microsoft、第三方和您的組織發行的特定應用程式。</span><span class="sxs-lookup"><span data-stu-id="f5eba-105">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span> <span data-ttu-id="f5eba-106">當您封鎖應用程式時，擁有原則的使用者將無法從 Teams 應用程式商店安裝該應用程式。</span><span class="sxs-lookup"><span data-stu-id="f5eba-106">When you block an app, users who have the policy are unable to install it from the Teams app store.</span></span> <span data-ttu-id="f5eba-107">您必須是全域系統管理員或 Teams 服務系統管理員，才能管理這些原則。</span><span class="sxs-lookup"><span data-stu-id="f5eba-107">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="f5eba-108">您可以在 Microsoft Teams 系統管理中心管理應用程式權限原則。</span><span class="sxs-lookup"><span data-stu-id="f5eba-108">You manage app permission policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="f5eba-109">您可以使用全域 (全組織預設值) 原則，或建立並指派自訂原則。</span><span class="sxs-lookup"><span data-stu-id="f5eba-109">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="f5eba-110">除非您建立並指派自訂原則，否則組織中的使用者將會自動取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="f5eba-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="f5eba-111">編輯或指派原則之後，變更可能需要幾個小時的時間才會生效。</span><span class="sxs-lookup"><span data-stu-id="f5eba-111">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

![應用程式權限原則的螢幕擷取畫面](media/app-permission-policies.png)

> [!NOTE]
> <span data-ttu-id="f5eba-113">全組織應用程式設定會覆寫全域原則與您建立並指派給使用者的任何自訂原則。</span><span class="sxs-lookup"><span data-stu-id="f5eba-113">Org-wide app settings override the global policy and any custom policies that you create and assign to users.</span></span>

<span data-ttu-id="f5eba-114">如果您的組織已採用 Teams，您在 Microsoft 365 系統管理中心的 [全租用戶設定 **]** 中所設定的應用程式設定，會反映在 [管理應用程式 []](manage-apps.md) 頁面的全組織設定。</span><span class="sxs-lookup"><span data-stu-id="f5eba-114">If your organization is already on Teams, the app settings you configured in **Tenant-wide settings** in the Microsoft 365 admin center are reflected in org-wide app settings on the [Manage apps](manage-apps.md) page.</span></span> <span data-ttu-id="f5eba-115">如果您是 Teams 的新使用者，且是剛開始使用，依預設，會在全域原則中允許所有應用程式。</span><span class="sxs-lookup"><span data-stu-id="f5eba-115">If you're new to Teams and just getting started, by default, all apps are allowed in the global policy.</span></span> <span data-ttu-id="f5eba-116">這包括由 Microsoft、第三方和您的組織所發佈的應用程式。</span><span class="sxs-lookup"><span data-stu-id="f5eba-116">This includes apps published by Microsoft, third-parties, and your organization.</span></span>

<span data-ttu-id="f5eba-117">比方說，假設您想要針對組織中的人力資源小組，封鎖所有第三方應用程式並允許來自 Microsoft 的特定應用程式。</span><span class="sxs-lookup"><span data-stu-id="f5eba-117">Say, for example, you want to block all third-party apps and allow specific apps from Microsoft for the HR team in your organization.</span></span> <span data-ttu-id="f5eba-118">首先，您會移至 [管理應用程式[]](manage-apps.md) 頁面，並確認您想要針對人力資源小組允許的應用程式會於組織層級允許。</span><span class="sxs-lookup"><span data-stu-id="f5eba-118">First, you would go to the [Manage apps](manage-apps.md) page and make sure that the apps that you want to allow for the HR team are allowed at the org level.</span></span> <span data-ttu-id="f5eba-119">然後，建立名為「人力資源應用程式權限原則」的自訂原則，將它設定為封鎖並允許您需要的應用程式，然後將它指派給人力資源小組的使用者。</span><span class="sxs-lookup"><span data-stu-id="f5eba-119">Then, create a custom policy named HR App Permission Policy, set it to block and allow the apps that you want, and assign it to users on the HR team.</span></span>

> [!NOTE]
> <span data-ttu-id="f5eba-120">如果您在 Microsoft 365 政府社群雲端高 (GCCH) 和國防部 (DoD) 環境中部署 Teams，請參閱管理 [Microsoft 365](#manage-org-wide-app-settings-for-microsoft-365-government) 政府版全組織 App 設定，以深入瞭解 GCCH 和 DoD 特有的協力廠商應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="f5eba-120">If you deployed Teams in a Microsoft 365 Government Community Cloud High (GCCH) and Department of Defense (DoD) environment, see [Manage org-wide app settings for Microsoft 365 Government](#manage-org-wide-app-settings-for-microsoft-365-government) to learn more about third-party app settings that are unique to GCCH and DoD.</span></span>

## <a name="create-a-custom-app-permission-policy"></a><span data-ttu-id="f5eba-121">建立自訂應用程式權限原則</span><span class="sxs-lookup"><span data-stu-id="f5eba-121">Create a custom app permission policy</span></span>

<span data-ttu-id="f5eba-122">如果您想要控制組織中不同使用者群組可用的應用程式，請建立並指派一或多個自訂應用程式權限原則。</span><span class="sxs-lookup"><span data-stu-id="f5eba-122">If you want to control the apps that are available for different groups of users in your organization, create and assign one or more custom app permission policies.</span></span> <span data-ttu-id="f5eba-123">您可以根據應用程式是否由 Microsoft、第三方或您的組織發佈，來建立並指派個別的自訂原則。</span><span class="sxs-lookup"><span data-stu-id="f5eba-123">You can create and assign separate custom policies based on whether apps are published by Microsoft, third-parties, or your organization.</span></span> <span data-ttu-id="f5eba-124">務必知道，建立自訂原則之後，如果已在全組織應用程式設定中停用第三方應用程式，就無法變更該自訂原則。</span><span class="sxs-lookup"><span data-stu-id="f5eba-124">It's important to know that after you create a custom policy, you can't change it if third-party apps are disabled in org-wide app settings.</span></span>

1. <span data-ttu-id="f5eba-125">在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [Teams 應用程式 **]**  >  [權限原則 **]**。</span><span class="sxs-lookup"><span data-stu-id="f5eba-125">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="f5eba-p106">按一下 [新增 **]**。</span><span class="sxs-lookup"><span data-stu-id="f5eba-p106">Click **Add**. </span></span><br>
    <span data-ttu-id="f5eba-127">![新增應用程式權限原則的螢幕擷取畫面](media/app-permission-policies-new-policy.png)</span><span class="sxs-lookup"><span data-stu-id="f5eba-127">![Screenshot of new app permission policy](media/app-permission-policies-new-policy.png)</span></span>
3. <span data-ttu-id="f5eba-128">輸入原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="f5eba-128">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="f5eba-129">在 [Microsoft 應用程式 **]**、[第三方應用程式 **]** 和 [自訂應用程式 **]** 下，選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="f5eba-129">Under **Microsoft apps**, **Third-party apps**, and **Custom apps**, select one of the following:</span></span>

    - <span data-ttu-id="f5eba-130">**允許所有應用程式**</span><span class="sxs-lookup"><span data-stu-id="f5eba-130">**Allow all apps**</span></span>
    - <span data-ttu-id="f5eba-131">**允許特定的應用程式並封鎖所有其他的**</span><span class="sxs-lookup"><span data-stu-id="f5eba-131">**Allow specific apps and block all others**</span></span>
    - <span data-ttu-id="f5eba-132">**封鎖特定的應用程式並允許所有其他的**</span><span class="sxs-lookup"><span data-stu-id="f5eba-132">**Block specific apps and allow all others**</span></span>
    - <span data-ttu-id="f5eba-133">**封鎖所有應用程式**</span><span class="sxs-lookup"><span data-stu-id="f5eba-133">**Block all apps**</span></span>

5. <span data-ttu-id="f5eba-134">如果您選取 [允許特定的應用程式並封鎖所有其他的 **]**，請新增您要允許的應用程式：</span><span class="sxs-lookup"><span data-stu-id="f5eba-134">If you selected **Allow specific apps and block others**, add the apps that you want to allow:</span></span>

    1. <span data-ttu-id="f5eba-135">選取 [允許應用程式 **]**。</span><span class="sxs-lookup"><span data-stu-id="f5eba-135">Select **Allow apps**.</span></span>
    1. <span data-ttu-id="f5eba-136">搜尋您要允許的應用程式，然後按一下 [新增 **]**。</span><span class="sxs-lookup"><span data-stu-id="f5eba-136">Search for the apps that you want to allow, and then click **Add**.</span></span> <span data-ttu-id="f5eba-137">搜尋結果會篩選至應用程式發行者 (**Microsoft 應用程式**、**第三方應用程式** 或 **自訂應用程式**)。</span><span class="sxs-lookup"><span data-stu-id="f5eba-137">The search results are filtered to the app publisher (**Microsoft apps**, **Third-party apps**, or **Custom apps**).</span></span>
    1. <span data-ttu-id="f5eba-138">選取應用程式清單後，請按一下 [允許 **]**。</span><span class="sxs-lookup"><span data-stu-id="f5eba-138">When you've chosen the list of apps, click **Allow**.</span></span> 

6. <span data-ttu-id="f5eba-139">同樣地，如果您選取 [封鎖特定的應用程式並允許所有其他的 **]**，請搜尋並新增您要封鎖的應用程式，然後按一下 [封鎖 **]**。</span><span class="sxs-lookup"><span data-stu-id="f5eba-139">Similarly, if you selected **Block specific apps and allow all others**, search for and add the apps that you want to block, and then click **Block**.</span></span>
7. <span data-ttu-id="f5eba-140">按一下 [儲存 **]**。</span><span class="sxs-lookup"><span data-stu-id="f5eba-140">Click **Save**.</span></span>

## <a name="edit-an-app-permission-policy"></a><span data-ttu-id="f5eba-141">編輯應用程式權限原則</span><span class="sxs-lookup"><span data-stu-id="f5eba-141">Edit an app permission policy</span></span>

<span data-ttu-id="f5eba-142">您可以使用 Microsoft Teams 系統管理中心來編輯原則，包括您建立的全域原則和自訂原則。</span><span class="sxs-lookup"><span data-stu-id="f5eba-142">You can use the Microsoft Teams admin center to edit a policy, including the global policy and custom policies that you create.</span></span>

1. <span data-ttu-id="f5eba-143">在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [Teams 應用程式 **]**  >  [權限原則 **]**。</span><span class="sxs-lookup"><span data-stu-id="f5eba-143">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="f5eba-144">按一下原則名稱左側來選取原則，然後按一下 [編輯 **]**。</span><span class="sxs-lookup"><span data-stu-id="f5eba-144">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="f5eba-145">從此處，進行您需要的變更。</span><span class="sxs-lookup"><span data-stu-id="f5eba-145">From here, make the changes that you want.</span></span> <span data-ttu-id="f5eba-146">您可以根據應用程式發行者來管理設定，並根據允許/封鎖設定來新增和移除應用程式。</span><span class="sxs-lookup"><span data-stu-id="f5eba-146">You can manage settings based on the app publisher and add and remove apps based on the allow/block setting.</span></span>
4. <span data-ttu-id="f5eba-147">按一下 [儲存 **]**。</span><span class="sxs-lookup"><span data-stu-id="f5eba-147">Click **Save**.</span></span>

## <a name="assign-a-custom-app-permission-policy-to-users"></a><span data-ttu-id="f5eba-148">將自訂應用程式權限原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="f5eba-148">Assign a custom app permission policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="manage-org-wide-app-settings-for-microsoft-365-government"></a><span data-ttu-id="f5eba-149">管理 Microsoft 365 政府版的全組織應用程式設定</span><span class="sxs-lookup"><span data-stu-id="f5eba-149">Manage org-wide app settings for Microsoft 365 Government</span></span>  

<span data-ttu-id="f5eba-150">在 Microsoft 365 政府版 - GCCH 和 Teams 的 DoD 部署中，瞭解協力廠商應用程式設定非常重要，這些設定是 GCCH 和 DoD 所特有的。</span><span class="sxs-lookup"><span data-stu-id="f5eba-150">In a Microsoft 365 Government - GCCH and DoD deployment of Teams, it's important to know the following about third-party app settings, which are unique to GCCH and DoD.</span></span>

<span data-ttu-id="f5eba-151">在 GCCH 和 DoD 中，所有協力廠商應用程式預設會封鎖。</span><span class="sxs-lookup"><span data-stu-id="f5eba-151">In GCCH and DoD, all third-party apps are blocked by default.</span></span> <span data-ttu-id="f5eba-152">此外，您會在 Microsoft Teams 系統管理中心的應用程式權限原則頁面上，看到以下關於管理第三方應用程式的說明。</span><span class="sxs-lookup"><span data-stu-id="f5eba-152">Additionally, you'll see the following note about managing third-party apps on the app permission policies page in the Microsoft Teams admin center.</span></span>

![GCCH 和 DoD 中的應用程式權限原則螢幕擷取畫面](media/app-permission-policies-gcc.png)

<span data-ttu-id="f5eba-154">使用全組織應用程式設定來控制使用者是否可以安裝第三方應用程式。</span><span class="sxs-lookup"><span data-stu-id="f5eba-154">Use org-wide app settings to control whether users can install third-party apps.</span></span> <span data-ttu-id="f5eba-155">全組織應用程式設定會控管所有使用者的行為，並覆寫指派給使用者的任何其他應用程式權限原則。</span><span class="sxs-lookup"><span data-stu-id="f5eba-155">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="f5eba-156">您可以使用這些原則來控制惡意或有問題的應用程式。</span><span class="sxs-lookup"><span data-stu-id="f5eba-156">You can use them to control malicious or problematic apps.</span></span>

1. <span data-ttu-id="f5eba-157">在 [權限原則 **]** 頁面上，選取 [全組織應用程式設定 **]**。</span><span class="sxs-lookup"><span data-stu-id="f5eba-157">On the **Permission policies** page, select **Org-wide app settings**.</span></span> <span data-ttu-id="f5eba-158">然後您就可以在面板中設定您要的設定。</span><span class="sxs-lookup"><span data-stu-id="f5eba-158">You can then configure the settings you want in the panel.</span></span>

    ![全組織應用程式設定的螢幕擷取畫面](media/app-permission-policies-gcc-org-wide.png)
    
2. <span data-ttu-id="f5eba-160">在 [第三方應用程式 **]** 下，關閉或開啟這些設定，以控制對第三方應用程式的存取權：</span><span class="sxs-lookup"><span data-stu-id="f5eba-160">Under **Third-party apps**, turn off or turn on these settings to control access to third-party apps:</span></span>

    - <span data-ttu-id="f5eba-161">**允許第三方應用程式**：這會控制使用者是否可以使用第三方應用程式。</span><span class="sxs-lookup"><span data-stu-id="f5eba-161">**Allow third-party apps**: This controls whether users can use third-party apps.</span></span> <span data-ttu-id="f5eba-162">如果您關閉此設定，您的使用者將無法安裝或使用任何第三方應用程式。</span><span class="sxs-lookup"><span data-stu-id="f5eba-162">If you turn off this setting, your users won't be able to install or use any third-party apps.</span></span> <span data-ttu-id="f5eba-163">在 Microsoft 365 政府 - GCCH 和 Teams DoD 部署中，此設定預設為關閉。</span><span class="sxs-lookup"><span data-stu-id="f5eba-163">In a Microsoft 365 Government - GCCH and DoD deployment of Teams, this setting is off by default.</span></span>
    - <span data-ttu-id="f5eba-164">**預設允許發行到商店的任何新第三方應用程式**：這會控制發佈至 Teams 應用程式商店的新第三方應用程式是否會自動在 Teams 中提供使用。</span><span class="sxs-lookup"><span data-stu-id="f5eba-164">**Allow any new third-party apps published to the store by default**: This controls whether new third-party apps that are published to the Teams app store become automatically available in Teams.</span></span> <span data-ttu-id="f5eba-165">您只能在允許第三方應用程式時設定此選項。</span><span class="sxs-lookup"><span data-stu-id="f5eba-165">You can only set this option if you allow third-party apps.</span></span>

3. <span data-ttu-id="f5eba-166">在 [封鎖的應用程式 **]** 下，新增您想要在組織中封鎖存取權的應用程式。</span><span class="sxs-lookup"><span data-stu-id="f5eba-166">Under **Blocked apps**, add the apps you want to block across your organization.</span></span> <span data-ttu-id="f5eba-167">在 Microsoft 365 政府版 - GCCH 和 Teams 的 DoD 部署中，所有協力廠商應用程式預設會新加到此清單。</span><span class="sxs-lookup"><span data-stu-id="f5eba-167">In a Microsoft 365 Government - GCCH and DoD deployment of Teams, all third-party apps are added to this list by default.</span></span> <span data-ttu-id="f5eba-168">針對您想要在組織中允許的任何第三方應用程式，請從此封鎖的應用程式清單中移除該應用程式。</span><span class="sxs-lookup"><span data-stu-id="f5eba-168">For any third-party app you want to allow in your organization, remove the app from this blocked apps list.</span></span> <span data-ttu-id="f5eba-169">在全組織封鎖某個應用程式時，會自動為所有使用者封鎖該應用程式，而無論任何應用程式權限原則中是否允許該應用程式。</span><span class="sxs-lookup"><span data-stu-id="f5eba-169">When you block an app org-wide, the app is automatically blocked for all your users, regardless of whether it's allowed in any app permission policies</span></span>
4. <span data-ttu-id="f5eba-170">按一下 [儲存 **]**，讓全組織應用程式設定生效。</span><span class="sxs-lookup"><span data-stu-id="f5eba-170">Click **Save** for org-wide app settings to take effect.</span></span>

<span data-ttu-id="f5eba-171">如稍早所提，若要允許第三方應用程式，您可以編輯並使用全域 (全組織預設值) 原則，或建立並指派自訂原則。</span><span class="sxs-lookup"><span data-stu-id="f5eba-171">As mentioned earlier, to allow third-party apps, you can either edit and use the global (Org-wide default) policy or create and assign custom policies.</span></span>

## <a name="faq"></a><span data-ttu-id="f5eba-172">常見問題集</span><span class="sxs-lookup"><span data-stu-id="f5eba-172">FAQ</span></span>

### <a name="working-with-app-permission-policies"></a><span data-ttu-id="f5eba-173">使用應用程式權限原則</span><span class="sxs-lookup"><span data-stu-id="f5eba-173">Working with app permission policies</span></span>

#### <a name="what-app-interactions-do-permission-policies-affect"></a><span data-ttu-id="f5eba-174">權限原則會影響哪些應用程式互動？</span><span class="sxs-lookup"><span data-stu-id="f5eba-174">What app interactions do permission policies affect?</span></span>
<span data-ttu-id="f5eba-175">權限原則會透過控制使用者的安裝、探索及互動，來控管應用程式的使用狀況。</span><span class="sxs-lookup"><span data-stu-id="f5eba-175">Permission policies govern app usage by controlling installation, discovery, and interaction for end users.</span></span> <span data-ttu-id="f5eba-176">系統管理員仍可以在 Microsoft Teams 系統管理中心中管理應用程式，而無論指派給他們的權限原則為何。</span><span class="sxs-lookup"><span data-stu-id="f5eba-176">Admins can still manage apps in the Microsoft Teams admin center regardless of the permission policies assigned to them.</span></span>

#### <a name="can-i-control-line-of-business-lob-apps"></a><span data-ttu-id="f5eba-177">我可以控制企業營運 (LOB) 應用程式嗎？</span><span class="sxs-lookup"><span data-stu-id="f5eba-177">Can I control line of business (LOB) apps?</span></span>
<span data-ttu-id="f5eba-178">是的，您可以使用應用程式權限原則來控制自訂 (LOB) 應用程式的推出和發佈。</span><span class="sxs-lookup"><span data-stu-id="f5eba-178">Yes, you can use app permission policies to control the rollout and distribution of custom (LOB) apps.</span></span> <span data-ttu-id="f5eba-179">您可以建立自訂原則或編輯全域原則，以根據組織的需求來允許或封鎖自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="f5eba-179">You can create a custom policy or edit the global policy to allow or block custom apps based on the needs of your organization.</span></span>

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a><span data-ttu-id="f5eba-180">應用程式權限原則與釘選的應用程式和應用程式設定原則有何關聯？</span><span class="sxs-lookup"><span data-stu-id="f5eba-180">How do app permission policies relate to pinned apps and app setup policies?</span></span>

<span data-ttu-id="f5eba-181">您可以將應用程式設定原則與應用程式權限原則搭配使用。</span><span class="sxs-lookup"><span data-stu-id="f5eba-181">You can use app setup policies together with app permission policies.</span></span> <span data-ttu-id="f5eba-182">系統會為使用者從已啟用的應用程式集合中選取預先釘選的應用程式。</span><span class="sxs-lookup"><span data-stu-id="f5eba-182">Pre-pinned apps are selected from the set of enabled apps for a user.</span></span> <span data-ttu-id="f5eba-183">此外，如果使用者的應用程式權限原則會封鎖其應用程式設定原則中的應用程式，該應用程式就不會顯示在 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="f5eba-183">Additionally, if a user has an app permission policy that blocks an app in their app setup policy, that app won't appear in Teams.</span></span>

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps"></a><span data-ttu-id="f5eba-184">我可以使用應用程式權限原則來限制上傳自訂應用程式嗎？</span><span class="sxs-lookup"><span data-stu-id="f5eba-184">Can I use app permission policies to restrict uploading custom apps?</span></span>

<span data-ttu-id="f5eba-185">您可以使用 [管理應用程式 **]** 頁面上的全組織應用程式設定，或應用程式設定原則來限制上傳組織的自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="f5eba-185">You can use org-wide settings on the **Manage apps** page, or app setup policies to restrict uploading custom apps for your organization.</span></span>  

<span data-ttu-id="f5eba-186">若要限制特定使用者上傳自訂應用程式，請使用自訂的應用程式原則。</span><span class="sxs-lookup"><span data-stu-id="f5eba-186">To restrict specific users from uploading custom apps, use custom app policies.</span></span> <span data-ttu-id="f5eba-187">若要深入了解，請參閱[在 Teams 中管理自訂應用程式原則和設定](teams-custom-app-policies-and-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="f5eba-187">To learn more, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a><span data-ttu-id="f5eba-188">封鎖某個應用程式是否會套用至 Teams 行動裝置用戶端？</span><span class="sxs-lookup"><span data-stu-id="f5eba-188">Does blocking an app apply to Teams mobile clients?</span></span>

<span data-ttu-id="f5eba-189">是的，當您封鎖某個應用程式，會於所有 Teams 用戶端間封鎖該應用程式。</span><span class="sxs-lookup"><span data-stu-id="f5eba-189">Yes, when you block an app, that app is blocked across all Teams clients.</span></span>  

### <a name="user-experience"></a><span data-ttu-id="f5eba-190">使用者體驗</span><span class="sxs-lookup"><span data-stu-id="f5eba-190">User experience</span></span>

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a><span data-ttu-id="f5eba-191">當某個應用程式遭到封鎖，使用者會遇到什麼情況？</span><span class="sxs-lookup"><span data-stu-id="f5eba-191">What does a user experience when an app is blocked?</span></span>

<span data-ttu-id="f5eba-192">使用者無法與封鎖的應用程式或其功能 (例如 bot、索引標籤和傳訊擴充功能) 互動。</span><span class="sxs-lookup"><span data-stu-id="f5eba-192">Users can't interact with a blocked app or its capabilities, such bots, tabs, and messaging extensions.</span></span> <span data-ttu-id="f5eba-193">在共用的內容 (例如小組或群組聊天) 中，bot 仍然可以傳送訊息給該內容的所有參與者。</span><span class="sxs-lookup"><span data-stu-id="f5eba-193">In a shared context, such as a team or group chat, bots can still send messages to all participants of that context.</span></span> <span data-ttu-id="f5eba-194">當某個應用程式遭到封鎖時，Teams 會向使用者指出。</span><span class="sxs-lookup"><span data-stu-id="f5eba-194">Teams indicates to the user when an app is blocked.</span></span>

<span data-ttu-id="f5eba-195">例如，當某個應用程式遭到封鎖時，使用者就無法執行下列任何一項動作：</span><span class="sxs-lookup"><span data-stu-id="f5eba-195">For example, when an app is blocked, users can't do any of the following:</span></span>

- <span data-ttu-id="f5eba-196">自行新增應用程式或將應用程式新增至聊天或小組</span><span class="sxs-lookup"><span data-stu-id="f5eba-196">Add the app personally or to a chat or team</span></span>
- <span data-ttu-id="f5eba-197">傳送訊息至應用程式的 bot</span><span class="sxs-lookup"><span data-stu-id="f5eba-197">Send messages to the app’s bot</span></span>
- <span data-ttu-id="f5eba-198">執行會將資訊傳送回應用程式的按鈕動作，例如，可採取動作的郵件</span><span class="sxs-lookup"><span data-stu-id="f5eba-198">Perform button actions that send information back to the app, such as actionable messages</span></span>  
- <span data-ttu-id="f5eba-199">檢視應用程式的索引標籤</span><span class="sxs-lookup"><span data-stu-id="f5eba-199">View the app’s tab</span></span>
- <span data-ttu-id="f5eba-200">設定連接器以接收通知</span><span class="sxs-lookup"><span data-stu-id="f5eba-200">Set up connectors to receive notifications</span></span>
- <span data-ttu-id="f5eba-201">使用應用程式的傳訊擴充功能</span><span class="sxs-lookup"><span data-stu-id="f5eba-201">Use the app’s messaging extension</span></span>

<span data-ttu-id="f5eba-202">允許舊版入口網站在組織層級控制應用程式，這表示當某個應用程式遭到封鎖時，系統會為組織中的所有使用者封鎖該應用程式。</span><span class="sxs-lookup"><span data-stu-id="f5eba-202">The legacy portal allowed controlling apps at the organization level, which means when an app is blocked, it's blocked for all users in the organization.</span></span> <span data-ttu-id="f5eba-203">在 [管理應用程式[]](manage-apps.md) 頁面上封鎖應用程式的運作方式完全相同。</span><span class="sxs-lookup"><span data-stu-id="f5eba-203">Blocking an app on the [Manage apps](manage-apps.md) page works exactly the same way.</span></span>

<span data-ttu-id="f5eba-204">針對指派給特定使用者的應用程式權限原則，如果先允許具有 bot 或連接器的應用程式然後封鎖它，並且接著僅在共用的內容中對部分使用者允許該應用程式，則不具有該應用程式權限的群組聊天或頻道成員，可以查看由 bot 或連接器所張貼的訊息歷程記錄和訊息，但是無法與其互動。</span><span class="sxs-lookup"><span data-stu-id="f5eba-204">For app permission policies assigned to specific users, if an app with bot or connector capability was allowed and then blocked, and if the app is then allowed only for some users in a shared context, members of a group chat or channel that don't have permission to that app can see the message history and messages that were posted by the bot or connector, but can't interact with it.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f5eba-205">相關主題</span><span class="sxs-lookup"><span data-stu-id="f5eba-205">Related topics</span></span>

[<span data-ttu-id="f5eba-206">在 Teams 中管理應用程式的設定</span><span class="sxs-lookup"><span data-stu-id="f5eba-206">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="f5eba-207">在 Teams 中將原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="f5eba-207">Assign policies to your users in Teams</span></span>](assign-policies.md)
