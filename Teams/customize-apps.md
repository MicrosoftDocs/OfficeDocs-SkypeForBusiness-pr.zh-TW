---
title: 在 Teams 中自訂 Microsoft 應用程式
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: vaagarw
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
description: 瞭解如何在 Microsoft Teams 中自訂應用程式。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: b2e924da384b5bff54e63872aa7026d2da456311
ms.sourcegitcommit: 88cb2362d07bca88402cf771a6f366c972e26001
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2021
ms.locfileid: "51471497"
---
# <a name="customize-apps-in-microsoft-teams"></a><span data-ttu-id="1f124-103">在 Microsoft Teams 中自訂應用程式</span><span class="sxs-lookup"><span data-stu-id="1f124-103">Customize apps in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

 <span data-ttu-id="1f124-104">Microsoft Teams 提供應用程式自訂功能，以增強 Teams 體驗。</span><span class="sxs-lookup"><span data-stu-id="1f124-104">Microsoft Teams provides app customization to enhance the Teams experience.</span></span> <span data-ttu-id="1f124-105">有些應用程式開發人員允許 Teams 系統管理員自訂應用程式。管理員可以使用 Teams 系統管理中心管理應用程式頁面，根據組織需求自訂或重新建立應用程式 **屬性** 的品牌。</span><span class="sxs-lookup"><span data-stu-id="1f124-105">Some app developers allow an app to be customized by the Teams admin. The admin can customize or rebrand the app properties based on the organizational needs using the Teams admin center **Manage apps** page.</span></span> <span data-ttu-id="1f124-106">您可以自訂的詳細資訊有：</span><span class="sxs-lookup"><span data-stu-id="1f124-106">The details you can customize are:</span></span>

- <span data-ttu-id="1f124-107">簡短名稱</span><span class="sxs-lookup"><span data-stu-id="1f124-107">Short name</span></span>
- <span data-ttu-id="1f124-108">簡短描述</span><span class="sxs-lookup"><span data-stu-id="1f124-108">Short description</span></span>
- <span data-ttu-id="1f124-109">完整描述</span><span class="sxs-lookup"><span data-stu-id="1f124-109">Full description</span></span>
- <span data-ttu-id="1f124-110">隱私權政策 URL</span><span class="sxs-lookup"><span data-stu-id="1f124-110">Privacy policy URL</span></span>
- <span data-ttu-id="1f124-111">網站 URL</span><span class="sxs-lookup"><span data-stu-id="1f124-111">Website URL</span></span>
- <span data-ttu-id="1f124-112">使用條款 URL</span><span class="sxs-lookup"><span data-stu-id="1f124-112">Terms of use URL</span></span>
- <span data-ttu-id="1f124-113">色彩圖示</span><span class="sxs-lookup"><span data-stu-id="1f124-113">Color icon</span></span>
- <span data-ttu-id="1f124-114">大綱圖示</span><span class="sxs-lookup"><span data-stu-id="1f124-114">Outline icon</span></span>
- <span data-ttu-id="1f124-115">強調色彩</span><span class="sxs-lookup"><span data-stu-id="1f124-115">Accent color</span></span>

<span data-ttu-id="1f124-116">請參閱 [Teams 清單架構](https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema) ，瞭解您可以自訂之欄位的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="1f124-116">See the [Teams Manifest schema](https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema) for details about the fields that you can customize.</span></span>

## <a name="customize-the-apps-details"></a><span data-ttu-id="1f124-117">自訂應用程式詳細資料</span><span class="sxs-lookup"><span data-stu-id="1f124-117">Customize the app's details</span></span>

<span data-ttu-id="1f124-118">若要開始自訂應用程式，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="1f124-118">To start customizing an app, complete the following steps:</span></span>

