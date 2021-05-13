---
title: 在應用程式中自訂Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在應用程式中自訂Microsoft Teams。
ms.openlocfilehash: a43272c19c00079b5a0f0299a5630ca6e6ec78e5
ms.sourcegitcommit: 40f76bc6b5e304faea8516a78f8576ba1cdb7f7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2021
ms.locfileid: "52337800"
---
# <a name="customize-apps-in-microsoft-teams"></a><span data-ttu-id="cdafd-103">在應用程式中自訂Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cdafd-103">Customize apps in Microsoft Teams</span></span>

 <span data-ttu-id="cdafd-104">Microsoft Teams應用程式自訂功能，以增強Teams體驗。</span><span class="sxs-lookup"><span data-stu-id="cdafd-104">Microsoft Teams provides app customization to enhance the Teams experience.</span></span> <span data-ttu-id="cdafd-105">有些應用程式開發人員允許系統管理員自訂Teams應用程式。管理員可以使用系統管理中心管理應用程式頁面，根據組織需求自訂或重新Teams **應用程式** 屬性。</span><span class="sxs-lookup"><span data-stu-id="cdafd-105">Some app developers allow an app to be customized by the Teams admin. The admin can customize or rebrand the app properties based on the organizational needs using the Teams admin center **Manage apps** page.</span></span> <span data-ttu-id="cdafd-106">您可以自訂的詳細資訊有：</span><span class="sxs-lookup"><span data-stu-id="cdafd-106">The details you can customize are:</span></span>

- <span data-ttu-id="cdafd-107">簡短名稱</span><span class="sxs-lookup"><span data-stu-id="cdafd-107">Short name</span></span>
- <span data-ttu-id="cdafd-108">簡短描述</span><span class="sxs-lookup"><span data-stu-id="cdafd-108">Short description</span></span>
- <span data-ttu-id="cdafd-109">完整描述</span><span class="sxs-lookup"><span data-stu-id="cdafd-109">Full description</span></span>
- <span data-ttu-id="cdafd-110">隱私權政策 URL</span><span class="sxs-lookup"><span data-stu-id="cdafd-110">Privacy policy URL</span></span>
- <span data-ttu-id="cdafd-111">網站 URL</span><span class="sxs-lookup"><span data-stu-id="cdafd-111">Website URL</span></span>
- <span data-ttu-id="cdafd-112">使用條款 URL</span><span class="sxs-lookup"><span data-stu-id="cdafd-112">Terms of use URL</span></span>
- <span data-ttu-id="cdafd-113">色彩圖示</span><span class="sxs-lookup"><span data-stu-id="cdafd-113">Color icon</span></span>
- <span data-ttu-id="cdafd-114">大綱圖示</span><span class="sxs-lookup"><span data-stu-id="cdafd-114">Outline icon</span></span>
- <span data-ttu-id="cdafd-115">強調色彩</span><span class="sxs-lookup"><span data-stu-id="cdafd-115">Accent color</span></span>

<span data-ttu-id="cdafd-116">請參閱Teams清單[架構](https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema)，以瞭解有關您可以自訂之欄位的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="cdafd-116">See the [Teams Manifest schema](https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema) for details about the fields that you can customize.</span></span>

> [!NOTE]
> <span data-ttu-id="cdafd-117">目前，在 政府社群雲端 GCCH (或) DoD (不支援自訂應用程式) 。</span><span class="sxs-lookup"><span data-stu-id="cdafd-117">Customizing apps isn't supported in Government Community Cloud High (GCCH) or Department of Defense (DoD) at this time.</span></span>

## <a name="customize-the-apps-details"></a><span data-ttu-id="cdafd-118">自訂應用程式詳細資料</span><span class="sxs-lookup"><span data-stu-id="cdafd-118">Customize the app's details</span></span>

<span data-ttu-id="cdafd-119">若要開始自訂應用程式，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="cdafd-119">To start customizing an app, complete the following steps:</span></span>

