---
title: 在 Microsoft 團隊中管理您的商務用應用程式
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: joglocke
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
description: 瞭解如何將自訂團隊 app 從開發開發到部署。
ms.openlocfilehash: f8c5a7dcc12bc9b3823285138d15a0ccdf11c52a
ms.sourcegitcommit: 7093388425b34c80e444a50d062290187b80047d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/22/2020
ms.locfileid: "42229933"
---
# <a name="manage-your-line-of-business-apps-in-microsoft-teams"></a><span data-ttu-id="1cbe6-103">在 Microsoft 團隊中管理您的商務用應用程式</span><span class="sxs-lookup"><span data-stu-id="1cbe6-103">Manage your line-of-business apps in Microsoft Teams</span></span>

<span data-ttu-id="1cbe6-104">本文提供如何將您的小組 app 從開發開發到部署的端對端指導方針。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-104">This article provides end-to-end guidance for how to take your Teams app from development to deployment.</span></span> <span data-ttu-id="1cbe6-105">本指南主要說明 app 的小組各部分，且適用于 IT 專業人員。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-105">This guidance focuses on the Teams aspects of the app and is intended for IT pros.</span></span> <span data-ttu-id="1cbe6-106">如需開發小組 app 的詳細資訊，請參閱<a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">這裡</a>。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-106">For more information on developing Teams apps, see <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">here</a>.</span></span>

![從開發到部署的應用程式概覽](media/manage-your-lob-apps.png)

## <a name="getting-started"></a><span data-ttu-id="1cbe6-108">快速入門</span><span class="sxs-lookup"><span data-stu-id="1cbe6-108">Getting started</span></span>

<span data-ttu-id="1cbe6-109">若要在小組中建立及管理企業往來（LOB）應用程式，您需要兩個租使用者：用於開發和生產租使用者的測試租使用者。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-109">To create and manage line-of-business (LOB) apps in Teams, you’ll need two tenants: a test tenant for development and a production tenant.</span></span>

> [!NOTE]
> <span data-ttu-id="1cbe6-110">如果您還沒有測試租使用者，您可以使用 Office 365 開發人員程式，快速建立一個並填入測試資料。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-110">If you don’t already have a test tenant, you can quickly create one and populate it with test data using the Office 365 Developer Program.</span></span> <span data-ttu-id="1cbe6-111"><a href="https://developer.microsoft.com/office/dev-program" target="_blank">深入瞭解</a>。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-111"><a href="https://developer.microsoft.com/office/dev-program" target="_blank">Learn more here</a>.</span></span>

## <a name="step-1-develop-and-test"></a><span data-ttu-id="1cbe6-112">步驟1：開發與測試</span><span class="sxs-lookup"><span data-stu-id="1cbe6-112">Step 1: Develop and test</span></span>

### <a name="create-test-users"></a><span data-ttu-id="1cbe6-113">建立測試使用者</span><span class="sxs-lookup"><span data-stu-id="1cbe6-113">Create test users</span></span>

<span data-ttu-id="1cbe6-114">請確定您的開發人員（無論是內部還是外部）在您的測試租使用者中有帳戶。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-114">Make sure that your developers, whether in-house or external, have accounts in your test tenant.</span></span> <span data-ttu-id="1cbe6-115"><a href="https://docs.microsoft.com/office365/admin/add-users/add-users" target="_blank">深入瞭解如何新增使用者</a>。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-115"><a href="https://docs.microsoft.com/office365/admin/add-users/add-users" target="_blank">Learn more about adding users</a>.</span></span>

### <a name="allow-custom-apps-in-the-test-tenant"></a><span data-ttu-id="1cbe6-116">允許測試租使用者中的自訂應用程式</span><span class="sxs-lookup"><span data-stu-id="1cbe6-116">Allow custom apps in the test tenant</span></span>

<span data-ttu-id="1cbe6-117">若要為開發人員提供測試所需的存取權，請允許測試租使用者中的所有使用者上傳自訂應用程式（也稱為邊載）。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-117">To give developers the access they need for testing, allow all users in the test tenant to upload custom apps (also known as sideloading).</span></span> <span data-ttu-id="1cbe6-118">這可讓開發人員上傳自訂的應用程式，以供個人或跨測試租使用者使用，而不需將 app 提交到 [小組 app] 存放區。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-118">This lets developers upload a custom app to be used personally or across the test tenant without having to submit the app to the Teams apps store.</span></span> <span data-ttu-id="1cbe6-119">上傳自訂的應用程式可讓開發人員在您更廣泛地發佈 app 之前先測試應用程式。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-119">Uploading a custom app lets developers test an app before you distribute it more widely.</span></span>