1. <span data-ttu-id="1f124-119">登入 Teams 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="1f124-119">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="1f124-120">展開 **Teams 應用程式** ，然後選取 **管理應用程式**。</span><span class="sxs-lookup"><span data-stu-id="1f124-120">Expand **Teams Apps** and select **Manage apps**.</span></span>
3. <span data-ttu-id="1f124-121">檢查應用程式 **清單** 的可自訂欄，並按可自訂的應用程式排序。</span><span class="sxs-lookup"><span data-stu-id="1f124-121">Check the **Customizable** column of the apps list and sort by apps that are customizable.</span></span>

   ![已排序的自訂欄](media/customize-column.png)

   <span data-ttu-id="1f124-123">有三個進入點可存取自訂功能：</span><span class="sxs-lookup"><span data-stu-id="1f124-123">There are three entry points to access the customize feature:</span></span>

   - <span data-ttu-id="1f124-124">選取要自訂之應用程式旁的 ， **然後選取** 自訂 。</span><span class="sxs-lookup"><span data-stu-id="1f124-124">Select next to the app that you want to customize, and then select **Customize**.</span></span>

     ![自訂選取選項 1](media/select-app-to-customize1.png)

   - <span data-ttu-id="1f124-126">選取應用程式名稱，然後選取可 **自訂**。</span><span class="sxs-lookup"><span data-stu-id="1f124-126">Select the app name and then **Customizable**.</span></span>

     ![自訂選取選項 2](media/app-details-customizable.png)

   - <span data-ttu-id="1f124-128">選取應用程式名稱， **然後從動作** 下拉下拉選取 **自訂** 。</span><span class="sxs-lookup"><span data-stu-id="1f124-128">Select the app name, and then select **Customize** from the **Actions** dropdown.</span></span>

     ![自訂選取選項 3](media/customize-action-menu.png)

4. <span data-ttu-id="1f124-130">展開詳細 **資料** 區段並自訂下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="1f124-130">Expand the **Details** section and customize the following fields:</span></span>

    - <span data-ttu-id="1f124-131">簡短名稱</span><span class="sxs-lookup"><span data-stu-id="1f124-131">Short name</span></span>
    - <span data-ttu-id="1f124-132">簡短描述</span><span class="sxs-lookup"><span data-stu-id="1f124-132">Short description</span></span>
    - <span data-ttu-id="1f124-133">完整描述</span><span class="sxs-lookup"><span data-stu-id="1f124-133">Full description</span></span>
    - <span data-ttu-id="1f124-134">網站</span><span class="sxs-lookup"><span data-stu-id="1f124-134">Website</span></span>
    - <span data-ttu-id="1f124-135">隱私權政策 URL</span><span class="sxs-lookup"><span data-stu-id="1f124-135">Privacy policy URL</span></span>
    - <span data-ttu-id="1f124-136">使用條款 URL</span><span class="sxs-lookup"><span data-stu-id="1f124-136">Terms of use URL</span></span>

   ![自訂設定](media/customize-settings.png)

> [!Note]
> <span data-ttu-id="1f124-138">只會顯示 App 開發人員指派為可自訂的欄位。</span><span class="sxs-lookup"><span data-stu-id="1f124-138">Only the fields that the app developer has assigned as customizable will be visible.</span></span>

5. <span data-ttu-id="1f124-139">展開圖示 **區** 段。</span><span class="sxs-lookup"><span data-stu-id="1f124-139">Expand the **Icon** section.</span></span>

   <span data-ttu-id="1f124-140">a.</span><span class="sxs-lookup"><span data-stu-id="1f124-140">a.</span></span> <span data-ttu-id="1f124-141">上傳圖示。</span><span class="sxs-lookup"><span data-stu-id="1f124-141">Upload an icon.</span></span> <span data-ttu-id="1f124-142">在 PNG 格式的 192x192 (圖元) 全色圖示。</span><span class="sxs-lookup"><span data-stu-id="1f124-142">Use one full-color icon (192x192) pixel in PNG format.</span></span>

   <span data-ttu-id="1f124-143">b.</span><span class="sxs-lookup"><span data-stu-id="1f124-143">b.</span></span> <span data-ttu-id="1f124-144">選擇圖示外邊框色彩。</span><span class="sxs-lookup"><span data-stu-id="1f124-144">Choose an icon outline color.</span></span> <span data-ttu-id="1f124-145">使用一個 32x32 (32x32) PNG 格式的透明外邊框。</span><span class="sxs-lookup"><span data-stu-id="1f124-145">Use one transparent outline (32x32) pixel in PNG format.</span></span>

   <span data-ttu-id="1f124-146">C。</span><span class="sxs-lookup"><span data-stu-id="1f124-146">c.</span></span> <span data-ttu-id="1f124-147">選取符合圖示的應用程式強調色彩。</span><span class="sxs-lookup"><span data-stu-id="1f124-147">Select an app accent color that matches the icon.</span></span>

    ![自訂圖示面板色彩選項](media/customize-app-colors.png)

