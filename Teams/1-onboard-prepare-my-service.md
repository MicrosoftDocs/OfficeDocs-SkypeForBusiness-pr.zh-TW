---
title: 準備部署雲端語音服務
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 使用 [加入檢查清單] 來為小組準備 Office 365，並設定小組核心功能、網路和雲端語音工作負載。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 710a365ef68d3e187013892ef978cd8e12557cc1
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137993"
---
# <a name="prepare-my-service"></a>準備我的服務

本文概述為貴組織準備雲端語音服務的需求。 透過正確地準備，您可以確定您已準備好將雲端語音功能提供給您的組織。

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>Microsoft 團隊語音工作負載的加入檢查清單

下列檢查清單會逐步引導您完成在 Microsoft 團隊中實現音訊會議、電話系統與通話方案（「通話方案」），以及手機系統 Direct 路由（"直接路由"）功能的步驟。

*  [為團隊準備 Office 365](onboarding-checklist-enable-office-365.md)

*  [設定團隊核心功能](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [準備您的網路](prepare-network.md)

*  [在團隊中設定雲端語音工作負載](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [在團隊中設定直接路由](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

這些檢查清單中的工作與活動是「待辦事項」專案，可套用至團隊的每個雲端語音功能部署。 您可以自訂檢查清單，以包含您自己團隊歷程所特有的活動和工作。

>[!NOTE]
>本指南專門說明通話方案、音訊會議及直接路由。 如果您是團隊新手，請參閱[Microsoft 團隊的概覽](teams-overview.md)。 如需規劃團隊部署的一般指導方針，請先[在 Microsoft 團隊中開始部署聊天、團隊、頻道和應用程式](deploy-chat-teams-channels-microsoft-teams-landing-page.md)。

使用提供的檢查清單來追蹤每個個別活動和工作的狀態，並確認您未略過任何重要步驟。 每個活動都包含所需動作的詳細描述，以及您可以用來完成該活動的其他資訊參考。

雖然我們建議您依照檢查清單的順序，但確切的順序取決於您的部署範圍，以及環境的設定和複雜性。 其組織結構是支援「嶄新」團隊部署（沒有先前的商務用 skype Online 目前狀態），或從商務用 Skype Online 遷移至團隊。 如果您是從商務用 Skype Online 進行遷移，您可能已經完成這些活動，而且現在可以略過它們。

如果您是以每個網站為基礎加入使用者，我們強烈建議您使用 [[網站啟用嚮導] （行動手冊））](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)作為這些檢查清單的輔助指南。

>[!NOTE]
>在團隊與商務用 Skype Online 之間，大部分的設定都是常見的配置。 您使用 Microsoft 365 系統管理中心及 Microsoft 團隊系統管理中心來設定這些設定。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>決策點</td><td><ul><li>誰將負責監視加入核對檢查的完成情況？</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>後續步驟</td><td><ul><li>下載加入檢查清單。</li><li>依照貴組織的部署方案逐步逐步完成 [加入檢查清單專案]。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>繼續加入

完成這些檢查清單後，您就可以成功地在小組部署中新增語音功能了。

在下一個步驟中，使用 [[網站啟用行動手冊-語音（行動手冊）](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) ] 協助您在每個網站上為您的使用者進行設計，並協助確保您規劃並執行重要的網站特定活動。

-   [由網站推出方案準備就緒] 網站

-   建立服務管理流程

-   執行測試與修正

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>在團隊中測試雲端語音工作負載

在構想階段中定義並記錄您的小組雲端業務成功和技術實現方案之後，且在系統管理中心進行您想要的設定後，下一步就是透過功能、功能和可用性來驗證貴組織的預期與需求是否已完成。 您應該先執行此驗證步驟，才能在您的生產環境中部署試驗或最終部署。

您可以利用在您的構想階段所定義的商業成功方案，作為判斷活動、預期、功能/功能測試案例的基礎，以及在測試階段評估的整體範圍。

## <a name="define-your-testing-approach"></a>定義您的測試方法

在其最簡單的形式中，您的測試方法是以您的語音會議、呼叫方案或直接路由服務的功能功能為基礎，並開發測試方案，以驗證範圍中的使用者是否符合您的功能需求。 下列是音訊會議實現的板載階段範例測試方案。


| 要測試的音訊會議功能 | 結果摘要 | 其他筆記 |
|------------|-----------------|------------------|
| 安排包含音訊會議撥入資訊的即席小組會議 | 通過/失敗   | TBD |
| 使用電話從 PSTN 撥入會議音訊，並提供隨附的撥入資訊 | 通過/失敗 | TBD |
| 透過 PSTN 撥出，將其他人加入現有的會議 | 通過/失敗 | TBD |



| 通話方案或直接路由功能以進行測試 | 結果摘要 | 其他筆記 |
|----------------------------------------------------|-----------------|------------------|
| 透過撥 PSTN 號碼撥打 PSTN 電話       | 通過/失敗       | TBD |
| 從外部線路撥打 PSTN 號碼（行動裝置、有線電話），接聽 PSTN 電話 | 通過/失敗 | TBD|
| 將 PSTN 呼叫從一個團隊使用者轉接到另一個。 | 通過/失敗 | TBD |


>[!TIP]
>若要協助將測試案例建立作為起點，請參閱[小組會議和通話](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)中提供的使用者指南清單。

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>為團隊設定雲端語音工作負載

現在您已定義測試方法，下一個步驟是在團隊雲端語音功能的範圍內設定您的服務環境和使用者。

如需其他資訊，請參閱：

- [音訊會議的技術規劃](cloud-voice-deployment.md)

- [設定 Microsoft Teams 的音訊會議](set-up-audio-conferencing-in-teams.md)

- [使用通話方案的電話系統技術規劃](calling-plan-landing-page.md)

- [設定商務用 Skype 和 Microsoft 團隊的通話方案](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [規劃直接路由](https://docs.microsoft.com/microsoftteams/direct-routing-plan)

- [設定直接路由](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

### <a name="execute-the-test-plan"></a>執行測試方案

[//]: # (編輯好嗎？「使用者」似乎對我而言有點不明確。)
在使用者環境和服務設定之後，測試的最後一個步驟，包括將焦點放在功能和功能驗證的測試方案執行。 

**音訊會議：針對範圍中的使用者和網站，測試先決條件及假設：**

-   已完成音訊會議服務的商務使用案例定義。

-   提供音訊會議所需的授權，且已指派。

-   已識別組織網站和使用者群組的清單。

-   已識別並設定具有語言喜好設定的專用和共用音訊會議撥入號碼的清單。

-   已針對您的組織設定[通訊點數](what-are-communications-credits.md)（如有需要）。

-   已識別並設定音訊會議的 [會議橋接] 設定（PIN 長度、進入/結束通知、啟用通知喜好設定）。

-   已識別、設定及套用支援音訊會議撥出案例的租使用者會議原則和撥號方案設定。

-   已確認並設定音訊會議規範需求。

**針對範圍中的使用者和網站，呼叫方案測試先決條件與假設：**

-   已完成通話方案服務的商務使用案例定義。

-   提供通話方案所需的授權，且已指派。

-   已識別組織網站和使用者群組的清單。

-   要指派給使用者的電話號碼已取得或移植至 Microsoft，且可在租使用者入口網站使用。

-   已針對您的組織設定[通訊點數](what-are-communications-credits.md)（如有需要）。

-   已識別、設定及套用支援通話方案案例的租使用者原則和撥號方案設定。

-   已確認及設定通話方案規範需求。

**在範圍中針對使用者和網站的直接路由測試先決條件及假設：**

-   已完成直傳送服務的商務使用案例定義。

-   直接路由所需的授權可供使用且已指派。

-   已識別組織網站和使用者群組的清單。

-   已[驗證的會話邊界控制器（SBC）](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs)已部署、設定並與電話系統配對。

-   已啟用企業語音，且已指派電話號碼。

-   已確認、設定並指派語音路由策略。

-   Microsoft 團隊已設定為 [作用中的使用者] 的首選呼叫用戶端。
 
-   已確認並設定直接路由合規性需求。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>決策點</td><td><ul><li>決定將部署哪些音訊會議功能功能（服務決策）。</li><li>識別音訊會議的使用者功能需求。</li><li>識別音訊會議的服務設定需求。</li><br><li>決定是否要部署及設定直接路由或通話方案。<li>決定要部署哪些電話系統功能功能（服務決策）。</li><li>識別通話方案或直接路由的使用者功能需求。</li><li>識別通話方案或直接路由的服務設定需求。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>後續步驟</td><td><ul><li>開發並記錄您的測試方案方法。</li><li>為您的服務環境和使用者準備作用中的音訊會議功能。</li><li>針對通話方案或直接路由功能，在範圍中準備您的服務環境和使用者。</li><li>針對您想要啟用的音訊會議功能執行測試驗證。</li><li>針對您想要啟用的通話方案或直接路由功能執行測試驗證。</li><li>針對任何測試失敗，請確認您的設定正確無誤、查看社區文章，並視需要（如果需要的話）引發支援案例。</li></ul></td></tr>
</table>


如需如何在團隊中執行音訊會議測試的其他詳細指導方針，請參閱[音訊會議的詳細測試指南](onboarding-test-plan-for-enterprises-Audio-Conferencing.md)。

如需如何在團隊中針對通話方案進行測試的其他詳細指導方針，請參閱[電話系統的詳細測試指南](onboarding-test-plan-for-enterprises-Phone-System.md)。

<!--ENDOFSECTION-->
