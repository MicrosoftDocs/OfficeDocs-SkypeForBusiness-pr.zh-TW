---
title: 自訂應用程式Microsoft Teams
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
ms.openlocfilehash: dbf92ec3899599f732f2898f042f51f30f91f15b
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684590"
---
# <a name="customize-apps-in-microsoft-teams"></a><span data-ttu-id="71397-103">自訂應用程式Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="71397-103">Customize apps in Microsoft Teams</span></span>

 <span data-ttu-id="71397-104">Microsoft Teams應用程式自訂功能，以增強Teams體驗。</span><span class="sxs-lookup"><span data-stu-id="71397-104">Microsoft Teams provides app customization to enhance the Teams experience.</span></span> <span data-ttu-id="71397-105">有些應用程式開發人員允許系統管理員自訂Teams應用程式。管理員可以使用系統管理中心管理應用程式頁面，根據組織需求自訂或重新Teams **應用程式** 屬性。</span><span class="sxs-lookup"><span data-stu-id="71397-105">Some app developers allow an app to be customized by the Teams admin. The admin can customize or rebrand the app properties based on the organizational needs using the Teams admin center **Manage apps** page.</span></span> <span data-ttu-id="71397-106">您可以自訂的詳細資訊有：</span><span class="sxs-lookup"><span data-stu-id="71397-106">The details you can customize are:</span></span>

- <span data-ttu-id="71397-107">簡短名稱</span><span class="sxs-lookup"><span data-stu-id="71397-107">Short name</span></span>
- <span data-ttu-id="71397-108">簡短描述</span><span class="sxs-lookup"><span data-stu-id="71397-108">Short description</span></span>
- <span data-ttu-id="71397-109">完整描述</span><span class="sxs-lookup"><span data-stu-id="71397-109">Full description</span></span>
- <span data-ttu-id="71397-110">隱私權政策 URL</span><span class="sxs-lookup"><span data-stu-id="71397-110">Privacy policy URL</span></span>
- <span data-ttu-id="71397-111">網站 URL</span><span class="sxs-lookup"><span data-stu-id="71397-111">Website URL</span></span>
- <span data-ttu-id="71397-112">使用條款 URL</span><span class="sxs-lookup"><span data-stu-id="71397-112">Terms of use URL</span></span>
- <span data-ttu-id="71397-113">色彩圖示</span><span class="sxs-lookup"><span data-stu-id="71397-113">Color icon</span></span>
- <span data-ttu-id="71397-114">大綱圖示</span><span class="sxs-lookup"><span data-stu-id="71397-114">Outline icon</span></span>
- <span data-ttu-id="71397-115">強調色彩</span><span class="sxs-lookup"><span data-stu-id="71397-115">Accent color</span></span>

<span data-ttu-id="71397-116">請參閱Teams清單[架構](/microsoftteams/platform/resources/schema/manifest-schema)，以瞭解有關您可以自訂之欄位的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="71397-116">See the [Teams Manifest schema](/microsoftteams/platform/resources/schema/manifest-schema) for details about the fields that you can customize.</span></span>

> [!NOTE]
> <span data-ttu-id="71397-117">目前不支援在 政府社群雲端 (GCCH) 或 (DoD) 自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="71397-117">Customizing apps isn't supported in Government Community Cloud High (GCCH) or Department of Defense (DoD) at this time.</span></span>

## <a name="customize-the-apps-details"></a><span data-ttu-id="71397-118">自訂應用程式詳細資料</span><span class="sxs-lookup"><span data-stu-id="71397-118">Customize the app's details</span></span>

<span data-ttu-id="71397-119">若要開始自訂應用程式，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="71397-119">To start customizing an app, complete the following steps:</span></span>

