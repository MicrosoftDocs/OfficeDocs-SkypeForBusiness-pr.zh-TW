---
title: Microsoft Teams 中的聊天、團隊、頻道和應用程式
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 在 Microsoft Teams 中推出聊天、團隊、頻道和應用程式的逐步指引
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.quickstartteamsadmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2acb9d1734bb04c4db522417064c3d99fd660d89
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863214"
---
# <a name="chat-teams-channels--apps-in-microsoft-teams"></a><span data-ttu-id="49585-103">Microsoft Teams 中的聊天、團隊、頻道和應用程式</span><span class="sxs-lookup"><span data-stu-id="49585-103">Chat, teams, channels, & apps in Microsoft Teams</span></span>

<span data-ttu-id="49585-104">Teams 為您的組織提供絕佳的現成共同作業體驗，而大部分組織認為預設設定就能滿足其需求。</span><span class="sxs-lookup"><span data-stu-id="49585-104">Teams provides a great out-of-the-box collaboration experience for your organization, and most organizations find that the default settings work for them.</span></span> <span data-ttu-id="49585-105">本文可協助您決定是否要根據組織的設定檔和商務需求來變更任何預設設定，並逐步引導您完成每個變更。</span><span class="sxs-lookup"><span data-stu-id="49585-105">This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="49585-106">我們已將設定分割成兩個群組，從[您最可能進行的變更](#core-deployment-decisions)的核心集開始。</span><span class="sxs-lookup"><span data-stu-id="49585-106">We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="49585-107">根據組織的需求，第二個群組包括您可能想要設定的[其他設定](#additional-deployment-decisions)。</span><span class="sxs-lookup"><span data-stu-id="49585-107">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span> 

<span data-ttu-id="49585-108">若要開始使用，請觀看我們的簡短 Teams 聊天、團隊和頻道影片 (4 分 30 秒)：</span><span class="sxs-lookup"><span data-stu-id="49585-108">To get started, watch our short Teams chat, teams, and channels video (4:30 minutes):</span></span> 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE476Yj]

