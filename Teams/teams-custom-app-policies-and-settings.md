---
title: 管理 Microsoft 團隊中的自訂應用程式原則和設定
author: lanachin
ms.author: v-lanac
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
description: 瞭解如何管理自訂應用程式原則和設定，以控制貴組織中的哪些人員可以上傳 Microsoft 團隊中的自訂應用程式。
f1keywords:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
ms.openlocfilehash: 9d700ae83dd62c8308e7a792acd2d97c999649fa
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570242"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a><span data-ttu-id="adca6-103">管理 Microsoft 團隊中的自訂應用程式原則和設定</span><span class="sxs-lookup"><span data-stu-id="adca6-103">Manage custom app policies and settings in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="adca6-104">若要使用應用程式 Studio，請參閱[使用 c #/.NET 和 App Studio 的 Microsoft 團隊平臺快速](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-dotnet-app-studio)入門最後一個步驟尚無法運作，因此您必須先下載該 zip，然後在將[應用程式套件上傳到 Microsoft 團隊](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload)時將它安裝。</span><span class="sxs-lookup"><span data-stu-id="adca6-104">To use App Studio see [Get started on the Microsoft Teams platform with C#/.NET and App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-dotnet-app-studio) The last step is not working yet, so you will need to download the zip and install it the old way at [Upload an app package to Microsoft Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload).</span></span>

<span data-ttu-id="adca6-105">做為管理員，您可以使用自訂的應用程式原則和設定來控制貴組織中的哪些人可以將自訂應用程式上傳到 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="adca6-105">As an admin, you can use custom app policies and settings to control who in your organization can upload custom apps to Microsoft Teams.</span></span> <span data-ttu-id="adca6-106">系統管理員決定可以上傳自訂應用程式的使用者，以及系統管理員和小組擁有者可以判斷您組織中的特定團隊是否允許將自訂應用程式新增到他們。</span><span class="sxs-lookup"><span data-stu-id="adca6-106">Admins decide which users can upload custom apps, and admins and team owners can determine whether specific teams in your organization allow custom apps to be added to them.</span></span>  

## <a name="overview-of-custom-apps"></a><span data-ttu-id="adca6-107">自訂應用程式的概覽</span><span class="sxs-lookup"><span data-stu-id="adca6-107">Overview of custom apps</span></span>

<span data-ttu-id="adca6-108">使用者可以將自訂 app 新增至團隊，方法是將應用程式套件（在 .zip 檔案中）直接上傳到小組或個人內容。</span><span class="sxs-lookup"><span data-stu-id="adca6-108">Users can add a custom app to Teams by uploading an app package (in a .zip file) directly to a team or in the personal context.</span></span> <span data-ttu-id="adca6-109">這與透過 [團隊 app store] 新增應用程式的方式不同。</span><span class="sxs-lookup"><span data-stu-id="adca6-109">This is different from how apps are added through the Teams app store.</span></span> <span data-ttu-id="adca6-110">透過上傳應用程式套件（又稱為邊載）來新增自訂應用程式，可讓您在開發應用程式之前先測試該 app，然後才能廣泛發佈。</span><span class="sxs-lookup"><span data-stu-id="adca6-110">Adding a custom app by uploading an app package, also known as sideloading, lets you test an app as it's being developed, before it's ready to be widely distributed.</span></span> <span data-ttu-id="adca6-111">它也可讓您建立僅供內部使用的 app，並與您的小組共用該應用程式，而不需提交至 [小組] app 商店中的 [小組] 應用程式目錄。</span><span class="sxs-lookup"><span data-stu-id="adca6-111">It also lets you build an app for internal use only and share it with your team without submitting it to the Teams app catalog in the Teams app store.</span></span>