1. <span data-ttu-id="cdafd-120">登入 Teams 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="cdafd-120">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="cdafd-121">展開 **Teams應用程式**，然後選取 **管理應用程式**。</span><span class="sxs-lookup"><span data-stu-id="cdafd-121">Expand **Teams Apps** and select **Manage apps**.</span></span>
3. <span data-ttu-id="cdafd-122">檢查應用程式 **清單** 的可自訂欄，並按可自訂的應用程式排序。</span><span class="sxs-lookup"><span data-stu-id="cdafd-122">Check the **Customizable** column of the apps list and sort by apps that are customizable.</span></span>

   ![已排序的自訂欄](media/customize-column.png)

   <span data-ttu-id="cdafd-124">有三個進入點可存取自訂功能：</span><span class="sxs-lookup"><span data-stu-id="cdafd-124">There are three entry points to access the customize feature:</span></span>

   - <span data-ttu-id="cdafd-125">選取要自訂之應用程式旁的 ， **然後選取** 自訂 。</span><span class="sxs-lookup"><span data-stu-id="cdafd-125">Select next to the app that you want to customize, and then select **Customize**.</span></span>

     ![自訂選取選項 1](media/select-app-to-customize1.png)

   - <span data-ttu-id="cdafd-127">選取應用程式名稱，然後選取可 **自訂**。</span><span class="sxs-lookup"><span data-stu-id="cdafd-127">Select the app name and then **Customizable**.</span></span>

     ![自訂選取選項 2](media/app-details-customizable.png)

   - <span data-ttu-id="cdafd-129">選取應用程式名稱， **然後從動作** 下拉下拉選取 **自訂** 。</span><span class="sxs-lookup"><span data-stu-id="cdafd-129">Select the app name, and then select **Customize** from the **Actions** dropdown.</span></span>

     ![自訂選取選項 3](media/customize-action-menu.png)

4. <span data-ttu-id="cdafd-131">展開詳細 **資料** 區段並自訂下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="cdafd-131">Expand the **Details** section and customize the following fields:</span></span>

    - <span data-ttu-id="cdafd-132">簡短名稱</span><span class="sxs-lookup"><span data-stu-id="cdafd-132">Short name</span></span>
    - <span data-ttu-id="cdafd-133">簡短描述</span><span class="sxs-lookup"><span data-stu-id="cdafd-133">Short description</span></span>
    - <span data-ttu-id="cdafd-134">完整描述</span><span class="sxs-lookup"><span data-stu-id="cdafd-134">Full description</span></span>
    - <span data-ttu-id="cdafd-135">網站</span><span class="sxs-lookup"><span data-stu-id="cdafd-135">Website</span></span>
    - <span data-ttu-id="cdafd-136">隱私權政策 URL</span><span class="sxs-lookup"><span data-stu-id="cdafd-136">Privacy policy URL</span></span>
    - <span data-ttu-id="cdafd-137">使用條款 URL</span><span class="sxs-lookup"><span data-stu-id="cdafd-137">Terms of use URL</span></span>

   ![自訂設定](media/customize-settings.png)

> [!Note]
> <span data-ttu-id="cdafd-139">只會顯示 App 開發人員指派為可自訂的欄位。</span><span class="sxs-lookup"><span data-stu-id="cdafd-139">Only the fields that the app developer has assigned as customizable will be visible.</span></span>

