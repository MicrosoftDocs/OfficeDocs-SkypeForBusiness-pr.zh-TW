---
title: 使用小組 App 提交 API 來提交及核准您的自訂應用程式
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
description: 瞭解如何使用 Microsoft 團隊中的小組 App 提交 API 來核准已提交的自訂應用程式。
ms.openlocfilehash: 5b6c8512943527a82b3477579e535bcc151331c0
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731091"
---
# <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a><span data-ttu-id="f7d87-103">發佈透過團隊 App 提交 API 提交的自訂應用程式</span><span class="sxs-lookup"><span data-stu-id="f7d87-103">Publish a custom app submitted through the Teams App Submission API</span></span>

## <a name="overview"></a><span data-ttu-id="f7d87-104">概觀</span><span class="sxs-lookup"><span data-stu-id="f7d87-104">Overview</span></span>

> [!NOTE]
> <span data-ttu-id="f7d87-105">當您發佈自訂團隊 app 時，您組織的 app store 中的使用者就能使用該應用程式。</span><span class="sxs-lookup"><span data-stu-id="f7d87-105">When you publish a custom Teams app, it's available to users in your organization's app store.</span></span> <span data-ttu-id="f7d87-106">發佈自訂應用程式的方式有兩種，您使用的方式取決於您取得 app 的方式。</span><span class="sxs-lookup"><span data-stu-id="f7d87-106">There are two ways to publish a custom app and the way that you use depends on how you get the app.</span></span> <span data-ttu-id="f7d87-107">**本文重點說明如何核准併發布開發人員透過團隊 App 提交 API 提交的自訂應用程式**。</span><span class="sxs-lookup"><span data-stu-id="f7d87-107">**This article focuses on how to approve and publish a custom app that a developer submits through the Teams App Submission API**.</span></span> <span data-ttu-id="f7d87-108">當開發人員以 .zip 格式傳送您的應用程式套件時，會使用另一個方法（上傳自訂的應用程式）。</span><span class="sxs-lookup"><span data-stu-id="f7d87-108">The other method, uploading a custom app, is used when a developer sends you an app package in .zip format.</span></span> <span data-ttu-id="f7d87-109">若要深入瞭解該方法，請參閱 <a href="https://docs.microsoft.com/microsoftteams/upload-custom-apps" target="_blank">上傳應用程式套件以發佈自訂應用程式</a>。</span><span class="sxs-lookup"><span data-stu-id="f7d87-109">To learn more about that method, see <a href="https://docs.microsoft.com/microsoftteams/upload-custom-apps" target="_blank">Publish a custom app by uploading an app package</a>.</span></span>

<span data-ttu-id="f7d87-110">本文提供如何將您的小組 app 從開發移至部署到探索的端對端指導方針。</span><span class="sxs-lookup"><span data-stu-id="f7d87-110">This article provides end-to-end guidance for how to take your Teams app from development to deployment to discovery.</span></span> <span data-ttu-id="f7d87-111">您將掌握團隊在 app 週期中提供的連線體驗的概覽，以簡化在組織的 app store 中開發、部署及管理自訂應用程式的方式。</span><span class="sxs-lookup"><span data-stu-id="f7d87-111">You'll get an overview of the connected experiences that Teams provides across the app lifecycle to streamline how to develop, deploy, and manage custom apps in your organization's app store.</span></span>

<span data-ttu-id="f7d87-112">我們將涵蓋生命週期的每個步驟，包括開發人員如何使用團隊 App 提交 API 直接將自訂應用程式提交至 Microsoft 團隊系統管理中心，以供您查看及核准，以及如何設定策略來管理組織中的使用者應用程式，以及使用者如何在團隊中找到他們。</span><span class="sxs-lookup"><span data-stu-id="f7d87-112">We'll cover each step of the lifecycle, including how developers can use the Teams App Submission API to submit custom apps directly to the Microsoft Teams admin center for you to review and approve, how to set policies to manage apps for users in your organization, and how your users discover them in Teams.</span></span>

![從開發到部署的應用程式概覽](media/custom-app-lifecycle.png)