1. <span data-ttu-id="71397-120">登入 Teams 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="71397-120">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="71397-121">展開 **Teams 應用程式**，然後選取 **管理應用程式**。</span><span class="sxs-lookup"><span data-stu-id="71397-121">Expand **Teams Apps** and select **Manage apps**.</span></span>
3. <span data-ttu-id="71397-122">檢查應用程式 **清單** 的可自訂欄，並按可自訂的應用程式排序。</span><span class="sxs-lookup"><span data-stu-id="71397-122">Check the **Customizable** column of the apps list and sort by apps that are customizable.</span></span>

   ![已排序的自訂欄](media/customize-column.png)

   <span data-ttu-id="71397-124">有三個進入點可存取自訂功能：</span><span class="sxs-lookup"><span data-stu-id="71397-124">There are three entry points to access the customize feature:</span></span>

   - <span data-ttu-id="71397-125">選取您想要自訂的應用程式旁，然後選取 **自訂**。</span><span class="sxs-lookup"><span data-stu-id="71397-125">Select next to the app that you want to customize, and then select **Customize**.</span></span>

     ![自訂選取選項 1](media/select-app-to-customize1.png)

   - <span data-ttu-id="71397-127">選取應用程式名稱，然後選取可 **自訂**。</span><span class="sxs-lookup"><span data-stu-id="71397-127">Select the app name and then **Customizable**.</span></span>

     ![自訂選取選項 2](media/app-details-customizable.png)

   - <span data-ttu-id="71397-129">選取應用程式名稱， **然後從動作** 下拉下拉選取 **自訂** 。</span><span class="sxs-lookup"><span data-stu-id="71397-129">Select the app name, and then select **Customize** from the **Actions** dropdown.</span></span>

     ![自訂選取選項 3](media/customize-action-menu.png)

4. <span data-ttu-id="71397-131">展開詳細 **資料** 區段並自訂下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="71397-131">Expand the **Details** section and customize the following fields:</span></span>

    - <span data-ttu-id="71397-132">簡短名稱</span><span class="sxs-lookup"><span data-stu-id="71397-132">Short name</span></span>
    - <span data-ttu-id="71397-133">簡短描述</span><span class="sxs-lookup"><span data-stu-id="71397-133">Short description</span></span>
    - <span data-ttu-id="71397-134">完整描述</span><span class="sxs-lookup"><span data-stu-id="71397-134">Full description</span></span>
    - <span data-ttu-id="71397-135">網站</span><span class="sxs-lookup"><span data-stu-id="71397-135">Website</span></span>
    - <span data-ttu-id="71397-136">隱私權政策 URL</span><span class="sxs-lookup"><span data-stu-id="71397-136">Privacy policy URL</span></span>
    - <span data-ttu-id="71397-137">使用條款 URL</span><span class="sxs-lookup"><span data-stu-id="71397-137">Terms of use URL</span></span>

   ![自訂設定](media/customize-settings.png)

> [!Note]
> <span data-ttu-id="71397-139">只有應用程式開發人員已指派為可自訂的欄位才能顯示。</span><span class="sxs-lookup"><span data-stu-id="71397-139">Only the fields that the app developer has assigned as customizable will be visible.</span></span>

5. <span data-ttu-id="71397-140">展開圖示 **區** 段。</span><span class="sxs-lookup"><span data-stu-id="71397-140">Expand the **Icon** section.</span></span>

   <span data-ttu-id="71397-141">a.</span><span class="sxs-lookup"><span data-stu-id="71397-141">a.</span></span> <span data-ttu-id="71397-142">Upload圖示。</span><span class="sxs-lookup"><span data-stu-id="71397-142">Upload an icon.</span></span> <span data-ttu-id="71397-143">在 PNG 格式的 192x192 (圖元) 全色圖示。</span><span class="sxs-lookup"><span data-stu-id="71397-143">Use one full-color icon (192x192) pixel in PNG format.</span></span>

   <span data-ttu-id="71397-144">b.</span><span class="sxs-lookup"><span data-stu-id="71397-144">b.</span></span> <span data-ttu-id="71397-145">選擇圖示外邊框色彩。</span><span class="sxs-lookup"><span data-stu-id="71397-145">Choose an icon outline color.</span></span> <span data-ttu-id="71397-146">使用一個 32x32 (32x32) PNG 格式的透明外邊框。</span><span class="sxs-lookup"><span data-stu-id="71397-146">Use one transparent outline (32x32) pixel in PNG format.</span></span>

   <span data-ttu-id="71397-147">C。</span><span class="sxs-lookup"><span data-stu-id="71397-147">c.</span></span> <span data-ttu-id="71397-148">選取符合圖示的應用程式強調色彩。</span><span class="sxs-lookup"><span data-stu-id="71397-148">Select an app accent color that matches the icon.</span></span>

    ![自訂圖示面板色彩選項](media/customize-app-colors.png)

