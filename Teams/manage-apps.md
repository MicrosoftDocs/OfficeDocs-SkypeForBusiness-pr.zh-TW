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
ms.reviewer: vaibhava
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: 瞭解如何在 Microsoft 團隊系統管理中心的 [管理應用程式] 頁面上管理您的團隊應用程式
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 23ff7cc90d30dc931b0677ce5ec5aa8db98981fb
ms.sourcegitcommit: e0e089f0ab217d920e128377af653f7dbfdedacf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/20/2020
ms.locfileid: "46818182"
---
<a name="manage-your-apps-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="eb2e0-103">在 Microsoft 團隊系統管理中心管理您的應用程式</span><span class="sxs-lookup"><span data-stu-id="eb2e0-103">Manage your apps in the Microsoft Teams admin center</span></span>
======================================================

<span data-ttu-id="eb2e0-104">做為管理員，Microsoft [團隊管理中心] 中的 [管理應用程式] 頁面是您在其中查看及管理組織的所有團隊應用程式的位置。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-104">As an admin, the Manage apps page in the Microsoft Teams admin center is where you view and manage all Teams apps for your organization.</span></span> <span data-ttu-id="eb2e0-105">在這裡，您可以查看應用程式的組織層級狀態和屬性、核准或上傳新的自訂應用程式到貴組織的 app 商店、封鎖或允許應用程式在組織階層、購買服務的協力廠商應用程式，以及管理整個組織的應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-105">Here, you can see the org-level status and properties of apps, approve or upload new custom apps to your organization's app store, block or allow apps at the org level, purchase services for third-party apps, and manage org-wide app settings.</span></span>

<span data-ttu-id="eb2e0-106">[管理應用程式] 頁面可讓您查看所有可用的應用程式，為您提供決定要允許或封鎖整個組織的 app 所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-106">The Manage apps page gives you a view into all available apps, providing you with the information you need to decide which apps to allow or block across your organization.</span></span> <span data-ttu-id="eb2e0-107">接著，您可以使用 [應用程式許可權原則](teams-app-permission-policies.md)、 [應用程式設定原則](teams-app-setup-policies.md)，以及 [自訂的 app 原則和設定](teams-custom-app-policies-and-settings.md) ，為貴組織中的特定使用者設定 app 體驗。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-107">You can then use [app permission policies](teams-app-permission-policies.md), [app setup policies](teams-app-setup-policies.md), and [custom app policies and settings](teams-custom-app-policies-and-settings.md) to configure the app experience for specific users in your organization.</span></span>

<span data-ttu-id="eb2e0-108">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**  >  **管理應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-108">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="eb2e0-109">您必須是全域系統管理員或團隊服務系統管理員，才能存取該頁面。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-109">You must be a global admin or Teams service admin to access the page.</span></span>

> [!NOTE]
> <span data-ttu-id="eb2e0-110">[管理應用程式] 頁面尚無法在 Microsoft 365 政府社區中使用 (GCC) 小組部署。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-110">The Manage apps page isn't available yet in Microsoft 365 Government Community Cloud (GCC) deployments of Teams.</span></span>

## <a name="view-apps"></a><span data-ttu-id="eb2e0-111">查看應用程式</span><span class="sxs-lookup"><span data-stu-id="eb2e0-111">View apps</span></span>

<span data-ttu-id="eb2e0-112">您可以查看每個應用程式，包括下列每個應用程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-112">You can view every app including the following information about each app.</span></span>

![[受管理的應用程式] 頁面的螢幕擷取畫面](media/manage-apps.png)

- <span data-ttu-id="eb2e0-114">**Name （名稱**）：應用程式名稱。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-114">**Name**: The app name.</span></span> <span data-ttu-id="eb2e0-115">按一下應用程式名稱，查看該應用程式的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-115">Click the app name to see more information about the app.</span></span> <span data-ttu-id="eb2e0-116">這包括應用程式的描述、是否允許或封鎖、版本、套用至應用程式的類別、認證狀態、支援的功能，以及應用程式識別碼。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-116">This includes a description of the app, whether it's allowed or blocked, version, categories that apply to the app, certification status, supported capabilities, and app ID.</span></span> <span data-ttu-id="eb2e0-117">以下是一個範例：</span><span class="sxs-lookup"><span data-stu-id="eb2e0-117">Here's an example:</span></span>

  ![應用程式的 [應用程式詳細資料] 頁面的螢幕擷取畫面](media/manage-apps-app-details.png)
  
