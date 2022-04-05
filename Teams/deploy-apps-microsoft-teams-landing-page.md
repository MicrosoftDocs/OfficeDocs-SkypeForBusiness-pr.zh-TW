---
title: 了解 Microsoft Teams 中的應用程式
ms.reviewer: null
description: 了解應用程式，並根據您的組織設定檔和商務需求，決定 Teams 中允許哪些應用程式。
ms.topic: article
author: guptaashish
ms.author: guptaashish
manager: prkosh
audience: admin
ms.date: 04/05/2022
ms.service: msteams
ms.collection:
  - M365-collaboration
f1.keywords:
  - NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
  - Microsoft Teams
ms.custom: seo-marvel-apr2020
---
# <a name="about-apps-in-microsoft-teams"></a>關於 Microsoft Teams 中的應用程式

應用程式是一種將工作場所工具和服務彙集在一起，並與其他人共同合作的方式。 應用程式可協助使用者提高工作效率、共同作業，以及提高工作效率。 組織會使用應用程式與客戶聯繫、提供服務及共用資訊。 應用程式可讓使用者在聊天、Teams和頻道中更有效。 例如，使用者在 Teams 中使用釘釘的日曆來與其他人快速共同作業、提供 bot 功能的應用程式，告知 Teams 頻道中的 QoS Web 服務使用者，以及一個 App 來共用工作，並將工作指派給頻道中的各種使用者。

我們在市集中廣泛選用經過驗證且安全的應用程式，讓使用者能夠存取貴組織每天所需的工具和服務。 Microsoft Teams應用程式是 Web 型 SaaS 應用程式，不需要部署。 使用者只能根據您Teams，才能在應用程式中使用 App。 做為系統管理員，您只要核准或封鎖貴組織使用者的任何應用程式。 您可以控制會議、聊天和頻道中所有使用者的應用程式可用性。

若要為使用者提供他們所需的應用程式，請繼續閱讀以瞭解應用程式類型，以及使用者在何處存取這些應用程式。 若要深入瞭解 App 的使用，請參閱使用者 [應用程式概觀](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)

<!--- Commenting the previous content as part of this article revamp.

Apps let users find content from their favorite services and share it in Teams. They let you do tasks such as pin services at the top of a channel, automate notifications using bots, or share and assign tasks.

--->

您的使用者可在其中使用的不同應用程式類型Teams：

