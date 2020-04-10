---
title: Microsoft Teams 中的會議和召集會議
ms.reviewer: ''
description: 使用這些部署資源可協助您在 Microsoft Teams 中推出會議。
ms.topic: article
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7aee2a4a8e17480be9eb99b4504ef6967e6b2bb3
ms.sourcegitcommit: a610bfe9c0192432744dfaf8d5ff5c2bb5a16b00
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/08/2020
ms.locfileid: "43190859"
---
# <a name="meetings-and-conferencing-in-microsoft-teams"></a>Microsoft Teams 中的會議和召集會議

您已完成[開始使用](get-started-with-teams-quick-start.md)。 您已使用[聊天、團隊、頻道和應用程式](deploy-chat-teams-channels-microsoft-teams-landing-page.md)在組織中推出 Teams。 現在您已準備好要新增會議工作負載，包括[音訊會議](deploy-audio-conferencing-teams-landing-page.md)、視訊和共用。 本文將逐步引導您完成會議與音訊會議的推出。 請從觀看我們的 Teams 會議、召集會議和裝置影片開始 (3 分 28 秒)：

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE46ZdQ]

若要深入了解使用者的會議體驗，請參閱 [會議和通話](https://support.office.com/article/meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)。 


*2020 年 4 月新增功能*：會議召集人可以在會議期間按一下會議控制項中的 [結束會議]****，結束 Teams 中所有會議參與者的會議。  

*2019 年 11 月中的新功能*：您現在可以[使用 Advisor for Teams (預覽) 協助您推出 Microsoft Teams](use-advisor-teams-roll-out.md)。 Advisor for Teams (預覽) 會引導您完成 Teams 的推出，包括會議和召集會議。 在您於 Teams 中成功推出會議和召集會議之前，它會評估您的 Office 365 環境，找出可能需要更新或修改的最常用設定。

## <a name="meetings-and-conferencing-deployment-decisions"></a>會議和召集會議部署決策

Teams 為您的組織提供絕佳的現成體驗，而大部分組織認為預設設定就能滿足其需求。 本文可協助您決定是否要根據組織的設定檔和商務需求來變更任何預設設定，並逐步引導您完成每個變更。 我們已將設定分割成兩個群組，從[您最可能進行的變更](#core-deployment-decisions)的核心集開始。 根據組織的需求，第二個群組包括您可能想要設定的[其他設定](#additional-deployment-decisions)。

> [!Tip]
> 請觀看下列部分以深入了解會議：[IT 專業人員適用的 Microsoft Teams 中的會議簡介](https://aka.ms/teams-meetings-intro)


## <a name="meetings-and-conferencing-prerequisites"></a>會議和召集會議必要條件 

在組織中擴展您的會議部署之前，請用一些時間來檢閱並確認您的環境已備妥，可為使用者提供最佳的體驗。 請檢閱下列資訊，並視需要對您的環境進行任何必要的變更。

若要獲得 Teams 的最佳體驗，組織必須已部署 Exchange Online 和 SharePoint Online，並且必須具有 O365 經驗證的網域，例如 *contoso.com*。

若要將會議擴及整個組織，您應確保所有使用者位置都擁有網際網路存取權，可連線至 Office 365 服務。 您應至少確保已從使用者的位置，將下列常見連接埠設為對網際網路開放：

- 從將使用 Teams 的用戶端傳出的 TCP 連接埠 80 和 443
- 從將使用 Teams 的用戶端傳出的 UDP 連接埠 3478 到 3481

您可以使用[網路測試小幫手](https://www.powershellgallery.com/packages/NetworkTestingCompanion/1.5.2)來確認您的網路位置已針對支援會議體驗所需的語音及視訊流量準備就緒。

| 問問自己 | 動作 |
|--------------|--------|
|我的網路是否已準備好進行 Teams 會議部署？ | 若要確認您的網路已準備就緒，請參閱：<ul><li>[針對 Microsoft Teams 準備組織的網路](https://docs.microsoft.com/MicrosoftTeams/prepare-network)</li><li>[Office 365 URL 與 IP 位址範圍](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges)</li></ul> |
|||

## <a name="core-deployment-decisions"></a>核心部署決策

這些是大部分組織想要變更的設定 (如果 Teams 的預設設定不符合組織的需求)。

### <a name="teams-administrators"></a>Teams 系統管理員

Teams 提供了一組自訂管理員角色，可用來為組織管理 Teams。 這些角色為系統管理員提供各種能力。 

| 問問自己 | 動作 |
|--------------|--------|
|誰將獲指派 Teams 通訊系統管理員角色？|若要深入了解 Teams 系統管理員角色，請參閱[使用 Microsoft Teams 系統管理員角色管理來管理 Teams](using-admin-roles.md)。|
|誰將獲指派 Teams 通訊支援工程師角色？|若要指派系統管理員角色，[使用 Azure Active Directory 將系統管理員和非系統管理員角色指派給使用者](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。|
|誰將獲指派 Teams 通訊支援專員角色？||
|||

### <a name="meetings-settings"></a>會議設定 

會議設定可用於控制匿名使用者是否可以加入 Teams 會議、設定會議邀請，以及針對即時流量設定連接埠 (如果您要開啟服務品質，即 QoS)。 這些設定會用於使用者在組織中排程的所有 Teams 會議。 

| 問問自己 | 動作 |
|--------------|--------|
|我要自訂初始會議設定嗎？ |若要深入了解會議設定，請參閱 [Teams 中的會議教學課程](tutorial-meetings-in-teams.yml)。|
|我要實作 QoS 嗎？|如需 QoS 概念的相關資訊，請參閱 [Microsoft Teams 中的服務品質](qos-in-teams.md)。 案例和實作。|
|||

### <a name="meeting-policies"></a>會議原則

會議原則用於控制使用者加入 Teams 會議時可使用的功能。 您可以使用預設原則或是為組織中舉辦會議的人員建立一或多個自訂會議原則。 若要深入了解，請參閱 [Microsoft Teams 中的會議教學課程](tutorial-meetings-in-teams.yml)。

| 問問自己 | 動作 |
|--------------|--------|
|<ul><li>我要自訂初始會議原則嗎？</li><li>我需要多個會議原則嗎？</li><li>我如何判斷哪些使用者群組會套用哪些會議原則？</li></ul>|<br>請閱讀[在 Teams 中管理會議原則](meeting-policies-in-teams.md)。|
|||

### <a name="audio-conferencing"></a>音訊會議

音訊會議能讓會議參與者使用傳統有線電話、專用交換機 (PBX) 或行動電話撥入，透過公用交換電話網路 (PSTN) 加入會議，為組織提供任何會議 (臨機操作或排程) 的其他進入點。 

當您準備好要推出音訊會議時，請參閱深入的[音訊會議推出](deploy-audio-conferencing-teams-landing-page.md)指導方針。

### <a name="meeting-room-and-personal-devices"></a>會議室和個人裝置

若要在 Teams 中獲得最佳會議體驗，請考慮使用 Teams 裝置，例如會議室系統、電話、耳機和相機。 若要深入了解，請參閱[適用於智慧型通訊的 Microsoft Teams 裝置](https://products.office.com/microsoft-teams/across-devices)。

| 問問自己 | 動作 |
|--------------|--------|
|我要為使用者購買個人裝置嗎？ |請閱讀[在 Teams 中管理裝置](device-management.md)。 |
|我要為會議室購買並部署會議室系統裝置嗎？|請閱讀[會議室裝置和解決方案](https://docs.microsoft.com/skypeforbusiness/certification/devices-meeting-rooms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)。|
|||

### <a name="reporting"></a>報告

使用活動報告來查看組織中的使用者如何使用 Teams。 例如，如果有人還沒使用 Teams，可能是他們不知道如何開始，或不了解如何使用 Teams 提高生產力和共同作業。 組織可以使用活動報告來決定要優先進行訓練和溝通的方面。 


| 問問自己 | 動作 |
|--------------|--------|
|誰將負責報告？|請閱讀[對 Teams 使用活動報告](teams-activity-reports.md)。  |
|誰將負責監視使用情況？|請閱讀[在 Teams 中監視使用情況和意見反應](get-started-with-teams-monitor-usage-and-feedback.md)。|
|||

## <a name="additional-deployment-decisions"></a>其他部署決策

根據組織的需求和組態而定，您可能會想要變更這些設定。

### <a name="bandwidth-planning"></a>頻寬規劃 

頻寬規劃可讓組織估計在其廣域網路和網際網路連結上支援會議所需的頻寬，讓他們能夠確認網路已正確佈建，可支援向外擴充的會議服務。 

| 問問自己 | 動作 |
|--------------|--------|
| 我是否需要在會議推出之前和期間進行頻寬規劃？ |如需詳細資訊和可簡化規劃程序的工具連結，請參閱[網路整備](3-envision-evaluate-my-environment.md#network-readiness)。|
|||

### <a name="meeting-recording-and-archiving"></a>會議錄製和封存

使用者可以記錄其會議和群組通話，以擷取音訊、視訊和螢幕共用的活動。 您也可以使用自動轉錄的錄製選項，便於使用者播放具有隱藏式輔助字幕的會議錄製，並在文字記錄中搜尋重要的討論項目。 錄製會在雲端中進行，並儲存到 Microsoft Stream，因此使用者可以安全地在整個組織內共用檔案。 若要尋找會議的錄製，請前往會議交談。

若要深入了解，請參閱 [Teams 雲端會議錄製](cloud-recording.md)。

| 問問自己 | 動作 |
|--------------|--------|
| 我將開啟會議轉錄服務嗎？|請參閱[開啟或關閉錄製轉錄](cloud-recording.md#turn-on-or-turn-off-recording-transcription)|
|||


### <a name="live-events-policies"></a>即時事件原則

Teams 即時事件原則用於管理使用者群組的事件設定。 您可以使用預設原則或建立可指派給組織內舉辦活動的使用者的額外原則。 

| 問問自己 | 動作 |
|--------------|--------|
| 我的組織是否會使用 Teams 即時事件？| 如需規劃、設定及設定 Teams 即時事件的詳細資訊，請參閱[即時事件文章](teams-live-events/what-are-teams-live-events.md)。|
|||

### <a name="conference-room-systems-rollout"></a>會議室系統推出

擁有多個會議室的組織可能需要使用結構化的方法來清查其會議室、找出適當的裝置，然後將它們推出。 



| 問問自己 | 動作 |
|--------------|--------|
| 要推出會議室系統，我需要做什麼？|請查看[規劃 Microsoft Teams 會議室](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)文章。|
|||

### <a name="cloud-video-interop"></a>雲端視訊 Interop

雲端視訊 Interop 可讓第三方會議室裝置加入 Teams 會議。 

具有內容共同作業的視訊電話會議可協助您充分利用會議。 不過，會議室系統和裝置的升級成本過於高昂。 適用於 Teams 的雲端視訊 Interop 可搭配第三方系統使用，並可為所有參與者 (會議室中或 Teams 用戶端內) 提供原生的會議體驗。 

| 問問自己 | 動作 |
|--------------|--------|
| 我將隨著會議室系統部署使用雲端視訊 Interop 解決方案嗎？ | 請閱讀 [Teams 雲端視訊 Interop](cloud-video-interop.md)。|
|||


### <a name="personal-device-rollout"></a>個人裝置推出

當規劃推出大量個人裝置以支援會議或語音部署時，請考慮使用可重複執行的站對站推出程序，以提供相同的品質。

| 問問自己 | 動作 |
|--------------|--------|
|我要使用站對站方法來推出會議嗎？ |  [Teams 的網站啟用語音手冊](3-onboard-deploy-my-service.md#site-enablement-playbook-for-microsoft-teams-voice-workloads)可提供良好的基礎，供您用於自己的部署。 本指南著重於語音，但是裝置交付、帳戶整備、採用及訓練的一般原則亦適用大型會議部署。 |
|||

### <a name="troubleshoot-meeting-and-call-quality"></a>對會議和通話品質進行疑難排解 

Teams 有兩種方式可供您監視和疑難排解通話品質問題：[通話分析和通話品質儀表板](difference-between-call-analytics-and-call-quality-dashboard.md)。 通話分析能顯示每位使用者在特定通話和會議的裝置、網路和連線詳細資訊。 通話分析的設計目的在於協助系統管理員和支援人員疑難排解特定通話的通話品質問題，而通話品質儀表板的設計目的則是在協助系統管理員和網路工程師最佳化網路。 通話品質儀表板的重點不在特定使用者身上，而是會查看整個 Teams 組織的匯彙資訊。 

|問問自己|動作 |
|------------|-------|
| 誰會負責監視及疑難排解通話品質問題？ | 如需疑難排解通話品質問題所需權限等級的相關資訊，請閱讀[使用通話分析來疑難排解不良通話品質](use-call-analytics-to-troubleshoot-poor-call-quality.md)。|
|||

### <a name="operate-your-meetings-service"></a>操作會議服務

請務必了解 Teams 服務的整體運作狀況，這樣才能主動提醒在組織中的其他人會影響服務的任何活動。 [營運我的服務](1-drive-value-operate-my-service.md)文章提供服務作業的深入指引。

|問問自己|動作 |
|------------|-------|
|我的組織中的哪些人員將負責管理會議服務？ | 請確定這個人員擁有管理您的會議服務所需的 Teams 系統管理員權限。 若要深入了解 Teams 系統管理員角色，請參閱[使用 Microsoft Teams 系統管理員角色管理來管理 Teams](using-admin-roles.md)。|
|||


## <a name="next-steps"></a>後續步驟
- 在您的組織中推動會議和召集會議的[採用](adopt-microsoft-teams-landing-page.md)。
- [新增音訊會議](deploy-audio-conferencing-teams-landing-page.md)
- [推出雲端語音](cloud-voice-landing-page.md)
- 在您的 Teams 初始推出中包含精選應用程式，例如 Planner。 在開始推動 Teams 的採用時，則新增其他[應用程式、Bot 和連接器](deploy-apps-microsoft-teams-landing-page.md)。
