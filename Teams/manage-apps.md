---
title: 在系統管理中心管理Microsoft Teams應用程式
author: cichur
ms.author: v-cichur
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
description: 瞭解如何在系統管理中心的 Teams 管理應用程式頁面管理Microsoft Teams應用程式
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 6ea09ae40068277c5e450c19b6e258d04fd40fdc
ms.sourcegitcommit: d77104d5606ff93a792e8712d6c7780ae247b536
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2021
ms.locfileid: "53126909"
---
# <a name="manage-your-apps-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="5f667-103">在系統管理中心管理Microsoft Teams應用程式</span><span class="sxs-lookup"><span data-stu-id="5f667-103">Manage your apps in the Microsoft Teams admin center</span></span>

<span data-ttu-id="5f667-104">作為系統管理員，系統管理中心中的 Microsoft Teams 頁面就是您查看及管理組織Teams應用程式的地方。</span><span class="sxs-lookup"><span data-stu-id="5f667-104">As an admin, the Manage apps page in the Microsoft Teams admin center is where you view and manage all Teams apps for your organization.</span></span> <span data-ttu-id="5f667-105">在這裡，您可以查看應用程式的組織層級狀態和屬性、核准或上傳新的自訂應用程式至貴組織的 App Store、封鎖或允許組織層級的應用程式、新增應用程式至團隊、購買協力廠商應用程式的服務、查看應用程式要求的許可權、授予 App 系統管理員同意，以及管理整個組織的應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="5f667-105">Here, you can see the org-level status and properties of apps, approve or upload new custom apps to your organization's app store, block or allow apps at the org level, add apps to teams, purchase services for third-party apps, view permissions requested by apps, grant admin consent to apps, and manage org-wide app settings.</span></span>

<span data-ttu-id="5f667-106">管理應用程式頁面提供您所有可用 App 的視圖，為您提供決定要允許或封鎖整個組織之應用程式所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="5f667-106">The Manage apps page gives you a view into all available apps, providing you with the information you need to decide which apps to allow or block across your organization.</span></span> <span data-ttu-id="5f667-107">然後，您可以使用 [應用程式權限原則](teams-app-permission-policies.md)、 [應用程式設定](teams-app-setup-policies.md)策略，以及 [自訂應用程式策略和](teams-custom-app-policies-and-settings.md) 設定，為貴組織的特定使用者設定應用程式體驗。</span><span class="sxs-lookup"><span data-stu-id="5f667-107">You can then use [app permission policies](teams-app-permission-policies.md), [app setup policies](teams-app-setup-policies.md), and [custom app policies and settings](teams-custom-app-policies-and-settings.md) to configure the app experience for specific users in your organization.</span></span>

<span data-ttu-id="5f667-108">在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 **Teams 應用程式** > **管理應用程式**。</span><span class="sxs-lookup"><span data-stu-id="5f667-108">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="5f667-109">您必須是全域系統管理員Teams服務系統管理員才能存取頁面。</span><span class="sxs-lookup"><span data-stu-id="5f667-109">You must be a global admin or Teams service admin to access the page.</span></span>

> [!NOTE]
> <span data-ttu-id="5f667-110">Microsoft 365 政府社群雲端 GCCH (或美國) DoD (DoD) 尚未提供 Teams。</span><span class="sxs-lookup"><span data-stu-id="5f667-110">The Manage apps page isn't available yet in Microsoft 365 Government Community Cloud High (GCCH) or Department of Defense (DoD) deployments of Teams.</span></span>

## <a name="view-apps"></a><span data-ttu-id="5f667-111">查看應用程式</span><span class="sxs-lookup"><span data-stu-id="5f667-111">View apps</span></span>

<span data-ttu-id="5f667-112">您可以查看每個應用程式，包括每個 App 的下列資訊。</span><span class="sxs-lookup"><span data-stu-id="5f667-112">You can view every app including the following information about each app.</span></span>

![受管理應用程式頁面的螢幕擷取畫面](media/manage-apps.png)

- <span data-ttu-id="5f667-114">**名稱**：應用程式名稱。</span><span class="sxs-lookup"><span data-stu-id="5f667-114">**Name**: The app name.</span></span> <span data-ttu-id="5f667-115">選取應用程式名稱以前往應用程式詳細資料頁面，以查看應用程式的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="5f667-115">Select the app name to go to the app details page to see more information about the app.</span></span> <span data-ttu-id="5f667-116">這包括應用程式的描述，無論是允許或封鎖、版本、隱私權原則、使用條款、適用于應用程式的類別、認證狀態、支援的功能，以及應用程式識別碼。</span><span class="sxs-lookup"><span data-stu-id="5f667-116">This includes a description of the app, whether it's allowed or blocked, version, privacy policy, terms of use, categories that apply to the app, certification status, supported capabilities, and app ID.</span></span> <span data-ttu-id="5f667-117">以下是範例：</span><span class="sxs-lookup"><span data-stu-id="5f667-117">Here's an example:</span></span>

  ![應用程式詳細資料頁面的螢幕擷取畫面](media/manage-apps-app-details.png)
  
