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
description: 使用上線檢查清單來為Teams準備Microsoft 365或Office 365，並設定Teams核心功能、網路和雲端語音工作負載。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a91a57a077db38675a62238289ad2c204040a9cd
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675435"
---
# <a name="prepare-my-service"></a>準備我的服務

本文將概略說明為貴組織準備雲端語音服務的需求。 透過妥善準備，您可以確定您已準備好為組織提供雲端語音功能。

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>Microsoft Teams語音工作負載的上線檢查清單

下列檢查清單會逐步引導您執行音訊會議、電話系統使用通話方案 (「通話方案」) ，以及電話系統直接路由 (「直接路由」) 功能Microsoft Teams中的步驟。

*  [為Teams準備Microsoft 365或Office 365](onboarding-checklist-enable-office-365.md)

*  [設定Teams核心功能](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [準備您的網路](prepare-network.md)

*  [在 Teams 中設定雲端語音工作負載](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [在 Teams 中設定直接路由](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

這些檢查清單中的工作和活動是套用至每個雲端語音功能部署的核心「待辦事項」專案，Teams。 您可以自訂檢查清單，以包含您專屬Teams旅程的活動和工作。

>[!NOTE]
>本指引僅著重于通話方案、音訊會議和直接路由。 如果您是Teams的新使用者，請檢閱[Microsoft Teams概觀](teams-overview.md)。 如需規劃Teams部署的一般指導方針，請從在[Microsoft Teams 中部署聊天、團隊、頻道和應用程式](deploy-chat-teams-channels-microsoft-teams-landing-page.md)開始。

使用提供的檢查清單來追蹤每個個別活動和工作的狀態，並確定您沒有略過任何重要步驟。 每個活動都包含必要動作的詳細描述，以及您可以用來完成該活動的其他資訊的參照。

雖然我們建議您依序遵循檢查清單，但確切的順序將視您的部署範圍以及您的環境設定和複雜度而定。 它們的組織是為了支援「綠原」Teams部署 (一個之前沒有線上商務用 Skype目前狀態) 的部署，或是從 商務用 Skype Online 移轉到Teams。 如果您是從 商務用 Skype Online 進行移轉，您可能已完成其中一些活動，現在可以略過這些活動。

當您在每個網站上線使用者時，強烈建議您使用 [Voice (Playbook 的網站啟用播放簿) ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 這些檢查清單的補充指南。

>[!NOTE]
>大部分的組態設定在 Teams 和 商務用 Skype Online 之間很常見。 您可以使用Microsoft 365 系統管理中心和Microsoft Teams系統管理中心來設定這些設定。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>決策點</td><td><ul><li>神秘負責監督上線檢查清單的完成情況嗎？</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>後續步驟</td><td><ul><li>下載上線檢查清單。</li><li>依照貴組織的部署計畫逐步執行上線檢查清單專案。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>繼續上線

完成這些檢查清單之後，您就可以成功將語音功能新增至Teams部署。

在下一個步驟中，使用 [Voice (Playbook 的網站啟用播放簿) ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 來協助您在每一個網站上設定使用者，並協助確保您規劃和執行重要的網站特定活動。

-   依網站部署規劃準備就緒的網站

-   建立服務管理程式

-   執行測試與補救

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>測試 Teams 中的雲端語音工作負載

在您將Teams雲端語音業務成功與技術實作計畫定義並記錄為 [想像] 階段的一部分，並在系統管理中心中執行您想要的設定之後，下一步是驗證您組織是否能透過功能、功能和可用性來達成您的期望和需求。 在您的生產環境中部署試驗或最終部署之前，您應該先執行此驗證步驟。

您可以運用您在 [想像] 階段定義的商務成功計畫，做為判斷要在測試階段期間評估的活動、預期、功能測試案例和整體範圍的基礎。

## <a name="define-your-testing-approach"></a>定義您的測試方法

以最簡單的形式來說，您的測試方法是根據您檢閱音訊會議、通話方案或直接路由服務的功能功能，並開發測試計劃來確認符合範圍內使用者的功能需求。 下列是音訊會議實作之 [上線] 階段的範例測試計劃。


| 音訊會議要測試的功能 | 結果摘要 | 其他筆記 |
|------------|-----------------|------------------|
| 排程包含音訊會議撥入資訊的臨時Teams會議 | 傳遞/失敗   | 待定 |
| 從 PSTN 撥入會議並提供撥入資訊，以使用電話進行會議音訊 | 傳遞/失敗 | 待定 |
| 透過 PSTN 撥出電話，加入其他人至現有的會議 | 傳遞/失敗 | 待定 |



| 要測試的通話方案或直接路由功能 | 結果摘要 | 其他筆記 |
|----------------------------------------------------|-----------------|------------------|
| 撥打 PSTN 號碼撥打 PSTN 電話       | 傳遞/失敗       | 待定 |
| 從行動電話、有線電話 (外部電話線撥打 PSTN 號碼來接聽 PSTN 電話)  | 傳遞/失敗 | 待定|
| 將 PSTN 電話從一個Teams使用者轉接至另一個使用者 | 傳遞/失敗 | 待定 |


>[!TIP]
>若要協助建立測試案例做為起點，請參閱[Teams會議和通話](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)中可用的使用者指導方針清單。

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>設定Teams的雲端語音工作負載

現在您已定義測試方法，下一個步驟是設定服務環境和Teams雲端語音功能範圍中的使用者。

如需詳細資訊，請參閱：

- [音訊會議的技術規劃](./cloud-voice-landing-page.md)

- [設定 Microsoft Teams 的音訊會議](set-up-audio-conferencing-in-teams.md)

- [使用通話方案電話系統的技術規劃](calling-plan-landing-page.md)

- [設定 商務用 Skype 和 Microsoft Teams 的通話方案](/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [規劃直接路由](./direct-routing-plan.md)

- [設定直接路由](./direct-routing-configure.md)

### <a name="execute-the-test-plan"></a>執行測試計劃

[//]: # (編輯正常嗎？「使用者」對我有點不明確。)
設定使用者環境和服務之後，測試的最後一個步驟包括測試計劃執行，並著重于功能驗證。 

**音訊會議測試範圍中使用者和網站的先決條件和假設：**

-   已完成音訊會議服務的商務用案例定義。

-   音訊會議所需的授權可供使用，並已指派授權。

-   已識別組織網站和使用者群組的清單。

-   已識別並設定具有語言喜好設定的專用和共用音訊會議撥號號碼清單。

-   [如果您](what-are-communications-credits.md) 的組織已設定必要) ，通訊點數 (。

-   已識別音訊會議會議橋接器設定，並設定 (PIN 長度、進入/結束通知、啟用通知喜好設定) 。

-   已識別、設定及套用支援音訊會議撥出案例的租使用者會議原則和撥號對應表設定。

-   音訊會議已識別並設定合規性要求。

**通話方案測試的必要條件和假設適用于範圍內的使用者和網站：**

-   通話方案服務的企業使用案例定義已經完成。

-   通話方案所需的授權可供使用且已指派。

-   已識別組織網站和使用者群組的清單。

-   電話已取得或移轉給 Microsoft，且可在租使用者入口網站中取得或移轉給使用者的號碼。

-   [如果您](what-are-communications-credits.md) 的組織已設定必要) ，通訊點數 (。

-   已識別、設定及套用支援通話方案案例的租使用者使用者原則和撥號對應表設定。

-   已識別並設定通話方案合規性要求。

**使用者和網站範圍內的直接路由測試先決條件和假設：**

-   已完成直接路由服務的企業使用案例定義。

-   直接路由所需的授權可供使用且已指派。

-   已識別組織網站和使用者群組的清單。

-   已部署、設定及配對[SBC)  (認證的會話框線控制器](./direct-routing-plan.md#supported-session-border-controllers-sbcs)電話系統。

-   Enterprise已啟用語音，而且已指派電話號碼。

-   已識別、設定和指派語音路由原則。

-   Microsoft Teams設定為範圍內使用者的慣用通話用戶端。
 
-   已識別並設定直接路由合規性需求。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>決策點</td><td><ul><li>決定要 (服務決策) 部署哪些音訊會議功能。</li><li>識別音訊會議的使用者功能需求。</li><li>找出音訊會議的服務設定需求。</li><br><li>決定是否要部署和設定直接路由或通話方案。<li>決定要部署哪些電話系統功能 (服務決策) 。</li><li>找出通話方案或直接路由的使用者功能需求。</li><li>找出通話方案或直接路由的服務設定需求。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>後續步驟</td><td><ul><li>開發並記錄您的測試計劃方法。</li><li>針對音訊會議功能，為您的服務環境和使用者做好準備。</li><li>針對通話方案或直接路由功能，準備您的服務環境和範圍內的使用者。</li><li>針對您要啟用的音訊會議功能執行測試驗證。</li><li>針對您要啟用的通話方案或直接路由功能執行測試驗證。</li><li>對於任何測試失敗，請確認您的設定正確無誤，檢閱社群文章，並視需要提出支援案例。</li></ul></td></tr>
</table>


如需有關如何在 Teams 中執行音訊會議測試的其他詳細指導方針，請參閱[音訊會議的詳細測試指南](./deploy-audio-conferencing-teams-landing-page.md)。

如需有關如何在 Teams 中執行通話方案測試的其他詳細指導方針，請參閱[電話系統的詳細測試指南](./cloud-voice-landing-page.md)。

<!--ENDOFSECTION-->