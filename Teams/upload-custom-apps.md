---
title: Upload系統管理中心Microsoft Teams自訂應用程式
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: joglocke, vaibhava
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在系統管理中心將自訂應用程式上傳到Microsoft Teams市。
ms.openlocfilehash: 9473c8e2fc4284c4ca205666152ef183b0210841
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115521"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a><span data-ttu-id="60668-103">上傳應用程式套件來發佈自訂應用程式</span><span class="sxs-lookup"><span data-stu-id="60668-103">Publish a custom app by uploading an app package</span></span>

> [!NOTE]
> <span data-ttu-id="60668-104">當您發佈自訂 Teams應用程式時，組織 App Store 中的使用者可以使用自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="60668-104">When you publish a custom Teams app, it's available to users in your organization's app store.</span></span> <span data-ttu-id="60668-105">發佈自訂應用程式的方法有兩種，而使用方式取決於您取得應用程式的方式。</span><span class="sxs-lookup"><span data-stu-id="60668-105">There are two ways to publish a custom app and the way that you use depends on how you get the app.</span></span> <span data-ttu-id="60668-106">**本文著重瞭解如何** 以開發人員傳送 (格式.zip應用程式套件) 發佈自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="60668-106">**This article focuses on how to publish a custom app by uploading an app package (in .zip format) that a developer sends you**.</span></span> <span data-ttu-id="60668-107">另一種方法是核准自訂應用程式，當開發人員透過應用程式提交 API 將應用程式直接提交<a href="/microsoftteams/manage-apps" target="_blank"></a>到管理應用程式頁面Teams使用。</span><span class="sxs-lookup"><span data-stu-id="60668-107">The other method, approving a custom app, is used when a developer submits an app directly to the <a href="/microsoftteams/manage-apps" target="_blank">Manage apps</a> page through the Teams App Submission API.</span></span> <span data-ttu-id="60668-108">若要深入瞭解這個方法，請參閱發佈透過應用程式提交 API 提交的Teams<a href="/microsoftteams/submit-approve-custom-apps" target="_blank">應用程式</a>。</span><span class="sxs-lookup"><span data-stu-id="60668-108">To learn more about that method, see <a href="/microsoftteams/submit-approve-custom-apps" target="_blank">Publish a custom app submitted through the Teams App Submission API</a>.</span></span>

<span data-ttu-id="60668-109">本文提供端對端指南，瞭解如何將應用程式從開發Teams部署到探索。</span><span class="sxs-lookup"><span data-stu-id="60668-109">This article provides end-to-end guidance for how to take your Teams app from development to deployment to discovery.</span></span> <span data-ttu-id="60668-110">本指南著重于應用程式Teams，適用于系統管理員和 IT 專業人員。</span><span class="sxs-lookup"><span data-stu-id="60668-110">This guidance focuses on the Teams aspects of the app and is intended for admins and IT pros.</span></span> <span data-ttu-id="60668-111">有關開發應用程式Teams，請參閱Teams<a href="/microsoftteams/platform" target="_blank">檔</a>。</span><span class="sxs-lookup"><span data-stu-id="60668-111">For more information about developing Teams apps, see the <a href="/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

![從開發到部署的應用程式概觀](media/upload-custom-apps.png)

## <a name="develop"></a><span data-ttu-id="60668-113">開發</span><span class="sxs-lookup"><span data-stu-id="60668-113">Develop</span></span>

### <a name="create-your-app"></a><span data-ttu-id="60668-114">建立您的應用程式</span><span class="sxs-lookup"><span data-stu-id="60668-114">Create your app</span></span>

<span data-ttu-id="60668-115">開發人員Microsoft Teams平臺，讓開發人員能輕鬆整合您自己的應用程式和服務，以提高生產力、更快速地做出決策，以及與現有內容和工作流程建立共同作業。</span><span class="sxs-lookup"><span data-stu-id="60668-115">The Microsoft Teams developer platform makes it easy for developers to integrate your own apps and services to improve productivity, make decisions faster, and create collaboration around existing content and workflows.</span></span> <span data-ttu-id="60668-116">以平臺Teams的應用程式，是用戶端Teams服務與工作流程之間的橋樑，直接將它們納入您的共同合作平臺中。</span><span class="sxs-lookup"><span data-stu-id="60668-116">Apps built on the Teams platform are bridges between the Teams client and your services and workflows, bringing them directly into the context of your collaboration platform.</span></span> <span data-ttu-id="60668-117">若要詳細資訊，請參閱開發人員Teams<a href="/microsoftteams/platform" target="_blank">檔</a>。</span><span class="sxs-lookup"><span data-stu-id="60668-117">For more information, go to the <a href="/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