<span data-ttu-id="49585-109">*2019 年 11 月的新增功能*</span><span class="sxs-lookup"><span data-stu-id="49585-109">*New in November 2019*</span></span>
 - <span data-ttu-id="49585-110">您現在可以使用 [Advisor for Teams (預覽) 協助您推出 Microsoft Teams](use-advisor-teams-roll-out.md)。</span><span class="sxs-lookup"><span data-stu-id="49585-110">You can now [use Advisor for Teams (preview) to help you roll out Microsoft Teams](use-advisor-teams-roll-out.md).</span></span> <span data-ttu-id="49585-111">Advisor for Teams (預覽) 會引導您完成 Teams 的推出。</span><span class="sxs-lookup"><span data-stu-id="49585-111">Advisor for Teams (preview) walks you through your Teams rollout.</span></span> <span data-ttu-id="49585-112">在您成功推出 Teams 前，它會評估您的 Office 365 環境，找出可能需要更新或修改的最常用設定。</span><span class="sxs-lookup"><span data-stu-id="49585-112">It assesses your Office 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.</span></span>
 - <span data-ttu-id="49585-113">[適用於 IT YouTube 頻道的 Microsoft Teams 基本版](https://aka.ms/MicrosoftTeamsforIT)，包括告訴您如何推出、設定及管理 Teams 的簡短 (8-10 分鐘) 影片。</span><span class="sxs-lookup"><span data-stu-id="49585-113">[Microsoft Teams Essentials for IT YouTube channel](https://aka.ms/MicrosoftTeamsforIT), including short (8-10 minute) videos that show you how to roll out, configure, and manage Teams.</span></span>

> [!TIP]
> <span data-ttu-id="49585-114">建議您初始推出 Teams 時能夠包含我們的精選應用程式，例如 Planner。</span><span class="sxs-lookup"><span data-stu-id="49585-114">We recommend that you include our featured apps-such as Planner-in your initial Teams rollout.</span></span> <span data-ttu-id="49585-115">在開始推動 Teams 的採用時，則新增其他[應用程式、Bot 和連接器](deploy-apps-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="49585-115">Add other [apps, bots, and connectors](deploy-apps-microsoft-teams-landing-page.md) as you drive Teams adoption.</span></span>

## <a name="chat-deployment-prerequisites"></a><span data-ttu-id="49585-116">聊天部署必要條件</span><span class="sxs-lookup"><span data-stu-id="49585-116">Chat deployment prerequisites</span></span>

<span data-ttu-id="49585-117">在您的組織中推出 Teams 之前，請先用點時間確認您的環境已針對 Teams 備妥。</span><span class="sxs-lookup"><span data-stu-id="49585-117">Before you roll out Teams across your organization, take time to confirm that your environment is ready for Teams.</span></span> <span data-ttu-id="49585-118">請檢閱下列資訊，並對您的環境進行任何必要的變更。</span><span class="sxs-lookup"><span data-stu-id="49585-118">Review the following information and make any required changes to your environment.</span></span>

- <span data-ttu-id="49585-119">若要獲得完整的 Teams 體驗，組織必須已部署 [Exchange Online 和 SharePoint Online](#exchange-and-sharepoint-interoperability)，並且必須具有 Office 365 經驗證的網域 (例如 contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="49585-119">To get the full Teams experience, your organization must have deployed [Exchange Online and SharePoint Online](#exchange-and-sharepoint-interoperability), and you must have a verified domain for Office 365 (for example, contoso.com).</span></span>

- <span data-ttu-id="49585-120">若要在整個組織中擴展聊天、團隊和頻道，請確認所有位置都擁有網際網路存取，使得它們能夠連線到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="49585-120">To scale chat, teams, and channels across your organization, make sure all locations have internet access so they can connect to Office 365.</span></span> <span data-ttu-id="49585-121">請至少確保已從所有位置將下列常見連接埠對網際網路開放：</span><span class="sxs-lookup"><span data-stu-id="49585-121">At a minimum, make sure that the following common ports are open to the internet from all locations:</span></span>

    - <span data-ttu-id="49585-122">對來自將使用 Teams 用戶端的連出流量開放 **TCP** 連接埠 80 和 443</span><span class="sxs-lookup"><span data-stu-id="49585-122">Open **TCP** ports 80 and 443 for outgoing traffic from clients that will use Teams</span></span>
    - <span data-ttu-id="49585-123">對來自將使用 Teams 用戶端的連出流量開放 **UDP** 連接埠 3478 到3481</span><span class="sxs-lookup"><span data-stu-id="49585-123">Open **UDP** ports 3478 through 3481 for outgoing traffic from clients that will use Teams</span></span>

|<span data-ttu-id="49585-124">問問自己</span><span class="sxs-lookup"><span data-stu-id="49585-124">Ask yourself</span></span>|<span data-ttu-id="49585-125">動作</span><span class="sxs-lookup"><span data-stu-id="49585-125">Action</span></span> |
|------------|-------|
|<span data-ttu-id="49585-126">我的組織是否已準備好要推出 Teams？</span><span class="sxs-lookup"><span data-stu-id="49585-126">Is my organization ready to roll out Teams?</span></span>|<span data-ttu-id="49585-127">若要回答此問題，請參閱：</span><span class="sxs-lookup"><span data-stu-id="49585-127">To answer this question, see:</span></span> <ul><li>[<span data-ttu-id="49585-128">針對 Teams 準備組織的網路</span><span class="sxs-lookup"><span data-stu-id="49585-128">Prepare your organization's network for Teams</span></span>](prepare-network.md)</li><li>[<span data-ttu-id="49585-129">Office 365 URL 與 IP 位址範圍</span><span class="sxs-lookup"><span data-stu-id="49585-129">Office 365 URLs and IP address ranges</span></span>](office-365-urls-ip-address-ranges.md)</li><li>[<span data-ttu-id="49585-130">建立團隊時規劃 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="49585-130">Plan for Office 365 Groups when creating teams</span></span>](plan-office-365-groups.md)</li></ul>|
|||

## <a name="core-deployment-decisions"></a><span data-ttu-id="49585-131">核心部署決策</span><span class="sxs-lookup"><span data-stu-id="49585-131">Core deployment decisions</span></span>

<span data-ttu-id="49585-132">這些是大部分組織想要變更的聊天、團隊和頻道設定 (如果預設設定不符合他們的需求)。</span><span class="sxs-lookup"><span data-stu-id="49585-132">These are the chat, teams, and channels settings that most organizations want to change (if the default settings don't work for them).</span></span>

### <a name="teams-administrators"></a><span data-ttu-id="49585-133">Teams 系統管理員</span><span class="sxs-lookup"><span data-stu-id="49585-133">Teams administrators</span></span>

<span data-ttu-id="49585-134">Teams 提供了一組自訂管理員角色，可用來為組織管理 Teams。</span><span class="sxs-lookup"><span data-stu-id="49585-134">Teams provides a set of custom administrator roles that can be used to manage Teams for your organization.</span></span> <span data-ttu-id="49585-135">這些角色為系統管理員提供各種能力。</span><span class="sxs-lookup"><span data-stu-id="49585-135">The roles provide various capabilities to administrators.</span></span>

| <span data-ttu-id="49585-136">問問自己</span><span class="sxs-lookup"><span data-stu-id="49585-136">Ask yourself</span></span> | <span data-ttu-id="49585-137">動作</span><span class="sxs-lookup"><span data-stu-id="49585-137">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="49585-138">誰將獲指派 Teams 通訊系統管理員角色？</span><span class="sxs-lookup"><span data-stu-id="49585-138">Who will be assigned the Teams Communications Administrator role?</span></span>|<span data-ttu-id="49585-139">若要深入了解 Teams 系統管理員角色，請參閱[使用 Microsoft Teams 系統管理員角色管理來管理 Teams](using-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="49585-139">To learn more about Teams administrator roles see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span>|
|<span data-ttu-id="49585-140">誰將獲指派 Teams 通訊支援工程師角色？</span><span class="sxs-lookup"><span data-stu-id="49585-140">Who will be assigned the Teams Communications Support Engineer role?</span></span>|<span data-ttu-id="49585-141">若要指派系統管理員角色，[使用 Azure Active Directory 將系統管理員和非系統管理員角色指派給使用者](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="49585-141">To assign admin roles, see [Assign administrator and non-administrator roles to users with Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span>|
|<span data-ttu-id="49585-142">誰將獲指派 Teams 通訊支援專員角色？</span><span class="sxs-lookup"><span data-stu-id="49585-142">Who will be assigned the Teams Communications Support Specialist role?</span></span>||
|||

### <a name="teams-owners-and-members"></a><span data-ttu-id="49585-143">Teams 擁有者和成員</span><span class="sxs-lookup"><span data-stu-id="49585-143">Teams owners and members</span></span>

<span data-ttu-id="49585-144">除了系統管理員角色，Teams 還能讓您指派擁有者和成員使用者角色，並選擇性地賦予他們仲裁者功能 (如果已設定仲裁)，以控制誰可以在頻道內執行特定動作。</span><span class="sxs-lookup"><span data-stu-id="49585-144">In addition to administrator roles, Teams lets you assign owner and member user roles, and selectively give them moderator capabilities (if moderation has been set up) to control who can perform certain actions within a channel.</span></span> <span data-ttu-id="49585-145">仲裁可讓您控制誰可以在頻道中開始新的文章、以仲裁者身分新增和移除團隊人員，以及控制團隊成員是否可以回覆現有的頻道訊息。</span><span class="sxs-lookup"><span data-stu-id="49585-145">Moderation allows you to control who can start new posts in a channel, add and remove team members as moderators, and control whether team members can reply to existing channel messages.</span></span>

|<span data-ttu-id="49585-146">問問自己</span><span class="sxs-lookup"><span data-stu-id="49585-146">Ask yourself</span></span>|<span data-ttu-id="49585-147">動作</span><span class="sxs-lookup"><span data-stu-id="49585-147">Action</span></span> |
|------------|-------|
|<span data-ttu-id="49585-148">應該對每個角色指派誰？</span><span class="sxs-lookup"><span data-stu-id="49585-148">Who should be assigned to each role?</span></span> | <span data-ttu-id="49585-149">若要比較每個角色的功能，請參閱[在 Microsoft Teams 中指派團隊擁有者、仲裁者和成員](assign-roles-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="49585-149">To compare the capabilities of each role, see [Assign team owners, moderators, and members in Microsoft Teams](assign-roles-permissions.md).</span></span>
|<span data-ttu-id="49585-150">如何指派使用者角色？</span><span class="sxs-lookup"><span data-stu-id="49585-150">How do I assign a user role?</span></span> | <span data-ttu-id="49585-151">若要指派或變更角色，請參閱[指派使用者角色](assign-roles-permissions.md#assign-a-user-role)。</span><span class="sxs-lookup"><span data-stu-id="49585-151">To assign or change a role, see [Assign a user role](assign-roles-permissions.md#assign-a-user-role).</span></span>
|<span data-ttu-id="49585-152">我需要控制誰可以在頻道中貼文及回覆嗎？</span><span class="sxs-lookup"><span data-stu-id="49585-152">Do I need to control who can post and reply in a channel?</span></span> | <span data-ttu-id="49585-153">若要設定仲裁，請參閱[在 Microsoft Teams 中設定和管理頻道仲裁](manage-channel-moderation-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="49585-153">To configure moderation, see [Set up and manage channel moderation in Microsoft Teams](manage-channel-moderation-in-teams.md).</span></span>

### <a name="messaging-policies"></a><span data-ttu-id="49585-154">訊息原則</span><span class="sxs-lookup"><span data-stu-id="49585-154">Messaging policies</span></span>

<span data-ttu-id="49585-155">管理原則可控制 Teams 中的使用者可使用的聊天及頻道訊息功能。</span><span class="sxs-lookup"><span data-stu-id="49585-155">Messaging policies control which chat and channel messaging features are available to users in Teams.</span></span> <span data-ttu-id="49585-156">例如，誰可以編輯和刪除已傳送的郵件、誰可以使用聊天、誰可以在交談中使用 Meme 等等。</span><span class="sxs-lookup"><span data-stu-id="49585-156">For example, who can edit and delete sent messages, who can use chat, who can use memes in conversations, and more.</span></span> <span data-ttu-id="49585-157">依預設，使用者會獲指派全域訊息原則，且所有功能都會**開啟**。</span><span class="sxs-lookup"><span data-stu-id="49585-157">By default, users are assigned the global messaging policy and all features are **On**.</span></span> <span data-ttu-id="49585-158">您可以使用預設的全域原則或是為組織中的人員建立一或多個自訂訊息原則。</span><span class="sxs-lookup"><span data-stu-id="49585-158">You can use the default global policy or create one or more custom messaging policies for people in your organization.</span></span> 

|<span data-ttu-id="49585-159">問問自己</span><span class="sxs-lookup"><span data-stu-id="49585-159">Ask yourself</span></span>|<span data-ttu-id="49585-160">動作</span><span class="sxs-lookup"><span data-stu-id="49585-160">Action</span></span> |
|------------|-------|
|<span data-ttu-id="49585-161">我要自訂全域訊息原則嗎？</span><span class="sxs-lookup"><span data-stu-id="49585-161">Will I customize the global messaging policy?</span></span>|<span data-ttu-id="49585-162">如需使用 Microsoft Teams 系統管理中心來變更全域訊息原則或新增原則的相關資訊，請參閱[在 Teams 中管理訊息原則](messaging-policies-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="49585-162">For information about using the Microsoft Teams admin center to change the global messaging policy or add a new policy, see [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>|
|<span data-ttu-id="49585-163">我需要多個訊息原則嗎？</span><span class="sxs-lookup"><span data-stu-id="49585-163">Do I require multiple messaging policies?</span></span>|<span data-ttu-id="49585-164">若要在 PowerShell 中建立並指派訊息原則，請參閱 [PowerShell 指令碼範例 - 建立並指派訊息原則](scripts/powershell-script-teams-messaging-policy-edu.md)。</span><span class="sxs-lookup"><span data-stu-id="49585-164">To create and assign a messaging policy in PowerShell, see [PowerShell script sample - Create and assign a messaging policy](scripts/powershell-script-teams-messaging-policy-edu.md).</span></span>|
|<span data-ttu-id="49585-165">我如何判斷哪些使用者群組可以獲得哪個訊息原則？</span><span class="sxs-lookup"><span data-stu-id="49585-165">How will I determine which groups of users get which messaging policy?</span></span>|<span data-ttu-id="49585-166">若要了解 CsTeamsMessagingPolicy Cmdlet，請參閱 [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="49585-166">To learn about the CsTeamsMessagingPolicy cmdlets, see [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps).</span></span>|
||| 

### <a name="external-access"></a><span data-ttu-id="49585-167">外部存取</span><span class="sxs-lookup"><span data-stu-id="49585-167">External access</span></span>

<span data-ttu-id="49585-168">外部存取 (之前稱為同盟) 可讓您的 Teams 和商務用 Skype 使用者與組織外部的使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="49585-168">External access (formerly known as federation) lets your Teams and Skype for Business users communicate with users who are outside of your organization.</span></span> <span data-ttu-id="49585-169">藉由將此功能開啟並將網域新增到允許清單，您的使用者即能夠與其他網域和組織中的使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="49585-169">By turning this on and adding domains to the allowed list, your users can communicate with users in other domains and organizations.</span></span><span data-ttu-id="49585-170">外部存取與來賓存取的不同在於，整個網域都會獲賦予存取權限，而非個人。</span><span class="sxs-lookup"><span data-stu-id="49585-170"> External access differs from guest access in that an entire domain is given access permission, not an individual.</span></span> <span data-ttu-id="49585-171">外部存取依預設為關閉。</span><span class="sxs-lookup"><span data-stu-id="49585-171">External access is turned off by default.</span></span>

|<span data-ttu-id="49585-172">問問自己</span><span class="sxs-lookup"><span data-stu-id="49585-172">Ask yourself</span></span>|<span data-ttu-id="49585-173">動作</span><span class="sxs-lookup"><span data-stu-id="49585-173">Action</span></span> |
|------------|-------|
|<ul><li><span data-ttu-id="49585-174">我要將組織的外部存取開啟嗎？</span><span class="sxs-lookup"><span data-stu-id="49585-174">Will I turn on external access for my organization?</span></span></li><li><span data-ttu-id="49585-175">如果啟用，我要限制組織可以與其通訊的網域嗎？</span><span class="sxs-lookup"><span data-stu-id="49585-175">If enabled, will I limit which domains my organization can communicate with?</span></span></li></ul> |<br><span data-ttu-id="49585-176">若要開啟外部存取，請參閱[規劃外部存取](manage-external-access.md#plan-for-external-access)。</span><span class="sxs-lookup"><span data-stu-id="49585-176">To turn on external access, see [Plan for external access](manage-external-access.md#plan-for-external-access).</span></span>|
|||

### <a name="guest-access"></a><span data-ttu-id="49585-177">來賓存取</span><span class="sxs-lookup"><span data-stu-id="49585-177">Guest access</span></span>

<span data-ttu-id="49585-178">Teams 中的來賓存取可讓組織外部的個人存取團隊和頻道。</span><span class="sxs-lookup"><span data-stu-id="49585-178">Guest access in Teams lets individuals outside your organization access teams and channels.</span></span> <span data-ttu-id="49585-179">您可使用來賓存取設定來控制來賓使用者可否使用的功能。</span><span class="sxs-lookup"><span data-stu-id="49585-179">You can use the guest access settings to control which features guest users can or can’t use.</span></span> <span data-ttu-id="49585-180">來賓存取依預設為關閉。</span><span class="sxs-lookup"><span data-stu-id="49585-180">Guest access is turned off by default.</span></span> <span data-ttu-id="49585-181">若要深入了解，請參閱 [Teams 中的來賓存取](https://docs.microsoft.com/microsoftteams/guest-access)。</span><span class="sxs-lookup"><span data-stu-id="49585-181">To learn more, see [Guest access in Teams](https://docs.microsoft.com/microsoftteams/guest-access).</span></span>

|<span data-ttu-id="49585-182">問問自己</span><span class="sxs-lookup"><span data-stu-id="49585-182">Ask yourself</span></span>|<span data-ttu-id="49585-183">動作</span><span class="sxs-lookup"><span data-stu-id="49585-183">Action</span></span> |
|------------|-------|
|<span data-ttu-id="49585-184">我要將組織的來賓存取開啟嗎？</span><span class="sxs-lookup"><span data-stu-id="49585-184">Will I turn on guest access for my organization?</span></span>|<span data-ttu-id="49585-185">若要開啟來賓存取，請參閱[開啟或關閉 Teams 中的來賓存取](set-up-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="49585-185">To turn on guest access, see [Turn on or off guest access in Teams](set-up-guests.md).</span></span>|
|<span data-ttu-id="49585-186">如果啟用，我將會自訂組織中來賓可使用的功能嗎？</span><span class="sxs-lookup"><span data-stu-id="49585-186">If enabled, will I customize the features available to guests in my organization?</span></span>|<span data-ttu-id="49585-187">若要自訂來賓存取功能的可用性，請參閱[在 Teams 中授權來賓存取](teams-dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="49585-187">To customize guest access feature availability, see [Authorize guest access in Teams](teams-dependencies.md).</span></span>|
|||

### <a name="teams-settings"></a><span data-ttu-id="49585-188">Teams 設定</span><span class="sxs-lookup"><span data-stu-id="49585-188">Teams settings</span></span>

<span data-ttu-id="49585-189">Teams 設定可讓您為團隊設定使用電子郵件整合、雲端儲存選項、組織索引標籤、會議室裝置設定和搜尋範圍等功能。</span><span class="sxs-lookup"><span data-stu-id="49585-189">Teams settings let you set up your teams for features such as email integration, cloud storage options, organization tab, meeting room device setup, and search scope.</span></span> <span data-ttu-id="49585-190">對這些設定進行變更時，設定會套用到組織中的所有團隊。</span><span class="sxs-lookup"><span data-stu-id="49585-190">When you make changes to these settings, they apply to all the teams in your organization.</span></span><span data-ttu-id="49585-191">若要深入了解，請參閱 [ Teams 設定](enable-features-office-365.md#teams-settings)。</span><span class="sxs-lookup"><span data-stu-id="49585-191"> To learn more, see [Teams settings](enable-features-office-365.md#teams-settings).</span></span>

|<span data-ttu-id="49585-192">問問自己</span><span class="sxs-lookup"><span data-stu-id="49585-192">Ask yourself</span></span>|<span data-ttu-id="49585-193">動作</span><span class="sxs-lookup"><span data-stu-id="49585-193">Action</span></span> |
|------------|-------|
|<span data-ttu-id="49585-194">我要自訂組織的 Teams 設定嗎？</span><span class="sxs-lookup"><span data-stu-id="49585-194">Will I customize Teams settings for my organization?</span></span> | <span data-ttu-id="49585-195">若要了解 Teams 設定以及如何加以自訂，請參閱 [Teams 設定](enable-features-office-365.md#teams-settings)。</span><span class="sxs-lookup"><span data-stu-id="49585-195">To learn about Teams settings and how to customize them, see [Teams settings](enable-features-office-365.md#teams-settings).</span></span>|
|||

### <a name="teams-clients"></a><span data-ttu-id="49585-196">Teams 用戶端</span><span class="sxs-lookup"><span data-stu-id="49585-196">Teams clients</span></span>

<span data-ttu-id="49585-197">Teams 支援許多用戶端，範圍從網頁、桌面到行動裝置，且預設組態可讓使用者選擇他們想要使用的任何用戶端。</span><span class="sxs-lookup"><span data-stu-id="49585-197">Teams supports a number of clients from web to desktop to mobile, and the default configuration lets users choose whichever clients they want.</span></span><span data-ttu-id="49585-198">若要深入了解，請參閱[取得 Teams 用戶端](get-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="49585-198"> To learn more, see [Get clients for Teams](get-clients.md).</span></span>

|<span data-ttu-id="49585-199">問問自己</span><span class="sxs-lookup"><span data-stu-id="49585-199">Ask yourself</span></span>|<span data-ttu-id="49585-200">動作</span><span class="sxs-lookup"><span data-stu-id="49585-200">Action</span></span> |
|------------|-------|
|<span data-ttu-id="49585-201">我要自訂組織的 Teams 用戶端可用性嗎？</span><span class="sxs-lookup"><span data-stu-id="49585-201">Will I customize Teams client availability for my organization?</span></span>|<span data-ttu-id="49585-202">請查看 [Teams 應用程式的硬體需求](hardware-requirements-for-the-teams-app.md)。</span><span class="sxs-lookup"><span data-stu-id="49585-202">Check out [Hardware requirements for the Teams app](hardware-requirements-for-the-teams-app.md).</span></span> |
|<span data-ttu-id="49585-203">我要自訂組織的 Teams 用戶端設定嗎？</span><span class="sxs-lookup"><span data-stu-id="49585-203">Will I customize Teams client settings for my organization?</span></span>|<span data-ttu-id="49585-204">了解如何[使用 MSI 安裝 Teams](msi-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="49585-204">Learn how to [Install Teams using MSI](msi-deployment.md).</span></span>|
|||


### <a name="teams-usage-reporting"></a><span data-ttu-id="49585-205">Teams 使用情況報告</span><span class="sxs-lookup"><span data-stu-id="49585-205">Teams usage reporting</span></span>

<span data-ttu-id="49585-206">Office 365 中的全域系統管理員、Teams 服務系統管理員和報告讀取者角色可檢視 Teams 使用情況報告。</span><span class="sxs-lookup"><span data-stu-id="49585-206">The Global Admin in Office 365, Teams Service Admin, and Reports Readers roles can view Teams usage reports.</span></span> <span data-ttu-id="49585-207">若要深入了解，請參閱 [Microsoft 365 使用情況分析文章](https://docs.microsoft.com/office365/admin/usage-analytics/usage-analytics?redirectSourcePath=%252farticle%252fMicrosoft-365-usage-analytics-77ff780d-ab19-4553-adea-09cb65ad0f1f&view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="49585-207">To learn more, see the [Microsoft 365 usage analytics articles](https://docs.microsoft.com/office365/admin/usage-analytics/usage-analytics?redirectSourcePath=%252farticle%252fMicrosoft-365-usage-analytics-77ff780d-ab19-4553-adea-09cb65ad0f1f&view=o365-worldwide).</span></span>

|<span data-ttu-id="49585-208">問問自己</span><span class="sxs-lookup"><span data-stu-id="49585-208">Ask yourself</span></span>|<span data-ttu-id="49585-209">動作</span><span class="sxs-lookup"><span data-stu-id="49585-209">Action</span></span> |
|------------|-------|
|<br> <span data-ttu-id="49585-210">誰需要查看 Teams 使用情況報告，以及他們是否具備檢視報告的正確角色？</span><span class="sxs-lookup"><span data-stu-id="49585-210">Who needs to see the Teams usage reports, and do they have the correct role to view them?</span></span> |<ul><li><span data-ttu-id="49585-211">如果使用者不是系統管理員，請[指派報告讀取者角色](teams-activity-reports.md#reports-reader-role)。</span><span class="sxs-lookup"><span data-stu-id="49585-211">If the user isn't an admin, [assign the Reports reader role](teams-activity-reports.md#reports-reader-role).</span></span></li><li><span data-ttu-id="49585-212">請參閱[角色和使用權限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)和[檢視和指派角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)來了解如何在 Azure Active Directory 中指派系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="49585-212">See [Roles and permissions](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [View and assign roles](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal) to learn how to assign admin roles in Azure Active Directory.</span></span> |
|||

### <a name="teams-default-apps"></a><span data-ttu-id="49585-213">Teams 預設應用程式</span><span class="sxs-lookup"><span data-stu-id="49585-213">Teams default apps</span></span> 

<span data-ttu-id="49585-214">Teams 提供大量的第一方 (Microsoft 提供) 和第三方應用程式，用來吸引使用者、支援生產力，並將常用的商務服務整合到 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="49585-214">Teams provides a number of first-party (Microsoft provided) and third-party apps to engage users, support productivity, and integrate commonly used business services into Teams.</span></span> <span data-ttu-id="49585-215">從 Teams 市集取得應用程式。</span><span class="sxs-lookup"><span data-stu-id="49585-215">Get apps from the Teams Store.</span></span> <span data-ttu-id="49585-216">Teams 中的應用程式預設會開啟。</span><span class="sxs-lookup"><span data-stu-id="49585-216">Apps are turned on by default in Teams.</span></span> 

<span data-ttu-id="49585-217">若要深入了解如何在 Teams 中推出和管理應用程式，請參閱我們的深入[應用程式、Bot 和連接器](deploy-apps-microsoft-teams-landing-page.md)指引。</span><span class="sxs-lookup"><span data-stu-id="49585-217">To learn more about rolling out and managing apps in Teams, see our in-depth [Apps, bots, & connectors](deploy-apps-microsoft-teams-landing-page.md) guidance.</span></span>


## <a name="additional-deployment-decisions"></a><span data-ttu-id="49585-218">其他部署決策</span><span class="sxs-lookup"><span data-stu-id="49585-218">Additional deployment decisions</span></span>

<span data-ttu-id="49585-219">根據組織的需求和組態而定，您可能會想要變更這些設定。</span><span class="sxs-lookup"><span data-stu-id="49585-219">You may want to change these settings, based on your organization's needs and configuration.</span></span>

### <a name="teams-licensing"></a><span data-ttu-id="49585-220">Teams 授權</span><span class="sxs-lookup"><span data-stu-id="49585-220">Teams licensing</span></span>

<span data-ttu-id="49585-221">Teams 會隨著許多 Office 365 授權的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="49585-221">Teams is provided as part of many Office 365 licenses.</span></span> <span data-ttu-id="49585-222">若要深入了解 Teams 授權，請參閱 [Teams 的 Office 365 授權](office-365-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="49585-222">To learn more about Teams licensing, see [Office 365 licensing for Teams](office-365-licensing.md).</span></span>

|<span data-ttu-id="49585-223">問問自己</span><span class="sxs-lookup"><span data-stu-id="49585-223">Ask yourself</span></span>|<span data-ttu-id="49585-224">動作</span><span class="sxs-lookup"><span data-stu-id="49585-224">Action</span></span> |
|------------|-------|
|<span data-ttu-id="49585-225">我的使用者是否擁有使用我要推出的 Teams 所有功能所需的授權？</span><span class="sxs-lookup"><span data-stu-id="49585-225">Do my users have the licenses they need in order to use all the Teams features I want to roll out?</span></span> | <span data-ttu-id="49585-226">若要了解授權需求，請參閱 [Teams 的 Office 365 授權](office-365-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="49585-226">To learn about licensing requirements, read [Office 365 licensing for Teams](office-365-licensing.md).</span></span>|
|||

### <a name="exchange-and-sharepoint-interoperability"></a><span data-ttu-id="49585-227">Exchange 和 SharePoint 互通性</span><span class="sxs-lookup"><span data-stu-id="49585-227">Exchange and SharePoint interoperability</span></span> 

<span data-ttu-id="49585-228">為了獲得完整的 Teams 體驗，每個使用者都應能夠建立 Exchange Online、SharePoint Online 和 Office 365 群組。</span><span class="sxs-lookup"><span data-stu-id="49585-228">For the full Teams experience, every user should be enabled for Exchange Online, SharePoint Online, and Office 365 Group creation.</span></span> <span data-ttu-id="49585-229">下列文章概述與各種環境中託管的 Exchange 信箱相關的資訊、Exchange 與 Teams 如何互動，以及 SharePoint 和商務用 OneDrive 的類似考量。</span><span class="sxs-lookup"><span data-stu-id="49585-229">The following articles outline information related to Exchange mailboxes hosted in various environments, how Exchange and Teams interact, and similar considerations for SharePoint and OneDrive for Business.</span></span> 

|<span data-ttu-id="49585-230">問問自己</span><span class="sxs-lookup"><span data-stu-id="49585-230">Ask yourself</span></span>|<span data-ttu-id="49585-231">動作</span><span class="sxs-lookup"><span data-stu-id="49585-231">Action</span></span> |
|------------|-------|
| <span data-ttu-id="49585-232">我是否能部署我目前使用 Exchange 和 SharePoint 部署所需的 Teams 功能？</span><span class="sxs-lookup"><span data-stu-id="49585-232">Will I be able to deploy the Teams features that I require with the current Exchange and SharePoint deployments?</span></span> |<span data-ttu-id="49585-233">如需 Teams 中 Exchange 和 SharePoint 的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="49585-233">For more information about Exchange and SharePoint in Teams, see:</span></span><ul><li> [<span data-ttu-id="49585-234">Exchange 和 Teams 如何互動</span><span class="sxs-lookup"><span data-stu-id="49585-234">How Exchange and Teams interact</span></span>](exchange-teams-interact.md)</li><li>[<span data-ttu-id="49585-235">SharePoint Online 和商務用 OneDrive 如何與 Teams 互動</span><span class="sxs-lookup"><span data-stu-id="49585-235">How SharePoint Online and OneDrive for Business interact with Teams</span></span>](sharepoint-onedrive-interact.md)|
|||

### <a name="teams-limits-and-specifications"></a><span data-ttu-id="49585-236">Teams 的限制和規格</span><span class="sxs-lookup"><span data-stu-id="49585-236">Teams limits and specifications</span></span> 

<span data-ttu-id="49585-237">規劃 Teams 的企業部署時，應考慮任何相關的限制和規格，例如團隊中成員人數的上限、使用者可建立的團隊人數上限等等。</span><span class="sxs-lookup"><span data-stu-id="49585-237">When planning an enterprise deployment of Teams, you should take into account any relevant limitations and specifications, such as the maximum number of members in a team, the maximum number of teams a user can create, and so on.</span></span>

|<span data-ttu-id="49585-238">問問自己</span><span class="sxs-lookup"><span data-stu-id="49585-238">Ask yourself</span></span>|<span data-ttu-id="49585-239">動作</span><span class="sxs-lookup"><span data-stu-id="49585-239">Action</span></span> |
|------------|-------|
| <span data-ttu-id="49585-240">隨著我的 Teams 推出，我可能會有哪些限制？</span><span class="sxs-lookup"><span data-stu-id="49585-240">What limits am I likely to hit with my Teams rollout?</span></span> | <span data-ttu-id="49585-241">若要深入了解，請參閱 [Teams 的限制和規格](limits-specifications-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="49585-241">To learn more, read [Limits and specifications for Teams](limits-specifications-teams.md).</span></span> |
|||

### <a name="office-365-urls-and-ports"></a><span data-ttu-id="49585-242">Office 365 URL 和連接埠</span><span class="sxs-lookup"><span data-stu-id="49585-242">Office 365 URLs and ports</span></span>

<span data-ttu-id="49585-243">對網際網路流量保有精細控制的組織，應閱讀 [Office 365 URL 和 IP 位址範圍](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)，以取得必須為 Teams 正確設定的最新 URL、IP 位址、連接埠和通訊協定的清單。</span><span class="sxs-lookup"><span data-stu-id="49585-243">Organizations that maintain fine-grained control of their internet traffic should read [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) for an up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams.</span></span> <span data-ttu-id="49585-244">Microsoft 會持續改善 Office 365 服務並加入新的功能，這表示必要的連接埠、URL 和 IP 位址可能會隨著時間變更。</span><span class="sxs-lookup"><span data-stu-id="49585-244">Microsoft is continuously improving the Office 365 service and adding new functionality, which means the required ports, URLs, and IP addresses may change over time.</span></span> <span data-ttu-id="49585-245">建議您透過 RSS 訂閱，以便在此資訊更新或變更時收到通知。</span><span class="sxs-lookup"><span data-stu-id="49585-245">We recommend that you subscribe via RSS to receive notifications when this information is updated or changed.</span></span> <span data-ttu-id="49585-246">至少，請確認您已開放以上的[聊天部署必要條件](#chat-deployment-prerequisites)中所列的連接埠。</span><span class="sxs-lookup"><span data-stu-id="49585-246">At a minimum, make sure you've opened the ports listed above in [Chat deployment prerequisites](#chat-deployment-prerequisites).</span></span>

|<span data-ttu-id="49585-247">問問自己</span><span class="sxs-lookup"><span data-stu-id="49585-247">Ask yourself</span></span>|<span data-ttu-id="49585-248">動作</span><span class="sxs-lookup"><span data-stu-id="49585-248">Action</span></span> |
|------------|-------|
| <span data-ttu-id="49585-249">我是否需要網際網路存取規則，才能讓使用者能使用 Teams，或是開放必要的最基本連接埠即已足夠？</span><span class="sxs-lookup"><span data-stu-id="49585-249">Do I require internet access rules to enable users to use Teams, or is it sufficient to open the minimum required ports?</span></span> | <span data-ttu-id="49585-250">若要深入了解，請參閱 [Office 365 URL 和 IP 位址範圍](office-365-urls-ip-address-ranges.md)。</span><span class="sxs-lookup"><span data-stu-id="49585-250">To learn more, see [Office 365 URLs and IP address ranges](office-365-urls-ip-address-ranges.md).</span></span>|
|||


### <a name="governance-naming-conventions-who-can-create-teams"></a><span data-ttu-id="49585-251">控管 (命名慣例，可建立團隊的人員)</span><span class="sxs-lookup"><span data-stu-id="49585-251">Governance (naming conventions, who can create teams)</span></span>

<span data-ttu-id="49585-252">您的組織可能會要求您對團隊的命名和分類方式、誰可以建立團隊以及團隊到期日、保留和封存實作控制。</span><span class="sxs-lookup"><span data-stu-id="49585-252">Your organization might require that you implement controls on how teams are named and classified, who can create teams, and team expiration, retention, and archiving.</span></span> <span data-ttu-id="49585-253">這稱為控管。</span><span class="sxs-lookup"><span data-stu-id="49585-253">This is called governance.</span></span> <span data-ttu-id="49585-254">您可以使用 Azure Active Directory (Azure AD) 來設定每一個區域。</span><span class="sxs-lookup"><span data-stu-id="49585-254">You can use Azure Active Directory (Azure AD) to configure each of these areas.</span></span>


| <span data-ttu-id="49585-255">問問自己</span><span class="sxs-lookup"><span data-stu-id="49585-255">Ask yourself</span></span> | <span data-ttu-id="49585-256">動作</span><span class="sxs-lookup"><span data-stu-id="49585-256">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="49585-257">我是否需要對可以建立團隊的人員實作控制？</span><span class="sxs-lookup"><span data-stu-id="49585-257">Will I need to implement controls on who can create teams?</span></span>| <span data-ttu-id="49585-258">請閱讀[規劃 Teams 中的控管](plan-teams-governance.md)。</span><span class="sxs-lookup"><span data-stu-id="49585-258">Read [Plan for governance in Teams](plan-teams-governance.md).</span></span>|
|<span data-ttu-id="49585-259">我是否需要對團隊的命名方式實作控制？</span><span class="sxs-lookup"><span data-stu-id="49585-259">Will I need to implement controls on how teams are named?</span></span>|<span data-ttu-id="49585-260">請閱讀[在 Azure AD 中對 Office 365 群組強制執行命名原則](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)。</span><span class="sxs-lookup"><span data-stu-id="49585-260">Read [Enforce a naming policy for Office 365 groups in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy).</span></span>|
|||

### <a name="teams-application-policy-side-rail-control"></a><span data-ttu-id="49585-261">Teams 應用程式原則 (側邊欄控制)</span><span class="sxs-lookup"><span data-stu-id="49585-261">Teams application policy (side-rail control)</span></span>

<span data-ttu-id="49585-262">釘選的應用程式會顯示在 Teams 的側邊欄中。</span><span class="sxs-lookup"><span data-stu-id="49585-262">A pinned app shows up in the side rail in Teams.</span></span> <span data-ttu-id="49585-263">透過建立 Teams 應用程式原則，您可以預先設定釘選 Teams 應用程式的集合，以針對選取的使用者群組將 Teams 個人化。</span><span class="sxs-lookup"><span data-stu-id="49585-263">By creating Teams application policies, you can preconfigure sets of pinned Teams apps to personalize Teams for select groups of users.</span></span> <span data-ttu-id="49585-264">[在 Microsoft Teams 中允許外部應用程式]\*\*\*\* 設定預設為開啟。</span><span class="sxs-lookup"><span data-stu-id="49585-264">By default, the **Allow external apps in Microsoft Teams** setting is turned on.</span></span>

| <span data-ttu-id="49585-265">問問自己</span><span class="sxs-lookup"><span data-stu-id="49585-265">Ask yourself</span></span> | <span data-ttu-id="49585-266">動作</span><span class="sxs-lookup"><span data-stu-id="49585-266">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="49585-267">我應該建立預先設定的釘選 Teams 應用程式集嗎？</span><span class="sxs-lookup"><span data-stu-id="49585-267">Should I create preconfigured sets of pinned Teams applications?</span></span> | <span data-ttu-id="49585-268">請閱讀[在 Teams 中管理應用程式的設定](admin-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="49585-268">Read [Admin settings for apps in Teams](admin-settings.md).</span></span>|
|<span data-ttu-id="49585-269">我如何決定哪些群組會收到這些應用程式群組？</span><span class="sxs-lookup"><span data-stu-id="49585-269">How will I decide which groups receive these app groupings?</span></span>|<span data-ttu-id="49585-270">請閱讀 [Teams 應用程式權限和考量](app-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="49585-270">Read [Teams apps permissions and considerations](app-permissions.md).</span></span>|
|||

### <a name="archiving-and-compliance"></a><span data-ttu-id="49585-271">封存與合規性</span><span class="sxs-lookup"><span data-stu-id="49585-271">Archiving and compliance</span></span> 

<span data-ttu-id="49585-272">您的組織可能會要求您對團隊的封存方式以及特定團隊類型中保留的資料類型實作控制。</span><span class="sxs-lookup"><span data-stu-id="49585-272">Your organization might require that you implement controls on how teams are archived and the types of data that are held in certain types of teams.</span></span> <span data-ttu-id="49585-273">請閱讀 [Teams 的安全性與合規性概觀](security-compliance-overview.md)，以了解預設會開啟哪些設定。</span><span class="sxs-lookup"><span data-stu-id="49585-273">Read [Overview of security and compliance in Teams](security-compliance-overview.md) to learn which settings are turned on by default.</span></span>

| <span data-ttu-id="49585-274">問問自己</span><span class="sxs-lookup"><span data-stu-id="49585-274">Ask yourself</span></span> | <span data-ttu-id="49585-275">動作</span><span class="sxs-lookup"><span data-stu-id="49585-275">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="49585-276">我需要設定團隊保留嗎？</span><span class="sxs-lookup"><span data-stu-id="49585-276">Will I need to configure team retention?</span></span>|<span data-ttu-id="49585-277">若要設定保留原則，請參閱[設定 Teams 保留原則](retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="49585-277">To set up retention policies, see [Set up Teams retention policies](retention-policies.md).</span></span>|
|<span data-ttu-id="49585-278">我需要設定團隊封存嗎？</span><span class="sxs-lookup"><span data-stu-id="49585-278">Will I need to configure team archiving?</span></span>|<span data-ttu-id="49585-279">若要封存或還原團隊，請參閱[封存或還原團隊](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)。</span><span class="sxs-lookup"><span data-stu-id="49585-279">To archive or restore a team, see [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>|
|<span data-ttu-id="49585-280">我需要設定額外的合規性設定嗎？</span><span class="sxs-lookup"><span data-stu-id="49585-280">Will I need to configure additional compliance settings?</span></span>|<span data-ttu-id="49585-281">如需安全性和合規性的詳細資訊，請參閱 [Teams 的安全性與合規性概觀](security-compliance-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="49585-281">For more information about security and compliance, see [Overview of security and compliance in Teams](security-compliance-overview.md).</span></span>|
|||

### <a name="conditional-access"></a><span data-ttu-id="49585-282">條件式存取</span><span class="sxs-lookup"><span data-stu-id="49585-282">Conditional access</span></span> 

<span data-ttu-id="49585-283">針對包括會議、行事曆、交互操作聊天和檔案共用在內的核心生產力案例中，Teams 極為依賴 Exchange Online、SharePoint Online 及商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="49585-283">Teams relies heavily on Exchange Online, SharePoint Online, and Skype for Business Online for core productivity scenarios, including meetings, calendars, interop chats, and file sharing.</span></span> <span data-ttu-id="49585-284">當使用者在任何用戶端上直接登入 Teams 時，對這些雲端應用程式設定的條件式存取原則會套用至 Teams。</span><span class="sxs-lookup"><span data-stu-id="49585-284">Conditional access policies that are set for these cloud apps apply to Teams when a user signs in directly to Teams, on any client.</span></span> <span data-ttu-id="49585-285">為 Teams 雲端應用程式控制方面設定的條件式存取原則，例如，使用者是否可以從特定網路存取 Teams 服務。</span><span class="sxs-lookup"><span data-stu-id="49585-285">Conditional access policies that are set for the Teams cloud app control aspects such as whether users can access Teams services from certain networks.</span></span>

| <span data-ttu-id="49585-286">問問自己</span><span class="sxs-lookup"><span data-stu-id="49585-286">Ask yourself</span></span> | <span data-ttu-id="49585-287">動作</span><span class="sxs-lookup"><span data-stu-id="49585-287">Action</span></span> |
|--------------|--------|
|<br><span data-ttu-id="49585-288">我需要為 Teams 設定條件式存取嗎？</span><span class="sxs-lookup"><span data-stu-id="49585-288">Will I need to configure conditional access for Teams?</span></span>|<ul><li><span data-ttu-id="49585-289">若要了解存取原則的運作方式，請參閱[條件式存取原則如何適合 Teams？](security-compliance-overview.md#how-do-conditional-access-policies-work-for-teams)</span><span class="sxs-lookup"><span data-stu-id="49585-289">To understand how access policies work, see [How do conditional access policies work for Teams?](security-compliance-overview.md#how-do-conditional-access-policies-work-for-teams)</span></span></li><li><span data-ttu-id="49585-290">若要為 Teams 設定多重要素驗證 (MFA)，請參閱：</span><span class="sxs-lookup"><span data-stu-id="49585-290">To set up multi-factor authentication (MFA) for Teams, see:</span></span><ul><li>[<span data-ttu-id="49585-291">快速入門：透過 Azure Active Directory 條件式存取來要求特定應用程式需要 MFA</span><span class="sxs-lookup"><span data-stu-id="49585-291">Quickstart: Require MFA for specific apps with Azure Active Directory conditional access</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-mfa)</li><li>[<span data-ttu-id="49585-292">Azure Active Directory 條件式存取設定參考</span><span class="sxs-lookup"><span data-stu-id="49585-292">Azure Active Directory conditional access settings reference</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference)</li></ul></ul>|
|||


### <a name="education-edu"></a><span data-ttu-id="49585-293">教育版 (EDU)</span><span class="sxs-lookup"><span data-stu-id="49585-293">Education (EDU)</span></span> 

<span data-ttu-id="49585-294">在教育單位工作的 IT 專業人員可以利用教育版 Teams，該版本提供許多專為與學生、教職員和更廣泛企業的教育特定案例而量身打造的功能。</span><span class="sxs-lookup"><span data-stu-id="49585-294">IT pros working in education can take advantage of Teams for Education, which comes with a number of capabilities that have been tailored to meet education-specific scenarios for students, faculty, and the wider business.</span></span>

| <span data-ttu-id="49585-295">問問自己</span><span class="sxs-lookup"><span data-stu-id="49585-295">Ask yourself</span></span> | <span data-ttu-id="49585-296">動作</span><span class="sxs-lookup"><span data-stu-id="49585-296">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="49585-297">我要使用教育版特定的 Teams 範本嗎？</span><span class="sxs-lookup"><span data-stu-id="49585-297">Will I use EDU-specific Teams templates?</span></span> |<span data-ttu-id="49585-298">若要深入了解教育版 Teams，請參閱[系統管理員的 Microsoft 教育控管常見問題集](plan-teams-governance-edu.md)。</span><span class="sxs-lookup"><span data-stu-id="49585-298">To learn more about Teams for Education, see [Microsoft Education governance FAQ for admins](plan-teams-governance-edu.md).</span></span>|
|<span data-ttu-id="49585-299">我將部署限定範圍搜尋嗎？</span><span class="sxs-lookup"><span data-stu-id="49585-299">Will I deploy scoped search?</span></span>|<span data-ttu-id="49585-300">若要設定 Teams 教育版，請參閱[快速入門 - Teams 教育版系統管理員](teams-quick-start-edu.yml)。</span><span class="sxs-lookup"><span data-stu-id="49585-300">To set up Teams for EDU, see [Quickstart - Teams for Education admins](teams-quick-start-edu.yml).</span></span>|
|<span data-ttu-id="49585-301">我要將 Teams 與學校資料同步處理服務整合，以佈建使用者帳戶嗎？</span><span class="sxs-lookup"><span data-stu-id="49585-301">Will I integrate Teams with the School Data Sync service to provision user accounts?</span></span>|[<span data-ttu-id="49585-302">Teams 教育版管理員的資源</span><span class="sxs-lookup"><span data-stu-id="49585-302">Teams resources for Education admins</span></span>](resources-teams-edu.md)|
|||

### <a name="government---gcc-considerations"></a><span data-ttu-id="49585-303">政府版 - GCC 考量</span><span class="sxs-lookup"><span data-stu-id="49585-303">Government - GCC considerations</span></span>

<span data-ttu-id="49585-304">Microsoft 365 政府版 - GCC (專長認證的政府機關) 適合用來滿足在美國聯邦、州、當地、部落或特區政府實體推動 Office 365 部署或處理受限於政府法規和需求的其他實體 IT 專業人員的需求。</span><span class="sxs-lookup"><span data-stu-id="49585-304">The use of Microsoft 365 for Government - GCC (government certificate of competency) is appropriate to meet the requirements of IT pros who are driving deployments of Office 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that’s subject to government regulations and requirements.</span></span>

| <span data-ttu-id="49585-305">問問自己</span><span class="sxs-lookup"><span data-stu-id="49585-305">Ask yourself</span></span> | <span data-ttu-id="49585-306">動作</span><span class="sxs-lookup"><span data-stu-id="49585-306">Action</span></span> |
|--------------|--------|
| <span data-ttu-id="49585-307">我需要在 Microsoft 365 政府版 - GCC 環境中部署 Teams 嗎？</span><span class="sxs-lookup"><span data-stu-id="49585-307">Will I need to deploy Teams in a Microsoft 365 Government – GCC environment?</span></span> | <span data-ttu-id="49585-308">如需部署考量，請參閱[規劃 Microsoft 365 政府版 - GCC 部署](plan-for-government-gcc.md)。</span><span class="sxs-lookup"><span data-stu-id="49585-308">For deployment considerations, see [Plan for Microsoft 365 Government - GCC deployments](plan-for-government-gcc.md).</span></span>|
|||

## <a name="next-steps"></a><span data-ttu-id="49585-309">後續步驟</span><span class="sxs-lookup"><span data-stu-id="49585-309">Next steps</span></span>
- <span data-ttu-id="49585-310">聊天、團隊、頻道和應用程式的[推動採用](adopt-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="49585-310">[Drive adoption](adopt-microsoft-teams-landing-page.md) of chat, teams, channels, & apps.</span></span>
- <span data-ttu-id="49585-311">在您的 Teams 初始推出中包含精選應用程式，例如 Planner。</span><span class="sxs-lookup"><span data-stu-id="49585-311">Include featured apps - such as Planner - in your initial Teams rollout.</span></span> <span data-ttu-id="49585-312">在開始推動 Teams 的採用時，則新增其他[應用程式、Bot 和連接器](deploy-apps-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="49585-312">Add other [apps, bots, & connectors](deploy-apps-microsoft-teams-landing-page.md) as you drive Teams adoption.</span></span>
- [<span data-ttu-id="49585-313">推出會議和研討會</span><span class="sxs-lookup"><span data-stu-id="49585-313">Roll out meetings & conferencing</span></span>](deploy-meetings-microsoft-teams-landing-page.md)
- [<span data-ttu-id="49585-314">推出雲端語音</span><span class="sxs-lookup"><span data-stu-id="49585-314">Roll out cloud voice</span></span>](cloud-voice-landing-page.md)

