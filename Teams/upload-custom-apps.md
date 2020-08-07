---
title: 在 Microsoft 團隊系統管理中心上傳您的自訂應用程式
author: lanachin
ms.author: v-lanac
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
description: 瞭解如何將自訂應用程式上傳到 Microsoft 團隊系統管理中心的組織 app 存放區。
ms.openlocfilehash: d43b19f4ada3ce6f0424a324cdea6f194575325b
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583642"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a><span data-ttu-id="c03fc-103">透過上傳應用程式套件發佈自訂應用程式</span><span class="sxs-lookup"><span data-stu-id="c03fc-103">Publish a custom app by uploading an app package</span></span>

> [!NOTE]
> <span data-ttu-id="c03fc-104">當您發佈自訂團隊 app 時，您組織的 app store 中的使用者就能使用該應用程式。</span><span class="sxs-lookup"><span data-stu-id="c03fc-104">When you publish a custom Teams app, it's available to users in your organization's app store.</span></span> <span data-ttu-id="c03fc-105">發佈自訂應用程式的方式有兩種，您使用的方式取決於您取得 app 的方式。</span><span class="sxs-lookup"><span data-stu-id="c03fc-105">There are two ways to publish a custom app and the way that you use depends on how you get the app.</span></span> <span data-ttu-id="c03fc-106">**本文將重點說明如何發佈自訂應用程式，方法是使用開發人員傳送給您的 .zip 格式) 來上傳應用程式套件 (。**</span><span class="sxs-lookup"><span data-stu-id="c03fc-106">**This article focuses on how to publish a custom app by uploading an app package (in .zip format) that a developer sends you**.</span></span> <span data-ttu-id="c03fc-107">當開發人員透過團隊 App 提交 API 直接向 [<a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">管理應用</a>程式] 頁面提交應用程式時，就會使用另一個方法（核准自訂的應用程式）。</span><span class="sxs-lookup"><span data-stu-id="c03fc-107">The other method, approving a custom app, is used when a developer submits an app directly to the <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page through the Teams App Submission API.</span></span> <span data-ttu-id="c03fc-108">若要深入瞭解該方法，請參閱<a href="https://docs.microsoft.com/microsoftteams/submit-approve-custom-apps" target="_blank">發佈透過團隊 App 提交 API 提交的自訂應用程式</a>。</span><span class="sxs-lookup"><span data-stu-id="c03fc-108">To learn more about that method, see <a href="https://docs.microsoft.com/microsoftteams/submit-approve-custom-apps" target="_blank">Publish a custom app submitted through the Teams App Submission API</a>.</span></span>

<span data-ttu-id="c03fc-109">本文提供如何將您的小組 app 從開發移至部署到探索的端對端指導方針。</span><span class="sxs-lookup"><span data-stu-id="c03fc-109">This article provides end-to-end guidance for how to take your Teams app from development to deployment to discovery.</span></span> <span data-ttu-id="c03fc-110">本指南主要說明 app 的小組各部分，且適用于系統管理員和 IT 專業人員。</span><span class="sxs-lookup"><span data-stu-id="c03fc-110">This guidance focuses on the Teams aspects of the app and is intended for admins and IT pros.</span></span> <span data-ttu-id="c03fc-111">如需開發小組 app 的詳細資訊，請參閱<a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">團隊開發人員檔</a>。</span><span class="sxs-lookup"><span data-stu-id="c03fc-111">For more information about developing Teams apps, see the <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

![從開發到部署的應用程式概覽](media/upload-custom-apps.png)

## <a name="develop"></a><span data-ttu-id="c03fc-113">開發</span><span class="sxs-lookup"><span data-stu-id="c03fc-113">Develop</span></span>

### <a name="create-your-app"></a><span data-ttu-id="c03fc-114">建立您的應用程式</span><span class="sxs-lookup"><span data-stu-id="c03fc-114">Create your app</span></span>

<span data-ttu-id="c03fc-115">Microsoft 團隊開發人員平臺可讓開發人員輕鬆地整合您自己的 app 與服務，以提高生產力、更快速地作出決策，以及在現有的內容和工作流程中建立共同作業。</span><span class="sxs-lookup"><span data-stu-id="c03fc-115">The Microsoft Teams developer platform makes it easy for developers to integrate your own apps and services to improve productivity, make decisions faster, and create collaboration around existing content and workflows.</span></span> <span data-ttu-id="c03fc-116">在團隊平臺上建立的應用程式是團隊用戶端與您的服務與工作流程之間的橋樑，可直接將它們納入共同作業平臺的內容。</span><span class="sxs-lookup"><span data-stu-id="c03fc-116">Apps built on the Teams platform are bridges between the Teams client and your services and workflows, bringing them directly into the context of your collaboration platform.</span></span> <span data-ttu-id="c03fc-117">如需詳細資訊，請移至<a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">團隊開發人員檔</a>。</span><span class="sxs-lookup"><span data-stu-id="c03fc-117">For more information, go to the <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

## <a name="validate"></a><span data-ttu-id="c03fc-118">核實</span><span class="sxs-lookup"><span data-stu-id="c03fc-118">Validate</span></span>

### <a name="get-the-app-package"></a><span data-ttu-id="c03fc-119">取得應用程式套件</span><span class="sxs-lookup"><span data-stu-id="c03fc-119">Get the app package</span></span>

<span data-ttu-id="c03fc-120">當應用程式準備好在生產中使用時，開發人員應該會產生應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="c03fc-120">When the app is ready for use in production, the developer should produce an app package.</span></span> <span data-ttu-id="c03fc-121">他們可以使用<a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">應用程式 Studio</a>來執行此程式。</span><span class="sxs-lookup"><span data-stu-id="c03fc-121">They can use <a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">App Studio</a> for that.</span></span> <span data-ttu-id="c03fc-122">他們會以 .zip 格式傳送檔案。</span><span class="sxs-lookup"><span data-stu-id="c03fc-122">They'll send you the file in .zip format.</span></span>

<span data-ttu-id="c03fc-123">Microsoft 使用<a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">這些指導方針</a>，以確保 app 符合全域團隊 app store 的品質與安全性標準。</span><span class="sxs-lookup"><span data-stu-id="c03fc-123">Microsoft uses <a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">these guidelines</a> to ensure apps comply with the quality and security standards of the global Teams apps store.</span></span>

### <a name="allow-trusted-users-to-upload-custom-apps"></a><span data-ttu-id="c03fc-124">允許信任的使用者上傳自訂應用程式</span><span class="sxs-lookup"><span data-stu-id="c03fc-124">Allow trusted users to upload custom apps</span></span>

<span data-ttu-id="c03fc-125">若要驗證 app 在您的生產租使用者中是否正常運作，您必須允許自己和/或受信任的使用者上傳生產租使用者中的自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="c03fc-125">To validate that the app is working correctly in your production tenant, you need to allow yourself and/or trusted users to upload custom apps in the production tenant.</span></span> <span data-ttu-id="c03fc-126">您可以使用<a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">應用程式設定原則</a>來執行這項作業。</span><span class="sxs-lookup"><span data-stu-id="c03fc-126">You use <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">app setup policies</a> to do this.</span></span>

> [!NOTE]
> <span data-ttu-id="c03fc-127">如果您不滿意將 app 上傳到您的生產租使用者進行驗證，即使您是自己或信任的使用者，您也可以略過此步驟，並遵循[上傳](#upload)和[設定及管理](#set-up-and-manage)區段中的步驟，將 unvalidated 應用程式發佈到貴組織的 app store。</span><span class="sxs-lookup"><span data-stu-id="c03fc-127">If you're uncomfortable with uploading the app to your production tenant for validation, even for yourself or trusted users, you can skip this step and follow the steps in the [Upload](#upload) and [Set up and manage](#set-up-and-manage) sections to publish the unvalidated app to your organization's app store.</span></span> <span data-ttu-id="c03fc-128">然後，將該 app 的存取許可權制為只有您自己和您信任的使用者。</span><span class="sxs-lookup"><span data-stu-id="c03fc-128">Then, restrict access to that app to only yourself and users you trust.</span></span> <span data-ttu-id="c03fc-129">然後，這些使用者就可以從貴組織的 app store 取得 app 來執行驗證。</span><span class="sxs-lookup"><span data-stu-id="c03fc-129">These users can then get the app from your organization's app store to perform validation.</span></span> <span data-ttu-id="c03fc-130">驗證應用程式後，請使用相同的許可權原則來開啟 access，並將 app 滾出以供生產使用。</span><span class="sxs-lookup"><span data-stu-id="c03fc-130">After the app is validated, use the same permission policies to open access and roll the app out for production use.</span></span>

<span data-ttu-id="c03fc-131">若要允許信任的使用者上傳自訂應用程式，請依照下列步驟執行：</span><span class="sxs-lookup"><span data-stu-id="c03fc-131">To allow trusted users to upload custom apps, follow these steps:</span></span>

1. <span data-ttu-id="c03fc-132">開啟 [**允許與自訂應用程式互動**] 全組織性應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="c03fc-132">Turn on the **Allow interaction with custom apps** org-wide app setting.</span></span> <span data-ttu-id="c03fc-133">若要執行此動作：</span><span class="sxs-lookup"><span data-stu-id="c03fc-133">To do this:</span></span>
    1. <span data-ttu-id="c03fc-134">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**  >  **管理 app**]，然後按一下 [**全組織式應用程式設定**]。</span><span class="sxs-lookup"><span data-stu-id="c03fc-134">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**, and then click **Org-wide app settings**.</span></span>
    2. <span data-ttu-id="c03fc-135">開啟 [**自訂應用程式**] 底下的 [**允許與自訂應用程式互動**]，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="c03fc-135">Under **Custom apps**, turn on **Allow interaction with custom apps**, and then click **Save**.</span></span>
2. <span data-ttu-id="c03fc-136">關閉全域 app 設定原則中的 [**上傳自訂應用程式**] 設定。</span><span class="sxs-lookup"><span data-stu-id="c03fc-136">Turn off the **Upload custom apps** setting in the global app setup policy.</span></span> <span data-ttu-id="c03fc-137">若要執行此動作：</span><span class="sxs-lookup"><span data-stu-id="c03fc-137">To do this:</span></span>
    1. <span data-ttu-id="c03fc-138">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**  >  **設定原則**]，然後按一下 [\*\*全域 (組織範圍的預設) \*\*原則。</span><span class="sxs-lookup"><span data-stu-id="c03fc-138">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**, and then click the **Global (Org-wide default)** policy.</span></span>
    2. <span data-ttu-id="c03fc-139">關閉 **[上傳自訂應用程式**]，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="c03fc-139">Turn off **Upload custom apps**, and then click **Save**.</span></span>
3. <span data-ttu-id="c03fc-140">建立新的應用程式設定原則，以允許上傳自訂應用程式，並將它指派給您的一組受信任的使用者。</span><span class="sxs-lookup"><span data-stu-id="c03fc-140">Create a new app setup policy that allows uploading custom apps and assign it to your set of trusted users.</span></span> <span data-ttu-id="c03fc-141">若要執行此動作：</span><span class="sxs-lookup"><span data-stu-id="c03fc-141">To do this:</span></span>
    1. <span data-ttu-id="c03fc-142">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**  >  **設定原則**]，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="c03fc-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**, and then click the **Add**.</span></span> <span data-ttu-id="c03fc-143">提供新原則的名稱和描述、開啟 **[上傳自訂應用程式**]，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="c03fc-143">Give the new policy a name and description, turn on **Upload custom apps**, and then click **Save**.</span></span>
    2. <span data-ttu-id="c03fc-144">選取您建立的新原則，然後按一下 [**管理使用者**]。</span><span class="sxs-lookup"><span data-stu-id="c03fc-144">Select the new policy you created, and then click **Manage users**.</span></span> <span data-ttu-id="c03fc-145">搜尋使用者 **，按一下 [\*\*\*\*新增**]，然後按一下 [套用]。</span><span class="sxs-lookup"><span data-stu-id="c03fc-145">Search for a user, click **Add**, and then click **Apply**.</span></span> <span data-ttu-id="c03fc-146">重複此步驟，將原則指派給所有信任的使用者。</span><span class="sxs-lookup"><span data-stu-id="c03fc-146">Repeat this step to assign the policy to all your trusted users.</span></span>

        ![[新增應用程式設定原則] 頁面的螢幕擷取畫面](media/manage-your-lob-apps-new-app-setup-policy.png)

    <span data-ttu-id="c03fc-148">這些使用者現在可以上傳應用程式資訊清單，以驗證 app 在生產租使用者中是否正常運作。</span><span class="sxs-lookup"><span data-stu-id="c03fc-148">These users can now upload the app manifest to validate that the app is working correctly in the production tenant.</span></span>

## <a name="upload"></a><span data-ttu-id="c03fc-149">將</span><span class="sxs-lookup"><span data-stu-id="c03fc-149">Upload</span></span>

<span data-ttu-id="c03fc-150">若要讓貴組織 app store 中的使用者使用該應用程式，請上傳 app。</span><span class="sxs-lookup"><span data-stu-id="c03fc-150">To make the app available to users in your organization's app store, upload the app.</span></span> <span data-ttu-id="c03fc-151">您可以在 Microsoft 團隊系統管理中心的 [<a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">管理應用程式</a>] 頁面上執行此動作。</span><span class="sxs-lookup"><span data-stu-id="c03fc-151">You can do this on the <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page of the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="c03fc-152">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**  >  **管理應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="c03fc-152">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="c03fc-153">按一下 **[上傳**]，按一下 [**選取**檔案]，然後選取您從開發人員收到的應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="c03fc-153">Click **Upload**, click **Select a file**, and then select the app package that you received from the developer.</span></span>

   ![在系統管理中心上傳應用程式的螢幕擷取畫面](media/manage-your-lob-apps-upload-new-app.png) 

## <a name="set-up-and-manage"></a><span data-ttu-id="c03fc-155">設定和管理</span><span class="sxs-lookup"><span data-stu-id="c03fc-155">Set up and manage</span></span>

### <a name="control-access-to-the-app"></a><span data-ttu-id="c03fc-156">控制對應用程式的存取權</span><span class="sxs-lookup"><span data-stu-id="c03fc-156">Control access to the app</span></span>

<span data-ttu-id="c03fc-157">根據預設，貴組織中的所有使用者都可以存取貴組織 app store 中的 app。</span><span class="sxs-lookup"><span data-stu-id="c03fc-157">By default, all users in your organization can access the app in your organization's app store.</span></span> <span data-ttu-id="c03fc-158">若要限制及控制誰有權使用該應用程式，您可以建立並指派應用程式許可權原則。</span><span class="sxs-lookup"><span data-stu-id="c03fc-158">To restrict and control who has permission to use the app, you can create and assign an app permission policy.</span></span> <span data-ttu-id="c03fc-159">若要深入瞭解，請參閱<a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">在團隊中管理 app 許可權原則</a>。</span><span class="sxs-lookup"><span data-stu-id="c03fc-159">To learn more, see <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">Manage app permission policies in Teams</a>.</span></span>

### <a name="pin-and-install-the-app-for-users-to-discover"></a><span data-ttu-id="c03fc-160">釘選並安裝應用程式供使用者探索</span><span class="sxs-lookup"><span data-stu-id="c03fc-160">Pin and install the app for users to discover</span></span>

<span data-ttu-id="c03fc-161">根據預設，使用者可以找到您組織的 app 商店所需的 app，然後流覽或搜尋該應用程式。</span><span class="sxs-lookup"><span data-stu-id="c03fc-161">By default, for users to find the app they have to go to your organization's app store and browse or search for it.</span></span> <span data-ttu-id="c03fc-162">若要讓使用者能夠輕鬆存取應用程式，您可以將應用程式釘選到 [團隊] 中的應用程式行。</span><span class="sxs-lookup"><span data-stu-id="c03fc-162">To make it easy for users to get to the app, you can pin the app to the app bar in Teams.</span></span> <span data-ttu-id="c03fc-163">若要這樣做，請建立應用程式設定原則，並將它指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="c03fc-163">To do this, create an app setup policy and assign it to users.</span></span> <span data-ttu-id="c03fc-164">若要深入瞭解，請參閱<a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">管理團隊中的 app 設定原則</a>。</span><span class="sxs-lookup"><span data-stu-id="c03fc-164">To learn more, see <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">Manage app setup policies in Teams</a>.</span></span>

### <a name="search-the-audit-log-for-teams-app-events"></a><span data-ttu-id="c03fc-165">搜尋小組 app 事件的審核記錄</span><span class="sxs-lookup"><span data-stu-id="c03fc-165">Search the audit log for Teams app events</span></span>

<span data-ttu-id="c03fc-166">您可以搜尋 [審核記錄]，以查看貴組織中的 [小組 app] 活動。</span><span class="sxs-lookup"><span data-stu-id="c03fc-166">You can search the audit log to view Teams apps activity in your organization.</span></span> <span data-ttu-id="c03fc-167">若要進一步瞭解如何搜尋審核記錄，以及查看在審核記錄中記錄的小組活動清單，請參閱<a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">在審核記錄中搜尋小組中的事件</a>。</span><span class="sxs-lookup"><span data-stu-id="c03fc-167">To learn more about how to search the audit log and to see a list of Teams activities that are logged in the audit log, see <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">Search the audit log for events in Teams</a>.</span></span>

<span data-ttu-id="c03fc-168">在您可以搜尋審核記錄之前，您必須先在<a href="https://protection.office.com" target="_blank">安全性 & 合規性中心</a>開啟審核。</span><span class="sxs-lookup"><span data-stu-id="c03fc-168">Before you can search the audit log, you have to first turn on auditing in the <a href="https://protection.office.com" target="_blank">Security & Compliance Center</a>.</span></span> <span data-ttu-id="c03fc-169">若要深入瞭解，請參閱<a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">開啟或關閉審核記錄搜尋</a>。</span><span class="sxs-lookup"><span data-stu-id="c03fc-169">To learn more, see <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">Turn audit log search on or off</a>.</span></span> <span data-ttu-id="c03fc-170">請記住，審核資料只能從您開啟審核的位置取得。</span><span class="sxs-lookup"><span data-stu-id="c03fc-170">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="discover-and-adopt"></a><span data-ttu-id="c03fc-171">探索與採納</span><span class="sxs-lookup"><span data-stu-id="c03fc-171">Discover and adopt</span></span>

<span data-ttu-id="c03fc-172">擁有 app 許可權的使用者可以在您組織的 app store 中找到該應用程式。</span><span class="sxs-lookup"><span data-stu-id="c03fc-172">Users who have permissions to the app can find it in your organization's app store.</span></span> <span data-ttu-id="c03fc-173">移至 [應用程式] 頁面上的 [**針對*您的組織名稱*建立**]，以尋找貴組織的自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="c03fc-173">Go to **Built for *Your Organization Name*** on the Apps page to find your organization's custom apps.</span></span>

![<span data-ttu-id="c03fc-174">顯示已發佈 app 之 [應用程式] 頁面的螢幕擷取畫面</span><span class="sxs-lookup"><span data-stu-id="c03fc-174">Screenshot of Apps page showing published app</span></span> ](media/custom-app-lifecycle-discovery.png)

<span data-ttu-id="c03fc-175">如果您已建立並指派應用程式設定原則，應用程式會釘選在團隊中的應用程式行上，輕鬆存取指派了原則的使用者。</span><span class="sxs-lookup"><span data-stu-id="c03fc-175">If you created and assigned an app setup policy, the app is pinned to the app bar in Teams for easy access for those users who were assigned the policy.</span></span>

## <a name="update"></a><span data-ttu-id="c03fc-176">時更新</span><span class="sxs-lookup"><span data-stu-id="c03fc-176">Update</span></span>

<span data-ttu-id="c03fc-177">若要更新應用程式，開發人員應該繼續遵循[開發](#develop)和[驗證](#validate)區段中的步驟。</span><span class="sxs-lookup"><span data-stu-id="c03fc-177">To update an app, developers should continue to follow the steps in the [Develop](#develop) and [Validate](#validate) sections.</span></span>

<span data-ttu-id="c03fc-178">您可以在 Microsoft 團隊系統管理中心的 [管理應用程式] 頁面上更新應用程式。</span><span class="sxs-lookup"><span data-stu-id="c03fc-178">You can update the app on the Manage apps page in the Microsoft Teams admin center.</span></span> <span data-ttu-id="c03fc-179">若要這樣做，請在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**  >  **管理應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="c03fc-179">To do this, in the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="c03fc-180">按一下應用程式名稱，然後按一下 [**更新**]。</span><span class="sxs-lookup"><span data-stu-id="c03fc-180">Click the app name, and then click **Update**.</span></span> <span data-ttu-id="c03fc-181">這麼做會取代現有的 app，而且所有 app 許可權原則和 app 設定原則都會針對更新的 app 保持強制執行。</span><span class="sxs-lookup"><span data-stu-id="c03fc-181">Doing this replaces the existing app, and all app permission policies and app setup policies remain enforced for the updated app.</span></span>

### <a name="end-user-update-experience"></a><span data-ttu-id="c03fc-182">最終使用者更新體驗</span><span class="sxs-lookup"><span data-stu-id="c03fc-182">End user update experience</span></span>

<span data-ttu-id="c03fc-183">在大多數情況下，當您完成應用程式更新後，系統會自動針對最終使用者顯示新版本。</span><span class="sxs-lookup"><span data-stu-id="c03fc-183">In most cases, after you complete an app update the new version automatically appears for end users.</span></span> <span data-ttu-id="c03fc-184">不過， <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft 團隊資訊清單</a>有一些更新需要使用者驗收才能完成：</span><span class="sxs-lookup"><span data-stu-id="c03fc-184">However, there are some updates to the <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams manifest</a> that require user acceptance to complete:</span></span>

* <span data-ttu-id="c03fc-185">已新增或移除 bot</span><span class="sxs-lookup"><span data-stu-id="c03fc-185">A bot was added or removed</span></span>
* <span data-ttu-id="c03fc-186">現有 bot 的 "botId" 屬性已變更</span><span class="sxs-lookup"><span data-stu-id="c03fc-186">An existing bot's "botId" property changed</span></span>
* <span data-ttu-id="c03fc-187">現有 bot 的 "isNotificationOnly" 屬性已變更</span><span class="sxs-lookup"><span data-stu-id="c03fc-187">An existing bot's "isNotificationOnly" property changed</span></span>
* <span data-ttu-id="c03fc-188">Bot 的 "supportsFiles" 屬性已變更</span><span class="sxs-lookup"><span data-stu-id="c03fc-188">The bot's "supportsFiles" property changed</span></span>
* <span data-ttu-id="c03fc-189">已新增或移除訊息延伸</span><span class="sxs-lookup"><span data-stu-id="c03fc-189">A Messaging extension was added or removed</span></span>
* <span data-ttu-id="c03fc-190">已新增新的連接器</span><span class="sxs-lookup"><span data-stu-id="c03fc-190">A new connector was added</span></span>
* <span data-ttu-id="c03fc-191">新增了 [靜態] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="c03fc-191">A new static tab was added</span></span>
* <span data-ttu-id="c03fc-192">新增 [可設定] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="c03fc-192">A new configurable tab was added</span></span>
* <span data-ttu-id="c03fc-193">"WebApplicationInfo" 中的屬性已變更</span><span class="sxs-lookup"><span data-stu-id="c03fc-193">Properties inside "webApplicationInfo" changed</span></span>

![[應用程式清單] 的螢幕擷取畫面，顯示已推出新版本的 app](media/manage-your-custom-apps-update1.png)

![App 之升級選項的螢幕擷取畫面](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a><span data-ttu-id="c03fc-196">相關主題</span><span class="sxs-lookup"><span data-stu-id="c03fc-196">Related topics</span></span>

- [<span data-ttu-id="c03fc-197">發佈透過團隊 App 提交 API 提交的自訂應用程式</span><span class="sxs-lookup"><span data-stu-id="c03fc-197">Publish a custom app submitted through the Teams App Submission API</span></span>](submit-approve-custom-apps.md)
- [<span data-ttu-id="c03fc-198">在 Microsoft 團隊系統管理中心管理您的應用程式</span><span class="sxs-lookup"><span data-stu-id="c03fc-198">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="c03fc-199">在 Teams 中管理自訂應用程式原則和設定</span><span class="sxs-lookup"><span data-stu-id="c03fc-199">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
- [<span data-ttu-id="c03fc-200">在 Teams 中管理應用程式權限原則</span><span class="sxs-lookup"><span data-stu-id="c03fc-200">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
- [<span data-ttu-id="c03fc-201">在 Teams 中管理應用程式設定原則</span><span class="sxs-lookup"><span data-stu-id="c03fc-201">Manage app setup policies in Teams</span></span>](teams-app-setup-policies.md)