6. <span data-ttu-id="1f124-149">自訂應用程式之後，請選取 **Apply**。</span><span class="sxs-lookup"><span data-stu-id="1f124-149">Once your app has been customized, select **Apply**.</span></span>

7. <span data-ttu-id="1f124-150">選取 **發佈** 以發佈自訂的應用程式。</span><span class="sxs-lookup"><span data-stu-id="1f124-150">Select **Publish** to publish the customized app.</span></span>

   <span data-ttu-id="1f124-151">自訂的應用程式現在會列在您的管理 **應用程式頁面中** 。</span><span class="sxs-lookup"><span data-stu-id="1f124-151">The customized app is now listed in your **Manage apps** page.</span></span> <span data-ttu-id="1f124-152">由於自訂應用程式功能不會建立應用程式的副本，因此您只會擁有一個版本的應用程式。</span><span class="sxs-lookup"><span data-stu-id="1f124-152">You'll have only one version of the app, since customizing the app features doesn't create a copy of the app.</span></span>

<span data-ttu-id="1f124-153">現在您的 Teams 使用者可以開啟 Teams 用戶端來查看自訂的應用程式。</span><span class="sxs-lookup"><span data-stu-id="1f124-153">Now your Teams end users can open their Teams client to see the customized app.</span></span>

   ![Teams 用戶端中的自訂應用程式](media/find-customized-app.png)

### <a name="special-considerations-for-customizing-an-app"></a><span data-ttu-id="1f124-155">自訂應用程式的特殊考慮</span><span class="sxs-lookup"><span data-stu-id="1f124-155">Special considerations for customizing an app</span></span>

<span data-ttu-id="1f124-156">下列附注包含自訂應用程式的重要詳細資料。</span><span class="sxs-lookup"><span data-stu-id="1f124-156">The following note includes important details about customizing an app.</span></span>

> [!Note]
> - <span data-ttu-id="1f124-157">當您自訂 App 和任何與應用程式相關的描述時，請確保您遵循應用程式發行者提供的自訂指導方針。</span><span class="sxs-lookup"><span data-stu-id="1f124-157">When you customize apps and any description related to an app, ensure that you follow the Customization Guidelines provided by the app publisher.</span></span> <span data-ttu-id="1f124-158">您有責任尊重其他人對於您可能使用之協力廠商影像的權利。</span><span class="sxs-lookup"><span data-stu-id="1f124-158">You're responsible for respecting the rights of others regarding third-party images you might use.</span></span>
> - <span data-ttu-id="1f124-159">系統管理提供的自訂資料會儲存在最近的地區的 Settings Store 中。</span><span class="sxs-lookup"><span data-stu-id="1f124-159">Admin-provided customization data is stored in the Settings Store in the nearest region.</span></span> <span data-ttu-id="1f124-160">它並不一定在任何 GoLocal Cloud Teams 部署中。</span><span class="sxs-lookup"><span data-stu-id="1f124-160">It isn't necessarily in any GoLocal Cloud Teams deployment.</span></span>
> - <span data-ttu-id="1f124-161">您負責確保使用條款或隱私權政策的連結有效。</span><span class="sxs-lookup"><span data-stu-id="1f124-161">You're responsible for ensuring that the links to the terms of use or privacy policy are valid.</span></span> <span data-ttu-id="1f124-162">您必須提供適當的管理，以管理他們 (或允許對應用程式中繼資料) 進行變更。</span><span class="sxs-lookup"><span data-stu-id="1f124-162">You must provide appropriate management of the changes they make (or allow to be made) to app metadata.</span></span> <span data-ttu-id="1f124-163">目前的實現會提供支援，可協助您將 URL 還原為開發人員提供的 URL。</span><span class="sxs-lookup"><span data-stu-id="1f124-163">Current implementation will provide support to help you to revert to developer-provided URLs.</span></span> <span data-ttu-id="1f124-164">如果應用程式允許自訂 URL 或 (，您不得設定沒有 URL) 。</span><span class="sxs-lookup"><span data-stu-id="1f124-164">You may not configure the app without a URL (if the app allows customization of the URLs).</span></span>
> - <span data-ttu-id="1f124-165">如果應用程式發行者不再允許欄位可自訂，應用程式詳細資料頁面上會出現一則訊息，通知系統管理員無法再自訂的欄位。</span><span class="sxs-lookup"><span data-stu-id="1f124-165">In case the app publisher no longer allows a field to be customizable, a message appears on the app details page notifying the admin about the fields that can't be customized any longer.</span></span> <span data-ttu-id="1f124-166">對該欄位進行的所有變更都會還原為原始值。</span><span class="sxs-lookup"><span data-stu-id="1f124-166">All the changes made to that field will be reverted to the original values.</span></span>
> - <span data-ttu-id="1f124-167">品牌變更最多可能需要 24 小時，使用者才能看到變更。</span><span class="sxs-lookup"><span data-stu-id="1f124-167">Changes to branding might require up to 24 hours for the users to see the changes.</span></span>

