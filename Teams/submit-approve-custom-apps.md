---
title: 使用 Teams App 提交 API 來提交和核准您的自訂應用程式
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
description: 瞭解如何核准使用 Microsoft Teams 中的 Teams App 提交 API 提交的自訂應用程式。
ms.openlocfilehash: 8c12d93a0b4420fd248064c69308e8049dc6326f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116971"
---
# <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a><span data-ttu-id="666b4-103">發佈透過 Teams App 提交 API 提交的自訂應用程式</span><span class="sxs-lookup"><span data-stu-id="666b4-103">Publish a custom app submitted through the Teams App Submission API</span></span>

## <a name="overview"></a><span data-ttu-id="666b4-104">概觀</span><span class="sxs-lookup"><span data-stu-id="666b4-104">Overview</span></span>

> [!NOTE]
> <span data-ttu-id="666b4-105">當您發佈自訂 Teams App 時，組織 App Store 中的使用者可以使用它。</span><span class="sxs-lookup"><span data-stu-id="666b4-105">When you publish a custom Teams app, it's available to users in your organization's app store.</span></span> <span data-ttu-id="666b4-106">發佈自訂應用程式的方法有兩種，而使用方式取決於您取得應用程式的方式。</span><span class="sxs-lookup"><span data-stu-id="666b4-106">There are two ways to publish a custom app and the way that you use depends on how you get the app.</span></span> <span data-ttu-id="666b4-107">**本文著重于如何核准** 及發佈開發人員透過 Teams App 提交 API 提交的自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="666b4-107">**This article focuses on how to approve and publish a custom app that a developer submits through the Teams App Submission API**.</span></span> <span data-ttu-id="666b4-108">當開發人員以 .zip 格式傳送應用程式套件時，會使用另一種方法 ，即上傳自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="666b4-108">The other method, uploading a custom app, is used when a developer sends you an app package in .zip format.</span></span> <span data-ttu-id="666b4-109">若要深入瞭解這個方法，請參閱上傳應用程式套件 <a href="/microsoftteams/upload-custom-apps" target="_blank">來發佈自訂應用程式</a>。</span><span class="sxs-lookup"><span data-stu-id="666b4-109">To learn more about that method, see <a href="/microsoftteams/upload-custom-apps" target="_blank">Publish a custom app by uploading an app package</a>.</span></span> <span data-ttu-id="666b4-110">GCC 租使用者無法使用核准應用程式小工具。</span><span class="sxs-lookup"><span data-stu-id="666b4-110">The approve app widget isn't available in GCC tenants.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="666b4-111">這個方法目前不適用於 GCC 環境。</span><span class="sxs-lookup"><span data-stu-id="666b4-111">This method is not currently available for GCC environments.</span></span> <span data-ttu-id="666b4-112">您必須使用上傳 *自訂應用程式的方法* 。</span><span class="sxs-lookup"><span data-stu-id="666b4-112">You must use the *uploading a custom app* method.</span></span>

<span data-ttu-id="666b4-113">本文提供如何將 Teams 應用程式從開發到部署到探索的端對端指南。</span><span class="sxs-lookup"><span data-stu-id="666b4-113">This article provides end-to-end guidance for how to take your Teams app from development to deployment to discovery.</span></span> <span data-ttu-id="666b4-114">您將概觀瞭解 Teams 在應用程式生命週期內提供的連接體驗，以簡化如何開發、部署及管理貴組織 App Store 中的自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="666b4-114">You'll get an overview of the connected experiences that Teams provides across the app lifecycle to streamline how to develop, deploy, and manage custom apps in your organization's app store.</span></span>

<span data-ttu-id="666b4-115">我們將涵蓋生命週期的每一個步驟，包括開發人員如何使用 Teams App 提交 API 將自訂應用程式直接提交至 Microsoft Teams 系統管理中心，以便您進行審閱和核准、如何設定管理貴組織使用者相關應用程式的政策，以及使用者如何在 Teams 中探索這些 App。</span><span class="sxs-lookup"><span data-stu-id="666b4-115">We'll cover each step of the lifecycle, including how developers can use the Teams App Submission API to submit custom apps directly to the Microsoft Teams admin center for you to review and approve, how to set policies to manage apps for users in your organization, and how your users discover them in Teams.</span></span>

