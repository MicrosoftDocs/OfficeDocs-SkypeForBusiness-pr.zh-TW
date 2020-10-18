---
title: 設定音訊會議設定 - Microsoft Teams
ms.reviewer: ''
description: 使用這些部署資源幫助您在 Microsoft Teams中，將音訊會議做為會議工作負載的一部分推出。
ms.topic: article
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: admin
ms.date: 01/28/2019
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
ms.custom:
- seo-marvel-mar2020
f1.keywords:
- NOCSH
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 755a8499f62e39333b075519cc181dbd7c44e143
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521620"
---
# <a name="learn-how-to-deploy-audio-conferencing-in-microsoft-teams"></a>了解如何在 Microsoft Teams 中部署音訊會議

音訊會議是由一般電話加入 Teams 會議，並由會議撥出電話號碼的功能。 請確認您已在組織中檢閱[會議推出](deploy-meetings-microsoft-teams-landing-page.md)做為推出音訊會議的一部分。

## <a name="audio-conferencing-deployment-decisions"></a>音訊會議部署決策

本文可協助您決定是否要根據組織的設定檔和商務需求來變更任何預設音訊會議設定，並逐步引導您完成每個變更。 我們已將設定分割成兩個群組，從[您最可能進行的變更](#core-deployment-decisions)的核心集開始。 根據組織的需求，第二個群組包括您可能想要設定的[其他設定](#additional-deployment-decisions)。

您只需要為打算排程或主持會議的人員設定音訊會議即可。 撥入的會議出席者不需獲得任何指派的授權或進行任何其他設定。 撥入 (撥號) 會議對於不在現場且無法在其筆記本電腦或行動裝置上使用商務用 Skype 或 Teams 應用程式的使用者而言，是很實用的功能。 


## <a name="audio-conferencing-prerequisites"></a>音訊會議的必要條件 

您必須先考量下列問題，才可推出 Teams 的音訊會議：

|問問自己|動作 |
|------------|-------|
|我所在的國家/地區是否可使用音訊會議？|若要了解您的國家/地區是否可使用音訊會議，請參閱[音訊會議與通話方案的適用國家/地區](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。|
|我的使用者是否具有 Teams 音訊會議的適當授權？|音訊會議授權可隨 Microsoft 365 或 Office 365 E5 訂閱取得，或是從 Microsoft 365 商務標準版、E1 或 E3 訂閱的附加服務取得。 <ul><li>若要取得並指派授權，請參閱[試用或購買 Microsoft 365 或 Office 365 中的音訊會議](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)和[指派或移除 Microsoft 365 Apps 商務版的授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</li><li> 若要深入了解，請參閱 [Microsoft Teams 附加元件授權](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)。 </li><li>若要查看包含在各方案中的雲端功能，請參閱[根據您方案的授權選項](teams-add-on-licensing/office-365-business-premium.md)文章。</li></ul>|
|對於獲得音訊會議授權的使用者，我是否需要為他們購買通訊點數？|若要深入了解，請參閱[什麼是通訊點數](what-are-communications-credits.md)，然後查看下方的[通訊點數](#communications-credits) 一節。|
|||


## <a name="core-deployment-decisions"></a>核心部署決策

符合音訊會議先決條件之後，請完成下列工作以為您的使用者設定音訊會議。


### <a name="teams-administrators"></a>Teams 系統管理員

Teams 提供了一組自訂管理員角色，可用來為組織管理 Teams。 這些角色為系統管理員提供各種能力。 

| 問問自己 | 動作 |
|--------------|--------|
|誰將獲指派 Teams 通訊系統管理員角色？|若要深入了解 Teams 系統管理員角色，請參閱[使用 Microsoft Teams 系統管理員角色管理來管理 Teams](using-admin-roles.md)。|
|誰將獲指派 Teams 通訊支援工程師角色？|若要指派系統管理員角色，[使用 Azure Active Directory 將系統管理員和非系統管理員角色指派給使用者](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。|
|誰將獲指派 Teams 通訊支援專員角色？||
|||

### <a name="conferencing-bridges-and-phone-numbers"></a>會議橋接器和電話號碼

會議橋接器可讓與會者使用電話撥入會議。 您可以使用會議橋接器的預設設定，或變更電話號碼 (付費和免付費) 以及其他設定，例如 PIN 或使用的語言。

如需詳細資訊，請參閱[音訊會議](audio-conferencing-in-office-365.md)。

|問問自己|動作 |
|------------|-------|
|是否需要新增新的會議橋接器號碼？| 若要新增新號碼，請參閱[取得服務電話號碼](/microsoftteams/getting-service-phone-numbers)。|
|需要修改橋接器設定嗎？|若要修改橋接器設定，請參閱[變更音訊會議橋接器的設定](change-the-settings-for-an-audio-conferencing-bridge.md)。|
|需要連接埠號碼搭配音訊會議使用嗎？|如需連接埠號碼的詳細資訊，請參閱[將電話號碼移轉至 Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。|
|||


### <a name="default-and-alternate-languages"></a>預設和替代語言

Teams 音訊會議可讓您設定會議橋接器的預設和替代語言。

|問問自己|動作 |
|------------|-------|
| 自動語音應答問候語應選擇哪些語言？ | 若要選擇語言，請參閱[設定音訊會議的自動語音應答語言](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)。|
|||

### <a name="conferencing-bridge-settings"></a>會議橋接器設定 

設定會議橋接 (包括預設和替代語言) 後，您應確認預設設定 (例如，進入/退出通知和 PIN 長度) 就是您要使用的設定。 如果不是，您可加以變更。 

|問問自己|動作 |
|------------|-------|
| 使用者加入或離開會議時，出席者是否會聽到通知？ | 若要變更這些設定，請參閱[變更音訊會議橋接器的設定](change-the-settings-for-an-audio-conferencing-bridge.md)。|
|會議召集人用來開始會議的 PIN 所需長度為何？||
|||

### <a name="dial-in-phone-number-settings-for-users-who-lead-meetings"></a>會議主持使用者的撥入電話號碼設定

在建立音訊會議橋接器之後，您必須設定主持會議的使用者所將使用的付費和/或免付費電話號碼。

|問問自己|動作 |
|------------|-------|
| 要指派給每位主持會議使用者之會議橋接器電話號碼為何？ | 若要為使用者指派撥入電話號碼，請參閱[步驟7：為主持會議使用者指派撥入電話號碼](set-up-audio-conferencing-in-teams.md#step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings)。 |
|||

### <a name="communications-credits"></a>通訊點數

若要提供免付費會議橋接器電話號碼，以及支援電話會議撥出的國際電話號碼，您必須為組織設定通訊點數。 若要深入了解通訊點數，請參閱[什麼是通訊點數？](what-are-communications-credits.md)。

|問問自己|動作 |
|------------|-------|
|我的語音會議實作是否需要通訊點數？ |若要了解您是否需要設定通訊點數，請參閱[設定貴組織的通訊點數](set-up-communications-credits-for-your-organization.md)。|
|如果通訊點數為必須，應該花費多少購買？|若要決定通訊點數金額，請參閱[建議的資金金額](what-are-communications-credits.md#recommended-funding-amounts)。|
|需要設定自動儲值金額嗎？|若要設定自動儲值金額，請參閱[設定貴組織的通訊點數](set-up-communications-credits-for-your-organization.md)。|
|||



## <a name="additional-deployment-decisions"></a>其他部署決策

根據組織的需求和組態而定，您可能會想要變更這些設定。

### <a name="outbound-calling-restriction-policies"></a>撥出通話限制原則 

身為系統管理員，您可以使用撥出通話控制來限制組織中的使用者可進行的音訊會議類型和終端使用者 PSTN 通話類型。

|問問自己|動作 |
|------------|-------|
| 要限制允許的撥出通話類型嗎？ | 若要限制撥出通話，請參閱[音訊會議和使用者 PSTN 通話的撥出通話限制原則](outbound-calling-restriction-policies.md)。|
|||


### <a name="dial-plans"></a>撥號對應表

撥號對應表包含在 Microsoft 365 或 Office 365 的電話系統中，是可將撥打的電話號碼轉換為替代格式 (通常是 E.164 格式)，以進行通話授權和通話路由的正規化規則集合。

如需撥號對應表的相關資訊，請參閱[什麼是撥號對應表？](what-are-dial-plans.md)

|問問自己|動作 |
|------------|-------|
|我的組織需要自訂的撥號對應表？|若要幫助決定是否需要自訂的撥號對應表，請參閱[規劃租用戶撥號對應表](what-are-dial-plans.md#planning-for-tenant-dial-plans)。 |
|哪些使用者需要自訂的撥號對應表，以及應指派給每個使用者何種租用戶撥號對應表？|若要使用 PowerShell 將使用者新增至自訂撥號對應表，請參閱 [建立及管理撥號對應表](create-and-manage-dial-plans.md)。|
|||

### <a name="troubleshoot-meeting-and-call-quality"></a>對會議和通話品質進行疑難排解 

Teams 有兩種方式可供您監視和疑難排解通話品質問題：[通話分析和通話品質儀表板](monitor-call-quality-qos.md)。 通話分析能顯示每位使用者在特定通話和會議的裝置、網路和連線詳細資訊。 通話分析的設計目的在於協助系統管理員和支援人員疑難排解特定通話的通話品質問題，而通話品質儀表板的設計目的則是在協助系統管理員和網路工程師最佳化網路。 通話品質儀表板的重點不在特定使用者身上，而是會查看整個 Teams 組織的匯彙資訊。 

|問問自己|動作 |
|------------|-------|
| 誰會負責監視及疑難排解通話品質問題？ | 如需疑難排解通話品質問題所需權限等級的相關資訊，請參閱[使用通話分析來疑難排解低劣的通話品質](use-call-analytics-to-troubleshoot-poor-call-quality.md)。|
|||


## <a name="next-steps"></a>後續步驟
- 組織中音訊會議的[驅動採用率](adopt-microsoft-teams-landing-page.md)。
- [推出雲端語音](cloud-voice-landing-page.md)
- 在您的 Teams 初始推出中包含精選應用程式，例如 Planner。 在開始推動 Teams 的採用時，則新增其他[應用程式、Bot 和連接器](deploy-apps-microsoft-teams-landing-page.md)。
