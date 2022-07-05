---
title: 了解 Microsoft Teams 中的應用程式
ms.reviewer: ''
description: 了解應用程式，並根據您的組織設定檔和商務需求，決定 Teams 中允許哪些應用程式。
ms.topic: article
author: guptaashish
ms.author: guptaashish
manager: prkosh
audience: admin
ms.date: 04/05/2022
ms.service: msteams
ms.subservice: teams-apps
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020; intro-overview; intro-hub-or-landing
ms.openlocfilehash: f802506ff815745aaf555501e37171ebddfc7f91
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615859"
---
# <a name="about-apps-in-microsoft-teams"></a>關於 Microsoft Teams 中的應用程式

應用程式是彙集工作場所工具與服務，並與他人共同作業的絕佳方式。 應用程式可協助使用者在日常工作中提高生產力、共同作業並發揮效率。 組織會使用應用程式與客戶聯繫、提供服務及分享資訊。 應用程式可讓使用者在 Teams 聊天、會議和頻道中更有效率。 例如，使用者在 Teams 中使用釘選行事曆快速與其他人共同作業、應用程式具有機器人功能，可通知使用者 Teams 頻道中 Web 服務的 QoS，以及共用和指派工作給頻道中各種使用者的應用程式。

在我們 Microsoft Store 中各式各樣經過驗證且安全的應用程式，可供使用者取得貴組織每天需要的工具和服務。 Microsoft Teams 應用程式是不需要部署的 Web SaaS 應用程式。 使用者只能根據您提供的[權限](https://admin.teams.microsoft.com/policies/app-permission)，使用 Teams 中的應用程式。 身為系統管理員，您只要核准或封鎖貴組織使用者使用任何應用程式即可。 您可以控制所有使用者在會議、聊天和頻道中的應用程式可用性。

若要為使用者提供所需的應用程式，請繼續閱讀以瞭解應用程式類型，以及使用者存取這些應用程式的位置。 若要深入了解應用程式的使用，請參閱 [適用於使用者的應用程式概觀](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)。

<!--- Commenting the previous content as part of this article revamp.

Apps let users find content from their favorite services and share it in Teams. They let you do tasks such as pin services at the top of a channel, automate notifications using bots, or share and assign tasks.

--->

您的使用者在 Teams 中可使用的不同類型應用程式包括：

* [屬於 Teams 一部分的核心應用程式](#core-apps)。
* [Microsoft 創建的其他應用程式](#microsoft-provided-apps)。
* 合作夥伴 (經 Microsoft 驗證) 的[協力廠商應用程式](#third-party-apps-validated-by-microsoft)。
* 由您自己的組織創建的[自訂應用程式](#custom-apps)。

## <a name="core-apps"></a>核心應用程式

某些預設功能 (例如活動摘要、Teams 頻道、聊天、行事曆和通話) 預設為可用，並且釘選供使用者輕鬆存取。 身為系統管理員，您可以使用[設定原則](/microsoftteams/teams-app-setup-policies)來修改預設行為。

:::image type="content" source="media/core-apps-pinned1.png" alt-text="核心應用程式是預設釘選在 Teams 中的應用程式。" lightbox="media/core-apps-pinned2.png":::

## <a name="microsoft-provided-apps"></a>使用 Microsoft 提供的應用程式

Microsoft 提供許多應用程式來提升生產力和共同作業。 您和使用者可透過在系統管理中心尋找 Microsoft 列為「發行者」(Publisher)，或在 Teams 市集中列為「提供者」(Provider)，以找到這些應用程式。

Teams 隨附一組內建的應用程式，包括清單、工作、稱讚、核准等。 建議您在初始推出 Teams 時包括 Teams 的精選應用程式，例如 Planner。

:::image type="content" source="media/microsoft-apps-in-tac1.png" alt-text="Microsoft Teams 系統管理中心的 Microsoft 應用程式" lightbox="media/microsoft-apps-in-tac2.png":::

## <a name="third-party-apps-validated-by-microsoft"></a>由 Microsoft 驗證的協力廠商應用程式

除了 Microsoft 提供的應用程式，您還可以使用 Microsoft 認證的協力廠商應用程式。 Microsoft 在 Teams 市集中提供這些應用程式之前，先驗證這些應用程式的功能和安全性。 若要瞭解應用程式驗證的優點，請參閱 [驗證協力廠商應用程式](overview-of-app-validation.md)。

:::image type="content" source="media/3p-apps-in-teams.png" alt-text="Teams 市集中協力廠商應用程式的範例":::

## <a name="custom-apps"></a>自訂應用程式

由貴組織中的開發人員建立的應用程式稱為自訂應用程式。 這類應用程式為因應貴組織的特定需求委任開發，而且您有允許或不允許這類應用程式的控制項。 貴組織的開發人員可以使用與 [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions) 整合的 Teams 來快速建立自訂低程式碼解決方案。

當系統管理員允許使用自訂應用程式後，使用者可以在 Teams 市集的左側瀏覽中按一下 **[專為貴組織打造]** 來尋找這類應用程式。

:::image type="content" source="media/built-for-your-org1.png" alt-text="Teams 傳統型應用程式中的 Teams 市集自訂應用程式" lightbox="media/built-for-your-org2.png":::

### <a name="understand-sideloading-of-custom-apps"></a>瞭解自訂應用程式側載

開發自訂應用程式，並在發佈給使用者之前，開發人員先測試應用程式，透過將應用程式新增至 Microsoft Store 以自行測試，或是與側載應用程式的團隊一起測試。 此方法稱為側載應用程式，僅適用於自訂應用程式。

開發人員可以側載應用程式，將它提供給特定團隊的成員使用，通常是用來測試開發中的應用程式。 如果允許側載，則不需要系統管理員核准。 身為系統管理員，您可以不允許任何開發人員側載。

如果您不允許側載，開發人員仍然可以在[測試租用戶](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant)中測試其應用程式。 自訂應用程式開發完成後，開發人員會要求系統管理員將自訂應用程式發佈給使用者。 如需詳細資料，請參閱 [如何發佈自訂應用程式](/microsoftteams/upload-custom-apps)。 身為系統管理員，您可以允許或不允許特定使用者使用自訂應用程式。

### <a name="about-app-templates"></a>關於應用程式範本

Teams 的應用程式範本是由 Microsoft 建立的功能化、生產就緒的範例應用程式，用來說明熱門使用案例、展示應用程式開發的最佳做法，以及提供開放原始碼應用程式，讓開發人員可以擴充以建立自訂應用程式。 您的組織開發人員需要對 GitHub 中可用的程式碼進行簡單的變更，以自訂貴組織的應用程式範本。 身為系統管理員，您可以提供這些應用程式做為使用者的自訂應用程式。

若要深入了解，請參閱 [Microsoft Teams 應用程式範本](https://adoption.microsoft.com/microsoft-teams/app-templates/)。

## <a name="understand-app-capabilities"></a>瞭解應用程式功能

為了提供讓使用者在 Teams 內工作的豐富體驗，應用程式開發人員可運用下列應用程式功能。 訊息擴充功能可讓使用者與您的 Web 服務 Teams 用戶端互動。 它們會在外部系統中搜尋或開始動作。 您可以使用豐富的格式化卡片，將互動的結果傳送給 Teams 用戶端。 會議擴充性應用程式整合了開發人員在會議中的應用程式，並提供回應式的會議內體驗。

Bot 也稱為聊天機器人或交談機器人。 它是執行簡單且重複的工作的應用程式。 聊天機器人互動可以是快速的問題與解答，也可以是提供存取服務或協助的複雜交談。 使用者可以與一對一或頻道中的機器人聊天。 例如，您可以使用 [Polly] 應用程式建立快速問卷、取得意見反應，以及執行脈搏檢查。

索引標籤是釘選在頻道或聊天頂端的 Teams 感知網頁。 索引標籤可讓您以類似網頁的體驗與內容和服務互動。 您可以在小組、群組聊天或個別使用者的個人應用程式內，新增索引標籤做為頻道的一部分。

Webhooks 和連接器會從使用者經常使用提供內容和更新的服務 (例如 Jira Cloud 和 Bitbucket) 直接進入頻道交談。 使用此功能的應用程式可以與外部應用程式通訊，並可從外部服務傳送或接收通知和訊息。

訊息中心擴充功能是插入應用程式內容或處理郵件的快速鍵，使用者不需要離開交談。 訊息擴充功能可以具有搜尋命令，讓使用者快速找到外部內容，並將其插入郵件或動作命令中。

若要檢視對應至 Teams 功能的常見使用案例，請參閱 [將您的使用案例對應至 Teams 應用程式功能](/microsoftteams/platform/concepts/design/map-use-cases)。

<!--- TBD: Admins do many considerations and decisions around app adoption and app governance. These are to be covered in a separate article. Commenting the below content for now as part of this article revamp.

## Apps deployment decisions

Teams provides a great out-of-the-box collaboration experience for your organization, and most organizations find that the default settings work for them. This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change. We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions). The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.

## Core deployment decisions

These are the apps settings that most organizations want to change (if the Teams default settings don't work for them).

### App availability settings

Teams provides many apps published by Microsoft and by third parties to engage users, support productivity, and integrate commonly used business services into Teams.
Get apps from the Teams Store. By default, all apps, including custom apps that you've submitted via the [Teams Store approval process](/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process), are turned on for all users. For example, users can use the Planner app to build and manage team tasks in Teams.

By default, all Microsoft-provided, third-party, and custom apps are available, and you can turn individual apps on or off. There are org-wide settings that let you turn all third-party and/or custom apps on or off for your entire organization.

| Ask yourself | Action |
|--------------|--------|
|Will you change the default Teams apps settings? | For more information about policies and settings that you can use to manage apps in your organization, see [Admin settings for apps in Microsoft Teams](admin-settings.md).|

### App permissions and other considerations

Apps are consented to by users and managed by the admin or IT pro through policies. However, app permissions and risk profile are defined in the app itself.

| Ask yourself | Action |
|--------------|--------|
|<br>Which apps do I want to allow access to? Which ones do I not want to allow access to?  | <ul><li>See [Microsoft Teams apps permissions and considerations](app-permissions.md) for a list of things you should consider when allowing access to an app, bot, tab, or connector.</li><li>See [Manage your apps in the Microsoft Teams admin center](manage-apps.md) for information about making an app available to users in your organization.</li></ul>|

--->

<!--- TBD: Rewrite this to talk about bots and tabs as a capability of apps. Admins do not govern bots, tabs, etc. Admins only govern apps that contain capabilities such as connectors, bots, etc. This writeup gives an impression that admins manage apps + bots + tabs + connectors, etc.

### Bots for private chats and channels

Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about. Bots allow users to interact with cloud services such as task management, scheduling, and polling in a Teams chat. Teams supports bots in private chats and channels. Administrators can control whether the use of bots is allowed in a Microsoft 365 or Office 365 organization.

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow custom bots in my organization?|For more information about adding bots, see [Add bots for private chats and channels in Microsoft Teams](/microsoftteams/platform/bots/what-are-bots). For information about turning custom bots on or off, see [Admin settings for apps in Microsoft Teams](admin-settings.md).|

### Built-in and custom tabs

Owners and team members can add tabs to a channel, private chat, and group chat to help integrate their cloud services. Add tabs to help users access and manage the data they need or use the most. In channels, the Conversations and Files tabs are created by default. In every private chat, the Conversations, Files, Organization, and Activity tabs are created by default. In addition to these built-in tabs, you can design and add custom tabs. To learn about turning Teams apps on or off for your organization, read [Admin settings for apps in Teams](admin-settings.md).

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow custom tabs in my organization?|For more information, see [Use built-in and custom tabs in Teams](/microsoftteams/platform/tabs/what-are-tabs).|

### Custom connectors

Connectors keep your team current by delivering content and updates from services you frequently use directly into a channel. With connectors, your Teams users can receive updates from popular services such as Trello, Wunderlist, GitHub, and Azure DevOps Services in their Teams chats.

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow users to create custom connectors?|For more information, see [Use custom connectors in Teams](office-365-custom-connectors.md).|

--->

<!--- TBD: Activity reports is not part of app overview. Commenting for now. To be reused in a different article later.

### Activity reports

You can use activity reports to see how users in your organization are using Teams. For example, if some don't use Teams yet, they might not know how to get started or understand how they can use Teams to be more productive and collaborative. Your organization can use the activity reports to decide where to prioritize training and communication efforts. To view activity reports, you must be a global admin in Microsoft 365 or Office 365, Teams service admin, or Skype for Business admin.

| Ask yourself | Action |
|--------------|--------|
| Who needs to see the activity reports, and do they have the correct permissions to view them? |<ul><li>If you don't want to assign an admin role to a user, you can [assign the Reports reader role](teams-activity-reports.md#reports-reader-role).</li><li>See [Roles and permissions](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [View and assign roles](/azure/active-directory/users-groups-roles/directory-manage-roles-portal) for information about assigning admin roles in Azure Active Directory.</li></ul> |

--->
