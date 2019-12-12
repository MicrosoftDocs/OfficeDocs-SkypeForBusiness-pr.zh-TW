---
title: Microsoft Teams 中的應用程式、Bot 和連接器
ms.reviewer: ''
description: 使用者這些部署資源協助您在 Microsoft 中部署應用程式。
ms.topic: article
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: admin
ms.date: 01/28/2019
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: c808c8a44a649a37f6d13d31538dd08797d56b24
ms.sourcegitcommit: dc70fd277d9542d831741e14dba9ae22367210ae
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2019
ms.locfileid: "39909449"
---
# <a name="apps-bots--connectors-in-microsoft-teams"></a><span data-ttu-id="f7ec6-103">Microsoft Teams 中的應用程式、Bot 和連接器</span><span class="sxs-lookup"><span data-stu-id="f7ec6-103">Apps, bots, & connectors in Microsoft Teams</span></span>

<span data-ttu-id="f7ec6-104">您可利用應用程式在最愛的服務中尋找內容，然後在 Teams 中分享。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-104">Apps let you find content from your favorite services and share it right in Teams.</span></span> <span data-ttu-id="f7ec6-105">他們可幫助您執行作業，例如在頻道最上方釘選服務、與 Bot 聊天或共用及指派工作。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-105">They help you do things such as pin services at the top of a channel, chat with bots, or share and assign tasks.</span></span> <span data-ttu-id="f7ec6-106">若要深入了解，請參閱[ Teams 中的應用程式概觀](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-106">To learn more, read [Overview of apps in Teams](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0).</span></span>

<span data-ttu-id="f7ec6-107">建議您在一開始推出 Teams 時能夠包含我們的精選應用程式，例如 Planner。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-107">We recommend that you include our featured apps - such as Planner - in your initial Teams rollout.</span></span> <span data-ttu-id="f7ec6-108">然後在推廣 Teams 的採用時，新增其他應用程式、Bot 和連接器。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-108">Add other apps, bots, & connectors as you drive Teams adoption.</span></span>

<span data-ttu-id="f7ec6-109">您也可以選擇建立自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-109">You also have the option of creating your own custom apps.</span></span> <span data-ttu-id="f7ec6-110">如需詳細資訊，請參閱我們的[開發人員文件](/microsoftteams/platform/overview)。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-110">See our [developer documentation](/microsoftteams/platform/overview) for more information.</span></span>

## <a name="apps-deployment-decisions"></a><span data-ttu-id="f7ec6-111">應用程式部署決策</span><span class="sxs-lookup"><span data-stu-id="f7ec6-111">Apps deployment decisions</span></span>

<span data-ttu-id="f7ec6-112">Teams 為您的組織提供絕佳的現成共同作業體驗，而大部分組織認為預設設定就能滿足其需求。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-112">Teams provides a great out-of-the-box collaboration experience for your organization, and most organizations find that the default settings work for them.</span></span> <span data-ttu-id="f7ec6-113">本文可協助您決定是否要根據組織的設定檔和商務需求來變更任何預設設定，並逐步引導您完成每個變更。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-113">This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="f7ec6-114">我們已將設定分割成兩個群組，從[您最可能進行的變更](#core-deployment-decisions)的核心集開始。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-114">We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="f7ec6-115">根據組織的需求，第二個群組包括您可能想要設定的[其他設定](#additional-deployment-decisions)。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-115">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="f7ec6-116">核心部署決策</span><span class="sxs-lookup"><span data-stu-id="f7ec6-116">Core deployment decisions</span></span>

<span data-ttu-id="f7ec6-117">這些應用程式設定是大部分組織想要變更的 (如果 Teams 的預設設定不符合組織的需求)。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-117">These are the settings that most organizations want to change (if the Teams default settings don't work for the organization).</span></span>

### <a name="app-availability-settings"></a><span data-ttu-id="f7ec6-118">應用程式可用性設定</span><span class="sxs-lookup"><span data-stu-id="f7ec6-118">App availability settings</span></span> 

<span data-ttu-id="f7ec6-119">Teams 提供數個由 Microsoft 發行的應用程式和第三方應用程式，以吸引使用者、支援生產活動，並將常用的商務服務整合到 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-119">Teams provides a number of first-party (Microsoft provided) and third-party apps to engage users, support productivity, and integrate commonly used business services into Teams.</span></span> <span data-ttu-id="f7ec6-120">從 Teams 市集取得應用程式。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-120">Get apps from the Teams Store.</span></span> <span data-ttu-id="f7ec6-121">根據預設，所有的應用程式 (包括透過 [Teams 市集核准程序](https://docs.microsoft.com/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process)提交的自訂應用程式) 都會針對所有使用者開啟。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-121">By default, all apps, including custom apps that you've submitted via the [Teams Store approval process](https://docs.microsoft.com/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process), are turned on for all users.</span></span> <span data-ttu-id="f7ec6-122">例如，使用者可以使用 Planner 應用程式來建立和管理 Teams 中的小組工作。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-122">For example, users can use the Planner app to build and manage team tasks in Teams.</span></span>

<span data-ttu-id="f7ec6-123">根據預設，您可使用所有 Microsoft 提供和自訂的應用程式，並且可開啟或關閉個別應用程式。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-123">By default, all Microsoft-provided and custom apps are available, and you can turn individual apps on or off.</span></span> <span data-ttu-id="f7ec6-124">這是全組織的設定，可讓您開啟或關閉整個組織的所有自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-124">There's an org-wide setting that lets you turn all custom apps on or off for your entire organization.</span></span>

| <span data-ttu-id="f7ec6-125">問問自己</span><span class="sxs-lookup"><span data-stu-id="f7ec6-125">Ask yourself</span></span> | <span data-ttu-id="f7ec6-126">動作</span><span class="sxs-lookup"><span data-stu-id="f7ec6-126">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="f7ec6-127">您是否會變更預設的 Teams 應用程式設定？</span><span class="sxs-lookup"><span data-stu-id="f7ec6-127">Will you change the default Teams apps settings?</span></span> | <span data-ttu-id="f7ec6-128">如需可用來管理組織中的應用程式的原則和設定的詳細資訊，請參閱 [Microsoft Teams 中應用程式的系統管理設定](admin-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-128">For more information about policies and settings that you can use to manage apps in your organization, see [Admin settings for apps in Microsoft Teams](admin-settings.md).</span></span>|
|||

### <a name="app-permissions-and-other-considerations"></a><span data-ttu-id="f7ec6-129">應用程式權限和其他考量</span><span class="sxs-lookup"><span data-stu-id="f7ec6-129">App permissions and other considerations</span></span>

<span data-ttu-id="f7ec6-130">應用程式經過使用者同意，並且由系統管理員或 IT 專業人員透過原則管理。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-130">Apps are consented to by users and managed by the admin or IT pro through policies.</span></span> <span data-ttu-id="f7ec6-131">不過在絕大多數情況下，應用程式的權限和風險設定檔是在應用程式本身中定義。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-131">However, for the most part, an app's permissions and risk profile are defined in the app itself.</span></span> 

| <span data-ttu-id="f7ec6-132">問問自己</span><span class="sxs-lookup"><span data-stu-id="f7ec6-132">Ask yourself</span></span> | <span data-ttu-id="f7ec6-133">動作</span><span class="sxs-lookup"><span data-stu-id="f7ec6-133">Action</span></span> |
|--------------|--------|
|<br><span data-ttu-id="f7ec6-134">我想允許哪些應用程式的存取權？</span><span class="sxs-lookup"><span data-stu-id="f7ec6-134">Which apps do I want to allow access to?</span></span> <span data-ttu-id="f7ec6-135">我不想允許哪些應用程式的存取權？</span><span class="sxs-lookup"><span data-stu-id="f7ec6-135">Which ones do I not want to allow access to?</span></span>  | <ul><li><span data-ttu-id="f7ec6-136">如需在允許應用程式、Bot、索引標籤或連接器的存取權時應考慮的事項清單，請參閱 [Microsoft Teams 應用程式權限和考量事項](app-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-136">See [Microsoft Teams apps permissions and considerations](app-permissions.md) for a list of things you should consider when allowing access to an app, bot, tab, or connector.</span></span></li><li><span data-ttu-id="f7ec6-137">如需提供應用程式讓組織的使用者使用的相關資訊，請參閱 [在 Teams 租用戶應用程式目錄中發佈應用程式](tenant-apps-catalog-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-137">See [Publish apps in the Teams tenant apps catalog](tenant-apps-catalog-teams.md) for information about making an app available to users in your organization.</span></span></li></ul>|
|||

### <a name="bots-for-private-chats-and-channels"></a><span data-ttu-id="f7ec6-138">適用於私人聊天和頻道的 Bot</span><span class="sxs-lookup"><span data-stu-id="f7ec6-138">Bots for private chats and channels</span></span>

<span data-ttu-id="f7ec6-139">Bot 是自動程式，可回應查詢或可針對使用者感興趣或希望隨時了解的詳細資訊提供更新和通知。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-139">Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about.</span></span> <span data-ttu-id="f7ec6-140">Bot 可讓使用者與 Teams 聊天中的雲端服務互動，例如工作管理、排程和投票等。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-140">Bots allow users to interact with cloud services such as task management, scheduling, and polling in a Teams chat.</span></span> <span data-ttu-id="f7ec6-141">Teams 支援在私人聊天和頻道中使用 Bot。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-141">Teams supports bots in private chats and channels.</span></span> <span data-ttu-id="f7ec6-142">系統管理員可以控制是否允許在 Office 365 租用戶中使用 Bot。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-142">Administrators can control whether the use of bots is allowed in an Office 365 tenant.</span></span>

| <span data-ttu-id="f7ec6-143">問問自己</span><span class="sxs-lookup"><span data-stu-id="f7ec6-143">Ask yourself</span></span> | <span data-ttu-id="f7ec6-144">動作</span><span class="sxs-lookup"><span data-stu-id="f7ec6-144">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="f7ec6-145">我想要在我的 Office 365 租用戶中允許使用自訂 Bot 嗎？</span><span class="sxs-lookup"><span data-stu-id="f7ec6-145">Do I want to allow custom bots in my Office 365 tenant?</span></span>|<span data-ttu-id="f7ec6-146">如需新增 Bot 的詳細資訊，請參閱[在 Microsoft Teams 中新增適用於私人聊天和頻道的 Bot](add-bots.md) (英文)。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-146">For more information about adding bots, see [Add bots for private chats and channels in Microsoft Teams](add-bots.md).</span></span> <span data-ttu-id="f7ec6-147">如需開啟或關閉自訂 Bot 的詳細資訊，請參閱 [Microsoft Teams 中應用程式的系統管理設定](admin-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-147">For information about turning custom bots on or off, see [Admin settings for apps in Microsoft Teams](admin-settings.md).</span></span>|
|||

### <a name="built-in-and-custom-tabs"></a><span data-ttu-id="f7ec6-148">內建和自訂索引標籤</span><span class="sxs-lookup"><span data-stu-id="f7ec6-148">Built-in and custom tabs</span></span>

<span data-ttu-id="f7ec6-149">擁有者與團隊成員可以在頻道、私人聊天和群組聊天中新增索引標籤，協助整合其雲端服務。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-149">Owners and team members can add tabs to a channel, private chat, and group chat to help integrate their cloud services.</span></span> <span data-ttu-id="f7ec6-150">新增索引標籤可協助使用者存取及管理他們所需或最常用的資料。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-150">Add tabs to help users access and manage the data they need or use the most.</span></span> <span data-ttu-id="f7ec6-151">在頻道中，預設會建立 [交談] 和 [檔案] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-151">In channels, the Conversations and Files tabs are created by default.</span></span> <span data-ttu-id="f7ec6-152">在每個私人聊天中，預設會建立 [交談]、[檔案]、[組織] 和 [活動] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-152">In every private chat, the Conversations, Files, Organization, and Activity tabs are created by default.</span></span> <span data-ttu-id="f7ec6-153">除了這些內建索引標籤之外，您還可以設計及新增自訂索引標籤。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-153">In addition to these built-in tabs, you can design and add custom tabs.</span></span> <span data-ttu-id="f7ec6-154">若要瞭解如何為組織開啟或關閉Teams 應用程式，請參閱 [Teams 中應用程式的系統管理設定](admin-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-154">To learn about turning Teams apps on or off for your organization, read [Admin settings for apps in Teams](admin-settings.md).</span></span>

| <span data-ttu-id="f7ec6-155">問問自己</span><span class="sxs-lookup"><span data-stu-id="f7ec6-155">Ask yourself</span></span> | <span data-ttu-id="f7ec6-156">動作</span><span class="sxs-lookup"><span data-stu-id="f7ec6-156">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="f7ec6-157">我想要在我的 Office 365 租用戶中允許使用自訂索引標籤嗎？</span><span class="sxs-lookup"><span data-stu-id="f7ec6-157">Do I want to allow custom tabs in my Office 365 tenant?</span></span>|<span data-ttu-id="f7ec6-158">如需詳細資訊，請參閱 [在 Teams 中使用內建和自訂索引標籤](built-in-custom-tabs.md)。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-158">For more information, see [Use built-in and custom tabs in Teams](built-in-custom-tabs.md).</span></span>|
|||

### <a name="office-365-and-custom-connectors"></a><span data-ttu-id="f7ec6-159">Office 365 和自訂連接器</span><span class="sxs-lookup"><span data-stu-id="f7ec6-159">Use Office 365 and custom connectors</span></span>

<span data-ttu-id="f7ec6-160">連接器透過將您經常使用的服務中的內容和更新直接發送到頻道中，進而使您的團隊保持最新狀態。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-160">Connectors keep your team current by delivering content and updates from services you frequently use directly into a channel.</span></span> <span data-ttu-id="f7ec6-161">有了連接器，您的 Teams 使用者就能在其 Teams 聊天中接收來自來自 Twitter、Trello、Wunderlist、GitHub 和 Azure DevOps 服務等熱門服務的更新。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-161">With connectors, your Teams users can receive updates from popular services such as Twitter, Trello, Wunderlist, GitHub, and Azure DevOps Services in their Teams chats.</span></span>

| <span data-ttu-id="f7ec6-162">問問自己</span><span class="sxs-lookup"><span data-stu-id="f7ec6-162">Ask yourself</span></span> | <span data-ttu-id="f7ec6-163">動作</span><span class="sxs-lookup"><span data-stu-id="f7ec6-163">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="f7ec6-164">我是否要允許使用者建立自訂連接器？</span><span class="sxs-lookup"><span data-stu-id="f7ec6-164">Do I want to allow users to create custom connectors?</span></span>|<span data-ttu-id="f7ec6-165">如需詳細資訊，請參閱 [在 Teams 中使用 Office 365 和自訂連接器](office-365-custom-connectors.md)。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-165">For more information, see [Use Office 365 and custom connectors in Teams](office-365-custom-connectors.md).</span></span>|
|||

## <a name="additional-deployment-decisions"></a><span data-ttu-id="f7ec6-166">其他部署決策</span><span class="sxs-lookup"><span data-stu-id="f7ec6-166">Additional deployment decisions</span></span>

<span data-ttu-id="f7ec6-167">根據組織的需求和組態而定，您可能會想要變更這些設定。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-167">You may want to change these settings, based on your organization's needs and configuration.</span></span>

### <a name="activity-reports"></a><span data-ttu-id="f7ec6-168">活動報告</span><span class="sxs-lookup"><span data-stu-id="f7ec6-168">Activity reports</span></span>

<span data-ttu-id="f7ec6-169">您可以使用活動報告來查看組織中的使用者如何使用 Teams。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-169">Use activity reports to see how users in your organization are using Teams.</span></span> <span data-ttu-id="f7ec6-170">例如，如果有人還沒使用 Teams，可能是他們不知道如何開始，或不了解如何使用 Teams 提高生產力和共同作業。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-170">For example, if some don’t use Teams yet, they might not know how to get started or understand how they can use Teams to be more productive and collaborative.</span></span> <span data-ttu-id="f7ec6-171">組織可以使用活動報告來決定要優先進行訓練和溝通的方面。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-171">Your organization can use the activity reports to decide where to prioritize training and communication efforts.</span></span> <span data-ttu-id="f7ec6-172">若要查看活動報告，您必須是 Office 365 的全域系統管理員、Teams 服務系統管理員或商務用 Skype 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-172">To view activity reports, you must be a global admin in Office 365, Teams service admin, or Skype for Business admin.</span></span>

| <span data-ttu-id="f7ec6-173">問問自己</span><span class="sxs-lookup"><span data-stu-id="f7ec6-173">Ask yourself</span></span> | <span data-ttu-id="f7ec6-174">動作</span><span class="sxs-lookup"><span data-stu-id="f7ec6-174">Action</span></span> |
|--------------|--------|
| <br><span data-ttu-id="f7ec6-175">誰需要查看活動報告，以及他們是否具備檢視報告的正確權限？</span><span class="sxs-lookup"><span data-stu-id="f7ec6-175">Who needs to see the Teams usage reports, and do they have the correct role to view them?</span></span> |<ul><li><span data-ttu-id="f7ec6-176">如果您不想將系統管理員角色指派給使用者，您可以 [指派報告讀取者角色](teams-activity-reports.md#reports-reader-role)。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-176">If you don't want to assign an admin role to a user, you can [assign the Reports reader role](teams-activity-reports.md#reports-reader-role).</span></span></li><li><span data-ttu-id="f7ec6-177">如需如何在 Azure Active Directory 中指派系統管理員角色的詳細資訊，請參閱[角色和權限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 和[查看和指派角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-177">See [Roles and permissions](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [View and assign roles](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal) to learn how to assign admin roles in Azure Active Directory.</span></span></li></ul> |
|||

### <a name="app-templates"></a><span data-ttu-id="f7ec6-178">應用程式範本</span><span class="sxs-lookup"><span data-stu-id="f7ec6-178">App templates for Teams</span></span>

<span data-ttu-id="f7ec6-179">應用程式範本是適用於 Microsoft Teams 生產環境的應用程式，其由社群推動、為開放原始碼，而且可在 GitHub 上取得。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-179">App templates are production-ready apps for Microsoft Teams that are community driven, open-source, and available on GitHub.</span></span> <span data-ttu-id="f7ec6-180">每個範本都包含詳細的指示，可用來部署和安裝組織的應用程式，並提供了一個可立即使用的應用程式，讓您立即安裝並開始使用。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-180">Each contains detailed instructions for deploying and installing that app for your organization, providing a ready-to-use app that you can install and begin using immediately.</span></span> <span data-ttu-id="f7ec6-181">同時也提供完整的原始程式碼，您可以在其中詳細探索，或衍生程式碼並加以變更，以符合您的特定需求。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-181">The complete source code is available as well, so you can explore it in detail,or fork the code and alter it to meet your specific needs.</span></span>

| <span data-ttu-id="f7ec6-182">問問自己</span><span class="sxs-lookup"><span data-stu-id="f7ec6-182">Ask yourself</span></span> | <span data-ttu-id="f7ec6-183">動作</span><span class="sxs-lookup"><span data-stu-id="f7ec6-183">Action</span></span> |
|--------------|--------|
| <span data-ttu-id="f7ec6-184">我是否要安裝任何 Teams 應用程式範本，例如 Icebreaker？</span><span class="sxs-lookup"><span data-stu-id="f7ec6-184">Do I want to install any Teams app templates, such as Icebreaker?</span></span> |<span data-ttu-id="f7ec6-185">若要深入瞭解，請參閱 [Teams 的應用程式範本](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates?toc=MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) (英文)。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-185">To learn more, read [App templates for Teams](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates?toc=MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span></span>|
|||


## <a name="next-steps"></a><span data-ttu-id="f7ec6-186">後續步驟</span><span class="sxs-lookup"><span data-stu-id="f7ec6-186">Next steps</span></span>
- <span data-ttu-id="f7ec6-187">[推廣採用](adopt-microsoft-teams-landing-page.md)精選應用程式，例如 Planner。</span><span class="sxs-lookup"><span data-stu-id="f7ec6-187">[Drive adoption](adopt-microsoft-teams-landing-page.md) of featured apps, such as Planner.</span></span>
- [<span data-ttu-id="f7ec6-188">推出會議和研討會</span><span class="sxs-lookup"><span data-stu-id="f7ec6-188">Roll out meetings & conferencing</span></span>](deploy-meetings-microsoft-teams-landing-page.md)
- [<span data-ttu-id="f7ec6-189">推出雲端語音</span><span class="sxs-lookup"><span data-stu-id="f7ec6-189">Roll out cloud voice</span></span>](cloud-voice-landing-page.md)