![從開發到部署的應用程式概觀](media/custom-app-lifecycle.png)

<span data-ttu-id="666b4-117">本指南著重于應用程式的 Teams 層面，適用于系統管理員和 IT 專業人員。</span><span class="sxs-lookup"><span data-stu-id="666b4-117">This guidance focuses on the Teams aspects of the app and is intended for admins and IT pros.</span></span> <span data-ttu-id="666b4-118">有關開發 Teams 應用程式的資訊，請參閱 <a href="/microsoftteams/platform" target="_blank">Teams 開發人員檔</a>。</span><span class="sxs-lookup"><span data-stu-id="666b4-118">For information about developing Teams apps, see the <a href="/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

## <a name="develop"></a><span data-ttu-id="666b4-119">開發</span><span class="sxs-lookup"><span data-stu-id="666b4-119">Develop</span></span>

### <a name="create-the-app"></a><span data-ttu-id="666b4-120">建立應用程式</span><span class="sxs-lookup"><span data-stu-id="666b4-120">Create the app</span></span>

<span data-ttu-id="666b4-121">Microsoft Teams 開發人員平臺讓開發人員能輕鬆整合您自己的應用程式和服務，以提高生產力、更快速地做出決策，並圍繞現有內容和工作流程建立共同作業。</span><span class="sxs-lookup"><span data-stu-id="666b4-121">The Microsoft Teams developer platform makes it easy for developers to integrate your own apps and services to improve productivity, make decisions faster, and create collaboration around existing content and workflows.</span></span> <span data-ttu-id="666b4-122">Teams 平臺內建的應用程式是 Teams 用戶端與服務與工作流程之間的橋樑，直接將它們納入您的共同合作平臺中。</span><span class="sxs-lookup"><span data-stu-id="666b4-122">Apps built on the Teams platform are bridges between the Teams client and your services and workflows, bringing them directly into the context of your collaboration platform.</span></span> <span data-ttu-id="666b4-123">若要詳細資訊，請前往 <a href="/microsoftteams/platform" target="_blank">Teams 開發人員檔</a>。</span><span class="sxs-lookup"><span data-stu-id="666b4-123">For more information, go to the <a href="/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

### <a name="submit-the-app"></a><span data-ttu-id="666b4-124">提交應用程式</span><span class="sxs-lookup"><span data-stu-id="666b4-124">Submit the app</span></span>

<span data-ttu-id="666b4-125">當應用程式可供生產使用時，開發人員可以使用 Teams App 提交 API 提交應用程式，此 API 可稱為 <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank" target="_blank">Graph API、</a>整合式開發環境 (IDE) 例如 Visual Studio 程式碼，或 Power Apps 和 Power Virtual Agents 等平臺。</span><span class="sxs-lookup"><span data-stu-id="666b4-125">When the app is ready for use in production, the developer can submit the app using the Teams App Submission API, which can be called from <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank" target="_blank">Graph API</a>, an integrated development environment (IDE) such as Visual Studio Code, or a platform such as Power Apps and Power Virtual Agents.</span></span> <span data-ttu-id="666b4-126">這麼做之後，App 就可以在<a href="/microsoftteams/manage-apps" target="_blank"></a>Microsoft Teams 系統管理中心的管理應用程式頁面上使用，而您的系統管理員可以在這裡進行審核和核准。</span><span class="sxs-lookup"><span data-stu-id="666b4-126">Doing this makes the app available on the <a href="/microsoftteams/manage-apps" target="_blank">Manage apps</a> page of the Microsoft Teams admin center, where you, the admin, can review and approve it.this</span></span>

<span data-ttu-id="666b4-127">Microsoft Graph 內建的 <a href="/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">Teams</a>App 提交 API 可讓您的組織在所選擇的平臺上開發，並自動化 Teams 上自訂應用程式的提交至核准程式。</span><span class="sxs-lookup"><span data-stu-id="666b4-127">The Teams App Submission API, <a href="/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">built on Microsoft Graph</a>, allows your organization to develop on the platform of your choice and automates the submission-to-approval process for custom apps on Teams.</span></span>

