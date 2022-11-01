---
title: 了解 Microsoft Teams 中的應用程式
ms.reviewer: ''
description: 了解應用程式，並根據您的組織設定檔和商務需求，決定 Teams 中允許哪些應用程式。
ms.topic: conceptual
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
audience: admin
ms.service: msteams
ms.subservice: teams-apps
ms.date: 10/01/2022
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020; intro-overview; intro-hub-or-landing
ms.openlocfilehash: 83654452460da41bf72b0feca30d3373de1533ef
ms.sourcegitcommit: ffcc4c7d5688fee28f5fdc8bb8e6b78afb1ee626
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2022
ms.locfileid: "68795425"
---
# <a name="understand-microsoft-teams-apps"></a>了解 Microsoft Teams 應用程式

Teams 中的應用程式可協助使用者整合工作場所的工具和服務，並與其他人共同作業。 例如，使用者在 Teams 中使用釘選行事曆應用程式快速與其他人共同作業、應用程式具有機器人功能，可通知使用者 Teams 頻道中 Web 服務的品質，以及共用和指派工作給頻道中各種使用者的應用程式。 Microsoft Teams 應用程式是 Web 架構的 SaaS 應用程式，不需要在本機部署。

身為系統管理員，您可以設定應用程式控管程式，在使用者的眾多需求與貴組織的 IT 原則、標準和風險設定檔之間取得平衡。

