---
title: 在 Microsoft 團隊系統管理中心管理您的應用程式
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: 瞭解如何在 Microsoft 團隊系統管理中心的 [管理應用程式] 頁面上管理您的團隊應用程式
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 532129792dd35a2b016510094f1b08beade1b32a
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/03/2020
ms.locfileid: "43136843"
---
<a name="manage-your-apps-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="24b59-103">在 Microsoft 團隊系統管理中心管理您的應用程式</span><span class="sxs-lookup"><span data-stu-id="24b59-103">Manage your apps in the Microsoft Teams admin center</span></span>
======================================================

<span data-ttu-id="24b59-104">做為管理員，Microsoft [團隊管理中心] 中的 [**管理應用**程式] 頁面是您在組織的應用程式目錄中查看和管理所有團隊應用程式的位置。</span><span class="sxs-lookup"><span data-stu-id="24b59-104">As an admin, the **Manage apps** page in the Microsoft Teams admin center is where you view and manage all Teams apps in your organization's app catalog.</span></span> <span data-ttu-id="24b59-105">在這裡，您可以查看應用程式的組織層級狀態和屬性、將新的自訂應用程式上傳到您的租使用者應用程式目錄、封鎖或允許組織階層的應用程式，以及管理整個組織的應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="24b59-105">Here, you can see the org-level status and properties of apps, upload new custom apps to your tenant app catalog, block or allow apps at the org level, and manage org-wide app settings.</span></span>

<span data-ttu-id="24b59-106">[**管理應用程式**] 頁面可讓您查看租使用者目錄中所有可用的應用程式，為您提供所需的資訊，讓您決定要允許或封鎖整個組織的哪些應用程式。</span><span class="sxs-lookup"><span data-stu-id="24b59-106">The **Manage apps** page gives you a view into all available apps in your tenant catalog, providing you with the information you need to decide which apps to allow or block across your organization.</span></span> <span data-ttu-id="24b59-107">接著，您可以使用[應用程式許可權原則](teams-app-permission-policies.md)、[應用程式設定原則](teams-app-setup-policies.md)，以及[自訂的 app 原則和設定](teams-custom-app-policies-and-settings.md)，為貴組織中的特定使用者設定 app 體驗。</span><span class="sxs-lookup"><span data-stu-id="24b59-107">You can then use [app permission policies](teams-app-permission-policies.md), [app setup policies](teams-app-setup-policies.md), and [custom app policies and settings](teams-custom-app-policies-and-settings.md) to configure the app experience for specific users in your organization.</span></span>

<span data-ttu-id="24b59-108">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app** > **管理應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="24b59-108">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="24b59-109">您必須是全域系統管理員或團隊服務系統管理員，才能存取該頁面。</span><span class="sxs-lookup"><span data-stu-id="24b59-109">You must be a global admin or Teams service admin to access the page.</span></span>

## <a name="view-apps-in-your-tenant-app-catalog"></a><span data-ttu-id="24b59-110">在您的租使用者應用程式目錄中查看應用程式</span><span class="sxs-lookup"><span data-stu-id="24b59-110">View apps in your tenant app catalog</span></span>

<span data-ttu-id="24b59-111">您可以查看租使用者應用程式目錄中的每個應用程式，包括下列每個應用程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="24b59-111">You can view every app in your tenant app catalog including the following information about each app.</span></span>

![[受管理的應用程式] 頁面的螢幕擷取畫面](media/manage-apps.png)

