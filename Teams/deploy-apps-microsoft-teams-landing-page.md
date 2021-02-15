---
title: Microsoft Teams 中的應用程式、Bot 和連接器
ms.reviewer: ''
description: 了解應用程式、Bot 和連接器，以及如何根據貴組織的設定檔和商務需求，決定要在 Microsoft Teams 中部署哪些應用程式、Bot 和連接器。
ms.topic: article
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: admin
ms.date: 02/10/2021
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d1a6462d0cb1581142eb2f5076e6b2ebad2b9003
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196517"
---
# <a name="apps-bots--connectors-in-microsoft-teams"></a><span data-ttu-id="52bcc-103">Microsoft Teams 中的應用程式、Bot 和連接器</span><span class="sxs-lookup"><span data-stu-id="52bcc-103">Apps, bots, & connectors in Microsoft Teams</span></span>

<span data-ttu-id="52bcc-104">應用程式可讓您透過喜好服務尋找內容，並在 Teams 中分享它。</span><span class="sxs-lookup"><span data-stu-id="52bcc-104">Apps let you find content from your favorite services and share it in Teams.</span></span> <span data-ttu-id="52bcc-105">他們可幫助您執行作業，例如在頻道最上方釘選服務、與 Bot 聊天或共用及指派工作。</span><span class="sxs-lookup"><span data-stu-id="52bcc-105">They help you do things such as pin services at the top of a channel, chat with bots, or share and assign tasks.</span></span> <span data-ttu-id="52bcc-106">若要深入了解，請參閱[ Teams 中的應用程式概觀](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)。</span><span class="sxs-lookup"><span data-stu-id="52bcc-106">To learn more, read [Overview of apps in Teams](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0).</span></span> 

<span data-ttu-id="52bcc-107">您可以使用隨著 Microsoft Teams 提供的應用程式、使用認證的協力廠商應用程式和範本，以及透過建立您自己的自訂應用程式，將應用程式新增到您的 Teams 部署。</span><span class="sxs-lookup"><span data-stu-id="52bcc-107">You can add apps to your Teams deployment by using the apps provided with Microsoft Teams, by using certified third-party apps and templates, and by creating your own custom apps.</span></span>

## <a name="use-microsoft-provided-apps"></a><span data-ttu-id="52bcc-108">使用 Microsoft 提供的應用程式</span><span class="sxs-lookup"><span data-stu-id="52bcc-108">Use Microsoft-provided apps</span></span>

<span data-ttu-id="52bcc-109">Teams 隨附一組內建的應用程式，包括清單、工作、稱讚、核准等。</span><span class="sxs-lookup"><span data-stu-id="52bcc-109">Teams comes with a set of built-in apps, including Lists, Tasks, Praise, Approvals, and more.</span></span> <span data-ttu-id="52bcc-110">建議您在一開始推出 Teams 時能夠包含 Teams 的精選應用程式，例如 Planner。</span><span class="sxs-lookup"><span data-stu-id="52bcc-110">We recommend that you include Teams featured apps - such as Planner - in your initial Teams rollout.</span></span> <span data-ttu-id="52bcc-111">在推廣 Teams 的採用時，新增其他應用程式、Bot 和連接器。</span><span class="sxs-lookup"><span data-stu-id="52bcc-111">Add other apps, bots, & connectors as you drive Teams adoption.</span></span>

## <a name="use-third-party-apps"></a><span data-ttu-id="52bcc-112">使用協力廠商應用程式</span><span class="sxs-lookup"><span data-stu-id="52bcc-112">Use third-party apps</span></span>