5. <span data-ttu-id="cdafd-140">展開圖示 **區** 段。</span><span class="sxs-lookup"><span data-stu-id="cdafd-140">Expand the **Icon** section.</span></span>

   <span data-ttu-id="cdafd-141">a.</span><span class="sxs-lookup"><span data-stu-id="cdafd-141">a.</span></span> <span data-ttu-id="cdafd-142">Upload圖示。</span><span class="sxs-lookup"><span data-stu-id="cdafd-142">Upload an icon.</span></span> <span data-ttu-id="cdafd-143">在 PNG 格式的 192x192 (圖元) 全色圖示。</span><span class="sxs-lookup"><span data-stu-id="cdafd-143">Use one full-color icon (192x192) pixel in PNG format.</span></span>

   <span data-ttu-id="cdafd-144">b.</span><span class="sxs-lookup"><span data-stu-id="cdafd-144">b.</span></span> <span data-ttu-id="cdafd-145">選擇圖示外邊框色彩。</span><span class="sxs-lookup"><span data-stu-id="cdafd-145">Choose an icon outline color.</span></span> <span data-ttu-id="cdafd-146">使用一個 32x32 (32x32) PNG 格式的透明外邊框。</span><span class="sxs-lookup"><span data-stu-id="cdafd-146">Use one transparent outline (32x32) pixel in PNG format.</span></span>

   <span data-ttu-id="cdafd-147">C。</span><span class="sxs-lookup"><span data-stu-id="cdafd-147">c.</span></span> <span data-ttu-id="cdafd-148">選取符合圖示的應用程式強調色彩。</span><span class="sxs-lookup"><span data-stu-id="cdafd-148">Select an app accent color that matches the icon.</span></span>

    ![自訂圖示面板色彩選項](media/customize-app-colors.png)

6. <span data-ttu-id="cdafd-150">自訂應用程式之後，請選取 **Apply**。</span><span class="sxs-lookup"><span data-stu-id="cdafd-150">Once your app has been customized, select **Apply**.</span></span>

7. <span data-ttu-id="cdafd-151">選取 **發佈** 以發佈自訂的應用程式。</span><span class="sxs-lookup"><span data-stu-id="cdafd-151">Select **Publish** to publish the customized app.</span></span>

   <span data-ttu-id="cdafd-152">自訂的應用程式現在會列在您的管理 **應用程式頁面中** 。</span><span class="sxs-lookup"><span data-stu-id="cdafd-152">The customized app is now listed in your **Manage apps** page.</span></span> <span data-ttu-id="cdafd-153">由於自訂應用程式功能不會建立應用程式的副本，因此您只會擁有一個版本的應用程式。</span><span class="sxs-lookup"><span data-stu-id="cdafd-153">You'll have only one version of the app, since customizing the app features doesn't create a copy of the app.</span></span>

<span data-ttu-id="cdafd-154">現在您的Teams使用者可以開啟其Teams用戶端以查看自訂的應用程式。</span><span class="sxs-lookup"><span data-stu-id="cdafd-154">Now your Teams end users can open their Teams client to see the customized app.</span></span>

   ![用戶端中的自訂Teams應用程式](media/contoso-app.png)

### <a name="special-considerations-for-customizing-an-app"></a><span data-ttu-id="cdafd-156">自訂應用程式的特殊考慮</span><span class="sxs-lookup"><span data-stu-id="cdafd-156">Special considerations for customizing an app</span></span>

<span data-ttu-id="cdafd-157">下列附注包含自訂應用程式的重要詳細資料。</span><span class="sxs-lookup"><span data-stu-id="cdafd-157">The following note includes important details about customizing an app.</span></span>

> [!Note]
> - <span data-ttu-id="cdafd-158">當您自訂應用程式，以及任何與應用程式相關的描述時，請確保遵循應用程式發行者在檔或使用條款中提供的任何自訂指導方針。</span><span class="sxs-lookup"><span data-stu-id="cdafd-158">When you customize apps, and any description related to an app, ensure that you follow any customization guidelines if provided by the app publisher in their documentation or terms of use.</span></span> <span data-ttu-id="cdafd-159">您也有責任尊重其他人對於您可能使用之任何協力廠商影像的權利。</span><span class="sxs-lookup"><span data-stu-id="cdafd-159">You're also responsible for respecting the rights of others regarding any third-party images you might use.</span></span>
> - <span data-ttu-id="cdafd-160">系統管理提供的自訂資料會儲存在最近的地區。</span><span class="sxs-lookup"><span data-stu-id="cdafd-160">Admin-provided customization data is stored in the nearest region.</span></span>
> - <span data-ttu-id="cdafd-161">您負責確保使用條款或隱私權政策的連結有效。</span><span class="sxs-lookup"><span data-stu-id="cdafd-161">You are responsible for ensuring that links to terms of use or privacy policy are valid.</span></span>
> - <span data-ttu-id="cdafd-162">如果應用程式發行者不再允許欄位可自訂，應用程式詳細資料頁面上會出現一則訊息，通知系統管理員無法再自訂的欄位。</span><span class="sxs-lookup"><span data-stu-id="cdafd-162">In case the app publisher no longer allows a field to be customizable, a message appears on the app details page notifying the admin about the fields that can't be customized any longer.</span></span> <span data-ttu-id="cdafd-163">對該欄位進行的所有變更都會還原為原始值。</span><span class="sxs-lookup"><span data-stu-id="cdafd-163">All the changes made to that field will be reverted to the original values.</span></span>
> - <span data-ttu-id="cdafd-164">變更商標可能需要最多 24 小時，使用者才能看到變更。</span><span class="sxs-lookup"><span data-stu-id="cdafd-164">Changes to branding might require up to 24 hours for the users to see the changes.</span></span>