<span data-ttu-id="f7d87-114">本指南主要說明 app 的小組各部分，且適用于系統管理員和 IT 專業人員。</span><span class="sxs-lookup"><span data-stu-id="f7d87-114">This guidance focuses on the Teams aspects of the app and is intended for admins and IT pros.</span></span> <span data-ttu-id="f7d87-115">如需開發小組 app 的詳細資訊，請參閱 <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">團隊開發人員檔</a>。</span><span class="sxs-lookup"><span data-stu-id="f7d87-115">For information about developing Teams apps, see the <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

## <a name="develop"></a><span data-ttu-id="f7d87-116">開發</span><span class="sxs-lookup"><span data-stu-id="f7d87-116">Develop</span></span>

### <a name="create-the-app"></a><span data-ttu-id="f7d87-117">建立應用程式</span><span class="sxs-lookup"><span data-stu-id="f7d87-117">Create the app</span></span>

<span data-ttu-id="f7d87-118">Microsoft 團隊開發人員平臺可讓開發人員輕鬆地整合您自己的 app 與服務，以提高生產力、更快速地作出決策，以及在現有的內容和工作流程中建立共同作業。</span><span class="sxs-lookup"><span data-stu-id="f7d87-118">The Microsoft Teams developer platform makes it easy for developers to integrate your own apps and services to improve productivity, make decisions faster, and create collaboration around existing content and workflows.</span></span> <span data-ttu-id="f7d87-119">在團隊平臺上建立的應用程式是團隊用戶端與您的服務與工作流程之間的橋樑，可直接將它們納入共同作業平臺的內容。</span><span class="sxs-lookup"><span data-stu-id="f7d87-119">Apps built on the Teams platform are bridges between the Teams client and your services and workflows, bringing them directly into the context of your collaboration platform.</span></span> <span data-ttu-id="f7d87-120">如需詳細資訊，請移至 <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">團隊開發人員檔</a>。</span><span class="sxs-lookup"><span data-stu-id="f7d87-120">For more information, go to the <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

### <a name="submit-the-app"></a><span data-ttu-id="f7d87-121">提交應用程式</span><span class="sxs-lookup"><span data-stu-id="f7d87-121">Submit the app</span></span>