## <a name="validate"></a><span data-ttu-id="60668-118">驗證</span><span class="sxs-lookup"><span data-stu-id="60668-118">Validate</span></span>

### <a name="get-the-app-package"></a><span data-ttu-id="60668-119">取得應用程式套件</span><span class="sxs-lookup"><span data-stu-id="60668-119">Get the app package</span></span>

<span data-ttu-id="60668-120">當應用程式準備好用於生產時，開發人員應產生應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="60668-120">When the app is ready for use in production, the developer should produce an app package.</span></span> <span data-ttu-id="60668-121">他們可以使用<a href="/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">App Studio。</a></span><span class="sxs-lookup"><span data-stu-id="60668-121">They can use <a href="/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">App Studio</a> for that.</span></span> <span data-ttu-id="60668-122">他們將以新的格式傳送.zip檔案。</span><span class="sxs-lookup"><span data-stu-id="60668-122">They'll send you the file in .zip format.</span></span>

<span data-ttu-id="60668-123">Microsoft<a href="/microsoftteams/platform/publishing/office-store-approval" target="_blank">會使用這些指導方針</a>，確保應用程式符合全球應用程式市Teams的品質和安全性標準。</span><span class="sxs-lookup"><span data-stu-id="60668-123">Microsoft uses <a href="/microsoftteams/platform/publishing/office-store-approval" target="_blank">these guidelines</a> to ensure apps comply with the quality and security standards of the global Teams apps store.</span></span>

### <a name="allow-trusted-users-to-upload-custom-apps"></a><span data-ttu-id="60668-124">允許信任的使用者上傳自訂應用程式</span><span class="sxs-lookup"><span data-stu-id="60668-124">Allow trusted users to upload custom apps</span></span>

<span data-ttu-id="60668-125">若要驗證應用程式在生產租使用者中是否正確工作，您必須允許您自己和/或信任的使用者在生產租使用者中上傳自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="60668-125">To validate that the app is working correctly in your production tenant, you need to allow yourself and/or trusted users to upload custom apps in the production tenant.</span></span> <span data-ttu-id="60668-126">您可以使用 <a href="/microsoftteams/teams-app-setup-policies" target="_blank">應用程式設定策略</a> 執行這項操作。</span><span class="sxs-lookup"><span data-stu-id="60668-126">You use <a href="/microsoftteams/teams-app-setup-policies" target="_blank">app setup policies</a> to do this.</span></span>