## <a name="review-app-details"></a><span data-ttu-id="cdafd-165">查看應用程式詳細資料</span><span class="sxs-lookup"><span data-stu-id="cdafd-165">Review app details</span></span>

<span data-ttu-id="cdafd-166">您可能會想要查看應用程式詳細資料，以檢查資訊。</span><span class="sxs-lookup"><span data-stu-id="cdafd-166">You might want to see the app details to review the information.</span></span>

1. <span data-ttu-id="cdafd-167">登入 Teams 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="cdafd-167">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="cdafd-168">展開 [Teams 應用程式 **]**，然後選取 [管理應用程式 **]**。</span><span class="sxs-lookup"><span data-stu-id="cdafd-168">Expand **Teams apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="cdafd-169">選取應用程式名稱。</span><span class="sxs-lookup"><span data-stu-id="cdafd-169">Select the app name.</span></span>

4. <span data-ttu-id="cdafd-170">查看應用程式詳細資料，包括原始應用程式名稱 **Publisher 的簡短名稱**。</span><span class="sxs-lookup"><span data-stu-id="cdafd-170">View the app details, including the original app name **Short name from publisher**.</span></span>

   ![自訂圖示面板應用程式名稱](media/original-app-version.png)

   <span data-ttu-id="cdafd-172">只有 **您變更了** 應用程式的簡短名稱，才能看到來自發行者欄位的簡短名稱。</span><span class="sxs-lookup"><span data-stu-id="cdafd-172">The **Short name from publisher** field is only visible if you've changed the app's short name.</span></span>

## <a name="reset-app-details-to-default"></a><span data-ttu-id="cdafd-173">將應用程式詳細資料重設為預設值</span><span class="sxs-lookup"><span data-stu-id="cdafd-173">Reset app details to default</span></span>

<span data-ttu-id="cdafd-174">您隨時都可以將應用程式詳細資料重設為原始設定。</span><span class="sxs-lookup"><span data-stu-id="cdafd-174">At any time, you can reset the app details to the original settings.</span></span>

1. <span data-ttu-id="cdafd-175">登入 Teams 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="cdafd-175">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="cdafd-176">展開 **Teams應用程式**，然後選取 **管理應用程式**。</span><span class="sxs-lookup"><span data-stu-id="cdafd-176">Expand **Teams Apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="cdafd-177">選取應用程式名稱。</span><span class="sxs-lookup"><span data-stu-id="cdafd-177">Select the app name.</span></span>

