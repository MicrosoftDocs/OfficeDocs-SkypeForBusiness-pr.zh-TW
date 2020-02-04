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
f1.keywords:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
ms.openlocfilehash: 5357f368d6c5716c5af30e110a9193c4b4c2ad5f
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41708459"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a><span data-ttu-id="d0b32-103">管理 Microsoft 團隊中的自訂應用程式原則和設定</span><span class="sxs-lookup"><span data-stu-id="d0b32-103">Manage custom app policies and settings in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="d0b32-104">若要使用應用程式 Studio，請參閱[使用 c #/.NET 和 App Studio 的 Microsoft 團隊平臺快速](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-dotnet-app-studio)入門最後一個步驟尚無法運作，因此您必須先下載該 zip，然後在將[應用程式套件上傳到 Microsoft 團隊](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload)時將它安裝。</span><span class="sxs-lookup"><span data-stu-id="d0b32-104">To use App Studio see [Get started on the Microsoft Teams platform with C#/.NET and App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-dotnet-app-studio) The last step is not working yet, so you will need to download the zip and install it the old way at [Upload an app package to Microsoft Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload).</span></span>

<span data-ttu-id="d0b32-105">做為管理員，您可以使用自訂的應用程式原則和設定來控制貴組織中的哪些人可以將自訂應用程式上傳到 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="d0b32-105">As an admin, you can use custom app policies and settings to control who in your organization can upload custom apps to Microsoft Teams.</span></span> <span data-ttu-id="d0b32-106">系統管理員決定可以上傳自訂應用程式的使用者，以及系統管理員和小組擁有者可以判斷您組織中的特定團隊是否允許將自訂應用程式新增到他們。</span><span class="sxs-lookup"><span data-stu-id="d0b32-106">Admins decide which users can upload custom apps, and admins and team owners can determine whether specific teams in your organization allow custom apps to be added to them.</span></span>  <span data-ttu-id="d0b32-107">在您編輯自訂應用程式原則之後，變更才會生效24小時。</span><span class="sxs-lookup"><span data-stu-id="d0b32-107">After you edit the Custom App policy, it can take up to 24 hours for changes to take effect.</span></span>

## <a name="overview-of-custom-apps"></a><span data-ttu-id="d0b32-108">自訂應用程式的概覽</span><span class="sxs-lookup"><span data-stu-id="d0b32-108">Overview of custom apps</span></span>

<span data-ttu-id="d0b32-109">使用者可以將自訂 app 新增至團隊，方法是將應用程式套件（在 .zip 檔案中）直接上傳到小組或個人內容。</span><span class="sxs-lookup"><span data-stu-id="d0b32-109">Users can add a custom app to Teams by uploading an app package (in a .zip file) directly to a team or in the personal context.</span></span> <span data-ttu-id="d0b32-110">這與透過 [團隊 app store] 新增應用程式的方式不同。</span><span class="sxs-lookup"><span data-stu-id="d0b32-110">This is different from how apps are added through the Teams app store.</span></span> <span data-ttu-id="d0b32-111">透過上傳應用程式套件（又稱為邊載）來新增自訂應用程式，可讓您在開發應用程式之前先測試該 app，然後才能廣泛發佈。</span><span class="sxs-lookup"><span data-stu-id="d0b32-111">Adding a custom app by uploading an app package, also known as sideloading, lets you test an app as it's being developed, before it's ready to be widely distributed.</span></span> <span data-ttu-id="d0b32-112">它也可讓您建立僅供內部使用的 app，並與您的小組共用該應用程式，而不需提交至 [小組] app 商店中的 [小組] 應用程式目錄。</span><span class="sxs-lookup"><span data-stu-id="d0b32-112">It also lets you build an app for internal use only and share it with your team without submitting it to the Teams app catalog in the Teams app store.</span></span>

