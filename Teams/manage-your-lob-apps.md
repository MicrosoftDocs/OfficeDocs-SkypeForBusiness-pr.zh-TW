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
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何將自訂團隊 app 從開發開發到部署。
ms.openlocfilehash: cd64ff0a3307ada0f1fbfaf29b94cfcd1da3c0df
ms.sourcegitcommit: d6a0ff7f00defda2b58726f5f0f0fac871f46ab7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2019
ms.locfileid: "37682693"
---
# <a name="manage-your-line-of-business-apps-in-microsoft-teams"></a><span data-ttu-id="bc7de-103">在 Microsoft 團隊中管理您的商務用應用程式</span><span class="sxs-lookup"><span data-stu-id="bc7de-103">Manage your line-of-business apps in Microsoft Teams</span></span>

<span data-ttu-id="bc7de-104">本文提供如何將您的小組 app 從開發開發到部署的端對端指導方針。</span><span class="sxs-lookup"><span data-stu-id="bc7de-104">This article provides end-to-end guidance for how to take your Teams app from development to deployment.</span></span> <span data-ttu-id="bc7de-105">本指南主要說明 app 的小組各部分，且適用于 IT 專業人員。</span><span class="sxs-lookup"><span data-stu-id="bc7de-105">This guidance focuses on the Teams aspects of the app and is intended for IT pros.</span></span> <span data-ttu-id="bc7de-106">如需開發小組 app 的詳細資訊，請參閱[這裡](https://docs.microsoft.com/microsoftteams/platform)。</span><span class="sxs-lookup"><span data-stu-id="bc7de-106">For more information on developing Teams apps, see [here](https://docs.microsoft.com/microsoftteams/platform).</span></span>

![從開發到部署的應用程式概覽](media/manage-your-lob-apps.png)

## <a name="getting-started"></a><span data-ttu-id="bc7de-108">快速入門</span><span class="sxs-lookup"><span data-stu-id="bc7de-108">Getting started</span></span>

<span data-ttu-id="bc7de-109">若要在小組中建立及管理企業往來（LOB）應用程式，您需要兩個租使用者：用於開發和生產租使用者的測試租使用者。</span><span class="sxs-lookup"><span data-stu-id="bc7de-109">To create and manage line-of-business (LOB) apps in Teams, you’ll need two tenants: a test tenant for development and a production tenant.</span></span>

> [!NOTE]
> <span data-ttu-id="bc7de-110">如果您還沒有測試租使用者，您可以使用 Office 365 開發人員程式，快速建立一個並填入測試資料。</span><span class="sxs-lookup"><span data-stu-id="bc7de-110">If you don’t already have a test tenant, you can quickly create one and populate it with test data using the Office 365 Developer Program.</span></span> <span data-ttu-id="bc7de-111">[深入瞭解](https://developer.microsoft.com/office/dev-program)。</span><span class="sxs-lookup"><span data-stu-id="bc7de-111">[Learn more here](https://developer.microsoft.com/office/dev-program).</span></span>

## <a name="step-1-develop-and-test"></a><span data-ttu-id="bc7de-112">步驟1：開發與測試</span><span class="sxs-lookup"><span data-stu-id="bc7de-112">Step 1: Develop and test</span></span>

### <a name="create-test-users"></a><span data-ttu-id="bc7de-113">建立測試使用者</span><span class="sxs-lookup"><span data-stu-id="bc7de-113">Create test users</span></span>

<span data-ttu-id="bc7de-114">請確定您的開發人員（無論是內部還是外部）在您的測試租使用者中有帳戶。</span><span class="sxs-lookup"><span data-stu-id="bc7de-114">Make sure that your developers, whether in-house or external, have accounts in your test tenant.</span></span> <span data-ttu-id="bc7de-115">[深入瞭解如何新增使用者](https://docs.microsoft.com/office365/admin/add-users/add-users)。</span><span class="sxs-lookup"><span data-stu-id="bc7de-115">[Learn more about adding users](https://docs.microsoft.com/office365/admin/add-users/add-users).</span></span>

### <a name="allow-custom-apps-in-the-test-tenant"></a><span data-ttu-id="bc7de-116">允許測試租使用者中的自訂應用程式</span><span class="sxs-lookup"><span data-stu-id="bc7de-116">Allow custom apps in the test tenant</span></span>

<span data-ttu-id="bc7de-117">若要為開發人員提供測試所需的存取權，請允許測試租使用者中的所有使用者上傳自訂應用程式（也稱為邊載）。</span><span class="sxs-lookup"><span data-stu-id="bc7de-117">To give developers the access they need for testing, allow all users in the test tenant to upload custom apps (also known as sideloading).</span></span> <span data-ttu-id="bc7de-118">這可讓開發人員上傳自訂的應用程式，以供個人或跨測試租使用者使用，而不需將 app 提交到 [小組 app] 存放區。</span><span class="sxs-lookup"><span data-stu-id="bc7de-118">This lets developers upload a custom app to be used personally or across the test tenant without having to submit the app to the Teams apps store.</span></span> <span data-ttu-id="bc7de-119">上傳自訂的應用程式可讓開發人員在您更廣泛地發佈 app 之前先測試應用程式。</span><span class="sxs-lookup"><span data-stu-id="bc7de-119">Uploading a custom app lets developers test an app before you distribute it more widely.</span></span>

<span data-ttu-id="bc7de-120">若要允許使用者上傳自訂應用程式，請依照下列步驟執行：</span><span class="sxs-lookup"><span data-stu-id="bc7de-120">To allow users to upload custom apps, follow these steps:</span></span>

1. <span data-ttu-id="bc7de-121">開啟 [**允許與自訂應用程式互動**] 的全組織性設定。</span><span class="sxs-lookup"><span data-stu-id="bc7de-121">Turn on the **Allow interaction with custom apps** org-wide setting.</span></span> <span data-ttu-id="bc7de-122">若要執行此動作：</span><span class="sxs-lookup"><span data-stu-id="bc7de-122">To do this:</span></span>
    1. <span data-ttu-id="bc7de-123">在[Microsoft 團隊系統管理中心](https://admin.teams.microsoft.com/)的左導覽中，移至 [**團隊 app** > **許可權原則**]，然後按一下 [**全組織性設定**]。</span><span class="sxs-lookup"><span data-stu-id="bc7de-123">In the left navigation of the [Microsoft Teams admin center](https://admin.teams.microsoft.com/), go to **Teams apps** > **Permission policies**, and then click **Org-wide settings**.</span></span>
    2. <span data-ttu-id="bc7de-124">開啟 [**自訂應用程式**] 底下的 [**允許與自訂應用程式互動**]，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="bc7de-124">Under **Custom apps**, turn on **Allow interaction with custom apps**, and then click **Save**.</span></span>

    ![[允許與自訂應用程式互動] 的螢幕擷取畫面-全組織性設定](media/manage-your-lob-apps-org-wide-custom-apps.png)

2. <span data-ttu-id="bc7de-126">開啟全域 app 設定原則中的 [上**傳自訂應用程式**] 設定。</span><span class="sxs-lookup"><span data-stu-id="bc7de-126">Turn on the **Upload custom apps** setting in the global app setup policy.</span></span> <span data-ttu-id="bc7de-127">若要執行此動作：</span><span class="sxs-lookup"><span data-stu-id="bc7de-127">To do this:</span></span>
    1. <span data-ttu-id="bc7de-128">在[Microsoft 團隊系統管理中心](https://admin.teams.microsoft.com/)的左導覽中，移至 [**團隊 app** > **設定原則**]，然後按一下 [**全域（組織範圍預設值）** ] 原則。</span><span class="sxs-lookup"><span data-stu-id="bc7de-128">In the left navigation of the [Microsoft Teams admin center](https://admin.teams.microsoft.com/), go to **Teams apps** > **Setup policies**, and then click the **Global (Org-wide default)** policy.</span></span>
    2. <span data-ttu-id="bc7de-129">開啟 **[上傳自訂應用程式**]，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="bc7de-129">Turn on **Upload custom apps**, and then click **Save**.</span></span>

    ![[上傳自訂應用程式] app 設定策略設定的螢幕擷取畫面](media/manage-your-lob-apps-app-setup-custom-apps.png)

> [!NOTE]
> <span data-ttu-id="bc7de-131">此外，小組層級也會有上傳自訂應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="bc7de-131">There's also an upload custom app setting at the team level.</span></span> <span data-ttu-id="bc7de-132">根據預設，此設定為 [開啟]。</span><span class="sxs-lookup"><span data-stu-id="bc7de-132">By default this setting is on.</span></span> <span data-ttu-id="bc7de-133">不過，如果開發人員無法將自訂應用程式上傳至團隊，請按照[這裡](teams-custom-app-policies-and-settings.md#configure-the-team-custom-app-setting)的步驟來檢查該設定。</span><span class="sxs-lookup"><span data-stu-id="bc7de-133">However, if developers are unable to upload a custom app to a team, check the setting by following the steps [here](teams-custom-app-policies-and-settings.md#configure-the-team-custom-app-setting).</span></span>

### <a name="create-your-app"></a><span data-ttu-id="bc7de-134">建立您的應用程式</span><span class="sxs-lookup"><span data-stu-id="bc7de-134">Create your app</span></span>

<span data-ttu-id="bc7de-135">開發人員現在應該擁有建立您 app 所需的專案。</span><span class="sxs-lookup"><span data-stu-id="bc7de-135">Developers should now have what they need to create your app.</span></span> <span data-ttu-id="bc7de-136">請參閱[這裡](https://docs.microsoft.commicrosoftteams/platform)以取得相關指導方針。</span><span class="sxs-lookup"><span data-stu-id="bc7de-136">See [here](https://docs.microsoft.commicrosoftteams/platform) for guidance on that.</span></span>

## <a name="step-2-validate-in-production"></a><span data-ttu-id="bc7de-137">步驟2：在生產中驗證</span><span class="sxs-lookup"><span data-stu-id="bc7de-137">Step 2: Validate in production</span></span>

### <a name="get-the-app-package"></a><span data-ttu-id="bc7de-138">取得應用程式套件</span><span class="sxs-lookup"><span data-stu-id="bc7de-138">Get the app package</span></span>

<span data-ttu-id="bc7de-139">當應用程式準備好在生產中使用時，開發人員應該會產生應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="bc7de-139">When the app is ready for use in production, the developer should produce an app package.</span></span> <span data-ttu-id="bc7de-140">他們可以使用[應用程式 Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)來執行此程式。</span><span class="sxs-lookup"><span data-stu-id="bc7de-140">They can use [App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio) for that.</span></span> <span data-ttu-id="bc7de-141">他們會以 .zip 格式傳送檔案。</span><span class="sxs-lookup"><span data-stu-id="bc7de-141">They'll send you the file in .zip format.</span></span>

<span data-ttu-id="bc7de-142">Microsoft 使用[這些指導方針](https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval)，以確保 app 符合全域團隊 app store 的品質與安全性標準。</span><span class="sxs-lookup"><span data-stu-id="bc7de-142">Microsoft uses [these guidelines](https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval) to ensure apps comply with the quality and security standards of the global Teams apps store.</span></span>

### <a name="allow-trusted-users-to-upload-custom-apps-in-the-production-tenant"></a><span data-ttu-id="bc7de-143">允許信任的使用者上傳生產租使用者中的自訂應用程式</span><span class="sxs-lookup"><span data-stu-id="bc7de-143">Allow trusted users to upload custom apps in the production tenant</span></span>

<span data-ttu-id="bc7de-144">若要驗證 app 在您的生產租使用者中是否正常運作，您必須允許您的組織中的人員和/或受信任的使用者上傳自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="bc7de-144">To validate that the app is working correctly in your production tenant, you need to allow yourself and/or trusted users in your organization to upload custom apps.</span></span>  <span data-ttu-id="bc7de-145">與 [測試租使用者] 步驟中的 [舊版[允許自訂應用](#allow-custom-apps-in-the-test-tenant)程式] 相似，您可以使用 app 設定原則來執行這項作業。</span><span class="sxs-lookup"><span data-stu-id="bc7de-145">Much like in the earlier [Allow custom apps in the test tenant](#allow-custom-apps-in-the-test-tenant) step, you use app setup policies to do this.</span></span>

> [!NOTE]
> <span data-ttu-id="bc7de-146">如果您不滿意將 app 上傳到您的生產租使用者進行驗證，即使您是自己或受信任的使用者，您也可以略過此步驟，然後遵循步驟3和4，將 unvalidated 應用程式上傳到您的租使用者應用程式存放區。</span><span class="sxs-lookup"><span data-stu-id="bc7de-146">If you’re uncomfortable with uploading the app to your production tenant for validation, even for yourself or trusted users, you can skip this step and follow steps 3 and 4 to upload the unvalidated app to your tenant apps store.</span></span> <span data-ttu-id="bc7de-147">然後，將該 app 的存取許可權制為只有您自己和您信任的使用者。</span><span class="sxs-lookup"><span data-stu-id="bc7de-147">Then, restrict access to that app to only yourself and users you trust.</span></span> <span data-ttu-id="bc7de-148">然後，這些使用者就可以從租使用者應用程式商店取得 app 來執行驗證。</span><span class="sxs-lookup"><span data-stu-id="bc7de-148">These users can then get the app from the tenant apps store to perform validation.</span></span> <span data-ttu-id="bc7de-149">驗證應用程式後，請使用相同的許可權原則來開啟 access，並將 app 滾出以供生產使用。</span><span class="sxs-lookup"><span data-stu-id="bc7de-149">After the app is validated, use the same permission policies to open access and roll the app out for production use.</span></span>

<span data-ttu-id="bc7de-150">若要允許信任的使用者上傳自訂應用程式，請依照下列步驟執行：</span><span class="sxs-lookup"><span data-stu-id="bc7de-150">To allow trusted users to upload custom apps, follow these steps:</span></span>

1. <span data-ttu-id="bc7de-151">開啟 [**允許與自訂應用程式互動**] 的全組織性設定。</span><span class="sxs-lookup"><span data-stu-id="bc7de-151">Turn on the **Allow interaction with custom apps** org-wide setting.</span></span> <span data-ttu-id="bc7de-152">若要執行此動作：</span><span class="sxs-lookup"><span data-stu-id="bc7de-152">To do this:</span></span>
    1. <span data-ttu-id="bc7de-153">在[Microsoft 團隊系統管理中心](https://admin.teams.microsoft.com/)的左導覽中，移至 [**團隊 app** > **許可權原則**]，然後按一下 [**全組織性設定**]。</span><span class="sxs-lookup"><span data-stu-id="bc7de-153">In the left navigation of the [Microsoft Teams admin center](https://admin.teams.microsoft.com/), go to **Teams apps** > **Permission policies**, and then click **Org-wide settings**.</span></span>
    2. <span data-ttu-id="bc7de-154">開啟 [**自訂應用程式**] 底下的 [**允許與自訂應用程式互動**]，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="bc7de-154">Under **Custom apps**, turn on **Allow interaction with custom apps**, and then click **Save**.</span></span>
2. <span data-ttu-id="bc7de-155">關閉全域 app 設定原則中的 [**上傳自訂應用程式**] 設定。</span><span class="sxs-lookup"><span data-stu-id="bc7de-155">Turn off the **Upload custom apps** setting in the global app setup policy.</span></span> <span data-ttu-id="bc7de-156">若要執行此動作：</span><span class="sxs-lookup"><span data-stu-id="bc7de-156">To do this:</span></span>
    1. <span data-ttu-id="bc7de-157">在[Microsoft 團隊系統管理中心](https://admin.teams.microsoft.com/)的左導覽中，移至 [**團隊 app** > **設定原則**]，然後按一下 [**全域（組織範圍預設值）** ] 原則。</span><span class="sxs-lookup"><span data-stu-id="bc7de-157">In the left navigation of the [Microsoft Teams admin center](https://admin.teams.microsoft.com/), go to **Teams apps** > **Setup policies**, and then click the **Global (Org-wide default)** policy.</span></span>
    2. <span data-ttu-id="bc7de-158">關閉 **[上傳自訂應用程式**]，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="bc7de-158">Turn off **Upload custom apps**, and then click **Save**.</span></span>
3. <span data-ttu-id="bc7de-159">建立新的應用程式設定原則，以允許上傳自訂應用程式，並將它指派給您的一組受信任的使用者。</span><span class="sxs-lookup"><span data-stu-id="bc7de-159">Create a new app setup policy that allows uploading custom apps and assign it to your set of trusted users.</span></span> <span data-ttu-id="bc7de-160">若要執行此動作：</span><span class="sxs-lookup"><span data-stu-id="bc7de-160">To do this:</span></span>
    1. <span data-ttu-id="bc7de-161">在[Microsoft 團隊系統管理中心](https://admin.teams.microsoft.com/)的左導覽中，移至 [**團隊 app** > **設定原則**]，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="bc7de-161">In the left navigation of the [Microsoft Teams admin center](https://admin.teams.microsoft.com/), go to **Teams apps** > **Setup policies**, and then click the **Add**.</span></span> <span data-ttu-id="bc7de-162">提供新原則的名稱和描述、開啟 **[上傳自訂應用程式**]，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="bc7de-162">Give the new policy a name and description, turn on **Upload custom apps**, and then click **Save**.</span></span>
    2. <span data-ttu-id="bc7de-163">選取您建立的新原則，然後按一下 [**管理使用者**]。</span><span class="sxs-lookup"><span data-stu-id="bc7de-163">Select the new policy you created, and then click **Manage users**.</span></span> <span data-ttu-id="bc7de-164">搜尋使用者 **，按一下 [\*\*\*\*新增**]，然後按一下 [套用]。</span><span class="sxs-lookup"><span data-stu-id="bc7de-164">Search for a user, click **Add**, and then click **Apply**.</span></span> <span data-ttu-id="bc7de-165">重複此步驟，將原則指派給所有信任的使用者。</span><span class="sxs-lookup"><span data-stu-id="bc7de-165">Repeat this step to assign the policy to all your trusted users.</span></span>

        ![[新增應用程式設定原則] 頁面的螢幕擷取畫面](media/manage-your-lob-apps-new-app-setup-policy.png)

    <span data-ttu-id="bc7de-167">這些使用者現在可以上傳應用程式資訊清單，以驗證 app 在生產租使用者中是否正常運作。</span><span class="sxs-lookup"><span data-stu-id="bc7de-167">These users can now upload the app manifest to validate that the app is working correctly in the production tenant.</span></span>

## <a name="step-3-upload-to-the-tenant-apps-catalog"></a><span data-ttu-id="bc7de-168">步驟3：上傳至租使用者應用程式目錄</span><span class="sxs-lookup"><span data-stu-id="bc7de-168">Step 3: Upload to the Tenant Apps Catalog</span></span>

<span data-ttu-id="bc7de-169">若要讓 [租使用者應用程式] 存放區中的使用者使用 app，請上傳 app。</span><span class="sxs-lookup"><span data-stu-id="bc7de-169">To make the app available to users in the tenant apps store, upload the app.</span></span> <span data-ttu-id="bc7de-170">您可以使用小組桌面用戶端來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="bc7de-170">You can do this using the Teams desktop client.</span></span> <span data-ttu-id="bc7de-171">請按照[這裡](tenant-apps-catalog-teams.md#go-to-the-tenant-apps-catalog)的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="bc7de-171">Follow the steps [here](tenant-apps-catalog-teams.md#go-to-the-tenant-apps-catalog).</span></span>

![[應用程式] 頁面的螢幕擷取畫面](media/manage-your-lob-apps-store.png)

## <a name="step-4-configure-and-assign-permissions"></a><span data-ttu-id="bc7de-173">步驟4：設定及指派許可權</span><span class="sxs-lookup"><span data-stu-id="bc7de-173">Step 4: Configure and assign permissions</span></span>

### <a name="control-access-to-the-app"></a><span data-ttu-id="bc7de-174">控制對應用程式的存取權</span><span class="sxs-lookup"><span data-stu-id="bc7de-174">Control access to the app</span></span>

<span data-ttu-id="bc7de-175">根據預設，所有使用者都可以在 [團隊 app] 商店中存取此應用程式。</span><span class="sxs-lookup"><span data-stu-id="bc7de-175">By default, all users have access to this app in the the Teams apps store.</span></span> <span data-ttu-id="bc7de-176">若要限制及控制誰有權使用該應用程式，您可以建立並指派新的應用程式許可權原則。</span><span class="sxs-lookup"><span data-stu-id="bc7de-176">To restrict and control who has permission to use the app, you can create and assign a new app permission policy.</span></span> <span data-ttu-id="bc7de-177">請按照[這裡](teams-app-permission-policies.md#create-a-custom-app-permission-policy)的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="bc7de-177">Follow the steps [here](teams-app-permission-policies.md#create-a-custom-app-permission-policy).</span></span>

![[新增應用程式許可權原則] 頁面的螢幕擷取畫面](media/manage-your-lob-apps-new-app-permission-policy.png)

### <a name="pin-the-app-for-users-to-discover"></a><span data-ttu-id="bc7de-179">釘選應用程式供使用者探索</span><span class="sxs-lookup"><span data-stu-id="bc7de-179">Pin the app for users to discover</span></span>

<span data-ttu-id="bc7de-180">根據預設，使用者必須移至 [小組 app] 商店，然後流覽或搜尋。</span><span class="sxs-lookup"><span data-stu-id="bc7de-180">By default, for users to find this app they would have to go to Teams apps store and browse or search for it.</span></span> <span data-ttu-id="bc7de-181">若要讓使用者能夠輕鬆存取應用程式，您可以將應用程式釘選到 [團隊] 中的應用程式行。</span><span class="sxs-lookup"><span data-stu-id="bc7de-181">To make it easy for users to get to the app, you can pin the app to the app bar in Teams.</span></span> <span data-ttu-id="bc7de-182">若要這樣做，請建立新的應用程式設定原則，並將它指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="bc7de-182">To do this, create a new app setup policy and assign it to users.</span></span> <span data-ttu-id="bc7de-183">請按照[這裡](teams-app-setup-policies.md#create-a-custom-app-setup-policy)的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="bc7de-183">Follow the steps [here](teams-app-setup-policies.md#create-a-custom-app-setup-policy).</span></span>

![[新增釘選的 app] 窗格的螢幕擷取畫面](media/manage-your-lob-apps-pinned-apps.png)

## <a name="step-5-update-the-app"></a><span data-ttu-id="bc7de-185">步驟5：更新應用程式</span><span class="sxs-lookup"><span data-stu-id="bc7de-185">Step 5: Update the app</span></span>

![從開發到部署的應用程式概覽](media/manage-your-lob-apps-update.png)

<span data-ttu-id="bc7de-187">若要更新應用程式，開發人員應該繼續遵循[步驟 1](#step-1-develop-and-test)和[步驟 2](#step-2-validate-in-production)。</span><span class="sxs-lookup"><span data-stu-id="bc7de-187">To update an app, developers should continue to follow [step 1](#step-1-develop-and-test) and [step 2](#step-2-validate-in-production).</span></span>

<span data-ttu-id="bc7de-188">您可以透過租使用者應用程式目錄來更新應用程式。</span><span class="sxs-lookup"><span data-stu-id="bc7de-188">You can update the app through the Tenant Apps Catalog.</span></span> <span data-ttu-id="bc7de-189">若要這樣做，請在團隊桌面用戶端，移至**針對&lt;您的租&gt;使用者名稱所建的** **app** > ，按一下 **...**</span><span class="sxs-lookup"><span data-stu-id="bc7de-189">To do this, in the Teams desktop client, go to **Apps** > **Built for &lt;Your tenant name&gt;**, click **…**</span></span> <span data-ttu-id="bc7de-190">按一下應用程式右上角的，然後按一下 [**更新**]。</span><span class="sxs-lookup"><span data-stu-id="bc7de-190">in the upper-right corner of the app, and then click **Update**.</span></span> <span data-ttu-id="bc7de-191">這麼做會取代租使用者應用程式目錄中的現有應用程式，而且擁有權限原則和設定原則都會針對更新的 app 保持強制執行。</span><span class="sxs-lookup"><span data-stu-id="bc7de-191">Doing this replaces the existing app in the Tenant Apps Catalog, and all permission policies and setup policies remain enforced for the updated app.</span></span> 

![在 [應用程式] 頁面上更新應用程式的螢幕擷取畫面](media/manage-your-lob-apps-update-app.png)