- <span data-ttu-id="eb2e0-119">**認證**：如果 app 已透過認證，您就會看到 **Microsoft 365 認證** 或 **發行商認證**。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-119">**Certification**: If the app has gone through certification, you'll see either **Microsoft 365 certified** or **Publisher attestation**.</span></span> <span data-ttu-id="eb2e0-120">按一下連結以查看 app 的認證詳細資料。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-120">Click the link to view certification details for the app.</span></span> <span data-ttu-id="eb2e0-121">如果您看到「」 **--** ，表示沒有 app 的認證資訊。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-121">If you see "**--**", we don't have certification information for the app.</span></span> <span data-ttu-id="eb2e0-122">若要深入瞭解團隊中的認證應用程式，請參閱 [Microsoft 365 App 認證計畫](https://docs.microsoft.com/teams-app-certification/all-apps)。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-122">To learn more about certified apps in Teams, read [Microsoft 365 App Certification program](https://docs.microsoft.com/teams-app-certification/all-apps).</span></span>  
- <span data-ttu-id="eb2e0-123">**Publisher**：發行者的名稱。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-123">**Publisher**: Name of the publisher.</span></span>
- <span data-ttu-id="eb2e0-124">**發佈狀態**：自訂應用程式的發佈狀態。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-124">**Publishing status**: Publishing status of custom apps.</span></span>
- <span data-ttu-id="eb2e0-125">**狀態**：組織階層的 app 狀態，可以是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="eb2e0-125">**Status**: Status of the app at the org level, which can be one of the following:</span></span>

    - <span data-ttu-id="eb2e0-126">**允許**：應用程式可供貴組織中的所有使用者使用。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-126">**Allowed**: The app is available for all users in your organization.</span></span>
    
    - <span data-ttu-id="eb2e0-127">已**封鎖**：應用程式遭到封鎖，且無法供貴組織中的任何使用者使用。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-127">**Blocked**: The app is blocked and not available for any users in your organization.</span></span>
    
    - <span data-ttu-id="eb2e0-128">已**封鎖整個組織**結構：應用程式在整個組織內的應用程式設定中遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-128">**Blocked org-wide**: The app is blocked in org-wide app settings.</span></span>
    
      <span data-ttu-id="eb2e0-129">請務必注意，此資料行代表原在 **整個組織結構設定** 窗格中之 app 的「允許」和「封鎖」狀態。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-129">It's important to know that this column represents the allowed and blocked status of apps that were formerly on the **Org-wide settings** pane.</span></span> <span data-ttu-id="eb2e0-130">您現在可以在 [ **管理應用程式** ] 頁面上的整個組織結構中查看、封鎖及允許 app。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-130">You now view, block, and allow apps at the org-wide on the **Manage apps** page.</span></span> 
- <span data-ttu-id="eb2e0-131">**授權**：指出 app 是否提供軟體作為服務 (SaaS) 訂閱以進行購買。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-131">**Licenses**: Indicates whether an app offers a Software as a Service (SaaS) subscription for purchase.</span></span> <span data-ttu-id="eb2e0-132">此欄僅適用于協力廠商應用程式。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-132">This column applies only to third-party apps.</span></span> <span data-ttu-id="eb2e0-133">每個協力廠商應用程式將會有下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="eb2e0-133">Each third-party app will have one of the following values:</span></span>
    - <span data-ttu-id="eb2e0-134">[**立即購買**]： App 提供 SaaS 訂閱，且可供購買。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-134">**Purchase now**: The app offers a SaaS subscription and is available to purchase.</span></span>  
    - <span data-ttu-id="eb2e0-135">已**購買**： App 提供 SaaS 訂閱，且您已為其購買授權。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-135">**Purchased**: The app offers a SaaS subscription and you've purchased licenses for it.</span></span>
    - <span data-ttu-id="eb2e0-136">**--**：應用程式不會提供 SaaS 訂閱。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-136">**- -**: The app doesn't offer a SaaS subscription.</span></span>
- <span data-ttu-id="eb2e0-137">**自訂 app**：應用程式是否為自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-137">**Custom app**: Whether the app is a custom app.</span></span>
- <span data-ttu-id="eb2e0-138">[**類別**]：適用于 app 的類別。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-138">**Categories**: Categories that apply to the app.</span></span>
- <span data-ttu-id="eb2e0-139">**版本**： App 版本。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-139">**Version**: App version.</span></span>

<span data-ttu-id="eb2e0-140">若要在表格中查看您想要的資訊，請按一下右上角的 [ **編輯欄** ]，在表格中新增或移除欄。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-140">To see the information that you want in the table, click **Edit Column** in the upper-right corner to add or remove columns to the table.</span></span>

## <a name="publish-a-custom-app-to-your-organizations-app-store"></a><span data-ttu-id="eb2e0-141">將自訂應用程式發佈到貴組織的 app store</span><span class="sxs-lookup"><span data-stu-id="eb2e0-141">Publish a custom app to your organization's app store</span></span>

<span data-ttu-id="eb2e0-142">使用 [管理應用程式] 頁面，發佈專為貴組織建立的應用程式。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-142">Use the Manage apps page to publish apps that are built specifically for your organization.</span></span> <span data-ttu-id="eb2e0-143">發佈自訂應用程式之後，您組織的 app store 中的使用者就可以使用它。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-143">After you publish a custom app, it's available to users in your organization's app store.</span></span> <span data-ttu-id="eb2e0-144">您可以透過兩種方式將自訂應用程式發佈到貴組織的 app store。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-144">There are two ways to publish a custom app to your organization's app store.</span></span> <span data-ttu-id="eb2e0-145">您使用的方式取決於您取得 app 的方式。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-145">The way that you use depends on how you get the app.</span></span>

- <span data-ttu-id="eb2e0-146">[核准自訂應用程式](#approve-a-custom-app)：如果開發人員使用小組 APP 提交 API 直接將 app 提交到 [管理應用程式] 頁面，請使用這個方法。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-146">[Approve a custom app](#approve-a-custom-app): Use this method if the developer submits the app directly to the Manage apps page using the Teams App Submission API.</span></span> <span data-ttu-id="eb2e0-147">然後，您可以直接從應用程式詳細資料頁面查看併發布 (或拒絕) app。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-147">You can then review and publish (or reject) the app directly from the app details page.</span></span>
- <span data-ttu-id="eb2e0-148">[上傳應用程式套件](#upload-an-app-package)：如果開發人員以 .zip 格式傳送您的應用程式套件，請使用這個方法。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-148">[Upload an app package](#upload-an-app-package): Use this method if the developer sends you the app package in .zip format.</span></span> <span data-ttu-id="eb2e0-149">您可以透過上傳應用程式套件來發佈應用程式。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-149">You publish the app by uploading the app package.</span></span>

###  <a name="approve-a-custom-app"></a><span data-ttu-id="eb2e0-150">核准自訂應用程式</span><span class="sxs-lookup"><span data-stu-id="eb2e0-150">Approve a custom app</span></span>

<span data-ttu-id="eb2e0-151">當開發人員使用小組 App 提交 API 提交 app 時，[管理 app] 頁面上的 [ **待定核准** ] 小工具會通知您。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-151">The **Pending approvals** widget on the Manage apps page notifies you when a developer submits an app by using the Teams App Submission API.</span></span> <span data-ttu-id="eb2e0-152">新提交的應用程式會列在已**提交**的**發佈狀態**，且**狀態**為 [已**封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-152">A newly submitted app is listed with a **Publishing status** of **Submitted** and an **Status** of **Blocked**.</span></span> <span data-ttu-id="eb2e0-153">移至 [應用程式詳細資料] 頁面以查看應用程式的詳細資訊，然後將其發佈，將 [ **發佈狀態** ] 設定為 [ **發佈**]。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-153">Go to the app details page to see more information about the app, and then to publish it, set **Publishing status** to **Publish**.</span></span>

<span data-ttu-id="eb2e0-154">當開發人員提交自訂應用程式的更新時，您也會收到通知。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-154">You're also notified when a developer submits an update to a custom app.</span></span> <span data-ttu-id="eb2e0-155">然後，您可以在應用程式詳細資料頁面上查看併發布 (或拒絕) 更新。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-155">You can then review and publish (or reject) the update on the app details page.</span></span> <span data-ttu-id="eb2e0-156">所有 app 許可權原則和 app 設定原則，都會針對更新的 app 保持強制執行。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-156">All app permission policies and app setup policies remain enforced for the updated app.</span></span>

<span data-ttu-id="eb2e0-157">若要深入瞭解，請參閱 [發佈透過團隊 App 提交 API 提交的自訂應用程式](submit-approve-custom-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-157">To learn more, see [Publish a custom app submitted through the Teams App Submission API](submit-approve-custom-apps.md).</span></span>

### <a name="upload-an-app-package"></a><span data-ttu-id="eb2e0-158">上傳應用程式套件</span><span class="sxs-lookup"><span data-stu-id="eb2e0-158">Upload an app package</span></span>

<span data-ttu-id="eb2e0-159">開發人員會使用 [團隊 App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)建立小組應用程式套件，然後以 .zip 格式將它傳送給您。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-159">The developer creates a Teams app package using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio), and then sends it to you in .zip format.</span></span> <span data-ttu-id="eb2e0-160">當您有應用程式套件時，可以將它上傳到貴組織的 app store。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-160">When you have the app package, you can upload it to your organization's app store.</span></span>

<span data-ttu-id="eb2e0-161">若要上傳新的自訂應用程式，請選取 **[上傳** ] 以上傳應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-161">To upload a new custom app, select **Upload** to upload the app package.</span></span> <span data-ttu-id="eb2e0-162">應用程式在上傳後不會醒目提示，因此您必須在 [管理 app] 頁面上搜尋應用程式清單來尋找。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-162">The app isn't highlighted after it's uploaded so you'll need to search the list of apps on the Manage apps page to find it.</span></span>

<span data-ttu-id="eb2e0-163">若要在上傳應用程式後進行更新，請在 [管理應用程式] 頁面上的應用程式清單中，按一下應用程式名稱，然後按一下 [ **更新**]。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-163">To update an app after it's uploaded, in the list of apps on the Manage apps page, click the app name, and then click **Update**.</span></span> <span data-ttu-id="eb2e0-164">這麼做會取代現有的 app，以及所有 app 許可權原則，以及 app 設定原則，都將針對更新的 app 保持強制執行。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-164">Doing this replaces the existing app and all app permission policies and app setup policies remain enforced for the updated app.</span></span>

<span data-ttu-id="eb2e0-165">若要深入瞭解，請參閱 [上傳應用程式套件以發佈自訂應用程式](upload-custom-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-165">To learn more, see [Publish a custom app by uploading an app package](upload-custom-apps.md).</span></span>

## <a name="allow-and-block-apps"></a><span data-ttu-id="eb2e0-166">允許及封鎖應用程式</span><span class="sxs-lookup"><span data-stu-id="eb2e0-166">Allow and block apps</span></span>

<span data-ttu-id="eb2e0-167">[管理應用程式] 頁面是您在組織階層允許或封鎖個別 app 的位置。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-167">The Manage apps page is where you allow or block individual apps at the org level.</span></span> <span data-ttu-id="eb2e0-168">它會顯示每個可用的 app 及其目前的組織層級 app 狀態。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-168">It shows every available app and its current org-level app status.</span></span> <span data-ttu-id="eb2e0-169">在組織階層 (封鎖及允許 app 已從 **組織範圍的應用程式設定** 窗格移至此處。 ) </span><span class="sxs-lookup"><span data-stu-id="eb2e0-169">(Blocking and allowing apps at the org level has moved from the **Org-wide app settings** pane to here.)</span></span>

<span data-ttu-id="eb2e0-170">若要允許或封鎖應用程式，請選取它，然後按一下 [ **允許** ] 或 [ **封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-170">To allow or block an app, select it, and then click **Allow** or **Block**.</span></span> <span data-ttu-id="eb2e0-171">當您封鎖 app 時，所有與該 app 的互動都會停用，而且該 app 不會出現在小組中您組織中的任何使用者。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-171">When you block an app, all interactions with that app are disabled and the app doesn't appear in Teams for any users in your organization.</span></span>

<span data-ttu-id="eb2e0-172">當您封鎖或允許 [管理應用程式] 頁面上的應用程式時，該應用程式會遭到封鎖，或您組織中的所有使用者都能使用該 app。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-172">When you block or allow an app on the Manage apps page, that app is blocked or allowed for all users in your organization.</span></span>  <span data-ttu-id="eb2e0-173">當您在小組 app 許可權原則中封鎖或允許應用程式時，系統會封鎖或允許指派該原則的使用者。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-173">When you block or allow an app in a Teams app permission policy, it's blocked or allowed for users who are assigned that policy.</span></span> <span data-ttu-id="eb2e0-174">若要讓使用者能夠安裝任何 app 並與之互動，您必須在 [管理應用程式] 頁面上，或已指派給使用者的 app 許可權原則中，允許該應用程式位於組織層級。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-174">For a user to be able to install and interact with any app, you must allow the app at the org level on the Manage apps page and in the app permission policy that's assigned to the user.</span></span>

 > [!NOTE]
 > <span data-ttu-id="eb2e0-175">若要卸載應用程式，請以滑鼠右鍵按一下應用程式，然後按一下左側的 [ **卸載** ] 或 [ **更多應用程式** ] 功能表。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-175">To uninstall an app, right-click the app and then click **Uninstall** or use the **More apps** menu on the left side.</span></span>

## <a name="purchase-services-for-third-party-apps"></a><span data-ttu-id="eb2e0-176">協力廠商應用程式的購買服務</span><span class="sxs-lookup"><span data-stu-id="eb2e0-176">Purchase services for third-party apps</span></span>

<span data-ttu-id="eb2e0-177">您可以直接從 [管理應用程式] 頁面，搜尋並購買貴組織中使用者所提供服務的授權。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-177">You can search for and purchase licenses for services offered by third-party apps for users in your organization directly from the Manage apps page.</span></span> <span data-ttu-id="eb2e0-178">資料表中的 [ **授權** ] 欄會指出 app 是否提供付費的 SaaS 訂閱。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-178">The **Licenses** column in the table indicates whether an app offers a paid SaaS subscription.</span></span> <span data-ttu-id="eb2e0-179">按一下 [ **立即購買** ] 來查看方案和定價資訊，並為您的使用者購買授權。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-179">Click **Purchase now** to view plans and pricing information and buy licenses for your users.</span></span> <span data-ttu-id="eb2e0-180">若要深入瞭解，請參閱 [Microsoft 團隊系統管理中心的 [針對團隊協力廠商應用程式購買服務](purchase-third-party-apps.md)]。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-180">To learn more, see [Purchase services for Teams third-party apps in the Microsoft Teams admin center](purchase-third-party-apps.md).</span></span>

## <a name="manage-org-wide-app-settings"></a><span data-ttu-id="eb2e0-181">管理整個組織內的應用程式設定</span><span class="sxs-lookup"><span data-stu-id="eb2e0-181">Manage org-wide app settings</span></span>

<span data-ttu-id="eb2e0-182">使用整個組織的 app 設定來控制使用者是否可以安裝協力廠商應用程式，以及使用者是否可以上傳或與您組織中的自訂應用程式互動。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-182">Use org-wide app settings to control whether users can install third-party apps and whether users can upload or interact with custom  apps in your organization.</span></span> <span data-ttu-id="eb2e0-183">全組織式應用程式設定會控制所有使用者的行為，並覆寫指派給使用者的任何其他應用程式許可權原則。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-183">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="eb2e0-184">您可以使用它們來控制惡意或有問題的 app。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-184">You can use them to control malicious or problematic apps.</span></span>

> [!NOTE]
> <span data-ttu-id="eb2e0-185">若要瞭解如何在 Microsoft 365 政府版的團隊部署中使用整個組織內的應用程式設定，請參閱 [在團隊中管理 app 許可權原則](teams-app-permission-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-185">To learn how to use org-wide app settings in Microsoft 365 Government - GCC deployments of Teams, see [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>

1. <span data-ttu-id="eb2e0-186">在 [管理應用程式] 頁面上，選取 [ **全組織式應用程式設定**]。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-186">On the Manage apps page, select **Org-wide app settings**.</span></span> <span data-ttu-id="eb2e0-187">接著，您可以在面板中設定您想要的設定。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-187">You can then configure the settings you want in the panel.</span></span>

    ![整個組織內的應用程式設定的螢幕擷取畫面](media/manage-apps-org-wide-app-settings.png)
    
2. <span data-ttu-id="eb2e0-189">在 **協力廠商應用程式**下，關閉或開啟這些設定以控制對協力廠商應用程式的存取：</span><span class="sxs-lookup"><span data-stu-id="eb2e0-189">Under **Third-party apps**, turn off or turn on these settings to control access to third-party apps:</span></span>

    - <span data-ttu-id="eb2e0-190">**允許協力廠商應用程式**：控制使用者是否可以使用協力廠商應用程式。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-190">**Allow third-party apps**: This controls whether users can use third-party apps.</span></span> <span data-ttu-id="eb2e0-191">如果您關閉此設定，您的使用者將無法安裝或使用任何協力廠商應用程式，而且這些應用程式的應用程式狀態會在表格中顯示為已 **封鎖的組織內** 。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-191">If you turn off this setting, your users won't be able to install or use any third-party apps and the app status of these apps is displayed as **Blocked org-wide** in the table.</span></span>

        > [!NOTE]
        > <span data-ttu-id="eb2e0-192">[ **允許協力廠商應用程式** ] 關閉時，系統會停用 [傳出 webhooks](https://docs.microsoft.com/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) ，這表示使用者無法建立。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-192">When **Allow third-party apps** is off, [outgoing webhooks](https://docs.microsoft.com/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) are disabled, which means that users can't create them.</span></span> <span data-ttu-id="eb2e0-193">開啟此設定時，系統會針對所有使用者啟用傳出 webhooks，您可以透過 [應用程式許可權原則](teams-app-permission-policies.md)允許或封鎖傳出 Webhook app，以在使用者層級進行控制。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-193">When this setting is on, outgoing webhooks are enabled for all users and you can control them at the user level by allowing or blocking the Outgoing Webhook app through [app permission policies](teams-app-permission-policies.md).</span></span> <br><br><span data-ttu-id="eb2e0-194">請注意，如果您有適用于**Microsoft** app 的現有[應用程式許可權原則](teams-app-permission-policies.md)，且使用 [**允許特定應用程式] 和 [封鎖所有人**] 設定，而您想要為使用者啟用外寄 webhooks，請將傳出 Webhook app 新增至清單。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-194">Note that if you have existing [app permission policies](teams-app-permission-policies.md) for **Microsoft apps** that use the **Allow specific apps and block all others** setting, and you want to enable outgoing webhooks for users, add the Outgoing Webhook app to the list.</span></span>
    - <span data-ttu-id="eb2e0-195">**允許預設發佈至商店的任何新的協力廠商應用程式**：這會控制發佈至 [小組] 應用程式商店的新的協力廠商應用程式是否會自動在小組中提供。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-195">**Allow any new third-party apps published to the store by default**: This controls whether new third-party apps that are published to the Teams app store become automatically available in Teams.</span></span> <span data-ttu-id="eb2e0-196">如果您允許協力廠商應用程式，則只能設定此選項。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-196">You can only set this option if you allow third-party apps.</span></span>

3. <span data-ttu-id="eb2e0-197">在 [ **自訂應用程式**] 底下，關閉或開啟 [ **允許與自訂應用程式互動**]。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-197">Under **Custom apps**, turn off or turn on **Allow interaction with custom apps**.</span></span> <span data-ttu-id="eb2e0-198">這個設定控制使用者是否能與自訂 app 互動。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-198">This setting controls whether users can interact with custom apps.</span></span> <span data-ttu-id="eb2e0-199">若要深入瞭解，請參閱 [管理團隊中的自訂應用程式原則和設定](teams-custom-app-policies-and-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-199">To learn more, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>
4. <span data-ttu-id="eb2e0-200">按一下 [ **儲存** 以組織範圍內的應用程式設定] 生效。</span><span class="sxs-lookup"><span data-stu-id="eb2e0-200">Click **Save** for org-wide app settings to take effect.</span></span>

## <a name="related-topics"></a><span data-ttu-id="eb2e0-201">相關主題</span><span class="sxs-lookup"><span data-stu-id="eb2e0-201">Related topics</span></span>

- [<span data-ttu-id="eb2e0-202">在 Teams 中的應用程式系統管理設定</span><span class="sxs-lookup"><span data-stu-id="eb2e0-202">Admin settings for apps in Teams</span></span>](admin-settings.md)