4. <span data-ttu-id="cdafd-178">從 **動作下拉下** 拉選取預設值。</span><span class="sxs-lookup"><span data-stu-id="cdafd-178">Select **Reset to default** from the **Actions** dropdown.</span></span>

   ![選取重設以預設為已強調](media/select-reset.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="cdafd-180">常見問題集</span><span class="sxs-lookup"><span data-stu-id="cdafd-180">Frequently asked questions</span></span>

<span data-ttu-id="cdafd-181">**我的使用者需要多久時間查看自訂的應用程式？**</span><span class="sxs-lookup"><span data-stu-id="cdafd-181">**How long will it take for my users to see the customized app?**</span></span>

<span data-ttu-id="cdafd-182">雖然系統管理員可以在系統管理中心Teams變更，但使用者最多可能需要 24 小時才能看到變更。</span><span class="sxs-lookup"><span data-stu-id="cdafd-182">Although the admin can immediately see the changes in Teams Admin Center, it might take up to 24 hours for the end users to see the changes.</span></span>  

<span data-ttu-id="cdafd-183">**應用程式提供者可以為客戶自訂應用程式嗎？**</span><span class="sxs-lookup"><span data-stu-id="cdafd-183">**Can the app provider customize the app for its customers?**</span></span>

 <span data-ttu-id="cdafd-184">否，租使用者系統管理員需要使用系統管理中心自訂租使用者Teams應用程式。</span><span class="sxs-lookup"><span data-stu-id="cdafd-184">No, the admin of a tenant needs to customize the app for their tenant using the Teams Admin Center.</span></span>

<span data-ttu-id="cdafd-185">**自訂的應用程式會自動部署以取代租使用者中的目前自訂應用程式嗎？**</span><span class="sxs-lookup"><span data-stu-id="cdafd-185">**Will the customized app automatically get deployed to replace my current custom app in a tenant?**</span></span>

<span data-ttu-id="cdafd-186">否，租使用者系統管理員必須手動移除任何自訂應用程式，併發布自訂版本的應用程式。</span><span class="sxs-lookup"><span data-stu-id="cdafd-186">No, the tenant admins will have to manually remove any custom app and publish the customized version of the app.</span></span> <span data-ttu-id="cdafd-187">如果您自訂應用程式並將其發佈為自訂應用程式，使用 App 自訂功能自訂的新應用程式無法取代目前的自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="cdafd-187">If you have customized an app and published it as a custom app, the new app customized using the app customization feature won't replace the current custom app.</span></span>  

<span data-ttu-id="cdafd-188">**應用程式使用方式報告也會顯示自訂的值 ，例如自訂的簡短名稱嗎？**</span><span class="sxs-lookup"><span data-stu-id="cdafd-188">**Will the app usage report also show the customized values such as customized short name?**</span></span>

 <span data-ttu-id="cdafd-189">否，應用程式使用方式報告仍然會顯示從發行者寄來的應用程式原始名稱。</span><span class="sxs-lookup"><span data-stu-id="cdafd-189">No, the app usage report will still show the original name of the app sent from the publisher.</span></span>

<span data-ttu-id="cdafd-190">**我可以使用應用程式自訂功能自訂哪些應用程式？**</span><span class="sxs-lookup"><span data-stu-id="cdafd-190">**Which apps can I customize using the app customization feature?**</span></span>

<span data-ttu-id="cdafd-191">您只可以自訂應用程式發行者允許可自訂的應用程式。</span><span class="sxs-lookup"><span data-stu-id="cdafd-191">You can only customize apps that have been allowed to be customizable by the app publisher.</span></span> <span data-ttu-id="cdafd-192">應用程式發行者必須加入宣告，允許其客戶自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="cdafd-192">The app publisher will need to opt in to allow its customers to customize the app.</span></span>

<span data-ttu-id="cdafd-193">**自訂屬性會顯示在圖形許可權同意畫面上嗎？**</span><span class="sxs-lookup"><span data-stu-id="cdafd-193">**Will the customized properties show up on the graph permission consent screen?**</span></span>

<span data-ttu-id="cdafd-194">否，許可權同意畫面仍然會顯示發行者所寄的原始值。</span><span class="sxs-lookup"><span data-stu-id="cdafd-194">No, the permission consent screen will still show the original value sent by the publisher.</span></span>

## <a name="related-article"></a><span data-ttu-id="cdafd-195">相關文章</span><span class="sxs-lookup"><span data-stu-id="cdafd-195">Related article</span></span>

- [<span data-ttu-id="cdafd-196">管理應用程式</span><span class="sxs-lookup"><span data-stu-id="cdafd-196">Manage apps</span></span>](manage-apps.md)
- [<span data-ttu-id="cdafd-197">自訂您的 App Store</span><span class="sxs-lookup"><span data-stu-id="cdafd-197">Customize your app store</span></span>](customize-your-app-store.md)