- <span data-ttu-id="5f667-119">**認證**：如果應用程式已經通過認證，則會看到已認證 **Microsoft 365或Publisher\*\*\*\*認證**。</span><span class="sxs-lookup"><span data-stu-id="5f667-119">**Certification**: If the app has gone through certification, you'll see either **Microsoft 365 certified** or **Publisher attestation**.</span></span> <span data-ttu-id="5f667-120">選取連結以查看應用程式的認證詳細資料。</span><span class="sxs-lookup"><span data-stu-id="5f667-120">Select the link to view certification details for the app.</span></span> <span data-ttu-id="5f667-121">如果您看到 **--** 「」，我們並沒有應用程式的認證資訊。</span><span class="sxs-lookup"><span data-stu-id="5f667-121">If you see "**--**", we don't have certification information for the app.</span></span> <span data-ttu-id="5f667-122">若要深入瞭解應用程式中的認證Teams，請參閱[Microsoft 365認證計畫](/teams-app-certification/all-apps)。</span><span class="sxs-lookup"><span data-stu-id="5f667-122">To learn more about certified apps in Teams, read [Microsoft 365 App Certification program](/teams-app-certification/all-apps).</span></span>  
- <span data-ttu-id="5f667-123">**Publisher：** 發行者的名稱。</span><span class="sxs-lookup"><span data-stu-id="5f667-123">**Publisher**: Name of the publisher.</span></span>
- <span data-ttu-id="5f667-124">**發佈狀態**：發佈自訂應用程式的狀態。</span><span class="sxs-lookup"><span data-stu-id="5f667-124">**Publishing status**: Publishing status of custom apps.</span></span>
- <span data-ttu-id="5f667-125">**狀態**：組織層級的應用程式狀態，可以是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="5f667-125">**Status**: Status of the app at the org level, which can be one of the following:</span></span>
- <span data-ttu-id="5f667-126">**允許**：此應用程式可供貴組織的所有使用者使用。</span><span class="sxs-lookup"><span data-stu-id="5f667-126">**Allowed**: The app is available for all users in your organization.</span></span>
- <span data-ttu-id="5f667-127">**已封鎖**：應用程式已封鎖，且不適用於貴組織的任何使用者。</span><span class="sxs-lookup"><span data-stu-id="5f667-127">**Blocked**: The app is blocked and not available for any users in your organization.</span></span>
  - <span data-ttu-id="5f667-128">**封鎖整個組織**：應用程式會封鎖在全組織的應用程式設定中。</span><span class="sxs-lookup"><span data-stu-id="5f667-128">**Blocked org-wide**: The app is blocked in org-wide app settings.</span></span>
      <span data-ttu-id="5f667-129">請注意，此欄代表之前位於全 **組織** 設定窗格中之應用程式的允許和封鎖狀態。</span><span class="sxs-lookup"><span data-stu-id="5f667-129">It's important to know that this column represents the allowed and blocked status of apps that were formerly on the **Org-wide settings** pane.</span></span> <span data-ttu-id="5f667-130">現在，您可以在管理應用程式頁面的全組織範圍內，查看、封鎖及 **允許應用程式** 。</span><span class="sxs-lookup"><span data-stu-id="5f667-130">You now view, block, and allow apps at the org-wide on the **Manage apps** page.</span></span>
- <span data-ttu-id="5f667-131">**授權**：指出應用程式是否提供軟體即服務 (SaaS) 訂閱以購買。</span><span class="sxs-lookup"><span data-stu-id="5f667-131">**Licenses**: Indicates whether an app offers a Software as a Service (SaaS) subscription for purchase.</span></span> <span data-ttu-id="5f667-132">此欄僅適用于協力廠商應用程式。</span><span class="sxs-lookup"><span data-stu-id="5f667-132">This column applies only to third-party apps.</span></span> <span data-ttu-id="5f667-133">每個協力廠商應用程式都會有下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="5f667-133">Each third-party app will have one of the following values:</span></span>
- <span data-ttu-id="5f667-134">**現在購買**：應用程式提供 SaaS 訂閱，可供購買。</span><span class="sxs-lookup"><span data-stu-id="5f667-134">**Purchase now**: The app offers a SaaS subscription and is available to purchase.</span></span>  
- <span data-ttu-id="5f667-135">**已** 購買：應用程式提供 SaaS 訂閱，而且您已購買其授權。</span><span class="sxs-lookup"><span data-stu-id="5f667-135">**Purchased**: The app offers a SaaS subscription and you've purchased licenses for it.</span></span>
- <span data-ttu-id="5f667-136">**- -**：應用程式不會提供 SaaS 訂閱。</span><span class="sxs-lookup"><span data-stu-id="5f667-136">**- -**: The app doesn't offer a SaaS subscription.</span></span>
- <span data-ttu-id="5f667-137">**自訂應用程式**：應用程式是否為自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="5f667-137">**Custom app**: Whether the app is a custom app.</span></span>
- <span data-ttu-id="5f667-138">**許可權**：指出已在 Azure AD Azure Active Directory (註冊的協力廠商或) 應用程式是否具有需要同意的許可權。</span><span class="sxs-lookup"><span data-stu-id="5f667-138">**Permissions**: Indicates whether a third-party or custom app that's registered in Azure Active Directory (Azure AD) has permissions that need consent.</span></span> <span data-ttu-id="5f667-139">您會看到下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="5f667-139">You'll see one of the following values:</span></span>
- <span data-ttu-id="5f667-140">**查看詳細** 資料：應用程式具有需要同意的許可權，應用程式才能存取資料。</span><span class="sxs-lookup"><span data-stu-id="5f667-140">**View details**: The app has permissions that require consent before the app can access data.</span></span>
- <span data-ttu-id="5f667-141">**- ：** 應用程式沒有需要同意的許可權。</span><span class="sxs-lookup"><span data-stu-id="5f667-141">**- -**: The app doesn't have permissions that need consent.</span></span>
- <span data-ttu-id="5f667-142">**類別**：適用于應用程式的類別。</span><span class="sxs-lookup"><span data-stu-id="5f667-142">**Categories**: Categories that apply to the app.</span></span>
- <span data-ttu-id="5f667-143">**版本**：應用程式版本。</span><span class="sxs-lookup"><span data-stu-id="5f667-143">**Version**: App version.</span></span>

