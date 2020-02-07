---
title: 使用 Advisor for Teams (預覽) 協助您推出 Microsoft Teams
author: lolajacobsen
ms.author: lolaj
ms.reviewer: brandber
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1.keywords:
- CSH
ms.custom: ''
description: 使用 Advisor for Teams (預覽) 協助您規劃和完成您的 Microsoft Teams 部署。
ms.openlocfilehash: c1da173ffbdb150d032b11e0d70ba85e3e4f308b
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836773"
---
# <a name="use-advisor-for-teams-to-help-you-roll-out-microsoft-teams"></a>使用 Advisor for Teams 協助您推出 Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Advisor for Teams (預覽) 會引導您完成 Microsoft Teams 的推廣。 在您成功推出 Teams 前，Advisor for Teams 會評估您的 Office 365 租用戶環境，找出可能需要更新或修改的最常用設定。 接著，Advisor for Teams 會建立部署團隊 (在 Teams 中)，並為您要推出的每個工作負載建立頻道。部署團隊中的每項工作負載隨附有全方位的 Planner 計劃，其中包含每個工作負載的所有推出工作。  您可以使用此 Planner 計劃，將工作指派給每個推廣階段的負責人，包括專案經理、Teams 和 Office 365 系統管理員、支援人員，以及您的採用和使用者整備團隊。 每項推廣工作都包含所有您成功完成工作所需的指引和資源。