![螢幕擷取畫面顯示 app store 中的 [上傳自訂應用程式] 選項](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a><span data-ttu-id="adca6-113">自訂 app 原則和設定</span><span class="sxs-lookup"><span data-stu-id="adca6-113">Custom app policy and settings</span></span>

<span data-ttu-id="adca6-114">三個元件會判斷使用者是否可將自訂應用程式上傳至團隊，讓您精細控制哪些人可以將自訂應用程式新增至團隊，以及可將哪些團隊自訂應用程式新增至：</span><span class="sxs-lookup"><span data-stu-id="adca6-114">Three components determine whether a user can upload a custom app to a team, giving you granular control over who can add custom apps to a team and which teams custom apps can be added to:</span></span>

- [<span data-ttu-id="adca6-115">使用者自訂 app 原則</span><span class="sxs-lookup"><span data-stu-id="adca6-115">User custom app policy</span></span>](#user-custom-app-policy)
- [<span data-ttu-id="adca6-116">團隊自訂應用程式設定</span><span class="sxs-lookup"><span data-stu-id="adca6-116">Team custom app setting</span></span>](#team-custom-app-setting)
- [<span data-ttu-id="adca6-117">全組織的自訂應用程式設定</span><span class="sxs-lookup"><span data-stu-id="adca6-117">Org-wide custom app setting</span></span>](#org-wide-custom-app-setting)

<span data-ttu-id="adca6-118">這些設定不會影響封鎖協力廠商應用程式的能力。</span><span class="sxs-lookup"><span data-stu-id="adca6-118">These settings don't affect the ability to block third-party apps.</span></span>  

### <a name="user-custom-app-policy"></a><span data-ttu-id="adca6-119">使用者自訂 app 原則</span><span class="sxs-lookup"><span data-stu-id="adca6-119">User custom app policy</span></span>

<span data-ttu-id="adca6-120">在[應用程式設定原則](teams-app-setup-policies.md)中，系統管理員可以使用原則設定、**允許上傳自訂應用程式**，控制使用者是否能將自訂應用程式上傳給團隊。</span><span class="sxs-lookup"><span data-stu-id="adca6-120">As part of [app setup policies](teams-app-setup-policies.md), admins can use a policy setting, **Allow uploading custom apps**, to control whether a user can upload custom apps to Teams.</span></span>
 
<span data-ttu-id="adca6-121">如果已關閉此設定：</span><span class="sxs-lookup"><span data-stu-id="adca6-121">If this setting is turned off:</span></span>

- <span data-ttu-id="adca6-122">使用者無法將自訂應用程式上傳到貴組織中的任何小組或個人內容。</span><span class="sxs-lookup"><span data-stu-id="adca6-122">The user can't upload a custom app to any team in your organization or in the personal context.</span></span>
- <span data-ttu-id="adca6-123">根據組織範圍內的自訂應用程式設定，使用者可以與自訂應用程式互動。</span><span class="sxs-lookup"><span data-stu-id="adca6-123">The user can interact with custom apps, depending on the org-wide custom app setting.</span></span>

<span data-ttu-id="adca6-124">如果已開啟此設定：</span><span class="sxs-lookup"><span data-stu-id="adca6-124">If this setting is turned on:</span></span>

- <span data-ttu-id="adca6-125">使用者可以將自訂應用程式上傳給小組，讓他們能根據組織範圍內的自訂應用程式設定，將自訂 app 上傳給擁有者的團隊。</span><span class="sxs-lookup"><span data-stu-id="adca6-125">The user can upload custom apps to teams that allow it and to teams for which they are owners, depending on the org-wide custom app setting.</span></span>
- <span data-ttu-id="adca6-126">使用者可以將自訂應用程式上傳到個人內容。</span><span class="sxs-lookup"><span data-stu-id="adca6-126">The user can upload custom apps to the personal context.</span></span> 
- <span data-ttu-id="adca6-127">根據組織範圍內的自訂應用程式設定，使用者可以與自訂應用程式互動。</span><span class="sxs-lookup"><span data-stu-id="adca6-127">The user can interact with custom apps, depending on the org-wide custom app setting.</span></span>

<span data-ttu-id="adca6-128">您可以編輯全域 app 設定原則中的設定，以包含您想要的 app。</span><span class="sxs-lookup"><span data-stu-id="adca6-128">You can edit the settings in the global app setup policy to include the apps that you want.</span></span> <span data-ttu-id="adca6-129">如果您想要針對貴組織中不同的使用者群組自訂小組，請建立並指派一或多個自訂應用程式設定原則。</span><span class="sxs-lookup"><span data-stu-id="adca6-129">If you want to customize Teams for different groups of users in your organization, create and assign one or more custom app setup policies.</span></span>

#### <a name="set-a-user-custom-app-policy"></a><span data-ttu-id="adca6-130">設定使用者自訂 app 原則</span><span class="sxs-lookup"><span data-stu-id="adca6-130">Set a user custom app policy</span></span>

1. <span data-ttu-id="adca6-131">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app** > **設定原則**]。</span><span class="sxs-lookup"><span data-stu-id="adca6-131">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="adca6-132">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="adca6-132">Click **Add**.</span></span>
3. <span data-ttu-id="adca6-133">開啟或關閉 [**允許上傳自訂應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="adca6-133">Turn on or turn off **Allow uploading custom apps**.</span></span>
4. <span data-ttu-id="adca6-134">選擇您想要用於原則的任何其他設定。</span><span class="sxs-lookup"><span data-stu-id="adca6-134">Choose any other settings that you want to for the policy.</span></span>
5. <span data-ttu-id="adca6-135">按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="adca6-135">Click **Save**.</span></span>

### <a name="team-custom-app-setting"></a><span data-ttu-id="adca6-136">團隊自訂應用程式設定</span><span class="sxs-lookup"><span data-stu-id="adca6-136">Team custom app setting</span></span>

<span data-ttu-id="adca6-137">系統管理員和小組擁有者可以控制團隊是否允許將自訂應用程式新增到其中。</span><span class="sxs-lookup"><span data-stu-id="adca6-137">Admins and team owners can control whether a team allows for custom apps to be added to it.</span></span> <span data-ttu-id="adca6-138">此設定可**讓成員上傳自訂應用程式**，以及使用者的自訂應用程式原則，決定誰可以將自訂應用程式新增至特定團隊。</span><span class="sxs-lookup"><span data-stu-id="adca6-138">This setting, **Allow members to upload custom apps**, together with a user's custom app policy determines who can add custom apps to a particular team.</span></span>
 
<span data-ttu-id="adca6-139">如果已關閉此設定：</span><span class="sxs-lookup"><span data-stu-id="adca6-139">If this setting is turned off:</span></span>

- <span data-ttu-id="adca6-140">如果他們的自訂 app 原則允許，小組擁有者可以新增自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="adca6-140">Team owners can add custom apps, if their custom app policy allows it.</span></span>
- <span data-ttu-id="adca6-141">不是團隊擁有者的小組成員無法將自訂應用程式新增至團隊。</span><span class="sxs-lookup"><span data-stu-id="adca6-141">Team members who aren't team owners can't add custom apps to the team.</span></span>

<span data-ttu-id="adca6-142">如果已開啟此設定：</span><span class="sxs-lookup"><span data-stu-id="adca6-142">If this setting is turned on:</span></span>

- <span data-ttu-id="adca6-143">小組擁有者可以新增自訂的應用程式（如果他們的自訂應用程式原則允許）。</span><span class="sxs-lookup"><span data-stu-id="adca6-143">Team owners can add custom apps, if their custom app policy allows for it.</span></span>
- <span data-ttu-id="adca6-144">不是團隊擁有者的小組成員可以新增自訂應用程式（如果他們的自訂應用程式原則允許）。</span><span class="sxs-lookup"><span data-stu-id="adca6-144">Team members who aren't team owners can add custom apps, if their custom app policy allows for it.</span></span>

#### <a name="configure-the-team-custom-app-setting"></a><span data-ttu-id="adca6-145">設定小組自訂應用程式設定</span><span class="sxs-lookup"><span data-stu-id="adca6-145">Configure the team custom app setting</span></span>

1. <span data-ttu-id="adca6-146">在 [團隊] 中，移至團隊，按一下 [**更多選項] ̇̇̇** > [**管理團隊**]。</span><span class="sxs-lookup"><span data-stu-id="adca6-146">In Teams, go to the team, click **More options ˙˙˙** > **Manage team**.</span></span>
2. <span data-ttu-id="adca6-147">按一下 [**設定**]，然後展開 [**成員許可權**]。</span><span class="sxs-lookup"><span data-stu-id="adca6-147">Click **Settings**, and then expand **Member permissions**.</span></span>
3. <span data-ttu-id="adca6-148">選取或清除 [**允許成員上傳自訂應用程式**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="adca6-148">Select or clear the **Allow members to upload custom apps** check box.</span></span>

    ![顯示小組自訂應用程式設定的螢幕擷取畫面](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a><span data-ttu-id="adca6-150">全組織的自訂應用程式設定</span><span class="sxs-lookup"><span data-stu-id="adca6-150">Org-wide custom app setting</span></span>

<span data-ttu-id="adca6-151">組織範圍的自訂應用程式設定，可**讓您與自訂應用程式進行互動**，並將其套用至組織中的所有人，並控制他們是否可以上傳或與自訂 app 互動。</span><span class="sxs-lookup"><span data-stu-id="adca6-151">The org-wide custom app setting, **Allow interaction with custom apps**, applies to everyone in your organization and governs whether they can upload or interact with custom apps.</span></span> <span data-ttu-id="adca6-152">此設定會覆寫使用者和團隊的自訂應用程式原則與設定。</span><span class="sxs-lookup"><span data-stu-id="adca6-152">This setting overrides the user and team custom app policy and setting.</span></span> <span data-ttu-id="adca6-153">它是用來在安全性事件期間作為主機開啟/關閉切換。</span><span class="sxs-lookup"><span data-stu-id="adca6-153">It's intended to serve as a master on/off switch during security events.</span></span>

#### <a name="configure-the-org-wide-custom-app-setting"></a><span data-ttu-id="adca6-154">設定組織範圍的自訂應用程式設定</span><span class="sxs-lookup"><span data-stu-id="adca6-154">Configure the org-wide custom app setting</span></span>

1. <span data-ttu-id="adca6-155">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app** > ]**許可權原則**。</span><span class="sxs-lookup"><span data-stu-id="adca6-155">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="adca6-156">按一下 [**全組織式應用程式設定**]。</span><span class="sxs-lookup"><span data-stu-id="adca6-156">Click **Org-wide app settings**.</span></span>
3. <span data-ttu-id="adca6-157">在 [**自訂應用程式**] 底下，開啟或關閉 [**允許與自訂應用程式互動**]。</span><span class="sxs-lookup"><span data-stu-id="adca6-157">Under **Custom apps**, turn on or turn off **Allow interaction with custom apps**.</span></span>

    ![顯示組織範圍自訂應用程式設定的螢幕擷取畫面](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a><span data-ttu-id="adca6-159">自訂 app 原則與設定如何共同運作</span><span class="sxs-lookup"><span data-stu-id="adca6-159">How custom app policies and settings work together</span></span>

<span data-ttu-id="adca6-160">下表摘要列出自訂應用程式原則和設定、它們如何共同運作，以及其結合控制哪些人可以將自訂應用程式上傳至團隊的效果。</span><span class="sxs-lookup"><span data-stu-id="adca6-160">This table summarizes the custom app policy and settings, how they work together, and their combined effect on controlling who in your organization can upload custom apps to Teams.</span></span>

<span data-ttu-id="adca6-161">例如，您想要只允許團隊擁有者將自訂應用程式上傳到特定團隊。</span><span class="sxs-lookup"><span data-stu-id="adca6-161">Say, for example, you want to allow only team owners to upload custom apps to specific teams.</span></span> <span data-ttu-id="adca6-162">您可以設定下列專案：</span><span class="sxs-lookup"><span data-stu-id="adca6-162">You would set the following:</span></span>
- <span data-ttu-id="adca6-163">在 Microsoft 團隊系統管理中心開啟 [**允許與自訂應用程式互動**] 設定。</span><span class="sxs-lookup"><span data-stu-id="adca6-163">Turn on the **Allow interaction with custom apps** setting in the Microsoft Teams admin center.</span></span>
- <span data-ttu-id="adca6-164">針對您要限制存取權的每個團隊，關閉 [**允許成員上傳自訂應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="adca6-164">Turn off the **Allow members to upload custom apps** for every team to which you want to restrict access.</span></span>
- <span data-ttu-id="adca6-165">在 Microsoft 團隊系統管理中心建立並指派自訂的應用程式設定原則，**使用者可以開啟 [自訂應用程式**] 設定，然後將它指派給小組擁有者。</span><span class="sxs-lookup"><span data-stu-id="adca6-165">Create and assign a custom app setup policy in the Microsoft Teams admin center with the **User can upload custom apps** setting turned on, and assign it to the team owners.</span></span>

|<span data-ttu-id="adca6-166">全組織的自訂應用程式設定</span><span class="sxs-lookup"><span data-stu-id="adca6-166">Org-wide custom app setting</span></span> |<span data-ttu-id="adca6-167">團隊自訂應用程式設定</span><span class="sxs-lookup"><span data-stu-id="adca6-167">Team custom app setting</span></span> |<span data-ttu-id="adca6-168">使用者自訂 app 原則</span><span class="sxs-lookup"><span data-stu-id="adca6-168">User custom app policy</span></span> |<span data-ttu-id="adca6-169">效果</span><span class="sxs-lookup"><span data-stu-id="adca6-169">Effect</span></span>  |
|---------|---------|---------|---------|
| <span data-ttu-id="adca6-170">出</span><span class="sxs-lookup"><span data-stu-id="adca6-170">Off</span></span>    | <span data-ttu-id="adca6-171">出</span><span class="sxs-lookup"><span data-stu-id="adca6-171">Off</span></span>    | <span data-ttu-id="adca6-172">出</span><span class="sxs-lookup"><span data-stu-id="adca6-172">Off</span></span>     |<span data-ttu-id="adca6-173">您的組織已封鎖與所有自訂應用程式的互動。</span><span class="sxs-lookup"><span data-stu-id="adca6-173">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="adca6-174">任何人都無法上傳自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="adca6-174">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="adca6-175">您可以使用 PowerShell 來移除自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="adca6-175">You can use PowerShell to remove the custom app.</span></span>   |
| <span data-ttu-id="adca6-176">出</span><span class="sxs-lookup"><span data-stu-id="adca6-176">Off</span></span>     | <span data-ttu-id="adca6-177">出</span><span class="sxs-lookup"><span data-stu-id="adca6-177">Off</span></span>     | <span data-ttu-id="adca6-178">按</span><span class="sxs-lookup"><span data-stu-id="adca6-178">On</span></span>        |<span data-ttu-id="adca6-179">您的組織已封鎖與所有自訂應用程式的互動。</span><span class="sxs-lookup"><span data-stu-id="adca6-179">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="adca6-180">任何人都無法上傳自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="adca6-180">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="adca6-181">您可以使用 PowerShell 來移除自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="adca6-181">You can use PowerShell to remove the custom app.</span></span>         |
| <span data-ttu-id="adca6-182">出</span><span class="sxs-lookup"><span data-stu-id="adca6-182">Off</span></span>    | <span data-ttu-id="adca6-183">按</span><span class="sxs-lookup"><span data-stu-id="adca6-183">On</span></span>        | <span data-ttu-id="adca6-184">出</span><span class="sxs-lookup"><span data-stu-id="adca6-184">Off</span></span>        |<span data-ttu-id="adca6-185">您的組織已封鎖與所有自訂應用程式的互動。</span><span class="sxs-lookup"><span data-stu-id="adca6-185">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="adca6-186">任何人都無法上傳自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="adca6-186">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="adca6-187">您可以使用 Windows PowerShell 來刪除自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="adca6-187">You can use Windows PowerShell to delete custom apps.</span></span>         |
| <span data-ttu-id="adca6-188">出</span><span class="sxs-lookup"><span data-stu-id="adca6-188">Off</span></span>    | <span data-ttu-id="adca6-189">按</span><span class="sxs-lookup"><span data-stu-id="adca6-189">On</span></span>      | <span data-ttu-id="adca6-190">按</span><span class="sxs-lookup"><span data-stu-id="adca6-190">On</span></span>       |<span data-ttu-id="adca6-191">您的組織已封鎖與所有自訂應用程式的互動。</span><span class="sxs-lookup"><span data-stu-id="adca6-191">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="adca6-192">任何人都無法上傳自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="adca6-192">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="adca6-193">您可以使用 PowerShell 來移除自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="adca6-193">You can use PowerShell to remove the custom app.</span></span>         |
| <span data-ttu-id="adca6-194">按</span><span class="sxs-lookup"><span data-stu-id="adca6-194">On</span></span>    | <span data-ttu-id="adca6-195">出</span><span class="sxs-lookup"><span data-stu-id="adca6-195">Off</span></span>       | <span data-ttu-id="adca6-196">出</span><span class="sxs-lookup"><span data-stu-id="adca6-196">Off</span></span>         |  <span data-ttu-id="adca6-197">使用者無法上傳自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="adca6-197">The user can't upload custom apps.</span></span>      |
| <span data-ttu-id="adca6-198">按</span><span class="sxs-lookup"><span data-stu-id="adca6-198">On</span></span>     | <span data-ttu-id="adca6-199">出</span><span class="sxs-lookup"><span data-stu-id="adca6-199">Off</span></span>       | <span data-ttu-id="adca6-200">按</span><span class="sxs-lookup"><span data-stu-id="adca6-200">On</span></span>         | <span data-ttu-id="adca6-201">如果使用者是團隊擁有者，則可將自訂應用程式上傳至團隊。</span><span class="sxs-lookup"><span data-stu-id="adca6-201">If the user is a team owner, they can upload custom apps to the team.</span></span> <span data-ttu-id="adca6-202">如果使用者不是團隊擁有者，則他們無法將自訂應用程式上傳至團隊。</span><span class="sxs-lookup"><span data-stu-id="adca6-202">If the user isn't a team owner, they can't upload custom apps to the team.</span></span> <span data-ttu-id="adca6-203">使用者可以在個人內容中上傳自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="adca6-203">The user can upload custom apps in the personal context.</span></span>     |
| <span data-ttu-id="adca6-204">按</span><span class="sxs-lookup"><span data-stu-id="adca6-204">On</span></span>     | <span data-ttu-id="adca6-205">按</span><span class="sxs-lookup"><span data-stu-id="adca6-205">On</span></span>     | <span data-ttu-id="adca6-206">出</span><span class="sxs-lookup"><span data-stu-id="adca6-206">Off</span></span>         | <span data-ttu-id="adca6-207">使用者無法上傳自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="adca6-207">The user can't upload custom apps.</span></span>       |
| <span data-ttu-id="adca6-208">按</span><span class="sxs-lookup"><span data-stu-id="adca6-208">On</span></span>    | <span data-ttu-id="adca6-209">按</span><span class="sxs-lookup"><span data-stu-id="adca6-209">On</span></span>        | <span data-ttu-id="adca6-210">按</span><span class="sxs-lookup"><span data-stu-id="adca6-210">On</span></span>        | <span data-ttu-id="adca6-211">無論使用者是否為小組擁有者，使用者都可以將自訂應用程式上傳至團隊。</span><span class="sxs-lookup"><span data-stu-id="adca6-211">The user can upload custom apps to the team, regardless of whether the user is a team owner.</span></span> <span data-ttu-id="adca6-212">使用者可以在個人內容中上傳自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="adca6-212">The user can upload custom apps in the personal context.</span></span>       |

 ## <a name="related-topics"></a><span data-ttu-id="adca6-213">相關主題</span><span class="sxs-lookup"><span data-stu-id="adca6-213">Related topics</span></span>
- [<span data-ttu-id="adca6-214">團隊中應用程式的系統管理設定</span><span class="sxs-lookup"><span data-stu-id="adca6-214">Admin settings for apps in Teams</span></span>](admin-settings.md)
