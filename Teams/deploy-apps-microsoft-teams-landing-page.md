---
title: 了解 Microsoft Teams 中的應用程式
ms.reviewer: ''
description: 了解應用程式，並根據您的組織設定檔和商務需求，決定 Teams 中允許哪些應用程式。
ms.topic: article
author: guptaashish
ms.author: guptaashish
manager: prkosh
audience: admin
ms.date: 02/10/2021
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
ms.openlocfilehash: b6fd5ef344550cf85420faef1748c34f6e87e88b
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556524"
---
# <a name="about-apps-in-microsoft-teams"></a>關於 Microsoft Teams 中的應用程式

應用程式可讓使用者從最愛的服務中尋找內容，並分享至 Teams。 其可讓您執行工作，例如釘選在頻道頂端的服務、使用 Bot 自動通知，或共用和指派工作。 若要深入了解應用程式的使用，請參閱[適用於終端使用者的應用程式概觀](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)。

終端使用者在 Teams 中可使用的不同類型應用程式包括 Microsoft 建立的應用程式、通過認證的協力廠商應用程式，以及貴組織所建立自訂的應用程式。

## <a name="use-microsoft-provided-apps"></a>使用 Microsoft 提供的應用程式

Teams 隨附一組內建的應用程式，包括清單、工作、稱讚、核准等。 建議您在初始推出 Teams 時包括 Teams 的精選應用程式，例如 Planner。 在推動 Teams 採用時新增其他應用程式。 某些預設功能 (例如活動串流、聊天、行事曆和通話) 預設為可用，而且也會釘選供使用者輕鬆存取。

## <a name="use-third-party-apps"></a>使用協力廠商應用程式

除了 Microsoft 提供的應用程式之外，您還可以使用 Microsoft 驗證的協力廠商應用程式。Microsoft 與 Microsoft 365 開發人員合作夥伴合作，以提供以加快使用 Teams 應用程式的決策所需的資訊。如需詳細資訊，請參閱 [Microsoft Teams 應用程式安全性與合規性](/microsoft-365-app-certification/teams/teams-apps)。

## <a name="use-open-source-sample-apps-provided-by-microsoft"></a>使用 Microsoft 提供的開放來源範例應用程式

您也可以使用 [Teams 範本](/microsoftteams/platform/samples/app-templates?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json)，其為針對由社群驅動、開放原始碼且可在 GitHub 上取得的適用於 Microsoft Teams 的生產就緒應用程式。

## <a name="create-custom-apps"></a>建立自訂應用程式

您可以使用與 [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions) 的 Teams 整合來快速建立自訂低程式碼解決方案。 您也可以建立自己的自訂應用程式，以符合您的商務需求。 如需詳細資訊，請參閱[為 Microsoft Teams 建立應用程式](/microsoftteams/platform/overview)。  

## <a name="apps-deployment-decisions"></a>應用程式部署決策