6. <span data-ttu-id="71397-150">自訂應用程式之後，請選取 **Apply**。</span><span class="sxs-lookup"><span data-stu-id="71397-150">Once your app has been customized, select **Apply**.</span></span>

7. <span data-ttu-id="71397-151">選取 **發佈** 以發佈自訂的應用程式。</span><span class="sxs-lookup"><span data-stu-id="71397-151">Select **Publish** to publish the customized app.</span></span>

   <span data-ttu-id="71397-152">自訂的應用程式現在會列在您的管理 **應用程式頁面中** 。</span><span class="sxs-lookup"><span data-stu-id="71397-152">The customized app is now listed in your **Manage apps** page.</span></span> <span data-ttu-id="71397-153">由於自訂應用程式功能不會建立應用程式的副本，因此您只會擁有一個版本的應用程式。</span><span class="sxs-lookup"><span data-stu-id="71397-153">You'll have only one version of the app, since customizing the app features doesn't create a copy of the app.</span></span>

<span data-ttu-id="71397-154">現在您的Teams使用者可以開啟其Teams用戶端以查看自訂的應用程式。</span><span class="sxs-lookup"><span data-stu-id="71397-154">Now your Teams end users can open their Teams client to see the customized app.</span></span>

   ![用戶端中的自訂Teams應用程式](media/contoso-app.png)

### <a name="special-considerations-for-customizing-an-app"></a><span data-ttu-id="71397-156">自訂應用程式的特殊考慮</span><span class="sxs-lookup"><span data-stu-id="71397-156">Special considerations for customizing an app</span></span>

<span data-ttu-id="71397-157">下列附注包含自訂應用程式的重要詳細資料。</span><span class="sxs-lookup"><span data-stu-id="71397-157">The following note includes important details about customizing an app.</span></span>

> [!Note]
> - <span data-ttu-id="71397-158">當您自訂應用程式，以及任何與應用程式相關的描述時，請確保遵循應用程式發行者在檔或使用條款中提供的任何自訂指導方針。</span><span class="sxs-lookup"><span data-stu-id="71397-158">When you customize apps, and any description related to an app, ensure that you follow any customization guidelines if provided by the app publisher in their documentation or terms of use.</span></span> <span data-ttu-id="71397-159">您也有責任尊重其他人對於您可能使用之任何協力廠商影像的權利。</span><span class="sxs-lookup"><span data-stu-id="71397-159">You're also responsible for respecting the rights of others regarding any third-party images you might use.</span></span>
> - <span data-ttu-id="71397-160">系統管理提供的自訂資料會儲存在最近的地區。</span><span class="sxs-lookup"><span data-stu-id="71397-160">Admin-provided customization data is stored in the nearest region.</span></span>
> - <span data-ttu-id="71397-161">您負責確保使用條款或隱私權政策的連結有效。</span><span class="sxs-lookup"><span data-stu-id="71397-161">You are responsible for ensuring that links to terms of use or privacy policy are valid.</span></span>
> - <span data-ttu-id="71397-162">如果應用程式發行者不再允許欄位可自訂，應用程式詳細資料頁面上會出現一則訊息，通知系統管理員無法再自訂的欄位。</span><span class="sxs-lookup"><span data-stu-id="71397-162">In case the app publisher no longer allows a field to be customizable, a message appears on the app details page notifying the admin about the fields that can't be customized any longer.</span></span> <span data-ttu-id="71397-163">對該欄位進行的所有變更都會還原為原始值。</span><span class="sxs-lookup"><span data-stu-id="71397-163">All the changes made to that field will be reverted to the original values.</span></span>
> - <span data-ttu-id="71397-164">品牌變更最多可能需要 24 小時，使用者才能看到變更。</span><span class="sxs-lookup"><span data-stu-id="71397-164">Changes to branding might require up to 24 hours for the users to see the changes.</span></span>