## <a name="review-app-details"></a><span data-ttu-id="1f124-168">查看應用程式詳細資料</span><span class="sxs-lookup"><span data-stu-id="1f124-168">Review app details</span></span>

<span data-ttu-id="1f124-169">您可能會想要查看應用程式詳細資料，以檢查資訊。</span><span class="sxs-lookup"><span data-stu-id="1f124-169">You might want to see the app details to review the information.</span></span>

1. <span data-ttu-id="1f124-170">登入 Teams 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="1f124-170">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="1f124-171">展開 [Teams 應用程式 **]**，然後選取 [管理應用程式 **]**。</span><span class="sxs-lookup"><span data-stu-id="1f124-171">Expand **Teams apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="1f124-172">選取應用程式名稱。</span><span class="sxs-lookup"><span data-stu-id="1f124-172">Select the app name.</span></span>

4. <span data-ttu-id="1f124-173">查看應用程式詳細資料，包括原始應用程式名稱 **Publisher 的簡短名稱**。</span><span class="sxs-lookup"><span data-stu-id="1f124-173">View the app details, including the original app name **Short name from publisher**.</span></span>

   ![自訂圖示面板應用程式名稱](media/app-details-original-name.png)

   <span data-ttu-id="1f124-175">只有 **您變更了** 應用程式的簡短名稱，才能看到來自發行者欄位的簡短名稱。</span><span class="sxs-lookup"><span data-stu-id="1f124-175">The **Short name from publisher** field is only visible if you've changed the app's short name.</span></span>

## <a name="reset-app-details-to-default"></a><span data-ttu-id="1f124-176">將應用程式詳細資料重設為預設值</span><span class="sxs-lookup"><span data-stu-id="1f124-176">Reset app details to default</span></span>

<span data-ttu-id="1f124-177">您隨時都可以將應用程式詳細資料重設為原始設定。</span><span class="sxs-lookup"><span data-stu-id="1f124-177">At any time, you can reset the app details to the original settings.</span></span>

1. <span data-ttu-id="1f124-178">登入 Teams 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="1f124-178">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="1f124-179">展開 **Teams 應用程式** ，然後選取 **管理應用程式**。</span><span class="sxs-lookup"><span data-stu-id="1f124-179">Expand **Teams Apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="1f124-180">選取應用程式名稱。</span><span class="sxs-lookup"><span data-stu-id="1f124-180">Select the app name.</span></span>