<span data-ttu-id="5f667-144">若要在表格中查看您想要的資訊，請選取右上角的編輯欄，以新增或移除表格中的欄。</span><span class="sxs-lookup"><span data-stu-id="5f667-144">To see the information that you want in the table, select **Edit Column** in the upper-right corner to add or remove columns to the table.</span></span>

## <a name="publish-a-custom-app-to-your-organizations-app-store"></a><span data-ttu-id="5f667-145">將自訂應用程式發佈到組織的 App Store</span><span class="sxs-lookup"><span data-stu-id="5f667-145">Publish a custom app to your organization's app store</span></span>

<span data-ttu-id="5f667-146">使用管理應用程式頁面來發佈專為貴組織所建立的應用程式。</span><span class="sxs-lookup"><span data-stu-id="5f667-146">Use the Manage apps page to publish apps that are built specifically for your organization.</span></span> <span data-ttu-id="5f667-147">發佈自訂應用程式之後，組織 App Store 中的使用者可以使用它。</span><span class="sxs-lookup"><span data-stu-id="5f667-147">After you publish a custom app, it's available to users in your organization's app store.</span></span> <span data-ttu-id="5f667-148">有兩種方法可以發佈自訂應用程式至貴組織的 App Store。</span><span class="sxs-lookup"><span data-stu-id="5f667-148">There are two ways to publish a custom app to your organization's app store.</span></span> <span data-ttu-id="5f667-149">使用方式取決於您取得應用程式的方式。</span><span class="sxs-lookup"><span data-stu-id="5f667-149">The way that you use depends on how you get the app.</span></span>

