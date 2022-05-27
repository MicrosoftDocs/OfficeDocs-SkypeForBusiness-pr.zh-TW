---
title: Microsoft Teams 中的聊天、團隊、頻道和應用程式
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 包含逐步指導，以在 Microsoft Teams 中為聊天、團隊、應用程式和頻道設定 Teams 設定。
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.quickstartteamsadmin
appliesto:
- Microsoft Teams
- seo-marvel-apr2020
- seo-marvel-may2020
ms.openlocfilehash: 625bf2c1c99cf7a72da22709b1daebf48fa7c9c4
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676175"
---
# <a name="chat-teams-channels--apps-in-microsoft-teams"></a>Microsoft Teams 中的聊天、團隊、頻道和應用程式

Teams 為您的組織提供絕佳的現成共同作業體驗，而大部分組織認為預設設定就能滿足其需求。本文可協助您決定是否要根據組織的設定檔和商務需求來變更任何預設設定，並逐步引導您完成每個變更。我們已將設定分割成兩個群組，從[您最可能進行的變更](#core-deployment-decisions)的核心集開始。根據組織的需求，第二個群組包括您可能想要設定的[其他設定](#additional-deployment-decisions)。

若要開始使用，請觀看我們的簡短 Teams 聊天、團隊和頻道影片 (4 分 30 秒)：

<br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE476Yj]

您可以[使用 Advisor for Teams 協助您推出 Microsoft Teams](use-advisor-teams-roll-out.md)。Advisor for Teams 會引導您完成 Teams 的推出。在您成功推出 Teams 前，它會評估您的 Microsoft 365 環境，找出可能需要更新或修改的最常用設定。