<span data-ttu-id="52bcc-113">除了 Microsoft 提供的應用程式，您還可以使用 Microsoft 認證的協力廠商應用程式。</span><span class="sxs-lookup"><span data-stu-id="52bcc-113">In addition to Microsoft-provided apps, you can use Microsoft-certified third-party apps.</span></span> <span data-ttu-id="52bcc-114">Microsoft 與 Microsoft 365 開發人員合作夥伴合作，以提供以加快使用 Teams 應用程式和增益集的決策所需的資訊。如需詳細資訊，請參閱 [Microsoft Teams 應用程式安全性與合規性](https://docs.microsoft.com/microsoft-365-app-certification/teams/teams-apps)。</span><span class="sxs-lookup"><span data-stu-id="52bcc-114">Microsoft works with  Microsoft 365 developer partners to provide the information needed to expedite decisions about using Teams apps and add-ins. For more information, see [Microsoft Teams App Security and Compliance](https://docs.microsoft.com/microsoft-365-app-certification/teams/teams-apps).</span></span>

## <a name="use-teams-templates"></a><span data-ttu-id="52bcc-115">使用 Teams 範本</span><span class="sxs-lookup"><span data-stu-id="52bcc-115">Use Teams templates</span></span>

<span data-ttu-id="52bcc-116">您也可以使用 [Teams 範本](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)，其為針對由社群驅動、開放原始碼且可在 GitHub 上取得的適用於 Microsoft Teams 的生產就緒應用程式。</span><span class="sxs-lookup"><span data-stu-id="52bcc-116">You can also use [Teams templates](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json), production-ready apps for Microsoft Teams that are community driven, open-source, and available on GitHub.</span></span>

## <a name="create-custom-apps"></a><span data-ttu-id="52bcc-117">建立自訂應用程式</span><span class="sxs-lookup"><span data-stu-id="52bcc-117">Create custom apps</span></span>

<span data-ttu-id="52bcc-118">您可以使用與 [Microsoft Power Platform](teams-power-platfom-integration.md) 的 Teams 整合來快速建立自訂低程式碼解決方案。</span><span class="sxs-lookup"><span data-stu-id="52bcc-118">You can quickly build custom low-code solutions by using Teams integration with [Microsoft Power Platform](teams-power-platfom-integration.md).</span></span> <span data-ttu-id="52bcc-119">您也可以建立自己的自訂應用程式，以符合您的商務需求。</span><span class="sxs-lookup"><span data-stu-id="52bcc-119">You can also create your own custom app to suit your business needs.</span></span> <span data-ttu-id="52bcc-120">如需詳細資訊，請參閱[為 Microsoft Teams 建立應用程式](https://docs.microsoft.com/microsoftteams/platform/overview)。</span><span class="sxs-lookup"><span data-stu-id="52bcc-120">For more information, see [Build apps for Microsoft Teams](https://docs.microsoft.com/microsoftteams/platform/overview).</span></span>  


## <a name="apps-deployment-decisions"></a><span data-ttu-id="52bcc-121">應用程式部署決策</span><span class="sxs-lookup"><span data-stu-id="52bcc-121">Apps deployment decisions</span></span>

<span data-ttu-id="52bcc-p105">Teams 為您的組織提供絕佳的現成共同作業體驗，而大部分組織認為預設設定就能滿足其需求。本文可協助您決定是否要根據組織的設定檔和商務需求來變更任何預設設定，並逐步引導您完成每個變更。我們已將設定分割成兩個群組，從[您最可能進行的變更](#core-deployment-decisions)的核心集開始。根據組織的需求，第二個群組包括您可能想要設定的[其他設定](#additional-deployment-decisions)。</span><span class="sxs-lookup"><span data-stu-id="52bcc-p105">Teams provides a great out-of-the-box collaboration experience for your organization, and most organizations find that the default settings work for them. This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change. We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions). The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="52bcc-126">核心部署決策</span><span class="sxs-lookup"><span data-stu-id="52bcc-126">Core deployment decisions</span></span>

<span data-ttu-id="52bcc-127">這些應用程式設定是大部分組織想要變更的 (如果 Teams 的預設設定不符合組織的需求)。</span><span class="sxs-lookup"><span data-stu-id="52bcc-127">These are the apps settings that most organizations want to change (if the Teams default settings don't work for them).</span></span>

### <a name="app-availability-settings"></a><span data-ttu-id="52bcc-128">應用程式可用性設定</span><span class="sxs-lookup"><span data-stu-id="52bcc-128">App availability settings</span></span> 

<span data-ttu-id="52bcc-129">Teams 提供許多由 Microsoft 和第三方發行的應用程式，以吸引使用者、支援生產活動，並將常用的商務服務整合到 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="52bcc-129">Teams provides many apps published by Microsoft and by third parties to engage users, support productivity, and integrate commonly used business services into Teams.</span></span> <span data-ttu-id="52bcc-130">從 Teams 市集取得應用程式。</span><span class="sxs-lookup"><span data-stu-id="52bcc-130">Get apps from the Teams Store.</span></span> <span data-ttu-id="52bcc-131">根據預設，所有的應用程式 (包括透過 [Teams 市集核准程序](https://docs.microsoft.com/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process)提交的自訂應用程式) 都會針對所有使用者開啟。</span><span class="sxs-lookup"><span data-stu-id="52bcc-131">By default, all apps, including custom apps that you've submitted via the [Teams Store approval process](https://docs.microsoft.com/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process), are turned on for all users.</span></span> <span data-ttu-id="52bcc-132">例如，使用者可以使用 Planner 應用程式來建立和管理 Teams 中的小組工作。</span><span class="sxs-lookup"><span data-stu-id="52bcc-132">For example, users can use the Planner app to build and manage team tasks in Teams.</span></span>

<span data-ttu-id="52bcc-133">根據預設，您可使用所有由 Microsoft 及協力廠商提供和自訂的應用程式，並且可開啟或關閉個別應用程式。</span><span class="sxs-lookup"><span data-stu-id="52bcc-133">By default, all Microsoft-provided, third-party, and custom apps are available, and you can turn individual apps on or off.</span></span> <span data-ttu-id="52bcc-134">這是全組織的設定，可讓您開啟或關閉整個組織的所有協力廠商的和/或自訂的應用程式。</span><span class="sxs-lookup"><span data-stu-id="52bcc-134">There are org-wide settings that lets you turn all third-party and/or custom apps on or off for your entire organization.</span></span>

| <span data-ttu-id="52bcc-135">問問自己</span><span class="sxs-lookup"><span data-stu-id="52bcc-135">Ask yourself</span></span> | <span data-ttu-id="52bcc-136">動作</span><span class="sxs-lookup"><span data-stu-id="52bcc-136">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="52bcc-137">您是否會變更預設的 Teams 應用程式設定？</span><span class="sxs-lookup"><span data-stu-id="52bcc-137">Will you change the default Teams apps settings?</span></span> | <span data-ttu-id="52bcc-138">如需可用來管理組織中的應用程式的原則和設定的詳細資訊，請參閱 [Microsoft Teams 中應用程式的系統管理設定](admin-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="52bcc-138">For more information about policies and settings that you can use to manage apps in your organization, see [Admin settings for apps in Microsoft Teams](admin-settings.md).</span></span>|
|||

### <a name="app-permissions-and-other-considerations"></a><span data-ttu-id="52bcc-139">應用程式權限和其他考量</span><span class="sxs-lookup"><span data-stu-id="52bcc-139">App permissions and other considerations</span></span>

<span data-ttu-id="52bcc-140">應用程式經過使用者同意，並且由系統管理員或 IT 專業人員透過原則管理。</span><span class="sxs-lookup"><span data-stu-id="52bcc-140">Apps are consented to by users and managed by the admin or IT pro through policies.</span></span> <span data-ttu-id="52bcc-141">不過在絕大多數情況下，應用程式的權限和風險設定檔是在應用程式本身中定義。</span><span class="sxs-lookup"><span data-stu-id="52bcc-141">However, for the most part, an app's permissions and risk profile are defined in the app itself.</span></span> 

| <span data-ttu-id="52bcc-142">問問自己</span><span class="sxs-lookup"><span data-stu-id="52bcc-142">Ask yourself</span></span> | <span data-ttu-id="52bcc-143">動作</span><span class="sxs-lookup"><span data-stu-id="52bcc-143">Action</span></span> |
|--------------|--------|
|<br><span data-ttu-id="52bcc-144">我想允許哪些應用程式的存取權？</span><span class="sxs-lookup"><span data-stu-id="52bcc-144">Which apps do I want to allow access to?</span></span> <span data-ttu-id="52bcc-145">我不想允許哪些應用程式的存取權？</span><span class="sxs-lookup"><span data-stu-id="52bcc-145">Which ones do I not want to allow access to?</span></span>  | <ul><li><span data-ttu-id="52bcc-146">如需在允許應用程式、Bot、索引標籤或連接器的存取權時應考慮的事項清單，請參閱 [Microsoft Teams 應用程式權限和考量事項](app-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="52bcc-146">See [Microsoft Teams apps permissions and considerations](app-permissions.md) for a list of things you should consider when allowing access to an app, bot, tab, or connector.</span></span></li><li><span data-ttu-id="52bcc-147">如需提供應用程式讓貴組織的使用者使用的相關資訊，請參閱[在 Microsoft Teams 系統管理中心管理您的應用程式](manage-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="52bcc-147">See [Manage your apps in the Microsoft Teams admin center](manage-apps.md) for information about making an app available to users in your organization.</span></span></li></ul>|
|||

### <a name="bots-for-private-chats-and-channels"></a><span data-ttu-id="52bcc-148">適用於私人聊天和頻道的 Bot</span><span class="sxs-lookup"><span data-stu-id="52bcc-148">Bots for private chats and channels</span></span>

<span data-ttu-id="52bcc-149">Bot 是自動程式，可回應查詢或可針對使用者感興趣或希望隨時了解的詳細資訊提供更新和通知。</span><span class="sxs-lookup"><span data-stu-id="52bcc-149">Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about.</span></span> <span data-ttu-id="52bcc-150">Bot 可讓使用者與 Teams 聊天中的雲端服務互動，例如工作管理、排程和投票等。</span><span class="sxs-lookup"><span data-stu-id="52bcc-150">Bots allow users to interact with cloud services such as task management, scheduling, and polling in a Teams chat.</span></span> <span data-ttu-id="52bcc-151">Teams 支援在私人聊天和頻道中使用 Bot。</span><span class="sxs-lookup"><span data-stu-id="52bcc-151">Teams supports bots in private chats and channels.</span></span> <span data-ttu-id="52bcc-152">系統管理員可以控制是否允許在 Microsoft 365 或 Office 365 組織中使用 Bot。</span><span class="sxs-lookup"><span data-stu-id="52bcc-152">Administrators can control whether the use of bots is allowed in a Microsoft 365 or Office 365 organization.</span></span>

| <span data-ttu-id="52bcc-153">問問自己</span><span class="sxs-lookup"><span data-stu-id="52bcc-153">Ask yourself</span></span> | <span data-ttu-id="52bcc-154">動作</span><span class="sxs-lookup"><span data-stu-id="52bcc-154">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="52bcc-155">我想要在我的組織中允許使用自訂 Bot 嗎？</span><span class="sxs-lookup"><span data-stu-id="52bcc-155">Do I want to allow custom bots in my organization?</span></span>|<span data-ttu-id="52bcc-156">如需新增 Bot 的詳細資訊，請參閱[在 Microsoft Teams 中新增適用於私人聊天和頻道的 Bot](add-bots.md) (英文)。</span><span class="sxs-lookup"><span data-stu-id="52bcc-156">For more information about adding bots, see [Add bots for private chats and channels in Microsoft Teams](add-bots.md).</span></span> <span data-ttu-id="52bcc-157">如需開啟或關閉自訂 Bot 的詳細資訊，請參閱 [Microsoft Teams 中應用程式的系統管理設定](admin-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="52bcc-157">For information about turning custom bots on or off, see [Admin settings for apps in Microsoft Teams](admin-settings.md).</span></span>|
|||

### <a name="built-in-and-custom-tabs"></a><span data-ttu-id="52bcc-158">內建和自訂索引標籤</span><span class="sxs-lookup"><span data-stu-id="52bcc-158">Built-in and custom tabs</span></span>

<span data-ttu-id="52bcc-159">擁有者與團隊成員可以在頻道、私人聊天和群組聊天中新增索引標籤，協助整合其雲端服務。</span><span class="sxs-lookup"><span data-stu-id="52bcc-159">Owners and team members can add tabs to a channel, private chat, and group chat to help integrate their cloud services.</span></span> <span data-ttu-id="52bcc-160">新增索引標籤可協助使用者存取及管理他們所需或最常用的資料。</span><span class="sxs-lookup"><span data-stu-id="52bcc-160">Add tabs to help users access and manage the data they need or use the most.</span></span> <span data-ttu-id="52bcc-161">在頻道中，預設會建立 [交談] 和 [檔案] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="52bcc-161">In channels, the Conversations and Files tabs are created by default.</span></span> <span data-ttu-id="52bcc-162">在每個私人聊天中，預設會建立 [交談]、[檔案]、[組織] 和 [活動] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="52bcc-162">In every private chat, the Conversations, Files, Organization, and Activity tabs are created by default.</span></span> <span data-ttu-id="52bcc-163">除了這些內建索引標籤之外，您還可以設計及新增自訂索引標籤。</span><span class="sxs-lookup"><span data-stu-id="52bcc-163">In addition to these built-in tabs, you can design and add custom tabs.</span></span> <span data-ttu-id="52bcc-164">若要瞭解如何為組織開啟或關閉Teams 應用程式，請參閱 [Teams 中應用程式的系統管理設定](admin-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="52bcc-164">To learn about turning Teams apps on or off for your organization, read [Admin settings for apps in Teams](admin-settings.md).</span></span>

| <span data-ttu-id="52bcc-165">問問自己</span><span class="sxs-lookup"><span data-stu-id="52bcc-165">Ask yourself</span></span> | <span data-ttu-id="52bcc-166">動作</span><span class="sxs-lookup"><span data-stu-id="52bcc-166">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="52bcc-167">我想要在我的組織中允許使用自訂索引標籤嗎？</span><span class="sxs-lookup"><span data-stu-id="52bcc-167">Do I want to allow custom tabs in my organization?</span></span>|<span data-ttu-id="52bcc-168">如需詳細資訊，請參閱 [在 Teams 中使用內建和自訂索引標籤](built-in-custom-tabs.md)。</span><span class="sxs-lookup"><span data-stu-id="52bcc-168">For more information, see [Use built-in and custom tabs in Teams](built-in-custom-tabs.md).</span></span>|
|||

### <a name="custom-connectors"></a><span data-ttu-id="52bcc-169">自訂連接器</span><span class="sxs-lookup"><span data-stu-id="52bcc-169">Custom connectors</span></span>

<span data-ttu-id="52bcc-170">連接器透過將您經常使用的服務中的內容和更新直接發送到頻道中，進而使您的團隊保持最新狀態。</span><span class="sxs-lookup"><span data-stu-id="52bcc-170">Connectors keep your team current by delivering content and updates from services you frequently use directly into a channel.</span></span> <span data-ttu-id="52bcc-171">有了連接器，您的 Teams 使用者就能在其 Teams 聊天中接收來自來自 Twitter、Trello、Wunderlist、GitHub 和 Azure DevOps 服務等熱門服務的更新。</span><span class="sxs-lookup"><span data-stu-id="52bcc-171">With connectors, your Teams users can receive updates from popular services such as Twitter, Trello, Wunderlist, GitHub, and Azure DevOps Services in their Teams chats.</span></span>

| <span data-ttu-id="52bcc-172">問問自己</span><span class="sxs-lookup"><span data-stu-id="52bcc-172">Ask yourself</span></span> | <span data-ttu-id="52bcc-173">動作</span><span class="sxs-lookup"><span data-stu-id="52bcc-173">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="52bcc-174">我是否要允許使用者建立自訂連接器？</span><span class="sxs-lookup"><span data-stu-id="52bcc-174">Do I want to allow users to create custom connectors?</span></span>|<span data-ttu-id="52bcc-175">如需詳細資訊，請參閱[在 Teams 中使用自訂連接器](office-365-custom-connectors.md)。</span><span class="sxs-lookup"><span data-stu-id="52bcc-175">For more information, see [Use custom connectors in Teams](office-365-custom-connectors.md).</span></span>|
|||

## <a name="additional-deployment-decisions"></a><span data-ttu-id="52bcc-176">其他部署決策</span><span class="sxs-lookup"><span data-stu-id="52bcc-176">Additional deployment decisions</span></span>

<span data-ttu-id="52bcc-177">根據組織的需求和組態而定，您可能會想要變更這些設定。</span><span class="sxs-lookup"><span data-stu-id="52bcc-177">You may want to change these settings, based on your organization's needs and configuration.</span></span>

### <a name="activity-reports"></a><span data-ttu-id="52bcc-178">活動報告</span><span class="sxs-lookup"><span data-stu-id="52bcc-178">Activity reports</span></span>

<span data-ttu-id="52bcc-179">您可以使用活動報告來查看組織中的使用者如何使用 Teams。</span><span class="sxs-lookup"><span data-stu-id="52bcc-179">You can use activity reports to see how users in your organization are using Teams.</span></span> <span data-ttu-id="52bcc-180">例如，如果有人還沒使用 Teams，可能是他們不知道如何開始，或不了解如何使用 Teams 提高生產力和共同作業。</span><span class="sxs-lookup"><span data-stu-id="52bcc-180">For example, if some don't use Teams yet, they might not know how to get started or understand how they can use Teams to be more productive and collaborative.</span></span> <span data-ttu-id="52bcc-181">組織可以使用活動報告來決定要優先進行訓練和溝通的方面。</span><span class="sxs-lookup"><span data-stu-id="52bcc-181">Your organization can use the activity reports to decide where to prioritize training and communication efforts.</span></span> <span data-ttu-id="52bcc-182">若要查看活動報告，您必須是 Microsoft 365 或 Office 365 的全域系統管理員、Teams 服務系統管理員或商務用 Skype 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="52bcc-182">To view activity reports, you must be a global admin in Microsoft 365 or Office 365, Teams service admin, or Skype for Business admin.</span></span>

| <span data-ttu-id="52bcc-183">問問自己</span><span class="sxs-lookup"><span data-stu-id="52bcc-183">Ask yourself</span></span> | <span data-ttu-id="52bcc-184">動作</span><span class="sxs-lookup"><span data-stu-id="52bcc-184">Action</span></span> |
|--------------|--------|
| <br><span data-ttu-id="52bcc-185">誰需要查看活動報告，以及他們是否具備檢視報告的正確權限？</span><span class="sxs-lookup"><span data-stu-id="52bcc-185">Who needs to see the activity reports, and do they have the correct permissions to view them?</span></span> |<ul><li><span data-ttu-id="52bcc-186">如果您不想將系統管理員角色指派給使用者，您可以 [指派報告讀取者角色](teams-activity-reports.md#reports-reader-role)。</span><span class="sxs-lookup"><span data-stu-id="52bcc-186">If you don't want to assign an admin role to a user, you can [assign the Reports reader role](teams-activity-reports.md#reports-reader-role).</span></span></li><li><span data-ttu-id="52bcc-187">如需如何在 Azure Active Directory 中指派系統管理員角色的詳細資訊，請參閱[角色和權限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 和[查看和指派角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)。</span><span class="sxs-lookup"><span data-stu-id="52bcc-187">See [Roles and permissions](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [View and assign roles](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal) for information about assigning admin roles in Azure Active Directory.</span></span></li></ul> |
|||

### <a name="app-templates"></a><span data-ttu-id="52bcc-188">應用程式範本</span><span class="sxs-lookup"><span data-stu-id="52bcc-188">App templates</span></span>

<span data-ttu-id="52bcc-189">應用程式範本是適用於 Microsoft Teams 生產環境的應用程式，其由社群推動、為開放原始碼，而且可在 GitHub 上取得。</span><span class="sxs-lookup"><span data-stu-id="52bcc-189">App templates are production-ready apps for Microsoft Teams that are community driven, open-source, and available on GitHub.</span></span> <span data-ttu-id="52bcc-190">每個範本都包含詳細的指示，可用來部署和安裝組織的應用程式，並提供了一個可立即使用的應用程式，讓您立即安裝並開始使用。</span><span class="sxs-lookup"><span data-stu-id="52bcc-190">Each contains detailed instructions for deploying and installing that app for your organization, providing a ready-to-use app that you can install and begin using immediately.</span></span> <span data-ttu-id="52bcc-191">同時也提供完整的原始程式碼，您可以在其中詳細探索，或衍生程式碼並加以變更，以符合您的特定需求。</span><span class="sxs-lookup"><span data-stu-id="52bcc-191">The complete source code is available as well, so you can explore it in detail, or fork the code and alter it to meet your specific needs.</span></span>

| <span data-ttu-id="52bcc-192">問問自己</span><span class="sxs-lookup"><span data-stu-id="52bcc-192">Ask yourself</span></span> | <span data-ttu-id="52bcc-193">動作</span><span class="sxs-lookup"><span data-stu-id="52bcc-193">Action</span></span> |
|--------------|--------|
| <span data-ttu-id="52bcc-194">我是否要安裝任何 Teams 應用程式範本，例如 Icebreaker？</span><span class="sxs-lookup"><span data-stu-id="52bcc-194">Do I want to install any Teams app templates, such as Icebreaker?</span></span> |<span data-ttu-id="52bcc-195">若要深入瞭解，請參閱 [Teams 的應用程式範本](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates?toc=MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) (英文)。</span><span class="sxs-lookup"><span data-stu-id="52bcc-195">To learn more, read [App templates for Teams](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates?toc=MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span></span>|
|||