<span data-ttu-id="1cbe6-120">若要允許使用者上傳自訂應用程式，請依照下列步驟執行：</span><span class="sxs-lookup"><span data-stu-id="1cbe6-120">To allow users to upload custom apps, follow these steps:</span></span>

1. <span data-ttu-id="1cbe6-121">開啟 [**允許與自訂應用程式互動**] 全組織性應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-121">Turn on the **Allow interaction with custom apps** org-wide app setting.</span></span> <span data-ttu-id="1cbe6-122">若要執行此動作：</span><span class="sxs-lookup"><span data-stu-id="1cbe6-122">To do this:</span></span>
    1. <span data-ttu-id="1cbe6-123">在<a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft 團隊系統管理中心</a>的左導覽中，移至 [**團隊 app** > **管理 app**]，然後按一下 [**全組織式應用程式設定**]。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-123">In the left navigation of the <a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft Teams admin center</a>, go to **Teams apps** > **Manage apps**, and then click **Org-wide app settings**.</span></span>
    2. <span data-ttu-id="1cbe6-124">開啟 [**自訂應用程式**] 底下的 [**允許與自訂應用程式互動**]，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-124">Under **Custom apps**, turn on **Allow interaction with custom apps**, and then click **Save**.</span></span>

    ![「允許與自訂 app 互動」的螢幕擷取畫面](media/manage-your-lob-apps-org-wide-custom-apps.png)

2. <span data-ttu-id="1cbe6-126">開啟全域 app 設定原則中的 [上**傳自訂應用程式**] 設定。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-126">Turn on the **Upload custom apps** setting in the global app setup policy.</span></span> <span data-ttu-id="1cbe6-127">若要執行此動作：</span><span class="sxs-lookup"><span data-stu-id="1cbe6-127">To do this:</span></span>
    1. <span data-ttu-id="1cbe6-128">在<a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft 團隊系統管理中心</a>的左導覽中，移至 [**團隊 app** > **設定原則**]，然後按一下 [**全域（組織範圍預設值）** ] 原則。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-128">In the left navigation of the <a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft Teams admin center</a>, go to **Teams apps** > **Setup policies**, and then click the **Global (Org-wide default)** policy.</span></span>
    2. <span data-ttu-id="1cbe6-129">開啟 **[上傳自訂應用程式**]，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-129">Turn on **Upload custom apps**, and then click **Save**.</span></span>

    ![[上傳自訂應用程式] app 設定策略設定的螢幕擷取畫面](media/manage-your-lob-apps-app-setup-custom-apps.png)

> [!NOTE]
> <span data-ttu-id="1cbe6-131">此外，小組層級也會有上傳自訂應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-131">There's also an upload custom app setting at the team level.</span></span> <span data-ttu-id="1cbe6-132">根據預設，此設定為 [開啟]。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-132">By default this setting is on.</span></span> <span data-ttu-id="1cbe6-133">不過，如果開發人員無法將自訂應用程式上傳至團隊，請按照<a href="https://docs.microsoft.com/microsoftteams/teams-custom-app-policies-and-settings#configure-the-team-custom-app-setting" target="_blank">這裡</a>的步驟來檢查該設定。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-133">However, if developers are unable to upload a custom app to a team, check the setting by following the steps <a href="https://docs.microsoft.com/microsoftteams/teams-custom-app-policies-and-settings#configure-the-team-custom-app-setting" target="_blank">here</a>.</span></span>

### <a name="create-your-app"></a><span data-ttu-id="1cbe6-134">建立您的應用程式</span><span class="sxs-lookup"><span data-stu-id="1cbe6-134">Create your app</span></span>

<span data-ttu-id="1cbe6-135">開發人員現在應該擁有建立您 app 所需的專案。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-135">Developers should now have what they need to create your app.</span></span> <span data-ttu-id="1cbe6-136">請參閱<a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">這裡</a>以取得相關指導方針。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-136">See <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">here</a> for guidance on that.</span></span>

## <a name="step-2-validate-in-production"></a><span data-ttu-id="1cbe6-137">步驟2：在生產中驗證</span><span class="sxs-lookup"><span data-stu-id="1cbe6-137">Step 2: Validate in production</span></span>