4. <span data-ttu-id="1f124-181">從 **動作下拉下** 拉選取預設值。</span><span class="sxs-lookup"><span data-stu-id="1f124-181">Select **Reset to default** from the **Actions** dropdown.</span></span>

   ![選取重設以預設為已強調](media/select-reset.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="1f124-183">常見問題集</span><span class="sxs-lookup"><span data-stu-id="1f124-183">Frequently asked questions</span></span>

<span data-ttu-id="1f124-184">**我的使用者需要多久時間查看自訂的應用程式？**</span><span class="sxs-lookup"><span data-stu-id="1f124-184">**How long will it take for my users to see the customized app?**</span></span>

<span data-ttu-id="1f124-185">雖然系統管理員可以立即在 Teams 系統管理中心看到變更，但使用者最多可能需要 24 小時才能看到變更。</span><span class="sxs-lookup"><span data-stu-id="1f124-185">Although the admin can immediately see the changes in Teams Admin Center, it might take up to 24 hours for the end users to see the changes.</span></span>  

<span data-ttu-id="1f124-186">**應用程式提供者可以為客戶自訂應用程式嗎？**</span><span class="sxs-lookup"><span data-stu-id="1f124-186">**Can the app provider customize the app for its customers?**</span></span>

 <span data-ttu-id="1f124-187">否，租使用者系統管理員需要使用 Teams 系統管理中心自訂其租使用者的應用程式。</span><span class="sxs-lookup"><span data-stu-id="1f124-187">No, the admin of a tenant needs to customize the app for their tenant using the Teams Admin Center.</span></span>

<span data-ttu-id="1f124-188">**自訂的應用程式會自動部署以取代租使用者中的目前自訂應用程式嗎？**</span><span class="sxs-lookup"><span data-stu-id="1f124-188">**Will the customized app automatically get deployed to replace my current custom app in a tenant?**</span></span>

<span data-ttu-id="1f124-189">否，租使用者系統管理員必須手動移除任何自訂應用程式，併發布自訂版本的應用程式。</span><span class="sxs-lookup"><span data-stu-id="1f124-189">No, the tenant admins will have to manually remove any custom app and publish the customized version of the app.</span></span> <span data-ttu-id="1f124-190">如果您自訂應用程式並將其發佈為自訂應用程式，使用 App 自訂功能自訂的新應用程式無法取代目前的自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="1f124-190">If you have customized an app and published it as a custom app, the new app customized using the app customization feature won't replace the current custom app.</span></span>  

<span data-ttu-id="1f124-191">**應用程式使用方式報告也會顯示自訂的值 ，例如自訂的簡短名稱嗎？**</span><span class="sxs-lookup"><span data-stu-id="1f124-191">**Will the app usage report also show the customized values such as customized short name?**</span></span>

 <span data-ttu-id="1f124-192">否，應用程式使用方式報告仍然會顯示從發行者寄來的應用程式原始名稱。</span><span class="sxs-lookup"><span data-stu-id="1f124-192">No, the app usage report will still show the original name of the app sent from the publisher.</span></span>

<span data-ttu-id="1f124-193">**我可以使用應用程式自訂功能自訂哪些應用程式？**</span><span class="sxs-lookup"><span data-stu-id="1f124-193">**Which apps can I customize using the app customization feature?**</span></span>

<span data-ttu-id="1f124-194">您只可以自訂應用程式發行者允許可自訂的應用程式。</span><span class="sxs-lookup"><span data-stu-id="1f124-194">You can only customize apps that have been allowed to be customizable by the app publisher.</span></span> <span data-ttu-id="1f124-195">應用程式發行者必須加入宣告，允許其客戶自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="1f124-195">The app publisher will need to opt in to allow its customers to customize the app.</span></span>

<span data-ttu-id="1f124-196">**自訂屬性會顯示在圖形許可權同意畫面上嗎？**</span><span class="sxs-lookup"><span data-stu-id="1f124-196">**Will the customized properties show up on the graph permission consent screen?**</span></span>

<span data-ttu-id="1f124-197">否，許可權同意畫面仍然會顯示發行者所寄的原始值。</span><span class="sxs-lookup"><span data-stu-id="1f124-197">No, the permission consent screen will still show the original value sent by the publisher.</span></span>

## <a name="related-article"></a><span data-ttu-id="1f124-198">相關文章</span><span class="sxs-lookup"><span data-stu-id="1f124-198">Related article</span></span>

- [<span data-ttu-id="1f124-199">管理應用程式</span><span class="sxs-lookup"><span data-stu-id="1f124-199">Manage apps</span></span>](manage-apps.md)
- [<span data-ttu-id="1f124-200">自訂您的 App Store</span><span class="sxs-lookup"><span data-stu-id="1f124-200">Customize your app store</span></span>](customize-your-app-store.md)