Teams 為您的組織提供絕佳的現成共同作業體驗，而大部分組織認為預設設定就能滿足其需求。本文可協助您決定是否要根據組織的設定檔和商務需求來變更任何預設設定，並逐步引導您完成每個變更。我們已將設定分割成兩個群組，從[您最可能進行的變更](#core-deployment-decisions)的核心集開始。根據組織的需求，第二個群組包括您可能想要設定的[其他設定](#additional-deployment-decisions)。

## <a name="core-deployment-decisions"></a>核心部署決策

這些應用程式設定是大部分組織想要變更的 (如果 Teams 的預設設定不符合組織的需求)。

### <a name="app-availability-settings"></a>應用程式可用性設定

Teams 提供許多由 Microsoft 和第三方發行的應用程式，以吸引使用者、支援生產活動，並將常用的商務服務整合到 Teams 中。
從 Teams 市集取得應用程式。 根據預設，所有的應用程式 (包括透過 [Teams 市集核准程序](/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process)提交的自訂應用程式) 都會針對所有使用者開啟。 例如，使用者可以使用 Planner 應用程式來建立和管理 Teams 中的小組工作。

根據預設，您可使用所有由 Microsoft 及協力廠商提供和自訂的應用程式，並且可開啟或關閉個別應用程式。 這是全組織的設定，可讓您開啟或關閉整個組織的所有協力廠商的應用程式和/或自訂應用程式。

| 問問自己 | 動作 |
|--------------|--------|
|您是否會變更預設的 Teams 應用程式設定？ | 如需可用來管理組織中的應用程式的原則和設定的詳細資訊，請參閱 [Microsoft Teams 中應用程式的系統管理設定](admin-settings.md)。|

### <a name="app-permissions-and-other-considerations"></a>應用程式權限和其他考量

應用程式經過使用者同意，並且由系統管理員或 IT 專業人員透過原則管理。 不過，應用程式的權限和風險設定檔是在應用程式本身中定義。

| 問問自己 | 動作 |
|--------------|--------|
|<br>我想允許哪些應用程式的存取權？ 我不想允許哪些應用程式的存取權？  | <ul><li>如需在允許應用程式、Bot、索引標籤或連接器的存取權時應考慮的事項清單，請參閱 [Microsoft Teams 應用程式權限和考量事項](app-permissions.md)。</li><li>如需提供應用程式讓貴組織的使用者使用的相關資訊，請參閱[在 Microsoft Teams 系統管理中心管理您的應用程式](manage-apps.md)。</li></ul>|

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
|Do I want to allow custom tabs in my organization?|For more information, see [Use built-in and custom tabs in Teams](built-in-custom-tabs.md).|

### Custom connectors

Connectors keep your team current by delivering content and updates from services you frequently use directly into a channel. With connectors, your Teams users can receive updates from popular services such as Trello, Wunderlist, GitHub, and Azure DevOps Services in their Teams chats.

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow users to create custom connectors?|For more information, see [Use custom connectors in Teams](office-365-custom-connectors.md).|

--->

## <a name="additional-deployment-decisions"></a>其他部署決策

您可根據組織的需求和設定來變更這些設定。

### <a name="activity-reports"></a>活動報告

您可以使用活動報告來查看組織中的使用者如何使用 Teams。 例如，如果有人還沒使用 Teams，可能是他們不知道如何開始，或不了解如何使用 Teams 提高生產力和共同作業。 組織可以使用活動報告來決定要優先進行訓練和溝通的方面。 若要查看活動報告，您必須是 Microsoft 365 或 Office 365 的全域系統管理員、Teams 服務系統管理員或商務用 Skype 系統管理員。

| 問問自己 | 動作 |
|--------------|--------|
| <br>誰需要查看活動報告，以及他們是否具備檢視報告的正確權限？ |<ul><li>如果您不想將系統管理員角色指派給使用者，您可以 [指派報告讀取者角色](teams-activity-reports.md#reports-reader-role)。</li><li>如需如何在 Azure Active Directory 中指派系統管理員角色的詳細資訊，請參閱[角色和權限](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 和[查看和指派角色](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)。</li></ul> |

### <a name="app-templates"></a>應用程式範本

應用程式範本是適用於 Microsoft 生產環境的應用程式，其由社群推動、為開放原始碼，而且可在 GitHub 上取得。 每個應用程式都包含為貴組織部署及加以安裝的詳細指示，且是可供您立即安裝並開始使用的現成應用程式。

同時也提供完整的原始程式碼，您可以在其中詳細探索，或衍生程式碼並加以變更，以符合您的特定需求。

| 問問自己 | 動作 |
|--------------|--------|
| 我是否要安裝任何 Teams 應用程式範本，例如 Icebreaker？ |若要深入瞭解，請參閱 [Teams 的應用程式範本](/microsoftteams/platform/samples/app-templates?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=MicrosoftTeams%2ftoc.json)。|
