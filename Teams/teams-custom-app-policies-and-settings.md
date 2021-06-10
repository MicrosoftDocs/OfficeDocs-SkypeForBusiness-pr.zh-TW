---
title: 管理自訂應用程式策略和設定
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: akino
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
description: 瞭解如何管理自訂應用程式策略和設定，以控制組織中誰可以在 Microsoft Teams 中上傳自訂Microsoft Teams。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- seo-marvel-mar2020
ms.openlocfilehash: e89a7aa3a2d016551695406551068cd07a2042e6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119212"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a><span data-ttu-id="5e194-103">在應用程式中管理自訂應用程式Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5e194-103">Manage custom app policies and settings in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="5e194-104">若要使用 App Studio，請參閱在 Microsoft Teams 平臺上開始使用[C#/.NET](/microsoftteams/platform/get-started/get-started-dotnet-app-studio)和 App Studio 的最後一個步驟尚未執行，因此您必須在 Upload 應用程式套件中以舊方式將 zip 下載並安裝至[Microsoft Teams。](/microsoftteams/platform/concepts/apps/apps-upload)</span><span class="sxs-lookup"><span data-stu-id="5e194-104">To use App Studio see [Get started on the Microsoft Teams platform with C#/.NET and App Studio](/microsoftteams/platform/get-started/get-started-dotnet-app-studio) The last step is not working yet, so you will need to download the zip and install it the old way at [Upload an app package to Microsoft Teams](/microsoftteams/platform/concepts/apps/apps-upload).</span></span>

<span data-ttu-id="5e194-105">做為系統管理員，您可以使用自訂應用程式策略和設定來控制組織中誰可以上傳自訂應用程式Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="5e194-105">As an admin, you can use custom app policies and settings to control who in your organization can upload custom apps to Microsoft Teams.</span></span> <span data-ttu-id="5e194-106">系統管理員會決定哪些使用者可以上傳自訂應用程式，而系統管理員和團隊擁有者可以判斷貴組織的特定團隊是否允許將自訂應用程式新加入他們。</span><span class="sxs-lookup"><span data-stu-id="5e194-106">Admins decide which users can upload custom apps, and admins and team owners can determine whether specific teams in your organization allow custom apps to be added to them.</span></span>  <span data-ttu-id="5e194-107">編輯自訂應用程式政策之後，可能需要幾個小時，變更才能生效。</span><span class="sxs-lookup"><span data-stu-id="5e194-107">After you edit the custom app policy, it can take a few hours for changes to take effect.</span></span> <span data-ttu-id="5e194-108">您必須是全域系統管理員或 Teams 服務系統管理員，才能管理這些原則。</span><span class="sxs-lookup"><span data-stu-id="5e194-108">You must be a global admin or Teams service admin to manage these policies.</span></span>

## <a name="overview-of-custom-apps"></a><span data-ttu-id="5e194-109">自訂應用程式概觀</span><span class="sxs-lookup"><span data-stu-id="5e194-109">Overview of custom apps</span></span>

<span data-ttu-id="5e194-110">使用者可以將自訂應用程式Teams， (將應用程式套件.zip檔案) 直接上傳至小組或個人內容。</span><span class="sxs-lookup"><span data-stu-id="5e194-110">Users can add a custom app to Teams by uploading an app package (in a .zip file) directly to a team or in the personal context.</span></span> <span data-ttu-id="5e194-111">這和透過應用程式商店新增應用程式的方式Teams不同。</span><span class="sxs-lookup"><span data-stu-id="5e194-111">This is different from how apps are added through the Teams app store.</span></span> <span data-ttu-id="5e194-112">上傳應用程式套件來新增自訂應用程式 ，也稱為側載功能，可讓您在應用程式準備好廣泛發佈之前，先測試正在開發中的應用程式。</span><span class="sxs-lookup"><span data-stu-id="5e194-112">Adding a custom app by uploading an app package, also known as sideloading, lets you test an app as it's being developed, before it's ready to be widely distributed.</span></span> <span data-ttu-id="5e194-113">它也可讓您建立僅供內部使用的應用程式，並與小組共用，而不將應用程式提交給 Teams 應用程式Teams目錄。</span><span class="sxs-lookup"><span data-stu-id="5e194-113">It also lets you build an app for internal use only and share it with your team without submitting it to the Teams app catalog in the Teams app store.</span></span>

![顯示 App Store 中上傳自訂應用程式選項的螢幕擷取畫面](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a><span data-ttu-id="5e194-115">自訂應用程式策略和設定</span><span class="sxs-lookup"><span data-stu-id="5e194-115">Custom app policy and settings</span></span>

<span data-ttu-id="5e194-116">三個元件可決定使用者是否可以將自訂應用程式上傳至團隊，讓您精細控制誰可以新增自訂應用程式至團隊，以及哪些團隊自訂應用程式可以新增到：</span><span class="sxs-lookup"><span data-stu-id="5e194-116">Three components determine whether a user can upload a custom app to a team, giving you granular control over who can add custom apps to a team and which teams custom apps can be added to:</span></span>

- [<span data-ttu-id="5e194-117">使用者自訂應用程式策略</span><span class="sxs-lookup"><span data-stu-id="5e194-117">User custom app policy</span></span>](#user-custom-app-policy)
- [<span data-ttu-id="5e194-118">小組自訂應用程式設定</span><span class="sxs-lookup"><span data-stu-id="5e194-118">Team custom app setting</span></span>](#team-custom-app-setting)
- [<span data-ttu-id="5e194-119">全組織自訂應用程式設定</span><span class="sxs-lookup"><span data-stu-id="5e194-119">Org-wide custom app setting</span></span>](#org-wide-custom-app-setting)

<span data-ttu-id="5e194-120">這些設定不會影響封鎖協力廠商應用程式的能力。</span><span class="sxs-lookup"><span data-stu-id="5e194-120">These settings don't affect the ability to block third-party apps.</span></span>  

### <a name="user-custom-app-policy"></a><span data-ttu-id="5e194-121">使用者自訂應用程式策略</span><span class="sxs-lookup"><span data-stu-id="5e194-121">User custom app policy</span></span>

<span data-ttu-id="5e194-122">在 [應用程式設定政策](teams-app-setup-policies.md)中，系統管理員可以使用策略設定 ，Upload **自訂應用程式**，以控制使用者是否可以將自訂應用程式上傳到 Teams。</span><span class="sxs-lookup"><span data-stu-id="5e194-122">As part of [app setup policies](teams-app-setup-policies.md), admins can use a policy setting, **Upload custom apps**, to control whether a user can upload custom apps to Teams.</span></span>
 
<span data-ttu-id="5e194-123">如果此設定已關閉：</span><span class="sxs-lookup"><span data-stu-id="5e194-123">If this setting is turned off:</span></span>

- <span data-ttu-id="5e194-124">使用者無法將自訂應用程式上傳到貴組織或個人環境中的任何小組。</span><span class="sxs-lookup"><span data-stu-id="5e194-124">The user can't upload a custom app to any team in your organization or in the personal context.</span></span>
- <span data-ttu-id="5e194-125">使用者可以視整個組織自訂應用程式設定，與自訂應用程式互動。</span><span class="sxs-lookup"><span data-stu-id="5e194-125">The user can interact with custom apps, depending on the org-wide custom app setting.</span></span>

<span data-ttu-id="5e194-126">如果已開啟此設定：</span><span class="sxs-lookup"><span data-stu-id="5e194-126">If this setting is turned on:</span></span>

- <span data-ttu-id="5e194-127">使用者可以視整個組織自訂應用程式設定，將自訂應用程式上傳到允許的小組，以及他們擁有的團隊。</span><span class="sxs-lookup"><span data-stu-id="5e194-127">The user can upload custom apps to teams that allow it and to teams for which they are owners, depending on the org-wide custom app setting.</span></span>
- <span data-ttu-id="5e194-128">使用者可以將自訂應用程式上傳至個人內容。</span><span class="sxs-lookup"><span data-stu-id="5e194-128">The user can upload custom apps to the personal context.</span></span> 
- <span data-ttu-id="5e194-129">使用者可以視整個組織自訂應用程式設定，與自訂應用程式互動。</span><span class="sxs-lookup"><span data-stu-id="5e194-129">The user can interact with custom apps, depending on the org-wide custom app setting.</span></span>

<span data-ttu-id="5e194-130">您可以編輯全域應用程式設定策略中的設定，以包含您想要的應用程式。</span><span class="sxs-lookup"><span data-stu-id="5e194-130">You can edit the settings in the global app setup policy to include the apps that you want.</span></span> <span data-ttu-id="5e194-131">如果您想要為貴組織Teams使用者群組自訂應用程式，請建立並指派一或多個自訂應用程式設定策略。</span><span class="sxs-lookup"><span data-stu-id="5e194-131">If you want to customize Teams for different groups of users in your organization, create and assign one or more custom app setup policies.</span></span>

#### <a name="set-a-user-custom-app-policy"></a><span data-ttu-id="5e194-132">設定使用者自訂應用程式策略</span><span class="sxs-lookup"><span data-stu-id="5e194-132">Set a user custom app policy</span></span>

1. <span data-ttu-id="5e194-133">在系統管理中心的左側導Microsoft Teams，請前往 Teams **設定**  >  **政策**。</span><span class="sxs-lookup"><span data-stu-id="5e194-133">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="5e194-134">按一下 [新增 **]**。</span><span class="sxs-lookup"><span data-stu-id="5e194-134">Click **Add**.</span></span>
3. <span data-ttu-id="5e194-135">開啟或關閉自訂 **Upload應用程式**。</span><span class="sxs-lookup"><span data-stu-id="5e194-135">Turn on or turn off **Upload custom apps**.</span></span>
4. <span data-ttu-id="5e194-136">選擇您想要用於該策略的其他任何設定。</span><span class="sxs-lookup"><span data-stu-id="5e194-136">Choose any other settings that you want to for the policy.</span></span>
5. <span data-ttu-id="5e194-137">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="5e194-137">Click **Save**.</span></span>

### <a name="team-custom-app-setting"></a><span data-ttu-id="5e194-138">小組自訂應用程式設定</span><span class="sxs-lookup"><span data-stu-id="5e194-138">Team custom app setting</span></span>

<span data-ttu-id="5e194-139">系統管理員和團隊擁有者可以控制團隊是否允許新增自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="5e194-139">Admins and team owners can control whether a team allows for custom apps to be added to it.</span></span> <span data-ttu-id="5e194-140">此設定 **：允許成員上傳自訂應用程式**，以及使用者的自訂應用程式策略，決定誰可以新增自訂應用程式至特定團隊。</span><span class="sxs-lookup"><span data-stu-id="5e194-140">This setting, **Allow members to upload custom apps**, together with a user's custom app policy determines who can add custom apps to a particular team.</span></span>
 
<span data-ttu-id="5e194-141">如果此設定已關閉：</span><span class="sxs-lookup"><span data-stu-id="5e194-141">If this setting is turned off:</span></span>

- <span data-ttu-id="5e194-142">團隊擁有者可以新增自訂應用程式 ，如果他們的自訂應用程式策略允許的話。</span><span class="sxs-lookup"><span data-stu-id="5e194-142">Team owners can add custom apps, if their custom app policy allows it.</span></span>
- <span data-ttu-id="5e194-143">不是團隊擁有者的小組成員無法新增自訂應用程式至團隊。</span><span class="sxs-lookup"><span data-stu-id="5e194-143">Team members who aren't team owners can't add custom apps to the team.</span></span>

<span data-ttu-id="5e194-144">如果已開啟此設定：</span><span class="sxs-lookup"><span data-stu-id="5e194-144">If this setting is turned on:</span></span>

- <span data-ttu-id="5e194-145">團隊擁有者可以新增自訂應用程式 ，如果他們的自訂應用程式策略允許的話。</span><span class="sxs-lookup"><span data-stu-id="5e194-145">Team owners can add custom apps, if their custom app policy allows for it.</span></span>
- <span data-ttu-id="5e194-146">如果團隊成員的自訂應用程式策略允許，不是團隊擁有者的小組成員可以新增自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="5e194-146">Team members who aren't team owners can add custom apps, if their custom app policy allows for it.</span></span>

#### <a name="configure-the-team-custom-app-setting"></a><span data-ttu-id="5e194-147">設定小組自訂應用程式設定</span><span class="sxs-lookup"><span data-stu-id="5e194-147">Configure the team custom app setting</span></span>

1. <span data-ttu-id="5e194-148">在 Teams，請前往團隊，按一下 [**更多選項 1 12 月 13**  >  **日管理小組**。</span><span class="sxs-lookup"><span data-stu-id="5e194-148">In Teams, go to the team, click **More options ˙˙˙** > **Manage team**.</span></span>
2. <span data-ttu-id="5e194-149">按一下 **設定**，然後展開 **[成員許可權**> 。</span><span class="sxs-lookup"><span data-stu-id="5e194-149">Click **Settings**, and then expand **Member permissions**.</span></span>
3. <span data-ttu-id="5e194-150">選取或清除允許 **成員上傳自訂應用程式** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="5e194-150">Select or clear the **Allow members to upload custom apps** check box.</span></span>

    ![顯示小組自訂應用程式設定之螢幕擷取畫面](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a><span data-ttu-id="5e194-152">全組織自訂應用程式設定</span><span class="sxs-lookup"><span data-stu-id="5e194-152">Org-wide custom app setting</span></span>

<span data-ttu-id="5e194-153">在 **管理應用程式** 頁面上，允許與自訂應用程式互動的全組織自訂 [](manage-apps.md)應用程式設定會適用于貴組織中的每個人，並規範他們是否可以上傳或與自訂應用程式互動。</span><span class="sxs-lookup"><span data-stu-id="5e194-153">The **Allow interaction with custom apps** org-wide custom app setting on the [Manage apps](manage-apps.md) page applies to everyone in your organization and governs whether they can upload or interact with custom apps.</span></span> <span data-ttu-id="5e194-154">此設定可做為使用者和小組自訂應用程式策略設定的主開啟/關閉開關。</span><span class="sxs-lookup"><span data-stu-id="5e194-154">This setting acts as a master on/off switch for the user and team custom app policy settings.</span></span> <span data-ttu-id="5e194-155">它旨在做為安全性事件期間的主開啟/關閉開關。</span><span class="sxs-lookup"><span data-stu-id="5e194-155">It's intended to serve as a master on/off switch during security events.</span></span> <span data-ttu-id="5e194-156">因此，使用者和小組自訂應用程式策略設定不會生效，除非啟用全組織自訂應用程式設定，即使已啟用使用者和小組自訂應用程式策略設定。</span><span class="sxs-lookup"><span data-stu-id="5e194-156">As such, user and team custom app policy settings will not take effect unless the org-wide custom app setting is enabled even if user and team custom app policy settings are enabled.</span></span>

#### <a name="configure-the-org-wide-custom-app-setting"></a><span data-ttu-id="5e194-157">設定全組織自訂應用程式設定</span><span class="sxs-lookup"><span data-stu-id="5e194-157">Configure the org-wide custom app setting</span></span>

1. <span data-ttu-id="5e194-158">在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 **Teams 應用程式** > **管理應用程式**。</span><span class="sxs-lookup"><span data-stu-id="5e194-158">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="5e194-159">按一下 **[全組織應用程式設定>**。</span><span class="sxs-lookup"><span data-stu-id="5e194-159">Click **Org-wide app settings**.</span></span>
3. <span data-ttu-id="5e194-160">在 **自訂應用程式下**，開啟或關閉允許 **與自訂應用程式互動**。</span><span class="sxs-lookup"><span data-stu-id="5e194-160">Under **Custom apps**, turn on or turn off **Allow interaction with custom apps**.</span></span>

    ![顯示全組織自訂應用程式設定之螢幕擷取畫面](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a><span data-ttu-id="5e194-162">自訂應用程式策略和設定如何共同作業</span><span class="sxs-lookup"><span data-stu-id="5e194-162">How custom app policies and settings work together</span></span>

<span data-ttu-id="5e194-163">此表格摘要列出自訂應用程式策略和設定、它們如何共同作業，以及它們對於控制組織中誰可以將自訂應用程式上傳至 Teams。</span><span class="sxs-lookup"><span data-stu-id="5e194-163">This table summarizes the custom app policy and settings, how they work together, and their combined effect on controlling who in your organization can upload custom apps to Teams.</span></span>

<span data-ttu-id="5e194-164">例如，假設您想要只允許團隊擁有者將自訂應用程式上傳至特定團隊。</span><span class="sxs-lookup"><span data-stu-id="5e194-164">Say, for example, you want to allow only team owners to upload custom apps to specific teams.</span></span> <span data-ttu-id="5e194-165">您可以設定下列專案：</span><span class="sxs-lookup"><span data-stu-id="5e194-165">You would set the following:</span></span>
- <span data-ttu-id="5e194-166">開啟 **系統管理中心** 中的允許與自訂應用程式Microsoft Teams設定。</span><span class="sxs-lookup"><span data-stu-id="5e194-166">Turn on the **Allow interaction with custom apps** setting in the Microsoft Teams admin center.</span></span>
- <span data-ttu-id="5e194-167">關閉允許 **成員針對** 您想要限制存取的每一個團隊上傳自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="5e194-167">Turn off the **Allow members to upload custom apps** for every team to which you want to restrict access.</span></span>
- <span data-ttu-id="5e194-168">在系統管理中心建立並Microsoft Teams自訂應用程式設定，Upload **自訂** 應用程式設定，並將它指派給團隊擁有者。</span><span class="sxs-lookup"><span data-stu-id="5e194-168">Create and assign a custom app setup policy in the Microsoft Teams admin center with the **Upload custom apps** setting turned on, and assign it to the team owners.</span></span>

|<span data-ttu-id="5e194-169">全組織自訂應用程式設定</span><span class="sxs-lookup"><span data-stu-id="5e194-169">Org-wide custom app setting</span></span> |<span data-ttu-id="5e194-170">小組自訂應用程式設定</span><span class="sxs-lookup"><span data-stu-id="5e194-170">Team custom app setting</span></span> |<span data-ttu-id="5e194-171">使用者自訂應用程式策略</span><span class="sxs-lookup"><span data-stu-id="5e194-171">User custom app policy</span></span> |<span data-ttu-id="5e194-172">影響</span><span class="sxs-lookup"><span data-stu-id="5e194-172">Effect</span></span>  |
|---------|---------|---------|---------|
| <span data-ttu-id="5e194-173">關閉</span><span class="sxs-lookup"><span data-stu-id="5e194-173">Off</span></span>    | <span data-ttu-id="5e194-174">關閉</span><span class="sxs-lookup"><span data-stu-id="5e194-174">Off</span></span>    | <span data-ttu-id="5e194-175">關閉</span><span class="sxs-lookup"><span data-stu-id="5e194-175">Off</span></span>     |<span data-ttu-id="5e194-176">貴組織會封鎖所有自訂應用程式的互動。</span><span class="sxs-lookup"><span data-stu-id="5e194-176">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="5e194-177">除了服務系統管理員或全域系統管理員之外，Teams無法上傳自訂應用程式。您可以使用 PowerShell 移除自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="5e194-177">Custom apps can't be uploaded by anyone except a Teams Service Admin or a Global admin. You can use PowerShell to remove the custom app.</span></span>   |
| <span data-ttu-id="5e194-178">關閉</span><span class="sxs-lookup"><span data-stu-id="5e194-178">Off</span></span>     | <span data-ttu-id="5e194-179">關閉</span><span class="sxs-lookup"><span data-stu-id="5e194-179">Off</span></span>     | <span data-ttu-id="5e194-180">開啟</span><span class="sxs-lookup"><span data-stu-id="5e194-180">On</span></span>        |<span data-ttu-id="5e194-181">貴組織會封鎖所有自訂應用程式的互動。</span><span class="sxs-lookup"><span data-stu-id="5e194-181">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="5e194-182">除了服務系統管理員或全域系統管理員之外，Teams無法上傳自訂應用程式。您可以使用 PowerShell 移除自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="5e194-182">Custom apps can't be uploaded by anyone except a Teams Service Admin or a Global admin. You can use PowerShell to remove the custom app.</span></span>         |
| <span data-ttu-id="5e194-183">關閉</span><span class="sxs-lookup"><span data-stu-id="5e194-183">Off</span></span>    | <span data-ttu-id="5e194-184">開啟</span><span class="sxs-lookup"><span data-stu-id="5e194-184">On</span></span>        | <span data-ttu-id="5e194-185">關閉</span><span class="sxs-lookup"><span data-stu-id="5e194-185">Off</span></span>        |<span data-ttu-id="5e194-186">貴組織會封鎖所有自訂應用程式的互動。</span><span class="sxs-lookup"><span data-stu-id="5e194-186">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="5e194-187">除了服務系統管理員或全域系統管理員之外，Teams無法上傳自訂應用程式。您可以使用自訂Windows PowerShell刪除自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="5e194-187">Custom apps can't be uploaded by anyone except a Teams Service Admin or a Global admin. You can use Windows PowerShell to delete custom apps.</span></span>         |
| <span data-ttu-id="5e194-188">關閉</span><span class="sxs-lookup"><span data-stu-id="5e194-188">Off</span></span>    | <span data-ttu-id="5e194-189">開啟</span><span class="sxs-lookup"><span data-stu-id="5e194-189">On</span></span>      | <span data-ttu-id="5e194-190">開啟</span><span class="sxs-lookup"><span data-stu-id="5e194-190">On</span></span>       |<span data-ttu-id="5e194-191">貴組織會封鎖所有自訂應用程式的互動。</span><span class="sxs-lookup"><span data-stu-id="5e194-191">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="5e194-192">除了服務系統管理員或全域系統管理員之外，Teams無法上傳自訂應用程式。您可以使用 PowerShell 移除自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="5e194-192">Custom apps can't be uploaded by anyone except a Teams Service Admin or a Global admin. You can use PowerShell to remove the custom app.</span></span>         |
| <span data-ttu-id="5e194-193">開啟</span><span class="sxs-lookup"><span data-stu-id="5e194-193">On</span></span>    | <span data-ttu-id="5e194-194">關閉</span><span class="sxs-lookup"><span data-stu-id="5e194-194">Off</span></span>       | <span data-ttu-id="5e194-195">關閉</span><span class="sxs-lookup"><span data-stu-id="5e194-195">Off</span></span>         |  <span data-ttu-id="5e194-196">使用者無法上傳自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="5e194-196">The user can't upload custom apps.</span></span>      |
| <span data-ttu-id="5e194-197">開啟</span><span class="sxs-lookup"><span data-stu-id="5e194-197">On</span></span>     | <span data-ttu-id="5e194-198">關閉</span><span class="sxs-lookup"><span data-stu-id="5e194-198">Off</span></span>       | <span data-ttu-id="5e194-199">開啟</span><span class="sxs-lookup"><span data-stu-id="5e194-199">On</span></span>         | <span data-ttu-id="5e194-200">如果使用者是團隊擁有者，他們可以將自訂應用程式上傳至團隊。</span><span class="sxs-lookup"><span data-stu-id="5e194-200">If the user is a team owner, they can upload custom apps to the team.</span></span> <span data-ttu-id="5e194-201">如果使用者不是團隊擁有者，他們無法將自訂應用程式上傳至團隊。</span><span class="sxs-lookup"><span data-stu-id="5e194-201">If the user isn't a team owner, they can't upload custom apps to the team.</span></span> <span data-ttu-id="5e194-202">使用者可以在個人環境中上傳自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="5e194-202">The user can upload custom apps in the personal context.</span></span>     |
| <span data-ttu-id="5e194-203">開啟</span><span class="sxs-lookup"><span data-stu-id="5e194-203">On</span></span>     | <span data-ttu-id="5e194-204">開啟</span><span class="sxs-lookup"><span data-stu-id="5e194-204">On</span></span>     | <span data-ttu-id="5e194-205">關閉</span><span class="sxs-lookup"><span data-stu-id="5e194-205">Off</span></span>         | <span data-ttu-id="5e194-206">使用者無法上傳自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="5e194-206">The user can't upload custom apps.</span></span>       |
| <span data-ttu-id="5e194-207">開啟</span><span class="sxs-lookup"><span data-stu-id="5e194-207">On</span></span>    | <span data-ttu-id="5e194-208">開啟</span><span class="sxs-lookup"><span data-stu-id="5e194-208">On</span></span>        | <span data-ttu-id="5e194-209">開啟</span><span class="sxs-lookup"><span data-stu-id="5e194-209">On</span></span>        | <span data-ttu-id="5e194-210">無論使用者是否是團隊擁有者，使用者都可以將自訂應用程式上傳至團隊。</span><span class="sxs-lookup"><span data-stu-id="5e194-210">The user can upload custom apps to the team, regardless of whether the user is a team owner.</span></span> <span data-ttu-id="5e194-211">使用者可以在個人環境中上傳自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="5e194-211">The user can upload custom apps in the personal context.</span></span>       |

## <a name="related-topics"></a><span data-ttu-id="5e194-212">相關主題</span><span class="sxs-lookup"><span data-stu-id="5e194-212">Related topics</span></span>
 
[<span data-ttu-id="5e194-213">在 Teams 中管理應用程式的設定</span><span class="sxs-lookup"><span data-stu-id="5e194-213">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="5e194-214">在 Teams 中將原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="5e194-214">Assign policies to your users in Teams</span></span>](assign-policies.md)