> [!NOTE]
> <span data-ttu-id="60668-127">如果您不喜歡將應用程式上傳至生產租使用者進行驗證，即使您自己或信任的使用者也一樣，您可以略過此步驟，並按照 Upload 和[設定](#upload)及管理節中的步驟，將未驗證[](#set-up-and-manage)的應用程式發佈到組織的 App Store。</span><span class="sxs-lookup"><span data-stu-id="60668-127">If you're uncomfortable with uploading the app to your production tenant for validation, even for yourself or trusted users, you can skip this step and follow the steps in the [Upload](#upload) and [Set up and manage](#set-up-and-manage) sections to publish the unvalidated app to your organization's app store.</span></span> <span data-ttu-id="60668-128">接著，將該應用程式的存取許可權制為只有您自己和您信任的使用者。</span><span class="sxs-lookup"><span data-stu-id="60668-128">Then, restrict access to that app to only yourself and users you trust.</span></span> <span data-ttu-id="60668-129">這些使用者接著可以從組織的 App Store 取得應用程式來執行驗證。</span><span class="sxs-lookup"><span data-stu-id="60668-129">These users can then get the app from your organization's app store to perform validation.</span></span> <span data-ttu-id="60668-130">應用程式驗證之後，請使用相同的權限原則來開啟存取，並推出應用程式供生產使用。</span><span class="sxs-lookup"><span data-stu-id="60668-130">After the app is validated, use the same permission policies to open access and roll the app out for production use.</span></span>

<span data-ttu-id="60668-131">若要允許信任的使用者上傳自訂應用程式，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="60668-131">To allow trusted users to upload custom apps, follow these steps:</span></span>

1. <span data-ttu-id="60668-132">開啟允許 **與自訂應用程式** 全組織 App 互動設定。</span><span class="sxs-lookup"><span data-stu-id="60668-132">Turn on the **Allow interaction with custom apps** org-wide app setting.</span></span> <span data-ttu-id="60668-133">若要這麼做：</span><span class="sxs-lookup"><span data-stu-id="60668-133">To do this:</span></span>
    1. <span data-ttu-id="60668-134">在系統管理中心的左側導Microsoft Teams，前往 [管理Teams **應用程式**>，然後按一下 [全  >  \*\*\*\*\*\*組織應用程式設定\*\*> 。</span><span class="sxs-lookup"><span data-stu-id="60668-134">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**, and then click **Org-wide app settings**.</span></span>
    2. <span data-ttu-id="60668-135">在 **[自訂應用程式」** 下，開啟 [ **允許與自訂應用程式互動**，然後按一下 [ **儲存**> 。</span><span class="sxs-lookup"><span data-stu-id="60668-135">Under **Custom apps**, turn on **Allow interaction with custom apps**, and then click **Save**.</span></span>
2. <span data-ttu-id="60668-136">關閉 **全域Upload** 設定策略中的自訂應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="60668-136">Turn off the **Upload custom apps** setting in the global app setup policy.</span></span> <span data-ttu-id="60668-137">若要這麼做：</span><span class="sxs-lookup"><span data-stu-id="60668-137">To do this:</span></span>
    1. <span data-ttu-id="60668-138">在系統管理中心的左側導Microsoft Teams，前往 [Teams **應用程式** 設定政策，然後按一下 [全域 ( >  \*\*\*\*\*\*全組織\*\* 的預設) 規則。</span><span class="sxs-lookup"><span data-stu-id="60668-138">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**, and then click the **Global (Org-wide default)** policy.</span></span>
    2. <span data-ttu-id="60668-139">關閉自訂 **Upload** 應用程式，然後按一下 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="60668-139">Turn off **Upload custom apps**, and then click **Save**.</span></span>
3. <span data-ttu-id="60668-140">建立新的應用程式設定策略，允許上傳自訂應用程式，並將它指派給一組信任的使用者。</span><span class="sxs-lookup"><span data-stu-id="60668-140">Create a new app setup policy that allows uploading custom apps and assign it to your set of trusted users.</span></span> <span data-ttu-id="60668-141">若要這麼做：</span><span class="sxs-lookup"><span data-stu-id="60668-141">To do this:</span></span>
    1. <span data-ttu-id="60668-142">在系統管理中心的左側導Microsoft Teams，請Teams **應用程式設定** 政策，然後按一下 [  >  \*\*\*\*\*\*新增\*\*。</span><span class="sxs-lookup"><span data-stu-id="60668-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**, and then click the **Add**.</span></span> <span data-ttu-id="60668-143">為新政策命名和描述，Upload **自訂應用程式，** 然後按一下 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="60668-143">Give the new policy a name and description, turn on **Upload custom apps**, and then click **Save**.</span></span>
    2. <span data-ttu-id="60668-144">選取您建立的新政策，然後按一下 [ **管理使用者**。</span><span class="sxs-lookup"><span data-stu-id="60668-144">Select the new policy you created, and then click **Manage users**.</span></span> <span data-ttu-id="60668-145">搜尋使用者，按一下 [**新增**，然後按一下 **[Apply.**</span><span class="sxs-lookup"><span data-stu-id="60668-145">Search for a user, click **Add**, and then click **Apply**.</span></span> <span data-ttu-id="60668-146">重複此步驟，將策略指派給所有信任的使用者。</span><span class="sxs-lookup"><span data-stu-id="60668-146">Repeat this step to assign the policy to all your trusted users.</span></span>

        ![「新增應用程式設定政策」頁面的螢幕擷取畫面](media/manage-your-lob-apps-new-app-setup-policy.png)

    <span data-ttu-id="60668-148">這些使用者現在可以上傳應用程式清單，以驗證應用程式在生產租使用者中是否正確工作。</span><span class="sxs-lookup"><span data-stu-id="60668-148">These users can now upload the app manifest to validate that the app is working correctly in the production tenant.</span></span>

## <a name="upload"></a><span data-ttu-id="60668-149">Upload</span><span class="sxs-lookup"><span data-stu-id="60668-149">Upload</span></span>

<span data-ttu-id="60668-150">若要讓應用程式可供貴組織 App Store 中的使用者使用，請上傳應用程式。</span><span class="sxs-lookup"><span data-stu-id="60668-150">To make the app available to users in your organization's app store, upload the app.</span></span> <span data-ttu-id="60668-151">您可以在系統管理中心的管理應用程式<a href="/microsoftteams/manage-apps" target="_blank">頁面上Microsoft Teams</a>這項功能。</span><span class="sxs-lookup"><span data-stu-id="60668-151">You can do this on the <a href="/microsoftteams/manage-apps" target="_blank">Manage apps</a> page of the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="60668-152">在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 **Teams 應用程式** > **管理應用程式**。</span><span class="sxs-lookup"><span data-stu-id="60668-152">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="60668-153">按一下 **Upload**，按一下 [**選取檔案**，然後選取您從開發人員收到的應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="60668-153">Click **Upload**, click **Select a file**, and then select the app package that you received from the developer.</span></span>

   ![在系統管理中心上傳應用程式的螢幕擷取畫面](media/manage-your-lob-apps-upload-new-app.png) 

## <a name="set-up-and-manage"></a><span data-ttu-id="60668-155">設定和管理</span><span class="sxs-lookup"><span data-stu-id="60668-155">Set up and manage</span></span>

### <a name="control-access-to-the-app"></a><span data-ttu-id="60668-156">控制應用程式的存取權</span><span class="sxs-lookup"><span data-stu-id="60668-156">Control access to the app</span></span>

<span data-ttu-id="60668-157">根據預設，貴組織的所有使用者都可以存取貴組織 App Store 中的應用程式。</span><span class="sxs-lookup"><span data-stu-id="60668-157">By default, all users in your organization can access the app in your organization's app store.</span></span> <span data-ttu-id="60668-158">若要限制及控制誰有權使用應用程式，您可以建立並指派應用程式權限原則。</span><span class="sxs-lookup"><span data-stu-id="60668-158">To restrict and control who has permission to use the app, you can create and assign an app permission policy.</span></span> <span data-ttu-id="60668-159">若要深入了解，請參閱<a href="/microsoftteams/teams-app-permission-policies" target="_blank">管理 Teams 中的應用程式權限原則</a>。</span><span class="sxs-lookup"><span data-stu-id="60668-159">To learn more, see <a href="/microsoftteams/teams-app-permission-policies" target="_blank">Manage app permission policies in Teams</a>.</span></span>

### <a name="pin-and-install-the-app-for-users-to-discover"></a><span data-ttu-id="60668-160">釘上並安裝應用程式供使用者探索</span><span class="sxs-lookup"><span data-stu-id="60668-160">Pin and install the app for users to discover</span></span>

<span data-ttu-id="60668-161">根據預設，使用者若要尋找應用程式，必須前往貴組織的 App Store 並流覽或搜尋。</span><span class="sxs-lookup"><span data-stu-id="60668-161">By default, for users to find the app they have to go to your organization's app store and browse or search for it.</span></span> <span data-ttu-id="60668-162">若要讓使用者輕鬆取得應用程式，您可以將應用程式釘到 Teams。</span><span class="sxs-lookup"><span data-stu-id="60668-162">To make it easy for users to get to the app, you can pin the app to the app bar in Teams.</span></span> <span data-ttu-id="60668-163">若要這麼做，請建立應用程式設定策略並指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="60668-163">To do this, create an app setup policy and assign it to users.</span></span> <span data-ttu-id="60668-164">若要深入了解，請參閱<a href="/microsoftteams/teams-app-setup-policies" target="_blank">管理 Teams 中的應用程式設定原則</a>。</span><span class="sxs-lookup"><span data-stu-id="60668-164">To learn more, see <a href="/microsoftteams/teams-app-setup-policies" target="_blank">Manage app setup policies in Teams</a>.</span></span>

### <a name="search-the-audit-log-for-teams-app-events"></a><span data-ttu-id="60668-165">搜尋稽核記錄Teams應用程式事件</span><span class="sxs-lookup"><span data-stu-id="60668-165">Search the audit log for Teams app events</span></span>

<span data-ttu-id="60668-166">您可以搜尋稽核記錄來Teams組織中應用程式活動。</span><span class="sxs-lookup"><span data-stu-id="60668-166">You can search the audit log to view Teams apps activity in your organization.</span></span> <span data-ttu-id="60668-167">若要深入瞭解如何搜尋稽核記錄，以及查看記錄在稽核記錄中的 Teams 活動清單，請參閱在 Teams 中搜尋稽核<a href="/microsoftteams/audit-log-events" target="_blank">記錄</a>。</span><span class="sxs-lookup"><span data-stu-id="60668-167">To learn more about how to search the audit log and to see a list of Teams activities that are logged in the audit log, see <a href="/microsoftteams/audit-log-events" target="_blank">Search the audit log for events in Teams</a>.</span></span>

<span data-ttu-id="60668-168">在您可以搜尋稽核記錄檔之前，您必須先在<a href="https://protection.office.com" target="_blank">安全性與合規性中心</a>中開啟稽核。</span><span class="sxs-lookup"><span data-stu-id="60668-168">Before you can search the audit log, you have to first turn on auditing in the <a href="https://protection.office.com" target="_blank">Security & Compliance Center</a>.</span></span> <span data-ttu-id="60668-169">如需深入了解，請參閱<a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">開啟或關閉稽核記錄</a>。</span><span class="sxs-lookup"><span data-stu-id="60668-169">To learn more, see <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">Turn audit log search on or off</a>.</span></span> <span data-ttu-id="60668-170">請記住，只有當您開啟稽核時，才能使用稽核資料。</span><span class="sxs-lookup"><span data-stu-id="60668-170">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="discover-and-adopt"></a><span data-ttu-id="60668-171">探索及採用</span><span class="sxs-lookup"><span data-stu-id="60668-171">Discover and adopt</span></span>

<span data-ttu-id="60668-172">擁有應用程式許可權的使用者可以在貴組織的 App Store 中找到它。</span><span class="sxs-lookup"><span data-stu-id="60668-172">Users who have permissions to the app can find it in your organization's app store.</span></span> <span data-ttu-id="60668-173">前往 **應用程式頁面上 *的*** 專為您的組織名稱建立，以尋找貴組織的自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="60668-173">Go to **Built for *Your Organization Name*** on the Apps page to find your organization's custom apps.</span></span>

![<span data-ttu-id="60668-174">顯示已發佈應用程式之應用程式之應用程式頁面的螢幕擷取畫面</span><span class="sxs-lookup"><span data-stu-id="60668-174">Screenshot of Apps page showing published app</span></span> ](media/custom-app-lifecycle-discovery.png)

<span data-ttu-id="60668-175">如果您建立並指派應用程式設定策略，應用程式會釘到 Teams 中的應用程式欄，以便指派該策略的使用者輕鬆存取。</span><span class="sxs-lookup"><span data-stu-id="60668-175">If you created and assigned an app setup policy, the app is pinned to the app bar in Teams for easy access for those users who were assigned the policy.</span></span>

## <a name="update"></a><span data-ttu-id="60668-176">更新</span><span class="sxs-lookup"><span data-stu-id="60668-176">Update</span></span>

<span data-ttu-id="60668-177">若要更新應用程式，開發人員應該繼續遵循開發和驗證[區段](#develop)[的步驟](#validate)。</span><span class="sxs-lookup"><span data-stu-id="60668-177">To update an app, developers should continue to follow the steps in the [Develop](#develop) and [Validate](#validate) sections.</span></span>

<span data-ttu-id="60668-178">您可以在系統管理中心的管理應用程式頁面上更新Microsoft Teams應用程式。</span><span class="sxs-lookup"><span data-stu-id="60668-178">You can update the app on the Manage apps page in the Microsoft Teams admin center.</span></span> <span data-ttu-id="60668-179">若要這麼做，在系統管理中心的左側導Microsoft Teams，請前往管理Teams \*\*\*\*  >  **應用程式**。</span><span class="sxs-lookup"><span data-stu-id="60668-179">To do this, in the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="60668-180">按一下應用程式名稱，然後按一下 [ **更新**。</span><span class="sxs-lookup"><span data-stu-id="60668-180">Click the app name, and then click **Update**.</span></span> <span data-ttu-id="60668-181">這麼做會取代現有的應用程式，而且所有應用程式權限原則及應用程式設定策略會持續為更新的應用程式強制執行。</span><span class="sxs-lookup"><span data-stu-id="60668-181">Doing this replaces the existing app, and all app permission policies and app setup policies remain enforced for the updated app.</span></span>

### <a name="end-user-update-experience"></a><span data-ttu-id="60668-182">使用者更新體驗</span><span class="sxs-lookup"><span data-stu-id="60668-182">End user update experience</span></span>

<span data-ttu-id="60668-183">在大多數情況下，完成應用程式更新後，系統會自動為使用者顯示新版本。</span><span class="sxs-lookup"><span data-stu-id="60668-183">In most cases, after you complete an app update the new version automatically appears for end users.</span></span> <span data-ttu-id="60668-184">不過，系統對 Microsoft Teams<a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">清單</a>有一些更新需要使用者接受才能完成：</span><span class="sxs-lookup"><span data-stu-id="60668-184">However, there are some updates to the <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams manifest</a> that require user acceptance to complete:</span></span>

* <span data-ttu-id="60668-185">已新增或移除 Bot</span><span class="sxs-lookup"><span data-stu-id="60668-185">A bot was added or removed</span></span>
* <span data-ttu-id="60668-186">現有 Bot 的 「botId」 屬性已變更</span><span class="sxs-lookup"><span data-stu-id="60668-186">An existing bot's "botId" property changed</span></span>
* <span data-ttu-id="60668-187">已變更現有 Bot 的 "isNotificationOnly" 屬性</span><span class="sxs-lookup"><span data-stu-id="60668-187">An existing bot's "isNotificationOnly" property changed</span></span>
* <span data-ttu-id="60668-188">Bot 的「支援Files」屬性已變更</span><span class="sxs-lookup"><span data-stu-id="60668-188">The bot's "supportsFiles" property changed</span></span>
* <span data-ttu-id="60668-189">已新增或移除訊息擴充功能</span><span class="sxs-lookup"><span data-stu-id="60668-189">A Messaging extension was added or removed</span></span>
* <span data-ttu-id="60668-190">已新增連接器</span><span class="sxs-lookup"><span data-stu-id="60668-190">A new connector was added</span></span>
* <span data-ttu-id="60668-191">已新增靜態定位停駐點</span><span class="sxs-lookup"><span data-stu-id="60668-191">A new static tab was added</span></span>
* <span data-ttu-id="60668-192">已新增可配置的 Tab</span><span class="sxs-lookup"><span data-stu-id="60668-192">A new configurable tab was added</span></span>
* <span data-ttu-id="60668-193">「webApplicationInfo」中的屬性已變更</span><span class="sxs-lookup"><span data-stu-id="60668-193">Properties inside "webApplicationInfo" changed</span></span>

![應用程式清單的螢幕擷取畫面，顯示提供新版本的應用程式](media/manage-your-custom-apps-update1.png)

![應用程式升級選項的螢幕擷取畫面](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a><span data-ttu-id="60668-196">相關主題</span><span class="sxs-lookup"><span data-stu-id="60668-196">Related topics</span></span>

- [<span data-ttu-id="60668-197">發佈透過應用程式提交 API Teams提交的自訂應用程式</span><span class="sxs-lookup"><span data-stu-id="60668-197">Publish a custom app submitted through the Teams App Submission API</span></span>](submit-approve-custom-apps.md)
- [<span data-ttu-id="60668-198">在系統管理中心管理Microsoft Teams應用程式</span><span class="sxs-lookup"><span data-stu-id="60668-198">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="60668-199">在 Teams 中管理自訂應用程式原則和設定</span><span class="sxs-lookup"><span data-stu-id="60668-199">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
- [<span data-ttu-id="60668-200">在 Teams 中管理應用程式權限原則</span><span class="sxs-lookup"><span data-stu-id="60668-200">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
- [<span data-ttu-id="60668-201">在 Teams 中管理應用程式設定原則</span><span class="sxs-lookup"><span data-stu-id="60668-201">Manage app setup policies in Teams</span></span>](teams-app-setup-policies.md)