我們豐富的已驗證且安全的 Teams 應用程式 [目錄](https://appsource.microsoft.com/marketplace/apps?product=office%3Bteams&page=1) ，可讓使用者存取貴組織每天需要的工具和服務。 Teams 系統管理中心提供系統管理員企業級的控制項和組態來管理應用程式。 您可以控制每個使用者在會議、聊天和頻道等各種內容中的應用程式可用性。

此文章可協助您了解應用程式類型，以及使用者可從何處存取這些應用程式。 若要深入了解應用程式的使用，請參閱[適用於終端使用者的應用程式概觀](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)。

您的使用者在 Teams 中可使用的不同類型應用程式包括：

* [屬於 Teams 一部分的核心應用程式](#core-apps)。
* [Microsoft 創建的其他應用程式](#apps-created-by-microsoft)。
* 由合作夥伴建立[的協力廠商應用程式](#third-party-apps-created-by-independent-app-developers) (經過 Microsoft) 驗證。
* 由您自己的組織創建的[自訂應用程式](#custom-apps-created-within-an-organization-for-internal-use)。

## <a name="core-apps"></a>核心應用程式

某些 Teams 功能，例如：活動摘要、小組、聊天、行事曆、通話、檔案和作業 (教育界租用戶) 會預設為可用，並且預設為釘選以供終端使用者輕鬆存取。 對於前線員工而言，僅有活動、班次、聊天和通話可供使用和釘選。 身為系統管理員，您可以使用此[設定原則](/microsoftteams/teams-app-setup-policies)來修改預設行為。

:::image type="content" source="media/core-apps-pinned1.png" alt-text="核心應用程式是預設釘選在 Teams 中的應用程式。" lightbox="media/core-apps-pinned2.png":::

## <a name="apps-created-by-microsoft"></a>Microsoft 建立的應用程式

Microsoft 提供許多應用程式來提升生產力和共同作業。 您和使用者可以在 Teams 系統管理中心尋找列為 Publisher 的 Microsoft，或在 Teams 市集中列為「提供者」，藉此找到這些應用程式。

Teams 隨附一組內建的應用程式，包括清單、工作、稱讚、核准等。 建議您在初始推出 Teams 時包括精選的應用程式，例如 Microsoft Planner。

:::image type="content" source="media/microsoft-apps-in-tac1.png" alt-text="顯示 Teams 系統管理中心中 Microsoft 應用程式清單的螢幕擷取畫面。" lightbox="media/microsoft-apps-in-tac2.png":::

## <a name="third-party-apps-created-by-independent-app-developers"></a>由獨立應用程式開發人員建立的協力廠商應用程式

除了 Microsoft 提供的應用程式之外，您還可以使用協力廠商應用程式。 Microsoft 會嚴格驗證所有這些應用程式的功能和安全性。 在 Teams 市集中提供這些應用程式之前，會先執行詳盡的手動和自動化測試，而且即使在即時發佈應用程式之後，許多測試仍會以一般頻率繼續。 若要瞭解應用程式驗證的優點，請參閱 [驗證協力廠商應用程式](overview-of-app-validation.md)。 部分訂閱 [Microsoft 合規性計畫的](overview-of-app-certification.md) 應用程式會經歷驗證以外的多層進一步檢查。

:::image type="content" source="media/3p-apps-in-teams.png" alt-text="Teams 市集中協力廠商應用程式範例的螢幕擷取畫面。":::

## <a name="custom-apps-created-within-an-organization-for-internal-use"></a>在組織內建立供內部使用的自訂應用程式

由貴組織中的開發人員建立的應用程式稱為自訂應用程式 (或企業營運應用程式)。 貴組織可能會針對組織特定的需求委託建立自訂應用程式。 您有權為整個組織或特定使用者允許或封鎖此類應用程式。 貴組織的開發人員可以使用與 [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions) 整合的 Teams 來建立自訂低程式碼解決方案。

當系統管理員允許使用自訂應用程式後，使用者可以在 Teams 市集的左側流覽中選取 **[為您的組織打造** ] 來尋找這類應用程式。

:::image type="content" source="media/built-for-your-org1.png" alt-text="Teams 傳統型應用程式中 Teams 市集中自訂應用程式的螢幕擷取畫面。" lightbox="media/built-for-your-org2.png":::

如需詳細資訊，請參 [閱瞭解及管理自訂及側載的應用程式](custom-app-overview.md)。

## <a name="about-app-templates"></a>關於應用程式範本

使用應用程式開發方法，Microsoft 會建立並提供功能與生產就緒的範例應用程式。 這些應用程式統稱為 Teams 的應用程式範本，並提供給：

* 說明 Teams 中的一些共同作業使用案例。
* 展示應用程式開發的最佳做法和方法。
* 提供開放原始碼應用程式，讓開發人員可以擴充以建立自己的應用程式。

您的組織開發人員會透過簡易變更提供的原始程式碼來自訂應用程式範本。 您為使用者提供這些應用程式做為自訂應用程式，以符合任何組織的需求。

若要深入了解，請參閱 [Microsoft Teams 應用程式範本](https://adoption.microsoft.com/microsoft-teams/app-templates/)。

## <a name="understand-app-capabilities"></a>瞭解應用程式功能

Teams 應用程式功能是可以在應用程式中內建的核心功能，以啟用整合和互動。

:::row:::
    :::column span="":::
    :::column-end:::
    :::column span="3":::
        :::image type="content" source="media/teams-app-capabilities-group.png" alt-text="顯示 Microsoft Teams 應用程式應用程式功能的圖形。" border="false":::
    :::column-end:::
    :::column:::
    :::column-end:::
:::row-end:::

為了提供讓使用者在 Teams 中工作的豐富體驗，應用程式開發人員可使用下列功能建立應用程式：

* **Bot**：Bot 也稱為聊天機器人或交談機器人。 它是執行簡單且重複的工作的應用程式。 聊天機器人互動可以是快速的問題與解答，也可以是提供存取服務或協助的複雜交談。 使用者可以在個人聊天、頻道或群組聊天中與 Bot 交談。 如需詳細資訊，請參閱 [Microsoft Teams 中的 Bot](/microsoftteams/platform/bots/what-are-bots)。

  Teams 支援在私人聊天和頻道中使用 Bot。 系統管理員可以控制是否允許在 Microsoft 365 或 Office 365 組織中使用 Bot。 如需開啟或關閉自訂 Bot 的相關資訊，請參 [閱 Teams 系統管理中心的應用程式管理和控管概觀](manage-apps.md)。

* **索引標籤**：索引標籤是釘選在頻道或聊天頂端的 Teams 感知網頁。 索引標籤可讓您以類似網頁的體驗與內容和服務互動。 它們是簡單的 HTML <iframe \> 標籤，指向應用程式資訊清單中宣告的網域，而且可以新增為個別使用者團隊、群組聊天或個人應用程式內頻道的一部分。 如需詳細資訊，請參閱 [Microsoft Teams 索引標籤](/microsoftteams/platform/tabs/what-are-tabs)。

  在每個私人聊天中，預設會建立 [交談]、[檔案]、[組織] 和 [活動] 索引標籤。 除了這些內建索引標籤之外，開發人員還可以設計和新增自訂索引標籤。 如需詳細資訊，請參閱 [在 Teams 中使用內建和自訂索引標籤](/microsoftteams/platform/tabs/what-are-tabs)。

* **Web 端子和連接器**：Web 端子和連接器可協助將 Web 服務連線到 Microsoft Teams 中的頻道和團隊。 Web 端子是使用者定義的 HTTP 回撥，會通知使用者 Teams 頻道中已執行的任何動作。 這是應用程式取得即時資料的一種方式。 連接器可讓使用者訂閱，以接收來自您 Web 服務的通知和訊息。 如需詳細資訊，請參閱 [網路任務和連接器](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)。

  若要允許使用者在 Teams 中使用自訂連接器，請參閱 [在 Teams 中使用自訂連接器](office-365-custom-connectors.md)。

* **訊息中心延伸** 模組：訊息擴充功能是插入應用程式內容或在訊息上採取行動的快速鍵，使用者不必離開交談。 使用者可以從撰寫郵件區域、命令方塊或直接從郵件中搜尋或啟動外部系統中的動作。 如需詳細資訊，請參閱 [訊息延伸模組](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions?tabs=dotnet)。

* **會議擴充** 功能：使用者可以整合會議中的索引標籤、Bot 和訊息擴充功能，增強會議體驗，提高會議生產力。 您可以識別各種參與者角色和使用者類型、取得會議事件，以及產生會議內對話方塊。 如需詳細資訊，請參閱 [Teams 會議相關應用程式](/microsoftteams/platform/apps-in-teams-meetings/teams-apps-in-meetings)。

* **卡片和工作模組：卡** 片可為使用者提供各種視覺、音訊和可選取的訊息，以及交談流程中的說明。 工作模組可協助您在 Microsoft Teams 中建立模式快顯體驗。 它們對於開始和完成工作，或是顯示如影片或 Power business intelligence (BI) 儀表板等豐富資訊很有用。 如需詳細資訊，請參閱 [卡片和工作模組](/microsoftteams/platform/task-modules-and-cards/cards-and-task-modules)。

若要檢視對應至 Teams 功能的常見使用案例，請參閱將 [您的使用案例對應至 Teams 應用程式功能](/microsoftteams/platform/concepts/design/map-use-cases)。

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

## <a name="related-articles"></a>相關文章

* [深入瞭解 Teams 的應用程式範本](/microsoftteams/platform/samples/app-templates)。

* [Teams 系統管理中心的應用程式管理和控管概觀](manage-apps.md)

* [在 Microsoft Teams 系統管理中心管理您的應用程式](manage-apps.md)
