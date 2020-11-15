---
title: Microsoft Teams 中的聊天、團隊、頻道和應用程式
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 包含逐步指導，以在 Microsoft Teams 中為聊天、團隊、應用程式和頻道設定 Teams 設定。
localization_priority: Priority
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.quickstartteamsadmin
appliesto:
- Microsoft Teams
- seo-marvel-apr2020
- seo-marvel-may2020
ms.openlocfilehash: cefcb240e27f5934538c88f5316181be25f24a60
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031229"
---
# <a name="chat-teams-channels--apps-in-microsoft-teams"></a><span data-ttu-id="3c1a5-103">Microsoft Teams 中的聊天、團隊、頻道和應用程式</span><span class="sxs-lookup"><span data-stu-id="3c1a5-103">Chat, teams, channels, & apps in Microsoft Teams</span></span>

<span data-ttu-id="3c1a5-p101">Teams 為您的組織提供絕佳的現成共同作業體驗，而大部分組織認為預設設定就能滿足其需求。本文可協助您決定是否要根據組織的設定檔和商務需求來變更任何預設設定，並逐步引導您完成每個變更。我們已將設定分割成兩個群組，從[您最可能進行的變更](#core-deployment-decisions)的核心集開始。根據組織的需求，第二個群組包括您可能想要設定的[其他設定](#additional-deployment-decisions)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-p101">Teams provides a great out-of-the-box collaboration experience for your organization, and most organizations find that the default settings work for them. This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change. We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions). The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

<span data-ttu-id="3c1a5-108">若要開始使用，請觀看我們簡短的 Teams 聊天、團隊和頻道影片 (4 分 30 秒)：</span><span class="sxs-lookup"><span data-stu-id="3c1a5-108">To get started, watch our short Teams chat, teams, and channels video (4:30 minutes):</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE476Yj]