- <span data-ttu-id="24b59-113">**Name （名稱**）：應用程式名稱。</span><span class="sxs-lookup"><span data-stu-id="24b59-113">**Name**: The app name.</span></span> <span data-ttu-id="24b59-114">按一下應用程式名稱，查看該應用程式的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="24b59-114">Click the app name to see more information about the app.</span></span> <span data-ttu-id="24b59-115">這包括應用程式的描述、是否允許或封鎖、版本、套用至應用程式的類別、認證狀態、支援的功能，以及應用程式識別碼。</span><span class="sxs-lookup"><span data-stu-id="24b59-115">This includes a description of the app, whether it's allowed or blocked, version, categories that apply to the app, certification status, supported capabilities, and app ID.</span></span> <span data-ttu-id="24b59-116">以下是一個範例：</span><span class="sxs-lookup"><span data-stu-id="24b59-116">Here's an example:</span></span><br><span data-ttu-id="24b59-117"> 
![應用程式的 [應用程式詳細資料] 頁面的螢幕擷取畫面](media/manage-apps-app-details.png)</span><span class="sxs-lookup"><span data-stu-id="24b59-117"> 
![Screenshot of the apps details page for an app](media/manage-apps-app-details.png)</span></span>
- <span data-ttu-id="24b59-118">**認證**：如果 app 已透過認證，您就會看到**Microsoft 365 認證**或**發行商認證**。</span><span class="sxs-lookup"><span data-stu-id="24b59-118">**Certification**: If the app has gone through certification, you'll see either **Microsoft 365 certified** or **Publisher attestation**.</span></span> <span data-ttu-id="24b59-119">按一下連結以查看 app 的認證詳細資料。</span><span class="sxs-lookup"><span data-stu-id="24b59-119">Click the link to view certification details for the app.</span></span> <span data-ttu-id="24b59-120">如果您看到**--**「」，表示沒有 app 的認證資訊。</span><span class="sxs-lookup"><span data-stu-id="24b59-120">If you see "**--**", we don't have certification information for the app.</span></span> <span data-ttu-id="24b59-121">若要深入瞭解團隊中的認證應用程式，請參閱[Microsoft 365 App 認證計畫](https://docs.microsoft.com/teams-app-certification/all-apps)。</span><span class="sxs-lookup"><span data-stu-id="24b59-121">To learn more about certified apps in Teams, read [Microsoft 365 App Certification program](https://docs.microsoft.com/teams-app-certification/all-apps).</span></span>  
- <span data-ttu-id="24b59-122">[**類別**]：適用于 app 的類別。</span><span class="sxs-lookup"><span data-stu-id="24b59-122">**Categories**: Categories that apply to the app.</span></span>
- <span data-ttu-id="24b59-123">**App 狀態**：組織階層的 app 狀態，可能是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="24b59-123">**App status**: Status of the app at the org level, which can be one of the following:</span></span>
    - <span data-ttu-id="24b59-124">**允許**：應用程式可供貴組織中的所有使用者使用。</span><span class="sxs-lookup"><span data-stu-id="24b59-124">**Allowed**: The app is available for all users in your organization.</span></span>
    - <span data-ttu-id="24b59-125">已**封鎖**：應用程式遭到封鎖，且無法供貴組織中的任何使用者使用。</span><span class="sxs-lookup"><span data-stu-id="24b59-125">**Blocked**: The app is blocked and not available for any users in your organization.</span></span><br>
<span data-ttu-id="24b59-126">請務必注意，此資料行代表原在**整個組織結構設定**窗格中之 app 的「允許」和「封鎖」狀態。</span><span class="sxs-lookup"><span data-stu-id="24b59-126">It's important to know that this column represents the allowed and blocked status of apps that were formerly on the **Org-wide settings** pane.</span></span> <span data-ttu-id="24b59-127">您現在可以在 [**管理應用程式**] 頁面上的整個組織結構中查看、封鎖及允許 app。</span><span class="sxs-lookup"><span data-stu-id="24b59-127">You now view, block, and allow apps at the org-wide on the **Manage apps** page.</span></span> 
- <span data-ttu-id="24b59-128">**版本**： App 版本。</span><span class="sxs-lookup"><span data-stu-id="24b59-128">**Version**: App version.</span></span>

<span data-ttu-id="24b59-129">若要在表格中查看您想要的資訊，請按一下右上角的 [**編輯欄**]，在表格中新增或移除欄。</span><span class="sxs-lookup"><span data-stu-id="24b59-129">To see the information that you want in the table, click **Edit Column** in the upper-right corner to add or remove columns to the table.</span></span>

## <a name="upload-a-new-app"></a><span data-ttu-id="24b59-130">上傳新的應用程式</span><span class="sxs-lookup"><span data-stu-id="24b59-130">Upload a new app</span></span>

<span data-ttu-id="24b59-131">您可以使用您的 [應用程式目錄] 來測試及發佈專為貴組織建立的業務線應用程式。</span><span class="sxs-lookup"><span data-stu-id="24b59-131">You can use your app catalog to test and distribute line-of-business applications that are built specifically for your organization.</span></span> <span data-ttu-id="24b59-132">團隊應用程式套件是使用[團隊 App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)建立的。</span><span class="sxs-lookup"><span data-stu-id="24b59-132">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="24b59-133">當您有應用程式套件時，您可以將它新增到您的 [應用程式目錄]。</span><span class="sxs-lookup"><span data-stu-id="24b59-133">When you have the app package, you can add it to the your app catalog.</span></span> <span data-ttu-id="24b59-134">雖然貴組織中的所有使用者都可以查看應用程式目錄，但只有全域管理員和團隊服務系統管理員可以發佈及管理它。</span><span class="sxs-lookup"><span data-stu-id="24b59-134">While all users in your organization can view the app catalog, only global admins and Teams service admins can publish and manage it.</span></span>

<span data-ttu-id="24b59-135">若要將新的自訂應用程式上傳到您的租使用者應用程式目錄，請按一下 **[上傳新應用程式**]，以 .zip 格式上傳您的</span><span class="sxs-lookup"><span data-stu-id="24b59-135">To upload a new custom app to your tenant app catalog, click **Upload new app** to upload your app package in .zip format.</span></span> <span data-ttu-id="24b59-136">應用程式在上傳後不會醒目提示，因此您需要搜尋您的應用程式目錄來尋找它。</span><span class="sxs-lookup"><span data-stu-id="24b59-136">The app isn't highlighted after it's uploaded so you'll need to search your app catalog to find it.</span></span>

<span data-ttu-id="24b59-137">若要在上傳應用程式後進行更新，請在 [**管理應用**程式] 頁面上的應用程式清單中，按一下應用程式名稱，然後按一下 [**更新**]。</span><span class="sxs-lookup"><span data-stu-id="24b59-137">To update an app after it's uploaded, in the list of apps on the **Manage apps** page, click the app name, and then click **Update**.</span></span> <span data-ttu-id="24b59-138">這麼做會取代應用程式目錄中的現有應用程式，以及所有應用程式許可權原則，以及 app 設定原則，都會針對更新的應用程式繼續執行。</span><span class="sxs-lookup"><span data-stu-id="24b59-138">Doing this replaces the existing app in your app catalog and all app permission policies and app setup policies remain enforced for the updated app.</span></span>

<span data-ttu-id="24b59-139">若要深入瞭解，請參閱[在團隊中管理您的商務用應用程式](manage-your-lob-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="24b59-139">To learn more, see [Manage your line-of-business apps in Teams](manage-your-lob-apps.md).</span></span>

## <a name="allow-and-block-apps"></a><span data-ttu-id="24b59-140">允許及封鎖應用程式</span><span class="sxs-lookup"><span data-stu-id="24b59-140">Allow and block apps</span></span>

<span data-ttu-id="24b59-141">[**管理應用程式**] 頁面是您在組織階層允許或封鎖個別 app 的位置。</span><span class="sxs-lookup"><span data-stu-id="24b59-141">The **Manage apps** page is where you allow or block individual apps at the org level.</span></span> <span data-ttu-id="24b59-142">它會顯示每個可用的 app 及其目前的組織層級 app 狀態。</span><span class="sxs-lookup"><span data-stu-id="24b59-142">It shows every available app and its current org-level app status.</span></span> <span data-ttu-id="24b59-143">（封鎖及允許組織階層的 app 已從**整個組織範圍的應用程式設定**窗格移至這裡。）</span><span class="sxs-lookup"><span data-stu-id="24b59-143">(Blocking and allowing apps at the org level has moved from the **Org-wide app settings** pane to here.)</span></span>

<span data-ttu-id="24b59-144">若要允許或封鎖應用程式，請選取它，然後按一下 [**允許**] 或 [**封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="24b59-144">To allow or block an app, select it, and then click **Allow** or **Block**.</span></span> <span data-ttu-id="24b59-145">當您封鎖 app 時，所有與該 app 的互動都會停用，而且該 app 不會出現在小組中您組織中的任何使用者。</span><span class="sxs-lookup"><span data-stu-id="24b59-145">When you block an app, all interactions with that app are disabled and the app doesn't appear in Teams for any users in your organization.</span></span>

<span data-ttu-id="24b59-146">當您封鎖或允許 [**管理應用程式**] 頁面上的應用程式時，該應用程式會遭到封鎖，或您組織中的所有使用者都能使用該 app。</span><span class="sxs-lookup"><span data-stu-id="24b59-146">When you block or allow an app on the **Manage apps** page, that app is blocked or allowed for all users in your organization.</span></span>  <span data-ttu-id="24b59-147">當您在小組 app 許可權原則中封鎖或允許應用程式時，系統會封鎖或允許指派該原則的使用者。</span><span class="sxs-lookup"><span data-stu-id="24b59-147">When you block or allow an app in a Teams app permission policy, it's blocked or allowed for users who are assigned that policy.</span></span> <span data-ttu-id="24b59-148">若要讓使用者能夠安裝任何 app 並與之互動，您必須在 [**管理應用程式**] 頁面上，或已指派給使用者的 app 許可權原則中，允許該應用程式位於組織層級。</span><span class="sxs-lookup"><span data-stu-id="24b59-148">For a user to be able to install and interact with any app, you must allow the app at the org level on the **Manage apps** page and in the app permission policy that's assigned to the user.</span></span>

## <a name="manage-org-wide-app-settings"></a><span data-ttu-id="24b59-149">管理整個組織內的應用程式設定</span><span class="sxs-lookup"><span data-stu-id="24b59-149">Manage org-wide app settings</span></span>

<span data-ttu-id="24b59-150">使用整個組織的 app 設定來控制使用者是否可以安裝協力廠商應用程式，以及使用者是否可以上傳或與您組織中的自訂應用程式互動。</span><span class="sxs-lookup"><span data-stu-id="24b59-150">Use org-wide app settings to control whether users can install third-party apps and whether users can upload or interact with custom  apps in your organization.</span></span> <span data-ttu-id="24b59-151">全組織式應用程式設定會控制所有使用者的行為，並覆寫指派給使用者的任何其他應用程式許可權原則。</span><span class="sxs-lookup"><span data-stu-id="24b59-151">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="24b59-152">您可以使用它們來控制惡意或有問題的 app。</span><span class="sxs-lookup"><span data-stu-id="24b59-152">You can use them to control malicious or problematic apps.</span></span>

1. <span data-ttu-id="24b59-153">在 [**管理應用程式**] 頁面上，選取 [**全組織式應用程式設定**]。</span><span class="sxs-lookup"><span data-stu-id="24b59-153">On the **Manage apps** page, select **Org-wide app settings**.</span></span> <span data-ttu-id="24b59-154">接著，您可以在面板中設定您想要的設定。</span><span class="sxs-lookup"><span data-stu-id="24b59-154">You can then configure the settings you want in the panel.</span></span>

    ![整個組織內的應用程式設定的螢幕擷取畫面](media/manage-apps-org-wide-app-settings.png)
    
2. <span data-ttu-id="24b59-156">在**協力廠商應用程式**下，關閉或開啟這些設定以控制對協力廠商應用程式的存取：</span><span class="sxs-lookup"><span data-stu-id="24b59-156">Under **Third-party apps**, turn off or turn on these settings to control access to third-party apps:</span></span>

    - <span data-ttu-id="24b59-157">**允許團隊中的協力廠商應用程式**：這可控制使用者是否可以使用協力廠商應用程式。</span><span class="sxs-lookup"><span data-stu-id="24b59-157">**Allow third-party apps in Teams**: This controls whether users can use third-party apps.</span></span> <span data-ttu-id="24b59-158">如果您關閉此設定，您的使用者將無法安裝或使用任何協力廠商應用程式。</span><span class="sxs-lookup"><span data-stu-id="24b59-158">If you turn off this setting, your users won't be able to install or use any third-party apps.</span></span> <span data-ttu-id="24b59-159">針對您允許的應用程式，狀態會顯示為 [允許]，**但已停用整個組織**結構。</span><span class="sxs-lookup"><span data-stu-id="24b59-159">For apps that you allowed, the status shows as **Allowed but disabled org-wide**.</span></span>              

        > [!NOTE]
        > <span data-ttu-id="24b59-160">在 Microsoft 365 政府版團隊部署中，[**允許團隊中的協力廠商應用程式**] 設定預設為關閉。</span><span class="sxs-lookup"><span data-stu-id="24b59-160">In a Microsoft 365 Government - GCC deployment of Teams, the **Allow third-party apps in Teams** setting is off by default.</span></span>

        <span data-ttu-id="24b59-161">當 [**允許團隊中的協力廠商應用程式**關閉] 時，系統會停用[傳出 webhooks](https://docs.microsoft.com/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) ，這表示使用者無法建立。</span><span class="sxs-lookup"><span data-stu-id="24b59-161">When **Allow third-party apps in Teams** is off, [outgoing webhooks](https://docs.microsoft.com/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) are disabled, which means that users can't create them.</span></span> <span data-ttu-id="24b59-162">當此設定為 [開啟] 時，無論使用者應用程式許可權原則中的設定為開啟或關閉，所有使用者都能啟用外寄 webhooks。</span><span class="sxs-lookup"><span data-stu-id="24b59-162">When this setting is on, outgoing webhooks are enabled for all users regardless of whether the setting is on or off in the users' app permission policy.</span></span>
    - <span data-ttu-id="24b59-163">**允許預設發佈至商店的任何新的協力廠商應用程式**：這會控制發佈至 [小組] 應用程式商店的新的協力廠商應用程式是否會自動在小組中提供。</span><span class="sxs-lookup"><span data-stu-id="24b59-163">**Allow any new third-party apps published to the store by default**: This controls whether new third-party apps that are published to the Teams app store become automatically available in Teams.</span></span> <span data-ttu-id="24b59-164">如果您允許協力廠商應用程式，則只能設定此選項。</span><span class="sxs-lookup"><span data-stu-id="24b59-164">You can only set this option if you allow third-party apps.</span></span>

3. <span data-ttu-id="24b59-165">在 [**自訂應用程式**] 底下，關閉或開啟 [**允許與自訂應用程式互動**]。</span><span class="sxs-lookup"><span data-stu-id="24b59-165">Under **Custom apps**, turn off or turn on **Allow interaction with custom apps**.</span></span> <span data-ttu-id="24b59-166">這個設定控制使用者是否能與自訂 app 互動。</span><span class="sxs-lookup"><span data-stu-id="24b59-166">This setting controls whether users can interact with custom apps.</span></span> <span data-ttu-id="24b59-167">若要深入瞭解，請參閱[管理團隊中的自訂應用程式原則和設定](teams-custom-app-policies-and-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="24b59-167">To learn more, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>
4. <span data-ttu-id="24b59-168">按一下 [**儲存**以組織範圍內的應用程式設定] 生效。</span><span class="sxs-lookup"><span data-stu-id="24b59-168">Click **Save** for org-wide app settings to take effect.</span></span>

## <a name="related-topics"></a><span data-ttu-id="24b59-169">相關主題</span><span class="sxs-lookup"><span data-stu-id="24b59-169">Related topics</span></span>

- [<span data-ttu-id="24b59-170">在 Teams 中的應用程式系統管理設定</span><span class="sxs-lookup"><span data-stu-id="24b59-170">Admin settings for apps in Teams</span></span>](admin-settings.md)