## <a name="review-app-details"></a><span data-ttu-id="71397-165">查看應用程式詳細資料</span><span class="sxs-lookup"><span data-stu-id="71397-165">Review app details</span></span>

<span data-ttu-id="71397-166">您可能會想要查看應用程式詳細資料，以檢查資訊。</span><span class="sxs-lookup"><span data-stu-id="71397-166">You might want to see the app details to review the information.</span></span>

1. <span data-ttu-id="71397-167">登入 Teams 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="71397-167">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="71397-168">展開 [Teams 應用程式 **]**，然後選取 [管理應用程式 **]**。</span><span class="sxs-lookup"><span data-stu-id="71397-168">Expand **Teams apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="71397-169">選取應用程式名稱。</span><span class="sxs-lookup"><span data-stu-id="71397-169">Select the app name.</span></span>

4. <span data-ttu-id="71397-170">查看應用程式詳細資料，包括原始應用程式名稱 **Publisher 的簡短名稱**。</span><span class="sxs-lookup"><span data-stu-id="71397-170">View the app details, including the original app name **Short name from publisher**.</span></span>

   ![自訂圖示面板應用程式名稱](media/original-app-version.png)

   <span data-ttu-id="71397-172">只有 **您變更了** 應用程式的簡短名稱，才能看到來自發行者欄位的簡短名稱。</span><span class="sxs-lookup"><span data-stu-id="71397-172">The **Short name from publisher** field is only visible if you've changed the app's short name.</span></span>

## <a name="reset-app-details-to-default"></a><span data-ttu-id="71397-173">將應用程式詳細資料重設為預設值</span><span class="sxs-lookup"><span data-stu-id="71397-173">Reset app details to default</span></span>

<span data-ttu-id="71397-174">您隨時都可以將應用程式詳細資料重設為原始設定。</span><span class="sxs-lookup"><span data-stu-id="71397-174">At any time, you can reset the app details to the original settings.</span></span>

1. <span data-ttu-id="71397-175">登入 Teams 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="71397-175">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="71397-176">展開 **Teams 應用程式**，然後選取 **管理應用程式**。</span><span class="sxs-lookup"><span data-stu-id="71397-176">Expand **Teams Apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="71397-177">選取應用程式名稱。</span><span class="sxs-lookup"><span data-stu-id="71397-177">Select the app name.</span></span>