### <a name="get-the-app-package"></a><span data-ttu-id="1cbe6-138">取得應用程式套件</span><span class="sxs-lookup"><span data-stu-id="1cbe6-138">Get the app package</span></span>

<span data-ttu-id="1cbe6-139">當應用程式準備好在生產中使用時，開發人員應該會產生應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-139">When the app is ready for use in production, the developer should produce an app package.</span></span> <span data-ttu-id="1cbe6-140">他們可以使用<a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">應用程式 Studio</a>來執行此程式。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-140">They can use <a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">App Studio</a> for that.</span></span> <span data-ttu-id="1cbe6-141">他們會以 .zip 格式傳送檔案。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-141">They'll send you the file in .zip format.</span></span>

<span data-ttu-id="1cbe6-142">Microsoft 使用<a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">這些指導方針</a>，以確保 app 符合全域團隊 app store 的品質與安全性標準。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-142">Microsoft uses <a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">these guidelines</a> to ensure apps comply with the quality and security standards of the global Teams apps store.</span></span>

### <a name="allow-trusted-users-to-upload-custom-apps-in-the-production-tenant"></a><span data-ttu-id="1cbe6-143">允許信任的使用者上傳生產租使用者中的自訂應用程式</span><span class="sxs-lookup"><span data-stu-id="1cbe6-143">Allow trusted users to upload custom apps in the production tenant</span></span>

<span data-ttu-id="1cbe6-144">若要驗證 app 在您的生產租使用者中是否正常運作，您必須允許您的組織中的人員和/或受信任的使用者上傳自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-144">To validate that the app is working correctly in your production tenant, you need to allow yourself and/or trusted users in your organization to upload custom apps.</span></span>  <span data-ttu-id="1cbe6-145">就像在前面的<a href="https://docs.microsoft.com/microsoftteams/manage-your-lob-apps#allow-custom-apps-in-the-test-tenant" target="_blank">步驟</a>中，您可以使用應用程式設定原則來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-145">Much like in the earlier <a href="https://docs.microsoft.com/microsoftteams/manage-your-lob-apps#allow-custom-apps-in-the-test-tenant" target="_blank">step</a>, you use app setup policies to do this.</span></span>

> [!NOTE]
> <span data-ttu-id="1cbe6-146">如果您不滿意將 app 上傳到您的生產租使用者進行驗證，即使您是自己或受信任的使用者，您也可以略過此步驟，並遵循步驟3和4，將 unvalidated 應用程式上傳到您的租使用者 app store。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-146">If you’re uncomfortable with uploading the app to your production tenant for validation, even for yourself or trusted users, you can skip this step and follow steps 3 and 4 to upload the unvalidated app to your tenant app store.</span></span> <span data-ttu-id="1cbe6-147">然後，將該 app 的存取許可權制為只有您自己和您信任的使用者。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-147">Then, restrict access to that app to only yourself and users you trust.</span></span> <span data-ttu-id="1cbe6-148">然後，這些使用者就可以從租使用者應用程式商店取得 app 來執行驗證。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-148">These users can then get the app from the tenant app store to perform validation.</span></span> <span data-ttu-id="1cbe6-149">驗證應用程式後，請使用相同的許可權原則來開啟 access，並將 app 滾出以供生產使用。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-149">After the app is validated, use the same permission policies to open access and roll the app out for production use.</span></span>

<span data-ttu-id="1cbe6-150">若要允許信任的使用者上傳自訂應用程式，請依照下列步驟執行：</span><span class="sxs-lookup"><span data-stu-id="1cbe6-150">To allow trusted users to upload custom apps, follow these steps:</span></span>

1. <span data-ttu-id="1cbe6-151">開啟 [**允許與自訂應用程式互動**] 全組織性應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-151">Turn on the **Allow interaction with custom apps** org-wide app setting.</span></span> <span data-ttu-id="1cbe6-152">若要執行此動作：</span><span class="sxs-lookup"><span data-stu-id="1cbe6-152">To do this:</span></span>
    1. <span data-ttu-id="1cbe6-153">在<a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft 團隊系統管理中心</a>的左導覽中，移至 [**團隊 app** > **管理 app**]，然後按一下 [**全組織式應用程式設定**]。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-153">In the left navigation of the <a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft Teams admin center</a>, go to **Teams apps** > **Manage apps**, and then click **Org-wide app settings**.</span></span>
    2. <span data-ttu-id="1cbe6-154">開啟 [**自訂應用程式**] 底下的 [**允許與自訂應用程式互動**]，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-154">Under **Custom apps**, turn on **Allow interaction with custom apps**, and then click **Save**.</span></span>