- <span data-ttu-id="5f667-150">[核准自訂應用程式](#approve-a-custom-app)：如果開發人員使用應用程式提交 API 將應用程式直接提交到管理應用程式Teams使用此方法。</span><span class="sxs-lookup"><span data-stu-id="5f667-150">[Approve a custom app](#approve-a-custom-app): Use this method if the developer submits the app directly to the Manage apps page using the Teams App Submission API.</span></span> <span data-ttu-id="5f667-151">然後，您可以直接從應用程式詳細資料頁面 (或拒絕) 應用程式。</span><span class="sxs-lookup"><span data-stu-id="5f667-151">You can then review and publish (or reject) the app directly from the app details page.</span></span>
- <span data-ttu-id="5f667-152">[Upload應用程式套件](#upload-an-app-package)：如果開發人員以新的格式傳送應用程式套件，.zip方法。</span><span class="sxs-lookup"><span data-stu-id="5f667-152">[Upload an app package](#upload-an-app-package): Use this method if the developer sends you the app package in .zip format.</span></span> <span data-ttu-id="5f667-153">您可以上傳應用程式套件來發佈應用程式。</span><span class="sxs-lookup"><span data-stu-id="5f667-153">You publish the app by uploading the app package.</span></span>

### <a name="approve-a-custom-app"></a><span data-ttu-id="5f667-154">核准自訂應用程式</span><span class="sxs-lookup"><span data-stu-id="5f667-154">Approve a custom app</span></span>

<span data-ttu-id="5f667-155">當 **開發人員使用** 應用程式提交 API 提交應用程式時，在管理應用程式頁面上的擱置核准小工具Teams通知您。</span><span class="sxs-lookup"><span data-stu-id="5f667-155">The **Pending approvals** widget on the Manage apps page notifies you when a developer submits an app by using the Teams App Submission API.</span></span> <span data-ttu-id="5f667-156">新提交的應用程式會列出已提交之發佈狀態和封鎖 **狀態**。 </span><span class="sxs-lookup"><span data-stu-id="5f667-156">A newly submitted app is listed with a **Publishing status** of **Submitted** and an **Status** of **Blocked**.</span></span> <span data-ttu-id="5f667-157">請前往應用程式詳細資料頁面以查看應用程式的詳細資訊，然後發佈，將發佈 **狀態設定** 為 **發佈**。</span><span class="sxs-lookup"><span data-stu-id="5f667-157">Go to the app details page to see more information about the app, and then to publish it, set **Publishing status** to **Publish**.</span></span>

<span data-ttu-id="5f667-158">當開發人員將更新提交到自訂應用程式時，您也會收到通知。</span><span class="sxs-lookup"><span data-stu-id="5f667-158">You're also notified when a developer submits an update to a custom app.</span></span> <span data-ttu-id="5f667-159">然後，您可以在應用程式詳細資料頁面上 (或拒絕) 更新。</span><span class="sxs-lookup"><span data-stu-id="5f667-159">You can then review and publish (or reject) the update on the app details page.</span></span> <span data-ttu-id="5f667-160">對於更新的應用程式，所有應用程式權限原則與應用程式設定策略仍然強制執行。</span><span class="sxs-lookup"><span data-stu-id="5f667-160">All app permission policies and app setup policies remain enforced for the updated app.</span></span>

<span data-ttu-id="5f667-161">若要深入瞭解，請參閱發佈[透過](submit-approve-custom-apps.md)應用程式提交 API 提交的Teams應用程式。</span><span class="sxs-lookup"><span data-stu-id="5f667-161">To learn more, see [Publish a custom app submitted through the Teams App Submission API](submit-approve-custom-apps.md).</span></span>

### <a name="upload-an-app-package"></a><span data-ttu-id="5f667-162">Upload應用程式套件</span><span class="sxs-lookup"><span data-stu-id="5f667-162">Upload an app package</span></span>

<span data-ttu-id="5f667-163">開發人員使用 App [Studio](/microsoftteams/platform/get-started/get-started-app-studio)Teams應用程式套件，Teams應用程式套件，然後以 .zip格式傳送它。</span><span class="sxs-lookup"><span data-stu-id="5f667-163">The developer creates a Teams app package using [Teams App Studio](/microsoftteams/platform/get-started/get-started-app-studio), and then sends it to you in .zip format.</span></span> <span data-ttu-id="5f667-164">當您有應用程式套件時，您可以將它上傳到組織的 App Store。</span><span class="sxs-lookup"><span data-stu-id="5f667-164">When you have the app package, you can upload it to your organization's app store.</span></span>

<span data-ttu-id="5f667-165">若要上傳新的自訂應用程式，請選取 **Upload** 上傳應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="5f667-165">To upload a new custom app, select **Upload** to upload the app package.</span></span> <span data-ttu-id="5f667-166">應用程式上傳後不會加亮顯示，因此您必須在管理應用程式頁面上搜尋應用程式清單以尋找。</span><span class="sxs-lookup"><span data-stu-id="5f667-166">The app isn't highlighted after it's uploaded so you'll need to search the list of apps on the Manage apps page to find it.</span></span>

<span data-ttu-id="5f667-167">若要在應用程式上傳後更新，請在管理應用程式頁面上的應用程式清單中，選取應用程式名稱， **然後選取更新**。</span><span class="sxs-lookup"><span data-stu-id="5f667-167">To update an app after it's uploaded, in the list of apps on the Manage apps page, select the app name, and then select **Update**.</span></span> <span data-ttu-id="5f667-168">這麼做會取代現有的應用程式，所有應用程式權限原則及應用程式設定策略會持續為更新的應用程式強制執行。</span><span class="sxs-lookup"><span data-stu-id="5f667-168">Doing this replaces the existing app and all app permission policies and app setup policies remain enforced for the updated app.</span></span>

<span data-ttu-id="5f667-169">若要深入瞭解，請參閱上傳應用程式套件 [來發佈自訂應用程式](upload-custom-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="5f667-169">To learn more, see [Publish a custom app by uploading an app package](upload-custom-apps.md).</span></span>

## <a name="allow-and-block-apps"></a><span data-ttu-id="5f667-170">允許並封鎖應用程式</span><span class="sxs-lookup"><span data-stu-id="5f667-170">Allow and block apps</span></span>

<span data-ttu-id="5f667-171">您可以在組織層級允許或封鎖個別 App 的管理應用程式頁面。</span><span class="sxs-lookup"><span data-stu-id="5f667-171">The Manage apps page is where you allow or block individual apps at the org level.</span></span> <span data-ttu-id="5f667-172">它會顯示每個可用的應用程式及其目前的組織層級應用程式狀態。</span><span class="sxs-lookup"><span data-stu-id="5f667-172">It shows every available app and its current org-level app status.</span></span> <span data-ttu-id="5f667-173"> (封鎖及允許組織層級的應用程式，已從全 **組織** 應用程式設定窗格移至這裡。) </span><span class="sxs-lookup"><span data-stu-id="5f667-173">(Blocking and allowing apps at the org level has moved from the **Org-wide app settings** pane to here.)</span></span>

<span data-ttu-id="5f667-174">若要允許或封鎖應用程式，請選取它，然後選取允許或 **封鎖**。</span><span class="sxs-lookup"><span data-stu-id="5f667-174">To allow or block an app, select it, and then select **Allow** or **Block**.</span></span> <span data-ttu-id="5f667-175">當您封鎖應用程式時，與該應用程式的所有互動會停用，且應用程式不會顯示在貴組織Teams中。</span><span class="sxs-lookup"><span data-stu-id="5f667-175">When you block an app, all interactions with that app are disabled and the app doesn't appear in Teams for any users in your organization.</span></span>

<span data-ttu-id="5f667-176">當您封鎖或允許管理應用程式頁面上的應用程式時，該應用程式會封鎖或允許貴組織的所有使用者使用。</span><span class="sxs-lookup"><span data-stu-id="5f667-176">When you block or allow an app on the Manage apps page, that app is blocked or allowed for all users in your organization.</span></span>  <span data-ttu-id="5f667-177">當您在應用程式許可權Teams中封鎖或允許應用程式時，系統會封鎖或允許指派該策略的使用者使用。</span><span class="sxs-lookup"><span data-stu-id="5f667-177">When you block or allow an app in a Teams app permission policy, it's blocked or allowed for users who are assigned that policy.</span></span> <span data-ttu-id="5f667-178">若要讓使用者能夠安裝任何應用程式並與其互動，您必須在組織層級允許應用程式位於管理應用程式頁面，並允許在指派給使用者的應用程式許可權政策中。</span><span class="sxs-lookup"><span data-stu-id="5f667-178">For a user to be able to install and interact with any app, you must allow the app at the org level on the Manage apps page and in the app permission policy that's assigned to the user.</span></span>

 > [!NOTE]
 > <span data-ttu-id="5f667-179">若要卸載應用程式，請以滑鼠右鍵按一下應用程式，然後按一下 [**卸載** 或使用左側的 [其他應用程式> 功能表。</span><span class="sxs-lookup"><span data-stu-id="5f667-179">To uninstall an app, right-click the app, and then click **Uninstall** or use the **More apps** menu on the left side.</span></span>

## <a name="add-an-app-to-a-team"></a><span data-ttu-id="5f667-180">新增應用程式至小組</span><span class="sxs-lookup"><span data-stu-id="5f667-180">Add an app to a team</span></span>

<span data-ttu-id="5f667-181">您可以使用新增 **到小組** 按鈕，將應用程式安裝到團隊。</span><span class="sxs-lookup"><span data-stu-id="5f667-181">You use the **Add to team** button to install an app to a team.</span></span> <span data-ttu-id="5f667-182">請記住，這僅適用于可在小組範圍內安裝的 App。</span><span class="sxs-lookup"><span data-stu-id="5f667-182">Keep in mind that this is only for apps that can be installed in a team scope.</span></span> <span data-ttu-id="5f667-183">只有 **個人範圍** 中的 App 才能使用新增到小組按鈕。</span><span class="sxs-lookup"><span data-stu-id="5f667-183">The **Add to team** button isn't available for apps that can only be installed in the personal scope.</span></span>

![新增到小組按鈕的螢幕擷取畫面](media/manage-apps-add-app-team.png)

1. <span data-ttu-id="5f667-185">搜尋您想要的應用程式，然後按一下應用程式名稱左側以選取應用程式。</span><span class="sxs-lookup"><span data-stu-id="5f667-185">Search for the app you want, and then select the app by clicking to the left of the app name.</span></span>
2. <span data-ttu-id="5f667-186">選取 **新增到團隊**。</span><span class="sxs-lookup"><span data-stu-id="5f667-186">Select **Add to team**.</span></span>
3. <span data-ttu-id="5f667-187">在新增 **到小組窗格中** ，搜尋您想要新增應用程式的團隊，選取該團隊，然後 **選取應用程式**。</span><span class="sxs-lookup"><span data-stu-id="5f667-187">In the **Add to team** pane, search for the team you want to add the app to, select the team, and then select **Apply**.</span></span>

## <a name="customize-an-app"></a><span data-ttu-id="5f667-188">自訂應用程式</span><span class="sxs-lookup"><span data-stu-id="5f667-188">Customize an app</span></span>

<span data-ttu-id="5f667-189">現在，您可以自訂應用程式，以根據您的組織需求包含特定的外觀和感受。</span><span class="sxs-lookup"><span data-stu-id="5f667-189">You can now customize an app to include a specific look and feel according to your organization needs.</span></span> <span data-ttu-id="5f667-190">請參閱[在 Teams 中自訂Teams。](customize-apps.md)</span><span class="sxs-lookup"><span data-stu-id="5f667-190">See [Customize apps in Teams](customize-apps.md).</span></span>

## <a name="purchase-services-for-third-party-apps"></a><span data-ttu-id="5f667-191">購買協力廠商應用程式服務</span><span class="sxs-lookup"><span data-stu-id="5f667-191">Purchase services for third-party apps</span></span>

<span data-ttu-id="5f667-192">您可以直接從管理應用程式頁面搜尋及購買貴組織使用者協力廠商應用程式所提供的服務授權。</span><span class="sxs-lookup"><span data-stu-id="5f667-192">You can search for and purchase licenses for services offered by third-party apps for users in your organization directly from the Manage apps page.</span></span> <span data-ttu-id="5f667-193">表格中 **的** 授權欄會指出應用程式是否提供付費的 SaaS 訂閱。</span><span class="sxs-lookup"><span data-stu-id="5f667-193">The **Licenses** column in the table indicates whether an app offers a paid SaaS subscription.</span></span> <span data-ttu-id="5f667-194">選取 **立即購買** 來查看方案與定價資訊，並購買使用者授權。</span><span class="sxs-lookup"><span data-stu-id="5f667-194">Select **Purchase now** to view plans and pricing information and buy licenses for your users.</span></span> <span data-ttu-id="5f667-195">若要深入瞭解，請參閱在系統管理中心[Teams購買](purchase-third-party-apps.md)第三Microsoft Teams服務。</span><span class="sxs-lookup"><span data-stu-id="5f667-195">To learn more, see [Purchase services for Teams third-party apps in the Microsoft Teams admin center](purchase-third-party-apps.md).</span></span>

## <a name="grant-admin-consent-to-apps"></a><span data-ttu-id="5f667-196">將系統管理員同意授予應用程式</span><span class="sxs-lookup"><span data-stu-id="5f667-196">Grant admin consent to apps</span></span>

<span data-ttu-id="5f667-197">您可以審查並授權代表貴組織中所有使用者要求許可權的應用程式。</span><span class="sxs-lookup"><span data-stu-id="5f667-197">You can review and grant consent to apps that request permissions on behalf of all users in your organization.</span></span> <span data-ttu-id="5f667-198">如此一來，使用者就不需要在啟動 App 時，查看並接受應用程式要求的許可權。</span><span class="sxs-lookup"><span data-stu-id="5f667-198">You do this so that users don't have to review and accept the permissions requested by the app when they start the app.</span></span> <span data-ttu-id="5f667-199">許可權 **欄** 會指出應用程式是否具有需要同意的許可權。</span><span class="sxs-lookup"><span data-stu-id="5f667-199">The **Permissions** column indicates whether an app has permissions that need consent.</span></span> <span data-ttu-id="5f667-200">針對在 Azure  AD 中註冊並擁有需要同意許可權的每個應用程式，您會看到一個 View 詳細資料連結。</span><span class="sxs-lookup"><span data-stu-id="5f667-200">You'll see a **View details** link for each app registered in Azure AD that has permissions that need consent.</span></span> <span data-ttu-id="5f667-201">若要深入瞭解，請參閱在系統管理中心中查看應用程式許可權Microsoft Teams[管理員同意](app-permissions-admin-center.md)。</span><span class="sxs-lookup"><span data-stu-id="5f667-201">To learn more, see [View app permissions and grant admin consent in the Microsoft Teams admin center](app-permissions-admin-center.md).</span></span>

## <a name="view-resource-specific-consent-permissions"></a><span data-ttu-id="5f667-202">查看特定資源同意許可權</span><span class="sxs-lookup"><span data-stu-id="5f667-202">View resource-specific consent permissions</span></span>

<span data-ttu-id="5f667-203">資源特定 (RSC) 許可權，讓團隊擁有者同意應用程式存取及修改小組的資料。</span><span class="sxs-lookup"><span data-stu-id="5f667-203">Resource-specific consent (RSC) permissions let team owners grant consent for an app to access and modify a team's data.</span></span> <span data-ttu-id="5f667-204">RSC 許可權是精細Teams特定許可權，可定義應用程式可在特定小組中執行哪些工作。</span><span class="sxs-lookup"><span data-stu-id="5f667-204">RSC permissions are granular, Teams-specific permissions that define what an app can do in a specific team.</span></span> <span data-ttu-id="5f667-205">您可以在應用程式詳細資料頁面的許可權選項卡上，查看 RSC 許可權。</span><span class="sxs-lookup"><span data-stu-id="5f667-205">You can view RSC permissions on the **Permissions** tab of the app details page for an app.</span></span> <span data-ttu-id="5f667-206">若要深入瞭解，請參閱在系統管理中心中查看應用程式許可權Microsoft Teams[管理員同意](app-permissions-admin-center.md)。</span><span class="sxs-lookup"><span data-stu-id="5f667-206">To learn more, see [View app permissions and grant admin consent in the Microsoft Teams admin center](app-permissions-admin-center.md).</span></span>

## <a name="manage-org-wide-app-settings"></a><span data-ttu-id="5f667-207">管理全組織的應用程式設定</span><span class="sxs-lookup"><span data-stu-id="5f667-207">Manage org-wide app settings</span></span>

<span data-ttu-id="5f667-208">使用全組織 App 設定來控制使用者是否可以安裝協力廠商應用程式，以及使用者是否可以上傳或與組織中的自訂應用程式互動。</span><span class="sxs-lookup"><span data-stu-id="5f667-208">Use org-wide app settings to control whether users can install third-party apps and whether users can upload or interact with custom  apps in your organization.</span></span> <span data-ttu-id="5f667-209">全組織應用程式設定會控管所有使用者的行為，並覆寫指派給使用者的任何其他應用程式權限原則。</span><span class="sxs-lookup"><span data-stu-id="5f667-209">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="5f667-210">您可以使用這些原則來控制惡意或有問題的應用程式。</span><span class="sxs-lookup"><span data-stu-id="5f667-210">You can use them to control malicious or problematic apps.</span></span>

> [!NOTE]
> <span data-ttu-id="5f667-211">若要瞭解如何在 Microsoft 365 政府 - 政府社群雲端 高 GCCH 和國防部 (DoD) Teams 部署中使用全組織應用程式設定，請參閱管理 Teams 中的[應用程式許可權](teams-app-permission-policies.md)政策。</span><span class="sxs-lookup"><span data-stu-id="5f667-211">To learn how to use org-wide app settings in Microsoft 365 Government - Government Community Cloud High GCCH and Department of Defense (DoD) deployments of Teams, see [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>

1. <span data-ttu-id="5f667-212">在管理應用程式頁面上，選取 **整個組織的應用程式設定**。</span><span class="sxs-lookup"><span data-stu-id="5f667-212">On the Manage apps page, select **Org-wide app settings**.</span></span> <span data-ttu-id="5f667-213">然後您就可以在面板中設定您要的設定。</span><span class="sxs-lookup"><span data-stu-id="5f667-213">You can then configure the settings you want in the panel.</span></span>

    ![全組織應用程式設定的螢幕擷取畫面](media/manage-apps-org-wide-app-settings.png)

2. <span data-ttu-id="5f667-215">在 [第三方應用程式 **]** 下，關閉或開啟這些設定，以控制對第三方應用程式的存取權：</span><span class="sxs-lookup"><span data-stu-id="5f667-215">Under **Third-party apps**, turn off or turn on these settings to control access to third-party apps:</span></span>

    - <span data-ttu-id="5f667-216">**允許第三方應用程式**：這會控制使用者是否可以使用第三方應用程式。</span><span class="sxs-lookup"><span data-stu-id="5f667-216">**Allow third-party apps**: This controls whether users can use third-party apps.</span></span> <span data-ttu-id="5f667-217">如果您關閉此設定，您的使用者將無法安裝或使用任何協力廠商應用程式，且這些 App 的應用程式狀態會顯示為表格中的全組織封鎖狀態。 </span><span class="sxs-lookup"><span data-stu-id="5f667-217">If you turn off this setting, your users won't be able to install or use any third-party apps and the app status of these apps is displayed as **Blocked org-wide** in the table.</span></span>

        > [!NOTE]
        > <span data-ttu-id="5f667-218">當 **允許第** 三方應用程式關閉時，[](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)所有使用者仍可使用外發網頁連結，但您可以透過應用程式許可權政策允許或封鎖外發 Web 上手應用程式，以在使用者層級控制 [這些應用程式](teams-app-permission-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="5f667-218">When **Allow third-party apps** is off, [outgoing webhooks](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) are still enabled for all users, but you can control them at the user level by allowing or blocking the Outgoing Webhook app through [app permission policies](teams-app-permission-policies.md).</span></span> <br><br><span data-ttu-id="5f667-219">請注意，如果您有 Microsoft 應用程式的現有應用程式許可權策略，使用允許特定應用程式並封鎖所有其他設定，而且您想要為使用者啟用外發網頁連結，請新增外發 Web 上手應用程式至清單。 [](teams-app-permission-policies.md)</span><span class="sxs-lookup"><span data-stu-id="5f667-219">Note that if you have existing [app permission policies](teams-app-permission-policies.md) for **Microsoft apps** that use the **Allow specific apps and block all others** setting, and you want to enable outgoing webhooks for users, add the Outgoing Webhook app to the list.</span></span>

        > [!NOTE]
        > <span data-ttu-id="5f667-220">Teams 使用者可以在主持會議或與其他組織人員聊天時新增應用程式。</span><span class="sxs-lookup"><span data-stu-id="5f667-220">Teams users can add apps when they host meetings or chats with people from other organizations.</span></span> <span data-ttu-id="5f667-221">當他們加入由其他組織主持的會議或聊天時，他們也可以使用由其他組織人員共用的應用程式。</span><span class="sxs-lookup"><span data-stu-id="5f667-221">They can also use apps shared by people in other organizations when they join meetings or chats hosted by those organizations.</span></span> <span data-ttu-id="5f667-222">將會套用託管使用者組織的資料原則，以及該使用者組織共用的任何協力廠商應用程式的資料共用做法。</span><span class="sxs-lookup"><span data-stu-id="5f667-222">The data policies of the hosting user's organization, as well as the data sharing practices of any third-party apps shared by that user's organization, are applied.</span></span>

    - <span data-ttu-id="5f667-223">**預設允許發行到商店的任何新第三方應用程式**：這會控制發佈至 Teams 應用程式商店的新第三方應用程式是否會自動在 Teams 中提供使用。</span><span class="sxs-lookup"><span data-stu-id="5f667-223">**Allow any new third-party apps published to the store by default**: This controls whether new third-party apps that are published to the Teams app store become automatically available in Teams.</span></span> <span data-ttu-id="5f667-224">您只能在允許第三方應用程式時設定此選項。</span><span class="sxs-lookup"><span data-stu-id="5f667-224">You can only set this option if you allow third-party apps.</span></span>

3. <span data-ttu-id="5f667-225">在 **自訂應用程式下**，關閉或開啟允許 **與自訂應用程式互動。**</span><span class="sxs-lookup"><span data-stu-id="5f667-225">Under **Custom apps**, turn off or turn on **Allow interaction with custom apps**.</span></span> <span data-ttu-id="5f667-226">此設定可控制使用者是否能與自訂應用程式互動。</span><span class="sxs-lookup"><span data-stu-id="5f667-226">This setting controls whether users can interact with custom apps.</span></span> <span data-ttu-id="5f667-227">若要深入了解，請參閱[在 Teams 中管理自訂應用程式原則和設定](teams-custom-app-policies-and-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="5f667-227">To learn more, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>
4. <span data-ttu-id="5f667-228">選取 **儲存** 以讓全組織的應用程式設定生效。</span><span class="sxs-lookup"><span data-stu-id="5f667-228">Select **Save** for org-wide app settings to take effect.</span></span>

## <a name="view-security-and-compliance-information-for-microsoft-365-certified-apps"></a><span data-ttu-id="5f667-229">查看認證應用程式的安全性Microsoft 365合規性資訊</span><span class="sxs-lookup"><span data-stu-id="5f667-229">View security and compliance information for Microsoft 365 Certified apps</span></span>

<span data-ttu-id="5f667-230">當評估其組織的應用程式時，系統管理員可以使用獨立的雲端存取安全性代理程式 (CASB) ，例如 Microsoft Cloud App Security (MCAS) ，以尋找 App 安全性和行為的資訊。</span><span class="sxs-lookup"><span data-stu-id="5f667-230">When evaluating an app for their organization, admins can use independent Cloud Access Security Brokers (CASB), such as Microsoft Cloud App Security (MCAS), to find information about security and behaviors of an app.</span></span> <span data-ttu-id="5f667-231">系統Teams系統管理中心包含 MCAS 針對 Microsoft 365 認證應用程式的安全性與合規性資訊，因此您將擁有 App 是否符合您需求之詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="5f667-231">The Teams admin center includes security and compliance information from MCAS for Microsoft 365 Certified apps so you'll have more information on whether or not the app meets your needs.</span></span>

> [!NOTE]
> <span data-ttu-id="5f667-232">不論貴組織是否有支援 MCAS 的授權，所有系統管理員都可以使用這項功能。</span><span class="sxs-lookup"><span data-stu-id="5f667-232">This feature is available to all admins, whether or not your organization has a license that supports MCAS.</span></span>

<span data-ttu-id="5f667-233">若要存取 MCAS 資訊，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="5f667-233">To access MCAS information, follow these steps:</span></span>

1. <span data-ttu-id="5f667-234">在系統管理Teams **中，選取** 管理應用程式Teams **應用程式**。</span><span class="sxs-lookup"><span data-stu-id="5f667-234">In the Teams admin center, select **Manage apps** under **Teams apps**.</span></span>
1. <span data-ttu-id="5f667-235">選取 **認證** 以排序應用程式，Microsoft 365所有認證應用程式都推至表格頂端。</span><span class="sxs-lookup"><span data-stu-id="5f667-235">Select **Certification** to sort apps and push all Microsoft 365 Certified apps to the top of the table.</span></span>
1. <span data-ttu-id="5f667-236">選擇一Microsoft 365認證應用程式。</span><span class="sxs-lookup"><span data-stu-id="5f667-236">Choose a Microsoft 365 Certified app.</span></span>
1. <span data-ttu-id="5f667-237">選取安全性 **與合規性選項卡** 。</span><span class="sxs-lookup"><span data-stu-id="5f667-237">Select the **Security and compliance** tab.</span></span>

![系統管理Teams安全性與合規性選項卡的螢幕擷取畫面](media/mcas.png)

<span data-ttu-id="5f667-239">您可以在此選項卡上找到安全性、合規性和資料保護的資訊。</span><span class="sxs-lookup"><span data-stu-id="5f667-239">On this tab, you'll find information on security, compliance, and data protection.</span></span> <span data-ttu-id="5f667-240">您也可以展開每個下拉清單，以取得所選應用程式支援哪些功能的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="5f667-240">You can also expand each dropdown list to get more details about which capabilities are supported for the selected application.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5f667-241">相關主題</span><span class="sxs-lookup"><span data-stu-id="5f667-241">Related topics</span></span>

- [<span data-ttu-id="5f667-242">在 Teams 中管理應用程式的設定</span><span class="sxs-lookup"><span data-stu-id="5f667-242">Admin settings for apps in Teams</span></span>](admin-settings.md)