4. <span data-ttu-id="71397-178">從 **動作下拉下** 拉選取預設值。</span><span class="sxs-lookup"><span data-stu-id="71397-178">Select **Reset to default** from the **Actions** dropdown.</span></span>

   ![選取重設以預設為已強調](media/select-reset.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="71397-180">常見問題集</span><span class="sxs-lookup"><span data-stu-id="71397-180">Frequently asked questions</span></span>

<span data-ttu-id="71397-181">**我的使用者需要多久時間查看自訂的應用程式？**</span><span class="sxs-lookup"><span data-stu-id="71397-181">**How long will it take for my users to see the customized app?**</span></span>

<span data-ttu-id="71397-182">雖然系統管理員可以在系統管理中心Teams變更，但使用者最多可能需要 24 小時才能看到變更。</span><span class="sxs-lookup"><span data-stu-id="71397-182">Although the admin can immediately see the changes in Teams Admin Center, it might take up to 24 hours for the end users to see the changes.</span></span>  

<span data-ttu-id="71397-183">**應用程式提供者可以為客戶自訂應用程式嗎？**</span><span class="sxs-lookup"><span data-stu-id="71397-183">**Can the app provider customize the app for its customers?**</span></span>

 <span data-ttu-id="71397-184">否，租使用者系統管理員需要使用系統管理中心自訂租使用者Teams應用程式。</span><span class="sxs-lookup"><span data-stu-id="71397-184">No, the admin of a tenant needs to customize the app for their tenant using the Teams Admin Center.</span></span>

<span data-ttu-id="71397-185">**自訂的應用程式會自動部署以取代租使用者中的目前自訂應用程式嗎？**</span><span class="sxs-lookup"><span data-stu-id="71397-185">**Will the customized app automatically get deployed to replace my current custom app in a tenant?**</span></span>

<span data-ttu-id="71397-186">否，租使用者系統管理員必須手動移除任何自訂應用程式，併發布自訂版本的應用程式。</span><span class="sxs-lookup"><span data-stu-id="71397-186">No, the tenant admins will have to manually remove any custom app and publish the customized version of the app.</span></span> <span data-ttu-id="71397-187">如果您自訂應用程式並將其發佈為自訂應用程式，使用 App 自訂功能自訂的新應用程式無法取代目前的自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="71397-187">If you have customized an app and published it as a custom app, the new app customized using the app customization feature won't replace the current custom app.</span></span>  

<span data-ttu-id="71397-188">**應用程式使用方式報告也會顯示自訂的值 ，例如自訂的簡短名稱嗎？**</span><span class="sxs-lookup"><span data-stu-id="71397-188">**Will the app usage report also show the customized values such as customized short name?**</span></span>

 <span data-ttu-id="71397-189">否，應用程式使用方式報告仍然會顯示從發行者寄來的應用程式原始名稱。</span><span class="sxs-lookup"><span data-stu-id="71397-189">No, the app usage report will still show the original name of the app sent from the publisher.</span></span>

<span data-ttu-id="71397-190">**我可以使用應用程式自訂功能自訂哪些應用程式？**</span><span class="sxs-lookup"><span data-stu-id="71397-190">**Which apps can I customize using the app customization feature?**</span></span>

<span data-ttu-id="71397-191">您只可以自訂應用程式發行者允許可自訂的應用程式。</span><span class="sxs-lookup"><span data-stu-id="71397-191">You can only customize apps that have been allowed to be customizable by the app publisher.</span></span> <span data-ttu-id="71397-192">應用程式發行者必須加入宣告，允許其客戶自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="71397-192">The app publisher will need to opt in to allow its customers to customize the app.</span></span>

<span data-ttu-id="71397-193">**自訂屬性會顯示在圖形許可權同意畫面上嗎？**</span><span class="sxs-lookup"><span data-stu-id="71397-193">**Will the customized properties show up on the graph permission consent screen?**</span></span>

<span data-ttu-id="71397-194">否，許可權同意畫面仍然會顯示發行者所寄的原始值。</span><span class="sxs-lookup"><span data-stu-id="71397-194">No, the permission consent screen will still show the original value sent by the publisher.</span></span>

## <a name="related-article"></a><span data-ttu-id="71397-195">相關文章</span><span class="sxs-lookup"><span data-stu-id="71397-195">Related article</span></span>

- [<span data-ttu-id="71397-196">管理應用程式</span><span class="sxs-lookup"><span data-stu-id="71397-196">Manage apps</span></span>](manage-apps.md)
- [<span data-ttu-id="71397-197">自訂您的 App Store</span><span class="sxs-lookup"><span data-stu-id="71397-197">Customize your app store</span></span>](customize-your-app-store.md)
- [<span data-ttu-id="71397-198">重新品牌您的應用程式</span><span class="sxs-lookup"><span data-stu-id="71397-198">Rebrand your apps</span></span>](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/rebrand-apps-to-your-own-organization-s-branding-with-app/ba-p/2376296)
