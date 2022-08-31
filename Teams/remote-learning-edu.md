---
title: 開始使用 Microsoft Teams 進行遠端學習
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith, lakuan
description: Microsoft Teams 教育版的遠端學習啟動指導方針。
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 231007549102b8cddc02a0d2a5d29266662b4b2f
ms.sourcegitcommit: 7a1fb6e15c21368afa34cd212865437781f721e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/31/2022
ms.locfileid: "67466021"
---
# <a name="get-started-with-microsoft-teams-for-remote-learning"></a>開始使用 Microsoft Teams 進行遠端學習

本文涵蓋 IT 系統管理步驟，讓您的教育機構使用 Microsoft Teams 設定遠端學習。

在 Teams **中，授課者** 可以：

- 與學生快速交談。
- 共用檔案和網站。
- 建立 OneNote 課程筆記本。
  - 整理互動式課程。
  - 提供有效且及時的意見反應。
- 發佈作業並評分作業。
- 在專業學習社群中共用說明材料。

**教育系統管理員和教職員** 可以：

- 隨時掌握最新事件。
- 使用教職員 Teams 共同作業以進行公告和主題交談。

# <a name="accounts--licenses"></a>[帳戶&授權](#tab/accounts)

## <a name="user-accounts-licenses-and-identity-security"></a>使用者帳戶、授權和身分識別安全性

Teams 會使用 Microsoft 365 驗證使用者並提供服務。 所有使用者都應該建立 Microsoft 365 身分識別以促進共同作業。

如果使用者身分識別不存在，請依照此程式建立：

1. [使用學校資料同步處理建立使用者](/microsoft-365/education/deploy/school-data-sync)。
2. [指派授權給使用者](teams-edu-licensing.md)。
3. [建立 Microsoft 365 群組](Office-365-groups.md)。
4. [設定 Exchange](Exchange-Teams-interact.md)。
5. [設定 SharePoint 和 OneDrive](SharePoint-OneDrive-interact.md)。
6. [設定擁有 Google 電子郵件的使用者](/microsoft-365/education/deploy/enabling-teams-for-education-for-google-users)。

Microsoft Teams 包含在所有 Microsoft 365 方案中，包括免費的 A1 教育版方案。

如需部署 Microsoft 365 和設定 Teams 的指導方針，請參閱 [建立您的 Microsoft 365 租使用者](/microsoft-365/education/deploy/create-your-office-365-tenant)。

# <a name="set-up-teams"></a>[設定 Teams](#tab/setup)

## <a name="easily-set-up-teams"></a>輕鬆設定 Teams

以下是啟動並執行 Teams 所需的兩件事：

### <a name="1-allow-users-to-create-teams"></a>1. 允許使用者建立 Teams

**根據預設，每個人都可以建立 Microsoft 365 群組和 Teams**，但這項功能不一定適合。

例如，有些學校可能會想要限制學生不監督地建立 Teams。 Microsoft 365 群組和團隊建立可以 [限制于特定安全性群組](/microsoft-365/admin/create-groups/manage-creation-of-groups)。

對於教育機構，我們建議允許包括學生在內的所有人建立班級、研究、群組專案和研究群組的團隊。

