---
title: Microsoft Teams 中的應用程式、Bot 和連接器
ms.reviewer: ''
description: 了解應用程式、Bot 和連接器，以及如何根據貴組織的設定檔和商務需求，決定要在 Microsoft Teams 中部署哪些應用程式、Bot 和連接器。
ms.topic: article
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: admin
ms.date: 01/28/2019
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
ms.openlocfilehash: c7ad1c83a09a17fb45adae149272177c8d42d17e
ms.sourcegitcommit: fb4edc26c566228d74c10cb51a063b5fdc7e11a1
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48177333"
---
# <a name="apps-bots--connectors-in-microsoft-teams"></a>Microsoft Teams 中的應用程式、Bot 和連接器

您可利用應用程式在最愛的服務中尋找內容，然後在 Teams 中分享。 他們可幫助您執行作業，例如在頻道最上方釘選服務、與 Bot 聊天或共用及指派工作。 若要深入了解，請參閱[ Teams 中的應用程式概觀](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)。

建議您在一開始推出 Teams 時能夠包含我們的精選應用程式，例如 Planner。 然後在推廣 Teams 的採用時，新增其他應用程式、Bot 和連接器。

您也可以選擇建立自訂應用程式。 如需詳細資訊，請參閱我們的[開發人員文件](/microsoftteams/platform/overview)。

## <a name="apps-deployment-decisions"></a>應用程式部署決策