2. <span data-ttu-id="1cbe6-155">關閉全域 app 設定原則中的 [**上傳自訂應用程式**] 設定。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-155">Turn off the **Upload custom apps** setting in the global app setup policy.</span></span> <span data-ttu-id="1cbe6-156">若要執行此動作：</span><span class="sxs-lookup"><span data-stu-id="1cbe6-156">To do this:</span></span>
    1. <span data-ttu-id="1cbe6-157">在<a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft 團隊系統管理中心</a>的左導覽中，移至 [**團隊 app** > **設定原則**]，然後按一下 [**全域（組織範圍預設值）** ] 原則。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-157">In the left navigation of the <a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft Teams admin center</a>, go to **Teams apps** > **Setup policies**, and then click the **Global (Org-wide default)** policy.</span></span>
    2. <span data-ttu-id="1cbe6-158">關閉 **[上傳自訂應用程式**]，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-158">Turn off **Upload custom apps**, and then click **Save**.</span></span>
3. <span data-ttu-id="1cbe6-159">建立新的應用程式設定原則，以允許上傳自訂應用程式，並將它指派給您的一組受信任的使用者。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-159">Create a new app setup policy that allows uploading custom apps and assign it to your set of trusted users.</span></span> <span data-ttu-id="1cbe6-160">若要執行此動作：</span><span class="sxs-lookup"><span data-stu-id="1cbe6-160">To do this:</span></span>
    1. <span data-ttu-id="1cbe6-161">在<a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft 團隊系統管理中心</a>的左導覽中，移至 [**團隊 app** > **設定原則**]，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-161">In the left navigation of the <a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft Teams admin center</a>, go to **Teams apps** > **Setup policies**, and then click the **Add**.</span></span> <span data-ttu-id="1cbe6-162">提供新原則的名稱和描述、開啟 **[上傳自訂應用程式**]，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-162">Give the new policy a name and description, turn on **Upload custom apps**, and then click **Save**.</span></span>
    2. <span data-ttu-id="1cbe6-163">選取您建立的新原則，然後按一下 [**管理使用者**]。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-163">Select the new policy you created, and then click **Manage users**.</span></span> <span data-ttu-id="1cbe6-164">搜尋使用者 **，按一下 [\*\*\*\*新增**]，然後按一下 [套用]。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-164">Search for a user, click **Add**, and then click **Apply**.</span></span> <span data-ttu-id="1cbe6-165">重複此步驟，將原則指派給所有信任的使用者。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-165">Repeat this step to assign the policy to all your trusted users.</span></span>

        ![[新增應用程式設定原則] 頁面的螢幕擷取畫面](media/manage-your-lob-apps-new-app-setup-policy.png)

    <span data-ttu-id="1cbe6-167">這些使用者現在可以上傳應用程式資訊清單，以驗證 app 在生產租使用者中是否正常運作。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-167">These users can now upload the app manifest to validate that the app is working correctly in the production tenant.</span></span>

## <a name="step-3-upload-to-the-tenant-app-catalog"></a><span data-ttu-id="1cbe6-168">步驟3：上傳至租使用者應用程式目錄</span><span class="sxs-lookup"><span data-stu-id="1cbe6-168">Step 3: Upload to the tenant app catalog</span></span>

<span data-ttu-id="1cbe6-169">若要讓租使用者 app store 中的使用者使用該應用程式，請上傳 app。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-169">To make the app available to users in the tenant app store, upload the app.</span></span> <span data-ttu-id="1cbe6-170">您可以在 Microsoft 團隊系統管理中心的 [[管理應用程式](manage-apps.md)] 頁面上執行此動作。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-170">You can do this on the [Manage apps](manage-apps.md) page of the Microsoft Teams admin center.</span></span>

![系統管理中心 [管理應用程式] 頁面的螢幕擷取畫面](media/manage-your-lob-apps-upload-new-app.png)

## <a name="step-4-configure-and-assign-permissions"></a><span data-ttu-id="1cbe6-172">步驟4：設定及指派許可權</span><span class="sxs-lookup"><span data-stu-id="1cbe6-172">Step 4: Configure and assign permissions</span></span>