![螢幕擷取畫面顯示 app store 中的 [上傳自訂應用程式] 選項](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a><span data-ttu-id="d0b32-114">自訂 app 原則和設定</span><span class="sxs-lookup"><span data-stu-id="d0b32-114">Custom app policy and settings</span></span>

<span data-ttu-id="d0b32-115">三個元件會判斷使用者是否可將自訂應用程式上傳至團隊，讓您精細控制哪些人可以將自訂應用程式新增至團隊，以及可將哪些團隊自訂應用程式新增至：</span><span class="sxs-lookup"><span data-stu-id="d0b32-115">Three components determine whether a user can upload a custom app to a team, giving you granular control over who can add custom apps to a team and which teams custom apps can be added to:</span></span>

- [<span data-ttu-id="d0b32-116">使用者自訂 app 原則</span><span class="sxs-lookup"><span data-stu-id="d0b32-116">User custom app policy</span></span>](#user-custom-app-policy)
- [<span data-ttu-id="d0b32-117">團隊自訂應用程式設定</span><span class="sxs-lookup"><span data-stu-id="d0b32-117">Team custom app setting</span></span>](#team-custom-app-setting)
- [<span data-ttu-id="d0b32-118">全組織的自訂應用程式設定</span><span class="sxs-lookup"><span data-stu-id="d0b32-118">Org-wide custom app setting</span></span>](#org-wide-custom-app-setting)

<span data-ttu-id="d0b32-119">這些設定不會影響封鎖協力廠商應用程式的能力。</span><span class="sxs-lookup"><span data-stu-id="d0b32-119">These settings don't affect the ability to block third-party apps.</span></span>  

### <a name="user-custom-app-policy"></a><span data-ttu-id="d0b32-120">使用者自訂 app 原則</span><span class="sxs-lookup"><span data-stu-id="d0b32-120">User custom app policy</span></span>

<span data-ttu-id="d0b32-121">在[應用程式設定原則](teams-app-setup-policies.md)中，系統管理員可以使用原則設定、**允許上傳自訂應用程式**，控制使用者是否能將自訂應用程式上傳給團隊。</span><span class="sxs-lookup"><span data-stu-id="d0b32-121">As part of [app setup policies](teams-app-setup-policies.md), admins can use a policy setting, **Allow uploading custom apps**, to control whether a user can upload custom apps to Teams.</span></span>
 
<span data-ttu-id="d0b32-122">如果已關閉此設定：</span><span class="sxs-lookup"><span data-stu-id="d0b32-122">If this setting is turned off:</span></span>

- <span data-ttu-id="d0b32-123">使用者無法將自訂應用程式上傳到貴組織中的任何小組或個人內容。</span><span class="sxs-lookup"><span data-stu-id="d0b32-123">The user can't upload a custom app to any team in your organization or in the personal context.</span></span>
- <span data-ttu-id="d0b32-124">根據組織範圍內的自訂應用程式設定，使用者可以與自訂應用程式互動。</span><span class="sxs-lookup"><span data-stu-id="d0b32-124">The user can interact with custom apps, depending on the org-wide custom app setting.</span></span>

<span data-ttu-id="d0b32-125">如果已開啟此設定：</span><span class="sxs-lookup"><span data-stu-id="d0b32-125">If this setting is turned on:</span></span>

- <span data-ttu-id="d0b32-126">使用者可以將自訂應用程式上傳給小組，讓他們能根據組織範圍內的自訂應用程式設定，將自訂 app 上傳給擁有者的團隊。</span><span class="sxs-lookup"><span data-stu-id="d0b32-126">The user can upload custom apps to teams that allow it and to teams for which they are owners, depending on the org-wide custom app setting.</span></span>
- <span data-ttu-id="d0b32-127">使用者可以將自訂應用程式上傳到個人內容。</span><span class="sxs-lookup"><span data-stu-id="d0b32-127">The user can upload custom apps to the personal context.</span></span> 
- <span data-ttu-id="d0b32-128">根據組織範圍內的自訂應用程式設定，使用者可以與自訂應用程式互動。</span><span class="sxs-lookup"><span data-stu-id="d0b32-128">The user can interact with custom apps, depending on the org-wide custom app setting.</span></span>

<span data-ttu-id="d0b32-129">您可以編輯全域 app 設定原則中的設定，以包含您想要的 app。</span><span class="sxs-lookup"><span data-stu-id="d0b32-129">You can edit the settings in the global app setup policy to include the apps that you want.</span></span> <span data-ttu-id="d0b32-130">如果您想要針對貴組織中不同的使用者群組自訂小組，請建立並指派一或多個自訂應用程式設定原則。</span><span class="sxs-lookup"><span data-stu-id="d0b32-130">If you want to customize Teams for different groups of users in your organization, create and assign one or more custom app setup policies.</span></span>

#### <a name="set-a-user-custom-app-policy"></a><span data-ttu-id="d0b32-131">設定使用者自訂 app 原則</span><span class="sxs-lookup"><span data-stu-id="d0b32-131">Set a user custom app policy</span></span>

1. <span data-ttu-id="d0b32-132">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app** > **設定原則**]。</span><span class="sxs-lookup"><span data-stu-id="d0b32-132">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="d0b32-133">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="d0b32-133">Click **Add**.</span></span>
3. <span data-ttu-id="d0b32-134">開啟或關閉 [**允許上傳自訂應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="d0b32-134">Turn on or turn off **Allow uploading custom apps**.</span></span>
4. <span data-ttu-id="d0b32-135">選擇您想要用於原則的任何其他設定。</span><span class="sxs-lookup"><span data-stu-id="d0b32-135">Choose any other settings that you want to for the policy.</span></span>
5. <span data-ttu-id="d0b32-136">按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="d0b32-136">Click **Save**.</span></span>

### <a name="team-custom-app-setting"></a><span data-ttu-id="d0b32-137">團隊自訂應用程式設定</span><span class="sxs-lookup"><span data-stu-id="d0b32-137">Team custom app setting</span></span>

<span data-ttu-id="d0b32-138">系統管理員和小組擁有者可以控制團隊是否允許將自訂應用程式新增到其中。</span><span class="sxs-lookup"><span data-stu-id="d0b32-138">Admins and team owners can control whether a team allows for custom apps to be added to it.</span></span> <span data-ttu-id="d0b32-139">此設定可**讓成員上傳自訂應用程式**，以及使用者的自訂應用程式原則，決定誰可以將自訂應用程式新增至特定團隊。</span><span class="sxs-lookup"><span data-stu-id="d0b32-139">This setting, **Allow members to upload custom apps**, together with a user's custom app policy determines who can add custom apps to a particular team.</span></span>
 
<span data-ttu-id="d0b32-140">如果已關閉此設定：</span><span class="sxs-lookup"><span data-stu-id="d0b32-140">If this setting is turned off:</span></span>

- <span data-ttu-id="d0b32-141">如果他們的自訂 app 原則允許，小組擁有者可以新增自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="d0b32-141">Team owners can add custom apps, if their custom app policy allows it.</span></span>
- <span data-ttu-id="d0b32-142">不是團隊擁有者的小組成員無法將自訂應用程式新增至團隊。</span><span class="sxs-lookup"><span data-stu-id="d0b32-142">Team members who aren't team owners can't add custom apps to the team.</span></span>

<span data-ttu-id="d0b32-143">如果已開啟此設定：</span><span class="sxs-lookup"><span data-stu-id="d0b32-143">If this setting is turned on:</span></span>

- <span data-ttu-id="d0b32-144">小組擁有者可以新增自訂的應用程式（如果他們的自訂應用程式原則允許）。</span><span class="sxs-lookup"><span data-stu-id="d0b32-144">Team owners can add custom apps, if their custom app policy allows for it.</span></span>
- <span data-ttu-id="d0b32-145">不是團隊擁有者的小組成員可以新增自訂應用程式（如果他們的自訂應用程式原則允許）。</span><span class="sxs-lookup"><span data-stu-id="d0b32-145">Team members who aren't team owners can add custom apps, if their custom app policy allows for it.</span></span>

#### <a name="configure-the-team-custom-app-setting"></a><span data-ttu-id="d0b32-146">設定小組自訂應用程式設定</span><span class="sxs-lookup"><span data-stu-id="d0b32-146">Configure the team custom app setting</span></span>

1. <span data-ttu-id="d0b32-147">在 [團隊] 中，移至團隊，按一下 [**更多選項] ̇̇̇** > [**管理團隊**]。</span><span class="sxs-lookup"><span data-stu-id="d0b32-147">In Teams, go to the team, click **More options ˙˙˙** > **Manage team**.</span></span>
2. <span data-ttu-id="d0b32-148">按一下 [**設定**]，然後展開 [**成員許可權**]。</span><span class="sxs-lookup"><span data-stu-id="d0b32-148">Click **Settings**, and then expand **Member permissions**.</span></span>
3. <span data-ttu-id="d0b32-149">選取或清除 [**允許成員上傳自訂應用程式**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d0b32-149">Select or clear the **Allow members to upload custom apps** check box.</span></span>

    ![顯示小組自訂應用程式設定的螢幕擷取畫面](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a><span data-ttu-id="d0b32-151">全組織的自訂應用程式設定</span><span class="sxs-lookup"><span data-stu-id="d0b32-151">Org-wide custom app setting</span></span>

<span data-ttu-id="d0b32-152">組織範圍的自訂應用程式設定，可**讓您與自訂應用程式進行互動**，並將其套用至組織中的所有人，並控制他們是否可以上傳或與自訂 app 互動。</span><span class="sxs-lookup"><span data-stu-id="d0b32-152">The org-wide custom app setting, **Allow interaction with custom apps**, applies to everyone in your organization and governs whether they can upload or interact with custom apps.</span></span> <span data-ttu-id="d0b32-153">此設定會覆寫使用者和團隊的自訂應用程式原則與設定。</span><span class="sxs-lookup"><span data-stu-id="d0b32-153">This setting overrides the user and team custom app policy and setting.</span></span> <span data-ttu-id="d0b32-154">它是用來在安全性事件期間作為主機開啟/關閉切換。</span><span class="sxs-lookup"><span data-stu-id="d0b32-154">It's intended to serve as a master on/off switch during security events.</span></span>

#### <a name="configure-the-org-wide-custom-app-setting"></a><span data-ttu-id="d0b32-155">設定組織範圍的自訂應用程式設定</span><span class="sxs-lookup"><span data-stu-id="d0b32-155">Configure the org-wide custom app setting</span></span>

1. <span data-ttu-id="d0b32-156">在[Microsoft 團隊系統管理中心](https://admin.teams.microsoft.com/)的左導覽中，移至 [**團隊 app** > ]**許可權原則**。</span><span class="sxs-lookup"><span data-stu-id="d0b32-156">In the left navigation of the [Microsoft Teams admin center](https://admin.teams.microsoft.com/), go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="d0b32-157">按一下 [**全組織式應用程式設定**]。</span><span class="sxs-lookup"><span data-stu-id="d0b32-157">Click **Org-wide app settings**.</span></span>
3. <span data-ttu-id="d0b32-158">在 [**自訂應用程式**] 底下，開啟或關閉 [**允許與自訂應用程式互動**]。</span><span class="sxs-lookup"><span data-stu-id="d0b32-158">Under **Custom apps**, turn on or turn off **Allow interaction with custom apps**.</span></span>

    ![顯示組織範圍自訂應用程式設定的螢幕擷取畫面](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a><span data-ttu-id="d0b32-160">自訂 app 原則與設定如何共同運作</span><span class="sxs-lookup"><span data-stu-id="d0b32-160">How custom app policies and settings work together</span></span>

<span data-ttu-id="d0b32-161">下表摘要列出自訂應用程式原則和設定、它們如何共同運作，以及其結合控制哪些人可以將自訂應用程式上傳至團隊的效果。</span><span class="sxs-lookup"><span data-stu-id="d0b32-161">This table summarizes the custom app policy and settings, how they work together, and their combined effect on controlling who in your organization can upload custom apps to Teams.</span></span>

<span data-ttu-id="d0b32-162">例如，您想要只允許團隊擁有者將自訂應用程式上傳到特定團隊。</span><span class="sxs-lookup"><span data-stu-id="d0b32-162">Say, for example, you want to allow only team owners to upload custom apps to specific teams.</span></span> <span data-ttu-id="d0b32-163">您可以設定下列專案：</span><span class="sxs-lookup"><span data-stu-id="d0b32-163">You would set the following:</span></span>
- <span data-ttu-id="d0b32-164">在 Microsoft 團隊系統管理中心開啟 [**允許與自訂應用程式互動**] 設定。</span><span class="sxs-lookup"><span data-stu-id="d0b32-164">Turn on the **Allow interaction with custom apps** setting in the Microsoft Teams admin center.</span></span>
- <span data-ttu-id="d0b32-165">針對您要限制存取權的每個團隊，關閉 [**允許成員上傳自訂應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="d0b32-165">Turn off the **Allow members to upload custom apps** for every team to which you want to restrict access.</span></span>
- <span data-ttu-id="d0b32-166">在 Microsoft 團隊系統管理中心建立並指派自訂的應用程式設定原則，**使用者可以開啟 [自訂應用程式**] 設定，然後將它指派給小組擁有者。</span><span class="sxs-lookup"><span data-stu-id="d0b32-166">Create and assign a custom app setup policy in the Microsoft Teams admin center with the **User can upload custom apps** setting turned on, and assign it to the team owners.</span></span>

|<span data-ttu-id="d0b32-167">全組織的自訂應用程式設定</span><span class="sxs-lookup"><span data-stu-id="d0b32-167">Org-wide custom app setting</span></span> |<span data-ttu-id="d0b32-168">團隊自訂應用程式設定</span><span class="sxs-lookup"><span data-stu-id="d0b32-168">Team custom app setting</span></span> |<span data-ttu-id="d0b32-169">使用者自訂 app 原則</span><span class="sxs-lookup"><span data-stu-id="d0b32-169">User custom app policy</span></span> |<span data-ttu-id="d0b32-170">效果</span><span class="sxs-lookup"><span data-stu-id="d0b32-170">Effect</span></span>  |
|---------|---------|---------|---------|
| <span data-ttu-id="d0b32-171">出</span><span class="sxs-lookup"><span data-stu-id="d0b32-171">Off</span></span>    | <span data-ttu-id="d0b32-172">出</span><span class="sxs-lookup"><span data-stu-id="d0b32-172">Off</span></span>    | <span data-ttu-id="d0b32-173">出</span><span class="sxs-lookup"><span data-stu-id="d0b32-173">Off</span></span>     |<span data-ttu-id="d0b32-174">您的組織已封鎖與所有自訂應用程式的互動。</span><span class="sxs-lookup"><span data-stu-id="d0b32-174">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="d0b32-175">任何人都無法上傳自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="d0b32-175">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="d0b32-176">您可以使用 PowerShell 來移除自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="d0b32-176">You can use PowerShell to remove the custom app.</span></span>   |
| <span data-ttu-id="d0b32-177">出</span><span class="sxs-lookup"><span data-stu-id="d0b32-177">Off</span></span>     | <span data-ttu-id="d0b32-178">出</span><span class="sxs-lookup"><span data-stu-id="d0b32-178">Off</span></span>     | <span data-ttu-id="d0b32-179">按</span><span class="sxs-lookup"><span data-stu-id="d0b32-179">On</span></span>        |<span data-ttu-id="d0b32-180">您的組織已封鎖與所有自訂應用程式的互動。</span><span class="sxs-lookup"><span data-stu-id="d0b32-180">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="d0b32-181">任何人都無法上傳自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="d0b32-181">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="d0b32-182">您可以使用 PowerShell 來移除自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="d0b32-182">You can use PowerShell to remove the custom app.</span></span>         |
| <span data-ttu-id="d0b32-183">出</span><span class="sxs-lookup"><span data-stu-id="d0b32-183">Off</span></span>    | <span data-ttu-id="d0b32-184">按</span><span class="sxs-lookup"><span data-stu-id="d0b32-184">On</span></span>        | <span data-ttu-id="d0b32-185">出</span><span class="sxs-lookup"><span data-stu-id="d0b32-185">Off</span></span>        |<span data-ttu-id="d0b32-186">您的組織已封鎖與所有自訂應用程式的互動。</span><span class="sxs-lookup"><span data-stu-id="d0b32-186">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="d0b32-187">任何人都無法上傳自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="d0b32-187">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="d0b32-188">您可以使用 Windows PowerShell 來刪除自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="d0b32-188">You can use Windows PowerShell to delete custom apps.</span></span>         |
| <span data-ttu-id="d0b32-189">出</span><span class="sxs-lookup"><span data-stu-id="d0b32-189">Off</span></span>    | <span data-ttu-id="d0b32-190">按</span><span class="sxs-lookup"><span data-stu-id="d0b32-190">On</span></span>      | <span data-ttu-id="d0b32-191">按</span><span class="sxs-lookup"><span data-stu-id="d0b32-191">On</span></span>       |<span data-ttu-id="d0b32-192">您的組織已封鎖與所有自訂應用程式的互動。</span><span class="sxs-lookup"><span data-stu-id="d0b32-192">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="d0b32-193">任何人都無法上傳自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="d0b32-193">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="d0b32-194">您可以使用 PowerShell 來移除自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="d0b32-194">You can use PowerShell to remove the custom app.</span></span>         |
| <span data-ttu-id="d0b32-195">按</span><span class="sxs-lookup"><span data-stu-id="d0b32-195">On</span></span>    | <span data-ttu-id="d0b32-196">出</span><span class="sxs-lookup"><span data-stu-id="d0b32-196">Off</span></span>       | <span data-ttu-id="d0b32-197">出</span><span class="sxs-lookup"><span data-stu-id="d0b32-197">Off</span></span>         |  <span data-ttu-id="d0b32-198">使用者無法上傳自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="d0b32-198">The user can't upload custom apps.</span></span>      |
| <span data-ttu-id="d0b32-199">按</span><span class="sxs-lookup"><span data-stu-id="d0b32-199">On</span></span>     | <span data-ttu-id="d0b32-200">出</span><span class="sxs-lookup"><span data-stu-id="d0b32-200">Off</span></span>       | <span data-ttu-id="d0b32-201">按</span><span class="sxs-lookup"><span data-stu-id="d0b32-201">On</span></span>         | <span data-ttu-id="d0b32-202">如果使用者是團隊擁有者，則可將自訂應用程式上傳至團隊。</span><span class="sxs-lookup"><span data-stu-id="d0b32-202">If the user is a team owner, they can upload custom apps to the team.</span></span> <span data-ttu-id="d0b32-203">如果使用者不是團隊擁有者，則他們無法將自訂應用程式上傳至團隊。</span><span class="sxs-lookup"><span data-stu-id="d0b32-203">If the user isn't a team owner, they can't upload custom apps to the team.</span></span> <span data-ttu-id="d0b32-204">使用者可以在個人內容中上傳自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="d0b32-204">The user can upload custom apps in the personal context.</span></span>     |
| <span data-ttu-id="d0b32-205">按</span><span class="sxs-lookup"><span data-stu-id="d0b32-205">On</span></span>     | <span data-ttu-id="d0b32-206">按</span><span class="sxs-lookup"><span data-stu-id="d0b32-206">On</span></span>     | <span data-ttu-id="d0b32-207">出</span><span class="sxs-lookup"><span data-stu-id="d0b32-207">Off</span></span>         | <span data-ttu-id="d0b32-208">使用者無法上傳自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="d0b32-208">The user can't upload custom apps.</span></span>       |
| <span data-ttu-id="d0b32-209">按</span><span class="sxs-lookup"><span data-stu-id="d0b32-209">On</span></span>    | <span data-ttu-id="d0b32-210">按</span><span class="sxs-lookup"><span data-stu-id="d0b32-210">On</span></span>        | <span data-ttu-id="d0b32-211">按</span><span class="sxs-lookup"><span data-stu-id="d0b32-211">On</span></span>        | <span data-ttu-id="d0b32-212">無論使用者是否為小組擁有者，使用者都可以將自訂應用程式上傳至團隊。</span><span class="sxs-lookup"><span data-stu-id="d0b32-212">The user can upload custom apps to the team, regardless of whether the user is a team owner.</span></span> <span data-ttu-id="d0b32-213">使用者可以在個人內容中上傳自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="d0b32-213">The user can upload custom apps in the personal context.</span></span>       |

 ## <a name="related-topics"></a><span data-ttu-id="d0b32-214">相關主題</span><span class="sxs-lookup"><span data-stu-id="d0b32-214">Related topics</span></span>
- [<span data-ttu-id="d0b32-215">在 Teams 中的應用程式系統管理設定</span><span class="sxs-lookup"><span data-stu-id="d0b32-215">Admin settings for apps in Teams</span></span>](admin-settings.md)