<span data-ttu-id="666b4-128">以下範例說明此 App 提交步驟在 Visual Studio Code 中的外觀：</span><span class="sxs-lookup"><span data-stu-id="666b4-128">Here's an example of what this app submission step looks like in Visual Studio Code:</span></span>

![在 Visual Studio 程式碼中提交應用程式](media/custom-app-lifecycle-submit-app.png)

<span data-ttu-id="666b4-130">請記住，這尚未將應用程式發佈至組織的 App Store。</span><span class="sxs-lookup"><span data-stu-id="666b4-130">Keep in mind that this doesn't publish the app to your organization's app store yet.</span></span> <span data-ttu-id="666b4-131">此步驟將應用程式提交至 Microsoft Teams 系統管理中心，您可以在此核准 App 發佈到貴組織的 App Store。</span><span class="sxs-lookup"><span data-stu-id="666b4-131">This step submits the app to the Microsoft Teams admin center where you can approve it for publishing to your organization's app store.</span></span>

<span data-ttu-id="666b4-132">有關使用 Graph API 提交應用程式之詳細資訊，請參閱 <a href="/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">這裡</a>。</span><span class="sxs-lookup"><span data-stu-id="666b4-132">For more information about using the Graph API to submit apps, see <a href="/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">here</a>.</span></span>

## <a name="validate"></a><span data-ttu-id="666b4-133">驗證</span><span class="sxs-lookup"><span data-stu-id="666b4-133">Validate</span></span>

<span data-ttu-id="666b4-134">Microsoft Teams <a href="/microsoftteams/manage-apps" target="_blank">系統</a>管理中心中的 (頁面位於左側流覽中，請前往 **Teams 應用程式** 管理應用程式) ，讓您查看貴組織的所有 Teams  >  應用程式。</span><span class="sxs-lookup"><span data-stu-id="666b4-134">The <a href="/microsoftteams/manage-apps" target="_blank">Manage apps</a> page in the Microsoft Teams admin center (in the left navigation, go to **Teams apps** > **Manage apps**), gives you a view into all Teams apps for your organization.</span></span> <span data-ttu-id="666b4-135">頁面 **頂端的** 擱置核准小工具可讓您知道何時提交自訂應用程式供核准。</span><span class="sxs-lookup"><span data-stu-id="666b4-135">The **Pending approval** widget at the top of the page lets you know when a custom app is submitted for approval.</span></span>

<span data-ttu-id="666b4-136">在表格中，新提交的應用程式會自動顯示已提交和封鎖狀態的 **發佈狀態**。  </span><span class="sxs-lookup"><span data-stu-id="666b4-136">In the table, a newly submitted app automatically shows a **Publishing status** of **Submitted** and **Status** of **Blocked**.</span></span> <span data-ttu-id="666b4-137">您可以 **以遞減** 順序排序發佈狀態列，以快速找到應用程式。</span><span class="sxs-lookup"><span data-stu-id="666b4-137">You can sort the **Publishing status** column in descending order to quickly find the app.</span></span>

![<span data-ttu-id="666b4-138">發佈狀態</span><span class="sxs-lookup"><span data-stu-id="666b4-138">publishing status</span></span> ](media/custom-app-lifecycle-validate-app.png)

<span data-ttu-id="666b4-139">按一下應用程式名稱以前往應用程式詳細資料頁面。</span><span class="sxs-lookup"><span data-stu-id="666b4-139">Click the app name to go to the app details page.</span></span> <span data-ttu-id="666b4-140">在關於 **的** 選項卡上，您可以查看應用程式的詳細資訊，包括描述、狀態、提交者及應用程式識別碼。</span><span class="sxs-lookup"><span data-stu-id="666b4-140">On the **About** tab, you can view details about the app, including description, status, submitter, and app ID.</span></span>

![提交應用程式的應用程式詳細資料頁面](media/custom-app-lifecycle-app-details.png)

<span data-ttu-id="666b4-142">有關使用 Graph API 檢查發佈狀態之詳細資訊，請參閱<a href="/graph/api/appcatalogs-list-teamsapps?tabs=http&view=graph-rest-beta#example-3-find-application-based-on-the-teams-app-manifest-id" target="_blank">這裡</a>。</span><span class="sxs-lookup"><span data-stu-id="666b4-142">For more information about using the Graph API to check the **Publishing status**, see <a href="/graph/api/appcatalogs-list-teamsapps?tabs=http&view=graph-rest-beta#example-3-find-application-based-on-the-teams-app-manifest-id" target="_blank">here</a>.</span></span>

