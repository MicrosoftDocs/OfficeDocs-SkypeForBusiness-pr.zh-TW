---
title: 使用 Advisor for Teams 協助您推出 Microsoft Teams
author: SerdarSoysal
ms.author: serdars
ms.reviewer: pkrebs
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- remotework
- m365initiative-deployteams
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.deploymentadvisor.overview
description: 使用 Advisor for Teams 協助您規劃和完成您的 Microsoft Teams 部署。
ms.openlocfilehash: 865575bf030720fcd25ae029d4b552730f05a992
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093763"
---
# <a name="use-advisor-for-teams-to-help-you-roll-out-microsoft-teams"></a>使用 Advisor for Teams 協助您推出 Microsoft Teams

Advisor for Teams 會引導您完成 Microsoft Teams 的推廣。 它能評估您的Microsoft Office 365 組織環境，並指出您在成功推行 Microsoft Teams前可能需要更新或修改的最常用設定。 接著，Advisor for Teams 會建立部署團隊 (在 Teams 中)，並為您要推出的每個工作負載建立頻道。部署團隊中的每項工作負載隨附有全方位的 Planner 計劃，其中包含每個工作負載的所有推出工作。  您可以使用此 Planner 計劃，將工作指派給每個推廣階段的負責人，包括專案經理、Teams 服務系統管理員、支援人員，以及您的採用和使用者整備團隊。 每項推廣工作都包含所有您成功完成工作所需的指引和資源。