> [!TIP]
> 建議您在您的 Teams 初始推出中包含我們的精選應用程式，例如 Planner。在開始推動 Teams 的採用時，則新增其他[應用程式、Bot 和連接器](deploy-apps-microsoft-teams-landing-page.md)。

 > [!Note]
 > 如需有關不同平台上 Teams 功能的詳細資訊，請參閱[依平台的 Teams 功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

## <a name="chat-deployment-prerequisites"></a>聊天部署必要條件

在您的組織中推出 Teams 之前，請先用點時間確認您的環境已針對 Teams 備妥。請參閱[針對 Teams 準備組織的網路](prepare-network.md)，並對您的環境進行任何必要的變更。

|問問自己|動作 |
|------------|-------|
|我的組織是否已準備好要推出 Teams？|若要回答此問題，請參閱： <ul><li>[針對 Teams 準備組織的網路](prepare-network.md)</li><li>[URL 和 IP 位址範圍](office-365-urls-ip-address-ranges.md)</li><li>[在建立團隊時規劃 Microsoft 365 群組](plan-office-365-groups.md)</li></ul>|

## <a name="core-deployment-decisions"></a>核心部署決策

這些是大部分組織想要變更的聊天、團隊和頻道設定 (如果預設設定不符合他們的需求)。

### <a name="teams-administrators"></a>Teams 系統管理員

Teams 提供了一組自訂管理員角色，可用來為組織管理 Teams。這些角色為系統管理員提供了多種能力。

| 問問自己 | 動作 |
|--------------|--------|
|誰將獲指派 Teams 通訊系統管理員角色？|若要深入了解 Teams 系統管理員角色，請參閱[使用 Microsoft Teams 系統管理員角色管理來管理 Teams](using-admin-roles.md)。|
|誰將獲指派 Teams 通訊支援工程師角色？|若要指派系統管理員角色，[使用 Azure Active Directory 將系統管理員和非系統管理員角色指派給使用者](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。|
|誰將獲指派 Teams 通訊支援專員角色？||

### <a name="teams-owners-and-members"></a>Teams 擁有者和成員

除了系統管理員角色，Teams 還能讓您指派擁有者和成員使用者角色，並選擇性地賦與他們仲裁者功能 (如果已設定仲裁)，以控制誰可以在頻道內執行特定動作。仲裁可讓您控制誰可以在頻道中開始新的文章、以仲裁者身分新增和移除團隊人員，以及控制團隊成員是否可以回覆現有的頻道訊息。

|問問自己|動作 |
|------------|-------|
|應該對每個角色指派誰？ | 若要比較每個角色的功能，請參閱[在 Microsoft Teams 中指派團隊擁有者、仲裁者和成員](assign-roles-permissions.md)。
|如何指派使用者角色？ | 若要指派或變更角色，請參閱[指派使用者角色](assign-roles-permissions.md#assign-a-user-role)。
|我需要控制誰可以在頻道中貼文及回覆嗎？ | 若要設定仲裁，請參閱[在 Microsoft Teams 中設定和管理頻道仲裁](manage-channel-moderation-in-teams.md)。

### <a name="messaging-policies"></a>訊息原則

管理原則可控制 Teams 中的使用者可使用的聊天及頻道訊息功能。例如，誰可以編輯和刪除已傳送的郵件、誰可以使用聊天、誰可以在交談中使用 Meme 等等。依預設，使用者會獲指派全域訊息原則，且所有功能都會 **開啟**。您可以使用預設的全域原則或是為組織中的人員建立一或多個自訂訊息原則。 

|問問自己|動作 |
|------------|-------|
|我要自訂全域訊息原則嗎？|如需使用 Microsoft Teams 系統管理中心來變更全域訊息原則或新增原則的相關資訊，請參閱[在 Teams 中管理訊息原則](messaging-policies-in-teams.md)。|
|我需要多個訊息原則嗎？|若要在 PowerShell 中建立並指派訊息原則，請參閱 [PowerShell 指令碼範例 - 建立並指派訊息原則](scripts/powershell-script-teams-messaging-policy-edu.md)。|
|我如何判斷哪些使用者群組可以獲得哪個訊息原則？|若要了解 CsTeamsMessagingPolicy Cmdlet，請參閱 [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)。|

### <a name="external-access"></a>外部存取

外部存取 (同盟) 可讓您的使用者透過聊天與組織外部人員通訊。透過開啟此功能並將網域新增至允許清單，您的使用者即可以與其他網域和組織的使用者通訊。外部存取預設為開啟。

|問問自己|動作 |
|------------|-------|
|<ul><li>我要關閉組織的外部會議和聊天嗎？</li><li>如果啟用，我要限制組織可以與其通訊的網域嗎？</li></ul> |<br>若要開啟或關閉外部會議和聊天，請參閱 [管理外部會議和聊天](manage-external-access.md)。|

### <a name="guest-access"></a>來賓存取

Teams 中的來賓存取可讓組織外部的人員存取 Teams 和頻道。您可以使用來賓存取設定來控制來賓可以或不能使用的功能。來賓存取依預設為開啟。若要深入了解，請參閱 [Teams 中的來賓存取](./guest-access.md)。

> [!NOTE]
> 若要深入了解外部存取和來賓存取，請參閱這裡 - [在 Microsoft Teams 中與其他組織的使用者通訊](communicate-with-users-from-other-organizations.md)


|問問自己|動作 |
|------------|-------|
|我要將組織的來賓存取關閉嗎？|若要開啟或關閉來賓存取，請參閱[開啟或關閉 Teams 中的來賓存取](set-up-guests.md)。|
|如果啟用，我將會自訂組織中來賓可使用的功能嗎？|若要自訂來賓存取功能的可用性，請參閱[在 Teams 中授權來賓存取](teams-dependencies.md)。|

### <a name="private-channels"></a>私人頻道

私人頻道允許小組成員的子集在其他小組成員無法查看或存取的私人空間中共同作業。 任何人 (包括來賓) 都可以新增為私人頻道的成員，只要他們已經是小組的成員即可。

|問問自己|動作 |
|------------|-------|
|我想要允許小組擁有者和成員建立私人頻道嗎？|若要為組織設定私人頻道原則，請參閱[在 Microsoft Teams 中管理頻道原則](teams-policies.md)|

### <a name="shared-channels"></a>共用頻道

共用頻道允許您將不是小組成員的人員新增至頻道。 這包括組織外部人員。 共用頻道優於來賓存取的方面在於，組織外部人員不需要在您的目錄中具有來賓帳戶。

|問問自己|動作 |
|------------|-------|
|使用共用頻道與來賓存取的時機為何？|請參閱 [Microsoft Teams 中的共用頻道](shared-channels.md)。|
|<ul><li>我是否將允許小組擁有者建立共用頻道？</li><li>我是否將允許小組擁有者與組織外部人員共用頻道？</li><li>我是否將允許使用者參與組織外部的共用頻道？</li></ul> |<br>若要為組織設定共用頻道原則，請參閱[在 Microsoft Teams 中管理頻道原則](teams-policies.md)。|

### <a name="teams-settings"></a>Teams 設定

Teams 設定可讓您為團隊設定使用電子郵件整合、雲端儲存選項、組織索引標籤、會議室裝置設定和搜尋範圍等功能。對這些設定進行變更時，設定會套用到組織中的所有團隊。若要深入了解，請參閱 [Teams 設定](enable-features-office-365.md#teams-settings)。

|問問自己|動作 |
|------------|-------|
|我要自訂組織的 Teams 設定嗎？ | 若要了解 Teams 設定以及如何加以自訂，請參閱 [Teams 設定](enable-features-office-365.md#teams-settings)。|

### <a name="teams-clients"></a>Teams 用戶端

Teams 支援許多用戶端，範圍從網頁、桌面到行動裝置，且預設設定可讓使用者選擇他們想要使用的用戶端。若要深入了解，請參閱[取得 Teams 用戶端](get-clients.md)。

|問問自己|動作 |
|------------|-------|
|我要自訂組織的 Teams 用戶端可用性嗎？|請查看 [Teams 應用程式的硬體需求](hardware-requirements-for-the-teams-app.md)。 |
|我要自訂組織的 Teams 用戶端設定嗎？|了解如何[使用 MSI 安裝 Teams](msi-deployment.md)。|

### <a name="teams-usage-reporting"></a>Teams 使用情況報告

全域系統管理員、Teams 服務系統管理員和報告讀取者角色可檢視 Teams 使用情況報告。若要深入了解，請參閱 [Microsoft 365 流量分析](/microsoft-365/admin/usage-analytics/usage-analytics)。

|問問自己|動作 |
|------------|-------|
|<br> 誰需要查看 Teams 使用情況報告，以及他們是否具備檢視報告的正確角色？ |<ul><li>如果使用者不是系統管理員，請[指派報告讀取者角色](teams-activity-reports.md#reports-reader-role)。</li><li>請參閱[角色和使用權限](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)和[檢視和指派角色](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)來了解如何在 Azure Active Directory 中指派系統管理員角色。|

### <a name="teams-default-apps"></a>Teams 預設應用程式 

Teams 提供大量的第一方 (Microsoft 提供) 和第三方應用程式，用來吸引使用者、支援生產力，並將常用的商務服務整合到 Teams 中。從 Teams 市集取得應用程式。Teams 中的應用程式預設會開啟。 

若要深入了解如何在 Teams 中推出和管理應用程式，請參閱我們的深入[應用程式、Bot 和連接器](deploy-apps-microsoft-teams-landing-page.md)指引。

## <a name="additional-deployment-decisions"></a>其他部署決策

根據組織的需求和組態而定，您可能會想要變更這些設定。

### <a name="teams-licensing"></a>Teams 授權

Teams 會隨著許多 Microsoft 365 授權提供。

|問問自己|動作 |
|------------|-------|
|我的使用者是否擁有使用我要推出的 Teams 所有功能所需的授權？ | 若要深入瞭解授權需求，請參閱 [Microsoft Teams 服務描述](/office365/servicedescriptions/teams-service-description)。|

### <a name="exchange-and-sharepoint-interoperability"></a>Exchange 和 SharePoint 互通性

為了獲得完整的小組體驗，每個使用者都應啟用 Exchange、SharePoint 及 Microsoft 365 群組建立。下列文章概述與各種環境中託管的 Exchange 信箱相關的資訊、Exchange 與 Teams 如何互動，以及 SharePoint 和商務用 OneDrive 的類似考量。

|問問自己|動作 |
|------------|-------|
| 我是否能部署我目前使用 Exchange 和 SharePoint 部署所需的 Teams 功能？ |如需 Teams 中 Exchange 和 SharePoint 的詳細資訊，請參閱：<ul><li> [Exchange 和 Teams 如何互動](exchange-teams-interact.md)</li><li>[SharePoint Online 和 OneDrive 如何與 Teams 互動](sharepoint-onedrive-interact.md)|

### <a name="teams-limits-and-specifications"></a>Teams 的限制和規格 

規劃 Teams 的企業部署時，應考慮任何相關的限制和規格，例如團隊中成員人數的上限、使用者可建立的團隊人數上限等等。

|問問自己|動作 |
|------------|-------|
| 隨著我的 Teams 推出，我可能會有哪些限制？ | 若要深入了解，請參閱 [Teams 的限制和規格](limits-specifications-teams.md)。 |

### <a name="urls-and-ports"></a>URL 和連接埠

對網際網路流量保有精細控制的組織，應閱讀 [URL 和 IP 位址範圍](/office365/enterprise/urls-and-ip-address-ranges)，以取得必須為 Teams 正確設定的最新 URL、IP 位址、連接埠和通訊協定的清單。Microsoft 會持續改善 Microsoft 365 服務並加入新的功能，這表示必要的連接埠、URL 和 IP 位址可能會隨著時間變更。建議您透過 RSS 訂閱，以便在此資訊更新或變更時收到通知。至少，請確認您已開放以上的[聊天部署先決條件](#chat-deployment-prerequisites)中所列的連接埠。

|問問自己|動作 |
|------------|-------|
| 我是否需要網際網路存取規則，才能讓使用者能使用 Teams，或是開放必要的最基本連接埠即已足夠？ | 若要深入了解，請參閱 [URL 和 IP 位址範圍](office-365-urls-ip-address-ranges.md)。|

### <a name="governance-naming-conventions-who-can-create-teams"></a>控管 (命名慣例，可建立團隊的人員)

您的組織可能會要求您對團隊的命名和分類方式、誰可以建立團隊以及團隊到期日、保留和封存實作控制。這稱為控管。您可以使用 Azure Active Directory (Azure AD) 來設定每一個區域。


| 問問自己 | 動作 |
|--------------|--------|
|我是否需要對可以建立團隊的人員實作控制？| 請閱讀[規劃 Teams 中的控管](plan-teams-governance.md)。|
|我是否需要對團隊的命名方式實作控制？|請閱讀[在 Azure AD 中對 Microsoft 365 群組強制執行命名原則](/azure/active-directory/users-groups-roles/groups-naming-policy)。|

### <a name="teams-application-policy-side-rail-control"></a>Teams 應用程式原則 (側邊欄控制)

釘選的應用程式會顯示在 Teams 的側邊欄中。透過建立 Teams 應用程式原則，您可以預先設定釘選 Teams 應用程式的集合，以針對選取的使用者群組將 Teams 個人化。[在 Microsoft Teams 中允許外部應用程式 **]** 設定預設為開啟。

| 問問自己 | 動作 |
|--------------|--------|
|我應該建立預先設定的釘選 Teams 應用程式集嗎？ | 請閱讀[在 Teams 中管理應用程式的設定](admin-settings.md)。|
|我如何決定哪些群組會收到這些應用程式群組？|請閱讀 [Teams 應用程式權限和考量](app-permissions.md)。|

### <a name="archiving-and-compliance"></a>封存與合規性 

您的組織可能會要求您對團隊的封存方式以及在特定團隊類型中保留的資料類型採取控制措施。請閱讀 [Teams 的安全性與合規性概觀](security-compliance-overview.md)，以了解預設會開啟哪些 Teams 設定。

| 問問自己 | 動作 |
|--------------|--------|
|我需要設定團隊保留嗎？|若要設定保留原則，請參閱[設定 Teams 保留原則](retention-policies.md)。|
|我需要設定團隊封存嗎？|若要封存或還原團隊，請參閱[封存或還原團隊](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)。|
|我需要設定額外的合規性設定嗎？|如需安全性和合規性的詳細資訊，請參閱 [Teams 的安全性與合規性概觀](security-compliance-overview.md)。|

### <a name="conditional-access"></a>條件式存取 

Teams 極度依賴 Exchange 和 SharePoint 進行包括會議、行事曆、交互操作聊天和檔案共用在內的核心生產力案例。當使用者在任何用戶端上直接登入 Teams 時，對這些雲端應用程式設定的條件式存取原則會套用至 Teams。為 Teams 雲端應用程式控制方面設定的條件式存取原則，例如，使用者是否可以從特定網路存取 Teams 服務。

| 問問自己 | 動作 |
|--------------|--------|
|<br>我需要為 Teams 設定條件式存取嗎？|<ul><li>若要了解存取原則的運作方式，請參閱[條件式存取原則如何適合 Teams？](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)</li><li>若要為 Teams 設定多重要素驗證 (MFA)，請參閱：<ul><li>[快速入門：透過 Azure Active Directory 條件式存取來要求特定應用程式需要 MFA](/azure/active-directory/conditional-access/app-based-mfa)</li><li>[Azure Active Directory 條件式存取設定參考](/azure/active-directory/conditional-access/technical-reference)</li></ul></ul>|

### <a name="education-edu"></a>教育版 (EDU) 

在教育單位工作的 IT 專業人員可以利用教育版 Teams，該版本提供許多專為與學生、教職員和更廣泛企業的教育特定案例而量身打造的功能。

| 問問自己 | 動作 |
|--------------|--------|
|我要使用教育版特定的 Teams 範本嗎？ |若要深入了解教育版 Teams，請參閱[系統管理員的 Microsoft 教育控管常見問題集](plan-teams-governance-edu.md)。|
|我將部署限定範圍搜尋嗎？|若要設定 Teams 教育版，請參閱[快速入門 - Teams 教育版系統管理員](teams-quick-start-edu.yml)。|
|我要將 Teams 與學校資料同步處理服務整合，以佈建使用者帳戶嗎？|[Teams 教育版管理員的資源](resources-teams-edu.md)|

### <a name="government---gcc-considerations"></a>政府版 - GCC 考量

Office 365 政府版 - GCC (政府社群雲端) 適合用來滿足在美國聯邦、州、當地、部落或特區政府實體推動 Office 365 部署或處理受限於政府法規和需求的其他實體 IT 專業人員的需求。

| 問問自己 | 動作 |
|--------------|--------|
| 我會需要在 Office 365 政府版 (政府社群雲端環境) 中部署 Teams 嗎? | 如需部署考量，請參閱[規劃 Office 365 政府版 - GCC 部署](plan-for-government-gcc.md)。|

## <a name="next-steps"></a>後續步驟
- 聊天、團隊、頻道和應用程式的[推動採用](adopt-microsoft-teams-landing-page.md)。
- 在您的 Teams 初始推出中包含精選應用程式，例如 Planner。在開始推動 Teams 的採用時，則新增其他[應用程式、Bot 和連接器](deploy-apps-microsoft-teams-landing-page.md)。
- [推出會議和研討會](deploy-meetings-microsoft-teams-landing-page.md)
- [推出雲端語音](cloud-voice-landing-page.md)