## <a name="publish"></a><span data-ttu-id="666b4-143">發佈</span><span class="sxs-lookup"><span data-stu-id="666b4-143">Publish</span></span>

<span data-ttu-id="666b4-144">當您準備好要讓使用者使用 App 時，請發佈應用程式。</span><span class="sxs-lookup"><span data-stu-id="666b4-144">When you're ready to make the app available to users, publish the app.</span></span>

1. <span data-ttu-id="666b4-145">在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 **Teams 應用程式** > **管理應用程式**。</span><span class="sxs-lookup"><span data-stu-id="666b4-145">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="666b4-146">按一下應用程式名稱以前往應用程式詳細資料頁面，然後在 [發佈 **狀態** > 方塊中，選取 [ **發佈**> 。</span><span class="sxs-lookup"><span data-stu-id="666b4-146">Click the app name to go to the app details page, and then in the **Publishing status** box, select **Publish**.</span></span>

    <span data-ttu-id="666b4-147">發佈應用程式之後，發佈 **狀態會變更\*\*\*\*為已發佈**，而狀態 **會自動** 變更為 **允許**。</span><span class="sxs-lookup"><span data-stu-id="666b4-147">After you publish the app, the **Publishing status** changes to **Published** and the **Status** automatically changes to **Allowed**.</span></span>

## <a name="set-up-and-manage"></a><span data-ttu-id="666b4-148">設定和管理</span><span class="sxs-lookup"><span data-stu-id="666b4-148">Set up and manage</span></span>

### <a name="control-access-to-the-app"></a><span data-ttu-id="666b4-149">控制應用程式的存取權</span><span class="sxs-lookup"><span data-stu-id="666b4-149">Control access to the app</span></span>

<span data-ttu-id="666b4-150">根據預設，貴組織的所有使用者都可以存取貴組織 App Store 中的應用程式。</span><span class="sxs-lookup"><span data-stu-id="666b4-150">By default, all users in your organization can access the app in your organization's app store.</span></span> <span data-ttu-id="666b4-151">若要限制及控制誰有權使用應用程式，您可以建立並指派應用程式權限原則。</span><span class="sxs-lookup"><span data-stu-id="666b4-151">To restrict and control who has permission to use the app, you can create and assign an app permission policy.</span></span> <span data-ttu-id="666b4-152">如需深入了解，請參閱<a href="/microsoftteams/teams-app-permission-policies" target="_blank">管理 Teams 中的應用程式權限原則</a>。</span><span class="sxs-lookup"><span data-stu-id="666b4-152">To learn more, see <a href="/microsoftteams/teams-app-permission-policies" target="_blank">Manage app permission policies in Teams</a>.</span></span>

### <a name="pin-and-install-the-app-for-users-to-discover"></a><span data-ttu-id="666b4-153">釘上並安裝應用程式供使用者探索</span><span class="sxs-lookup"><span data-stu-id="666b4-153">Pin and install the app for users to discover</span></span>

<span data-ttu-id="666b4-154">根據預設，使用者若要尋找應用程式，必須前往貴組織的 App Store 並流覽或搜尋。</span><span class="sxs-lookup"><span data-stu-id="666b4-154">By default, for users to find the app they have to go to your organization's app store and browse or search for it.</span></span> <span data-ttu-id="666b4-155">若要讓使用者輕鬆取得應用程式，您可以將應用程式釘到 Teams 中的應用程式欄。</span><span class="sxs-lookup"><span data-stu-id="666b4-155">To make it easy for users to get to the app, you can pin the app to the app bar in Teams.</span></span> <span data-ttu-id="666b4-156">若要這麼做，請建立應用程式設定策略並指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="666b4-156">To do this, create an app setup policy and assign it to users.</span></span> <span data-ttu-id="666b4-157">若要深入了解，請參閱<a href="/microsoftteams/teams-app-setup-policies" target="_blank">管理 Teams 中的應用程式設定原則</a>。</span><span class="sxs-lookup"><span data-stu-id="666b4-157">To learn more, see <a href="/microsoftteams/teams-app-setup-policies" target="_blank">Manage app setup policies in Teams</a>.</span></span>

### <a name="search-the-audit-log-for-teams-app-events"></a><span data-ttu-id="666b4-158">搜尋 Teams App 事件的稽核記錄</span><span class="sxs-lookup"><span data-stu-id="666b4-158">Search the audit log for Teams app events</span></span>

<span data-ttu-id="666b4-159">您可以搜尋稽核記錄來查看貴組織的 Teams 應用程式活動。</span><span class="sxs-lookup"><span data-stu-id="666b4-159">You can search the audit log to view Teams apps activity in your organization.</span></span> <span data-ttu-id="666b4-160">若要深入瞭解如何搜尋稽核記錄，以及查看記錄在稽核記錄中的 Teams 活動清單，請參閱在 Teams 中搜尋稽核 <a href="/microsoftteams/audit-log-events" target="_blank">記錄中的事件</a>。</span><span class="sxs-lookup"><span data-stu-id="666b4-160">To learn more about how to search the audit log and to see a list of Teams activities that are logged in the audit log, see <a href="/microsoftteams/audit-log-events" target="_blank">Search the audit log for events in Teams</a>.</span></span>

<span data-ttu-id="666b4-161">在您可以搜尋稽核記錄檔之前，您必須先在<a href="https://protection.office.com" target="_blank">安全性與合規性中心</a>中開啟稽核。</span><span class="sxs-lookup"><span data-stu-id="666b4-161">Before you can search the audit log, you have to first turn on auditing in the <a href="https://protection.office.com" target="_blank">Security & Compliance Center</a>.</span></span> <span data-ttu-id="666b4-162">如需深入了解，請參閱<a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">開啟或關閉稽核記錄</a>。</span><span class="sxs-lookup"><span data-stu-id="666b4-162">To learn more, see <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">Turn audit log search on or off</a>.</span></span> <span data-ttu-id="666b4-163">請記住，只有當您開啟稽核時，才能使用稽核資料。</span><span class="sxs-lookup"><span data-stu-id="666b4-163">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="discover-and-adopt"></a><span data-ttu-id="666b4-164">探索及採用</span><span class="sxs-lookup"><span data-stu-id="666b4-164">Discover and adopt</span></span>

<span data-ttu-id="666b4-165">擁有應用程式許可權的使用者可以在貴組織的 App Store 中找到它。</span><span class="sxs-lookup"><span data-stu-id="666b4-165">Users who have permissions to the app can find it in your organization's app store.</span></span> <span data-ttu-id="666b4-166">前往 **應用程式頁面上 *的*** 專為您的組織名稱建立，以尋找貴組織的自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="666b4-166">Go to **Built for *Your Organization Name*** on the Apps page to find your organization's custom apps.</span></span>

![<span data-ttu-id="666b4-167">顯示已發佈 App 的 App 頁面</span><span class="sxs-lookup"><span data-stu-id="666b4-167">Apps page showing published app</span></span> ](media/custom-app-lifecycle-discovery.png)

<span data-ttu-id="666b4-168">如果您建立並指派了應用程式設定策略，應用程式會釘到 Teams 中的應用程式欄，以便指派該策略的使用者輕鬆存取。</span><span class="sxs-lookup"><span data-stu-id="666b4-168">If you created and assigned an app setup policy, the app is pinned to the app bar in Teams for easy access for those users who were assigned the policy.</span></span>

## <a name="update"></a><span data-ttu-id="666b4-169">更新</span><span class="sxs-lookup"><span data-stu-id="666b4-169">Update</span></span>

<span data-ttu-id="666b4-170">若要更新應用程式，開發人員應該繼續遵循開發區段 [的步驟](#develop) 。</span><span class="sxs-lookup"><span data-stu-id="666b4-170">To update an app, developers should continue to follow the steps in the [Develop](#develop) section.</span></span>

<span data-ttu-id="666b4-171">當開發人員將更新提交到已發佈的自訂 App 時，系統就會在管理應用程式頁面的擱置 **核准** 小工具 <a href="/microsoftteams/manage-apps" target="_blank">中收到通知</a> 。</span><span class="sxs-lookup"><span data-stu-id="666b4-171">When the developer submits an update to a published custom app, you'll get notified in the **Pending approval** widget of the <a href="/microsoftteams/manage-apps" target="_blank">Manage apps</a> page.</span></span> <span data-ttu-id="666b4-172">在表格中， **應用程式的** 發佈狀態會設定為已 **提交更新**。</span><span class="sxs-lookup"><span data-stu-id="666b4-172">In the table, the **Publishing status** of the app will be set to **Update submitted**.</span></span>

![<span data-ttu-id="666b4-173">顯示擱置要求和應用程式狀態的管理應用程式頁面</span><span class="sxs-lookup"><span data-stu-id="666b4-173">Manage apps page showing pending requests and app status</span></span> ](media/custom-app-lifecycle-update-submitted.png)

<span data-ttu-id="666b4-174">若要審查併發布應用程式更新：</span><span class="sxs-lookup"><span data-stu-id="666b4-174">To review and publish an app update:</span></span>

1. <span data-ttu-id="666b4-175">在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 **Teams 應用程式** > **管理應用程式**。</span><span class="sxs-lookup"><span data-stu-id="666b4-175">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="666b4-176">按一下應用程式名稱以前往應用程式詳細資料頁面，然後選取 [可用的更新來查看更新詳細資料。</span><span class="sxs-lookup"><span data-stu-id="666b4-176">Click the app name to go to the app details page, and then select **Update available** to review details of the update.</span></span>

    ![應用程式詳細資料頁面](media/custom-app-lifecycle-update-app.png)
3. <span data-ttu-id="666b4-178">當您準備好時，請選取 **發佈** 以發佈更新。</span><span class="sxs-lookup"><span data-stu-id="666b4-178">When you're ready, select **Publish** to publish the update.</span></span> <span data-ttu-id="666b4-179">這麼做會取代現有的應用程式、更新版本號碼，以及將 **發佈狀態變更** 為 **已發佈**。</span><span class="sxs-lookup"><span data-stu-id="666b4-179">Doing this replaces the existing app, updates the version number, and changes the **Publishing status** to **Published**.</span></span> <span data-ttu-id="666b4-180">對於更新的應用程式，所有應用程式權限原則與應用程式設定策略仍然會強制執行。</span><span class="sxs-lookup"><span data-stu-id="666b4-180">All app permission policies and app setup policies remain enforced for the updated app.</span></span>

    <span data-ttu-id="666b4-181">如果您拒絕更新，應用程式的較舊版本會維持發佈狀態。</span><span class="sxs-lookup"><span data-stu-id="666b4-181">If you reject the update, the earlier version of the app remains published.</span></span>

<span data-ttu-id="666b4-182">請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="666b4-182">Keep in mind the following:</span></span>

- <span data-ttu-id="666b4-183">應用程式核准後，任何一個人都可以將更新提交至應用程式。</span><span class="sxs-lookup"><span data-stu-id="666b4-183">When an app is approved, any one can submit an update to the app.</span></span> <span data-ttu-id="666b4-184">這表示其他開發人員 ，包括原本提交應用程式的開發人員，可以提交更新至應用程式。</span><span class="sxs-lookup"><span data-stu-id="666b4-184">This means other developers, including the developer who originally submitted the app, can submit an update to the app.</span></span>
- <span data-ttu-id="666b4-185">當開發人員提交 App 且要求擱置中時，只有相同的開發人員可以提交更新至應用程式。</span><span class="sxs-lookup"><span data-stu-id="666b4-185">When a developer submits an app and the request is pending, only that same developer can submit an update to the app.</span></span> <span data-ttu-id="666b4-186">其他開發人員只能在應用程式核准後提交更新。</span><span class="sxs-lookup"><span data-stu-id="666b4-186">Other developers can submit an update only after the app is approved.</span></span>

<span data-ttu-id="666b4-187">有關使用 Graph API 更新應用程式之詳細資訊，請參閱 <a href="/graph/api/teamsapp-update?view=graph-rest-beta#example-2-update-a-previously-reviewed-and-published-application-to-the-teams-app-catalog" target="_blank">這裡</a>。</span><span class="sxs-lookup"><span data-stu-id="666b4-187">For more information about using the Graph API to update apps, see <a href="/graph/api/teamsapp-update?view=graph-rest-beta#example-2-update-a-previously-reviewed-and-published-application-to-the-teams-app-catalog" target="_blank">here</a>.</span></span>

### <a name="update-experience-for-users"></a><span data-ttu-id="666b4-188">使用者的更新體驗</span><span class="sxs-lookup"><span data-stu-id="666b4-188">Update experience for users</span></span>

<span data-ttu-id="666b4-189">在大多數的情況下，發佈 App 更新之後，新版本會自動顯示給使用者。</span><span class="sxs-lookup"><span data-stu-id="666b4-189">In most cases, after you publish an app update, the new version automatically appears for users.</span></span> <span data-ttu-id="666b4-190">不過，Microsoft <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Teams</a> 清單有一些更新需要使用者接受才能完成：</span><span class="sxs-lookup"><span data-stu-id="666b4-190">However, there are some updates to the <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams manifest</a> that require user acceptance to complete:</span></span>

* <span data-ttu-id="666b4-191">已新增或移除 Bot</span><span class="sxs-lookup"><span data-stu-id="666b4-191">A bot was added or removed</span></span>
* <span data-ttu-id="666b4-192">現有 Bot 的「botId」屬性已變更</span><span class="sxs-lookup"><span data-stu-id="666b4-192">An existing bot's "botId" property changed</span></span>
* <span data-ttu-id="666b4-193">已變更現有 Bot 的 "isNotificationOnly" 屬性</span><span class="sxs-lookup"><span data-stu-id="666b4-193">An existing bot's "isNotificationOnly" property changed</span></span>
* <span data-ttu-id="666b4-194">Bot 的「支援檔」屬性已變更</span><span class="sxs-lookup"><span data-stu-id="666b4-194">The bot's "supportsFiles" property changed</span></span>
* <span data-ttu-id="666b4-195">已新增或移除訊息擴充功能</span><span class="sxs-lookup"><span data-stu-id="666b4-195">A messaging extension was added or removed</span></span>
* <span data-ttu-id="666b4-196">已新增連接器</span><span class="sxs-lookup"><span data-stu-id="666b4-196">A new connector was added</span></span>
* <span data-ttu-id="666b4-197">已新增靜態定位停駐點</span><span class="sxs-lookup"><span data-stu-id="666b4-197">A new static tab was added</span></span>
* <span data-ttu-id="666b4-198">已新增可配置的選項卡</span><span class="sxs-lookup"><span data-stu-id="666b4-198">A new configurable tab was added</span></span>
* <span data-ttu-id="666b4-199">「webApplicationInfo」中的屬性已變更</span><span class="sxs-lookup"><span data-stu-id="666b4-199">Properties inside "webApplicationInfo" changed</span></span>

![提供新版本](media/manage-your-custom-apps-update1.png)

![應用程式的升級選項](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a><span data-ttu-id="666b4-202">相關主題</span><span class="sxs-lookup"><span data-stu-id="666b4-202">Related topics</span></span>

- [<span data-ttu-id="666b4-203">上傳應用程式套件來發佈自訂應用程式</span><span class="sxs-lookup"><span data-stu-id="666b4-203">Publish a custom app by uploading an app package</span></span>](upload-custom-apps.md)
- [<span data-ttu-id="666b4-204">在 Microsoft Teams 系統管理中心管理您的應用程式</span><span class="sxs-lookup"><span data-stu-id="666b4-204">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="666b4-205">在 Teams 中管理自訂應用程式原則和設定</span><span class="sxs-lookup"><span data-stu-id="666b4-205">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
- [<span data-ttu-id="666b4-206">在 Teams 中管理應用程式權限原則</span><span class="sxs-lookup"><span data-stu-id="666b4-206">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
- [<span data-ttu-id="666b4-207">在 Teams 中管理應用程式設定原則</span><span class="sxs-lookup"><span data-stu-id="666b4-207">Manage app setup policies in Teams</span></span>](teams-app-setup-policies.md)
- <span data-ttu-id="666b4-208"><a href="/graph/api/resources/teamsapp?view=graph-rest-beta" target="_blank">Teams 應用程式的 Microsoft Graph API</a></span><span class="sxs-lookup"><span data-stu-id="666b4-208"><a href="/graph/api/resources/teamsapp?view=graph-rest-beta" target="_blank">Microsoft Graph API for Teams apps</a></span></span>