<span data-ttu-id="3c1a5-109">*2019 年 11 月的新增功能*</span><span class="sxs-lookup"><span data-stu-id="3c1a5-109">*New in November 2019*</span></span>
 - <span data-ttu-id="3c1a5-p102">您現在可以[使用 Advisor for Teams (預覽) 協助您推出 Microsoft Teams](use-advisor-teams-roll-out.md)。Advisor for Teams (預覽) 會引導您完成 Teams 的推出。在您成功推出 Teams 前，它會評估您的 Microsoft 365 或 Office 365 環境，找出可能需要更新或修改的最常用設定。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-p102">You can now [use Advisor for Teams (preview) to help you roll out Microsoft Teams](use-advisor-teams-roll-out.md). Advisor for Teams (preview) walks you through your Teams rollout. It assesses your Microsoft 365 or Office 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.</span></span>
 - <span data-ttu-id="3c1a5-113">[適用於 IT 的 Microsoft Teams 基本資訊 YouTube 頻道](https://aka.ms/MicrosoftTeamsforIT)，包括簡短 (8-10 分鐘) 影片，其中說明如何推出、設定及管理 Teams。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-113">[Microsoft Teams Essentials for IT YouTube channel](https://aka.ms/MicrosoftTeamsforIT), including short (8-10 minute) videos that show you how to roll out, configure, and manage Teams.</span></span>

> [!TIP]
> <span data-ttu-id="3c1a5-p103">建議您在您的 Teams 初始推出中包含我們的精選應用程式，例如 Planner。在開始推動 Teams 的採用時，則新增其他[應用程式、Bot 和連接器](deploy-apps-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-p103">We recommend that you include our featured apps -- such as Planner -- in your initial Teams rollout. Add other [apps, bots, and connectors](deploy-apps-microsoft-teams-landing-page.md) as you drive Teams adoption.</span></span>

 > [!Note]
 > <span data-ttu-id="3c1a5-116">如需有關不同平台上 Teams 功能的詳細資訊，請參閱[依平台的 Teams 功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-116">For details about Teams features on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="chat-deployment-prerequisites"></a><span data-ttu-id="3c1a5-117">聊天部署先決條件</span><span class="sxs-lookup"><span data-stu-id="3c1a5-117">Chat deployment prerequisites</span></span>

<span data-ttu-id="3c1a5-p104">在您的組織中推出 Teams 之前，請先用點時間確認您的環境已針對 Teams 備妥。請參閱[針對 Teams 準備組織的網路](prepare-network.md)，並對您的環境進行任何必要的變更。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-p104">Before you roll out Teams across your organization, take time to confirm that your environment is ready for Teams. Review [Prepare your organization's network for Teams](prepare-network.md) and make any required changes to your environment.</span></span>

|<span data-ttu-id="3c1a5-120">問問自己</span><span class="sxs-lookup"><span data-stu-id="3c1a5-120">Ask yourself</span></span>|<span data-ttu-id="3c1a5-121">動作</span><span class="sxs-lookup"><span data-stu-id="3c1a5-121">Action</span></span> |
|------------|-------|
|<span data-ttu-id="3c1a5-122">我的組織是否已準備好要推出 Teams？</span><span class="sxs-lookup"><span data-stu-id="3c1a5-122">Is my organization ready to roll out Teams?</span></span>|<span data-ttu-id="3c1a5-123">若要回答此問題，請參閱：</span><span class="sxs-lookup"><span data-stu-id="3c1a5-123">To answer this question, see:</span></span> <ul><li>[<span data-ttu-id="3c1a5-124">針對 Teams 準備組織的網路</span><span class="sxs-lookup"><span data-stu-id="3c1a5-124">Prepare your organization's network for Teams</span></span>](prepare-network.md)</li><li>[<span data-ttu-id="3c1a5-125">URL 和 IP 位址範圍</span><span class="sxs-lookup"><span data-stu-id="3c1a5-125">URLs and IP address ranges</span></span>](office-365-urls-ip-address-ranges.md)</li><li>[<span data-ttu-id="3c1a5-126">在建立團隊時規劃 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="3c1a5-126">Plan for Microsoft 365 Groups when creating teams</span></span>](plan-office-365-groups.md)</li></ul>|
|||

## <a name="core-deployment-decisions"></a><span data-ttu-id="3c1a5-127">核心部署決策</span><span class="sxs-lookup"><span data-stu-id="3c1a5-127">Core deployment decisions</span></span>

<span data-ttu-id="3c1a5-128">這些是大部分組織想要變更的聊天、團隊和頻道設定 (如果預設設定不符合他們的需求)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-128">These are the chat, teams, and channels settings that most organizations want to change (if the default settings don't work for them).</span></span>

### <a name="teams-administrators"></a><span data-ttu-id="3c1a5-129">Teams 系統管理員</span><span class="sxs-lookup"><span data-stu-id="3c1a5-129">Teams administrators</span></span>

<span data-ttu-id="3c1a5-p105">Teams 提供了一組自訂管理員角色，可用來為組織管理 Teams。這些角色為系統管理員提供了多種能力。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-p105">Teams provides a set of custom administrator roles that can be used to manage Teams for your organization. The roles provide various capabilities to administrators.</span></span>

| <span data-ttu-id="3c1a5-132">問問自己</span><span class="sxs-lookup"><span data-stu-id="3c1a5-132">Ask yourself</span></span> | <span data-ttu-id="3c1a5-133">動作</span><span class="sxs-lookup"><span data-stu-id="3c1a5-133">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="3c1a5-134">誰將獲指派 Teams 通訊系統管理員角色？</span><span class="sxs-lookup"><span data-stu-id="3c1a5-134">Who will be assigned the Teams Communications Administrator role?</span></span>|<span data-ttu-id="3c1a5-135">若要深入了解 Teams 系統管理員角色，請參閱[使用 Microsoft Teams 系統管理員角色管理來管理 Teams](using-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-135">To learn more about Teams administrator roles see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span>|
|<span data-ttu-id="3c1a5-136">誰將獲指派 Teams 通訊支援工程師角色？</span><span class="sxs-lookup"><span data-stu-id="3c1a5-136">Who will be assigned the Teams Communications Support Engineer role?</span></span>|<span data-ttu-id="3c1a5-137">若要指派系統管理員角色，[使用 Azure Active Directory 將系統管理員和非系統管理員角色指派給使用者](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-137">To assign admin roles, see [Assign administrator and non-administrator roles to users with Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span>|
|<span data-ttu-id="3c1a5-138">誰將獲指派 Teams 通訊支援專員角色？</span><span class="sxs-lookup"><span data-stu-id="3c1a5-138">Who will be assigned the Teams Communications Support Specialist role?</span></span>||
|||

### <a name="teams-owners-and-members"></a><span data-ttu-id="3c1a5-139">Teams 擁有者和成員</span><span class="sxs-lookup"><span data-stu-id="3c1a5-139">Teams owners and members</span></span>

<span data-ttu-id="3c1a5-p106">除了系統管理員角色，Teams 還能讓您指派擁有者和成員使用者角色，並選擇性地賦與他們仲裁者功能 (如果已設定仲裁)，以控制誰可以在頻道內執行特定動作。仲裁可讓您控制誰可以在頻道中開始新的文章、以仲裁者身分新增和移除團隊人員，以及控制團隊成員是否可以回覆現有的頻道訊息。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-p106">In addition to administrator roles, Teams lets you assign owner and member user roles, and selectively give them moderator capabilities (if moderation has been set up) to control who can perform certain actions within a channel. Moderation allows you to control who can start new posts in a channel, add and remove team members as moderators, and control whether team members can reply to existing channel messages.</span></span>

|<span data-ttu-id="3c1a5-142">問問自己</span><span class="sxs-lookup"><span data-stu-id="3c1a5-142">Ask yourself</span></span>|<span data-ttu-id="3c1a5-143">動作</span><span class="sxs-lookup"><span data-stu-id="3c1a5-143">Action</span></span> |
|------------|-------|
|<span data-ttu-id="3c1a5-144">應該對每個角色指派誰？</span><span class="sxs-lookup"><span data-stu-id="3c1a5-144">Who should be assigned to each role?</span></span> | <span data-ttu-id="3c1a5-145">若要比較每個角色的功能，請參閱[在 Microsoft Teams 中指派團隊擁有者、仲裁者和成員](assign-roles-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-145">To compare the capabilities of each role, see [Assign team owners, moderators, and members in Microsoft Teams](assign-roles-permissions.md).</span></span>
|<span data-ttu-id="3c1a5-146">如何指派使用者角色？</span><span class="sxs-lookup"><span data-stu-id="3c1a5-146">How do I assign a user role?</span></span> | <span data-ttu-id="3c1a5-147">若要指派或變更角色，請參閱[指派使用者角色](assign-roles-permissions.md#assign-a-user-role)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-147">To assign or change a role, see [Assign a user role](assign-roles-permissions.md#assign-a-user-role).</span></span>
|<span data-ttu-id="3c1a5-148">我需要控制誰可以在頻道中貼文及回覆嗎？</span><span class="sxs-lookup"><span data-stu-id="3c1a5-148">Do I need to control who can post and reply in a channel?</span></span> | <span data-ttu-id="3c1a5-149">若要設定仲裁，請參閱[在 Microsoft Teams 中設定和管理頻道仲裁](manage-channel-moderation-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-149">To configure moderation, see [Set up and manage channel moderation in Microsoft Teams](manage-channel-moderation-in-teams.md).</span></span>

### <a name="messaging-policies"></a><span data-ttu-id="3c1a5-150">訊息原則</span><span class="sxs-lookup"><span data-stu-id="3c1a5-150">Messaging policies</span></span>

<span data-ttu-id="3c1a5-p107">管理原則可控制 Teams 中的使用者可使用的聊天及頻道訊息功能。例如，誰可以編輯和刪除已傳送的郵件、誰可以使用聊天、誰可以在交談中使用 Meme 等等。依預設，使用者會獲指派全域訊息原則，且所有功能都會 **開啟** 。您可以使用預設的全域原則或是為組織中的人員建立一或多個自訂訊息原則。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-p107">Messaging policies control which chat and channel messaging features are available to users in Teams. For example, who can edit and delete sent messages, who can use chat, who can use memes in conversations, and more. By default, users are assigned the global messaging policy and all features are **On**. You can use the default global policy or create one or more custom messaging policies for people in your organization.</span></span> 

|<span data-ttu-id="3c1a5-155">問問自己</span><span class="sxs-lookup"><span data-stu-id="3c1a5-155">Ask yourself</span></span>|<span data-ttu-id="3c1a5-156">動作</span><span class="sxs-lookup"><span data-stu-id="3c1a5-156">Action</span></span> |
|------------|-------|
|<span data-ttu-id="3c1a5-157">我要自訂全域訊息原則嗎？</span><span class="sxs-lookup"><span data-stu-id="3c1a5-157">Will I customize the global messaging policy?</span></span>|<span data-ttu-id="3c1a5-158">如需使用 Microsoft Teams 系統管理中心來變更全域訊息原則或新增原則的相關資訊，請參閱[在 Teams 中管理訊息原則](messaging-policies-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-158">For information about using the Microsoft Teams admin center to change the global messaging policy or add a new policy, see [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>|
|<span data-ttu-id="3c1a5-159">我需要多個訊息原則嗎？</span><span class="sxs-lookup"><span data-stu-id="3c1a5-159">Do I require multiple messaging policies?</span></span>|<span data-ttu-id="3c1a5-160">若要在 PowerShell 中建立並指派訊息原則，請參閱 [PowerShell 指令碼範例 - 建立並指派訊息原則](scripts/powershell-script-teams-messaging-policy-edu.md)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-160">To create and assign a messaging policy in PowerShell, see [PowerShell script sample - Create and assign a messaging policy](scripts/powershell-script-teams-messaging-policy-edu.md).</span></span>|
|<span data-ttu-id="3c1a5-161">我如何判斷哪些使用者群組可以獲得哪個訊息原則？</span><span class="sxs-lookup"><span data-stu-id="3c1a5-161">How will I determine which groups of users get which messaging policy?</span></span>|<span data-ttu-id="3c1a5-162">若要了解 CsTeamsMessagingPolicy Cmdlet，請參閱 [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-162">To learn about the CsTeamsMessagingPolicy cmdlets, see [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps).</span></span>|
||| 

### <a name="external-access"></a><span data-ttu-id="3c1a5-163">外部存取</span><span class="sxs-lookup"><span data-stu-id="3c1a5-163">External access</span></span>

<span data-ttu-id="3c1a5-p108">外部存取 (之前稱為同盟) 可讓您的 Teams 和商務用 Skype 使用者與組織外部的使用者通訊。藉由將此功能開啟並將網域新增到允許清單，您的使用者即能夠與其他網域和組織中的使用者通訊。外部存取與來賓存取的不同在於，整個網域都會獲授與存取權限，而非個人。外部存取依預設為關閉。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-p108">External access (formerly known as federation) lets your Teams and Skype for Business users communicate with users who are outside of your organization. By turning this on and adding domains to the allowed list, your users can communicate with users in other domains and organizations. External access differs from guest access in that an entire domain is given access permission, not an individual. External access is turned off by default.</span></span>

|<span data-ttu-id="3c1a5-168">問問自己</span><span class="sxs-lookup"><span data-stu-id="3c1a5-168">Ask yourself</span></span>|<span data-ttu-id="3c1a5-169">動作</span><span class="sxs-lookup"><span data-stu-id="3c1a5-169">Action</span></span> |
|------------|-------|
|<ul><li><span data-ttu-id="3c1a5-170">我要將組織的外部存取開啟嗎？</span><span class="sxs-lookup"><span data-stu-id="3c1a5-170">Will I turn on external access for my organization?</span></span></li><li><span data-ttu-id="3c1a5-171">如果啟用，我要限制組織可以與其通訊的網域嗎？</span><span class="sxs-lookup"><span data-stu-id="3c1a5-171">If enabled, will I limit which domains my organization can communicate with?</span></span></li></ul> |<br><span data-ttu-id="3c1a5-172">若要開啟外部存取，請參閱[規劃外部存取](manage-external-access.md#plan-for-external-access)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-172">To turn on external access, see [Plan for external access](manage-external-access.md#plan-for-external-access).</span></span>|
|||

### <a name="guest-access"></a><span data-ttu-id="3c1a5-173">來賓存取</span><span class="sxs-lookup"><span data-stu-id="3c1a5-173">Guest access</span></span>

<span data-ttu-id="3c1a5-p109">Teams 中的來賓存取可讓組織外部的人員存取 Teams 和頻道。您可以使用來賓存取設定來控制來賓使用者可以或不能使用的功能。來賓存取依預設為關閉。若要深入了解，請參閱 [Teams 中的來賓存取](https://docs.microsoft.com/microsoftteams/guest-access)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-p109">Guest access in Teams lets individuals outside your organization access teams and channels. You can use the guest access settings to control which features guest users can or can't use. Guest access is turned off by default. To learn more, see [Guest access in Teams](https://docs.microsoft.com/microsoftteams/guest-access).</span></span>

> [!NOTE]
> <span data-ttu-id="3c1a5-178">若要深入了解外部存取和來賓存取，請參閱這裡 - [在 Microsoft Teams 中與其他組織的使用者通訊](communicate-with-users-from-other-organizations.md)</span><span class="sxs-lookup"><span data-stu-id="3c1a5-178">For more on External access and Guest access see here - [Communicate with users from other organizations in Microsoft Teams](communicate-with-users-from-other-organizations.md)</span></span>


|<span data-ttu-id="3c1a5-179">問問自己</span><span class="sxs-lookup"><span data-stu-id="3c1a5-179">Ask yourself</span></span>|<span data-ttu-id="3c1a5-180">動作</span><span class="sxs-lookup"><span data-stu-id="3c1a5-180">Action</span></span> |
|------------|-------|
|<span data-ttu-id="3c1a5-181">我要將組織的來賓存取開啟嗎？</span><span class="sxs-lookup"><span data-stu-id="3c1a5-181">Will I turn on guest access for my organization?</span></span>|<span data-ttu-id="3c1a5-182">若要開啟來賓存取，請參閱[開啟或關閉 Teams 中的來賓存取](set-up-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-182">To turn on guest access, see [Turn on or off guest access in Teams](set-up-guests.md).</span></span>|
|<span data-ttu-id="3c1a5-183">如果啟用，我將會自訂組織中來賓可使用的功能嗎？</span><span class="sxs-lookup"><span data-stu-id="3c1a5-183">If enabled, will I customize the features available to guests in my organization?</span></span>|<span data-ttu-id="3c1a5-184">若要自訂來賓存取功能的可用性，請參閱[在 Teams 中授權來賓存取](teams-dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-184">To customize guest access feature availability, see [Authorize guest access in Teams](teams-dependencies.md).</span></span>|
|||

### <a name="teams-settings"></a><span data-ttu-id="3c1a5-185">Teams 設定</span><span class="sxs-lookup"><span data-stu-id="3c1a5-185">Teams settings</span></span>

<span data-ttu-id="3c1a5-p110">Teams 設定可讓您為團隊設定使用電子郵件整合、雲端儲存選項、組織索引標籤、會議室裝置設定和搜尋範圍等功能。對這些設定進行變更時，設定會套用到組織中的所有團隊。若要深入了解，請參閱 [Teams 設定](enable-features-office-365.md#teams-settings)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-p110">Teams settings let you set up your teams for features such as email integration, cloud storage options, organization tab, meeting room device setup, and search scope. When you make changes to these settings, they apply to all the teams in your organization. To learn more, see [Teams settings](enable-features-office-365.md#teams-settings).</span></span>

|<span data-ttu-id="3c1a5-189">問問自己</span><span class="sxs-lookup"><span data-stu-id="3c1a5-189">Ask yourself</span></span>|<span data-ttu-id="3c1a5-190">動作</span><span class="sxs-lookup"><span data-stu-id="3c1a5-190">Action</span></span> |
|------------|-------|
|<span data-ttu-id="3c1a5-191">我要自訂組織的 Teams 設定嗎？</span><span class="sxs-lookup"><span data-stu-id="3c1a5-191">Will I customize Teams settings for my organization?</span></span> | <span data-ttu-id="3c1a5-192">若要了解 Teams 設定以及如何加以自訂，請參閱 [Teams 設定](enable-features-office-365.md#teams-settings)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-192">To learn about Teams settings and how to customize them, see [Teams settings](enable-features-office-365.md#teams-settings).</span></span>|
|||

### <a name="teams-clients"></a><span data-ttu-id="3c1a5-193">Teams 用戶端</span><span class="sxs-lookup"><span data-stu-id="3c1a5-193">Teams clients</span></span>

<span data-ttu-id="3c1a5-p111">Teams 支援許多用戶端，範圍從網頁、桌面到行動裝置，且預設設定可讓使用者選擇他們想要使用的用戶端。若要深入了解，請參閱[取得 Teams 用戶端](get-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-p111">Teams supports a number of clients from web to desktop to mobile, and the default configuration lets users choose whichever clients they want. To learn more, see [Get clients for Teams](get-clients.md).</span></span>

|<span data-ttu-id="3c1a5-196">問問自己</span><span class="sxs-lookup"><span data-stu-id="3c1a5-196">Ask yourself</span></span>|<span data-ttu-id="3c1a5-197">動作</span><span class="sxs-lookup"><span data-stu-id="3c1a5-197">Action</span></span> |
|------------|-------|
|<span data-ttu-id="3c1a5-198">我要自訂組織的 Teams 用戶端可用性嗎？</span><span class="sxs-lookup"><span data-stu-id="3c1a5-198">Will I customize Teams client availability for my organization?</span></span>|<span data-ttu-id="3c1a5-199">請查看 [Teams 應用程式的硬體需求](hardware-requirements-for-the-teams-app.md)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-199">Check out [Hardware requirements for the Teams app](hardware-requirements-for-the-teams-app.md).</span></span> |
|<span data-ttu-id="3c1a5-200">我要自訂組織的 Teams 用戶端設定嗎？</span><span class="sxs-lookup"><span data-stu-id="3c1a5-200">Will I customize Teams client settings for my organization?</span></span>|<span data-ttu-id="3c1a5-201">了解如何[使用 MSI 安裝 Teams](msi-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-201">Learn how to [Install Teams using MSI](msi-deployment.md).</span></span>|
|||

### <a name="teams-usage-reporting"></a><span data-ttu-id="3c1a5-202">Teams 使用情況報告</span><span class="sxs-lookup"><span data-stu-id="3c1a5-202">Teams usage reporting</span></span>

<span data-ttu-id="3c1a5-p112">全域系統管理員、Teams 服務系統管理員和報告讀取者角色可檢視 Teams 使用情況報告。若要深入了解，請參閱 [Microsoft 365 流量分析](https://docs.microsoft.com/microsoft-365/admin/usage-analytics/usage-analytics)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-p112">The Global Admin, Teams Service Admin, and Reports Readers roles can view Teams usage reports. To learn more, see the [Microsoft 365 usage analytics](https://docs.microsoft.com/microsoft-365/admin/usage-analytics/usage-analytics).</span></span>

|<span data-ttu-id="3c1a5-205">問問自己</span><span class="sxs-lookup"><span data-stu-id="3c1a5-205">Ask yourself</span></span>|<span data-ttu-id="3c1a5-206">動作</span><span class="sxs-lookup"><span data-stu-id="3c1a5-206">Action</span></span> |
|------------|-------|
|<br> <span data-ttu-id="3c1a5-207">誰需要查看 Teams 使用情況報告，以及他們是否具備檢視報告的正確角色？</span><span class="sxs-lookup"><span data-stu-id="3c1a5-207">Who needs to see the Teams usage reports, and do they have the correct role to view them?</span></span> |<ul><li><span data-ttu-id="3c1a5-208">如果使用者不是系統管理員，請[指派報告讀取者角色](teams-activity-reports.md#reports-reader-role)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-208">If the user isn't an admin, [assign the Reports reader role](teams-activity-reports.md#reports-reader-role).</span></span></li><li><span data-ttu-id="3c1a5-209">請參閱[角色和使用權限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)和[檢視和指派角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)來了解如何在 Azure Active Directory 中指派系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-209">See [Roles and permissions](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [View and assign roles](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal) to learn how to assign admin roles in Azure Active Directory.</span></span> |
|||

### <a name="teams-default-apps"></a><span data-ttu-id="3c1a5-210">Teams 預設應用程式</span><span class="sxs-lookup"><span data-stu-id="3c1a5-210">Teams default apps</span></span> 

<span data-ttu-id="3c1a5-p113">Teams 提供大量的第一方 (Microsoft 提供) 和第三方應用程式，用來吸引使用者、支援生產力，並將常用的商務服務整合到 Teams 中。從 Teams 市集取得應用程式。Teams 中的應用程式預設會開啟。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-p113">Teams provides a number of first-party (Microsoft provided) and third-party apps to engage users, support productivity, and integrate commonly used business services into Teams. Get apps from the Teams Store. Apps are turned on by default in Teams.</span></span> 

<span data-ttu-id="3c1a5-214">若要深入了解如何在 Teams 中推出和管理應用程式，請參閱我們深入的[應用程式、Bot 和連接器](deploy-apps-microsoft-teams-landing-page.md)指導方針。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-214">To learn more about rolling out and managing apps in Teams, see our in-depth [Apps, bots, & connectors](deploy-apps-microsoft-teams-landing-page.md) guidance.</span></span>

## <a name="additional-deployment-decisions"></a><span data-ttu-id="3c1a5-215">其他部署決策</span><span class="sxs-lookup"><span data-stu-id="3c1a5-215">Additional deployment decisions</span></span>

<span data-ttu-id="3c1a5-216">根據組織的需求和組態而定，您可能會想要變更這些設定。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-216">You may want to change these settings, based on your organization's needs and configuration.</span></span>

### <a name="teams-licensing"></a><span data-ttu-id="3c1a5-217">Teams 授權</span><span class="sxs-lookup"><span data-stu-id="3c1a5-217">Teams licensing</span></span>

<span data-ttu-id="3c1a5-p114">Teams 會隨著許多 Microsoft 365 或 Office 365 授權提供。若要深入了解 Teams 授權，請參閱 [Microsoft Teams 服務描述](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-p114">Teams is provided as part of many Microsoft 365 or Office 365 licenses. To learn more about Teams licensing, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

|<span data-ttu-id="3c1a5-220">問問自己</span><span class="sxs-lookup"><span data-stu-id="3c1a5-220">Ask yourself</span></span>|<span data-ttu-id="3c1a5-221">動作</span><span class="sxs-lookup"><span data-stu-id="3c1a5-221">Action</span></span> |
|------------|-------|
|<span data-ttu-id="3c1a5-222">我的使用者是否擁有使用我要推出的 Teams 所有功能所需的授權？</span><span class="sxs-lookup"><span data-stu-id="3c1a5-222">Do my users have the licenses they need in order to use all the Teams features I want to roll out?</span></span> | <span data-ttu-id="3c1a5-223">若要深入瞭解授權需求，請參閱 [Microsoft Teams 服務描述](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-223">To learn about licensing requirements, read [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>|
|||

### <a name="exchange-and-sharepoint-interoperability"></a><span data-ttu-id="3c1a5-224">Exchange 和 SharePoint 互通性</span><span class="sxs-lookup"><span data-stu-id="3c1a5-224">Exchange and SharePoint interoperability</span></span>

<span data-ttu-id="3c1a5-p115">為了獲得完整的團隊體驗，每個使用者都應啟用 Exchange Online、SharePoint Online 及 Microsoft 365 群組建立。下列文章概述與各種環境中託管的 Exchange 信箱相關的資訊、Exchange 與 Teams 如何互動，以及 SharePoint 和商務用 OneDrive 的類似考量。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-p115">For the full Teams experience, every user should be enabled for Exchange Online, SharePoint Online, and Microsoft 365 group creation. The following articles outline information related to Exchange mailboxes hosted in various environments, how Exchange and Teams interact, and similar considerations for SharePoint and OneDrive for Business.</span></span>

|<span data-ttu-id="3c1a5-227">問問自己</span><span class="sxs-lookup"><span data-stu-id="3c1a5-227">Ask yourself</span></span>|<span data-ttu-id="3c1a5-228">動作</span><span class="sxs-lookup"><span data-stu-id="3c1a5-228">Action</span></span> |
|------------|-------|
| <span data-ttu-id="3c1a5-229">我是否能部署我目前使用 Exchange 和 SharePoint 部署所需的 Teams 功能？</span><span class="sxs-lookup"><span data-stu-id="3c1a5-229">Will I be able to deploy the Teams features that I require with the current Exchange and SharePoint deployments?</span></span> |<span data-ttu-id="3c1a5-230">如需 Teams 中 Exchange 和 SharePoint 的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="3c1a5-230">For more information about Exchange and SharePoint in Teams, see:</span></span><ul><li> [<span data-ttu-id="3c1a5-231">Exchange 和 Teams 如何互動</span><span class="sxs-lookup"><span data-stu-id="3c1a5-231">How Exchange and Teams interact</span></span>](exchange-teams-interact.md)</li><li>[<span data-ttu-id="3c1a5-232">SharePoint Online 和商務用 OneDrive 如何與 Teams 互動</span><span class="sxs-lookup"><span data-stu-id="3c1a5-232">How SharePoint Online and OneDrive for Business interact with Teams</span></span>](sharepoint-onedrive-interact.md)|
|||

### <a name="teams-limits-and-specifications"></a><span data-ttu-id="3c1a5-233">Teams 的限制和規格</span><span class="sxs-lookup"><span data-stu-id="3c1a5-233">Teams limits and specifications</span></span> 

<span data-ttu-id="3c1a5-234">規劃 Teams 的企業部署時，應考慮任何相關的限制和規格，例如團隊中成員人數的上限、使用者可建立的團隊人數上限等等。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-234">When planning an enterprise deployment of Teams, you should take into account any relevant limitations and specifications, such as the maximum number of members in a team, the maximum number of teams a user can create, and so on.</span></span>

|<span data-ttu-id="3c1a5-235">問問自己</span><span class="sxs-lookup"><span data-stu-id="3c1a5-235">Ask yourself</span></span>|<span data-ttu-id="3c1a5-236">動作</span><span class="sxs-lookup"><span data-stu-id="3c1a5-236">Action</span></span> |
|------------|-------|
| <span data-ttu-id="3c1a5-237">隨著我的 Teams 推出，我可能會有哪些限制？</span><span class="sxs-lookup"><span data-stu-id="3c1a5-237">What limits am I likely to hit with my Teams rollout?</span></span> | <span data-ttu-id="3c1a5-238">若要深入了解，請參閱 [Teams 的限制和規格](limits-specifications-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-238">To learn more, read [Limits and specifications for Teams](limits-specifications-teams.md).</span></span> |
|||

### <a name="urls-and-ports"></a><span data-ttu-id="3c1a5-239">URL 和連接埠</span><span class="sxs-lookup"><span data-stu-id="3c1a5-239">URLs and ports</span></span>

<span data-ttu-id="3c1a5-p116">對網際網路流量保有精細控制的組織，應閱讀 [URL 和 IP 位址範圍](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)，以取得必須為 Teams 正確設定的最新 URL、IP 位址、連接埠和通訊協定的清單。Microsoft 會持續改善 Microsoft 365 及 Office 365 服務並加入新的功能，這表示必要的連接埠、URL 和 IP 位址可能會隨著時間變更。建議您透過 RSS 訂閱，以便在此資訊更新或變更時收到通知。至少，請確認您已開放以上的[聊天部署先決條件](#chat-deployment-prerequisites)中所列的連接埠。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-p116">Organizations that maintain fine-grained control of their internet traffic should read [URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) for an up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams. Microsoft is continuously improving the Microsoft 365 and Office 365 services and adding new functionality, which means the required ports, URLs, and IP addresses may change over time. We recommend that you subscribe via RSS to receive notifications when this information is updated or changed. At a minimum, make sure you've opened the ports listed above in [Chat deployment prerequisites](#chat-deployment-prerequisites).</span></span>

|<span data-ttu-id="3c1a5-244">問問自己</span><span class="sxs-lookup"><span data-stu-id="3c1a5-244">Ask yourself</span></span>|<span data-ttu-id="3c1a5-245">動作</span><span class="sxs-lookup"><span data-stu-id="3c1a5-245">Action</span></span> |
|------------|-------|
| <span data-ttu-id="3c1a5-246">我是否需要網際網路存取規則，才能讓使用者能使用 Teams，或是開放必要的最基本連接埠即已足夠？</span><span class="sxs-lookup"><span data-stu-id="3c1a5-246">Do I require internet access rules to enable users to use Teams, or is it sufficient to open the minimum required ports?</span></span> | <span data-ttu-id="3c1a5-247">若要深入了解，請參閱 [URL 和 IP 位址範圍](office-365-urls-ip-address-ranges.md)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-247">To learn more, see [URLs and IP address ranges](office-365-urls-ip-address-ranges.md).</span></span>|
|||

### <a name="governance-naming-conventions-who-can-create-teams"></a><span data-ttu-id="3c1a5-248">控管 (命名慣例，可建立團隊的人員)</span><span class="sxs-lookup"><span data-stu-id="3c1a5-248">Governance (naming conventions, who can create teams)</span></span>

<span data-ttu-id="3c1a5-p117">您的組織可能會要求您對團隊的命名和分類方式、誰可以建立團隊以及團隊到期日、保留和封存實作控制。這稱為控管。您可以使用 Azure Active Directory (Azure AD) 來設定每一個區域。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-p117">Your organization might require that you implement controls on how teams are named and classified, who can create teams, and team expiration, retention, and archiving. This is called governance. You can use Azure Active Directory (Azure AD) to configure each of these areas.</span></span>


| <span data-ttu-id="3c1a5-252">問問自己</span><span class="sxs-lookup"><span data-stu-id="3c1a5-252">Ask yourself</span></span> | <span data-ttu-id="3c1a5-253">動作</span><span class="sxs-lookup"><span data-stu-id="3c1a5-253">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="3c1a5-254">我是否需要對可以建立團隊的人員實作控制？</span><span class="sxs-lookup"><span data-stu-id="3c1a5-254">Will I need to implement controls on who can create teams?</span></span>| <span data-ttu-id="3c1a5-255">請閱讀[規劃 Teams 中的控管](plan-teams-governance.md)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-255">Read [Plan for governance in Teams](plan-teams-governance.md).</span></span>|
|<span data-ttu-id="3c1a5-256">我是否需要對團隊的命名方式實作控制？</span><span class="sxs-lookup"><span data-stu-id="3c1a5-256">Will I need to implement controls on how teams are named?</span></span>|<span data-ttu-id="3c1a5-257">請閱讀[在 Azure AD 中對 Microsoft 365 群組強制執行命名原則](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-257">Read [Enforce a naming policy for Microsoft 365 groups in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy).</span></span>|
|||

### <a name="teams-application-policy-side-rail-control"></a><span data-ttu-id="3c1a5-258">Teams 應用程式原則 (側邊欄控制)</span><span class="sxs-lookup"><span data-stu-id="3c1a5-258">Teams application policy (side-rail control)</span></span>

<span data-ttu-id="3c1a5-p118">釘選的應用程式會顯示在 Teams 的側邊欄中。透過建立 Teams 應用程式原則，您可以預先設定釘選 Teams 應用程式的集合，以針對選取的使用者群組將 Teams 個人化。[在 Microsoft Teams 中允許外部應用程式 **]** 設定預設為開啟。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-p118">A pinned app shows up in the side rail in Teams. By creating Teams application policies, you can preconfigure sets of pinned Teams apps to personalize Teams for select groups of users. By default, the **Allow external apps in Microsoft Teams** setting is turned on.</span></span>

| <span data-ttu-id="3c1a5-262">問問自己</span><span class="sxs-lookup"><span data-stu-id="3c1a5-262">Ask yourself</span></span> | <span data-ttu-id="3c1a5-263">動作</span><span class="sxs-lookup"><span data-stu-id="3c1a5-263">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="3c1a5-264">我應該建立預先設定的釘選 Teams 應用程式集嗎？</span><span class="sxs-lookup"><span data-stu-id="3c1a5-264">Should I create preconfigured sets of pinned Teams applications?</span></span> | <span data-ttu-id="3c1a5-265">請閱讀[在 Teams 中管理應用程式的設定](admin-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-265">Read [Admin settings for apps in Teams](admin-settings.md).</span></span>|
|<span data-ttu-id="3c1a5-266">我如何決定哪些群組會收到這些應用程式群組？</span><span class="sxs-lookup"><span data-stu-id="3c1a5-266">How will I decide which groups receive these app groupings?</span></span>|<span data-ttu-id="3c1a5-267">請閱讀 [Teams 應用程式權限和考量](app-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-267">Read [Teams apps permissions and considerations](app-permissions.md).</span></span>|
|||

### <a name="archiving-and-compliance"></a><span data-ttu-id="3c1a5-268">封存與合規性</span><span class="sxs-lookup"><span data-stu-id="3c1a5-268">Archiving and compliance</span></span> 

<span data-ttu-id="3c1a5-p119">您的組織可能會要求您對團隊的封存方式以及在特定團隊類型中保留的資料類型採取控制措施。請閱讀 [Teams 的安全性與合規性概觀](security-compliance-overview.md)，以了解預設會開啟哪些 Teams 設定。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-p119">Your organization might require that you implement controls on how teams are archived and the types of data that are held in certain types of teams. Read [Overview of security and compliance in Teams](security-compliance-overview.md) to learn which Teams settings are turned on by default.</span></span>

| <span data-ttu-id="3c1a5-271">問問自己</span><span class="sxs-lookup"><span data-stu-id="3c1a5-271">Ask yourself</span></span> | <span data-ttu-id="3c1a5-272">動作</span><span class="sxs-lookup"><span data-stu-id="3c1a5-272">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="3c1a5-273">我需要設定團隊保留嗎？</span><span class="sxs-lookup"><span data-stu-id="3c1a5-273">Will I need to configure team retention?</span></span>|<span data-ttu-id="3c1a5-274">若要設定保留原則，請參閱[設定 Teams 保留原則](retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-274">To set up retention policies, see [Set up Teams retention policies](retention-policies.md).</span></span>|
|<span data-ttu-id="3c1a5-275">我需要設定團隊封存嗎？</span><span class="sxs-lookup"><span data-stu-id="3c1a5-275">Will I need to configure team archiving?</span></span>|<span data-ttu-id="3c1a5-276">若要封存或還原團隊，請參閱[封存或還原團隊](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-276">To archive or restore a team, see [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>|
|<span data-ttu-id="3c1a5-277">我需要設定額外的合規性設定嗎？</span><span class="sxs-lookup"><span data-stu-id="3c1a5-277">Will I need to configure additional compliance settings?</span></span>|<span data-ttu-id="3c1a5-278">如需安全性和合規性的詳細資訊，請參閱 [Teams 的安全性與合規性概觀](security-compliance-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-278">For more information about security and compliance, see [Overview of security and compliance in Teams](security-compliance-overview.md).</span></span>|
|||

### <a name="conditional-access"></a><span data-ttu-id="3c1a5-279">條件式存取</span><span class="sxs-lookup"><span data-stu-id="3c1a5-279">Conditional access</span></span> 

<span data-ttu-id="3c1a5-p120">針對包括會議、行事曆、交互操作聊天和檔案共用在內的核心生產力案例中，Teams 極為依賴 Exchange Online、SharePoint Online 及商務用 Skype Online。當使用者在任何用戶端上直接登入 Teams 時，對這些雲端應用程式設定的條件式存取原則會套用至 Teams。為 Teams 雲端應用程式控制方面設定的條件式存取原則，例如，使用者是否可以從特定網路存取 Teams 服務。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-p120">Teams relies heavily on Exchange Online, SharePoint Online, and Skype for Business Online for core productivity scenarios, including meetings, calendars, interop chats, and file sharing. Conditional access policies that are set for these cloud apps apply to Teams when a user signs in directly to Teams, on any client. Conditional access policies that are set for the Teams cloud app control aspects such as whether users can access Teams services from certain networks.</span></span>

| <span data-ttu-id="3c1a5-283">問問自己</span><span class="sxs-lookup"><span data-stu-id="3c1a5-283">Ask yourself</span></span> | <span data-ttu-id="3c1a5-284">動作</span><span class="sxs-lookup"><span data-stu-id="3c1a5-284">Action</span></span> |
|--------------|--------|
|<br><span data-ttu-id="3c1a5-285">我需要為 Teams 設定條件式存取嗎？</span><span class="sxs-lookup"><span data-stu-id="3c1a5-285">Will I need to configure conditional access for Teams?</span></span>|<ul><li><span data-ttu-id="3c1a5-286">若要了解存取原則的運作方式，請參閱[條件式存取原則如何適合 Teams？](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)</span><span class="sxs-lookup"><span data-stu-id="3c1a5-286">To understand how access policies work, see [How do conditional access policies work for Teams?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)</span></span></li><li><span data-ttu-id="3c1a5-287">若要為 Teams 設定多重要素驗證 (MFA)，請參閱：</span><span class="sxs-lookup"><span data-stu-id="3c1a5-287">To set up multi-factor authentication (MFA) for Teams, see:</span></span><ul><li>[<span data-ttu-id="3c1a5-288">快速入門：透過 Azure Active Directory 條件式存取來要求特定應用程式需要 MFA</span><span class="sxs-lookup"><span data-stu-id="3c1a5-288">Quickstart: Require MFA for specific apps with Azure Active Directory conditional access</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-mfa)</li><li>[<span data-ttu-id="3c1a5-289">Azure Active Directory 條件式存取設定參考</span><span class="sxs-lookup"><span data-stu-id="3c1a5-289">Azure Active Directory conditional access settings reference</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference)</li></ul></ul>|
|||


### <a name="education-edu"></a><span data-ttu-id="3c1a5-290">教育版 (EDU)</span><span class="sxs-lookup"><span data-stu-id="3c1a5-290">Education (EDU)</span></span> 

<span data-ttu-id="3c1a5-291">在教育單位工作的 IT 專業人員可以利用教育版 Teams，該版本提供許多專為與學生、教職員和更廣泛企業的教育特定案例而量身打造的功能。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-291">IT pros working in education can take advantage of Teams for Education, which comes with a number of capabilities that have been tailored to meet education-specific scenarios for students, faculty, and the wider business.</span></span>

| <span data-ttu-id="3c1a5-292">問問自己</span><span class="sxs-lookup"><span data-stu-id="3c1a5-292">Ask yourself</span></span> | <span data-ttu-id="3c1a5-293">動作</span><span class="sxs-lookup"><span data-stu-id="3c1a5-293">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="3c1a5-294">我要使用教育版特定的 Teams 範本嗎？</span><span class="sxs-lookup"><span data-stu-id="3c1a5-294">Will I use EDU-specific Teams templates?</span></span> |<span data-ttu-id="3c1a5-295">若要深入了解教育版 Teams，請參閱[系統管理員的 Microsoft 教育控管常見問題集](plan-teams-governance-edu.md)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-295">To learn more about Teams for Education, see [Microsoft Education governance FAQ for admins](plan-teams-governance-edu.md).</span></span>|
|<span data-ttu-id="3c1a5-296">我將部署限定範圍搜尋嗎？</span><span class="sxs-lookup"><span data-stu-id="3c1a5-296">Will I deploy scoped search?</span></span>|<span data-ttu-id="3c1a5-297">若要設定 Teams 教育版，請參閱[快速入門 - Teams 教育版系統管理員](teams-quick-start-edu.yml)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-297">To set up Teams for EDU, see [Quickstart - Teams for Education admins](teams-quick-start-edu.yml).</span></span>|
|<span data-ttu-id="3c1a5-298">我要將 Teams 與學校資料同步處理服務整合，以佈建使用者帳戶嗎？</span><span class="sxs-lookup"><span data-stu-id="3c1a5-298">Will I integrate Teams with the School Data Sync service to provision user accounts?</span></span>|[<span data-ttu-id="3c1a5-299">Teams 教育版管理員的資源</span><span class="sxs-lookup"><span data-stu-id="3c1a5-299">Teams resources for Education admins</span></span>](resources-teams-edu.md)|
|||

### <a name="government---gcc-considerations"></a><span data-ttu-id="3c1a5-300">政府版 - GCC 考量</span><span class="sxs-lookup"><span data-stu-id="3c1a5-300">Government - GCC considerations</span></span>

<span data-ttu-id="3c1a5-301">Office 365 政府版 - GCC (政府社群雲端) 適合用來滿足在美國聯邦、州、當地、部落或特區政府實體推動 Office 365 部署或處理受限於政府法規和需求的其他實體 IT 專業人員的需求。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-301">The use of Office 365 for Government - GCC (Government Community Cloud) is appropriate to meet the requirements of IT pros who are driving deployments of Office 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that's subject to government regulations and requirements.</span></span>

| <span data-ttu-id="3c1a5-302">問問自己</span><span class="sxs-lookup"><span data-stu-id="3c1a5-302">Ask yourself</span></span> | <span data-ttu-id="3c1a5-303">動作</span><span class="sxs-lookup"><span data-stu-id="3c1a5-303">Action</span></span> |
|--------------|--------|
| <span data-ttu-id="3c1a5-304">我需要在 Office 365 政府版 (GCC 環境) 中部署 Teams 嗎？</span><span class="sxs-lookup"><span data-stu-id="3c1a5-304">Will I need to deploy Teams in a Office 365 for Government – GCC environment?</span></span> | <span data-ttu-id="3c1a5-305">如需部署考量，請參閱[規劃 Office 365 政府版 - GCC 部署](plan-for-government-gcc.md)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-305">For deployment considerations, see [Plan for Office 365 Government - GCC deployments](plan-for-government-gcc.md).</span></span>|
|||

## <a name="next-steps"></a><span data-ttu-id="3c1a5-306">後續步驟</span><span class="sxs-lookup"><span data-stu-id="3c1a5-306">Next steps</span></span>
- <span data-ttu-id="3c1a5-307">聊天、團隊、頻道和應用程式的[推動採用](adopt-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-307">[Drive adoption](adopt-microsoft-teams-landing-page.md) of chat, teams, channels, & apps.</span></span>
- <span data-ttu-id="3c1a5-p121">在您的 Teams 初始推出中包含精選應用程式，例如 Planner。在開始推動 Teams 的採用時，則新增其他[應用程式、Bot 和連接器](deploy-apps-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-p121">Include featured apps - such as Planner - in your initial Teams rollout. Add other [apps, bots, & connectors](deploy-apps-microsoft-teams-landing-page.md) as you drive Teams adoption.</span></span>
- [<span data-ttu-id="3c1a5-310">推出會議和研討會</span><span class="sxs-lookup"><span data-stu-id="3c1a5-310">Roll out meetings & conferencing</span></span>](deploy-meetings-microsoft-teams-landing-page.md)
- [<span data-ttu-id="3c1a5-311">推出雲端語音</span><span class="sxs-lookup"><span data-stu-id="3c1a5-311">Roll out cloud voice</span></span>](cloud-voice-landing-page.md)