如需如何建立 Teams 的逐步解說，請參閱 [在 Microsoft Teams 中建立班級團隊](https://support.office.com/article/create-a-class-team-in-microsoft-teams-preview-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b)。

### <a name="2-configure-user-experiences-using-policies"></a>2. 使用原則設定使用者體驗

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> 請參閱 [在 Teams 中保護學生安全，以進行遠距學習](https://support.office.com/article/f00fa399-0473-4d31-ab72-644c137e11c8)。
>
> 如果您想要檢視我們的教育原則建議，請參閱 [Teams 教育版原則和原則套件](policy-packages-edu.md)。

Teams 原則可控制特定使用者或群組可用的功能。 原則可以定義誰應允許使用私人聊天、私人通話、會議排程、可共用的內容類型等等。

**教育人員、教育人員和學生** 可以使用預設 (全域) 原則。 您可以調整原則，為 Teams 新增更多功能，包括 [翻譯功能](messaging-policies-in-teams.md#messaging-policy-settings) 和 [自動會議轉譯](meetings-policies-recording-and-transcription.md#transcription)。

**中等學校學生** 可能需要受限制的功能。 建議您變更全域 (全組織預設) 的原則。

應指派授與重要功能的 **中學教職員和授課者** 原則，例如允許私人聊天和會議排程。 [將這些原則大量指派給您的教職員和授課者](batch-group-policy-assignment-edu.md)。

> [!IMPORTANT]
> 對於指派給任何使用者的會議原則，建議您設定 **[自動允許人員** 進入 **貴組織中的每個人] 設定**。 這可確保未經驗證的使用者必須先獲准進入大廳，才能加入 Teams 會議。
>
> 如需詳細資訊，請參閱[在 Teams 中管理會議原則](meeting-policies-participants-and-guests.md#automatically-admit-people)。

# <a name="class-teams"></a>[班級團隊](#tab/class-teams)

## <a name="create-class-teams-for-secure-classroom-use"></a>建立班級團隊以確保教室使用安全

Microsoft Teams 教育版提供[特定團隊類型](https://support.office.com/article/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67)供教育使用。 [班級團隊類型](https://support.office.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b)專為教室使用設計，並隨附支援教室需求的特定功能，包括：

- 作業。
- 成績。
- OneNote 教室筆記本。
- 用於保護學生唯讀內容的[[課程教材](https://support.office.com/article/Use-folders-to-create-read-only-files-for-students-or-other-team-members-0e7791d7-8c9c-4749-9bca-984289477988)] 資料夾。
- [深入解析](./class-insights.md) 針對每個教室提供學生參與情況、作業及健康的即時資料。
- 在新增學生之前，[優先授課者可以](https://support.microsoft.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78)設定班級。
- 將干擾學生和其他特殊許可權設為靜音的功能。

您可以透過下列方式建立班級團隊：

- [學校資料同步 (SDS) ](#automatic-team-creation-using-sds)。
- [使用 Microsoft 365 課程群組以授課者為導向的創作作品](#educator-led-team-creation-from-microsoft-365-class-groups)。
- [使用圖形 API 的 PowerShell 腳本](#powershell-script-using-graph-apis)。
- [手動建立團隊](#manual-team-creation)。

我們將逐步執行各種選項，協助您選擇最符合您需求的正確部署路徑。

### <a name="automatic-team-creation-using-sds"></a>使用 SDS 自動建立團隊

[學校資料同步 (SDS) ](/SchoolDataSync) 會讀取機構記錄系統的資料，例如學生資訊系統 (SIS) 或學習管理系統 (LMS) 。

SDS 可以從任何記錄系統匯入資料，並擁有內建連接器至許多 [SIS 廠商](/schooldatasync/frequently-asked-questions#what-sismis-vendors-does-school-data-sync-support)。  

#### <a name="benefits-of-sds"></a>SDS 的優點

- 自動建立使用者並套用授權。
- 自動建立及維護班級團隊。
- 與 SIS/LMS 同步處理以維護學生成員資格變更。
- [可讓授課者先準備課程，然後再新增學生](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78)。
- 可以自動建立安全性群組。
- 建立限定管理委派範圍的系統管理單位。
- [允許授課者密碼重設](/schooldatasync/how-to-enable-teacher-password-reset)。
- 具有可重新命名和封存群組和團隊的內建清理功能。
- [將成績從 Teams 同步處理到 SIS](/schooldatasync/grade-sync)。
- [保護學生個人資料](/schooldatasync/protecting-student-personal-data)。
- 追蹤及管理監護人同意。
- 提供更好的教育版 Insights資料。

#### <a name="considerations-for-sds"></a>SDS 的考慮

SDS 會透過兩個步驟建立團隊：

1. SDS 會在 Azure Active Directory (Azure AD) 中建立 Microsoft 365 群組。
2. SDS 會自動將該群組轉換為團隊。

建立團隊的第二個步驟在 SDS 中為選擇性。 取決於部署時間和可能造成的未使用團隊數量，系統管理員可能不想要自動建立團隊。 請改為參閱 [授課者帶領的團隊建立方法](#educator-led-team-creation-from-microsoft-365-class-groups)。  

#### <a name="get-started-with-sds"></a>開始使用 SDS

若要開始使用，請移至 [學校資料同步 (SDS) ](/SchoolDataSync) 並連絡 [https://aka.ms/sdssupport](https://aka.ms/sdssupport) 以取得免費的部署協助。  

### <a name="educator-led-team-creation-from-microsoft-365-class-groups"></a>由授課者帶領的團隊從 Microsoft 365 課程群組建立

授課者所帶領的團隊建立功能可讓授課者輕鬆建立所需的課程。  

此方法可讓您使用 SDS 為每個班級建立群組 (建議) 或使用[圖形 API](/graph/api/educationroot-post-classes)自行建立群組。

準備好班級群組之後，授課者可以將其群組轉換成團隊：

1. 選取 Teams 中的 [Teams] 索引標籤。
2. 在用戶端頂端，選取 **[建議的課程]** 圖示。

#### <a name="benefits-of-educator-led-team-creation"></a>授課者主導團隊建立的好處

- 除非授課者打算使用課程，否則系統會準備並建議課程，但不會建立。
- 對於擁有超過 500，000 個團隊的機構，此方法可減少不必要的團隊數目。
- [SDS 權益](#benefits-of-sds)。
- 圖形 API權益。
  - 讓授課者控制要建立哪些班級。
  - 不要求使用 SDS 整合。

#### <a name="considerations-for-educator-led-team-creation"></a>授課者主導團隊建立的考慮事項

- 並非完全自動化，需要授課者執行一些動作。
- 沒有建立團隊許可權的授課者仍然可以 [從現有的群組建立團隊](https://support.office.com/article/create-a-class-team-in-microsoft-teams-preview-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b)。
- 圖形 API需要高階的技術專長、建立和執行腳本的時間，以及修正任何問題的時間。

#### <a name="get-started-with-educator-led-team-creation"></a>開始使用授課者帶領的團隊建立

若要開始使用 SDS 方法，請移至 [學校資料同步 (SDS) ](/SchoolDataSync) 並連絡 [https://aka.ms/sdssupport](https://aka.ms/sdssupport) 以取得免費的部署協助。

- 您必須關閉 SDS 設定檔中的自動團隊建立開關。
- 您可以使用兩個 SDS 設定檔，為班級團隊使用自動和授課者導向的團隊建立組合。

若要使用 Graph API 方法，請參閱 [Graph API](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-1.0&preserve-view=true) 和[建立班級團隊](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-beta&preserve-view=true)。  

### <a name="powershell-script-using-graph-apis"></a>使用 Graph API 的 PowerShell 指令碼

您可以使用 PowerShell 撰寫腳本來建立團隊和頻道，並自動設定設定。

此方法需要系統管理員 [先建立群組、新增授課者和學生，然後建立團隊](/graph/teams-create-group-and-team)。

您也可以使用[Microsoft 圖形 API來建立、設定、複製及封存團隊](/graph/api/resources/teams-api-overview)。

#### <a name="benefits-of-powershell-scripts"></a>PowerShell 腳本的優點

- 讓 IT 系統管理員控制班級建立。
- 建立早期授課者存取團隊或立即讓學生存取團隊的選項。
- [將學生成員資格變更同步處理至 Azure AD 群組](/graph/api/team-post?tabs=http&view=graph-rest-beta#example-4-create-a-team-from-group&preserve-view=true)。

#### <a name="considerations-for-powershell-scripts"></a>PowerShell 腳本的考慮

- 需要高階技術專業知識和時間來建立及執行指令碼，並修正建立班級群組時所發生的任何問題。
- 沒有內建的錯誤處理或重試邏輯。
- 成員資格變更不會與 SIS 同步處理。

> [!NOTE]
> 班級團隊需要隱藏的群組成員資格，所以只有班級內的授課者和學生可以看到該班級的所有成員。 若要建立 Microsoft 365 課程群組，請參閱 [建立班級團隊](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-beta&preserve-view=true) 以符合隱私權需求。

### <a name="manual-team-creation"></a>手動建立團隊

使用者可以建立自己的團隊，藉此量身打造自己的 Teams 體驗。

根據使用者的許可權，他們可以：

- [設定自己的團隊並邀請使用者，包括學生](https://support.microsoft.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b#ID0EADAAA=Create_a_team_from_scratch)。
- [手動將使用者新增至團隊](https://support.office.com/article/add-a-student-to-a-class-team-b88263bb-ace1-4702-8a48-f8a2cf4af954)。
- [共用聯結代碼](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f)。
- [與團隊共用連結](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f)。

建議授課者將學生新增至團隊，以確保學生能夠存取，並收到已新增學生的通知。

#### <a name="benefits-of-manual-team-creation"></a>手動建立團隊的好處

- 讓授課者完全控制班級建立。
- 課程團隊會立即建立。

#### <a name="considerations-for-manual-team-creation"></a>手動建立團隊的考慮

- 需要授課者執行動作和時間。
- 學生成員資格未與 SIS 同步處理，需要手動管理。
- 學生將立即取得班級團隊的存取權。

### <a name="recommended-best-practices"></a>建議的最佳做法

- 盡早部署，以確保各個項目都能可靠運作，且備妥供學校的第一天使用。

- 對於 SDS 自動建立團隊的問題，授課者可以使用 [授課者帶領的團隊建立方法](#educator-led-team-creation-from-microsoft-365-class-groups) 來重試。 [手動建立團隊](#manual-team-creation) 是另一個解決方案，但課程不會與 SIS 同步。

- 租用戶團隊的限制為 50 萬個團隊。 因此，系統管理員應減少未使用的團隊數目，以避免達到這些限制。 如需詳細資訊，請參閱 [Microsoft Teams 的限制和規格](limits-specifications-teams.md)。  

# <a name="educator-early-access"></a>[授課者優先存取](#tab/early-access)

## <a name="early-access-to-class-teams"></a>優先存取班級團隊

早期存取課程 Teams 可讓授課者先存取班級團隊，學生才能檢視。 授課者有時間設定、新增檔案並整理，然後再授與學生存取權。

當學生準備好存取團隊時，他們可以 [啟用他們的班級](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78)。

### <a name="how-do-i-create-class-teams-that-allow-educators-early-access-to-set-up-a-team-before-admitting-students"></a>我該如何建立班級團隊，以允許授課者可以在學生加入前，搶先存取並設定團隊？

從群組（透過 SDS、授課者引導的或 Graph API）建立的團隊會預設自動建立優先存取團隊。

若要使用 Graph API 建立您自己的優先存取團隊，您將會需要 [建立班級](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-beta&preserve-view=true) 和 [從群組建議團隊](/graph/api/team-post?tabs=http&view=graph-rest-beta#example-4-create-a-team-from-group&preserve-view=true)。

### <a name="how-do-i-check-if-a-class-is-activated"></a>我該如何檢查我的班級是否已啟用？

在 [小組資源類型](/graph/api/resources/team?view=graph-rest-beta&preserve-view=true)中，檢視屬性 [為MembershipLimitedToOwners](/graph/api/resources/team?view=graph-rest-beta#properties&preserve-view=true)，以查看是否已啟用班級。

使用 [取得 Team API](/graph/api/team-get?tabs=http&view=graph-rest-beta&preserve-view=true) 以查詢特定班級的```isMembershipLimitedToOwners```屬性。 若已啟用該團隊，查詢的回傳值為 false。  如果團隊尚未啟用，它會傳回 True 值。

### <a name="how-do-i-activate-a-class-for-an-educator"></a>我該如何為授課者啟用班級？

使用 [[更新小組 API](/graph/api/team-update?tabs=http&view=graph-rest-beta&preserve-view=true)]，並將屬性設 ```isMembershipLimitedToOwners``` 為 false，以代表授課者啟用團隊。 小組啟用之後，就無法反轉。

### <a name="create-staff-teams-for-staff-communication-and-collaboration"></a>建立教職員團隊來進行教職員通訊和共同作業

[教職員類型團隊](https://support.office.com/article/create-a-staff-team-in-microsoft-teams-314ac9d5-36a9-408e-8ae4-7ef20e9f1ddf) 適用于教育系統管理員和教職員，以共用資訊並共同處理整個機構的方案。

教育系統管理員可以使用團隊建立精靈將教職員新增至團隊、在 [團隊建立後新增成員](https://support.office.com/article/add-members-to-a-team-in-teams-aff2249d-b456-4bc3-81e7-52327b6b38e9)，或 [是共用加入代碼或連結至團隊](https://support.office.com/article/create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f)。

# <a name="meeting-scenarios"></a>[會議案例](#tab/scenarios)

## <a name="teams-meeting-scenarios"></a>Teams 會議案例

### <a name="collaborative-meetings-for-virtual-classes"></a>虛擬班級的共同會議

[Microsoft Teams 會議](./tutorial-meetings-in-teams.yml)最多可支援 250 個並行的出席者，包括音訊、視訊、[內容共用](https://support.office.com/article/show-your-screen-during-a-meeting-90c84e5a-b6fe-4ed4-9687-5923d230d3a7)、白板和共用筆記等功能。

會議可以是：

- [在 Teams 用戶端內排程](./tutorial-meetings-in-teams.yml)。
- 記錄並儲存，供出席者稍後檢閱。
- [轉譯可輕鬆尋找內容](https://support.office.com/article/Microsoft-Stream-automatically-creates-closed-captions-for-videos-8d6ac353-9ff2-4e2b-bca1-329499455308)。
- 使用膝上型電腦或行動電話網路攝影機、麥克風和喇叭存取。
- [針對特定裝置優化](https://products.office.com/microsoft-teams/across-devices/devices)。
- 所有參與者都已結束，以確保學生不會在會議不受監督的情況下參加。

### <a name="districtuniversity-events-or-updates"></a>校區/大學活動或更新

有些會議有大量觀眾和額外的生產需求。 這些會議通常已定義簡報者、製作人和控管式問與答。

Teams 使用 [Microsoft Teams 即時活動](teams-live-events/what-are-teams-live-events.md)來支援這些工作階段。

即時事件可用於案例，例如：

- 地區或全校更新。
- 領導權位址。
- 適用于大型班級或學生群組的指示。
- 延伸至您的社群。

瞭解如何進行即時會話，請參閱：

- [規劃及排程即時活動](https://support.office.com/article/video-plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502)。
- [製作即時活動](https://support.office.com/article/video-produce-a-live-event-34c89e79-ffd4-4a6a-baf6-77055e0709cb)。
- [參加即時活動](https://support.office.com/article/video-attend-a-live-event-d837ad8d-ce34-44d0-9744-9beb50e943ac)。
- [調製 Q&A](https://support.office.com/article/video-moderating-a-q-a-4984e582-8c66-4ea3-aaaf-d93cf62e1b76)。

# <a name="resources"></a>[資源](#tab/resources)

## <a name="support-resources"></a>支援資源

如需轉換到遠端學習的概觀， [請從這裡開始](https://www.microsoft.com/education/remote-learning)

如果您是 IT 系統管理員、授課者、學生或監護人，這些資源可協助您使用 Teams：

- **IT 系統管理員**
  - [依平臺的 Teams 功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。
  - [下載併發布 Teams 用戶端](get-clients.md)。
  - [Teams 疑難排解](/MicrosoftTeams/troubleshoot/teams)。
  - [適用于虛擬化桌面基礎結構的 Teams](./teams-for-vdi.md)。
  - [監控及管理通話品質](monitor-call-quality-qos.md)。
  - [確認 Teams 的服務健康情況](service-health.md)。
  - [針對遠端員工優化 Microsoft 365 流量](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571)。
  - [Teams 的支援連絡人](/microsoft-365/admin/contact-support-for-business-products)。
  - [Teams 教育版網路研討會](https://aka.ms/TeamsEDUWebinars)。

- **授課者**
  - [適用于授課者的說明中心](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114)。
  - [遠端學習說明](https://aka.ms/RemoteLearningHelp)。
  - [下載 Teams](get-clients.md)。
  - [Teams 教育版網路研討會](https://aka.ms/TeamsEDUWebinars)。
  - [適用于使用 Teams 之授課者的線上課程](https://education.microsoft.com/course/9c9f5c11/overview)。
  - [線上課程，與 Teams 打造共同作業學習環境](https://education.microsoft.com/course/b1e15cfc/overview)。
  - [提交支援票證](https://www.microsoft.com/microsoft-teams/download-app)。

- **學生**
  - [學生的說明中心](https://support.office.com/article/student-help-center-395ab230-55bf-44c6-b265-e832d729b694)。
  - [遠端學習說明](https://aka.ms/RemoteLearningHelp)。
  - [下載 Teams](https://www.microsoft.com/microsoft-teams/download-app)。

- **監護人**
  - [遠端學習說明](https://aka.ms/RemoteLearningHelp)。
  - [下載 Teams](https://www.microsoft.com/microsoft-teams/download-app)。

---