Advisor for Teams 是 [Teams 系統管理中心](https://admin.teams.microsoft.com)的功能之一。 您至少會需要 Microsoft 365 商務基本版授權，才能運用 Advisor for Teams 和 Forms 與 Planner 的整合。 若要開始使用 Advisor for Teams，請在儀表板上按一下 **[部署 Teams 工作負載]** 小工具中的 **[啟動]** 按鈕。 或者前往 **規劃** > **Teams 建議程式**。

> [!IMPORTANT]
> Advisor for Teams 不適用於 Microsoft 365 政府版 (GCC High 或 DoD) 部署。

如需 Advisor for Teams 的逐步指導，請參閱[部署及設定 Microsoft Teams](https://youtu.be/o2mlsUubIO4?t=50) Microsoft Mechanics 影片。

## <a name="using-advisor-for-teams"></a>使用 Advisor for Teams

**Teams、Forms 和 Planner 授權是使用適用於 Teams 的建議程式所需的授權。** 不過，若要使用 Advisor for Teams，您不必成為 Teams 系統管理員，組織中的任何人都能使用。 我們已設定特殊權限，讓非系統管理員的使用者可以使用 Advisor for Teams，即使 Advisor for Teams 位於 Teams 系統管理中心亦可。 您必須是 Teams 系統管理員、Teams 服務管理員或全域管理員，才能開啟租用戶整備評估 (這是因為特殊的非管理員角色無法存取位於評估底層的 Microsoft Graph API)。

> [!IMPORTANT]
> 如果小組系統管理中心的 [規劃] 中遺漏 **Teams 建議程式**，表示該使用者未取得 Teams 的授權。

第一次使用 Advisor for Teams 時，系統會為您在 Teams 中建立部署團隊。 並針對您選取的每個工作負載新增頻道。

> [!IMPORTANT]
> 如果部署團隊已建立，而其他使用者嘗試建立，則會發生錯誤，通知他們與其支援小組聯繫。 這可防止 Teams 意外公開現有團隊及其成員的相關資訊。 請要求部署團隊的擁有者新增您，或與支援人員聯繫以取得協助。

## <a name="available-advisor-for-teams-plans"></a>可使用的 Advisor for Teams 方案

Advisor for Teams 目前提供下列方案:

1. 聊天、團隊、頻道和應用程式
    - 租用戶評估
    - Planner 計劃，包括採用工作
    - Forms 使用者問卷
    - Advisor for Teams Bot
1. 會議和研討會
    - 租用戶評估
    - Planner 計劃，包括採用工作
    - Forms 使用者問卷
    - Advisor for Teams Bot
1. 商務用 Skype 升級
    - 租用戶評估
    - Planner 計劃，包括採用工作
    - Forms 使用者問卷
    - Advisor for Teams Bot
    - 專為目前正在使用商務用 Skype Online 或商務用 Skype 內部部署環境的客戶設計，商務用 Skype 升級計畫可幫助您擺脫升級過程中的猜測。 該計劃將利用一個行之有效的成功框架來實作變更，無論您是剛開始使用 Teams、已經將 Teams與商務用 Skype 搭配使用還是準備進行升級，它都將指導您逐步進行操作。 該計劃還將提供您[線上指南和最佳做法](./upgrade-start-here.md)、[可下載資產](https://aka.ms/UpgradeSuccessKit)、[即時一對多規劃研討會](./upgrade-workshops-landing-page.yml)以及其他資源，以支援您成功升級。

我們建議您從交談、團隊、頻道和應用程式的方案開始。 您完成該工作負載的部署後，請返回 Advisor for Teams，選取 **[新增頻道]** 以開始下一項工作負載。

## <a name="tenant-assessment"></a>租用戶評估

每個方案都包含租用戶整備評估，可讓您在推出 Teams 前快速識別任何可能需要修復的環境問題。 評估包括必要條件與最佳做法。 每個評估測試都會顯示綠色核取記號或橙色警告三角形。

- <sub><img src="media/use-advisor-teams-roll-out-image2.png" alt="Green check mark"/></img></sub>綠色核取記號表示租用戶已通過特定測試。
- <sub><img src="media/use-advisor-teams-roll-out-image1.png" alt="Yellow alert mark"/></img></sub>橙色警告三角形表示我們建議您追蹤以判斷是否需要任何動作 (例如，建議使用 Microsoft 365 群組到期原則，但非必須)。

> [!IMPORTANT]
> 擁有系統管理員角色的使用者啟動 Advisor for Teams 後，所有評估都會在背景執行。 如果您進行更新或修補，這些內容可能不會在最多 24 小時內反映到評估中。

下列各節說明每項評估，包括是否有任何一項是必要條件或最佳做法、每項評估檢查的執行方式和理由，並視需要提供修補指引。

### <a name="assessment-tests-for-all-workloads"></a>所有工作負載的評估測試

|評估測試  |代表意義  |
|---------|---------|
|已設定虛名網域     |您的租用戶是否有設定非 @onmicrosoft.com 的網域 (例如 @contoso.onmicrosoft.com)。 當然，您可以選擇使用 @onmicrosoft.com 網域或設定虛名網域。 如需詳細資訊，請參閱[新增網域至 Microsoft 365](/microsoft-365/admin/setup/add-domain)。 |
|Teams 授權     |這是必要條件，您 **必須具有** Teams 授權才能推出 Teams。 查詢 Microsoft Graph，查看您是否具有 Teams 授權 (至少有一個授權可供指派)。 如需詳細資訊，請參閱 [Microsoft Teams 服務描述](/office365/servicedescriptions/teams-service-description)。    |
|Exchange Online 授權     |您的可用 Exchange Online 授權是否為有效訂閱。 雖然 Exchange 並非 Teams 基本功能的必要項目，但是與 Exchange 整合可以提供最佳的 Teams 體驗。 查詢 Microsoft Graph 以分析與租用戶相關聯的訂閱，並驗證您是否具有合格的 Exchange Online 授權訂閱 (至少有一個授權可供指派)。 如需詳細資訊，請參閱 [Exchange 和 Teams 如何互動](exchange-teams-interact.md)。    |
|SharePoint Online 授權     |您的可用 SharePoint Online 授權是否為有效訂閱。 我們建議採用每位使用者 SharePoint Online 授權，以便在聊天中提供商務用 OneDrive 用於檔案儲存。 查詢 Microsoft Graph，查看您是否具有 SharePoint Online 授權 (至少有一個授權可供指派)。 如需詳細資訊，請參閱 [Sharepoint 和商務用 OneDrive 如何與 Teams 互動](./sharepoint-onedrive-interact.md)。    |
|已啟用來賓存取     |是否已開啟[來賓存取](guest-access.md)。 來賓存取可讓您邀請外部使用者加入您的團隊。 查閱 [在小組中與來賓共同作業](/microsoft-365/solutions/collaborate-as-team)逐步引導您開啟 Teams 中的來賓存取；此檢查清單包含所需的 Azure AD 設定。 |
|已設定外部存取     |是否已開啟[外部存取](manage-external-access.md)。 預設為開啟，並採用開放式同盟。 |

### <a name="assessments-for-chat-teams-channels-and-apps"></a>聊天、團隊、頻道和應用程式評估

除了[所有工作負載的評估測試](#assessment-tests-for-all-workloads)，還會針對聊天、團隊、頻道和應用程式工作負載執行下列額外的評估：

|評估測試  |代表意義  |
|---------|---------|
|Microsoft 365 群組命名原則已設定完成     |是否已針對 Microsoft 365 群組設定命名標準。 Microsoft 365 群組命名原則可讓貴組織為使用者建立的團隊套用一致的命名策略，也適用於其他群組工作負載 (包括 Outlook、SharePoint、Planner 和 Yammer)。 此測試會經由 Microsoft Graph 查詢 Azure AD，以檢查適用於 Microsoft 365 群組的命名原則是否存在。 如需詳細資訊，請參閱 [群組命名原則](/microsoft-365/admin/create-groups/groups-naming-policy)。    |
|Microsoft 365 群組到期原則已設定完成。     |是否已為 Microsoft 365 群組定義群組到期原則。 這能讓貴組織自動移除非作用中的團隊。 預設為關閉。 此測試經由 Microsoft Graph 查詢 Azure AD，並報告是否已修改預設值。 如需詳細資訊，請參閱 [Microsoft 365 群組到期原則](/microsoft-365/admin/create-groups/office-365-groups-expiration-policy)。    |

### <a name="assessments-for-meetings-and-conferencing"></a>會議和研討會評估

除了[所有工作負載的評估測試](#assessment-tests-for-all-workloads)，還會針對會議和研討會工作負載執行下列額外的評估：

|評估測試  |代表意義  |
|---------|---------|
|音訊會議授權    |您的音訊會議授權是否為有效訂閱。 如果您要部署音訊會議橋接器，這是必要條件。 查詢 Microsoft Graph，查看您是否具有音訊會議授權 (至少有一個授權可供指派)。如需詳細資訊，請參閱 [Teams 附加元件授權](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。    |
|Stream 授權     |您是否有使用 Microsoft Stream 授權的有效訂閱。 如果您要開啟會議錄製，這是必要條件。 查詢 Microsoft Graph，查看您是否具有 Microsoft Stream 授權 (至少有一個授權可供指派)。 如需有關 Stream 和開啟方式的詳細資訊，請參閱 [Teams 雲端會議錄製](cloud-recording.md)。

### <a name="assessments-for-skype-for-business-upgrade"></a>商務用 Skype 升級評估

除了[所有工作負載的評估測試](#assessment-tests-for-all-workloads)之外，商務用 Skype 升級也包含評估會議與會議方案。

### <a name="advisor-for-teams-bot"></a>Advisor for Teams Bot

Advisor for Teams 建立部署團隊後，Advisor Bot 會在 [一般] 頻道傳遞下列訊息：

>**歡迎使用 Microsoft Teams 的部署團隊！**
>  
>此團隊的目的是引導您完成您組織的 Teams 推廣，給予您所有需要的資源並提供共同作業空間給專案團隊使用。 使用 Advisor for Teams 建立的每個頻道都包含有逐步的 Planner 規劃和其他資源，例如可在推廣期間使用的 Forms 使用者問卷。 您可以隨時返回並檢閱租用戶整備評估，或是使用 Teams 系統管理中心新增額外的工作負載計劃。
>
>**行動信號**
>
>- 如果您剛開始使用 Teams 或 Planner，請參閱我們的 [Teams 逐步解說](https://teamsdemo.office.com/) 並觀賞 [Planner 快速入門影片](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7)。
>- 前往 Teams 中的部署團隊。 選取您的工作負載頻道 (例如交談、團隊、頻道和應用程式)，然後選取 **[Planner]** 索引標籤以開始使用。
>
>若要深入了解 Advisor for Teams，請閱讀 [使用 Advisor for Teams 推出 Microsoft Teams](use-advisor-teams-roll-out.md)。
>

> [!IMPORTANT]
> Advisor for Teams Bot 只能用來傳遞歡迎訊息給部署團隊。 不會收集額外的資料。

> [!IMPORTANT]
> Advisor for Teams Bot 依預設為開啟。 如果您使用或計劃使用 Advisor for Teams，則請勿關閉此功能。

## <a name="advisor-for-teams-and-microsoft-365-learning-pathways"></a>Advisor for Teams 和 Microsoft 365 學習路徑

[Microsoft 365 學習路徑](/office365/customlearning/) 是隨選學習解決方案，您可以自訂以訓練您的使用者，並提高您組織中對於 Teams 的使用及採用。 將學習路徑與 Advisor for Teams 搭配使用，以讓您的使用者快速設定並執行和推動採用。

學習路徑可提供您 SharePoint Online 網站範本，以及為使用者輕鬆建立學習網站的能力。 您可以自訂學習路徑訓練入口網站，以包含特定於使用者需求的訓練與支援內容。 從 Microsoft online 目錄使用 Teams 播放清單，並新增您自己的播放清單。

您可以在學習路徑建立學習網站，然後將它以索引標籤新增至小組中的頻道，讓使用者快速輕鬆地存取。

舉例來說，使用 Advisor for Teams 搭配使用學習路徑以訓練您的支援人員和擁護者，然後讓學習路徑支援訓練您的終端使用者。 建立學習網站，以協助您將支援人員和擁護者加入小組，然後將它以索引標籤新增至您正在推出的每個工作負載頻道。您的支援人員和擁護者之後就可以在學習路徑訓練入口網站建立支援頁面，其中包含連結和自訂播放清單以支援 Teams 上的使用者。 這個支援頁面可新增至任何小組的頻道，以協助訓練您的終端使用者。

以下是如何使用 Advisor for Teams 搭配使用學習路徑的概觀。

### <a name="get-started-in-learning-pathways"></a>開始使用學習路徑

若要開始使用學習路徑，請參閱 [開始使用學習路徑](/office365/customlearning/)。

若要在您的環境中設定新的學習路徑解決方案，請參閱 [提供新的學習路徑解決方案](/office365/customlearning/custom_provision)。

### <a name="create-a-learning-plan"></a>建立學習計劃

#### <a name="plan-your-learning-content"></a>規劃您的學習內容

在您將網站建立在學習路徑中之前，請先花時間檢閱並收集您可以使用的學習資源和功能。 透過學習路徑，您可以使用在 Microsoft 365 訓練頁面中的內容，並新增您建立的內容，以量身打造具您獨特需求的網站。

若要深入瞭解，請參閱 [規劃您的學習路徑內容](/office365/customlearning/custom_plancontent)，以及 [支援遠端工作力的資源](/office365/customlearning/custom_plancontent_remoteresources)。

#### <a name="explore-teams-content-in-learning-pathways"></a>探索學習路徑中的 Teams 內容

學習路徑提供 SharePoint 網站，其中包含已連線至線上目錄的網頁組件。 主控網頁元件的 Microsoft 365 訓練頁面顯示出學習路徑中可供使用的所有訓練。 請多看看以熟悉有哪些服務，及內容的組織方式。

[移至您的學習路徑網站](/office365/customlearning/custom_goto)，選取 [ **Microsoft 365 訓練**]，然後選取 **Microsoft Teams** 以查看線上目錄中所有的 Teams 訓練播放清單。 選取播放清單，然後選取 **[下一步]** 和 **上一步** 按鈕以進行瀏覽。 您也可以按一下向下鍵，以檢視播放清單內容，並移至特定主題。

#### <a name="take-an-inventory-of-teams-learning-resources-in-your-organization"></a>清查貴組織中的 Teams 學習資源

檢視已可在貴組織中使用的 Teams 學習內容。 例如，您可能已針對 Teams 開發自訂的登入、訓練或支援內容。 您現有的 SharePoint 資產可以與播放清單中的 Microsoft 內容混用，以為您的組織建立目標播放清單。

#### <a name="build-your-site-in-learning-pathways"></a>在學習路徑中建立您的網站

學習路徑中的 [系統管理成功中心](/office365/customlearning/custom_successcenter) 提供指引和資源，以協助您規劃和自訂您組織中的學習路徑。 瞭解如何 [自訂網站](/office365/customlearning/custom_overview)、顯示及隱藏內容、建立自訂播放清單等等。

若要存取 [系統管理成功中心]，請在學習路徑首頁上選取 **系統管理成功中心**。

#### <a name="add-your-site-to-teams"></a>將您的網站新增至 Teams

當您的網站準備就緒時，請將它新增到任一小組的頻道中，以便快速輕鬆地存取。

1. 在 Teams 中，請前往小組然後選取頻道。
2. 在頻道頁面頂端，選取 **+** (**新增索引標籤**)。
3. 選取 **[SharePoint 頁面]**，然後選取 **[在任何 SharePoint 網站新增頁面]**。
4. 將您的學習路徑網站 URL 貼上，然後選取 **[儲存]**。

若要深入瞭解，請參閱 [將 SharePoint 頁面或清單新增至 Teams 中的頻道](https://support.microsoft.com/office/add-a-sharepoint-page-or-list-to-a-channel-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b)。

### <a name="train-your-support-team"></a>訓練您的支援小組

使用您學習路徑網站中的資源，以將您的支援人員和擁護者加入 Teams。 透過他們所需的工具和資訊使其準備就緒，以支援您在 Teams 中的使用者。

如需有關針對 Teams 準備您的支援人員和擁護者的指引和資源，請參閱 [訓練您的組織](https://adoption.microsoft.com/microsoft-teams/#train-your-org) 和 [打造擁護者](https://adoption.microsoft.com/microsoft-teams/#build-champions)。

當您的使用者針對「操作方法」」問題而移至聯絡時，您的技術人員和擁護者可使用 [學習路徑] 網站以訓練使用者，並將該網站視為建立支援票證的其他選項。 透過建立訓練和支援頁面，鼓勵您的技術人員和擁護者以 [自訂您的學習路徑網站](/office365/customlearning/)，然後在小組中將其 [以索引標籤新增至頻道中](#add-your-site-to-teams) 供使用者自助服務。

### <a name="drive-adoption"></a>推動採用

在您自訂您的網站並將您的學習方案放在一起之後，請考量您將如何促進使用者的認知，以鼓勵他們針對持續學習來使用學習路徑。

使用您的通訊頻道以推廣網站及引起關注。 例如，在與您的使用者溝通中加入標準的標語，像是「查看我們的訓練及支援網站，瞭解如何透過 Teams 提高生產力」。

透過將使用者可在 Teams 中共同作業的方式醒目提示，給予他們鼓勵，然後將他們導向至學習路徑網站以瞭解使用方式。

請檢視這些資源，其中包括指引、採用套件、最佳做法等等，以協助您執行成功的推出和採用計畫。  

- [推動採用學習路徑](/office365/customlearning/driveadoption)
- [採用 Teams](adopt-microsoft-teams-landing-page.md)
- [Teams 的採用資源](https://adoption.microsoft.com/microsoft-teams/)

## <a name="frequently-asked-questions"></a>常見問題集

### <a name="what-are-the-licensing-requirements-for-advisor-for-teams"></a>Advisor for Teams 的授權需求為何？

您至少會需要 Microsoft 365 商務基本版，才能運用 Advisor for Teams 和 Forms 與 Planner 的整合。

### <a name="can-i-delete-the-deployment-team"></a>我可以刪除部署團隊嗎？

在 Advisor for Teams 建立您的部署團隊後，請像管理其他團隊一樣管理該團隊，包括刪除團隊。 請注意，如果您不是使用 Teams 系統管理中心刪除團隊，Teams 系統管理中心會顯示該團隊依然存在。

### <a name="can-i-add-or-remove-channels-in-the-deployment-team"></a>我是否可以在部署團隊中新增或移除頻道？

可以，部署團隊建立後，您就能使用與其他任何團隊相同的方式管理頻道。

### <a name="can-i-add-or-remove-project-team-members-in-the-deployment-team"></a>我是否可以在部署團隊中新增或移除專案團隊成員？

可以，部署團隊建立後，您就能使用與其他任何團隊相同的方式管理該團隊。

### <a name="can-i-modify-the-planner-plans"></a>我可以修改 Planner 計劃嗎？

是的，Advisor for Teams 建立部署團隊後，您應該更新 Planner 計劃，使這項計劃能夠完全支援 Teams 的推出。 您可以修改任何項目，如目標區、工作、工作詳細資訊，就像其他任何 Planner 計劃一樣。

### <a name="can-i-modify-the-forms-survey"></a>我可以修改 Forms 問卷嗎

可以，Advisor for Teams 建立部署團隊後，您可以視需要修改 Forms 問卷。

### <a name="are-there-any-differences-between-advisor-for-teams-in-gcc"></a>在 GCC 中的 Advisor for Teams 是否有任何不同

有的，使用者問卷 Forms 已建立，但尚未固定在計畫頻道中，因為目前 GCC 尚不支援 Teams Forms 應用程式。

### <a name="what-information-is-advisor-for-teams-collecting-about-my-organization"></a>Advisor for Teams 會收集有關我組織的哪些資訊？

Advisor for Teams 會尋求您的同意才收集非 EUII (使用者識別資訊)。 這些資訊以遙測形式進行收集，將有關 Advisor for Teams 成功導入後的成果以及需要改善之處的回饋意見提供給 Microsoft。 相同的資料也會用來找出 Microsoft 可以主動與您組織合作的機會，協助您進行部署。

### <a name="can-i-use-advisor-for-teams-with-fasttrack"></a>我可以使用 Advisor for Teams 搭配 FastTrack 嗎

可以，FastTrack 會針對所有希望部署 Teams 的客戶運用 Advisor for Teams。 他們可以使用 Advisor for Teams 協助您部署團隊的初始設定 (如有需要)，也可以在 Teams 推出期間針對特定主題提供所需的支援。

### <a name="can-i-use-advisor-for-teams-with-a-partner"></a>我可以與合作夥伴一起使用 Advisor for Teams 嗎？

可以，您使用 Advisor for Teams 的同時，也可以利用部署合作夥伴進行 Teams 部署。 如果您的合作夥伴是 CSP 並代替您管理租用戶，則您的合作夥伴可以使用 Advisor for Teams 建立部署團隊並協助您執行整個專案。 此外，您可以與任何合作夥伴合作，方法是將這些個人新增為部署團隊中的來賓，讓他們參與成為整個專案團隊的成員。

### <a name="how-do-i-use-planner"></a>如何使用 Planner

請參閱 [Microsoft Planner 說明](https://support.office.com/article/Microsoft-Planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) 和 [Planner 快速入門影片](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7)。

### <a name="how-do-i-use-forms"></a>如何使用 Forms

請前往 [Forms 說明中心](https://support.office.com/forms)。

## <a name="related-topics"></a>相關主題

[自訂您的 Teams Advisor](/office365/customlearning/custom_teamsadvisor)

[如何推出 Teams](./deploy-overview.md)

[在 Teams 中組織團隊的最佳做法](best-practices-organizing.md)

[用於授權的產品名稱和服務方案識別碼](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)