Teams 為您的組織提供絕佳的現成共同作業體驗，而大部分組織認為預設設定就能滿足其需求。 本文可協助您決定是否要根據組織的設定檔和商務需求來變更任何預設設定，並逐步引導您完成每個變更。 我們已將設定分割成兩個群組，從[您最可能進行的變更](#core-deployment-decisions)的核心集開始。 根據組織的需求，第二個群組包括您可能想要設定的[其他設定](#additional-deployment-decisions)。

## <a name="core-deployment-decisions"></a>核心部署決策

這些應用程式設定是大部分組織想要變更的 (如果 Teams 的預設設定不符合組織的需求)。

### <a name="app-availability-settings"></a>應用程式可用性設定 

Teams 提供數個由 Microsoft 發行的應用程式和第三方應用程式，以吸引使用者、支援生產活動，並將常用的商務服務整合到 Teams 中。 從 Teams 市集取得應用程式。 根據預設，所有的應用程式 (包括透過 [Teams 市集核准程序](https://docs.microsoft.com/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process)提交的自訂應用程式) 都會針對所有使用者開啟。 例如，使用者可以使用 Planner 應用程式來建立和管理 Teams 中的小組工作。

根據預設，您可使用所有由 Microsoft 及協力廠商提供和自訂的應用程式，並且可開啟或關閉個別應用程式。 這是全組織的設定，可讓您開啟或關閉整個組織的所有協力廠商的和/或自訂的應用程式。

| 問問自己 | 動作 |
|--------------|--------|
|您是否會變更預設的 Teams 應用程式設定？ | 如需可用來管理組織中的應用程式的原則和設定的詳細資訊，請參閱 [Microsoft Teams 中應用程式的系統管理設定](admin-settings.md)。|
|||

### <a name="app-permissions-and-other-considerations"></a>應用程式權限和其他考量

應用程式經過使用者同意，並且由系統管理員或 IT 專業人員透過原則管理。 不過在絕大多數情況下，應用程式的權限和風險設定檔是在應用程式本身中定義。 

| 問問自己 | 動作 |
|--------------|--------|
|<br>我想允許哪些應用程式的存取權？ 我不想允許哪些應用程式的存取權？  | <ul><li>如需在允許應用程式、Bot、索引標籤或連接器的存取權時應考慮的事項清單，請參閱 [Microsoft Teams 應用程式權限和考量事項](app-permissions.md)。</li><li>如需提供應用程式讓貴組織的使用者使用的相關資訊，請參閱[在 Microsoft Teams 系統管理中心管理您的應用程式](manage-apps.md)。</li></ul>|
|||

### <a name="bots-for-private-chats-and-channels"></a>適用於私人聊天和頻道的 Bot

Bot 是自動程式，可回應查詢或可針對使用者感興趣或希望隨時了解的詳細資訊提供更新和通知。 Bot 可讓使用者與 Teams 聊天中的雲端服務互動，例如工作管理、排程和投票等。 Teams 支援在私人聊天和頻道中使用 Bot。 系統管理員可以控制是否允許在 Microsoft 365 或 Office 365 組織中使用 Bot。

| 問問自己 | 動作 |
|--------------|--------|
|我想要在我的組織中允許使用自訂 Bot 嗎？|如需新增 Bot 的詳細資訊，請參閱[在 Microsoft Teams 中新增適用於私人聊天和頻道的 Bot](add-bots.md) (英文)。 如需開啟或關閉自訂 Bot 的詳細資訊，請參閱 [Microsoft Teams 中應用程式的系統管理設定](admin-settings.md)。|
|||

### <a name="built-in-and-custom-tabs"></a>內建和自訂索引標籤

擁有者與團隊成員可以在頻道、私人聊天和群組聊天中新增索引標籤，協助整合其雲端服務。 新增索引標籤可協助使用者存取及管理他們所需或最常用的資料。 在頻道中，預設會建立 [交談] 和 [檔案] 索引標籤。 在每個私人聊天中，預設會建立 [交談]、[檔案]、[組織] 和 [活動] 索引標籤。 除了這些內建索引標籤之外，您還可以設計及新增自訂索引標籤。 若要瞭解如何為組織開啟或關閉Teams 應用程式，請參閱 [Teams 中應用程式的系統管理設定](admin-settings.md)。

| 問問自己 | 動作 |
|--------------|--------|
|我想要在我的組織中允許使用自訂索引標籤嗎？|如需詳細資訊，請參閱 [在 Teams 中使用內建和自訂索引標籤](built-in-custom-tabs.md)。|
|||

### <a name="custom-connectors"></a>自訂連接器

連接器透過將您經常使用的服務中的內容和更新直接發送到頻道中，進而使您的團隊保持最新狀態。 有了連接器，您的 Teams 使用者就能在其 Teams 聊天中接收來自來自 Twitter、Trello、Wunderlist、GitHub 和 Azure DevOps 服務等熱門服務的更新。

| 問問自己 | 動作 |
|--------------|--------|
|我是否要允許使用者建立自訂連接器？|如需詳細資訊，請參閱[在 Teams 中使用自訂連接器](office-365-custom-connectors.md)。|
|||

## <a name="additional-deployment-decisions"></a>其他部署決策

根據組織的需求和組態而定，您可能會想要變更這些設定。

### <a name="activity-reports"></a>活動報告

您可以使用活動報告來查看組織中的使用者如何使用 Teams。 例如，如果有人還沒使用 Teams，可能是他們不知道如何開始，或不了解如何使用 Teams 提高生產力和共同作業。 組織可以使用活動報告來決定要優先進行訓練和溝通的方面。 若要查看活動報告，您必須是 Microsoft 365 或 Office 365 的全域系統管理員、Teams 服務系統管理員或商務用 Skype 系統管理員。

| 問問自己 | 動作 |
|--------------|--------|
| <br>誰需要查看活動報告，以及他們是否具備檢視報告的正確權限？ |<ul><li>如果您不想將系統管理員角色指派給使用者，您可以 [指派報告讀取者角色](teams-activity-reports.md#reports-reader-role)。</li><li>如需如何在 Azure Active Directory 中指派系統管理員角色的詳細資訊，請參閱[角色和權限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 和[查看和指派角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)。</li></ul> |
|||

### <a name="app-templates"></a>應用程式範本

應用程式範本是適用於 Microsoft Teams 生產環境的應用程式，其由社群推動、為開放原始碼，而且可在 GitHub 上取得。 每個範本都包含詳細的指示，可用來部署和安裝組織的應用程式，並提供了一個可立即使用的應用程式，讓您立即安裝並開始使用。 同時也提供完整的原始程式碼，您可以在其中詳細探索，或衍生程式碼並加以變更，以符合您的特定需求。

| 問問自己 | 動作 |
|--------------|--------|
| 我是否要安裝任何 Teams 應用程式範本，例如 Icebreaker？ |若要深入瞭解，請參閱 [Teams 的應用程式範本](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates?toc=MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) (英文)。|
|||


## <a name="next-steps"></a>後續步驟
- [推廣採用](adopt-microsoft-teams-landing-page.md)精選應用程式，例如 Planner。
- [推出會議和研討會](deploy-meetings-microsoft-teams-landing-page.md)
- [推出雲端語音](cloud-voice-landing-page.md)