* [屬於應用程式核心Teams](#core-apps)。
* Microsoft [建立的其他 App](#microsoft-provided-apps)。
* [合作夥伴的第](#third-party-apps-validated-by-microsoft) 三方應用程式 (Microsoft) 。
* [由您自己的](#custom-apps) 組織所建立自訂應用程式。

## <a name="core-apps"></a>核心應用程式

某些預設功能 ，例如活動Teams、頻道、聊天、日曆和通話，預設為使用者易於存取。 做為系統管理員，您可以使用設定策略修改 [預設行為](/microsoftteams/teams-app-setup-policies)。

:::image type="content" source="media/core-apps-pinned1.png" alt-text="核心應用程式是預設釘Teams的應用程式。" lightbox="media/core-apps-pinned2.png":::

## <a name="microsoft-provided-apps"></a>Microsoft 提供的 App

Microsoft 提供許多應用程式以改善生產力和共同作業。 您和使用者可以找到這些應用程式，請尋找列為系統管理中心Publisher Microsoft，或列在小組市Publisher中的提供者。

Teams 隨附一組內建的應用程式，包括清單、工作、稱讚、核准等。 建議您在初始推出 Teams 時包括 Teams 的精選應用程式，例如 Planner。

:::image type="content" source="media/microsoft-apps-in-tac1.png" alt-text="系統管理Teams中的 Microsoft 應用程式" lightbox="media/microsoft-apps-in-tac2.png":::

## <a name="third-party-apps-validated-by-microsoft"></a>Microsoft 驗證的協力廠商應用程式

除了 Microsoft 提供的 App 之外，您還可以使用 Microsoft 驗證的協力廠商應用程式。 Microsoft 會先驗證這些 App 的功能和安全性，然後再在市Teams提供。

<!--- TBD: Link to the new article later when it is created.
To understand the benefits of app validation, see [validation of third-party apps]().

--->

:::image type="content" source="media/3p-apps-in-teams.png" alt-text="市/市中協力廠商應用程式Teams範例":::

<!--- TBD: Check the relevance of this link here.
For more information, see [Microsoft Teams App Security and Compliance](/microsoft-365-app-certification/teams/teams-apps).
--->

## <a name="custom-apps"></a>自訂應用程式

貴組織中開發人員所建立的應用程式稱為自訂應用程式。 這類應用程式的開發是受貴組織的特定需求所委託，而且您擁有允許或不允許這類 App 的控制項。 貴組織的開發人員可以使用與 Microsoft Power Platform Teams快速建立自訂低程式碼[解決方案](/microsoftteams/platform/samples/teams-low-code-solutions)。

在系統管理員允許使用自訂應用程式之後，使用者按一下市集左側導Teams為您的組織建立這類應用程式。

:::image type="content" source="media/built-for-your-org1.png" alt-text="在桌面應用程式中Teams自訂Teams應用程式" lightbox="media/built-for-your-org2.png":::

### <a name="understand-sideloading-of-custom-apps"></a>瞭解自訂應用程式的側載

在開發自訂 App 之前，開發人員會先將應用程式新增到市集測試，以自行測試，或與小組一起測試應用程式，然後再將應用程式發佈給使用者。 這個方法稱為 App 的側載，並僅適用于自訂應用程式。

開發人員可以側載應用程式，讓特定小組成員使用，通常是測試開發不足的應用程式。 如果允許側載，這不需要系統管理員核准。 做為系統管理員，您可以禁止任何開發人員進行側載。

如果您不允許側載，開發人員仍可在測試租使用者中測試 [其應用程式](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant)。 自訂應用程式開發完成後，開發人員會要求系統管理員將其自訂應用程式發佈給使用者。 若要瞭解詳細資料， [請參閱如何發佈自訂應用程式](/microsoftteams/upload-custom-apps)。 做為系統管理員，您可以允許或不允許特定使用者使用自訂應用程式。

### <a name="about-app-templates"></a>關於應用程式範本

適用于 Teams 的應用程式範本是 Microsoft 為說明熱門使用案例、展示應用程式開發最佳做法，以及提供開放來源應用程式供開發人員擴充以建立自訂應用程式所建立的功能型生產範例應用程式。 貴組織的開發人員可針對貴組織的需求自訂應用程式範本，只需對可用於 GitHub 中的程式碼進行變更。 您做為系統管理員，會為使用者提供這些 App 做為自訂應用程式。

若要進一Microsoft Teams[，請參閱應用程式範本](https://adoption.microsoft.com/microsoft-teams/app-templates/)。

## <a name="understand-app-capabilities"></a>瞭解應用程式功能

訊息應用程式包含來自頻道或聊天 App 的內容。 會議可擴展應用程式將開發人員的應用程式整合在會議中，並提供回應式會議內體驗。 為了提供各種功能，應用程式開發人員會利用下列應用程式功能。

Bot 會提供解答、更新和協助。 您可以與這些一對一聊天，或在頻道內聊天。 他們可以協助進行任務管理、排程等工作。 例如，您可以使用 Polly 應用程式建立快速問卷、取得意見反應，以及執行脈動檢查。

釘在頻道頂端的定位點，讓您以網頁式體驗與內容和服務互動。
連接器會提供您經常使用之服務的內容 (更新，例如 Jira Cloud 和 Bitbucket) 直接進入頻道交談。

訊息擴充功能是插入應用程式內容或處理訊息的快捷方式，而使用者不需要離開交談。 訊息擴充功能可以具有使用者快速尋找外部內容的搜尋命令，並將它插入郵件或動作命令中。

若要查看對應至功能Teams的常見使用案例，請參閱將您的使用案例對應[Teams應用程式功能](/microsoftteams/platform/concepts/design/map-use-cases)。

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
| <br>Who needs to see the activity reports, and do they have the correct permissions to view them? |<ul><li>If you don't want to assign an admin role to a user, you can [assign the Reports reader role](teams-activity-reports.md#reports-reader-role).</li><li>See [Roles and permissions](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [View and assign roles](/azure/active-directory/users-groups-roles/directory-manage-roles-portal) for information about assigning admin roles in Azure Active Directory.</li></ul> |

--->
