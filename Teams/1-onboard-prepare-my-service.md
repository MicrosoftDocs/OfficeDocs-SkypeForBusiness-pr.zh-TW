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
description: 使用上Microsoft 365檢查清單Microsoft 365 Office 365 Teams，並Teams核心功能、網路和雲端語音工作負載。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b42abb1f82dd5e080e98127d15435d3250a73d87
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58590927"
---
# <a name="prepare-my-service"></a>準備我的服務

本文概述為貴組織準備雲端語音服務的需求。 通過妥善準備，您可以確定已準備好為貴組織提供雲端語音功能。

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>針對語音工作負載的Microsoft Teams檢查清單

下列檢查清單會引導您完成在 Microsoft Teams 中執行音訊會議、電話系統 使用通話方案 (「通話方案」) 和 電話系統 直接路由 (「直接路由」) 功能的步驟。

*  [準備Microsoft 365或Office 365 Teams](onboarding-checklist-enable-office-365.md)

*  [設定Teams核心功能](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [準備您的網路](prepare-network.md)

*  [設定雲端語音工作負載Teams](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [在中設定直接路由Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

這些檢查清單的工作和活動是核心的「工作」專案，可適用于每一個部署雲端語音功能Teams。 您可以自訂檢查清單，以包含您特定行程的活動Teams工作。

>[!NOTE]
>本指南僅著重于通話方案、音訊會議和直接路由。 如果您是新進[Teams，請](teams-overview.md)Microsoft Teams。 有關規劃部署之一般Teams，請從部署聊天、團隊、頻道[和應用程式](deploy-chat-teams-channels-microsoft-teams-landing-page.md)開始，Microsoft Teams。

使用提供的檢查清單來追蹤每個個別活動和工作的狀態，並確保您未略過任何重要步驟。 每個活動包含所需動作的詳細描述，以及可用於完成該活動之額外資訊的參照。

雖然我們建議您依序遵循檢查清單，但確切的順序會視您的部署範圍，以及您環境的組組和複雜度而決定。 他們組織起來支援「greenfield」Teams部署 (之前沒有 商務用 Skype Online 目前狀態) 或從 商務用 Skype Online 移往 Teams。 如果您是從線上商務用 Skype，您可能已經完成其中一些活動，現在可以忽略這些活動。

當您以每個網站為基礎啟動使用者時，我們強烈建議您使用 Voice [ (Playbook ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)) 網站啟用 Playbook) 做為這些檢查清單的補充指南。

>[!NOTE]
>大部分的設定設定在 Teams 和 商務用 Skype 之間商務用 Skype常見。 您可以使用系統管理Microsoft 365 系統管理系統管理Microsoft Teams設定這些設定。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>決策點</td><td><ul><li>神秘將負責監督上機檢查清單的完成情況？</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>後續步驟</td><td><ul><li>下載上機檢查清單。</li><li>依照貴組織的部署計畫，逐步完成上載檢查清單專案。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>繼續上機

完成這些檢查清單之後，您已成功新增語音功能至您的Teams部署。

下一個步驟是使用 Voice [ (Playbook) ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 網站啟用 Playbook) 來協助您在每個網站上上手，並有助於確保您規劃並執行重要的網站特定活動。

-   已準備就緒的按網站推出計畫的網站

-   建立服務管理程式

-   執行測試和補救

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>測試雲端語音工作負載Teams

在您將 Teams 雲端語音業務成功及技術實施計畫定義為構想階段中的一部分，並著手在系統管理中心進行您想要的設定之後，下一個步驟是驗證貴組織的預期和需求是否透過功能、功能和可用性符合。 在生產環境中部署試驗或最終部署之前，您應該先執行此驗證步驟。

您可以利用在構想階段期間定義的商務成功計畫，做為判斷活動、預期、功能/功能測試案例，以及測試階段期間要評估的整體範圍的基礎。

## <a name="define-your-testing-approach"></a>定義您的測試方法

測試方法最簡單的形式是檢閱音訊會議、通話方案或直接路由服務的功能，並開發測試計劃，以確認您的功能需求在範圍中符合使用者。 以下是音訊會議實施之板載階段範例測試計劃。


| 要測試的音訊會議功能 | 結果摘要 | 其他筆記 |
|------------|-----------------|------------------|
| 排程包含音訊Teams撥入資訊的臨時會議 | 通過/失敗   | 待定 |
| 使用電話使用會議音訊，從 PSTN 撥入會議，並包含提供的撥入資訊 | 通過/失敗 | 待定 |
| 透過 PSTN 撥出電話，讓其他人加入現有的會議 | 通過/失敗 | 待定 |



| 要測試的通話方案或直接路由功能 | 結果摘要 | 其他筆記 |
|----------------------------------------------------|-----------------|------------------|
| 撥打 PSTN 號碼進行 PSTN 通話       | 通過/失敗       | 待定 |
| 從行動電話、有線電話 (撥打 PSTN 號碼)  | 通過/失敗 | 待定|
| 將 PSTN 通話從一位Teams轉接到另一個使用者 | 通過/失敗 | 待定 |


>[!TIP]
>若要協助建立測試案例做為起點，請參閱在會議[Teams提供的使用者指南清單](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)。

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>設定雲端語音工作負載Teams

現在，您定義測試方法後，下一個步驟就是針對雲端語音功能來Teams服務環境和使用者。

有關其他資訊，請參閱：

- [音訊會議的技術規劃](./cloud-voice-landing-page.md)

- [設定 Microsoft Teams 的音訊會議](set-up-audio-conferencing-in-teams.md)

- [使用通話方案電話系統方案的技術規劃](calling-plan-landing-page.md)

- [設定通話和通話商務用 Skype Microsoft Teams](/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [規劃直接路由](./direct-routing-plan.md)

- [設定直接路由](./direct-routing-configure.md)

### <a name="execute-the-test-plan"></a>執行測試計劃

[//]: # (編輯正常嗎？「使用者」對我來說似乎有點模糊。)
在使用者環境和服務完成配置之後，測試的最後一個步驟包括測試計劃執行，並著重于功能驗證。 

**音訊會議測試使用者和網站在範圍中的先決條件和假設：**

-   音訊會議服務的企業使用案例定義已經完成。

-   音訊會議所需的授權可供使用，而且已指派。

-   已識別組織網站和使用者群組清單。

-   已識別並設定具有語言喜好設定之專用和共用音訊會議電話撥入清單。

-   [已](what-are-communications-credits.md) 針對 (設定) 通訊信用額度。

-   音訊會議橋接器設定已識別並設定為 (PIN 長度、進入/離開通知、啟用通知喜好設定) 。

-   已識別、設定及應用支援音訊會議撥出案例的租使用者會議原則及撥號方案設定。

-   已識別並配置音訊會議合規性需求。

**通話方案測試使用者和網站在範圍中的先決條件和假設：**

-   已完成通話方案服務的企業使用案例定義。

-   通話方案所需的授權是可用的，而且已指派。

-   已識別組織網站和使用者群組清單。

-   電話指派給使用者的號碼已經取得或移植到 Microsoft，可在租使用者入口網站取得。

-   [已](what-are-communications-credits.md) 針對 (設定) 通訊信用額度。

-   已識別、設定及應用支援通話方案案例的租使用者使用者原則與撥號方案設定。

-   已識別並配置通話方案合規性需求。

**使用者和網站在範圍中的直接路由測試先決條件和假設：**

-   直接路由服務的企業使用案例定義已經完成。

-   直接路由所需的授權是可用的，而且已指派。

-   已識別組織網站和使用者群組清單。

-   已[部署、 (SBC](./direct-routing-plan.md#supported-session-border-controllers-sbcs)) 驗證會話邊界控制器，並搭配 電話系統。

-   Enterprise已啟用語音，且已指派電話號碼。

-   已識別、配置及指派語音路由策略。

-   Microsoft Teams範圍中使用者偏好的通話用戶端。
 
-   已識別並配置直接路由合規性需求。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>決策點</td><td><ul><li>決定將部署哪些音訊會議功能 (服務決策) 。</li><li>識別音訊會議的使用者功能需求。</li><li>識別音訊會議的服務組組需求。</li><br><li>決定是否要部署和配置直接路由或通話方案。<li>決定電話系統服務決策中 (哪些功能) 。</li><li>識別通話方案或直接路由的使用者功能需求。</li><li>識別通話方案或直接路由的服務組組需求。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>後續步驟</td><td><ul><li>開發和記錄您的測試計劃方法。</li><li>在音訊會議功能範圍內準備您的服務環境和使用者。</li><li>在通話方案或直接路由功能範圍內準備您的服務環境和使用者。</li><li>針對您想要啟用的音訊會議功能執行測試驗證。</li><li>針對您想要啟用的通話方案或直接路由功能執行測試驗證。</li><li>針對任何測試失敗，請確認您的組組正確無誤，檢閱社群文章，並提出支援案例 ，如有必要。</li></ul></td></tr>
</table>


若要進一步瞭解如何在 Teams 中執行音訊會議測試的詳細指南，請參閱音訊會議[的詳細測試指南](./deploy-audio-conferencing-teams-landing-page.md)。

有關如何在 Teams 中執行通話方案測試的其他詳細[電話系統。](./cloud-voice-landing-page.md)

<!--ENDOFSECTION-->