Advisor for Teams 是 [Teams 系統管理中心](https://admin.teams.microsoft.com)的功能之一。 您至少會需要 Office 365 商務基本版授權，才能運用 Advisor for Teams 和 Forms 與 Planner 的整合。 若要開始使用 Advisor for Teams，請在儀表板上按一下 **[部署 Teams 工作負載]** 小工具中的 **[啟動]** 按鈕。 或者前往**規劃** > **Teams 建議程式**。

> [!IMPORTANT]
> Advisor for Teams 不適用於 Microsoft 365 政府版 - GCC High 或 DoD 部署。

如需 Advisor for Teams 的逐步指導，請參閱[部署及設定 Microsoft Teams](https://youtu.be/o2mlsUubIO4?t=50) Microsoft Mechanics 影片。

## <a name="using-advisor-for-teams-preview"></a>使用 Advisor for Teams (預覽)

**Teams、Forms 和 Planner 授權是使用適用於 Teams 的建議程式所需的授權。** 不過，若要使用 Advisor for Teams，您不必成為 Teams 系統管理員，組織中的任何人都能使用。 我們已設定特殊權限，讓非系統管理員的使用者可以使用 Advisor for Teams，即使 Advisor for Teams 位於 Teams 系統管理中心亦可。 您必須是 Teams 系統管理員、Teams 服務管理員或全域管理員，才能開啟租用戶整備評估 (這是因為特殊的非管理員角色無法存取位於評估底層的 Microsoft Graph API)。

> [!IMPORTANT]
> 如果小組系統管理中心的 [規劃]**** 中遺漏 **Teams 建議程式**，表示該使用者未取得 Teams 的授權。 這項行為將在未來變更。

第一次使用 Advisor for Teams 時，Advisor for Teams 會在 Teams 中為您建立部署團隊。 並針對您選取的每個工作負載新增頻道。

> [!IMPORTANT]
> 如果部署團隊已建立，而其他使用者嘗試建立，則會發生錯誤，通知他們與支援小組聯繫。 這可防止 Teams 意外公開現有團隊及其成員的相關資訊。 請要求部署團隊的擁有者新增您，或與支援人員聯繫以取得協助。

## <a name="available-advisor-for-teams-plans"></a>可使用的 Advisor for Teams 方案

由於 Advisor for Teams 目前為預覽，我們提供以下兩個方案：

1. 交談、團隊、頻道和應用程式
    - 租用戶評估
    - Planner 計劃，包括採用工作
    - Forms 使用者問卷
    - Advisor for Teams Bot
1. 會議和研討會
    - 租用戶評估
    - Planner 計劃，包括採用工作
    - Forms 使用者問卷
    - Advisor for Teams Bot

我們建議您從交談、團隊、頻道和應用程式的方案開始。 您完成該工作負載的部署後，請返回 Advisor for Teams，按一下 **[新增頻道]** 以開始下一項工作負載。

## <a name="tenant-assessment"></a>租用戶評估
每個方案都包含租用戶整備評估，可讓您在推出 Teams 前快速識別任何可能需要修復的環境問題。 評估包括必要條件與最佳做法。 每個評估測試都會顯示綠色核取記號或橙色警告三角形。 

- <sub><img src="media/use-advisor-teams-roll-out-image2.png" alt="Green check mark"/></img></sub>綠色核取記號表示租用戶已通過特定測試。 
- <sub><img src="media/use-advisor-teams-roll-out-image1.png" alt="Yellow alert mark"/></img></sub>橙色警告三角形表示我們建議您追蹤以判斷是否需要任何動作 (例如，建議使用 Office 365 群組到期原則，但非必須)。

> [!IMPORTANT]
> 擁有系統管理員角色的使用者啟動 Advisor for Teams 後，所有評估都會在背景執行。 如果您進行更新或修補，這些內容可能不會在最多 24 小時內反映到評估中。 這只是暫時的，只要 Advisor for Teams 離開預覽版並公開發布，評估便會即時更新。

下列各節說明每項評估，包括是否有任何一項是必要條件或最佳做法、每項評估檢查的執行方式和理由，並視需要提供修補指引。

### <a name="assessment-tests-for-all-workloads"></a>所有工作負載的評估測試

|評估測試  |代表意義  |
|---------|---------|
|已設定虛名網域     |您的租用戶是否有設定非 @onmicrosoft.com 的網域 (例如 @contoso.onmicrosoft.com)。 當然，您可以選擇使用 @onmicrosoft.com 網域或設定虛名網域。 如需詳細資訊，請參閱[新增網域至 Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain)。 |
|Teams 授權     |這是必要條件，您**必須具有** Teams 授權才能推出 Teams。 查詢 Microsoft Graph，查看您是否具有 Teams 授權 (至少有一個授權可供指派)。 如需詳細資訊，請參閱 [Teams 的 Office 365 授權](https://docs.microsoft.com/microsoftteams/office-365-licensing)。    |
|Exchange Online 授權     |您的可用 Exchange Online 授權是否為有效訂閱。 雖然 Exchange 並非 Teams 基本功能的必要項目，但是與 Exchange 整合可以提供最佳的 Teams 體驗。 查詢 Microsoft Graph 以分析與租用戶相關聯的訂閱，並驗證您是否具有合格的 Exchange Online 授權訂閱 (至少有一個授權可供指派)。 如需詳細資訊，請參閱 [Exchange 和 Teams 如何互動](exchange-teams-interact.md)。    |
|SharePoint Online 授權     |您的可用 SharePoint Online 授權是否為有效訂閱。 我們建議採用每位使用者 SharePoint Online 授權，以便在聊天中提供商務用 OneDrive 用於檔案儲存。 查詢 Microsoft Graph，查看您是否具有 SharePoint Online 授權 (至少有一個授權可供指派)。 如需詳細資訊，請參閱 [Sharepoint 和商務用 OneDrive 如何與 Teams 互動](https://docs.microsoft.com/microsoftteams/sharepoint-onedrive-interact)。    |
|已啟用來賓存取     |是否已開啟[來賓存取](guest-access.md)。 來賓存取可讓您邀請外部使用者加入您的團隊。 使用 [Teams 來賓存取檢查清單](guest-access-checklist.md)逐步引導您開啟 Teams 中的來賓存取；此檢查清單包含所需的 Azure AD 組態。 |
|已設定外部存取     |是否已開啟[外部存取](manage-external-access.md)。 預設為開啟，並採用開放式同盟。 |

### <a name="assessments-for-chat-teams-channels-and-apps"></a>聊天、團隊、頻道和應用程式評估

除了[所有工作負載的評估測試](#assessment-tests-for-all-workloads)，還會針對聊天、團隊、頻道和應用程式工作負載執行下列額外的評估：

|評估測試  |代表意義  |
|---------|---------|
|已設定 Office 365 群組命名原則     |是否已針對 Office 365 群組設定命名標準。 Office 365 群組命名原則可讓貴組織為使用者建立的團隊套用一致的命名策略，也適用於其他群組工作負載 (包括 Outlook、SharePoint、Planner 和 Yammer)。 此測試會經由 Microsoft Graph 查詢 Azure AD，以檢查適用於 Office 365 群組的命名原則是否存在。 如需詳細資訊，請參閱 [Office 365 群組命名原則](https://docs.microsoft.com/office365/admin/create-groups/groups-naming-policy)。    |
|已設定 Office 365 群組到期原則     |是否已為 Office 365 群組定義群組到期原則。 這能讓貴組織自動移除非作用中的團隊。 預設為關閉。 此測試經由 Microsoft Graph 查詢 Azure AD，並報告是否已修改預設值。 如需詳細資訊，請參閱 [Office 365 群組到期原則](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups-expiration-policy)。    |

### <a name="assessments-for-meetings-and-conferencing"></a>會議和研討會評估

除了[所有工作負載的評估測試](#assessment-tests-for-all-workloads)，還會針對會議和研討會工作負載執行下列額外的評估：

|評估測試  |代表意義  |
|---------|---------|
|音訊會議授權    |您的音訊會議授權是否為有效訂閱。 如果您要部署音訊會議橋接器，這是必要條件。 查詢 Microsoft Graph，查看您是否具有音訊會議授權 (至少有一個授權可供指派)。如需詳細資訊，請參閱 [Teams 附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。    |
|Stream 授權     |您是否有使用 Microsoft Stream 授權的有效訂閱。 如果您要開啟會議錄製，這是必要條件。 查詢 Microsoft Graph，查看您是否具有 Microsoft Stream 授權 (至少有一個授權可供指派)。 如需有關 Stream 和開啟方式的詳細資訊，請參閱 [Teams 雲端會議錄製](cloud-recording.md)。

### <a name="advisor-for-teams-bot"></a>Advisor for Teams Bot

Advisor for Teams 建立部署團隊後，Advisor Bot 會在 [一般] 頻道傳遞下列訊息：

>**歡迎使用 Microsoft Teams 的部署團隊！**
>  
>此團隊的目的是引導您完成您組織的 Teams 推廣，給予您所有需要的資源並提供共同作業空間給專案團隊使用。 使用 Advisor for Teams 建立的每個頻道都包含有逐步的 Planner 規劃和其他資源，例如可在推廣期間使用的 Forms 使用者問卷。 您可以隨時返回並檢閱租用戶整備評估，或是使用 Teams 系統管理中心新增額外的工作負載計劃。
> 
>**行動信號** 
>- 如果您剛開始使用 Teams 或 Planner，請參閱我們的 [Teams 逐步解說](https://teamsdemo.office.com/) 並觀賞 [Planner 快速入門影片](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7)。 
>- 前往 Teams 中的部署團隊。 選取您的工作負載頻道 (例如交談、團隊、頻道和應用程式)，然後選取 **[Planner]** 索引標籤以開始使用。
> 
>若要深入了解 Advisor for Teams，請閱讀 [使用 Advisor for Teams 推出 Microsoft Teams](use-advisor-teams-roll-out.md)。
>

> [!IMPORTANT]
> Advisor for Teams Bot 只能用來傳遞歡迎訊息給部署團隊。 不會收集額外的資料。

> [!IMPORTANT]
> Advisor for Teams Bot 依預設為開啟。 如果您使用或計劃使用 Advisor for Teams，則請勿關閉此功能。

## <a name="frequently-asked-questions"></a>常見問題集
### <a name="what-are-the-licensing-requirements-for-advisor-for-teams"></a>Advisor for Teams 的授權需求為何？
您至少會需要 Office 365 商務基本版，才能運用 Advisor for Teams 和 Forms 與 Planner 的整合。

### <a name="can-i-delete-the-deployment-team"></a>我可以刪除部署團隊嗎？
在 Advisor for Teams 建立您的部署團隊後，請像管理其他團隊一樣管理該團隊，包括刪除團隊。 請注意，如果您不是使用 Teams 系統管理中心刪除團隊，Teams 系統管理中心會顯示該團隊依然存在。 這只是暫時的，Advisor for Teams 離開預覽期間並公開發布時，便會修正此問題。

### <a name="can-i-add-or-remove-channels-in-the-deployment-team"></a>我是否可以在部署團隊中新增或移除頻道？
可以，部署團隊建立後，您就能使用與其他任何團隊相同的方式管理頻道。

### <a name="can-i-add-or-remove-project-team-members-in-the-deployment-team"></a>我是否可以在部署團隊中新增或移除專案團隊成員？
可以，部署團隊建立後，您就能使用與其他任何團隊相同的方式管理該團隊。

### <a name="can-i-modify-the-planner-plans"></a>我可以修改 Planner 計劃嗎？
是的，Advisor for Teams 建立部署團隊後，您應該更新 Planner 計劃，使這項計劃能夠完全支援 Teams 的推出。 您可以修改任何項目，如目標區、工作、工作詳細資訊，就像其他任何 Planner 計劃一樣。

### <a name="can-i-modify-the-forms-survey"></a>我可以修改 Forms 問卷嗎？
可以，Advisor for Teams 建立部署團隊後，您可以視需要修改 Forms 問卷。

### <a name="what-information-is-advisor-for-teams-collecting-about-my-organization"></a>Advisor for Teams 會收集有關我組織的哪些資訊？
Advisor for Teams 會尋求您的同意才收集非 EUII (使用者識別資訊)。 這些資訊以遙測形式進行收集，將有關 Advisor for Teams 成功導入後的成果以及需要改善之處的回饋意見提供給 Microsoft。 相同的資料也會用來找出 Microsoft 可以主動與您組織合作的機會，協助您進行部署。

### <a name="can-i-use-advisor-for-teams-with-fasttrack"></a>我可以使用 Advisor for Teams 搭配 FastTrack 嗎？
可以，FastTrack 會針對所有希望部署 Teams 的客戶運用 Advisor for Teams。 他們可以使用 Advisor for Teams 協助您部署團隊的初始設定 (如有需要)，也可以在 Teams 推出期間針對特定主題提供所需的支援。

### <a name="can-i-use-advisor-for-teams-with-a-partner"></a>我可以與合作夥伴一起使用 Advisor for Teams 嗎？
可以，您使用 Advisor for Teams 的同時，也可以利用部署合作夥伴進行 Teams 部署。 如果您的合作夥伴是 CSP 並代替您管理租用戶，則您的合作夥伴可以使用 Advisor for Teams 建立部署團隊並協助您執行整個專案。 此外，您可以與任何合作夥伴合作，方法是將這些個人新增為部署團隊中的來賓，讓他們參與成為整個專案團隊的成員。

### <a name="how-do-i-use-planner"></a>如何使用 Planner？
請參閱 [Microsoft Planner 說明](https://support.office.com/article/Microsoft-Planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) 和 [Planner 快速入門影片](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7)。 

### <a name="how-do-i-use-forms"></a>如何使用 Forms？
請前往 [Forms 說明中心](https://support.office.com/forms)。

## <a name="related-topics"></a>相關主題

[如何推出 Teams](How-to-roll-out-teams.md)

[用於授權的產品名稱和服務方案識別碼](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference
) 