<span data-ttu-id="f7d87-122">當應用程式準備好在生產中使用時，開發人員可以使用小組 App 提交 API 來提交應用程式，這可以從 <a href="https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd" target="_blank">圖表 API</a>、整合開發環境 (IDE) （例如 Visual Studio 程式碼），或諸如電源 App 與 Power Virtual agent 之類的平臺。</span><span class="sxs-lookup"><span data-stu-id="f7d87-122">When the app is ready for use in production, the developer can submit the app using the Teams App Submission API, which can be called from <a href="https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd" target="_blank">Graph API</a>, an integrated development environment (IDE) such as Visual Studio Code, or a platform such as Power Apps and Power Virtual Agents.</span></span> <span data-ttu-id="f7d87-123">如此一來，Microsoft 團隊系統管理中心的 [ <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">管理</a> app] 頁面上的應用程式可供使用，您可以在此查看及核准。</span><span class="sxs-lookup"><span data-stu-id="f7d87-123">Doing this makes the app available on the <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page of the Microsoft Teams admin center, where you, the admin, can review and approve it.this</span></span>

<span data-ttu-id="f7d87-124"><a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">建立于 Microsoft Graph</a>的小組 APP 提交 API 可讓您的組織在您選擇的平臺上進行開發，並自動針對團隊中的自訂應用程式提供核准式提交程式。</span><span class="sxs-lookup"><span data-stu-id="f7d87-124">The Teams App Submission API, <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">built on Microsoft Graph</a>, allows your organization to develop on the platform of your choice and automates the submission-to-approval process for custom apps on Teams.</span></span>

<span data-ttu-id="f7d87-125">以下是這個 app 提交步驟在 Visual Studio 程式碼中的外觀範例：</span><span class="sxs-lookup"><span data-stu-id="f7d87-125">Here's an example of what this app submission step looks like in Visual Studio Code:</span></span>

![在 Visual Studio 程式碼中提交應用程式](media/custom-app-lifecycle-submit-app.png)

<span data-ttu-id="f7d87-127">請記住，這並不會將 app 發佈到貴組織的 app store。</span><span class="sxs-lookup"><span data-stu-id="f7d87-127">Keep in mind that this doesn't publish the app to your organization's app store yet.</span></span> <span data-ttu-id="f7d87-128">此步驟會將 app 提交至 Microsoft 團隊系統管理中心，您可以在其中核准發佈至組織的 app store。</span><span class="sxs-lookup"><span data-stu-id="f7d87-128">This step submits the app to the Microsoft Teams admin center where you can approve it for publishing to your organization's app store.</span></span>

<span data-ttu-id="f7d87-129">如需使用圖形 API 來提交應用程式的詳細資訊，請參閱 <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">這裡</a>。</span><span class="sxs-lookup"><span data-stu-id="f7d87-129">For more information about using the Graph API to submit apps, see <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">here</a>.</span></span>

## <a name="validate"></a><span data-ttu-id="f7d87-130">核實</span><span class="sxs-lookup"><span data-stu-id="f7d87-130">Validate</span></span>

<span data-ttu-id="f7d87-131">[Microsoft 團隊系統管理中心] 中的 [<a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">管理應用程式</a>] 頁面 (左側導覽中，移至 [**團隊 app**  >  **管理 app** ]) ，為您的組織提供所有團隊 app 的視圖。</span><span class="sxs-lookup"><span data-stu-id="f7d87-131">The <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page in the Microsoft Teams admin center (in the left navigation, go to **Teams apps** > **Manage apps**), gives you a view into all Teams apps for your organization.</span></span> <span data-ttu-id="f7d87-132">頁面頂端的 **待定核准** 小工具可讓您知道何時提交自訂 app 以供核准。</span><span class="sxs-lookup"><span data-stu-id="f7d87-132">The **Pending approval** widget at the top of the page lets you know when a custom app is submitted for approval.</span></span>

<span data-ttu-id="f7d87-133">在表格中，新提交的 app 會自動顯示已 **提交** 且已封鎖 **狀態** 的 **發佈狀態**。</span><span class="sxs-lookup"><span data-stu-id="f7d87-133">In the table, a newly submitted app automatically shows a **Publishing status** of **Submitted** and **Status** of **Blocked**.</span></span> <span data-ttu-id="f7d87-134">您可以依遞減順序排序 [ **發佈狀態** ] 欄，以快速找到該應用程式。</span><span class="sxs-lookup"><span data-stu-id="f7d87-134">You can sort the **Publishing status** column in descending order to quickly find the app.</span></span>

![<span data-ttu-id="f7d87-135">發佈狀態</span><span class="sxs-lookup"><span data-stu-id="f7d87-135">publishing status</span></span> ](media/custom-app-lifecycle-validate-app.png)

<span data-ttu-id="f7d87-136">按一下應用程式名稱，移至 [應用程式詳細資料] 頁面。</span><span class="sxs-lookup"><span data-stu-id="f7d87-136">Click the app name to go to the app details page.</span></span> <span data-ttu-id="f7d87-137">在 [ **關於** ] 索引標籤上，您可以查看應用程式的詳細資料，包括描述、狀態、提交者和應用程式識別碼。</span><span class="sxs-lookup"><span data-stu-id="f7d87-137">On the **About** tab, you can view details about the app, including description, status, submitter, and app ID.</span></span>

<span data-ttu-id="f7d87-138">！已提交 app 的 app 詳細資料頁面 (媒體/custom-app-lifecycle-app-details.png) </span><span class="sxs-lookup"><span data-stu-id="f7d87-138">!app details page for a submitted app](media/custom-app-lifecycle-app-details.png)</span></span>

<span data-ttu-id="f7d87-139">如需使用圖形 API 檢查 **發佈狀態** 的詳細資訊，請參閱 <a href="https://docs.microsoft.com/graph/api/teamsapp-list?view=graph-rest-1.0&tabs=http#example-3-list-applications-with-a-given-id-and-return-the-submission-review-state" target="_blank">這裡</a>。</span><span class="sxs-lookup"><span data-stu-id="f7d87-139">For more information about using the Graph API to check the **Publishing status**, see <a href="https://docs.microsoft.com/graph/api/teamsapp-list?view=graph-rest-1.0&tabs=http#example-3-list-applications-with-a-given-id-and-return-the-submission-review-state" target="_blank">here</a>.</span></span>

## <a name="publish"></a><span data-ttu-id="f7d87-140">出版</span><span class="sxs-lookup"><span data-stu-id="f7d87-140">Publish</span></span>

<span data-ttu-id="f7d87-141">當您準備好讓使用者使用 app 時，請發佈 app。</span><span class="sxs-lookup"><span data-stu-id="f7d87-141">When you're ready to make the app available to users, publish the app.</span></span>

1. <span data-ttu-id="f7d87-142">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**  >  **管理應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="f7d87-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="f7d87-143">按一下應用程式名稱，移至 [應用程式詳細資料] 頁面，然後在 [ **發佈狀態** ] 方塊中，選取 [ **發佈**]。</span><span class="sxs-lookup"><span data-stu-id="f7d87-143">Click the app name to go to the app details page, and then in the **Publishing status** box, select **Publish**.</span></span>

    <span data-ttu-id="f7d87-144">發佈應用程式後， **發佈狀態** 會變更為 [ **已發佈** ]，而且 **狀態** 會自動變更為 [ **允許**]。</span><span class="sxs-lookup"><span data-stu-id="f7d87-144">After you publish the app, the **Publishing status** changes to **Published** and the **Status** automatically changes to **Allowed**.</span></span>

## <a name="set-up-and-manage"></a><span data-ttu-id="f7d87-145">設定和管理</span><span class="sxs-lookup"><span data-stu-id="f7d87-145">Set up and manage</span></span>

### <a name="control-access-to-the-app"></a><span data-ttu-id="f7d87-146">控制對應用程式的存取權</span><span class="sxs-lookup"><span data-stu-id="f7d87-146">Control access to the app</span></span>

<span data-ttu-id="f7d87-147">根據預設，貴組織中的所有使用者都可以存取貴組織 app store 中的 app。</span><span class="sxs-lookup"><span data-stu-id="f7d87-147">By default, all users in your organization can access the app in your organization's app store.</span></span> <span data-ttu-id="f7d87-148">若要限制及控制誰有權使用該應用程式，您可以建立並指派應用程式許可權原則。</span><span class="sxs-lookup"><span data-stu-id="f7d87-148">To restrict and control who has permission to use the app, you can create and assign an app permission policy.</span></span> <span data-ttu-id="f7d87-149">若要深入瞭解，請參閱 <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">在團隊中管理 app 許可權原則</a>。</span><span class="sxs-lookup"><span data-stu-id="f7d87-149">To learn more, see <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">Manage app permission policies in Teams</a>.</span></span>

### <a name="pin-and-install-the-app-for-users-to-discover"></a><span data-ttu-id="f7d87-150">釘選並安裝應用程式供使用者探索</span><span class="sxs-lookup"><span data-stu-id="f7d87-150">Pin and install the app for users to discover</span></span>

<span data-ttu-id="f7d87-151">根據預設，使用者可以找到您組織的 app 商店所需的 app，然後流覽或搜尋該應用程式。</span><span class="sxs-lookup"><span data-stu-id="f7d87-151">By default, for users to find the app they have to go to your organization's app store and browse or search for it.</span></span> <span data-ttu-id="f7d87-152">若要讓使用者能夠輕鬆存取應用程式，您可以將應用程式釘選到 [團隊] 中的應用程式行。</span><span class="sxs-lookup"><span data-stu-id="f7d87-152">To make it easy for users to get to the app, you can pin the app to the app bar in Teams.</span></span> <span data-ttu-id="f7d87-153">若要這樣做，請建立應用程式設定原則，並將它指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="f7d87-153">To do this, create an app setup policy and assign it to users.</span></span> <span data-ttu-id="f7d87-154">若要深入瞭解，請參閱 <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">管理團隊中的 app 設定原則</a>。</span><span class="sxs-lookup"><span data-stu-id="f7d87-154">To learn more, see <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">Manage app setup policies in Teams</a>.</span></span>

### <a name="search-the-audit-log-for-teams-app-events"></a><span data-ttu-id="f7d87-155">搜尋小組 app 事件的審核記錄</span><span class="sxs-lookup"><span data-stu-id="f7d87-155">Search the audit log for Teams app events</span></span>

<span data-ttu-id="f7d87-156">您可以搜尋 [審核記錄]，以查看貴組織中的 [小組 app] 活動。</span><span class="sxs-lookup"><span data-stu-id="f7d87-156">You can search the audit log to view Teams apps activity in your organization.</span></span> <span data-ttu-id="f7d87-157">若要進一步瞭解如何搜尋審核記錄，以及查看在審核記錄中記錄的小組活動清單，請參閱 <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">在審核記錄中搜尋小組中的事件</a>。</span><span class="sxs-lookup"><span data-stu-id="f7d87-157">To learn more about how to search the audit log and to see a list of Teams activities that are logged in the audit log, see <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">Search the audit log for events in Teams</a>.</span></span>

<span data-ttu-id="f7d87-158">在您可以搜尋審核記錄之前，您必須先在 <a href="https://protection.office.com" target="_blank">安全性 & 合規性中心</a>開啟審核。</span><span class="sxs-lookup"><span data-stu-id="f7d87-158">Before you can search the audit log, you have to first turn on auditing in the <a href="https://protection.office.com" target="_blank">Security & Compliance Center</a>.</span></span> <span data-ttu-id="f7d87-159">若要深入瞭解，請參閱 <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">開啟或關閉審核記錄搜尋</a>。</span><span class="sxs-lookup"><span data-stu-id="f7d87-159">To learn more, see <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">Turn audit log search on or off</a>.</span></span> <span data-ttu-id="f7d87-160">請記住，審核資料只能從您開啟審核的位置取得。</span><span class="sxs-lookup"><span data-stu-id="f7d87-160">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="discover-and-adopt"></a><span data-ttu-id="f7d87-161">探索與採納</span><span class="sxs-lookup"><span data-stu-id="f7d87-161">Discover and adopt</span></span>

<span data-ttu-id="f7d87-162">擁有 app 許可權的使用者可以在您組織的 app store 中找到該應用程式。</span><span class="sxs-lookup"><span data-stu-id="f7d87-162">Users who have permissions to the app can find it in your organization's app store.</span></span> <span data-ttu-id="f7d87-163">移至 [應用程式] 頁面上的 [**針對 *您的組織名稱* 建立**]，以尋找貴組織的自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="f7d87-163">Go to **Built for *Your Organization Name*** on the Apps page to find your organization's custom apps.</span></span>

![<span data-ttu-id="f7d87-164">顯示已發佈應用程式的 [應用程式] 頁面</span><span class="sxs-lookup"><span data-stu-id="f7d87-164">Apps page showing published app</span></span> ](media/custom-app-lifecycle-discovery.png)

<span data-ttu-id="f7d87-165">如果您已建立並指派應用程式設定原則，應用程式會釘選在團隊中的應用程式行上，輕鬆存取指派了原則的使用者。</span><span class="sxs-lookup"><span data-stu-id="f7d87-165">If you created and assigned an app setup policy, the app is pinned to the app bar in Teams for easy access for those users who were assigned the policy.</span></span>

## <a name="update"></a><span data-ttu-id="f7d87-166">時更新</span><span class="sxs-lookup"><span data-stu-id="f7d87-166">Update</span></span>

<span data-ttu-id="f7d87-167">若要更新應用程式，開發人員應該繼續遵循 [ [開發](#develop) ] 區段中的步驟。</span><span class="sxs-lookup"><span data-stu-id="f7d87-167">To update an app, developers should continue to follow the steps in the [Develop](#develop) section.</span></span>

<span data-ttu-id="f7d87-168">當開發人員提交已發佈的自訂應用程式的更新時，您會在 [<a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">管理應用程式</a>] 頁面上的 [**待定核准**] 小工具中收到通知。</span><span class="sxs-lookup"><span data-stu-id="f7d87-168">When the developer submits an update to a published custom app, you'll get notified in the **Pending approval** widget of the <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page.</span></span> <span data-ttu-id="f7d87-169">在表格中，應用程式的 **發佈狀態** 會設定為 [已 **提交更新**]。</span><span class="sxs-lookup"><span data-stu-id="f7d87-169">In the table, the **Publishing status** of the app will be set to **Update submitted**.</span></span>

![<span data-ttu-id="f7d87-170">[管理應用程式] 頁面，顯示擱置的要求和 app 狀態</span><span class="sxs-lookup"><span data-stu-id="f7d87-170">Manage apps page showing pending requests and app status</span></span> ](media/custom-app-lifecycle-update-submitted.png)

<span data-ttu-id="f7d87-171">若要查看併發布應用程式更新：</span><span class="sxs-lookup"><span data-stu-id="f7d87-171">To review and publish an app update:</span></span>

1. <span data-ttu-id="f7d87-172">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**  >  **管理應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="f7d87-172">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="f7d87-173">按一下應用程式名稱，移至 [應用程式詳細資料] 頁面，然後選取 [ **可用** 以查看更新的詳細資料]。</span><span class="sxs-lookup"><span data-stu-id="f7d87-173">Click the app name to go to the app details page, and then select **Update available** to review details of the update.</span></span>

    ![[應用程式詳細資料] 頁面](media/custom-app-lifecycle-update-app.png)
3. <span data-ttu-id="f7d87-175">當您準備好時，請選取 [ **發佈** ] 以發佈更新。</span><span class="sxs-lookup"><span data-stu-id="f7d87-175">When you're ready, select **Publish** to publish the update.</span></span> <span data-ttu-id="f7d87-176">這麼做會取代現有的 app、更新版本號碼，並將 **發佈狀態** 變更為 [ **已發佈**]。</span><span class="sxs-lookup"><span data-stu-id="f7d87-176">Doing this replaces the existing app, updates the version number, and changes the **Publishing status** to **Published**.</span></span> <span data-ttu-id="f7d87-177">所有 app 許可權原則和 app 設定原則，都會針對更新的 app 保持強制執行。</span><span class="sxs-lookup"><span data-stu-id="f7d87-177">All app permission policies and app setup policies remain enforced for the updated app.</span></span>

    <span data-ttu-id="f7d87-178">如果您拒絕更新，較舊版本的 app 會保持發佈。</span><span class="sxs-lookup"><span data-stu-id="f7d87-178">If you reject the update, the earlier version of the app remains published.</span></span>

<span data-ttu-id="f7d87-179">請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="f7d87-179">Keep in mind the following:</span></span>

- <span data-ttu-id="f7d87-180">當應用程式獲核准時，任何人都可以提交應用程式的更新。</span><span class="sxs-lookup"><span data-stu-id="f7d87-180">When an app is approved, any one can submit an update to the app.</span></span> <span data-ttu-id="f7d87-181">這表示其他開發人員，包括最初提交 app 的開發人員，可以提交應用程式的更新。</span><span class="sxs-lookup"><span data-stu-id="f7d87-181">This means other developers, including the developer who originally submitted the app, can submit an update to the app.</span></span>
- <span data-ttu-id="f7d87-182">當開發人員提交應用程式且要求擱置時，只有同一位開發人員才能提交應用程式的更新。</span><span class="sxs-lookup"><span data-stu-id="f7d87-182">When a developer submits an app and the request is pending, only that same developer can submit an update to the app.</span></span> <span data-ttu-id="f7d87-183">其他開發人員只能在應用程式核准後提交更新。</span><span class="sxs-lookup"><span data-stu-id="f7d87-183">Other developers can submit an update only after the app is approved.</span></span>

<span data-ttu-id="f7d87-184">如需使用圖形 API 來更新應用程式的詳細資訊，請參閱 <a href="https://docs.microsoft.com/graph/api/teamsapp-update?view=graph-rest-1.0#example-2-update-a-previously-reviewed-and-published-application-to-the-teams-app-catalog" target="_blank">這裡</a>。</span><span class="sxs-lookup"><span data-stu-id="f7d87-184">For more information about using the Graph API to update apps, see <a href="https://docs.microsoft.com/graph/api/teamsapp-update?view=graph-rest-1.0#example-2-update-a-previously-reviewed-and-published-application-to-the-teams-app-catalog" target="_blank">here</a>.</span></span>

### <a name="update-experience-for-users"></a><span data-ttu-id="f7d87-185">使用者的更新體驗</span><span class="sxs-lookup"><span data-stu-id="f7d87-185">Update experience for users</span></span>

<span data-ttu-id="f7d87-186">在大多數情況下，發佈應用程式更新之後，系統會自動為使用者顯示新版本。</span><span class="sxs-lookup"><span data-stu-id="f7d87-186">In most cases, after you publish an app update, the new version automatically appears for users.</span></span> <span data-ttu-id="f7d87-187">不過， <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft 團隊資訊清單</a> 有一些更新需要使用者驗收才能完成：</span><span class="sxs-lookup"><span data-stu-id="f7d87-187">However, there are some updates to the <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams manifest</a> that require user acceptance to complete:</span></span>

* <span data-ttu-id="f7d87-188">已新增或移除 bot</span><span class="sxs-lookup"><span data-stu-id="f7d87-188">A bot was added or removed</span></span>
* <span data-ttu-id="f7d87-189">現有 bot 的 "botId" 屬性已變更</span><span class="sxs-lookup"><span data-stu-id="f7d87-189">An existing bot's "botId" property changed</span></span>
* <span data-ttu-id="f7d87-190">現有 bot 的 "isNotificationOnly" 屬性已變更</span><span class="sxs-lookup"><span data-stu-id="f7d87-190">An existing bot's "isNotificationOnly" property changed</span></span>
* <span data-ttu-id="f7d87-191">Bot 的 "supportsFiles" 屬性已變更</span><span class="sxs-lookup"><span data-stu-id="f7d87-191">The bot's "supportsFiles" property changed</span></span>
* <span data-ttu-id="f7d87-192">已新增或移除訊息延伸</span><span class="sxs-lookup"><span data-stu-id="f7d87-192">A messaging extension was added or removed</span></span>
* <span data-ttu-id="f7d87-193">已新增新的連接器</span><span class="sxs-lookup"><span data-stu-id="f7d87-193">A new connector was added</span></span>
* <span data-ttu-id="f7d87-194">新增了 [靜態] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="f7d87-194">A new static tab was added</span></span>
* <span data-ttu-id="f7d87-195">新增 [可設定] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="f7d87-195">A new configurable tab was added</span></span>
* <span data-ttu-id="f7d87-196">"WebApplicationInfo" 中的屬性已變更</span><span class="sxs-lookup"><span data-stu-id="f7d87-196">Properties inside "webApplicationInfo" changed</span></span>

![新版本可供使用](media/manage-your-custom-apps-update1.png)

![app 的升級選項](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a><span data-ttu-id="f7d87-199">相關主題</span><span class="sxs-lookup"><span data-stu-id="f7d87-199">Related topics</span></span>

- [<span data-ttu-id="f7d87-200">透過上傳應用程式套件發佈自訂應用程式</span><span class="sxs-lookup"><span data-stu-id="f7d87-200">Publish a custom app by uploading an app package</span></span>](upload-custom-apps.md)
- [<span data-ttu-id="f7d87-201">在 Microsoft 團隊系統管理中心管理您的應用程式</span><span class="sxs-lookup"><span data-stu-id="f7d87-201">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="f7d87-202">在 Teams 中管理自訂應用程式原則和設定</span><span class="sxs-lookup"><span data-stu-id="f7d87-202">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
- [<span data-ttu-id="f7d87-203">在 Teams 中管理應用程式權限原則</span><span class="sxs-lookup"><span data-stu-id="f7d87-203">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
- [<span data-ttu-id="f7d87-204">在 Teams 中管理應用程式設定原則</span><span class="sxs-lookup"><span data-stu-id="f7d87-204">Manage app setup policies in Teams</span></span>](teams-app-setup-policies.md)
- <span data-ttu-id="f7d87-205"><a href="https://docs.microsoft.com/graph/api/resources/teamsapp?view=graph-rest-1.0" target="_blank">適用于團隊 app 的 Microsoft Graph API</a></span><span class="sxs-lookup"><span data-stu-id="f7d87-205"><a href="https://docs.microsoft.com/graph/api/resources/teamsapp?view=graph-rest-1.0" target="_blank">Microsoft Graph API for Teams apps</a></span></span>