### <a name="control-access-to-the-app"></a><span data-ttu-id="1cbe6-173">控制對應用程式的存取權</span><span class="sxs-lookup"><span data-stu-id="1cbe6-173">Control access to the app</span></span>

<span data-ttu-id="1cbe6-174">根據預設，所有使用者都可以在 [團隊 app] 商店中存取此應用程式。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-174">By default, all users have access to this app in the the Teams apps store.</span></span> <span data-ttu-id="1cbe6-175">若要限制及控制誰有權使用該應用程式，您可以建立並指派新的應用程式許可權原則。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-175">To restrict and control who has permission to use the app, you can create and assign a new app permission policy.</span></span> <span data-ttu-id="1cbe6-176">請按照<a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies#create-a-custom-app-permission-policy" target="_blank">這裡</a>的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-176">Follow the steps <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies#create-a-custom-app-permission-policy" target="_blank">here</a>.</span></span>

![[新增應用程式許可權原則] 頁面的螢幕擷取畫面](media/manage-your-lob-apps-new-app-permission-policy.png)

### <a name="pin-the-app-for-users-to-discover"></a><span data-ttu-id="1cbe6-178">釘選應用程式供使用者探索</span><span class="sxs-lookup"><span data-stu-id="1cbe6-178">Pin the app for users to discover</span></span>

<span data-ttu-id="1cbe6-179">根據預設，使用者必須移至 [小組 app] 商店，然後流覽或搜尋。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-179">By default, for users to find this app they would have to go to Teams apps store and browse or search for it.</span></span> <span data-ttu-id="1cbe6-180">若要讓使用者能夠輕鬆存取應用程式，您可以將應用程式釘選到 [團隊] 中的應用程式行。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-180">To make it easy for users to get to the app, you can pin the app to the app bar in Teams.</span></span> <span data-ttu-id="1cbe6-181">若要這樣做，請建立新的應用程式設定原則，並將它指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-181">To do this, create a new app setup policy and assign it to users.</span></span> <span data-ttu-id="1cbe6-182">請按照<a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies#create-a-custom-app-setup-policy" target="_blank">這裡</a>的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-182">Follow the steps  <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies#create-a-custom-app-setup-policy" target="_blank">here</a>.</span></span>

![[新增釘選的 app] 窗格的螢幕擷取畫面](media/manage-your-lob-apps-pinned-apps.png)

## <a name="step-5-update-the-app"></a><span data-ttu-id="1cbe6-184">步驟5：更新應用程式</span><span class="sxs-lookup"><span data-stu-id="1cbe6-184">Step 5: Update the app</span></span>

![從開發到部署的應用程式概覽](media/manage-your-lob-apps-update.png)

<span data-ttu-id="1cbe6-186">若要更新應用程式，開發人員應該繼續遵循[步驟 1](#step-1-develop-and-test)和[步驟 2](#step-2-validate-in-production)。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-186">To update an app, developers should continue to follow [step 1](#step-1-develop-and-test) and [step 2](#step-2-validate-in-production).</span></span>

<span data-ttu-id="1cbe6-187">您可以透過租使用者應用程式目錄來更新應用程式。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-187">You can update the app through the tenant app catalog.</span></span> <span data-ttu-id="1cbe6-188">若要這樣做，請在 Microsoft 團隊系統管理中心，移至 [**團隊 app** > **管理應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-188">To do this, in the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="1cbe6-189">在應用程式清單中，按一下應用程式名稱，然後按一下 [**更新**]。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-189">In the list of apps, click the app name, and then click **Update**.</span></span> <span data-ttu-id="1cbe6-190">這樣做會取代租使用者目錄中現有的 app，而且所有 app 許可權原則和應用程式設定原則都會針對更新的 app 保持強制執行。</span><span class="sxs-lookup"><span data-stu-id="1cbe6-190">Doing this replaces the existing app in the tenant app catalog, and all app permission policies and app setup policies remain enforced for the updated app.</span></span>

## <a name="related-apps"></a><span data-ttu-id="1cbe6-191">相關應用程式</span><span class="sxs-lookup"><span data-stu-id="1cbe6-191">Related apps</span></span>

- [<span data-ttu-id="1cbe6-192">在 Microsoft 團隊系統管理中心管理您的應用程式</span><span class="sxs-lookup"><span data-stu-id="1cbe6-192">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)